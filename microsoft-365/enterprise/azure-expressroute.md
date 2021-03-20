---
title: Office 365 向け Azure ExpressRoute
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/5/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 6d2534a2-c19c-4a99-be5e-33a0cee5d3bd
description: Azure ExpressRoute を 365 で使用Office、展開する場合はネットワーク実装プロジェクトを計画する方法について説明します。
ms.openlocfilehash: 7e44feefd375088d2fef36c7e7859e242c1a30aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905358"
---
# <a name="azure-expressroute-for-office-365"></a><span data-ttu-id="169db-103">Office 365 向け Azure ExpressRoute</span><span class="sxs-lookup"><span data-stu-id="169db-103">Azure ExpressRoute for Office 365</span></span>

<span data-ttu-id="169db-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="169db-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="169db-105">Office 365 で Azure ExpressRoute を使用する方法と、Azure ExpressRoute を Office 365 で使用する場合に必要となるネットワーク実装プロジェクトを計画する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="169db-105">Learn how Azure ExpressRoute is used with Office 365 and how to plan the network implementation project that will be required if you are deploying Azure ExpressRoute for use with Office 365.</span></span> <span data-ttu-id="169db-106">Azure で実行されるインフラストラクチャサービスとプラットフォーム サービスは、多くの場合、ネットワーク アーキテクチャとパフォーマンスに関する考慮事項に対処することでメリットがあります。</span><span class="sxs-lookup"><span data-stu-id="169db-106">Infrastructure and platform services running in Azure will often benefit by addressing network architecture and performance considerations.</span></span> <span data-ttu-id="169db-107">このような場合は、ExpressRoute for Azure をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="169db-107">We recommend ExpressRoute for Azure in these cases.</span></span> <span data-ttu-id="169db-108">Office 365 や Dynamics 365 などのサービス製品は、インターネット経由で安全かつ確実にアクセスするために構築されています。</span><span class="sxs-lookup"><span data-stu-id="169db-108">Software as a Service offerings like Office 365 and Dynamics 365 have been built to be accessed securely and reliably via the Internet.</span></span> <span data-ttu-id="169db-109">インターネットのパフォーマンスとセキュリティについて、また、Azure ExpressRoute for Office 365 について検討する場合は [、「365](assessing-network-connectivity.md)ネットワーク接続の評価Office参照してください。</span><span class="sxs-lookup"><span data-stu-id="169db-109">You can read about Internet performance and security and when you might consider Azure ExpressRoute for Office 365 in the article [Assessing Office 365 network connectivity](assessing-network-connectivity.md).</span></span>

> [!NOTE]
> <span data-ttu-id="169db-110">Microsoft の承認は、ExpressRoute を 365 にOfficeです。</span><span class="sxs-lookup"><span data-stu-id="169db-110">Microsoft authorization is required to use ExpressRoute for Office 365.</span></span> <span data-ttu-id="169db-111">Microsoft は、お客様の規制要件に直接接続が義務付Office場合、すべての顧客要求を確認し、ExpressRoute に対して 365 回の使用を承認します。</span><span class="sxs-lookup"><span data-stu-id="169db-111">Microsoft reviews every customer request and authorizes ExpressRoute for Office 365 usage when a customer's regulatory requirement mandates direct connectivity.</span></span> <span data-ttu-id="169db-112">そのような要件がある場合は、Microsoft のレビューを開始するために [、ExpressRoute for Office 365 Request Form](https://aka.ms/O365ERReview) で直接接続が必要と解釈される規制へのテキスト抜粋と Web リンクを提供してください。</span><span class="sxs-lookup"><span data-stu-id="169db-112">If you have such requirements, please provide the text excerpt and web link to the regulation which you interpret to mean that direct connectivity is required in the [ExpressRoute for Office 365 Request Form](https://aka.ms/O365ERReview) to begin a Microsoft review.</span></span> <span data-ttu-id="169db-113">365 のルート フィルターを作成しようとしている未承認のサブスクリプションOfficeエラー メッセージが [表示されます](https://support.microsoft.com/kb/3181709)。</span><span class="sxs-lookup"><span data-stu-id="169db-113">Unauthorized subscriptions trying to create route filters for Office 365 will receive an [error message](https://support.microsoft.com/kb/3181709).</span></span>

