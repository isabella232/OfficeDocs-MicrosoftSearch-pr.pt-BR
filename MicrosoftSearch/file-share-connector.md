---
title: Conector de compartilhamento de arquivos para o Microsoft Search
ms.author: v-pamcn
author: TrishaMc1
manager: mnirkhe
ms.date: 10/08/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configure o conector de compartilhamento de arquivos para o Microsoft Search.
ms.openlocfilehash: d5fbc1af2868ce7baa70017f617a9731340fb19a
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949535"
---
# <a name="file-share-connector"></a><span data-ttu-id="2ed5b-103">Conector de compartilhamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="2ed5b-103">File share connector</span></span>

<span data-ttu-id="2ed5b-104">Com o conector de compartilhamento de arquivos, os usuários da sua organização podem pesquisar em compartilhamentos de arquivos locais.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-104">With the File share connector, users in your organization can search on-premises file shares.</span></span> <span data-ttu-id="2ed5b-105">Os resultados da pesquisa desses compartilhamentos são mesclados com os resultados do SharePoint e do Microsoft OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-105">The search results from these shares merge with the results from SharePoint and Microsoft OneDrive for Business.</span></span>

<span data-ttu-id="2ed5b-106">Este artigo é para os administradores do Microsoft 365 ou qualquer pessoa que configure, execute e monitore um conector de compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-106">This article is for Microsoft 365 administrators or anyone who configures, runs, and monitors a File share connector.</span></span> <span data-ttu-id="2ed5b-107">Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-107">It explains how to configure your connector and connector capabilities, limitations, and troubleshooting techniques.</span></span>

## <a name="install-a-data-gateway"></a><span data-ttu-id="2ed5b-108">Instalar um data gateway</span><span class="sxs-lookup"><span data-stu-id="2ed5b-108">Install a data gateway</span></span>
<span data-ttu-id="2ed5b-109">Para acessar seus dados de terceiros, você deve instalar e configurar um gateway do Microsoft Power BI.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-109">In order to access your third-party data, you must install and configure a Microsoft Power BI gateway.</span></span> <span data-ttu-id="2ed5b-110">Consulte [Install and local gateway on-premises](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-110">See [Install and on-premises gateway](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) to learn more.</span></span>  

## <a name="connect-to-a-data-source"></a><span data-ttu-id="2ed5b-111">Conectar-se a uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="2ed5b-111">Connect to a data source</span></span>
<span data-ttu-id="2ed5b-112">Na página **conectar-se à fonte de dados** , crie uma pasta e forneça um caminho para o compartilhamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-112">On the **Connect to data source** page, create a folder and provide a path to the file share.</span></span> <span data-ttu-id="2ed5b-113">Em seguida, selecione o gateway instalado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-113">Then select your previously installed gateway.</span></span> <span data-ttu-id="2ed5b-114">Insira as credenciais de uma conta de usuário do Windows com **acesso de leitura** para todos os arquivos no compartilhamento.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-114">Enter the credentials for a Windows user account with **read access** to all the files in the share.</span></span> <span data-ttu-id="2ed5b-115">Em seguida, você pode verificar os arquivos presentes no compartilhamento e ver todos os metadados buscados.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-115">You can then verify the files present in the share and see all the fetched metadata.</span></span>

## <a name="manage-search-permissions"></a><span data-ttu-id="2ed5b-116">Gerenciar permissões de pesquisa</span><span class="sxs-lookup"><span data-stu-id="2ed5b-116">Manage search permissions</span></span>
<span data-ttu-id="2ed5b-117">O conector de compartilhamento de arquivos só oferece suporte a permissões de pesquisa visíveis para **todos**.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-117">The File share connector only supports search permissions visible to **Everyone**.</span></span> <span data-ttu-id="2ed5b-118">Dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários da organização.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-118">Indexed data appears in the search results and is visible to all users in the organization.</span></span>

## <a name="set-the-refresh-schedule"></a><span data-ttu-id="2ed5b-119">Definir o agendamento de atualização</span><span class="sxs-lookup"><span data-stu-id="2ed5b-119">Set the refresh schedule</span></span>
<span data-ttu-id="2ed5b-120">O intervalo de agendamento de atualização padrão recomendado é de 15 minutos, mas você pode alterá-lo para outro intervalo de sua preferência.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-120">The recommended default refresh schedule interval is 15 minutes, but you can change it to another interval that you prefer.</span></span>

