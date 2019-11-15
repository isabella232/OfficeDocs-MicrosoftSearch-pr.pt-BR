---
title: Gerenciar plantas baixas
ms.author: rasrivas
author: rasrivas
manager: tonytha
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: O recurso plantas baixas no Microsoft Search ajuda os usuários a encontrar pessoas, escritórios e outros amenities dentro de um edifício.
ms.openlocfilehash: 9871cda3790f210dc0c406d1d29abe2c571c1085
ms.sourcegitcommit: 21361af7c244ffd6ff8689fd0ff0daa359bf4129
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38626788"
---
# <a name="manage-floor-plans"></a>Gerenciar plantas baixas

Os planos do Microsoft Search Floor ajudam os usuários a encontrar pessoas e salas de reunião dentro de um edifício. Plantas baixas respondam a estas perguntas:
- Onde está o Office do Allan?
- Onde está a sala de reunião C1?

![Mapa de planta baixa que aponta o local do escritório do usuário dentro do edifício.](media/floorplans-officelocation.png)

Para facilitar a localização de respostas a perguntas como essas, as informações sobre os prédios, escritórios e instalações de uma organização precisam estar disponíveis e ser pesquisadas. Organizações maiores normalmente têm equipes de gerenciamento de instalações ou de espaço e podem já ter essas informações disponíveis. Em uma organização menor, o administrador de pesquisa pode ter que criar e adicioná-lo.

## <a name="48-hours-before-you-begin"></a>48 horas antes de começar
Antes de começar a carregar planos de piso, você precisa indexar os locais do Office dos usuários. Dependendo do tamanho da sua organização, pode levar até 48 horas para ser concluída. Se você ignorar esta etapa, receberá erros ao executar o procedimento.

![Captura de tela da página de plantas de piso com "a Microsoft precisa reunir e organizar locais do Office antes de carregar planos de piso".](media/floorplans_hydrationstep.png)

