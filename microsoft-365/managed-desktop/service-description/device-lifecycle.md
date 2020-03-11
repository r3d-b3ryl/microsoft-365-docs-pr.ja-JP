---
title: Microsoft マネージドデスクトップ製品のライフサイクル
description: このトピックでは、Microsoft マネージドデスクトップで使用されるデバイスの仕様を示します。
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: b65724a1eee35149d473fb69ff646b5ef5751b2c
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583174"
---
# <a name="microsoft-managed-desktop-product-lifecycle"></a><span data-ttu-id="7266d-104">Microsoft マネージドデスクトップ製品のライフサイクル</span><span class="sxs-lookup"><span data-stu-id="7266d-104">Microsoft Managed Desktop product lifecycle</span></span>

<span data-ttu-id="7266d-105">Microsoft マネージドデスクトップでは、エンドユーザーが、最高のパフォーマンス、信頼性、設計、およびセキュリティ機能 (Windows Hello のような機能のサポートなど) を提供するデバイスを常に使用していることが保証されます。</span><span class="sxs-lookup"><span data-stu-id="7266d-105">Microsoft Managed Desktop benefits end users assuring that they always use devices that offer the best performance, reliability, design, and security capabilities (such as support for features like Windows Hello).</span></span> <span data-ttu-id="7266d-106">これを実現するために、Microsoft マネージドデスクトップは、継続的に更新される[承認済みデバイス](device-list.md)の短いカタログを保持します。</span><span class="sxs-lookup"><span data-stu-id="7266d-106">To accomplish this, Microsoft Managed Desktop maintains a short catalog of continuously updated [approved devices](device-list.md).</span></span> 
 
<span data-ttu-id="7266d-107">このトピックでは、承認済みカタログに追加または削除されたデバイスのライフサイクルについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7266d-107">This topic details the lifecycle of devices as they are added and removed from the approved catalog.</span></span> 

> [!NOTE]
> <span data-ttu-id="7266d-108">このトピックでは、"デバイス" と "product" を区別します。</span><span class="sxs-lookup"><span data-stu-id="7266d-108">In this topic, we'll make a distinction between a "device" and a "product."</span></span> <span data-ttu-id="7266d-109">"デバイス" によって、1つの個別の特定のコンピューターを意味します。</span><span class="sxs-lookup"><span data-stu-id="7266d-109">By "device," we mean one individual, specific computer.</span></span> <span data-ttu-id="7266d-110">たとえば、"Serial number 1234"、"Bill's pc"、"Shared VM XYZ" は、特定のデバイスを参照します。</span><span class="sxs-lookup"><span data-stu-id="7266d-110">For example, "Serial number 1234", "Bill's laptop", "Shared VM XYZ" refer to specific devices.</span></span> <span data-ttu-id="7266d-111">ただし、"product" は、デバイスのコレクションまたはファミリを指します。</span><span class="sxs-lookup"><span data-stu-id="7266d-111">A "product", however, refers to a collection or family of devices.</span></span> <span data-ttu-id="7266d-112">たとえば、"Fabrikam ラップトップ"、"Adatum ZX450 ラップトップ" などです。これは、製品を[承認済みリスト](device-list.md)、またはカタログに追加し、デバイスが Microsoft マネージドデスクトップに登録されるものであるため、重要です。</span><span class="sxs-lookup"><span data-stu-id="7266d-112">For example, "Fabrikam Laptop", "Adatum ZX450 Laptop", etc. This is important because products are added to our [approved list](device-list.md), or catalog, and devices are what get enrolled into Microsoft Managed Desktop.</span></span>

## <a name="product-lifecycle"></a><span data-ttu-id="7266d-113">製品のライフサイクル</span><span class="sxs-lookup"><span data-stu-id="7266d-113">Product lifecycle</span></span>

 <span data-ttu-id="7266d-114">一般に、製品は次のライフサイクルフェーズを経て移動します。</span><span class="sxs-lookup"><span data-stu-id="7266d-114">Generally, products move through these lifecycle phases:</span></span>

