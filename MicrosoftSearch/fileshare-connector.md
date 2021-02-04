---
title: Conector do Graph de compartilhamento de arquivos para a Pesquisa da Microsoft
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
ROBOTS: NoIndex
description: Configurar o conector do Graph de compartilhamento de arquivos para a Pesquisa da Microsoft
ms.openlocfilehash: e8a68a1c6b9c2c8a8592fb915fe9bf846a758e77
ms.sourcegitcommit: d53b91f8f52a4a96281b66831c2449bbffe2177c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097417"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a><span data-ttu-id="ff6ec-103">Conector do Graph de compartilhamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="ff6ec-103">File share Graph connector</span></span>

<span data-ttu-id="ff6ec-104">O conector do Graph de compartilhamento de arquivos permite que os usuários em sua organização pesquisem compartilhamentos de arquivos locais do Windows.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-104">The File share Graph connector allows users in your organization to search on-premise Windows file shares.</span></span>

> [!NOTE]
> <span data-ttu-id="ff6ec-105">Leia o [**artigo Configuração do seu conector do Graph**](configure-connector.md) para entender o processo geral de configuração de conectores do Graph.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-105">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="ff6ec-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="ff6ec-106">Before you get started</span></span>

### <a name="install-the-graph-connector-agent"></a><span data-ttu-id="ff6ec-107">Instalar o agente do conector do Graph</span><span class="sxs-lookup"><span data-stu-id="ff6ec-107">Install the Graph connector agent</span></span>

<span data-ttu-id="ff6ec-108">Para indexar seus compartilhamentos de arquivos do Windows, você deve instalar e registrar o agente do conector do Graph.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-108">To index your Windows file shares, you must install and register the Graph connector agent.</span></span> <span data-ttu-id="ff6ec-109">Consulte [Instalar o agente do conector do Graph](on-prem-agent.md) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-109">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

### <a name="content-requirements"></a><span data-ttu-id="ff6ec-110">Requisitos de conteúdo</span><span class="sxs-lookup"><span data-stu-id="ff6ec-110">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="ff6ec-111">Tipos de arquivo</span><span class="sxs-lookup"><span data-stu-id="ff6ec-111">File types</span></span>

<span data-ttu-id="ff6ec-112">O conteúdo dos seguintes formatos pode ser indexado e pesquisado: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS e ZIP.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-112">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="ff6ec-113">Somente o conteúdo textual desses formatos é indexado.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-113">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="ff6ec-114">Todo o conteúdo multimídia é ignorado.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-114">All multimedia content is ignored.</span></span> <span data-ttu-id="ff6ec-115">Para qualquer arquivo que não pertença a esse formato, os metadados são indexados.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-115">For any file that doesn't belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="ff6ec-116">Limites de tamanho de arquivo</span><span class="sxs-lookup"><span data-stu-id="ff6ec-116">File size limits</span></span>

<span data-ttu-id="ff6ec-117">O tamanho máximo de arquivo com suporte é de 100 MB.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-117">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="ff6ec-118">Os arquivos com mais de 100 MB não são indexados.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-118">Files that exceed 100 MB aren't indexed.</span></span> <span data-ttu-id="ff6ec-119">O limite máximo de tamanho pós-processado é de 4 MB.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-119">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="ff6ec-120">O processamento é interrompido quando o tamanho de um arquivo atinge 4 MB.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-120">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="ff6ec-121">Portanto, algumas frases presentes no arquivo podem não funcionar para pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-121">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="ff6ec-122">Etapa 1: Adicionar um conector do Graph no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ff6ec-122">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="ff6ec-123">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ff6ec-123">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="ff6ec-124">Etapa 2: Nomear a conexão</span><span class="sxs-lookup"><span data-stu-id="ff6ec-124">Step 2: Name the connection</span></span>

<span data-ttu-id="ff6ec-125">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ff6ec-125">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="ff6ec-126">Etapa 3: Definir as configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="ff6ec-126">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="ff6ec-127">Na página **Conectar-se à fonte de dados,** selecione **compartilhamento de** arquivos e forneça o nome, a ID da conexão e a descrição.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-127">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="ff6ec-128">Na próxima página, forneça o caminho para o compartilhamento de arquivos e selecione o agente de conector do Graph instalado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-128">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="ff6ec-129">Insira as credenciais de uma conta [de usuário do Microsoft Windows](https://microsoft.com/windows) com acesso de leitura a todos os arquivos no compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-129">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

### <a name="preserve-last-access-time"></a><span data-ttu-id="ff6ec-130">Preservar a hora do último acesso</span><span class="sxs-lookup"><span data-stu-id="ff6ec-130">Preserve last access time</span></span>

<span data-ttu-id="ff6ec-131">Quando o conector tenta rastrear um arquivo, o campo "horário do último acesso" em seus metadados é atualizado.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-131">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="ff6ec-132">Se você depender desse campo para qualquer solução de arquivamento e backup e não quiser atualizá-lo quando o conector o acessar, poderá configurar essa opção na página Configurações **Avançadas.**</span><span class="sxs-lookup"><span data-stu-id="ff6ec-132">If you depend on that field for any archiving and backup solutions and doesn't want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="ff6ec-133">Etapa 4: Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="ff6ec-133">Step 4: Manage search permissions</span></span>

<span data-ttu-id="ff6ec-134">Você pode restringir a permissão para pesquisar qualquer arquivo com base em Listas de Controle de Acesso de Compartilhamento ou Listas de Controle de Acesso do Sistema de Arquivos de Nova Tecnologia (NTFS).</span><span class="sxs-lookup"><span data-stu-id="ff6ec-134">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="ff6ec-135">Se você quiser usar As Listas de Controle de Acesso, selecione a opção apropriada na **página Configurações Avançadas.**</span><span class="sxs-lookup"><span data-stu-id="ff6ec-135">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="ff6ec-136">Se você quiser usar listas de controle de acesso NTFS, selecione a opção apropriada na **página Gerenciar permissões de** pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ff6ec-136">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="ff6ec-137">Etapa 5: Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="ff6ec-137">Step 5: Assign property labels</span></span>

<span data-ttu-id="ff6ec-138">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ff6ec-138">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="ff6ec-139">Etapa 6: Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="ff6ec-139">Step 6: Manage schema</span></span>

<span data-ttu-id="ff6ec-140">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ff6ec-140">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="ff6ec-141">Etapa 7: Escolher configurações de atualização</span><span class="sxs-lookup"><span data-stu-id="ff6ec-141">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="ff6ec-142">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ff6ec-142">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="ff6ec-143">Etapa 8: Analisar a conexão</span><span class="sxs-lookup"><span data-stu-id="ff6ec-143">Step 8: Review connection</span></span>

<span data-ttu-id="ff6ec-144">Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)</span><span class="sxs-lookup"><span data-stu-id="ff6ec-144">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
