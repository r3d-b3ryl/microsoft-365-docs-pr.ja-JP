---
title: サポートされている Microsoft 脅威保護 Api
description: サポートされている Microsoft 脅威保護 Api
keywords: MTP、Api、api
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
ms.openlocfilehash: 49fa182a6142748ca7769411fe74389f365ba75f
ms.sourcegitcommit: 9a275a13af3e063e80ce1bd3cd8142a095db92d2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "47650396"
---
# <a name="supported-microsoft-threat-protection-apis"></a>サポートされている Microsoft 脅威保護 Api 
**適用対象:**
- Microsoft Threat Protection

>[!IMPORTANT] 
>一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.


### <a name="end-point-uris"></a>エンドポイント Uri:

- サービスベース URI は次のとおりです。 https://api.security.microsoft.com <br>

>[!NOTE]
>パフォーマンスを向上させるには、次のようにサーバーを地域の場所に近づけることができます。
> - api-us.security.microsoft.com
> - api-eu.security.microsoft.com
> - api-uk.security.microsoft.com

 - トークンを取得するためのリソースは次のようになります。 https://api.security.microsoft.com

 - Path の下にあるすべての Api ```/api``` は OData api です。 (. ```https://api.security.microsoft.com/api/incidents```

## <a name="list-of-available-apis"></a>利用可能な Api のリスト:

トピック | 説明
:---|:---
[高度な検索 API](api-advanced-hunting.md) | API から高度な検索クエリを実行します。
[インシデント Api](api-incident.md) | インシデント関連の API 呼び出しを実行します。インシデントの一覧表示、インシデントの更新など。
