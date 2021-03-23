---
title: Definir mecanismo de pesquisa padrão
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
description: Saiba como configurar o Bing como o mecanismo de pesquisa padrão da sua empresa usando a Pesquisa da Microsoft.
ms.openlocfilehash: 346bf3bf2da10178a8bd19390920db2d9de2629e
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031751"
---
# <a name="make-bing-the-default-search-engine"></a><span data-ttu-id="48962-103">Definir o Bing como mecanismo de pesquisa padrão</span><span class="sxs-lookup"><span data-stu-id="48962-103">Make Bing the default search engine</span></span>
  
<span data-ttu-id="48962-104">Este artigo explica como tornar o Bing o mecanismo de pesquisa padrão para o Microsoft Edge, Google Chrome e Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="48962-104">This article explains how you can make Bing the default search engine for Microsoft Edge, Google Chrome, and Internet Explorer.</span></span> 
  
## <a name="microsoft-edge-on-windows-10-version-1703-or-later"></a><span data-ttu-id="48962-105">Microsoft Edge no Windows 10, Versão 1703 ou posterior</span><span class="sxs-lookup"><span data-stu-id="48962-105">Microsoft Edge on Windows 10, Version 1703 or later</span></span>

<span data-ttu-id="48962-106">Embora você defina o Bing como mecanismo de pesquisa padrão, o Microsoft Edge permite que os usuários alterem as configurações para usar um mecanismo de pesquisa diferente.</span><span class="sxs-lookup"><span data-stu-id="48962-106">Although you'll set Bing as the default search engine, Microsoft Edge allows users to change their settings to use a different search engine.</span></span>
  
