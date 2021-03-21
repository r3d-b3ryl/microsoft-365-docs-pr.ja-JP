---
title: データ移行をリクエストする方法
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5bb64310-36fc-473d-b791-a0176f21707f
f1.keywords:
- NOCSH
description: 既存のOffice 365 のお客様は、Microsoft 365 サービス データを新しい地域に移動するために、国の期限前に要求を提出する必要があります。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e68feeca842061c43c7be70d9b8b930f068d8e4e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927314"
---
# <a name="how-to-request-your-data-move"></a><span data-ttu-id="c0e6a-103">データ移行をリクエストする方法</span><span class="sxs-lookup"><span data-stu-id="c0e6a-103">How to request your data move</span></span>

> [!NOTE]
> <span data-ttu-id="c0e6a-104">このページの情報は、データセンター geo で新しいデータセンターが開く前に、既存の Microsoft 365 テナントを持っていたお客様にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-104">The information on this page only applies to customers who had existing Microsoft 365 tenants before the new datacenters in their datacenter geo opened.</span></span> <span data-ttu-id="c0e6a-105">移行の適格性は、特定のサービス プロビジョニング日にも依存します。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-105">Migration eligibility also depends on the specific service provisioning date.</span></span>  <span data-ttu-id="c0e6a-106">テナントの作成日が必ずしも重要な 1 つの日付ではない場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-106">The tenant creation date may not always be the single date that matters.</span></span>
  
<span data-ttu-id="c0e6a-107">対象となる Microsoft 365 のお客様は、組織全体の主要な顧客データの移行を一時要求できます。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-107">Eligible Microsoft 365 customers may request migration for their entire organization’s core customer data at rest.</span></span>  <span data-ttu-id="c0e6a-108">このプログラムは、表に記載されている期間および Microsoft 365 テナントに関連付けられた対象となるサインアップ国を持つ顧客からの、各国の要求をサポートします。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-108">The program supports requests for each country in the time period described in the table and from customers with an eligible signup country associated with their Microsoft 365 tenant.</span></span>
  
## <a name="when-can-i-request-a-move"></a><span data-ttu-id="c0e6a-109">いつ移行をリクエストできますか?</span><span class="sxs-lookup"><span data-stu-id="c0e6a-109">When can I request a move?</span></span>

