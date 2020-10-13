---
title: Microsoft 365 テナントからテナントへの移行
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Microsoft 365 テナントを移行する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17aabbd945c6dec699384eb9f203029255ae62f6
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48447152"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a>Microsoft 365 テナントからテナントへの移行

既存の Microsoft 365 テナントを新しいテナントに移行することにつながる、合併、買収、divestitures、その他のシナリオには、いくつかのアーキテクチャ手法があります。 ほとんどのお客様は、Microsoft コンサルティングサービスまたは Microsoft パートナーと連携して、サードパーティ製のツールを使用してコンテンツを移行するなど、テナントを移行します。 

テナントからテナントへの [移行アーキテクチャモデル](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) を使用して、Microsoft 365 テナント間移行と移行の手順を計画する方法について理解します。

[![テナント間移行モデル](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) 

このモデルは、 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) または [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.vsdx) 形式でダウンロードして、レター、リーガル、またはタブロイド (11 x 17) サイズの用紙に印刷することもできます。

このモデルでは、次の項目を計画するためのガイダンスと出発点を示します。

- ビジネスシナリオをアーキテクチャ手法にマッピングする
- 設計上の考慮事項

このモデルには、次の詳細な例も含まれています。

- 単一イベント移行フロー
- 段階的な移行フロー
- テナント移動または分岐フロー
