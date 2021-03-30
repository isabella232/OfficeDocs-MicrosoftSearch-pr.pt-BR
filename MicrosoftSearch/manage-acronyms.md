---
title: Gerenciar respostas de acrônimo na Pesquisa da Microsoft
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Criar e atualizar respostas de acrônimos na Pesquisa da Microsoft
ms.openlocfilehash: 013510da28599f41c9dc4bf74da99efa2f6c3e97
ms.sourcegitcommit: 62cb7b8c6a311760cc728f2c70a9a22ca76e977e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408710"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="75424-103">Gerenciar respostas de acrônimos na Pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="75424-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="75424-104">Os usuários geralmente têm acrônimos e abreviações desconhecidos usados por sua organização ou equipe.</span><span class="sxs-lookup"><span data-stu-id="75424-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="75424-105">Os termos específicos para organizações ou equipes podem ser novos para pessoas que se movem de uma equipe para outra, trabalham com equipes de parceiros internas ou são novos para a organização.</span><span class="sxs-lookup"><span data-stu-id="75424-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="75424-106">As organizações nem sempre têm uma única referência para sua terminologia padrão.</span><span class="sxs-lookup"><span data-stu-id="75424-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="75424-107">A falta de uma única referência torna difícil encontrar definições para esses acrônimos.</span><span class="sxs-lookup"><span data-stu-id="75424-107">Lack of a single reference makes it hard to find definitions for these acronyms.</span></span> <span data-ttu-id="75424-108">A Pesquisa da Microsoft resolve esse problema com acrônimos.</span><span class="sxs-lookup"><span data-stu-id="75424-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="75424-109">O que os usuários experimentam</span><span class="sxs-lookup"><span data-stu-id="75424-109">What users experience</span></span>

