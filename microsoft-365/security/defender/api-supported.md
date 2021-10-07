---
title: サポートされている Microsoft 365 Defender API
description: サポートされている Microsoft 365 Defender API
keywords: Microsoft 365 Defender API、API
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
ms.openlocfilehash: c77e825fa680a038ba89a9054e04ce939dcb7941
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203917"
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
[高度な追求 API](api-advanced-hunting.md) | 高度な検索クエリを実行します。
[インシデント API](api-incident.md) | 他の実用的なタスクと共に、インシデントを一覧表示および更新します。
[ストリーミング API](streaming-api.md) | 1 つのデータ ストリームで発生するリアルタイム イベントとアラートを出荷します。

### <a name="endpoint-uris"></a>エンドポイント URI

両方のメイン API の基本 URI は次の値です https://api.security.microsoft.com 。 パフォーマンスを向上するには、位置情報に近いサーバーを使用します。

- 米国: api-us.security.microsoft.com
- ヨーロッパ: api-eu.security.microsoft.com
- 英国: api-uk.security.microsoft.com

トークンは、アクセスすることで取得できます https://api.security.microsoft.com 。

パスに沿ったすべての `/api` API は [、OData プロトコル](/odata/overview) を使用します。たとえば、 https://api.security.microsoft.com/api/incidents です。

## <a name="related-articles"></a>関連記事

- [Microsoft 365 DefenderAPI の概要](api-overview.md)
- [API にMicrosoft 365 Defenderする](api-access.md)
- [ストリーミング API](../defender-endpoint/raw-data-export.md)
- [API の制限とライセンスの詳細](api-terms.md)
- [エラー コードについて](api-error-codes.md)
