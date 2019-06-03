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
ROBOTS: NoIndex
description: Adicione respostas a perguntas frequentes rapidamente com ferramentas de importação no portal de administração da Pesquisa da Microsoft
ms.openlocfilehash: 7368014f3bc2f21a788625f0bf826af963366e1b
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591364"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="9fc35-103">Criar P e R em massa</span><span class="sxs-lookup"><span data-stu-id="9fc35-103">Bulk create Q&As</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9fc35-104">Este artigo se aplica à Pesquisa da Microsoft no portal de administração do Bing.</span><span class="sxs-lookup"><span data-stu-id="9fc35-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="9fc35-105">Estamos movendo o portal para o centro de administração do Microsoft 365 e, posteriormente, ele será removido.</span><span class="sxs-lookup"><span data-stu-id="9fc35-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="9fc35-106">Recomendamos que você use o centro de administração do Microsoft 365 para começar.</span><span class="sxs-lookup"><span data-stu-id="9fc35-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> [<span data-ttu-id="9fc35-107">Visão geral da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9fc35-107">Overview of Microsoft Search</span></span>](overview-microsoft-search.md)
    
<span data-ttu-id="9fc35-108">Baixe e use o modelo .csv para criar e editar P e R em massa.</span><span class="sxs-lookup"><span data-stu-id="9fc35-108">Download and use the .csv template to bulk create or bulk edit Q&As.</span></span> <span data-ttu-id="9fc35-109">Também é uma maneira simples de salvar em massa rascunhos de perguntas e respostas que precisam de edições e atualizações adicionais.</span><span class="sxs-lookup"><span data-stu-id="9fc35-109">It's also a simple way to bulk save draft Q&As that need additional edits or updates.</span></span> <span data-ttu-id="9fc35-110">Para editar perguntas e respostas existentes em massa, exporte-as do portal de administração, faça as edições necessárias e depois importe-as.</span><span class="sxs-lookup"><span data-stu-id="9fc35-110">If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="9fc35-111">No canto superior direito da seção Perguntas e Respostas, clique em **Importar**</span><span class="sxs-lookup"><span data-stu-id="9fc35-111">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="9fc35-112">Clique em **Baixar modelo de perguntas e respostas (.csv)**</span><span class="sxs-lookup"><span data-stu-id="9fc35-112">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="9fc35-113">Salve e abra o arquivo .csv</span><span class="sxs-lookup"><span data-stu-id="9fc35-113">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="9fc35-114">Adicione o conteúdo e as configurações de P e R e salve o arquivo</span><span class="sxs-lookup"><span data-stu-id="9fc35-114">Add the Q&A content and settings and save the file</span></span>

    <span data-ttu-id="9fc35-115">O arquivo .csv deve ser salvo como um arquivo CSV UTF-8; outros tipos de arquivo e/ou codificações podem causar erros de importação</span><span class="sxs-lookup"><span data-stu-id="9fc35-115">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="9fc35-116">No canto superior direito da seção P e R, clique em **Importar**</span><span class="sxs-lookup"><span data-stu-id="9fc35-116">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="9fc35-117">No painel Importar P e R, clique em **Procurar** e navegue até o arquivo .csv que deseja importar.</span><span class="sxs-lookup"><span data-stu-id="9fc35-117">In the Import locations pane, select **Browse**, and then the .csv file that you want to import.</span></span> 
    
7. <span data-ttu-id="9fc35-118">Clique em **Importar**</span><span class="sxs-lookup"><span data-stu-id="9fc35-118">Click **Import**.</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="9fc35-119">Evite erros de importação</span><span class="sxs-lookup"><span data-stu-id="9fc35-119">Prevent import errors</span></span>      
<span data-ttu-id="9fc35-120">Se os dados necessários estiverem ausentes ou forem inválidos, você receberá um erro.</span><span class="sxs-lookup"><span data-stu-id="9fc35-120">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="9fc35-121">Dependendo do erro, pode ser gerado um arquivo de registro com mais informações sobre quais linhas e colunas precisam ser corrigidas.</span><span class="sxs-lookup"><span data-stu-id="9fc35-121">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="9fc35-122">Faça as edições necessárias e tente importar o arquivo novamente.</span><span class="sxs-lookup"><span data-stu-id="9fc35-122">Make necessary edits and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="9fc35-123">Até que todos os erros sejam resolvidos, não será possível criar ou editar nenhum item de P e R.</span><span class="sxs-lookup"><span data-stu-id="9fc35-123">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="9fc35-124">Para ajudar a evitar erros, verifique se o arquivo de importação está formatado corretamente:</span><span class="sxs-lookup"><span data-stu-id="9fc35-124">To prevent errors, make sure your import file is properly formatted and:</span></span>
- <span data-ttu-id="9fc35-125">Inclui a linha de cabeçalho que estava no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="9fc35-125">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="9fc35-126">Inclui todas as colunas que estavam no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="9fc35-126">Includes the header row and all the columns that were in the import template</span></span>
- <span data-ttu-id="9fc35-127">A ordem das colunas é igual ao modelo de importação</span><span class="sxs-lookup"><span data-stu-id="9fc35-127">The column order is the same as the import template</span></span>
- <span data-ttu-id="9fc35-128">Essas colunas podem estar vazias: Id, Última Modificação e Última Modificação Por</span><span class="sxs-lookup"><span data-stu-id="9fc35-128">All columns have values, except the three that can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="9fc35-129">A coluna Estado não pode estar vazia, essa informação é necessária</span><span class="sxs-lookup"><span data-stu-id="9fc35-129">The State column is not empty, as this information is required</span></span>  
<span data-ttu-id="9fc35-130">Com base no campo Estado, as P e R serão salvas como rascunho, sugerido, programado, ou serão publicadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9fc35-130">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="9fc35-131">Além disso, se você incluir o Id de uma pergunta e resposta existente, ele será substituído pelas informações no arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="9fc35-131">If you include the Id of an existing bookmark, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="9fc35-132">Para organizações com vários locatários, você pode exportar suas P e R de um locatário e importá-las para outro.</span><span class="sxs-lookup"><span data-stu-id="9fc35-132">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="9fc35-133">Mas você deve remover todos os dados na coluna Id antes de importar.</span><span class="sxs-lookup"><span data-stu-id="9fc35-133">But you must remove the data in the Id column before you import.</span></span>

<span data-ttu-id="9fc35-134">Para saber mais sobre os campos obrigatórios e recomendados, consulte [Criar P e R](create-qas.md).</span><span class="sxs-lookup"><span data-stu-id="9fc35-134">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

