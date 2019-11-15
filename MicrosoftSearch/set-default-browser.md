---
title: Definir o navegador padrão
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 53e2b71a-348b-4dfe-a504-6e97d573effe
description: Defina o navegador padrão para o Microsoft Edge ou o Internet Explorer para os usuários da Pesquisa da Microsoft.
ms.openlocfilehash: b99127411d070b37fe34a4f8468449f2354cb6be
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626932"
---
# <a name="make-microsoft-edge-the-default-browser"></a><span data-ttu-id="aa91f-103">Tornar o Microsoft Edge o navegador padrão</span><span class="sxs-lookup"><span data-stu-id="aa91f-103">Make Microsoft Edge the default browser</span></span>
  
<span data-ttu-id="aa91f-104">Para dar aos usuários a melhor experiência com a Pesquisa da Microsoft, você pode tornar o Microsoft Edge o navegador padrão.</span><span class="sxs-lookup"><span data-stu-id="aa91f-104">To give your users the best experience with Microsoft Search, you can make Microsoft Edge the default browser.</span></span> <span data-ttu-id="aa91f-105">Isso só definirá o Microsoft Edge como navegador padrão para usuários em sua organização, usuários individuais ainda poderão selecionar um navegador diferente.</span><span class="sxs-lookup"><span data-stu-id="aa91f-105">This will only set Microsoft Edge as the default browser for users in your org, individual users can still select a different browser.</span></span>
  
  
## <a name="windows-8-and-later"></a><span data-ttu-id="aa91f-106">Windows 8 e posteriores</span><span class="sxs-lookup"><span data-stu-id="aa91f-106">Windows 8 and later</span></span>

<span data-ttu-id="aa91f-107">Essas instruções mostram como tornar o Microsoft Edge ou o Internet Explorer como navegador padrão para computadores com Windows 8 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="aa91f-107">These instructions show you how to make Microsoft Edge or Internet Explorer as the default browser for computers running Windows 8 or later.</span></span> <span data-ttu-id="aa91f-108">Os usuários poderão alterar o navegador, após a definição dessa política.</span><span class="sxs-lookup"><span data-stu-id="aa91f-108">Users will be able to change the browser after this policy is set.</span></span>
  
### <a name="step-1-create-the-default-associations-file"></a><span data-ttu-id="aa91f-109">ETAPA 1: Criar o arquivo de associações padrão</span><span class="sxs-lookup"><span data-stu-id="aa91f-109">STEP 1: Create the default associations file</span></span>
<span data-ttu-id="aa91f-110">Crie o arquivo de associações padrão na pasta SYSVOL do controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="aa91f-110">Create the default associations file in the SYSVOL folder of the domain controller.</span></span>

1. <span data-ttu-id="aa91f-111">Abra um console administrativo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa91f-111">Open an administrative PowerShell console.</span></span>
1. `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
1. `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
1. `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
  
### <a name="step-2-add-or-edit-the-default-associations-file"></a><span data-ttu-id="aa91f-112">ETAPA 2.</span><span class="sxs-lookup"><span data-stu-id="aa91f-112">STEP 2.</span></span> <span data-ttu-id="aa91f-113">Adicionar ou editar um arquivo de associações padrão</span><span class="sxs-lookup"><span data-stu-id="aa91f-113">Add or edit the default associations file</span></span>

1. `Notepad "$SettingsPath\AppAssoc.xml"`
1. <span data-ttu-id="aa91f-114">Edite as seguintes entradas (.htm, .html, http, https) e remova as outras entradas, caso elas não sejam necessárias.</span><span class="sxs-lookup"><span data-stu-id="aa91f-114">Edit the following entries (.htm, .html, http, https), and remove other entries if they're not needed.</span></span>
  - <span data-ttu-id="aa91f-115">**Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="aa91f-115">**Microsoft Edge**</span></span>
    - `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
              
    - `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
    - `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - <span data-ttu-id="aa91f-116">**Internet Explorer**</span><span class="sxs-lookup"><span data-stu-id="aa91f-116">**Internet Explorer**</span></span>
    
    - `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`        
    - `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`

