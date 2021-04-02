---
title: エンドポイント用 Microsoft Defender の高度な検索での FileProfile() 関数
description: FileProfile() を使用して高度な検索クエリ結果のファイルに関する情報を強化する方法について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、mdatp、Microsoft Defender ATP、エンドポイント用 Microsoft Defender、Windows Defender、Windows Defender ATP、Windows Defender Advanced Threat Protection、検索、クエリ、テレメトリ、スキーマ参照、kusto、FileProfile、ファイル プロファイル、関数、エンリッチメント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 6c828418d27db24cbd6e87f040486b3abc45e6c6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499553"
---
# <a name="fileprofile"></a>FileProfile()

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

この `FileProfile()` 関数は、高度な検索の[](advanced-hunting-overview.md)エンリッチメント関数で、クエリで見つかったファイルに次のデータを追加します。

Column | データ型 | 説明
-|-|-
SHA1 | 文字列 | 記録されたアクションが適用されたファイルの SHA-1
SHA256 | 文字列 | 記録されたアクションが適用されたファイルの SHA-256
MD5 | 文字列 | 記録されたアクションが適用されたファイルの MD5 ハッシュ
FileSize | int | ファイルのサイズ (バイト単位)
GlobalPrevalence | int | Microsoft がグローバルに観察したエンティティのインスタンス数
GlobalFirstSeen | 日付型 | エンティティが最初に Microsoft によってグローバルに観察された日時
GlobalLastSeen | 日付型 | エンティティが Microsoft によってグローバルに最後に観察された日時
署名者 | 文字列 | ファイルの署名者に関する情報
発行者 | 文字列 | 発行元証明機関 (CA) に関する情報
SignerHash | 文字列 | 署名者を識別する一意のハッシュ値
IsCertificateValid | boolean | ファイルの署名に使用する証明書が有効かどうか
IsRootSignerMicrosoft | boolean | ルート証明書の署名者が Microsoft であるかどうかを示します。
IsExecutable | boolean | ファイルがポータブル実行可能ファイル (PE) ファイルかどうか
ThreatName | 文字列 | マルウェアまたは検出された他の脅威の検出名
発行者 | 文字列 | ファイルを発行した組織の名前
SoftwareName | string | ソフトウェア製品の名前

## <a name="syntax"></a>構文

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>引数

- **x** — 使用するファイル ID 列: `SHA1` 、、または 、 ; `SHA256` `InitiatingProcessSHA1` `InitiatingProcessSHA256` 関数が指定されていない `SHA1` 場合に使用する
- **y** - エンリッチするレコードの数に制限、1 ~ 1000。指定されていない場合、関数は 100 を使用します。

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

- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
