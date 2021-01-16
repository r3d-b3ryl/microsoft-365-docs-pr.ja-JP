---
title: Basic Mobility and Security 管理対象デバイスの詳細を取得する
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
description: このWindows PowerShell使用して、組織内の Basic Mobility and Security デバイスに関する詳細を取得します。
ms.openlocfilehash: 7c6a0365dfd573377c3675bbcee8ee8280e33816
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876890"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Basic Mobility and Security 管理対象デバイスの詳細を取得する

この記事では、Windows PowerShell を使用して、Basic Mobility and Security に設定した組織内のデバイスに関する詳細を取得する方法について説明します。

利用可能なデバイスの詳細の内訳を次に示します。

|**詳細**|**PowerShell で探す情報**|
|:----------------|:------------------------------------------------------------------------------|
|デバイスが Basic Mobility and Security に登録されている。 詳細については [、「Basic Mobility and Security を使用してモバイル デバイスを登録する」を参照してください。](enroll-your-mobile-device.md)| *isManaged* パラメーターの値   は次の値です。<br/>**True**= デバイスが登録されています。<br/>**False**= デバイスが登録されていない。 |
|デバイスは、デバイスのセキュリティ ポリシーに準拠しています。 詳しくは、「デバイス セキュリティ [ポリシーの作成」をご覧ください。](create-device-security-policies.md)| *isCompliant パラメーターの値は*   次の値です。<br/>**True**  = デバイスはポリシーに準拠しています。<br/>**False**  = デバイスはポリシーに準拠していません。|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本的なモビリティとセキュリティの PowerShell パラメーター":::

>[!NOTE]
>この記事のコマンドとスクリプトは [、Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)で管理されているデバイスに関する詳細も返します。

## <a name="before-you-begin"></a>はじめに

この記事で説明するコマンドとスクリプトを実行するには、いくつかの設定が必要です。

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>手順 1: Azure Active Directory モジュールをダウンロードしてインストールWindows PowerShell

これらの手順について詳しくは、「PowerShell を使用して [Microsoft 365 に接続する」をご覧ください](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)。

