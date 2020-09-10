---
title: Visualização de conectores
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Saiba mais sobre a visualização de conectores do Microsoft Graph para o Microsoft Search.
ms.openlocfilehash: 81d169074a316b6ab07f47156e0f057e50c12e3e
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422888"
---
# <a name="microsoft-graph-connectors-preview"></a><span data-ttu-id="8963e-103">Visualização de conectores do Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="8963e-103">Microsoft Graph connectors preview</span></span>

<span data-ttu-id="8963e-104">Os conectores do Microsoft Graph e as APIs de pesquisa da Microsoft (consulta e índice) estão atualmente no status de visualização.</span><span class="sxs-lookup"><span data-stu-id="8963e-104">Microsoft Graph connectors and Microsoft Search APIs (query and index) are currently in preview status.</span></span> <span data-ttu-id="8963e-105">Para obter acesso à funcionalidade de conectores, você deve ativar a opção de lançamento direcionado no locatário.</span><span class="sxs-lookup"><span data-stu-id="8963e-105">To gain access to connectors functionality, you must turn on the Targeted release option in your tenant.</span></span> <span data-ttu-id="8963e-106">Esta é uma visualização inicial e não há garantia de nível de serviço.</span><span class="sxs-lookup"><span data-stu-id="8963e-106">This is an early preview, and there's no service level guarantee.</span></span> <span data-ttu-id="8963e-107">Incentivamos os clientes a experimentar a funcionalidade de conectores e a fornecer comentários.</span><span class="sxs-lookup"><span data-stu-id="8963e-107">We encourage customers to try connectors functionality and provide feedback.</span></span> <span data-ttu-id="8963e-108">Não recomendamos o uso de conectores para fins de produção durante o período de visualização.</span><span class="sxs-lookup"><span data-stu-id="8963e-108">We don’t recommend using connectors for production purposes during the preview period.</span></span>

## <a name="set-up-targeted-release"></a><span data-ttu-id="8963e-109">Configurar lançamento direcionado</span><span class="sxs-lookup"><span data-stu-id="8963e-109">Set up Targeted release</span></span>

