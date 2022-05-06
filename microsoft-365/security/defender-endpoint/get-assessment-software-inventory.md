---
title: デバイスごとのソフトウェア インベントリ評価をエクスポートする
description: DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。
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
ms.openlocfilehash: 4c3464a3aec242bd098503ac5bca997943ac2a4a
ms.sourcegitcommit: dd6514ae173f1c821d4ec25298145df6cb232e2e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/19/2022
ms.locfileid: "62074572"
---
# <a name="export-software-inventory-assessment-per-device"></a>デバイスごとのソフトウェア インベントリ評価をエクスポートする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


異なる API 呼び出しは、さまざまな種類のデータを取得します。 データの量は大きくなる可能性があるため、取得する方法は 2 つあります。

- [ソフトウェア インベントリ評価 **JSON 応答を** エクスポートする](#1-export-software-inventory-assessment-json-response)API は、組織内のすべてのデータを Json 応答としてプルします。 この方法は、 _100 K 未満のデバイスを持つ小規模な組織_ に最適です。 応答はページ分割されるため、応答の odata.nextLink フィールドを使用 \@して次の結果をフェッチできます。

- [**ファイルを使用して** ソフトウェア インベントリの評価をエクスポートする](#2-export-software-inventory-assessment-via-files) この API ソリューションを使用すると、大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織に推奨されます。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storageからすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のようにAzure Storageからすべてのデータをダウンロードできます。
  - すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。
  - ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。

( _Json 応答_ または _ファイルを使用して_) 収集されるデータは、現在の状態の現在のスナップショットです。 履歴データは含まれません。 履歴データを収集するには、お客様が独自のデータ ストレージにデータを保存する必要があります。

> [!NOTE]
> 特に明記されていない限り、一覧表示されているすべてのエクスポート評価方法は **_、完全なエクスポート_** と **_デバイス別_** ( **_デバイスごと_** とも呼ばれます) です。

## <a name="1-export-software-inventory-assessment-json-response"></a>1. ソフトウェア インベントリ評価をエクスポートする (JSON 応答)

### <a name="11-api-method-description"></a>1.1 API メソッドの説明

この API 応答には、デバイスごとにインストールされているソフトウェアのすべてのデータが含まれます。 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。

#### <a name="limitations"></a>制限事項

- 最大ページ サイズは 200,000 です。
- この API のレート制限は、1 分あたり 30 回の呼び出しと 1 時間あたり 1,000 回の呼び出しです。

### <a name="12-permissions"></a>1.2 アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API を使用する」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
---|---|---
アプリケーション|Software.Read.All|\'脅威と脆弱性の管理の脆弱性情報を読み取る\'
委任 (職場または学校のアカウント)|Software.Read|\'脅威と脆弱性の管理の脆弱性情報を読み取る\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a>1.4 パラメーター

- pageSize (既定値は 50,000): 応答する結果の数。
- $top: 返される結果の数 (@odata.nextLink が返されないため、すべてのデータがプルされるわけではありません)

### <a name="15-properties"></a>1.5 プロパティ

> [!NOTE]
>
> - 各レコードは約 0.5 KB のデータです。 正しい pageSize パラメーターを選択するときは、これを考慮する必要があります。
> - 次の表で定義されているプロパティは、プロパティ ID でアルファベット順に一覧表示されます。 この API を実行する場合、結果の出力は必ずしもこの表に示されているのと同じ順序で返されるとは限りません。
> - 応答で追加の列が返される場合があります。 これらの列は一時的なものであり、削除される可能性があります。ドキュメント化された列のみを使用してください。

<br>

****

プロパティ (ID)|データ型|説明|返された値の例
:---|:---|:---|:---
DeviceId|string|サービス内のデバイスの一意の識別子。|9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName|string|デバイスの完全修飾ドメイン名 (FQDN)。|johnlaptop.europe.contoso.com
DiskPaths|Array[string]|製品がデバイスにインストールされていることを示すディスク証拠。|[ "C:\\Program Files (x86)\\MicrosoftSilverlightApplication\\\\\\silverlight.exe" ]
EndOfSupportDate|string|このソフトウェアのサポートが終了または終了する日付。|2020-12-30
EndOfSupportStatus|string|サポートの終了状態。 次の値を含めることができます。None、EOS バージョン、今後の EOS バージョン、EOS ソフトウェア、今後の EOS ソフトウェア。|今後の EOS
ID|string|レコードの一意の識別子。|123ABG55_573AG&mnp!
NumberOfWeaknesses|int|このデバイス上のこのソフトウェアの弱点の数|3
OSPlatform|string|デバイスで実行されているオペレーティング システムのプラットフォーム。 これらは、Windows 10やWindows 11など、同じファミリ内のバリエーションを持つ特定のオペレーティング システムです。 詳細については、tvm でサポートされているオペレーティング システムとプラットフォームを参照してください。|Windows10 とWindows 11
RbacGroupName|string|ロールベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。|サーバー
RegistryPaths|Array[string]|製品がデバイスにインストールされていることを示すレジストリ証拠。|[ "HKEY_LOCAL_MACHINE\\SOFTWAREWOW6432NodeMicrosoft\\\\\\ Windows\\ CurrentVersionUninstallMicrosoft\\\\ Silverlight" ]
SoftwareFirstSeenTimestamp|string|このソフトウェアがデバイスで初めて表示された。|2019-04-07 02:06:47
SoftwareName|string|ソフトウェア製品の名前。|Silverlight
SoftwareVendor|string|ソフトウェア ベンダーの名前。|microsoft
SoftwareVersion|string|ソフトウェア製品のバージョン番号。|81.0.4044.138
|

### <a name="16-examples"></a>1.6 例

#### <a name="161-request-example"></a>1.6.1 要求の例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="162-response-example"></a>1.6.2 応答の例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10" "Windows_11",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a>2. ソフトウェア インベントリ評価をエクスポートする (ファイル経由)

### <a name="21-api-method-description"></a>2.1 API メソッドの説明

この API 応答には、デバイスごとにインストールされているソフトウェアのすべてのデータが含まれます。 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。

#### <a name="211-limitations"></a>2.1.1 制限事項

この API のレート制限は、1 分あたり 5 回の呼び出しと 1 時間あたり 20 回の呼び出しです。

### <a name="22-permissions"></a>2.2 アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API を使用する」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
---|---|---
アプリケーション|Software.Read.All|\'脅威と脆弱性の管理の脆弱性情報を読み取る\'
委任 (職場または学校のアカウント)|Software.Read|\'脅威と脆弱性の管理の脆弱性情報を読み取る\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a>パラメーター

- sasValidHours: ダウンロード URL が有効になる時間数 (最大 24 時間)

### <a name="25-properties"></a>2.5 プロパティ

> [!NOTE]
>
> - ファイルは、複数行 JSON 形式の gzip 圧縮&です。
> - ダウンロード URL は 3 時間だけ有効です。 それ以外の場合は、パラメーターを使用できます。
> - データの最大ダウンロード速度を確保するために、データが存在するのと同じ Azure リージョンからダウンロードしていることを確認できます。

<br>

****

プロパティ (ID)|データ型|説明|返された値の例
:---|:---|:---|:---
ファイルをエクスポートする|arraystring\[\]|組織の現在のスナップショットを保持しているファイルのダウンロード URL の一覧|"[Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1", "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2"]
GeneratedTime|string|エクスポートが生成された時刻。|2021-05-20T08:00:00Z
|

### <a name="26-examples"></a>2.6 例

#### <a name="261-request-example"></a>2.6.1 要求の例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a>2.6.2 応答の例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>関連項目

- [デバイスごとの評価方法とプロパティをエクスポートする](get-assessment-methods-properties.md)
- [デバイスごとのセキュリティで保護された構成評価をエクスポートする](get-assessment-secure-config.md)
- [デバイスごとのソフトウェア脆弱性評価のエクスポート](get-assessment-software-vulnerabilities.md)

その他の関連

- [リスクベースの脅威& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [組織の脆弱性](tvm-weaknesses.md)