| <span data-ttu-id="c0e6a-110">サインアップ国を持つお客様</span><span class="sxs-lookup"><span data-stu-id="c0e6a-110">Customers with signup country in</span></span> | <span data-ttu-id="c0e6a-111">リクエスト期間の開始</span><span class="sxs-lookup"><span data-stu-id="c0e6a-111">Request period begins</span></span> | <span data-ttu-id="c0e6a-112">リクエストの期限</span><span class="sxs-lookup"><span data-stu-id="c0e6a-112">Request deadline</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="c0e6a-113">日本</span><span class="sxs-lookup"><span data-stu-id="c0e6a-113">Japan</span></span>  <br/> |<span data-ttu-id="c0e6a-114">2020 年 1 月 1 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-114">January 1, 2020</span></span>  <br/> |<span data-ttu-id="c0e6a-115">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-115">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="c0e6a-116">オーストラリア、ニュージーランド、フィジー</span><span class="sxs-lookup"><span data-stu-id="c0e6a-116">Australia, New Zealand, Fiji</span></span>  <br/> |<span data-ttu-id="c0e6a-117">2020 年 1 月 1 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-117">January 1, 2020</span></span>  <br/> |<span data-ttu-id="c0e6a-118">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-118">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="c0e6a-119">インド</span><span class="sxs-lookup"><span data-stu-id="c0e6a-119">India</span></span>  <br/> |<span data-ttu-id="c0e6a-120">2020 年 1 月 1 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-120">January 1, 2020</span></span>  <br/> |<span data-ttu-id="c0e6a-121">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-121">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="c0e6a-122">カナダ</span><span class="sxs-lookup"><span data-stu-id="c0e6a-122">Canada</span></span>  <br/> |<span data-ttu-id="c0e6a-123">2020 年 1 月 1 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-123">January 1, 2020</span></span>  <br/> |<span data-ttu-id="c0e6a-124">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-124">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="c0e6a-125">英国</span><span class="sxs-lookup"><span data-stu-id="c0e6a-125">United Kingdom</span></span>  <br/> |<span data-ttu-id="c0e6a-126">2020 年 1 月 1 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-126">January 1, 2020</span></span>  <br/> |<span data-ttu-id="c0e6a-127">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-127">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="c0e6a-128">韓国</span><span class="sxs-lookup"><span data-stu-id="c0e6a-128">South Korea</span></span>  <br/> |<span data-ttu-id="c0e6a-129">2020 年 1 月 1 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-129">January 1, 2020</span></span>  <br/> |<span data-ttu-id="c0e6a-130">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-130">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="c0e6a-131">フランス</span><span class="sxs-lookup"><span data-stu-id="c0e6a-131">France</span></span>  <br/> |<span data-ttu-id="c0e6a-132">2020 年 1 月 1 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-132">January 1, 2020</span></span>  <br/> |<span data-ttu-id="c0e6a-133">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-133">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="c0e6a-134">アラブ首長国連邦</span><span class="sxs-lookup"><span data-stu-id="c0e6a-134">United Arab Emirates</span></span>  <br/> |<span data-ttu-id="c0e6a-135">2019 年 7 月 15 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-135">July 15, 2019</span></span>  <br/> |<span data-ttu-id="c0e6a-136">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-136">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="c0e6a-137">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="c0e6a-137">South Africa</span></span>  <br/> |<span data-ttu-id="c0e6a-138">2019 年 7 月 25 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-138">July 25, 2019</span></span>  <br/> |<span data-ttu-id="c0e6a-139">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-139">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="c0e6a-140">スイス、リヒテンシュタイン</span><span class="sxs-lookup"><span data-stu-id="c0e6a-140">Switzerland, Liechtenstein</span></span>  <br/> |<span data-ttu-id="c0e6a-141">2019 年 12 月 10 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-141">December 10, 2019</span></span>  <br/> |<span data-ttu-id="c0e6a-142">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-142">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="c0e6a-143">ノルウェー</span><span class="sxs-lookup"><span data-stu-id="c0e6a-143">Norway</span></span>  <br/> |<span data-ttu-id="c0e6a-144">2020 年 4 月 15 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-144">April 15, 2020</span></span>  <br/> |<span data-ttu-id="c0e6a-145">2020 年 10 月 31 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-145">October 31, 2020</span></span>  <br/> |
|<span data-ttu-id="c0e6a-146">ドイツ</span><span class="sxs-lookup"><span data-stu-id="c0e6a-146">Germany</span></span>  <br/> |<span data-ttu-id="c0e6a-147">2020 年 11 月 1 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-147">November 1, 2020</span></span>  <br/> |<span data-ttu-id="c0e6a-148">2021 年 4 月 30 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-148">April 30, 2021</span></span>  <br/> |
|<span data-ttu-id="c0e6a-149">ブラジル</span><span class="sxs-lookup"><span data-stu-id="c0e6a-149">Brazil</span></span>  <br/> |<span data-ttu-id="c0e6a-150">2020 年 11 月 18 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-150">November 18, 2020</span></span>  <br/> |<span data-ttu-id="c0e6a-151">2021 年 5 月 31 日</span><span class="sxs-lookup"><span data-stu-id="c0e6a-151">May 31, 2021</span></span>  <br/> |

## <a name="how-to-request-a-move"></a><span data-ttu-id="c0e6a-152">移行をリクエストする方法</span><span class="sxs-lookup"><span data-stu-id="c0e6a-152">How to request a move</span></span>

<span data-ttu-id="c0e6a-153">対象となるお客様には、Microsoft 365 管理センターにページが表示され、コア顧客データを新しいデータセンター領域に移動できます。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-153">Eligible customers will see a page in the Microsoft 365 admin center, which will allow them to request to have their core customer data moved to their new datacenter region.</span></span>  
  
<span data-ttu-id="c0e6a-154">Microsoft 365 管理センターのページにアクセスするには、左側のナビゲーション ウィンドウで [設定] を展開し、[組織の設定]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-154">To access the page in the Microsoft 365 admin center, in the navigation pane on the left, expand **Settings**, and then click **Org Settings**.</span></span>
<span data-ttu-id="c0e6a-155">[組織プロファイル] **タブを選択** し、[データ常駐 **] オプションを選択します**。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-155">Select the tab **Organization profile**, then select the option **Data residency**.</span></span>
  
