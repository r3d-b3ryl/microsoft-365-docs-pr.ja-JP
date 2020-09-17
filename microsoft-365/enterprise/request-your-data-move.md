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
ms.openlocfilehash: f7ca333ca12faab84df54582ecd3212842d26e1a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949800"
---
# <a name="how-to-request-your-data-move"></a><span data-ttu-id="f0c5f-103">データ移行をリクエストする方法</span><span class="sxs-lookup"><span data-stu-id="f0c5f-103">How to request your data move</span></span>

> [!NOTE]
> <span data-ttu-id="f0c5f-104">このページの情報は、geo で新しいデータセンターを開始する前に、既存の Microsoft 365 テナントを持っているお客様にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-104">The information on this page only applies to customers who had existing Microsoft 365 tenants before the new datacenters in their geo launched.</span></span> <span data-ttu-id="f0c5f-105">移行の適格性は、特定のワークロードプロビジョニングの日付にも依存しているため、テナントの作成日は常に重要な1つの日付になるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-105">Migration eligibility also depends on the specific workload provisioning date, so tenant creation date may not always be the single date that matters.</span></span>
  
<span data-ttu-id="f0c5f-106">既存の Microsoft 365 お客様は、組織の主要な顧客データ全体の移行を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-106">Existing Microsoft 365 customers are eligible to request migration for their entire organization’s core customer data at rest.</span></span>  
  
## <a name="when-can-i-request-a-move"></a><span data-ttu-id="f0c5f-107">いつ移行をリクエストできますか?</span><span class="sxs-lookup"><span data-stu-id="f0c5f-107">When can I request a move?</span></span>

|<span data-ttu-id="f0c5f-108">**国がサインアップしているお客様**</span><span class="sxs-lookup"><span data-stu-id="f0c5f-108">**Customers with signup country in**</span></span>|<span data-ttu-id="f0c5f-109">**リクエスト期間の開始**</span><span class="sxs-lookup"><span data-stu-id="f0c5f-109">**Request period begins**</span></span>|<span data-ttu-id="f0c5f-110">**リクエストの期限**</span><span class="sxs-lookup"><span data-stu-id="f0c5f-110">**Request deadline**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f0c5f-111">日本</span><span class="sxs-lookup"><span data-stu-id="f0c5f-111">Japan</span></span>  <br/> |<span data-ttu-id="f0c5f-112">2020年1月1日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-112">January 1, 2020</span></span>  <br/> |<span data-ttu-id="f0c5f-113">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-113">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="f0c5f-114">オーストラリア、ニュージーランド、フィジー</span><span class="sxs-lookup"><span data-stu-id="f0c5f-114">Australia, New Zealand, Fiji</span></span>  <br/> |<span data-ttu-id="f0c5f-115">2020年1月1日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-115">January 1, 2020</span></span>  <br/> |<span data-ttu-id="f0c5f-116">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-116">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="f0c5f-117">インド</span><span class="sxs-lookup"><span data-stu-id="f0c5f-117">India</span></span>  <br/> |<span data-ttu-id="f0c5f-118">2020年1月1日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-118">January 1, 2020</span></span>  <br/> |<span data-ttu-id="f0c5f-119">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-119">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="f0c5f-120">カナダ</span><span class="sxs-lookup"><span data-stu-id="f0c5f-120">Canada</span></span>  <br/> |<span data-ttu-id="f0c5f-121">2020年1月1日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-121">January 1, 2020</span></span>  <br/> |<span data-ttu-id="f0c5f-122">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-122">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="f0c5f-123">英国</span><span class="sxs-lookup"><span data-stu-id="f0c5f-123">United Kingdom</span></span>  <br/> |<span data-ttu-id="f0c5f-124">2020年1月1日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-124">January 1, 2020</span></span>  <br/> |<span data-ttu-id="f0c5f-125">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-125">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="f0c5f-126">韓国</span><span class="sxs-lookup"><span data-stu-id="f0c5f-126">South Korea</span></span>  <br/> |<span data-ttu-id="f0c5f-127">2020年1月1日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-127">January 1, 2020</span></span>  <br/> |<span data-ttu-id="f0c5f-128">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-128">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="f0c5f-129">フランス</span><span class="sxs-lookup"><span data-stu-id="f0c5f-129">France</span></span>  <br/> |<span data-ttu-id="f0c5f-130">2020年1月1日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-130">January 1, 2020</span></span>  <br/> |<span data-ttu-id="f0c5f-131">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-131">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="f0c5f-132">アラブ首長国連邦</span><span class="sxs-lookup"><span data-stu-id="f0c5f-132">United Arab Emirates</span></span>  <br/> |<span data-ttu-id="f0c5f-133">2019 年 7 月 15 日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-133">July 15, 2019</span></span>  <br/> |<span data-ttu-id="f0c5f-134">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-134">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="f0c5f-135">南アフリカ</span><span class="sxs-lookup"><span data-stu-id="f0c5f-135">South Africa</span></span>  <br/> |<span data-ttu-id="f0c5f-136">2019 年 7 月 25 日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-136">July 25, 2019</span></span>  <br/> |<span data-ttu-id="f0c5f-137">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-137">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="f0c5f-138">スイス、リヒテンシュタイン</span><span class="sxs-lookup"><span data-stu-id="f0c5f-138">Switzerland, Liechtenstein</span></span>  <br/> |<span data-ttu-id="f0c5f-139">2019 年 12 月 10 日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-139">December 10, 2019</span></span>  <br/> |<span data-ttu-id="f0c5f-140">2020 年 6 月 30 日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-140">June 30, 2020</span></span>  <br/> |
|<span data-ttu-id="f0c5f-141">ノルウェー</span><span class="sxs-lookup"><span data-stu-id="f0c5f-141">Norway</span></span>  <br/> |<span data-ttu-id="f0c5f-142">2020 年 4 月 15 日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-142">April 15, 2020</span></span>  <br/> |<span data-ttu-id="f0c5f-143">2020年10月31日</span><span class="sxs-lookup"><span data-stu-id="f0c5f-143">October 31, 2020</span></span>  <br/> |
|<span data-ttu-id="f0c5f-144">ドイツ</span><span class="sxs-lookup"><span data-stu-id="f0c5f-144">Germany</span></span>  <br/> |<span data-ttu-id="f0c5f-145">計画</span><span class="sxs-lookup"><span data-stu-id="f0c5f-145">Planned</span></span>  <br/> |<span data-ttu-id="f0c5f-146">計画</span><span class="sxs-lookup"><span data-stu-id="f0c5f-146">Planned</span></span>  <br/> |

