---
title: Microsoft マネージド デスクトップ製品のライフサイクル
description: この記事では、Microsoft マネージド デスクトップで使用されるデバイスの仕様を示します。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 75e6c2853a0ff41efdf7d5639f675927f3b95ea4
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841201"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a><span data-ttu-id="248d3-104">Microsoft マネージド デスクトップ製品のライフサイクル</span><span class="sxs-lookup"><span data-stu-id="248d3-104">Microsoft Managed Desktop product lifecycle</span></span>

<span data-ttu-id="248d3-105">Microsoft マネージド デスクトップは、最高のパフォーマンス、信頼性、設計、セキュリティ機能 (Windows Hello などの機能のサポートなど) を提供するデバイスを常に使用するユーザーにとってメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="248d3-105">Microsoft Managed Desktop benefits users assuring that they always use devices that offer the best performance, reliability, design, and security capabilities (such as support for features like Windows Hello).</span></span> <span data-ttu-id="248d3-106">これを実現するために、Microsoft マネージド デスクトップは、継続的に更新される承認されたデバイスの短いカタログ [を保持しています](device-list.md)。</span><span class="sxs-lookup"><span data-stu-id="248d3-106">To accomplish this, Microsoft Managed Desktop maintains a short catalog of continuously updated [approved devices](device-list.md).</span></span> 
 
<span data-ttu-id="248d3-107">この記事では、承認されたカタログに対してデバイスが追加および削除される場合の、デバイスのライフサイクルについて詳しい説明します。</span><span class="sxs-lookup"><span data-stu-id="248d3-107">This article details the lifecycle of devices as they are added and removed from the approved catalog.</span></span> 

> [!NOTE]
> <span data-ttu-id="248d3-108">このトピックでは、"デバイス" と "製品" を区別します。</span><span class="sxs-lookup"><span data-stu-id="248d3-108">In this topic, we'll make a distinction between a "device" and a "product."</span></span> <span data-ttu-id="248d3-109">"デバイス" とは、1 つの個別の特定のコンピューターを意味します。</span><span class="sxs-lookup"><span data-stu-id="248d3-109">By "device," we mean one individual, specific computer.</span></span> <span data-ttu-id="248d3-110">たとえば、"Serial number 1234"、"Bill's laptop"、"Shared VM XYZ" は特定のデバイスを参照します。</span><span class="sxs-lookup"><span data-stu-id="248d3-110">For example, "Serial number 1234", "Bill's laptop", "Shared VM XYZ" refer to specific devices.</span></span> <span data-ttu-id="248d3-111">ただし、"製品" とは、デバイスのコレクションまたはファミリを指します。</span><span class="sxs-lookup"><span data-stu-id="248d3-111">A "product", however, refers to a collection or family of devices.</span></span> <span data-ttu-id="248d3-112">たとえば、"Fabrikam Laptop"、"Adatum ZX450 Laptop" などです。これは、承認済みリスト (カタログ) に[](device-list.md)製品が追加され、Microsoft マネージド デスクトップに登録されるデバイスなので重要です。</span><span class="sxs-lookup"><span data-stu-id="248d3-112">For example, "Fabrikam Laptop", "Adatum ZX450 Laptop", etc. This is important because products are added to our [approved list](device-list.md), or catalog, and devices are what get enrolled into Microsoft Managed Desktop.</span></span>

## <a name="product-lifecycle"></a><span data-ttu-id="248d3-113">製品のライフサイクル</span><span class="sxs-lookup"><span data-stu-id="248d3-113">Product lifecycle</span></span>

 <span data-ttu-id="248d3-114">一般に、製品は次のライフサイクル フェーズを通じて移行します。</span><span class="sxs-lookup"><span data-stu-id="248d3-114">Generally, products move through these lifecycle phases:</span></span>

