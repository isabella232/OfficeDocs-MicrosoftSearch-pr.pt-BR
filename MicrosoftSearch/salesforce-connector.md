---
title: Conector Salesforce para pesquisa da Microsoft
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector do Salesforce para a pesquisa da Microsoft
ms.openlocfilehash: 149d1d9a297e09e9b895aeb0947c7ff4a3cbdf84
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367645"
---
# <a name="salesforce-connector-preview"></a><span data-ttu-id="2fe87-103">Conector Salesforce (visualização)</span><span class="sxs-lookup"><span data-stu-id="2fe87-103">Salesforce connector (preview)</span></span>

<span data-ttu-id="2fe87-104">Com o conector do Salesforce Graph, sua organização pode indexar os objetos contatos, oportunidades, clientes potenciais e contas em sua instância do Salesforce.</span><span class="sxs-lookup"><span data-stu-id="2fe87-104">With the Salesforce Graph connector, your organization can index Contacts, Opportunities, Leads and Accounts objects in your Salesforce instance.</span></span> <span data-ttu-id="2fe87-105">Depois de configurar o conector e o conteúdo do índice a partir do Salesforce, os usuários finais podem pesquisar esses itens de qualquer cliente de pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2fe87-105">After you configure the connector and index content from Salesforce, end users can search for those items from any Microsoft Search client.</span></span>

<span data-ttu-id="2fe87-106">Este artigo é para os administradores do [Microsoft 365](https://www.microsoft.com/microsoft-365) ou qualquer pessoa que configure, execute e monitore um conector do Salesforce.</span><span class="sxs-lookup"><span data-stu-id="2fe87-106">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors a Salesforce connector.</span></span> <span data-ttu-id="2fe87-107">Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="2fe87-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

>[!IMPORTANT]
><span data-ttu-id="2fe87-108">O conector do Salesforce Graph atualmente é compatível com o verão de 19 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="2fe87-108">The Salesforce Graph connector currently supports Summer '19 or later.</span></span>

## <a name="connection-settings"></a><span data-ttu-id="2fe87-109">Configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="2fe87-109">Connection settings</span></span>

<span data-ttu-id="2fe87-110">Para se conectar à sua instância do Salesforce, você precisa da URL da instância do Salesforce, da ID do cliente e do segredo do cliente para autenticação OAuth.</span><span class="sxs-lookup"><span data-stu-id="2fe87-110">To connect to your Salesforce instance, you need your Salesforce instance URL, the Client ID, and Client Secret for OAuth authentication.</span></span> <span data-ttu-id="2fe87-111">As etapas a seguir explicam como você ou seu administrador do Salesforce podem obter essas informações da sua conta do Salesforce:</span><span class="sxs-lookup"><span data-stu-id="2fe87-111">The following steps explain how you or your Salesforce administrator can get this information from your Salesforce account:</span></span>

- <span data-ttu-id="2fe87-112">Faça logon na sua instância do Salesforce e vá para a instalação</span><span class="sxs-lookup"><span data-stu-id="2fe87-112">Log in to your Salesforce instance and go to Setup</span></span>

- <span data-ttu-id="2fe87-113">Navegue até aplicativos-> Gerenciador de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="2fe87-113">Navigate to Apps -> App Manager.</span></span>

- <span data-ttu-id="2fe87-114">Selecione **novo aplicativo conectado**.</span><span class="sxs-lookup"><span data-stu-id="2fe87-114">Select **New connected app**.</span></span>

- <span data-ttu-id="2fe87-115">Conclua a seção API da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2fe87-115">Complete the API section as follows:</span></span>

    - <span data-ttu-id="2fe87-116">Marque a caixa de seleção para **habilitar as configurações do OAuth**.</span><span class="sxs-lookup"><span data-stu-id="2fe87-116">Select the checkbox for **Enable Oauth Settings**.</span></span>

    - <span data-ttu-id="2fe87-117">Especifique a URL de retorno de chamada como: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span><span class="sxs-lookup"><span data-stu-id="2fe87-117">Specify the Callback URL as: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)</span></span>

    - <span data-ttu-id="2fe87-118">Selecione estes escopos OAuth necessários.</span><span class="sxs-lookup"><span data-stu-id="2fe87-118">Select these required OAuth scopes.</span></span> 

        - <span data-ttu-id="2fe87-119">Acessar e gerenciar seus dados (API)</span><span class="sxs-lookup"><span data-stu-id="2fe87-119">Access and manage your data (api)</span></span> 

        - <span data-ttu-id="2fe87-120">Executar solicitações em seu nome a qualquer momento (refresh_token offline_access)</span><span class="sxs-lookup"><span data-stu-id="2fe87-120">Perform requests on your behalf at any time (refresh_token, offline_access)</span></span> 

    - <span data-ttu-id="2fe87-121">Marque a caixa de seleção para **exigir segredo para o fluxo do servidor Web**.</span><span class="sxs-lookup"><span data-stu-id="2fe87-121">Select the checkbox for **Require secret for web server flow**.</span></span>

    - <span data-ttu-id="2fe87-122">Salve o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2fe87-122">Save the app.</span></span>
    
      ![Seção API na instância do Salesforce após o administrador inserir todas as configurações necessárias listadas acima.](media/salesforce-connector/sf1.png)