1. IT プロフェッショナル [用 Microsoft Online Services Sign-In RTWl に移動し](https://www.microsoft.com/download/details.aspx?id=41950)、サインイン アシスタントの [ダウンロード    **Microsoft Online Services選択します**。   

2. 以下の手順に従って、Windows PowerShell の Microsoft Azure Active Directory モジュールをインストールします。

    1. 管理者レベルの PowerShell コマンド プロンプトを開きます。  

    2. Install-Module MSOnline コマンドを実行します。

    3. NuGet プロバイダーをインストールするようにメッセージが表示されたら、「Y」と入力し、ENTER を押します。

    4. PSGallery からモジュールをインストールするようにメッセージが表示されたら、「Y」と入力し、Enter を押します。

    5. インストール後、PowerShell コマンド ウィンドウを閉じます。

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>手順 2: Microsoft 365 サブスクリプションに接続する

1. Windows Azure Active Directory モジュールでWindows PowerShellコマンドを実行します。  

    $UserCredential = Get-Credential

2. [資格情報Windows PowerShell] ダイアログ ボックスで、Microsoft 365 グローバル管理者アカウントのユーザー名とパスワードを入力し **、[OK]** を選択します。

3. 次のコマンドを実行します。

    Connect-MsolService -Credential $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>手順 3: PowerShell スクリプトを実行できる点を確認する

>[!NOTE]
>PowerShell スクリプトを実行する設定が既にされている場合は、この手順を省略できます。

このスクリプトをGet-MsolUserDeviceComplianceStatus.ps1、PowerShell スクリプトの実行を有効にする必要があります。

1. Windows デスクトップから [スタート] を **選択し**、次のコマンドをWindows PowerShell。 管理者として実行Windows PowerShellを右クリックし、[管理者として **実行] を選択します**。

2. 次のコマンドを実行します。

    Set-ExecutionPolicy RemoteSigned

3. メッセージが表示されたら、「Y」と入力し、Enter キーを押します。

**Get-MsolDevice コマンドレットを実行して、組織内のすべてのデバイスの詳細を表示する**

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。  

2. 次のコマンドを実行します。

    Get-MsolDevice -All -ReturnRegisteredOwners |Where-Object {$_.RegisteredOwners.Count -gt 0}

その他の例については  [、「Get-MsolDevice」を参照してください](https://go.microsoft.com/fwlink/?linkid=841721)。

## <a name="run-a-script-to-get-device-details"></a>スクリプトを実行してデバイスの詳細を取得する

まず、スクリプトをコンピューターに保存します。

1. 次のテキストをコピーしてメモ帳に貼り付けます。  

2.  param (

3.  [PSObject[]]$users = @(),

4.  [スイッチ]$export、

5.  [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",

6.  [String]$exportPath = [Environment]::GetFolderPath("Desktop")

7.  )

9.  [System.Collections.IDictionary]$script:schema = @{

11.  DeviceId = ''

12.  DeviceOSType = ''

13.  DeviceOSVersion = ''

14.  DeviceTrustLevel = ''

15.  DisplayName = ''

16.  IsCompliant = ''

17.  IsManaged = ''

18.  ApproximateLastLogonTimestamp = ''

19.  DeviceObjectId = ''

20.  RegisteredOwnerUpn = ''

21.  RegisteredOwnerObjectId = ''
    

22.  RegisteredOwnerDisplayName = ''
    

23.  }
    

25.  function createResultObject
    

26.  {
    

28.  [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
    

30.  return $resultObject
    

31.  }
    

33.  If ($users.Count -eq 0)
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject[]]$result = foreach ($u in $users)
    

39.  {
    

41.  [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
    

42.  foreach ($d in $devices)
    

43.  {
    

44.  [PSObject]$deviceResult = createResultObject
    

45.  $deviceResult.DeviceId = $d.DeviceId
    

46.  $deviceResult.DeviceOSType = $d.DeviceOSType
    

47.  $deviceResult.DeviceOSVersion = $d.DeviceOSVersion
    

48.  $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
    

49.  $deviceResult.DisplayName = $d.DisplayName
    

50.  $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
    

51.  $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
    

52.  $deviceResult.DeviceObjectId = $d.ObjectId
    

53.  $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
    

54.  $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
    

55.  $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
    

56.  $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  If ($export)
    

64.  {
    

65.  $result |Export-Csv -path ($exportPath + " \" + $exportFileName) -NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  ファイル拡張子 .ps1 をWindows PowerShellスクリプト ファイルとして保存します。たとえば、Get-MsolUserDeviceComplianceStatus.ps1。   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>スクリプトを実行して単一のユーザー アカウントのデバイス情報を取得する

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。
    
2. スクリプトを保存したフォルダーに移動します。 たとえば、C:\PS-Scripts に保存した場合は、次のコマンドを実行します。
    
    cd C:\PS-Scripts

3. 次のコマンドを実行して、デバイスの詳細を取得するユーザーを特定します。 この例では、データの詳細を取得bar@example.com。
    
    $u = Get-MsolUser -UserPrincipalName bar@example.com

4. スクリプトを開始するには、次のコマンドを実行します。

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

この情報は、CSV ファイルとして Windows デスクトップにエクスポートされます。 CSV のファイル名とパスを指定するには、追加のパラメーターを使用できます。

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>スクリプトを実行してユーザーのグループのデバイス情報を取得する

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。
    
2. スクリプトを保存したフォルダーに移動します。 たとえば、C:\PS-Scripts に保存した場合は、次のコマンドを実行します。   

    cd C:\PS-Scripts

3. 次のコマンドを実行して、デバイスの詳細を取得するグループを特定します。 この例では、FinanceStaff グループのユーザーの詳細を取得します。 

    $u = Get-MsolGroupMember -SearchString "FinanceStaff" |% { Get-MsolUser -ObjectId $_.ObjectId }

4. スクリプトを開始するには、次のコマンドを実行します。   

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

この情報は、CSV ファイルとして Windows デスクトップにエクスポートされます。 CSV のファイル名とパスを指定するには、追加のパラメーターを使用できます。

## <a name="related-topics"></a>関連項目

[Microsoft Connect は廃止されました](https://docs.microsoft.com/collaborate/connect-redirect)

[基本的なモビリティとセキュリティの概要](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)