---
title: 既存のデバイスをj自分で登録する
description: Microsoft マネージド デスクトップで管理できるよう、既に自分が持っている可能性がある再利用可能なデバイスを登録する
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: c2ba687b38f1de4d2ed09b0bd690e02b43f15f8d
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840517"
---
# <a name="register-existing-devices-yourself"></a>既存のデバイスをj自分で登録する

>[!NOTE]
>このトピックでは、既に持っているデバイスを再利用し、Microsoft マネージド デスクトップに登録する手順について説明します。 新しいデバイスを使用している場合は [、「Microsoft マネージド](register-devices-self.md) デスクトップに新しいデバイスを自分で登録する」の手順に従ってください。

パートナーのプロセスについては、「パートナーがデバイスを登録するための [手順」を参照してください](register-devices-partner.md)。

Microsoft マネージド デスクトップは、新しいデバイスで動作するか、既に持っているデバイスを再利用できます (デバイスのイメージを再作成する必要があります)。 Microsoft Endpoint Manager ポータルで、Microsoft マネージド デスクトップにデバイスを登録できます。

## <a name="prepare-to-register-existing-devices"></a>既存のデバイスの登録を準備する


既存のデバイスを登録するには、次の手順を実行します。

1. [各デバイスのハードウェア ハッシュを取得します。](#obtain-the-hardware-hash)
2. [ハッシュ データをマージする](#merge-hash-data)
3. [Microsoft マネージド デスクトップにデバイスを登録します](#register-devices-by-using-the-admin-portal)。
4. [画像が正しいか、確認してください。](#check-the-image)
5. [デバイスの配信](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>ハードウェア ハッシュを取得する

Microsoft マネージド デスクトップでは、ハードウェア ハッシュを参照して各デバイスを一意に識別します。 既に使用しているデバイスからこの情報を取得するには、次の 4 つのオプションがあります。

- ハードウェア ハッシュを含む AutoPilot 登録ファイルを OEM 供給者に問い合わせ、
- [Microsoft Endpoint Configuration Manager で情報を収集します](#microsoft-endpoint-configuration-manager)。
- [Active](#active-directory-powershell-script-method) Directory Windows PowerShell手動でスクリプトを実行し、結果を[](#manual-powershell-script-method)ファイルに収集します。
- 各デバイスを起動します。ただし、Windows セットアップ エクスペリエンスを完了する必要があります。また、リムーバブル フラッシュ ドライブでハッシュ [を収集します](#flash-drive-method)。

#### <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

Microsoft Endpoint Configuration Manager を使用して、Microsoft マネージド デスクトップに登録する既存のデバイスからハードウェア ハッシュを収集できます。

> [!IMPORTANT]
> この情報を取得するデバイスは、Windows 10 バージョン 1703 以降を実行している必要があります。 

これらすべての前提条件を満たした場合は、次の手順に従って情報を収集する準備が整います。

1. Configuration Manager コンソールで、[監視] を **選択します**。 
2. [監視] ワークスペースで、[レポート] ノード **を展開し** 、[ **レポート**] を展開して、[ハードウェア - 全般] **ノードを選択** します。 
3. レポートの **Windows Autopilot Device Information を実行し**、結果を表示します。
4. レポート ビューアーでエクスポート アイコンを選択し **、CSV (コンマ区切り) オプションを選択** します。
5. ファイルを保存した後、Microsoft マネージド デスクトップに登録する予定のデバイスに対して結果をフィルター処理し、データを Microsoft マネージド デスクトップにアップロードする必要があります。 Microsoft Endpoint Manager を開き、[デバイス] メニューに移動し、[Microsoft マネージド デスクトップ] セクションを探し、[デバイス] を選択 **します**。 [+ **デバイスの登録]** を選択すると、新しいデバイスを登録するフライインが開きます。


詳細については [、「管理ポータルを使用してデバイスを登録する](#register-devices-by-using-the-admin-portal) 」を参照してください。


#### <a name="active-directory-powershell-script-method"></a>Active Directory PowerShell スクリプト メソッド

Active Directory 環境では、PowerShell コマンドレットを使用して、WinRM を使用して Active Directory グループ内のデバイスからリモートで情報 `Get-WindowsAutoPilotInfo` を収集できます。 このコマンドレットを使用して、カタログに含まれる特定のハードウェア モデル名に対してフィルター処理された結果 `Get-AD Computer` を取得することもできます。 続行する前に、まずこれらの前提条件を確認してから、次の手順に進みます。

- WinRM が有効になっている。
- 登録するデバイスはネットワーク上でアクティブです (つまり、切断またはオフにされません)。
- デバイスでリモートで実行するアクセス許可を持つドメイン資格情報パラメーターを持っている必要があります。
- Windows ファイアウォールで WMI へのアクセスが許可されている必要があります。 これを行うには、次の手順を実行します。

    1. Windows Defender **ファイアウォール** のコントロール パネルを開き、ファイアウォールからアプリまたは機能 **を許可Windows Defenderします**。
    
    2. 一 **覧で Windows Management Instrumentation (WMI)** を見つけ **、Private** と Public の両方を有効にして **、[OK]** を選択します。

1.  管理者権限で PowerShell プロンプトを開きます。

2.  次 *のいずれかのスクリプト* を実行します。

    ```powershell
    Install-script -name Get-WindowsAutoPilotInfo 
    #example one – leverage Get-ADComputer to enumerate devices 
    Get-ADComputer -filter * | powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname>
    ```

    ```powershell 
    #example two – target specific devices: 
    Set-ExecutionPolicy powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo.ps1 -credential Domainname\<accountname> -Name Machine1,Machine2,Machine3
    ```

3. デバイスのエントリがある可能性があるディレクトリにアクセスします。 Windows Server Active Directoryドメイン サービスと Azure Active Directory を含むすべてのディレクトリから、各デバイスのエントリを削除します。 完全に処理するには、削除に数時間かかる可能性があります。

4. デバイスのエントリがある可能性があるアクセス管理サービス。 Microsoft Endpoint Configuration Manager、Microsoft Intune、Windows Autopilot など、すべての管理サービスから各デバイスのエントリを削除します。  完全に処理するには、削除に数時間かかる可能性があります。

これで、デバイスの登録に [進みます](#register-devices-by-using-the-admin-portal)。

#### <a name="manual-powershell-script-method"></a>手動 PowerShell スクリプトメソッド

1.  管理者権限で PowerShell プロンプトを開きます。
2.  `Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。
3.  `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。
4. [ハッシュ データをマージします。](#merge-hash-data)

#### <a name="flash-drive-method"></a>フラッシュ ドライブ方式

1. 登録するデバイス以外のデバイスに USB ドライブを挿入します。
2. 管理者権限で PowerShell プロンプトを開きます。
3. `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>` を実行します。
4. 登録するデバイスをオンにしますが、セットアップ *エクスペリエンスは開始してください*。 誤ってセットアップ エクスペリエンスを開始した場合は、デバイスをリセットまたは再イメージ化する必要があります。
5. USB ドライブを挿入し、Shift キーを押しながら F10 キーを押します。
6. 管理者権限で PowerShell プロンプトを開き、次に実行します `cd <pathToUsb>` 。
7. `Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。
8. `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。
9. USB ドライブを取り外し、次に実行してデバイスをシャットダウンします。 `shutdown -s -t 0`
10. [ハッシュ データをマージします。](#merge-hash-data)

>[!IMPORTANT]
>登録が完了するまで、登録するデバイスの電源を入れる必要はありません。 



### <a name="merge-hash-data"></a>ハッシュ データをマージする

手動の PowerShell またはフラッシュ ドライブの方法でハードウェア ハッシュ データを収集した場合、登録を完了するには、CSV ファイル内のデータを 1 つのファイルに結合する必要があります。 簡単に実行できる PowerShell スクリプトのサンプルを次に示します。

```powershell
Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv
```

ハッシュ データを 1 つの CSV ファイルにマージすると、デバイスの登録 [に進むことができます](#register-devices-by-using-the-admin-portal)。


#### <a name="register-devices-by-using-the-admin-portal"></a>管理ポータルを使用してデバイスを登録する

[Microsoft Endpoint Manager で、](https://endpoint.microsoft.com/)左側のナビゲーション ウィンドウで [デバイス] を選択します。  メニューの [Microsoft マネージド デスクトップ] セクションを探し、[デバイス] を選択 **します**。 Microsoft マネージド デスクトップ デバイス ワークスペースで、デバイスの選択 **と** 登録を行います。このワークスペースでは、新しいデバイスを登録するフライインが開きます。

<!-- Update with new picture [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


次の手順を実行します。

1. [ **ファイルのアップロード**] で、前に作成した CSV ファイルへのパスを指定します。

1. [デバイス **の登録] を選択します**。 システムによって、[デバイス] ブレードのデバイスの一覧にデバイスが追加されます。登録が保留中 **としてマークされます**。 通常、登録に要する時間は 10 分未満です。正常に終了すると、デバイスは "準備完了" と表示されます。つまり、デバイスは準備が整い、ユーザーが使い始めるのを待ちます。


デバイス登録の進行状況は、メイン ページで監視できます。 報告される可能性がある状態は次のとおりです。

| 状態 | 説明 |
|---------------|-------------|
| Registration Pending | 登録はまだ完了していません。 後で確認してください。 |
| 登録に失敗しました | 登録を完了する必要があります。 詳細については [、「デバイス登録のトラブルシューティング」](#troubleshooting-device-registration) を参照してください。 |
| ユーザーの準備完了 | 登録が成功し、デバイスをユーザーに配信する準備が整いました。 Microsoft マネージド デスクトップでは、初回セットアップについて説明します。そのため、追加の準備を行う必要はありません。 |
| Active | デバイスがユーザーに配信され、テナントに登録されている。 これは、デバイスを定期的に使用している場合も示します。 |
| 非アクティブ | デバイスがユーザーに配信され、テナントに登録されている。 ただし、最近 (過去 7 日間で) デバイスを使用していない。  | 

#### <a name="troubleshooting-device-registration"></a>デバイス登録のトラブルシューティング

| エラー メッセージ | 詳細 |
|---------------|-------------|
| デバイスが見つかりません | 提供された製造元、モデル、シリアル番号に一致するデバイスが見つからなかったため、このデバイスを登録できなかった。 デバイスの供給者にこれらの値を確認します。 |
| ハードウェア ハッシュが無効です | このデバイスに指定したハードウェア ハッシュが正しくフォーマットされていません。 ハードウェア ハッシュを再確認し、再送信します。 |
| デバイスが既に登録されている | このデバイスは既に組織に登録されています。 それ以上の操作は必要ありません。 |
| 別の組織によって要求されたデバイス | このデバイスは、別の組織によって既に要求されています。 デバイスの供給者に確認します。 |
| 予期しないエラーです | 要求を自動的に処理する必要がありました。 サポートに問い合わせ、要求 ID を入力します。 <requestId> |

### <a name="check-the-image"></a>画像を確認する

デバイスが Microsoft マネージド デスクトップ パートナーの供給者から提供されている場合は、イメージが正しい必要があります。

必要に応じて、画像を自分で適用することもできます。 To get started, contact the Microsoft representative you're working with and they will provide you the location and steps for applying the image.

### <a name="deliver-the-device"></a>デバイスの配信

> [!IMPORTANT]
> デバイスをユーザーに渡す前に、そのユーザーに適切なライセンスを取得して [適用してください](../get-ready/prerequisites.md) 。

すべてのライセンスが適用されている場合は、ユーザー[](get-started-devices.md)がデバイスを使用する準備を整え、ユーザーがデバイスを起動して Windows セットアップ エクスペリエンスを続行できます。









