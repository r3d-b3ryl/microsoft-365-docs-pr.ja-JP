---
title: SharePoint Online のキャパシティ プランニングとロード テスト
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: この記事では、許可されないので、従来SharePointを実行せずにオンラインに展開する方法について説明します。
ms.openlocfilehash: fb54864168b35fed290ccb1139cb6c607969820d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905226"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a><span data-ttu-id="bda5f-103">SharePoint Online のキャパシティ プランニングとロード テスト</span><span class="sxs-lookup"><span data-stu-id="bda5f-103">Capacity planning and load testing SharePoint Online</span></span>
<span data-ttu-id="bda5f-104">この記事では、従来の負荷テストを行わずに SharePoint Online に展開する方法について説明します。この方法は、オンラインでは読み込みテストがSharePointです。</span><span class="sxs-lookup"><span data-stu-id="bda5f-104">This article describes how you can deploy to SharePoint Online without traditional load testing, since load-testing is not permitted on SharePoint Online.</span></span> <span data-ttu-id="bda5f-105">SharePointオンラインはクラウド サービスであり、サービスの負荷機能、正常性、および全体的な負荷のバランスは Microsoft によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="bda5f-105">SharePoint Online is a cloud service and the load capabilities, health and overall balance of load in the service is managed by Microsoft.</span></span>
  
<span data-ttu-id="bda5f-106">サイトを起動する成功を確実にするための最善の方法は、ポータルの起動ロールアウトの計画で強調されている基本的な原則、プラクティス、推奨事項に [従う方法です](planportallaunchroll-out.md)。</span><span class="sxs-lookup"><span data-stu-id="bda5f-106">The best approach to ensuring the success of launching your site is to follow basic principles, practices and recommendations which are highlighted in the [plan your portal launch roll-out](planportallaunchroll-out.md).</span></span>

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a><span data-ttu-id="bda5f-107">オンラインで容量計画SharePoint実行する方法の概要</span><span class="sxs-lookup"><span data-stu-id="bda5f-107">Overview of how SharePoint Online performs Capacity planning</span></span> 
<span data-ttu-id="bda5f-108">オンプレミス展開に対する SharePoint Online の主な利点の 1 つは、クラウドの弾力性と、分散地域のユーザーの最適化です。</span><span class="sxs-lookup"><span data-stu-id="bda5f-108">One of the main benefits of SharePoint Online over an on-premises deployment is the elasticity of the cloud as well as optimizations for users in distributed regions.</span></span> <span data-ttu-id="bda5f-109">当社の大規模な環境は、毎日何百万人ものユーザーにサービスを提供するために設定されています。そのため、ファームのバランスを取り、拡大することで容量を効果的に処理することが重要です。</span><span class="sxs-lookup"><span data-stu-id="bda5f-109">Our large scale environment is set up to service millions of users on a daily basis, so it is important that we handle capacity effectively by balancing and expanding farms.</span></span>
  
<span data-ttu-id="bda5f-110">多くの場合、1 つのファーム内の 1 つのテナントの増加は予測できませんが、要求の集計合計は時間の間に予測可能です。</span><span class="sxs-lookup"><span data-stu-id="bda5f-110">While the growth is often unpredictable for any one tenant in any one farm, the aggregated sum of requests is predictable over time.</span></span> <span data-ttu-id="bda5f-111">オンラインの成長傾向をSharePoint、今後の拡大を計画できます。</span><span class="sxs-lookup"><span data-stu-id="bda5f-111">By identifying the growth trends in SharePoint Online, we can plan for future expansion.</span></span>
  
<span data-ttu-id="bda5f-112">容量を効率的に使用し、予期しない成長に対処するために、どのファームでも、サービスのさまざまな要素を追跡および監視するオートメーションがあります。</span><span class="sxs-lookup"><span data-stu-id="bda5f-112">In order to efficiently use capacity and deal with unexpected growth, in any farm, we have automation that tracks and monitors various elements of the service.</span></span> <span data-ttu-id="bda5f-113">複数のメトリックが使用され、主要なメトリックの 1 つが CPU 負荷になります。これは、フロントエンド サーバーをスケールアップするシグナルとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="bda5f-113">Multiple metrics are utilized, with one of the main ones being CPU load, which is used as a signal to scale-up front end servers.</span></span> <span data-ttu-id="bda5f-114">さらに、SQL 環境は負荷と時間の増加に応じて拡張され、フェーズとウェーブに従ってその負荷と成長の正しい分布が可能になりますので、段階的[/](planportallaunchroll-out.md)波のアプローチをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bda5f-114">Additionally to this we recommend a [phased / wave approach](planportallaunchroll-out.md), as SQL environments will scale according to load and growth over time, and following the phases and waves allows for the correct distribution of that load and growth.</span></span> 

