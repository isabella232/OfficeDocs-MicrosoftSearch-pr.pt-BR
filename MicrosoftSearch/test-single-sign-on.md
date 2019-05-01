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
description: Reduza o número de vezes que seus usuários do Windows 10 são solicitados a entrar no Microsoft Search e no Office 365
ms.openlocfilehash: 55d359edac36020ec8cf2aad6b64ca9737ee1066
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508926"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="e2618-103">Testar o logon único</span><span class="sxs-lookup"><span data-stu-id="e2618-103">Test single sign-on</span></span>

<span data-ttu-id="e2618-p101">O logon único reduz o número de vezes que os usuários são solicitados a entrar. O teste de logon único com um pequeno grupo de usuários ajudará a identificar problemas de configuração de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="e2618-p101">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="e2618-106">Para usuários do Chrome no Windows 10, o logon único só funcionará se a extensão de logon do Windows 10 e do AAD para o Chrome estiver instalada.</span><span class="sxs-lookup"><span data-stu-id="e2618-106">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="e2618-107">Faça o download da extensão de logon do Windows 10 e do AAD para o Chrome</span><span class="sxs-lookup"><span data-stu-id="e2618-107">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="e2618-108">Recomendamos a criação de uma política de grupo para instalar automaticamente essa extensão.</span><span class="sxs-lookup"><span data-stu-id="e2618-108">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="e2618-109">Acesse o Portal de Administração da Pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e2618-109">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="e2618-110">No painel de navegação, clique em **Ferramentas**</span><span class="sxs-lookup"><span data-stu-id="e2618-110">In the navigation pane, click **Tools**</span></span>
    
3. <span data-ttu-id="e2618-111">Na lista Ferramentas, faça o download da **extensão de logon do Windows 10 e do AAD para o Chrome**</span><span class="sxs-lookup"><span data-stu-id="e2618-111">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="e2618-112">Compartilhe a extensão com usuários do Chrome no Windows 10</span><span class="sxs-lookup"><span data-stu-id="e2618-112">Share the extension with Chrome users on Windows 10</span></span>

  

