---
title: Gerenciar as respostas de acrônimo no Microsoft Search
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Criar e atualizar respostas de acrônimos no Microsoft Search
ms.openlocfilehash: e328ecb7604a144b51f3a1483eef1b1c3a7e0bcb
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422942"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="5f73f-103">Gerenciar as respostas de acrônimos no Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="5f73f-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="5f73f-104">Geralmente, os usuários podem ter acrônimos e abreviaturas desconhecidos usados por sua organização ou equipe.</span><span class="sxs-lookup"><span data-stu-id="5f73f-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="5f73f-105">Os termos específicos para organizações ou equipes podem ser novos para pessoas que se movem de uma equipe para outra, trabalham com equipes de parceiros internas ou que são novos na organização.</span><span class="sxs-lookup"><span data-stu-id="5f73f-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="5f73f-106">As organizações nem sempre têm uma única referência para sua terminologia padrão.</span><span class="sxs-lookup"><span data-stu-id="5f73f-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="5f73f-107">A falta de uma única referência dificulta a localização de definições ou expansões desses acrônimos.</span><span class="sxs-lookup"><span data-stu-id="5f73f-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="5f73f-108">O Microsoft Search resolve esse problema com acrônimos.</span><span class="sxs-lookup"><span data-stu-id="5f73f-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="5f73f-109">O que os usuários experimentam</span><span class="sxs-lookup"><span data-stu-id="5f73f-109">What users experience</span></span>

