---
title: 基本的なモビリティとセキュリティの管理対象デバイスに関する詳細を取得する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Windows PowerShell を使用して、組織内の基本的なモビリティおよびセキュリティ デバイスの詳細を取得します。
ms.openlocfilehash: 231eeb87d3f72ca4107c0ee6bef5bd60c713bb3f
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58564467"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>基本的なモビリティとセキュリティの管理対象デバイスに関する詳細を取得する

この記事では、Windows PowerShell を使用して、基本的なモビリティとセキュリティ用に設定した組織内のデバイスの詳細を取得する方法について説明します。

利用可能なデバイスの詳細の内訳は次のとおりです。

|**詳細**|**PowerShell で検索する内容**|
|:----------------|:------------------------------------------------------------------------------|
|デバイスは基本的なモビリティとセキュリティに登録されています。 詳細については、「[基本的なモビリティとセキュリティを使用してモバイル デバイスを登録する](enroll-your-mobile-device.md)」を参照してください。| *isManaged*  パラメーターの値: <br/>**True** = デバイスは登録されています。<br/>**False** = デバイスは登録されていません。 |
|デバイスはデバイス セキュリティ ポリシーに準拠しているかどうか 詳細については、「[デバイス セキュリティ ポリシーの作成](create-device-security-policies.md)」を参照してください。| *isCompliant*  パラメーターの値: <br/>**True**  = デバイスはポリシーに準拠しています。<br/>**False**  = デバイスはポリシーに準拠していません。|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本的なモビリティとセキュリティの PowerShell パラメーター。":::

> [!NOTE]
> この記事のコマンドとスクリプトでは、 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune) で管理されるデバイスに関する詳細情報も返されます。

## <a name="before-you-begin"></a>はじめに

この記事で説明されているコマンドとスクリプトを実行するために、少し設定を行う必要あります。

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>手順 1: Windows PowerShell 用 Microsoft Azure Active Directory モジュールをダウンロードして、インストールする

これらの手順の詳細については、「 [PowerShell を使用して Microsoft 365 に接続する](/office365/enterprise/powershell/connect-to-office-365-powershell)」を参照してください。

1.  [IT プロフェッショナル向け Microsoft Online Services サインイン アシスタント RTWl](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi)  に移動し、 **Microsoft Online Services サインイン アシスタント用にダウンロード** を選択します。

2. 以下の手順に従って、Windows PowerShell の Microsoft Azure Active Directory モジュールをインストールします。

    1. 管理者レベルの PowerShell コマンド プロンプトを開きます。

    2. `Install-Module MSOnline` コマンドを実行します。

    3. NuGet プロバイダーをインストールするようにメッセージが表示されたら、「Y」と入力し、ENTER を押します。

    4. PSGallery からモジュールをインストールするようにメッセージが表示されたら、「Y」と入力し、Enter を押します。

    5. インストール後、PowerShell コマンド ウィンドウを閉じます。

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>手順 2: Microsoft 365 サブスクリプションに接続する

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールで、次のコマンドを実行します。

   ```powershell
   $UserCredential = Get-Credential
   ```

2. [Windows PowerShell 資格情報の要求] ダイアログ ボックスで、Microsoft 365 グローバル管理者アカウントのユーザー名とパスワードを入力してから、**[OK]** を選択します。

3. 次のコマンドを実行します。

   ```powershell
   Connect-MsolService -Credential $UserCredential
   ```

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>手順 3: PowerShell スクリプトを実行できることを確認します。

> [!NOTE]
> 既に PowerShell スクリプトを実行できるように設定している場合は、この手順をスキップできます。

Get-MsolUserDeviceComplianceStatus.ps1 スクリプトを実行するには、PowerShell スクリプトの実行を有効にする必要があります。

1. Windows デスクトップから [ **スタート**] を選択し、「Windows PowerShell」と入力します。 [Windows PowerShell] を右クリックし、 **[管理者として実行]** を選択します。

