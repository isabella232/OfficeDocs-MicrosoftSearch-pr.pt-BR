---
title: Gerenciar P e R
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
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Encontre e atualize as respostas individualmente ou use as ferramentas da Pesquisa da Microsoft disponíveis para editar todas elas de uma só vez
ms.openlocfilehash: 8620842e64a40eb32467c42a289bdec3b67d303b
ms.sourcegitcommit: be2e837d9b087bffe6ce40d72d7ae58a8fcdf3fe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/30/2019
ms.locfileid: "34591517"
---
# <a name="manage-qas"></a>Gerenciar P e R

A criação de P e R é semelhante à criação de indicadores. As P e R permitem que você responda uma pergunta do usuário, em vez de apenas fornecer um link para uma página da Web. Você pode formatar a resposta em rich text usando as ferramentas disponíveis. Se um indicador e um P e R compartilham a mesma palavra-chave, o resultado do indicador é mostrado primeiro. Como os Indicadores, o índice de P e R é atualizado imediatamente depois que um P e R é adicionado ou alterado. 

## <a name="add-or-edit-a-single-qa"></a>Adicione ou edite um único P e R
1. Vá para o **centro de administração do Microsoft 365**.
1. No painel de navegação, vá para **Configurações** e selecione **Pesquisa da Microsoft**.
1. Selecione a guia **P e R**. Por padrão, a primeira guia (**Indicadores**) se encontra selecionada.
1. Para adicionar P e R, selecione **Adicionar novo**.
Para editar P e R, selecione o P e R na lista P e R relevante.
1. À medida que você adiciona ou edita as informações, a visualização é atualizada automaticamente.
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

## <a name="bulk-add-or-edit-qas"></a>Adicionar ou editar P e R em massa
Os administradores podem usar os recursos de importação e exportação para criar ou editar P e R em massa. Esse é um recurso útil quando os administradores precisam adicionar ou editar um grande número de P e R. 

Use o recurso de importação/exportação para:
1. Adicionar P e R em massa - Adicione detalhes no arquivo de modelo P e R e importe-o.
1. Edição em massa de P e R - Exporte P e R para um ficheiro .csv, edite os detalhes de P e R no ficheiro .csv exportado e, em seguida, importe o ficheiro .csv.
1. Backup de P e R - Exporte P e R para um arquivo .csv.

Para importar ou exportar P e R:
1. No canto superior direito da guia P e R, selecione **Importar**. Selecione **Exportar** para baixar todas as P e R existentes em um arquivo .csv.
1. No painel direito, escolha a opção de importar usando um arquivo .csv.
Faça o download do arquivo de modelo para obter uma lista dos campos e detalhes necessários. 
1. Adicione ou edite os detalhes de P e R no arquivo de modelo e salve-o no seu computador. 
1. No painel **Importar P e R**, selecione **Procurar** e, em seguida, o arquivo .csv que você deseja importar.
1. Selecione **Importar**.

Aqui estão alguns pontos importantes sobre o arquivo de modelo:
- Nunca edite os dados nesses campos: *Id*, *Última modificação* e *Última modificação por*
- Se você incluir o *Id* de um indicador existente, ele será substituído pelas informações no arquivo de importação.
- Se houver um indicador existente com o mesmo título ou URL, o indicador será atualizado com informações no arquivo de importação.
- Nem todos os campos no arquivo de modelo são obrigatórios, e os campos obrigatórios variam dependendo do estado do indicador.
- Com base no campo Estado, os indicadores serão salvos como rascunho, sugerido ou programado, ou serão publicados automaticamente.
- Para organizações com vários locatários, você pode exportar seus indicadores de um locatário e importá-lo para outro. Mas você deve remover os dados na coluna *Id* antes de importar.

**Observação:** Você não pode importar P e R se houver algum erro no arquivo de modelo. Para evitar erros, verifique se o arquivo de importação está formatado corretamente e inclua todas as informações necessárias. 

Para obter mais informações sobre como evitar erros, consulte [Evite erros de importação](manage-bookmarks.md#prevent-import-errors).