## <a name="set-up-your-search-results-page"></a><span data-ttu-id="2ed5b-121">Configurar a página de resultados de pesquisa</span><span class="sxs-lookup"><span data-stu-id="2ed5b-121">Set up your search results page</span></span>
<span data-ttu-id="2ed5b-122">Para exibir os resultados de conexão de arquivos diferentes nas guias **todos** e **arquivos** , você precisa configurar uma página de resultados do mecanismo de pesquisa do SharePoint:</span><span class="sxs-lookup"><span data-stu-id="2ed5b-122">To display different file connection results in the **All** and **Files** tabs, you need to set up a SharePoint search engine results page:</span></span>
- <span data-ttu-id="2ed5b-123">A tabela **All** mostra os resultados combinados de suas conexões de arquivo, arquivos do SharePoint, arquivos do onedrive e sites do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-123">The **All** table shows combined results from your file connections, SharePoint files, OneDrive files, and SharePoint sites.</span></span> 
- <span data-ttu-id="2ed5b-124">O arquivo vertical mostra todos os resultados **de arquivos de** suas conexões, do SharePoint e do onedrive.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-124">The **Files** vertical shows all file results from your connections, SharePoint, and OneDrive.</span></span>
<span data-ttu-id="2ed5b-125">Os resultados das conexões de arquivo são adicionados aos resultados já existentes em **todos** os **arquivos** verticais.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-125">Results from file connections are added to already existing results in both the **All** and **Files** verticals.</span></span>

<span data-ttu-id="2ed5b-126">Para configurar a página de resultados da pesquisa, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2ed5b-126">To set up your search results page, take these steps:</span></span>
1. <span data-ttu-id="2ed5b-127">Crie um conjunto de sites do SharePoint com uma página de pesquisa moderna.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-127">Create a SharePoint site collection with a modern search page.</span></span>

