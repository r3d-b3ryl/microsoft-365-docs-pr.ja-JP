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
description: 既存のOffice 365ユーザーは、その国のサービス データを新しい地域に移動Microsoft 365前に要求を提出する必要があります。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e68feeca842061c43c7be70d9b8b930f068d8e4e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927314"
---
# <a name="how-to-request-your-data-move"></a><span data-ttu-id="46e51-103">データ移行をリクエストする方法</span><span class="sxs-lookup"><span data-stu-id="46e51-103">How to request your data move</span></span>

> [!NOTE]
> <span data-ttu-id="46e51-104">このページの情報は、データセンター geo で新しいデータセンターが開く前Microsoft 365既存のテナントを持っていたお客様にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="46e51-104">The information on this page only applies to customers who had existing Microsoft 365 tenants before the new datacenters in their datacenter geo opened.</span></span> <span data-ttu-id="46e51-105">移行の適格性は、特定のサービス プロビジョニング日にも依存します。</span><span class="sxs-lookup"><span data-stu-id="46e51-105">Migration eligibility also depends on the specific service provisioning date.</span></span>  <span data-ttu-id="46e51-106">テナントの作成日が必ずしも重要な 1 つの日付ではない場合があります。</span><span class="sxs-lookup"><span data-stu-id="46e51-106">The tenant creation date may not always be the single date that matters.</span></span>
  
<span data-ttu-id="46e51-107">対象となるMicrosoft 365顧客は、組織の主要な顧客データ全体に対して移行を要求できます。</span><span class="sxs-lookup"><span data-stu-id="46e51-107">Eligible Microsoft 365 customers may request migration for their entire organization’s core customer data at rest.</span></span>  <span data-ttu-id="46e51-108">このプログラムは、表に記載されている期間、および対象となるサインアップ国がテナントに関連付けられているお客様からの、各国Microsoft 365します。</span><span class="sxs-lookup"><span data-stu-id="46e51-108">The program supports requests for each country in the time period described in the table and from customers with an eligible signup country associated with their Microsoft 365 tenant.</span></span>
  
## <a name="when-can-i-request-a-move"></a><span data-ttu-id="46e51-109">いつ移行をリクエストできますか?</span><span class="sxs-lookup"><span data-stu-id="46e51-109">When can I request a move?</span></span>

