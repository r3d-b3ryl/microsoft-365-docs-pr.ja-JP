---
title: サポートされている Microsoft 365 Defender API
description: サポートされている Microsoft 365 Defender API
keywords: MTP、API、api
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: dbb7613dae3755b0fb794a3d68b5b424d765cc62
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719324"
---
# <a name="supported-microsoft-365-defender-apis"></a>サポートされている Microsoft 365 Defender API 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**
- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="list-of-available-apis"></a>使用可能な API の一覧

記事 | 説明
-|-
[高度な追及 API](api-advanced-hunting.md) | 高度な検索クエリを実行します。
[インシデント API](api-incident.md) | インシデントのリストと更新、および他の実用的なタスク。

### <a name="endpoint-uris"></a>エンドポイント URI

両方のメイン API のベース URI は次の値です https://api.security.microsoft.com 。 パフォーマンスを向上するには、位置情報に近いサーバーを使用します。

- 米国: api-us.security.microsoft.com
- ヨーロッパ: api-eu.security.microsoft.com
- 英国: api-uk.security.microsoft.com

トークンは、アクセスすることで取得できます https://api.security.microsoft.com 。

パス上のすべての API `/api` は [、OData](https://docs.microsoft.com/odata/overview) プロトコルを使用します。たとえば https://api.security.microsoft.com/api/incidents 、 .

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [Microsoft Threat Protection API へのアクセス](api-access.md)
- [API の制限とライセンスについて](api-terms.md)
- [エラー コードを理解する](api-error-codes.md)
