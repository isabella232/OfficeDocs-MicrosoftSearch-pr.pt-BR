---
title: Gerenciar respostas de acrônimo na Pesquisa da Microsoft
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
description: Criar e atualizar respostas de acrônimos na Pesquisa da Microsoft
ms.openlocfilehash: 45d3cc7b33f27d2f4e77d8099fbfa91e01aabcbb
ms.sourcegitcommit: ef94ffd6111acb929c8343f0f4f82ea109b68fb6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122152"
---
# <a name="manage-acronyms-answers-in-microsoft-search"></a>Gerenciar respostas de acrônimos na Pesquisa da Microsoft

Os usuários geralmente têm acrônimos e abreviações desconhecidos usados por sua organização ou equipe. Os termos específicos para organizações ou equipes podem ser novos para pessoas que mudarem de uma equipe para outra, trabalhem com equipes parceiras internas ou sejam novos na organização.

As organizações nem sempre têm uma única referência para sua terminologia padrão. A falta de uma única referência dificulta encontrar definições ou expansões para esses acrônimos. A Pesquisa da Microsoft resolve esse problema com acrônimos.

## <a name="what-users-experience"></a>O que os usuários experimentam

Os usuários da Pesquisa da Microsoft podem obter definições com acrônimos no [Bing,](https://Bing.com) [no SharePoint](https://products.office.com/sharepoint/collaboration)e [no Office 365.](https://Office.com) Na caixa **Pesquisar,** os usuários ins são consultadas como estes exemplos:

- *O que é* DNN
- *Definir* DNN
- Definição  de DNN
- *Expandir* DNN
- Expansão  de DNN
- *Significado de* DNN
- DNN *significa*

O resultado inclui todos os significados de DNN presentes na organização do usuário.

> [!NOTE]
> Os usuários devem inserir uma consulta que inclua as palavras-chave *especificadas* do acrônimo para disparar suas respostas correspondentes. Consultas de acrônimo não são sensíveis a minúsculas.

## <a name="set-up-acronyms-answers"></a>Configurar respostas de acrônimos

No centro [de administração do Microsoft 365,](https://admin.microsoft.com)vá para Acrônimos e selecione Adicionar **acrônimo.** [](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)

A Pesquisa da Microsoft consulta duas fontes de dados para fornecer respostas de Acrônimos às pesquisas dos usuários:

1. **Administração gerenciada**. Fornecido por administradores de IT no centro [de administração.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms)
2. **Curadado pelo sistema.** Descoberta pela Pesquisa da Microsoft a partir de emails e documentos dos usuários e dados disponíveis publicamente dentro da organização.

### <a name="set-up-admin-curated-acronyms"></a>Configurar acrônimos com administração

Os administradores de pesquisa podem adicionar acrônimos na [guia Acrônimos](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/acronyms) no centro [de administração da Pesquisa da Microsoft.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch) Você pode adicionar acrônimos de qualquer site ou repositório interno ao centro de administração. Esses acrônimos podem ser adicionados **ao estado Publicado** ou **Rascunho:**

**Estado publicado.** Os acrônimos estão disponíveis para os usuários da organização por meio da Pesquisa da Microsoft.

> [!NOTE]
> Pode levar até três dias para que os acrônimos adicionados ao estado Publicado se tornem disponíveis na Pesquisa da Microsoft.

**Estado de rascunho.** Se quiser revisar um acrônimo antes de disponibilizar na Pesquisa da Microsoft, você pode adicionar o acrônimo em um estado rascunho. Os acrônimos no estado Rascunho não aparecerão nos resultados da pesquisa. Você precisará mover o acrônimo para o estado Publicado para que ele apareça nos resultados da pesquisa.

Você pode adicionar acrônimos individualmente ou importá-los em massa em um arquivo CSV. Carregue um arquivo CSV com os campos mostrados na tabela a seguir:

| Acrônimo (obrigatório) | Expansão (obrigatório) | Url | Descrição  | Estado (obrigatório) | Última Modificação | Última modificação por | Id |
| --------- | --------- | --------- | ---------- | --------- |--------- |--------- |--------- |
| *XXX* | *Abreviação spelled out* | *Fonte* |  | *Publicado ou rascunho* |  |  |  |

### <a name="csv-fields"></a>Campos CSV

**Acrônimo**. Contém o formato curto ou acrônimo real. Um exemplo é *DNN*.

**Expansão**. Contém a expansão do acrônimo. Um exemplo é *Deep Neural Network*.

**Descrição**. Uma breve descrição do acrônimo que fornece aos usuários mais informações sobre o acrônimo e sua expansão. Por exemplo, uma rede neural profunda é uma rede neural com um determinado nível de complexidade, uma rede neural com *mais de duas camadas.*

**Fonte**. A URL da página ou site onde você deseja que os usuários acessem para obter mais informações sobre o acrônimo.

**Estado**. Esse campo pode ter dois valores:

- **Rascunho**. Adiciona o acrônimo ao estado Rascunho.
- **Publicado**. Adiciona o acrônimo ao estado Publicado e o disponibiliza na Pesquisa da Microsoft.

### <a name="system-curated-acronyms"></a>Acrônimos com cura do sistema

Pode ser um desafio para os administradores adicionarem todos os acrônimos usados em uma organização às Respostas. Esse recurso pode encontrar acrônimos que os administradores de pesquisa nem sabem. Para fazer esse trabalho, a Pesquisa da Microsoft também descobre e reúne acrônimos destas fontes:

- Emails dos usuários
- Documentos no [SharePoint,](https://products.office.com/sharepoint/collaboration) [Microsoft OneDrive]( https://onedrive.live.com/about/)e [Microsoft OneNote](https://www.onenote.com/)
- Documentos públicos dentro da organização aos qual os usuários têm acesso no SharePoint, OneDrive ou OneNote

A Pesquisa da Microsoft garante que somente os usuários com acesso e permissões para um documento possam ver os acrônimos descobertos a partir dela. Quando um acrônimo é encontrado na caixa de correio de um usuário, somente esse usuário pode ver esse acrônimo.

> [!NOTE]
> Nenhuma configuração é necessária para acrônimos com administração.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**P: Como os dados coletados pelo administrador e pelo sistema são classificados?**

**R:** A classificação dos resultados pode variar de pessoa para pessoa, pois os resultados são personalizados para cada usuário. Nenhuma dessas categorias terá precedência sobre a outra.

**P: Quanto tempo leva para que os acrônimos com administração sejam visíveis na Pesquisa da Microsoft depois que eles são publicados?**

**R:**  Leva até três dias para que os acrônimos adicionados ao estado Publicado se tornem disponíveis na Pesquisa da Microsoft.

**P: Como os usuários disparam respostas de acrônimos?**

**R:** Para obter respostas de acrônimos, os usuários devem inserir padrões de consulta específicos em uma caixa de pesquisa do [Bing,](https://bing.com) [do SharePoint](https://products.office.com/sharepoint/collaboration)ou do [Office 365.](https://Office.com) 

**P: Quanto tempo leva para que os acrônimos de sistema apareçam depois que você receber ou enviar um novo email ou documento?**

**R:** Os acrônimos encontrados em um novo email ou documento levam até sete dias para aparecerem nos resultados da Pesquisa da Microsoft.

**P: Os documentos precisam estar em um formato específico para que a mineração os pegue?**

**R:** Não. Damos suporte a todos os tipos de arquivo, exceto arquivos de imagem, pastas e zip.

**P: A Microsoft descobrirá acrônimos de documentos em todos os idiomas?**

**R:** A Microsoft só dá suporte à mineração de documentos em inglês. O suporte para outros idiomas será adicionado em fases.

**P: E se minha organização não quiser mostrar acrônimos com organização do sistema? Posso parar de mostrar esse tipo de acrônimo nos resultados da pesquisa?**

**R:** Para desativar a exibição de acrônimos de sistema nos resultados da pesquisa, crie um tíquete de suporte ao cliente seguindo as instruções em Contato com o suporte [para produtos comerciais.](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
Depois de criar um tíquete de suporte, leva até 48 horas para que os acrônimos com a cura do sistema parem de aparecer nos resultados da pesquisa.
