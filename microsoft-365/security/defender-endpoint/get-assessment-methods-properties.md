---
title: デバイスごとの評価方法とプロパティのエクスポート
description: "\"データの取得\" を行う API に脅威と脆弱性の管理します。 さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。 一般に、各 API 呼び出しには、組織内のデバイスの必要なデータが含まれる。"
keywords: api、apis、エクスポート評価、デバイス評価あたり、マシン評価、脆弱性評価レポート、デバイスの脆弱性評価、デバイスの脆弱性レポート、セキュリティで保護された構成評価、セキュリティで保護された構成レポート、ソフトウェアの脆弱性評価、ソフトウェアの脆弱性レポート、マシン別の脆弱性レポート、
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 3f37ec12b7e54e0241e66def76d9ed2d6892b7a7
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53655733"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>デバイスごとの評価方法とプロパティのエクスポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="api-description"></a>API の説明

デバイス単位でデータを取得する API に脅威と脆弱性の管理プロパティの詳細を提供します。 さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。 一般に、各 API 呼び出しには、組織内のデバイスの必要なデータが含まれる。

> [!NOTE]
> 特に示されていない限り、一覧表示されているエクスポート評価方法はすべて、**** 完全なエクスポートと **_デバイス別_**(デバイス単位とも **_呼_** ばれます) です。

エクスポート評価 API を使用して、さまざまな種類の情報を取得 (エクスポート) できます。

