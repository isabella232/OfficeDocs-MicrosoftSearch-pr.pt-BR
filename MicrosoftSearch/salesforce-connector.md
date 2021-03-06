---
title: Conector do Salesforce Graph para Pesquisa da Microsoft
ms.author: mecampos
author: mecampos
manager: umas
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector do Salesforce Graph para a Pesquisa da Microsoft
ms.openlocfilehash: 86140a4650593e08188f171be54f1753b73ecf7a
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508819"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a>Conector do Salesforce Graph (visualização)

O conector do Salesforce Graph permite que sua organização indexe os objetos Contatos, Oportunidades, Leads e Contas em sua instância do Salesforce. Depois de configurar o conector e o conteúdo de índice do Salesforce, os usuários finais podem pesquisar esses itens de qualquer cliente de Pesquisa da Microsoft.

> [!NOTE]
> Leia o [**artigo Instalação do conector do Graph**](configure-connector.md) para entender as instruções gerais de configuração dos conectores do Graph.

Este artigo é para qualquer pessoa que configure, executa e monitore um conector do Salesforce Graph. Ele complementa o processo de instalação geral e mostra instruções que se aplicam apenas ao conector do Salesforce Graph. Este artigo também inclui informações sobre [Limitações.](#limitations)

>[!IMPORTANT]
>O conector do Salesforce Graph atualmente dá suporte ao Verão '19 ou posterior.

## <a name="before-you-get-started"></a>Antes de começar

Para se conectar à sua instância do Salesforce, você precisa da URL da instância do Salesforce, da ID do Cliente e do Segredo do Cliente para autenticação OAuth. As etapas a seguir explicam como você ou o administrador do Salesforce podem obter essas informações da sua conta do Salesforce:

- Faça logoff em sua instância do Salesforce e vá para a Instalação

- Navegue até Apps -> App Manager.

- Selecione **Novo aplicativo conectado**.

- Conclua a seção API da seguinte forma:

    - Selecione a caixa de seleção **Habilitar Configurações Oauth**.

    - Especifique a URL de retorno de chamada como: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)

    - Selecione esses escopos OAuth necessários.

        - Acessar e gerenciar seus dados (api)

        - Execute solicitações em seu nome a qualquer momento (refresh_token, offline_access)

    - Selecione a caixa de seleção para **Exigir segredo para fluxo de servidor Web.**

    - Salve o aplicativo.
    
      > [!div class="mx-imgBorder"]
      > ![Seção API na instância do Salesforce após o administrador ter inserido todas as configurações necessárias listadas acima.](media/salesforce-connector/sf1.png)

- Copie a chave do consumidor e o segredo do consumidor. Essas informações serão usadas como a ID do Cliente e o Segredo do Cliente quando você configurar as Configurações de Conexão do seu Conector do Graph no portal de administração do Microsoft 365.

  > [!div class="mx-imgBorder"]
  > ![Resultados retornados pela seção API na instância salesforce depois que o administrador enviou todas as configurações necessárias. A Chave do Consumidor está na parte superior da coluna esquerda e o Segredo do Consumidor está na parte superior da coluna direita.](media/salesforce-connector/clientsecret.png)
  
- Antes de fechar sua instância do Salesforce, siga estas etapas para garantir que os tokens de atualização não expirem:
    - Acesse Apps -> App Manager
    - Encontre o aplicativo criado e selecione o drop-down à direita. Selecione **Gerenciar**
    - Selecionar **políticas de edição**
    - Para política de token de atualização, selecione **Atualizar token é válido até revogado**

  > [!div class="mx-imgBorder"]
  > ![Selecione a Política de Token de Atualização chamada "O token de atualização é válido até revogado"](media/salesforce-connector/oauthpolicies.png)

