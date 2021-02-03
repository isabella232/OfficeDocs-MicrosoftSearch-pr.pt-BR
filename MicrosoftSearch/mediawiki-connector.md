---
title: Conector MediaWiki Graph para a Pesquisa da Microsoft
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector MediaWiki Graph para a Pesquisa da Microsoft
ms.openlocfilehash: 9d9d7a1ef9aeaba079f8cccef1ec4a4836768e8d
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084979"
---
<!---Previous ms.author: monaray --->

# <a name="mediawiki-graph-connector"></a><span data-ttu-id="95432-103">Conector MediaWiki Graph</span><span class="sxs-lookup"><span data-stu-id="95432-103">MediaWiki Graph connector</span></span>

<span data-ttu-id="95432-104">O conector MediaWiki Graph permite que sua organização descubra e indexe dados de um wiki criado usando o software MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="95432-104">The MediaWiki Graph connector allows your organization to discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="95432-105">Esse conector indexa o conteúdo especificado na Pesquisa da Microsoft e oferece suporte a rastreamentos periódicos para manter o índice atualizado.</span><span class="sxs-lookup"><span data-stu-id="95432-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

> [!NOTE]
> <span data-ttu-id="95432-106">Leia o [**artigo Configuração do seu conector do Graph**](configure-connector.md) para entender o processo geral de configuração de conectores do Graph.</span><span class="sxs-lookup"><span data-stu-id="95432-106">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

<span data-ttu-id="95432-107">Este artigo é para qualquer pessoa que configure, executa e monitore um conector do ServiceNow Graph.</span><span class="sxs-lookup"><span data-stu-id="95432-107">This article is for anyone who configures, runs, and monitors a ServiceNow Graph connector.</span></span> <span data-ttu-id="95432-108">Ele complementa o processo de instalação geral e mostra instruções que se aplicam somente ao conector MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="95432-108">It supplements the general setup process, and shows instructions that apply only for the MediaWiki Graph connector.</span></span> <span data-ttu-id="95432-109">Este artigo também inclui informações sobre [limitações.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="95432-109">This article also includes information about [Limitations](#limitations).</span></span>

<!---## Before you get started-->

<!---Insert "Before you get started" recommendations for this data source-->

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="95432-110">Etapa 1: Adicionar um conector do Graph no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="95432-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="95432-111">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="95432-111">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="95432-112">Etapa 2: Nomear a conexão</span><span class="sxs-lookup"><span data-stu-id="95432-112">Step 2: Name the connection</span></span>

<span data-ttu-id="95432-113">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="95432-113">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="95432-114">Etapa 3: Definir as configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="95432-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="95432-115">Insira sua **URL wiki** e escolha o tipo **de autenticação** no menu suspenso de opções.</span><span class="sxs-lookup"><span data-stu-id="95432-115">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="95432-116">As opções são **None**, **Basic** e **OAuth 2.0 AAD**.</span><span class="sxs-lookup"><span data-stu-id="95432-116">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="95432-117">Se você escolher **Básico** como o tipo de autenticação, será necessário fornecer o nome **de** usuário e **a** senha para o wiki.</span><span class="sxs-lookup"><span data-stu-id="95432-117">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="95432-118">Se você escolher **OAuth 2.0 AAD** como o tipo de autenticação, será necessário fornecer a **ID** de recurso da instalação wiki.</span><span class="sxs-lookup"><span data-stu-id="95432-118">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="95432-119">Você também precisará fornecer a **ID** do cliente e o segredo **do** cliente gerados na página de registro do aplicativo AAD.</span><span class="sxs-lookup"><span data-stu-id="95432-119">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="95432-120">Etapa 4: Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="95432-120">Step 4: Manage search permissions</span></span>

<span data-ttu-id="95432-121">O conector MediaWiki só dá suporte a permissões de pesquisa visíveis para **Todos.**</span><span class="sxs-lookup"><span data-stu-id="95432-121">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="95432-122">Os dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários na organização.</span><span class="sxs-lookup"><span data-stu-id="95432-122">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="95432-123">Etapa 5: Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="95432-123">Step 5: Assign property labels</span></span>

<span data-ttu-id="95432-124">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="95432-124">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="95432-125">Etapa 6: Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="95432-125">Step 6: Manage schema</span></span>

<span data-ttu-id="95432-126">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="95432-126">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="95432-127">Etapa 7: Escolher configurações de atualização</span><span class="sxs-lookup"><span data-stu-id="95432-127">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="95432-128">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="95432-128">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="95432-129">Etapa 8: Analisar a conexão</span><span class="sxs-lookup"><span data-stu-id="95432-129">Step 8: Review connection</span></span>

<span data-ttu-id="95432-130">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="95432-130">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="95432-131">Limitações</span><span class="sxs-lookup"><span data-stu-id="95432-131">Limitations</span></span>

<span data-ttu-id="95432-132">O conector MediaWiki tem estas limitações na versão de visualização:</span><span class="sxs-lookup"><span data-stu-id="95432-132">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="95432-133">Oferece suporte somente a wikis baseados em nuvem.</span><span class="sxs-lookup"><span data-stu-id="95432-133">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="95432-134">Dá suporte apenas ao Basic ou ao OAuth 2.0 com a autenticação do Azure Active Directory ou do Azure.</span><span class="sxs-lookup"><span data-stu-id="95432-134">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="95432-135">Não dá suporte à seleção de namespace para indexação.</span><span class="sxs-lookup"><span data-stu-id="95432-135">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="95432-136">Indexa apenas os namespaces Principal, Categoria e Arquivo.</span><span class="sxs-lookup"><span data-stu-id="95432-136">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="95432-137">Não dá suporte a ACLs (Listas de Controle de Acesso).</span><span class="sxs-lookup"><span data-stu-id="95432-137">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="95432-138">Assim, as páginas indexadas ficam visíveis para todos os usuários na organização.</span><span class="sxs-lookup"><span data-stu-id="95432-138">Thus, indexed pages are visible to all users in the organization.</span></span>
