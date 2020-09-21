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
ms.openlocfilehash: eb65121b53ab110b91880a65a5146d868f3a7405
ms.sourcegitcommit: d88226f9c3a99540a591dc0a26408bb9960cf39a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/19/2020
ms.locfileid: "48134163"
---
# <a name="manage-bookmarks"></a>Gerenciar indicadores

Você pode criar um indicador em apenas algumas etapas. Cada indicador inclui um título, uma URL e um conjunto de palavras-chave que o acionam. Você também pode adicionar categorias a um indicador que pode ser usado para classificação e filtragem no portal de administração. Um indicador pode ter várias palavras-chave e os indicadores podem compartilhar a mesma palavra-chave, mas a palavra-chave reservada não pode ser compartilhada. Quando um indicador é criado ou modificado, o índice de pesquisa é atualizado imediatamente e o indicador fica disponível para os usuários imediatamente.

Se sua organização configurou resultados promovidos no SharePoint, você pode importar os resultados promovidos para a **pesquisa da Microsoft** e disponibilizar o conteúdo importado para seus usuários. Essa é uma maneira fácil de preencher rapidamente os resultados da pesquisa assim que você configurar a **Pesquisa da Microsoft** e torná-la mais eficiente para os usuários. Recomendamos o uso de resultados promovidos do SharePoint como referência para entender como nomear e criar resultados de pesquisa relevantes.

## <a name="add-or-edit-a-single-bookmark"></a>Adicionar ou editar um único indicador

1. No [centro de administração do Microsoft 365](https://admin.microsoft.com), acesse [**indicadores**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks).
1. Para adicionar um indicador, selecione **Adicionar**.
Para editar um indicador, selecione o indicador na lista de indicador relevante.
1. À medida que você adiciona ou edita as informações, a visualização é atualizada automaticamente.
1. Salve suas alterações.

## <a name="add-or-edit-bookmark-using-browser-extensions"></a>Adicionar ou editar indicador usando extensões de navegador

Os administradores de pesquisa podem criar conteúdo de pesquisa facilmente usando extensões de navegador. Instale a extensão do navegador, vá para o site que você deseja adicionar como indicador e adicione o marcador.

Atualmente, as extensões do navegador estão disponíveis para o Edge e o Chrome.

- Para baixar extensões de borda, vá para a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) e baixe o aplicativo.
- Para baixar as extensões Chrome, vá para o [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) e baixe o aplicativo.

## <a name="bulk-add-or-edit-bookmarks"></a>Adicionar ou editar indicadores em massa

Use o recurso importar ou exportar para criar ou editar os indicadores em massa. Ela torna a adição ou edição de um grande número de indicadores mais rápido e mais fácil. Use-o para:

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

Estes são alguns pontos importantes sobre o arquivo de modelo:

- Nunca edite dados nestes campos: *ID*, *última modificação*e *última modificação por*
- Se você incluir a *ID* de um indicador existente, ele será substituído pelas informações no arquivo de importação.
- Para o indicador existente com o mesmo título ou URL, o indicador será atualizado com informações no arquivo de importação.
- Nem todos os campos no arquivo de modelo são obrigatórios, e os campos obrigatórios variam dependendo do estado do indicador.
- Com base no campo *estado* , os indicadores serão salvos como rascunho, sugerido, agendado ou serão publicados automaticamente.
- Para parceiros que gerenciam várias organizações, você pode exportar seus indicadores de uma organização e importá-los para outro. Mas você deve remover os dados na coluna *ID* antes de importar.

### <a name="prevent-import-errors"></a>Evite erros de importação

Você receberá um erro se algum dado necessário estiver faltando ou for inválido, e um arquivo de log será gerado com mais informações sobre as linhas e colunas a serem corrigidas. Faça as edições necessárias e tente importar o arquivo novamente. Você não pode importar ou salvar nenhum indicador até que todos os erros sejam resolvidos.

Para evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente e:

- Que ele inclua a linha de cabeçalho e todas as colunas que estavam no modelo de importação
- Que a ordem das colunas seja igual ao modelo de importação
- Todas as colunas têm valores, exceto os três que podem estar vazios: *ID*, *última modificação*e *última modificação por*
- A coluna de *estado* não está vazia, as informações são necessárias

Para evitar erros de duplicação de indicador para indicador:

- Não use URLS duplicadas para indicadores diferentes. Se uma URL for atribuída a outro indicador e você tentar adicioná-la novamente a partir de um arquivo de importação, receberá um erro. Isso também se aplica a URLs duplicadas para outros tipos de respostas.
- Ao atualizar indicadores existentes, use a coluna *ID do indicador* . Você pode atualizar qualquer outra propriedade de um indicador existente, como palavra-chave ou descrição, mas você deve certificar-se de que a *ID do indicador* está na coluna apropriada do arquivo de importação. Se a *ID do indicador* estiver presente, ela não será tratada como nova adição e não será processada como um erro.

## <a name="power-apps"></a>Aplicativos de energia

Ajudar os usuários a concluir tarefas, como inserir tempo de férias ou relatar despesas, adicionando aplicativos de alimentação existentes aos seus indicadores.

### <a name="power-apps-explained"></a>Aplicativos de energia explicados

O aplicativos de energia é um serviço que permite criar aplicativos de negócios que são executados em um navegador ou em um telefone ou Tablet sem nenhuma experiência de codificação necessária. Os aplicativos de energia funcionam em qualquer navegador e em qualquer dispositivo e levam menos de um minuto para serem adicionados. Para obter mais informações sobre aplicativos avançados, consulte:

- [Aprendizagem Orientada](https://docs.microsoft.com/learn/browse/?terms=power%20apps)
- [Documentação](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [Início de aplicativos de energia](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-power-app-to-a-bookmark"></a>Adicionar um aplicativo de alimentação a um indicador

1. Encontre a [ID do aplicativo para o aplicativo de energia](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) que você deseja adicionar.
1. No [centro de administração do Microsoft 365](https://admin.microsoft.com), acesse [**indicadores**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks).
1. Adicione um indicador ou localize um indicador existente ao qual você deseja adicionar um **aplicativo de alimentação** .
1. Em **configurações de indicador**, selecione **aplicativo de energia**e insira ou cole a ID do **aplicativo**.
    A altura e a largura são ajustadas automaticamente com base na orientação selecionada quando o aplicativo de energia foi criado. Os indicadores dão suporte a orientações retrato e paisagem. A visualização do indicador mostra um PowerApp totalmente funcional para facilitar o teste.
1. Selecione **Publicar** ou **Salvar em Rascunhos**.
