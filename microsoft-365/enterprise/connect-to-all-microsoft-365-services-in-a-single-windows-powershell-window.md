---
title: 単一の PowerShell ウィンドウですべての Microsoft 365 サービスに接続する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/02/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- Ent_Office_Other
- O365ITProTrain
- httpsfix
ms.assetid: 53d3eef6-4a16-4fb9-903c-816d5d98d7e8
description: '概要: 単一の PowerShell ウィンドウですべての Microsoft 365 サービスに接続します。'
ms.openlocfilehash: cfe720193da1633c21cbe5be5a39478fe54971f0028e9881f5fe30bee0f29e03
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53849993"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>単一の PowerShell ウィンドウですべての Microsoft 365 サービスに接続する

PowerShell を使用して Microsoft 365 を管理する場合は、同時に複数の PowerShell セッションを開くことができます。 ユーザー アカウント、SharePoint Online、Exchange Online、Skype for Business Online、Microsoft Teams、セキュリティ &amp; コンプライアンス センターを管理するために、異なる PowerShell ウィンドウが必要な場合があります。
  
このシナリオでは、サービス間管理のためにウィンドウ間でデータを交換できないため、Microsoft 365 の管理に最適な状況ではありません。 この記事では、Microsoft 365 アカウント、Skype for Business Online、Exchange Online、SharePoint Online、Microsoft Teams、セキュリティ &amp; コンプライアンス センターを管理する PowerShell の単一のインスタンスを使用する方法について説明します。

>[!Note]
>この記事には現在、ワールドワイド (+ GCC) クラウドに接続するコマンドのみ含まれています。 メモでは、他の Microsoft 365 クラウドへの接続に関する記事へのリンクを提供しています。

## <a name="before-you-begin"></a>開始する前に

PowerShell の単一のインスタンスからすべての Microsoft 365 を管理する前に、次の前提条件を考慮してください。
  
- Microsoft 365 の職場または学校のアカウントは、Microsoft 365 管理者ロールのメンバーである必要があります。 詳細については、[「管理者の役割について」](../admin/add-users/about-admin-roles.md) を参照してください。 これは Microsoft 365向け PowerShell の要件ではあるものの、他のすべての Microsoft 365 サービスについては必ずしも当てはまりません。
    
- 次の Windows の 64 ビット バージョンを使用できます。
    
  - Windows 10
    
  - Windows 8.1 または Windows 8
    
  - Windows Server 2019
    
  - Windows Server 2016
    
  - Windows Server 2012 R2 または Windows Server 2012
    
  - Windows 7 Service Pack 1 (SP1)*
    
  - Windows Server 2008 R2 SP1*
    
    \*Microsoft .NET Framework 4.5 をインストールする必要があります。*x* と、Windows Management Framework 3.0 または4.0 です。 詳細については、 [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview) を参照してください。
    
    Skype for Business Online モジュール、および Microsoft 365 モジュールの要件のため、64 ビット バージョンの Windows を使用する必要があります。
    
