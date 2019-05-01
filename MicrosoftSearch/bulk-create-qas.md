---
title: Criar perguntas e respostas em massa
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
ms.assetid: 7bada218-8908-4956-aae3-6ffaeef384ca
description: Adicionar rapidamente as respostas às perguntas frequentes com as ferramentas de importação no portal de administração de pesquisa da Microsoft
ms.openlocfilehash: 28fcf57c44f809e7f9b0c1b27042f4549067a0f8
ms.sourcegitcommit: a5fd9d4f46bbb7c539630735ac16e0c786939e5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2019
ms.locfileid: "33508668"
---
# <a name="bulk-create-qas"></a>Criar perguntas e respostas em massa

Baixe e use o modelo. csv para criar ou editar em massa Q&As. Também é uma maneira simples de salvar em massa as Q&As de rascunho que precisam de edições ou atualizações adicionais. Se você precisar editar em massa o Q&As existente, exporte-os do portal de administração, faça as edições necessárias e importe-as.
  
1. No canto superior direito da seção Q&As, clique em **importar**
    
2. Clique em **baixar modelo do Q&A (. csv)**
    
3. Salve e abra o arquivo. csv
    
4. Adicione o conteúdo e as configurações do Q&A e salve o arquivo

    O arquivo. csv deve ser salvo como um arquivo CSV UTF-8, outros tipos de arquivo e codificações podem causar erros de importação
    
5. No canto superior direito da seção Q&As, clique em **importar**
    
6. No painel importar Q&As, clique em **procurar** e navegue até o arquivo. csv que você deseja importar 
    
7. Clique em **importar**

# <a name="prevent-import-errors"></a>Impedir erros de importação      
Você receberá um erro se os dados necessários estiverem ausentes ou forem inválidos. Dependendo do erro, um arquivo de log pode ser gerado com mais informações sobre as linhas e colunas que precisam ser corrigidas. Faça as edições necessárias e tente importar o arquivo novamente.

> [!NOTE]
> Até que todos os erros sejam resolvidos, não será possível criar ou editar qualquer Q&As. 

Para ajudar a evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente:
- Inclui a linha de cabeçalho que estava no modelo de importação
- Inclui todas as colunas que estavam no modelo de importação
- A ordem da coluna é o mesmo que o modelo de importação
- Essas colunas podem estar vazias: ID, última modificação e última modificação por
- A coluna de estado não pode ficar vazia, essas informações são necessárias  
Com base no campo Estado, Q&As será salvo como rascunho, sugerido, agendado ou será publicado automaticamente.

Além disso, se você incluir a ID de um Q&A existente, ele será substituído pelas informações no arquivo de importação.

Para organizações com vários locatários, você pode exportar seu Q&As de um locatário e importá-lo para outro. Mas você deve remover todos os dados na coluna ID antes de importar.

Para saber mais sobre os campos obrigatórios e recomendados, consulte [criar Q&As](create-qas.md).

  

