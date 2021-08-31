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
description: Agente in-prem
ms.openlocfilehash: 4b9dddba7741388f2e6c96510e5f41b196def330
ms.sourcegitcommit: e5d56d6ce1cd285c5af3e0472ce169cb34883017
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2021
ms.locfileid: "58469956"
---
# <a name="microsoft-graph-connector-agent"></a>Agente Graph conector da Microsoft

O uso de conectores in-prem exige que você instale o software de agente do *conector Graph* Microsoft. Ele permite a transferência segura de dados entre os dados locais e as APIs do conector. Este artigo orienta você pela instalação e configuração do agente.

## <a name="installation"></a>Instalação

Baixe a versão mais recente do Graph conector de e instale o [https://aka.ms/GCAdownload](https://aka.ms/gcadownload) software usando o assistente de instalação. Usando a configuração recomendada do computador descrito abaixo, o software pode manipular até três conexões. Quaisquer conexões além disso podem degradar o desempenho de todas as conexões no agente.

Configuração recomendada:

* Windows 10, Windows Server 2016 R2 e acima
* [.NET Core Desktop Runtime 3.1 (x64)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
* 8 núcleos, 3 GHz
* 16 GB de RAM, 2 GB de espaço em disco
* Acesso de rede à fonte de dados e à Internet por meio do 443

Depois de instalar o agente, se os servidores proxy ou firewalls da sua organização bloquearem a comunicação com domínios desconhecidos, adicione os abaixo à lista de autorizações.

1. *.servicebus.windows.net
2. *.events.data.microsoft.com
3. https://<span>logon.microsoftonline.</span> com
4. https://<span>gcs.office.</span> com/
5. https://<span>graph.microsoft.</span> com/

>[!NOTE]
>Não há suporte para autenticação de proxy. Se seu ambiente tiver um proxy que exija autenticação, nossa recomendação é permitir que o agente do conector ignore o proxy.

## <a name="create-and-configure-an-app-for-the-agent"></a>Criar e configurar um aplicativo para o agente  

Primeiro, entre e observe que o privilégio mínimo necessário na conta é o administrador de pesquisa. Em seguida, o agente solicitará que você forneça detalhes de autenticação. Use as etapas abaixo para criar um aplicativo e gerar os detalhes de autenticação necessários.

### <a name="create-an-app"></a>Criar um aplicativo

1. Acesse o [portal do Azure](https://portal.azure.com) e entre com credenciais de administrador para o locatário.

2. Navegue **até Azure Active Directory** de  ->  **aplicativos** no painel de navegação e selecione Novo **registro**.

3. Forneça um nome para o aplicativo e selecione **Registrar**.

4. Anote a ID do aplicativo (cliente).

5. Abra **permissões de API** no painel de navegação e selecione Adicionar uma **permissão**.

6. Selecione **Microsoft Graph** e permissões de **aplicativo.**

7. Pesquise "ExternalItem.ReadWrite.All" e "Directory.Read.All" nas permissões e selecione **Adicionar permissões**.

8. Selecione **Conceder consentimento de administrador para [TenantName]** e confirme selecionando **Sim**.

9. Verifique se as permissões estão no estado "concedido".

    :::image type="content" alt-text="Permissões mostradas como concedidas na coluna verde à direita." source="media/onprem-agent/granted-state.png" lightbox="media/onprem-agent/granted-state.png":::

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
2. Upload certificado para o portal do Azure
3. Atribuir o certificado ao agente

##### <a name="step-1-get-a-certificate"></a>Etapa 1: Obter um certificado

O script abaixo pode ser usado para gerar um certificado auto-assinado. Sua organização pode não permitir certificados auto-assinados. Nesse caso, use essas informações para entender os requisitos e adquirir um certificado de acordo com as políticas da sua organização.

```powershell
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

##### <a name="step-2-upload-the-certificate-in-the-azure-portal"></a>Etapa 2: Upload o certificado no portal do Azure

1. Abra o aplicativo e navegue até a seção certificados e segredos do painel esquerdo.

2. Selecione **Upload certificado e** carregue o arquivo .cer.

3. Abra **o registro do** aplicativo e selecione **Certificados e** segredos do painel de navegação. Copie a impressão digital do certificado.

:::image type="content" alt-text="Lista de certificados de miniatura quando Certificados e segredos são selecionados no painel esquerdo." source="media/onprem-agent/certificates.png" lightbox="media/onprem-agent/certificates.png":::

##### <a name="step-3-assign-the-certificate-to-the-agent"></a>Etapa 3: Atribuir o certificado ao agente

Se você usou o script de exemplo para gerar um certificado, o arquivo PFX pode ser encontrado no local identificado no script.

1. Baixe o arquivo pfx de certificado para o computador agente.

2. Clique duas vezes no arquivo pfx para iniciar a caixa de diálogo de instalação do certificado.

3. Selecione **Máquina Local para** o local do armazenamento durante a instalação do certificado.

4. Depois de instalar o certificado, abra **Gerenciar certificados de computador** por meio menu Iniciar.

5. Selecione o certificado recém-instalado em   >  **Certificados Pessoais.**

6. Clique com o botão direito do mouse no certificado e selecione **Todas as Tarefas** Gerenciar Chaves  >  **Privadas** Opção.

7. Na caixa de diálogo permissões, selecione adicionar opção. Ele aparece em uma nova janela. Selecione a opção "Locais" nele. Selecione o computador no qual o agente está instalado entre a lista de locais mostrados e clique em **OK**.

8. Na caixa de diálogo seleção do usuário, escreva: **NT Service\GcaHostService** e clique em **OK**. Não clique no botão Verificar **Nomes.**

9. Clique em ok na caixa de diálogo permissões. O computador agente agora está configurado para que o agente gere tokens usando o certificado.

## <a name="troubleshooting"></a>Solução de problemas

### <a name="installation-failure"></a>Falha na instalação

Se a instalação falhar, verifique os logs de instalação executando: msiexec /i "< caminho para msi >\GcaInstaller.msi" /L*V "< caminho de destino >\install.log". Se os erros não são resolvêveis, alcance o suporte no MicrosoftGraphConnectorsFeedback@service.microsoft.com com os logs.

### <a name="registration-failure"></a>Falha no registro

Se entrar no aplicativo de configuração falhar com o erro "Falha ao entrar. Clique no botão Entrar para tentar novamente." mesmo após a autenticação do navegador ter êxito, abra services.msc e verifique se O GcaHostService está em execução. Se não estiver, inicie-o manualmente.

Se o serviço falhar ao iniciar com o erro "O serviço não começou devido a uma falha de logon", verifique se a conta virtual NT Service\GcaHostService tem permissão para fazer logon como um serviço no computador. Verifique [este link para](/windows/security/threat-protection/security-policy-settings/log-on-as-a-service) obter instruções. Se a opção para adicionar usuário ou grupo estiver acinzenada na Atribuição de Direitos do Usuário\Políticas Locais, isso significa que o usuário que está tentando adicionar essa conta não tem privilégios de administrador neste computador ou que há uma política de grupo substituindo isso. A política de grupo precisa ser atualizada para permitir que o serviço host seja logon como um serviço.

### <a name="connection-failure"></a>Falha na conexão

Se a ação 'Testar conexão' falhar ao criar conexão com o erro "Verifique nome de usuário/senha e o caminho do datasource" mesmo quando o nome de usuário e a senha fornecidos estão corretos, verifique se a conta de usuário tem direitos de logon interativos para o computador onde o agente do conector do Graph está instalado. Consulte a documentação sobre [o gerenciamento de política de logon](/windows/security/threat-protection/security-policy-settings/allow-log-on-locally#policy-management) para verificar os direitos de logon. Verifique também se a fonte de dados e o computador agente estão na mesma rede.

Se uma conexão falhar com o erro "1011: o agente do conector do Graph não está acessível ou offline.", faça logon no computador onde o agente está instalado e inicie o aplicativo de agente se ainda não estiver em execução. Se a conexão continuar falhando, verifique se o certificado ou o segredo do cliente fornecido ao agente durante o registro não expirou e tem permissões necessárias.
