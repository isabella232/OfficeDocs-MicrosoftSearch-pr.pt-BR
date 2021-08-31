---
title: Gerenciar planos de piso
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
description: O recurso de planos de piso no Pesquisa da Microsoft ajuda os usuários a encontrar pessoas, escritórios e outras comodidades em um edifício.
ms.openlocfilehash: 6cbba6d764fd3904d251fa53fd96c3a66a6aed6b
ms.sourcegitcommit: e5d56d6ce1cd285c5af3e0472ce169cb34883017
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "58470019"
---
# <a name="manage-floor-plans"></a>Gerenciar planos de piso

Os planos **de** Pesquisa da Microsoft ajudam os usuários a encontrar pessoas e salas de reunião em um edifício. Os planos de piso respondem às seguintes perguntas:

- Onde é o escritório de Allan Deyoung?
- Construção do 2º andar 3
- Encontrar 2/11173

## <a name="add-floor-plans"></a>Adicionar planos de piso

Siga estas etapas para configurar respostas de planos de piso **em Pesquisa da Microsoft**.

### <a name="step-1-determine-your-building-codes"></a>Etapa 1: Determinar seus códigos de construção

Os códigos de construção são usados como parte do local do escritório de um usuário. Você usará esses códigos ao atualizar perfis de usuário. Digamos que sua organização tenha um edifício neste local: *Edifício 2, 350 5th Avenue, Cidade de Nova York, NY 10016*

Aqui estão alguns bons exemplos para o código deste edifício: 2, B2, Building2, Building 2 ou NYCB2. Cada edifício deve ter um código exclusivo.

### <a name="step-2-review-your-floor-plans"></a>Etapa 2: revisar seus planos de piso

Os arquivos de planos de piso devem estar no formato DWG; Arquivos DWG podem conter rótulos de texto. Quando um rótulo de texto marca uma sala, ele é chamado de rótulo de sala. O arquivo DWG deve ter **pelo menos 10 salas marcadas** com rótulos. Aqui estão alguns exemplos de arquivos DWG com tipos de rótulo diferentes:

|**Rótulos de texto, incluindo rótulos de sala**|**Rótulos de texto, mas nenhum rótulo de sala**|**Sem rótulos de texto**|
|:-----:|:-----:|:-----:|
|![floorplans-textandroomlabels.png.](media/floorplans-textandroomlabels.png)|![floorplans-textnoroomlabels.png](media/floorplans-textnoroomlabels.png)|![floorplans-nolabels.png](media/floorplans-nolabels.png)|

