---
title: 高度なハンティング スキーマの DeviceTvmInfoGatheringKB テーブル
description: 高度なハンティング スキーマの DeviceTvmInfoGathering テーブルで、評価イベントのメタデータについて説明します。
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, 脅威&脆弱性管理, TVM, デバイス管理, ソフトウェア, インベントリ, 脆弱性, CVE ID, OS DeviceTvmSoftwareInventoryVulnerabilities
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
ms.openlocfilehash: c654ca395762426072bf8e5e20fd3f62e78a480c
ms.sourcegitcommit: bfbe2574f487ced69e711b48ce140120bd99181b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2022
ms.locfileid: "66607110"
---
# <a name="devicetvminfogatheringkb"></a>DeviceTvmInfoGatheringKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

`DeviceTvmInfoGatheringKB`高度なハンティング スキーマのテーブルには、テーブルで収集された[Microsoft Defender 脆弱性の管理](/microsoft-365/security/defender-vulnerability-management/defender-vulnerability-management)評価イベント データのメタデータが`DeviceTvmInfoGathering`含まれています。 この `DeviceTvmInfoGatheringKB` 表には、Defender Vulnerability Management の情報収集によってデバイスを評価するために使用されるさまざまな構成と攻撃領域の評価の一覧が含まれています。 このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `IgId` | `string` | 収集された情報の一意識別子 |
| `FieldName` | `string` | DeviceTvmInfoGathering テーブルの AdditionalFields 列にこの情報が表示されるフィールドの名前 |
| `Description` | `string` | 収集された情報の説明 |
| `Categories` | `string` | 情報が属するカテゴリの一覧 (JSON 配列形式)  |
| `DataStructure` | `string` | 収集された情報のデータ構造  |

この表を使用して、使用可能な情報の種類を調べて、後で `DeviceTvmInfoGathering` ハンティング クエリを微調整できます。

たとえば、収集される情報の一覧を表示するには、次のクエリを試すことができます。

```kusto
// Check out what is being collected 
DeviceTvmInfoGatheringKB  
```

結果から、使用可能なカテゴリに興味を持つようになったとします。次のクエリを使用できます。

```kusto
// Return all available categories 
DeviceTvmInfoGatheringKB 
| mv-expand Categories to typeof(string) 
| distinct Categories 
```

次に、TLS プロトコルに関連する評価カテゴリを表示するとします。

```kusto
// Return all findings for a specified category 
DeviceTvmInfoGatheringKB 
| where Categories contains "tls" 
```

その後、結果のフィールドを使用 `DeviceTvmInfoGathering` して、TLS クライアント バージョン 1.0 を使用してデバイスの一覧を取得できます。

```kusto
// Return all devices on which the TLS version 1.0 is enabled 
DeviceTvmInfoGathering 
| where AdditionalFields.TlsClient10 == "Enabled" or AdditionalFields.TlsServer10 == "Enabled" 
```

## <a name="related-topics"></a>関連トピック

- [DeviceTvmInfoGathering](advanced-hunting-devicetvminfogathering-table.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [Defender の脆弱性管理の概要](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
