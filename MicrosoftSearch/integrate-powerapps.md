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
description: Incluir aplicativos baseados em navegador nos resultados de indicadores da Pesquisa da Microsoft
ms.openlocfilehash: 96b409274e3fa06cef7dcc6f1c43360a3e6b9d34
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968370"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="7f2c3-103">Integrar o PowerApps</span><span class="sxs-lookup"><span data-stu-id="7f2c3-103">Integrate PowerApps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f2c3-104">As configurações da Pesquisa da Microsoft no Bing agora estão disponíveis no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7f2c3-104">Microsoft Search in Bing settings are now available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="7f2c3-105">Comece por [atribuir administradores de pesquisa](https://docs.microsoft.com/pt-BR/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) ao seu centro de administração.</span><span class="sxs-lookup"><span data-stu-id="7f2c3-105">Get started by [assigning search admins](https://docs.microsoft.com/en-us/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) in your admin center.</span></span>
    
<span data-ttu-id="7f2c3-106">Ajude os usuários a concluir as tarefas, como inserir tempo de férias ou relatórios de despesas por meio da integração de PowerApps existentes com seus indicadores.</span><span class="sxs-lookup"><span data-stu-id="7f2c3-106">Help your users complete tasks, such as entering vacation time or reporting expenses, by adding existing PowerApps to your bookmarks.</span></span> <span data-ttu-id="7f2c3-107">PowerApps integrados aparecem em um resultado de indicador, eliminando a necessidade de ir para outro site ou de abrir uma ferramenta separada, o que economiza tempo e esforço.</span><span class="sxs-lookup"><span data-stu-id="7f2c3-107">Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="7f2c3-108">O que são PowerApps?</span><span class="sxs-lookup"><span data-stu-id="7f2c3-108">What are PowerApps?</span></span>

<span data-ttu-id="7f2c3-109">PowerApps é um serviço que permite criar aplicativos de negócios que são executados em um navegador, um telefone ou tablet sem necessidade de nenhuma experiência de codificação.</span><span class="sxs-lookup"><span data-stu-id="7f2c3-109">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="7f2c3-110">Saiba mais:</span><span class="sxs-lookup"><span data-stu-id="7f2c3-110">Learn more:</span></span>
  
- <span data-ttu-id="7f2c3-111">
  [Aprendizagem Orientada](https://docs.microsoft.com/pt-BR/learn/browse/?products=powerapps)</span><span class="sxs-lookup"><span data-stu-id="7f2c3-111">[Guided Learning](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)</span></span>
    
- <span data-ttu-id="7f2c3-112">
  [Documentação](https://docs.microsoft.com/pt-BR/powerapps/)</span><span class="sxs-lookup"><span data-stu-id="7f2c3-112">[Documentation](https://docs.microsoft.com/en-us/powerapps/)</span></span>
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="7f2c3-113">Adicionar um PowerApp a um indicador</span><span class="sxs-lookup"><span data-stu-id="7f2c3-113">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="7f2c3-114">PowerApps funcionam em qualquer navegador e em qualquer dispositivo, e leva menos de um minuto para adicioná-los.</span><span class="sxs-lookup"><span data-stu-id="7f2c3-114">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="7f2c3-115">
  [Encontre o ID do aplicativo para o PowerApp](https://docs.microsoft.com/pt-BR/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que você deseja integrar</span><span class="sxs-lookup"><span data-stu-id="7f2c3-115">Find the [App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) that you want to add.</span></span> 
    
2. <span data-ttu-id="7f2c3-116">No portal de administração da Pesquisa da Microsoft, vá para **Indicadores**</span><span class="sxs-lookup"><span data-stu-id="7f2c3-116">In the Microsoft SearchAdmin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="7f2c3-117">Adicionar um indicador ou encontrar um indicador existente ao qual você deseja adicionar um PowerApp</span><span class="sxs-lookup"><span data-stu-id="7f2c3-117">Add a bookmark or find an existing bookmark that you want to add a PowerApp to.</span></span>
    
4. <span data-ttu-id="7f2c3-118">Nas configurações de indicador, clique em **PowerApp**e, em seguida, em **Adicionar um PowerApp**</span><span class="sxs-lookup"><span data-stu-id="7f2c3-118">In Bookmark settings, select Power App, and then Add a Power App.</span></span>
    
5. <span data-ttu-id="7f2c3-119">Insira ou cole o ID do aplicativo</span><span class="sxs-lookup"><span data-stu-id="7f2c3-119">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="7f2c3-120">A altura e largura são adicionadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7f2c3-120">The height and width are automatically adjusted.</span></span> <span data-ttu-id="7f2c3-121">Os indicadores são compatíveis com orientações tipo retrato e paisagem; porém, no momento, o tamanho não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="7f2c3-121">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="7f2c3-122">A visualização do indicador mostra como o PowerApp aparecerá no resultado do indicador</span><span class="sxs-lookup"><span data-stu-id="7f2c3-122">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="7f2c3-123">O PowerApp na visualização é totalmente funcional para facilitar o teste e o uso.</span><span class="sxs-lookup"><span data-stu-id="7f2c3-123">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="7f2c3-124">Clique em **Publicar**</span><span class="sxs-lookup"><span data-stu-id="7f2c3-124">Click **Publish this draft**.</span></span>
    
<span data-ttu-id="7f2c3-125">Quando um usuário autorizado da Pesquisa da Microsoft pesquisa no Bing por qualquer uma das palavras-chave do indicador ou palavras-chave reservadas, o PowerApp aparecerá no resultado do indicador.</span><span class="sxs-lookup"><span data-stu-id="7f2c3-125">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>

  

