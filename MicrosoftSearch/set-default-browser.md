---
title: Navegador do conjunto padrão
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/20/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
description: Saiba como configurar um navegador padrão para sua empresa com o Microsoft Search.
ms.openlocfilehash: 13a0a878b3288abeb7b07defdab839a158adc2ac
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378423"
---
# <a name="set-default-browser"></a><span data-ttu-id="d8459-103">Navegador do conjunto padrão</span><span class="sxs-lookup"><span data-stu-id="d8459-103">Set default browser</span></span>

<span data-ttu-id="d8459-104">Configurar o navegador padrão, o mecanismo de pesquisa padrão e a página inicial padrão ajudarão os usuários Descubra os recursos do Microsoft Search, incentivar o uso de mais e fornecer uma experiência mais suave.</span><span class="sxs-lookup"><span data-stu-id="d8459-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="d8459-105">Para definir o navegador padrão para sua organização, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="d8459-105">To set the default browser for your organization, follow the steps below.</span></span>
  
## <a name="windows-8-and-above"></a><span data-ttu-id="d8459-106">Windows 8 e acima</span><span class="sxs-lookup"><span data-stu-id="d8459-106">Windows 8 and above</span></span>

<span data-ttu-id="d8459-107">Para definir o Internet Explorer ou Microsoft Edge como o navegador padrão, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d8459-107">To set Internet Explorer or Microsoft Edge as the default browser, follow these steps:</span></span>
  
### <a name="create-default-associations-file"></a><span data-ttu-id="d8459-108">Criar o arquivo de associações padrão</span><span class="sxs-lookup"><span data-stu-id="d8459-108">Create default associations file</span></span>

1. <span data-ttu-id="d8459-109">Abra um console administrativo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8459-109">Open an administrative PowerShell console.</span></span>
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
<span data-ttu-id="d8459-110">Estas etapas tente e criar o arquivo de associações padrão na pasta SYSVOL do controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="d8459-110">These steps try and create the default associations file in the SYSVOL folder of the domain controller.</span></span>
  
### <a name="add-or-edit-the-default-associations-file"></a><span data-ttu-id="d8459-111">Adicionar ou editar o arquivo de associações padrão</span><span class="sxs-lookup"><span data-stu-id="d8459-111">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. <span data-ttu-id="d8459-112">Editar as seguintes entradas (. htm,. HTML, http, https) e remover outras entradas se eles não sejam necessários.</span><span class="sxs-lookup"><span data-stu-id="d8459-112">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
    
  - <span data-ttu-id="d8459-113">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="d8459-113">**Microsoft Edge**</span></span>
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="d8459-114">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="d8459-114">**Internet Explorer**</span></span>
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. <span data-ttu-id="d8459-115">Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e alterne para a edição de qualquer política existente ou criar um novo.</span><span class="sxs-lookup"><span data-stu-id="d8459-115">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="d8459-116">Navegue até o **computador \ Modelos Administrativos\Componentes do Components\File Explorer**</span><span class="sxs-lookup"><span data-stu-id="d8459-116">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**</span></span>
    
2. <span data-ttu-id="d8459-117">Clique duas vezes em **definir um arquivo de configuração de associações padrão**, defini-la como **habilitada**e digite o caminho para AppAssoc.xml (por exemplo, %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span><span class="sxs-lookup"><span data-stu-id="d8459-117">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)</span></span>
    
4. <span data-ttu-id="d8459-118">Impor o GPO resultante ao vinculá-lo ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="d8459-118">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="d8459-119">Os usuários poderão alterar o navegador após essa diretiva estiver definida.</span><span class="sxs-lookup"><span data-stu-id="d8459-119">Users will be able to change the browser after this policy is set.</span></span>
  
## <a name="windows-7"></a><span data-ttu-id="d8459-120">Windows 7</span><span class="sxs-lookup"><span data-stu-id="d8459-120">Windows 7</span></span>

1. <span data-ttu-id="d8459-121">Configure a máquina local que será usada para definir o GPO.</span><span class="sxs-lookup"><span data-stu-id="d8459-121">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="d8459-122">Abra **Programas padrão do controle Panel\Programs\Default Programs\Set** e defina o Internet Explorer como padrão.</span><span class="sxs-lookup"><span data-stu-id="d8459-122">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="d8459-123">Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e alterne para a edição de qualquer política existente ou criar um novo.</span><span class="sxs-lookup"><span data-stu-id="d8459-123">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="d8459-124">Navegue até \*\* \<usuário do computador\> Configuration\Policies\Preferences\Windows configurações\*\*.</span><span class="sxs-lookup"><span data-stu-id="d8459-124">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="d8459-125">Com o botão direito em **Registry\New** e selecione **Assistente do registro**.</span><span class="sxs-lookup"><span data-stu-id="d8459-125">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="d8459-126">Da janela do navegador do registro, selecione o **Computador Local** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d8459-126">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="d8459-p101">Navegue até **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selecione o valor ProgId. Verifique se que o valor parecido com aquele abaixo:</span><span class="sxs-lookup"><span data-stu-id="d8459-p101">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![Selecione o valor ProgID em Editar cadeia de caracteres](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="d8459-p102">Navegue até **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selecione o valor ProgId. Certifique-se que o valor parecido com aquele abaixo:</span><span class="sxs-lookup"><span data-stu-id="d8459-p102">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![Selecione ProgId para HTTPS na cadeia de caracteres de edição](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="d8459-133">Impor o GPO resultante ao vinculá-lo ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="d8459-133">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="d8459-134">Os usuários poderão alterar o navegador após essa diretiva estiver definida.</span><span class="sxs-lookup"><span data-stu-id="d8459-134">Users will be able to change the browser after this policy is set.</span></span>