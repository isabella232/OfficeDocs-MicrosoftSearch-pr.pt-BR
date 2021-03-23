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
ms.openlocfilehash: 5677ff6915c9e43e2559964c40086cb360a05db7
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031364"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="3761f-103">Gerenciar respostas de acrônimos na Pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3761f-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="3761f-104">Os usuários geralmente têm acrônimos e abreviações desconhecidos usados por sua organização ou equipe.</span><span class="sxs-lookup"><span data-stu-id="3761f-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="3761f-105">Os termos específicos para organizações ou equipes podem ser novos para pessoas que se movem de uma equipe para outra, trabalham com equipes de parceiros internas ou são novos para a organização.</span><span class="sxs-lookup"><span data-stu-id="3761f-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="3761f-106">As organizações nem sempre têm uma única referência para sua terminologia padrão.</span><span class="sxs-lookup"><span data-stu-id="3761f-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="3761f-107">A falta de uma única referência torna difícil encontrar definições ou expansões para esses acrônimos.</span><span class="sxs-lookup"><span data-stu-id="3761f-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="3761f-108">A Pesquisa da Microsoft resolve esse problema com acrônimos.</span><span class="sxs-lookup"><span data-stu-id="3761f-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="3761f-109">O que os usuários experimentam</span><span class="sxs-lookup"><span data-stu-id="3761f-109">What users experience</span></span>

