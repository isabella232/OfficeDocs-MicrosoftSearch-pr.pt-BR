---
title: Visão geral dos Conectores do Microsoft Graph
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
description: Visão geral dos conectores do Microsoft Graph para Pesquisa da Microsoft
ms.openlocfilehash: 77f145f58cf06e49f88af25bcb4d28cfa7d2bd56
ms.sourcegitcommit: 08a7086185d28df14b06d1f7fdfbb1637288f7a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51042570"
---
<!---Previous ms.author: monaray --->

# <a name="overview-of-microsoft-graph-connectors"></a><span data-ttu-id="efdf0-103">Visão geral dos conectores do Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="efdf0-103">Overview of Microsoft Graph connectors</span></span>

<span data-ttu-id="efdf0-104">[A Pesquisa da Microsoft](./overview-microsoft-search.md) indexa todos os dados do [Microsoft 365](https://www.microsoft.com/microsoft-365) para torná-los pesquisáveis para usuários.</span><span class="sxs-lookup"><span data-stu-id="efdf0-104">[Microsoft Search](./overview-microsoft-search.md) indexes all your [Microsoft 365](https://www.microsoft.com/microsoft-365) data to make it searchable for users.</span></span> <span data-ttu-id="efdf0-105">Com os conectores do Microsoft Graph, sua organização pode indexar dados de terceiros para que apareçam nos resultados da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="efdf0-105">With Microsoft Graph connectors, your organization can index third-party data so it appears in Microsoft Search results.</span></span> <span data-ttu-id="efdf0-106">Esse recurso expande os tipos de fontes de conteúdo pesquisáveis em seus aplicativos de produtividade do Microsoft 365 e no ecossistema da Microsoft mais amplo.</span><span class="sxs-lookup"><span data-stu-id="efdf0-106">This feature expands the types of content sources that are searchable in your Microsoft 365 productivity apps and the broader Microsoft ecosystem.</span></span> <span data-ttu-id="efdf0-107">Os dados de terceiros podem ser hospedados no local ou nas nuvens públicas ou privadas.</span><span class="sxs-lookup"><span data-stu-id="efdf0-107">The third-party data can be hosted on-premises or in the public or private clouds.</span></span>

<!---link Microsoft Graph reference in line 19 when we have access to relevant documentation--->

<span data-ttu-id="efdf0-108">Este artigo destina-se a ajudar os administradores do Microsoft 365 a localizar os recursos disponíveis para responder às seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="efdf0-108">This article is intended to help Microsoft 365 administrators locate the resources that are available to answer the following questions:</span></span>

* [<span data-ttu-id="efdf0-109">Quais fontes de dados podem ser conectadas à Pesquisa da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="efdf0-109">What data sources can be connected to Microsoft Search?</span></span>](#what-data-sources-can-be-connected-to-microsoft-search)
* [<span data-ttu-id="efdf0-110">Como faço para gerenciar minhas conexões?</span><span class="sxs-lookup"><span data-stu-id="efdf0-110">How do I manage my connections?</span></span>](#how-do-i-manage-my-connections)
* [<span data-ttu-id="efdf0-111">Quais são os requisitos de licença e os termos de uso para conectores do Graph?</span><span class="sxs-lookup"><span data-stu-id="efdf0-111">What are the license requirements and terms of use for Graph connectors?</span></span>](#what-are-the-license-requirements-and-terms-of-use-for-graph-connectors)
* [<span data-ttu-id="efdf0-112">Quais são os recursos de visualização?</span><span class="sxs-lookup"><span data-stu-id="efdf0-112">What are the preview features?</span></span>](#what-are-the-preview-features)
* [<span data-ttu-id="efdf0-113">Como personalizar e configurar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="efdf0-113">How do I customize and configure search results?</span></span>](#how-do-i-customize-and-configure-search-results)
* [<span data-ttu-id="efdf0-114">Como faço para pesquisar dados do meu conector de um aplicativo personalizado?</span><span class="sxs-lookup"><span data-stu-id="efdf0-114">How do I search my connector data from a custom application?</span></span>](#how-do-i-search-my-connector-data-from-a-custom-application)
* [<span data-ttu-id="efdf0-115">Como personalizar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="efdf0-115">How do I customize search results?</span></span>](#how-do-i-customize-search-results)
* [<span data-ttu-id="efdf0-116">Quais são as limitações do conector</span><span class="sxs-lookup"><span data-stu-id="efdf0-116">What are the connector limitations</span></span>](#what-are-the-connector-limitations)

<!---Modify to another note that is more accurate after rollout completion--->
> [!IMPORTANT]
> <span data-ttu-id="efdf0-117">Os conectores do Microsoft Graph e as APIs de Pesquisa da Microsoft agora estão geralmente disponíveis.</span><span class="sxs-lookup"><span data-stu-id="efdf0-117">Microsoft Graph connectors and Microsoft Search APIs are now generally available.</span></span> <span data-ttu-id="efdf0-118">As primeiras versões serão para clientes configurados para lançamento direcionado.</span><span class="sxs-lookup"><span data-stu-id="efdf0-118">The first rollouts will be to customers configured for  targeted release.</span></span> <span data-ttu-id="efdf0-119">Se você quiser usar um conector Graph em seu locatário, os usuários e administradores devem optar [pela versão direcionada.](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="efdf0-119">If you want to use a Graph connector in your tenant, users and administrators must opt into [Targeted release](/microsoft-365/admin/manage/release-options-in-office-365?preserve-view=true&view=o365-worldwide).</span></span>

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

## <a name="what-data-sources-can-be-connected-to-microsoft-search"></a><span data-ttu-id="efdf0-120">Quais fontes de dados podem ser conectadas à Pesquisa da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="efdf0-120">What data sources can be connected to Microsoft Search?</span></span>

<span data-ttu-id="efdf0-121">A Microsoft fornece 9 conectores do Graph e nossos parceiros de ecossistema criaram mais de 100 conectores graph.</span><span class="sxs-lookup"><span data-stu-id="efdf0-121">Microsoft provides 9 Graph connectors and our ecosystem partners have created over 100 more Graph connectors.</span></span> <span data-ttu-id="efdf0-122">Você também pode criar seu próprio conector do Graph.</span><span class="sxs-lookup"><span data-stu-id="efdf0-122">You can also build your own Graph connector.</span></span>

### <a name="graph-connectors-by-microsoft"></a><span data-ttu-id="efdf0-123">Conectores de gráfico da Microsoft</span><span class="sxs-lookup"><span data-stu-id="efdf0-123">Graph connectors by Microsoft</span></span>

<span data-ttu-id="efdf0-124">Você pode se conectar às seguintes fontes de dados usando conectores graph criados pela Microsoft:</span><span class="sxs-lookup"><span data-stu-id="efdf0-124">You can connect to the following data sources using Graph connectors created by Microsoft:</span></span>

<!---Add links below when new docs are created--->
* [<span data-ttu-id="efdf0-125">Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="efdf0-125">Azure Data Lake Storage Gen2</span></span>](azure-data-lake-connector.md)
* [<span data-ttu-id="efdf0-126">Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="efdf0-126">Azure DevOps</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="efdf0-127">Azure SQL e Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="efdf0-127">Azure SQL and Microsoft SQL Server</span></span>](MSSQL-connector.md)
* [<span data-ttu-id="efdf0-128">Sites empresariais</span><span class="sxs-lookup"><span data-stu-id="efdf0-128">Enterprise websites</span></span>](enterprise-web-connector.md)
* [<span data-ttu-id="efdf0-129">MediaWiki</span><span class="sxs-lookup"><span data-stu-id="efdf0-129">MediaWiki</span></span>](mediawiki-connector.md)
* [<span data-ttu-id="efdf0-130">Compartilhamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="efdf0-130">File share</span></span>](fileshare-connector.md)
* [<span data-ttu-id="efdf0-131">Oracle SQL (visualização)</span><span class="sxs-lookup"><span data-stu-id="efdf0-131">Oracle SQL (preview)</span></span>](OracleSQL-connector.md)
* [<span data-ttu-id="efdf0-132">Salesforce (visualização)</span><span class="sxs-lookup"><span data-stu-id="efdf0-132">Salesforce (preview)</span></span>](salesforce-connector.md)
* [<span data-ttu-id="efdf0-133">ServiceNow</span><span class="sxs-lookup"><span data-stu-id="efdf0-133">ServiceNow</span></span>](servicenow-connector.md)

<span data-ttu-id="efdf0-134">A [galeria de conectores do Graph](connectors-gallery.md) contém uma breve descrição de cada um desses conectores do Graph.</span><span class="sxs-lookup"><span data-stu-id="efdf0-134">The [Graph connectors gallery](connectors-gallery.md) contains a brief description of each of these Graph connectors.</span></span> <span data-ttu-id="efdf0-135">Se você estiver pronto para conectar uma dessas fontes de dados [](configure-connector.md) ao seu locatário, leia a visão geral da Instalação e quaisquer outros artigos na seção Conectores de Instalação da Microsoft que se apliquem à sua fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="efdf0-135">If you're ready to connect one of these data sources to your tenant, be sure to read the [Setup overview](configure-connector.md) and any other articles in the Setup connectors by Microsoft section that apply to your data source.</span></span>

### <a name="graph-connectors-by-our-partners"></a><span data-ttu-id="efdf0-136">Conectores de gráfico por nossos parceiros</span><span class="sxs-lookup"><span data-stu-id="efdf0-136">Graph connectors by our partners</span></span>

<span data-ttu-id="efdf0-137">A [galeria de conectores](connectors-gallery.md) do Microsoft Graph inclui uma breve descrição de cada um dos conectores do Graph criados por nossos parceiros e um link para o site de cada parceiro.</span><span class="sxs-lookup"><span data-stu-id="efdf0-137">The [Microsoft Graph connectors gallery](connectors-gallery.md) includes a brief description of each of the Graph connectors created by our partners, and a link to each partner's website.</span></span> <span data-ttu-id="efdf0-138">Para saber mais, entre em contato diretamente com cada parceiro.</span><span class="sxs-lookup"><span data-stu-id="efdf0-138">To learn more, contact each partner directly.</span></span>

### <a name="build-your-own-graph-connector"></a><span data-ttu-id="efdf0-139">Criar seu próprio conector do Graph</span><span class="sxs-lookup"><span data-stu-id="efdf0-139">Build your own Graph connector</span></span>

<span data-ttu-id="efdf0-140">Você pode criar seu próprio conector do Graph, se preferir.</span><span class="sxs-lookup"><span data-stu-id="efdf0-140">You can build your own Graph connector if you prefer.</span></span> <span data-ttu-id="efdf0-141">Para obter mais informações sobre como criar conectores do Graph, consulte [a Visão geral da API de Pesquisa da Microsoft no Microsoft Graph](/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="efdf0-141">For more information on building Graph connectors, see the [Overview of the Microsoft Search API in Microsoft Graph](/graph/search-concept-overview).</span></span>

## <a name="how-do-i-manage-my-connections"></a><span data-ttu-id="efdf0-142">Como faço para gerenciar minhas conexões?</span><span class="sxs-lookup"><span data-stu-id="efdf0-142">How do I manage my connections?</span></span>

<span data-ttu-id="efdf0-143">Você pode gerenciar suas conexões na [guia Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) no Centro de administração [do Microsoft 365.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="efdf0-143">You can manage your connections from the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="efdf0-144">Para obter mais informações sobre como gerenciar conexões, consulte: [Gerenciar suas conexões](manage-connector.md).</span><span class="sxs-lookup"><span data-stu-id="efdf0-144">For more information about managing connections, see: [Manage your connections](manage-connector.md).</span></span>

## <a name="what-are-the-license-requirements-and-terms-of-use-for-graph-connectors"></a><span data-ttu-id="efdf0-145">Quais são os requisitos de licença e os termos de uso para conectores do Graph?</span><span class="sxs-lookup"><span data-stu-id="efdf0-145">What are the license requirements and terms of use for Graph connectors?</span></span>

<span data-ttu-id="efdf0-146">Você precisa de uma licença válida do Microsoft 365 ou office 365 e cota suficiente de Conectores do Graph para que os usuários em sua organização visualizam dados de conectores em seus resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="efdf0-146">You need a valid Microsoft 365 or Office 365 license and sufficient Graph Connectors quota for users in your organization to view data from connectors in their search results.</span></span>

<span data-ttu-id="efdf0-147">Para saber mais, confira [Requisitos de licença e preços](licensing.md) e Termos de [uso.](terms-of-use.md)</span><span class="sxs-lookup"><span data-stu-id="efdf0-147">To learn more, see [License requirements and pricing](licensing.md) and [Terms of use](terms-of-use.md).</span></span>

## <a name="what-are-the-preview-features"></a><span data-ttu-id="efdf0-148">Quais são os recursos de visualização?</span><span class="sxs-lookup"><span data-stu-id="efdf0-148">What are the preview features?</span></span>

<span data-ttu-id="efdf0-149">Embora os conectores do Microsoft Graph e as APIs de Pesquisa da Microsoft agora estão geralmente disponíveis, há vários recursos que estão na visualização.</span><span class="sxs-lookup"><span data-stu-id="efdf0-149">Although Microsoft Graph connectors and Microsoft Search APIs are now generally available, there are several features that are in preview.</span></span>

<span data-ttu-id="efdf0-150">O conjunto de conectores e recursos na visualização inclui:</span><span class="sxs-lookup"><span data-stu-id="efdf0-150">The set of connectors and features in preview include:</span></span>

* [<span data-ttu-id="efdf0-151">Conector do Azure DevOps</span><span class="sxs-lookup"><span data-stu-id="efdf0-151">Azure DevOps connector</span></span>](azure-devops-connector.md)
* [<span data-ttu-id="efdf0-152">Conector do Salesforce</span><span class="sxs-lookup"><span data-stu-id="efdf0-152">Salesforce connector</span></span>](salesforce-connector.md)
* <span data-ttu-id="efdf0-153">[Conector ServiceNow](servicenow-connector.md) com permissões de pesquisa que usam ACLs de origem</span><span class="sxs-lookup"><span data-stu-id="efdf0-153">[ServiceNow connector](servicenow-connector.md) with search permissions that use source ACLs</span></span>
* [<span data-ttu-id="efdf0-154">Gerenciar tipos de cluster</span><span class="sxs-lookup"><span data-stu-id="efdf0-154">Manage result cluster</span></span>](result-cluster.md)

## <a name="how-do-i-customize-and-configure-search-results"></a><span data-ttu-id="efdf0-155">Como personalizar e configurar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="efdf0-155">How do I customize and configure search results?</span></span>

<span data-ttu-id="efdf0-156">Há muitas maneiras de personalizar e configurar os resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="efdf0-156">There are many ways to customize and configure search results.</span></span> <span data-ttu-id="efdf0-157">Confira os seguintes artigos para saber mais:</span><span class="sxs-lookup"><span data-stu-id="efdf0-157">See the following articles to learn more:</span></span>

* [<span data-ttu-id="efdf0-158">Gerenciar verticais e tipos de resultados</span><span class="sxs-lookup"><span data-stu-id="efdf0-158">Manage verticals and result types</span></span>](customize-search-page.md)
* [<span data-ttu-id="efdf0-159">Gerenciar layouts de resultados de pesquisa</span><span class="sxs-lookup"><span data-stu-id="efdf0-159">Manage search result layouts</span></span>](customize-results-layout.md)
* [<span data-ttu-id="efdf0-160">Gerenciar tipos de cluster</span><span class="sxs-lookup"><span data-stu-id="efdf0-160">Manage result cluster</span></span>](result-cluster.md)
* [<span data-ttu-id="efdf0-161">Gerenciar filtros personalizados</span><span class="sxs-lookup"><span data-stu-id="efdf0-161">Manage custom filters</span></span>](custom-filters.md)

## <a name="how-do-i-search-my-connector-data-from-a-custom-application"></a><span data-ttu-id="efdf0-162">Como faço para pesquisar dados do meu conector de um aplicativo personalizado?</span><span class="sxs-lookup"><span data-stu-id="efdf0-162">How do I search my connector data from a custom application?</span></span>

<span data-ttu-id="efdf0-163">Depois que os dados personalizados são indexados, os [desenvolvedores podem consultar esses dados.](/graph/search-concept-custom-types)</span><span class="sxs-lookup"><span data-stu-id="efdf0-163">After custom data is indexed, developers can [query this data](/graph/search-concept-custom-types).</span></span> <span data-ttu-id="efdf0-164">Você pode exibir seus dados em qualquer aplicativo.</span><span class="sxs-lookup"><span data-stu-id="efdf0-164">You can view your data in any application.</span></span> <span data-ttu-id="efdf0-165">Para obter mais informações, consulte [Visão geral da API de Pesquisa da Microsoft no Microsoft Graph](/graph/search-concept-overview).</span><span class="sxs-lookup"><span data-stu-id="efdf0-165">For more information, see the [Overview of the Microsoft Search API in Microsoft Graph](/graph/search-concept-overview).</span></span>

## <a name="how-do-i-customize-search-results"></a><span data-ttu-id="efdf0-166">Como personalizar os resultados da pesquisa?</span><span class="sxs-lookup"><span data-stu-id="efdf0-166">How do I customize search results?</span></span>

<span data-ttu-id="efdf0-167">A próxima etapa é personalizar os resultados da pesquisa conforme recomendado neste artigo Como personalizar e configurar os resultados [da pesquisa?](#how-do-i-customize-and-configure-search-results).</span><span class="sxs-lookup"><span data-stu-id="efdf0-167">The next step is to customize the search results as recommended in this article [How do I customize and configure search results?](#how-do-i-customize-and-configure-search-results).</span></span> <span data-ttu-id="efdf0-168">Para saber mais sobre como personalizar os resultados da pesquisa, consulte [Personalizar a página de resultados da pesquisa.](customize-search-page.md)</span><span class="sxs-lookup"><span data-stu-id="efdf0-168">To learn more about customizing search results, see [Customize the search results page](customize-search-page.md).</span></span>

## <a name="what-are-the-connector-limitations"></a><span data-ttu-id="efdf0-169">Quais são as limitações do conector?</span><span class="sxs-lookup"><span data-stu-id="efdf0-169">What are the connector limitations?</span></span>

* <span data-ttu-id="efdf0-170">Quando você **publica** um conector criado pela Microsoft, pode levar alguns minutos para que a conexão seja criada.</span><span class="sxs-lookup"><span data-stu-id="efdf0-170">When you **publish** a Microsoft-built connector, it might take a few minutes for the connection to be created.</span></span> <span data-ttu-id="efdf0-171">Durante esse tempo, a conexão mostrará seu status como pendente.</span><span class="sxs-lookup"><span data-stu-id="efdf0-171">During that time, the connection will show its status as pending.</span></span>

* <span data-ttu-id="efdf0-172">O Centro de administração do [Microsoft 365](https://admin.microsoft.com) não dá suporte à edição do **esquema** de pesquisa depois que uma conexão é publicada.</span><span class="sxs-lookup"><span data-stu-id="efdf0-172">The [Microsoft 365 admin center](https://admin.microsoft.com) doesn't support editing the **search schema** after a connection is published.</span></span> <span data-ttu-id="efdf0-173">Para editar o esquema de pesquisa, exclua sua conexão e crie um novo.</span><span class="sxs-lookup"><span data-stu-id="efdf0-173">To edit the search schema, delete your connection and then create a new one.</span></span>

* <span data-ttu-id="efdf0-174">A produtividade de ingestão é acelerada em cerca de quatro itens por segundo.</span><span class="sxs-lookup"><span data-stu-id="efdf0-174">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="efdf0-175">Não há suporte para atualizações de esquema.</span><span class="sxs-lookup"><span data-stu-id="efdf0-175">There is no support for schema updates.</span></span> <span data-ttu-id="efdf0-176">Depois de criar uma configuração de conexão, não há como atualizar o esquema.</span><span class="sxs-lookup"><span data-stu-id="efdf0-176">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="efdf0-177">Você só pode excluir e re-criar a conexão.</span><span class="sxs-lookup"><span data-stu-id="efdf0-177">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="efdf0-178">Há um limite de conexão.</span><span class="sxs-lookup"><span data-stu-id="efdf0-178">There is a connection limit.</span></span> <span data-ttu-id="efdf0-179">Cada locatário pode criar até 10 conexões.</span><span class="sxs-lookup"><span data-stu-id="efdf0-179">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="efdf0-180">O suporte de edição para conexão não está disponível.</span><span class="sxs-lookup"><span data-stu-id="efdf0-180">Edit support for connection is not available.</span></span> <span data-ttu-id="efdf0-181">Depois que a conexão tiver sido criada, você não poderá editá-la ou alterá-la.</span><span class="sxs-lookup"><span data-stu-id="efdf0-181">Once the connection has been created, you can't edit or change it.</span></span> <span data-ttu-id="efdf0-182">Se precisar alterar qualquer detalhe, exclua e recrie a conexão.</span><span class="sxs-lookup"><span data-stu-id="efdf0-182">If you need to change any details, you must delete and recreate the connection.</span></span>