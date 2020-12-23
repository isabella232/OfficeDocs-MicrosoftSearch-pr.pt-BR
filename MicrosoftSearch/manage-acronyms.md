---
title: Gerenciar as respostas de acrônimo no Microsoft Search
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
description: Criar e atualizar respostas de acrônimos no Microsoft Search
ms.openlocfilehash: ff79e3d741e10d401873c29d86739e61c9f53329
ms.sourcegitcommit: e6ceb07cae208648dadd5452a077414ab5a4513f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2020
ms.locfileid: "49728002"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="f2fa5-103">Gerenciar as respostas de acrônimos no Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="f2fa5-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="f2fa5-104">Geralmente, os usuários podem ter acrônimos e abreviaturas desconhecidos usados por sua organização ou equipe.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="f2fa5-105">Os termos específicos para organizações ou equipes podem ser novos para pessoas que se movem de uma equipe para outra, trabalham com equipes de parceiros internas ou que são novos na organização.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="f2fa5-106">As organizações nem sempre têm uma única referência para sua terminologia padrão.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="f2fa5-107">A falta de uma única referência dificulta a localização de definições ou expansões desses acrônimos.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="f2fa5-108">O Microsoft Search resolve esse problema com acrônimos.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="f2fa5-109">O que os usuários experimentam</span><span class="sxs-lookup"><span data-stu-id="f2fa5-109">What users experience</span></span>

