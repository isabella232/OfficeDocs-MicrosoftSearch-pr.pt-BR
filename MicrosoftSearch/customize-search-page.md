---
title: Personalizar a Pesquisa da Microsoft página
ms.author: jeffkizn
author: jypal
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Adicionar verticais de pesquisa e personalizar resultados de pesquisa
ms.openlocfilehash: 1ca436a2617e32e285715e4fffd622dc7a571ca1
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375621"
---
# <a name="customize-the-search-results-page"></a>Personalizar a página de resultados da pesquisa

Você pode criar tipos  de resultados e *verticais* de pesquisa para personalizar os resultados de pesquisa que os usuários veem quando pesquisam no Microsoft [SharePoint,](https://sharepoint.com/) [Microsoft Office](https://office.com)e Pesquisa da Microsoft em [Bing](https://bing.com). As verticais facilitam que os usuários encontrem as informações que eles têm permissão para ver.

Por exemplo, você pode criar uma pesquisa vertical para dados de análise de marketing de software de terceiros para seus usuários no departamento de marketing. Você também pode definir tipos de resultados e personalizar o layout desses dados.

## <a name="about-search-verticals"></a>Sobre as verticais de pesquisa

Há uma linha de guias na parte superior da página Pesquisa da Microsoft resultados. São verticais de pesquisa. Uma pesquisa vertical mostra apenas resultados de um determinado tipo ou de um determinado conjunto de conteúdo. Exemplos são **Arquivos** ou **Notícias.** Por padrão, Pesquisa da Microsoft mostra as verticais **Todos**, **Pessoas,** **Arquivos,** **Sites** e **Notícias**.  

Você pode adicionar verticais de pesquisa relevantes à sua organização. Elas serão exibidas na página Pesquisa da Microsoft resultados em SharePoint, Office e Bing. Por exemplo, você pode criar uma vertical para conteúdo relacionado ao marketing e outra para vendas, com base no tipo de informação que cada departamento precisa. Você pode adicionar verticais para mostrar resultados somente de conteúdo indexado por meio de conectores.

Você pode criar tipos de resultados e verticais em dois níveis:

- **Nível da** organização – Uma vertical que você cria no nível da organização aparece na página de resultados da pesquisa quando os usuários pesquisam [na](https://sharepoint.com/) página inicial do SharePoint, no [Office](https://office.com)ou no [Bing](https://bing.com).
- **Nível do** site – Por exemplo, talvez você queira permitir que seus funcionários do serviço de atendimento ao cliente pesquisem incidentes de Gravidade *1* diretamente do site de segurança SharePoint departamento.

### <a name="multiple-connections-in-a-vertical"></a>Várias conexões em um vertical

Uma pesquisa vertical pode surgir resultados de várias fontes de conector. Essa opção oferece flexibilidade ao projetar sua página de resultados de pesquisa. O processo de instalação vertical permite que os administradores selecionem várias conexões na etapa "Fonte de conteúdo".

Se você nomear com precisão o máximo possível de *rótulos* semânticos, essa experiência será aprimorada. Você adiciona rótulos semânticos no ponto de definição e ingestão de esquema. [Consulte mais sobre como criar e gerenciar rótulos semânticos.](configure-connector.md#step-6-assign-property-labels)
[Aqui](configure-connector.md#step-6-assign-property-labels) estão informações adicionais sobre como criar e gerenciar rótulos semânticos.

> [!NOTE]
> As várias conexões em um recurso vertical estão atualmente em visualização. Para obter mais informações, consulte [Conectores recursos de visualização](connectors-overview.md#what-are-the-preview-features).

Uma conexão pode ser adicionada como uma fonte de conteúdo em uma única vertical. Não é possível usar conexões em várias verticais.

Para configurar uma consulta para uma pesquisa vertical onde várias fontes de conexão foram adicionadas, use propriedades de origem comuns para criar a consulta.

### <a name="before-you-create-verticals-and-result-types"></a>Antes de criar tipos de resultados e verticais

Considere estes fatores:

- Certifique-se de que o conector foi indexado. Isso pode levar até 48 horas, dependendo do tamanho do arquivo.

- Não é possível criar uma vertical para conteúdo que reside em SharePoint.

Estas são as etapas para implementar uma vertical:

1. Crie o vertical. Nesta etapa, você define o nome da vertical, a fonte de conteúdo e o escopo do conteúdo a ser pesquisado.
2. Defina como serão os resultados dessa vertical.  
3. Habilita a vertical (a ser exibida) na página de lista vertical.

## <a name="step-1-create-the-search-vertical"></a>Etapa 1: Criar a pesquisa vertical

Depois de iniciar o assistente, você é orientado por etapas para definir o nome vertical, a fonte de conteúdo e o escopo do conteúdo a ser pesquisado.

>[!Note]
>As verticais são criadas em um estado desabilitado. Habilita-os a torná-los exibiveis.

Você pode usar um conjunto limitado de [KQL (Keyword Query Language) para](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) restringir o escopo. (As propriedades que você pode usar são descritas posteriormente neste artigo.) Recomendamos que você use palavras-chave de texto livre e restrições de propriedade com operadores booleano. O KQL também dá suporte [a variáveis de consulta de perfil](#profile-query-variables) para ajustar os resultados na vertical.

### <a name="create-a-vertical-at-the-organization-level"></a>Criar uma vertical no nível da organização

Para criar uma vertical no Pesquisa da Microsoft em SharePoint, Office ou Bing, siga estas etapas:

1. No [Centro de administração do Microsoft 365,](https://admin.microsoft.com)vá para [**Verticals**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals).
2. Selecione **Adicionar** para começar.  

### <a name="create-a-vertical-at-the-site-level"></a>Criar uma vertical no nível do site

1. No site [SharePoint](https://sharepoint.com/) onde você deseja verticais, vá para **Configurações**.
2. Selecione **Informações do** site e selecione Exibir todas as **configurações do site.**
3. Localize **a Pesquisa da Microsoft** e selecione Configurar Pesquisa da Microsoft para este conjunto de **sites.**
4. No painel de navegação, vá para **Experiência personalizada** e selecione a **guia Verticals.**
5. Para adicionar um vertical, selecione **Adicionar**. Ou para editar um vertical, selecione-o na lista.

## <a name="step-2-create-result-types"></a>Etapa 2: Criar tipos de resultados

Você pode usar *tipos de resultados* para definir como os resultados são exibidos na vertical. O layout de resultados permite que você mostre informações importantes diretamente nos resultados da pesquisa, para que os usuários não tenham que selecionar cada resultado para ver se encontraram o que estão procurando.

### <a name="default-search-result-layout"></a>Layout padrão do resultado da pesquisa

Um layout de resultado de pesquisa padrão  será  mostrado para conteúdo do conector se os rótulos e as propriedades de conteúdo foram mapeados corretamente para as propriedades de origem quando o conector foi configurado. O *rótulo* de título é o rótulo mais importante. É *recomendável que* você tenha uma propriedade atribuída a esse rótulo para usar o layout de resultado da pesquisa padrão.

### <a name="create-your-own-result-type"></a>Criar seu próprio tipo de resultado

Para criar seu próprio layout de resultado de pesquisa e substituir o layout padrão do resultado da pesquisa, crie um *tipo de resultado*. O tipo do resultado de pesquisa é uma função que faz com que diferentes tipos de resultados de pesquisa sejam exibidos de diferentes maneiras. Ele consiste em:

- **Uma ou mais condições para** comparar cada resultado de pesquisa, como a fonte de conteúdo do resultado da pesquisa.  
- Um **layout de resultado** a ser usado para resultados de pesquisa que atendem às condições. O layout resultante controla como os resultados que atendem às condições aparecem e se comportam em uma página de resultados de pesquisa.

*Se você não fizer o mapeamento apropriado para mostrar o layout padrão do resultado da pesquisa, deverá criar pelo menos um tipo de resultado para que os resultados seja exibidos na vertical.* 

Você pode criar vários tipos de resultados para cada vertical, o que permite usar layouts diferentes para diferentes tipos de resultados. Por exemplo, você pode personalizar *incidentes de* Gravidade 1 para ter cores mais proeminentes e uma fonte maior do que incidentes *de Gravidade 3.*

Depois de iniciar o assistente, você é orientado pelas etapas para definir o nome, a fonte de conteúdo e as condições do tipo de resultado. Você pode definir a prioridade do tipo de resultado no exibição de lista.
  
### <a name="create-a-result-type-at-the-organization-level"></a>Criar um tipo de resultado no nível da organização

1. Na [Centro de administração do Microsoft 365,](https://admin.microsoft.com)vá para [**Tipos de resultado**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes).
2. Para adicionar um tipo de resultado, selecione **Adicionar**. Para editar um tipo de resultado, selecione o tipo de resultado na lista relevante.

### <a name="create-a-result-type-at-the-site-level"></a>Criar um tipo de resultado no nível do site

1. No site [SharePoint](https://sharepoint.com/) onde você deseja o tipo de resultado, vá para **Configurações**.
2. Selecione **Informações do** site e selecione Exibir todas as **configurações do site.**
3. Procure a seção **Pesquisa da Microsoft** e selecione Configurar Pesquisa da Microsoft **para este conjunto de sites.**
4. No painel de navegação, vá para **Experiência personalizada** e selecione a guia **Tipo de** resultado.
5. Para adicionar um tipo de resultado, selecione **Adicionar**.  Ou, para editar um tipo de resultado, selecione o tipo de resultado na lista.

## <a name="step-3-view-the-vertical-after-its-enabled"></a>Etapa 3: Exibir a vertical depois de habilitada

Depois de habilitar a vertical, há um atraso de algumas horas antes de poder exibi-lo. Mas você pode anexar à URL em SharePoint `cacheClear=true` e Office para exibir a vertical imediatamente. Para Bing, anexar `&features=uncachedVerticals` ao modo de `Work vertical URL` exibição vertical imediatamente.

> [!NOTE]
> As verticais adicionadas não são visíveis no SharePoint]( e Office quando exibidas de https://sharepoint.com/) navegadores da Web móveis. [](https://office.com)

## <a name="profile-query-variables"></a>Variáveis de consulta de perfil

Use variáveis na seção de consulta KQL de uma vertical para fornecer dados dinâmicos como uma entrada para a consulta de uma vertical. Você pode usar as variáveis de consulta de perfil para tornar os resultados da pesquisa contextuais para o usuário in-locar. As variáveis de consulta de perfil buscam valores do perfil do usuário [de entrada.](/graph/api/resources/profile)

Por exemplo, para criar uma vertical "Tíquetes" para o usuário encontrar tíquetes de suporte atribuídos a eles, você pode especificar a seguinte consulta na seção "Consulta" durante a criação vertical na página de administração:  

`AssignedTo:{Profile.accounts.userPrincipalName}`

Esse idioma restringirá os resultados da pesquisa para mostrar apenas os itens para os quais o destinatário é o usuário que executa a pesquisa.

[O recurso Profile](/graph/api/resources/profile) expõe propriedades como coleções. Por exemplo, informações relacionadas a endereços de email são expostas por meio de coleta de emails, posições de trabalho como conjunto de posições e assim por diante. Todas as propriedades disponíveis no perfil de usuário, que têm o AAD como o tipo de origem, são expostas como variáveis de consulta.


Considere um usuário que tenha três endereços de email disponíveis no conjunto de emails, conforme mostrado aqui:

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

- A consulta `MyProperty: {Profile.emails.address}` resolverá para *MyProperty: "Megan.Bowen@contoso.com"*.  

- Para resolver todos os valores do atributo address, use a sintaxe de expansão de vários valores. A consulta resolverá `{|MyProperty:{Profile.emails.address}}` *((MyProperty:"Megan.Bowen@contoso \. com")* ou *(MyProperty: "meganb@hotmail \. com")* ou  *(MyProperty:"meganb@outlook \. com"))*.

Use o operador "|" para resolver variáveis de vários valores. Consulte a tabela a seguir para obter mais exemplos de expansão de perfil.

| #         | Sintaxe |  Valor retornado  |
| --------- | ------ | --- |
| 1    | MyProperty:{Profile.emails.address}  |   "Megan \. Bowen@contoso.com"  |
| 2 | MyProperty:{Profile.emails}   |    {Profile.emails} Isso não será resolvido porque *os emails* são um objeto.|
| 3    | {? MyProperty:{Profile.emails}}  |  Isso não será resolvido porque *os emails* são um objeto. O "?" o operador ignora as variáveis de consulta que não são resolvidas. Essa variável será removida quando passada para baixo na pilha de consulta.   |
| 4  | {&#124;MyProperty: {Profile.emails.source.Type}}    |  ((MyProperty:"official") ou (MyProperty:"non-official") ou (MyProperty:"personal"))    |

> [!NOTE]
>
> - As variáveis de consulta de perfil só têm suporte para verticais personalizadas que usam um [conector](connectors-overview.md) como fonte de conteúdo.
> - As variáveis de consulta de perfil são definidas na seção "Consulta" do [processo de instalação vertical](customize-search-page.md#step-1-create-the-search-vertical).
> - O recurso de variáveis de consulta de perfil está atualmente em visualização. Para obter mais informações sobre visualização, consulte [Conectores recursos de visualização](connectors-overview.md#what-are-the-preview-features).

## <a name="troubleshooting"></a>Solução de problemas

Aqui está uma lista de problemas comuns que você pode encontrar e ações para corrigi-los.

|Problema  |Ação  |
|---------|---------|
| Vejo uma mensagem de erro "Algo deu errado" na vertical. | Os tipos vertical e de resultado são necessários para concluir a instalação. Certifique-se de ter criado ambos para a mesma fonte de conteúdo. |
| Não vejo meu layout de resultado, embora tenha criado um. | Pode haver um atraso de alguns minutos porque essas configurações são armazenadas em cache. Aguarde alguns minutos e tente novamente.        |
| Não vejo fontes de conteúdo na página vertical ou do tipo de resultado. | Certifique-se de ter configurado conectores e dados indexados.   |

## <a name="next-steps"></a>Próximas etapas

[Personalizar o layout de resultados](customize-results-layout.md)
