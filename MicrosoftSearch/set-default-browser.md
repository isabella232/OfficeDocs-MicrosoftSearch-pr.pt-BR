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
description: Saiba como configurar um navegador padrão para a empresa com a Pesquisa da Microsoft.
ms.openlocfilehash: 160dbbef9981127b74c51f54f86428667ecd4471
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508984"
---
# <a name="set-default-browser"></a>Definir o navegador padrão

Configurar o navegador, o mecanismo de pesquisa e a home page padrão ajuda os usuários a descobrir os recursos, promove o uso e proporciona uma experiência aprimorada da Pesquisa da Microsoft.
  
Para definir o navegador padrão da organização, faça os procedimentos abaixo.
  
## <a name="windows-8-and-above"></a>Windows 8 e versão posterior

Para configurar o Microsoft Edge ou Internet Explorer como navegador padrão, faça o seguinte:
  
### <a name="create-default-associations-file"></a>Criar um arquivo de associações padrão

1. Abra um console administrativo do PowerShell.
    
2.  `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
    
3.  `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
    
4.  `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
Essas etapas se destinam a testar e criar o arquivo de associações padrão na pasta SYSVOL do controlador de domínio.
  
### <a name="add-or-edit-the-default-associations-file"></a>Adicionar ou editar um arquivo de associações padrão

1. `Notepad "$SettingsPath\AppAssoc.xml"`
    
2. Edite as seguintes entradas (.htm, .html, http, https) e remova as outras entradas, caso elas não sejam necessárias.
    
  - **Microsoft Edge**
    
     `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
  
     `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - **Internet Explorer**
    
     `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
  
     `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`
    
3. Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a opção para editar uma política existente ou criar uma nova.
    
1. Navegue para **Configuração do Computador\Modelos Administrativos\Componentes do Windows\Explorador de Arquivos**
    
2. Clique duas vezes em **Definir um arquivo de configuração de associações padrão**, defina-o como **habilitado** e insira o caminho para AppAssoc.xml (por exemplo %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml)
    
4. Aplique o GPO resultante vinculando-o ao domínio apropriado.
    
Os usuários poderão alterar o navegador, após a definição dessa política.
  
## <a name="windows-7"></a>Windows 7

1. Configure o computador local que será usado para configurar o GPO.
    
1. Abra **Painel de Controle\Programas\Programas Padrão\Definir Programas Padrão** e defina o Internet Explorer como padrão. 
    
2. Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a opção para editar uma política existente ou criar uma nova.
    
1. Navegue para **\<Computador/Usuário\> Configuração\Políticas\Preferências\Configurações do Windows**.
    
2. Clique com o botão direito do mouse em **Registro/Novo** e selecione **Assistente do Registro**.
    
3. Na janela do Navegador do Registro, selecione **Computador local** e clique em **Avançar**.
    
4. Navegue para **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selecione o valor ProgID. Verifique se o valor tem a seguinte aparência, conforme exibido abaixo: 
    
    ![Selecione o valor ProgID em Editar Cadeia de Caracteres](media/f6173dcc-b898-4967-8c40-4b0fe411a92b.png)
  
5. Navegue para **HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell\Associations\UrlAssociations\https** e selecione o valor ProgID. Verifique se o valor tem a seguinte aparência, conforme exibido abaixo: 
    
    ![Selecione a ProgID para HTTPS em Editar Cadeia de Caracteres](media/3519e13b-4fe7-4d15-946c-82fd50fc49bb.png)
  
3. Aplique o GPO resultante vinculando-o ao domínio apropriado.
    
Os usuários poderão alterar o navegador, após a definição dessa política.