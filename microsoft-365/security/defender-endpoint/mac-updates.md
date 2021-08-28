---
title: Microsoft Defender for Endpoint の更新プログラムを Mac に展開する
description: エンタープライズ環境での Microsoft Defender for Endpoint on Mac の更新プログラムを制御します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, updates, deploy
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dd299db1f8894851cb6d26d82756014b942c8240
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58573529"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a>macOS で Microsoft Defender for Endpoint の更新プログラムを展開する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [macOS 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft は、パフォーマンス、セキュリティ、および新機能の提供を行うソフトウェア更新プログラムを定期的に発行しています。

macOS のエンドポイント用 Microsoft Defender を更新するには、Microsoft AutoUpdate (MAU) という名前のプログラムが使用されます。 既定では、MAU は更新プログラムを毎日自動的にチェックしますが、毎週、月次、または手動に変更できます。

![MAU のスクリーンショット。](images/MDATP-34-MAU.png)

ソフトウェア配布ツールを使用して更新プログラムを展開する場合は、ソフトウェア更新プログラムを手動で確認する MAU を構成する必要があります。 組織の Mac の更新プログラムを MAU がチェックする方法と時間を構成する基本設定を展開できます。

## <a name="use-msupdate"></a>Msupdate の使用

MAU には *msupdate* と呼ばれるコマンド ライン ツールが含まれています。このツールは、IT 管理者向けに設計され、更新プログラムの適用時間を正確に制御できます。 このツールの使い方については、「msupdate を使用した更新プログラムOffice for Mac[を参照してください](/deployoffice/mac/update-office-for-mac-using-msupdate)。

MAU では、macOS 上のエンドポイント用 Microsoft Defender のアプリケーション識別子は *WDAV00 です*。 macOS の Microsoft Defender for Endpoint の最新の更新プログラムをダウンロードしてインストールするには、ターミナル ウィンドウから次のコマンドを実行します。

```dos
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a>Microsoft AutoUpdate の基本設定を設定する

このセクションでは、MAU の構成に使用できる最も一般的な基本設定について説明します。 これらの設定は、企業が使用している管理コンソールを介して構成プロファイルとして展開できます。 構成プロファイルの例を次のセクションに示します。

### <a name="set-the-channel-name"></a>チャネル名を設定する

チャネルは、MAU を通じて提供される更新プログラムの種類と頻度を決定します。 デバイスは `Beta` 、デバイスの前に新しい機能を試 `Preview` し `Current` 、.

チャネル `Current` には、製品の最も安定したバージョンが含まれている。

> [!IMPORTANT]
> Microsoft AutoUpdate バージョン 4.29 より前のチャネルの名前は異なります。
>
> - `Beta` という名前 `InsiderFast` が付けられた (Insider Fast)
> - `Preview` という名前 `External` が付けられた (Insider Slow)
> - `Current` という名前が付けられた `Production`

>[!TIP]
>新機能をプレビューし、早期のフィードバックを提供するには、企業内の一部のデバイスを構成するか、またはに構成をお `Beta` 勧めします `Preview` 。

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.autoupdate2`|
|**Key**|ChannelName|
|**データ型**|String|
|**指定可能な値**|ベータ版 <p> Preview <p> Current|
|||

>[!WARNING]
>この設定は、Microsoft AutoUpdate を通じて更新されるすべてのアプリケーションのチャネルを変更します。 macOS 上の Microsoft Defender for Endpoint のチャネルのみを変更するには、目的のチャネルに置き換えた後、次のコマンド `[channel-name]` を実行します。
>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender ATP.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a>更新チェックの頻度を設定する

MAU が更新プログラムを検索する頻度を変更します。

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.autoupdate2`|
|**Key**|UpdateCheckFrequency|
|**データ型**|整数|
|**既定値**|720 (分)|
|**コメント**|この値は分で設定されます。|

### <a name="change-how-mau-interacts-with-updates"></a>MAU と更新プログラムのやり取り方法を変更する

MAU が更新プログラムを検索する方法を変更します。

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.autoupdate2`|
|**Key**|HowToCheck|
|**データ型**|String|
|**指定可能な値**|Manual <p> AutomaticCheck <p> AutomaticDownload|
|**コメント**|AutomaticDownload はダウンロードを実行し、可能であればサイレント インストールします。|

