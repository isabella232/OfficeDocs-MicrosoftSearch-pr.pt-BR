---
title: Definir a home page padrão
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
description: Saiba como definir o Bing como home page padrão para a empresa com a Pesquisa da Microsoft.
ms.openlocfilehash: db0611ebd7f4a8344664825bbb42025f3bb36486
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508967"
---
# <a name="set-default-homepage"></a><span data-ttu-id="d94b8-103">Definir a home page padrão</span><span class="sxs-lookup"><span data-stu-id="d94b8-103">Set default homepage</span></span>

<span data-ttu-id="d94b8-104">Configurar o navegador, o mecanismo de pesquisa e a home page padrão ajuda os usuários a descobrir os recursos, promove o uso e proporciona uma experiência aprimorada da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d94b8-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search  capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="d94b8-105">Para definir a home page padrão da organização, faça os procedimentos abaixo.</span><span class="sxs-lookup"><span data-stu-id="d94b8-105">To set the default homepage for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="d94b8-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="d94b8-106">Internet Explorer</span></span>

### <a name="internet-explorer-50-or-later"></a><span data-ttu-id="d94b8-107">Internet Explorer 5.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="d94b8-107">Internet Explorer 5.0 or later</span></span>

1. <span data-ttu-id="d94b8-108">Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a opção para editar uma política existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="d94b8-108">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="d94b8-109">Navegue para **Configuração do Usuário\Preferências\Configurações do Painel de Controle\Configurações da Internet**.</span><span class="sxs-lookup"><span data-stu-id="d94b8-109">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="d94b8-110">Clique com o botão direito do mouse em **Configurações da Internet** e selecione **Internet Explorer 10**.</span><span class="sxs-lookup"><span data-stu-id="d94b8-110">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d94b8-111">Selecione a opção do Internet Explorer 10 a fim de aplicar as configurações para o Internet Explorer 11, pois as mesmas configurações se aplicam à esta versão do programa.</span><span class="sxs-lookup"><span data-stu-id="d94b8-111">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="d94b8-p101">As configurações sublinhadas em vermelho não são configuradas na máquina de destino, exceto as sublinhadas em verde. Para alterar o sublinhado, use as seguintes teclas de função:</span><span class="sxs-lookup"><span data-stu-id="d94b8-p101">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="d94b8-114">F5 – Habilitar todas as configurações na guia atual</span><span class="sxs-lookup"><span data-stu-id="d94b8-114">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="d94b8-115">F6 – Habilitar a configuração atualmente selecionada</span><span class="sxs-lookup"><span data-stu-id="d94b8-115">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="d94b8-116">F7 – Desabilitar a configuração atualmente selecionada</span><span class="sxs-lookup"><span data-stu-id="d94b8-116">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="d94b8-117">F8 – Desabilitar todas as configurações na guia atual</span><span class="sxs-lookup"><span data-stu-id="d94b8-117">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="d94b8-p102">Pressione **F8** para desabilitar todas as configurações antes de configurar tudo. A tela deve ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="d94b8-p102">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Caixa de diálogo Propriedades do Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="d94b8-121">Pressione **F6** na configuração da Página Inicial e insira `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="d94b8-121">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="d94b8-122">Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="d94b8-122">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d94b8-123">Os usuários ainda poderão alterar a home page, após a definição dessa política.</span><span class="sxs-lookup"><span data-stu-id="d94b8-123">Users can still change the homepage after this policy is set.</span></span> 
  
## <a name="microsoft-edge"></a><span data-ttu-id="d94b8-124">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="d94b8-124">Microsoft Edge</span></span>

### <a name="windows-10-version-1511-or-later"></a><span data-ttu-id="d94b8-125">Windows 10, versão 1511 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="d94b8-125">Windows 10, Version 1511 or later</span></span>

1. <span data-ttu-id="d94b8-126">Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a opção para editar uma política existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="d94b8-126">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="d94b8-127">Navegue para **Modelos Administrativos\Componentes do Windows\Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="d94b8-127">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>
    
