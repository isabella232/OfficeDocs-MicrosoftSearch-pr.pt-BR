---
title: Gerenciar as respostas de acrônimo no Microsoft Search
ms.author: jeffkizn
author: jeffkizn
manager: parulm
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Criar e atualizar respostas de acrônimos no Microsoft Search
ms.openlocfilehash: 9d58306751f735cef77eba4404597c73c0528c11
ms.sourcegitcommit: 9ba062f8b632a74e56ad7ec4dffaa1d8dab57614
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44996072"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Gerenciar as respostas de acrônimos no Microsoft Search

Geralmente, os usuários podem ter acrônimos e abreviaturas desconhecidos usados por sua organização ou equipe. Os termos específicos para organizações ou equipes podem ser novos para pessoas que se movem de uma equipe para outra, aqueles que trabalham com equipes de parceiros internas ou que são novos na organização.

As organizações nem sempre têm uma única referência para sua terminologia padrão. A falta de uma única referência dificulta a localização de definições ou expansões desses acrônimos. O Microsoft Search resolve esse problema com acrônimos.

## <a name="what-users-experience"></a>O que os usuários experimentam

Os usuários de pesquisa da Microsoft podem obter definições com acrônimos no [Bing](https://Bing.com). Na caixa de **pesquisa** , os usuários inserem consultas como estes exemplos:

- *O que é* DNN
- *Definir* DNN
- *Definição* DNN
- *Expand* DNN
- *Expansão* DNN
- *Significado de* DNN
- DNN *significa*

O resultado inclui todos os significados do DNN que estão presentes na organização do usuário.

> [!NOTE]
> Os usuários devem inserir uma consulta que inclua as *palavras-chave* especificadas pelo acrônimo para disparar suas respostas correspondentes. As consultas de acrônimos não diferenciam maiúsculas de minúsculas.

## <a name="set-up-acronyms-answers"></a>Configurar respostas de acrônimos

No [centro de administração](https://admin.microsoft.com)do Microsoft 365, acesse **definições**de  >  respostas da**pesquisa da Microsoft**  >  **Answers**  >  [**Acronyms**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)e selecione **Adicionar acrônimos**.

O Microsoft Search consulta duas fontes de dados para fornecer respostas de acrônimos às pesquisas dos usuários:

1. **Acrônimos editoriais**. Fornecido por administradores de ti no [centro de administração](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).
2. **Acrônimos minados**. O Microsoft Search dos emails e dos documentos pessoais do usuário e dos dados publicamente disponíveis dentro da organização.

### <a name="set-up-editorial-acronyms"></a>Configurar acrônimos editoriais

Os administradores de pesquisa podem configurar acrônimos editoriais na [guia acrônimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) no [centro de administração de pesquisa da Microsoft](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch). Você pode adicionar acrônimos de qualquer site ou repositório interno ao centro de administração. Acrônimos editoriais podem ser adicionados ao estado **publicado** ou de **rascunho** :

**Estado publicado**. Os acrônimos estão disponíveis para os funcionários da organização através da pesquisa da Microsoft.

> [!NOTE]
> Pode levar até três dias para que os acrônimos adicionados ao estado publicado fiquem disponíveis no Microsoft Search.

**Estado de rascunho**. Se os administradores desejarem revisar as respostas de acrônimos antes de disponibilizá-las no Microsoft Search, poderão adicionar os acrônimos ao estado de rascunho. Os acrônimos adicionados ao estado de rascunho não estão disponíveis no Microsoft Search. Os administradores precisam adicionar os acrônimos ao estado publicado para torná-los disponíveis.

Os administradores podem adicionar acrônimos individualmente ou importá-los em massa em um arquivo CSV. Carregue um arquivo CSV com os campos mostrados na tabela a seguir:

| Sigla (obrigatório) | Expansão (obrigatória) | Descrição  | Origem | Estado (obrigatório) |
| --------- | --------- | ---------- | --------- |--------- |
| *XXX* | *Abreviatura de abreviação* |  | *URL* | *Publicado ou rascunho* |

### <a name="csv-fields"></a>Campos CSV

**Sigla**. Contém a forma curta ou sigla real. Um exemplo é *DNN*.

**Expansão**. Contém a expansão do acrônimo. Um exemplo é uma *rede neural profunda*.

**Descrição**. Uma breve descrição do acrônimo que oferece aos usuários uma percepção rápida sobre o que o acrônimo e sua média de expansão. Por exemplo, *uma rede neural profunda é uma rede neural com um determinado nível de complexidade, uma rede neural com mais de duas camadas*.

**Fonte**. A URL da página ou site onde você deseja que os usuários vá para obter mais informações sobre o acrônimo.

**Estado**. Este campo pode ter dois valores:

- **Rascunho**. Adiciona o acrônimo ao estado de rascunho.
- **Publicado**. Adiciona a sigla ao estado publicado e a disponibiliza no Microsoft Search.

### <a name="mined-acronyms"></a>Acrônimos minados

Pode ser um desafio para os administradores adicionarem todos os acrônimos usados dentro de uma organização para responder. Esse recurso pode encontrar acrônimos que os administradores de pesquisa nem são compatíveis. Para fazer isso, a pesquisa da Microsoft também extrai acrônimos dessas fontes:

- Emails dos usuários.
- Documentos no [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft onedrive]( https://onedrive.live.com/about/) e [Microsoft OneNote](http://www.onenote.com/).
- Documentos públicos dentro da organização aos quais os usuários têm acesso no SharePoint, no OneDrive ou no OneNote.

A pesquisa da Microsoft garante que apenas usuários com acesso e permissões a um documento possam ver os acrônimos que são minados. Quando um acrônimo é minado da caixa de correio de um usuário, apenas esse usuário pode ver esse acrônimo.

> [!NOTE]
> Nenhuma configuração é necessária para acrônimos minados.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**P: como os dados de editorial e minados são classificados?**

**A:** O recurso atualmente classifica os acrônimos editoriais acima de acrônimos minados.

**P: quanto tempo demora para que os acrônimos editoriais fiquem visíveis na pesquisa da Microsoft após serem publicados?**

**A:**  É necessário até três dias para que os acrônimos adicionados ao estado publicado sejam disponibilizados na pesquisa da Microsoft.

**P: como os usuários acionam as respostas de acrônimos?**

**A**: para obter respostas de acrônimos, os usuários devem inserir padrões de consulta específicos em uma caixa de **pesquisa** do [Bing](https://bing.com) . No momento, as respostas de acrônimo não estão disponíveis no [Office 365](https://Office.com) ou [SharePoint](https://products.office.com/sharepoint/collaboration).

**P: quanto tempo leva para que acrônimos minados apareçam após você receber ou enviar um novo email ou documento?**

**A:** Os acrônimos minados de um novo email ou documento levam até sete dias para serem exibidos nos resultados da pesquisa da Microsoft.

**P: os documentos precisam estar em um formato específico para que a mineração os pegue?**

**A:** Não. Oferecemos suporte a todos os tipos de arquivo, exceto imagem, pastas e arquivos zip.

**P: a Microsoft vai minar as acrônimos de documentos em todos os idiomas?**

**A: A**Microsoft dá suporte apenas à mineração de documentos em inglês. O suporte para outros idiomas será adicionado em fases.

**P: e se minha organização não quiser mostrar acrônimos minados? Posso parar de mostrar acrônimos minados nos resultados da pesquisa?**

**A**: para desativar a exibição de acrônimos minados nos resultados da pesquisa, crie um tíquete de suporte ao cliente seguindo as instruções em [contato com o suporte para produtos de negócios](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).
Depois de criar um tíquete de suporte, serão necessários até 48 horas para que os acrônimos minados parem de aparecer nos resultados da pesquisa.

**P: Quando verá as respostas de acrônimos no [Office 365](https://Office.com) e no [SharePoint Online](https://products.office.com/sharepoint/collaboration)?**

**A**: as respostas de acrônimos no Office 365 e no SharePoint Online fazem parte do nosso roteiro de produtos, mas não é possível fornecer uma data ou um prazo.
