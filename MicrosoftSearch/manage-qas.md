---
title: Gerenciar P e R
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
description: Encontre e atualize as respostas individualmente ou use as ferramentas da Pesquisa da Microsoft disponíveis para editar todas elas de uma só vez
ms.openlocfilehash: ee239aa73d4e650289f39d33c63c3e2df4f100cc
ms.sourcegitcommit: 3e91a6e70b48a0100adfed1b62ba79f2fd1735d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2019
ms.locfileid: "33968464"
---
# <a name="manage-qas"></a>Gerenciar P e R

> [!IMPORTANT]
> As configurações da Pesquisa da Microsoft no Bing agora estão disponíveis no centro de administração do Microsoft 365. Comece por [atribuir administradores de pesquisa](https://docs.microsoft.com/pt-BR/microsoftsearch/setup-microsoft-search#step-2-assign-search-admin-and-search-editor) ao seu centro de administração.
    
Ao longo do tempo, talvez seja necessário atualizar o status e o conteúdo de um item de P e R para mantê-lo relevante.
  
## <a name="filter-qas"></a>Filtrar perguntas e respostas

Use a opção de filtro no canto superior direito da página Perguntas e Respostas para localizar as perguntas e respostas por data e quem as modificou. Por exemplo, defina o controle deslizante para 30 dias e escolha um administrador ou editor para ver a lista de P e R que você criou ou modificou naquele momento.
  
## <a name="change-qa-content-or-settings"></a>Alterar o conteúdo e as configurações de P e R

1. Acesse o Portal de Administração da Pesquisa da Microsoft
    
2. No painel de navegação, clique em **P e R**
    
3. Para localizar um item de perguntas e respostas, pesquise, filtre ou clique no status de um item de perguntas e respostas para restringir os resultados
    
4. Para alterar ou atualizar um item de perguntas e respostas, clique no título
    
5. Faça alterações ou atualizações no conteúdo ou configurações e visualize como ficará sua aparência
    
6. Clique em **Salvar**
    
## <a name="bulk-export-and-edit-qas"></a>Exporte e edite itens de perguntas e respostas em massa

Nunca edite dados nesses campos:
  
- Id
    
- Última Modificação
    
- Última Modificação Por
    
ID é um identificador exclusivo para cada item de P e R e nunca deve ser editado. Os campos Última Modificação e Última Modificação Por só devem ser usados para classificar e localizar P e R.
  
1. Se quiser exportar um subconjunto de itens de P e R, filtre-os
    
2. No canto superior direito da página Perguntas e Respostas, clique em **Exportar**
    
3. Salve ou abra o arquivo .csv
    
4. Edite os dados em qualquer um destes campos:
    
   - Pergunta
    
   - URL
      
   - Palavras-chave
    
   - Estado
    
   - Descrição da resposta
    
   - Palavras-chave Reservadas
    
   - Data de Início
    
   - Data de Término
    
   - País/Região
    
   - Grupos
    
   - Sistema Operacional do dispositivo&amp;
    
   - Variações Direcionadas
    
5. Salve o arquivo .csv

    O arquivo .csv deve ser salvo como um arquivo CSV UTF-8; outros tipos de arquivo e/ou codificações podem causar erros de importação
    
6. No canto superior direito da página P e R, clique em **Importar**
    
7. No painel Importar P e R, clique em **Procurar** e selecione o arquivo .csv editado 
    
8. Clique em **Importar**
    
Se os dados necessários estiverem ausentes ou forem inválidos, você receberá um erro. Dependendo do erro, pode ser gerado um arquivo de registro com mais informações sobre quais linhas e colunas precisam ser corrigidas. Faça as edições necessárias e tente importar o arquivo novamente.
  
> [!NOTE]
> Até que todos os erros sejam resolvidos, não será possível criar ou editar nenhum item de P e R. 
  
Nem todos os campos são necessários e os campos necessários variam dependendo do estado das P e R. Com base no campo de estado, as P e R serão salvas como rascunho, sugeridas, programadas, ou serão publicadas automaticamente. Descubra mais sobre os campos necessários e recomendados em [Criar P e R](create-qas.md).

  

