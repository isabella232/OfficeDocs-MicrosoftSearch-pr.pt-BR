---
title: Gerenciar indicadores
ms.author: dawholl
author: dawholl
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: c0c814d0-f7e4-444e-b18e-09beb45c9322
description: Criar e atualizar indicadores e maneiras de editar em massa resultados de indicadores para a Pesquisa da Microsoft
ms.openlocfilehash: b801e75f772a585c2ddfedd09aff3b74c1d909b5
ms.sourcegitcommit: 2f770de12b27546b18b2e86517d2c25522eb9022
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929603"
---
# <a name="manage-bookmarks"></a>Gerenciar indicadores

Indicadores ajudam as pessoas a encontrar rapidamente sites e ferramentas importantes com apenas uma pesquisa. Cada indicador inclui um título, URL, um conjunto de palavras-chave amigáveis para disparar o indicador e uma categoria.

## <a name="what-makes-a-great-bookmark"></a>O que torna um ótimo indicador

Um indicador excelente tem quatro elementos-chave:

1. Um título forte e **informativo.** Aponte para no máximo oito palavras ou cerca de 60 caracteres. Você deseja que os usuários cliquem no título e exibirem o conteúdo, mas evitem clique óbvio:
    - Bom: experimente os favoritos mais interessantes desta semana no menu de cafeteria. Title is clear, concise, and interesting, but could be overpromising.
    - Melhor: menu de cafeteria desta semana. Não se sobrepromiza ou soa como um ad.
    - Evite: você não acreditará no que está chegando ao menu da cafeteria esta semana. Usa clichês de clickbait que soam como um ad.
2. Uma descrição **sucinto**, cerca de 300 caracteres, que resume a finalidade ou a funcionalidade do recurso vinculado.
3. Uma coleção de **palavras-chave que** ajudará as pessoas a encontrar o indicador quando pesquisam. Sugerimos um mínimo de cinco palavras-chave. Além disso, inclua variações que as pessoas em sua organização podem usar, por exemplo, menu de jantar, menus de almoço e menu de café podem ser variações para o menu de cafeteria.
4. Um conjunto útil de **categorias** que facilita a classificação e filtragem de indicadores no centro de administração. Seus usuários nunca veem as categorias atribuídas.

## <a name="create-bookmark-answers"></a>Criar respostas de indicador

