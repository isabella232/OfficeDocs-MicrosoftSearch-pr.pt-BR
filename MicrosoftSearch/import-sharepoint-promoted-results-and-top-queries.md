---
title: Importar resultados promovidos e principais consultas do SharePoint
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 9/8/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 3d2a1498-174e-4214-9cf1-8b58cce5a872
ROBOTS: NOINDEX
description: Use consultas de pesquisa do SharePoint para criar resultados de trabalho para a Pesquisa da Microsoft
ms.openlocfilehash: 1538c57a7b4138b36fe62e3076feb58d746b2b3e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591598"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="d4f46-103">Importar resultados promovidos e principais consultas do SharePoint</span><span class="sxs-lookup"><span data-stu-id="d4f46-103">Import SharePoint promoted results and top queries</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d4f46-104">Este artigo se aplica à Pesquisa do Microsoft no portal de administração do Bing.</span><span class="sxs-lookup"><span data-stu-id="d4f46-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="d4f46-105">Estamos movendo o portal para o centro de administração do Microsoft 365 e, posteriormente, ele será removido.</span><span class="sxs-lookup"><span data-stu-id="d4f46-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="d4f46-106">Recomendamos que você use o centro de administração do Microsoft 365 para começar.</span><span class="sxs-lookup"><span data-stu-id="d4f46-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> [<span data-ttu-id="d4f46-107">Visão geral da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d4f46-107">Overview of Microsoft Search</span></span>](overview-microsoft-search.md)
    
<span data-ttu-id="d4f46-108">Para aproveitar as consultas dos usuários e as Melhores Opções que você criou no SharePoint, a Pesquisa da Microsoft inclui duas ferramentas para importar essas informações como indicadores sugeridos:</span><span class="sxs-lookup"><span data-stu-id="d4f46-108">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="d4f46-109">Importar regras de consulta de resultados promovidos do SharePoint</span><span class="sxs-lookup"><span data-stu-id="d4f46-109">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="d4f46-110">Importe essas regras, anteriormente chamadas Best Bets, como indicadores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="d4f46-110">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="d4f46-111">Para disponibilizá-las aos seus usuários, você pode publicá-las.</span><span class="sxs-lookup"><span data-stu-id="d4f46-111">To make them available to your users, publish them.</span></span> <span data-ttu-id="d4f46-112">O tempo de publicação varia de acordo com o número de marcadores que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="d4f46-112">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="d4f46-113">Importar as consultas do SharePoint usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4f46-113">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="d4f46-114">Baixe as principais consultas a partir do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d4f46-114">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="d4f46-115">O script do PowerShell solicitará suas credenciais de administrador do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d4f46-115">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="d4f46-116">Execute uma pesquisa do SharePoint para cada uma das principais consultas para obter o maior resultado de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d4f46-116">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="d4f46-117">Adicione indicadores sugeridos ao portal de administração.</span><span class="sxs-lookup"><span data-stu-id="d4f46-117">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="d4f46-118">As principais consultas do SharePoint são ótimas candidatas a indicadores.</span><span class="sxs-lookup"><span data-stu-id="d4f46-118">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="d4f46-119">Use o script do PowerShell para importá-las como indicadores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="d4f46-119">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="d4f46-120">Use este script:</span><span class="sxs-lookup"><span data-stu-id="d4f46-120">This script will:</span></span>
    
<span data-ttu-id="d4f46-121">Para saber mais sobre requisitos, exemplos e parâmetros disponíveis, baixe o script e revise o arquivo Leiame.</span><span class="sxs-lookup"><span data-stu-id="d4f46-121">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="d4f46-122">Após a execução do script do PowerShell, um administrador ou o editor deverá revisar os indicadores sugeridos e fazer as edições necessárias antes que eles sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="d4f46-122">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

