---
title: Basic Mobility および Security 管理対象デバイスの詳細を取得する
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
description: 組織Windows PowerShellの Basic Mobility および Security デバイスの詳細を取得するには、次の情報を使用します。
ms.openlocfilehash: 92fcd6f39ffff97d7a4ecd2a69626ece54b481b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904254"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>Basic Mobility および Security 管理対象デバイスの詳細を取得する

この記事では、基本モビリティとセキュリティWindows PowerShell設定した組織内のデバイスに関する詳細を取得する方法について説明します。

利用可能なデバイスの詳細の内訳を次に示します。

|**詳細**|**PowerShell で探す情報**|
|:----------------|:------------------------------------------------------------------------------|
|デバイスは Basic Mobility and Security に登録されています。 詳細については、「Basic [Mobility and Security を使用してモバイル デバイスを登録する」を参照してください。](enroll-your-mobile-device.md)| *isManaged* パラメーターの値   は次の値です。<br/>**True**= デバイスが登録されています。<br/>**False**= デバイスは登録されません。 |
|デバイスは、デバイスのセキュリティ ポリシーに準拠しています。 詳細については、「デバイス セキュリティ [ポリシーの作成」を参照してください。](create-device-security-policies.md)| *isCompliant パラメーターの値は次*   の値です。<br/>**True**  = デバイスはポリシーに準拠しています。<br/>**False**  = デバイスがポリシーに準拠していません。|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本的なモビリティとセキュリティの PowerShell パラメーター":::

>[!NOTE]
>この記事のコマンドとスクリプトは、Microsoft Intune によって管理されるデバイスに関する詳細 [も返します](https://www.microsoft.com/cloud-platform/microsoft-intune)。

## <a name="before-you-begin"></a>はじめに

この記事で説明するコマンドとスクリプトを実行するために設定する必要があるものがあります。

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>手順 1: Azure Active Directory モジュールをダウンロードしてインストールします。Windows PowerShell

これらの手順の詳細については [、「Connect to Microsoft 365 with PowerShell」を参照してください](/office365/enterprise/powershell/connect-to-office-365-powershell)。

1. [IT 担当者 [向Microsoft Online Services Sign-In RTWl]](https://www.microsoft.com/download/details.aspx?id=41950)に移動し、[サインイン アシスタントのダウンロードMicrosoft Online Services    **を選択します**。

2. 以下の手順に従って、Windows PowerShell の Microsoft Azure Active Directory モジュールをインストールします。

    1. 管理者レベルの PowerShell コマンド プロンプトを開きます。  

    2. Install-Module MSOnline コマンドを実行します。

    3. NuGet プロバイダーをインストールするようにメッセージが表示されたら、「Y」と入力し、ENTER を押します。

    4. PSGallery からモジュールをインストールするようにメッセージが表示されたら、「Y」と入力し、Enter を押します。

    5. インストール後、PowerShell コマンド ウィンドウを閉じます。

### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>手順 2: Microsoft 365 サブスクリプションに接続する

1. Windows Azure Active Directory モジュールで、Windows PowerShellコマンドを実行します。  

    $UserCredential = Get-Credential

2. [資格情報Windows PowerShell] ダイアログ ボックスで、Microsoft 365 グローバル管理者アカウントのユーザー名とパスワードを入力し **、[OK] を選択します**。

3. 次のコマンドを実行します。

    Connect-MsolService -Credential $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>手順 3: PowerShell スクリプトを実行することを確認する

>[!NOTE]
>PowerShell スクリプトの実行を既に設定している場合は、この手順を省略できます。

このスクリプトをGet-MsolUserDeviceComplianceStatus.ps1するには、PowerShell スクリプトの実行を有効にする必要があります。

1. Windows デスクトップで 、[スタート] を **選択し**、[スタート] と入力Windows PowerShell。 [管理者] をWindows PowerShellし、[管理者として **実行] を選択します**。

2. 次のコマンドを実行します。

    Set-ExecutionPolicy RemoteSigned

3. プロンプトが表示されたら、「Y」と入力し、Enter キーを押します。

**組織のすべてのGet-MsolDeviceの詳細を表示するには、このコマンドレットを実行します。**

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。  

2. 次のコマンドを実行します。

    Get-MsolDevice -All -ReturnRegisteredOwners |Where-Object {$_.RegisteredOwners.Count -gt 0}

その他の例については  [、「Get-MsolDevice」を参照してください](https://go.microsoft.com/fwlink/?linkid=2157939)。

## <a name="run-a-script-to-get-device-details"></a>スクリプトを実行してデバイスの詳細を取得する

まず、スクリプトをコンピューターに保存します。

1. 次のテキストをコピーしてメモ帳に貼り付けます。  

2.  param (

3.  [PSObject[]]$users = @(),

4.  [Switch]$export,

5.  [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",

6.  [String]$exportPath = [環境]::GetFolderPath("Desktop")

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
    

25.  関数 createResultObject
    

26.  {
    

28.  [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
    

30.  戻り$resultObject
    

31.  }
    

33.  If ($users.Count -eq 0)
    

34.  {
    

35.  $users = Get-MsolUser
    

36.  }
    

38.  [PSObject[]] $result = foreach ($u $users)
    

39.  {
    

41.  [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
    

42.  foreach ($dの$devices)
    

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
    

71.  ファイル拡張子 .ps1 を使用Windows PowerShellスクリプト ファイルとして保存します。たとえば、Get-MsolUserDeviceComplianceStatus.ps1。   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>スクリプトを実行して、1 つのユーザー アカウントのデバイス情報を取得する

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。
    
2. スクリプトを保存したフォルダーに移動します。 たとえば、C:\PS-Scripts に保存した場合は、次のコマンドを実行します。
    
    cd C:\PS-Scripts

3. 次のコマンドを実行して、デバイスの詳細を取得するユーザーを特定します。 この例では、データの詳細を取得 bar@example.com。
    
    $u = Get-MsolUser -UserPrincipalName bar@example.com

4. スクリプトを開始するには、次のコマンドを実行します。

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

この情報は、CSV ファイルとして Windows デスクトップにエクスポートされます。 追加のパラメーターを使用して、CSV のファイル名とパスを指定できます。

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>スクリプトを実行して、ユーザーのグループのデバイス情報を取得する

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。
    
2. スクリプトを保存したフォルダーに移動します。 たとえば、C:\PS-Scripts に保存した場合は、次のコマンドを実行します。   

    cd C:\PS-Scripts

3. 次のコマンドを実行して、デバイスの詳細を取得するグループを特定します。 この例では、FinanceStaff グループのユーザーの詳細を取得します。 

    $u = Get-MsolGroupMember -SearchString "FinanceStaff" |% { Get-MsolUser -ObjectId $_.ObjectId }

4. スクリプトを開始するには、次のコマンドを実行します。

    .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export

この情報は、CSV ファイルとして Windows デスクトップにエクスポートされます。 追加のパラメーターを使用して、CSV のファイル名とパスを指定できます。

## <a name="related-topics"></a>関連項目

[Microsoft Connect が廃止されました](/collaborate/connect-redirect)

[基本的なモビリティとセキュリティの概要](overview.md)

[Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=2157939)