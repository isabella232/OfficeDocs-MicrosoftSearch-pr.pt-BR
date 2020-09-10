---
title: Conector de compartilhamento de arquivos para o Microsoft Search
ms.author: monaray
author: monaray97
manager: jameslau
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Configure o conector de compartilhamento de arquivos para o Microsoft Search.
ms.openlocfilehash: d497e60d7d13749b0ee3cc80a134061ac70407d8
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422969"
---
# <a name="file-share-connector"></a>Conector de compartilhamento de arquivos

Com o conector de compartilhamento de arquivos, os usuários da sua organização podem pesquisar em compartilhamentos de arquivos locais. Os resultados da pesquisa desses compartilhamentos são mesclados com os resultados do [SharePoint](http://sharepoint.com/) e do [Microsoft onedrive for Business](https://onedrive.live.com/about/business/).

Este artigo é para os administradores do [Microsoft 365](https://www.microsoft.com/microsoft-365) ou qualquer pessoa que configure, execute e monitore um conector de compartilhamento de arquivos. Ele explica como configurar seus recursos de conector e conector, limitações e técnicas de solução de problemas.

## <a name="install-a-data-gateway"></a>Instalar um data gateway
Para acessar seus dados de terceiros, você deve instalar e configurar um gateway [do Microsoft Power bi](https://msit.powerbi.com/) . Confira [instalar um gateway local](https://docs.microsoft.com/data-integration/gateway/service-gateway-install) para saber mais.  

## <a name="content-requirements"></a>Requisitos de conteúdo
**Tipos de arquivo**. Somente arquivos nestes formatos podem ser indexados e pesquisados: DOC, DOCM, DOCX, DOT, DOTX, EML, GIF, HTML, JPEG, MHT, MHTML, NWS, OBT, OBD,, PPS, ODS, ODT, a, PDF, POT e PPS, o e o formato. XLS, o, o, o XML e o formato ZIP do. Somente o conteúdo textual desses formatos é indexado. Todo o conteúdo multimídia é ignorado.
 
**Limites de tamanho de arquivo**. O tamanho máximo de arquivo com suporte é de 100 MB. Arquivos que excedem 100 MB são ignorados da indexação. O limite máximo de tamanho processado é de 4 MB. O processamento pára quando o tamanho de um arquivo atinge 4 MB. Como resultado, algumas frases presentes no arquivo podem não funcionar para pesquisa.

## <a name="connect-to-a-data-source"></a>Conectar-se a uma fonte de dados
Na página **conectar-se à fonte de dados** , selecione **compartilhamento de arquivos** e forneça o nome, a ID de conexão e a descrição. Na próxima página, forneça o caminho para o compartilhamento de arquivo e selecione seu gateway instalado anteriormente. Insira as credenciais de uma conta de usuário do [Microsoft Windows](https://microsoft.com/windows) com acesso de leitura para todos os arquivos no compartilhamento. Passe o resto das configurações e publique a conexão.

## <a name="set-the-refresh-schedule"></a>Definir o agendamento de atualização
O intervalo de agendamento de atualização padrão recomendado é de 15 minutos, mas você pode alterá-lo para outro intervalo de sua preferência.

## <a name="set-up-your-search-results-page"></a>Configurar a página de resultados de pesquisa
Para exibir os resultados de conexão de arquivos diferentes nas guias **todos** e **arquivos** , você precisa configurar uma página de resultados do mecanismo de pesquisa [do SharePoint](http://sharepoint.com/) :
- A tabela **All** mostra os resultados combinados de suas conexões de arquivo, arquivos do SharePoint, arquivos do [onedrive](https://onedrive.live.com/about/business/) e sites do SharePoint. 
- O arquivo vertical mostra todos os resultados **de arquivos de** suas conexões, do SharePoint e do onedrive.
Os resultados das conexões de arquivo são adicionados aos resultados já existentes em **todos** os **arquivos** verticais.

Para configurar a página de resultados da pesquisa, siga estas etapas:
1. Crie um conjunto de sites do SharePoint com uma página de pesquisa moderna.

2. Instale um [Shell de gerenciamento do SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588).

3. Abra o Shell de gerenciamento do SharePoint Online como administrador e importe o módulo **Microsoft.SharePoint.Client.dll** presente em `C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll` .

> [!NOTE]
> Esse caminho pode não ser o mesmo para todos os usuários.

Para importar o módulo, execute este comando no [Shell de gerenciamento do SharePoint Online](https://www.microsoft.com/download/details.aspx?id=35588):
```bash
Import-Module "C:\Windows\Microsoft.NET\assembly\GAC_MSIL\Microsoft.SharePoint.Client\v4.0_16.0.0.0__71e9bce111e9429c\Microsoft.SharePoint.Client.dll" 
```

4. Agora, execute este script:
```bash
$orgName = Read-Host -prompt 'Please enter your org name'
$userName = Read-Host -prompt 'Enter user name'
$userCreds = Get-Credential -UserName $userName -Message "Type the password"
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $userCreds

$url = Read-Host -Prompt 'Please enter the site url'
$site = Get-SPOSite -Identity $url
Set-SPOSite $url -DenyAddAndCustomizePages 0

$pwd = Read-Host -AsSecureString 'type the password'
$context = New-Object Microsoft.SharePoint.Client.ClientContext($url)
$credential = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($userName, $pwd)
$context.Credentials = $credential
$web = $context.Web
$context.Load($web)
$web.AllProperties["AllVerticalContent"] = "Combined"
$web.Update()
$context.ExecuteQuery()
$web.AllProperties["FilesVerticalContent"] = "ConnectorsOnly"
$web.Update()
$context.ExecuteQuery()
Set-SPOSite $url -DenyAddAndCustomizePages 1

Write-Host "Success" -ForegroundColor Cyan
Read-Host -Prompt 'Press enter to exit'
```

5. Insira os valores necessários no [Microsoft PowerShell](https://microsoft.com/powershell), como nome da organização, nome de usuário, senha e URL do site. Por **exemplo**, se suas credenciais de administrador são `admin@a830edad9050849823J19081300.onmicrosoft.com` , o nome da sua organização é **a830edad9050849823J19081300**e a URL do site é `https:// a830edad9050849823J19081300.sharepoint.com` .

> [!NOTE]
> A configuração de **propriedadeproperties** só pode ser feita em um nível de conjunto de sites (site de equipe/comms).

6. Agora você pode pesquisar arquivos indexados e ver resultados nas guias **todos** e **arquivos** .

## <a name="search-for-file-share-content-in-the-search-results-page"></a>Pesquisar conteúdo de compartilhamento de arquivo na página de resultados de pesquisa
Para pesquisar conteúdo indexado, vá para a página inicial do [SharePoint](http://sharepoint.com/) do seu locatário de teste. Os resultados serão exibidos nas guias **todos** e **arquivos** .

Devido às restrições do navegador, não é possível selecionar um resultado de arquivo para exibir ou abrir arquivos de pesquisas de compartilhamento de arquivos local. Para abrir esses arquivos, copie o link do resultado do arquivo e cole-o na barra de endereços do navegador do seu sistema. Para o [Windows](https://microsoft.com/windows), use o Windows Explorer. Em seguida, você pode abrir o arquivo no sistema.

![Pesquisa do SharePoint com a caixa de diálogo Copiar link aberta.](media/fileshare-search.png)

## <a name="troubleshooting"></a>Solução de problemas
Se algo estiver muito errado com uma conexão, seu status será exibido como **falha**. Para obter mais informações sobre os três tipos de erros, vá para a página de **detalhes do erro** e selecione a conexão com falha. Confira [gerenciar seu conector](manage-connector.md) para saber mais.
1. **Gateway não acessível (código de erro: 11)**. A máquina gateway para a conexão está inativa. Verifique se o processo do [Power bi](https://msit.powerbi.com/) é executado no computador do gateway.
2. **Erro de autenticação (código de erro: 12)**. As credenciais que foram usadas para criar a conexão expiraram ou não são mais válidas. Para resolver esse erro, insira as credenciais válidas.
3. **Erro interno (código de erro: qualquer coisa diferente de 11 ou 12)**. Há um erro na infraestrutura do conector. Confira o artigo de [feedback](connectors-feedback.md) para saber como relatar esses erros.

## <a name="limitations"></a>Limitações
O conector de compartilhamento de arquivos tem estas limitações na versão prévia:
* Você só pode indexar arquivos com propriedades fixas, não arquivos com propriedades personalizadas.
* As listas de controle de acesso (ACLs) do compartilhamento de arquivos não são suportadas atualmente. Só há suporte para ACLs de NTFS de arquivo.
* Identidades externas não são suportadas. Eles devem ser mapeados para identidades [do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) .
