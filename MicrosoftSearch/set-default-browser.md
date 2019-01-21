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
# <a name="set-default-browser"></a>Navegador do conjunto padrão

Configurar o navegador padrão, o mecanismo de pesquisa padrão e a página inicial padrão ajudarão os usuários Descubra os recursos do Microsoft Search, incentivar o uso de mais e fornecer uma experiência mais suave.
  
Para definir o navegador padrão para sua organização, siga as etapas abaixo.
  
## <a name="windows-8-and-above"></a>Windows 8 e acima

Para definir o Internet Explorer ou Microsoft Edge como o navegador padrão, siga estas etapas:
  
### <a name="create-default-associations-file"></a>Criar o arquivo de associações padrão

1. Abra um console administrativo do PowerShell.
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
Estas etapas tente e criar o arquivo de associações padrão na pasta SYSVOL do controlador de domínio.
  
### <a name="add-or-edit-the-default-associations-file"></a>Adicionar ou editar o arquivo de associações padrão

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. Editar as seguintes entradas (. htm,. HTML, http, https) e remover outras entradas se eles não sejam necessários.
    
  - **Microsoft Edge**
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - **Internet Explorer**
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e alterne para a edição de qualquer política existente ou criar um novo.
    
1. Navegue até o **computador \ Modelos Administrativos\Componentes do Components\File Explorer**
    
2. Clique duas vezes em **definir um arquivo de configuração de associações padrão**, defini-la como **habilitada**e digite o caminho para AppAssoc.xml (por exemplo, %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)
    
4. Impor o GPO resultante ao vinculá-lo ao domínio apropriado.
    
Os usuários poderão alterar o navegador após essa diretiva estiver definida.
  
## <a name="windows-7"></a>Windows 7

1. Configure a máquina local que será usada para definir o GPO.
    
1. Abra **Programas padrão do controle Panel\Programs\Default Programs\Set** e defina o Internet Explorer como padrão. 
    
2. Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e alterne para a edição de qualquer política existente ou criar um novo.
    
1. Navegue até ** \<usuário do computador\> Configuration\Policies\Preferences\Windows configurações**.
    
2. Com o botão direito em **Registry\New** e selecione **Assistente do registro**.
    
3. Da janela do navegador do registro, selecione o **Computador Local** e clique em **Avançar**.
    
4. Navegue até **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selecione o valor ProgId. Verifique se que o valor parecido com aquele abaixo: 
    
    ![Selecione o valor ProgID em Editar cadeia de caracteres](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. Navegue até **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selecione o valor ProgId. Certifique-se que o valor parecido com aquele abaixo: 
    
    ![Selecione ProgId para HTTPS na cadeia de caracteres de edição](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. Impor o GPO resultante ao vinculá-lo ao domínio apropriado.
    
Os usuários poderão alterar o navegador após essa diretiva estiver definida.