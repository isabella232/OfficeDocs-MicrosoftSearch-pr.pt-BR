---
title: Visualização de conectores
ms.author: mounika.narayanan
author: monaray
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Saiba mais sobre a visualização de conectores do Microsoft Graph para o Microsoft Search.
ms.openlocfilehash: 4bcd8360957be69bc701e8b356cd222de32bfc5f
ms.sourcegitcommit: 64eea81f8c1db9ee955013462a7b51612fb7d0b7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2020
ms.locfileid: "44604379"
---
# <a name="microsoft-graph-connectors-preview"></a>Visualização de conectores do Microsoft Graph

Os conectores do Microsoft Graph e as APIs de pesquisa da Microsoft (consulta e índice) estão atualmente no status de visualização. Para obter acesso à funcionalidade de conectores, você deve ativar a opção de lançamento direcionado no locatário. Esta é uma visualização inicial e não há garantia de nível de serviço. Incentivamos os clientes a experimentar a funcionalidade de conectores e a fornecer comentários. Não recomendamos o uso de conectores para fins de produção durante o período de visualização.

## <a name="set-up-targeted-release"></a>Configurar lançamento direcionado

Para experimentar os conectores, você deve ter a opção de **lançamento direcionada** definida para todos os usuários em sua organização. Para saber mais sobre a opção de lançamento direcionado e como configurá-la, confira [configurar as opções de lançamento padrão ou direcionadas no Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).

## <a name="choose-a-preview-environment"></a>Escolha um ambiente de visualização

Para testar os conectores, as APIs de indexação e as APIs de pesquisa, recomendamos estes dois métodos:

1. **Testar locatário**.  Recomendamos que você use um locatário de teste para experimentar a visualização dos conectores do Microsoft Graph.

2. **Conjunto de sites de teste**. Se você não tem um locatário de teste, pode criar um conjunto de sites de teste para experimentar a funcionalidade de conectores. Para mostrar resultados de conectores sem afetar as páginas de pesquisa em qualquer outra parte da sua organização, personalize a experiência de pesquisa apenas desse conjunto de sites.

## <a name="preview-limitations"></a>Limitações de visualização

A versão prévia tem as seguintes limitações:

* O throughput da inclusão é limitado em cerca de quatro itens por segundo.

* Não há suporte para atualizações de esquema. Após criar uma configuração de conexão, não há como atualizar o esquema. Você só pode excluir e recriar a conexão.

* O conteúdo indexado aparece na página de resultados de pesquisa em uma vertical personalizada. Essa restrição se aplica ao conteúdo com tipos personalizados.

* Qualquer conexão que você configurar durante o período de visualização talvez precise ser excluída e recriada. Essas conexões não funcionarão mais se não forem compatíveis com as alterações feitas para melhorar o produto.

* Há um limite de conexões. Cada locatário pode criar até 10 conexões.

* Tamanho do repositório de origem. Recomendamos que você visualize os conectores com um repositório de origem de cerca de 200.000 itens, já que esse é nosso limite de escala de pesquisa testada. Estamos trabalhando para melhorar o desempenho da pesquisa e esperamos oferecer suporte para tamanhos de repositório maiores em um futuro próximo.

* Editar o suporte para conexão não está disponível. Depois que a conexão tiver sido criada, você não poderá editá-la ou alterá-la. Se for necessário alterar os detalhes, você deverá excluir e recriar a conexão.

* O conteúdo do conector só pode ser pesquisado em verticais personalizadas.

* O conteúdo do conector de apenas uma conexão pode ser exibido em cada vertical personalizada e requer a criação do tipo de resultado.
