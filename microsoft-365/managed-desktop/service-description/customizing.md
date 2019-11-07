---
title: サービスプランの例外
description: ''
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5c9e53278f76665d1b48da0fbeb4555565c183aa
ms.sourcegitcommit: 543ac29a15412a348b61db2297e7bcdcca842206
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "38020380"
---
# <a name="exceptions-to-the-service-plan"></a><span data-ttu-id="a243e-103">サービスプランの例外</span><span class="sxs-lookup"><span data-stu-id="a243e-103">Exceptions to the service plan</span></span>

<span data-ttu-id="a243e-104">Microsoft マネージドデスクトップは、合わせデバイスリスト、[標準デバイス設定](device-policies.md)、アプリケーション要件、および特定の[構成可能な設定](../working-with-managed-desktop/config-setting-overview.md)を提供します。これらの設定は、エンドユーザーにとって安全で生産的で快適な操作性を提供するために設計されています。</span><span class="sxs-lookup"><span data-stu-id="a243e-104">Microsoft Managed Desktop provides a curated device list, [standard device settings](device-policies.md), applications requirements, and certain [configurable settings](../working-with-managed-desktop/config-setting-overview.md), all designed to provide a secure, productive, and pleasant experience for end users.</span></span> <span data-ttu-id="a243e-105">提供されたとおりにサービスを常に使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a243e-105">It’s best to always stay with the service as provided.</span></span> <span data-ttu-id="a243e-106">ただし、一部のサービスの詳細が組織のニーズに完全に適合しない場合があることを認識しています。</span><span class="sxs-lookup"><span data-stu-id="a243e-106">However, we recognize that some details of the service might not fit exactly with your organization’s needs.</span></span> <span data-ttu-id="a243e-107">何らかの方法でサービスを変更する必要があると思われる場合は、次のプロセスに従って変更を依頼することが重要です。</span><span class="sxs-lookup"><span data-stu-id="a243e-107">If you feel you need to alter the service in some way, it’s important that you follow the following processes to request those changes.</span></span>

 
## <a name="types-of-exceptions"></a><span data-ttu-id="a243e-108">例外の種類</span><span class="sxs-lookup"><span data-stu-id="a243e-108">Types of exceptions</span></span>
<span data-ttu-id="a243e-109">例外は、Microsoft マネージドデスクトップ基本構成に追加または変更されたものです。例としては、USB ポート構成から新しいセキュリティエージェントを展開する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a243e-109">An exception is any addition or change to the Microsoft Managed Desktop base configuration; examples range from USB ports configuration to deploying a new security agent.</span></span> <span data-ttu-id="a243e-110">さまざまな例外は、次のようにグループ化します。</span><span class="sxs-lookup"><span data-stu-id="a243e-110">We group various exceptions as follows:</span></span>


