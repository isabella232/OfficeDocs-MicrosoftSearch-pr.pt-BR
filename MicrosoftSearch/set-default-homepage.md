---
title: Definir a página inicial padrão
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
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
description: Saiba como configurar o Bing como a página inicial padrão para sua empresa com o Microsoft Search.
ms.openlocfilehash: db0611ebd7f4a8344664825bbb42025f3bb36486
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612486"
---
# <a name="set-default-homepage"></a><span data-ttu-id="ff7a6-103">Definir a página inicial padrão</span><span class="sxs-lookup"><span data-stu-id="ff7a6-103">Set default homepage</span></span>

<span data-ttu-id="ff7a6-104">Configurar o navegador padrão, o mecanismo de pesquisa padrão e a página inicial padrão ajudarão os usuários Descubra os recursos do Microsoft Search, incentivar o uso de mais e fornecer uma experiência mais suave.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search  capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="ff7a6-105">Para definir a página inicial padrão para sua organização, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-105">To set the default homepage for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="ff7a6-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="ff7a6-106">Internet Explorer</span></span>

### <a name="internet-explorer-50-or-later"></a><span data-ttu-id="ff7a6-107">Internet Explorer 5.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="ff7a6-107">Internet Explorer 5.0 or later</span></span>

1. <span data-ttu-id="ff7a6-108">Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e alterne para a edição de qualquer política existente ou criar um novo.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-108">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="ff7a6-109">Navegue até **configurações do usuário Configuration\Preferences\Control painel Settings\Internet**.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-109">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="ff7a6-110">Com o botão direito em **Configurações da Internet** e selecione o **Internet Explorer 10**.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-110">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ff7a6-111">Você precisa selecionar a opção do Internet Explorer 10 para aplicar as configurações para o Internet Explorer 11, conforme as mesmas configurações se aplicam ao Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-111">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="ff7a6-p101">Configurações que são sublinhadas em vermelho não são definidas na máquina de destino, enquanto as configurações sublinhadas em verde são definidas na máquina de destino. Para alterar o sublinhado, use as teclas de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="ff7a6-p101">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="ff7a6-114">F5 - habilita todas as configurações na guia atual</span><span class="sxs-lookup"><span data-stu-id="ff7a6-114">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="ff7a6-115">F6 - habilitar a configuração selecionada no momento</span><span class="sxs-lookup"><span data-stu-id="ff7a6-115">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="ff7a6-116">F7 - desabilitar a configuração selecionada no momento</span><span class="sxs-lookup"><span data-stu-id="ff7a6-116">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="ff7a6-117">F8 - desabilita todas as configurações na guia atual</span><span class="sxs-lookup"><span data-stu-id="ff7a6-117">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="ff7a6-p102">Pressione **F8** para desabilitar todas as configurações antes de configurar nada. A tela deve ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="ff7a6-p102">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Caixa de diálogo Propriedades do Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="ff7a6-121">Pressione a **tecla F6** na configuração da Home page e insira`https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="ff7a6-121">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="ff7a6-122">Impor o GPO resultante ao vinculá-lo ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-122">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ff7a6-123">Os usuários ainda podem alterar a página inicial após essa diretiva estiver definida.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-123">Users can still change the homepage after this policy is set.</span></span> 
  
## <a name="microsoft-edge"></a><span data-ttu-id="ff7a6-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ff7a6-124">Microsoft Edge</span></span>

### <a name="windows-10-version-1511-or-later"></a><span data-ttu-id="ff7a6-125">Windows 10, versão 1511 ou posterior</span><span class="sxs-lookup"><span data-stu-id="ff7a6-125">Windows 10, Version 1511 or later</span></span>

1. <span data-ttu-id="ff7a6-126">Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e alterne para a edição de qualquer política existente ou criar um novo.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-126">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="ff7a6-127">Navegue até a **borda de Windows\Console Administrativos\Componentes administrativas**</span><span class="sxs-lookup"><span data-stu-id="ff7a6-127">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>
    
