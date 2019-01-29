---
title: Definir mecanismo de pesquisa padrão
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
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
description: Saiba como configurar o Bing como o mecanismo de pesquisa padrão da sua empresa usar o Microsoft Search.
ms.openlocfilehash: a0798da94f4433bb754c71b9e0d00e09ba5a543b
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612526"
---
# <a name="set-default-search-engine"></a><span data-ttu-id="9df28-103">Definir mecanismo de pesquisa padrão</span><span class="sxs-lookup"><span data-stu-id="9df28-103">Set default search engine</span></span>

<span data-ttu-id="9df28-104">Configurar o navegador padrão, o mecanismo de pesquisa padrão e a página inicial padrão ajudarão os usuários Descubra os recursos do Microsoft Search, incentivar o uso de mais e fornecer uma experiência mais suave.</span><span class="sxs-lookup"><span data-stu-id="9df28-104">Configuring the default browser, default search engine, and default homepage will help your users discover Microsoft Search capabilities, encourage more usage, and provide a smoother experience.</span></span>
  
<span data-ttu-id="9df28-105">Para definir o mecanismo de pesquisa padrão para sua organização, siga as etapas abaixo.</span><span class="sxs-lookup"><span data-stu-id="9df28-105">To set the default search engine for your organization, follow the steps below.</span></span>
  
## <a name="internet-explorer"></a><span data-ttu-id="9df28-106">Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="9df28-106">Internet Explorer</span></span>

### <a name="internet-explorer-11"></a><span data-ttu-id="9df28-107">Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="9df28-107">Internet Explorer 11</span></span>

<span data-ttu-id="9df28-108">Os usuários poderão alterar o provedor de pesquisa depois que essa diretiva estiver definida.</span><span class="sxs-lookup"><span data-stu-id="9df28-108">Users will be able to change the search provider after this policy is set.</span></span>
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a><span data-ttu-id="9df28-109">1. configure a máquina local que será usada para definir o GPO</span><span class="sxs-lookup"><span data-stu-id="9df28-109">1. Configure the local machine that will be used to set the GPO</span></span>

<span data-ttu-id="9df28-110">Cole o seguinte texto em um registro (\*. reg) arquivos.</span><span class="sxs-lookup"><span data-stu-id="9df28-110">Paste the following text into a reg(\*.reg) file.</span></span>
  
<span data-ttu-id="9df28-111">Editor do Registro do Windows Versão 5.00</span><span class="sxs-lookup"><span data-stu-id="9df28-111">Windows Registry Editor Version 5.00</span></span>
  
<pre>[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes]
"DefaultScope"="{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}"
[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes\{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}]
"Codepage"=dword:0000fde9
"DisplayName"="Microsoft Search in Bing"
"OSDFileURL"="https://www.bing.com/sa/osd/bfb.xml"
"FaviconURL"="https://www.bing.com/sa/simg/bb.ico"
"SuggestionsURL_JSON"="https://business.ing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA"
"ShowSearchSuggestions"=dword:00000001
"URL"="https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR"</pre>
  
<span data-ttu-id="9df28-p101">Duas vezes no arquivo criado e siga as etapas para importar o arquivo. A importação bem-sucedida deve resultar na caixa de diálogo seguinte:</span><span class="sxs-lookup"><span data-stu-id="9df28-p101">Double-click the file created and follow the steps to import the file. A successful import should result in the following dialog:</span></span>
  
