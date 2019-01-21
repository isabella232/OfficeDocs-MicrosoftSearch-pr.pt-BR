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
description: Certifique-se de uma experiência uniforme entrar para seus usuários, configurando o servidor DNS usando um registro CNAME
ms.openlocfilehash: f08fc4c29c4c4356a1616faab67fdebdd6c85839
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378410"
---
# <a name="advanced-dns-configuration"></a><span data-ttu-id="66907-103">Configuração avançada de DNS</span><span class="sxs-lookup"><span data-stu-id="66907-103">Advanced DNS configuration</span></span>

<span data-ttu-id="66907-p101">Para garantir o Bing pode sempre identificar usuários dentro da sua organização e assiná-las com êxito suas contas de trabalho ou da escola, configure seu servidor DNS interno ou um servidor proxy para resolver de `www.bing.com` para `ms.bing.com`. Para fazer isso, crie uma entrada DNS para `www.bing.com` para ser um registro CNAME para `ms.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="66907-p101">To ensure Bing can always identify users within your organization and successfully sign them in to their work or school account, configure your internal DNS server or proxy server to resolve from `www.bing.com` to `ms.bing.com`. To do this, create a DNS entry for `www.bing.com` to be a CNAME for `ms.bing.com`.</span></span>
  
****

|<span data-ttu-id="66907-106">**Nome**</span><span class="sxs-lookup"><span data-stu-id="66907-106">**Name**</span></span>|<span data-ttu-id="66907-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="66907-107">**Type**</span></span>|<span data-ttu-id="66907-108">**Valor**</span><span class="sxs-lookup"><span data-stu-id="66907-108">**Value**</span></span>|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |<span data-ttu-id="66907-109">CNAME</span><span class="sxs-lookup"><span data-stu-id="66907-109">CNAME</span></span>  <br/> |`ms.bing.com`  <br/> |
   
<span data-ttu-id="66907-p102">Usando um registro CNAME em vez do endereço IP é preferido, desde que um registro CNAME continuarão a funcionar se altera o endereço IP. Depois de fazer essa alteração DNS, resultados continuará apareça para os seus usuários, como se eles são provenientes `www.bing.com`.</span><span class="sxs-lookup"><span data-stu-id="66907-p102">Using a CNAME rather than the IP address is preferred since a CNAME will continue to work if the IP address changes. After you make this DNS change, results will continue to appear to your users as if they are coming from `www.bing.com`.</span></span> 
  
<span data-ttu-id="66907-p103">Isso requer nenhuma configuração adicional em computadores clientes e oferece uma experiência uniforme para seus usuários. Quando eles vão para `bing.com`, eles vai ser automaticamente conectados mais consistentemente e se eles não podem ser conectados automaticamente, serão solicitados a fazer isso.</span><span class="sxs-lookup"><span data-stu-id="66907-p103">This requires no additional configuration on client machines and provides a seamless experience for your users. When they go to `bing.com`, they'll be automatically signed in more consistently, and if they can't be signed in automatically, they'll be prompted to do so.</span></span>
