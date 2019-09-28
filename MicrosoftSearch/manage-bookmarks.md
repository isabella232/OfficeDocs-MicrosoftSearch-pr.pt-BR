---
title: Gerenciar indicadores
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.date: 05/30/2019
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Criar e atualizar marcadores e maneiras de editar em massa resultados de indicadores para o Microsoft Search
ms.openlocfilehash: 02b9bfecd97210ba8cd5b46bf3bc108bf66b6f01
ms.sourcegitcommit: 3da22a2e09830672ebf199e05a32fa89b75c083b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288968"
---
# <a name="manage-bookmarks"></a>Gerenciar indicadores

Você pode criar um indicador em apenas algumas etapas. Cada indicador inclui um título, uma URL e um conjunto de palavras-chave que o acionam. Um indicador pode ter várias palavras-chave e vários indicadores podem compartilhar a mesma palavra-chave, mas a palavra-chave reservada não pode ser compartilhada. Quando um indicador é criado ou modificado, o índice de pesquisa é atualizado imediatamente e o indicador fica disponível para os usuários imediatamente.

Se sua organização promoveu os resultados configurados no SharePoint, você pode importar os resultados promovidos para a **pesquisa da Microsoft** e disponibilizar o conteúdo importado para seus usuários. Essa é uma maneira fácil de preencher rapidamente os resultados da pesquisa assim que você configurar a **Pesquisa da Microsoft** e torná-la mais eficiente para os usuários. Recomendamos que você use os resultados promovidos do SharePoint como referência para entender como nomear e criar resultados de pesquisa relevantes. 

## <a name="add-or-edit-a-single-bookmark"></a>Adicionar ou editar um único indicador
1. Vá para o **centro de administração do Microsoft 365**.
1. No painel de navegação, vá para **Configurações** e selecione **Pesquisa da Microsoft**.
Por padrão, a guia **Indicadores** se encontra selecionada.
1. Para adicionar um indicador, selecione **Adicionar novo**. Para editar um indicador, selecione o indicador na lista de indicador relevante. 
1. À medida que você adiciona ou edita as informações, a visualização é atualizada automaticamente.
1. Salve suas alterações.

## <a name="add-or-edit-bookmark-using-browser-extensions"></a>Adicionar ou editar indicador usando extensões de navegador
Os administradores de pesquisa podem criar conteúdo de pesquisa facilmente usando extensões de navegador. Instale a extensão de navegador e, em seguida, vá para o site para o qual você deseja adicionar um indicador e adicione o indicador.

Atualmente, as extensões do navegador estão disponíveis para o Edge e o Chrome. 
- Para baixar a extensão do Edge, vá para a [Loja da Microsoft](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) e baixe o aplicativo.
- Para baixar a extensão do Chrome, acesse a [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) e faça o download do aplicativo.

## <a name="bulk-add-or-edit-bookmarks"></a>Adicionar ou editar indicadores em massa
O administrador de pesquisa pode usar os recursos Importar ou Exportar para criar ou editar indicadores em massa. Esse é um recurso muito útil quando um administrador deseja adicionar ou editar um grande número de indicadores. 

Use o recurso de importação/exportação para:
- Adicionar indicadores em massa - Adicione detalhes no arquivo de modelo de indicador e, em seguida, importe-o.
- Edição em massa de indicadores - Exporte os indicadores para um arquivo .csv, edite os detalhes de indicador no arquivo .csv exportado e, em seguida, importe o arquivo .csv atualizado.
- Importar sites promovidos do SharePoint.
- Indicadores de backup - Exportar indicadores para um arquivo .csv.

Para importar ou exportar indicadores:
1. No canto superior direito da guia **Indicadores**, selecione **Importar**. Selecione **Exportar** para baixar todos os indicadores existentes em um arquivo .csv.
1. No painel direito, escolha a opção de importar usando um arquivo .csv ou do SharePoint.
Faça o download do arquivo de modelo para obter uma lista dos campos e detalhes necessários. 
1. Adicione ou edite os detalhes do indicador no arquivo de modelo e salve-o no seu computador. 
1. No painel **Importar indicadores**, selecione **Procurar** e, em seguida, selecione o arquivo .csv que você deseja importar.
1. Selecione **Importar**.

Aqui estão alguns pontos importantes a serem observados em relação ao arquivo de modelo:
- Nunca edite os dados nesses campos: *Id*, *Última modificação* e *Última modificação por*
- Se você incluir o *Id* de um indicador existente, ele será substituído pelas informações no arquivo de importação.
- Se houver um indicador existente com o mesmo título ou URL, o indicador será atualizado com informações no arquivo de importação.
- Nem todos os campos no arquivo de modelo são obrigatórios, e os campos obrigatórios variam dependendo do estado do indicador.
- Com base no campo *Estado*, os indicadores serão salvos como rascunho, sugerido ou programado, ou serão publicados automaticamente.
- Para organizações com vários locatários, você pode exportar seus indicadores de um locatário e importá-lo para outro. Mas você deve remover os dados na coluna *Id* antes de importar.

### <a name="prevent-import-errors"></a>Evite erros de importação
Você receberá um erro se algum dado necessário estiver faltando ou for inválido, e um arquivo de log será gerado com mais informações sobre as linhas e colunas a serem corrigidas. Faça as edições necessárias e tente importar o arquivo novamente. Você não pode importar ou salvar nenhum indicador até que todos os erros sejam resolvidos.

Para evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente e:
- Que ele inclua a linha de cabeçalho e todas as colunas que estavam no modelo de importação
- Que a ordem das colunas seja igual ao modelo de importação
- Todas as colunas têm valores, exceto as três que podem estar vazias: *Id*, *Última modificação* e *Última modificação por* 
- A coluna *Estado* não está vazia, pois essa informação é necessária

## <a name="powerapps"></a>PowerApps
Ajude seus usuários a concluir tarefas, como inserir período de férias ou informar despesas, adicionando PowerApps existentes aos seus indicadores. 

### <a name="what-are-powerapps"></a>O que são PowerApps?
PowerApps é um serviço que permite criar aplicativos de negócios que são executados em um navegador, telefone ou tablet sem necessidade de nenhuma experiência de codificação. PowerApps funcionam em qualquer navegador e em qualquer dispositivo, e leva menos de um minuto para adicioná-los. Para mais informações sobre PowerApps, consulte:
- 
  [Aprendizagem Orientada](https://docs.microsoft.com/learn/browse/?products=powerapps)
- [Documentação](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [Página inicial do PowerApps](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Adicionar um PowerApp a um indicador
1. Encontre o [ID do aplicativo para o PowerApp](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que você deseja adicionar.
1. Faça logon e vá para o **centro de administração do Microsoft 365**.
1. No painel de navegação, vá para **Configurações** e selecione **Pesquisa da Microsoft**.
1. Adicione um indicador ou encontre um indicador existente ao qual você deseja adicionar um **PowerApp**.
1. Em **Configurações de indicadores**, selecione **Power App** e, em seguida, **Adicionar um Power App**.
1. Insira ou cole o **ID do aplicativo**.
    A altura e a largura são ajustadas automaticamente. Os indicadores são compatíveis com orientações tipo retrato e paisagem; porém, no momento, o tamanho não pode ser alterado. A visualização do indicador mostra um PowerApp totalmente funcional para facilitar o teste.
1. Selecione **Publicar** ou **Salvar em Rascunhos**.
