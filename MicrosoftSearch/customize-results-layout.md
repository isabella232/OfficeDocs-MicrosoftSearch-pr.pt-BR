---
title: Personalizar o layout dos resultados da pesquisa
ms.author: jypal
author: jypal6
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Usando cartões adaptáveis, crie um layout para exibir seus resultados de pesquisa personalizados
ms.openlocfilehash: 0856adfd85a921cf026cd59a8ca2c5beea2ffcf2
ms.sourcegitcommit: 7ceefb7a96ae6886145b929791c7448c139366b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2020
ms.locfileid: "48595269"
---
<!-- markdownlint-disable no-hard-tabs -->
# <a name="create-a-layout-to-customize-search-results"></a><span data-ttu-id="a1719-103">Criar um layout para personalizar os resultados da pesquisa</span><span class="sxs-lookup"><span data-stu-id="a1719-103">Create a layout to customize search results</span></span>

<span data-ttu-id="a1719-104">Você pode criar o layout de resultado para uma vertical personalizada usando o designer de layout de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a1719-104">You can design the result layout for a custom vertical using the search layout designer.</span></span> <span data-ttu-id="a1719-105">Você pode começar a criar o layout escolhendo modelos oferecidos no designer de layout e usá-los se eles atenderem aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="a1719-105">You can start designing the layout by choosing templates offered in the layout designer and using them if they fit your requirements.</span></span> <span data-ttu-id="a1719-106">Ou você pode optar por editar esses modelos de várias maneiras para atender aos seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="a1719-106">Or you can choose to edit these templates in various ways to fit your requirements.</span></span> <span data-ttu-id="a1719-107">Por exemplo, adicionar/remover imagens, adicionar/remover texto e modificar texto.</span><span class="sxs-lookup"><span data-stu-id="a1719-107">For example, add/remove images, add/remove text, and modify text.</span></span> <span data-ttu-id="a1719-108">Se nenhum dos modelos atender aos seus requisitos, você poderá optar por começar a criar o layout usando um modelo em branco.</span><span class="sxs-lookup"><span data-stu-id="a1719-108">If none of the templates meet your requirements, you can choose to start designing your layout using a blank template.</span></span>  

