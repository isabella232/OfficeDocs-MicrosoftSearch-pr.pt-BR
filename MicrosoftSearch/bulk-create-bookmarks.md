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
ms.openlocfilehash: 07694de1f546a1431f371fa24ffc5721ea66337c
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068399"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="1b06c-103">Criar indicadores em massa</span><span class="sxs-lookup"><span data-stu-id="1b06c-103">Bulk create bookmarks</span></span>

<span data-ttu-id="1b06c-p101">Baixe e use o modelo. csv para criar, editar e salvar os indicadores em massa. Para editar em massa indicadores existentes, exporte-os do portal de administração, faça as edições necessárias e importe-as.</span><span class="sxs-lookup"><span data-stu-id="1b06c-p101">Download and use the .csv template to bulk create, edit, and save bookmarks. To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="1b06c-106">No canto superior direito da seção indicadores, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="1b06c-106">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="1b06c-107">Clique em **baixar indicadores de modelo (. csv)**</span><span class="sxs-lookup"><span data-stu-id="1b06c-107">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="1b06c-108">Salve e abra o arquivo. csv</span><span class="sxs-lookup"><span data-stu-id="1b06c-108">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="1b06c-109">Adicione o conteúdo e as configurações do indicador e salve o arquivo</span><span class="sxs-lookup"><span data-stu-id="1b06c-109">Add the bookmark content and settings and save the file</span></span>
    
5. <span data-ttu-id="1b06c-110">No canto superior direito da seção indicadores, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="1b06c-110">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="1b06c-111">No painel importar marcadores, clique em **procurar** e navegue até o arquivo. csv que você deseja importar</span><span class="sxs-lookup"><span data-stu-id="1b06c-111">In the Import bookmarks pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="1b06c-112">Clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="1b06c-112">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="1b06c-113">Impedir erros de importação</span><span class="sxs-lookup"><span data-stu-id="1b06c-113">Prevent import errors</span></span>      
<span data-ttu-id="1b06c-p102">Você receberá um erro se os dados necessários estiverem ausentes ou forem inválidos. Dependendo do erro, um arquivo de log pode ser gerado com mais informações sobre as linhas e colunas que precisam ser corrigidas. Faça as edições necessárias e tente importar o arquivo novamente.</span><span class="sxs-lookup"><span data-stu-id="1b06c-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="1b06c-117">Até que todos os erros sejam resolvidos, não será possível criar ou editar nenhum indicador.</span><span class="sxs-lookup"><span data-stu-id="1b06c-117">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="1b06c-118">Para ajudar a evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente:</span><span class="sxs-lookup"><span data-stu-id="1b06c-118">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="1b06c-119">Inclui a linha de cabeçalho que estava no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="1b06c-119">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="1b06c-120">Inclui todas as colunas que estavam no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="1b06c-120">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="1b06c-121">A ordem da coluna é o mesmo que o modelo de importação</span><span class="sxs-lookup"><span data-stu-id="1b06c-121">The column order is the same as the import template</span></span>
- <span data-ttu-id="1b06c-122">Essas colunas podem estar vazias: ID, última modificação e última modificação por</span><span class="sxs-lookup"><span data-stu-id="1b06c-122">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="1b06c-123">A coluna de estado não pode ficar vazia, essas informações são necessárias</span><span class="sxs-lookup"><span data-stu-id="1b06c-123">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="1b06c-124">Com base no campo Estado, os indicadores serão salvos como rascunho, sugerido, agendado ou serão publicados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1b06c-124">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="1b06c-125">Além disso, se você incluir a ID de um indicador existente, ele será substituído pelas informações no arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="1b06c-125">Also, if you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="1b06c-p103">Para organizações com vários locatários, você pode exportar seus indicadores de um locatário e importá-los para outro. Mas você deve remover todos os dados na coluna ID antes de importar.</span><span class="sxs-lookup"><span data-stu-id="1b06c-p103">For organizations with mulitple tenants, you can export your bookmarks from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="1b06c-128">Para saber mais sobre os campos obrigatórios e recomendados, confira [criar indicadores](create-bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="1b06c-128">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
