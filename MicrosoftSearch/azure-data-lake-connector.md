---
title: Conector do Azure Data Lake Graph para Pesquisa da Microsoft
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
description: Configurar o conector do Azure Data Lake Storage Gen2 Graph para a Pesquisa da Microsoft
ms.openlocfilehash: 37a035b3de9dc217f885f193992d1e74a675fb35
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031319"
---
<!---Previous ms.author: monaray --->

# <a name="azure-data-lake-storage-gen2-graph-connector"></a><span data-ttu-id="1bb77-103">Conector do Gráfico de Armazenamento gen2 do Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="1bb77-103">Azure Data Lake Storage Gen2 Graph connector</span></span>

<span data-ttu-id="1bb77-104">O conector do Azure Data Lake Storage Gen2 Graph permite que os usuários em sua organização pesquisem arquivos armazenados em contas de Armazenamento de Blob do [Azure Blob](/azure/storage/blobs/storage-blobs-introduction) e do [Azure Data Lake Gen 2 Storage.](/azure/storage/blobs/data-lake-storage-introduction)</span><span class="sxs-lookup"><span data-stu-id="1bb77-104">The Azure Data Lake Storage Gen2 Graph connector allows users in your organization to search for files stored in [Azure Blob Storage](/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](/azure/storage/blobs/data-lake-storage-introduction) accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="1bb77-105">Leia o [**artigo Configurar seu conector do Graph**](configure-connector.md) para entender as instruções gerais de configuração dos conectores do Graph.</span><span class="sxs-lookup"><span data-stu-id="1bb77-105">Read the [**Setup your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup instructions.</span></span>

<span data-ttu-id="1bb77-106">Este artigo é para qualquer pessoa que configure, executa e monitore um conector de armazenamento do Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="1bb77-106">This article is for anyone who configures, runs, and monitors an Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="1bb77-107">Ele complementa o processo de instalação geral e mostra instruções que se aplicam apenas ao conector de armazenamento do Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="1bb77-107">It supplements the general setup process, and shows instructions that apply only for the Azure Data Lake Storage Gen2 connector.</span></span> <span data-ttu-id="1bb77-108">Este artigo também inclui informações sobre [Limitações.](#limitations)</span><span class="sxs-lookup"><span data-stu-id="1bb77-108">This article also includes information about [Limitations](#limitations).</span></span>

<span data-ttu-id="1bb77-109">No artigo, usamos o *Armazenamento do Azure como* um termo genérico para Armazenamento de Blob do [Azure](/azure/storage/blobs/storage-blobs-introduction) e Armazenamento do [Azure Data Lake Gen 2](/azure/storage/blobs/data-lake-storage-introduction).</span><span class="sxs-lookup"><span data-stu-id="1bb77-109">In the article, we use *Azure Storage* as a generic term for [Azure Blob Storage](/azure/storage/blobs/storage-blobs-introduction) and [Azure Data Lake Gen 2 Storage](/azure/storage/blobs/data-lake-storage-introduction).</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="1bb77-110">Etapa 1: Adicionar um conector graph no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1bb77-110">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="1bb77-111">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="1bb77-111">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="1bb77-112">Etapa 2: nomear a conexão</span><span class="sxs-lookup"><span data-stu-id="1bb77-112">Step 2: Name the connection</span></span>

<span data-ttu-id="1bb77-113">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="1bb77-113">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="1bb77-114">Etapa 3: Configurar as configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="1bb77-114">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="1bb77-115">Insira a cadeia de caracteres de conexão de armazenamento principal.</span><span class="sxs-lookup"><span data-stu-id="1bb77-115">Enter your Primary storage connection String.</span></span> <span data-ttu-id="1bb77-116">Essa cadeia de caracteres é necessária para permitir o acesso à sua conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1bb77-116">This string is required to allow access to your storage account.</span></span> <span data-ttu-id="1bb77-117">Para encontrar sua cadeia de caracteres de conexão,  vá para o [portal do Azure](https://ms.portal.azure.com/#home) e navegue até a seção Chaves da sua conta de Armazenamento relevante do Azure.</span><span class="sxs-lookup"><span data-stu-id="1bb77-117">To find your connection string, go to the [Azure portal](https://ms.portal.azure.com/#home) and navigate to the **Keys** section of your relevant Azure Storage account.</span></span>

<span data-ttu-id="1bb77-118">Se você preferir não fornecer o **AccountKey** (um parâmetro na cadeia de caracteres de conexão de armazenamento principal), conceda acesso ao nosso Serviço de Conectores do Graph para as seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="1bb77-118">If you prefer not to provide the **AccountKey** (a parameter in the primary storage connection string), grant access to our Graph Connectors Service for the following roles:</span></span>

* <span data-ttu-id="1bb77-119">Leitor de Dados de Blob de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="1bb77-119">Storage Blob Data Reader</span></span>
* <span data-ttu-id="1bb77-120">Colaborador de dados da fila de armazenamento</span><span class="sxs-lookup"><span data-stu-id="1bb77-120">Storage Queue Data Contributor</span></span>
* <span data-ttu-id="1bb77-121">Delegator de Blob de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="1bb77-121">Storage Blob Delegator</span></span>

<span data-ttu-id="1bb77-122">Navegue até a guia **Controle** de Acesso da sua conta de Armazenamento do Azure e siga as instruções para conceder acesso ao seguinte aplicativo:</span><span class="sxs-lookup"><span data-stu-id="1bb77-122">Navigate to the **Access Control** tab of your Azure Storage account, and follow the instructions there to grant access to the following app:</span></span>

* <span data-ttu-id="1bb77-123">**ID do aplicativo de** primeira parte: 56c1da01-2129-48f7-9355-af6d59d42766</span><span class="sxs-lookup"><span data-stu-id="1bb77-123">**First Party App ID:** 56c1da01-2129-48f7-9355-af6d59d42766</span></span>
* <span data-ttu-id="1bb77-124">**Nome do aplicativo de primeira parte:** Serviço de Conector do Graph</span><span class="sxs-lookup"><span data-stu-id="1bb77-124">**First Party App Name:** Graph Connector Service</span></span>

### <a name="storage-account-and-queue-notifications-optional"></a><span data-ttu-id="1bb77-125">Notificações de conta de armazenamento e fila (Opcional)</span><span class="sxs-lookup"><span data-stu-id="1bb77-125">Storage account and queue notifications (Optional)</span></span>

<span data-ttu-id="1bb77-126">O suporte para processar alterações em tempo real no Serviço de Conectores do Graph pode ser adicionado no futuro.</span><span class="sxs-lookup"><span data-stu-id="1bb77-126">Support to process changes in real time in the Graph Connectors Service might be added in the future.</span></span> <span data-ttu-id="1bb77-127">Nesse caso, monitoraremos as notificações de alteração de armazenamento do Azure armazenadas em uma fila.</span><span class="sxs-lookup"><span data-stu-id="1bb77-127">In that case, we'll monitor Azure Storage change notifications stored in a queue.</span></span> <span data-ttu-id="1bb77-128">Você precisará criar uma fila na mesma conta que sua conta de Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="1bb77-128">You'll need to create a queue in the same account as your Azure Storage account.</span></span>

<span data-ttu-id="1bb77-129">Depois de criar uma fila, vá até a guia **Eventos** na página fila para configurar a **Assinatura de Evento**.</span><span class="sxs-lookup"><span data-stu-id="1bb77-129">After you create a queue, go to the **Events** tab on the queue page to configure **Event Subscription**.</span></span> <span data-ttu-id="1bb77-130">Escolha todos os eventos Blob que a fila receberá e conecte a fila à conta de Armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="1bb77-130">Choose all the Blob events that the queue will receive, and connect the queue to the Azure Storage account.</span></span>

## <a name="step-4-assign-property-labels"></a><span data-ttu-id="1bb77-131">Etapa 4: Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="1bb77-131">Step 4: Assign property labels</span></span>

<span data-ttu-id="1bb77-132">Você pode atribuir uma propriedade de origem a cada rótulo escolhendo a partir de um menu de opções.</span><span class="sxs-lookup"><span data-stu-id="1bb77-132">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="1bb77-133">Embora essa etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá melhores resultados de pesquisa para usuários finais.</span><span class="sxs-lookup"><span data-stu-id="1bb77-133">While this step isn't mandatory, having some property labels will improve the search relevance and ensure better search results for end users.</span></span>

## <a name="step-5-manage-schema"></a><span data-ttu-id="1bb77-134">Etapa 5: Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="1bb77-134">Step 5: Manage schema</span></span>

<span data-ttu-id="1bb77-135">Na tela **Gerenciar Esquema,** você pode alterar os atributos de esquema associados às propriedades, as opções são **Consulta,** **Pesquisa,** **Recuperação** e **Refinar**.</span><span class="sxs-lookup"><span data-stu-id="1bb77-135">On the **Manage Schema** screen, you can change the schema attributes associated with the properties, the options are **Query**, **Search**, **Retrieve**, and **Refine**.</span></span> <span data-ttu-id="1bb77-136">Você também pode adicionar aliases opcionais e escolher a **propriedade** Content.</span><span class="sxs-lookup"><span data-stu-id="1bb77-136">You also can add optional aliases, and choose the **Content** property.</span></span>

## <a name="step-6-manage-search-permissions"></a><span data-ttu-id="1bb77-137">Etapa 6: Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="1bb77-137">Step 6: Manage search permissions</span></span>

### <a name="azure-data-lake-gen-2"></a><span data-ttu-id="1bb77-138">Azure Data Lake Gen 2</span><span class="sxs-lookup"><span data-stu-id="1bb77-138">Azure Data Lake Gen 2</span></span>

<span data-ttu-id="1bb77-139">Você pode optar por ingerir as Listas de Controle de Acesso (ACLs) da sua conta de Armazenamento do [Azure Data Lake Gen 2.](/azure/storage/blobs/data-lake-storage-introduction)</span><span class="sxs-lookup"><span data-stu-id="1bb77-139">You can choose to ingest the Access Control Lists (ACLs) from your [Azure Data Lake Gen 2 Storage](/azure/storage/blobs/data-lake-storage-introduction) account.</span></span> <span data-ttu-id="1bb77-140">Quando essas permissões de pesquisa são definidas, o conteúdo da pesquisa é cortado com base nas permissões do usuário assinado no [Azure Active Directory](/azure/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="1bb77-140">When these search permissions are set, search content is trimmed based on the permissions of the user signed in [Azure Active Directory](/azure/active-directory/).</span></span> <span data-ttu-id="1bb77-141">Como alternativa, você pode optar por tornar todo o conteúdo indexado de sua conta de armazenamento visível para todos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1bb77-141">Alternatively, you can choose to make all the content indexed from your storage account visible to everyone in your organization.</span></span> <span data-ttu-id="1bb77-142">Nesse caso, todos na sua organização terão acesso a todos os dados em sua conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="1bb77-142">In this case, everyone in your organization will have access to all the data in your storage account.</span></span>

<span data-ttu-id="1bb77-143">O conector do Azure Data Lake Storage Gen2 Graph dá suporte a permissões de pesquisa visíveis para Todos **ou** Somente pessoas com acesso a essa fonte **de dados**.</span><span class="sxs-lookup"><span data-stu-id="1bb77-143">The Azure Data Lake Storage Gen2 Graph connector supports search permissions visible to **Everyone**, or **Only people with access to this data source**.</span></span> <span data-ttu-id="1bb77-144">Os dados indexados que aparecem nos resultados da pesquisa podem estar visíveis para os usuários da organização que têm acesso a cada item.</span><span class="sxs-lookup"><span data-stu-id="1bb77-144">Indexed data that appears in the search results could be visible to users in the organization who have access to each item.</span></span>

### <a name="azure-blob-storage"></a><span data-ttu-id="1bb77-145">Armazenamento de BLOBs do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="1bb77-145">Azure Blob Storage</span></span>

<span data-ttu-id="1bb77-146">Para uma conexão com o Armazenamento de Blob do [Azure](/azure/storage/blobs/storage-blobs-introduction), todo o conteúdo indexado da fonte configurada fica visível para todos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="1bb77-146">For a connection to [Azure Blob Storage](/azure/storage/blobs/storage-blobs-introduction), all the content indexed from the configured source is visible to everyone in your organization.</span></span> <span data-ttu-id="1bb77-147">As listas de controle de acesso não são suportadas no nível blob no Armazenamento de Blob do Azure.</span><span class="sxs-lookup"><span data-stu-id="1bb77-147">Access control lists aren't supported at Blob level in Azure Blob Storage.</span></span>

## <a name="step-7-set-the-refresh-schedule"></a><span data-ttu-id="1bb77-148">Etapa 7: Definir o cronograma de atualização</span><span class="sxs-lookup"><span data-stu-id="1bb77-148">Step 7: Set the refresh schedule</span></span>

<span data-ttu-id="1bb77-149">Na tela **Atualizar Configurações,** você pode definir o intervalo de rastreamento incremental e o intervalo de rastreamento completo.</span><span class="sxs-lookup"><span data-stu-id="1bb77-149">On the **Refresh Settings** screen, you can set the incremental crawl interval and the full crawl interval.</span></span> <span data-ttu-id="1bb77-150">Os intervalos padrão para o conector gen2 de armazenamento do Azure Data Lake são 15 minutos para um rastreamento incremental e uma semana para um rastreamento completo.</span><span class="sxs-lookup"><span data-stu-id="1bb77-150">The default intervals for the Azure Data Lake Storage Gen2 connector are 15 minutes for an incremental crawl and one week for a full crawl.</span></span>

## <a name="step-8-review-connection"></a><span data-ttu-id="1bb77-151">Etapa 8: Revisar conexão</span><span class="sxs-lookup"><span data-stu-id="1bb77-151">Step 8: Review connection</span></span>

<span data-ttu-id="1bb77-152">Siga as instruções [gerais de instalação](./configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="1bb77-152">Follow the general [setup instructions](./configure-connector.md).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a><span data-ttu-id="1bb77-153">Limitações</span><span class="sxs-lookup"><span data-stu-id="1bb77-153">Limitations</span></span>

<span data-ttu-id="1bb77-154">Uma conexão publicada para o Armazenamento de Blob do Azure não pode ser reconfigurada para a fonte de armazenamento do Azure Data Lake Gen2 e o contrário.</span><span class="sxs-lookup"><span data-stu-id="1bb77-154">A published connection for Azure Blob Storage cannot be reconfigured for Azure Data Lake Storage Gen2 source and the other way around.</span></span> <span data-ttu-id="1bb77-155">Nesses cenários, é recomendável configurar uma nova conexão.</span><span class="sxs-lookup"><span data-stu-id="1bb77-155">In such scenarios, it's recommended to configure a new connection.</span></span>

<span data-ttu-id="1bb77-156">Além disso, o tamanho dos arquivos precisa ser de 4 MB ou menos para que ele seja rastreado.</span><span class="sxs-lookup"><span data-stu-id="1bb77-156">Also, the size of the files needs to be 4 MB or less for it to be crawled.</span></span> <span data-ttu-id="1bb77-157">Os tipos de arquivo atualmente suportados são:</span><span class="sxs-lookup"><span data-stu-id="1bb77-157">File types currently supported are:</span></span>

* <span data-ttu-id="1bb77-158">Word (docx, .docm, .dotx, .dotm)</span><span class="sxs-lookup"><span data-stu-id="1bb77-158">Word (docx, .docm, .dotx, .dotm)</span></span>
* <span data-ttu-id="1bb77-159">PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)</span><span class="sxs-lookup"><span data-stu-id="1bb77-159">PowerPoint (.pptm, .pptx, .potm, .potx, .ppam, .ppsm, .ppsx)</span></span>
* <span data-ttu-id="1bb77-160">Excel (.xlsx, .xlsm)</span><span class="sxs-lookup"><span data-stu-id="1bb77-160">Excel (.xlsx, .xlsm)</span></span>
* <span data-ttu-id="1bb77-161">Formatos herddos do Office (.doc, .dot, etc.)</span><span class="sxs-lookup"><span data-stu-id="1bb77-161">Legacy Office formats (.doc, .dot, etc.)</span></span>
* <span data-ttu-id="1bb77-162">Texto (.txt)</span><span class="sxs-lookup"><span data-stu-id="1bb77-162">Text (.txt)</span></span>
* <span data-ttu-id="1bb77-163">HTML</span><span class="sxs-lookup"><span data-stu-id="1bb77-163">HTML</span></span>
* <span data-ttu-id="1bb77-164">PDF</span><span class="sxs-lookup"><span data-stu-id="1bb77-164">PDF</span></span>

<span data-ttu-id="1bb77-165">Arquivos binários como imagens (.jpg, .bmp, etc.) não são suportados.</span><span class="sxs-lookup"><span data-stu-id="1bb77-165">Binary files like images (.jpg, .bmp, etc.) are not supported.</span></span> <span data-ttu-id="1bb77-166">Por exemplo, se um arquivo .docx contiver apenas imagens, ele poderá ser ignorado porque não retornou nenhum conteúdo.</span><span class="sxs-lookup"><span data-stu-id="1bb77-166">For example, if a .docx file contains only images, it might be skipped because it didn't return any content.</span></span>