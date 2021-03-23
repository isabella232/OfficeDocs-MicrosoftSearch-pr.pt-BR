---
title: Páginas clássicas no SharePoint Online e na Pesquisa da Microsoft
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
description: Usando a Pesquisa da Microsoft em páginas clássicas do SharePoint
ms.openlocfilehash: 33215c730d34c14f8ce1d55e93730615688f1e2a
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031427"
---
# <a name="classic-pages-and-microsoft-search"></a><span data-ttu-id="1995f-103">Páginas clássicas e Pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1995f-103">Classic pages and Microsoft Search</span></span>

<span data-ttu-id="1995f-104">Os sites do SharePoint criados antes dos sites modernos usam uma caixa de pesquisa clássica e uma experiência clássica de resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1995f-104">SharePoint sites created prior to modern sites use a classic search box and classic search results experience.</span></span> <span data-ttu-id="1995f-105">Vamos lançar um recurso que irá padrão de páginas clássicas para começar a usar a experiência de pesquisa moderna que usa a Pesquisa da Microsoft, que fornece resultados personalizados com maior relevância.</span><span class="sxs-lookup"><span data-stu-id="1995f-105">We will be rolling out a feature that will default classic pages to start using the modern search experience that uses Microsoft Search, which provides personalized results with higher relevance.</span></span>

<span data-ttu-id="1995f-106">O uso da Pesquisa da Microsoft é recomendado para todos os sites, incluindo clássicos, mas se seus sites clássicos usarem páginas mestras personalizadas e/ou você tiver personalizado sua experiência clássica de resultados de pesquisa, detectaremos automaticamente essas personalizações e não mudaremos para a Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1995f-106">Using Microsoft Search is recommended for all sites, including classic, but if your classic sites use custom master pages and/or you have customized your classic search results experience, we will auto-detect these customizations and not switch to Microsoft Search.</span></span>

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a><span data-ttu-id="1995f-107">Sites clássicos que alternarão automaticamente para a Pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1995f-107">Classic sites that will automatically switch to Microsoft Search</span></span>

<span data-ttu-id="1995f-108">Sites clássicos começarão a usar a Pesquisa da Microsoft se todos os seguintes são verdadeiros:</span><span class="sxs-lookup"><span data-stu-id="1995f-108">Classic sites will start using Microsoft Search if all of the following are true:</span></span>

