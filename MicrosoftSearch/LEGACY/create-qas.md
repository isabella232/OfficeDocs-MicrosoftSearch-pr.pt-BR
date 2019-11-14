---
title: Criar perguntas e respostas
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: d432b9d9-3792-47a0-9a13-30a1a83caabc
ROBOTS: NoIndex
description: Maneiras de criar respostas para perguntas frequentes em seus resultados de trabalho da Pesquisa da Microsoft
ms.openlocfilehash: 6f9e3b6faca636102fe390f64b6ebc19add1a055
ms.sourcegitcommit: 6b531b2ce7253c16251c7089795dedf1d2f3fc33
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "38311316"
---
# <a name="create-qas"></a>Criar P e R

> [!IMPORTANT]
> Este artigo se aplica à Pesquisa da Microsoft no portal de administração do Bing. Estamos movendo o portal para o centro de administração do Microsoft 365 e, em seguida, a Pesquisa da Microsoft no portal do Bing será removida. Recomendamos que você use o centro de administração do Microsoft 365 para começar. [Visão geral da Pesquisa da Microsoft.](overview-microsoft-search.md)

As perguntas e respostas fornecem uma resposta ou informações aos usuários, inclusive um link opcional. O ideal é que uma P e R inclua todos os detalhes que os usuários estão procurando para que eles não precisem ir até a fonte. É possível formatar o conteúdo da P e R e incluir imagens, listas e tabelas.
  
## <a name="create-a-qa"></a>Criar uma pergunta e resposta

Para saber mais sobre como criar de maneira eficaz títulos, descrições, palavras-chave e muito mais, confira [Planejar o conteúdo.](plan-your-content.md)
  
1. Ir para o Portal de Administração da Pesquisa da Microsoft
    
2. No painel de navegação, clique em **P e R**
    
3. Na parte superior da página, clique em **Adicionar P e R**
    
    A página Editar P e R é exibida, com uma visualização de como as P e Rs aparecerão no Bing. Conforme você adiciona as informações necessárias, a visualização é atualizada automaticamente.
    
4. Inserir um **Título**
    
    O título é o cabeçalho exibido no resultado. Pode ter até 120 caracteres e é recomendável usar um formato de pergunta.
    
5. Se necessário, insira a **URL** da página, site ou local ao qual o indicador será vinculado 
    
    Assim os usuários que precisam de mais informações podem acessar a fonte de modo fácil para saber mais.
    
6. Insira uma **Descrição da resposta**
    
    Ela deve responder à pergunta feita no título. Você pode copiar o conteúdo HTML existente e colá-lo aqui. As marcas sem suporte serão ignoradas.
    
7. Use as marcas HTML e as opções internas para formatar o texto, adicionar imagens, listas, tabelas e muito mais
    
    Use a visualização na parte superior da página para ver como as marcas e a formatação serão exibidas no Bing. Para obter informações sobre:
    
  - marcas HTML, veja a lista de marcas HTML compatíveis abaixo
    
  - Opções internas, clique em **Guia de markdown** (ícone de ponto de interrogação) 
    
8. Insira as **Palavras-chave** que você quer para acionar esta P e R 
    
    Como um indicador, quando um usuário pesquisa qualquer uma das palavras-chave incluídas, esse P e R será incluído em seus resultados de trabalho. Tente adicionar o máximo de variantes possíveis, incluindo o título do P e R.
    
9. Selecione **Corresponder automaticamente a palavras-chave semelhante** para expandir seu conjunto de palavras-chave 
    
    Isso proporciona uma correspondência maior dos termos de pesquisa e ajuda a garantir que esse P e R estará incluído nos resultados de trabalhos relevantes.
    
10. Insira as **Palavras-chave reservadas**
    
    Se uma palavra-chave acionar várias P e R, a Pesquisa da Microsoft colocará a mais popular no topo e mostrará as outras como links relacionados. Use uma ou mais palavras-chave reservadas para garantir que a P e R sempre apareça como o melhor resultado. As palavras-chave reservadas não podem ser compartilhadas em P e R. Além disso, não é recomendado compartilhar palavras-chave reservadas em P e R e indicadores. Se um indicador e uma P e R compartilharem uma palavra-chave ou uma palavra-chave reservada, o indicador sempre terá precedência e a P e R não será exibida.
    
## <a name="add-qa-settings"></a>Adicionar configurações de P e R

As configurações de P e R disponibilizam um controle adicional sobre quando uma P e R é exibida e quem a vê.
  
- Datas
    
    Defina uma data de início, bem como uma data de término opcional para controlar quando uma P e R será publicada ou expirará.
    
- País/região
    
    Se você selecionar países ou regiões, somente os usuários desses locais verão essa P e R.
    
- Grupos
    
    Use a configuração de Grupos para disponibilizar um resultado de P e R somente para membros de um grupo selecionado. Por exemplo, se você estiver criando uma P e R que se aplica apenas aos funcionários no departamento de RH, é possível mapear essa configuração ao grupo de segurança de RH apropriado.
    
- SO &amp; dispositivo
    
    Se você selecionar os tipos de dispositivo ou sistemas operacionais, somente os usuários pesquisando nesses dispositivos ou usando estes sistemas verão a P e R.
    
- Variações de destino
    
    Use esta configuração para variar o conteúdo da P e R com base no dispositivo e no local do usuário.
    
## <a name="use-a-browser-extension-to-create-content"></a>Usar a extensão do navegador para criar conteúdo

Na seção Ferramentas do Portal do Administrador, baixe e instale a extensão de navegador do criador de Conteúdo para o Edge ou Chrome. Para usar a extensão, faça logon e acesse um site ou uma página que você deseja adicionar como uma P e R. Revise e altere o conteúdo sugerido, como palavras-chave, adicione qualquer conteúdo adicional e salve a P e R.
  
Se várias P e Rs forem encontradas, analise cada uma e determine se você deseja publicar, salvar como rascunho ou salvar todos como rascunho.
  
## <a name="supported-html-tags"></a>Marcas HTML com suporte

Você pode usar o conteúdo HTML existente ou adicionar marcas HTML à descrição da resposta. Marcas sem suporte são ignoradas.
  
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

  

