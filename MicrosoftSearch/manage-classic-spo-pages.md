---
title: Páginas clássicas no SharePoint Online e Pesquisa da Microsoft
ms.author: keremy
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Usando Pesquisa da Microsoft em páginas SharePoint clássicas
ms.openlocfilehash: 5b9c40da63ccf3b28cf2d61282763d3d4f62f867
ms.sourcegitcommit: bb99601a7bd0f16dde7b271de516465d134e5bac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/08/2021
ms.locfileid: "58973747"
---
# <a name="classic-pages-and-microsoft-search"></a>Páginas clássicas e Pesquisa da Microsoft

SharePoint sites criados antes dos sites modernos usam uma caixa de pesquisa clássica e uma experiência clássica de resultados de pesquisa. Vamos lançar um recurso que irá padrão de páginas clássicas para começar a usar a experiência de pesquisa moderna que usa Pesquisa da Microsoft, que fornece resultados personalizados com maior relevância.

O uso do Pesquisa da Microsoft é recomendado para todos os sites, incluindo os clássicos, mas se seus sites clássicos usarem páginas mestras personalizadas e/ou você tiver personalizado sua experiência clássica de resultados de pesquisa, detectaremos automaticamente essas personalizações e não mudaremos para Pesquisa da Microsoft.

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Sites clássicos que alternarão automaticamente para Pesquisa da Microsoft

Sites clássicos começarão a usar Pesquisa da Microsoft se todos os seguintes são verdadeiros:

* O site se baseia no modelo de site de equipe (como STS#0 e STS#1).
* O site não tem o recurso de publicação ligado.
* O site não usa uma página mestra personalizada (uma página mestra diferente de oslo.master ou seattle.master).
* Não há regras de consulta ativas que não sejam aquelas que adicionam resultados promovidos para o site, conjunto de sites ou locatário na fonte de resultados padrão.
* Não há tipos de resultados personalizados para o site ou o conjunto de sites na fonte de resultados padrão.
* O site ou o conjunto de sites não é optado pela opção usando a *configuração SearchBoxInNavBar* descrita abaixo.

Após a opção para Pesquisa da Microsoft, as páginas clássicas no site começarão a mostrar a caixa de pesquisa na barra de navegação do pacote e removerão a caixa de pesquisa clássica da página. Em seguida, quando um usuário pesquisa um termo, os resultados serão exibidos usando a experiência de pesquisa moderna de Pesquisa da Microsoft.

## <a name="staying-with-the-classic-search-experience"></a>Permanecendo com a experiência de pesquisa clássica

Se seu site atender aos critérios listados acima, mas você não quiser que ele alterne para a experiência de Pesquisa da Microsoft, você pode optar por usar os seguintes comandos, como o proprietário do site ou do conjunto de sites.

Você pode usar esse comando a qualquer momento, antes ou depois que a opção acontecer, portanto, é fácil voltar à experiência de pesquisa que você tinha anteriormente.

Para executar os comandos abaixo, você usará o PowerShell com SharePoint extensões pnP do PowerShell. Você pode instalar e saber mais sobre como começar [aqui](/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps). Você fará login no seu site ou conjunto de sites usando este comando:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

Para manter a experiência de pesquisa clássica para um site, execute o seguinte comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

Alternativamente, se você quiser defini-lo para todos os sites em um conjunto de sites, você pode usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Opting into Pesquisa da Microsoft

Para os sites que não atendem aos critérios listados acima ou para sites específicos em um conjunto de sites que optaram por permanecer no clássico, você pode habilitar manualmente a experiência de Pesquisa da Microsoft.

Para alterar essa configuração para um site específico, você pode usar este comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

Se você quiser defini-lo para todos os sites em um conjunto de sites, use este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> Você pode habilitar manualmente Pesquisa da Microsoft somente para um Site de Equipe ou Site de Publicação (ids de modelo que contenham "STS", "CMSPUBLISHING", "BLANKINTERNET" e "GROUP").