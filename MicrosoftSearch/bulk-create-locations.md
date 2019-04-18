---
title: Criar locais em massa
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
ms.assetid: 15c9fada-f7a6-4210-aa6b-028b32217830
description: Adicionar vários locais de uma só vez com as ferramentas de importação para o portal de administração de pesquisa da Microsoft
ms.openlocfilehash: 3c7e43b03b97b46769d5e73f20ddae47b3459b59
ms.sourcegitcommit: c70dd5eae43abb775acc6fc4522c2e6be4f0bb67
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2019
ms.locfileid: "31901805"
---
# <a name="bulk-create-locations"></a>Criar locais em massa

Baixe e use o modelo. csv para criar, editar e salvar locais em massa. 
  
1. No canto superior direito da seção locais, clique em **importar**
    
2. Clique em **baixar locais modelo (. csv)**
    
3. Salve e abra o arquivo. csv
    
4. Adicione o conteúdo do local e salve o arquivo

    O arquivo. csv deve ser salvo como um arquivo CSV UTF-8, outros tipos de arquivo e codificações podem causar erros de importação
    
5. No canto superior direito da seção locais, clique em **importar**
    
6. No painel importar locais, clique em **procurar** e navegue até o arquivo. csv que você deseja importar 
    
7. Clique em **importar**

Os campos nos modelos de importação e exportação de locais são os mesmos. Você pode exportar, editar em massa e importar as edições ou começar com um modelo vazio para criar novos locais em massa. Para editar em massa locais existentes, exportá-los do portal de administração, fazer as edições necessárias e importá-las.

# <a name="prevent-import-errors"></a>Impedir erros de importação  
Você receberá um erro se os dados necessários estiverem ausentes ou forem inválidos. Dependendo do erro, um arquivo de log pode ser gerado com mais informações sobre as linhas e colunas que precisam ser corrigidas. Faça as edições necessárias e tente importar o arquivo novamente.
  
> [!NOTE]
> Até que todos os erros sejam resolvidos, não será possível criar ou editar nenhum local. 

Para ajudar a evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente:
- Inclui a linha de cabeçalho que estava no modelo de importação
- Inclui todas as colunas que estavam no modelo de importação
- A ordem da coluna é o mesmo que o modelo de importação
- Essas colunas podem estar vazias: ID, última modificação, última modificação, e lat/long  
Tentaremos determinar lat/long com base no endereço se esse campo estiver vazio
- A coluna de estado não pode ficar vazia, essas informações são necessárias  
Com base no campo Estado, os locais serão salvos como rascunho, sugerido, agendado ou serão publicados automaticamente.

Além disso, se você incluir a ID de um local existente, ele será substituído pelas informações no arquivo de importação.

Para organizações com vários locatários, você pode exportar seus locais de um locatário e importá-los para outro. Mas você deve remover todos os dados na coluna ID antes de importar.
  
Para saber mais sobre os campos obrigatórios e recomendados, confira [Adicionar um local](add-a-location.md).

  

