---
title: Microsoft 365 ネットワーク接続の評価
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 64b420ef-0218-48f6-8a34-74bb27633b10
description: Microsoft 365 は、世界中のお客様がインターネット接続を使用してサービスに接続できるよう設計されています。 サービスの進化に伴い、Microsoft 365 のセキュリティ、パフォーマンス、および信頼性は、インターネットを使用してサービスへの接続を確立する顧客に基づいて向上します。
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905478"
---
# <a name="assessing-microsoft-365-network-connectivity"></a><span data-ttu-id="aa354-104">Microsoft 365 ネットワーク接続の評価</span><span class="sxs-lookup"><span data-stu-id="aa354-104">Assessing Microsoft 365 network connectivity</span></span>

<span data-ttu-id="aa354-105">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="aa354-105">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="aa354-106">Microsoft 365 は、世界中のお客様がインターネット接続を使用してサービスに接続できるよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="aa354-106">Microsoft 365 is designed to enable customers all over the world to connect to the service using an internet connection.</span></span> <span data-ttu-id="aa354-107">サービスの進化に伴い、Microsoft 365 のセキュリティ、パフォーマンス、および信頼性は、インターネットを使用してサービスへの接続を確立する顧客に基づいて向上します。</span><span class="sxs-lookup"><span data-stu-id="aa354-107">As the service evolves, the security, performance, and reliability of Microsoft 365 are improved based on customers using the internet to establish a connection to the service.</span></span>
  
<span data-ttu-id="aa354-108">Microsoft 365 の使用を計画しているお客様は、展開プロジェクトの一環として、既存の予測されたインターネット接続ニーズを評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa354-108">Customers planning to use Microsoft 365 should assess their existing and forecasted internet connectivity needs as a part of the deployment project.</span></span> <span data-ttu-id="aa354-109">エンタープライズ クラスの展開では、Microsoft 365 の機能とシナリオを使用する上で、信頼できる適切なサイズのインターネット接続が重要です。</span><span class="sxs-lookup"><span data-stu-id="aa354-109">For enterprise class deployments reliable and appropriately sized internet connectivity is a critical part of consuming Microsoft 365 features and scenarios.</span></span>
  
<span data-ttu-id="aa354-110">ネットワーク評価は、サイズや好みに応じて、さまざまなユーザーや組織によって実行できます。</span><span class="sxs-lookup"><span data-stu-id="aa354-110">Network evaluations can be performed by many different people and organizations depending on your size and preferences.</span></span> <span data-ttu-id="aa354-111">評価のネットワーク スコープは、展開プロセスの場所によっても異なります。</span><span class="sxs-lookup"><span data-stu-id="aa354-111">The network scope of the assessment can also vary depending on where you're at in your deployment process.</span></span> <span data-ttu-id="aa354-112">ネットワーク評価の実行に必要な情報をより深く理解するために、利用可能なオプションを理解するためのネットワーク評価ガイドを作成しました。</span><span class="sxs-lookup"><span data-stu-id="aa354-112">To help you get a better understanding of what it takes to perform a network assessment, we've produced a network assessment guide to help you understand the options available to you.</span></span> <span data-ttu-id="aa354-113">この評価は、Microsoft 365 を正常に採用するために展開プロジェクトに追加する必要がある手順とリソースを決定します。</span><span class="sxs-lookup"><span data-stu-id="aa354-113">This assessment will determine what steps and resources need to be added to the deployment project to enable you to successfully adopt Microsoft 365.</span></span>
  
<span data-ttu-id="aa354-114">包括的なネットワーク評価は、ネットワーク設計の課題に対する可能な解決策と実装の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="aa354-114">A comprehensive network assessment will provide possible solutions to networking design challenges along with implementation details.</span></span> <span data-ttu-id="aa354-115">一部のネットワーク評価では、Microsoft 365 への最適なネットワーク接続が、既存のネットワークおよびインターネット出力インフラストラクチャのわずかな構成または設計変更に対応できると示されます。</span><span class="sxs-lookup"><span data-stu-id="aa354-115">Some network assessments will show that optimal network connectivity to Microsoft 365 can be accommodated with minor configuration or design changes to the existing network and internet egress infrastructure.</span></span>

