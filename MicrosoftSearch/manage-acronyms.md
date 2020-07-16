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
ms.openlocfilehash: bbdd27b00be323db8d80994fe9ff6ab7fac17416
ms.sourcegitcommit: b5142052ed17cd430b4c193b67d8f3d90d94ba6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2020
ms.locfileid: "45143861"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="15bcb-103">Gerenciar as respostas de acrônimos no Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="15bcb-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="15bcb-104">Geralmente, os usuários podem ter acrônimos e abreviaturas desconhecidos usados por sua organização ou equipe.</span><span class="sxs-lookup"><span data-stu-id="15bcb-104">Users often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="15bcb-105">Os termos específicos para organizações ou equipes podem ser novos para pessoas que se movem de uma equipe para outra, trabalham com equipes de parceiros internas ou que são novos na organização.</span><span class="sxs-lookup"><span data-stu-id="15bcb-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, work with internal partner teams, or are new to the organization.</span></span>

<span data-ttu-id="15bcb-106">As organizações nem sempre têm uma única referência para sua terminologia padrão.</span><span class="sxs-lookup"><span data-stu-id="15bcb-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="15bcb-107">A falta de uma única referência dificulta a localização de definições ou expansões desses acrônimos.</span><span class="sxs-lookup"><span data-stu-id="15bcb-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="15bcb-108">O Microsoft Search resolve esse problema com acrônimos.</span><span class="sxs-lookup"><span data-stu-id="15bcb-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="15bcb-109">O que os usuários experimentam</span><span class="sxs-lookup"><span data-stu-id="15bcb-109">What users experience</span></span>

