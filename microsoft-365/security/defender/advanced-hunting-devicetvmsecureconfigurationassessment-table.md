---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessment テーブル
description: 高度なハンティング スキーマの DeviceTvmSecureConfigurationAssessment テーブルのセキュリティ評価イベントについて説明します。 これらのイベントは、デバイス情報、セキュリティ構成の詳細、影響、コンプライアンス情報を提供します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、説明、脅威& 脆弱性の管理、TVM、デバイス管理、セキュリティ構成、DeviceTvmSecureConfigurationAssessment
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
ms.openlocfilehash: 3487ced09cfd0bbd3a25f8e8124f84a05368d290
ms.sourcegitcommit: bd43f08b4719ba984ea6712227508d4a281148cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2021
ms.locfileid: "61035972"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint


`DeviceTvmSecureConfigurationAssessment` テーブルの各行には、[脅威および脆弱性管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) からの特定のセキュリティ構成に対する評価イベントが含まれます。 このリファレンスを使用して最新の評価結果を確認し、デバイスが準拠しているかどうかを確認します。

このテーブルを[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)テーブルと結合すると、たとえば、構成評価結果の表の列から構成のテキスト説明を表示できます。 `ConfigurationId` `ConfigurationDescription` `DeviceTvmSecureConfigurationAssessmentKB`

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `DeviceId` | string | サービス内のデバイスの一意の識別子 |
| `DeviceName` | string | デバイスの完全修飾ドメイン名 (FQDN) |
| `OSPlatform` | string | デバイスで実行されているオペレーティング システムのプラットフォーム。 11、Windows Windows 10、および 7 など、同じファミリ内Windows 10オペレーティング システムWindows示します。|
| `Timestamp` | datetime | レコードが作成された日付と時刻 |
| `ConfigurationId` | 文字列 | 特定の構成の一意の識別子 |
| `ConfigurationCategory` | string | 構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御 |
| `ConfigurationSubcategory` | string | 構成が属するサブカテゴリまたはサブグループ。 多くの場合、文字列は特定の機能または機能を記述します。 |
| `ConfigurationImpact` | string | 構成の評価が全体の構成スコア (1-10) に及ぼす影響 |
| `IsCompliant` | ブール値 | 構成やポリシーが正しく構成されているかどうかを示します |
| `IsApplicable` | ブール値 | 構成またはポリシーがデバイスに適用されるかどうかを示します。 |
| `Context` | string | 構成またはポリシーに関するその他のコンテキスト情報 |
| `IsExpectedUserImpact` | ブール値 | 構成またはポリシーが適用された場合にユーザーに影響を与えるかどうかを示します。 |

次のクエリ例を使用して、非準拠のウイルス対策構成を持つデバイスに関する情報と、関連する構成メタデータを表から返 `DeviceTvmSecureConfigurationAssessmentKB` します。

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