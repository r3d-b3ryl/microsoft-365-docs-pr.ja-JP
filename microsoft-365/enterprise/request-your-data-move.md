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
description: 既存の Office 365 のお客様は、お住まいの国が新しい geo に Microsoft 365 サービスデータを移動する前に、要求を提出する必要があります。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 10c77fdde8583c9d791c9fed936f94aad8fc7264
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333886"
---
# <a name="how-to-request-your-data-move"></a><span data-ttu-id="14cdf-103">データ移行をリクエストする方法</span><span class="sxs-lookup"><span data-stu-id="14cdf-103">How to request your data move</span></span>

> [!NOTE]
> <span data-ttu-id="14cdf-104">このページの情報は、データセンター geo の新しいデータセンターが開かれる前に、既存の Microsoft 365 テナントを持っているお客様にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="14cdf-104">The information on this page only applies to customers who had existing Microsoft 365 tenants before the new datacenters in their datacenter geo opened.</span></span> <span data-ttu-id="14cdf-105">移行の適格性は、特定のサービスのプロビジョニング日付にも依存します。</span><span class="sxs-lookup"><span data-stu-id="14cdf-105">Migration eligibility also depends on the specific service provisioning date.</span></span>  <span data-ttu-id="14cdf-106">テナントの作成日は、必ずしも重要な1つの日付ではありません。</span><span class="sxs-lookup"><span data-stu-id="14cdf-106">The tenant creation date may not always be the single date that matters.</span></span>
  
<span data-ttu-id="14cdf-107">対象となる Microsoft 365 のお客様は、組織全体の主要な顧客データを保存して、移行を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="14cdf-107">Eligible Microsoft 365 customers may request migration for their entire organization’s core customer data at rest.</span></span>  <span data-ttu-id="14cdf-108">このプログラムは、Microsoft 365 テナントに関連付けられた適格なサインアップ国を持つ、表に記載されている期間内の各国に対する要求をサポートします。</span><span class="sxs-lookup"><span data-stu-id="14cdf-108">The program supports requests for each country in the time period described in the table and from customers with an eligible signup country associated with their Microsoft 365 tenant.</span></span>
  
## <a name="when-can-i-request-a-move"></a><span data-ttu-id="14cdf-109">いつ移行をリクエストできますか?</span><span class="sxs-lookup"><span data-stu-id="14cdf-109">When can I request a move?</span></span>

