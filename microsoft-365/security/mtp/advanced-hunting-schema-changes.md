---
title: Microsoft 365 Defender 高度な検索スキーマでの名前の変更
description: 高度な検索スキーマの名前付け変更テーブルと列を追跡および確認する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、データ、名前付けの変更、名前の変更、Microsoft Threat Protection
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 0bef5f4abcaf0d57af9c160ff31f859c2536ccd2
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780813"
---
# <a name="advanced-hunting-schema---naming-changes"></a>高度な検索スキーマ - 名前の変更

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

高度 [な検索スキーマは定期的](advanced-hunting-schema-tables.md) に更新され、新しいテーブルと列が追加されます。 場合によっては、既存の列名の名前が変更または置換され、ユーザー エクスペリエンスが向上します。 クエリに影響を与える可能性がある名前付けの変更を確認するには、この記事を参照してください。

名前付けの変更は、カスタム検出ルールで使用されるクエリを含め、セキュリティ センターに保存されるクエリに自動的に適用されます。 これらのクエリを手動で更新する必要はありません。 ただし、次のクエリを更新する必要があります。
- API を使用して実行されるクエリ
- セキュリティ センターの外部の別の場所に保存されるクエリ

## <a name="december-2020"></a>2020年12月

| テーブル名 | 元の列名 | 新しい列名 | 変更理由
|--|--|--|--|
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailAction | EmailAction | お客様のフィードバック |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicy | EmailActionPolicy | お客様のフィードバック |
| [EmailEvents](advanced-hunting-emailevents-table.md) | FinalEmailActionPolicyGuid | EmailActionPolicyGuid | お客様のフィードバック |

## <a name="related-topics"></a>関連項目
- [高度な検出の概要](advanced-hunting-overview.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)