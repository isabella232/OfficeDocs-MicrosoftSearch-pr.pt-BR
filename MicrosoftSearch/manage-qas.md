---
title: Gerenciar P e R
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
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Encontre e atualize as respostas individualmente ou use as ferramentas de pesquisa da Microsoft disponíveis para editar Q&todas ao mesmo tempo.
ms.openlocfilehash: 2ec06fb0940172621255946283290450c1f2e036
ms.sourcegitcommit: 7ad6f4b0ab6cd7b912862273a8b4d48a6507bc29
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2020
ms.locfileid: "44878229"
---
# <a name="manage-qas"></a>Gerenciar P e R

A criação de P e R é semelhante à criação de indicadores. P&como permitir que você responda às perguntas do usuário em vez de apenas fornecer um link para uma página da Web. Você também pode formatar a resposta em Rich Text. Se um indicador e um Q&um compartilham a mesma palavra-chave, o resultado do indicador será mostrado primeiro. Como indicadores, o Q&um índice é atualizado imediatamente após um Q&A é adicionado ou alterado.

## <a name="add-or-edit-a-single-qa"></a>Adicione ou edite um único P e R

1. Vá para o **centro de administração do Microsoft 365**.
1. No painel de navegação, vá para **Configurações** e selecione **Pesquisa da Microsoft**.
1. Selecione a guia **Q&uma** .
1. Para adicionar P e R, selecione **Adicionar novo**.
Para editar P e R, selecione o P e R na lista P e R relevante. À medida que você adiciona ou edita as informações, a visualização é atualizada automaticamente.
1. Salve suas alterações.

### <a name="supported-html-tags"></a>Tags HTML com suporte

Você pode usar o conteúdo HTML existente ou adicionar tags HTML à sua resposta (descrição). Tags não compatíveis são ignoradas.

As seguintes tags HTML são compatíveis:

- blockquote
- div
- em
- h1, h2, h3 e h4
- ol, ul e li
- p
- pre
- span
- strong
- table, thead, tbody, tr, th e td
- u
- a
- code
- br
- hr
- img

## <a name="add-or-edit-qas-using-browser-extensions"></a>Adicionar ou Editar Q&como usando extensões de navegador

Os administradores de pesquisa podem criar conteúdo de pesquisa facilmente usando extensões de navegador. Instale a extensão do navegador e vá para o site do qual você deseja gerar um p&A. Você pode criar o Q&A e incluir um link para o site de origem.

No momento, as extensões do navegador estão disponíveis para o Microsoft Edge e o Chrome.

- Para baixar extensões para borda (herdadas), acesse [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Para baixar as extensões Chrome ou Edge (Chromium), vá para o [repositório da Web do Chrome](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="bulk-add-or-edit-qas"></a>Adicionar ou editar P e R em massa

Os administradores podem usar os recursos de importação e exportação para criar ou editar em massa&como.

Use o recurso importar/exportar para:

- Adição em massa&como: adicionar detalhes no arquivo de modelo Q&um e, em seguida, importá-lo.
- Editar em massa&como-Export Q&como em um arquivo. csv, edite os detalhes do&a no arquivo exportado e, em seguida, importe o arquivo.
- Faça backup de p&como exportar Q&como em um arquivo. csv.

Para importar ou exportar Q&como:

1. No canto superior direito da guia P e R, selecione **Importar**.
Selecione **Exportar** para baixar todos os Q&existentes como em um arquivo. csv.
1. No painel direito, selecione a opção para importar usando um arquivo. csv. Baixe o arquivo de modelo para obter uma lista dos campos e detalhes necessários.
1. Adicione ou edite Q&um detalhes no arquivo de modelo e salve-o no computador.
1. No painel **importar p&um** , selecione **procurar**e selecione o arquivo. csv que você deseja importar.
1. Selecione **Importar**.

Dicas importantes de arquivos de modelo:

- Nunca edite os dados nesses campos: **Id**, **Última modificação** e **Última modificação por**
- Se você incluir o **Id** de um indicador existente, ele será substituído pelas informações no arquivo de importação.
- Se houver um indicador existente com o mesmo título ou URL, o indicador será atualizado com informações no arquivo de importação.
- Nem todos os campos no arquivo de modelo são necessários e os campos obrigatórios variam dependendo do estado do indicador.
- Com base no campo **estado** , os indicadores são salvos como *rascunho*, *sugerido*ou *agendado*ou são publicados automaticamente.
- Para parceiros que gerenciam várias organizações: você pode exportar seus indicadores de uma organização e importá-los para outro. Mas você deve remover os dados na coluna **Id** antes de importar.

> [!NOTE]
> Não é possível importar Q&como se há erros no arquivo de modelo. Para evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente e inclua todas as informações necessárias.

Para obter mais informações sobre como evitar erros, consulte [evitar erros de importação](manage-bookmarks.md#prevent-import-errors).
