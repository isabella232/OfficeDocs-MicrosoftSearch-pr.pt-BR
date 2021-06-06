---
title: Conector de Graph salesforce para Pesquisa da Microsoft
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector de Graph Salesforce para a Pesquisa da Microsoft
ms.openlocfilehash: 7d73454fb909db24514c969f34158e3f2be5e34c
ms.sourcegitcommit: 6cffa2d29448be9a22514e7b4c3009c522af0860
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52774085"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a><span data-ttu-id="f05b9-103">Conector Graph Salesforce (visualização)</span><span class="sxs-lookup"><span data-stu-id="f05b9-103">Salesforce Graph connector (preview)</span></span>

<span data-ttu-id="f05b9-104">O conector Graph Salesforce permite que sua organização indexe objetos Contatos, Oportunidades, Leads e Contas em sua instância do Salesforce.</span><span class="sxs-lookup"><span data-stu-id="f05b9-104">The Salesforce Graph connector, allows your organization to index Contacts, Opportunities, Leads, and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="f05b9-105">Depois de configurar o conector e o conteúdo de índice do Salesforce, os usuários finais podem pesquisar esses itens de qualquer cliente de Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f05b9-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="f05b9-106">Leia o [**artigo Instalação do conector Graph para**](configure-connector.md) entender as instruções gerais Graph configuração de conectores.</span><span class="sxs-lookup"><span data-stu-id="f05b9-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="f05b9-107">Este artigo é para qualquer pessoa que configure, executa e monitore um conector Graph Salesforce.</span><span class="sxs-lookup"><span data-stu-id="f05b9-107">This article is for anyone who configures, runs, and monitors a Salesforce Graph connector.</span></span> <span data-ttu-id="f05b9-108">Ele complementa o processo de instalação geral e mostra instruções que se aplicam somente ao conector Graph Salesforce.</span><span class="sxs-lookup"><span data-stu-id="f05b9-108">It supplements the general setup process, and shows instructions that apply only for the Salesforce Graph connector.</span></span> <span data-ttu-id="f05b9-109">Este artigo também inclui informações sobre [Limitações.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="f05b9-109">This article also includes information about [Limitations](#limitations).</span></span>

>[!IMPORTANT]
><span data-ttu-id="f05b9-110">O conector Graph Salesforce atualmente dá suporte ao Verão 19 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="f05b9-110">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="f05b9-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f05b9-111">Before you get started</span></span>

<span data-ttu-id="f05b9-112">Para se conectar à sua instância do Salesforce, você precisa da URL da instância do Salesforce, da ID do Cliente e do Segredo do Cliente para autenticação OAuth.</span><span class="sxs-lookup"><span data-stu-id="f05b9-112">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="f05b9-113">As etapas a seguir explicam como você ou o administrador do Salesforce podem obter essas informações da sua conta do Salesforce:</span><span class="sxs-lookup"><span data-stu-id="f05b9-113">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="f05b9-114">Faça logoff em sua instância do Salesforce e vá para a Instalação</span><span class="sxs-lookup"><span data-stu-id="f05b9-114">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="f05b9-115">Navegue até Apps -> App Manager.</span><span class="sxs-lookup"><span data-stu-id="f05b9-115">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="f05b9-116">Selecione **Novo aplicativo conectado**.</span><span class="sxs-lookup"><span data-stu-id="f05b9-116">Select **New connected app**.</span></span>

