---
title: 基本的なモビリティおよびセキュリティ管理デバイスの詳細を取得する
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
description: Windows PowerShell を使用して、組織内の基本的なモビリティおよびセキュリティデバイスに関する詳細を取得します。
ms.openlocfilehash: d34263ee215c568834034f2735bb69d9cef9ac6d
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430235"
---
# <a name="get-details-about-basic-mobility-and-security-managed-devices"></a>基本的なモビリティおよびセキュリティ管理デバイスの詳細を取得する

この記事では、Windows PowerShell を使用して、基本的なモビリティとセキュリティのためにセットアップした組織内のデバイスに関する詳細を取得する方法について説明します。

使用可能なデバイスの詳細については、次の表を参照してください。

|**詳細**|**PowerShell での検索対象**|
|:----------------|:------------------------------------------------------------------------------|
|デバイスは基本的なモビリティとセキュリティに登録されています。 詳細については、「 [Basic Mobility And Security を使用したモバイルデバイスの登録](enroll-your-mobile-device.md)」を参照してください。| *Ismanaged*   パラメーターの値は次のとおりです。<br/>**True**= デバイスは登録されています。<br/>**False**= デバイスは登録されていません。 |
|デバイスは、デバイスのセキュリティポリシーに準拠しています。 詳細については、「[デバイスセキュリティポリシーの作成](create-device-security-policies.md)」を参照してください。| *Iscompliant*   パラメーターの値は次のとおりです。<br/>**True**  = デバイスはポリシーに準拠しています。<br/>**False**  = デバイスはポリシーに準拠していません。|

:::image type="content" source="../../media/basic-mobility-security/bms-7-powershell-parameters.png" alt-text="基本的な Mobility および Security PowerShell パラメーター":::

>[!NOTE]
>この記事のコマンドとスクリプトは、 [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune)によって管理されるすべてのデバイスに関する詳細も返します。

## <a name="before-you-begin"></a>はじめに

この記事で説明されているコマンドとスクリプトを実行するためにセットアップする必要があるいくつかの事柄があります。

### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>手順 1: Windows PowerShell 用 Azure Active Directory モジュールをダウンロードしてインストールする

これらの手順の詳細については、「 [Connect To Microsoft 365 With PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)」を参照してください。

1.  [IT プロフェッショナル向け Microsoft Online Services サインインアシスタント](https://www.microsoft.com/download/details.aspx?id=41950)に移動   し、  **Microsoft online Services サインインアシスタントのダウンロード**を選択します。   

2. 以下の手順に従って、Windows PowerShell の Microsoft Azure Active Directory モジュールをインストールします。   

    1. 管理者レベルの PowerShell コマンド プロンプトを開きます。  

    2. Install-Module MSOnline コマンドを実行します。
    
    3. NuGet プロバイダーをインストールするようにメッセージが表示されたら、「Y」と入力し、ENTER を押します。   

    4. PSGallery からモジュールをインストールするようにメッセージが表示されたら、「Y」と入力し、Enter を押します。   

    5. インストール後、PowerShell コマンド ウィンドウを閉じます。
    
### <a name="step-2-connect-to-your-microsoft-365-subscription"></a>手順 2: Microsoft 365 サブスクリプションに接続する

1. Windows PowerShell 用 Windows Azure Active Directory モジュールで、次のコマンドを実行します。  

    $UserCredential = Get-Credential

2. [Windows PowerShell 資格情報の要求] ダイアログボックスで、Microsoft 365 グローバル管理者アカウントのユーザー名とパスワードを入力し、[ **OK]** を選択します。
    
3. 次のコマンドを実行します。
    
    Connect-msolservice-Credential $UserCredential

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>手順 3: PowerShell スクリプトを実行できることを確認する

>[!NOTE]
>PowerShell スクリプトを実行するように設定されている場合は、この手順を省略できます。

Get-MsolUserDeviceComplianceStatus.ps1 スクリプトを実行するには、PowerShell スクリプトの実行を有効にする必要があります。

1. Windows デスクトップから [ **スタート**] を選択し、「windows PowerShell」と入力します。 [Windows PowerShell] を右クリックし、[ **管理者として実行**] を選択します。

2. 次のコマンドを実行します。
    
    ExecutionPolicy RemoteSigned

3. プロンプトが表示されたら、「Y」と入力し、Enter キーを押します。
    
**MsolDevice コマンドレットを実行して、組織内のすべてのデバイスの詳細を表示します。**

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。  

2. 次のコマンドを実行します。
    
    MsolDevice-ReturnRegisteredOwners |ここで、オブジェクト {$ _ を指定します。RegisteredOwners-gt 0}

詳細な例については、「  [MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)」を参照してください。

## <a name="run-a-script-to-get-device-details"></a>スクリプトを実行してデバイスの詳細を取得する

最初に、スクリプトをコンピューターに保存します。

1. 次のテキストをコピーしてメモ帳に貼り付けます。  

2.  param
    

3.  [PSObject []] $users = @ ()、
    

4.  [スイッチ] $export、
    

5.  [String] $exportFileName = "UserDeviceComplianceStatus_" + (取得日-日付形式 "yyMMdd_HHMMss") + ".csv"、
    

6.  [String] $exportPath = [Environment]:: GetFolderPath ("Desktop")
    

7.  )
    

