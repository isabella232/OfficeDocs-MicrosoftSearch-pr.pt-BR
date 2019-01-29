---
title: Testar logon único
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
description: Reduzir o número de vezes que os usuários do Windows 10 for solicitados a entrar no Microsoft Search e o Office 365
ms.openlocfilehash: 55d359edac36020ec8cf2aad6b64ca9737ee1066
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612344"
---
# <a name="test-single-sign-on"></a><span data-ttu-id="8fdd7-103">Testar logon único</span><span class="sxs-lookup"><span data-stu-id="8fdd7-103">Test single sign-on</span></span>

<span data-ttu-id="8fdd7-p101">Logon único reduz o número de vezes que os usuários são solicitados a entrar. Testar o single sign-on com um pequeno grupo de usuários ajudará a identificar problemas de configuração de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="8fdd7-p101">Single sign-on reduces the number of times users are prompted to sign in. Testing single sign-on with a small group of users will help identify any blocking configuration issues.</span></span> 
  
<span data-ttu-id="8fdd7-106">Para usuários do Chrome em Windows 10, sign-on único funcionará somente se o Windows 10 e AAD entrar extensão cromo está instalada.</span><span class="sxs-lookup"><span data-stu-id="8fdd7-106">For Chrome users on Windows 10, single sign-on will only work if the Windows 10 and AAD sign-in extension for Chrome is installed.</span></span> 
  
## <a name="download-the-windows-10-and-aad-sign-in-extension-for-chrome"></a><span data-ttu-id="8fdd7-107">Baixe o Windows 10 e AAD entrar extensão para Chrome</span><span class="sxs-lookup"><span data-stu-id="8fdd7-107">Download the Windows 10 and AAD sign-in extension for Chrome</span></span>

<span data-ttu-id="8fdd7-108">Recomendamos que você crie uma diretiva de grupo para instalar automaticamente essa extensão.</span><span class="sxs-lookup"><span data-stu-id="8fdd7-108">We recommend that you create a group policy to automatically install this extension.</span></span>
  
1. <span data-ttu-id="8fdd7-109">Vá para o portal de administração de pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8fdd7-109">Go to the Microsoft Search Admin portal</span></span>
    
2. <span data-ttu-id="8fdd7-110">No painel de navegação, clique em **Ferramentas**</span><span class="sxs-lookup"><span data-stu-id="8fdd7-110">In the navigation pane, click **Tools**</span></span>
    
3. <span data-ttu-id="8fdd7-111">Na lista de ferramentas, baixe o **Windows 10 e AAD entrar extensão de cromo**</span><span class="sxs-lookup"><span data-stu-id="8fdd7-111">In the Tools list, download the **Windows 10 and AAD sign-in extension for Chrome**</span></span>
    
4. <span data-ttu-id="8fdd7-112">Compartilhar a extensão com usuários de Chrome em Windows 10</span><span class="sxs-lookup"><span data-stu-id="8fdd7-112">Share the extension with Chrome users on Windows 10</span></span>

  

