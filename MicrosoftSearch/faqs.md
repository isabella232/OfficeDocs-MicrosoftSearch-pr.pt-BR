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
ms.openlocfilehash: 3ff2aabae4e09170b6b0380d520bfc620d5de5d8
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626251"
---
# <a name="frequently-asked-questions"></a>Perguntas frequentes

Esta é uma lista das perguntas mais frequentes.

> [!TIP]
> Não encontra resposta à sua pergunta aqui? Faça a sua pergunta nos comentários desse artigo.

## <a name="is-advanced-query-understanding-supported"></a>Há suporte para noções básicas sobre consultas avançadas?

Sim, a Pesquisa da Microsoft analisa a intenção de consulta de frases maiores. Esse recurso usa a IA para aprender frases supérfluas comuns que os usuários adicionam às consultas e que não afetam a intenção de pesquisa. Por exemplo, quando um usuário pesquisa "quero saber mais sobre como alterar minha senha", extraímos as palavras menos importantes da consulta e acionamos a consulta com base nas palavras-chave relevantes, como "alterar senha".
  
Este recurso não substituirá o conjunto de palavras-chave no centro de administração.
  
## <a name="can-you-search-for-files-on-premises"></a>É possível pesquisar arquivos no local?

Sim. Você pode pesquisar arquivos do SharePoint no local caso tenha uma implantação híbrida do SharePoint.
  
## <a name="how-do-i-make-bing-the-default-search-engine-for-people-in-my-org"></a>Como posso transformar o Bing no mecanismo de pesquisa padrão da minha organização?

Estas são as instruções para configurar o mecanismo de pesquisa padrão, a página inicial padrão e o navegador padrão para oferecer aos usuários a melhor experiência com a Pesquisa da Microsoft no Bing:

- [Definir o Microsoft Edge como navegador padrão](set-default-browser.md)
- [Definir o Bing como mecanismo de pesquisa padrão](set-default-search-engine.md)
- [Definir o Bing.com como página inicial da empresa](set-default-homepage.md)

  
## <a name="how-are-my-search-results-protected"></a>Como os resultados da pesquisa são protegidos?

É necessário a autenticação do Azure Active Directory (AAD) para acessar resultados do Trusted Cloud. Os usuários autenticados apenas visualizam o conteúdo ao qual eles têm acesso. As consultas de pesquisa são desidentificadas e os logs são armazenados separadamente do tráfego de pesquisa público do Bing. Esse nível de proteção não está disponível em nenhum outro local do setor.

## <a name="can-i-search-across-federated-organizations"></a>Posso pesquisar nas organizações federadas?

Não.

## <a name="where-can-i-get-info-about-office-365-and-microsoft-365-compliance-tiers-and-categories"></a>Onde posso obter informações sobre os níveis e categorias de conformidade do Office 365 e do Microsoft 365?

Os detalhes podem ser encontrados em [Estrutura de Conformidade para Padrões e Regulamentações do Setor](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf) (baixar o PDF).

## <a name="can-users-earn-microsoft-rewards-points-with-their-work-or-school-account"></a>Os usuários podem ganhar pontos do Microsoft Rewards com uma conta corporativa ou de estudante?

O Microsoft Search exige que os usuários corporativos entrem com uma conta corporativa ou de estudante. No entanto, os usuários não podem participar do Microsoft Rewards ou entrar nele com essas contas. No entanto, há uma situação em que um usuário corporativo pode ver os pontos acumulados. Isso pode acontecer quando um usuário do Microsoft Search tem uma conta Rewards que foi criada com uma <a href="https://www.microsoft.com/en-us/welcome?rtc=1">conta da Microsoft</a>. (O endereço de email associado a uma conta da Microsoft pode ser de Outlook.com, Hotmail.com, Gmail, Yahoo ou outros provedores). Se os usuários entrarem com a conta de trabalho e com a conta da Microsoft na mesma sessão do navegador, eles poderão acumular pontos para a sua conta Rewards. Os usuários podem parar de acumular pontos quando usarem o Microsoft Search limpando os cookies. 

