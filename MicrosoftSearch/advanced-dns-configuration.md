---
title: Configuração avançada de DNS
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
description: Garanta uma experiência conexão perfeita para seus usuários ao configurar o servidor DNS usando um CNAME
ms.openlocfilehash: fa797b95f346d6d03bd020da146bb330c715e392
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612427"
---
# <a name="advanced-dns-configuration"></a>Configuração avançada de DNS

Para garantir que o Bing sempre possa identificar usuários em sua organização e conectá-los com êxito em sua conta corporativa ou de estudante, configure seu servidor DNS interno ou servidor proxy para resolver de `www.bing.com` a `ms.bing.com`. Para fazer isso, crie uma entrada de DNS para `www.bing.com` para servir como um CNAME para `ms.bing.com`.
  
****

|**Nome**|**Tipo**|**Valor**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |CNAME  <br/> |`ms.bing.com`  <br/> |
   
É preferível usar um CNAME em vez do endereço IP já que um CNAME continuará a funcionar se o endereço IP mudar. Depois que você fizer essa alteração de DNS, os resultados continuarão aparecendo para seus usuários como se fossem provenientes de `www.bing.com`. 
  
Isso não requer configuração adicional nas máquinas clientes e fornece uma experiência perfeita para seus usuários. Ao acessarem `bing.com`, eles serão automaticamente conectados de forma mais consistente e, se não puderem ser conectados automaticamente, serão solicitados a fazê-lo.
