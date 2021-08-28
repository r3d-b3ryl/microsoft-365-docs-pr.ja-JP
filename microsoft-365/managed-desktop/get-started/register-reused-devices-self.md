---
title: 既存のデバイスをj自分で登録する
description: 再利用済みのデバイスを登録して、ユーザーが自分で管理Microsoft マネージド デスクトップ
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: c817805994662b080f530b76b76cbb111ee36795
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58575554"
---
# <a name="register-existing-devices-yourself"></a>既存のデバイスをj自分で登録する

>[!NOTE]
>このトピックでは、既に使用しているデバイスを再利用し、デバイスを既存のデバイスに登録する手順Microsoft マネージド デスクトップ。 新しいデバイスを操作する場合は、「新しいデバイスを自分で登録する」の手順に[Microsoft マネージド デスクトップ](register-devices-self.md)してください。

パートナーのプロセスについては、「デバイスを登録 [するパートナー向け手順」に記載されています](register-devices-partner.md)。

Microsoft マネージド デスクトップ新しいデバイスを操作したり、既に持っている可能性のあるデバイスを再利用することもできます (再イメージ化が必要になります)。 デバイスの登録は、Microsoft マネージド デスクトップポータルMicrosoft エンドポイント マネージャーできます。

## <a name="prepare-to-register-existing-devices"></a>既存のデバイスを登録する準備


既存のデバイスを登録するには、次の手順を実行します。

