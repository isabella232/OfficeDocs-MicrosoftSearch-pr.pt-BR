---
title: Configuração avançada de DNS
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/19/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MOE150
- MED150
ms.assetid: 47eedbb9-6da9-47e0-aac5-078d34a7fd8f
ROBOTS: NoIndex
description: Garanta uma experiência conexão perfeita para seus usuários ao configurar o servidor DNS usando um CNAME
ms.openlocfilehash: 062c43cfbc8d25c263eb2402bd05191e385411b2
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311322"
---
# <a name="advanced-dns-configuration"></a><span data-ttu-id="c3950-103">Configuração avançada de DNS</span><span class="sxs-lookup"><span data-stu-id="c3950-103">Advanced DNS configuration</span></span>

<span data-ttu-id="c3950-p101">Para garantir que o Bing sempre possa identificar usuários em sua organização e conectá-los com êxito em sua conta corporativa ou de estudante, configure seu servidor DNS interno ou servidor proxy para resolver de `www.bing.com` a `ms.bing.com`. Para fazer isso, crie uma entrada de DNS para `www.bing.com` para servir como um CNAME para `ms.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="c3950-p101">To ensure Bing can always identify users within your organization and successfully sign them in to their work or school account, configure your internal DNS server or proxy server to resolve from `www.bing.com` to `ms.bing.com`. To do this, create a DNS entry for `www.bing.com` to be a CNAME for `ms.bing.com`.</span></span>
  
****

|<span data-ttu-id="c3950-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="c3950-106">**Name**</span></span>|<span data-ttu-id="c3950-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c3950-107">**Type**</span></span>|<span data-ttu-id="c3950-108">**Valor**</span><span class="sxs-lookup"><span data-stu-id="c3950-108">**Value**</span></span>|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |<span data-ttu-id="c3950-109">CNAME</span><span class="sxs-lookup"><span data-stu-id="c3950-109">CNAME</span></span>  <br/> |`ms.bing.com`  <br/> |
   
<span data-ttu-id="c3950-p102">É preferível usar um CNAME em vez do endereço IP já que um CNAME continuará a funcionar se o endereço IP mudar. Depois que você fizer essa alteração de DNS, os resultados continuarão aparecendo para seus usuários como se fossem provenientes de `www.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="c3950-p102">Using a CNAME rather than the IP address is preferred since a CNAME will continue to work if the IP address changes. After you make this DNS change, results will continue to appear to your users as if they are coming from `www.bing.com`.</span></span> 
  
<span data-ttu-id="c3950-p103">Isso não requer configuração adicional nas máquinas clientes e fornece uma experiência perfeita para seus usuários. Ao acessarem `bing.com`, eles serão automaticamente conectados de forma mais consistente e, se não puderem ser conectados automaticamente, serão solicitados a fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="c3950-p103">This requires no additional configuration on client machines and provides a seamless experience for your users. When they go to `bing.com`, they'll be automatically signed in more consistently, and if they can't be signed in automatically, they'll be prompted to do so.</span></span>