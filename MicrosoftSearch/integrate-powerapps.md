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
ROBOTS: NOINDEX
description: Incluir aplicativos baseados em navegador nos resultados de indicadores da Pesquisa da Microsoft
ms.openlocfilehash: 1f4cf7512ee176015537be2fbe2f59429cde6578
ms.sourcegitcommit: fe7f3dae4edba97071a4d127e8a27bdf4fa00d81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2019
ms.locfileid: "34727965"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="deb01-103">Integrar o PowerApps</span><span class="sxs-lookup"><span data-stu-id="deb01-103">Integrate PowerApps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="deb01-104">Este artigo se aplica à Pesquisa da Microsoft no portal de administração do Bing.</span><span class="sxs-lookup"><span data-stu-id="deb01-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="deb01-105">Estamos movendo o portal para o centro de administração do Microsoft 365 e, em seguida, ele será removido.</span><span class="sxs-lookup"><span data-stu-id="deb01-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="deb01-106">Recomendamos que você use o centro de administração do Microsoft 365 para começar.</span><span class="sxs-lookup"><span data-stu-id="deb01-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> [<span data-ttu-id="deb01-107">Visão geral da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="deb01-107">Overview of Microsoft Search</span></span>](overview-microsoft-search.md)
    
<span data-ttu-id="deb01-108">Ajude os usuários a concluir as tarefas, como inserir período de férias ou relatórios de despesas por meio da integração de PowerApps existentes em seus indicadores.</span><span class="sxs-lookup"><span data-stu-id="deb01-108">Help your users complete tasks, such as entering vacation time or reporting expenses, by adding existing PowerApps to your bookmarks.</span></span> <span data-ttu-id="deb01-109">PowerApps integrados aparecem em um resultado de indicador, eliminando a necessidade de ir para outro site ou de abrir uma ferramenta separada, o que economiza tempo e esforço.</span><span class="sxs-lookup"><span data-stu-id="deb01-109">Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="deb01-110">O que são PowerApps?</span><span class="sxs-lookup"><span data-stu-id="deb01-110">What are PowerApps?</span></span>

<span data-ttu-id="deb01-111">PowerApps é um serviço que permite criar aplicativos de negócios que são executados em um navegador, um telefone ou tablet sem necessidade de nenhuma experiência de codificação.</span><span class="sxs-lookup"><span data-stu-id="deb01-111">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required.</span></span> <span data-ttu-id="deb01-112">Saiba mais:</span><span class="sxs-lookup"><span data-stu-id="deb01-112">Learn more:</span></span>
  
- <span data-ttu-id="deb01-113">
  [Aprendizagem Orientada](https://docs.microsoft.com/pt-BR/learn/browse/?products=powerapps)</span><span class="sxs-lookup"><span data-stu-id="deb01-113">[Guided Learning](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)</span></span>
    
- <span data-ttu-id="deb01-114">
  [Documentação](https://docs.microsoft.com/pt-BR/powerapps/)</span><span class="sxs-lookup"><span data-stu-id="deb01-114">[Documentation](https://docs.microsoft.com/en-us/powerapps/)</span></span>
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="deb01-115">Adicionar um PowerApp a um indicador</span><span class="sxs-lookup"><span data-stu-id="deb01-115">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="deb01-116">PowerApps funcionam em qualquer navegador e em qualquer dispositivo, e leva menos de um minuto para adicioná-los.</span><span class="sxs-lookup"><span data-stu-id="deb01-116">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="deb01-117">
  [Encontre o ID do aplicativo para o PowerApp](https://docs.microsoft.com/pt-BR/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que você deseja integrar</span><span class="sxs-lookup"><span data-stu-id="deb01-117">Find the [App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) that you want to add.</span></span> 
    
2. <span data-ttu-id="deb01-118">No portal de administração da Pesquisa da Microsoft, vá para **Indicadores**</span><span class="sxs-lookup"><span data-stu-id="deb01-118">In the Microsoft Search Admin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="deb01-119">Adicionar um indicador ou encontrar um indicador existente ao qual você deseja adicionar um PowerApp</span><span class="sxs-lookup"><span data-stu-id="deb01-119">Add a bookmark or find an existing bookmark that you want to add a PowerApp to.</span></span>
    
4. <span data-ttu-id="deb01-120">Nas configurações de indicador, clique em **PowerApp**e, em seguida, em **Adicionar um PowerApp**</span><span class="sxs-lookup"><span data-stu-id="deb01-120">In Bookmark settings, select Power App, and then Add a Power App.</span></span>
    
5. <span data-ttu-id="deb01-121">Insira ou cole o ID do aplicativo</span><span class="sxs-lookup"><span data-stu-id="deb01-121">Enter or paste the App ID.</span></span>
    
    <span data-ttu-id="deb01-122">A altura e largura são adicionadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="deb01-122">The height and width are automatically adjusted.</span></span> <span data-ttu-id="deb01-123">Os indicadores são compatíveis com orientações tipo retrato e paisagem; porém, no momento, o tamanho não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="deb01-123">Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="deb01-124">A visualização do indicador mostra como o PowerApp aparecerá no resultado do indicador</span><span class="sxs-lookup"><span data-stu-id="deb01-124">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="deb01-125">O PowerApp na visualização é totalmente funcional para facilitar o teste e o uso.</span><span class="sxs-lookup"><span data-stu-id="deb01-125">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="deb01-126">Clique em **Publicar**</span><span class="sxs-lookup"><span data-stu-id="deb01-126">Click **Publish this draft**.</span></span>
    
<span data-ttu-id="deb01-127">Quando um usuário autorizado da Pesquisa da Microsoft pesquisa no Bing por qualquer uma das palavras-chave do indicador ou palavras-chave reservadas, o PowerApp aparecerá no resultado do indicador.</span><span class="sxs-lookup"><span data-stu-id="deb01-127">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>

  

