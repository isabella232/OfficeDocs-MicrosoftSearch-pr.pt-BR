---
title: Gerenciar conectores do Microsoft Graph para Pesquisa da Microsoft
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
description: Gerenciar conectores do Microsoft Graph para Pesquisa da Microsoft.
ms.openlocfilehash: 488b6e9452e381f8fc64ad06c6f063aa170ca7f5
ms.sourcegitcommit: 3ed4d21510020045d25e8c5b7e168013d96c1b7e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50464036"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a><span data-ttu-id="1a1f2-103">Monitorar as suas conexões</span><span class="sxs-lookup"><span data-stu-id="1a1f2-103">Monitor your connections</span></span>

<span data-ttu-id="1a1f2-104">Para acessar e gerenciar seus conectores, você deve ser designado como administrador de pesquisa para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-104">To access and manage your connectors, you must be designated as a search administrator for your tenant.</span></span> <span data-ttu-id="1a1f2-105">Entre em contato com o administrador do locatário para provisioná-lo para a função de administrador de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-105">Contact your tenant administrator to provision you for the search administrator role.</span></span>

## <a name="connection-operations"></a><span data-ttu-id="1a1f2-106">Operações de conexão</span><span class="sxs-lookup"><span data-stu-id="1a1f2-106">Connection Operations</span></span>

