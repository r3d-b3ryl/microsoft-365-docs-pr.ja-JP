---
title: 既存のデバイスの手動登録
description: 既存のデバイスを Microsoft Managed Desktop で管理できるよう登録する
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 1d100cc3336dcb465e54f4b81d13d50ecd4bfe1e
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319082"
---
# <a name="manual-registration-for-existing-devices"></a>既存のデバイスの手動登録

>[!NOTE]
>この記事では、既に使用しているデバイスを再利用し、Microsoft Managed Desktop に登録する手順について説明します。 新しいデバイスを操作する場合は、「 [Microsoft Managed Desktop](manual-registration.md) で新しいデバイスを自分で登録する」の手順に従ってください。 <br> <br> パートナーのプロセスについては、「デバイスを登録 [するパートナー向け手順」に記載されています](partner-registration.md)。

Microsoft Managed Desktop は、新しいデバイスを使用したり、既に持っている可能性のあるデバイスを再利用できます。 デバイスを再利用する場合は、デバイスを再イメージ化する必要があります。 Microsoft Managed Desktop にデバイスを登録するには、Microsoft エンドポイント マネージャーできます。

## <a name="prepare-to-register-existing-devices"></a>既存のデバイスを登録する準備

**既存のデバイスを登録するには、次の方法を実行します。**

