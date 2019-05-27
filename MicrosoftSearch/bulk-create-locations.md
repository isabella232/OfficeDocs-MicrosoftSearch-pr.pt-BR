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
description: Adicione vários locais de uma só vez com ferramentas de importação para o portal de administração da Pesquisa da Microsoft
ms.openlocfilehash: 1d360fda2851083def0bcbd8fcffd77cfa15240e
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968288"
---
# <a name="bulk-create-locations"></a><span data-ttu-id="5591c-103">Criar locais em massa</span><span class="sxs-lookup"><span data-stu-id="5591c-103">Bulk create locations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5591c-104">As configurações da Pesquisa da Microsoft no Bing agora estão disponíveis no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5591c-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5591c-105">Comece por [atribuir administradores de pesquisa](https://docs.microsoft.com/pt-BR/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) ao seu centro de administração.</span><span class="sxs-lookup"><span data-stu-id="5591c-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="5591c-106">Faça o download e use o modelo .csv para criar, editar e salvar locais em massa.</span><span class="sxs-lookup"><span data-stu-id="5591c-106">Download and use the .csv template to bulk create, edit, and save locations.</span></span> 
  
1. <span data-ttu-id="5591c-107">No canto superior direito da seção Locais, clique em **Importar**</span><span class="sxs-lookup"><span data-stu-id="5591c-107">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
2. <span data-ttu-id="5591c-108">Clique em **Baixar modelo de locais (.csv)**</span><span class="sxs-lookup"><span data-stu-id="5591c-108">Click **Download locations template (.csv)**</span></span>
    
3. <span data-ttu-id="5591c-109">Salve e abra o arquivo .csv</span><span class="sxs-lookup"><span data-stu-id="5591c-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="5591c-110">Adicione o conteúdo do local e salve o arquivo</span><span class="sxs-lookup"><span data-stu-id="5591c-110">Add the location content and save the file</span></span>

    <span data-ttu-id="5591c-111">O arquivo .csv deve ser salvo como um arquivo CSV UTF-8; outros tipos de arquivo e/ou codificações podem causar erros de importação</span><span class="sxs-lookup"><span data-stu-id="5591c-111">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="5591c-112">No canto superior direito da seção Locais, clique em **Importar**</span><span class="sxs-lookup"><span data-stu-id="5591c-112">In the upper-right corner of the Locations tab, select **Import**.</span></span>
    
6. <span data-ttu-id="5591c-113">No painel Importar Locais, clique em **Procurar** e navegue até o arquivo .csv que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="5591c-113">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="5591c-114">Clique em **Importar**</span><span class="sxs-lookup"><span data-stu-id="5591c-114">Click **Import**.</span></span>

<span data-ttu-id="5591c-115">Os campos nos modelos de locais de importação e exportação são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="5591c-115">The fields in the import and export locations templates are the same.</span></span> <span data-ttu-id="5591c-116">Você pode exportar, editar em massa e importar as edições, ou começar com um modelo vazio para criar novos locais em massa.</span><span class="sxs-lookup"><span data-stu-id="5591c-116">You can export, bulk edit, and import the edits, or start with an empty template to bulk create new locations.</span></span> <span data-ttu-id="5591c-117">Para editar locais existentes em massa, exporte-os a partir do portal de administração, efetue as edições necessárias e, em seguida, importe-os.</span><span class="sxs-lookup"><span data-stu-id="5591c-117">To bulk edit existing locations, export them from the Admin portal, make the necessary edits, and then import them.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="5591c-118">Evite erros de importação</span><span class="sxs-lookup"><span data-stu-id="5591c-118">Prevent import errors</span></span>  
<span data-ttu-id="5591c-119">Se os dados necessários estiverem ausentes ou forem inválidos, você receberá um erro.</span><span class="sxs-lookup"><span data-stu-id="5591c-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="5591c-120">Dependendo do erro, pode ser gerado um arquivo de registro com mais informações sobre quais linhas e colunas precisam ser corrigidas.</span><span class="sxs-lookup"><span data-stu-id="5591c-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="5591c-121">Faça as edições necessárias e tente importar o arquivo novamente.</span><span class="sxs-lookup"><span data-stu-id="5591c-121">Make necessary edits and try importing the file again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5591c-122">Até que todos os erros sejam resolvidos, você não poderá criar ou editar nenhum local.</span><span class="sxs-lookup"><span data-stu-id="5591c-122">Until all errors are resolved, you can't create or edit any locations.</span></span> 

<span data-ttu-id="5591c-123">Para ajudar a evitar erros, verifique se o arquivo de importação está formatado corretamente:</span><span class="sxs-lookup"><span data-stu-id="5591c-123">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="5591c-124">Inclui a linha de cabeçalho que estava no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="5591c-124">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="5591c-125">Inclui todas as colunas que estavam no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="5591c-125">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="5591c-126">A ordem das colunas é igual ao modelo de importação</span><span class="sxs-lookup"><span data-stu-id="5591c-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="5591c-127">Essas colunas podem estar vazias: Id, Última Modificação, Última Modificação Por e Lat/Long</span><span class="sxs-lookup"><span data-stu-id="5591c-127">These columns can be empty: Id, Last Modified, Last Modified By, and Lat/Long</span></span>  
<span data-ttu-id="5591c-128">Vamos tentar determinar a lat/long com base no endereço se esse campo estiver vazio</span><span class="sxs-lookup"><span data-stu-id="5591c-128">We'll try to determine lat/long based on the address if that field is empty</span></span>
- <span data-ttu-id="5591c-129">A coluna Estado não pode estar vazia, essa informação é necessária</span><span class="sxs-lookup"><span data-stu-id="5591c-129">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="5591c-130">Com base no campo Estado, os locais serão salvos como rascunho, sugerido ou programado, ou serão publicados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5591c-130">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="5591c-131">Além disso, se você incluir o ID de um local existente, ele será substituído pelas informações no arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="5591c-131">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="5591c-132">Para organizações com vários locatários, você pode exportar seus locais de um locatário e importá-los para outro.</span><span class="sxs-lookup"><span data-stu-id="5591c-132">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="5591c-133">Mas você deve remover todos os dados na coluna Id antes de importar.</span><span class="sxs-lookup"><span data-stu-id="5591c-133">But you must remove the data in the Id column before you import.</span></span>
  
<span data-ttu-id="5591c-134">Para saber mais sobre os campos obrigatórios e recomendados, consulte [Adicionar um local](add-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="5591c-134">To find out more about required and recommended fields, see [Add a location](add-a-location.md).</span></span>

  

