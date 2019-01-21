---
title: Gerenciar Q&As
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: 7e3432e6-5317-4d63-90b0-52da6fddd343
description: Localizar e atualizar respostas individualmente ou usar ferramentas do Microsoft Search disponíveis para editá-los ao mesmo tempo
ms.openlocfilehash: c0f6b42aa1e0ad8c4736d37ec4dcc8cff6025dbc
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378413"
---
# <a name="manage-qas"></a>Gerenciar Q&As

Ao longo do tempo, você pode precisar atualizar status de um Q&A e conteúdo para mantê-la relevantes.
  
## <a name="filter-qas"></a>Filtro Q&As

Use a opção filtro no canto superior direito da página Q&As para encontrar Q&As por data e quem o modificou. Por exemplo, defina o controle deslizante de data para 30 dias e selecione um administrador ou um editor para ver a lista de Q&As eles foram criado ou alterado no momento.
  
## <a name="change-qa-content-or-settings"></a>Alterar configurações ou Q&A conteúdo

1. Vá para o portal de administração de pesquisa da Microsoft
    
2. No painel de navegação, clique em **Q&As**
    
3. Para localizar um Q&A, a pesquisa, o filtro ou clique em um status de Q&A para restringir os resultados
    
4. Para alterar ou atualizar um Q&A, clique no título
    
5. Fazer quaisquer alterações ou atualizações no conteúdo ou configurações e como eles aparecerá de visualização
    
6. Clique em **Salvar**
    
## <a name="bulk-export-and-edit-qas"></a>Exportação em massa e editar Q&As

Nunca edite dados nesses campos:
  
- Id
    
- Modificado pela última vez
    
- Modificado pela última vez
    
ID é um identificador exclusivo para cada Q&A e nunca deve ser editado. Os campos de última modificação e modificado por só devem ser usados para classificar e localizar Q&As.
  
1. Se você deseja exportar um subconjunto de sua Q&As, filtrá-los
    
2. No canto superior direito da página Q&As, clique em **Exportar**
    
3. Salvar ou abrir o arquivo. csv
    
4. Edite dados em qualquer um desses campos:
    
   - Pergunta
    
   - URL
      
   - Palavras-chave
    
   - Estado
    
   - Descrição de resposta
    
   - Palavras-chave reservadas
    
   - Data de Início
    
   - Data de término
    
   - País/Região
    
   - Grupos
    
   - Dispositivo&amp;SO
    
   - Variações direcionadas
    
5. Salve o arquivo. csv
    
6. No canto superior direito da página Q&As, clique em **Importar**
    
7. No painel de Q&As de importação, clique em **Procurar** e selecione o arquivo. csv editadas 
    
8. Clique em **Importar**
    
Você receberá um erro se todos os dados necessários estão ausente ou inválido. Dependendo do erro, um arquivo de log pode ser gerado com mais informações sobre as linhas e colunas que precisam ser corrigido. Faça qualquer edições necessárias e tente importar o arquivo novamente.
  
> [!NOTE]
> Até que todos os erros forem resolvidos, é possível criar ou editar qualquer Q&As. 
  
Nem todos os campos são necessários e campos obrigatórios variam dependendo do estado de Q&A. Com base no campo de estado, as Q&As será salva como agendado de rascunho, sugerido, ou eles serão publicados automaticamente. Saiba mais sobre campos necessários e recomendados em [criar Q&As](create-qas.md).

  

