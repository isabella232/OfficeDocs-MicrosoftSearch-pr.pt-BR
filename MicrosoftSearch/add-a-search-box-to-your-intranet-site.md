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
ms.openlocfilehash: ea3efc224b69ffe894104068b055efe8b5882cc1
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2019
ms.locfileid: "34727920"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>Adicionar uma caixa de pesquisa ao site de intranet

Para ter acesso rápido a sugestões de pesquisa relevantes e encontrar resultados de trabalho mais rapidamente, adicione uma caixa de pesquisa da Pesquisa da Microsoft a um site ou página da intranet.
  
## <a name="add-a-search-box-to-an-intranet-page"></a>Adicionar uma caixa de pesquisa à página de intranet

Você precisa adicionar dois elementos à página: um contêiner para a caixa de pesquisa e o script que a alimenta.
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

Em um site clássico do SharePoint, adicione uma Web Part do Editor de Scripts e solte o script nela.
  
## <a name="enable-the-search-box-for-mobile"></a>Habilitar a caixa de pesquisa para dispositivos móveis

Para sites da intranet ou páginas disponíveis para usuários móveis, adicione isMobile: true ao objeto settings:
  
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

## <a name="put-focus-on-the-search-box-by-default"></a>Colocar o foco na caixa de pesquisa padrão

Para ajudar os usuários a pesquisar mais rapidamente, quando a página ou o site for carregado, coloque o cursor do mouse sobre a caixa de pesquisa adicionando focus: true ao objeto settings:
  
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

## <a name="customize-the-appearance-of-the-search-box"></a>Personalizar a aparência da caixa de pesquisa 

Para ajudar a caixa de pesquisa se ajustar melhor ao estilo da sua intranet, existe uma variedade de opções de configurações que você pode usar. Misturar e combinar as opções para atender às suas necessidades.

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

## <a name="use-an-iframe-to-embed-a-search-box"></a>Usar um iFrame para incorporar uma caixa de pesquisa

Se incorporar um script não for uma opção para o site, use um iFrame para adicionar a caixa de pesquisa. Você não poderá personalizar a aparência da caixa de pesquisa.
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```