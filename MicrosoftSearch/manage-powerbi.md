---
title: Gerenciar Power BI respostas
ms.author: dawholl
author: dawholl
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Gerenciar como Power BI relatórios e dados aparecem nos resultados da pesquisa
ms.openlocfilehash: 4b2251bdb8039c25fb1ec5290f3374a9f4eb3fd1
ms.sourcegitcommit: 4b72a31910753d46373a829a64ffec77fe6bc855
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52547696"
---
# <a name="manage-power-bi-answers"></a>Gerenciar Power BI respostas

Para facilitar que os usuários encontrem os dados e análises necessários para tomar decisões informadas, a Pesquisa da Microsoft adicionou suporte para painéis Power BI e relatórios. Aqui estão alguns dos benefícios da pesquisa Power BI:

* **Fácil de usar:** Essa experiência de pesquisa pronta ajuda os usuários a encontrar facilmente e rapidamente Power BI painéis e relatórios em toda a sua organização.
* **Conteúdo mais rico:** Para tornar Power BI resultados de pesquisa mais úteis, eles incluem informações importantes, como o tipo de conteúdo — painel ou relatório — e a equipe ou pessoa proprietária.
* **Proteção de dados interna: Power BI** resultados serão exibidos apenas para usuários que tenham acesso ao painel ou relatório.
* **Experiência de pesquisa unificada:** Para manter uma experiência coesiva, Power BI resultados são consistentes em todos os pontos de entrada da pesquisa. Onde quer que você pesquise, você obterá os mesmos resultados com a mesma aparência.

## <a name="what-users-experience"></a>O que os usuários experimentam

Os usuários da Pesquisa da Microsoft podem encontrar Power BI resultados pesquisando Windows caixa de pesquisa, SharePoint, Office 365 e Bing. Os usuários podem pesquisar relatórios e painéis com consultas como estas:

* Power BI sobre`<topic>`
* Power BI para`<topic>`
* `<topic>`Power BI painel ou painel Power BI painel`<topic>`
* `<topic>`Power BI relatório ou relatório Power BI relatório`<topic>`
* `<topic>`Power BI métricas ou Power BI métricas`<topic>`
* `<topic>`Power BI scorecard ou Power BI scorecard`<topic>`

Substitua nos exemplos acima pelas informações que você está procurando, como `<topic>` vendas, uso, capacidade, 2021, Q1 e muito mais, para ver resultados relevantes do Power BI.

:::image type="content" source="media/powerbi-answers/powerbi-serp.png" alt-text="Captura de tela de um SERP com Power BI respostas e verticais" border="true":::

## <a name="turn-power-bi-search-on-or-off"></a>Ativar Power BI pesquisa ou desativar

Power BI resultados estão habilitados para sua organização por padrão. Seu Power BI administrador pode desabilitá-los a qualquer momento. No portal Power BI Administrador, acesse Configurações de locatário e desabilite a configuração **Usar pesquisa global para Power BI.** Para saber mais, consulte [Administering Power BI in the admin portal](/power-bi/admin/service-admin-portal#use-global-search-for-power-bi-preview).

:::image type="content" source="media/powerbi-answers/powerbi-admin.png" alt-text="Captura de tela da configuração para ativar ou desativar Power BI respostas" border="true":::

> [!NOTE]
> Ao usar a Pesquisa da Microsoft, sua consulta de pesquisa e os resultados retornados do Power BI podem ser processados em uma região ou geografia diferente de onde seus dados de locatário Power BI estão localizados.

## <a name="frequently-asked-questions"></a>Perguntas Frequentes

**P: a Power BI está habilitada por padrão?**

**R:** Sim, ele é um dos mais bem Power BI pesquisa está habilitada por padrão para a Pesquisa da Microsoft. Não há nenhuma configuração de primeira hora necessária pelo administrador do locatário para esse recurso.

**P: A Power BI pesquisa pode ser habilitada ou desabilitada para grupos ou usuários específicos?**

**R:** Atualmente, ele só pode ser habilitado ou desabilitado para toda a organização.

**P: Se Power BI pesquisa estiver desabilitada, Power BI página de resultados da pesquisa oculta?**

**R:** Não. A Power BI de resultados da pesquisa aparecerá com uma mensagem informando aos usuários que ela não está disponível no momento para sua organização.

**P: Eu vou ver a página Power BI resultado da pesquisa se eu não tiver uma Power BI de pesquisa?**

**R:** Não. Se um usuário de pesquisa não tiver uma licença de Power BI, a página Power BI resultado da pesquisa não aparecerá nos resultados da Pesquisa da Microsoft.

**P: Vou ver Power BI resultados de pesquisa que não consigo acessar?**

**R:** Não. A Pesquisa da Microsoft retornará apenas Power BI resultados aos que você tem acesso.

**P: Posso personalizar os Power BI de pesquisa (por exemplo, o tipo de relatório ou o proprietário do relatório)?**

**R:** Atualmente, não há suporte para personalizar os campos incluídos nos Power BI de pesquisa.