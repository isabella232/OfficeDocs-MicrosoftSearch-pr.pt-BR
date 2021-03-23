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
description: Detalhes da experiência do Cluster de Resultados dos Conectores
ms.openlocfilehash: ae5528f2e12c9e331b66e821f2a9c03947d788df
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031769"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="551bf-103">Cluster de resultados de conectores de gráfico</span><span class="sxs-lookup"><span data-stu-id="551bf-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="551bf-104">Visão geral do cluster de resultados de conectores do Graph (Visualização)</span><span class="sxs-lookup"><span data-stu-id="551bf-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="551bf-105">Com clusters de resultados de conectores do Graph, as empresas podem pesquisar conteúdo de fontes de dados de terceiros em seu modo de exibição padrão, a guia **Todos,** no SharePoint, Office.com e a Pesquisa da Microsoft no Bing.</span><span class="sxs-lookup"><span data-stu-id="551bf-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view, the **All** tab, in SharePoint, Office.com, and Microsoft Search in Bing.</span></span>

<span data-ttu-id="551bf-106">Os clusters de resultados ajudam os usuários a descobrir todo o conteúdo de terceiros em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="551bf-106">Result clusters help users discover all third party content in one place.</span></span> <span data-ttu-id="551bf-107">Os resultados mostrados em um cluster de resultados são agrupados com base na configuração vertical da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="551bf-107">The results shown in a result cluster are grouped together based on the search vertical configuration.</span></span>

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="551bf-108">Como os resultados do conector são selecionados e exibidos</span><span class="sxs-lookup"><span data-stu-id="551bf-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="551bf-109">Os resultados do conector fornecidos no cluster de resultados são derivados de verticais de pesquisa individuais com conteúdo de conector.</span><span class="sxs-lookup"><span data-stu-id="551bf-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="551bf-110">Cada pesquisa vertical fornece um conjunto de resultados relevantes que se torna um cluster de resultados de candidato.</span><span class="sxs-lookup"><span data-stu-id="551bf-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="551bf-111">Os resultados relevantes são escolhidos com base na propriedade "title" e na propriedade "content" de cada item.</span><span class="sxs-lookup"><span data-stu-id="551bf-111">Relevant results are chosen based on the "title" property and "content" property of each item.</span></span> <span data-ttu-id="551bf-112">A propriedade content é marcada como *isContent=true* no esquema.</span><span class="sxs-lookup"><span data-stu-id="551bf-112">The content property is marked as *isContent=true* on the schema.</span></span>

<span data-ttu-id="551bf-113">Para garantir a descoberta de conteúdo das verticais de pesquisa, recomendamos fornecer títulos significativos para seus itens.</span><span class="sxs-lookup"><span data-stu-id="551bf-113">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="551bf-114">Isso afeta positivamente a arbitragem de candidatos a cluster de resultados e a probabilidade de seu conteúdo aparecer em um cluster de resultados.</span><span class="sxs-lookup"><span data-stu-id="551bf-114">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="551bf-115">Por exemplo, evite o uso de IDs como valores para a propriedade "title" a menos que seus usuários usem IDs para procurar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="551bf-115">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="551bf-116">A frequência com que um cluster de resultados é mostrado varia em fatores como o número de verticais de pesquisa que você configura e o tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="551bf-116">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="551bf-117">Ao interagir ou ignorar um cluster de resultados, os usuários fornecerão implicitamente dicas que ajustarão seu gatilho ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="551bf-117">By either interacting or ignoring a result cluster, users will implicitly provide hints that will adjust its triggering over time.</span></span>

<span data-ttu-id="551bf-118">A experiência de resultado da pesquisa para itens de conector mostrados em seu cluster de resultados usa [tipos de resultados](./customize-search-page.md#create-your-own-result-type) definidos por você.</span><span class="sxs-lookup"><span data-stu-id="551bf-118">The search result experience for connector items shown in your result cluster uses [result types](./customize-search-page.md#create-your-own-result-type) defined by you.</span></span> <span data-ttu-id="551bf-119">Se nenhum tipo de resultado for configurado, um [layout gerado pelo sistema](./customize-search-page.md#default-search-result-layout) será usado.</span><span class="sxs-lookup"><span data-stu-id="551bf-119">If no result type is configured, a [system generated layout](./customize-search-page.md#default-search-result-layout) is used.</span></span> 

<span data-ttu-id="551bf-120">Recomendamos usar a propriedade "title" como o título do resultado da pesquisa e a propriedade "content" como a descrição da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="551bf-120">We recommend using the “title” property as the search result title and the "content" property as the search description.</span></span> <span data-ttu-id="551bf-121">Isso fornecerá a melhor experiência para seus usuários por meio do acionamento preciso do cluster de resultados e dos resultados mais relevantes no cluster.</span><span class="sxs-lookup"><span data-stu-id="551bf-121">This will provide the best experience for your users through accurate triggering of the result cluster and most relevant results in the cluster.</span></span> 

## <a name="enable-result-clusters"></a><span data-ttu-id="551bf-122">Habilitar clusters de resultados</span><span class="sxs-lookup"><span data-stu-id="551bf-122">Enable result clusters</span></span>
  
<span data-ttu-id="551bf-123">A experiência de cluster de resultados é desligada por padrão.</span><span class="sxs-lookup"><span data-stu-id="551bf-123">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="551bf-124">Siga estas etapas para ativar a experiência no nível da organização:</span><span class="sxs-lookup"><span data-stu-id="551bf-124">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="551bf-125">No Centro de administração do [Microsoft 365,](https://admin.microsoft.com)vá para [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span><span class="sxs-lookup"><span data-stu-id="551bf-125">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="551bf-126">Selecione Todos **os verticais** e, em seguida, **habilitar Mostrar resultados do conector**.</span><span class="sxs-lookup"><span data-stu-id="551bf-126">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="551bf-127">Siga estas etapas para ativar a experiência no nível do site do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="551bf-127">Follow these steps to turn on the experience at the SharePoint site level:</span></span>

1. <span data-ttu-id="551bf-128">No site do SharePoint onde você deseja a experiência de cluster de resultados, vá para **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="551bf-128">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="551bf-129">Acesse Informações **do site** Exibir todas > **as configurações do site.**</span><span class="sxs-lookup"><span data-stu-id="551bf-129">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="551bf-130">Vá para a seção Pesquisa da Microsoft e selecione **Configurar a Pesquisa da Microsoft para este conjunto de sites.**</span><span class="sxs-lookup"><span data-stu-id="551bf-130">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="551bf-131">No painel de navegação, vá para **Experiência personalizada** e selecione **Verticals**.</span><span class="sxs-lookup"><span data-stu-id="551bf-131">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="551bf-132">Selecione Todos **os verticais** e, em seguida, **habilitar Mostrar resultados do conector**.</span><span class="sxs-lookup"><span data-stu-id="551bf-132">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="551bf-133">Exibir a experiência de cluster de resultados depois de habilitada</span><span class="sxs-lookup"><span data-stu-id="551bf-133">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="551bf-134">Depois de ativar a experiência de cluster de resultados, pode levar até 12 horas para poder exibi-la.</span><span class="sxs-lookup"><span data-stu-id="551bf-134">After you turn on the result cluster experience, it can take up to 12 hours before you can view it.</span></span> <span data-ttu-id="551bf-135">Se quiser a experiência imediatamente, você pode anexar *cacheClear=true* à URL no SharePoint e no Office.</span><span class="sxs-lookup"><span data-stu-id="551bf-135">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>