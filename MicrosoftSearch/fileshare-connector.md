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
description: Configurar o conector gráfico de compartilhamento de arquivos para a Pesquisa da Microsoft
ms.openlocfilehash: ed1c148a018ba9492a8a93685327bf43153d65d3
ms.sourcegitcommit: 6a7522d9aeaedeedaac096c485d3f343ce98d3d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421068"
---
<!---Previous ms.author: rusamai --->

# <a name="file-share-graph-connector"></a><span data-ttu-id="7ff29-103">Conector graph de compartilhamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="7ff29-103">File share Graph connector</span></span>

<span data-ttu-id="7ff29-104">O conector graph de compartilhamento de arquivos permite que os usuários em sua organização pesquisem compartilhamentos de arquivos do Windows no local.</span><span class="sxs-lookup"><span data-stu-id="7ff29-104">The File share Graph connector allows users in your organization to search on-premise Windows file shares.</span></span>

> [!NOTE]
> <span data-ttu-id="7ff29-105">Leia o [**artigo Instalação do conector do Graph**](configure-connector.md) para entender o processo de configuração geral dos conectores do Graph.</span><span class="sxs-lookup"><span data-stu-id="7ff29-105">Read the [**Setup for your Graph connector**](configure-connector.md) article to understand the general Graph connectors setup process.</span></span>

## <a name="before-you-get-started"></a><span data-ttu-id="7ff29-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7ff29-106">Before you get started</span></span>

### <a name="install-the-graph-connector-agent"></a><span data-ttu-id="7ff29-107">Instalar o agente de conector do Graph</span><span class="sxs-lookup"><span data-stu-id="7ff29-107">Install the Graph connector agent</span></span>

<span data-ttu-id="7ff29-108">Para indexar seus compartilhamentos de arquivos do Windows, você deve instalar e registrar o agente conector do Graph.</span><span class="sxs-lookup"><span data-stu-id="7ff29-108">To index your Windows file shares, you must install and register the Graph connector agent.</span></span> <span data-ttu-id="7ff29-109">Consulte [Instalar o agente de conector do Graph](on-prem-agent.md) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="7ff29-109">See [Install the Graph connector agent](on-prem-agent.md) to learn more.</span></span>  

### <a name="content-requirements"></a><span data-ttu-id="7ff29-110">Requisitos de conteúdo</span><span class="sxs-lookup"><span data-stu-id="7ff29-110">Content requirements</span></span>

### <a name="file-types"></a><span data-ttu-id="7ff29-111">Tipos de arquivo</span><span class="sxs-lookup"><span data-stu-id="7ff29-111">File types</span></span>

<span data-ttu-id="7ff29-112">O conteúdo dos seguintes formatos pode ser indexado e pesquisado: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS e ZIP.</span><span class="sxs-lookup"><span data-stu-id="7ff29-112">Content of the following formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="7ff29-113">Somente o conteúdo textual desses formatos é indexado.</span><span class="sxs-lookup"><span data-stu-id="7ff29-113">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="7ff29-114">Todo o conteúdo multimídia é ignorado.</span><span class="sxs-lookup"><span data-stu-id="7ff29-114">All multimedia content is ignored.</span></span> <span data-ttu-id="7ff29-115">Para qualquer arquivo que não pertença a esse formato, os metadados são indexados.</span><span class="sxs-lookup"><span data-stu-id="7ff29-115">For any file that doesn't belong to this format, the metadata alone is indexed.</span></span>

### <a name="file-size-limits"></a><span data-ttu-id="7ff29-116">Limites de tamanho de arquivo</span><span class="sxs-lookup"><span data-stu-id="7ff29-116">File size limits</span></span>

<span data-ttu-id="7ff29-117">O tamanho máximo do arquivo com suporte é de 100 MB.</span><span class="sxs-lookup"><span data-stu-id="7ff29-117">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="7ff29-118">Os arquivos que excedem 100 MB não são indexados.</span><span class="sxs-lookup"><span data-stu-id="7ff29-118">Files that exceed 100 MB aren't indexed.</span></span> <span data-ttu-id="7ff29-119">O limite máximo de tamanho pós-processado é 4 MB.</span><span class="sxs-lookup"><span data-stu-id="7ff29-119">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="7ff29-120">O processamento é interrompido quando o tamanho de um arquivo atinge 4 MB.</span><span class="sxs-lookup"><span data-stu-id="7ff29-120">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="7ff29-121">Portanto, algumas frases presentes no arquivo podem não funcionar para pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7ff29-121">Therefore, some phrases present in the file might not work for search.</span></span>

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a><span data-ttu-id="7ff29-122">Etapa 1: Adicionar um conector graph no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7ff29-122">Step 1: Add a Graph connector in the Microsoft 365 admin center</span></span>

