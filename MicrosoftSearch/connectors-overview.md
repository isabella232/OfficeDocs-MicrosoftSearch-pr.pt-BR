---
title: Visão geral dos conectores
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Visão geral dos conectores do Microsoft Graph para o Microsoft Search
ms.openlocfilehash: 7388653927ca6a7af0ba64c3c592f2689780c181
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367519"
---
# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="513e9-103">Visão geral dos conectores do Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="513e9-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="513e9-104">O [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexa todos os seus dados do [Microsoft 365](https://www.microsoft.com/microsoft-365) para torná-los pesquisáveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="513e9-104">[Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="513e9-105">Com os conectores do Microsoft Graph, sua organização pode indexar dados de terceiros para que apareçam nos resultados da pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="513e9-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="513e9-106">Isso expande os tipos de fontes de conteúdo que podem ser pesquisadas nos seus aplicativos de produtividade do Microsoft 365 e no ecossistema mais amplo da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="513e9-106">This expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="513e9-107">Os dados de terceiros podem ser hospedados no local ou nas nuvens públicas ou privadas.</span><span class="sxs-lookup"><span data-stu-id="513e9-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="513e9-108">O restante deste artigo destina-se a ajudar os administradores da Microsoft 365 a localizar os recursos que estão disponível para responder às seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="513e9-108">The rest of this article is intended to help Microsoft 365 administrators locate the resources that are avaiable to answer the following questions:</span></span>