<span data-ttu-id="aa354-116">一部の評価では、Microsoft 365 へのネットワーク接続にネットワーク コンポーネントへの追加投資が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="aa354-116">Some assessments will indicate network connectivity to Microsoft 365 will require additional investments in networking components.</span></span> <span data-ttu-id="aa354-117">たとえば、ブランチ オフィスと複数の地理的地域にまたがるエンタープライズ ネットワークでは、Microsoft 365 へのインターネット接続をサポートするために、SD-WAN ソリューションや最適化されたルーティング インフラストラクチャへの投資が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="aa354-117">For example, enterprise networks that span branch offices and multiple geographic regions may require investments in SD-WAN solutions or optimized routing infrastructure to support internet connectivity to Microsoft 365.</span></span> <span data-ttu-id="aa354-118">場合によっては、評価は、Microsoft 365 へのネットワーク接続が [、Skype for Business Online](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)メディア品質などのシナリオの規制やパフォーマンス要件の影響を受ける可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="aa354-118">Occasionally an assessment will indicate network connectivity to Microsoft 365 is influenced by regulation or performance requirements for scenarios such as [Skype for Business Online media quality](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917).</span></span> <span data-ttu-id="aa354-119">これらの追加の要件は、インターネット接続インフラストラクチャ、ルーティングの最適化、および専用の直接接続への投資につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="aa354-119">These additional requirements may lead to investments in internet connectivity infrastructure, routing optimization, and specialized direct connectivity.</span></span>

<span data-ttu-id="aa354-120">ネットワークの評価に役立ついくつかのリソース:</span><span class="sxs-lookup"><span data-stu-id="aa354-120">Some resources to help you assess your network:</span></span>

