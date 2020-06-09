---
title: Microsoft SQL Server e Azure SQL Connector para Microsoft Search
ms.author: mounika.narayanan
author: monaray
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configure o Microsoft SQL Server ou o Azure SQL Connector para Microsoft Search.
ms.openlocfilehash: adb923527576a72663efe3a069918f38a5e89526
ms.sourcegitcommit: 64eea81f8c1db9ee955013462a7b51612fb7d0b7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2020
ms.locfileid: "44604397"
---
# <a name="microsoft-sql-server-and-azure-sql-connector"></a>Microsoft SQL Server e Azure SQL Connector

Com o Microsoft SQL Server ou o Azure SQL Connector, sua organização pode descobrir e indexar dados de um banco de dados do SQL Server local ou de um banco de dados hospedado em sua instância do Azure SQL na nuvem. O conector indexa o conteúdo especificado na pesquisa da Microsoft. Para manter o índice atualizado com os dados de origem, ele oferece suporte a rastreamentos completos e incrementais periódicos. Com esses conectores SQL, você também pode restringir o acesso aos resultados de pesquisa de determinados usuários.

Este artigo é para os administradores do Microsoft 365 ou qualquer pessoa que configure, execute e monitore um Microsoft SQL Server Connector. Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.

## <a name="install-a-data-gateway-required-for-on-premises-microsoft-sql-server-connector-only"></a>Instalar um data gateway (necessário somente para o Microsoft SQL Server Connector local)
Para acessar seus dados de terceiros, você deve instalar e configurar um gateway do Microsoft Power BI. Confira [instalar um gateway local](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) para saber mais.  

## <a name="connect-to-a-data-source"></a>Conectar-se a uma fonte de dados
Para conectar o Microsoft SQL Server Connector a uma fonte de dados, você deve configurar o servidor de banco de dados que deseja rastrear e o gateway local. Em seguida, você pode se conectar ao banco de dados com o método de autenticação necessário.

Para o Azure SQL Connector, é necessário especificar apenas o nome do servidor ou o endereço IP ao qual você deseja se conectar. O Azure SQL Connector só oferece suporte à autenticação do Azure Active Directory Open ID Connect (OIDC) para se conectar ao banco de dados.

> [!NOTE]
> Seu banco de dados deve executar o SQL Server versão 2008 ou posterior para que o Microsoft SQL Server Connector possa se conectar a ele

Para pesquisar seu conteúdo de banco de dados, você deve especificar consultas SQL ao configurar o conector. Essas consultas SQL precisam nomear todas as colunas do banco de dados que você deseja indexar (ou seja, propriedades de origem), incluindo quaisquer junções SQL que precisam ser executadas para obter todas as colunas. Para restringir o acesso aos resultados da pesquisa, você deve especificar listas de controle de acesso (ACLs) em consultas SQL ao configurar o conector.

## <a name="full-crawl-required"></a>Rastreamento completo (obrigatório)
Nesta etapa, você configura a consulta SQL que executa um rastreamento completo do banco de dados. O rastreamento completo seleciona todas as colunas ou propriedades que você deseja tornar **consultáveis**, **pesquisáveis**ou **recuperáveis**. Você também pode especificar colunas ACL para restringir o acesso de resultados de pesquisa a usuários ou grupos específicos.

> [!Tip]
> Para obter todas as colunas necessárias, você pode ingressar em várias tabelas.

