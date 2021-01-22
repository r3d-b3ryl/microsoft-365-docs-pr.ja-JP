---
title: Microsoft 365 Defender 高度な検索スキーマでの名前の変更
description: 高度な検索スキーマの名前付け変更テーブルと列を追跡および確認する
keywords: 高度な捜索、脅威の捜索、サイバー脅威の捜索、Microsoft Threat Protection、Microsoft 365、mtp、m365、検索、クエリ、テレメトリ、スキーマ リファレンス、kusto、テーブル、データ、名前付けの変更、名前の変更、Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 483fedd1fb152e3df5311c981b305e621ec2aec3
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932204"
---
# <a name="advanced-hunting-schema---naming-changes"></a><span data-ttu-id="14de5-104">高度な検索スキーマ - 名前の変更</span><span class="sxs-lookup"><span data-stu-id="14de5-104">Advanced hunting schema - Naming changes</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="14de5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="14de5-105">**Applies to:**</span></span>
- <span data-ttu-id="14de5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="14de5-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="14de5-107">高度 [な検索スキーマは定期的](advanced-hunting-schema-tables.md) に更新され、新しいテーブルと列が追加されます。</span><span class="sxs-lookup"><span data-stu-id="14de5-107">The [advanced hunting schema](advanced-hunting-schema-tables.md) is updated regularly to add new tables and columns.</span></span> <span data-ttu-id="14de5-108">場合によっては、既存の列名の名前が変更または置換され、ユーザー エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="14de5-108">In some cases, existing columns names are renamed or replaced to improve the user experience.</span></span> <span data-ttu-id="14de5-109">クエリに影響を与える可能性がある名前付けの変更を確認するには、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="14de5-109">Refer to this article to review naming changes that could impact your queries.</span></span>

<span data-ttu-id="14de5-110">名前付けの変更は、カスタム検出ルールで使用されるクエリを含め、セキュリティ センターに保存されるクエリに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="14de5-110">Naming changes are automatically applied to queries that are saved in the security center, including queries used by custom detection rules.</span></span> <span data-ttu-id="14de5-111">これらのクエリを手動で更新する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="14de5-111">You don't need to update these queries manually.</span></span> <span data-ttu-id="14de5-112">ただし、次のクエリを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14de5-112">However, you will need to update the following queries:</span></span>
- <span data-ttu-id="14de5-113">API を使用して実行されるクエリ</span><span class="sxs-lookup"><span data-stu-id="14de5-113">Queries that are run using the API</span></span>
- <span data-ttu-id="14de5-114">セキュリティ センターの外部の別の場所に保存されるクエリ</span><span class="sxs-lookup"><span data-stu-id="14de5-114">Queries that are saved elsewhere outside the security center</span></span>

## <a name="december-2020"></a><span data-ttu-id="14de5-115">2020年12月</span><span class="sxs-lookup"><span data-stu-id="14de5-115">December 2020</span></span>

| <span data-ttu-id="14de5-116">テーブル名</span><span class="sxs-lookup"><span data-stu-id="14de5-116">Table name</span></span> | <span data-ttu-id="14de5-117">元の列名</span><span class="sxs-lookup"><span data-stu-id="14de5-117">Original column name</span></span> | <span data-ttu-id="14de5-118">新しい列名</span><span class="sxs-lookup"><span data-stu-id="14de5-118">New column name</span></span> | <span data-ttu-id="14de5-119">変更理由</span><span class="sxs-lookup"><span data-stu-id="14de5-119">Reason for change</span></span>
|--|--|--|--|
| [<span data-ttu-id="14de5-120">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="14de5-120">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="14de5-121">FinalEmailAction</span><span class="sxs-lookup"><span data-stu-id="14de5-121">FinalEmailAction</span></span> | <span data-ttu-id="14de5-122">EmailAction</span><span class="sxs-lookup"><span data-stu-id="14de5-122">EmailAction</span></span> | <span data-ttu-id="14de5-123">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="14de5-123">Customer feedback</span></span> |
| [<span data-ttu-id="14de5-124">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="14de5-124">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="14de5-125">FinalEmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="14de5-125">FinalEmailActionPolicy</span></span> | <span data-ttu-id="14de5-126">EmailActionPolicy</span><span class="sxs-lookup"><span data-stu-id="14de5-126">EmailActionPolicy</span></span> | <span data-ttu-id="14de5-127">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="14de5-127">Customer feedback</span></span> |
| [<span data-ttu-id="14de5-128">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="14de5-128">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="14de5-129">FinalEmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="14de5-129">FinalEmailActionPolicyGuid</span></span> | <span data-ttu-id="14de5-130">EmailActionPolicyGuid</span><span class="sxs-lookup"><span data-stu-id="14de5-130">EmailActionPolicyGuid</span></span> | <span data-ttu-id="14de5-131">お客様のフィードバック</span><span class="sxs-lookup"><span data-stu-id="14de5-131">Customer feedback</span></span> |

## <a name="related-topics"></a><span data-ttu-id="14de5-132">関連項目</span><span class="sxs-lookup"><span data-stu-id="14de5-132">Related topics</span></span>
- [<span data-ttu-id="14de5-133">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="14de5-133">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="14de5-134">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="14de5-134">Understand the schema</span></span>](advanced-hunting-schema-tables.md)