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
# <a name="advanced-dns-configuration"></a>Configuração avançada de DNS

Para garantir o Bing pode sempre identificar usuários dentro da sua organização e assiná-las com êxito suas contas de trabalho ou da escola, configure seu servidor DNS interno ou um servidor proxy para resolver de `www.bing.com` para `ms.bing.com`. Para fazer isso, crie uma entrada DNS para `www.bing.com` para ser um registro CNAME para `ms.bing.com`.
  
****

|**Nome**|**Tipo**|**Valor**|
|:-----|:-----|:-----|
|`www.bing.com`  <br/> |CNAME  <br/> |`ms.bing.com`  <br/> |
   
Usando um registro CNAME em vez do endereço IP é preferido, desde que um registro CNAME continuarão a funcionar se altera o endereço IP. Depois de fazer essa alteração DNS, resultados continuará apareça para os seus usuários, como se eles são provenientes `www.bing.com`. 
  
Isso requer nenhuma configuração adicional em computadores clientes e oferece uma experiência uniforme para seus usuários. Quando eles vão para `bing.com`, eles vai ser automaticamente conectados mais consistentemente e se eles não podem ser conectados automaticamente, serão solicitados a fazer isso.
