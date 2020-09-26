---
title: 新しいデバイスを自分で登録する
description: Microsoft マネージドデスクトップで管理できるようにデバイスを自分で登録する
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 225cb8b74a50fa8308cc14e8ad35283e6a7aa044
ms.sourcegitcommit: e9f32675061cd1cf4a3e2dada393e10d7c552efe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2020
ms.locfileid: "48279569"
---
# <a name="register-new-devices-yourself"></a>新しいデバイスを自分で登録する

Microsoft マネージドデスクトップをブランド化されたデバイスで使用することも、既に所有しているデバイスを再利用することもできます (イメージを再作成する必要があります)。 Microsoft マネージドデスクトップにデバイスを登録するには、Microsoft エンドポイントマネージャーポータルを使用します。

> [!NOTE]
> パートナーと協力してデバイスを入手する方法 その場合は、ハードウェアハッシュの取得について心配する必要はありません。そのようにします。 パートナーが [パートナーセンター](https://partner.microsoft.com/dashboard)でお客様との関係を確立していることを確認してください。 パートナーが詳細については、 [パートナーセンターのヘルプ](https://docs.microsoft.com/partner-center/request-a-relationship-with-a-customer)を参照してください。 この関係が確立されると、パートナーは単にデバイスを登録するだけで済みます。これ以上の操作は必要ありません。 詳細を確認する場合、またはパートナーに質問がある場合は、「 [パートナーがデバイスを登録する手順](register-devices-partner.md)」を参照してください。 デバイスが登録されたら、 [画像の確認](#check-the-image) とユーザーへ [のデバイスの配信](#deliver-the-device) を続行できます。

## <a name="prepare-to-register-brand-new-devices"></a>ブランドを登録するために準備する-新しいデバイス


新しいデバイスを用意したら、次の手順を実行します。

1. [各デバイスのハードウェアハッシュを取得します。](#obtain-the-hardware-hash)
2. [ハッシュデータを結合する](#merge-hash-data)
3. [Microsoft マネージドデスクトップにデバイスを登録](#register-devices-by-using-the-admin-portal)します。
4. [画像が正しいことをもう一度確認してください。](#check-the-image)
5. [デバイスを配信する](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>ハードウェアハッシュを取得する

Microsoft マネージドデスクトップは、ハードウェアハッシュを参照して各デバイスを一意に識別します。 この情報を取得するには、次の3つのオプションがあります。

- ハードウェアハッシュを含む自動操縦登録ファイルについては、OEM サプライヤーにお問い合わせください。
- 各デバイスで [Windows PowerShell スクリプト](#powershell-script-method) を実行し、ファイルに結果を収集します。
- 各デバイスを開始しますが、Windows セットアップの動作を完了せず [に、リムーバブルフラッシュドライブでハッシュを収集](#flash-drive-method)します。

#### <a name="powershell-script-method"></a>PowerShell スクリプトメソッド

PowerShell Gallery web サイトで [Get-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) powershell スクリプトを使用できます。 デバイス id とハードウェアハッシュの詳細については、「 [Windows 自動操縦にデバイスを追加する](https://docs.microsoft.com/mem/autopilot/add-devices#device-identification)」を参照してください。

1.  管理者権限を持つ PowerShell プロンプトを開きます。
2.  `Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。
3.  `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。

#### <a name="flash-drive-method"></a>Flash drive メソッド

1. 登録している以外のデバイスに USB ドライブを挿入します。
2. 管理者権限を持つ PowerShell プロンプトを開きます。
3. `Save-Script -Name Get-WindowsAutoPilotInfo -Path <pathToUsb>` を実行します。
4. 登録するデバイスを有効にしますが、 *セットアップの操作は開始*しないでください。 セットアップの操作を誤って開始した場合は、デバイスをリセットまたは再イメージする必要があります。
5. USB ドライブを挿入して、SHIFT + F10 キーを押します。
6. 管理者権限で PowerShell プロンプトを開き、を実行し `cd <pathToUsb>` ます。
7. `Set-ExecutionPolicy -ExecutionPolicy Unrestricted` を実行します。
8. `.\Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。
9. USB ドライブを取り外し、次のようにしてデバイスをシャットダウンします。 `shutdown -s -t 0`

>[!IMPORTANT]
>登録が完了するまでは、デバイスの電源を入れないでください。 


### <a name="merge-hash-data"></a>ハッシュデータを結合する

登録を完了するには、CSV ファイル内のデータを1つのファイルに結合する必要があります。 これを簡単にするためのサンプル PowerShell スクリプトを次に示します。

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`


#### <a name="register-devices-by-using-the-admin-portal"></a>管理ポータルを使用してデバイスを登録する

[Microsoft エンドポイントマネージャー](https://endpoint.microsoft.com/)で、左側のナビゲーションウィンドウの [**デバイス**] を選択します。 メニューの [Microsoft Managed Desktop] セクションを探し、[ **デバイス**] を選択します。 [Microsoft Managed Desktop Devices] ワークスペースで、[ **+ デバイスの登録** ] を選択して、新しいデバイスを登録するためのフライインを開きます。

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->


<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->


次の手順を実行します。

1. [ **ファイルのアップロード**] で、以前に作成した CSV ファイルへのパスを指定します。
3. [ **デバイスの登録**] を選択します。 システムによってデバイス **ブレード**上のデバイスの一覧にデバイスが追加され、[ **登録保留中**] としてマークされます。 通常、登録にかかる時間は10分未満で、成功した場合、デバイスは **ユーザーのための** 準備完了として表示され、ユーザーが使用を開始するのを待っています。


メインページでのデバイス登録の進行状況を監視できます。 報告される状態は次のとおりです。

| 状態 | 説明 |
|---------------|-------------|
| 登録保留中 | 登録はまだ行われていません。 後でもう一度確認してください。 |
| 登録の失敗 | 登録を完了できませんでした。 詳細については、「 [device registration のトラブルシューティング](#troubleshooting-device-registration) 」を参照してください。 |
| ユーザーの準備完了 | 登録が成功し、デバイスをユーザーに配信する準備ができました。 Microsoft マネージドデスクトップでは、初めてセットアップを実行することができます。したがって、これ以上の準備を行う必要はありません。 |
| Active | デバイスはユーザーに配信され、テナントに登録されています。 これは、デバイスを定期的に使用していることも示しています。 |
| 未使用 | デバイスはユーザーに配信され、テナントに登録されています。 しかし、最近7日間ではデバイスを使用していません。  | 

#### <a name="troubleshooting-device-registration"></a>デバイス登録のトラブルシューティング

| エラー メッセージ | 詳細 |
|---------------|-------------|
| デバイスが見つかりません | 提供された製造元、モデル、またはシリアル番号に一致するものが見つからなかったため、このデバイスを登録できませんでした。 これらの値は、デバイスの提供元に確認してください。 |
| ハードウェアハッシュが無効です | このデバイスに対して提供されたハードウェアハッシュが正しくフォーマットされていませんでした。 ハードウェアハッシュをもう一度確認してから再送信します。 |
| デバイスは既に登録されています | このデバイスは既に組織に登録されています。 その他のアクションは必要ありません。 |
| 別の組織によって要求されるデバイス | このデバイスは、既に別の組織によって要求されています。 デバイスサプライヤーに確認します。 |
| 予期しないエラーです | 要求は自動的に処理されませんでした。 サポートに連絡して、要求 ID を提供します。 <requestId> |

### <a name="check-the-image"></a>画像を確認する

デバイスが Microsoft マネージドデスクトップパートナーのサプライヤーからのものである場合は、イメージが正しいことを確認してください。

また、必要に応じて、自分で画像を適用することも歓迎しています。 開始するには、作業している Microsoft の担当者に連絡して、イメージを適用するための場所と手順を提供します。

### <a name="deliver-the-device"></a>デバイスを配信する

> [!IMPORTANT]
> ユーザーにデバイスを渡す前に、そのユーザーの [適切なライセンス](../get-ready/prerequisites.md) を取得して適用していることを確認してください。

すべてのライセンスが適用されている場合は、 [デバイスを使用する準備](get-started-devices.md)ができたら、ユーザーはデバイスを起動して、Windows セットアップ操作を続行することができます。