![Mensagem de importação bem-sucedida do Editor do registro](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a><span data-ttu-id="9df28-115">2. Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e vá para editar uma política existente ou criar um novo</span><span class="sxs-lookup"><span data-stu-id="9df28-115">2. Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one</span></span>

1. <span data-ttu-id="9df28-116">Navegue até **as configurações do usuário Configuration\Policies\Preferences\Windows**.</span><span class="sxs-lookup"><span data-stu-id="9df28-116">Navigate to **User Configuration\Policies\Preferences\Windows Settings**.</span></span>
    
2. <span data-ttu-id="9df28-p102">Com o botão direito em **Registry\New** e selecione **Assistente do registro**. Da janela do navegador do registro, selecione o **Computador Local** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9df28-p102">Right-click on **Registry\New** and select **Registry Wizard**. From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
    
3. <span data-ttu-id="9df28-119">Navegue até **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span><span class="sxs-lookup"><span data-stu-id="9df28-119">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span></span>
    
4. <span data-ttu-id="9df28-120">Dessa chave, certifique-se de selecionar DefaultScope.</span><span class="sxs-lookup"><span data-stu-id="9df28-120">From this key, make sure to select DefaultScope.</span></span>
    
    ![Navegador de registro com DefaultScope selecionado](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. <span data-ttu-id="9df28-p103">Verifique se todas as chaves de sub, que contém o GUID do Microsoft Search no Bing e cada valor na chave exceto qualquer caminho para os perfis de usuário. Role para baixo para selecionar outros itens.</span><span class="sxs-lookup"><span data-stu-id="9df28-p103">Check all sub keys containing the GUID for Microsoft Search in Bing and every value under the key except any path to user profiles. Scroll down to select other items.</span></span>
    
    ![Navegador de registro com valores adicionais selecionados](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. <span data-ttu-id="9df28-125">Clique em Concluir para completar esta configuração.</span><span class="sxs-lookup"><span data-stu-id="9df28-125">Click Finish to complete this configuration.</span></span>
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a><span data-ttu-id="9df28-126">3. configurar as preferências de usuário para ajudar a eliminar um aviso que o usuário pode fazer quando DefaultScope pesquisa é imposta</span><span class="sxs-lookup"><span data-stu-id="9df28-126">3. Set up User Preferences to help eliminate a warning the user may get when DefaultScope search is enforced</span></span>

<span data-ttu-id="9df28-127">Esse aviso é por design e usuários de um programa tentando modificar suas configurações de alertas.</span><span class="sxs-lookup"><span data-stu-id="9df28-127">This warning is by design and alerts users of a program trying to modify their settings.</span></span>
  
1. <span data-ttu-id="9df28-128">Dentro do mesmo GPO, clique com o botão direito em **Registry\New** e selecione **Assistente do registro**.</span><span class="sxs-lookup"><span data-stu-id="9df28-128">Within the same GPO, right click on **Registry\New** and select **Registry Wizard**.</span></span>
    
2. <span data-ttu-id="9df28-129">Navegue até **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User preferências**.</span><span class="sxs-lookup"><span data-stu-id="9df28-129">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span></span>
    
3. <span data-ttu-id="9df28-130">Selecione a chave de **Preferência do usuário** .</span><span class="sxs-lookup"><span data-stu-id="9df28-130">Select the **User Preference** key.</span></span>
    
4. <span data-ttu-id="9df28-131">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="9df28-131">Click **Finish**.</span></span>
    
5. <span data-ttu-id="9df28-p104">Clique no objeto recém-criado. No painel do lado direito, clique duas vezes no objeto preferências do usuário, altere a **ação** **Excluir e salvar**.</span><span class="sxs-lookup"><span data-stu-id="9df28-p104">Click on the newly created object. On the right-side pane double click on the User Preferences object, change the **Action** to **Delete and Save**.</span></span>
    
<span data-ttu-id="9df28-134">Impor o GPO resultante ao vinculá-lo ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="9df28-134">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
  
## <a name="microsoft-edge"></a><span data-ttu-id="9df28-135">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="9df28-135">Microsoft Edge</span></span>

### <a name="windows-10-version-1703-or-later"></a><span data-ttu-id="9df28-136">Windows 10, versão 1703 ou posterior</span><span class="sxs-lookup"><span data-stu-id="9df28-136">Windows 10, Version 1703 or later</span></span>

<span data-ttu-id="9df28-137">Os usuários poderão alterar o provedor de pesquisa depois que essa diretiva estiver definida.</span><span class="sxs-lookup"><span data-stu-id="9df28-137">Users will be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="9df28-138">Os arquivos ADMX mais recentes para diversas versões do Windows, consulte [como criar e gerenciar o repositório Central de modelos administrativos de diretiva de grupo no Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="9df28-138">For the latest ADMX files for various versions of Windows, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
  
<span data-ttu-id="9df28-p105">Se a configuração descrita nesta seção não pode ser encontrada no GPMC, baixe o ADMX apropriado e copiá-los para o repositório central. Para obter mais informações, consulte [Usando arquivos de ADMX de GPOs edição](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Um repositório central no controlador de é uma pasta com a seguinte convenção de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="9df28-p105">If the setting described in this section cannot be found inside of GPMC, download the appropriate ADMX and copy them to the central store. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="9df28-142">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="9df28-142">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="9df28-p106">Cada que processa seu controlador de domínio deve obter uma pasta separada. O comando a seguir pode ser usado para copiar o arquivo ADMX no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="9df28-p106">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="9df28-145">Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e alternar para editar uma política existente ou criar um novo.</span><span class="sxs-lookup"><span data-stu-id="9df28-145">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="9df28-146">Navegue até \*\* &lt;configuração do usuário do computador&gt;\Administrative Templates\Windows Windows\Console borda\*\*.</span><span class="sxs-lookup"><span data-stu-id="9df28-146">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Windows Components\Microsoft Edge**.</span></span>
    
1. <span data-ttu-id="9df28-147">Clique duas vezes em **definir o mecanismo de pesquisa padrão**, definida como **habilitada**e insira`https://www.bing.com/sa/osd/bfb.xml`</span><span class="sxs-lookup"><span data-stu-id="9df28-147">Double-click **Set default search engine**, set to **Enabled**, and enter `https://www.bing.com/sa/osd/bfb.xml`</span></span>
    
3. <span data-ttu-id="9df28-148">Impor o GPO resultante ao vinculá-lo ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="9df28-148">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
## <a name="google-chrome"></a><span data-ttu-id="9df28-149">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="9df28-149">Google Chrome</span></span>

### <a name="windows-xp-sp2-or-later"></a><span data-ttu-id="9df28-150">Windows XP SP2 ou posterior</span><span class="sxs-lookup"><span data-stu-id="9df28-150">Windows XP SP2 or later</span></span>

<span data-ttu-id="9df28-151">Os usuários não poderão alterar o provedor de pesquisa depois que essa diretiva estiver definida.</span><span class="sxs-lookup"><span data-stu-id="9df28-151">Users won't be able to change the search provider after this policy is set.</span></span>
  
<span data-ttu-id="9df28-p107">Chrome vem com seu próprio conjunto de configurações de diretiva de grupo, que pode ser baixado no formato de um arquivo ADMX do [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202). Se o Windows Vista de sistemas operacionais/Server 2008 ou posterior são usados para gerenciar do GPO para o domínio, o arquivo ADMX fornecido neste pacote cuida das configurações de cromo no Windows XP SP2 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="9df28-p107">Chrome comes with its own set of group policy settings which can be downloaded in the form of an ADMX file from [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202). If operating systems Windows Vista/Server 2008 or later are used to manage GPO's for the domain, the ADMX file provided in this package takes care of Chrome settings on Windows XP SP2 or later.</span></span>
  
<span data-ttu-id="9df28-p108">Copie o arquivo de modelo para um repositório central para arquivos ADMX no controlador de domínio. Para obter mais informações, consulte [Usando arquivos de ADMX de GPOs edição](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Um repositório central no controlador de é uma pasta com a seguinte convenção de nomenclatura:</span><span class="sxs-lookup"><span data-stu-id="9df28-p108">Copy the template file to a central store for ADMX files on the domain controller. For more information, see [Editing Domain-Based GPOs Using ADMX Files](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Central store on the controller is a folder with the following naming convention:</span></span>
  
 <span data-ttu-id="9df28-157">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="9df28-157">**%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="9df28-p109">Cada que processa seu controlador de domínio deve obter uma pasta separada. O comando a seguir pode ser usado para copiar o arquivo ADMX no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="9df28-p109">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="9df28-160">Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e alterne para a edição de qualquer política existente ou criar um novo.</span><span class="sxs-lookup"><span data-stu-id="9df28-160">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
    
2. <span data-ttu-id="9df28-161">Verifique se as seguintes pastas aparecem na seção modelos administrativos de ambas as configuração do computador do usuário: Google Chrome e Google Chrome - configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="9df28-161">Make sure the following folders appear in the Administrative Templates section of both User/Computer Configuration: Google Chrome and Google Chrome - Default Settings.</span></span>
    
  - <span data-ttu-id="9df28-162">As configurações da primeira seção corrigidas e administradores locais não será possível alterá-los no navegador.</span><span class="sxs-lookup"><span data-stu-id="9df28-162">The settings of the first section are fixed and local administrators won't be able to change them in the browser.</span></span>
    
  - <span data-ttu-id="9df28-163">As configurações da seção última das diretivas pode ser alterada pelos usuários nas configurações do navegador.</span><span class="sxs-lookup"><span data-stu-id="9df28-163">The settings of the latter section of policies can be changed by users in the browser settings.</span></span>
    
3. <span data-ttu-id="9df28-164">Navegue até \*\* \<usuário do computador\> provedor de pesquisa de configuração do computador\Modelos Templates\Google Chrome\Default\*\*</span><span class="sxs-lookup"><span data-stu-id="9df28-164">Navigate to **\<Computer/User\> Configuration\Administrative Templates\Google Chrome\Default search provider**</span></span>
    
4. <span data-ttu-id="9df28-165">Clique duas vezes em **Habilitar o provedor de pesquisa padrão**e defini-la como **habilitada**.</span><span class="sxs-lookup"><span data-stu-id="9df28-165">Double-click **Enable the default search provider**, and set it to **Enabled**.</span></span>
    
5. <span data-ttu-id="9df28-166">Clique duas vezes em **Default ícone do provedor de pesquisa**, defini-la como **habilitada**e insira`https://www.bing.com/sa/simg/bb.ico`</span><span class="sxs-lookup"><span data-stu-id="9df28-166">Double-click **Default search provider icon**, set it to **Enabled**, and enter `https://www.bing.com/sa/simg/bb.ico`</span></span>
    
6. <span data-ttu-id="9df28-167">Clique duas vezes em **URL instantânea do provedor de pesquisa padrão**e, em seguida, digite`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="9df28-167">Double-click **Default search provider instant URL**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
7. <span data-ttu-id="9df28-168">Clique duas vezes no **nome do provedor de pesquisa padrão**, defini-la como habilitada e insira a 'Microsoft Search no Bing'</span><span class="sxs-lookup"><span data-stu-id="9df28-168">Double-click **Default search provider name**, set it to Enabled, and enter 'Microsoft Search in Bing'</span></span>
    
8. <span data-ttu-id="9df28-169">Clique duas vezes em **URL de pesquisa do provedor de pesquisa padrão**, defini-la como **habilitada**e insira`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="9df28-169">Double-click **Default search provider search URL**, set it to **Enabled**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
    
9. <span data-ttu-id="9df28-170">Clique duas vezes no **provedor de pesquisa padrão sugerir URL**, defini-la como **habilitada**e insira`https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span><span class="sxs-lookup"><span data-stu-id="9df28-170">Double-click **Default search provider suggest URL**, set it to **Enabled**, and enter `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`</span></span>
    
10. <span data-ttu-id="9df28-171">Impor o GPO resultante ao vinculá-lo ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="9df28-171">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>
    
<span data-ttu-id="9df28-p110">Configurando o mecanismo de pesquisa padrão, você adicionará o recurso de sugestões de pesquisa do Microsoft Search na barra de endereço do navegador. Atualmente, isso suporta apenas os indicadores. Os usuários verão as sugestões de dois indicador principais acima sugestões da web públicos, conforme elas digitam na barra de endereços.</span><span class="sxs-lookup"><span data-stu-id="9df28-p110">Setting the default search engine will add the Microsoft Search search suggestions feature in the browser address bar. Currently, this supports bookmarks only. Users will see the top two bookmark suggestions above public web suggestions as they type in the address bar.</span></span>