|<span data-ttu-id="14cdf-110">**国がサインアップしているお客様**</span><span class="sxs-lookup"><span data-stu-id="14cdf-110">**Customers with signup country in**</span></span>|<span data-ttu-id="14cdf-111">**リクエスト期間の開始**</span><span class="sxs-lookup"><span data-stu-id="14cdf-111">**Request period begins**</span></span>|<span data-ttu-id="14cdf-112">**リクエストの期限**</span><span class="sxs-lookup"><span data-stu-id="14cdf-112">**Request deadline**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="14cdf-113">日本</span><span class="sxs-lookup"><span data-stu-id="14cdf-113">Japan</span></span>  <br/> |<span data-ttu-id="14cdf-114">2020年1月1日</span><span class="sxs-lookup"><span data-stu-id="14cdf-114">January 1, 2020</span></span>  <br/> |<span data-ttu-id="14cdf-115">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="14cdf-115">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="14cdf-116">オーストラリア、ニュージーランド、フィジー</span><span class="sxs-lookup"><span data-stu-id="14cdf-116">Australia, New Zealand, Fiji</span></span>  <br/> |<span data-ttu-id="14cdf-117">2020年1月1日</span><span class="sxs-lookup"><span data-stu-id="14cdf-117">January 1, 2020</span></span>  <br/> |<span data-ttu-id="14cdf-118">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="14cdf-118">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="14cdf-119">インド</span><span class="sxs-lookup"><span data-stu-id="14cdf-119">India</span></span>  <br/> |<span data-ttu-id="14cdf-120">2020年1月1日</span><span class="sxs-lookup"><span data-stu-id="14cdf-120">January 1, 2020</span></span>  <br/> |<span data-ttu-id="14cdf-121">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="14cdf-121">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="14cdf-122">カナダ</span><span class="sxs-lookup"><span data-stu-id="14cdf-122">Canada</span></span>  <br/> |<span data-ttu-id="14cdf-123">2020年1月1日</span><span class="sxs-lookup"><span data-stu-id="14cdf-123">January 1, 2020</span></span>  <br/> |<span data-ttu-id="14cdf-124">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="14cdf-124">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="14cdf-125">英国</span><span class="sxs-lookup"><span data-stu-id="14cdf-125">United Kingdom</span></span>  <br/> |<span data-ttu-id="14cdf-126">2020年1月1日</span><span class="sxs-lookup"><span data-stu-id="14cdf-126">January 1, 2020</span></span>  <br/> |<span data-ttu-id="14cdf-127">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="14cdf-127">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="14cdf-128">韓国</span><span class="sxs-lookup"><span data-stu-id="14cdf-128">South Korea</span></span>  <br/> |<span data-ttu-id="14cdf-129">2020年1月1日</span><span class="sxs-lookup"><span data-stu-id="14cdf-129">January 1, 2020</span></span>  <br/> |<span data-ttu-id="14cdf-130">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="14cdf-130">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="14cdf-131">フランス</span><span class="sxs-lookup"><span data-stu-id="14cdf-131">France</span></span>  <br/> |<span data-ttu-id="14cdf-132">2020年1月1日</span><span class="sxs-lookup"><span data-stu-id="14cdf-132">January 1, 2020</span></span>  <br/> |<span data-ttu-id="14cdf-133">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="14cdf-133">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="14cdf-134">アラブ首長国連邦</span><span class="sxs-lookup"><span data-stu-id="14cdf-134">United Arab Emirates</span></span>  <br/> |<span data-ttu-id="14cdf-135">2019 年 7 月 15 日</span><span class="sxs-lookup"><span data-stu-id="14cdf-135">July 15, 2019</span></span>  <br/> |<span data-ttu-id="14cdf-136">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="14cdf-136">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="14cdf-137">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="14cdf-137">South Africa</span></span>  <br/> |<span data-ttu-id="14cdf-138">2019 年 7 月 25 日</span><span class="sxs-lookup"><span data-stu-id="14cdf-138">July 25, 2019</span></span>  <br/> |<span data-ttu-id="14cdf-139">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="14cdf-139">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="14cdf-140">スイス、リヒテンシュタイン</span><span class="sxs-lookup"><span data-stu-id="14cdf-140">Switzerland, Liechtenstein</span></span>  <br/> |<span data-ttu-id="14cdf-141">2019 年 12 月 10 日</span><span class="sxs-lookup"><span data-stu-id="14cdf-141">December 10, 2019</span></span>  <br/> |<span data-ttu-id="14cdf-142">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="14cdf-142">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="14cdf-143">ノルウェー</span><span class="sxs-lookup"><span data-stu-id="14cdf-143">Norway</span></span>  <br/> |<span data-ttu-id="14cdf-144">2020 年 4 月 15 日</span><span class="sxs-lookup"><span data-stu-id="14cdf-144">April 15, 2020</span></span>  <br/> |<span data-ttu-id="14cdf-145">2020年10月31日</span><span class="sxs-lookup"><span data-stu-id="14cdf-145">October 31, 2020</span></span>  <br/> |
|<span data-ttu-id="14cdf-146">ドイツ</span><span class="sxs-lookup"><span data-stu-id="14cdf-146">Germany</span></span>  <br/> |<span data-ttu-id="14cdf-147">2020年10月1日</span><span class="sxs-lookup"><span data-stu-id="14cdf-147">October 1, 2020</span></span>  <br/> |<span data-ttu-id="14cdf-148">2021年3月31日</span><span class="sxs-lookup"><span data-stu-id="14cdf-148">March 31, 2021</span></span>  <br/> |

## <a name="how-to-request-a-move"></a><span data-ttu-id="14cdf-149">移行をリクエストする方法</span><span class="sxs-lookup"><span data-stu-id="14cdf-149">How to request a move</span></span>

