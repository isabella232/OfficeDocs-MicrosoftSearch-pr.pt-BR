---
title: Personalizar a página de pesquisa da Microsoft
ms.author: anfowler
author: adefowler
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Adicionar verticais de pesquisa e personalizar os resultados da pesquisa
ms.openlocfilehash: 87b394847281e43683f2ed9dfd42d19aa103d3e2
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949560"
---
# <a name="customize-the-microsoft-search-page"></a>Personalizar a página de pesquisa da Microsoft

Criando verticais de pesquisa e tipos de resultados você pode personalizar os resultados de pesquisa que são mostrados para os usuários quando eles pesquisam no **SharePoint**, no **Office.com** e **no Microsoft Search no Bing** . Os verticais facilitam para os usuários a localização das informações que têm permissão para ver.  Por exemplo, você pode criar uma pesquisa vertical para dados de análise de marketing do software de terceiros para seus usuários no departamento de marketing. Você também pode definir tipos de resultados e personalizar o layout desses dados.  

Você pode criar verticais e tipos de resultado nesses níveis: 

- Nível da organização – quando você adiciona um vertical no nível da organização, ele aparece na página de resultados da pesquisa quando os usuários pesquisam a página inicial do SharePoint, no Office.com e no Bing.com. 
- Nível de site – por exemplo, você pode querer permitir que seus funcionários de atendimento ao cliente pesquisem incidentes de "gravidade 1" diretamente do site do SharePoint do departamento. 

## <a name="whats-a-search-vertical"></a>O que é uma pesquisa vertical?

Na parte superior da página de resultados de pesquisa da Microsoft, há uma linha de guias, que são verticais de pesquisa. Uma vertical de pesquisa mostra os resultados de determinado tipo ou de determinado conteúdo, por exemplo, somente arquivos ou notícias. Por padrão, a pesquisa da Microsoft mostra os verticais todos, pessoas, arquivos, sites e notícias.  

Você pode adicionar verticais de pesquisa que são relevantes para sua organização. Eles serão exibidos na página de resultados da pesquisa da Microsoft no SharePoint, no Office.com e no Bing.  Por exemplo, você pode criar um vertical para o conteúdo relacionado ao marketing e outro para vendas, com base no tipo de informação que cada grupo deverá ter. Você pode adicionar Verticals para mostrar resultados apenas do conteúdo indexado via conectores.  

**Isenção de responsabilidade:** Os tipos de resultados e verticais estão atualmente em visualização como parte da visualização do Microsoft Connectors. Você não pode criar uma vertical para o conteúdo que reside no SharePoint ou de conteúdo indexado pelo conector FileShare. Para saber mais sobre a visualização, confira [visualização de conectores](connectors-preview.md). Para participar da visualização, você deve primeiro enviar o [formulário de inscrição prévia dos conectores do Microsoft Graph](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbRxWYgu82J_RFnMMATAS6_chUNVYwNU1CMDNZUDBSSDZKWVo2RDJDRjRLQi4u).

## <a name="things-to-consider"></a>Considerações a serem consideradas...

Antes de começar, certifique-se de que o conector tenha sido indexado. Pode levar até 48 horas, dependendo do tamanho do arquivo.

Você não pode criar uma vertical para o conteúdo que reside no SharePoint ou de conteúdo indexado pelo conector FileShare. Saiba como indexar conteúdo (link para a documentação do conector).

Em um alto nível, há três etapas principais para adicionar um vertical. 

1. Criar o vertical – nesta etapa, você definirá o nome vertical, a fonte de conteúdo e o escopo do conteúdo a ser pesquisado. 
2. Defina a aparência dos resultados para esta vertical.  
3. Habilitar a vertical (para ser exibida) da página de lista vertical.   

## <a name="step-1-create-the-search-vertical"></a>ETAPA 1: criar a pesquisa vertical

Depois de iniciar o assistente, você será orientado nas etapas para definir o nome vertical, a fonte de conteúdo e o escopo do conteúdo que pesquisará. A vertical é criada em um estado desabilitado. Você habilitará a vertical mais tarde.

Você pode usar um conjunto limitado da [linguagem de consulta de palavra-chave (KQL)](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) para restringir o escopo e a página mostra listar as propriedades disponíveis para você. Recomendamos o uso de palavras-chave de texto livre e restrições de propriedade com operadores booleanos para a criação do KQL 

### <a name="create-a-vertical-at-the-organization-level"></a>Criar uma vertical no nível da organização

Para criar o vertical no Microsoft Search no SharePoint Home, Bing ou Office.com, siga estas etapas:

1. No centro de administração do Microsoft 365, vá para **configurações** > **** > **verticais**de pesquisa da Microsoft.
1. Selecione **Adicionar** para começar.  

