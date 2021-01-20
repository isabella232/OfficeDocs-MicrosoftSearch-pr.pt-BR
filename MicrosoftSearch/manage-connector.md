---
title: Gerenciar conectores do Microsoft Graph para a Pesquisa da Microsoft
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
description: Gerenciar conectores do Microsoft Graph para a Pesquisa da Microsoft.
ms.openlocfilehash: 5258f26a5c97be4ee9f90c7a8b2b9bb8fec447bc
ms.sourcegitcommit: 39bf9f0db7f9bff2ab82c99a059b0ddcf1c98f5f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/19/2021
ms.locfileid: "49905926"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a><span data-ttu-id="e36ac-103">Monitorar suas conexões</span><span class="sxs-lookup"><span data-stu-id="e36ac-103">Monitor your connections</span></span>

<span data-ttu-id="e36ac-104">Para acessar e gerenciar seus conectores, você deve ser designado como um administrador de pesquisa para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="e36ac-104">To access and manage your connectors, you must be designated as a search administrator for your tenant.</span></span> <span data-ttu-id="e36ac-105">Entre em contato com o administrador de locatários para provisioná-lo para a função de administrador de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e36ac-105">Contact your tenant administrator to provision you for the search administrator role.</span></span>

## <a name="connection-operations"></a><span data-ttu-id="e36ac-106">Operações de conexão</span><span class="sxs-lookup"><span data-stu-id="e36ac-106">Connection Operations</span></span>

