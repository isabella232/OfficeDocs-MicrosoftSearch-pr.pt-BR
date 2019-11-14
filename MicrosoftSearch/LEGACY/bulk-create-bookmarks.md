---
title: Criar indicadores em massa
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: def300e7-103c-4e92-a062-28ffa27561d7
ROBOTS: NoIndex
description: Criar muitos indicadores de uma vez com as ferramentas de importação para o portal de administração de pesquisa da Microsoft
ms.openlocfilehash: 2983a47a8761a2463b25497911024f9bfd069369
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311353"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="62099-103">Criar indicadores em massa</span><span class="sxs-lookup"><span data-stu-id="62099-103">Bulk create bookmarks</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62099-104">Este artigo se aplica à Pesquisa da Microsoft no portal de administração do Bing.</span><span class="sxs-lookup"><span data-stu-id="62099-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="62099-105">Estamos movendo o portal para o centro de administração do Microsoft 365 e, em seguida, a Pesquisa da Microsoft no portal do Bing será removida.</span><span class="sxs-lookup"><span data-stu-id="62099-105">We’re moving the portal to the Microsoft 365 admin center, and then the Microsoft Search in Bing portal will be removed.</span></span> <span data-ttu-id="62099-106">Recomendamos que você use o centro de administração do Microsoft 365 para começar.</span><span class="sxs-lookup"><span data-stu-id="62099-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> <span data-ttu-id="62099-107">[Visão geral da Pesquisa da Microsoft.](overview-microsoft-search.md)</span><span class="sxs-lookup"><span data-stu-id="62099-107">[Overview of Microsoft Search](overview-microsoft-search.md).</span></span>
    
<span data-ttu-id="62099-108">Baixe e use o modelo. csv para criar, editar e salvar os indicadores em massa.</span><span class="sxs-lookup"><span data-stu-id="62099-108">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="62099-109">Para editar em massa indicadores existentes, exporte-os do portal de administração, faça as edições necessárias e importe-as.</span><span class="sxs-lookup"><span data-stu-id="62099-109">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="62099-110">No canto superior direito da seção indicadores, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="62099-110">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="62099-111">Clique em **baixar indicadores de modelo (. csv)**</span><span class="sxs-lookup"><span data-stu-id="62099-111">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="62099-112">Salve e abra o arquivo .csv</span><span class="sxs-lookup"><span data-stu-id="62099-112">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="62099-113">Adicione o conteúdo e as configurações do indicador e salve o arquivo</span><span class="sxs-lookup"><span data-stu-id="62099-113">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="62099-114">O arquivo .csv deve ser salvo como um arquivo CSV UTF-8; outros tipos de arquivo e/ou codificações podem causar erros de importação</span><span class="sxs-lookup"><span data-stu-id="62099-114">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="62099-115">No canto superior direito da seção indicadores, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="62099-115">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="62099-116">No painel importar marcadores, clique em **procurar** e navegue até o arquivo. csv que você deseja importar</span><span class="sxs-lookup"><span data-stu-id="62099-116">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="62099-117">Clique em **Importar**</span><span class="sxs-lookup"><span data-stu-id="62099-117">Click **Import**</span></span>

## <a name="prevent-import-errors"></a><span data-ttu-id="62099-118">Evite erros de importação</span><span class="sxs-lookup"><span data-stu-id="62099-118">Prevent import errors</span></span>      
<span data-ttu-id="62099-119">Se os dados necessários estiverem ausentes ou forem inválidos, você receberá um erro.</span><span class="sxs-lookup"><span data-stu-id="62099-119">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="62099-120">Dependendo do erro, pode ser gerado um arquivo de registro com mais informações sobre quais linhas e colunas precisam ser corrigidas.</span><span class="sxs-lookup"><span data-stu-id="62099-120">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="62099-121">Faça as edições necessárias e tente importar o arquivo novamente.</span><span class="sxs-lookup"><span data-stu-id="62099-121">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="62099-122">Até que todos os erros sejam resolvidos, não será possível criar ou editar nenhum indicador.</span><span class="sxs-lookup"><span data-stu-id="62099-122">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="62099-123">Para ajudar a evitar erros, verifique se o arquivo de importação está formatado corretamente:</span><span class="sxs-lookup"><span data-stu-id="62099-123">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="62099-124">Inclui a linha de cabeçalho que estava no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="62099-124">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="62099-125">Inclui todas as colunas que estavam no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="62099-125">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="62099-126">A ordem das colunas é igual ao modelo de importação</span><span class="sxs-lookup"><span data-stu-id="62099-126">The column order is the same as the import template</span></span>
- <span data-ttu-id="62099-127">Essas colunas podem estar vazias: Id, Última Modificação e Última Modificação Por</span><span class="sxs-lookup"><span data-stu-id="62099-127">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="62099-128">A coluna Estado não pode estar vazia, essa informação é necessária</span><span class="sxs-lookup"><span data-stu-id="62099-128">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="62099-129">Com base no campo Estado, os indicadores serão salvos como rascunho, sugerido ou programado, ou serão publicados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="62099-129">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="62099-130">Além disso, se você incluir a ID de um indicador existente, ele será substituído pelas informações no arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="62099-130">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="62099-131">Para parceiros que gerenciam várias organizações, você pode exportar seus indicadores de uma organização e importá-los para outro.</span><span class="sxs-lookup"><span data-stu-id="62099-131">For partners who manage multiple organizations, you can export your bookmarks from one org and import them into another.</span></span> <span data-ttu-id="62099-132">Mas você deve remover todos os dados na coluna Id antes de importar.</span><span class="sxs-lookup"><span data-stu-id="62099-132">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="62099-133">Para saber mais sobre os campos obrigatórios e recomendados, confira [criar indicadores](create-bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="62099-133">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
