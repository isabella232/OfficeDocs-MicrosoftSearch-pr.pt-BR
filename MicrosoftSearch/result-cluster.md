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
description: Detalhes da experiência do Cluster de Resultados de Conectores
ms.openlocfilehash: fb29fb9c14811698fb7c5d043853b57231c76a0b
ms.sourcegitcommit: d1bc6c41ecf47584373ce57543502bed55753d0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080833"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="c7959-103">Cluster de resultados de conectores do Graph</span><span class="sxs-lookup"><span data-stu-id="c7959-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="c7959-104">Visão geral do cluster de resultados dos conectores do Graph (Visualização)</span><span class="sxs-lookup"><span data-stu-id="c7959-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

<span data-ttu-id="c7959-105">Com os clusters de resultados de conectores do Graph, as empresas  podem pesquisar conteúdo de fontes de dados de terceiros em sua exibição padrão, a guia Todos, no SharePoint, no Office.com e na Pesquisa da Microsoft no Bing.</span><span class="sxs-lookup"><span data-stu-id="c7959-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view, the **All** tab, in SharePoint, Office.com, and Microsoft Search in Bing.</span></span>

<span data-ttu-id="c7959-106">Os clusters de resultados ajudam os usuários a descobrir todo o conteúdo de terceiros em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="c7959-106">Result clusters help users discover all third party content in one place.</span></span> <span data-ttu-id="c7959-107">Os resultados mostrados em um cluster de resultados são agrupados com base na configuração vertical de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c7959-107">The results shown in a result cluster are grouped together based on the search vertical configuration.</span></span>

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="c7959-108">Como os resultados do conector são selecionados e exibidos</span><span class="sxs-lookup"><span data-stu-id="c7959-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="c7959-109">Os resultados do conector fornecidos no cluster de resultados são derivados de pesquisas verticais individuais com conteúdo do conector.</span><span class="sxs-lookup"><span data-stu-id="c7959-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="c7959-110">Cada pesquisa vertical fornece um conjunto de resultados relevantes que se torna um cluster de resultados candidatos.</span><span class="sxs-lookup"><span data-stu-id="c7959-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="c7959-111">Os resultados relevantes são escolhidos com base na propriedade "title" e na propriedade "content" de cada item.</span><span class="sxs-lookup"><span data-stu-id="c7959-111">Relevant results are chosen based on the "title" property and "content" property of each item.</span></span> <span data-ttu-id="c7959-112">A propriedade de conteúdo é marcada *como isContent=true* no esquema.</span><span class="sxs-lookup"><span data-stu-id="c7959-112">The content property is marked as *isContent=true* on the schema.</span></span>

<span data-ttu-id="c7959-113">Para garantir a descoberta de conteúdo dos verticais de pesquisa, recomendamos fornecer títulos significativos para seus itens.</span><span class="sxs-lookup"><span data-stu-id="c7959-113">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="c7959-114">Isso positivamente afeta a arbitragem de candidatos a cluster de resultados e a probabilidade de seu conteúdo aparecer em um cluster de resultados.</span><span class="sxs-lookup"><span data-stu-id="c7959-114">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="c7959-115">Por exemplo, evite o uso de IDs como valores para a propriedade "title", a menos que os usuários usem IDs para procurar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c7959-115">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="c7959-116">A frequência com que um cluster de resultados é exibido varia em fatores como o número de pesquisas verticais que você configura e o tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c7959-116">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="c7959-117">Ao interagir ou ignorar um cluster de resultados, os usuários fornecerão implicitamente dicas que ajustarão seu gatilho ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="c7959-117">By either interacting or ignoring a result cluster, users will implicitly provide hints that will adjust its triggering over time.</span></span>

