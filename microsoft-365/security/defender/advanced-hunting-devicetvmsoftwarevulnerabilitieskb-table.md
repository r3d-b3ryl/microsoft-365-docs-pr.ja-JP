---
title: 高度な捜索スキーマの DeviceTvmSoftwareVulnerabilitiesKB テーブル
description: 高度なハンティング スキーマの DeviceTvmSoftwareVulnerabilitiesKB テーブルで、Microsoft Defender 脆弱性の管理によって追跡されるソフトウェアの脆弱性について説明します。
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ, 参照, kusto, テーブル, 列, データ型, 説明, 脅威&脆弱性管理, TVM, デバイス管理, ソフトウェア, インベントリ, 脆弱性, CVE ID, CVSS, DeviceTvmSoftwareVulnerabilitiesKB
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
ms.openlocfilehash: 91656759f4f70c52776cdad87c4061e2c340088b
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67329203"
---
# <a name="devicetvmsoftwarevulnerabilitieskb"></a>DeviceTvmSoftwareVulnerabilitiesKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint



`DeviceTvmSoftwareVulnerabilitiesKB`高度なハンティング スキーマの表には、デバイスを評価[Microsoft Defender 脆弱性の管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)脆弱性の一覧が含まれています。 このテーブルの情報を返すクエリを作成するには、このレファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `CveId` | `string` | 共通脆弱性識別子 (CVE) システムでセキュリティの脆弱性に割り当てられている一意の識別子  |
| `CvssScore` | `string` | 共通脆弱性評価システム (CVSS) でセキュリティの脆弱性に割り当てられている重大度スコア |
| `IsExploitAvailable` | `boolean` | 脆弱性の悪用コードが公開されているかどうかを示す |
| `VulnerabilitySeverityLevel` | `string` | CVSS スコアと脅威の度合いの影響を受ける動的要因に基づいて、セキュリティの脆弱性に割り当てられている重大度レベル |
| `LastModifiedTime` | `datetime` | アイテムまたは関連するメタデータが最後に変更された日付 |
| `PublishedDate` | `datetime` | 脆弱性が一般に公開された日付 |
| `VulnerabilityDescription` | `string` | 脆弱性と関連するリスクの説明 |
| `AffectedSoftware` | `string` | 脆弱性の影響を受けるすべてのソフトウェア製品の一覧 |

## <a name="related-topics"></a>関連項目

- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [Microsoft Defender 脆弱性の管理の概要](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)