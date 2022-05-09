---
title: Mac でMicrosoft Defender for Endpointの環境設定を設定する
description: エンタープライズ組織で Mac でMicrosoft Defender for Endpointを構成します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, 管理, 環境設定, エンタープライズ, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: cb3f38b861f85849165be330e03fe1d96a9c708c
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63326707"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a>macOS 上で Microsoft Defender for Endpoint 用の基本設定を設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [macOS 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!IMPORTANT]
> この記事では、エンタープライズ組織の macOS でMicrosoft Defender for Endpointの基本設定を設定する方法について説明します。 コマンド ライン インターフェイスを使用して macOS でMicrosoft Defender for Endpointを構成するには、「[リソース](mac-resources.md#configuring-from-the-command-line)」を参照してください。

## <a name="summary"></a>概要

エンタープライズ組織では、macOS 上のMicrosoft Defender for Endpointは、いくつかの管理ツールのいずれかを使用して展開される構成プロファイルを使用して管理できます。 セキュリティ運用チームによって管理される基本設定は、デバイス上でローカルに設定されている基本設定よりも優先されます。 構成プロファイルを使用して設定される基本設定を変更するには、エスカレートされた特権が必要であり、管理者アクセス許可のないユーザーは使用できません。

この記事では、構成プロファイルの構造について説明し、使用できる推奨プロファイルを含め、プロファイルを展開する方法について説明します。

## <a name="configuration-profile-structure"></a>構成プロファイル構造

構成プロファイルは *.plist* ファイルであり、キーによって識別されるエントリ (基本設定の名前を示します)、値が続き、基本設定の性質に依存します。 値には、単純な値 (数値など) または複雑な値を指定できます (設定の入れ子になったリストなど)。

> [!CAUTION]
>構成プロファイルのレイアウトは、使用している管理コンソールによって異なります。 次のセクションでは、JAMF とIntuneの構成プロファイルの例を示します。

構成プロファイルの最上位レベルには、製品全体の基本設定とMicrosoft Defender for Endpointのサブエリアのエントリが含まれています。これについては、次のセクションで詳しく説明します。

### <a name="antivirus-engine-preferences"></a>ウイルス対策エンジンの基本設定

構成プロファイルの *antivirusEngine* セクションは、Microsoft Defender for Endpointのウイルス対策コンポーネントの基本設定を管理するために使用されます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|antivirusEngine|
|**データ型**|ディクショナリ (入れ子になった設定)|
|**Comments**|ディクショナリの内容の説明については、次のセクションを参照してください。|
|||

#### <a name="enforcement-level-for-antivirus-engine"></a>ウイルス対策エンジンの適用レベル

ウイルス対策エンジンの適用設定を指定します。 適用レベルを設定する場合は、次の 3 つの値があります。

- リアルタイム (`real_time`): リアルタイム保護 (アクセス時にファイルをスキャン) が有効になっています。
- オンデマンド (`on_demand`): ファイルはオンデマンドでのみスキャンされます。 この場合:
  - リアルタイム保護はオフになっています。
- パッシブ (`passive`): パッシブ モードでウイルス対策エンジンを実行します。 この場合:
  - リアルタイム保護はオフになっています。
  - オンデマンド スキャンがオンになっている。
  - 脅威の自動修復はオフになっています。
  - セキュリティ インテリジェンスの更新プログラムがオンになっています。
  - [状態] メニュー アイコンは非表示です。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|enforcementLevel|
|**データ型**|String|
|**指定可能な値**|real_time (既定) <p> on_demand <p> パッシブ|
|**コメント**|Microsoft Defender for Endpoint バージョン 101.10.72 以降で使用できます。|
|||

#### <a name="run-a-scan-after-definitions-are-updated"></a>定義が更新された後にスキャンを実行する

デバイスに新しいセキュリティ インテリジェンス更新プログラムがダウンロードされた後にプロセス スキャンを開始するかどうかを指定します。 この設定を有効にすると、デバイスの実行中のプロセスでウイルス対策スキャンがトリガーされます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|scanAfterDefinitionUpdate|
|**データ型**|Boolean|
|**指定可能な値**|true (既定値) <p> false|
|**コメント**|Microsoft Defender for Endpoint バージョン 101.41.10 以降で使用できます。|
|||

#### <a name="scan-archives-on-demand-antivirus-scans-only"></a>スキャン アーカイブ (オンデマンドウイルス対策スキャンのみ)

オンデマンドウイルス対策スキャン中にアーカイブをスキャンするかどうかを指定します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|scanArchives|
|**データ型**|Boolean|
|**指定可能な値**|true (既定値) <p> false|
|**コメント**|Microsoft Defender for Endpoint バージョン 101.41.10 以降で使用できます。|
|||

#### <a name="degree-of-parallelism-for-on-demand-scans"></a>オンデマンド スキャンの並列処理の程度

オンデマンド スキャンの並列処理の度合いを指定します。 これは、スキャンの実行に使用されるスレッドの数に対応し、CPU 使用率とオンデマンド スキャンの期間に影響します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|maximumOnDemandScanThreads|
|**データ型**|整数|
|**指定可能な値**|2 (既定値)。 使用できる値は、1 から 64 までの整数です。|
|**コメント**|Microsoft Defender for Endpoint バージョン 101.41.10 以降で使用できます。|
|||

#### <a name="exclusion-merge-policy"></a>除外マージ ポリシー

除外するマージ ポリシーを指定します。 これは、管理者定義の除外とユーザー定義の除外 ()、または管理者定義の除外 (`merge``admin_only`) のみを組み合わせて使用できます。 この設定を使用すると、ローカル ユーザーが独自の除外を定義できないように制限できます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|exclusionsMergePolicy|
|**データ型**|String|
|**指定可能な値**|merge (既定値) <p> admin_only|
|**コメント**|Microsoft Defender for Endpoint バージョン 100.83.73 以降で使用できます。|
|||

#### <a name="scan-exclusions"></a>除外をスキャンする

スキャン対象から除外されたエンティティを指定します。 除外は、完全なパス、拡張子、またはファイル名で指定できます。
(除外は項目の配列として指定され、管理者は必要な数の要素を任意の順序で指定できます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|除外|
|**データ型**|ディクショナリ (入れ子になった設定)|
|**コメント**|ディクショナリの内容の説明については、次のセクションを参照してください。|
|||

##### <a name="type-of-exclusion"></a>除外の種類

種類別にスキャンから除外されるコンテンツを指定します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|$type|
|**データ型**|String|
|**指定可能な値**|excludedPath <p> excludedFileExtension <p> excludedFileName|
|||

##### <a name="path-to-excluded-content"></a>除外されたコンテンツへのパス

完全なファイル パスでスキャンから除外されるコンテンツを指定します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|パス|
|**データ型**|String|
|**指定可能な値**|有効なパス|
|**Comments**|*$type**が excludedPath* の場合にのみ適用されます|
|||

## <a name="supported-exclusion-types"></a>サポートされている除外の種類

次の表は、Defender for Endpoint on Mac でサポートされている除外の種類を示しています。

<br>

****

|除外|定義|例|
|---|---|---|
|ファイル拡張子|拡張機能を持つすべてのファイル(デバイス上の任意の場所)|`.test`|
|ファイル|完全パスで識別される特定のファイル|`/var/log/test.log` <p> `/var/log/*.log` <p> `/var/log/install.?.log`|
|フォルダー|指定したフォルダーの下にあるすべてのファイル (再帰的)|`/var/log/` <p> `/var/*/`|
|プロセス|特定のプロセス (完全なパスまたはファイル名で指定) とそのプロセスによって開かれたすべてのファイル|`/bin/cat` <p> `cat` <p> `c?t`|
||||

> [!IMPORTANT]
> 正しく除外するには、上記のパスはシンボリック リンクではなくハード リンクである必要があります。 パスがシンボリック リンクであるかどうかを確認するには、次を実行します `file <path-name>`。

ファイル、フォルダー、およびプロセスの除外では、次のワイルドカードがサポートされます。

<br>

****

|ワイルドカード|説明|例|一致|一致しない|
|---|---|---|---|---|
|\*|none を含む任意の数の文字と一致します (パス内でこのワイルドカードを使用すると、フォルダーは 1 つのみ置き換えられます)|`/var/\*/\*.log`|`/var/log/system.log`|`/var/log/nested/system.log`|
|?|任意の 1 文字に一致します|`file?.log`|`file1.log` <p> `file2.log`|`file123.log`|
||||||

### <a name="path-type-file--directory"></a>パスの種類 (ファイル/ディレクトリ)

*path* プロパティがファイルまたはディレクトリを参照しているかどうかを示します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|isDirectory|
|**データ型**|Boolean|
|**指定可能な値**|false (既定) <p> true|
|**コメント**|*$type**が excludedPath* の場合にのみ適用されます|
|||

### <a name="file-extension-excluded-from-the-scan"></a>スキャンから除外されたファイル拡張子

ファイル拡張子によるスキャンから除外されるコンテンツを指定します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|拡張子|
|**データ型**|String|
|**指定可能な値**|有効なファイル拡張子|
|**コメント**|*$type**が除外されている場合にのみ適用されるFileExtension*|
|||

### <a name="process-excluded-from-the-scan"></a>スキャンから除外されたプロセス

すべてのファイル アクティビティをスキャンから除外するプロセスを指定します。 プロセスは、その名前 (たとえば、 `cat`) または完全パス (例: `/bin/cat`) で指定できます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|name|
|**データ型**|String|
|**指定可能な値**|任意の文字列|
|**コメント**|*$type**が excludedFileName* の場合にのみ適用されます|
|||

#### <a name="allowed-threats"></a>許可される脅威

Defender for Endpoint on Mac によってブロックされない脅威を名前で指定します。 これらの脅威の実行が許可されます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|allowedThreats|
|**データ型**|文字列の配列|
|||

#### <a name="disallowed-threat-actions"></a>許可されていない脅威アクション

脅威が検出されたときにデバイスのローカル ユーザーが実行できるアクションを制限します。 この一覧に含まれるアクションは、ユーザー インターフェイスには表示されません。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|disallowedThreatActions|
|**データ型**|文字列の配列|
|**指定可能な値**|allow (ユーザーによる脅威の許可を制限) <p> restore (ユーザーが検疫からの脅威を復元できないように制限)|
|**コメント**|Microsoft Defender for Endpoint バージョン 100.83.73 以降で使用できます。|
|||

#### <a name="threat-type-settings"></a>脅威の種類の設定

macOS 上のMicrosoft Defender for Endpointによって特定の脅威の種類を処理する方法を指定します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|threatTypeSettings|
|**データ型**|ディクショナリ (入れ子になった設定)|
|**コメント**|ディクショナリの内容の説明については、次のセクションを参照してください。|
|||

##### <a name="threat-type"></a>脅威の種類

脅威の種類を指定します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|キー|
|**データ型**|String|
|**指定可能な値**|potentially_unwanted_application <p> archive_bomb|
|||

##### <a name="action-to-take"></a>実行する操作

前のセクションで指定した種類の脅威が検出された場合に実行するアクションを指定します。 次のオプションから選択します。

- **監査**: デバイスはこの種類の脅威から保護されていませんが、脅威に関するエントリがログに記録されます。
- **ブロック**: デバイスはこの種類の脅威から保護され、ユーザー インターフェイスとセキュリティ コンソールで通知されます。
- **オフ**: デバイスはこの種類の脅威から保護されておらず、何もログに記録されません。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|値|
|**データ型**|String|
|**指定可能な値**|監査 (既定) <p> ブロック <p> オフ|
|||

#### <a name="threat-type-settings-merge-policy"></a>脅威の種類の設定のマージ ポリシー

脅威の種類の設定にマージ ポリシーを指定します。 これは、管理者が定義した設定とユーザー定義の設定 (`merge`) の組み合わせか、管理者が定義した設定 (`admin_only`) のみを使用できます。 この設定を使用すると、ローカル ユーザーがさまざまな脅威の種類に対して独自の設定を定義できないように制限できます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|threatTypeSettingsMergePolicy|
|**データ型**|String|
|**指定可能な値**|merge (既定値) <p> admin_only|
|**コメント**|Microsoft Defender for Endpoint バージョン 100.83.73 以降で使用できます。|
|||

#### <a name="antivirus-scan-history-retention-in-days"></a>ウイルス対策スキャン履歴の保持期間 (日数)

デバイスのスキャン履歴に結果が保持される日数を指定します。 古いスキャン結果は履歴から削除されます。 ディスクからも削除された古い検疫済みファイル。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|scanResultsRetentionDays|
|**データ型**|String|
|**指定可能な値**|90 (既定値)。 使用できる値は 1 日から 180 日です。|
|**コメント**|Microsoft Defender for Endpoint バージョン 101.07.23 以降で使用できます。|
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>ウイルス対策スキャン履歴内のアイテムの最大数

スキャン履歴に保持するエントリの最大数を指定します。 エントリには、過去に実行されたすべてのオンデマンド スキャンとすべてのウイルス対策検出が含まれます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|scanHistoryMaximumItems|
|**データ型**|String|
|**指定可能な値**|10000 (既定値)。 使用できる値は、5,000 項目から 15,000 項目です。|
|**コメント**|Microsoft Defender for Endpoint バージョン 101.07.23 以降で使用できます。|
|||

### <a name="cloud-delivered-protection-preferences"></a>クラウド配信の保護の基本設定

macOS でMicrosoft Defender for Endpointのクラウド駆動型保護機能を構成します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|cloudService|
|**データ型**|ディクショナリ (入れ子になった設定)|
|**コメント**|ディクショナリの内容の説明については、次のセクションを参照してください。|
|||

#### <a name="enable--disable-cloud-delivered-protection"></a>クラウド配信保護を有効または無効にする

デバイスのクラウド配信保護を有効にするかどうかを指定します。 サービスのセキュリティを向上させるために、この機能をオンにしておくことをお勧めします。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|enabled|
|**データ型**|Boolean|
|**指定可能な値**|true (既定値) <p> false|
|||

#### <a name="diagnostic-collection-level"></a>診断収集のレベル

診断データは、Microsoft Defender for Endpointセキュリティと最新の状態を維持し、問題を検出、診断、修正し、製品の改善にも使用されます。 この設定は、Microsoft Defender for Endpointから Microsoft に送信される診断のレベルを決定します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|diagnosticLevel|
|**データ型**|String|
|**指定可能な値**|省略可能 (既定値) <p> 必須出席者|
|||

#### <a name="enable--disable-automatic-sample-submissions"></a>サンプルの自動送信を有効または無効にする

疑わしいサンプル (脅威を含む可能性が高い) を Microsoft に送信するかどうかを決定します。 送信されたファイルに個人情報が含まれている可能性が高い場合は、メッセージが表示されます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|automaticSampleSubmission|
|**データ型**|Boolean|
|**指定可能な値**|true (既定値) <p> false|
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>セキュリティ インテリジェンスの自動更新を有効または無効にする

セキュリティ インテリジェンス更新プログラムを自動的にインストールするかどうかを決定します。

<br>

****

|Section|値|
|---|---|
|**キー**|automaticDefinitionUpdateEnabled|
|**データ型**|Boolean|
|**指定可能な値**|true (既定値) <p> false|
|||

### <a name="user-interface-preferences"></a>ユーザー インターフェイスの基本設定

macOS でMicrosoft Defender for Endpointのユーザー インターフェイスの基本設定を管理します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|userInterface|
|**データ型**|ディクショナリ (入れ子になった設定)|
|**コメント**|ディクショナリの内容の説明については、次のセクションを参照してください。|
|||

#### <a name="show--hide-status-menu-icon"></a>[状態] メニュー アイコンを表示/非表示にする

画面の右上隅にある状態メニュー アイコンを表示または非表示にするかどうかを指定します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|hideStatusMenuIcon|
|**データ型**|Boolean|
|**指定可能な値**|false (既定) <p> true|
|||

#### <a name="show--hide-option-to-send-feedback"></a>フィードバックを送信するオプションを表示/非表示にする

に移動 `Help` > `Send Feedback`して、ユーザーが Microsoft にフィードバックを送信できるかどうかを指定します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|userInitiatedFeedback|
|**データ型**|String|
|**指定可能な値**|有効 (既定) <p> 無効|
|**コメント**|Microsoft Defender for Endpoint バージョン 101.19.61 以降で使用できます。|
|||



#### <a name="control-sign-in-to-consumer-version-of-microsoft-defender"></a>コンシューマー バージョンの Microsoft Defender へのサインインを制御する

ユーザーがコンシューマー バージョンの Microsoft Defender にサインインできるかどうかを指定します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|consumerExperience|
|**データ型**|String|
|**指定可能な値**|有効 (既定) <p> 無効|
|**Comments**|Microsoft Defender for Endpoint バージョン 101.60.18 以降で使用できます。|
|||


### <a name="endpoint-detection-and-response-preferences"></a>エンドポイントの検出と応答の基本設定

macOS でMicrosoft Defender for Endpointのエンドポイントでの検出と対応 (EDR) コンポーネントの基本設定を管理します。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|Edr|
|**データ型**|ディクショナリ (入れ子になった設定)|
|**Comments**|ディクショナリの内容の説明については、次のセクションを参照してください。|
|||

#### <a name="device-tags"></a>デバイス タグ

タグ名とその値を指定します。

- GROUP タグは、指定した値でデバイスにタグを付けます。 タグは、デバイス ページのポータルに反映され、デバイスのフィルター処理とグループ化に使用できます。

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|tags|
|**データ型**|ディクショナリ (入れ子になった設定)|
|**コメント**|ディクショナリの内容の説明については、次のセクションを参照してください。|
|||

##### <a name="type-of-tag"></a>タグの種類

タグの種類を指定します

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|キー|
|**データ型**|String|
|**指定可能な値**|`GROUP`|
|||

##### <a name="value-of-tag"></a>タグの値

タグの値を指定します

<br>

****

|Section|値|
|---|---|
|**ドメイン**|`com.microsoft.wdav`|
|**キー**|値|
|**データ型**|String|
|**指定可能な値**|任意の文字列|
|||

> [!IMPORTANT]
>
> - タグの種類ごとに 1 つの値のみを設定できます。
> - タグの種類は一意であり、同じ構成プロファイルで繰り返し使用しないでください。

## <a name="recommended-configuration-profile"></a>推奨される構成プロファイル

開始するには、企業が提供するすべての保護機能を利用するために、次の構成Microsoft Defender for Endpoint推奨します。

次の構成プロファイル (または JAMF の場合は、カスタム設定構成プロファイルにアップロードできるプロパティ リスト) は次のようになります。

- リアルタイム保護 (RTP) を有効にする
- 次の脅威の種類を処理する方法を指定します。
  - **望ましくない可能性があるアプリケーション (PUA)** がブロックされる
  - **アーカイブ ボム** (圧縮率が高いファイル) は、Microsoft Defender for Endpoint ログに対して監査されます
- セキュリティ インテリジェンスの自動更新を有効にする
- クラウドによる保護の有効化
- サンプルの自動送信を有効にする

### <a name="property-list-for-jamf-recommended-configuration-profile"></a>JAMF 推奨構成プロファイルのプロパティ 一覧

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enforcementLevel</key>
        <string>real_time</string>
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

### <a name="intune-recommended-profile"></a>推奨プロファイルIntune

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
                    <key>enforcementLevel</key>
                    <string>real_time</string>
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

次のテンプレートには、このドキュメントで説明されているすべての設定のエントリが含まれており、macOS でMicrosoft Defender for Endpointをより詳細に制御するより高度なシナリオに使用できます。

### <a name="property-list-for-jamf-full-configuration-profile"></a>JAMF 完全構成プロファイルのプロパティ 一覧

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enforcementLevel</key>
        <string>real_time</string>
        <key>scanAfterDefinitionUpdate</key>
        <true/>
        <key>scanArchives</key>
        <true/>
        <key>maximumOnDemandScanThreads</key>
        <integer>2</integer>
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

### <a name="intune-full-profile"></a>完全なプロファイルIntuneする

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
                    <key>enforcementLevel</key>
                    <string>real_time</string>
                    <key>scanAfterDefinitionUpdate</key>
                    <true/>
                    <key>scanArchives</key>
                    <true/>
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
    </dict>
</plist>
```

## <a name="property-list-validation"></a>プロパティ リストの検証

プロパティ リストは、有効な *.plist* ファイルである必要があります。 これは、次のコマンドを実行して確認できます。

```bash
plutil -lint com.microsoft.wdav.plist
```

```Output
com.microsoft.wdav.plist: OK
```

ファイルが整形式の場合は、上記のコマンドが出力 `OK` され、終了コード `0`. それ以外の場合は、問題を説明するエラーが表示され、コマンドは終了コード `1`.

## <a name="configuration-profile-deployment"></a>構成プロファイルの展開

エンタープライズの構成プロファイルを構築したら、エンタープライズが使用している管理コンソールを使用して展開できます。 次のセクションでは、JAMF とIntuneを使用してこのプロファイルをデプロイする方法について説明します。

### <a name="jamf-deployment"></a>JAMF デプロイ

JAMF コンソールで **[コンピューター** \> **構成プロファイル]** を開き、使用する構成プロファイルに移動し、[**カスタム 設定**] を選択します。 基本設定ドメインとしてエントリ `com.microsoft.wdav` を作成し、前に生成した *.plist を* アップロードします。

> [!CAUTION]
> 適切な基本設定ドメイン (`com.microsoft.wdav`)を入力する必要があります。それ以外の場合、基本設定はMicrosoft Defender for Endpointによって認識されません。

### <a name="intune-deployment"></a>Intuneデプロイ

1. デバイス **構成の管理** \> **を** 開きます。 [**プロファイルの****管理**\>] **の [プロファイル** の\>作成] を選択します。

2. プロファイルの名前を選択します。 **Platform=macOS** を **プロファイルの種類=カスタム** に変更します。 [構成] を選択します。

3. 前に生成した .plist を .plist として `com.microsoft.wdav.xml`保存します。

4. **カスタム構成プロファイル名** として入力`com.microsoft.wdav`します。

5. 構成プロファイルを開き、ファイルをアップロードします `com.microsoft.wdav.xml` 。 (このファイルは手順 3 で作成されました。

6. **[OK]** を選択します。

7. [**割り当ての****管理**\>] を選択します。 [ **インクルード** ] タブで、[ **すべてのユーザーに割り当てる] & [すべてのデバイス**] を選択します。

> [!CAUTION]
> 正しいカスタム構成プロファイル名を入力する必要があります。それ以外の場合、これらの設定はMicrosoft Defender for Endpointによって認識されません。

## <a name="resources"></a>リソース

- [プロファイル構成リファレンス (Apple 開発者向けドキュメント)](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
