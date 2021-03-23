---
title: Gerenciando a caixa de pesquisa em sites do SharePoint
ms.author: keremy
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
description: Como personalizar a experiência da caixa de pesquisa em sites do SharePoint
ms.openlocfilehash: c58e7cf0a47d22fa9c6fd3abd93cc97087625690
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031355"
---
# <a name="search-box-settings-on-sharepoint-sites"></a>Configurações da caixa de pesquisa em sites do SharePoint

Uma das várias maneiras de a Pesquisa da Microsoft ser personalizada em sites do SharePoint é adaptar como a caixa de pesquisa na barra de navegação do pacote funciona em sites do SharePoint para melhor se ajustar às suas necessidades.

Para outras opções de personalização, consulte Changing the Microsoft Search results page to add [custom verticals, result types and layouts](customize-search-page.md), and [Creating a custom search results page](create-search-results-pages.md).

> [!NOTE]
> A caixa de pesquisa da barra de navegação do pacote não está disponível para todos os clientes no momento, mas essas opções ainda podem ser definidas agora e terão efeito quando ela se tornar disponível.

Para as tarefas listadas abaixo, você usará o PowerShell com extensões pnP do PowerShell do SharePoint. Você pode instalar e saber mais sobre como começar [aqui](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps). Você entrará em seu site ou conjunto de sites usando este comando:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a>Alterando o escopo da pesquisa

Quando você cria um novo site no SharePoint Online hoje e digita na caixa de pesquisa, é levado para a página de resultados da Pesquisa da Microsoft. Esta página mostra os resultados do site atual por padrão e permite expandir o escopo da pesquisa para o hub ao qual o site atual está associado (se houver um) ou para toda a organização.

O escopo que a caixa de pesquisa usa, por padrão, depende do tipo de site.

* Sites regulares pesquisam no site atual.
* Sites de hub pesquisam todos os sites no hub.
* Sites locais pesquisam todo o conteúdo.

Em alguns casos, talvez você queira alterar esses padrões para sempre pesquisar em toda a organização ou no hub ao que um site está associado, sem precisar de um clique adicional.

Como proprietário do site, você pode alterar esses padrões usando o seguinte comando:

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

Depois de executar esse comando, o site que estava anteriormente mostrando resultados do site atual por padrão começará a mostrar resultados de toda a organização.

Para voltar à configuração padrão, execute o comando novamente com o valor "DefaultScope". Para pesquisar no Hub, use "Hub" como o valor SearchScope.

Essa configuração se aplica ao nível de site individual. Não há configuração equivalente para os conjunto de sites.

## <a name="show-or-hide-the-search-box"></a>Mostrar ou ocultar a caixa de pesquisa

Você pode optar por ocultar a caixa de pesquisa da barra de navegação do pacote se quiser impedir que os usuários pesquisem ou usem uma implementação de caixa de pesquisa personalizada.

Para alterar essa configuração para um determinado site, use este comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Alternativamente, se você quiser defini-lo para todos os sites em um conjunto de sites, você pode usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Depois de executar esses comandos, a caixa de pesquisa não será mais aparecer na barra de navegação na parte superior da página. Para voltar a mostrar a caixa de pesquisa, execute os comandos novamente com o valor fornecido para o parâmetro "SearchBoxInNavBar" como "Herdar".

Há vários pontos a considerar:

* Essa configuração só se aplica à caixa de pesquisa na barra de navegação do pacote. Ele não se aplica às caixas de pesquisa que estão na página ou às caixas de pesquisa em páginas clássicas.

* Depois de desabilitar a caixa de pesquisa na barra de navegação, se quiser a funcionalidade de pesquisa em seu site, será preciso fornecer você mesmo usando uma Web Part personalizada ou uma extensão da Estrutura do SharePoint.

* Essa solução também removerá a caixa de pesquisa de listas e bibliotecas do seu site. Sua solução de pesquisa personalizada precisará considerar pesquisas contextuais para listas e bibliotecas do SharePoint, além da pesquisa em todo o site.

* Se você aplicar a configuração ao site raiz do seu domínio, a página inicial do SharePoint também interromperá a exibição da caixa de pesquisa.

## <a name="changing-the-hint-displayed-in-the-search-box"></a>Alterar a dica exibida na caixa de pesquisa

Você pode alterar a dica que a caixa de pesquisa mostra para um determinado site ou conjunto de sites. Este é o texto que aparece na caixa de pesquisa antes de começar a digitar nele. Isso pode ajudar a orientar os usuários sobre o que esperar da pesquisa se você configurou uma página de resultados personalizada ou alterou o comportamento da pesquisa de outras maneiras.

> [!NOTE]
> Para fazer essa alteração, você precisa permitir a execução de scripts personalizados no site em questão como administrador de locatários, o que é não permitido por padrão. Confira https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script mais detalhes. Você pode permitir a execução de scripts personalizados, fazer a alteração e, em seguida, reverter para não permitir scripts para o site, se necessário.

Para alterar essa configuração para um determinado site, execute o seguinte comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

Alternativamente, se você quiser defini-lo para todos os sites em um conjunto de sites, você pode usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

Para voltar ao texto de espaço reservado padrão, de definir o valor como em branco ("").