* [<span data-ttu-id="513e9-109">Quais fontes de dados podem ser conectadas à pesquisa da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="513e9-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="513e9-110">Como gerenciar minhas conexões?</span><span class="sxs-lookup"><span data-stu-id="513e9-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="513e9-111">Quais são os requisitos de licença e os termos de uso para conectores do Graph?</span><span class="sxs-lookup"><span data-stu-id="513e9-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="513e9-112">Como personalizar e configurar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="513e9-112">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="513e9-113">Como pesquisar dados do meu conector de um aplicativo personalizado?</span><span class="sxs-lookup"><span data-stu-id="513e9-113">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)

<!---Modify to another note that is more accurate--->
> [!IMPORTANT]
> <span data-ttu-id="513e9-114">Agora, os conectores do Microsoft Graph e as APIs de pesquisa da Microsoft estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="513e9-114">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="513e9-115">As primeiras distribuições serão para os clientes configurados para lançamento direcionado.</span><span class="sxs-lookup"><span data-stu-id="513e9-115">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="513e9-116">Se você quiser usar um conector de gráfico em seu locatário, os usuários e os administradores deverão optar pelo [lançamento direcionado](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="513e9-116">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](https://docs.microsoft.com/microsoftsearch/overview-microsoft-search) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below**_
To create a _*connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="513e9-117">Quais fontes de dados podem ser conectadas à pesquisa da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="513e9-117">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="513e9-118">A Microsoft fornece dez conectores de gráfico e nossos parceiros de ecossistema criaram mais de 100 conectores de gráficos adicionais.</span><span class="sxs-lookup"><span data-stu-id="513e9-118">Microsoft provides ten Graph connectors and our ecosystem partners have created over 100 additional Graph connectors.</span></span> <span data-ttu-id="513e9-119">Você também pode criar seu próprio conector de Graph.</span><span class="sxs-lookup"><span data-stu-id="513e9-119">You can also build your own Graph connector.</span></span> 

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="513e9-120">Conectores do Graph pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="513e9-120">Graph connectors by Microsoft</span></span>

<span data-ttu-id="513e9-121">Você pode se conectar às fontes de dados a seguir usando os conectores do Graph criados pela Microsoft:</span><span class="sxs-lookup"><span data-stu-id="513e9-121">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Need to add a few links below when docs exist--->
* [<span data-ttu-id="513e9-122">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="513e9-122">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="513e9-123">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="513e9-123">Azure DevOps</span></span>](azure-devops-connector.md)
* <span data-ttu-id="513e9-124">Azure SQL</span><span class="sxs-lookup"><span data-stu-id="513e9-124">Azure SQL</span></span>
* [<span data-ttu-id="513e9-125">Sites empresariais</span><span class="sxs-lookup"><span data-stu-id="513e9-125">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="513e9-126">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="513e9-126">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="513e9-127">Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="513e9-127">Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="513e9-128">Compartilhamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="513e9-128">File share</span></span>](fileshare-connector.md)
* <span data-ttu-id="513e9-129">Oracle (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="513e9-129">Oracle (preview)</span></span>
* [<span data-ttu-id="513e9-130">Salesforce (visualização)</span><span class="sxs-lookup"><span data-stu-id="513e9-130">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="513e9-131">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="513e9-131">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="513e9-132">A [Galeria de conectores do Graph](connectors-gallery.md) contém uma breve descrição de cada um desses conectores gráficos.</span><span class="sxs-lookup"><span data-stu-id="513e9-132">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="513e9-133">Se você estiver pronto para conectar uma dessas fontes de dados ao seu locatário, leia a [visão geral da instalação](configure-connector.md) e outros artigos na seção conectores de instalação pela Microsoft que se aplicam à sua fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="513e9-133">If you are ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="513e9-134">Conectores do Graph por nossos parceiros</span><span class="sxs-lookup"><span data-stu-id="513e9-134">Graph connectors by our partners</span></span>

<span data-ttu-id="513e9-135">A [Galeria de conectores do Microsoft Graph](connectors-gallery.md) inclui uma breve descrição de cada um dos conectores de gráficos criados por nossos parceiros e um link para o site de cada parceiro.</span><span class="sxs-lookup"><span data-stu-id="513e9-135">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief descriptions of each of the Graph connectors created by our partners and a link to each partner's website.</span></span> <span data-ttu-id="513e9-136">Entre em contato diretamente com cada parceiro para saber mais.</span><span class="sxs-lookup"><span data-stu-id="513e9-136">Contact each partner directly to learn more.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="513e9-137">Criar seu próprio conector de gráfico</span><span class="sxs-lookup"><span data-stu-id="513e9-137">Build your own Graph connector</span></span>

<span data-ttu-id="513e9-138">Se você planeja Compilar seu próprio conector de gráfico, confira a [visão geral da API de pesquisa da Microsoft no Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="513e9-138">If you plan to build your own Graph connector, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview) for more information.</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="513e9-139">Como gerenciar minhas conexões?</span><span class="sxs-lookup"><span data-stu-id="513e9-139">How do I manage my connections?</span></span>

<span data-ttu-id="513e9-140">Você pode gerenciar suas conexões na [guia conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) do [centro de administração do Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="513e9-140">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="513e9-141">Confira [gerenciar suas conexões](manage-connector.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="513e9-141">See [Manage your connections](manage-connector.md) for more information.</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="513e9-142">Quais são os requisitos de licença e os termos de uso para conectores do Graph?</span><span class="sxs-lookup"><span data-stu-id="513e9-142">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="513e9-143">Você precisa de uma licença válida do Microsoft 365 ou do Office 365 e uma cota de conectores de gráfico suficiente para que os usuários em sua organização exibam dados de conectores em seus resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="513e9-143">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="513e9-144">Para saber mais, veja [requisitos de licença e preços](licensing.md) e [termos de uso](terms-of-use.md).</span><span class="sxs-lookup"><span data-stu-id="513e9-144">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="513e9-145">Como personalizar e configurar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="513e9-145">How do I customize and configure search results?</span></span>

<span data-ttu-id="513e9-146">Há várias maneiras de personalizar e configurar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="513e9-146">There are a number of ways to customize and configure search results.</span></span> <span data-ttu-id="513e9-147">Consulte os seguintes artigos para saber mais:</span><span class="sxs-lookup"><span data-stu-id="513e9-147">See the following articles to learn more:</span></span>

* [<span data-ttu-id="513e9-148">Gerenciar verticais e tipos de resultados</span><span class="sxs-lookup"><span data-stu-id="513e9-148">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="513e9-149">Gerenciar layouts de resultados de pesquisa</span><span class="sxs-lookup"><span data-stu-id="513e9-149">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="513e9-150">Gerenciar o cluster de resultados</span><span class="sxs-lookup"><span data-stu-id="513e9-150">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="513e9-151">Gerenciar filtros personalizados</span><span class="sxs-lookup"><span data-stu-id="513e9-151">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="513e9-152">Como pesquisar dados do meu conector de um aplicativo personalizado?</span><span class="sxs-lookup"><span data-stu-id="513e9-152">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="513e9-153">Após a indexação dos dados personalizados, os desenvolvedores podem [consultar esses dados](https://docs.microsoft.com/graph/search-concept-custom-types).</span><span class="sxs-lookup"><span data-stu-id="513e9-153">After custom data is indexed, developers can [query this data](https://docs.microsoft.com/graph/search-concept-custom-types).</span></span> <span data-ttu-id="513e9-154">Você pode exibir seus dados em qualquer aplicativo.</span><span class="sxs-lookup"><span data-stu-id="513e9-154">You can view your data in any application.</span></span> <span data-ttu-id="513e9-155">Para obter mais informações, consulte a [visão geral da API de pesquisa da Microsoft no Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="513e9-155">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](https://docs.microsoft.com/graph/search-concept-overview).</span></span>