## <a name="how-to-request-a-move"></a><span data-ttu-id="f0c5f-147">移行をリクエストする方法</span><span class="sxs-lookup"><span data-stu-id="f0c5f-147">How to request a move</span></span>

<span data-ttu-id="f0c5f-148">対象となるお客様には、 [Microsoft 365 管理センター](https://aka.ms/365admin)にページが表示されます。これにより、お客様は自社のコア顧客データを新しいデータセンターリージョンに移動するよう要求できます。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-148">Eligible customers will see a page in the [Microsoft 365 admin center](https://aka.ms/365admin), which will allow them to request to have their core customer data moved to their new datacenter region.</span></span>  
  
<span data-ttu-id="f0c5f-149">Microsoft 365 管理センターのページにアクセスするには、左側のナビゲーションウィンドウで [ **設定**] を展開し、[ **組織の設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-149">To access the page in the Microsoft 365 admin center, in the navigation pane on the left, expand **Settings**, and then click **Org Settings**.</span></span>
<span data-ttu-id="f0c5f-150">Tab **組織プロファイル**を選択して、[ **Data レジデンシー**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-150">Select the tab **Organization profile**, then select the option **Data residency**.</span></span>
  
<span data-ttu-id="f0c5f-151">このセクションは、テナントが Microsoft 365 引っ越しプログラムの対象外である場合には表示されません。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-151">You will not see this section if your tenant is not eligible for the Microsoft 365 Move Program.</span></span>  <span data-ttu-id="f0c5f-152">データ常駐の要件があり、移行を要求する必要がある組織の場合は、チェックボックスをオンにして、 **保存**します。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-152">If your organization has data residency requirements and you need to request migration, mark the checkbox and then **Save**.</span></span>
  
![データセンターのオプトイン操作画面](../media/dataresidencyflyoutae.jpg)
  
<span data-ttu-id="f0c5f-154">「 **Data レジデンシー** 」セクションのテキストが、組織が適切な国および日付に **データを移動するように要求** したことを示すように変化することを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-154">You should see the text on the **Data residency** section change to indicate **Your organization has requested to move its data** to the appropriate country and date.</span></span> <span data-ttu-id="f0c5f-155">メッセージ センターにも確認メッセージが届きます。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-155">You'll also have a confirmation message in your message center.</span></span> <span data-ttu-id="f0c5f-156">これにより、移行が正常にリクエストされたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-156">This confirms that you have successfully requested a move.</span></span> 


  
## <a name="what-happens-after-requesting-a-move"></a><span data-ttu-id="f0c5f-157">移行をリクエストした後はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="f0c5f-157">What happens after requesting a move?</span></span>

<span data-ttu-id="f0c5f-158">移行をリクエストした後、運用上の制約が許容されるように、をすばやく移行することを計画します。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-158">After requesting a move, we will plan to move you as quickly as our operational constraints allow.</span></span> <span data-ttu-id="f0c5f-159">予測不可能な性質の制約が数多くあるため、移行が実施される特定の日付や時間帯を共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-159">Due to the unpredictable nature of many of the constraints, we cannot share a specific date or timeframe for the moves.</span></span> <span data-ttu-id="f0c5f-160">お客様のテナントの管理者は、各サービスの移行が完了した後で、メッセージセンターに通知が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-160">Customer tenant administrators will see a notification in Message Center after the move for each service has completed.</span></span>
  
<span data-ttu-id="f0c5f-161">移行を完了するには、お住まいの国のリクエストの期限から最大 24 か月かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-161">Moves may take up to 24 months from the request deadline for your country to complete.</span></span>
  
## <a name="microsoft-teams"></a><span data-ttu-id="f0c5f-162">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f0c5f-162">Microsoft Teams</span></span>

<span data-ttu-id="f0c5f-163">2020年1月の間、対象となる Office 365 諸国のお客様は、Microsoft Teams chat service データの移行をオプトインできます。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-163">As of January 2020, customers in eligible Office 365 countries can opt-in for migration of Microsoft Teams chat service data.</span></span>  <span data-ttu-id="f0c5f-164">オプトインタイムラインは、対象となるすべての国に対して再オープンまたは拡張されています。これにより、お客様は、範囲内の Microsoft Teams で移行プログラムを検討する機会を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-164">Opt-in timelines have been reopened or extended for all eligible countries to give customers an opportunity to consider the migration program with Microsoft Teams in scope.</span></span> <span data-ttu-id="f0c5f-165">データ常駐移行のために以前にオプトインされていたお客様は、Teams をローカルデータセンター geo に移行することもできます。これらのお客様には、追加の作業は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f0c5f-165">Customers that previously opted-in for a Data Residency move will also have Teams move to their local datacenter geo, no additional action is required from these customers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f0c5f-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="f0c5f-166">Related topics</span></span>

[<span data-ttu-id="f0c5f-167">コア データを新しい Office 365 データ センター geo に移行する</span><span class="sxs-lookup"><span data-stu-id="f0c5f-167">Moving core data to new Office 365 datacenter geos</span></span>](moving-data-to-new-datacenter-geos.md)

[<span data-ttu-id="f0c5f-168">データ移行についての一般的な FAQ</span><span class="sxs-lookup"><span data-stu-id="f0c5f-168">Data move general FAQ</span></span>](data-move-faq.md)

[<span data-ttu-id="f0c5f-169">Microsoft Dynamics CRM Online の新しいデータ センター geo</span><span class="sxs-lookup"><span data-stu-id="f0c5f-169">New datacenter geos for Microsoft Dynamics CRM Online</span></span>](https://go.microsoft.com/fwlink/p/?Linkid=615924)
  
[<span data-ttu-id="f0c5f-170">Azure のリージョン</span><span class="sxs-lookup"><span data-stu-id="f0c5f-170">Azure services by region</span></span>](https://azure.microsoft.com/regions/)
  