<span data-ttu-id="7ff29-123">Siga as instruções [gerais de instalação](https://docs.microsoft.com/microsoftsearch/configure-connector).</span><span class="sxs-lookup"><span data-stu-id="7ff29-123">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a><span data-ttu-id="7ff29-124">Etapa 2: nomear a conexão</span><span class="sxs-lookup"><span data-stu-id="7ff29-124">Step 2: Name the connection</span></span>

<span data-ttu-id="7ff29-125">Siga as instruções [gerais de instalação](https://docs.microsoft.com/microsoftsearch/configure-connector).</span><span class="sxs-lookup"><span data-stu-id="7ff29-125">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a><span data-ttu-id="7ff29-126">Etapa 3: Configurar as configurações de conexão</span><span class="sxs-lookup"><span data-stu-id="7ff29-126">Step 3: Configure the connection settings</span></span>

<span data-ttu-id="7ff29-127">Na página **Conectar-se à fonte de** dados, selecione **Compartilhamento** de arquivos e forneça o nome, a ID da conexão e a descrição.</span><span class="sxs-lookup"><span data-stu-id="7ff29-127">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="7ff29-128">Na próxima página, forneça o caminho para o compartilhamento de arquivos e selecione o agente de conector do Graph instalado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7ff29-128">On the next page, provide the path to the file share and select your previously installed Graph connector agent.</span></span> <span data-ttu-id="7ff29-129">Insira as credenciais de uma conta de usuário do [Microsoft Windows](https://microsoft.com/windows) com acesso de leitura a todos os arquivos no compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="7ff29-129">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the file share.</span></span>

### <a name="preserve-last-access-time"></a><span data-ttu-id="7ff29-130">Preservar a última hora de acesso</span><span class="sxs-lookup"><span data-stu-id="7ff29-130">Preserve last access time</span></span>

<span data-ttu-id="7ff29-131">Quando o conector tenta rastrear um arquivo, o campo "última hora de acesso" em seus metadados é atualizado.</span><span class="sxs-lookup"><span data-stu-id="7ff29-131">When the connector attempts to crawl a file, the "last access time" field in its metadata is updated.</span></span> <span data-ttu-id="7ff29-132">Se você depender desse campo para qualquer solução de arquivamento e backup e não quiser atualizá-lo quando o conector acessá-lo, você poderá configurar essa opção na página Configurações **Avançadas.**</span><span class="sxs-lookup"><span data-stu-id="7ff29-132">If you depend on that field for any archiving and backup solutions and doesn't want to update it when the connector accesses it, you can configure this option in the **Advanced settings** page.</span></span>

## <a name="step-4-manage-search-permissions"></a><span data-ttu-id="7ff29-133">Etapa 4: Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="7ff29-133">Step 4: Manage search permissions</span></span>

<span data-ttu-id="7ff29-134">Você pode restringir a permissão para pesquisar qualquer arquivo com base em Listas de Controle do Share Access ou Listas de Controle de Acesso do Sistema de Arquivos de Nova Tecnologia (NTFS), selecionando a opção desejada na página Gerenciar permissões **de** pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7ff29-134">You can restrict the permission to search for any file based on Share Access Control Lists or New Technology File System (NTFS) Access Control Lists, by selecting the desired option in **Manage search permissions** page.</span></span> <span data-ttu-id="7ff29-135">As contas de usuário e os grupos fornecidos nessas Listas de Controle de Acesso devem ser gerenciados pelo Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="7ff29-135">The user accounts and groups provided in these Access Control Lists must be managed by Active Directory (AD).</span></span> <span data-ttu-id="7ff29-136">Se você estiver usando qualquer outro sistema para gerenciamento de contas de usuário, poderá selecionar a opção "todos", que permite que os usuários pesquisem todos os arquivos sem restrições de acesso.</span><span class="sxs-lookup"><span data-stu-id="7ff29-136">If you are using any other system for user accounts management, you can select 'everyone' option, which lets users search for all the files without any access restrictions.</span></span> <span data-ttu-id="7ff29-137">No entanto, quando os usuários tentam abrir o arquivo, os controles de acesso definidos na origem se aplicam.</span><span class="sxs-lookup"><span data-stu-id="7ff29-137">However, when users try to open the file, access controls set at the source apply.</span></span>

<span data-ttu-id="7ff29-138">Observe que as janelas por padrão fornece permissão 'Ler' para 'Todos' em AcLs do Share quando uma pasta é compartilhada na rede.</span><span class="sxs-lookup"><span data-stu-id="7ff29-138">Note that windows by default provides 'Read' permission to 'Everyone' in Share ACLs when a folder is shared on network.</span></span> <span data-ttu-id="7ff29-139">Por extensão, se você estiver escolhendo Compartilhar ACLs em **Gerenciar** permissões de pesquisa, os usuários poderão pesquisar todos os arquivos.</span><span class="sxs-lookup"><span data-stu-id="7ff29-139">By extension, if you are choosing Share ACLs in **Manage search permissions**, users will be able to search for all the files.</span></span> <span data-ttu-id="7ff29-140">Se você quiser restringir o acesso, remova o acesso 'Leitura' para 'Todos' em compartilhamentos de arquivos e forneça acesso somente aos usuários e grupos desejados.</span><span class="sxs-lookup"><span data-stu-id="7ff29-140">If you want to restrict access, remove 'Read' access for 'Everyone' in file shares and provide access only to the desired users and groups.</span></span> <span data-ttu-id="7ff29-141">Em seguida, o conector lê essas restrições de acesso e as aplica à pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7ff29-141">The connector then reads these access restrictions and applies them to search.</span></span>

<span data-ttu-id="7ff29-142">Você pode escolher Compartilhar ACLs somente se o caminho de compartilhamento fornecido seguir o formato de caminho UNC.</span><span class="sxs-lookup"><span data-stu-id="7ff29-142">You can choose Share ACLs only if the share path you provided follows UNC path format.</span></span> <span data-ttu-id="7ff29-143">Você pode criar um caminho no formato UNC indo para 'Compartilhamento Avançado' na opção 'Compartilhamento'.</span><span class="sxs-lookup"><span data-stu-id="7ff29-143">You can create a path in UNC format by going to 'Advanced Sharing' under 'Sharing' option.</span></span>

![Advanced_sharing](media/file-connector/file-advanced-sharing.png)

## <a name="step-5-assign-property-labels"></a><span data-ttu-id="7ff29-145">Etapa 5: Atribuir rótulos de propriedade</span><span class="sxs-lookup"><span data-stu-id="7ff29-145">Step 5: Assign property labels</span></span>

<span data-ttu-id="7ff29-146">Siga as instruções [gerais de instalação](https://docs.microsoft.com/microsoftsearch/configure-connector).</span><span class="sxs-lookup"><span data-stu-id="7ff29-146">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-6-manage-schema"></a><span data-ttu-id="7ff29-147">Etapa 6: Gerenciar esquema</span><span class="sxs-lookup"><span data-stu-id="7ff29-147">Step 6: Manage schema</span></span>

<span data-ttu-id="7ff29-148">Siga as instruções [gerais de instalação](https://docs.microsoft.com/microsoftsearch/configure-connector).</span><span class="sxs-lookup"><span data-stu-id="7ff29-148">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-7-choose-refresh-settings"></a><span data-ttu-id="7ff29-149">Etapa 7: Escolher configurações de atualização</span><span class="sxs-lookup"><span data-stu-id="7ff29-149">Step 7: Choose refresh settings</span></span>

<span data-ttu-id="7ff29-150">Siga as instruções [gerais de instalação](https://docs.microsoft.com/microsoftsearch/configure-connector).</span><span class="sxs-lookup"><span data-stu-id="7ff29-150">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-8-review-connection"></a><span data-ttu-id="7ff29-151">Etapa 8: Revisar conexão</span><span class="sxs-lookup"><span data-stu-id="7ff29-151">Step 8: Review connection</span></span>

<span data-ttu-id="7ff29-152">Siga as instruções [gerais de instalação](https://docs.microsoft.com/microsoftsearch/configure-connector).</span><span class="sxs-lookup"><span data-stu-id="7ff29-152">Follow the general [setup instructions](https://docs.microsoft.com/microsoftsearch/configure-connector).</span></span>
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup 
instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

<!---## Limitations-->
<!---Insert limitations for this data source-->
