---
title: Configurar seu conector criado pela Microsoft para a Pesquisa da Microsoft
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar seu conector criado pela Microsoft para a Pesquisa da Microsoft
ms.openlocfilehash: 61a7d444ddc4c290b5098c327faa8e70f0ef1049
ms.sourcegitcommit: 469be70ad295a5837978d75babf5243115257f77
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49847542"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a>Visão geral da instalação dos conectores do Graph pela Microsoft 

Este artigo resume o processo básico necessário para usar o centro de administração do [Microsoft 365](https://admin.microsoft.com) para configurar qualquer um dos conectores do Graph pela Microsoft. O processo básico inclui as seguintes etapas:  
<!---Add links to each section in the doc--->

1. Adicione um conector do Graph no centro de administração do Microsoft 365.
2. Nome da conexão.
3. Definir as configurações de conexão.
4. Gerenciar permissões de pesquisa.
5. Atribuir rótulos de propriedade.
6. Gerenciar esquema.
7. Escolha as configurações de atualização.
8. Revise a conexão.

É importante observar que o processo de instalação é muito semelhante para todos os conectores do Graph pela Microsoft, mas não é exatamente o mesmo. **Além de ler este artigo, leia as informações específicas do conector para sua fonte de dados.**  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: Adicionar um conector do Graph no centro de administração do Microsoft 365

Conclua as etapas a seguir para configurar qualquer um dos conectores integrados pela Microsoft.

1. Entre em sua conta de administrador no Centro [de administração do Microsoft 365](https://admin.microsoft.com)
2. No painel de navegação, selecione **Configurações** e, em seguida, selecione **Search & inteligência.** Selecione a [guia Conectores.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors)
3. Selecione **+Adicionar** e, em seguida, selecione a fonte de dados de sua escolha no menu de opções disponíveis.

![As fontes de dados disponíveis incluem: ADLS Gen2, sites corporativos, Microsoft SQL Server, Azure SQL, banco de dados Oracle SQL, ServiceNow, compartilhamento de arquivos, Azure DevOps e MediaWiki.](media/add-connector.png)

>[! Observação:] Você pode adicionar no máximo dez conexões do Graph a cada locatário.

## <a name="step-2-name-the-connection"></a>Etapa 2: Nomear a conexão
Você precisará especificar estes atributos: 

* Nome  
* ID da conexão 
* Descrição (opcional) 

A ID de conexão cria propriedades implícitas para seu conector. Ele deve conter somente caracteres alfanuméricos e ter no máximo 32 caracteres. 

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Definir as configurações de conexão

O processo para definir as configurações de Conexão varia com base no tipo de fonte de dados. Consulte as informações específicas do Conector para o tipo de fonte de dados que você deseja adicionar ao seu locatário para concluir esta etapa no processo de configuração.  

Para saber mais sobre como se conectar a uma fonte de dados local, consulte Instalar um [gateway de dados local.](https://aka.ms/configuregateway)

## <a name="step-4-manage-search-permissions"></a>Etapa 4: Gerenciar permissões de pesquisa

As ACLs (Listas de Controle de Acesso) determinam quais usuários em sua organização podem acessar cada item de dados.  

Alguns conectores, como [o Microsoft SQL](MSSQL-connector.md) e o [Azure Data Lake Storage Gen2,](azure-data-lake-connector.md) suportam nativamente as ACLs do [Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/)

Outros conectores como [ServiceNow](servicenow-connector.md), [Azure DevOps](azure-devops-connector.md)e [Salesforce](salesforce-connector.md) suportam a sincronização de usuários e grupos que não são do Azure AD.  

## <a name="step-5-assign-property-labels"></a>Etapa 5: Atribuir rótulos de propriedade
Você pode atribuir rótulos semânticos às suas propriedades de origem na página "Atribuir rótulos de propriedade". Rótulos são marcas bem conhecidas fornecidas pela Microsoft que fornecem significado semântico. Eles permitem que a Microsoft integre os dados do conector às experiências do Microsoft 365, como pesquisa aprimorada, cartões de pessoas, descoberta inteligente e muito mais.  

A tabela a seguir lista os rótulos com suporte no momento e suas descrições.  

Rótulo | Descrição
--- | ---  
**título** | O título do item que você deseja mostrar na pesquisa e outras experiências 
**url** | A URL de destino do item no sistema de origem 
**createdBy** | Nome da pessoa que criou o item 
**lastModifiedBy** | Nome da pessoa que editou o item mais recentemente 
**autores** | Nome das pessoas que participaram/colaboraram no item 
**createdDateTime** | Quando o item foi criado 
**lastModifiedDateTime** | Quando o item foi editado mais recentemente 
**fileName** | Nome do item de arquivo 
**FileExtension** | Tipo de item de arquivo, como .pdf ou .word 

As propriedades nesta página são pré-selecionadas com base em sua fonte de dados, mas você pode alterar essa seleção se houver uma propriedade diferente que seja mais adequada para um rótulo específico.  

O título **do rótulo** é o rótulo mais importante. É altamente **recomendável que** você tenha uma propriedade atribuída a esse rótulo para que sua conexão participe da experiência [do cluster de resultados.](result-cluster.md)

O mapeamento incorreto de rótulos causará uma experiência de pesquisa prejudicada. Não há problema para alguns rótulos não ter uma propriedade atribuída a ele.  

## <a name="step-6-manage-schema"></a>Etapa 6: Gerenciar esquema

### <a name="content-property"></a>Propriedade Content

É altamente recomendável que você selecione uma **Propriedade de Conteúdo" no menu suspenso de opções ou mantenha o padrão se uma estiver presente. Essa propriedade é usada para indexação de texto completo de conteúdo, geração de trecho de página de resultados de pesquisa, participação do [cluster](result-cluster.md) de resultados, detecção de idioma, suporte a HTML/texto, classificação e relevância e formulação de consulta.

Se você selecionar uma propriedade de conteúdo, você terá a opção de usar o **ResultSnippet** de propriedade gerada pelo sistema ao [criar seu tipo de resultado.](customize-results-layout.md) Essa propriedade serve como um espaço reservado para os trechos dinâmicos gerados a partir da propriedade de conteúdo no momento da consulta. Se você usar essa propriedade em seu tipo de resultado, os trechos de código serão gerados nos resultados da pesquisa.

### <a name="creating-aliases-for-source-properties"></a>Criando aliases para propriedades de origem

Você pode adicionar aliases às suas propriedades na coluna "Alias" na página "Gerenciar esquema". Aliases são nomes amigáveis para suas propriedades. Eles são usados em consultas e na criação de filtros. Eles também são usados para normalizar as propriedades de origem de várias conexões de forma que tenham o mesmo nome. Dessa forma, você pode criar um único filtro para uma vertical com várias conexões. Consulte [Personalizar a página de resultados da pesquisa](customize-search-page.md) para obter mais informações.  

### <a name="search-schema-attributes"></a>Atributos de esquema de pesquisa

Você pode definir os atributos de esquema de pesquisa para controlar a funcionalidade de pesquisa de cada propriedade de origem. Um esquema de pesquisa ajuda a determinar quais resultados são exibidos na página de resultados da pesquisa e quais informações os usuários finais podem exibir e acessar.

Os atributos de esquema **de** pesquisa **incluem pesquisável, queryable**, **recuperável** e **refinável.** A tabela a seguir lista cada um dos atributos que os conectores do Microsoft Graph suportam e explica suas funções.

Atributo de esquema de pesquisa | Função | Exemplo
--- | --- | ---
PESQUISÁVEL | Torna o conteúdo de texto de uma propriedade pesquisável. O conteúdo da propriedade é incluído no índice de texto completo. | Se a propriedade for **título**, uma consulta para **Enterprise** retornará respostas que contenham a palavra **Enterprise** em qualquer texto ou título.
QUERYABLE | Pesquisa por consulta por uma combinação de uma propriedade específica. O nome da propriedade pode ser especificado na consulta de forma programática ou verbatim. |  Se a **propriedade Title** for queryable, a consulta **Title: Enterprise** será suportada. 
RECUPERÁVEL | Somente as propriedades recuperáveis podem ser usadas no tipo de resultado e exibidas no resultado da pesquisa. |
REFINÁVEL | Propriedades refináveis podem ser usadas como na página de resultados da Pesquisa da Microsoft. | Os usuários em sua organização podem [filtrar](custom-filters.md) **por lastModifiedDateTime** na página de resultados da pesquisa se a propriedade for marcada como refinável durante a configuração da conexão

Para todos os conectores, exceto o conector de compartilhamento de arquivos, os tipos personalizados devem ser definidos manualmente. Para ativar os recursos de pesquisa para cada campo, você precisa de um esquema de pesquisa mapeado para uma lista de propriedades. O assistente de conexão seleciona automaticamente um esquema de pesquisa com base no conjunto de propriedades de origem que você escolher. Você pode modificar esse esquema selecionando as caixas de seleção de cada propriedade e atributo na página de esquema de pesquisa.

![O esquema de um conector pode ser personalizado adicionando ou removendo funções de consulta, pesquisa e recuperação.](media/manageschema.png)
 
### <a name="restrictions-and-recommendations-for-search-schema-settings"></a>Restrições e recomendações para configurações de esquema de pesquisa

* A **propriedade** de conteúdo é pesquisável somente. Uma vez selecionada na lista suspenso, essa propriedade não pode ser marcada **como recuperável** ou **queryable**.

* Problemas de desempenho significativos ocorrem quando os resultados da pesquisa são renderizar com a **propriedade de** conteúdo. Um exemplo é o **campo de** conteúdo texto para um artigo da base de dados de conhecimento [do ServiceNow.](https://www.servicenow.com)

* Somente propriedades marcadas como renderização recuperável nos resultados da pesquisa e podem ser usadas para criar tipos de resultados modernos (MRTs).

* Somente as propriedades de cadeia de caracteres podem ser marcadas como pesquisáveis.

> [!NOTE]
> Depois de criar uma conexão, **você não pode** modificar o esquema. Para fazer isso, você precisa excluir sua conexão e criar uma nova.

## <a name="step-7-refresh-settings"></a>Etapa 7: Atualizar configurações

O intervalo de atualização determina com que frequência seus dados são sincronizados entre a fonte de dados e a Pesquisa da Microsoft. Cada tipo de fonte de dados tem um conjunto diferente de agendamentos de atualização ideais com base na frequência com que os dados são modificados e no tipo de modificações.

Há dois tipos de intervalos  de atualização, que são Atualização completa e atualização **incremental,** mas as atções incrementais não estão disponíveis para algumas fontes de dados.

Com uma atualização completa, o mecanismo de pesquisa processa e indexa cada item na fonte de conteúdo, independentemente dos rastreamentos anteriores. Uma atualização completa funciona melhor para estas situações:

* Detectando exclusões de dados.
* A atualização incremental falhou ao atualizar o conteúdo devido a erros.
* AS ACLs foram modificadas.
* As regras de rastreamento foram modificadas.
* Quando o esquema da conexão tiver sido atualizado (as atualizações de esquema ainda não são suportadas)

Com uma **atualização Incremental,** o mecanismo de pesquisa pode processar e indexar somente os itens que foram criados ou modificados desde o último rastreamento bem-sucedido. Portanto, nem todos os dados na fonte de conteúdo são indexados outra vez. As atualizações incrementais funcionam melhor para detectar conteúdo, metadados, permissão e outras atualizações.

As atções incrementais são muito mais rápidas do que as atções completas porque os itens inalterados não são processados. No entanto, se você optar por executar atções incrementais, ainda precisará executar atções completas periodicamente para manter uma sincronização de dados precisa entre a fonte de conteúdo e o índice de pesquisa.

![Configurações de rastreamento incremental e de intervalo de rastreamento completo mostrando Incremental em 15 minutos e Rastreamento completo em 1 semana.](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a>Etapa 8: Analisar a conexão

Você pode revisar toda a configuração e editar as configurações conforme necessário antes de concluir a conexão. **Certifique-se de ler as informações específicas do conector para sua fonte de dados, caso ainda não tenha feito isso.** Selecione **Concluir atualização quando** estiver pronto para concluir a conexão.

## <a name="how-do-i-know-the-connection-setup-worked"></a>Como saber se a configuração da conexão funcionou?

Vá para a lista de suas conexões **publicadas** na guia Conectores no centro [de administração.](https://admin.microsoft.com) Para saber como fazer atualizações e exclusões, consulte [Gerenciar seu conector.](manage-connector.md)
