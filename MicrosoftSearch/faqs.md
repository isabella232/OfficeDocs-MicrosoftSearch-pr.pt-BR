---
title: Perguntas frequentes
ms.author: anfowler
author: adefowler
manager: shohara
ms.date: 10/19/2018
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: cd3ee09d-58ab-4b8a-8822-fa11a1399672
ROBOTS: NoIndex
description: Obtenha respostas para perguntas frequentes comuns sobre o Enterprise Search e a Pesquisa da Microsoft
ms.openlocfilehash: 3b30980c76915405767381fb3b6397468bdd1b68
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639493"
---
# <a name="frequently-asked-questions"></a><span data-ttu-id="ea414-103">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="ea414-103">Frequently asked questions</span></span>

<span data-ttu-id="ea414-104">Esta é uma lista das perguntas mais frequentes.</span><span class="sxs-lookup"><span data-stu-id="ea414-104">Here's a list of the most common questions.</span></span>

> [!TIP]
> <span data-ttu-id="ea414-105">Não encontra resposta à sua pergunta aqui?</span><span class="sxs-lookup"><span data-stu-id="ea414-105">Don't see your question answered here?</span></span> <span data-ttu-id="ea414-106">Faça a sua pergunta nos comentários desse artigo.</span><span class="sxs-lookup"><span data-stu-id="ea414-106">Ask your question in this article's feedback.</span></span>

## <a name="is-advanced-query-understanding-supported"></a><span data-ttu-id="ea414-107">Há suporte para noções básicas sobre consultas avançadas?</span><span class="sxs-lookup"><span data-stu-id="ea414-107">Is advanced query understanding supported?</span></span>

<span data-ttu-id="ea414-p102">Sim, a Pesquisa da Microsoft analisa a intenção de consulta de frases maiores. Esse recurso usa a IA para aprender frases supérfluas comuns que os usuários adicionam às consultas e que não afetam a intenção de pesquisa. Por exemplo, quando um usuário pesquisa "quero saber mais sobre como alterar minha senha", extraímos as palavras menos importantes da consulta e acionamos a consulta com base nas palavras-chave relevantes, como "alterar senha".</span><span class="sxs-lookup"><span data-stu-id="ea414-p102">Yes, Microsoft Search parses query intent from larger phrases. This feature uses AI to learn common superfluous phrases users add to their queries that don't impact their search intent. For example, when a user searches for 'tell me more about how to change my password please' we extract the less important words from the query and trigger based on the relevant ones like 'change password.'</span></span>
  
<span data-ttu-id="ea414-111">Este recurso não substituirá o conjunto de palavras-chave no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="ea414-111">This feature will not override keywords set in the Admin portal.</span></span>
  
## <a name="can-you-search-for-files-on-premises"></a><span data-ttu-id="ea414-112">É possível pesquisar arquivos no local?</span><span class="sxs-lookup"><span data-stu-id="ea414-112">Can you search for files on-premises?</span></span>

<span data-ttu-id="ea414-113">Sim.</span><span class="sxs-lookup"><span data-stu-id="ea414-113">Yes.</span></span> <span data-ttu-id="ea414-114">Você pode pesquisar arquivos do SharePoint no local caso tenha uma implantação híbrida do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ea414-114">You can search on-premises SharePoint files if you have a hybrid deployment of SharePoint.</span></span>
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a><span data-ttu-id="ea414-115">Como posso transformar o Bing no mecanismo de pesquisa padrão da minha organização?</span><span class="sxs-lookup"><span data-stu-id="ea414-115">How do I make Bing the default search engine for people in my org?</span></span>

<span data-ttu-id="ea414-116">Estas são as instruções para configurar o mecanismo de pesquisa padrão, a página inicial padrão e o navegador padrão para oferecer aos usuários a melhor experiência com a Pesquisa da Microsoft no Bing:</span><span class="sxs-lookup"><span data-stu-id="ea414-116">Here's the instructions for setting the default search engine, default homepage, and default browser to give your users the best experience with Microsoft Search in Bing:</span></span>

- [<span data-ttu-id="ea414-117">Definir o Microsoft Edge como navegador padrão</span><span class="sxs-lookup"><span data-stu-id="ea414-117">Set Edge as your default browser</span></span>](set-default-browser.md)
- [<span data-ttu-id="ea414-118">Definir o Bing como mecanismo de pesquisa padrão</span><span class="sxs-lookup"><span data-stu-id="ea414-118">Make Bing your default search engine</span></span>](set-default-search-engine.md)
- [<span data-ttu-id="ea414-119">Definir o Bing.com como página inicial da empresa</span><span class="sxs-lookup"><span data-stu-id="ea414-119">Set Bing.com as your enterprise homepage</span></span>](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a><span data-ttu-id="ea414-120">Como os resultados da pesquisa são protegidos?</span><span class="sxs-lookup"><span data-stu-id="ea414-120">How are my search results protected?</span></span>

<span data-ttu-id="ea414-121">É necessário a autenticação do Azure Active Directory (AAD) para acessar resultados do Trusted Cloud.</span><span class="sxs-lookup"><span data-stu-id="ea414-121">We require Azure Active Directory (AAD) authentication to access results from the Trusted Cloud.</span></span> <span data-ttu-id="ea414-122">Os usuários autenticados apenas visualizam o conteúdo ao qual eles têm acesso.</span><span class="sxs-lookup"><span data-stu-id="ea414-122">Authenticated users only see content they have access to.</span></span> <span data-ttu-id="ea414-123">As consultas de pesquisa são desidentificadas e os logs são armazenados separadamente do tráfego de pesquisa público do Bing.</span><span class="sxs-lookup"><span data-stu-id="ea414-123">Search queries are de-identified and logs are separated from public Bing search traffic.</span></span> <span data-ttu-id="ea414-124">Esse nível de proteção não está disponível em nenhum outro local do setor.</span><span class="sxs-lookup"><span data-stu-id="ea414-124">This level of protection is unavailable anywhere else in the industry.</span></span>

## <a name="can-i-search-across-federated-organizations"></a><span data-ttu-id="ea414-125">Posso pesquisar nas organizações federadas?</span><span class="sxs-lookup"><span data-stu-id="ea414-125">Can I search across federated organizations?</span></span>

<span data-ttu-id="ea414-126">Não.</span><span class="sxs-lookup"><span data-stu-id="ea414-126">No.</span></span>

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a><span data-ttu-id="ea414-127">Onde posso obter informações sobre os níveis e categorias de conformidade do Office 365 e do Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="ea414-127">Where can I get info about Office 365 and Microsoft 365 compliance tiers and categories?</span></span>

<span data-ttu-id="ea414-128">Os detalhes podem ser encontrados em [Estrutura de Conformidade para Padrões e Regulamentações do Setor](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (baixar o PDF).</span><span class="sxs-lookup"><span data-stu-id="ea414-128">Details can be found in the [Compliance Framework for Industry Standards and Regulations](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (PDF download).</span></span>