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