<span data-ttu-id="f2fa5-110">Os usuários de pesquisa da Microsoft podem obter definições com acrônimos no [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)e [Office 365](https://Office.com).</span><span class="sxs-lookup"><span data-stu-id="f2fa5-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="f2fa5-111">Na caixa de **pesquisa** , os usuários inserem consultas como estes exemplos:</span><span class="sxs-lookup"><span data-stu-id="f2fa5-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="f2fa5-112">*O que é* DNN</span><span class="sxs-lookup"><span data-stu-id="f2fa5-112">*What is* DNN</span></span>
- <span data-ttu-id="f2fa5-113">*Definir* DNN</span><span class="sxs-lookup"><span data-stu-id="f2fa5-113">*Define* DNN</span></span>
- <span data-ttu-id="f2fa5-114">*Definição* DNN</span><span class="sxs-lookup"><span data-stu-id="f2fa5-114">DNN *definition*</span></span>
- <span data-ttu-id="f2fa5-115">*Expand* DNN</span><span class="sxs-lookup"><span data-stu-id="f2fa5-115">*Expand* DNN</span></span>
- <span data-ttu-id="f2fa5-116">*Expansão* DNN</span><span class="sxs-lookup"><span data-stu-id="f2fa5-116">DNN *expansion*</span></span>
- <span data-ttu-id="f2fa5-117">*Significado de* DNN</span><span class="sxs-lookup"><span data-stu-id="f2fa5-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="f2fa5-118">DNN *significa*</span><span class="sxs-lookup"><span data-stu-id="f2fa5-118">DNN *means*</span></span>

<span data-ttu-id="f2fa5-119">O resultado inclui todos os significados do DNN que estão presentes na organização do usuário.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="f2fa5-120">Os usuários devem inserir uma consulta que inclua as *palavras-chave* especificadas pelo acrônimo para disparar suas respostas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="f2fa5-121">As consultas de acrônimos não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="f2fa5-122">Configurar respostas de acrônimos</span><span class="sxs-lookup"><span data-stu-id="f2fa5-122">Set up acronyms answers</span></span>

<span data-ttu-id="f2fa5-123">No [centro de administração do Microsoft 365](https://admin.microsoft.com), vá até [**acrônimos**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)e, em seguida, selecione **Adicionar sigla**.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="f2fa5-124">O Microsoft Search consulta duas fontes de dados para fornecer respostas de acrônimos às pesquisas dos usuários:</span><span class="sxs-lookup"><span data-stu-id="f2fa5-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="f2fa5-125">**Administração-organizada**.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-125">**Admin-curated**.</span></span> <span data-ttu-id="f2fa5-126">Fornecido por administradores de ti no [centro de administração](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span><span class="sxs-lookup"><span data-stu-id="f2fa5-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="f2fa5-127">**De sistema-organizada**.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-127">**System-curated**.</span></span> <span data-ttu-id="f2fa5-128">Descoberto pela Microsoft Search de emails e documentos de usuários e dados publicamente disponíveis dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-128">Discovered by Microsoft Search from users' email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-admin-curated-acronyms"></a><span data-ttu-id="f2fa5-129">Configurar acrônimos auxiliares de administrador</span><span class="sxs-lookup"><span data-stu-id="f2fa5-129">Set up Admin-curated acronyms</span></span>

<span data-ttu-id="f2fa5-130">Os administradores de pesquisa podem adicionar acrônimos à [guia acrônimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) no  [centro de administração de pesquisa da Microsoft](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span><span class="sxs-lookup"><span data-stu-id="f2fa5-130">Search administrators can add acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="f2fa5-131">Você pode adicionar acrônimos de qualquer site ou repositório interno ao centro de administração.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="f2fa5-132">Esses acrônimos podem ser adicionados ao estado **publicado** ou de **rascunho** :</span><span class="sxs-lookup"><span data-stu-id="f2fa5-132">These acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="f2fa5-133">**Estado publicado**.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-133">**Published state**.</span></span> <span data-ttu-id="f2fa5-134">Os acrônimos estão disponíveis para os usuários da organização através da pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-134">Acronyms are available to the organization’s users through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="f2fa5-135">Pode levar até três dias para que os acrônimos adicionados ao estado publicado fiquem disponíveis no Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="f2fa5-136">**Estado de rascunho**.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-136">**Draft state**.</span></span> <span data-ttu-id="f2fa5-137">Se você deseja revisar um acrônimo antes de disponibilizá-lo no Microsoft Search, você pode adicionar o acrônimo em um estado de rascunho.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-137">If you want to review an acronym before making it available in Microsoft Search, you can add the acronym in a Draft state.</span></span> <span data-ttu-id="f2fa5-138">Os acrônimos no estado rascunho não serão exibidos nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-138">Acronyms in the Draft state will not appear in search results.</span></span> <span data-ttu-id="f2fa5-139">Você precisará mover o acrônimo para o estado publicado para que ele apareça nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-139">You will need to move the acronym to the Published state to make it appear in search results.</span></span>

<span data-ttu-id="f2fa5-140">Você pode adicionar acrônimos individualmente ou importá-los em massa em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-140">You can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="f2fa5-141">Carregue um arquivo CSV com os campos mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="f2fa5-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="f2fa5-142">Sigla (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f2fa5-142">Acronym (mandatory)</span></span> | <span data-ttu-id="f2fa5-143">Expansão (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="f2fa5-143">Expansion (mandatory)</span></span> | <span data-ttu-id="f2fa5-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="f2fa5-144">Description</span></span>  | <span data-ttu-id="f2fa5-145">Origem</span><span class="sxs-lookup"><span data-stu-id="f2fa5-145">Source</span></span> | <span data-ttu-id="f2fa5-146">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="f2fa5-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="f2fa5-147">*XXX*</span><span class="sxs-lookup"><span data-stu-id="f2fa5-147">*XXX*</span></span> | <span data-ttu-id="f2fa5-148">*Abreviatura de abreviação*</span><span class="sxs-lookup"><span data-stu-id="f2fa5-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="f2fa5-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="f2fa5-149">*URL*</span></span> | <span data-ttu-id="f2fa5-150">*Publicado ou rascunho*</span><span class="sxs-lookup"><span data-stu-id="f2fa5-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="f2fa5-151">Campos CSV</span><span class="sxs-lookup"><span data-stu-id="f2fa5-151">CSV fields</span></span>

<span data-ttu-id="f2fa5-152">**Sigla**.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-152">**Acronym**.</span></span> <span data-ttu-id="f2fa5-153">Contém a forma curta ou sigla real.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="f2fa5-154">Um exemplo é *DNN*.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-154">An example is *DNN*.</span></span>

<span data-ttu-id="f2fa5-155">**Expansão**.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-155">**Expansion**.</span></span> <span data-ttu-id="f2fa5-156">Contém a expansão do acrônimo.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="f2fa5-157">Um exemplo é uma *rede neural profunda*.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="f2fa5-158">**Descrição**.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-158">**Description**.</span></span> <span data-ttu-id="f2fa5-159">Uma breve descrição do acrônimo que oferece aos usuários mais informações sobre o acrônimo e sua expansão.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="f2fa5-160">Por exemplo, *uma rede neural profunda é uma rede neural com um determinado nível de complexidade, uma rede neural com mais de duas camadas*.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="f2fa5-161">**Fonte**.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-161">**Source**.</span></span> <span data-ttu-id="f2fa5-162">A URL da página ou site onde você deseja que os usuários vá para obter mais informações sobre o acrônimo.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="f2fa5-163">**Estado**.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-163">**State**.</span></span> <span data-ttu-id="f2fa5-164">Este campo pode ter dois valores:</span><span class="sxs-lookup"><span data-stu-id="f2fa5-164">This field can take two values:</span></span>

- <span data-ttu-id="f2fa5-165">**Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-165">**Draft**.</span></span> <span data-ttu-id="f2fa5-166">Adiciona o acrônimo ao estado de rascunho.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="f2fa5-167">**Publicado**.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-167">**Published**.</span></span> <span data-ttu-id="f2fa5-168">Adiciona a sigla ao estado publicado e a disponibiliza no Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="system-curated-acronyms"></a><span data-ttu-id="f2fa5-169">Acrônimos organizados pelo sistema</span><span class="sxs-lookup"><span data-stu-id="f2fa5-169">System-curated acronyms</span></span>

<span data-ttu-id="f2fa5-170">Pode ser um desafio para os administradores adicionarem todos os acrônimos usados dentro de uma organização para responder.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="f2fa5-171">Esse recurso pode encontrar acrônimos que os administradores de pesquisa nem são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="f2fa5-172">Para fazer isso funcionar, a pesquisa da Microsoft também descobre e busca acrônimos dessas fontes:</span><span class="sxs-lookup"><span data-stu-id="f2fa5-172">To do that work, Microsoft Search also discovers and curates acronyms from these sources:</span></span>

- <span data-ttu-id="f2fa5-173">Emails dos usuários</span><span class="sxs-lookup"><span data-stu-id="f2fa5-173">Users’ emails</span></span>
- <span data-ttu-id="f2fa5-174">Documentos no [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft onedrive]( https://onedrive.live.com/about/)e [Microsoft OneNote](https://www.onenote.com/)</span><span class="sxs-lookup"><span data-stu-id="f2fa5-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/)</span></span>
- <span data-ttu-id="f2fa5-175">Documentos públicos dentro da organização para os quais os usuários têm acesso no SharePoint, OneDrive ou OneNote</span><span class="sxs-lookup"><span data-stu-id="f2fa5-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote</span></span>

<span data-ttu-id="f2fa5-176">A pesquisa da Microsoft garante que somente os usuários com acesso e permissões a um documento possam ver os acrônimos descobertos.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are discovered from it.</span></span> <span data-ttu-id="f2fa5-177">Quando um acrônimo é encontrado na caixa de correio de um usuário, apenas esse usuário pode ver esse acrônimo.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-177">When an acronym is found in a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="f2fa5-178">Nenhuma configuração é necessária para acrônimos auxiliares de administrador.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-178">No setup is needed for admin-curated acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="f2fa5-179">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="f2fa5-179">Frequently asked questions</span></span>

<span data-ttu-id="f2fa5-180">**P: como os dados de administrador e de sistema são classificados de acordo?**</span><span class="sxs-lookup"><span data-stu-id="f2fa5-180">**Q: How is admin-curated and system-curated data ranked?**</span></span>

<span data-ttu-id="f2fa5-181">**A:** A classificação dos resultados pode variar de pessoa para pessoa à medida que os resultados são personalizados para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-181">**A:** The ranking of results may vary from person to person as results are personalized for each user.</span></span> <span data-ttu-id="f2fa5-182">Nenhuma dessas categorias sempre terá precedência sobre a outra.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-182">Neither of these categories will always take precedence over the other.</span></span>

<span data-ttu-id="f2fa5-183">**P: quanto tempo demora para que os acrônimos auxiliares sejam visíveis na pesquisa da Microsoft após serem publicados?**</span><span class="sxs-lookup"><span data-stu-id="f2fa5-183">**Q: How long does it take for admin-curated acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="f2fa5-184">**A:**  É necessário até três dias para que os acrônimos adicionados ao estado publicado sejam disponibilizados na pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-184">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="f2fa5-185">**P: como os usuários acionam as respostas de acrônimos?**</span><span class="sxs-lookup"><span data-stu-id="f2fa5-185">**Q: How do users trigger acronyms answers?**</span></span>

<span data-ttu-id="f2fa5-186">**A**: para obter respostas de acrônimos, os usuários devem inserir padrões de consulta específicos em uma caixa de **pesquisa** [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)ou [Office 365](https://Office.com) .</span><span class="sxs-lookup"><span data-stu-id="f2fa5-186">**A**: To get acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="f2fa5-187">**P: quanto tempo leva para que os acrônimos de sistema sejam exibidos depois que você recebe ou envia um novo email ou documento?**</span><span class="sxs-lookup"><span data-stu-id="f2fa5-187">**Q: How long does it take for system-curated acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="f2fa5-188">**A:** Os acrônimos encontrados em um novo email ou documento levam até sete dias para serem exibidos nos resultados da pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-188">**A:** Acronyms found in a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="f2fa5-189">**P: os documentos precisam estar em um formato específico para que a mineração os pegue?**</span><span class="sxs-lookup"><span data-stu-id="f2fa5-189">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="f2fa5-190">**A:** Não.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-190">**A:** No.</span></span> <span data-ttu-id="f2fa5-191">Oferecemos suporte a todos os tipos de arquivo, exceto imagem, pastas e arquivos zip.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-191">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="f2fa5-192">**P: a Microsoft descobrirá as abreviações de documentos em todos os idiomas?**</span><span class="sxs-lookup"><span data-stu-id="f2fa5-192">**Q: Will Microsoft discover acronyms from documents in all languages?**</span></span>

<span data-ttu-id="f2fa5-193">**A: A** Microsoft dá suporte apenas à mineração de documentos em inglês.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-193">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="f2fa5-194">O suporte para outros idiomas será adicionado em fases.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-194">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="f2fa5-195">**P: e se minha organização não quiser mostrar os acrônimos de sistema. Posso parar de mostrar esse tipo de sigla nos meus resultados de pesquisa?**</span><span class="sxs-lookup"><span data-stu-id="f2fa5-195">**Q: What if my organization doesn’t want to show system-curated acronyms? Can I stop showing this type of acronym in my search results?**</span></span>

<span data-ttu-id="f2fa5-196">**A**: para desativar a exibição de acrônimos de sistema não organizados em resultados de pesquisa, crie um tíquete de suporte ao cliente seguindo as instruções em [contato com o suporte para produtos de negócios](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span><span class="sxs-lookup"><span data-stu-id="f2fa5-196">**A**: To turn off showing system-curated acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="f2fa5-197">Depois de criar um tíquete de suporte, serão necessários até 48 horas para que os acrônimos de sistema separados parem de aparecer nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f2fa5-197">After you create a support ticket, it takes up to 48 hours for system-curated acronyms to stop appearing in search results.</span></span>