![Script mostrando as propriedades Ordertable e AclTable com exemplo](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Selecionar colunas de dados (obrigatórias) e colunas ACL (opcional)
O exemplo demonstra a seleção de cinco colunas de dados que armazenam os dados da pesquisa: NúmeroDoPedido, OrderTitle, OrderDesc, CreatedDateTime e IsDeleted. Para definir as permissões de exibição para cada linha de dados, você pode, opcionalmente, selecionar essas colunas de ACL: AllowedUsers, AllowedGroups, DeniedUsers e DeniedGroups. Todas essas colunas de dados podem se tornar **consultáveis**, **pesquisáveis**ou **recuperáveis**.

Selecione colunas de dados, conforme mostrado neste exemplo de consulta:`SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`
 
Para gerenciar o acesso aos resultados da pesquisa, você pode especificar uma ou mais colunas ACL na consulta. O conector SQL permite controlar o acesso no nível de registro. Você pode optar por ter o mesmo controle de acesso para todos os registros em uma tabela. Se as informações de ACL forem armazenadas em uma tabela separada, talvez seja necessário fazer uma junção com essas tabelas em sua consulta.

O uso de cada uma das colunas ACL na consulta acima é descrita abaixo. A lista a seguir explica os quatro **mecanismos de controle de acesso**. 
* **AllowedUsers**: especifica a lista de IDs de usuário que poderão acessar os resultados da pesquisa. No exemplo a seguir, a lista de usuários: john@contoso.com, keith@contoso.com e lisa@contoso.com teria apenas acesso a um registro com NúmeroDoPedido = 12. 
* **AllowedGroups**: especifica o grupo de usuários que poderá acessar os resultados da pesquisa. No exemplo a seguir, o grupo sales-team@contoso.com só teria acesso ao registro com NúmeroDoPedido = 12.
* **DeniedUsers**: especifica a lista de usuários que **não** têm acesso aos resultados da pesquisa. No exemplo a seguir, os usuários john@contoso.com e keith@contoso.com não têm acesso ao registro com NúmeroDoPedido = 13, enquanto todas as outras pessoas têm acesso a esse registro. 
* **DeniedGroups**: especifica o grupo de usuários que **não** têm acesso aos resultados da pesquisa. No exemplo a seguir, os grupos engg-team@contoso.com e pm-team@contoso.com não têm acesso ao registro com NúmeroDoPedido = 15, enquanto todas as outras pessoas têm acesso a esse registro.  

![](media/MSSQL-ACL1.png)

### <a name="watermark-required"></a>Marca d' água (obrigatório)
Para evitar a sobrecarga do banco de dados, o conector batche e retoma consultas de rastreamento completo com uma coluna de marca d' água de rastreamento completo. Usando o valor da coluna watermark, cada lote subsequente é buscado e a consulta é retomada do último ponto de verificação. Essencialmente, este é um mecanismo para controlar a atualização de dados para rastreamentos completos.

Criar trechos de consulta para marcas d' água, conforme mostrado nestes exemplos:
* `WHERE (CreatedDateTime > @watermark)`. Cite o nome da coluna da marca d' água com a palavra-chave reservada `@watermark` . Se a ordem de classificação da coluna de marca d' água for crescente, use `>` ; caso contrário, use `<` .
* `ORDER BY CreatedDateTime ASC`. Classifique na coluna de marca d' água em ordem crescente ou decrescente.

Na configuração mostrada na imagem a seguir, `CreatedDateTime` é a coluna de marca d' água selecionada. Para buscar o primeiro lote de linhas, especifique o tipo de dados da coluna de marca d' água. Nesse caso, o tipo de dados é `DateTime` .

![](media/MSSQL-watermark.png)

A primeira consulta busca a **primeira quantidade de** linhas usando: "CreatedDateTime > 1 de janeiro de 1753 00:00:00" (o valor mín do tipo de dados DateTime). Após o primeiro lote ser obtido, o valor mais alto de `CreatedDateTime` retornado no lote é salvo como o ponto de verificação se as linhas forem classificadas em ordem crescente. Um exemplo é 1 de março de 2019 03:00:00. Em seguida, o próximo lote de **N** linhas é buscado usando "CreatedDateTime > 1 de março de 2019 03:00:00" na consulta.

### <a name="skipping-soft-deleted-rows-optional"></a>Ignorando linhas excluídas por software (opcional)
Para excluir as linhas excluídas de forma reversível em seu banco de dados, especifique o nome da coluna de exclusão reversível e o valor que indica que a linha foi excluída.

![Configurações de exclusão reversível: "coluna de exclusão reversível" e "valor da coluna de exclusão reversível que indica uma linha excluída"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Rastreamento completo: gerenciar permissões de pesquisa
Clique em **gerenciar permissões** para selecionar as várias colunas de controle de acesso (ACL) que especificam o mecanismo de controle de acesso. Selecione o nome da coluna que você especificou na consulta SQL de rastreamento completo. 

Cada uma das colunas ACL deve ser uma coluna de vários valores. Esses valores de ID múltiplos podem ser separados por separadores como ponto-e-vírgula (;), vírgula (,) e assim por diante. Você precisa especificar esse separador no campo **separador de valores** .
 
Os seguintes tipos de ID têm suporte para o uso como ACLs: 
* **Nome principal do usuário (UPN)**: um nome de usuário principal (UPN) é o nome de um usuário do sistema em um formato de endereço de email. Um UPN (por exemplo: john.doe@domain.com) consiste do nome de usuário (nome de logon), separador (o símbolo @) e nome de domínio (sufixo UPN). 
* **ID do Azure Active Directory (AAD)**: no AAD, cada usuário ou grupo tem uma ID de objeto que se parece com algo como ' e0d3ad3d-0000-1111-2222-3c5f5c52ab9b ' 
* **ID de segurança do Active Directory (AD)**: em uma instalação do AD local, todos os usuários e grupos têm um identificador de segurança imutável e exclusivo que se parece com o valor-1-5-21-3878594291-2115959936-132693609-65242.

![](media/MSSQL-ACL2.png)

## <a name="incremental-crawl-optional"></a>Rastreamento incremental (opcional)
Nesta etapa opcional, forneça uma consulta SQL para executar um rastreamento incremental do banco de dados. Com essa consulta, o conector SQL determina quaisquer alterações nos dados desde o último rastreamento incremental. Como no rastreamento completo, selecione todas as colunas que você deseja tornar **consultáveis**, **pesquisáveis**ou **recuperáveis**. Especifique o mesmo conjunto de colunas de ACL que você especificou na consulta de rastreamento completo.

Os componentes da imagem a seguir são semelhantes aos componentes de rastreamento completo com uma exceção. Nesse caso, "ModifiedDatetime" é a coluna de marca d' água selecionada. Revise as [etapas de rastreamento completo](#full-crawl-required) para saber como escrever sua consulta de rastreamento incremental e consulte a imagem a seguir como um exemplo.

![O script de rastreamento incremental mostrando as propriedades Ordertable, AclTable e example que podem ser usadas.](media/MSSQL-incrcrawl.png)

## <a name="manage-search-permissions"></a>Gerenciar permissões de pesquisa 
Você pode optar por usar as [ACLs especificadas na tela de rastreamento completo](#full-crawl-manage-search-permissions) ou pode substituí-las para tornar o conteúdo visível para todos.

## <a name="limitations"></a>Limitações
Os conectores SQL têm estas limitações na versão prévia:
* Microsoft SQL Server Connector: o banco de dados local deve executar o SQL Server versão 2008 ou posterior.
* As ACLs só são compatíveis com o uso de um UPN (nome principal de usuário), do Azure Active Directory (Azure AD) ou da segurança do Active Directory. 
* Não há suporte para indexação de conteúdo avançado nas colunas do banco de dados. Exemplos desse tipo de conteúdo são HTML, JSON, XML, BLOBs e análises de documento que existem como links dentro das colunas do banco de dados.
