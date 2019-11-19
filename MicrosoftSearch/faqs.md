---
title: Perguntas frequentes
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Obtenha respostas para perguntas frequentes comuns sobre o Enterprise Search e a Pesquisa da Microsoft
ms.openlocfilehash: edfb8346263d60184d8655afa24118ed4b3e3bca
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699789"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="d1658-103">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="d1658-103">Frequently asked questions</span></span>

<span data-ttu-id="d1658-104">Esta é uma lista das perguntas mais frequentes.</span><span class="sxs-lookup"><span data-stu-id="d1658-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="d1658-105">Não encontra resposta à sua pergunta aqui?</span><span class="sxs-lookup"><span data-stu-id="d1658-105">Don't see your question answered here?</span></span> <span data-ttu-id="d1658-106">Faça a sua pergunta nos comentários desse artigo.</span><span class="sxs-lookup"><span data-stu-id="d1658-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="d1658-107">Há suporte para noções básicas sobre consultas avançadas?</span><span class="sxs-lookup"><span data-stu-id="d1658-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="d1658-p102">Sim, o Microsoft Search analisa a intenção de consulta de frases maiores. Este recurso usa o AI para aprender frases supérfluas comuns que os usuários adicionam às suas consultas que não impactam a sua intenção de pesquisa. Por exemplo, quando um usuário pesquisa para *saber mais sobre como alterar minha senha*, extraímos as palavras menos importantes da consulta e do gatilho com base nos relevantes como *alterar senha*.</span><span class="sxs-lookup"><span data-stu-id="d1658-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for *tell me more about how to change my password please*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="d1658-111">Este recurso não substituirá as palavras-chave definidas no [centro de administração](https://admin.microsoft.com)do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d1658-111">This feature won't override keywords set in the Microsoft 365 [admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="d1658-112">É possível pesquisar arquivos no local?</span><span class="sxs-lookup"><span data-stu-id="d1658-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="d1658-113">Sim.</span><span class="sxs-lookup"><span data-stu-id="d1658-113">Yes.</span></span> <span data-ttu-id="d1658-114">Você pode pesquisar arquivos [do SharePoint](http://sharepoint.com/) no local se tiver uma implantação híbrida do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="d1658-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="d1658-115">Como posso transformar o Bing no mecanismo de pesquisa padrão da minha organização?</span><span class="sxs-lookup"><span data-stu-id="d1658-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="d1658-116">Veja a seguir as instruções para configurar o mecanismo de pesquisa padrão, a Home Page padrão e o navegador padrão para dar aos seus usuários a melhor experiência com o Microsoft Search no [Bing](https://Bing.com):</span><span class="sxs-lookup"><span data-stu-id="d1658-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="d1658-117">Definir o Microsoft Edge como seu navegador padrão</span><span class="sxs-lookup"><span data-stu-id="d1658-117">Set Microsoft Edge as your default browser</span></span>](set-default-browser.md)
- [<span data-ttu-id="d1658-118">Definir o Bing como mecanismo de pesquisa padrão</span><span class="sxs-lookup"><span data-stu-id="d1658-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="d1658-119">Definir o Bing.com como página inicial da empresa</span><span class="sxs-lookup"><span data-stu-id="d1658-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="d1658-120">Como os resultados da pesquisa são protegidos?</span><span class="sxs-lookup"><span data-stu-id="d1658-120">How are my search results protected?</span></span>

<span data-ttu-id="d1658-121">Requer a autenticação [do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) para acessar os resultados da nuvem confiável.</span><span class="sxs-lookup"><span data-stu-id="d1658-121">We require [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="d1658-122">Os usuários autenticados apenas visualizam o conteúdo ao qual eles têm acesso.</span><span class="sxs-lookup"><span data-stu-id="d1658-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="d1658-123">As consultas de pesquisa são desidentificadas e os logs são separados do tráfego de pesquisa do [Bing](https://Bing.com) público.</span><span class="sxs-lookup"><span data-stu-id="d1658-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic.</span></span> <span data-ttu-id="d1658-124">Esse nível de proteção não está disponível em nenhum outro local do setor.</span><span class="sxs-lookup"><span data-stu-id="d1658-124">This level of protection is unavailable anywhere else in the industry.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="d1658-125">Posso pesquisar nas organizações federadas?</span><span class="sxs-lookup"><span data-stu-id="d1658-125">Can I search across federated organizations?</span></span>

<span data-ttu-id="d1658-126">Não.</span><span class="sxs-lookup"><span data-stu-id="d1658-126">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a><span data-ttu-id="d1658-127">Onde posso obter informações sobre os níveis e categorias de conformidade do Office 365 e do Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="d1658-127">Where can I get info about Office 365 and Microsoft 365 compliance tiers and categories?</span></span>

<span data-ttu-id="d1658-128">Os detalhes podem ser encontrados em [Estrutura de Conformidade para Padrões e Regulamentações do Setor](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (baixar o PDF).</span><span class="sxs-lookup"><span data-stu-id="d1658-128">Details can be found in the [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download).</span></span>

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a><span data-ttu-id="d1658-129">Os usuários podem ganhar pontos do Microsoft Rewards com uma conta corporativa ou de estudante?</span><span class="sxs-lookup"><span data-stu-id="d1658-129">Can users earn Microsoft Rewards points with their work or school account?</span></span>

<span data-ttu-id="d1658-130">O Microsoft Search exige que os usuários corporativos entrem com uma conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="d1658-130">Microsoft Search requires that enterprise users sign in with a work or school account.</span></span> <span data-ttu-id="d1658-131">No entanto, os usuários não podem participar do Microsoft Rewards ou entrar nele com essas contas.</span><span class="sxs-lookup"><span data-stu-id="d1658-131">But users can’t join or sign in to the Microsoft Rewards program with those accounts.</span></span> <span data-ttu-id="d1658-132">No entanto, há uma situação em que um usuário corporativo pode ver os pontos acumulados.</span><span class="sxs-lookup"><span data-stu-id="d1658-132">However, there is an instance when an enterprise user may see Rewards points accrue.</span></span> <span data-ttu-id="d1658-133">Isso pode acontecer quando um usuário do Microsoft Search tem uma conta Rewards que foi criada com uma <a href="https://www.microsoft.com/welcome?rtc=1">conta da Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="d1658-133">This can happen when a Microsoft Search user has a Rewards account that was created with a <a href="https://www.microsoft.com/welcome?rtc=1">Microsoft account</a>.</span></span> <span data-ttu-id="d1658-134">(O endereço de email associado a uma conta da Microsoft pode ser de Outlook.com, Hotmail.com, Gmail, Yahoo ou outros provedores). Se os usuários entrarem com a conta de trabalho e com a conta da Microsoft na mesma sessão do navegador, eles poderão acumular pontos para a sua conta Rewards.</span><span class="sxs-lookup"><span data-stu-id="d1658-134">(The email address associated with a Microsoft account can be from Outlook.com, Hotmail.com, Gmail, Yahoo, or other providers.) If users sign in alternately with both their work account and Microsoft account in the same browser session, they might accrue points to their Rewards account.</span></span> <span data-ttu-id="d1658-135">Os usuários podem parar de acumular pontos quando usarem o Microsoft Search limpando os cookies.</span><span class="sxs-lookup"><span data-stu-id="d1658-135">Users can stop accruing points while searching with Microsoft Search by clearing their cookies.</span></span> 