### <a name="change-whether-the-check-for-updates-button-is-enabled"></a>[更新プログラムの確認] ボタンが有効になっているかどうかを変更する

ローカル ユーザーが Microsoft AutoUpdate ユーザー インターフェイスの [更新プログラムの確認] オプションをクリックできるかどうかを変更します。

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.autoupdate2`|
|**Key**|EnableCheckForUpdatesButton|
|**データ型**|Boolean|
|**指定可能な値**|True (既定) <p> 不正解|

### <a name="disable-insider-checkbox"></a>Insider チェック ボックスを無効にする

true に設定すると、"Insider Program.Office参加" になります。チェックボックスが使用できない/ユーザーにグレー表示されます。

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.autoupdate2`|
|**Key**|DisableInsiderCheckbox|
|**データ型**|Boolean|
|**指定可能な値**|False (既定) <p> 正解|

### <a name="limit-the-telemetry-that-is-sent-from-mau"></a>MAU から送信されるテレメトリを制限する

最小限のハートビート データ、アプリケーションの使用状況、および環境の詳細を送信するには、false に設定します。

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.autoupdate2`|
|**Key**|SendAllTelemetryEnabled|
|**データ型**|Boolean|
|**指定可能な値**|True (既定) <p> 不正解|

## <a name="example-configuration-profile"></a>構成プロファイルの例

次の構成プロファイルを使用して、次の構成プロファイルを使用します。

- デバイスを実稼働チャネルに配置する
- 更新プログラムを自動的にダウンロードしてインストールする
- ユーザー インターフェイスで [更新プログラムの確認] ボタンを有効にする
- デバイス上のユーザーが Insider チャネルに登録を許可する

> [!WARNING]
> 次の構成は構成の例であり、設定の適切な確認と構成の調整なしに実稼働環境で使用する必要があります。

> [!TIP]
> 新機能をプレビューし、早期のフィードバックを提供するには、企業内の一部のデバイスを構成するか、またはに構成をお `Beta` 勧めします `Preview` 。

### <a name="jamf"></a>JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>ChannelName</key>
    <string>Production</string>
    <key>HowToCheck</key>
    <string>AutomaticDownload</string>
    <key>EnableCheckForUpdatesButton</key>
    <true/>
    <key>DisableInsiderCheckbox</key>
    <false/>
    <key>SendAllTelemetryEnabled</key>
    <true/>
</dict>
</plist>
```

### <a name="intune"></a>Intune

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>B762FF60-6ACB-4A72-9E72-459D00C936F3</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.autoupdate2</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft AutoUpdate settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft AutoUpdate configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
            <key>PayloadUUID</key>
            <string>5A6F350A-CC2C-440B-A074-68E3F34EBAE9</string>
            <key>PayloadType</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadOrganization</key>
            <string>Microsoft</string>
            <key>PayloadIdentifier</key>
            <string>com.microsoft.autoupdate2</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft AutoUpdate configuration settings</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>ChannelName</key>
            <string>Production</string>
            <key>HowToCheck</key>
            <string>AutomaticDownload</string>
            <key>EnableCheckForUpdatesButton</key>
            <true/>
            <key>DisableInsiderCheckbox</key>
            <false/>
            <key>SendAllTelemetryEnabled</key>
            <true/>
            </dict>
        </array>
    </dict>
</plist>
```

MAU を構成するには、企業が使用している管理ツールからこの構成プロファイルを展開できます。

- JAMF から、この構成プロファイルをアップロードし、Preference ドメインを *com.microsoft.autoupdate2 に設定します*。
- Intune から、この構成プロファイルをアップロードし、カスタム構成プロファイル名を *com.microsoft.autoupdate2 に設定します*。

## <a name="resources"></a>リソース

- [msupdate リファレンス](/deployoffice/mac/update-office-for-mac-using-msupdate)
