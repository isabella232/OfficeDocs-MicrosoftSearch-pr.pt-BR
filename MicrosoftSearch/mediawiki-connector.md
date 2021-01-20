---
title: Conector MediaWiki para a Pesquisa da Microsoft
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector MediaWiki para a Pesquisa da Microsoft
ms.openlocfilehash: 7a22fcc84f6f435bf438aa027c42c76eb8be1eaf
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905944"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="e8b95-103">Conector MediaWiki</span><span class="sxs-lookup"><span data-stu-id="e8b95-103">MediaWiki connector</span></span>

<span data-ttu-id="e8b95-104">Com o conector MediaWiki, sua organização pode descobrir e indexar dados de um wiki criado usando o software MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="e8b95-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="e8b95-105">Esse conector indexa o conteúdo especificado na Pesquisa da Microsoft e oferece suporte a rastreamentos periódicos para manter o índice atualizado.</span><span class="sxs-lookup"><span data-stu-id="e8b95-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="e8b95-106">Este artigo é destinado a administradores do Microsoft 365 ou qualquer pessoa que configure, executa e monitore um conector MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="e8b95-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki Graph connector.</span></span> <span data-ttu-id="e8b95-107">Ele complementa as instruções gerais fornecidas no artigo [Configurar seu conector do Graph.](configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="e8b95-107">It supplements the general instructions provided in the [Set up your Graph connector](configure-connector.md) article.</span></span> <span data-ttu-id="e8b95-108">Se você ainda não tiver feito isso, leia todo o artigo Configurar seu conector do Graph para entender o processo de configuração geral.</span><span class="sxs-lookup"><span data-stu-id="e8b95-108">If you have not already done so, read the entire Set up your Graph connector article to understand the general setup process.</span></span>

