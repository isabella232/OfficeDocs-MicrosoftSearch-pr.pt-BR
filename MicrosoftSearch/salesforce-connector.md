---
title: Conector salesforce Graph para a Pesquisa da Microsoft
ms.author: mecampos
author: mecampos
manager: umas
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configurar o conector do Salesforce Graph para a Pesquisa da Microsoft
ms.openlocfilehash: 0b80bf7d3296236887d1cc1bf8e75da976b6a1f1
ms.sourcegitcommit: d39113376db26333872d3a2c7baddc3a3a7aea61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "50084995"
---
<!---Previous ms.author: rusamai --->

# <a name="salesforce-graph-connector-preview"></a>Conector salesforce Graph (visualização)

O conector salesforce Graph permite que sua organização indexe contatos, oportunidades, clientes em geral e objetos de contas em sua instância da Salesforce. Depois de configurar o conector e o conteúdo do índice do Salesforce, os usuários finais podem pesquisar esses itens em qualquer cliente da Pesquisa da Microsoft.

> [!NOTE]
> Leia o [**artigo Configuração do seu conector do Graph**](configure-connector.md) para entender o processo geral de configuração de conectores do Graph.

Este artigo é para qualquer pessoa que configure, executa e monitore um conector do ServiceNow Graph. Ele complementa o processo de instalação geral e mostra instruções que se aplicam somente ao conector do Salesforce Graph. Este artigo também inclui informações sobre [limitações.](#limitations)

>[!IMPORTANT]
>O conector do Salesforce Graph atualmente dá suporte a Verão '19 ou posterior.

## <a name="before-you-get-started"></a>Antes de começar

Para se conectar à sua instância da Salesforce, você precisa da URL da instância da Salesforce, da ID do Cliente e do Segredo do Cliente para autenticação OAuth. As etapas a seguir explicam como você ou seu administrador da Salesforce podem obter essas informações de sua conta da Salesforce:

- Entre na instância da Salesforce e vá para a Instalação

- Navegue até Apps -> App Manager.

- Selecione **Novo aplicativo conectado.**

- Conclua a seção da API da seguinte forma:

    - Marque a caixa de seleção para **Habilitar Configurações do Oauth.**

    - Especifique a URL de retorno de chamada como: [https://gcs.office.com/v1.0/admin/oauth/callback](https://gcs.office.com/v1.0/admin/oauth/callback)

    - Selecione estes escopos OAuth necessários.

        - Acessar e gerenciar seus dados (api)

        - Executar solicitações em seu nome a qualquer momento (refresh_token, offline_access)

    - Marque a caixa de seleção para **Exigir segredo para o fluxo do servidor Web.**

    - Salve o aplicativo.
    
      > [!div class="mx-imgBorder"]
      > ![Seção api na instância salesforce depois que o administrador tiver inserido todas as configurações necessárias listadas acima.](media/salesforce-connector/sf1.png)

- Copie a chave do consumidor e o segredo do consumidor. Essas informações serão usadas como a ID do Cliente e o Segredo do Cliente quando você definir as Configurações de Conexão para seu Conector do Graph no portal de administração do Microsoft 365.

  > [!div class="mx-imgBorder"]
  > ![Resultados retornados pela seção API na instância salesforce depois que o administrador enviou todas as configurações necessárias. A Chave do Consumidor está na parte superior da coluna esquerda e o Segredo do Consumidor está na parte superior da coluna direita.](media/salesforce-connector/clientsecret.png)
  
- Antes de fechar a instância da Salesforce, siga estas etapas para garantir que os tokens de atualização não expirem:
    - Go to Apps -> App Manager
    - Encontre o aplicativo que você criou e selecione o drop-down à direita. Selecionar **Gerenciar**
    - Selecionar **políticas de edição**
    - Para a política de token de atualização, selecionar **Token de atualização é válido até ser revogado**

  > [!div class="mx-imgBorder"]
  > ![Selecione a Política de Token de Atualização chamada "O token de atualização é válido até ser revogado"](media/salesforce-connector/oauthpolicies.png)

Agora você pode usar o Centro de Administração do [M365](https://admin.microsoft.com/) para concluir o restante do processo de instalação do conector do Graph.

## <a name="step-1-add-a-graph-connector-in-the-microsoft-365-admin-center"></a>Etapa 1: Adicionar um conector do Graph no centro de administração do Microsoft 365

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-2-name-the-connection"></a>Etapa 2: Nomear a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

## <a name="step-3-configure-the-connection-settings"></a>Etapa 3: Definir as configurações de conexão

Para a URL da Instância, use https://[domain].my.salesforce.com onde o domínio seria o domínio Salesforce da sua organização.

Insira a ID do Cliente e o Segredo do Cliente obtidos da instância da Salesforce e selecione Entrar.

Na primeira vez que você tentar entrar com essas configurações, você verá um pop-up solicitando que você faça logoff no Salesforce com seu nome de usuário e senha de administrador. A captura de tela abaixo mostra o pop-up. Insira suas credenciais e selecione "Entrar".

  ![Pop-up de logon solicitando nome de usuário e senha.](media/salesforce-connector/sf4.png)

  >[!NOTE]
  >Se o pop-up não aparecer, ele pode estar sendo bloqueado no navegador, portanto, você deve permitir pop-ups e redirecionamentos.

Verifique se a conexão foi bem-sucedida pesquisando uma faixa verde que diz "Conexão bem-sucedida", conforme mostra a captura de tela abaixo.

  > [!div class="mx-imgBorder"]
  > ![Captura de tela do logon bem-sucedido. A faixa verde que diz "Conexão bem-sucedida" está localizada sob o campo da URL da Instância da Salesforce](media/salesforce-connector/sf5.png)

## <a name="step-4-manage-search-permissions"></a>Etapa 4: Gerenciar permissões de pesquisa

Você precisará escolher quais usuários verão os resultados da pesquisa dessa fonte de dados. Se você permitir que apenas determinados usuários do Azure Active Directory (Azure AD) ou do Azure AD vejam os resultados da pesquisa, mapeie as identidades.

## <a name="step-4a-select-permissions"></a>Etapa 4a: Selecionar permissões

Você pode optar por ingerir listas de controle de acesso (ACLs) de sua instância da Salesforce ou permitir que todos em sua organização vejam os resultados de pesquisa dessa fonte de dados. As ACLs podem incluir identidades do Azure Active Directory (AAD) (usuários federados do Azure AD para a Salesforce), identidades não-Azure AD (usuários nativos do Salesforce que têm identidades correspondentes no Azure AD) ou ambas.

>[!NOTE]
>Se você usar um Provedor de Identidade de terceiros, como a ID de Ping ou secureAuth, selecione "não-AAD" como o tipo de identidade.

> [!div class="mx-imgBorder"]
> ![Tela Selecionar permissões que foi concluída por um administrador. O administrador selecionou a opção "Somente pessoas com acesso a essa fonte de dados" e também selecionou "AAD" em um menu suspenso de tipos de identidade.](media/salesforce-connector/sf6.png)

Se você optou por ingerir uma ACL da sua instância do Salesforce e selecionou "não-AAD" para o tipo de identidade, confira Mapear suas identidades não [Azure AD](map-non-aad.md) para obter instruções sobre como mapear as identidades.

## <a name="step-4b-map-aad-identities"></a>Etapa 4b: Mapear identidades do AAD

Se você optou por ingerir uma ACL da sua instância do Salesforce e selecionou "AAD" para o tipo de identidade, confira Mapear as identidades do [Azure AD](map-aad.md) para obter instruções sobre como mapear as identidades. Para saber como configurar o SSO do Azure AD para Salesforce, confira este [tutorial.](https://docs.microsoft.com/azure/active-directory/saas-apps/salesforce-tutorial)

## <a name="step-5-assign-property-labels"></a>Etapa 5: Atribuir rótulos de propriedade

Você pode atribuir uma propriedade de origem a cada rótulo escolhendo em um menu de opções. Embora essa etapa não seja obrigatória, ter alguns rótulos de propriedade melhorará a relevância da pesquisa e garantirá melhores resultados de pesquisa para usuários finais. Por padrão, algumas das etiquetas como "Title", "URL", "CreatedBy" e "LastModifiedBy" já foram atribuídas a propriedades de origem.

## <a name="step-6-manage-schema"></a>Etapa 6: Gerenciar esquema

Você pode selecionar quais propriedades de origem devem ser indexadas para que elas sejam acionadas nos resultados da pesquisa. Por padrão, o assistente de conexão seleciona um esquema de pesquisa com base em um conjunto de propriedades de origem. Você pode modificá-lo selecionando as caixas de seleção de cada propriedade e atributo na página de esquema de pesquisa. Os atributos de esquema de pesquisa incluem Pesquisa, Consulta, Recuperação e Refinamento.
Refinar permite definir as propriedades que podem ser usadas posteriormente como refinadores ou filtros personalizados na experiência de pesquisa.  

> [!div class="mx-imgBorder"]
> ![Selecione o esquema para cada propriedade de origem. As opções são Consulta, Pesquisa, Recuperar e Refinar](media/salesforce-connector/sf9.png)

## <a name="step-7-set-the-refresh-schedule"></a>Etapa 7: Definir o agendamento de atualização

O conector salesforce suporta apenas agendamentos de atualização para rastreamentos completos no momento.

>[!IMPORTANT]
>Um rastreamento completo localiza objetos excluídos e usuários que foram sincronizados anteriormente com o índice da Pesquisa da Microsoft.

O agendamento recomendado é de uma semana para um rastreamento completo.

## <a name="step-8-review-connection"></a>Etapa 8: Analisar a conexão

Siga as instruções [gerais de configuração.](https://docs.microsoft.com/microsoftsearch/configure-connector)
<!---If the above phrase does not apply, delete it and insert specific details for your data source that are different from general setup instructions.-->

<!---## Troubleshooting-->
<!---Insert troubleshooting recommendations for this data source-->

## <a name="limitations"></a>Limitações

- No momento, o conector do Graph não dá suporte ao compartilhamento e compartilhamento baseado em território da Apex usando grupos pessoais da Salesforce.
- Há um bug conhecido na API salesforce que o conector do Graph usa, onde os padrões de toda a organização privada para leads não são compatíveis no momento.  
- Se um campo tiver segurança de nível de campo (FLS) definida para um perfil, o conector do Graph não ingeri esse campo para nenhum perfil nessa organização salesforce. Como resultado, os usuários não poderão pesquisar os valores desses campos, nem aparecerão nos resultados.  
- Na tela Gerenciar Esquema, esses nomes de propriedade padrão comuns são listados uma vez, as opções são **Consulta** **,** **Pesquisa,** Recuperar e **Refinar** e aplicar a todos ou a nenhum.
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