- [<span data-ttu-id="7266d-115">製品のリリースと評価</span><span class="sxs-lookup"><span data-stu-id="7266d-115">Product release and evaluation</span></span>](#product-release-and-evaluation)
- [<span data-ttu-id="7266d-116">製品の主な利用可能期間</span><span class="sxs-lookup"><span data-stu-id="7266d-116">Product primary availability period</span></span>](#product-primary-availability-period)
- [<span data-ttu-id="7266d-117">製品の猶予期間</span><span class="sxs-lookup"><span data-stu-id="7266d-117">Product grace period</span></span>](#product-grace-period)
- [<span data-ttu-id="7266d-118">製品の定年</span><span class="sxs-lookup"><span data-stu-id="7266d-118">Product retirement</span></span>](#product-retirement)


<span data-ttu-id="7266d-119">次の図は、シーケンス全体を示しています。</span><span class="sxs-lookup"><span data-stu-id="7266d-119">This illustration shows the entire sequence:</span></span>

![ライフサイクルのタイムライン: 製品の一般提供開始から、"プライマリ可用性" は2年間続きます。](../../media/non-dark1-edits.PNG)

<span data-ttu-id="7266d-125">製品は最大24か月間カタログに保持されますが、<em>デバイス</em>はそれぞれの登録日に基づいて3年間管理されたままになります。</span><span class="sxs-lookup"><span data-stu-id="7266d-125">Products remain on the catalog for up to 24 months, but <em>devices</em> remain under management for 3 years based on their individual enrollment dates.</span></span> <span data-ttu-id="7266d-126">実質的に、各製品には3つの重要な日付がありますが、各デバイスには1つしかありません。</span><span class="sxs-lookup"><span data-stu-id="7266d-126">Effectively, each product has three important dates, but each device has only one.</span></span> <span data-ttu-id="7266d-127">製品については、これらの3つの日付すべてが<em>承認日</em>に基づいて計算されるため、これらの日付を承認時に公開するので、常に製品のライフサイクル全体に対して適切に検討し、計画することができます。</span><span class="sxs-lookup"><span data-stu-id="7266d-127">For products, all three of these dates are calculated based on the <em>approval date</em>, and therefore we publish these dates upon approval so that you can always look ahead and plan appropriately for the product's entire lifecycle.</span></span>

<span data-ttu-id="7266d-128">次の表に、理論上の製品の日付の例を示します。</span><span class="sxs-lookup"><span data-stu-id="7266d-128">This table shows example dates for a theoretical product:</span></span>


|<span data-ttu-id="7266d-129">製品</span><span class="sxs-lookup"><span data-stu-id="7266d-129">Product</span></span>  |<span data-ttu-id="7266d-130">承認日</span><span class="sxs-lookup"><span data-stu-id="7266d-130">Approved date</span></span>  |<span data-ttu-id="7266d-131">プライマリ可用性の終了</span><span class="sxs-lookup"><span data-stu-id="7266d-131">End of primary availability</span></span>  |<span data-ttu-id="7266d-132">適格性の終了</span><span class="sxs-lookup"><span data-stu-id="7266d-132">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="7266d-133">Fabrikam のラップトップ</span><span class="sxs-lookup"><span data-stu-id="7266d-133">Fabrikam Laptop</span></span>    | <span data-ttu-id="7266d-134">1/1/2017</span><span class="sxs-lookup"><span data-stu-id="7266d-134">1/1/2017</span></span> | <span data-ttu-id="7266d-135">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="7266d-135">6/1/2019</span></span> | <span data-ttu-id="7266d-136">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="7266d-136">6/1/2022</span></span> |
|<span data-ttu-id="7266d-137">Adatum ラップトップ</span><span class="sxs-lookup"><span data-stu-id="7266d-137">Adatum Laptop</span></span>   | <span data-ttu-id="7266d-138">1/1/2018</span><span class="sxs-lookup"><span data-stu-id="7266d-138">1/1/2018</span></span> | <span data-ttu-id="7266d-139">6/1/2020</span><span class="sxs-lookup"><span data-stu-id="7266d-139">6/1/2020</span></span> | <span data-ttu-id="7266d-140">6/1/2023</span><span class="sxs-lookup"><span data-stu-id="7266d-140">6/1/2023</span></span>  |

<span data-ttu-id="7266d-141">次の表に、理論的な*デバイス*の日付の例を示します。</span><span class="sxs-lookup"><span data-stu-id="7266d-141">This table shows example dates for theoretical *devices*:</span></span>


|<span data-ttu-id="7266d-142">デバイス ID</span><span class="sxs-lookup"><span data-stu-id="7266d-142">Device ID</span></span>  |<span data-ttu-id="7266d-143">登録日</span><span class="sxs-lookup"><span data-stu-id="7266d-143">Enrollment date</span></span>  |<span data-ttu-id="7266d-144">定年後の日付</span><span class="sxs-lookup"><span data-stu-id="7266d-144">Retirement date</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="7266d-145">ラップトップ #123412</span><span class="sxs-lookup"><span data-stu-id="7266d-145">Laptop #123412</span></span>     |  <span data-ttu-id="7266d-146">2/3/2018</span><span class="sxs-lookup"><span data-stu-id="7266d-146">2/3/2018</span></span>       |  <span data-ttu-id="7266d-147">2/3/2021</span><span class="sxs-lookup"><span data-stu-id="7266d-147">2/3/2021</span></span>       |
|<span data-ttu-id="7266d-148">デスクトップ #321513</span><span class="sxs-lookup"><span data-stu-id="7266d-148">Desktop #321513</span></span>     | <span data-ttu-id="7266d-149">6/2/2018</span><span class="sxs-lookup"><span data-stu-id="7266d-149">6/2/2018</span></span>        |  <span data-ttu-id="7266d-150">6/2/2021</span><span class="sxs-lookup"><span data-stu-id="7266d-150">6/2/2021</span></span>       |


## <a name="product-release-and-evaluation"></a><span data-ttu-id="7266d-151">製品のリリースと評価</span><span class="sxs-lookup"><span data-stu-id="7266d-151">Product release and evaluation</span></span>

<span data-ttu-id="7266d-152">製品ライフサイクルは、製造元が一般に製品をリリースした時点で開始されます。</span><span class="sxs-lookup"><span data-stu-id="7266d-152">The product lifecycle starts when a manufacturer publicly releases the product:</span></span>

![リリースと評価期間を示すライフサイクルタイムライン](../../media/non-dark3-edits.PNG)

<span data-ttu-id="7266d-154">この段階では、Microsoft マネージドデスクトップエンジニアリングチームが製品の評価と証明書を行います。</span><span class="sxs-lookup"><span data-stu-id="7266d-154">During this stage, the Microsoft Managed Desktop engineering team does their evaluation and certification of a product.</span></span> <span data-ttu-id="7266d-155">このチームは、Windows との信頼性とパフォーマンス、ハードウェアベースライン、市場心理、およびチャネルの準備状況などを評価します。</span><span class="sxs-lookup"><span data-stu-id="7266d-155">The team evaluates things like reliability and performance with Windows, compliance with a hardware baseline, market sentiment, and inventory and channel readiness, among other things.</span></span> <span data-ttu-id="7266d-156">通常、このプロセスには約6週間かかります。</span><span class="sxs-lookup"><span data-stu-id="7266d-156">This process typically takes approximately 6 weeks.</span></span>
  
<span data-ttu-id="7266d-157">Microsoft マネージドデスクトップでは、最初の6か月間の可用性の範囲内で、認定されたデバイスのみを評価します。</span><span class="sxs-lookup"><span data-stu-id="7266d-157">Microsoft Managed Desktop will only evaluate devices for certification within their first 6 months of availability.</span></span> <span data-ttu-id="7266d-158">これにより、お客様は常に最新のハードウェアの世代に注目しています。</span><span class="sxs-lookup"><span data-stu-id="7266d-158">This ensures that we're always focusing our efforts on the latest generation of hardware.</span></span>
 
<span data-ttu-id="7266d-159">このフェーズの最後に、Microsoft Managed Desktop が製品を[承認済みリスト](device-list.md)に追加し、顧客が登録されている製品を効果的にリリースします。</span><span class="sxs-lookup"><span data-stu-id="7266d-159">At the end of this phase, Microsoft Managed Desktop adds the product to the [approved list](device-list.md), effectively releasing the product for customer enrollments.</span></span> <span data-ttu-id="7266d-160">デバイスが認定されている日付に関係なく、承認された**日付**は製品固有の一般的な利用可能日の日付になります。</span><span class="sxs-lookup"><span data-stu-id="7266d-160">Regardless of the date when a device is certified, its **approved date** is back-dated to the product's own general availability date.</span></span> 


## <a name="product-primary-availability-period"></a><span data-ttu-id="7266d-161">製品の主な利用可能期間</span><span class="sxs-lookup"><span data-stu-id="7266d-161">Product primary availability period</span></span>

<span data-ttu-id="7266d-162">この期間は、製品の可用性の中核となります。</span><span class="sxs-lookup"><span data-stu-id="7266d-162">This period is the core of product availability:</span></span>

![プライマリの可用性を示すライフサイクルタイムライン](../../media/non-dark4-edits.PNG)

<span data-ttu-id="7266d-164">この期間中に登録されたすべてのデバイスは、Microsoft マネージドデスクトップからの最高3年間のサポートを受けます (青いタイムラインに表示されます)。</span><span class="sxs-lookup"><span data-stu-id="7266d-164">Any device enrolled during this period receives the full three years of support from Microsoft Managed Desktop (as shown by the blue timeline).</span></span> <span data-ttu-id="7266d-165">この期間は、終了日が通常の利用可能日から24か月に設定されるまで続きます。</span><span class="sxs-lookup"><span data-stu-id="7266d-165">This period lasts until an end date set to 24 months from the general availability date.</span></span>

<span data-ttu-id="7266d-166">この期間は効率的に "登録を開く" と考えることができます。そのため、Microsoft マネージドデスクトップの価値を最大にするために、調達モデルと選択した製品をこの期間内に収まるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7266d-166">You can think of this period as effectively "open enrollment", so to maximize the value of Microsoft Managed Desktop, you should target your procurement models and selected products to fall within this period.</span></span> <span data-ttu-id="7266d-167">簡単な例として、お客様が2年間の製品を使用して、第1の主要な可用性を実現しないようにする必要があります。これらのデバイスのほとんどは、Microsoft の管理されたデスクトップ管理 (「[猶予期間](#product-grace-period)」を参照してください) の全3年間を受け取ることはありません。</span><span class="sxs-lookup"><span data-stu-id="7266d-167">As a small example, a customer should avoid settling on a two-year roll-out period using a product that is in its final month of primary availability – most of those devices will not receive the full three years of Microsoft Managed Desktop management (see [grace period](#product-grace-period) for more information).</span></span>  

## <a name="product-grace-period"></a><span data-ttu-id="7266d-168">製品の猶予期間</span><span class="sxs-lookup"><span data-stu-id="7266d-168">Product grace period</span></span>

<span data-ttu-id="7266d-169">製品の猶予期間は、主な可用性に続く3年間の期間です。</span><span class="sxs-lookup"><span data-stu-id="7266d-169">The product grace period is a three-year period following primary availability.</span></span> <span data-ttu-id="7266d-170">このフェーズでは、サポートされている製品ファミリからのデバイスを登録することができますが、最新のハードウェアとデバイスのパフォーマンスに関しては、Microsoft マネージドデスクトップの約束に対して会社を引き続き保持しています。</span><span class="sxs-lookup"><span data-stu-id="7266d-170">This phase allows you to enroll devices that are from a supported product family, but still hold firm to the promises of Microsoft Managed Desktop regarding modern hardware and device performance.</span></span> <span data-ttu-id="7266d-171">このフェーズは、Microsoft マネージドデスクトップについて理解する前に、調達に関する決定を下したお客様に最適です。</span><span class="sxs-lookup"><span data-stu-id="7266d-171">This phase is ideal for customers who have made procurement decisions before knowing about Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="7266d-172">Microsoft マネージドデスクトップに登録する前に、承認済みデバイスを最近購入したことがある場合は、登録を行うことはできますが、3年間の管理が必要になることはありません。</span><span class="sxs-lookup"><span data-stu-id="7266d-172">If you've recently bought a number of approved devices prior to enrolling with Microsoft Managed Desktop, you can still enroll them, but you won't receive a full three years of management.</span></span> <span data-ttu-id="7266d-173">その代わりに、登録されている時期に関係なく、定年後の日付に準拠しなくなります。</span><span class="sxs-lookup"><span data-stu-id="7266d-173">Instead, they'll fall out of compliance on the retirement date, regardless of when they were enrolled.</span></span> <span data-ttu-id="7266d-174">バックグラウンドでは、Microsoft Managed Desktop は、これらのデバイスがプライマリ可用性の最終日に登録されたものとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="7266d-174">Behind the scenes, Microsoft Managed Desktop will treat these devices as if they were enrolled on the last day of primary availability.</span></span> <span data-ttu-id="7266d-175">この図では、次のようなシナリオを示しています。これは、同日に青と緑の両方のデバイスが、登録の1年間の違いにかかわらず、同じ日に終了することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7266d-175">In this illustration, you can see this scenario by noting that both the blue and green device end on the same day, despite their one-year difference in enrollment:</span></span>


![猶予期間を示すライフサイクルタイムライン](../../media/non-dark2-edits.PNG)

<span data-ttu-id="7266d-177">前の表の Fabrikam のラップトップの例は、このような状況を示しています。</span><span class="sxs-lookup"><span data-stu-id="7266d-177">The Fabrikam Laptop example from the previous table illustrates this situation:</span></span> 

|<span data-ttu-id="7266d-178">製品</span><span class="sxs-lookup"><span data-stu-id="7266d-178">Product</span></span>  |<span data-ttu-id="7266d-179">承認日</span><span class="sxs-lookup"><span data-stu-id="7266d-179">Approved date</span></span>  |<span data-ttu-id="7266d-180">プライマリ可用性の終了</span><span class="sxs-lookup"><span data-stu-id="7266d-180">End of primary availability</span></span>  |<span data-ttu-id="7266d-181">適格性の終了</span><span class="sxs-lookup"><span data-stu-id="7266d-181">End of eligibility</span></span>  |
|---------|---------|---------|---------|
|<span data-ttu-id="7266d-182">Fabrikam のラップトップ</span><span class="sxs-lookup"><span data-stu-id="7266d-182">Fabrikam Laptop</span></span>    | <span data-ttu-id="7266d-183">6/1/2017</span><span class="sxs-lookup"><span data-stu-id="7266d-183">6/1/2017</span></span> | <span data-ttu-id="7266d-184">6/1/2019</span><span class="sxs-lookup"><span data-stu-id="7266d-184">6/1/2019</span></span> | <span data-ttu-id="7266d-185">6/1/2022</span><span class="sxs-lookup"><span data-stu-id="7266d-185">6/1/2022</span></span> |

<span data-ttu-id="7266d-186">お客様は、6/1/2022 までのすべての方法で Fabrikam のラップトップを登録することができます。ただし、6/1/2019 に登録した場合と同様に処理されます。</span><span class="sxs-lookup"><span data-stu-id="7266d-186">As a customer, you can enroll Fabrikam Laptops all the way until 6/1/2022 – however they will all be treated as though you enrolled them on 6/1/2019.</span></span> <span data-ttu-id="7266d-187">6/1/2021 で Fabrikam のラップトップを登録すると、1年分の管理しか得られません。</span><span class="sxs-lookup"><span data-stu-id="7266d-187">If you enroll a Fabrikam Laptop on 6/1/2021 you'll only get one year of management.</span></span> <span data-ttu-id="7266d-188">このポリシーを使用すると、新しいデバイスを事前に購入しなくても、以前にサポートされていた製品から部分的なライフサイクルを抽出することができます。</span><span class="sxs-lookup"><span data-stu-id="7266d-188">This policy allows you to extract partial lifecycles from products that were previously supported, rather than having to procure new devices prematurely.</span></span> 

<span data-ttu-id="7266d-189">最後に、このフェーズでは、デバイスが[デバイスリスト](device-list.md)から削除され、アーカイブされた[デバイスリスト](archived-device-list.md)に移動します。</span><span class="sxs-lookup"><span data-stu-id="7266d-189">Finally, during this phase the device is removed from the [device list](device-list.md) and moved to the [archived device list](archived-device-list.md).</span></span>


## <a name="product-retirement"></a><span data-ttu-id="7266d-190">製品の定年</span><span class="sxs-lookup"><span data-stu-id="7266d-190">Product retirement</span></span>

<span data-ttu-id="7266d-191">製品の廃止は、ライフサイクルの最終フェーズです。</span><span class="sxs-lookup"><span data-stu-id="7266d-191">Product retirement is the final phase of the lifecycle.</span></span> <span data-ttu-id="7266d-192">このフェーズでは、その製品タイプの新しいデバイスを Microsoft Managed Desktop に登録することはできません。定義により、既存のすべてのデバイスが許可された3年間の期間外になります。</span><span class="sxs-lookup"><span data-stu-id="7266d-192">In this phase, no new devices of that product type can be enrolled in Microsoft Managed Desktop and, by definition, all existing devices are now outside their allowed three-year term.</span></span> <span data-ttu-id="7266d-193">この間、Microsoft Managed Desktop は、パブリックリストからデバイスを完全に削除します。</span><span class="sxs-lookup"><span data-stu-id="7266d-193">During this time, Microsoft Managed Desktop will remove the device from the public list entirely.</span></span> <span data-ttu-id="7266d-194">また、このフェーズでは、まだ置換を行っていない場合は、Microsoft Managed Desktop を開始すると、コンプライアンスが適用されていないデバイスのランプダウンが発生し始めて、低下しているサービスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="7266d-194">It's also during this phase where, if you haven't already procured replacements, you'll start to see diminished services as Microsoft Managed Desktop starts to ramp down on the devices which are out of compliance.</span></span> 

## <a name="devices-that-are-out-of-compliance"></a><span data-ttu-id="7266d-195">準拠していないデバイス</span><span class="sxs-lookup"><span data-stu-id="7266d-195">Devices that are out of compliance</span></span>

<span data-ttu-id="7266d-196">Microsoft Managed Desktop management の許可されたウィンドウが経過したときにデバイスが準拠していません。</span><span class="sxs-lookup"><span data-stu-id="7266d-196">A device is out of compliance when its allowed window for Microsoft Managed Desktop management has elapsed.</span></span> <span data-ttu-id="7266d-197">これは、デバイスが3年の管理に達した場合、またはその製品の種類がデバイスカタログから削除された場合に、最初に発生します。</span><span class="sxs-lookup"><span data-stu-id="7266d-197">This occurs when the device has reached three years of management or when that product type is removed from the device catalog, whichever occurs first.</span></span> <span data-ttu-id="7266d-198">現在のデバイスが準拠していない状態になる前に、新しいデバイスが展開されるように、常に調達サイクルを対象とする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7266d-198">You should always target your procurement cycles such that new devices are deployed prior to current devices going out of compliance.</span></span>

<span data-ttu-id="7266d-199">Microsoft マネージドデスクトップチームは、調達サイクルが長く、長期予算に関連して計画されていることを認識しています。</span><span class="sxs-lookup"><span data-stu-id="7266d-199">The Microsoft Managed Desktop team knows that procurement cycles are long and planned around long-running budgets.</span></span> <span data-ttu-id="7266d-200">常にデバイスの作成状態を認識していることを確認するために、管理下にあるすべてのデバイスを一覧表示する[web サイト](https://aka.ms/mmdportal)を提供し、その経過時間と、コンプライアンスを示す状態を提供します。</span><span class="sxs-lookup"><span data-stu-id="7266d-200">To ensure that you're always aware of the state of your device population, we provide a [website](https://aka.ms/mmdportal) that lists every device under management, its age, and a status indicating its compliance.</span></span> <span data-ttu-id="7266d-201">これは、デバイスの有効期限に関する最新情報を常に持っており、任意の調達計画サイクルでそのレポートを使用できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="7266d-201">This means you always have the latest information regarding device age and can use the report in any procurement planning cycle.</span></span> 







