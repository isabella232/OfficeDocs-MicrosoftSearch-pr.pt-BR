---
title: Gerenciar conectores do Microsoft Graph para Pesquisa da Microsoft
ms.author: mecampos
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Gerenciar conectores do Microsoft Graph para Pesquisa da Microsoft.
ms.openlocfilehash: 685b501f3afe25d75c13a1fe6cc2c1b5db8a3511
ms.sourcegitcommit: e5d695c40b68c2f1fa082fa9de20b9aa6d5b8050
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52325164"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a><span data-ttu-id="f5643-103">Monitorar as suas conexões</span><span class="sxs-lookup"><span data-stu-id="f5643-103">Monitor your connections</span></span>

<span data-ttu-id="f5643-104">Para acessar e gerenciar seus conectores, você deve ser designado como administrador de pesquisa para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="f5643-104">To access and manage your connectors, you must be designated as a search administrator for your tenant.</span></span> <span data-ttu-id="f5643-105">Entre em contato com o administrador do locatário para provisioná-lo para a função de administrador de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f5643-105">Contact your tenant administrator to provision you for the search administrator role.</span></span>

## <a name="connection-operations"></a><span data-ttu-id="f5643-106">Operações de conexão</span><span class="sxs-lookup"><span data-stu-id="f5643-106">Connection Operations</span></span>

