---
title: Conector Graph salesforce para Pesquisa da Microsoft
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
ms.localizationpriority: medium
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector Graph Salesforce para Pesquisa da Microsoft
ms.openlocfilehash: c2679002affe494ba31777718d265b5526b744c0
ms.sourcegitcommit: ca5ee826ba4f4bb9b9baabc9ae8a130011c2a3d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59375701"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector"></a>Conector Graph Salesforce

O conector Graph Salesforce permite que sua organização indexe os objetos Contatos, Oportunidades, Leads, Casos e Contas em sua instância do Salesforce. Depois de configurar o conector e o conteúdo de índice do Salesforce, os usuários finais podem pesquisar esses itens de qualquer Pesquisa da Microsoft cliente.

> [!NOTE]
> Leia o [**artigo Instalação do conector Graph para**](configure-connector.md) entender as instruções gerais Graph configuração de conectores.

Este artigo é para qualquer pessoa que configure, executa e monitore um conector Graph Salesforce. Ele complementa o processo de instalação geral e mostra instruções que se aplicam somente ao conector Graph Salesforce. Este artigo também inclui informações sobre [Limitações.](#limitations)

>[!IMPORTANT]
>O conector Graph Salesforce atualmente dá suporte ao Verão 19 ou posterior.

## <a name="before-you-get-started"></a>Antes de começar

Para se conectar à sua instância do Salesforce, você precisa da URL da instância do Salesforce, da ID do Cliente e do Segredo do Cliente para autenticação OAuth. As etapas a seguir explicam como você ou o administrador do Salesforce podem obter essas informações da sua conta do Salesforce:

- Faça logoff em sua instância do Salesforce e vá para a Instalação

- Navegue até Apps -> App Manager.

- Selecione **Novo aplicativo conectado**.

- Conclua a seção API da seguinte forma:

    - Marque a caixa de seleção **Habilitar o Oauth Configurações**.

    - Especifique a URL de retorno de chamada como: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)

    - Selecione esses escopos OAuth necessários.

        - Acessar e gerenciar seus dados (api)

        - Execute solicitações em seu nome a qualquer momento (refresh_token, offline_access)

    - Selecione a caixa de seleção para **Exigir segredo para fluxo de servidor Web.**

    - Salve o aplicativo.
    
      > [!div class="mx-imgBorder"]
      > ![Seção API na instância do Salesforce após o administrador ter inserido todas as configurações necessárias listadas acima.](media/salesforce-connector/sf1.png)

- Copie a chave do consumidor e o segredo do consumidor. Essas informações serão usadas como a ID do Cliente e o Segredo do Cliente quando você configurar a conexão Configurações para o conector Graph no portal de administração Microsoft 365.

  > [!div class="mx-imgBorder"]
  > ![Resultados retornados pela seção API na instância salesforce depois que o administrador enviou todas as configurações necessárias. A Chave do Consumidor está na parte superior da coluna esquerda e o Segredo do Consumidor está na parte superior da coluna direita.](media/salesforce-connector/clientsecret.png)
  
- Antes de fechar sua instância do Salesforce, siga estas etapas para garantir que os tokens de atualização não expirem:
    - Acesse Apps -> App Manager
    - Encontre o aplicativo criado e selecione o drop-down à direita. Selecione **Gerenciar**
    - Selecionar **políticas de edição**
    - Para política de token de atualização, selecione **Atualizar token é válido até revogado**

  > [!div class="mx-imgBorder"]
  > ![Selecione a Política de Token de Atualização chamada "O token de atualização é válido até ser revogado".](media/salesforce-connector/oauthpolicies.png)