<span data-ttu-id="c0e6a-156">テナントが Microsoft 365 Move Program の対象ではない場合、このセクションは表示されない。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-156">You will not see this section if your tenant is not eligible for the Microsoft 365 Move Program.</span></span>  <span data-ttu-id="c0e6a-157">組織にデータ常駐の要件がある場合、移行を要求する必要がある場合は、チェック ボックスをオンにして、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-157">If your organization has data residency requirements and you need to request migration, mark the checkbox and then **Save**.</span></span>
  
![データセンターのオプトイン操作画面](../media/dataresidencyflyoutae.jpg)
  
<span data-ttu-id="c0e6a-159">[データ常駐]**セクションのテキスト** は、組織が適切な国と日付にデータを移動する要求を示すために変更されます。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-159">The text in the **Data residency** will section change to indicate **Your organization has requested to move its data** to the appropriate country and date.</span></span> <span data-ttu-id="c0e6a-160">メッセージ センターにも確認メッセージが届きます。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-160">You'll also have a confirmation message in your message center.</span></span> <span data-ttu-id="c0e6a-161">これにより、移行が正常にリクエストされたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-161">This confirms that you have successfully requested a move.</span></span> 
  
## <a name="what-happens-after-requesting-a-move"></a><span data-ttu-id="c0e6a-162">移行をリクエストした後はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="c0e6a-162">What happens after requesting a move?</span></span>

<span data-ttu-id="c0e6a-163">移行を要求した後、運用上の制約が許す限り、対象となる Microsoft 365 サービスに対して、コア顧客データを保存中に移動する予定です。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-163">After requesting a move, we will plan to move your core customer data at rest for eligible Microsoft 365 services as quickly as our operational constraints allow.</span></span> <span data-ttu-id="c0e6a-164">予測不可能な性質の制約が数多くあるため、移行が実施される特定の日付や時間帯を共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-164">Due to the unpredictable nature of many of the constraints, we cannot share a specific date or timeframe for the moves.</span></span> <span data-ttu-id="c0e6a-165">顧客テナント管理者は、各サービスの移動が完了した後、メッセージ センターに通知を表示します。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-165">Customer tenant administrators will see a notification in Message Center after the move for each service has completed.</span></span>
  
<span data-ttu-id="c0e6a-166">移行を完了するには、お住まいの国のリクエストの期限から最大 24 か月かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-166">Moves may take up to 24 months from the request deadline for your country to complete.</span></span>
  
## <a name="microsoft-teams"></a><span data-ttu-id="c0e6a-167">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0e6a-167">Microsoft Teams</span></span>

<span data-ttu-id="c0e6a-168">2020 年 1 月現在、365 か国Office対象地域のお客様は、Microsoft Teams チャット サービス データの移行をオプトインできます。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-168">As of January 2020, customers in eligible Office 365 countries can opt-in for migration of Microsoft Teams chat service data.</span></span>  <span data-ttu-id="c0e6a-169">以前に Data Residency の移行をオプトインしたお客様は、Teams をローカル データセンター geo に移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-169">Customers that previously opted-in for a Data Residency move will also have Teams move to their local datacenter geo.</span></span>  <span data-ttu-id="c0e6a-170">これらの顧客は追加のアクションを必要とします。</span><span class="sxs-lookup"><span data-stu-id="c0e6a-170">No additional action is required by these customers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c0e6a-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0e6a-171">Related topics</span></span>

[<span data-ttu-id="c0e6a-172">コア データを新しい Office 365 データ センター geo に移行する</span><span class="sxs-lookup"><span data-stu-id="c0e6a-172">Moving core data to new Office 365 datacenter geos</span></span>](moving-data-to-new-datacenter-geos.md)

[<span data-ttu-id="c0e6a-173">データ移行についての一般的な FAQ</span><span class="sxs-lookup"><span data-stu-id="c0e6a-173">Data move general FAQ</span></span>](data-move-faq.md)

[<span data-ttu-id="c0e6a-174">Microsoft Dynamics CRM Online の新しいデータ センター geo</span><span class="sxs-lookup"><span data-stu-id="c0e6a-174">New datacenter geos for Microsoft Dynamics CRM Online</span></span>](/power-platform/admin/new-datacenter-regions)
  
[<span data-ttu-id="c0e6a-175">Azure のリージョン</span><span class="sxs-lookup"><span data-stu-id="c0e6a-175">Azure services by region</span></span>](https://azure.microsoft.com/regions/)
