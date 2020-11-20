---
title: Conector MediaWiki para o Microsoft Search
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
description: Configurar o conector MediaWiki para o Microsoft Search
ms.openlocfilehash: 7f6b34dcafc4b82ab3778ec1d7a4921383e44a44
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367636"
---
# <a name="mediawiki-connector"></a><span data-ttu-id="8cbf0-103">Conector MediaWiki</span><span class="sxs-lookup"><span data-stu-id="8cbf0-103">MediaWiki connector</span></span>

<span data-ttu-id="8cbf0-104">Com o conector MediaWiki, sua organização pode descobrir e indexar dados de um wiki criado usando o software do MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-104">With the MediaWiki connector, your organization can discover and index data from a wiki created by using MediaWiki software.</span></span> <span data-ttu-id="8cbf0-105">Esse conector indexa o conteúdo especificado à pesquisa da Microsoft e dá suporte a rastreamentos periódicos para manter o índice atualizado.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-105">This connector indexes specified content into Microsoft Search and supports periodic crawls to keep the index up to date.</span></span>

<span data-ttu-id="8cbf0-106">Este artigo é para os administradores do Microsoft 365 ou qualquer pessoa que configure, execute e monitore um conector MediaWiki.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a MediaWiki connector.</span></span> <span data-ttu-id="8cbf0-107">Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="8cbf0-108">Conectar-se a uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="8cbf0-108">Connect to a data source</span></span>

<span data-ttu-id="8cbf0-109">Insira a URL e as credenciais do MediaWiki para autenticar a conexão.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-109">Enter your MediaWiki URL and credentials for authenticating the connection.</span></span> <span data-ttu-id="8cbf0-110">Você precisará das seguintes informações: **ID do locatário**, **ID do recurso**, ID do **cliente** e segredo do **cliente**.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-110">You'll need the following information: **Tenant ID**, **Resource ID**, **Client ID**, and the **Client Secret**.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="8cbf0-111">Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="8cbf0-111">Manage search permissions</span></span>

<span data-ttu-id="8cbf0-112">O conector MediaWiki suporta apenas as permissões de pesquisa visíveis para **todos**.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-112">The MediaWiki connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="8cbf0-113">Dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-113">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="8cbf0-114">Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="8cbf0-114">Assign property labels</span></span>

<span data-ttu-id="8cbf0-115">Você pode atribuir uma propriedade Source a cada rótulo escolhendo a partir de um menu de opções.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-115">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="8cbf0-116">Embora esta etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá resultados de pesquisa mais precisos para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-116">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="8cbf0-117">Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="8cbf0-117">Manage schema</span></span>

<span data-ttu-id="8cbf0-118">Na tela **gerenciar esquema** , você tem a opção de alterar os atributos de esquema (**consultável**, **pesquisável**, **recuperável** e **refinável**) associados às propriedades, adicionar aliases opcionais e escolher a propriedade **Content** .</span><span class="sxs-lookup"><span data-stu-id="8cbf0-118">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="8cbf0-119">Definir o agendamento de atualização</span><span class="sxs-lookup"><span data-stu-id="8cbf0-119">Set the refresh schedule</span></span>

<span data-ttu-id="8cbf0-120">Essa agenda atualiza dados indexados, portanto, as alterações no wiki são refletidas no Microsoft Search.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-120">This schedule refreshes indexed data, so changes to the wiki are reflected in Microsoft Search.</span></span> <span data-ttu-id="8cbf0-121">Todas as novas páginas, páginas excluídas, conteúdo de página ou alterações de metadados aparecem nos resultados da pesquisa após o intervalo de atualização especificado.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-121">All new pages, deleted pages, page content, or metadata changes appear in search results after the specified refresh interval.</span></span> <span data-ttu-id="8cbf0-122">O tempo de rastreamento depende do tamanho do wiki.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-122">The crawl time is dependent on the size of the wiki.</span></span> <span data-ttu-id="8cbf0-123">No momento, o conector é rastreado em torno de 50 páginas por minuto.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-123">Currently the connector crawls at around 50 pages per minute.</span></span>

## <a name="limitations"></a><span data-ttu-id="8cbf0-124">Limitações</span><span class="sxs-lookup"><span data-stu-id="8cbf0-124">Limitations</span></span>

<span data-ttu-id="8cbf0-125">O conector MediaWiki tem essas limitações na versão prévia:</span><span class="sxs-lookup"><span data-stu-id="8cbf0-125">The MediaWiki connector has these limitations in the preview release:</span></span>

* <span data-ttu-id="8cbf0-126">Oferece suporte somente a wikis baseados em nuvem.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-126">Supports only cloud-based wikis.</span></span>
* <span data-ttu-id="8cbf0-127">O suporta somente o Basic ou o OAuth 2,0 com a autenticação do Azure Active Directory ou do Azure.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-127">Supports only Basic or OAuth 2.0 with Azure Active Directory or Azure authentication.</span></span>
* <span data-ttu-id="8cbf0-128">Não dá suporte à seleção de namespace para indexação.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-128">Doesn't support namespace selection for indexing.</span></span> <span data-ttu-id="8cbf0-129">Indexa somente namespaces **principal**, de **categoria** e de **arquivo** .</span><span class="sxs-lookup"><span data-stu-id="8cbf0-129">Indexes only **Main**, **Category**, and **File** namespaces.</span></span>
* <span data-ttu-id="8cbf0-130">Não oferece suporte a listas de controle de acesso (ACLs).</span><span class="sxs-lookup"><span data-stu-id="8cbf0-130">Doesn't support Access Control Lists (ACLs).</span></span> <span data-ttu-id="8cbf0-131">Portanto, as páginas indexadas são visíveis para todos os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="8cbf0-131">Thus, indexed pages are visible to all users in the organization.</span></span>
