---
title: 高度なハンティング スキーマの AlertInfo テーブル
description: 高度なハンティング スキーマの AlertInfo テーブルでアラート生成イベントについて説明します
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, スキーマ参照, kusto, テーブル, 列, データ型, 説明, AlertInfo, アラート, 重大度, カテゴリ, MITRE, ATT&CK, Microsoft Defender for Endpoint,Microsoft Defender for Office 365、Microsoft Cloud App Security、MCAS、Microsoft Defender for Identity
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
ms.openlocfilehash: 20d9cc76f3da2efea31c0cf430022d8a83897583
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67388663"
---
# <a name="alertinfo"></a>AlertInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender


## <a name="get-access"></a>アクセスを取得する
高度なハンティングやその他[のMicrosoft 365 Defender](microsoft-365-defender.md)機能を使用するには、Azure Active Directory で適切なロールが必要です。 [高度な捜索に必要なロールとアクセス許可について説明](custom-roles.md)します。

また、エンドポイント データへのアクセスは、Microsoft Defender for Endpointのロールベースのアクセス制御 (RBAC) 設定によって決まります。 [Microsoft 365 Defenderへのアクセスの管理について説明します](m365d-permissions.md)。

## <a name="alertinfo"></a>AlertInfo

`AlertInfo` [高度なハンティング](advanced-hunting-overview.md) スキーマの表には、Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Cloud Apps、およびMicrosoft Defender for Identity。 このテーブルの情報を返すクエリを作成するには、このリファレンスを使用します。

高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。

| 列名 | データ型 | 説明 |
|-------------|-----------|-------------|
| `Timestamp` | `datetime` | イベントが記録された日付と時刻 |
| `AlertId` | `string` | アラートの一意識別子 |
| `Title` | `string` | アラートのタイトル |
| `Category` | `string` | アラートで識別された脅威インジケーターまたは侵害アクティビティの種類 |
| `Severity` | `string` | アラートで識別された脅威インジケーターまたは侵害アクティビティの起こりうる影響 (高、中、低) を示します。 |
| `ServiceSource` | `string` | アラート情報を提供した製品またはサービス |
| `DetectionSource` | `string` | 注目すべきコンポーネントまたはアクティビティを識別した検出テクノロジまたはセンサー |
| `AttackTechniques` | `string` | MITRE ATT&アラートをトリガーしたアクティビティに関連付けられた CK 手法 |

## <a name="related-topics"></a>関連項目
- [高度な追求の概要](advanced-hunting-overview.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [共有クエリを使用する](advanced-hunting-shared-queries.md)
- [デバイス、メール、アプリ、ID 全体で探す](advanced-hunting-query-emails-devices.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [クエリのベスト プラクティスを適用する](advanced-hunting-best-practices.md)
