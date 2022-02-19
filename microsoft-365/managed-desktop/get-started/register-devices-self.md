---
title: 新しいデバイスを自分で登録する
description: デバイスを自分で登録して、Microsoft Managed Desktop で管理できるよう
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
ms.openlocfilehash: 8aba31c60d587667c4623d18b2a3d0e389681685
ms.sourcegitcommit: 966344e1aa442a4d10a0fb05f56badd38c833bb2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2022
ms.locfileid: "62909737"
---
# <a name="register-new-devices-yourself"></a>新しいデバイスを自分で登録する

Microsoft Managed Desktop は、新しいデバイスを使用したり、既に持っている可能性のあるデバイスを再利用できます。 デバイスを再利用する場合は、デバイスを再イメージ化する必要があります。 Microsoft Managed Desktop にデバイスを登録するには、Microsoft エンドポイント マネージャーできます。

> [!NOTE]
> パートナーと一緒にデバイスを入手する その場合は、ハードウェア ハッシュの取得について心配する必要はありません。彼らはその世話をします。 パートナーがパートナー センターでユーザーとの関係を[確立します。](https://partner.microsoft.com/dashboard) パートナーは、パートナー センターのヘルプ [で詳細を確認できます](/partner-center/request-a-relationship-with-a-customer)。 <br><br>この関係が確立されると、パートナーはユーザーに代わってデバイスを登録するだけで、それ以上の操作は必要ありません。 詳細を確認する場合、またはパートナーに質問がある場合は、「デバイスを登録するパートナー向け [手順」を参照してください](register-devices-partner.md)。 デバイスが登録された後、イメージの [確認と](#check-the-image) ユーザーへのデバイスの [配信](#deliver-the-device) を続行できます。

## <a name="prepare-to-register-brand-new-devices"></a>新しいデバイスを登録する準備をする

新しいデバイスを手に入したら、次の手順を実行します。

1. [各デバイスのハードウェア ハッシュを取得します。](#obtain-the-hardware-hash)
2. [ハッシュ データを結合します](#merge-hash-data)。
3. [Microsoft Managed Desktop にデバイスを登録します](#register-devices-by-using-the-admin-portal)。
4. [画像が正しいか確認してください。](#check-the-image)
5. [デバイスを配信します](#deliver-the-device)。

### <a name="obtain-the-hardware-hash"></a>ハードウェア ハッシュの取得

Microsoft Managed Desktop は、ハードウェア ハッシュを参照することによって、各デバイスを一意に識別します。 この情報を取得するには、3 つのオプションがあります。

**ハードウェア ハッシュを取得するには、次の方法を実行します。**

- ハードウェア ハッシュを含む AutoPilot 登録ファイルを OEM サプライヤーに問い合わせ。
- 各デバイスWindows PowerShell[スクリプト](#powershell-script-method)を実行し、結果をファイルに収集します。
- 各デバイスを起動しますが、セットアップ エクスペリエンスを完了Windows、リムーバブル フラッシュ ドライブでハッシュ[を収集します](#flash-drive-method)。

#### <a name="powershell-script-method"></a>PowerShell スクリプト メソッド

PowerShell ギャラリー web [ サイトGet-WindowsAutoPilotInfo.ps1](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) PowerShell スクリプトを使用できます。 デバイス ID とハードウェア ハッシュの詳細については、「デバイスを [Autopilot に追加するWindows参照してください](/mem/autopilot/add-devices#device-identification)。

**Powershell スクリプト メソッドを使用するには、次のコマンドを実行します。**

1. 管理者権限を持つ PowerShell プロンプトを開きます。
2. `Install-Script -Name Get-WindowsAutoPilotInfo` を実行します。
3. `powershell -ExecutionPolicy Unrestricted Get-WindowsAutoPilotInfo -OutputFile <path>\hardwarehash.csv` を実行します。
4. 後続 `powershell -ExecutionPolicy restricted` の制限されていないスクリプトが実行されるのを防ぐために実行します。

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
9. USB ドライブを削除し、実行してデバイスをシャットダウンする `shutdown -s -t 0`

> [!IMPORTANT]
> 登録が完了するまで、登録するデバイスの電源を入れる必要はありません。

### <a name="merge-hash-data"></a>ハッシュ データの結合

登録を完了するには、CSV ファイル内のデータを 1 つのファイルに結合する必要があります。 簡単に行う PowerShell スクリプトの例を次に示します。

`Import-CSV -Path (Get-ChildItem -Filter *.csv) | ConvertTo-Csv -NoTypeInformation | % {$_.Replace('"', '')} | Out-File .\aggregatedDevices.csv`

> [!NOTE]
> 追加の列はサポートされていません。 引用符はサポートされていません。 ANSI 形式のテキスト ファイルのみを使用できます (Unicode は使用できません)。 ヘッダーでは大文字と小文字が区別されます。 これらの要件のために、Excelを編集して CSV ファイルとして保存すると、使用できるファイルは生成できません。 デバイスのシリアル番号の先頭のゼロは必ず保持してください。

### <a name="register-devices-by-using-the-admin-portal"></a>管理者ポータルを使用してデバイスを登録する

[[Microsoft エンドポイント マネージャー](https://endpoint.microsoft.com/)] で、左側 **のナビゲーション ウィンドウ** で [デバイス] を選択します。 [Microsoft Managed Desktop] セクションで、[デバイス] を **選択します**。 [Microsoft Managed Desktop Devices] ワークスペースで、[デバイス **の選択と** 登録] をクリックすると、新しいデバイスを登録するフライインが開きます。

<!-- [![Fly-in after selecting Register devices, listing devices with columns for assigned users, serial number, status, last-seen date, and age.](../../media/new-registration-ui.png)](../../media/new-registration-ui.png) -->

<!--Registering any existing devices with Managed Desktop will completely re-image them; make sure you've backed up any important data prior to starting the registration process.-->

**管理ポータルを使用してデバイスを登録するには、次のコマンドを実行します。**

1. [ **ファイルのアップロード]** で、前に作成した CSV ファイルへのパスを指定します。
2. ドロップダウン メニュー [でデバイス](../service-description/profiles.md) プロファイルを選択します。
3. [デバイス **の登録] を選択します**。 システムは、デバイスのリストにデバイスを追加します。登録保留として **マークされます**。 登録に要する時間は通常 10 分未満で、成功するとデバイスは Ready **for user** として表示され、ユーザーが使用を開始する準備ができていることを意味します。

> [!NOTE]
> デバイスの Azure Active Directory (AAD) グループ メンバーシップを手動で変更すると、デバイス プロファイルのグループに自動的に再割り当てされ、競合するグループから削除されます。

デバイス登録の進行状況は、メイン ページで監視できます。 報告される可能性がある状態は次のとおりです。

| 状態 | 説明 |
| -----|-----|
| 登録保留中 | 登録はまだ完了していません。 後で確認してください。 |
| 登録に失敗しました | 登録を完了できなかった。 詳細については、「デバイス登録の [トラブルシューティング」を参照してください](#troubleshooting-device-registration)。 |
| ユーザーの準備ができました | 登録が成功しました。 これで、デバイスをユーザーに配信する準備ができました。 Microsoft Managed Desktop では、初回セットアップをガイドしますので、それ以上の準備を行う必要はありません。 |
| Active | デバイスがユーザーに配信され、テナントに登録されています。 この状態は、デバイスを定期的に使用している場合も示します。 |
| 非アクティブ | デバイスがユーザーに配信され、テナントに登録されています。 ただし、最近 (過去 7 日間) デバイスを使用していない。  |

#### <a name="troubleshooting-device-registration"></a>デバイス登録のトラブルシューティング

| エラー メッセージ | 詳細 |
|-----| ----- |
| デバイスが見つかりません | 提供されている製造元、モデル、シリアル番号に一致するデバイスが見つからないので、このデバイスを登録できなかった。 これらの値をデバイスのサプライヤーに確認します。 |
| ハードウェア ハッシュが無効 | このデバイスに指定したハードウェア ハッシュが正しく書式設定されていません。 ハードウェア ハッシュを再確認してから、再送信します。 |
| デバイスが既に登録されている | このデバイスは既に組織に登録されています。 それ以上のアクションは必要ありません。 |
| 別の組織によって要求されたデバイス | このデバイスは、既に別の組織によって要求されています。 デバイスのサプライヤーに確認します。 |
| 予期しないエラーです | 要求を自動的に処理できなかった。 サポートに問い合わせ、要求 ID を入力します。 `<requestId>` |

### <a name="check-the-image"></a>画像を確認する

デバイスが Microsoft Managed Desktop パートナー サプライヤーから提供されている場合は、イメージが正しい必要があります。

必要に応じて、自分で画像を適用することもできます。 作業を開始するには、使用している Microsoft 担当者にお問い合わせください。 担当者が、画像を適用する場所と手順を提供します。

### <a name="autopilot-group-tag"></a>Autopilot グループ タグ

管理者ポータルを使用してデバイスを登録すると、[パートナー センターを使用してデバイスを登録する] に記載されているデバイス プロファイルに関連付けられた自動パイロット グループ タグが自動的に [割り当てされます](register-devices-partner.md)。
このサービスは、すべての Microsoft Managed Desktop デバイスを毎日監視し、グループ タグをまだ持ってないデバイスに割り当てします。

### <a name="deliver-the-device"></a>デバイスの配信

> [!IMPORTANT]
> デバイスをユーザーに渡す前に、そのユーザーに適切なライセンスを取得して [適用](../get-ready/prerequisites.md) してください。

すべてのライセンスが適用されている場合は、ユーザー [にデバイスを使用する準備を整えます](get-started-devices.md)。 次に、ユーザーはデバイスを起動し、セットアップ エクスペリエンスのWindows進みます。
