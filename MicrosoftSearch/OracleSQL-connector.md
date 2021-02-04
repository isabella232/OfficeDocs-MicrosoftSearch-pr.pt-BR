---
title: Conector Oracle SQL Graph para a Pesquisa da Microsoft
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Configurar o conector Oracle SQL Graph para a Pesquisa da Microsoft.
ms.openlocfilehash: 01e4cd6b04d2997ea11ef006e94ea09b03280f41
ms.sourcegitcommit: 6a7f36769e92b714588b47efb0c185eddabe6953
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099331"
---
<!---Previous ms.author:vivg --->

# <a name="oracle-sql-graph-connector"></a>Conector oracle SQL Graph

O conector Oracle SQL Graph permite que sua organização descubra e indexe dados de um banco de dados Oracle local. O conector indexa o conteúdo especificado na Pesquisa da Microsoft. Para manter o índice atualizado com os dados de origem, ele oferece suporte a rastreamentos completos e incrementais periódicos. Com o conector Oracle SQL, você também pode restringir o acesso aos resultados da pesquisa para determinados usuários.

> [!NOTE]
> Leia o [**artigo Configuração do seu conector do Graph**](configure-connector.md) para entender o processo geral de configuração de conectores do Graph.

Este artigo é destinado a qualquer pessoa que configure, seja executado e monitore um conector Oracle SQL Graph. Ele complementa o processo de instalação geral e mostra instruções que se aplicam somente ao conector Oracle SQL Graph. Este artigo também inclui informações sobre solução [de problemas](#troubleshooting) e [limitações.](#limitations)

## <a name="before-you-get-started"></a>Antes de começar

### <a name="install-the-graph-connector-agent"></a>Instalar o agente do conector do Graph

Para acessar seus dados de terceiros no local, você deve instalar e configurar o agente de conector do Graph. Consulte [Instalar o agente do conector do Graph](on-prem-agent.md) para saber mais.  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: Adicionar um conector do Graph no centro de administração do Microsoft 365

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: Nomear a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Definir as configurações de conexão

Para conectar seu conector Oracle SQL a uma fonte de dados, você deve configurar o servidor de banco de dados que deseja rastrear e o agente do conector do Graph local. Em seguida, você pode se conectar ao banco de dados com o método de autenticação necessário.

Para o conector Oracle SQL, você precisa especificar o nome do Host, Porta e Serviço (banco de dados) juntamente com o método de autenticação preferencial, o nome de usuário e a senha.

> [!NOTE]
> Seu banco de dados deve executar o banco de dados Oracle versão 11g ou posterior para que o conector possa se conectar. O conector dá suporte ao banco de dados Oracle hospedado em plataformas de VM do Windows, Linux e Azure.

Para pesquisar o conteúdo do banco de dados, você deve especificar consultas SQL ao configurar o conector. Essas consultas SQL precisam nomear todas as colunas de banco de dados que você deseja indexar (ou seja, propriedades de origem), incluindo quaisquer junções SQL que precisam ser executadas para obter todas as colunas. Para restringir o acesso aos resultados da pesquisa, você deve especificar listas de controle de acesso (ACLs) em consultas SQL ao configurar o conector.

## <a name="step-3a-full-crawl-required"></a>Etapa 3a: Rastreamento completo (obrigatório)

Nesta etapa, você configura a consulta SQL que executa um rastreamento completo do banco de dados. O rastreamento completo seleciona todas as colunas ou propriedades onde você deseja selecionar as opções **Consulta** **,** Pesquisa ou **Recuperar**. Você também pode especificar colunas ACL para restringir o acesso dos resultados da pesquisa a usuários ou grupos específicos.

> [!Tip]
> Para obter todas as colunas de que você precisa, você pode unir várias tabelas.

![Script mostrando as propriedades OrderTable e AclTable com exemplo](media/MSSQL-fullcrawl.png)

### <a name="select-data-columns-required-and-acl-columns-optional"></a>Selecionar colunas de dados (Obrigatório) e ACL (Opcional)

O exemplo demonstra a seleção de cinco colunas de dados que mantém os dados da pesquisa: OrderId, OrderTitle, OrderDesc, CreatedDateTime e IsDeleted. Para definir permissões de exibição para cada linha de dados, você pode selecionar opcionalmente estas colunas de ACL: AllowedUsers, AllowedGroups, DeniedUsers e DeniedGroups. Para todas essas colunas de dados, você pode selecionar as opções **para Consulta,** **Pesquisa** ou **Recuperar.**

Selecione colunas de dados, conforme mostrado nesta consulta de exemplo: `SELECT OrderId, OrderTitle, OrderDesc, AllowedUsers, AllowedGroups, DeniedUsers, DeniedGroups, CreatedDateTime, IsDeleted`

Para gerenciar o acesso aos resultados da pesquisa, você pode especificar uma ou mais colunas ACL na consulta. O conector SQL permite controlar o acesso por nível de registro. Você pode optar por ter o mesmo controle de acesso para todos os registros em uma tabela. Se as informações da ACL são armazenadas em uma tabela separada, talvez seja preciso fazer uma junção com essas tabelas em sua consulta.

O uso de cada uma das colunas ACL na consulta acima é descrito abaixo. A lista a seguir explica os quatro **mecanismos de controle de acesso.**

* **AllowedUsers**: esta opção especifica a lista de IDs de usuário que poderão acessar os resultados da pesquisa. No exemplo a seguir, a lista de usuários: john@contoso.com, keith@contoso.com e lisa@contoso.com só teriam acesso a um registro com OrderId = 12.
* **AllowedGroups**: esta opção especifica o grupo de usuários que poderão acessar os resultados da pesquisa. No exemplo a seguir, o grupo sales-team@contoso.com só teria acesso para gravar com OrderId = 12.
* **DeniedUsers**: esta opção especifica a lista de usuários que **não têm** acesso aos resultados da pesquisa. No exemplo a seguir, os usuários john@contoso.com e keith@contoso.com não têm acesso para gravar com OrderId = 13, enquanto todos os outros têm acesso a esse registro.
* **DeniedGroups**: esta opção especifica o grupo de usuários que **não têm** acesso aos resultados da pesquisa. No exemplo a seguir, os grupos engg-team@contoso.com e pm-team@contoso.com não têm acesso para gravar com OrderId = 15, enquanto todos os outros têm acesso a esse registro.  

![Dados de exemplo mostrando as propriedades OrderTable e AclTable com exemplo](media/MSSQL-ACL1.png)

### <a name="supported-data-types"></a>Tipos de dados com suporte

A tabela a seguir resume os tipos de dados suportados pelo conector Oracle SQL. A tabela também resume o tipo de dados de indexação para o tipo de dados SQL com suporte. Para saber mais sobre os conectores do Microsoft Graph com suporte para tipos de dados para indexação, consulte a documentação sobre tipos [de recurso de propriedade.](https://docs.microsoft.com/graph/api/resources/property?view=graph-rest-beta#properties&preserve-view=true)

| Categoria | Tipo de dados de origem | Tipo de dados de indexação |
| ------------ | ------------ | ------------ |
| Tipo de dados número | NUMBER(p,0) | int64 (para p <= 18) <br> double (para p > 18) |
| Tipo de dados de número de ponto flutuante | NUMBER(p,s) <br> FLOAT(p) | double |
| Tipo de dados de data | DATA <br> TIMESTAMP <br> TIMESTAMP(n) | datetime |
| Tipo de dados de caractere | CHAR(n) <br> VARCHAR <br> VARCHAR2 <br> LONG <br> CLOB <br> NCLOB | cadeia de caracteres |
| Tipo de dados de caractere Unicode | NCHAR <br> NVARCHAR | cadeia de caracteres |
| Tipo de dados RowID | ROWID <br> UROWID | cadeia de caracteres |

Para qualquer outro tipo de dados não suportado diretamente no momento, a coluna precisa ser explicitamente lançada para um tipo de dados com suporte.

### <a name="watermark-required"></a>Marca d'água (obrigatório)

Para evitar a sobrecarga do banco de dados, o conector lota e retoma consultas de rastreamento completo com uma coluna de marca d'água de rastreamento completo. Usando o valor da coluna de marca d'água, cada lote subsequente é buscado e a consulta é retomada a partir do último ponto de verificação. Essencialmente, esse é um mecanismo para controlar a atualização de dados para rastreamentos completos.

Crie trechos de consulta para marcas d'água, conforme mostrado nestes exemplos:

* `WHERE (CreatedDateTime > @watermark)`. Cite o nome da coluna de marca d'água com a palavra-chave `@watermark` reservada. Você só pode classificar a coluna de marca d'água em ordem crescente.
* `ORDER BY CreatedDateTime ASC`. Classificar na coluna de marca d'água em ordem crescente.

Na configuração mostrada na imagem a seguir, `CreatedDateTime` está a coluna de marca d'água selecionada. Para buscar o primeiro lote de linhas, especifique o tipo de dados da coluna de marca d'água. Nesse caso, o tipo de dados é `DateTime` .

![Configuração de colunas de marca d'água](media/MSSQL-watermark.png)

A primeira consulta busca o primeiro **número N** de linhas usando: "CreatedDateTime > January 1, 1753 00:00:00" (valor mínimo do tipo de dados DateTime). Depois que o primeiro lote é buscado, o maior valor de retornado no lote é salvo como o ponto de verificação se as linhas são ordenadas `CreatedDateTime` em ordem crescente. Um exemplo é 1º de março de 2019 03:00:00. Em seguida, o próximo lote de **linhas N** é buscado usando "CreatedDateTime > 1º de março de 2019 03:00:00" na consulta.

### <a name="skipping-soft-deleted-rows-optional"></a>Ignorar linhas excluídas de forma suave (opcional)

Para excluir as linhas excluídas de forma suave do banco de dados de serem indexadas, especifique o nome e o valor da coluna de exclusão suave que indica que a linha foi excluída.

![Configurações de exclusão suave: "Coluna exclusão suave" e "Valor da coluna exclusão suave que indica uma linha excluída"](media/MSSQL-softdelete.png)

### <a name="full-crawl-manage-search-permissions"></a>Rastreamento completo: Gerenciar permissões de pesquisa

Selecione **Gerenciar permissões para** escolher as várias colunas de controle de acesso (ACL) que especificam o mecanismo de controle de acesso. Selecione o nome da coluna que você especificou na consulta SQL de rastreamento completo.

Cada uma das colunas da ACL deve ser uma coluna de vários valores. Esses vários valores de ID podem ser separados por separadores, como ponto-e-vírgula (;), vírgula (,) e assim por diante. Você precisa especificar esse separador no campo **separador de** valor.

Os seguintes tipos de ID são suportados para uso como ACLs:

* **Nome UPN: Nome UPN** é o nome de um usuário do sistema em um formato de endereço de email. Um UPN (por exemplo: john.doe@domain.com) consiste no nome de usuário (nome de logon), separador (o símbolo @) e nome de domínio (sufixo UPN).
* **ID do Azure Active Directory (AAD)**: no Azure AD, cada usuário ou grupo tem uma ID de objeto parecida com 'e0d3ad3d-0000-1111-2222-3c5f5c52ab9b'
* ID de Segurança do **Active Directory (AD),** em uma configuração do AD local, cada usuário e grupo tem um identificador de segurança imutável e exclusivo que se parece com 'S-1-5-21-3878594291-2115959936-132693609-65242.'

![Configurações de permissão de pesquisa para configurar listas de controle de acesso](media/MSSQL-ACL2.png)

## <a name="step-3b-incremental-crawl-optional"></a>Etapa 3b: Rastreamento incremental (opcional)

Nesta etapa opcional, forneça uma consulta SQL para executar um rastreamento incremental do banco de dados. Com essa consulta, o conector SQL determina as alterações nos dados desde o último rastreamento incremental. Como no rastreamento completo, selecione entre as opções **Consulta**, **Pesquisa** ou **Recuperar**. Especifique o mesmo conjunto de colunas ACL que você especificou na consulta de rastreamento completo.

Os componentes na imagem a seguir são semelhantes aos componentes de rastreamento completo, com uma exceção. Nesse caso, "ModifiedDateTime" é a coluna de marca d'água selecionada. Revise as [etapas completas do](#step-3a-full-crawl-required) rastreamento para saber como escrever sua consulta de rastreamento incremental e veja a imagem a seguir como exemplo.

![Script de rastreamento incremental mostrando as propriedades OrderTable, AclTable e exemplo que podem ser usadas.](media/MSSQL-incrcrawl.png)

## <a name="step-4-assign-property-labels"></a>Etapa 4: Atribuir rótulos de propriedade

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-5-manage-schema"></a>Etapa 5: Gerenciar esquema

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-search-permissions"></a>Etapa 6: Gerenciar permissões de pesquisa

Você pode optar por usar as [ACLs especificadas](#full-crawl-manage-search-permissions) na tela de rastreamento completa ou substituí-las para tornar seu conteúdo visível para todos.

## <a name="step-7-choose-refresh-settings"></a>Etapa 7: Escolher configurações de atualização

O conector Oracle SQL dá suporte a agendamentos de atualização para rastreamentos completos e incrementais. Recomendamos que você de definir ambos.

Um cronograma de rastreamento completo localiza linhas excluídas que foram sincronizadas anteriormente com o índice da Pesquisa da Microsoft e quaisquer linhas que foram movidas do filtro de sincronização. Quando você se conecta pela primeira vez ao banco de dados, um rastreamento completo é executado para sincronizar todas as linhas recuperadas da consulta de rastreamento completo. Para sincronizar novas linhas e fazer atualizações, você precisa agendar rastreamentos incrementais.

## <a name="step-8-review-connection"></a>Etapa 8: Analisar a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="next-steps-customize-the-search-results-page"></a>Próximas etapas: Personalizar a página de resultados da pesquisa

Crie seus próprios tipos de resultados e verticais, para que os usuários finais possam exibir os resultados da pesquisa a partir de novas conexões. Sem essa etapa, os dados da conexão não aparecerão na página de resultados da pesquisa.

Para saber mais sobre como criar seus itens verticais e MRTs, consulte [Personalização da página de resultados de pesquisa.](customize-search-page.md)

## <a name="troubleshooting"></a>Solução de problemas

Abaixo está uma lista de erros comuns observados durante a configuração do conector e seus possíveis motivos.

| Etapa de configuração | Mensagem de erro | Possíveis motivos |
| ------------ | ------------ | ------------ |
| Configurações do banco de dados | Erro do servidor de banco de dados: Solicitação de conexão com tempo final | Nome de host inválido <br> Host não acessível |
| Configurações do banco de dados | Erro do servidor de banco de dados: ORA-12541: TNS: Sem ouvinte | Porta inválida |
| Configurações do banco de dados | Erro do servidor de banco de dados: ORA-12514: TNS: ouvinte atualmente não sabe do serviço solicitado no descritor de conector | Nome de serviço (banco de dados) inválido |
| Configurações do banco de dados | Erro do servidor de banco de dados: Falha de logon para o `user` usuário ''. | Nome de usuário ou senha inválido |

## <a name="limitations"></a>Limitações

O conector Oracle SQL tem estas limitações na versão de visualização:

* O banco de dados local deve executar o Banco de Dados Oracle versão 11g ou posterior.
* As ACLs só são suportadas usando um Nome Principal de Usuário (UPN), Azure Active Directory (Azure AD) ou Segurança do Active Directory.
* A indexação de conteúdo rico em colunas de banco de dados não é suportada. Exemplos desse conteúdo são HTML, JSON, XML, blobs e análise de documentos que existem como links dentro das colunas do banco de dados.