- <span data-ttu-id="2fe87-124">Copie a chave do consumidor e o segredo do consumidor.</span><span class="sxs-lookup"><span data-stu-id="2fe87-124">Copy the consumer key and the consumer secret.</span></span> <span data-ttu-id="2fe87-125">Eles serão usados como a ID do cliente e o segredo do cliente quando você definir as configurações de conexão para o seu conector de gráfico no portal de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2fe87-125">These will be used as the Client ID and the Client Secret when you configure the Connection Settings for your Graph Connector in the Microsoft 365 admin portal.</span></span>

  ![Resultados retornados pela seção de API na instância do Salesforce após o administrador enviar todas as configurações necessárias.](media/salesforce-connector/clientsecret.png)
- <span data-ttu-id="2fe87-128">Antes de fechar sua instância do Salesforce, execute as seguintes etapas para garantir que os tokens de atualização não expirem:</span><span class="sxs-lookup"><span data-stu-id="2fe87-128">Before closing your Salesforce instance, perform the following steps to ensure that refresh tokens do not expire:</span></span>
    - <span data-ttu-id="2fe87-129">Vá para o Gerenciador de aplicativos do > app</span><span class="sxs-lookup"><span data-stu-id="2fe87-129">Go to Apps -> App Manager</span></span>
    - <span data-ttu-id="2fe87-130">Localize o aplicativo que você acabou de criar e selecione o menu suspenso à direita.</span><span class="sxs-lookup"><span data-stu-id="2fe87-130">Find the app you just created and select the drop down on the right.</span></span> <span data-ttu-id="2fe87-131">Selecionar **gerenciar**</span><span class="sxs-lookup"><span data-stu-id="2fe87-131">Select **Manage**</span></span>
    - <span data-ttu-id="2fe87-132">Selecionar **Editar políticas**</span><span class="sxs-lookup"><span data-stu-id="2fe87-132">Select **edit policies**</span></span>
    - <span data-ttu-id="2fe87-133">Para política de token de atualização, selecione o **token de atualização é válido até ser revogado**</span><span class="sxs-lookup"><span data-stu-id="2fe87-133">For refresh token policy, select **Refresh token is valid until revoked**</span></span>

  ![Selecione a política de token de atualização chamada "o token de atualização é válido até ser revogado"](media/salesforce-connector/oauthpolicies.png)

