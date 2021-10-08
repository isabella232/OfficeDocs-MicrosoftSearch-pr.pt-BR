---
title: Gerenciar tipos de resultados
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Gerenciar tipos de resultados na página de resultados da pesquisa
ms.openlocfilehash: eb0c00cbc05f899a31cd961d89147ac63c97e82c
ms.sourcegitcommit: 02d4f91210d992da080fd39d5b60f8cf30d8f0b2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2021
ms.locfileid: "60238417"
---
# <a name="manage-result-types"></a>Gerenciar tipos de resultados

Você pode definir como os resultados da pesquisa são exibidos na página de resultados da pesquisa [projetando](customize-results-layout.md) o layout usando tipos de resultados. O layout do resultado permite que você mostre informações úteis diretamente nos resultados da pesquisa para que os usuários possam encontrar rapidamente as informações necessárias.

Tipos de conteúdo integrados, como arquivos e pessoas, têm um layout padrão que não pode ser modificado. Os tipos de resultados são usados [para Graph conteúdo de conectores.](connectors-overview.md) Quando você configura um conector com mapeamentos de propriedades, Pesquisa da Microsoft usará um layout de resultado de pesquisa padrão para os resultados da pesquisa do conector. O título *do rótulo* é o mais importante; você sempre deve ter uma propriedade atribuída a esse rótulo para usar o layout de resultado padrão. No entanto, criar um tipo de resultado personalizado para o conteúdo do conector pode tornar esses resultados mais impactáveis para seus usuários.

Ao usar conteúdo vertical e conector, você deve criar um tipo de resultado ou fazer os mapeamentos para um layout padrão. Se você não fizer isso, a vertical não exibirá nenhum resultado de pesquisa.

## <a name="understanding-result-types"></a>Noções básicas sobre tipos de resultados

Crie seu próprio [layout de resultado de pesquisa](customize-results-layout.md) e substitua o layout padrão do resultado da pesquisa criando um tipo de resultado. Um tipo de resultado de pesquisa é uma regra que faz com que tipos distintos de resultados de pesquisa sejam exibidos de forma diferente. Ele consiste nos seguintes parâmetros:

- **Uma ou mais condições**   para comparar cada resultado de pesquisa com. Exemplos de condições são fonte de conteúdo e título.
- Um **layout de resultado** a ser usado para resultados de pesquisa que atendem às   condições. O layout resultante controla como os resultados que atendem às condições aparecem na página de resultados da pesquisa.

Você pode usar vários tipos de resultados para conteúdo exibido em um vertical. Isso pode ser importante ao combinar várias fontes de conteúdo em uma única vertical. Ele também pode ser usado para um layout mais impactante, mesmo quando há apenas um tipo de conteúdo. Por exemplo, em uma vertical que exibe detalhes de incidentes, você pode personalizar incidentes de "alta gravidade" para ter mais cores proeminentes do que incidentes de "baixa gravidade". Isso pode ser feito definindo condições na propriedade "severidade" na **seção Regras.**

## <a name="create-or-update-result-types"></a>Criar ou atualizar tipos de resultados

A experiência de gerenciamento de tipo de resultado é orientada pelo assistente, você é orientado por etapas para definir o nome, a fonte de conteúdo, as regras e o layout. Os tipos de resultados podem ser personalizados no nível da organização e SharePoint site.

### <a name="manage-organization-level-result-types"></a>Gerenciar tipos de resultados no nível da organização

1. Em  [Centro de administração do Microsoft 365](https://admin.microsoft.com/), vá para a página [**Tipos de**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) resultado na seção **Personalização.**
2. Para criar um novo tipo de resultado, clique em **Adicionar** ou selecione um existente para editá-lo.
3. Depois de configurar seu tipo de resultado, você pode revisá-lo e salvá-lo.

### <a name="manage-site-level-result-types"></a>Gerenciar tipos de resultados no nível do site

1. No site do Sharepoint onde você deseja gerenciar tipos de resultados, abra o painel de configurações clicando na engrenagem.
2. Selecione **Informações do** site e selecione Exibir todas as **configurações do site.**  
3. Procure a seção Pesquisa da Microsoft e selecione **Configurar configurações de pesquisa**.
4. No painel de navegação, vá para Experiência personalizada e selecione o **tipo De resultado**.
5. Para adicionar um tipo de resultado, clique em **Adicionar**. Ou, para editar um tipo de resultado, selecione o tipo de resultado na lista.
6. Depois de modificar um tipo de resultado, você pode revisar e salvar o tipo de resultado.

## <a name="troubleshooting"></a>Solução de problemas

Aqui está uma lista de problemas comuns que você pode ver e ações para corrigi-los.

|Problema  |Ação  |
|---------|---------|
| Não vejo meu layout de resultado na página de pesquisa, embora tenha criado um. | Pode haver um atraso de alguns minutos porque essas configurações são armazenadas em cache. Aguarde alguns minutos e tente novamente.        |
| Não vejo fontes de conteúdo na página de tipo de resultado. | Certifique-se de ter configurado conectores e dados indexados.   |
