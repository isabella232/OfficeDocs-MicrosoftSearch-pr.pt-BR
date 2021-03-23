---
title: Conector do MediaWiki Graph para Pesquisa da Microsoft
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector do MediaWiki Graph para a Pesquisa da Microsoft
ms.openlocfilehash: 5922cf76aa112430f9f6e857066acd054182058c
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031688"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a><span data-ttu-id="8be4c-103">Conector MediaWiki Graph</span><span class="sxs-lookup"><span data-stu-id="8be4c-103">MediaWiki Graph connector</span></span>

<span data-ttu-id="8be4c-104">O conector MediaWiki Graph permite que sua organização descubra e indexe dados de um wiki criado usando o software MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="8be4c-104">The MediaWiki Graph connector allows your organization to discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="8be4c-105">Esse conector indexa o conteúdo especificado na Pesquisa da Microsoft e oferece suporte a rastreamentos periódicos para manter o índice atualizado.</span><span class="sxs-lookup"><span data-stu-id="8be4c-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

> [!NOTE]
> <span data-ttu-id="8be4c-106">Leia o [**artigo Instalação do conector do Graph**](configure-connector.md) para entender as instruções gerais de configuração dos conectores do Graph.</span><span class="sxs-lookup"><span data-stu-id="8be4c-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="8be4c-107">Este artigo é para qualquer pessoa que configure, executa e monitore um conector do MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="8be4c-107">This article is for anyone who configures, runs, and monitors a MediaWiki Graph connector.</span></span> <span data-ttu-id="8be4c-108">Ele complementa o processo de instalação geral e mostra instruções que se aplicam somente ao conector do MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="8be4c-108">It supplements the general setup process, and shows instructions that apply only for the MediaWiki Graph connector.</span></span> <span data-ttu-id="8be4c-109">Este artigo também inclui informações sobre [Limitações.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="8be4c-109">This article also includes information about [Limitations](#limitations).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="8be4c-110">Etapa 1: Adicionar um conector graph no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8be4c-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="8be4c-111">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="8be4c-111">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="8be4c-112">Etapa 2: nomear a conexão</span><span class="sxs-lookup"><span data-stu-id="8be4c-112">Step 2: Name the connection</span></span>

<span data-ttu-id="8be4c-113">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="8be4c-113">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="8be4c-114">Etapa 3: Configurar as configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="8be4c-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="8be4c-115">Insira sua **URL wiki** e escolha o tipo **autenticação** no menu suspenso de opções.</span><span class="sxs-lookup"><span data-stu-id="8be4c-115">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="8be4c-116">As opções são **None**, **Basic** e **OAuth 2.0 AAD**.</span><span class="sxs-lookup"><span data-stu-id="8be4c-116">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="8be4c-117">Se você escolher **Basic como** o tipo de Autenticação, precisará fornecer o **Nome** de Usuário e Senha **para** o wiki.</span><span class="sxs-lookup"><span data-stu-id="8be4c-117">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="8be4c-118">Se você escolher **OAuth 2.0 AAD** como o tipo de Autenticação, precisará fornecer a **ID** de Recurso da instalação wiki.</span><span class="sxs-lookup"><span data-stu-id="8be4c-118">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="8be4c-119">Você também precisará fornecer a **ID do Cliente** e o **segredo do** cliente gerado na página de registro do Aplicativo AAD.</span><span class="sxs-lookup"><span data-stu-id="8be4c-119">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="8be4c-120">Etapa 4: Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="8be4c-120">Step 4: Manage search permissions</span></span>

<span data-ttu-id="8be4c-121">O conector MediaWiki só dá suporte a permissões de pesquisa visíveis para **Todos.**</span><span class="sxs-lookup"><span data-stu-id="8be4c-121">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="8be4c-122">Os dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários na organização.</span><span class="sxs-lookup"><span data-stu-id="8be4c-122">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="8be4c-123">Etapa 5: Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="8be4c-123">Step 5: Assign property labels</span></span>

<span data-ttu-id="8be4c-124">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="8be4c-124">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="8be4c-125">Etapa 6: Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="8be4c-125">Step 6: Manage schema</span></span>

<span data-ttu-id="8be4c-126">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="8be4c-126">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="8be4c-127">Etapa 7: Escolher configurações de atualização</span><span class="sxs-lookup"><span data-stu-id="8be4c-127">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="8be4c-128">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="8be4c-128">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="8be4c-129">Etapa 8: Revisar conexão</span><span class="sxs-lookup"><span data-stu-id="8be4c-129">Step 8: Review connection</span></span>

<span data-ttu-id="8be4c-130">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="8be4c-130">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="8be4c-131">Limitações</span><span class="sxs-lookup"><span data-stu-id="8be4c-131">Limitations</span></span>

<span data-ttu-id="8be4c-132">O conector MediaWiki tem essas limitações na versão de visualização:</span><span class="sxs-lookup"><span data-stu-id="8be4c-132">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="8be4c-133">Oferece suporte apenas a wikis baseados em nuvem.</span><span class="sxs-lookup"><span data-stu-id="8be4c-133">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="8be4c-134">Oferece suporte apenas ao Basic ou ao OAuth 2.0 com autenticação do Azure Active Directory ou do Azure.</span><span class="sxs-lookup"><span data-stu-id="8be4c-134">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="8be4c-135">Não dá suporte à seleção de namespace para indexação.</span><span class="sxs-lookup"><span data-stu-id="8be4c-135">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="8be4c-136">Indexa somente namespaces Main, Category e File.</span><span class="sxs-lookup"><span data-stu-id="8be4c-136">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="8be4c-137">Não dá suporte a Listas de Controle de Acesso (ACLs).</span><span class="sxs-lookup"><span data-stu-id="8be4c-137">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="8be4c-138">Assim, as páginas indexadas ficam visíveis para todos os usuários na organização.</span><span class="sxs-lookup"><span data-stu-id="8be4c-138">Thus, indexed pages are visible to all users in the organization.</span></span>