### <a name="step-3-edit-the-group-policy"></a><span data-ttu-id="aa91f-117">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="aa91f-117">Step 3.</span></span> <span data-ttu-id="aa91f-118">Editar a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="aa91f-118">Edit the Group Policy</span></span>

1. <span data-ttu-id="aa91f-119">Abra o **Console de Gerenciamento de Política de Grupo** (gpmc.msc) e alterne para editar qualquer política existente ou para criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="aa91f-119">Open **Group Policy Management Console** (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
1. <span data-ttu-id="aa91f-120">Navegue para **Configuração do Computador/Modelos Administrativos/Componentes do Windows/Explorador de Arquivos**.</span><span class="sxs-lookup"><span data-stu-id="aa91f-120">Navigate to **Computer Configuration\Administrative Templates\Windows Components\File Explorer**.</span></span>
1. <span data-ttu-id="aa91f-121">Clique duas vezes em **Definir um arquivo de configuração de associações padrão**, defina-o como **Habilitado** e insira o caminho para AppAssoc.xml (por exemplo, %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="aa91f-121">Double-click **Set a default associations configuration file**, set it to **Enabled**, and enter the path to AppAssoc.xml (for example %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

  
## <a name="windows-7"></a><span data-ttu-id="aa91f-122">Windows 7</span><span class="sxs-lookup"><span data-stu-id="aa91f-122">Windows 7</span></span>

1. <span data-ttu-id="aa91f-123">Configure o computador local que será usado para configurar o GPO.</span><span class="sxs-lookup"><span data-stu-id="aa91f-123">Configure the local machine that will be used to set the GPO.</span></span>
    
1. <span data-ttu-id="aa91f-124">Abra **Painel de Controle\Programas\Programas Padrão\Definir Programas Padrão** e defina o Internet Explorer como padrão.</span><span class="sxs-lookup"><span data-stu-id="aa91f-124">Open **Control Panel\Programs\Default Programs\Set Default Programs** and set Internet Explorer as the default.</span></span> 
    
2. <span data-ttu-id="aa91f-125">Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a opção para editar uma política existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="aa91f-125">Open Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
1. <span data-ttu-id="aa91f-126">Navegue para **\<Computador/Usuário\> Configuração\Políticas\Preferências\Configurações do Windows**.</span><span class="sxs-lookup"><span data-stu-id="aa91f-126">Navigate to **\<Computer/User\> Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="aa91f-127">Clique com o botão direito do mouse em **Registro/Novo** e selecione **Assistente do Registro**.</span><span class="sxs-lookup"><span data-stu-id="aa91f-127">Right-click on **Registry\New** and select **Registry Wizard**.</span></span>
    
3. <span data-ttu-id="aa91f-128">Na janela do Navegador do Registro, selecione **Computador local** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="aa91f-128">From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
4. <span data-ttu-id="aa91f-p105">Navegue para **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selecione o valor ProgID. Verifique se o valor tem a seguinte aparência, conforme exibido abaixo:</span><span class="sxs-lookup"><span data-stu-id="aa91f-p105">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure the value looks like the one below:</span></span> 
    
    ![Selecione o valor ProgID em Editar Cadeia de Caracteres](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. <span data-ttu-id="aa91f-p106">Navegue para **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selecione o valor ProgID. Verifique se o valor tem a seguinte aparência, conforme exibido abaixo:</span><span class="sxs-lookup"><span data-stu-id="aa91f-p106">Navigate to **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** and select the ProgId value. Make sure that the value looks like the one below:</span></span> 
    
    ![Selecione a ProgID para HTTPS em Editar Cadeia de Caracteres](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. <span data-ttu-id="aa91f-135">Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="aa91f-135">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
