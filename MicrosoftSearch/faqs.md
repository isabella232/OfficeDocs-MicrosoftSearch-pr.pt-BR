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
# <a name="frequently-asked-questions"></a>Perguntas frequentes

Esta é uma lista das perguntas mais frequentes.

> [!TIP]
> Não encontra resposta à sua pergunta aqui? Faça a sua pergunta nos comentários desse artigo.

## <a name="is-advanced-query-understanding-supported"></a>Há suporte para noções básicas sobre consultas avançadas?

Sim, a Pesquisa da Microsoft analisará a intenção de consulta de frases maiores. Esse recurso usa a IA para aprender frases supérfluas comuns que os usuários adicionam às suas consultas que não impactam suas intenções de pesquisa. Por exemplo, quando um usuário procura saber mais sobre como alterar minha *senha,* extraimos as palavras menos importantes da consulta e disparamos com base nas relevantes, como alterar senha *.*
  
Esse recurso não substituirá palavras-chave definidas no centro [Microsoft 365 administrador.](https://admin.microsoft.com)
  
## <a name="can-you-search-for-files-on-premises"></a>É possível pesquisar arquivos no local?

Sim. Você pode pesquisar arquivos SharePoint [locais](http://sharepoint.com/) se tiver uma implantação híbrida de SharePoint.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Como posso transformar o Bing no mecanismo de pesquisa padrão da minha organização?

Aqui estão as instruções para definir o mecanismo de pesquisa padrão, a homepage padrão e o navegador padrão para dar aos usuários a melhor experiência com a Pesquisa da Microsoft [em](https://Bing.com)Bing :

- [Definir Microsoft Edge como seu navegador padrão](/deployedge/edge-default-browser)
- [Definir o Bing como mecanismo de pesquisa padrão](set-default-search-engine.md)
- [Definir o Bing.com como página inicial da empresa](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>Como os resultados da pesquisa são protegidos?

Exigimos [Azure Active Directory](/azure/active-directory/) autenticação para acessar resultados da Nuvem Confiável. Os usuários autenticados apenas visualizam o conteúdo ao qual eles têm acesso. As consultas de pesquisa são des identificadas [](https://Bing.com) e os logs são separados do tráfego de pesquisa Bing público quando você usa a Pesquisa da Microsoft no Bing.

## <a name="can-i-search-across-federated-organizations"></a>Posso pesquisar nas organizações federadas?

Não.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>Onde posso obter informações sobre Office 365 segurança, conformidade e privacidade?

Os detalhes podem ser encontrados nas páginas [da Central de Confiações para Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>Os usuários convidados podem aproveitar a Pesquisa da Microsoft na minha organização?

Microsoft 365 permite a colaboração com pessoas de fora da sua organização por meio [do acesso de convidados.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Esses usuários poderão executar operações de pesquisa em documentos, sites, grupos, listas e bibliotecas. No entanto, os usuários convidados não terão a experiência completa e personalizada da Pesquisa da Microsoft e talvez precisem aproveitar a caixa de pesquisa na página, em vez da caixa unificada da Pesquisa da Microsoft no header.