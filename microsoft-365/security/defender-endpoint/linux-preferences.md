---
title: Linux 上のエンドポイント用 Microsoft Defender の基本設定を設定する
ms.reviewer: ''
description: エンタープライズで Microsoft Defender for Endpoint on Linux を構成する方法について説明します。
keywords: Microsoft、Defender、Microsoft Defender for Endpoint、Linux、インストール、展開、アンインストール、puppet、ansible、linux、redhat、ubuntu、debian、sles、suse、centos
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
ms.openlocfilehash: d6ead5c1c23facbab1e80c29cac664ef50a6e8a0
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168908"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a>Linux 上のエンドポイント用 Microsoft Defender の基本設定を設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> このトピックでは、エンタープライズ環境で Defender for Endpoint on Linux の基本設定を設定する方法について説明します。 コマンド ラインからデバイスで製品を構成する場合は、「Resources」を参照 [してください](linux-resources.md#configure-from-the-command-line)。

エンタープライズ環境では、Defender for Endpoint on Linux を構成プロファイルで管理できます。 このプロファイルは、選択した管理ツールから展開されます。 企業が管理する基本設定は、デバイス上でローカルに設定された基本設定よりも優先されます。 つまり、企業のユーザーは、この構成プロファイルを介して設定された基本設定を変更できないのです。

この記事では、このプロファイルの構造 (開始に使用できる推奨プロファイルを含む) と、プロファイルを展開する方法について説明します。

## <a name="configuration-profile-structure"></a>構成プロファイル構造

構成プロファイルは 、キーで識別されるエントリ (基本設定の名前を示す) で構成される .json ファイルで、その後に、基本設定の性質に依存する値が続きます。 数値などの単純な値や、入れ子になった基本設定のリストなどの複雑な値を指定できます。

通常、構成管理ツールを使用して、名前を持つファイルを場所 ```mdatp_managed.json``` にプッシュします ```/etc/opt/microsoft/mdatp/managed/``` 。

構成プロファイルのトップ レベルには、製品全体の基本設定と、製品のサブエリアのエントリが含まれています。これは、次のセクションで詳しく説明します。

### <a name="antivirus-engine-preferences"></a>ウイルス対策エンジンの基本設定

構成 *プロファイルの antivirusEngine* セクションを使用して、製品のウイルス対策コンポーネントの基本設定を管理します。

<br>

****

|説明|値|
|---|---|
|**キー**|antivirusEngine|
|**データ型**|辞書 (入れ子になった基本設定)|
|**コメント**|辞書の内容の説明については、以下のセクションを参照してください。|
|

#### <a name="enable--disable-real-time-protection"></a>リアルタイム保護を有効/無効にする

リアルタイム保護 (アクセス時のファイルのスキャン) を有効にするかどうかを指定します。

<br>

****

|説明|値|
|---|---|
|**キー**|enableRealTimeProtection|
|**データ型**|Boolean|
|**指定可能な値**|true (既定) <p> false|
|

#### <a name="enable--disable-passive-mode"></a>パッシブ モードを有効/無効にする

ウイルス対策エンジンがパッシブ モードで実行されるかどうかを決定します。 パッシブ モードの場合:

- リアルタイム保護はオフです。
- オンデマンド スキャンが有効です。
- 脅威の自動修復が無効になります。
- セキュリティ インテリジェンスの更新プログラムが有効になっている。
- [状態] メニュー アイコンは非表示です。

<br>

****

|説明|値|
|---|---|
|**キー**|passiveMode|
|**データ型**|Boolean|
|**指定可能な値**|false (既定) <p> true|
|**コメント**|Defender for Endpoint version 100.67.60 以上で使用できます。|
|


#### <a name="enabledisable-behavior-monitoring"></a>動作監視を有効または無効にする 

デバイスで動作の監視とブロック機能を有効にするかどうかを決定します。セキュリティ保護の有効性を向上させるために、この機能を有効に保つことをお勧めします。

<br>

****

|説明|値|
|---|---|
|**キー**|behaviorMonitoring|
|**データ型**|String|
|**指定可能な値**|disabled <p> 有効 (既定)|
|**コメント**|Defender for Endpoint version 101.45.00 以上で使用できます。|
  
#### <a name="run-a-scan-after-definitions-are-updated"></a>定義の更新後にスキャンを実行する

新しいセキュリティ インテリジェンス更新プログラムがデバイスにダウンロードされた後にプロセス スキャンを開始するかどうかを指定します。 この設定を有効にすると、デバイスの実行中のプロセスでウイルス対策スキャンがトリガーされます。

<br>

****

|説明|値|
|---|---|
|**キー**|scanAfterDefinitionUpdate|
|**データ型**|Boolean|
|**指定可能な値**|true (既定) <p> false|
|**コメント**|Defender for Endpoint version 101.45.00 以上で使用できます。|
|

