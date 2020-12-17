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
description: Como personalizar a experiência de caixa de pesquisa em sites do SharePoint
ms.openlocfilehash: 6ebd084aadb38acb5475b7e43d7c4092ffc09eb8
ms.sourcegitcommit: c5fe4e01403379b3ee7ea4dbded8b31696311d79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49700960"
---
# <a name="search-box-settings-on-sharepoint-sites"></a>Configurações da caixa de pesquisa em sites do SharePoint

Uma das várias maneiras de o Microsoft Search ser personalizada nos sites do SharePoint é personalizar como a caixa de pesquisa na barra de navegação do pacote funciona em sites do SharePoint para atender melhor às suas necessidades.

Para outras opções de personalização, confira [alterar a página de resultados da pesquisa da Microsoft para adicionar verticais, tipos e layouts de resultados personalizados](customize-search-page.md)e [criar uma página de resultados de pesquisa personalizada](create-search-results-pages.md).

> [!NOTE]
> A caixa de pesquisa da barra de navegação do pacote não está disponível para todos os clientes no momento, mas essas opções ainda podem ser definidas e elas entrarão em vigor quando estiverem disponíveis.

Para as tarefas listadas abaixo, você usará o PowerShell com as extensões do PowerShell PnP do SharePoint. Você pode instalar e saber mais sobre como começar [aqui](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps). Você entrará no site ou no conjunto de sites usando este comando:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials 
```

## <a name="changing-the-scope-of-search"></a>Alterar o escopo da pesquisa

Quando você cria um novo site no SharePoint Online hoje e digita na caixa de pesquisa, é exibida a página de resultados da pesquisa da Microsoft. Essa página mostra os resultados do seu site atual por padrão e permite que você expanda o escopo de sua pesquisa para o Hub ao qual o site atual está associado (se houver algum) ou a toda a organização.

O escopo usado pela caixa de pesquisa, por padrão, depende do tipo de site.

* Pesquisa de sites regulares no site atual.
* Os sites de Hub pesquisam todos os sites no Hub.
* Sites domésticos pesquisam todo o conteúdo.

Em alguns casos, talvez você queira alterar esses padrões para sempre Pesquisar toda a organização ou ao longo do Hub ao qual um site está associado, sem precisar de mais um clique.

Como proprietário do site, você pode alterar esses padrões usando o seguinte comando:

```powershell
Set-PnPSearchSettings -SearchScope Tenant
# DefaultScope | Hub | Site | Tenant
```

Depois de executar esse comando, o site que estava mostrando os resultados do site atual por padrão será iniciado para mostrar os resultados da organização inteira.

Para voltar para a configuração padrão, execute o comando novamente com o valor "DefaultScope". Para Pesquisar pelo Hub, use "Hub" como o valor SearchScope.

Essa configuração se aplica ao nível de site individual. Não há nenhuma configuração equivalente para conjuntos de sites.

## <a name="show-or-hide-the-search-box"></a>Mostrar ou ocultar a caixa de pesquisa

Você pode optar por ocultar a caixa de pesquisa da barra de navegação do pacote se quiser impedir que os usuários pesquisem ou usem uma implementação de caixa de pesquisa personalizada.

Para alterar essa configuração para um determinado site, use este comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Como alternativa, se você quiser defini-lo para todos os sites em um conjunto de sites, poderá usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar Hidden
# Hidden | Inherit
```

Após a execução desses comandos, a caixa de pesquisa não será mais exibida na barra de navegação na parte superior da página. Para voltar a mostrar a caixa de pesquisa, execute os comandos novamente com o valor fornecido para o parâmetro "SearchBoxInNavBar" como "Inherit".

Há vários pontos a serem considerados:

* Essa configuração só se aplica à caixa de pesquisa na barra de navegação do pacote. Ela não se aplica às caixas de pesquisa que estão na página ou às caixas de pesquisa em páginas clássicas.

* Depois de desabilitar a caixa de pesquisa na barra de navegação, se você quiser a funcionalidade de pesquisa no seu site, você terá que fazê-lo sozinho usando uma Web Part personalizada ou uma extensão da estrutura do SharePoint.

* Essa solução também removerá a caixa de pesquisa de listas e bibliotecas do seu site. Sua solução de pesquisa personalizada precisará considerar pesquisas contextuais para listas e bibliotecas do SharePoint, além de pesquisa em todo o site.

* Se você aplicar a configuração ao site raiz do seu domínio, a página inicial do SharePoint também será interrompida mostrando a caixa de pesquisa.

## <a name="changing-the-hint-displayed-in-the-search-box"></a>Alterar a dica exibida na caixa de pesquisa

Você pode alterar a dica que a caixa de pesquisa mostra para um determinado site ou conjunto de sites. Este é o texto que aparece na caixa de pesquisa antes de começar a digitar nele. Isso pode ajudar a orientar os usuários sobre o que esperar da pesquisa se você tiver configurado uma página de resultados personalizada ou alterado o comportamento de pesquisa de outras maneiras.

> [!NOTE]
> Para poder fazer essa alteração, você precisa permitir a execução de scripts personalizados no site em questão como um administrador de locatários, que não é permitido por padrão. Confira os https://docs.microsoft.com/sharepoint/allow-or-prevent-custom-script detalhes. Você pode permitir a execução de scripts personalizados, fazer a alteração e, em seguida, reverter para não permitir scripts para o site, se necessário.

Para alterar essa configuração para um determinado site, execute o seguinte comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxPlaceholderText "my placeholder" 
```

Como alternativa, se você quiser defini-lo para todos os sites em um conjunto de sites, poderá usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxPlaceholderText "my placeholder" 
```

Para voltar ao texto do espaço reservado padrão, defina o valor como em branco ("").
