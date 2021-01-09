---
title: Personalizar a página da Pesquisa da Microsoft
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Adicionar verticais de pesquisa e personalizar resultados de pesquisa
ms.openlocfilehash: 4896fdb9923c93602acc48c2360039d512e4d72e
ms.sourcegitcommit: a86265684871da86562a76c4961d0a6c1869f517
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790327"
---
# <a name="customize-the-search-results-page"></a>Personalizar a página de resultados da pesquisa

Você pode criar pesquisas verticais e tipos de resultados para personalizar os resultados da pesquisa que os usuários veem quando pesquisam no Microsoft [SharePoint,](https://sharepoint.com/) [no Microsoft Office](https://office.com)e na Pesquisa da Microsoft no [Bing.](https://bing.com) Verticals facilitam para os usuários encontrar as informações que eles têm permissão para ver. Por exemplo, você poderia criar uma pesquisa vertical para dados de análise de marketing de software de terceiros para seus usuários no departamento de marketing. Você também pode definir tipos de resultados e personalizar o layout para esses dados.  

Você pode criar verticais e tipos de resultados nestes níveis:

- **Nível da** organização – Quando você adiciona uma vertical no nível da organização, ela aparece na página de resultados da pesquisa quando os usuários pesquisam na página inicial do [SharePoint,](https://sharepoint.com/) no [Office](https://office.com)ou no [Bing.](https://bing.com)
- **Nível do** site – Por exemplo, talvez você queira permitir que seus funcionários de atendimento ao cliente pesquisem incidentes de Severidade *1* diretamente do site do SharePoint do departamento.

## <a name="search-verticals-explained"></a>Pesquisas verticais explicadas

Na parte superior da página de resultados da Pesquisa da Microsoft, há uma linha de guias. Estas são as verticais de pesquisa. Uma pesquisa vertical mostra apenas os resultados de um determinado tipo ou de determinado conteúdo. Exemplos são **Arquivos** ou **Notícias.** Por padrão, a Pesquisa da Microsoft mostra as verticais **All**, **People**, **Files**, **Sites** e **Notícias.**  

Você pode adicionar verticais de pesquisa relevantes à sua organização. Eles aparecerão na página de resultados da Pesquisa da Microsoft [no SharePoint,](https://sharepoint.com/) [Office](https://Office.com)e [Bing.](https://bing.com) Por exemplo, você pode criar uma vertical para conteúdo relacionado ao marketing e outra para vendas, com base no tipo de informação que cada grupo precisa. Você pode adicionar verticais para mostrar resultados somente do conteúdo indexado por meio de conectores.  

### <a name="multiple-connections-in-a-vertical"></a>Várias conexões em uma vertical

Uma pesquisa vertical agora pode mostrar resultados de várias fontes de conector. Isso oferece maior flexibilidade ao projetar sua página de resultados de pesquisa. A experiência administrativa existente da instalação vertical permite que você selecione várias conexões na etapa "Fonte de Conteúdo".
Se você indicar com precisão o máximo possível de rótulos semânticos, essa experiência será aprimorada. Você pode adicionar rótulos semânticos na definição e ingestão do esquema.

[Aqui](configure-connector.md#step-5-assign-property-labels) estão informações adicionais sobre como criar e gerenciar rótulos semânticos.

### <a name="things-you-should-know"></a>Coisas que você deve saber

1. Uma conexão só pode ser adicionada como uma fonte de conteúdo em uma vertical. Não é permitido reutilizar conexões em vários verticais.
2. Se você precisar configurar uma consulta para uma pesquisa vertical onde várias fontes de conexão foram adicionadas, as propriedades de origem comuns devem ser usadas para criar uma consulta desse tipo.

## <a name="things-to-consider"></a>Itens a considerar

Antes de começar, certifique-se de que o conector foi indexado. Isso pode levar até 48 horas, dependendo do tamanho do arquivo.

Não é possível criar uma vertical para o conteúdo que reside no [SharePoint.](https://sharepoint.com/)

Há três etapas básicas para adicionar uma vertical:

1. Crie a vertical. Nesta etapa, você define o nome vertical, a fonte de conteúdo e o escopo do conteúdo a ser pesquisado.
2. Defina a aparência dos resultados para essa vertical.  
3. Habilita a vertical (a ser exibida) na página de lista vertical.

## <a name="step-1-create-the-search-vertical"></a>ETAPA 1: Criar a pesquisa vertical

Depois de iniciar o assistente, você é orientado pelas etapas para definir o nome vertical, a fonte de conteúdo e o escopo do conteúdo a ser pesquisado. A vertical é criada em um estado desabilitado. Você o habilita mais tarde.

Você pode usar um conjunto limitado de [KQL (Keyword Query Language)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) para restringir o escopo. Esta página lista as propriedades que estão disponíveis. Recomendamos que você use palavras-chave de texto livre e restrições de propriedade com operadores boolários para criar o KQL.

### <a name="create-a-vertical-at-the-organization-level"></a>Criar uma vertical no nível da organização

Para criar a vertical na pesquisa da Microsoft na página base do [SharePoint,](https://sharepoint.com/) [Office](https://office.com)ou [Bing,](https://bing.com)siga estas etapas:

1. No centro [de administração do Microsoft 365,](https://admin.microsoft.com)vá para [**Verticais.**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals)
2. Selecione **Adicionar** para começar.  

### <a name="create-a-vertical-at-the-site-level"></a>Criar uma vertical no nível do site

1. No site [do SharePoint](https://sharepoint.com/) onde você deseja a vertical, vá para **Configurações**.
2. Selecione **Informações do site** **e, em seguida, Exibir todas as configurações do site.**
3. Procure a seção **Pesquisa da Microsoft** e selecione Configurar a Pesquisa da Microsoft para este conjunto de **sites.**
4. No painel de navegação, vá para **Experiência personalizada** e selecione a **guia Verticals.**
5. Para adicionar um vertical, selecione **Adicionar**.
  Ou, para editar uma vertical, selecione-a na lista.

Lembre-se de que as verticais são criadas em um estado desabilitado. Eles devem ser habilitados para que os usuários possam vê-los.

## <a name="step-2-create-the-result-types"></a>ETAPA 2: Criar os tipos de resultados

Você pode definir como os resultados são exibidos na vertical projetando o layout usando tipos de resultado. O layout do resultado permite que você mostre informações importantes diretamente nos resultados da pesquisa, para que os usuários não tenham que selecionar cada resultado para ver se descobriram o que estão procurando.

### <a name="default-search-result-layout"></a>Layout de resultado de pesquisa padrão

Um layout de resultado de pesquisa  padrão  será mostrado para o conteúdo do Conector se os rótulos e a propriedade de conteúdo foram mapeados corretamente para as propriedades de origem no momento da configuração do conector. O título **do rótulo** é o rótulo mais importante. É altamente **recomendável que** você tenha uma propriedade atribuída a esse rótulo para usar o layout de resultado de pesquisa padrão.

### <a name="create-your-own-result-type"></a>Criar seu próprio tipo de resultado

Você pode optar por criar seu próprio layout de resultado de pesquisa e substituir o layout de resultado de pesquisa padrão criando um tipo **de resultado.** O tipo do resultado de pesquisa é uma função que faz com que diferentes tipos de resultados de pesquisa sejam exibidos de diferentes maneiras. Ele consiste no seguinte:

- **Uma ou mais condições para** comparar cada resultado de pesquisa, como a fonte de conteúdo do resultado da pesquisa.  
- Um **layout de resultado** a ser usado para resultados de pesquisa que atendem às condições. O layout de resultado controla a maneira como todos os resultados que atendem às condições aparecem e se comportam em uma página de resultados de pesquisa.

**Se o mapeamento apropriado não for feito para mostrar o layout de resultado de pesquisa padrão, você deve criar pelo menos um tipo de resultado para que os resultados seja exibidos na vertical.** Você pode criar vários tipos de resultados para cada vertical, o que permite que você use layouts diferentes para diferentes tipos de resultados. Por exemplo, você pode personalizar incidentes de Severidade *1* para ter cores mais destacadas e uma fonte maior em comparação aos incidentes de Gravidade *3.*

Depois de iniciar o assistente, você será orientado pelas etapas para definir o nome, a fonte de conteúdo e as condições para o tipo de resultado. Você pode definir a prioridade do tipo de resultado na exibição de lista.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Criar um tipo de resultado no nível da organização

1. No centro [de administração do Microsoft 365,](https://admin.microsoft.com)vá para Tipos de [**resultado.**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes)
2. Para adicionar um **tipo de resultado,** selecione **Adicionar**. Para editar um tipo de resultado, selecione o tipo de resultado na lista relevante.

### <a name="create-a-results-type-at-the-site-level"></a>Criar um tipo de resultados no nível do site

1. No site [do SharePoint](https://sharepoint.com/) onde você deseja criar o tipo de resultado, vá para **Configurações**.
2. Selecione **Informações do site** **e, em seguida, Exibir todas as configurações do site.**
3. Procure a seção Pesquisa da Microsoft e selecione **Configurar a Pesquisa da Microsoft para este conjunto de sites.**
4. No painel de navegação, vá para **Experiência personalizada e** selecione a guia Tipo **de** resultado.
5. Para adicionar um tipo de resultado, selecione **Adicionar**.  Ou, para editar um tipo de resultado, selecione o tipo de resultado na lista.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>ETAPA 3: Exibir a vertical após ela ser habilitada

Depois de habilitar a vertical, pode levar algum tempo até que você possa exibi-la. Se você não quiser esperar depois de habilita-lo, poderá anexar **cacheClear=true** à URL no [SharePoint](https://sharepoint.com/) e no [Office](https://office.com) para exibir a vertical imediatamente. Para [o Bing](https://bing.com),&**features=uncachedVerticals** à URL vertical de Trabalho para exibir as verticais imediatamente.

## <a name="troubleshooting"></a>Solução de Problemas

Aqui está uma lista de problemas comuns que você pode encontrar e ações para corrigi-los.

|Erro  |Ação  |
|---------|---------|
| Vejo uma mensagem de erro "Algo deu errado" na vertical. | Os tipos vertical e de resultado são necessários para concluir a configuração. Certifique-se de ter criado ambos para a mesma fonte de conteúdo. |
| Não vejo meu layout de resultado, embora tenha criado um. | Demora alguns minutos porque essas configurações geralmente são armazenadas em cache. Aguarde alguns minutos e tente novamente.        |
| Não vejo nenhuma fonte de conteúdo na página de tipo vertical ou de resultado. | Certifique-se de ter configurado conectores e dados indexados.   |

## <a name="next-steps"></a>Próximas etapas

[Personalizar o layout dos resultados](customize-results-layout.md)