|<span data-ttu-id="a243e-111">型</span><span class="sxs-lookup"><span data-stu-id="a243e-111">Type</span></span>  |<span data-ttu-id="a243e-112">説明</span><span class="sxs-lookup"><span data-stu-id="a243e-112">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="a243e-113">生産性向上ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="a243e-113">Productivity software</span></span>     |  <span data-ttu-id="a243e-114">エンドユーザーが必要とするフォアグラウンドソフトウェア、[アプリケーション要件](mmd-app-requirements.md)による制限</span><span class="sxs-lookup"><span data-stu-id="a243e-114">Foreground software needed by end users, restricted by the [application requirements](mmd-app-requirements.md)</span></span>       |
|<span data-ttu-id="a243e-115">Vpn & のセキュリティエージェント</span><span class="sxs-lookup"><span data-stu-id="a243e-115">Security agents & VPNs</span></span>     |  <span data-ttu-id="a243e-116">デバイスまたはネットワークの動作をセキュリティで保護、監視、または変更するために使用されるソフトウェア</span><span class="sxs-lookup"><span data-stu-id="a243e-116">Software used to secure, monitor, or change the behavior of the device or network</span></span>       |
|<span data-ttu-id="a243e-117">デジタル環境の監視</span><span class="sxs-lookup"><span data-stu-id="a243e-117">Digital experience monitoring</span></span>     |  <span data-ttu-id="a243e-118">ユーザーのデバイス上のデータを追跡してレポートを作成するために使用されるソフトウェア</span><span class="sxs-lookup"><span data-stu-id="a243e-118">Software used to track data on a user’s device to report to IT</span></span>       |
|<span data-ttu-id="a243e-119">ハードウェアまたはソフトウェアのドライバー</span><span class="sxs-lookup"><span data-stu-id="a243e-119">Hardware or software drivers</span></span>     |   <span data-ttu-id="a243e-120">デバイスドライバー。[アプリケーション要件](mmd-app-requirements.md)による制限</span><span class="sxs-lookup"><span data-stu-id="a243e-120">Device drivers, restricted by the [application requirements](mmd-app-requirements.md)</span></span>      |
|<span data-ttu-id="a243e-121">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a243e-121">Policies</span></span>     | <span data-ttu-id="a243e-122">管理対象デバイスでの Windows 10 または Office 365 ProPlus の設定</span><span class="sxs-lookup"><span data-stu-id="a243e-122">Windows 10 or Office 365 ProPlus settings on a managed device</span></span>        |
|<span data-ttu-id="a243e-123">デバイス</span><span class="sxs-lookup"><span data-stu-id="a243e-123">Devices</span></span>     | <span data-ttu-id="a243e-124">Microsoft マネージドデスクトップ[デバイスリスト](device-list.md)にないデバイス</span><span class="sxs-lookup"><span data-stu-id="a243e-124">Devices which are not on the Microsoft Managed Desktop [device list](device-list.md)</span></span>        |
|<span data-ttu-id="a243e-125">Other</span><span class="sxs-lookup"><span data-stu-id="a243e-125">Other</span></span>     |  <span data-ttu-id="a243e-126">他の領域でカバーされていないもの</span><span class="sxs-lookup"><span data-stu-id="a243e-126">Anything not covered by the other areas</span></span>       |



 
## <a name="request-an-exception"></a><span data-ttu-id="a243e-127">例外を要求する</span><span class="sxs-lookup"><span data-stu-id="a243e-127">Request an exception</span></span>

<span data-ttu-id="a243e-128">変更要求を作成して、Microsoft 管理対象デスクトップ管理ポータル経由で要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="a243e-128">Submit requests through the Microsoft Managed Desktop Admin portal by creating a change request.</span></span> <span data-ttu-id="a243e-129">次の詳細を含めるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="a243e-129">Be sure to include these details:</span></span>
-    <span data-ttu-id="a243e-130">型: excmption のカテゴリはどれですか?</span><span class="sxs-lookup"><span data-stu-id="a243e-130">type: Which category of excmption is it?</span></span> <span data-ttu-id="a243e-131">(前の表を参照)</span><span class="sxs-lookup"><span data-stu-id="a243e-131">(see the previous table)</span></span>
-   <span data-ttu-id="a243e-132">要件: の特定のビジネス要件は何ですか。</span><span class="sxs-lookup"><span data-stu-id="a243e-132">Requirement: What is the specific business requirement for the ?</span></span>
-   <span data-ttu-id="a243e-133">提案: ビジネスが要求しているのはどのソリューションですか?</span><span class="sxs-lookup"><span data-stu-id="a243e-133">Proposal: Which solution is your business requesting?</span></span>
-   <span data-ttu-id="a243e-134">タイムライン: この例外は、どのくらいの期間、最後に実行しますか?</span><span class="sxs-lookup"><span data-stu-id="a243e-134">Timeline: How long do you want this exception to last?</span></span> 


## <a name="how-we-assess-an-exception-request"></a><span data-ttu-id="a243e-135">例外要求を評価する方法</span><span class="sxs-lookup"><span data-stu-id="a243e-135">How we assess an exception request</span></span>

<span data-ttu-id="a243e-136">例外要求を確認するときは、次の順序でこれらの要素を評価します。</span><span class="sxs-lookup"><span data-stu-id="a243e-136">When we review exception requests, we assess these factors in this order:</span></span>
 
