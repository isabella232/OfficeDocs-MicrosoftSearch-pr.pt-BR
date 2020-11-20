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
ms.openlocfilehash: eac4180a247fe17b4e86b57a69f2b7bdb79e56bb
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367710"
---
# <a name="graph-connectors-result-cluster"></a><span data-ttu-id="e03df-103">Cluster de resultados do conectores do Graph</span><span class="sxs-lookup"><span data-stu-id="e03df-103">Graph connectors result cluster</span></span>

## <a name="overview-of-the-graph-connectors-result-cluster-preview"></a><span data-ttu-id="e03df-104">Visão geral do cluster de resultados do conectores do Graph (visualização)</span><span class="sxs-lookup"><span data-stu-id="e03df-104">Overview of the Graph connectors result cluster (Preview)</span></span>  

 <span data-ttu-id="e03df-105">Com os grupos de resultados de conectores do Graph, as empresas podem pesquisar conteúdo de fontes de dados de terceiros em seu modo de exibição padrão (a guia tudo) no SharePoint e no Office.com.</span><span class="sxs-lookup"><span data-stu-id="e03df-105">With Graph connectors result clusters, enterprises can search for content from third party data sources in their default view (the All tab) in SharePoint and Office.com.</span></span>

<span data-ttu-id="e03df-106">Os clusters de resultados ajudam os usuários a descobrir todo o conteúdo de terceiros (previoulsy vinculado a um único conector e vertical) em um só lugar.</span><span class="sxs-lookup"><span data-stu-id="e03df-106">Result clusters help users discover all third party content (previoulsy tied to a single connector and vertical) in one place.</span></span> <span data-ttu-id="e03df-107">Os resultados mostrados em um cluster de resultados são agrupados juntos com base em como o administrador de locatários os configura em uma vertical de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e03df-107">The results shown in a result cluster are grouped together based on how the tenant administrator configures them in a search vertical.</span></span>  

## <a name="how-connector-results-are-selected-and-displayed"></a><span data-ttu-id="e03df-108">Como os resultados do conector são selecionados e exibidos</span><span class="sxs-lookup"><span data-stu-id="e03df-108">How connector results are selected and displayed</span></span>

<span data-ttu-id="e03df-109">Os resultados do conector fornecidos no cluster de resultados são derivados das verticais de pesquisa individuais com o conteúdo do conector.</span><span class="sxs-lookup"><span data-stu-id="e03df-109">Connector results provided in the result cluster are derived from individual search verticals with connector content.</span></span> <span data-ttu-id="e03df-110">Cada vertical de pesquisa fornece um conjunto de resultados relevantes que se torna um cluster de resultado candidato.</span><span class="sxs-lookup"><span data-stu-id="e03df-110">Each search vertical provides a set of relevant results which becomes a candidate result cluster.</span></span> <span data-ttu-id="e03df-111">Os resultados relevantes são escolhidos com base na propriedade "título", no trecho de resultados e no componente de conteúdo de cada item.</span><span class="sxs-lookup"><span data-stu-id="e03df-111">Relevant results are chosen based on the "title" property, result snippet, and content component of each item.</span></span>

<span data-ttu-id="e03df-112">Para garantir a descoberta de conteúdo de verticais de pesquisa, recomendamos fornecer títulos significativos para seus itens.</span><span class="sxs-lookup"><span data-stu-id="e03df-112">To ensure discovery of content from the search verticals, we recommend providing meaningful titles for your items.</span></span> <span data-ttu-id="e03df-113">Isso afeta positivamente a arbitragem dos candidatos do cluster de resultados e a probabilidade de seu conteúdo aparecer em um cluster de resultados.</span><span class="sxs-lookup"><span data-stu-id="e03df-113">This positively impacts the arbitration of result cluster candidates and the likelihood of your content showing up in a result cluster.</span></span> <span data-ttu-id="e03df-114">Por exemplo, evite o uso de IDs como valores para a propriedade "title", a menos que os usuários estejam usando IDs para procurar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e03df-114">For example, avoid the use of IDs as values for the property "title" unless your users are using IDs to look for content.</span></span>

<span data-ttu-id="e03df-115">A frequência com que um cluster de resultados é mostrado varia em fatores como o número de verticais de pesquisa que você configura e o tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e03df-115">How often a result cluster is shown varies on factors such as the number of search verticals that you configure and the type of content.</span></span> <span data-ttu-id="e03df-116">Ao selecionar ou ignorar resultados de cluster de resultados, você fornecerá implicitamente dicas que ajustarão o disparo dos clusters de resultados ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="e03df-116">By either selecting or ignoring result cluster results, you will implicitly provide hints that will adjust the triggering of result clusters over time.</span></span>

