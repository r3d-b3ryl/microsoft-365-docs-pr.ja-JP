---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessmentKB テーブル
description: 高度なハンティング スキーマの DeviceTvmSecureConfigurationassessmentKB テーブルで、Microsoft Defender 脆弱性の管理によって評価されるさまざまなセキュリティで保護された構成について説明します。
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, データ型, 説明, 脅威&脆弱性管理, TVM, デバイス管理, セキュリティ構成, MITRE ATT&CK フレームワーク, サポート情報, KB, DeviceTvmSecureConfigurationassessmentKB, MDVM,Microsoft Defender 脆弱性の管理
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
ms.openlocfilehash: 881f1b12f85529e4295c6de11b975d69dc617b81
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67329423"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint

`DeviceTvmSecureConfigurationAssessmentKB`高度なハンティング スキーマの表には、[Microsoft Defender 脆弱性の管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)によってチェックされたさまざまなセキュリティで保護された構成に関する情報が含まれています。 このテーブルには、リスク情報、関連する業界ベンチマーク、適用される MITRE ATT&CK のテクニックおよび戦術も記載されています。

このテーブルは、イベントまたはレコードを返しません。 このテーブルを [DeviceTvmSecureConfigurationassessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) テーブル `ConfigurationId` に参加させて、返された評価のセキュリティ構成に関するテキスト情報を表示することをお勧めします。

たとえば、テーブルに対してクエリを `DeviceTvmSecureConfigurationAssessment` 実行する場合は、評価結果に表示されるセキュリティ構成を表示 `ConfigurationDescription` できます。 この情報は、このテーブルを using `ConfigurationId` と project `ConfigurationDescription`に`DeviceTvmSecureConfigurationAssessment`結合することで確認できます。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `ConfigurationId` | `string` | 特定の構成の一意の識別子 |
| `ConfigurationImpact` | `string` | 構成が全体の構成スコアに与える影響の評価 (1-10) |
| `ConfigurationName` | `string` | 構成の表示名 |
| `ConfigurationDescription` | `string` | 構成の説明 |
| `RiskDescription` | `string` | 関連するリスクの説明 |
| `ConfigurationCategory` | `string` | 構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御|
| `ConfigurationSubcategory` | `string` |構成が属するサブカテゴリまたはサブグループ。 多くの場合、これは特定の機能または機能を説明します。 |
| `ConfigurationBenchmarks` | `string` | 同じ構成または類似した構成を推奨する業界ベンチマークの一覧 |
| `Tags` | `string` | セキュリティ構成を識別または分類するために使用されるさまざまな属性を表すラベル |
| `RemediationOptions` | `string` | 関連するリスクを軽減または対処するための推奨されるアクション |

次のクエリ例を試して、関連する構成メタデータと、非準拠のウイルス対策構成を持つデバイスに関する情報を `DeviceTvmSecureConfigurationAssessment` 表から返すことができます。

```kusto
// Get information on devices with antivirus configurations issues
DeviceTvmSecureConfigurationAssessment
| where ConfigurationSubcategory == 'Antivirus' and IsApplicable == 1 and IsCompliant == 0
| join kind=leftouter (
    DeviceTvmSecureConfigurationAssessmentKB
    | project ConfigurationId, ConfigurationName, ConfigurationDescription, RiskDescription, Tags, ConfigurationImpact
) on ConfigurationId
| project DeviceName, OSPlatform, ConfigurationId, ConfigurationName, ConfigurationCategory, ConfigurationSubcategory, ConfigurationDescription, RiskDescription, ConfigurationImpact, Tags
```

## <a name="related-topics"></a>関連項目

- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [Microsoft Defender 脆弱性の管理の概要](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)