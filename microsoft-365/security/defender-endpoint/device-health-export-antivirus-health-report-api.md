---
title: Microsoft Defender ウイルス対策デバイス正常性エクスポート デバイスのウイルス対策正常性レポート
description: Microsoft Defender ウイルス対策デバイスの正常性の詳細を取得するメソッドを示します。
keywords: API, グラフ API, サポートされている API, GET, デバイス正常性 API, Microsoft Defender for Endpoint レポート API Microsoft Defender レポート API, Microsoft Defender for Endpoint レポート API, Windows Defender レポート API, Defender for Endpoint レポート API, Windows Defender レポート API
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: d47b4d4920fe49a1270a6eecc7c4ef8a661bdc0d
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67386929"
---
# <a name="export-device-antivirus-health-report"></a>デバイス ウイルス対策の正常性レポートをエクスポートする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

この API には、Microsoft Defender ウイルス対策デバイスのウイルス対策の正常性の詳細を取得する 2 つの方法があります。

- **方法 1:** [1 正常性レポート **JSON 応答**\)をエクスポートする \(](#1-export-health-reporting-json-response) メソッドは、組織内のすべてのデータを JSON 応答としてプルします。 この方法は、 _100 K 未満のデバイスを持つ小規模な組織_ に最適です。 応答はページ分割されるため、応答の \@odata.nextLink フィールドを使用して次の結果をフェッチできます。

- **方法 2:** [2 ファイル\)**を使用して** 正常性レポートを\(エクスポート](#2-export-health-reporting-via-files)する この方法では、より多くのデータを迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織におすすめです。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storage からすべてのデータをダウンロードするための URL が含まれています。 この API を使用すると、次のように Azure Storage からすべてのデータをダウンロードできます:
  - すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。
  - ダウンロード URL を使用してすべてのファイルをダウンロードし、データを好きなように処理します。

"_JSON 応答_ または _ファイル経由_" を使用して収集されるデータは、現在の状態の現在のスナップショットです。 履歴データは含まれません。 履歴データを収集するには、お客様が独自のデータ ストレージにデータを保存する必要があります。 [デバイス正常性の詳細 API のメソッドとプロパティのエクスポートに](device-health-api-methods-properties.md)関する説明を参照してください。

> [!IMPORTANT]
>
> Windows &nbsp;Server&nbsp; 2012 &nbsp;R2 と Windows &nbsp;Server&nbsp; 2016 がデバイス正常性レポートに表示されるようにするには、これらのデバイスを最新の統合ソリューション パッケージを使用してオンボードする必要があります。 詳細については、「[Windows Server 2012 R2 と 2016 の最新の統合ソリューションの新機能](/microsoft-365/security/defender-endpoint/configure-server-endpoints#new-windows-server-2012-r2-and-2016-functionality-in-the-modern-unified-solution)」を参照してください。

> [!NOTE]
>
> Microsoft 365 セキュリティ ダッシュボードで **デバイスの正常性とウイルス対策のコンプライアンス** レポート ツールを使用する方法については、「[Microsoft Defender for Endpoint のデバイスの正常性とウイルス対策のコンプライアンス レポート](machine-reports.md)」を参照してください。
>

## <a name="1-export-health-reporting-json-response"></a>1 正常性レポートのエクスポート (JSON 応答)

### <a name="11-api-method-description"></a>1.1 API メソッドの説明

この API は、Microsoft Defender ウイルス対策デバイスのウイルス対策の正常性の詳細の一覧を取得します。 次の一意の組み合わせごとにエントリを含むテーブルを返します。

- DeviceId
- デバイス名
- AV モード
- 最新の状態
- 結果をスキャンする

#### <a name="111-limitations"></a>1.1.1 制限事項

- 最大ページ サイズは 200,000 です
- この API のレート制限 (**_例:_** 1 分あたり 30 回、hour._あたり 1,000 回の呼び出し)

#### <a name="odata-supported-operators"></a>OData でサポートされている演算子

- ```$filter``` on: ```machineId```, , ```computerDnsName```, ```osKind```, ```osPlatform```, ```avMode``````osVersion```, ```avSignatureVersion```, ```avEngineVersion``````avPlatformVersion```, ```quickScanResult```, ```quickScanError```, ```fullScanResult```, ```fullScanError```, ```avIsSignatureUpToDate```, ```avIsEngineUpToDate```, , ```avIsPlatformUpToDate``````rbacGroupId```
- ```$top``` 最大値が 10,000 です。
- ```$skip```.

### <a name="12-permissions"></a>1.2 アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。 アクセス許可の選択方法など、詳細については、「Microsoft Defender for Endpoint API を使用する」を参照してください。

| アクセス許可の種類 | アクセス許可 | アクセス許可の表示名 |
|:---|:---|:---|
| アプリケーション | Machine.Read.All | 'すべてのマシン プロファイルを読み取る' |
|委任 (職場または学校のアカウント) | Machine.Read | 'マシン情報の読み取り' |

### <a name="13-url-http-request"></a>1.3 URL (HTTP 要求)

```http
URL: GET: /api/deviceavinfo
```

#### <a name="131-request-headers"></a>1.3.1 要求ヘッダー

| 名前 | 種類 | 説明 |
|:---|:---|:---|
| Authorization | String | ベアラー {token}。必須です。 |

#### <a name="132-request-body"></a>1.3.2 要求本文

Empty

#### <a name="133-response"></a>1.3.3 応答

成功した場合、このメソッドは 200 OK をデバイスの正常性の詳細のリストと共に返します。

### <a name="14-parameters"></a>1.4 パラメーター

- 既定のページ サイズは 20 です
-  [Microsoft Defender for Endpointを使用した OData クエリの](exposed-apis-odata-samples.md)例を参照してください。

### <a name="15-properties"></a>1.5 プロパティ

参照: [1.2 デバイス ウイルス対策正常性の詳細 API プロパティのエクスポート (JSON 応答)](device-health-api-methods-properties.md#12-export-device-antivirus-health-details-api-properties-json-response)

 [OData V4 クエリをサポートします](https://www.odata.org/documentation/)。

### <a name="16-example"></a>1.6 例

#### <a name="request-example"></a>要求の例

要求の例を次に示します。

```http
GET https://api.securitycenter.microsoft.com/api/deviceavinfo 
```

#### <a name="response-example"></a>応答の例

応答の例を次に示します。

```json
{ 

    @odata.context: "https://api.securitycenter.microsoft.com/api/$metadata#DeviceAvInfo", 

"value": [{ 

            "id": "Sample Guid", 

            "machineId": "Sample Machine Guid", 

            "computerDnsName": "appblockstg1", 

            "osKind": "windows", 

            "osPlatform": "Windows10", 

            "osVersion": "10.0.19044.1865", 

            "avMode": "0", 

            "avSignatureVersion": "1.371.1279.0", 

            "avEngineVersion": "1.1.19428.0", 

            "avPlatformVersion": "4.18.2206.108", 

            "lastSeenTime": "2022-08-02T19:40:45Z", 

            "quickScanResult": "Completed", 

            "quickScanError": "", 

            "quickScanTime": "2022-08-02T18:40:15.882Z", 

            "fullScanResult": "", 

            "fullScanError": "", 

            "fullScanTime": null, 

            "dataRefreshTimestamp": "2022-08-02T21:16:23Z", 

            "avEngineUpdateTime": "2022-08-02T00:03:39Z", 

            "avSignatureUpdateTime": "2022-08-02T00:03:39Z", 

            "avPlatformUpdateTime": "2022-06-20T16:59:35Z", 

            "avIsSignatureUpToDate": "True", 

            "avIsEngineUpToDate": "True", 

            "avIsPlatformUpToDate": "True", 

            "avSignaturePublishTime": "2022-08-02T00:03:39Z", 

            "rbacGroupName": "TVM1", 

            "rbacGroupId": 4415 

        }, 

        ... 

     ] 

} 
```

## <a name="2-export-health-reporting-via-files"></a>2 正常性レポートをエクスポートする (ファイル経由)

### <a name="21-api-method-description"></a>2.1 API メソッドの説明

この API 応答には、デバイスごとのウイルス対策の正常性と状態のすべてのデータが含まれます。 次の一意の組み合わせごとにエントリを含むテーブルを返します。

- DeviceId
- デバイス名
- AV モード
- 最新の状態
- 結果をスキャンする

#### <a name="212-limitations"></a>2.1.2 制限事項

- 最大ページ サイズは 200,000 です。
- この API のレート制限は、1 分あたり 30 回の呼び出しと 1 時間あたり 1,000 回の呼び出しです。

### <a name="22-permissions"></a>2.2 アクセス許可

この API を呼び出すには、次のいずれかのアクセス許可が必要です。

| アクセス許可の種類 | アクセス許可 | アクセス許可の表示名 |
|:---|:---|:---|
| アプリケーション | Vulnerability.Read.All | '"脅威と脆弱性の管理" の脆弱性情報を読み取る  |
| 委任 (職場または学校のアカウント) | Vulnerability.Read | '"脅威と脆弱性の管理" の脆弱性情報を読み取る |

アクセス許可の選択方法など、詳細については、「[Microsoft Defender for Endpoint API を使用する」を参照してください](apis-intro.md)。

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/InfoGatheringExport 
```

### <a name="24-parameters"></a>2.4 パラメーター

- ```sasValidHours```: ダウンロード URL が有効になる時間数 (最大 24 時間)。

### <a name="25-properties"></a>2.5 プロパティ

「[1.3 ファイル\)を使用してデバイスウイルス対策の正常性の詳細 API プロパティ\(をエクスポート](device-health-api-methods-properties.md#13-export-device-antivirus-health-details-api-properties-via-files)する」を参照してください。

### <a name="26-examples"></a>2.6 例

#### <a name="261-request-example"></a>2.6.1 要求の例

要求の例を次に示します。

```HTTP
GET https://api-us.securitycenter.contoso.com/api/machines/InfoGatheringExport 
```

#### <a name="262-response-example"></a>2.6.2 応答の例  

応答の例を次に示します。

```json
{

   "@odata.context": "https://api-us.securitycenter.windows.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",

   "exportFiles": [

       "https://tvmexportexternalprdeus.blob.core.windows.net/temp-../2022-08-02/2201/InfoGatheringExport/json/OrgId=../_RbacGroupId=../part-00055-12fc2fcd-8f56-4e09-934f-e8efe7ce74a0.c000.json.gz?sv=2020-08-04&st=2022-08-02T22%3A47%3A11Z&se=2022-08-03T01%3A47%3A11Z&sr=b&sp=r&sig=..",               

       "https://tvmexportexternalprdeus.blob.core.windows.net/temp-../2022-08-02/2201/InfoGatheringExport/json/OrgId=../_RbacGroupId=../part-00055-12fc2fcd-8f56-4e09-934f-e8efe7ce74a0.c000.json.gz?sv=2020-08-04&st=2022-08-02T22%3A47%3A11Z&se=2022-08-03T01%3A47%3A11Z&sr=b&sp=r&sig=.."

   ],


   "generatedTime": "2022-08-02T22:01:00Z"


}
```

## <a name="see-also"></a>関連項目

[デバイスの正常性のメソッドとプロパティをエクスポートする](device-health-api-methods-properties.md)

[デバイスの正常性とコンプライアンスのレポート](machine-reports.md)
