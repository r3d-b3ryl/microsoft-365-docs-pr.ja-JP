---
title: デバイスごとの評価方法とプロパティをエクスポートする
description: "\"Microsoft Defender 脆弱性の管理\" データをプルする API に関する情報を提供します。 さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。 一般に、各 API 呼び出しには、組織内のデバイスに必要なデータが含まれています。"
keywords: api, apis, export assessment, per device assessment, per machine assessment, vulnerability assessment report, device Vulnerability Assessment, device vulnerability report, secure configuration Assessment, secure configuration report, secure configuration report, software Vulnerabilities assessment, software Vulnerability report, software vulnerability report, vulnerability report by machine,
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: a6a542f07e77a35661cab10b64133f6cfa2a26ed
ms.sourcegitcommit: 7374c7b013890744d74e5214f7f8d69ca7874466
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2022
ms.locfileid: "67408355"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>デバイスごとの評価方法とプロパティをエクスポートする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender 脆弱性の管理](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="api-description"></a>API の説明

デバイスごとに脆弱性管理データをプルする API に関するメソッドとプロパティの詳細を提供します。 さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。 一般に、各 API 呼び出しには、組織内のデバイスに必要なデータが含まれています。

> [!NOTE]
> 特に明記されていない限り、一覧表示されているすべてのエクスポート評価方法は **_、完全なエクスポート_** と **_デバイス別_** ( **_デバイスごと_** とも呼ばれます) です。

エクスポート評価 API を使用して、さまざまな種類の情報を取得 (エクスポート) できます。

- [1. セキュリティで保護された構成の評価をエクスポートする](#1-export-secure-configurations-assessment)
- [2. ソフトウェア インベントリの評価をエクスポートする](#2-export-software-inventory-assessment)
- [3. ソフトウェアの脆弱性評価をエクスポートする](#3-export-software-vulnerabilities-assessment)
- [4. 製品コード以外のソフトウェア インベントリ評価をエクスポートする](#4-export-non-product-code-software-inventory-assessment)

エクスポート情報の種類に対応する API については、セクション 1、2、および 3 で説明します。

各メソッドには、さまざまな種類のデータを取得するための異なる API 呼び出しがあります。 データの量は大きくなる可能性があるため、取得する方法は 2 つあります。

- **JSON 応答**  API は、組織内のすべてのデータを JSON 応答としてプルします。 この方法は、 _100 K 未満のデバイスを持つ小規模な組織_ に最適です。 応答はページ分割されるため、応答の \@odata.nextLink フィールドを使用して次の結果をフェッチできます。

- **ファイル経由** この API ソリューションを使用すると、大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織におすすめです。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storage からすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のように Azure Storage からすべてのデータをダウンロードできます:
  - すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。
  - ダウンロード URL を使用してすべてのファイルをダウンロードし、データを好きなように処理します。

"_JSON 応答_ または _ファイル経由_" を使用して収集されるデータは、現在の状態の現在のスナップショットです。 履歴データは含まれません。 履歴データを収集するには、お客様が独自のデータ ストレージにデータを保存する必要があります。

## <a name="1-export-secure-configurations-assessment"></a>1. セキュリティで保護された構成の評価をエクスポートする

デバイスごとに、すべての構成とその状態を返します。

### <a name="11-methods"></a>1.1 メソッド

Method|データ型|説明
:---|:---|:---
セキュリティで保護された構成評価 **をエクスポートする (JSON 応答)**|デバイス コレクションによるセキュリティで保護された構成。 参照: [1.2 プロパティ (JSON 応答)](#12-properties-json-response)|DeviceId、ConfigurationId のすべての一意の組み合わせのエントリを含むテーブルを返します。 API は、組織内のすべてのデータを JSON 応答としてプルします。 この方法は、10 万個未満のデバイスのある小規模な組織に最適です。 応答はページ分割されるため、応答の@odata.nextLink フィールドを使用して、次の結果をフェッチできます。
セキュリティで保護された構成評価 **をエクスポートする (ファイル経由)**|デバイス コレクションによるセキュリティで保護された構成。 参照: [1.3 プロパティ (ファイル経由)](#13-properties-via-files)|DeviceId、ConfigurationId のすべての一意の組み合わせのエントリを含むテーブルを返します。 この API ソリューションを使用すると、より大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織におすすめです。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storage からすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のように Azure Storage からすべてのデータをダウンロードできます: <ol><li>すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。</li><li>ダウンロード URL を使用してすべてのファイルをダウンロードし、データを好きなように処理します。</li></ol>

### <a name="12-properties-json-response"></a>1.2 プロパティ (JSON 応答)

プロパティ (ID)|データ型|説明
:---|:---|:---
configurationCategory|文字列|構成が属するカテゴリまたはグループ:アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御。
configurationId|文字列|特定の構成の一意の識別子。
configurationImpact|文字列|構成の全体的な構成スコア (1 ~ 10) に対する評価された効果。
configurationName|文字列|構成の表示名。
configurationSubcategory|文字列|構成が属するサブカテゴリまたはサブグループ。 多くの場合、特定の機能または機能。
deviceId|String|サービス内のデバイスの一意の識別子。
deviceName|String|デバイスの完全修飾ドメイン名 (FQDN)。
isApplicable|ブール|構成またはポリシーが適用可能かどうかを示します。
isCompliant|ブール|構成またはポリシーが適切に構成されているかどうかを示します。
isExpectedUserImpact|ブール|構成が適用される場合に、ユーザーが影響を受けるかどうかを示します。
osPlatform|String|デバイスで実行されているオペレーティング システムのプラットフォーム。 Windows 10やWindows 11など、同じファミリ内にバリエーションがある特定のオペレーティング システム。 詳細については [、「サポートされているオペレーティング システム、プラットフォーム、および機能](../defender-vulnerability-management/tvm-supported-os.md) 」を参照してください。
osVersion|String|デバイスで実行されているオペレーティング システムの特定のバージョン。
rbacGroupName|String|ロールベースのアクセス制御 (RBAC) グループ。 デバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。
rbacGroupId|文字列|ロールベースのアクセス制御 (RBAC) グループ ID。
recommendationReference|文字列|ソフトウェアに関連する推奨事項 ID への参照。
timestamp|文字列|デバイスで最後に構成が表示された時刻。

### <a name="13-properties-via-files"></a>1.3 プロパティ (ファイル経由)

プロパティ (ID)|データ型|説明
:---|:---|:---
ファイルをエクスポートする|配列\[文字列\]|組織の現在のスナップショットを保持しているファイルのダウンロード URL のリスト。
GeneratedTime|String|エクスポートが生成された時刻。

## <a name="2-export-software-inventory-assessment"></a>2. ソフトウェア インベントリの評価をエクスポートする

インストールされているすべてのソフトウェアとその詳細を各デバイスに返します。

### <a name="21-methods"></a>2.1 メソッド

|Method|データ型|説明|
|:---|:---|:---|
|ソフトウェア インベントリ評価 **のエクスポート (JSON 応答)**|デバイス コレクション別のソフトウェア インベントリ。 参照: [2.2 プロパティ (JSON 応答)](#22-properties-json-response)|DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。 API は、組織内のすべてのデータを JSON 応答としてプルします。 この方法は、10 万個未満のデバイスのある小規模な組織に最適です。 応答はページ分割されるため、応答の@odata.nextLink フィールドを使用して、次の結果をフェッチできます。 |
| ソフトウェア インベントリ評価 **のエクスポート (ファイル経由)**|デバイス ファイル別のソフトウェア インベントリ。 参照: [2.3 プロパティ (ファイル経由)](#23-properties-via-files)|DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。 この API ソリューションを使用すると、より大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織におすすめです。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storage からすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のように Azure Storage からデータをダウンロードできます。 <ol><li>組織のデータを含むダウンロード URL の一覧を取得するには、API を呼び出します</li><li>ダウンロード URL を使用してファイルをダウンロードし、必要に合ったデータを処理します。</li></ol> |

### <a name="22-properties-json-response"></a>2.2 プロパティ (JSON 応答)

プロパティ (ID)|データ型|説明
:---|:---|:---
DeviceId|文字列|サービス内のデバイスの一意の識別子。
DeviceName|文字列|デバイスの完全修飾ドメイン名 (FQDN)。
DiskPaths|Array[string]|製品がデバイスにインストールされていることを示すディスク証拠。
EndOfSupportDate|文字列|このソフトウェアのサポートが終了または終了する日付。
EndOfSupportStatus|文字列|サポートの終了状態。 次の値を含めることができます。None、EOS バージョン、今後の EOS バージョン、EOS ソフトウェア、今後の EOS ソフトウェア。
NumberOfWeaknesses|Int|このデバイス上のこのソフトウェアの弱点の数。
OSPlatform|文字列|デバイスで実行されているオペレーティング システムのプラットフォーム。Windows 10やWindows 11など、同じファミリ内のバリエーションを持つ特定のオペレーティング システム。 詳細については [、「サポートされているオペレーティング システム、プラットフォーム、および機能](../defender-vulnerability-management/tvm-supported-os.md) 」を参照してください。
RbacGroupName|文字列|ロールベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。
rbacGroupId|文字列|ロールベースのアクセス制御 (RBAC) グループ ID。
RegistryPaths|Array[string]|製品がデバイスにインストールされていることを示すレジストリ証拠。
SoftwareFirstSeenTimestamp|文字列|このソフトウェアがデバイスで初めて表示された。
SoftwareName|文字列|ソフトウェア製品の名前。
SoftwareVendor|文字列|ソフトウェア ベンダーの名前。
SoftwareVersion|文字列|ソフトウェア製品のバージョン番号。

### <a name="23-properties-via-files"></a>2.3 プロパティ (ファイル経由)

プロパティ (ID)|データ型|説明
:---|:---|:---
ファイルをエクスポートする|配列\[文字列\]|組織の現在のスナップショットを保持しているファイルのダウンロード URL のリスト。
GeneratedTime|String|エクスポートが生成された時刻。

## <a name="3-export-software-vulnerabilities-assessment"></a>3. ソフトウェアの脆弱性評価をエクスポートする

すべてのデバイスについて、デバイス上のすべての既知の脆弱性とその詳細を返します。

### <a name="31-methods"></a>3.1 メソッド

Method|データ型|説明
:---|:---|:---
ソフトウェアの脆弱性評価 **のエクスポート (JSON 応答)**|調査コレクション See: [3.2 プロパティ (JSON 応答)](#32-properties-json-response)|DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId のすべての一意の組み合わせのエントリを含むテーブルを返します。 API は、組織内のすべてのデータを JSON 応答としてプルします。 この方法は、10 万個未満のデバイスのある小規模な組織に最適です。 応答はページ分割されるため、応答の@odata.nextLink フィールドを使用して、次の結果をフェッチできます。
ソフトウェア脆弱性評価のエクスポート **(ファイル経由)**|調査エンティティ参照: [3.3 プロパティ (ファイル経由)](#33-properties-via-files)|DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId のすべての一意の組み合わせのエントリを含むテーブルを返します。 この API ソリューションを使用すると、より大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織におすすめです。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storage からすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のように Azure Storage からすべてのデータをダウンロードできます: <ol><li>すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。</li><li>ダウンロード URL を使用してすべてのファイルをダウンロードし、データを好きなように処理します。</li></ol>
**Delta Export** ソフトウェアの脆弱性評価 **(JSON 応答)**|調査コレクション See: [3.4 Properties Delta export (JSON 応答)](#34-properties-delta-export-json-response)|DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId、EventTimestamp のすべての一意の組み合わせのエントリを含むテーブルを返します。 <p> API は、組織内のデータを JSON 応答としてプルします。 応答はページ分割されるため、応答の@odata.nextLink フィールドを使用して、次の結果をフェッチできます。 完全なソフトウェア脆弱性評価 (JSON 応答) は、組織のソフトウェア脆弱性評価のスナップショット全体をデバイス別に取得するために使用されます。 ただし、デルタ エクスポート API 呼び出しは、選択した日付と現在の日付 ("delta" API 呼び出し) の間に発生した変更のみをフェッチするために使用されます。 毎回大量のデータを含む完全なエクスポートを取得する代わりに、新しい脆弱性、修正された脆弱性、更新された脆弱性に関する特定の情報のみを取得します。 Delta export API 呼び出しを使用して、"修正された脆弱性の数" など、さまざまな KPI を計算することもできます。 または"組織に追加された新しい脆弱性の数? <p> ソフトウェアの脆弱性に対する Delta export API 呼び出しでは、対象となる日付範囲のみのデータが返されるため、完全な _エクスポート_ とは見なされません。

### <a name="32-properties-json-response"></a>3.2 プロパティ (JSON 応答)

プロパティ (ID)|データ型|説明
:---|:---|:---
CveId|文字列|共通の脆弱性と公開 (CVE) システムのセキュリティの脆弱性に割り当てられた一意の識別子。
CvssScore|文字列|CVE の CVSS スコア。
DeviceId|文字列|サービス内のデバイスの一意の識別子。
DeviceName|文字列|デバイスの完全修飾ドメイン名 (FQDN)。
DiskPaths|配列\[文字列\]|製品がデバイスにインストールされていることを示すディスク証拠。
ExploitabilityLevel|文字列|この脆弱性の悪用可能性レベル (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit)
FirstSeenTimestamp|文字列|この製品の CVE がデバイスで初めて確認されたとき。
Id|String|レコードの一意の識別子。
LastSeenTimestamp|文字列|デバイスで CVE が最後に表示された時刻。
OSPlatform|文字列|デバイスで実行されているオペレーティング システムのプラットフォーム。Windows 10やWindows 11など、同じファミリ内のバリエーションを持つ特定のオペレーティング システム。 詳細については [、「サポートされているオペレーティング システム、プラットフォーム、および機能](../defender-vulnerability-management/tvm-supported-os.md) 」を参照してください。
RbacGroupName|文字列|ロールベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。
rbacGroupId|文字列|ロールベースのアクセス制御 (RBAC) グループ ID。
RecommendationReference|文字列|このソフトウェアに関連する推奨事項 ID への参照。
RecommendedSecurityUpdate|文字列|ソフトウェア ベンダーが脆弱性に対処するために提供するセキュリティ更新プログラムの名前または説明。
RecommendedSecurityUpdateId|文字列|該当するセキュリティ更新プログラムの識別子、または対応するガイダンスまたはサポート情報 (KB) の記事の識別子。
レジストリ パス|Array[string]|製品がデバイスにインストールされていることを示すレジストリ証拠。
SecurityUpdateAvailable|ブール型|ソフトウェアでセキュリティ更新プログラムを使用できるかどうかを示します。
SoftwareName|文字列|ソフトウェア製品の名前。
SoftwareVendor|文字列|ソフトウェア ベンダーの名前。
SoftwareVersion|文字列|ソフトウェア製品のバージョン番号。
VulnerabilitySeverityLevel|文字列|CVSS スコアに基づいてセキュリティの脆弱性に割り当てられる重大度レベル。

### <a name="33-properties-via-files"></a>3.3 プロパティ (ファイル経由)

プロパティ (ID)|データ型|説明
:---|:---|:---
ファイルをエクスポートする|配列\[文字列\]|組織の現在のスナップショットを保持しているファイルのダウンロード URL のリスト。
GeneratedTime|String|エクスポートが生成された時刻。

### <a name="34-properties-delta-export-json-response"></a>3.4 プロパティ (delta export JSON response)

プロパティ (ID)|データ型|説明
:---|:---|:---
CveId |文字列|共通の脆弱性と公開 (CVE) システムのセキュリティの脆弱性に割り当てられた一意の識別子。
CvssScore|文字列|CVE の CVSS スコア。
DeviceId|文字列|サービス内のデバイスの一意の識別子。
DeviceName|文字列|デバイスの完全修飾ドメイン名 (FQDN)。
DiskPaths|Array[string]|製品がデバイスにインストールされていることを示すディスク証拠。
EventTimestamp|文字列|デルタ イベントが検出された時刻。
ExploitabilityLevel|文字列|脆弱性の悪用可能性レベル (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit)
FirstSeenTimestamp|文字列|製品の CVE がデバイスで初めて見られた時。
Id|String|レコードの一意の識別子。  
LastSeenTimestamp|文字列|デバイスで CVE が最後に表示された時刻。
OSPlatform|文字列|デバイスで実行されているオペレーティング システムのプラットフォーム。Windows 10やWindows 11など、同じファミリ内のバリエーションを持つ特定のオペレーティング システム。 詳細については [、「サポートされているオペレーティング システム、プラットフォーム、および機能](../defender-vulnerability-management/tvm-supported-os.md) 」を参照してください。
RbacGroupName|文字列|ロールベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。
RecommendationReference|文字列|このソフトウェアに関連する推奨事項 ID への参照。
RecommendedSecurityUpdate |文字列|ソフトウェア ベンダーが脆弱性に対処するために提供するセキュリティ更新プログラムの名前または説明。
RecommendedSecurityUpdateId |文字列|該当するガイダンスまたはサポート情報 (KB) の記事の該当するセキュリティ更新プログラムまたは識別子の識別子
RegistryPaths |Array[string]|製品がデバイスにインストールされていることを示すレジストリ証拠。
SoftwareName|文字列|ソフトウェア製品の名前。
SoftwareVendor|文字列|ソフトウェア ベンダーの名前。
SoftwareVersion|文字列|ソフトウェア製品のバージョン番号。
状態|文字列|**新規** (デバイスに導入された新しい脆弱性の場合)。 **修正されました** (デバイスに存在しなくなった脆弱性の場合、修復されたことを意味します)。 **更新されました** (変更されたデバイスの脆弱性の場合)。 可能な変更は、CVSS スコア、悪用可能性レベル、重大度レベル、DiskPaths、RegistryPaths、RecommendedSecurityUpdate です。
VulnerabilitySeverityLevel|文字列|CVSS スコアに基づいてセキュリティの脆弱性に割り当てられた重大度レベル。

## <a name="4-export-non-product-code-software-inventory-assessment"></a>4. 製品コード以外のソフトウェア インベントリ評価をエクスポートする

[共通プラットフォーム列挙 (CPE)](https://nvd.nist.gov/products/cpe) を持たないインストールされているすべてのソフトウェアと、各デバイスの詳細を返します。

### <a name="41-methods"></a>4.1 メソッド

|Method|データ型|説明|
|:---|:---|:---|
|製品コード以外のソフトウェア インベントリ評価 **をエクスポートする (JSON 応答)**|デバイス コレクション別の非製品コード ソフトウェア インベントリ。 参照: [4.2 プロパティ (JSON 応答)](#42-properties-json-response)|DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。 API は、組織内のすべてのデータを JSON 応答としてプルします。 この方法は、10 万個未満のデバイスのある小規模な組織に最適です。 応答はページ分割されるため、応答の@odata.nextLink フィールドを使用して、次の結果をフェッチできます。 |
| (**ファイル経由で)** 製品コード以外のソフトウェア インベントリ評価をエクスポートする|デバイス ファイル別の製品コード以外のソフトウェア インベントリ。 参照: [4.3 プロパティ (ファイル経由)](#43-properties-via-files)|DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。 この API ソリューションを使用すると、より大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織におすすめです。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storage からすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のように Azure Storage からデータをダウンロードできます。 <ol><li>組織のデータを含むダウンロード URL の一覧を取得するには、API を呼び出します</li><li>ダウンロード URL を使用してファイルをダウンロードし、必要に合ったデータを処理します。</li></ol> |

### <a name="42-properties-json-response"></a>4.2 プロパティ (JSON 応答)

プロパティ (ID)|データ型|説明
:---|:---|:---
DeviceId|string|サービス内のデバイスの一意の識別子。
DeviceName|string|デバイスの完全修飾ドメイン名 (FQDN)。
OSPlatform|string|デバイスで実行されているオペレーティング システムのプラットフォーム。 これらは、Windows 10やWindows 11など、同じファミリ内のバリエーションを持つ特定のオペレーティング システムです。 詳細については [、「サポートされているオペレーティング システム、プラットフォーム、および機能](../defender-vulnerability-management/tvm-supported-os.md) 」を参照してください。
RbacGroupName|string|ロールベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。
RbacGroupId|string|ロールベースのアクセス制御 (RBAC) グループ ID。
SoftwareLastSeenTimestamp|文字列|このソフトウェアがデバイスで最後に表示された時刻。
SoftwareName|string|ソフトウェア製品の名前。
SoftwareVendor|string|ソフトウェア ベンダーの名前。
SoftwareVersion|string|ソフトウェア製品のバージョン番号。

### <a name="43-properties-via-files"></a>4.3 プロパティ (ファイル経由)

プロパティ (ID)|データ型|説明
:---|:---|:---
ファイルをエクスポートする|配列\[文字列\]|組織の現在のスナップショットを保持しているファイルのダウンロード URL のリスト。
GeneratedTime|String|エクスポートが生成された時刻。

## <a name="see-also"></a>関連項目

- [デバイスごとのセキュリティで保護された構成評価をエクスポートする](get-assessment-secure-config.md)
- [デバイスごとのソフトウェア インベントリ評価をエクスポートする](get-assessment-software-inventory.md)
- [デバイスごとのソフトウェア脆弱性評価のエクスポート](get-assessment-software-vulnerabilities.md)
- [デバイスごとの cpe 以外のソフトウェア インベントリ評価をエクスポートする](get-assessment-non-cpe-software-inventory.md)

その他の関連

- [Microsoft Defender 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [組織の脆弱性](tvm-weaknesses.md)
