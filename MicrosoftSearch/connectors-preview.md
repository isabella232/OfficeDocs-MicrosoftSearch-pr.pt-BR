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
ms.openlocfilehash: f95f6283fa875a1cfa84556640b16a902b2f2185
ms.sourcegitcommit: c41334350654daef3a4cd45b5b18ea4401286997
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2020
ms.locfileid: "40947013"
---
# <a name="microsoft-graph-connectors-preview"></a>Visualização de conectores do Microsoft Graph

Os conectores do Microsoft Graph e as APIs de pesquisa da Microsoft (consulta e índice) estão atualmente no status de visualização. Para obter acesso à funcionalidade de conectores, você deve solicitar para participar do programa de visualização enviando o <a href="https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u" target="_blank">formulário de inscrição para visualização do conector do Microsoft Graph</a>. Esta é uma visualização inicial e não há garantia de nível de serviço. Incentivamos os clientes a experimentar a funcionalidade de conectores e a fornecer comentários. Não recomendamos o uso de conectores para fins de produção durante o período de visualização.

## <a name="set-up-targeted-release"></a>Configurar lançamento direcionado
Para experimentar os conectores, você deve ter a opção de **lançamento direcionada** definida para todos os usuários em sua organização. O requisito de lançamento direcionado se aplica independentemente dos seguintes ambientes de visualização que você escolher.
Para saber mais sobre a opção de lançamento direcionado e como configurá-la, confira <a href="https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide" target="_blank">configurar as opções de lançamento padrão ou direcionadas no Office 365</a>.

## <a name="choose-a-preview-environment"></a>Escolha um ambiente de visualização 
Para testar os conectores, as APIs de indexação e as APIs de pesquisa, recomendamos estes dois métodos:
1. **Testar locatário**.  Recomendamos que você use um locatário de teste para experimentar a visualização dos conectores do Microsoft Graph.
2. **Conjunto de sites de teste**. Se você não tem um locatário de teste, pode criar um conjunto de sites de teste para experimentar a funcionalidade de conectores. Para mostrar resultados de conectores sem afetar as páginas de pesquisa em qualquer outra parte da sua organização, personalize a experiência de pesquisa apenas desse conjunto de sites.

## <a name="preview-limitations"></a>Limitações de visualização
A versão prévia tem as seguintes limitações:
* A visualização pública dos conectores do Microsoft Graph só está disponível para locatários nas regiões dos EUA e da Europa. 
* O throughput da inclusão é limitado em cerca de quatro itens por segundo.
* Não há suporte para atualizações de esquema. Após criar uma configuração de conexão, não há como atualizar o esquema. Você só pode excluir e recriar a conexão.
* O conteúdo indexado aparece na página de resultados de pesquisa em uma vertical personalizada. Essa restrição se aplica ao conteúdo com tipos personalizados.
* Antes da disponibilidade geral, qualquer conexão que você configurou durante o período de visualização pode precisar ser excluída e recriada. Essas conexões não funcionarão mais se não forem compatíveis com as alterações feitas para melhorar o produto.
* Há um limite de conexões. Cada locatário pode criar até 10 conexões.
