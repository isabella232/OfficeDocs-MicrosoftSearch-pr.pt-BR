---
title: Gerenciar P e R
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 05/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Encontre e atualize as respostas individualmente ou use as ferramentas da Pesquisa da Microsoft disponíveis para editar todas elas de uma só vez
ms.openlocfilehash: 8620842e64a40eb32467c42a289bdec3b67d303b
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591517"
---
# <a name="manage-qas"></a><span data-ttu-id="10afa-103">Gerenciar P e R</span><span class="sxs-lookup"><span data-stu-id="10afa-103">Manage Q&As</span></span>

<span data-ttu-id="10afa-104">A criação de P e R é semelhante à criação de indicadores.</span><span class="sxs-lookup"><span data-stu-id="10afa-104">Creating a Q&A is similar to creating bookmarks.</span></span> <span data-ttu-id="10afa-105">As P e R permitem que você responda uma pergunta do usuário, em vez de apenas fornecer um link para uma página da Web.</span><span class="sxs-lookup"><span data-stu-id="10afa-105">Q&A allows you to answer the user's question instead of just providing a link to webpage.</span></span> <span data-ttu-id="10afa-106">Você pode formatar a resposta em rich text usando as ferramentas disponíveis.</span><span class="sxs-lookup"><span data-stu-id="10afa-106">You can format the answer in rich text using the available tools.</span></span> <span data-ttu-id="10afa-107">Se um indicador e um P e R compartilham a mesma palavra-chave, o resultado do indicador é mostrado primeiro.</span><span class="sxs-lookup"><span data-stu-id="10afa-107">If a Bookmark and a Q&A share the same keyword, the Bookmark result is shown first.</span></span> <span data-ttu-id="10afa-108">Como os Indicadores, o índice de P e R é atualizado imediatamente depois que um P e R é adicionado ou alterado.</span><span class="sxs-lookup"><span data-stu-id="10afa-108">Like Bookmarks, the Q&A index is refreshed immediately after a Q&A is added or changed.</span></span> 

## <a name="add-or-edit-a-single-qa"></a><span data-ttu-id="10afa-109">Adicione ou edite um único P e R</span><span class="sxs-lookup"><span data-stu-id="10afa-109">Add or edit a single Q&A</span></span>
1. <span data-ttu-id="10afa-110">Vá para o **centro de administração do Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="10afa-110">Go to **Microsoft 365 admin center**.</span></span>
1. <span data-ttu-id="10afa-111">No painel de navegação, vá para **Configurações** e selecione **Pesquisa da Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="10afa-111">In the navigation pane, go to **Settings** and select **Microsoft Search**.</span></span>
1. <span data-ttu-id="10afa-112">Selecione a guia **P e R**. Por padrão, a primeira guia (**Indicadores**) se encontra selecionada.</span><span class="sxs-lookup"><span data-stu-id="10afa-112">Select **Q&A** tab. By default, the first tab (**Bookmarks**) is selected.</span></span>
1. <span data-ttu-id="10afa-113">Para adicionar P e R, selecione **Adicionar novo**.</span><span class="sxs-lookup"><span data-stu-id="10afa-113">To add a Q&A, select **Add new**.</span></span>
<span data-ttu-id="10afa-114">Para editar P e R, selecione o P e R na lista P e R relevante.</span><span class="sxs-lookup"><span data-stu-id="10afa-114">To edit a Q&A, select the Q&A in the relevant Q&A list.</span></span>
1. <span data-ttu-id="10afa-115">À medida que você adiciona ou edita as informações, a visualização é atualizada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="10afa-115">As you add or edit the information, the preview automatically updates.</span></span>
1. <span data-ttu-id="10afa-116">Salve suas alterações.</span><span class="sxs-lookup"><span data-stu-id="10afa-116">Save your changes.</span></span>

