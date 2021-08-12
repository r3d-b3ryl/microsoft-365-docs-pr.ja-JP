---
title: Mac 上のエンドポイント用 Microsoft Defender の基本設定を設定する
description: エンタープライズ組織で MMicrosoft Defender for Endpoint on Mac を構成します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, management, preferences, enterprise, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 4c09d3a9caa59a8fb6f24f93fb0cb5883d4ca06ad19eaae40a9057f8ed5522de
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53800104"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a>macOS のエンドポイント用 Microsoft Defender の基本設定を設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [macOS 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
>この記事では、エンタープライズ組織の macOS で Microsoft Defender for Endpoint の基本設定を設定する方法について説明します。 コマンド ライン インターフェイスを使用して macOS 上の Microsoft Defender for Endpoint を構成するには、「Resources」を [参照してください](mac-resources.md#configuring-from-the-command-line)。

## <a name="summary"></a>概要

エンタープライズ組織では、macOS 上の Microsoft Defender for Endpoint を、いくつかの管理ツールのいずれかを使用して展開される構成プロファイルを介して管理できます。 セキュリティ運用チームによって管理される基本設定は、デバイス上でローカルに設定されている基本設定よりも優先されます。 構成プロファイルを使用して設定される基本設定を変更するには、エスカレートされた特権が必要であり、管理アクセス許可のないユーザーでは使用できません。

この記事では、構成プロファイルの構造、開始に使用できる推奨プロファイル、およびプロファイルの展開方法について説明します。

## <a name="configuration-profile-structure"></a>構成プロファイル構造

構成プロファイルは *.plist* ファイルで、キーによって識別されるエントリ (基本設定の名前を示す) で構成され、その後に、プリファレンスの性質に依存する値が続きます。 値は、単純な (数値など) か、入れ子になった基本設定リストなどの複雑な値を指定できます。

>[!CAUTION]
>構成プロファイルのレイアウトは、使用している管理コンソールによって異なります。 次のセクションでは、JAMF と Intune の構成プロファイルの例を示します。

構成プロファイルのトップ レベルには、製品全体の基本設定と、Microsoft Defender for Endpoint のサブエリアのエントリが含まれています。これは、次のセクションで詳しく説明します。

### <a name="antivirus-engine-preferences"></a>ウイルス対策エンジンの基本設定

構成 *プロファイルの antivirusEngine* セクションは、Microsoft Defender for Endpoint のウイルス対策コンポーネントの基本設定を管理するために使用されます。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|antivirusEngine|
|**データ型**|辞書 (入れ子になった基本設定)|
|**コメント**|辞書の内容の説明については、以下のセクションを参照してください。|

#### <a name="enable--disable-real-time-protection"></a>リアルタイム保護を有効/無効にする

アクセス時にファイルをスキャンするリアルタイム保護を有効にするかどうかを指定します。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|enableRealTimeProtection|
|**データ型**|Boolean|
|**指定可能な値**|true (既定) <p> false|

#### <a name="enable--disable-passive-mode"></a>パッシブ モードを有効/無効にする

ウイルス対策エンジンをパッシブ モードで実行するかどうかを指定します。 パッシブ モードには、次のような影響があります。

- リアルタイム保護がオフになっている
- オンデマンド スキャンが有効になっている
- 脅威の自動修復が無効になっている
- セキュリティ インテリジェンスの更新プログラムが有効になっている
- [状態] メニュー アイコンが非表示

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|passiveMode|
|**データ型**|Boolean|
|**指定可能な値**|false (既定) <p> true|
|**コメント**|Microsoft Defender for Endpoint version 100.67.60 以上で使用できます。|

#### <a name="exclusion-merge-policy"></a>除外マージ ポリシー

除外のマージ ポリシーを指定します。 これには、管理者定義の除外とユーザー定義の除外 ( ) の組み合わせ、または管理者定義の除外 ( ) のみを `merge` 組み合わせて指定できます `admin_only` 。 この設定は、ローカル ユーザーが独自の除外を定義するのを制限するために使用できます。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|exclusionsMergePolicy|
|**データ型**|String|
|**指定可能な値**|merge (既定) <p> admin_only|
|**コメント**|Microsoft Defender for Endpoint version 100.83.73 以上で使用できます。|

#### <a name="scan-exclusions"></a>スキャンの除外

スキャン対象から除外されるエンティティを指定します。 除外は、完全パス、拡張子、またはファイル名で指定できます。
(除外はアイテムの配列として指定されます。管理者は必要な数の要素を任意の順序で指定できます)。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|除外|
|**データ型**|辞書 (入れ子になった基本設定)|
|**コメント**|辞書の内容の説明については、以下のセクションを参照してください。|

##### <a name="type-of-exclusion"></a>除外の種類

種類別にスキャン対象から除外されるコンテンツを指定します。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|$type|
|**データ型**|String|
|**指定可能な値**|excludedPath <p> excludedFileExtension <p> excludedFileName|

##### <a name="path-to-excluded-content"></a>除外されたコンテンツへのパス

完全なファイル パスでスキャンされるコンテンツを除外するを指定します。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|path|
|**データ型**|String|
|**指定可能な値**|有効なパス|
|**コメント**|適用 *できるのは、$type**が excludedPath である場合のみです。*|

## <a name="supported-exclusion-types"></a>サポートされる除外の種類

次の表に、Defender for Endpoint on Mac でサポートされている除外の種類を示します。

除外|定義|例
---|---|---
ファイル拡張子|拡張子が付いたすべてのファイル(デバイス上の任意の場所)|`.test`
File|完全パスで識別される特定のファイル|`/var/log/test.log` <p> `/var/log/*.log` <p> `/var/log/install.?.log`
フォルダー|指定したフォルダーの下のすべてのファイル (再帰的)|`/var/log/` <p> `/var/*/`
プロセス|特定のプロセス (完全なパスまたはファイル名で指定) と、そのプロセスで開くすべてのファイル|`/bin/cat` <p> `cat` <p> `c?t`

> [!IMPORTANT]
> 正常に除外するには、上記のパスは、シンボリック リンクではなくハード リンクである必要があります。 パスがシンボリック リンクである場合は、実行して確認できます `file <path-name>` 。

ファイル、フォルダー、およびプロセスの除外は、次のワイルドカードをサポートします。

ワイルドカード|説明|例|一致|一致しない
---|---|---|---|---
\*|none を含む任意の数の文字と一致します (パス内でこのワイルドカードを使用すると、1 つのフォルダーのみを置き換える点に注意してください)|`/var/\*/\*.log`|`/var/log/system.log`|`/var/log/nested/system.log`
?|任意の 1 文字に一致する|`file?.log`|`file1.log` <p> `file2.log`|`file123.log`

##### <a name="path-type-file--directory"></a>パスの種類 (ファイル/ディレクトリ)

path プロパティが *ファイル* またはディレクトリを参照しているかどうかを示します。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|isDirectory|
|**データ型**|Boolean|
|**指定可能な値**|false (既定) <p> true|
|**コメント**|適用 *できるのは、$type**が excludedPath である場合のみです。*|

##### <a name="file-extension-excluded-from-the-scan"></a>スキャンから除外されたファイル拡張子

ファイル拡張子によるスキャン対象から除外されるコンテンツを指定します。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|拡張機能|
|**データ型**|String|
|**指定可能な値**|有効なファイル拡張子|
|**コメント**|適用 *できるのは* 、$type FileExtension が *除外されている場合のみです。*|

##### <a name="process-excluded-from-the-scan"></a>スキャンから除外されるプロセス

すべてのファイル アクティビティがスキャンから除外されるプロセスを指定します。 プロセスは、名前 (例: ) または完全 `cat` パス (例: ) で指定できます `/bin/cat` 。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|name|
|**データ型**|String|
|**指定可能な値**|任意の文字列|
|**コメント**|ファイルが excludedFileName *$type**場合にのみ適用されます。*|

#### <a name="allowed-threats"></a>許可される脅威

Defender for Endpoint on Mac でブロックされない脅威を名前で指定します。 これらの脅威の実行が許可されます。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|allowedThreats|
|**データ型**|文字列の配列|

#### <a name="disallowed-threat-actions"></a>禁止された脅威アクション

脅威が検出された場合にデバイスのローカル ユーザーが実行できるアクションを制限します。 この一覧に含まれるアクションは、ユーザー インターフェイスには表示されません。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|disallowedThreatActions|
|**データ型**|文字列の配列|
|**指定可能な値**|allow (ユーザーによる脅威の許可を制限する) <p> 復元 (検疫からの脅威の復元をユーザーに制限する)|
|**コメント**|Microsoft Defender for Endpoint version 100.83.73 以上で使用できます。|

#### <a name="threat-type-settings"></a>脅威の種類の設定

特定の脅威の種類を macOS 上の Microsoft Defender for Endpoint で処理する方法を指定します。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|threatTypeSettings|
|**データ型**|辞書 (入れ子になった基本設定)|
|**コメント**|辞書の内容の説明については、以下のセクションを参照してください。|

##### <a name="threat-type"></a>脅威の種類

脅威の種類を指定します。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|キー|
|**データ型**|String|
|**指定可能な値**|potentially_unwanted_application <p> archive_bomb|

##### <a name="action-to-take"></a>実行する操作

前のセクションで指定した種類の脅威が検出された場合に実行するアクションを指定します。 次のオプションから選択します。

- **監査**: デバイスは、この種類の脅威から保護されませんが、脅威に関するエントリがログに記録されます。
- **ブロック**: デバイスは、この種類の脅威から保護され、ユーザー インターフェイスとセキュリティ コンソールで通知されます。
- **オフ**: デバイスは、この種類の脅威から保護され、何もログに記録されません。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|値|
|**データ型**|String|
|**指定可能な値**|監査 (既定) <p> block <p> off|

#### <a name="threat-type-settings-merge-policy"></a>脅威の種類の設定の差し込みポリシー

脅威の種類の設定のマージ ポリシーを指定します。 これは、管理者定義設定とユーザー定義設定 ( ) の組み合わせか、管理者定義の設定 ( ) のみを `merge` 組み合わせて使用できます `admin_only` 。 この設定を使用すると、ローカル ユーザーがさまざまな脅威の種類に対して独自の設定を定義するのを制限できます。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|threatTypeSettingsMergePolicy|
|**データ型**|String|
|**指定可能な値**|merge (既定) <p> admin_only|
|**コメント**|Microsoft Defender for Endpoint version 100.83.73 以上で使用できます。|

#### <a name="antivirus-scan-history-retention-in-days"></a>ウイルス対策スキャン履歴の保持 (日数)

デバイスのスキャン履歴に結果が保持される日数を指定します。 古いスキャン結果は履歴から削除されます。 ディスクから削除された古い検疫済みファイル。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|scanResultsRetentionDays|
|**データ型**|String|
|**指定可能な値**|90 (既定)。 使用できる値は、1 日から 180 日です。|
|**コメント**|エンドポイント バージョン 101.07.23 以上の Microsoft Defender で使用できます。|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>ウイルス対策スキャン履歴内のアイテムの最大数

スキャン履歴に保持するエントリの最大数を指定します。 エントリには、過去に実行されたオンデマンド スキャンとすべてのウイルス対策検出が含まれます。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|scanHistoryMaximumItems|
|**データ型**|String|
|**指定可能な値**|10000 (既定値)。 許可される値は、5000 アイテムから 15,000 アイテムまでです。|
|**コメント**|エンドポイント バージョン 101.07.23 以上の Microsoft Defender で使用できます。|

### <a name="cloud-delivered-protection-preferences"></a>クラウドによる保護の基本設定

macOS 上の Microsoft Defender for Endpoint のクラウド駆動型保護機能を構成します。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|cloudService|
|**データ型**|辞書 (入れ子になった基本設定)|
|**コメント**|辞書の内容の説明については、以下のセクションを参照してください。|

#### <a name="enable--disable-cloud-delivered-protection"></a>クラウド配信の保護を有効または無効にする

デバイスのクラウド配信保護を有効にするかどうかを指定します。 サービスのセキュリティを向上させるために、この機能を有効にすることをお勧めします。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|enabled|
|**データ型**|Boolean|
|**指定可能な値**|true (既定) <p> false|

#### <a name="diagnostic-collection-level"></a>診断コレクション レベル

診断データは、Microsoft Defender for Endpoint を安全かつ最新の状態に保ち、問題を検出、診断、修正し、製品の改善を行う場合に使用されます。 この設定は、Microsoft Defender for Endpoint から Microsoft に送信される診断のレベルを決定します。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|diagnosticLevel|
|**データ型**|String|
|**指定可能な値**|省略可能 (既定) <p> 必須|

#### <a name="enable--disable-automatic-sample-submissions"></a>自動サンプル申請を有効または無効にする

疑わしいサンプル (脅威を含む可能性が高い) を Microsoft に送信するかどうかを決定します。 送信されたファイルに個人情報が含まれている可能性が高い場合は、メッセージが表示されます。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|automaticSampleSubmission|
|**データ型**|Boolean|
|**指定可能な値**|true (既定) <p> false|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>セキュリティ インテリジェンスの自動更新を有効または無効にする

セキュリティ インテリジェンスの更新プログラムが自動的にインストールされるかどうかを決定します。

|Section|値|
|:---|:---|
|**キー**|automaticDefinitionUpdateEnabled|
|**データ型**|Boolean|
|**指定可能な値**|true (既定) <p> false|

### <a name="user-interface-preferences"></a>ユーザー インターフェイスの基本設定

macOS 上の Microsoft Defender for Endpoint のユーザー インターフェイスの基本設定を管理します。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|userInterface|
|**データ型**|辞書 (入れ子になった基本設定)|
|**コメント**|辞書の内容の説明については、以下のセクションを参照してください。|

#### <a name="show--hide-status-menu-icon"></a>状態メニューアイコンの表示/非表示

画面の右上隅にある状態メニュー アイコンを表示または非表示にするかどうかを指定します。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|hideStatusMenuIcon|
|**データ型**|Boolean|
|**指定可能な値**|false (既定) <p> true|

#### <a name="show--hide-option-to-send-feedback"></a>フィードバックを送信するオプションを表示/非表示にする

にアクセスしてユーザーが Microsoft にフィードバックを送信できるかどうかを指定します `Help`  >  `Send Feedback` 。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|userInitiatedFeedback|
|**データ型**|String|
|**指定可能な値**|有効 (既定) <p> disabled|
|**コメント**|Microsoft Defender for Endpoint version 101.19.61 以上で使用できます。|

### <a name="endpoint-detection-and-response-preferences"></a>エンドポイントの検出と応答の基本設定

macOS 上の Microsoft Defender for Endpoint のエンドポイント検出および応答 (EDR) コンポーネントの基本設定を管理します。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|edr|
|**データ型**|辞書 (入れ子になった基本設定)|
|**コメント**|辞書の内容の説明については、以下のセクションを参照してください。|

#### <a name="device-tags"></a>デバイス タグ

タグ名とその値を指定します。

- GROUP タグは、デバイスに指定された値をタグ付けします。 タグは、デバイス ページの下のポータルに反映され、デバイスのフィルター処理とグループ化に使用できます。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|tags|
|**データ型**|辞書 (入れ子になった基本設定)|
|**コメント**|辞書の内容の説明については、以下のセクションを参照してください。|

##### <a name="type-of-tag"></a>タグの種類

タグの種類を指定します。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|キー|
|**データ型**|String|
|**指定可能な値**|`GROUP`|

##### <a name="value-of-tag"></a>タグの値

tag の値を指定します。

|Section|値|
|:---|:---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|値|
|**データ型**|String|
|**指定可能な値**|任意の文字列|

> [!IMPORTANT]
>
> - タグの種類ごとに設定できる値は 1 つのみです。
> - タグの種類は一意であり、同じ構成プロファイルで繰り返し使用する必要があります。

## <a name="recommended-configuration-profile"></a>推奨される構成プロファイル

開始するには、Microsoft Defender for Endpoint が提供するすべての保護機能を利用するために、企業の次の構成をお勧めします。

次の構成プロファイル (JAMF の場合は、カスタム設定構成プロファイルにアップロードできるプロパティ リスト) は次のようになります。

- リアルタイム保護を有効にする (RTP)
- 次の脅威の種類の処理方法を指定します。
  - **望ましくない可能性のあるアプリケーション (PUA) が** ブロックされる
  - **アーカイブボム** (圧縮率が高いファイル) が Microsoft Defender for Endpoint ログに監査される
- セキュリティ インテリジェンスの自動更新を有効にする
- クラウドによる保護の有効化
- サンプルの自動送信を有効にする

### <a name="property-list-for-jamf-configuration-profile"></a>JAMF 構成プロファイルのプロパティ 一覧

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Intune プロファイル

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
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
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a>完全な構成プロファイルの例

次のテンプレートには、このドキュメントで説明されているすべての設定のエントリが含まれています。macOS の Microsoft Defender for Endpoint を詳細に制御する高度なシナリオで使用できます。

### <a name="property-list-for-jamf-configuration-profile"></a>JAMF 構成プロファイルのプロパティ 一覧

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>maximumOnDemandScanThreads</key>
        <integer>1</integer>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/Users/*/git</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Intune プロファイル

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
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
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>maximumOnDemandScanThreads</key>
                    <integer>1</integer>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/Users/*/git</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a>プロパティ リストの検証

プロパティ リストは、有効な *.plist ファイルである必要* があります。 これを確認するには、次のコマンドを実行します。

```bash
plutil -lint com.microsoft.wdav.plist
```

```Output
com.microsoft.wdav.plist: OK
```

ファイルの形式が整っている場合、上記のコマンドは、 の終了 `OK` コードを出力して返します `0` 。 それ以外の場合は、問題を説明するエラーが表示され、コマンドは終了コードを返します `1` 。

## <a name="configuration-profile-deployment"></a>構成プロファイルの展開

エンタープライズの構成プロファイルを構築したら、企業が使用している管理コンソールを使用して展開できます。 以下のセクションでは、JAMF と Intune を使用してこのプロファイルを展開する方法について説明します。

### <a name="jamf-deployment"></a>JAMF の展開

JAMF コンソールで、[**コンピューター** 構成プロファイル] を開き、使用する構成プロファイルに移動し、[カスタム 構成プロファイル] を  >  設定。  優先ドメインとしてエントリ `com.microsoft.wdav` を作成し、前に作成した *.plist を* アップロードします。

> [!CAUTION]
> 正しい基本設定ドメイン ( ) を入力する必要があります。それ以外の場合、設定は `com.microsoft.wdav` Microsoft Defender for Endpoint によって認識されません。

### <a name="intune-deployment"></a>Intune の展開

1. [デバイス **構成**  >  **の管理] を開きます**。 [プロファイル **の**  >  **管理] [プロファイルの**  >  **作成] を選択します**。

2. プロファイルの名前を選択します。 **Platform=macOS をプロファイル****の種類=カスタム に変更します**。 [構成] を選択します。

3. 以前に作成した .plist を次のように保存します `com.microsoft.wdav.xml` 。

4. カスタム `com.microsoft.wdav` 構成プロファイル **名として入力します**。

5. 構成プロファイルを開き、ファイルを `com.microsoft.wdav.xml` アップロードします。 (このファイルは手順 3 で作成されました。

6. **[OK]** をクリックします。

7. [割 **り当**  >  **ての管理] を選択します**。 [含める **] タブ** で、[すべてのユーザーに割り当てる] & **を選択します**。

> [!CAUTION]
> 正しいカスタム構成プロファイル名を入力する必要があります。それ以外の場合、これらの基本設定は Microsoft Defender for Endpoint によって認識されません。

## <a name="resources"></a>リソース

- [プロファイル構成リファレンス (Apple 開発者向けドキュメント)](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
