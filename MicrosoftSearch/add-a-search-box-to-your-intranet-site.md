---
title: Adicionar uma caixa de pesquisa ao site de intranet
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 10/31/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: f980b90f-95e2-4b66-8b21-69f601ff4b50
ROBOTS: NoIndex
description: Para ter acesso a sugestões de pesquisa relevantes e encontrar resultados de trabalho mais rapidamente, adicione uma caixa de pesquisa da Pesquisa da Microsoft a um site ou página da intranet.
ms.openlocfilehash: 867282393c7a4bffa63363a3455e4f1543c7f8a1
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34590689"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="d69c8-103">Adicionar uma caixa de pesquisa ao site de intranet</span><span class="sxs-lookup"><span data-stu-id="d69c8-103">Add a search box to your intranet site</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d69c8-104">Este artigo se aplica ao Microsoft Search no portal de administração do Bing.</span><span class="sxs-lookup"><span data-stu-id="d69c8-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="d69c8-105">Estamos movendo o portal para o centro de administração do Microsoft 365 e, posteriormente, ele será removido.</span><span class="sxs-lookup"><span data-stu-id="d69c8-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="d69c8-106">Recomendamos que você use o centro de administração do Microsoft 365 para começar.</span><span class="sxs-lookup"><span data-stu-id="d69c8-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> [<span data-ttu-id="d69c8-107">Visão geral do Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="d69c8-107">Overview of Microsoft Search</span></span>](overview-microsoft-search.md)

<span data-ttu-id="d69c8-108">Para ter acesso rápido a sugestões de pesquisa relevantes e encontrar resultados de trabalho mais rapidamente, adicione uma caixa de pesquisa da Pesquisa da Microsoft a um site ou página da intranet.</span><span class="sxs-lookup"><span data-stu-id="d69c8-108">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="d69c8-109">Adicionar uma caixa de pesquisa à página de intranet</span><span class="sxs-lookup"><span data-stu-id="d69c8-109">Add a search box to an intranet page</span></span>

<span data-ttu-id="d69c8-110">Você precisa adicionar dois elementos à página: um contêiner para a caixa de pesquisa e o script que a alimenta.</span><span class="sxs-lookup"><span data-stu-id="d69c8-110">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="d69c8-111">Em um site clássico do SharePoint, adicione uma Web Part do Editor de Scripts e solte o script nela.</span><span class="sxs-lookup"><span data-stu-id="d69c8-111">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="d69c8-112">Habilitar a caixa de pesquisa para dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="d69c8-112">Enable the search box for mobile</span></span>

<span data-ttu-id="d69c8-113">Para sites da intranet ou páginas disponíveis para usuários móveis, adicione isMobile: true ao objeto settings:</span><span class="sxs-lookup"><span data-stu-id="d69c8-113">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="d69c8-114">Colocar o foco na caixa de pesquisa padrão</span><span class="sxs-lookup"><span data-stu-id="d69c8-114">Put focus on the search box by default</span></span>

<span data-ttu-id="d69c8-115">Para ajudar os usuários a pesquisar mais rapidamente, quando a página ou o site for carregado, coloque o cursor do mouse sobre a caixa de pesquisa adicionando focus: true ao objeto settings:</span><span class="sxs-lookup"><span data-stu-id="d69c8-115">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="d69c8-116">Personalizar a aparência da caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="d69c8-116">Customize the appearance of the search box</span></span> 

<span data-ttu-id="d69c8-117">Para ajudar a caixa de pesquisa se ajustar melhor ao estilo da sua intranet, existe uma variedade de opções de configurações que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="d69c8-117">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="d69c8-118">Misturar e combinar as opções para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="d69c8-118">Mix and match options to suit your needs.</span></span>

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
                                                // when absent, ghost text will be "Search work and the web"
                                                // when specified, text will be "Search the web and [Contoso]"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="d69c8-119">Usar um iFrame para incorporar uma caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="d69c8-119">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="d69c8-120">Se incorporar um script não for uma opção para o site, use um iFrame para adicionar a caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d69c8-120">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="d69c8-121">Você não poderá personalizar a aparência da caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d69c8-121">You won't be able to customize the appearance of the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```