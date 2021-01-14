---
title: Páginas clássicas no SharePoint Online e na Pesquisa da Microsoft
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
description: Usando a Pesquisa da Microsoft em páginas clássicas do SharePoint
ms.openlocfilehash: 9a5aeb2e683297faccfb55d3407653c1791b3961
ms.sourcegitcommit: 7133d46ca9c3a5216ee9159db781febd17e5a831
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49863170"
---
# <a name="classic-pages-and-microsoft-search"></a>Páginas clássicas e Pesquisa da Microsoft

Os sites do SharePoint criados antes dos sites modernos usam uma caixa de pesquisa clássica e uma experiência clássica de resultados de pesquisa. We will be rolling out a feature that will default classic pages to start using the modern search experience that uses Microsoft Search, which provides personalized results with higher relevance.

O uso da Pesquisa da Microsoft é recomendado para todos os sites, incluindo clássico, mas se os sites clássicos usarem páginas mestras personalizadas e/ou você tiver personalizado sua experiência clássica de resultados de pesquisa, detectaremos automaticamente essas personalizações e não alternamos para a Pesquisa da Microsoft.

## <a name="classic-sites-that-will-automatically-switch-to-microsoft-search"></a>Sites clássicos que alternarão automaticamente para a Pesquisa da Microsoft

Os sites clássicos começarão a usar a Pesquisa da Microsoft se todos os seguintes são verdadeiros:

* O site é baseado no modelo de site de equipe (como STS#0 e STS#1).
* O site não tem o recurso de publicação ligado.
* O site não usa uma página mestra personalizada (uma página mestra diferente de oslo.master ou seattle.master).
* Não há regras de consulta ativas além das que adicionam resultados promovidos para o site, conjunto de sites ou locatário na fonte de resultados padrão.
* Não há nenhum tipo de resultado personalizado para o site ou o conjunto de sites na fonte de resultados padrão.
* O site ou o conjunto de sites não é optado pela opção usando a configuração *SearchBoxInNavBar* descrita abaixo.

Após a mudança para a Pesquisa da Microsoft, as páginas clássicas do site começarão a mostrar a caixa de pesquisa na barra de navegação do pacote e removerão a caixa de pesquisa clássica da página. Em seguida, quando um usuário procurar um termo, os resultados serão exibidos usando a experiência de pesquisa moderna da Pesquisa da Microsoft.

## <a name="staying-with-the-classic-search-experience"></a>Mantendo a experiência de pesquisa clássica

Se o seu site atender aos critérios listados acima, mas você não quiser que ele mude para a experiência da Pesquisa da Microsoft, você poderá optar por não usar os seguintes comandos, como o proprietário do site ou do conjunto de sites.

Você pode usar esse comando a qualquer momento, antes ou depois que a troca acontece, portanto, é fácil voltar à experiência de pesquisa que você tinha anteriormente.

Para executar os comandos abaixo, você usará o PowerShell com extensões do PowerShell pnP do SharePoint. Você pode instalar e saber mais sobre como começar [aqui.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-pnp/sharepoint-pnp-cmdlets?view=sharepoint-ps) Você fará o login no seu site ou conjunto de sites usando este comando:

```powershell
Connect-PnPOnline -Url <yoursiteurl> -UseWebLogin
# this will prompt you to sign in to your site. Use the site owner credentials.
```

Para permanecer com a experiência de pesquisa clássica de um site, execute o seguinte comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

Como alternativa, se você quiser defini-lo para todos os sites em um conjunto de sites, poderá usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar ModernOnly
# ModernOnly | Inherit
```

## <a name="opting-into-microsoft-search"></a>Optando pela Pesquisa da Microsoft

Para os sites que não atendem aos critérios listados acima ou para sites específicos em um conjunto de sites que optaram por permanecer no clássico, você pode habilitar manualmente a experiência de Pesquisa da Microsoft.

Para alterar essa configuração para um site específico, você pode usar este comando:

```powershell
Set-PnPSearchSettings -Scope Web -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

Se você quiser defini-lo para todos os sites em um conjunto de sites, poderá usar este comando:

```powershell
Set-PnPSearchSettings -Scope Site -SearchBoxInNavBar AllPages
# AllPages | Inherit
```

> [!NOTE]
> Você pode habilitar manualmente a Pesquisa da Microsoft apenas para um Site de Equipe ou Site de Publicação (IDs de modelo que contenham "STS", "CMSPUBLISHING", "BLANKINTERNET" e "GROUP").
