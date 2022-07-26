---
title: デバイスごとの証明書の評価方法とプロパティ
description: "\"脅威と脆弱性の管理\" データをプルする証明書 API に関する情報を提供します。 さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。 一般に、各 API 呼び出しには、組織内のデバイスに必要なデータが含まれています。"
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
ms.openlocfilehash: 69ba04d80a14e73550b65df19d17627616597b5b
ms.sourcegitcommit: 6e570b79944862c86735db455349b685d5b903b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/26/2022
ms.locfileid: "67020453"
---
# <a name="export-certificate-inventory-per-device"></a>デバイスごとの証明書インベントリのエクスポート

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender 脆弱性の管理](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender 脆弱性の管理を体験しますか? [Microsoft Defender 脆弱性の管理パブリック プレビュー試用版](../defender-vulnerability-management/get-defender-vulnerability-management.md)にサインアップする方法の詳細については、こちらを参照してください。

さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。 一般に、各 API 呼び出しには、組織内のデバイスに必要なデータが含まれています。

- **JSON 応答**  API は、組織内のすべてのデータを JSON 応答としてプルします。 この方法は、 _100 K 未満のデバイスを持つ小規模な組織_ に最適です。 応答はページ分割されるため、応答の odata.nextLink フィールドを使用 \@して次の結果をフェッチできます。

- **ファイル経由** この API ソリューションを使用すると、大量のデータをより迅速かつ確実にプルできます。 そのため、100 K を超えるデバイスを持つ大規模な組織に推奨されます。 この API は、組織内のすべてのデータをダウンロード ファイルとしてプルします。 応答には、Azure Storage からすべてのデータをダウンロードするための URL が含まれています。 Azure Storage から次のようにデータをダウンロードできます。
  - すべての組織データを含むダウンロード URL の一覧を取得するには、API を呼び出します。
  - ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。

"_JSON 応答_ または _ファイル経由_" を使用して収集されるデータは、現在の状態の現在のスナップショットです。 履歴データは含まれません。 履歴データを収集するには、お客様が独自のデータ ストレージにデータを保存する必要があります。

> [!NOTE]
> 特に明記されていない限り、一覧表示されているすべてのエクスポート セキュリティ ベースライン評価方法は **_、完全なエクスポート_** と **_デバイス別_** ( **_デバイスごと_** とも呼ばれます) です。

## <a name="1-export-certificate-assessment-json-response"></a>1. 証明書の評価をエクスポートする (JSON 応答)

### <a name="11-api-method-description"></a>1.1 API メソッドの説明

デバイスごとに、すべてのデバイスのすべての証明書評価を返します。 DeviceId、拇印、およびパスの一意の組み合わせごとに個別のエントリを持つテーブルを返します。

#### <a name="12-limitations"></a>1.2 制限事項

- 最大ページ サイズは 200,000 です。
- この API のレート制限は、1 分あたり 30 回の呼び出しと 1 時間あたり 1,000 回の呼び出しです。

### <a name="13-parameters"></a>1.3 パラメーター

- pageSize (既定値は 50,000): 応答する結果の数。
- $top: 返される結果の数 (@odata.nextLink が返されないため、すべてのデータがプルされるわけではありません)。

### <a name="14-http-request"></a>1.4 HTTP 要求

```http
GET /api/machines/certificateAssessmentByMachine
```

### <a name="15-properties-json-response"></a>1.5 プロパティ (JSON 応答)

> [!NOTE]
> 各レコードは約 1 KB のデータです。 正しい pageSize パラメーターを選択するときは、これを考慮する必要があります。
>
> 応答で追加の列が返される場合があります。 これらの列は一時的なものであり、削除される可能性があります。 ドキュメント化された列のみを使用します。
>
> 次の表で定義されているプロパティは、プロパティ ID でアルファベット順に一覧表示されます。 この API を実行する場合、結果の出力は必ずしもこの表に示されているのと同じ順序で返されるとは限りません。

プロパティ (ID)|データ型|説明
:---|:---|:---
|DeviceId|String|サービス内のデバイスの一意の識別子。
|DeviceName|String|デバイスの完全修飾ドメイン名 (FQDN)。
|Thumbprint|ブール型|証明書の一意の識別子。
|Path|String|証明書の場所。
|SignatureAlgorithm|String|ハッシュ アルゴリズムと暗号化アルゴリズムが使用されます。
|KeySize|String|署名アルゴリズムで使用されるキーのサイズ。
|ExpirationDate|String|証明書が無効になった日付と時刻。
|IssueDate|String|証明書が有効になった最も早い日付と時刻。
|SubjectType|String|証明書の所有者が CA またはエンド エンティティであるかどうかを示します。
|シリアル番号|String|証明機関のシステム内の証明書の一意の識別子。
|IssuedTo|オブジェクト|証明書が属するエンティティ。には、デバイス、個人、または組織を指定できます。
|IssuedBy|オブジェクト|情報を検証し、証明書に署名したエンティティ。
|KeyUsage|String|証明書の公開キーの有効な暗号化の使用。
|ExtendedKeyUsage|String|証明書のその他の有効な用途。
|RbacGroupId|String|ロールベースのアクセス制御 (RBAC) グループ ID。
|RbacGroupName|String|ロールベースのアクセス制御 (RBAC) グループ。 このデバイスが RBAC グループに割り当てられていない場合、値は "未割り当て" になります。 組織に RBAC グループが含まれていない場合、値は "None" になります。

## <a name="16-example"></a>1.6 例

### <a name="161-request-example"></a>1.6.1 要求の例

```http
GET https://api.securitycenter.microsoft.com/api/machines/BaselineComplianceAssessmentByMachine
```

### <a name="162-response-example"></a>1.6.2 応答の例

```json

  {
     "@odata.context":"https://127.0.0.1/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetCertificateAssessment)",
      "value":[
        {
        "deviceId":"49126b9e4a5473b5229c73799e9e55c48668101b",
        "deviceName":"testmachine5",
        "thumbprint":"A4B37F4F6DE956922273D5CB8E7E0AAFB7033B90",
        "path":"LocalMachine\\TestSignRoot\\A4B37F4F6DE956922273D5CB8E7E0AAFB7033B90",
        "signatureAlgorithm":"sha384ECDSA",
        "keyLength":0,"notAfter":"0001-01-01T00:00:00Z",
        "notBefore":"0001-01-01T00:00:00Z",
        "subjectType":"CA",
        "serialNumber":"6086A185EAFA2B9943B4671603F40323",
        "subjectObject":null,
        "issuerObject":null,
        "keyUsageArray":null,
        "extendedKeyUsageArray":null,
        "isSelfSigned":false,
        "rbacGroupId":4226,
        "rbacGroupName":"testO6343398Gq31"}],
        "@odata.nextLink":"https://127.0.0.1/api/machines/CertificateAssessmentByMachine?pagesize=1&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMi0wMy0yMS8wNTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjF9"
  }
```

## <a name="2-export-certificate-assessment-via-files"></a>2. 証明書の評価をエクスポートする (ファイル経由)

### <a name="21-api-method-description"></a>2.1 API メソッドの説明

デバイスごとに、すべてのデバイスのすべての証明書評価を返します。 DeviceId、拇印、およびパスの一意の組み合わせごとに個別のエントリを持つテーブルを返します。

#### <a name="22-limitations"></a>2.2 制限事項

- この API のレート制限は、1 分あたり 5 回の呼び出しと 1 時間あたり 20 回の呼び出しです。 

### <a name="23-parameters"></a>2.3 パラメーター

- sasValidHours: ダウンロード URL が有効になる時間数 (最大 24 時間)。

### <a name="24-http-request"></a>2.4 HTTP 要求

```http
GET /api/machines/certificateAssessmentExport
```

### <a name="25-properties-json-response"></a>2.5 プロパティ (JSON 応答)

> [!NOTE]
> ファイルは、複数行の Json 形式の gzip 圧縮&です。
>
> ダウンロード URL は 3 時間だけ有効です。それ以外の場合は、パラメーターを使用できます。
>
> ダウンロード速度を最大化するには、データが存在するのと同じ Azure リージョンからデータをダウンロードしていることを確認します。
>
> 各レコードは約 1 KB のデータです。 この点を考慮に入れる必要があります。これは、自分に適した pageSize パラメーターを選択する場合に考慮する必要があります。
>
> 応答で追加の列が返される場合があります。 これらの列は一時的なものであり、削除される可能性があります。 ドキュメント化された列のみを使用します。

プロパティ (ID)|データ型|説明
:---|:---|:---
|ファイルをエクスポートする|String[array]|組織の現在のスナップショットを保持しているファイルのダウンロード URL の一覧。
|GeneratedTime|DateTime|エクスポートが生成された時刻。


## <a name="26-example"></a>2.6 例

### <a name="261-request-example"></a>2.6.1 要求の例

```http
GET https://api.securitycenter.contoso.com/api/machines/certificateAssessmentExport
```

### <a name="262-response-example"></a>2.6.2 応答の例

```json
    {
        "@odata.context":"https://127.0.0.1/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
        "exportFiles":["https://tvmexportexternalstgeus.blob.core.windows.net/temp-5c080622-f613-42bb-9fee-e17ccdff90d3/2022-03-20/1318/CertificateAssessmentExport/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=4226/part-00000-65a62a9d-7a01-4d78-bbdb-6d3e07b34cc9.c000.json.gz?sv=2020-02-10&st=2022-03-20T13%3A35%3A37Z&se=2022-03-20T16%3A35%3A37Z&sr=b&sp=r&sig=IMmwTOYmGvU0ei5AHLNAxnFCmZkE2jvBHzRmuAu9xaA%3D","https://tvmexportexternalstgeus.blob.core.windows.net/temp-5c080622-f613-42bb-9fee-e17ccdff90d3/2022-03-20/1318/CertificateAssessmentExport/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=4414/part-00000-65a62a9d-7a01-4d78-bbdb-6d3e07b34cc9.c000.json.gz?sv=2020-02-10&st=2022-03-20T13%3A35%3A37Z&se=2022-03-20T16%3A35%3A37Z&sr=b&sp=r&sig=2r0y74WZsATa0DjQTwfBxNqL5vN2Wl0AZKHMNrxuJ30%3D","https://tvmexportexternalstgeus.blob.core.windows.net/temp-5c080622-f613-42bb-9fee-e17ccdff90d3/2022-03-20/1318/CertificateAssessmentExport/json/OrgId=47d41a0c-188d-46d3-bbea-a93dbc0bfcaa/_RbacGroupId=75/part-00000-65a62a9d-7a01-4d78-bbdb-6d3e07b34cc9.c000.json.gz?sv=2020-02-10&st=2022-03-20T13%3A35%3A37Z&se=2022-03-20T16%3A35%3A37Z&sr=b&sp=r&sig=uVdY4%2BBpMdPMwaD3G0RJTZkS4R9J8oN8I3tu%2FOcG35c%3D"],
        "generatedTime":"2022-03-20T13:18:00Z"
   }
```
