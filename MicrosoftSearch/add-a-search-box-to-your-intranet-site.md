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
description: Para ter acesso a sugestões de pesquisa relevantes e encontrar resultados de trabalho mais rapidamente, adicione uma caixa de pesquisa da Pesquisa da Microsoft a um site ou página da intranet.
ms.openlocfilehash: 699cfd9c411c9b86f3a2f8742c425aaedef1ebc5
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612414"
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

## <a name="use-an-iframe-to-embed-a-search-box"></a>Usar um iFrame para inserir uma caixa de pesquisa

Se incorporar um script não for uma opção para o site, use um iFrame para adicionar a caixa de pesquisa:
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
