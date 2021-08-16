---
title: Personalizar a Pesquisa da Microsoft página
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
ms.openlocfilehash: 440b9afbbeb4c4cd86b2b9f67443e644c36ce042
ms.sourcegitcommit: 8ac77db22002d47bb461222b81b7cfc1c15a72fb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2021
ms.locfileid: "58340074"
---
# <a name="customize-the-search-results-page"></a>Personalizar a página de resultados da pesquisa

Você pode criar tipos de resultados e verticais de pesquisa para personalizar os resultados de pesquisa que os usuários veem quando pesquisam no Microsoft [SharePoint,](https://sharepoint.com/) [Microsoft Office](https://office.com)e Pesquisa da Microsoft em [Bing](https://bing.com). As verticais facilitam que os usuários encontrem as informações que eles têm permissão para ver. Por exemplo, você pode criar uma pesquisa vertical para dados de análise de marketing de software de terceiros para seus usuários no departamento de marketing. Você também pode definir tipos de resultados e personalizar o layout desses dados.  

Você pode criar tipos de resultados e verticais nesses níveis:

- **Nível da** organização – quando você adiciona uma vertical no nível da organização, ela aparece na página de resultados da pesquisa quando os usuários pesquisam [na](https://sharepoint.com/) página inicial do SharePoint, no [Office](https://office.com)ou no [Bing](https://bing.com).
- **Nível do** site – Por exemplo, talvez você queira permitir que seus funcionários do serviço de atendimento ao cliente pesquisem incidentes de Gravidade *1* diretamente do site de segurança SharePoint departamento.

## <a name="search-verticals-explained"></a>Pesquisas verticais explicadas

Na parte superior da página Pesquisa da Microsoft resultados, há uma linha de guias. Estas são as verticais de pesquisa. Uma pesquisa vertical mostra apenas resultados de um determinado tipo ou de determinado conteúdo. Exemplos são **Arquivos** ou **Notícias.** Por padrão, Pesquisa da Microsoft mostra as verticais **Todos**, **Pessoas,** **Arquivos,** **Sites** e **Notícias**.  

Você pode adicionar verticais de pesquisa relevantes à sua organização. Elas serão exibidas na página Pesquisa da Microsoft resultados em [SharePoint,](https://sharepoint.com/) [Office](https://Office.com)e [Bing](https://bing.com). Por exemplo, você pode criar uma vertical para conteúdo relacionado ao marketing e outra para vendas, com base no tipo de informação que cada grupo precisa. Você pode adicionar verticais para mostrar resultados somente de conteúdo indexado por meio de conectores.  

### <a name="multiple-connections-in-a-vertical"></a>Várias conexões em um vertical

Uma pesquisa vertical agora pode surgir resultados de várias fontes de conector. Isso oferece maior flexibilidade ao projetar sua página de resultados de pesquisa. A experiência administrativa existente da instalação vertical permite selecionar várias conexões na etapa "Fonte de Conteúdo".
Se você nomear com precisão quantos rótulos semânticos for possível, essa experiência será aprimorada. Você pode adicionar rótulos semânticos na definição e ingestão do esquema.

[Aqui](configure-connector.md#step-6-assign-property-labels) estão informações adicionais sobre como criar e gerenciar rótulos semânticos.

> [!NOTE]
> Várias conexões em uma vertical estão atualmente em visualização. Para obter mais informações sobre visualização, consulte [Conectores recursos de visualização](connectors-overview.md#what-are-the-preview-features).

### <a name="things-you-should-know"></a>Coisas que você deve saber

1. Uma conexão pode ser adicionada como uma fonte de conteúdo somente em uma vertical. Não é permitido reutilizar conexões em várias verticais.
2. Se você precisar configurar uma consulta para uma pesquisa vertical onde várias fontes de conexão foram adicionadas, as propriedades de origem comuns devem ser usadas para criar uma consulta desse tipo.

## <a name="things-to-consider"></a>Itens a considerar

Antes de iniciar, certifique-se de que o conector foi indexado. Isso pode levar até 48 horas, dependendo do tamanho do arquivo.

Não é possível criar uma vertical para conteúdo que reside em [SharePoint](https://sharepoint.com/).

Há três etapas básicas para adicionar um vertical:

1. Crie o vertical. Nesta etapa, você define o nome da vertical, a fonte de conteúdo e o escopo do conteúdo a ser pesquisado.
2. Defina como serão os resultados dessa vertical.  
3. Habilita a vertical (a ser exibida) na página de lista vertical.

## <a name="step-1-create-the-search-vertical"></a>ETAPA 1: Criar a pesquisa vertical

Depois de iniciar o assistente, você é orientado pelas etapas para definir o nome vertical, a fonte de conteúdo e o escopo do conteúdo a ser pesquisado. A vertical é criada em um estado desabilitado. Você a habilitará mais tarde.

Você pode usar um conjunto limitado de [KQL (Keyword Query Language) para](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) restringir o escopo. Esta página lista as propriedades disponíveis. Recomendamos que você use palavras-chave de texto livre e restrições de propriedade com operadores boolianas para criar o KQL.
O KQL também dá suporte ao uso de [variáveis de consulta](#profile-query-variables) de perfil para ajustar os resultados na vertical.

### <a name="create-a-vertical-at-the-organization-level"></a>Criar uma vertical no nível da organização

Para criar a vertical no Pesquisa da Microsoft [em](https://sharepoint.com/) [SharePoint,](https://office.com)Office , ou [Bing](https://bing.com), siga estas etapas:

1. No [Centro de administração do Microsoft 365,](https://admin.microsoft.com)vá para [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Selecione **Adicionar** para começar.  

### <a name="create-a-vertical-at-the-site-level"></a>Criar uma vertical no nível do site

1. No site [SharePoint](https://sharepoint.com/) onde você deseja verticais, vá para **Configurações**.
2. Selecione **Informações do site** e, em **seguida, Exibir todas as configurações do site**.
3. Procure a seção **Pesquisa da Microsoft** e selecione Configurar Pesquisa da Microsoft **para este conjunto de sites.**
4. No painel de navegação, vá para **Experiência personalizada** e selecione a **guia Verticals.**
5. Para adicionar um vertical, selecione **Adicionar**.
  Ou, para editar uma vertical, selecione-a na lista.

Lembre-se de que as verticais são criadas em um estado desabilitado. Eles devem estar habilitados para que os usuários possam vê-los.

## <a name="step-2-create-the-result-types"></a>ETAPA 2: Criar os tipos de resultados

Você pode definir como os resultados são exibidos na vertical, projetando o layout usando tipos de resultados. O layout de resultados permite que você mostre informações importantes diretamente nos resultados da pesquisa, para que os usuários não tenham que selecionar cada resultado para ver se encontraram o que estão procurando.

### <a name="default-search-result-layout"></a>Layout padrão do resultado da pesquisa

Um layout de resultado de pesquisa  padrão será mostrado para conteúdo do Conector se os rótulos e a propriedade **de** conteúdo foram mapeados corretamente para as propriedades de origem no momento da configuração do conector. O título **do rótulo** é o rótulo mais importante. É altamente **recomendável que** você tenha uma propriedade atribuída a esse rótulo para usar o layout de resultado da pesquisa padrão.

### <a name="create-your-own-result-type"></a>Criar seu próprio tipo de resultado

Você pode optar por criar seu próprio layout de resultado de pesquisa e substituir o layout padrão do resultado da pesquisa criando um **tipo de resultado**. O tipo do resultado de pesquisa é uma função que faz com que diferentes tipos de resultados de pesquisa sejam exibidos de diferentes maneiras. Ele consiste no seguinte:

- **Uma ou mais condições para** comparar cada resultado de pesquisa, como a fonte de conteúdo do resultado da pesquisa.  
- Um **layout de resultado** a ser usado para resultados de pesquisa que atendem às condições. O layout resultante controla a forma como todos os resultados que atendem às condições aparecem e se comportam em uma página de resultados de pesquisa.

**Se o mapeamento apropriado não for feito para mostrar o layout padrão do resultado da pesquisa, você deve criar pelo menos um tipo de resultado para que os resultados seja exibidos na vertical.** Você pode criar vários tipos de resultados para cada vertical, o que permite usar layouts diferentes para diferentes tipos de resultados. Por exemplo, você pode personalizar *incidentes de* Gravidade 1 para ter cores mais proeminentes e uma fonte maior em comparação com incidentes de Gravidade *3.*

Depois de iniciar o assistente, você é orientado pelas etapas para definir o nome, a fonte de conteúdo e as condições do tipo de resultado. Você pode definir a prioridade do tipo de resultado no exibição de lista.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Criar um tipo de resultado no nível da organização

1. Na [Centro de administração do Microsoft 365,](https://admin.microsoft.com)vá para [**Tipos de resultado**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).
2. Para adicionar um **tipo de resultado,** selecione **Adicionar**. Para editar um tipo de resultado, selecione o tipo de resultado na lista relevante.

### <a name="create-a-results-type-at-the-site-level"></a>Criar um tipo de resultados no nível do site

1. No site [SharePoint](https://sharepoint.com/) onde você deseja criar o tipo de resultado, vá para **Configurações**.
2. Selecione **Informações do site** e, em **seguida, Exibir todas as configurações do site**.
3. Procure a seção Pesquisa da Microsoft e selecione Configurar Pesquisa da Microsoft **para este conjunto de sites.**
4. No painel de navegação, vá para **Experiência personalizada** e selecione Guia **Tipo de** resultado.
5. Para adicionar um tipo de resultado, selecione **Adicionar**.  Ou, para editar um tipo de resultado, selecione o tipo de resultado na lista.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>ETAPA 3: Exibir a vertical depois de habilitada

Depois de habilitar a vertical, levará algumas horas para poder exibi-la. Se você não quiser esperar depois de habilita-lo, você pode anexar **cacheClear=true** à URL no [SharePoint](https://sharepoint.com/) e [Office](https://office.com) para exibir a vertical imediatamente. Para [Bing](https://bing.com), anexar&**features=uncachedVerticals** à URL vertical de Trabalho para exibir as verticais imediatamente.

> [!NOTE]
> As verticais adicionadas não estarão visíveis SharePoint [e](https://sharepoint.com/) [Office](https://office.com) quando exibidas de navegadores da Web móveis.

## <a name="profile-query-variables"></a>Variáveis de consulta de perfil

As variáveis de consulta são usadas na seção de consulta KQL de uma vertical para fornecer dados dinâmicos como uma entrada para a consulta de uma vertical. Você pode usar as variáveis de consulta de perfil para tornar os resultados da pesquisa contextuais para o usuário in-locar. As variáveis de consulta de perfil buscam valores do perfil do usuário [de entrada.](/graph/api/resources/profile?view=graph-rest-beta)

Por exemplo, se você quiser criar uma vertical "Tíquetes" onde um usuário inscreveu pode pesquisar por tíquetes de suporte atribuídos a eles, você pode especificar a seguinte consulta na seção "Consulta" durante a criação vertical na página de administração.  

**AssignedTo:{Profile.accounts.userPrincipalName}**

Isso restringirá os resultados da pesquisa para mostrar apenas os itens em que o destinatário é o usuário que está executando a pesquisa.

[O recurso Profile](/graph/api/resources/profile?view=graph-rest-beta) expõe propriedades como coleções. Por exemplo, informações relacionadas a endereços de email são expostas por meio de coleta de emails, posições de trabalho como conjunto de posições e assim por diante. Todas as propriedades disponíveis no perfil de usuário, que têm o AAD como o tipo de origem, são expostas como variáveis de consulta.

Considere um usuário que tenha 3 endereços de email disponíveis no conjunto de emails, conforme mostrado abaixo.

```json
"emails": [{ 

        "address": "Megan.Bowen@contoso.com",
        "id": "xyz", 
        "source": { 
            "CreatedBy": "xyz", 
            "CreatedOn": "2222", 
            "Type": "official" 
        },
        "type": "main" 
    }, { 
        "address": "meganb@hotmail.com",
        "id": "abc", 
        "source": { 
            "CreatedBy": "abc",
            "CreatedOn": "3333", 
            "Type": "non-official",
        },
        "type": "work"
    }, { 
        "address": "meganb@outlook.com",
        "id": "pqr", 
        "source": { 
            "CreatedBy": "pqr", 
            "CreatedOn": "4444", 
            "Type": "personal" 
        },
        "type": "personal" 
    } 
] 
```

- A consulta **MyProperty: {Profile.emails.address}** resolverá para MyProperty: "Megan.Bowen@contoso.com".  

- Se desejar resolver todos os valores do atributo address, você terá que usar a sintaxe de expansão de vários valores. A consulta **{| MyProperty:{Profile.emails.address}}** resolverá para ((MyProperty:"Megan.Bowen@contoso.com") OR (MyProperty: "meganb@hotmail.com") OR (MyProperty:"meganb@outlook.com"))  

O operador "|" deve ser usado para resolver variáveis de vários valores. Para obter mais exemplos de expansão de perfil, consulte a tabela abaixo.

| #         | Sintaxe |  Valor retornado  |
| --------- | ------ | --- |
| 1     | MyProperty:{Profile.emails.address}  |   "Megan.Bowen@contoso.com"  |
| 2 | MyProperty:{Profile.emails}   |    {Profile.emails} Isso não será resolvido porque os emails são um objeto.|
| 3     | {? MyProperty:{Profile.emails}}  |  Isso não será resolvido porque os emails são um objeto. O "?" o operador ignora as variáveis de consulta que não são resolvidas. Essa variável será removida quando passada para baixo na pilha de consulta.   |
| 4  | {&#124;MyProperty: {Profile.emails.source.Type}}    |  ((MyProperty:"official") OR (MyProperty:"non-official") OR (MyProperty:"personal"))    |

> [!NOTE]
>
> - As variáveis de consulta de perfil só têm suporte para verticais personalizadas usando [um conector](connectors-overview.md) como fonte de conteúdo.
> - As variáveis de consulta de perfil são definidas na seção "Consulta" do [processo de configuração vertical](customize-search-page.md#step-1-create-the-search-vertical).
> - As variáveis de consulta de perfil estão atualmente em visualização. Para obter mais informações sobre visualização, consulte [Conectores recursos de visualização](connectors-overview.md#what-are-the-preview-features).

## <a name="troubleshooting"></a>Solução de problemas

Aqui está uma lista de problemas comuns que você pode encontrar e ações para corrigi-los.

|Erro  |Ação  |
|---------|---------|
| Vejo uma mensagem de erro "Algo deu errado" na vertical. | Os tipos vertical e de resultado são necessários para concluir a instalação. Certifique-se de ter criado ambos para a mesma fonte de conteúdo. |
| Não vejo meu layout de resultado, embora tenha criado um. | Leva alguns minutos porque essas configurações geralmente são armazenadas em cache. Aguarde alguns minutos e tente novamente.        |
| Não vejo fontes de conteúdo na página vertical ou do tipo de resultado. | Certifique-se de ter configurado conectores e dados indexados.   |

## <a name="next-steps"></a>Próximas etapas

[Personalizar o layout de resultados](customize-results-layout.md)
