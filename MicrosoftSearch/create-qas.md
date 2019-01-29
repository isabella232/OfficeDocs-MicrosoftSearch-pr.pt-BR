---
title: Criar Q&As
ms.author: dawholl
author: dawholl
manager: kellis
ms.date: 12/18/2018
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Priority
search.appverid:
- BFB160
- MET150
- MOE150
ms.assetid: d432b9d9-3792-47a0-9a13-30a1a83caabc
description: Maneiras de criar respostas para perguntas frequentes para o Microsoft Search funcionam resultados
ms.openlocfilehash: 9713608450688a0841aa64d1f3198183b10e05ee
ms.sourcegitcommit: 1c038d87efab4840d97b1f367b39e2b9ecdfee4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "29612494"
---
# <a name="create-qas"></a>Criar Q&As

Q&As fornecem uma resposta ou info aos usuários, incluindo um link opcional. Idealmente, um Q&A inclui todos os detalhes de que os usuários estão procurando por isso, eles não precisam passar para a fonte. Você pode formatar seu conteúdo Q&A e incluir imagens, listas e tabelas.
  
## <a name="create-a-qa"></a>Criar um Q&A

Para obter informações sobre a criação de títulos efetivos, descrições, palavras-chave e muito mais, consulte [planejar seu conteúdo.](plan-your-content.md)
  
1. Vá para o portal de administração de pesquisa da Microsoft
    
2. No painel de navegação, clique em **Q&As**
    
3. Na parte superior da página, clique em **Adicionar Q&A**
    
    A página Editar Q&A é exibida, com uma visualização da aparência o Q&A em Bing. Conforme você adiciona as informações necessárias, a visualização será atualizado automaticamente.
    
4. Insira um **título**
    
    O título é o título que aparece no resultado. Ele pode ter até 120 caracteres de comprimento e é recomendável usar um formato de pergunta.
    
5. Se necessário, digite a **URL** da página, site ou fará um link para o indicador de local 
    
    Este permite que os usuários que precisam de informações adicionais facilmente têm para a fonte para ler mais.
    
6. Insira uma **Descrição de resposta**
    
    Isso deve responder à pergunta que será perguntada do título. Você pode copiar o conteúdo HTML existente e colá-lo aqui. Quaisquer marcas sem suporte serão ignoradas.
    
7. Usar marcas HTML e as opções internas para formatar o texto, adicione imagens, listas, tabelas e muito mais
    
    Use a visualização na parte superior da página para ver como seu marcas e a formatação será exibido em Bing. Para obter informações sobre:
    
  - Marcas HTML, consulte a lista de marcas HTML suportada abaixo
    
  - Opções internas, clique em **guia de redução** (ícone de ponto de interrogação) 
    
8. Insira **palavras-chave** que você deseja acionar este Q&A 
    
    Como um indicador, quando um usuário procura por qualquer uma das palavras-chave que já tiver incluído, este Q&A serão incluídos em seus resultados de trabalho. Tente adicionar tantos variantes possível, incluindo o título do Q&A.
    
9. Selecione **corresponder automaticamente palavras-chave semelhantes** para expandir seu conjunto de palavras-chave 
    
    Isso permite que uma correspondência mais ampla de termos de pesquisa e ajuda a garantir que este Q&A é incluído nos resultados de trabalho relevantes.
    
10. Insira **palavras-chave reservadas**
    
    Se uma palavra-chave acionar vários Q&As, Microsoft Search será aquele mais popular na parte superior de mostrar os outros como links relacionados. Use um ou mais palavras-chave reservadas para garantir que uma Q&A sempre aparece como o resultado de superior. Palavras-chave reservadas não podem ser compartilhadas entre Q&As. Além disso, o compartilhamento de palavras-chave reservadas entre Q&As e indicadores não é recomendável. Se um indicador e um Q&A compartilham uma palavra-chave ou uma palavra reservada, o indicador sempre terão precedência e o Q&A não será exibida.
    
## <a name="add-qa-settings"></a>Adicionar Q&A configurações

Configurações de Q&A conceder controle adicional sobre quando um Q&A aparece e quem vê-lo.
  
- Datas
    
    Defina uma data de início, bem como uma data de término opcional para controlar quando um Q&A serão publicados ou expirar.
    
- País/região
    
    Se você selecionar países ou regiões, somente os usuários nesses locais verão que Q&A.
    
- Grupos
    
    Use os grupos de configuração para disponibilizar um resultado Q&A somente aos membros de um grupo selecionado. Por exemplo, se você estiver criando Q&As relativas apenas para os funcionários do departamento de RH, você pode mapear essa configuração para o grupo de segurança de RH apropriado.
    
- Dispositivo &amp; SO
    
    Se você selecionar tipos de dispositivo ou sistemas operacionais, somente os usuários pesquisando nesses dispositivos ou usando aqueles sistemas verão que Q&A.
    
- Variações direcionadas
    
    Use esta configuração para variar o conteúdo do Q&A com base no dispositivo e o local de um usuário.
    
## <a name="use-a-browser-extension-to-create-content"></a>Usar uma extensão de navegador para criar conteúdo

Na seção Ferramentas de portal de administração, baixe e instale a extensão de navegador do criador do conteúdo para a borda ou Chrome. Para usar a extensão, entrar e vá para um site ou página que você deseja adicionar como uma revisão Q&A. e altere o conteúdo sugerido, incluindo palavras-chave, adicione qualquer conteúdo adicional e salve o Q&A.
  
Se vários Q&As forem encontradas, revise cada um deles e determinar se você deseja publicar, salve rascunho ou salvar todos para rascunho.
  
## <a name="supported-html-tags"></a>Marcas HTML com suporte

Você pode usar o conteúdo HTML existente ou adicionar marcas HTML à sua descrição de resposta. Não há suporte para as marcas serão ignoradas.
  
- blockquote
    
- div
    
- em
    
- S1, S2, S3 e h4
    
- OL, ul e li
    
- p
    
- pré
    
- SPAN
    
- forte
    
- tabela, thead, tbody, tr, th e td
    
- u
    
- a
    
- código
    
- br
    
- hr
    
- img

  

