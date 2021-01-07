---
title: Cluster de resultados de conectores
ms.author: manusi
author: manusi
manager: ruppala
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Detalhes sobre a experiência de cluster do resultado dos conectores
ms.openlocfilehash: f2355213a0b1821968c801153841c274e539d72e
ms.sourcegitcommit: 7294c953e7939e48f128656cc2f8f22705ae3f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49773023"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="ea097-103">Cluster de resultados do conectores do Graph</span><span class="sxs-lookup"><span data-stu-id="ea097-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="ea097-104">Visão geral do cluster de resultados do conectores do Graph (visualização)</span><span class="sxs-lookup"><span data-stu-id="ea097-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="ea097-105">Com os conectores do Graph os clusters de resultados, as empresas podem pesquisar conteúdo de fontes de dados de terceiros no modo de exibição padrão, na guia **tudo** , no SharePoint, no Office.com e no Microsoft Search no Bing.</span><span class="sxs-lookup"><span data-stu-id="ea097-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view, the **All** tab, in SharePoint, Office.com, and Microsoft Search in Bing.</span></span>

<span data-ttu-id="ea097-106">Os clusters de resultados ajudam os usuários a descobrir todo o conteúdo de terceiros em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="ea097-106">Result clusters help users discover all third party content in one place.</span></span> <span data-ttu-id="ea097-107">Os resultados mostrados em um cluster de resultados são agrupados juntos com base na configuração vertical de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ea097-107">The results shown in a result cluster are grouped together based on the search vertical configuration.</span></span>

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="ea097-108">Como os resultados do conector são selecionados e exibidos</span><span class="sxs-lookup"><span data-stu-id="ea097-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="ea097-109">Os resultados do conector fornecidos no cluster de resultados são derivados das verticais de pesquisa individuais com o conteúdo do conector.</span><span class="sxs-lookup"><span data-stu-id="ea097-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="ea097-110">Cada vertical de pesquisa fornece um conjunto de resultados relevantes que se torna um cluster de resultado candidato.</span><span class="sxs-lookup"><span data-stu-id="ea097-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="ea097-111">Os resultados relevantes são escolhidos com base na propriedade "título" e na propriedade "conteúdo" de cada item.</span><span class="sxs-lookup"><span data-stu-id="ea097-111">Relevant results are chosen based on the "title" property and "content" property of each item.</span></span> <span data-ttu-id="ea097-112">A propriedade Content está marcada como *IsContent = true* no esquema.</span><span class="sxs-lookup"><span data-stu-id="ea097-112">The content property is marked as *isContent=true* on the schema.</span></span>

<span data-ttu-id="ea097-113">Para garantir a descoberta de conteúdo de verticais de pesquisa, recomendamos fornecer títulos significativos para seus itens.</span><span class="sxs-lookup"><span data-stu-id="ea097-113">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="ea097-114">Isso afeta positivamente a arbitragem dos candidatos do cluster de resultados e a probabilidade de seu conteúdo aparecer em um cluster de resultados.</span><span class="sxs-lookup"><span data-stu-id="ea097-114">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="ea097-115">Por exemplo, evite o uso de IDs como valores para a propriedade "title", a menos que os usuários estejam usando IDs para procurar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ea097-115">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="ea097-116">A frequência com que um cluster de resultados é mostrado varia em fatores como o número de verticais de pesquisa que você configura e o tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ea097-116">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="ea097-117">Por meio da interação ou ignoração de um cluster de resultados, os usuários fornecem implicitamente dicas que ajustarão o disparador ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="ea097-117">By either interacting or ignoring a result cluster, users will implicitly provide hints that will adjust its triggering over time.</span></span>

<span data-ttu-id="ea097-118">A experiência de resultados de pesquisa para itens de conector mostrados em seu cluster de resultados usa [tipos de resultados](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) definidos por você.</span><span class="sxs-lookup"><span data-stu-id="ea097-118">The search result experience for connector items shown in your result cluster uses [result types](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) defined by you.</span></span> <span data-ttu-id="ea097-119">Se nenhum tipo de resultado é configurado, um [layout gerado pelo sistema](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) é usado.</span><span class="sxs-lookup"><span data-stu-id="ea097-119">If no result type is configured, a [system generated layout](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) is used.</span></span> 

<span data-ttu-id="ea097-120">É recomendável usar a propriedade "title" como o título do resultado da pesquisa e a propriedade "content" como a descrição da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ea097-120">We recommend using the “title” property as the search result title and the "content" property as the search description.</span></span> <span data-ttu-id="ea097-121">Isso oferecerá a melhor experiência para os usuários por meio de um disparo preciso do cluster de resultados e dos resultados mais relevantes no cluster.</span><span class="sxs-lookup"><span data-stu-id="ea097-121">This will provide the best experience for your users through accurate triggering of the result cluster and most relevant results in the cluster.</span></span> 

## <a name="enable-result-clusters"></a><span data-ttu-id="ea097-122">Habilitar clusters de resultados</span><span class="sxs-lookup"><span data-stu-id="ea097-122">Enable result clusters</span></span>
  
<span data-ttu-id="ea097-123">A experiência de cluster de resultados está desativada por padrão.</span><span class="sxs-lookup"><span data-stu-id="ea097-123">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="ea097-124">Siga estas etapas para ativar a experiência no nível da organização:</span><span class="sxs-lookup"><span data-stu-id="ea097-124">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="ea097-125">No [centro de administração do Microsoft 365](https://admin.microsoft.com), acesse [**verticalmente**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span><span class="sxs-lookup"><span data-stu-id="ea097-125">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="ea097-126">Selecione **todos os** verticais e, em seguida, habilitar **Mostrar resultados do conector**.</span><span class="sxs-lookup"><span data-stu-id="ea097-126">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="ea097-127">Siga estas etapas para ativar a experiência no nível do site do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="ea097-127">Follow these steps to turn on the experience at the SharePoint site level:</span></span>

1. <span data-ttu-id="ea097-128">No site do SharePoint em que você deseja a experiência de cluster de resultados, vá para **configurações**.</span><span class="sxs-lookup"><span data-stu-id="ea097-128">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="ea097-129">Vá para **informações do site** > **Exibir todas as configurações do site**.</span><span class="sxs-lookup"><span data-stu-id="ea097-129">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="ea097-130">Vá para a seção de pesquisa da Microsoft e selecione **Configurar a pesquisa da Microsoft para este conjunto de sites**.</span><span class="sxs-lookup"><span data-stu-id="ea097-130">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="ea097-131">No painel de navegação, vá para **experiência personalizada** e, em seguida, selecione **vertical**.</span><span class="sxs-lookup"><span data-stu-id="ea097-131">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="ea097-132">Selecione **todos os** verticais e, em seguida, habilitar **Mostrar resultados do conector**.</span><span class="sxs-lookup"><span data-stu-id="ea097-132">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="ea097-133">Exibir a experiência de cluster de resultados após a habilitação</span><span class="sxs-lookup"><span data-stu-id="ea097-133">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="ea097-134">Depois que você ativar a experiência de cluster de resultados, poderá levar alguns minutos para que você possa visualizá-lo.</span><span class="sxs-lookup"><span data-stu-id="ea097-134">After you turn on the result cluster experience, it might take a few minutes before you can view it.</span></span> <span data-ttu-id="ea097-135">Se quiser a experiência imediatamente, você poderá acrescentar *cacheClear = true* à URL no SharePoint e no Office.</span><span class="sxs-lookup"><span data-stu-id="ea097-135">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
