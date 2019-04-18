---
title: Gerenciar indicadores
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/08/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Localizar indicadores que precisam ser atualizados e maneiras de editar em massa resultados de indicadores para o Microsoft Search
ms.openlocfilehash: f87176c645e127e20edd9e70a74efe05dd381236
ms.sourcegitcommit: c70dd5eae43abb775acc6fc4522c2e6be4f0bb67
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901797"
---
# <a name="manage-bookmarks"></a>Gerenciar indicadores

Com o tempo, talvez seja necessário atualizar o status e o conteúdo de um indicador para mantê-lo relevante. 
  
## <a name="filter-bookmarks"></a>Marcadores de filtro

Use a opção filtro no canto superior direito da página marcadores para localizar indicadores por data e que os modificaram. Por exemplo, defina o controle deslizante de data como 30 dias e selecione um administrador ou editor para ver a lista de marcadores criados ou alterados nesse momento.
  
## <a name="change-bookmark-content-or-settings"></a>Alterar o conteúdo ou as configurações do indicador

1. Acesse o Portal de Administração da Pesquisa da Microsoft
    
2. No painel de navegação, clique em **Indicadores**
    
3. Para localizar um indicador, pesquisa, filtro ou clique em um status de indicador para restringir os resultados
    
4. Para alterar ou atualizar um indicador, clique no título
    
5. Faça as alterações ou atualizações no conteúdo ou nas configurações e visualize como elas aparecerão 
    
6. Clique em **Salvar**
    
## <a name="bulk-export-and-edit-bookmarks"></a>Marcadores de exportação e edição em massa

Nunca edite dados nestes campos:
  
- Id
    
- Última modificação
    
- Modificado pela última vez por
    
ID é um identificador exclusivo para cada indicador e nunca deve ser editado. Os campos última modificação e modificado pela última vez por devem ser usados apenas para classificar e localizar indicadores.
  
1. Se você deseja exportar um subconjunto de seus indicadores, filtre-os
    
2. No canto superior direito da página indicadores, clique em **Exportar**
    
3. Salve ou abra o arquivo. csv
    
4. Edite dados em qualquer um destes campos:
   - Título
    
   - URL
    
   - Palavras-chave
    
   - Estado
    
   - Descrição
    
   - Palavras-chave reservadas
    
   - Data de Início
    
   - Data de término
    
   - País/Região
    
   - Grupos
    
   - So&amp;do dispositivo
    
   - Variações direcionadas
    
5. Salvar o arquivo. csv

    O arquivo. csv deve ser salvo como um arquivo CSV UTF-8, outros tipos de arquivo e codificações podem causar erros de importação
    
6. No canto superior direito da página indicadores, clique em **importar**
    
7. No painel importar marcadores, clique em **procurar** e selecione o arquivo. csv editado 
    
8. Clique em **importar**