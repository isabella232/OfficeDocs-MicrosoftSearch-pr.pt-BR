---
title: Conector gráfico de sites corporativos para Pesquisa da Microsoft
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
description: Configurar o conector gráfico de sites corporativos para a Pesquisa da Microsoft
ms.openlocfilehash: 42c3f0a80b21e23bb625db06c4f9e89f2c10de4a
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031625"
---
<!---Previous ms.author: monaray --->

<!-- markdownlint-disable no-inline-html -->

# <a name="enterprise-websites-graph-connector"></a><span data-ttu-id="0df00-103">Conector gráfico de sites corporativos</span><span class="sxs-lookup"><span data-stu-id="0df00-103">Enterprise websites Graph connector</span></span>

<span data-ttu-id="0df00-104">O conector do Graph de sites corporativos permite que sua organização indexe artigos e **conteúdo de seus sites voltados para internamente.**</span><span class="sxs-lookup"><span data-stu-id="0df00-104">The Enterprise websites Graph connector allows your organization to index articles and **content from its internal-facing websites**.</span></span> <span data-ttu-id="0df00-105">Depois de configurar o conector e sincronizar o conteúdo do site, os usuários finais poderão pesquisar esse conteúdo de qualquer cliente de Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0df00-105">After you configure the connector and sync content from the website, end users can search for that content from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="0df00-106">Leia o [**artigo Configurar seu conector do Graph**](configure-connector.md) para entender as instruções gerais de configuração dos conectores do Graph.</span><span class="sxs-lookup"><span data-stu-id="0df00-106">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="0df00-107">Este artigo é para qualquer pessoa que configure, executa e monitore um conector de sites enterprise.</span><span class="sxs-lookup"><span data-stu-id="0df00-107">This article is for anyone who configures, runs, and monitors an Enterprise websites connector.</span></span> <span data-ttu-id="0df00-108">Ele complementa o processo de instalação geral e mostra instruções que se aplicam somente ao conector de sites da Empresa.</span><span class="sxs-lookup"><span data-stu-id="0df00-108">It supplements the general setup process, and shows instructions that apply only for the Enterprise websites connector.</span></span> <span data-ttu-id="0df00-109">Este artigo também inclui informações sobre Solução de [Problemas](#troubleshooting) e [Limitações.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="0df00-109">This article also includes information about [Troubleshooting](#troubleshooting) and [Limitations](#limitations).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="0df00-110">Etapa 1: Adicionar um conector graph no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0df00-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="0df00-111">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="0df00-111">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="0df00-112">Etapa 2: nomear a conexão</span><span class="sxs-lookup"><span data-stu-id="0df00-112">Step 2: Name the connection</span></span>

<span data-ttu-id="0df00-113">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="0df00-113">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="0df00-114">Etapa 3: Configurar as configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="0df00-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="0df00-115">Para se conectar à sua fonte de dados, você precisa preencher a URL raiz do site, selecionar uma fonte de rastreamento e o tipo de autenticação que você gostaria de usar: None, Basic Authentication ou OAuth 2.0 com o [Azure Active Directory (Azure AD)](/azure/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="0df00-115">To connect to your data source, you need to fill in the root URL of the website, select a crawl source, and the type of authentication you'd like to use: None, Basic Authentication, or OAuth 2.0 with [Azure Active Directory (Azure AD)](/azure/active-directory/).</span></span> <span data-ttu-id="0df00-116">Depois de concluir essas informações, selecione Conexão de Teste para verificar suas configurações.</span><span class="sxs-lookup"><span data-stu-id="0df00-116">After you complete this information, select Test Connection to verify your settings.</span></span>

### <a name="url"></a><span data-ttu-id="0df00-117">URL</span><span class="sxs-lookup"><span data-stu-id="0df00-117">URL</span></span>