<span data-ttu-id="e03df-117">A experiência de resultados de pesquisa para itens de conector mostrados em seu cluster de resultados é gerada pelo sistema e não usa layouts de resultados personalizados.</span><span class="sxs-lookup"><span data-stu-id="e03df-117">The search result experience for connector items shown in your result cluster is system generated and does not use custom result layouts.</span></span> <span data-ttu-id="e03df-118">Você deve declarar a propriedade "título" e o conteúdo do item durante o registro da conexão, se quiser que os resultados apareçam no seu cluster de resultados.</span><span class="sxs-lookup"><span data-stu-id="e03df-118">You must declare the "title" property and item content during connection registration if you want results to appear in your result cluster.</span></span>

## <a name="enable-result-clusters"></a><span data-ttu-id="e03df-119">Habilitar clusters de resultados</span><span class="sxs-lookup"><span data-stu-id="e03df-119">Enable result clusters</span></span>
  
<span data-ttu-id="e03df-120">A experiência de cluster de resultados está desativada por padrão.</span><span class="sxs-lookup"><span data-stu-id="e03df-120">The result cluster experience is turned off by default.</span></span>  
<span data-ttu-id="e03df-121">Siga estas etapas para ativar a experiência no nível da organização:</span><span class="sxs-lookup"><span data-stu-id="e03df-121">Follow these steps to turn on the experience at the organization level:</span></span>

<span data-ttu-id="e03df-122">Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e03df-122">Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="e03df-123">No [centro de administração do Microsoft 365](https://admin.microsoft.com/), vá para **configurações**  >  **&** de personalização de inteligência de pesquisa  >  **Customization**  >  **Verticals**.</span><span class="sxs-lookup"><span data-stu-id="e03df-123">In the [Microsoft 365 admin center](https://admin.microsoft.com/), go to **Settings** > **Search & intelligence** > **Customization** > **Verticals**.</span></span>  
2. <span data-ttu-id="e03df-124">Selecione o botão **todos** vertical e vá para a seção **Mostrar resultados do conector** .</span><span class="sxs-lookup"><span data-stu-id="e03df-124">Select  the **All** vertical and go to the **Show connector results** section.</span></span> <span data-ttu-id="e03df-125">Ative a experiência no nível do site.</span><span class="sxs-lookup"><span data-stu-id="e03df-125">Turn on the experience at the site level.</span></span>

<span data-ttu-id="e03df-126">Do</span><span class="sxs-lookup"><span data-stu-id="e03df-126">Sharepoint</span></span>

1. <span data-ttu-id="e03df-127">No site do SharePoint em que você deseja a experiência de cluster de resultados, vá para **configurações**.</span><span class="sxs-lookup"><span data-stu-id="e03df-127">On the SharePoint site where you want the result cluster experience, go to **Settings**.</span></span>
2. <span data-ttu-id="e03df-128">Vá para **informações do site** > **Exibir todas as configurações do site**.</span><span class="sxs-lookup"><span data-stu-id="e03df-128">Go to **Site information**>**View all site settings**.</span></span>
3. <span data-ttu-id="e03df-129">Vá para a seção de pesquisa da Microsoft e selecione **Configurar a pesquisa da Microsoft para este conjunto de sites**.</span><span class="sxs-lookup"><span data-stu-id="e03df-129">Go to the Microsoft Search section, then select **Configure Microsoft Search for this site collection**.</span></span>
4. <span data-ttu-id="e03df-130">No painel de navegação, vá para **experiência personalizada** e, em seguida, selecione **vertical**.</span><span class="sxs-lookup"><span data-stu-id="e03df-130">In the navigation pane, go to **Custom experience**, then select **Verticals**.</span></span>
5. <span data-ttu-id="e03df-131">Selecione **todos os** verticais e, em seguida, habilitar **Mostrar resultados do conector**.</span><span class="sxs-lookup"><span data-stu-id="e03df-131">Select the **All** vertical, then enable **Show connector results**.</span></span>

## <a name="view-the-result-cluster-experience-after-it-is-enabled"></a><span data-ttu-id="e03df-132">Exibir a experiência de cluster de resultados após a habilitação</span><span class="sxs-lookup"><span data-stu-id="e03df-132">View the result cluster experience after it is enabled</span></span>

<span data-ttu-id="e03df-133">Depois que você ativar a experiência de cluster de resultados, poderá levar alguns minutos para que você possa visualizá-lo.</span><span class="sxs-lookup"><span data-stu-id="e03df-133">After you turn on the result cluster experience, it might take a few minutes before you can view it.</span></span> <span data-ttu-id="e03df-134">Se quiser a experiência imediatamente, você poderá acrescentar *cacheClear = true* à URL no SharePoint e no Office.</span><span class="sxs-lookup"><span data-stu-id="e03df-134">If you want the experience immediately, you can append *cacheClear=true* to the URL in SharePoint and Office.</span></span>
