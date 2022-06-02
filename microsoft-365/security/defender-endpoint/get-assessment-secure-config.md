---
title: デバイスごとのセキュリティで保護された構成評価をエクスポートする
description: DeviceId、ConfigurationId のすべての一意の組み合わせのエントリを返します。
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
ms.openlocfilehash: 6d706dc8552490b7705cc23fca4751f810211d47
ms.sourcegitcommit: a7cd723fd62b4b0aae9c2c2df04ead3c28180084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2022
ms.locfileid: "65839296"
---
# <a name="export-secure-configuration-assessment-per-device"></a>デバイスごとのセキュリティで保護された構成評価をエクスポートする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender 脆弱性の管理](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

デバイスごとに、すべての構成とその状態を返します。

さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。 データの量は大きくなる可能性があるため、取得する方法は 2 つあります。

- [セキュリティで保護された構成評価 **JSON 応答** をエクスポート](#1-export-secure-configuration-assessment-json-response)する: API は、組織内のすべてのデータを Json 応答としてプルします。 この方法は、 _100 K 未満のデバイスを持つ小規模な組織_ に最適です。 応答はページ分割されるため、応答の odata.nextLink フィールドを使用 \@して次の結果をフェッチできます。

- [**ファイルを使用して** セキュリティで保護された構成評価をエクスポート](#2-export-secure-configuration-assessment-via-files)する: この API ソリューションを使用すると、大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織に推奨されます。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storageからすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のようにAzure Storageからすべてのデータをダウンロードできます。

  - すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。

  - ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。

( _JSON 応答_ またはファイルを使用 _して_) 収集されるデータは、現在の状態の現在のスナップショットであり、履歴データは含まれません。 履歴データを収集するには、お客様が独自のデータ ストレージにデータを保存する必要があります。

> [!NOTE]
> 特に明記されていない限り、一覧表示されているすべてのエクスポート評価方法は **_、完全なエクスポート_** と **_デバイス別_** ( **_デバイスごと_** とも呼ばれます) です。

## <a name="1-export-secure-configuration-assessment-json-response"></a>1. セキュリティで保護された構成評価 (JSON 応答) をエクスポートする

### <a name="11-api-method-description"></a>1.1 API メソッドの説明

この API 応答には、公開されているデバイスのセキュリティで保護された構成評価が含まれており、DeviceId、ConfigurationId のすべての一意の組み合わせのエントリが返されます。

#### <a name="111-limitations"></a>1.1.1 制限事項

- 最大ページ サイズは 200,000 です。

- この API のレート制限は、1 分あたり 30 回の呼び出しと 1 時間あたり 1,000 回の呼び出しです。

### <a name="12-permissions"></a>1.2 アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API を使用](apis-intro.md)する」を参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
---|---|---
アプリケーション|Vulnerability.Read.All|\'脅威と脆弱性の管理の脆弱性情報を読み取る\'
委任 (職場または学校のアカウント)|Vulnerability.Read|\'脅威と脆弱性の管理の脆弱性情報を読み取る\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a>1.4 パラメーター

- pageSize \(default = 50,000\): 応答の結果の数。
- \$top: 返 \(す結果の数は odata.nextLink を返 \@さないので、すべてのデータ\)をプルしません。

### <a name="15-properties"></a>1.5 プロパティ

> [!NOTE]
>
> - 次の表で定義されているプロパティは、プロパティ ID でアルファベット順に一覧表示されます。 この API を実行する場合、結果の出力は必ずしもこの表に示されているのと同じ順序で返されるとは限りません。
> - 応答で追加の列が返される場合があります。 これらの列は一時的なものであり、削除される可能性があります。ドキュメント化された列のみを使用してください。

<br>

****

プロパティ (ID)|データ型|説明|返された値の例
---|---|---|---
ConfigurationCategory|string|構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御|セキュリティ コントロール
ConfigurationId|string|特定の構成の一意の識別子|scid-10000
ConfigurationImpact|string|構成が全体の構成スコアに与える影響の評価 (1-10)|9 
ConfigurationName|string|構成の表示名|デバイスを Microsoft Defender for Endpoint にオンボードする
ConfigurationSubcategory|string|構成が属するサブカテゴリまたはサブグループ。 多くの場合、これは特定の機能または機能を説明します。|デバイスのオンボード
DeviceId|string|サービス内のデバイスの一意の識別子。|9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
DeviceName|string|デバイスの完全修飾ドメイン名 (FQDN)。|johnlaptop.europe.contoso.com
IsApplicable|bool|構成またはポリシーが適用可能かどうかを示します|true
IsCompliant|bool|構成やポリシーが正しく構成されているかどうかを示します|false
IsExpectedUserImpact|bool|構成が適用される場合にユーザーに影響を与えるかどうかを示します|true
OSPlatform|string|デバイスで実行されているオペレーティング システムのプラットフォーム。 これは、Windows 10やWindows 11など、同じファミリ内のバリエーションを含む特定のオペレーティング システムを示します。 詳細については、tvm でサポートされているオペレーティング システムとプラットフォームを参照してください。|Windows10 とWindows 11
RbacGroupName|string|ロールベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。|サーバー
RecommendationReference|string|このソフトウェアに関連する推奨事項 ID への参照。|sca-_-scid-20000
Timestamp|string|デバイスで最後に構成が表示された時刻|2020-11-03 10:13:34.8476880
|

### <a name="16-examples"></a>1.6 例

#### <a name="161-request-example"></a>1.6.1 要求の例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5
```

#### <a name="162-response-example"></a>1.6.2 応答の例

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol - Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol - Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10" "Windows11",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a>2. セキュリティで保護された構成評価をエクスポートする (ファイル経由)

### <a name="21-api-method-description"></a>2.1 API メソッドの説明

この API 応答には、公開されているデバイスのセキュリティで保護された構成評価が含まれており、DeviceId、ConfigurationId のすべての一意の組み合わせのエントリが返されます。

#### <a name="212-limitations"></a>2.1.2 制限事項

この API のレート制限は、1 分あたり 5 回の呼び出しと 1 時間あたり 20 回の呼び出しです。

### <a name="22-permissions"></a>2.2 アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API を使用する」を参照してください。](apis-intro.md)

アクセス許可の種類|アクセス許可|アクセス許可の表示名
---|---|---
アプリケーション|Vulnerability.Read.All|\'"脅威と脆弱性の管理" の脆弱性情報を読む\'
委任 (職場または学校のアカウント)|Vulnerability.Read|\'"脅威と脆弱性の管理" の脆弱性情報を読む\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a>パラメーター

- sasValidHours: ダウンロード URL が有効になる時間数 (最大 24 時間)。

### <a name="25-properties"></a>2.5 プロパティ

> [!NOTE]
>
> - ファイルは、複数行の Json 形式の gzip 圧縮&です。
> - ダウンロード URL は 3 時間だけ有効です。それ以外の場合は、パラメーターを使用できます。
> - データの最大ダウンロード速度を確保するために、データが存在するのと同じ Azure リージョンからダウンロードしていることを確認できます。

<br>

****

プロパティ (ID)|データ型|説明|返された値の例
---|---|---|---
ファイルをエクスポートする|配列\[文字列\]|組織の現在のスナップショットを保持しているファイルのダウンロード URL の一覧|["Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1", "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2"]
GeneratedTime|string|エクスポートが生成された時刻。|2021-05-20T08:00:00Z
|

### <a name="26-examples"></a>2.6 例

#### <a name="261-request-example"></a>2.6.1 要求の例

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a>2.6.2 応答の例

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>関連項目

- [デバイスごとの評価方法とプロパティをエクスポートする](get-assessment-methods-properties.md)
- [デバイスごとのソフトウェア インベントリ評価をエクスポートする](get-assessment-software-inventory.md)
- [デバイスごとのソフトウェア脆弱性評価のエクスポート](get-assessment-software-vulnerabilities.md)

その他の関連

- [リスクベースの脅威& 脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [組織の脆弱性](tvm-weaknesses.md)
