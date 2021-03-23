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
ms.openlocfilehash: 0617108d0bdcefe417290a1a3ccf37ad50eb2415
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031589"
---
# <a name="make-content-easy-to-find"></a>Tornar o conteúdo fácil de encontrar

A Pesquisa da Microsoft ajuda os usuários a encontrar conteúdo relevante. É uma maneira segura de pesquisar tanto a intranet quanto o conteúdo da Web. Esse tipo de integração entre a Web e as organizações só está disponível na Microsoft. Com a Pesquisa da Microsoft, os administradores podem usar o conhecimento de uma organização para facilitar a busca de conteúdo relevante para os usuários. 

## <a name="components-that-find-content"></a>Componentes que encontram conteúdo
Na Pesquisa da Microsoft, os administradores criam [Indicadores,](manage-bookmarks.md) [PowerApps,](integrate-powerapps.md) [Q&A](manage-qas.md)e [Locais](manage-locations.md) que facilitam a localização do conteúdo. Cada um desses componentes de pesquisa inclui um título, uma URL e um conjunto de palavras-chave que o acionam.

## <a name="bookmarks"></a>Indicadores
Você pode criar [Indicadores](manage-bookmarks.md) em apenas algumas etapas. Cada indicador inclui um título, uma URL e um conjunto de palavras-chave que o acionam. Um indicador pode ter várias palavras-chave e vários indicadores podem compartilhar a mesma palavra-chave. Mas palavras-chave reservadas não podem ser compartilhadas. Quando você cria ou modifica um indicador, o índice de pesquisa é atualizado e o indicador fica disponível imediatamente para os usuários.

