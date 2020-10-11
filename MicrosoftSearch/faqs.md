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
ms.openlocfilehash: 5a134116c98b4feea0c04909349ce4b972c59ffe
ms.sourcegitcommit: 0b8c3c57384cecaa93c5cbaf3b3b30f8e20d1a69
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408434"
---
<!-- markdownlint-disable no-trailing-punctuation -->
# <a name="frequently-asked-questions"></a>Perguntas frequentes

Esta é uma lista das perguntas mais frequentes.

> [!TIP]
> Não encontra resposta à sua pergunta aqui? Faça a sua pergunta nos comentários desse artigo.

## <a name="is-advanced-query-understanding-supported"></a>Há suporte para noções básicas sobre consultas avançadas?

Sim, o Microsoft Search analisa a intenção de consulta de frases maiores. Este recurso usa o AI para aprender frases supérfluas comuns que os usuários adicionam às suas consultas que não impactam a sua intenção de pesquisa. Por exemplo, quando um usuário pesquisa para *saber mais sobre como alterar minha senha*, extraímos as palavras menos importantes da consulta e do gatilho com base nos relevantes como *alterar senha*.
  
Este recurso não substituirá as palavras-chave definidas no [centro de administração do Microsoft 365](https://admin.microsoft.com).
  
## <a name="can-you-search-for-files-on-premises"></a>É possível pesquisar arquivos no local?

Sim. Você pode pesquisar arquivos [do SharePoint](http://sharepoint.com/) no local se tiver uma implantação híbrida do SharePoint.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Como posso transformar o Bing no mecanismo de pesquisa padrão da minha organização?

Veja a seguir as instruções para configurar o mecanismo de pesquisa padrão, a Home Page padrão e o navegador padrão para dar aos seus usuários a melhor experiência com o Microsoft Search no [Bing](https://Bing.com):

- [Definir o Microsoft Edge como seu navegador padrão](set-default-browser.md)
- [Definir o Bing como mecanismo de pesquisa padrão](set-default-search-engine.md)
- [Definir o Bing.com como página inicial da empresa](set-default-homepage.md)

## <a name="how-are-my-search-results-protected"></a>Como os resultados da pesquisa são protegidos?

Requer a autenticação [do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) para acessar os resultados da nuvem confiável. Os usuários autenticados apenas visualizam o conteúdo ao qual eles têm acesso. As consultas de pesquisa são desidentificadas e os logs são separados do tráfego de pesquisa do [Bing](https://Bing.com) público. Esse nível de proteção não está disponível em nenhum outro local do setor.

## <a name="can-i-search-across-federated-organizations"></a>Posso pesquisar nas organizações federadas?

Não.

## <a name="where-can-i-get-info-about-office-365-security-compliance-and-privacy"></a>Onde posso obter informações sobre segurança, conformidade e privacidade do Office 365?

Os detalhes podem ser encontrados nas [páginas da central de confiabilidade do Office 365](https://www.microsoft.com/TrustCenter/CloudServices/office365/default.aspx).

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a>Os usuários podem ganhar pontos do Microsoft Rewards com uma conta corporativa ou de estudante?

O Microsoft Search exige que os usuários corporativos entrem com uma conta corporativa ou de estudante. No entanto, os usuários não podem participar do Microsoft Rewards ou entrar nele com essas contas. No entanto, há uma situação em que um usuário corporativo pode ver os pontos acumulados. Isso pode acontecer quando um usuário do Microsoft Search tem uma conta Rewards que foi criada com uma [conta da Microsoft](https://www.microsoft.com/welcome?rtc=1). (O endereço de email associado a uma conta da Microsoft pode ser de Outlook.com, Hotmail.com, Gmail, Yahoo ou outros provedores). Se os usuários entrarem com a conta de trabalho e com a conta da Microsoft na mesma sessão do navegador, eles poderão acumular pontos para a sua conta Rewards. Os usuários podem parar de acumular pontos quando usarem o Microsoft Search limpando os cookies.

## <a name="can-guest-users-leverage-microsoft-search-in-my-organization"></a>Os usuários convidados podem aproveitar a pesquisa da Microsoft em minha organização?

A Microsoft 365 permite colaboração avançada com pessoas de fora da sua organização por meio de [acesso de convidados.](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization) Esses usuários poderão executar operações de pesquisa em documentos, sites, grupos, listas e bibliotecas. No entanto, os usuários convidados não terão a experiência completa, personalizada e de pesquisa da Microsoft e talvez precisem aproveitar a caixa de pesquisa na página, em vez da caixa de pesquisa da Microsoft unificada no cabeçalho.
