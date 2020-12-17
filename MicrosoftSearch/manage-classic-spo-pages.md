---
title: Páginas clássicas no SharePoint Online e no Microsoft Search
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
description: Usando o Microsoft Search em páginas clássicas do SharePoint
ms.openlocfilehash: 605e63a30ad166c63320c7e89e1b2745e628e15d
ms.sourcegitcommit: c5fe4e01403379b3ee7ea4dbded8b31696311d79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49700969"
---
# <a name="classic-pages-and-microsoft-search"></a><span data-ttu-id="a0089-103">Páginas clássicas e pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a0089-103">Classic pages and Microsoft Search</span></span>

<span data-ttu-id="a0089-104">Os sites do SharePoint criados antes de sites modernos usam uma caixa de pesquisa clássica e uma experiência de resultados de pesquisa clássica.</span><span class="sxs-lookup"><span data-stu-id="a0089-104">SharePoint sites created prior to modern sites use a classic search box and classic search results experience.</span></span> <span data-ttu-id="a0089-105">Iremos distribuir um recurso que usará as páginas clássicas padrão para começar a usar a experiência de pesquisa moderna que usa a pesquisa da Microsoft, que fornece resultados personalizados com maior relevância.</span><span class="sxs-lookup"><span data-stu-id="a0089-105">We will be rolling out a feature that will default classic pages to start using the modern search experience that uses Microsoft Search, which provides personalized results with higher relevance.</span></span>

<span data-ttu-id="a0089-106">O uso da pesquisa da Microsoft é recomendado para todos os sites, incluindo o clássico, mas se seus sites clássicos usarem páginas mestras personalizadas e/ou se você tiver personalizado sua experiência de resultados de pesquisa clássica, iremos detectar automaticamente essas personalizações e não mudar para o Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="a0089-106">Using Microsoft Search is recommended for all sites, including classic, but if your classic sites use custom master pages and/or you have customized your classic search results experience, we will auto-detect these customizations and not switch to Microsoft Search.</span></span>

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a><span data-ttu-id="a0089-107">Sites clássicos que mudarão automaticamente para a pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a0089-107">Classic sites that will automatically switch to Microsoft Search</span></span>

<span data-ttu-id="a0089-108">Os sites clássicos começarão a usar o Microsoft Search se todos os itens a seguir forem verdadeiros.</span><span class="sxs-lookup"><span data-stu-id="a0089-108">Classic sites will start using Microsoft Search if all of the following are true.</span></span>

