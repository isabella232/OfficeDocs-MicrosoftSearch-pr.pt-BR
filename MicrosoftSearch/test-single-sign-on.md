---
title: Testar o logon único
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: a220c1bf-7cee-448a-90a3-310284d03e81
ROBOTS: NOINDEX
description: Reduza o número de vezes que seus usuários do Windows 10 são solicitados a entrar no Microsoft Search e no Office 365
ms.openlocfilehash: c05a8ffcc973926add551bdbb20273b41ea23bc0
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591040"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="7d439-103">Testar o logon único</span><span class="sxs-lookup"><span data-stu-id="7d439-103">Test single sign-on</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d439-104">Este artigo se aplica à Pesquisa do Microsoft no portal de administração do Bing.</span><span class="sxs-lookup"><span data-stu-id="7d439-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="7d439-105">Estamos movendo o portal para o centro de administração do Microsoft 365 e, posteriormente, ele será removido.</span><span class="sxs-lookup"><span data-stu-id="7d439-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="7d439-106">Recomendamos que você use o centro de administração do Microsoft 365 para começar.</span><span class="sxs-lookup"><span data-stu-id="7d439-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> [<span data-ttu-id="7d439-107">Visão geral da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7d439-107">Overview of Microsoft Search</span></span>](overview-microsoft-search.md)
    
<span data-ttu-id="7d439-p102">O logon único reduz o número de vezes que os usuários são solicitados a entrar. O teste de logon único com um pequeno grupo de usuários ajudará a identificar problemas de configuração de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="7d439-p102">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="7d439-110">Para usuários do Chrome no Windows 10, o logon único só funcionará se a extensão de logon do Windows 10 e do AAD para o Chrome estiver instalada.</span><span class="sxs-lookup"><span data-stu-id="7d439-110">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="7d439-111">Faça o download da extensão de logon do Windows 10 e do AAD para o Chrome</span><span class="sxs-lookup"><span data-stu-id="7d439-111">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="7d439-112">Recomendamos a criação de uma política de grupo para instalar automaticamente essa extensão.</span><span class="sxs-lookup"><span data-stu-id="7d439-112">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="7d439-113">Acesse o Portal de Administração da Pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7d439-113">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="7d439-114">No painel de navegação, clique em **Ferramentas**</span><span class="sxs-lookup"><span data-stu-id="7d439-114">In the navigation pane, click **Tools**</span></span>
    
3. <span data-ttu-id="7d439-115">Na lista Ferramentas, faça o download da **extensão de logon do Windows 10 e do AAD para o Chrome**</span><span class="sxs-lookup"><span data-stu-id="7d439-115">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="7d439-116">Compartilhe a extensão com usuários do Chrome no Windows 10</span><span class="sxs-lookup"><span data-stu-id="7d439-116">Share the extension with Chrome users on Windows 10</span></span>

  

