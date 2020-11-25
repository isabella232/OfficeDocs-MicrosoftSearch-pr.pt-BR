---
title: Oracle SQL Connector para Microsoft Search
ms.author: vivg
author: Vivek
manager: harshkum
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Configurar o Oracle SQL Connector para o Microsoft Search.
ms.openlocfilehash: 794ba81778ae5acf30c539f78390872579ac5467
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408911"
---
# <a name="oracle-sql-connector"></a>SQL Connector do Oracle

Com o Oracle SQL Connector, sua organização pode descobrir e indexar dados de um banco de dados Oracle local. O conector indexa o conteúdo especificado na pesquisa da Microsoft. Para manter o índice atualizado com os dados de origem, ele oferece suporte a rastreamentos completos e incrementais periódicos. Com o SQL Connector do Oracle, você também pode restringir o acesso aos resultados de pesquisa de determinados usuários.

Este artigo é para os administradores do Microsoft 365 ou qualquer pessoa que configure, execute e monitore um SQL Server Connector Oracle. Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.

## <a name="install-the-graph-connector-agent"></a>Instalar o agente do conector do Graph

Para acessar seus dados de terceiros locais, você deve instalar e configurar o agente do conector do Graph. Confira [instalar o agente do conector do Graph](on-prem-agent.md) para saber mais.  

## <a name="connect-to-a-data-source"></a>Conectar-se a uma fonte de dados

Para conectar seu SQL Connector do Oracle a uma fonte de dados, você deve configurar o servidor de banco de dados que deseja rastrear e o agente de conector de gráfico local. Em seguida, você pode se conectar ao banco de dados com o método de autenticação necessário.

Para o Oracle SQL Connector, você precisa especificar o nome do host, a porta e o nome do serviço (banco de dados), juntamente com o método de autenticação preferencial, o nome de usuário e a senha.

> [!NOTE]
> Seu banco de dados deve executar o Oracle Database versão 11g ou posterior para que o conector possa se conectar. O conector suporta o banco de dados Oracle hospedado nas plataformas Windows, Linux e VM do Azure.

Para pesquisar seu conteúdo de banco de dados, você deve especificar consultas SQL ao configurar o conector. Essas consultas SQL precisam nomear todas as colunas do banco de dados que você deseja indexar (ou seja, propriedades de origem), incluindo quaisquer junções SQL que precisam ser executadas para obter todas as colunas. Para restringir o acesso aos resultados da pesquisa, você deve especificar listas de controle de acesso (ACLs) em consultas SQL ao configurar o conector.

## <a name="full-crawl-required"></a>Rastreamento completo (obrigatório)

Nesta etapa, você configura a consulta SQL que executa um rastreamento completo do banco de dados. O rastreamento completo seleciona todas as colunas ou propriedades que você deseja tornar **consultáveis**, **pesquisáveis** ou **recuperáveis**. Você também pode especificar colunas ACL para restringir o acesso de resultados de pesquisa a usuários ou grupos específicos.

> [!Tip]
> Para obter todas as colunas necessárias, você pode ingressar em várias tabelas.

