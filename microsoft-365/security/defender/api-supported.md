---
title: サポートされている Microsoft 365 Defender API
description: サポートされている Microsoft 365 Defender API
keywords: Microsoft 365 Defender、API、API
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.custom: api
ms.openlocfilehash: 1785186f778c489cb4a254fe39cc41921a4de86e
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2022
ms.locfileid: "62171015"
---
# <a name="supported-microsoft-365-defender-apis"></a>サポートされている Microsoft 365 Defender API 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

## <a name="list-of-available-apis"></a>使用可能な API の一覧

記事 | 説明
-|-
[高度な追求 API](api-advanced-hunting.md) | 高度なハンティング クエリを実行します。
[インシデント API](api-incident.md) | インシデントの一覧表示と更新、およびその他の実用的なタスク。
[ストリーミング API](streaming-api.md) | 1 つのデータ ストリームで発生したイベントとアラートをリアルタイムで配信します。

### <a name="endpoint-uris"></a>エンドポイント URI

メイン API の両方の基本 URI は次のとおりです https://api.security.microsoft.com。 パフォーマンスを向上させるには、位置情報に近いサーバーを使用します。

- 米国: api-us.security.microsoft.com
- ヨーロッパ: api-eu.security.microsoft.com
- 英国: api-uk.security.microsoft.com

トークンは、次 https://api.security.microsoft.comの方法で取得できます。

パスに沿った`/api`すべての API は [OData](/odata/overview) プロトコルを使用します。たとえば、 https://api.security.microsoft.com/api/incidents

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [Microsoft 365 Defender API にアクセスする](api-access.md)
- [ストリーミング API](../defender-endpoint/raw-data-export.md)
- [API の制限とライセンスについて学習する](api-terms.md)
- [エラー コードについて](api-error-codes.md)
