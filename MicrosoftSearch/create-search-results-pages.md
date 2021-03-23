---
title: Criar uma página de resultados de pesquisa personalizada no SharePoint Online
ms.author: jeffkizn
author: jeffkizn
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: Criar sua própria página de resultados de pesquisa para um site do SharePoint Online
ms.openlocfilehash: b5abb25f15795389dd8b6d5683ac336af7422e0a
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031634"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>Criar uma página de resultados de pesquisa personalizada no SharePoint Online

Uma maneira de personalizar a experiência de pesquisa no SharePoint é criar uma página de resultados de pesquisa personalizada para um site. Isso permite que você use uma página que você criou, em vez do padrão na página de resultados da Pesquisa da Microsoft. Isso oferece mais flexibilidade sobre a aparência da experiência de resultados da pesquisa para seus usuários.

>[!NOTE]
> Para fazer alterações na página padrão de resultados da Pesquisa da Microsoft que está disponível por padrão, consulte Personalizar a [página de resultados da pesquisa](customize-search-page.md).

Com uma página de resultados personalizada, você pode criar uma nova página que pode ser usada para controlar o layout e o design dos resultados da pesquisa para dar suporte às necessidades da sua organização. Você pode usar web parts internas, web parts de pesquisa de código aberto da comunidade de Padrões e Práticas do SharePoint, bem como qualquer Web Parts personalizadas que você possa ter desenvolvido usando a Estrutura do SharePoint.

## <a name="configure-a-results-page"></a>Configurar uma página de resultados

Para configurar uma página de resultados personalizada no SharePoint Online, siga as etapas abaixo:

1. Navegue até o site onde você gostaria de configurar uma página de resultados personalizada e acesse Configurações do Site > Configurações do Conjunto de Sites **> Configurações de Pesquisa**.

2. Em Configurações de Pesquisa, desempure a seleção de Usar as mesmas configurações de página de resultados que meu **pai,** escolha Enviar consultas para uma página de resultados personalizadas e forneça um valor para **a** URL da página **Resultados:**. Em seguida, salve suas alterações. A URL que você usa aqui deve ser para a página que você criou para usar como sua página de resultados personalizados.

>[!NOTE]
> A página de resultados personalizados precisa estar no mesmo domínio que seu site, mas não precisa estar no mesmo conjunto de sites.  

Como alternativa, você pode usar o [comando Set-PnPSearchSettings SharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) para definir o valor em vez de usar a página Configurações do Site.

Depois de definida, a página de resultados de pesquisa personalizada é exibida quando você pesquisa usando a caixa de Pesquisa da Microsoft que aparece na barra de navegação na parte superior da página e é usada quando você insiro a pesquisa nas páginas do site ou na home page do site. Ele não é usado quando você está pesquisando em uma lista, biblioteca ou na página de conteúdo do site. Você pode usar o link para expandir sua pesquisa a partir dos resultados da pesquisa em listas e bibliotecas para chegar à página de resultados personalizados.

## <a name="change-the-layout-of-your-custom-results-page"></a>Alterar o layout da página de resultados personalizados

Um layout de página chamado **HeaderlessSearchResults** pode ser usado para fazer com que a página de resultados da pesquisa apareça mais próxima da nossa experiência de resultados de pesquisa fora da caixa de correio. Esse novo layout só pode estar ativo para as páginas definidas como a página de resultados da pesquisa personalizada.

Para definir o layout da página, você pode usar o comando [Set-PnPClientSidePageSharePoint PnP PowerShell](/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) com -LayoutType HeaderlessSearchResults.

## <a name="use-sharepoint-framework-query-extensions"></a>Usar extensões de consulta da Estrutura do SharePoint

Páginas de resultados de pesquisa personalizadas também podem usar a Extensão de Consulta da Estrutura do [SharePoint](/sharepoint/dev/spfx/building-search-extensions) para modificar a consulta antes de ser enviada ao mecanismo de pesquisa.

## <a name="additional-resources"></a>Recursos adicionais

Para saber mais sobre a página de resultados personalizados, confira nossa sessão de Personalização e Desenvolvimento de Pesquisa do [Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions)

Para projetos de código aberto, começar com nossas APIs de Pesquisa da Microsoft e mais exemplos de personalização e extensibilidade, visite a Pesquisa da [Microsoft no GitHub](https://github.com/microsoft-search).