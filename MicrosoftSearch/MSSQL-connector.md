---
title: Microsoft SQL Connector para pesquisa da Microsoft
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
description: Configurar o Microsoft SQL Connector para o Microsoft Search.
ms.openlocfilehash: a073a6d3f226e5f8b0ea297494a8889f1f50bab1
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626752"
---
# <a name="microsoft-sql-server-connector"></a>Microsoft SQL Server Connector

Com o Microsoft SQL Server Connector, sua organização pode descobrir e indexar dados de um banco de dados do SQL Server local. O conector indexa o conteúdo especificado na pesquisa da Microsoft. Para manter o índice atualizado com os dados de origem, ele oferece suporte a rastreamentos completos e incrementais periódicos. Com o SQL Server Connector, você também pode restringir o acesso aos resultados da pesquisa para determinados usuários.

Este artigo é para os administradores do Microsoft 365 ou qualquer pessoa que configure, execute e monitore um Microsoft SQL Server Connector. Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.

## <a name="install-a-data-gateway"></a>Instalar um data gateway
Para acessar seus dados de terceiros, você deve instalar e configurar um gateway do Microsoft Power BI. Consulte [Install and local gateway on-premises](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) para saber mais.  

## <a name="connect-to-a-data-source"></a>Conectar-se a uma fonte de dados
Para conectar o Microsoft SQL Server Connector a uma fonte de dados, você deve configurar o servidor de banco de dados que deseja rastrear e o gateway local. Em seguida, você pode se conectar ao banco de dados com o método de autenticação necessário.

> [!NOTE]
> Seu banco de dados deve executar o SQL Server versão 2008 ou posterior.

Para pesquisar seu conteúdo de banco de dados, você deve especificar consultas SQL ao configurar o conector. Essas consultas SQL precisam nomear todas as colunas do banco de dados que você deseja indexar (ou seja, propriedades de origem), incluindo quaisquer junções SQL que precisam ser executadas para obter todas as colunas. Para restringir o acesso aos resultados da pesquisa, você deve especificar listas de controle de acesso (ACLs) com consultas SQL ao configurar o Microsoft SQL Server Connector.

## <a name="full-crawl-required"></a>Rastreamento completo (obrigatório)
Nesta etapa, você configura a consulta SQL que executa um rastreamento completo do banco de dados. O rastreamento completo seleciona todas as colunas ou propriedades que você deseja tornar **consultáveis**, **pesquisáveis**ou **recuperáveis**. Você também pode especificar colunas ACL para restringir o acesso de resultados de pesquisa a usuários ou grupos específicos.

> [!Tip]
> Para obter todas as colunas necessárias, você pode ingressar em várias tabelas.

![Script mostrando as propriedades Ordertable e AclTable com exemplo](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Selecionar colunas de dados (obrigatórias) e colunas ACL (opcional)
O exemplo demonstra a seleção de cinco colunas de dados que armazenam os dados da pesquisa: NúmeroDoPedido, OrderTitle, OrderDesc, CreatedDateTime e IsDeleted. Para definir as permissões de exibição para cada linha de dados, você pode, opcionalmente, selecionar essas colunas de ACL: AllowedUsers, AllowedGroups, DeniedUsers e DeniedGroups. Todas essas colunas de dados podem se tornar **consultáveis**, **pesquisáveis**ou **recuperáveis**.

Selecione colunas de dados, conforme mostrado neste exemplo de consulta:`SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

### <a name="watermark-required"></a>Marca d' água (obrigatório)
Para evitar a sobrecarga do banco de dados, o conector batche e retoma consultas de rastreamento completo com uma coluna de marca d' água de rastreamento completo. Usando o valor da coluna watermark, cada lote subsequente é buscado e a consulta é retomada do último ponto de verificação. Essencialmente, este é um mecanismo para controlar a atualização de dados para rastreamentos completos.

Criar trechos de consulta para marcas d' água, conforme mostrado nestes exemplos:
* `WHERE (CreatedDateTime > @watermark)`. Cite o nome da coluna da marca d' água `@watermark`com a palavra-chave reservada. Se a ordem de classificação da coluna de marca d' água for crescente `>`, use; caso contrário, `<`use.
* `ORDER BY CreatedDateTime ASC`. Classifique na coluna de marca d' água em ordem crescente ou decrescente.

Na configuração mostrada na imagem a seguir, `CreatedDateTime` é a coluna de marca d' água selecionada. Para buscar o primeiro lote de linhas, especifique o tipo de dados da coluna de marca d' água. Nesse caso, o tipo de dados é `DateTime`.

![](media/MSSQL-watermark.png)

A primeira consulta busca a **primeira quantidade de** linhas usando: "CreatedDateTime > 1 de janeiro de 1753 00:00:00" (o valor mín do tipo de dados DateTime). Após o primeiro lote ser obtido, o valor mais alto de `CreatedDateTime` retornado no lote é salvo como o ponto de verificação se as linhas forem classificadas em ordem crescente. Um exemplo é 1 de março de 2019 03:00:00. Em seguida, o próximo lote de **N** linhas é buscado usando "CreatedDateTime > 1 de março de 2019 03:00:00" na consulta.

### <a name="skipping-soft-deleted-rows-optional"></a>Ignorando linhas excluídas por software (opcional)
Para excluir as linhas excluídas de forma reversível em seu banco de dados, especifique o nome da coluna de exclusão reversível e o valor que indica que a linha foi excluída.

![Configurações de exclusão reversível: "coluna de exclusão reversível" e "valor da coluna de exclusão reversível que indica uma linha excluída"](media/MSSQL-softdelete.png)

## <a name="incremental-crawl-optional"></a>Rastreamento incremental (opcional)
Nesta etapa opcional, forneça uma consulta SQL para executar um rastreamento incremental do banco de dados. Com essa consulta, o Microsoft SQL Server Connector faz qualquer alteração nos dados desde o último rastreamento incremental. Como no rastreamento completo, selecione todas as colunas que você deseja tornar **consultáveis**, **pesquisáveis**ou **recuperáveis**. Especifique o mesmo conjunto de colunas de ACL que você especificou na consulta de rastreamento completo.

Os componentes da imagem a seguir são semelhantes aos componentes de rastreamento completo com uma exceção. Nesse caso, "ModifiedDatetime" é a coluna de marca d' água selecionada. Revise as [etapas de rastreamento completo](#full-crawl-required) para saber como escrever sua consulta de rastreamento incremental e consulte a imagem a seguir como um exemplo.

![O script de rastreamento incremental mostrando as propriedades Ordertable, AclTable e example que podem ser usadas.](media/MSSQL-incrcrawl.png)

## <a name="limitations"></a>Limitações
O Microsoft SQL Server Connector tem essas limitações na versão prévia:
* O banco de dados local deve executar o SQL Server versão 2008 ou posterior.
* As ACLs só são compatíveis com o uso de um UPN (nome principal de usuário), do Azure Active Directory (Azure AD) ou da segurança do Active Directory.
* Não há suporte para indexação de conteúdo avançado nas colunas do banco de dados. Exemplos desse tipo de conteúdo são HTML, JSON, XML, BLOBs e análises de documento que existem como links dentro das colunas do banco de dados.

