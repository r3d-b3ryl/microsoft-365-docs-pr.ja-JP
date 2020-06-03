---
title: Microsoft の脅威保護のための高度な検索の FileProfile () 関数
description: FileProfile () を使用して、高度な検索クエリ結果のファイルに関する情報を表示する方法について説明します。
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、FileProfile、file profile、function、エンリッチメント
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 039b9dc038cd1a1645aee2289f3bdb389eb3f426
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515924"
---
# <a name="fileprofile"></a>FileProfile ()

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

この `FileProfile()` 関数は、クエリによって検出されたファイルに次のデータを追加する、[高度な](advanced-hunting-overview.md)検索のエンリッチメント関数です。

| 列 | データ型 | 説明 |
|------------|-------------|-------------|
| SHA1 | 文字列 | 記録されたアクションが適用されたファイルの SHA-1 |
| SHA256 | string | 記録された操作が適用されたファイルの256 |
| MD5 | string | 記録されたアクションが適用されたファイルの MD5 ハッシュ |
| FileSize | int | ファイルのサイズ (バイト数) |
| GlobalPrevalence | int | Microsoft によってグローバルに監視されたエンティティのインスタンスの数 |
| GlobalFirstSeen | 日付型 | エンティティが最初に Microsoft によって監視された日付と時刻 |
| GlobalLastSeen | 日付型 | エンティティが最後に Microsoft によって監視された日付と時刻 |
| 署名者 | string | ファイルの署名者に関する情報 |
| 発行者 | string | 発行元の証明機関 (CA) に関する情報 |
| SignerHash | string | 署名者を識別する一意のハッシュ値 |
| IsCertificateValid | boolean | ファイルへの署名に使用された証明書が有効かどうか |
| IsRootSignerMicrosoft | boolean | ルート証明書の署名者が Microsoft であるかどうかを示します |
| IsExecutable | boolean | ファイルが移植可能な実行可能 (PE) ファイルであるかどうか |
| Mail.threatname です | string | 検出されたマルウェアまたは他の脅威の検出名 |
| Publisher | string | ファイルを発行した組織の名前 |
| SoftwareName | string | ソフトウェア製品の名前 |

## <a name="syntax"></a>構文

```kusto
invoke FileProfile(x,y)
```

## <a name="arguments"></a>引数

- **x** —使用するファイル ID 列: `SHA1` 、 `SHA256` 、 `InitiatingProcessSHA1` または `InitiatingProcessSHA256` 関数が `SHA1` 未指定の場合に使用します。
- **y** —強化するレコード数を1-1000 に制限します。関数は、未指定の場合は100を使用します。

## <a name="examples"></a>例

### <a name="project-only-the-sha1-column-and-enrich-it"></a>SHA1 列のみをプロジェクトにして、さらに充実します。

```kusto
DeviceFileEvents
| where isnotempty(SHA1) and Timestamp > ago(1d)
| take 10
| project SHA1
| invoke FileProfile()
```

### <a name="enrich-the-first-500-records-and-list-low-prevalence-files"></a>最初の500レコードを強化し、流行していないファイルを一覧表示する

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