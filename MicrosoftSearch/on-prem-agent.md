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
ROBOTS: NoIndex
description: Agente local
ms.openlocfilehash: 5dbca392fefdcc11de253fd244cc98a6adcee68a
ms.sourcegitcommit: e8d770fa72ac83e074a5de57098cb55d06d8db07
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588363"
---
# <a name="graph-connector-agent"></a>Agente do conector do Graph

O uso de conectores de gráfico local exige que você instale o software de *agente do conector do Graph* . Ele permite a transferência segura de dados entre os dados locais e as APIs do conector do Graph. Este artigo orienta você durante a instalação e a configuração do agente.

## <a name="installation"></a>Instalação

Baixe a versão mais recente do agente do conector do Graph [aqui](https://aka.ms/gcadownload) e instale o software usando o assistente de instalação. Usando a configuração recomendada da máquina descrita abaixo, o software pode lidar com até três conexões. As conexões além disso podem degradar o desempenho de todas as conexões no agente.

Configuração recomendada:

* Windows 10, Windows Server 2016 R2 e superior
* [.NET Core desktop Runtime 3,1 (x64)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8 núcleos, 3 GHz
* 16 GB de RAM, 2 GB de espaço em disco
* Acesso de rede à fonte de dados e à Internet por meio de 443

## <a name="create-and-configure-an-app-for-the-agent"></a>Criar e configurar um aplicativo para o agente  

Antes de usar o agente, você deve criar um aplicativo e configurar os detalhes de autenticação.

### <a name="create-an-app"></a>Criar um aplicativo

1. Vá para o [portal do Azure](https://portal.azure.com) e entre com as credenciais de administrador do locatário.
2. Navegue até registros de aplicativos do **Azure Active Directory**  ->  **App registrations** no painel de navegação e selecione **novo registro**.
3. Forneça um nome para o aplicativo e selecione **registrar**.
4. Anote a ID do aplicativo (cliente).
5. Abra **permissões de API** do painel de navegação e selecione **Adicionar uma permissão**.
6. Selecione **Microsoft Graph** e, em seguida, **permissões de aplicativo**.
7. Procure "ExternalItem. ReadWrite. All" e "Directory. Read. All" nas permissões e selecione **adicionar permissões**.
8. Selecione **conceder consentimento do administrador para [locatárioname]** e confirmar selecionando **Sim**.
9. Verifique se as permissões estão no estado "concedido".
     ![Permissões mostradas como concedidas na coluna verde à direita.](media/onprem-agent/granted-state.png)

### <a name="configure-authentication"></a>Configurar autenticação

Os detalhes de autenticação podem ser fornecidos usando um segredo do cliente ou um certificado. Siga as etapas para sua escolha.

#### <a name="configuring-the-client-secret-for-authentication"></a>Configurando o segredo do cliente para autenticação

1. Vá para o [portal do Azure](https://portal.azure.com) e entre com as credenciais de administrador do locatário.
2. Abra o **registro de aplicativos** no painel de navegação e vá para o aplicativo apropriado. Em **gerenciar**, selecione **certificados e segredos**.
3. Selecione **novo segredo do cliente** e selecione um período de expiração para o segredo. Copie o segredo gerado e salve-o porque ele não será mostrado novamente.
4. Use este segredo do cliente junto com a ID do aplicativo para configurar o agente. Não é possível usar espaços em branco no campo **nome** do agente. Caracteres numéricos Alfa são aceitos.

#### <a name="using-a-certificate-for-authentication"></a>Usando um certificado para autenticação

Há três etapas simples para usar a autenticação baseada em certificado:

1. Criar ou obter um certificado
1. Carregar o certificado no portal do Azure
1. Atribuir o certificado ao agente

##### <a name="step-1-get-a-certificate"></a>Etapa 1: obter um certificado

O script a seguir pode ser usado para gerar um certificado autoassinado. Sua organização pode não permitir certificados autoassinados. Nesse caso, use essas informações para entender os requisitos e adquirir um certificado de acordo com as políticas da sua organização.

```Powershell
$dnsName = "<TenantDomain like agent.onmicrosoft.com>" # Your DNS name
$password = "<password>" # Certificate password
$folderPath = "D:\New folder\" # Where do you want the files to get saved to? The folder needs to exist.
$fileName = "agentcert" # What do you want to call the cert files? without the file extension
$yearsValid = 10 # Number of years until you need to renew the certificate
$certStoreLocation = "cert:\LocalMachine\My"
$expirationDate = (Get-Date).AddYears($yearsValid)
$certificate = New-SelfSignedCertificate -DnsName $dnsName -CertStoreLocation $certStoreLocation -NotAfter $expirationDate -KeyExportPolicy Exportable -KeySpec Signature
$certificatePath = $certStoreLocation + '\' + $certificate.Thumbprint
$filePath = $folderPath + '\' + $fileName
$securePassword = ConvertTo-SecureString -String $password -Force -AsPlainText
Export-Certificate -Cert $certificatePath -FilePath ($filePath + '.cer')
Export-PfxCertificate -Cert $certificatePath -FilePath ($filePath + '.pfx') -Password $securePassword
```

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>Etapa 2: carregar o certificado no portal do Azure

1. Abra o aplicativo e navegue até a seção de certificados e segredos no painel esquerdo
1. Selecione "carregar certificado" e carregar o arquivo. cer
1. Abra o **registro do aplicativo** e selecione **certificados e segredos** no painel de navegação. Copie a impressão digital do certificado.

![Lista de certificados do thumbrint quando os certificados e segredos são selecionados no painel esquerdo](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>Etapa 3: atribuir o certificado ao agente

Se você usou o script de exemplo para gerar um certificado, o arquivo PFX pode ser encontrado no local identificado no script.

1. Baixe o arquivo PFX de certificado no computador do agente.
1. Clique duas vezes no arquivo PFX para iniciar a caixa de diálogo de instalação de certificado.
1. Selecione "máquina local" para local de armazenamento ao instalar o certificado.
1. Após instalar o certificado, abra a guia gerenciar certificados de computador por meio do menu iniciar
1. Selecione o certificado recém-instalado em ' pessoal '-> ' certificados '
1. Clique com o botão direito do mouse no certificado e selecione "todas as tarefas"-> ' gerenciar chaves privadas... ' Opção
1. Na caixa de diálogo permissões, selecione Adicionar opção. Na caixa de diálogo seleção de usuário, escreva: "NT Service\GcaHostService" e clique em "OK". Não clique no botão "verificar nomes".
1. Clique em OK na caixa de diálogo permissões. A máquina do agente agora está configurada para que o agente gere tokens usando o certificado.
