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
ROBOTS: NoIndex
description: Adicionar vários locais de uma só vez com as ferramentas de importação para o portal de administração de pesquisa da Microsoft
ms.openlocfilehash: e01c3774439a931dc81f850d8cbee76cc6128a53
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311337"
---
# <a name="bulk-create-locations"></a>Criar locais em massa

> [!IMPORTANT]
> Este artigo se aplica à Pesquisa da Microsoft no portal de administração do Bing. Estamos movendo o portal para o centro de administração do Microsoft 365 e, em seguida, a Pesquisa da Microsoft no portal do Bing será removida. Recomendamos que você use o centro de administração do Microsoft 365 para começar. [Visão geral da Pesquisa da Microsoft.](overview-microsoft-search.md)
    
Baixe e use o modelo. csv para criar, editar e salvar locais em massa. 
  
1. No canto superior direito da seção locais, clique em **importar**
    
2. Clique em **baixar locais modelo (. csv)**
    
3. Salve e abra o arquivo .csv
    
4. Adicione o conteúdo do local e salve o arquivo

    O arquivo .csv deve ser salvo como um arquivo CSV UTF-8; outros tipos de arquivo e/ou codificações podem causar erros de importação
    
5. No canto superior direito da seção locais, clique em **importar**
    
6. No painel importar locais, clique em **procurar** e navegue até o arquivo. csv que você deseja importar 
    
7. Clique em **Importar**

Os campos nos modelos de importação e exportação de locais são os mesmos. Você pode exportar, editar em massa e importar as edições ou começar com um modelo vazio para criar novos locais em massa. Para editar em massa locais existentes, exportá-los do portal de administração, fazer as edições necessárias e importá-las.

## <a name="prevent-import-errors"></a>Evite erros de importação  
Se os dados necessários estiverem ausentes ou forem inválidos, você receberá um erro. Dependendo do erro, pode ser gerado um arquivo de registro com mais informações sobre quais linhas e colunas precisam ser corrigidas. Faça as edições necessárias e tente importar o arquivo novamente.
  
> [!NOTE]
> Até que todos os erros sejam resolvidos, não será possível criar ou editar nenhum local. 

Para ajudar a evitar erros, verifique se o arquivo de importação está formatado corretamente:
- Inclui a linha de cabeçalho que estava no modelo de importação
- Inclui todas as colunas que estavam no modelo de importação
- A ordem das colunas é igual ao modelo de importação
- Essas colunas podem estar vazias: ID, última modificação, última modificação, e lat/long  
Tentaremos determinar lat/long com base no endereço se esse campo estiver vazio
- A coluna Estado não pode estar vazia, essa informação é necessária  
Com base no campo Estado, os locais serão salvos como rascunho, sugerido, agendado ou serão publicados automaticamente.

Além disso, se você incluir a ID de um local existente, ele será substituído pelas informações no arquivo de importação.

Para parceiros que gerenciam várias organizações, você pode exportar seus locais de uma organização e importá-los para outro. Mas você deve remover todos os dados na coluna Id antes de importar.
  
Para saber mais sobre os campos obrigatórios e recomendados, confira [Adicionar um local](add-a-location.md).

  

