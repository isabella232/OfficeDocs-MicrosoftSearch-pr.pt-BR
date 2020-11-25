---
title: Conector de compartilhamento de arquivos
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Configurar o conector de compartilhamento de arquivos para o Microsoft Search
ms.openlocfilehash: a95cfe90ca35a385bb9ce3a4c565c18c5a42ec80
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408929"
---
# <a name="file-share-connector"></a><span data-ttu-id="af26f-103">Conector de compartilhamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="af26f-103">File share connector</span></span>

<span data-ttu-id="af26f-104">Com o conector de gráfico de compartilhamento de arquivos, os usuários da sua organização podem pesquisar compartilhamentos de arquivos do Windows locais.</span><span class="sxs-lookup"><span data-stu-id="af26f-104">With the File share Graph connector, users in your organization can search on-premise Windows file shares.</span></span>

<span data-ttu-id="af26f-105">Este artigo é para os administradores do Microsoft 365 ou qualquer pessoa que configure, execute e monitore um conector de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="af26f-105">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a file share connector.</span></span> <span data-ttu-id="af26f-106">Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="af26f-106">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-graph-connector-agent"></a><span data-ttu-id="af26f-107">Instalar o agente do conector do Graph</span><span class="sxs-lookup"><span data-stu-id="af26f-107">Install Graph connector agent</span></span>

<span data-ttu-id="af26f-108">Para indexar seus compartilhamentos de arquivos do Windows, você deve instalar e registrar o software de [agente do conector do Graph](on-prem-agent.md) .</span><span class="sxs-lookup"><span data-stu-id="af26f-108">In order to index your Windows file shares, you must install and register [Graph connector agent](on-prem-agent.md) software.</span></span>

## <a name="content-requirements"></a><span data-ttu-id="af26f-109">Requisitos de conteúdo</span><span class="sxs-lookup"><span data-stu-id="af26f-109">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="af26f-110">Tipos de arquivo</span><span class="sxs-lookup"><span data-stu-id="af26f-110">File types</span></span>

<span data-ttu-id="af26f-111">O conteúdo dos seguintes formatos pode ser indexado e pesquisado: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, NWS, OBT, OBD,, PPS, ODS, ODT, a, PDF, POT e PPS, o e o formato. XLS, o, o, o XML e o formato ZIP do.</span><span class="sxs-lookup"><span data-stu-id="af26f-111">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="af26f-112">Somente o conteúdo textual desses formatos é indexado.</span><span class="sxs-lookup"><span data-stu-id="af26f-112">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="af26f-113">Todo o conteúdo multimídia é ignorado.</span><span class="sxs-lookup"><span data-stu-id="af26f-113">All multimedia content is ignored.</span></span> <span data-ttu-id="af26f-114">Para qualquer arquivo que não pertença a esse formato, os metadados sozinhos serão indexados.</span><span class="sxs-lookup"><span data-stu-id="af26f-114">For any file that does not belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="af26f-115">Limites de tamanho de arquivo</span><span class="sxs-lookup"><span data-stu-id="af26f-115">File size limits</span></span>

<span data-ttu-id="af26f-116">O tamanho máximo de arquivo com suporte é de 100 MB.</span><span class="sxs-lookup"><span data-stu-id="af26f-116">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="af26f-117">Arquivos que excederem 100 MB não serão indexados.</span><span class="sxs-lookup"><span data-stu-id="af26f-117">Files that exceed 100 MB are not indexed.</span></span> <span data-ttu-id="af26f-118">O limite máximo de tamanho processado é de 4 MB.</span><span class="sxs-lookup"><span data-stu-id="af26f-118">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="af26f-119">O processamento pára quando o tamanho de um arquivo atinge 4 MB.</span><span class="sxs-lookup"><span data-stu-id="af26f-119">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="af26f-120">Portanto, algumas frases presentes no arquivo podem não funcionar para pesquisa.</span><span class="sxs-lookup"><span data-stu-id="af26f-120">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="af26f-121">Conectar-se a uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="af26f-121">Connect to a data source</span></span>

