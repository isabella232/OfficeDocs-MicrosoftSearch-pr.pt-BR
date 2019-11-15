---
title: Torne o conteúdo fácil de encontrar com a Pesquisa da Microsoft
ms.author: anfowler
author: adefowler
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Crie indicadores, locais e itens de P e R para facilitar a localização do conteúdo da sua organização.
ms.openlocfilehash: 605610264e2068deb6215c3157efc24cf0b0a2fd
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626824"
---
# <a name="make-content-easy-to-find"></a>Tornar o conteúdo fácil de encontrar

A Pesquisa da Microsoft ajuda os usuários a encontrar conteúdo relevante. É uma maneira segura de Pesquisar o conteúdo da Web e de intranet. Esse tipo de integração através da Web e de organizações só está disponível na Microsoft. Com o Microsoft Search, os administradores podem usar o conhecimento de uma organização para facilitar para os usuários a localização de conteúdo relevante. 

## <a name="components-that-find-content"></a>Componentes que localizam conteúdo
No Microsoft Search, os administradores criam [indicadores](manage-bookmarks.md), [PowerApps](integrate-powerapps.md), [Q&A](manage-qas.md)e [locais](manage-locations.md) que facilitam a localização do conteúdo. Cada um desses componentes de pesquisa inclui um título, uma URL e um conjunto de palavras-chave que o acionam.

## <a name="bookmarks"></a>Indicadores
Você pode criar [indicadores](manage-bookmarks.md) em apenas algumas etapas. Cada indicador inclui um título, uma URL e um conjunto de palavras-chave que o acionam. Um indicador pode ter várias palavras-chave e vários indicadores podem compartilhar a mesma palavra-chave. Mas palavras-chave reservadas não podem ser compartilhadas. Quando você cria ou modifica um indicador, o índice de pesquisa é atualizado e o indicador fica imediatamente disponível para os usuários.

