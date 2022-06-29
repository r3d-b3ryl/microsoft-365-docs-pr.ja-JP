---
title: デバイスごとのソフトウェア脆弱性評価のエクスポート
description: API 応答はデバイスごとに行われ、公開されているデバイスにインストールされている脆弱なソフトウェアと、これらのソフトウェア製品の既知の脆弱性が含まれています。 このテーブルには、オペレーティング システム情報、CVE ID、および脆弱性の重要度の情報も含まれます。
keywords: api, apis, export assessment, per device assessment, Vulnerability Assessment report, device Vulnerability assessment, device vulnerability report, secure configuration assessment, secure configuration report, software vulnerabilities assessment, software Vulnerability report, software vulnerability report, vulnerability report by machine,
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
ms.openlocfilehash: 52dc38d3675ffe15bd781aefaecede9d1783bac3
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66487172"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a>デバイスごとのソフトウェア脆弱性評価のエクスポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender 脆弱性の管理](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

デバイスごとに、すべての既知のソフトウェアの脆弱性とそのすべてのデバイスの詳細を返します。

異なる API 呼び出しは、さまざまな種類のデータを取得します。 データの量は大きくなる可能性があるため、取得する方法は 2 つあります。

1. [ソフトウェアの脆弱性評価 **JSON 応答** をエクスポートする](#1-export-software-vulnerabilities-assessment-json-response) API は、組織内のすべてのデータを Json 応答としてプルします。 この方法は、 _100 K 未満のデバイスを持つ小規模な組織_ に最適です。 応答はページ分割されるため、応答の odata.nextLink フィールドを使用 \@して次の結果をフェッチできます。

2. [**ファイルを使用して** ソフトウェアの脆弱性評価をエクスポート](#2-export-software-vulnerabilities-assessment-via-files)するこの API ソリューションを使用すると、大量のデータをより迅速かつ確実にプルできます。 100 K を超えるデバイスを使用する大規模な組織では、Via-files をお勧めします。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storage からすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のように Azure Storage からすべてのデータをダウンロードできます。
   - すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。
   - ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。

3. [Delta Export ソフトウェアの脆弱性評価 **JSON 応答**](#3-delta-export-software-vulnerabilities-assessment-json-response)  DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId、EventTimestamp のすべての一意の組み合わせのエントリを含むテーブルを返します。
API は、組織内のデータを Json 応答としてプルします。 応答はページ分割されるため、応答の@odata.nextLink フィールドを使用して、次の結果をフェッチできます。

   完全な "ソフトウェア脆弱性評価 (JSON 応答)" は、組織のソフトウェア脆弱性評価のスナップショット全体をデバイス別に取得するために使用されます。 ただし、デルタ エクスポート API 呼び出しは、選択した日付と現在の日付 ("delta" API 呼び出し) の間に発生した変更のみをフェッチするために使用されます。 毎回大量のデータを含む完全なエクスポートを取得する代わりに、新しい脆弱性、修正された脆弱性、更新された脆弱性に関する特定の情報のみを取得します。 差分エクスポート JSON 応答 API 呼び出しを使用して、"修正された脆弱性の数" など、さまざまな KPI を計算することもできます。 または"組織に追加された新しい脆弱性の数?

   ソフトウェアの脆弱性に対する Delta export JSON 応答 API 呼び出しでは、対象となる日付範囲のみのデータが返されるため、完全な _エクスポート_ とは見なされません。

( _Json 応答_ または _ファイルを使用して_) 収集されるデータは、現在の状態の現在のスナップショットです。 履歴データは含まれません。 履歴データを収集するには、お客様が独自のデータ ストレージにデータを保存する必要があります。

> [!NOTE]
> 特に明記されていない限り、一覧表示されているすべてのエクスポート評価方法は **_、完全なエクスポート_** と **_デバイス別_** ( **_デバイスごと_** とも呼ばれます) です。

## <a name="1-export-software-vulnerabilities-assessment-json-response"></a>1. ソフトウェア脆弱性評価のエクスポート (JSON 応答)

### <a name="11-api-method-description"></a>1.1 API メソッドの説明

この API 応答には、デバイスごとにインストールされているソフトウェアのすべてのデータが含まれます。 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID のすべての一意の組み合わせのエントリを含むテーブルを返します。

#### <a name="111-limitations"></a>1.1.1 制限事項

- 最大ページ サイズは 200,000 です。
- この API のレート制限は、1 分あたり 30 回の呼び出しと 1 時間あたり 1,000 回の呼び出しです。

### <a name="12-permissions"></a>1.2 アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API を使用する」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
---|---|---
アプリケーション|Vulnerability.Read.All|\'脅威と脆弱性の管理の脆弱性情報を読み取る\'
委任 (職場または学校のアカウント)|Vulnerability.Read|\'脅威と脆弱性の管理の脆弱性情報を読み取る\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a>1.4 パラメーター

- pageSize (既定値は 50,000): 応答する結果の数。
- $top: 返される結果の数 (@odata.nextLink が返されないため、すべてのデータがプルされるわけではありません)。

### <a name="15-properties"></a>1.5 プロパティ

> [!NOTE]
>
> - 各レコードは約 1 KB のデータです。 正しい pageSize パラメーターを選択するときは、これを考慮する必要があります。
> - 応答で追加の列が返される場合があります。 これらの列は一時的なものであり、削除される可能性があります。ドキュメント化された列のみを使用してください。
> - 次の表で定義されているプロパティは、プロパティ ID でアルファベット順に一覧表示されます。 この API を実行する場合、結果の出力は必ずしもこの表に示されているのと同じ順序で返されるとは限りません。

<br>

****

プロパティ (ID)|データ型|説明|返された値の例
:---|:---|:---|:---
CveId|String|共通の脆弱性と公開 (CVE) システムのセキュリティの脆弱性に割り当てられた一意の識別子。|CVE-2020-15992
CvssScore|String|CVE の CVSS スコア。|6.2
DeviceId|String|サービス内のデバイスの一意の識別子。|9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName|String|デバイスの完全修飾ドメイン名 (FQDN)。|johnlaptop.europe.contoso.com
DiskPaths|配列\[文字列\]|製品がデバイスにインストールされていることを示すディスク証拠。|[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]
ExploitabilityLevel|String|この脆弱性の悪用可能性レベル (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit)|ExploitIsInKit
FirstSeenTimestamp|String|この製品の CVE がデバイスで初めて確認されたとき。|2020-11-03 10:13:34.8476880
Id|String|レコードの一意の識別子。|123ABG55_573AG&mnp!
LastSeenTimestamp|String|デバイスで CVE が最後に表示された時刻。|2020-11-03 10:13:34.8476880
OSPlatform|String|デバイスで実行されているオペレーティング システムのプラットフォーム。 このプロパティは、Windows 10やWindows 11など、同じファミリ内のバリエーションを持つ特定のオペレーティング システムを示します。 詳細については、tvm でサポートされているオペレーティング システムとプラットフォームを参照してください。|Windows10 とWindows 11
RbacGroupName|String|ロールベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。|サーバー
RecommendationReference|String|このソフトウェアに関連する推奨事項 ID への参照。|va _--microsoft-_-silverlight
RecommendedSecurityUpdate (省略可能)|String|ソフトウェア ベンダーが脆弱性に対処するために提供するセキュリティ更新プログラムの名前または説明。|2020 年 4 月のセキュリティ 更新
RecommendedSecurityUpdateId (省略可能)|String|該当するガイダンスまたはサポート情報 (KB) の記事の該当するセキュリティ更新プログラムまたは識別子の識別子|4550961
RegistryPaths|配列\[文字列\]|製品がデバイスにインストールされていることを示すレジストリ証拠。|[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]
SecurityUpdateAvailable|Boolean|ソフトウェアでセキュリティ更新プログラムを使用できるかどうかを示します。| 指定できる値は true または false です。
SoftwareName|String|ソフトウェア製品の名前。|Chrome
SoftwareVendor|String|ソフトウェア ベンダーの名前。|Google
SoftwareVersion|String|ソフトウェア製品のバージョン番号。|81.0.4044.138
VulnerabilitySeverityLevel|String|CVSS スコアと脅威の状況の影響を受ける動的な要因に基づいて、セキュリティの脆弱性に割り当てられた重大度レベル。|中
|

### <a name="16-examples"></a>1.6 例

#### <a name="161-request-example"></a>1.6.1 要求の例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a>1.6.2 応答の例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge",
            "securityUpdateAvailable": true
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework",
            "securityUpdateAvailable": true
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection",
            "securityUpdateAvailable": true
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive",
            "securityUpdateAvailable": true
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10" "Windows_11",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10" "va-_-microsoft-_-windows_11",
            "securityUpdateAvailable": true
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a>2. ソフトウェアの脆弱性評価をエクスポートする (ファイル経由)

### <a name="21-api-method-description"></a>2.1 API メソッドの説明

この API 応答には、デバイスごとにインストールされているソフトウェアのすべてのデータが含まれます。 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID のすべての一意の組み合わせのエントリを含むテーブルを返します。

#### <a name="212-limitations"></a>2.1.2 制限事項

この API のレート制限は、1 分あたり 5 回の呼び出しと 1 時間あたり 20 回の呼び出しです。

### <a name="22-permissions"></a>2.2 アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API を使用する」を参照してください](apis-intro.md)。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
---|---|---
アプリケーション|Vulnerability.Read.All|\'脅威と脆弱性の管理の脆弱性情報を読み取る\'
委任 (職場または学校のアカウント)|Vulnerability.Read|\'脅威と脆弱性の管理の脆弱性情報を読み取る\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a>2.4 パラメーター

- sasValidHours: ダウンロード URL が有効になる時間数 (最大 24 時間)。

### <a name="25-properties"></a>2.5 プロパティ

> [!NOTE]
>
> - ファイルは、複数行の Json 形式の gzip 圧縮&です。
> - ダウンロード URL は 3 時間だけ有効です。それ以外の場合は、パラメーターを使用できます。
> - データの最大ダウンロード速度を確保するために、データが存在するのと同じ Azure リージョンからダウンロードしていることを確認できます。
>
> - 各レコードは約 1 KB のデータです。 正しい pageSize パラメーターを選択するときは、これを考慮する必要があります。
> - 応答で追加の列が返される場合があります。 これらの列は一時的なものであり、削除される可能性があります。ドキュメント化された列のみを使用してください。

<br>

****

プロパティ (ID)|データ型|説明|返された値の例
:---|:---|:---|:---
ファイルをエクスポートする|配列\[文字列\]|組織の現在のスナップショットを保持しているファイルのダウンロード URL の一覧。|["https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1", "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2"]
GeneratedTime|String|エクスポートが生成された時刻。|2021-05-20T08:00:00Z
|

### <a name="26-examples"></a>2.6 例

#### <a name="261-request-example"></a>2.6.1 要求の例

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a>2.6.2 応答の例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="3-delta-export-software-vulnerabilities-assessment-json-response"></a>3. 差分エクスポート ソフトウェアの脆弱性評価 (JSON 応答)

### <a name="31-api-method-description"></a>3.1 API メソッドの説明

DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CveId のすべての一意の組み合わせのエントリを含むテーブルを返します。 API は、組織内のデータを Json 応答としてプルします。 応答はページ分割されるため、応答の@odata.nextLink フィールドを使用して、次の結果をフェッチできます。 完全なソフトウェア脆弱性評価 (JSON 応答) (デバイス別に組織のソフトウェア脆弱性評価のスナップショット全体を取得するために使用) とは異なり、差分エクスポート JSON 応答 API 呼び出しは、選択した日付と現在の日付 ("delta" API 呼び出し) の間に発生した変更のみをフェッチするために使用されます。 毎回大量のデータを含む完全なエクスポートを取得する代わりに、新しい脆弱性、修正された脆弱性、更新された脆弱性に関する特定の情報のみを取得します。 差分エクスポート JSON 応答 API 呼び出しを使用して、"修正された脆弱性の数" など、さまざまな KPI を計算することもできます。 または"組織に追加された新しい脆弱性の数?

> [!NOTE]
> デバイス API 呼び出しによる完全なエクスポート ソフトウェアの脆弱性評価を少なくとも週に 1 回使用することを強くお勧めします。この追加のエクスポート ソフトウェアの脆弱性は、デバイス (delta) API 呼び出しによってその他のすべての曜日に変更されます。 他の Assessments JSON 応答 API とは異なり、"delta export" は完全なエクスポートではありません。 差分エクスポートには、選択した日付と現在の日付 ("delta" API 呼び出し) の間に発生した変更のみが含まれます。

#### <a name="311-limitations"></a>3.1.1 制限事項

- 最大ページ サイズは 200,000 です。
- sinceTime パラメーターの最大日数は 14 日です。
- この API のレート制限は、1 分あたり 30 回の呼び出しと 1 時間あたり 1,000 回の呼び出しです。

### <a name="32-permissions"></a>3.2 アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API を使用する」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
---|---|---
アプリケーション|Vulnerability.Read.All|'脅威と脆弱性管理の脆弱性情報の読み取り'
委任 (職場または学校のアカウント)|Vulnerability.Read|'脅威と脆弱性管理の脆弱性情報の読み取り'

### <a name="33-url"></a>3.3 URL

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine
```

### <a name="34-parameters"></a>3.4 パラメーター

- sinceTime (必須): 選択した時刻と今日の間のデータ。
- pageSize (既定値は 50,000): 応答の結果の数。
- $top: 返される結果の数 (@odata.nextLink を返すわけではないため、すべてのデータがプルされるわけではありません)。

### <a name="35-properties"></a>3.5 プロパティ

返される各レコードには、デバイス API による完全なエクスポート ソフトウェア脆弱性評価のすべてのデータに加えて、  _**EventTimestamp**_ と Status という 2 つのフィールドが含 _**まれます**_。

> [!NOTE]
>
> - 応答で追加の列が返される場合があります。 これらの列は一時的なものであり、削除される可能性があるため、ドキュメント化された列のみを使用してください。
> - 次の表で定義されているプロパティは、プロパティ ID でアルファベット順に一覧表示されます。 この API を実行する場合、結果の出力は必ずしもこの表に示されているのと同じ順序で返されるとは限りません。

<br>

****

プロパティ (ID)|データ型|説明|戻り値の例
:---|:---|:---|:---
CveId |String|共通の脆弱性と公開 (CVE) システムのセキュリティの脆弱性に割り当てられた一意の識別子。|CVE-2020-15992  
CvssScore|String|CVE の CVSS スコア。|6.2  
DeviceId|String|サービス内のデバイスの一意の識別子。|9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1  
DeviceName|String|デバイスの完全修飾ドメイン名 (FQDN)。|johnlaptop.europe.contoso.com  
DiskPaths|Array[string]|製品がデバイスにインストールされていることを示すディスク証拠。|["C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe"]  
EventTimestamp|String|この差分イベントが検出された時刻。|2021-01-11T11:06:08.291Z
ExploitabilityLevel|String|この脆弱性の悪用可能性レベル (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit)|ExploitIsInKit  
FirstSeenTimestamp|String|この製品の CVE がデバイスで初めて確認されたとき。|2020-11-03 10:13:34.8476880  
Id|String|レコードの一意の識別子。|123ABG55_573AG&mnp!  
LastSeenTimestamp|String|デバイスで CVE が最後に表示された時刻。|2020-11-03 10:13:34.8476880  
OSPlatform|String|デバイスで実行されているオペレーティング システムのプラットフォーム。Windows 10やWindows 11など、同じファミリ内のバリエーションを持つ特定のオペレーティング システム。 詳細については、tvm でサポートされているオペレーティング システムとプラットフォームを参照してください。|Windows10 とWindows 11 
RbacGroupName|String|ロールベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。|サーバー  
RecommendationReference|文字列|このソフトウェアに関連する推奨事項 ID への参照。|va--microsoft--silverlight  
RecommendedSecurityUpdate |String|ソフトウェア ベンダーが脆弱性に対処するために提供するセキュリティ更新プログラムの名前または説明。|2020 年 4 月のセキュリティ 更新  
RecommendedSecurityUpdateId |String|該当するガイダンスまたはサポート情報 (KB) の記事の該当するセキュリティ更新プログラムまたは識別子の識別子|4550961  
RegistryPaths |Array[string]|製品がデバイスにインストールされていることを示すレジストリ証拠。|[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]  
SoftwareName|String|ソフトウェア製品の名前。|Chrome  
SoftwareVendor|String|ソフトウェア ベンダーの名前。|Google  
SoftwareVersion|String|ソフトウェア製品のバージョン番号。|81.0.4044.138  
状態|String|**新規** (デバイスに導入された新しい脆弱性の場合) (1) **修正されました** (この脆弱性がデバイスにもう存在しない場合、修復されたことを意味します)。 (2) **更新 (** デバイスの脆弱性が変更された場合)。 可能な変更は、CVSS スコア、悪用可能性レベル、重大度レベル、DiskPaths、RegistryPaths、RecommendedSecurityUpdate です。 |Fixed
VulnerabilitySeverityLevel|String|セキュリティの脆弱性に割り当てられている重大度レベル。 これは、CVSS スコアと、脅威の状況の影響を受けた動的な要因に基づいています。|中
|

#### <a name="clarifications"></a>説明

- ソフトウェアがバージョン 1.0 からバージョン 2.0 に更新され、両方のバージョンが CVE-A に公開されている場合は、次の 2 つの個別のイベントを受け取ります。
   1. 修正済み: バージョン 1.0 の CVE-A が修正されました。
   1. 新規: バージョン 2.0 の CVE-A が追加されました。

- 特定の脆弱性 (CVE-A など) がバージョン 1.0 のソフトウェアで特定の時刻 (たとえば、1 月 10 日) に最初に見られ、数日後にそのソフトウェアが同じ CVE-A にも公開されているバージョン 2.0 に更新された場合、次の 2 つの別々のイベントが発生します。
   1. 修正済み: CVE-X、FirstSeenTimestamp 1 月 10 日バージョン 1,0。
   1. 新機能: CVE-X、FirstSeenTimestamp 1 月 10 日バージョン 2.0。

### <a name="36-examples"></a>3.6 例

#### <a name="361-request-example"></a>3.6.1 要求の例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a>3.6.2 応答の例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)",
    "value": [
        {
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__",
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0.19042.685",
            "osArchitecture": "x64",
            "softwareVendor": "google",
            "softwareName": "chrome",
            "softwareVersion": "87.0.4280.88",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe"
            ],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome"
            ],
            "lastSeenTimestamp": "2021-01-04 00:29:42",
            "firstSeenTimestamp": "2020-11-06 03:12:44",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-google-_-chrome",
            "status": "Fixed",
            "eventTimestamp": "2021-01-11T11:06:08.291Z"
        },
        {
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__",
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0.18363.1256",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.64.329.3",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-11 19:49:48",
            "firstSeenTimestamp": "2020-12-07 18:25:47",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive",
            "status": "Fixed",
            "eventTimestamp": "2021-01-11T11:06:08.291Z"
        },
        {
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_",
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0.19042.685",
            "osArchitecture": "x64",
            "softwareVendor": "mozilla",
            "softwareName": "firefox",
            "softwareVersion": "83.0.0.0",
            "cveId": "CVE-2020-26971",
            "vulnerabilitySeverityLevel": "High",
            "recommendedSecurityUpdate": "193220",
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe"
            ],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)"
            ],
            "lastSeenTimestamp": "2021-01-05 17:04:30",
            "firstSeenTimestamp": "2020-05-06 12:42:19",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-mozilla-_-firefox",
            "status": "Fixed",
            "eventTimestamp": "2021-01-11T11:06:08.291Z"
        },
        {
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__",
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0.19042.685",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "project",
            "softwareVersion": "16.0.13701.20000",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us"
            ],
            "lastSeenTimestamp": "2021-01-03 23:38:03",
            "firstSeenTimestamp": "2019-08-01 22:56:12",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-project",
            "status": "Fixed",
            "eventTimestamp": "2021-01-11T11:06:08.291Z"
        },
        {
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_",
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0.18363.1256",
            "osArchitecture": "x64",
            "softwareVendor": "google",
            "softwareName": "chrome",
            "softwareVersion": "81.0.4044.138",
            "cveId": "CVE-2020-16011",
            "vulnerabilitySeverityLevel": "High",
            "recommendedSecurityUpdate": "ADV 200002",
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe"
            ],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}"
            ],
            "lastSeenTimestamp": "2020-12-10 22:45:41",
            "firstSeenTimestamp": "2020-07-26 02:13:43",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-google-_-chrome",
            "status": "Fixed",
            "eventTimestamp": "2021-01-11T11:06:08.291Z"
        }
    ],
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="see-also"></a>関連項目

- [デバイスごとの評価方法とプロパティをエクスポートする](get-assessment-methods-properties.md)
- [デバイスごとのセキュリティで保護された構成評価をエクスポートする](get-assessment-secure-config.md)
- [デバイスごとのソフトウェア インベントリ評価をエクスポートする](get-assessment-software-inventory.md)

その他の関連

- [リスクベースの脅威&脆弱性管理](next-gen-threat-and-vuln-mgt.md)
- [組織の脆弱性](tvm-weaknesses.md)