<span data-ttu-id="c7959-118">A experiência de resultado de pesquisa para itens de conector mostrados em seu cluster de resultados usa [tipos de](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) resultados definidos por você.</span><span class="sxs-lookup"><span data-stu-id="c7959-118">The search result experience for connector items shown in your result cluster uses [result types](https://docs.microsoft.com/microsoftsearch/customize-search-page#create-your-own-result-type) defined by you.</span></span> <span data-ttu-id="c7959-119">Se nenhum tipo de resultado for configurado, um [layout gerado pelo](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) sistema será usado.</span><span class="sxs-lookup"><span data-stu-id="c7959-119">If no result type is configured, a [system generated layout](https://docs.microsoft.com/microsoftsearch/customize-search-page#default-search-result-layout) is used.</span></span> 

<span data-ttu-id="c7959-120">Recomendamos usar a propriedade "title" como o título do resultado da pesquisa e a propriedade "content" como a descrição da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c7959-120">We recommend using the “title” property as the search result title and the "content" property as the search description.</span></span> <span data-ttu-id="c7959-121">Isso fornecerá a melhor experiência para seus usuários por meio do disparo preciso do cluster de resultados e dos resultados mais relevantes no cluster.</span><span class="sxs-lookup"><span data-stu-id="c7959-121">This will provide the best experience for your users through accurate triggering of the result cluster and most relevant results in the cluster.</span></span> 

## <a name="enable-result-clusters"></a><span data-ttu-id="c7959-122">Habilitar clusters de resultados</span><span class="sxs-lookup"><span data-stu-id="c7959-122">Enable result clusters</span></span>
  
<span data-ttu-id="c7959-123">A experiência do cluster de resultados está desligada por padrão.</span><span class="sxs-lookup"><span data-stu-id="c7959-123">The result cluster experience is turned off by default.</span></span>  

<span data-ttu-id="c7959-124">Siga estas etapas para ativar a experiência no nível da organização:</span><span class="sxs-lookup"><span data-stu-id="c7959-124">Follow these steps to turn on the experience at the organization level:</span></span>

1. <span data-ttu-id="c7959-125">No centro [de administração do Microsoft 365,](https://admin.microsoft.com)vá para [**Verticais.**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)</span><span class="sxs-lookup"><span data-stu-id="c7959-125">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
2. <span data-ttu-id="c7959-126">Selecione Todos **os verticais** e habilitar **Mostrar resultados do conector.**</span><span class="sxs-lookup"><span data-stu-id="c7959-126">Select  the **All** vertical, then enable **Show connector results**.</span></span> 


<span data-ttu-id="c7959-127">Siga estas etapas para ativar a experiência no nível do site do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="c7959-127">Follow these steps to turn on the experience at the SharePoint site level:</span></span>

1. <span data-ttu-id="c7959-128">No site do SharePoint onde você deseja a experiência de cluster de resultados, vá para **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="c7959-128">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="c7959-129">Vá para Informações **do Site** Exibir todas > **as configurações do site.**</span><span class="sxs-lookup"><span data-stu-id="c7959-129">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="c7959-130">Vá para a seção Pesquisa da Microsoft e selecione **Configurar a Pesquisa da Microsoft para este conjunto de sites.**</span><span class="sxs-lookup"><span data-stu-id="c7959-130">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="c7959-131">No painel de navegação, vá para **Experiência personalizada** e selecione **Verticals.**</span><span class="sxs-lookup"><span data-stu-id="c7959-131">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="c7959-132">Selecione Todos **os verticais** e habilitar **Mostrar resultados do conector.**</span><span class="sxs-lookup"><span data-stu-id="c7959-132">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="c7959-133">Exibir a experiência do cluster de resultados depois que ela for habilitada</span><span class="sxs-lookup"><span data-stu-id="c7959-133">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="c7959-134">Depois de ativar a experiência do cluster de resultados, pode levar até 12 horas para que você possa exibi-la.</span><span class="sxs-lookup"><span data-stu-id="c7959-134">After you turn on the result cluster experience, it can take up to 12 hours before you can view it.</span></span> <span data-ttu-id="c7959-135">Se quiser a experiência imediatamente, você pode anexar *cacheClear=true* à URL no SharePoint e no Office.</span><span class="sxs-lookup"><span data-stu-id="c7959-135">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
