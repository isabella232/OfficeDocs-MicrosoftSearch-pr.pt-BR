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
description: Crie vários indicadores de uma só vez com ferramentas de importação para o portal de administração da Pesquisa da Microsoft
ms.openlocfilehash: 560cda6f94060d428f2d18cc61bd2430cb31b474
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968344"
---
# <a name="bulk-create-bookmarks"></a>Criar indicadores em massa

> [!IMPORTANT]
> As configurações da Pesquisa da Microsoft no Bing agora estão disponíveis no centro de administração do Microsoft 365. Comece por [atribuir administradores de pesquisa](https://docs.microsoft.com/pt-BR/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) ao seu centro de administração.
    
Baixe e use o modelo .csv para criar, editar e salvar indicadores em massa. Para editar indicadores existentes em massa, exportá-los do portal de administração, fazer as edições necessárias e depois importá-los.
  
1. No canto superior direito da página Indicadores, clique em **Importar**
    
2. Clique em **Baixar modelo indicadores (.csv)**
    
3. Salve e abra o arquivo .csv
    
4. Adicione o conteúdo e as configurações do indicador e salve o arquivo

    O arquivo .csv deve ser salvo como um arquivo CSV UTF-8; outros tipos de arquivo e/ou codificações podem causar erros de importação
    
5. No canto superior direito da seção Indicadores, clique em **Importar**
    
6. No painel Importar indicadores, clique em **Procurar** e navegue até o arquivo .csv que você deseja importar 
    
7. Clique em **Importar**

# <a name="prevent-import-errors"></a>Evite erros de importação      
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

Além disso, se você incluir o ID de um indicador existente, ele será substituído pelas informações no arquivo de importação.

Para organizações com vários locatários, você pode exportar seus indicadores de um locatário e importá-los para outro. Mas você deve remover todos os dados na coluna Id antes de importar.

Para saber mais sobre campos obrigatórios e recomendados, consulte [Criar indicadores](create-bookmarks.md).
