---
title: Conector de Graph serviceNow para Pesquisa da Microsoft
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector de Graph ServiceNow catalog para Pesquisa da Microsoft
ms.openlocfilehash: c46388a086f563eec36dbd7e5492d8065b1ae296
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375697"
---
<!---Previous ms.author: kam1 --->

# <a name="servicenow-catalog-graph-connector-preview"></a>ServiceNow Catalog Graph Connector (Visualização)

Com o Microsoft Graph Conector para ServiceNow, [](https://www.servicenow.com/products/it-service-automation-applications/service-catalog.html) sua organização pode fazer o serviço de itens de catálogo visíveis para todos os usuários ou restritos com permissões de critérios de usuário em sua organização. Depois de configurar o conector e o conteúdo de índice do ServiceNow, os usuários finais podem pesquisar esses itens de catálogo de qualquer Pesquisa da Microsoft cliente.

>[!NOTE]
>ServiceNow Catalog Graph Connector está em visualização. Se você deseja obter acesso antecipado para experimentar, inscreva-se usando [<b> este formulário </b>](https://forms.office.com/r/QyYwQQY2EX).  

Este artigo é para Microsoft 365 administradores ou qualquer pessoa que configure, executa e monitore um conector de Graph ServiceNow Catalog. Ele complementa as instruções gerais fornecidas no [artigo Configurar seu](configure-connector.md) Graph conector. Se você ainda não tiver feito isso, leia todo o artigo Configurar o conector Graph para entender o processo de instalação geral.

Cada etapa no processo de instalação é listada abaixo juntamente com uma observação que indica que você deve seguir as [](#troubleshooting) instruções gerais de instalação OU outras instruções que se aplicam apenas ao conector de Graph ServiceNow, incluindo informações sobre Solução de Problemas e Limitações. [](#limitations)

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: Adicionar um conector Graph no Centro de administração do Microsoft 365.
Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="step-2-name-the-connection"></a>Etapa 2: nomear a conexão.
Siga as instruções [gerais de instalação](./configure-connector.md).


## <a name="step-3-connection-settings"></a>Etapa 3: Conexão Configurações
Para se conectar aos dados serviceNow, você precisa da URL da instância **serviceNow da sua organização.** A URL da instância ServiceNow da sua organização normalmente se parece https:// **&lt; sua organização-domínio>.service-now.com**. 

Junto com essa URL, você precisará de uma conta de serviço para configurar **a** conexão com ServiceNow, bem como para permitir Pesquisa da Microsoft atualizar periodicamente os itens de catálogo com base no cronograma de atualização. A conta de serviço precisará de acesso de leitura aos seguintes registros da tabela **ServiceNow** para rastrear várias entidades com êxito.

Recurso | Ler tabelas necessárias de acesso | Descrição
--- | --- | ---
Itens do catálogo de índices disponíveis para <em>Todos</em> | sc_cat_item | Para rastrear itens de catálogo
Permissões de critérios de usuário de indexação e suporte | sc_cat_item_user_criteria_mtom | Who acessar esse item de catálogo
| | sc_cat_item_user_criteria_no_mtom | Who não pode acessar esse item de catálogo
| | sys_user | Ler tabela de usuário
| | sys_user_has_role | Ler informações de função de usuários
| | sys_user_grmember | Ler associação de grupo de usuários
| | user_criteria | Ler permissões de critérios de usuário

Você pode **criar e atribuir uma função** para a conta de serviço que você usa para se conectar com Pesquisa da Microsoft. [Saiba como atribuir função para contas ServiceNow.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html) O acesso de leitura às tabelas pode ser atribuído na função criada. Para saber mais sobre como definir o acesso de leitura aos registros de tabela, consulte [Proteger registros de tabela.](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls) 


>[!NOTE]
> O ServiceNow Catalog Graph Conector pode indexar itens de catálogo e permissões de critérios de usuário sem scripts avançados. Se um critério de usuário contiver script avançado, todos os itens de catálogo relacionados serão ocultos dos resultados da pesquisa.

Para autenticar e sincronizar conteúdo do ServiceNow, escolha **um dos três** métodos com suporte: 
 
- Autenticação básica 
- ServiceNow OAuth (recomendado)
- OpenID do Azure AD Conexão

## <a name="step-31-basic-authentication"></a>Etapa 3.1: Autenticação básica

Insira o nome de usuário e a senha da conta ServiceNow com a função **de** catálogo para autenticar a sua instância.

## <a name="step-32-servicenow-oauth"></a>Etapa 3.2: ServiceNow OAuth

Para usar ServiceNow OAuth para autenticação, um administrador do ServiceNow precisa provisionar um ponto de extremidade em sua instância serviceNow, para que o aplicativo Pesquisa da Microsoft possa acessá-lo. Para saber mais, confira Criar um ponto de extremidade para que os clientes [acessem](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) a instância na documentação ServiceNow.

A tabela a seguir fornece orientações sobre como preencher o formulário de criação do ponto de extremidade:

Campo | Descrição | Valor Recomendado 
--- | --- | ---
Nome | Valor exclusivo que identifica o aplicativo para o que você precisa de acesso OAuth. | Pesquisa da Microsoft
ID do cliente | Uma ID exclusiva gerada automaticamente somente leitura para o aplicativo. A instância usa a ID do cliente quando solicita um token de acesso. | NA
Segredo do cliente | Com essa cadeia de caracteres secreta compartilhada, a instância serviceNow e Pesquisa da Microsoft autorizam comunicações entre si. | Siga as práticas recomendadas de segurança tratando o segredo como uma senha.
URL de redirecionamento | Uma URL de retorno de chamada necessária para a que o servidor de autorização redireciona. | https://gcs.office.com/v1.0/admin/oauth/callback
URL de logotipo | Uma URL que contém a imagem do logotipo do aplicativo. | NA
Ativo | Marque a caixa de seleção para tornar o registro do aplicativo ativo. | Definir como ativo
Atualizar tempo de vida útil do token | O número de segundos em que um token de atualização é válido. Por padrão, os tokens de atualização expiram em 100 dias (8.640.000 segundos). | 31.536.000 (1 ano)
Tempo de vida útil do token de acesso | O número de segundos em que um token de acesso é válido. | 43.200 (12 horas)

Insira a ID do cliente e o segredo do cliente para se conectar à sua instância. Depois de se conectar, use uma credencial de conta ServiceNow para autenticar a permissão para rastrear. A conta deve ter pelo menos a **função de** catálogo. Consulte a tabela no início da etapa [3:](#step-3-connection-settings) configurações de conexão para fornecer acesso de leitura a mais registros de tabela ServiceNow e permissões de critérios de usuário de índice.

## <a name="step-33-azure-ad-openid-connect"></a>Etapa 3.3: Azure AD OpenID Conexão

Para usar o Azure AD OpenID Conexão autenticação, siga as etapas abaixo.

### <a name="step-331-register-a-new-application-in-azure-active-directory"></a>Etapa 3.3.1: Registrar um novo aplicativo no Azure Active Directory

Para saber mais sobre como registrar um novo aplicativo no Azure Active Directory, consulte [Register an application](/azure/active-directory/develop/quickstart-register-app#register-an-application). Selecione diretório organizacional de locatário único. O URI de redirecionamento não é necessário. Após o registro, anote a ID do Aplicativo (cliente) e a ID de Diretório (locatário).

### <a name="step-332-create-a-client-secret"></a>Etapa 3.3.2: Criar um segredo do cliente

Para saber mais sobre como criar um segredo do cliente, consulte [Creating a client secret](/azure/active-directory/develop/quickstart-register-app#add-a-client-secret). Anote o segredo do cliente.

### <a name="step-333-retrieve-service-principal-object-identifier"></a>Etapa 3.3.3: Recuperar o Identificador de Objeto Principal do Serviço

Siga as etapas para recuperar o Identificador de Objeto Principal do Serviço

1. Execute o PowerShell.

2. Instale Azure PowerShell usando o comando a seguir.

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. Conexão para o Azure.

   ```powershell
   Connect-AzAccount
   ```

4. Obter o Identificador de Objeto Principal do Serviço.

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   Substitua "ID de aplicativo" por ID de aplicativo (cliente) (sem aspas) do aplicativo registrado na etapa 3.a. Observe o valor do objeto ID da saída do PowerShell. É a ID da Entidade de Serviço.

Agora você tem todas as informações necessárias do portal do Azure. Um resumo rápido das informações é dado na tabela abaixo.

Propriedade | Descrição 
--- | ---
ID de diretório (ID do locatário) | ID exclusiva do locatário Azure Active Directory, a partir da etapa 3.a.
ID do aplicativo (ID do cliente) | ID exclusiva do aplicativo registrado na etapa 3.a.
Segredo de Cliente | A chave secreta do aplicativo (da etapa 3.b). Trate-o como uma senha.
ID da Entidade de Serviço | Uma identidade para o aplicativo em execução como um serviço. (da etapa 3.c)

### <a name="step-334-register-servicenow-application"></a>Etapa 3.3.4: Registrar Aplicativo ServiceNow

A instância ServiceNow precisa da seguinte configuração:

1. Registre uma nova entidade OAuth OIDC. Para saber, confira [Criar um provedor OAuth OIDC](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html).

2. A tabela a seguir fornece orientações sobre como preencher o formulário de registro do provedor OIDC

   Campo | Descrição | Valor Recomendado
   --- | --- | ---
   Nome | Um nome exclusivo que identifica a entidade OAuth OIDC. | Microsoft Azure AD
   ID do cliente | A ID do cliente do aplicativo registrado no servidor OAuth OIDC de terceiros. A instância usa a ID do cliente ao solicitar um token de acesso. | ID do aplicativo (cliente) da etapa 3.a
   Segredo de Cliente | O segredo do cliente do aplicativo registrado no servidor OAuth OIDC de terceiros. | Segredo do Cliente da etapa 3.b

   Todos os outros valores podem ser padrão.

3. No formulário de registro do provedor OIDC, você precisa adicionar uma nova configuração de provedor OIDC. Selecione o ícone de pesquisa no campo Configuração do Provedor *OAuth OIDC* para abrir os registros de configurações OIDC. Selecione Novo.

4. A tabela a seguir fornece orientações sobre como preencher o formulário de configuração do provedor OIDC

   Campo | Valor Recomendado
   --- | ---
   Provedor OIDC |  Microsoft Azure AD
   URL de metadados OIDC | A URL deve estar no formato https \: //login.microsoftonline.com/<tenandId">/.well-known/openid-configuration <br/>Substitua "tenantID" pela ID de Diretório (locatário) da etapa 3.a.
   Período de vida útil do cache de configuração do OIDC |  120
   Aplicativo | Global
   Declaração de usuário | sub
   Campo usuário | ID do Usuário
   Habilitar a verificação de declaração JTI | Desabilitado

5. Selecione Enviar e Atualizar o formulário Entidade OAuth OIDC.

### <a name="step-335-create-a-servicenow-account"></a>Etapa 3.3.5: Criar uma conta ServiceNow

Consulte as instruções para criar uma conta ServiceNow, [criar um usuário em ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).

A tabela a seguir fornece orientações sobre como preencher o registro da conta de usuário serviceNow

Campo | Valor Recomendado
--- | ---
ID do Usuário | ID da Entidade de Serviço da etapa 3.c
Somente acesso ao serviço Web | Marcado

Todos os outros valores podem ser deixados como padrão.

### <a name="step-336-enable-catalog-role-for-the-servicenow-account"></a>Etapa 3.3.6: Habilitar a função de catálogo para a conta ServiceNow

Acesse a conta ServiceNow criada com a ID principal do ServiceNow como ID do usuário e atribua a função de catálogo. As instruções para atribuir uma função a uma conta ServiceNow podem ser encontradas aqui, [atribuir uma função a um usuário](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html). Consulte a tabela no início da etapa [3:](#step-3-connection-settings) configurações de conexão para fornecer acesso de leitura a mais registros de tabela ServiceNow e permissões de critérios de usuário de índice.

Use a ID do Aplicativo como ID do Cliente (da etapa 3.a) e o segredo do cliente (da etapa 3.b) no assistente de configuração do centro de administração para autenticar para sua instância serviceNow usando o Azure AD OpenID Conexão.

## <a name="step-4-select-properties-and-filter-data"></a>Etapa 4: selecionar propriedades e filtrar dados

Nesta etapa, você pode adicionar ou remover propriedades disponíveis da fonte de dados ServiceNow. Microsoft 365 já selecionou algumas propriedades por padrão.

Com uma cadeia de caracteres de consulta ServiceNow, você pode especificar condições para sincronizar artigos. É como uma cláusula **Where** em uma **instrução SQL Select.** Por exemplo, você pode optar por indexar apenas itens que estão ativos. Para saber mais sobre como criar sua própria cadeia de caracteres de consulta, consulte Gerar uma cadeia de caracteres de [consulta codificada usando um filtro](https://docs.servicenow.com/bundle/rome-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html).

Use o botão de resultados de visualização para verificar os valores de exemplo das propriedades selecionadas e o filtro de consulta.

## <a name="step-5-manage-search-permissions"></a>Etapa 5: Gerenciar permissões de pesquisa

O conector ServiceNow dá suporte a permissões de pesquisa visíveis para **todos** ou somente pessoas **com acesso a essa fonte de dados**. Os dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários na organização ou usuários que têm acesso a eles por meio da permissão de critérios do usuário, respectivamente. Se um item de catálogo não estiver habilitado com um critério de usuário, ele aparecerá nos resultados de pesquisa de todos na organização.

O ServiceNow Catalog Graph Connector oferece suporte a permissões de critérios de usuário padrão sem scripts avançados. Quando o conector encontra um critério de usuário com script avançado, todos os dados que usam esses critérios de usuário não aparecerão nos resultados da pesquisa.

Se você escolher **Somente** pessoas com acesso a essa fonte de dados, você precisará escolher se sua instância serviceNow tem usuários Azure Active Directory (AAD) provisionados ou usuários não AAD.

Para identificar qual opção é adequada para sua organização:

1. Escolha a **opção AAD** se a ID  de Email dos usuários serviceNow for igual à UPN (UserPrincipalName) de usuários no AAD.
2. Escolha a **opção Não AAD** se a ID  de email dos usuários serviceNow for diferente do UserPrincipalName (UPN) de usuários no AAD. 

>[!NOTE]
> * Se você escolher o AAD como o tipo de fonte de identidade, o conector mapeia as IDs de Email dos usuários obtidos do ServiceNow diretamente para a propriedade UPN do AAD.
> * Se você escolheu "Non-AAD" para o tipo de identidade, consulte Mapear suas Identidades não [Azure AD](map-non-aad.md) para obter instruções sobre como mapear as identidades. Você pode usar essa opção para fornecer a expressão regular de mapeamento de ID de Email para UPN.

## <a name="step-6-assign-property-labels"></a>Etapa 6: Atribuir rótulos de propriedade

Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="step-7-manage-schema"></a>Etapa 7: Gerenciar esquema

Siga as instruções [gerais de instalação](./configure-connector.md).

## <a name="step-8-choose-refresh-settings"></a>Etapa 8: Escolher configurações de atualização

Siga as instruções [gerais de instalação](./configure-connector.md).

>[!NOTE]
>Para identidades, somente o rastreamento completo agendado será aplicado.

## <a name="step-9-review-connection"></a>Etapa 9: Analisar Conexão

Siga as instruções [gerais de instalação](./configure-connector.md).

Depois de publicar a conexão, você precisa personalizar a página de resultados da pesquisa. Para saber mais sobre como personalizar resultados de pesquisa, consulte [Personalizar a página de resultados da pesquisa](/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).

## <a name="limitations"></a>Limitações
O conector Graph serviceNow Catalog tem as seguintes limitações em sua versão mais recente:

- *Somente as pessoas com acesso a esse recurso de fonte* de dados em Etapa Gerenciar permissões de pesquisa processam apenas permissões de [critérios de](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) usuário. Qualquer outro tipo de permissão de acesso não será aplicado nos resultados da pesquisa.
- As permissões de critérios do usuário configuradas na categoria de catálogo não são suportadas. 
- Os critérios do usuário com scripts avançados não são suportados na versão atual. Todos os itens de catálogo com essa restrição de acesso serão indexados negando o acesso de todos, ou seja, eles não aparecerão nos resultados da pesquisa para qualquer usuário até que os suportemos.

## <a name="troubleshooting"></a>Solução de problemas
Depois de publicar sua conexão, personalização da página de resultados, você pode revisar o status na guia **Fontes** de Dados no centro [de administração](https://admin.microsoft.com). Para saber como fazer atualizações e exclusões, consulte [Manage your connector](manage-connector.md).
Você pode encontrar etapas de solução de problemas para problemas comumente vistos abaixo.
### <a name="1-unable-to-login-due-to-single-sign-on-enabled-servicenow-instance"></a>1. Não é possível fazer logon devido Sign-On serviceNow habilitada

Se a sua organização habilitar o SSO (Single Sign-On) para ServiceNow, talvez você tenha problemas para entrar com a conta de serviço. Você pode trazer o logon <em> `login.do` </em> baseado em nome de usuário e senha adicionando à URL da instância serviceNow. Exemplo. `https://<your-organization-domain>.service-now.com./login.do` 

### <a name="2-unauthorized-or-forbidden-response-to-api-request"></a>2. Resposta não autorizada ou proibida à solicitação de API

#### <a name="21-check-table-access-permissions"></a>2.1. Verificar permissões de acesso à tabela
Se você vir resposta proibida ou não autorizada no status da conexão, verifique se a conta de serviço exigiu acesso às [tabelas mencionadas](#step-3-connection-settings)na etapa 3: configurações de conexão . Verifique se todas as colunas nas tabelas têm acesso de leitura.

#### <a name="22-check-if-servicenow-instance-behind-firewall"></a>2.2. Verificar se a instância serviceNow está atrás do firewall
Graph O conector pode não conseguir alcançar sua instância serviceNow se estiver atrás de um firewall de rede. Você precisará permitir explicitamente o acesso ao serviço Graph Connector. Você pode encontrar o intervalo de endereços IP públicos Graph Connector Service na tabela abaixo. Com base em sua região de locatário, adicione-o à sua lista de autorizações de rede de instância do ServiceNow.

 Ambiente | Região | Intervalo
--- | --- | ---
PROD | América do Norte | 52.250.92.252/30, 52.224.250.216/30
PROD | Europa | 20.54.41.208/30, 51.105.159.88/30 
PROD | Pacífico Asiático | 52.139.188.212/30, 20.43.146.44/30 

#### <a name="23-access-permissions-not-working-as-expected"></a>2.3. Permissões de acesso não funcionando conforme esperado
Se você observar discrepâncias nas permissões de acesso aplicadas aos resultados da pesquisa, verifique a configuração de critérios do usuário na aplicação de critérios [de usuário aos itens de catálogo.](https://docs.servicenow.com/bundle/orlando-it-service-management/page/product/service-catalog-management/task/t_AppUserCritItemsCat.html)

Se você tiver outros problemas ou quiser fornecer comentários, escreva para nós [aka.ms/TalkToGraphConnectors](https://aka.ms/TalkToGraphConnectors)
