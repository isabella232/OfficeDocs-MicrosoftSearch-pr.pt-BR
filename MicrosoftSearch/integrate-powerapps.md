---
title: Integrar o PowerApps
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 1fadcba3-4a7f-4a55-8476-d4e64d49a15f
description: Incluir aplicativos baseados em navegador nos resultados dos indicadores da pesquisa da Microsoft
ms.openlocfilehash: d8d9d099848e719c86e0f3cadee330263566d243
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508822"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="3169f-103">Integrar o PowerApps</span><span class="sxs-lookup"><span data-stu-id="3169f-103">Integrate PowerApps</span></span>

<span data-ttu-id="3169f-104">Ajudar os usuários a concluir tarefas, como inserir o tempo de férias ou relatar despesas integrando o PowerApps existente em seus indicadores.</span><span class="sxs-lookup"><span data-stu-id="3169f-104">Help your users complete tasks, such as entering vacation time or reporting expenses by integrating existing PowerApps into your bookmarks.</span></span> <span data-ttu-id="3169f-105">O PowerApps integrado aparece dentro de um resultado de indicador, eliminando a necessidade de acessar um site diferente ou abrir uma ferramenta separada, o que poupa tempo e esforço.</span><span class="sxs-lookup"><span data-stu-id="3169f-105">Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="3169f-106">O que é PowerApps?</span><span class="sxs-lookup"><span data-stu-id="3169f-106">What are PowerApps?</span></span>

<span data-ttu-id="3169f-107">O PowerApps é um serviço que permite criar aplicativos de negócios que são executados em um navegador ou em um telefone ou Tablet sem nenhuma experiência de codificação necessária.</span><span class="sxs-lookup"><span data-stu-id="3169f-107">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="3169f-108">Saiba mais:</span><span class="sxs-lookup"><span data-stu-id="3169f-108">Learn more:</span></span>
  
- [<span data-ttu-id="3169f-109">Aprendizado guiado</span><span class="sxs-lookup"><span data-stu-id="3169f-109">Guided Learning</span></span>](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="3169f-110">Documentação</span><span class="sxs-lookup"><span data-stu-id="3169f-110">Documentation</span></span>](https://docs.microsoft.com/en-us/powerapps/)
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="3169f-111">Adicionar um PowerApp a um indicador</span><span class="sxs-lookup"><span data-stu-id="3169f-111">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="3169f-112">O PowerApps funciona em qualquer navegador e em qualquer dispositivo e levar menos de um minuto para adicionar.</span><span class="sxs-lookup"><span data-stu-id="3169f-112">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="3169f-113">[Encontre a ID do aplicativo para o PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que você deseja integrar</span><span class="sxs-lookup"><span data-stu-id="3169f-113">[Find the App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate</span></span> 
    
2. <span data-ttu-id="3169f-114">No portal do Microsoft SearchAdmin, vá para **indicadores**</span><span class="sxs-lookup"><span data-stu-id="3169f-114">In the Microsoft SearchAdmin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="3169f-115">Adicione um indicador ou localize um indicador existente ao qual você deseja adicionar um PowerApp</span><span class="sxs-lookup"><span data-stu-id="3169f-115">Add a bookmark or find an existing bookmark that you want to add a PowerApp to</span></span>
    
4. <span data-ttu-id="3169f-116">Nas configurações de indicador, clique em **aplicativo avançado**e em **Adicionar um aplicativo avançado**</span><span class="sxs-lookup"><span data-stu-id="3169f-116">In the bookmark settings, click **Power App**, and then click **Add a Power App**</span></span>
    
5. <span data-ttu-id="3169f-117">Insira ou cole a ID do aplicativo</span><span class="sxs-lookup"><span data-stu-id="3169f-117">Enter or paste the App ID</span></span>
    
    <span data-ttu-id="3169f-118">A altura e a largura são automaticamente adicionadas.</span><span class="sxs-lookup"><span data-stu-id="3169f-118">The height and width are automatically added.</span></span> <span data-ttu-id="3169f-119">Os indicadores podem dar suporte a orientações retrato e paisagem, mas atualmente o tamanho não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="3169f-119">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="3169f-120">A visualização do indicador mostra como o PowerApp será exibido no resultado do indicador</span><span class="sxs-lookup"><span data-stu-id="3169f-120">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="3169f-121">O PowerApp na visualização é totalmente funcional para facilitar o teste e o uso.</span><span class="sxs-lookup"><span data-stu-id="3169f-121">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="3169f-122">Clique em **publicar**</span><span class="sxs-lookup"><span data-stu-id="3169f-122">Click **Publish**</span></span>
    
<span data-ttu-id="3169f-123">Quando um usuário autorizado da Microsoft Search pesquisa no Bing para qualquer uma das palavras-chave ou reservadas do indicador, o PowerApp aparecerá no resultado do indicador.</span><span class="sxs-lookup"><span data-stu-id="3169f-123">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>

  

