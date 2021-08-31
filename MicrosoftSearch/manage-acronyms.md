---
title: Gerenciar respostas de acrônimo no Pesquisa da Microsoft
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
description: Criar e atualizar respostas de acrônimos Pesquisa da Microsoft
ms.openlocfilehash: 3b0f87fb252c3e88160f1b3753aad09b1e3f5083
ms.sourcegitcommit: e5d56d6ce1cd285c5af3e0472ce169cb34883017
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "58470244"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Gerenciar respostas de acrônimos Pesquisa da Microsoft

Os usuários geralmente têm acrônimos e abreviações desconhecidos usados por sua organização ou equipe. Os termos específicos para organizações ou equipes podem ser novos para pessoas que se movem de uma equipe para outra, trabalham com equipes de parceiros internas ou são novos para a organização.

As organizações nem sempre têm uma única referência para sua terminologia padrão. A falta de uma única referência torna difícil encontrar definições para esses acrônimos. Pesquisa da Microsoft resolve esse problema com acrônimos.

## <a name="what-users-experience"></a>O que os usuários experimentam

Pesquisa da Microsoft usuários podem obter definições com acrônimos em [Bing](https://Bing.com), [SharePoint](https://products.office.com/sharepoint/collaboration), [Office 365](https://Office.com), Outlook na Web, Outlook Mobile (Android) e Teams Mobile (iOS e Android). Na caixa **Pesquisa,** os usuários entram em consultas como estes exemplos:

- *O que é* DNN
- *Definir* DNN
- Definição de *DNN*
- *Expandir* DNN
- Expansão  de DNN
- *Significado de* DNN
- DNN *significa*
- DNN *significa*

O resultado inclui todos os significados de DNN presentes na organização do usuário.

> [!NOTE]
> Os usuários devem inserir uma consulta que inclua as palavras-chave *especificadas* do acrônimo para disparar suas respostas correspondentes. As consultas de acrônimo não são sensíveis a minúsculas.

## <a name="set-up-acronyms-answers"></a>Configurar respostas de acrônimos

Na [Centro de administração do Microsoft 365,](https://admin.microsoft.com)vá para [**Acrônimos**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)e selecione **Adicionar acrônimo**.

Pesquisa da Microsoft consulta duas fontes de dados para fornecer respostas de acrônimos às pesquisas dos usuários:

1. **Admin-curated**. Fornecido por administradores de IT no [centro de administração](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms).
2. **Cura do sistema**. Descoberto por Pesquisa da Microsoft de emails e documentos dos usuários, bem como dados disponíveis publicamente dentro da organização.

### <a name="set-up-admin-curated-acronyms"></a>Configurar acrônimos com cura de administrador

Os administradores de pesquisa podem adicionar acrônimos na [guia Acrônimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) [no Pesquisa da Microsoft de administração.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) Você pode adicionar acrônimos de qualquer site interno ou repositório ao centro de administração. Esses acrônimos podem ser adicionados **ao estado Publicado** ou **Rascunho:**

**Estado publicado**. Os acrônimos estão disponíveis para os usuários da organização por meio Pesquisa da Microsoft.

> [!NOTE]
> Leva até um dia para que os acrônimos adicionados ao estado publicado se tornem disponíveis Pesquisa da Microsoft.

**Estado de rascunho**. Se você quiser revisar um acrônimo antes de disponibilizar Pesquisa da Microsoft, adicione o acrônimo em um estado rascunho. Os acrônimos no estado Rascunho não aparecerão nos resultados da pesquisa. Você precisará mover o acrônimo para o estado Publicado para torná-lo exibido nos resultados da pesquisa.

**Estado excluído**. Se você quiser impedir que um acrônimo apareça no Pesquisa da Microsoft, use **Excluir um acrônimo** para adicioná-lo. Para impedir que um acrônimo seja excluído, você precisará excluir o acrônimo excluído e adicioná-lo ou verificar se ele está em sua lista publicada.

Você pode adicionar acrônimos individualmente ou importá-los em massa em um arquivo CSV. Upload um arquivo CSV com os campos mostrados na tabela a seguir:

| Acrônimo (Obrigatório) | Representa (obrigatório) | Url | Descrição  | Estado (Obrigatório) | Última Modificação | Última modificação por | Id |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| *XXX* | *Abreviação escrita* | *Fonte* |  | *Publicado, Rascunho ou Excluído* |  |  |  |

### <a name="csv-fields"></a>Campos CSV

**Acrônimo**. Contém o formulário curto ou acrônimo real. Um exemplo é *DNN*.

**Significa**. Contém a definição do acrônimo. Um exemplo é *Rede Neural Profunda*.

**Descrição**. Uma breve descrição do acrônimo que fornece aos usuários mais informações sobre o acrônimo e sua definição. Por exemplo, uma rede neural profunda é uma rede neural com um determinado nível de complexidade, uma rede *neural com mais de duas camadas*.

**Fonte**. A URL da página ou site onde você deseja que os usuários acessem para obter mais informações sobre o acrônimo.

**Estado**. Este campo pode ter dois valores:

- **Rascunho**. Adiciona o acrônimo ao estado Rascunho.
- **Publicado**. Adiciona o acrônimo ao estado Publicado e o disponibiliza no Pesquisa da Microsoft.
- **Excluído**. Adiciona o acrônimo ao estado Excluído e impede que ele apareça no Pesquisa da Microsoft.

### <a name="system-curated-acronyms"></a>Acrônimos com cura do sistema

Pode ser um desafio para os administradores adicionarem todos os acrônimos usados em uma organização ao Answers. Esse recurso pode encontrar acrônimos que os administradores de pesquisa nem sabem. Para fazer esse trabalho, Pesquisa da Microsoft também descobre e cura acrônimos dessas fontes:

- Emails dos usuários
- Documentos em [SharePoint,](https://products.office.com/sharepoint/collaboration) [Microsoft OneDrive]( https://onedrive.live.com/about/)e [Microsoft OneNote](https://www.onenote.com/)
- Documentos públicos na organização aos SharePoint, OneDrive ou OneNote

Pesquisa da Microsoft garante que somente usuários com acesso e permissões para um documento possam ver os acrônimos descobertos nele. Quando um acrônimo é encontrado na caixa de correio de um usuário, somente esse usuário pode ver esse acrônimo.

> [!NOTE]
> Nenhuma configuração é necessária para acrônimos com cura do sistema.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**P: Como os dados com cura do administrador e do sistema são classificados?**

**R:** A classificação dos resultados pode variar de pessoa para pessoa, pois os resultados são personalizados para cada usuário. Nenhuma dessas categorias sempre terá precedência sobre a outra.

**P: Como os usuários acionam respostas de acrônimos?**

**R:** Para obter respostas de acrônimos, os usuários devem inserir padrões de consulta específicos em uma caixa de pesquisa Bing [,](https://bing.com) [SharePoint](https://products.office.com/sharepoint/collaboration), [Office 365](https://Office.com), Outlook na Web, Outlook Mobile (Android)  ou Teams Mobile (iOS e Android).

**P: Os usuários podem inserir apenas o acrônimo ao pesquisar?**

**R:** No Bing, os usuários agora podem encontrar respostas de acrônimo apenas pesquisando um acrônimo, uma palavra-chave não é mais necessária. Essa mesma experiência será habilitada para outros Pesquisa da Microsoft pontos de entrada em fases.

**P: Quanto tempo leva para que os acrônimos com cura do administrador sejam visíveis Pesquisa da Microsoft depois que eles são publicados?**

**R:** Leva até um dia para que os acrônimos adicionados ao estado publicado se tornem disponíveis Pesquisa da Microsoft.

**P: Quanto tempo leva para que os acrônimos com cura do sistema apareçam depois de receber ou enviar um novo email ou documento?**

**R:** Os acrônimos encontrados em um novo email ou documento levam até sete dias para aparecerem Pesquisa da Microsoft resultados.

**P: O que acontece quando um acrônimo é excluído e publicado?**

**R:** O acrônimo excluído recebe prioridade e impede que o acrônimo publicado apareça nos resultados da pesquisa. Ele não exclui ou remove o acrônimo publicado.

**P: Quanto tempo leva para um acrônimo ser excluído dos Pesquisa da Microsoft resultados?**

**R:** Leva até um dia para um acrônimo excluído parar de aparecer nos resultados da pesquisa.

**P: Para acrônimos com cura do sistema, os documentos precisam estar em um formato específico?**

**R:** Não. Suportamos todos os tipos de arquivo, exceto arquivos de imagem, pasta e zip.

**P: A Microsoft descobrirá acrônimos de documentos em todos os idiomas?**

**R:** A Microsoft só dá suporte a acrônimos com cura do sistema a partir de documentos em inglês, espanhol, francês, italiano, alemão e português. O suporte para outros idiomas será adicionado em fases.

**P: E se minha organização não quiser mostrar acrônimos com cura do sistema? Posso parar de mostrar esse tipo de acrônimo nos meus resultados de pesquisa?**

**R:** Para desativar a exibição de acrônimos com cura do sistema nos resultados da pesquisa, crie um tíquete de suporte ao cliente seguindo as instruções em [Contact support for business products](/microsoft-365/admin/contact-support-for-business-products).
Depois de criar um tíquete de suporte, leva até 48 horas para que os acrônimos com cura do sistema parem de aparecer nos resultados da pesquisa.
