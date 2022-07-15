---
title: Microsoft 365 Defenderの高度なハンティングにおける FileProfile() 関数
description: FileProfile() を使用して、高度なハンティング クエリの結果のファイルに関する情報を強化する方法について説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, FileProfile, ファイル プロファイル, 関数, エンリッチメント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 3e530bd9c1e6af58c83a88fc16b5ac4f9aee60e0
ms.sourcegitcommit: a209c9f86a7b4340a426c4cfed2d36a388c71124
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66797931"
---
# <a name="fileprofile"></a>FileProfile()

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

この `FileProfile()` 関数は、 [高度な捜索](advanced-hunting-overview.md) のエンリッチメント関数であり、クエリで見つかったファイルに次のデータを追加します。

| Column | データ型 | 説明 |
|------------|---------------|-------------|
| `SHA1` | `string` | 記録されたアクションが適用されたファイルの SHA-1 |
| `SHA256` | `string` | 記録されたアクションが適用されたファイルの SHA-256 |
| `MD5` | `string` | 記録されたアクションが適用されたファイルの MD5 ハッシュ |
| `FileSize` | `int` | ファイルのサイズ (バイト単位) |
| `GlobalPrevalence` | `int` | Microsoft によってグローバルに観察されたエンティティのインスタンスの数 |
| `GlobalFirstSeen` | `datetime` | エンティティが Microsoft によってグローバルに最初に観察された日時 |
| `GlobalLastSeen` | `datetime` | エンティティが Microsoft によってグローバルに最後に観察された日時 |
| `Signer` | `string` | ファイルの署名者に関する情報 |
| `Issuer` | `string` | 発行元証明機関 (CA) に関する情報 |
| `SignerHash` | `string` | 署名者を識別する一意のハッシュ値 |
| `IsCertificateValid` | `boolean` | ファイルの署名に使用される証明書が有効かどうか |
| `IsRootSignerMicrosoft` | `boolean` | ルート証明書の署名者が Microsoft で、ファイルが Windows OS に組み込まれているかどうかを示します |
| `SignatureState` | `string` | ファイル署名の状態: SignedValid - ファイルは有効な署名で署名されています。SignedInvalid - ファイルは署名されていますが、証明書は無効です。Unsigned - ファイルは署名されていません。不明 - ファイルに関する情報を取得できません
| `IsExecutable` | `boolean` | ファイルがポータブル実行可能ファイル (PE) ファイルであるかどうか |
| `ThreatName` | `string` | 検出されたマルウェアまたはその他の脅威の検出名 |
| `Publisher` | `string` | ファイルを発行した組織の名前 |
| `SoftwareName` | `string` | ソフトウェア製品の名前 |

## <a name="syntax"></a>構文

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>引数

- **x** - 使用するファイル ID 列: `SHA1`、、`InitiatingProcessSHA1``SHA256`、または `InitiatingProcessSHA256`; 関数が指定されていない場合に使用`SHA1`します
- **y** - エンリッチするレコードの数に制限し、1 ~ 1000。指定されていない場合、関数は 100 を使用します


>[!TIP]
> エンリッチメント関数は、利用可能な場合にのみ補足情報を表示します。 情報の可用性はさまざまであり、多くの要因によって異なります。 クエリで FileProfile() を使用する場合、またはカスタム検出を作成する場合は、この点を考慮してください。 最適な結果を得るには、SHA1 で FileProfile() 関数を使用することをお勧めします。

## <a name="examples"></a>例

### <a name="project-only-the-sha1-column-and-enrich-it"></a>SHA1 列のみを投影してエンリッチする

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>最初の 500 レコードをエンリッチし、低い普及率のファイルを一覧表示する

```kusto
DeviceFileEvents
| where ActionType == "FileCreated" and Timestamp > ago(1d)
| project CreatedOn = Timestamp, FileName, FolderPath, SHA1
| invoke FileProfile("SHA1", 500) 
| where GlobalPrevalence < 15
```

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [その他のクエリの例を取得する](advanced-hunting-shared-queries.md)
