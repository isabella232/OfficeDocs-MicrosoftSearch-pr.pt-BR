---
title: Criar P e R em massa
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
ROBOTS: NoIndex
description: Adicione respostas a perguntas frequentes rapidamente com ferramentas de importação no portal de administração da Pesquisa da Microsoft
ms.openlocfilehash: 660f5663ff6238f4ab59dab36d51f1311d5c7260
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949028"
---
# <a name="bulk-create-qas"></a>Criar P e R em massa

> [!IMPORTANT]
> Este artigo se aplica à Pesquisa da Microsoft no portal de administração do Bing. Estamos movendo o portal para o centro de administração do Microsoft 365 e, em seguida, a Pesquisa da Microsoft no portal do Bing será removida. Recomendamos que você use o centro de administração do Microsoft 365 para começar. [Visão geral da Pesquisa da Microsoft.](overview-microsoft-search.md)
    
Baixe e use o modelo .csv para criar e editar P e R em massa. Também é uma maneira simples de salvar em massa rascunhos de perguntas e respostas que precisam de edições e atualizações adicionais. Para editar perguntas e respostas existentes em massa, exporte-as do portal de administração, faça as edições necessárias e depois importe-as.
  
1. No canto superior direito da seção Perguntas e Respostas, clique em **Importar**
    
2. Clique em **Baixar modelo de perguntas e respostas (.csv)**
    
3. Salve e abra o arquivo .csv
    
4. Adicione o conteúdo e as configurações de P e R e salve o arquivo

    O arquivo .csv deve ser salvo como um arquivo CSV UTF-8; outros tipos de arquivo e/ou codificações podem causar erros de importação
    
5. No canto superior direito da seção P e R, clique em **Importar**
    
6. No painel Importar P e R, clique em **Procurar** e navegue até o arquivo .csv que deseja importar. 
    
7. Clique em **Importar**

## <a name="prevent-import-errors"></a>Evite erros de importação      
Se os dados necessários estiverem ausentes ou forem inválidos, você receberá um erro. Dependendo do erro, pode ser gerado um arquivo de registro com mais informações sobre quais linhas e colunas precisam ser corrigidas. Faça as edições necessárias e tente importar o arquivo novamente.

> [!NOTE]
> Até que todos os erros sejam resolvidos, não será possível criar ou editar nenhum item de P e R. 

Para ajudar a evitar erros, verifique se o arquivo de importação está formatado corretamente:
- Inclui a linha de cabeçalho que estava no modelo de importação
- Inclui todas as colunas que estavam no modelo de importação
- A ordem das colunas é igual ao modelo de importação
- Essas colunas podem estar vazias: Id, Última Modificação e Última Modificação Por
- A coluna Estado não pode estar vazia, essa informação é necessária  
Com base no campo Estado, as P e R serão salvas como rascunho, sugerido, programado, ou serão publicadas automaticamente.

Além disso, se você incluir o Id de uma pergunta e resposta existente, ele será substituído pelas informações no arquivo de importação.

Para parceiros que gerenciam várias organizações, você pode exportar seus Q&como de um org e importá-los para outro. Mas você deve remover todos os dados na coluna Id antes de importar.

Para saber mais sobre os campos obrigatórios e recomendados, consulte [Criar P e R](create-qas.md).

  

