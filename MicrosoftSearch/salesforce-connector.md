---
title: Conector salesforce Graph para a Pesquisa da Microsoft
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
description: Configurar o conector do Salesforce Graph para a Pesquisa da Microsoft
ms.openlocfilehash: 0b80bf7d3296236887d1cc1bf8e75da976b6a1f1
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084995"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a><span data-ttu-id="6d242-103">Conector salesforce Graph (visualização)</span><span class="sxs-lookup"><span data-stu-id="6d242-103">Salesforce Graph connector (preview)</span></span>

<span data-ttu-id="6d242-104">O conector salesforce Graph permite que sua organização indexe contatos, oportunidades, clientes em geral e objetos de contas em sua instância da Salesforce.</span><span class="sxs-lookup"><span data-stu-id="6d242-104">The Salesforce Graph connector, allows your organization to index Contacts, Opportunities, Leads, and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="6d242-105">Depois de configurar o conector e o conteúdo do índice do Salesforce, os usuários finais podem pesquisar esses itens em qualquer cliente da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d242-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="6d242-106">Leia o [**artigo Configuração do seu conector do Graph**](configure-connector.md) para entender o processo geral de configuração de conectores do Graph.</span><span class="sxs-lookup"><span data-stu-id="6d242-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="6d242-107">Este artigo é para qualquer pessoa que configure, executa e monitore um conector do ServiceNow Graph.</span><span class="sxs-lookup"><span data-stu-id="6d242-107">This article is for anyone who configures, runs, and monitors a ServiceNow Graph connector.</span></span> <span data-ttu-id="6d242-108">Ele complementa o processo de instalação geral e mostra instruções que se aplicam somente ao conector do Salesforce Graph.</span><span class="sxs-lookup"><span data-stu-id="6d242-108">It supplements the general setup process, and shows instructions that apply only for the Salesforce Graph connector.</span></span> <span data-ttu-id="6d242-109">Este artigo também inclui informações sobre [limitações.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="6d242-109">This article also includes information about [Limitations](#limitations).</span></span>

>[!IMPORTANT]
><span data-ttu-id="6d242-110">O conector do Salesforce Graph atualmente dá suporte a Verão '19 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="6d242-110">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="6d242-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6d242-111">Before you get started</span></span>

<span data-ttu-id="6d242-112">Para se conectar à sua instância da Salesforce, você precisa da URL da instância da Salesforce, da ID do Cliente e do Segredo do Cliente para autenticação OAuth.</span><span class="sxs-lookup"><span data-stu-id="6d242-112">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="6d242-113">As etapas a seguir explicam como você ou seu administrador da Salesforce podem obter essas informações de sua conta da Salesforce:</span><span class="sxs-lookup"><span data-stu-id="6d242-113">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="6d242-114">Entre na instância da Salesforce e vá para a Instalação</span><span class="sxs-lookup"><span data-stu-id="6d242-114">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="6d242-115">Navegue até Apps -> App Manager.</span><span class="sxs-lookup"><span data-stu-id="6d242-115">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="6d242-116">Selecione **Novo aplicativo conectado.**</span><span class="sxs-lookup"><span data-stu-id="6d242-116">Select **New connected app**.</span></span>

- <span data-ttu-id="6d242-117">Conclua a seção da API da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="6d242-117">Complete the API section as follows:</span></span>

    - <span data-ttu-id="6d242-118">Marque a caixa de seleção para **Habilitar Configurações do Oauth.**</span><span class="sxs-lookup"><span data-stu-id="6d242-118">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="6d242-119">Especifique a URL de retorno de chamada como: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="6d242-119">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="6d242-120">Selecione estes escopos OAuth necessários.</span><span class="sxs-lookup"><span data-stu-id="6d242-120">Select these required OAuth scopes.</span></span>

        - <span data-ttu-id="6d242-121">Acessar e gerenciar seus dados (api)</span><span class="sxs-lookup"><span data-stu-id="6d242-121">Access and manage your data (api)</span></span>

        - <span data-ttu-id="6d242-122">Executar solicitações em seu nome a qualquer momento (refresh_token, offline_access)</span><span class="sxs-lookup"><span data-stu-id="6d242-122">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span>

    - <span data-ttu-id="6d242-123">Marque a caixa de seleção para **Exigir segredo para o fluxo do servidor Web.**</span><span class="sxs-lookup"><span data-stu-id="6d242-123">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="6d242-124">Salve o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6d242-124">Save the app.</span></span>
    
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="6d242-125">![Seção api na instância salesforce depois que o administrador tiver inserido todas as configurações necessárias listadas acima.](media/salesforce-connector/sf1.png)</span><span class="sxs-lookup"><span data-stu-id="6d242-125">![API section in Salesforce instance after admin has entered all required configurations listed above.](media/salesforce-connector/sf1.png)</span></span>