<span data-ttu-id="5f73f-110">Os usuários de pesquisa da Microsoft podem obter definições com acrônimos no [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)e [Office 365](https://Office.com).</span><span class="sxs-lookup"><span data-stu-id="5f73f-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), and [Office 365](https://Office.com).</span></span> <span data-ttu-id="5f73f-111">Na caixa de **pesquisa** , os usuários inserem consultas como estes exemplos:</span><span class="sxs-lookup"><span data-stu-id="5f73f-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="5f73f-112">*O que é* DNN</span><span class="sxs-lookup"><span data-stu-id="5f73f-112">*What is* DNN</span></span>
- <span data-ttu-id="5f73f-113">*Definir* DNN</span><span class="sxs-lookup"><span data-stu-id="5f73f-113">*Define* DNN</span></span>
- <span data-ttu-id="5f73f-114">*Definição* DNN</span><span class="sxs-lookup"><span data-stu-id="5f73f-114">DNN *definition*</span></span>
- <span data-ttu-id="5f73f-115">*Expand* DNN</span><span class="sxs-lookup"><span data-stu-id="5f73f-115">*Expand* DNN</span></span>
- <span data-ttu-id="5f73f-116">*Expansão* DNN</span><span class="sxs-lookup"><span data-stu-id="5f73f-116">DNN *expansion*</span></span>
- <span data-ttu-id="5f73f-117">*Significado de* DNN</span><span class="sxs-lookup"><span data-stu-id="5f73f-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="5f73f-118">DNN *significa*</span><span class="sxs-lookup"><span data-stu-id="5f73f-118">DNN *means*</span></span>

<span data-ttu-id="5f73f-119">O resultado inclui todos os significados do DNN que estão presentes na organização do usuário.</span><span class="sxs-lookup"><span data-stu-id="5f73f-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="5f73f-120">Os usuários devem inserir uma consulta que inclua as *palavras-chave* especificadas pelo acrônimo para disparar suas respostas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="5f73f-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="5f73f-121">As consultas de acrônimos não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="5f73f-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="5f73f-122">Configurar respostas de acrônimos</span><span class="sxs-lookup"><span data-stu-id="5f73f-122">Set up Acronyms answers</span></span>

<span data-ttu-id="5f73f-123">No [centro de administração do Microsoft 365](https://admin.microsoft.com), vá até [**acrônimos**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)e, em seguida, selecione **Adicionar sigla**.</span><span class="sxs-lookup"><span data-stu-id="5f73f-123">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronym**.</span></span>

<span data-ttu-id="5f73f-124">O Microsoft Search consulta duas fontes de dados para fornecer respostas de acrônimos às pesquisas dos usuários:</span><span class="sxs-lookup"><span data-stu-id="5f73f-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="5f73f-125">**Acrônimos editoriais**.</span><span class="sxs-lookup"><span data-stu-id="5f73f-125">**Editorial acronyms**.</span></span> <span data-ttu-id="5f73f-126">Fornecido por administradores de ti no [centro de administração](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span><span class="sxs-lookup"><span data-stu-id="5f73f-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="5f73f-127">**Acrônimos minados**.</span><span class="sxs-lookup"><span data-stu-id="5f73f-127">**Mined acronyms**.</span></span> <span data-ttu-id="5f73f-128">O Microsoft Search dos emails e dos documentos pessoais do usuário e dos dados publicamente disponíveis dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="5f73f-128">Mined by Microsoft Search from the user’s personal email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-editorial-acronyms"></a><span data-ttu-id="5f73f-129">Configurar acrônimos editoriais</span><span class="sxs-lookup"><span data-stu-id="5f73f-129">Set up editorial acronyms</span></span>

<span data-ttu-id="5f73f-130">Os administradores de pesquisa podem configurar acrônimos editoriais na [guia acrônimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) no  [centro de administração de pesquisa da Microsoft](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span><span class="sxs-lookup"><span data-stu-id="5f73f-130">Search administrators can set up editorial acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="5f73f-131">Você pode adicionar acrônimos de qualquer site ou repositório interno ao centro de administração.</span><span class="sxs-lookup"><span data-stu-id="5f73f-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="5f73f-132">Acrônimos editoriais podem ser adicionados ao estado **publicado** ou de **rascunho** :</span><span class="sxs-lookup"><span data-stu-id="5f73f-132">Editorial acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="5f73f-133">**Estado publicado**.</span><span class="sxs-lookup"><span data-stu-id="5f73f-133">**Published state**.</span></span> <span data-ttu-id="5f73f-134">Os acrônimos estão disponíveis para os funcionários da organização através da pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5f73f-134">Acronyms are available to the organization’s employees through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="5f73f-135">Pode levar até três dias para que os acrônimos adicionados ao estado publicado fiquem disponíveis no Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="5f73f-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="5f73f-136">**Estado de rascunho**.</span><span class="sxs-lookup"><span data-stu-id="5f73f-136">**Draft state**.</span></span> <span data-ttu-id="5f73f-137">Se os administradores desejarem revisar as respostas de acrônimos antes de disponibilizá-las no Microsoft Search, poderão adicionar os acrônimos ao estado de rascunho.</span><span class="sxs-lookup"><span data-stu-id="5f73f-137">If admins want to review Acronyms answers before making them available in Microsoft Search, they can add the acronyms to Draft state.</span></span> <span data-ttu-id="5f73f-138">Os acrônimos adicionados ao estado de rascunho não estão disponíveis no Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="5f73f-138">Acronyms added to Draft state aren’t available in Microsoft Search.</span></span> <span data-ttu-id="5f73f-139">Os administradores precisam adicionar os acrônimos ao estado publicado para torná-los disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5f73f-139">Admins need to add the acronyms to Published state to make them available.</span></span>

<span data-ttu-id="5f73f-140">Os administradores podem adicionar acrônimos individualmente ou importá-los em massa em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="5f73f-140">Admins can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="5f73f-141">Carregue um arquivo CSV com os campos mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="5f73f-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="5f73f-142">Sigla (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5f73f-142">Acronym (mandatory)</span></span> | <span data-ttu-id="5f73f-143">Expansão (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="5f73f-143">Expansion (mandatory)</span></span> | <span data-ttu-id="5f73f-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="5f73f-144">Description</span></span>  | <span data-ttu-id="5f73f-145">Origem</span><span class="sxs-lookup"><span data-stu-id="5f73f-145">Source</span></span> | <span data-ttu-id="5f73f-146">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="5f73f-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="5f73f-147">*XXX*</span><span class="sxs-lookup"><span data-stu-id="5f73f-147">*XXX*</span></span> | <span data-ttu-id="5f73f-148">*Abreviatura de abreviação*</span><span class="sxs-lookup"><span data-stu-id="5f73f-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="5f73f-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="5f73f-149">*URL*</span></span> | <span data-ttu-id="5f73f-150">*Publicado ou rascunho*</span><span class="sxs-lookup"><span data-stu-id="5f73f-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="5f73f-151">Campos CSV</span><span class="sxs-lookup"><span data-stu-id="5f73f-151">CSV fields</span></span>

<span data-ttu-id="5f73f-152">**Sigla**.</span><span class="sxs-lookup"><span data-stu-id="5f73f-152">**Acronym**.</span></span> <span data-ttu-id="5f73f-153">Contém a forma curta ou sigla real.</span><span class="sxs-lookup"><span data-stu-id="5f73f-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="5f73f-154">Um exemplo é *DNN*.</span><span class="sxs-lookup"><span data-stu-id="5f73f-154">An example is *DNN*.</span></span>

<span data-ttu-id="5f73f-155">**Expansão**.</span><span class="sxs-lookup"><span data-stu-id="5f73f-155">**Expansion**.</span></span> <span data-ttu-id="5f73f-156">Contém a expansão do acrônimo.</span><span class="sxs-lookup"><span data-stu-id="5f73f-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="5f73f-157">Um exemplo é uma *rede neural profunda*.</span><span class="sxs-lookup"><span data-stu-id="5f73f-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="5f73f-158">**Descrição**.</span><span class="sxs-lookup"><span data-stu-id="5f73f-158">**Description**.</span></span> <span data-ttu-id="5f73f-159">Uma breve descrição do acrônimo que oferece aos usuários mais informações sobre o acrônimo e sua expansão.</span><span class="sxs-lookup"><span data-stu-id="5f73f-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="5f73f-160">Por exemplo, *uma rede neural profunda é uma rede neural com um determinado nível de complexidade, uma rede neural com mais de duas camadas*.</span><span class="sxs-lookup"><span data-stu-id="5f73f-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="5f73f-161">**Fonte**.</span><span class="sxs-lookup"><span data-stu-id="5f73f-161">**Source**.</span></span> <span data-ttu-id="5f73f-162">A URL da página ou site onde você deseja que os usuários vá para obter mais informações sobre o acrônimo.</span><span class="sxs-lookup"><span data-stu-id="5f73f-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="5f73f-163">**Estado**.</span><span class="sxs-lookup"><span data-stu-id="5f73f-163">**State**.</span></span> <span data-ttu-id="5f73f-164">Este campo pode ter dois valores:</span><span class="sxs-lookup"><span data-stu-id="5f73f-164">This field can take two values:</span></span>

- <span data-ttu-id="5f73f-165">**Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="5f73f-165">**Draft**.</span></span> <span data-ttu-id="5f73f-166">Adiciona o acrônimo ao estado de rascunho.</span><span class="sxs-lookup"><span data-stu-id="5f73f-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="5f73f-167">**Publicado**.</span><span class="sxs-lookup"><span data-stu-id="5f73f-167">**Published**.</span></span> <span data-ttu-id="5f73f-168">Adiciona a sigla ao estado publicado e a disponibiliza no Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="5f73f-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="mined-acronyms"></a><span data-ttu-id="5f73f-169">Acrônimos minados</span><span class="sxs-lookup"><span data-stu-id="5f73f-169">Mined acronyms</span></span>

<span data-ttu-id="5f73f-170">Pode ser um desafio para os administradores adicionarem todos os acrônimos usados dentro de uma organização para responder.</span><span class="sxs-lookup"><span data-stu-id="5f73f-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="5f73f-171">Esse recurso pode encontrar acrônimos que os administradores de pesquisa nem são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="5f73f-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="5f73f-172">Para fazer isso, a pesquisa da Microsoft também extrai acrônimos dessas fontes:</span><span class="sxs-lookup"><span data-stu-id="5f73f-172">To do that work, Microsoft Search also mines acronyms from these sources:</span></span>

- <span data-ttu-id="5f73f-173">Emails dos usuários.</span><span class="sxs-lookup"><span data-stu-id="5f73f-173">Users’ emails.</span></span>
- <span data-ttu-id="5f73f-174">Documentos no [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft onedrive]( https://onedrive.live.com/about/)e [Microsoft OneNote](https://www.onenote.com/).</span><span class="sxs-lookup"><span data-stu-id="5f73f-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/).</span></span>
- <span data-ttu-id="5f73f-175">Documentos públicos dentro da organização aos quais os usuários têm acesso no SharePoint, no OneDrive ou no OneNote.</span><span class="sxs-lookup"><span data-stu-id="5f73f-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote.</span></span>

<span data-ttu-id="5f73f-176">A pesquisa da Microsoft garante que apenas usuários com acesso e permissões a um documento possam ver os acrônimos que são minados.</span><span class="sxs-lookup"><span data-stu-id="5f73f-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are mined from it.</span></span> <span data-ttu-id="5f73f-177">Quando um acrônimo é minado da caixa de correio de um usuário, apenas esse usuário pode ver esse acrônimo.</span><span class="sxs-lookup"><span data-stu-id="5f73f-177">When an acronym is mined from a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="5f73f-178">Nenhuma configuração é necessária para acrônimos minados.</span><span class="sxs-lookup"><span data-stu-id="5f73f-178">No setup is needed for mined acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="5f73f-179">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="5f73f-179">Frequently asked questions</span></span>

<span data-ttu-id="5f73f-180">**P: como os dados de editorial e minados são classificados?**</span><span class="sxs-lookup"><span data-stu-id="5f73f-180">**Q: How is editorial and mined data ranked?**</span></span>

<span data-ttu-id="5f73f-181">**A:** O recurso atualmente classifica os acrônimos editoriais acima de acrônimos minados.</span><span class="sxs-lookup"><span data-stu-id="5f73f-181">**A:** The feature currently ranks editorial acronyms above mined acronyms.</span></span>

<span data-ttu-id="5f73f-182">**P: quanto tempo demora para que os acrônimos editoriais fiquem visíveis na pesquisa da Microsoft após serem publicados?**</span><span class="sxs-lookup"><span data-stu-id="5f73f-182">**Q: How long does it take for editorial acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="5f73f-183">**A:**  É necessário até três dias para que os acrônimos adicionados ao estado publicado sejam disponibilizados na pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5f73f-183">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="5f73f-184">**P: como os usuários acionam as respostas de acrônimos?**</span><span class="sxs-lookup"><span data-stu-id="5f73f-184">**Q: How do users trigger Acronyms answers?**</span></span>

<span data-ttu-id="5f73f-185">**A**: para obter respostas de acrônimos, os usuários devem inserir padrões de consulta específicos em uma caixa de **pesquisa** [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)ou [Office 365](https://Office.com) .</span><span class="sxs-lookup"><span data-stu-id="5f73f-185">**A**: To get Acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), or [Office 365](https://Office.com) **Search** box.</span></span>

<span data-ttu-id="5f73f-186">**P: quanto tempo leva para que acrônimos minados apareçam após você receber ou enviar um novo email ou documento?**</span><span class="sxs-lookup"><span data-stu-id="5f73f-186">**Q: How long does it take for mined acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="5f73f-187">**A:** Os acrônimos minados de um novo email ou documento levam até sete dias para serem exibidos nos resultados da pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5f73f-187">**A:** Mined acronyms from a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="5f73f-188">**P: os documentos precisam estar em um formato específico para que a mineração os pegue?**</span><span class="sxs-lookup"><span data-stu-id="5f73f-188">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="5f73f-189">**A:** Não.</span><span class="sxs-lookup"><span data-stu-id="5f73f-189">**A:** No.</span></span> <span data-ttu-id="5f73f-190">Oferecemos suporte a todos os tipos de arquivo, exceto imagem, pastas e arquivos zip.</span><span class="sxs-lookup"><span data-stu-id="5f73f-190">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="5f73f-191">**P: a Microsoft vai minar as acrônimos de documentos em todos os idiomas?**</span><span class="sxs-lookup"><span data-stu-id="5f73f-191">**Q: Will Microsoft mine acronyms from documents in all languages?**</span></span>

<span data-ttu-id="5f73f-192">**A: A**Microsoft dá suporte apenas à mineração de documentos em inglês.</span><span class="sxs-lookup"><span data-stu-id="5f73f-192">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="5f73f-193">O suporte para outros idiomas será adicionado em fases.</span><span class="sxs-lookup"><span data-stu-id="5f73f-193">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="5f73f-194">**P: e se minha organização não quiser mostrar acrônimos minados? Posso parar de mostrar acrônimos minados nos resultados da pesquisa?**</span><span class="sxs-lookup"><span data-stu-id="5f73f-194">**Q: What if my organization doesn’t want to show mined acronyms? Can I stop showing mined acronyms in search results?**</span></span>

<span data-ttu-id="5f73f-195">**A**: para desativar a exibição de acrônimos minados nos resultados da pesquisa, crie um tíquete de suporte ao cliente seguindo as instruções em [contato com o suporte para produtos de negócios](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span><span class="sxs-lookup"><span data-stu-id="5f73f-195">**A**: To turn off showing mined acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="5f73f-196">Depois de criar um tíquete de suporte, serão necessários até 48 horas para que os acrônimos minados parem de aparecer nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="5f73f-196">After you create a support ticket, it takes up to 48 hours for mined acronyms to stop appearing in search results.</span></span>