2. 次のコマンドを実行します。

   ```powershell
   Set-ExecutionPolicy  RemoteSigned
   ```

3. メッセージが表示されたら、「Y」を入力し、Enter キーを押します。

#### <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>Get-MsolDevice コマンドレットを実行して組織内のすべてのデバイスの詳細情報を表示する

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。

2. 次のコマンドを実行します。

   ```powershell
   Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
   ```

その他の例については、「 [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)」を参照してください。

## <a name="run-a-script-to-get-device-details"></a>スクリプトを実行してデバイスの詳細情報を取得する

最初に、コンピューターにスクリプトを保存します。

1. 次のテキストをメモ帳にコピーして貼り付けます。

   ```powershell
   param (
   [PSObject[]]$users = @(),
   [Switch]$export,
   [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
   [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
   [System.Collections.IDictionary]$script:schema = @{
   DeviceId = ''
   DeviceOSType = ''
   DeviceOSVersion = ''
   DeviceTrustLevel = ''
   DisplayName = ''
   IsCompliant = ''
   IsManaged = ''
   ApproximateLastLogonTimestamp = ''
   DeviceObjectId = ''
   RegisteredOwnerUpn = ''
   RegisteredOwnerObjectId = ''
   RegisteredOwnerDisplayName = ''
   }
   function createResultObject
   {
   [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
   return $resultObject
   }
   If ($users.Count -eq 0)
   {
   $users = Get-MsolUser
   }
   [PSObject[]]$result = foreach ($u in $users)
   {
   [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
   foreach ($d in $devices)
   {
   [PSObject]$deviceResult = createResultObject
   $deviceResult.DeviceId = $d.DeviceId
   $deviceResult.DeviceOSType = $d.DeviceOSType
   $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
   $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
   $deviceResult.DisplayName = $d.DisplayName
   $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
   $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
   $deviceResult.DeviceObjectId = $d.ObjectId
   $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
   $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
   $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
   $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
   $deviceResult
   }
   }
   If ($export)
   {
   $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
   }
   Else
   {
   $result
   }
   ```

2. ファイル拡張子 .ps1 を使用して、WindowsPowerShell スクリプト ファイルとして保存します。 たとえば、Get-MsolUserDeviceComplianceStatus.ps1 です。

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>スクリプトを実行して、単一のユーザー アカウントのデバイス情報を取得する

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。

2. スクリプトを保存したフォルダーに移動します。 たとえば、C:\PS-Scripts に保存した場合は、次のコマンドを実行します。

   ```powershell
   cd C:\PS-Scripts
   ```

3. 次のコマンドを実行して、デバイスの詳細情報を取得するユーザーを特定します。 この例では、bar@example.com の詳細情報を取得します。

   ```powershell
   $u = Get-MsolUser -UserPrincipalName bar@example.com
   ```

4. 次のコマンドを実行して、スクリプトを開始します。

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

この情報は、Windows デスクトップに CSV ファイルとしてエクスポートされます。 追加のパラメーターを使用して、ファイル名と CSV のパスを指定することができます。

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>スクリプトを実行して、ユーザーのグループのデバイス情報を取得する

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。

2. スクリプトを保存したフォルダーに移動します。 たとえば、C:\PS-Scripts に保存した場合は、次のコマンドを実行します。

   ```powershell
   cd C:\PS-Scripts
   ```

3. 次のコマンドを実行して、デバイスの詳細情報を取得するグループを特定します。 この例では、FinanceStaff グループのユーザーの詳細情報を取得します。

   ```powershell
   $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
   ```

4. 次のコマンドを実行して、スクリプトを開始します。

   ```powershell
   .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
   ```

この情報は、Windows デスクトップに CSV ファイルとしてエクスポートされます。 追加のパラメーターを使用して、ファイル名と CSV のパスを指定することができます。

## <a name="related-topics"></a>関連トピック

[Microsoft Connect は廃止されました](/collaborate/connect-redirect)

[基本的なモビリティとセキュリティの概要](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)