Consulte a [seção Perguntas frequentes](#frequently-asked-questions) para obter informações sobre como exibir e atualizar arquivos DWG.

### <a name="step-3-update-office-locations-on-user-profiles"></a>Etapa 3: Atualizar locais do office em perfis de usuário

O local do escritório de um usuário é uma combinação de um código de construção e um rótulo de sala. Por exemplo, se o código de construção for *2* e o rótulo da sala for *1173*, o local do escritório será *2/1173*.

Adicione ou atualize locais de escritório para cada usuário em sua organização. Você pode alterar o local do [](https://admin.microsoft.com) escritório no perfil de usuário no Centro de administração do Microsoft 365 ou pode alterar no Active Directory local para sincronizar com Azure Active Directory. *PhysicalDeliveryOfficeName* é o campo usado para o local do escritório. Se os rótulos de sala não incluirem números de piso, consulte perguntas frequentes sobre dicas.

Neste exemplo, o escritório de Henrique está na sala 1173 no piso 1 do edifício 2.
![floorplans-userlestview.png.](media/floorplans-userlistview.png)

> [!NOTE]
> Para ver os locais de escritório atualizados ao pesquisar planos de piso, você deve atualizar os locais do office para pelo menos **10 pessoas** em cada andar.

### <a name="step-4-verify-office-location"></a>Etapa 4: Verificar o local do office

Use **Pesquisa da Microsoft** para localizar um usuário e verificar se o local do escritório está aparecendo corretamente. Se você acabou de atualizar locais, talvez seja necessário aguardar até **72** horas para que as atualizações apareçam nos resultados da pesquisa.

![floorplans-peoplecard.png.](media/floorplans-peoplecard.png)

### <a name="step-5-add-building-locations"></a>Etapa 5: Adicionar locais de construção

Os planos de piso [usam Locais](manage-locations.md) para definir seus edifícios. Na [Centro de administração do Microsoft 365,](https://admin.microsoft.com)vá para [**Locais**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/locations)e selecione **Adicionar**. Insira o nome, o endereço e as palavras-chave do edifício. Adicione quantos edifícios você precisar.

![floorplans-locations.png.](media/floorplans-locations.png)

Para obter mais detalhes sobre locais, consulte [Manage Locations](manage-locations.md)

### <a name="step-6-gather-and-organize-office-locations"></a>Etapa 6: Reunir e organizar locais do office

Antes de poder usar planos de piso, os locais do office devem ser indexados. Esta é uma operação única que pode levar até 48 horas para ser concluída. O tempo total dependerá do tamanho da sua organização.

No [centro de administração,](https://admin.microsoft.com)vá para [**Planos de piso**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/floorplans)e selecione **Começar**. Se você não vir esse aviso, essa etapa já foi concluída para sua organização

![floorplans_hydrationstep.png.](media/floorplans_hydrationstep.png)

### <a name="step-7-upload-floor-plans"></a>Etapa 7: Upload de piso

1. No centro [de administração,](https://admin.microsoft.com)vá para [**Planos de piso.**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/floorplans)
2. Selecione um edifício na listada e selecione **Próximo**. Se o edifício não estiver listado, volte e adicione [locais de construção.](#step-5-add-building-locations)
3. Selecione **Upload arquivos** e escolha o plano de piso que você está carregando.
4. Quando o carregamento for concluído, você deverá inserir o número de piso representado no arquivo de plano de piso. Em seguida, selecione **Avançar**.
5. (Opcional) Se o piso tiver asas ou zonas, insira esse detalhe.
6. Você verá uma tela de revisão listando quantos locais de escritório foram mapeados para os planos de piso. Selecione **Detalhes** para garantir que o mapeamento está correto.
    - Se nenhum usuário for mapeado ou você não estiver satisfeito com o mapeamento, selecione **Continuar mapeamento**. Para publicar, selecione **Ignorar e publicar**.
7. Insira o código de construção para este plano de piso. O código de construção pode ser encontrado na propriedade de local do escritório dos usuários. Por exemplo, se o local do escritório de um usuário for **2/1173**, o código de construção **será 2**.
8. Na tela de revisão, repita a etapa 6 para garantir que o mapeamento está correto.
9. (Opcional) Revise e identifique os padrões de local para todos os planos de piso carregados e selecione **Next**.
10. Na tela de revisão, repita a etapa 6 para garantir que o mapeamento está correto.
11. Quando estiver pronto, selecione **Publicar para** disponibilizar o plano de piso em **Pesquisa da Microsoft**.

> [!NOTE]
> **Leva 48 horas para que os planos de piso sejam publicados.** Depois disso, os usuários verão resultados de um plano de piso semelhante ao abaixo quando procurarem o escritório de um colega de trabalho.

![floorplans-officelocation.png.](media/floorplans-officelocation.png)

### <a name="step-8-optional-specify-location-patterns"></a>Etapa 8: (Opcional) Especificar padrões de local

Depois de carregar um plano de piso, os rótulos de texto serão comparados aos locais do office nos perfis dos usuários. Se houver menos de 10 combinações, a tela Especificar padrões **de** local será exibida. Os padrões de local são usados para extrair informações de piso, asa e sala de locais do escritório.

![floorplans-locationpattern.png.](media/floorplans-locationpattern.png)

Somente a sala é necessária, o piso e a asa são opcionais e você pode ignorar locais conforme necessário.

## <a name="edit-floor-plans"></a>Editar planos de piso

Para atualizar um plano de piso existente, selecione o plano de piso que você deseja alterar e selecione **Editar**. Faça suas alterações e salve-as.

## <a name="troubleshooting"></a>Solução de problemas

|**Etapa**|**Mensagem de erro**|**Tipo**|**Ação**|
|:-----|:-----|:-----|:-----|
|Upload de piso|Não é possível ler CC_1.dwg. Carregue ou exclua o plano de piso.|Error|Tente carregar o arquivo novamente. Se isso não funcionar, exclua o arquivo e tente novamente.|
|Upload de piso|Há dois arquivos chamados CC_1.dwg. Exclua um deles ou carregue-o com outro nome.|Error|Se o nome do arquivo estiver incorreto, o nome do arquivo será exclusivo adicionando informações de piso ou asa e, em seguida, carregue o arquivo novamente. Se você adicionou acidentalmente o mesmo arquivo duas vezes, exclua-o.|
|Upload de piso|Nenhum dado encontrado.|Error|Verifique seu arquivo para certificar-se de que ele é o correto e, em seguida, carregue-o novamente ou exclua-o.|
|Upload de piso|Referências externas estão ausentes neste arquivo. Carregue CC_1_furniture.dwg ou exclua esse arquivo.|Aviso|Upload ou excluir arquivos de referência externos.|
|Upload de piso|Não foi possível ler números de sala ou marcas no arquivo DWG. Exclua esse arquivo.|Aviso|Verifique seu arquivo DWG para verificar se os dados estão incluídos e, em seguida, exclua o arquivo e tente novamente.|
|Vincular locais do office|Nenhum local de escritório encontrado no Azure Active Directory. Adicione dados de localização Azure Active Directory antes de configurar planos de piso.|Error|[Atualizar locais do office em perfis de usuário](#step-3-update-office-locations-on-user-profiles) |

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**P:** Como posso exibir e editar arquivos DWG?

**R:** Use qualquer uma dessas opções para exibir arquivos DWG:

- Upload o arquivo para SharePoint e abri-lo.
- Abra o arquivo no [Microsoft Visio](https://support.office.com/article/Open-insert-convert-and-save-DWG-and-DXF-AutoCAD-drawings-60cab691-0f4c-4fc9-b775-583273c8dac5) [autodesk DWG TrueView](https://www.autodesk.com/products/dwg).
- Upload o arquivo para [o Visualizador Online do Autodesk.](https://viewer.autodesk.com/)

**P:** Como adicionar rótulos de texto a salas não marcadas?

**R:** Abra o arquivo DWG em um editor e [adicione rótulos de sala.](https://knowledge.autodesk.com/support/autocad-map-3d/learn-explore/caas/CloudHelp/cloudhelp/2019/ENU/MAP3D-Learn/files/GUID-4854F184-6279-4E0C-9487-34A4759017F6-htm.html)

**P:** Como criar ou editar arquivos DWG para fins de teste?

**R:** Crie um arquivo DWG no Microsoft Visio, Autodesk AutoCAD ou qualquer outro editor DWG. Certifique-se de que 10 ou mais salas sejam rotuladas no arquivo.

**P:** Qual é o melhor formato para rótulos de texto em arquivos DWG?

**R:** Para os melhores resultados, os rótulos de texto devem conter números de piso e números de sala. Os exemplos abaixo usam 2 ou SC para o código de construção.
<!-- markdownlint-disable no-inline-html -->
|Tipos de rótulo de sala|ArredMultB|Room|Rótulo de texto de exemplo|Office local (criação de código/rótulo de texto)|
|:-----|:-----|:-----|:-----|:-----|
|Tem o número do piso e da sala|1|173|1173|2/1173|
|| 21 |45|21045|2/21045|
||23|100K|23-100K|23/02-100K|
||1|G06-07|1G06-07|2/1G06-07|
||2|1024A|02.1024A|02/02/1024A|
||2|1024A|02.1024A|02/02/1024A|
||2|105.01|2105.01|2/2105.01|
|Tem código de construção, piso e número de sala|0|X-11-M-12|2-0-X-11-M-12|2/2-0-X-11-M-12<br/>2-0-X-11-M-12|
||2|128A|22128A|2/22128A<br/>22128A|
||1|B2-11|21-B2-11|21/21-B2-11<br/>21-B2-11|
||2|45|SC2045|SC/SC2045<br/>SC2045|

**P:** Posso usar um arquivo DWG que não inclui números de piso?

**R:** Sim, você pode. Ao atualizar os locais de escritório no perfil de Azure Active Directory do usuário, inclua o número do piso como parte do número da sala, mesmo que ele não seja do arquivo DWG. Depois de carregar o arquivo, a tela Especificar padrões de local aparecerá e você poderá indicar ambos os valores.

Por exemplo, um arquivo DWG que inclui números de sala, mas nenhum número de piso, pode ser semelhante a este:

![floorplans-nofloors.png.](media/floorplans-nofloors.png)

O local do escritório no perfil do usuário deve ser 2/1175 onde '2' é o código de construção, '1' é o número do piso e '175' é o número da sala.