<span data-ttu-id="169db-114">これで、選択した 365 ネットワーク トラフィックOffice 365 にOffice追加できます。</span><span class="sxs-lookup"><span data-stu-id="169db-114">You can now add a direct network connection to Office 365 for selected Office 365 network traffic.</span></span> <span data-ttu-id="169db-115">Azure ExpressRoute は直接接続、予測可能なパフォーマンスを提供し、Microsoft ネットワーク コンポーネントのアップタイム SLA は 99.95% です。</span><span class="sxs-lookup"><span data-stu-id="169db-115">Azure ExpressRoute offers a direct connection, predictable performance, and comes with an uptime SLA of 99.95% for the Microsoft networking components.</span></span> <span data-ttu-id="169db-116">Azure ExpressRoute でサポートされていないサービスには、引き続きインターネット接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="169db-116">You'll still require an internet connection for services that aren't supported over Azure ExpressRoute.</span></span>

## <a name="planning-azure-expressroute-for-office-365"></a><span data-ttu-id="169db-117">Azure ExpressRoute for Office 365</span><span class="sxs-lookup"><span data-stu-id="169db-117">Planning Azure ExpressRoute for Office 365</span></span>

<span data-ttu-id="169db-118">インターネット接続に加えて、予測可能性と Microsoft ネットワーク コンポーネントの 99.95% のアップタイム SLA を提供する直接接続を通して、Office 365 ネットワーク トラフィックのサブセットをルーティングすることができます。</span><span class="sxs-lookup"><span data-stu-id="169db-118">In addition to internet connectivity, you may choose to route a subset of their Office 365 network traffic over a direct connection that offers predictability and a 99.95% uptime SLA for the Microsoft networking components.</span></span> <span data-ttu-id="169db-119">Azure ExpressRoute は、365 および他の Microsoft クラウド サービスOffice専用のネットワーク接続を提供します。</span><span class="sxs-lookup"><span data-stu-id="169db-119">Azure ExpressRoute provides you with this dedicated network connection to Office 365 and other Microsoft cloud services.</span></span>