#### <a name="scan-archives-on-demand-antivirus-scans-only"></a>アーカイブのスキャン (オンデマンド ウイルス対策スキャンのみ)

オンデマンドウイルス対策スキャン中にアーカイブをスキャンするかどうかを指定します。

<br>

****

|説明|値|
|---|---|
|**キー**|scanArchives|
|**データ型**|Boolean|
|**指定可能な値**|true (既定) <p> false|
|**コメント**|エンドポイント バージョン 101.45.00 以上の Microsoft Defender で使用できます。|
|||

#### <a name="degree-of-parallelism-for-on-demand-scans"></a>オンデマンド スキャンの並列処理の程度

オンデマンド スキャンの並列処理の程度を指定します。 これは、スキャンの実行に使用されるスレッドの数に対応し、CPU 使用率とオンデマンド スキャンの期間に影響します。

<br>

****

|説明|値|
|---|---|
|**キー**|maximumOnDemandScanThreads|
|**データ型**|整数|
|**指定可能な値**|2 (既定)。 使用できる値は、1 ~ 64 の整数です。|
|**コメント**|エンドポイント バージョン 101.45.00 以上の Microsoft Defender で使用できます。|
|||
  

#### <a name="exclusion-merge-policy"></a>除外マージ ポリシー

除外のマージ ポリシーを指定します。 管理者定義の除外とユーザー定義の除外 ( ) の組み合わせ、または管理者定義の除外 ( ) のみを `merge` 組み合わせて指定できます `admin_only` 。 この設定は、ローカル ユーザーが独自の除外を定義するのを制限するために使用できます。

<br>

****

|説明|値|
|---|---|
|**キー**|exclusionsMergePolicy|
|**データ型**|String|
|**指定可能な値**|merge (既定) <p> admin_only|
|**コメント**|Defender for Endpoint version 100.83.73 以上で使用できます。|
|

#### <a name="scan-exclusions"></a>除外をスキャンする

スキャンから除外されたエンティティ。 除外は、完全パス、拡張子、またはファイル名で指定できます。
(除外はアイテムの配列として指定されます。管理者は必要な数の要素を任意の順序で指定できます)。

<br>

****

|説明|値|
|---|---|
|**キー**|除外|
|**データ型**|辞書 (入れ子になった基本設定)|
|**コメント**|辞書の内容の説明については、以下のセクションを参照してください。|
|

##### <a name="type-of-exclusion"></a>除外の種類

スキャンから除外されるコンテンツの種類を指定します。

<br>

****

|説明|値|
|---|---|
|**キー**|$type|
|**データ型**|String|
|**指定可能な値**|excludedPath <p> excludedFileExtension <p> excludedFileName|
|

##### <a name="path-to-excluded-content"></a>除外されたコンテンツへのパス

完全なファイル パスでスキャンからコンテンツを除外するために使用します。

<br>

****

|説明|値|
|---|---|
|**キー**|path|
|**データ型**|String|
|**指定可能な値**|有効なパス|
|**コメント**|適用 *できるのは、$type**が excludedPath である場合のみです。*|
|

##### <a name="path-type-file--directory"></a>パスの種類 (ファイル/ディレクトリ)

*path* プロパティがファイルまたはディレクトリを参照しているかどうかを示します。

<br>

****

|説明|値|
|---|---|
|**キー**|isDirectory|
|**データ型**|Boolean|
|**指定可能な値**|false (既定) <p> true|
|**コメント**|適用 *できるのは、$type**が excludedPath である場合のみです。*|
|

##### <a name="file-extension-excluded-from-the-scan"></a>スキャンから除外されたファイル拡張子

ファイル拡張子でスキャンからコンテンツを除外するために使用します。

<br>

****

|説明|値|
|---|---|
|**キー**|拡張機能|
|**データ型**|String|
|**指定可能な値**|有効なファイル拡張子|
|**コメント**|適用 *できるのは* 、$type FileExtension が *除外されている場合のみです。*|
|

##### <a name="process-excluded-from-the-scan"></a>スキャンから除外されるプロセス*

すべてのファイル アクティビティがスキャンから除外されるプロセスを指定します。 プロセスは、名前 (たとえば) または完全パス `cat` (たとえば) で指定できます `/bin/cat` 。

<br>

****

|説明|値|
|---|---|
|**キー**|name|
|**データ型**|String|
|**指定可能な値**|任意の文字列|
|**コメント**|ファイルが excludedFileName *$type**場合にのみ適用されます。*|
|

#### <a name="allowed-threats"></a>許可される脅威

製品によってブロックされ、代わりに実行が許可されている脅威の一覧 (名前で識別されます)。