<span data-ttu-id="48962-107">Para obter os arquivos ADMX mais recentes para várias versões do Windows, confira [Como criar e gerenciar um Repositório central para modelos administrativos de política de grupo do Windows](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span><span class="sxs-lookup"><span data-stu-id="48962-107">For the latest ADMX files for various versions of Windows, see [How to create and manage the Central Store for Group Policy Administrative Templates in Windows](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).</span></span>
  
<span data-ttu-id="48962-108">Se a configuração descrita nesta seção não puder ser encontrada dentro do GPMC, baixe o ADMX apropriado e copie-os para o armazenamento central.</span><span class="sxs-lookup"><span data-stu-id="48962-108">If the setting described in this section cannot be found inside of GPMC, download the appropriate ADMX and copy them to the central store.</span></span> <span data-ttu-id="48962-109">Para obter mais informações, [consulte Editing Domain-Based GPOs Using ADMX Files](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29).</span><span class="sxs-lookup"><span data-stu-id="48962-109">For more information, see [Editing Domain-Based GPOs Using ADMX Files](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29).</span></span> <span data-ttu-id="48962-110">O armazenamento central no controlador é uma pasta com a seguinte convenção de nomenização: **%systemroot%\sysvol \\<domínio \> \policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="48962-110">Central store on the controller is a folder with the following naming convention: **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="48962-p102">Cada domínio processado pelo controlador deve ter uma pasta separada. O comando a seguir pode ser usado para copiar o arquivo ADMX usando o prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="48962-p102">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="48962-113">Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a opção para editar uma política existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="48962-113">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one.</span></span>
2. <span data-ttu-id="48962-114">Navegue até **&lt;Computador\Configuração do usuário&gt;\Administrativos\Modelos\Componentes do Windows\Microsoft Edge**.</span><span class="sxs-lookup"><span data-stu-id="48962-114">Navigate to **&lt;Computer/User Configuration&gt;\Administrative Templates\Windows Components\Microsoft Edge**.</span></span>
3. <span data-ttu-id="48962-115">Clique duas vezes em **Definir mecanismo de pesquisa padrão**, defina como **Habilitado** e insira `https://www.bing.com/sa/osd/bfb.xml`</span><span class="sxs-lookup"><span data-stu-id="48962-115">Double-click **Set default search engine**, set to **Enabled**, and enter `https://www.bing.com/sa/osd/bfb.xml`</span></span>
4. <span data-ttu-id="48962-116">Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="48962-116">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>


## <a name="google-chrome-on-windows-10-version-1507-or-later"></a><span data-ttu-id="48962-117">Google Chrome no Windows 10, Versão 1507 ou posterior</span><span class="sxs-lookup"><span data-stu-id="48962-117">Google Chrome on Windows 10, Version 1507 or later</span></span>

<span data-ttu-id="48962-118">Os usuários não poderão alternar o mecanismo de pesquisa padrão após a definição dessa política.</span><span class="sxs-lookup"><span data-stu-id="48962-118">Users won't be able to change the default search engine after this policy is set.</span></span>
  
<span data-ttu-id="48962-119">O Chrome vem com seu próprio conjunto de configurações de política de grupo que podem ser baixadas na forma de um arquivo ADMX da Ajuda [do Google Chrome Enterprise.](https://support.google.com/chrome/a/answer/187202)</span><span class="sxs-lookup"><span data-stu-id="48962-119">Chrome comes with its own set of group policy settings which can be downloaded in the form of an ADMX file from [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202).</span></span>
  
<span data-ttu-id="48962-120">Copie o arquivo de modelo para um armazenamento central para arquivos ADMX no controlador de domínio.</span><span class="sxs-lookup"><span data-stu-id="48962-120">Copy the template file to a central store for ADMX files on the domain controller.</span></span> <span data-ttu-id="48962-121">Para obter mais informações, [consulte Editing Domain-Based GPOs Using ADMX Files](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29).</span><span class="sxs-lookup"><span data-stu-id="48962-121">For more information, see [Editing Domain-Based GPOs Using ADMX Files](/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29).</span></span> <span data-ttu-id="48962-122">O armazenamento central no controlador é uma pasta com a seguinte convenção de nomenização: **%systemroot%\sysvol \\<domínio \> \policies\PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="48962-122">Central store on the controller is a folder with the following naming convention: **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**</span></span>
  
<span data-ttu-id="48962-p104">Cada domínio processado pelo controlador deve ter uma pasta separada. O comando a seguir pode ser usado para copiar o arquivo ADMX usando o prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="48962-p104">Each domain that your controller handles should get a separate folder. The following command can be used to copy the ADMX file from the command prompt:</span></span>
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. <span data-ttu-id="48962-125">Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e alterne para editar uma política existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="48962-125">Open the Group Policy Management Console (gpmc.msc) and switch to editing any existing policy or creating a new one.</span></span>
2. <span data-ttu-id="48962-126">Verifique se as seguintes pastas são exibidas na seção Modelos Administrativos da Configuração do Computador e da Configuração do Usuário: Google Chrome e Configurações Padrão do Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="48962-126">Make sure the following folders appear in the Administrative Templates section of both User/Computer Configuration: Google Chrome and Google Chrome - Default Settings.</span></span>

    - <span data-ttu-id="48962-127">As configurações da primeira seção são permanentes e os administradores locais não podem alterá-las no navegador.</span><span class="sxs-lookup"><span data-stu-id="48962-127">The settings of the first section are fixed and local administrators won't be able to change them in the browser.</span></span>
    - <span data-ttu-id="48962-128">As configurações da última seção das políticas podem ser alteradas pelos usuários nas configurações do navegador.</span><span class="sxs-lookup"><span data-stu-id="48962-128">The settings of the latter section of policies can be changed by users in the browser settings.</span></span>

3. <span data-ttu-id="48962-129">Navegue **\<Computer/User\> até Configuration\Administrative Templates\Google Chrome\Provedor de pesquisa padrão**</span><span class="sxs-lookup"><span data-stu-id="48962-129">Navigate to **\<Computer/User\> Configuration\Administrative Templates\Google Chrome\Default search provider**</span></span>
4. <span data-ttu-id="48962-130">Clique duas vezes em **Habilitar o provedor de pesquisa padrão** e defina como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="48962-130">Double-click **Enable the default search provider**, and set it to **Enabled**.</span></span>
5. <span data-ttu-id="48962-131">Clique duas vezes em **Ícone do provedor de pesquisa padrão**, defina como **Habilitado** e insira `https://www.bing.com/sa/simg/bb.ico`</span><span class="sxs-lookup"><span data-stu-id="48962-131">Double-click **Default search provider icon**, set it to **Enabled**, and enter `https://www.bing.com/sa/simg/bb.ico`</span></span>
6. <span data-ttu-id="48962-132">Clique duas vezes na **URL instantânea do provedor de pesquisa padrão** e insira `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="48962-132">Double-click **Default search provider instant URL**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
7. <span data-ttu-id="48962-133">Clique duas vezes no **Nome do provedor de pesquisa padrão**, defina como Ativado e insira "Pesquisa da Microsoft no Bing"</span><span class="sxs-lookup"><span data-stu-id="48962-133">Double-click **Default search provider name**, set it to Enabled, and enter 'Microsoft Search in Bing'</span></span>
8. <span data-ttu-id="48962-134">Clique duas vezes na **URL de pesquisa do provedor pesquisa padrão**, defina como **Habilitado** e insira `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span><span class="sxs-lookup"><span data-stu-id="48962-134">Double-click **Default search provider search URL**, set it to **Enabled**, and enter `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`</span></span>
9. <span data-ttu-id="48962-135">Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="48962-135">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>

## <a name="internet-explorer-11-or-later"></a><span data-ttu-id="48962-136">Internet Explorer 11 ou posterior</span><span class="sxs-lookup"><span data-stu-id="48962-136">Internet Explorer 11 or later</span></span>

<span data-ttu-id="48962-137">Os usuários poderão alterar o provedor de pesquisa após a definição dessa política.</span><span class="sxs-lookup"><span data-stu-id="48962-137">Users will be able to change the search provider after this policy is set.</span></span>
  
### <a name="step-1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a><span data-ttu-id="48962-138">ETAPA 1.</span><span class="sxs-lookup"><span data-stu-id="48962-138">STEP 1.</span></span> <span data-ttu-id="48962-139">Configure o computador local que será usado para configurar o GPO</span><span class="sxs-lookup"><span data-stu-id="48962-139">Configure the local machine that will be used to set the GPO</span></span>

<span data-ttu-id="48962-140">Cole o texto a seguir em um arquivo reg (\*.reg).</span><span class="sxs-lookup"><span data-stu-id="48962-140">Paste the following text into a reg(\*.reg) file.</span></span>
  
<span data-ttu-id="48962-141">Editor do Registro do Windows Versão 5.00</span><span class="sxs-lookup"><span data-stu-id="48962-141">Windows Registry Editor Version 5.00</span></span>
  
<pre>[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes]
"DefaultScope"="{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}"
[HKEY_CURRENT_USER\Software\Microsoft\Internet Explorer\SearchScopes\{D54CD0C8-C007-4BC4-B2DD-1E4896B8406D}]
"Codepage"=dword:0000fde9
"DisplayName"="Microsoft Search in Bing"
"OSDFileURL"="https://www.bing.com/sa/osd/bfb.xml"
"FaviconURL"="https://www.bing.com/sa/simg/bb.ico"
"URL"="https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR"</pre>
  
<span data-ttu-id="48962-p106">Clique duas vezes no arquivo criado e siga as etapas para importar o arquivo. Uma importação bem-sucedida deve resultar na seguinte caixa de diálogo:</span><span class="sxs-lookup"><span data-stu-id="48962-p106">Double-click the file created and follow the steps to import the file. A successful import should result in the following dialog:</span></span>
  
![Mensagem de importação bem-sucedida do Editor do registro](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
### <a name="step-2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a><span data-ttu-id="48962-145">ETAPA 2.</span><span class="sxs-lookup"><span data-stu-id="48962-145">STEP 2.</span></span> <span data-ttu-id="48962-146">Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e alterne para editar uma política existente ou criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="48962-146">Open the Group Policy Management Console (gpmc.msc) and switch to editing an existing policy or creating a new one</span></span>

1. <span data-ttu-id="48962-147">Navegue até **Usuário Configuração\Políticas\Preferências\Configurações do Windows**.</span><span class="sxs-lookup"><span data-stu-id="48962-147">Navigate to **User Configuration\Policies\Preferences\Windows Settings**.</span></span>
2. <span data-ttu-id="48962-p108">Clique com botão direito em **Registro\Novo** e selecione **Assistente do registro**. Na janela do Navegador do registro, selecione **Computador local** e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="48962-p108">Right-click on **Registry\New** and select **Registry Wizard**. From the Registry Browser window, select **Local Computer** and click **Next**.</span></span>
3. <span data-ttu-id="48962-150">Navegue até **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span><span class="sxs-lookup"><span data-stu-id="48962-150">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.</span></span>
4. <span data-ttu-id="48962-151">Nesta chave, certifique-se de selecionar DefaultScope.</span><span class="sxs-lookup"><span data-stu-id="48962-151">From this key, make sure to select DefaultScope.</span></span>

    ![Navegador de registro com DefaultScope selecionado](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
5. <span data-ttu-id="48962-p109">Marque todas as subchaves com a GUID da Pesquisa da Microsoft no Bing e todos os valores na chave, exceto qualquer caminho ao perfil do usuário. Role para baixo para escolher outros itens.</span><span class="sxs-lookup"><span data-stu-id="48962-p109">Check all sub keys containing the GUID for Microsoft Search in Bing and every value under the key except any path to user profiles. Scroll down to select other items.</span></span>
6. <span data-ttu-id="48962-155">Clique em Concluir para finalizar essa configuração.</span><span class="sxs-lookup"><span data-stu-id="48962-155">Click Finish to complete this configuration.</span></span>

### <a name="step-3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a><span data-ttu-id="48962-156">ETAPA 3.</span><span class="sxs-lookup"><span data-stu-id="48962-156">STEP 3.</span></span> <span data-ttu-id="48962-157">Configurar as Preferências do usuário para ajudar a eliminar o aviso que o usuário pode receber quando a pesquisa DefaultScope for aplicada</span><span class="sxs-lookup"><span data-stu-id="48962-157">Set up User Preferences to help eliminate a warning the user may get when DefaultScope search is enforced</span></span>

<span data-ttu-id="48962-158">Este aviso é projetado e avisa os usuários que um programa está tentando modificar suas configurações.</span><span class="sxs-lookup"><span data-stu-id="48962-158">This warning is by design and alerts users of a program trying to modify their settings.</span></span>
  
1. <span data-ttu-id="48962-159">Dentro do mesmo GPO, clique com o botão direito do mouse em **Registro\Novo** e selecione **Assistente do Registro**.</span><span class="sxs-lookup"><span data-stu-id="48962-159">Within the same GPO, right click on **Registry\New** and select **Registry Wizard**.</span></span>
2. <span data-ttu-id="48962-160">Navegue até **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span><span class="sxs-lookup"><span data-stu-id="48962-160">Navigate to **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.</span></span>
3. <span data-ttu-id="48962-161">Selecione a chave **User Preference**.</span><span class="sxs-lookup"><span data-stu-id="48962-161">Select the **User Preference** key.</span></span>
4. <span data-ttu-id="48962-162">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="48962-162">Click **Finish**.</span></span>
5. <span data-ttu-id="48962-p111">Clique no objeto recém-criado. No painel do lado direito, clique duas vezes no objeto Preferências do usuário, altere a **Ação** para **Excluir e salvar**.</span><span class="sxs-lookup"><span data-stu-id="48962-p111">Click on the newly created object. On the right-side pane double click on the User Preferences object, change the **Action** to **Delete and Save**.</span></span>
6. <span data-ttu-id="48962-165">Aplique o GPO resultante vinculando-o ao domínio apropriado.</span><span class="sxs-lookup"><span data-stu-id="48962-165">Enforce the resultant GPO by linking it to the appropriate domain.</span></span>