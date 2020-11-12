---
title: Gerenciando comentários do usuário
ms.author: lebhansa
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Analisar e agir sobre o feedback do usuário no Microsoft Search
ms.openlocfilehash: 332410cd29a7256cccd651c3a668fdf3eb473ba4
ms.sourcegitcommit: 102371815e739da33d1711197cdc743ae8124baa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2020
ms.locfileid: "48996788"
---
# <a name="managing-user-feedback"></a>Gerenciando comentários do usuário

A criação de uma ótima experiência de pesquisa para seus usuários é uma parceria entre a Microsoft e o administrador de pesquisa. Comentários de seus usuários nos permitem avaliar continuamente o produto e ajustá-lo para obter a melhor experiência. Alguns comentários, no entanto, são melhor tratados por você.

Agora, estamos oferecendo ferramentas que lhe permitirão examinar e gerenciar os comentários que seus usuários estão fornecendo na experiência de pesquisa.

## <a name="how-users-submit-feedback"></a>Como os usuários enviam comentários

À medida que as pessoas da sua organização usam o Microsoft Search, elas podem ter comentários sobre a experiência. Quando eles clicam em um link de comentários na página de resultados, eles podem categorizar seus comentários e incluir comentários adicionais.

![Formulário de comentários globais](media/feedback/feedback-global-dialog.png)

Os usuários também têm a opção de enviar suas consultas e outras informações de diagnóstico, juntamente com a categoria e os comentários, para a Microsoft. [Saiba mais](https://privacy.microsoft.com/en-US/privacystatement) sobre privacidade e como protegemos esses dados. Os dados de diagnóstico contêm as informações mais críticas que a Microsoft precisa para usar o item de comentários para a melhoria do produto.

A maioria dos envios de comentários é exibida na seção de [comentários](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/feedback) do centro de administração de pesquisa da Microsoft. O feedback enviado com a opção **desejo sugerir uma categoria de link interno** aparece como um indicador sugerido na seção [bookmarks](https://admin-ignite.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) e pode ser visto por filtragem em status **sugerido** .

## <a name="review-feedback"></a>Revisar comentários

Na página de [comentários](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/feedback) , você pode revisar e exportar comentários que as pessoas em sua organização enviaram nos últimos 30 dias. Quando um usuário envia comentários, ele aparecerá na lista em 20 minutos. Você pode usar o botão atualizar para garantir que você está examinando os dados mais atuais

Usando um filtro, você pode ver comentários para tipos de resposta específicos. Você também pode filtrar por fonte e intervalo de datas.

Você pode usar a caixa de pesquisa acima da lista de comentários para pesquisar comentários sobre uma consulta específica.

Na lista de comentários, a coluna textual indica que o feedback do usuário também inclui um comentário ou uma sugestão. Para lê-lo, clique na consulta para abrir o painel de **detalhes** .

## <a name="update-feedback-state"></a>Atualizar estado de comentários

Como o feedback aparece, ele estará em um *novo* estado e permanecerá lá até que você o altere para *resolvido* ou *duplicado*.

Para alterar este Estado:

1. Ao lado da consulta, selecione **mais opções** (três pontos verticais).
1. No menu, selecione **Marcar como resolvido** ou **Marcar como duplicado.**
1. A lista será atualizada e mostrará o estado atualizado.

Você também pode atualizar o estado de vários itens, basta selecioná-los e, em seguida, selecione mais opções em qualquer um desses itens.

## <a name="export-feedback"></a>Exportar comentários

Se você quiser compartilhar comentários de pesquisa com outras pessoas ou mantê-los por mais de 30 dias, clique em **Exportar.** Um arquivo. csv denominado comentários com a data, como "Feedbacks_10_31_2020.csv", será baixado automaticamente.

## <a name="send-user-feedback-to-microsoft"></a>Enviar comentários do usuário para a Microsoft

Por padrão, todos os comentários do usuário são enviados para a Microsoft e para sua adição. Para interromper o envio de comentários para a Microsoft, clique em **gerenciar configurações** e desmarque a caixa de seleção **enviar comentários do usuário para a Microsoft automaticamente** . Pode levar até 24 horas para que essa alteração entre em vigor.

Se você optou por não enviar comentários à Microsoft automaticamente, ainda poderá enviar itens individuais de comentários para a Microsoft.

1. Selecione os comentários que você deseja compartilhar.
1. Na barra de ações, selecione mais (três pontos) e clique em **enviar comentários para a Microsoft**.

1. O status na coluna enviado para a Microsoft será alterado para pendente. Quando o comentário é enviado, ele será alterado para Sim.

Se você compartilhar comentários automaticamente ou manualmente, ele nunca incluirá consultas e outras informações de diagnóstico para usuários que optaram por não incluir essas informações.

## <a name="suggestions-on-how-to-use-feedback"></a>Sugestões sobre como usar comentários

Como administrador de pesquisa, você deve entender a principal pessoa em sua organização e os tipos de conteúdo com os quais as pessoas geralmente interagem e pesquisa. Com essa compreensão, você pode usar comentários para fazer melhorias direcionadas para a experiência de pesquisa dos seus usuários.

1. "Não encontrei o que eu estava procurando" e comentários semelhantes podem ser usados para identificar o conteúdo que os usuários desejam, mas não estão incluídos no índice de pesquisa. A determinação desse artigo muitas vezes faz a investigação e a inferência com base na compreensão de seus usuários. Uma vez encontrado, decida quais métodos de incluindo esse conteúdo seriam os mais apropriados:
    1. Os indicadores são úteis para fontes de conteúdo com uma página de aterrissagem de alta qualidade e uma variedade limitada de termos de pesquisa, de forma que a comunidade de usuários obtenha um resultado de alta qualidade do indicador e possa localizar de forma eficiente o que estão procurando.
    1. P&A é útil para respostas individuais que são muito frequentes, mas não mudam.
    1. Os conectores são úteis para fontes de conteúdo com uma ampla variedade de conteúdo e grande variedade de termos de pesquisa.
1. "Os resultados levaram muito tempo para carregar" & "Eu encontrei um problema" pode ser indicadores de um problema mais amplo. Procurar comentários diariamente pode ajudar e, se forem exibidos vários casos, você poderá verificar a experiência de pesquisa para si mesmo e abrir um caso de suporte com a Microsoft, se necessário. Esse tipo de feedback também é importante para a Microsoft e é um excelente motivo para o fluxo de todos os comentários para nós.
1. "Desejo sugerir um link interno" pode ser avaliado para ser adicionado como indicador ou conteúdo conectado. Seu primeiro pensamento deve ser um indicador; Se o indicador estiver com alto uso, você pode considerar a possibilidade de colocar o conteúdo por meio de um conector para habilitar uma experiência de pesquisa ainda mais rica.