* <span data-ttu-id="a0089-109">O site é baseado no modelo de site de equipe (como STS # 0 e STS # 1).</span><span class="sxs-lookup"><span data-stu-id="a0089-109">The site is based on the team site template (like STS#0 and STS#1).</span></span>
* <span data-ttu-id="a0089-110">O site não tem o recurso publicação ativado.</span><span class="sxs-lookup"><span data-stu-id="a0089-110">The site does not have the publishing feature turned on.</span></span>
* <span data-ttu-id="a0089-111">O site não usa uma página mestra personalizada (uma página mestra diferente de Oslo. Master ou Seattle. Master).</span><span class="sxs-lookup"><span data-stu-id="a0089-111">The site does not use a custom master page (a different master page than oslo.master or seattle.master).</span></span>
* <span data-ttu-id="a0089-112">Não há nenhuma regra de consulta ativa além daquelas que adicionam resultados promovidos para o site, o conjunto de sites ou o locatário na fonte de resultados padrão.</span><span class="sxs-lookup"><span data-stu-id="a0089-112">There are no active query rules other than those adding promoted results for the site, site collection or tenant on the default result source.</span></span>
* <span data-ttu-id="a0089-113">Não há tipos de resultados personalizados para o site ou o conjunto de sites na fonte de resultados padrão.</span><span class="sxs-lookup"><span data-stu-id="a0089-113">There are no custom result types for the site or the site collection on the default result source.</span></span>
* <span data-ttu-id="a0089-114">O site ou o conjunto de sites no qual ele faz parte não foi recusado usando a configuração SearchBoxInNavBar descrita abaixo.</span><span class="sxs-lookup"><span data-stu-id="a0089-114">The site or the site collection it is part of has not opted out of the switch using the SearchBoxInNavBar setting described below.</span></span>

<span data-ttu-id="a0089-115">Após a mudança para o Microsoft Search, as páginas clássicas no site começarão a mostrar a caixa de pesquisa na barra de navegação do pacote e removerá a caixa de pesquisa clássica da página.</span><span class="sxs-lookup"><span data-stu-id="a0089-115">After the switch to Microsoft Search, classic pages in the site will start to show the search box in the suite navigation bar and remove the classic search box from the page.</span></span> <span data-ttu-id="a0089-116">Assim, quando um usuário procurar um termo, os resultados serão exibidos usando a experiência de pesquisa moderna do Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="a0089-116">Then, when a user searches for a term, the results will be displayed using the modern search experience of Microsoft Search.</span></span>

## <a name="staying-with-the-classic-search-experience"></a><span data-ttu-id="a0089-117">Manter a experiência de pesquisa clássica</span><span class="sxs-lookup"><span data-stu-id="a0089-117">Staying with the classic search experience</span></span>

<span data-ttu-id="a0089-118">Se seu site atender aos critérios listados acima, mas você não quiser que ele mude para a experiência de pesquisa da Microsoft, você pode optar por usar os seguintes comandos, como o proprietário do site ou do conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="a0089-118">If your site meets the criteria listed above, but you do not want it to switch to the Microsoft Search experience, you can opt out using the following commands, as the site or site collection owner.</span></span>

<span data-ttu-id="a0089-119">Você pode usar esse comando a qualquer momento, antes ou depois que a mudança ocorrer, portanto, é fácil voltar para a experiência de pesquisa que você tinha anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a0089-119">You can use this command at any time, before or after the switch happens, so it is easy to go back to the search experience you had previously.</span></span>

<span data-ttu-id="a0089-120">Para executar os comandos abaixo, você usará o PowerShell com as extensões do PowerShell PnP do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="a0089-120">To run the commands below, you will use PowerShell with SharePoint PnP PowerShell extensions.</span></span> <span data-ttu-id="a0089-121">Você pode instalar e saber mais sobre como começar [aqui](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="a0089-121">You can install and learn more about how to get started [here](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps).</span></span> <span data-ttu-id="a0089-122">Você entrará no site ou no conjunto de sites usando este comando:</span><span class="sxs-lookup"><span data-stu-id="a0089-122">You will sign into your site or site collection using this command:</span></span>

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials
```

<span data-ttu-id="a0089-123">Para manter a experiência de pesquisa clássica para um site, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a0089-123">To stay with classic search experience for a site, run the following command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

<span data-ttu-id="a0089-124">Como alternativa, se você quiser defini-lo para todos os sites em um conjunto de sites, poderá usar este comando:</span><span class="sxs-lookup"><span data-stu-id="a0089-124">Alternately, if you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a><span data-ttu-id="a0089-125">Optando pela pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="a0089-125">Opting into Microsoft Search</span></span>

<span data-ttu-id="a0089-126">Para os sites que não atendem aos critérios listados acima ou para sites específicos em um conjunto de sites que optou por permanecer no Classic, você pode habilitar manualmente a experiência de pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a0089-126">For those sites that do not meet the criteria listed above, or for specific sites in a site collection that opted to stay in classic, you can manually enable the Microsoft Search experience.</span></span>

<span data-ttu-id="a0089-127">Para alterar essa configuração para um site específico, você pode usar este comando:</span><span class="sxs-lookup"><span data-stu-id="a0089-127">To change this setting for a specific site, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

<span data-ttu-id="a0089-128">Se quiser defini-lo para todos os sites em um conjunto de sites, você pode usar este comando:</span><span class="sxs-lookup"><span data-stu-id="a0089-128">If you want to set it for all the sites in a site collection, you can use this command:</span></span>

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> <span data-ttu-id="a0089-129">Você pode habilitar manualmente a pesquisa da Microsoft para um site de equipe ou site de publicação (IDs de modelo que contenham "STS", "CMSPUBLISHING", "BLANKINTERNET" e "GROUP").</span><span class="sxs-lookup"><span data-stu-id="a0089-129">You can manually enable Microsoft Search only for a Team Site or Publishing Site (template ids that contain "STS", "CMSPUBLISHING", "BLANKINTERNET" and "GROUP").</span></span>
