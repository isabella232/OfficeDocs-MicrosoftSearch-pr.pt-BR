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
ROBOTS: NOINDEX
description: Saiba como definir o Bing como home page padrão para a empresa com a Pesquisa da Microsoft.
ms.openlocfilehash: 0fc16bc7389b8cfffc2ad528b3b10c7ae1d498c3
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591175"
---
# <a name="set-default-homepage"></a><span data-ttu-id="6c9b0-103">Definir a home page padrão</span><span class="sxs-lookup"><span data-stu-id="6c9b0-103">Set default homepage</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c9b0-104">Este artigo se aplica à Pesquisa do Microsoft no portal de administração do Bing.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-104">This article applies to the Microsoft Search in Bing admin portal.</span></span> <span data-ttu-id="6c9b0-105">Estamos movendo o portal para o centro de administração do Microsoft 365 e, posteriormente, ele será removido.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-105">We’re moving the portal to the Microsoft 365 admin center, and then it will be removed.</span></span> <span data-ttu-id="6c9b0-106">Recomendamos que você use o centro de administração do Microsoft 365 para começar.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-106">We recommend that you use the Microsoft 365 admin center to get started.</span></span> [<span data-ttu-id="6c9b0-107">Visão geral da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-107">Overview of Microsoft Search</span></span>](overview-microsoft-search.md)

<span data-ttu-id="6c9b0-108">Configurar o navegador, o mecanismo de pesquisa e a home page padrão ajuda os usuários a descobrir os recursos, promove o uso e proporciona uma experiência aprimorada da Pesquisa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-108">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search  capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="6c9b0-109">Para definir a home page padrão da organização, faça os procedimentos abaixo.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-109">To set the default homepage for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="6c9b0-110">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="6c9b0-110">Internet Explorer</span></span>

### <a name="internet-explorer-50-or-later"></a><span data-ttu-id="6c9b0-111">Internet Explorer 5.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="6c9b0-111">Internet Explorer 5.0 or later</span></span>

1. <span data-ttu-id="6c9b0-112">Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a opção para editar uma política existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-112">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="6c9b0-113">Navegue para **Configuração do Usuário\Preferências\Configurações do Painel de Controle\Configurações da Internet**.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-113">Navigate to **User Configuration\Preferences\Control Panel Settings\Internet Settings**.</span></span>
    
3. <span data-ttu-id="6c9b0-114">Clique com o botão direito do mouse em **Configurações da Internet** e selecione **Internet Explorer 10**.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-114">Right-click on **Internet Settings** and select **Internet Explorer 10**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6c9b0-115">Selecione a opção do Internet Explorer 10 a fim de aplicar as configurações para o Internet Explorer 11, pois as mesmas configurações se aplicam à esta versão do programa.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-115">You need to select the option of Internet Explorer 10 to apply the settings for Internet Explorer 11 as the same settings apply to Internet Explorer 11.</span></span> 
  
4. <span data-ttu-id="6c9b0-p102">As configurações sublinhadas em vermelho não são configuradas na máquina de destino, exceto as sublinhadas em verde. Para alterar o sublinhado, use as seguintes teclas de função:</span><span class="sxs-lookup"><span data-stu-id="6c9b0-p102">Settings which are underlined in red are not configured at the target machine, while settings underlined in green are configured at the target machine. To change the underlining, use the following function keys:</span></span>
    
    <span data-ttu-id="6c9b0-118">F5 – Habilitar todas as configurações na guia atual</span><span class="sxs-lookup"><span data-stu-id="6c9b0-118">F5 - Enable all settings on the current tab</span></span>
    
    <span data-ttu-id="6c9b0-119">F6 – Habilitar a configuração atualmente selecionada</span><span class="sxs-lookup"><span data-stu-id="6c9b0-119">F6 - Enable the currently selected setting</span></span>
    
    <span data-ttu-id="6c9b0-120">F7 – Desabilitar a configuração atualmente selecionada</span><span class="sxs-lookup"><span data-stu-id="6c9b0-120">F7 - Disable the currently selected setting</span></span>
    
    <span data-ttu-id="6c9b0-121">F8 – Desabilitar todas as configurações na guia atual</span><span class="sxs-lookup"><span data-stu-id="6c9b0-121">F8 - Disable all settings on the current tab</span></span>
    
