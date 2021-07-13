---
title: Visão geral Graph conectores da Microsoft
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
description: Visão geral dos conectores Graph microsoft para Pesquisa da Microsoft
ms.openlocfilehash: 87645e32e274eb166d6ba008c4ac720667105a1f
ms.sourcegitcommit: 52129e0129a201ec056903b2461d012fda6d3636
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2021
ms.locfileid: "53383479"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="676ac-103">Visão geral dos conectores do Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="676ac-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="676ac-104">[Pesquisa da Microsoft](./overview-microsoft-search.md) indexa todos os dados [Microsoft 365](https://www.microsoft.com/microsoft-365) para torná-los pesquisáveis para usuários.</span><span class="sxs-lookup"><span data-stu-id="676ac-104">[Microsoft Search](./overview-microsoft-search.md) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="676ac-105">Com os conectores Graph Microsoft, sua organização pode indexar dados de terceiros para que apareçam em Pesquisa da Microsoft resultados.</span><span class="sxs-lookup"><span data-stu-id="676ac-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="676ac-106">Esse recurso expande os tipos de fontes de conteúdo que podem ser pesquisadas nos aplicativos de produtividade do Microsoft 365 e no ecossistema da Microsoft mais amplo.</span><span class="sxs-lookup"><span data-stu-id="676ac-106">This feature expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="676ac-107">Os dados de terceiros podem ser hospedados no local ou nas nuvens públicas ou privadas.</span><span class="sxs-lookup"><span data-stu-id="676ac-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="676ac-108">Este artigo destina-se a ajudar Microsoft 365 os administradores localizarem os recursos disponíveis para responder às seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="676ac-108">This article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="676ac-109">Quais fontes de dados podem ser conectadas Pesquisa da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="676ac-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="676ac-110">Como faço para gerenciar minhas conexões?</span><span class="sxs-lookup"><span data-stu-id="676ac-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="676ac-111">Quais são os requisitos de licença e os termos de uso para conectores Graph Microsoft?</span><span class="sxs-lookup"><span data-stu-id="676ac-111">What are the license requirements and terms of use for Microsoft Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-connectors)
* [<span data-ttu-id="676ac-112">Quais são os recursos de visualização?</span><span class="sxs-lookup"><span data-stu-id="676ac-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="676ac-113">Como personalizar e configurar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="676ac-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="676ac-114">Como faço para pesquisar dados do meu conector de um aplicativo personalizado?</span><span class="sxs-lookup"><span data-stu-id="676ac-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)
* [<span data-ttu-id="676ac-115">Como personalizar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="676ac-115">How do I customize search results?</span></span>](#how-do-i-customize-search-results)
* [<span data-ttu-id="676ac-116">Quais são as limitações do conector</span><span class="sxs-lookup"><span data-stu-id="676ac-116">What are the connector limitations</span></span>](#what-are-the-connector-limitations)

<!---Add Value, scenario, example, and/or graphic in December updates--->
<!---Probably remove architecture section below
## Architecture

The following architectural diagram of the Microsoft Graph platform shows how Graph connector content flows through content indexing to user results in [Microsoft Search](./overview-microsoft-search.md) clients. The rest of this section explains each of the key building blocks in the diagram.

![Diagram: on-premises and cloud-based data is pulled by connectors and indexed by the Microsoft Search API, and then the Microsoft Search service delivers the results to users.](media/connectors-overview/highlevel-connectors.png)
Graph connectors can pull data from cloud-based (SaaS) data sources and on-premises data stores. The above diagram shows connections to only two data sources, but you can add connections to up ten sources per tenant.

The Microsoft Graph Connectors API instantiates one connection per data source. Then, the API indexes and stores the data. Established connections interact with Microsoft Search, so users can get search results.

You can use the Microsoft 365 [admin center](https://admin.microsoft.com) to setup and manage any of the Graph connectors by Microsoft. The admin center has a simple user interface that makes it easy to establish the connection to your data source, and monitor connection status and utilization.

***Edit paragraph below***
To create a **connection** to a data source, admins need authenticated access to the data and the entire content repository. The data is fed to the graph connector service for indexing.--->

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="676ac-117">Quais fontes de dados podem ser conectadas Pesquisa da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="676ac-117">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="676ac-118">A Microsoft fornece 9 conectores e nossos parceiros de ecossistema criaram mais de 100 conectores.</span><span class="sxs-lookup"><span data-stu-id="676ac-118">Microsoft provides 9 connectors and our ecosystem partners have created over 100 more connectors.</span></span> <span data-ttu-id="676ac-119">Você também pode criar seu próprio conector.</span><span class="sxs-lookup"><span data-stu-id="676ac-119">You can also build your own connector.</span></span>

### <a name="microsoft-graph-connectors-by-microsoft"></a><span data-ttu-id="676ac-120">Microsoft Graph conectores da Microsoft</span><span class="sxs-lookup"><span data-stu-id="676ac-120">Microsoft Graph connectors by Microsoft</span></span>

<span data-ttu-id="676ac-121">Você pode se conectar às seguintes fontes de dados usando conectores criados pela Microsoft:</span><span class="sxs-lookup"><span data-stu-id="676ac-121">You can connect to the following data sources using connectors created by Microsoft:</span></span>

<!---Add links below when new docs are created--->
* [<span data-ttu-id="676ac-122">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="676ac-122">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="676ac-123">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="676ac-123">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="676ac-124">Azure SQL e Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="676ac-124">Azure SQL and Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="676ac-125">Sites empresariais</span><span class="sxs-lookup"><span data-stu-id="676ac-125">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="676ac-126">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="676ac-126">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="676ac-127">Compartilhamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="676ac-127">File share</span></span>](fileshare-connector.md)
* [<span data-ttu-id="676ac-128">Oracle SQL</span><span class="sxs-lookup"><span data-stu-id="676ac-128">Oracle SQL</span></span>](OracleSQL-connector.md)
* [<span data-ttu-id="676ac-129">Salesforce (visualização)</span><span class="sxs-lookup"><span data-stu-id="676ac-129">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="676ac-130">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="676ac-130">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="676ac-131">A [galeria Graph conectores da Microsoft](https://www.microsoft.com/microsoft-search/connectors) contém uma breve descrição de cada um desses conectores.</span><span class="sxs-lookup"><span data-stu-id="676ac-131">The [Microsoft Graph connectors gallery](https://www.microsoft.com/microsoft-search/connectors) contains a brief description of each of these connectors.</span></span> <span data-ttu-id="676ac-132">Se você estiver pronto para conectar uma dessas fontes de dados [](configure-connector.md) ao seu locatário, leia a visão geral da Instalação e quaisquer outros artigos na seção Conectores de Instalação da Microsoft que se apliquem à sua fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="676ac-132">If you're ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="microsoft-graph-connectors-by-our-partners"></a><span data-ttu-id="676ac-133">Microsoft Graph conectores por nossos parceiros</span><span class="sxs-lookup"><span data-stu-id="676ac-133">Microsoft Graph connectors by our partners</span></span>

<span data-ttu-id="676ac-134">A [galeria Graph](https://www.microsoft.com/microsoft-search/connectors) conectores da Microsoft inclui uma breve descrição de cada um dos conectores criados por nossos parceiros e um link para o site de cada parceiro.</span><span class="sxs-lookup"><span data-stu-id="676ac-134">The [Microsoft Graph connectors gallery](https://www.microsoft.com/microsoft-search/connectors) includes a brief description of each of the connectors created by our partners, and a link to each partner's website.</span></span> <span data-ttu-id="676ac-135">Para saber mais, entre em contato diretamente com cada parceiro.</span><span class="sxs-lookup"><span data-stu-id="676ac-135">To learn more, contact each partner directly.</span></span>

### <a name="build-your-own-microsoft-graph-connector"></a><span data-ttu-id="676ac-136">Criar seu próprio conector de Graph Microsoft</span><span class="sxs-lookup"><span data-stu-id="676ac-136">Build your own Microsoft Graph connector</span></span>

<span data-ttu-id="676ac-137">Você pode criar seu próprio conector, se preferir.</span><span class="sxs-lookup"><span data-stu-id="676ac-137">You can build your own connector if you prefer.</span></span> <span data-ttu-id="676ac-138">Para obter mais informações sobre como criar conectores, consulte [Build your first custom Microsoft Graph connector](/graph/connecting-external-content-build-quickstart).</span><span class="sxs-lookup"><span data-stu-id="676ac-138">For more information on building connectors, see  [Build your first custom Microsoft Graph connector](/graph/connecting-external-content-build-quickstart).</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="676ac-139">Como faço para gerenciar minhas conexões?</span><span class="sxs-lookup"><span data-stu-id="676ac-139">How do I manage my connections?</span></span>

<span data-ttu-id="676ac-140">Você pode gerenciar suas conexões a partir [da guia Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) no [Centro de administração do Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="676ac-140">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="676ac-141">Para obter mais informações sobre como gerenciar conexões, consulte: [Gerenciar suas conexões](manage-connector.md).</span><span class="sxs-lookup"><span data-stu-id="676ac-141">For more information about managing connections, see: [Manage your connections](manage-connector.md).</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-connectors"></a><span data-ttu-id="676ac-142">Quais são os requisitos de licença e os termos de uso para conectores?</span><span class="sxs-lookup"><span data-stu-id="676ac-142">What are the license requirements and terms of use for connectors?</span></span>

<span data-ttu-id="676ac-143">Você precisa de uma licença Microsoft 365 ou Office 365 e cota de conectores suficientes para que os usuários em sua organização exibirem dados de conectores em seus resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="676ac-143">You need a valid Microsoft 365 or Office 365 license and sufficient connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="676ac-144">Para saber mais, confira [Requisitos de licença e preços](licensing.md) e Termos de [uso.](terms-of-use.md)</span><span class="sxs-lookup"><span data-stu-id="676ac-144">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="676ac-145">Quais são os recursos de visualização?</span><span class="sxs-lookup"><span data-stu-id="676ac-145">What are the preview features?</span></span>

<span data-ttu-id="676ac-146">Embora os Graph da Microsoft e as APIs Pesquisa da Microsoft agora estão geralmente disponíveis, há vários recursos que estão na visualização.</span><span class="sxs-lookup"><span data-stu-id="676ac-146">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="676ac-147">O conjunto de conectores e recursos na visualização inclui:</span><span class="sxs-lookup"><span data-stu-id="676ac-147">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="676ac-148">Azure DevOps conector</span><span class="sxs-lookup"><span data-stu-id="676ac-148">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="676ac-149">Conector do Salesforce</span><span class="sxs-lookup"><span data-stu-id="676ac-149">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="676ac-150">[Conector ServiceNow](servicenow-connector.md) com permissões de pesquisa que usam ACLs de origem</span><span class="sxs-lookup"><span data-stu-id="676ac-150">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="676ac-151">Gerenciar tipos de cluster</span><span class="sxs-lookup"><span data-stu-id="676ac-151">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="676ac-152">Várias conexões em um vertical</span><span class="sxs-lookup"><span data-stu-id="676ac-152">Multiple connections in a vertical</span></span>](customize-search-page.md#multiple-connections-in-a-vertical)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="676ac-153">Como personalizar e configurar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="676ac-153">How do I customize and configure search results?</span></span>

<span data-ttu-id="676ac-154">Há muitas maneiras de personalizar e configurar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="676ac-154">There are many ways to customize and configure search results.</span></span> <span data-ttu-id="676ac-155">Confira os seguintes artigos para saber mais:</span><span class="sxs-lookup"><span data-stu-id="676ac-155">See the following articles to learn more:</span></span>

* [<span data-ttu-id="676ac-156">Gerenciar verticais e tipos de resultados</span><span class="sxs-lookup"><span data-stu-id="676ac-156">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="676ac-157">Gerenciar layouts de resultados de pesquisa</span><span class="sxs-lookup"><span data-stu-id="676ac-157">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="676ac-158">Gerenciar tipos de cluster</span><span class="sxs-lookup"><span data-stu-id="676ac-158">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="676ac-159">Gerenciar filtros personalizados</span><span class="sxs-lookup"><span data-stu-id="676ac-159">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="676ac-160">Como faço para pesquisar dados do meu conector de um aplicativo personalizado?</span><span class="sxs-lookup"><span data-stu-id="676ac-160">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="676ac-161">Depois que os dados personalizados são indexados, os [desenvolvedores podem consultar esses dados.](/graph/search-concept-custom-types)</span><span class="sxs-lookup"><span data-stu-id="676ac-161">After custom data is indexed, developers can [query this data](/graph/search-concept-custom-types).</span></span> <span data-ttu-id="676ac-162">Você pode exibir seus dados em qualquer aplicativo.</span><span class="sxs-lookup"><span data-stu-id="676ac-162">You can view your data in any application.</span></span> <span data-ttu-id="676ac-163">Para obter mais informações, consulte [Overview of the Pesquisa da Microsoft API in Microsoft Graph](/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="676ac-163">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](/graph/search-concept-overview).</span></span>

## <a name="how-do-i-customize-search-results"></a><span data-ttu-id="676ac-164">Como personalizar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="676ac-164">How do I customize search results?</span></span>

<span data-ttu-id="676ac-165">A próxima etapa é personalizar os resultados da pesquisa conforme recomendado neste artigo Como personalizar e configurar os resultados [da pesquisa?](#how-do-i-customize-and-configure-search-results).</span><span class="sxs-lookup"><span data-stu-id="676ac-165">The next step is to customize the search results as recommended in this article [How do I customize and configure search results?](#how-do-i-customize-and-configure-search-results).</span></span> <span data-ttu-id="676ac-166">Para saber mais sobre como personalizar os resultados da pesquisa, consulte [Personalizar a página de resultados da pesquisa.](customize-search-page.md)</span><span class="sxs-lookup"><span data-stu-id="676ac-166">To learn more about customizing search results, see [Customize the search results page](customize-search-page.md).</span></span>

## <a name="what-are-the-connector-limitations"></a><span data-ttu-id="676ac-167">Quais são as limitações do conector?</span><span class="sxs-lookup"><span data-stu-id="676ac-167">What are the connector limitations?</span></span>

* <span data-ttu-id="676ac-168">Quando você **publica** um conector criado pela Microsoft, pode levar alguns minutos para que a conexão seja criada.</span><span class="sxs-lookup"><span data-stu-id="676ac-168">When you **publish** a Microsoft-built connector, it can take a few minutes for the connection to be created.</span></span> <span data-ttu-id="676ac-169">Durante esse tempo, a conexão mostrará seu status como pendente.</span><span class="sxs-lookup"><span data-stu-id="676ac-169">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="676ac-170">A produtividade de ingestão é acelerada em aproximadamente quatro itens por segundo.</span><span class="sxs-lookup"><span data-stu-id="676ac-170">Ingestion throughput is throttled at approximately four items per second.</span></span>

* <span data-ttu-id="676ac-171">Não há suporte para atualizações de esquema.</span><span class="sxs-lookup"><span data-stu-id="676ac-171">There is no support for schema updates.</span></span> <span data-ttu-id="676ac-172">Depois de criar uma configuração de conexão, não há como atualizar o esquema.</span><span class="sxs-lookup"><span data-stu-id="676ac-172">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="676ac-173">Você só pode excluir e re-criar a conexão.</span><span class="sxs-lookup"><span data-stu-id="676ac-173">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="676ac-174">Há um limite de conexão.</span><span class="sxs-lookup"><span data-stu-id="676ac-174">There is a connection limit.</span></span> <span data-ttu-id="676ac-175">Cada locatário pode criar até 10 conexões.</span><span class="sxs-lookup"><span data-stu-id="676ac-175">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="676ac-176">Não é possível editar ou alterar uma conexão depois que ela tiver sido criada.</span><span class="sxs-lookup"><span data-stu-id="676ac-176">You cannot edit or change a connection after it has been created.</span></span> <span data-ttu-id="676ac-177">Se precisar alterar qualquer detalhe, exclua e recrie a conexão.</span><span class="sxs-lookup"><span data-stu-id="676ac-177">If you need to change any details, you must delete and recreate the connection.</span></span>
