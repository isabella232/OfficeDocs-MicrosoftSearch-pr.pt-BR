---
title: Definir o navegador padrão
ms.author: anfowler
author: adefowler
manager: shohara
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
ROBOTS: NOINDEX
description: Defina o navegador padrão para o Microsoft Edge ou o Internet Explorer para os usuários da Pesquisa da Microsoft.
ms.openlocfilehash: ed145a1811aba0b58158ed04dd3bf8dc089a0682
ms.sourcegitcommit: c2c9e66af1038efd2849d578f846680851f9e5d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2019
ms.locfileid: "36639735"
---
# <a name="make-microsoft-edge-the-default-browser"></a>Tornar o Microsoft Edge o navegador padrão
  
Para dar aos usuários a melhor experiência com a Pesquisa da Microsoft, você pode tornar o Microsoft Edge o navegador padrão. Isso só definirá o Microsoft Edge como navegador padrão para usuários em sua organização, usuários individuais ainda poderão selecionar um navegador diferente.
  
  
## <a name="windows-8-and-later"></a>Windows 8 e posteriores

Essas instruções mostram como tornar o Microsoft Edge ou o Internet Explorer como navegador padrão para computadores com Windows 8 ou posterior. Os usuários poderão alterar o navegador, após a definição dessa política.
  
### <a name="step-1-create-the-default-associations-file"></a>ETAPA 1: Criar o arquivo de associações padrão
Crie o arquivo de associações padrão na pasta SYSVOL do controlador de domínio.

1. Abra um console administrativo do PowerShell.
1. `New-Item -Path "\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN" -Type Directory -Name "Settings"`
1. `$SettingsPath="\\$env:USERDOMAIN\SYSVOL\$env:USERDNSDOMAIN\Settings"`
1. `Start-Process Dism.exe -PassThru "/Online /Export-DefaultAppAssociations:$SettingsPath\AppAssoc.xml"`
    
  
### <a name="step-2-add-or-edit-the-default-associations-file"></a>ETAPA 2. Adicionar ou editar um arquivo de associações padrão

1. `Notepad "$SettingsPath\AppAssoc.xml"`
1. Edite as seguintes entradas (.htm, .html, http, https) e remova as outras entradas, caso elas não sejam necessárias.
  - **Microsoft Edge**
    - `<Association Identifier=".htm" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
              
    - `<Association Identifier=".html" ProgId="AppX4hxtad77fbk3jkkeerkrm0ze94wjf3s9" ApplicationName="Microsoft Edge" />`
    - `<Association Identifier="http" ProgId="AppXq0fevzme2pys62n3e0fbqa7peapykr8v" ApplicationName="Microsoft Edge" />`
    
  - **Internet Explorer**
    
    - `<Association Identifier=".htm" ProgId="htmlfile" ApplicationName="Internet Explorer" />`        
    - `<Association Identifier=".html" ProgId="htmlfile" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="http" ProgId="IE.HTTP" ApplicationName="Internet Explorer" />`
    - `<Association Identifier="https" ProgId="IE.HTTPS" ApplicationName="Internet Explorer" />`

### <a name="step-3-edit-the-group-policy"></a>Etapa 3. Editar a Política de Grupo

1. Abra o **Console de Gerenciamento de Política de Grupo** (gpmc.msc) e alterne para editar qualquer política existente ou para criar uma nova.
1. Navegue para **Configuração do Computador/Modelos Administrativos/Componentes do Windows/Explorador de Arquivos**.
1. Clique duas vezes em **Definir um arquivo de configuração de associações padrão**, defina-o como **Habilitado** e insira o caminho para AppAssoc.xml (por exemplo, %USERDOMAIN%\SYSVOL\%USERDNSDOMAIN%\Settings\AppAssoc.xml) Aplique o GPO resultante vinculando-o ao domínio apropriado.

  
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
    