Agora você pode usar a [central Administração Microsoft 365 para](https://admin.microsoft.com/) concluir o restante do processo de instalação do conector Graph.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: adicionar um conector Graph no Centro de administração do Microsoft 365

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: nomear a conexão

Siga as instruções [gerais de instalação](./configure-connector.md).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Configurar as configurações de conexão

Para a URL de instância, use https://[domain].my.salesforce.com onde o domínio seria o domínio Salesforce para sua organização.

Insira a ID do Cliente e o Segredo do Cliente que você obteve da sua instância do Salesforce e selecione Entrar.

Na primeira vez que você tentar entrar com essas configurações, você obterá um pop-up solicitando que você faça logoff no Salesforce com seu nome de usuário e senha do administrador. A captura de tela abaixo mostra o pop-up. Insira suas credenciais e selecione "Entrar".

  ![Pop-up de logon solicitando nome de usuário e senha.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  >Se o pop-up não aparecer, ele pode estar sendo bloqueado no navegador, portanto, você deve permitir pop-ups e redirecionamentos.

Verifique se a conexão foi bem-sucedida pesquisando uma faixa verde que diz "Conexão bem-sucedida" como mostra a captura de tela abaixo.

  > [!div class="mx-imgBorder"]
  > ![Captura de tela de logon bem-sucedido. A faixa verde que diz "Conexão bem-sucedida" está localizada no campo para a URL da instância do Salesforce](media/salesforce-connector/salesforce-connector-connection-settings.png)

## <a name="step-4-select-properties"></a>Etapa 4: Selecionar propriedades

Selecione os objetos Salesforce que você deseja que o conector pesquise e inclua nos resultados da pesquisa. Se o Contato estiver selecionado, Account também será selecionado automaticamente.

>[!NOTE]
>Se um campo tiver fls (segurança de nível de campo) definido para um perfil, o conector não ingerirá esse campo para nenhum perfil nessa organização do Salesforce. Como resultado, os usuários não poderão pesquisar os valores desses campos, nem aparecerão nos resultados.

## <a name="step-5-manage-search-permissions"></a>Etapa 5: Gerenciar permissões de pesquisa

Você precisará escolher quais usuários verão os resultados da pesquisa nesta fonte de dados. Se você permitir que Azure Active Directory apenas determinados usuários do Azure AD (Azure AD) ou não do Azure AD vejam os resultados da pesquisa, certifique-se de mapear as identidades.

### <a name="step-5a-select-permissions"></a>Etapa 5.a: Selecionar permissões

Você pode optar por ingerir listas de controle de acesso (ACLs) de sua instância do Salesforce ou permitir que todos em sua organização vejam os resultados da pesquisa a partir dessa fonte de dados. As ACLs podem incluir Azure Active Directory identidades (AAD) (usuários federados do Azure AD para o Salesforce), identidades não-Azure AD (usuários nativos do Salesforce que têm identidades correspondentes no Azure AD) ou ambos.

>[!NOTE]
>Se você usar um Provedor de Identidade de terceiros, como Ping ID ou secureAuth, selecione "não-AAD" como o tipo de identidade.

> [!div class="mx-imgBorder"]
> ![Selecione a tela de permissões que foi concluída por um administrador. O administrador selecionou a opção "Somente pessoas com acesso a essa fonte de dados" e também selecionou "AAD" em um menu suspenso de tipos de identidade.](media/salesforce-connector/sf6.png)

Se você optou por ingerir um ACL da sua instância do Salesforce e selecionou "não-AAD" para o tipo de identidade, consulte Mapear suas Identidades [não-Azure AD](map-non-aad.md) para obter instruções sobre como mapear as identidades.

### <a name="step-5b-map-aad-identities"></a>Etapa 5.b: Mapear identidades do AAD

Se você optou por ingerir um ACL da sua instância do Salesforce e selecionou "AAD" para o tipo de identidade, consulte Mapear suas Identidades do [Azure AD](map-aad.md) para obter instruções sobre como mapear as identidades. Para saber como configurar o SSO do Azure AD para Salesforce, consulte este [tutorial](/azure/active-directory/saas-apps/salesforce-tutorial).

### <a name="apply-user-mapping-to-sync-your-salesforce-identities-to-azure-ad-identities"></a>Aplicar mapeamento de usuário para sincronizar suas identidades do Salesforce às identidades do Azure AD

Neste vídeo, você pode ver o processo de autenticação à sua instância do Salesforce, sincronizar suas identidades não Azure Active Directory com suas identidades Azure Active Directory e aplicar os recortes de segurança apropriados aos itens do Salesforce.

> [!VIDEO https://www.youtube-nocookie.com/embed/SZYiFxZMKcM]

## <a name="step-6-assign-property-labels"></a>Etapa 6: Atribuir rótulos de propriedade

Você pode atribuir uma propriedade de origem a cada rótulo escolhendo a partir de um menu de opções. Embora essa etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá melhores resultados de pesquisa para usuários finais. Por padrão, algumas das propriedades de origem "Title", "URL", "CreatedBy" e "LastModifiedBy" já foram atribuídas.

## <a name="step-7-manage-schema"></a>Etapa 7: Gerenciar esquema

Você pode selecionar quais propriedades de origem devem ser indexadas para que elas sejam acionadas nos resultados da pesquisa. O assistente de conexão por padrão seleciona um esquema de pesquisa com base em um conjunto de propriedades de origem. Você pode modificá-lo selecionando as caixas de seleção para cada propriedade e atributo na página esquema de pesquisa. Os atributos de esquema de pesquisa incluem Pesquisa, Consulta, Recuperação e Refinamento.
Refinar permite definir as propriedades que podem ser usadas posteriormente como refinadores ou filtros personalizados na experiência de pesquisa.  

> [!div class="mx-imgBorder"]
> ![Selecione o esquema para cada propriedade de origem. As opções são Consulta, Pesquisa, Recuperação e Refine.](media/salesforce-connector/sf9.png)

## <a name="step-8-set-the-refresh-schedule"></a>Etapa 8: Definir o cronograma de atualização

O conector do Salesforce dá suporte apenas a agendas de atualização para rastreamentos completos no momento.

>[!IMPORTANT]
>Um rastreamento completo localiza objetos excluídos e usuários que foram sincronizados anteriormente com o índice Pesquisa da Microsoft de dados.

A agenda recomendada é de uma semana para um rastreamento completo.

## <a name="step-9-review-connection"></a>Etapa 9: Analisar conexão

Siga as instruções [gerais de instalação](./configure-connector.md).

>[!TIP]
>**Tipo de resultado padrão**
>* O conector salesforce registra automaticamente um [tipo de resultado](./customize-search-page.md#step-2-create-result-types) depois que o conector é publicado. O tipo de resultado usa um layout de [resultado](./customize-results-layout.md) gerado dinamicamente com base nos campos selecionados na etapa 3.
>* Você pode gerenciar o tipo de resultado navegando até [**Tipos de**](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/resulttypes) resultado no [Centro de administração do Microsoft 365](https://admin.microsoft.com). O tipo de resultado padrão será nomeado como " `ConnectionId` Padrão". Por exemplo, se sua id de conexão for `Salesforce` , seu layout de resultado será nomeado: "SalesforceDefault"
>* Além disso, você pode optar por criar seu próprio tipo de resultado, se necessário.
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limitações

- O Graph conector atualmente não dá suporte ao compartilhamento e compartilhamento baseado em território baseado em Apex usando grupos pessoais do Salesforce.
- Há um bug conhecido na API salesforce que o conector Graph usa, onde os padrões de toda a organização privada para leads não são acadados no momento.  
- Se um campo tiver fls (segurança de nível de campo) definido para um perfil, o conector Graph não ingerirá esse campo para nenhum perfil nessa organização do Salesforce. Como resultado, os usuários não poderão pesquisar os valores desses campos, nem aparecerão nos resultados.  
- Na tela Gerenciar Esquema, esses nomes de propriedade padrão comuns são listados uma vez, as opções são **Consulta,** **Pesquisa,** **Recuperar** e **Refinar** e aplicar a todos ou a nenhum.
    - Nome
    - Url
    - Descrição
    - Fax
    - Telefone
    - MobilePhone
    - Email
    - Tipo
    - Cargo
    - AccountId
    - AccountName
    - AccountUrl
    - AccountOwner
    - AccountOwnerUrl
    - Proprietário
    - OwnerUrl
    - CreatedBy
    - CreatedByUrl
    - LastModifiedBy
    - LastModifiedByUrl
    - LastModifiedDate
    - ObjectName
