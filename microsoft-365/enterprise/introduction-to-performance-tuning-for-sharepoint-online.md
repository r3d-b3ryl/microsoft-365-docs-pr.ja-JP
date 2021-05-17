---
title: SharePoint Online のパフォーマンス チューニングの概要
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: この記事では、オンラインで最高のパフォーマンスを得るページを設計する際に考慮する必要がある具体的なSharePoint説明します。
ms.openlocfilehash: 6f40243c9d6a1657b6716a071288f5b4fb018164
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909740"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a><span data-ttu-id="8a522-103">SharePoint Online のパフォーマンス チューニングの概要</span><span class="sxs-lookup"><span data-stu-id="8a522-103">Introduction to performance tuning for SharePoint Online</span></span>

<span data-ttu-id="8a522-104">この記事では、オンラインで最高のパフォーマンスを得るページを設計する際に考慮する必要がある具体的なSharePoint説明します。</span><span class="sxs-lookup"><span data-stu-id="8a522-104">This article explains what specific aspects you need to consider when designing pages for best performance in SharePoint Online.</span></span>
     
## <a name="sharepoint-online-metrics"></a><span data-ttu-id="8a522-105">SharePointオンライン 指標</span><span class="sxs-lookup"><span data-stu-id="8a522-105">SharePoint Online metrics</span></span>

<span data-ttu-id="8a522-106">オンラインの次の広範な指標SharePointパフォーマンスに関する実際のデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="8a522-106">The following broad metrics for SharePoint Online provide real world data about performance:</span></span>
  
- <span data-ttu-id="8a522-107">ページの読み込み速度</span><span class="sxs-lookup"><span data-stu-id="8a522-107">How fast pages load</span></span>
    
- <span data-ttu-id="8a522-108">ページごとに必要なラウンド トリップの数</span><span class="sxs-lookup"><span data-stu-id="8a522-108">How many round trips required per page</span></span>
    
- <span data-ttu-id="8a522-109">サービスに関する問題</span><span class="sxs-lookup"><span data-stu-id="8a522-109">Issues with the service</span></span>
    
- <span data-ttu-id="8a522-110">パフォーマンスの低下を引き起こすその他の問題</span><span class="sxs-lookup"><span data-stu-id="8a522-110">Other things that cause performance degradation</span></span>
    
### <a name="conclusions-reached-because-of-the-data"></a><span data-ttu-id="8a522-111">データのために達した結論</span><span class="sxs-lookup"><span data-stu-id="8a522-111">Conclusions reached because of the data</span></span>

<span data-ttu-id="8a522-112">データには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8a522-112">The data tells us:</span></span>
  
- <span data-ttu-id="8a522-113">ほとんどのページは、オンライン上でSharePointします。</span><span class="sxs-lookup"><span data-stu-id="8a522-113">Most of the pages perform well on SharePoint Online.</span></span>
    
- <span data-ttu-id="8a522-114">カスタマイズされていないページは非常に迅速に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="8a522-114">Non-customized pages load very quickly.</span></span>
    
- <span data-ttu-id="8a522-115">OneDrive for Business、チーム サイトとシステム ページ (_layoutsなど) は、すべて読み込みも簡単です。</span><span class="sxs-lookup"><span data-stu-id="8a522-115">OneDrive for Business, team sites and system pages, such as _layouts, etc., are all quick to load.</span></span>
    
- <span data-ttu-id="8a522-116">オンライン ページの最もSharePoint 1% の読み込みには 5,000 ミリ秒以上かかる。</span><span class="sxs-lookup"><span data-stu-id="8a522-116">The slowest 1% of SharePoint Online pages take more than 5,000 milliseconds to load.</span></span>
    
<span data-ttu-id="8a522-117">使用できる簡単なベンチマーク テストの 1 つは、カスタマイズされた機能の使用が少なく、独自のポータルの読み込み時間と OneDrive for Business ホーム ページの読み込み時間を比較してパフォーマンスを測定する方法です。</span><span class="sxs-lookup"><span data-stu-id="8a522-117">One simple benchmark test you can use would be to measure performance by comparing the load time of your own portal against the load time of the OneDrive for Business home page as it uses few customized features.</span></span> <span data-ttu-id="8a522-118">これは、多くの場合、ネットワーク パフォーマンスの問題のトラブルシューティング時に完了を求める最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="8a522-118">This will often be the first step Support will ask you to complete when troubleshooting network performance issues.</span></span>
  
