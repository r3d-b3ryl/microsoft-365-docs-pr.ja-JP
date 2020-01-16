---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessmentKB テーブル
description: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessmentKB テーブルに記載される、脅威および脆弱性管理により評価されるさまざまなセキュリティ構成について説明します。
keywords: '高度な検索、脅威の検索、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、description、threat & 脆弱性管理、TVM、デバイス管理、セキュリティの構成、MITRE ATT&DeviceTvmSecureConfigurationAssessmentKB: サポート技術情報、KB、'
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 2bcf3ab438dc8894c186ac7ee477af1821e783cc
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210182"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

**適用対象:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

高度な検索スキーマの `DeviceTvmSecureConfigurationAssessmentKB` テーブルには、自動更新がデバイスでオンになっているかどうかなど、[脅威および脆弱性管理](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)によりチェックされるさまざまなセキュリティ構成に関する情報が含まれています。 このテーブルには、リスク情報、関連する業界ベンチマーク、適用される MITRE ATT&CK のテクニックおよび戦術も記載されています。 このテーブルの情報を返すクエリを作成するには、この参照を使用できます。

高度な検索スキーマのその他のテーブルの詳細については、「[高度な検索リファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

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
| `RelatedMitreTechniques` | string | 構成に関連する Mitre ATT&CK フレームワーク テクニックの一覧 |
| `RelatedMitreTactics ` | string | 構成に関連する Mitre ATT&CK フレームワーク戦術の一覧 |

## <a name="related-topics"></a>関連項目

- [積極的に脅威を検索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使う](advanced-hunting-shared-queries.md)
- [デバイスとメール全体で脅威を検索する](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [脅威および脆弱性管理の概要](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
