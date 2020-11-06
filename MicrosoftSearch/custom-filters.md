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
ms.openlocfilehash: 75273035a7825683f626464df7bbc8e294b41b6f
ms.sourcegitcommit: 59435698bece013ae64ca2a68c43455ca10e3fdf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48927375"
---
# <a name="create-custom-filters"></a><span data-ttu-id="edb50-103">Criar filtros personalizados</span><span class="sxs-lookup"><span data-stu-id="edb50-103">Create custom Filters</span></span>

<span data-ttu-id="edb50-104">Você pode criar filtros para personalizar a experiência de pesquisa que os usuários veem quando pesquisam no Microsoft [SharePoint](https://sharepoint.com/), no Microsoft [Office](https://office.com)e no Microsoft Search no [Bing](https://bing.com).</span><span class="sxs-lookup"><span data-stu-id="edb50-104">You can create filters to customize the search experience that users see when they search in Microsoft [SharePoint](https://sharepoint.com/), Microsoft [Office](https://office.com), and Microsoft Search in [Bing](https://bing.com).</span></span> <span data-ttu-id="edb50-105">Filtros permite que os usuários aprimorem rapidamente o conjunto de resultados de suas consultas de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="edb50-105">Filters lets users quickly refine the set of results from their search query.</span></span>

<span data-ttu-id="edb50-106">Um filtro personalizado pode ser criado dentro de um vertical com base em uma propriedade de conexão.</span><span class="sxs-lookup"><span data-stu-id="edb50-106">A custom filter can be created inside a vertical based on a connection property.</span></span> <span data-ttu-id="edb50-107">Por exemplo, você pode criar um filtro **publicado na** conexão do ServiceNow dentro de uma vertical personalizada.</span><span class="sxs-lookup"><span data-stu-id="edb50-107">For example, you can create a **Published On** filter for ServiceNow connection inside a custom vertical.</span></span>

## <a name="things-to-consider"></a><span data-ttu-id="edb50-108">Itens a considerar</span><span class="sxs-lookup"><span data-stu-id="edb50-108">Things to consider</span></span>

1. <span data-ttu-id="edb50-109">Para criar um filtro personalizado na fonte de conteúdo de conexão, são fornecidas algumas capacidades adicionais:</span><span class="sxs-lookup"><span data-stu-id="edb50-109">For creating custom filter on connection content source, some additional capabilities are provided:</span></span>
- <span data-ttu-id="edb50-110">Você também pode criar um filtro em um alias para propriedades de origem do conector</span><span class="sxs-lookup"><span data-stu-id="edb50-110">You can also create filter on an alias to connector source properties</span></span>
- <span data-ttu-id="edb50-111">Caso a vertical tenha várias conexões, você pode criar um filtro comum entre essas conexões.</span><span class="sxs-lookup"><span data-stu-id="edb50-111">In case your vertical has multiple connections then you can create a common filter across these connections.</span></span> <span data-ttu-id="edb50-112">Isso pode ser feito criando o filtro em um alias comum que faz o alias de propriedades de origem entre diferentes conexões.</span><span class="sxs-lookup"><span data-stu-id="edb50-112">This can be done by creating the filter on an common alias which aliases source properties across across different connections.</span></span> <span data-ttu-id="edb50-113">Por exemplo, você pode criar um filtro de **autor** através de um & uma conexão do JIRA criando aliases da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="edb50-113">For example you can create an **Author** filter across a ServiceNow & a Jira connection by creating aliases as follows:</span></span>

| <span data-ttu-id="edb50-114">Connection</span><span class="sxs-lookup"><span data-stu-id="edb50-114">Connection</span></span> | <span data-ttu-id="edb50-115">Propriedade</span><span class="sxs-lookup"><span data-stu-id="edb50-115">Property</span></span> | <span data-ttu-id="edb50-116">Alias</span><span class="sxs-lookup"><span data-stu-id="edb50-116">Alias</span></span> |
| --- | --- | --- |
| <span data-ttu-id="edb50-117">Serviço agora</span><span class="sxs-lookup"><span data-stu-id="edb50-117">Service Now</span></span> | <span data-ttu-id="edb50-118">Proprietário</span><span class="sxs-lookup"><span data-stu-id="edb50-118">Owner</span></span> | <span data-ttu-id="edb50-119">Autor</span><span class="sxs-lookup"><span data-stu-id="edb50-119">Author</span></span> |
| <span data-ttu-id="edb50-120">Jira</span><span class="sxs-lookup"><span data-stu-id="edb50-120">Jira</span></span> | <span data-ttu-id="edb50-121">Publisher</span><span class="sxs-lookup"><span data-stu-id="edb50-121">Publisher</span></span> | <span data-ttu-id="edb50-122">Autor</span><span class="sxs-lookup"><span data-stu-id="edb50-122">Author</span></span> |

2. <span data-ttu-id="edb50-123">Há filtros no escopo da vertical.</span><span class="sxs-lookup"><span data-stu-id="edb50-123">Filters exist within the scope of the vertical.</span></span> <span data-ttu-id="edb50-124">Excluí</span><span class="sxs-lookup"><span data-stu-id="edb50-124">Hence,</span></span>  
- <span data-ttu-id="edb50-125">Se um filtro for criado em uma vertical que está no nível organizacional, o filtro só poderá ser visto no nível organizacional</span><span class="sxs-lookup"><span data-stu-id="edb50-125">If a filter is created in a vertical which is at organizational level, then the filter would only be visible at the organizational level</span></span>
- <span data-ttu-id="edb50-126">Se um filtro for criado em uma vertical que está no nível do site, o filtro só poderá ser visto no nível do site.</span><span class="sxs-lookup"><span data-stu-id="edb50-126">If a filter is created in a vertical which is at site level, then the filter would only be visible at the site level.</span></span>

## <a name="steps-to-create-custom-filter"></a><span data-ttu-id="edb50-127">Etapas para criar um filtro personalizado</span><span class="sxs-lookup"><span data-stu-id="edb50-127">Steps to Create custom filter</span></span>

### <a name="create-filter-in-organizational-level-vertical"></a><span data-ttu-id="edb50-128">Criar filtro no nível organizacional vertical:</span><span class="sxs-lookup"><span data-stu-id="edb50-128">Create filter in organizational level vertical:</span></span>

<span data-ttu-id="edb50-129">Para criar um filtro na pesquisa da Microsoft, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="edb50-129">To create a filter on Microsoft search follow these steps:</span></span>

1. <span data-ttu-id="edb50-130">No centro de administração do Microsoft 365, vá para a página [vertical](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) .</span><span class="sxs-lookup"><span data-stu-id="edb50-130">In the Microsoft 365 admin center, go to the [Verticals](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) page.</span></span>
2. <span data-ttu-id="edb50-131">Criar/editar a vertical na qual você deseja criar o filtro</span><span class="sxs-lookup"><span data-stu-id="edb50-131">Create/Edit the vertical in which you want to create the filter</span></span>
3. <span data-ttu-id="edb50-132">Navegue até a etapa ' filtros ' no assistente</span><span class="sxs-lookup"><span data-stu-id="edb50-132">Navigate to the 'Filters' step in the wizard</span></span>
4. <span data-ttu-id="edb50-133">Clique em "Adicionar filtro" e comece após adicionar filtros, você pode revisar e salvar a vertical.</span><span class="sxs-lookup"><span data-stu-id="edb50-133">Click on 'Add Filter' and get started After adding filters, you can review and save the vertical.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="edb50-134">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="edb50-134">Known Limitations</span></span>

1. <span data-ttu-id="edb50-135">No momento, você pode criar filtros somente nas propriedades gerenciadas de tipo de data & de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="edb50-135">You can currently create filters only on String & Date type managed properties.</span></span>
2. <span data-ttu-id="edb50-136">Não é possível criar filtros hierárquicos</span><span class="sxs-lookup"><span data-stu-id="edb50-136">You cannot create hierarchical filters</span></span>

## <a name="resources"></a><span data-ttu-id="edb50-137">Recursos</span><span class="sxs-lookup"><span data-stu-id="edb50-137">Resources</span></span>

[<span data-ttu-id="edb50-138">Personalizar página de resultados de pesquisa</span><span class="sxs-lookup"><span data-stu-id="edb50-138">Customize search result page</span></span>](customize-search-page.md)