1. [各デバイスのハードウェア ハッシュを取得します。](#obtain-the-hardware-hash)
2. [ハッシュ データを結合する](#merge-hash-data)
3. [デバイスを [デバイス] に登録Microsoft マネージド デスクトップ。](#register-devices-by-using-the-admin-portal)
4. [画像が正しいか確認してください。](#check-the-image)
5. [デバイスの配信](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>ハードウェア ハッシュの取得

Microsoft マネージド デスクトップハードウェア ハッシュを参照して、各デバイスを一意に識別します。 既に使用しているデバイスからこの情報を取得するには、次の 4 つのオプションがあります。

- ハードウェア ハッシュを含む AutoPilot 登録ファイルを OEM サプライヤーに問い合わせ。
- で情報を[収集Microsoft Endpoint Configuration Manager。](#microsoft-endpoint-configuration-manager)
- Active [Directory](#active-directory-powershell-script-method)をWindows PowerShell、または各デバイスで手動でスクリプト[](#manual-powershell-script-method)を実行し、結果をファイルに収集します。
- 各デバイスを起動しますが、セットアップ エクスペリエンスWindows完了して、リムーバブル フラッシュ ドライブでハッシュ[を収集する必要があります](#flash-drive-method)。

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

ユーザーは、Microsoft Endpoint Configuration Managerを使用して、デバイスに登録する既存のデバイスからハードウェア ハッシュを収集Microsoft マネージド デスクトップ。

> [!IMPORTANT]
> この情報を取得するデバイスは、バージョン 1703 以降Windows 10実行している必要があります。 

これらすべての前提条件を満たしている場合は、次の手順に従って情報を収集する準備が整いました。

1. Configuration Manager コンソールで、[監視] を **選択します**。 
2. [監視] ワークスペースで、[レポート] ノード **を展開し** 、[レポート] を **展開** し、[ハードウェア **- 全般] ノードを選択** します。 
3. レポートを実行し **、[Windows情報] をクリックし**、結果を表示します。
4. レポート ビューアーで、[エクスポート] **アイコンを** 選択し、CSV (コンマ区切り **) オプションを選択** します。
5. ファイルを保存した後は、データに登録する予定のデバイスに対して結果をフィルター処理し、Microsoft マネージド デスクトップにデータをアップロードするMicrosoft マネージド デスクトップ。 [デバイスMicrosoft エンドポイント マネージャー開き、[デバイス]メニューに移動し、[デバイス] セクションMicrosoft マネージド デスクトップデバイス] を **選択します**。 [+ **デバイスの登録]** を選択すると、フライインが開き、新しいデバイスが登録されます。


詳細については [、「管理ポータルを使用してデバイスを登録する](#register-devices-by-using-the-admin-portal) 」を参照してください。


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell スクリプト メソッド

Active Directory 環境では、PowerShell コマンドレットを使用して、WinRM を使用して Active Directory グループ内のデバイスから情報をリモート `Get-WindowsAutoPilotInfo` で収集できます。 コマンドレットを使用して、カタログに含まれる特定のハードウェア モデル名に対してフィルター処理された結果 `Get-AD Computer` を取得することもできます。 続行する前に、まずこれらの前提条件を確認してから、次の手順に進みます。

- WinRM が有効です。
- 登録するデバイスは、ネットワーク上でアクティブです (つまり、切断またはオフにされません)。
- デバイスでリモートで実行するアクセス許可を持つドメイン資格情報パラメーターを持っている必要があります。
- [ファイアウォール] でWindows WMI へのアクセスを許可します。 そのためには、次の手順に従います。

    1. [ファイアウォール] **Windows Defenderパネルを** 開き、[ファイアウォール経由でアプリまたは機能を許可 **する] Windows Defenderします**。

    2. リスト **Windows管理インストルメンテーション (WMI)** を検索し、プライベートとパブリックの両方を有効にして **、[OK] を選択します**。

1. 管理者権限を持つ PowerShell プロンプトを開きます。

2. 次 *のいずれかのスクリプト* を実行します。

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. デバイスのエントリがある可能性があるディレクトリにアクセスします。 ドメイン サービスとドメイン サービスを含むすべてのディレクトリから各Windows Server Active Directoryエントリを削除Azure Active Directory。 完全に処理するには、削除に数時間かかる場合があります。

4. デバイスのエントリがある可能性がある管理サービスにアクセスします。 すべての管理サービスから各デバイスのエントリを削除します(Microsoft Endpoint Configuration Manager、Microsoft Intune、Windows)。 完全に処理するには、削除に数時間かかる場合があります。

これで、デバイスの登録 [に進みます](#register-devices-by-using-the-admin-portal)。

#### <a name="manual-powershell-script-method"></a>手動 PowerShell スクリプト メソッド

1. 管理者権限を持つ PowerShell プロンプトを開きます。
2. `Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。
3. `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。
4. [ハッシュ データを結合します。](#merge-hash-data)

#### <a name="flash-drive-method"></a>フラッシュ ドライブの方法

1. 登録するデバイス以外のデバイスで、USB ドライブを挿入します。
2. 管理者権限を持つ PowerShell プロンプトを開きます。
3. `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>` を実行します。
4. 登録するデバイスをオンにしますが、セットアップ *エクスペリエンスは開始しない*。 セットアップ エクスペリエンスを誤って開始した場合は、デバイスをリセットまたは再イメージ化する必要があります。
5. USB ドライブを挿入し、Shift + F10 キーを押します。
6. 管理者権限を持つ PowerShell プロンプトを開き、次に実行します `cd <pathToUsb>` 。
7. `Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。
8. `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。
9. USB ドライブを削除し、実行してデバイスをシャットダウンする `shutdown -s -t 0`
10. [ハッシュ データを結合します。](#merge-hash-data)

> [!IMPORTANT]
> 登録が完了するまで、登録するデバイスの電源を入れる必要はありません。 

### <a name="merge-hash-data"></a>ハッシュ データの結合

手動の PowerShell またはフラッシュ ドライブの方法でハードウェア ハッシュ データを収集した場合は、CSV ファイル内のデータを 1 つのファイルに結合して登録を完了する必要があります。 簡単に行う PowerShell スクリプトの例を次に示します。

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

ハッシュ データを 1 つの CSV ファイルにマージすると、デバイスの登録 [に進むことができます](#register-devices-by-using-the-admin-portal)。

## <a name="register-devices-by-using-the-admin-portal"></a>管理者ポータルを使用してデバイスを登録する

[[Microsoft エンドポイント マネージャー]](https://endpoint.microsoft.com/)で、左側 **のナビゲーション ウィンドウ** で [デバイス] を選択します。 メニューの [Microsoft マネージド デスクトップ] セクションを探し、[デバイス] を **選択します**。 [デバイスのMicrosoft マネージド デスクトップ] ワークスペースで、[デバイスの登録]**を** 選択し、新しいデバイスを登録するフライインを開きます。

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age.](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->

次の手順を実行します。

1. [ **ファイルのアップロード]** で、前に作成した CSV ファイルへのパスを指定します。
2. ドロップダウン メニュー [でデバイス](../service-description/profiles.md) プロファイルを選択します。
3. [デバイス **の登録] を選択します**。 システムは、[デバイス] ブレードのデバイスのリストにデバイスを追加します 。登録保留中 **とマークされます**。 登録に要する時間は通常 10 分未満で、成功するとデバイスは Ready **for user** として表示され、ユーザーが使用を開始する準備ができていることを意味します。

> [!NOTE]
> デバイスの Azure Active Directory (AAD) グループ メンバーシップを手動で変更すると、デバイス プロファイルのグループに自動的に再割り当てされ、競合するグループから削除されます。

デバイス登録の進行状況は、メイン ページで監視できます。 報告される可能性がある状態は次のとおりです。

| 状態 | 説明 |
|---------------|-------------|
| 登録保留中 | 登録はまだ行っていません。 後で確認してください。 |
| 登録に失敗しました | 登録を完了する必要があります。 詳細については [、「デバイス登録のトラブルシューティング](#troubleshooting-device-registration) 」を参照してください。 |
| ユーザーの準備ができました | 登録が成功し、デバイスをユーザーに配信する準備が整いました。 Microsoft マネージド デスクトップセットアップをガイドしますので、それ以上の準備をする必要はありません。 |
| アクティブ | デバイスがユーザーに配信され、テナントに登録されています。 これは、デバイスを定期的に使用している場合も示します。 |
| 非アクティブ | デバイスがユーザーに配信され、テナントに登録されています。 ただし、最近デバイスを使用していない (過去 7 日間)。  | 

### <a name="troubleshooting-device-registration"></a>デバイス登録のトラブルシューティング

| エラー メッセージ | 詳細 |
|---------------|-------------|
| デバイスが見つかりません | 提供されている製造元、モデル、シリアル番号に一致するデバイスが見つからないので、このデバイスを登録できなかった。 これらの値をデバイスのサプライヤーに確認します。 |
| ハードウェア ハッシュが無効 | このデバイスに指定したハードウェア ハッシュが正しく書式設定されていません。 ハードウェア ハッシュを再確認してから、再送信します。 |
| デバイスが既に登録されている | このデバイスは既に組織に登録されています。 それ以上のアクションは必要ありません。 |
| 別の組織によって要求されたデバイス | このデバイスは、既に別の組織によって要求されています。 デバイスのサプライヤーに確認します。 |
| 予期しないエラーです | 要求を自動的に処理する必要があります。 サポートに問い合わせ、要求 ID を入力します。 <requestId> |

## <a name="check-the-image"></a>画像を確認する

デバイスがパートナー サプライヤーからMicrosoft マネージド デスクトップ場合、イメージは正しい必要があります。

必要に応じて、自分で画像を適用することもできます。 作業を開始するには、使用している Microsoft 担当者に問い合わせ、画像を適用するための場所と手順を提供します。

## <a name="deliver-the-device"></a>デバイスの配信

> [!IMPORTANT]
> デバイスをユーザーに渡す前に、そのユーザーに適切なライセンスを取得して [適用](../get-ready/prerequisites.md) してください。

すべてのライセンスが適用されている場合は、ユーザー[](get-started-devices.md)にデバイスを使用する準備を整え、ユーザーがデバイスを起動し、デバイスのセットアップ エクスペリエンスをWindowsできます。
