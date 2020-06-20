---
title: Adicionar uma caixa de pesquisa ao site de intranet
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: Para ter acesso a sugestões de pesquisa relevantes e encontrar resultados de trabalho mais rapidamente, adicione uma caixa de pesquisa da Pesquisa da Microsoft a um site ou página da intranet.
ms.openlocfilehash: af12ce4d17c2695e196f8e4d79ccd515f002f238
ms.sourcegitcommit: 92206ea179ec00b22496f6fd2866b5406449cf40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44798221"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="2ef97-103">Adicionar uma caixa de pesquisa ao site de intranet</span><span class="sxs-lookup"><span data-stu-id="2ef97-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="2ef97-104">Para permitir que seus usuários tenham acesso fácil aos resultados da sua organização, adicione uma pesquisa da Microsoft na caixa de pesquisa do Bing a qualquer site da intranet ou página.</span><span class="sxs-lookup"><span data-stu-id="2ef97-104">To provide your users with easy access to results from your organization, add a Microsoft Search in Bing search box to any intranet site or page.</span></span> <span data-ttu-id="2ef97-105">Estes são alguns dos benefícios:</span><span class="sxs-lookup"><span data-stu-id="2ef97-105">These are some of the benefits:</span></span>

- <span data-ttu-id="2ef97-106">Uma caixa de pesquisa em seu portal do SharePoint ou intranet fornece um ponto de entrada confiável e familiar para iniciar a pesquisa</span><span class="sxs-lookup"><span data-stu-id="2ef97-106">A search box on your SharePoint or intranet portal provides a familiar, trusted entry point to start searching</span></span>
- <span data-ttu-id="2ef97-107">Dá suporte a todos os principais navegadores da Web, incluindo o Google Chrome e o Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2ef97-107">Supports all major web browsers, including Google Chrome and Microsoft Edge</span></span>
- <span data-ttu-id="2ef97-108">Somente as sugestões de pesquisa de sua organização são exibidas, as sugestões da Web nunca são incluídas</span><span class="sxs-lookup"><span data-stu-id="2ef97-108">Only search suggestions from your organization appear, web suggestions are never included</span></span>
- <span data-ttu-id="2ef97-109">Leva os usuários para uma pesquisa da Microsoft na página de resultados de trabalho do Bing, que exclui anúncios e resultados da Web</span><span class="sxs-lookup"><span data-stu-id="2ef97-109">Takes users to a Microsoft Search in Bing work results page, which excludes ads and web results</span></span>
- <span data-ttu-id="2ef97-110">Você controla a aparência e o comportamento da caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="2ef97-110">You control the appearance and behavior of the search box</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="2ef97-111">Adicionar uma caixa de pesquisa à página de intranet</span><span class="sxs-lookup"><span data-stu-id="2ef97-111">Add a search box to an intranet page</span></span>

<span data-ttu-id="2ef97-112">Você precisa adicionar dois elementos à página: um contêiner para a caixa de pesquisa e o script que a alimenta.</span><span class="sxs-lookup"><span data-stu-id="2ef97-112">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="2ef97-113">Em um site clássico do SharePoint, adicione uma Web Part do Editor de Scripts e solte o script nela.</span><span class="sxs-lookup"><span data-stu-id="2ef97-113">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="2ef97-114">Habilitar a caixa de pesquisa para dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="2ef97-114">Enable the search box for mobile</span></span>

<span data-ttu-id="2ef97-115">Para sites da intranet ou páginas disponíveis para usuários móveis, adicione isMobile: true ao objeto settings:</span><span class="sxs-lookup"><span data-stu-id="2ef97-115">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox", 
        isMobile: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="2ef97-116">Colocar o foco na caixa de pesquisa padrão</span><span class="sxs-lookup"><span data-stu-id="2ef97-116">Put focus on the search box by default</span></span>

<span data-ttu-id="2ef97-117">Para ajudar os usuários a pesquisar mais rapidamente, quando a página ou o site for carregado, coloque o cursor do mouse sobre a caixa de pesquisa adicionando focus: true ao objeto settings:</span><span class="sxs-lookup"><span data-stu-id="2ef97-117">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        focus: true
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="2ef97-118">Personalizar a aparência da caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="2ef97-118">Customize the appearance of the search box</span></span> 

<span data-ttu-id="2ef97-119">Para ajudar a caixa de pesquisa se ajustar melhor ao estilo da sua intranet, existe uma variedade de opções de configurações que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="2ef97-119">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="2ef97-120">Misturar e combinar as opções para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="2ef97-120">Mix and match options to suit your needs.</span></span>

```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox",
        width: 560,                             // default: 560, min: 360, max: 650
        height: 40,                             // default: 40, min: 40, max: 72
        cornerRadius: 6,                        // default: 6, min: 0, max: 25                                   
        strokeOutline: true,                    // default: true
        dropShadow: true,                       // default: true
        iconColor: "#067FA6",                   // default: #067FA6
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="2ef97-121">Usar um iFrame para incorporar uma caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="2ef97-121">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="2ef97-122">Se incorporar um script não for uma opção para o site, use um iFrame para adicionar a caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2ef97-122">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="2ef97-123">Você não poderá personalizar a aparência da caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2ef97-123">You won't be able to customize the appearance of the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
