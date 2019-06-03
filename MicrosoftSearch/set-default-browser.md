---
title: Definir o navegador padrão
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
ROBOTS: NOINDEX
description: Saiba como configurar um navegador padrão para a empresa com a Pesquisa da Microsoft.
ms.openlocfilehash: daff7f66bd38bdd56179e44c36092a2c4fd42b42
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591157"
---
# <a name="set-default-browser"></a><span data-ttu-id="6703d-103">Definir o navegador padrão</span><span class="sxs-lookup"><span data-stu-id="6703d-103">Set default browser</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6703d-104">Este artigo se aplica à Pesquisa do Microsoft no portal de administração do Bing.</span><span class="sxs-lookup"><span data-stu-id="6703d-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="6703d-105">Estamos movendo o portal para o centro de administração do Microsoft 365 e, posteriormente, ele será removido.</span><span class="sxs-lookup"><span data-stu-id="6703d-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="6703d-106">Recomendamos que você use o centro de administração do Microsoft 365 para começar.</span><span class="sxs-lookup"><span data-stu-id="6703d-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> [<span data-ttu-id="6703d-107">Visão geral da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6703d-107">Overview of Microsoft Search</span></span>](overview-microsoft-search.md)
    
<span data-ttu-id="6703d-108">Configurar o navegador, o mecanismo de pesquisa e a home page padrão ajuda os usuários a descobrir os recursos, promove o uso e proporciona uma experiência aprimorada da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6703d-108">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="6703d-109">Para definir o navegador padrão da organização, faça os procedimentos abaixo.</span><span class="sxs-lookup"><span data-stu-id="6703d-109">To set the default browser for your organization, follow the steps below.</span></span>
  
## <a name="windows-8-and-above"></a><span data-ttu-id="6703d-110">Windows 8 e versão posterior</span><span class="sxs-lookup"><span data-stu-id="6703d-110">Windows 8 and above</span></span>

<span data-ttu-id="6703d-111">Para configurar o Microsoft Edge ou Internet Explorer como navegador padrão, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="6703d-111">To set Internet Explorer or Microsoft Edge as the default browser, follow these steps:</span></span>
  
### <a name="create-default-associations-file"></a><span data-ttu-id="6703d-112">Criar um arquivo de associações padrão</span><span class="sxs-lookup"><span data-stu-id="6703d-112">Create default associations file</span></span>

1. <span data-ttu-id="6703d-113">Abra um console administrativo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6703d-113">Open an administrative PowerShell console.</span></span>
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
<span data-ttu-id="6703d-114">Essas etapas se destinam a testar e criar o arquivo de associações padrão na pasta SYSVOL do controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="6703d-114">These steps try and create the default associations file in the SYSVOL folder of the domain controller.</span></span>
  
### <a name="add-or-edit-the-default-associations-file"></a><span data-ttu-id="6703d-115">Adicionar ou editar um arquivo de associações padrão</span><span class="sxs-lookup"><span data-stu-id="6703d-115">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. <span data-ttu-id="6703d-116">Edite as seguintes entradas (.htm, .html, http, https) e remova as outras entradas, caso elas não sejam necessárias.</span><span class="sxs-lookup"><span data-stu-id="6703d-116">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
    
  - <span data-ttu-id="6703d-117">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="6703d-117">**Microsoft Edge**</span></span>
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="6703d-118">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="6703d-118">**Internet Explorer**</span></span>
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. <span data-ttu-id="6703d-119">Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a opção para editar uma política existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="6703d-119">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="6703d-120">Navegue para **Configuração do Computador\Modelos Administrativos\Componentes do Windows\Explorador de Arquivos**</span><span class="sxs-lookup"><span data-stu-id="6703d-120">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**</span></span>
    
2. <span data-ttu-id="6703d-121">Clique duas vezes em **Definir um arquivo de configuração de associações padrão**, defina-o como **habilitado** e insira o caminho para AppAssoc.xml (por exemplo %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span><span class="sxs-lookup"><span data-stu-id="6703d-121">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span></span>
    
4. <span data-ttu-id="6703d-122">Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="6703d-122">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="6703d-123">Os usuários poderão alterar o navegador, após a definição dessa política.</span><span class="sxs-lookup"><span data-stu-id="6703d-123">Users will be able to change the browser after this policy is set.</span></span>
  
## <a name="windows-7"></a><span data-ttu-id="6703d-124">Windows 7</span><span class="sxs-lookup"><span data-stu-id="6703d-124">Windows 7</span></span>

1. <span data-ttu-id="6703d-125">Configure o computador local que será usado para configurar o GPO.</span><span class="sxs-lookup"><span data-stu-id="6703d-125">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="6703d-126">Abra **Painel de Controle\Programas\Programas Padrão\Definir Programas Padrão** e defina o Internet Explorer como padrão.</span><span class="sxs-lookup"><span data-stu-id="6703d-126">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="6703d-127">Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a opção para editar uma política existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="6703d-127">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="6703d-128">Navegue para **\<Computador/Usuário\> Configuração\Políticas\Preferências\Configurações do Windows**.</span><span class="sxs-lookup"><span data-stu-id="6703d-128">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="6703d-129">Clique com o botão direito do mouse em **Registro/Novo** e selecione **Assistente do Registro**.</span><span class="sxs-lookup"><span data-stu-id="6703d-129">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="6703d-130">Na janela do Navegador do Registro, selecione **Computador local** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6703d-130">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="6703d-p102">Navegue para **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selecione o valor ProgID. Verifique se o valor tem a seguinte aparência, conforme exibido abaixo:</span><span class="sxs-lookup"><span data-stu-id="6703d-p102">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![Selecione o valor ProgID em Editar Cadeia de Caracteres](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="6703d-p103">Navegue para **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selecione o valor ProgID. Verifique se o valor tem a seguinte aparência, conforme exibido abaixo:</span><span class="sxs-lookup"><span data-stu-id="6703d-p103">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![Selecione a ProgID para HTTPS em Editar Cadeia de Caracteres](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="6703d-137">Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="6703d-137">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="6703d-138">Os usuários poderão alterar o navegador, após a definição dessa política.</span><span class="sxs-lookup"><span data-stu-id="6703d-138">Users will be able to change the browser after this policy is set.</span></span>