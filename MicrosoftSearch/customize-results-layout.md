---
title: Personalizar o layout dos resultados da pesquisa
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
description: Usando cartões adaptáveis, crie um layout para exibir seus resultados de pesquisa personalizados
ms.openlocfilehash: 2ca53f2e2dc207acdf48542f39ee4f448bdeb90e
ms.sourcegitcommit: bfcab9d42e93addccd1e3875b41bc9cc1b6986cc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "37949539"
---
# <a name="create-a-layout-to-customize-search-results"></a>Criar um layout para personalizar os resultados da pesquisa

Você pode criar o layout de resultado para uma vertical personalizada usando o designer de layout de pesquisa. Você pode começar a criar o layout escolhendo modelos oferecidos no designer de layout e usá-los se eles atenderem aos seus requisitos. Ou você pode optar por editar esses modelos de várias maneiras para atender aos seus requisitos. Por exemplo, adicionar/remover imagens, adicionar/remover texto, modificar texto. Se nenhum dos modelos atender aos requisitos, você poderá optar por começar a criar o layout usando um modelo em branco.  

 

Depois que o layout estiver pronto, você usa a [linguagem de modelo cartões adaptáveis](https://docs.microsoft.com/adaptive-cards/templating/language) para criar o JSON de layout de resultado do Thea, que é usado para definir um tipo de resultado. Você mapeia as propriedades de resultado para o layout usando a etapa de mapeamento no designer de layout.  

## <a name="create-a-layout-on-your-own"></a>Criar um layout por conta própria
Criar um layout por conta própria requer conhecimento de [cartões adaptáveis](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) e seu [esquema](https://adaptivecards.io/explorer/). Layout do resultado da pesquisa usa um subconjunto dos elementos oferecidos por cartões adaptáveis e você pode usar o designer de layout para saber mais sobre o conjunto de elementos com suporte.  

Ao criar seu próprio layout, crie o layout do cartão adaptável usando dados do e Finalize o layout.
Há duas etapas principais na criação de seu próprio layout
- Criando o layout
- Separando os dados do modelo

#### <a name="designing-the-layout"></a>Criando o layout

Neste exemplo, estamos mostrando um layout com cabeçalho, link e texto descritivo.

![Exemplo de layout com cabeçalho, link e descrição.](media/Verts-ExampleLayout.png)

E aqui está o arquivo JSON associado do layout:


```json
{ 
    "type": "AdaptiveCard", 
    "version": "1.0", 
     "body": [ 
{ 

            "type": "ColumnSet", 
             "columns": [ 
                 { 
                     "type": "Column", 
                     "width": 8, 
                     "items": [ 
                         { 
                             "type": "TextBlock", 
                             "text": "Contoso Marketing Analysis - Q3 FY18", 
                             "color": "Accent", 
                             "size": "Medium", 
                             "spacing": "None", 
                             "$when": "{title != \"\"}", 
                             "weight": "Bolder" 
                        }, 
                        { 
                        "type": "TextBlock",  
                        "text": "https://contoso.com/hr/link", 
                        "spacing": "None",  
                        "color": "Dark", 
                        "weight": "Bolder" 

                        }, 

                        {  
                        "type": "TextBlock", 
                        "text": "Marketing team at Contoso.., and looking at the Contoso Marketing documents on the team site. This contains the data from FY20 and will taken over to FY21...Marketing Planning is ongoing for FY20..",  
                        "wrap": true, 
                        "maxLines": 2, 
                        "spacing": "Medium" 
                        } 
                        ], 

                    "horizontalAlignment": "Center", 
                    "spacing": "None" 

                } 

            ] 

        } 
        ], 

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json" 
}
```

#### <a name="separating-the-data-from-the-layout"></a>Separando os dados do layout

Você pode separar os dados do layout e vincular os dados. 

Veja a seguir o layout JSON depois de vincular os dados:


```json
{ 

    "type": "AdaptiveCard", 
    "version": "1.0", 
    "body": [ 
    { 
    "type": "ColumnSet", 
"columns": [ 

                { 
                "type": "Column", 
                "width": 8, 
                "items": [ 
                { 
                "type": "TextBlock", 
                "text": "[{title}]({titleUrl})", 
                "color": "Accent", 
                "size": "Medium",
                "spacing": "None", 
                "weight": "Bolder" 

                 }, 
                 { 
                 "type": "TextBlock", 
                 "text": "{link}",
                 "spacing": "None", 
                 "color": "Dark",
                 "weight": "Bolder" 
                 }, 
                 { 
                 "type": "TextBlock",
                 "text": "{description}",
                 "wrap": true,
                 "maxLines": 2, 
                 "spacing": "Medium" 
                 } 
                 ], 
                 "horizontalAlignment": "Center", 
                 "spacing": "None" 
                 } 
                 ] 

        } 

    ], 

    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json" 
}
```

Dados de exemplo: especifique dados de exemplo no **Editor de dados de exemplo** para exibir o cartão associado a dados no "modo de visualização".

```json
{ 

    "title": "Contoso Marketing Analysis - Q3 FY18", 
    "titleUrl": "https://contoso.com/hr/link", 
    "link": "https://contoso.com/hr/link", 
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?" 

} 
```

## <a name="map-the-layout-to-the-result-properties"></a>Mapear o layout para as propriedades de resultado

Você deve mapear cada campo do layout para uma propriedade Result ou uma propriedade Connector para gerar o resultado de layout JSON.

![Verts-SearchLayoutDesigner. png](media/Verts-SearchLayoutDesigner.png)

Selecione um campo no layout para realçar as variáveis que precisam ser mapeadas. Você pode usar várias variáveis para um único campo e todos os campos devem ser mapeados para as propriedades do resultado.

## <a name="things-to-consider"></a>Considerações a serem consideradas...

Antes de começar, há algumas coisas que você deve fazer e algumas coisas que você deve evitar para garantir que seus layouts serão bem-sucedidos.

### <a name="do"></a>Fazer

- Edite um modelo para fornecer o link de logotipo no layout se você estiver usando links estáticos para logotipos e não resultados de propriedades.   
- Validar o layout do resultado para cenários em que nenhum dado é retornado para uma propriedade Result usada no resultado JSON. Use `$when` a condição para ocultar um elemento se a propriedade não contiver dados.  
- Certifique-se de que os tipos `$when` de dados da condição e a propriedade Result correspondam. Por exemplo, não comparar `Number` com `Text` em `$when` condição.  
- Considere os requisitos de temas ao criar um layout de resultados.  
- Certifique-se `Textblock`  de que o elemento pode manipular conteúdo dinâmico. Você pode usar as `wrap` propriedades `maxLines` de elemento e para essa finalidade. 
- Formatar corretamente a data ao usar `{DATE()}` na redução.  

### <a name="dont"></a>Não fazer

- Não defina tipos de dados inválidos ao vincular valores. Para obter mais informações sobre os tipos de dados, consulte [Manage The Search Schema](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema ).
- Evite cortar o resultado na página de resultados seguindo a altura máxima do JSON de layout de resultados. Se você exceder a altura máxima do layout do resultado, o resultado será cortado na página de resultados.
- Não use `px` valores nas propriedades do elemento.


## <a name="resources"></a>Recursos
[Personalizar página de resultados de pesquisa](customize-search-page.md)

[Cartões adaptáveis](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)

[Idioma do modelo de cartões adaptáveis](https://docs.microsoft.com/adaptive-cards/templating/language)

[Esquema de cartão adaptável](https://adaptivecards.io/explorer/)