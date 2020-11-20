---
title: Agente local
ms.author: rusamai
author: rsamai
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Agente local
ms.openlocfilehash: 30ddf0ac8c6df76d1c598606754066b3d2e93615
ms.sourcegitcommit: 59cdd3f0f82b7918399bf44d27d9891076090f4f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367713"
---
# <a name="on-prem-agent"></a>Agente local

## <a name="graph-connector-agent"></a>Agente do conector do Graph

Os conectores do Graph local exigem que você instale o software de *agente do conector do Graph* . Permite a transferência rápida e segura de dados entre os serviços de nuvem e dados locais. Este artigo orienta você pelas etapas de instalação e configuração do software. Uma vez configurada, ela estará disponível para a criação de conexões com suas fontes de dados locais no [centro de administração do Microsoft 365](https://admin.microsoft.com).

## <a name="installation"></a>Instalação

Baixe a versão mais recente do agente do conector do Graph usando [este link](https://download.microsoft.com/download/d/d/e/dde18236-9c67-437d-a864-894a0a888ef2/AgentPackage.msi) e instale o software usando o assistente de instalação. Com a configuração recomendada da máquina descrita abaixo, o software pode lidar perfeitamente com até três conexões. Qualquer conexão além disso pode prejudicar o desempenho.

Configuração recomendada:

* Windows 10, Windows Server 2012 R2 e superior
* 8 núcleos, 3GHz
* QLE2662 RAM, 1 GB de espaço em disco
* Acesso de rede à fonte de dados e à Internet por meio de 443

## <a name="creating-app-for-the-agent"></a>Criando aplicativo para o agente  

A instância do agente precisa ser alimentada por poucos parâmetros críticos antes da criação de conexões. Esses parâmetros incluem detalhes de autenticação necessários para usar as APIs de inclusão de gráfico.  

Etapas para criar o aplicativo para o agente.

1. Vá para o [portal do Azure](https://portal.azure.com) e entre com as credenciais de administrador do locatário.
2. Navegue até registros de aplicativos do **Azure Active Directory**  ->  **App registrations** no painel de navegação e selecione **novo registro**.
3. Forneça um nome para o aplicativo e selecione **registrar**.
4. Anote a ID do aplicativo (cliente).
5. Abra **permissões de API** do painel de navegação e selecione **Adicionar uma permissão**.
6. Selecione **Microsoft Graph** e, em seguida, **permissões de aplicativo**.
7. Procure "ExternalItem. ReadWrite. All" e "Directory. Read. All" nas permissões e selecione **adicionar permissões**.
8. Selecione **conceder consentimento do administrador para [locatárioname]** e confirmar selecionando **Sim**.
9. Verifique se as permissões estão no Estado concedido.
     ![Permissões mostradas como concedidas na coluna verde à direita.](media/onprem-agent/granted-state.png)

## <a name="configuring-graph-connector-agent"></a>Configurando o agente do conector do Graph

Depois de criar o aplicativo para o agente do, você deve configurar o agente com os detalhes de autenticação apropriados.

Os detalhes de autenticação podem ser fornecidos em um dos formatos a seguir.

### <a name="configuring-the-client-secret-for-authentation"></a>Configurando o segredo do cliente para o authentation

1. Vá para o [portal do Azure](https://portal.azure.com) e entre com as credenciais de administrador do locatário.
2. Abra o **registro de aplicativos** no painel de navegação e vá para o aplicativo apropriado. Em **gerenciar**, selecione **certificados e segredos**.
3. Selecione **novo segredo do cliente** e selecione um período de expiração para o segredo. Copie o segredo gerado e salve-o porque ele não será mostrado novamente.
4. Use este segredo do cliente junto com a ID do aplicativo para configurar o agente. Não use espaços em branco no campo **nome** do agente. Caracteres numéricos Alfa são aceitos.

## <a name="using-thumbprint-certificate-for-authentication"></a>Usando o certificado de impressão digital para autenticação

Se você já configurou os detalhes de autenticação seguindo [a configuração do segredo do cliente para o authentation](#Configuring-the-client-secret-for-authentication) , poderá ir direto para a [visão geral da instalação](configure-connector.md).

1. Abra o **registro do aplicativo** e selecione **certificados e segredos** no painel de navegação. Copie a impressão digital do certificado.
![Lista de certificados do thumbrint quando os certificados e segredos são selecionados no painel esquerdo](media/onprem-agent/certificates.png)
2. Use o segredo do cliente ou a impressão digital para registrar o agente do conector do Graph.
![Registrar formulário solicitando nome, ID do aplicativo, tipo de credencial e certificado](media/onprem-agent/register.png)
