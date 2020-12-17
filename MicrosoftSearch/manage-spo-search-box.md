---
title: Gerenciando a caixa de pesquisa em sites do SharePoint
ms.author: keremy
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Como personalizar a experiência de caixa de pesquisa em sites do SharePoint
ms.openlocfilehash: 6ebd084aadb38acb5475b7e43d7c4092ffc09eb8
ms.sourcegitcommit: c5fe4e01403379b3ee7ea4dbded8b31696311d79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49700960"
---
# <a name="search-box-settings-on-sharepoint-sites"></a><span data-ttu-id="07882-103">Configurações da caixa de pesquisa em sites do SharePoint</span><span class="sxs-lookup"><span data-stu-id="07882-103">Search box settings on SharePoint sites</span></span>

<span data-ttu-id="07882-104">Uma das várias maneiras de o Microsoft Search ser personalizada nos sites do SharePoint é personalizar como a caixa de pesquisa na barra de navegação do pacote funciona em sites do SharePoint para atender melhor às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="07882-104">One of the several ways Microsoft Search can be customized on SharePoint sites is to tailor how the search box in the suite navigation bar works in SharePoint sites to best fit your needs.</span></span>

<span data-ttu-id="07882-105">Para outras opções de personalização, confira [alterar a página de resultados da pesquisa da Microsoft para adicionar verticais, tipos e layouts de resultados personalizados](customize-search-page.md)e [criar uma página de resultados de pesquisa personalizada](create-search-results-pages.md).</span><span class="sxs-lookup"><span data-stu-id="07882-105">For other customization options, see [Changing the Microsoft Search results page to add custom verticals, result types and layouts](customize-search-page.md), and [Creating a custom search results page](create-search-results-pages.md).</span></span>

> [!NOTE]
> <span data-ttu-id="07882-106">A caixa de pesquisa da barra de navegação do pacote não está disponível para todos os clientes no momento, mas essas opções ainda podem ser definidas e elas entrarão em vigor quando estiverem disponíveis.</span><span class="sxs-lookup"><span data-stu-id="07882-106">The suite navigation bar search box is not available for all customers at this time, but these options can still be set now and they will take effect when it becomes available.</span></span>

