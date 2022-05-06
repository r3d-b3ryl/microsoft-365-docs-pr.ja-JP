---
title: デバイスごとの評価方法とプロパティをエクスポートする
description: "\"脅威と脆弱性の管理\" データをプルする API に関する情報を提供します。 さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。 一般に、各 API 呼び出しには、組織内のデバイスに必要なデータが含まれています。 データの量は大きくなる可能性があるため、2 つの方法で取得できます。"
keywords: api, apis, export assessment, per device assessment, per machine assessment, vulnerability assessment report, device Vulnerability Assessment, device vulnerability report, secure configuration Assessment, secure configuration report, secure configuration report, software Vulnerabilities assessment, software Vulnerability report, software vulnerability report, vulnerability report by machine,
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
ms.openlocfilehash: e820875a3350761824c3e4e67311e55507a9cb6f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778402"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>デバイスごとの評価方法とプロパティをエクスポートする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="api-description"></a>API の説明

デバイスごとに脅威と脆弱性の管理データをプルする API に関するメソッドとプロパティの詳細を提供します。 さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。 一般に、各 API 呼び出しには、組織内のデバイスに必要なデータが含まれています。

> [!Note]
>
> 特に明記されていない限り、一覧表示されているすべてのエクスポート評価方法は **_、完全なエクスポート_** と **_デバイス別_** ( **_デバイスごと_** とも呼ばれます) です。

さまざまな種類の情報を取得 (エクスポート) するために使用できる API メソッドは 3 つあります。

1. セキュリティで保護された構成の評価をエクスポートする

2. ソフトウェア在庫評価のエクスポート

3. ソフトウェアの脆弱性評価のエクスポート

メソッドごとに、さまざまな種類のデータを取得するための API 呼び出しが異なります。 データの量は大きくなる可能性があるため、取得する方法は 2 つあります。

- **Odata**  この API は、OData プロトコルに従って、組織内のすべてのデータを Json 応答としてプルします。 この方法は、 _100 K 未満のデバイスを持つ小規模な組織_ に最適です。 応答はページ分割されるため、応答の odata.nextLink フィールドを使用 \@して次の結果をフェッチできます。

- **ファイル経由** この API ソリューションを使用すると、大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織に推奨されます。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storageからすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のようにAzure Storageからすべてのデータをダウンロードできます。

  - すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。

  - ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。

( _OData_ または _ファイルを使用して_) 収集されるデータは、現在の状態の現在のスナップショットであり、履歴データは含まれません。 履歴データを収集するには、お客様が独自のデータ ストレージにデータを保存する必要があります。

## <a name="1-export-secure-configurations-assessment"></a>1. セキュリティで保護された構成の評価をエクスポートする

デバイスごとに、すべての構成とその状態を返します。

### <a name="11-methods"></a>1.1 メソッド

