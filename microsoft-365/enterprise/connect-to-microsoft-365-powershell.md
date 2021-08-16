---
title: PowerShell を使用して Microsoft 365 に接続する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Microsoft 365 テナントに接続するには、Microsoft 365 用 PowerShell を使用して、コマンド ラインから管理センターのタスクを実行します。
ms.openlocfilehash: f42112761fe7899742487a79a41973a8c6cb2ab6
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2021
ms.locfileid: "58355006"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>PowerShell を使用して Microsoft 365 に接続する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 用 PowerShell では、コマンド ラインから Microsoft 365 の設定を管理することが可能です。 PowerShell への接続は、必要なソフトウェアをインストールして、Microsoft 365 の組織に接続するだけです。

Microsoft 365 および管理者のユーザー アカウント、グループ、ライセンスへの接続に使用可能な PowerShell モジュールには、次の 2 つのバージョンがあります。

- コマンドレット名に *AzureAD* が含まれる Graph 用 Azure Active Directory PowerShell
- コマンドレット名に *Msol* が含まれる Windows PowerShell 用 Microsoft Azure Active Directory モジュール

現時点で、Graph 用 Azure Active Directory PowerShell モジュールは、ユーザー、グループ、およびライセンスの管理について Windows PowerShell 用 Microsoft Azure Active Directory モジュールの機能に完全に置き換わるものではありません。時には、両方のバージョンを使用する必要があります。同じコンピューターに両方のバージョンを安全にインストールできます。

>[!Note]
>また、Microsoft 365 管理センターで [Azure Cloud Shell](#connect-with-the-azure-cloud-shell) と接続することもできます。
>


## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報


**オペレーティング システム**

64 ビット バージョンの Windows を使用する必要があります。Windows PowerShell 用の Microsoft Azure Active Directory モジュールの 32 ビット バージョンのサポートは 2014 年に終了しました。

次の Windows のバージョンを使用できます。
    
  - Windows 10、Windows 8.1、Windows 8、または Windows 7 Service Pack 1 (SP1) 
    
  - Windows Server 2019、Windows Server 2016、Windows Server 2012 R2、Windows Server 2012、または Windows Server 2008 R2 SP1

>[!Note]
>Windows 8.1、Windows 8、Windows 7 Service Pack 1 (SP1)、Windows Server 2012 R2、Windows Server 2012、および Windows Server 2008 R2 SP1 の場合は、[Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616) をダウンロードしてインストールします。

**PowerShell**

- Graph 用 Azure Active Directory PowerShell モジュールでは、PowerShell バージョン 5.1 以降を使用する必要があります。

- Windows PowerShell 用 Microsoft Azure Active Directory モジュールでは、PowerShell バージョン 5.1 から PowerShell バージョン 6 までを使用する必要があります。PowerShell バージョン 7 は使用できません。
       
>[!Note]
>これらの手順は、Microsoft 365 の管理者の役割を持つユーザーを対象としています。 詳細については、[「管理者の役割について」](../admin/add-users/about-admin-roles.md) を参照してください。


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>Graph 用 Azure Active Directory PowerShell モジュールに接続する

Graph 用 Azure Active Directory PowerShell モジュールのコマンドには、コマンドレット名に *AzureAD* が含まれます。 [Graph 用 Azure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2) モジュールか [Azure PowerShell](/powershell/azure/install-az-ps) をインストールできます。

Graph 用 Azure Active Directory PowerShell モジュールにおいて新しいコマンドレットを必要とするプロシージャについては、以下の手順に従い、モジュールをインストールし、Microsoft 365 サブスクリプションに接続します。

> [!Note]
> Windows のさまざまなバージョンに対するサポート情報については、「[Graph 用 Azure Active Directory PowerShell モジュール](/powershell/azure/active-directory/install-adv2)」を参照してください。

### <a name="step-1-install-the-required-software"></a>手順 1: 必要なソフトウェアをインストールする

これらの手順は、お使いのコンピューターで一度だけ行う必要があります。 ただし、定期的にソフトウェアを更新する必要があります。
  
1. 管理者特権で Windows PowerShell コマンド プロンプト ウィンドウを開きます (Windows PowerShell を管理者として実行)。
    
2. 次のコマンドを実行します。
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  既定では、PowerShell ギャラリー (PSGallery) は、**PowerShellGet** 用の信頼されたリポジトリとして構成されません。 初めて PSGallery を使用する場合は、次のメッセージが表示されます。

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

インストールを続行するには [**はい**] または [**すべてにはい**] をクリックします。


### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>手順 2: Microsoft 365 サブスクリプション用の Azure AD に接続する

アカウント名とパスワードまたは多要素認証 (MFA) を使用して Microsoft 365 サブスクリプション用の Azure Active Directory (Azure AD) に接続するには、Windows PowerShell コマンド プロンプトから次のいずれかのコマンドを実行します (昇格する必要はありません)。

| Office 365 のクラウド | コマンド |
|:-------|:-----|
| Office 365 ワールドワイド (+GCC) | `Connect-AzureAD` |
| 21 Vianet が運営する Office 365 | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 Germany | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| Office 365 U.S. Government DoD と Office 365 U.S. Government GCC High | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

[**アカウントにサインイン**] ダイアログ ボックスで、Microsoft 365 の職場または学校のアカウントのユーザー名とパスワードを入力し、[**OK**] を選択します。

多要素認証を使用している場合は、手順に従って確認コードなどの追加認証情報を入力します。

接続後は、[Graph 用 Azure Active Directory PowerShell モジュール](/powershell/module/azuread)のコマンドレットを使用できます。

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell 用 Microsoft Azure Active Directory モジュールとの接続

>[!Note]
>Windows PowerShell 用 Microsoft Azure Active Directory モジュールには、コマンドレット名に *Msol* が含まれています。

PowerShell バージョン 7 以降は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。 PowerShell バージョン 7 以降では、Graph 用 Azure Active Directory PowerShell モジュールか Azure PowerShell を使用する必要があります。

PowerShell Core は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。 これらのコマンドレットは、Windows PowerShell から実行します。
    
### <a name="step-1-install-the-required-software"></a>手順 1: 必要なソフトウェアをインストールする

これらの手順は、お使いのコンピューターで一度だけ行う必要があります。 ただし、定期的にソフトウェアを更新する必要があります。
  
1.  Windows 10を実行中でない場合は、Microsoft Online Services サインイン アシスタントの 64 ビット版をインストールします: [IT プロフェッショナル用 Microsoft Online Services サインイン アシスタント RTW](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)。
    
2. 以下の手順に従って、Windows PowerShell の Microsoft Azure Active Directory モジュールをインストールします。
    
   1. 管理者特権で Windows PowerShell コマンド プロンプトを開きます (Windows PowerShell を管理者として実行)。
   1.  **Install-Module MSOnline** コマンドを実行します。
   1. NuGet プロバイダーをインストールするようにメッセージが表示されたら、「**Y**」と入力し、Enter キーを押します。
   1. PSGallery からモジュールをインストールするようにメッセージが表示されたら、「**Y**」と入力し、Enter キーを押します。
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>手順 2: Microsoft 365 サブスクリプション用の Azure AD に接続する

アカウント名とパスワードまたは多要素認証 (MFA) を使用して Microsoft 365 サブスクリプション用の Azure AD に接続するには、Windows PowerShell コマンド プロンプトから次のいずれかのコマンドを実行します (昇格する必要はありません)。

| Office 365 のクラウド | コマンド |
|:-------|:-----|
| Office 365 ワールドワイド (+GCC) | `Connect-MsolService` |
| 21 Vianet が運営する Office 365 | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 Germany | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| Office 365 U.S. Government DoD と Office 365 U.S. Government GCC High | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

[**アカウントにサインイン**] ダイアログ ボックスで、Microsoft 365 の職場または学校のアカウントのユーザー名とパスワードを入力し、[**OK**] を選択します。

多要素認証を使用している場合は、手順に従って確認コードなどの追加認証情報を入力します。

### <a name="how-do-you-know-it-worked"></a>正常な動作を確認する方法

エラー メッセージが表示されなければ、正常に接続されています。 簡単に確かめるには、**Get-MsolUser** などの Microsoft 365 コマンドレットを実行して結果を確認します。
  
エラー メッセージが表示される場合は、次の点を確認します。
  
- **よくある原因は、正しくないパスワードです**。 [手順 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) をもう一度実行し、その際入力するユーザー名とパスワードには特に注意します。
    
- **Windows PowerShell 用 Microsoft Azure Active Directory モジュールには、Microsoft .NET Framework 3.5 が必要です。お使いのコンピューターで* x* が有効になっています**。コンピューターにより新しいバージョンがインストールされている可能性があります (4 または 4.5.* x* など)。 ただし、以前の .NET Framework のバージョンとの下位互換性を有効または無効にすることができます。 詳細については、次の記事を参照してください。
    
  - Windows Server 2012 または Windows Server 2012 R2 の場合は、「[役割と機能の追加ウィザードを使用して .NET Framework 3.5 を有効にする](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10))」を参照してください。
    
  - Windows 7 または Windows Server 2008 R2 の場合は、「[Windows PowerShell 用 Azure Active Directory モジュールを開くことができない](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell)」を参照してください。

  - Windows 10、Windows 8.1、および Windows 8 の場合は、「[Windows 8、Windows 8.1、および Windows 10 への .NET Framework 3.5 のインストール](/dotnet/framework/install/dotnet-35-windows-10)」を参照してください。

  