5. <span data-ttu-id="6c9b0-p103">Pressione **F8** para desabilitar todas as configurações antes de configurar tudo. A tela deve ter a seguinte aparência:</span><span class="sxs-lookup"><span data-stu-id="6c9b0-p103">Press **F8** to disable all settings before configuring anything. The screen should look like this:</span></span> 
    
    ![Caixa de diálogo Propriedades do Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. <span data-ttu-id="6c9b0-125">Pressione **F6** na configuração da Página Inicial e insira `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="6c9b0-125">Press **F6** on the Home page setting and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="6c9b0-126">Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-126">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6c9b0-127">Os usuários ainda poderão alterar a home page, após a definição dessa política.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-127">Users can still change the homepage after this policy is set.</span></span> 
  
## <a name="microsoft-edge"></a><span data-ttu-id="6c9b0-128">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6c9b0-128">Microsoft Edge</span></span>

### <a name="windows-10-version-1511-or-later"></a><span data-ttu-id="6c9b0-129">Windows 10, versão 1511 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-129">Windows 10, Version 1511 or later</span></span>

1. <span data-ttu-id="6c9b0-130">Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a opção para editar uma política existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-130">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="6c9b0-131">Navegue para **Modelos Administrativos\Componentes do Windows\Microsoft Edge**</span><span class="sxs-lookup"><span data-stu-id="6c9b0-131">Navigate to **Administrative Templates\Windows Components\Microsoft Edge**</span></span>
    
1. <span data-ttu-id="6c9b0-132">Clique duas vezes em **Configurar páginas iniciais**, defina como **Habilitado** e insira `https://www.bing.com/business`</span><span class="sxs-lookup"><span data-stu-id="6c9b0-132">Double-click **Configure Start pages**, set it to **Enabled**, and enter `https://www.bing.com/business`</span></span>
    
3. <span data-ttu-id="6c9b0-133">Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-133">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
> [!CAUTION]
> <span data-ttu-id="6c9b0-134">Os usuários não poderão alterar o provedor de pesquisa, após a definição dessa política.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-134">Users won't be able to change the search provider after this policy is set.</span></span> 
  
## <a name="google-chrome"></a><span data-ttu-id="6c9b0-135">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="6c9b0-135">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="6c9b0-136">Windows XP SP2 ou posterior</span><span class="sxs-lookup"><span data-stu-id="6c9b0-136">Windows XP SP2 or later</span></span>

<span data-ttu-id="6c9b0-137">O artigo do Suporte do Windows sobre como gerenciar arquivos ADMX, bem como os arquivos ADMX mais recentes para as diversas versões do Windows estão disponíveis [no Suporte da Microsoft](https://support.microsoft.com/pt-BR/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="6c9b0-137">The Windows Support article on managing ADMX files and the latest ADMX files for different versions of Windows can be found [on Microsoft Support](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>

<span data-ttu-id="6c9b0-138">É necessário também o arquivo de política do Google mais recente, que está disponível na página de [Ajuda do Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).</span><span class="sxs-lookup"><span data-stu-id="6c9b0-138">You'll also need the latest Google policy file, which you can find on [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="6c9b0-p104">Caso as configurações descritas nesta seção não estejam disponíveis no GPMC, baixe o arquivo ADMX apropriado e copie-o para o [Repositório Central](https://docs.microsoft.com/pt-BR/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). O Repositório Central no controlador é uma pasta com a seguinte convenção de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="6c9b0-p104">If the settings described in this section can't be found inside of GPMC, download the appropriate ADMX and copy them to the [central store](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="6c9b0-141">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="6c9b0-141">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="6c9b0-p105">Cada domínio processado pelo controlador deve ter uma pasta separada. O comando a seguir pode ser usado para copiar o arquivo ADMX do prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="6c9b0-p105">Each domain your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="6c9b0-144">Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a opção para editar uma política existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-144">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="6c9b0-145">Verifique se as seguintes pastas estão exibidas na seção **Modelos Administrativos** da *Configuração do Computador e da Configuração do Usuário*: Google Chrome e Configurações Padrão do Google Chrome (os usuários podem substituir).</span><span class="sxs-lookup"><span data-stu-id="6c9b0-145">Make sure the following folders appear in the **Administrative Templates** section of both *User/Computer Configuration*: Google Chrome and Google Chrome - Default Settings (users can override).</span></span>
    
   - <span data-ttu-id="6c9b0-146">As configurações da primeira seção são permanentes e o administrador local não poderá alterá-las.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-146">The settings of the first section are fixed and the local administrator won't be able to change them.</span></span>
    
   - <span data-ttu-id="6c9b0-p106">As configurações da última seção de políticas podem ser alteradas pelos usuários nas configurações do navegador. Você deve determinar se os usuários podem substituir a configuração padrão. Nas etapas a seguir, altere a configuração na pasta que corresponde à política e às necessidades da organização. As etapas abaixo usam as Configurações Padrão do Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-p106">The settings of the latter section of policies can be changed by users in their browser settings. You should decide if users can override your default setting. In the following steps, change in the setting in the folder that corresponds to your organization policy and needs. The steps below use the Google Chrome - Default Settings as the default.</span></span>
    
3. <span data-ttu-id="6c9b0-151">Navegue para **&lt;Computador/Configuração do Usuário&gt;\Modelos Administrativos\Google Chrome – Configurações Padrão\Home Page**.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-151">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\Home Page**.</span></span>
    
4. <span data-ttu-id="6c9b0-152">Clique duas vezes em **Usar página de nova guia como home page** e defina como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-152">Double-click **Use New Tab Page as homepage**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="6c9b0-153">Navegue para **&lt;Computador/Configuração do Usuário&gt;\Modelos Administrativos\Google Chrome – Configurações Padrão\Página de Nova Guia**.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-153">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Google Chrome - Default Settings\New Tab Page**.</span></span>
    
6. <span data-ttu-id="6c9b0-154">Clique duas vezes em **Configurar a URL da página de nova guia**, defina como **Habilitado** e insira `https://www.bing.com/business?form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="6c9b0-154">Double-click **Configure the New Tab Page URL**, set it to **Enabled**, and enter `https://www.bing.com/business?form=BFBSPR`</span></span>
    
7. <span data-ttu-id="6c9b0-155">Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-155">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="6c9b0-156">Os usuários poderão alterar a home page, após a definição dessa política.</span><span class="sxs-lookup"><span data-stu-id="6c9b0-156">Users will be able to change the home page after this policy is set.</span></span>