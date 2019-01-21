---
title: Mecanismo de pesquisa do conjunto padrão
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
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
description: Saiba como configurar o Bing como o mecanismo de pesquisa padrão da sua empresa usar o Microsoft Search.
ms.openlocfilehash: 1102c4c58b1e46e450276430a1e79b34964b4ad4
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378411"
---
# <a name="set-default-search-engine"></a>Mecanismo de pesquisa do conjunto padrão

Configurar o navegador padrão, o mecanismo de pesquisa padrão e a página inicial padrão ajudarão os usuários Descubra os recursos do Microsoft Search, incentivar o uso de mais e fornecer uma experiência mais suave.
  
Para definir o mecanismo de pesquisa padrão para sua organização, siga as etapas abaixo.
  
## <a name="internet-explorer"></a>Internet Explorer

### <a name="internet-explorer-11"></a>Internet Explorer 11

Os usuários poderão alterar o provedor de pesquisa depois que essa diretiva estiver definida.
  
#### <a name="1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a>1. configure a máquina local que será usada para definir o GPO

Cole o seguinte texto em um registro (\*. reg) arquivos.
  
Editor do Registro do Windows Versão 5.00
  
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
  
Duas vezes no arquivo criado e siga as etapas para importar o arquivo. A importação bem-sucedida deve resultar na caixa de diálogo seguinte:
  
![Mensagem de importação bem-sucedida do Editor do registro](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
#### <a name="2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a>2. Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e vá para editar uma política existente ou criar um novo

1. Navegue até **as configurações do usuário Configuration\Policies\Preferences\Windows**.
    
2. Com o botão direito em **Registry\New** e selecione **Assistente do registro**. Da janela do navegador do registro, selecione o **Computador Local** e clique em **Avançar**.
    
3. Navegue até **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.
    
4. Dessa chave, certifique-se de selecionar DefaultScope.
    
    ![Navegador de registro com DefaultScope selecionado](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. Verifique se todas as chaves de sub, que contém o GUID do Microsoft Search no Bing e cada valor na chave exceto qualquer caminho para os perfis de usuário. Role para baixo para selecionar outros itens.
    
    ![Navegador de registro com valores adicionais selecionados](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. Clique em Concluir para completar esta configuração.
    
#### <a name="3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a>3. configurar as preferências de usuário para ajudar a eliminar um aviso que o usuário pode fazer quando DefaultScope pesquisa é imposta

Esse aviso é por design e usuários de um programa tentando modificar suas configurações de alertas.
  
1. Dentro do mesmo GPO, clique com o botão direito em **Registry\New** e selecione **Assistente do registro**.
    
2. Navegue até **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User preferências**.
    
3. Selecione a chave de **Preferência do usuário** .
    
4. Clique em **Concluir**.
    
5. Clique no objeto recém-criado. No painel do lado direito, clique duas vezes no objeto preferências do usuário, altere a **ação** **Excluir e salvar**.
    
Impor o GPO resultante ao vinculá-lo ao domínio apropriado.
  
## <a name="microsoft-edge"></a>Microsoft Edge

### <a name="windows-10-version-1703-or-later"></a>Windows 10, versão 1703 ou posterior

Os usuários poderão alterar o provedor de pesquisa depois que essa diretiva estiver definida.
  
Os arquivos ADMX mais recentes para diversas versões do Windows, consulte [como criar e gerenciar o repositório Central de modelos administrativos de diretiva de grupo no Windows](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).
  
Se a configuração descrita nesta seção não pode ser encontrada no GPMC, baixe o ADMX apropriado e copiá-los para o repositório central. Para obter mais informações, consulte [Usando arquivos de ADMX de GPOs edição](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Um repositório central no controlador de é uma pasta com a seguinte convenção de nomenclatura:
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
Cada que processa seu controlador de domínio deve obter uma pasta separada. O comando a seguir pode ser usado para copiar o arquivo ADMX no prompt de comando:
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e alternar para editar uma política existente ou criar um novo.
    
2. Navegue até ** &lt;configuração do usuário do computador&gt;\Administrative Templates\Windows Windows\Console borda**.
    
1. Clique duas vezes em **definir o mecanismo de pesquisa padrão**, definida como **habilitada**e insira`https://www.bing.com/sa/osd/bfb.xml`
    
3. Impor o GPO resultante ao vinculá-lo ao domínio apropriado.
    
## <a name="google-chrome"></a>Google Chrome

### <a name="windows-xp-sp2-or-later"></a>Windows XP SP2 ou posterior

Os usuários não poderão alterar o provedor de pesquisa depois que essa diretiva estiver definida.
  
Chrome vem com seu próprio conjunto de configurações de diretiva de grupo, que pode ser baixado no formato de um arquivo ADMX do [Google Chrome Enterprise Help](https://support.google.com/chrome/a/answer/187202). Se o Windows Vista de sistemas operacionais/Server 2008 ou posterior são usados para gerenciar do GPO para o domínio, o arquivo ADMX fornecido neste pacote cuida das configurações de cromo no Windows XP SP2 ou posterior.
  
Copie o arquivo de modelo para um repositório central para arquivos ADMX no controlador de domínio. Para obter mais informações, consulte [Usando arquivos de ADMX de GPOs edição](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Um repositório central no controlador de é uma pasta com a seguinte convenção de nomenclatura:
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
Cada que processa seu controlador de domínio deve obter uma pasta separada. O comando a seguir pode ser usado para copiar o arquivo ADMX no prompt de comando:
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e alterne para a edição de qualquer política existente ou criar um novo.
    
2. Verifique se as seguintes pastas aparecem na seção modelos administrativos de ambas as configuração do computador do usuário: Google Chrome e Google Chrome - configurações padrão.
    
  - As configurações da primeira seção corrigidas e administradores locais não será possível alterá-los no navegador.
    
  - As configurações da seção última das diretivas pode ser alterada pelos usuários nas configurações do navegador.
    
3. Navegue até ** \<usuário do computador\> provedor de pesquisa de configuração do computador\Modelos Templates\Google Chrome\Default**
    
4. Clique duas vezes em **Habilitar o provedor de pesquisa padrão**e defini-la como **habilitada**.
    
5. Clique duas vezes em **Default ícone do provedor de pesquisa**, defini-la como **habilitada**e insira`https://www.bing.com/sa/simg/bb.ico`
    
6. Clique duas vezes em **URL instantânea do provedor de pesquisa padrão**e, em seguida, digite`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
7. Clique duas vezes no **nome do provedor de pesquisa padrão**, defini-la como habilitada e insira a 'Microsoft Search no Bing'
    
8. Clique duas vezes em **URL de pesquisa do provedor de pesquisa padrão**, defini-la como **habilitada**e insira`https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
9. Clique duas vezes no **provedor de pesquisa padrão sugerir URL**, defini-la como **habilitada**e insira`https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`
    
10. Impor o GPO resultante ao vinculá-lo ao domínio apropriado.
    
Configurando o mecanismo de pesquisa padrão, você adicionará o recurso de sugestões de pesquisa do Microsoft Search na barra de endereço do navegador. Atualmente, isso suporta apenas os indicadores. Os usuários verão as sugestões de dois indicador principais acima sugestões da web públicos, conforme elas digitam na barra de endereços.