- <span data-ttu-id="aa354-121">[Microsoft 365 ネットワーク](microsoft-365-networking-overview.md)に関する概念的な情報については、「Microsoft 365 ネットワーク接続の概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa354-121">See [Microsoft 365 network connectivity overview](microsoft-365-networking-overview.md) for conceptual information about Microsoft 365 networking.</span></span>
- <span data-ttu-id="aa354-122">Microsoft 365 トラフィックを安全に管理し、可能な限り最高のパフォーマンスを得る接続の原則については [、「Microsoft 365](./microsoft-365-network-connectivity-principles.md) ネットワーク接続の原則」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa354-122">See [Microsoft 365 Network Connectivity Principles](./microsoft-365-network-connectivity-principles.md) to understand the connectivity principles for securely managing Microsoft 365 traffic and getting the best possible performance.</span></span>
- <span data-ttu-id="aa354-123">Microsoft 365 の計画、設計、展開に関するガイド付きサポートについては、Microsoft [FastTrack](https://www.microsoft.com/fasttrack) にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="aa354-123">Sign up for [Microsoft FastTrack](https://www.microsoft.com/fasttrack) for guided assistance with Microsoft 365 planning, design and deployment.</span></span> 
- <span data-ttu-id="aa354-124">特定のユーザーの場所と Microsoft 365 の間で行えるネットワーク接続の改善に関する具体的なガイダンスを提供する基本的な接続テストを実行するには、以下の [「Microsoft 365](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) 接続テスト」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa354-124">See the [Microsoft 365 connectivity test](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) section below to run basic connectivity tests that provide specific guidance about networking connectivity improvements that can be made between a given user location and Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="aa354-125">Microsoft の承認は、ExpressRoute を 365 にOfficeです。</span><span class="sxs-lookup"><span data-stu-id="aa354-125">Microsoft authorization is required to use ExpressRoute for Office 365.</span></span> <span data-ttu-id="aa354-126">Microsoft は、すべての顧客要求を確認し、お客様の規制要件が直接接続をOffice 365 の使用に対する ExpressRoute のみを承認します。</span><span class="sxs-lookup"><span data-stu-id="aa354-126">Microsoft reviews every customer request and only authorizes ExpressRoute for Office 365 usage when a customer's regulatory requirement mandates direct connectivity.</span></span> <span data-ttu-id="aa354-127">そのような要件がある場合は、Microsoft のレビューを開始するために [、ExpressRoute for Office 365 Request Form](https://aka.ms/O365ERReview) で直接接続が必要と解釈される規制へのテキスト抜粋と Web リンクを提供してください。</span><span class="sxs-lookup"><span data-stu-id="aa354-127">If you have such requirements, please provide the text excerpt and web link to the regulation which you interpret to mean that direct connectivity is required in the [ExpressRoute for Office 365 Request Form](https://aka.ms/O365ERReview) to begin a Microsoft review.</span></span> <span data-ttu-id="aa354-128">365 のルート フィルターを作成しようとしている未承認のサブスクリプションOfficeエラー メッセージが [表示されます](https://support.microsoft.com/kb/3181709)。</span><span class="sxs-lookup"><span data-stu-id="aa354-128">Unauthorized subscriptions trying to create route filters for Office 365 will receive an [error message](https://support.microsoft.com/kb/3181709).</span></span>
  
<span data-ttu-id="aa354-129">Microsoft 365 のネットワーク評価を計画する際に考慮すべき重要な点:</span><span class="sxs-lookup"><span data-stu-id="aa354-129">Key points to consider when planning your network assessment for Microsoft 365:</span></span>
  
- <span data-ttu-id="aa354-130">Microsoft 365 は、パブリック インターネット上で実行される、安全で信頼性の高い高性能サービスです。</span><span class="sxs-lookup"><span data-stu-id="aa354-130">Microsoft 365 is a secure, reliable, high performance service that runs over the public internet.</span></span> <span data-ttu-id="aa354-131">サービスのこれらの側面を強化するために引き続き投資を行っています。</span><span class="sxs-lookup"><span data-stu-id="aa354-131">We continue to invest to enhance these aspects of the service.</span></span> <span data-ttu-id="aa354-132">すべての Microsoft 365 サービスは、インターネット接続経由で利用できます。</span><span class="sxs-lookup"><span data-stu-id="aa354-132">All Microsoft 365 services are available via internet connectivity.</span></span>

- <span data-ttu-id="aa354-133">Microsoft 365 の主要な側面 (可用性、グローバルリーチ、インターネット ベースの接続のパフォーマンスなど) を継続的に最適化しています。</span><span class="sxs-lookup"><span data-stu-id="aa354-133">We are continually optimizing core aspects of Microsoft 365 such as availability, global reach, and performance for internet based connectivity.</span></span> <span data-ttu-id="aa354-134">たとえば、多くの Microsoft 365 サービスは、インターネットに接続するエッジ ノードの拡張セットを利用します。</span><span class="sxs-lookup"><span data-stu-id="aa354-134">For example, many Microsoft 365 services leverage an expanding set of internet facing edge nodes.</span></span> <span data-ttu-id="aa354-135">このエッジ ネットワークは、インターネットを越える接続に最適な近接性とパフォーマンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="aa354-135">This edge network offers the best proximity and performance to connections coming over the internet.</span></span>

- <span data-ttu-id="aa354-136">Teams や Skype for Business Online の音声、ビデオ、会議の機能など、含まれるサービスに Microsoft 365 を使用する場合は、エンド to エンドのネットワーク評価を完了し [、Microsoft FastTrack](https://www.microsoft.com/fasttrack)を使用して接続要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa354-136">When considering using Microsoft 365 for any of the included services such as Teams or Skype for Business Online voice, video, or meeting capabilities, customers should complete an end to end network assessment and meet connectivity requirements using [Microsoft FastTrack](https://www.microsoft.com/fasttrack).</span></span>

<span data-ttu-id="aa354-137">Microsoft 365 を評価する場合で、ネットワーク評価の開始場所が不明な場合や、克服するための支援が必要なネットワーク設計上の課題が見つかった場合は、Microsoft アカウント チームと協力してください。</span><span class="sxs-lookup"><span data-stu-id="aa354-137">If you're evaluating Microsoft 365 and aren't sure where to begin with your network assessment or have found network design challenges that you need assistance to overcome, please work with your Microsoft account team.</span></span>

## <a name="the-microsoft-365-connectivity-test"></a><span data-ttu-id="aa354-138">Microsoft 365 接続テスト</span><span class="sxs-lookup"><span data-stu-id="aa354-138">The Microsoft 365 connectivity test</span></span>

<span data-ttu-id="aa354-139">[Microsoft 365](https://aka.ms/netonboard)接続テストは概念実証 (POC) ネットワーク評価ツールであり、Microsoft 365 テナントに対して基本的な接続テストを実行し、最適な Microsoft 365 パフォーマンスを実現するために特定のネットワーク設計の推奨事項を作成します。</span><span class="sxs-lookup"><span data-stu-id="aa354-139">The [Microsoft 365 connectivity test](https://aka.ms/netonboard) is a proof of concept (POC) network assessment tool that runs basic connectivity tests against your Microsoft 365 tenant and makes specific network design recommendations for optimal Microsoft 365 performance.</span></span> <span data-ttu-id="aa354-140">このツールでは、一般的な大規模なエンタープライズ ネットワーク境界設計の選択肢が強調表示され、インターネット Web ブラウズに役立ちますが、Microsoft 365 などの大規模な SaaS アプリケーションのパフォーマンスに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="aa354-140">The tool highlights common large enterprise network perimeter design choices which are useful for Internet web browsing but impact the performance of large SaaS applications such as Microsoft 365.</span></span>

<span data-ttu-id="aa354-141">ネットワーク オンボーディング ツールは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="aa354-141">The Network Onboarding tool does the following:</span></span>

- <span data-ttu-id="aa354-142">場所を検出するか、テストする場所を指定できます</span><span class="sxs-lookup"><span data-stu-id="aa354-142">Detects your location, or you can specify a location to test</span></span>
- <span data-ttu-id="aa354-143">ネットワーク出力の場所を確認する</span><span class="sxs-lookup"><span data-stu-id="aa354-143">Checks the location of your network egress</span></span>
- <span data-ttu-id="aa354-144">最も近い Microsoft 365 サービス フロント ドアへのネットワーク パスをテストする</span><span class="sxs-lookup"><span data-stu-id="aa354-144">Tests the network path to the nearest Microsoft 365 service front door</span></span>
- <span data-ttu-id="aa354-145">プロキシ サーバー、ファイアウォール、DNS に関連する境界ネットワーク設計の推奨事項を作成する、ダウンロード可能な Windows 10 アプリケーションを使用した高度なテストを提供します。</span><span class="sxs-lookup"><span data-stu-id="aa354-145">Provides advanced tests using a downloadable Windows 10 application that makes perimeter network design recommendations related to proxy servers, firewalls, and DNS.</span></span> <span data-ttu-id="aa354-146">このツールでは、Skype for Business Online、Microsoft Teams、SharePoint Online、Exchange Online のパフォーマンス テストも実行します。</span><span class="sxs-lookup"><span data-stu-id="aa354-146">The tool also runs performance tests for Skype for Business Online, Microsoft Teams, SharePoint Online and Exchange Online.</span></span>

<span data-ttu-id="aa354-147">このツールには、基本的な接続情報を収集するブラウザー ベースの UI と、高度なテストを実行し、追加の評価データを返すダウンロード可能な Windows 10 アプリケーションの 2 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="aa354-147">The tool has two components: a browser-based UI that collects basic connectivity information, and a downloadable Windows 10 application that runs advanced tests and returns additional assessment data.</span></span>

<span data-ttu-id="aa354-148">ブラウザー ベースのツールには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aa354-148">The browser-based tool displays the following information:</span></span>

- <span data-ttu-id="aa354-149">[結果と影響] タブ</span><span class="sxs-lookup"><span data-stu-id="aa354-149">Results and impact tab</span></span>
  - <span data-ttu-id="aa354-150">使用中のサービス フロント ドアのマップ上の場所</span><span class="sxs-lookup"><span data-stu-id="aa354-150">The location on a map of the in-use service front door</span></span>
  - <span data-ttu-id="aa354-151">最適な接続を提供する他のサービス フロント ドアのマップ上の場所</span><span class="sxs-lookup"><span data-stu-id="aa354-151">The location on a map of other service front doors that would provide optimal connectivity</span></span>
  - <span data-ttu-id="aa354-152">お近くの他の Microsoft 365 のお客様と比較した相対的なパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="aa354-152">Relative performance compared to other Microsoft 365 customers near you</span></span>
- <span data-ttu-id="aa354-153">[詳細とソリューション] タブ</span><span class="sxs-lookup"><span data-stu-id="aa354-153">Details and solutions tab</span></span>
  - <span data-ttu-id="aa354-154">都市と国別のユーザーの場所</span><span class="sxs-lookup"><span data-stu-id="aa354-154">User location by city and country</span></span>
  - <span data-ttu-id="aa354-155">都市、州、国別のネットワーク出力場所</span><span class="sxs-lookup"><span data-stu-id="aa354-155">Network egress location by city, state and country</span></span>
  - <span data-ttu-id="aa354-156">ユーザーからネットワークへの出力距離</span><span class="sxs-lookup"><span data-stu-id="aa354-156">User to network egress distance</span></span>
  - <span data-ttu-id="aa354-157">Microsoft 365 Exchange Online サービスのフロント ドアの場所</span><span class="sxs-lookup"><span data-stu-id="aa354-157">Microsoft 365 Exchange Online service front door location</span></span>
  - <span data-ttu-id="aa354-158">ユーザーの場所に最適な Microsoft 365 Exchange Online サービスのフロント ドア</span><span class="sxs-lookup"><span data-stu-id="aa354-158">Optimal Microsoft 365 Exchange Online service front door(s) for user location</span></span>
  - <span data-ttu-id="aa354-159">パフォーマンスの向上を実現するメトロエリアのお客様</span><span class="sxs-lookup"><span data-stu-id="aa354-159">Customers in your metro area with better performance</span></span>

<span data-ttu-id="aa354-160">Advanced Tests ダウンロード可能アプリケーションには、次の追加情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="aa354-160">The Advanced Tests downloadable application provides the following additional information:</span></span>

- <span data-ttu-id="aa354-161">[詳細とソリューション] タブ (追加)</span><span class="sxs-lookup"><span data-stu-id="aa354-161">Details and solutions tab (appended)</span></span>
  - <span data-ttu-id="aa354-162">ユーザーの既定のゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="aa354-162">User's default gateway</span></span>
  - <span data-ttu-id="aa354-163">クライアント DNS サーバー</span><span class="sxs-lookup"><span data-stu-id="aa354-163">Client DNS Server</span></span>
  - <span data-ttu-id="aa354-164">クライアント DNS 再帰的リゾルバー</span><span class="sxs-lookup"><span data-stu-id="aa354-164">Client DNS Recursive Resolver</span></span>
  - <span data-ttu-id="aa354-165">Exchange Online DNS サーバー</span><span class="sxs-lookup"><span data-stu-id="aa354-165">Exchange Online DNS server</span></span>
  - <span data-ttu-id="aa354-166">SharePoint Online DNS サーバー</span><span class="sxs-lookup"><span data-stu-id="aa354-166">SharePoint Online DNS server</span></span>
  - <span data-ttu-id="aa354-167">プロキシ サーバーの ID</span><span class="sxs-lookup"><span data-stu-id="aa354-167">Proxy server identification</span></span>
  - <span data-ttu-id="aa354-168">メディア接続チェック</span><span class="sxs-lookup"><span data-stu-id="aa354-168">Media connectivity check</span></span>
  - <span data-ttu-id="aa354-169">メディア品質のパケット損失</span><span class="sxs-lookup"><span data-stu-id="aa354-169">Media quality packet loss</span></span>
  - <span data-ttu-id="aa354-170">メディア品質の待機時間</span><span class="sxs-lookup"><span data-stu-id="aa354-170">Media quality latency</span></span>
  - <span data-ttu-id="aa354-171">メディア品質ジッター</span><span class="sxs-lookup"><span data-stu-id="aa354-171">Media quality jitter</span></span>
  - <span data-ttu-id="aa354-172">メディア品質のパケットの並べ替え</span><span class="sxs-lookup"><span data-stu-id="aa354-172">Media quality packet reorder</span></span>
- <span data-ttu-id="aa354-173">複数の機能固有のエンドポイントへの接続テスト</span><span class="sxs-lookup"><span data-stu-id="aa354-173">Connectivity tests to multiple feature-specific endpoints</span></span>
- <span data-ttu-id="aa354-174">Exchange Online、SharePoint Online、Teams サービスの tracert および待機時間データを含むネットワーク パス診断</span><span class="sxs-lookup"><span data-stu-id="aa354-174">Network path diagnostics that include tracert and latency data for the Exchange Online, SharePoint Online and Teams services</span></span>

<span data-ttu-id="aa354-175">Microsoft 365 接続テストについて読み、フィードバックを提供するには、 [更新された Microsoft 365 接続テスト POC](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) で、新しいネットワーク設計の推奨事項に関するブログ投稿を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aa354-175">You can read about the Microsoft 365 connectivity test and provide feedback at the [Updated Microsoft 365 connectivity test POC with new network design recommendations](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) blog post.</span></span> <span data-ttu-id="aa354-176">このツールと他の Microsoft 365 ネットワーク更新プログラムの今後の更新に関する情報は、Office [365 Networking](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) ブログに投稿されます。</span><span class="sxs-lookup"><span data-stu-id="aa354-176">Information about future updates to this tool and other Microsoft 365 networking updates will be posted to the [Office 365 Networking](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) blog.</span></span>
  
<span data-ttu-id="aa354-177">戻って来るのに使用できる短いリンクを次に示します[ https://aka.ms/o365networkconnectivity 。](./microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="aa354-177">Here's a short link you can use to come back: [https://aka.ms/o365networkconnectivity.](./microsoft-365-network-connectivity-principles.md)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="aa354-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="aa354-178">Related topics</span></span>

[<span data-ttu-id="aa354-179">Microsoft 365 ネットワーク接続の概要</span><span class="sxs-lookup"><span data-stu-id="aa354-179">Microsoft 365 Network Connectivity Overview</span></span>](microsoft-365-networking-overview.md)

[<span data-ttu-id="aa354-180">Microsoft 365 ネットワーク接続の原則</span><span class="sxs-lookup"><span data-stu-id="aa354-180">Microsoft 365 Network Connectivity Principles</span></span>](./microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="aa354-181">Office 365 エンドポイントの管理</span><span class="sxs-lookup"><span data-stu-id="aa354-181">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="aa354-182">Office 365 の URL および IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="aa354-182">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="aa354-183">Office 365 IP アドレスと URL の Web サービス </span><span class="sxs-lookup"><span data-stu-id="aa354-183">Office 365 IP Address and URL Web service</span></span>](microsoft-365-ip-web-service.md)

[<span data-ttu-id="aa354-184">Microsoft 365 ネットワークとパフォーマンスのチューニング</span><span class="sxs-lookup"><span data-stu-id="aa354-184">Microsoft 365 network and performance tuning</span></span>](network-planning-and-performance.md)

[<span data-ttu-id="aa354-185">Microsoft 365 Enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="aa354-185">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)