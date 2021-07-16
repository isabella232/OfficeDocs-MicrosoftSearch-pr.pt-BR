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
# <a name="add-a-search-box-to-your-intranet-site"></a><span data-ttu-id="82b8a-103">Adicionar uma caixa de pesquisa ao site de intranet</span><span class="sxs-lookup"><span data-stu-id="82b8a-103">Add a search box to your intranet site</span></span>

<span data-ttu-id="82b8a-104">Para fornecer aos usuários acesso fácil aos resultados da sua organização, adicione um Pesquisa da Microsoft na caixa Bing de pesquisa a qualquer site ou página da intranet.</span><span class="sxs-lookup"><span data-stu-id="82b8a-104">To provide your users with easy access to results from your organization, add a Microsoft Search in Bing search box to any intranet site or page.</span></span> <span data-ttu-id="82b8a-105">Estes são alguns dos benefícios:</span><span class="sxs-lookup"><span data-stu-id="82b8a-105">These are some of the benefits:</span></span>

- <span data-ttu-id="82b8a-106">Uma caixa de pesquisa em seu SharePoint ou portal de intranet fornece um ponto de entrada familiar e confiável para começar a pesquisar</span><span class="sxs-lookup"><span data-stu-id="82b8a-106">A search box on your SharePoint or intranet portal provides a familiar, trusted entry point to start searching</span></span>
- <span data-ttu-id="82b8a-107">Oferece suporte a todos os principais navegadores da Web, incluindo o Google Chrome e Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="82b8a-107">Supports all major web browsers, including Google Chrome and Microsoft Edge</span></span>
- <span data-ttu-id="82b8a-108">Somente sugestões de pesquisa de sua organização aparecem, as sugestões da Web nunca são incluídas</span><span class="sxs-lookup"><span data-stu-id="82b8a-108">Only search suggestions from your organization appear, web suggestions are never included</span></span>
- <span data-ttu-id="82b8a-109">Leva os usuários a uma Pesquisa da Microsoft na Bing de resultados do trabalho, que exclui anúncios e resultados da Web</span><span class="sxs-lookup"><span data-stu-id="82b8a-109">Takes users to a Microsoft Search in Bing work results page, which excludes ads and web results</span></span>
- <span data-ttu-id="82b8a-110">Você controla a aparência e o comportamento da caixa de pesquisa, incluindo a capacidade de pousar usuários em um padrão vertical ou em uma vertical personalizada que você criou</span><span class="sxs-lookup"><span data-stu-id="82b8a-110">You control the appearance and behavior of the search box, including the ability to land users on a default vertical or a custom vertical you've created</span></span>
  
## <a name="add-a-search-box-to-an-intranet-page"></a><span data-ttu-id="82b8a-111">Adicionar uma caixa de pesquisa à página de intranet</span><span class="sxs-lookup"><span data-stu-id="82b8a-111">Add a search box to an intranet page</span></span>

<span data-ttu-id="82b8a-112">Você precisa adicionar dois elementos à página: um contêiner para a caixa de pesquisa e o script que a alimenta.</span><span class="sxs-lookup"><span data-stu-id="82b8a-112">You need to add two elements to the page: a container for the search box and the script that powers it.</span></span>
  
```html
<div id="bfb_searchbox"></div>
<script>
    var bfbSearchBoxConfig = {
        containerSelector: "bfb_searchbox"
    };
</script>
<script async src="https://www.bing.com/business/s?k=sb"></script>
```

<span data-ttu-id="82b8a-113">Em um site clássico do SharePoint, adicione uma Web Part do Editor de Scripts e solte o script nela.</span><span class="sxs-lookup"><span data-stu-id="82b8a-113">On a SharePoint classic site, add a Script Editor Web Part and drop the script in it.</span></span>
  
## <a name="enable-the-search-box-for-mobile"></a><span data-ttu-id="82b8a-114">Habilitar a caixa de pesquisa para dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="82b8a-114">Enable the search box for mobile</span></span>

<span data-ttu-id="82b8a-115">Para sites da intranet ou páginas disponíveis para usuários móveis, adicione isMobile: true ao objeto settings:</span><span class="sxs-lookup"><span data-stu-id="82b8a-115">For intranet sites or pages available to mobile users, add isMobile: true to the settings object:</span></span>
  
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

## <a name="put-focus-on-the-search-box-by-default"></a><span data-ttu-id="82b8a-116">Colocar o foco na caixa de pesquisa padrão</span><span class="sxs-lookup"><span data-stu-id="82b8a-116">Put focus on the search box by default</span></span>

<span data-ttu-id="82b8a-117">Para ajudar os usuários a pesquisar mais rapidamente, quando a página ou o site for carregado, coloque o cursor do mouse sobre a caixa de pesquisa adicionando focus: true ao objeto settings:</span><span class="sxs-lookup"><span data-stu-id="82b8a-117">To help users search faster, when the page or site loads place the cursor in the search box by adding focus: true to the settings object:</span></span>
  
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

## <a name="customize-the-appearance-of-the-search-box"></a><span data-ttu-id="82b8a-118">Personalizar a aparência da caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="82b8a-118">Customize the appearance of the search box</span></span> 