<span data-ttu-id="75424-110">Os usuários da Pesquisa da Microsoft podem obter definições com acrônimos no [Bing,](https://Bing.com) [no SharePoint](https://products.office.com/sharepoint/collaboration)e [no Office 365](https://Office.com).</span><span class="sxs-lookup"><span data-stu-id="75424-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="75424-111">Na caixa **Pesquisa,** os usuários entram em consultas como estes exemplos:</span><span class="sxs-lookup"><span data-stu-id="75424-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="75424-112">*O que é* DNN</span><span class="sxs-lookup"><span data-stu-id="75424-112">*What is* DNN</span></span>
- <span data-ttu-id="75424-113">*Definir* DNN</span><span class="sxs-lookup"><span data-stu-id="75424-113">*Define* DNN</span></span>
- <span data-ttu-id="75424-114">Definição de *DNN*</span><span class="sxs-lookup"><span data-stu-id="75424-114">DNN *definition*</span></span>
- <span data-ttu-id="75424-115">*Expandir* DNN</span><span class="sxs-lookup"><span data-stu-id="75424-115">*Expand* DNN</span></span>
- <span data-ttu-id="75424-116">Expansão  de DNN</span><span class="sxs-lookup"><span data-stu-id="75424-116">DNN *expansion*</span></span>
- <span data-ttu-id="75424-117">*Significado de* DNN</span><span class="sxs-lookup"><span data-stu-id="75424-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="75424-118">DNN *significa*</span><span class="sxs-lookup"><span data-stu-id="75424-118">DNN *means*</span></span>
- <span data-ttu-id="75424-119">DNN *significa*</span><span class="sxs-lookup"><span data-stu-id="75424-119">DNN *stands for*</span></span>

<span data-ttu-id="75424-120">O resultado inclui todos os significados de DNN presentes na organização do usuário.</span><span class="sxs-lookup"><span data-stu-id="75424-120">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="75424-121">Os usuários devem inserir uma consulta que inclua as palavras-chave *especificadas* do acrônimo para disparar suas respostas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="75424-121">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="75424-122">As consultas de acrônimo não são sensíveis a minúsculas.</span><span class="sxs-lookup"><span data-stu-id="75424-122">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="75424-123">Configurar respostas de acrônimos</span><span class="sxs-lookup"><span data-stu-id="75424-123">Set up acronyms answers</span></span>

<span data-ttu-id="75424-124">No Centro de administração do [Microsoft 365,](https://admin.microsoft.com)vá para [**Acrônimos**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)e selecione **Adicionar acrônimo**.</span><span class="sxs-lookup"><span data-stu-id="75424-124">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="75424-125">A Pesquisa da Microsoft consulta duas fontes de dados para fornecer respostas de acrônimos às pesquisas dos usuários:</span><span class="sxs-lookup"><span data-stu-id="75424-125">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="75424-126">**Admin-curated**.</span><span class="sxs-lookup"><span data-stu-id="75424-126">**Admin-curated**.</span></span> <span data-ttu-id="75424-127">Fornecido por administradores de IT no [centro de administração](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span><span class="sxs-lookup"><span data-stu-id="75424-127">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="75424-128">**Cura do sistema**.</span><span class="sxs-lookup"><span data-stu-id="75424-128">**System-curated**.</span></span> <span data-ttu-id="75424-129">Descoberta pela Pesquisa da Microsoft a partir de emails e documentos dos usuários, bem como dados disponíveis publicamente dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="75424-129">Discovered by Microsoft Search from users' email and documents, as well as publicly available data within the organization.</span></span>

### <a name="set-up-admin-curated-acronyms"></a><span data-ttu-id="75424-130">Configurar acrônimos com cura de administrador</span><span class="sxs-lookup"><span data-stu-id="75424-130">Set up Admin-curated acronyms</span></span>

<span data-ttu-id="75424-131">Os administradores de pesquisa podem adicionar acrônimos na [guia Acrônimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) no centro de [administração da Pesquisa da Microsoft.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)</span><span class="sxs-lookup"><span data-stu-id="75424-131">Search administrators can add acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="75424-132">Você pode adicionar acrônimos de qualquer site interno ou repositório ao centro de administração.</span><span class="sxs-lookup"><span data-stu-id="75424-132">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="75424-133">Esses acrônimos podem ser adicionados **ao estado Publicado** ou **Rascunho:**</span><span class="sxs-lookup"><span data-stu-id="75424-133">These acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="75424-134">**Estado publicado**.</span><span class="sxs-lookup"><span data-stu-id="75424-134">**Published state**.</span></span> <span data-ttu-id="75424-135">Os acrônimos estão disponíveis para os usuários da organização por meio da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75424-135">Acronyms are available to the organization’s users through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="75424-136">Pode levar até três dias para que os acrônimos adicionados ao estado publicado se tornem disponíveis na Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75424-136">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="75424-137">**Estado de rascunho**.</span><span class="sxs-lookup"><span data-stu-id="75424-137">**Draft state**.</span></span> <span data-ttu-id="75424-138">Se você quiser revisar um acrônimo antes de disponibilizar na Pesquisa da Microsoft, você pode adicionar o acrônimo em um estado rascunho.</span><span class="sxs-lookup"><span data-stu-id="75424-138">If you want to review an acronym before making it available in Microsoft Search, you can add the acronym in a Draft state.</span></span> <span data-ttu-id="75424-139">Os acrônimos no estado Rascunho não aparecerão nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="75424-139">Acronyms in the Draft state will not appear in search results.</span></span> <span data-ttu-id="75424-140">Você precisará mover o acrônimo para o estado Publicado para torná-lo exibido nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="75424-140">You will need to move the acronym to the Published state to make it appear in search results.</span></span>

<span data-ttu-id="75424-141">**Estado excluído**.</span><span class="sxs-lookup"><span data-stu-id="75424-141">**Excluded state**.</span></span> <span data-ttu-id="75424-142">Se você quiser impedir que um acrônimo apareça na Pesquisa da Microsoft, use **Excluir um acrônimo** para adicioná-lo.</span><span class="sxs-lookup"><span data-stu-id="75424-142">If you want to prevent an acronym from appearing in Microsoft Search, use **Exclude an acronym** to add it.</span></span> <span data-ttu-id="75424-143">Para impedir que um acrônimo seja excluído, você precisará excluir o acrônimo excluído e adicioná-lo ou verificar se ele está em sua lista publicada.</span><span class="sxs-lookup"><span data-stu-id="75424-143">To stop an acronym from being excluded, you'll need to delete the excluded acronym and add it or verify it's in your published list.</span></span>

<span data-ttu-id="75424-144">Você pode adicionar acrônimos individualmente ou importá-los em massa em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="75424-144">You can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="75424-145">Carregue um arquivo CSV com os campos mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="75424-145">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="75424-146">Acrônimo (Obrigatório)</span><span class="sxs-lookup"><span data-stu-id="75424-146">Acronym (Mandatory)</span></span> | <span data-ttu-id="75424-147">Representa (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="75424-147">Stands for (Mandatory)</span></span> | <span data-ttu-id="75424-148">Url</span><span class="sxs-lookup"><span data-stu-id="75424-148">Url</span></span> | <span data-ttu-id="75424-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="75424-149">Description</span></span>  | <span data-ttu-id="75424-150">Estado (Obrigatório)</span><span class="sxs-lookup"><span data-stu-id="75424-150">State (Mandatory)</span></span> | <span data-ttu-id="75424-151">Última Modificação</span><span class="sxs-lookup"><span data-stu-id="75424-151">Last Modified</span></span> | <span data-ttu-id="75424-152">Última modificação por</span><span class="sxs-lookup"><span data-stu-id="75424-152">Last Modified By</span></span> | <span data-ttu-id="75424-153">Id</span><span class="sxs-lookup"><span data-stu-id="75424-153">Id</span></span> |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| <span data-ttu-id="75424-154">*XXX*</span><span class="sxs-lookup"><span data-stu-id="75424-154">*XXX*</span></span> | <span data-ttu-id="75424-155">*Abreviação escrita*</span><span class="sxs-lookup"><span data-stu-id="75424-155">*Spelled out abbreviation*</span></span> | <span data-ttu-id="75424-156">*Fonte*</span><span class="sxs-lookup"><span data-stu-id="75424-156">*Source*</span></span> |  | <span data-ttu-id="75424-157">*Publicado, Rascunho ou Excluído*</span><span class="sxs-lookup"><span data-stu-id="75424-157">*Published, Draft, or Excluded*</span></span> |  |  |  |

### <a name="csv-fields"></a><span data-ttu-id="75424-158">Campos CSV</span><span class="sxs-lookup"><span data-stu-id="75424-158">CSV fields</span></span>

<span data-ttu-id="75424-159">**Acrônimo**.</span><span class="sxs-lookup"><span data-stu-id="75424-159">**Acronym**.</span></span> <span data-ttu-id="75424-160">Contém o formulário curto ou acrônimo real.</span><span class="sxs-lookup"><span data-stu-id="75424-160">Contains the actual short form or acronym.</span></span> <span data-ttu-id="75424-161">Um exemplo é *DNN*.</span><span class="sxs-lookup"><span data-stu-id="75424-161">An example is *DNN*.</span></span>

<span data-ttu-id="75424-162">**Significa**.</span><span class="sxs-lookup"><span data-stu-id="75424-162">**Stands for**.</span></span> <span data-ttu-id="75424-163">Contém a definição do acrônimo.</span><span class="sxs-lookup"><span data-stu-id="75424-163">Contains the definition of the acronym.</span></span> <span data-ttu-id="75424-164">Um exemplo é *Rede Neural Profunda*.</span><span class="sxs-lookup"><span data-stu-id="75424-164">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="75424-165">**Descrição**.</span><span class="sxs-lookup"><span data-stu-id="75424-165">**Description**.</span></span> <span data-ttu-id="75424-166">Uma breve descrição do acrônimo que fornece aos usuários mais informações sobre o acrônimo e sua definição.</span><span class="sxs-lookup"><span data-stu-id="75424-166">A brief description of the acronym that gives users more info about the acronym and its definition.</span></span> <span data-ttu-id="75424-167">Por exemplo, uma rede neural profunda é uma rede neural com um determinado nível de complexidade, uma rede *neural com mais de duas camadas*.</span><span class="sxs-lookup"><span data-stu-id="75424-167">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="75424-168">**Fonte**.</span><span class="sxs-lookup"><span data-stu-id="75424-168">**Source**.</span></span> <span data-ttu-id="75424-169">A URL da página ou site onde você deseja que os usuários acessem para obter mais informações sobre o acrônimo.</span><span class="sxs-lookup"><span data-stu-id="75424-169">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="75424-170">**Estado**.</span><span class="sxs-lookup"><span data-stu-id="75424-170">**State**.</span></span> <span data-ttu-id="75424-171">Este campo pode ter dois valores:</span><span class="sxs-lookup"><span data-stu-id="75424-171">This field can take two values:</span></span>

- <span data-ttu-id="75424-172">**Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="75424-172">**Draft**.</span></span> <span data-ttu-id="75424-173">Adiciona o acrônimo ao estado Rascunho.</span><span class="sxs-lookup"><span data-stu-id="75424-173">Adds the acronym to the Draft state.</span></span>
- <span data-ttu-id="75424-174">**Publicado**.</span><span class="sxs-lookup"><span data-stu-id="75424-174">**Published**.</span></span> <span data-ttu-id="75424-175">Adiciona o acrônimo ao estado Publicado e o disponibiliza na Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75424-175">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>
- <span data-ttu-id="75424-176">**Excluído**.</span><span class="sxs-lookup"><span data-stu-id="75424-176">**Excluded**.</span></span> <span data-ttu-id="75424-177">Adiciona o acrônimo ao estado Excluído e impede que ele apareça na Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75424-177">Adds the acronym to the Excluded state and prevents it from appearing in Microsoft Search.</span></span>

### <a name="system-curated-acronyms"></a><span data-ttu-id="75424-178">Acrônimos com cura do sistema</span><span class="sxs-lookup"><span data-stu-id="75424-178">System-curated acronyms</span></span>

<span data-ttu-id="75424-179">Pode ser um desafio para os administradores adicionarem todos os acrônimos usados em uma organização ao Answers.</span><span class="sxs-lookup"><span data-stu-id="75424-179">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="75424-180">Esse recurso pode encontrar acrônimos que os administradores de pesquisa nem sabem.</span><span class="sxs-lookup"><span data-stu-id="75424-180">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="75424-181">Para fazer esse trabalho, a Pesquisa da Microsoft também descobre e cura acrônimos dessas fontes:</span><span class="sxs-lookup"><span data-stu-id="75424-181">To do that work, Microsoft Search also discovers and curates acronyms from these sources:</span></span>

- <span data-ttu-id="75424-182">Emails dos usuários</span><span class="sxs-lookup"><span data-stu-id="75424-182">Users’ emails</span></span>
- <span data-ttu-id="75424-183">Documentos no [SharePoint,](https://products.office.com/sharepoint/collaboration) [Microsoft OneDrive]( https://onedrive.live.com/about/)e [Microsoft OneNote](https://www.onenote.com/)</span><span class="sxs-lookup"><span data-stu-id="75424-183">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/)</span></span>
- <span data-ttu-id="75424-184">Documentos públicos dentro da organização aos qual os usuários têm acesso no SharePoint, OneDrive ou OneNote</span><span class="sxs-lookup"><span data-stu-id="75424-184">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote</span></span>

<span data-ttu-id="75424-185">A Pesquisa da Microsoft garante que somente usuários com acesso e permissões para um documento possam ver os acrônimos descobertos nele.</span><span class="sxs-lookup"><span data-stu-id="75424-185">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are discovered from it.</span></span> <span data-ttu-id="75424-186">Quando um acrônimo é encontrado na caixa de correio de um usuário, somente esse usuário pode ver esse acrônimo.</span><span class="sxs-lookup"><span data-stu-id="75424-186">When an acronym is found in a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="75424-187">Nenhuma configuração é necessária para acrônimos com cura do sistema.</span><span class="sxs-lookup"><span data-stu-id="75424-187">No setup is needed for system-curated acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="75424-188">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="75424-188">Frequently asked questions</span></span>

<span data-ttu-id="75424-189">**P: Como os dados com cura do administrador e do sistema são classificados?**</span><span class="sxs-lookup"><span data-stu-id="75424-189">**Q: How is admin-curated and system-curated data ranked?**</span></span>

<span data-ttu-id="75424-190">**R:** A classificação dos resultados pode variar de pessoa para pessoa, pois os resultados são personalizados para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="75424-190">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span> <span data-ttu-id="75424-191">Nenhuma dessas categorias sempre terá precedência sobre a outra.</span><span class="sxs-lookup"><span data-stu-id="75424-191">Neither of these categories will always take precedence over the other.</span></span>

<span data-ttu-id="75424-192">**P: Quanto tempo leva para que os acrônimos com cura de administrador sejam visíveis na Pesquisa da Microsoft depois que eles são publicados?**</span><span class="sxs-lookup"><span data-stu-id="75424-192">**Q: How long does it take for admin-curated acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="75424-193">**R:**  Leva até um dia para que os acrônimos adicionados ao estado Publicado se tornem disponíveis na Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75424-193">**A:**  It takes up to a day for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="75424-194">**P: Como os usuários acionam respostas de acrônimos?**</span><span class="sxs-lookup"><span data-stu-id="75424-194">**Q: How do users trigger acronyms answers?**</span></span>

<span data-ttu-id="75424-195">**R:** Para obter respostas de acrônimos, os usuários devem inserir padrões de consulta específicos em uma caixa de pesquisa [do Bing,](https://bing.com) [do SharePoint](https://products.office.com/sharepoint/collaboration)ou do [Office 365.](https://Office.com) </span><span class="sxs-lookup"><span data-stu-id="75424-195">**A**: To get acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="75424-196">**P: Quanto tempo leva para que os acrônimos com cura do sistema apareçam depois de receber ou enviar um novo email ou documento?**</span><span class="sxs-lookup"><span data-stu-id="75424-196">**Q: How long does it take for system-curated acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="75424-197">**R:** Os acrônimos encontrados em um novo email ou documento levam até sete dias para aparecerem nos resultados da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75424-197">**A:** Acronyms found in a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="75424-198">**P: O que acontece quando um acrônimo é excluído e publicado?**</span><span class="sxs-lookup"><span data-stu-id="75424-198">**Q: What happens when an acronym is both excluded and published?**</span></span>

<span data-ttu-id="75424-199">**R:** O acrônimo excluído recebe prioridade e impede que o acrônimo publicado apareça nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="75424-199">**A:** The excluded acronym is given priority and prevents the published acronym from appearing in search results.</span></span> <span data-ttu-id="75424-200">Ele não exclui ou remove o acrônimo publicado.</span><span class="sxs-lookup"><span data-stu-id="75424-200">It doesn't delete or remove the published acronym.</span></span>

<span data-ttu-id="75424-201">**P: Quanto tempo leva para um acrônimo ser excluído dos resultados da Pesquisa da Microsoft?**</span><span class="sxs-lookup"><span data-stu-id="75424-201">**Q: How long does it take for an acronym to be excluded from Microsoft Search results?**</span></span>

<span data-ttu-id="75424-202">**R:** Leva até um dia para um acrônimo excluído parar de aparecer nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="75424-202">**A**: It takes up to a day for an excluded acronym to stop appearing in search results.</span></span>

<span data-ttu-id="75424-203">**P: Para acrônimos com cura do sistema, os documentos precisam estar em um formato específico?**</span><span class="sxs-lookup"><span data-stu-id="75424-203">**Q: For system-curated acronyms, do documents need to be in a specific format?**</span></span>

<span data-ttu-id="75424-204">**R:** Não.</span><span class="sxs-lookup"><span data-stu-id="75424-204">**A:** No.</span></span> <span data-ttu-id="75424-205">Suportamos todos os tipos de arquivo, exceto arquivos de imagem, pasta e zip.</span><span class="sxs-lookup"><span data-stu-id="75424-205">We support all file types except image, folder, and zip files.</span></span>

<span data-ttu-id="75424-206">**P: A Microsoft descobrirá acrônimos de documentos em todos os idiomas?**</span><span class="sxs-lookup"><span data-stu-id="75424-206">**Q: Will Microsoft discover acronyms from documents in all languages?**</span></span>

<span data-ttu-id="75424-207">**R:** A Microsoft só dá suporte a acrônimos com cura do sistema a partir de documentos em inglês, espanhol, francês, italiano, alemão e português.</span><span class="sxs-lookup"><span data-stu-id="75424-207">**A**: Microsoft only supports system-curated acronyms from documents in English, Spanish, French, Italian, German, and Portuguese.</span></span> <span data-ttu-id="75424-208">O suporte para outros idiomas será adicionado em fases.</span><span class="sxs-lookup"><span data-stu-id="75424-208">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="75424-209">**P: E se minha organização não quiser mostrar acrônimos com cura do sistema? Posso parar de mostrar esse tipo de acrônimo nos meus resultados de pesquisa?**</span><span class="sxs-lookup"><span data-stu-id="75424-209">**Q: What if my organization doesn’t want to show system-curated acronyms? Can I stop showing this type of acronym in my search results?**</span></span>

<span data-ttu-id="75424-210">**R:** Para desativar a exibição de acrônimos com cura do sistema nos resultados da pesquisa, crie um tíquete de suporte ao cliente seguindo as instruções em [Contact support for business products](/microsoft-365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="75424-210">**A**: To turn off showing system-curated acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](/microsoft-365/admin/contact-support-for-business-products).</span></span>
<span data-ttu-id="75424-211">Depois de criar um tíquete de suporte, leva até 48 horas para que os acrônimos com cura do sistema parem de aparecer nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="75424-211">After you create a support ticket, it takes up to 48 hours for system-curated acronyms to stop appearing in search results.</span></span>