<span data-ttu-id="3761f-110">Os usuários da Pesquisa da Microsoft podem obter definições com acrônimos no [Bing,](https://Bing.com) [no SharePoint](https://products.office.com/sharepoint/collaboration)e [no Office 365](https://Office.com).</span><span class="sxs-lookup"><span data-stu-id="3761f-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="3761f-111">Na caixa **Pesquisa,** os usuários entram em consultas como estes exemplos:</span><span class="sxs-lookup"><span data-stu-id="3761f-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="3761f-112">*O que é* DNN</span><span class="sxs-lookup"><span data-stu-id="3761f-112">*What is* DNN</span></span>
- <span data-ttu-id="3761f-113">*Definir* DNN</span><span class="sxs-lookup"><span data-stu-id="3761f-113">*Define* DNN</span></span>
- <span data-ttu-id="3761f-114">Definição de *DNN*</span><span class="sxs-lookup"><span data-stu-id="3761f-114">DNN *definition*</span></span>
- <span data-ttu-id="3761f-115">*Expandir* DNN</span><span class="sxs-lookup"><span data-stu-id="3761f-115">*Expand* DNN</span></span>
- <span data-ttu-id="3761f-116">Expansão  de DNN</span><span class="sxs-lookup"><span data-stu-id="3761f-116">DNN *expansion*</span></span>
- <span data-ttu-id="3761f-117">*Significado de* DNN</span><span class="sxs-lookup"><span data-stu-id="3761f-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="3761f-118">DNN *significa*</span><span class="sxs-lookup"><span data-stu-id="3761f-118">DNN *means*</span></span>

<span data-ttu-id="3761f-119">O resultado inclui todos os significados de DNN presentes na organização do usuário.</span><span class="sxs-lookup"><span data-stu-id="3761f-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="3761f-120">Os usuários devem inserir uma consulta que inclua as palavras-chave *especificadas* do acrônimo para disparar suas respostas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="3761f-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="3761f-121">As consultas de acrônimo não são sensíveis a minúsculas.</span><span class="sxs-lookup"><span data-stu-id="3761f-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="3761f-122">Configurar respostas de acrônimos</span><span class="sxs-lookup"><span data-stu-id="3761f-122">Set up acronyms answers</span></span>

<span data-ttu-id="3761f-123">No Centro de administração do [Microsoft 365,](https://admin.microsoft.com)vá para [**Acrônimos**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)e selecione **Adicionar acrônimo**.</span><span class="sxs-lookup"><span data-stu-id="3761f-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="3761f-124">A Pesquisa da Microsoft consulta duas fontes de dados para fornecer respostas de acrônimos às pesquisas dos usuários:</span><span class="sxs-lookup"><span data-stu-id="3761f-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="3761f-125">**Admin-curated**.</span><span class="sxs-lookup"><span data-stu-id="3761f-125">**Admin-curated**.</span></span> <span data-ttu-id="3761f-126">Fornecido por administradores de IT no [centro de administração](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span><span class="sxs-lookup"><span data-stu-id="3761f-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="3761f-127">**Cura do sistema**.</span><span class="sxs-lookup"><span data-stu-id="3761f-127">**System-curated**.</span></span> <span data-ttu-id="3761f-128">Descoberta pela Pesquisa da Microsoft a partir de emails e documentos dos usuários e dados disponíveis publicamente dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="3761f-128">Discovered by Microsoft Search from users' email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-admin-curated-acronyms"></a><span data-ttu-id="3761f-129">Configurar acrônimos com cura de administrador</span><span class="sxs-lookup"><span data-stu-id="3761f-129">Set up Admin-curated acronyms</span></span>

<span data-ttu-id="3761f-130">Os administradores de pesquisa podem adicionar acrônimos na [guia Acrônimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) no centro de [administração da Pesquisa da Microsoft.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch)</span><span class="sxs-lookup"><span data-stu-id="3761f-130">Search administrators can add acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="3761f-131">Você pode adicionar acrônimos de qualquer site interno ou repositório ao centro de administração.</span><span class="sxs-lookup"><span data-stu-id="3761f-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="3761f-132">Esses acrônimos podem ser adicionados **ao estado Publicado** ou **Rascunho:**</span><span class="sxs-lookup"><span data-stu-id="3761f-132">These acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="3761f-133">**Estado publicado**.</span><span class="sxs-lookup"><span data-stu-id="3761f-133">**Published state**.</span></span> <span data-ttu-id="3761f-134">Os acrônimos estão disponíveis para os usuários da organização por meio da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3761f-134">Acronyms are available to the organization’s users through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="3761f-135">Pode levar até três dias para que os acrônimos adicionados ao estado publicado se tornem disponíveis na Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3761f-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="3761f-136">**Estado de rascunho**.</span><span class="sxs-lookup"><span data-stu-id="3761f-136">**Draft state**.</span></span> <span data-ttu-id="3761f-137">Se você quiser revisar um acrônimo antes de disponibilizar na Pesquisa da Microsoft, você pode adicionar o acrônimo em um estado rascunho.</span><span class="sxs-lookup"><span data-stu-id="3761f-137">If you want to review an acronym before making it available in Microsoft Search, you can add the acronym in a Draft state.</span></span> <span data-ttu-id="3761f-138">Os acrônimos no estado Rascunho não aparecerão nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3761f-138">Acronyms in the Draft state will not appear in search results.</span></span> <span data-ttu-id="3761f-139">Você precisará mover o acrônimo para o estado Publicado para torná-lo exibido nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3761f-139">You will need to move the acronym to the Published state to make it appear in search results.</span></span>

<span data-ttu-id="3761f-140">Você pode adicionar acrônimos individualmente ou importá-los em massa em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="3761f-140">You can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="3761f-141">Carregue um arquivo CSV com os campos mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="3761f-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="3761f-142">Acrônimo (Obrigatório)</span><span class="sxs-lookup"><span data-stu-id="3761f-142">Acronym (Mandatory)</span></span> | <span data-ttu-id="3761f-143">Expansão (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="3761f-143">Expansion (Mandatory)</span></span> | <span data-ttu-id="3761f-144">Url</span><span class="sxs-lookup"><span data-stu-id="3761f-144">Url</span></span> | <span data-ttu-id="3761f-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="3761f-145">Description</span></span>  | <span data-ttu-id="3761f-146">Estado (Obrigatório)</span><span class="sxs-lookup"><span data-stu-id="3761f-146">State (Mandatory)</span></span> | <span data-ttu-id="3761f-147">Última Modificação</span><span class="sxs-lookup"><span data-stu-id="3761f-147">Last Modified</span></span> | <span data-ttu-id="3761f-148">Última modificação por</span><span class="sxs-lookup"><span data-stu-id="3761f-148">Last Modified By</span></span> | <span data-ttu-id="3761f-149">Id</span><span class="sxs-lookup"><span data-stu-id="3761f-149">Id</span></span> |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| <span data-ttu-id="3761f-150">*XXX*</span><span class="sxs-lookup"><span data-stu-id="3761f-150">*XXX*</span></span> | <span data-ttu-id="3761f-151">*Abreviação escrita*</span><span class="sxs-lookup"><span data-stu-id="3761f-151">*Spelled out abbreviation*</span></span> | <span data-ttu-id="3761f-152">*Fonte*</span><span class="sxs-lookup"><span data-stu-id="3761f-152">*Source*</span></span> |  | <span data-ttu-id="3761f-153">*Publicado ou Rascunho*</span><span class="sxs-lookup"><span data-stu-id="3761f-153">*Published or Draft*</span></span> |  |  |  |

### <a name="csv-fields"></a><span data-ttu-id="3761f-154">Campos CSV</span><span class="sxs-lookup"><span data-stu-id="3761f-154">CSV fields</span></span>

<span data-ttu-id="3761f-155">**Acrônimo**.</span><span class="sxs-lookup"><span data-stu-id="3761f-155">**Acronym**.</span></span> <span data-ttu-id="3761f-156">Contém o formulário curto ou acrônimo real.</span><span class="sxs-lookup"><span data-stu-id="3761f-156">Contains the actual short form or acronym.</span></span> <span data-ttu-id="3761f-157">Um exemplo é *DNN*.</span><span class="sxs-lookup"><span data-stu-id="3761f-157">An example is *DNN*.</span></span>

<span data-ttu-id="3761f-158">**Expansão**.</span><span class="sxs-lookup"><span data-stu-id="3761f-158">**Expansion**.</span></span> <span data-ttu-id="3761f-159">Contém a expansão do acrônimo.</span><span class="sxs-lookup"><span data-stu-id="3761f-159">Contains the expansion of the acronym.</span></span> <span data-ttu-id="3761f-160">Um exemplo é *Rede Neural Profunda*.</span><span class="sxs-lookup"><span data-stu-id="3761f-160">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="3761f-161">**Descrição**.</span><span class="sxs-lookup"><span data-stu-id="3761f-161">**Description**.</span></span> <span data-ttu-id="3761f-162">Uma breve descrição do acrônimo que fornece aos usuários mais informações sobre o acrônimo e sua expansão.</span><span class="sxs-lookup"><span data-stu-id="3761f-162">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="3761f-163">Por exemplo, uma rede neural profunda é uma rede neural com um determinado nível de complexidade, uma rede *neural com mais de duas camadas*.</span><span class="sxs-lookup"><span data-stu-id="3761f-163">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="3761f-164">**Fonte**.</span><span class="sxs-lookup"><span data-stu-id="3761f-164">**Source**.</span></span> <span data-ttu-id="3761f-165">A URL da página ou site onde você deseja que os usuários acessem para obter mais informações sobre o acrônimo.</span><span class="sxs-lookup"><span data-stu-id="3761f-165">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="3761f-166">**Estado**.</span><span class="sxs-lookup"><span data-stu-id="3761f-166">**State**.</span></span> <span data-ttu-id="3761f-167">Este campo pode ter dois valores:</span><span class="sxs-lookup"><span data-stu-id="3761f-167">This field can take two values:</span></span>

- <span data-ttu-id="3761f-168">**Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="3761f-168">**Draft**.</span></span> <span data-ttu-id="3761f-169">Adiciona o acrônimo ao estado Rascunho.</span><span class="sxs-lookup"><span data-stu-id="3761f-169">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="3761f-170">**Publicado**.</span><span class="sxs-lookup"><span data-stu-id="3761f-170">**Published**.</span></span> <span data-ttu-id="3761f-171">Adiciona o acrônimo ao estado Publicado e o disponibiliza na Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3761f-171">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="system-curated-acronyms"></a><span data-ttu-id="3761f-172">Acrônimos com cura do sistema</span><span class="sxs-lookup"><span data-stu-id="3761f-172">System-curated acronyms</span></span>

<span data-ttu-id="3761f-173">Pode ser um desafio para os administradores adicionarem todos os acrônimos usados em uma organização ao Answers.</span><span class="sxs-lookup"><span data-stu-id="3761f-173">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="3761f-174">Esse recurso pode encontrar acrônimos que os administradores de pesquisa nem sabem.</span><span class="sxs-lookup"><span data-stu-id="3761f-174">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="3761f-175">Para fazer esse trabalho, a Pesquisa da Microsoft também descobre e cura acrônimos dessas fontes:</span><span class="sxs-lookup"><span data-stu-id="3761f-175">To do that work, Microsoft Search also discovers and curates acronyms from these sources:</span></span>

- <span data-ttu-id="3761f-176">Emails dos usuários</span><span class="sxs-lookup"><span data-stu-id="3761f-176">Users’ emails</span></span>
- <span data-ttu-id="3761f-177">Documentos no [SharePoint,](https://products.office.com/sharepoint/collaboration) [Microsoft OneDrive]( https://onedrive.live.com/about/)e [Microsoft OneNote](https://www.onenote.com/)</span><span class="sxs-lookup"><span data-stu-id="3761f-177">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/)</span></span>
- <span data-ttu-id="3761f-178">Documentos públicos dentro da organização aos qual os usuários têm acesso no SharePoint, OneDrive ou OneNote</span><span class="sxs-lookup"><span data-stu-id="3761f-178">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote</span></span>

<span data-ttu-id="3761f-179">A Pesquisa da Microsoft garante que somente usuários com acesso e permissões para um documento possam ver os acrônimos descobertos nele.</span><span class="sxs-lookup"><span data-stu-id="3761f-179">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are discovered from it.</span></span> <span data-ttu-id="3761f-180">Quando um acrônimo é encontrado na caixa de correio de um usuário, somente esse usuário pode ver esse acrônimo.</span><span class="sxs-lookup"><span data-stu-id="3761f-180">When an acronym is found in a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="3761f-181">Nenhuma configuração é necessária para acrônimos com cura do administrador.</span><span class="sxs-lookup"><span data-stu-id="3761f-181">No setup is needed for admin-curated acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="3761f-182">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="3761f-182">Frequently asked questions</span></span>

<span data-ttu-id="3761f-183">**P: Como os dados com cura do administrador e do sistema são classificados?**</span><span class="sxs-lookup"><span data-stu-id="3761f-183">**Q: How is admin-curated and system-curated data ranked?**</span></span>

<span data-ttu-id="3761f-184">**R:** A classificação dos resultados pode variar de pessoa para pessoa, pois os resultados são personalizados para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="3761f-184">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span> <span data-ttu-id="3761f-185">Nenhuma dessas categorias sempre terá precedência sobre a outra.</span><span class="sxs-lookup"><span data-stu-id="3761f-185">Neither of these categories will always take precedence over the other.</span></span>

<span data-ttu-id="3761f-186">**P: Quanto tempo leva para que os acrônimos com cura de administrador sejam visíveis na Pesquisa da Microsoft depois que eles são publicados?**</span><span class="sxs-lookup"><span data-stu-id="3761f-186">**Q: How long does it take for admin-curated acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="3761f-187">**R:**  Leva até três dias para que os acrônimos adicionados ao estado Publicado se tornem disponíveis na Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3761f-187">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="3761f-188">**P: Como os usuários acionam respostas de acrônimos?**</span><span class="sxs-lookup"><span data-stu-id="3761f-188">**Q: How do users trigger acronyms answers?**</span></span>

<span data-ttu-id="3761f-189">**R:** Para obter respostas de acrônimos, os usuários devem inserir padrões de consulta específicos em uma caixa de pesquisa [do Bing,](https://bing.com) [do SharePoint](https://products.office.com/sharepoint/collaboration)ou do [Office 365.](https://Office.com) </span><span class="sxs-lookup"><span data-stu-id="3761f-189">**A**: To get acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="3761f-190">**P: Quanto tempo leva para que os acrônimos com cura do sistema apareçam depois de receber ou enviar um novo email ou documento?**</span><span class="sxs-lookup"><span data-stu-id="3761f-190">**Q: How long does it take for system-curated acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="3761f-191">**R:** Os acrônimos encontrados em um novo email ou documento levam até sete dias para aparecerem nos resultados da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3761f-191">**A:** Acronyms found in a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="3761f-192">**P: Os documentos precisam estar em um formato específico para que a mineração os pegue?**</span><span class="sxs-lookup"><span data-stu-id="3761f-192">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="3761f-193">**R:** Não.</span><span class="sxs-lookup"><span data-stu-id="3761f-193">**A:** No.</span></span> <span data-ttu-id="3761f-194">Suportamos todos os tipos de arquivo, exceto arquivos de imagem, pastas e zip.</span><span class="sxs-lookup"><span data-stu-id="3761f-194">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="3761f-195">**P: A Microsoft descobrirá acrônimos de documentos em todos os idiomas?**</span><span class="sxs-lookup"><span data-stu-id="3761f-195">**Q: Will Microsoft discover acronyms from documents in all languages?**</span></span>

<span data-ttu-id="3761f-196">**R:** A Microsoft só dá suporte à mineração de documentos em inglês.</span><span class="sxs-lookup"><span data-stu-id="3761f-196">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="3761f-197">O suporte para outros idiomas será adicionado em fases.</span><span class="sxs-lookup"><span data-stu-id="3761f-197">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="3761f-198">**P: E se minha organização não quiser mostrar acrônimos com cura do sistema? Posso parar de mostrar esse tipo de acrônimo nos meus resultados de pesquisa?**</span><span class="sxs-lookup"><span data-stu-id="3761f-198">**Q: What if my organization doesn’t want to show system-curated acronyms? Can I stop showing this type of acronym in my search results?**</span></span>

<span data-ttu-id="3761f-199">**R:** Para desativar a exibição de acrônimos com cura do sistema nos resultados da pesquisa, crie um tíquete de suporte ao cliente seguindo as instruções em [Contact support for business products](/microsoft-365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="3761f-199">**A**: To turn off showing system-curated acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](/microsoft-365/admin/contact-support-for-business-products).</span></span>
<span data-ttu-id="3761f-200">Depois de criar um tíquete de suporte, leva até 48 horas para que os acrônimos com cura do sistema parem de aparecer nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3761f-200">After you create a support ticket, it takes up to 48 hours for system-curated acronyms to stop appearing in search results.</span></span>