---
title: Microsoft 365 テナント間の移行
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
ms.openlocfilehash: 09b2bc77333afaf1991064369846241328db85ff
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461645"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="598bf-103">Microsoft 365 テナント間の移行</span><span class="sxs-lookup"><span data-stu-id="598bf-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="598bf-104">合併、買収、売却、その他のシナリオでは、既存の Microsoft 365 テナントを新しいテナントに移行するためのアーキテクチャアプローチがいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="598bf-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="598bf-105">ほとんどのお客様は、Microsoft Consulting Services または Microsoft パートナーと一緒に、コンテンツの移行にサードパーティ製のツールを使用するなどのテナントの移行を行います。</span><span class="sxs-lookup"><span data-stu-id="598bf-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="598bf-106">テナント間 [移行アーキテクチャ](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) モデルを使用して、Microsoft 365 テナント間の移行を計画する方法と移行の手順を理解します。</span><span class="sxs-lookup"><span data-stu-id="598bf-106">Use the [Tenant-to-tenant migration architecture model](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="598bf-107">[![テナント間移行モデル](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="598bf-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="598bf-108">このモデルは PDF 形式で [ダウンロード](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) し、レター、リーガル、またはタブロイド (11 x 17) サイズの用紙に印刷します。</span><span class="sxs-lookup"><span data-stu-id="598bf-108">You download this model in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="598bf-109">このモデルでは、次のセクションを計画するガイダンスと開始点を提供します。</span><span class="sxs-lookup"><span data-stu-id="598bf-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="598bf-110">ビジネス シナリオとアーキテクチャアプローチのマッピング</span><span class="sxs-lookup"><span data-stu-id="598bf-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="598bf-111">設計上の考慮事項</span><span class="sxs-lookup"><span data-stu-id="598bf-111">Design considerations</span></span>

<span data-ttu-id="598bf-112">このモデルには、次の詳細な例も含まれている。</span><span class="sxs-lookup"><span data-stu-id="598bf-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="598bf-113">単一のイベント移行フロー</span><span class="sxs-lookup"><span data-stu-id="598bf-113">A single event migration flow</span></span>
- <span data-ttu-id="598bf-114">段階的な移行フロー</span><span class="sxs-lookup"><span data-stu-id="598bf-114">A phased migration flow</span></span>
- <span data-ttu-id="598bf-115">テナントの移動または分割フロー</span><span class="sxs-lookup"><span data-stu-id="598bf-115">A tenant move or split flow</span></span>
