---
title: Perguntas frequentes
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: reference
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Obtenha respostas para perguntas frequentes comuns sobre o Enterprise Search e a Pesquisa da Microsoft
ms.openlocfilehash: 8b4de717ab63af8842dc86135748e551ff386a2a
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58702152"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>Perguntas frequentes

Esta é uma lista das perguntas mais frequentes.

> [!TIP]
> Não encontra resposta à sua pergunta aqui? Faça a sua pergunta nos comentários desse artigo.

## <a name="is-advanced-query-understanding-supported"></a>Há suporte para noções básicas sobre consultas avançadas?

Sim, Pesquisa da Microsoft analisar a intenção de consulta de frases maiores. Esse recurso usa a IA para aprender frases supérfluas comuns que os usuários adicionam às consultas que não afetam suas intenções de pesquisa. Por exemplo, quando um usuário procura saber mais sobre como alterar minha *senha,* extraimos as palavras menos importantes da consulta e disparamos com base nas relevantes, como alterar senha *.*
  
Esse recurso não substituirá palavras-chave definidas no [Centro de administração do Microsoft 365](https://admin.microsoft.com).
  
## <a name="can-you-search-for-files-on-premises"></a>É possível pesquisar arquivos no local?

Sim. Você pode pesquisar arquivos SharePoint [locais](http://sharepoint.com/) se tiver uma implantação híbrida de SharePoint.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Como posso transformar o Bing no mecanismo de pesquisa padrão da minha organização?

Aqui estão as instruções para definir o mecanismo de pesquisa padrão, a homepage padrão e o navegador padrão para dar aos usuários a melhor experiência com Pesquisa da Microsoft em [Bing](https://Bing.com):

- [Definir Microsoft Edge como seu navegador padrão](/deployedge/edge-default-browser)
- [Definir o Bing como mecanismo de pesquisa padrão](set-default-search-engine.md)
- [Definir o Bing.com como página inicial da empresa](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>Como os resultados da pesquisa são protegidos?

Exigimos [Azure Active Directory](/azure/active-directory/) autenticação para acessar resultados da Nuvem Confiável. Os usuários autenticados apenas visualizam o conteúdo ao qual eles têm acesso. Ao usar Pesquisa da Microsoft no Bing, as consultas de pesquisa são des identificadas e os logs são separados do tráfego de pesquisa [Bing](https://Bing.com) público.

## <a name="can-i-search-across-federated-organizations"></a>Posso pesquisar nas organizações federadas?

Não.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>Onde posso obter informações sobre Office 365 segurança, conformidade e privacidade?

Os detalhes podem ser encontrados nas páginas [da Central de Confiações para Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).

## <a name="can-guest-users-access-microsoft-search-in-my-organization"></a>Os usuários convidados podem acessar Pesquisa da Microsoft em minha organização?

Microsoft 365 permite a colaboração com pessoas de fora da sua organização por meio [do acesso de convidados.](/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Esses usuários podem pesquisar documentos, sites, grupos, listas e bibliotecas. No entanto, os usuários convidados não receberão a experiência completa e personalizada Pesquisa da Microsoft e talvez precisem usar a caixa de pesquisa na página em vez da caixa Pesquisa da Microsoft unificada no header.

## <a name="how-do-i-turn-microsoft-search-in-bing-on-or-off"></a>Como ativar ou desativar Pesquisa da Microsoft em Bing ou desativar?

Para a maioria das organizações, incluindo a empresa e a educação, Pesquisa da Microsoft no Bing por padrão. Para ativar Pesquisa da Microsoft em Bing, vá para a [](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/configurations) página Configurações no Centro de administração do Microsoft 365. Em Pesquisa da Microsoft em Bing configurações, escolha  Alterar configurações e a opção Permitir que sua organização use Pesquisa da Microsoft **em** Bing . Leva até 24 horas para que essa alteração entre em vigor.

Se essa configuração estiver desligada, os usuários não obterão resultados internos quando pesquisam em Bing, Windows Pesquisa ou em Microsoft Edge. A Pesquisa da Microsoft no Bing não para ou impede que o conteúdo interno seja adicionado ao índice de pesquisa. Ele desabilita apenas Bing pontos de entrada para Pesquisa da Microsoft. Para encontrar respostas e resultados internos, os usuários precisarão usar outros pontos de entrada, por exemplo, SharePoint Online ou um Office 365 aplicativo.
