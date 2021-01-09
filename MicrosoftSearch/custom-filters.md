---
title: Gerenciar filtros personalizados
ms.author: rodhb
author: rodhb
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gerenciar filtros personalizados
ms.openlocfilehash: a050921058eac50d7588f1e71f5b0f56cc8e5752
ms.sourcegitcommit: a86265684871da86562a76c4961d0a6c1869f517
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790325"
---
# <a name="manage-custom-filters"></a><span data-ttu-id="63366-103">Gerenciar filtros personalizados</span><span class="sxs-lookup"><span data-stu-id="63366-103">Manage custom filters</span></span>

<span data-ttu-id="63366-104">Você pode usar filtros para personalizar a experiência da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="63366-104">You can use filters to customize the Microsoft Search experience.</span></span> <span data-ttu-id="63366-105">Os filtros permitem que os usuários refinem rapidamente o conjunto de resultados de sua consulta de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="63366-105">Filters let users quickly refine the set of results from their search query.</span></span>

<span data-ttu-id="63366-106">Um filtro personalizado pode ser criado dentro de uma vertical com base em uma propriedade de conexão.</span><span class="sxs-lookup"><span data-stu-id="63366-106">A custom filter can be created inside a vertical based on a connection property.</span></span> <span data-ttu-id="63366-107">Por exemplo, você pode criar um filtro **Publicado em** para conexão ServiceNow dentro de uma vertical.</span><span class="sxs-lookup"><span data-stu-id="63366-107">For example, you can create a **Published On** filter for ServiceNow connection inside a vertical.</span></span>

## <a name="create-a-filter-in-an-organizational-level-vertical"></a><span data-ttu-id="63366-108">Criar um filtro em um nível organizacional vertical</span><span class="sxs-lookup"><span data-stu-id="63366-108">Create a filter in an organizational level vertical</span></span>

<span data-ttu-id="63366-109">Para criar um filtro na pesquisa da Microsoft, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="63366-109">To create a filter on Microsoft search follow these steps:</span></span>

1. <span data-ttu-id="63366-110">No centro de administração do Microsoft 365, vá para [Verticais.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)</span><span class="sxs-lookup"><span data-stu-id="63366-110">In the Microsoft 365 admin center, go to [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).</span></span>
1. <span data-ttu-id="63366-111">Criar/editar a vertical na qual você deseja criar o filtro</span><span class="sxs-lookup"><span data-stu-id="63366-111">Create/Edit the vertical in which you want to create the filter</span></span>
1. <span data-ttu-id="63366-112">Navegue até a etapa "Filtros" no assistente</span><span class="sxs-lookup"><span data-stu-id="63366-112">Navigate to the 'Filters' step in the wizard</span></span>
1. <span data-ttu-id="63366-113">Clique em "Adicionar Filtro" e começar</span><span class="sxs-lookup"><span data-stu-id="63366-113">Click on 'Add Filter' and get started</span></span>
1. <span data-ttu-id="63366-114">Depois de adicionar filtros, você pode revisar e salvar a vertical.</span><span class="sxs-lookup"><span data-stu-id="63366-114">After adding filters, you can review and save the vertical.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="63366-115">Itens a considerar</span><span class="sxs-lookup"><span data-stu-id="63366-115">Things to consider</span></span>

1. <span data-ttu-id="63366-116">Existem recursos adicionais de filtro no conteúdo da conexão.</span><span class="sxs-lookup"><span data-stu-id="63366-116">Additional filter capabilities exist on connection content.</span></span>

    - <span data-ttu-id="63366-117">Você também pode criar filtro em um alias para propriedades de origem do conector</span><span class="sxs-lookup"><span data-stu-id="63366-117">You can also create filter on an alias to connector source properties</span></span>
    - <span data-ttu-id="63366-118">Se uma vertical tiver várias conexões, você poderá criar um filtro comum entre essas conexões.</span><span class="sxs-lookup"><span data-stu-id="63366-118">If a vertical has multiple connections, you can create a common filter across these connections.</span></span> <span data-ttu-id="63366-119">Isso pode ser feito criando o filtro em um alias comum que aliases propriedades de origem entre as diferentes conexões.</span><span class="sxs-lookup"><span data-stu-id="63366-119">This can be done by creating the filter on an common alias which aliases source properties across across the different connections.</span></span> <span data-ttu-id="63366-120">Por exemplo, você pode criar um **filtro Autor** em uma conexão ServiceNow e Jira criando aliases da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="63366-120">For example you can create an **Author** filter across a ServiceNow and a Jira connection by creating aliases as follows:</span></span>

    | <span data-ttu-id="63366-121">Connection</span><span class="sxs-lookup"><span data-stu-id="63366-121">Connection</span></span> | <span data-ttu-id="63366-122">Propriedade</span><span class="sxs-lookup"><span data-stu-id="63366-122">Property</span></span> | <span data-ttu-id="63366-123">Alias</span><span class="sxs-lookup"><span data-stu-id="63366-123">Alias</span></span> |
    | --- | --- | --- |
    | <span data-ttu-id="63366-124">Serviço Agora</span><span class="sxs-lookup"><span data-stu-id="63366-124">Service Now</span></span> | <span data-ttu-id="63366-125">Proprietário</span><span class="sxs-lookup"><span data-stu-id="63366-125">Owner</span></span> | <span data-ttu-id="63366-126">Autor</span><span class="sxs-lookup"><span data-stu-id="63366-126">Author</span></span> |
    | <span data-ttu-id="63366-127">Jira</span><span class="sxs-lookup"><span data-stu-id="63366-127">Jira</span></span> | <span data-ttu-id="63366-128">Publisher</span><span class="sxs-lookup"><span data-stu-id="63366-128">Publisher</span></span> | <span data-ttu-id="63366-129">Autor</span><span class="sxs-lookup"><span data-stu-id="63366-129">Author</span></span> |

1. <span data-ttu-id="63366-130">Existem filtros dentro do escopo de uma vertical.</span><span class="sxs-lookup"><span data-stu-id="63366-130">Filters exist within the scope of a vertical.</span></span>

    - <span data-ttu-id="63366-131">Se um filtro for criado em uma vertical que está no nível organizacional, o filtro só ficará visível no nível organizacional</span><span class="sxs-lookup"><span data-stu-id="63366-131">If a filter is created in a vertical which is at organizational level, then the filter would only be visible at the organizational level</span></span>
    - <span data-ttu-id="63366-132">Se um filtro for criado em uma vertical que está no nível do site, o filtro só ficará visível no nível do site.</span><span class="sxs-lookup"><span data-stu-id="63366-132">If a filter is created in a vertical which is at site level, then the filter would only be visible at the site level.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="63366-133">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="63366-133">Known Limitations</span></span>

1. <span data-ttu-id="63366-134">Atualmente, você só pode criar filtros em propriedades gerenciadas de tipo de & de caracteres.</span><span class="sxs-lookup"><span data-stu-id="63366-134">You can currently create filters only on string & date type managed properties.</span></span>
1. <span data-ttu-id="63366-135">Não é possível criar filtros hierárquicos.</span><span class="sxs-lookup"><span data-stu-id="63366-135">You cannot create hierarchical filters.</span></span>

## <a name="resources"></a><span data-ttu-id="63366-136">Recursos</span><span class="sxs-lookup"><span data-stu-id="63366-136">Resources</span></span>

[<span data-ttu-id="63366-137">Gerenciar verticais e tipos de resultados</span><span class="sxs-lookup"><span data-stu-id="63366-137">Manage verticals and result types</span></span>](customize-search-page.md)