<span data-ttu-id="8963e-110">Para experimentar os conectores, você deve ter a opção de **lançamento direcionada** definida para todos os usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="8963e-110">To try connectors, you must have the **Targeted release** option set for all users in your organization.</span></span> <span data-ttu-id="8963e-111">Para saber mais sobre a opção de lançamento direcionado e como configurá-la, confira [configurar as opções de lançamento padrão ou direcionadas no Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="8963e-111">To learn more about the Targeted release option and how to set it, see [Set up the Standard or Targeted release options in Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

## <a name="choose-a-preview-environment"></a><span data-ttu-id="8963e-112">Escolha um ambiente de visualização</span><span class="sxs-lookup"><span data-stu-id="8963e-112">Choose a preview environment</span></span>

<span data-ttu-id="8963e-113">Para testar os conectores, as APIs de indexação e as APIs de pesquisa, recomendamos estes dois métodos:</span><span class="sxs-lookup"><span data-stu-id="8963e-113">To try connectors, indexing APIs, and search APIs, we recommend these two methods:</span></span>

1. <span data-ttu-id="8963e-114">**Testar locatário**.</span><span class="sxs-lookup"><span data-stu-id="8963e-114">**Test tenant**.</span></span>  <span data-ttu-id="8963e-115">Recomendamos que você use um locatário de teste para experimentar a visualização dos conectores do Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="8963e-115">We encourage you to use a test tenant to try the Microsoft Graph connectors preview.</span></span>

2. <span data-ttu-id="8963e-116">**Conjunto de sites de teste**.</span><span class="sxs-lookup"><span data-stu-id="8963e-116">**Test site collection**.</span></span> <span data-ttu-id="8963e-117">Se você não tem um locatário de teste, pode criar um conjunto de sites de teste para experimentar a funcionalidade de conectores.</span><span class="sxs-lookup"><span data-stu-id="8963e-117">If you don't have a test tenant, you can create a test site collection to try out connectors functionality.</span></span> <span data-ttu-id="8963e-118">Para mostrar resultados de conectores sem afetar as páginas de pesquisa em qualquer outra parte da sua organização, personalize a experiência de pesquisa apenas desse conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="8963e-118">To show results from connectors without impacting the search pages anywhere else in your organization, customize the search experience of only that site collection.</span></span>

## <a name="preview-limitations"></a><span data-ttu-id="8963e-119">Limitações de visualização</span><span class="sxs-lookup"><span data-stu-id="8963e-119">Preview limitations</span></span>

<span data-ttu-id="8963e-120">A versão prévia tem as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="8963e-120">The preview release has the following limitations:</span></span>

* <span data-ttu-id="8963e-121">O throughput da inclusão é limitado em cerca de quatro itens por segundo.</span><span class="sxs-lookup"><span data-stu-id="8963e-121">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="8963e-122">Não há suporte para atualizações de esquema.</span><span class="sxs-lookup"><span data-stu-id="8963e-122">There's no support for schema updates.</span></span> <span data-ttu-id="8963e-123">Após criar uma configuração de conexão, não há como atualizar o esquema.</span><span class="sxs-lookup"><span data-stu-id="8963e-123">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="8963e-124">Você só pode excluir e recriar a conexão.</span><span class="sxs-lookup"><span data-stu-id="8963e-124">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="8963e-125">O conteúdo indexado aparece na página de resultados de pesquisa em uma vertical personalizada.</span><span class="sxs-lookup"><span data-stu-id="8963e-125">Indexed content only shows up in the search results page under a custom vertical.</span></span> <span data-ttu-id="8963e-126">Essa restrição se aplica ao conteúdo com tipos personalizados.</span><span class="sxs-lookup"><span data-stu-id="8963e-126">This restriction applies to content with custom types.</span></span>

* <span data-ttu-id="8963e-127">Qualquer conexão que você configurar durante o período de visualização talvez precise ser excluída e recriada.</span><span class="sxs-lookup"><span data-stu-id="8963e-127">Any connection you set up during the preview period might need to be deleted and re-created.</span></span> <span data-ttu-id="8963e-128">Essas conexões não funcionarão mais se não forem compatíveis com as alterações feitas para melhorar o produto.</span><span class="sxs-lookup"><span data-stu-id="8963e-128">Those connections won't work anymore if they're incompatible with changes made to improve the product.</span></span>

* <span data-ttu-id="8963e-129">Há um limite de conexões.</span><span class="sxs-lookup"><span data-stu-id="8963e-129">There's a connections limit.</span></span> <span data-ttu-id="8963e-130">Cada locatário pode criar até 10 conexões.</span><span class="sxs-lookup"><span data-stu-id="8963e-130">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="8963e-131">Tamanho do repositório de origem.</span><span class="sxs-lookup"><span data-stu-id="8963e-131">Source repository size.</span></span> <span data-ttu-id="8963e-132">Recomendamos que você visualize os conectores com um repositório de origem de cerca de 200.000 itens, já que esse é nosso limite de escala de pesquisa testada.</span><span class="sxs-lookup"><span data-stu-id="8963e-132">We recommend that you preview connectors with a source repository of about 200,000 items as this is our tested search scale limit.</span></span> <span data-ttu-id="8963e-133">Estamos trabalhando para melhorar o desempenho da pesquisa e esperamos oferecer suporte para tamanhos de repositório maiores em um futuro próximo.</span><span class="sxs-lookup"><span data-stu-id="8963e-133">We are working on improving the performance of search, and we expect to support for larger repository sizes in the near future.</span></span>

* <span data-ttu-id="8963e-134">Editar o suporte para conexão não está disponível.</span><span class="sxs-lookup"><span data-stu-id="8963e-134">Edit support for connection is not available.</span></span> <span data-ttu-id="8963e-135">Depois que a conexão tiver sido criada, você não poderá editá-la ou alterá-la.</span><span class="sxs-lookup"><span data-stu-id="8963e-135">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="8963e-136">Se for necessário alterar os detalhes, você deverá excluir e recriar a conexão.</span><span class="sxs-lookup"><span data-stu-id="8963e-136">If you need to change any details, you must delete and recreate the connection.</span></span>

* <span data-ttu-id="8963e-137">O conteúdo do conector só pode ser pesquisado em verticais personalizadas.</span><span class="sxs-lookup"><span data-stu-id="8963e-137">Connector content can only be searched on custom verticals.</span></span>

* <span data-ttu-id="8963e-138">O conteúdo do conector de apenas uma conexão pode ser exibido em cada vertical personalizada e requer a criação do tipo de resultado.</span><span class="sxs-lookup"><span data-stu-id="8963e-138">Connector content from only one connection can be displayed in each custom vertical and requires result type creation.</span></span>
