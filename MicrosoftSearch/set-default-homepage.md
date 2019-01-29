---
title: Definir a página inicial padrão
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
description: Saiba como configurar o Bing como a página inicial padrão para sua empresa com o Microsoft Search.
ms.openlocfilehash: db0611ebd7f4a8344664825bbb42025f3bb36486
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612486"
---
# <a name="set-default-homepage"></a>Definir a página inicial padrão

Configurar o navegador padrão, o mecanismo de pesquisa padrão e a página inicial padrão ajudarão os usuários Descubra os recursos do Microsoft Search, incentivar o uso de mais e fornecer uma experiência mais suave.
  
Para definir a página inicial padrão para sua organização, siga as etapas abaixo.
  
## <a name="internet-explorer"></a>Internet Explorer

### <a name="internet-explorer-50-or-later"></a>Internet Explorer 5.0 ou posterior

1. Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e alterne para a edição de qualquer política existente ou criar um novo.
    
2. Navegue até **configurações do usuário Configuration\Preferences\Control painel Settings\Internet**.
    
3. Com o botão direito em **Configurações da Internet** e selecione o **Internet Explorer 10**.
    
    > [!NOTE]
    > Você precisa selecionar a opção do Internet Explorer 10 para aplicar as configurações para o Internet Explorer 11, conforme as mesmas configurações se aplicam ao Internet Explorer 11. 
  
4. Configurações que são sublinhadas em vermelho não são definidas na máquina de destino, enquanto as configurações sublinhadas em verde são definidas na máquina de destino. Para alterar o sublinhado, use as teclas de função a seguir:
    
    F5 - habilita todas as configurações na guia atual
    
    F6 - habilitar a configuração selecionada no momento
    
    F7 - desabilitar a configuração selecionada no momento
    
    F8 - desabilita todas as configurações na guia atual
    
5. Pressione **F8** para desabilitar todas as configurações antes de configurar nada. A tela deve ter esta aparência: 
    
    ![Caixa de diálogo Propriedades do Internet Explorer 10](media/2fd55755-5007-4e33-a795-c42ce2fcef4a.jpg)
  
6. Pressione a **tecla F6** na configuração da Home page e insira`https://www.bing.com/business?form=BFBSPR`
    
7. Impor o GPO resultante ao vinculá-lo ao domínio apropriado.
    
> [!NOTE]
> Os usuários ainda podem alterar a página inicial após essa diretiva estiver definida. 
  
## <a name="microsoft-edge"></a>Microsoft Edge

### <a name="windows-10-version-1511-or-later"></a>Windows 10, versão 1511 ou posterior

1. Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e alterne para a edição de qualquer política existente ou criar um novo.
    
2. Navegue até a **borda de Windows\Console Administrativos\Componentes administrativas**
    
1. Clique duas vezes em **Configurar Start pages**, defini-la como **habilitada**e insira`https://www.bing.com/business`
    
3. Impor o GPO resultante ao vinculá-lo ao domínio apropriado.
    
> [!CAUTION]
> Os usuários não poderão alterar o provedor de pesquisa depois que essa diretiva estiver definida. 
  
## <a name="google-chrome"></a>Google Chrome

### <a name="windows-xp-sp2-or-later"></a>Windows XP SP2 ou posterior

O artigo de suporte do Windows no gerenciamento de arquivos ADMX e os arquivos ADMX mais recentes para diferentes versões do Windows pode ser encontrado [no suporte da Microsoft](https://support.microsoft.com/en-us/help/3087759/how-to-create-and-manage-the-central-store-for-group-policy-administra).

Você também precisará o arquivo de diretiva mais recente do Google, que pode ser encontrado na [Ajuda do Google Chrome Enterprise](https://support.google.com/chrome/a/answer/187202).
  
Se as configurações descritas nesta seção não podem ser encontradas no GPMC, baixe o ADMX apropriado e copiá-los para o [repositório central](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-vista/cc748955%28v%3dws.10%29). Um repositório central no controlador de é uma pasta com a seguinte convenção de nomenclatura:
  
 **%systemroot%\sysvol\\<domain\>\policies\PolicyDefinitions**
  
Cada domínio seus identificadores de controlador devem obter uma pasta separada. O comando a seguir pode ser usado para copiar o arquivo ADMX no prompt de comando:
  
 `Copy <path_to_ADMX.ADMX> %systemroot%\sysvol\<domain>\policies\PolicyDefinitions`
  
1. Abra o Console de gerenciamento de diretiva de grupo (GPMC. msc) e alterne para a edição de qualquer política existente ou criar um novo.
    
2. Verifique se as seguintes pastas aparecem na seção **Modelos administrativos** de ambas as *Configuração do computador do usuário*: Google Chrome e Google Chrome - Default Settings (os usuários podem substituir).
    
   - As configurações da primeira seção corrigidas e o administrador local não será possível alterá-los.
    
   - As configurações da seção última das diretivas podem ser alteradas por usuários em suas configurações do navegador. Você deve decidir se os usuários podem substituir sua configuração padrão. Nas etapas a seguir, altere na configuração na pasta correspondente para suas necessidades e a política da organização. As etapas a seguir usam o Google Chrome - configurações padrão como o padrão.
    
3. Navegue até ** &lt;configuração do usuário do computador&gt;\Administrative Templates\Google Chrome - página de Settings\Home padrão**.
    
4. Clique duas vezes em **Nova página de guia uso como home page**e defina-o como **habilitada**.
    
5. Navegue até ** &lt;configuração do usuário do computador&gt;\Administrative Templates\Google Chrome - página da guia Settings\New padrão**.
    
6. Clique duas vezes em **Configure a URL da página nova guia**, defini-la como **habilitada**e insira`https://www.bing.com/business?form=BFBSPR`
    
7. Impor o GPO resultante ao vinculá-lo ao domínio apropriado.
    
Os usuários poderão alterar a home page, depois que essa diretiva estiver definida.