1. <span data-ttu-id="d94b8-128">Clique duas vezes em **Configurar páginas iniciais**, defina como **Habilitado** e insira `https://www.bing.com/business`</span><span class="sxs-lookup"><span data-stu-id="d94b8-128">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
    
3. <span data-ttu-id="d94b8-129">Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="d94b8-129">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="d94b8-130">Os usuários não poderão alterar o provedor de pesquisa, após a definição dessa política.</span><span class="sxs-lookup"><span data-stu-id="d94b8-130">Users won't be able to change the search provider after this policy is set.</span></span> 
  
## <a name="google-chrome"></a><span data-ttu-id="d94b8-131">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="d94b8-131">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="d94b8-132">Windows XP SP2 ou posterior</span><span class="sxs-lookup"><span data-stu-id="d94b8-132">Windows XP SP2 or later</span></span>

<span data-ttu-id="d94b8-133">O artigo do Suporte do Windows sobre como gerenciar arquivos ADMX, bem como os arquivos ADMX mais recentes para as diversas versões do Windows estão disponíveis [no Suporte da Microsoft](https://support.microsoft.com/pt-BR/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="d94b8-133">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/pt-BR/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="d94b8-134">É necessário também o arquivo de política do Google mais recente, que está disponível na página de [Ajuda do Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).</span><span class="sxs-lookup"><span data-stu-id="d94b8-134">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="d94b8-p103">Caso as configurações descritas nesta seção não estejam disponíveis no GPMC, baixe o arquivo ADMX apropriado e copie-o para o [Repositório Central](https://docs.microsoft.com/pt-BR/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). O Repositório Central no controlador é uma pasta com a seguinte convenção de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="d94b8-p103">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/pt-BR/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="d94b8-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="d94b8-137">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="d94b8-p104">Cada domínio processado pelo controlador deve ter uma pasta separada. O comando a seguir pode ser usado para copiar o arquivo ADMX do prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="d94b8-p104">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="d94b8-140">Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a opção para editar uma política existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="d94b8-140">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="d94b8-141">Verifique se as seguintes pastas estão exibidas na seção **Modelos Administrativos** da *Configuração do Computador e da Configuração do Usuário*: Google Chrome e Configurações Padrão do Google Chrome (os usuários podem substituir).</span><span class="sxs-lookup"><span data-stu-id="d94b8-141">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
    
   - <span data-ttu-id="d94b8-142">As configurações da primeira seção são permanentes e o administrador local não poderá alterá-las.</span><span class="sxs-lookup"><span data-stu-id="d94b8-142">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
    
   - <span data-ttu-id="d94b8-p105">As configurações da última seção de políticas podem ser alteradas pelos usuários nas configurações do navegador. Você deve determinar se os usuários podem substituir a configuração padrão. Nas etapas a seguir, altere a configuração na pasta que corresponde à política e às necessidades da organização. As etapas abaixo usam as Configurações Padrão do Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="d94b8-p105">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>
    
3. <span data-ttu-id="d94b8-147">Navegue para **&lt;Computador/Configuração do Usuário&gt;\Modelos Administrativos\Google Chrome – Configurações Padrão\Home Page**.</span><span class="sxs-lookup"><span data-stu-id="d94b8-147">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span>
    
4. <span data-ttu-id="d94b8-148">Clique duas vezes em **Usar página de nova guia como home page** e defina como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="d94b8-148">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="d94b8-149">Navegue para **&lt;Computador/Configuração do Usuário&gt;\Modelos Administrativos\Google Chrome – Configurações Padrão\Página de Nova Guia**.</span><span class="sxs-lookup"><span data-stu-id="d94b8-149">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span>
    
6. <span data-ttu-id="d94b8-150">Clique duas vezes em **Configurar a URL da página de nova guia**, defina como **Habilitado** e insira `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="d94b8-150">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="d94b8-151">Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="d94b8-151">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="d94b8-152">Os usuários poderão alterar a home page, após a definição dessa política.</span><span class="sxs-lookup"><span data-stu-id="d94b8-152">Users will be able to change the home page after this policy is set.</span></span>