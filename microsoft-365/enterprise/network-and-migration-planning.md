---
title: Office 365 のネットワークと移行の計画
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
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
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: この記事には、ネットワークの計画、テスト、および移行に関する情報へのリンクが含Office 365。
ms.openlocfilehash: 99bcc1bd0447b192860fc0bcc67fc18d87c2d5fc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923590"
---
# <a name="network-and-migration-planning-for-office-365"></a><span data-ttu-id="dc57c-103">Office 365 のネットワークと移行の計画</span><span class="sxs-lookup"><span data-stu-id="dc57c-103">Network and migration planning for Office 365</span></span>

<span data-ttu-id="dc57c-104">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="dc57c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="dc57c-105">この記事では、ネットワークの計画とテスト、およびネットワークへの移行に関する情報へのOffice 365。</span><span class="sxs-lookup"><span data-stu-id="dc57c-105">This article contains links to information about network planning and testing, and migration to Office 365.</span></span>
  
<span data-ttu-id="dc57c-106">初めて展開するか、Office 365 に移行する前に、これらのトピックの情報を使用して必要な帯域幅を見積もり、Office 365 に展開または移行するのに十分な帯域幅をテストして確認できます。</span><span class="sxs-lookup"><span data-stu-id="dc57c-106">Before you deploy for the first time or migrate to Office 365, you can use the information in these topics to estimate the bandwidth you need and then to test and verify that you have enough bandwidth to deploy or migrate to Office 365.</span></span>

<span data-ttu-id="dc57c-107">この記事は、ネットワークの計画と[パフォーマンスの調整](./network-planning-and-performance.md)の一部Office 365。</span><span class="sxs-lookup"><span data-stu-id="dc57c-107">This article is part of [Network planning and performance tuning for Office 365](./network-planning-and-performance.md).</span></span>

<span data-ttu-id="dc57c-108">Microsoft Cloud Networking for Microsoft 365およびサービス向けネットワークを最適化する手順については[、「Microsoft Cloud Networking for microsoft Cloud Networking for Enterprise」を参照](../solutions/cloud-architecture-models.md)してください。</span><span class="sxs-lookup"><span data-stu-id="dc57c-108">For the steps to optimize your network for Microsoft 365 and other Microsoft cloud platforms and services, see the [Microsoft Cloud Networking for Enterprise Architects](../solutions/cloud-architecture-models.md) poster.</span></span>
   
## <a name="estimate-network-bandwidth-requirements"></a><span data-ttu-id="dc57c-109">ネットワーク帯域幅の要件の見積もり</span><span class="sxs-lookup"><span data-stu-id="dc57c-109">Estimate network bandwidth requirements</span></span>
<span data-ttu-id="dc57c-110"><a name="EstimateBandwidthRequirements"> </a></span><span class="sxs-lookup"><span data-stu-id="dc57c-110"><a name="EstimateBandwidthRequirements"> </a></span></span>

<span data-ttu-id="dc57c-111">このOffice 365使用すると、組織のインターネット回線の使用率が向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc57c-111">Using Office 365 may increase the utilization of your organization's internet circuit.</span></span> <span data-ttu-id="dc57c-112">現在利用可能な帯域幅の量が、Office 365 が完全に展開された後、最も多くの日を処理するために少なくとも 20% の容量を残しながら、予想される増加を処理するのに十分かどうかを判断することが重要です。</span><span class="sxs-lookup"><span data-stu-id="dc57c-112">It's important to determine if the amount of bandwidth currently available is enough to handle the estimated increase once Office 365 is fully deployed while leaving at least 20% capacity to handle the busiest of days.</span></span>
  
<span data-ttu-id="dc57c-113">帯域幅を推定するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="dc57c-113">To estimate the bandwidth, use the following steps:</span></span>
  
1. <span data-ttu-id="dc57c-114">各インターネット出力を使用するクライアントの数を評価します。</span><span class="sxs-lookup"><span data-stu-id="dc57c-114">Assess the number of clients that will use each Internet egress.</span></span> <span data-ttu-id="dc57c-115">マルチテラビット ネットワークで可能な限り多くの接続を処理します。</span><span class="sxs-lookup"><span data-stu-id="dc57c-115">Let our multi-terabit network handle as much of the connection as possible.</span></span> 
    
