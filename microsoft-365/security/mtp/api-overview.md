---
title: Microsoft 365 Defender Api の概要
description: Microsoft 365 Defender で利用可能な Api について説明します。
keywords: api、api、概要、インシデント、インシデント、脅威を探す
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
ms.openlocfilehash: 75a5853e7128667420819c84fbc3c50b07d669b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845014"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="4edf9-104">Microsoft 365 Defender Api の概要</span><span class="sxs-lookup"><span data-stu-id="4edf9-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4edf9-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4edf9-105">**Applies to:**</span></span>
- <span data-ttu-id="4edf9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4edf9-106">Microsoft 365 Defender</span></span>


>[!IMPORTANT] 
><span data-ttu-id="4edf9-107">一部の情報は、市販される前に大幅に変更される可能性がある prereleased 製品に関連しています。</span><span class="sxs-lookup"><span data-stu-id="4edf9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="4edf9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="4edf9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="4edf9-109">Microsoft 365 Defender ソリューションは、統合対応のプラットフォームの上に構築されています。</span><span class="sxs-lookup"><span data-stu-id="4edf9-109">Microsoft 365 Defender solution is built on top of an integration-ready platform.</span></span> 

<span data-ttu-id="4edf9-110">Lop レベルの Microsoft 365 Defender Api を使用すると、共有インシデントと高度な検索テーブルに基づいてワークフローを自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="4edf9-110">The lop-level Microsoft 365 Defender APIs will enable you to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="4edf9-111">**インシデントキューの組み合わせ** -セキュリティ担当者にとって重要なことが重視されます。</span><span class="sxs-lookup"><span data-stu-id="4edf9-111">**Combined incidents queue** - Helps security professionals focus on what's critical.</span></span> <span data-ttu-id="4edf9-112">完全な攻撃の範囲と影響を受けるアセットがグループ化され、インシデント API の下で適時に表面化されるようにするために役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="4edf9-112">Helps to ensure that the full attack scope and impacted assets are grouped together and surfaced in a timely manner under the incident API.</span></span>

- <span data-ttu-id="4edf9-113">**クロス積脅威** 検索-セキュリティチームは、さまざまな保護製品によって収集された未加工のデータを使用して独自のカスタムクエリを作成することによって、侵害の兆候を探すことができます。</span><span class="sxs-lookup"><span data-stu-id="4edf9-113">**Cross-product threat hunting** - Security teams can leverage their unique organizational knowledge to hunt for signs of compromise by creating their own custom queries via APIs over the raw data collected by the various protection products.</span></span> 

<span data-ttu-id="4edf9-114">これらの Api セットに加えて、さまざまな保護製品は、各製品の機能に基づいて改革するために役立つ追加の Api を公開しています。</span><span class="sxs-lookup"><span data-stu-id="4edf9-114">In addition to these set of APIs, each of the various protection products expose additional APIs to help you innovate based on each product capability.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4edf9-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="4edf9-115">Related topics</span></span>
- [<span data-ttu-id="4edf9-116">Microsoft の脅威保護 Api にアクセスする</span><span class="sxs-lookup"><span data-stu-id="4edf9-116">Access the Microsoft Threat Protection APIs</span></span>](api-access.md)
- [<span data-ttu-id="4edf9-117">その他の API リソース</span><span class="sxs-lookup"><span data-stu-id="4edf9-117">Other API resources</span></span>](api-articles.md)
