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
description: Adicione vários locais de uma só vez com ferramentas de importação para o portal de administração da Pesquisa da Microsoft
ms.openlocfilehash: 1d360fda2851083def0bcbd8fcffd77cfa15240e
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968288"
---
# <a name="bulk-create-locations"></a>Criar locais em massa

> [!IMPORTANT]
> As configurações da Pesquisa da Microsoft no Bing agora estão disponíveis no centro de administração do Microsoft 365. Comece por [atribuir administradores de pesquisa](https://docs.microsoft.com/pt-BR/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) ao seu centro de administração.
    
Faça o download e use o modelo .csv para criar, editar e salvar locais em massa. 
  
1. No canto superior direito da seção Locais, clique em **Importar**
    
2. Clique em **Baixar modelo de locais (.csv)**
    
3. Salve e abra o arquivo .csv
    
4. Adicione o conteúdo do local e salve o arquivo

    O arquivo .csv deve ser salvo como um arquivo CSV UTF-8; outros tipos de arquivo e/ou codificações podem causar erros de importação
    
5. No canto superior direito da seção Locais, clique em **Importar**
    
6. No painel Importar Locais, clique em **Procurar** e navegue até o arquivo .csv que você deseja importar. 
    
7. Clique em **Importar**

Os campos nos modelos de locais de importação e exportação são os mesmos. Você pode exportar, editar em massa e importar as edições, ou começar com um modelo vazio para criar novos locais em massa. Para editar locais existentes em massa, exporte-os a partir do portal de administração, efetue as edições necessárias e, em seguida, importe-os.

# <a name="prevent-import-errors"></a>Evite erros de importação  
Se os dados necessários estiverem ausentes ou forem inválidos, você receberá um erro. Dependendo do erro, pode ser gerado um arquivo de registro com mais informações sobre quais linhas e colunas precisam ser corrigidas. Faça as edições necessárias e tente importar o arquivo novamente.
  
> [!NOTE]
> Até que todos os erros sejam resolvidos, você não poderá criar ou editar nenhum local. 

Para ajudar a evitar erros, verifique se o arquivo de importação está formatado corretamente:
- Inclui a linha de cabeçalho que estava no modelo de importação
- Inclui todas as colunas que estavam no modelo de importação
- A ordem das colunas é igual ao modelo de importação
- Essas colunas podem estar vazias: Id, Última Modificação, Última Modificação Por e Lat/Long  
Vamos tentar determinar a lat/long com base no endereço se esse campo estiver vazio
- A coluna Estado não pode estar vazia, essa informação é necessária  
Com base no campo Estado, os locais serão salvos como rascunho, sugerido ou programado, ou serão publicados automaticamente.

Além disso, se você incluir o ID de um local existente, ele será substituído pelas informações no arquivo de importação.

Para organizações com vários locatários, você pode exportar seus locais de um locatário e importá-los para outro. Mas você deve remover todos os dados na coluna Id antes de importar.
  
Para saber mais sobre os campos obrigatórios e recomendados, consulte [Adicionar um local](add-a-location.md).

  

