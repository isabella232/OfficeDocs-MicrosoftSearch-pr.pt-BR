---
title: Configurar seu conector criado pela Microsoft para a pesquisa da Microsoft
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
description: Configurar seu conector criado pela Microsoft para a pesquisa da Microsoft
ms.openlocfilehash: 86ddf0387e3d00a005f25207a322c8470799b76b
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367600"
---
<!-- markdownlint-disable no-trailing-punctuation -->

# <a name="setup-overview-for-graph-connectors-by-microsoft"></a>Visão geral da configuração dos conectores do Graph pela Microsoft 

Este artigo resume o processo básico necessário para usar o [centro de administração do Microsoft 365](https://admin.microsoft.com) para configurar qualquer um dos conectores de gráfico da Microsoft. O processo básico inclui as seguintes etapas:  
<!---Add links to each section in the doc--->

1. Adicione um conector de gráfico no centro de administração do Microsoft 365.
2. Nomear a conexão.
3. Definir as configurações de conexão.
4. Gerenciar permissões de pesquisa.
5. Atribuir rótulos de propriedade.
6. Gerenciar o esquema.
7. Escolha Atualizar configurações.
8. Revise a conexão.

É importante observar que o processo de instalação é muito semelhante para todos os conectores do Graph pela Microsoft, mas não é exatamente o mesmo. **Além de ler este artigo, não deixe de ler o conector específico para sua fonte de dados.**  

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: adicionar um conector de gráfico no centro de administração do Microsoft 365

Conclua as seguintes etapas para configurar qualquer um dos conectores criados pela Microsoft.

1. Entre em sua conta de administrador no [centro de administração do Microsoft 365](https://admin.microsoft.com)
2. No painel de navegação, selecione **configurações** e, em seguida, selecione **pesquisa & inteligência**. Selecione a [guia conectores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors).
3.  Selecione **+ Adicionar** e, em seguida, selecione a fonte de dados de sua escolha no menu de opções disponíveis.

![As fontes de dados disponíveis incluem: ADLS Gen2, sites corporativos, Microsoft SQL Server, Azure SQL, banco de dados SQL Oracle, ServiceNow, compartilhamento de arquivos, Azure DevOps e MediaWiki.](media/add-connector.png)

>[! Observação:] você pode adicionar no máximo dez conexões de gráfico a cada locatário.

## <a name="step-2-name-the-connection"></a>Etapa 2: nomear a conexão
Será necessário especificar esses atributos: 

* Nome  
* ID de conexão 
* Descrição (opcional) 

A ID de conexão cria propriedades implícitas para seu conector. Ele deve conter apenas caracteres alfanuméricos e ter no máximo 32 caracteres. 

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: definir as configurações de conexão

O processo para definir as configurações de conexão varia de acordo com o tipo de fonte de dados. Confira as informações específicas do conector para o tipo de fonte de dados que você deseja adicionar ao seu locatário para concluir esta etapa no processo de instalação.  

Para saber mais sobre como se conectar a uma fonte de dados local, consulte [install an local data gateway](https://aka.ms/configuregateway).

## <a name="step-4-manage-search-permissions"></a>Etapa 4: gerenciar permissões de pesquisa

As listas de controle de acesso (ACLs) determinam quais usuários em sua organização podem acessar cada item de dados.  

Alguns conectores, como [o Microsoft SQL e o](MSSQL-connector.md) [Azure data Lake Storage Gen2](azure-data-lake-connector.md) dão suporte nativo às ACLs [do Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/) .

Outros conectores como o [ServiceNow](servicenow-connector.md), o [Azure DevOps](azure-devops-connector.md)e o [Salesforce](salesforce-connector.md) dão suporte à sincronização de usuários e grupos não do Azure AD.  

## <a name="step-5-assign-property-labels"></a>Etapa 5: atribuir rótulos de propriedade
Você pode atribuir rótulos de semântica às suas propriedades de origem na página "atribuir rótulos de propriedade". Os rótulos são marcas conhecidas fornecidas pela Microsoft que oferecem significado semântico. Eles permitem que a Microsoft Integre seus dados do conector às experiências do Microsoft 365, como pesquisa avançada, cartões de pessoas, descoberta inteligente e muito mais.  

A tabela a seguir lista os rótulos atualmente suportados e suas descrições.  

Rótulo | Descrição
--- | ---  
**título** | O título do item que você deseja exibir na pesquisa e em outras experiências 
**url** | A URL de destino do item no sistema de origem 
**createdBy** | Nome da pessoa que criou o item 
**lastModifiedBy** | Nome da pessoa que editou o item mais recentemente 
**autores** | Nome das pessoas que participaram/colaboraram com o item 
**createdDateTime** | Quando o item foi criado 
**lastModifiedDateTime** | Quando o item foi editado mais recentemente 
**fileName** | Nome do item de arquivo 
**FileExtension** | Tipo de item de arquivo, como. pdf ou. Word 

As propriedades nessa página são previamente selecionadas com base na sua fonte de dados, mas você pode alterar essa seleção se houver uma propriedade diferente mais adequada a um rótulo específico.  

O **título** do rótulo é o rótulo mais importante. É **altamente recomendável** que você tenha uma propriedade atribuída a esse rótulo para que sua conexão participe da [experiência de cluster de resultados](result-cluster.md).

O mapeamento incorreto de rótulos causará uma experiência de pesquisa deteriorada. Há algum problema para alguns rótulos não terem uma propriedade atribuída a ele.  

## <a name="step-6-manage-schema"></a>Etapa 6: gerenciar o esquema

### <a name="content-property"></a>Propriedade Content

É altamente recomendável que você selecione uma propriedade de conteúdo * * no menu suspenso de opções ou mantenha o padrão, se houver um. Essa propriedade é usada para indexação de texto completo de conteúdo, geração de trecho de página de resultados de pesquisa, participação no [cluster de resultados](result-cluster.md) , detecção de idioma, suporte a HTML/texto, classificação e relevância e formulação de consulta.

Se você selecionar uma propriedade de conteúdo, terá a opção de usar a propriedade gerada pelo sistema **ResultSnippet** ao [criar seu tipo de resultado](customize-results-layout.md). Essa propriedade serve como um espaço reservado para os trechos dinâmicos gerados a partir da propriedade Content no momento da consulta. Se você usar essa propriedade no tipo de resultado, os trechos de código serão gerados nos resultados da pesquisa.

### <a name="creating-aliases-for-source-properties"></a>Criando aliases para propriedades de origem

Você pode adicionar aliases às suas propriedades na coluna "alias" na página "gerenciar esquema". Aliases são nomes amigáveis para suas propriedades. Eles são usados em consultas e na criação de filtros. Eles também são usados para normalizar as propriedades de origem de várias conexões, de forma que tenham o mesmo nome. Dessa forma, você pode criar um único filtro para uma vertical com várias conexões. Consulte [Personalizar a página de resultados da pesquisa](customize-search-page.md) para obter mais informações.  

### <a name="search-schema-attributes"></a>Atributos de esquema de pesquisa

Você pode definir os atributos de esquema de pesquisa para controlar a funcionalidade de pesquisa de cada propriedade de origem. Um esquema de pesquisa ajuda a determinar quais resultados são exibidos na página de resultados da pesquisa e quais informações os usuários finais podem exibir e acessar.

Os atributos de esquema de pesquisa incluem **pesquisáveis**, **consultáveis**, **recuperáveis** e **refinável**. A tabela a seguir lista cada um dos atributos aos quais os conectores do Microsoft Graph dão suporte e explica suas funções.

Atributo de esquema de pesquisa | Função | Exemplo
--- | --- | ---
PESQUISÁVEIS | Torna o conteúdo de texto de uma propriedade pesquisável. O conteúdo da propriedade está incluído no índice de texto completo. | Se a propriedade for **título**, uma consulta de **empresa** retornará as respostas que contenham a palavra **Enterprise** em qualquer texto ou título.
Question | Pesquisa por consulta para uma correspondência de uma determinada propriedade. O nome da propriedade pode ser especificado na consulta de forma programática ou textual. |  Se a propriedade **title** for consultável, o título da consulta **: Enterprise** será suportado. 
RECUPERÁVEIS | Somente as propriedades recuperáveis podem ser usadas no tipo de resultado e no resultado da pesquisa. |
REFINÁVEL | As propriedades refinável podem ser usadas como na página de resultados de pesquisa da Microsoft. | Os usuários da sua organização podem [Filtrar](custom-filters.md) por **lastModifiedDateTime** na página de resultados da pesquisa se a propriedade estiver marcada refinável durante a configuração da conexão

Para todos os conectores, exceto o conector de compartilhamento de arquivos, os tipos personalizados devem ser definidos manualmente. Para ativar os recursos de pesquisa para cada campo, você precisa de um esquema de pesquisa mapeado para uma lista de propriedades. O assistente de conexão seleciona automaticamente um esquema de pesquisa com base no conjunto de propriedades de origem que você escolher. Você pode modificar esse esquema marcando as caixas de seleção de cada propriedade e atributo na página de esquema de pesquisa.

![O esquema de um conector pode ser personalizado adicionando ou removendo funções de consulta, pesquisa e recuperação.](media/manageschema.png)
 
### <a name="restrictions-and-recommendations-for-search-schema-settings"></a>Restrições e recomendações para configurações de esquema de pesquisa

* A propriedade de **conteúdo** só é pesquisável. Uma vez selecionada na lista suspensa, esta propriedade não pode ser marcada como **recuperável** ou **consultável**.

* Problemas de desempenho significativos ocorrem quando os resultados da pesquisa renderizam com a propriedade de **conteúdo** . Um exemplo é o campo de conteúdo de **texto** para um artigo da base de dados de conhecimento do [ServiceNow](https://www.servicenow.com) .

* Somente as propriedades marcadas como recuperáveis são renderizadas nos resultados da pesquisa e podem ser usadas para criar tipos de resultados modernos (MRTs).

* Somente as propriedades de cadeia de caracteres podem ser marcadas como pesquisáveis.

> [!NOTE]
> Após criar uma conexão, você **não poderá** modificar o esquema. Para fazer isso, você precisa excluir sua conexão e criar uma nova.

## <a name="step-7-refresh-settings"></a>Etapa 7: atualizar as configurações

O intervalo de atualização determina com que frequência os dados são sincronizados entre a fonte de dados e a pesquisa da Microsoft. Cada tipo de fonte de dados tem um conjunto diferente de agendas de atualização ideais com base na frequência com que os dados são modificados e o tipo de modificações.

Há dois tipos de intervalos de atualização, que são **atualização completa** e **atualização incremental**, mas atualizações incrementais não estão disponíveis para algumas fontes de dados.

Com uma atualização completa, o mecanismo de pesquisa processa e indexa todos os itens da fonte de conteúdo, independentemente dos rastreamentos anteriores. Uma atualização completa funciona melhor para estas situações:

* Detectar exclusões de dados.
* A atualização incremental não pôde atualizar o conteúdo devido a erros.
* ACLs foram modificadas.
* As regras de rastreamento foram modificadas.
* Quando o esquema da conexão foi atualizado (ainda não há suporte para atualizações de esquema)

Com uma **atualização incremental**, o mecanismo de pesquisa pode processar e indexar somente os itens que foram criados ou modificados desde o último rastreamento bem-sucedido. Portanto, nem todos os dados na fonte de conteúdo são re-indexados. As atualizações incrementais funcionam melhor para detectar conteúdo, metadados, permissões e outras atualizações.

As atualizações incrementais são muito mais rápidas do que as atualizações completas porque itens inalterados não são processados. No entanto, se você optar por executar atualizações incrementais, ainda será necessário executar atualizações completas periodicamente para manter uma sincronização de dados precisa entre a fonte de conteúdo e o índice de pesquisa.

![Configurações de rastreamento incremental e intervalo de rastreamento completo mostrando a incremental em 15 minutos e rastreamento completo em 1 semana.](media/refreshschedule.png)

<!---Change screenshot for one that shows both options in new UI (try ServiceNow)--->

## <a name="step-8-review-connection"></a>Etapa 8: revisar a conexão

Você pode examinar a configuração inteira e editar as configurações conforme necessário antes de concluir a conexão. **Certifique-se de ler as informações específicas do conector para sua fonte de dados, se você ainda não tiver feito isso.** Selecione **concluir atualização** quando você estiver pronto para concluir a conexão.

## <a name="how-do-i-know-the-connection-setup-worked"></a>Como saber se a configuração de conexão funcionou?

Vá para a lista de suas conexões publicadas na guia **conectores** do [centro de administração](https://admin.microsoft.com). Para saber como fazer atualizações e exclusões, confira [gerenciar o conector](manage-connector.md).