### <a name="supported-html-tags"></a><span data-ttu-id="10afa-117">Tags HTML com suporte</span><span class="sxs-lookup"><span data-stu-id="10afa-117">Supported HTML tags</span></span>
<span data-ttu-id="10afa-118">Você pode usar o conteúdo HTML existente ou adicionar tags HTML à sua resposta (descrição).</span><span class="sxs-lookup"><span data-stu-id="10afa-118">You can use existing HTML content or add HTML tags to your answer (description).</span></span> <span data-ttu-id="10afa-119">Tags não compatíveis são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="10afa-119">Unsupported tags are ignored.</span></span>  
<span data-ttu-id="10afa-120">As seguintes tags HTML são compatíveis:</span><span class="sxs-lookup"><span data-stu-id="10afa-120">The following HTML tags are supported:</span></span>
- <span data-ttu-id="10afa-121">blockquote</span><span class="sxs-lookup"><span data-stu-id="10afa-121">blockquote</span></span>
- <span data-ttu-id="10afa-122">div</span><span class="sxs-lookup"><span data-stu-id="10afa-122">div</span></span>
- <span data-ttu-id="10afa-123">em</span><span class="sxs-lookup"><span data-stu-id="10afa-123">em</span></span>
- <span data-ttu-id="10afa-124">h1, h2, h3 e h4</span><span class="sxs-lookup"><span data-stu-id="10afa-124">h1, h2, h3, and h4</span></span>
- <span data-ttu-id="10afa-125">ol, ul e li</span><span class="sxs-lookup"><span data-stu-id="10afa-125">ol, ul, and li</span></span>
- <span data-ttu-id="10afa-126">p</span><span class="sxs-lookup"><span data-stu-id="10afa-126">p</span></span>
- <span data-ttu-id="10afa-127">pre</span><span class="sxs-lookup"><span data-stu-id="10afa-127">pre</span></span>
- <span data-ttu-id="10afa-128">span</span><span class="sxs-lookup"><span data-stu-id="10afa-128">span</span></span>
- <span data-ttu-id="10afa-129">strong</span><span class="sxs-lookup"><span data-stu-id="10afa-129">strong</span></span>
- <span data-ttu-id="10afa-130">table, thead, tbody, tr, th e td</span><span class="sxs-lookup"><span data-stu-id="10afa-130">table, thead, tbody, tr, th, and td</span></span>
- <span data-ttu-id="10afa-131">u</span><span class="sxs-lookup"><span data-stu-id="10afa-131">u</span></span>
- <span data-ttu-id="10afa-132">a</span><span class="sxs-lookup"><span data-stu-id="10afa-132">a</span></span>
- <span data-ttu-id="10afa-133">code</span><span class="sxs-lookup"><span data-stu-id="10afa-133">code</span></span>
- <span data-ttu-id="10afa-134">br</span><span class="sxs-lookup"><span data-stu-id="10afa-134">br</span></span>
- <span data-ttu-id="10afa-135">hr</span><span class="sxs-lookup"><span data-stu-id="10afa-135">hr</span></span>
- <span data-ttu-id="10afa-136">img</span><span class="sxs-lookup"><span data-stu-id="10afa-136">img</span></span>

## <a name="bulk-add-or-edit-qas"></a><span data-ttu-id="10afa-137">Adicionar ou editar P e R em massa</span><span class="sxs-lookup"><span data-stu-id="10afa-137">Bulk add or edit Q&A</span></span>
<span data-ttu-id="10afa-138">Os administradores podem usar os recursos de importação e exportação para criar ou editar P e R em massa.</span><span class="sxs-lookup"><span data-stu-id="10afa-138">Administrators can use the Import and Export features to bulk create or edit Q&A.</span></span> <span data-ttu-id="10afa-139">Esse é um recurso útil quando os administradores precisam adicionar ou editar um grande número de P e R.</span><span class="sxs-lookup"><span data-stu-id="10afa-139">This is a useful feature when administrators need to add or edit a large number of Q&A.</span></span> 

<span data-ttu-id="10afa-140">Use o recurso de importação/exportação para:</span><span class="sxs-lookup"><span data-stu-id="10afa-140">Use the import/export feature to:</span></span>
1. <span data-ttu-id="10afa-141">Adicionar P e R em massa - Adicione detalhes no arquivo de modelo P e R e importe-o.</span><span class="sxs-lookup"><span data-stu-id="10afa-141">Bulk add Q&A - Add details in the Q&A template file, and then import it.</span></span>
1. <span data-ttu-id="10afa-142">Edição em massa de P e R - Exporte P e R para um ficheiro .csv, edite os detalhes de P e R no ficheiro .csv exportado e, em seguida, importe o ficheiro .csv.</span><span class="sxs-lookup"><span data-stu-id="10afa-142">Bulk edit Q&A - Export Q&A to a .csv file, then edit the Q&A details in the exported .csv file, and then import the .csv file.</span></span>
1. <span data-ttu-id="10afa-143">Backup de P e R - Exporte P e R para um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="10afa-143">Backup Q&A - Export Q&A to a .csv file.</span></span>

