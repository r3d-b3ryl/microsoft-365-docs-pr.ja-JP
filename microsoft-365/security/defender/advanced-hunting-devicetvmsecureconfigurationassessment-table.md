---
title: 高度な検索スキーマの DeviceTvmSecureConfigurationAssessment テーブル
description: 高度なハンティング スキーマの DeviceTvmSecureConfigurationAssessment テーブルのセキュリティ評価イベントについて説明します。 これらの脅威& 脆弱性の管理イベントは、デバイス情報、セキュリティ構成の詳細、影響、コンプライアンス情報を提供します。
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 8acb59c220bd400894aba2be17d5b2ac3216d7591fae5f5928b4670e0c4d2b5e
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53817029"
---
# <a name="devicetvmsecureconfigurationassessment"></a>DeviceTvmSecureConfigurationAssessment

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender
- Microsoft Defender for Endpoint



`DeviceTvmSecureConfigurationAssessment` テーブルの各行には、[脅威および脆弱性管理](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) からの特定のセキュリティ構成に対する評価イベントが含まれます。 このリファレンスを使用して最新の評価結果を確認し、デバイスが準拠しているかどうかを確認します。

高度な検索スキーマの他のテーブルの詳細については、「[高度な検索リファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `DeviceId` | string | サービス内のデバイスの一意の識別子 |
| `DeviceName` | string | デバイスの完全修飾ドメイン名 (FQDN) |
| `OSPlatform` | string | デバイスで実行されているオペレーティング システムのプラットフォーム。 これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。|
| `Timestamp` | datetime | レコードが作成された日付と時刻 |
| `ConfigurationId` | 文字列 | 特定の構成の一意の識別子 |
| `ConfigurationCategory` | string | 構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御 |
| `ConfigurationSubcategory` | string | 構成が属するサブカテゴリまたはサブグループ。 多くの場合、これは特定の機能または機能を説明します。 |
| `ConfigurationImpact` | 文字列 | 構成の評価が全体の構成スコア (1-10) に及ぼす影響 |
| `IsCompliant` | ブール値 | 構成やポリシーが正しく構成されているかどうかを示します |
| `IsApplicable` | ブール値 | 構成またはポリシーがデバイスに適用されるかどうかを示します。 |
| `Context` | string | 構成またはポリシーに関するその他のコンテキスト情報 |
| `IsExpectedUserImpact` | ブール値 | 構成またはポリシーが適用された場合にユーザーに影響を与えるかどうかを示します。 |

## <a name="related-topics"></a>関連項目

- [積極的に脅威を捜索する](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
- [脅威および脆弱性管理の概要](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)