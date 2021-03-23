---
title: Definir a home page padrão
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
ms.assetid: c020bd72-9906-4dfd-bc77-57287f5927ce
description: Saiba como definir o Bing como home page padrão para a empresa com a Pesquisa da Microsoft.
ms.openlocfilehash: 0d8fac0302e672c603853185ff0810bf6d42371c
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031670"
---
# <a name="make-bingcom-the-default-home-page"></a><span data-ttu-id="3c4a8-103">Definir o Bing.com como página inicial padrão</span><span class="sxs-lookup"><span data-stu-id="3c4a8-103">Make Bing.com the default home page</span></span>

<span data-ttu-id="3c4a8-104">Este artigo explica como definir o Bing como o mecanismo de pesquisa padrão para o Microsoft Edge, o Google Chrome e o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-104">This article explains how to set Bing.com as the default home page for Microsoft Edge, Google Chrome, and Internet Explorer browsers.</span></span> 
  
 
## <a name="microsoft-edge-on-windows-10-version-1511-or-later"></a><span data-ttu-id="3c4a8-105">Microsoft Edge no Windows 10, Versão 1511 ou posterior</span><span class="sxs-lookup"><span data-stu-id="3c4a8-105">Microsoft Edge on Windows 10, Version 1511 or later</span></span>

<span data-ttu-id="3c4a8-106">Os usuários não poderão alterar isso após a definição dessa política.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-106">Users won't be able to change this once this policy is set.</span></span> 

1. <span data-ttu-id="3c4a8-107">Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a alterne para editar uma política existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-107">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span> 
1. <span data-ttu-id="3c4a8-108">Navegue até **Modelos Administrativos\Componentes do Windows\Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-108">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**.</span></span>    
1. <span data-ttu-id="3c4a8-109">Clique duas vezes em **Configurar páginas iniciais**, defina como **Habilitado** e insira `https://www.bing.com/business`</span><span class="sxs-lookup"><span data-stu-id="3c4a8-109">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
1.  <span data-ttu-id="3c4a8-110">Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-110">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

  
## <a name="google-chrome-on-windows-xp-sp2-or-later"></a><span data-ttu-id="3c4a8-111">Google Chrome no Windows XP SP2 ou posterior</span><span class="sxs-lookup"><span data-stu-id="3c4a8-111">Google Chrome on Windows XP SP2 or later</span></span>


<span data-ttu-id="3c4a8-112">O artigo do Suporte do Windows sobre como gerenciar arquivos ADMX, bem como os arquivos ADMX mais recentes para as diversas versões do Windows estão disponíveis [no Suporte da Microsoft](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="3c4a8-112">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="3c4a8-113">É necessário também o arquivo de política do Google mais recente, que está disponível na página de [Ajuda do Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).</span><span class="sxs-lookup"><span data-stu-id="3c4a8-113">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="3c4a8-p101">Caso as configurações descritas nesta seção não estejam disponíveis no GPMC, baixe o arquivo ADMX apropriado e copie-o para o [Repositório Central](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). O Repositório Central no controlador é uma pasta com a seguinte convenção de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="3c4a8-p101">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="3c4a8-116">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="3c4a8-116">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="3c4a8-p102">Cada domínio processado pelo controlador deve ter uma pasta separada. O comando a seguir pode ser usado para copiar o arquivo ADMX do prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="3c4a8-p102">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="3c4a8-119">Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a opção para editar uma política existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-119">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
1. <span data-ttu-id="3c4a8-120">Verifique se as seguintes pastas estão exibidas na seção **Modelos Administrativos** da *Configuração do Computador e da Configuração do Usuário*: Google Chrome e Configurações Padrão do Google Chrome (os usuários podem substituir).</span><span class="sxs-lookup"><span data-stu-id="3c4a8-120">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
   - <span data-ttu-id="3c4a8-121">As configurações da primeira seção são permanentes e o administrador local não poderá alterá-las.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-121">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
   - <span data-ttu-id="3c4a8-p103">As configurações da última seção de políticas podem ser alteradas pelos usuários nas configurações do navegador. Você deve determinar se os usuários podem substituir a configuração padrão. Nas etapas a seguir, altere a configuração na pasta que corresponde à política e às necessidades da organização. As etapas abaixo usam as Configurações Padrão do Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-p103">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>

1. <span data-ttu-id="3c4a8-126">Navegue para **&lt;Computador/Configuração do Usuário&gt;\Modelos Administrativos\Google Chrome – Configurações Padrão\Home Page**.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-126">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span> 
1. <span data-ttu-id="3c4a8-127">Clique duas vezes em **Usar página de nova guia como home page** e defina como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-127">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span> 
1. <span data-ttu-id="3c4a8-128">Navegue para **&lt;Computador/Configuração do Usuário&gt;\Modelos Administrativos\Google Chrome – Configurações Padrão\Página de Nova Guia**.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-128">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span> 
1. <span data-ttu-id="3c4a8-129">Clique duas vezes em **Configurar a URL da página de nova guia**, defina como **Habilitado** e insira `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="3c4a8-129">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span> 
1. <span data-ttu-id="3c4a8-130">Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-130">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

## <a name="internet-explorer-50-or-later"></a><span data-ttu-id="3c4a8-131">Internet Explorer 5.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="3c4a8-131">Internet Explorer 5.0 or later</span></span>
<span data-ttu-id="3c4a8-132">Os usuários ainda poderão alterar a home page após a definição dessa política.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-132">Users can still change the home page after this policy is set.</span></span> 

1. <span data-ttu-id="3c4a8-133">Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a opção para editar uma política existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-133">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="3c4a8-134">Navegue para **Configuração do Usuário\Preferências\Configurações do Painel de Controle\Configurações da Internet**.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-134">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="3c4a8-135">Clique com o botão direito do mouse em **Configurações da Internet** e selecione **Internet Explorer 10**.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-135">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3c4a8-136">Selecione a opção do Internet Explorer 10 a fim de aplicar as configurações para o Internet Explorer 11, pois as mesmas configurações se aplicam à esta versão do programa.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-136">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="3c4a8-p104">As configurações sublinhadas em vermelho não são configuradas na máquina de destino, exceto as sublinhadas em verde. Para alterar o sublinhado, use as seguintes teclas de função:</span><span class="sxs-lookup"><span data-stu-id="3c4a8-p104">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="3c4a8-139">F5 – Habilitar todas as configurações na guia atual</span><span class="sxs-lookup"><span data-stu-id="3c4a8-139">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="3c4a8-140">F6 – Habilitar a configuração atualmente selecionada</span><span class="sxs-lookup"><span data-stu-id="3c4a8-140">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="3c4a8-141">F7 – Desabilitar a configuração atualmente selecionada</span><span class="sxs-lookup"><span data-stu-id="3c4a8-141">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="3c4a8-142">F8 – Desabilitar todas as configurações na guia atual</span><span class="sxs-lookup"><span data-stu-id="3c4a8-142">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="3c4a8-p105">Pressione **F8** para desabilitar todas as configurações antes de configurar tudo. A tela deve ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="3c4a8-p105">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Caixa de diálogo Propriedades do Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="3c4a8-146">Pressione **F6** na configuração da Página Inicial e insira `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="3c4a8-146">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="3c4a8-147">Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="3c4a8-147">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>