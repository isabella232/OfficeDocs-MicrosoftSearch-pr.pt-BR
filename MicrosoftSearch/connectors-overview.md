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
ms.openlocfilehash: 4bcfb871fabae07270611762d2112a6e72d4762b
ms.sourcegitcommit: 93fc70f0073ab45b4dbd702441ac2fc07a7668bc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2021
ms.locfileid: "53230885"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="3901c-103">Visão geral dos conectores do Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="3901c-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="3901c-104">[Pesquisa da Microsoft](./overview-microsoft-search.md) indexa todos os dados [Microsoft 365](https://www.microsoft.com/microsoft-365) para torná-los pesquisáveis para usuários.</span><span class="sxs-lookup"><span data-stu-id="3901c-104">[Microsoft Search](./overview-microsoft-search.md) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="3901c-105">Com os conectores Graph Microsoft, sua organização pode indexar dados de terceiros para que apareçam em Pesquisa da Microsoft resultados.</span><span class="sxs-lookup"><span data-stu-id="3901c-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="3901c-106">Esse recurso expande os tipos de fontes de conteúdo que podem ser pesquisadas nos aplicativos de produtividade do Microsoft 365 e no ecossistema da Microsoft mais amplo.</span><span class="sxs-lookup"><span data-stu-id="3901c-106">This feature expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="3901c-107">Os dados de terceiros podem ser hospedados no local ou nas nuvens públicas ou privadas.</span><span class="sxs-lookup"><span data-stu-id="3901c-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="3901c-108">Este artigo destina-se a ajudar Microsoft 365 os administradores localizarem os recursos disponíveis para responder às seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="3901c-108">This article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="3901c-109">Quais fontes de dados podem ser conectadas Pesquisa da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="3901c-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="3901c-110">Como faço para gerenciar minhas conexões?</span><span class="sxs-lookup"><span data-stu-id="3901c-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="3901c-111">Quais são os requisitos de licença e os termos de uso para conectores Graph Microsoft?</span><span class="sxs-lookup"><span data-stu-id="3901c-111">What are the license requirements and terms of use for Microsoft Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-connectors)
* [<span data-ttu-id="3901c-112">Quais são os recursos de visualização?</span><span class="sxs-lookup"><span data-stu-id="3901c-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="3901c-113">Como personalizar e configurar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="3901c-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="3901c-114">Como faço para pesquisar dados do meu conector de um aplicativo personalizado?</span><span class="sxs-lookup"><span data-stu-id="3901c-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)
* [<span data-ttu-id="3901c-115">Como personalizar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="3901c-115">How do I customize search results?</span></span>](#how-do-i-customize-search-results)
* [<span data-ttu-id="3901c-116">Quais são as limitações do conector</span><span class="sxs-lookup"><span data-stu-id="3901c-116">What are the connector limitations</span></span>](#what-are-the-connector-limitations)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> <span data-ttu-id="3901c-117">Os Graph e as APIs Pesquisa da Microsoft da Microsoft agora estão geralmente disponíveis.</span><span class="sxs-lookup"><span data-stu-id="3901c-117">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="3901c-118">As primeiras versões serão para clientes configurados para lançamento direcionado.</span><span class="sxs-lookup"><span data-stu-id="3901c-118">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="3901c-119">Se você quiser usar um conector Graph no locatário, os usuários e administradores devem optar [por Versão direcionada.](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="3901c-119">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide).</span></span>

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="3901c-120">Quais fontes de dados podem ser conectadas Pesquisa da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="3901c-120">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="3901c-121">A Microsoft fornece 9 conectores e nossos parceiros de ecossistema criaram mais de 100 conectores.</span><span class="sxs-lookup"><span data-stu-id="3901c-121">Microsoft provides 9 connectors and our ecosystem partners have created over 100 more connectors.</span></span> <span data-ttu-id="3901c-122">Você também pode criar seu próprio conector.</span><span class="sxs-lookup"><span data-stu-id="3901c-122">You can also build your own connector.</span></span>

### <a name="microsoft-graph-connectors-by-microsoft"></a><span data-ttu-id="3901c-123">Microsoft Graph conectores da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3901c-123">Microsoft Graph connectors by Microsoft</span></span>

<span data-ttu-id="3901c-124">Você pode se conectar às seguintes fontes de dados usando conectores criados pela Microsoft:</span><span class="sxs-lookup"><span data-stu-id="3901c-124">You can connect to the following data sources using connectors created by Microsoft:</span></span>

<!---Add links below when new docs are created--->
* [<span data-ttu-id="3901c-125">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="3901c-125">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="3901c-126">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="3901c-126">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="3901c-127">Azure SQL e Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="3901c-127">Azure SQL and Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="3901c-128">Sites empresariais</span><span class="sxs-lookup"><span data-stu-id="3901c-128">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="3901c-129">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="3901c-129">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="3901c-130">Compartilhamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="3901c-130">File share</span></span>](fileshare-connector.md)
* [<span data-ttu-id="3901c-131">Oracle SQL</span><span class="sxs-lookup"><span data-stu-id="3901c-131">Oracle SQL</span></span>](OracleSQL-connector.md)
* [<span data-ttu-id="3901c-132">Salesforce (visualização)</span><span class="sxs-lookup"><span data-stu-id="3901c-132">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="3901c-133">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="3901c-133">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="3901c-134">A [galeria Graph conectores da Microsoft](https://www.microsoft.com/microsoft-search/connectors) contém uma breve descrição de cada um desses conectores.</span><span class="sxs-lookup"><span data-stu-id="3901c-134">The [Microsoft Graph connectors gallery](https://www.microsoft.com/microsoft-search/connectors) contains a brief description of each of these connectors.</span></span> <span data-ttu-id="3901c-135">Se você estiver pronto para conectar uma dessas fontes de dados [](configure-connector.md) ao seu locatário, leia a visão geral da Instalação e quaisquer outros artigos na seção Conectores de Instalação da Microsoft que se apliquem à sua fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="3901c-135">If you're ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="microsoft-graph-connectors-by-our-partners"></a><span data-ttu-id="3901c-136">Microsoft Graph conectores por nossos parceiros</span><span class="sxs-lookup"><span data-stu-id="3901c-136">Microsoft Graph connectors by our partners</span></span>

<span data-ttu-id="3901c-137">A [galeria Graph](https://www.microsoft.com/microsoft-search/connectors) conectores da Microsoft inclui uma breve descrição de cada um dos conectores criados por nossos parceiros e um link para o site de cada parceiro.</span><span class="sxs-lookup"><span data-stu-id="3901c-137">The [Microsoft Graph connectors gallery](https://www.microsoft.com/microsoft-search/connectors) includes a brief description of each of the connectors created by our partners, and a link to each partner's website.</span></span> <span data-ttu-id="3901c-138">Para saber mais, entre em contato diretamente com cada parceiro.</span><span class="sxs-lookup"><span data-stu-id="3901c-138">To learn more, contact each partner directly.</span></span>

### <a name="build-your-own-microsoft-graph-connector"></a><span data-ttu-id="3901c-139">Criar seu próprio conector de Graph Microsoft</span><span class="sxs-lookup"><span data-stu-id="3901c-139">Build your own Microsoft Graph connector</span></span>

<span data-ttu-id="3901c-140">Você pode criar seu próprio conector, se preferir.</span><span class="sxs-lookup"><span data-stu-id="3901c-140">You can build your own connector if you prefer.</span></span> <span data-ttu-id="3901c-141">Para obter mais informações sobre como criar conectores, consulte [Build your first custom Microsoft Graph connector](/graph/connecting-external-content-build-quickstart).</span><span class="sxs-lookup"><span data-stu-id="3901c-141">For more information on building connectors, see  [Build your first custom Microsoft Graph connector](/graph/connecting-external-content-build-quickstart).</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="3901c-142">Como faço para gerenciar minhas conexões?</span><span class="sxs-lookup"><span data-stu-id="3901c-142">How do I manage my connections?</span></span>

<span data-ttu-id="3901c-143">Você pode gerenciar suas conexões a partir [da guia Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) no [Centro de administração do Microsoft 365](https://admin.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="3901c-143">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="3901c-144">Para obter mais informações sobre como gerenciar conexões, consulte: [Gerenciar suas conexões](manage-connector.md).</span><span class="sxs-lookup"><span data-stu-id="3901c-144">For more information about managing connections, see: [Manage your connections](manage-connector.md).</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-connectors"></a><span data-ttu-id="3901c-145">Quais são os requisitos de licença e os termos de uso para conectores?</span><span class="sxs-lookup"><span data-stu-id="3901c-145">What are the license requirements and terms of use for connectors?</span></span>

<span data-ttu-id="3901c-146">Você precisa de uma licença Microsoft 365 ou Office 365 e cota de conectores suficientes para que os usuários em sua organização exibirem dados de conectores em seus resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3901c-146">You need a valid Microsoft 365 or Office 365 license and sufficient connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="3901c-147">Para saber mais, confira [Requisitos de licença e preços](licensing.md) e Termos de [uso.](terms-of-use.md)</span><span class="sxs-lookup"><span data-stu-id="3901c-147">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="3901c-148">Quais são os recursos de visualização?</span><span class="sxs-lookup"><span data-stu-id="3901c-148">What are the preview features?</span></span>

<span data-ttu-id="3901c-149">Embora os Graph da Microsoft e as APIs Pesquisa da Microsoft agora estão geralmente disponíveis, há vários recursos que estão na visualização.</span><span class="sxs-lookup"><span data-stu-id="3901c-149">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="3901c-150">O conjunto de conectores e recursos na visualização inclui:</span><span class="sxs-lookup"><span data-stu-id="3901c-150">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="3901c-151">Azure DevOps conector</span><span class="sxs-lookup"><span data-stu-id="3901c-151">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="3901c-152">Conector do Salesforce</span><span class="sxs-lookup"><span data-stu-id="3901c-152">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="3901c-153">[Conector ServiceNow](servicenow-connector.md) com permissões de pesquisa que usam ACLs de origem</span><span class="sxs-lookup"><span data-stu-id="3901c-153">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="3901c-154">Gerenciar tipos de cluster</span><span class="sxs-lookup"><span data-stu-id="3901c-154">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="3901c-155">Várias conexões em um vertical</span><span class="sxs-lookup"><span data-stu-id="3901c-155">Multiple connections in a vertical</span></span>](customize-search-page.md#multiple-connections-in-a-vertical)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="3901c-156">Como personalizar e configurar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="3901c-156">How do I customize and configure search results?</span></span>

<span data-ttu-id="3901c-157">Há muitas maneiras de personalizar e configurar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3901c-157">There are many ways to customize and configure search results.</span></span> <span data-ttu-id="3901c-158">Confira os seguintes artigos para saber mais:</span><span class="sxs-lookup"><span data-stu-id="3901c-158">See the following articles to learn more:</span></span>

* [<span data-ttu-id="3901c-159">Gerenciar verticais e tipos de resultados</span><span class="sxs-lookup"><span data-stu-id="3901c-159">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="3901c-160">Gerenciar layouts de resultados de pesquisa</span><span class="sxs-lookup"><span data-stu-id="3901c-160">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="3901c-161">Gerenciar tipos de cluster</span><span class="sxs-lookup"><span data-stu-id="3901c-161">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="3901c-162">Gerenciar filtros personalizados</span><span class="sxs-lookup"><span data-stu-id="3901c-162">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="3901c-163">Como faço para pesquisar dados do meu conector de um aplicativo personalizado?</span><span class="sxs-lookup"><span data-stu-id="3901c-163">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="3901c-164">Depois que os dados personalizados são indexados, os [desenvolvedores podem consultar esses dados.](/graph/search-concept-custom-types)</span><span class="sxs-lookup"><span data-stu-id="3901c-164">After custom data is indexed, developers can [query this data](/graph/search-concept-custom-types).</span></span> <span data-ttu-id="3901c-165">Você pode exibir seus dados em qualquer aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3901c-165">You can view your data in any application.</span></span> <span data-ttu-id="3901c-166">Para obter mais informações, consulte [Overview of the Pesquisa da Microsoft API in Microsoft Graph](/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="3901c-166">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](/graph/search-concept-overview).</span></span>

## <a name="how-do-i-customize-search-results"></a><span data-ttu-id="3901c-167">Como personalizar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="3901c-167">How do I customize search results?</span></span>

<span data-ttu-id="3901c-168">A próxima etapa é personalizar os resultados da pesquisa conforme recomendado neste artigo Como personalizar e configurar os resultados [da pesquisa?](#how-do-i-customize-and-configure-search-results).</span><span class="sxs-lookup"><span data-stu-id="3901c-168">The next step is to customize the search results as recommended in this article [How do I customize and configure search results?](#how-do-i-customize-and-configure-search-results).</span></span> <span data-ttu-id="3901c-169">Para saber mais sobre como personalizar os resultados da pesquisa, consulte [Personalizar a página de resultados da pesquisa.](customize-search-page.md)</span><span class="sxs-lookup"><span data-stu-id="3901c-169">To learn more about customizing search results, see [Customize the search results page](customize-search-page.md).</span></span>

## <a name="what-are-the-connector-limitations"></a><span data-ttu-id="3901c-170">Quais são as limitações do conector?</span><span class="sxs-lookup"><span data-stu-id="3901c-170">What are the connector limitations?</span></span>

* <span data-ttu-id="3901c-171">Quando você **publica** um conector criado pela Microsoft, pode levar alguns minutos para que a conexão seja criada.</span><span class="sxs-lookup"><span data-stu-id="3901c-171">When you **publish** a Microsoft-built connector, it can take a few minutes for the connection to be created.</span></span> <span data-ttu-id="3901c-172">Durante esse tempo, a conexão mostrará seu status como pendente.</span><span class="sxs-lookup"><span data-stu-id="3901c-172">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="3901c-173">A produtividade de ingestão é acelerada em aproximadamente quatro itens por segundo.</span><span class="sxs-lookup"><span data-stu-id="3901c-173">Ingestion throughput is throttled at approximately four items per second.</span></span>

* <span data-ttu-id="3901c-174">Não há suporte para atualizações de esquema.</span><span class="sxs-lookup"><span data-stu-id="3901c-174">There is no support for schema updates.</span></span> <span data-ttu-id="3901c-175">Depois de criar uma configuração de conexão, não há como atualizar o esquema.</span><span class="sxs-lookup"><span data-stu-id="3901c-175">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="3901c-176">Você só pode excluir e re-criar a conexão.</span><span class="sxs-lookup"><span data-stu-id="3901c-176">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="3901c-177">Há um limite de conexão.</span><span class="sxs-lookup"><span data-stu-id="3901c-177">There is a connection limit.</span></span> <span data-ttu-id="3901c-178">Cada locatário pode criar até 10 conexões.</span><span class="sxs-lookup"><span data-stu-id="3901c-178">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="3901c-179">Não é possível editar ou alterar uma conexão depois que ela tiver sido criada.</span><span class="sxs-lookup"><span data-stu-id="3901c-179">You cannot edit or change a connection after it has been created.</span></span> <span data-ttu-id="3901c-180">Se precisar alterar qualquer detalhe, exclua e recrie a conexão.</span><span class="sxs-lookup"><span data-stu-id="3901c-180">If you need to change any details, you must delete and recreate the connection.</span></span>