Se sua organização **promoveu resultados** definidos no [SharePoint,](http://sharepoint.com/)você pode importar esses resultados para a Pesquisa da Microsoft. Com os resultados promovidos, você pode preencher rapidamente os resultados da pesquisa, disponibilizar o conteúdo para os usuários e tornar a Pesquisa da Microsoft mais eficaz assim que você o configurar. Recomendamos que você use os resultados promovidos do SharePoint como referência para entender como nomear e criar resultados de pesquisa relevantes. 

### <a name="add-or-edit-bookmarks-by-using-browser-extensions"></a>Adicionar ou editar Indicadores usando extensões do navegador
Os administradores de pesquisa podem criar conteúdo de pesquisa facilmente usando extensões de navegador. Para adicionar o site como um indicador, instale a extensão do navegador. Em seguida, vá para o site e adicione-o como um indicador. Para saber mais, confira [Gerenciar indicadores](manage-bookmarks.md).

Atualmente, as extensões do navegador estão disponíveis para [o Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) e o Google [Chrome](https://www.google.com): 
- Para baixar a extensão de Borda, vá para a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab).
- Para baixar a extensão do Chrome, vá para o [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm).

## <a name="powerapps"></a>PowerApps

Adicionando [PowerApps existentes](integrate-powerapps.md) aos seus [Indicadores,](manage-bookmarks.md)os usuários podem concluir tarefas como inserir períodos de férias ou relatar despesas. 

Com [o PowerApps,](integrate-powerapps.md)você pode criar aplicativos de negócios que são executados em um navegador ou em um telefone ou tablet. Nenhuma experiência de codificação é necessária. Os PowerApps funcionam em qualquer navegador e em qualquer dispositivo. Eles levam menos de um minuto para adicionar. Para saber mais sobre o PowerApps, consulte estes artigos:
- [Aprendizado guiado](/learn/browse/?products=powerapps)
- [Documentação do PowerApps](/powerapps/maker/canvas-apps/get-sessionid)
- [PowerApps home](https://make.preview.powerapps.com/environments/839eace6-59ab-4243-97ec-a5b8fcc104e4/home)

### <a name="add-a-powerapp-to-a-bookmark"></a>Adicionar um PowerApp a um indicador

1. Encontre a [ID do aplicativo](/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id) para o PowerApp que você deseja adicionar.
1. No Centro de administração [](https://admin.microsoft.com)do Microsoft 365, acesse **Configurações**  >  **da Pesquisa da Microsoft.** 
1. Adicione um indicador ou encontre um indicador existente ao qual você deseja adicionar um PowerApp.
1. Em **Configurações de indicador,** selecione **Power App**. Em seguida, **selecione Adicionar um Aplicativo do Power**.
1. Insira a **ID do aplicativo**. A altura e a largura se ajustam automaticamente. [Indicadores podem](manage-bookmarks.md) dar suporte a orientações de retrato e paisagem, mas atualmente o tamanho não pode ser alterado. Para facilitar o teste, a visualização do indicador mostra um PowerApp totalmente funcional.
1. Selecione **Publicar** ou **Salvar em Rascunhos**.

## <a name="qa"></a>P e R

Criar um [Q&A](manage-qas.md) é como criar [Indicadores](manage-bookmarks.md). Com Q&A, você pode fornecer respostas às perguntas dos usuários em vez de apenas um link para a página da Web. Você pode formatar respostas em texto rico usando ferramentas disponíveis. Se um indicador e um Q&A compartilharem a mesma palavra-chave, o resultado do indicador será primeiro. Como indicadores, o índice Q&A é atualizado imediatamente após você adicionar ou alterar um Q&A. 

### <a name="supported-html-tags"></a>Marcas HTML com suporte

Você pode usar conteúdo HTML ou adicionar marcas HTML à sua resposta ou descrição. Damos suporte a essas marcas HTML:
 
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

As marcas sem suporte são ignoradas ou exibidas como texto. Certifique-se de visualizar seus cartões.

> [!Note]
> Não é possível importar itens Q&A se houver erros no arquivo de modelo. Para evitar erros, certifique-se de que o arquivo de importação está formatado corretamente e ele inclui todas as informações necessárias. Confira mais informações sobre como evitar [erros de importação.](#prevent-import-errors)

## <a name="locations"></a>Locais

Com [Locais](manage-locations.md), os usuários podem localizar endereços e localizar os edifícios da sua organização. O **recurso Locais** fornece um local preciso para escritórios, campus e edifícios, bem como direções e navegação. Para melhores resultados, os administradores precisam adicionar todos os locais importantes de suas organizações à Pesquisa da Microsoft. Ao [contrário de Indicadores](manage-bookmarks.md) e [&A](manage-qas.md), o índice Locations não é atualizado imediatamente. Pode levar várias horas para que locais novos ou alterados apareçam nos resultados da pesquisa.

## <a name="get-started"></a>Começar
Para descobrir do que os usuários precisam e facilitar a descoberta dessas informações, experimente alguns desses métodos:

- Use os registros de pesquisa da intranet para saber quais sites e páginas recebem mais tráfego.
- Saiba quais aplicativos, sites e ferramentas são usados diariamente ou semanalmente.
- Encontre links diretos para benefícios dos funcionários.
- Encontre políticas e processos dos quais os usuários precisam estar cientes.
- Decida quem os usuários contatarão para suporte e como eles fazem isso.
- Obter informações necessárias de forma recorrente, sazonalmente ou com base em ciclos de negócios. Um exemplo são as pessoas que procuram ferramentas para reservar o tempo de folga ou as atualizações financeiras trimestrais.
- Coletar políticas para usuários regionais ou móveis. Exemplos são benefícios que variam de acordo com o local.
- Determine sites internos e informações para pesquisas comuns na Web. Exemplos são tráfego, informações de transporte público, clima local, descontos disponíveis de parceiros corporativos e programas de saúde e fitness.
- Encontre informações sobre eventos, conferências ou confraternizações patrocinados pela empresa.
- Pesquise sobre questões comuns de TI, RH e suporte, além de perguntas frequentes (FAQs) e respostas.

## <a name="involve-smes-and-users"></a>Envolver SMEs e usuários
Em uma organização, os usuários pesquisam por um intervalo de tópicos simples e complexos. Exemplos simples são endereços de escritório e benefícios de funcionários. Exemplos complexos são novos processos de trabalho, informações técnicas e conteúdo de como fazer. Para criar ou encontrar uma grande variedade de conteúdo, você precisa de experiência em diferentes campos, assuntos e tecnologias. 

A maioria dos administradores de pesquisa não tem conhecimento específico sobre cada assunto. Para dimensionar a quantidade de conteúdo disponível sem ajuda de recursos externos, procure conhecimento e experiência de outras pessoas em sua organização.

### <a name="get-content-from-smes"></a>Obter conteúdo de SMEs
Aproveite os especialistas em assunto (SMEs) em sua organização, incluindo especialistas de RH, suporte, vendas, tecnologia e outras áreas-chave. As SMEs podem contribuir com conteúdo diretamente se você adicioná-los como editores da Pesquisa da Microsoft. 

### <a name="involve-your-users"></a>Envolva seus usuários
Peça aos usuários para sugerir recursos para os quais criar indicadores. Peça também que os usuários reportem erros como links quebrados ou inválidos.

## <a name="set-up-components"></a>Configurar componentes
Para adicionar ou editar indicadores [individuais](manage-bookmarks.md)ou em massa, [P&A](manage-qas.md)e [Localizações,](manage-locations.md)dê as etapas nas seções a seguir. 

### <a name="add-or-edit-a-single-bookmark-qa-or-location-component"></a>Adicionar ou editar um único indicador, P&A ou componente de local
1. No Centro de administração [](https://admin.microsoft.com)do Microsoft 365, acesse **Configurações**  >  **da Pesquisa da Microsoft.** Selecione a guia nomeada do componente. A **guia Indicadores** é selecionada por padrão.
1. Para adicionar um componente, selecione **Adicionar novo**. 
1. Para editar um componente, selecione o indicador na lista de componentes relevante. 
1. À medida que você adiciona ou edita as informações, a visualização é atualizada automaticamente.

### <a name="bulk-add-or-edit-components"></a>Adicionar ou editar componentes em massa
Com os **recursos de importação** **e exportação,** os administradores de pesquisa podem criar ou [editar](manage-bookmarks.md)indicadores em massa, P [&A](manage-qas.md)e [Locais.](manage-locations.md) Esse recurso é útil quando um administrador deseja adicionar ou editar muitos componentes. 

Os recursos de importação e exportação fornecem estas funções:
- **Adicionar em massa**. Adicione detalhes no arquivo de modelo do componente e importe-o.
- **Edição em massa**. Exporte componentes para um arquivo CSV, edite os detalhes do indicador no CSV exportado e importe o CSV atualizado.
- **Importar sites promovidos do [SharePoint](http://sharepoint.com/)**. Esse recurso só se aplica [a Indicadores](manage-bookmarks.md).
- **Backup**. Exportar componentes para um arquivo CSV.

Para importar ou exportar componentes, tome estas etapas:
1. No canto superior direito da guia nomeada do componente, selecione **Importar**. 
1. Para baixar todos os componentes existentes em um arquivo CSV, selecione **Exportar**.
1. No painel direito, escolha a opção para importar usando um arquivo CSV ou do [SharePoint](http://sharepoint.com/).
1. Para obter uma lista dos campos e detalhes necessários, baixe o arquivo de modelo do componente. 
1. Adicione ou edite detalhes do componente no arquivo de modelo. Em seguida, salve-o em seu computador. 
1. No painel Importação **do** componente, selecione **Procurar**. Em seguida, selecione o arquivo CSV que você deseja e selecione **Importar**.

### <a name="template-guidelines"></a>Diretrizes de modelo
Esteja ciente dessas diretrizes e restrições ao trabalhar com arquivos de modelo:
- Nunca edite dados nestes campos: *Id*, *Last Modified* e *Last Modified By*.
- Se você incluir *a ID* de um indicador existente, ela será substituída pela informação no arquivo de importação.
- Se houver um indicador com o mesmo título ou URL no arquivo existente, o indicador será atualizado com informações no arquivo de importação.
- Nem todos os campos no arquivo de modelo são necessários e os campos necessários variam dependendo do estado do indicador.
- Com base no *campo Estado,* os indicadores são salvos como **rascunho,** **sugerido** ou **agendado.** Caso contrário, eles são publicados automaticamente.
- Se você gerenciar várias organizações, poderá exportar seus indicadores de uma organização e importá-los para outra. Mas você deve remover os dados na coluna *Id* antes de importar.

> [!Note]
> Não é possível importar itens de componente se houver erros no arquivo de modelo. Para evitar erros, certifique-se de que o arquivo de importação está formatado corretamente e ele inclui todas as informações necessárias.

### <a name="prevent-import-errors"></a>Evite erros de importação

Você receberá uma mensagem de erro se algum dado necessário estiver ausente ou inválido. Um arquivo de log gera com mais informações sobre as linhas e colunas a serem corrigidas. Faça edições necessárias e tente importar o arquivo novamente. Não é possível importar ou salvar indicadores até que todos os erros sejam resolvidos.

Para evitar erros, certifique-se de que o arquivo de importação está formatado corretamente e atenda a esses requisitos:
- A linha de header e todas as colunas no modelo de importação estão incluídas.
- A ordem de coluna é igual ao modelo de importação.
- Todas as colunas têm valores, exceto os três que podem estar vazios: *Id*, *Last Modified* e Last *Modified By*. 
- A *coluna Estado* não está vazia.

### <a name="titles-and-descriptions"></a>Títulos e descrições
Títulos e descrições conectados ajudam os usuários a determinar se os resultados respondem à consulta de pesquisa. Bons títulos e descrições refletem a finalidade principal do resultado. Um exemplo é o título **Childcare benefits** with the description *Learn about benefits to help pay childcare costs*. Com esses dados conectados, os usuários que pesquisam por **assistência** à criança podem encontrar benefícios de suporte monetário e obter um link para saber mais.

### <a name="keywords"></a>Palavras-chave
Com palavras-chave, os usuários em sua organização podem pesquisar e encontrar conteúdo relevante. Você precisa associar termos de palavra-chave aos resultados de pesquisa relacionados. A Pesquisa da Microsoft sugere palavras-chave com base no título e NAL do seu conteúdo. Para identificar mais palavras-chave, obter respostas para estas perguntas:

1. **Quais termos de pesquisa podem encontrar as informações identificadas?** Consulte qualquer terminologia existente em sua organização, bem como variações relacionadas, acrônimos, assuntos e tópicos.
1. **Quais variações ou palavras as pessoas usam para falar sobre essas informações?** Peça à sua equipe de suporte para fornecer essas palavras-chave.

Por exemplo, se você criar um resultado que vincula a uma ferramenta para enviar solicitações de férias, as palavras-chave **férias** e enviar solicitação de férias **são** boas opções para incluir. Os usuários em sua organização também podem pesquisar informações relacionadas a férias com **férias** ou **folga.** Para facilitar que os usuários encontrem conteúdo relevante, adicione  essas palavras-chave e outras, como enviar solicitação de feriado e **solicitar folga.**

### <a name="reserved-keywords"></a>Palavras-chave reservadas
 Uma palavra-chave reservada é um termo ou frase única que aciona um resultado. Ao contrário de outras palavras-chave, as palavras-chave reservadas são associadas apenas a um resultado. Use as palavras-chave reservadas com parcimônia, para permitir que a Pesquisa da Microsoft aprenda com base no uso.

Um exemplo é um indicador para um site para enviar suas horas. Se **o tempo de** log for uma palavra-chave reservada, os usuários em sua organização que pesquisam o tempo de **log** verão esse site como o único indicador na caixa Pesquisa da Microsoft. 

### <a name="group-related-content-with-keywords"></a>Conteúdo relacionado ao grupo com palavras-chave
Se você quiser que os usuários encontrem conjuntos de conteúdo relacionado quando pesquisam um termo específico, atribua a mesma palavra-chave a todo o conteúdo relacionado. Um exemplo é uma pesquisa de processos e ferramentas em torno de alterações de status de vida. Para agrupar respostas sobre a atualização de benefícios, informações fiscais e alterações de nome e alias, inclua uma palavra-chave como **o casamento**.

### <a name="search-settings"></a>Configurações de pesquisa
Com as configurações de pesquisa, você pode adaptar seu conteúdo e direcionar grupos específicos de usuários. Essas configurações da Pesquisa da Microsoft controlam quando um resultado de pesquisa é exibido e quem pode vê-lo:

- **Data**. Para controlar quando o conteúdo está disponível ou indisponível, de definir uma data de início e uma data de término. Por exemplo, o material sensível ao tempo aparece nos resultados da pesquisa quando relevante.
- **País ou região**. Você pode selecionar países ou regiões, portanto, somente os usuários nesses locais veem determinado conteúdo. Por exemplo, informações específicas do país aparecem apenas nos resultados da pesquisa nesses países.
- **As** configurações de grupo disponibilizam resultados apenas para membros de grupos selecionados. Por exemplo, se você criar sites que se relacionam apenas com funcionários no departamento de RH, mapeie essa configuração para o grupo de segurança de RH apropriado.
- **Dispositivo ou sistema operacional**. Selecione tipos de dispositivo ou sistemas operacionais, portanto, somente os usuários que pesquisam nesses dispositivos ou usam esses sistemas veem esse indicador.
- **Variações direcionadas**. Essa configuração varia o conteúdo de um indicador com base no dispositivo e no local de um usuário.

## <a name="test-your-content"></a>Testar seu conteúdo
Depois de criar [Indicadores](manage-bookmarks.md) e [&A,](manage-qas.md)verifique estes resultados:
- O indicador correto ou Q&A é exibido.
- Todo o conteúdo agrupado com palavras-chave aparece junto conforme planejado.
- Nada inesperado aparece nas respostas de pesquisa.
- O indicador ou Q&A tem informações suficientes.

Usuários e SMEs que contribuem para a criação de conteúdo podem ajudar a testar e validar os resultados da pesquisa.

## <a name="review-and-update-periodically"></a>Revisar e atualizar periodicamente
Informações autoritativas, como [Indicadores](manage-bookmarks.md) e [&A,](manage-qas.md) precisam permanecer recentes. Tome estas etapas regularmente:
- Correção ou remoção de URLs quebradas e inválidas.
- Remova indicadores ou Q&A que não sejam mais relevantes.
- Verifique se há alterações na ferramenta, no nome do site ou no nome da equipe.
- Considere se o indicador ou Q&A é autoritativo o suficiente ou precisa de uma descrição mais clara.

## <a name="get-insights-about-bookmarks-qa-and-locations"></a>Obter informações sobre indicadores,&A e Locais

A Pesquisa da Microsoft mostra quantos [Indicadores](manage-bookmarks.md), [Q&A](manage-qas.md)e [Locais](manage-locations.md) são publicados, agendados ou sugeridos. O [painel Insights](./usage-reports.md) mostra indicador, Q&A e totais de local por status:

- **Publicado:** o número de resultados publicados que estão disponíveis para os usuários.
- **Agendado:** o número de resultados agendados no pipeline de publicação.
- **Sugerido:** o número de sugestões dos usuários.

Indicadores [sugeridos,](manage-bookmarks.md) [Q&A](manage-qas.md)e [Locais](manage-locations.md) são um bom indicador de lacunas em seu conteúdo. Eles ajudam você a entender o que os usuários estão procurando, mas não encontram. Esses dados podem indicar que você precisa criar mais indicadores, Q&A ou Locais. Ou talvez seja necessário atualizar seu conteúdo existente usando palavras-chave melhores, palavras-chave reservadas e cadeias de caracteres de pesquisa para tornar seu conteúdo mais descoberto.

### <a name="review-top-search-queries"></a>Examine as principais consultas de pesquisa

Para descobrir quais pesquisas geraram mais impressões nos últimos 90 dias, revise suas principais consultas de pesquisa. *Impressão* significa quantas vezes uma página foi exibida nos resultados da pesquisa. O **cartão Principais Consultas** no painel [Insights](./usage-reports.md) mostra as 25 principais pesquisas de usuário para cada tipo de resultado, o número total de pesquisas e a taxa de cliques (CTR). Com este relatório, você pode identificar o volume da consulta de pesquisa e determinar consultas com atividade de pesquisa alta e baixa.

A contagem baixa de pesquisa pode indicar a insatisfação do usuário. Os usuários não estão procurando por esse conteúdo ou estão usando palavras-chave diferentes para encontrá-lo. A CTR mostra com que frequência os usuários selecionam os resultados promovidos e indica qual a utilidade das suas regras e resultados de consulta para os usuários. Uma CTR baixa indica que os usuários encontram o conteúdo, mas não atendem às suas necessidades. Nesses casos, revise o conteúdo. Para alinhar o conteúdo às consultas de pesquisa, certifique-se de que ele corresponde aos títulos de pesquisa e atualização dos usuários, descrições e palavras-chave. 

### <a name="analyze-impressions-by-result-type"></a>Analise impressões por tipo de resultado

Gráficos fáceis de ler no cartão de distribuição **Impressão** no painel [do Insights](./usage-reports.md) mostram impressões ao longo de vários quadros de tempo. A linha do tempo mostra o número de diário de impressões para um tipo de resultado. Com esses gráficos, você pode determinar qual tipo de resultado é usado com mais frequência ou com pouca frequência. O uso frequente de um determinado tipo de resultado não significa necessariamente que o tipo de resultado não seja bom. Apenas mostra como os usuários estão usando o resultado da pesquisa.

 Se um determinado tipo de resultado for preferido pelos usuários, você poderá criar mais resultados de pesquisa do mesmo tipo. Para garantir que as palavras-chave sejam apropriadas, revise as palavras-chave dos tipos de resultados com baixo uso. Com este relatório, você também pode ver alterações no comportamento do usuário ao longo do tempo.