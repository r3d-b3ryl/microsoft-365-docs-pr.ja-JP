---
title: 単一の PowerShell ウィンドウですべての Microsoft 365 サービスに接続する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/23/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
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
ms.openlocfilehash: babb5c308310e1444a2ac20b6557f4f7a2050f79
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66016902"
---
# <a name="connect-to-all-microsoft-365-services-in-a-single-powershell-window"></a>単一の PowerShell ウィンドウですべての Microsoft 365 サービスに接続する

PowerShell を使用して Microsoft 365 を管理する場合は、同時に複数の PowerShell セッションを開くことができます。 ユーザー アカウント、SharePoint Online、Exchange Online、Microsoft Teams、Microsoft Defender for Office 365 の機能 (セキュリティ)、および Microsoft Purview コンプライアンス機能を管理するためのさまざまな PowerShell ウィンドウがある場合があります。

このシナリオでは、サービス間管理のためにウィンドウ間でデータを交換できないため、Microsoft 365 の管理に最適な状況ではありません。 この記事では、PowerShell の単一インスタンスを使用して、Microsoft 365 アカウント、Exchange Online、SharePoint Online、Microsoft Teams、Defender for Office 365 Microsoft Purview コンプライアンスの機能を管理する方法について説明します。

>[!Note]
>この記事には現在、ワールドワイド (+ GCC) クラウドに接続するコマンドのみ含まれています。 メモでは、他の Microsoft 365 クラウドへの接続に関する記事へのリンクを提供しています。

## <a name="before-you-begin"></a>開始する前に

PowerShell の単一のインスタンスからすべての Microsoft 365 を管理する前に、次の前提条件を考慮してください。

- Microsoft 365 の職場または学校のアカウントは、Microsoft 365 管理者ロールのメンバーである必要があります。 詳細については、[「管理者の役割について」](../admin/add-users/about-admin-roles.md) を参照してください。 これは Microsoft 365向け PowerShell の要件ではあるものの、他のすべての Microsoft 365 サービスについては必ずしも当てはまりません。

- 次の Windows の 64 ビット バージョンを使用できます。
  - Windows 11
  - Windows 10
  - Windows 8.1 または Windows 8
  - Windows Server 2019
  - Windows Server 2016
  - Windows Server 2012 R2 または Windows Server 2012
  - Windows 7 Service Pack 1 (SP1)*
  - Windows Server 2008 R2 SP1*

    \*Microsoft .NET Framework 4.5 をインストールする必要があります。*x* と、Windows Management Framework 3.0 または4.0 です。 詳細については、 [Windows Management Framework](/powershell/scripting/windows-powershell/wmf/overview) を参照してください。

- Azure Active Directory (Azure AD)、Exchange Online、Defender for Office 365、Microsoft Purview コンプライアンス、SharePoint Online、Teams に必要なモジュールをインストールする必要があります。

  - [Azure Active Directory V2](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)
  - [SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251)
  - [Teams PowerShell モジュール](/microsoftteams/teams-powershell-overview)
  - [Exchange Online PowerShell V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exchange-online-powershell-v2-module)
  - [Teams PowerShell の概要](/microsoftteams/teams-powershell-overview)

- Exchange Online、Defender for Office 365、および Microsoft Purview コンプライアンスの署名済みスクリプトを実行するように PowerShell を構成する必要があります。 管理者特権の PowerShell セッション (**管理者として実行** する PowerShell セッション) で、次のコマンドを実行します。

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

   > [!NOTE]
   > PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。これらのコマンドレットは PowerShell から実行する必要があります。

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

6. これらのコマンドを実行して、セキュリティ & コンプライアンス PowerShell に接続します。

   ```powershell
   $acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
   Connect-IPPSSession -UserPrincipalName $acctName
   ```

   > [!NOTE]
   > ワールドワイド以外でセキュリティ & コンプライアンス PowerShell for Microsoft 365 に接続するために、「[セキュリティ & コンプライアンス PowerShell への接続](/powershell/exchange/connect-to-scc-powershell)」を参照してください。

7. 次のコマンドを実行して、Teams PowerShell に接続します。

   ```powershell
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   > [!NOTE]
   > Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。 最新の Teams PowerShell パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。
   >
   > *全世界* 以外の Microsoft Teams クラウドに接続する方法については、[「Connect-MicrosoftTeams」](/powershell/module/teams/connect-microsoftteams)を参照してください。

### <a name="azure-active-directory-powershell-for-graph-module-when-using-just-a-password"></a>パスワードのみを使用する場合の Azure Active Directory PowerShell for Graph モジュール

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
#Security & Compliance
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module-when-using-just-a-password"></a>パスワードのみを使用する場合の Microsoft Azure Active Directory モジュール for Windows PowerShell モジュール

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
Connect-ExchangeOnline -ShowProgress $true
#Security & Compliance
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="connection-steps-when-using-multi-factor-authentication"></a>多要素認証を使用する場合の接続手順

### <a name="azure-active-directory-powershell-for-graph-module-when-using-mfa"></a>MFA を使用する場合の、Azure Active Directory PowerShell for Graph module モジュール

以下は、Graph モジュール用 Azure Active Directory PowerShell で多要素認証を使用する場合に、複数の Microsoft 365 サービスに接続するための単一ブロック内のすべてのコマンドです。

```powershell
$acctName="<UPN of the account, such as belindan@litwareinc.onmicrosoft.com>"
$orgName="<for example, litwareinc for litwareinc.onmicrosoft.com>"
#Azure Active Directory
Connect-AzureAD
#SharePoint Online
Connect-SPOService -Url https://$orgName-admin.sharepoint.com
#Exchange Online
Connect-ExchangeOnline -UserPrincipalName $acctName -ShowProgress $true
#Security & Compliance
Connect-IPPSSession -UserPrincipalName $acctName
#Teams and Skype for Business Online
Import-Module MicrosoftTeams
Connect-MicrosoftTeams
```

### <a name="microsoft-azure-active-directory-module-for-windows-powershell-module-when-using-mfa"></a>MFA を使用する際の、Microsoft Azure Active Directory モジュール for Windows PowerShell モジュール

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

PowerShell ウィンドウを閉じるには、次のコマンドを実行して、SharePoint Online、Teams、Defender for Office 365、および Microsoft Purview コンプライアンスへのアクティブなセッションを削除します。

```powershell
Disconnect-SPOService; Disconnect-MicrosoftTeams; Disconnect-ExchangeOnline
```

## <a name="see-also"></a>関連項目

- [PowerShell を使用して Microsoft 365 に接続する](connect-to-microsoft-365-powershell.md)
- [PowerShell を使用して SharePoint Online を管理する](manage-sharepoint-online-with-microsoft-365-powershell.md)
- [Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
