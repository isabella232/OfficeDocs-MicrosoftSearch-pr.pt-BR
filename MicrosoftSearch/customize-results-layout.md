---
title: Gerenciar layouts de resultados de pesquisa
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
description: Usando cartões adaptáveis, crie um layout para exibir seus resultados de pesquisa personalizados
ms.openlocfilehash: 44808d1dba8d765ba67fcd0c3dcf6f186a0b774c
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375620"
---
<!-- markdownlint-disable no-hard-tabs -->
# <a name="create-a-layout-to-customize-search-results"></a>Criar um layout para personalizar os resultados da pesquisa

Você pode projetar o layout de resultado para uma vertical personalizada usando o designer de layout de pesquisa. Você pode começar a projetar o layout escolhendo modelos oferecidos no designer de layout e usando-os se eles se ajustarem aos seus requisitos. Ou você pode optar por editar esses modelos de várias maneiras para se ajustar aos seus requisitos. Por exemplo, adicione/remova imagens, adicione/remova texto e modifique o texto. Se nenhum dos modelos atender aos seus requisitos, você poderá optar por começar a projetar seu layout usando um modelo em branco.  

Depois que o layout estiver pronto, use o idioma [Modelo](/adaptive-cards/templating/language) de Cartões Adaptáveis para criar um JSON de layout de resultado usado para definir um tipo de resultado. Você mapeia as propriedades de resultado para o layout usando a etapa Mapeamento no designer de layout.  

## <a name="create-a-layout-on-your-own"></a>Criar um layout por conta própria

Criar um layout por conta própria requer conhecimento de [cartões adaptáveis](/adaptive-cards/authoring-cards/getting-started) e [seu esquema.](https://adaptivecards.io/explorer/) O layout do resultado da pesquisa usa um subconjunto dos elementos oferecidos por cartões adaptáveis e você pode usar o designer de layout para saber mais sobre o conjunto de elementos com suporte.  

Ao criar seu próprio layout, crie o layout do cartão adaptável usando dados do conector e finalize o layout.
Há duas etapas principais na criação de seu próprio layout:

- Projete o layout.
- Separe os dados do modelo.

### <a name="design-the-layout"></a>Criar o layout

Neste exemplo, mostramos um layout com um header, link e texto descritivo.

![Exemplo de um layout com um header, link e descrição.](media/Verts-ExampleLayout.png)

E aqui está o arquivo JSON associado do layout:

```json
{
    "type": "AdaptiveCard",
    "version": "1.3",
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

### <a name="separate-the-data-from-the-layout"></a>Separar os dados do layout

Você pode separar os dados do layout e vincular os dados.

Veja Layout JSON após vincular os dados:

```json
{
    "type": "AdaptiveCard",
    "version": "1.3",
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
                            "text": "[${title}](${titleUrl})",
                            "color": "Accent",
                            "size": "Medium",
                            "spacing": "None",
                            "weight": "Bolder"
                        },
                        {
                            "type": "TextBlock",
                            "text": "${link}",
                            "spacing": "None",
                            "color": "Dark",
                            "weight": "Bolder"
                        },
                        {
                            "type": "TextBlock",
                            "text": "${description}",
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

Dados de exemplo: especifique dados de exemplo no Editor de Dados de **Exemplo** para exibir o cartão vinculado a dados quando estiver no **modo de visualização.**

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a>Mapear o layout para as propriedades de resultado

Você deve mapear cada campo do layout para uma propriedade de resultado ou uma propriedade do conector para gerar o JSON de layout de resultado.

![Captura de tela de um layout de exemplo na página Designer de Layout de Pesquisa com um campo selecionado e o painel de propriedades aberto.](media/Verts-SearchLayoutDesigner.png)

Selecione um campo no layout para realçar as variáveis que precisam ser mapeadas. Você pode usar várias variáveis para um único campo e todos os campos devem ser mapeados para as propriedades de resultado.

### <a name="show-snippet-on-search-result"></a>Mostrar trecho no resultado da pesquisa  

Trechos dinâmicos gerados na propriedade **de** conteúdo do resultado do conector podem ser mostrados no resultado da pesquisa. **ResultSnippet** é a propriedade do sistema que age como uma propriedade de espaço reservado para os trechos gerados para cada resultado do Conector. Para mostrar os trechos no layout do resultado, a propriedade do sistema **ResultSnippet** deve ser mapeada para um campo apropriado, por exemplo, Description, no layout do resultado da pesquisa. Trechos gerados em cada resultado também realçam as partidas no trecho com o termo de consulta inserido pelo usuário.

## <a name="things-to-consider"></a>Itens a considerar

Antes de começar, há algumas coisas que você deve fazer e algumas coisas que você deve evitar para garantir que seus layouts sejam bem-sucedidos.

### <a name="do"></a>Fazer

- Edite um modelo para fornecer o link de logotipo no layout se você estiver usando links estáticos para logotipos e não propriedades de resultado.
- Valide o layout de resultados para cenários em que nenhum dado é retornado para uma propriedade de resultado usada no JSON de resultado. Use a `$when` condição para ocultar um elemento se a propriedade não contém dados.  
- Certifique-se de que os tipos de dados `$when` da condição e da propriedade de resultado corresponderem. Por exemplo, não compare `Number` com `Text` na `$when` condição.  
- Pense nos requisitos de tema ao projetar um layout de resultado.  
- Certifique-se de que `Textblock`   o elemento possa manipular o conteúdo dinâmico. Você pode usar as `wrap` propriedades e elemento para essa `maxLines` finalidade.
- Formatar corretamente a data ao usar `{DATE()}` em Markdown.  

### <a name="dont"></a>Não fazer

- Não defina tipos de dados inválidos quando os valores de associação. Para obter mais informações sobre tipos de dados, consulte [Manage the Search schema](/sharepoint/search/manage-the-search-schema).
- Evite recorte o resultado na página de resultados seguindo a altura máxima do layout de resultado JSON. Se você exceder a altura máxima do layout do resultado, o resultado será cortado na página de resultados.
- Não use valores `px` nas propriedades do elemento.
- Não use a marcação com a **propriedade ResultSnippet** no layout do resultado para realçar a combinação de consulta no resultado da pesquisa.

## <a name="resources"></a>Recursos

[Personalizar a página de resultados da pesquisa](customize-search-page.md)

[Cartões adaptáveis](/adaptive-cards/authoring-cards/getting-started)

[Idioma do Modelo de Cartões Adaptáveis](/adaptive-cards/templating/language)

[Esquema de cartão adaptável](https://adaptivecards.io/explorer/)