1.  <span data-ttu-id="a243e-137">Microsoft Managed Desktop がすべてのデバイスに展開されているアプリケーションとポリシーによってはネゴシエートできない場合があるため、要求がそれらに影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="a243e-137">Some applications and policies which Microsoft Managed Desktop deploys to all devices aren't negotiable, so your request must not affect those.</span></span> <span data-ttu-id="a243e-138">詳細については、「[デバイスの構成](device-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a243e-138">See [Device configuration](device-policies.md) for more information.</span></span>
2.  <span data-ttu-id="a243e-139">エンドユーザーがジョブを実行するために必要な制限のある生産性ソフトウェアは、承認される可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="a243e-139">Restricted productivity software required by an end user to do their job will likely be approved.</span></span> 
3.  <span data-ttu-id="a243e-140">Microsoft テクノロジを使用して要件を満たすことができる場合は、3 ~ 12 か月の例外移行期間の要求を承認する可能性があります (プロジェクトのスコープによって異なります)。</span><span class="sxs-lookup"><span data-stu-id="a243e-140">If we can meet your requirement by using Microsoft technology, we’ll likely approve your request for an exception migration period of three to twelve months (depending on the scope of the project).</span></span>
4.  <span data-ttu-id="a243e-141">Microsoft テクノロジを使用して要件を満たすことができない場合は、以下の条件のいずれかに違反しない限り、要求を承認する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="a243e-141">If we can’t meet your requirement by using Microsoft technology, we’ll likely approve your request unless it violates one of the conditions below.</span></span>  

<span data-ttu-id="a243e-142">これらの原則により、Microsoft マネージドデスクトップは、標準テンプレートからの逸脱を追跡しながら、常にニーズを満たすことができます。</span><span class="sxs-lookup"><span data-stu-id="a243e-142">These principles ensure that Microsoft Managed Desktop can always meet your needs while tracking deviations from our standard template.</span></span> 

## <a name="key-conditions"></a><span data-ttu-id="a243e-143">重要な条件</span><span class="sxs-lookup"><span data-stu-id="a243e-143">Key conditions</span></span>

<span data-ttu-id="a243e-144">例外を確認して、次の条件に違反していないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a243e-144">We review exceptions to ensure they don't violate any of these conditions:</span></span>

-   <span data-ttu-id="a243e-145">例外は、システムセキュリティに悪影響を与えないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a243e-145">An exception must not adversely impact system security.</span></span> 
-   <span data-ttu-id="a243e-146">例外を維持するには、Microsoft の管理されたデスクトップの操作またはサポートのコストが大きくならないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a243e-146">Maintaining the exception must not incur a significant cost for either Microsoft Managed Desktop operations or support.</span></span>
-   <span data-ttu-id="a243e-147">例外は、カーネルモードのクラッシュやハングなどの原因で、システムの安定性に影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="a243e-147">An exception must not affect system stability, for example, by causing kernel mode crashes or hangs.</span></span>
-   <span data-ttu-id="a243e-148">この変更によって、サービスの運用または Microsoft マネージドデスクトップのコアテクノロジとの競合が制限されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a243e-148">The change must not restrict us from operating the service or conflict with core Microsoft Managed Desktop technology.</span></span>

<span data-ttu-id="a243e-149">これらの条件は将来変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a243e-149">These conditions could change in the future.</span></span> <span data-ttu-id="a243e-150">このような変更を行う場合は、これらの条件が有効になる前に、30日の通知が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a243e-150">If we do make such changes, we’ll provide 30 days notice prior to those conditions coming into effect.</span></span>

## <a name="revoking-approval-for-an-exception"></a><span data-ttu-id="a243e-151">例外の承認を取り消す</span><span class="sxs-lookup"><span data-stu-id="a243e-151">Revoking approval for an exception</span></span>

