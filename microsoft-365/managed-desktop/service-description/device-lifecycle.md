---
title: Microsoft マネージド デスクトップライフサイクル
description: この記事では、デバイスの仕様を示Microsoft マネージド デスクトップ。
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a8b8abc58b82d08d004d204396cfd8e381c6303a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245314"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a><span data-ttu-id="6f5a9-104">Microsoft マネージド デスクトップライフサイクル</span><span class="sxs-lookup"><span data-stu-id="6f5a9-104">Microsoft Managed Desktop product lifecycle</span></span>

<span data-ttu-id="6f5a9-105">Microsoft マネージド デスクトップユーザーは、最高のパフォーマンス、信頼性、設計、およびセキュリティ機能 (Windows Hello などの機能のサポートなど) を提供するデバイスを常に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-105">Microsoft Managed Desktop benefits users assuring that they always use devices that offer the best performance, reliability, design, and security capabilities (such as support for features like Windows Hello).</span></span> <span data-ttu-id="6f5a9-106">これを実現するために、Microsoft マネージド デスクトップ、継続的に更新された承認済みデバイスの短いカタログが保持されます。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-106">To accomplish this, Microsoft Managed Desktop maintains a short catalog of continuously updated approved devices.</span></span> <span data-ttu-id="6f5a9-107">承認済みデバイスを表示するには、ビジネス Microsoft マネージド デスクトップサイトでWindows 10 Pro[をフィルター処理](https://www.microsoft.com/windowsforbusiness/view-all-devices)します。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-107">You can view approved devices by filtering for Microsoft Managed Desktop on the [Shop Windows 10 Pro business devices](https://www.microsoft.com/windowsforbusiness/view-all-devices) site.</span></span>
 
<span data-ttu-id="6f5a9-108">この記事では、承認済みカタログに追加および削除されるデバイスのライフサイクルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-108">This article details the lifecycle of devices as they are added and removed from the approved catalog.</span></span> 

> [!NOTE]
> <span data-ttu-id="6f5a9-109">このトピックでは、"デバイス" と "製品" を区別します。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-109">In this topic, we'll make a distinction between a "device" and a "product."</span></span> <span data-ttu-id="6f5a9-110">"デバイス" とは、1 つの個々の特定のコンピューターを意味します。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-110">By "device," we mean one individual, specific computer.</span></span> <span data-ttu-id="6f5a9-111">たとえば、「シリアル番号 1234」、"Bill's laptop"、"Shared VM XYZ" は、特定のデバイスを参照します。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-111">For example, "Serial number 1234", "Bill's laptop", "Shared VM XYZ" refer to specific devices.</span></span> <span data-ttu-id="6f5a9-112">ただし、「製品」とは、デバイスのコレクションまたはファミリを指します。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-112">A "product", however, refers to a collection or family of devices.</span></span> <span data-ttu-id="6f5a9-113">たとえば、「Fabrikam Laptop」、"Adatum ZX450 Laptop"などです。これは、製品が承認済みリストまたはカタログに追加され、デバイスが製品に登録されるMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-113">For example, "Fabrikam Laptop", "Adatum ZX450 Laptop", etc. This is important because products are added to our approved list, or catalog, and devices are what get enrolled into Microsoft Managed Desktop.</span></span>

## <a name="product-lifecycle"></a><span data-ttu-id="6f5a9-114">製品のライフサイクル</span><span class="sxs-lookup"><span data-stu-id="6f5a9-114">Product lifecycle</span></span>

 <span data-ttu-id="6f5a9-115">通常、製品は次のライフサイクル フェーズを通過します。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-115">Generally, products move through these lifecycle phases:</span></span>

- [<span data-ttu-id="6f5a9-116">製品のリリースと評価</span><span class="sxs-lookup"><span data-stu-id="6f5a9-116">Product release and evaluation</span></span>](#product-release-and-evaluation)
- [<span data-ttu-id="6f5a9-117">製品のプライマリ可用性期間</span><span class="sxs-lookup"><span data-stu-id="6f5a9-117">Product primary availability period</span></span>](#product-primary-availability-period)
- [<span data-ttu-id="6f5a9-118">製品の猶予期間</span><span class="sxs-lookup"><span data-stu-id="6f5a9-118">Product grace period</span></span>](#product-grace-period)
- [<span data-ttu-id="6f5a9-119">製品の退職</span><span class="sxs-lookup"><span data-stu-id="6f5a9-119">Product retirement</span></span>](#product-retirement)


<span data-ttu-id="6f5a9-120">次の図は、シーケンス全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-120">This illustration shows the entire sequence:</span></span>

![ライフサイクル のタイムライン: 製品の一般提供から始まる"プライマリ可用性" は 2 年間続きます。](../../media/non-dark1-edits.PNG)

<span data-ttu-id="6f5a9-126">製品はカタログに最大 24 か月間残ります<em></em>が、デバイスは個々の登録日に基づいて 3 年間管理されたままです。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-126">Products remain on the catalog for up to 24 months, but <em>devices</em> remain under management for three years based on their individual enrollment dates.</span></span> <span data-ttu-id="6f5a9-127">実質的には、各製品には 3 つの重要な日付がありますが、各デバイスには 1 つしか持てない。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-127">Effectively, each product has three important dates, but each device has only one.</span></span> <span data-ttu-id="6f5a9-128">製品の場合、これら 3 つの日付はすべて承認日<em></em>に基づいて計算されるため、これらの日付は承認時に公開されるため、製品のライフサイクル全体を常に見据え、適切に計画することができます。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-128">For products, all three of these dates are calculated based on the <em>approval date</em>, and therefore we publish these dates upon approval so that you can always look ahead and plan appropriately for the product's entire lifecycle.</span></span>

<span data-ttu-id="6f5a9-129">次の表に、理論上の製品の日付の例を示します。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-129">This table shows example dates for a theoretical product:</span></span>


|<span data-ttu-id="6f5a9-130">製品</span><span class="sxs-lookup"><span data-stu-id="6f5a9-130">Product</span></span>  |<span data-ttu-id="6f5a9-131">承認済み日付</span><span class="sxs-lookup"><span data-stu-id="6f5a9-131">Approved date</span></span>  |<span data-ttu-id="6f5a9-132">プライマリ可用性の終了</span><span class="sxs-lookup"><span data-stu-id="6f5a9-132">End of primary availability</span></span>  |<span data-ttu-id="6f5a9-133">資格の終了</span><span class="sxs-lookup"><span data-stu-id="6f5a9-133">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="6f5a9-134">Fabrikam Laptop</span><span class="sxs-lookup"><span data-stu-id="6f5a9-134">Fabrikam Laptop</span></span>    | <span data-ttu-id="6f5a9-135">1/1/2017</span><span class="sxs-lookup"><span data-stu-id="6f5a9-135">1/1/2017</span></span> | <span data-ttu-id="6f5a9-136">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="6f5a9-136">6/1/2019</span></span> | <span data-ttu-id="6f5a9-137">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="6f5a9-137">6/1/2022</span></span> |
|<span data-ttu-id="6f5a9-138">Adatum Laptop</span><span class="sxs-lookup"><span data-stu-id="6f5a9-138">Adatum Laptop</span></span>   | <span data-ttu-id="6f5a9-139">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="6f5a9-139">1/1/2018</span></span> | <span data-ttu-id="6f5a9-140">6/1/2020</span><span class="sxs-lookup"><span data-stu-id="6f5a9-140">6/1/2020</span></span> | <span data-ttu-id="6f5a9-141">6/1/2023</span><span class="sxs-lookup"><span data-stu-id="6f5a9-141">6/1/2023</span></span>  |

<span data-ttu-id="6f5a9-142">次の表に、理論デバイスの日付の例を *示します*。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-142">This table shows example dates for theoretical *devices*:</span></span>


|<span data-ttu-id="6f5a9-143">デバイス ID</span><span class="sxs-lookup"><span data-stu-id="6f5a9-143">Device ID</span></span>  |<span data-ttu-id="6f5a9-144">登録日</span><span class="sxs-lookup"><span data-stu-id="6f5a9-144">Enrollment date</span></span>  |<span data-ttu-id="6f5a9-145">退職日</span><span class="sxs-lookup"><span data-stu-id="6f5a9-145">Retirement date</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="6f5a9-146">ラップトップ #123412</span><span class="sxs-lookup"><span data-stu-id="6f5a9-146">Laptop #123412</span></span>     |  <span data-ttu-id="6f5a9-147">2/3/2018</span><span class="sxs-lookup"><span data-stu-id="6f5a9-147">2/3/2018</span></span>       |  <span data-ttu-id="6f5a9-148">2/3/2021</span><span class="sxs-lookup"><span data-stu-id="6f5a9-148">2/3/2021</span></span>       |
|<span data-ttu-id="6f5a9-149">デスクトップ #321513</span><span class="sxs-lookup"><span data-stu-id="6f5a9-149">Desktop #321513</span></span>     | <span data-ttu-id="6f5a9-150">6/2/2018</span><span class="sxs-lookup"><span data-stu-id="6f5a9-150">6/2/2018</span></span>        |  <span data-ttu-id="6f5a9-151">6/2/2021</span><span class="sxs-lookup"><span data-stu-id="6f5a9-151">6/2/2021</span></span>       |


## <a name="product-release-and-evaluation"></a><span data-ttu-id="6f5a9-152">製品のリリースと評価</span><span class="sxs-lookup"><span data-stu-id="6f5a9-152">Product release and evaluation</span></span>

<span data-ttu-id="6f5a9-153">製品ライフサイクルは、製造元が製品を一般にリリースすると開始されます。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-153">The product lifecycle starts when a manufacturer publicly releases the product:</span></span>

![リリースと評価期間を示すライフサイクル タイムライン](../../media/non-dark3-edits.PNG)

<span data-ttu-id="6f5a9-155">この段階では、Microsoft マネージド デスクトップチームが製品の評価と認定を行います。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-155">During this stage, the Microsoft Managed Desktop engineering team does their evaluation and certification of a product.</span></span> <span data-ttu-id="6f5a9-156">チームは、Windows の信頼性とパフォーマンス、ハードウェア ベースラインへの準拠、市場のセンチメント、インベントリとチャネルの準備などについて評価します。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-156">The team evaluates things like reliability and performance with Windows, compliance with a hardware baseline, market sentiment, and inventory and channel readiness, among other things.</span></span> <span data-ttu-id="6f5a9-157">通常、このプロセスには約 6 週間かかります。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-157">This process typically takes approximately six weeks.</span></span>
  
<span data-ttu-id="6f5a9-158">Microsoft マネージド デスクトップは、可用性の最初の 6 か月以内にデバイスの認定のみを評価します。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-158">Microsoft Managed Desktop will only evaluate devices for certification within their first six months of availability.</span></span> <span data-ttu-id="6f5a9-159">このポリシーにより、常に最新世代のハードウェアに注力しています。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-159">This policy ensures that we're always focusing our efforts on the latest generation of hardware.</span></span>
 
<span data-ttu-id="6f5a9-160">このフェーズの最後に、Microsoft マネージド デスクトップリストに製品を追加し、顧客[](device-list.md)登録用の製品を効果的にリリースします。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-160">At the end of this phase, Microsoft Managed Desktop adds the product to the [approved list](device-list.md), effectively releasing the product for customer enrollments.</span></span> <span data-ttu-id="6f5a9-161">デバイスが認定された日付に関係なく、承認された日付は製品の一般提供日に戻されます。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-161">Regardless of the date when a device is certified, its **approved date** is back-dated to the product's own general availability date.</span></span> 


## <a name="product-primary-availability-period"></a><span data-ttu-id="6f5a9-162">製品のプライマリ可用性期間</span><span class="sxs-lookup"><span data-stu-id="6f5a9-162">Product primary availability period</span></span>

<span data-ttu-id="6f5a9-163">この期間は、製品の可用性の中心です。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-163">This period is the core of product availability:</span></span>

![プライマリ可用性を示すライフサイクル タイムライン](../../media/non-dark4-edits.PNG)

<span data-ttu-id="6f5a9-165">この期間中に登録されたデバイスは、(青いタイムラインに示すように) Microsoft マネージド デスクトップから 3 年間のサポートを受けます。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-165">Any device enrolled during this period receives the full three years of support from Microsoft Managed Desktop (as shown by the blue timeline).</span></span> <span data-ttu-id="6f5a9-166">この期間は、一般提供日から 24 か月に設定された終了日まで続く。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-166">This period lasts until an end date set to 24 months from the general availability date.</span></span>

<span data-ttu-id="6f5a9-167">この期間を効果的に "オープン登録" と考えて、Microsoft マネージド デスクトップ の価値を最大化するには、調達モデルと選択した製品をこの期間内にターゲットに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-167">You can think of this period as effectively "open enrollment", so to maximize the value of Microsoft Managed Desktop, you should target your procurement models and selected products to fall within this period.</span></span> <span data-ttu-id="6f5a9-168">小さな例として、プライマリ可用性の最終月にある製品を使用して 2 年間のロールアウト期間に落ち着か回避する必要があります。これらのデバイスの大部分は、Microsoft マネージド デスクトップ 管理の 3 年間全体を受[](#product-grace-period)け取る予定ではありません (詳細については、猶予期間を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-168">As a small example, you should avoid settling on a two-year roll-out period using a product that is in its final month of primary availability – most of those devices will not receive the full three years of Microsoft Managed Desktop management (see [grace period](#product-grace-period) for more information).</span></span>  

## <a name="product-grace-period"></a><span data-ttu-id="6f5a9-169">製品の猶予期間</span><span class="sxs-lookup"><span data-stu-id="6f5a9-169">Product grace period</span></span>

<span data-ttu-id="6f5a9-170">製品の猶予期間は、プライマリ可用性の後の 3 年間の期間です。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-170">The product grace period is a three-year period following primary availability.</span></span> <span data-ttu-id="6f5a9-171">このフェーズでは、サポートされている製品ファミリからデバイスを登録できますが、最新のハードウェアとデバイスのパフォーマンスに関するMicrosoft マネージド デスクトップの約束をしっかりと保持できます。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-171">This phase allows you to enroll devices that are from a supported product family, but still hold firm to the promises of Microsoft Managed Desktop regarding modern hardware and device performance.</span></span> <span data-ttu-id="6f5a9-172">このフェーズは、購入の詳細を知る前に調達の決定を行ったMicrosoft マネージド デスクトップ。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-172">This phase is ideal for customers who have made procurement decisions before knowing about Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="6f5a9-173">Microsoft マネージド デスクトップ に登録する前に承認済みデバイスを最近購入した場合でも、登録できますが、3 年間の完全な管理を受け取る必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-173">If you've recently bought approved devices prior to enrolling with Microsoft Managed Desktop, you can still enroll them, but you won't receive a full three years of management.</span></span> <span data-ttu-id="6f5a9-174">代わりに、いつ登録したのかにかかわらず、退職日にコンプライアンスが満たされません。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-174">Instead, they'll fall out of compliance on the retirement date, regardless of when they were enrolled.</span></span> <span data-ttu-id="6f5a9-175">これらのデバイスは、Microsoft マネージド デスクトップ空き時間の最終日に登録された場合と同様に処理されます。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-175">Behind the scenes, Microsoft Managed Desktop will treat these devices as if they were enrolled on the last day of primary availability.</span></span> <span data-ttu-id="6f5a9-176">この図では、登録の 1 年間の違いにもかかわらず、青と緑の両方のデバイスが同じ日に終了します。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-176">In this illustration, you can see this scenario by noting that both the blue and green device end on the same day, despite their one-year difference in enrollment:</span></span>


![猶予期間を示すライフサイクル タイムライン](../../media/non-dark2-edits.PNG)

<span data-ttu-id="6f5a9-178">前の表の Fabrikam Laptop の例は、次の状況を示しています。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-178">The Fabrikam Laptop example from the previous table illustrates this situation:</span></span> 

|<span data-ttu-id="6f5a9-179">製品</span><span class="sxs-lookup"><span data-stu-id="6f5a9-179">Product</span></span>  |<span data-ttu-id="6f5a9-180">承認済み日付</span><span class="sxs-lookup"><span data-stu-id="6f5a9-180">Approved date</span></span>  |<span data-ttu-id="6f5a9-181">プライマリ可用性の終了</span><span class="sxs-lookup"><span data-stu-id="6f5a9-181">End of primary availability</span></span>  |<span data-ttu-id="6f5a9-182">資格の終了</span><span class="sxs-lookup"><span data-stu-id="6f5a9-182">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="6f5a9-183">Fabrikam Laptop</span><span class="sxs-lookup"><span data-stu-id="6f5a9-183">Fabrikam Laptop</span></span>    | <span data-ttu-id="6f5a9-184">6/1/2017</span><span class="sxs-lookup"><span data-stu-id="6f5a9-184">6/1/2017</span></span> | <span data-ttu-id="6f5a9-185">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="6f5a9-185">6/1/2019</span></span> | <span data-ttu-id="6f5a9-186">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="6f5a9-186">6/1/2022</span></span> |

<span data-ttu-id="6f5a9-187">顧客として Fabrikam Laptops は 2022 年 6 月 1 日まで登録できます。ただし、これらはすべて 2019 年 6 月 1 日に登録した場合と同じ扱いとなります。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-187">As a customer, you can enroll Fabrikam Laptops all the way until 6/1/2022 – however they will all be treated as though you enrolled them on 6/1/2019.</span></span> <span data-ttu-id="6f5a9-188">2021 年 6 月 1 日に Fabrikam Laptop を登録した場合、管理期間は 1 年のみです。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-188">If you enroll a Fabrikam Laptop on 6/1/2021, you'll only get one year of management.</span></span> <span data-ttu-id="6f5a9-189">このポリシーを使用すると、新しいデバイスを早期に調達するのではなく、以前にサポートされた製品から部分的なライフサイクルを抽出できます。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-189">This policy allows you to extract partial lifecycles from products that were previously supported, rather than having to procure new devices prematurely.</span></span> 

<span data-ttu-id="6f5a9-190">最後に、このフェーズ中にデバイスがデバイス リスト[](device-list.md)から削除され、アーカイブされたデバイス リスト[に移動されます](archived-device-list.md)。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-190">Finally, during this phase the device is removed from the [device list](device-list.md) and moved to the [archived device list](archived-device-list.md).</span></span>


## <a name="product-retirement"></a><span data-ttu-id="6f5a9-191">製品の退職</span><span class="sxs-lookup"><span data-stu-id="6f5a9-191">Product retirement</span></span>

<span data-ttu-id="6f5a9-192">製品の削除は、ライフサイクルの最終段階です。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-192">Product retirement is the final phase of the lifecycle.</span></span> <span data-ttu-id="6f5a9-193">このフェーズでは、その製品の種類の新しいデバイスは Microsoft マネージド デスクトップ に登録できません。また、定義上、すべての既存のデバイスは、許可される 3 年間の期間外になります。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-193">In this phase, no new devices of that product type can be enrolled in Microsoft Managed Desktop and, by definition, all existing devices are now outside their allowed three-year term.</span></span> <span data-ttu-id="6f5a9-194">この間、Microsoft マネージド デスクトップリストからデバイスが完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-194">During this time, Microsoft Managed Desktop will remove the device from the public list entirely.</span></span> <span data-ttu-id="6f5a9-195">また、このフェーズでは、まだ代替品を調達していない場合は、Microsoft マネージド デスクトップ がコンプライアンス外のデバイスでダウンし始めるに従って、サービスが減少し始めるのです。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-195">It's also during this phase where, if you haven't already procured replacements, you'll start to see diminished services as Microsoft Managed Desktop starts to ramp down on the devices that are out of compliance.</span></span> 

## <a name="devices-that-are-out-of-compliance"></a><span data-ttu-id="6f5a9-196">コンプライアンスが満たされているデバイス</span><span class="sxs-lookup"><span data-stu-id="6f5a9-196">Devices that are out of compliance</span></span>

<span data-ttu-id="6f5a9-197">デバイスは、管理に対して許可されているウィンドウが経過Microsoft マネージド デスクトップ準拠状態です。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-197">A device is out of compliance when its allowed window for Microsoft Managed Desktop management has elapsed.</span></span> <span data-ttu-id="6f5a9-198">この状況は、デバイスが 3 年間の管理に達した場合、または製品の種類がデバイス カタログから削除された場合に発生します。どちらが最初に発生した場合でも発生します。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-198">This situation occurs when the device has reached three years of management or when that product type is removed from the device catalog, whichever occurs first.</span></span> <span data-ttu-id="6f5a9-199">現在のデバイスがコンプライアンスから抜け出す前に、新しいデバイスを展開するなどの調達サイクルを常にターゲットに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-199">You should always target your procurement cycles such that new devices are deployed prior to current devices going out of compliance.</span></span>

<span data-ttu-id="6f5a9-200">このMicrosoft マネージド デスクトップチームは、調達サイクルが長く、長期の予算に関して計画されているのを知っています。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-200">The Microsoft Managed Desktop team knows that procurement cycles are long and planned around long-running budgets.</span></span> <span data-ttu-id="6f5a9-201">デバイスの母集団の状態を常に認識するために、管理下のすべてのデバイス、その年齢[](https://aka.ms/mmdportal)、コンプライアンスを示す状態を示す Web サイトが提供されます。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-201">To ensure that you're always aware of the state of your device population, we provide a [website](https://aka.ms/mmdportal) that lists every device under management, its age, and a status indicating its compliance.</span></span> <span data-ttu-id="6f5a9-202">この Web サイトは、デバイスの年齢に関する最新情報を常に提供するのに役立ち、任意の調達計画サイクルでレポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6f5a9-202">The website helps you always have the latest information regarding device age and can use the report in any procurement planning cycle.</span></span> 