2. <span data-ttu-id="dc57c-116">クライアントがOffice 365するサービスと機能を決定します。</span><span class="sxs-lookup"><span data-stu-id="dc57c-116">Determine which Office 365 services and features will be available for clients to use.</span></span> <span data-ttu-id="dc57c-117">サービスや利用状況プロファイルが異なるユーザーのグループがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc57c-117">You will likely have groups of people with different services or usage profiles.</span></span>
    
3. <span data-ttu-id="dc57c-118">クライアントのパイロット グループのネットワーク使用を測定します。</span><span class="sxs-lookup"><span data-stu-id="dc57c-118">Measure the network use for a pilot group of clients.</span></span> <span data-ttu-id="dc57c-119">パイロット クライアントが組織内のユーザーの異なるプロファイルと、さまざまな地理的な場所を表す必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc57c-119">Ensure the pilot clients are representative of the different profiles of people in the organization as well as the different geographic locations.</span></span> <span data-ttu-id="dc57c-120">結果を、古い計算機とクロスチェックして、ExchangeとMicrosoft Teams、独自のネットワーク[](/microsoftteams/prepare-network)で実行したケース スタディ[](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)を確認できます。 [](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744)</span><span class="sxs-lookup"><span data-stu-id="dc57c-120">You can cross-check your results against our old calculators for [Exchange](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) and [Microsoft Teams](/microsoftteams/prepare-network) or the [case study](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) we performed on our own network.</span></span> 
    
4. <span data-ttu-id="dc57c-121">パイロット グループの測定値を使用して、組織のニーズ全体を推定し、ネットワークに変更を加える前に、見積もりを検証するために再テストします。</span><span class="sxs-lookup"><span data-stu-id="dc57c-121">Use the measurements from the pilot group to extrapolate the entire organization's needs and re-test to validate the estimations before making any changes to your network.</span></span>
    
## <a name="test-your-existing-network"></a><span data-ttu-id="dc57c-122">既存のネットワークをテストする</span><span class="sxs-lookup"><span data-stu-id="dc57c-122">Test your existing network</span></span>
<span data-ttu-id="dc57c-123"><a name="calculators"> </a></span><span class="sxs-lookup"><span data-stu-id="dc57c-123"><a name="calculators"> </a></span></span>

 <span data-ttu-id="dc57c-124">**ネットワーク ツール。**</span><span class="sxs-lookup"><span data-stu-id="dc57c-124">**Network tools.**</span></span> <span data-ttu-id="dc57c-125">インターネット帯域幅をテストして検証し、ダウンロード、アップロード、遅延の制約を判断します。</span><span class="sxs-lookup"><span data-stu-id="dc57c-125">Test and validate your Internet bandwidth to determine download, upload, and latency constraints.</span></span> <span data-ttu-id="dc57c-126">これらのツールは、完全に展開した後と同様に、移行のためのネットワークの機能を判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dc57c-126">These tools will help you determine the capabilities of your network for migration as well as after you're fully deployed.</span></span> 
    
- <span data-ttu-id="dc57c-127">[Microsoft Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=517243): 環境内の接続Exchange Onlineテストします。</span><span class="sxs-lookup"><span data-stu-id="dc57c-127">[Microsoft Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/p/?LinkId=517243): Tests connectivity in your Exchange Online environment.</span></span>
    
