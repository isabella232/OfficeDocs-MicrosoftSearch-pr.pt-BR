---
title: Gerenciar as respostas de acrônimo no Microsoft Search
ms.author: rakkum
author: rakeshMSFT
manager: jeffkizn
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Criar e atualizar respostas de acrônimos no Microsoft Search
ms.openlocfilehash: ff79e3d741e10d401873c29d86739e61c9f53329
ms.sourcegitcommit: e6ceb07cae208648dadd5452a077414ab5a4513f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/22/2020
ms.locfileid: "49728002"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Gerenciar as respostas de acrônimos no Microsoft Search

Geralmente, os usuários podem ter acrônimos e abreviaturas desconhecidos usados por sua organização ou equipe. Os termos específicos para organizações ou equipes podem ser novos para pessoas que se movem de uma equipe para outra, trabalham com equipes de parceiros internas ou que são novos na organização.

As organizações nem sempre têm uma única referência para sua terminologia padrão. A falta de uma única referência dificulta a localização de definições ou expansões desses acrônimos. O Microsoft Search resolve esse problema com acrônimos.

## <a name="what-users-experience"></a>O que os usuários experimentam

Os usuários de pesquisa da Microsoft podem obter definições com acrônimos no [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)e [Office 365](https://Office.com). Na caixa de **pesquisa** , os usuários inserem consultas como estes exemplos:

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

No [centro de administração do Microsoft 365](https://admin.microsoft.com), vá até [**acrônimos**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)e, em seguida, selecione **Adicionar sigla**.

O Microsoft Search consulta duas fontes de dados para fornecer respostas de acrônimos às pesquisas dos usuários:

1. **Administração-organizada**. Fornecido por administradores de ti no [centro de administração](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).
2. **De sistema-organizada**. Descoberto pela Microsoft Search de emails e documentos de usuários e dados publicamente disponíveis dentro da organização.

### <a name="set-up-admin-curated-acronyms"></a>Configurar acrônimos auxiliares de administrador

Os administradores de pesquisa podem adicionar acrônimos à [guia acrônimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) no  [centro de administração de pesquisa da Microsoft](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch). Você pode adicionar acrônimos de qualquer site ou repositório interno ao centro de administração. Esses acrônimos podem ser adicionados ao estado **publicado** ou de **rascunho** :

**Estado publicado**. Os acrônimos estão disponíveis para os usuários da organização através da pesquisa da Microsoft.

> [!NOTE]
> Pode levar até três dias para que os acrônimos adicionados ao estado publicado fiquem disponíveis no Microsoft Search.

**Estado de rascunho**. Se você deseja revisar um acrônimo antes de disponibilizá-lo no Microsoft Search, você pode adicionar o acrônimo em um estado de rascunho. Os acrônimos no estado rascunho não serão exibidos nos resultados da pesquisa. Você precisará mover o acrônimo para o estado publicado para que ele apareça nos resultados da pesquisa.

Você pode adicionar acrônimos individualmente ou importá-los em massa em um arquivo CSV. Carregue um arquivo CSV com os campos mostrados na tabela a seguir:

| Sigla (obrigatório) | Expansão (obrigatória) | Descrição  | Origem | Estado (obrigatório) |
| --------- | --------- | ---------- | --------- |--------- |
| *XXX* | *Abreviatura de abreviação* |  | *URL* | *Publicado ou rascunho* |

### <a name="csv-fields"></a>Campos CSV

**Sigla**. Contém a forma curta ou sigla real. Um exemplo é *DNN*.

**Expansão**. Contém a expansão do acrônimo. Um exemplo é uma *rede neural profunda*.

**Descrição**. Uma breve descrição do acrônimo que oferece aos usuários mais informações sobre o acrônimo e sua expansão. Por exemplo, *uma rede neural profunda é uma rede neural com um determinado nível de complexidade, uma rede neural com mais de duas camadas*.

**Fonte**. A URL da página ou site onde você deseja que os usuários vá para obter mais informações sobre o acrônimo.

**Estado**. Este campo pode ter dois valores:

- **Rascunho**. Adiciona o acrônimo ao estado de rascunho.
- **Publicado**. Adiciona a sigla ao estado publicado e a disponibiliza no Microsoft Search.

### <a name="system-curated-acronyms"></a>Acrônimos organizados pelo sistema

Pode ser um desafio para os administradores adicionarem todos os acrônimos usados dentro de uma organização para responder. Esse recurso pode encontrar acrônimos que os administradores de pesquisa nem são compatíveis. Para fazer isso funcionar, a pesquisa da Microsoft também descobre e busca acrônimos dessas fontes:

- Emails dos usuários
- Documentos no [SharePoint](https://products.office.com/sharepoint/collaboration), [Microsoft onedrive]( https://onedrive.live.com/about/)e [Microsoft OneNote](https://www.onenote.com/)
- Documentos públicos dentro da organização para os quais os usuários têm acesso no SharePoint, OneDrive ou OneNote

A pesquisa da Microsoft garante que somente os usuários com acesso e permissões a um documento possam ver os acrônimos descobertos. Quando um acrônimo é encontrado na caixa de correio de um usuário, apenas esse usuário pode ver esse acrônimo.

> [!NOTE]
> Nenhuma configuração é necessária para acrônimos auxiliares de administrador.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**P: como os dados de administrador e de sistema são classificados de acordo?**

**A:** A classificação dos resultados pode variar de pessoa para pessoa à medida que os resultados são personalizados para cada usuário. Nenhuma dessas categorias sempre terá precedência sobre a outra.

**P: quanto tempo demora para que os acrônimos auxiliares sejam visíveis na pesquisa da Microsoft após serem publicados?**

**A:**  É necessário até três dias para que os acrônimos adicionados ao estado publicado sejam disponibilizados na pesquisa da Microsoft.

**P: como os usuários acionam as respostas de acrônimos?**

**A**: para obter respostas de acrônimos, os usuários devem inserir padrões de consulta específicos em uma caixa de **pesquisa** [Bing](https://bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration)ou [Office 365](https://Office.com) .

**P: quanto tempo leva para que os acrônimos de sistema sejam exibidos depois que você recebe ou envia um novo email ou documento?**

**A:** Os acrônimos encontrados em um novo email ou documento levam até sete dias para serem exibidos nos resultados da pesquisa da Microsoft.

**P: os documentos precisam estar em um formato específico para que a mineração os pegue?**

**A:** Não. Oferecemos suporte a todos os tipos de arquivo, exceto imagem, pastas e arquivos zip.

**P: a Microsoft descobrirá as abreviações de documentos em todos os idiomas?**

**A: A** Microsoft dá suporte apenas à mineração de documentos em inglês. O suporte para outros idiomas será adicionado em fases.

**P: e se minha organização não quiser mostrar os acrônimos de sistema. Posso parar de mostrar esse tipo de sigla nos meus resultados de pesquisa?**

**A**: para desativar a exibição de acrônimos de sistema não organizados em resultados de pesquisa, crie um tíquete de suporte ao cliente seguindo as instruções em [contato com o suporte para produtos de negócios](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?redirectSourcePath=%252f%252farticle%252fContact-Office-365-for-business-support-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b&view=o365-worldwide&tabs=online#BKMK_call_support).
Depois de criar um tíquete de suporte, serão necessários até 48 horas para que os acrônimos de sistema separados parem de aparecer nos resultados da pesquisa.