<span data-ttu-id="af26f-122">Na página **conectar-se à fonte de dados** , selecione **compartilhamento de arquivos** e forneça o nome, a ID de conexão e a descrição.</span><span class="sxs-lookup"><span data-stu-id="af26f-122">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="af26f-123">Na próxima página, forneça o caminho para o compartilhamento de arquivos e selecione seu agente do conector de gráfico instalado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="af26f-123">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="af26f-124">Insira as credenciais de uma conta de usuário do [Microsoft Windows](https://microsoft.com/windows) com acesso de leitura a todos os arquivos no compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="af26f-124">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

## <a name="preserve-last-access-time"></a><span data-ttu-id="af26f-125">Preservar o horário do último acesso</span><span class="sxs-lookup"><span data-stu-id="af26f-125">Preserve last access time</span></span>

<span data-ttu-id="af26f-126">Quando o conector tenta rastrear um arquivo, o campo "último horário de acesso" em seus metadados é atualizado.</span><span class="sxs-lookup"><span data-stu-id="af26f-126">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="af26f-127">Se você depender desse campo para qualquer solução de arquivamento e backup e não quiser atualizá-lo quando o conector acessá-lo, você pode configurar essa opção na página **Configurações avançadas** .</span><span class="sxs-lookup"><span data-stu-id="af26f-127">If you depend on that field for any archiving and backup solutions and do not want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="af26f-128">Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="af26f-128">Manage search permissions</span></span>

<span data-ttu-id="af26f-129">Você pode restringir a permissão para pesquisar qualquer arquivo com base nas listas de controle de acesso do compartilhamento ou nas listas de controle de acesso do sistema de arquivos de novas tecnologias (NTFS).</span><span class="sxs-lookup"><span data-stu-id="af26f-129">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists.</span></span> <span data-ttu-id="af26f-130">Se você quiser usar as listas de controle de acesso de compartilhamento, selecione a opção apropriada na página **Configurações avançadas** .</span><span class="sxs-lookup"><span data-stu-id="af26f-130">If you want to use Share Access Control Lists, select the appropriate option on the **Advanced settings** page.</span></span> <span data-ttu-id="af26f-131">Se quiser usar as listas de controle de acesso NTFS, selecione a opção apropriada na página **gerenciar permissões de pesquisa** .</span><span class="sxs-lookup"><span data-stu-id="af26f-131">If you want to use NTFS Access Control Lists, select the appropriate option on the **Manage search permissions** page.</span></span>

## <a name="assign-property-labels"></a><span data-ttu-id="af26f-132">Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="af26f-132">Assign property labels</span></span>

<span data-ttu-id="af26f-133">Você pode atribuir uma propriedade Source a cada rótulo escolhendo a partir de um menu de opções.</span><span class="sxs-lookup"><span data-stu-id="af26f-133">You can assign a source property to each label by choosing from a menu of options.</span></span> <span data-ttu-id="af26f-134">Embora esta etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá resultados de pesquisa mais precisos para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="af26f-134">While this step is not mandatory, having some property labels will improve the search relevance and ensure more accurate search results for end users.</span></span>

## <a name="manage-schema"></a><span data-ttu-id="af26f-135">Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="af26f-135">Manage schema</span></span>

<span data-ttu-id="af26f-136">Na tela **gerenciar esquema** , você tem a opção de alterar os atributos de esquema (**consultável**, **pesquisável**, **recuperável** e **refinável**) associados às propriedades, adicionar aliases opcionais e escolher a propriedade **Content** .</span><span class="sxs-lookup"><span data-stu-id="af26f-136">On the **Manage Schema** screen, you have the option to change the schema attributes (**queryable**, **searchable**, **retrievable**, and **refinable**) associated with the properties, add optional aliases, and choose the **Content** property.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="af26f-137">Definir o agendamento de atualização</span><span class="sxs-lookup"><span data-stu-id="af26f-137">Set the refresh schedule</span></span>

<span data-ttu-id="af26f-138">O intervalo de agendamento de atualização padrão recomendado é de 15 minutos, mas você pode alterá-lo com base em suas preferências.</span><span class="sxs-lookup"><span data-stu-id="af26f-138">The recommended default refresh schedule interval is 15 minutes, but you can change it based on your preferences.</span></span>
