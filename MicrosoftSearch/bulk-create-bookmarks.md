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
description: Crie vários indicadores de uma só vez com ferramentas de importação para o portal de administração da Pesquisa da Microsoft
ms.openlocfilehash: 560cda6f94060d428f2d18cc61bd2430cb31b474
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968344"
---
# <a name="bulk-create-bookmarks"></a><span data-ttu-id="9f746-103">Criar indicadores em massa</span><span class="sxs-lookup"><span data-stu-id="9f746-103">Bulk create bookmarks</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9f746-104">As configurações da Pesquisa da Microsoft no Bing agora estão disponíveis no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9f746-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9f746-105">Comece por [atribuir administradores de pesquisa](https://docs.microsoft.com/pt-BR/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) ao seu centro de administração.</span><span class="sxs-lookup"><span data-stu-id="9f746-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="9f746-106">Baixe e use o modelo .csv para criar, editar e salvar indicadores em massa.</span><span class="sxs-lookup"><span data-stu-id="9f746-106">Download and use the .csv template to bulk create, edit, and save bookmarks.</span></span> <span data-ttu-id="9f746-107">Para editar indicadores existentes em massa, exportá-los do portal de administração, fazer as edições necessárias e depois importá-los.</span><span class="sxs-lookup"><span data-stu-id="9f746-107">To bulk edit existing bookmarks, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="9f746-108">No canto superior direito da página Indicadores, clique em **Importar**</span><span class="sxs-lookup"><span data-stu-id="9f746-108">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
2. <span data-ttu-id="9f746-109">Clique em **Baixar modelo indicadores (.csv)**</span><span class="sxs-lookup"><span data-stu-id="9f746-109">Click **Download bookmarks template (.csv)**</span></span>
    
3. <span data-ttu-id="9f746-110">Salve e abra o arquivo .csv</span><span class="sxs-lookup"><span data-stu-id="9f746-110">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="9f746-111">Adicione o conteúdo e as configurações do indicador e salve o arquivo</span><span class="sxs-lookup"><span data-stu-id="9f746-111">Add the bookmark content and settings and save the file</span></span>

    <span data-ttu-id="9f746-112">O arquivo .csv deve ser salvo como um arquivo CSV UTF-8; outros tipos de arquivo e/ou codificações podem causar erros de importação</span><span class="sxs-lookup"><span data-stu-id="9f746-112">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="9f746-113">No canto superior direito da seção Indicadores, clique em **Importar**</span><span class="sxs-lookup"><span data-stu-id="9f746-113">In the upper-right corner of the Bookmarks section, click **Import**</span></span>
    
6. <span data-ttu-id="9f746-114">No painel Importar indicadores, clique em **Procurar** e navegue até o arquivo .csv que você deseja importar</span><span class="sxs-lookup"><span data-stu-id="9f746-114">In the Import bookmarks pane, select **Browse** and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="9f746-115">Clique em **Importar**</span><span class="sxs-lookup"><span data-stu-id="9f746-115">Click **Import**.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="9f746-116">Evite erros de importação</span><span class="sxs-lookup"><span data-stu-id="9f746-116">Prevent import errors</span></span>      
<span data-ttu-id="9f746-117">Se os dados necessários estiverem ausentes ou forem inválidos, você receberá um erro.</span><span class="sxs-lookup"><span data-stu-id="9f746-117">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="9f746-118">Dependendo do erro, pode ser gerado um arquivo de registro com mais informações sobre quais linhas e colunas precisam ser corrigidas.</span><span class="sxs-lookup"><span data-stu-id="9f746-118">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="9f746-119">Faça as edições necessárias e tente importar o arquivo novamente.</span><span class="sxs-lookup"><span data-stu-id="9f746-119">Make necessary edits and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="9f746-120">Até que todos os erros sejam resolvidos, não será possível criar ou editar nenhum indicador.</span><span class="sxs-lookup"><span data-stu-id="9f746-120">Until all errors are resolved, you can't create or edit any bookmarks.</span></span> 

<span data-ttu-id="9f746-121">Para ajudar a evitar erros, verifique se o arquivo de importação está formatado corretamente:</span><span class="sxs-lookup"><span data-stu-id="9f746-121">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="9f746-122">Inclui a linha de cabeçalho que estava no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="9f746-122">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="9f746-123">Inclui todas as colunas que estavam no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="9f746-123">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="9f746-124">A ordem das colunas é igual ao modelo de importação</span><span class="sxs-lookup"><span data-stu-id="9f746-124">The column order is the same as the import template</span></span>
- <span data-ttu-id="9f746-125">Essas colunas podem estar vazias: Id, Última Modificação e Última Modificação Por</span><span class="sxs-lookup"><span data-stu-id="9f746-125">All columns have values, except the three that can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="9f746-126">A coluna Estado não pode estar vazia, essa informação é necessária</span><span class="sxs-lookup"><span data-stu-id="9f746-126">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="9f746-127">Com base no campo Estado, os indicadores serão salvos como rascunho, sugerido ou programado, ou serão publicados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9f746-127">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="9f746-128">Além disso, se você incluir o ID de um indicador existente, ele será substituído pelas informações no arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="9f746-128">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="9f746-129">Para organizações com vários locatários, você pode exportar seus indicadores de um locatário e importá-los para outro.</span><span class="sxs-lookup"><span data-stu-id="9f746-129">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="9f746-130">Mas você deve remover todos os dados na coluna Id antes de importar.</span><span class="sxs-lookup"><span data-stu-id="9f746-130">But you must remove the data in the Id column before you import.</span></span>

<span data-ttu-id="9f746-131">Para saber mais sobre campos obrigatórios e recomendados, consulte [Criar indicadores](create-bookmarks.md).</span><span class="sxs-lookup"><span data-stu-id="9f746-131">To find out more about required and recommended fields, see [Create bookmarks](create-bookmarks.md).</span></span>
