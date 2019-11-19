---
title: Conector de compartilhamento de arquivos para o Microsoft Search
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configure o conector de compartilhamento de arquivos para o Microsoft Search.
ms.openlocfilehash: ece8997138182c1cd4ac7230aa2a3501af912933
ms.sourcegitcommit: 68087149c769a7cdde80944dd9c9933d2bf4a23f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "38699771"
---
# <a name="the-file-share-connector-for-microsoft-search"></a><span data-ttu-id="b1978-103">O conector de compartilhamento de arquivos da pesquisa da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b1978-103">The file share connector for Microsoft Search</span></span>

<span data-ttu-id="b1978-104">Com o conector de compartilhamento de arquivos, os usuários da sua organização podem pesquisar em compartilhamentos de arquivos locais.</span><span class="sxs-lookup"><span data-stu-id="b1978-104">With the file share connector, users in your organization can search on-premises file shares.</span></span> <span data-ttu-id="b1978-105">Os resultados da pesquisa desses compartilhamentos são mesclados com os resultados do [SharePoint](http://sharepoint.com/) e do [Microsoft onedrive for Business](https://onedrive.live.com/about/business/).</span><span class="sxs-lookup"><span data-stu-id="b1978-105">The search results from these shares merge with the results from [SharePoint](http://sharepoint.com/) and [Microsoft OneDrive for Business](https://onedrive.live.com/about/business/).</span></span>

<span data-ttu-id="b1978-106">Este artigo é para os administradores do [Microsoft 365](https://www.microsoft.com/microsoft-365) ou qualquer pessoa que configure, execute e monitore um conector de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="b1978-106">This article is for [Microsoft 365](https://www.microsoft.com/microsoft-365) administrators or anyone who configures, runs, and monitors a file share connector.</span></span> <span data-ttu-id="b1978-107">Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="b1978-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-a-data-gateway"></a><span data-ttu-id="b1978-108">Instalar um data gateway</span><span class="sxs-lookup"><span data-stu-id="b1978-108">Install a data gateway</span></span>
<span data-ttu-id="b1978-109">Para acessar seus dados de terceiros, você deve instalar e configurar um gateway [do Microsoft Power bi](https://msit.powerbi.com/) .</span><span class="sxs-lookup"><span data-stu-id="b1978-109">In order to access your third-party data, you must install and configure a [Microsoft Power BI](https://msit.powerbi.com/) gateway.</span></span> <span data-ttu-id="b1978-110">Confira [instalar um gateway local](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="b1978-110">See [Install an on-premises gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) to learn more.</span></span>  

## <a name="content-requirements"></a><span data-ttu-id="b1978-111">Requisitos de conteúdo</span><span class="sxs-lookup"><span data-stu-id="b1978-111">Content requirements</span></span>
<span data-ttu-id="b1978-112">**Tipos de arquivo**.</span><span class="sxs-lookup"><span data-stu-id="b1978-112">**File types**.</span></span> <span data-ttu-id="b1978-113">Somente arquivos nestes formatos podem ser indexados e pesquisados: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, NWS, OBT, OBD,, PPS, ODS, ODT, a, PDF, POT e PPS, o e o formato. XLS, o, o, o XML e o formato ZIP do.</span><span class="sxs-lookup"><span data-stu-id="b1978-113">Only files in these formats can be indexed and searched: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, MSG, NWS, OBD, OBT, ODP, ODS, ODT, ONE, PDF, POT, PPS, PPT, PPTM, PPTX, TXT, XLB, XLC, XLSB, XLS, XLSX, XLT, XLXM, XML, XPS, and ZIP.</span></span> <span data-ttu-id="b1978-114">Somente o conteúdo textual desses formatos é indexado.</span><span class="sxs-lookup"><span data-stu-id="b1978-114">Only the textual content of these formats is indexed.</span></span> <span data-ttu-id="b1978-115">Todo o conteúdo multimídia é ignorado.</span><span class="sxs-lookup"><span data-stu-id="b1978-115">All multimedia content is ignored.</span></span>
 
<span data-ttu-id="b1978-116">**Limites de tamanho de arquivo**.</span><span class="sxs-lookup"><span data-stu-id="b1978-116">**File size limits**.</span></span> <span data-ttu-id="b1978-117">O tamanho máximo de arquivo com suporte é de 100 MB.</span><span class="sxs-lookup"><span data-stu-id="b1978-117">The maximum supported file size is 100 MB.</span></span> <span data-ttu-id="b1978-118">Arquivos que excedem 100 MB são ignorados da indexação.</span><span class="sxs-lookup"><span data-stu-id="b1978-118">Files that exceed 100 MB are skipped from indexing.</span></span> <span data-ttu-id="b1978-119">O limite máximo de tamanho processado é de 4 MB.</span><span class="sxs-lookup"><span data-stu-id="b1978-119">The maximum post-processed size limit is 4 MB.</span></span> <span data-ttu-id="b1978-120">O processamento pára quando o tamanho de um arquivo atinge 4 MB.</span><span class="sxs-lookup"><span data-stu-id="b1978-120">Processing stops when a file's size reaches 4 MB.</span></span> <span data-ttu-id="b1978-121">Como resultado, algumas frases presentes no arquivo podem não funcionar para pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b1978-121">As a result, some phrases present in the file might not work for search.</span></span>

## <a name="connect-to-a-data-source"></a><span data-ttu-id="b1978-122">Conectar-se a uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="b1978-122">Connect to a data source</span></span>
<span data-ttu-id="b1978-123">Na página **conectar-se à fonte de dados** , selecione **compartilhamento de arquivos** e forneça o nome, a ID de conexão e a descrição.</span><span class="sxs-lookup"><span data-stu-id="b1978-123">On the **Connect to data source** page, select **File share** and provide the name, connection ID, and description.</span></span> <span data-ttu-id="b1978-124">Na próxima página, forneça o caminho para o compartilhamento de arquivo e selecione seu gateway instalado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b1978-124">On the next page, provide the path to the file share and select your previously installed gateway.</span></span> <span data-ttu-id="b1978-125">Insira as credenciais de uma conta de usuário do [Microsoft Windows](https://microsoft.com/windows) com acesso de leitura para todos os arquivos no compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="b1978-125">Enter the credentials for a [Microsoft Windows](https://microsoft.com/windows) user account with read access to all the files in the share.</span></span> <span data-ttu-id="b1978-126">Passe o resto das configurações e publique a conexão.</span><span class="sxs-lookup"><span data-stu-id="b1978-126">Go through the rest of the settings and publish the connection.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="b1978-127">Definir o agendamento de atualização</span><span class="sxs-lookup"><span data-stu-id="b1978-127">Set the refresh schedule</span></span>
<span data-ttu-id="b1978-128">O intervalo de agendamento de atualização padrão recomendado é de 15 minutos, mas você pode alterá-lo para outro intervalo de sua preferência.</span><span class="sxs-lookup"><span data-stu-id="b1978-128">The recommended default refresh schedule interval is 15 minutes, but you can change it to another interval that you prefer.</span></span>

## <a name="set-up-your-search-results-page"></a><span data-ttu-id="b1978-129">Configurar a página de resultados de pesquisa</span><span class="sxs-lookup"><span data-stu-id="b1978-129">Set up your search results page</span></span>
<span data-ttu-id="b1978-130">Para exibir os resultados de conexão de arquivos diferentes nas guias **todos** e **arquivos** , você precisa configurar uma página de resultados do mecanismo de pesquisa [do SharePoint](http://sharepoint.com/) :</span><span class="sxs-lookup"><span data-stu-id="b1978-130">To display different file connection results in the **All** and **Files** tabs, you need to set up a [SharePoint](http://sharepoint.com/) search engine results page:</span></span>
- <span data-ttu-id="b1978-131">A tabela **All** mostra os resultados combinados de suas conexões de arquivo, arquivos do SharePoint, arquivos do [onedrive](https://onedrive.live.com/about/business/) e sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b1978-131">The **All** table shows combined results from your file connections, SharePoint files, [OneDrive](https://onedrive.live.com/about/business/) files, and SharePoint sites.</span></span> 
- <span data-ttu-id="b1978-132">O arquivo vertical mostra todos os resultados **de arquivos de** suas conexões, do SharePoint e do onedrive.</span><span class="sxs-lookup"><span data-stu-id="b1978-132">The **Files** vertical shows all file results from your connections, SharePoint, and OneDrive.</span></span>
<span data-ttu-id="b1978-133">Os resultados das conexões de arquivo são adicionados aos resultados já existentes em **todos** os **arquivos** verticais.</span><span class="sxs-lookup"><span data-stu-id="b1978-133">Results from file connections are added to already existing results in both the **All** and **Files** verticals.</span></span>

<span data-ttu-id="b1978-134">Para configurar a página de resultados da pesquisa, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b1978-134">To set up your search results page, take these steps:</span></span>
1. <span data-ttu-id="b1978-135">Crie um conjunto de sites do SharePoint com uma página de pesquisa moderna.</span><span class="sxs-lookup"><span data-stu-id="b1978-135">Create a SharePoint site collection with a modern search page.</span></span>

2. <span data-ttu-id="b1978-136">Instale um [Shell de gerenciamento do SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588).</span><span class="sxs-lookup"><span data-stu-id="b1978-136">Install a [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

3. <span data-ttu-id="b1978-137">Abra o Shell de gerenciamento do SharePoint Online como administrador e importe o módulo **Microsoft. SharePoint. Client. dll** presente em `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`.</span><span class="sxs-lookup"><span data-stu-id="b1978-137">Open SharePoint Online Management Shell as an administrator and import the **Microsoft.SharePoint.Client.dll** module present at `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`.</span></span>

> [!NOTE]
> <span data-ttu-id="b1978-138">Esse caminho pode não ser o mesmo para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="b1978-138">This path might not be the same for all users.</span></span>

<span data-ttu-id="b1978-139">Para importar o módulo, execute este comando no [Shell de gerenciamento do SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588):</span><span class="sxs-lookup"><span data-stu-id="b1978-139">To import the module, run this command in [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588):</span></span>
```bash
Import-Module "C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll" 
```

4. <span data-ttu-id="b1978-140">Agora, execute este script:</span><span class="sxs-lookup"><span data-stu-id="b1978-140">Now run this script:</span></span>
```bash
$orgName = Read-Host -prompt 'Please enter your org name'
$userName = Read-Host -prompt 'Enter user name'
$userCreds = Get-Credential -UserName $userName -Message "Type the password"
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCreds

$url = Read-Host -Prompt 'Please enter the site url'
$site = Get-SPOSite -Identity $url
Set-SPOSite $url -DenyAddAndCustomizePages 0

$pwd = Read-Host -AsSecureString 'type the password'
$context = New-Object Microsoft.SharePoint.Client.ClientContext($url)
$credential = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($userName, $pwd)
$context.Credentials = $credential
$web = $context.Web
$context.Load($web)
$web.AllProperties["AllVerticalContent"] = "Combined"
$web.Update()
$context.ExecuteQuery()
$web.AllProperties["FilesVerticalContent"] = "ConnectorsOnly"
$web.Update()
$context.ExecuteQuery()
Set-SPOSite $url -DenyAddAndCustomizePages 1

Write-Host "Success" -ForegroundColor Cyan
Read-Host -Prompt 'Press enter to exit'
```

5. <span data-ttu-id="b1978-141">Insira os valores necessários no [Microsoft PowerShell](https://microsoft.com/powershell), como nome da organização, nome de usuário, senha e URL do site.</span><span class="sxs-lookup"><span data-stu-id="b1978-141">Enter the required values in [Microsoft PowerShell](https://microsoft.com/powershell), such as organization name, username, password, and site URL.</span></span> <span data-ttu-id="b1978-142">Por **exemplo**, se suas credenciais de administrador são `admin@a830edad9050849823J19081300.onmicrosoft.com`, o nome da sua organização é **a830edad9050849823J19081300**e a URL do site `https:// a830edad9050849823J19081300.sharepoint.com`é.</span><span class="sxs-lookup"><span data-stu-id="b1978-142">As an **example**, if your admin credentials are `admin@a830edad9050849823J19081300.onmicrosoft.com`, then your organization name is **a830edad9050849823J19081300**, and your site URL is `https:// a830edad9050849823J19081300.sharepoint.com`.</span></span>

> [!NOTE]
> <span data-ttu-id="b1978-143">A configuração de **propriedadeproperties** só pode ser feita em um nível de conjunto de sites (site de equipe/comms).</span><span class="sxs-lookup"><span data-stu-id="b1978-143">The **AllProperties** setting can only be done at a site collection level (Teams/Comms site).</span></span>

6. <span data-ttu-id="b1978-144">Agora você pode pesquisar arquivos indexados e ver resultados nas guias **todos** e **arquivos** .</span><span class="sxs-lookup"><span data-stu-id="b1978-144">Now you can search for indexed files and see results in both the **All** and **Files** tabs.</span></span>

## <a name="search-for-file-share-content-in-the-search-results-page"></a><span data-ttu-id="b1978-145">Pesquisar conteúdo de compartilhamento de arquivo na página de resultados de pesquisa</span><span class="sxs-lookup"><span data-stu-id="b1978-145">Search for file share content in the search results page</span></span>
<span data-ttu-id="b1978-146">Para pesquisar conteúdo indexado, vá para a página inicial do [SharePoint](http://sharepoint.com/) do seu locatário de teste.</span><span class="sxs-lookup"><span data-stu-id="b1978-146">To search for indexed content, go to the [SharePoint](http://sharepoint.com/) home page of your test tenant.</span></span> <span data-ttu-id="b1978-147">Os resultados serão exibidos nas guias **todos** e **arquivos** .</span><span class="sxs-lookup"><span data-stu-id="b1978-147">Results will be displayed in the **All** and **Files** tabs.</span></span>

<span data-ttu-id="b1978-148">Devido às restrições do navegador, não é possível selecionar um resultado de arquivo para exibir ou abrir arquivos de pesquisas de compartilhamento de arquivos local.</span><span class="sxs-lookup"><span data-stu-id="b1978-148">Because of browser restrictions, you can't select a file result to view or open files from local file share searches.</span></span> <span data-ttu-id="b1978-149">Para abrir esses arquivos, copie o link do resultado do arquivo e cole-o na barra de endereços do navegador do seu sistema.</span><span class="sxs-lookup"><span data-stu-id="b1978-149">To open these files, copy the file result's link and paste it into the address bar of your system's browser.</span></span> <span data-ttu-id="b1978-150">Para o [Windows](https://microsoft.com/windows), use o Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="b1978-150">For [Windows](https://microsoft.com/windows), use Windows Explorer.</span></span> <span data-ttu-id="b1978-151">Em seguida, você pode abrir o arquivo no sistema.</span><span class="sxs-lookup"><span data-stu-id="b1978-151">Then you can open the file on your system.</span></span>

![Pesquisa do SharePoint com a caixa de diálogo Copiar link aberta.](media/fileshare-search.png)

## <a name="troubleshooting"></a><span data-ttu-id="b1978-153">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="b1978-153">Troubleshooting</span></span>
<span data-ttu-id="b1978-154">Se algo estiver muito errado com uma conexão, seu status será exibido como **falha**.</span><span class="sxs-lookup"><span data-stu-id="b1978-154">If something is critically wrong with a connection, its status shows as **failed**.</span></span> <span data-ttu-id="b1978-155">Para obter mais informações sobre os três tipos de erros, vá para a página de **detalhes do erro** e selecione a conexão com falha.</span><span class="sxs-lookup"><span data-stu-id="b1978-155">To get more information on the three types of errors, go to the **error details** page and select the failing connection.</span></span> <span data-ttu-id="b1978-156">Confira [gerenciar seu conector](manage-connector.md) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="b1978-156">See [Manage your connector](manage-connector.md) to learn more.</span></span>
1. <span data-ttu-id="b1978-157">**Gateway não acessível (código de erro: 11)**.</span><span class="sxs-lookup"><span data-stu-id="b1978-157">**Gateway not reachable (error code: 11)**.</span></span> <span data-ttu-id="b1978-158">A máquina gateway para a conexão está inativa.</span><span class="sxs-lookup"><span data-stu-id="b1978-158">The gateway machine for the connection is down.</span></span> <span data-ttu-id="b1978-159">Verifique se o processo do [Power bi](https://msit.powerbi.com/) é executado no computador do gateway.</span><span class="sxs-lookup"><span data-stu-id="b1978-159">Verify if the [Power BI](https://msit.powerbi.com/) process runs on the gateway machine.</span></span>
2. <span data-ttu-id="b1978-160">**Erro de autenticação (código de erro: 12)**.</span><span class="sxs-lookup"><span data-stu-id="b1978-160">**Authentication error (error code: 12)**.</span></span> <span data-ttu-id="b1978-161">As credenciais que foram usadas para criar a conexão expiraram ou não são mais válidas.</span><span class="sxs-lookup"><span data-stu-id="b1978-161">The credentials that were used for creating the connection expired or are no longer valid.</span></span> <span data-ttu-id="b1978-162">Para resolver esse erro, insira as credenciais válidas.</span><span class="sxs-lookup"><span data-stu-id="b1978-162">To resolve this error, enter valid credentials.</span></span>
3. <span data-ttu-id="b1978-163">**Erro interno (código de erro: qualquer coisa diferente de 11 ou 12)**.</span><span class="sxs-lookup"><span data-stu-id="b1978-163">**Internal error (error code: anything other than 11 or 12)**.</span></span> <span data-ttu-id="b1978-164">Há um erro na infraestrutura do conector.</span><span class="sxs-lookup"><span data-stu-id="b1978-164">There's an error in the connector infrastructure.</span></span> <span data-ttu-id="b1978-165">Confira o artigo de [feedback](connectors-feedback.md) para saber como relatar esses erros.</span><span class="sxs-lookup"><span data-stu-id="b1978-165">See the [Feedback](connectors-feedback.md) article to find out how to report these errors.</span></span>

## <a name="limitations"></a><span data-ttu-id="b1978-166">Limitações</span><span class="sxs-lookup"><span data-stu-id="b1978-166">Limitations</span></span>
<span data-ttu-id="b1978-167">O conector de compartilhamento de arquivos tem estas limitações na versão prévia:</span><span class="sxs-lookup"><span data-stu-id="b1978-167">The file share connector has these limitations in the preview release:</span></span>
* <span data-ttu-id="b1978-168">Você só pode indexar arquivos com propriedades fixas, não arquivos com propriedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b1978-168">You can only index files with fixed properties, not files with custom properties.</span></span>
* <span data-ttu-id="b1978-169">As listas de controle de acesso (ACLs) do compartilhamento de arquivos não são suportadas atualmente.</span><span class="sxs-lookup"><span data-stu-id="b1978-169">File share Access Control Lists (ACLs) aren't currently supported.</span></span> <span data-ttu-id="b1978-170">Só há suporte para ACLs de NTFS de arquivo.</span><span class="sxs-lookup"><span data-stu-id="b1978-170">Only file NTFS ACLs are supported.</span></span>
* <span data-ttu-id="b1978-171">Identidades externas não são suportadas.</span><span class="sxs-lookup"><span data-stu-id="b1978-171">External identities aren't supported.</span></span> <span data-ttu-id="b1978-172">Eles devem ser mapeados para identidades [do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) .</span><span class="sxs-lookup"><span data-stu-id="b1978-172">They must be mapped to [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) identities.</span></span>