No [centro de administração](https://admin.microsoft.com)do Microsoft 365, vá para **configurações** > **do Microsoft Search** > **Floor Plan**e selecione **introdução**.

Se você não vir este aviso, então você ou alguém em sua organização já iniciou esta etapa.

## <a name="things-to-consider"></a>Itens a considerar
Para ajudar os usuários a encontrar informações sobre escritórios e criar instalações, você precisa adicionar:

|Relação     |Por que isso é importante?  |
|---------|---------|
|Local do edifício    |    Você precisará adicionar cada prédio aos locais de pesquisa da Microsoft. Você deve ter um formato de nomenclatura padrão para cada edifício. Você pode adicionar o edifício usando um endereço de rua ou coordenadas de mapa.     |
|Propriedade **Office** em todas as contas de usuário     |    Cada conta de usuário precisa ter a propriedade do **Office** com o local do escritório. E os locais do Office devem seguir um formato padrão e incluir informações de edifício, chão e sala.   <br> No Azure AD, essa propriedade é chamada de **PhysicalDeliveryOfficeName**.    |
|Arquivo de planta baixa no formato DWG     |   Você precisa de um planta comercial separado para cada andar ou asa da sua construção e incluir as informações do Office no mesmo formato que você usou na Propriedade do Office do usuário. O arquivo precisa estar no formato DWG de desenho do AutoCAD. |

Para obter mais informações, consulte [Best Practices for Microsoft Search Floor Plans](floorplans-bestpractices.md).

## <a name="building-location"></a>Local do edifício

Identificar os edifícios que precisam ser adicionados como locais. O endereço local e as coordenadas de mapa de um edifício são o primeiro ponto de identificação. Se o edifício ainda não for adicionado como um local, o administrador precisará adicioná-lo. Consulte [Manage Locations](manage-locations.md) para obter mais detalhes.

## <a name="floor-plans-files"></a>Arquivos de plantas baixas

Após a identificação de um edifício, você pode adicionar seus planos de piso. Todos os arquivos de planta baixa devem estar no formato DWG. Se sua organização ainda não as tiver, você precisará criar os planos de piso em um aplicativo compatível com DWG. Os planos de piso devem mapear corretamente todas as salas, incluindo salas de conferência ou reuniões, banheiros, cozinhas, salas de email e outras facilidades em cada andar do edifício para habilitar a pesquisa.

### <a name="office-locations"></a>Locais do Office

Para ser mapeado para plantas baixas, todos os locais do Office e os dados do escritório do funcionário devem estar na conta do usuário. Na planta baixa, os locais do Office devem ser exclusivos e não podem ser repetidos. Por exemplo, se duas pessoas compartilharem o Office 2/1173, **2/1173** só poderão ter uma única instância em seus planos de piso, mas as contas de usuário no Azure ad terão o mesmo local do Office.

![floorplans-peoplecard. png](media/floorplans-peoplecard.png)

 > [!Note] 
 > Quando um usuário procura uma sala ou um local do escritório de um colega, os números de sala em plantas baixas são correspondidos com os locais do Office no Azure AD. Se uma correspondência for encontrada, o mapa será exibido.

## <a name="add-floor-plan"></a>Adicionar planta baixa

 Na primeira vez que você passa para os planos de piso, você pode ver uma observação na parte superior da página que diz, *a Microsoft precisa reunir e organizar os locais do Office para que você possa carregar planos de piso*. Selecione **introdução** para indexar seus locais do Microsoft Azure AD. 

1. No [centro de administração](https://admin.microsoft.com), vá para **configurações** > **do Microsoft Search** >**Floor Plan**e selecione **Adicionar plantas baixas**.
4. Selecione o edifício no menu suspenso e selecione **Avançar**. Se o edifício não estiver listado, você precisará adicioná-lo em locais. Consulte [gerenciar locais](manage-locations.md) para obter mais informações.
6. Selecione **carregar arquivos**e, em seguida, selecione a planta baixa que você deseja carregar. 
1. Após o carregamento do arquivo ter êxito, você precisará identificar como o número de chão ou o asa será representado. 
7. Insira o código que identifica o edifício. O código de construção pode ser encontrado na conta do usuário na propriedade **local do escritório** . Por exemplo, se o local do escritório do usuário é **2/1173**, o código de construção é **2**. 
9. Revise e identifique os padrões de local para todos os planos de piso carregados e selecione **Avançar**.
10. Quando estiver pronto, selecione **publicar** para tornar o plano de planta baixa pesquisável.

> [!Note] 
> Quando uma planta baixa estiver em um estado de rascunho, ela estará incompleta. Um rascunho permite que os stakeholders coordenem o carregamento e a criação de plantas baixas. Também permite implantar plantas baixas em estágios.

## <a name="edit-floor-plans"></a>Editar plantas baixas

1. No [centro de administração](https://admin.microsoft.com), vá para **configurações** > **planos de piso**de pesquisa > da**Microsoft**. 
1. Selecione **publicado** ou **rascunho**, selecione a planta baixa que você deseja alterar e, em seguida, selecione **Editar**.
5. Faça as alterações e selecione **salvar**.

## <a name="troubleshoot-errors"></a>Erros de solução de problemas

Você não pode ir para a próxima etapa de definir informações de piso, de asa e de sala até que todos os erros sejam corrigidos. A tabela a seguir lista as mensagens de erro de upload de arquivo e as ações para corrigir os problemas.

| Mensagem de erro   | Tipo    | Action       |
|:----------------| :--------- | :-------------- |
| Não é possível ler CC_1. dwg. Carregue novamente ou exclua a planta baixa. | Error |  Tente carregar o arquivo novamente. Se isso não funcionar, exclua o arquivo e tente novamente. |
| Há dois arquivos chamados CC_1. dwg. Exclua um deles ou recarregue com outro nome.| Error | Se o nome do arquivo estiver incorreto, torne o nome do arquivo exclusivo adicionando informações de chão ou de asa e, em seguida, carregue o arquivo novamente. <br><br>Se você adicionou acidentalmente o mesmo arquivo duas vezes, basta excluí-lo. |
| Nenhum dado encontrado. | Error | Verifique seu arquivo para certificar-se de que ele é o correto e, em seguida, carregue-o novamente ou exclua-o. |
| As referências externas estão ausentes neste arquivo. Carregue o "CC_1_furniture. dwg" ou exclua esse arquivo. | Aviso | Carregar arquivos de referência externa ou excluir.|
| Não foi possível ler números ou marcas de sala no arquivo DWG. Exclua esse arquivo. | Aviso | Verifique o arquivo DWG para certificar-se de que os dados estão incluídos e, em seguida, exclua o arquivo e tente novamente. |
