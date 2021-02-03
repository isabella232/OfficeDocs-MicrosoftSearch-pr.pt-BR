---
title: Visão geral dos Conectores do Microsoft Graph
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
description: Visão geral dos conectores do Microsoft Graph para a Pesquisa da Microsoft
ms.openlocfilehash: 13127d092fe4e624ed448037d83f16f83ddc560a
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084871"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="ffc7b-103">Visão geral dos conectores do Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="ffc7b-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="ffc7b-104">[A Pesquisa da Microsoft](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexa todos [os dados do Microsoft 365](https://www.microsoft.com/microsoft-365) para torná-los pesquisáveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="ffc7b-105">Com os conectores do Microsoft Graph, sua organização pode indexar dados de terceiros para que eles apareçam nos resultados da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="ffc7b-106">Esse recurso expande os tipos de fontes de conteúdo que podem ser pesquisados nos aplicativos de produtividade do Microsoft 365 e no ecossistema mais amplo da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-106">This feature expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="ffc7b-107">Os dados de terceiros podem ser hospedados no local ou nas nuvens públicas ou privadas.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="ffc7b-108">Este artigo destina-se a ajudar os administradores do Microsoft 365 a localizar os recursos disponíveis para responder às seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="ffc7b-108">This article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="ffc7b-109">Quais fontes de dados podem ser conectadas à Pesquisa da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="ffc7b-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="ffc7b-110">Como faço para gerenciar minhas conexões?</span><span class="sxs-lookup"><span data-stu-id="ffc7b-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="ffc7b-111">Quais são os requisitos de licença e os termos de uso para conectores do Graph?</span><span class="sxs-lookup"><span data-stu-id="ffc7b-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="ffc7b-112">Quais são os recursos de visualização?</span><span class="sxs-lookup"><span data-stu-id="ffc7b-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="ffc7b-113">Como faço para personalizar e configurar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="ffc7b-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="ffc7b-114">Como pesquisar meus dados de conector a partir de um aplicativo personalizado?</span><span class="sxs-lookup"><span data-stu-id="ffc7b-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> <span data-ttu-id="ffc7b-115">Os conectores do Microsoft Graph e as APIs de Pesquisa da Microsoft agora estão geralmente disponíveis.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-115">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="ffc7b-116">As primeiras versões serão para clientes configurados para lançamento direcionado.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-116">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="ffc7b-117">Se você quiser usar um conector do Graph em seu locatário, os usuários e administradores deverão optar pela [versão direcionada.](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="ffc7b-117">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true).</span></span>

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="ffc7b-118">Quais fontes de dados podem ser conectadas à Pesquisa da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="ffc7b-118">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="ffc7b-119">A Microsoft fornece 9 conectores do Graph e nossos parceiros de ecossistema criaram mais de 100 conectores do Graph.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-119">Microsoft provides 9 Graph connectors and our ecosystem partners have created over 100 more Graph connectors.</span></span> <span data-ttu-id="ffc7b-120">Você também pode criar seu próprio conector do Graph.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-120">You can also build your own Graph connector.</span></span>

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="ffc7b-121">Conectores de gráfico da Microsoft</span><span class="sxs-lookup"><span data-stu-id="ffc7b-121">Graph connectors by Microsoft</span></span>

<span data-ttu-id="ffc7b-122">Você pode se conectar às seguintes fontes de dados usando conectores do Graph criados pela Microsoft:</span><span class="sxs-lookup"><span data-stu-id="ffc7b-122">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Add links below when new docs are created--->
* [<span data-ttu-id="ffc7b-123">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="ffc7b-123">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="ffc7b-124">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="ffc7b-124">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="ffc7b-125">Azure SQL e Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="ffc7b-125">Azure SQL and Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="ffc7b-126">Sites empresariais</span><span class="sxs-lookup"><span data-stu-id="ffc7b-126">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="ffc7b-127">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="ffc7b-127">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="ffc7b-128">Compartilhamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="ffc7b-128">File share</span></span>](fileshare-connector.md)
* [<span data-ttu-id="ffc7b-129">Oracle SQL (visualização)</span><span class="sxs-lookup"><span data-stu-id="ffc7b-129">Oracle SQL (preview)</span></span>](OracleSQL-connector.md)
* [<span data-ttu-id="ffc7b-130">Salesforce (visualização)</span><span class="sxs-lookup"><span data-stu-id="ffc7b-130">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="ffc7b-131">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="ffc7b-131">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="ffc7b-132">A [galeria de conectores do Graph](connectors-gallery.md) contém uma breve descrição de cada um desses conectores do Graph.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-132">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="ffc7b-133">Se você estiver pronto para conectar uma dessas fontes de dados [](configure-connector.md) ao seu locatário, leia a visão geral da Instalação e quaisquer outros artigos na seção Conectores de Instalação da Microsoft que se apliquem à sua fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-133">If you're ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="ffc7b-134">Conectores do Graph por nossos parceiros</span><span class="sxs-lookup"><span data-stu-id="ffc7b-134">Graph connectors by our partners</span></span>

<span data-ttu-id="ffc7b-135">A [galeria de conectores](connectors-gallery.md) do Microsoft Graph inclui uma breve descrição de cada um dos conectores do Graph criados por nossos parceiros e um link para o site de cada parceiro.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-135">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief description of each of the Graph connectors created by our partners, and a link to each partner's website.</span></span> <span data-ttu-id="ffc7b-136">Para saber mais, entre em contato diretamente com cada parceiro.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-136">To learn more, contact each partner directly.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="ffc7b-137">Criar seu próprio conector do Graph</span><span class="sxs-lookup"><span data-stu-id="ffc7b-137">Build your own Graph connector</span></span>

<span data-ttu-id="ffc7b-138">Se preferir, você pode criar seu próprio conector do Graph.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-138">You can build your own Graph connector if you prefer.</span></span> <span data-ttu-id="ffc7b-139">Para obter mais informações sobre como criar conectores do Graph, consulte a [visão geral da API de Pesquisa da Microsoft no Microsoft Graph.](https://docs.microsoft.com/graph/search-concept-overview)</span><span class="sxs-lookup"><span data-stu-id="ffc7b-139">For more information on building Graph connectors, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="ffc7b-140">Como faço para gerenciar minhas conexões?</span><span class="sxs-lookup"><span data-stu-id="ffc7b-140">How do I manage my connections?</span></span>

<span data-ttu-id="ffc7b-141">Você pode gerenciar suas conexões na [guia Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) no Centro [de administração do Microsoft 365.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="ffc7b-141">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="ffc7b-142">Para obter mais informações sobre como gerenciar conexões, consulte: [Gerenciar suas conexões.](manage-connector.md)</span><span class="sxs-lookup"><span data-stu-id="ffc7b-142">For more information about managing connections, see: [Manage your connections](manage-connector.md).</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="ffc7b-143">Quais são os requisitos de licença e os termos de uso para conectores do Graph?</span><span class="sxs-lookup"><span data-stu-id="ffc7b-143">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="ffc7b-144">Você precisa de uma licença válida do Microsoft 365 ou Office 365 e cota suficiente de Conectores do Graph para que os usuários em sua organização vejam dados de conectores nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-144">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="ffc7b-145">Para saber mais, consulte [Requisitos de licença e preços](licensing.md) e Termos de [uso.](terms-of-use.md)</span><span class="sxs-lookup"><span data-stu-id="ffc7b-145">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="ffc7b-146">Quais são os recursos de visualização?</span><span class="sxs-lookup"><span data-stu-id="ffc7b-146">What are the preview features?</span></span>

<span data-ttu-id="ffc7b-147">Embora os conectores do Microsoft Graph e as APIs de Pesquisa da Microsoft agora estão geralmente disponíveis, há vários recursos que estão em visualização.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-147">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="ffc7b-148">O conjunto de conectores e recursos na visualização incluem:</span><span class="sxs-lookup"><span data-stu-id="ffc7b-148">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="ffc7b-149">Conector do Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="ffc7b-149">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="ffc7b-150">Conector salesforce</span><span class="sxs-lookup"><span data-stu-id="ffc7b-150">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="ffc7b-151">[Conector do ServiceNow](servicenow-connector.md) com permissões de pesquisa que usam ACLs de origem</span><span class="sxs-lookup"><span data-stu-id="ffc7b-151">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="ffc7b-152">Gerenciar tipos de cluster</span><span class="sxs-lookup"><span data-stu-id="ffc7b-152">Manage result cluster</span></span>](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="ffc7b-153">Como faço para personalizar e configurar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="ffc7b-153">How do I customize and configure search results?</span></span>

<span data-ttu-id="ffc7b-154">Há muitas maneiras de personalizar e configurar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-154">There are many ways to customize and configure search results.</span></span> <span data-ttu-id="ffc7b-155">Consulte os seguintes artigos para saber mais:</span><span class="sxs-lookup"><span data-stu-id="ffc7b-155">See the following articles to learn more:</span></span>

* [<span data-ttu-id="ffc7b-156">Gerenciar verticais e tipos de resultados</span><span class="sxs-lookup"><span data-stu-id="ffc7b-156">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="ffc7b-157">Gerenciar layouts de resultados de pesquisa</span><span class="sxs-lookup"><span data-stu-id="ffc7b-157">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="ffc7b-158">Gerenciar tipos de cluster</span><span class="sxs-lookup"><span data-stu-id="ffc7b-158">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="ffc7b-159">Gerenciar filtros personalizados</span><span class="sxs-lookup"><span data-stu-id="ffc7b-159">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="ffc7b-160">Como pesquisar meus dados de conector a partir de um aplicativo personalizado?</span><span class="sxs-lookup"><span data-stu-id="ffc7b-160">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="ffc7b-161">Depois que os dados personalizados são indexados, os [desenvolvedores podem consultar esses dados.](https://docs.microsoft.com/graph/search-concept-custom-types)</span><span class="sxs-lookup"><span data-stu-id="ffc7b-161">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="ffc7b-162">Você pode exibir seus dados em qualquer aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-162">You can view your data in any application.</span></span> <span data-ttu-id="ffc7b-163">Para obter mais informações, consulte a [visão geral da API de Pesquisa da Microsoft no Microsoft Graph.](https://docs.microsoft.com/graph/search-concept-overview)</span><span class="sxs-lookup"><span data-stu-id="ffc7b-163">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ffc7b-164">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="ffc7b-164">Next steps</span></span>

<span data-ttu-id="ffc7b-165">Certifique-se de personalizar os resultados da pesquisa conforme recomendado neste artigo [Como personalizar e configurar os resultados da pesquisa?](#how-do-i-customize-and-configure-search-results).</span><span class="sxs-lookup"><span data-stu-id="ffc7b-165">Make sure you customize the search results as recommended in this article [How do I customize and configure search results?](#how-do-i-customize-and-configure-search-results).</span></span> <span data-ttu-id="ffc7b-166">Para saber mais sobre como personalizar os resultados da pesquisa, consulte [Personalizar a página de resultados da pesquisa.](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page)</span><span class="sxs-lookup"><span data-stu-id="ffc7b-166">To learn more about customizing search results, see [Customize the search results page](https://docs.microsoft.com/microsoftsearch/configure-connector#next-steps-customize-the-search-results-page).</span></span>

## <a name="limitations"></a><span data-ttu-id="ffc7b-167">Limitações</span><span class="sxs-lookup"><span data-stu-id="ffc7b-167">Limitations</span></span>

* <span data-ttu-id="ffc7b-168">Quando você **publica** um conector criado pela Microsoft, pode levar alguns minutos para que a conexão seja criada.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-168">When you **publish** a Microsoft-built connector, it might take a few minutes for the connection to be created.</span></span> <span data-ttu-id="ffc7b-169">Durante esse tempo, a conexão mostrará seu status como pendente.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-169">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="ffc7b-170">O Centro de administração do [Microsoft 365](https://admin.microsoft.com) não dá suporte à edição do esquema **de pesquisa** após a publicação de uma conexão.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-170">The [Microsoft 365 admin center](https://admin.microsoft.com) doesn't support editing the **search schema** after a connection is published.</span></span> <span data-ttu-id="ffc7b-171">Para editar o esquema de pesquisa, exclua sua conexão e crie um novo.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-171">To edit the search schema, delete your connection and then create a new one.</span></span>

* <span data-ttu-id="ffc7b-172">A produtividade da ingestão é acelerada em cerca de quatro itens por segundo.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-172">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="ffc7b-173">Não há suporte para atualizações de esquema.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-173">There is no support for schema updates.</span></span> <span data-ttu-id="ffc7b-174">Depois de criar uma configuração de conexão, não há como atualizar o esquema.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-174">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="ffc7b-175">Você só pode excluir e criar a conexão.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-175">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="ffc7b-176">Há um limite de conexões.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-176">There is a connections limit.</span></span> <span data-ttu-id="ffc7b-177">Cada locatário pode criar até 10 conexões.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-177">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="ffc7b-178">O suporte de edição para conexão não está disponível.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-178">Edit support for connection is not available.</span></span> <span data-ttu-id="ffc7b-179">Depois que a conexão tiver sido criada, você não poderá editá-la ou alterá-la.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-179">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="ffc7b-180">Se precisar alterar algum detalhe, você deve excluir e recriar a conexão.</span><span class="sxs-lookup"><span data-stu-id="ffc7b-180">If you need to change any details, you must delete and recreate the connection.</span></span>
