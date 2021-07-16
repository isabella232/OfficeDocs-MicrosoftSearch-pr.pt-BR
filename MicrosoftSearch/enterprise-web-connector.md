---
title: Enterprise sites Graph conector para Pesquisa da Microsoft
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
description: Configurar o conector Enterprise de sites Graph para Pesquisa da Microsoft
ms.openlocfilehash: 32e38c9bef036556dae2734e23b1d26ba4fe2c27
ms.sourcegitcommit: 38a0f09596c2bca0e12bf4cada7b4c64fd4c48e4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53449039"
---
<!---Previous ms.author: monaray --->

<!-- markdownlint-disable no-inline-html -->

# <a name="enterprise-websites-graph-connector"></a><span data-ttu-id="b0352-103">Enterprise sites Graph conector</span><span class="sxs-lookup"><span data-stu-id="b0352-103">Enterprise websites Graph connector</span></span>

<span data-ttu-id="b0352-104">O Enterprise de sites Graph permite que sua organização indexe artigos e **conteúdo de seus sites internos.**</span><span class="sxs-lookup"><span data-stu-id="b0352-104">The Enterprise websites Graph connector allows your organization to index articles and **content from its internal-facing websites**.</span></span> <span data-ttu-id="b0352-105">Depois de configurar o conector e sincronizar o conteúdo do site, os usuários finais poderão pesquisar esse conteúdo de qualquer Pesquisa da Microsoft cliente.</span><span class="sxs-lookup"><span data-stu-id="b0352-105">After you configure the connector and sync content from the website, end users can search for that content from any Microsoft Search client.</span></span>