| <span data-ttu-id="46e51-110">サインアップ国を持つお客様</span><span class="sxs-lookup"><span data-stu-id="46e51-110">Customers with signup country in</span></span> | <span data-ttu-id="46e51-111">リクエスト期間の開始</span><span class="sxs-lookup"><span data-stu-id="46e51-111">Request period begins</span></span> | <span data-ttu-id="46e51-112">リクエストの期限</span><span class="sxs-lookup"><span data-stu-id="46e51-112">Request deadline</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="46e51-113">日本</span><span class="sxs-lookup"><span data-stu-id="46e51-113">Japan</span></span>  <br/> |<span data-ttu-id="46e51-114">2020 年 1 月 1 日</span><span class="sxs-lookup"><span data-stu-id="46e51-114">January 1, 2020</span></span>  <br/> |<span data-ttu-id="46e51-115">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="46e51-115">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="46e51-116">オーストラリア、ニュージーランド、フィジー</span><span class="sxs-lookup"><span data-stu-id="46e51-116">Australia, New Zealand, Fiji</span></span>  <br/> |<span data-ttu-id="46e51-117">2020 年 1 月 1 日</span><span class="sxs-lookup"><span data-stu-id="46e51-117">January 1, 2020</span></span>  <br/> |<span data-ttu-id="46e51-118">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="46e51-118">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="46e51-119">インド</span><span class="sxs-lookup"><span data-stu-id="46e51-119">India</span></span>  <br/> |<span data-ttu-id="46e51-120">2020 年 1 月 1 日</span><span class="sxs-lookup"><span data-stu-id="46e51-120">January 1, 2020</span></span>  <br/> |<span data-ttu-id="46e51-121">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="46e51-121">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="46e51-122">カナダ</span><span class="sxs-lookup"><span data-stu-id="46e51-122">Canada</span></span>  <br/> |<span data-ttu-id="46e51-123">2020 年 1 月 1 日</span><span class="sxs-lookup"><span data-stu-id="46e51-123">January 1, 2020</span></span>  <br/> |<span data-ttu-id="46e51-124">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="46e51-124">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="46e51-125">英国</span><span class="sxs-lookup"><span data-stu-id="46e51-125">United Kingdom</span></span>  <br/> |<span data-ttu-id="46e51-126">2020 年 1 月 1 日</span><span class="sxs-lookup"><span data-stu-id="46e51-126">January 1, 2020</span></span>  <br/> |<span data-ttu-id="46e51-127">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="46e51-127">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="46e51-128">韓国</span><span class="sxs-lookup"><span data-stu-id="46e51-128">South Korea</span></span>  <br/> |<span data-ttu-id="46e51-129">2020 年 1 月 1 日</span><span class="sxs-lookup"><span data-stu-id="46e51-129">January 1, 2020</span></span>  <br/> |<span data-ttu-id="46e51-130">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="46e51-130">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="46e51-131">フランス</span><span class="sxs-lookup"><span data-stu-id="46e51-131">France</span></span>  <br/> |<span data-ttu-id="46e51-132">2020 年 1 月 1 日</span><span class="sxs-lookup"><span data-stu-id="46e51-132">January 1, 2020</span></span>  <br/> |<span data-ttu-id="46e51-133">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="46e51-133">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="46e51-134">アラブ首長国連邦</span><span class="sxs-lookup"><span data-stu-id="46e51-134">United Arab Emirates</span></span>  <br/> |<span data-ttu-id="46e51-135">2019 年 7 月 15 日</span><span class="sxs-lookup"><span data-stu-id="46e51-135">July 15, 2019</span></span>  <br/> |<span data-ttu-id="46e51-136">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="46e51-136">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="46e51-137">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="46e51-137">South Africa</span></span>  <br/> |<span data-ttu-id="46e51-138">2019 年 7 月 25 日</span><span class="sxs-lookup"><span data-stu-id="46e51-138">July 25, 2019</span></span>  <br/> |<span data-ttu-id="46e51-139">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="46e51-139">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="46e51-140">スイス、リヒテンシュタイン</span><span class="sxs-lookup"><span data-stu-id="46e51-140">Switzerland, Liechtenstein</span></span>  <br/> |<span data-ttu-id="46e51-141">2019 年 12 月 10 日</span><span class="sxs-lookup"><span data-stu-id="46e51-141">December 10, 2019</span></span>  <br/> |<span data-ttu-id="46e51-142">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="46e51-142">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="46e51-143">ノルウェー</span><span class="sxs-lookup"><span data-stu-id="46e51-143">Norway</span></span>  <br/> |<span data-ttu-id="46e51-144">2020 年 4 月 15 日</span><span class="sxs-lookup"><span data-stu-id="46e51-144">April 15, 2020</span></span>  <br/> |<span data-ttu-id="46e51-145">2020 年 10 月 31 日</span><span class="sxs-lookup"><span data-stu-id="46e51-145">October 31, 2020</span></span>  <br/> |
|<span data-ttu-id="46e51-146">ドイツ</span><span class="sxs-lookup"><span data-stu-id="46e51-146">Germany</span></span>  <br/> |<span data-ttu-id="46e51-147">2020 年 11 月 1 日</span><span class="sxs-lookup"><span data-stu-id="46e51-147">November 1, 2020</span></span>  <br/> |<span data-ttu-id="46e51-148">2021 年 4 月 30 日</span><span class="sxs-lookup"><span data-stu-id="46e51-148">April 30, 2021</span></span>  <br/> |
|<span data-ttu-id="46e51-149">ブラジル</span><span class="sxs-lookup"><span data-stu-id="46e51-149">Brazil</span></span>  <br/> |<span data-ttu-id="46e51-150">2020 年 11 月 18 日</span><span class="sxs-lookup"><span data-stu-id="46e51-150">November 18, 2020</span></span>  <br/> |<span data-ttu-id="46e51-151">2021 年 5 月 31 日</span><span class="sxs-lookup"><span data-stu-id="46e51-151">May 31, 2021</span></span>  <br/> |

## <a name="how-to-request-a-move"></a><span data-ttu-id="46e51-152">移行をリクエストする方法</span><span class="sxs-lookup"><span data-stu-id="46e51-152">How to request a move</span></span>

<span data-ttu-id="46e51-153">対象となる顧客には、Microsoft 365 管理センターにページが表示され、コア顧客データを新しいデータセンター領域に移動できます。</span><span class="sxs-lookup"><span data-stu-id="46e51-153">Eligible customers will see a page in the Microsoft 365 admin center, which will allow them to request to have their core customer data moved to their new datacenter region.</span></span>  
  
<span data-ttu-id="46e51-154">管理センターのMicrosoft 365にアクセスするには、左側のナビゲーション ウィンドウで [設定]**を展開** し、[組織] 設定 を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="46e51-154">To access the page in the Microsoft 365 admin center, in the navigation pane on the left, expand **Settings**, and then click **Org Settings**.</span></span>
<span data-ttu-id="46e51-155">[組織プロファイル] **タブを選択** し、[データ常駐 **] オプションを選択します**。</span><span class="sxs-lookup"><span data-stu-id="46e51-155">Select the tab **Organization profile**, then select the option **Data residency**.</span></span>
  
