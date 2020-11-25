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
ms.openlocfilehash: 487c5b179e09fd99fa26ae7a237e89ca38b7be4d
ms.sourcegitcommit: 69a1c544cc8db364991cb58d7818d7158ff108b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49408938"
---
# <a name="on-prem-agent"></a><span data-ttu-id="582d0-103">Agente local</span><span class="sxs-lookup"><span data-stu-id="582d0-103">On-Prem Agent</span></span>

## <a name="graph-connector-agent"></a><span data-ttu-id="582d0-104">Agente do conector do Graph</span><span class="sxs-lookup"><span data-stu-id="582d0-104">Graph connector agent</span></span>

<span data-ttu-id="582d0-105">Os conectores do Graph local exigem que você instale o software de *agente do conector do Graph* .</span><span class="sxs-lookup"><span data-stu-id="582d0-105">On-prem Graph connectors require you to install *Graph connector agent* software.</span></span> <span data-ttu-id="582d0-106">Permite a transferência rápida e segura de dados entre os serviços de nuvem e dados locais.</span><span class="sxs-lookup"><span data-stu-id="582d0-106">It allows quick and secure data transfer between on-premises data and cloud services.</span></span> <span data-ttu-id="582d0-107">Este artigo orienta você pelas etapas de instalação e configuração do software.</span><span class="sxs-lookup"><span data-stu-id="582d0-107">This article guides you through the steps of installing and configuring the software.</span></span> <span data-ttu-id="582d0-108">Uma vez configurada, ela estará disponível para a criação de conexões com suas fontes de dados locais no [centro de administração do Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="582d0-108">Once configured, it will be available for creating connections to your on-prem data sources from the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

## <a name="installation"></a><span data-ttu-id="582d0-109">Instalação</span><span class="sxs-lookup"><span data-stu-id="582d0-109">Installation</span></span>

<span data-ttu-id="582d0-110">Baixe a versão mais recente do agente do conector do Graph usando [este link](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) e instale o software usando o assistente de instalação.</span><span class="sxs-lookup"><span data-stu-id="582d0-110">Download the latest version of Graph connector agent using [this link](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) and install the software using the installation wizard.</span></span> <span data-ttu-id="582d0-111">Com a configuração recomendada da máquina descrita abaixo, o software pode lidar perfeitamente com até três conexões.</span><span class="sxs-lookup"><span data-stu-id="582d0-111">With the recommended configuration of the machine described below, the software can seamlessly handle up to three connections.</span></span> <span data-ttu-id="582d0-112">Qualquer conexão além disso pode prejudicar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="582d0-112">Any connections beyond that might degrade the performance.</span></span>

<span data-ttu-id="582d0-113">Configuração recomendada:</span><span class="sxs-lookup"><span data-stu-id="582d0-113">Recommended configuration:</span></span>

* <span data-ttu-id="582d0-114">Windows 10, Windows Server 2012 R2 e superior</span><span class="sxs-lookup"><span data-stu-id="582d0-114">Windows 10, Windows Server 2012 R2 and above</span></span>
* <span data-ttu-id="582d0-115">8 núcleos, 3GHz</span><span class="sxs-lookup"><span data-stu-id="582d0-115">8 cores, 3GHz</span></span>
* <span data-ttu-id="582d0-116">QLE2662 RAM, 1 GB de espaço em disco</span><span class="sxs-lookup"><span data-stu-id="582d0-116">16GB RAM, 1GB Disk Space</span></span>
* <span data-ttu-id="582d0-117">Acesso de rede à fonte de dados e à Internet por meio de 443</span><span class="sxs-lookup"><span data-stu-id="582d0-117">Network access to data source and internet through 443</span></span>

## <a name="creating-app-for-the-agent"></a><span data-ttu-id="582d0-118">Criando aplicativo para o agente</span><span class="sxs-lookup"><span data-stu-id="582d0-118">Creating App for the agent</span></span>  

<span data-ttu-id="582d0-119">A instância do agente precisa ser alimentada por poucos parâmetros críticos antes da criação de conexões.</span><span class="sxs-lookup"><span data-stu-id="582d0-119">The agent instance needs to be fed few critical parameters before you create connections.</span></span> <span data-ttu-id="582d0-120">Esses parâmetros incluem detalhes de autenticação necessários para usar as APIs de inclusão de gráfico.</span><span class="sxs-lookup"><span data-stu-id="582d0-120">These parameters include authentication details required for using Graph ingestion APIs.</span></span>  

<span data-ttu-id="582d0-121">Etapas para criar o aplicativo para o agente.</span><span class="sxs-lookup"><span data-stu-id="582d0-121">Steps for creating App for the agent.</span></span>

1. <span data-ttu-id="582d0-122">Vá para o [portal do Azure](https://portal.azure.com) e entre com as credenciais de administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="582d0-122">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="582d0-123">Navegue até registros de aplicativos do **Azure Active Directory**  ->  **App registrations** no painel de navegação e selecione **novo registro**.</span><span class="sxs-lookup"><span data-stu-id="582d0-123">Navigate to **Azure Active Directory** -> **App registrations** from the navigation pane and select **New registration**.</span></span>
3. <span data-ttu-id="582d0-124">Forneça um nome para o aplicativo e selecione **registrar**.</span><span class="sxs-lookup"><span data-stu-id="582d0-124">Provide a name for the app and select **Register**.</span></span>
4. <span data-ttu-id="582d0-125">Anote a ID do aplicativo (cliente).</span><span class="sxs-lookup"><span data-stu-id="582d0-125">Make a note of the Application (client) ID.</span></span>
5. <span data-ttu-id="582d0-126">Abra **permissões de API** do painel de navegação e selecione **Adicionar uma permissão**.</span><span class="sxs-lookup"><span data-stu-id="582d0-126">Open **API permissions** from the navigation pane and select **Add a permission**.</span></span>
6. <span data-ttu-id="582d0-127">Selecione **Microsoft Graph** e, em seguida, **permissões de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="582d0-127">Select **Microsoft Graph** and then **Application permissions**.</span></span>
7. <span data-ttu-id="582d0-128">Procure "ExternalItem. ReadWrite. All" e "Directory. Read. All" nas permissões e selecione **adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="582d0-128">Search for "ExternalItem.ReadWrite.All" and "Directory.Read.All" from the permissions and select **Add permissions**.</span></span>
8. <span data-ttu-id="582d0-129">Selecione **conceder consentimento do administrador para [locatárioname]** e confirmar selecionando **Sim**.</span><span class="sxs-lookup"><span data-stu-id="582d0-129">Select **Grant admin consent for [TenantName]** and confirm by selecting **Yes**.</span></span>
9. <span data-ttu-id="582d0-130">Verifique se as permissões estão no Estado concedido.</span><span class="sxs-lookup"><span data-stu-id="582d0-130">Check that the permissions are in the granted state.</span></span>
     <span data-ttu-id="582d0-131">![Permissões mostradas como concedidas na coluna verde à direita.](media/onprem-agent/granted-state.png)</span><span class="sxs-lookup"><span data-stu-id="582d0-131">![Permissions shown as granted in green on right hand column.](media/onprem-agent/granted-state.png)</span></span>

## <a name="configuring-graph-connector-agent"></a><span data-ttu-id="582d0-132">Configurando o agente do conector do Graph</span><span class="sxs-lookup"><span data-stu-id="582d0-132">Configuring Graph connector agent</span></span>

<span data-ttu-id="582d0-133">Depois de criar o aplicativo para o agente do, você deve configurar o agente com os detalhes de autenticação apropriados.</span><span class="sxs-lookup"><span data-stu-id="582d0-133">Once you have created the App for the agent, you must configure the agent with appropriate authentication details.</span></span>

<span data-ttu-id="582d0-134">Os detalhes de autenticação podem ser fornecidos em um dos formatos a seguir.</span><span class="sxs-lookup"><span data-stu-id="582d0-134">Authentication details can be provided in one of the following forms.</span></span>

### <a name="configuring-the-client-secret-for-authentication"></a><span data-ttu-id="582d0-135">Configurando o segredo do cliente para autenticação</span><span class="sxs-lookup"><span data-stu-id="582d0-135">Configuring the client secret for authentication</span></span>

1. <span data-ttu-id="582d0-136">Vá para o [portal do Azure](https://portal.azure.com) e entre com as credenciais de administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="582d0-136">Go to the [Azure portal](https://portal.azure.com) and sign in with admin credentials for the tenant.</span></span>
2. <span data-ttu-id="582d0-137">Abra o **registro de aplicativos** no painel de navegação e vá para o aplicativo apropriado.</span><span class="sxs-lookup"><span data-stu-id="582d0-137">Open **App Registration** from the navigation pane and go to the appropriate App.</span></span> <span data-ttu-id="582d0-138">Em **gerenciar**, selecione **certificados e segredos**.</span><span class="sxs-lookup"><span data-stu-id="582d0-138">Under **Manage**, select **Certificates and secrets**.</span></span>
3. <span data-ttu-id="582d0-139">Selecione **novo segredo do cliente** e selecione um período de expiração para o segredo.</span><span class="sxs-lookup"><span data-stu-id="582d0-139">Select **New Client secret** and select an expiry period for the secret.</span></span> <span data-ttu-id="582d0-140">Copie o segredo gerado e salve-o porque ele não será mostrado novamente.</span><span class="sxs-lookup"><span data-stu-id="582d0-140">Copy the generated secret and save it because it will not be shown again.</span></span>
4. <span data-ttu-id="582d0-141">Use este segredo do cliente junto com a ID do aplicativo para configurar o agente.</span><span class="sxs-lookup"><span data-stu-id="582d0-141">Use this Client secret along with the Application ID to configure the agent.</span></span> <span data-ttu-id="582d0-142">Não use espaços em branco no campo **nome** do agente.</span><span class="sxs-lookup"><span data-stu-id="582d0-142">Do not use any blank spaces in the **Name** field of the agent.</span></span> <span data-ttu-id="582d0-143">Caracteres numéricos Alfa são aceitos.</span><span class="sxs-lookup"><span data-stu-id="582d0-143">Alpha numeric characters are accepted.</span></span>

## <a name="using-thumbprint-certificate-for-authentication"></a><span data-ttu-id="582d0-144">Usando o certificado de impressão digital para autenticação</span><span class="sxs-lookup"><span data-stu-id="582d0-144">Using thumbprint certificate for authentication</span></span>

<span data-ttu-id="582d0-145">Se você já configurou os detalhes de autenticação seguindo [a configuração do segredo do cliente para autenticação](#configuring-the-client-secret-for-authentication) , poderá ir diretamente para a [visão geral da configuração](configure-connector.md).</span><span class="sxs-lookup"><span data-stu-id="582d0-145">If you have already configured the authentication details by following [Configuring the client secret for authentication](#configuring-the-client-secret-for-authentication) , then you can jump directly to [Setup overview](configure-connector.md).</span></span>

1. <span data-ttu-id="582d0-146">Abra o **registro do aplicativo** e selecione **certificados e segredos** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="582d0-146">Open **App registration** and select **Certificates and secrets** from the navigation pane.</span></span> <span data-ttu-id="582d0-147">Copie a impressão digital do certificado.</span><span class="sxs-lookup"><span data-stu-id="582d0-147">Copy the certificate thumbprint.</span></span>
<span data-ttu-id="582d0-148">![Lista de certificados do thumbrint quando os certificados e segredos são selecionados no painel esquerdo](media/onprem-agent/certificates.png)</span><span class="sxs-lookup"><span data-stu-id="582d0-148">![List of thumbrint certificates when Certificates and secrets is selected in the left pane](media/onprem-agent/certificates.png)</span></span>
2. <span data-ttu-id="582d0-149">Use o segredo do cliente ou a impressão digital para registrar o agente do conector do Graph.</span><span class="sxs-lookup"><span data-stu-id="582d0-149">Use either the client secret or thumbprint to register the Graph connector agent.</span></span>
<span data-ttu-id="582d0-150">![Registrar formulário solicitando nome, ID do aplicativo, tipo de credencial e certificado](media/onprem-agent/register.png)</span><span class="sxs-lookup"><span data-stu-id="582d0-150">![Register form asking for name, app id, credential type, and certificate](media/onprem-agent/register.png)</span></span>
