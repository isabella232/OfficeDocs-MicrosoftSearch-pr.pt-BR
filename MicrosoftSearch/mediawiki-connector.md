---
title: Conector MediaWiki para o Microsoft Search
ms.author: monaray
author: monaray97
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector MediaWiki para o Microsoft Search
ms.openlocfilehash: 7f6b34dcafc4b82ab3778ec1d7a4921383e44a44
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367636"
---
# <a name="mediawiki-connector"></a>Conector MediaWiki

Com o conector MediaWiki, sua organização pode descobrir e indexar dados de um wiki criado usando o software do MediaWiki. Esse conector indexa o conteúdo especificado à pesquisa da Microsoft e dá suporte a rastreamentos periódicos para manter o índice atualizado.

Este artigo é para os administradores do Microsoft 365 ou qualquer pessoa que configure, execute e monitore um conector MediaWiki. Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.

## <a name="connect-to-a-data-source"></a>Conectar-se a uma fonte de dados

Insira a URL e as credenciais do MediaWiki para autenticar a conexão. Você precisará das seguintes informações: **ID do locatário**, **ID do recurso**, ID do **cliente** e segredo do **cliente**.

## <a name="manage-search-permissions"></a>Gerenciar permissões de pesquisa

O conector MediaWiki suporta apenas as permissões de pesquisa visíveis para **todos**. Dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários da organização.

## <a name="assign-property-labels"></a>Atribuir rótulos de propriedade

Você pode atribuir uma propriedade Source a cada rótulo escolhendo a partir de um menu de opções. Embora esta etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá resultados de pesquisa mais precisos para os usuários finais.

## <a name="manage-schema"></a>Gerenciar esquema

Na tela **gerenciar esquema** , você tem a opção de alterar os atributos de esquema (**consultável**, **pesquisável**, **recuperável** e **refinável**) associados às propriedades, adicionar aliases opcionais e escolher a propriedade **Content** .

## <a name="set-the-refresh-schedule"></a>Definir o agendamento de atualização

Essa agenda atualiza dados indexados, portanto, as alterações no wiki são refletidas no Microsoft Search. Todas as novas páginas, páginas excluídas, conteúdo de página ou alterações de metadados aparecem nos resultados da pesquisa após o intervalo de atualização especificado. O tempo de rastreamento depende do tamanho do wiki. No momento, o conector é rastreado em torno de 50 páginas por minuto.

## <a name="limitations"></a>Limitações

O conector MediaWiki tem essas limitações na versão prévia:

* Oferece suporte somente a wikis baseados em nuvem.
* O suporta somente o Basic ou o OAuth 2,0 com a autenticação do Azure Active Directory ou do Azure.
* Não dá suporte à seleção de namespace para indexação. Indexa somente namespaces **principal**, de **categoria** e de **arquivo** .
* Não oferece suporte a listas de controle de acesso (ACLs). Portanto, as páginas indexadas são visíveis para todos os usuários da organização.
