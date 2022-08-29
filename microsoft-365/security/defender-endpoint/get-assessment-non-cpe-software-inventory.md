---
title: デバイスごとの製品コード以外のソフトウェア インベントリ評価をエクスポートする
description: 共通プラットフォーム列挙 (CPE) を持たないソフトウェアの DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。
keywords: api, apis, export assessment, per device assessment, Vulnerability Assessment report, device Vulnerability assessment, device vulnerability report, secure configuration assessment, secure configuration report, software vulnerabilities assessment, software Vulnerability report, software vulnerability report, vulnerability report by machine,
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 223ca8ab9eac14b456c62dad3d644ad067092766
ms.sourcegitcommit: 48a75b40e607542e5fe219b6e75ffc757804a9c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2022
ms.locfileid: "67344549"
---
# <a name="export-non-product-code-software-inventory-assessment-per-device"></a>デバイスごとの製品コード以外のソフトウェア インベントリ評価をエクスポートする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender 脆弱性の管理](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

この API は、共通 [プラットフォーム列挙 (CPE)](https://nvd.nist.gov/products/cpe) を持たないインストール済みソフトウェアのすべてのデータをデバイスごとに返します。 この API によって返される情報は、CPE を持つ [ソフトウェアのエクスポート ソフトウェア インベントリ評価](get-assessment-non-cpe-software-inventory.md) API によって返される情報と共に、組織全体にインストールされているソフトウェアと、インストールされているデバイスを完全に把握できます。

> [!NOTE]
> CPE のないソフトウェア製品は、脆弱性管理ではサポートされていません。 これらはソフトウェア インベントリ ページに表示されますが、CPE は脆弱性管理によってソフトウェアを識別するために使用されるため、脆弱性、悪用、公開されたデバイスの数、弱点などの情報は利用できません。 詳細については、「 [ソフトウェア インベントリ](../defender-vulnerability-management/tvm-software-inventory.md)」を参照してください。

異なる API 呼び出しは、さまざまな種類のデータを取得します。 データの量は大きくなる可能性があるため、取得する方法は 2 つあります。

- [製品コード以外のソフトウェア インベントリ評価 **JSON 応答** をエクスポートする](#1-export-non-product-code-software-inventory-assessment-json-response)API は、組織内のすべてのデータを Json 応答としてプルします。 この方法は、 _100 K 未満のデバイスを持つ小規模な組織_ に最適です。 応答はページ分割されるため、応答の \@odata.nextLink フィールドを使用して次の結果をフェッチできます。

- [**ファイルを使用して** 製品コード以外のソフトウェア インベントリ評価をエクスポート](#2-export-non-product-code-software-inventory-assessment-via-files)する この API ソリューションを使用すると、大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織におすすめです。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storage からすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のように Azure Storage からすべてのデータをダウンロードできます:
  - すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。
  - ダウンロード URL を使用してすべてのファイルをダウンロードし、データを好きなように処理します。

( _Json 応答_ または _ファイルを使用して_) 収集されるデータは、現在の状態の現在のスナップショットです。 履歴データは含まれません。 履歴データを収集するには、お客様が独自のデータ ストレージにデータを保存する必要があります。

> [!NOTE]
> 特に明記されていない限り、一覧表示されているすべてのエクスポート評価方法は **_、完全なエクスポート_** と **_デバイス別_** ( **_デバイスごと_** とも呼ばれます) です。

## <a name="1-export-non-product-code-software-inventory-assessment-json-response"></a>1. 製品コード以外のソフトウェア インベントリ評価 (JSON 応答) をエクスポートする

### <a name="11-api-method-description"></a>1.1 API メソッドの説明

この API 応答には、デバイスごとに [共通プラットフォーム列挙 (CPE)](https://nvd.nist.gov/products/cpe) を持たないインストール済みソフトウェアのすべてのデータが含まれます。 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。

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
GET /api/machines/SoftwareInventoryNoProductCodeByMachine
```

### <a name="14-parameters"></a>1.4 パラメーター

- pageSize (既定値は 50,000): 応答する結果の数。
- $top: 返される結果の数 (@odata.nextLink が返されないため、すべてのデータがプルされるわけではありません)

### <a name="15-properties"></a>1.5 プロパティ

> [!NOTE]
>
> - 各レコードは約 0.5 KB のデータです。 正しい pageSize パラメーターを選択するときは、これを考慮する必要があります。
> - 次のテーブルで定義されているプロパティは、プロパティ ID でアルファベット順にリスト表示されます。 この API を実行する場合、結果の出力は必ずしもこのテーブルにリストされているのと同じ順序で返されるとは限りません。
> - 応答で追加の列が返される場合があります。 これらの列は一時的なものであり、削除される可能性があります。ドキュメント化された列のみを使用してください。

<br>

プロパティ (ID)|データ型|説明
:---|:---|:---
DeviceId|文字列|サービス内のデバイスの一意の識別子。
DeviceName|string|デバイスの完全修飾ドメイン名 (FQDN)。
OSPlatform|string|デバイスで実行されているオペレーティング システムのプラットフォーム。 これらは、Windows 10やWindows 11など、同じファミリ内のバリエーションを持つ特定のオペレーティング システムです。 詳細については [、「サポートされているオペレーティング システム、プラットフォーム、および機能](../defender-vulnerability-management/tvm-supported-os.md) 」を参照してください。
RbacGroupName|string|ロールベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。
RbacGroupId|string|ロールベースのアクセス制御 (RBAC) グループ ID。
SoftwareLastSeenTimestamp|文字列|このソフトウェアがデバイスで最後に表示された時刻。
SoftwareName|文字列|ソフトウェア製品の名前。
SoftwareVendor|string|ソフトウェア ベンダーの名前。
SoftwareVersion|string|ソフトウェア製品のバージョン番号。

### <a name="16-examples"></a>1.6 例

#### <a name="161-request-example"></a>1.6.1 要求の例

```http
https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryNoProductCodeByMachine?pageSize=3  &sinceTime=2021-05-19
```

#### <a name="162-response-example"></a>1.6.2 応答の例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetNonCpeSoftware)",
    "value": [
        {
           "deviceId": "1234512345123451234512345",
            "rbacGroupId": 11,
            "rbacGroupName": "London",
            "deviceName": "Device1",
            "osPlatform": "Windows11",
            "softwareVendor": "microsoft",
            "softwareName": "vs_communitymsi",
            "softwareVersion": "11.11.31111.1",
            "softwareLastSeenTimestamp": "2021-01-30 11:31:12.271"
        },
        {
            "deviceId": "232323232323232322323232323",
            "rbacGroupId": 23,
            "rbacGroupName": "Tokyo",
            "deviceName": "Device23",
            "osPlatform": "Windows10",
            "softwareVendor": "intel",
            "softwareName": "intel®_software_installer",
            "softwareVersion": "22.20.2.2",
            "softwareLastSeenTimestamp": "2022-05-30 15:35:12.271"
        },
        {
            "deviceId": "6565656565",
            "rbacGroupId": 65,
            "rbacGroupName": "Center",
            "deviceName": "Device56",
            "osPlatform": "Windows10",
            "softwareVendor": "Lob Apps",
            "softwareName": "Headtrax",
            "softwareVersion": "60.273.3",
            "softwareLastSeenTimestamp": "2022-05-05 15:35:12.271"
        },
    ],
        "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryNoProductCodeByMachine?pagesize=3%20%20&sincetime=2021-05-19&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMi0wNS0zMC8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}

```

## <a name="2-export-non-product-code-software-inventory-assessment-via-files"></a>2. 製品コード以外のソフトウェア インベントリ評価 (ファイル経由) をエクスポートする

### <a name="21-api-method-description"></a>2.1 API メソッドの説明

この API 応答には、デバイスごとに [共通プラットフォーム列挙 (CPE)](https://nvd.nist.gov/products/cpe) を持たないインストール済みソフトウェアのすべてのデータが含まれます。 DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。

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
GET /api/machines/Api/Machines/SoftwareInventoryNonCpeExport
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

プロパティ (ID)|データ型|説明|戻り値の例
:---|:---|:---|:---
ファイルをエクスポートする|配列\[文字列\]|組織の現在のスナップショットを保持しているファイルのダウンロード URL の一覧|"[Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1", "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2"]
GeneratedTime|文字列|エクスポートが生成された時刻。|2021-05-20T08:00:00Z
|

### <a name="26-examples"></a>2.6 例

#### <a name="261-request-example"></a>2.6.1 要求の例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryNonCpeExport
```

#### <a name="262-response-example"></a>2.6.2 応答の例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportexternalprdcanc.blob.core.windows.net/temp-ffd80447-7b3d-4ad2-b366-f0979b129662/2022-05-30/1101/NonCpeSoftwareInventory/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=1/part-00337-5e15412b-5c85-4896-ac60-b7b3ab8da096.c000.json.gz?sv=2020-08-04&st=2022-05-30T13%3A41%3A59Z&se=2022-05-30T16%3A41%3A59Z&sr=b&sp=r&sig=aHnmuOKlIvpR0PsdamYfmCCDZ1nhpuXBzK2%2FkJ9xTpg%3D",
        "https://tvmexportexternalprdcanc.blob.core.windows.net/temp-ffd80447-7b3d-4ad2-b366-f0979b129662/2022-05-30/1101/NonCpeSoftwareInventory/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=1/part-00338-5e15412b-5c85-4896-ac60-b7b3ab8da096.c000.json.gz?sv=2020-08-04&st=2022-05-30T13%3A41%3A59Z&se=2022-05-30T16%3A41%3A59Z&sr=b&sp=r&sig=0fQg%2Ft469x26KvPLmvctLl0g6DC38CNM3lXYi9dnFfo%3D",
        "https://tvmexportexternalprdcanc.blob.core.windows.net/temp-ffd80447-7b3d-4ad2-b366-f0979b129662/2022-05-30/1101/NonCpeSoftwareInventory/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=1/part-00339-5e15412b-5c85-4896-ac60-b7b3ab8da096.c000.json.gz?sv=2020-08-04&st=2022-05-30T13%3A41%3A59Z&se=2022-05-30T16%3A41%3A59Z&sr=b&sp=r&sig=P6HGHoLXXipMauBpLueoQVrwHL7qmvLoCjcij6ERx8o%3D",
        "https://tvmexportexternalprdcanc.blob.core.windows.net/temp-ffd80447-7b3d-4ad2-b366-f0979b129662/2022-05-30/1101/NonCpeSoftwareInventory/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=1/part-00340-5e15412b-5c85-4896-ac60-b7b3ab8da096.c000.json.gz?sv=2020-08-04&st=2022-05-30T13%3A41%3A59Z&se=2022-05-30T16%3A41%3A59Z&sr=b&sp=r&sig=VnpVct%2F8vdiIFTf2xXP9DF7ngWv1Zqew30q2jBPVghg%3D",
        "https://tvmexportexternalprdcanc.blob.core.windows.net/temp-ffd80447-7b3d-4ad2-b366-f0979b129662/2022-05-30/1101/NonCpeSoftwareInventory/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=1/part-00341-5e15412b-5c85-4896-ac60-b7b3ab8da096.c000.json.gz?sv=2020-08-04&st=2022-05-30T13%3A41%3A59Z&se=2022-05-30T16%3A41%3A59Z&sr=b&sp=r&sig=GY0zxMfEmr9v9fZBWYyKEtT2k%2F0ELQIlOP0ct%2B6SdGU%3D",
    ],
    "generatedTime": "2022-05-30T11:01:00Z"
}
```

## <a name="see-also"></a>関連項目

- [デバイスごとのソフトウェア評価をエクスポートする](get-assessment-software-inventory.md)
- [デバイスごとの評価方法とプロパティをエクスポートする](get-assessment-methods-properties.md)
- [デバイスごとのセキュリティで保護された構成評価をエクスポートする](get-assessment-secure-config.md)
- [デバイスごとのソフトウェア脆弱性評価のエクスポート](get-assessment-software-vulnerabilities.md)

その他の関連
- [Microsoft Defender 脆弱性の管理](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [組織の脆弱性](tvm-weaknesses.md)