1. <span data-ttu-id="ff7a6-128">Clique duas vezes em **Configurar Start pages**, defini-la como **habilitada**e insira`https://www.bing.com/business`</span><span class="sxs-lookup"><span data-stu-id="ff7a6-128">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
    
3. <span data-ttu-id="ff7a6-129">Impor o GPO resultante ao vinculá-lo ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-129">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="ff7a6-130">Os usuários não poderão alterar o provedor de pesquisa depois que essa diretiva estiver definida.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-130">Users won't be able to change the search provider after this policy is set.</span></span> 
  
## <a name="google-chrome"></a><span data-ttu-id="ff7a6-131">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="ff7a6-131">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="ff7a6-132">Windows XP SP2 ou posterior</span><span class="sxs-lookup"><span data-stu-id="ff7a6-132">Windows XP SP2 or later</span></span>

<span data-ttu-id="ff7a6-133">O artigo de suporte do Windows no gerenciamento de arquivos ADMX e os arquivos ADMX mais recentes para diferentes versões do Windows pode ser encontrado [no suporte da Microsoft](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="ff7a6-133">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="ff7a6-134">Você também precisará o arquivo de diretiva mais recente do Google, que pode ser encontrado na [Ajuda do Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).</span><span class="sxs-lookup"><span data-stu-id="ff7a6-134">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="ff7a6-p103">Se as configurações descritas nesta seção não podem ser encontradas no GPMC, baixe o ADMX apropriado e copiá-los para o [repositório central](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Um repositório central no controlador de é uma pasta com a seguinte convenção de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="ff7a6-p103">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="ff7a6-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="ff7a6-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="ff7a6-p104">Cada domínio seus identificadores de controlador devem obter uma pasta separada. O comando a seguir pode ser usado para copiar o arquivo ADMX no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="ff7a6-p104">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="ff7a6-140">Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e alterne para a edição de qualquer política existente ou criar um novo.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-140">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="ff7a6-141">Verifique se as seguintes pastas aparecem na seção **Modelos administrativos** de ambas as *Configuração do computador do usuário*: Google Chrome e Google Chrome - Default Settings (os usuários podem substituir).</span><span class="sxs-lookup"><span data-stu-id="ff7a6-141">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
    
   - <span data-ttu-id="ff7a6-142">As configurações da primeira seção corrigidas e o administrador local não será possível alterá-los.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-142">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
    
   - <span data-ttu-id="ff7a6-p105">As configurações da seção última das diretivas podem ser alteradas por usuários em suas configurações do navegador. Você deve decidir se os usuários podem substituir sua configuração padrão. Nas etapas a seguir, altere na configuração na pasta correspondente para suas necessidades e a política da organização. As etapas a seguir usam o Google Chrome - configurações padrão como o padrão.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-p105">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>
    
3. <span data-ttu-id="ff7a6-147">Navegue até \*\* &lt;configuração do usuário do computador&gt;\Administrative Templates\Google Chrome - página de Settings\Home padrão\*\*.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-147">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span>
    
4. <span data-ttu-id="ff7a6-148">Clique duas vezes em **Nova página de guia uso como home page**e defina-o como **habilitada**.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-148">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="ff7a6-149">Navegue até \*\* &lt;configuração do usuário do computador&gt;\Administrative Templates\Google Chrome - página da guia Settings\New padrão\*\*.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-149">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span>
    
6. <span data-ttu-id="ff7a6-150">Clique duas vezes em **Configure a URL da página nova guia**, defini-la como **habilitada**e insira`https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="ff7a6-150">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="ff7a6-151">Impor o GPO resultante ao vinculá-lo ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-151">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="ff7a6-152">Os usuários poderão alterar a home page, depois que essa diretiva estiver definida.</span><span class="sxs-lookup"><span data-stu-id="ff7a6-152">Users will be able to change the home page after this policy is set.</span></span>