<span data-ttu-id="a243e-152">要求された例外が承認および展開された後、最初の場所で変更を承認したときに明らかになっていない重要な条件に違反する問題を検出する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a243e-152">After a requested exception is approved and deployed, it’s possible that we might discover problems that violate the key conditions that weren’t evident when we approved the change in the first place.</span></span> <span data-ttu-id="a243e-153">このような状況では、の承認を取り消す必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a243e-153">In this situation, we might have to revoke approval for the .</span></span>
 
<span data-ttu-id="a243e-154">このような状況が発生した場合は、Microsoft Managed Desktop 管理ポータルを使用して通知します。</span><span class="sxs-lookup"><span data-stu-id="a243e-154">If this happens, we’ll notify you by using the Microsoft Managed Desktop admin portal.</span></span> <span data-ttu-id="a243e-155">最初に通知した時点から、例外が発生したデバイスが Microsoft 管理対象デスクトップサービスレベル契約によってバインドされなくなる前に、90日以内に例外を削除することができます。</span><span class="sxs-lookup"><span data-stu-id="a243e-155">From the first time we notify you, you have 90 days to remove the exception before the devices with the exception are no longer bound by Microsoft Managed Desktop service level agreements.</span></span> <span data-ttu-id="a243e-156">厳密なタイムラインに従って複数の通知を送信します。ただし、重大なインシデントや脅威では、タイムラインを変更したり、例外に関する決定を行ったりする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a243e-156">We'll send you several notifications according to a strict timeline--however, a severe incident or threat might require us to change the timeline or our decisions about an exception.</span></span> <span data-ttu-id="a243e-157">同意せずに例外を*削除*することはありませんが、失効した例外があるデバイスはサービスレベル契約によってバインドされなくなります。</span><span class="sxs-lookup"><span data-stu-id="a243e-157">We won't *remove* an exception without your consent, but any device with a revoked exception will no longer be bound by our service level agreement.</span></span> <span data-ttu-id="a243e-158">送信する通知のタイムラインは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a243e-158">Here is the timeline of notifications we will send you:</span></span>

- <span data-ttu-id="a243e-159">**最初の通知:** 承認の取り消しについての最初の注意事項として、失効する理由、必要な処置、これらのアクションの期限、および決定を強化するための手順についての情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a243e-159">**First notice:** We provide the first notice of our decision to revoke approval, including information about why we’re revoking it, the actions we advise you to take, the deadline for those actions, and steps to follow if you want to appeal the decision.</span></span> <span data-ttu-id="a243e-160">これは、例外をすべてのデバイスから削除する必要がある前に、それよりも前の90日になります。</span><span class="sxs-lookup"><span data-stu-id="a243e-160">This is 90 days in advance before the exception needs to be removed from all devices.</span></span> 
- <span data-ttu-id="a243e-161">**2 番目の通知 (30 日後):** 最初の通知で提供されるものと同じ情報を含む2番目の通知が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a243e-161">**Second notice (30 days later):** We provide a second notice, including the same information provided in the first notice.</span></span> 
- <span data-ttu-id="a243e-162">**3 番目の通知 (最初の通知の60日以降):** 最初の通知で提供されるものと同じ情報を含む、3つ目の通知が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a243e-162">**Third notice (60 days after the first notice):** We provide a third notice, including the same information provided in the first notice.</span></span> 
- <span data-ttu-id="a243e-163">**最終通知 (90 日の期限の1週間前):** 最初の通知で提供されるものと同じ情報を含む4番目の通知が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a243e-163">**Final notice (1 week before the 90-day deadline):** We provide a fourth notice, including the same information provided in the first notice.</span></span>
- <span data-ttu-id="a243e-164">**最初の通知から90日後:** Microsoft マネージドデスクトップサービスレベルアグリーメントは、失効したデバイスには適用されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="a243e-164">**90 days after first notice:** Microsoft Managed Desktop service level agreements no longer apply to any devices that have the revoked .</span></span> <span data-ttu-id="a243e-165">いつでも、意思決定をチャレンジして、アップグレード、構成の変更、ソフトウェアの変更など、考慮すべき追加情報を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="a243e-165">At any time, you can challenge the decision and provide additional information for consideration, including upgrade, configuration changes, or change of software.</span></span> 

