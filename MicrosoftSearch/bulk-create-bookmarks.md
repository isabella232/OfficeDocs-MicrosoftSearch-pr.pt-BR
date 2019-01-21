---
title: Em massa criar indicadores
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
description: Criar muitos de indicadores de uma só vez com as ferramentas de importação para o portal de administração de pesquisa da Microsoft
ms.openlocfilehash: e5af84daf2619e58e2cb3299de1b9d9df9966673
ms.sourcegitcommit: bf52cc63b75f2e0324a716fe65da47702956b722
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/18/2019
ms.locfileid: "29378375"
---
# <a name="bulk-create-bookmarks"></a>Em massa criar indicadores

Fazer o download e usar o modelo em massa. csv criar, editar e salvar indicadores. Em massa indicadores existentes de editar, exportá-los a partir do portal de administração, faça as edições necessárias e importá-los.
  
1. No canto superior direito da seção indicadores, clique em **Importar**
    
2. Clique em **baixar o modelo de indicadores (. csv)**
    
3. Salve e abra o arquivo. csv
    
4. Adicione o conteúdo do indicador e configurações e salve o arquivo
    
5. No canto superior direito da seção indicadores, clique em **Importar**
    
6. No painel de indicadores de importação, clique em **Procurar** e navegue até o arquivo. csv que você deseja importar 
    
7. Clique em **Importar**
    
Você receberá um erro se todos os dados necessários estão ausente ou inválido. Dependendo do erro, um arquivo de log pode ser gerado com mais informações sobre as linhas e colunas que precisam ser corrigido. Faça qualquer edições necessárias e tente importar o arquivo novamente.
  
Observação: Até que todos os erros forem resolvidos, você não pode criar ou editar os indicadores.
  
Os campos nos modelos de indicador de importação e exportação são os mesmos. Você pode exportar, editar em massa e importar as edições ou iniciar com um modelo vazio para em massa criar novos indicadores.
  
Nem todos os campos são necessários e campos obrigatórios variam dependendo do estado do indicador. Com base no campo de estado, indicadores também são salvos como rascunho, sugerido, agendadas ou eles serão publicados automaticamente. Saiba mais sobre campos necessários e recomendados em [criar indicadores](create-bookmarks.md).

  