Agora você pode usar o Centro de [Administração do M365](https://admin.microsoft.com/) para concluir o restante do processo de instalação do conector do Graph.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: Adicionar um conector graph no centro de administração do Microsoft 365

Siga as instruções [gerais de instalação](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: nomear a conexão

Siga as instruções [gerais de instalação](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Configurar as configurações de conexão

Para a URL da instância, use https://[domain].my.salesforce.com onde o domínio seria o domínio Salesforce para sua organização.

Insira a ID do Cliente e o Segredo do Cliente que você obteve da sua instância do Salesforce e selecione Entrar.

Na primeira vez que você tentar entrar com essas configurações, você obterá um pop-up solicitando que você faça logoff no Salesforce com seu nome de usuário e senha do administrador. A captura de tela abaixo mostra o pop-up. Insira suas credenciais e selecione "Entrar".

  ![Pop-up de logon solicitando nome de usuário e senha.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  >Se o pop-up não aparecer, ele pode estar sendo bloqueado no navegador, portanto, você deve permitir pop-ups e redirecionamentos.

Verifique se a conexão foi bem-sucedida pesquisando uma faixa verde que diz "Conexão bem-sucedida" como mostra a captura de tela abaixo.

  > [!div class="mx-imgBorder"]
  > ![Captura de tela de logon bem-sucedido. A faixa verde que diz "Conexão bem-sucedida" está localizada no campo para a URL da instância do Salesforce](media/salesforce-connector/sf5.png)

## <a name="step-4-manage-search-permissions"></a>Etapa 4: Gerenciar permissões de pesquisa

Você precisará escolher quais usuários verão os resultados da pesquisa nesta fonte de dados. Se você permitir que apenas determinados usuários do Azure Active Directory (Azure AD) ou não do Azure AD vejam os resultados da pesquisa, certifique-se de mapear as identidades.

## <a name="step-4a-select-permissions"></a>Etapa 4a: Selecionar permissões

Você pode optar por ingerir listas de controle de acesso (ACLs) de sua instância do Salesforce ou permitir que todos em sua organização vejam os resultados da pesquisa a partir dessa fonte de dados. As ACLs podem incluir identidades do Azure Active Directory (AAD) (usuários federados do Azure AD para o Salesforce), identidades não-Azure AD (usuários nativos do Salesforce que têm identidades correspondentes no Azure AD) ou ambas.

>[!NOTE]
>Se você usar um Provedor de Identidade de terceiros, como Ping ID ou secureAuth, selecione "não-AAD" como o tipo de identidade.

> [!div class="mx-imgBorder"]
> ![Selecione a tela de permissões que foi concluída por um administrador. O administrador selecionou a opção "Somente pessoas com acesso a essa fonte de dados" e também selecionou "AAD" em um menu suspenso de tipos de identidade.](media/salesforce-connector/sf6.png)

Se você optou por ingerir um ACL da sua instância do Salesforce e selecionou "não-AAD" para o tipo de identidade, consulte Mapear suas Identidades [não-Azure AD](map-non-aad.md) para obter instruções sobre como mapear as identidades.

## <a name="step-4b-map-aad-identities"></a>Etapa 4b: Mapear identidades do AAD

Se você optou por ingerir um ACL da sua instância do Salesforce e selecionou "AAD" para o tipo de identidade, consulte Mapear suas Identidades do [Azure AD](map-aad.md) para obter instruções sobre como mapear as identidades. Para saber como configurar o SSO do Azure AD para Salesforce, consulte este [tutorial](https://docs.microsoft.com/azure/active-directory/saas-apps/salesforce-tutorial).

## <a name="step-5-assign-property-labels"></a>Etapa 5: Atribuir rótulos de propriedade

Você pode atribuir uma propriedade de origem a cada rótulo escolhendo a partir de um menu de opções. Embora essa etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá melhores resultados de pesquisa para usuários finais. Por padrão, algumas das propriedades de origem "Title", "URL", "CreatedBy" e "LastModifiedBy" já foram atribuídas.

## <a name="step-6-manage-schema"></a>Etapa 6: Gerenciar esquema

Você pode selecionar quais propriedades de origem devem ser indexadas para que elas sejam acionadas nos resultados da pesquisa. O assistente de conexão por padrão seleciona um esquema de pesquisa com base em um conjunto de propriedades de origem. Você pode modificá-lo selecionando as caixas de seleção para cada propriedade e atributo na página esquema de pesquisa. Os atributos de esquema de pesquisa incluem Pesquisa, Consulta, Recuperação e Refinamento.
Refinar permite definir as propriedades que podem ser usadas posteriormente como refinadores ou filtros personalizados na experiência de pesquisa.  

> [!div class="mx-imgBorder"]
> ![Selecione o esquema para cada propriedade de origem. As opções são Consulta, Pesquisa, Recuperação e Refine](media/salesforce-connector/sf9.png)

## <a name="step-7-set-the-refresh-schedule"></a>Etapa 7: Definir o cronograma de atualização

O conector do Salesforce dá suporte apenas a agendas de atualização para rastreamentos completos no momento.

>[!IMPORTANT]
>Um rastreamento completo localiza objetos excluídos e usuários que foram sincronizados anteriormente com o índice de Pesquisa da Microsoft.

A agenda recomendada é de uma semana para um rastreamento completo.

## <a name="step-8-review-connection"></a>Etapa 8: Revisar conexão

Siga as instruções [gerais de instalação](https://docs.microsoft.com/microsoftsearch/configure-connector).
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limitações

- No momento, o conector graph não dá suporte ao compartilhamento e compartilhamento baseado em território baseado em Apex usando grupos pessoais do Salesforce.
- Há um bug conhecido na API salesforce que o conector do Graph usa, onde os padrões de toda a organização privada para leads não são acadados no momento.  
- Se um campo tiver fls (segurança de nível de campo) definido para um perfil, o conector graph não ingerirá esse campo para nenhum perfil nessa organização do Salesforce. Como resultado, os usuários não poderão pesquisar os valores desses campos, nem aparecerão nos resultados.  
- Na tela Gerenciar Esquema, esses nomes de propriedade padrão comuns são listados uma vez, as opções são **Consulta,** **Pesquisa,** **Recuperar** e **Refinar** e aplicar a todos ou a nenhum.
    - Nome
    - Url
    - Descrição
    - Fax
    - Telefone
    - MobilePhone
    - Email
    - Tipo
    - Título
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
