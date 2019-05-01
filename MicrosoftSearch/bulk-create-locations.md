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
ms.openlocfilehash: 3c7e43b03b97b46769d5e73f20ddae47b3459b59
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508558"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="f4e96-103">Criar locais em massa</span><span class="sxs-lookup"><span data-stu-id="f4e96-103">Bulk create locations</span></span>

<span data-ttu-id="f4e96-104">Baixe e use o modelo. csv para criar, editar e salvar locais em massa.</span><span class="sxs-lookup"><span data-stu-id="f4e96-104">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="f4e96-105">No canto superior direito da seção locais, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="f4e96-105">In the upper-right corner of the Locations section, click **Import**</span></span>
    
2. <span data-ttu-id="f4e96-106">Clique em **baixar locais modelo (. csv)**</span><span class="sxs-lookup"><span data-stu-id="f4e96-106">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="f4e96-107">Salve e abra o arquivo. csv</span><span class="sxs-lookup"><span data-stu-id="f4e96-107">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="f4e96-108">Adicione o conteúdo do local e salve o arquivo</span><span class="sxs-lookup"><span data-stu-id="f4e96-108">Add the location content and save the file</span></span>

    <span data-ttu-id="f4e96-109">O arquivo. csv deve ser salvo como um arquivo CSV UTF-8, outros tipos de arquivo e codificações podem causar erros de importação</span><span class="sxs-lookup"><span data-stu-id="f4e96-109">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="f4e96-110">No canto superior direito da seção locais, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="f4e96-110">In the upper-right corner of the Locations section, click **Import**</span></span>
    
6. <span data-ttu-id="f4e96-111">No painel importar locais, clique em **procurar** e navegue até o arquivo. csv que você deseja importar</span><span class="sxs-lookup"><span data-stu-id="f4e96-111">In the Import locations pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="f4e96-112">Clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="f4e96-112">Click **Import**</span></span>

<span data-ttu-id="f4e96-113">Os campos nos modelos de importação e exportação de locais são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="f4e96-113">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="f4e96-114">Você pode exportar, editar em massa e importar as edições ou começar com um modelo vazio para criar novos locais em massa.</span><span class="sxs-lookup"><span data-stu-id="f4e96-114">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="f4e96-115">Para editar em massa locais existentes, exportá-los do portal de administração, fazer as edições necessárias e importá-las.</span><span class="sxs-lookup"><span data-stu-id="f4e96-115">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="f4e96-116">Impedir erros de importação</span><span class="sxs-lookup"><span data-stu-id="f4e96-116">Prevent import errors</span></span>  
<span data-ttu-id="f4e96-117">Você receberá um erro se os dados necessários estiverem ausentes ou forem inválidos.</span><span class="sxs-lookup"><span data-stu-id="f4e96-117">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="f4e96-118">Dependendo do erro, um arquivo de log pode ser gerado com mais informações sobre as linhas e colunas que precisam ser corrigidas.</span><span class="sxs-lookup"><span data-stu-id="f4e96-118">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="f4e96-119">Faça as edições necessárias e tente importar o arquivo novamente.</span><span class="sxs-lookup"><span data-stu-id="f4e96-119">Make any necessary edits, and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4e96-120">Até que todos os erros sejam resolvidos, não será possível criar ou editar nenhum local.</span><span class="sxs-lookup"><span data-stu-id="f4e96-120">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="f4e96-121">Para ajudar a evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente:</span><span class="sxs-lookup"><span data-stu-id="f4e96-121">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="f4e96-122">Inclui a linha de cabeçalho que estava no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="f4e96-122">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="f4e96-123">Inclui todas as colunas que estavam no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="f4e96-123">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="f4e96-124">A ordem da coluna é o mesmo que o modelo de importação</span><span class="sxs-lookup"><span data-stu-id="f4e96-124">The column order is the same as the import template</span></span>
- <span data-ttu-id="f4e96-125">Essas colunas podem estar vazias: ID, última modificação, última modificação, e lat/long</span><span class="sxs-lookup"><span data-stu-id="f4e96-125">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="f4e96-126">Tentaremos determinar lat/long com base no endereço se esse campo estiver vazio</span><span class="sxs-lookup"><span data-stu-id="f4e96-126">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="f4e96-127">A coluna de estado não pode ficar vazia, essas informações são necessárias</span><span class="sxs-lookup"><span data-stu-id="f4e96-127">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="f4e96-128">Com base no campo Estado, os locais serão salvos como rascunho, sugerido, agendado ou serão publicados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f4e96-128">Based on the State field, locations will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="f4e96-129">Além disso, se você incluir a ID de um local existente, ele será substituído pelas informações no arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="f4e96-129">Also, if you include the Id of an existing location, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="f4e96-130">Para organizações com vários locatários, você pode exportar seus locais de um locatário e importá-los para outro.</span><span class="sxs-lookup"><span data-stu-id="f4e96-130">For organizations with mulitple tenants, you can export your locations from one tenant and import it into another.</span></span> <span data-ttu-id="f4e96-131">Mas você deve remover todos os dados na coluna ID antes de importar.</span><span class="sxs-lookup"><span data-stu-id="f4e96-131">But you must remove all of the data in the Id column before you import.</span></span>
  
<span data-ttu-id="f4e96-132">Para saber mais sobre os campos obrigatórios e recomendados, confira [Adicionar um local](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="f4e96-132">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

