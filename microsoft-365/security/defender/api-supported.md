---
title: サポートされている Microsoft 365 Defender API
description: サポートされている Microsoft 365 Defender API
keywords: Microsoft 365 Defender、API、API
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.custom: api
ms.openlocfilehash: 71c4586e37f36418320c6baff456f2e9839cb1af
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482827"
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
