---
title: Gerenciar locais
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 8ab9aa00-cd74-405f-8410-9a1c3cfacdb9
description: Com o tempo, você pode precisar atualizar o status e o conteúdo de um local para mantê-lo relevante.
ms.openlocfilehash: bb229086f7dd8c1b8d17a0b8335bb618850106be
ms.sourcegitcommit: 063fec4a336b6b3118d4769a4bd0cc2d568ea7e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42276984"
---
# <a name="manage-locations"></a>Gerenciar locais

## <a name="location"></a>Localização

Os Locais ajudam os usuários a encontrarem endereços e localizarem os edifícios da sua organização, fornecendo uma localização precisa para escritórios, campi e edifícios, além de trajetos e navegação. Os administradores devem adicionar todos os locais importantes da sua organização. Ao contrário dos indicadores e das P e R, o índice não é atualizado imediatamente e pode levar várias horas para que locais novos ou alterados apareçam nos resultados de pesquisa.

### <a name="add-or-edit-a-single-location"></a>Adicionar ou editar um único local

1. Vá para o **centro de administração do Microsoft 365**.
1. No painel de navegação, vá para **Configurações** e selecione **Pesquisa da Microsoft**.
1. Selecione a guia **Locais**. Por padrão, a guia **Indicadores** se encontra selecionada na página de **Pesquisa da Microsoft**.
1. Para adicionar um novo local, selecione **Adicionar novo**.
1. Para editar um local, selecione o local na lista de locais relevantes.
1. À medida que você adiciona ou edita as informações, a visualização é atualizada automaticamente.
1. Salve suas alterações.

### <a name="bulk-add-or-edit-locations"></a>Adicionar ou editar locais em massa

Os administradores podem usar o recurso Importar ou Exportar para adicionar ou editar locais em massa.

Use o recurso de importação/exportação para:

1. Adicionar local em massa - Adicione detalhes no arquivo de modelo de local e, em seguida, importe-o.
1. Edição em massa de locais - exporte locais para um arquivo .csv, edite os detalhes do local no arquivo .csv exportado e importe o arquivo .csv atualizado.
1. Locais de backup – exportar locais existentes para um arquivo. csv.

Para exportar ou importar locais:

1. No canto superior direito da guia **Locais**, selecione **Importar**.
Selecione **Exportar** para baixar os locais existentes em um arquivo .csv.
1. No painel direito, escolha a opção de importar usando um arquivo .csv.
Faça o download do arquivo de modelo para obter uma lista dos campos e detalhes necessários.
1. Adicione ou edite detalhes do local no arquivo de modelo e, em seguida, salve-o no seu computador.
1. No painel **Importar** locais, selecione **Procurar** e, em seguida, selecione o arquivo .csv que você deseja importar.
1. Selecione **Importar**.

Aqui estão alguns pontos importantes sobre o arquivo de modelo:

- Nunca edite os dados nesses campos: *Id*, *Última modificação* e *Última modificação por*
- Se você incluir a *ID* de um local existente, ele será substituído pelas informações no arquivo de importação.
- Se houver um local existente com o mesmo nome, o local será atualizado com informações no arquivo de importação.
- Nem todos os campos no arquivo de modelo são obrigatórios e os campos obrigatórios variam de acordo com o estado do local.
- Com base no campo *estado* , os locais serão salvos como rascunho, sugerido, agendado ou serão publicados automaticamente.
- Para parceiros que gerenciam várias organizações, você pode exportar seus locais de uma organização e importá-los para outro. Mas você deve remover os dados na coluna *Id* antes de importar.

**Observação:** Você não pode importar Locais se houver algum erro no arquivo de modelo. Para evitar erros, verifique se o arquivo de importação está formatado corretamente e inclua todas as informações necessárias.

Para obter mais informações sobre como evitar erros, consulte [Evite erros de importação](manage-bookmarks.md#prevent-import-errors).