<span data-ttu-id="a1719-109">Depois que o layout estiver pronto, use o [idioma do modelo de cartões adaptáveis](https://docs.microsoft.com/adaptive-cards/templating/language) para criar um JSON de layout de resultado que é usado para definir um tipo de resultado.</span><span class="sxs-lookup"><span data-stu-id="a1719-109">After the layout is ready, use the [Adaptive Cards Template language](https://docs.microsoft.com/adaptive-cards/templating/language) to create a result layout JSON that's used to define a result type.</span></span> <span data-ttu-id="a1719-110">Você mapeia as propriedades de resultado para o layout usando a etapa de mapeamento no designer de layout.</span><span class="sxs-lookup"><span data-stu-id="a1719-110">You map the result properties to the layout using the Mapping step in the layout designer.</span></span>  

## <a name="create-a-layout-on-your-own"></a><span data-ttu-id="a1719-111">Criar um layout por conta própria</span><span class="sxs-lookup"><span data-stu-id="a1719-111">Create a layout on your own</span></span>

<span data-ttu-id="a1719-112">Criar um layout por conta própria requer conhecimento de [cartões adaptáveis](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) e seu [esquema](https://adaptivecards.io/explorer/).</span><span class="sxs-lookup"><span data-stu-id="a1719-112">Creating a layout on your own requires knowledge of [adaptive cards](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started) and their [schema](https://adaptivecards.io/explorer/).</span></span> <span data-ttu-id="a1719-113">Layout do resultado da pesquisa usa um subconjunto dos elementos oferecidos por cartões adaptáveis e você pode usar o designer de layout para saber mais sobre o conjunto de elementos com suporte.</span><span class="sxs-lookup"><span data-stu-id="a1719-113">Search result layout uses a subset of the elements offered by adaptive cards, and you can use the layout designer to learn about the supported set of elements.</span></span>  

<span data-ttu-id="a1719-114">Ao criar seu próprio layout, crie o layout do cartão adaptável usando dados do seu conector e Finalize o layout.</span><span class="sxs-lookup"><span data-stu-id="a1719-114">While creating your own layout, create the adaptive card layout using data from your connector, and then finalize the layout.</span></span>
<span data-ttu-id="a1719-115">Há duas etapas principais na criação de seu próprio layout:</span><span class="sxs-lookup"><span data-stu-id="a1719-115">There are two main steps in creating your own layout:</span></span>

- <span data-ttu-id="a1719-116">Criar o layout.</span><span class="sxs-lookup"><span data-stu-id="a1719-116">Design the layout.</span></span>
- <span data-ttu-id="a1719-117">Separe os dados do modelo.</span><span class="sxs-lookup"><span data-stu-id="a1719-117">Separate the data from the template.</span></span>

### <a name="design-the-layout"></a><span data-ttu-id="a1719-118">Criar o layout</span><span class="sxs-lookup"><span data-stu-id="a1719-118">Design the layout</span></span>

<span data-ttu-id="a1719-119">Neste exemplo, mostramos um layout com um cabeçalho, link e texto descritivo.</span><span class="sxs-lookup"><span data-stu-id="a1719-119">In this example, we show a layout with a header, link, and descriptive text.</span></span>

![Exemplo de layout com cabeçalho, link e descrição.](media/Verts-ExampleLayout.png)

<span data-ttu-id="a1719-121">E aqui está o arquivo JSON associado do layout:</span><span class="sxs-lookup"><span data-stu-id="a1719-121">And here's the layout's associated JSON file:</span></span>

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

### <a name="separate-the-data-from-the-layout"></a><span data-ttu-id="a1719-122">Separar os dados do layout</span><span class="sxs-lookup"><span data-stu-id="a1719-122">Separate the data from the layout</span></span>

<span data-ttu-id="a1719-123">Você pode separar os dados do layout e vincular os dados.</span><span class="sxs-lookup"><span data-stu-id="a1719-123">You can separate the data from the layout and bind the data.</span></span>

<span data-ttu-id="a1719-124">Veja a seguir o layout JSON depois de vincular os dados:</span><span class="sxs-lookup"><span data-stu-id="a1719-124">Here's Layout JSON after binding the data:</span></span>

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

<span data-ttu-id="a1719-125">Dados de exemplo: especifique dados de exemplo no **Editor de dados de exemplo** para exibir o cartão ligado a dados no modo de **Visualização**.</span><span class="sxs-lookup"><span data-stu-id="a1719-125">Sample data: Specify sample data in the **Sample Data Editor** to view the data-bound card when in **Preview Mode**.</span></span>

```json
{

    "title": "Contoso Marketing Analysis - Q3 FY18",
    "titleUrl": "https://contoso.com/hr/link",
    "link": "https://contoso.com/hr/link",
    "description": "Marketing team, and looking at the Contoso Marketing documents on the team site. Yo can't see right...Marketing Planning presentation?"

}
```

## <a name="map-the-layout-to-the-result-properties"></a><span data-ttu-id="a1719-126">Mapear o layout para as propriedades de resultado</span><span class="sxs-lookup"><span data-stu-id="a1719-126">Map the layout to the result properties</span></span>

<span data-ttu-id="a1719-127">Você deve mapear cada campo do layout para uma propriedade Result ou uma propriedade Connector para gerar o resultado de layout JSON.</span><span class="sxs-lookup"><span data-stu-id="a1719-127">You must map each field of the layout to a result property or a connector property to generate the result layout JSON.</span></span>

![Captura de tela de um layout de exemplo na página de designer de layout de pesquisa com um campo selecionado e o painel de propriedades aberto.](media/Verts-SearchLayoutDesigner.png)

<span data-ttu-id="a1719-129">Selecione um campo no layout para realçar as variáveis que precisam ser mapeadas.</span><span class="sxs-lookup"><span data-stu-id="a1719-129">Select a field in the layout to highlight the variables that need to be mapped.</span></span> <span data-ttu-id="a1719-130">Você pode usar várias variáveis para um único campo, e todos os campos devem ser mapeados para as propriedades do resultado.</span><span class="sxs-lookup"><span data-stu-id="a1719-130">You can use multiple variables for a single field, and all fields must be mapped to the result properties.</span></span>

### <a name="show-snippet-on-search-result"></a><span data-ttu-id="a1719-131">Mostrar trecho no resultado da pesquisa</span><span class="sxs-lookup"><span data-stu-id="a1719-131">Show snippet on search result</span></span>  

<span data-ttu-id="a1719-132">Trechos dinâmicos gerados na propriedade de **conteúdo** do resultado do conector podem ser mostrados no resultado da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a1719-132">Dynamic snippets generated on the **content** property of the connector result can be shown on the search result.</span></span> <span data-ttu-id="a1719-133">**ResultSnippet** é a propriedade do sistema que atua como uma propriedade de espaço reservado para os trechos gerados para cada resultado do conector.</span><span class="sxs-lookup"><span data-stu-id="a1719-133">**ResultSnippet** is the system property that acts as a placeholder property for the snippets generated for each Connector result.</span></span> <span data-ttu-id="a1719-134">Para mostrar os trechos de código no layout do resultado, a propriedade do sistema **ResultSnippet** deve ser mapeada para um campo apropriado, por exemplo, descrição, no layout do resultado da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a1719-134">To show the snippets on the result layout, the **ResultSnippet** system property must be mapped to an appropriate field, for example Description, in the search result layout.</span></span> <span data-ttu-id="a1719-135">Os trechos de código gerados em cada resultado também realçam as correspondências no trecho de código com o termo de consulta inserido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="a1719-135">Snippets generated on each result also highlight the matches in the Snippet with the query term entered by the user.</span></span> 

## <a name="things-to-consider"></a><span data-ttu-id="a1719-136">Itens a considerar</span><span class="sxs-lookup"><span data-stu-id="a1719-136">Things to consider</span></span>

<span data-ttu-id="a1719-137">Antes de começar, há algumas coisas que você deve fazer e algumas coisas que você deve evitar para garantir que seus layouts serão bem-sucedidos.</span><span class="sxs-lookup"><span data-stu-id="a1719-137">Before you get started, there are a few things that you should do and a few things you should avoid to ensure that your layouts will be successful.</span></span>

### <a name="do"></a><span data-ttu-id="a1719-138">Fazer</span><span class="sxs-lookup"><span data-stu-id="a1719-138">Do</span></span>

- <span data-ttu-id="a1719-139">Edite um modelo para fornecer o link de logotipo no layout se você estiver usando links estáticos para logotipos e não resultados de propriedades.</span><span class="sxs-lookup"><span data-stu-id="a1719-139">Edit a template to provide the logo link in the layout if you're using static links for logos and not result properties.</span></span>
- <span data-ttu-id="a1719-140">Validar o layout do resultado para cenários em que nenhum dado é retornado para uma propriedade Result usada no resultado JSON.</span><span class="sxs-lookup"><span data-stu-id="a1719-140">Validate the result layout for scenarios where no data is returned for a result property used in the result JSON.</span></span> <span data-ttu-id="a1719-141">Use a `$when` condição para ocultar um elemento se a propriedade não contiver dados.</span><span class="sxs-lookup"><span data-stu-id="a1719-141">Use the `$when` condition to hide an element if the property doesn't contain data.</span></span>  
- <span data-ttu-id="a1719-142">Certifique-se de que os tipos de dados da `$when` condição e a propriedade Result correspondam.</span><span class="sxs-lookup"><span data-stu-id="a1719-142">Make sure that data types of the `$when` condition and the result property match.</span></span> <span data-ttu-id="a1719-143">Por exemplo, não compare `Number` com `Text` na `$when` condição.</span><span class="sxs-lookup"><span data-stu-id="a1719-143">For example, don't compare `Number` with `Text` in the `$when` condition.</span></span>  
- <span data-ttu-id="a1719-144">Considere os requisitos de temas ao criar um layout de resultados.</span><span class="sxs-lookup"><span data-stu-id="a1719-144">Think of theme requirements when designing a result layout.</span></span>  
- <span data-ttu-id="a1719-145">Certifique-se de que o `Textblock`   elemento pode lidar com conteúdo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="a1719-145">Make sure that the `Textblock` element can handle dynamic content.</span></span> <span data-ttu-id="a1719-146">Você pode usar as `wrap` `maxLines` Propriedades de elemento e para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="a1719-146">You can use the `wrap` and `maxLines` element properties for this purpose.</span></span>
- <span data-ttu-id="a1719-147">Formatar corretamente a data ao usar `{DATE()}` na redução.</span><span class="sxs-lookup"><span data-stu-id="a1719-147">Properly format the date when using `{DATE()}` in Markdown.</span></span>  

### <a name="dont"></a><span data-ttu-id="a1719-148">Não fazer</span><span class="sxs-lookup"><span data-stu-id="a1719-148">Don't</span></span>

- <span data-ttu-id="a1719-149">Não defina tipos de dados inválidos ao vincular valores.</span><span class="sxs-lookup"><span data-stu-id="a1719-149">Don't define invalid data types when binding values.</span></span> <span data-ttu-id="a1719-150">Para obter mais informações sobre tipos de dados, consulte [Manage The Search Schema](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema).</span><span class="sxs-lookup"><span data-stu-id="a1719-150">For more information about data types, see [Manage the Search schema](https://docs.microsoft.com/sharepoint/search/manage-the-search-schema).</span></span>
- <span data-ttu-id="a1719-151">Evite cortar o resultado na página de resultados seguindo a altura máxima do JSON de layout de resultados.</span><span class="sxs-lookup"><span data-stu-id="a1719-151">Avoid cropping the result on the result page by following the maximum height of the result layout JSON.</span></span> <span data-ttu-id="a1719-152">Se você exceder a altura máxima do layout do resultado, o resultado será cortado na página de resultados.</span><span class="sxs-lookup"><span data-stu-id="a1719-152">If you exceed the maximum height of the result layout, the result will be cropped on the result page.</span></span>
- <span data-ttu-id="a1719-153">Não use `px` valores nas propriedades do elemento.</span><span class="sxs-lookup"><span data-stu-id="a1719-153">Don't use `px` values in element properties.</span></span>
- <span data-ttu-id="a1719-154">Não use redução quando tiver a propriedade **ResultSnippet** no layout do resultado para realçar a correspondência da consulta no resultado da pesquisa.</span><span class="sxs-lookup"><span data-stu-id="a1719-154">Don't use markdown when with the **ResultSnippet** property in the result layout to highlight query match in the search result.</span></span> 

## <a name="resources"></a><span data-ttu-id="a1719-155">Recursos</span><span class="sxs-lookup"><span data-stu-id="a1719-155">Resources</span></span>

[<span data-ttu-id="a1719-156">Personalizar página de resultados de pesquisa</span><span class="sxs-lookup"><span data-stu-id="a1719-156">Customize search result page</span></span>](customize-search-page.md)

[<span data-ttu-id="a1719-157">Cartões adaptáveis</span><span class="sxs-lookup"><span data-stu-id="a1719-157">Adaptive cards</span></span>](https://docs.microsoft.com/adaptive-cards/authoring-cards/getting-started)

[<span data-ttu-id="a1719-158">Idioma do modelo de cartões adaptáveis</span><span class="sxs-lookup"><span data-stu-id="a1719-158">Adaptive Cards Template language</span></span>](https://docs.microsoft.com/adaptive-cards/templating/language)

[<span data-ttu-id="a1719-159">Esquema de cartão adaptável</span><span class="sxs-lookup"><span data-stu-id="a1719-159">Adaptive card schema</span></span>](https://adaptivecards.io/explorer/)