<span data-ttu-id="1a1f2-107">Navegue até [a guia Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) no centro de administração [do Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1a1f2-107">Navigate to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="1a1f2-108">Para cada tipo de conector, o Centro de administração do [Microsoft 365](https://admin.microsoft.com) dá suporte às operações mostradas na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="1a1f2-108">For each connector type, the [Microsoft 365 admin center](https://admin.microsoft.com) supports the operations shown in the following table:</span></span>

<span data-ttu-id="1a1f2-109">Operation</span><span class="sxs-lookup"><span data-stu-id="1a1f2-109">Operation</span></span> | <span data-ttu-id="1a1f2-110">Conector criado pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="1a1f2-110">Microsoft-built connector</span></span> | <span data-ttu-id="1a1f2-111">Conector de parceiro ou personalizado</span><span class="sxs-lookup"><span data-stu-id="1a1f2-111">Partner or custom-built connector</span></span>
--- | --- | ---
<span data-ttu-id="1a1f2-112">Adicionar uma conexão</span><span class="sxs-lookup"><span data-stu-id="1a1f2-112">Add a connection</span></span> | :heavy_check_mark: <span data-ttu-id="1a1f2-113">(Consulte [Configure your Microsoft-built connector](configure-connector.md))</span><span class="sxs-lookup"><span data-stu-id="1a1f2-113">(See [Configure your Microsoft-built connector](configure-connector.md))</span></span> | :x: <span data-ttu-id="1a1f2-114">(Consulte seu parceiro ou UX de administrador de conector personalizado)</span><span class="sxs-lookup"><span data-stu-id="1a1f2-114">(Refer to your partner or custom-built connector admin UX)</span></span>
<span data-ttu-id="1a1f2-115">Excluir uma conexão</span><span class="sxs-lookup"><span data-stu-id="1a1f2-115">Delete a connection</span></span> | :heavy_check_mark: | :heavy_check_mark:
<span data-ttu-id="1a1f2-118">Editar uma conexão publicada</span><span class="sxs-lookup"><span data-stu-id="1a1f2-118">Edit a published connection</span></span> | :heavy_check_mark: <span data-ttu-id="1a1f2-119">Nome</span><span class="sxs-lookup"><span data-stu-id="1a1f2-119">Name</span></span><br></br> :heavy_check_mark: <span data-ttu-id="1a1f2-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="1a1f2-120">Description</span></span><br></br> :heavy_check_mark: <span data-ttu-id="1a1f2-121">credenciais de autenticação para sua fonte de dados externa</span><span class="sxs-lookup"><span data-stu-id="1a1f2-121">Authentication credentials for your external data source</span></span><br></br> :heavy_check_mark: <span data-ttu-id="1a1f2-122">Credenciais de gateway para sua fonte de dados local</span><span class="sxs-lookup"><span data-stu-id="1a1f2-122">Gateway credentials for your on-premises data source</span></span><br></br> :heavy_check_mark: <span data-ttu-id="1a1f2-123">Agenda de atualização</span><span class="sxs-lookup"><span data-stu-id="1a1f2-123">Refresh schedule</span></span><br></br> | :heavy_check_mark: <span data-ttu-id="1a1f2-124">Nome</span><span class="sxs-lookup"><span data-stu-id="1a1f2-124">Name</span></span><br></br> :heavy_check_mark: <span data-ttu-id="1a1f2-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="1a1f2-125">Description</span></span>
<span data-ttu-id="1a1f2-126">Editar uma conexão de rascunho</span><span class="sxs-lookup"><span data-stu-id="1a1f2-126">Edit a draft connection</span></span> | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-status"></a><span data-ttu-id="1a1f2-129">Monitorar o status da conexão</span><span class="sxs-lookup"><span data-stu-id="1a1f2-129">Monitor your connection status</span></span>

<span data-ttu-id="1a1f2-130">Depois de criar uma conexão, o número de itens **processados** aparece na guia Conectores na **página Pesquisa da Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="1a1f2-130">After you create a connection, the number of processed items shows on the **Connectors** tab on the **Microsoft Search** page.</span></span> <span data-ttu-id="1a1f2-131">Depois que o rastreamento completo inicial for concluído com êxito, o progresso de rastreamentos incrementais periódicos será exibido.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-131">After the initial full crawl completes successfully, the progress for periodic incremental crawls displays.</span></span> <span data-ttu-id="1a1f2-132">Esta página fornece informações sobre as operações diárias do conector e uma visão geral dos logs e do histórico de erros.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-132">This page provides information about the connector's day-to-day operations and an overview of the logs and error history.</span></span>

<span data-ttu-id="1a1f2-133">Quatro estados aparecem na coluna **Status** em cada conexão:</span><span class="sxs-lookup"><span data-stu-id="1a1f2-133">Four states show up in the **Status** column against each connection:</span></span>

* <span data-ttu-id="1a1f2-134">**Sincronizando**.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-134">**Syncing**.</span></span> <span data-ttu-id="1a1f2-135">O conector está rastreando os dados da fonte para indexar os itens existentes e fazer qualquer atualização.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-135">The connector is crawling the data from the source to index the existing items and make any updates.</span></span>

* <span data-ttu-id="1a1f2-136">**Habilitado**: a conexão está habilitada e não há rastreamento ativo em execução contra ela.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-136">**Enabled**: The connection is enabled, and there's no active crawl running against it.</span></span> <span data-ttu-id="1a1f2-137">**O último tempo de** sincronização indica quando ocorreu o último rastreamento bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-137">**Last sync time** indicates when the last successful crawl happened.</span></span> <span data-ttu-id="1a1f2-138">A conexão é tão recente quanto a última hora de sincronização.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-138">The connection is as fresh as the last sync time.</span></span>

* <span data-ttu-id="1a1f2-139">**Pausado**.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-139">**Paused**.</span></span> <span data-ttu-id="1a1f2-140">Os rastreamentos são pausados pelos administradores por meio da opção de pausa.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-140">The crawls are paused by the admins through the pause option.</span></span> <span data-ttu-id="1a1f2-141">O próximo rastreamento é executado somente quando é retomado manualmente.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-141">The next crawl runs only when it's manually resumed.</span></span> <span data-ttu-id="1a1f2-142">No entanto, os dados dessa conexão continuam a ser pesquisáveis.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-142">However, the data from this connection continues to be searchable.</span></span>

* <span data-ttu-id="1a1f2-143">**Falha**.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-143">**Failed**.</span></span> <span data-ttu-id="1a1f2-144">A conexão teve uma falha crítica.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-144">The connection had a critical failure.</span></span> <span data-ttu-id="1a1f2-145">Esse erro requer intervenção manual.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-145">This error requires manual intervention.</span></span> <span data-ttu-id="1a1f2-146">O administrador precisa tomar a ação apropriada com base na mensagem de erro mostrada.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-146">The admin needs to take appropriate action based on the error message shown.</span></span> <span data-ttu-id="1a1f2-147">Os dados indexados até o erro ocorrer são pesquisáveis.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-147">Data that was indexed until the error occurred is searchable.</span></span>

## <a name="monitor-your-index-quota-utilization"></a><span data-ttu-id="1a1f2-148">Monitorar a utilização da cota de índice</span><span class="sxs-lookup"><span data-stu-id="1a1f2-148">Monitor your index quota utilization</span></span>

<span data-ttu-id="1a1f2-149">A cota de índice disponível e o consumo são exibidos na página inicial dos conectores.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-149">The available index quota and consumption is displayed on the connectors landing page.</span></span>

![Barra de utilização de cota de índice](media/quota_utilization.png)

>[!NOTE]
><span data-ttu-id="1a1f2-151">Durante o período de visualização, todas as organizações que estavam tentando os conectores do Graph foram fornecidas uma cota fixa gratuita de até 2 milhões de itens em todas as conexões.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-151">During the preview period, every organization trying out Graph connectors was provided a free fixed quota of up to 2 million items across all connections.</span></span> <span data-ttu-id="1a1f2-152">Com os conectores do Graph geralmente disponíveis, a cota gratuita expirará em 1º de abril de 2021 para as organizações que têm usado conectores graph na visualização.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-152">With Graph connectors being generally available, the free quota will expire on April 1st, 2021 for those organizations who have been using Graph connectors in preview.</span></span>
><span data-ttu-id="1a1f2-153">Os conectores do Graph criado pela Microsoft rotulados como ["Visualização"](connectors-preview.md) não serão incluídos na cota de índice total cobrada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-153">Microsoft-built Graph connectors labeled as ["Preview"](connectors-preview.md) will not be included in the total charged index quota for your organization.</span></span> <span data-ttu-id="1a1f2-154">No entanto, ele contará para o número máximo de 10 conexões que você pode configurar para sua organização e o número máximo de 7 milhões de itens que sua organização pode indexar entre conexões; cada conexão é limitada a 700.000 itens.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-154">However, it will count towards the max number of 10 connections you can configure for your organization and the max number of 7 million items your organization can index across connections; each connection is limited 700,000 items.</span></span> 

<span data-ttu-id="1a1f2-155">A barra de utilização de cota indicará vários estados com base no consumo de cota pela sua organização:</span><span class="sxs-lookup"><span data-stu-id="1a1f2-155">The quota utilization bar will indicate various states based on consumption of quota by your organization:</span></span>

<span data-ttu-id="1a1f2-156">Estado</span><span class="sxs-lookup"><span data-stu-id="1a1f2-156">State</span></span> | <span data-ttu-id="1a1f2-157">Consumo de cotas</span><span class="sxs-lookup"><span data-stu-id="1a1f2-157">Quota consumption</span></span>
--- | ---
<span data-ttu-id="1a1f2-158">Normal</span><span class="sxs-lookup"><span data-stu-id="1a1f2-158">Normal</span></span> | <span data-ttu-id="1a1f2-159">1-69%</span><span class="sxs-lookup"><span data-stu-id="1a1f2-159">1-69%</span></span>
<span data-ttu-id="1a1f2-160">Alto</span><span class="sxs-lookup"><span data-stu-id="1a1f2-160">High</span></span> | <span data-ttu-id="1a1f2-161">70-89%</span><span class="sxs-lookup"><span data-stu-id="1a1f2-161">70-89%</span></span>
<span data-ttu-id="1a1f2-162">Crítico</span><span class="sxs-lookup"><span data-stu-id="1a1f2-162">Critical</span></span> | <span data-ttu-id="1a1f2-163">90%-99%</span><span class="sxs-lookup"><span data-stu-id="1a1f2-163">90%-99%</span></span>
<span data-ttu-id="1a1f2-164">Completo</span><span class="sxs-lookup"><span data-stu-id="1a1f2-164">Full</span></span> | <span data-ttu-id="1a1f2-165">100%</span><span class="sxs-lookup"><span data-stu-id="1a1f2-165">100%</span></span>

<span data-ttu-id="1a1f2-166">O número de itens indexados também será exibido com cada conexão.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-166">The number of items indexed will also be displayed with each connection.</span></span> <span data-ttu-id="1a1f2-167">O número de itens indexados por cada conexão contribui para a cota total disponível para sua organização.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-167">The number of items indexed by each connection contributes to the total quota available for your organization.</span></span>

<span data-ttu-id="1a1f2-168">Quando a cota de índice é excedida para sua organização, todas as conexões ativas serão impactadas e essas conexões operarão **no estado limite excedido.**</span><span class="sxs-lookup"><span data-stu-id="1a1f2-168">When index quota is exceeded for your organization, all active connections will be impacted, and those connections will operate in **limit exceeded** state.</span></span> <span data-ttu-id="1a1f2-169">Nesse estado, suas conexões ativas</span><span class="sxs-lookup"><span data-stu-id="1a1f2-169">In this state, your active connections</span></span>  

* <span data-ttu-id="1a1f2-170">Não será possível adicionar novos itens.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-170">Will not be able to add new items.</span></span>

* <span data-ttu-id="1a1f2-171">Será possível atualizar ou excluir itens existentes.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-171">Will be able to update or delete existing items.</span></span>

<span data-ttu-id="1a1f2-172">Para corrigir isso, você pode fazer qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="1a1f2-172">To fix this, you can do any of the following:</span></span>

* <span data-ttu-id="1a1f2-173">Saiba como comprar cota de índice para sua organização em [Requisitos de licenciamento e preços.](licensing.md)</span><span class="sxs-lookup"><span data-stu-id="1a1f2-173">Learn how to purchase index quota for your organization at [Licensing requirements and pricing](licensing.md).</span></span>

* <span data-ttu-id="1a1f2-174">Identifique conexões que tenham muito conteúdo sendo ingerido e atualize-as para indexar menos itens para dar espaço para cota.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-174">Identify connections which have too much content being ingested and update them to index fewer items to make room for quota.</span></span> <span data-ttu-id="1a1f2-175">Para atualizar a conexão, você deve excluir e criar uma nova conexão com um novo filtro de ingestão que traz menos itens.</span><span class="sxs-lookup"><span data-stu-id="1a1f2-175">To update the connection, you must delete and create a new connection with a new ingestion filter which brings in fewer items.</span></span>

* <span data-ttu-id="1a1f2-176">Excluir permanentemente uma ou mais conexões</span><span class="sxs-lookup"><span data-stu-id="1a1f2-176">Permanently delete one or more connections</span></span>
