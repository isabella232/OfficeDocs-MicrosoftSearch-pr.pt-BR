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
ms.openlocfilehash: 7aef2ea57c92929d4d4f45e1a738c84e6a3f4bba
ms.sourcegitcommit: ab4f81ded967168689e6e81c90e115b94719335c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50173058"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="fc475-103">Agente de conector do Graph</span><span class="sxs-lookup"><span data-stu-id="fc475-103">Graph connector agent</span></span>

<span data-ttu-id="fc475-104">O uso de conectores do Graph no computador exige a instalação do software *do agente do conector do Graph.*</span><span class="sxs-lookup"><span data-stu-id="fc475-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="fc475-105">Ele permite a transferência segura de dados entre os dados locais e as APIs do conector do Graph.</span><span class="sxs-lookup"><span data-stu-id="fc475-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="fc475-106">Este artigo orienta você durante a instalação e configuração do agente.</span><span class="sxs-lookup"><span data-stu-id="fc475-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="fc475-107">Instalação</span><span class="sxs-lookup"><span data-stu-id="fc475-107">Installation</span></span>

<span data-ttu-id="fc475-108">Baixe a versão mais recente do agente de conector do Graph [aqui](https://aka.ms/gcadownload) e instale o software usando o assistente de instalação.</span><span class="sxs-lookup"><span data-stu-id="fc475-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="fc475-109">Usando a configuração recomendada do computador descrita abaixo, o software pode lidar com até três conexões.</span><span class="sxs-lookup"><span data-stu-id="fc475-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="fc475-110">Qualquer conexão além disso pode prejudicar o desempenho de todas as conexões no agente.</span><span class="sxs-lookup"><span data-stu-id="fc475-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="fc475-111">Configuração recomendada:</span><span class="sxs-lookup"><span data-stu-id="fc475-111">Recommended configuration:</span></span>

* <span data-ttu-id="fc475-112">Windows 10, Windows Server 2016 R2 e superior</span><span class="sxs-lookup"><span data-stu-id="fc475-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* [<span data-ttu-id="fc475-113">.NET Core Desktop Runtime 3.1 (x64)</span><span class="sxs-lookup"><span data-stu-id="fc475-113">.NET Core Desktop Runtime 3.1 (x64)</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* <span data-ttu-id="fc475-114">8 núcleos, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="fc475-114">8 cores, 3 GHz</span></span>
* <span data-ttu-id="fc475-115">16 GB de RAM, 2 GB de espaço em disco</span><span class="sxs-lookup"><span data-stu-id="fc475-115">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="fc475-116">Acesso de rede à fonte de dados e à Internet por meio do 443</span><span class="sxs-lookup"><span data-stu-id="fc475-116">Network access to data source and internet through 443</span></span>

<span data-ttu-id="fc475-117">Depois de instalar o agente, se os servidores proxy ou firewalls da sua organização bloquearem a comunicação com domínios desconhecidos, adicione os abaixo à lista de autorizações.</span><span class="sxs-lookup"><span data-stu-id="fc475-117">After you install the agent, if your organization's proxy servers or firewalls block communication to unknown domains, please add below ones to the allow list.</span></span>

1. <span data-ttu-id="fc475-118">\*.servicebus.windows.net</span><span class="sxs-lookup"><span data-stu-id="fc475-118">\*.servicebus.windows.net</span></span>
2. <span data-ttu-id="fc475-119">\*.events.data.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fc475-119">\*.events.data.microsoft.com</span></span>
3. https://login.microsoftonline.com
4. https://gcs.office.com
5. https://graph.microsoft.com/


## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="fc475-120">Criar e configurar um aplicativo para o agente</span><span class="sxs-lookup"><span data-stu-id="fc475-120">Create and configure an App for the agent</span></span>  

<span data-ttu-id="fc475-121">Primeiro, entre e observe que o privilégio mínimo necessário na conta é o administrador de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fc475-121">First, sign in and note that the minimum required privilege on the account is search administrator.</span></span> <span data-ttu-id="fc475-122">Em seguida, o agente solicitará que você forneça detalhes de autenticação.</span><span class="sxs-lookup"><span data-stu-id="fc475-122">The agent will then ask you to provide authentication details.</span></span> <span data-ttu-id="fc475-123">Use as etapas abaixo para criar um aplicativo e gerar os detalhes de autenticação necessários.</span><span class="sxs-lookup"><span data-stu-id="fc475-123">Use the steps below to create an app and generate the required authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="fc475-124">Criar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="fc475-124">Create an app</span></span>

1. <span data-ttu-id="fc475-125">Acesse o [portal do Azure](https://portal.azure.com) e entre com as credenciais de administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="fc475-125">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="fc475-126">Navegue até registros de aplicativo do **Azure Active Directory** no  ->   painel de navegação e selecione **Novo registro.**</span><span class="sxs-lookup"><span data-stu-id="fc475-126">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="fc475-127">Forneça um nome para o aplicativo e selecione **Registrar.**</span><span class="sxs-lookup"><span data-stu-id="fc475-127">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="fc475-128">Anote a ID do aplicativo (cliente).</span><span class="sxs-lookup"><span data-stu-id="fc475-128">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="fc475-129">Abra **as permissões da API** no painel de navegação e selecione Adicionar uma **permissão.**</span><span class="sxs-lookup"><span data-stu-id="fc475-129">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="fc475-130">Selecione **o Microsoft Graph** e, em **seguida, permissões de aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="fc475-130">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="fc475-131">Procure por "ExternalItem.ReadWrite.All" e "Directory.Read.All" nas permissões e selecione **Adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="fc475-131">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="fc475-132">Selecione **Conceder consentimento de administrador para [TenantName]** e confirme selecionando **Sim**.</span><span class="sxs-lookup"><span data-stu-id="fc475-132">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="fc475-133">Verifique se as permissões estão no estado "concedido".</span><span class="sxs-lookup"><span data-stu-id="fc475-133">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="fc475-134">![Permissões mostradas como concedidas na coluna verde à direita.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="fc475-134">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="fc475-135">Configurar autenticação</span><span class="sxs-lookup"><span data-stu-id="fc475-135">Configure Authentication</span></span>

<span data-ttu-id="fc475-136">Os detalhes da autenticação podem ser fornecidos usando um segredo do cliente ou um certificado.</span><span class="sxs-lookup"><span data-stu-id="fc475-136">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="fc475-137">Siga as etapas de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="fc475-137">Follow the steps of your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="fc475-138">Configurando o segredo do cliente para autenticação</span><span class="sxs-lookup"><span data-stu-id="fc475-138">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="fc475-139">Acesse o [portal do Azure](https://portal.azure.com) e entre com as credenciais de administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="fc475-139">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="fc475-140">Abra **o Registro de** Aplicativo no painel de navegação e vá para o aplicativo apropriado.</span><span class="sxs-lookup"><span data-stu-id="fc475-140">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="fc475-141">Em **Gerenciar,** selecione **Certificados e segredos.**</span><span class="sxs-lookup"><span data-stu-id="fc475-141">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="fc475-142">Selecione **Novo Segredo do Cliente** e selecione um período de expiração para o segredo.</span><span class="sxs-lookup"><span data-stu-id="fc475-142">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="fc475-143">Copie o segredo gerado e salve-o porque ele não será mostrado novamente.</span><span class="sxs-lookup"><span data-stu-id="fc475-143">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="fc475-144">Use esse segredo do cliente juntamente com a ID do aplicativo para configurar o agente.</span><span class="sxs-lookup"><span data-stu-id="fc475-144">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="fc475-145">Não é possível usar espaços em branco **no campo** Nome do agente.</span><span class="sxs-lookup"><span data-stu-id="fc475-145">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="fc475-146">Caracteres numéricos alfa são aceitos.</span><span class="sxs-lookup"><span data-stu-id="fc475-146">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="fc475-147">Usando um certificado para autenticação</span><span class="sxs-lookup"><span data-stu-id="fc475-147">Using a certificate for authentication</span></span>

<span data-ttu-id="fc475-148">Há três etapas simples para usar a autenticação baseada em certificado:</span><span class="sxs-lookup"><span data-stu-id="fc475-148">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="fc475-149">Criar ou obter um certificado</span><span class="sxs-lookup"><span data-stu-id="fc475-149">Create or obtain a certificate</span></span>
1. <span data-ttu-id="fc475-150">Carregar o certificado no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="fc475-150">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="fc475-151">Atribuir o certificado ao agente</span><span class="sxs-lookup"><span data-stu-id="fc475-151">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="fc475-152">Etapa 1: Obter um certificado</span><span class="sxs-lookup"><span data-stu-id="fc475-152">Step 1: Get a certificate</span></span>

<span data-ttu-id="fc475-153">O script a seguir pode ser usado para gerar um certificado auto-assinado.</span><span class="sxs-lookup"><span data-stu-id="fc475-153">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="fc475-154">Sua organização pode não permitir certificados auto-assinados.</span><span class="sxs-lookup"><span data-stu-id="fc475-154">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="fc475-155">Nesse caso, use essas informações para entender os requisitos e adquirir um certificado de acordo com as políticas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="fc475-155">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="fc475-156">Etapa 2: Carregar o certificado no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="fc475-156">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="fc475-157">Abra o aplicativo e navegue até a seção certificados e segredos no painel esquerdo</span><span class="sxs-lookup"><span data-stu-id="fc475-157">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="fc475-158">Selecione "Carregar certificado" e carregue o arquivo .cer</span><span class="sxs-lookup"><span data-stu-id="fc475-158">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="fc475-159">Abra **o registro do** aplicativo e selecione **Certificados e** segredos no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="fc475-159">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="fc475-160">Copie a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="fc475-160">Copy the certificate thumbprint.</span></span>

![Lista de certificados em miniatura quando certificados e segredos são selecionados no painel esquerdo](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="fc475-162">Etapa 3: Atribuir o certificado ao agente</span><span class="sxs-lookup"><span data-stu-id="fc475-162">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="fc475-163">Se você usou o script de exemplo para gerar um certificado, o arquivo PFX pode ser encontrado no local identificado no script.</span><span class="sxs-lookup"><span data-stu-id="fc475-163">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="fc475-164">Baixe o arquivo pfx do certificado na máquina do Agente.</span><span class="sxs-lookup"><span data-stu-id="fc475-164">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="fc475-165">Clique duas vezes no arquivo pfx para iniciar a caixa de diálogo de instalação do certificado.</span><span class="sxs-lookup"><span data-stu-id="fc475-165">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="fc475-166">Selecione "Máquina Local" para o local de armazenamento durante a instalação do certificado.</span><span class="sxs-lookup"><span data-stu-id="fc475-166">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="fc475-167">Depois de instalar o certificado, abra "Gerenciar certificados de computador" por meio do menu Iniciar</span><span class="sxs-lookup"><span data-stu-id="fc475-167">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="fc475-168">Selecione o certificado recém-instalado em "Pessoal" -> 'Certificados'</span><span class="sxs-lookup"><span data-stu-id="fc475-168">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="fc475-169">Clique com o botão direito do mouse no certificado e selecione "Todas as Tarefas" -> "Gerenciar Chaves Privadas..."</span><span class="sxs-lookup"><span data-stu-id="fc475-169">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="fc475-170">Opção</span><span class="sxs-lookup"><span data-stu-id="fc475-170">Option</span></span>
1. <span data-ttu-id="fc475-171">Na caixa de diálogo permissões, selecione adicionar opção.</span><span class="sxs-lookup"><span data-stu-id="fc475-171">In the permissions dialog, select add option.</span></span> <span data-ttu-id="fc475-172">Na caixa de diálogo de seleção do usuário, escreva: 'NT Service\GcaHostService' e clique em 'OK'.</span><span class="sxs-lookup"><span data-stu-id="fc475-172">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="fc475-173">Não clique no botão "Verificar Nomes".</span><span class="sxs-lookup"><span data-stu-id="fc475-173">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="fc475-174">Clique em ok na caixa de diálogo permissões.</span><span class="sxs-lookup"><span data-stu-id="fc475-174">Click okay on the permissions dialog.</span></span> <span data-ttu-id="fc475-175">A máquina do agente agora está configurada para que o agente gere tokens usando o certificado.</span><span class="sxs-lookup"><span data-stu-id="fc475-175">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