<span data-ttu-id="bda5f-115">容量は、継続的にハードウェアを追加するだけでなく、有効な負荷要求にサービスを提供するためにその容量を管理および制御する方法にも関係します。</span><span class="sxs-lookup"><span data-stu-id="bda5f-115">Capacity is more than just about adding more hardware on a continuous basis but it also pertains to managing and controlling that capacity to ensure it is servicing valid load requests.</span></span> <span data-ttu-id="bda5f-116">お客様が最適なエクスペリエンスを得る方法を確認するために、推奨されるガイダンスに従ってお客様をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bda5f-116">We recommend that customers follow the recommended guidance to ensure they have the best experience.</span></span> <span data-ttu-id="bda5f-117">また、サービスで "虐待的な" 動作を許可しない調整パターンとコントロールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bda5f-117">It also means that we have throttling patterns and controls in place to ensure we do not allow "abusive" behavior in the service.</span></span> <span data-ttu-id="bda5f-118">すべての "悪い" 動作が意図的な動作ではない一方で、その動作の影響を制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bda5f-118">Whilst not all "bad" behavior is intentional, we do have to ensure that we limit the effect of that behavior.</span></span> <span data-ttu-id="bda5f-119">調整の詳細と回避方法については、「調整を回避する方法」のガイダンス記事 [を参照](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) してください。</span><span class="sxs-lookup"><span data-stu-id="bda5f-119">For further information on throttling and how to avoid it, review the [how to avoid being throttled guidance](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) article.</span></span>

## <a name="why-you-cannot-load-test-sharepoint-online"></a><span data-ttu-id="bda5f-120">オンラインでテスト を読み込SharePoint理由</span><span class="sxs-lookup"><span data-stu-id="bda5f-120">Why you cannot load test SharePoint Online</span></span>
<span data-ttu-id="bda5f-121">オンプレミス環境では、負荷テストを使用してスケールの仮定を検証し、最終的にはファームのブレークポイントを見つける。負荷で飽和状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="bda5f-121">With on-premises environments, load testing is used to validate scale assumption and ultimately find the breaking point of a farm; by saturating it with load.</span></span> 

<span data-ttu-id="bda5f-122">オンラインSharePointでは、スケールが比較的流動的で、特定のヒューリスティックに基づいて負荷を調整、制御する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bda5f-122">With SharePoint Online we need to do things differently because the scale is relatively fluid and adjusts, throttles and controls load, based on certain heuristics.</span></span> <span data-ttu-id="bda5f-123">このような大規模なマルチテナント環境なので、同じファーム内のすべてのテナントを保護する必要があります。そのため、負荷テストは自動的に調整されます。</span><span class="sxs-lookup"><span data-stu-id="bda5f-123">Being such a large scale multi-tenant environment, we must protect all tenants in the same farm, so we will automatically throttle any load tests.</span></span> <span data-ttu-id="bda5f-124">ただし、調整を行う以外に、テストを読み込もうとすると、スケールとファームのバランス調整アクションがオンオンに行われるため、今日テストしたファームは、テスト期間中またはテスト後数時間以内にスケール変更があった可能性が高いので、残念で誤解を招く可能性のある結果を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="bda5f-124">If you do however attempt to load test, besides being throttled, you will receive disappointing and potentially misleading results because the farm you tested today will probably have had scale changes during the testing window or within hours after testing, as scale and farm balancing actions are performed on an on-going basis.</span></span>

<span data-ttu-id="bda5f-125">サービスとしてテスト SharePointを読み込もうとするのではなく、推奨されるプラクティスに従い、「作成、起動、および正常なポータル ガイダンスの維持」に[従](/sharepoint/portal-health)ってください。</span><span class="sxs-lookup"><span data-stu-id="bda5f-125">Instead of trying to load test SharePoint as a service, rather focus on following the recommended practices and follow the [Creating, launching and maintaining a healthy portal](/sharepoint/portal-health) guidance.</span></span>