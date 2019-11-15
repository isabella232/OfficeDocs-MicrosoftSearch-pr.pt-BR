---
title: Conector MediaWiki para o Microsoft Search
ms.author: v-pamcn
author: monaray
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
ms.openlocfilehash: 2aa0ef494aa42b1a7364ec68f6532dec737b9c25
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626959"
---
# <a name="mediawiki-connector"></a>Conector MediaWiki

Com o conector MediaWiki, sua organização pode descobrir e indexar dados de um wiki criado usando o software do MediaWiki. Esse conector indexa o conteúdo especificado à pesquisa da Microsoft e dá suporte a rastreamentos periódicos para manter o índice atualizado.

Este artigo é para os administradores do Microsoft 365 ou qualquer pessoa que configure, execute e monitore um conector MediaWiki. Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.

## <a name="connect-to-a-data-source"></a>Conectar-se a uma fonte de dados
Insira a URL e as credenciais do MediaWiki para autenticar a conexão. Você precisará das seguintes informações: **ID do locatário**, **ID do recurso**, ID do **cliente**e segredo do **cliente**.

## <a name="manage-the-search-schema"></a>Gerenciar o esquema de pesquisa
Após a conexão bem-sucedida, configure o mapeamento de esquema de pesquisa. Você pode escolher quais propriedades tornar **consultáveis**, **pesquisáveis**e **recuperáveis**.

## <a name="manage-search-permissions"></a>Gerenciar permissões de pesquisa
O conector MediaWiki suporta apenas as permissões de pesquisa visíveis para **todos**. Dados indexados aparecem nos resultados da pesquisa e são visíveis para todos os usuários da organização.

## <a name="set-the-refresh-schedule"></a>Definir o agendamento de atualização 
Essa agenda atualiza dados indexados, portanto, as alterações no wiki são refletidas no Microsoft Search. Todas as novas páginas, páginas excluídas, conteúdo de página ou alterações de metadados aparecem nos resultados da pesquisa após o intervalo de atualização especificado. O tempo de rastreamento depende do tamanho do wiki. No momento, o conector é rastreado em torno de 50 páginas por minuto.

## <a name="limitations"></a>Limitações 
O conector MediaWiki tem essas limitações na versão prévia:
* Oferece suporte somente a wikis baseados em nuvem.
* O suporta somente o Basic ou o OAuth 2,0 com a autenticação do Azure Active Directory ou do Azure.
* Não dá suporte à seleção de namespace para indexação. Indexa somente namespaces **principal**, de **categoria**e de **arquivo** .
* Não oferece suporte a listas de controle de acesso (ACLs). Portanto, as páginas indexadas são visíveis para todos os usuários da organização.
