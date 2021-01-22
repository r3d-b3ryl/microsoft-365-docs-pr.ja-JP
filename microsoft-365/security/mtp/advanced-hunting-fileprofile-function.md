---
title: Microsoft 365 Defender の高度な検索での FileProfile() 関数
description: FileProfile() を使用して高度な検索クエリ結果のファイルに関する情報を強化する方法について説明します。
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、FileProfile、ファイル プロファイル、関数、エンリッチメント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 68196f126ac470088d7ba5e2923accc492d8764c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929552"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

この `FileProfile()` 関数は高度な検索のエン[](advanced-hunting-overview.md)リッチメント関数で、クエリで見つかったファイルに次のデータを追加します。

| Column | データ型 | 説明 |
|------------|-------------|-------------|
| SHA1 | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| SHA256 | string | 記録されたアクションが適用されたファイルの SHA-256 |
| MD5 | string | 記録されたアクションが適用されたファイルの MD5 ハッシュ |
| FileSize | int | ファイルのサイズ (バイト単位) |
| GlobalPrevalence | int | Microsoft がグローバルに観察したエンティティのインスタンス数 |
| GlobalFirstSeen | 日付型 | エンティティが最初に Microsoft によってグローバルに観察された日時 |
| GlobalLastSeen | 日付型 | エンティティが Microsoft によってグローバルに最後に観察された日時 |
| 署名者 | string | ファイルの署名者に関する情報 |
| 発行者 | string | 発行元証明機関 (CA) に関する情報 |
| SignerHash | string | 署名者を識別する一意のハッシュ値 |
| IsCertificateValid | ブール値 | ファイルの署名に使用する証明書が有効かどうか |
| IsRootSignerMicrosoft | ブール値 | ルート証明書の署名者が Microsoft かどうかを示します |
| IsExecutable | ブール値 | ファイルがポータブル実行可能 (PE) ファイルかどうか |
| ThreatName | string | 検出されたマルウェアまたは他の脅威の検出名 |
| 発行者 | string | ファイルを発行した組織の名前 |
| SoftwareName | string | ソフトウェア製品の名前 |

## <a name="syntax"></a>構文

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>引数

- **x**—使用するファイル ID 列: `SHA1` `SHA256` `InitiatingProcessSHA1` ,, `InitiatingProcessSHA256` or ; function uses `SHA1` if unspecified
- **y**- エンリッチ処理するレコード数に制限、1 ~ 1000。指定されていない場合、関数は 100 を使用します。

## <a name="examples"></a>例

### <a name="project-only-the-sha1-column-and-enrich-it"></a>SHA1 列のみをプロジェクト化して強化する

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>最初の 500 レコードを充実し、低確認ファイルを一覧表示する

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [その他のクエリ例を取得する](advanced-hunting-shared-queries.md)
