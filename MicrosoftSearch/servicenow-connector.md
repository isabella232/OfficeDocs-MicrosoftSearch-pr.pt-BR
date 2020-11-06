---
title: Conector do ServiceNow para pesquisa da Microsoft
ms.author: kam1
author: TheKarthikeyan
manager: harshkum
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector do ServiceNow para pesquisa da Microsoft
ms.openlocfilehash: b60583e61687b13c7fd631cd1c4a9f6d663724e8
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927194"
---
# <a name="servicenow-connector"></a>Conector do ServiceNow

Com o conector do ServiceNow, sua organização pode indexar artigos de base de conhecimento que são visíveis para todos os usuários da sua organização. Depois de configurar o conector e o conteúdo do índice do ServiceNow, os usuários finais podem pesquisar esses artigos de qualquer cliente de pesquisa da Microsoft.  

Este artigo é para os administradores do Microsoft 365 ou qualquer pessoa que configure, execute e monitore um conector do ServiceNow. Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.

Saiba como acessar os conectores internos da Microsoft [para configurar seu conector criado pela Microsoft para o Microsoft Search](https://docs.microsoft.com/microsoftsearch/configure-connector). A configuração específica do conector do ServiceNow é explicada no artigo abaixo.

## <a name="connection-settings"></a>Configurações de conexão
Para se conectar aos seus dados do ServiceNow, você precisa da **URL de instância do servicenow** da sua organização, as credenciais dessa conta e a ID do cliente e o segredo do cliente para autenticação OAuth.  

A URL da **instância do ServiceNow** da sua organização normalmente parece **https:// &lt; seu-Organization-Domain>. Service-Now.com**. Juntamente com esta URL, você precisará de uma conta para configurar a conexão com o ServiceNow, bem como para permitir que a pesquisa da Microsoft atualize periodicamente os artigos do ServiceNow com base no agendamento de atualização. A conta deve ter função de <em>conhecimento</em> . [Saiba como atribuir função para contas do ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).

Para autenticar e sincronizar o conteúdo do ServiceNow, escolha **um dos três** métodos com suporte:
1. Autenticação básica 
2. OAuth do ServiceNow (recomendado)
3. Conexão OpenID do Azure AD

#### <a name="basic-authentication"></a>Autenticação básica
Insira o nome de usuário e a senha da conta do ServiceNow com a função de <em>conhecimento</em> para autenticar sua instância.
#### <a name="servicenow-oauth"></a>OAuth do ServiceNow

Para usar o ServiceNow OAuth para autenticação, um administrador do ServiceNow precisa provisionar um ponto de extremidade na sua instância do ServiceNow, para que o aplicativo de pesquisa da Microsoft possa acessar a instância. Para saber mais, confira [criar um ponto de extremidade para os clientes acessar a instância](https://docs.servicenow.com/bundle/newyork-platform-administration/page/administer/security/task/t_CreateEndpointforExternalClients.html) na documentação do ServiceNow.

A tabela a seguir fornece orientação sobre como preencher o formulário de criação de ponto de extremidade:

**Field** | **Descrição** | **Valor recomendado**
--- | --- | ---
Nome | Esse valor exclusivo identifica o aplicativo para o qual você precisa de acesso OAuth. | Pesquisa da Microsoft
ID do cliente | Uma ID exclusiva somente leitura, gerada automaticamente, para o aplicativo. A instância usa a ID do cliente quando ele solicita um token de acesso. | NA
Segredo do cliente | Com essa cadeia de caracteres secreta compartilhada, a instância do ServiceNow e a pesquisa da Microsoft autorizam comunicações entre si. | Siga as práticas recomendadas de segurança tratando isso como uma senha.
URL de redirecionamento | Uma URL de retorno de chamada necessária para a qual o servidor de autorização é redirecionado. | https://gcs.office.com/v1.0/admin/oauth/callback
URL do Logotipo | Uma URL que contém a imagem do logotipo do aplicativo. | NA
Ativo | Marque a caixa de seleção para tornar o registro de aplicativo ativo. | Definido como ativo
Duração do token de atualização | O número de segundos que um token de atualização é válido. Por padrão, os tokens de atualização expiram em 100 dias (8640000 segundos). | 31.536.000 (1 ano)
Vida útil do token de acesso | O número de segundos que um token de acesso é válido. | 43.200 (12 horas)

Insira a ID do cliente e o segredo do cliente para se conectar à sua instância. Após a conexão, use uma credencial de conta do ServiceNow para autenticar a permissão de rastreamento. A conta deve ter função de <em>conhecimento</em> . 

#### <a name="azure-ad-openid-connect"></a>Conexão OpenID do Azure AD

Para usar o Azure AD OpenID Connect para autenticação, siga as etapas abaixo.

###### <a name="step-1-register-a-new-application-in-azure-active-directory"></a>Etapa 1: registrar um novo aplicativo no Azure Active Directory

Para saber mais sobre como registrar um novo aplicativo no Azure Active Directory, confira [registrar um aplicativo](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#register-an-application). Selecione o diretório organizacional de um único locatário. O URI de redirecionamento não é necessário. Após o registro, anote a ID de aplicativo (cliente) e a ID de diretório (locatário).

###### <a name="step-2-create-a-client-secret"></a>Etapa 2: criar um segredo do cliente

Para saber mais sobre como criar um segredo do cliente, consulte [Creating a Client Secret](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-client-secret). Anote o segredo do cliente.

###### <a name="step-3-retrieve-service-principal-object-identifier"></a>Etapa 3: recuperar o identificador de objeto principal de serviço

Siga as etapas para recuperar o identificador de objeto principal de serviço

1. Executar o PowerShell
2. Instale o Azure PowerShell usando o seguinte comando
```<language>
   Install-Module -Name Az -AllowClobber -Scope CurrentUser
```
3. Conectar-se ao Azure
```<language>
    Connect-AzAccount
```
4. Obter identificador de objeto da entidade de serviço
```<language>
   Get-AzADServicePrincipal -ApplicationId "Application-ID"
```
Substitua "Application-ID" pela ID do aplicativo (cliente) (sem as aspas) do aplicativo registrado na etapa 1. Observe o valor do objeto ID da saída do PowerShell. É a ID da entidade de serviço.

Agora você tem todas as informações necessárias do portal do Azure. Um resumo rápido das informações é fornecido na tabela abaixo.

**Property** | **Descrição**
--- | ---
ID de diretório (ID do locatário) | Esta é uma ID exclusiva que faz referência ao locatário do Azure Active Directory (da etapa 1).
ID do aplicativo (ID do cliente) | Esta é uma ID exclusiva que faz referência ao aplicativo registrado na etapa 1.
Segredo de Cliente | Esta é a chave secreta do aplicativo (da etapa 2). Tratá-lo como uma senha.
ID da entidade de serviço | Uma identidade para o aplicativo sendo executado como um serviço. (na etapa 3)

###### <a name="step-4-register-servicenow-application"></a>Etapa 4: registrar o aplicativo do ServiceNow

A configuração a seguir precisa ser feita na instância do ServiceNow.

1. Registrar uma nova entidade OIDC do OAuth. Para saber mais, confira [criar um provedor de OIDC OAuth](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/security/task/add-OIDC-entity.html).
2. A tabela a seguir fornece orientação sobre como preencher o formulário de registro do provedor OIDC

**Field** | **Descrição** | **Valor recomendado**
--- | --- | ---
Nome | Um nome exclusivo que identifica a entidade OIDC OAuth. | Azure AD
ID do cliente | A ID do cliente do aplicativo registrado no servidor OAuth OIDC de terceiros. A instância usa a ID do cliente ao solicitar um token de acesso. | ID do aplicativo (cliente) da etapa 1
Segredo de Cliente | O segredo do cliente do aplicativo registrado no servidor OAuth OIDC de terceiros. | Segredo do cliente da etapa 2

Todos os outros valores podem ser padrão.

3. No formulário de registro do provedor OIDC, você precisa adicionar uma nova configuração de provedor do OIDC. Clique no campo Pesquisar ícone no *provedor de OIDC de OAuth* para abrir os registros das configurações do OIDC. Clique em Novo.
4. A tabela a seguir fornece orientação sobre como preencher o formulário de configuração do provedor OIDC

**Field** | **Valor recomendado**
--- | ---
Provedor OIDC |  Azure AD
URL de metadados OIDC | Ele deve estar no formato https \: //login.microsoftonline.com/"tenandId"/.well-known/OpenID-Configuration <br/>Substitua "tenantid" pela ID de diretório (locatário) da etapa 1 (sem aspas).
Faixa de vida do cache de configuração OIDC |  120
Aplicativo | Global
Declaração de usuário | sub
Campo de usuário | ID do Usuário
Habilitar a verificação da declaração JTI | Desabilitado

5. Clique em enviar e atualizar o formulário de entidade OIDC do OAuth.

###### <a name="step-5-create-a-servicenow-account"></a>Etapa 5: criar uma conta do ServiceNow

Consulte as instruções para criar uma conta do ServiceNow, [criar um usuário no ServiceNow](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_CreateAUser.html).

A tabela a seguir fornece orientação sobre como preencher o registro da conta de usuário do ServiceNow

**Field** | **Valor recomendado**
--- | ---
ID do Usuário | ID da entidade de serviço da etapa 3
Somente acesso ao serviço Web | Marcado

Todos os outros valores podem ser deixados como padrão.

###### <a name="step-6-enable-knowledge-role-for-the-servicenow-account"></a>Etapa 6: habilitar a função de conhecimento para a conta do ServiceNow

Acessar a conta do ServiceNow que você criou com o ID principal do ServiceNow como ID de usuário e atribuir a função de conhecimento. As instruções para atribuir uma função a uma conta do ServiceNow podem ser encontradas aqui, [atribuir uma função a um usuário](https://docs.servicenow.com/bundle/paris-platform-administration/page/administer/users-and-groups/task/t_AssignARoleToAUser.html).

Use a ID do aplicativo como ID do cliente (da etapa 1) e o segredo do cliente (da etapa 2) no assistente de configuração do centro de administração para autenticar sua instância do ServiceNow usando o Azure AD OpenID Connect.

## <a name="filter-data"></a>Filtrar dados 
Com uma cadeia de caracteres de consulta do ServiceNow, você pode especificar condições para sincronizar artigos. É como uma cláusula **Where** em uma instrução **SQL SELECT** . Por exemplo, você pode optar por indexar apenas artigos publicados e ativos. Para saber mais sobre como criar sua própria cadeia de caracteres de consulta, confira [gerar uma cadeia de caracteres de consulta codificada usando um filtro](https://docs.servicenow.com/bundle/paris-platform-user-interface/page/use/using-lists/task/t_GenEncodQueryStringFilter.html).

## <a name="manage-search-permissions"></a>Gerenciar permissões de pesquisa
O conector do ServiceNow oferece suporte apenas às permissões de pesquisa visíveis para **todos**. Dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários da organização.

## <a name="manage-the-search-schema"></a>Gerenciar o esquema de pesquisa
Após a conexão bem-sucedida, configure o mapeamento de esquema de pesquisa. Você pode escolher quais propriedades tornar **consultáveis** , **pesquisáveis** e **recuperáveis**. Para saber mais sobre como gerenciar o esquema de pesquisa, confira [gerenciar o esquema de pesquisa](https://docs.microsoft.com/microsoftsearch/configure-connector#manage-the-search-schema).

## <a name="set-the-refresh-schedule"></a>Definir o agendamento de atualização
O conector do ServiceNow suporta agendas de atualização para rastreamentos completos e incrementais. Recomendamos que você defina ambas.

Um cronograma de rastreamento completo localiza artigos excluídos que foram previamente sincronizados com o índice de pesquisa da Microsoft e quaisquer artigos que tenham sido movidos do filtro de sincronização. Quando você se conecta pela primeira vez ao ServiceNow, um rastreamento completo é executado para sincronizar todos os artigos da base de conhecimento. Para sincronizar novos itens e fazer atualizações, você precisa agendar rastreamentos incrementais.

O padrão recomendado é um dia para um rastreamento completo e quatro horas para um rastreamento incremental.

## <a name="review-and-publish"></a>Revisar e publicar
Depois de configurar seu conector, você pode revisar e publicar a conexão.

## <a name="next-steps"></a>Próximas etapas
Após publicar a conexão, você precisa personalizar a página de resultados da pesquisa. Para saber mais sobre como personalizar os resultados da pesquisa, confira [Personalizar a página de resultados da pesquisa](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).