1. [各デバイスのハードウェア ハッシュを取得します。](#obtain-the-hardware-hash)
2. [ハッシュ データを結合します](#merge-hash-data)。
3. [Microsoft Managed Desktop にデバイスを登録します](#register-devices-by-using-the-admin-portal)。
4. [画像が正しいか確認してください。](#check-the-image)
5. [デバイスを配信します](#deliver-the-device)。

### <a name="obtain-the-hardware-hash"></a>ハードウェア ハッシュの取得

Microsoft Managed Desktop は、ハードウェア ハッシュを参照することによって、各デバイスを一意に識別します。 既に使用しているデバイスからこの情報を取得するには、4 つのオプションがあります。

**ハードウェア ハッシュを取得するには、次の方法を実行します。**

- ハードウェア ハッシュを含む AutoPilot 登録ファイルを OEM サプライヤーに問い合わせ。
- [情報の収集] [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)。
- [Active Directory](#active-directory-powershell-script-method) をWindows PowerShell、または各デバイスで手動でスクリプトを実行[](#manual-powershell-script-method)し、結果をファイルに収集します。
- 各デバイスを起動しますが、セットアップ エクスペリエンスWindows完了して、リムーバブル フラッシュ ドライブでハッシュ[を収集する必要があります](#flash-drive-method)。

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

Microsoft Managed Desktop にMicrosoft Endpoint Configuration Manager既存のデバイスからハードウェア ハッシュを収集するには、ハードウェア ハッシュを使用します。 これらすべての前提条件を満たしている場合は、情報を収集する準備が整いました。

> [!IMPORTANT]
> この情報を取得するデバイスは、バージョン 1703 以降Windows 10実行している必要があります。

**ハードウェア ハッシュ情報を収集するには、次の方法を実行します。**

1. Configuration Manager コンソールで、[監視] を **選択します**。
2. [監視] ワークスペースで、[レポート] ノード **を展開** し、[レポート] を **展開** し、[ハードウェア **- 全般] ノードを選択** します。
3. レポートを実行し、**Windowsデバイス情報を表示し**、結果を表示します。
4. レポート ビューアーで、[エクスポート] **アイコンを** 選択し、 **CSV (コンマ区切り) オプションを選択** します。
5. ファイルを保存した後、Microsoft Managed Desktop に登録する予定のデバイスにだけ結果をフィルター処理する必要があります。 次に、データを Microsoft Managed Desktop にアップロードします。
    - [デバイスMicrosoft エンドポイント マネージャー開き、[デバイス] メニュー **に移動** します。
    - [Microsoft Managed Desktop] セクションで、[デバイス] を **選択します**。
    - [ **+ デバイスの登録]** を選択し、フライインを開き、新しいデバイスを登録します。

詳細については、以下の「 [管理ポータルを使用してデバイスを登録する」を参照](#register-devices-by-using-the-admin-portal) してください。

#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell スクリプト メソッド

Active Directory 環境では `Get-WindowsAutoPilotInfo` 、PowerShell コマンドレットを使用して、WinRM を使用して Active Directory グループ内のデバイスから情報をリモートで収集できます。 コマンドレットを使用して、 `Get-AD Computer` カタログに含まれる特定のハードウェア モデル名に対してフィルター処理された結果を取得することもできます。 続行する前に、これらの前提条件を確認してから続行します。

**Active Directory PowerShell スクリプト メソッドを使用するには、次のコマンドを実行します。**

1. WinRM が有効になっているか確認します。
1. 登録するデバイスは、ネットワーク上でアクティブです。 つまり、切断またはオフにされません。
1. デバイスでリモートで実行するアクセス許可を持つドメイン資格情報パラメーターを持っている必要があります。
1. [ファイアウォール] Windows WMI へのアクセスを許可します。 そのためには、次の手順に従います。

    - [ファイアウォール] **Windows Defenderパネルを** 開き、[ファイアウォール経由でアプリまたは機能を許可 **する] Windows Defenderします**。
    - リスト **Windows管理インストルメンテーション (WMI)** を検索し、プライベートとパブリックの両方を有効にして、[**OK**] を選択します。
1. 管理者権限を持つ PowerShell プロンプトを開きます。
1. 次 *のいずれかのスクリプト* を実行します。

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

1. デバイスのエントリがある可能性があるディレクトリにアクセスします。 ドメイン サービスとドメイン サービスを含むすべてのディレクトリから各Windows Server Active Directoryエントリを削除Azure Active Directory。 完全に処理するには数時間かかる場合があります。
1. デバイスのエントリがある可能性がある管理サービスにアクセスします。 すべての管理サービスから各デバイスのエントリを削除します(Microsoft Endpoint Configuration Manager、Microsoft Intune、Windowsします。 完全に処理するには数時間かかる場合があります。

これで、デバイスの登録 [に進みます](#register-devices-by-using-the-admin-portal)。

#### <a name="manual-powershell-script-method"></a>手動 PowerShell スクリプト メソッド

**手動の Powershell スクリプト メソッドを使用するには、次の手順を実行します。**

1. 管理者権限を持つ PowerShell プロンプトを開きます。
2. `Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。
3. `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。
4. [ハッシュ データを結合します。](#merge-hash-data)

#### <a name="flash-drive-method"></a>フラッシュ ドライブの方法

**フラッシュ ドライブの方法を使用するには、次のコマンドを実行します。**

1. 登録するデバイス以外のデバイスで、USB ドライブを挿入します。
2. 管理者権限を持つ PowerShell プロンプトを開きます。
3. `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>` を実行します。
4. 登録するデバイスをオンにしますが、セットアップ *エクスペリエンスは開始しない*。 セットアップ エクスペリエンスを誤って開始した場合は、デバイスをリセットまたは再イメージ化する必要があります。
5. USB ドライブを挿入し、Shift + F10 キーを押します。
6. 管理者権限を持つ PowerShell プロンプトを開き、次に実行します `cd <pathToUsb>`。
7. `Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。
8. `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。
9. USB ドライブを取り外し、実行してデバイスをシャットダウンします `shutdown -s -t 0`。
10. [ハッシュ データを結合します。](#merge-hash-data)

> [!IMPORTANT]
> 登録が完了するまで、登録するデバイスの電源を入れる必要はありません。

### <a name="merge-hash-data"></a>ハッシュ データの結合

PowerShell またはフラッシュ ドライブの手動方法でハードウェア ハッシュ データを収集した場合は、2 つの CSV ファイル内のデータを 1 つのファイルに結合して登録を完了する必要があります。 簡単に行う PowerShell スクリプトの例を次に示します。

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

ハッシュ データを 1 つの CSV ファイルに結合すると、デバイスの登録 [に進むことができます](#register-devices-by-using-the-admin-portal)。

## <a name="register-devices-by-using-the-admin-portal"></a>管理者ポータルを使用してデバイスを登録する

[[Microsoft エンドポイント マネージャー](https://endpoint.microsoft.com/)] で、左側 **のナビゲーション ウィンドウ** で [デバイス] を選択します。 [Microsoft Managed Desktop] セクションで、[デバイス] を **選択します**。 [Microsoft Managed Desktop Devices] ワークスペースで、[デバイス **の選択と** 登録] をクリックすると、新しいデバイスを登録するフライインが開きます。

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age.](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->

**管理ポータルを使用してデバイスを登録するには、次のコマンドを実行します。**

1. [ **ファイルのアップロード]** で、前に作成した CSV ファイルへのパスを指定します。
2. ドロップダウン メニュー [でデバイス プロファイル](../service-description/profiles.md) を選択します。
3. [デバイス **の登録] を選択します**。 システムは、[デバイス] ブレードのデバイスのリストにデバイスを **追加します**。 デバイスは登録保留 **としてマークされます**。 通常、登録にかかる時間は 10 分未満で、成功するとデバイスは [ユーザーの準備 **完了] と表示されます**。 **ユーザーの準備が** 整っているということは、ユーザーが使用を開始する準備ができていることを意味します。

> [!NOTE]
> デバイスの Azure Active Directory (AAD) グループ メンバーシップを手動で変更すると、デバイス プロファイルのグループに自動的に再割り当てされ、競合するグループから削除されます。

デバイス登録の進行状況は、メイン ページで監視できます。 報告される可能性がある状態は次のとおりです。

| 状態 | 説明 |
| ----- | ----- |
| 登録保留中 | 登録はまだ完了していません。 後で確認してください。 |
| 登録に失敗しました | 登録を完了できなかった。 詳細については、「デバイス登録の [トラブルシューティング」を参照してください](#troubleshooting-device-registration)。 |
| ユーザーの準備ができました | 登録が成功しました。 これで、デバイスをユーザーに配信する準備ができました。 Microsoft Managed Desktop では、初回セットアップをガイドしますので、それ以上の準備を行う必要はありません。 |
| Active | デバイスがユーザーに配信され、テナントに登録されています。 この状態は、デバイスを定期的に使用している場合も示します。 |
| 非アクティブ | デバイスがユーザーに配信され、テナントに登録されています。 ただし、ユーザーがデバイスを最近使用した (過去 7 日間)。 |

### <a name="troubleshooting-device-registration"></a>デバイス登録のトラブルシューティング

| エラー メッセージ | 詳細 |
| ----- | ----- |
| デバイスが見つかりません | 提供されている製造元、モデル、シリアル番号に一致するデバイスが見つからないので、このデバイスを登録できなかった。 これらの値をデバイスのサプライヤーに確認します。 |
| ハードウェア ハッシュが無効 | このデバイスに指定したハードウェア ハッシュが正しく書式設定されていません。 ハードウェア ハッシュを再確認してから、再送信します。 |
| デバイスが既に登録されている | このデバイスは既に組織に登録されています。 それ以上のアクションは必要ありません。 |
| 別の組織によって要求されたデバイス | このデバイスは、既に別の組織によって要求されています。 デバイスのサプライヤーに確認します。 |
| 予期しないエラーです | 要求を自動的に処理できなかった。 サポートに問い合わせ、要求 ID を入力します。 `<requestId>` |

## <a name="check-the-image"></a>画像を確認する

デバイスが Microsoft Managed Desktop パートナー サプライヤーから提供されている場合は、イメージが正しい必要があります。

必要に応じて、自分で画像を適用することもできます。 作業を開始するには、使用している Microsoft 担当者に問い合わせ、画像の適用場所と手順を説明します。

## <a name="deliver-the-device"></a>デバイスの配信

> [!IMPORTANT]
> デバイスをユーザーに渡す前に、そのユーザーに適切なライセンスを取得して [適用](../get-ready/prerequisites.md) してください。

すべてのライセンスが適用されている場合は、ユーザーにデバイス [を使用する準備を整えます](get-started-devices.md)。 次に、ユーザーはデバイスを起動し、セットアップ エクスペリエンスのWindows進みます。
