---
title: Criar locais em massa
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 15c9fada-f7a6-4210-aa6b-028b32217830
description: Adicionar vários locais de uma só vez com as ferramentas de importação para o portal de administração de pesquisa da Microsoft
ms.openlocfilehash: eb51b93ceaa560e5142ac46d316ba745c614fe34
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068407"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="24477-103">Criar locais em massa</span><span class="sxs-lookup"><span data-stu-id="24477-103">Bulk create locations</span></span>

<span data-ttu-id="24477-104">Baixe e use o modelo. csv para criar, editar e salvar locais em massa.</span><span class="sxs-lookup"><span data-stu-id="24477-104">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="24477-105">No canto superior direito da seção locais, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="24477-105">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="24477-106">Clique em **baixar locais modelo (. csv)**</span><span class="sxs-lookup"><span data-stu-id="24477-106">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="24477-107">Salve e abra o arquivo. csv</span><span class="sxs-lookup"><span data-stu-id="24477-107">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="24477-108">Adicione o conteúdo do local e salve o arquivo</span><span class="sxs-lookup"><span data-stu-id="24477-108">Add the location content and save the file</span></span>
    
5. <span data-ttu-id="24477-109">No canto superior direito da seção locais, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="24477-109">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="24477-110">No painel importar locais, clique em **procurar** e navegue até o arquivo. csv que você deseja importar</span><span class="sxs-lookup"><span data-stu-id="24477-110">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="24477-111">Clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="24477-111">Click **Import**</span></span>

<span data-ttu-id="24477-p101">Os campos nos modelos de importação e exportação de locais são os mesmos. Você pode exportar, editar em massa e importar as edições ou começar com um modelo vazio para criar novos locais em massa. Para editar em massa locais existentes, exportá-los do portal de administração, fazer as edições necessárias e importá-las.</span><span class="sxs-lookup"><span data-stu-id="24477-p101">The fields in the import and export locations templates are the same. You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations. To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="24477-115">Impedir erros de importação</span><span class="sxs-lookup"><span data-stu-id="24477-115">Prevent import errors</span></span>  
<span data-ttu-id="24477-p102">Você receberá um erro se os dados necessários estiverem ausentes ou forem inválidos. Dependendo do erro, um arquivo de log pode ser gerado com mais informações sobre as linhas e colunas que precisam ser corrigidas. Faça as edições necessárias e tente importar o arquivo novamente.</span><span class="sxs-lookup"><span data-stu-id="24477-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="24477-119">Até que todos os erros sejam resolvidos, não será possível criar ou editar nenhum local.</span><span class="sxs-lookup"><span data-stu-id="24477-119">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="24477-120">Para ajudar a evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente:</span><span class="sxs-lookup"><span data-stu-id="24477-120">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="24477-121">Inclui a linha de cabeçalho que estava no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="24477-121">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="24477-122">Inclui todas as colunas que estavam no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="24477-122">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="24477-123">A ordem da coluna é o mesmo que o modelo de importação</span><span class="sxs-lookup"><span data-stu-id="24477-123">The column order is the same as the import template</span></span>
- <span data-ttu-id="24477-124">Essas colunas podem estar vazias: ID, última modificação, última modificação, e lat/long</span><span class="sxs-lookup"><span data-stu-id="24477-124">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="24477-125">Tentaremos determinar lat/long com base no endereço se esse campo estiver vazio</span><span class="sxs-lookup"><span data-stu-id="24477-125">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="24477-126">A coluna de estado não pode ficar vazia, essas informações são necessárias</span><span class="sxs-lookup"><span data-stu-id="24477-126">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="24477-127">Com base no campo Estado, os locais serão salvos como rascunho, sugerido, agendado ou serão publicados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="24477-127">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="24477-128">Além disso, se você incluir a ID de um local existente, ele será substituído pelas informações no arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="24477-128">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="24477-p103">Para organizações com vários locatários, você pode exportar seus locais de um locatário e importá-los para outro. Mas você deve remover todos os dados na coluna ID antes de importar.</span><span class="sxs-lookup"><span data-stu-id="24477-p103">For organizations with mulitple tenants, you can export your locations from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="24477-131">Para saber mais sobre os campos obrigatórios e recomendados, confira [Adicionar um local](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="24477-131">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