- **お使いの Windows PowerShell 用 Microsoft Azure Active Directory モジュールのバージョンは期限切れの可能性があります。** Microsoft 365用または PowerShell または Windows PowerShell 用 Microsoft Azure Active Directory モジュールで、次のコマンドを実行して確認します。
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    返されたバージョン番号が *1.0.8070.2* より小さい場合は、Windows PowerShell 用 Microsoft Azure Active Directory モジュールをアンインストールして、上の [手順 1](#step-1-install-the-required-software) からインストールします。

- **接続エラーが発生した場合** は、["Connect-MsolService: 例外がスローされました" というエラー](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception)に関するトピックをご覧ください。
    
- **「Get-Item: パスが見つかりません」エラーが表示された場合** は、次のコマンドを使用します。


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="connect-with-the-azure-cloud-shell"></a>Azure Cloud Shell との接続

Microsoft 365 管理センターで Azure Cloud Shell に接続して使用するには、タスク バーの右上にある PowerShell ウィンドウ アイコンを選択します。 **[Azure Cloud Shell へようこそ]** ウィンドウで、**PowerShell** を選択します。

Microsoft 365 サブスクリプションに関連付けられた、組織のアクティブな Azure サブスクリプションが必要です。 まだお持ちでない場合は、作成できます。 Azure サブスクリプションを取得すると、PowerShell ウィンドウが開き、PowerShell のコマンドやスクリプトを実行することができます。

詳細については、「[Azure Cloud Shell](/azure/cloud-shell/overview)」を参照してください。

## <a name="see-also"></a>関連項目

- [PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
- [単一の Windows PowerShell ウィンドウですべての Microsoft 365 サービスに接続する](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