<span data-ttu-id="07882-107">Para as tarefas listadas abaixo, você usará o PowerShell com as extensões do PowerShell PnP do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="07882-107">For the tasks listed below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="07882-108">Você pode instalar e saber mais sobre como começar [aqui](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="07882-108">You can install and learn more about how to get started [here](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="07882-109">Você entrará no site ou no conjunto de sites usando este comando:</span><span class="sxs-lookup"><span data-stu-id="07882-109">You will sign into your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a><span data-ttu-id="07882-110">Alterar o escopo da pesquisa</span><span class="sxs-lookup"><span data-stu-id="07882-110">Changing the scope of search</span></span>

<span data-ttu-id="07882-111">Quando você cria um novo site no SharePoint Online hoje e digita na caixa de pesquisa, é exibida a página de resultados da pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="07882-111">When you create a new site in SharePoint Online today, and type into the search box, you are taken to the Microsoft Search results page.</span></span> <span data-ttu-id="07882-112">Essa página mostra os resultados do seu site atual por padrão e permite que você expanda o escopo de sua pesquisa para o Hub ao qual o site atual está associado (se houver algum) ou a toda a organização.</span><span class="sxs-lookup"><span data-stu-id="07882-112">This page shows results from your current site by default and allows you to expand the scope of your search to the hub that the current site is associated with (if there is one), or to the whole organization.</span></span>

<span data-ttu-id="07882-113">O escopo usado pela caixa de pesquisa, por padrão, depende do tipo de site.</span><span class="sxs-lookup"><span data-stu-id="07882-113">The scope the search box uses, by default, depends on type of site.</span></span>

* <span data-ttu-id="07882-114">Pesquisa de sites regulares no site atual.</span><span class="sxs-lookup"><span data-stu-id="07882-114">Regular sites search over the current site.</span></span>
* <span data-ttu-id="07882-115">Os sites de Hub pesquisam todos os sites no Hub.</span><span class="sxs-lookup"><span data-stu-id="07882-115">Hub sites search over all sites in the hub.</span></span>
* <span data-ttu-id="07882-116">Sites domésticos pesquisam todo o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="07882-116">Home sites search over all content.</span></span>

<span data-ttu-id="07882-117">Em alguns casos, talvez você queira alterar esses padrões para sempre Pesquisar toda a organização ou ao longo do Hub ao qual um site está associado, sem precisar de mais um clique.</span><span class="sxs-lookup"><span data-stu-id="07882-117">In some cases, you may want to change these defaults to always search over the whole organization, or across the hub a site is associated with, without needing an additional click.</span></span>

<span data-ttu-id="07882-118">Como proprietário do site, você pode alterar esses padrões usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="07882-118">As a site owner, you can change these defaults using the following command:</span></span>

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

<span data-ttu-id="07882-119">Depois de executar esse comando, o site que estava mostrando os resultados do site atual por padrão será iniciado para mostrar os resultados da organização inteira.</span><span class="sxs-lookup"><span data-stu-id="07882-119">After running this command, the site that was previously showing results from the current site by default will start to show results from the whole organization.</span></span>

<span data-ttu-id="07882-120">Para voltar para a configuração padrão, execute o comando novamente com o valor "DefaultScope".</span><span class="sxs-lookup"><span data-stu-id="07882-120">To go back to the default setting, run the command again with the value “DefaultScope".</span></span> <span data-ttu-id="07882-121">Para Pesquisar pelo Hub, use "Hub" como o valor SearchScope.</span><span class="sxs-lookup"><span data-stu-id="07882-121">To search across the Hub, use “Hub” as the SearchScope value.</span></span>

<span data-ttu-id="07882-122">Essa configuração se aplica ao nível de site individual.</span><span class="sxs-lookup"><span data-stu-id="07882-122">This setting applies at the individual site level.</span></span> <span data-ttu-id="07882-123">Não há nenhuma configuração equivalente para conjuntos de sites.</span><span class="sxs-lookup"><span data-stu-id="07882-123">There is no equivalent setting for site collections.</span></span>

## <a name="show-or-hide-the-search-box"></a><span data-ttu-id="07882-124">Mostrar ou ocultar a caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="07882-124">Show or hide the search box</span></span>

<span data-ttu-id="07882-125">Você pode optar por ocultar a caixa de pesquisa da barra de navegação do pacote se quiser impedir que os usuários pesquisem ou usem uma implementação de caixa de pesquisa personalizada.</span><span class="sxs-lookup"><span data-stu-id="07882-125">You can choose to hide the suite navigation bar search box if you want to prevent your users from searching or to use a custom search box implementation.</span></span>

<span data-ttu-id="07882-126">Para alterar essa configuração para um determinado site, use este comando:</span><span class="sxs-lookup"><span data-stu-id="07882-126">To change this setting for a given site use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="07882-127">Como alternativa, se você quiser defini-lo para todos os sites em um conjunto de sites, poderá usar este comando:</span><span class="sxs-lookup"><span data-stu-id="07882-127">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

<span data-ttu-id="07882-128">Após a execução desses comandos, a caixa de pesquisa não será mais exibida na barra de navegação na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="07882-128">After running these commands, the search box will no longer show up in the navigation bar on top of your page.</span></span> <span data-ttu-id="07882-129">Para voltar a mostrar a caixa de pesquisa, execute os comandos novamente com o valor fornecido para o parâmetro "SearchBoxInNavBar" como "Inherit".</span><span class="sxs-lookup"><span data-stu-id="07882-129">To go back to showing the search box, run the commands again with the value provided to "SearchBoxInNavBar" parameter to “Inherit”.</span></span>

<span data-ttu-id="07882-130">Há vários pontos a serem considerados:</span><span class="sxs-lookup"><span data-stu-id="07882-130">There are several points to consider:</span></span>

* <span data-ttu-id="07882-131">Essa configuração só se aplica à caixa de pesquisa na barra de navegação do pacote.</span><span class="sxs-lookup"><span data-stu-id="07882-131">This setting only applies to the search box in the suite navigation bar.</span></span> <span data-ttu-id="07882-132">Ela não se aplica às caixas de pesquisa que estão na página ou às caixas de pesquisa em páginas clássicas.</span><span class="sxs-lookup"><span data-stu-id="07882-132">It does not apply to search boxes that are in the page, or to search boxes on classic pages.</span></span>

* <span data-ttu-id="07882-133">Depois de desabilitar a caixa de pesquisa na barra de navegação, se você quiser a funcionalidade de pesquisa no seu site, você terá que fazê-lo sozinho usando uma Web Part personalizada ou uma extensão da estrutura do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="07882-133">Once you’ve disabled the search box in the navigation bar, if you want search functionality in your site, you will have to provide it yourself using a custom web part or a SharePoint Framework extension.</span></span>

* <span data-ttu-id="07882-134">Essa solução também removerá a caixa de pesquisa de listas e bibliotecas do seu site.</span><span class="sxs-lookup"><span data-stu-id="07882-134">This solution will remove the search box from lists and libraries for your site as well.</span></span> <span data-ttu-id="07882-135">Sua solução de pesquisa personalizada precisará considerar pesquisas contextuais para listas e bibliotecas do SharePoint, além de pesquisa em todo o site.</span><span class="sxs-lookup"><span data-stu-id="07882-135">Your custom search solution will need to consider contextual searches for SharePoint lists and libraries, in addition to site-wide search.</span></span>

* <span data-ttu-id="07882-136">Se você aplicar a configuração ao site raiz do seu domínio, a página inicial do SharePoint também será interrompida mostrando a caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="07882-136">If you apply the setting to the root site of your domain, the SharePoint start page will also stop showing the search box.</span></span>

## <a name="changing-the-hint-displayed-in-the-search-box"></a><span data-ttu-id="07882-137">Alterar a dica exibida na caixa de pesquisa</span><span class="sxs-lookup"><span data-stu-id="07882-137">Changing the hint displayed in the search box</span></span>

<span data-ttu-id="07882-138">Você pode alterar a dica que a caixa de pesquisa mostra para um determinado site ou conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="07882-138">You can change the hint the search box shows for a given site or site collection.</span></span> <span data-ttu-id="07882-139">Este é o texto que aparece na caixa de pesquisa antes de começar a digitar nele.</span><span class="sxs-lookup"><span data-stu-id="07882-139">This is the text that appears in the search box before they start typing into it.</span></span> <span data-ttu-id="07882-140">Isso pode ajudar a orientar os usuários sobre o que esperar da pesquisa se você tiver configurado uma página de resultados personalizada ou alterado o comportamento de pesquisa de outras maneiras.</span><span class="sxs-lookup"><span data-stu-id="07882-140">This may help guide your users about what to expect from search if you’ve configured a custom results page or changed behavior of search in other ways.</span></span>

> [!NOTE]
> <span data-ttu-id="07882-141">Para poder fazer essa alteração, você precisa permitir a execução de scripts personalizados no site em questão como um administrador de locatários, que não é permitido por padrão.</span><span class="sxs-lookup"><span data-stu-id="07882-141">To be able to make this change, you need to allow running custom scripts on the site in question as a tenant administrator, which is disallowed by default.</span></span> <span data-ttu-id="07882-142">Confira os https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script detalhes.</span><span class="sxs-lookup"><span data-stu-id="07882-142">Please see https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script for details.</span></span> <span data-ttu-id="07882-143">Você pode permitir a execução de scripts personalizados, fazer a alteração e, em seguida, reverter para não permitir scripts para o site, se necessário.</span><span class="sxs-lookup"><span data-stu-id="07882-143">You can allow running custom scripts, make the change, and then revert to disallowing scripts for the site if necessary.</span></span>

<span data-ttu-id="07882-144">Para alterar essa configuração para um determinado site, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="07882-144">To change this setting for a given site run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="07882-145">Como alternativa, se você quiser defini-lo para todos os sites em um conjunto de sites, poderá usar este comando:</span><span class="sxs-lookup"><span data-stu-id="07882-145">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

<span data-ttu-id="07882-146">Para voltar ao texto do espaço reservado padrão, defina o valor como em branco ("").</span><span class="sxs-lookup"><span data-stu-id="07882-146">To go back to the default placeholder text, set the value to be blank ("").</span></span>
