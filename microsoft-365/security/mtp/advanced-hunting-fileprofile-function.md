---
title: Microsoft 365 Defender の高度な検索での FileProfile() 関数
description: FileProfile() を使用して高度な検索クエリ結果のファイルに関する情報を強化する方法について説明します。
keywords: 高度な狩猟、脅威の検出、サイバー脅威の検出、Microsoft の脅威保護、microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、FileProfile、ファイル プロファイル、関数、エンリッチメント
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
ms.openlocfilehash: f2e92967b8951cd0f5a3c394a537404db1d53819
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50424025"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

この `FileProfile()` 関数は、高度な検索の[](advanced-hunting-overview.md)エンリッチメント関数で、クエリで見つかったファイルに次のデータを追加します。

| 列 | データ型 | 説明 |
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
| IsCertificateValid | boolean | ファイルの署名に使用する証明書が有効かどうか |
| IsRootSignerMicrosoft | boolean | ルート証明書の署名者が Microsoft であるかどうかを示します。 |
| IsExecutable | boolean | ファイルがポータブル実行可能ファイル (PE) ファイルかどうか |
| ThreatName | string | マルウェアまたは検出された他の脅威の検出名 |
| 発行者 | string | ファイルを発行した組織の名前 |
| SoftwareName | string | ソフトウェア製品の名前 |

## <a name="syntax"></a>構文

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>引数

- **x**—使用するファイル ID 列: 、、 を使用する関数は `SHA1` `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` `SHA1` 、指定されていない場合に使用します。
- **y**—エンリッチするレコードの数に制限、1 ~ 1000。指定されていない場合、関数は 100 を使用します。


>[!TIP]
> エンリッチメント関数は、利用可能な場合にのみ補足情報を表示します。 情報の可用性はさまざまで、多くの要因に依存します。 クエリで FileProfile() を使用する場合、またはカスタム検出を作成する場合は、この点を考慮してください。 最良の結果を得る場合は、SHA1 で FileProfile() 関数を使用することをお勧めします。

## <a name="examples"></a>例

### <a name="project-only-the-sha1-column-and-enrich-it"></a>SHA1 列のみを投影してエンリッチする

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>最初の 500 レコードを強化し、低普及率のファイルを一覧表示する

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
- [クエリの例を追加する](advanced-hunting-shared-queries.md)
