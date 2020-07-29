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
ms.openlocfilehash: 9b168dccaa6126148c877b5841b91c63f7bdc2ac
ms.sourcegitcommit: 5fb46a04e86fb49477f8ce7ab3caa1b503215b8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "46503232"
---
# <a name="create-a-custom-search-results-page-in-sharepoint-online"></a>Criar uma página de resultados de pesquisa personalizada no SharePoint Online

Uma maneira de personalizar a experiência de pesquisa no SharePoint é criar uma página de resultados de pesquisa personalizada para um site. Isso permite que você use uma página que você criou, em vez do padrão na página de resultados da pesquisa da Microsoft. Isso lhe dá mais flexibilidade sobre como a experiência de resultados de pesquisa procura por seus usuários.

>[!NOTE]
> Para fazer alterações na página de resultados de pesquisa padrão da Microsoft que está disponível por padrão, confira [Personalizar a página de resultados de pesquisa](customize-search-page.md).

Com uma página de resultados personalizada, você pode criar uma nova página que pode ser usada para controlar o layout e o design dos resultados da pesquisa para dar suporte às necessidades da sua organização. Você pode usar Web Parts internas de pesquisa de código-fonte da comunidade de padrões e práticas do SharePoint, bem como qualquer Web Part personalizada que possa ter desenvolvido usando a estrutura do SharePoint.

## <a name="configure-a-results-page"></a>Configurar uma página de resultados

Para configurar uma página de resultados personalizada no SharePoint Online, siga as etapas abaixo:

1. Navegue até o site em que você gostaria de configurar uma página de resultados personalizados e vá para **configurações do site > definições de conjunto de sites > configurações de pesquisa**.

2. Em configurações de pesquisa, desmarcar seleção de **usar as mesmas configurações de página de resultados como meu pai**, escolha **enviar consultas para uma página de resultados personalizados**e forneça um valor para a **URL da página de resultados:**.Em seguida, salve suas alterações. A URL que você usa aqui deve ser para a página que você criou para usar como sua página de resultados personalizada.

>[!NOTE]
> A página de resultados personalizados precisa estar no mesmo domínio que seu site, mas não precisa estar no mesmo conjunto de sites.  

Como alternativa, você pode usar o [comando Set-PnPSearchSettings do SharePoint PNP PowerShell](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpsearchsettings?view=sharepoint-ps) para definir o valor em vez de usar a página Configurações do site.

Uma vez definido, a página de resultados de pesquisa personalizada é exibida quando você pesquisa usando a caixa de pesquisa da Microsoft que aparece na barra de navegação na parte superior da página e é usada quando você insere a pesquisa de páginas do site ou a home page do site. Ele não é usado quando você está pesquisando dentro de uma lista, biblioteca ou página de conteúdo do site. Você pode usar o link para expandir sua pesquisa de resultados de pesquisa em listas e bibliotecas para acessar a página de resultados personalizados.

## <a name="change-the-layout-of-your-custom-results-page"></a>Alterar o layout da página de resultados personalizados

Um layout de página chamado **HeaderlessSearchResults** pode ser usado para tornar a página de resultados de pesquisa mais próxima da experiência de resultados de pesquisa pronta para uso.Este novo layout só pode estar ativo para as páginas que estão definidas para ser a página de resultados de pesquisa personalizada.

Para definir o layout da página, você pode usar o [comando Set-PnPClientSidePageSharePoint PNP PowerShell](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnpclientsidepage?view=sharepoint-ps) com-LayoutType HeaderlessSearchResults.

## <a name="use-sharepoint-framework-query-extensions"></a>Usar extensões de consulta da estrutura do SharePoint

As páginas de resultados de pesquisa personalizadas também podem usar a [extensão de consulta da estrutura do SharePoint](https://docs.microsoft.com/sharepoint/dev/spfx/building-search-extensions) para modificar a consulta antes de enviá-la para o mecanismo de pesquisa.

## <a name="additional-resources"></a>Recursos adicionais

Para saber mais sobre a página de resultados personalizados, Confira nossa [sessão de implantação e personalização de pesquisa do Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/85238?source=sessions).

Para projetos de código aberto, introdução às APIs de pesquisa da Microsoft e mais exemplos de personalização e extensibilidade, visite [o Microsoft Search no GitHub](https://github.com/microsoft-search).
