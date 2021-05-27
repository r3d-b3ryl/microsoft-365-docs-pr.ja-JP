---
title: デバイスごとのソフトウェアの脆弱性評価のエクスポート
description: API 応答はデバイスごとに実行され、公開されているデバイスにインストールされている脆弱なソフトウェアと、これらのソフトウェア製品の既知の脆弱性が含まれる。 このテーブルには、オペレーティング システム情報、CVE ID、および脆弱性の重要度の情報も含まれます。
keywords: api、apis、エクスポート評価、デバイスごとの評価、脆弱性評価レポート、デバイスの脆弱性評価、デバイスの脆弱性レポート、セキュリティで保護された構成評価、セキュリティで保護された構成レポート、ソフトウェアの脆弱性評価、ソフトウェアの脆弱性レポート、コンピューターによる脆弱性レポート、
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
ms.openlocfilehash: 951f78ba361a12e404a5cce2071f931eab30c43f
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689215"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a>デバイスごとのソフトウェアの脆弱性評価のエクスポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]
>
>
すべての既知のソフトウェアの脆弱性と、すべてのデバイスの詳細をデバイスごとに返します。

さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。 データの量が非常に多い場合は、次の 2 つの方法で取得できます。

- [ソフトウェアの脆弱性評価 OData のエクスポート](#1-export-software-vulnerabilities-assessment-odata)  API は、OData プロトコルに従って、組織内のすべてのデータを Json 応答として取得します。 この方法は _、100 K 未満_ のデバイスを持つ小規模な組織に最適です。 応答がページ分割されたので、応答から \@ odata.nextLink フィールドを使用して次の結果を取得できます。

- [ファイルを使用してソフトウェアの脆弱性評価をエクスポートする](#2-export-software-vulnerabilities-assessment-via-files) この API ソリューションを使用すると、大量のデータを高速かつ確実に取得できます。 そのため、100 K を超えるデバイスを使用する大規模な組織に推奨されます。 この API は、組織内のすべてのデータをダウンロード ファイルとして取得します。 応答には、すべてのデータをダウンロードする URL が含Azure Storage。 この API を使用すると、すべてのデータを次のようにAzure Storageダウンロードできます。

  - API を呼び出して、すべての組織データを含むダウンロード URL の一覧を取得します。

  - ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。

収集されるデータ _(OData_ またはファイル _経由)_ は、現在の状態の現在のスナップショットであり、古いデータは含まれておりません。 過去のデータを収集するには、ユーザーがデータを独自のデータ ストレージに保存する必要があります。

> [!Note]
>
> 特に示されていない限り、一覧表示されているエクスポート評価方法はすべて、**** 完全なエクスポートと **_デバイス別_**(デバイス単位とも **_呼_** ばれます) です。

## <a name="1-export-software-vulnerabilities-assessment-odata"></a>1. ソフトウェア脆弱性評価のエクスポート (OData)

### <a name="11-api-method-description"></a>1.1 API メソッドの説明

この API 応答には、デバイスごとにインストールされているソフトウェアのすべてのデータが含まれる。 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID のすべての一意の組み合わせのエントリを含むテーブルを返します。

#### <a name="limitations"></a>制限事項

>- 最大ページ サイズは 200,000 です。
>
>- この API のレート制限は、1 分あたり 30 回の呼び出しと 1 時間あたり 1000 回の呼び出しです。

### <a name="12-permissions"></a>1.2 アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
---|---|---
アプリケーション | Vulnerability.Read.All | \'脅威と脆弱性管理の脆弱性情報の読み取り\'
委任 (職場または学校のアカウント) | 脆弱性。読み取り | \'脅威と脆弱性管理の脆弱性情報の読み取り\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a>1.4 パラメーター

- pageSize (既定値 = 50,000) – 応答の結果の数
- $top – 返す結果の数 (@odata.nextLink を返すので、すべてのデータを取得しない)

### <a name="15-properties"></a>1.5 プロパティ
>
>[!Note]
>
>- 各レコードは約 1KB のデータです。 正しい pageSize パラメーターを選択する場合は、これを考慮する必要があります。
>
>- 応答で追加の列が返される場合があります。 これらの列は一時的なもので、削除される場合があります。文書化された列のみを使用してください。
>
>- 次の表で定義されているプロパティは、プロパティ ID によってアルファベット順に一覧表示されます。  この API を実行する場合、結果の出力は必ずしもこの表に示されているのと同じ順序で返されるとは限りません。
>

プロパティ (ID) | データ型 | 説明 | 返される値の例
:---|:---|:---|:---
CveId | string | 共通の脆弱性と露出 (CVE) システムのセキュリティの脆弱性に割り当てられた一意の識別子。 | CVE-2020-15992
CvssScore | string | CVE の CVSS スコア。 | 6.2
DeviceId | string | サービス内のデバイスの一意の識別子。 | 9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName | string | デバイスの完全修飾ドメイン名 (FQDN)。 | johnlaptop.europe.contoso.com
DiskPaths  | 配列 \[ 文字列\] | 製品がデバイスにインストールされていることを示すディスク証拠。 | [ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]
ExploitabilityLevel | string | この脆弱性の悪用レベル (NoExploit、ExploitIsPublic、ExploitIsVerified、ExploitIsInKit) | ExploitIsInKit
FirstSeenTimestamp | string | この製品の CVE がデバイスで初めて表示された場合。 | 2020-11-03 10:13:34.8476880
ID | string | レコードの一意の識別子。 | 123ABG55_573AG&mnp!
LastSeenTimestamp | string | デバイスで CVE が最後に表示された時刻。 | 2020-11-03 10:13:34.8476880
OSPlatform | string | デバイスで実行されているオペレーティング システムのプラットフォーム。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。 詳細については、「tvm でサポートされるオペレーティング システムとプラットフォーム」を参照してください。 | Windows10
RbacGroupName  | string | 役割ベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "割り当てられていない" になります。 組織に RBAC グループが含まれている場合、値は "None" になります。 | Servers
RecommendationReference | string | このソフトウェアに関連する推奨事項 ID への参照。 | va-_-microsoft-_-silverlight
RecommendedSecurityUpdate (オプション) | string | ソフトウェア ベンダーが脆弱性に対処するために提供するセキュリティ更新プログラムの名前または説明。 | 2020 年 4 月のセキュリティ更新プログラム
RecommendedSecurityUpdateId (オプション) | string | 対応するガイダンスまたはナレッジ ベース (KB) 記事の該当するセキュリティ更新プログラムまたは識別子の識別子 | 4550961
RegistryPaths  | 配列 \[ 文字列\] | 製品がデバイスにインストールされていることを示すレジストリ証拠。 | [ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight"
SoftwareName | string | ソフトウェア製品の名前。 | クロム
SoftwareVendor | string | ソフトウェア ベンダーの名前。 | google
SoftwareVersion | string | ソフトウェア製品のバージョン番号。 | 81.0.4044.138
VulnerabilitySeverityLevel  | string | CVSS スコアに基づくセキュリティ脆弱性に割り当てられた重大度レベルと、脅威の状況の影響を受ける動的要因。 | 中

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
            "osPlatform": "Windows10",
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
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
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
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
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
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
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
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
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
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a>2. ソフトウェアの脆弱性評価をエクスポートする (ファイル経由)

### <a name="21-api-method-description"></a>2.1 API メソッドの説明

この API 応答には、デバイスごとにインストールされているソフトウェアのすべてのデータが含まれる。 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion、CVEID のすべての一意の組み合わせのエントリを含むテーブルを返します。

#### <a name="212-limitations"></a>2.1.2 制限事項

この API のレート制限は、1 分あたり 5 回の呼び出しと 1 時間あたり 20 回の呼び出しです。

### <a name="22-permissions"></a>2.2 アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください](apis-intro.md)。

アクセス許可の種類 | アクセス許可 | アクセス許可の表示名
---|---|---
アプリケーション | Vulnerability.Read.All | \'脅威と脆弱性管理の脆弱性情報の読み取り\'
委任 (職場または学校のアカウント) | 脆弱性。読み取り | \'脅威と脆弱性管理の脆弱性情報の読み取り\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a>2.4 パラメーター

- sasValidHours – ダウンロード URL が有効になる時間数 (最大 24 時間)

### <a name="25-properties"></a>2.5 プロパティ

>[!Note]
>
>- ファイルは、複数行 Json 形式& gzip 圧縮ファイルです。
>
>- ダウンロード URL は 3 時間のみ有効です。それ以外の場合は、パラメーターを使用できます。
>
>- データの最大ダウンロード速度を得る場合は、データが存在するのと同じ Azure 地域からダウンロードしてください。
>

>[!Note]
>
>- 各レコードは約 1KB のデータです。 正しい pageSize パラメーターを選択する場合は、これを考慮する必要があります。
>
>- 応答で追加の列が返される場合があります。 これらの列は一時的なもので、削除される場合があります。文書化された列のみを使用してください。
>

プロパティ (ID) | データ型 | 説明 | 返される値の例
:---|:---|:---|:---
ファイルのエクスポート | 配列 \[ 文字列\]  | 組織の現在のスナップショットを保持するファイルのダウンロード URL の一覧。 | [  “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2”  ]
GeneratedTime | string | エクスポートが生成された時刻。 | 2021-05-20T08:00:00Z

### <a name="26-examples"></a>2.6 例

#### <a name="261-request-example"></a>2.6.1 要求の例

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a>2.6.2 応答例

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

## <a name="see-also"></a>関連項目

- [デバイスごとの評価方法とプロパティのエクスポート](get-assessmnt-1methods-properties.md)

- [デバイスごとのセキュリティで保護された構成評価をエクスポートする](get-assessmnt-secure-cfg.md)

- [デバイスごとのソフトウェア インベントリ評価のエクスポート](get-assessmnt-software-inventory.md)

その他の関連

- [リスクベースの脅威& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)

- [組織の脆弱性](tvm-weaknesses.md)
