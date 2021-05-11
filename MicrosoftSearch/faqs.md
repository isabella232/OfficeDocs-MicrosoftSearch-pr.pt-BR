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
ms.openlocfilehash: 614fa241f353533b1c1e181904eb961fd55d0dfa
ms.sourcegitcommit: ea784081bc9c3ae7981a87a493d3a74503859dda
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306066"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a><span data-ttu-id="344a4-103">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="344a4-103">Frequently asked questions</span></span>

<span data-ttu-id="344a4-104">Esta é uma lista das perguntas mais frequentes.</span><span class="sxs-lookup"><span data-stu-id="344a4-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="344a4-105">Não encontra resposta à sua pergunta aqui?</span><span class="sxs-lookup"><span data-stu-id="344a4-105">Don't see your question answered here?</span></span> <span data-ttu-id="344a4-106">Faça a sua pergunta nos comentários desse artigo.</span><span class="sxs-lookup"><span data-stu-id="344a4-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="344a4-107">Há suporte para noções básicas sobre consultas avançadas?</span><span class="sxs-lookup"><span data-stu-id="344a4-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="344a4-108">Sim, a Pesquisa da Microsoft analisará a intenção de consulta de frases maiores.</span><span class="sxs-lookup"><span data-stu-id="344a4-108">Yes, Microsoft Search parses query intent from larger phrases.</span></span> <span data-ttu-id="344a4-109">Esse recurso usa a IA para aprender frases supérfluas comuns que os usuários adicionam às suas consultas que não impactam suas intenções de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="344a4-109">This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent.</span></span> <span data-ttu-id="344a4-110">Por exemplo, quando um usuário procura saber mais sobre como alterar minha *senha,* extraimos as palavras menos importantes da consulta e disparamos com base nas relevantes, como alterar senha *.*</span><span class="sxs-lookup"><span data-stu-id="344a4-110">For example, when a user searches for *tell me more about how to change my password*, we extract the less important words from the query and trigger based on the relevant ones like *change password*.</span></span>
  
<span data-ttu-id="344a4-111">Esse recurso não substituirá palavras-chave definidas no centro [Microsoft 365 administrador.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="344a4-111">This feature won't override keywords set in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="344a4-112">É possível pesquisar arquivos no local?</span><span class="sxs-lookup"><span data-stu-id="344a4-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="344a4-113">Sim.</span><span class="sxs-lookup"><span data-stu-id="344a4-113">Yes.</span></span> <span data-ttu-id="344a4-114">Você pode pesquisar arquivos SharePoint [locais](http://sharepoint.com/) se tiver uma implantação híbrida de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="344a4-114">You can search on-premises [SharePoint](http://sharepoint.com/) files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="344a4-115">Como posso transformar o Bing no mecanismo de pesquisa padrão da minha organização?</span><span class="sxs-lookup"><span data-stu-id="344a4-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="344a4-116">Aqui estão as instruções para definir o mecanismo de pesquisa padrão, a homepage padrão e o navegador padrão para dar aos usuários a melhor experiência com a Pesquisa da Microsoft [em](https://Bing.com)Bing :</span><span class="sxs-lookup"><span data-stu-id="344a4-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in [Bing](https://Bing.com):</span></span>

- [<span data-ttu-id="344a4-117">Definir Microsoft Edge como seu navegador padrão</span><span class="sxs-lookup"><span data-stu-id="344a4-117">Set Microsoft Edge as your default browser</span></span>](/deployedge/edge-default-browser)
- [<span data-ttu-id="344a4-118">Definir o Bing como mecanismo de pesquisa padrão</span><span class="sxs-lookup"><span data-stu-id="344a4-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="344a4-119">Definir o Bing.com como página inicial da empresa</span><span class="sxs-lookup"><span data-stu-id="344a4-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="344a4-120">Como os resultados da pesquisa são protegidos?</span><span class="sxs-lookup"><span data-stu-id="344a4-120">How are my search results protected?</span></span>

<span data-ttu-id="344a4-121">Exigimos [Azure Active Directory](/azure/active-directory/) autenticação para acessar resultados da Nuvem Confiável.</span><span class="sxs-lookup"><span data-stu-id="344a4-121">We require [Azure Active Directory](/azure/active-directory/) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="344a4-122">Os usuários autenticados apenas visualizam o conteúdo ao qual eles têm acesso.</span><span class="sxs-lookup"><span data-stu-id="344a4-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="344a4-123">As consultas de pesquisa são des identificadas [](https://Bing.com) e os logs são separados do tráfego de pesquisa Bing público quando você usa a Pesquisa da Microsoft no Bing.</span><span class="sxs-lookup"><span data-stu-id="344a4-123">Search queries are de-identified, and logs are separated from public [Bing](https://Bing.com) search traffic when you use Microsoft Search in Bing.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="344a4-124">Posso pesquisar nas organizações federadas?</span><span class="sxs-lookup"><span data-stu-id="344a4-124">Can I search across federated organizations?</span></span>

<span data-ttu-id="344a4-125">Não.</span><span class="sxs-lookup"><span data-stu-id="344a4-125">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a><span data-ttu-id="344a4-126">Onde posso obter informações sobre Office 365 segurança, conformidade e privacidade?</span><span class="sxs-lookup"><span data-stu-id="344a4-126">Where can I get info about Office 365 security, compliance, and privacy?</span></span>

<span data-ttu-id="344a4-127">Os detalhes podem ser encontrados nas páginas [da Central de Confiações para Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="344a4-127">Details can be found on the [Trust Center pages for Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).</span></span>

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a><span data-ttu-id="344a4-128">Os usuários convidados podem aproveitar a Pesquisa da Microsoft na minha organização?</span><span class="sxs-lookup"><span data-stu-id="344a4-128">Can guest users leverage Microsoft Search in my organization?</span></span>

<span data-ttu-id="344a4-129">Microsoft 365 permite a colaboração com pessoas de fora da sua organização por meio [do acesso de convidados.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span><span class="sxs-lookup"><span data-stu-id="344a4-129">Microsoft 365 enables rich collaboration with people outside of your organization through [guest access.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization)</span></span> <span data-ttu-id="344a4-130">Esses usuários poderão executar operações de pesquisa em documentos, sites, grupos, listas e bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="344a4-130">These users will be able to perform search operations on documents, sites, groups, lists, and libraries.</span></span> <span data-ttu-id="344a4-131">No entanto, os usuários convidados não terão a experiência completa e personalizada da Pesquisa da Microsoft e talvez precisem aproveitar a caixa de pesquisa na página, em vez da caixa unificada da Pesquisa da Microsoft no header.</span><span class="sxs-lookup"><span data-stu-id="344a4-131">However, guest users will not get the full, personalized, Microsoft Search experience and may need to leverage the on-page search box instead of the unified Microsoft Search box in the header.</span></span>