<br>

****

|説明|値|
|---|---|
|**キー**|allowedThreats|
|**データ型**|文字列の配列|
|

#### <a name="disallowed-threat-actions"></a>許可されていない脅威アクション

脅威が検出された場合にデバイスのローカル ユーザーが実行できるアクションを制限します。 この一覧に含まれるアクションは、ユーザー インターフェイスには表示されません。

<br>

****

|説明|値|
|---|---|
|**キー**|disallowedThreatActions|
|**データ型**|文字列の配列|
|**指定可能な値**|allow (ユーザーによる脅威の許可を制限する) <p> 復元 (検疫からの脅威の復元をユーザーに制限する)|
|**コメント**|Defender for Endpoint version 100.83.73 以上で使用できます。|
|

#### <a name="threat-type-settings"></a>脅威の種類の設定

ウイルス *対策エンジンの threatTypeSettings* 基本設定は、製品による特定の脅威の種類の処理方法を制御するために使用されます。

<br>

****

|説明|値|
|---|---|
|**キー**|threatTypeSettings|
|**データ型**|辞書 (入れ子になった基本設定)|
|**コメント**|辞書の内容の説明については、以下のセクションを参照してください。|
|

##### <a name="threat-type"></a>脅威の種類

動作が構成されている脅威の種類。

<br>

****

|説明|値|
|---|---|
|**キー**|キー|
|**データ型**|String|
|**指定可能な値**|potentially_unwanted_application <p> archive_bomb|
|

##### <a name="action-to-take"></a>実行する操作

前のセクションで指定した種類の脅威に出く際に実行するアクション。 次の指定が可能です。

- **監査**: デバイスは、この種類の脅威から保護されませんが、脅威に関するエントリがログに記録されます。
- **ブロック**: デバイスは、この種類の脅威から保護され、セキュリティ コンソールで通知されます。
- **オフ**: デバイスは、この種類の脅威から保護され、何もログに記録されません。

<br>

****

|説明|値|
|---|---|
|**キー**|値|
|**データ型**|String|
|**指定可能な値**|監査 (既定) <p> block <p> off|
|

#### <a name="threat-type-settings-merge-policy"></a>脅威の種類の設定の差し込みポリシー

脅威の種類の設定のマージ ポリシーを指定します。 これは、管理者定義設定とユーザー定義設定 ( ) の組み合わせか、管理者定義の設定 ( ) のみを `merge` 組み合わせて使用できます `admin_only` 。 この設定を使用すると、ローカル ユーザーがさまざまな脅威の種類に対して独自の設定を定義するのを制限できます。

<br>

****

|説明|値|
|---|---|
|**キー**|threatTypeSettingsMergePolicy|
|**データ型**|String|
|**指定可能な値**|merge (既定) <p> admin_only|
|**コメント**|Defender for Endpoint version 100.83.73 以上で使用できます。|
|

#### <a name="antivirus-scan-history-retention-in-days"></a>ウイルス対策スキャン履歴の保持 (日数)

デバイスのスキャン履歴に結果が保持される日数を指定します。 古いスキャン結果は履歴から削除されます。 ディスクから削除された古い検疫済みファイル。

<br>

****

|説明|値|
|---|---|
|**キー**|scanResultsRetentionDays|
|**データ型**|String|
|**指定可能な値**|90 (既定)。 使用できる値は、1 日から 180 日です。|
|**コメント**|Defender for Endpoint version 101.04.76 以上で使用できます。|
|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>ウイルス対策スキャン履歴内のアイテムの最大数

スキャン履歴に保持するエントリの最大数を指定します。 エントリには、過去に実行されたオンデマンド スキャンとすべてのウイルス対策検出が含まれます。

<br>

****

|説明|値|
|---|---|
|**キー**|scanHistoryMaximumItems|
|**データ型**|String|
|**指定可能な値**|10000 (既定値)。 許可される値は、5000 アイテムから 15,000 アイテムまでです。|
|**コメント**|Defender for Endpoint version 101.04.76 以上で使用できます。|
|

### <a name="cloud-delivered-protection-preferences"></a>クラウドによる保護の基本設定

構成 *プロファイルの cloudService* エントリを使用して、製品のクラウド駆動型保護機能を構成します。

<br>

****

|説明|値|
|---|---|
|**キー**|cloudService|
|**データ型**|辞書 (入れ子になった基本設定)|
|**コメント**|辞書の内容の説明については、以下のセクションを参照してください。|
|

#### <a name="enable--disable-cloud-delivered-protection"></a>クラウド配信保護を有効/無効にする

デバイスでクラウド配信の保護を有効にするかどうかを指定します。 サービスのセキュリティを向上させるために、この機能を有効にすることをお勧めします。