* <span data-ttu-id="1995f-109">O site se baseia no modelo de site de equipe (como STS#0 e STS#1).</span><span class="sxs-lookup"><span data-stu-id="1995f-109">The site is based on the team site template (like STS#0 and STS#1).</span></span>
* <span data-ttu-id="1995f-110">O site não tem o recurso de publicação ligado.</span><span class="sxs-lookup"><span data-stu-id="1995f-110">The site does not have the publishing feature turned on.</span></span>
* <span data-ttu-id="1995f-111">O site não usa uma página mestra personalizada (uma página mestra diferente de oslo.master ou seattle.master).</span><span class="sxs-lookup"><span data-stu-id="1995f-111">The site does not use a custom master page (a different master page than oslo.master or seattle.master).</span></span>
* <span data-ttu-id="1995f-112">Não há regras de consulta ativas que não sejam aquelas que adicionam resultados promovidos para o site, conjunto de sites ou locatário na fonte de resultados padrão.</span><span class="sxs-lookup"><span data-stu-id="1995f-112">There are no active query rules other than those adding promoted results for the site, site collection or tenant on the default result source.</span></span>
* <span data-ttu-id="1995f-113">Não há tipos de resultados personalizados para o site ou o conjunto de sites na fonte de resultados padrão.</span><span class="sxs-lookup"><span data-stu-id="1995f-113">There are no custom result types for the site or the site collection on the default result source.</span></span>
* <span data-ttu-id="1995f-114">O site ou o conjunto de sites não é optado pela opção usando a *configuração SearchBoxInNavBar* descrita abaixo.</span><span class="sxs-lookup"><span data-stu-id="1995f-114">The site or the site collection is not opted out of the switch using the *SearchBoxInNavBar* setting described below.</span></span>

<span data-ttu-id="1995f-115">Após a mudança para a Pesquisa da Microsoft, as páginas clássicas no site começarão a mostrar a caixa de pesquisa na barra de navegação do pacote e removerão a caixa de pesquisa clássica da página.</span><span class="sxs-lookup"><span data-stu-id="1995f-115">After the switch to Microsoft Search, classic pages in the site will start to show the search box in the suite navigation bar and remove the classic search box from the page.</span></span> <span data-ttu-id="1995f-116">Em seguida, quando um usuário pesquisa um termo, os resultados serão exibidos usando a experiência de pesquisa moderna da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1995f-116">Then, when a user searches for a term, the results will be displayed using the modern search experience of Microsoft Search.</span></span>

## <a name="staying-with-the-classic-search-experience"></a><span data-ttu-id="1995f-117">Permanecendo com a experiência de pesquisa clássica</span><span class="sxs-lookup"><span data-stu-id="1995f-117">Staying with the classic search experience</span></span>

<span data-ttu-id="1995f-118">Se seu site atender aos critérios listados acima, mas você não quiser que ele alterne para a experiência de Pesquisa da Microsoft, você pode optar por usar os seguintes comandos, como o proprietário do site ou do conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="1995f-118">If your site meets the criteria listed above, but you do not want it to switch to the Microsoft Search experience, you can opt out using the following commands, as the site or site collection owner.</span></span>

<span data-ttu-id="1995f-119">Você pode usar esse comando a qualquer momento, antes ou depois que a opção acontecer, portanto, é fácil voltar à experiência de pesquisa que você tinha anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1995f-119">You can use this command at any time, before or after the switch happens, so it is easy to go back to the search experience you had previously.</span></span>

<span data-ttu-id="1995f-120">Para executar os comandos abaixo, você usará o PowerShell com extensões pnP do PowerShell do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="1995f-120">To run the commands below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="1995f-121">Você pode instalar e saber mais sobre como começar [aqui](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="1995f-121">You can install and learn more about how to get started [here](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="1995f-122">Você fará login no seu site ou conjunto de sites usando este comando:</span><span class="sxs-lookup"><span data-stu-id="1995f-122">You will sign in to your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

<span data-ttu-id="1995f-123">Para manter a experiência de pesquisa clássica para um site, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="1995f-123">To stay with classic search experience for a site, run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

<span data-ttu-id="1995f-124">Alternativamente, se você quiser defini-lo para todos os sites em um conjunto de sites, você pode usar este comando:</span><span class="sxs-lookup"><span data-stu-id="1995f-124">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a><span data-ttu-id="1995f-125">Opting into Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="1995f-125">Opting into Microsoft Search</span></span>

<span data-ttu-id="1995f-126">Para os sites que não atendem aos critérios listados acima ou para sites específicos em um conjunto de sites que optaram por permanecer no clássico, você pode habilitar manualmente a experiência da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1995f-126">For those sites that do not meet the criteria listed above, or for specific sites in a site collection that opted to stay in classic, you can manually enable the Microsoft Search experience.</span></span>

<span data-ttu-id="1995f-127">Para alterar essa configuração para um site específico, você pode usar este comando:</span><span class="sxs-lookup"><span data-stu-id="1995f-127">To change this setting for a specific site, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

<span data-ttu-id="1995f-128">Se você quiser defini-lo para todos os sites em um conjunto de sites, use este comando:</span><span class="sxs-lookup"><span data-stu-id="1995f-128">If you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> <span data-ttu-id="1995f-129">Você pode habilitar manualmente a Pesquisa da Microsoft somente para um Site de Equipe ou Site de Publicação (ids de modelo que contenham "STS", "CMSPUBLISHING", "BLANKINTERNET" e "GROUP").</span><span class="sxs-lookup"><span data-stu-id="1995f-129">You can manually enable Microsoft Search only for a Team Site or Publishing Site (template ids that contain "STS", "CMSPUBLISHING", "BLANKINTERNET" and "GROUP").</span></span>