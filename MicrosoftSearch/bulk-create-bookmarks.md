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
description: Criar muitos indicadores de uma vez com as ferramentas de importação para o portal de administração de pesquisa da Microsoft
ms.openlocfilehash: 7c134784f0ca0d4cc84d5bce3a98f7e75aa6f441
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508614"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="efb66-103">Criar indicadores em massa</span><span class="sxs-lookup"><span data-stu-id="efb66-103">Bulk create bookmarks</span></span>

<span data-ttu-id="efb66-104">Baixe e use o modelo. csv para criar, editar e salvar os indicadores em massa.</span><span class="sxs-lookup"><span data-stu-id="efb66-104">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="efb66-105">Para editar em massa indicadores existentes, exporte-os do portal de administração, faça as edições necessárias e importe-as.</span><span class="sxs-lookup"><span data-stu-id="efb66-105">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="efb66-106">No canto superior direito da seção indicadores, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="efb66-106">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="efb66-107">Clique em **baixar indicadores de modelo (. csv)**</span><span class="sxs-lookup"><span data-stu-id="efb66-107">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="efb66-108">Salve e abra o arquivo. csv</span><span class="sxs-lookup"><span data-stu-id="efb66-108">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="efb66-109">Adicione o conteúdo e as configurações do indicador e salve o arquivo</span><span class="sxs-lookup"><span data-stu-id="efb66-109">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="efb66-110">O arquivo. csv deve ser salvo como um arquivo CSV UTF-8, outros tipos de arquivo e codificações podem causar erros de importação</span><span class="sxs-lookup"><span data-stu-id="efb66-110">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="efb66-111">No canto superior direito da seção indicadores, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="efb66-111">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="efb66-112">No painel importar marcadores, clique em **procurar** e navegue até o arquivo. csv que você deseja importar</span><span class="sxs-lookup"><span data-stu-id="efb66-112">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="efb66-113">Clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="efb66-113">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="efb66-114">Impedir erros de importação</span><span class="sxs-lookup"><span data-stu-id="efb66-114">Prevent import errors</span></span>      
<span data-ttu-id="efb66-115">Você receberá um erro se os dados necessários estiverem ausentes ou forem inválidos.</span><span class="sxs-lookup"><span data-stu-id="efb66-115">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="efb66-116">Dependendo do erro, um arquivo de log pode ser gerado com mais informações sobre as linhas e colunas que precisam ser corrigidas.</span><span class="sxs-lookup"><span data-stu-id="efb66-116">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="efb66-117">Faça as edições necessárias e tente importar o arquivo novamente.</span><span class="sxs-lookup"><span data-stu-id="efb66-117">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="efb66-118">Até que todos os erros sejam resolvidos, não será possível criar ou editar nenhum indicador.</span><span class="sxs-lookup"><span data-stu-id="efb66-118">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="efb66-119">Para ajudar a evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente:</span><span class="sxs-lookup"><span data-stu-id="efb66-119">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="efb66-120">Inclui a linha de cabeçalho que estava no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="efb66-120">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="efb66-121">Inclui todas as colunas que estavam no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="efb66-121">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="efb66-122">A ordem da coluna é o mesmo que o modelo de importação</span><span class="sxs-lookup"><span data-stu-id="efb66-122">The column order is the same as the import template</span></span>
- <span data-ttu-id="efb66-123">Essas colunas podem estar vazias: ID, última modificação e última modificação por</span><span class="sxs-lookup"><span data-stu-id="efb66-123">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="efb66-124">A coluna de estado não pode ficar vazia, essas informações são necessárias</span><span class="sxs-lookup"><span data-stu-id="efb66-124">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="efb66-125">Com base no campo Estado, os indicadores serão salvos como rascunho, sugerido, agendado ou serão publicados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="efb66-125">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="efb66-126">Além disso, se você incluir a ID de um indicador existente, ele será substituído pelas informações no arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="efb66-126">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="efb66-127">Para organizações com vários locatários, você pode exportar seus indicadores de um locatário e importá-los para outro.</span><span class="sxs-lookup"><span data-stu-id="efb66-127">For organizations with mulitple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="efb66-128">Mas você deve remover todos os dados na coluna ID antes de importar.</span><span class="sxs-lookup"><span data-stu-id="efb66-128">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="efb66-129">Para saber mais sobre os campos obrigatórios e recomendados, confira [criar indicadores](create-bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="efb66-129">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