- [<span data-ttu-id="248d3-115">製品のリリースと評価</span><span class="sxs-lookup"><span data-stu-id="248d3-115">Product release and evaluation</span></span>](#product-release-and-evaluation)
- [<span data-ttu-id="248d3-116">製品のプライマリ可用性期間</span><span class="sxs-lookup"><span data-stu-id="248d3-116">Product primary availability period</span></span>](#product-primary-availability-period)
- [<span data-ttu-id="248d3-117">製品の猶予期間</span><span class="sxs-lookup"><span data-stu-id="248d3-117">Product grace period</span></span>](#product-grace-period)
- [<span data-ttu-id="248d3-118">製品のリタイア</span><span class="sxs-lookup"><span data-stu-id="248d3-118">Product retirement</span></span>](#product-retirement)


<span data-ttu-id="248d3-119">この図は、シーケンス全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="248d3-119">This illustration shows the entire sequence:</span></span>

![ライフサイクルタイムライン: 製品の一般提供から始まる"プライマリ可用性" は 2 年間続きます。](../../media/non-dark1-edits.PNG)

<span data-ttu-id="248d3-125">製品はカタログに最大 24 か月間残ります<em></em>が、デバイスは個々の登録日に基づいて 3 年間管理されたままです。</span><span class="sxs-lookup"><span data-stu-id="248d3-125">Products remain on the catalog for up to 24 months, but <em>devices</em> remain under management for three years based on their individual enrollment dates.</span></span> <span data-ttu-id="248d3-126">事実上、各製品には 3 つの重要な日付がありますが、各デバイスには 1 つのみがあります。</span><span class="sxs-lookup"><span data-stu-id="248d3-126">Effectively, each product has three important dates, but each device has only one.</span></span> <span data-ttu-id="248d3-127">製品の場合、これら 3 つの日付はすべて承認日<em></em>に基づいて計算されるため、これらの日付は承認時に公開されるため、いつでも製品のライフサイクル全体を見て適切に計画することができます。</span><span class="sxs-lookup"><span data-stu-id="248d3-127">For products, all three of these dates are calculated based on the <em>approval date</em>, and therefore we publish these dates upon approval so that you can always look ahead and plan appropriately for the product's entire lifecycle.</span></span>

<span data-ttu-id="248d3-128">次の表に、理論上の製品の日付の例を示します。</span><span class="sxs-lookup"><span data-stu-id="248d3-128">This table shows example dates for a theoretical product:</span></span>


|<span data-ttu-id="248d3-129">製品</span><span class="sxs-lookup"><span data-stu-id="248d3-129">Product</span></span>  |<span data-ttu-id="248d3-130">承認済み日付</span><span class="sxs-lookup"><span data-stu-id="248d3-130">Approved date</span></span>  |<span data-ttu-id="248d3-131">プライマリ可用性の終了</span><span class="sxs-lookup"><span data-stu-id="248d3-131">End of primary availability</span></span>  |<span data-ttu-id="248d3-132">利用資格の終了</span><span class="sxs-lookup"><span data-stu-id="248d3-132">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="248d3-133">Fabrikam ノート PC</span><span class="sxs-lookup"><span data-stu-id="248d3-133">Fabrikam Laptop</span></span>    | <span data-ttu-id="248d3-134">1/1/2017</span><span class="sxs-lookup"><span data-stu-id="248d3-134">1/1/2017</span></span> | <span data-ttu-id="248d3-135">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="248d3-135">6/1/2019</span></span> | <span data-ttu-id="248d3-136">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="248d3-136">6/1/2022</span></span> |
|<span data-ttu-id="248d3-137">Adatum Laptop</span><span class="sxs-lookup"><span data-stu-id="248d3-137">Adatum Laptop</span></span>   | <span data-ttu-id="248d3-138">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="248d3-138">1/1/2018</span></span> | <span data-ttu-id="248d3-139">6/1/2020</span><span class="sxs-lookup"><span data-stu-id="248d3-139">6/1/2020</span></span> | <span data-ttu-id="248d3-140">6/1/2023</span><span class="sxs-lookup"><span data-stu-id="248d3-140">6/1/2023</span></span>  |

<span data-ttu-id="248d3-141">次の表に、理論上のデバイスの日付の *例を示します*。</span><span class="sxs-lookup"><span data-stu-id="248d3-141">This table shows example dates for theoretical *devices*:</span></span>


|<span data-ttu-id="248d3-142">デバイス ID</span><span class="sxs-lookup"><span data-stu-id="248d3-142">Device ID</span></span>  |<span data-ttu-id="248d3-143">登録日</span><span class="sxs-lookup"><span data-stu-id="248d3-143">Enrollment date</span></span>  |<span data-ttu-id="248d3-144">終了日</span><span class="sxs-lookup"><span data-stu-id="248d3-144">Retirement date</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="248d3-145">ノート PC #123412</span><span class="sxs-lookup"><span data-stu-id="248d3-145">Laptop #123412</span></span>     |  <span data-ttu-id="248d3-146">2/3/2018</span><span class="sxs-lookup"><span data-stu-id="248d3-146">2/3/2018</span></span>       |  <span data-ttu-id="248d3-147">2/3/2021</span><span class="sxs-lookup"><span data-stu-id="248d3-147">2/3/2021</span></span>       |
|<span data-ttu-id="248d3-148">デスクトップ #321513</span><span class="sxs-lookup"><span data-stu-id="248d3-148">Desktop #321513</span></span>     | <span data-ttu-id="248d3-149">6/2/2018</span><span class="sxs-lookup"><span data-stu-id="248d3-149">6/2/2018</span></span>        |  <span data-ttu-id="248d3-150">6/2/2021</span><span class="sxs-lookup"><span data-stu-id="248d3-150">6/2/2021</span></span>       |


## <a name="product-release-and-evaluation"></a><span data-ttu-id="248d3-151">製品のリリースと評価</span><span class="sxs-lookup"><span data-stu-id="248d3-151">Product release and evaluation</span></span>

<span data-ttu-id="248d3-152">製品ライフサイクルは、製造元が製品を一般にリリースすると開始します。</span><span class="sxs-lookup"><span data-stu-id="248d3-152">The product lifecycle starts when a manufacturer publicly releases the product:</span></span>

![リリース期間と評価期間を示すライフサイクル タイムライン](../../media/non-dark3-edits.PNG)

<span data-ttu-id="248d3-154">この段階では、Microsoft マネージド デスクトップ エンジニアリング チームが製品の評価と認定を行います。</span><span class="sxs-lookup"><span data-stu-id="248d3-154">During this stage, the Microsoft Managed Desktop engineering team does their evaluation and certification of a product.</span></span> <span data-ttu-id="248d3-155">チームは、Windows の信頼性とパフォーマンス、ハードウェアベースラインへの準拠、市場の感情、インベントリやチャネルの準備状況などの評価を行います。</span><span class="sxs-lookup"><span data-stu-id="248d3-155">The team evaluates things like reliability and performance with Windows, compliance with a hardware baseline, market sentiment, and inventory and channel readiness, among other things.</span></span> <span data-ttu-id="248d3-156">通常、このプロセスには約 6 週間かかります。</span><span class="sxs-lookup"><span data-stu-id="248d3-156">This process typically takes approximately six weeks.</span></span>
  
<span data-ttu-id="248d3-157">Microsoft マネージド デスクトップでは、最初の 6 か月以内にデバイスの認定が評価されます。</span><span class="sxs-lookup"><span data-stu-id="248d3-157">Microsoft Managed Desktop will only evaluate devices for certification within their first six months of availability.</span></span> <span data-ttu-id="248d3-158">このポリシーにより、常に最新世代のハードウェアに焦点を当て続け、取り組みを行っています。</span><span class="sxs-lookup"><span data-stu-id="248d3-158">This policy ensures that we're always focusing our efforts on the latest generation of hardware.</span></span>
 
<span data-ttu-id="248d3-159">このフェーズの最後に、Microsoft マネージド デスクトップは承認済みリストに[](device-list.md)製品を追加し、顧客登録用に製品を効果的にリリースします。</span><span class="sxs-lookup"><span data-stu-id="248d3-159">At the end of this phase, Microsoft Managed Desktop adds the product to the [approved list](device-list.md), effectively releasing the product for customer enrollments.</span></span> <span data-ttu-id="248d3-160">デバイスが認定された日付に関係なく、承認された日付は製品独自の一般提供日に日付が戻されます。</span><span class="sxs-lookup"><span data-stu-id="248d3-160">Regardless of the date when a device is certified, its **approved date** is back-dated to the product's own general availability date.</span></span> 


## <a name="product-primary-availability-period"></a><span data-ttu-id="248d3-161">製品のプライマリ可用性期間</span><span class="sxs-lookup"><span data-stu-id="248d3-161">Product primary availability period</span></span>

<span data-ttu-id="248d3-162">この期間は、製品の可用性の中核となります。</span><span class="sxs-lookup"><span data-stu-id="248d3-162">This period is the core of product availability:</span></span>

![プライマリ可用性を示すライフサイクル タイムライン](../../media/non-dark4-edits.PNG)

<span data-ttu-id="248d3-164">この期間中に登録されたデバイスは、(青いタイムラインで示すように) Microsoft マネージド デスクトップから 3 年間の完全なサポートを受けます。</span><span class="sxs-lookup"><span data-stu-id="248d3-164">Any device enrolled during this period receives the full three years of support from Microsoft Managed Desktop (as shown by the blue timeline).</span></span> <span data-ttu-id="248d3-165">この期間は、一般提供日から 24 か月に設定された終了日まで続く期間です。</span><span class="sxs-lookup"><span data-stu-id="248d3-165">This period lasts until an end date set to 24 months from the general availability date.</span></span>

<span data-ttu-id="248d3-166">この期間は、実質的に "登録を開く" と考え、Microsoft マネージド デスクトップの価値を最大限に高め、調達モデルと選択した製品をこの期間中に含めるべきです。</span><span class="sxs-lookup"><span data-stu-id="248d3-166">You can think of this period as effectively "open enrollment", so to maximize the value of Microsoft Managed Desktop, you should target your procurement models and selected products to fall within this period.</span></span> <span data-ttu-id="248d3-167">小さな例として、プライマリ可用性の最終月にある製品を使用して、2 年間のロールアウト期間を避ける必要があります。これらのデバイスの大部分は、Microsoft マネージド デスクトップ管理の完全な 3 年間を受[](#product-grace-period)け取る予定ではありません (詳細については、猶予期間を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="248d3-167">As a small example, you should avoid settling on a two-year roll-out period using a product that is in its final month of primary availability – most of those devices will not receive the full three years of Microsoft Managed Desktop management (see [grace period](#product-grace-period) for more information).</span></span>  

## <a name="product-grace-period"></a><span data-ttu-id="248d3-168">製品の猶予期間</span><span class="sxs-lookup"><span data-stu-id="248d3-168">Product grace period</span></span>

<span data-ttu-id="248d3-169">製品の猶予期間は、プライマリ可用性の 3 年間です。</span><span class="sxs-lookup"><span data-stu-id="248d3-169">The product grace period is a three-year period following primary availability.</span></span> <span data-ttu-id="248d3-170">このフェーズでは、サポートされている製品ファミリのデバイスを登録することができますが、最新のハードウェアとデバイスのパフォーマンスに関する Microsoft マネージド デスクトップの約束を引き続き果たします。</span><span class="sxs-lookup"><span data-stu-id="248d3-170">This phase allows you to enroll devices that are from a supported product family, but still hold firm to the promises of Microsoft Managed Desktop regarding modern hardware and device performance.</span></span> <span data-ttu-id="248d3-171">このフェーズは、Microsoft マネージド デスクトップについて知る前に調達の決定を行ったお客様に最適です。</span><span class="sxs-lookup"><span data-stu-id="248d3-171">This phase is ideal for customers who have made procurement decisions before knowing about Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="248d3-172">Microsoft マネージド デスクトップに登録する前に承認されたデバイスを最近購入した場合でも、デバイスを登録できますが、3 年間の完全な管理は受け取る必要はありません。</span><span class="sxs-lookup"><span data-stu-id="248d3-172">If you've recently bought approved devices prior to enrolling with Microsoft Managed Desktop, you can still enroll them, but you won't receive a full three years of management.</span></span> <span data-ttu-id="248d3-173">代わりに、いつ登録したのかにかかわらず、退職日にコンプライアンスに準拠しなきます。</span><span class="sxs-lookup"><span data-stu-id="248d3-173">Instead, they'll fall out of compliance on the retirement date, regardless of when they were enrolled.</span></span> <span data-ttu-id="248d3-174">Microsoft マネージド デスクトップでは、これらのデバイスは、プライマリ可用性の最後の日に登録されている場合と同様に処理されます。</span><span class="sxs-lookup"><span data-stu-id="248d3-174">Behind the scenes, Microsoft Managed Desktop will treat these devices as if they were enrolled on the last day of primary availability.</span></span> <span data-ttu-id="248d3-175">この図では、1 年間の登録の違いにもかかわらず、青と緑の両方のデバイスが同じ日に終了する点に注意することで、このシナリオを確認できます。</span><span class="sxs-lookup"><span data-stu-id="248d3-175">In this illustration, you can see this scenario by noting that both the blue and green device end on the same day, despite their one-year difference in enrollment:</span></span>


![猶予期間を示すライフサイクル タイムライン](../../media/non-dark2-edits.PNG)

<span data-ttu-id="248d3-177">前の表の Fabrikam ラップトップの例は、この状況を示しています。</span><span class="sxs-lookup"><span data-stu-id="248d3-177">The Fabrikam Laptop example from the previous table illustrates this situation:</span></span> 

|<span data-ttu-id="248d3-178">製品</span><span class="sxs-lookup"><span data-stu-id="248d3-178">Product</span></span>  |<span data-ttu-id="248d3-179">承認済み日付</span><span class="sxs-lookup"><span data-stu-id="248d3-179">Approved date</span></span>  |<span data-ttu-id="248d3-180">プライマリ可用性の終了</span><span class="sxs-lookup"><span data-stu-id="248d3-180">End of primary availability</span></span>  |<span data-ttu-id="248d3-181">利用資格の終了</span><span class="sxs-lookup"><span data-stu-id="248d3-181">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="248d3-182">Fabrikam ノート PC</span><span class="sxs-lookup"><span data-stu-id="248d3-182">Fabrikam Laptop</span></span>    | <span data-ttu-id="248d3-183">6/1/2017</span><span class="sxs-lookup"><span data-stu-id="248d3-183">6/1/2017</span></span> | <span data-ttu-id="248d3-184">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="248d3-184">6/1/2019</span></span> | <span data-ttu-id="248d3-185">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="248d3-185">6/1/2022</span></span> |

<span data-ttu-id="248d3-186">お客様は、2022 年 6 月 1 日まで Fabrikam Laptops を登録できます。ただし、これらはすべて 2019 年 6 月 1 日に登録した場合と同様に処理されます。</span><span class="sxs-lookup"><span data-stu-id="248d3-186">As a customer, you can enroll Fabrikam Laptops all the way until 6/1/2022 – however they will all be treated as though you enrolled them on 6/1/2019.</span></span> <span data-ttu-id="248d3-187">2021 年 6 月 1 日に Fabrikam ノート PC を登録した場合は、1 年間の管理しか受け取れなのみです。</span><span class="sxs-lookup"><span data-stu-id="248d3-187">If you enroll a Fabrikam Laptop on 6/1/2021, you'll only get one year of management.</span></span> <span data-ttu-id="248d3-188">このポリシーを使用すると、新しいデバイスを途中で調達する必要がなのではなく、以前にサポートされた製品から部分的なライフサイクルを抽出できます。</span><span class="sxs-lookup"><span data-stu-id="248d3-188">This policy allows you to extract partial lifecycles from products that were previously supported, rather than having to procure new devices prematurely.</span></span> 

<span data-ttu-id="248d3-189">最後に、このフェーズでは、デバイスがデバイス一覧[](device-list.md)から削除され、アーカイブされたデバイスの一覧[に移動されます](archived-device-list.md)。</span><span class="sxs-lookup"><span data-stu-id="248d3-189">Finally, during this phase the device is removed from the [device list](device-list.md) and moved to the [archived device list](archived-device-list.md).</span></span>


## <a name="product-retirement"></a><span data-ttu-id="248d3-190">製品のリタイア</span><span class="sxs-lookup"><span data-stu-id="248d3-190">Product retirement</span></span>

<span data-ttu-id="248d3-191">製品のサポートは、ライフサイクルの最終フェーズです。</span><span class="sxs-lookup"><span data-stu-id="248d3-191">Product retirement is the final phase of the lifecycle.</span></span> <span data-ttu-id="248d3-192">このフェーズでは、その製品の種類の新しいデバイスを Microsoft マネージド デスクトップに登録できません。定義上、すべての既存のデバイスは、許可される 3 年間の期間を外しています。</span><span class="sxs-lookup"><span data-stu-id="248d3-192">In this phase, no new devices of that product type can be enrolled in Microsoft Managed Desktop and, by definition, all existing devices are now outside their allowed three-year term.</span></span> <span data-ttu-id="248d3-193">この間、Microsoft マネージド デスクトップはパブリック リストからデバイスを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="248d3-193">During this time, Microsoft Managed Desktop will remove the device from the public list entirely.</span></span> <span data-ttu-id="248d3-194">また、このフェーズでは、まだ代替製品を調達していない場合、Microsoft マネージド デスクトップがコンプライアンスに準拠していないデバイスでダウンし始める際に、サービスの低下が発生します。</span><span class="sxs-lookup"><span data-stu-id="248d3-194">It's also during this phase where, if you haven't already procured replacements, you'll start to see diminished services as Microsoft Managed Desktop starts to ramp down on the devices that are out of compliance.</span></span> 

## <a name="devices-that-are-out-of-compliance"></a><span data-ttu-id="248d3-195">コンプライアンスに準拠しなきデバイス</span><span class="sxs-lookup"><span data-stu-id="248d3-195">Devices that are out of compliance</span></span>

<span data-ttu-id="248d3-196">Microsoft マネージド デスクトップ管理の許可されたウィンドウが経過すると、デバイスが準拠しなきます。</span><span class="sxs-lookup"><span data-stu-id="248d3-196">A device is out of compliance when its allowed window for Microsoft Managed Desktop management has elapsed.</span></span> <span data-ttu-id="248d3-197">この状況は、デバイスが 3 年間の管理に達した場合、またはデバイス カタログからその製品の種類が削除された場合に発生します。どちらが最初に発生した場合でも発生します。</span><span class="sxs-lookup"><span data-stu-id="248d3-197">This situation occurs when the device has reached three years of management or when that product type is removed from the device catalog, whichever occurs first.</span></span> <span data-ttu-id="248d3-198">現在のデバイスが準拠しなくる前に新しいデバイスを展開する前に、調達サイクルを常にターゲットに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="248d3-198">You should always target your procurement cycles such that new devices are deployed prior to current devices going out of compliance.</span></span>

<span data-ttu-id="248d3-199">Microsoft マネージド デスクトップ チームは、調達サイクルが長く、長時間の予算に関して計画されている状態を知っています。</span><span class="sxs-lookup"><span data-stu-id="248d3-199">The Microsoft Managed Desktop team knows that procurement cycles are long and planned around long-running budgets.</span></span> <span data-ttu-id="248d3-200">デバイスの母集団の状態を常に認識するために、管理対象のすべてのデバイス、その年齢[](https://aka.ms/mmdportal)、コンプライアンスを示す状態を一覧表示する Web サイトが提供されます。</span><span class="sxs-lookup"><span data-stu-id="248d3-200">To ensure that you're always aware of the state of your device population, we provide a [website](https://aka.ms/mmdportal) that lists every device under management, its age, and a status indicating its compliance.</span></span> <span data-ttu-id="248d3-201">この Web サイトは、デバイスの年齢に関する最新情報を常に取得するのに役立ち、調達計画サイクルでレポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="248d3-201">The website helps you always have the latest information regarding device age and can use the report in any procurement planning cycle.</span></span> 