<span data-ttu-id="169db-120">既存の MPLS WAN を持っているかどうかに関係なく、ExpressRoute は 3 つの方法の 1 つでネットワーク アーキテクチャに追加できます。は、サポートされているクラウド交換の共同場所プロバイダー、イーサネット ポイント間接続プロバイダー、または MPLS 接続プロバイダーを介して行います。</span><span class="sxs-lookup"><span data-stu-id="169db-120">Regardless of whether you have an existing MPLS WAN, ExpressRoute can be added to your network architecture in one of three ways; through a supported cloud exchange co-location provider, an Ethernet point-to-point connection provider, or through an MPLS connection provider.</span></span> <span data-ttu-id="169db-121">地域 [で利用できるプロバイダーを確認します](/azure/expressroute/expressroute-locations)。</span><span class="sxs-lookup"><span data-stu-id="169db-121">See what [providers are available in your region](/azure/expressroute/expressroute-locations).</span></span> <span data-ttu-id="169db-122">直接 ExpressRoute 接続を使用すると、「What [Office 365 サービスが含まれているか」で説明されているアプリケーションへの接続が可能](azure-expressroute.md#BKMK_WhatDoIGet) になります。</span><span class="sxs-lookup"><span data-stu-id="169db-122">The direct ExpressRoute connection will enable connectivity to the applications outlined in [What Office 365 services are included?](azure-expressroute.md#BKMK_WhatDoIGet) below.</span></span> <span data-ttu-id="169db-123">他のすべてのアプリケーションとサービスのネットワーク トラフィックは、引き続きインターネットを通過します。</span><span class="sxs-lookup"><span data-stu-id="169db-123">Network traffic for all other applications and services will continue to traverse the internet.</span></span>

<span data-ttu-id="169db-124">Office 365、Windows Update、TechNet などのすべての Microsoft アプリケーションにアクセスするために、インターネットを通して Microsoft のデータセンターに接続する一般的な Office 365 のお客様を示す、次の高レベルネットワーク図を検討してください。</span><span class="sxs-lookup"><span data-stu-id="169db-124">Consider the following high level network diagram which shows a typical Office 365 customer connecting to Microsoft's datacenters over the internet for access to all Microsoft applications such as Office 365, Windows Update, and TechNet.</span></span> <span data-ttu-id="169db-125">顧客は、オンプレミス ネットワークから接続しているか、独立したインターネット接続から接続しているかに関係なく、同様のネットワーク パスを使用します。</span><span class="sxs-lookup"><span data-stu-id="169db-125">Customers use a similar network path regardless of whether they're connecting from an on-premises network or from an independent internet connection.</span></span>

![Office 365 ネットワーク接続](../media/9d8bc622-4a38-4a3b-a0f3-68657712d460.png)

<span data-ttu-id="169db-127">次に、インターネットと ExpressRoute の両方を使用して 365 に接続する Office 365 の顧客を示す更新されたOfficeします。</span><span class="sxs-lookup"><span data-stu-id="169db-127">Now look at the updated diagram which depicts an Office 365 customer who uses both the internet and ExpressRoute to connect to Office 365.</span></span> <span data-ttu-id="169db-128">パブリック DNS ノードやコンテンツ配信ネットワーク ノードなどの一部の接続では、引き続きパブリック インターネット接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="169db-128">Notice that some connections such as Public DNS and Content Delivery Network nodes still require the public internet connection.</span></span> <span data-ttu-id="169db-129">また、ExpressRoute 接続ビル内に位置していないお客様のユーザーがインターネットを通じて接続している場合にも注意してください。</span><span class="sxs-lookup"><span data-stu-id="169db-129">Also notice the customer's users who are not located in their ExpressRoute connected building are connecting over the Internet.</span></span>

![Office 365 接続と ExpressRoute](../media/251788c4-0937-4584-9b2c-df08e11611fc.png)

<span data-ttu-id="169db-131">さらに詳しい情報が必要ですか?</span><span class="sxs-lookup"><span data-stu-id="169db-131">Still want more information?</span></span> <span data-ttu-id="169db-132">Azure ExpressRoute for [Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) でネットワーク トラフィックを管理する方法と、Azure ExpressRoute for Office [365](/azure/expressroute/expressroute-faqs)について説明します。</span><span class="sxs-lookup"><span data-stu-id="169db-132">Learn how to [manage your network traffic with Azure ExpressRoute for Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) and learn how to [configure Azure ExpressRoute for Office 365](/azure/expressroute/expressroute-faqs).</span></span> <span data-ttu-id="169db-133">また、チャネル 9 の Office [365 トレーニング](https://channel9.msdn.com/series/aer) シリーズ用の 10 パーツの Azure ExpressRoute を記録し、概念の詳細な説明を行いました。</span><span class="sxs-lookup"><span data-stu-id="169db-133">We've also recorded a 10 part [Azure ExpressRoute for Office 365 Training](https://channel9.msdn.com/series/aer) series on Channel 9 to help explain the concepts more thoroughly.</span></span>

## <a name="what-office-365-services-are-included"></a><span data-ttu-id="169db-134">365 Officeには何が含まれていますか?</span><span class="sxs-lookup"><span data-stu-id="169db-134">What Office 365 services are included?</span></span>
<span data-ttu-id="169db-135"><a name="BKMK_WhatDoIGet"> </a></span><span class="sxs-lookup"><span data-stu-id="169db-135"><a name="BKMK_WhatDoIGet"> </a></span></span>

<span data-ttu-id="169db-136">次の表に、ExpressRoute でOfficeされている 365 サービスの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="169db-136">The following table lists the Office 365 services that are supported over ExpressRoute.</span></span> <span data-ttu-id="169db-137">これらのアプリケーションに [対するOfficeインターネット](./urls-and-ip-address-ranges.md) 接続が必要なネットワーク要求を理解するには、365 エンドポイントに関する記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="169db-137">Please review the [Office 365 endpoints article](./urls-and-ip-address-ranges.md) to understand which network requests for these applications require internet connectivity.</span></span>

|<span data-ttu-id="169db-138">**含まれるアプリケーション**</span><span class="sxs-lookup"><span data-stu-id="169db-138">**Applications included**</span></span>|
|:-----|
|<span data-ttu-id="169db-139">Exchange Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="169db-139">Exchange Online<sup>1</sup></span></span> <br/> <span data-ttu-id="169db-140">Exchange Online Protection<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="169db-140">Exchange Online Protection<sup>1</sup></span></span> <br/> <span data-ttu-id="169db-141">Delve<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="169db-141">Delve<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="169db-142">Skype for Business Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="169db-142">Skype for Business Online<sup>1</sup></span></span> <br/> <span data-ttu-id="169db-143">Microsoft Teams <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="169db-143">Microsoft Teams <sup>1</sup></span></span> <br/> |
|<span data-ttu-id="169db-144">SharePoint Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="169db-144">SharePoint Online<sup>1</sup></span></span> <br/> <span data-ttu-id="169db-145">OneDrive for Business<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="169db-145">OneDrive for Business<sup>1</sup></span></span> <br/> <span data-ttu-id="169db-146">Project Online<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="169db-146">Project Online<sup>1</sup></span></span> <br/> |
|<span data-ttu-id="169db-147">ポータルと共有<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="169db-147">Portal and shared<sup>1</sup></span></span> <br/> <span data-ttu-id="169db-148">Azure Active Directory (Azure AD) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="169db-148">Azure Active Directory (Azure AD) <sup>1</sup></span></span> <br/> <span data-ttu-id="169db-149">Azure AD接続<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="169db-149">Azure AD Connect<sup>1</sup></span></span> <br/> <span data-ttu-id="169db-150">Office<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="169db-150">Office<sup>1</sup></span></span> <br/> |

<span data-ttu-id="169db-151"><sup>1</sup> これらの各アプリケーションには、ExpressRoute でサポートされていないインターネット接続要件があります。詳細については、「Office [365 エンドポイント](./urls-and-ip-address-ranges.md) 」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="169db-151"><sup>1</sup> Each of these applications have internet connectivity requirements not supported over ExpressRoute, see the [Office 365 endpoints article](./urls-and-ip-address-ranges.md) for more information.</span></span>

<span data-ttu-id="169db-152">Office 365 の ExpressRoute に含まれていないサービスは、Microsoft 365 Apps for enterprise クライアント ダウンロード、オンプレミス ID プロバイダー サインイン、および中国の Office 365 (21 Vianet が運営) サービスです。</span><span class="sxs-lookup"><span data-stu-id="169db-152">The services that aren't included with ExpressRoute for Office 365 are Microsoft 365 Apps for enterprise client downloads, On-premises Identity Provider Sign-In, and Office 365 (operated by 21 Vianet) service in China.</span></span>

## <a name="implementing-expressroute-for-office-365"></a><span data-ttu-id="169db-153">Office 365 向け ExpressRoute の実装</span><span class="sxs-lookup"><span data-stu-id="169db-153">Implementing ExpressRoute for Office 365</span></span>

<span data-ttu-id="169db-154">ExpressRoute を実装するには、ネットワークとアプリケーションの所有者の関与が必要であり、新しい[](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)ネットワーク ルーティング アーキテクチャ、帯域幅要件、セキュリティの実装場所、高可用性などについて慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="169db-154">Implementing ExpressRoute requires the involvement of network and application owners and requires careful planning to determine the new [network routing architecture](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408), bandwidth requirements, where security will be implemented, high availability, and so on.</span></span> <span data-ttu-id="169db-155">ExpressRoute を実装するには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="169db-155">To implement ExpressRoute, you'll need to:</span></span>

1. <span data-ttu-id="169db-156">ExpressRoute が 365 の接続計画で満たす必要Office十分に理解します。</span><span class="sxs-lookup"><span data-stu-id="169db-156">Fully understand the need ExpressRoute satisfies in your Office 365 connectivity planning.</span></span> <span data-ttu-id="169db-157">インターネットまたは ExpressRoute を使用するアプリケーションを理解し、Office 365 トラフィックに対してインターネットと ExpressRoute の両方を使用するコンテキストで、ネットワーク容量、セキュリティ、高可用性のニーズを完全に計画します。</span><span class="sxs-lookup"><span data-stu-id="169db-157">Understand what applications will use the internet or ExpressRoute and fully plan your network capacity, security, and high availability needs in the context of using both the internet and ExpressRoute for Office 365 traffic.</span></span>

2. <span data-ttu-id="169db-158">インターネットトラフィックと ExpressRoute トラフィック 1 の両方の出力とピアリングの場所を<sup>決定します</sup>。</span><span class="sxs-lookup"><span data-stu-id="169db-158">Determine the egress and peering locations for both internet and ExpressRoute traffic<sup>1</sup>.</span></span>

3. <span data-ttu-id="169db-159">インターネット接続と ExpressRoute 接続で必要な容量を決定します。</span><span class="sxs-lookup"><span data-stu-id="169db-159">Determine the capacity required on the internet and ExpressRoute connections.</span></span>

4. <span data-ttu-id="169db-160">セキュリティおよび他の標準境界コントロール 1 を実装するための計画を<sup>立てます</sup>。</span><span class="sxs-lookup"><span data-stu-id="169db-160">Have a plan in place for implementing security and other standard perimeter controls<sup>1</sup>.</span></span>

5. <span data-ttu-id="169db-161">ExpressRoute をサブスクライブする有効な Microsoft Azure アカウントを持っている。</span><span class="sxs-lookup"><span data-stu-id="169db-161">Have a valid Microsoft Azure account to subscribe to ExpressRoute.</span></span>

6. <span data-ttu-id="169db-162">接続モデルと承認済みプロバイダー [を選択します](/azure/expressroute/expressroute-locations)。</span><span class="sxs-lookup"><span data-stu-id="169db-162">Select a connectivity model and an [approved provider](/azure/expressroute/expressroute-locations).</span></span> <span data-ttu-id="169db-163">顧客は複数の接続モデルまたはパートナーを選択できます。パートナーは既存のネットワーク プロバイダーと同じである必要はなかっています。</span><span class="sxs-lookup"><span data-stu-id="169db-163">Keep in mind, customers can select multiple connectivity models or partners and the partner doesn't need to be the same as your existing network provider.</span></span>

7. <span data-ttu-id="169db-164">ExpressRoute にトラフィックを送信する前に展開を検証します。</span><span class="sxs-lookup"><span data-stu-id="169db-164">Validate deployment prior to directing traffic to ExpressRoute.</span></span>

8. <span data-ttu-id="169db-165">必要に応 [じて QoS を実装し](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) 、地域の拡張を評価します。</span><span class="sxs-lookup"><span data-stu-id="169db-165">Optionally [implement QoS](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) and evaluate regional expansion.</span></span>

<span data-ttu-id="169db-166"><sup>1</sup> 重要なパフォーマンスに関する考慮事項。</span><span class="sxs-lookup"><span data-stu-id="169db-166"><sup>1</sup> Important performance considerations.</span></span> <span data-ttu-id="169db-167">ここでの決定は、Skype for Business などのアプリケーションにとって重要な遅延に大きな影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="169db-167">Decisions here can dramatically impact latency which is a critical for applications such as Skype for Business.</span></span>

<span data-ttu-id="169db-168">その他の参照については、ExpressRoute [のドキュメントに加えて](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) 、ルーティング ガイド [を使用してください](/azure/expressroute/expressroute-introduction)。</span><span class="sxs-lookup"><span data-stu-id="169db-168">For additional references, use our [routing guide](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) in addition to the [ExpressRoute documentation](/azure/expressroute/expressroute-introduction).</span></span>

<span data-ttu-id="169db-169">Office 365 用の ExpressRoute を購入するには、1 つ以上の承認済[](/azure/expressroute/expressroute-locations)みプロバイダーと作業して、ExpressRoute Premium サブスクリプションで必要な数とサイズの回線をプロビジョニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="169db-169">To purchase ExpressRoute for Office 365, you'll need to work with one or more [approved providers](/azure/expressroute/expressroute-locations) to provision the desired number and size circuits with an ExpressRoute Premium subscription.</span></span> <span data-ttu-id="169db-170">365 から購入する追加のOfficeはありません。</span><span class="sxs-lookup"><span data-stu-id="169db-170">There are no additional licenses to purchase from Office 365.</span></span>

<span data-ttu-id="169db-171">ここに戻る場合は、次の短いリンクをご利用ください: [https://aka.ms/expressrouteoffice365]()</span><span class="sxs-lookup"><span data-stu-id="169db-171">Here's a short link you can use to come back: [https://aka.ms/expressrouteoffice365]()</span></span>

<span data-ttu-id="169db-172">ExpressRoute for Office [365 にサインアップする準備ができましたか](https://aka.ms/ert)?</span><span class="sxs-lookup"><span data-stu-id="169db-172">Ready to sign-up for [ExpressRoute for Office 365](https://aka.ms/ert)?</span></span>

## <a name="related-topics"></a><span data-ttu-id="169db-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="169db-173">Related Topics</span></span>

[<span data-ttu-id="169db-174">Office 365 ネットワーク接続の評価</span><span class="sxs-lookup"><span data-stu-id="169db-174">Assessing Office 365 network connectivity</span></span>](assessing-network-connectivity.md)

[<span data-ttu-id="169db-175">Office 365 向け ExpressRoute の管理</span><span class="sxs-lookup"><span data-stu-id="169db-175">Managing ExpressRoute for Office 365 connectivity</span></span>](managing-expressroute-for-connectivity.md)

[<span data-ttu-id="169db-176">Office 365 向け ExpressRoute でのルーティング</span><span class="sxs-lookup"><span data-stu-id="169db-176">Routing with ExpressRoute for Office 365</span></span>](routing-with-expressroute.md)

[<span data-ttu-id="169db-177">Office 365 向け ExpressRoute でのネットワーク計画</span><span class="sxs-lookup"><span data-stu-id="169db-177">Network planning with ExpressRoute for Office 365</span></span>](network-planning-with-expressroute.md)

[<span data-ttu-id="169db-178">Office 365 向け ExpressRoute の実装</span><span class="sxs-lookup"><span data-stu-id="169db-178">Implementing ExpressRoute for Office 365</span></span>](implementing-expressroute.md)

[<span data-ttu-id="169db-179">ExpressRoute での BGP コミュニティの 365 Office使用する</span><span class="sxs-lookup"><span data-stu-id="169db-179">Using BGP communities in ExpressRoute for Office 365 scenarios</span></span>](bgp-communities-in-expressroute.md)

[<span data-ttu-id="169db-180">Skype for Business Online でのメディア品質とネットワーク接続のパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="169db-180">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)

[<span data-ttu-id="169db-181">ベースラインとパフォーマンス履歴を使用した、Office 365 のパフォーマンスのチューニング</span><span class="sxs-lookup"><span data-stu-id="169db-181">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)

[<span data-ttu-id="169db-182">Office 365 のパフォーマンスに関するトラブルシューティングの計画</span><span class="sxs-lookup"><span data-stu-id="169db-182">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)

[<span data-ttu-id="169db-183">Office 365 の URL および IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="169db-183">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="169db-184">Office 365 のネットワークとパフォーマンスのチューニング</span><span class="sxs-lookup"><span data-stu-id="169db-184">Office 365 network and performance tuning</span></span>](network-planning-and-performance.md)

## <a name="see-also"></a><span data-ttu-id="169db-185">関連項目</span><span class="sxs-lookup"><span data-stu-id="169db-185">See also</span></span>

[<span data-ttu-id="169db-186">Microsoft 365 Enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="169db-186">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)