<span data-ttu-id="e8b95-109">Cada etapa do processo de instalação é listada abaixo, juntamente com uma observação que indica que você deve seguir as instruções gerais de instalação OU outras instruções que se aplicam apenas aos conectores MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="e8b95-109">Each step in the setup process is listed below along with either a note that indicates you should follow the general setup instructions OR other instructions that apply to only MediaWiki Graph connectors.</span></span> <span data-ttu-id="e8b95-110">Este artigo também inclui informações sobre limitações [para](#limitations) conectores MediaWiki Graph.</span><span class="sxs-lookup"><span data-stu-id="e8b95-110">This article also includes information about [Limitations](#limitations) for MediaWiki Graph connectors.</span></span> 

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="e8b95-111">Etapa 1: adicionar um conector do Graph no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e8b95-111">Step 1: Add a Graph connector in the Microsoft 365 admin center.</span></span>
<span data-ttu-id="e8b95-112">Siga as instruções gerais de configuração.</span><span class="sxs-lookup"><span data-stu-id="e8b95-112">Follow the general setup instructions.</span></span>

## <a name="step-2-name-the-connection"></a><span data-ttu-id="e8b95-113">Etapa 2: Nomear a conexão.</span><span class="sxs-lookup"><span data-stu-id="e8b95-113">Step 2: Name the connection.</span></span>
<span data-ttu-id="e8b95-114">Siga as instruções gerais de configuração.</span><span class="sxs-lookup"><span data-stu-id="e8b95-114">Follow the general setup instructions.</span></span>
 
## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="e8b95-115">Etapa 3: Definir as configurações de conexão.</span><span class="sxs-lookup"><span data-stu-id="e8b95-115">Step 3: Configure the connection settings.</span></span>
<span data-ttu-id="e8b95-116">Insira sua **URL wiki** e escolha o tipo **de autenticação** no menu suspenso de opções.</span><span class="sxs-lookup"><span data-stu-id="e8b95-116">Enter your **Wiki URL** and choose the **Authentication type** from the drop-down menu of options.</span></span> <span data-ttu-id="e8b95-117">As opções são **None**, **Basic** e **OAuth 2.0 AAD**.</span><span class="sxs-lookup"><span data-stu-id="e8b95-117">The options are **None**, **Basic**, and **OAuth 2.0 AAD**.</span></span>

<span data-ttu-id="e8b95-118">Se você escolher **Básico** como o tipo de autenticação, será necessário fornecer o nome **de** usuário e **a** senha para o wiki.</span><span class="sxs-lookup"><span data-stu-id="e8b95-118">If you choose **Basic** as the Authentication type, you will need to provide the **Username** and **Password** for the wiki.</span></span>

<span data-ttu-id="e8b95-119">Se você escolher **OAuth 2.0 AAD** como o tipo de autenticação, será necessário fornecer a **ID** de recurso da instalação wiki.</span><span class="sxs-lookup"><span data-stu-id="e8b95-119">If you choose **OAuth 2.0 AAD** as the Authentication type, you will need to provide the **Resource ID** of the wiki installation.</span></span> <span data-ttu-id="e8b95-120">Você também precisará fornecer a **ID** do cliente e o segredo **do** cliente gerados na página de registro do aplicativo AAD.</span><span class="sxs-lookup"><span data-stu-id="e8b95-120">You will also need to provide the **Client ID** and **Client secret** generated on the AAD Application registration page.</span></span> 

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="e8b95-121">Etapa 4: Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="e8b95-121">Step 4: Manage search permissions</span></span>
<span data-ttu-id="e8b95-122">O conector MediaWiki só dá suporte a permissões de pesquisa visíveis para **Todos.**</span><span class="sxs-lookup"><span data-stu-id="e8b95-122">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="e8b95-123">Os dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários na organização.</span><span class="sxs-lookup"><span data-stu-id="e8b95-123">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="e8b95-124">Etapa 5: Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="e8b95-124">Step 5: Assign property labels</span></span>
<span data-ttu-id="e8b95-125">Siga as instruções gerais de configuração.</span><span class="sxs-lookup"><span data-stu-id="e8b95-125">Follow the general setup instructions.</span></span>

## <a name="step-6-manage-schema"></a><span data-ttu-id="e8b95-126">Etapa 6: Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="e8b95-126">Step 6: Manage schema</span></span>
<span data-ttu-id="e8b95-127">Siga as instruções gerais de configuração.</span><span class="sxs-lookup"><span data-stu-id="e8b95-127">Follow the general setup instructions.</span></span>

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="e8b95-128">Etapa 7: Escolher configurações de atualização</span><span class="sxs-lookup"><span data-stu-id="e8b95-128">Step 7: Choose refresh settings</span></span>
<span data-ttu-id="e8b95-129">Siga as instruções gerais de configuração.</span><span class="sxs-lookup"><span data-stu-id="e8b95-129">Follow the general setup instructions.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="e8b95-130">Etapa 8: Analisar a conexão</span><span class="sxs-lookup"><span data-stu-id="e8b95-130">Step 8: Review connection</span></span>
<span data-ttu-id="e8b95-131">Siga as instruções gerais de configuração.</span><span class="sxs-lookup"><span data-stu-id="e8b95-131">Follow the general setup instructions.</span></span>

<!---## Troubleshooting-->
<!---To be added-->

## <a name="limitations"></a><span data-ttu-id="e8b95-132">Limitações</span><span class="sxs-lookup"><span data-stu-id="e8b95-132">Limitations</span></span>
<span data-ttu-id="e8b95-133">O conector MediaWiki tem estas limitações na versão de visualização:</span><span class="sxs-lookup"><span data-stu-id="e8b95-133">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="e8b95-134">Oferece suporte somente a wikis baseados em nuvem.</span><span class="sxs-lookup"><span data-stu-id="e8b95-134">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="e8b95-135">Dá suporte apenas ao Basic ou ao OAuth 2.0 com a autenticação do Azure Active Directory ou do Azure.</span><span class="sxs-lookup"><span data-stu-id="e8b95-135">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="e8b95-136">Não dá suporte à seleção de namespace para indexação.</span><span class="sxs-lookup"><span data-stu-id="e8b95-136">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="e8b95-137">Indexa apenas os namespaces Principal, Categoria e Arquivo.</span><span class="sxs-lookup"><span data-stu-id="e8b95-137">Indexes only Main, Category, and File namespaces.</span></span>
* <span data-ttu-id="e8b95-138">Não dá suporte a ACLs (Listas de Controle de Acesso).</span><span class="sxs-lookup"><span data-stu-id="e8b95-138">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="e8b95-139">Assim, as páginas indexadas ficam visíveis para todos os usuários na organização.</span><span class="sxs-lookup"><span data-stu-id="e8b95-139">Thus, indexed pages are visible to all users in the organization.</span></span>
