---
title: 新しいデバイスを自分で登録する
description: デバイスを自分で登録して、デバイスをユーザーが管理Microsoft マネージド デスクトップ
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
ms.openlocfilehash: e68a2013a2c883356f11b94d21ac68169faa42d8b719f8a41af1b73cbadc970f
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53854461"
---
# <a name="register-new-devices-yourself"></a>新しいデバイスを自分で登録する

Microsoft マネージド デスクトップ新しいデバイスを操作したり、既に持っている可能性のあるデバイスを再利用することもできます (再イメージ化が必要になります)。 デバイスの登録は、Microsoft マネージド デスクトップポータルMicrosoft エンドポイント マネージャーできます。

> [!NOTE]
> パートナーと一緒にデバイスを入手する その場合は、ハードウェア ハッシュの取得について心配する必要はありません。彼らはその世話をします。 パートナーがパートナー センターでユーザーとの関係を確立する [必要があります](https://partner.microsoft.com/dashboard)。 パートナーは、パートナー センターのヘルプ [で詳細を確認できます](/partner-center/request-a-relationship-with-a-customer)。 この関係が確立されると、パートナーはユーザーに代わってデバイスを登録するだけで、それ以上の操作は必要ありません。 詳細を確認する場合、またはパートナーに質問がある場合は、「デバイスを登録するパートナー向け [手順」を参照してください](register-devices-partner.md)。 デバイスが登録された後、イメージの [確認と](#check-the-image) ユーザーへのデバイスの [配信](#deliver-the-device) を続行できます。



## <a name="prepare-to-register-brand-new-devices"></a>新しいデバイスを登録する準備をする


新しいデバイスを手に入したら、次の手順を実行します。

1. [各デバイスのハードウェア ハッシュを取得します。](#obtain-the-hardware-hash)
2. [ハッシュ データを結合する](#merge-hash-data)
3. [デバイスを [デバイス] に登録Microsoft マネージド デスクトップ。](#register-devices-by-using-the-admin-portal)
4. [画像が正しいか確認してください。](#check-the-image)
5. [デバイスの配信](#deliver-the-device)

### <a name="obtain-the-hardware-hash"></a>ハードウェア ハッシュの取得

Microsoft マネージド デスクトップハードウェア ハッシュを参照して、各デバイスを一意に識別します。 この情報を取得するには、次の 3 つのオプションがあります。

- ハードウェア ハッシュを含む AutoPilot 登録ファイルを OEM サプライヤーに問い合わせ。
- 各デバイス[Windows PowerShellスクリプト](#powershell-script-method)を実行し、結果をファイルに収集します。
- 各デバイスを起動しますが、セットアップ エクスペリエンスWindows完了して、リムーバブル フラッシュ ドライブでハッシュ[を収集する必要があります](#flash-drive-method)。

#### <a name="powershell-script-method"></a>PowerShell スクリプト メソッド

PowerShell ギャラリー web [ サイトGet-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell スクリプトを使用できます。 デバイス ID とハードウェア ハッシュの詳細については、「デバイスを[Autopilot に追加Windows参照してください](/mem/autopilot/add-devices#device-identification)。

1. 管理者権限を持つ PowerShell プロンプトを開きます。
2. `Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。
3. `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。
4. 後続 `powershell -ExecutionPolicy restricted` の制限されていないスクリプトが実行されるのを防ぐために実行します。

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

> [!IMPORTANT]
> 登録が完了するまで、登録するデバイスの電源を入れる必要はありません。 

### <a name="merge-hash-data"></a>ハッシュ データの結合

登録を完了するには、CSV ファイル内のデータを 1 つのファイルに結合する必要があります。 簡単に行う PowerShell スクリプトの例を次に示します。

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

> [!NOTE]
> 追加の列はサポートされていません。 引用符はサポートされていません。 ANSI 形式のテキスト ファイルのみを使用できます (Unicode は使用できません)。 ヘッダーでは大文字と小文字が区別されます。 これらの要件のために、Excelを編集して CSV ファイルとして保存すると、使用できるファイルは生成できません。 デバイスのシリアル番号の先頭のゼロは必ず保持してください。

### <a name="register-devices-by-using-the-admin-portal"></a>管理者ポータルを使用してデバイスを登録する

[[Microsoft エンドポイント マネージャー]](https://endpoint.microsoft.com/)で、左側 **のナビゲーション ウィンドウ** で [デバイス] を選択します。 メニューの [Microsoft マネージド デスクトップ] セクションを探し、[デバイス] を **選択します**。 [デバイスのMicrosoft マネージド デスクトップ] ワークスペースで、[デバイスの登録]**を** 選択し、新しいデバイスを登録するフライインを開きます。

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->

次の手順を実行します。

1. [ **ファイルのアップロード]** で、前に作成した CSV ファイルへのパスを指定します。
2. ドロップダウン メニュー [でデバイス](../service-description/profiles.md) プロファイルを選択します。
3. [デバイス **の登録] を選択します**。 システムは、デバイスのリストにデバイスを追加します。 **登録** 保留として **マークされます**。 登録に要する時間は通常 10 分未満で、成功するとデバイスは Ready **for user** として表示され、ユーザーが使用を開始する準備ができていることを意味します。

> [!NOTE]
> デバイスの Azure Active Directory (AAD) グループ メンバーシップを手動で変更すると、デバイス プロファイルのグループに自動的に再割り当てされ、競合するグループから削除されます。

デバイス登録の進行状況は、メイン ページで監視できます。 報告される可能性がある状態は次のとおりです。

| 状態 | 説明 |
|---------------|-------------|
| 登録保留中 | 登録はまだ行っていません。 後で確認してください。 |
| 登録に失敗しました | 登録を完了する必要があります。 詳細については [、「デバイス登録のトラブルシューティング](#troubleshooting-device-registration) 」を参照してください。 |
| ユーザーの準備ができました | 登録が成功し、デバイスをユーザーに配信する準備が整いました。 Microsoft マネージド デスクトップセットアップをガイドしますので、それ以上の準備をする必要はありません。 |
| アクティブ | デバイスがユーザーに配信され、テナントに登録されています。 この状態は、デバイスを定期的に使用している場合も示します。 |
| 非アクティブ | デバイスがユーザーに配信され、テナントに登録されています。 ただし、最近デバイスを使用していない (過去 7 日間)。  | 

#### <a name="troubleshooting-device-registration"></a>デバイス登録のトラブルシューティング

| エラー メッセージ | 詳細 |
|---------------|-------------|
| デバイスが見つかりません | 提供されている製造元、モデル、シリアル番号に一致するデバイスが見つからないので、このデバイスを登録できなかった。 これらの値をデバイスのサプライヤーに確認します。 |
| ハードウェア ハッシュが無効 | このデバイスに指定したハードウェア ハッシュが正しく書式設定されていません。 ハードウェア ハッシュを再確認してから、再送信します。 |
| デバイスが既に登録されている | このデバイスは既に組織に登録されています。 それ以上のアクションは必要ありません。 |
| 別の組織によって要求されたデバイス | このデバイスは、既に別の組織によって要求されています。 デバイスのサプライヤーに確認します。 |
| 予期しないエラーです | 要求を自動的に処理する必要があります。 サポートに問い合わせ、要求 ID を入力します。 <requestId> |

### <a name="check-the-image"></a>画像を確認する

デバイスがパートナー サプライヤーからMicrosoft マネージド デスクトップ場合、イメージは正しい必要があります。

必要に応じて、自分で画像を適用することもできます。 作業を開始するには、使用している Microsoft 担当者に問い合わせ、画像を適用するための場所と手順を提供します。

### <a name="autopilot-group-tag"></a>Autopilot グループ タグ

管理者ポータルを使用してデバイスを登録すると、自動パイロット **グループ タグ** Microsoft365Managed_Autopilot自動的に割り当てされます。
サービスは、すべてのデバイスMicrosoft マネージド デスクトップ毎日監視し、グループ タグをまだ持ってないデバイスに割り当てします。

### <a name="deliver-the-device"></a>デバイスの配信

> [!IMPORTANT]
> デバイスをユーザーに渡す前に、そのユーザーに適切なライセンスを取得して [適用](../get-ready/prerequisites.md) してください。

すべてのライセンスが適用されている場合は、ユーザー[](get-started-devices.md)にデバイスを使用する準備を整え、ユーザーがデバイスを起動し、デバイスのセットアップ エクスペリエンスをWindowsできます。
