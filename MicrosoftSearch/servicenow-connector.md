---
title: Conector do ServiceNow Graph para a Pesquisa da Microsoft
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
description: Configurar o conector do ServiceNow Graph para a Pesquisa da Microsoft
ms.openlocfilehash: d1fdfb5f1aec5091fd526152de2bdc86932cfdb9
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084889"
---
<!---Previous ms.author: kam1 --->

# <a name="servicenow-graph-connector"></a>ServiceNow Graph Connector

O conector do ServiceNow Graph permite que sua organização indexe artigos baseados em conhecimento visíveis aos usuários de acordo com as permissões de critérios do usuário em sua organização. Depois de configurar o conector e o conteúdo de índice do ServiceNow, os usuários podem pesquisar os artigos de qualquer cliente da Pesquisa da Microsoft.

> [!NOTE]
> Leia o [**artigo Configuração do seu conector do Graph**](configure-connector.md) para entender o processo geral de configuração de conectores do Graph.

Este artigo é para qualquer pessoa que configure, executa e monitore um conector do ServiceNow Graph. Ele complementa o processo de instalação geral e mostra instruções que se aplicam somente ao conector do ServiceNow Graph. Este artigo também inclui informações sobre solução [de problemas](#troubleshooting) e [limitações.](#limitations)
  
## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: Adicionar um conector do Graph no centro de administração do Microsoft 365

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: Nomear a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-connection-settings"></a>Etapa 3: Configurações de conexão

Para se conectar aos dados do ServiceNow, use as credenciais de URL da instância do **ServiceNow** da sua organização para essa conta, a ID do Cliente e o Segredo do Cliente para autenticação OAuth.  

A URL da instância do **ServiceNow** da sua organização normalmente se parece https:// sua **&lt; organização-domínio>.service-now.com**. Junto com essa URL, você precisa de uma conta para configurar a conexão com o ServiceNow e para permitir que a Pesquisa da Microsoft atualize os artigos do ServiceNow com base na agenda de atualização. A conta deve ter pelo menos uma <em>função de</em> conhecimento. [Saiba como atribuir função para contas do ServiceNow.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)

>[!NOTE]
>Se você quiser rastrear identidades de usuários e grupos para honrar as permissões de acesso dos artigos de conhecimento nos resultados da Pesquisa da Microsoft, a conta deverá ter acesso para ler os seguintes registros de tabela no ServiceNow:
>* kb_uc_can_contribute_mtom
>* kb_uc_can_read_mtom
>* kb_uc_cannot_read_mtom
>* kb_uc_cannot_contribute_mtom
>* sys_user
>* sys_user_has_role
>* sys_user_grmember
>* user_criteria
>* kb_knowledge_base  
> Você pode criar e atribuir uma função para a conta que usa para se conectar à Pesquisa da Microsoft. O acesso de leitura às tabelas pode ser atribuído a essa função. Para saber mais sobre como configurar o acesso de leitura aos registros de tabela, consulte [Proteger registros de tabela.](https://developer.servicenow.com/dev.do#!/learn/learning-plans/orlando/new_to_servicenow/app_store_learnv2_securingapps_orlando_creating_and_editing_access_controls)

Para autenticar e sincronizar conteúdo do ServiceNow, escolha **um dos três** métodos com suporte:

1. Autenticação básica
1. ServiceNow OAuth (recomendado)
1. Azure AD OpenID Connect

### <a name="basic-authentication"></a>Autenticação básica

Insira o nome de usuário e a senha da conta do ServiceNow com **a função de** conhecimento para autenticar sua instância.

### <a name="servicenow-oauth"></a>ServiceNow OAuth

Para usar o ServiceNow OAuth para autenticação, provisione um ponto de extremidade em sua instância do ServiceNow. O aplicativo da Pesquisa da Microsoft o usará para acessar a instância. Para saber mais, consulte Criar um ponto de extremidade para que os clientes [acessem a instância](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) na documentação do ServiceNow.

A tabela a seguir fornece orientações sobre como preencher o formulário de criação de ponto de extremidade:

Campo | Descrição | Valor Recomendado 
--- | --- | ---
Nome | Valor exclusivo que identifica o aplicativo para o que você precisa de acesso OAuth. | Pesquisa da Microsoft
ID do cliente | Uma ID exclusiva gerada automaticamente somente leitura para o aplicativo. A instância usa a ID do cliente quando solicita um token de acesso. | NA
Segredo do cliente | Com essa cadeia de caracteres secreta compartilhada, a instância do ServiceNow e a Pesquisa da Microsoft autorizam as comunicações entre si. | Siga as práticas recomendadas de segurança tratando o segredo como uma senha.
URL de redirecionamento | Uma URL de retorno de chamada necessária para a que o servidor de autorização redireciona. | https://gcs.office.com/v1.0/admin/oauth/callback
URL do Logotipo | Uma URL que contém a imagem do logotipo do aplicativo. | NA
Ativo | Marque a caixa de seleção para tornar o Registro do aplicativo ativo. | Definido como ativo
Tempo de vida do token de atualização | O número de segundos em que um token de atualização é válido. Por padrão, os tokens de atualização expiram em 100 dias (8.640.000 segundos). | 31.536.000 (1 ano)
Tempo de vida do token de acesso | O número de segundos em que um token de acesso é válido. | 43.200 (12 horas)

Insira a ID do cliente e o segredo do cliente para se conectar à sua instância. Após a conexão, use uma credencial de conta do ServiceNow para autenticar a permissão de rastreamento. A conta deve ter pelo menos uma **função de** conhecimento.

### <a name="azure-ad-openid-connect"></a>Azure AD OpenID Connect

Para usar o OpenID Connect do Azure AD para autenticação, siga as etapas abaixo.

## <a name="step-3a-register-a-new-application-in-azure-active-directory"></a>Etapa 3.a: Registrar um novo aplicativo no Azure Active Directory

Para saber mais sobre como registrar um novo aplicativo no Azure Active Directory, confira [Registrar um aplicativo.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application) Selecione um diretório organizacional de locatário único. O URI de redirecionamento não é necessário. Após o registro, anote a ID do Aplicativo (cliente) e a ID do Diretório (locatário).

## <a name="step-3b-create-a-client-secret"></a>Etapa 3.b: Criar um segredo do cliente

Para saber mais sobre como criar um segredo do cliente, consulte [Criando um segredo do cliente.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret) Anote o segredo do cliente.

## <a name="step-3c-retrieve-service-principal-object-identifier"></a>Etapa 3.c: Recuperar o Identificador de Objeto da Entidade de Serviço

Siga as etapas para recuperar o Identificador de Objeto da Entidade de Serviço

1. Execute o PowerShell.

2. Instale o Azure PowerShell usando o seguinte comando.

   ```powershell
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
   ```

3. Conecte-se ao Azure.

   ```powershell
   Connect-AzAccount
   ```

4. Obter o Identificador de Objeto da Entidade de Serviço.

   ```powershell
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
   ```
   Substitua "Application-ID" pela ID do aplicativo (cliente) (sem aspas) do aplicativo registrado na etapa 3.a. Observe o valor do objeto ID da saída do PowerShell. É a ID da Entidade de Serviço.

Agora você tem todas as informações necessárias do portal do Azure. Um resumo rápido das informações é dado na tabela a seguir.

Propriedade | Descrição 
--- | ---
ID do diretório (ID do locatário) | ID exclusiva do locatário do Azure Active Directory, da etapa 3.a.
ID do aplicativo (ID do cliente) | ID exclusiva do aplicativo registrado na etapa 3.a.
Segredo de Cliente | A chave secreta do aplicativo (da etapa 3.b). Trate-o como uma senha.
ID da entidade de serviço | Uma identidade para o aplicativo em execução como um serviço. (da etapa 3.c)

## <a name="step-3d-register-servicenow-application"></a>Etapa 3.d: Registrar o aplicativo ServiceNow

A instância do ServiceNow precisa da seguinte configuração:

1. Registre uma nova entidade OAuth OIDC. Para saber mais, [consulte Criar um provedor OAuth OIDC.](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html)

2. A tabela a seguir fornece orientações sobre como preencher o formulário de registro do provedor OIDC

   Campo | Descrição | Valor Recomendado
   --- | --- | ---
   Nome | Um nome exclusivo que identifica a entidade OAuth OIDC. | Azure Active Directory
   ID do cliente | A ID do cliente do aplicativo registrado no servidor OAuth OIDC de terceiros. A instância usa a ID do cliente ao solicitar um token de acesso. | ID do aplicativo (cliente) da etapa 3.a
   Segredo de Cliente | O segredo do cliente do aplicativo registrado no servidor OAuth OIDC de terceiros. | Segredo do Cliente da etapa 3.b

   Todos os outros valores podem ser padrão.

3. No formulário de registro do provedor OIDC, você precisa adicionar uma nova configuração de provedor OIDC. Selecione o ícone de pesquisa no campo Configuração do Provedor *OAuth OIDC* para abrir os registros de configurações OIDC. Selecione Novo.

4. A tabela a seguir fornece orientações sobre como preencher o formulário de configuração do provedor OIDC

   Campo | Valor Recomendado
   --- | ---
   Provedor OIDC |  Azure Active Directory
   URL de metadados do OIDC | A URL deve estar no formato https \: //login.microsoftonline.com/<tenandId">/.well-known/openid-configuration <br/>Substitua "tenantID" pela ID de diretório (locatário) da etapa 3.a.
   Tempo de vida do cache de configuração do OIDC |  120
   Aplicativo | Global
   Declaração do usuário | sub
   Campo Usuário | ID do Usuário
   Habilitar verificação de declaração JTI | Desabilitado

5. Selecione Enviar e Atualizar o formulário entidade OAuth OIDC.

## <a name="step-3e-create-a-servicenow-account"></a>Etapa 3.e: Criar uma conta do ServiceNow

Consulte as instruções para criar uma conta do ServiceNow, [criar um usuário no ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).

A tabela a seguir fornece orientações sobre como preencher o registro da conta de usuário do ServiceNow

Campo | Valor Recomendado
--- | ---
ID do Usuário | ID da Entidade de Serviço da etapa 3.c
Somente acesso ao serviço Web | Marcado

Todos os outros valores podem ser deixados por padrão.

## <a name="step-3f-enable-knowledge-role-for-the-servicenow-account"></a>Etapa 3.f: Habilitar a função de conhecimento para a conta do ServiceNow

Acesse a conta do ServiceNow que você criou com a ID de entidade do ServiceNow como ID de usuário e atribua a função de conhecimento. As instruções para atribuir uma função a uma conta do ServiceNow podem ser encontradas aqui: [atribuir uma função a um usuário.](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html)

Use a ID do Aplicativo como ID do Cliente da etapa 3.a e o Segredo do Cliente da etapa 3.b, para se autenticar na instância do ServiceNow usando o OpenID Connect do Azure AD.

## <a name="step-4-select-properties-and-filter-data"></a>Etapa 4: Selecionar propriedades e filtrar dados

Nesta etapa, você pode adicionar ou remover as propriedades disponíveis da fonte de dados do ServiceNow. O Microsoft 365 já selecionou algumas propriedades por padrão.

Com uma cadeia de caracteres de consulta ServiceNow, você pode especificar condições para sincronizar artigos. É como uma cláusula **Where** em uma **instrução SQL Select.** Por exemplo, você pode optar por indexar somente os artigos publicados e ativos. Para saber como criar sua própria cadeia de caracteres de consulta, consulte Gerar uma cadeia [de caracteres de consulta codificada usando um filtro.](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html)

Use o botão visualizar resultados para verificar os valores de exemplo das propriedades selecionadas e o filtro de consulta.

## <a name="step-5-manage-search-permissions"></a>Etapa 5: Gerenciar permissões de pesquisa

O conector do ServiceNow dá suporte a permissões de pesquisa visíveis para **todas** as pessoas ou apenas **com acesso a essa fonte de dados.** Os dados indexados aparecem nos resultados da pesquisa e são visíveis aos usuários na organização que têm acesso a eles, respectivamente. O ServiceNow Connector dá suporte a permissões de critérios de usuário padrão sem scripts avançados. Quando o conector encontrar um critério de usuário com script avançado, todos os dados que usam esse critério de usuário não serão mostrados nos resultados da pesquisa.

Se você selecionar Apenas pessoas com acesso a essa fonte de **dados,** precisará escolher se a instância do ServiceNow tem usuários provisionados do Azure Active Directory (AAD) ou usuários não do AAD.

>[!NOTE]
>O conector do ServiceNow está em **visualização** se você escolher **Apenas as pessoas com acesso a essa fonte de dados.**

>[!NOTE]
>Se você escolher AAD como o tipo de fonte de identidade, certifique-se de estar atribuindo a propriedade de origem UPN para a propriedade direcionada de email no ServiceNow. Para verificar ou alterar seus mapeamentos, consulte Personalização de mapeamentos de atributos de provisionamento do usuário para [aplicativos SaaS no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/app-provisioning/customize-application-attributes)

Se você optou por ingerir uma ACL da sua instância do ServiceNow e selecionou "não-AAD" para o tipo de identidade, confira Mapear as identidades que não são do [Azure AD](map-non-aad.md) para obter instruções sobre como mapear as identidades.

## <a name="step-6-assign-property-labels"></a>Etapa 6: Atribuir rótulos de propriedade

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-manage-schema"></a>Etapa 7: Gerenciar esquema

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-choose-refresh-settings"></a>Etapa 8: Escolher configurações de atualização

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

>[!NOTE]
>Para identidades, somente o rastreamento completo agendado será aplicado.

## <a name="step-9-review-connection"></a>Etapa 9: revisar a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a>Solução de problemas

Depois de publicar sua conexão, personalizar a página de resultados, você pode revisar o status na guia **Conectores** no centro [de administração.](https://admin.microsoft.com) Para saber como fazer atualizações e exclusões, consulte [Gerenciar seu conector.](manage-connector.md)

## <a name="limitations"></a>Limitações

O conector do ServiceNow Graph tem as seguintes limitações em sua versão mais recente:

- A indexação de artigos de conhecimento disponíveis para todos em uma organização é um recurso geralmente disponível.
- *Somente as pessoas com acesso a esse recurso de* fonte de dados na etapa Gerenciar permissões de Pesquisa estão em visualização e processam apenas permissões de [critérios](https://hi.service-now.com/kb_view.do?sysparm_article=KB0550924) de usuário. Qualquer outro tipo de permissões de acesso não será aplicado nos resultados da pesquisa.
- Os critérios de usuário com scripts avançados não são suportados na versão de visualização atual. Os artigos de conhecimento com restrição de acesso serão indexados com negação de acesso a todos e não aparecerão nos resultados da pesquisa para nenhum usuário até que nós os suportemos.