## <a name="use-a-standard-user-account-when-checking-performance"></a><span data-ttu-id="8a522-119">パフォーマンスを確認するときに標準のユーザー アカウントを使用する</span><span class="sxs-lookup"><span data-stu-id="8a522-119">Use a standard user account when checking performance</span></span>

<span data-ttu-id="8a522-120">サイト コレクション管理者、サイト所有者、エディター、または共同作成者は、追加のセキュリティ グループに属し、追加のアクセス許可を持ち、ページに読み込SharePoint要素を追加します。</span><span class="sxs-lookup"><span data-stu-id="8a522-120">A Site Collection Administrator, Site Owner, Editor, or Contributor belong to additional security groups, have additional permissions, and therefore have additional elements that SharePoint loads on a page.</span></span>
  
<span data-ttu-id="8a522-121">これは、SharePoint および SharePoint Online に適用されますが、オンプレミスのシナリオでは、SharePoint Online と同じほど簡単に違いを確認できません。</span><span class="sxs-lookup"><span data-stu-id="8a522-121">This is applicable to SharePoint on-premises and SharePoint Online but in an on-premises scenario the differences will not be as easily noticed as in SharePoint Online.</span></span>
  
<span data-ttu-id="8a522-122">ユーザーに対するページのパフォーマンスを正しく評価するには、標準のユーザー アカウントを使用して、オーサリング コントロールやセキュリティ グループに関連する追加のトラフィックを読み込むのを避ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a522-122">In order to correctly evaluate how a page will perform for users, you should use a standard user account to avoid loading the authoring controls and additional traffic related to security groups.</span></span>
  
## <a name="connection-categories-for-performance-tuning"></a><span data-ttu-id="8a522-123">パフォーマンス調整用の接続カテゴリ</span><span class="sxs-lookup"><span data-stu-id="8a522-123">Connection categories for performance tuning</span></span>

<span data-ttu-id="8a522-124">サーバーとユーザーの間の接続を 3 つの主要なコンポーネントに分類できます。</span><span class="sxs-lookup"><span data-stu-id="8a522-124">You can categorize the connections between the server and the user into three main components.</span></span> <span data-ttu-id="8a522-125">読み込み時間を把握SharePointオンライン ページを設計する場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="8a522-125">Consider these when designing SharePoint Online pages for insight into load times.</span></span>
  
- <span data-ttu-id="8a522-126">**サーバー** Microsoft がデータセンターでホストするサーバー。</span><span class="sxs-lookup"><span data-stu-id="8a522-126">**Server** The servers that Microsoft hosts in datacenters.</span></span>
    
- <span data-ttu-id="8a522-127">**ネットワーク** データセンターとユーザーの間の Microsoft ネットワーク、インターネット、オンプレミス ネットワーク。</span><span class="sxs-lookup"><span data-stu-id="8a522-127">**Network** The Microsoft network, the Internet, and your on-premises network between the datacenter and your users.</span></span>
    
- <span data-ttu-id="8a522-128">**ブラウザー** ページが読み込まれる場所。</span><span class="sxs-lookup"><span data-stu-id="8a522-128">**Browser** Where the page is loaded.</span></span>
    
<span data-ttu-id="8a522-129">これらの 3 つの接続内には、通常、低速ページの 95% が発生する 5 つの理由があります。</span><span class="sxs-lookup"><span data-stu-id="8a522-129">Within these three connections there are typically five reasons that cause 95% of slow pages.</span></span> <span data-ttu-id="8a522-130">これらの理由のそれぞれについては、この記事で説明します。</span><span class="sxs-lookup"><span data-stu-id="8a522-130">Each of these reasons is discussed in this article:</span></span>
  
- <span data-ttu-id="8a522-131">ナビゲーションの問題</span><span class="sxs-lookup"><span data-stu-id="8a522-131">Navigation issues</span></span>
    
- <span data-ttu-id="8a522-132">コンテンツのロールアップ</span><span class="sxs-lookup"><span data-stu-id="8a522-132">Content roll up</span></span>
    
- <span data-ttu-id="8a522-133">大きなファイル</span><span class="sxs-lookup"><span data-stu-id="8a522-133">Large files</span></span>
    
- <span data-ttu-id="8a522-134">サーバーへの多くの要求</span><span class="sxs-lookup"><span data-stu-id="8a522-134">Many requests to the server</span></span>
    
- <span data-ttu-id="8a522-135">Web パーツの処理</span><span class="sxs-lookup"><span data-stu-id="8a522-135">Web Part processing</span></span>
    
