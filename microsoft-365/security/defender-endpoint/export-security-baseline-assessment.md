---
title: デバイスごとのセキュリティ ベースライン評価方法とプロパティ
description: "\"脅威と脆弱性の管理\" データをプルするセキュリティ ベースライン API に関する情報を提供します。 さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。 一般に、各 API 呼び出しには、組織内のデバイスに必要なデータが含まれています。"
keywords: api, apis, export assessment, per device assessment, per machine assessment, vulnerability assessment report, device Vulnerability Assessment, device vulnerability report, secure configuration Assessment, secure configuration report, secure configuration report, software Vulnerabilities assessment, software Vulnerability report, software vulnerability report, vulnerability report by machine,
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
ms.openlocfilehash: 5fd673f37dd35a83a714c0f3dd1c6ac3b0a049ca
ms.sourcegitcommit: a7cd723fd62b4b0aae9c2c2df04ead3c28180084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2022
ms.locfileid: "66994212"
---
# <a name="export-security-baselines-assessment-per-device"></a>デバイスごとのセキュリティ ベースライン評価をエクスポートする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender 脆弱性の管理](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender 脆弱性の管理を体験しますか? [無料試用版にサインアップしてください。- 更新](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。 一般に、各 API 呼び出しには、組織内のデバイスに必要なデータが含まれています。

- **JSON 応答**  API は、組織内のすべてのデータを JSON 応答としてプルします。 この方法は、 _100 K 未満のデバイスを持つ小規模な組織_ に最適です。 応答はページ分割されるため、応答の odata.nextLink フィールドを使用 \@して次の結果をフェッチできます。

- **ファイル経由** この API ソリューションを使用すると、大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織に推奨されます。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storage からすべてのデータをダウンロードするための URL が含まれています。 Azure Storage から次のようにデータをダウンロードできます。
  - すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。
  - ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。

"_JSON 応答_ または _ファイル経由_" を使用して収集されるデータは、現在の状態の現在のスナップショットです。 履歴データは含まれません。 履歴データを収集するには、お客様が独自のデータ ストレージにデータを保存する必要があります。

> [!NOTE]
> 特に明記されていない限り、一覧表示されているすべてのエクスポート セキュリティ ベースライン評価方法は **_、完全なエクスポート_** と **_デバイス別_** ( **_デバイスごと_** とも呼ばれます) です。

## <a name="1-export-security-baselines-assessment-json-response"></a>1. セキュリティ ベースライン評価をエクスポートする (JSON 応答)

### <a name="11-api-method-description"></a>1.1 API メソッドの説明

デバイスごとに、すべてのデバイスのすべてのセキュリティ ベースライン評価を返します。 DeviceId、ProfileId、ConfigurationId の一意の組み合わせごとに個別のエントリを持つテーブルを返します。

### <a name="12-permissions"></a>1.2 アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API を使用](apis-intro.md)する」を参照してください。

アクセス許可の種類|アクセス許可|アクセス許可の表示名
:---|:---|:---
アプリケーション|SecurityBaselinesAssessment.Read.All |'すべてのセキュリティ ベースライン評価情報を読み取る'
委任 (職場または学校のアカウント)|SecurityBaselinesAssessment.Read|'セキュリティ ベースライン評価情報の読み取り'

### <a name="13-limitations"></a>1.3 制限事項

- 最大ページ サイズは 200,000 です。
- この API のレート制限は、1 分あたり 30 回の呼び出しと 1 時間あたり 1,000 回の呼び出しです。

### <a name="14-parameters"></a>1.4 パラメーター

- pageSize (既定値は 50,000): 応答する結果の数。
- $top: 返される結果の数 (@odata.nextLink が返されないため、すべてのデータがプルされるわけではありません)。

### <a name="15-http-request"></a>1.5 HTTP 要求

```http
GET /api/machines/baselineComplianceAssessmentByMachine
```

### <a name="16-properties-json-response"></a>1.6 プロパティ (JSON 応答)

> [!NOTE]
> 各レコードは約 1 KB のデータです。 正しい pageSize パラメーターを選択するときは、これを考慮する必要があります。
>
> 応答で追加の列が返される場合があります。 これらの列は一時的なものであり、削除される可能性があります。 ドキュメント化された列のみを使用します。
>
> 次の表で定義されているプロパティは、プロパティ ID でアルファベット順に一覧表示されます。 この API を実行する場合、結果の出力は必ずしもこの表に示されているのと同じ順序で返されるとは限りません。

プロパティ (ID)|データ型|説明
:---|:---|:---
|configurationId|String|ベースライン ベンチマーク内の特定の構成の一意の識別子。
|profileId|String|評価されたプロファイルの一意の識別子。
|deviceId|String|サービス内のデバイスの一意の識別子。
|deviceName|String|デバイスの完全修飾ドメイン名 (FQDN)。
|isApplicable|ブール型|構成がこのデバイスに適用できるかどうかを示します。
|isCompliant|ブール値|デバイスが構成に準拠しているかどうかを示します。
|id|String|DeviceId、ProfileId、ConfigurationId の組み合わせであるレコードの一意の識別子。
|osVersion|String|デバイスで実行されているオペレーティング システムの特定のバージョン。
|osPlatform|String|デバイスで実行されているオペレーティング システム プラットフォーム。 Windows 10やWindows 11など、同じファミリ内にバリエーションがある特定のオペレーティング システム。 詳細については、 [TVM でサポートされているオペレーティング システムとプラットフォーム](tvm-supported-os.md) を参照してください。
|rbacGroupId|Int|ロールベースのアクセス制御 (RBAC) グループ ID。デバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。
|rbacGroupName|String|ロールベースのアクセス制御 (RBAC) グループ。 デバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。
|DataCollectionTimeOffset|DateTime|デバイスからデータが収集された時刻。 データが収集されなかった場合、このフィールドは表示されない場合があります。
|ComplianceCalculationTimeOffset|DateTime|評価の計算が行われた時刻。
|RecommendedValue|String|現在のデバイス設定に予期されるクレーム値のセット。
|CurrentValue|String|デバイスで検出された一連の検出された値。
|ソース|String|現在のデバイス設定を決定するために使用されるレジストリ パスまたはその他の場所。