<span data-ttu-id="0df00-118">Use o campo URL para especificar a raiz do site que você gostaria de rastrear.</span><span class="sxs-lookup"><span data-stu-id="0df00-118">Use the URL field to specify the root of the website that you'd like to crawl.</span></span> <span data-ttu-id="0df00-119">O conector de sites corporativos usará essa URL como ponto de partida e seguirá todos os links dessa URL para seu rastreamento.</span><span class="sxs-lookup"><span data-stu-id="0df00-119">The enterprise websites connector will use this URL as the starting point and follow all the links from this URL for its crawl.</span></span>

> [!NOTE]
> <span data-ttu-id="0df00-120">Se o site que você deseja rastrear tiver um mapa de site definido, o conector rastreará apenas as URLs listadas no sitemap.</span><span class="sxs-lookup"><span data-stu-id="0df00-120">If the site you want to crawl has a sitemap defined, the connector will only crawl the URLs listed in the sitemap.</span></span> <span data-ttu-id="0df00-121">Se nenhum sitemap for definido, o conector fará um rastreamento profundo de todos os links encontrados na URL raiz do site.</span><span class="sxs-lookup"><span data-stu-id="0df00-121">If no sitemap is defined, the connector will do a deep crawl of all the links found on the root URL of the site.</span></span>

### <a name="crawl-mode-cloud-or-on-premises-preview"></a><span data-ttu-id="0df00-122">Modo de rastreamento: Nuvem ou Local (Visualização)</span><span class="sxs-lookup"><span data-stu-id="0df00-122">Crawl mode: Cloud or On-premises (Preview)</span></span>

<span data-ttu-id="0df00-123">O modo de rastreamento determina o tipo de sites que você deseja indexar, na nuvem ou no local.</span><span class="sxs-lookup"><span data-stu-id="0df00-123">The crawl mode determines the type of websites you want to index, either cloud or on-premises.</span></span> <span data-ttu-id="0df00-124">Para seus sites de nuvem, selecione **Nuvem** como o modo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="0df00-124">For your cloud websites, select **Cloud** as the crawl mode.</span></span>

<span data-ttu-id="0df00-125">Além disso, o conector agora dá suporte ao rastreamento de sites locais.</span><span class="sxs-lookup"><span data-stu-id="0df00-125">Also, the connector now supports crawling of on-premises websites.</span></span> <span data-ttu-id="0df00-126">Esse modo está na visualização.</span><span class="sxs-lookup"><span data-stu-id="0df00-126">This mode is in preview.</span></span> <span data-ttu-id="0df00-127">Para acessar seus dados locais, você deve primeiro instalar e configurar o agente conector do Graph.</span><span class="sxs-lookup"><span data-stu-id="0df00-127">To access your on-premises data, you must first install and configure the Graph connector agent.</span></span> <span data-ttu-id="0df00-128">Para saber mais, consulte [Graph connector agent](./on-prem-agent.md).</span><span class="sxs-lookup"><span data-stu-id="0df00-128">To learn more, see [Graph connector agent](./on-prem-agent.md).</span></span>

<span data-ttu-id="0df00-129">Para seus sites locais, selecione **Agente** como o  modo de rastreamento e, no campo Agente Local, escolha o agente de conector do Graph que você instalou e configurou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0df00-129">For your on-premises websites, select **Agent** as the crawl mode and in the **On-Prem Agent** field, choose the Graph connector agent that you installed and configured earlier.</span></span>  

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0df00-130">![Captura de tela do painel Configurações de Conexão para o Conector web da Empresa](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)</span><span class="sxs-lookup"><span data-stu-id="0df00-130">![Screenshot of Connection Settings pane for Enterprise Web connector](media/enterprise-web-connector/connectors-enterpriseweb-settings.png)</span></span>

### <a name="authentication"></a><span data-ttu-id="0df00-131">Autenticação</span><span class="sxs-lookup"><span data-stu-id="0df00-131">Authentication</span></span>

