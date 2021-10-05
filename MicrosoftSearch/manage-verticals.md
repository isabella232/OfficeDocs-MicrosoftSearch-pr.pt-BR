---
title: Gerenciar verticalidades de pesquisa
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
ROBOTS: NOINDEX
description: Gerenciar as verticais de pesquisa na página de resultados
ms.openlocfilehash: 89887b6ce5391d2473692504efa3c0eb35407b48
ms.sourcegitcommit: 967a02ee932f8a6cee70cfd78bb0c8b1b78d07c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127752"
---
# <a name="manage-search-verticals"></a>Gerenciar verticalidades de pesquisa

As verticais de pesquisa são guias na página de resultados da pesquisa que mostram resultados de um tipo específico ou de fontes selecionadas. Por exemplo, a vertical Arquivos mostra resultados classificados como arquivos e facilita para os usuários que estão procurando encontrar documentos. Você pode personalizar verticais em Pesquisa da Microsoft para atender às necessidades de sua organização ou departamentos individuais.

Você pode gerenciar verticais em dois níveis:

- **Nível da** organização – Uma vertical no nível da organização [](https://sharepoint.com/) aparece na página de resultados da pesquisa quando os usuários pesquisam na página inicial do SharePoint, [Microsoft Office](https://office.com)e Pesquisa da Microsoft no [Bing](https://bing.com)
- **Nível do** site – Uma vertical no nível do site aparece na página de resultados da pesquisa quando os usuários pesquisam em um SharePoint site. Por exemplo, talvez você queira permitir que seus funcionários do serviço de atendimento ao cliente pesquisem incidentes de Gravidade 1 diretamente do site de SharePoint do departamento.

## <a name="understanding-search-verticals"></a>Noções básicas sobre as verticais de pesquisa

Pesquisa da Microsoft tem dois tipos de verticais, fora da caixa e verticais personalizadas. Verticalmente, como Todos, Arquivos e Pessoas, crie acesso fácil aos resultados de pesquisa mais usados.

Opções de configuração adicionais são oferecidas em verticais personalizadas e podem ser usadas para criar a melhor experiência para seus usuários.

Você pode adicionar verticais de pesquisa relevantes à sua organização. Por exemplo, você pode criar uma vertical para conteúdo relacionado ao marketing e outra para vendas, com base no tipo de informação que cada departamento precisa. As verticais podem ser adicionadas para mostrar resultados de conteúdo indexado por conectores Graph [,](connectors-overview.md)mas você não pode criar uma vertical para conteúdo que reside em SharePoint.

## <a name="create-search-verticals"></a>Criar vertical de pesquisa

A experiência de gerenciamento vertical é orientada pelo assistente, você é orientado por etapas para definir o nome vertical, a fonte de conteúdo e o escopo do conteúdo a ser pesquisado. Você pode usar um conjunto limitado de [KQL (Keyword Query Language)](#keyword-query-language-kql) para definir o escopo da pesquisa vertical para uma determinada fonte de conteúdo.

A seguir estão as etapas para criar as verticais personalizadas no Pesquisa da Microsoft em SharePoint [home,](https://sharepoint.com/) [Office](https://office.com/)ou [Bing](https://bing.com/).  

### <a name="manage-organization-level-verticals"></a>Gerenciar verticais no nível da organização

1. Na [Centro de administração do Microsoft 365](https://admin.microsoft.com), vá para a página [**Verticais**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/verticals) na seção **Personalização.**
1. Clique **em adicionar** para criar um novo vertical.
1. Depois de passar pelas etapas de configuração, você pode revisar e salvar a vertical.  

### <a name="manage-site-level-verticals"></a>Gerenciar verticais no nível do site

1. No site SharePoint onde você deseja gerenciar verticais, abra o painel de configurações clicando na engrenagem.
1. Selecione **Informações do** site e selecione Exibir todas as **configurações do site.**  
1. Procure a seção Pesquisa da Microsoft e selecione **Configurar configurações de pesquisa**.
1. No painel de navegação, vá para Experiência personalizada e selecione **Verticals**.
1. Clique **em adicionar** para criar um novo vertical.
1. Depois de definir sua configuração, você pode revisar e salvar a vertical.  

## <a name="view-the-vertical-in-search-results"></a>Exibir a vertical nos resultados da pesquisa

Um [layout de resultado de pesquisa](manage-result-types.md) é necessário para Graph resultados do conector para renderizar na página vertical da pesquisa. Ao garantir que o layout de resultados apropriado está presente, você pode habilitar a pesquisa vertical. Depois de habilitar uma vertical, há um atraso de algumas horas antes de poder exibi-lo. Você pode anexar cacheClear=true à URL no SharePoint e Office para exibir a vertical imediatamente. Em Bing, &features=uncachedVerticals à URL vertical do trabalho para exibir a vertical imediatamente.

> [!NOTE]
> As verticais adicionadas não são visíveis SharePoint [e](https://sharepoint.com/) [Office](https://office.com) quando exibidas de navegadores da Web móveis.

## <a name="advanced-configuration-options"></a>Opções de configuração avançadas

### <a name="multiple-connections-in-a-vertical"></a>Várias conexões em um vertical

Uma pesquisa vertical pode surgir resultados de várias fontes de conector. Essa opção oferece flexibilidade ao projetar sua página de resultados de pesquisa. O processo de instalação vertical permite que os administradores selecionem várias conexões na etapa "Fonte de conteúdo".

Se você nomear com precisão o máximo possível de *rótulos* semânticos, essa experiência será aprimorada. Você adiciona rótulos semânticos no ponto de definição e ingestão de esquema. [Consulte mais sobre como criar e gerenciar rótulos semânticos.](configure-connector.md#step-6-assign-property-labels)
[Aqui](configure-connector.md#step-6-assign-property-labels) estão informações adicionais sobre como criar e gerenciar rótulos semânticos.

> [!NOTE]
> - As várias conexões em um recurso vertical estão atualmente em visualização. Para obter mais informações, consulte [Conectores recursos de visualização](connectors-overview.md#what-are-the-preview-features).
> - Uma conexão pode ser adicionada como uma fonte de conteúdo em uma única vertical. Não é possível usar conexões em várias verticais.

Para configurar uma consulta para uma pesquisa vertical onde várias fontes de conexão foram adicionadas, use propriedades de origem comuns para criar a consulta.

### <a name="keyword-query-language-kql"></a>Idioma de consulta de palavra-chave (KQL)

Uma consulta pode ser adicionada a uma vertical para restringir os resultados mostrados na pesquisa vertical usando [KQL (Keyword Query Language)](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference) (suporte limitado). Esta página lista as propriedades disponíveis. Recomendamos que você use palavras-chave de texto livre e restrições de propriedade com operadores boolianas para criar o KQL. Operadores de classificação dinâmica, como XRANK, operadores de proximidade e palavras não são suportados.

Aqui estão algumas consultas de exemplo.

|Cenário         | Consulta   |  
| --------- | ------ |
|Excluindo resultados de sites arquivados           |NOT (path:http//contoso.sharepoint.com/archive OR path:http/contoso.sharepoint.com/CompanyArchive)|
| Excluindo resultados com base na propriedade tipo de arquivo | NOT(FileType:htm)|  

#### <a name="profile-query-variables"></a>Variáveis de consulta de perfil

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
> - O recurso de variáveis de consulta de perfil está atualmente em visualização. Para obter mais informações sobre visualização, consulte [Conectores recursos de visualização](connectors-overview.md#what-are-the-preview-features).

## <a name="troubleshooting"></a>Solução de problemas

Aqui está uma lista de problemas comuns que você pode encontrar e ações para corrigi-los.

|Problema  |Ação  |
|---------|---------|
| Vejo uma mensagem de erro "Algo deu errado" na vertical. | Os tipos vertical e de resultado são necessários para concluir a instalação. Certifique-se de que ambos estão definidos para a fonte de conteúdo. |
| Não vejo fontes de conteúdo na página vertical. | Certifique-se de ter configurado conectores e dados indexados.   |
