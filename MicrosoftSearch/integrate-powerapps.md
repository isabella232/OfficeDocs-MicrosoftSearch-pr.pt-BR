---
title: Integrar PowerApps
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
description: Incluir aplicativos baseados em navegador nos resultados de indicadores para o Microsoft Search
ms.openlocfilehash: d8d9d099848e719c86e0f3cadee330263566d243
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378401"
---
# <a name="integrate-powerapps"></a><span data-ttu-id="b02b1-103">Integrar PowerApps</span><span class="sxs-lookup"><span data-stu-id="b02b1-103">Integrate PowerApps</span></span>

<span data-ttu-id="b02b1-p101">Ajuda seus usuários a concluir tarefas, como inserir o tempo de férias ou relatórios de despesas integrando PowerApps existente em seus indicadores. PowerApps integrados aparecem dentro de um resultado de indicador, eliminando a necessidade de ir para um site diferente ou abrir uma ferramenta separada, que os tempos de gravações e esforço.</span><span class="sxs-lookup"><span data-stu-id="b02b1-p101">Help your users complete tasks, such as entering vacation time or reporting expenses by integrating existing PowerApps into your bookmarks. Integrated PowerApps appear within a bookmark result, eliminating the need to go to a different site or open a separate tool, which saves times and effort.</span></span>
  
## <a name="what-are-powerapps"></a><span data-ttu-id="b02b1-106">Cite PowerApps.</span><span class="sxs-lookup"><span data-stu-id="b02b1-106">What are PowerApps?</span></span>

<span data-ttu-id="b02b1-p102">PowerApps é um serviço que permite que você crie aplicativos de negócios que são executados em um navegador ou em um celular ou tablet com nenhuma experiência de codificação necessária. Saiba Mais:</span><span class="sxs-lookup"><span data-stu-id="b02b1-p102">PowerApps is a service that lets you build business apps that run in a browser or on a phone or tablet with no coding experience required. Learn more:</span></span>
  
- [<span data-ttu-id="b02b1-109">Aprendizado</span><span class="sxs-lookup"><span data-stu-id="b02b1-109">Guided Learning</span></span>](https://docs.microsoft.com/en-us/learn/browse/?products=powerapps)
    
- [<span data-ttu-id="b02b1-110">Documentação</span><span class="sxs-lookup"><span data-stu-id="b02b1-110">Documentation</span></span>](https://docs.microsoft.com/en-us/powerapps/)
    
## <a name="add-a-powerapp-to-a-bookmark"></a><span data-ttu-id="b02b1-111">Adicionar um PowerApp para um indicador</span><span class="sxs-lookup"><span data-stu-id="b02b1-111">Add a PowerApp to a bookmark</span></span>

<span data-ttu-id="b02b1-112">PowerApps trabalhar em qualquer navegador e em qualquer dispositivo e levar menos de um minuto para adicionar.</span><span class="sxs-lookup"><span data-stu-id="b02b1-112">PowerApps work in any browser and on any device and take less than a minute to add.</span></span>
  
1. <span data-ttu-id="b02b1-113">[Localizar a identificação de aplicativo para o PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que você deseja integrar</span><span class="sxs-lookup"><span data-stu-id="b02b1-113">[Find the App ID for the PowerApp](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) you want to integrate</span></span> 
    
2. <span data-ttu-id="b02b1-114">No portal do Microsoft SearchAdmin, vá para **indicadores**</span><span class="sxs-lookup"><span data-stu-id="b02b1-114">In the Microsoft SearchAdmin portal, go to **Bookmarks**</span></span>
    
3. <span data-ttu-id="b02b1-115">Adicionar um indicador ou localizar um indicador existente que você deseja adicionar um PowerApp para</span><span class="sxs-lookup"><span data-stu-id="b02b1-115">Add a bookmark or find an existing bookmark that you want to add a PowerApp to</span></span>
    
4. <span data-ttu-id="b02b1-116">Nas configurações do indicador, clique em **Aplicativo Power**e, em seguida, clique em **Adicionar um aplicativo de alimentação**</span><span class="sxs-lookup"><span data-stu-id="b02b1-116">In the bookmark settings, click **Power App**, and then click **Add a Power App**</span></span>
    
5. <span data-ttu-id="b02b1-117">Digite ou cole a ID de aplicativo</span><span class="sxs-lookup"><span data-stu-id="b02b1-117">Enter or paste the App ID</span></span>
    
    <span data-ttu-id="b02b1-p103">A altura e largura são adicionados automaticamente. Indicadores podem suportar orientações retrato e paisagem, mas atualmente o tamanho não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="b02b1-p103">The height and width are automatically added. Bookmarks can support both portrait and landscape orientations, but currently the size can't be changed.</span></span>
    
6. <span data-ttu-id="b02b1-120">A visualização de indicador mostra como o PowerApp será exibido no resultado do indicador</span><span class="sxs-lookup"><span data-stu-id="b02b1-120">The bookmark preview shows how the PowerApp will appear in the bookmark result</span></span>
    
    <span data-ttu-id="b02b1-121">O PowerApp na visualização é totalmente funcional para tornar mais fácil testar e usar.</span><span class="sxs-lookup"><span data-stu-id="b02b1-121">The PowerApp in the preview is fully functional to make it easy to test and use.</span></span>
    
7. <span data-ttu-id="b02b1-122">Clique em **Publicar**</span><span class="sxs-lookup"><span data-stu-id="b02b1-122">Click **Publish**</span></span>
    
<span data-ttu-id="b02b1-123">Quando um usuário autorizado da Microsoft Search pesquisa em Bing para qualquer uma das palavras-chave ou palavras-chave reservadas do indicador, o PowerApp aparecerá no resultado do indicador.</span><span class="sxs-lookup"><span data-stu-id="b02b1-123">When an authorized Microsoft Search user searches on Bing for any of the bookmark's keywords or reserved keywords, the PowerApp will appear in the bookmark result.</span></span>

  

