---
title: Gerenciar P e R
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Encontre e atualize respostas individualmente ou use as ferramentas Pesquisa da Microsoft disponíveis para editar Q&como tudo de uma vez.
ms.openlocfilehash: 2ee42e3feaf5c14b2af820360f753ecc2e116f9b
ms.sourcegitcommit: cc9d743bcf5e998720ce9cd6eefb4061d913dc65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58701981"
---
# <a name="manage-qas"></a>Gerenciar P e R

A criação de P e R é semelhante à criação de indicadores. P&As allow you to answer the user's questions instead of just providing a link to a webpage. Você também pode formatar a resposta em rich text. Se um indicador e um Q&A compartilharem a mesma palavra-chave, o resultado do indicador será mostrado primeiro. Como indicadores, o índice Q&A é atualizado imediatamente depois que um Q&A é adicionado ou alterado.

## <a name="add-or-edit-a-single-qa"></a>Adicione ou edite um único P e R

1. No [Centro de administração do Microsoft 365,](https://admin.microsoft.com)vá para [**Q&A**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/qnas)
1. Para adicionar um Q&A, selecione **Adicionar**.
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

## <a name="add-or-edit-qas-using-browser-extensions"></a>Adicionar ou editar Q&como usar extensões de navegador

Os administradores de pesquisa podem criar conteúdo de pesquisa facilmente usando extensões de navegador. Instale a extensão do navegador e vá para o site do qual você deseja gerar um Q&A. Em seguida, você pode criar o Q&A e incluir um link para o site de origem.

Atualmente, as extensões do navegador estão disponíveis para Microsoft Edge e Chrome.

- Para baixar extensões para Borda (Herdado), vá para [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Para baixar extensões Chrome ou Edge (Chromium), vá para o [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="bulk-add-or-edit-qas"></a>Adicionar ou editar P e R em massa

Os administradores podem usar os recursos Importar e Exportar para criar ou editar Q&As.

Use o recurso Importação/Exportação para:

- Adicionar Q&Como - Adicionar detalhes no arquivo de modelo Q&e importá-lo.
- Editar em massa Q&Como - Exportar Q&Como para um arquivo .csv, edite os detalhes de Q&A no arquivo exportado e importe o arquivo.
- Fazer o&Como - Exportar Q&Como para um arquivo .csv.

Para importar ou exportar Q&As:

1. No canto superior direito da guia P e R, selecione **Importar**.
Selecione **Exportar** para baixar todas as&existentes como em um .csv arquivo.
1. No painel direito, selecione a opção a ser importada usando um arquivo .csv. Baixe o arquivo de modelo para obter uma lista dos campos e detalhes necessários.
1. Adicione ou edite Q&Um detalhes no arquivo de modelo e salve-o em seu computador.
1. No painel **Importar Q&A,** selecione **Procurar** e selecione o arquivo .csv que você deseja importar.
1. Selecione **Importar**.

Dicas importantes de arquivo de modelo:

- Nunca edite os dados nesses campos: **Id**, **Última modificação** e **Última modificação por**
- Se você incluir o **Id** de um indicador existente, ele será substituído pelas informações no arquivo de importação.
- Se houver um indicador existente que tenha o mesmo título ou URL, o indicador será atualizado com informações no arquivo de importação.
- Nem todos os campos no arquivo de modelo são necessários e os campos necessários variam dependendo do estado do indicador.
- Com base no **campo Estado,** os indicadores são salvos como *rascunho,* *sugerido* ou agendado, ou são publicados automaticamente.
- Para parceiros que gerenciam várias organizações: você pode exportar seus indicadores de uma organização e importá-los para outra. Mas você deve remover os dados na coluna **Id** antes de importar.

> [!NOTE]
> Não é possível importar Q&como se houvesse algum erro no arquivo de modelo. Para evitar erros, certifique-se de que o arquivo de importação está formatado corretamente e inclua todas as informações necessárias.

Para obter mais informações sobre como evitar erros, consulte [Prevent import errors](manage-bookmarks.md#prevent-import-errors).