9.  [System.web] $script: スキーマ = @ {
    

11.  DeviceId = ' '
    

12.  DeviceOSType = ' '
    

13.  DeviceOSVersion = ' '
    

14.  DeviceTrustLevel = ' '
    

15.  DisplayName = ' '
    

16.  IsCompliant = ' '
    

17.  IsManaged = ' '
    

18.  ApproximateLastLogonTimestamp = ' '
    

19.  DeviceObjectId = ' '
    

20.  RegisteredOwnerUpn = ' '
    

21.  RegisteredOwnerObjectId = ' '
    

22.  RegisteredOwnerDisplayName = ' '
    

23.  }
    

25.  関数 createResultObject
    

26.  {
    

28.  [PSObject] $resultObject = New-Object-TypeName PSObject-Property $script: schema
    

30.  $resultObject を返します。
    

31.  }
    

33.  If ($users。Count-eq 0)
    

34.  {
    

35.  $users = Get-msoluser
    

36.  }
    

38.  [PSObject []] $result = foreach ($u $users)
    

39.  {
    

41.  [PSObject] $devices = msoldevice-RegisteredOwnerUpn $u
    

42.  foreach ($d $devices)
    

43.  {
    

44.  [PSObject] $deviceResult = createResultObject
    

45.  $deviceResult: DeviceId = $d
    

46.  $deviceResult DeviceOSType = $d DeviceOSType
    

47.  $deviceResult DeviceOSVersion = $d DeviceOSVersion
    

48.  DeviceTrustLevel = $d $deviceResult。 DeviceTrustLevel
    

49.  $deviceResult DisplayName = $d DisplayName
    

50.  $deviceResult IsCompliant = $d GraphDeviceObject 準拠
    

51.  $deviceResult IsManaged = $d GraphDeviceObject。
    

52.  $deviceResult DeviceObjectId = $d ObjectId
    

53.  $deviceResult RegisteredOwnerUpn = $u
    

54.  RegisteredOwnerObjectId = $u $deviceResult
    

55.  $deviceResult RegisteredOwnerDisplayName = $u
    

56.  ApproximateLastLogonTimestamp = $d $deviceResult。 ApproximateLastLogonTimestamp
    

58.  $deviceResult
    

59.  }
    

61.  }
    

63.  If ($export)
    

64.  {
    

65.  $result |エクスポート-Csv-path ($exportPath + " \" + $exportFileName)-NoTypeInformation
    

66.  }
    

67.  Else
    

68.  {
    

69.  $result
    

70.  }
    

71.  ファイル拡張子 ps1 を使用して、Windows PowerShell スクリプトファイルとして保存します。 ps1;たとえば、Get-MsolUserDeviceComplianceStatus.ps1 のようにします。   

## <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>スクリプトを実行して1つのユーザーアカウントのデバイス情報を取得する

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。
    
2. スクリプトを保存したフォルダーに移動します。 たとえば、これを c: ¥スクリプトに保存した場合は、次のコマンドを実行します。
    
    cd の C:\windows psscripts

3. デバイスの詳細を取得するユーザーを識別するには、次のコマンドを実行します。 この例では、bar@example.com の詳細を取得します。
    
    $u = Get-msoluser-UserPrincipalName bar@example.com

4. スクリプトを開始するには、次のコマンドを実行します。

    .\Get-MsolUserDeviceComplianceStatus.ps1-ユーザー $u エクスポート

情報は、CSV ファイルとして Windows デスクトップにエクスポートされます。 CSV のファイル名とパスを指定するには、追加のパラメーターを使用します。

## <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>スクリプトを実行してユーザーのグループのデバイス情報を取得する

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。
    
2. スクリプトを保存したフォルダーに移動します。 たとえば、これを c: ¥スクリプトに保存した場合は、次のコマンドを実行します。   

    cd の C:\windows psscripts

3. デバイスの詳細を取得するグループを識別するには、次のコマンドを実行します。 この例では、FinanceStaff グループ内のユーザーの詳細を取得します。 

    $u = MsolGroupMember-SearchString "FinanceStaff" |% {Get-msoluser-ObjectId $ _。Id

4. スクリプトを開始するには、次のコマンドを実行します。   

    .\Get-MsolUserDeviceComplianceStatus.ps1-ユーザー $u エクスポート

情報は、CSV ファイルとして Windows デスクトップにエクスポートされます。 CSV のファイル名とパスを指定するには、追加のパラメーターを使用します。

## <a name="related-topics"></a>関連項目

[Microsoft Connect は廃止されました](https://docs.microsoft.com/collaborate/connect-redirect)

[基本的なモビリティとセキュリティの概要](overview.md)

[MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)