## <a name="17-example"></a>1.7 例

### <a name="171-request-example"></a>1.7.1 要求の例

```http
GET https://api.securitycenter.microsoft.com/api/machines/BaselineComplianceAssessmentByMachine
```

### <a name="172-response-example"></a>1.7.2 応答の例

```json
{
"@odata.context": " https://api.securitycenter.microsoft.com /api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetBaselineAssessment)",
"value": [
{
    "id": "0000682575d5d473e82ed4d8680425d152411251_9e1b90be-e83e-485b-a5ec-4a429412e734_1.1.1",
    "configurationId": "1.1.1",
    "deviceId": "0000682575d5d473242222425d152411251",
    "deviceName": " ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596 ",
    "profileId": "9e1b90be-e83e-485b-a5ec-4a429412e734",
    "osPlatform": "WindowsServer2019",
    "osVersion": "10.0.17763.2330",
    "rbacGroupId": 86,
    "rbacGroupName": "UnassignedGroup",
    "isApplicable": true,
    "isCompliant": false,
    "dataCollectionTimeOffset": "2021-12-22T00:08:02.478Z",
    "recommendedValue": [
                    "Greater than or equal '24'"
                ],
                "currentValue": [
                    "24"
                ],
                "source": [
                    "password_hist_len"
                ],
}
```

## <a name="2-export-security-baselines-assessment-via-files"></a>2. セキュリティ ベースライン評価をエクスポートする (ファイル経由)

### <a name="21-api-method-description"></a>2.1 API メソッドの説明

デバイスごとに、すべてのデバイスのすべてのセキュリティ ベースライン評価を返します。 DeviceId、ProfileId、ConfigurationId の一意の組み合わせごとに個別のエントリを持つテーブルを返します。

### <a name="22-limitations"></a>2.2 制限事項

- この API のレート制限は、1 分あたり 5 回の呼び出しと 1 時間あたり 20 回の呼び出しです。

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/BaselineComplianceAssessmentExport
```

### <a name="24-parameters"></a>2.4 パラメーター

- sasValidHours: ダウンロード URL が有効になる時間数 (最大 24 時間)。

### <a name="25-properties-via-files"></a>2.5 プロパティ (ファイル経由)

> [!NOTE]
> ファイルは、複数行の Json 形式の gzip 圧縮&です。
>
>ダウンロード URL は 3 時間だけ有効です。それ以外の場合は、パラメーターを使用できます。
>
>ダウンロード速度を最大化するには、データが存在するのと同じ Azure リージョンからデータをダウンロードしていることを確認します。
>
>各レコードは約 1 KB のデータです。 この点を考慮に入れる必要があります。これは、自分に適した pageSize パラメーターを選択する場合に考慮する必要があります。
>
>応答で追加の列が返される場合があります。 これらの列は一時的なものであり、削除される可能性があります。 ドキュメント化された列のみを使用します。

プロパティ (ID)|データ型|説明
:---|:---|:---
|ファイルをエクスポートする|array[string]|組織の現在のスナップショットを保持しているファイルのダウンロード URL の一覧。
|GeneratedTime|String|エクスポートが生成された時刻。

## <a name="26-example"></a>2.6 例

### <a name="261-request-example"></a>2.6.1 要求の例

```http
GET https://api.securitycenter.microsoft.com/api/machines/BaselineComplianceAssessmentExport
```

### <a name="262-response-example"></a>2.6.2 応答の例

```json
{
    "@odata.context": "https://api.securitycenter. contoso.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": 
    [
    "https://tvmexportexternalstgeus.blob.core.windows.net/temp-1ebd3d09-d06a-4aad-ab80-ebc536cec61c/2021-12-22/0500/BaselineAssessmentExport/json/OrgId= OrgId=<Org Id>/_RbacGroupId=<Rbac Group Id>/part-00000-c09dfd00-2278-4735-b23a-71733751fcbc.c000.json.gz?sv=ABCD",
   "https://tvmexportexternalstgeus.blob.core.windows.net/temp-1ebd3d09-d06a-4aad-ab80-ebc536cec61c/2021-12-22/0500/BaselineAssessmentExport/json/OrgId=<Org Id>/_RbacGroupId=<Rbac Group Id>/part-00001-c09dfd00-2278-4735-b23a-71733751fcbc.c000.json.gz?sv= ABCD",
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>関連項目

- [セキュリティ ベースライン評価プロファイルを取得する](get-security-baselines-assessment-profiles.md)
- [セキュリティ ベースライン評価構成を取得する](get-security-baselines-assessment-configurations.md)
