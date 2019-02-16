---
title: Criar indicadores em massa
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 09/11/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: def300e7-103c-4e92-a062-28ffa27561d7
description: Criar muitos indicadores de uma vez com as ferramentas de importação para o portal de administração de pesquisa da Microsoft
ms.openlocfilehash: 07694de1f546a1431f371fa24ffc5721ea66337c
ms.sourcegitcommit: 61b4b84e581d3df6045851fe6c9c1291853dea06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2019
ms.locfileid: "30068399"
---
# <a name="bulk-create-bookmarks"></a>Criar indicadores em massa

Baixe e use o modelo. csv para criar, editar e salvar os indicadores em massa. Para editar em massa indicadores existentes, exporte-os do portal de administração, faça as edições necessárias e importe-as.
  
1. No canto superior direito da seção indicadores, clique em **importar**
    
2. Clique em **baixar indicadores de modelo (. csv)**
    
3. Salve e abra o arquivo. csv
    
4. Adicione o conteúdo e as configurações do indicador e salve o arquivo
    
5. No canto superior direito da seção indicadores, clique em **importar**
    
6. No painel importar marcadores, clique em **procurar** e navegue até o arquivo. csv que você deseja importar 
    
7. Clique em **importar**

# <a name="prevent-import-errors"></a>Impedir erros de importação      
Você receberá um erro se os dados necessários estiverem ausentes ou forem inválidos. Dependendo do erro, um arquivo de log pode ser gerado com mais informações sobre as linhas e colunas que precisam ser corrigidas. Faça as edições necessárias e tente importar o arquivo novamente.

> [!NOTE]
> Até que todos os erros sejam resolvidos, não será possível criar ou editar nenhum indicador. 

Para ajudar a evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente:
- Inclui a linha de cabeçalho que estava no modelo de importação
- Inclui todas as colunas que estavam no modelo de importação
- A ordem da coluna é o mesmo que o modelo de importação
- Essas colunas podem estar vazias: ID, última modificação e última modificação por
- A coluna de estado não pode ficar vazia, essas informações são necessárias  
Com base no campo Estado, os indicadores serão salvos como rascunho, sugerido, agendado ou serão publicados automaticamente.

Além disso, se você incluir a ID de um indicador existente, ele será substituído pelas informações no arquivo de importação.

Para organizações com vários locatários, você pode exportar seus indicadores de um locatário e importá-los para outro. Mas você deve remover todos os dados na coluna ID antes de importar.

Para saber mais sobre os campos obrigatórios e recomendados, confira [criar indicadores](create-bookmarks.md).
