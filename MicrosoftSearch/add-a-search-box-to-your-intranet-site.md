---
title: Adicionar uma caixa de pesquisa ao site de intranet
ms.author: dawholl
author: dawholl
manager: kellis
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
description: Obter sugestões de pesquisa relevantes e encontrar resultados de trabalho mais rapidamente adicionando uma Pesquisa da Microsoft de pesquisa ao seu site ou página da intranet.
ms.openlocfilehash: 7d9ca4be8d3be27a7549ffb940d6dc55b3763baf
ms.sourcegitcommit: 38a0f09596c2bca0e12bf4cada7b4c64fd4c48e4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53449057"
---
# <a name="add-a-search-box-to-your-intranet-site"></a>Adicionar uma caixa de pesquisa ao site de intranet

Para fornecer aos usuários acesso fácil aos resultados da sua organização, adicione um Pesquisa da Microsoft na caixa Bing de pesquisa a qualquer site ou página da intranet. Estes são alguns dos benefícios:

- Uma caixa de pesquisa em seu SharePoint ou portal de intranet fornece um ponto de entrada familiar e confiável para começar a pesquisar
- Oferece suporte a todos os principais navegadores da Web, incluindo o Google Chrome e Microsoft Edge
- Somente sugestões de pesquisa de sua organização aparecem, as sugestões da Web nunca são incluídas
- Leva os usuários a uma Pesquisa da Microsoft na Bing de resultados do trabalho, que exclui anúncios e resultados da Web
- Você controla a aparência e o comportamento da caixa de pesquisa, incluindo a capacidade de pousar usuários em um padrão vertical ou em uma vertical personalizada que você criou
  
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
        dropShadow: true,                       // default: false
        iconColor: "#067FA6",                   // default: #067FA6
        title: "Search box",                    // default: "Search box"
        vertical: "Person-people",              // default: not specified, search box directs to the All vertical on the WORK results page
        companyNameInGhostText: "Contoso"       // default: not specified
                                                // when absent, ghost text will be "Search work"
                                                // when specified, text will be "Search <companyNameInGhostText>"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

## <a name="direct-users-to-a-default-or-custom-vertical"></a>Direcionar os usuários para um padrão ou vertical personalizado

Para oferecer uma integração fácil entre seus aplicativos de linha de negócios ou sites de intranet e seus resultados de trabalho, você também pode personalizar a caixa de pesquisa especificando um padrão ou vertical personalizado em que os usuários devem pousar quando clicarem em uma sugestão de pesquisa.

Use a opção vertical em bfbSearchBoxConfig para definir o vertical que você deseja. Por exemplo, se você quiser que os usuários sempre aterrisem na vertical Sites, uma das verticais padrão, use o valor "Site-sites".

:::image type="content" alt-text="Captura de tela da página de resultados do trabalho no Pesquisa da Microsoft em Bing mostrando os resultados verticais de Sites e URL." source="media/sites-vertical-esb.png" lightbox="media/sites-vertical-esb.png":::

Para verticais personalizadas, use o hash no final da URL. Você pode encontrar esses valores pesquisando na página de trabalho no Bing, clicando em um rótulo vertical e copiando o valor após o sinal de número (#).

:::image type="content" alt-text="Captura de tela da página de resultados do trabalho no Pesquisa da Microsoft em Bing mostrando uma URL e resultados verticais de apresentação personalizados." source="media/custom-vertical-esb.png" lightbox="media/custom-vertical-esb.png":::

## <a name="use-an-iframe-to-embed-a-search-box"></a>Usar um iFrame para incorporar uma caixa de pesquisa

Se incorporar um script não for uma opção para o site, use um iFrame para adicionar a caixa de pesquisa. Você não poderá personalizar a caixa de pesquisa.
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```

## <a name="inprivate-mode-and-conditional-access"></a>Modo InPrivate e Acesso Condicional

Uma caixa de pesquisa incorporada será desabilitada se a página ou o site for aberto em uma janela InPrivate. Além disso, com o suporte ao Acesso Condicional do Azure AD no Microsoft Edge, Bing.com não dá suporte a entrada do AAD ao usar o modo InPrivate. Para obter mais informações sobre o Acesso Condicional na Borda, [consulte Microsoft Edge e Acesso Condicional.](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge) 
