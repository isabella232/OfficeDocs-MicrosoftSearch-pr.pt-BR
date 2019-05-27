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
description: Use consultas de pesquisa do SharePoint para criar resultados de trabalho para a Pesquisa da Microsoft
ms.openlocfilehash: 6e55e2000792bdb576a18a0efeb353dc3ea13605
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968448"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="4e979-103">Importar resultados promovidos e principais consultas do SharePoint</span><span class="sxs-lookup"><span data-stu-id="4e979-103">Import SharePoint promoted results and top queries</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e979-104">As configurações da Pesquisa da Microsoft no Bing agora estão disponíveis no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e979-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="4e979-105">Comece por [atribuir administradores de pesquisa](https://docs.microsoft.com/pt-BR/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) ao seu centro de administração.</span><span class="sxs-lookup"><span data-stu-id="4e979-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="4e979-106">Para aproveitar as consultas dos usuários e as Melhores Opções que você criou no SharePoint, a Pesquisa da Microsoft inclui duas ferramentas para importar essas informações como indicadores sugeridos:</span><span class="sxs-lookup"><span data-stu-id="4e979-106">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="4e979-107">Importar regras de consulta de resultados promovidos do SharePoint</span><span class="sxs-lookup"><span data-stu-id="4e979-107">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="4e979-108">Importe essas regras, anteriormente chamadas Best Bets, como indicadores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="4e979-108">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="4e979-109">Para disponibilizá-las aos seus usuários, você pode publicá-las.</span><span class="sxs-lookup"><span data-stu-id="4e979-109">To make them available to your users, publish them.</span></span> <span data-ttu-id="4e979-110">O tempo de publicação varia de acordo com o número de marcadores que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="4e979-110">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="4e979-111">Importar as consultas do SharePoint usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e979-111">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="4e979-112">Baixe as principais consultas a partir do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4e979-112">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="4e979-113">O script do PowerShell solicitará suas credenciais de administrador do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4e979-113">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="4e979-114">Execute uma pesquisa do SharePoint para cada uma das principais consultas para obter o maior resultado de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="4e979-114">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="4e979-115">Adicione indicadores sugeridos ao portal de administração.</span><span class="sxs-lookup"><span data-stu-id="4e979-115">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="4e979-116">As principais consultas do SharePoint são ótimas candidatas a indicadores.</span><span class="sxs-lookup"><span data-stu-id="4e979-116">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="4e979-117">Use o script do PowerShell para importá-las como indicadores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="4e979-117">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="4e979-118">Use este script:</span><span class="sxs-lookup"><span data-stu-id="4e979-118">This script will:</span></span>
    
<span data-ttu-id="4e979-119">Para saber mais sobre requisitos, exemplos e parâmetros disponíveis, baixe o script e revise o arquivo Leiame.</span><span class="sxs-lookup"><span data-stu-id="4e979-119">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="4e979-120">Após a execução do script do PowerShell, um administrador ou o editor deverá revisar os indicadores sugeridos e fazer as edições necessárias antes que eles sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="4e979-120">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