<span data-ttu-id="e36ac-107">Navegue até [a guia Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) no centro [de administração do Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="e36ac-107">Navigate to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="e36ac-108">Para cada tipo de conector, o [Centro de administração do Microsoft 365](https://admin.microsoft.com) dá suporte às operações mostradas na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="e36ac-108">For each connector type, the [Microsoft 365 admin center](https://admin.microsoft.com) supports the operations shown in the following table:</span></span>

<span data-ttu-id="e36ac-109">Operação</span><span class="sxs-lookup"><span data-stu-id="e36ac-109">Operation</span></span> | <span data-ttu-id="e36ac-110">Conector criado pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="e36ac-110">Microsoft-built connector</span></span> | <span data-ttu-id="e36ac-111">Conector de parceiro ou personalizado</span><span class="sxs-lookup"><span data-stu-id="e36ac-111">Partner or custom-built connector</span></span>
--- | --- | ---
<span data-ttu-id="e36ac-112">Adicionar uma conexão</span><span class="sxs-lookup"><span data-stu-id="e36ac-112">Add a connection</span></span> | :heavy_check_mark: <span data-ttu-id="e36ac-113">(Consulte [Configurar seu conector criado pela Microsoft)](configure-connector.md)</span><span class="sxs-lookup"><span data-stu-id="e36ac-113">(See [Configure your Microsoft-built connector](configure-connector.md))</span></span> | :x: <span data-ttu-id="e36ac-114">(Consulte sua UX de administrador de conector personalizado ou parceiro)</span><span class="sxs-lookup"><span data-stu-id="e36ac-114">(Refer to your partner or custom-built connector admin UX)</span></span>
<span data-ttu-id="e36ac-115">Excluir uma conexão</span><span class="sxs-lookup"><span data-stu-id="e36ac-115">Delete a connection</span></span> | :heavy_check_mark: | :heavy_check_mark:
<span data-ttu-id="e36ac-118">Editar uma conexão publicada</span><span class="sxs-lookup"><span data-stu-id="e36ac-118">Edit a published connection</span></span> | :heavy_check_mark: <span data-ttu-id="e36ac-119">Nome</span><span class="sxs-lookup"><span data-stu-id="e36ac-119">Name</span></span><br></br> :heavy_check_mark: <span data-ttu-id="e36ac-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="e36ac-120">Description</span></span><br></br> :heavy_check_mark: <span data-ttu-id="e36ac-121">Credenciais de autenticação para sua fonte de dados externa</span><span class="sxs-lookup"><span data-stu-id="e36ac-121">Authentication credentials for your external data source</span></span><br></br> :heavy_check_mark: <span data-ttu-id="e36ac-122">Credenciais de gateway para sua fonte de dados local</span><span class="sxs-lookup"><span data-stu-id="e36ac-122">Gateway credentials for your on-premises data source</span></span><br></br> :heavy_check_mark: <span data-ttu-id="e36ac-123">Atualizar agenda</span><span class="sxs-lookup"><span data-stu-id="e36ac-123">Refresh schedule</span></span><br></br> | :heavy_check_mark: <span data-ttu-id="e36ac-124">Nome</span><span class="sxs-lookup"><span data-stu-id="e36ac-124">Name</span></span><br></br> :heavy_check_mark: <span data-ttu-id="e36ac-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="e36ac-125">Description</span></span>
<span data-ttu-id="e36ac-126">Editar uma conexão de rascunho</span><span class="sxs-lookup"><span data-stu-id="e36ac-126">Edit a draft connection</span></span> | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a><span data-ttu-id="e36ac-129">Monitorar o status da conexão</span><span class="sxs-lookup"><span data-stu-id="e36ac-129">Monitor your connection status</span></span>

<span data-ttu-id="e36ac-130">Depois de criar uma conexão, o número de itens **processados** aparece na guia Conectores da **página Pesquisa da Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="e36ac-130">After you create a connection, the number of processed items shows on the **Connectors** tab on the **Microsoft Search** page.</span></span> <span data-ttu-id="e36ac-131">Depois que o rastreamento completo inicial for concluído com êxito, o progresso de rastreamentos incrementais periódicos será exibido.</span><span class="sxs-lookup"><span data-stu-id="e36ac-131">After the initial full crawl completes successfully, the progress for periodic incremental crawls displays.</span></span> <span data-ttu-id="e36ac-132">Esta página fornece informações sobre as operações diárias do conector e uma visão geral dos logs e do histórico de erros.</span><span class="sxs-lookup"><span data-stu-id="e36ac-132">This page provides information about the connector's day-to-day operations and an overview of the logs and error history.</span></span>

<span data-ttu-id="e36ac-133">Quatro estados aparecem na coluna **Status** em cada conexão:</span><span class="sxs-lookup"><span data-stu-id="e36ac-133">Four states show up in the **Status** column against each connection:</span></span>

* <span data-ttu-id="e36ac-134">**Sincronização**.</span><span class="sxs-lookup"><span data-stu-id="e36ac-134">**Syncing**.</span></span> <span data-ttu-id="e36ac-135">O conector está rastreando os dados da fonte para indexar os itens existentes e fazer atualizações.</span><span class="sxs-lookup"><span data-stu-id="e36ac-135">The connector is crawling the data from the source to index the existing items and make any updates.</span></span>

* <span data-ttu-id="e36ac-136">**Habilitado:** a conexão está habilitada e não há rastreamento ativo em execução.</span><span class="sxs-lookup"><span data-stu-id="e36ac-136">**Enabled**: The connection is enabled, and there's no active crawl running against it.</span></span> <span data-ttu-id="e36ac-137">**A hora da última sincronização** indica quando ocorreu o último rastreamento bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="e36ac-137">**Last sync time** indicates when the last successful crawl happened.</span></span> <span data-ttu-id="e36ac-138">A conexão é tão recente quanto a hora da última sincronização.</span><span class="sxs-lookup"><span data-stu-id="e36ac-138">The connection is as fresh as the last sync time.</span></span>

* <span data-ttu-id="e36ac-139">**Pausado**.</span><span class="sxs-lookup"><span data-stu-id="e36ac-139">**Paused**.</span></span> <span data-ttu-id="e36ac-140">Os rastreamentos são pausados pelos administradores por meio da opção de pausa.</span><span class="sxs-lookup"><span data-stu-id="e36ac-140">The crawls are paused by the admins through the pause option.</span></span> <span data-ttu-id="e36ac-141">O próximo rastreamento só será executado quando for retomado manualmente.</span><span class="sxs-lookup"><span data-stu-id="e36ac-141">The next crawl runs only when it's manually resumed.</span></span> <span data-ttu-id="e36ac-142">No entanto, os dados dessa conexão continuam a ser pesquisáveis.</span><span class="sxs-lookup"><span data-stu-id="e36ac-142">However, the data from this connection continues to be searchable.</span></span>

* <span data-ttu-id="e36ac-143">**Falha**.</span><span class="sxs-lookup"><span data-stu-id="e36ac-143">**Failed**.</span></span> <span data-ttu-id="e36ac-144">A conexão teve uma falha crítica.</span><span class="sxs-lookup"><span data-stu-id="e36ac-144">The connection had a critical failure.</span></span> <span data-ttu-id="e36ac-145">Esse erro requer intervenção manual.</span><span class="sxs-lookup"><span data-stu-id="e36ac-145">This error requires manual intervention.</span></span> <span data-ttu-id="e36ac-146">O administrador precisa tomar a ação apropriada com base na mensagem de erro mostrada.</span><span class="sxs-lookup"><span data-stu-id="e36ac-146">The admin needs to take appropriate action based on the error message shown.</span></span> <span data-ttu-id="e36ac-147">Os dados que foram indexados até que o erro ocorreu são pesquisáveis.</span><span class="sxs-lookup"><span data-stu-id="e36ac-147">Data that was indexed until the error occurred is searchable.</span></span>

## <a name="monitor-your-index-quota-utilization"></a><span data-ttu-id="e36ac-148">Monitorar a utilização da cota de índice</span><span class="sxs-lookup"><span data-stu-id="e36ac-148">Monitor your index quota utilization</span></span>

<span data-ttu-id="e36ac-149">A cota e o consumo do índice disponíveis são exibidos na página de aterrissagem dos conectores.</span><span class="sxs-lookup"><span data-stu-id="e36ac-149">The available index quota and consumption is displayed on the connectors landing page.</span></span>

![Barra de utilização da cota de índice](media/quota_utilization.png)

>[!NOTE]
><span data-ttu-id="e36ac-151">Durante o período de visualização, todas as organizações que estão tentando os conectores do Graph foram fornecidas uma cota fixa gratuita de até 2 milhões de itens em todas as conexões.</span><span class="sxs-lookup"><span data-stu-id="e36ac-151">During the preview period, every organization trying out Graph connectors was provided a free fixed quota of up to 2 million items across all connections.</span></span> <span data-ttu-id="e36ac-152">Com os conectores do Graph geralmente disponíveis, a cota gratuita expirará em 1º de fevereiro de 2021 para as organizações que usam conectores do Graph na visualização.</span><span class="sxs-lookup"><span data-stu-id="e36ac-152">With Graph connectors being generally available, the free quota will expire on Feb 1st, 2021 for those organizations who have been using Graph connectors in preview.</span></span>
><span data-ttu-id="e36ac-153">Os conectores do Graph integrados pela Microsoft rotulados como ["Visualização"](connectors-preview.md) não serão incluídos na cota de índice total cobrada da sua organização.</span><span class="sxs-lookup"><span data-stu-id="e36ac-153">Microsoft-built Graph connectors labeled as ["Preview"](connectors-preview.md) will not be included in the total charged index quota for your organization.</span></span> <span data-ttu-id="e36ac-154">No entanto, ele contará para o número máximo de 10 conexões que você pode configurar para sua organização e o número máximo de 7 milhões de itens que sua organização pode indexar entre conexões; cada conexão é limitada a 700.000 itens.</span><span class="sxs-lookup"><span data-stu-id="e36ac-154">However, it will count towards the max number of 10 connections you can configure for your organization and the max number of 7 million items your organization can index across connections; each connection is limited 700,000 items.</span></span> 

<span data-ttu-id="e36ac-155">A barra de utilização de cota indicará vários estados com base no consumo de cota por sua organização:</span><span class="sxs-lookup"><span data-stu-id="e36ac-155">The quota utilization bar will indicate various states based on consumption of quota by your organization:</span></span>

<span data-ttu-id="e36ac-156">Estado</span><span class="sxs-lookup"><span data-stu-id="e36ac-156">State</span></span> | <span data-ttu-id="e36ac-157">Consumo de cota</span><span class="sxs-lookup"><span data-stu-id="e36ac-157">Quota consumption</span></span>
--- | ---
<span data-ttu-id="e36ac-158">Normal</span><span class="sxs-lookup"><span data-stu-id="e36ac-158">Normal</span></span> | <span data-ttu-id="e36ac-159">1-69%</span><span class="sxs-lookup"><span data-stu-id="e36ac-159">1-69%</span></span>
<span data-ttu-id="e36ac-160">Alta</span><span class="sxs-lookup"><span data-stu-id="e36ac-160">High</span></span> | <span data-ttu-id="e36ac-161">70-89%</span><span class="sxs-lookup"><span data-stu-id="e36ac-161">70-89%</span></span>
<span data-ttu-id="e36ac-162">Crítico</span><span class="sxs-lookup"><span data-stu-id="e36ac-162">Critical</span></span> | <span data-ttu-id="e36ac-163">90%-99%</span><span class="sxs-lookup"><span data-stu-id="e36ac-163">90%-99%</span></span>
<span data-ttu-id="e36ac-164">Completo</span><span class="sxs-lookup"><span data-stu-id="e36ac-164">Full</span></span> | <span data-ttu-id="e36ac-165">100%</span><span class="sxs-lookup"><span data-stu-id="e36ac-165">100%</span></span>

<span data-ttu-id="e36ac-166">O número de itens indexados também será exibido com cada conexão.</span><span class="sxs-lookup"><span data-stu-id="e36ac-166">The number of items indexed will also be displayed with each connection.</span></span> <span data-ttu-id="e36ac-167">O número de itens indexados por cada conexão contribui para a cota total disponível para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e36ac-167">The number of items indexed by each connection contributes to the total quota available for your organization.</span></span>

<span data-ttu-id="e36ac-168">Quando a cota de índice for excedida para sua organização, todas as conexões ativas serão impactadas e essas conexões funcionarão **no estado excedido do** limite.</span><span class="sxs-lookup"><span data-stu-id="e36ac-168">When index quota is exceeded for your organization, all active connections will be impacted, and those connections will operate in **limit exceeded** state.</span></span> <span data-ttu-id="e36ac-169">Nesse estado, suas conexões ativas</span><span class="sxs-lookup"><span data-stu-id="e36ac-169">In this state, your active connections</span></span>  

* <span data-ttu-id="e36ac-170">Não será possível adicionar novos itens.</span><span class="sxs-lookup"><span data-stu-id="e36ac-170">Will not be able to add new items.</span></span>

* <span data-ttu-id="e36ac-171">Poderá atualizar ou excluir itens existentes.</span><span class="sxs-lookup"><span data-stu-id="e36ac-171">Will be able to update or delete existing items.</span></span>

<span data-ttu-id="e36ac-172">Para corrigir isso, você pode fazer qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="e36ac-172">To fix this, you can do any of the following:</span></span>

* <span data-ttu-id="e36ac-173">Saiba como comprar cota de índice para sua organização em [requisitos de licenciamento e preços.](licensing.md)</span><span class="sxs-lookup"><span data-stu-id="e36ac-173">Learn how to purchase index quota for your organization at [Licensing requirements and pricing](licensing.md).</span></span>

* <span data-ttu-id="e36ac-174">Identifique as conexões que têm muito conteúdo sendo ingerido e atualize-as para indexar menos itens para dar espaço à cota.</span><span class="sxs-lookup"><span data-stu-id="e36ac-174">Identify connections which have too much content being ingested and update them to index fewer items to make room for quota.</span></span> <span data-ttu-id="e36ac-175">Para atualizar a conexão, você deve excluir e criar uma nova conexão com um novo filtro de ingestão que traz menos itens.</span><span class="sxs-lookup"><span data-stu-id="e36ac-175">To update the connection, you must delete and create a new connection with a new ingestion filter which brings in fewer items.</span></span>

* <span data-ttu-id="e36ac-176">Excluir permanentemente uma ou mais conexões</span><span class="sxs-lookup"><span data-stu-id="e36ac-176">Permanently delete one or more connections</span></span>