<span data-ttu-id="10afa-144">Para importar ou exportar P e R:</span><span class="sxs-lookup"><span data-stu-id="10afa-144">To import or export Q&A:</span></span>
1. <span data-ttu-id="10afa-145">No canto superior direito da guia P e R, selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="10afa-145">In the upper-right corner of the Q&A tab, select **Import**.</span></span> <span data-ttu-id="10afa-146">Selecione **Exportar** para baixar todas as P e R existentes em um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="10afa-146">Select **Export** to download all the existing Q&A in a .csv file.</span></span>
1. <span data-ttu-id="10afa-147">No painel direito, escolha a opção de importar usando um arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="10afa-147">In the right pane, choose the option to import using a .csv file.</span></span>
<span data-ttu-id="10afa-148">Faça o download do arquivo de modelo para obter uma lista dos campos e detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="10afa-148">Download the template file for a list of the required fields and details.</span></span> 
1. <span data-ttu-id="10afa-149">Adicione ou edite os detalhes de P e R no arquivo de modelo e salve-o no seu computador.</span><span class="sxs-lookup"><span data-stu-id="10afa-149">Add or edit Q&A details in the template file and save it on your computer.</span></span> 
1. <span data-ttu-id="10afa-150">No painel **Importar P e R**, selecione **Procurar** e, em seguida, o arquivo .csv que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="10afa-150">In the **Import Q&A** pane, select **Browse**, and then the .csv file that you want to import.</span></span>
1. <span data-ttu-id="10afa-151">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="10afa-151">Select **Import**.</span></span>

<span data-ttu-id="10afa-152">Aqui estão alguns pontos importantes sobre o arquivo de modelo:</span><span class="sxs-lookup"><span data-stu-id="10afa-152">Here are some important points regarding the template file:</span></span>
- <span data-ttu-id="10afa-153">Nunca edite os dados nesses campos: *Id*, *Última modificação* e *Última modificação por*</span><span class="sxs-lookup"><span data-stu-id="10afa-153">Never edit data in these fields: *Id*, *Last Modified*, and *Last Modified By*</span></span>
- <span data-ttu-id="10afa-154">Se você incluir o *Id* de um indicador existente, ele será substituído pelas informações no arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="10afa-154">If you include the *Id* of an existing bookmark, it will be replaced with the information in the import file.</span></span>
- <span data-ttu-id="10afa-155">Se houver um indicador existente com o mesmo título ou URL, o indicador será atualizado com informações no arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="10afa-155">If there is an existing bookmark with the same title or URL, the bookmark will be updated with information in the import file.</span></span>
- <span data-ttu-id="10afa-156">Nem todos os campos no arquivo de modelo são obrigatórios, e os campos obrigatórios variam dependendo do estado do indicador.</span><span class="sxs-lookup"><span data-stu-id="10afa-156">Not all fields in the template file are required and required fields vary depending on the bookmark state.</span></span>
- <span data-ttu-id="10afa-157">Com base no campo Estado, os indicadores serão salvos como rascunho, sugerido ou programado, ou serão publicados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="10afa-157">Based on the State field, bookmarks will be saved as draft, suggested, scheduled, or they will be published automatically.</span></span>
- <span data-ttu-id="10afa-158">Para organizações com vários locatários, você pode exportar seus indicadores de um locatário e importá-lo para outro.</span><span class="sxs-lookup"><span data-stu-id="10afa-158">For organizations with multiple tenants, you can export your bookmarks from one tenant and import it into another.</span></span> <span data-ttu-id="10afa-159">Mas você deve remover os dados na coluna *Id* antes de importar.</span><span class="sxs-lookup"><span data-stu-id="10afa-159">But you must remove the data in the *Id* column before you import.</span></span>

<span data-ttu-id="10afa-160">**Observação:** Você não pode importar P e R se houver algum erro no arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="10afa-160">**Note:** You cannot import Q&A if there are any errors in the template file.</span></span> <span data-ttu-id="10afa-161">Para evitar erros, verifique se o arquivo de importação está formatado corretamente e inclua todas as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="10afa-161">To prevent errors, make sure your import file is properly formatted and include all the required information.</span></span> 

<span data-ttu-id="10afa-162">Para obter mais informações sobre como evitar erros, consulte [Evite erros de importação](manage-bookmarks.md#prevent-import-errors).</span><span class="sxs-lookup"><span data-stu-id="10afa-162">For more information on how to prevent error, see [Prevent import errors](manage-bookmarks.md#prevent-import-errors).</span></span>