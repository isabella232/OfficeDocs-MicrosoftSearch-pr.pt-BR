---
title: Páginas clássicas no SharePoint Online e no Microsoft Search
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
description: Usando o Microsoft Search em páginas clássicas do SharePoint
ms.openlocfilehash: 605e63a30ad166c63320c7e89e1b2745e628e15d
ms.sourcegitcommit: c5fe4e01403379b3ee7ea4dbded8b31696311d79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49700969"
---
# <a name="classic-pages-and-microsoft-search"></a>Páginas clássicas e pesquisa da Microsoft

Os sites do SharePoint criados antes de sites modernos usam uma caixa de pesquisa clássica e uma experiência de resultados de pesquisa clássica. Iremos distribuir um recurso que usará as páginas clássicas padrão para começar a usar a experiência de pesquisa moderna que usa a pesquisa da Microsoft, que fornece resultados personalizados com maior relevância.

O uso da pesquisa da Microsoft é recomendado para todos os sites, incluindo o clássico, mas se seus sites clássicos usarem páginas mestras personalizadas e/ou se você tiver personalizado sua experiência de resultados de pesquisa clássica, iremos detectar automaticamente essas personalizações e não mudar para o Microsoft Search.

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Sites clássicos que mudarão automaticamente para a pesquisa da Microsoft

Os sites clássicos começarão a usar o Microsoft Search se todos os itens a seguir forem verdadeiros.

* O site é baseado no modelo de site de equipe (como STS # 0 e STS # 1).
* O site não tem o recurso publicação ativado.
* O site não usa uma página mestra personalizada (uma página mestra diferente de Oslo. Master ou Seattle. Master).
* Não há nenhuma regra de consulta ativa além daquelas que adicionam resultados promovidos para o site, o conjunto de sites ou o locatário na fonte de resultados padrão.
* Não há tipos de resultados personalizados para o site ou o conjunto de sites na fonte de resultados padrão.
* O site ou o conjunto de sites no qual ele faz parte não foi recusado usando a configuração SearchBoxInNavBar descrita abaixo.

Após a mudança para o Microsoft Search, as páginas clássicas no site começarão a mostrar a caixa de pesquisa na barra de navegação do pacote e removerá a caixa de pesquisa clássica da página. Assim, quando um usuário procurar um termo, os resultados serão exibidos usando a experiência de pesquisa moderna do Microsoft Search.

## <a name="staying-with-the-classic-search-experience"></a>Manter a experiência de pesquisa clássica

Se seu site atender aos critérios listados acima, mas você não quiser que ele mude para a experiência de pesquisa da Microsoft, você pode optar por usar os seguintes comandos, como o proprietário do site ou do conjunto de sites.

Você pode usar esse comando a qualquer momento, antes ou depois que a mudança ocorrer, portanto, é fácil voltar para a experiência de pesquisa que você tinha anteriormente.

Para executar os comandos abaixo, você usará o PowerShell com as extensões do PowerShell PnP do SharePoint. Você pode instalar e saber mais sobre como começar [aqui](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps). Você entrará no site ou no conjunto de sites usando este comando:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign into your site. Use the site owner credentials
```

Para manter a experiência de pesquisa clássica para um site, execute o seguinte comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

Como alternativa, se você quiser defini-lo para todos os sites em um conjunto de sites, poderá usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Optando pela pesquisa da Microsoft

Para os sites que não atendem aos critérios listados acima ou para sites específicos em um conjunto de sites que optou por permanecer no Classic, você pode habilitar manualmente a experiência de pesquisa da Microsoft.

Para alterar essa configuração para um site específico, você pode usar este comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

Se quiser defini-lo para todos os sites em um conjunto de sites, você pode usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> Você pode habilitar manualmente a pesquisa da Microsoft para um site de equipe ou site de publicação (IDs de modelo que contenham "STS", "CMSPUBLISHING", "BLANKINTERNET" e "GROUP").
