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
ROBOTS: NoIndex
description: Criar muitos indicadores de uma vez com as ferramentas de importação para o portal de administração de pesquisa da Microsoft
ms.openlocfilehash: 2983a47a8761a2463b25497911024f9bfd069369
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37948920"
---
# <a name="bulk-create-bookmarks"></a>Criar indicadores em massa

> [!IMPORTANT]
> Este artigo se aplica à Pesquisa da Microsoft no portal de administração do Bing. Estamos movendo o portal para o centro de administração do Microsoft 365 e, em seguida, a Pesquisa da Microsoft no portal do Bing será removida. Recomendamos que você use o centro de administração do Microsoft 365 para começar. [Visão geral da Pesquisa da Microsoft.](overview-microsoft-search.md)
    
Baixe e use o modelo. csv para criar, editar e salvar os indicadores em massa. Para editar em massa indicadores existentes, exporte-os do portal de administração, faça as edições necessárias e importe-as.
  
1. No canto superior direito da seção indicadores, clique em **importar**
    
2. Clique em **baixar indicadores de modelo (. csv)**
    
3. Salve e abra o arquivo .csv
    
4. Adicione o conteúdo e as configurações do indicador e salve o arquivo

    O arquivo .csv deve ser salvo como um arquivo CSV UTF-8; outros tipos de arquivo e/ou codificações podem causar erros de importação
    
5. No canto superior direito da seção indicadores, clique em **importar**
    
6. No painel importar marcadores, clique em **procurar** e navegue até o arquivo. csv que você deseja importar 
    
7. Clique em **Importar**

## <a name="prevent-import-errors"></a>Evite erros de importação      
Se os dados necessários estiverem ausentes ou forem inválidos, você receberá um erro. Dependendo do erro, pode ser gerado um arquivo de registro com mais informações sobre quais linhas e colunas precisam ser corrigidas. Faça as edições necessárias e tente importar o arquivo novamente.

> [!NOTE]
> Até que todos os erros sejam resolvidos, não será possível criar ou editar nenhum indicador. 

Para ajudar a evitar erros, verifique se o arquivo de importação está formatado corretamente:
- Inclui a linha de cabeçalho que estava no modelo de importação
- Inclui todas as colunas que estavam no modelo de importação
- A ordem das colunas é igual ao modelo de importação
- Essas colunas podem estar vazias: Id, Última Modificação e Última Modificação Por
- A coluna Estado não pode estar vazia, essa informação é necessária  
Com base no campo Estado, os indicadores serão salvos como rascunho, sugerido ou programado, ou serão publicados automaticamente.

Além disso, se você incluir a ID de um indicador existente, ele será substituído pelas informações no arquivo de importação.

Para parceiros que gerenciam várias organizações, você pode exportar seus indicadores de uma organização e importá-los para outro. Mas você deve remover todos os dados na coluna Id antes de importar.

Para saber mais sobre os campos obrigatórios e recomendados, confira [criar indicadores](create-bookmarks.md).
