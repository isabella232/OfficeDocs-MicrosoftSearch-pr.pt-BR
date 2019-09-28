---
title: Definir mecanismo de pesquisa padrão
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
ms.assetid: ee40010e-5d7f-4ba8-a3f8-d240dab3af6d
ROBOTS: NOINDEX
description: Saiba como configurar o Bing como o mecanismo de pesquisa padrão da sua empresa usando a Pesquisa da Microsoft.
ms.openlocfilehash: 7c7ec8be726f2ac12a0e07f3d70c4b6515366bf3
ms.sourcegitcommit: 3da22a2e09830672ebf199e05a32fa89b75c083b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37289014"
---
# <a name="make-bing-the-default-search-engine"></a>Definir o Bing como mecanismo de pesquisa padrão
  
Este artigo explica como tornar o Bing o mecanismo de pesquisa padrão para o Microsoft Edge, Google Chrome e Internet Explorer. 
  
## <a name="microsoft-edge-on-windows-10-version-1703-or-later"></a>Microsoft Edge no Windows 10, Versão 1703 ou posterior

Embora você defina o Bing como mecanismo de pesquisa padrão, o Microsoft Edge permite que os usuários alterem as configurações para usar um mecanismo de pesquisa diferente.
  
Para obter os arquivos ADMX mais recentes para várias versões do Windows, confira [Como criar e gerenciar um Repositório central para modelos administrativos de política de grupo do Windows](https://support.microsoft.com/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).
  
Se a configuração descrita nesta seção não for encontrada dentro do GPMC, baixe o ADMX apropriado e o copie para o repositório central. Para saber mais, confira [Editar GPOs baseados em domínio usando arquivos ADMX](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). O Repositório central no controlador é uma pasta com a seguinte convenção de nomenclatura:
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
Cada domínio processado pelo controlador deve ter uma pasta separada. O comando a seguir pode ser usado para copiar o arquivo ADMX usando o prompt de comando:
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e a opção para editar uma política existente ou criar uma nova.
    
2. Navegue até **&lt;Computador\Configuração do usuário&gt;\Administrativos\Modelos\Componentes do Windows\Microsoft Edge**.
    
1. Clique duas vezes em **Definir mecanismo de pesquisa padrão**, defina como **Habilitado** e insira `https://www.bing.com/sa/osd/bfb.xml`
    
3. Aplique o GPO resultante vinculando-o ao domínio apropriado.


## <a name="google-chrome-on-windows-xp-sp2-or-later"></a>Google Chrome no Windows XP SP2 ou posterior

Os usuários não poderão alternar o mecanismo de pesquisa padrão após a definição dessa política.
  
O Chrome vem com seu próprio conjunto de configurações de políticas de grupo que pode ser baixado na forma de um arquivo ADMX em [Ajuda do Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202). Se forem usados os sistemas operacionais Windows Vista/Server 2008 ou posteriores para gerenciar o GPO do domínio, o arquivo ADMX incluído neste pacote cuida das configurações do Chrome no Windows XP SP2 ou posterior.
  
Copie o arquivo de modelo em um repositório central para arquivos ADMX no controlador de domínio. Para saber mais, confira [Editando GPOs baseados em domínio usando arquivos ADMX](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). O repositório central no controlador é uma pasta com a seguinte convenção de nomenclatura:
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
Cada domínio processado pelo controlador deve ter uma pasta separada. O comando a seguir pode ser usado para copiar o arquivo ADMX usando o prompt de comando:
  
 `Copy <path_to_Chrome.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e alterne para editar uma política existente ou criar uma nova.
    
2. Verifique se as seguintes pastas são exibidas na seção Modelos Administrativos da Configuração do Computador e da Configuração do Usuário: Google Chrome e Configurações Padrão do Google Chrome.
    
  - As configurações da primeira seção são permanentes e os administradores locais não podem alterá-las no navegador.
    
  - As configurações da última seção das políticas podem ser alteradas pelos usuários nas configurações do navegador.
    
3. Navegue até **\<Computador/Usuário\> Configuração\Modelos Administrativos\Google Chrome\Provedor de Pesquisa Padrão**
    
4. Clique duas vezes em **Habilitar o provedor de pesquisa padrão** e defina como **Habilitado**.
    
5. Clique duas vezes em **Ícone do provedor de pesquisa padrão**, defina como **Habilitado** e insira `https://www.bing.com/sa/simg/bb.ico`
    
6. Clique duas vezes na **URL instantânea do provedor de pesquisa padrão** e insira `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
7. Clique duas vezes no **Nome do provedor de pesquisa padrão**, defina como Ativado e insira "Pesquisa da Microsoft no Bing"
    
8. Clique duas vezes na **URL de pesquisa do provedor pesquisa padrão **, defina como **Habilitado** e insira `https://www.bing.com/business/search?q={searchTerms}&amp;form=BFBSPR`
    
9. Clique duas vezes na **URL de sugestão do provedor pesquisa padrão **, defina como **Habilitado** e insira `https://business.bing.com/api/v2/browser/suggest?q={searchTerms}&amp;form=BFBSPA`
    
10. Aplique o GPO resultante ao vinculá-lo ao domínio apropriado.
    
Configure o mecanismo de pesquisa padrão para adicionar o recurso de sugestões da Pesquisa da Microsoft na barra de endereços do navegador. Atualmente há suporte apenas para indicadores. Os usuários verão as duas principais sugestões de indicadores acima das sugestões da web pública conforme digitam na barra de endereço.

## <a name="internet-explorer-11-or-later"></a>Internet Explorer 11 ou posterior

Os usuários poderão alterar o provedor de pesquisa após a definição dessa política.
  
### <a name="step-1-configure-the-local-machine-that-will-be-used-to-set-the-gpo"></a>ETAPA 1. Configure o computador local que será usado para configurar o GPO

Cole o texto a seguir em um arquivo reg (\*.reg).
  
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
  
Clique duas vezes no arquivo criado e siga as etapas para importar o arquivo. Uma importação bem-sucedida deve resultar na seguinte caixa de diálogo:
  
![Mensagem de importação bem-sucedida do Editor do registro](media/ea3686b9-f6d7-481e-9a0d-2c96891bc501.png)
  
### <a name="step-2-open-the-group-policy-management-console-gpmcmsc-and-switch-to-editing-an-existing-policy-or-creating-a-new-one"></a>ETAPA 2. Abra o Console de Gerenciamento de Política de Grupo (gpmc.msc) e alterne para editar uma política existente ou criar uma nova.

1. Navegue até **Usuário Configuração\Políticas\Preferências\Configurações do Windows**.
    
2. Clique com botão direito em **Registro\Novo** e selecione **Assistente do registro**. Na janela do Navegador do registro, selecione **Computador local** e clique em **Próximo**.
    
3. Navegue até **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\SearchScopes**.
    
4. Nesta chave, certifique-se de selecionar DefaultScope.
    
    ![Navegador de registro com DefaultScope selecionado](media/ec5a450d-0cba-4e9c-acba-1a09e8e90bad.png)
  
5. Marque todas as subchaves com a GUID da Pesquisa da Microsoft no Bing e todos os valores na chave, exceto qualquer caminho ao perfil do usuário. Role para baixo para escolher outros itens.
    
    ![Navegador de registro com outros valores selecionados](media/7eef7690-8bc5-46cf-9cd8-bd134fc77a02.png)
  
6. Clique em Concluir para finalizar essa configuração.
    
### <a name="step-3-set-up-user-preferences-to-help-eliminate-a-warning-the-user-may-get-when-defaultscope-search-is-enforced"></a>ETAPA 3. Configurar as Preferências do usuário para ajudar a eliminar o aviso que o usuário pode receber quando a pesquisa DefaultScope for aplicada

Este aviso é projetado e avisa os usuários que um programa está tentando modificar suas configurações.
  
1. Dentro do mesmo GPO, clique com o botão direito do mouse em **Registro\Novo** e selecione **Assistente do Registro**.
    
2. Navegue até **HKEY_CURRENT_USER\SOFTWARE\Microsoft\Internet Explorer\User Preferences**.
    
3. Selecione a chave **User Preference**.
    
4. Clique em **Concluir**.
    
5. Clique no objeto recém-criado. No painel do lado direito, clique duas vezes no objeto Preferências do usuário, altere a **Ação** para **Excluir e salvar**.
1. Aplique o GPO resultante vinculando-o ao domínio apropriado.