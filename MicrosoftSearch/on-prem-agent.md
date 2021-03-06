---
title: Agente local
ms.author: rusamai
author: rsamai
manager: jameslau
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
ROBOTS: NoIndex
description: Agente in-prem
ms.openlocfilehash: 5134c0c4459f9d38825451f274e67469956756d2
ms.sourcegitcommit: f76ade4c8fed0fee9c36d067b3ca8288c6c980aa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50508801"
---
# <a name="graph-connector-agent"></a>Agente do conector do Graph

O uso de conectores do Graph in-prem exige que você instale o software de agente *do conector do Graph.* Ele permite a transferência segura de dados entre os dados locais e as APIs do conector do Graph. Este artigo orienta você pela instalação e configuração do agente.

## <a name="installation"></a>Instalação

Baixe a versão mais recente do agente de conector do Graph [aqui](https://aka.ms/gcadownload) e instale o software usando o assistente de instalação. Usando a configuração recomendada do computador descrito abaixo, o software pode manipular até três conexões. Quaisquer conexões além disso podem degradar o desempenho de todas as conexões no agente.

Configuração recomendada:

* Windows 10, Windows Server 2016 R2 e acima
* [.NET Core Desktop Runtime 3.1 (x64)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8 núcleos, 3 GHz
* 16 GB de RAM, 2 GB de espaço em disco
* Acesso de rede à fonte de dados e à Internet por meio do 443

Depois de instalar o agente, se os servidores proxy ou firewalls da sua organização bloquearem a comunicação com domínios desconhecidos, adicione os abaixo à lista de autorizações.

1. *.servicebus.windows.net
2. *.events.data.microsoft.com
3. https://<span>login.microsoftonline.</span>com
4. https://<span>gcs.office.</span> com/
5. https://<span>graph.microsoft.</span> com/


## <a name="create-and-configure-an-app-for-the-agent"></a>Criar e configurar um aplicativo para o agente  

Primeiro, entre e observe que o privilégio mínimo necessário na conta é o administrador de pesquisa. Em seguida, o agente solicitará que você forneça detalhes de autenticação. Use as etapas abaixo para criar um aplicativo e gerar os detalhes de autenticação necessários.

### <a name="create-an-app"></a>Criar um aplicativo

1. Acesse o [portal do Azure](https://portal.azure.com) e entre com credenciais de administrador para o locatário.
2. Navegue **até registros do Aplicativo do Azure Active Directory** no painel de navegação e selecione Novo  ->   **registro**.
3. Forneça um nome para o aplicativo e selecione **Registrar**.
4. Anote a ID do aplicativo (cliente).
5. Abra **permissões de API** no painel de navegação e selecione Adicionar uma **permissão**.
6. Selecione **o Microsoft Graph** e, em seguida, permissões de **aplicativo.**
7. Pesquise "ExternalItem.ReadWrite.All" e "Directory.Read.All" nas permissões e selecione **Adicionar permissões**.
8. Selecione **Conceder consentimento de administrador para [TenantName]** e confirme selecionando **Sim**.
9. Verifique se as permissões estão no estado "concedido".
     ![Permissões mostradas como concedidas na coluna verde à direita.](media/onprem-agent/granted-state.png)

### <a name="configure-authentication"></a>Configurar autenticação

Os detalhes da autenticação podem ser fornecidos usando um segredo do cliente ou um certificado. Siga as etapas de sua escolha.

#### <a name="configuring-the-client-secret-for-authentication"></a>Configurando o segredo do cliente para autenticação

1. Acesse o [portal do Azure](https://portal.azure.com) e entre com credenciais de administrador para o locatário.
2. Abra **o Registro de** Aplicativo no painel de navegação e vá para o Aplicativo apropriado. Em **Gerenciar,** selecione **Certificados e segredos.**
3. Selecione **Novo Segredo do Cliente** e selecione um período de expiração para o segredo. Copie o segredo gerado e salve-o porque ele não será mostrado novamente.
4. Use esse segredo de cliente juntamente com a ID do aplicativo para configurar o agente. Não é possível usar espaços em branco no **campo Nome** do agente. Caracteres numéricos alfa são aceitos.

#### <a name="using-a-certificate-for-authentication"></a>Usando um certificado para autenticação

Há três etapas simples para usar a autenticação baseada em certificado:

1. Criar ou obter um certificado
1. Carregar o certificado no portal do Azure
1. Atribuir o certificado ao agente

##### <a name="step-1-get-a-certificate"></a>Etapa 1: Obter um certificado

O script abaixo pode ser usado para gerar um certificado auto-assinado. Sua organização pode não permitir certificados auto-assinados. Nesse caso, use essas informações para entender os requisitos e adquirir um certificado de acordo com as políticas da sua organização.

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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>Etapa 2: Carregar o certificado no portal do Azure

1. Abra o aplicativo e navegue até a seção certificados e segredos do painel esquerdo
1. Selecione 'Carregar certificado' e carregue o arquivo .cer
1. Abra **o registro do** aplicativo e selecione **Certificados e** segredos do painel de navegação. Copie a impressão digital do certificado.

![Lista de certificados de miniatura quando Certificados e segredos são selecionados no painel esquerdo](media/onprem-agent/certificates.png)

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>Etapa 3: Atribuir o certificado ao agente

Se você usou o script de exemplo para gerar um certificado, o arquivo PFX pode ser encontrado no local identificado no script.

1. Baixe o arquivo pfx de certificado para o computador agente.
1. Clique duas vezes no arquivo pfx para iniciar a caixa de diálogo de instalação do certificado.
1. Selecione 'Máquina Local' para o local do armazenamento durante a instalação do certificado.
1. Depois de instalar o certificado, abra "Gerenciar certificados de computador" por meio do menu Iniciar
1. Selecione o certificado recém-instalado em 'Pessoal' -> 'Certificados'
1. Clique com o botão direito do mouse no certificado e selecione 'Todas as Tarefas' -> 'Gerenciar Chaves Privadas...' Opção
1. Na caixa de diálogo permissões, selecione adicionar opção. Na caixa de diálogo seleção do usuário, escreva: 'NT Service\GcaHostService' e clique em 'OK'. Não clique no botão "Verificar Nomes".
1. Clique em ok na caixa de diálogo permissões. O computador agente agora está configurado para que o agente gere tokens usando o certificado.

## <a name="troubleshooting"></a>Solução de Problemas
1. Se uma conexão falhar com o erro '1011: o agente do conector do Graph não está acessível ou offline.', faça logon no computador onde o agente está instalado e inicie o aplicativo de agente se ainda não estiver em execução. Se a conexão continuar falhando, verifique se o certificado ou o segredo do cliente fornecido ao agente durante o registro não expirou e tem permissões necessárias.