- <span data-ttu-id="6d242-126">Copie a chave do consumidor e o segredo do consumidor.</span><span class="sxs-lookup"><span data-stu-id="6d242-126">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="6d242-127">Essas informações serão usadas como a ID do Cliente e o Segredo do Cliente quando você definir as Configurações de Conexão para seu Conector do Graph no portal de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6d242-127">This information will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="6d242-128">![Resultados retornados pela seção API na instância salesforce depois que o administrador enviou todas as configurações necessárias.</span><span class="sxs-lookup"><span data-stu-id="6d242-128">![Results returned by API section in Salesforce instance after admin has submitted all required configurations.</span></span> <span data-ttu-id="6d242-129">A Chave do Consumidor está na parte superior da coluna esquerda e o Segredo do Consumidor está na parte superior da coluna direita.](media/salesforce-connector/clientsecret.png)</span><span class="sxs-lookup"><span data-stu-id="6d242-129">Consumer Key is at top of left column and Consumer Secret is at top of right column.](media/salesforce-connector/clientsecret.png)</span></span>
  
- <span data-ttu-id="6d242-130">Antes de fechar a instância da Salesforce, siga estas etapas para garantir que os tokens de atualização não expirem:</span><span class="sxs-lookup"><span data-stu-id="6d242-130">Before closing your Salesforce instance, follow these steps to ensure that refresh tokens don't expire:</span></span>
    - <span data-ttu-id="6d242-131">Go to Apps -> App Manager</span><span class="sxs-lookup"><span data-stu-id="6d242-131">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="6d242-132">Encontre o aplicativo que você criou e selecione o drop-down à direita.</span><span class="sxs-lookup"><span data-stu-id="6d242-132">Find the app you created and select the drop-down on the right.</span></span> <span data-ttu-id="6d242-133">Selecionar **Gerenciar**</span><span class="sxs-lookup"><span data-stu-id="6d242-133">Select **Manage**</span></span>
    - <span data-ttu-id="6d242-134">Selecionar **políticas de edição**</span><span class="sxs-lookup"><span data-stu-id="6d242-134">Select **edit policies**</span></span>
    - <span data-ttu-id="6d242-135">Para a política de token de atualização, selecionar **Token de atualização é válido até ser revogado**</span><span class="sxs-lookup"><span data-stu-id="6d242-135">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="6d242-136">![Selecione a Política de Token de Atualização chamada "O token de atualização é válido até ser revogado"](media/salesforce-connector/oauthpolicies.png)</span><span class="sxs-lookup"><span data-stu-id="6d242-136">![Select the Refresh Token Policy named "Refresh token is valid until revoked "](media/salesforce-connector/oauthpolicies.png)</span></span>

