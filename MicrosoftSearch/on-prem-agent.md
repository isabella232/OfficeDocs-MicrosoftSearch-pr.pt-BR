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
description: Agente local
ms.openlocfilehash: 763904f8dd96c5db8b0633e36795443502afe7d0
ms.sourcegitcommit: 0ed8ec8b3c4e0f5f669005081fd8b2219f07b4f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420829"
---
# <a name="graph-connector-agent"></a><span data-ttu-id="0a7ab-103">Agente do conector do Graph</span><span class="sxs-lookup"><span data-stu-id="0a7ab-103">Graph connector agent</span></span>

<span data-ttu-id="0a7ab-104">O uso de conectores de gráfico local exige que você instale o software de *agente do conector do Graph* .</span><span class="sxs-lookup"><span data-stu-id="0a7ab-104">Using on-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="0a7ab-105">Ele permite a transferência segura de dados entre os dados locais e as APIs do conector do Graph.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-105">It allows for secure data transfer between on-premises data and the Graph connector APIs.</span></span> <span data-ttu-id="0a7ab-106">Este artigo orienta você durante a instalação e a configuração do agente.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-106">This article guides you through the installing and configuring the agent.</span></span>

## <a name="installation"></a><span data-ttu-id="0a7ab-107">Instalação</span><span class="sxs-lookup"><span data-stu-id="0a7ab-107">Installation</span></span>