### <a name="create-a-vertical-at-the-site-level"></a>Criar uma vertical no nível do site

1. No site do SharePoint em que você deseja criar a vertical, vá para **configurações**.
1. Selecione **informações do site**e, em seguida, **exiba todas as configurações do site**.
1. Procure a seção **Microsoft Search** e, em seguida, selecione **Configurar a pesquisa da Microsoft para este conjunto de sites**.
1. No painel de navegação, vá para **experiência personalizada**e, em seguida, selecione a guia **verticais** .
1. Para adicionar uma vertical, selecione **Adicionar**. <br>
OU <br>Para editar uma vertical, selecione-a na lista.

Lembre-se de que as verticais são criadas em um estado desabilitado. Você ainda precisará habilitá-los para que os usuários possam ver as verticais.

## <a name="step-2-create-the-result-types"></a>ETAPA 2: criar os tipos de resultado

Você pode definir como os resultados são exibidos na vertical criando o layout usando tipos de resultados. O layout de resultado permite que você mostre informações importantes diretamente nos resultados da pesquisa, para que os usuários não precisem clicar em cada resultado para ver se encontraram o que estão procurando.

O tipo do resultado de pesquisa é uma função que faz com que diferentes tipos de resultados de pesquisa sejam exibidos de diferentes maneiras. Ele consiste no seguinte:

- *Uma ou mais condições* para comparar cada resultado de pesquisa, como a fonte de conteúdo do resultado da pesquisa.  
- Um *layout de resultado* a ser usado para resultados de pesquisa que atendam às condições. O layout de resultado controla a forma como todos os resultados que atendem às condições aparecem e se comportam em uma página de resultados de pesquisa.

**Você deve criar pelo menos um tipo de resultado para que os resultados sejam exibidos na vertical.** Você pode criar vários tipos de resultados para cada vertical, permitindo que você use diferentes layouts para diferentes tipos de resultados. Por exemplo, você pode personalizar os incidentes de "gravidade 1" para ter cores mais proeminentes e uma fonte maior em comparação aos incidentes de "gravidade 3". 

 Depois de iniciar o assistente, você será orientado pelas etapas para definir o nome, a fonte de conteúdo e as condições para o tipo de resultado. Você pode definir a prioridade do tipo de resultado no modo de exibição de lista. 
  
### <a name="create-a-result-type-at-the-organization-level"></a>Criar um tipo de resultado no nível da organização

1. No centro de administração do Microsoft 365, vá para **configuração** > **do Microsoft Search**e selecione **tipo de resultado**.
1. Para adicionar um **tipo de resultado**, selecione **Adicionar**. Para editar um tipo de resultado, selecione o tipo de resultado na lista relevante.
 
### <a name="create-a-results-type-at-the-site-level"></a>Criar um tipo de resultados no nível do site

1. No site do SharePoint onde você deseja criar o tipo de resultado, vá para **configurações**.
1. Selecione **informações do site**e, em seguida, **exiba todas as configurações do site**. 
1. Procure a seção Microsoft Search e, em seguida, selecione **Configurar a pesquisa da Microsoft para este conjunto de sites**.
1. No painel de navegação, vá para **experiência personalizada**e selecione guia tipo de resultado.
1. Para adicionar um tipo de resultado, selecione **Adicionar**. <br> OU <br>Para editar um tipo de resultado, selecione o tipo de resultado na lista.

### <a name="view-the-vertical-after-enabling"></a>Exibir a vertical após habilitar

Depois de habilitar a vertical, poderá demorar um pouco antes de poder visualizá-la.
Se você quiser aguardar depois de habilitá-lo, você pode acrescentar *cacheClear = true* à URL no SharePoint e Office.com para exibir a vertical imediatamente.

## <a name="troubleshooting"></a>Solução de problemas

Veja a seguir uma lista de problemas comuns que você pode encontrar e ações para corrigi-los.


|Error  |Action  |
|---------|---------|
|Vejo um erro "algo deu errado" na vertical|   Os tipos vertical e resultado são necessários para concluir a configuração. Verifique se você criou ambos para a mesma fonte de conteúdo.      |
|Por que não vejo o layout do resultado embora eu tenha criado um? | Leva alguns minutos para que os tipos de resultados sejam usados, pois essas configurações são geralmente armazenadas em cache. Aguarde alguns minutos e tente novamente        |
|Não vejo nenhuma fonte de conteúdo na página de tipo vertical ou de resultado     |      Verifique se você configurou conectores e dados indexados   |



## <a name="next-steps"></a>Próximas etapas
[ETAPA 3: personalizar o layout dos resultados](customize-results-layout.md)