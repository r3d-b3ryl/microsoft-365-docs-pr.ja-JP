---
title: サポートされている Microsoft 365 Defender API
description: サポートされている Microsoft 365 Defender API
keywords: Microsoft 365Defender、API、API
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f2c66dca326589807f5712c5548c177a0d08ade0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935727"
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
[高度な追及 API](api-advanced-hunting.md) | 高度な検索クエリを実行します。
[インシデント API](api-incident.md) | 他の実用的なタスクと共に、インシデントを一覧表示および更新します。

### <a name="endpoint-uris"></a>エンドポイント URI

両方のメイン API の基本 URI は次の値です https://api.security.microsoft.com 。 パフォーマンスを向上するには、位置情報に近いサーバーを使用します。

- 米国: api-us.security.microsoft.com
- ヨーロッパ: api-eu.security.microsoft.com
- 英国: api-uk.security.microsoft.com

トークンは、アクセスすることで取得できます https://api.security.microsoft.com 。

パスに沿ったすべての `/api` API は [、OData プロトコル](/odata/overview) を使用します。たとえば、 https://api.security.microsoft.com/api/incidents です。

## <a name="related-articles"></a>関連記事

- [Microsoft 365Defender API の概要](api-overview.md)
- [Defender API Microsoft 365アクセスする](api-access.md)
- [API の制限とライセンスの詳細](api-terms.md)
- [エラー コードについて](api-error-codes.md)