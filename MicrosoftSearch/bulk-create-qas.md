---
title: Criar perguntas e respostas em massa
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
description: Adicionar rapidamente as respostas às perguntas frequentes com as ferramentas de importação no portal de administração de pesquisa da Microsoft
ms.openlocfilehash: 28fcf57c44f809e7f9b0c1b27042f4549067a0f8
ms.sourcegitcommit: c70dd5eae43abb775acc6fc4522c2e6be4f0bb67
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901813"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="dd3db-103">Criar perguntas e respostas em massa</span><span class="sxs-lookup"><span data-stu-id="dd3db-103">Bulk create Q&As</span></span>

<span data-ttu-id="dd3db-104">Baixe e use o modelo. csv para criar ou editar em massa Q&As.</span><span class="sxs-lookup"><span data-stu-id="dd3db-104">Download and use the .csv template to bulk create or bulk edit Q&As.</span></span> <span data-ttu-id="dd3db-105">Também é uma maneira simples de salvar em massa as Q&As de rascunho que precisam de edições ou atualizações adicionais.</span><span class="sxs-lookup"><span data-stu-id="dd3db-105">It's also a simple way to bulk save draft Q&As that need additional edits or updates.</span></span> <span data-ttu-id="dd3db-106">Se você precisar editar em massa o Q&As existente, exporte-os do portal de administração, faça as edições necessárias e importe-as.</span><span class="sxs-lookup"><span data-stu-id="dd3db-106">If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="dd3db-107">No canto superior direito da seção Q&As, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="dd3db-107">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="dd3db-108">Clique em **baixar modelo do Q&A (. csv)**</span><span class="sxs-lookup"><span data-stu-id="dd3db-108">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="dd3db-109">Salve e abra o arquivo. csv</span><span class="sxs-lookup"><span data-stu-id="dd3db-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="dd3db-110">Adicione o conteúdo e as configurações do Q&A e salve o arquivo</span><span class="sxs-lookup"><span data-stu-id="dd3db-110">Add the Q&A content and settings and save the file</span></span>

    <span data-ttu-id="dd3db-111">O arquivo. csv deve ser salvo como um arquivo CSV UTF-8, outros tipos de arquivo e codificações podem causar erros de importação</span><span class="sxs-lookup"><span data-stu-id="dd3db-111">The .csv file should be saved as a CSV UTF-8 file, other file types and or encodings may cause import errors</span></span>
    
5. <span data-ttu-id="dd3db-112">No canto superior direito da seção Q&As, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="dd3db-112">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="dd3db-113">No painel importar Q&As, clique em **procurar** e navegue até o arquivo. csv que você deseja importar</span><span class="sxs-lookup"><span data-stu-id="dd3db-113">In the Import Q&As pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="dd3db-114">Clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="dd3db-114">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="dd3db-115">Impedir erros de importação</span><span class="sxs-lookup"><span data-stu-id="dd3db-115">Prevent import errors</span></span>      
<span data-ttu-id="dd3db-116">Você receberá um erro se os dados necessários estiverem ausentes ou forem inválidos.</span><span class="sxs-lookup"><span data-stu-id="dd3db-116">You'll get an error if any required data is missing or invalid.</span></span> <span data-ttu-id="dd3db-117">Dependendo do erro, um arquivo de log pode ser gerado com mais informações sobre as linhas e colunas que precisam ser corrigidas.</span><span class="sxs-lookup"><span data-stu-id="dd3db-117">Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected.</span></span> <span data-ttu-id="dd3db-118">Faça as edições necessárias e tente importar o arquivo novamente.</span><span class="sxs-lookup"><span data-stu-id="dd3db-118">Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="dd3db-119">Até que todos os erros sejam resolvidos, não será possível criar ou editar qualquer Q&As.</span><span class="sxs-lookup"><span data-stu-id="dd3db-119">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="dd3db-120">Para ajudar a evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente:</span><span class="sxs-lookup"><span data-stu-id="dd3db-120">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="dd3db-121">Inclui a linha de cabeçalho que estava no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="dd3db-121">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="dd3db-122">Inclui todas as colunas que estavam no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="dd3db-122">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="dd3db-123">A ordem da coluna é o mesmo que o modelo de importação</span><span class="sxs-lookup"><span data-stu-id="dd3db-123">The column order is the same as the import template</span></span>
- <span data-ttu-id="dd3db-124">Essas colunas podem estar vazias: ID, última modificação e última modificação por</span><span class="sxs-lookup"><span data-stu-id="dd3db-124">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="dd3db-125">A coluna de estado não pode ficar vazia, essas informações são necessárias</span><span class="sxs-lookup"><span data-stu-id="dd3db-125">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="dd3db-126">Com base no campo Estado, Q&As será salvo como rascunho, sugerido, agendado ou será publicado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="dd3db-126">Based on the State field, Q&As will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="dd3db-127">Além disso, se você incluir a ID de um Q&A existente, ele será substituído pelas informações no arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="dd3db-127">Also, if you include the Id of an existing Q&A, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="dd3db-128">Para organizações com vários locatários, você pode exportar seu Q&As de um locatário e importá-lo para outro.</span><span class="sxs-lookup"><span data-stu-id="dd3db-128">For organizations with mulitple tenants, you can export your Q&As from one tenant and import it into another.</span></span> <span data-ttu-id="dd3db-129">Mas você deve remover todos os dados na coluna ID antes de importar.</span><span class="sxs-lookup"><span data-stu-id="dd3db-129">But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="dd3db-130">Para saber mais sobre os campos obrigatórios e recomendados, consulte [criar Q&As](create-qas.md).</span><span class="sxs-lookup"><span data-stu-id="dd3db-130">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