### <a name="server-connection"></a><span data-ttu-id="8a522-136">サーバー接続</span><span class="sxs-lookup"><span data-stu-id="8a522-136">Server connection</span></span>

<span data-ttu-id="8a522-137">オンプレミスでのパフォーマンスに影響を与える問題のSharePointは、SharePoint Online にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="8a522-137">Many of the issues that affect performance with SharePoint on-premises also apply to SharePoint Online.</span></span>
  
<span data-ttu-id="8a522-138">予想通り、オンプレミスのサーバーを使用してサーバーのパフォーマンスをはるかに制御SharePoint。</span><span class="sxs-lookup"><span data-stu-id="8a522-138">As you would expect, you have far more control over how servers perform with on-premises SharePoint.</span></span> <span data-ttu-id="8a522-139">オンラインSharePointとは少し異なります。</span><span class="sxs-lookup"><span data-stu-id="8a522-139">With SharePoint Online things are a little different.</span></span> <span data-ttu-id="8a522-140">サーバーの作業が多くなると、ページのレンダリングにかかる時間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="8a522-140">The more work you make a server do, the longer it takes to render a page.</span></span> <span data-ttu-id="8a522-141">このSharePoint、この点で最大の原因は、複数の Web パーツを持つ複雑なページです。</span><span class="sxs-lookup"><span data-stu-id="8a522-141">With SharePoint, the biggest culprit in this respect are complex pages with multiple web parts.</span></span>
  
<span data-ttu-id="8a522-142">オンプレミスの SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="8a522-142">SharePoint Server on-premises</span></span>
  
