---
title: Perguntas frequentes
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Obtenha respostas para perguntas frequentes comuns sobre o Enterprise Search e a Pesquisa da Microsoft
ms.openlocfilehash: 98128297047d50e2d418a8ed062066ab9e86749e
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031616"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a><span data-ttu-id="9a767-103">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="9a767-103">Frequently asked questions</span></span>

<span data-ttu-id="9a767-104">Esta é uma lista das perguntas mais frequentes.</span><span class="sxs-lookup"><span data-stu-id="9a767-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="9a767-105">Não encontra resposta à sua pergunta aqui?</span><span class="sxs-lookup"><span data-stu-id="9a767-105">Don't see your question answered here?</span></span> <span data-ttu-id="9a767-106">Faça a sua pergunta nos comentários desse artigo.</span><span class="sxs-lookup"><span data-stu-id="9a767-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="9a767-107">Há suporte para noções básicas sobre consultas avançadas?</span><span class="sxs-lookup"><span data-stu-id="9a767-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="9a767-108">Sim, a Pesquisa da Microsoft analisará a intenção de consulta de frases maiores.</span><span class="sxs-lookup"><span data-stu-id="9a767-108">Yes, Microsoft Search parses query intent from larger phrases.</span></span> <span data-ttu-id="9a767-109">Esse recurso usa a IA para aprender frases supérfluas comuns que os usuários adicionam às suas consultas que não impactam suas intenções de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9a767-109">This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent.</span></span> <span data-ttu-id="9a767-110">Por exemplo, quando um usuário procura saber mais sobre como alterar minha *senha,* extraimos as palavras menos importantes da consulta e disparamos com base nas relevantes, como alterar senha *.*</span><span class="sxs-lookup"><span data-stu-id="9a767-110">For example, when a user searches for *tell me more about how to change my password*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="9a767-111">Esse recurso não substituirá palavras-chave definidas no Centro de administração [do Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="9a767-111">This feature won't override keywords set in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="9a767-112">É possível pesquisar arquivos no local?</span><span class="sxs-lookup"><span data-stu-id="9a767-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="9a767-113">Sim.</span><span class="sxs-lookup"><span data-stu-id="9a767-113">Yes.</span></span> <span data-ttu-id="9a767-114">Você pode pesquisar arquivos locais do [SharePoint](http://sharepoint.com/) se tiver uma implantação híbrida do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9a767-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="9a767-115">Como posso transformar o Bing no mecanismo de pesquisa padrão da minha organização?</span><span class="sxs-lookup"><span data-stu-id="9a767-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="9a767-116">Aqui estão as instruções para definir o mecanismo de pesquisa padrão, a homepage padrão e o navegador padrão para dar aos usuários a melhor experiência com a Pesquisa da Microsoft no [Bing](https://Bing.com):</span><span class="sxs-lookup"><span data-stu-id="9a767-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="9a767-117">Definir o Microsoft Edge como seu navegador padrão</span><span class="sxs-lookup"><span data-stu-id="9a767-117">Set Microsoft Edge as your default browser</span></span>](/deployedge/edge-default-browser)
- [<span data-ttu-id="9a767-118">Definir o Bing como mecanismo de pesquisa padrão</span><span class="sxs-lookup"><span data-stu-id="9a767-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="9a767-119">Definir o Bing.com como página inicial da empresa</span><span class="sxs-lookup"><span data-stu-id="9a767-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="9a767-120">Como os resultados da pesquisa são protegidos?</span><span class="sxs-lookup"><span data-stu-id="9a767-120">How are my search results protected?</span></span>

<span data-ttu-id="9a767-121">Exigimos [a autenticação do Azure Active Directory](/azure/active-directory/) para acessar os resultados da Nuvem Confiável.</span><span class="sxs-lookup"><span data-stu-id="9a767-121">We require [Azure Active Directory](/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="9a767-122">Os usuários autenticados apenas visualizam o conteúdo ao qual eles têm acesso.</span><span class="sxs-lookup"><span data-stu-id="9a767-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="9a767-123">As consultas de pesquisa são des identificadas e os logs são separados do tráfego público de pesquisa [do Bing](https://Bing.com) quando você usa a Pesquisa da Microsoft no Bing.</span><span class="sxs-lookup"><span data-stu-id="9a767-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic when you use Microsoft Search in Bing.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="9a767-124">Posso pesquisar nas organizações federadas?</span><span class="sxs-lookup"><span data-stu-id="9a767-124">Can I search across federated organizations?</span></span>

<span data-ttu-id="9a767-125">Não.</span><span class="sxs-lookup"><span data-stu-id="9a767-125">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a><span data-ttu-id="9a767-126">Onde posso obter informações sobre segurança, conformidade e privacidade do Office 365?</span><span class="sxs-lookup"><span data-stu-id="9a767-126">Where can I get info about Office 365 security, compliance, and privacy?</span></span>

<span data-ttu-id="9a767-127">Detalhes podem ser encontrados nas páginas [da Central de Confiações do Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="9a767-127">Details can be found on the [Trust Center pages for Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="9a767-128">Os usuários podem ganhar pontos do Microsoft Rewards com uma conta corporativa ou de estudante?</span><span class="sxs-lookup"><span data-stu-id="9a767-128">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="9a767-129">O Microsoft Search exige que os usuários corporativos entrem com uma conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="9a767-129">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="9a767-130">No entanto, os usuários não podem participar do Microsoft Rewards ou entrar nele com essas contas.</span><span class="sxs-lookup"><span data-stu-id="9a767-130">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="9a767-131">No entanto, há uma situação em que um usuário corporativo pode ver os pontos acumulados.</span><span class="sxs-lookup"><span data-stu-id="9a767-131">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="9a767-132">Isso pode acontecer quando um usuário do Microsoft Search tem uma conta Rewards que foi criada com uma [conta da Microsoft](https://www.microsoft.com/welcome?rtc=1).</span><span class="sxs-lookup"><span data-stu-id="9a767-132">This can happen when a Microsoft Search user has a Rewards account that was created with a [Microsoft account](https://www.microsoft.com/welcome?rtc=1).</span></span> <span data-ttu-id="9a767-133">(O endereço de email associado a uma conta da Microsoft pode ser de Outlook.com, Hotmail.com, Gmail, Yahoo ou outros provedores). Se os usuários entrarem com a conta de trabalho e com a conta da Microsoft na mesma sessão do navegador, eles poderão acumular pontos para a sua conta Rewards.</span><span class="sxs-lookup"><span data-stu-id="9a767-133">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="9a767-134">Os usuários podem parar de acumular pontos quando usarem o Microsoft Search limpando os cookies.</span><span class="sxs-lookup"><span data-stu-id="9a767-134">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span>

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a><span data-ttu-id="9a767-135">Os usuários convidados podem aproveitar a Pesquisa da Microsoft na minha organização?</span><span class="sxs-lookup"><span data-stu-id="9a767-135">Can guest users leverage Microsoft Search in my organization?</span></span>

<span data-ttu-id="9a767-136">O Microsoft 365 permite uma colaboração rica com pessoas fora da sua organização por meio [do acesso de convidados.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span><span class="sxs-lookup"><span data-stu-id="9a767-136">Microsoft 365 enables rich collaboration with people outside of your organization through [guest access.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span></span> <span data-ttu-id="9a767-137">Esses usuários poderão executar operações de pesquisa em documentos, sites, grupos, listas e bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="9a767-137">These users will be able to perform search operations on documents, sites, groups, lists, and libraries.</span></span> <span data-ttu-id="9a767-138">No entanto, os usuários convidados não terão a experiência completa e personalizada da Pesquisa da Microsoft e talvez precisem aproveitar a caixa de pesquisa na página, em vez da caixa unificada da Pesquisa da Microsoft no header.</span><span class="sxs-lookup"><span data-stu-id="9a767-138">However, guest users will not get the full, personalized, Microsoft Search experience and may need to leverage the on-page search box instead of the unified Microsoft Search box in the header.</span></span>