<span data-ttu-id="2fe87-135">Agora você pode usar o [centro de administração do M365](https://admin.microsoft.com/) para concluir o restante do processo de configuração do seu conector do Graph.</span><span class="sxs-lookup"><span data-stu-id="2fe87-135">You can now use the [M365 Admin Center](https://admin.microsoft.com/) to complete the rest of the setup process for your Graph connector.</span></span>  

<span data-ttu-id="2fe87-136">Defina as configurações de conexão para o seu conector de gráfico da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2fe87-136">Configure the Connection settings for your Graph connector as follows:</span></span>

- <span data-ttu-id="2fe87-137">Para a URL da instância, use https://[domínio]. My. Salesforce. com onde domínio seria o domínio Salesforce para sua organização.</span><span class="sxs-lookup"><span data-stu-id="2fe87-137">For the Instance URL, use https://[domain].my.salesforce.com where domain would be the Salesforce domain for your organization.</span></span> 
- <span data-ttu-id="2fe87-138">Insira a ID do cliente e o segredo do cliente obtidos da sua instância do Salesforce e selecione entrar.</span><span class="sxs-lookup"><span data-stu-id="2fe87-138">Enter the Client ID and Client Secret you obtained from your Salesforce instance and select Sign in.</span></span>
- <span data-ttu-id="2fe87-139">Se esta é a primeira vez que você tentou entrar com essas configurações, receberá uma janela pop-up solicitando o login no Salesforce com seu nome de usuário e senha de administrador.</span><span class="sxs-lookup"><span data-stu-id="2fe87-139">If this is the first time you have attempted to Sign in with these settings, you will get a pop up asking you to login to Salesforce with your admin username and password.</span></span> <span data-ttu-id="2fe87-140">A captura de tela abaixo mostra o pop-up.</span><span class="sxs-lookup"><span data-stu-id="2fe87-140">The screenshot below shows the popup.</span></span> <span data-ttu-id="2fe87-141">Insira suas credenciais e selecione fazer logon.</span><span class="sxs-lookup"><span data-stu-id="2fe87-141">Enter your credentials and select Log in.</span></span>

  ![Pop-up de login solicitando nome de usuário e senha.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  ><span data-ttu-id="2fe87-143">Se o pop up não aparecer, ele pode estar sendo bloqueado no navegador, portanto, você deve permitir pop-ups e redirecionamentos.</span><span class="sxs-lookup"><span data-stu-id="2fe87-143">If the pop up does not appear, it might be getting blocked in your browser, so you must allow pop-ups and redirects.</span></span>

  >[!NOTE]
  ><span data-ttu-id="2fe87-144">Se sua organização usa logon único (SSO), você pode selecionar **usar domínio personalizado** no canto inferior direito da interface de logon.</span><span class="sxs-lookup"><span data-stu-id="2fe87-144">If your organization uses single sign-on (SSO), you can select **Use Custom Domain** in the bottom, right-hand corner of the login interface.</span></span> <span data-ttu-id="2fe87-145">Insira o domínio e selecione **continuar**.</span><span class="sxs-lookup"><span data-stu-id="2fe87-145">Enter the domain and then select **Continue**.</span></span> <span data-ttu-id="2fe87-146">Ele vai para a página de login específica da sua organização, onde você terá a opção de fazer logon com SSO.</span><span class="sxs-lookup"><span data-stu-id="2fe87-146">It will go to your organization specific login page where you will have an option to login with SSO.</span></span>

- <span data-ttu-id="2fe87-147">Verifique se a conexão teve êxito procurando uma faixa verde que diga "conexão bem-sucedida", conforme mostrado na captura de tela abaixo.</span><span class="sxs-lookup"><span data-stu-id="2fe87-147">Check that the connection was successful by searching for a green banner that says "Connection successful" as show in the screenshot below.</span></span>

  ![Captura de tela do logon bem-sucedido.](media/salesforce-connector/sf5.png)

## <a name="manage-search-permissions"></a><span data-ttu-id="2fe87-150">Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="2fe87-150">Manage search permissions</span></span>
<span data-ttu-id="2fe87-151">Você precisará escolher quais usuários verão os resultados da pesquisa dessa fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="2fe87-151">You will need to choose which users will see search results from this data source.</span></span> <span data-ttu-id="2fe87-152">Se você permitir que apenas determinados usuários do Azure Active Directory (Azure AD) ou não-Azure AD vejam os resultados da pesquisa, será necessário mapear as identidades.</span><span class="sxs-lookup"><span data-stu-id="2fe87-152">If you allow only certain Azure Active Directory (Azure AD) or Non-Azure AD users to see the search results, you will then need to map the identities.</span></span>

### <a name="select-permissions"></a><span data-ttu-id="2fe87-153">Selecionar permissões</span><span class="sxs-lookup"><span data-stu-id="2fe87-153">Select Permissions</span></span>
<span data-ttu-id="2fe87-154">Você pode optar por incluir listas de controle de acesso (ACLs) em sua instância do Salesforce ou pode permitir que todas as pessoas em sua organização vejam os resultados da pesquisa dessa fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="2fe87-154">You can choose to ingest Access Control Lists (ACLs) from your Salesforce instance, or you can allow everyone in your organization to see search results from this data source.</span></span> <span data-ttu-id="2fe87-155">As ACLs podem incluir identidades do Azure Active Directory (AAD) (usuários que são federados do Azure AD para o Salesforce), identidades não do Azure AD (usuários nativos da equipe de vendas que possuem identidades correspondentes no Azure AD) ou ambos.</span><span class="sxs-lookup"><span data-stu-id="2fe87-155">ACLs can include Azure Active Directory (AAD) identities (users who are federated from Azure AD to Salesforce), non-Azure AD identities (native Salesforce users who have corresponding identities in Azure AD), or both.</span></span>

![Selecione a tela permissões que foi concluída por um administrador. O administrador selecionou a opção "apenas pessoas com acesso a esta fonte de dados" e também selecionou "AAD" em um menu suspenso de tipos de identidade.](media/salesforce-connector/sf6.png)

### <a name="map-non-aad-identities"></a><span data-ttu-id="2fe87-157">Mapear identidades não-AAD</span><span class="sxs-lookup"><span data-stu-id="2fe87-157">Map non-AAD identities</span></span> 
<span data-ttu-id="2fe87-158">Se você optar por incluir uma ACL de sua instância do Salesforce e selecionar "não AAD" para o tipo de identidade, confira [mapear suas identidades não do Azure ad](map-non-aad.md) para obter instruções sobre como mapear as identidades.</span><span class="sxs-lookup"><span data-stu-id="2fe87-158">If you chose to ingest an ACL from your Salesforce instance and selected "non-AAD" for the identity type see [Map your non-Azure AD Identities](map-non-aad.md) for instructions on mapping the identities.</span></span>

### <a name="map-aad-identities"></a><span data-ttu-id="2fe87-159">Mapear identidades do AAD</span><span class="sxs-lookup"><span data-stu-id="2fe87-159">Map AAD identities</span></span>
<span data-ttu-id="2fe87-160">Se você optar por incluir uma ACL de sua instância do Salesforce e selecionar "AAD" para o tipo de identidade, confira [mapear suas identidades do Azure ad](map-aad.md) para obter instruções sobre como mapear as identidades.</span><span class="sxs-lookup"><span data-stu-id="2fe87-160">If you chose to ingest an ACL from your Salesforce instance and selected "AAD" for the identity type see [Map your Azure AD Identities](map-aad.md) for instructions on mapping the identities.</span></span> <span data-ttu-id="2fe87-161">Para saber como configurar o Azure AD SSO para Salesforce, consulte este [tutorial](https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/salesforce-tutorial).</span><span class="sxs-lookup"><span data-stu-id="2fe87-161">To learn how to set up Azure AD SSO for Salesforce, see this [tutorial](https://docs.microsoft.com/en-us/azure/active-directory/saas-apps/salesforce-tutorial).</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="2fe87-162">Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="2fe87-162">Assign property labels</span></span> 
<span data-ttu-id="2fe87-163">Você pode atribuir uma propriedade Source a cada rótulo escolhendo a partir de um menu de opções.</span><span class="sxs-lookup"><span data-stu-id="2fe87-163">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="2fe87-164">Embora esta etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá resultados de pesquisa mais precisos para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="2fe87-164">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span> <span data-ttu-id="2fe87-165">Por padrão, alguns dos rótulos como "title", "URL", "CreatedBy" e "LastModifiedBy" já foram atribuídos a propriedades de origem.</span><span class="sxs-lookup"><span data-stu-id="2fe87-165">By default, some of the Labels like "Title," "URL," "CreatedBy," and  "LastModifiedBy" have already been assigned source properties.</span></span>

![Tela atribuir rótulos de propriedade mostrando as propriedades de fonte padrão.](media/salesforce-connector/sf8.png)

## <a name="manage-schema"></a><span data-ttu-id="2fe87-167">Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="2fe87-167">Manage Schema</span></span>
<span data-ttu-id="2fe87-168">Você pode selecionar quais propriedades de fonte devem ser indexadas para que possam ser exibidas nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2fe87-168">You can select what source properties should be indexed so that they can show up in search results.</span></span> <span data-ttu-id="2fe87-169">Por padrão, o assistente de conexão seleciona um esquema de pesquisa com base em um conjunto de propriedades de origem.</span><span class="sxs-lookup"><span data-stu-id="2fe87-169">The connection wizard by default selects a search schema based on a set of source properties.</span></span> <span data-ttu-id="2fe87-170">Você pode modificá-lo marcando as caixas de seleção para cada propriedade e atributo na página de esquema de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2fe87-170">You can modify it by selecting the check boxes for each property and attribute in the search schema page.</span></span> <span data-ttu-id="2fe87-171">Os atributos de esquema de pesquisa incluem pesquisa, consulta, recuperação e refinamento.</span><span class="sxs-lookup"><span data-stu-id="2fe87-171">Search schema attributes include Search, Query, Retrieve and Refine.</span></span> <span data-ttu-id="2fe87-172">Refine permite que você defina as propriedades que podem ser usadas posteriormente como refinadores personalizados ou filtros na experiência de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2fe87-172">Refine allows you to define the properties which can be later used as custom refiners or filters in the search experience.</span></span>  

![Selecione o esquema para cada propriedade de origem.](media/salesforce-connector/sf9.png)

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="2fe87-175">Definir o agendamento de atualização</span><span class="sxs-lookup"><span data-stu-id="2fe87-175">Set the refresh schedule</span></span>

<span data-ttu-id="2fe87-176">O conector Salesforce só suporta agendas de atualização para rastreamentos completos.</span><span class="sxs-lookup"><span data-stu-id="2fe87-176">The Salesforce connector only supports refresh schedules for full crawls currently.</span></span>

>[!IMPORTANT]
><span data-ttu-id="2fe87-177">Um rastreamento completo localiza objetos excluídos e usuários que foram previamente sincronizados com o índice de pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2fe87-177">A full crawl finds deleted objects and users that were previously synced to the Microsoft Search index.</span></span>

<span data-ttu-id="2fe87-178">O agendamento recomendado é uma semana para um rastreamento completo.</span><span class="sxs-lookup"><span data-stu-id="2fe87-178">The recommended schedule is one week for a full crawl.</span></span>

## <a name="limitations"></a><span data-ttu-id="2fe87-179">Limitações</span><span class="sxs-lookup"><span data-stu-id="2fe87-179">Limitations</span></span>

- <span data-ttu-id="2fe87-180">No momento, o conector do Graph não suporta o compartilhamento baseado em território e o compartilhamento por meio de grupos pessoais do Salesforce.</span><span class="sxs-lookup"><span data-stu-id="2fe87-180">The Graph connector does not currently support Apex based , territory-based sharing and sharing using personal groups from Salesforce.</span></span>
- <span data-ttu-id="2fe87-181">Há um bug conhecido na API do Salesforce que o conector do Graph usa onde os padrões de toda a organização privada para clientes potenciais não são honrados atualmente.</span><span class="sxs-lookup"><span data-stu-id="2fe87-181">There is a known bug in the Salesforce API that the Graph connector uses where the private org wide defaults for leads is not honored currently.</span></span>  
- <span data-ttu-id="2fe87-182">Se um campo tiver um conjunto de segurança de nível de campo (FLS) definido para um perfil, o conector do gráfico não inreceberá esse campo para qualquer perfil na organização do Salesforce. Portanto, os usuários não poderão pesquisar os valores desses campos, nem eles aparecerão nos resultados.</span><span class="sxs-lookup"><span data-stu-id="2fe87-182">If a field has field level security (FLS) set for a profile, the Graph connector will not ingest that field for any profiles in that Salesforce org. Users will thus not be able to search on values for those fields, nor will it  show up in the results.</span></span>  
- <span data-ttu-id="2fe87-183">Na tela Gerenciar esquema, esses nomes de propriedade padrão comuns são listados uma vez e a seleção feita para torná-los consultáveis, pesquisáveis e recuperáveis se aplicam a todos ou nenhum.</span><span class="sxs-lookup"><span data-stu-id="2fe87-183">In the Manage Schema screen these common standard property names are listed once and the selection done to make them queryable, searchable and retrievable apply to all or none.</span></span>
    - <span data-ttu-id="2fe87-184">Nome</span><span class="sxs-lookup"><span data-stu-id="2fe87-184">Name</span></span>
    - <span data-ttu-id="2fe87-185">Url</span><span class="sxs-lookup"><span data-stu-id="2fe87-185">Url</span></span> 
    - <span data-ttu-id="2fe87-186">Descrição</span><span class="sxs-lookup"><span data-stu-id="2fe87-186">Description</span></span>
    - <span data-ttu-id="2fe87-187">Fax</span><span class="sxs-lookup"><span data-stu-id="2fe87-187">Fax</span></span>
    - <span data-ttu-id="2fe87-188">Telefone</span><span class="sxs-lookup"><span data-stu-id="2fe87-188">Phone</span></span>
    - <span data-ttu-id="2fe87-189">MobilePhone</span><span class="sxs-lookup"><span data-stu-id="2fe87-189">MobilePhone</span></span>
    - <span data-ttu-id="2fe87-190">Email</span><span class="sxs-lookup"><span data-stu-id="2fe87-190">Email</span></span>
    - <span data-ttu-id="2fe87-191">Tipo</span><span class="sxs-lookup"><span data-stu-id="2fe87-191">Type</span></span>
    - <span data-ttu-id="2fe87-192">Título</span><span class="sxs-lookup"><span data-stu-id="2fe87-192">Title</span></span>
    - <span data-ttu-id="2fe87-193">AccountId</span><span class="sxs-lookup"><span data-stu-id="2fe87-193">AccountId</span></span>
    - <span data-ttu-id="2fe87-194">AccountName</span><span class="sxs-lookup"><span data-stu-id="2fe87-194">AccountName</span></span>
    - <span data-ttu-id="2fe87-195">AccountUrl</span><span class="sxs-lookup"><span data-stu-id="2fe87-195">AccountUrl</span></span>
    - <span data-ttu-id="2fe87-196">AccountOwner</span><span class="sxs-lookup"><span data-stu-id="2fe87-196">AccountOwner</span></span>
    - <span data-ttu-id="2fe87-197">AccountOwnerUrl</span><span class="sxs-lookup"><span data-stu-id="2fe87-197">AccountOwnerUrl</span></span>
    - <span data-ttu-id="2fe87-198">Proprietário</span><span class="sxs-lookup"><span data-stu-id="2fe87-198">Owner</span></span>
    - <span data-ttu-id="2fe87-199">OwnerUrl</span><span class="sxs-lookup"><span data-stu-id="2fe87-199">OwnerUrl</span></span>
    - <span data-ttu-id="2fe87-200">CreatedBy</span><span class="sxs-lookup"><span data-stu-id="2fe87-200">CreatedBy</span></span> 
    - <span data-ttu-id="2fe87-201">CreatedByUrl</span><span class="sxs-lookup"><span data-stu-id="2fe87-201">CreatedByUrl</span></span> 
    - <span data-ttu-id="2fe87-202">LastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="2fe87-202">LastModifiedBy</span></span> 
    - <span data-ttu-id="2fe87-203">LastModifiedByUrl</span><span class="sxs-lookup"><span data-stu-id="2fe87-203">LastModifiedByUrl</span></span> 
    - <span data-ttu-id="2fe87-204">LastModifiedDate</span><span class="sxs-lookup"><span data-stu-id="2fe87-204">LastModifiedDate</span></span>
    - <span data-ttu-id="2fe87-205">ObjectName</span><span class="sxs-lookup"><span data-stu-id="2fe87-205">ObjectName</span></span> 