<span data-ttu-id="14cdf-150">対象となるお客様には、 [Microsoft 365 管理センター](https://aka.ms/365admin)にページが表示されます。これにより、お客様は自社のコア顧客データを新しいデータセンターリージョンに移動するよう要求できます。</span><span class="sxs-lookup"><span data-stu-id="14cdf-150">Eligible customers will see a page in the [Microsoft 365 admin center](https://aka.ms/365admin), which will allow them to request to have their core customer data moved to their new datacenter region.</span></span>  
  
<span data-ttu-id="14cdf-151">Microsoft 365 管理センターのページにアクセスするには、左側のナビゲーションウィンドウで [ **設定**] を展開し、[ **組織の設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14cdf-151">To access the page in the Microsoft 365 admin center, in the navigation pane on the left, expand **Settings**, and then click **Org Settings**.</span></span>
<span data-ttu-id="14cdf-152">Tab **組織プロファイル**を選択して、[ **Data レジデンシー**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="14cdf-152">Select the tab **Organization profile**, then select the option **Data residency**.</span></span>
  
<span data-ttu-id="14cdf-153">このセクションは、テナントが Microsoft 365 引っ越しプログラムの対象外である場合には表示されません。</span><span class="sxs-lookup"><span data-stu-id="14cdf-153">You will not see this section if your tenant is not eligible for the Microsoft 365 Move Program.</span></span>  <span data-ttu-id="14cdf-154">データ常駐の要件があり、移行を要求する必要がある組織の場合は、チェックボックスをオンにして、 **保存**します。</span><span class="sxs-lookup"><span data-stu-id="14cdf-154">If your organization has data residency requirements and you need to request migration, mark the checkbox and then **Save**.</span></span>
  
![データセンターのオプトイン操作画面](../media/dataresidencyflyoutae.jpg)
  
<span data-ttu-id="14cdf-156">**データ常駐**のテキストは、組織が適切な国および日付に**データを移動するように要求**したことを示すように、セクションが変更されます。</span><span class="sxs-lookup"><span data-stu-id="14cdf-156">The text in the **Data residency** will section change to indicate **Your organization has requested to move its data** to the appropriate country and date.</span></span> <span data-ttu-id="14cdf-157">メッセージ センターにも確認メッセージが届きます。</span><span class="sxs-lookup"><span data-stu-id="14cdf-157">You'll also have a confirmation message in your message center.</span></span> <span data-ttu-id="14cdf-158">これにより、移行が正常にリクエストされたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="14cdf-158">This confirms that you have successfully requested a move.</span></span> 
  
## <a name="what-happens-after-requesting-a-move"></a><span data-ttu-id="14cdf-159">移行をリクエストした後はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="14cdf-159">What happens after requesting a move?</span></span>

<span data-ttu-id="14cdf-160">移行をリクエストした後は、運用上の制約が許す限り迅速に、コアのお客様のデータを、適用可能な Microsoft 365 サービスに移行することを計画します。</span><span class="sxs-lookup"><span data-stu-id="14cdf-160">After requesting a move, we will plan to move your core customer data at rest for eligible Microsoft 365 services as quickly as our operational constraints allow.</span></span> <span data-ttu-id="14cdf-161">予測不可能な性質の制約が数多くあるため、移行が実施される特定の日付や時間帯を共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="14cdf-161">Due to the unpredictable nature of many of the constraints, we cannot share a specific date or timeframe for the moves.</span></span> <span data-ttu-id="14cdf-162">お客様のテナントの管理者は、各サービスの移行が完了した後で、メッセージセンターに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="14cdf-162">Customer tenant administrators will see a notification in Message Center after the move for each service has completed.</span></span>
  
<span data-ttu-id="14cdf-163">移行を完了するには、お住まいの国のリクエストの期限から最大 24 か月かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="14cdf-163">Moves may take up to 24 months from the request deadline for your country to complete.</span></span>
  
## <a name="microsoft-teams"></a><span data-ttu-id="14cdf-164">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="14cdf-164">Microsoft Teams</span></span>

<span data-ttu-id="14cdf-165">2020年1月の間、対象となる Office 365 諸国のお客様は、Microsoft Teams chat service データの移行をオプトインできます。</span><span class="sxs-lookup"><span data-stu-id="14cdf-165">As of January 2020, customers in eligible Office 365 countries can opt-in for migration of Microsoft Teams chat service data.</span></span>  <span data-ttu-id="14cdf-166">以前にデータ常駐移行をオプトインしていたお客様も、Teams をローカルデータセンター geo に移行することになります。</span><span class="sxs-lookup"><span data-stu-id="14cdf-166">Customers that previously opted-in for a Data Residency move will also have Teams move to their local datacenter geo.</span></span>  <span data-ttu-id="14cdf-167">これらのお客様には、追加のアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="14cdf-167">No additional action is required by these customers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="14cdf-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="14cdf-168">Related topics</span></span>

[<span data-ttu-id="14cdf-169">コア データを新しい Office 365 データ センター geo に移行する</span><span class="sxs-lookup"><span data-stu-id="14cdf-169">Moving core data to new Office 365 datacenter geos</span></span>](moving-data-to-new-datacenter-geos.md)

[<span data-ttu-id="14cdf-170">データ移行についての一般的な FAQ</span><span class="sxs-lookup"><span data-stu-id="14cdf-170">Data move general FAQ</span></span>](data-move-faq.md)

[<span data-ttu-id="14cdf-171">Microsoft Dynamics CRM Online の新しいデータ センター geo</span><span class="sxs-lookup"><span data-stu-id="14cdf-171">New datacenter geos for Microsoft Dynamics CRM Online</span></span>](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[<span data-ttu-id="14cdf-172">Azure のリージョン</span><span class="sxs-lookup"><span data-stu-id="14cdf-172">Azure services by region</span></span>](https://azure.microsoft.com/regions/)
  