<span data-ttu-id="0a7ab-108">Baixe a versão mais recente do agente do conector do Graph [aqui](https://aka.ms/gcadownload) e instale o software usando o assistente de instalação.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-108">Download the latest version of Graph connector agent [here](https://aka.ms/gcadownload) and install the software using the installation wizard.</span></span> <span data-ttu-id="0a7ab-109">Usando a configuração recomendada da máquina descrita abaixo, o software pode lidar com até três conexões.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-109">Using the recommended configuration of the machine described below, the software can handle up to three connections.</span></span> <span data-ttu-id="0a7ab-110">As conexões além disso podem degradar o desempenho de todas as conexões no agente.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-110">Any connections beyond that might degrade the performance of all connections on the agent.</span></span>

<span data-ttu-id="0a7ab-111">Configuração recomendada:</span><span class="sxs-lookup"><span data-stu-id="0a7ab-111">Recommended configuration:</span></span>

* <span data-ttu-id="0a7ab-112">Windows 10, Windows Server 2016 R2 e superior</span><span class="sxs-lookup"><span data-stu-id="0a7ab-112">Windows 10, Windows Server 2016 R2 and above</span></span>
* <span data-ttu-id="0a7ab-113">8 núcleos, 3 GHz</span><span class="sxs-lookup"><span data-stu-id="0a7ab-113">8 cores, 3 GHz</span></span>
* <span data-ttu-id="0a7ab-114">16 GB de RAM, 2 GB de espaço em disco</span><span class="sxs-lookup"><span data-stu-id="0a7ab-114">16 GB RAM, 2 GB Disk Space</span></span>
* <span data-ttu-id="0a7ab-115">Acesso de rede à fonte de dados e à Internet por meio de 443</span><span class="sxs-lookup"><span data-stu-id="0a7ab-115">Network access to data source and internet through 443</span></span>

## <a name="create-and-configure-an-app-for-the-agent"></a><span data-ttu-id="0a7ab-116">Criar e configurar um aplicativo para o agente</span><span class="sxs-lookup"><span data-stu-id="0a7ab-116">Create and configure an App for the agent</span></span>  

<span data-ttu-id="0a7ab-117">Antes de usar o agente, você deve criar um aplicativo e configurar os detalhes de autenticação.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-117">Before using the agent, you must create an app and configure the authentication details.</span></span>

### <a name="create-an-app"></a><span data-ttu-id="0a7ab-118">Criar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="0a7ab-118">Create an app</span></span>

1. <span data-ttu-id="0a7ab-119">Vá para o [portal do Azure](https://portal.azure.com) e entre com as credenciais de administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-119">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="0a7ab-120">Navegue até registros de aplicativos do **Azure Active Directory**  ->  **App registrations** no painel de navegação e selecione **novo registro**.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-120">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="0a7ab-121">Forneça um nome para o aplicativo e selecione **registrar**.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-121">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="0a7ab-122">Anote a ID do aplicativo (cliente).</span><span class="sxs-lookup"><span data-stu-id="0a7ab-122">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="0a7ab-123">Abra **permissões de API** do painel de navegação e selecione **Adicionar uma permissão**.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-123">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="0a7ab-124">Selecione **Microsoft Graph** e, em seguida, **permissões de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-124">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="0a7ab-125">Procure "ExternalItem. ReadWrite. All" e "Directory. Read. All" nas permissões e selecione **adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-125">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="0a7ab-126">Selecione **conceder consentimento do administrador para [locatárioname]** e confirmar selecionando **Sim**.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-126">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="0a7ab-127">Verifique se as permissões estão no estado "concedido".</span><span class="sxs-lookup"><span data-stu-id="0a7ab-127">Check that the permissions are in the "granted" state.</span></span>
     <span data-ttu-id="0a7ab-128">![Permissões mostradas como concedidas na coluna verde à direita.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="0a7ab-128">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

### <a name="configure-authentication"></a><span data-ttu-id="0a7ab-129">Configurar autenticação</span><span class="sxs-lookup"><span data-stu-id="0a7ab-129">Configure Authentication</span></span>

<span data-ttu-id="0a7ab-130">Os detalhes de autenticação podem ser fornecidos usando um segredo do cliente ou um certificado.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-130">Authentication details can be provided using a client secret or a certificate.</span></span> <span data-ttu-id="0a7ab-131">Siga as etapas para sua escolha.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-131">Follow the steps for your choice.</span></span>

#### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="0a7ab-132">Configurando o segredo do cliente para autenticação</span><span class="sxs-lookup"><span data-stu-id="0a7ab-132">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="0a7ab-133">Vá para o [portal do Azure](https://portal.azure.com) e entre com as credenciais de administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-133">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="0a7ab-134">Abra o **registro de aplicativos** no painel de navegação e vá para o aplicativo apropriado.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-134">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="0a7ab-135">Em **gerenciar**, selecione **certificados e segredos**.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-135">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="0a7ab-136">Selecione **novo segredo do cliente** e selecione um período de expiração para o segredo.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-136">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="0a7ab-137">Copie o segredo gerado e salve-o porque ele não será mostrado novamente.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-137">Copy the generated secret and save it because it won't be shown again.</span></span>
4. <span data-ttu-id="0a7ab-138">Use este segredo do cliente junto com a ID do aplicativo para configurar o agente.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-138">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="0a7ab-139">Não é possível usar espaços em branco no campo **nome** do agente.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-139">You cannot use blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="0a7ab-140">Caracteres numéricos Alfa são aceitos.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-140">Alpha numeric characters are accepted.</span></span>

#### <a name="using-a-certificate-for-authentication"></a><span data-ttu-id="0a7ab-141">Usando um certificado para autenticação</span><span class="sxs-lookup"><span data-stu-id="0a7ab-141">Using a certificate for authentication</span></span>

<span data-ttu-id="0a7ab-142">Há três etapas simples para usar a autenticação baseada em certificado:</span><span class="sxs-lookup"><span data-stu-id="0a7ab-142">There are three simple steps for using certificate-based authentication:</span></span>

1. <span data-ttu-id="0a7ab-143">Criar ou obter um certificado</span><span class="sxs-lookup"><span data-stu-id="0a7ab-143">Create or obtain a certificate</span></span>
1. <span data-ttu-id="0a7ab-144">Carregar o certificado no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="0a7ab-144">Upload the certificate to the Azure portal</span></span>
1. <span data-ttu-id="0a7ab-145">Atribuir o certificado ao agente</span><span class="sxs-lookup"><span data-stu-id="0a7ab-145">Assign the certificate to the agent</span></span>

##### <a name="step-1-get-a-certificate"></a><span data-ttu-id="0a7ab-146">Etapa 1: obter um certificado</span><span class="sxs-lookup"><span data-stu-id="0a7ab-146">Step 1: Get a certificate</span></span>

<span data-ttu-id="0a7ab-147">O script a seguir pode ser usado para gerar um certificado autoassinado.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-147">The script below can be used to generate a self-signed certificate.</span></span> <span data-ttu-id="0a7ab-148">Sua organização pode não permitir certificados autoassinados.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-148">Your organization may not allow self-signed certificates.</span></span> <span data-ttu-id="0a7ab-149">Nesse caso, use essas informações para entender os requisitos e adquirir um certificado de acordo com as políticas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-149">In that case, use this information to understand the requirements and acquire a certificate in accordance to your organization's policies.</span></span>

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a><span data-ttu-id="0a7ab-150">Etapa 2: carregar o certificado no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="0a7ab-150">Step 2: Upload the certificate in the Azure portal</span></span>

1. <span data-ttu-id="0a7ab-151">Abra o aplicativo e navegue até a seção de certificados e segredos no painel esquerdo</span><span class="sxs-lookup"><span data-stu-id="0a7ab-151">Open the application and navigate to certificates and secrets section from left pane</span></span>
1. <span data-ttu-id="0a7ab-152">Selecione "carregar certificado" e carregar o arquivo. cer</span><span class="sxs-lookup"><span data-stu-id="0a7ab-152">Select 'Upload certificate' and upload the .cer file</span></span>
1. <span data-ttu-id="0a7ab-153">Abra o **registro do aplicativo** e selecione **certificados e segredos** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-153">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="0a7ab-154">Copie a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-154">Copy the certificate thumbprint.</span></span>

![Lista de certificados do thumbrint quando os certificados e segredos são selecionados no painel esquerdo](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a><span data-ttu-id="0a7ab-156">Etapa 3: atribuir o certificado ao agente</span><span class="sxs-lookup"><span data-stu-id="0a7ab-156">Step 3: Assign the certificate to the agent</span></span>

<span data-ttu-id="0a7ab-157">Se você usou o script de exemplo para gerar um certificado, o arquivo PFX pode ser encontrado no local identificado no script.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-157">If you used the sample script to generate a certificate, the PFX file can be found in the location identified in the script.</span></span>

1. <span data-ttu-id="0a7ab-158">Baixe o arquivo PFX de certificado no computador do agente.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-158">Download the certificate pfx file onto the Agent machine.</span></span>
1. <span data-ttu-id="0a7ab-159">Clique duas vezes no arquivo PFX para iniciar a caixa de diálogo de instalação de certificado.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-159">Double-click the pfx file to launch the certificate installation dialog.</span></span>
1. <span data-ttu-id="0a7ab-160">Selecione "máquina local" para local de armazenamento ao instalar o certificado.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-160">Select 'Local Machine' for store location while installing the certificate.</span></span>
1. <span data-ttu-id="0a7ab-161">Após instalar o certificado, abra a guia gerenciar certificados de computador por meio do menu iniciar</span><span class="sxs-lookup"><span data-stu-id="0a7ab-161">After installing the certificate, open 'Manage computer certificates' through Start menu</span></span>
1. <span data-ttu-id="0a7ab-162">Selecione o certificado recém-instalado em ' pessoal '-> ' certificados '</span><span class="sxs-lookup"><span data-stu-id="0a7ab-162">Select the newly installed certificate under 'Personal' -> 'Certificates'</span></span>
1. <span data-ttu-id="0a7ab-163">Clique com o botão direito do mouse no certificado e selecione "todas as tarefas"-> ' gerenciar chaves privadas... '</span><span class="sxs-lookup"><span data-stu-id="0a7ab-163">Right click on the cert and select 'All Tasks' -> 'Manage Private Keys…'</span></span> <span data-ttu-id="0a7ab-164">Opção</span><span class="sxs-lookup"><span data-stu-id="0a7ab-164">Option</span></span>
1. <span data-ttu-id="0a7ab-165">Na caixa de diálogo permissões, selecione Adicionar opção.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-165">In the permissions dialog, select add option.</span></span> <span data-ttu-id="0a7ab-166">Na caixa de diálogo seleção de usuário, escreva: "NT Service\GcaHostService" e clique em "OK".</span><span class="sxs-lookup"><span data-stu-id="0a7ab-166">In the user selection dialog, write: 'NT Service\GcaHostService' and click 'OK'.</span></span> <span data-ttu-id="0a7ab-167">Não clique no botão "verificar nomes".</span><span class="sxs-lookup"><span data-stu-id="0a7ab-167">Don't click the 'Check Names' button.</span></span>
1. <span data-ttu-id="0a7ab-168">Clique em OK na caixa de diálogo permissões.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-168">Click okay on the permissions dialog.</span></span> <span data-ttu-id="0a7ab-169">A máquina do agente agora está configurada para que o agente gere tokens usando o certificado.</span><span class="sxs-lookup"><span data-stu-id="0a7ab-169">The agent machine is now configured for agent to generate tokens using the certificate.</span></span>
