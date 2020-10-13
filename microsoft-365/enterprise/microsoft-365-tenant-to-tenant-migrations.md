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
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="ca017-103">Microsoft 365 テナントからテナントへの移行</span><span class="sxs-lookup"><span data-stu-id="ca017-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="ca017-104">既存の Microsoft 365 テナントを新しいテナントに移行することにつながる、合併、買収、divestitures、その他のシナリオには、いくつかのアーキテクチャ手法があります。</span><span class="sxs-lookup"><span data-stu-id="ca017-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="ca017-105">ほとんどのお客様は、Microsoft コンサルティングサービスまたは Microsoft パートナーと連携して、サードパーティ製のツールを使用してコンテンツを移行するなど、テナントを移行します。</span><span class="sxs-lookup"><span data-stu-id="ca017-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="ca017-106">テナントからテナントへの [移行アーキテクチャモデル](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) を使用して、Microsoft 365 テナント間移行と移行の手順を計画する方法について理解します。</span><span class="sxs-lookup"><span data-stu-id="ca017-106">Use the [Tenant-to-tenant migration architecture model](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="ca017-107">[![テナント間移行モデル](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="ca017-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](../downloads/Microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="ca017-108">このモデルは、 [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) または [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.vsdx) 形式でダウンロードして、レター、リーガル、またはタブロイド (11 x 17) サイズの用紙に印刷することもできます。</span><span class="sxs-lookup"><span data-stu-id="ca017-108">You can also download this model in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) or [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.vsdx) formats and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="ca017-109">このモデルでは、次の項目を計画するためのガイダンスと出発点を示します。</span><span class="sxs-lookup"><span data-stu-id="ca017-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="ca017-110">ビジネスシナリオをアーキテクチャ手法にマッピングする</span><span class="sxs-lookup"><span data-stu-id="ca017-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="ca017-111">設計上の考慮事項</span><span class="sxs-lookup"><span data-stu-id="ca017-111">Design considerations</span></span>

<span data-ttu-id="ca017-112">このモデルには、次の詳細な例も含まれています。</span><span class="sxs-lookup"><span data-stu-id="ca017-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="ca017-113">単一イベント移行フロー</span><span class="sxs-lookup"><span data-stu-id="ca017-113">A single event migration flow</span></span>
- <span data-ttu-id="ca017-114">段階的な移行フロー</span><span class="sxs-lookup"><span data-stu-id="ca017-114">A phased migration flow</span></span>
- <span data-ttu-id="ca017-115">テナント移動または分岐フロー</span><span class="sxs-lookup"><span data-stu-id="ca017-115">A tenant move or split flow</span></span>
