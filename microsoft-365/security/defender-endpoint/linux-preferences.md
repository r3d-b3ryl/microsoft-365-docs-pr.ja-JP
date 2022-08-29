---
title: Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する
ms.reviewer: ''
description: 企業の Linux でMicrosoft Defender for Endpointを構成する方法について説明します。
keywords: Microsoft、Defender、Microsoft Defender for Endpoint、Linux、インストール、展開、アンインストール、puppet、ansible、linux、redhat、ubuntu、debian、sles、suse、centos
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
ms.date: 08/10/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a6a31317ec95a4767f36cf6db21ec2e146f9eda8
ms.sourcegitcommit: 9b10e56b9e83f3a80757fa6108bebd1d80cf4178
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67320221"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a>Linux 上で Microsoft Defender for Endpoint 用の基本設定を設定する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!IMPORTANT]
> このトピックでは、エンタープライズ環境で Defender for Endpoint on Linux の基本設定を設定する方法について説明します。 コマンド ラインからデバイスで製品を構成する場合は、「 [リソース](linux-resources.md#configure-from-the-command-line)」を参照してください。

エンタープライズ環境では、Defender for Endpoint on Linux は構成プロファイルを使用して管理できます。 このプロファイルは、任意の管理ツールからデプロイされます。 企業によって管理される基本設定は、デバイスでローカルに設定されたものより優先されます。 つまり、企業内のユーザーは、この構成プロファイルを使用して設定された基本設定を変更することはできません。 除外がマネージド構成プロファイルを介して追加された場合は、マネージド構成プロファイルを使用してのみ削除できます。 コマンド ラインは、ローカルに追加された除外に対して機能します。

この記事では、このプロファイルの構造 (使用できる推奨プロファイルを含む) と、プロファイルをデプロイする方法について説明します。

## <a name="configuration-profile-structure"></a>構成プロファイル構造

構成プロファイルは .json ファイルであり、キーによって識別されるエントリ (これは、基本設定の名前を示します)、値が続き、基本設定の性質に依存します。 値は、数値などの単純な値や、入れ子になった基本設定のリストなどの複雑な値にすることができます。

通常、構成管理ツールを使用して、場所```/etc/opt/microsoft/mdatp/managed/```に名前```mdatp_managed.json```を付けてファイルをプッシュします。

構成プロファイルの最上位レベルには、製品全体の基本設定と製品のサブエリアのエントリが含まれています。これについては、次のセクションで詳しく説明します。

### <a name="antivirus-engine-preferences"></a>ウイルス対策エンジンの基本設定

構成プロファイルの *antivirusEngine* セクションは、製品のウイルス対策コンポーネントの基本設定を管理するために使用されます。

|説明|値|
|---|---|
|**Key**|antivirusEngine|
|**データ型**|ディクショナリ (入れ子になった設定)|
|**コメント**|ディクショナリの内容の説明については、次のセクションを参照してください。|

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

|説明|値|
|---|---|
|**Key**|enforcementLevel|
|**データ型**|String|
|**指定可能な値**|real_time (既定) <p> on_demand <p> パッシブ|
|**コメント**|Defender for Endpoint バージョン 101.10.72 以降で使用できます。|

#### <a name="enabledisable-behavior-monitoring"></a>動作監視を有効/無効にする 

デバイスで動作の監視とブロック機能を有効にするかどうかを決定します。 セキュリティ保護の有効性を向上させるために、この機能をオンにしておくことをお勧めします。

<br>

****

|説明|値|
|---|---|
|**Key**|behaviorMonitoring|
|**データ型**|String|
|**指定可能な値**|無効 (既定値) <p> enabled|
|**コメント**|Defender for Endpoint バージョン 101.45.00 以降で使用できます。|

#### <a name="configure-file-hash-computation-feature"></a>ファイル ハッシュ計算機能を構成する

ファイル ハッシュの計算機能を有効または無効にします。 この機能を有効にすると、Defender for Endpoint はスキャンするファイルのハッシュを計算します。 この機能を有効にすると、デバイスのパフォーマンスに影響する可能性があることに注意してください。 詳細については、「 [ファイルのインジケーターを作成する」を](indicator-file.md)参照してください。

|説明|値|
|---|---|
|**Key**|enableFileHashComputation|
|**データ型**|String|
|**指定可能な値**|無効 (既定値) <p> enabled|
|**コメント**|Defender for Endpoint バージョン 101.73.77 以降で使用できます。|
  
#### <a name="run-a-scan-after-definitions-are-updated"></a>定義が更新された後にスキャンを実行する

デバイスに新しいセキュリティ インテリジェンス更新プログラムがダウンロードされた後にプロセス スキャンを開始するかどうかを指定します。 この設定を有効にすると、デバイスの実行中のプロセスでウイルス対策スキャンがトリガーされます。

|説明|値|
|---|---|
|**Key**|scanAfterDefinitionUpdate|
|**データ型**|ブール型|
|**指定可能な値**|true (既定値) <p> false|
|**コメント**|Defender for Endpoint バージョン 101.45.00 以降で使用できます。|

#### <a name="scan-archives-on-demand-antivirus-scans-only"></a>スキャン アーカイブ (オンデマンドウイルス対策スキャンのみ)

オンデマンドウイルス対策スキャン中にアーカイブをスキャンするかどうかを指定します。

|説明|値|
|---|---|
|**Key**|scanArchives|
|**データ型**|ブール型|
|**指定可能な値**|true (既定値) <p> false|
|**コメント**|Microsoft Defender for Endpoint バージョン 101.45.00 以降で使用できます。|

#### <a name="degree-of-parallelism-for-on-demand-scans"></a>オンデマンド スキャンの並列処理の程度

オンデマンド スキャンの並列処理の度合いを指定します。 これは、スキャンの実行に使用されるスレッドの数に対応し、CPU 使用率とオンデマンド スキャンの期間に影響します。

|説明|値|
|---|---|
|**Key**|maximumOnDemandScanThreads|
|**データ型**|整数|
|**指定可能な値**|2 (既定値)。 使用できる値は、1 から 64 までの整数です。|
|**コメント**|Microsoft Defender for Endpoint バージョン 101.45.00 以降で使用できます。|

#### <a name="exclusion-merge-policy"></a>除外マージ ポリシー

除外のマージ ポリシーを指定します。 管理者定義の除外とユーザー定義の除外 () の組み合わせか、管理者定義の除外 (`merge``admin_only`) のみを使用できます。 この設定を使用すると、ローカル ユーザーが独自の除外を定義できないように制限できます。

|説明|値|
|---|---|
|**Key**|exclusionsMergePolicy|
|**データ型**|String|
|**指定可能な値**|merge (既定値) <p> admin_only|
|**コメント**|Defender for Endpoint バージョン 100.83.73 以降で使用できます。|

#### <a name="scan-exclusions"></a>除外をスキャンする

スキャンから除外されたエンティティ。 除外は、完全なパス、拡張子、またはファイル名で指定できます。
(除外は項目の配列として指定され、管理者は必要な数の要素を任意の順序で指定できます。

|説明|値|
|---|---|
|**Key**|除外|
|**データ型**|ディクショナリ (入れ子になった設定)|
|**コメント**|ディクショナリの内容の説明については、次のセクションを参照してください。|

##### <a name="type-of-exclusion"></a>除外の種類

スキャンから除外されるコンテンツの種類を指定します。

|説明|値|
|---|---|
|**Key**|$type|
|**データ型**|String|
|**指定可能な値**|excludedPath <p> excludedFileExtension <p> excludedFileName|

##### <a name="path-to-excluded-content"></a>除外されたコンテンツへのパス

完全なファイル パスでスキャンからコンテンツを除外するために使用されます。

|説明|値|
|---|---|
|**Key**|path|
|**データ型**|String|
|**指定可能な値**|有効なパス|
|**コメント**|*$type**が excludedPath* の場合にのみ適用されます|

##### <a name="path-type-file--directory"></a>パスの種類 (ファイル/ディレクトリ)

*path* プロパティがファイルまたはディレクトリを参照しているかどうかを示します。

|説明|値|
|---|---|
|**Key**|isDirectory|
|**データ型**|ブール型|
|**指定可能な値**|false (既定) <p> true|
|**コメント**|*$type**が excludedPath* の場合にのみ適用されます|

##### <a name="file-extension-excluded-from-the-scan"></a>スキャンから除外されたファイル拡張子

ファイル拡張子によるスキャンからコンテンツを除外するために使用されます。

|説明|値|
|---|---|
|**Key**|拡張子|
|**データ型**|String|
|**指定可能な値**|有効なファイル拡張子|
|**コメント**|*$type**が除外されている場合にのみ適用されるFileExtension*|

##### <a name="process-excluded-from-the-scan"></a>スキャンから除外されたプロセス*

すべてのファイル アクティビティがスキャンから除外されるプロセスを指定します。 プロセスは、その名前 (たとえば、 `cat`) または完全パス (例: `/bin/cat`) で指定できます。

|説明|値|
|---|---|
|**Key**|name|
|**データ型**|String|
|**指定可能な値**|任意の文字列|
|**コメント**|*$type**が excludedFileName* の場合にのみ適用されます|

#### <a name="allowed-threats"></a>許可される脅威

製品によってブロックされず、代わりに実行が許可されている脅威の一覧 (名前で識別されます)。

|説明|値|
|---|---|
|**Key**|allowedThreats|
|**データ型**|文字列の配列|

#### <a name="disallowed-threat-actions"></a>許可されていない脅威アクション

脅威が検出されたときにデバイスのローカル ユーザーが実行できるアクションを制限します。 この一覧に含まれるアクションは、ユーザー インターフェイスには表示されません。

|説明|値|
|---|---|
|**Key**|disallowedThreatActions|
|**データ型**|文字列の配列|
|**可能な値**|allow (ユーザーによる脅威の許可を制限) <p> restore (ユーザーが検疫からの脅威を復元できないように制限)|
|**コメント**|Defender for Endpoint バージョン 100.83.73 以降で使用できます。|

#### <a name="threat-type-settings"></a>脅威の種類の設定

ウイルス対策エンジンの *threatTypeSettings* 基本設定は、特定の脅威の種類が製品でどのように処理されるかを制御するために使用されます。

|説明|値|
|---|---|
|**Key**|threatTypeSettings|
|**データ型**|ディクショナリ (入れ子になった設定)|
|**コメント**|ディクショナリの内容の説明については、次のセクションを参照してください。|

##### <a name="threat-type"></a>脅威の種類

動作が構成されている脅威の種類。

|説明|値|
|---|---|
|**Key**|キー|
|**データ型**|String|
|**指定可能な値**|potentially_unwanted_application <p> archive_bomb|

##### <a name="action-to-take"></a>実行する操作

前のセクションで指定した種類の脅威に対処する場合に実行するアクション。 次のことができます。

- **監査**: デバイスはこの種類の脅威から保護されていませんが、脅威に関するエントリがログに記録されます。
- **ブロック**: デバイスはこの種類の脅威から保護され、セキュリティ コンソールに通知されます。
- **オフ**: デバイスはこの種類の脅威から保護されておらず、何もログに記録されません。

|説明|値|
|---|---|
|**Key**|値|
|**データ型**|String|
|**指定可能な値**|監査 (既定) <p> ブロック <p> オフ|

#### <a name="threat-type-settings-merge-policy"></a>脅威の種類の設定のマージ ポリシー

脅威の種類の設定のマージ ポリシーを指定します。 これは、管理者が定義した設定とユーザー定義の設定 (`merge`) の組み合わせか、管理者が定義した設定 (`admin_only`) のみを使用できます。 この設定を使用すると、ローカル ユーザーがさまざまな脅威の種類に対して独自の設定を定義できないように制限できます。

|説明|値|
|---|---|
|**Key**|threatTypeSettingsMergePolicy|
|**データ型**|String|
|**指定可能な値**|merge (既定値) <p> admin_only|
|**コメント**|Defender for Endpoint バージョン 100.83.73 以降で使用できます。|

#### <a name="antivirus-scan-history-retention-in-days"></a>ウイルス対策スキャン履歴の保持期間 (日数)

デバイスのスキャン履歴に結果が保持される日数を指定します。 古いスキャン結果は履歴から削除されます。 ディスクからも削除された古い検疫済みファイル。

|説明|値|
|---|---|
|**Key**|scanResultsRetentionDays|
|**データ型**|String|
|**指定可能な値**|90 (既定値)。 使用できる値は 1 日から 180 日です。|
|**コメント**|Defender for Endpoint バージョン 101.04.76 以降で使用できます。|

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>ウイルス対策スキャン履歴内のアイテムの最大数

スキャン履歴に保持するエントリの最大数を指定します。 エントリには、過去に実行されたすべてのオンデマンド スキャンとすべてのウイルス対策検出が含まれます。

|説明|値|
|---|---|
|**Key**|scanHistoryMaximumItems|
|**データ型**|String|
|**指定可能な値**|10000 (既定値)。 使用できる値は、5,000 項目から 15,000 項目です。|
|**コメント**|Defender for Endpoint バージョン 101.04.76 以降で使用できます。|

### <a name="cloud-delivered-protection-preferences"></a>クラウド配信の保護の基本設定

構成プロファイルの *cloudService* エントリは、製品のクラウドドリブン保護機能を構成するために使用されます。

|説明|値|
|---|---|
|**Key**|cloudService|
|**データ型**|ディクショナリ (入れ子になった設定)|
|**コメント**|ディクショナリの内容の説明については、次のセクションを参照してください。|

#### <a name="enable--disable-cloud-delivered-protection"></a>クラウド配信保護を有効/無効にする

クラウド配信保護をデバイスで有効にするかどうかを決定します。 サービスのセキュリティを向上させるために、この機能をオンにしておくことをお勧めします。

|説明|値|
|---|---|
|**Key**|enabled|
|**データ型**|ブール型|
|**指定可能な値**|true (既定値) <p> false|

#### <a name="diagnostic-collection-level"></a>診断収集のレベル

診断データは、Defender for Endpoint をセキュリティで保護し、最新の状態に保ち、問題を検出、診断、修正し、製品の改善にも使用されます。 この設定は、製品から Microsoft に送信される診断のレベルを決定します。

|説明|値|
|---|---|
|**Key**|diagnosticLevel|
|**データ型**|String|
|**指定可能な値**|省略可能 <p> 必須 (既定値)|
|

#### <a name="configure-cloud-block-level"></a>クラウド ブロック レベルを構成する

この設定は、疑わしいファイルをブロックおよびスキャンする Defender for Endpoint の攻撃性を決定します。 この設定がオンの場合、Defender for Endpoint は、ブロックおよびスキャンする疑わしいファイルを識別するときに、より積極的になります。それ以外の場合は、攻撃性が低くなり、より少ない頻度でブロックおよびスキャンされます。 クラウド ブロック レベルを設定する場合は、次の 5 つの値があります。

- 標準 (`normal`): 既定のブロック レベル。
- 中 (`moderate`): 高信頼度検出に対してのみ判定を行います。
- 高 (`high`): パフォーマンスを最適化しながら不明なファイルを積極的にブロックします (有害でないファイルをブロックする可能性が高くなります)。
- High Plus (`high_plus`): 不明なファイルを積極的にブロックし、追加の保護手段を適用します (クライアント デバイスのパフォーマンスに影響を与える可能性があります)。
- ゼロトレランス (`zero_tolerance`): 不明なプログラムをすべてブロックします。

|説明|値|
|---|---|
|**Key**|cloudBlockLevel|
|**データ型**|String|
|**指定可能な値**|normal (既定値) <p> 中程 度 <p> 高 <p> high_plus <p> zero_tolerance|
|**コメント**|Defender for Endpoint バージョン 101.56.62 以降で使用できます。|
  
#### <a name="enable--disable-automatic-sample-submissions"></a>サンプルの自動送信を有効または無効にする

疑わしいサンプル (脅威を含む可能性が高い) を Microsoft に送信するかどうかを決定します。 サンプルの提出を制御するための 3 つのレベルがあります。

- **なし**: 疑わしいサンプルは Microsoft に送信されません。
- **安全**: 個人を特定できる情報 (PII) を含まない疑わしいサンプルのみが自動的に送信されます。 これは、この設定の既定値です。
- **すべて**: 疑わしいサンプルはすべて Microsoft に送信されます。

|説明|値|
|---|---|
|**Key**|automaticSampleSubmissionConsent|
|**データ型**|String|
|**指定可能な値**|none <p> safe (既定値) <p> すべて|

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>セキュリティ インテリジェンスの自動更新を有効または無効にする

セキュリティ インテリジェンス更新プログラムを自動的にインストールするかどうかを決定します。

|説明|値|
|---|---|
|**Key**|automaticDefinitionUpdateEnabled|
|**データ型**|ブール型|
|**指定可能な値**|true (既定値) <p> false|

## <a name="recommended-configuration-profile"></a>推奨される構成プロファイル

開始するには、企業が Defender for Endpoint が提供するすべての保護機能を利用するために、次の構成プロファイルをお勧めします。

次の構成プロファイルは次のようになります。

- リアルタイム保護 (RTP) を有効にする
- 次の脅威の種類を処理する方法を指定します。
  - **望ましくない可能性があるアプリケーション (PUA)** がブロックされる
  - **アーカイブ ボム** (圧縮率が高いファイル) は、製品ログに監査されます
- セキュリティ インテリジェンスの自動更新を有効にする
- クラウドによる保護の有効化
- レベルで自動サンプル送信を `safe` 有効にする
- 動作監視を有効にする

### <a name="sample-profile"></a>サンプル プロファイル

```JSON
{
   "antivirusEngine":{
      "enforcementLevel":"real_time",
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
      "proxy": "<EXAMPLE DO NOT USE> http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a>完全な構成プロファイルの例

次の構成プロファイルには、このドキュメントで説明されているすべての設定のエントリが含まれており、製品をより詳細に制御するより高度なシナリオに使用できます。

### <a name="full-profile"></a>フル プロファイル

```JSON
{
   "antivirusEngine":{
      "enforcementLevel":"real_time",
      "scanAfterDefinitionUpdate":true,
      "scanArchives":true,
      "maximumOnDemandScanThreads":2,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log<EXAMPLE DO NOT USE>"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/run<EXAMPLE DO NOT USE>"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home/*/git<EXAMPLE DO NOT USE>"
         },
         {
            "$type":"excludedFileExtension",
            "extension":".pdf<EXAMPLE DO NOT USE>"
         },
         {
            "$type":"excludedFileName",
            "name":"cat<EXAMPLE DO NOT USE>"
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
      "proxy": "<EXAMPLE DO NOT USE> http://proxy.server:port/"
   }
}
```

## <a name="add-tag-or-group-id-to-the-configuration-profile"></a>構成プロファイルにタグまたはグループ ID を追加する

コマンドを `mdatp health` 初めて実行すると、タグとグループ ID の値は空白になります。 ファイルにタグまたはグループ ID を `mdatp_managed.json` 追加するには、次の手順に従います。
  
  1. パス `/etc/opt/microsoft/mdatp/managed/mdatp_managed.json`から構成プロファイルを開きます。
  2. ブロックが配置されている `cloudService` ファイルの下部に下に移動します。
  3. 次の例に示すように、必要なタグまたはグループ ID を 、.. の最後の中かっこの末尾に `cloudService`追加します。

  ```JSON
    },
    "cloudService": {
      "enabled": true,
      "diagnosticLevel": "optional",
      "automaticSampleSubmissionConsent": "safe",
      "automaticDefinitionUpdateEnabled": true,
      "proxy": "http://proxy.server:port/"
  },
  "edr": {
    "groupIds":"GroupIdExample",
    "tags": [
              {
              "key": "GROUP",
              "value": "Tag"
              }
            ]
        }
  }
  ```

  > [!NOTE]
  > ブロックの末尾 `cloudService` に、最後の中かっこの後にコンマを追加することを忘れないでください。 また、タグまたはグループ ID ブロックを追加した後に、2 つの終わりの中かっこがあることを確認します (上記の例を参照してください)。 現時点では、タグでサポートされているキー名は `GROUP`. 
  
## <a name="configuration-profile-validation"></a>構成プロファイルの検証

構成プロファイルは、有効な JSON 形式のファイルである必要があります。 これを確認するために使用できるツールがいくつかあります。 たとえば、デバイスにインストールしている `python` 場合は次のようになります。

```bash
python -m json.tool mdatp_managed.json
```

JSON が整形式の場合、上記のコマンドはターミナルに出力し、 `0`. それ以外の場合は、問題を説明するエラーが表示され、コマンドは終了コード `1`.

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a>mdatp_managed.json ファイルが期待どおりに動作していることを確認する

/etc/opt/microsoft/mdatp/managed/mdatp_managed.json が正しく動作していることを確認するには、次の設定の横に "[managed]" と表示されます。

- cloud_enabled
- cloud_automatic_sample_submission_consent
- passive_mode_enabled
- real_time_protection_enabled
- automatic_definition_update_enabled

> [!NOTE]
> mdatp_managed.json を有効にするには、deamon を `mdatp` 再起動する必要はありません。

## <a name="configuration-profile-deployment"></a>構成プロファイルの展開

エンタープライズの構成プロファイルを構築したら、エンタープライズが使用している管理ツールを使用して展開できます。 Linux 上の Defender for Endpoint は、 */etc/opt/microsoft/mdatp/managed/mdatp_managed.json* ファイルからマネージド構成を読み取ります。