- <span data-ttu-id="f05b9-117">Conclua a seção API da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="f05b9-117">Complete the API section as follows:</span></span>

    - <span data-ttu-id="f05b9-118">Marque a caixa de seleção **Habilitar o Oauth Configurações**.</span><span class="sxs-lookup"><span data-stu-id="f05b9-118">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="f05b9-119">Especifique a URL de retorno de chamada como: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="f05b9-119">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="f05b9-120">Selecione esses escopos OAuth necessários.</span><span class="sxs-lookup"><span data-stu-id="f05b9-120">Select these required OAuth scopes.</span></span>

        - <span data-ttu-id="f05b9-121">Acessar e gerenciar seus dados (api)</span><span class="sxs-lookup"><span data-stu-id="f05b9-121">Access and manage your data (api)</span></span>

        - <span data-ttu-id="f05b9-122">Execute solicitações em seu nome a qualquer momento (refresh_token, offline_access)</span><span class="sxs-lookup"><span data-stu-id="f05b9-122">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span>

    - <span data-ttu-id="f05b9-123">Selecione a caixa de seleção para **Exigir segredo para fluxo de servidor Web.**</span><span class="sxs-lookup"><span data-stu-id="f05b9-123">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="f05b9-124">Salve o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f05b9-124">Save the app.</span></span>
    
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="f05b9-125">![Seção API na instância do Salesforce após o administrador ter inserido todas as configurações necessárias listadas acima.](media/salesforce-connector/sf1.png)</span><span class="sxs-lookup"><span data-stu-id="f05b9-125">![API section in Salesforce instance after admin has entered all required configurations listed above.](media/salesforce-connector/sf1.png)</span></span>

- <span data-ttu-id="f05b9-126">Copie a chave do consumidor e o segredo do consumidor.</span><span class="sxs-lookup"><span data-stu-id="f05b9-126">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="f05b9-127">Essas informações serão usadas como a ID do Cliente e o Segredo do Cliente quando você configurar a conexão Configurações para o conector Graph no portal de administração Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f05b9-127">This information will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="f05b9-128">![Resultados retornados pela seção API na instância salesforce depois que o administrador enviou todas as configurações necessárias.</span><span class="sxs-lookup"><span data-stu-id="f05b9-128">![Results returned by API section in Salesforce instance after admin has submitted all required configurations.</span></span> <span data-ttu-id="f05b9-129">A Chave do Consumidor está na parte superior da coluna esquerda e o Segredo do Consumidor está na parte superior da coluna direita.](media/salesforce-connector/clientsecret.png)</span><span class="sxs-lookup"><span data-stu-id="f05b9-129">Consumer Key is at top of left column and Consumer Secret is at top of right column.](media/salesforce-connector/clientsecret.png)</span></span>
  
- <span data-ttu-id="f05b9-130">Antes de fechar sua instância do Salesforce, siga estas etapas para garantir que os tokens de atualização não expirem:</span><span class="sxs-lookup"><span data-stu-id="f05b9-130">Before closing your Salesforce instance, follow these steps to ensure that refresh tokens don't expire:</span></span>
    - <span data-ttu-id="f05b9-131">Acesse Apps -> App Manager</span><span class="sxs-lookup"><span data-stu-id="f05b9-131">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="f05b9-132">Encontre o aplicativo criado e selecione o drop-down à direita.</span><span class="sxs-lookup"><span data-stu-id="f05b9-132">Find the app you created and select the drop-down on the right.</span></span> <span data-ttu-id="f05b9-133">Selecione **Gerenciar**</span><span class="sxs-lookup"><span data-stu-id="f05b9-133">Select **Manage**</span></span>
    - <span data-ttu-id="f05b9-134">Selecionar **políticas de edição**</span><span class="sxs-lookup"><span data-stu-id="f05b9-134">Select **edit policies**</span></span>
    - <span data-ttu-id="f05b9-135">Para política de token de atualização, selecione **Atualizar token é válido até revogado**</span><span class="sxs-lookup"><span data-stu-id="f05b9-135">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="f05b9-136">![Selecione a Política de Token de Atualização chamada "O token de atualização é válido até revogado"](media/salesforce-connector/oauthpolicies.png)</span><span class="sxs-lookup"><span data-stu-id="f05b9-136">![Select the Refresh Token Policy named "Refresh token is valid until revoked "](media/salesforce-connector/oauthpolicies.png)</span></span>