<br>

****

|説明|値|
|---|---|
|**キー**|enabled|
|**データ型**|Boolean|
|**指定可能な値**|true (既定) <p> false|
|

#### <a name="diagnostic-collection-level"></a>診断収集のレベル

診断データは、Defender for Endpoint を安全かつ最新の状態に保ち、問題を検出、診断、修正し、製品の改善を行う場合に使用されます。 この設定は、製品から Microsoft に送信される診断のレベルを決定します。

<br>

****

|説明|値|
|---|---|
|**キー**|diagnosticLevel|
|**データ型**|String|
|**指定可能な値**|省略可能 (既定) <p> 必須出席者|
|

#### <a name="enable--disable-automatic-sample-submissions"></a>自動サンプル申請を有効または無効にする

疑わしいサンプル (脅威を含む可能性が高い) を Microsoft に送信するかどうかを決定します。 サンプル申請を制御するには、次の 3 つのレベルがあります。

- **なし**: 疑わしいサンプルは Microsoft に送信されません。
- **セーフ**: 個人を特定できる情報 (PII) を含む疑わしいサンプルだけが自動的に送信されます。 これは、この設定の既定値です。
- **すべて**: すべての疑わしいサンプルが Microsoft に送信されます。

<br>

****

|説明|値|
|---|---|
|**キー**|automaticSampleSubmissionConsent|
|**データ型**|String|
|**指定可能な値**|none <p> safe (既定) <p> すべての|
|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>セキュリティ インテリジェンスの自動更新を有効または無効にする

セキュリティ インテリジェンスの更新プログラムが自動的にインストールされるかどうかを決定します。

<br>

****

|説明|値|
|---|---|
|**キー**|automaticDefinitionUpdateEnabled|
|**データ型**|Boolean|
|**指定可能な値**|true (既定) <p> false|
|

## <a name="recommended-configuration-profile"></a>推奨される構成プロファイル

開始するには、Defender for Endpoint が提供するすべての保護機能を利用するために、企業の次の構成プロファイルをお勧めします。

次の構成プロファイルは次のようになります。

- リアルタイム保護を有効にする (RTP)
- 次の脅威の種類の処理方法を指定します。
  - **望ましくない可能性のあるアプリケーション (PUA) が** ブロックされる
  - **アーカイブボム** (圧縮率が高いファイル) は、製品ログに対して監査されます
- セキュリティ インテリジェンスの自動更新を有効にする
- クラウドによる保護の有効化
- レベルで自動サンプル提出を `safe` 有効にする
- 動作監視を有効にする

### <a name="sample-profile"></a>サンプル プロファイル

```JSON
{
   "antivirusEngine":{
      "behaviorMonitoring":"enabled",
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true,
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a>完全な構成プロファイルの例

次の構成プロファイルには、このドキュメントで説明されているすべての設定のエントリが含まれています。製品を詳細に制御する高度なシナリオに使用できます。

### <a name="full-profile"></a>フル プロファイル

```JSON
{
   "antivirusEngine":{
      "behaviorMonitoring":"enabled",
      "enableRealTimeProtection":true,
      "scanAfterDefinitionUpdate":true,
      "scanArchives":true,
      "maximumOnDemandScanThreads":2,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/run"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git"
         },
         {
            "$type":"excludedFileExtension",
            "extension":".pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "<EXAMPLE DO NOT USE>EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true,
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a>構成プロファイルの検証

構成プロファイルは、有効な JSON 形式のファイルである必要があります。 これを確認するために使用できるツールは多数ある。 たとえば、デバイスにインストール `python` されている場合は、次の情報を使用します。

```bash
python -m json.tool mdatp_managed.json
```

JSON が整形式の場合、上記のコマンドはターミナルに出力し、終了コードを返します `0` 。 それ以外の場合は、問題を説明するエラーが表示され、コマンドは終了コードを返します `1` 。

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a>mdatp_managed.json ファイルが期待通り動作しているのを確認する

/etc/opt/microsoft/mdatp/managed/mdatp_managed.json が正しく動作することを確認するには、次の設定の横に "[managed]" と表示されます。

- cloud_enabled
- cloud_automatic_sample_submission_consent
- passive_mode_enabled
- real_time_protection_enabled
- automatic_definition_update_enabled

> [!NOTE]
> mdatp_managed.json を有効にするために、wdavdaemon の再起動は必要ありません。

## <a name="configuration-profile-deployment"></a>構成プロファイルの展開

企業の構成プロファイルを構築したら、企業が使用している管理ツールを使用して展開できます。 Defender for Endpoint on Linux は *、/etc/opt/microsoft/mdatp/managed/mdatp_managed.json ファイルから管理構成を読み取* ります。
