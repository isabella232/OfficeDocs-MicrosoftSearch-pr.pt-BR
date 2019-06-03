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
ROBOTS: NoIndex
description: Garanta uma experiência conexão perfeita para seus usuários ao configurar o servidor DNS usando um CNAME
ms.openlocfilehash: 6a291165df33f8acc99d247104e8e88cd35c3a0e
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591355"
---
# <a name="advanced-dns-configuration"></a>Configuração avançada de DNS

> [!IMPORTANT]
> Este artigo se aplica à Pesquisa da Microsoft no portal de administração do Bing. Estamos movendo o portal para o centro de administração do Microsoft 365 e, posteriormente, ele será removido. Recomendamos que você use o centro de administração do Microsoft 365 para começar. [Visão geral da Pesquisa da Microsoft.](overview-microsoft-search.md)
    
Para garantir que o Bing sempre possa identificar usuários em sua organização e conectá-los com êxito em sua conta corporativa ou de estudante, configure seu servidor DNS interno ou servidor proxy para resolver de `www.bing.com` a `ms.bing.com`. Para fazer isso, crie uma entrada de DNS para `www.bing.com` para servir como um CNAME para `ms.bing.com`.
  
****

|**Nome**|**Tipo**|**Valor**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |CNAME  <br/> |`ms.bing.com`  <br/> |
   
É preferível usar um CNAME em vez do endereço IP já que um CNAME continuará a funcionar se o endereço IP mudar. Depois que você fizer essa alteração de DNS, os resultados continuarão aparecendo para seus usuários como se fossem provenientes de `www.bing.com`. 
  
Isso não requer configuração adicional nas máquinas clientes e fornece uma experiência perfeita para seus usuários. Ao acessarem `bing.com`, eles serão automaticamente conectados de forma mais consistente e, se não puderem ser conectados automaticamente, serão solicitados a fazê-lo.