<span data-ttu-id="f05b9-137">Agora você pode usar o Centro de Administração [do M365](https://admin.microsoft.com/) para concluir o restante do processo de instalação para o conector Graph usuário.</span><span class="sxs-lookup"><span data-stu-id="f05b9-137">You can now use the [M365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="f05b9-138">Etapa 1: adicionar um conector Graph no centro de Microsoft 365 de administração</span><span class="sxs-lookup"><span data-stu-id="f05b9-138">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="f05b9-139">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="f05b9-139">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="f05b9-140">Etapa 2: nomear a conexão</span><span class="sxs-lookup"><span data-stu-id="f05b9-140">Step 2: Name the connection</span></span>

<span data-ttu-id="f05b9-141">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="f05b9-141">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="f05b9-142">Etapa 3: Configurar as configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="f05b9-142">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="f05b9-143">Para a URL de instância, use https://[domain].my.salesforce.com onde o domínio seria o domínio Salesforce para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f05b9-143">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span>

<span data-ttu-id="f05b9-144">Insira a ID do Cliente e o Segredo do Cliente que você obteve da sua instância do Salesforce e selecione Entrar.</span><span class="sxs-lookup"><span data-stu-id="f05b9-144">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>

<span data-ttu-id="f05b9-145">Na primeira vez que você tentar entrar com essas configurações, você obterá um pop-up solicitando que você faça logoff no Salesforce com seu nome de usuário e senha do administrador.</span><span class="sxs-lookup"><span data-stu-id="f05b9-145">The first time you've attempted to sign in with these settings, you'll get a pop-up asking you to log in to Salesforce with your admin username and password.</span></span> <span data-ttu-id="f05b9-146">A captura de tela abaixo mostra o pop-up.</span><span class="sxs-lookup"><span data-stu-id="f05b9-146">The screenshot below shows the popup.</span></span> <span data-ttu-id="f05b9-147">Insira suas credenciais e selecione "Entrar".</span><span class="sxs-lookup"><span data-stu-id="f05b9-147">Enter your credentials and select "Log In".</span></span>

  ![Pop-up de logon solicitando nome de usuário e senha.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="f05b9-149">Se o pop-up não aparecer, ele pode estar sendo bloqueado no navegador, portanto, você deve permitir pop-ups e redirecionamentos.</span><span class="sxs-lookup"><span data-stu-id="f05b9-149">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

<span data-ttu-id="f05b9-150">Verifique se a conexão foi bem-sucedida pesquisando uma faixa verde que diz "Conexão bem-sucedida" como mostra a captura de tela abaixo.</span><span class="sxs-lookup"><span data-stu-id="f05b9-150">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="f05b9-151">![Captura de tela de logon bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="f05b9-151">![Screenshot of successful login.</span></span> <span data-ttu-id="f05b9-152">A faixa verde que diz "Conexão bem-sucedida" está localizada no campo para a URL da instância do Salesforce](media/salesforce-connector/sf5.png)</span><span class="sxs-lookup"><span data-stu-id="f05b9-152">The green banner that says "Connection successful" is located under the field for your Salesforce Instance URL](media/salesforce-connector/sf5.png)</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="f05b9-153">Etapa 4: Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="f05b9-153">Step 4: Manage search permissions</span></span>

<span data-ttu-id="f05b9-154">Você precisará escolher quais usuários verão os resultados da pesquisa nesta fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f05b9-154">You'll need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="f05b9-155">Se você permitir que Azure Active Directory apenas determinados usuários do Azure AD (Azure AD) ou não do Azure AD vejam os resultados da pesquisa, certifique-se de mapear as identidades.</span><span class="sxs-lookup"><span data-stu-id="f05b9-155">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, make sure you map the identities.</span></span>

### <a name="step-4a-select-permissions"></a><span data-ttu-id="f05b9-156">Etapa 4.a: Selecionar permissões</span><span class="sxs-lookup"><span data-stu-id="f05b9-156">Step 4.a: Select permissions</span></span>

<span data-ttu-id="f05b9-157">Você pode optar por ingerir listas de controle de acesso (ACLs) de sua instância do Salesforce ou permitir que todos em sua organização vejam os resultados da pesquisa a partir dessa fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f05b9-157">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="f05b9-158">As ACLs podem incluir Azure Active Directory identidades (AAD) (usuários federados do Azure AD para o Salesforce), identidades não-Azure AD (usuários nativos do Salesforce que têm identidades correspondentes no Azure AD) ou ambos.</span><span class="sxs-lookup"><span data-stu-id="f05b9-158">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

>[!NOTE]
><span data-ttu-id="f05b9-159">Se você usar um Provedor de Identidade de terceiros, como Ping ID ou secureAuth, selecione "não-AAD" como o tipo de identidade.</span><span class="sxs-lookup"><span data-stu-id="f05b9-159">If you use a third-party Identity Provider like Ping ID or secureAuth, you should select "non-AAD" as the identity type.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f05b9-160">![Selecione a tela de permissões que foi concluída por um administrador. O administrador selecionou a opção "Somente pessoas com acesso a essa fonte de dados" e também selecionou "AAD" em um menu suspenso de tipos de identidade.](media/salesforce-connector/sf6.png)</span><span class="sxs-lookup"><span data-stu-id="f05b9-160">![Select permissions screen that has been completed by an admin. The admin has selected the "Only people with access to this data source" option and has also selected "AAD" from a drop down menu of identity types.](media/salesforce-connector/sf6.png)</span></span>

<span data-ttu-id="f05b9-161">Se você optou por ingerir um ACL da sua instância do Salesforce e selecionou "não-AAD" para o tipo de identidade, consulte Mapear suas Identidades [não-Azure AD](map-non-aad.md) para obter instruções sobre como mapear as identidades.</span><span class="sxs-lookup"><span data-stu-id="f05b9-161">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type, see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

### <a name="step-4b-map-aad-identities"></a><span data-ttu-id="f05b9-162">Etapa 4.b: Mapear identidades do AAD</span><span class="sxs-lookup"><span data-stu-id="f05b9-162">Step 4.b: Map AAD identities</span></span>

<span data-ttu-id="f05b9-163">Se você optou por ingerir um ACL da sua instância do Salesforce e selecionou "AAD" para o tipo de identidade, consulte Mapear suas Identidades do [Azure AD](map-aad.md) para obter instruções sobre como mapear as identidades.</span><span class="sxs-lookup"><span data-stu-id="f05b9-163">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type, see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="f05b9-164">Para saber como configurar o SSO do Azure AD para Salesforce, consulte este [tutorial](/azure/active-directory/saas-apps/salesforce-tutorial).</span><span class="sxs-lookup"><span data-stu-id="f05b9-164">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

### <a name="apply-user-mapping-to-sync-your-salesforce-identities-to-azure-ad-identities"></a><span data-ttu-id="f05b9-165">Aplicar mapeamento de usuário para sincronizar suas identidades do Salesforce às identidades do Azure AD</span><span class="sxs-lookup"><span data-stu-id="f05b9-165">Apply user mapping to sync your Salesforce identities to Azure AD identities</span></span>

<span data-ttu-id="f05b9-166">Neste vídeo, você pode ver o processo de autenticação à sua instância do Salesforce, sincronizar suas identidades não Azure Active Directory com suas identidades Azure Active Directory e aplicar os recortes de segurança apropriados aos itens do Salesforce.</span><span class="sxs-lookup"><span data-stu-id="f05b9-166">In this video you can see the process to authenticate to your Salesforce instance, sync your non-Azure Active Directory identities to your Azure Active Directory identities, and apply the proper security trimmings to your Salesforce items.</span></span>

> [!VIDEO https://www.youtube-nocookie.com/embed/SZYiFxZMKcM]

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="f05b9-167">Etapa 5: Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="f05b9-167">Step 5: Assign property labels</span></span>

<span data-ttu-id="f05b9-168">Você pode atribuir uma propriedade de origem a cada rótulo escolhendo a partir de um menu de opções.</span><span class="sxs-lookup"><span data-stu-id="f05b9-168">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="f05b9-169">Embora essa etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá melhores resultados de pesquisa para usuários finais.</span><span class="sxs-lookup"><span data-stu-id="f05b9-169">While this step is not mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span> <span data-ttu-id="f05b9-170">Por padrão, algumas das propriedades de origem "Title", "URL", "CreatedBy" e "LastModifiedBy" já foram atribuídas.</span><span class="sxs-lookup"><span data-stu-id="f05b9-170">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="f05b9-171">Etapa 6: Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="f05b9-171">Step 6: Manage schema</span></span>

<span data-ttu-id="f05b9-172">Você pode selecionar quais propriedades de origem devem ser indexadas para que elas sejam acionadas nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f05b9-172">You can select what source properties should be indexed so that they show up in search results.</span></span> <span data-ttu-id="f05b9-173">O assistente de conexão por padrão seleciona um esquema de pesquisa com base em um conjunto de propriedades de origem.</span><span class="sxs-lookup"><span data-stu-id="f05b9-173">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="f05b9-174">Você pode modificá-lo selecionando as caixas de seleção para cada propriedade e atributo na página esquema de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f05b9-174">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="f05b9-175">Os atributos de esquema de pesquisa incluem Pesquisa, Consulta, Recuperação e Refinamento.</span><span class="sxs-lookup"><span data-stu-id="f05b9-175">Search schema attributes include Search, Query, Retrieve, and Refine.</span></span>
<span data-ttu-id="f05b9-176">Refinar permite definir as propriedades que podem ser usadas posteriormente como refinadores ou filtros personalizados na experiência de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f05b9-176">Refine allows you to define the properties that can be later used as custom refiners or filters in the search experience.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f05b9-177">![Selecione o esquema para cada propriedade de origem.</span><span class="sxs-lookup"><span data-stu-id="f05b9-177">![Select the schema for each source property.</span></span> <span data-ttu-id="f05b9-178">As opções são Consulta, Pesquisa, Recuperação e Refine](media/salesforce-connector/sf9.png)</span><span class="sxs-lookup"><span data-stu-id="f05b9-178">The options are Query, Search, Retrieve, and Refine](media/salesforce-connector/sf9.png)</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="f05b9-179">Etapa 7: Definir o cronograma de atualização</span><span class="sxs-lookup"><span data-stu-id="f05b9-179">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="f05b9-180">O conector do Salesforce dá suporte apenas a agendas de atualização para rastreamentos completos no momento.</span><span class="sxs-lookup"><span data-stu-id="f05b9-180">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="f05b9-181">Um rastreamento completo localiza objetos excluídos e usuários que foram sincronizados anteriormente com o índice de Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f05b9-181">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="f05b9-182">A agenda recomendada é de uma semana para um rastreamento completo.</span><span class="sxs-lookup"><span data-stu-id="f05b9-182">The recommended schedule is one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="f05b9-183">Etapa 8: Revisar conexão</span><span class="sxs-lookup"><span data-stu-id="f05b9-183">Step 8: Review connection</span></span>

<span data-ttu-id="f05b9-184">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="f05b9-184">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="f05b9-185">Limitações</span><span class="sxs-lookup"><span data-stu-id="f05b9-185">Limitations</span></span>

- <span data-ttu-id="f05b9-186">O Graph conector atualmente não dá suporte ao compartilhamento e compartilhamento baseado em território baseado em Apex usando grupos pessoais do Salesforce.</span><span class="sxs-lookup"><span data-stu-id="f05b9-186">The Graph connector doesn't currently support Apex based, territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="f05b9-187">Há um bug conhecido na API salesforce que o conector Graph usa, onde os padrões de toda a organização privada para leads não são acadados no momento.</span><span class="sxs-lookup"><span data-stu-id="f05b9-187">There's a known bug in the Salesforce API the Graph connector uses, where the private org-wide defaults for leads aren't honored currently.</span></span>  
- <span data-ttu-id="f05b9-188">Se um campo tiver fls (segurança de nível de campo) definido para um perfil, o conector Graph não ingerirá esse campo para nenhum perfil nessa organização do Salesforce. Como resultado, os usuários não poderão pesquisar os valores desses campos, nem aparecerão nos resultados.</span><span class="sxs-lookup"><span data-stu-id="f05b9-188">If a field has field level security (FLS) set for a profile, the Graph connector won't ingest that field for any profiles in that Salesforce org. As a result, users won't be able to search on values for those fields, nor will it show up in the results.</span></span>  
- <span data-ttu-id="f05b9-189">Na tela Gerenciar Esquema, esses nomes de propriedade padrão comuns são listados uma vez, as opções são **Consulta,** **Pesquisa,** **Recuperar** e **Refinar** e aplicar a todos ou a nenhum.</span><span class="sxs-lookup"><span data-stu-id="f05b9-189">In the Manage Schema screen these common standard property names are listed once, the options are **Query**, **Search**, **Retrieve**, and **Refine**, and apply to all or none.</span></span>
    - <span data-ttu-id="f05b9-190">Nome</span><span class="sxs-lookup"><span data-stu-id="f05b9-190">Name</span></span>
    - <span data-ttu-id="f05b9-191">Url</span><span class="sxs-lookup"><span data-stu-id="f05b9-191">Url</span></span>
    - <span data-ttu-id="f05b9-192">Descrição</span><span class="sxs-lookup"><span data-stu-id="f05b9-192">Description</span></span>
    - <span data-ttu-id="f05b9-193">Fax</span><span class="sxs-lookup"><span data-stu-id="f05b9-193">Fax</span></span>
    - <span data-ttu-id="f05b9-194">Telefone</span><span class="sxs-lookup"><span data-stu-id="f05b9-194">Phone</span></span>
    - <span data-ttu-id="f05b9-195">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="f05b9-195">MobilePhone</span></span>
    - <span data-ttu-id="f05b9-196">Email</span><span class="sxs-lookup"><span data-stu-id="f05b9-196">Email</span></span>
    - <span data-ttu-id="f05b9-197">Tipo</span><span class="sxs-lookup"><span data-stu-id="f05b9-197">Type</span></span>
    - <span data-ttu-id="f05b9-198">Título</span><span class="sxs-lookup"><span data-stu-id="f05b9-198">Title</span></span>
    - <span data-ttu-id="f05b9-199">AccountId</span><span class="sxs-lookup"><span data-stu-id="f05b9-199">AccountId</span></span>
    - <span data-ttu-id="f05b9-200">AccountName</span><span class="sxs-lookup"><span data-stu-id="f05b9-200">AccountName</span></span>
    - <span data-ttu-id="f05b9-201">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="f05b9-201">AccountUrl</span></span>
    - <span data-ttu-id="f05b9-202">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="f05b9-202">AccountOwner</span></span>
    - <span data-ttu-id="f05b9-203">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="f05b9-203">AccountOwnerUrl</span></span>
    - <span data-ttu-id="f05b9-204">Proprietário</span><span class="sxs-lookup"><span data-stu-id="f05b9-204">Owner</span></span>
    - <span data-ttu-id="f05b9-205">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="f05b9-205">OwnerUrl</span></span>
    - <span data-ttu-id="f05b9-206">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="f05b9-206">CreatedBy</span></span>
    - <span data-ttu-id="f05b9-207">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="f05b9-207">CreatedByUrl</span></span>
    - <span data-ttu-id="f05b9-208">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="f05b9-208">LastModifiedBy</span></span>
    - <span data-ttu-id="f05b9-209">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="f05b9-209">LastModifiedByUrl</span></span>
    - <span data-ttu-id="f05b9-210">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="f05b9-210">LastModifiedDate</span></span>
    - <span data-ttu-id="f05b9-211">ObjectName</span><span class="sxs-lookup"><span data-stu-id="f05b9-211">ObjectName</span></span>
