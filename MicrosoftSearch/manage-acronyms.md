---
title: Gerenciar as respostas de acrônimo no Microsoft Search
ms.author: v-pamcna
author: TrishaMc1
manager: mnirkhe
ms.date: 10/28/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Criar e atualizar respostas de acrônimos no Microsoft Search
ms.openlocfilehash: 8ff48f1eaa4ef8dab83411fad2f0ee4367158cd1
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949584"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a><span data-ttu-id="314ab-103">Gerenciar as respostas de acrônimos no Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="314ab-103">Manage Acronyms answers in Microsoft Search</span></span>

<span data-ttu-id="314ab-104">Os funcionários freqüentemente têm um acrônimo e abreviaturas desconhecidos usados por sua organização ou equipe.</span><span class="sxs-lookup"><span data-stu-id="314ab-104">Employees often run into unfamiliar acronyms and abbreviations used by their organization or team.</span></span> <span data-ttu-id="314ab-105">Os termos específicos para organizações ou equipes podem ser novos para pessoas que se movem de uma equipe para outra, aqueles que trabalham com equipes de parceiros internas ou novos funcionários.</span><span class="sxs-lookup"><span data-stu-id="314ab-105">Terms that are specific to organizations or teams might be new to people who move from one team to another, those who work with internal partner teams, or new employees.</span></span>