> [!NOTE]
> <span data-ttu-id="b0352-106">Leia o [**artigo Configurar seu Graph conector para**](configure-connector.md) entender as instruções gerais Graph configuração de conectores.</span><span class="sxs-lookup"><span data-stu-id="b0352-106">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="b0352-107">Este artigo é para qualquer pessoa que configure, executa e monitore um conector Enterprise sites.</span><span class="sxs-lookup"><span data-stu-id="b0352-107">This article is for anyone who configures, runs, and monitors an Enterprise websites connector.</span></span> <span data-ttu-id="b0352-108">Ele complementa o processo de instalação geral e mostra instruções que se aplicam somente ao conector Enterprise de sites.</span><span class="sxs-lookup"><span data-stu-id="b0352-108">It supplements the general setup process, and shows instructions that apply only for the Enterprise websites connector.</span></span> <span data-ttu-id="b0352-109">Este artigo também inclui informações sobre Solução [de Problemas](#troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="b0352-109">This article also includes information about [Troubleshooting](#troubleshooting).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b0352-110">Etapa 1: adicionar um conector Graph no Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0352-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="b0352-111">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="b0352-111">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="b0352-112">Etapa 2: nomear a conexão</span><span class="sxs-lookup"><span data-stu-id="b0352-112">Step 2: Name the connection</span></span>

<span data-ttu-id="b0352-113">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="b0352-113">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="b0352-114">Etapa 3: Configurar as configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="b0352-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="b0352-115">Para se conectar à sua fonte de dados, preencha a URL raiz do site, selecione uma fonte de rastreamento e o tipo de autenticação que você gostaria de usar: None, Basic Authentication ou OAuth 2.0 com [Azure Active Directory (Azure AD)](/azure/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="b0352-115">To connect to your data source, fill in the root URL of the website, select a crawl source, and the type of authentication you'd like to use: None, Basic Authentication, or OAuth 2.0 with [Azure Active Directory (Azure AD)](/azure/active-directory/).</span></span> <span data-ttu-id="b0352-116">Depois de concluir essas informações, selecione Conexão de Teste para verificar suas configurações.</span><span class="sxs-lookup"><span data-stu-id="b0352-116">After you complete this information, select Test Connection to verify your settings.</span></span>

### <a name="url"></a><span data-ttu-id="b0352-117">URL</span><span class="sxs-lookup"><span data-stu-id="b0352-117">URL</span></span>

<span data-ttu-id="b0352-118">Use o campo URL para especificar a raiz do site que você gostaria de rastrear.</span><span class="sxs-lookup"><span data-stu-id="b0352-118">Use the URL field to specify the root of the website that you'd like to crawl.</span></span> <span data-ttu-id="b0352-119">O conector de sites corporativos usará essa URL como ponto de partida e seguirá todos os links dessa URL para seu rastreamento.</span><span class="sxs-lookup"><span data-stu-id="b0352-119">The enterprise websites connector will use this URL as the starting point and follow all the links from this URL for its crawl.</span></span>

### <a name="crawl-websites-listed-in-the-sitemap"></a><span data-ttu-id="b0352-120">Rastrear sites listados no sitemap</span><span class="sxs-lookup"><span data-stu-id="b0352-120">Crawl websites listed in the sitemap</span></span>

<span data-ttu-id="b0352-121">Quando selecionado, o conector rastreará apenas as URLs listadas no sitemap.</span><span class="sxs-lookup"><span data-stu-id="b0352-121">When selected the connector will only crawl the URLs listed in the sitemap.</span></span> <span data-ttu-id="b0352-122">Se não for selecionado ou nenhum mapa de site for encontrado, o conector fará um rastreamento profundo de todos os links encontrados na URL raiz do site.</span><span class="sxs-lookup"><span data-stu-id="b0352-122">If not selected or no site map is found, the connector will do a deep crawl of all the links found on the root URL of the site.</span></span>

### <a name="dynamic-site-configuration"></a><span data-ttu-id="b0352-123">Configuração dinâmica do site</span><span class="sxs-lookup"><span data-stu-id="b0352-123">Dynamic site configuration</span></span>

<span data-ttu-id="b0352-124">Se seu site contiver conteúdo dinâmico, por exemplo, páginas da Web que vivem em sistemas de gerenciamento de conteúdo como Confluência ou Unily, você pode habilitar um rastreador dinâmico.</span><span class="sxs-lookup"><span data-stu-id="b0352-124">If your website contains dynamic content, for example, webpages that live in content management systems like Confluence or Unily, you can enable a dynamic crawler.</span></span> <span data-ttu-id="b0352-125">Para ative-lo, selecione **Habilitar rastreamento para sites dinâmicos.**</span><span class="sxs-lookup"><span data-stu-id="b0352-125">To turn it on, select **Enable crawl for dynamic sites**.</span></span> <span data-ttu-id="b0352-126">O rastreador aguardará a renderização do conteúdo dinâmico antes de começar a rastrear.</span><span class="sxs-lookup"><span data-stu-id="b0352-126">The crawler will wait for dynamic content to render before it begins crawling.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b0352-127">![Captura de tela do painel Configurações conexão para Enterprise Web](media/enterprise-web-connector/connectors-enterpriseweb-connectionsettings-dynamicconfig-small.png)</span><span class="sxs-lookup"><span data-stu-id="b0352-127">![Screenshot of Connection Settings pane for Enterprise Web connector](media/enterprise-web-connector/connectors-enterpriseweb-connectionsettings-dynamicconfig-small.png)</span></span>

<span data-ttu-id="b0352-128">Além da caixa de seleção, há três campos opcionais disponíveis:</span><span class="sxs-lookup"><span data-stu-id="b0352-128">In addition to the check box, there are three optional fields available:</span></span>

1. <span data-ttu-id="b0352-129">**DOM Pronto**: insira o elemento DOM que o rastreador deve usar como o sinal de que o conteúdo está totalmente renderizado e o rastreamento deve começar.</span><span class="sxs-lookup"><span data-stu-id="b0352-129">**DOM Ready**: Enter the DOM element the crawler should use as the signal that the content is fully rendered and the crawl should begin.</span></span>
1. <span data-ttu-id="b0352-130">**Cabeçalhos a adicionar:** especifique quais cabeçalhos HTTP o rastreador deve incluir ao enviar essa URL da Web específica.</span><span class="sxs-lookup"><span data-stu-id="b0352-130">**Headers to Add**: Specify which HTTP headers the crawler should include when sending that specific web URL.</span></span> <span data-ttu-id="b0352-131">Você pode definir vários headers para sites diferentes.</span><span class="sxs-lookup"><span data-stu-id="b0352-131">You can set multiple headers for different websites.</span></span> <span data-ttu-id="b0352-132">Sugerimos incluir valores de token de auth.</span><span class="sxs-lookup"><span data-stu-id="b0352-132">We suggest including auth token values.</span></span>
1. <span data-ttu-id="b0352-133">**Headers to Skip**: Especifique quaisquer headers desnecessários que devem ser excluídos das solicitações dinâmicas de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="b0352-133">**Headers to Skip**: Specify any unnecessary headers that should be excluded from dynamic crawling requests.</span></span>

> [!NOTE]
> <span data-ttu-id="b0352-134">O rastreamento dinâmico só é suportado para o modo de rastreamento do Agente.</span><span class="sxs-lookup"><span data-stu-id="b0352-134">Dynamic crawling is only supported for Agent crawl mode.</span></span>

### <a name="crawl-mode-cloud-or-on-premises"></a><span data-ttu-id="b0352-135">Modo de rastreamento: nuvem ou local</span><span class="sxs-lookup"><span data-stu-id="b0352-135">Crawl mode: Cloud or On-premises</span></span>

<span data-ttu-id="b0352-136">O modo de rastreamento determina o tipo de sites que você deseja indexar, na nuvem ou no local.</span><span class="sxs-lookup"><span data-stu-id="b0352-136">The crawl mode determines the type of websites you want to index, either cloud or on-premises.</span></span> <span data-ttu-id="b0352-137">Para seus sites de nuvem, selecione **Nuvem** como o modo de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="b0352-137">For your cloud websites, select **Cloud** as the crawl mode.</span></span>

<span data-ttu-id="b0352-138">Além disso, o conector agora dá suporte ao rastreamento de sites locais.</span><span class="sxs-lookup"><span data-stu-id="b0352-138">Also, the connector now supports crawling of on-premises websites.</span></span> <span data-ttu-id="b0352-139">Para acessar seus dados locais, você deve primeiro instalar e configurar o Graph conector.</span><span class="sxs-lookup"><span data-stu-id="b0352-139">To access your on-premises data, you must first install and configure the Graph connector agent.</span></span> <span data-ttu-id="b0352-140">Para saber mais, consulte [Graph conector](./on-prem-agent.md).</span><span class="sxs-lookup"><span data-stu-id="b0352-140">To learn more, see [Graph connector agent](./on-prem-agent.md).</span></span>

<span data-ttu-id="b0352-141">Para seus sites locais,  selecione Agente como o  modo de rastreamento e, no campo Agente Local, escolha o Graph conector que você instalou e configurou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b0352-141">For your on-premises websites, select **Agent** as the crawl mode and in the **On-prem Agent** field, choose the Graph connector agent that you installed and configured earlier.</span></span>  

### <a name="authentication"></a><span data-ttu-id="b0352-142">Autenticação</span><span class="sxs-lookup"><span data-stu-id="b0352-142">Authentication</span></span>

<span data-ttu-id="b0352-143">A Autenticação Básica requer um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="b0352-143">Basic Authentication requires a username and password.</span></span> <span data-ttu-id="b0352-144">Crie essa conta de bot usando o [Centro de administração do Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b0352-144">Create this bot account by using the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="b0352-145">OAuth 2.0 com [o Azure AD](/azure/active-directory/) requer uma ID de recurso, ID do Cliente e Segredo do Cliente.</span><span class="sxs-lookup"><span data-stu-id="b0352-145">OAuth 2.0 with [Azure AD](/azure/active-directory/) requires a resource ID, Client ID, and Client Secret.</span></span> <span data-ttu-id="b0352-146">OAuth 2.0 só funciona com o modo Nuvem.</span><span class="sxs-lookup"><span data-stu-id="b0352-146">OAuth 2.0 only works with Cloud mode.</span></span>

<span data-ttu-id="b0352-147">Para obter mais informações, consulte Autorizar o acesso Azure Active Directory aplicativos Web usando o fluxo de concessão de [código OAuth 2.0.](/azure/active-directory/develop/v1-protocols-oauth-code)</span><span class="sxs-lookup"><span data-stu-id="b0352-147">For more information, see [Authorize access to Azure Active Directory web applications using OAuth 2.0 code grant flow](/azure/active-directory/develop/v1-protocols-oauth-code).</span></span> <span data-ttu-id="b0352-148">Registre-se com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b0352-148">Register with the following values:</span></span>

<span data-ttu-id="b0352-149">**Nome:** Pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b0352-149">**Name:** Microsoft Search</span></span> <br/>
<span data-ttu-id="b0352-150">**Redirect_URI:**`https://gcs.office.com/v1.0/admin/oauth/callback`</span><span class="sxs-lookup"><span data-stu-id="b0352-150">**Redirect_URI:** `https://gcs.office.com/v1.0/admin/oauth/callback`</span></span>

<span data-ttu-id="b0352-151">Para obter os valores do recurso, client_id e client_secret, vá para Usar o código de autorização para solicitar um token de **acesso** na página da URL de redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="b0352-151">To get the values for the resource, client_id, and client_secret, go to **Use the authorization code to request an access token** on the redirect URL webpage.</span></span>

<span data-ttu-id="b0352-152">Para obter mais informações, consulte [Início rápido: Registrar um aplicativo com](/azure/active-directory/develop/quickstart-register-app)o plataforma de identidade da Microsoft .</span><span class="sxs-lookup"><span data-stu-id="b0352-152">For even more information, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>

## <a name="step-3a-add-urls-to-exclude-optional-crawl-restrictions"></a><span data-ttu-id="b0352-153">Etapa 3a: Adicionar URLs a excluir (restrições opcionais de rastreamento)</span><span class="sxs-lookup"><span data-stu-id="b0352-153">Step 3a: Add URLs to exclude (Optional crawl restrictions)</span></span>

<span data-ttu-id="b0352-154">Há duas maneiras de impedir que as páginas sejam rastreadas: não permitir que elas sejam rastreadas em seu arquivo robots.txt ou adicioná-las à lista De exclusão.</span><span class="sxs-lookup"><span data-stu-id="b0352-154">There are two ways to prevent pages from being crawled: disallow them in your robots.txt file or add them to the Exclusion list.</span></span>

### <a name="support-for-robotstxt"></a><span data-ttu-id="b0352-155">Suporte para robots.txt</span><span class="sxs-lookup"><span data-stu-id="b0352-155">Support for robots.txt</span></span>

<span data-ttu-id="b0352-156">O conector verifica se há um arquivo robots.txt para seu site raiz e, se existir, ele seguirá e respeitará as instruções encontradas nesse arquivo.</span><span class="sxs-lookup"><span data-stu-id="b0352-156">The connector checks to see if there is a robots.txt file for your root site and, if one exists, it will follow and respect the directions found within that file.</span></span> <span data-ttu-id="b0352-157">Se você não quiser que o conector rastrear determinadas páginas ou diretórios em seu site, poderá chamar essas páginas ou diretórios nas declarações "Desaproteção" no arquivo robots.txt.</span><span class="sxs-lookup"><span data-stu-id="b0352-157">If you do not want the connector to crawl certain pages or directories on your site, you can call out those pages or directories in the "Disallow" declarations in your robots.txt file.</span></span>

### <a name="add-urls-to-exclude"></a><span data-ttu-id="b0352-158">Adicionar URLs a excluir</span><span class="sxs-lookup"><span data-stu-id="b0352-158">Add URLs to exclude</span></span>

<span data-ttu-id="b0352-159">Opcionalmente, você pode criar uma lista **de** exclusão para excluir algumas URLs de ser rastreada se esse conteúdo for sensível ou não valer a pena rastrear.</span><span class="sxs-lookup"><span data-stu-id="b0352-159">You can optionally create an **Exclusion list** to exclude some URLs from getting crawled if that content is sensitive or not worth crawling.</span></span> <span data-ttu-id="b0352-160">Para criar uma lista de exclusão, navegue pela URL raiz.</span><span class="sxs-lookup"><span data-stu-id="b0352-160">To create an exclusion list, browse through the root URL.</span></span> <span data-ttu-id="b0352-161">Você pode adicionar as URLs excluídas à lista durante o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="b0352-161">You can add the excluded URLs to the list during the configuration process.</span></span>

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="b0352-162">Etapa 4: Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="b0352-162">Step 4: Assign property labels</span></span>

<span data-ttu-id="b0352-163">Você pode atribuir uma propriedade de origem a cada rótulo escolhendo a partir de um menu de opções.</span><span class="sxs-lookup"><span data-stu-id="b0352-163">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="b0352-164">Embora essa etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá resultados de pesquisa mais precisos para usuários finais.</span><span class="sxs-lookup"><span data-stu-id="b0352-164">While this step isn't mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="step-5-manage-schema"></a><span data-ttu-id="b0352-165">Etapa 5: Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="b0352-165">Step 5: Manage schema</span></span>

<span data-ttu-id="b0352-166">Na tela **Gerenciar Esquema,** você pode alterar os atributos de esquema (as opções são **Consulta,** **Pesquisa,** **Recuperar** e **Refinar**) associadas às propriedades, adicionar aliases opcionais e escolher a **propriedade Content.**</span><span class="sxs-lookup"><span data-stu-id="b0352-166">On the **Manage Schema** screen, you can change the schema attributes (the options are **Query**, **Search**, **Retrieve**, and **Refine**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="b0352-167">Etapa 6: Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="b0352-167">Step 6: Manage search permissions</span></span>

<span data-ttu-id="b0352-168">O Enterprise de sites só dá suporte a permissões de pesquisa visíveis para **Todos.**</span><span class="sxs-lookup"><span data-stu-id="b0352-168">The Enterprise websites connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="b0352-169">Os dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários na organização.</span><span class="sxs-lookup"><span data-stu-id="b0352-169">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="b0352-170">Etapa 7: Definir o cronograma de atualização</span><span class="sxs-lookup"><span data-stu-id="b0352-170">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="b0352-171">O Enterprise de sites só oferece suporte a uma atualização completa.</span><span class="sxs-lookup"><span data-stu-id="b0352-171">The Enterprise websites connector only supports a full refresh.</span></span> <span data-ttu-id="b0352-172">Isso significa que o conector recrawl todo o conteúdo do site durante cada atualização.</span><span class="sxs-lookup"><span data-stu-id="b0352-172">This means that the connector will recrawl all the website's content during every refresh.</span></span> <span data-ttu-id="b0352-173">Para garantir que o conector tenha tempo suficiente para rastrear o conteúdo, recomendamos definir um grande intervalo de agendamento de atualização.</span><span class="sxs-lookup"><span data-stu-id="b0352-173">To make sure the connector gets enough time to crawl the content, we recommend that you set a large refresh schedule interval.</span></span> <span data-ttu-id="b0352-174">Recomendamos uma atualização agendada entre uma e duas semanas.</span><span class="sxs-lookup"><span data-stu-id="b0352-174">We recommend a scheduled refresh between one and two weeks.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="b0352-175">Etapa 8: Revisar conexão</span><span class="sxs-lookup"><span data-stu-id="b0352-175">Step 8: Review connection</span></span>

<span data-ttu-id="b0352-176">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="b0352-176">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="troubleshooting"></a><span data-ttu-id="b0352-177">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="b0352-177">Troubleshooting</span></span>

<span data-ttu-id="b0352-178">Ao ler o conteúdo do site, o rastreamento pode encontrar alguns erros de origem, que são representados pelos códigos de erro detalhados abaixo.</span><span class="sxs-lookup"><span data-stu-id="b0352-178">When reading the website's content, the crawl may encounter some source errors, which are represented by the detailed error codes below.</span></span> <span data-ttu-id="b0352-179">Para obter mais informações sobre os tipos de erros, vá para a página de detalhes **de** erro após selecionar a conexão.</span><span class="sxs-lookup"><span data-stu-id="b0352-179">To get more information on the types of errors, go to the **error details** page after selecting the connection.</span></span> <span data-ttu-id="b0352-180">Selecione o **código de erro** para ver erros mais detalhados.</span><span class="sxs-lookup"><span data-stu-id="b0352-180">Select the **error code** to see more detailed errors.</span></span> <span data-ttu-id="b0352-181">Consulte Também Gerenciar [seu conector para](./manage-connector.md) saber mais.</span><span class="sxs-lookup"><span data-stu-id="b0352-181">Also refer to [Manage your connector](./manage-connector.md) to learn more.</span></span>

 <span data-ttu-id="b0352-182">Código de erro detalhado</span><span class="sxs-lookup"><span data-stu-id="b0352-182">Detailed Error code</span></span> | <span data-ttu-id="b0352-183">Mensagem de erro</span><span class="sxs-lookup"><span data-stu-id="b0352-183">Error message</span></span>
 --- | ---
 <span data-ttu-id="b0352-184">6001</span><span class="sxs-lookup"><span data-stu-id="b0352-184">6001</span></span> | <span data-ttu-id="b0352-185">O site que está sendo tentado indexar não é acessível</span><span class="sxs-lookup"><span data-stu-id="b0352-185">The site that is being tried to index is not reachable</span></span>
 <span data-ttu-id="b0352-186">6005</span><span class="sxs-lookup"><span data-stu-id="b0352-186">6005</span></span> | <span data-ttu-id="b0352-187">A página de origem que está sendo tentada indexar foi bloqueada de acordo com robots.txt configuração.</span><span class="sxs-lookup"><span data-stu-id="b0352-187">The source page that is being tried to index has been blocked by as per robots.txt configuration.</span></span>
 <span data-ttu-id="b0352-188">6008</span><span class="sxs-lookup"><span data-stu-id="b0352-188">6008</span></span> | <span data-ttu-id="b0352-189">Não é possível resolver o DNS</span><span class="sxs-lookup"><span data-stu-id="b0352-189">Unable to resolve the DNS</span></span>
 <span data-ttu-id="b0352-190">6009</span><span class="sxs-lookup"><span data-stu-id="b0352-190">6009</span></span> | <span data-ttu-id="b0352-191">Para todos os erros do lado do cliente (exceto HTTP 404, 408), consulte CÓDIGOS de erro HTTP 4xxx para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="b0352-191">For all client-side errors (Except HTTP 404, 408), refer to HTTP 4xx error codes for details.</span></span>
 <span data-ttu-id="b0352-192">6013</span><span class="sxs-lookup"><span data-stu-id="b0352-192">6013</span></span> | <span data-ttu-id="b0352-193">A página de origem que está sendo tentada indexar não foi encontrada.</span><span class="sxs-lookup"><span data-stu-id="b0352-193">The source page that is being tried to index could not be found.</span></span> <span data-ttu-id="b0352-194">(Erro HTTP 404)</span><span class="sxs-lookup"><span data-stu-id="b0352-194">(HTTP 404 error)</span></span>
 <span data-ttu-id="b0352-195">6018</span><span class="sxs-lookup"><span data-stu-id="b0352-195">6018</span></span> | <span data-ttu-id="b0352-196">A página de origem não está respondendo e a solicitação foi o tempo de saída. (Erro HTTP 408)</span><span class="sxs-lookup"><span data-stu-id="b0352-196">The source page is not responding, and the request has timed out. (HTTP 408 error)</span></span>
 <span data-ttu-id="b0352-197">6021</span><span class="sxs-lookup"><span data-stu-id="b0352-197">6021</span></span> | <span data-ttu-id="b0352-198">A página de origem que está sendo tentada indexar não tem conteúdo textual na página.</span><span class="sxs-lookup"><span data-stu-id="b0352-198">The source page that is being tried to index has no textual content on the page.</span></span>
 <span data-ttu-id="b0352-199">6023</span><span class="sxs-lookup"><span data-stu-id="b0352-199">6023</span></span> | <span data-ttu-id="b0352-200">A página de origem que está sendo tentada indexar não tem suporte (não é uma página HTML)</span><span class="sxs-lookup"><span data-stu-id="b0352-200">The source page that is being tried to index is unsupported (not an HTML page)</span></span>
 <span data-ttu-id="b0352-201">6024</span><span class="sxs-lookup"><span data-stu-id="b0352-201">6024</span></span> | <span data-ttu-id="b0352-202">A página de origem que está sendo tentada para indexar tem conteúdo sem suporte.</span><span class="sxs-lookup"><span data-stu-id="b0352-202">The source page that is being tried to index has unsupported content.</span></span>

* <span data-ttu-id="b0352-203">Os erros 6001-6013 ocorrem quando a fonte de dados não pode ser alcançada devido a um problema de rede ou quando a própria fonte de dados é excluída, movida ou renomeada.</span><span class="sxs-lookup"><span data-stu-id="b0352-203">Errors 6001-6013 occur when the data source is not reachable due to a network issue or when the data source itself is deleted, moved, or renamed.</span></span> <span data-ttu-id="b0352-204">Verifique se os detalhes da fonte de dados fornecidos ainda são válidos.</span><span class="sxs-lookup"><span data-stu-id="b0352-204">Check if the data source details provided are still valid.</span></span>
* <span data-ttu-id="b0352-205">Os erros 6021-6024 ocorrem quando a fonte de dados contém conteúdo não textual na página ou quando a página não é um HTML.</span><span class="sxs-lookup"><span data-stu-id="b0352-205">Errors 6021-6024 occur when the data source contains non-textual content on the page or when the page is not an HTML.</span></span> <span data-ttu-id="b0352-206">Verifique a fonte de dados e adicione esta página na lista de exclusão ou ignore o erro.</span><span class="sxs-lookup"><span data-stu-id="b0352-206">Check the data source and add this page in exclusion list or ignore the error.</span></span>