<span data-ttu-id="46e51-156">テナントが移行プログラムの対象ではない場合は、このセクションMicrosoft 365表示されます。</span><span class="sxs-lookup"><span data-stu-id="46e51-156">You will not see this section if your tenant is not eligible for the Microsoft 365 Move Program.</span></span>  <span data-ttu-id="46e51-157">組織にデータ常駐の要件がある場合、移行を要求する必要がある場合は、チェック ボックスをオンにして、[保存] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="46e51-157">If your organization has data residency requirements and you need to request migration, mark the checkbox and then **Save**.</span></span>
  
![データセンターのオプトイン操作画面](../media/dataresidencyflyoutae.jpg)
  
<span data-ttu-id="46e51-159">[データ常駐]**セクションのテキスト** は、組織が適切な国と日付にデータを移動する要求を示すために変更されます。</span><span class="sxs-lookup"><span data-stu-id="46e51-159">The text in the **Data residency** will section change to indicate **Your organization has requested to move its data** to the appropriate country and date.</span></span> <span data-ttu-id="46e51-160">メッセージ センターにも確認メッセージが届きます。</span><span class="sxs-lookup"><span data-stu-id="46e51-160">You'll also have a confirmation message in your message center.</span></span> <span data-ttu-id="46e51-161">これにより、移行が正常にリクエストされたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="46e51-161">This confirms that you have successfully requested a move.</span></span> 
  
## <a name="what-happens-after-requesting-a-move"></a><span data-ttu-id="46e51-162">移行をリクエストした後はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="46e51-162">What happens after requesting a move?</span></span>

<span data-ttu-id="46e51-163">移行を要求した後は、運用上の制約が許す限り迅速に、対象となるサービスMicrosoft 365顧客のコア データを移動する予定です。</span><span class="sxs-lookup"><span data-stu-id="46e51-163">After requesting a move, we will plan to move your core customer data at rest for eligible Microsoft 365 services as quickly as our operational constraints allow.</span></span> <span data-ttu-id="46e51-164">予測不可能な性質の制約が数多くあるため、移行が実施される特定の日付や時間帯を共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="46e51-164">Due to the unpredictable nature of many of the constraints, we cannot share a specific date or timeframe for the moves.</span></span> <span data-ttu-id="46e51-165">顧客テナント管理者は、各サービスの移動が完了した後、メッセージ センターに通知を表示します。</span><span class="sxs-lookup"><span data-stu-id="46e51-165">Customer tenant administrators will see a notification in Message Center after the move for each service has completed.</span></span>
  
<span data-ttu-id="46e51-166">移行を完了するには、お住まいの国のリクエストの期限から最大 24 か月かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="46e51-166">Moves may take up to 24 months from the request deadline for your country to complete.</span></span>
  
## <a name="microsoft-teams"></a><span data-ttu-id="46e51-167">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46e51-167">Microsoft Teams</span></span>

<span data-ttu-id="46e51-168">2020 年 1 月の現在、対象となるOffice 365のお客様は、チャット サービス データの移行Microsoft Teamsオプトインできます。</span><span class="sxs-lookup"><span data-stu-id="46e51-168">As of January 2020, customers in eligible Office 365 countries can opt-in for migration of Microsoft Teams chat service data.</span></span>  <span data-ttu-id="46e51-169">以前に移行を選択したお客様Data Residency、ローカル データセンター geo Teams移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46e51-169">Customers that previously opted-in for a Data Residency move will also have Teams move to their local datacenter geo.</span></span>  <span data-ttu-id="46e51-170">これらの顧客は追加のアクションを必要とします。</span><span class="sxs-lookup"><span data-stu-id="46e51-170">No additional action is required by these customers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="46e51-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="46e51-171">Related topics</span></span>

[<span data-ttu-id="46e51-172">コア データを新しい Office 365 データ センター geo に移行する</span><span class="sxs-lookup"><span data-stu-id="46e51-172">Moving core data to new Office 365 datacenter geos</span></span>](moving-data-to-new-datacenter-geos.md)

[<span data-ttu-id="46e51-173">データ移行についての一般的な FAQ</span><span class="sxs-lookup"><span data-stu-id="46e51-173">Data move general FAQ</span></span>](data-move-faq.md)

[<span data-ttu-id="46e51-174">Microsoft Dynamics CRM Online の新しいデータ センター geo</span><span class="sxs-lookup"><span data-stu-id="46e51-174">New datacenter geos for Microsoft Dynamics CRM Online</span></span>](/power-platform/admin/new-datacenter-regions)
  
[<span data-ttu-id="46e51-175">Azure のリージョン</span><span class="sxs-lookup"><span data-stu-id="46e51-175">Azure services by region</span></span>](https://azure.microsoft.com/regions/)
