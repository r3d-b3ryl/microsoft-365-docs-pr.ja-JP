---
title: 新しいデバイスを自分で登録する
description: Microsoft マネージド デスクトップで管理できるようデバイスを自分で登録する
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: df6013f2f7fec32e79557a82f9b56fe4ad487786
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840683"
---
# <a name="register-new-devices-yourself"></a>新しいデバイスを自分で登録する

Microsoft マネージド デスクトップは、新しいデバイスで動作するか、既に持っているデバイスを再利用できます (デバイスのイメージを再作成する必要があります)。 Microsoft Endpoint Manager ポータルで、Microsoft マネージド デスクトップにデバイスを登録できます。

> [!NOTE]
> パートナーと一緒にデバイスを入手する場合 その場合は、ハードウェア ハッシュの取得について心配する必要はありません。この問題はユーザーに対して行います。 パートナーがパートナー センターでパートナーとの関係を [確立します。](https://partner.microsoft.com/dashboard) パートナーは、パートナー センターのヘルプ [で詳細を確認できます](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)。 この関係が確立されると、パートナーはユーザーに代わってデバイスを登録するだけで、それ以上の操作は必要ありません。 詳細を確認する場合、またはパートナーに質問がある場合は、「パートナーがデバイスを登録するための手順 [」を参照してください](register-devices-partner.md)。 デバイスを登録したら、イメージの [確認](#check-the-image) とユーザーへのデバイスの配信 [に進](#deliver-the-device) みます。

## <a name="prepare-to-register-brand-new-devices"></a>新しいデバイスの登録を準備する


新しいデバイスを手に入したら、次の手順に従います。

1. [各デバイスのハードウェア ハッシュを取得します。](#obtain-the-hardware-hash)
2. [ハッシュ データをマージする](#merge-hash-data)
3. [Microsoft マネージド デスクトップにデバイスを登録します](#register-devices-by-using-the-admin-portal)。
4. [画像が正しいか、確認してください。](#check-the-image)
5. [デバイスの配信](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>ハードウェア ハッシュを取得する

Microsoft マネージド デスクトップでは、ハードウェア ハッシュを参照して各デバイスを一意に識別します。 この情報を取得するには、次の 3 つのオプションがあります。

- ハードウェア ハッシュを含む AutoPilot 登録ファイルを OEM 供給者に問い合わせ、
- 各デバイス [Windows PowerShellスクリプト](#powershell-script-method) を実行し、結果をファイルに収集します。
- 各デバイスを起動します。ただし、Windows セットアップ エクスペリエンスを完了する必要があります。また、リムーバブル フラッシュ ドライブでハッシュ [を収集します](#flash-drive-method)。

#### <a name="powershell-script-method"></a>PowerShell スクリプトメソッド

PowerShell ギャラリー Web [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell スクリプトを使用できます。 デバイスの識別とハードウェア ハッシュの詳細については [、「Windows Autopilot](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification)へのデバイスの追加」を参照してください。

1.  管理者権限で PowerShell プロンプトを開きます。
2.  `Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。
3.  `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。
4.  後続 `powershell -ExecutionPolicy restricted` の制限のないスクリプトが実行されるのを防ぐために実行します。


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

>[!IMPORTANT]
>登録が完了するまで、もう一度登録しているデバイスの電源を入れる必要はありません。 


### <a name="merge-hash-data"></a>ハッシュ データをマージする

登録を完了するには、CSV ファイル内のデータを 1 つのファイルに結合する必要があります。 簡単に実行できる PowerShell スクリプトのサンプルを次に示します。

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>管理ポータルを使用してデバイスを登録する

[Microsoft Endpoint Manager で、](https://endpoint.microsoft.com/)左側のナビゲーション ウィンドウで [デバイス] を選択します。  メニューの [Microsoft マネージド デスクトップ] セクションを探し、[デバイス] を選択 **します**。 Microsoft マネージド デスクトップ デバイス ワークスペースで、デバイスの選択 **と** 登録を行います。このワークスペースでは、新しいデバイスを登録するフライインが開きます。

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


次の手順を実行します。

1. [ **ファイルのアップロード**] で、前に作成した CSV ファイルへのパスを指定します。
3. [デバイス **の登録] を選択します**。 登録保留中としてマークされているデバイスの一覧に、デバイス **が追加されます**。 通常、登録に要する時間は 10 分未満です。正常に終了すると、デバイスは "準備完了" と表示されます。つまり、デバイスは準備が整い、ユーザーが使い始めるのを待ちます。


デバイス登録の進行状況は、メイン ページで監視できます。 報告される可能性がある状態は次のとおりです。

| 状態 | 説明 |
|---------------|-------------|
| Registration Pending | 登録はまだ完了していません。 後で確認してください。 |
| 登録に失敗しました | 登録を完了する必要があります。 詳細については [、「デバイス登録のトラブルシューティング」](#troubleshooting-device-registration) を参照してください。 |
| ユーザーの準備完了 | 登録が成功し、デバイスをユーザーに配信する準備が整いました。 Microsoft マネージド デスクトップでは、初回セットアップについて説明します。そのため、追加の準備を行う必要はありません。 |
| Active | デバイスがユーザーに配信され、テナントに登録されている。 この状態は、デバイスを定期的に使用している場合も示します。 |
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





