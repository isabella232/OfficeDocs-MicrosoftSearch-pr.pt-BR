---
title: Criar Q&As em massa
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
ms.openlocfilehash: 53f1d167948f6b621ad139620553df51b0cb91c2
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068391"
---
# <a name="bulk-create-qas"></a><span data-ttu-id="cfb17-103">Criar Q&As em massa</span><span class="sxs-lookup"><span data-stu-id="cfb17-103">Bulk create Q&As</span></span>

<span data-ttu-id="cfb17-p101">Baixe e use o modelo. csv para criar ou editar em massa Q&As. Também é uma maneira simples de salvar em massa as Q&As de rascunho que precisam de edições ou atualizações adicionais. Se você precisar editar em massa o Q&As existente, exporte-os do portal de administração, faça as edições necessárias e importe-as.</span><span class="sxs-lookup"><span data-stu-id="cfb17-p101">Download and use the .csv template to bulk create or bulk edit Q&As. It's also a simple way to bulk save draft Q&As that need additional edits or updates. If you need to bulk edit existing Q&As, export them from the Admin portal, make the necessary edits, and then import them.</span></span>
  
1. <span data-ttu-id="cfb17-107">No canto superior direito da seção Q&As, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="cfb17-107">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
2. <span data-ttu-id="cfb17-108">Clique em **baixar modelo do Q&A (. csv)**</span><span class="sxs-lookup"><span data-stu-id="cfb17-108">Click **Download Q&A template (.csv)**</span></span>
    
3. <span data-ttu-id="cfb17-109">Salve e abra o arquivo. csv</span><span class="sxs-lookup"><span data-stu-id="cfb17-109">Save and open the .csv file</span></span>
    
4. <span data-ttu-id="cfb17-110">Adicione o conteúdo e as configurações do Q&A e salve o arquivo</span><span class="sxs-lookup"><span data-stu-id="cfb17-110">Add the Q&A content and settings and save the file</span></span>
    
5. <span data-ttu-id="cfb17-111">No canto superior direito da seção Q&As, clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="cfb17-111">In the upper-right corner of the Q&As section, click **Import**</span></span>
    
6. <span data-ttu-id="cfb17-112">No painel importar Q&As, clique em **procurar** e navegue até o arquivo. csv que você deseja importar</span><span class="sxs-lookup"><span data-stu-id="cfb17-112">In the Import Q&As pane, click **Browse** and navigate to the .csv file you want to import</span></span> 
    
7. <span data-ttu-id="cfb17-113">Clique em **importar**</span><span class="sxs-lookup"><span data-stu-id="cfb17-113">Click **Import**</span></span>

# <a name="prevent-import-errors"></a><span data-ttu-id="cfb17-114">Impedir erros de importação</span><span class="sxs-lookup"><span data-stu-id="cfb17-114">Prevent import errors</span></span>      
<span data-ttu-id="cfb17-p102">Você receberá um erro se os dados necessários estiverem ausentes ou forem inválidos. Dependendo do erro, um arquivo de log pode ser gerado com mais informações sobre as linhas e colunas que precisam ser corrigidas. Faça as edições necessárias e tente importar o arquivo novamente.</span><span class="sxs-lookup"><span data-stu-id="cfb17-p102">You'll get an error if any required data is missing or invalid. Depending on the error, a log file may be generated with more information about the rows and columns that need to be corrected. Make any necessary edits, and try importing the file again.</span></span>

> [!NOTE]
> <span data-ttu-id="cfb17-118">Até que todos os erros sejam resolvidos, não será possível criar ou editar qualquer Q&As.</span><span class="sxs-lookup"><span data-stu-id="cfb17-118">Until all errors are resolved, you can't create or edit any Q&As.</span></span> 

<span data-ttu-id="cfb17-119">Para ajudar a evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente:</span><span class="sxs-lookup"><span data-stu-id="cfb17-119">To help prevent errors, make sure your import file is properly formatted:</span></span>
- <span data-ttu-id="cfb17-120">Inclui a linha de cabeçalho que estava no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="cfb17-120">Includes the header row that was in the import template</span></span>
- <span data-ttu-id="cfb17-121">Inclui todas as colunas que estavam no modelo de importação</span><span class="sxs-lookup"><span data-stu-id="cfb17-121">Includes all columns that were in the import template</span></span>
- <span data-ttu-id="cfb17-122">A ordem da coluna é o mesmo que o modelo de importação</span><span class="sxs-lookup"><span data-stu-id="cfb17-122">The column order is the same as the import template</span></span>
- <span data-ttu-id="cfb17-123">Essas colunas podem estar vazias: ID, última modificação e última modificação por</span><span class="sxs-lookup"><span data-stu-id="cfb17-123">These columns can be empty: Id, Last Modified, and Last Modified By</span></span>
- <span data-ttu-id="cfb17-124">A coluna de estado não pode ficar vazia, essas informações são necessárias</span><span class="sxs-lookup"><span data-stu-id="cfb17-124">The State column can't be empty, this information is required</span></span>  
<span data-ttu-id="cfb17-125">Com base no campo Estado, Q&As será salvo como rascunho, sugerido, agendado ou será publicado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="cfb17-125">Based on the State field, Q&As will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>

<span data-ttu-id="cfb17-126">Além disso, se você incluir a ID de um Q&A existente, ele será substituído pelas informações no arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="cfb17-126">Also, if you include the Id of an existing Q&A, it will be replaced with the information in the import file.</span></span>

<span data-ttu-id="cfb17-p103">Para organizações com vários locatários, você pode exportar seu Q&As de um locatário e importá-lo para outro. Mas você deve remover todos os dados na coluna ID antes de importar.</span><span class="sxs-lookup"><span data-stu-id="cfb17-p103">For organizations with mulitple tenants, you can export your Q&As from one tenant and import it into another. But you must remove all of the data in the Id column before you import.</span></span>

<span data-ttu-id="cfb17-129">Para saber mais sobre os campos obrigatórios e recomendados, consulte [criar Q&As](create-qas.md).</span><span class="sxs-lookup"><span data-stu-id="cfb17-129">To find out more about required and recommended fields, see [Create Q&As](create-qas.md).</span></span>

  

