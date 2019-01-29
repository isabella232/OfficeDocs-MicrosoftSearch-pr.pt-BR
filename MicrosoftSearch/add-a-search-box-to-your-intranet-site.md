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
# <a name="add-a-search-box-to-your-intranet-site"></a>Adicionar uma caixa de pesquisa ao seu site de intranet

Para obter acesso rápido a sugestões de pesquisa relevantes e resultados de trabalho, adicione uma caixa de pesquisa do Microsoft Search a qualquer site da intranet ou da página.
  
## <a name="add-a-search-box-to-an-intranet-page"></a>Adicionar uma caixa de pesquisa a uma página de intranet

Você precisa adicionar dois elementos à página: um contêiner para a caixa de pesquisa e o script que alimenta-lo.
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

Em um site do SharePoint clássico, adicione um Web Part do Editor de scripts e solte o script nela.
  
## <a name="enable-the-search-box-for-mobile"></a>Habilite a caixa de pesquisa para dispositivos móveis

Para sites de intranet ou páginas disponíveis para os usuários móveis, adicione isMobile: True para o objeto de configurações:
  
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

## <a name="put-focus-on-the-search-box-by-default"></a>Colocar o foco na caixa de pesquisa por padrão

Para ajudar os usuários a pesquisa mais rápida, quando as cargas de site ou página coloque o cursor na caixa Pesquisar, adicionando o foco: True para o objeto de configurações:
  
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

## <a name="use-an-iframe-to-embed-a-search-box"></a>Use um iFrame para inserir uma caixa de pesquisa

Se incorporar um script não for uma opção para o site, use um iFrame para adicionar a caixa de pesquisa:
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```