2. <span data-ttu-id="2ed5b-128">Instale um [Shell de gerenciamento do SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588).</span><span class="sxs-lookup"><span data-stu-id="2ed5b-128">Install a [SharePoint Online Management Shell](https://www.microsoft.com/download/details.aspx?id=35588).</span></span>

3. <span data-ttu-id="2ed5b-129">Abra o Shell de gerenciamento do SharePoint Online como administrador e importe o módulo **Microsoft. SharePoint. Client. dll** presente em `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-129">Open SharePoint Online Management Shell as an administrator and import the **Microsoft.SharePoint.Client.dll** module present at `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll`.</span></span>

> [!NOTE]
> <span data-ttu-id="2ed5b-130">Esse caminho pode não ser o mesmo para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-130">This path might not be the same for all users.</span></span>

<span data-ttu-id="2ed5b-131">Para importar o módulo, execute este comando no Shell de gerenciamento do SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="2ed5b-131">To import the module, run this command in SharePoint Online Management Shell:</span></span>
```bash
Import-Module "C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll" 
```

4. <span data-ttu-id="2ed5b-132">Agora, execute este script:</span><span class="sxs-lookup"><span data-stu-id="2ed5b-132">Now run this script:</span></span>
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

5. <span data-ttu-id="2ed5b-133">Insira os valores necessários no PowerShell, como nome da organização, nome de usuário, senha e URL do site.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-133">Enter the required values in PowerShell, such as organization name, username, password, and site URL.</span></span> <span data-ttu-id="2ed5b-134">Por **exemplo**, se suas credenciais de administrador são `admin@a830edad9050849823J19081300.onmicrosoft.com`, o nome da sua organização é **a830edad9050849823J19081300**e a URL do site `https:// a830edad9050849823J19081300.sharepoint.com`é.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-134">As an **example**, if your admin credentials are `admin@a830edad9050849823J19081300.onmicrosoft.com`, then your organization name is **a830edad9050849823J19081300**, and your site URL is `https:// a830edad9050849823J19081300.sharepoint.com`.</span></span>

> [!NOTE]
> <span data-ttu-id="2ed5b-135">A configuração de **propriedadeproperties** só pode ser feita em um nível de conjunto de sites (site de equipe/comms).</span><span class="sxs-lookup"><span data-stu-id="2ed5b-135">The **AllProperties** setting can only be done at a site collection level (Teams/Comms site).</span></span>

6. <span data-ttu-id="2ed5b-136">Agora você pode pesquisar arquivos indexados e ver resultados nas guias **todos** e **arquivos** .</span><span class="sxs-lookup"><span data-stu-id="2ed5b-136">Now you can search for indexed files and see results in both the **All** and **Files** tabs.</span></span>

## <a name="search-for-file-share-content-in-the-search-results-page"></a><span data-ttu-id="2ed5b-137">Pesquisar conteúdo de compartilhamento de arquivo na página de resultados de pesquisa</span><span class="sxs-lookup"><span data-stu-id="2ed5b-137">Search for file share content in the search results page</span></span>
<span data-ttu-id="2ed5b-138">Para pesquisar conteúdo indexado, vá para a página inicial do SharePoint do seu locatário de teste.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-138">To search for indexed content, go to the SharePoint home page of your test tenant.</span></span> <span data-ttu-id="2ed5b-139">Os resultados serão exibidos nas guias **todos** e **arquivos** .</span><span class="sxs-lookup"><span data-stu-id="2ed5b-139">Results will be displayed in the **All** and **Files** tabs.</span></span>

<span data-ttu-id="2ed5b-140">Devido às restrições do navegador, não é possível selecionar um resultado de arquivo para exibir ou abrir arquivos de pesquisas de compartilhamento de arquivos local.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-140">Because of browser restrictions, you can't select a file result to view or open files from local file share searches.</span></span> <span data-ttu-id="2ed5b-141">Para abrir esses arquivos, copie o link do resultado do arquivo e cole-o na barra de endereços do navegador do seu sistema.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-141">To open these files, copy the file result's link and paste it into the address bar of your system's browser.</span></span> <span data-ttu-id="2ed5b-142">Para o Windows, use o Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-142">For Windows, use Windows Explorer.</span></span> <span data-ttu-id="2ed5b-143">Em seguida, você pode abrir o arquivo no sistema.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-143">Then you can open the file on your system.</span></span>

![Pesquisa do SharePoint com a caixa de diálogo Copiar link aberta.](media/fileshare-search.png)

## <a name="troubleshooting"></a><span data-ttu-id="2ed5b-145">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="2ed5b-145">Troubleshooting</span></span>
<span data-ttu-id="2ed5b-146">Se algo estiver muito errado com uma conexão, seu status será exibido como **falha**.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-146">If something is critically wrong with a connection, its status shows as **failed**.</span></span> <span data-ttu-id="2ed5b-147">Para obter mais informações sobre os três tipos de erros, vá para a página de **detalhes do erro** e selecione a conexão com falha.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-147">To get more information on the three types of errors, go to the **error details** page and select the failing connection.</span></span> <span data-ttu-id="2ed5b-148">Confira [gerenciar seu conector](manage-connector.md) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-148">See [Manage your connector](manage-connector.md) to learn more.</span></span>
1. <span data-ttu-id="2ed5b-149">**Gateway não acessível (código de erro: 11)**.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-149">**Gateway not reachable (error code: 11)**.</span></span> <span data-ttu-id="2ed5b-150">A máquina gateway para a conexão está inativa.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-150">The gateway machine for the connection is down.</span></span> <span data-ttu-id="2ed5b-151">Verifique se o processo do Microsoft Power BI é executado no computador do gateway.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-151">Verify if the Microsoft Power BI process runs on the gateway machine.</span></span>
2. <span data-ttu-id="2ed5b-152">**Erro de autenticação (código de erro: 12)**.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-152">**Authentication error (error code: 12)**.</span></span> <span data-ttu-id="2ed5b-153">As credenciais que foram usadas para criar a conexão expiraram ou não são mais válidas.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-153">The credentials that were used for creating the connection expired or are no longer valid.</span></span> <span data-ttu-id="2ed5b-154">Para resolver esse erro, insira as credenciais válidas.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-154">To resolve this error, enter valid credentials.</span></span>
3. <span data-ttu-id="2ed5b-155">**Erro interno (código de erro: qualquer coisa diferente de 11 ou 12)**.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-155">**Internal error (error code: anything other than 11 or 12)**.</span></span> <span data-ttu-id="2ed5b-156">Há um erro na infraestrutura do conector.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-156">There's an error in the connector infrastructure.</span></span> <span data-ttu-id="2ed5b-157">Confira o artigo de [feedback](connectors-feedback.md) para saber como relatar esses erros.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-157">See the [Feedback](connectors-feedback.md) article to find out how to report these errors.</span></span>

## <a name="limitations"></a><span data-ttu-id="2ed5b-158">Limitações</span><span class="sxs-lookup"><span data-stu-id="2ed5b-158">Limitations</span></span>
<span data-ttu-id="2ed5b-159">O conector de compartilhamento de arquivos tem estas limitações na versão prévia:</span><span class="sxs-lookup"><span data-stu-id="2ed5b-159">The File share connector has these limitations in the preview release:</span></span>
* <span data-ttu-id="2ed5b-160">Você só pode indexar arquivos com propriedades fixas, não arquivos com propriedades personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-160">You can only index files with fixed properties, not files with custom properties.</span></span>
* <span data-ttu-id="2ed5b-161">As listas de controle de acesso (ACLs) do compartilhamento de arquivos não são suportadas atualmente.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-161">File share Access Control Lists (ACLs) aren't currently supported.</span></span>
* <span data-ttu-id="2ed5b-162">Identidades externas não são suportadas.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-162">External identities aren't supported.</span></span> <span data-ttu-id="2ed5b-163">Eles devem ser mapeados para identidades do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2ed5b-163">They must be mapped to Azure Active Directory identities.</span></span>