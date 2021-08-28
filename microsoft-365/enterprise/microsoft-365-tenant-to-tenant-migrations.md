---
title: Microsoft 365テナント間の移行の方法
ms.author: kvice
author: kelleyvice-msft
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
description: テナントを移行するMicrosoft 365します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5bc0c7b61c33f5de5e0896d9947419f553226d30
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58574281"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a>Microsoft 365テナント間の移行の方法

合併、買収、売却、その他のシナリオには、既存の Microsoft 365 テナントを新しいテナントに移行するためのいくつかのアーキテクチャアプローチがあります。 ほとんどのお客様は、Microsoft Consulting Services または Microsoft パートナーと一緒に、コンテンツの移行にサードパーティ製のツールを使用するなどのテナントの移行を行います。 

テナント間[移行アーキテクチャ](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)モデルを使用して、Microsoft 365 テナント間移行を計画する方法と移行の手順を理解します。

[![テナント間の移行モデル。](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) 

このモデルは PDF 形式で [ダウンロード](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) し、レター、リーガル、またはタブロイド (11 x 17) サイズの用紙に印刷します。

このモデルでは、次のセクションを計画するガイダンスと開始点を提供します。

- ビジネス シナリオとアーキテクチャアプローチのマッピング
- 設計上の考慮事項

このモデルには、次の詳細な例も含まれている。

- 単一のイベント移行フロー
- 段階的な移行フロー
- テナントの移動または分割フロー