<span data-ttu-id="15bcb-110">Os usuários de pesquisa da Microsoft podem obter definições com acrônimos no [Bing](https://Bing.com) e no [SharePoint](https://products.office.com/sharepoint/collaboration).</span><span class="sxs-lookup"><span data-stu-id="15bcb-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com) and [SharePoint](https://products.office.com/sharepoint/collaboration).</span></span> <span data-ttu-id="15bcb-111">Na caixa de **pesquisa** , os usuários inserem consultas como estes exemplos:</span><span class="sxs-lookup"><span data-stu-id="15bcb-111">In the **Search** box, users enter queries like these examples:</span></span>

- <span data-ttu-id="15bcb-112">*O que é* DNN</span><span class="sxs-lookup"><span data-stu-id="15bcb-112">*What is* DNN</span></span>
- <span data-ttu-id="15bcb-113">*Definir* DNN</span><span class="sxs-lookup"><span data-stu-id="15bcb-113">*Define* DNN</span></span>
- <span data-ttu-id="15bcb-114">*Definição* DNN</span><span class="sxs-lookup"><span data-stu-id="15bcb-114">DNN *definition*</span></span>
- <span data-ttu-id="15bcb-115">*Expand* DNN</span><span class="sxs-lookup"><span data-stu-id="15bcb-115">*Expand* DNN</span></span>
- <span data-ttu-id="15bcb-116">*Expansão* DNN</span><span class="sxs-lookup"><span data-stu-id="15bcb-116">DNN *expansion*</span></span>
- <span data-ttu-id="15bcb-117">*Significado de* DNN</span><span class="sxs-lookup"><span data-stu-id="15bcb-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="15bcb-118">DNN *significa*</span><span class="sxs-lookup"><span data-stu-id="15bcb-118">DNN *means*</span></span>

<span data-ttu-id="15bcb-119">O resultado inclui todos os significados do DNN que estão presentes na organização do usuário.</span><span class="sxs-lookup"><span data-stu-id="15bcb-119">The result includes all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="15bcb-120">Os usuários devem inserir uma consulta que inclua as *palavras-chave* especificadas pelo acrônimo para disparar suas respostas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="15bcb-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span> <span data-ttu-id="15bcb-121">As consultas de acrônimos não diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="15bcb-121">Acronym queries are not case sensitive.</span></span>

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="15bcb-122">Configurar respostas de acrônimos</span><span class="sxs-lookup"><span data-stu-id="15bcb-122">Set up Acronyms answers</span></span>

<span data-ttu-id="15bcb-123">No [centro de administração](https://admin.microsoft.com)do Microsoft 365, acesse **definições**de  >  respostas da**pesquisa da Microsoft**  >  **Answers**  >  [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)e selecione **Adicionar acrônimos**.</span><span class="sxs-lookup"><span data-stu-id="15bcb-123">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Settings** > **Microsoft Search** > **Answers** > [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms), and then select **Add acronyms**.</span></span>

<span data-ttu-id="15bcb-124">O Microsoft Search consulta duas fontes de dados para fornecer respostas de acrônimos às pesquisas dos usuários:</span><span class="sxs-lookup"><span data-stu-id="15bcb-124">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1. <span data-ttu-id="15bcb-125">**Acrônimos editoriais**.</span><span class="sxs-lookup"><span data-stu-id="15bcb-125">**Editorial acronyms**.</span></span> <span data-ttu-id="15bcb-126">Fornecido por administradores de ti no [centro de administração](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span><span class="sxs-lookup"><span data-stu-id="15bcb-126">Provided by IT administrators in the [admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).</span></span>
2. <span data-ttu-id="15bcb-127">**Acrônimos minados**.</span><span class="sxs-lookup"><span data-stu-id="15bcb-127">**Mined acronyms**.</span></span> <span data-ttu-id="15bcb-128">O Microsoft Search dos emails e dos documentos pessoais do usuário e dos dados publicamente disponíveis dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="15bcb-128">Mined by Microsoft Search from the user’s personal email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-editorial-acronyms"></a><span data-ttu-id="15bcb-129">Configurar acrônimos editoriais</span><span class="sxs-lookup"><span data-stu-id="15bcb-129">Set up editorial acronyms</span></span>

<span data-ttu-id="15bcb-130">Os administradores de pesquisa podem configurar acrônimos editoriais na [guia acrônimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) no [centro de administração de pesquisa da Microsoft](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span><span class="sxs-lookup"><span data-stu-id="15bcb-130">Search administrators can set up editorial acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) in the  [Microsoft Search admin center](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch).</span></span> <span data-ttu-id="15bcb-131">Você pode adicionar acrônimos de qualquer site ou repositório interno ao centro de administração.</span><span class="sxs-lookup"><span data-stu-id="15bcb-131">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="15bcb-132">Acrônimos editoriais podem ser adicionados ao estado **publicado** ou de **rascunho** :</span><span class="sxs-lookup"><span data-stu-id="15bcb-132">Editorial acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="15bcb-133">**Estado publicado**.</span><span class="sxs-lookup"><span data-stu-id="15bcb-133">**Published state**.</span></span> <span data-ttu-id="15bcb-134">Os acrônimos estão disponíveis para os funcionários da organização através da pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="15bcb-134">Acronyms are available to the organization’s employees through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="15bcb-135">Pode levar até três dias para que os acrônimos adicionados ao estado publicado fiquem disponíveis no Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="15bcb-135">It might take up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="15bcb-136">**Estado de rascunho**.</span><span class="sxs-lookup"><span data-stu-id="15bcb-136">**Draft state**.</span></span> <span data-ttu-id="15bcb-137">Se os administradores desejarem revisar as respostas de acrônimos antes de disponibilizá-las no Microsoft Search, poderão adicionar os acrônimos ao estado de rascunho.</span><span class="sxs-lookup"><span data-stu-id="15bcb-137">If admins want to review Acronyms answers before making them available in Microsoft Search, they can add the acronyms to Draft state.</span></span> <span data-ttu-id="15bcb-138">Os acrônimos adicionados ao estado de rascunho não estão disponíveis no Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="15bcb-138">Acronyms added to Draft state aren’t available in Microsoft Search.</span></span> <span data-ttu-id="15bcb-139">Os administradores precisam adicionar os acrônimos ao estado publicado para torná-los disponíveis.</span><span class="sxs-lookup"><span data-stu-id="15bcb-139">Admins need to add the acronyms to Published state to make them available.</span></span>

<span data-ttu-id="15bcb-140">Os administradores podem adicionar acrônimos individualmente ou importá-los em massa em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="15bcb-140">Admins can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="15bcb-141">Carregue um arquivo CSV com os campos mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="15bcb-141">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="15bcb-142">Sigla (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="15bcb-142">Acronym (mandatory)</span></span> | <span data-ttu-id="15bcb-143">Expansão (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="15bcb-143">Expansion (mandatory)</span></span> | <span data-ttu-id="15bcb-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="15bcb-144">Description</span></span>  | <span data-ttu-id="15bcb-145">Origem</span><span class="sxs-lookup"><span data-stu-id="15bcb-145">Source</span></span> | <span data-ttu-id="15bcb-146">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="15bcb-146">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="15bcb-147">*XXX*</span><span class="sxs-lookup"><span data-stu-id="15bcb-147">*XXX*</span></span> | <span data-ttu-id="15bcb-148">*Abreviatura de abreviação*</span><span class="sxs-lookup"><span data-stu-id="15bcb-148">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="15bcb-149">*URL*</span><span class="sxs-lookup"><span data-stu-id="15bcb-149">*URL*</span></span> | <span data-ttu-id="15bcb-150">*Publicado ou rascunho*</span><span class="sxs-lookup"><span data-stu-id="15bcb-150">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="15bcb-151">Campos CSV</span><span class="sxs-lookup"><span data-stu-id="15bcb-151">CSV fields</span></span>

<span data-ttu-id="15bcb-152">**Sigla**.</span><span class="sxs-lookup"><span data-stu-id="15bcb-152">**Acronym**.</span></span> <span data-ttu-id="15bcb-153">Contém a forma curta ou sigla real.</span><span class="sxs-lookup"><span data-stu-id="15bcb-153">Contains the actual short form or acronym.</span></span> <span data-ttu-id="15bcb-154">Um exemplo é *DNN*.</span><span class="sxs-lookup"><span data-stu-id="15bcb-154">An example is *DNN*.</span></span>

<span data-ttu-id="15bcb-155">**Expansão**.</span><span class="sxs-lookup"><span data-stu-id="15bcb-155">**Expansion**.</span></span> <span data-ttu-id="15bcb-156">Contém a expansão do acrônimo.</span><span class="sxs-lookup"><span data-stu-id="15bcb-156">Contains the expansion of the acronym.</span></span> <span data-ttu-id="15bcb-157">Um exemplo é uma *rede neural profunda*.</span><span class="sxs-lookup"><span data-stu-id="15bcb-157">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="15bcb-158">**Descrição**.</span><span class="sxs-lookup"><span data-stu-id="15bcb-158">**Description**.</span></span> <span data-ttu-id="15bcb-159">Uma breve descrição do acrônimo que oferece aos usuários mais informações sobre o acrônimo e sua expansão.</span><span class="sxs-lookup"><span data-stu-id="15bcb-159">A brief description of the acronym that gives users more info about the acronym and its expansion.</span></span> <span data-ttu-id="15bcb-160">Por exemplo, *uma rede neural profunda é uma rede neural com um determinado nível de complexidade, uma rede neural com mais de duas camadas*.</span><span class="sxs-lookup"><span data-stu-id="15bcb-160">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="15bcb-161">**Fonte**.</span><span class="sxs-lookup"><span data-stu-id="15bcb-161">**Source**.</span></span> <span data-ttu-id="15bcb-162">A URL da página ou site onde você deseja que os usuários vá para obter mais informações sobre o acrônimo.</span><span class="sxs-lookup"><span data-stu-id="15bcb-162">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="15bcb-163">**Estado**.</span><span class="sxs-lookup"><span data-stu-id="15bcb-163">**State**.</span></span> <span data-ttu-id="15bcb-164">Este campo pode ter dois valores:</span><span class="sxs-lookup"><span data-stu-id="15bcb-164">This field can take two values:</span></span>

- <span data-ttu-id="15bcb-165">**Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="15bcb-165">**Draft**.</span></span> <span data-ttu-id="15bcb-166">Adiciona o acrônimo ao estado de rascunho.</span><span class="sxs-lookup"><span data-stu-id="15bcb-166">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="15bcb-167">**Publicado**.</span><span class="sxs-lookup"><span data-stu-id="15bcb-167">**Published**.</span></span> <span data-ttu-id="15bcb-168">Adiciona a sigla ao estado publicado e a disponibiliza no Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="15bcb-168">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="mined-acronyms"></a><span data-ttu-id="15bcb-169">Acrônimos minados</span><span class="sxs-lookup"><span data-stu-id="15bcb-169">Mined acronyms</span></span>

<span data-ttu-id="15bcb-170">Pode ser um desafio para os administradores adicionarem todos os acrônimos usados dentro de uma organização para responder.</span><span class="sxs-lookup"><span data-stu-id="15bcb-170">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="15bcb-171">Esse recurso pode encontrar acrônimos que os administradores de pesquisa nem são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="15bcb-171">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="15bcb-172">Para fazer isso, a pesquisa da Microsoft também extrai acrônimos dessas fontes:</span><span class="sxs-lookup"><span data-stu-id="15bcb-172">To do that work, Microsoft Search also mines acronyms from these sources:</span></span>

- <span data-ttu-id="15bcb-173">Emails dos usuários.</span><span class="sxs-lookup"><span data-stu-id="15bcb-173">Users’ emails.</span></span>
- <span data-ttu-id="15bcb-174">Documentos no [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft onedrive]( https://onedrive.live.com/about/)e [Microsoft OneNote](https://www.onenote.com/).</span><span class="sxs-lookup"><span data-stu-id="15bcb-174">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/), and [Microsoft OneNote](https://www.onenote.com/).</span></span>
- <span data-ttu-id="15bcb-175">Documentos públicos dentro da organização aos quais os usuários têm acesso no SharePoint, no OneDrive ou no OneNote.</span><span class="sxs-lookup"><span data-stu-id="15bcb-175">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote.</span></span>

<span data-ttu-id="15bcb-176">A pesquisa da Microsoft garante que apenas usuários com acesso e permissões a um documento possam ver os acrônimos que são minados.</span><span class="sxs-lookup"><span data-stu-id="15bcb-176">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are mined from it.</span></span> <span data-ttu-id="15bcb-177">Quando um acrônimo é minado da caixa de correio de um usuário, apenas esse usuário pode ver esse acrônimo.</span><span class="sxs-lookup"><span data-stu-id="15bcb-177">When an acronym is mined from a user's mailbox, only that user can see that acronym.</span></span>

> [!NOTE]
> <span data-ttu-id="15bcb-178">Nenhuma configuração é necessária para acrônimos minados.</span><span class="sxs-lookup"><span data-stu-id="15bcb-178">No setup is needed for mined acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="15bcb-179">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="15bcb-179">Frequently asked questions</span></span>

<span data-ttu-id="15bcb-180">**P: como os dados de editorial e minados são classificados?**</span><span class="sxs-lookup"><span data-stu-id="15bcb-180">**Q: How is editorial and mined data ranked?**</span></span>

<span data-ttu-id="15bcb-181">**A:** O recurso atualmente classifica os acrônimos editoriais acima de acrônimos minados.</span><span class="sxs-lookup"><span data-stu-id="15bcb-181">**A:** The feature currently ranks editorial acronyms above mined acronyms.</span></span>

<span data-ttu-id="15bcb-182">**P: quanto tempo demora para que os acrônimos editoriais fiquem visíveis na pesquisa da Microsoft após serem publicados?**</span><span class="sxs-lookup"><span data-stu-id="15bcb-182">**Q: How long does it take for editorial acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="15bcb-183">**A:**  É necessário até três dias para que os acrônimos adicionados ao estado publicado sejam disponibilizados na pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="15bcb-183">**A:**  It takes up to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="15bcb-184">**P: como os usuários acionam as respostas de acrônimos?**</span><span class="sxs-lookup"><span data-stu-id="15bcb-184">**Q: How do users trigger Acronyms answers?**</span></span>

<span data-ttu-id="15bcb-185">**A**: para obter respostas de acrônimos, os usuários devem inserir padrões de consulta específicos em uma caixa de **pesquisa** [Bing](https://bing.com) ou [SharePoint](https://products.office.com/sharepoint/collaboration) .</span><span class="sxs-lookup"><span data-stu-id="15bcb-185">**A**: To get Acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com) or [SharePoint](https://products.office.com/sharepoint/collaboration) **Search** box.</span></span> <span data-ttu-id="15bcb-186">No momento, as respostas de acrônimo não estão disponíveis no [Office 365](https://Office.com).</span><span class="sxs-lookup"><span data-stu-id="15bcb-186">Currently, Acronym answers aren't available in [Office 365](https://Office.com).</span></span>

<span data-ttu-id="15bcb-187">**P: quanto tempo leva para que acrônimos minados apareçam após você receber ou enviar um novo email ou documento?**</span><span class="sxs-lookup"><span data-stu-id="15bcb-187">**Q: How long does it take for mined acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="15bcb-188">**A:** Os acrônimos minados de um novo email ou documento levam até sete dias para serem exibidos nos resultados da pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="15bcb-188">**A:** Mined acronyms from a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="15bcb-189">**P: os documentos precisam estar em um formato específico para que a mineração os pegue?**</span><span class="sxs-lookup"><span data-stu-id="15bcb-189">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="15bcb-190">**A:** Não.</span><span class="sxs-lookup"><span data-stu-id="15bcb-190">**A:** No.</span></span> <span data-ttu-id="15bcb-191">Oferecemos suporte a todos os tipos de arquivo, exceto imagem, pastas e arquivos zip.</span><span class="sxs-lookup"><span data-stu-id="15bcb-191">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="15bcb-192">**P: a Microsoft vai minar as acrônimos de documentos em todos os idiomas?**</span><span class="sxs-lookup"><span data-stu-id="15bcb-192">**Q: Will Microsoft mine acronyms from documents in all languages?**</span></span>

<span data-ttu-id="15bcb-193">**A: A**Microsoft dá suporte apenas à mineração de documentos em inglês.</span><span class="sxs-lookup"><span data-stu-id="15bcb-193">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="15bcb-194">O suporte para outros idiomas será adicionado em fases.</span><span class="sxs-lookup"><span data-stu-id="15bcb-194">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="15bcb-195">**P: e se minha organização não quiser mostrar acrônimos minados? Posso parar de mostrar acrônimos minados nos resultados da pesquisa?**</span><span class="sxs-lookup"><span data-stu-id="15bcb-195">**Q: What if my organization doesn’t want to show mined acronyms? Can I stop showing mined acronyms in search results?**</span></span>

<span data-ttu-id="15bcb-196">**A**: para desativar a exibição de acrônimos minados nos resultados da pesquisa, crie um tíquete de suporte ao cliente seguindo as instruções em [contato com o suporte para produtos de negócios](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span><span class="sxs-lookup"><span data-stu-id="15bcb-196">**A**: To turn off showing mined acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="15bcb-197">Depois de criar um tíquete de suporte, serão necessários até 48 horas para que os acrônimos minados parem de aparecer nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="15bcb-197">After you create a support ticket, it takes up to 48 hours for mined acronyms to stop appearing in search results.</span></span>

<span data-ttu-id="15bcb-198">**P: Quando verá as respostas de acrônimos no [Office 365](https://Office.com)?**</span><span class="sxs-lookup"><span data-stu-id="15bcb-198">**Q: When will I see Acronyms answers in [Office 365](https://Office.com)?**</span></span>

<span data-ttu-id="15bcb-199">**A**: as respostas dos acrônimos no Office 365 fazem parte do nosso roteiro de produtos, mas não é possível fornecer uma data ou um prazo.</span><span class="sxs-lookup"><span data-stu-id="15bcb-199">**A**: Acronyms answers in Office 365 are part of our product roadmap, but we're currently unable to provide a date or timeframe.</span></span>
