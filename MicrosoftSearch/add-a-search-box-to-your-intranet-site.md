---
title: Adicionar uma caixa de pesquisa ao seu site de intranet
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
description: Obter sugestões de pesquisa relevantes e localizar resultados de trabalho mais rápidos, adicionando uma caixa de pesquisa do Microsoft Search para uma página ou um site da intranet.
ms.openlocfilehash: 699cfd9c411c9b86f3a2f8742c425aaedef1ebc5
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612414"
---
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="e3aa9-103">Adicionar uma caixa de pesquisa ao seu site de intranet</span><span class="sxs-lookup"><span data-stu-id="e3aa9-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="e3aa9-104">Para obter acesso rápido a sugestões de pesquisa relevantes e resultados de trabalho, adicione uma caixa de pesquisa do Microsoft Search a qualquer site da intranet ou da página.</span><span class="sxs-lookup"><span data-stu-id="e3aa9-104">For fast access to relevant search suggestions and work results, add a Microsoft Search search box to any intranet site or page.</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="e3aa9-105">Adicionar uma caixa de pesquisa a uma página de intranet</span><span class="sxs-lookup"><span data-stu-id="e3aa9-105">Add a search box to an intranet page</span></span>

<span data-ttu-id="e3aa9-106">Você precisa adicionar dois elementos à página: um contêiner para a caixa de pesquisa e o script que alimenta-lo.</span><span class="sxs-lookup"><span data-stu-id="e3aa9-106">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="e3aa9-107">Em um site do SharePoint clássico, adicione um Web Part do Editor de scripts e solte o script nela.</span><span class="sxs-lookup"><span data-stu-id="e3aa9-107">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="e3aa9-108">Habilite a caixa de pesquisa para dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="e3aa9-108">Enable the search box for mobile</span></span>

<span data-ttu-id="e3aa9-109">Para sites de intranet ou páginas disponíveis para os usuários móveis, adicione isMobile: True para o objeto de configurações:</span><span class="sxs-lookup"><span data-stu-id="e3aa9-109">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="e3aa9-110">Colocar o foco na caixa de pesquisa por padrão</span><span class="sxs-lookup"><span data-stu-id="e3aa9-110">Put focus on the search box by default</span></span>

<span data-ttu-id="e3aa9-111">Para ajudar os usuários a pesquisa mais rápida, quando as cargas de site ou página coloque o cursor na caixa Pesquisar, adicionando o foco: True para o objeto de configurações:</span><span class="sxs-lookup"><span data-stu-id="e3aa9-111">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="e3aa9-112">Use um iFrame para inserir uma caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="e3aa9-112">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="e3aa9-113">Se incorporar um script não for uma opção para o site, use um iFrame para adicionar a caixa de pesquisa:</span><span class="sxs-lookup"><span data-stu-id="e3aa9-113">If embedding a script isn't an option for the site, use an iFrame to add the search box:</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
