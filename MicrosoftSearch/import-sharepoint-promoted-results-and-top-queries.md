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
description: Usar consultas de pesquisa do SharePoint para criar resultados de trabalho para o Microsoft Search
ms.openlocfilehash: f4fa4354fed667800c1cdcf63c86f59d736c342a
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508750"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="cf807-103">Importar resultados promovidos e principais consultas do SharePoint</span><span class="sxs-lookup"><span data-stu-id="cf807-103">Import SharePoint promoted results and top queries</span></span>

<span data-ttu-id="cf807-104">Para aproveitar as consultas dos usuários e as melhores opções criadas no SharePoint, o Microsoft Search inclui duas ferramentas para importar essas informações como indicadores sugeridos:</span><span class="sxs-lookup"><span data-stu-id="cf807-104">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="cf807-105">Importar regras de consulta de resultados promovidos do SharePoint</span><span class="sxs-lookup"><span data-stu-id="cf807-105">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="cf807-106">Importe essas regras, anteriormente chamadas de melhores opções, como indicadores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="cf807-106">Import these rules, previously called Best Bets, as suggested bookmarks.</span></span> <span data-ttu-id="cf807-107">Para disponibilizá-los aos usuários, publique-os.</span><span class="sxs-lookup"><span data-stu-id="cf807-107">To make them available to your users, publish them.</span></span> <span data-ttu-id="cf807-108">O tempo de publicação varia com base no número de marcadores selecionados.</span><span class="sxs-lookup"><span data-stu-id="cf807-108">Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="cf807-109">Importar as principais consultas do SharePoint usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="cf807-109">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="cf807-110">Baixe as principais consultas do seu SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cf807-110">Download the top queries from your SharePoint.</span></span> <span data-ttu-id="cf807-111">O script do PowerShell solicitará suas credenciais de administrador do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="cf807-111">The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="cf807-112">Execute uma pesquisa do SharePoint para cada uma das principais consultas para obter o resultado da pesquisa principal.</span><span class="sxs-lookup"><span data-stu-id="cf807-112">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="cf807-113">Adicione indicadores sugeridos ao portal de administração.</span><span class="sxs-lookup"><span data-stu-id="cf807-113">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="cf807-114">Suas principais consultas do SharePoint são excelentes candidatos para indicadores.</span><span class="sxs-lookup"><span data-stu-id="cf807-114">Your top SharePoint queries are excellent candidates for bookmarks.</span></span> <span data-ttu-id="cf807-115">Use o script do PowerShell para importá-los como indicadores sugeridos.</span><span class="sxs-lookup"><span data-stu-id="cf807-115">Use the PowerShell script to import them as suggested bookmarks.</span></span> <span data-ttu-id="cf807-116">Este script irá:</span><span class="sxs-lookup"><span data-stu-id="cf807-116">This script will:</span></span>
    
<span data-ttu-id="cf807-117">Para obter informações sobre requisitos, exemplos e parâmetros disponíveis, baixe o script e revise o arquivo LEIAme.</span><span class="sxs-lookup"><span data-stu-id="cf807-117">For information about requirements, examples, and available parameters, download the script and review the README file.</span></span> <span data-ttu-id="cf807-118">Após a execução do script do PowerShell, um administrador ou editor deve revisar os indicadores sugeridos e fazer as edições necessárias antes que sejam publicados.</span><span class="sxs-lookup"><span data-stu-id="cf807-118">After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