メソッド | データ型 | 説明
:---|:---|:---
セキュリティで保護された構成評価 **(OData)** をエクスポートする | デバイス コレクションによるセキュリティで保護された構成。 参照: [1.2 プロパティ (OData)](#12-properties-odata) | DeviceId、ConfigurationId のすべての一意の組み合わせのエントリを含むテーブルを返します。 この API は、OData プロトコルに従って、組織内のすべてのデータを Json 応答としてプルします。 この方法は、100 K 未満のデバイスを持つ小規模な組織に最適です。 応答はページ分割されるため、応答の@odata.nextLink フィールドを使用して、次の結果をフェッチできます。
セキュリティで保護された構成評価 **をエクスポートする (ファイル経由)** | デバイス コレクションによるセキュリティで保護された構成。 参照: [1.2 プロパティ (OData)](#12-properties-odata) | DeviceId、ConfigurationId のすべての一意の組み合わせのエントリを含むテーブルを返します。 この API ソリューションを使用すると、大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織に推奨されます。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storageからすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のようにAzure Storageからすべてのデータをダウンロードできます。  すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。 2.  ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。

### <a name="12-properties-odata"></a>1.2 プロパティ (OData)

プロパティ (ID) | データ型 | 説明
:---|:---|:---
ConfigurationCategory | string | 構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御
ConfigurationId | string | 特定の構成の一意の識別子
ConfigurationImpact | string | 構成が全体の構成スコアに与える影響の評価 (1-10)
ConfigurationName | string | 構成の表示名
ConfigurationSubcategory | string | 構成が属するサブカテゴリまたはサブグループ。 多くの場合、これは特定の機能または機能を説明します。
DeviceId | string | サービス内のデバイスの一意の識別子。
DeviceName | string | デバイスの完全修飾ドメイン名 (FQDN)。
IsApplicable | bool | 構成またはポリシーが適用可能かどうかを示します
IsCompliant | bool | 構成やポリシーが正しく構成されているかどうかを示します
IsExpectedUserImpact | bool | 構成が適用される場合にユーザーに影響を与えるかどうかを示します
OSPlatform | string | デバイスで実行されているオペレーティング システムのプラットフォーム。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 詳細については、tvm でサポートされているオペレーティング システムとプラットフォームを参照してください。
RbacGroupName | string | ロールベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。
RecommendationReference | string | このソフトウェアに関連する推奨事項 ID への参照。
Timestamp | string | デバイスで最後に構成が表示された時刻

### <a name="13-properties-via-files"></a>1.3 プロパティ (ファイル経由)

プロパティ (ID) | データ型 | 説明
:---|:---|:---
ファイルをエクスポートする | arraystring\[\] | 組織の現在のスナップショットを保持しているファイルのダウンロード URL の一覧。
GeneratedTime | string | エクスポートが生成された時刻。

## <a name="2-export-software-inventory-assessment"></a>2. ソフトウェア インベントリの評価をエクスポートする

インストールされているすべてのソフトウェアとその詳細を各デバイスに返します。

### <a name="21-methods"></a>2.1 メソッド

メソッド | データ型 | 説明
:---|:---|:---
ソフトウェア インベントリ評価 **のエクスポート (OData)** | デバイス コレクション別のソフトウェア インベントリ。 参照: [2.2 プロパティ (OData)](#22-properties-odata) | DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。 この API は、OData プロトコルに従って、組織内のすべてのデータを Json 応答としてプルします。 この方法は、100 K 未満のデバイスを持つ小規模な組織に最適です。 応答はページ分割されるため、応答の@odata.nextLink フィールドを使用して、次の結果をフェッチできます。
ソフトウェア インベントリ評価 **のエクスポート (ファイル経由)** | デバイス ファイル別のソフトウェア インベントリ。 参照: [2.3 プロパティ (ファイル経由)](#23-properties-via-files) | DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。 この API ソリューションを使用すると、大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織に推奨されます。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storageからすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のようにAzure Storageからすべてのデータをダウンロードできます。  すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。 2.  ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。

### <a name="22-properties-odata"></a>2.2 プロパティ (OData)

プロパティ (ID) | データ型 | 説明
:---|:---|:---
DeviceId | string | サービス内のデバイスの一意の識別子。
DeviceName | string | デバイスの完全修飾ドメイン名 (FQDN)。
DiskPaths | Array[string]  | 製品がデバイスにインストールされていることを示すディスク証拠。
EndOfSupportDate | string | このソフトウェアのサポートが終了または終了する日付。
EndOfSupportStatus | string | サポートの終了状態。 次の値を含めることができます。None、EOS バージョン、今後の EOS バージョン、EOS ソフトウェア、今後の EOS ソフトウェア。
ID | string | レコードの一意の識別子。
NumberOfWeaknesses | int|このデバイス上のこのソフトウェアの弱点の数
OSPlatform | string | デバイスで実行されているオペレーティング システムのプラットフォーム。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 詳細については、tvm でサポートされているオペレーティング システムとプラットフォームを参照してください。
RbacGroupName | string | ロールベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。
RegistryPaths | Array[string] | 製品がデバイスにインストールされていることを示すレジストリ証拠。
SoftwareFirstSeenTimestamp | string | このソフトウェアがデバイスで初めて表示された。
SoftwareName | string | ソフトウェア製品の名前。
SoftwareVendor | string | ソフトウェア ベンダーの名前。
SoftwareVersion | string | ソフトウェア製品のバージョン番号。

### <a name="23-properties-via-files"></a>2.3 プロパティ (ファイル経由)

プロパティ (ID) | データ型 | 説明
:---|:---|:---
ファイルをエクスポートする | arraystring\[\] | 組織の現在のスナップショットを保持しているファイルのダウンロード URL の一覧。
GeneratedTime | string | エクスポートが生成された時刻。

## <a name="3-export-software-vulnerabilities-assessment"></a>3. ソフトウェアの脆弱性評価をエクスポートする

すべてのデバイスについて、デバイス上のすべての既知の脆弱性とその詳細を返します。

### <a name="31-methods"></a>3.1 メソッド

メソッド | データ型 | 説明
:---|:---|:---
ソフトウェア脆弱性評価のエクスポート **(OData)** | 調査コレクション See: [3.2 プロパティ (OData)](#32-properties-odata) | DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId のすべての一意の組み合わせのエントリを含むテーブルを返します。 この API は、OData プロトコルに従って、組織内のすべてのデータを Json 応答としてプルします。 この方法は、100 K 未満のデバイスを持つ小規模な組織に最適です。 応答はページ分割されるため、応答の@odata.nextLink フィールドを使用して、次の結果をフェッチできます。
ソフトウェア脆弱性評価のエクスポート **(ファイル経由)** | 調査エンティティ参照: [3.3 プロパティ (ファイル経由)](#33-properties-via-files) | DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId のすべての一意の組み合わせのエントリを含むテーブルを返します。 この API ソリューションを使用すると、大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織に推奨されます。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storageからすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のようにAzure Storageからすべてのデータをダウンロードできます。  すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。 2.  ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。

### <a name="32-properties-odata"></a>3.2 プロパティ (OData)

プロパティ (ID) | データ型 | 説明
:---|:---|:---
CveId | string | 共通の脆弱性と公開 (CVE) システムのセキュリティの脆弱性に割り当てられた一意の識別子。
CvssScore | string | CVE の CVSS スコア。
DeviceId | string | サービス内のデバイスの一意の識別子。
DeviceName | string | デバイスの完全修飾ドメイン名 (FQDN)。
DiskPaths | Arraystring\[\] | 製品がデバイスにインストールされていることを示すディスク証拠。
ExploitabilityLevel | string | この脆弱性の悪用可能性レベル (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit)
FirstSeenTimestamp | string | この製品の CVE がデバイスで初めて確認されたとき。
ID | string | レコードの一意の識別子。
LastSeenTimestamp | string | デバイスで CVE が最後に表示された時刻。
OSPlatform | string | デバイスで実行されているオペレーティング システムのプラットフォーム。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 詳細については、tvm でサポートされているオペレーティング システムとプラットフォームを参照してください。
RbacGroupName | string | ロールベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。
RecommendationReference | string | このソフトウェアに関連する推奨事項 ID への参照。
RecommendedSecurityUpdate | string | ソフトウェア ベンダーが脆弱性に対処するために提供するセキュリティ更新プログラムの名前または説明。
RecommendedSecurityUpdateId | string | 該当するガイダンスまたはサポート情報 (KB) の記事の該当するセキュリティ更新プログラムまたは識別子の識別子
レジストリ パス配列\[文字列\] | 製品がデバイスにインストールされていることを示すレジストリ証拠。
SoftwareName | string | ソフトウェア製品の名前。
SoftwareVendor | string | ソフトウェア ベンダーの名前。
SoftwareVersion | string | ソフトウェア製品のバージョン番号。
VulnerabilitySeverityLevel | string | CVSS スコアと脅威の状況の影響を受ける動的な要因に基づいて、セキュリティの脆弱性に割り当てられた重大度レベル。

### <a name="33-properties-via-files"></a>3.3 プロパティ (ファイル経由)

プロパティ (ID) | データ型 | 説明
:---|:---|:---
ファイルをエクスポートする | arraystring\[\]  | 組織の現在のスナップショットを保持しているファイルのダウンロード URL の一覧。
GeneratedTime | string | エクスポートが生成された時刻。

## <a name="see-also"></a>関連項目

- [デバイスごとのセキュリティで保護された構成評価をエクスポートする](get-assessmnt-secure-cfg.md)

- [デバイスごとのソフトウェア インベントリ評価をエクスポートする](get-assessmnt-software-inventory.md)

- [デバイスごとのソフトウェア脆弱性評価のエクスポート](get-assessmnt-software-vulnerabilities.md)

その他の関連

- [リスクベースの脅威& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)

- [組織の脆弱性](tvm-weaknesses.md)