<span data-ttu-id="314ab-106">As organizações nem sempre têm uma única referência para sua terminologia padrão.</span><span class="sxs-lookup"><span data-stu-id="314ab-106">Organizations don't always have a single reference for their standard terminology.</span></span> <span data-ttu-id="314ab-107">A falta de uma única referência dificulta a localização de definições ou expansões desses acrônimos.</span><span class="sxs-lookup"><span data-stu-id="314ab-107">Lack of a single reference makes it hard to find definitions or expansions for these acronyms.</span></span> <span data-ttu-id="314ab-108">O Microsoft Search resolve esse problema com acrônimos.</span><span class="sxs-lookup"><span data-stu-id="314ab-108">Microsoft Search solves that problem with Acronyms.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="314ab-109">O que os usuários experimentam</span><span class="sxs-lookup"><span data-stu-id="314ab-109">What users experience</span></span>
<span data-ttu-id="314ab-110">Os usuários de pesquisa da Microsoft podem obter definições com acrônimos no [Bing](https://Bing.com), [Microsoft Office 365](https://Office.com)e [Microsoft SharePoint Online](https://products.office.com/sharepoint/collaboration).</span><span class="sxs-lookup"><span data-stu-id="314ab-110">Microsoft Search users can get definitions with Acronyms in [Bing](https://Bing.com), [Microsoft Office 365](https://Office.com), and [Microsoft SharePoint Online](https://products.office.com/sharepoint/collaboration).</span></span> <span data-ttu-id="314ab-111">Nas caixas de **pesquisa** nas barras de cabeçalho, os usuários inserem consultas como estes exemplos:</span><span class="sxs-lookup"><span data-stu-id="314ab-111">In the **Search** boxes in the header bars, users enter queries like these examples:</span></span>

- <span data-ttu-id="314ab-112">*O que é* DNN</span><span class="sxs-lookup"><span data-stu-id="314ab-112">*What is* DNN</span></span>
- <span data-ttu-id="314ab-113">*Definir* DNN</span><span class="sxs-lookup"><span data-stu-id="314ab-113">*Define* DNN</span></span>
- <span data-ttu-id="314ab-114">*Definição* DNN</span><span class="sxs-lookup"><span data-stu-id="314ab-114">DNN *definition*</span></span>
- <span data-ttu-id="314ab-115">*Expand* DNN</span><span class="sxs-lookup"><span data-stu-id="314ab-115">*Expand* DNN</span></span>
- <span data-ttu-id="314ab-116">*Expansão* DNN</span><span class="sxs-lookup"><span data-stu-id="314ab-116">DNN *expansion*</span></span>
- <span data-ttu-id="314ab-117">*Significado de* DNN</span><span class="sxs-lookup"><span data-stu-id="314ab-117">*Meaning of* DNN</span></span>
- <span data-ttu-id="314ab-118">DNN *significa*</span><span class="sxs-lookup"><span data-stu-id="314ab-118">DNN *means*</span></span>

<span data-ttu-id="314ab-119">Os resultados sugeridos incluem todos os significados do DNN que estão presentes na organização do usuário.</span><span class="sxs-lookup"><span data-stu-id="314ab-119">The suggested results include all the meanings of DNN that are present within the user’s organization.</span></span>

> [!NOTE]
> <span data-ttu-id="314ab-120">Os usuários devem inserir uma consulta que inclua as *palavras-chave* especificadas pelo acrônimo para disparar suas respostas correspondentes.</span><span class="sxs-lookup"><span data-stu-id="314ab-120">Users must enter a query that includes the acronym’s specified *keywords* to trigger its corresponding answers.</span></span>  

## <a name="set-up-acronyms-answers"></a><span data-ttu-id="314ab-121">Configurar respostas de acrônimos</span><span class="sxs-lookup"><span data-stu-id="314ab-121">Set up Acronyms answers</span></span>
<span data-ttu-id="314ab-122">No [centro de administração](https://admin.microsoft.com)do Microsoft 365, vá para **configurações** > **acrônimos**de**pesquisa** >da Microsoft e selecione **Adicionar acrônimos**.</span><span class="sxs-lookup"><span data-stu-id="314ab-122">In the Microsoft 365 [admin center](https://admin.microsoft.com), go to **Settings** > **Microsoft Search** >**Acronyms**, and then select **Add acronyms**.</span></span> 

<span data-ttu-id="314ab-123">O Microsoft Search consulta duas fontes de dados para fornecer respostas de acrônimos às pesquisas dos usuários:</span><span class="sxs-lookup"><span data-stu-id="314ab-123">Microsoft Search queries two data sources to provide Acronyms answers to users’ searches:</span></span>

1.  <span data-ttu-id="314ab-124">**Acrônimos editoriais**.</span><span class="sxs-lookup"><span data-stu-id="314ab-124">**Editorial acronyms**.</span></span> <span data-ttu-id="314ab-125">Fornecido por administradores de ti no [centro de administração](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="314ab-125">Provided by IT administrators in the [admin center](https://admin.microsoft.com).</span></span>
2.  <span data-ttu-id="314ab-126">**Acrônimos minados**.</span><span class="sxs-lookup"><span data-stu-id="314ab-126">**Mined acronyms**.</span></span> <span data-ttu-id="314ab-127">O Microsoft Search dos emails e dos documentos pessoais do usuário e dos dados publicamente disponíveis dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="314ab-127">Mined by Microsoft Search from the user’s personal email and documents and publicly available data within the organization.</span></span>

### <a name="set-up-editorial-acronyms"></a><span data-ttu-id="314ab-128">Configurar acrônimos editoriais</span><span class="sxs-lookup"><span data-stu-id="314ab-128">Set up editorial acronyms</span></span>
<span data-ttu-id="314ab-129">Os administradores de ti podem configurar acrônimos editoriais na [guia acrônimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) no [centro de administração do Microsoft 365]( https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="314ab-129">IT admins can set up editorial acronyms on the [Acronyms tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) in the  [Microsoft 365 admin center]( https://admin.microsoft.com).</span></span> <span data-ttu-id="314ab-130">Você pode adicionar acrônimos de qualquer site ou repositório interno ao centro de administração.</span><span class="sxs-lookup"><span data-stu-id="314ab-130">You can add acronyms from any internal site or repository to the admin center.</span></span> <span data-ttu-id="314ab-131">Acrônimos editoriais podem ser adicionados ao estado **publicado** ou de **rascunho** :</span><span class="sxs-lookup"><span data-stu-id="314ab-131">Editorial acronyms can be added to **Published** or **Draft** state:</span></span>

<span data-ttu-id="314ab-132">**Estado publicado**.</span><span class="sxs-lookup"><span data-stu-id="314ab-132">**Published state**.</span></span> <span data-ttu-id="314ab-133">Os acrônimos estão disponíveis para os funcionários da organização através da pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="314ab-133">Acronyms are available to the organization’s employees through Microsoft Search.</span></span>

> [!NOTE]
> <span data-ttu-id="314ab-134">Pode levar até três dias para que os acrônimos adicionados ao estado publicado fiquem disponíveis no Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="314ab-134">It might take up  to three days for acronyms added to Published state to become available in Microsoft Search.</span></span>

<span data-ttu-id="314ab-135">**Estado de rascunho**.</span><span class="sxs-lookup"><span data-stu-id="314ab-135">**Draft state**.</span></span> <span data-ttu-id="314ab-136">Se os administradores desejarem revisar as respostas de acrônimos antes de disponibilizá-las no Microsoft Search, poderão adicionar os acrônimos ao estado de rascunho.</span><span class="sxs-lookup"><span data-stu-id="314ab-136">If admins want to review Acronyms answers before making them available in Microsoft Search, they can add the acronyms to Draft state.</span></span> <span data-ttu-id="314ab-137">Os acrônimos adicionados ao estado de rascunho não estão disponíveis no Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="314ab-137">Acronyms added to Draft state aren’t available in Microsoft Search.</span></span> <span data-ttu-id="314ab-138">Os administradores precisam adicionar os acrônimos ao estado publicado para torná-los disponíveis.</span><span class="sxs-lookup"><span data-stu-id="314ab-138">Admins need to add the acronyms to Published state to make them available.</span></span>

<span data-ttu-id="314ab-139">Os administradores podem adicionar acrônimos individualmente ou importá-los em massa em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="314ab-139">Admins can add acronyms individually or bulk import them in a CSV file.</span></span> <span data-ttu-id="314ab-140">Carregue um arquivo CSV com os campos mostrados na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="314ab-140">Upload a CSV file with the fields shown in the following table:</span></span>

| <span data-ttu-id="314ab-141">Sigla (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="314ab-141">Acronym (mandatory)</span></span> | <span data-ttu-id="314ab-142">Expansão (obrigatória)</span><span class="sxs-lookup"><span data-stu-id="314ab-142">Expansion (mandatory)</span></span> | <span data-ttu-id="314ab-143">Descrição</span><span class="sxs-lookup"><span data-stu-id="314ab-143">Description</span></span>  | <span data-ttu-id="314ab-144">Origem</span><span class="sxs-lookup"><span data-stu-id="314ab-144">Source</span></span> | <span data-ttu-id="314ab-145">Estado (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="314ab-145">State (mandatory)</span></span> |
| --------- | --------- | ---------- | --------- |--------- |
| <span data-ttu-id="314ab-146">*XXX*</span><span class="sxs-lookup"><span data-stu-id="314ab-146">*XXX*</span></span> | <span data-ttu-id="314ab-147">*Abreviatura de abreviação*</span><span class="sxs-lookup"><span data-stu-id="314ab-147">*Spelled out abbreviation*</span></span> |  | <span data-ttu-id="314ab-148">*URL*</span><span class="sxs-lookup"><span data-stu-id="314ab-148">*URL*</span></span> | <span data-ttu-id="314ab-149">*Publicado ou rascunho*</span><span class="sxs-lookup"><span data-stu-id="314ab-149">*Published or Draft*</span></span> |

### <a name="csv-fields"></a><span data-ttu-id="314ab-150">Campos CSV</span><span class="sxs-lookup"><span data-stu-id="314ab-150">CSV fields</span></span>
<span data-ttu-id="314ab-151">**Sigla**.</span><span class="sxs-lookup"><span data-stu-id="314ab-151">**Acronym**.</span></span> <span data-ttu-id="314ab-152">Contém a forma curta ou sigla real.</span><span class="sxs-lookup"><span data-stu-id="314ab-152">Contains the actual short form or acronym.</span></span> <span data-ttu-id="314ab-153">Um exemplo é *DNN*.</span><span class="sxs-lookup"><span data-stu-id="314ab-153">An example is *DNN*.</span></span>

<span data-ttu-id="314ab-154">**Expansão**.</span><span class="sxs-lookup"><span data-stu-id="314ab-154">**Expansion**.</span></span> <span data-ttu-id="314ab-155">Contém a expansão do acrônimo.</span><span class="sxs-lookup"><span data-stu-id="314ab-155">Contains the expansion of the acronym.</span></span> <span data-ttu-id="314ab-156">Um exemplo é uma *rede neural profunda*.</span><span class="sxs-lookup"><span data-stu-id="314ab-156">An example is *Deep Neural Network*.</span></span>

<span data-ttu-id="314ab-157">**Descrição**.</span><span class="sxs-lookup"><span data-stu-id="314ab-157">**Description**.</span></span> <span data-ttu-id="314ab-158">Uma breve descrição do acrônimo que oferece aos usuários uma percepção rápida sobre o que o acrônimo e sua média de expansão.</span><span class="sxs-lookup"><span data-stu-id="314ab-158">A brief description of the acronym that gives users quick insight into what the acronym and its expansion mean.</span></span> <span data-ttu-id="314ab-159">Por exemplo, *uma rede neural profunda é uma rede neural com um determinado nível de complexidade, uma rede neural com mais de duas camadas*.</span><span class="sxs-lookup"><span data-stu-id="314ab-159">For example, *A deep neural network is a neural network with a certain level of complexity, a neural network with more than two layers*.</span></span>

<span data-ttu-id="314ab-160">**Fonte**.</span><span class="sxs-lookup"><span data-stu-id="314ab-160">**Source**.</span></span> <span data-ttu-id="314ab-161">A URL da página ou site onde você deseja que os usuários vá para obter mais informações sobre o acrônimo.</span><span class="sxs-lookup"><span data-stu-id="314ab-161">The URL of the page or website where you want users to go for more information about the acronym.</span></span>

<span data-ttu-id="314ab-162">**Estado**.</span><span class="sxs-lookup"><span data-stu-id="314ab-162">**State**.</span></span> <span data-ttu-id="314ab-163">Este campo pode ter dois valores:</span><span class="sxs-lookup"><span data-stu-id="314ab-163">This field can take two values:</span></span>

- <span data-ttu-id="314ab-164">**Rascunho**.</span><span class="sxs-lookup"><span data-stu-id="314ab-164">**Draft**.</span></span> <span data-ttu-id="314ab-165">Adiciona o acrônimo ao estado de rascunho.</span><span class="sxs-lookup"><span data-stu-id="314ab-165">Adds  the acronym to the Draft state.</span></span>
- <span data-ttu-id="314ab-166">**Publicado**.</span><span class="sxs-lookup"><span data-stu-id="314ab-166">**Published**.</span></span> <span data-ttu-id="314ab-167">Adiciona a sigla ao estado publicado e a disponibiliza no Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="314ab-167">Adds the acronym to the Published state and makes it available in Microsoft Search.</span></span>

### <a name="mined-acronyms"></a><span data-ttu-id="314ab-168">Acrônimos minados</span><span class="sxs-lookup"><span data-stu-id="314ab-168">Mined acronyms</span></span>
<span data-ttu-id="314ab-169">Pode ser um desafio para os administradores adicionarem todos os acrônimos usados dentro de uma organização para responder.</span><span class="sxs-lookup"><span data-stu-id="314ab-169">It might be a challenge for admins to add all the acronyms used within an organization to Answers.</span></span> <span data-ttu-id="314ab-170">Esse recurso pode encontrar acrônimos que os administradores de pesquisa nem são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="314ab-170">This feature can find acronyms that search administrators aren’t even aware of.</span></span> <span data-ttu-id="314ab-171">Para fazer isso, a pesquisa da Microsoft também extrai acrônimos dessas fontes:</span><span class="sxs-lookup"><span data-stu-id="314ab-171">To do that work, Microsoft Search also mines acronyms from these sources:</span></span>

- <span data-ttu-id="314ab-172">Emails dos usuários.</span><span class="sxs-lookup"><span data-stu-id="314ab-172">Users’ emails.</span></span>
- <span data-ttu-id="314ab-173">Documentos no [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft onedrive]( https://onedrive.live.com/about/) e [Microsoft OneNote](http://www.onenote.com/).</span><span class="sxs-lookup"><span data-stu-id="314ab-173">Documents in [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft OneDrive]( https://onedrive.live.com/about/) and [Microsoft OneNote](http://www.onenote.com/).</span></span>
- <span data-ttu-id="314ab-174">Documentos públicos dentro da organização aos quais os usuários têm acesso no SharePoint, no OneDrive ou no OneNote.</span><span class="sxs-lookup"><span data-stu-id="314ab-174">Public documents within the organization that users have access to in SharePoint, OneDrive, or OneNote.</span></span>

<span data-ttu-id="314ab-175">A pesquisa da Microsoft garante que apenas usuários com acesso e permissões a um documento possam ver os acrônimos que são minados.</span><span class="sxs-lookup"><span data-stu-id="314ab-175">Microsoft Search makes sure that only users with access and permissions to a document can see the acronyms that are mined from it.</span></span> <span data-ttu-id="314ab-176">Os acrônimos são minados da caixa de entrada de um usuário e armazenados no fragmentos de usuários.</span><span class="sxs-lookup"><span data-stu-id="314ab-176">The acronyms are mined from a user’s inbox and stored in the user shard.</span></span> <span data-ttu-id="314ab-177">Somente o usuário pode acessar os acrônimos minados da caixa de entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="314ab-177">Only the user can access the acronyms mined from the user’s own inbox.</span></span>

> [!NOTE]
> <span data-ttu-id="314ab-178">Nenhuma configuração de administração de ti é necessária para acrônimos minados.</span><span class="sxs-lookup"><span data-stu-id="314ab-178">No IT admin setup is needed for mined acronyms.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="314ab-179">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="314ab-179">Frequently asked questions</span></span>
<span data-ttu-id="314ab-180">**P: como os dados de editorial e minados são classificados?**</span><span class="sxs-lookup"><span data-stu-id="314ab-180">**Q: How is editorial and mined data ranked?**</span></span>

<span data-ttu-id="314ab-181">**A:** O recurso atualmente classifica os acrônimos editoriais acima de acrônimos minados.</span><span class="sxs-lookup"><span data-stu-id="314ab-181">**A:** The feature currently ranks editorial acronyms above mined acronyms.</span></span>

<span data-ttu-id="314ab-182">**P: quanto tempo demora para que os acrônimos editoriais fiquem visíveis na pesquisa da Microsoft após serem publicados?**</span><span class="sxs-lookup"><span data-stu-id="314ab-182">**Q: How long does it take for editorial acronyms to be visible in Microsoft Search after they’re published?**</span></span>

<span data-ttu-id="314ab-183">**A:**  É necessário até três dias para que os acrônimos adicionados ao estado publicado sejam disponibilizados na pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="314ab-183">**A:**  It takes up  to three days for acronyms added to Published state to become available in Microsoft Search.</span></span> 

<span data-ttu-id="314ab-184">**P: como os usuários acionam as respostas de acrônimos?**</span><span class="sxs-lookup"><span data-stu-id="314ab-184">**Q: How do users trigger Acronyms answers?**</span></span>

<span data-ttu-id="314ab-185">**A**: para obter respostas de acrônimos, os usuários devem inserir padrões de consulta específicos em uma caixa de **pesquisa** [Bing](https://bing.com), [Office 365](https://Office.com)ou [SharePoint](https://products.office.com/sharepoint/collaboration) .</span><span class="sxs-lookup"><span data-stu-id="314ab-185">**A**: To get Acronyms answers, users must enter specific query patterns in a [Bing](https://bing.com), [Office 365](https://Office.com), or [SharePoint](https://products.office.com/sharepoint/collaboration) **Search** box.</span></span> <span data-ttu-id="314ab-186">Exemplos de consultas que encontrem respostas para o termo *DNN* são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="314ab-186">Examples of queries that find answers for the term *DNN* are as follows:</span></span>

- <span data-ttu-id="314ab-187">*O que é* DNN</span><span class="sxs-lookup"><span data-stu-id="314ab-187">*What is* DNN</span></span>
- <span data-ttu-id="314ab-188">*Definir* DNN</span><span class="sxs-lookup"><span data-stu-id="314ab-188">*Define* DNN</span></span>
- <span data-ttu-id="314ab-189">*Definição* DNN</span><span class="sxs-lookup"><span data-stu-id="314ab-189">DNN *definition*</span></span>
- <span data-ttu-id="314ab-190">*Expand* DNN</span><span class="sxs-lookup"><span data-stu-id="314ab-190">*Expand* DNN</span></span>
- <span data-ttu-id="314ab-191">*Expansão* DNN</span><span class="sxs-lookup"><span data-stu-id="314ab-191">DNN *expansion*</span></span>
- <span data-ttu-id="314ab-192">*Significado de* DNN</span><span class="sxs-lookup"><span data-stu-id="314ab-192">*Meaning of* DNN</span></span>
- <span data-ttu-id="314ab-193">DNN *significa*</span><span class="sxs-lookup"><span data-stu-id="314ab-193">DNN *means*</span></span>

<span data-ttu-id="314ab-194">**P: quanto tempo leva para que acrônimos minados apareçam após você receber ou enviar um novo email ou documento?**</span><span class="sxs-lookup"><span data-stu-id="314ab-194">**Q: How long does it take for mined acronyms to appear after you receive or send a new email or document?**</span></span>

<span data-ttu-id="314ab-195">**A:** Os acrônimos minados de um novo email ou documento levam até sete dias para serem exibidos nos resultados da pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="314ab-195">**A:** Mined acronyms from a new email or document take up to seven days to appear in Microsoft Search results.</span></span>

<span data-ttu-id="314ab-196">**P: os documentos precisam estar em um formato específico para que a mineração os pegue?**</span><span class="sxs-lookup"><span data-stu-id="314ab-196">**Q: Do documents need to be in a specific format for mining to pick them up?**</span></span>

<span data-ttu-id="314ab-197">**A:** Não.</span><span class="sxs-lookup"><span data-stu-id="314ab-197">**A:** No.</span></span> <span data-ttu-id="314ab-198">Oferecemos suporte a todos os tipos de arquivo, exceto imagem, pastas e arquivos zip.</span><span class="sxs-lookup"><span data-stu-id="314ab-198">We support all file types except image, folders, and zip files.</span></span>

<span data-ttu-id="314ab-199">**P: a Microsoft vai minar as acrônimos de documentos em todos os idiomas?**</span><span class="sxs-lookup"><span data-stu-id="314ab-199">**Q: Will Microsoft mine acronyms from documents in all languages?**</span></span>

<span data-ttu-id="314ab-200">**A: A**Microsoft dá suporte apenas à mineração de documentos em inglês.</span><span class="sxs-lookup"><span data-stu-id="314ab-200">**A**: Microsoft only supports mining from documents in English.</span></span> <span data-ttu-id="314ab-201">O suporte para outros idiomas será adicionado em fases.</span><span class="sxs-lookup"><span data-stu-id="314ab-201">Support for other languages will be added in phases.</span></span>

<span data-ttu-id="314ab-202">**P: e se minha organização não quiser mostrar acrônimos minados? Posso parar de mostrar acrônimos minados nos resultados da pesquisa?**</span><span class="sxs-lookup"><span data-stu-id="314ab-202">**Q: What if my organization doesn’t want to show mined acronyms? Can I stop showing mined acronyms in search results?**</span></span>

<span data-ttu-id="314ab-203">**A**: para desativar a exibição de acrônimos minados nos resultados da pesquisa, crie um tíquete de suporte ao cliente seguindo as instruções em [contato com o suporte para produtos de negócios](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252fen-us%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span><span class="sxs-lookup"><span data-stu-id="314ab-203">**A**: To turn off showing mined acronyms in search results, create a customer support ticket by following the instructions at [Contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252fen-us%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).</span></span>
<span data-ttu-id="314ab-204">Depois de criar um tíquete de suporte, serão necessários até 48 horas para que os acrônimos minados parem de aparecer nos resultados da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="314ab-204">After you create a support ticket, it takes up to 48 hours for mined acronyms to stop appearing in search results.</span></span> 

<span data-ttu-id="314ab-205">**P: Quando verá as respostas de acrônimos no [Office 365](https://Office.com) e no [SharePoint Online](https://products.office.com/sharepoint/collaboration)?**</span><span class="sxs-lookup"><span data-stu-id="314ab-205">**Q: When will I see Acronyms answers in [Office 365](https://Office.com) and [SharePoint Online](https://products.office.com/sharepoint/collaboration)?**</span></span>

<span data-ttu-id="314ab-206">**A**: as respostas de acrônimos atualmente só estão disponíveis no Microsoft Search no [Bing](https://bing.com).</span><span class="sxs-lookup"><span data-stu-id="314ab-206">**A**: Acronyms answers are currently only available in Microsoft Search in [Bing](https://bing.com).</span></span> <span data-ttu-id="314ab-207">Eles serão implantados no Office 365 e no SharePoint Online no 2020.</span><span class="sxs-lookup"><span data-stu-id="314ab-207">They’ll be rolled out to Office 365 and SharePoint Online in 2020.</span></span>