- <span data-ttu-id="dc57c-128">Microsoft サポート/回復アシスタント[を使用Office 365](https://diagnostics.office.com/#/Download?env=SOC)問題Outlook解決Office 365してください。</span><span class="sxs-lookup"><span data-stu-id="dc57c-128">Use the [Microsoft Support and Recovery Assistant for Office 365](https://diagnostics.office.com/#/Download?env=SOC) to fix Outlook and Office 365 problems.</span></span> 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a><span data-ttu-id="dc57c-129">ネットワーク計画と移行パフォーマンスの向上に関するベスト プラクティスは、Office 365</span><span class="sxs-lookup"><span data-stu-id="dc57c-129">Best practices for network planning and improving migration performance for Office 365</span></span>
<span data-ttu-id="dc57c-130"><a name="BestPractices"> </a></span><span class="sxs-lookup"><span data-stu-id="dc57c-130"><a name="BestPractices"> </a></span></span>

<span data-ttu-id="dc57c-131">エクスペリエンスの向上に関する詳細については、これらのベスト プラクティスについて詳Office 365してください。</span><span class="sxs-lookup"><span data-stu-id="dc57c-131">Dig a little deeper into these best practices for more information about improving your Office 365 experience.</span></span>
  
1. <span data-ttu-id="dc57c-132">ユーザーを支援する方法を、今すぐ始めてみませんか?</span><span class="sxs-lookup"><span data-stu-id="dc57c-132">Want to get started helping your users right away?</span></span> <span data-ttu-id="dc57c-133">ネットワーク[が](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)連携していないSharePoint Online、Exchange Online、Lync Online などの Office 365 の使用に関するヒントについては、「低速ネットワークで Office 365 を使用するためのベスト プラクティス」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc57c-133">See [Best practices for using Office 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) for tips on using Office 365, including SharePoint Online, Exchange Online, and Lync Online, when your network just isn't cooperating.</span></span> <span data-ttu-id="dc57c-134">この記事では、Office 365 エクスペリエンスを最適化するための TechNet と Support.office.com のコンテンツの負荷にリンクし、web ページをカスタマイズする簡単な方法と、Office 365 エクスペリエンスを最大限に活用するために Internet Explorer 設定を設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dc57c-134">This article links out to loads of content on TechNet and Support.office.com for optimizing your Office 365 experience and includes information on easy ways to customize your web pages and how to set your Internet Explorer settings for the best Office 365 experience.</span></span> 
    
2. <span data-ttu-id="dc57c-135">ネットワーク[Office 365の](./microsoft-365-network-connectivity-principles.md)原則を参照して、トラフィックを安全に管理し、可能な限り最高のパフォーマンスを得Office 365接続の原則を理解してください。</span><span class="sxs-lookup"><span data-stu-id="dc57c-135">Read [Office 365 Network Connectivity Principles](./microsoft-365-network-connectivity-principles.md) to understand the connectivity principles for securely managing Office 365 traffic and getting the best possible performance.</span></span> <span data-ttu-id="dc57c-136">この記事では、Office 365 ネットワーク接続をセキュリティで保護するための最新のガイドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="dc57c-136">This article will help you understand the most recent guidance for securely optimizing Office 365 network connectivity.</span></span> 
    
3. <span data-ttu-id="dc57c-137">更新プログラムのスケジュールを慎重に管理することで、メールWindows向上します。</span><span class="sxs-lookup"><span data-stu-id="dc57c-137">Improve mail migration performance by carefully managing the schedule for Windows Updates.</span></span> <span data-ttu-id="dc57c-138">クライアント コンピューターをバッチで更新し、ネットワーク帯域幅の使用を調整するために Office 365 に移行する前に、すべてのクライアント コンピューターが更新されます。</span><span class="sxs-lookup"><span data-stu-id="dc57c-138">You can update your client computers in batches and ensure that all client computers are updated before migrating to Office 365 to regulate the use of network bandwidth.</span></span> <span data-ttu-id="dc57c-139">詳細については、「最新の更新プログラムのデスクトップを手動で更新および構成[Office 365を参照してください](https://support.microsoft.com/gp/office-2013-365-update)。</span><span class="sxs-lookup"><span data-stu-id="dc57c-139">For more information, see [Manually update and configure desktops for Office 365 for the latest updates](https://support.microsoft.com/gp/office-2013-365-update).</span></span>
    
4. <span data-ttu-id="dc57c-140">Office 365ネットワーク トラフィックは、信頼できるインターネット サービスとして扱い、一部の組織が信頼されていないインターネット サービスへのネットワーク トラフィックに配置する従来のフィルター処理とスキャンの多くをバイパスできる場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="dc57c-140">Office 365 network traffic performs best when it's treated as a trusted Internet service and allowed to bypass much of the traditional filtering and scanning that some organizations place on network traffic to untrusted Internet services.</span></span> <span data-ttu-id="dc57c-141">これには、通常、プロキシ ユーザー認証やパケット 検査などの送信処理を削除し、ネットワーク アドレス変換 (NAT) を適切に使用してインターネットへのローカル出力を確保し、増加するネットワーク要求を処理するのに十分な帯域幅容量が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dc57c-141">This typically includes removing outbound processing such as proxy user authentication and packet inspection, as well as ensuring local egress to the Internet with the proper Network Address Translation (NAT) and enough bandwidth capacity to handle the increased network requests.</span></span> <span data-ttu-id="dc57c-142">ネットワーク上の[信頼Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)インターネット サービスとしてネットワークを処理するためのネットワークの構成に関するOffice 365詳細については、「ネットワーク エンドポイントの管理」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc57c-142">Refer to [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)for additional guidance on configuring your network to handle Office 365 as a trusted Internet service on your network.</span></span>
    
1. <span data-ttu-id="dc57c-143">[[エンドポイントのOffice 365する] を確認します](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)。</span><span class="sxs-lookup"><span data-stu-id="dc57c-143">Ensure [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span> <span data-ttu-id="dc57c-144">追加のトラフィックがOffice 365、送信プロキシ接続が増加し、TLS/SSL を使用したセキュリティで保護されたトラフィックが増加します。</span><span class="sxs-lookup"><span data-stu-id="dc57c-144">The additional traffic going to Office 365 results in an increase of outbound proxy connections as well as an increase in secure traffic over TLS/SSL.</span></span>
    
2. <span data-ttu-id="dc57c-145">送信プロキシでユーザー認証が必要な場合は、接続が遅くなるか、機能が失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc57c-145">If your outbound proxies require user authentication you may experience slow connectivity or a loss of functionality.</span></span> <span data-ttu-id="dc57c-146">ドメインの認証要件をバイパスOffice 365このオーバーヘッドを削減できます。</span><span class="sxs-lookup"><span data-stu-id="dc57c-146">Bypassing the authentication requirement for the Office 365 domains can reduce this overhead.</span></span>
    
3. <span data-ttu-id="dc57c-147">共有予定表とメールボックスの数が多い場合は、ユーザーからユーザーへの接続数がOutlook Exchange。</span><span class="sxs-lookup"><span data-stu-id="dc57c-147">If you have a large number of shared calendars and mailboxes, you may see an increase in the number of connections from Outlook to Exchange.</span></span> <span data-ttu-id="dc57c-148">たとえば、クライアントは、Outlook共有予定表ごとに最大 2 つの追加接続を開く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc57c-148">For instance, the Outlook client may open up to two additional connections for each shared calendar in use.</span></span> <span data-ttu-id="dc57c-149">この状況では、出力プロキシが接続を処理できるか、またはプロキシをバイパスして、Office 365接続Outlook。</span><span class="sxs-lookup"><span data-stu-id="dc57c-149">In this situation, ensure that the egress proxy can handle the connections, or bypass the proxy for connections to Office 365 for Outlook.</span></span>
    
4. <span data-ttu-id="dc57c-150">パブリック IP アドレスでサポートされるデバイスの最大数と、複数の IP アドレス間で負荷分散する方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="dc57c-150">Determine the maximum number of supported devices for a public IP address and how to load balance across multiple IP addresses.</span></span> <span data-ttu-id="dc57c-151">詳細については、[Office 365 の NAT サポート](nat-support-with-microsoft-365.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="dc57c-151">For more information, see [NAT support with Office 365](nat-support-with-microsoft-365.md).</span></span>
    
5. <span data-ttu-id="dc57c-152">ネットワーク上のコンピューターからの送信接続を検査する場合は、このフィルターを Office 365 ドメインにバイパスすると、接続とパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="dc57c-152">If you're inspecting outbound connections from computers on your network, bypassing this filtering to the Office 365 domains will improve connectivity and performance.</span></span> <span data-ttu-id="dc57c-153">さらに、多くの場合、送信検査をバイパスすると、単一のインターネット出力が不要になる場合が多く、ネットワーク要求に対するローカル インターネット出力Office 365有効にできます。</span><span class="sxs-lookup"><span data-stu-id="dc57c-153">Additionally, bypassing outbound inspection often removes the need for a single Internet egress and enables local Internet egress for Office 365 destined network requests.</span></span>
    
6. <span data-ttu-id="dc57c-154">一部のお客様は、内部ネットワーク設定がパフォーマンスに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc57c-154">Some customers find internal network settings may affect performance.</span></span> <span data-ttu-id="dc57c-155">設定伝送ユニット (MTU) の最大サイズ、ネットワークの自動ネゴシエーションまたは自動検出、インターネットへの最適なルートなど、一般的な場所です。</span><span class="sxs-lookup"><span data-stu-id="dc57c-155">Settings such as maximum transmission unit (MTU) size, network auto-negotiation or auto-detection, and sub-optimal routes to the Internet are common places to look.</span></span>
    
## <a name="network-planning-reference-for-office-365"></a><span data-ttu-id="dc57c-156">ネットワーク計画に関するOffice 365</span><span class="sxs-lookup"><span data-stu-id="dc57c-156">Network planning reference for Office 365</span></span>
<span data-ttu-id="dc57c-157"><a name="NetReference"> </a></span><span class="sxs-lookup"><span data-stu-id="dc57c-157"><a name="NetReference"> </a></span></span>

<span data-ttu-id="dc57c-158">これらのトピックには、ネットワーク参照Office 365詳細な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="dc57c-158">These topics contain detailed Office 365 network reference information.</span></span>
  
- [<span data-ttu-id="dc57c-159">Office 365 エンドポイントの管理</span><span class="sxs-lookup"><span data-stu-id="dc57c-159">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [<span data-ttu-id="dc57c-160">コンテンツ配信ネットワーク</span><span class="sxs-lookup"><span data-stu-id="dc57c-160">Content delivery networks</span></span>](content-delivery-networks.md)
    
- [<span data-ttu-id="dc57c-161">Office 365 の外部ドメイン ネーム システムのレコード</span><span class="sxs-lookup"><span data-stu-id="dc57c-161">External Domain Name System records for Office 365</span></span>](external-domain-name-system-records.md)
    
- [<span data-ttu-id="dc57c-162">Office 365 サービスでの IPv6 サポート</span><span class="sxs-lookup"><span data-stu-id="dc57c-162">IPv6 support in Office 365 services</span></span>](ipv6-support.md)
    
- [<span data-ttu-id="dc57c-163">Office 365 ネットワーク接続の原則</span><span class="sxs-lookup"><span data-stu-id="dc57c-163">Office 365 Network Connectivity Principles</span></span>](./microsoft-365-network-connectivity-principles.md)
    
- [<span data-ttu-id="dc57c-164">Office 365ネットワークに関するよく寄せられる質問 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="dc57c-164">Office 365 video networking Frequently Asked Questions (FAQ)</span></span>](office-365-video-networking-faq.md)
    
- [<span data-ttu-id="dc57c-165">Office 365 サービスに接続するネットワーク デバイスの計画</span><span class="sxs-lookup"><span data-stu-id="dc57c-165">Plan for network devices that connect to Office 365 services</span></span>](plan-for-network-devices.md)
    
- [<span data-ttu-id="dc57c-166">サービスのセットアップ Office 365ガイド</span><span class="sxs-lookup"><span data-stu-id="dc57c-166">Setup guides for Office 365 services</span></span>](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a><span data-ttu-id="dc57c-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="dc57c-167">See also</span></span>

[<span data-ttu-id="dc57c-168">Microsoft 365 Enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="dc57c-168">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)