<span data-ttu-id="0df00-132">A Autenticação Básica requer um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="0df00-132">Basic Authentication requires a username and password.</span></span> <span data-ttu-id="0df00-133">Crie essa conta de bot usando o centro de administração [do Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="0df00-133">Create this bot account by using the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="0df00-134">OAuth 2.0 com [o Azure AD](/azure/active-directory/) requer uma ID de recurso, ID do Cliente e Segredo do Cliente.</span><span class="sxs-lookup"><span data-stu-id="0df00-134">OAuth 2.0 with [Azure AD](/azure/active-directory/) requires a resource ID, Client ID, and Client Secret.</span></span> <span data-ttu-id="0df00-135">OAuth 2.0 só funciona com o modo Nuvem.</span><span class="sxs-lookup"><span data-stu-id="0df00-135">OAuth 2.0 only works with Cloud mode.</span></span>

<span data-ttu-id="0df00-136">Para obter mais informações, consulte Autorizar o acesso a aplicativos Web do Azure Active Directory usando o fluxo de concessão de [código OAuth 2.0.](/azure/active-directory/develop/v1-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="0df00-136">For more information, see [Authorize access to Azure Active Directory web applications using OAuth 2.0 code grant flow](/azure/active-directory/develop/v1-protocols-oauth-code).</span></span> <span data-ttu-id="0df00-137">Registre-se com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="0df00-137">Register with the following values:</span></span>

<span data-ttu-id="0df00-138">**Nome:** Pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0df00-138">**Name:** Microsoft Search</span></span> <br/>
<span data-ttu-id="0df00-139">**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`</span><span class="sxs-lookup"><span data-stu-id="0df00-139">**Redirect_URI:** `https://gcs.office.com/v1.0/admin/oauth/callback`</span></span>

<span data-ttu-id="0df00-140">Para obter os valores do recurso, client_id e client_secret, vá para Usar o código de autorização para solicitar um token de **acesso** na página da URL de redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="0df00-140">To get the values for the resource, client_id, and client_secret, go to **Use the authorization code to request an access token** on the redirect URL webpage.</span></span>

<span data-ttu-id="0df00-141">Para saber mais, confira [Início rápido: Registrar um aplicativo com a plataforma de identidade da Microsoft.](/azure/active-directory/develop/quickstart-register-app)</span><span class="sxs-lookup"><span data-stu-id="0df00-141">For even more information, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>

## <a name="step-3a-add-urls-to-exclude-optional-crawl-restrictions"></a><span data-ttu-id="0df00-142">Etapa 3a: Adicionar URLs a excluir (restrições opcionais de rastreamento)</span><span class="sxs-lookup"><span data-stu-id="0df00-142">Step 3a: Add URLs to exclude (Optional crawl restrictions)</span></span>

<span data-ttu-id="0df00-143">Há duas maneiras de impedir que as páginas sejam rastreadas: não permitir que elas sejam rastreadas em seu arquivo robots.txt ou adicioná-las à lista De exclusão.</span><span class="sxs-lookup"><span data-stu-id="0df00-143">There are two ways to prevent pages from being crawled: disallow them in your robots.txt file or add them to the Exclusion list.</span></span>

### <a name="support-for-robotstxt"></a><span data-ttu-id="0df00-144">Suporte para robots.txt</span><span class="sxs-lookup"><span data-stu-id="0df00-144">Support for robots.txt</span></span>

<span data-ttu-id="0df00-145">O conector verifica se há um arquivo robots.txt para seu site raiz e, se existir, ele seguirá e respeitará as instruções encontradas nesse arquivo.</span><span class="sxs-lookup"><span data-stu-id="0df00-145">The connector checks to see if there is a robots.txt file for your root site and, if one exists, it will follow and respect the directions found within that file.</span></span> <span data-ttu-id="0df00-146">Se você não quiser que o conector rastrear determinadas páginas ou diretórios em seu site, poderá chamar essas páginas ou diretórios nas declarações "Desaproteção" no arquivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="0df00-146">If you do not want the connector to crawl certain pages or directories on your site, you can call out those pages or directories in the "Disallow" declarations in your robots.txt file.</span></span>

### <a name="add-urls-to-exclude"></a><span data-ttu-id="0df00-147">Adicionar URLs a excluir</span><span class="sxs-lookup"><span data-stu-id="0df00-147">Add URLs to exclude</span></span>

<span data-ttu-id="0df00-148">Opcionalmente, você pode criar uma lista **de** exclusão para excluir algumas URLs de ser rastreada se esse conteúdo for sensível ou não valer a pena rastrear.</span><span class="sxs-lookup"><span data-stu-id="0df00-148">You can optionally create an **Exclusion list** to exclude some URLs from getting crawled if that content is sensitive or not worth crawling.</span></span> <span data-ttu-id="0df00-149">Para criar uma lista de exclusão, navegue pela URL raiz.</span><span class="sxs-lookup"><span data-stu-id="0df00-149">To create an exclusion list, browse through the root URL.</span></span> <span data-ttu-id="0df00-150">Você pode adicionar as URLs excluídas à lista durante o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="0df00-150">You can add the excluded URLs to the list during the configuration process.</span></span>

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="0df00-151">Etapa 4: Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="0df00-151">Step 4: Assign property labels</span></span>

<span data-ttu-id="0df00-152">Você pode atribuir uma propriedade de origem a cada rótulo escolhendo a partir de um menu de opções.</span><span class="sxs-lookup"><span data-stu-id="0df00-152">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="0df00-153">Embora essa etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá resultados de pesquisa mais precisos para usuários finais.</span><span class="sxs-lookup"><span data-stu-id="0df00-153">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="step-5-manage-schema"></a><span data-ttu-id="0df00-154">Etapa 5: Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="0df00-154">Step 5: Manage schema</span></span>

<span data-ttu-id="0df00-155">Na tela **Gerenciar Esquema,** você pode alterar os atributos de esquema (as opções são **Consulta,** **Pesquisa,** **Recuperar** e **Refinar**) associadas às propriedades, adicionar aliases opcionais e escolher a **propriedade Content.**</span><span class="sxs-lookup"><span data-stu-id="0df00-155">On the **Manage Schema** screen, you can change the schema attributes (the options are **Query**, **Search**, **Retrieve**, and **Refine**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="0df00-156">Etapa 6: Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="0df00-156">Step 6: Manage search permissions</span></span>

<span data-ttu-id="0df00-157">O conector de sites corporativos só dá suporte a permissões de pesquisa visíveis para **Todos.**</span><span class="sxs-lookup"><span data-stu-id="0df00-157">The Enterprise websites connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="0df00-158">Os dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários na organização.</span><span class="sxs-lookup"><span data-stu-id="0df00-158">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="0df00-159">Etapa 7: Definir o cronograma de atualização</span><span class="sxs-lookup"><span data-stu-id="0df00-159">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="0df00-160">O conector de sites corporativos só oferece suporte a uma atualização completa.</span><span class="sxs-lookup"><span data-stu-id="0df00-160">The Enterprise websites connector only supports a full refresh.</span></span> <span data-ttu-id="0df00-161">Isso significa que o conector recrawl todo o conteúdo do site durante cada atualização.</span><span class="sxs-lookup"><span data-stu-id="0df00-161">This means that the connector will recrawl all the website's content during every refresh.</span></span> <span data-ttu-id="0df00-162">Para garantir que o conector tenha tempo suficiente para rastrear o conteúdo, recomendamos definir um grande intervalo de agendamento de atualização.</span><span class="sxs-lookup"><span data-stu-id="0df00-162">To make sure the connector gets enough time to crawl the content, we recommend that you set a large refresh schedule interval.</span></span> <span data-ttu-id="0df00-163">Recomendamos uma atualização agendada entre uma e duas semanas.</span><span class="sxs-lookup"><span data-stu-id="0df00-163">We recommend a scheduled refresh between one and two weeks.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="0df00-164">Etapa 8: Revisar conexão</span><span class="sxs-lookup"><span data-stu-id="0df00-164">Step 8: Review connection</span></span>

<span data-ttu-id="0df00-165">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="0df00-165">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a><span data-ttu-id="0df00-166">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="0df00-166">Troubleshooting</span></span>

<span data-ttu-id="0df00-167">Ao ler o conteúdo do site, o rastreamento pode encontrar alguns erros de origem, que são representados pelos códigos de erro detalhados abaixo.</span><span class="sxs-lookup"><span data-stu-id="0df00-167">When reading the website's content, the crawl may encounter some source errors, which are represented by the detailed error codes below.</span></span> <span data-ttu-id="0df00-168">Para obter mais informações sobre os tipos de erros, vá para a página de detalhes **de** erro após selecionar a conexão.</span><span class="sxs-lookup"><span data-stu-id="0df00-168">To get more information on the types of errors, go to the **error details** page after selecting the connection.</span></span> <span data-ttu-id="0df00-169">Selecione o **código de erro** para ver erros mais detalhados.</span><span class="sxs-lookup"><span data-stu-id="0df00-169">Select the **error code** to see more detailed errors.</span></span> <span data-ttu-id="0df00-170">Consulte Também Gerenciar [seu conector para](./manage-connector.md) saber mais.</span><span class="sxs-lookup"><span data-stu-id="0df00-170">Also refer to [Manage your connector](./manage-connector.md) to learn more.</span></span>

 <span data-ttu-id="0df00-171">Código de erro detalhado</span><span class="sxs-lookup"><span data-stu-id="0df00-171">Detailed Error code</span></span> | <span data-ttu-id="0df00-172">Mensagem de erro</span><span class="sxs-lookup"><span data-stu-id="0df00-172">Error message</span></span>
 --- | ---
 <span data-ttu-id="0df00-173">6001</span><span class="sxs-lookup"><span data-stu-id="0df00-173">6001</span></span> | <span data-ttu-id="0df00-174">O site que está sendo tentado indexar não é acessível</span><span class="sxs-lookup"><span data-stu-id="0df00-174">The site that is being tried to index is not reachable</span></span>
 <span data-ttu-id="0df00-175">6005</span><span class="sxs-lookup"><span data-stu-id="0df00-175">6005</span></span> | <span data-ttu-id="0df00-176">A página de origem que está sendo tentada indexar foi bloqueada de acordo com robots.txt configuração.</span><span class="sxs-lookup"><span data-stu-id="0df00-176">The source page that is being tried to index has been blocked by as per robots.txt configuration.</span></span>
 <span data-ttu-id="0df00-177">6008</span><span class="sxs-lookup"><span data-stu-id="0df00-177">6008</span></span> | <span data-ttu-id="0df00-178">Não é possível resolver o DNS</span><span class="sxs-lookup"><span data-stu-id="0df00-178">Unable to resolve the DNS</span></span>
 <span data-ttu-id="0df00-179">6009</span><span class="sxs-lookup"><span data-stu-id="0df00-179">6009</span></span> | <span data-ttu-id="0df00-180">Para todos os erros do lado do cliente (exceto HTTP 404, 408), consulte CÓDIGOS de erro HTTP 4xxx para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="0df00-180">For all client-side errors (Except HTTP 404, 408), refer to HTTP 4xx error codes for details.</span></span>
 <span data-ttu-id="0df00-181">6013</span><span class="sxs-lookup"><span data-stu-id="0df00-181">6013</span></span> | <span data-ttu-id="0df00-182">A página de origem que está sendo tentada indexar não foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="0df00-182">The source page that is being tried to index could not be found.</span></span> <span data-ttu-id="0df00-183">(Erro HTTP 404)</span><span class="sxs-lookup"><span data-stu-id="0df00-183">(HTTP 404 error)</span></span>
 <span data-ttu-id="0df00-184">6018</span><span class="sxs-lookup"><span data-stu-id="0df00-184">6018</span></span> | <span data-ttu-id="0df00-185">A página de origem não está respondendo e a solicitação foi o tempo de saída. (Erro HTTP 408)</span><span class="sxs-lookup"><span data-stu-id="0df00-185">The source page is not responding, and the request has timed out. (HTTP 408 error)</span></span>
 <span data-ttu-id="0df00-186">6021</span><span class="sxs-lookup"><span data-stu-id="0df00-186">6021</span></span> | <span data-ttu-id="0df00-187">A página de origem que está sendo tentada indexar não tem conteúdo textual na página.</span><span class="sxs-lookup"><span data-stu-id="0df00-187">The source page that is being tried to index has no textual content on the page.</span></span>
 <span data-ttu-id="0df00-188">6023</span><span class="sxs-lookup"><span data-stu-id="0df00-188">6023</span></span> | <span data-ttu-id="0df00-189">A página de origem que está sendo tentada indexar não tem suporte (não é uma página HTML)</span><span class="sxs-lookup"><span data-stu-id="0df00-189">The source page that is being tried to index is unsupported (not an HTML page)</span></span>
 <span data-ttu-id="0df00-190">6024</span><span class="sxs-lookup"><span data-stu-id="0df00-190">6024</span></span> | <span data-ttu-id="0df00-191">A página de origem que está sendo tentada para indexar tem conteúdo sem suporte.</span><span class="sxs-lookup"><span data-stu-id="0df00-191">The source page that is being tried to index has unsupported content.</span></span>

* <span data-ttu-id="0df00-192">Os erros 6001-6013 ocorrem quando a fonte de dados não pode ser alcançada devido a um problema de rede ou quando a própria fonte de dados é excluída, movida ou renomeada.</span><span class="sxs-lookup"><span data-stu-id="0df00-192">Errors 6001-6013 occur when the data source is not reachable due to a network issue or when the data source itself is deleted, moved, or renamed.</span></span> <span data-ttu-id="0df00-193">Verifique se os detalhes da fonte de dados fornecidos ainda são válidos.</span><span class="sxs-lookup"><span data-stu-id="0df00-193">Check if the data source details provided are still valid.</span></span>
* <span data-ttu-id="0df00-194">Os erros 6021-6024 ocorrem quando a fonte de dados contém conteúdo não textual na página ou quando a página não é um HTML.</span><span class="sxs-lookup"><span data-stu-id="0df00-194">Errors 6021-6024 occur when the data source contains non-textual content on the page or when the page is not an HTML.</span></span> <span data-ttu-id="0df00-195">Verifique a fonte de dados e adicione esta página na lista de exclusão ou ignore o erro.</span><span class="sxs-lookup"><span data-stu-id="0df00-195">Check the data source and add this page in exclusion list or ignore the error.</span></span>

## <a name="limitations"></a><span data-ttu-id="0df00-196">Limitações</span><span class="sxs-lookup"><span data-stu-id="0df00-196">Limitations</span></span>

<span data-ttu-id="0df00-197">O conector de sites corporativos não dá suporte à pesquisa de dados em **páginas da Web dinâmicas.**</span><span class="sxs-lookup"><span data-stu-id="0df00-197">The Enterprise websites connector doesn't support searching data on **dynamic webpages**.</span></span> <span data-ttu-id="0df00-198">Exemplos dessas páginas da Web vivem em sistemas de gerenciamento de conteúdo, como [Confluência](https://www.atlassian.com/software/confluence) e [Unily](https://www.unily.com/) ou bancos de dados que armazenam conteúdo do site.</span><span class="sxs-lookup"><span data-stu-id="0df00-198">Examples of those webpages live in content management systems like [Confluence](https://www.atlassian.com/software/confluence) and [Unily](https://www.unily.com/) or databases that store website content.</span></span>