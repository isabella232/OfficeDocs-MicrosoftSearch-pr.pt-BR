---
title: Gerenciar indicadores
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
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Criar e atualizar marcadores e maneiras de editar em massa resultados de indicadores para o Microsoft Search
ms.openlocfilehash: 64e430309ef1969ab804e8d757b987332f0a6006
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996099"
---
# <a name="manage-bookmarks"></a>Gerenciar indicadores

Você pode criar um indicador em apenas algumas etapas. Cada indicador inclui um título, uma URL e um conjunto de palavras-chave que o acionam. Um indicador pode ter várias palavras-chave e vários indicadores podem compartilhar a mesma palavra-chave, mas a palavra-chave reservada não pode ser compartilhada. Quando um indicador é criado ou modificado, o índice de pesquisa é atualizado imediatamente e o indicador fica disponível para os usuários imediatamente.

Se sua organização promoveu os resultados configurados no SharePoint, você pode importar os resultados promovidos para a **pesquisa da Microsoft** e disponibilizar o conteúdo importado para seus usuários. Essa é uma maneira fácil de preencher rapidamente os resultados da pesquisa assim que você configurar a **Pesquisa da Microsoft** e torná-la mais eficiente para os usuários. Recomendamos que você use os resultados promovidos do SharePoint como referência para entender como nomear e criar resultados de pesquisa relevantes.

## <a name="add-or-edit-a-single-bookmark"></a>Adicionar ou editar um único indicador

1. Vá para o **centro de administração do Microsoft 365**.
1. No painel de navegação, vá para **configurações**  >  indicadores de respostas da**pesquisa da Microsoft**  >  **Answers**  >  [**Bookmarks**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks).
1. Para adicionar um indicador, selecione **Adicionar novo**.
Para editar um indicador, selecione o indicador na lista de indicador relevante.
1. À medida que você adiciona ou edita as informações, a visualização é atualizada automaticamente.
1. Salve suas alterações.

## <a name="add-or-edit-bookmark-using-browser-extensions"></a>Adicionar ou editar indicador usando extensões de navegador

Os administradores de pesquisa podem criar conteúdo de pesquisa facilmente usando extensões de navegador. Instale a extensão de navegador e, em seguida, vá para o site para o qual você deseja adicionar um indicador e adicione o indicador.

Atualmente, as extensões do navegador estão disponíveis para o Edge e o Chrome.

- Para baixar extensões de borda, vá para a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) e baixe o aplicativo.
- Para baixar as extensões Chrome, vá para o [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) e baixe o aplicativo.

## <a name="bulk-add-or-edit-bookmarks"></a>Adicionar ou editar indicadores em massa

O administrador de pesquisa pode usar os recursos Importar ou Exportar para criar ou editar indicadores em massa. Esse é um recurso muito útil quando um administrador deseja adicionar ou editar um grande número de indicadores.

Use o recurso de importação/exportação para:

- Adicionar indicadores em massa - Adicione detalhes no arquivo de modelo de indicador e, em seguida, importe-o.
- Edição em massa de indicadores - Exporte os indicadores para um arquivo .csv, edite os detalhes de indicador no arquivo .csv exportado e, em seguida, importe o arquivo .csv atualizado.
- Importar sites promovidos do SharePoint.
- Indicadores de backup - Exportar indicadores para um arquivo .csv.

Para importar ou exportar indicadores:

1. No canto superior direito da guia **Indicadores**, selecione **Importar**.
Selecione **Exportar** para baixar todos os indicadores existentes em um arquivo .csv.
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
- Para parceiros que gerenciam várias organizações, você pode exportar seus indicadores de uma organização e importá-los para outro. Mas você deve remover os dados na coluna *Id* antes de importar.

### <a name="prevent-import-errors"></a>Evite erros de importação

Você receberá um erro se algum dado necessário estiver faltando ou for inválido, e um arquivo de log será gerado com mais informações sobre as linhas e colunas a serem corrigidas. Faça as edições necessárias e tente importar o arquivo novamente. Você não pode importar ou salvar nenhum indicador até que todos os erros sejam resolvidos.

Para evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente e:

- Que ele inclua a linha de cabeçalho e todas as colunas que estavam no modelo de importação
- Que a ordem das colunas seja igual ao modelo de importação
- Todas as colunas têm valores, exceto as três que podem estar vazias: *Id*, *Última modificação* e *Última modificação por*
- A coluna *Estado* não está vazia, pois essa informação é necessária

Para evitar erros de duplicação de indicador a indicador, siga estas práticas recomendadas:

- Não use URLS duplicadas para indicadores diferentes. Se uma URL já estiver atribuída a outro indicador e você a adicionar novamente a partir de um arquivo de importação, você receberá um erro. Isso também se aplica a URLs duplicadas para outros tipos de respostas.
- Use a coluna *ID do indicador* ao atualizar indicadores existentes. Você pode atualizar qualquer outra propriedade de um indicador existente, como palavra-chave ou descrição, mas você deve certificar-se de que a *ID do indicador* está na coluna apropriada do arquivo de importação. Se a *ID do indicador* estiver presente, o serviço não o considerará como nova adição e não será processado como um erro.

## <a name="power-apps"></a>Aplicativos de energia

Ajude seus usuários a concluir tarefas, como inserir período de férias ou informar despesas, adicionando PowerApps existentes aos seus indicadores.

### <a name="power-apps-explained"></a>Aplicativos de energia explicados

O aplicativos de energia é um serviço que permite criar aplicativos de negócios que são executados em um navegador ou em um telefone ou Tablet sem nenhuma experiência de codificação necessária. PowerApps funcionam em qualquer navegador e em qualquer dispositivo, e leva menos de um minuto para adicioná-los. Para mais informações sobre PowerApps, consulte:

- [Aprendizagem Orientada](https://docs.microsoft.com/learn/browse/?products=powerapps)
- [Documentação](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [Início de aplicativos de energia](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-power-app-to-a-bookmark"></a>Adicionar um aplicativo de alimentação a um indicador

1. Encontre a [ID do aplicativo para o aplicativo de energia](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que você deseja adicionar.
1. Entre no centro de [**Administração do Microsoft 365**](https://admin.microsoft.com).
1. No painel de navegação, vá para **configurações**  >  indicadores de respostas da**pesquisa da Microsoft**  >  **Answers**  >  [**Bookmarks**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks).
1. Adicione um indicador ou encontre um indicador existente ao qual você deseja adicionar um **PowerApp**.
1. Em **Configurações de indicadores**, selecione **Power App** e, em seguida, **Adicionar um Power App**.
1. Insira ou cole o **ID do aplicativo**.
    A altura e a largura são ajustadas automaticamente. Os indicadores são compatíveis com orientações tipo retrato e paisagem; porém, no momento, o tamanho não pode ser alterado. A visualização do indicador mostra um PowerApp totalmente funcional para facilitar o teste.
1. Selecione **Publicar** ou **Salvar em Rascunhos**.
