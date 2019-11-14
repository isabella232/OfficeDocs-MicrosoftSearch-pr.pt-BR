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
ROBOTS: NoIndex
description: Adicionar vários locais de uma só vez com as ferramentas de importação para o portal de administração de pesquisa da Microsoft
ms.openlocfilehash: e01c3774439a931dc81f850d8cbee76cc6128a53
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311337"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="d88b1-103">Criar locais em massa</span><span class="sxs-lookup"><span data-stu-id="d88b1-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d88b1-104">Este artigo se aplica à Pesquisa da Microsoft no portal de administração do Bing.</span><span class="sxs-lookup"><span data-stu-id="d88b1-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="d88b1-105">Estamos movendo o portal para o centro de administração do Microsoft 365 e, em seguida, a Pesquisa da Microsoft no portal do Bing será removida.</span><span class="sxs-lookup"><span data-stu-id="d88b1-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="d88b1-106">Recomendamos que você use o centro de administração do Microsoft 365 para começar.</span><span class="sxs-lookup"><span data-stu-id="d88b1-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="d88b1-107">[Visão geral da Pesquisa da Microsoft.](overview-microsoft-search.md)</span><span class="sxs-lookup"><span data-stu-id="d88b1-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="d88b1-108">Baixe e use o modelo. csv para criar, editar e salvar locais em massa.</span><span class="sxs-lookup"><span data-stu-id="d88b1-108">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="d88b1-109">No canto superior direito da seção locais, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="d88b1-109">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="d88b1-110">Clique em **baixar locais modelo (. csv)**</span><span class="sxs-lookup"><span data-stu-id="d88b1-110">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="d88b1-111">Salve e abra o arquivo .csv</span><span class="sxs-lookup"><span data-stu-id="d88b1-111">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="d88b1-112">Adicione o conteúdo do local e salve o arquivo</span><span class="sxs-lookup"><span data-stu-id="d88b1-112">Add the location content and save the file</span></span>

    <span data-ttu-id="d88b1-113">O arquivo .csv deve ser salvo como um arquivo CSV UTF-8; outros tipos de arquivo e/ou codificações podem causar erros de importação</span><span class="sxs-lookup"><span data-stu-id="d88b1-113">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="d88b1-114">No canto superior direito da seção locais, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="d88b1-114">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="d88b1-115">No painel importar locais, clique em **procurar** e navegue até o arquivo. csv que você deseja importar</span><span class="sxs-lookup"><span data-stu-id="d88b1-115">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="d88b1-116">Clique em **Importar**</span><span class="sxs-lookup"><span data-stu-id="d88b1-116">Click **Import**</span></span>

<span data-ttu-id="d88b1-117">Os campos nos modelos de importação e exportação de locais são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="d88b1-117">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="d88b1-118">Você pode exportar, editar em massa e importar as edições ou começar com um modelo vazio para criar novos locais em massa.</span><span class="sxs-lookup"><span data-stu-id="d88b1-118">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="d88b1-119">Para editar em massa locais existentes, exportá-los do portal de administração, fazer as edições necessárias e importá-las.</span><span class="sxs-lookup"><span data-stu-id="d88b1-119">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="d88b1-120">Evite erros de importação</span><span class="sxs-lookup"><span data-stu-id="d88b1-120">Prevent import errors</span></span>  
<span data-ttu-id="d88b1-121">Se os dados necessários estiverem ausentes ou forem inválidos, você receberá um erro.</span><span class="sxs-lookup"><span data-stu-id="d88b1-121">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="d88b1-122">Dependendo do erro, pode ser gerado um arquivo de registro com mais informações sobre quais linhas e colunas precisam ser corrigidas.</span><span class="sxs-lookup"><span data-stu-id="d88b1-122">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="d88b1-123">Faça as edições necessárias e tente importar o arquivo novamente.</span><span class="sxs-lookup"><span data-stu-id="d88b1-123">Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d88b1-124">Até que todos os erros sejam resolvidos, não será possível criar ou editar nenhum local.</span><span class="sxs-lookup"><span data-stu-id="d88b1-124">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="d88b1-125">Para ajudar a evitar erros, verifique se o arquivo de importação está formatado corretamente:</span><span class="sxs-lookup"><span data-stu-id="d88b1-125">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="d88b1-126">Inclui a linha de cabeçalho que estava no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="d88b1-126">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="d88b1-127">Inclui todas as colunas que estavam no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="d88b1-127">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="d88b1-128">A ordem das colunas é igual ao modelo de importação</span><span class="sxs-lookup"><span data-stu-id="d88b1-128">The column order is the same as the import template</span></span>
- <span data-ttu-id="d88b1-129">Essas colunas podem estar vazias: ID, última modificação, última modificação, e lat/long</span><span class="sxs-lookup"><span data-stu-id="d88b1-129">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="d88b1-130">Tentaremos determinar lat/long com base no endereço se esse campo estiver vazio</span><span class="sxs-lookup"><span data-stu-id="d88b1-130">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="d88b1-131">A coluna Estado não pode estar vazia, essa informação é necessária</span><span class="sxs-lookup"><span data-stu-id="d88b1-131">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="d88b1-132">Com base no campo Estado, os locais serão salvos como rascunho, sugerido, agendado ou serão publicados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d88b1-132">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="d88b1-133">Além disso, se você incluir a ID de um local existente, ele será substituído pelas informações no arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="d88b1-133">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="d88b1-134">Para parceiros que gerenciam várias organizações, você pode exportar seus locais de uma organização e importá-los para outro.</span><span class="sxs-lookup"><span data-stu-id="d88b1-134">For partners who manage multiple organizations, you can export your locations from one org and import them into another.</span></span> <span data-ttu-id="d88b1-135">Mas você deve remover todos os dados na coluna Id antes de importar.</span><span class="sxs-lookup"><span data-stu-id="d88b1-135">But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="d88b1-136">Para saber mais sobre os campos obrigatórios e recomendados, confira [Adicionar um local](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="d88b1-136">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

