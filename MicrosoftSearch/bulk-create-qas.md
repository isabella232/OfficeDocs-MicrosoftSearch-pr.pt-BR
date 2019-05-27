---
title: Criar P e R em massa
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
ms.assetid: 7bada218-8908-4956-aae3-6ffaeef384ca
description: Adicione respostas a perguntas frequentes rapidamente com ferramentas de importação no portal de administração da Pesquisa da Microsoft
ms.openlocfilehash: f535cb7ae843def536976cb1f05c8601de592cbb
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968296"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="9d6e6-103">Criar P e R em massa</span><span class="sxs-lookup"><span data-stu-id="9d6e6-103">Bulk create Q&As</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d6e6-104">As configurações da Pesquisa da Microsoft no Bing agora estão disponíveis no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d6e6-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="9d6e6-105">Comece por [atribuir administradores de pesquisa](https://docs.microsoft.com/pt-BR/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) ao seu centro de administração.</span><span class="sxs-lookup"><span data-stu-id="9d6e6-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="9d6e6-106">Baixe e use o modelo .csv para criar e editar P e R em massa.</span><span class="sxs-lookup"><span data-stu-id="9d6e6-106">Download and use the .csv template to bulk create or bulk edit Q&As.</span></span> <span data-ttu-id="9d6e6-107">Também é uma maneira simples de salvar em massa rascunhos de perguntas e respostas que precisam de edições e atualizações adicionais.</span><span class="sxs-lookup"><span data-stu-id="9d6e6-107">It's also a simple way to bulk save draft Q&As that need additional edits or updates.</span></span> <span data-ttu-id="9d6e6-108">Para editar perguntas e respostas existentes em massa, exporte-as do portal de administração, faça as edições necessárias e depois importe-as.</span><span class="sxs-lookup"><span data-stu-id="9d6e6-108">If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="9d6e6-109">No canto superior direito da seção Perguntas e Respostas, clique em **Importar**</span><span class="sxs-lookup"><span data-stu-id="9d6e6-109">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="9d6e6-110">Clique em **Baixar modelo de perguntas e respostas (.csv)**</span><span class="sxs-lookup"><span data-stu-id="9d6e6-110">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="9d6e6-111">Salve e abra o arquivo .csv</span><span class="sxs-lookup"><span data-stu-id="9d6e6-111">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="9d6e6-112">Adicione o conteúdo e as configurações de P e R e salve o arquivo</span><span class="sxs-lookup"><span data-stu-id="9d6e6-112">Add the Q&A content and settings and save the file</span></span>

    <span data-ttu-id="9d6e6-113">O arquivo .csv deve ser salvo como um arquivo CSV UTF-8; outros tipos de arquivo e/ou codificações podem causar erros de importação</span><span class="sxs-lookup"><span data-stu-id="9d6e6-113">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="9d6e6-114">No canto superior direito da seção P e R, clique em **Importar**</span><span class="sxs-lookup"><span data-stu-id="9d6e6-114">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="9d6e6-115">No painel Importar P e R, clique em **Procurar** e navegue até o arquivo .csv que deseja importar.</span><span class="sxs-lookup"><span data-stu-id="9d6e6-115">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="9d6e6-116">Clique em **Importar**</span><span class="sxs-lookup"><span data-stu-id="9d6e6-116">Click **Import**.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="9d6e6-117">Evite erros de importação</span><span class="sxs-lookup"><span data-stu-id="9d6e6-117">Prevent import errors</span></span>      
<span data-ttu-id="9d6e6-118">Se os dados necessários estiverem ausentes ou forem inválidos, você receberá um erro.</span><span class="sxs-lookup"><span data-stu-id="9d6e6-118">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="9d6e6-119">Dependendo do erro, pode ser gerado um arquivo de registro com mais informações sobre quais linhas e colunas precisam ser corrigidas.</span><span class="sxs-lookup"><span data-stu-id="9d6e6-119">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="9d6e6-120">Faça as edições necessárias e tente importar o arquivo novamente.</span><span class="sxs-lookup"><span data-stu-id="9d6e6-120">Make necessary edits and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="9d6e6-121">Até que todos os erros sejam resolvidos, não será possível criar ou editar nenhum item de P e R.</span><span class="sxs-lookup"><span data-stu-id="9d6e6-121">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="9d6e6-122">Para ajudar a evitar erros, verifique se o arquivo de importação está formatado corretamente:</span><span class="sxs-lookup"><span data-stu-id="9d6e6-122">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="9d6e6-123">Inclui a linha de cabeçalho que estava no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="9d6e6-123">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="9d6e6-124">Inclui todas as colunas que estavam no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="9d6e6-124">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="9d6e6-125">A ordem das colunas é igual ao modelo de importação</span><span class="sxs-lookup"><span data-stu-id="9d6e6-125">The column order is the same as the import template</span></span>
- <span data-ttu-id="9d6e6-126">Essas colunas podem estar vazias: Id, Última Modificação e Última Modificação Por</span><span class="sxs-lookup"><span data-stu-id="9d6e6-126">All columns have values, except the three that can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="9d6e6-127">A coluna Estado não pode estar vazia, essa informação é necessária</span><span class="sxs-lookup"><span data-stu-id="9d6e6-127">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="9d6e6-128">Com base no campo Estado, as P e R serão salvas como rascunho, sugerido, programado, ou serão publicadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9d6e6-128">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="9d6e6-129">Além disso, se você incluir o Id de uma pergunta e resposta existente, ele será substituído pelas informações no arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="9d6e6-129">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="9d6e6-130">Para organizações com vários locatários, você pode exportar suas P e R de um locatário e importá-las para outro.</span><span class="sxs-lookup"><span data-stu-id="9d6e6-130">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="9d6e6-131">Mas você deve remover todos os dados na coluna Id antes de importar.</span><span class="sxs-lookup"><span data-stu-id="9d6e6-131">But you must remove the data in the Id column before you import.</span></span>

<span data-ttu-id="9d6e6-132">Para saber mais sobre os campos obrigatórios e recomendados, consulte [Criar P e R](create-qas.md).</span><span class="sxs-lookup"><span data-stu-id="9d6e6-132">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