- [1. セキュリティで保護された構成の評価をエクスポートする](#1-export-secure-configurations-assessment)
- [2. ソフトウェア インベントリ評価のエクスポート](#2-export-software-inventory-assessment)
- [3. ソフトウェアの脆弱性評価のエクスポート](#3-export-software-vulnerabilities-assessment)

エクスポート情報の種類に対応する API については、セクション 1、2、および 3 で説明します。

メソッドごとに、異なる種類のデータを取得する異なる API 呼び出しがあります。 データの量が多い場合は、次の 2 つの方法で取得できます。

- **JSON 応答**  API は、組織内のすべてのデータを JSON 応答として取得します。 この方法は _、100 K_ 未満のデバイスを持つ小規模な組織に最適です。 応答がページ分割されたので、応答から \@ odata.nextLink フィールドを使用して次の結果を取得できます。

- **ファイル経由** この API ソリューションを使用すると、大量のデータを高速かつ確実に取得できます。 そのため、100 K を超えるデバイスを使用する大規模な組織に推奨されます。 この API は、組織内のすべてのデータをダウンロード ファイルとして取得します。 応答には、すべてのデータをダウンロードする URL が含Azure Storage。 この API を使用すると、すべてのデータを次のようにAzure Storageダウンロードできます。
  - API を呼び出して、すべての組織データを含むダウンロード URL の一覧を取得します。
  - ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。

(JSON 応答またはファイルを使用 _して)_ 収集されるデータは、現在の状態の現在のスナップショットであり、歴史的なデータは含まれておりません。 過去のデータを収集するには、ユーザーがデータを独自のデータ ストレージに保存する必要があります。

## <a name="1-export-secure-configurations-assessment"></a>1. セキュリティで保護された構成の評価をエクスポートする

すべての構成とその状態をデバイス単位で返します。

### <a name="11-methods"></a>1.1 メソッド

メソッド|データ型|説明
:---|:---|:---
セキュリティで保護された構成評価 **のエクスポート (JSON 応答)**|デバイス コレクションによる構成をセキュリティで保護します。 参照: [1.2 プロパティ (JSON 応答)](#12-properties-json-response)|DeviceId、 ConfigurationId のすべての一意の組み合わせのエントリを含むテーブルを返します。 API は、組織内のすべてのデータを JSON 応答として取得します。 この方法は、100 K 未満のデバイスを持つ小規模な組織に最適です。 応答がページ分割されたので、応答から @odata.nextLink フィールドを使用して次の結果をフェッチできます。
セキュリティで保護された構成評価 **をエクスポートする (ファイル経由)**|デバイス コレクションによる構成をセキュリティで保護します。 参照: [1.3 プロパティ (ファイル経由)](#13-properties-via-files)|DeviceId、 ConfigurationId のすべての一意の組み合わせのエントリを含むテーブルを返します。 この API ソリューションを使用すると、大量のデータを高速かつ確実に取得できます。 そのため、100 K を超えるデバイスを使用する大規模な組織に推奨されます。 この API は、組織内のすべてのデータをダウンロード ファイルとして取得します。 応答には、すべてのデータをダウンロードする URL が含Azure Storage。 この API を使用すると、次のように、すべてのデータAzure Storageダウンロードできます。1。  API を呼び出して、すべての組織データを含むダウンロード URL の一覧を取得します。 2.  ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。

### <a name="12-properties-json-response"></a>1.2 プロパティ (JSON 応答)

プロパティ (ID)|データ型|説明
:---|:---|:---
ConfigurationCategory|string|構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御
ConfigurationId|string|特定の構成の一意の識別子
ConfigurationImpact|string|構成が全体の構成スコアに与える影響の評価 (1-10)
ConfigurationName|string|構成の表示名
ConfigurationSubcategory|string|構成が属するサブカテゴリまたはサブグループ。 多くの場合、これは特定の機能または機能を説明します。
DeviceId|string|サービス内のデバイスの一意の識別子。
DeviceName|string|デバイスの完全修飾ドメイン名 (FQDN)。
IsApplicable|bool|構成またはポリシーが適用可能かどうかを示します。
IsCompliant|bool|構成やポリシーが正しく構成されているかどうかを示します
IsExpectedUserImpact|bool|構成が適用される場合にユーザーに影響を与えるかどうかを示します。
OSPlatform|string|デバイスで実行されているオペレーティング システムのプラットフォーム。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 詳細については、「tvm でサポートされるオペレーティング システムとプラットフォーム」を参照してください。
RbacGroupName|string|役割ベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "割り当てられていない" になります。 組織に RBAC グループが含まれている場合、値は "None" になります。
RecommendationReference|string|このソフトウェアに関連する推奨事項 ID への参照。
Timestamp|string|デバイスで構成が最後に表示された時刻

### <a name="13-properties-via-files"></a>1.3 プロパティ (ファイル経由)

プロパティ (ID)|データ型|説明
:---|:---|:---
ファイルのエクスポート|配列 \[ 文字列\]|組織の現在のスナップショットを保持するファイルのダウンロード URL の一覧。
GeneratedTime|string|エクスポートが生成された時刻。

## <a name="2-export-software-inventory-assessment"></a>2. ソフトウェア インベントリ評価のエクスポート

インストールされているソフトウェアのすべてと、各デバイスの詳細を返します。

### <a name="21-methods"></a>2.1 メソッド

メソッド|データ型|説明
:---|:---|:---
ソフトウェア インベントリ評価のエクスポート **(JSON 応答)**|デバイス コレクション別のソフトウェア インベントリ。 参照: [2.2 プロパティ (JSON 応答)](#22-properties-json-response)|DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。 API は、組織内のすべてのデータを JSON 応答として取得します。 この方法は、100 K 未満のデバイスを持つ小規模な組織に最適です。 応答がページ分割されたので、応答から @odata.nextLink フィールドを使用して次の結果をフェッチできます。
ソフトウェア インベントリ評価のエクスポート **(ファイル経由)**|デバイス ファイル別のソフトウェア インベントリ。 参照: [2.3 プロパティ (ファイル経由)](#23-properties-via-files)|DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。 この API ソリューションを使用すると、大量のデータを高速かつ確実に取得できます。 そのため、100 K を超えるデバイスを使用する大規模な組織に推奨されます。 この API は、組織内のすべてのデータをダウンロード ファイルとして取得します。 応答には、すべてのデータをダウンロードする URL が含Azure Storage。 この API を使用すると、次のように、すべてのデータAzure Storageダウンロードできます。1。  API を呼び出して、すべての組織データを含むダウンロード URL の一覧を取得します。 2.  ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。

### <a name="22-properties-json-response"></a>2.2 プロパティ (JSON 応答)

プロパティ (ID)|データ型|説明
:---|:---|:---
DeviceId|string|サービス内のデバイスの一意の識別子。
DeviceName|string|デバイスの完全修飾ドメイン名 (FQDN)。
DiskPaths|Array[string]|製品がデバイスにインストールされていることを示すディスク証拠。
EndOfSupportDate|string|このソフトウェアのサポートが終了または終了する日付。
EndOfSupportStatus|string|サポートの状態の終了。 これらの可能な値を含めることができます。 なし、EOS バージョン、今後の EOS バージョン、EOS ソフトウェア、今後の EOS ソフトウェア。
ID|string|レコードの一意の識別子。
NumberOfWeaknesses|整数|このデバイス上のこのソフトウェアの弱点の数
OSPlatform|string|デバイスで実行されているオペレーティング システムのプラットフォーム。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 詳細については、「tvm でサポートされるオペレーティング システムとプラットフォーム」を参照してください。
RbacGroupName|string|役割ベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "割り当てられていない" になります。 組織に RBAC グループが含まれている場合、値は "None" になります。
RegistryPaths|Array[string]|製品がデバイスにインストールされていることを示すレジストリ証拠。
SoftwareFirstSeenTimestamp|string|このソフトウェアがデバイスで初めて見られた。
SoftwareName|string|ソフトウェア製品の名前。
SoftwareVendor|string|ソフトウェア ベンダーの名前。
SoftwareVersion|string|ソフトウェア製品のバージョン番号。

### <a name="23-properties-via-files"></a>2.3 プロパティ (ファイル経由)

プロパティ (ID)|データ型|説明
:---|:---|:---
ファイルのエクスポート|配列 \[ 文字列\]|組織の現在のスナップショットを保持するファイルのダウンロード URL の一覧。
GeneratedTime|string|エクスポートが生成された時刻。

## <a name="3-export-software-vulnerabilities-assessment"></a>3. ソフトウェアの脆弱性評価のエクスポート

すべてのデバイスについて、デバイス上のすべての既知の脆弱性とその詳細を返します。

### <a name="31-methods"></a>3.1 メソッド

メソッド|データ型|説明
:---|:---|:---
ソフトウェアの脆弱性評価のエクスポート **(JSON 応答)**|調査コレクション 参照: [3.2 プロパティ (JSON 応答)](#32-properties-json-response)|DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId のすべての一意の組み合わせのエントリを含むテーブルを返します。 API は、組織内のすべてのデータを JSON 応答として取得します。 この方法は、100 K 未満のデバイスを持つ小規模な組織に最適です。 応答がページ分割されたので、応答から @odata.nextLink フィールドを使用して次の結果をフェッチできます。
ソフトウェアの脆弱性評価のエクスポート **(ファイル経由)**|調査エンティティ参照: [3.3 プロパティ (ファイル経由)](#33-properties-via-files)|DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId のすべての一意の組み合わせのエントリを含むテーブルを返します。 この API ソリューションを使用すると、大量のデータを高速かつ確実に取得できます。 そのため、100 K を超えるデバイスを使用する大規模な組織に推奨されます。 この API は、組織内のすべてのデータをダウンロード ファイルとして取得します。 応答には、すべてのデータをダウンロードする URL が含Azure Storage。 この API を使用すると、次のように、すべてのデータAzure Storageダウンロードできます。1。  API を呼び出して、すべての組織データを含むダウンロード URL の一覧を取得します。 2.  ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。
**デルタ エクスポート ソフトウェア** の脆弱性評価 **(JSON 応答)**|調査コレクション 参照: [3.4 Properties Delta エクスポート (JSON 応答)](#34-properties-delta-export-json-response)|DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId、EventTimestamp の各一意の組み合わせのエントリを含むテーブルを返します。 <br><br> API は、JSON 応答として組織内のデータをプルします。 応答がページ分割されたので、応答から @odata.nextLink フィールドを使用して次の結果をフェッチできます。 デバイス別に組織のソフトウェア脆弱性評価のスナップショット全体を取得するために使用される完全なソフトウェア脆弱性評価 (JSON 応答) とは異なり、デルタ エクスポート API 呼び出しは、選択した日付と現在の日付 ("デルタ" API 呼び出し) の間に発生した変更のみを取得するために使用されます。 毎回大量のデータを含む完全なエクスポートを取得する代わりに、新規、固定、および更新された脆弱性に関する特定の情報のみを取得します。 デルタ エクスポート API 呼び出しを使用して、「修正された脆弱性の数」など、さまざまな KPI を計算することもできます。 または "組織に追加された新しい脆弱性の数"  <br><br> ソフトウェアの脆弱性に対するデルタ エクスポート API 呼び出しは、対象の日付範囲のデータのみを返すので、完全なエクスポートとは _見なされません_。

### <a name="32-properties-json-response"></a>3.2 プロパティ (JSON 応答)

プロパティ (ID)|データ型|説明
:---|:---|:---
CveId|string|共通の脆弱性と露出 (CVE) システムのセキュリティの脆弱性に割り当てられた一意の識別子。
CvssScore|string|CVE の CVSS スコア。
DeviceId|string|サービス内のデバイスの一意の識別子。
DeviceName|string|デバイスの完全修飾ドメイン名 (FQDN)。
DiskPaths|配列 \[ 文字列\]|製品がデバイスにインストールされていることを示すディスク証拠。
ExploitabilityLevel|string|この脆弱性の悪用レベル (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit)
FirstSeenTimestamp|string|この製品の CVE がデバイスで初めて表示された場合。
ID|string|レコードの一意の識別子。
LastSeenTimestamp|string|デバイスで CVE が最後に表示された時刻。
OSPlatform|string|デバイスで実行されているオペレーティング システムのプラットフォーム。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 詳細については、「tvm でサポートされるオペレーティング システムとプラットフォーム」を参照してください。
RbacGroupName|string|役割ベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "割り当てられていない" になります。 組織に RBAC グループが含まれている場合、値は "None" になります。
RecommendationReference|string|このソフトウェアに関連する推奨事項 ID への参照。
RecommendedSecurityUpdate|string|ソフトウェア ベンダーが脆弱性に対処するために提供するセキュリティ更新プログラムの名前または説明。
RecommendedSecurityUpdateId|string|対応するガイダンスまたはナレッジ ベース (KB) 記事の該当するセキュリティ更新プログラムまたは識別子の識別子
レジストリ パス配列 \[ の文字列\]|製品がデバイスにインストールされていることを示すレジストリ証拠。
SoftwareName|string|ソフトウェア製品の名前。
SoftwareVendor|string|ソフトウェア ベンダーの名前。
SoftwareVersion|string|ソフトウェア製品のバージョン番号。
VulnerabilitySeverityLevel|string|CVSS スコアに基づくセキュリティ脆弱性に割り当てられた重大度レベルと、脅威の状況の影響を受ける動的要因。

### <a name="33-properties-via-files"></a>3.3 プロパティ (ファイル経由)

プロパティ (ID)|データ型|説明
:---|:---|:---
ファイルのエクスポート|配列 \[ 文字列\]|組織の現在のスナップショットを保持するファイルのダウンロード URL の一覧。
GeneratedTime|string|エクスポートが生成された時刻。

### <a name="34-properties-delta-export-json-response"></a>3.4 プロパティ (デルタ エクスポート JSON 応答)

プロパティ (ID)|データ型|説明
:---|:---|:---
CveId |string|共通の脆弱性と露出 (CVE) システムのセキュリティの脆弱性に割り当てられた一意の識別子。
CvssScore|string|CVE の CVSS スコア。
DeviceId|string|サービス内のデバイスの一意の識別子。
DeviceName|string|デバイスの完全修飾ドメイン名 (FQDN)。
DiskPaths|Array[string]|製品がデバイスにインストールされていることを示すディスク証拠。
EventTimestamp|String|このデルタ イベントが見つかった時刻。
ExploitabilityLevel|string|この脆弱性の悪用レベル (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit)
FirstSeenTimestamp|string|この製品の CVE がデバイスで初めて表示された場合。
ID|string|レコードの一意の識別子。  
LastSeenTimestamp|string|デバイスで CVE が最後に表示された時刻。
OSPlatform|string|デバイスで実行されているオペレーティング システムのプラットフォーム。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 詳細については、「tvm でサポートされるオペレーティング システムとプラットフォーム」を参照してください。
RbacGroupName|string|役割ベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "割り当てられていない" になります。 組織に RBAC グループが含まれている場合、値は "None" になります。
RecommendationReference|string|このソフトウェアに関連する推奨事項 ID への参照。
RecommendedSecurityUpdate |string|ソフトウェア ベンダーが脆弱性に対処するために提供するセキュリティ更新プログラムの名前または説明。
RecommendedSecurityUpdateId |string|対応するガイダンスまたはナレッジ ベース (KB) 記事の該当するセキュリティ更新プログラムまたは識別子の識別子
RegistryPaths |Array[string]|製品がデバイスにインストールされていることを示すレジストリ証拠。
SoftwareName|string|ソフトウェア製品の名前。
SoftwareVendor|string|ソフトウェア ベンダーの名前。
SoftwareVersion|string|ソフトウェア製品のバージョン番号。
状態|String|**New**  (デバイスに導入された新しい脆弱性の場合)。 **固定**  (デバイス上にもう存在しない脆弱性の場合は、修復されたという意味です)。 **更新**  (変更されたデバイスの脆弱性の場合)。 変更の可能性は、CVSS スコア、悪用可能性レベル、重大度レベル、DiskPaths、RegistryPaths、RecommendedSecurityUpdate などです。
VulnerabilitySeverityLevel|string|CVSS スコアに基づくセキュリティ脆弱性に割り当てられた重大度レベルと、脅威の状況の影響を受ける動的要因。

## <a name="see-also"></a>関連項目

- [デバイスごとのセキュリティで保護された構成評価をエクスポートする](get-assessment-secure-config.md)
- [デバイスごとのソフトウェア インベントリ評価のエクスポート](get-assessment-software-inventory.md)
- [デバイスごとのソフトウェアの脆弱性評価のエクスポート](get-assessment-software-vulnerabilities.md)

その他の関連

- [リスクベースの脅威& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [組織の脆弱性](tvm-weaknesses.md)
