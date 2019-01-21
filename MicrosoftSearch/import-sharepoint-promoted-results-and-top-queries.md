---
title: Importação SharePoint promovidos principais consultas e resultados
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
description: Use as consultas de pesquisa do SharePoint para criar resultados de trabalho para o Microsoft Search
ms.openlocfilehash: f4fa4354fed667800c1cdcf63c86f59d736c342a
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378406"
---
# <a name="import-sharepoint-promoted-results-and-top-queries"></a><span data-ttu-id="d8a92-103">Importação SharePoint promovidos principais consultas e resultados</span><span class="sxs-lookup"><span data-stu-id="d8a92-103">Import SharePoint promoted results and top queries</span></span>

<span data-ttu-id="d8a92-104">Para aproveitar as melhores opções que você criou no SharePoint e consultas dos usuários, o Microsoft Search inclui duas ferramentas para importar estas informações como indicadores sugeridas:</span><span class="sxs-lookup"><span data-stu-id="d8a92-104">To leverage users' queries and Best Bets you've created in SharePoint, Microsoft Search includes two tools to import this information as suggested bookmarks:</span></span> 
  
## <a name="import-sharepoint-promoted-result-query-rules"></a><span data-ttu-id="d8a92-105">Importação SharePoint promovidos regras de consulta de resultados</span><span class="sxs-lookup"><span data-stu-id="d8a92-105">Import SharePoint promoted result query rules</span></span>

<span data-ttu-id="d8a92-p101">Importe essas regras, anteriormente denominada melhores opções, como indicadores sugeridas. Para torná-los disponíveis para seus usuários, publicá-los. Tempo de publicação varia de acordo com o número de indicadores que você selecionar.</span><span class="sxs-lookup"><span data-stu-id="d8a92-p101">Import these rules, previously called Best Bets, as suggested bookmarks. To make them available to your users, publish them. Publishing time varies based on the number of bookmarks you select.</span></span>
  
## <a name="import-top-sharepoint-queries-using-powershell"></a><span data-ttu-id="d8a92-109">Importar principais consultas do SharePoint usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d8a92-109">Import top SharePoint queries using PowerShell</span></span>

- <span data-ttu-id="d8a92-p102">Baixe as principais consultas a partir do SharePoint. O script do PowerShell solicitará suas credenciais de administrador do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d8a92-p102">Download the top queries from your SharePoint. The PowerShell script will prompt you for your SharePoint administrator credentials.</span></span>
    
- <span data-ttu-id="d8a92-112">Execute uma pesquisa do SharePoint para cada um dos principais consultas para obter o resultado de pesquisa principais.</span><span class="sxs-lookup"><span data-stu-id="d8a92-112">Run a SharePoint search for each of the top queries to get the top search result.</span></span>
    
- <span data-ttu-id="d8a92-113">Adicione indicadores sugeridos para o portal de administração.</span><span class="sxs-lookup"><span data-stu-id="d8a92-113">Add suggested bookmarks to the Admin portal.</span></span>
    
- <span data-ttu-id="d8a92-p103">Seus principais consultas do SharePoint são excelentes candidatos para indicadores. Use o script do PowerShell para importá-los como marcadores sugeridas. Esse script será:</span><span class="sxs-lookup"><span data-stu-id="d8a92-p103">Your top SharePoint queries are excellent candidates for bookmarks. Use the PowerShell script to import them as suggested bookmarks. This script will:</span></span>
    
<span data-ttu-id="d8a92-p104">Para obter informações sobre requisitos, exemplos e parâmetros disponíveis, baixe o script e revise o arquivo README. Após o script do PowerShell é executado, um administrador ou um editor deve revisar os indicadores sugeridos e faça qualquer edições de necessárias antes que eles estão publicados.</span><span class="sxs-lookup"><span data-stu-id="d8a92-p104">For information about requirements, examples, and available parameters, download the script and review the README file. After the PowerShell script runs, an admin or editor should review the suggested bookmarks and make any necessary edits before they're published.</span></span>

  