<span data-ttu-id="82b8a-119">Para ajudar a caixa de pesquisa se ajustar melhor ao estilo da sua intranet, existe uma variedade de opções de configurações que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="82b8a-119">To help the search box better fit with the style of your intranet, there are a variety of configuration options you can use.</span></span> <span data-ttu-id="82b8a-120">Misturar e combinar as opções para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="82b8a-120">Mix and match options to suit your needs.</span></span>

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

## <a name="direct-users-to-a-default-or-custom-vertical"></a><span data-ttu-id="82b8a-121">Direcionar os usuários para um padrão ou vertical personalizado</span><span class="sxs-lookup"><span data-stu-id="82b8a-121">Direct users to a default or custom vertical</span></span>

<span data-ttu-id="82b8a-122">Para oferecer uma integração fácil entre seus aplicativos de linha de negócios ou sites de intranet e seus resultados de trabalho, você também pode personalizar a caixa de pesquisa especificando um padrão ou vertical personalizado em que os usuários devem pousar quando clicarem em uma sugestão de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="82b8a-122">To provide easy integration between your line-of-business apps or intranet sites and your work results, you can also customize the search box by specifying a default or custom vertical that users should land on when they click a search suggestion.</span></span>

<span data-ttu-id="82b8a-123">Use a opção vertical em bfbSearchBoxConfig para definir o vertical que você deseja.</span><span class="sxs-lookup"><span data-stu-id="82b8a-123">Use the vertical option in bfbSearchBoxConfig to define the vertical you want.</span></span> <span data-ttu-id="82b8a-124">Por exemplo, se você quiser que os usuários sempre aterrisem na vertical Sites, uma das verticais padrão, use o valor "Site-sites".</span><span class="sxs-lookup"><span data-stu-id="82b8a-124">For example, if you want users to always land on the Sites vertical, one of the default verticals, use the value "Site-sites".</span></span>

:::image type="content" alt-text="Captura de tela da página de resultados do trabalho no Pesquisa da Microsoft em Bing mostrando os resultados verticais de Sites e URL." source="media/sites-vertical-esb.png" lightbox="media/sites-vertical-esb.png":::

<span data-ttu-id="82b8a-126">Para verticais personalizadas, use o hash no final da URL.</span><span class="sxs-lookup"><span data-stu-id="82b8a-126">For custom verticals, use the hash at the end of the URL.</span></span> <span data-ttu-id="82b8a-127">Você pode encontrar esses valores pesquisando na página de trabalho no Bing, clicando em um rótulo vertical e copiando o valor após o sinal de número (#).</span><span class="sxs-lookup"><span data-stu-id="82b8a-127">You can find these values by searching from the work page on Bing, clicking a vertical label, and copying the value after the number sign (#).</span></span>

:::image type="content" alt-text="Captura de tela da página de resultados do trabalho no Pesquisa da Microsoft em Bing mostrando uma URL e resultados verticais de apresentação personalizados." source="media/custom-vertical-esb.png" lightbox="media/custom-vertical-esb.png":::

## <a name="use-an-iframe-to-embed-a-search-box"></a><span data-ttu-id="82b8a-129">Usar um iFrame para incorporar uma caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="82b8a-129">Use an iFrame to embed a search box</span></span>

<span data-ttu-id="82b8a-130">Se incorporar um script não for uma opção para o site, use um iFrame para adicionar a caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="82b8a-130">If embedding a script isn't an option for the site, use an iFrame to add the search box.</span></span> <span data-ttu-id="82b8a-131">Você não poderá personalizar a caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="82b8a-131">You won't be able to customize the search box.</span></span>
  
```html
<iframe width="564" height="400" src="https://www.bing.com/business/searchbox"></iframe>
```

## <a name="inprivate-mode-and-conditional-access"></a><span data-ttu-id="82b8a-132">Modo InPrivate e Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="82b8a-132">InPrivate mode and Conditional Access</span></span>

<span data-ttu-id="82b8a-133">Uma caixa de pesquisa incorporada será desabilitada se a página ou o site for aberto em uma janela InPrivate.</span><span class="sxs-lookup"><span data-stu-id="82b8a-133">An embedded search box will be disabled if the page or site is opened in an InPrivate window.</span></span> <span data-ttu-id="82b8a-134">Além disso, com o suporte ao Acesso Condicional do Azure AD no Microsoft Edge, Bing.com não dá suporte a entrada do AAD ao usar o modo InPrivate.</span><span class="sxs-lookup"><span data-stu-id="82b8a-134">Also, with Azure AD Conditional Access support in Microsoft Edge, Bing.com doesn't support AAD sign in when using InPrivate mode.</span></span> <span data-ttu-id="82b8a-135">Para obter mais informações sobre o Acesso Condicional na Borda, [consulte Microsoft Edge e Acesso Condicional.](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge)</span><span class="sxs-lookup"><span data-stu-id="82b8a-135">For more information about Conditional Access in Edge, see [Microsoft Edge and Conditional Access](/deployedge/ms-edge-security-conditional-access#accessing-conditional-access-protected-resources-in-microsoft-edge).</span></span> 