No Centro de administração do [Microsoft 365,](https://admin.microsoft.com/)acesse [Indicadores](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/bookmarks) e escolha como você deseja criar novos indicadores:

- Adicionar indicadores
- Importar resultados do SharePoint
- Adicionar indicadores padrão e indicadores sugeridos
- Importar indicadores
- Publicar ou revisar indicadores recomendados

### <a name="add-bookmarks"></a>Adicionar indicadores

Os administradores e editores de pesquisa podem adicionar indicadores no Centro de administração do Microsoft 365 e publicá-los ou salvá-los no rascunho. Publicar um indicador atualiza imediatamente o índice de pesquisa, tornando-o descoberto imediatamente para os usuários. Você também pode agendar um indicador especificando a data e a hora em que ele será publicado.

- **Publicado**: Os indicadores estão disponíveis para os usuários da organização por meio da Pesquisa da Microsoft.
- **Rascunho**: Indicadores salvos como rascunhos não estão disponíveis para seus usuários. Use esse status se você ou outros participantes quiserem revisar ou atualizar indicadores antes de publicá-los.
- **Agendado**: Indicadores que serão publicados na data e hora especificadas.

Você pode usar a extensão do navegador criador de conteúdo da Pesquisa da Microsoft para adicionar indicadores facilmente. Para instalar a extensão do navegador, vá para o site que você deseja adicionar como um indicador e clique em Adicionar na extensão.
Instale a extensão para Borda e Chrome:

- Para Borda Chromium ou Chrome: vá para o [Chrome Web Store](https://chrome.google.com/webstore/detail/microsoft-search-content/nocnablpaoeecfmfnjoheefkogmleipm) e adicione a extensão.
- Para o Edge herdados: vá para a [Microsoft Store](https://www.microsoft.com/p/microsoft-search-content-creator/9nrqdbcbwq55?activetab=pivot:overviewtab) e adicione a extensão.

### <a name="import-sharepoint-results"></a>Importar resultados do SharePoint

Se sua organização configurar Os Resultados Promovidos no SharePoint, você poderá importar os títulos, URLs e descrições dos Resultados Promovidos para seu locatário para a Pesquisa da Microsoft e disponibilizar o conteúdo importado para seus usuários. Na maioria dos casos, a importação de resultados do SharePoint leva apenas alguns minutos. Se você estiver importando um grande número de resultados, pode levar até 48 horas. Essa é uma maneira fácil de preencher rapidamente os resultados da pesquisa e torná-los mais eficazes para seus usuários. Recomendamos o uso de resultados promovidos do SharePoint como referência para entender como nomear e criar resultados de pesquisa relevantes.

### <a name="add-default-and-suggested-bookmarks"></a>Adicionar indicadores padrão e sugeridos

Incluímos alguns indicadores sugeridos padrão que seus usuários podem achar úteis, incluindo indicadores para RH, benefícios, suporte a IT, gerenciamento de senhas e muito mais. Revise, atualize e publique esses indicadores sugeridos para fornecer resultados de alta qualidade aos usuários imediatamente.

Seus usuários também podem sugerir indicadores que gostaria de ver adicionados usando links de comentários na Pesquisa da Microsoft. Suas recomendações aparecerão como indicadores sugeridos.

### <a name="import-bookmarks"></a>Importar indicadores

Use o recurso Import para tornar a adição ou edição de um grande número de indicadores mais rápido e fácil. Use-o para:

- Adicionar indicadores em massa: Adicione detalhes no arquivo de modelo de indicador e importe-o.
- Indicadores de edição em massa: Exportar indicadores para um arquivo .csv, editar os detalhes do indicador no arquivo exportado e importar o arquivo editado.

Alguns pontos importantes sobre o arquivo de modelo:

- Nunca edite dados nesses campos: *ID,* *Última* Modificação e *Última Modificação por*
- Se você incluir a *ID* de um indicador existente, ela será substituída pela informação no arquivo de importação.
- Para indicadores existentes com o mesmo título ou URL, o indicador será atualizado com informações no arquivo de importação.
- Nem todos os campos no arquivo de modelo são obrigatórios, e os campos obrigatórios variam dependendo do estado do indicador.
- Com base no *campo Estado,* os indicadores serão salvos como rascunho, sugeridos, agendados, excluídos ou serão publicados automaticamente.
- Para parceiros que gerenciam várias organizações, você pode exportar seus indicadores de uma organização e importá-los para outra. Mas você deve remover os dados na coluna *ID* antes de importar.

### <a name="prevent-import-errors"></a>Evite erros de importação

Você receberá um erro se algum dado necessário estiver faltando ou for inválido, e um arquivo de log será gerado com mais informações sobre as linhas e colunas a serem corrigidas. Faça as edições necessárias e tente importar o arquivo novamente. Não é possível importar ou salvar indicadores até que todos os erros sejam resolvidos.

Para evitar erros, certifique-se de que o arquivo de importação esteja formatado corretamente e:

- Que ele inclua a linha de cabeçalho e todas as colunas que estavam no modelo de importação
- Que a ordem das colunas seja igual ao modelo de importação
- Todas as colunas têm valores, exceto os três que podem estar vazios: *ID*, *Última* Modificação e *Última Modificação por*
- A *coluna Estado* não está vazia, são informações necessárias
- Ao importar indicadores Publicados, Sugeridos, Agendados ou Rascunhos, as colunas *Título,* *URL* e *Palavras-chave* são necessárias
- Ao importar indicadores excluídos, a coluna *URL* é necessária

Para evitar erros de duplicação de indicador para indicador:

- Não use URLS duplicadas para indicadores diferentes. Se uma URL for atribuída a outro indicador e você tentar adicioná-la novamente de um arquivo de importação, você obterá um erro. Isso também se aplica a URLs duplicadas para outros tipos de respostas.
- Ao atualizar indicadores existentes, use a coluna *ID do* indicador. Você pode atualizar qualquer outra propriedade de um indicador existente, como palavra-chave ou descrição, mas certifique-se de que a *ID* do indicador está na coluna apropriada do arquivo de importação. Se a *ID do* indicador estiver presente, ela não será tratada como nova adição e não será processada como um erro.

### <a name="publish-or-review-recommended-bookmarks"></a>Publicar ou revisar indicadores recomendados

Para reduzir o esforço manual necessário para adicionar indicadores, a Pesquisa da Microsoft pode avaliar os links do SharePoint da sua organização e recomendar indicadores. Você pode revisá-los antes de publicá-los ou defini-los para publicar automaticamente. Nenhuma configuração é necessária para indicadores recomendados, eles estão habilitados e definidos como autopublicidade por padrão. Para alterar essas configurações a qualquer momento, selecione **Gerenciar indicadores** para abrir o painel de configurações do Indicador.

![Captura de tela das configurações de indicador recomendadas no portal de administração do Microsoft 365](media/bookmarks-recommendedsettings.png)

Se os indicadores recomendados estão habilitados, o mecanismo de recomendação avaliará sites do SharePoint em sua organização para identificar links de alto tráfego. Após um período de avaliação inicial, os indicadores recomendados serão publicados automaticamente ou adicionados à lista de indicadores sugeridos. O próximo ciclo — um período de avaliação de 30 dias seguido de publicação automática ou adição de indicadores sugeridos — começará.

Sugerimos que os administradores ou editores de pesquisa revisem esses indicadores publicados automaticamente ou sugeridos regularmente. Além disso, os indicadores recomendados nunca incluirão URLs encontradas em indicadores publicados, sugeridos, agendados ou excluídos existentes.

Para garantir que somente os usuários com acesso vejam um indicador recomendado nos resultados do trabalho, um recurso de verificação de acesso é incluído para todos os indicadores recomendados. Os usuários nunca verão um indicador recomendado para um site do SharePoint que não podem acessar. Essa verificação de acesso é controlada pela opção Somente pessoas com acesso a esse **link** na configuração Grupos para cada indicador recomendado.

A verificação de acesso será parada se a URL no indicador recomendado ou a configuração Grupos for alterada.

Para impedir que o mecanismo de recomendação publice ou sugira um indicador a um site específico, você pode adicionar a URL a uma lista excluída. O mecanismo de recomendação nunca publicará ou sugerirá um indicador para um site excluído ou uma página em um site excluído.

## <a name="about-keywords-and-reserved-keywords"></a>Sobre palavras-chave e palavras-chave reservadas

Um indicador pode ter várias palavras-chave e compartilhar a mesma palavra-chave, mas a palavra-chave reservada não pode ser compartilhada. Uma palavra-chave reservada é um termo ou frase exclusivo que dispara um indicador específico. Uma palavra-chave reservada pode ser associada apenas a uma resposta. Use palavras-chave reservadas com moderação.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**P: Quanto tempo leva para que um indicador seja visível na Pesquisa da Microsoft depois de publicado?**

**R:**  Um indicador está disponível na Pesquisa da Microsoft imediatamente após a publicação.

**P: Quanto tempo leva para que um indicador recomendado apareça?**

**R:**  Os indicadores recomendados só aparecerão na Pesquisa da Microsoft se os indicadores recomendados e a publicação automática estão habilitados. Durante o período de avaliação inicial, o mecanismo de recomendação avaliará o tráfego do SharePoint para identificar indicadores adequados e publicá-los automaticamente. Depois de publicados, eles ficam disponíveis imediatamente na Pesquisa da Microsoft.

**P: Quanto tempo leva para que um indicador excluído seja removido dos resultados da Pesquisa da Microsoft?**

**R:** Indicadores excluídos são removidos imediatamente dos resultados do trabalho.

**P: A Pesquisa da Microsoft recomendará indicadores de sites em todos os idiomas?**

**R:** Sim, a Pesquisa da Microsoft pode recomendar indicadores de qualquer site interno do SharePoint, independentemente do idioma.

**P: Posso parar de mostrar indicadores recomendados nos resultados da pesquisa?**

**R:** Para parar de mostrar indicadores recomendados, desabilite a configuração de autopublicidade no centro de administração. Indicadores recomendados serão adicionados à lista de indicadores sugeridos.

**P: Como posso identificar um indicador recomendado nos resultados da pesquisa ou no centro de administração?**

**R:** Nos resultados da pesquisa, os indicadores recomendados incluem a frase "Sugerido para você" antes da URL. No centro de administração, os indicadores recomendados terão um valor proprietário de "SYSTEM".

**P: Como o acesso a um indicador recomendado é gerenciado?**

**R:** Um mecanismo de acesso projetado pela Microsoft determina se a URL do indicador está acessível a um usuário específico e mostrará apenas o indicador recomendado para o público correto. No entanto, se a URL for editada ou a configuração Grupos for alterada, o mecanismo de acesso projetado será desabilitado.

**P: O que acontece se nenhuma ação for tomada em indicadores recomendados adicionados à lista Sugerida?**

**R:** Para evitar um alto volume de indicadores na lista sugerida, um indicador recomendado (proprietário = SYSTEM) será limpo após 180 dias.

**P: Onde encontro a ID do aplicativo para um Aplicativo Do Power?**

**R:** Vá para o site do Power Apps e veja o painel Detalhes do aplicativo. Saiba mais sobre [como obter uma ID do aplicativo.](https://docs.microsoft.com/powerapps/maker/canvas-apps/get-sessionid#get-an-app-id)