<span data-ttu-id="6d242-137">Agora você pode usar o Centro de Administração do [M365](https://admin.microsoft.com/) para concluir o restante do processo de instalação do conector do Graph.</span><span class="sxs-lookup"><span data-stu-id="6d242-137">You can now use the [M365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6d242-138">Etapa 1: Adicionar um conector do Graph no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6d242-138">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="6d242-139">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="6d242-139">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="6d242-140">Etapa 2: Nomear a conexão</span><span class="sxs-lookup"><span data-stu-id="6d242-140">Step 2: Name the connection</span></span>

<span data-ttu-id="6d242-141">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="6d242-141">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="6d242-142">Etapa 3: Definir as configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="6d242-142">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="6d242-143">Para a URL da Instância, use https://[domain].my.salesforce.com onde o domínio seria o domínio Salesforce da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6d242-143">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span>

<span data-ttu-id="6d242-144">Insira a ID do Cliente e o Segredo do Cliente obtidos da instância da Salesforce e selecione Entrar.</span><span class="sxs-lookup"><span data-stu-id="6d242-144">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>

<span data-ttu-id="6d242-145">Na primeira vez que você tentar entrar com essas configurações, você verá um pop-up solicitando que você faça logoff no Salesforce com seu nome de usuário e senha de administrador.</span><span class="sxs-lookup"><span data-stu-id="6d242-145">The first time you've attempted to sign in with these settings, you'll get a pop-up asking you to log in to Salesforce with your admin username and password.</span></span> <span data-ttu-id="6d242-146">A captura de tela abaixo mostra o pop-up.</span><span class="sxs-lookup"><span data-stu-id="6d242-146">The screenshot below shows the popup.</span></span> <span data-ttu-id="6d242-147">Insira suas credenciais e selecione "Entrar".</span><span class="sxs-lookup"><span data-stu-id="6d242-147">Enter your credentials and select "Log In".</span></span>

  ![Pop-up de logon solicitando nome de usuário e senha.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="6d242-149">Se o pop-up não aparecer, ele pode estar sendo bloqueado no navegador, portanto, você deve permitir pop-ups e redirecionamentos.</span><span class="sxs-lookup"><span data-stu-id="6d242-149">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

<span data-ttu-id="6d242-150">Verifique se a conexão foi bem-sucedida pesquisando uma faixa verde que diz "Conexão bem-sucedida", conforme mostra a captura de tela abaixo.</span><span class="sxs-lookup"><span data-stu-id="6d242-150">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="6d242-151">![Captura de tela do logon bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="6d242-151">![Screenshot of successful login.</span></span> <span data-ttu-id="6d242-152">A faixa verde que diz "Conexão bem-sucedida" está localizada sob o campo da URL da Instância da Salesforce](media/salesforce-connector/sf5.png)</span><span class="sxs-lookup"><span data-stu-id="6d242-152">The green banner that says "Connection successful" is located under the field for your Salesforce Instance URL](media/salesforce-connector/sf5.png)</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="6d242-153">Etapa 4: Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="6d242-153">Step 4: Manage search permissions</span></span>

<span data-ttu-id="6d242-154">Você precisará escolher quais usuários verão os resultados da pesquisa dessa fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="6d242-154">You'll need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="6d242-155">Se você permitir que apenas determinados usuários do Azure Active Directory (Azure AD) ou do Azure AD vejam os resultados da pesquisa, mapeie as identidades.</span><span class="sxs-lookup"><span data-stu-id="6d242-155">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, make sure you map the identities.</span></span>

## <a name="step-4a-select-permissions"></a><span data-ttu-id="6d242-156">Etapa 4a: Selecionar permissões</span><span class="sxs-lookup"><span data-stu-id="6d242-156">Step 4a: Select permissions</span></span>

<span data-ttu-id="6d242-157">Você pode optar por ingerir listas de controle de acesso (ACLs) de sua instância da Salesforce ou permitir que todos em sua organização vejam os resultados de pesquisa dessa fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="6d242-157">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="6d242-158">As ACLs podem incluir identidades do Azure Active Directory (AAD) (usuários federados do Azure AD para a Salesforce), identidades não-Azure AD (usuários nativos do Salesforce que têm identidades correspondentes no Azure AD) ou ambas.</span><span class="sxs-lookup"><span data-stu-id="6d242-158">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

>[!NOTE]
><span data-ttu-id="6d242-159">Se você usar um Provedor de Identidade de terceiros, como a ID de Ping ou secureAuth, selecione "não-AAD" como o tipo de identidade.</span><span class="sxs-lookup"><span data-stu-id="6d242-159">If you use a third-party Identity Provider like Ping ID or secureAuth, you should select "non-AAD" as the identity type.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6d242-160">![Tela Selecionar permissões que foi concluída por um administrador. O administrador selecionou a opção "Somente pessoas com acesso a essa fonte de dados" e também selecionou "AAD" em um menu suspenso de tipos de identidade.](media/salesforce-connector/sf6.png)</span><span class="sxs-lookup"><span data-stu-id="6d242-160">![Select permissions screen that has been completed by an admin. The admin has selected the "Only people with access to this data source" option and has also selected "AAD" from a drop down menu of identity types.](media/salesforce-connector/sf6.png)</span></span>

<span data-ttu-id="6d242-161">Se você optou por ingerir uma ACL da sua instância do Salesforce e selecionou "não-AAD" para o tipo de identidade, confira Mapear suas identidades não [Azure AD](map-non-aad.md) para obter instruções sobre como mapear as identidades.</span><span class="sxs-lookup"><span data-stu-id="6d242-161">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type, see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

## <a name="step-4b-map-aad-identities"></a><span data-ttu-id="6d242-162">Etapa 4b: Mapear identidades do AAD</span><span class="sxs-lookup"><span data-stu-id="6d242-162">Step 4b: Map AAD identities</span></span>

<span data-ttu-id="6d242-163">Se você optou por ingerir uma ACL da sua instância do Salesforce e selecionou "AAD" para o tipo de identidade, confira Mapear as identidades do [Azure AD](map-aad.md) para obter instruções sobre como mapear as identidades.</span><span class="sxs-lookup"><span data-stu-id="6d242-163">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type, see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="6d242-164">Para saber como configurar o SSO do Azure AD para Salesforce, confira este [tutorial.](https://docs.microsoft.com/azure/active-directory/saas-apps/salesforce-tutorial)</span><span class="sxs-lookup"><span data-stu-id="6d242-164">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](https://docs.microsoft.com/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="6d242-165">Etapa 5: Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="6d242-165">Step 5: Assign property labels</span></span>

<span data-ttu-id="6d242-166">Você pode atribuir uma propriedade de origem a cada rótulo escolhendo em um menu de opções.</span><span class="sxs-lookup"><span data-stu-id="6d242-166">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="6d242-167">Embora essa etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá melhores resultados de pesquisa para usuários finais.</span><span class="sxs-lookup"><span data-stu-id="6d242-167">While this step is not mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span> <span data-ttu-id="6d242-168">Por padrão, algumas das etiquetas como "Title", "URL", "CreatedBy" e "LastModifiedBy" já foram atribuídas a propriedades de origem.</span><span class="sxs-lookup"><span data-stu-id="6d242-168">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="6d242-169">Etapa 6: Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="6d242-169">Step 6: Manage schema</span></span>

<span data-ttu-id="6d242-170">Você pode selecionar quais propriedades de origem devem ser indexadas para que elas sejam acionadas nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6d242-170">You can select what source properties should be indexed so that they show up in search results.</span></span> <span data-ttu-id="6d242-171">Por padrão, o assistente de conexão seleciona um esquema de pesquisa com base em um conjunto de propriedades de origem.</span><span class="sxs-lookup"><span data-stu-id="6d242-171">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="6d242-172">Você pode modificá-lo selecionando as caixas de seleção de cada propriedade e atributo na página de esquema de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6d242-172">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="6d242-173">Os atributos de esquema de pesquisa incluem Pesquisa, Consulta, Recuperação e Refinamento.</span><span class="sxs-lookup"><span data-stu-id="6d242-173">Search schema attributes include Search, Query, Retrieve, and Refine.</span></span>
<span data-ttu-id="6d242-174">Refinar permite definir as propriedades que podem ser usadas posteriormente como refinadores ou filtros personalizados na experiência de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="6d242-174">Refine allows you to define the properties that can be later used as custom refiners or filters in the search experience.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6d242-175">![Selecione o esquema para cada propriedade de origem.</span><span class="sxs-lookup"><span data-stu-id="6d242-175">![Select the schema for each source property.</span></span> <span data-ttu-id="6d242-176">As opções são Consulta, Pesquisa, Recuperar e Refinar](media/salesforce-connector/sf9.png)</span><span class="sxs-lookup"><span data-stu-id="6d242-176">The options are Query, Search, Retrieve, and Refine](media/salesforce-connector/sf9.png)</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="6d242-177">Etapa 7: Definir o agendamento de atualização</span><span class="sxs-lookup"><span data-stu-id="6d242-177">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="6d242-178">O conector salesforce suporta apenas agendamentos de atualização para rastreamentos completos no momento.</span><span class="sxs-lookup"><span data-stu-id="6d242-178">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="6d242-179">Um rastreamento completo localiza objetos excluídos e usuários que foram sincronizados anteriormente com o índice da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d242-179">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="6d242-180">O agendamento recomendado é de uma semana para um rastreamento completo.</span><span class="sxs-lookup"><span data-stu-id="6d242-180">The recommended schedule is one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="6d242-181">Etapa 8: Analisar a conexão</span><span class="sxs-lookup"><span data-stu-id="6d242-181">Step 8: Review connection</span></span>

<span data-ttu-id="6d242-182">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="6d242-182">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="6d242-183">Limitações</span><span class="sxs-lookup"><span data-stu-id="6d242-183">Limitations</span></span>

- <span data-ttu-id="6d242-184">No momento, o conector do Graph não dá suporte ao compartilhamento e compartilhamento baseado em território da Apex usando grupos pessoais da Salesforce.</span><span class="sxs-lookup"><span data-stu-id="6d242-184">The Graph connector doesn't currently support Apex based, territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="6d242-185">Há um bug conhecido na API salesforce que o conector do Graph usa, onde os padrões de toda a organização privada para leads não são compatíveis no momento.</span><span class="sxs-lookup"><span data-stu-id="6d242-185">There's a known bug in the Salesforce API the Graph connector uses, where the private org-wide defaults for leads aren't honored currently.</span></span>  
- <span data-ttu-id="6d242-186">Se um campo tiver segurança de nível de campo (FLS) definida para um perfil, o conector do Graph não ingeri esse campo para nenhum perfil nessa organização salesforce. Como resultado, os usuários não poderão pesquisar os valores desses campos, nem aparecerão nos resultados.</span><span class="sxs-lookup"><span data-stu-id="6d242-186">If a field has field level security (FLS) set for a profile, the Graph connector won't ingest that field for any profiles in that Salesforce org. As a result, users won't be able to search on values for those fields, nor will it show up in the results.</span></span>  
- <span data-ttu-id="6d242-187">Na tela Gerenciar Esquema, esses nomes de propriedade padrão comuns são listados uma vez, as opções são **Consulta** **,** **Pesquisa,** Recuperar e **Refinar** e aplicar a todos ou a nenhum.</span><span class="sxs-lookup"><span data-stu-id="6d242-187">In the Manage Schema screen these common standard property names are listed once, the options are **Query**, **Search**, **Retrieve**, and **Refine**, and apply to all or none.</span></span>
    - <span data-ttu-id="6d242-188">Nome</span><span class="sxs-lookup"><span data-stu-id="6d242-188">Name</span></span>
    - <span data-ttu-id="6d242-189">Url</span><span class="sxs-lookup"><span data-stu-id="6d242-189">Url</span></span>
    - <span data-ttu-id="6d242-190">Descrição</span><span class="sxs-lookup"><span data-stu-id="6d242-190">Description</span></span>
    - <span data-ttu-id="6d242-191">Fax</span><span class="sxs-lookup"><span data-stu-id="6d242-191">Fax</span></span>
    - <span data-ttu-id="6d242-192">Telefone</span><span class="sxs-lookup"><span data-stu-id="6d242-192">Phone</span></span>
    - <span data-ttu-id="6d242-193">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="6d242-193">MobilePhone</span></span>
    - <span data-ttu-id="6d242-194">Email</span><span class="sxs-lookup"><span data-stu-id="6d242-194">Email</span></span>
    - <span data-ttu-id="6d242-195">Tipo</span><span class="sxs-lookup"><span data-stu-id="6d242-195">Type</span></span>
    - <span data-ttu-id="6d242-196">Título</span><span class="sxs-lookup"><span data-stu-id="6d242-196">Title</span></span>
    - <span data-ttu-id="6d242-197">AccountId</span><span class="sxs-lookup"><span data-stu-id="6d242-197">AccountId</span></span>
    - <span data-ttu-id="6d242-198">AccountName</span><span class="sxs-lookup"><span data-stu-id="6d242-198">AccountName</span></span>
    - <span data-ttu-id="6d242-199">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="6d242-199">AccountUrl</span></span>
    - <span data-ttu-id="6d242-200">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="6d242-200">AccountOwner</span></span>
    - <span data-ttu-id="6d242-201">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="6d242-201">AccountOwnerUrl</span></span>
    - <span data-ttu-id="6d242-202">Proprietário</span><span class="sxs-lookup"><span data-stu-id="6d242-202">Owner</span></span>
    - <span data-ttu-id="6d242-203">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="6d242-203">OwnerUrl</span></span>
    - <span data-ttu-id="6d242-204">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="6d242-204">CreatedBy</span></span>
    - <span data-ttu-id="6d242-205">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="6d242-205">CreatedByUrl</span></span>
    - <span data-ttu-id="6d242-206">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="6d242-206">LastModifiedBy</span></span>
    - <span data-ttu-id="6d242-207">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="6d242-207">LastModifiedByUrl</span></span>
    - <span data-ttu-id="6d242-208">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="6d242-208">LastModifiedDate</span></span>
    - <span data-ttu-id="6d242-209">ObjectName</span><span class="sxs-lookup"><span data-stu-id="6d242-209">ObjectName</span></span>