Se sua organização **promoveu os resultados** configurados no [SharePoint](http://sharepoint.com/), você pode importar esses resultados para o Microsoft Search. Com os resultados promovidos, você pode rapidamente preencher os resultados da pesquisa, tornar o conteúdo disponível para os usuários e tornar a pesquisa da Microsoft mais eficiente assim que você configurá-la. Recomendamos que você use os resultados promovidos do SharePoint como referência para entender como nomear e criar resultados de pesquisa relevantes. 

### <a name="add-or-edit-bookmarks-by-using-browser-extensions"></a>Adicionar ou editar indicadores usando extensões do navegador
Os administradores de pesquisa podem criar conteúdo de pesquisa facilmente usando extensões de navegador. Para adicionar o site como um indicador, instale a extensão do navegador. Em seguida, vá para o site e adicione-o como um indicador. Para saber mais, confira [gerenciar indicadores](manage-bookmarks.md).

No momento, as extensões do navegador estão disponíveis para [o Microsoft Edge e o](https://www.microsoft.com/windows/microsoft-edge) [Google Chrome](https://www.google.com): 
- Para baixar a extensão de borda, vá para a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Para baixar a extensão Chrome, vá para o [repositório da Web Chrome](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="powerapps"></a>PowerApps

Ao adicionar o [PowerApps](integrate-powerapps.md) existente aos seus [indicadores](manage-bookmarks.md), os usuários podem concluir tarefas como inserir tempo de férias ou relatar despesas. 

Com o [PowerApps](integrate-powerapps.md), você pode criar aplicativos de negócios que são executados em um navegador ou em um telefone ou Tablet. Nenhuma experiência de codificação é necessária. O PowerApps funciona em qualquer navegador e em qualquer dispositivo. Elas levam menos de um minuto para serem adicionadas. Para saber mais sobre o PowerApps, consulte estes artigos:
- [Aprendizado guiado](https://docs.microsoft.com/learn/browse/?products=powerapps)
- [Documentação do PowerApps](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid)
- [Página inicial do PowerApps](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Adicionar um PowerApp a um indicador

1. Encontre a [ID do aplicativo](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) para o PowerApp que você deseja adicionar.
1. No [centro de administração](https://admin.microsoft.com)do Microsoft 365, vá para **configurações** > de**pesquisa da Microsoft**. 
1. Adicione um indicador ou encontre um indicador existente ao qual você deseja adicionar um PowerApp.
1. Em **configurações de indicador**, selecione **aplicativo de energia**. Em seguida, selecione **Adicionar um aplicativo de energia**.
1. Insira a **ID do aplicativo**. A altura e a largura se ajustam automaticamente. Os [indicadores](manage-bookmarks.md) podem dar suporte a orientações retrato e paisagem, mas atualmente o tamanho não pode ser alterado. Para facilitar o teste, a visualização do indicador mostra um PowerApp totalmente funcional.
1. Selecione **Publicar** ou **Salvar em Rascunhos**.

## <a name="qa"></a>P e R

Criar um [&](manage-qas.md) é como criar [indicadores](manage-bookmarks.md). Com o Q&A, você pode fornecer respostas para as perguntas dos usuários em vez de apenas um link para a página da Web. Você pode formatar as respostas em Rich Text usando as ferramentas disponíveis. Se um indicador e um Q&um compartilham a mesma palavra-chave, o resultado do indicador é mostrado primeiro. Como indicadores, o Q&um índice é atualizado imediatamente após adicionar ou alterar um Q&A. 

### <a name="supported-html-tags"></a>Marcas HTML com suporte

Você pode usar o conteúdo HTML ou adicionar marcas HTML à sua resposta ou descrição. Damos suporte a essas marcas HTML:
 
- blockquote
- div
- em
- h1, h2, h3 e h4
- ol, ul e li
- p
- pre
- span
- strong
- table, thead, tbody, tr, th e td
- u
- a
- code
- br
- hr
- img

Marcas sem suporte são ignoradas ou exibidas como texto. Certifique-se de visualizar seus cartões.

> [!Note]
> Você não pode importar Q&itens se houver erros no arquivo de modelo. Para evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente e inclua todas as informações necessárias. Confira mais informações sobre como [evitar erros de importação](#prevent-import-errors).

## <a name="locations"></a>Locais

Com os [locais](manage-locations.md), os usuários podem encontrar endereços e localizar os prédios da sua organização. O recurso **locais** fornece um local preciso para escritórios, campus e prédios, bem como orientações e navegação. Para obter melhores resultados, os administradores precisam adicionar todos os locais importantes de suas organizações à pesquisa da Microsoft. Ao contrário dos [indicadores](manage-bookmarks.md) e [p&a](manage-qas.md), o índice de locais não é atualizado imediatamente. Pode levar várias horas para que os locais novos ou alterados apareçam nos resultados da pesquisa.

## <a name="get-started"></a>Introdução
Para descobrir o que os usuários precisam e tornar essas informações fáceis de descobrir, experimente alguns destes métodos:

- Use os registros de pesquisa da intranet para saber quais sites e páginas recebem mais tráfego.
- Saiba quais aplicativos, sites e ferramentas são usados diariamente ou semanalmente.
- Encontre links diretos para benefícios dos funcionários.
- Encontre políticas e processos dos quais os usuários precisam estar cientes.
- Decida quem é o contato dos usuários para obter suporte e como eles fazem isso.
- Obtenha informações que sejam necessárias periodicamente ou com base nos ciclos de negócios. Um exemplo é que as pessoas que procuram ferramentas para agendar atualizações financeiras por tempo ou trimestralmente.
- Coletar políticas para usuários regionais ou móveis. Os exemplos são benefícios que variam de acordo com o local.
- Determinar sites internos e informações para pesquisas comuns na Web. Os exemplos são tráfego, informações de trânsito públicas, clima local, descontos disponíveis em parceiros corporativos e programas de integridade e adequação.
- Encontre informações sobre eventos, conferências ou confraternizações patrocinados pela empresa.
- Pesquise sobre questões comuns de TI, RH e suporte, além de perguntas frequentes (FAQs) e respostas.

## <a name="involve-smes-and-users"></a>Envolver SMEs e usuários
Em uma organização, os usuários pesquisam um intervalo de tópicos simples e complexos. Exemplos simples são endereços do Office e benefícios do funcionário. Exemplos complexos são novos processos de trabalho, informações técnicas e conteúdo de instruções. Para criar ou encontrar uma ampla variedade de conteúdo, você precisa de experiência em diferentes campos, assuntos e tecnologias. 

A maioria dos administradores de pesquisa não têm conhecimento específico sobre cada assunto. Para dimensionar a quantidade de conteúdo disponível sem a ajuda de fora dos recursos, procure a expertise e o conhecimento de outras pessoas em sua organização.

### <a name="get-content-from-smes"></a>Obter conteúdo de SMEs
Aproveite os especialistas no assunto (SMEs) em sua organização, incluindo especialistas de RH, suporte, vendas, tecnologia e outras áreas importantes. O SMEs pode contribuir com o conteúdo diretamente se você adicioná-los como editores de pesquisa da Microsoft. 

### <a name="involve-your-users"></a>Envolva seus usuários
Peça aos usuários para sugerir recursos para os quais criar indicadores. Solicite também aos usuários que relatem erros como links rompidos ou inválidos.

## <a name="set-up-components"></a>Configurar componentes
Para adicionar ou editar [marcadores](manage-bookmarks.md)únicos ou em massa, [p&A](manage-qas.md)e [locais](manage-locations.md), execute as etapas nas seções a seguir. 

### <a name="add-or-edit-a-single-bookmark-qa-or-location-component"></a>Adicionar ou editar um único indicador, Q&um ou componente de local
1. No [centro de administração](https://admin.microsoft.com)do Microsoft 365, vá para **configurações** > de**pesquisa da Microsoft**. Selecione a guia nomeada do componente. A guia **marcadores** está selecionada por padrão.
1. Para adicionar um componente, selecione **Adicionar novo**. 
1. Para editar um componente, selecione o indicador na lista componente relevante. 
1. À medida que você adiciona ou edita as informações, a visualização é atualizada automaticamente.

### <a name="bulk-add-or-edit-components"></a>Adicionar ou editar componentes em massa
Com os recursos de **importação** e **exportação** , os administradores de pesquisa podem criar ou editar os [indicadores](manage-bookmarks.md)em massa, [p&A](manage-qas.md)e [locais](manage-locations.md). Esse recurso é útil quando um administrador deseja adicionar ou editar vários componentes. 

Os recursos de importação e exportação fornecem estas funções:
- **Adição em massa**. Adicione detalhes no arquivo de modelo do componente e importe-o.
- **Edição em massa**. Exporte componentes para um arquivo CSV, edite os detalhes do indicador no CSV exportado e, em seguida, importe o CSV atualizado.
- **Importe sites promovidos do [SharePoint](http://sharepoint.com/)**. Este recurso se aplica somente a [indicadores](manage-bookmarks.md).
- **Backup**. Exportar componentes para um arquivo CSV.

Para importar ou exportar componentes, siga estas etapas:
1. No canto superior direito da guia nome do componente, selecione **importar**. 
1. Para baixar todos os componentes existentes em um arquivo CSV, selecione **Exportar**.
1. No painel direito, escolha a opção para importar usando um arquivo CSV ou do [SharePoint](http://sharepoint.com/).
1. Para obter uma lista dos campos e detalhes necessários, baixe o arquivo de modelo do componente. 
1. Adicione ou edite detalhes do componente no arquivo de modelo. Em seguida, salve-o em seu computador. 
1. No painel **importar** do componente, selecione **procurar**. Em seguida, selecione o arquivo CSV desejado e selecione **importar**.

### <a name="template-guidelines"></a>Diretrizes de modelo
Esteja ciente dessas diretrizes e restrições quando trabalhar com arquivos de modelo:
- Nunca edite dados nestes campos: *ID*, *última modificação*e *última modificação por*.
- Se você incluir a *ID* de um indicador existente, ele será substituído pelas informações no arquivo de importação.
- Se houver um indicador com o mesmo título ou URL no arquivo existente, o indicador será atualizado com informações no arquivo de importação.
- Nem todos os campos no arquivo de modelo são necessários, e os campos obrigatórios variam de acordo com o estado do indicador.
- Com base no campo *estado* , os indicadores são salvos como **rascunho**, **sugerido**ou **agendado**. Caso contrário, elas serão publicadas automaticamente.
- Se você gerenciar várias organizações, poderá exportar seus indicadores de uma organização e importá-los para outro. Mas você deve remover os dados na coluna *Id* antes de importar.

> [!Note]
> Você não pode importar itens de componente se houver erros no arquivo de modelo. Para evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente e inclua todas as informações necessárias.

### <a name="prevent-import-errors"></a>Evite erros de importação

Você receberá uma mensagem de erro se os dados necessários estiverem ausentes ou forem inválidos. Um arquivo de log é gerado com mais informações sobre as linhas e colunas a serem corrigidas. Faça as edições necessárias e tente importar o arquivo novamente. Você não pode importar ou salvar nenhum indicador até que todos os erros sejam resolvidos.

Para evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente e atenda a esses requisitos:
- A linha de cabeçalho e todas as colunas no modelo de importação estão incluídas.
- A ordem da coluna é o mesmo que o modelo de importação.
- Todas as colunas têm valores, exceto os três que podem estar vazios: *ID*, *última modificação*e *última modificação por*. 
- A coluna de *estado* não está vazia.

### <a name="titles-and-descriptions"></a>Títulos e descrições
Títulos e descrições conectados ajudam os usuários a determinar se os resultados responderão às suas consultas de pesquisa. Bons títulos e descrições refletem a finalidade principal do resultado. Um exemplo é o título **Childcare benefícios** com a descrição *saiba mais sobre os benefícios para ajudar a pagar os custos do Childcare*. Com esses dados conectados, os usuários que pesquisam o **Childcare** podem encontrar benefícios monetários de suporte e obter um link para obter mais informações.

### <a name="keywords"></a>Palavras-chave
Com palavras-chave, os usuários em sua organização podem pesquisar e localizar conteúdo relevante. Você precisa associar termos de palavra-chave com seus resultados de pesquisa relacionados. A pesquisa da Microsoft sugere palavras-chave com base no título e na URL do seu conteúdo. Para identificar mais palavras-chave, obtenha respostas para essas perguntas:

1. **Quais termos de pesquisa podem localizar as informações que você identificou?** Consulte qualquer terminologia existente em sua organização, bem como variações relacionadas, acrônimos, assuntos e tópicos.
1. **Quais variações ou palavras as pessoas usam para falar sobre essas informações?** Peça à equipe de suporte para fornecer essas palavras-chave.

Por exemplo, se você criar um resultado que vincule uma ferramenta para enviar solicitações de férias, as palavras-chave **férias** e **Enviar solicitação de férias** serão boas opções a serem incluídas. Os usuários da sua organização também podem pesquisar informações relacionadas a férias com **feriado** ou **folga**. Para facilitar para os usuários a localização de conteúdo relevante, adicione essas palavras-chave e outras, como **enviar solicitações de feriados** e **tempo de solicitação desativada**.

### <a name="reserved-keywords"></a>Palavras-chave reservadas
 Uma palavra-chave reservada é um termo ou frase única que aciona um resultado. Diferentemente de outras palavras-chave, palavras-chave reservadas são associadas somente a um resultado. Use as palavras-chave reservadas com parcimônia, para permitir que a Pesquisa da Microsoft aprenda com base no uso.

Um exemplo é um indicador de um site para o envio de suas horas. Se o **tempo de log** for uma palavra-chave reservada, os usuários de sua organização que pesquisam o horário de **log** veem esse site como o único indicador na caixa de pesquisa da Microsoft. 

### <a name="group-related-content-with-keywords"></a>Agrupar conteúdo relacionado com palavras-chave
Se quiser que os usuários encontrem conjuntos de conteúdo relacionado quando pesquisarem um termo específico, atribua a mesma palavra-chave a todo o conteúdo relacionado. Um exemplo é uma pesquisa por processos e ferramentas sobre alterações de status de vida. Para agrupar as respostas em benefícios da atualização, informações de impostos e alterações de nome e alias, inclua uma palavra-chave como **casamento**.

### <a name="search-settings"></a>Configurações de pesquisa
Com as configurações de pesquisa, você pode adaptar o conteúdo e os grupos de usuários específicos. Essas configurações de pesquisa da Microsoft controlam quando um resultado de pesquisa aparece e quem pode vê-lo:

- **Data**. Para controlar quando o conteúdo está disponível ou indisponível, defina uma data de início e uma data de término. Por exemplo, o material sensível ao tempo aparece nos resultados da pesquisa quando é relevante.
- **País ou região**. Você pode selecionar países ou regiões, de modo que somente os usuários desses locais vejam determinados conteúdos. Por exemplo, as informações específicas do país aparecem nos resultados da pesquisa apenas nesses países.
- As configurações de **grupo** disponibilizam os resultados somente para membros dos grupos selecionados. Por exemplo, se você criar sites que se relacionem apenas a funcionários no departamento de RH, mapeie esta configuração para o grupo de segurança RH apropriado.
- **Dispositivo ou sistema operacional**. Selecione tipos de dispositivo ou sistemas operacionais, para que apenas os usuários que pesquisam nesses dispositivos ou usem esses sistemas vejam esse indicador.
- **Variações direcionadas**. Essa configuração varia o conteúdo de um indicador com base no dispositivo e local do usuário.

## <a name="test-your-content"></a>Testar o conteúdo
Depois de criar [indicadores](manage-bookmarks.md) e [p&A](manage-qas.md), verifique estes resultados:
- O indicador ou o p&correto aparece.
- Todo o conteúdo agrupado com palavras-chave aparecerá juntos conforme planejado.
- Nada de inesperado aparece nas respostas da pesquisa.
- O indicador ou Q&A tem informações suficientes.

Os usuários e SMEs que contribuem para a criação de conteúdo podem ajudar a testar e validar os resultados da pesquisa.

## <a name="review-and-update-periodically"></a>Revisar e atualizar periodicamente
Informações autoritativas, como [indicadores](manage-bookmarks.md) e [p&a](manage-qas.md) precisa permanecer atualizadas. Siga estas etapas regularmente:
- Corrigir ou remover URLs desfeitas e inválidas.
- Remova indicadores ou p&um que não seja mais relevante.
- Verifique se há alterações na ferramenta, no nome do site ou no nome da equipe.
- Considere se o indicador ou p&A é autoritativo o suficiente ou precisa de uma descrição mais clara.

## <a name="get-insights-about-bookmarks-qa-and-locations"></a>Obter informações sobre indicadores, p&A e locais

A pesquisa da Microsoft mostra quantos [indicadores](manage-bookmarks.md), [Q&A](manage-qas.md)e [locais](manage-locations.md) são publicados, agendados ou sugeridos. O [painel do insights](get-insights.md) mostra um indicador, Q&A e os totais de local por status:

- **Publicado:** o número de resultados publicados que estão disponíveis para os usuários.
- **Agendado:** o número de resultados agendados no pipeline de publicação.
- **Sugerido:** o número de sugestões dos usuários.

[Indicadores](manage-bookmarks.md)sugeridos, [Q&A](manage-qas.md)e [locais](manage-locations.md) são um bom indicador de lacunas no seu conteúdo. Eles o ajudam a entender o que seus usuários procuram, mas não localizam. Esses dados podem indicar que você precisa criar mais indicadores, Q&A ou locais. Ou talvez seja necessário atualizar o conteúdo existente usando palavras-chave melhores, palavras-chave reservadas e seqüências de pesquisa para tornar seu conteúdo mais detectável.

### <a name="review-top-search-queries"></a>Examine as principais consultas de pesquisa

Para descobrir quais pesquisas geraram a maioria das prensas nos últimos 90 dias, revise suas consultas de pesquisa principais. *Impressão* significa quantas vezes uma página foi visualizada nos resultados da pesquisa. O cartão de **consultas principais** no [painel do insights](get-insights.md) mostra as 25 principais pesquisas de usuários para cada tipo de resultado, o número total de pesquisas e a taxa de cliques (CTR). Com esse relatório, você pode identificar o volume de consulta de pesquisa e determinar consultas com alta e baixa atividade de pesquisa.

A contagem de pesquisa baixa pode indicar insatisfação do usuário. Os usuários não procuram o conteúdo ou estão usando palavras-chave diferentes para encontrá-lo. A CTR mostra com que frequência os usuários selecionam os resultados promovidos e indica qual a utilidade das suas regras e resultados de consulta para os usuários. Um CTR baixo indica que os usuários localizaram o conteúdo, mas não atendem às suas necessidades. Nesses casos, revise o conteúdo. Para alinhar o conteúdo às consultas de pesquisa, verifique se ela corresponde aos títulos de pesquisa e atualização, descrições e palavras-chave. 

### <a name="analyze-impressions-by-result-type"></a>Analise impressões por tipo de resultado

Gráficos de fácil leitura no cartão de distribuição de **impressão** no [painel do insights](get-insights.md) mostram impressões sobre vários intervalos de tempo. A linha do tempo mostra o número de diário de impressões para um tipo de resultado. Com esses gráficos, você pode determinar qual tipo de resultado é mais frequentemente ou raramente usado. O uso não freqüente de um tipo de resultado específico não significa necessariamente que o tipo de resultado não é bom. Apenas mostra como os usuários estão usando o resultado da pesquisa.

 Se um tipo de resultado específico for preferencial para os usuários, você poderá criar mais resultados de pesquisa do mesmo tipo. Para garantir que as palavras-chave sejam apropriadas, revise as palavras-chave dos tipos de resultados com pouco uso. Com esse relatório, você também pode ver as alterações no comportamento do usuário ao longo do tempo.
