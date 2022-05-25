---
title: Mac で Microsoft Defender for Endpoint の更新プログラムを展開する
description: エンタープライズ環境で Mac 上のMicrosoft Defender for Endpointの更新プログラムを制御します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, updates, deploy
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4612c7ca68ab0b55fa2a2f28821cb5baef6ff6e9
ms.sourcegitcommit: 6c2ab5e8efe74d0dc2df610e2d9d2fdda8aaf074
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65669344"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-macos"></a>macOSにMicrosoft Defender for Endpointの更新プログラムをデプロイする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [macOS 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft は、パフォーマンス、セキュリティ、新機能を提供するために、ソフトウェア更新プログラムを定期的に発行しています。

macOSでMicrosoft Defender for Endpointを更新するには、Microsoft AutoUpdate (MAU) という名前のプログラムが使用されます。 既定では、MAU は毎日更新プログラムを自動的にチェックしますが、毎週、毎月、または手動で変更できます。

:::image type="content" source="images/MDATP-34-MAU.png" alt-text="マウ" lightbox="images/MDATP-34-MAU.png":::

ソフトウェア配布ツールを使用して更新プログラムを展開する場合は、ソフトウェア更新プログラムを手動で確認するように MAU を構成する必要があります。 基本設定を展開して、MAU が組織内の Mac の更新プログラムを確認する方法とタイミングを構成できます。

## <a name="use-msupdate"></a>Msupdate の使用

MAU には *msupdate* と呼ばれるコマンド ライン ツールが含まれています。このツールは IT 管理者向けに設計されており、更新プログラムの適用時期をより正確に制御できます。 このツールの使用方法については、[msupdate を使用した update Office for Macを参照](/deployoffice/mac/update-office-for-mac-using-msupdate)してください。

MAU では、macOS上のMicrosoft Defender for Endpointのアプリケーション識別子は *WDAV00 です*。 macOSでMicrosoft Defender for Endpointの最新の更新プログラムをダウンロードしてインストールするには、ターミナル ウィンドウから次のコマンドを実行します。

```dos
cd /Library/Application\ Support/Microsoft/MAU2.0/Microsoft\ AutoUpdate.app/Contents/MacOS
./msupdate --install --apps wdav00
```

## <a name="set-preferences-for-microsoft-autoupdate"></a>Microsoft AutoUpdate の基本設定を設定する

このセクションでは、MAU の構成に使用できる最も一般的な設定について説明します。 これらの設定は、企業が使用している管理コンソールを使用して構成プロファイルとして展開できます。 次のセクションでは、構成プロファイルの例を示します。

### <a name="set-the-channel-name"></a>チャネル名を設定する

チャネルは、MAU を通じて提供される更新プログラムの種類と頻度を決定します。 デバイスの前に`Beta`新しい機能`Preview`を試すことができます。`Current`

`Current`チャネルには、製品の最も安定したバージョンが含まれています。

> [!IMPORTANT]
> Microsoft AutoUpdate バージョン 4.29 より前のチャネルの名前は異なります。
>
> - `Beta` という名前 `InsiderFast` (Insider Fast)
> - `Preview` という名前 `External` (Insider Slow)
> - `Current` という名前が付けられていた `Production`

> [!TIP]
> 新しい機能をプレビューし、早期のフィードバックを提供するには、企業 `Beta` 内の一部のデバイスを構成するか、または `Preview`構成することをお勧めします。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.autoupdate2`|
|**キー**|ChannelName|
|**データ型**|String|
|**指定可能な値**|ベータ版 <p> プレビュー <p> Current|
|||

> [!WARNING]
> この設定は、Microsoft AutoUpdate を通じて更新されるすべてのアプリケーションのチャネルを変更します。 macOSのMicrosoft Defender for Endpointに対してのみチャネルを変更するには、目的のチャネルに置き換えた後、次のコマンドを`[channel-name]`実行します。
>
> ```bash
> defaults write com.microsoft.autoupdate2 Applications -dict-add "/Applications/Microsoft Defender.app" " { 'Application ID' = 'WDAV00' ; 'App Domain' = 'com.microsoft.wdav' ; LCID = 1033 ; ChannelName = '[channel-name]' ; }"
> ```

### <a name="set-update-check-frequency"></a>更新チェック頻度を設定する

MAU が更新プログラムを検索する頻度を変更します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.autoupdate2`|
|**キー**|UpdateCheckFrequency|
|**データ型**|整数|
|**既定値**|720 (分)|
|**コメント**|この値は分単位で設定されます。|
|||

### <a name="change-how-mau-interacts-with-updates"></a>MAU が更新プログラムと対話する方法を変更する

MAU で更新プログラムを検索する方法を変更します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.autoupdate2`|
|**キー**|HowToCheck|
|**データ型**|String|
|**指定可能な値**|Manual <p> AutomaticCheck <p> AutomaticDownload|
|**コメント**|AutomaticDownload はダウンロードを行い、可能であればサイレント インストールされることに注意してください。|
|||

### <a name="change-whether-the-check-for-updates-button-is-enabled"></a>[更新プログラムの確認] ボタンが有効になっているかどうかを変更する

ローカル ユーザーが Microsoft AutoUpdate ユーザー インターフェイスで [更新プログラムの確認] オプションをクリックできるかどうかを変更します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.autoupdate2`|
|**キー**|EnableCheckForUpdatesButton|
|**データ型**|Boolean|
|**指定可能な値**|True (既定値) <p> いいえ|
|||

### <a name="disable-insider-checkbox"></a>[Insider を無効にする] チェック ボックス

true に設定すると、"Office Insider Program.. に参加できます。チェックボックスは使用不可/ユーザーに灰色表示されます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.autoupdate2`|
|**キー**|DisableInsiderCheckbox|
|**データ型**|Boolean|
|**指定可能な値**|False (既定値) <p> はい|
|||

### <a name="limit-the-telemetry-that-is-sent-from-mau"></a>MAU から送信されるテレメトリを制限する

最小限のハートビート データ、アプリケーションの使用状況、および環境の詳細を送信しない場合は false に設定します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.autoupdate2`|
|**キー**|SendAllTelemetryEnabled|
|**データ型**|Boolean|
|**指定可能な値**|True (既定値) <p> いいえ|
|||

## <a name="example-configuration-profile"></a>構成プロファイルの例

次の構成プロファイルを使用します。

- デバイスを運用チャネルに配置する
- 更新プログラムを自動的にダウンロードしてインストールする
- ユーザー インターフェイスで [更新プログラムの確認] ボタンを有効にする
- デバイス上のユーザーが Insider チャネルに登録できるようにする

> [!WARNING]
> 次の構成は構成の例であり、設定を適切に確認し、構成を調整せずに運用環境で使用しないでください。

> [!TIP]
> 新しい機能をプレビューし、早期のフィードバックを提供するには、企業 `Beta` 内の一部のデバイスを構成するか、または `Preview`構成することをお勧めします。

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

MAU を構成するには、企業が使用している管理ツールからこの構成プロファイルをデプロイできます。

- JAMF から、この構成プロファイルをアップロードし、基本設定ドメインを *com.microsoft.autoupdate2* に設定します。
- Intuneから、この構成プロファイルをアップロードし、カスタム構成プロファイル名を *com.microsoft.autoupdate2* に設定します。

## <a name="resources"></a>リソース

- [msupdate リファレンス](/deployoffice/mac/update-office-for-mac-using-msupdate)