![オンプレミスのサーバーのスクリーンショット](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
<span data-ttu-id="8a522-144">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8a522-144">SharePoint Online</span></span>
  
![オンラインのサーバーのスクリーンショット](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
<span data-ttu-id="8a522-146">オンラインSharePoint、特定のページ要求が実際に複数のサーバーを呼び出す可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a522-146">With SharePoint Online, certain page requests may actually end up calling multiple servers.</span></span> <span data-ttu-id="8a522-147">個々の要求に対するサーバー間の要求のマトリックスで終わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a522-147">You could end up with a matrix of requests between servers for an individual request.</span></span> <span data-ttu-id="8a522-148">これらの操作は、ページ読み込みの観点からコストがかかるので、動作が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="8a522-148">These interactions are expensive from a page load perspective and will make things slow.</span></span>
  
<span data-ttu-id="8a522-149">これらのサーバー間の対話の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="8a522-149">Examples of these server to server interactions are:</span></span>
  
- <span data-ttu-id="8a522-150">Web to SQL サーバー</span><span class="sxs-lookup"><span data-stu-id="8a522-150">Web to SQL Servers</span></span>
    
- <span data-ttu-id="8a522-151">Web からアプリケーション サーバーへ</span><span class="sxs-lookup"><span data-stu-id="8a522-151">Web to application servers</span></span>
    
<span data-ttu-id="8a522-152">サーバーの操作が遅くなる可能性があるもう 1 つの問題は、キャッシュ ミスです。</span><span class="sxs-lookup"><span data-stu-id="8a522-152">The other thing that can slow down server interactions is cache misses.</span></span> <span data-ttu-id="8a522-153">オンプレミスのサイトとはSharePoint、以前にアクセスしたページに対して同じサーバーをヒットする可能性が非常に低い場合があります。これにより、オブジェクトのキャッシュは使用されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8a522-153">Unlike on-premises SharePoint, there is a very slim chance that you will hit the same server for a page that you have visited previously; this makes object caching obsolete.</span></span>
  
### <a name="network-connection"></a><span data-ttu-id="8a522-154">ネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="8a522-154">Network connection</span></span>

<span data-ttu-id="8a522-155">WAN を使用しないオンプレミス SharePointを使用すると、データセンターとエンド ユーザーの間で高速接続を使用できます。</span><span class="sxs-lookup"><span data-stu-id="8a522-155">With on-premises SharePoint that doesn't make use of a WAN, you may use a high-speed connection between datacenter and end-users.</span></span> <span data-ttu-id="8a522-156">一般に、ネットワークの観点から簡単に管理できます。</span><span class="sxs-lookup"><span data-stu-id="8a522-156">Generally, things are easy to manage from a network perspective.</span></span>
  
<span data-ttu-id="8a522-157">オンラインSharePoint、考慮すべきいくつかの要素があります。例えば：</span><span class="sxs-lookup"><span data-stu-id="8a522-157">With SharePoint Online, there are a few more factors to consider; for example:</span></span>
  
- <span data-ttu-id="8a522-158">Microsoft ネットワーク</span><span class="sxs-lookup"><span data-stu-id="8a522-158">The Microsoft network</span></span>
    
- <span data-ttu-id="8a522-159">インターネット</span><span class="sxs-lookup"><span data-stu-id="8a522-159">The Internet</span></span>
    
- <span data-ttu-id="8a522-160">The ISP</span><span class="sxs-lookup"><span data-stu-id="8a522-160">The ISP</span></span>
    
<span data-ttu-id="8a522-161">どのバージョンのネットワーク (SharePoint) を使用している場合でも、通常はネットワークがビジー状態になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a522-161">Regardless of which version of SharePoint (and which network) you are using, things that will typically cause the network to be busy include:</span></span>
  
- <span data-ttu-id="8a522-162">大きなペイロード</span><span class="sxs-lookup"><span data-stu-id="8a522-162">Large payload</span></span>
    
- <span data-ttu-id="8a522-163">多くのファイル</span><span class="sxs-lookup"><span data-stu-id="8a522-163">Many files</span></span>
    
- <span data-ttu-id="8a522-164">サーバーへの物理的な距離が大きい</span><span class="sxs-lookup"><span data-stu-id="8a522-164">Large physical distance to the server</span></span>
    
<span data-ttu-id="8a522-165">オンラインで活用できる機能の 1 SharePointは、Microsoft CDN (Content Delivery Network) です。</span><span class="sxs-lookup"><span data-stu-id="8a522-165">One feature that you can leverage in SharePoint Online is the Microsoft CDN (Content Delivery Network).</span></span> <span data-ttu-id="8a522-166">このCDNは、基本的に複数のデータセンターに展開されるサーバーの分散コレクションです。</span><span class="sxs-lookup"><span data-stu-id="8a522-166">A CDN is basically a distributed collection of servers deployed across multiple datacenters.</span></span> <span data-ttu-id="8a522-167">クライアントがCDNサーバーから離れた場合でも、ページ上のコンテンツをクライアントに近いサーバーでホストSharePointできます。</span><span class="sxs-lookup"><span data-stu-id="8a522-167">With a CDN, content on pages can be hosted on a server close to the client even if the client is far away from the originating SharePoint Server.</span></span> <span data-ttu-id="8a522-168">Microsoft は、今後、カスタマイズできないページのローカル インスタンス (たとえば、オンライン管理者ホーム ページなど) を格納SharePoint使用します。</span><span class="sxs-lookup"><span data-stu-id="8a522-168">Microsoft will be using this more in the future to store local instances of pages which cannot be customized, for example the SharePoint Online admin home page.</span></span> <span data-ttu-id="8a522-169">CDN の詳細については、「コンテンツ配信 [ネットワーク」を参照してください](content-delivery-networks.md)。</span><span class="sxs-lookup"><span data-stu-id="8a522-169">For more information about CDNs, see [Content delivery networks](content-delivery-networks.md).</span></span>
  
<span data-ttu-id="8a522-170">注意する必要がありますが、あまり実行できない可能性がある点は、ISP の接続速度です。</span><span class="sxs-lookup"><span data-stu-id="8a522-170">Something that you need to be aware of but may not be able to do much about is the connection speed of your ISP.</span></span> <span data-ttu-id="8a522-171">簡単な速度テスト ツールは、接続速度を示します。</span><span class="sxs-lookup"><span data-stu-id="8a522-171">A simple speed test tool will tell you the connection speed.</span></span>
  
### <a name="browser-connection"></a><span data-ttu-id="8a522-172">ブラウザー接続</span><span class="sxs-lookup"><span data-stu-id="8a522-172">Browser connection</span></span>

<span data-ttu-id="8a522-173">パフォーマンスの観点から Web ブラウザーで考慮すべきいくつかの要因があります。</span><span class="sxs-lookup"><span data-stu-id="8a522-173">There are a few factors to consider with web browsers from a performance perspective.</span></span>
  
<span data-ttu-id="8a522-174">複雑なページにアクセスすると、パフォーマンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="8a522-174">Visiting complex pages will affect performance.</span></span> <span data-ttu-id="8a522-175">ほとんどのブラウザーはキャッシュが小さい (約 90 MB) ですが、平均的な Web ページは通常約 1.6 MB です。</span><span class="sxs-lookup"><span data-stu-id="8a522-175">Most browsers only have a small cache (around 90MB), while the average web page is typically around 1.6MB.</span></span> <span data-ttu-id="8a522-176">これは使い慣れるのに時間はかからない。</span><span class="sxs-lookup"><span data-stu-id="8a522-176">This doesn't take long to get used up.</span></span>
  
<span data-ttu-id="8a522-177">帯域幅も問題になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a522-177">Bandwidth may also be an issue.</span></span> <span data-ttu-id="8a522-178">たとえば、ユーザーが別のセッションでビデオを視聴している場合、ユーザーのページのパフォーマンスにSharePointされます。</span><span class="sxs-lookup"><span data-stu-id="8a522-178">For example, if a user is watching videos in another session, this will affect the performance of your SharePoint page.</span></span> <span data-ttu-id="8a522-179">ユーザーがメディアをストリーミングするのを防ぐことはできないが、ページがユーザーに対して読み込む方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="8a522-179">While you can't prevent users from streaming media, you can control the way a page will load for users.</span></span>
  
<span data-ttu-id="8a522-180">最適なパフォーマンスを実現するために役立つさまざまな方法SharePointオンライン ページのカスタマイズ手法や他のベスト プラクティスについては、以下の記事をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8a522-180">Check out the following articles for different SharePoint Online page customization techniques and other best practices to help you achieve optimal performance.</span></span>
  
- [<span data-ttu-id="8a522-181">SharePoint Online のナビゲーション オプション</span><span class="sxs-lookup"><span data-stu-id="8a522-181">Navigation options for SharePoint Online</span></span>](navigation-options-for-sharepoint-online.md)
    
- [<span data-ttu-id="8a522-182">オンラインのページ診断ツールを使用SharePointする</span><span class="sxs-lookup"><span data-stu-id="8a522-182">Use the Page Diagnostics tool for SharePoint Online</span></span>](page-diagnostics-for-spo.md)
    
- [<span data-ttu-id="8a522-183">SharePoint Online のイメージの最適化</span><span class="sxs-lookup"><span data-stu-id="8a522-183">Image optimization for SharePoint Online</span></span>](image-optimization-for-sharepoint-online.md)
    
- [<span data-ttu-id="8a522-184">SharePoint Online での画像の読み込み遅延と JavaScript</span><span class="sxs-lookup"><span data-stu-id="8a522-184">Delay loading images and JavaScript in SharePoint Online</span></span>](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [<span data-ttu-id="8a522-185">SharePoint Online での縮小とバンドル</span><span class="sxs-lookup"><span data-stu-id="8a522-185">Minification and bundling in SharePoint Online</span></span>](minification-and-bundling-in-sharepoint-online.md)
    
- [<span data-ttu-id="8a522-186">SharePoint Online での Office 365 コンテンツ配信ネットワーク (CDN) の使用</span><span class="sxs-lookup"><span data-stu-id="8a522-186">Use the Office 365 Content Delivery Network (CDN) with SharePoint Online</span></span>](use-microsoft-365-cdn-with-spo.md)
    
- [<span data-ttu-id="8a522-187">コンテンツ クエリ Web パーツの代わりにコンテンツ検索 Web パーツを使用してオンラインでのパフォーマンスSharePointする</span><span class="sxs-lookup"><span data-stu-id="8a522-187">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [<span data-ttu-id="8a522-188">SharePoint Online のキャパシティ プランニングとロード テスト</span><span class="sxs-lookup"><span data-stu-id="8a522-188">Capacity planning and load testing SharePoint Online</span></span>](capacity-planning-and-load-testing-sharepoint-online.md)
    
- [<span data-ttu-id="8a522-189">SharePoint Online のパフォーマンスの問題の診断</span><span class="sxs-lookup"><span data-stu-id="8a522-189">Diagnosing performance issues with SharePoint Online</span></span>](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [<span data-ttu-id="8a522-190">Online でオブジェクト キャッシュをSharePointする</span><span class="sxs-lookup"><span data-stu-id="8a522-190">Using the object cache with SharePoint Online</span></span>](using-the-object-cache-with-sharepoint-online.md)
    
- [<span data-ttu-id="8a522-191">方法:SharePoint Online で調整またはブロックを回避する</span><span class="sxs-lookup"><span data-stu-id="8a522-191">How to: Avoid getting throttled or blocked in SharePoint Online</span></span>](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
