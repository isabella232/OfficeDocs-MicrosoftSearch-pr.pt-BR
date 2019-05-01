---
title: Gerenciar perguntas e respostas
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
description: Localizar e atualizar respostas individualmente ou usar as ferramentas de pesquisa da Microsoft disponíveis para editar todas de uma só vez
ms.openlocfilehash: 47882deeb95133cfc19f4eec6417fc20fb7203de
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508814"
---
# <a name="manage-qas"></a>Gerenciar perguntas e respostas

Com o tempo, talvez seja necessário atualizar um status e conteúdo do Q&A's para mantê-lo relevante.
  
## <a name="filter-qas"></a>Filtrar Q&As

Use a opção filtro no canto superior direito da página Q&As para localizar Q&As por data e quem as modificou. Por exemplo, defina o controle deslizante de data como 30 dias e selecione um administrador ou editor para ver a lista de Q&As que eles criaram ou mudaram nesse momento.
  
## <a name="change-qa-content-or-settings"></a>Alterar o conteúdo ou as configurações do Q&A

1. Ir para o Portal de Administração da Pesquisa da Microsoft
    
2. No painel de navegação, clique em **P e R**
    
3. Para localizar um Q&A, pesquisa, filtro ou clique em um status de Q&A para restringir os resultados
    
4. Para alterar ou atualizar um Q&A, clique no título
    
5. Faça as alterações ou atualizações no conteúdo ou nas configurações e visualize como elas aparecerão
    
6. Clique em **Salvar**
    
## <a name="bulk-export-and-edit-qas"></a>Exportação e edição em massa Q&As

Nunca edite dados nestes campos:
  
- Id
    
- Última modificação
    
- Modificado pela última vez por
    
ID é um identificador exclusivo para cada Q&A e nunca deve ser editado. Os campos última modificação e modificado pela última vez por devem ser usados apenas para classificar e localizar Q&As.
  
1. Se você deseja exportar um subconjunto de seu Q&As, filtre-os
    
2. No canto superior direito da página Q&As, clique em **Exportar**
    
3. Salve ou abra o arquivo. csv
    
4. Edite dados em qualquer um destes campos:
    
   - Pergunta
    
   - URL
      
   - Palavras-chave
    
   - Estado
    
   - Descrição da resposta
    
   - Palavras-chave reservadas
    
   - Data de Início
    
   - Data de término
    
   - País/Região
    
   - Grupos
    
   - So&amp;do dispositivo
    
   - Variações direcionadas
    
5. Salvar o arquivo. csv

    O arquivo. csv deve ser salvo como um arquivo CSV UTF-8, outros tipos de arquivo e codificações podem causar erros de importação
    
6. No canto superior direito da página Q&As, clique em **importar**
    
7. No painel importar Q&As, clique em **procurar** e selecione o arquivo. csv editado 
    
8. Clique em **importar**
    
Você receberá um erro se os dados necessários estiverem ausentes ou forem inválidos. Dependendo do erro, um arquivo de log pode ser gerado com mais informações sobre as linhas e colunas que precisam ser corrigidas. Faça as edições necessárias e tente importar o arquivo novamente.
  
> [!NOTE]
> Até que todos os erros sejam resolvidos, não será possível criar ou editar qualquer Q&As. 
  
Nem todos os campos obrigatórios e obrigatórios variam de acordo com o estado Q&A. Com base no campo Estado, Q&As será salvo como rascunho, sugerido, agendado ou será publicado automaticamente. Saiba mais sobre os campos obrigatórios e recomendados em [criar Q&As](create-qas.md).

  

