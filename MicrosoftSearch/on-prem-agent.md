---
title: Agente local
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
description: Agente no prem
ms.openlocfilehash: 31220196849fe90ab2611e9c2b83a1cec0a02b34
ms.sourcegitcommit: a04f1df14a3221776ccd141f6060328612d80e06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876494"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="47f18-103">Agente do conector do Graph</span><span class="sxs-lookup"><span data-stu-id="47f18-103">Graph connector agent</span></span>

<span data-ttu-id="47f18-104">O uso de conectores do Graph no centro exige a instalação do software *do agente do conector do Graph.*</span><span class="sxs-lookup"><span data-stu-id="47f18-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="47f18-105">Ele permite a transferência segura de dados entre os dados locais e as APIs do conector do Graph.</span><span class="sxs-lookup"><span data-stu-id="47f18-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="47f18-106">Este artigo orienta você durante a instalação e configuração do agente.</span><span class="sxs-lookup"><span data-stu-id="47f18-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="47f18-107">Instalação</span><span class="sxs-lookup"><span data-stu-id="47f18-107">Installation</span></span>

<span data-ttu-id="47f18-108">Baixe a versão mais recente do agente de conector do Graph [aqui](https://aka.ms/gcadownload) e instale o software usando o assistente de instalação.</span><span class="sxs-lookup"><span data-stu-id="47f18-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="47f18-109">Usando a configuração recomendada do computador descrita abaixo, o software pode lidar com até três conexões.</span><span class="sxs-lookup"><span data-stu-id="47f18-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="47f18-110">Qualquer conexão além disso pode prejudicar o desempenho de todas as conexões no agente.</span><span class="sxs-lookup"><span data-stu-id="47f18-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="47f18-111">Configuração recomendada:</span><span class="sxs-lookup"><span data-stu-id="47f18-111">Recommended configuration:</span></span>

* <span data-ttu-id="47f18-112">Windows 10, Windows Server 2016 R2 e superior</span><span class="sxs-lookup"><span data-stu-id="47f18-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="47f18-113">.NET Core Desktop Runtime 3.1 (x64)</span><span class="sxs-lookup"><span data-stu-id="47f18-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="47f18-114">8 núcleos, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="47f18-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="47f18-115">16 GB de RAM, 2 GB de espaço em disco</span><span class="sxs-lookup"><span data-stu-id="47f18-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="47f18-116">Acesso de rede à fonte de dados e à Internet por meio do 443</span><span class="sxs-lookup"><span data-stu-id="47f18-116">Network access to data source and internet through 443</span></span>

## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="47f18-117">Criar e configurar um aplicativo para o agente</span><span class="sxs-lookup"><span data-stu-id="47f18-117">Create and configure an App for the agent</span></span>  

<span data-ttu-id="47f18-118">Primeiro, entre e observe que o privilégio mínimo necessário na conta é o administrador de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="47f18-118">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="47f18-119">Em seguida, o agente solicitará que você forneça detalhes de autenticação.</span><span class="sxs-lookup"><span data-stu-id="47f18-119">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="47f18-120">Use as etapas abaixo para criar um aplicativo e gerar os detalhes de autenticação necessários.</span><span class="sxs-lookup"><span data-stu-id="47f18-120">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="47f18-121">Criar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="47f18-121">Create an app</span></span>

1. <span data-ttu-id="47f18-122">Acesse o [portal do Azure](https://portal.azure.com) e entre com as credenciais de administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="47f18-122">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="47f18-123">Navegue até registros de aplicativo do **Azure Active Directory** no  ->   painel de navegação e selecione **Novo registro.**</span><span class="sxs-lookup"><span data-stu-id="47f18-123">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="47f18-124">Forneça um nome para o aplicativo e selecione **Registrar.**</span><span class="sxs-lookup"><span data-stu-id="47f18-124">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="47f18-125">Anote a ID do aplicativo (cliente).</span><span class="sxs-lookup"><span data-stu-id="47f18-125">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="47f18-126">Abra **permissões da API** no painel de navegação e selecione Adicionar uma **permissão.**</span><span class="sxs-lookup"><span data-stu-id="47f18-126">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="47f18-127">Selecione **o Microsoft Graph** e, em **seguida, permissões de aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="47f18-127">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="47f18-128">Procure por "ExternalItem.ReadWrite.All" e "Directory.Read.All" nas permissões e selecione **Adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="47f18-128">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="47f18-129">Selecione **Conceder consentimento de administrador para [TenantName]** e confirme selecionando **Sim**.</span><span class="sxs-lookup"><span data-stu-id="47f18-129">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="47f18-130">Verifique se as permissões estão no estado "concedido".</span><span class="sxs-lookup"><span data-stu-id="47f18-130">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="47f18-131">![Permissões mostradas como concedidas na coluna verde à direita.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="47f18-131">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="47f18-132">Configurar autenticação</span><span class="sxs-lookup"><span data-stu-id="47f18-132">Configure Authentication</span></span>

<span data-ttu-id="47f18-133">Os detalhes da autenticação podem ser fornecidos usando um segredo do cliente ou um certificado.</span><span class="sxs-lookup"><span data-stu-id="47f18-133">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="47f18-134">Siga as etapas de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="47f18-134">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="47f18-135">Configurando o segredo do cliente para autenticação</span><span class="sxs-lookup"><span data-stu-id="47f18-135">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="47f18-136">Acesse o [portal do Azure](https://portal.azure.com) e entre com as credenciais de administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="47f18-136">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="47f18-137">Abra **o Registro de** Aplicativo no painel de navegação e vá para o aplicativo apropriado.</span><span class="sxs-lookup"><span data-stu-id="47f18-137">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="47f18-138">Em **Gerenciar,** selecione **Certificados e segredos.**</span><span class="sxs-lookup"><span data-stu-id="47f18-138">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="47f18-139">Selecione **Novo Segredo do Cliente** e selecione um período de expiração para o segredo.</span><span class="sxs-lookup"><span data-stu-id="47f18-139">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="47f18-140">Copie o segredo gerado e salve-o porque ele não será mostrado novamente.</span><span class="sxs-lookup"><span data-stu-id="47f18-140">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="47f18-141">Use esse segredo do cliente juntamente com a ID do aplicativo para configurar o agente.</span><span class="sxs-lookup"><span data-stu-id="47f18-141">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="47f18-142">Não é possível usar espaços em branco **no campo** Nome do agente.</span><span class="sxs-lookup"><span data-stu-id="47f18-142">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="47f18-143">Caracteres numéricos alfa são aceitos.</span><span class="sxs-lookup"><span data-stu-id="47f18-143">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="47f18-144">Usando um certificado para autenticação</span><span class="sxs-lookup"><span data-stu-id="47f18-144">Using a certificate for authentication</span></span>

<span data-ttu-id="47f18-145">Há três etapas simples para usar a autenticação baseada em certificado:</span><span class="sxs-lookup"><span data-stu-id="47f18-145">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="47f18-146">Criar ou obter um certificado</span><span class="sxs-lookup"><span data-stu-id="47f18-146">Create or obtain a certificate</span></span>
1. <span data-ttu-id="47f18-147">Carregar o certificado no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="47f18-147">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="47f18-148">Atribuir o certificado ao agente</span><span class="sxs-lookup"><span data-stu-id="47f18-148">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="47f18-149">Etapa 1: Obter um certificado</span><span class="sxs-lookup"><span data-stu-id="47f18-149">Step 1: Get a certificate</span></span>

<span data-ttu-id="47f18-150">O script abaixo pode ser usado para gerar um certificado auto-assinado.</span><span class="sxs-lookup"><span data-stu-id="47f18-150">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="47f18-151">Sua organização pode não permitir certificados auto-assinados.</span><span class="sxs-lookup"><span data-stu-id="47f18-151">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="47f18-152">Nesse caso, use essas informações para entender os requisitos e adquirir um certificado de acordo com as políticas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="47f18-152">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

```Powershell
$dnsName = "<TenantDomain like agent.onmicrosoft.com>" # Your DNS name
$password = "<password>" # Certificate password
$folderPath = "D:\New folder\" # Where do you want the files to get saved to? The folder needs to exist.
$fileName = "agentcert" # What do you want to call the cert files? without the file extension
$yearsValid = 10 # Number of years until you need to renew the certificate
$certStoreLocation = "cert:\LocalMachine\My"
$expirationDate = (Get-Date).AddYears($yearsValid)
$certificate = New-SelfSignedCertificate -DnsName $dnsName -CertStoreLocation $certStoreLocation -NotAfter $expirationDate -KeyExportPolicy Exportable -KeySpec Signature
$certificatePath = $certStoreLocation + '\' + $certificate.Thumbprint
$filePath = $folderPath + '\' + $fileName
$securePassword = ConvertTo-SecureString -String $password -Force -AsPlainText
Export-Certificate -Cert $certificatePath -FilePath ($filePath + '.cer')
Export-PfxCertificate -Cert $certificatePath -FilePath ($filePath + '.pfx') -Password $securePassword
```

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="47f18-153">Etapa 2: Carregar o certificado no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="47f18-153">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="47f18-154">Abra o aplicativo e navegue até a seção certificados e segredos no painel esquerdo</span><span class="sxs-lookup"><span data-stu-id="47f18-154">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="47f18-155">Selecione "Carregar certificado" e carregue o arquivo .cer</span><span class="sxs-lookup"><span data-stu-id="47f18-155">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="47f18-156">Abra **o registro do** aplicativo e selecione **Certificados e** segredos no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="47f18-156">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="47f18-157">Copie a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="47f18-157">Copy the certificate thumbprint.</span></span>

![Lista de certificados em miniatura quando certificados e segredos são selecionados no painel esquerdo](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="47f18-159">Etapa 3: Atribuir o certificado ao agente</span><span class="sxs-lookup"><span data-stu-id="47f18-159">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="47f18-160">Se você usou o script de exemplo para gerar um certificado, o arquivo PFX pode ser encontrado no local identificado no script.</span><span class="sxs-lookup"><span data-stu-id="47f18-160">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="47f18-161">Baixe o arquivo pfx do certificado na máquina do Agente.</span><span class="sxs-lookup"><span data-stu-id="47f18-161">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="47f18-162">Clique duas vezes no arquivo pfx para iniciar a caixa de diálogo de instalação do certificado.</span><span class="sxs-lookup"><span data-stu-id="47f18-162">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="47f18-163">Selecione "Computador Local" para o local de armazenamento durante a instalação do certificado.</span><span class="sxs-lookup"><span data-stu-id="47f18-163">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="47f18-164">Depois de instalar o certificado, abra "Gerenciar certificados de computador" por meio do menu Iniciar</span><span class="sxs-lookup"><span data-stu-id="47f18-164">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="47f18-165">Selecione o certificado recém-instalado em "Pessoal" -> 'Certificados'</span><span class="sxs-lookup"><span data-stu-id="47f18-165">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="47f18-166">Clique com o botão direito do mouse no certificado e selecione "Todas as Tarefas" -> "Gerenciar Chaves Privadas..."</span><span class="sxs-lookup"><span data-stu-id="47f18-166">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="47f18-167">Opção</span><span class="sxs-lookup"><span data-stu-id="47f18-167">Option</span></span>
1. <span data-ttu-id="47f18-168">Na caixa de diálogo permissões, selecione adicionar opção.</span><span class="sxs-lookup"><span data-stu-id="47f18-168">In the permissions dialog, select add option.</span></span> <span data-ttu-id="47f18-169">Na caixa de diálogo de seleção do usuário, escreva: 'NT Service\GcaHostService' e clique em 'OK'.</span><span class="sxs-lookup"><span data-stu-id="47f18-169">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="47f18-170">Não clique no botão "Verificar Nomes".</span><span class="sxs-lookup"><span data-stu-id="47f18-170">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="47f18-171">Clique em ok na caixa de diálogo permissões.</span><span class="sxs-lookup"><span data-stu-id="47f18-171">Click okay on the permissions dialog.</span></span> <span data-ttu-id="47f18-172">A máquina do agente agora está configurada para que o agente gere tokens usando o certificado.</span><span class="sxs-lookup"><span data-stu-id="47f18-172">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