- Azure Active Directory (Azure AD)、Exchange Online、SharePoint Online、Skype for Business Online、および Teams に必要なモジュールをインストールする必要があります。
    
  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [Skype for Business Online、PowerShell モジュール](/microsoftteams/teams-powershell-overview)
  - [Exchange Online PowerShell V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [Teams PowerShell の概要](/microsoftteams/teams-powershell-overview)
    
-  Skype for Business Online やセキュリティ&amp;コンプライアンス センターに対して署名付きスクリプトを実行するよう PowerShell を構成する必要があります。 管理者特権の PowerShell セッション (**管理者として実行** する PowerShell セッション) で、次のコマンドを実行します。
    
   ```powershell
   Set-ExecutionPolicy RemoteSigned
   ```

## <a name="connection-steps-when-using-just-a-password"></a>パスワードだけを使用する場合の接続手順

サインインにパスワードだけを使用する場合に、単一の PowerShell ウィンドウ内ですべてのサービスに接続するための次のような手順を説明します。
  
1. Windows PowerShell を開きます。
    
2. 次のコマンドを実行し、Microsoft 365職場または学校のアカウントの資格情報を入力します。
    
   ```powershell
   $credential = Get-Credential
   ```

3. 次のコマンドを実行して、Azure Active Directory PowerShell for Graph モジュールを使用して Azure AD に接続します。
    
   ```powershell
   Connect-AzureAD -Credential $credential
   ```
  
   または、Windows PowerShell モジュール用 Microsoft Azure Active Directory モジュールを使用する場合、次のコマンドを実行します。
      
   ```powershell
   Connect-MsolService -Credential $credential
   ```

   > [!Note]
   > PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。 これらのコマンドレットは、PowerShell から実行する必要があります。

4. 次のコマンドを実行して、SharePoint Online に接続します。 ドメインの組織名を指定します。 たとえば、"litwareinc\.onmicrosoft.com" の場合、組織名の値は "litwareinc" です。
    
   ```powershell
   $orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
   Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
   Connect-SPOService -Url https://$orgName-admin.sharepoint.com -Credential $Credential
   ```

5. 次のコマンドを実行して、Exchange Online に接続します。
    
   ```powershell
   Import-Module ExchangeOnlineManagement
   Connect-ExchangeOnline -ShowProgress $true
   ```

   > [!Note]
   > 全世界以外の Exchange Online for Microsoft 365 クラウドに接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」をご覧ください。

6. 次のコマンドを実行して、セキュリティ &amp; コンプライアンス センター に接続します。
    
   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!Note]
   > Microsoft 365 クラウド向けセキュリティ &amp; コンプライアンス センターに接続するには、[「セキュリティ/コンプライアンス センター PowerShell に接続する」](/powershell/exchange/connect-to-scc-powershell) を参照してください。

7. 次のコマンドを実行して、Teams の PowerShell (および Skype for Business Online) に接続します。
    
   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
  
   > [!Note]
   > Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。 最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。
  
   > [!Note]
   > *全世界* 以外の Microsoft Teams クラウドに接続する方法については、[「Connect-MicrosoftTeams」](/powershell/module/teams/connect-microsoftteams)を参照してください。
  


### <a name="azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュール

以下は、Graph 用 Azure Active Directory PowerShell モジュールを使用する場合の、単一のブロック内のすべてのサービスのコマンドです。 ドメイン ホストの名前とサインインの UPN を指定してから、それらすべてを同時に実行します。
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-AzureAD -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Windows PowerShell モジュール用 Microsoft Azure Active Directory モジュール

以下は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールを使用する場合の、単一のブロック内のすべてのサービスのコマンドです。 ドメイン ホストの名前とサインインの UPN を指定してから、それらすべてを同時に実行します。
  
```powershell
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$credential = Get-Credential -UserName $acctName -Message "Type the account's password."
#Azure Active Directory
Connect-MsolService -Credential $credential
#SharePoint Online
Import-Module Microsoft.Online.SharePoint.PowerShell -DisableNameChecking
Connect-SPOService -Url https://$orgName-admin.sharepoint.com -credential $credential
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a>多要素認証を使用する場合の接続手順

### <a name="azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュール

以下は、Graph モジュール用 Azure Active Directory PowerShell で多要素認証を使用する場合に、複数の Microsoft 365 サービスに接続するための単一ブロック内のすべてのコマンドです。

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```
### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module"></a>Windows PowerShell モジュール用 Microsoft Azure Active Directory モジュール

以下は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールで多要素認証を使用する場合に、複数の Microsoft 365 サービスに接続するための単一ブロック内のすべてのコマンドです。

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-MsolService
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance Center
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

## <a name="close-the-powershell-window"></a>PowerShell ウィンドウを閉じる

PowerShell ウィンドウを閉じるために、次のコマンドを実行して Skype for Business Online、および Teams に対するアクティブなセッションを削除します。
  
```powershell
Remove-PSSession $sfboSession ; Disconnect-SPOService ; Disconnect-MicrosoftTeams 
```

## <a name="see-also"></a>関連項目

- [PowerShell を使用して Microsoft 365 に接続する](connect-to-microsoft-365-powershell.md)
- [PowerShell を使用して SharePoint Online を管理する](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
