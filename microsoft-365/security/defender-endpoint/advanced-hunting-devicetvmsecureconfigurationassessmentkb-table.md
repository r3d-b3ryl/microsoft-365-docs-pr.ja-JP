---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessmentKB テーブル
description: Advanced ハンティング スキーマの DeviceTvmSecureConfigurationAssessmentKB テーブルで、Threat & の脆弱性管理によって評価されるさまざまなセキュリティで保護された構成について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、スキーマ参照、kusto、table、列、データ型、説明、脅威 & 脆弱性管理、TVM、デバイス管理、セキュリティ構成、MITRE ATT&CK フレームワーク、ナレッジ ベース、KB、DeviceTvmSecureConfigurationAssessmentKB
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3ba0d90fae872eff209b41b7ba62baeccfe62808
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067004"
---
# <a name="devicetvmsecureconfigurationassessmentkb"></a>DeviceTvmSecureConfigurationAssessmentKB

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

高度な検索スキーマの `DeviceTvmSecureConfigurationAssessmentKB` テーブルには、自動更新がデバイスでオンになっているかどうかなど、[脅威および脆弱性管理](next-gen-threat-and-vuln-mgt.md)によりチェックされるさまざまなセキュリティ構成に関する情報が含まれています。 このテーブルには、リスク情報、関連する業界ベンチマーク、適用される MITRE ATT&CK のテクニックおよび戦術も記載されています。 このテーブルの情報を返すクエリを作成するには、この参照を使用できます。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)」 を参照してください。

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

- [高度な検出の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-reference.md)
- [脅威および脆弱性管理の概要](next-gen-threat-and-vuln-mgt.md)
