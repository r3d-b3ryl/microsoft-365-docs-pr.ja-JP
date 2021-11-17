---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessmentKB テーブル
description: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessmentKB テーブルに記載される、脅威および脆弱性管理により評価されるさまざまなセキュリティ構成について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、脅威 & 脆弱性の管理、TVM、デバイス管理、セキュリティ構成、MITRE ATT&CK フレームワーク、ナレッジ ベース、KB、DeviceTvmSecureConfigurationAssessmentKBsment
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
ms.openlocfilehash: bf65634e38d7676eaef20386b3effa828aa46f4b
ms.sourcegitcommit: bd43f08b4719ba984ea6712227508d4a281148cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2021
ms.locfileid: "61041879"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint


高度 `DeviceTvmSecureConfigurationAssessmentKB` な検索スキーマの表には、Threat &脆弱性管理によってチェックされるさまざまなセキュリティ[で保護された構成に関する情報が含まれている。](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) このテーブルには、リスク情報、関連する業界ベンチマーク、適用される MITRE ATT&CK のテクニックおよび戦術も記載されています。

このテーブルは、イベントやレコードを返す必要があります。 このテーブルを [DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) テーブルに結合して、返される評価のセキュリティ構成に関するテキスト情報を表示することをお `ConfigurationId` 勧めします。

たとえば、テーブルにクエリを実行すると、評価結果に表示されるセキュリティ構成を `DeviceTvmSecureConfigurationAssessment` `ConfigurationDescription` 表示できます。 この情報は、このテーブルを使用してプロジェクトに参加 `DeviceTvmSecureConfigurationAssessment` することで `ConfigurationId` 確認できます `ConfigurationDescription` 。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `ConfigurationId` | string | 特定の構成の一意の識別子 |
| `ConfigurationImpact` | string | 構成が全体の構成スコアに与える影響の評価 (1-10) |
| `ConfigurationName` | string | 構成の表示名 |
| `ConfigurationDescription` | string | 構成の説明 |
| `RiskDescription` | string | 関連するリスクの説明 |
| `ConfigurationCategory` | string | 構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御|
| `ConfigurationSubcategory` | string |構成が属するサブカテゴリまたはサブグループ。 多くの場合、これは特定の機能または機能を説明します。 |
| `ConfigurationBenchmarks` | string | 同じ構成または類似した構成を推奨する業界ベンチマークの一覧 |
| `Tags` | string | セキュリティ構成を識別または分類するために使用されるさまざまな属性を表すラベル |
| `RemediationOptions` | string | 関連するリスクを軽減または対処するために推奨されるアクション |

次のクエリ例を試して、関連する構成メタデータと、非準拠のウイルス対策構成を持つデバイスに関する情報を表から返 `DeviceTvmSecureConfigurationAssessment` します。

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
- [脅威および脆弱性管理の概要](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)