![Script mostrando as propriedades Ordertable e AclTable com exemplo](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Selecionar colunas de dados (obrigatórias) e colunas ACL (opcional)

O exemplo demonstra a seleção de cinco colunas de dados que armazenam os dados da pesquisa: NúmeroDoPedido, OrderTitle, OrderDesc, CreatedDateTime e IsDeleted. Para definir as permissões de exibição para cada linha de dados, você pode, opcionalmente, selecionar essas colunas de ACL: AllowedUsers, AllowedGroups, DeniedUsers e DeniedGroups. Todas essas colunas de dados podem se tornar **consultáveis**, **pesquisáveis** ou **recuperáveis**.

Selecione colunas de dados, conforme mostrado neste exemplo de consulta: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Para gerenciar o acesso aos resultados da pesquisa, você pode especificar uma ou mais colunas ACL na consulta. O conector SQL permite controlar o acesso no nível de registro. Você pode optar por ter o mesmo controle de acesso para todos os registros em uma tabela. Se as informações de ACL forem armazenadas em uma tabela separada, talvez seja necessário fazer uma junção com essas tabelas em sua consulta.

O uso de cada uma das colunas ACL na consulta acima é descrita abaixo. A lista a seguir explica os quatro **mecanismos de controle de acesso**.

* **AllowedUsers**: especifica a lista de IDs de usuário que poderão acessar os resultados da pesquisa. No exemplo a seguir, a lista de usuários: john@contoso.com, keith@contoso.com e lisa@contoso.com teria apenas acesso a um registro com NúmeroDoPedido = 12.
* **AllowedGroups**: especifica o grupo de usuários que poderá acessar os resultados da pesquisa. No exemplo a seguir, o grupo sales-team@contoso.com só teria acesso ao registro com NúmeroDoPedido = 12.
* **DeniedUsers**: especifica a lista de usuários que **não** têm acesso aos resultados da pesquisa. No exemplo a seguir, os usuários john@contoso.com e keith@contoso.com não têm acesso ao registro com NúmeroDoPedido = 13, enquanto todas as outras pessoas têm acesso a esse registro.
* **DeniedGroups**: especifica o grupo de usuários que **não** têm acesso aos resultados da pesquisa. No exemplo a seguir, os grupos engg-team@contoso.com e pm-team@contoso.com não têm acesso ao registro com NúmeroDoPedido = 15, enquanto todas as outras pessoas têm acesso a esse registro.  

![Dados de exemplo mostrando as propriedades Ordertable e AclTable com exemplo](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Tipos de dados com suporte

A tabela a seguir resume os tipos de dados suportados pelo SQL Connector do Oracle. A tabela também resume o tipo de dados de indexação para o tipo de dados SQL suportado. Para saber mais sobre os tipos de dados compatíveis com conectores do Microsoft Graph para indexação, consulte a documentação sobre [tipos de recurso de propriedade](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties).

| Categoria | Tipo de dados de origem | Tipo de dados de indexação |
| ------------ | ------------ | ------------ |
| Tipo de dados número | NÚMERO (p, 0) | Int64 (para p <= 18) <br> Double (para p > 18) |
| Tipo de dados numéricos de ponto flutuante | NÚMERO (p, s) <br> FLUTUAr (p) | double |
| Tipo de dados de data | DATA <br> REGISTRA <br> CARIMBO de data/hora (n) | datetime |
| Tipo de dados character | CHAR (n) <br> VARCHAR <br> VARCHAR2 <br> Longas <br> CLOB <br> NCLOB | string |
| Tipo de dados de caractere Unicode | NCHAR <br> NVARCHAR | string |
| Tipo de dados de RowID | ROWID <br> UROWID | string |

Para qualquer outro tipo de dados atualmente não suportado, a coluna precisa ser explicitamente convertida para um tipo de dados com suporte.

### <a name="watermark-required"></a>Marca d' água (obrigatório)

Para evitar a sobrecarga do banco de dados, o conector batche e retoma consultas de rastreamento completo com uma coluna de marca d' água de rastreamento completo. Usando o valor da coluna watermark, cada lote subsequente é buscado e a consulta é retomada do último ponto de verificação. Essencialmente, este é um mecanismo para controlar a atualização de dados para rastreamentos completos.

Criar trechos de consulta para marcas d' água, conforme mostrado nestes exemplos:

* `WHERE (CreatedDateTime > @watermark)`. Cite o nome da coluna da marca d' água com a palavra-chave reservada `@watermark` . Só é possível classificar a coluna de marca d' água em ordem crescente.
* `ORDER BY CreatedDateTime ASC`. Classifique na coluna de marca d' água em ordem crescente.

Na configuração mostrada na imagem a seguir, `CreatedDateTime` é a coluna de marca d' água selecionada. Para buscar o primeiro lote de linhas, especifique o tipo de dados da coluna de marca d' água. Nesse caso, o tipo de dados é `DateTime` .

![Configuração da coluna de marca d' água](media/MSSQL-watermark.png)

A primeira consulta busca o primeiro número **N** de linhas usando: "CreatedDateTime > 1 de janeiro de 1753 00:00:00" (valor mínimo de data e hora). Após o primeiro lote ser obtido, o valor mais alto de `CreatedDateTime` retornado no lote é salvo como o ponto de verificação se as linhas forem classificadas em ordem crescente. Um exemplo é 1 de março de 2019 03:00:00. Em seguida, o próximo lote de **N** linhas é buscado usando "CreatedDateTime > 1 de março de 2019 03:00:00" na consulta.

### <a name="skipping-soft-deleted-rows-optional"></a>Ignorando linhas excluídas por software (opcional)

Para excluir as linhas excluídas de forma reversível em seu banco de dados, especifique o nome da coluna de exclusão reversível e o valor que indica que a linha foi excluída.

![Configurações de exclusão reversível: "coluna de exclusão reversível" e "valor da coluna de exclusão reversível que indica uma linha excluída"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Rastreamento completo: gerenciar permissões de pesquisa

Clique em **gerenciar permissões** para selecionar as várias colunas de controle de acesso (ACL) que especificam o mecanismo de controle de acesso. Selecione o nome da coluna que você especificou na consulta SQL de rastreamento completo.

Cada uma das colunas ACL deve ser uma coluna de vários valores. Esses valores de ID múltiplos podem ser separados por separadores como ponto-e-vírgula (;), vírgula (,) e assim por diante. Você precisa especificar esse separador no campo **separador de valores** .

Os seguintes tipos de ID têm suporte para o uso como ACLs:

* **Nome principal do usuário (UPN)**: um nome de usuário principal (UPN) é o nome de um usuário do sistema em um formato de endereço de email. Um UPN (por exemplo: john.doe@domain.com) consiste do nome de usuário (nome de logon), separador (o símbolo @) e nome de domínio (sufixo UPN).
* **ID do Azure Active Directory (AAD)**: no Azure AD, cada usuário ou grupo tem uma ID de objeto que se parece com algo como ' e0d3ad3d-0000-1111-2222-3c5f5c52ab9b '
* **ID de segurança do Active Directory (AD)**: em uma instalação do AD local, todos os usuários e grupos têm um identificador de segurança imutável e exclusivo que se parece com o valor-1-5-21-3878594291-2115959936-132693609-65242.

![Configurações de permissão de pesquisa para configurar listas de controle de acesso](media/MSSQL-ACL2.png)

## <a name="incremental-crawl-optional"></a>Rastreamento incremental (opcional)

Nesta etapa opcional, forneça uma consulta SQL para executar um rastreamento incremental do banco de dados. Com essa consulta, o conector SQL determina quaisquer alterações nos dados desde o último rastreamento incremental. Como no rastreamento completo, selecione todas as colunas que você deseja tornar **consultáveis**, **pesquisáveis** ou **recuperáveis**. Especifique o mesmo conjunto de colunas de ACL que você especificou na consulta de rastreamento completo.

Os componentes da imagem a seguir são semelhantes aos componentes de rastreamento completo com uma exceção. Nesse caso, "ModifiedDatetime" é a coluna de marca d' água selecionada. Revise as [etapas de rastreamento completo](#full-crawl-required) para saber como escrever sua consulta de rastreamento incremental e consulte a imagem a seguir como um exemplo.

![O script de rastreamento incremental mostrando as propriedades Ordertable, AclTable e example que podem ser usadas.](media/MSSQL-incrcrawl.png)

## <a name="manage-search-permissions"></a>Gerenciar permissões de pesquisa

Você pode optar por usar as [ACLs especificadas na tela de rastreamento completo](#full-crawl-manage-search-permissions) ou pode substituí-las para tornar o conteúdo visível para todos.

## <a name="set-the-refresh-schedule"></a>Definir o agendamento de atualização

O Oracle SQL Connector suporta agendas de atualização para rastreamentos completos e incrementais. Recomendamos que você defina ambas.

Um cronograma de rastreamento completo localiza linhas excluídas que foram previamente sincronizadas com o índice de pesquisa da Microsoft e quaisquer linhas que foram movidas para o filtro de sincronização. Quando você se conecta ao banco de dados pela primeira vez, um rastreamento completo é executado para sincronizar todas as linhas recuperadas da consulta de rastreamento completo. Para sincronizar novas linhas e fazer atualizações, você precisa agendar rastreamentos incrementais.

## <a name="next-steps-customize-the-search-results-page"></a>Próximas etapas: personalizar a página de resultados de pesquisa

Crie seus próprios tipos de resultados e verticais para que os usuários finais possam exibir os resultados de pesquisa de novas conexões. Sem esta etapa, os dados da sua conexão não aparecerão na página de resultados da pesquisa.

Para saber mais sobre como criar seus verticais e MRTs, confira [personalização da página de resultados da pesquisa](customize-search-page.md).

## <a name="limitations"></a>Limitações

O Oracle SQL Connector tem essas limitações na versão prévia:

* O banco de dados local deve executar o Oracle Database versão 11g ou posterior.
* As ACLs só são compatíveis com o uso de um UPN (nome principal de usuário), do Azure Active Directory (Azure AD) ou da segurança do Active Directory.
* Não há suporte para indexação de conteúdo avançado nas colunas do banco de dados. Exemplos desse tipo de conteúdo são HTML, JSON, XML, BLOBs e análises de documento que existem como links dentro das colunas do banco de dados.

## <a name="troubleshooting-guide"></a>Guia de solução de problemas

Abaixo está uma lista de erros comuns observados durante a configuração do conector e seus possíveis motivos.
| Etapa de configuração | Mensagem de erro | Possível motivo (s) |
| ------------ | ------------ | ------------ |
| Configurações do banco de dados | Erro do servidor de banco de dados: a solicitação de conexão atingiu o tempo limite | Nome de host inválido <br> Host inacessível |
| Configurações do banco de dados | Erro do servidor de banco de dados: ORA-12541: TNS: não listner | Porta inválida |
| Configurações do banco de dados | Erro do servidor de banco de dados: ORA-12514: TNS: o listner não está ciente de serviço solicitado no descritor de conector | Nome de serviço (banco de dados) inválido |
| Configurações do banco de dados | Erro do servidor de banco de dados: falha de logon para o usuário ' `user` '. | Nome de usuário ou senha inválido |