<span data-ttu-id="f5643-107">Navegue até [a guia Conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) no centro de administração [do Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="f5643-107">Navigate to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="f5643-108">Para cada tipo de conector, o Centro de administração do [Microsoft 365](https://admin.microsoft.com) dá suporte às operações mostradas na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="f5643-108">For each connector type, the [Microsoft 365 admin center](https://admin.microsoft.com) supports the operations shown in the following table:</span></span>

<span data-ttu-id="f5643-109">Operation</span><span class="sxs-lookup"><span data-stu-id="f5643-109">Operation</span></span> | <span data-ttu-id="f5643-110">Conectores de gráfico da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f5643-110">Graph connectors by Microsoft</span></span> | <span data-ttu-id="f5643-111">Conectores de parceiros ou gráficos</span><span class="sxs-lookup"><span data-stu-id="f5643-111">Partner or Graph connectors</span></span>
--- | --- | ---
<span data-ttu-id="f5643-112">Adicionar uma conexão</span><span class="sxs-lookup"><span data-stu-id="f5643-112">Add a connection</span></span> | :heavy_check_mark: <span data-ttu-id="f5643-113">(Consulte Visão [geral da Instalação](configure-connector.md))</span><span class="sxs-lookup"><span data-stu-id="f5643-113">(See [Setup overview](configure-connector.md))</span></span> | :x: <span data-ttu-id="f5643-114">(Consulte seu parceiro ou UX de administrador de conector personalizado)</span><span class="sxs-lookup"><span data-stu-id="f5643-114">(Refer to your partner or custom-built connector admin UX)</span></span>
<span data-ttu-id="f5643-115">Excluir uma conexão</span><span class="sxs-lookup"><span data-stu-id="f5643-115">Delete a connection</span></span> | :heavy_check_mark: | :heavy_check_mark:
<span data-ttu-id="f5643-118">Editar uma conexão publicada</span><span class="sxs-lookup"><span data-stu-id="f5643-118">Edit a published connection</span></span> | :heavy_check_mark: <span data-ttu-id="f5643-119">Nome e Descrição</span><span class="sxs-lookup"><span data-stu-id="f5643-119">Name and Description</span></span><br></br> :heavy_check_mark: <span data-ttu-id="f5643-120">Configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="f5643-120">Connection settings</span></span><br></br> :heavy_check_mark: <span data-ttu-id="f5643-121">Rótulos de propriedades</span><span class="sxs-lookup"><span data-stu-id="f5643-121">Property labels</span></span><br></br> :heavy_check_mark: <span data-ttu-id="f5643-122">Esquema</span><span class="sxs-lookup"><span data-stu-id="f5643-122">Schema</span></span><br></br> :heavy_check_mark: <span data-ttu-id="f5643-123">Agenda de atualização</span><span class="sxs-lookup"><span data-stu-id="f5643-123">Refresh schedule</span></span><br></br> | :heavy_check_mark: <span data-ttu-id="f5643-124">Nome</span><span class="sxs-lookup"><span data-stu-id="f5643-124">Name</span></span><br></br> :heavy_check_mark: <span data-ttu-id="f5643-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="f5643-125">Description</span></span>
<span data-ttu-id="f5643-126">Editar uma conexão de rascunho</span><span class="sxs-lookup"><span data-stu-id="f5643-126">Edit a draft connection</span></span> | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a><span data-ttu-id="f5643-129">Monitorar seu estado de conexão</span><span class="sxs-lookup"><span data-stu-id="f5643-129">Monitor your connection state</span></span>

<span data-ttu-id="f5643-130">Depois de criar uma conexão, o número de itens **processados** aparece na guia Conectores na **página Pesquisa da Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="f5643-130">After you create a connection, the number of processed items shows on the **Connectors** tab on the **Microsoft Search** page.</span></span> <span data-ttu-id="f5643-131">Depois que o rastreamento completo inicial for concluído com êxito, o progresso de rastreamentos incrementais periódicos será exibido.</span><span class="sxs-lookup"><span data-stu-id="f5643-131">After the initial full crawl completes successfully, the progress for periodic incremental crawls displays.</span></span> <span data-ttu-id="f5643-132">Esta página fornece informações sobre as operações diárias do conector e uma visão geral dos logs e do histórico de erros.</span><span class="sxs-lookup"><span data-stu-id="f5643-132">This page provides information about the connector's day-to-day operations and an overview of the logs and error history.</span></span>

<span data-ttu-id="f5643-133">Cinco estados aparecem na coluna **Estado em** cada conexão:</span><span class="sxs-lookup"><span data-stu-id="f5643-133">Five states show up in the **State** column against each connection:</span></span>

* <span data-ttu-id="f5643-134">**Sincronizando**.</span><span class="sxs-lookup"><span data-stu-id="f5643-134">**Syncing**.</span></span> <span data-ttu-id="f5643-135">O conector está rastreando os dados da fonte para indexar os itens existentes e fazer qualquer atualização.</span><span class="sxs-lookup"><span data-stu-id="f5643-135">The connector is crawling the data from the source to index the existing items and make any updates.</span></span>

* <span data-ttu-id="f5643-136">**Pronto**: a conexão está pronta e não há rastreamento ativo em execução contra ela.</span><span class="sxs-lookup"><span data-stu-id="f5643-136">**Ready**: The connection is ready, and there's no active crawl running against it.</span></span> <span data-ttu-id="f5643-137">**O último tempo de** sincronização indica quando ocorreu o último rastreamento bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="f5643-137">**Last sync time** indicates when the last successful crawl happened.</span></span> <span data-ttu-id="f5643-138">A conexão é tão recente quanto a última hora de sincronização.</span><span class="sxs-lookup"><span data-stu-id="f5643-138">The connection is as fresh as the last sync time.</span></span>

* <span data-ttu-id="f5643-139">**Pausado**.</span><span class="sxs-lookup"><span data-stu-id="f5643-139">**Paused**.</span></span> <span data-ttu-id="f5643-140">Os rastreamentos são pausados pelos administradores por meio da opção de pausa.</span><span class="sxs-lookup"><span data-stu-id="f5643-140">The crawls are paused by the admins through the pause option.</span></span> <span data-ttu-id="f5643-141">O próximo rastreamento é executado somente quando é retomado manualmente.</span><span class="sxs-lookup"><span data-stu-id="f5643-141">The next crawl runs only when it's manually resumed.</span></span> <span data-ttu-id="f5643-142">No entanto, os dados dessa conexão continuam a ser pesquisáveis.</span><span class="sxs-lookup"><span data-stu-id="f5643-142">However, the data from this connection continues to be searchable.</span></span>

* <span data-ttu-id="f5643-143">**Falha**.</span><span class="sxs-lookup"><span data-stu-id="f5643-143">**Failed**.</span></span> <span data-ttu-id="f5643-144">A conexão teve uma falha crítica.</span><span class="sxs-lookup"><span data-stu-id="f5643-144">The connection had a critical failure.</span></span> <span data-ttu-id="f5643-145">Esse erro requer intervenção manual.</span><span class="sxs-lookup"><span data-stu-id="f5643-145">This error requires manual intervention.</span></span> <span data-ttu-id="f5643-146">O administrador precisa tomar a ação apropriada com base na mensagem de erro mostrada.</span><span class="sxs-lookup"><span data-stu-id="f5643-146">The admin needs to take appropriate action based on the error message shown.</span></span> <span data-ttu-id="f5643-147">Os dados indexados até o erro ocorrer são pesquisáveis.</span><span class="sxs-lookup"><span data-stu-id="f5643-147">Data that was indexed until the error occurred is searchable.</span></span>

* <span data-ttu-id="f5643-148">**Delete Failed**.</span><span class="sxs-lookup"><span data-stu-id="f5643-148">**Delete Failed**.</span></span> <span data-ttu-id="f5643-149">Falha na exclusão da conexão.</span><span class="sxs-lookup"><span data-stu-id="f5643-149">The deletion of connection failed.</span></span> <span data-ttu-id="f5643-150">Dependendo do motivo da falha, os dados ainda podem ser indexados, a cota de item ainda pode ser consumida e os rastreamentos ainda podem ser executados para a conexão.</span><span class="sxs-lookup"><span data-stu-id="f5643-150">Depending upon the failure reason, the data might still be indexed, item quota may still be consumed and crawls might still run for the connection.</span></span> <span data-ttu-id="f5643-151">É recomendável tentar excluir a conexão novamente neste estado.</span><span class="sxs-lookup"><span data-stu-id="f5643-151">It is recommended to try deleting the connection again in this state.</span></span>

## <a name="monitor-your-index-quota-utilization"></a><span data-ttu-id="f5643-152">Monitorar a utilização da cota de índice</span><span class="sxs-lookup"><span data-stu-id="f5643-152">Monitor your index quota utilization</span></span>

<span data-ttu-id="f5643-153">A cota de índice disponível e o consumo são exibidos na página inicial dos conectores.</span><span class="sxs-lookup"><span data-stu-id="f5643-153">The available index quota and consumption is displayed on the connectors landing page.</span></span>

![Barra de utilização de cota de índice](media/quota_utilization.png)
 
>[!NOTE]
><span data-ttu-id="f5643-155">Durante o período de visualização, todas as organizações que estavam tentando os conectores do Graph foram fornecidas uma cota fixa gratuita de até 2 milhões de itens em todas as conexões.</span><span class="sxs-lookup"><span data-stu-id="f5643-155">During the preview period, every organization trying out Graph connectors was provided a free fixed quota of up to 2 million items across all connections.</span></span> <span data-ttu-id="f5643-156">Com os conectores do Graph geralmente disponíveis, a cota gratuita expirará em 1º de abril de 2021 para as organizações que têm usado conectores graph na visualização.</span><span class="sxs-lookup"><span data-stu-id="f5643-156">With Graph connectors being generally available, the free quota will expire on April 1st, 2021 for those organizations who have been using Graph connectors in preview.</span></span>
><span data-ttu-id="f5643-157">Os conectores do Graph criado pela Microsoft rotulados como ["Visualização"](./connectors-overview.md) não serão incluídos na cota de índice total cobrada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f5643-157">Microsoft-built Graph connectors labeled as ["Preview"](./connectors-overview.md) will not be included in the total charged index quota for your organization.</span></span> <span data-ttu-id="f5643-158">No entanto, ele contará para o número máximo de 10 conexões que você pode configurar para sua organização e o número máximo de 7 milhões de itens que sua organização pode indexar entre conexões; cada conexão é limitada a 700.000 itens.</span><span class="sxs-lookup"><span data-stu-id="f5643-158">However, it will count towards the max number of 10 connections you can configure for your organization and the max number of 7 million items your organization can index across connections; each connection is limited 700,000 items.</span></span> 

<span data-ttu-id="f5643-159">A barra de utilização de cota indicará vários estados com base no consumo de cota pela sua organização:</span><span class="sxs-lookup"><span data-stu-id="f5643-159">The quota utilization bar will indicate various states based on consumption of quota by your organization:</span></span>

<span data-ttu-id="f5643-160">Estado</span><span class="sxs-lookup"><span data-stu-id="f5643-160">State</span></span> | <span data-ttu-id="f5643-161">Níveis de utilização de cota</span><span class="sxs-lookup"><span data-stu-id="f5643-161">Quota utilization levels</span></span>
--- | --- 
<span data-ttu-id="f5643-162">Normal</span><span class="sxs-lookup"><span data-stu-id="f5643-162">Normal</span></span> | <span data-ttu-id="f5643-163">0-79%</span><span class="sxs-lookup"><span data-stu-id="f5643-163">0-79%</span></span>
<span data-ttu-id="f5643-164">Alto</span><span class="sxs-lookup"><span data-stu-id="f5643-164">High</span></span> | <span data-ttu-id="f5643-165">80-89%</span><span class="sxs-lookup"><span data-stu-id="f5643-165">80-89%</span></span>
<span data-ttu-id="f5643-166">Crítico</span><span class="sxs-lookup"><span data-stu-id="f5643-166">Critical</span></span> | <span data-ttu-id="f5643-167">90%-99%</span><span class="sxs-lookup"><span data-stu-id="f5643-167">90%-99%</span></span>
<span data-ttu-id="f5643-168">Completo</span><span class="sxs-lookup"><span data-stu-id="f5643-168">Full</span></span> | <span data-ttu-id="f5643-169">100%</span><span class="sxs-lookup"><span data-stu-id="f5643-169">100%</span></span>

<!-- 
![Quota utilization levels](media/connectors-quota-utilization-levels.png)
-->

<span data-ttu-id="f5643-170">O número de itens indexados também será exibido com cada conexão.</span><span class="sxs-lookup"><span data-stu-id="f5643-170">The number of items indexed will also be displayed with each connection.</span></span> <span data-ttu-id="f5643-171">O número de itens indexados por cada conexão contribui para a cota total disponível para sua organização.</span><span class="sxs-lookup"><span data-stu-id="f5643-171">The number of items indexed by each connection contributes to the total quota available for your organization.</span></span>

<span data-ttu-id="f5643-172">Quando a cota de índice é excedida para sua organização, todas as conexões ativas serão impactadas e essas conexões operarão **no estado limite excedido.**</span><span class="sxs-lookup"><span data-stu-id="f5643-172">When index quota is exceeded for your organization, all active connections will be impacted, and those connections will operate in **limit exceeded** state.</span></span> <span data-ttu-id="f5643-173">Nesse estado, suas conexões ativas</span><span class="sxs-lookup"><span data-stu-id="f5643-173">In this state, your active connections</span></span>  

* <span data-ttu-id="f5643-174">Não será possível adicionar novos itens.</span><span class="sxs-lookup"><span data-stu-id="f5643-174">Will not be able to add new items.</span></span>

* <span data-ttu-id="f5643-175">Será possível atualizar ou excluir itens existentes.</span><span class="sxs-lookup"><span data-stu-id="f5643-175">Will be able to update or delete existing items.</span></span>

<span data-ttu-id="f5643-176">Para corrigir isso, você pode fazer qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="f5643-176">To fix this, you can do any of the following:</span></span>

* <span data-ttu-id="f5643-177">Saiba como comprar cota de índice para sua organização em [Requisitos de licenciamento e preços.](licensing.md)</span><span class="sxs-lookup"><span data-stu-id="f5643-177">Learn how to purchase index quota for your organization at [Licensing requirements and pricing](licensing.md).</span></span>

* <span data-ttu-id="f5643-178">Identifique conexões que tenham muito conteúdo sendo ingerido e atualize-as para indexar menos itens para dar espaço para cota.</span><span class="sxs-lookup"><span data-stu-id="f5643-178">Identify connections which have too much content being ingested and update them to index fewer items to make room for quota.</span></span> <span data-ttu-id="f5643-179">Para atualizar a conexão, você deve excluir e criar uma nova conexão com um novo filtro de ingestão que traz menos itens.</span><span class="sxs-lookup"><span data-stu-id="f5643-179">To update the connection, you must delete and create a new connection with a new ingestion filter which brings in fewer items.</span></span>

* <span data-ttu-id="f5643-180">Excluir permanentemente uma ou mais conexões</span><span class="sxs-lookup"><span data-stu-id="f5643-180">Permanently delete one or more connections</span></span>