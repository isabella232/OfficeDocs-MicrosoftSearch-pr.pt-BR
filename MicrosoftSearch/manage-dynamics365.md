---
title: Pesquisa de federação do Dynamics 365 (visualização)
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: Gerenciar como o conteúdo do Dynamics 365 aparece nos resultados da pesquisa
ms.openlocfilehash: d2874febe39abf68653fa82d6a50121ebd1a357b
ms.sourcegitcommit: fbe565b1a8994425b4f7ff0114a69044659e3892
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2021
ms.locfileid: "58380029"
---
# <a name="dynamics-365-federation-search-preview"></a>Pesquisa de federação do Dynamics 365 (visualização)

## <a name="microsoft-search-federation-and-connectors"></a>Pesquisa da Microsoft Federação e conectores

Para ajudar a Pesquisa da Microsoft mais útil, apresentamos Pesquisa da Microsoft Federação. Com a pesquisa federada, as organizações podem tornar os dados nesses cenários acessíveis em Pesquisa da Microsoft:

* Dados em sistemas que estão sujeitos a requisitos estritos de conformidade
* Dados que não podem deixar limites do sistema
* Dados confidenciais armazenados no local que sua organização não deseja indexar na nuvem

Os dados acessados por meio de uma conexão de pesquisa federada não são indexados Pesquisa da Microsoft. Além disso, usando conectores integrados da Microsoft, é fácil configurar conexões de pesquisa federadas. Nosso conector do Dynamics 365 está atualmente em visualização. Se você estiver interessado em ingressar na visualização, nos avise [em](https://aka.ms/D365FederationSearchPreview)aka.ms/D365FederationSearchPreview . Para ver o período de tempo de lançamento, consulte [o Pesquisa da Microsoft Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=Microsoft%20Search).

## <a name="dynamics-365-federation-connector"></a>Conector de federação do Dynamics 365

O Microsoft Dynamics 365 é uma linha de aplicativos corporativos inteligentes projetados para planejamento de recursos corporativos e gerenciamento de relacionamento com o cliente. Com a federação do Dynamics 365, o Pesquisa da Microsoft oferece uma experiência de pesquisa perfeita, permitindo que os usuários encontrem facilmente os dados de clientes e negócios mais relevantes armazenados no Dynamics 365. O conector de federação do Dynamics 365 oferece alguns benefícios importantes:

* **Fácil de administrar:** Processo simplificado para configurar e manter a conexão de pesquisa com uma instância do Dynamics 365.
* **Fácil de usar:** Os usuários podem encontrar facilmente e rapidamente informações importantes armazenadas no Dynamics 365, incluindo contas, contatos, oportunidades abertas e muito mais.
* **Conteúdo mais rico:** Para tornar os resultados de pesquisa do Dynamics 365 mais úteis, eles incluem informações importantes, como contatos e detalhes da conta.
* **Proteção de dados integrado:** Os resultados do Dynamics 365 só serão exibidos para usuários que tenham acesso à instância conectada.
* **Experiência de pesquisa unificada:** Para manter uma experiência coesiva, os resultados do Dynamics 365 são consistentes em todos os pontos de entrada da pesquisa. Onde quer que você pesquise, você obterá os mesmos resultados com a mesma aparência.

## <a name="what-users-experience"></a>O que os usuários experimentam

As respostas do Dynamics 365 aparecem nos resultados da pesquisa em todas as Pesquisa da Microsoft, incluindo SharePoint Online, Bing e Office.

:::image type="content" alt-text="Captura de tela das respostas do Dynamics 365 em SharePoint, Bing e Office" source="media/dynamics365/dynamics365-answer.png" lightbox="media/dynamics365/dynamics365-answer.png":::

Na resposta, é fácil ver mais resultados de pesquisa do Dynamics 365 usando o link mais resultados do **Dynamics 365.** Ele leva os usuários para uma página de resultados do Dynamics 365 dedicada com mais resultados relevantes para sua consulta.

:::image type="content" alt-text="Captura de tela do Dynamics 365 vertical e resultados em SharePoint, Bing e Office" source="media/dynamics365/dynamics365-vertical.png" lightbox="media/dynamics365/dynamics365-vertical.png":::

Clicar ou tocar em qualquer resultado abre o Dynamics 365 e mostra as informações detalhadas.

:::image type="content" alt-text="Captura de tela da página de detalhes no Dynamics 365" source="media/dynamics365/dynamics365-detail-page.png" lightbox="media/dynamics365/dynamics365-detail-page.png":::

Não importa onde seus usuários iniciem a pesquisa, sua experiência será consistente e permitirá que eles encontrem rapidamente os resultados mais relevantes do Dynamics 365. Confira nosso vídeo do Microsoft Build 2021 para uma demonstração.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4P83t]

## <a name="supported-query-patterns"></a>Padrões de consulta com suporte

Tanto a linguagem natural quanto as consultas de nome do produto são suportadas ao usar Pesquisa da Microsoft para encontrar resultados do Dynamics 365. Além disso, as consultas do Dynamics 365 não são sensíveis a casos. Use padrões de idioma natural para localizar contatos, conta e oportunidades -- pelo nome do cliente ou local -- e outras consultas usadas com frequência. Veja alguns exemplos:

* Who é o contato da Contoso
* Oportunidades abertas para Contoso
* Quais são as oportunidades abertas em Seattle
* Quais são as contas em Seattle
* Quais são os contatos em Seattle
* Quais são os meus leads que fecham este mês
* Chamada telefônica de alta prioridade
* Contatar emails ausentes

Os padrões de nome do produto suportam um intervalo de aplicativos do Dynamics 365 e disparam os resultados do Dynamics 365, independentemente de onde aparecem em uma consulta:

* D365
* Dynamics 365
* Dynamics365
* Dynamics CRM
* Dynamics Sales
* Dynamics Customer Service
* Serviço Dynamics
* Dynamics Field Service

## <a name="configure-the-dynamics-365-connector"></a>Configurar o conector do Dynamics 365

Com essa configuração simples, você pode habilitar a experiência de pesquisa de federação do Dynamics 365 para pessoas em sua organização.

1. No [Centro de administração do Microsoft 365,](https://admin.microsoft.com)vá para [Fontes de dados](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors).

2. Na seção Aplicativos e serviços da Microsoft, em Microsoft Dynamics 365, selecione **Gerenciar** para abrir o painel do Microsoft Dynamics 365.

3. Habilita o conector para sua organização.

4. Na lista **Pontos de** Extremidade, selecione seu ambiente do Dynamics 365.

5. Na **ID da Conexão,** insira uma ID exclusiva para essa conexão.

6. Revise e selecione a caixa de seleção consentimento.

7. Selecione **Salvar** para concluir a configuração da conexão.

:::image type="content" alt-text="Captura de tela do painel de configuração do Dynamics 365 no Centro de administração do Microsoft 365" source="media/dynamics365/dynamic365-connection-setup.png" lightbox="media/dynamics365/dynamic365-connection-setup.png":::

Quando a instalação for concluída, as respostas e verticais do Dynamics 365 aparecerão somente para usuários com uma licença válida do Dynamics 365 e acesso ao ambiente conectado do Dynamics 365. A qualquer momento, você pode retornar a essas configurações e alterar o ambiente do ponto de extremidade de conexão ou desativar a conexão.
