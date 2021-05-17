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
description: Microsoft 365は、世界中のお客様がインターネット接続を使用してサービスに接続できるよう設計されています。 サービスが進化するにつれて、Microsoft 365 のセキュリティ、パフォーマンス、および信頼性は、インターネットを使用してサービスへの接続を確立する顧客に基づいて向上します。
ms.openlocfilehash: 4d80bdf5642b2456ac8293291c720429f7f18fb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905478"
---
# <a name="assessing-microsoft-365-network-connectivity"></a><span data-ttu-id="05966-104">Microsoft 365 ネットワーク接続の評価</span><span class="sxs-lookup"><span data-stu-id="05966-104">Assessing Microsoft 365 network connectivity</span></span>

<span data-ttu-id="05966-105">*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="05966-105">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="05966-106">Microsoft 365は、世界中のお客様がインターネット接続を使用してサービスに接続できるよう設計されています。</span><span class="sxs-lookup"><span data-stu-id="05966-106">Microsoft 365 is designed to enable customers all over the world to connect to the service using an internet connection.</span></span> <span data-ttu-id="05966-107">サービスが進化するにつれて、Microsoft 365 のセキュリティ、パフォーマンス、および信頼性は、インターネットを使用してサービスへの接続を確立する顧客に基づいて向上します。</span><span class="sxs-lookup"><span data-stu-id="05966-107">As the service evolves, the security, performance, and reliability of Microsoft 365 are improved based on customers using the internet to establish a connection to the service.</span></span>
  
<span data-ttu-id="05966-108">既存のインターネット接続Microsoft 365を展開プロジェクトの一部として評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05966-108">Customers planning to use Microsoft 365 should assess their existing and forecasted internet connectivity needs as a part of the deployment project.</span></span> <span data-ttu-id="05966-109">エンタープライズ クラスの展開では、信頼性が高く、適切なサイズのインターネット接続が、ユーザーの機能とシナリオを使用Microsoft 365重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="05966-109">For enterprise class deployments reliable and appropriately sized internet connectivity is a critical part of consuming Microsoft 365 features and scenarios.</span></span>
  
<span data-ttu-id="05966-110">ネットワーク評価は、サイズや好みに応じて、さまざまなユーザーや組織によって実行できます。</span><span class="sxs-lookup"><span data-stu-id="05966-110">Network evaluations can be performed by many different people and organizations depending on your size and preferences.</span></span> <span data-ttu-id="05966-111">評価のネットワーク スコープは、展開プロセスの場所によっても異なります。</span><span class="sxs-lookup"><span data-stu-id="05966-111">The network scope of the assessment can also vary depending on where you're at in your deployment process.</span></span> <span data-ttu-id="05966-112">ネットワーク評価の実行に必要な情報をより深く理解するために、利用可能なオプションを理解するためのネットワーク評価ガイドを作成しました。</span><span class="sxs-lookup"><span data-stu-id="05966-112">To help you get a better understanding of what it takes to perform a network assessment, we've produced a network assessment guide to help you understand the options available to you.</span></span> <span data-ttu-id="05966-113">この評価では、展開プロジェクトに追加する必要がある手順とリソースを決定し、この手順を正常に採用Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="05966-113">This assessment will determine what steps and resources need to be added to the deployment project to enable you to successfully adopt Microsoft 365.</span></span>
  
<span data-ttu-id="05966-114">包括的なネットワーク評価は、ネットワーク設計の課題に対する可能な解決策と実装の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="05966-114">A comprehensive network assessment will provide possible solutions to networking design challenges along with implementation details.</span></span> <span data-ttu-id="05966-115">一部のネットワーク評価では、Microsoft 365 への最適なネットワーク接続が、既存のネットワークおよびインターネット出力インフラストラクチャに対するマイナーな構成または設計変更に対応できると示されます。</span><span class="sxs-lookup"><span data-stu-id="05966-115">Some network assessments will show that optimal network connectivity to Microsoft 365 can be accommodated with minor configuration or design changes to the existing network and internet egress infrastructure.</span></span>

<span data-ttu-id="05966-116">一部の評価では、ネットワーク コンポーネントへのネットワークMicrosoft 365追加の投資が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="05966-116">Some assessments will indicate network connectivity to Microsoft 365 will require additional investments in networking components.</span></span> <span data-ttu-id="05966-117">たとえば、ブランチ オフィスと複数の地理的地域にまたがるエンタープライズ ネットワークでは、SD-WAN ソリューションへの投資や、ネットワークへのインターネット接続をサポートするための最適化されたルーティング インフラストラクチャが必要Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="05966-117">For example, enterprise networks that span branch offices and multiple geographic regions may require investments in SD-WAN solutions or optimized routing infrastructure to support internet connectivity to Microsoft 365.</span></span> <span data-ttu-id="05966-118">場合によっては、評価は、オンライン メディア品質などのシナリオMicrosoft 365規制やパフォーマンス要件の影響を受けるネットワーク接続を示Skype for Business[場合があります](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)。</span><span class="sxs-lookup"><span data-stu-id="05966-118">Occasionally an assessment will indicate network connectivity to Microsoft 365 is influenced by regulation or performance requirements for scenarios such as [Skype for Business Online media quality](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917).</span></span> <span data-ttu-id="05966-119">これらの追加の要件は、インターネット接続インフラストラクチャ、ルーティングの最適化、および専用の直接接続への投資につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="05966-119">These additional requirements may lead to investments in internet connectivity infrastructure, routing optimization, and specialized direct connectivity.</span></span>

<span data-ttu-id="05966-120">ネットワークの評価に役立ついくつかのリソース:</span><span class="sxs-lookup"><span data-stu-id="05966-120">Some resources to help you assess your network:</span></span>

- <span data-ttu-id="05966-121">ネットワーク[Microsoft 365に関する](microsoft-365-networking-overview.md)概念的な情報については、「ネットワーク接続の概要」をMicrosoft 365してください。</span><span class="sxs-lookup"><span data-stu-id="05966-121">See [Microsoft 365 network connectivity overview](microsoft-365-networking-overview.md) for conceptual information about Microsoft 365 networking.</span></span>
- <span data-ttu-id="05966-122">トラフィック[Microsoft 365を](./microsoft-365-network-connectivity-principles.md)安全に管理し、可能な限り最高のパフォーマンスを得るMicrosoft 365の原則を理解するには、「ネットワーク接続の原則」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05966-122">See [Microsoft 365 Network Connectivity Principles](./microsoft-365-network-connectivity-principles.md) to understand the connectivity principles for securely managing Microsoft 365 traffic and getting the best possible performance.</span></span>
- <span data-ttu-id="05966-123">Microsoft [FastTrack にサインアップして](https://www.microsoft.com/fasttrack)、計画、設計、展開Microsoft 365ガイド付きサポートを受けてください。</span><span class="sxs-lookup"><span data-stu-id="05966-123">Sign up for [Microsoft FastTrack](https://www.microsoft.com/fasttrack) for guided assistance with Microsoft 365 planning, design and deployment.</span></span> 
- <span data-ttu-id="05966-124">以下の[Microsoft 365 接続](assessing-network-connectivity.md#the-microsoft-365-connectivity-test)テスト セクションを参照して、特定のユーザーの場所とユーザー間で行えるネットワーク接続の改善に関する具体的なガイダンスを提供する基本的な接続テストを実行Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="05966-124">See the [Microsoft 365 connectivity test](assessing-network-connectivity.md#the-microsoft-365-connectivity-test) section below to run basic connectivity tests that provide specific guidance about networking connectivity improvements that can be made between a given user location and Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="05966-125">Microsoft の承認は、ExpressRoute を使用してユーザーにOffice 365。</span><span class="sxs-lookup"><span data-stu-id="05966-125">Microsoft authorization is required to use ExpressRoute for Office 365.</span></span> <span data-ttu-id="05966-126">Microsoft は、すべての顧客要求を確認し、お客様の規制要件が直接接続をOffice 365場合にのみ、ExpressRoute の使用を承認します。</span><span class="sxs-lookup"><span data-stu-id="05966-126">Microsoft reviews every customer request and only authorizes ExpressRoute for Office 365 usage when a customer's regulatory requirement mandates direct connectivity.</span></span> <span data-ttu-id="05966-127">そのような要件がある場合は、Microsoft のレビューを開始するために[ExpressRoute](https://aka.ms/O365ERReview) for Office 365 要求フォームで直接接続が必要と解釈される規制へのテキスト抜粋と Web リンクを提供してください。</span><span class="sxs-lookup"><span data-stu-id="05966-127">If you have such requirements, please provide the text excerpt and web link to the regulation which you interpret to mean that direct connectivity is required in the [ExpressRoute for Office 365 Request Form](https://aka.ms/O365ERReview) to begin a Microsoft review.</span></span> <span data-ttu-id="05966-128">未承認のサブスクリプションがルート フィルターを作成しようとOffice 365エラー メッセージが[表示されます](https://support.microsoft.com/kb/3181709)。</span><span class="sxs-lookup"><span data-stu-id="05966-128">Unauthorized subscriptions trying to create route filters for Office 365 will receive an [error message](https://support.microsoft.com/kb/3181709).</span></span>
  
<span data-ttu-id="05966-129">ネットワーク評価を計画する際に考慮すべき重要なMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="05966-129">Key points to consider when planning your network assessment for Microsoft 365:</span></span>
  
- <span data-ttu-id="05966-130">Microsoft 365は、パブリック インターネット上で実行される、セキュリティで保護された、信頼性の高い、高性能なサービスです。</span><span class="sxs-lookup"><span data-stu-id="05966-130">Microsoft 365 is a secure, reliable, high performance service that runs over the public internet.</span></span> <span data-ttu-id="05966-131">サービスのこれらの側面を強化するために引き続き投資を行っています。</span><span class="sxs-lookup"><span data-stu-id="05966-131">We continue to invest to enhance these aspects of the service.</span></span> <span data-ttu-id="05966-132">すべてのMicrosoft 365サービスは、インターネット接続経由で利用できます。</span><span class="sxs-lookup"><span data-stu-id="05966-132">All Microsoft 365 services are available via internet connectivity.</span></span>

- <span data-ttu-id="05966-133">インターネット ベースの接続の可用性、グローバルリーチMicrosoft 365パフォーマンスなど、ユーザーの主要な側面を継続的に最適化しています。</span><span class="sxs-lookup"><span data-stu-id="05966-133">We are continually optimizing core aspects of Microsoft 365 such as availability, global reach, and performance for internet based connectivity.</span></span> <span data-ttu-id="05966-134">たとえば、多くのMicrosoft 365は、インターネットに接続するエッジ ノードの拡張セットを利用します。</span><span class="sxs-lookup"><span data-stu-id="05966-134">For example, many Microsoft 365 services leverage an expanding set of internet facing edge nodes.</span></span> <span data-ttu-id="05966-135">このエッジ ネットワークは、インターネットを越える接続に最適な近接性とパフォーマンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="05966-135">This edge network offers the best proximity and performance to connections coming over the internet.</span></span>

- <span data-ttu-id="05966-136">Teams や Skype for Business Online の音声、ビデオ、会議の機能など、含まれるサービスに Microsoft 365 を使用する場合は、エンド to エンドのネットワーク評価を完了し[、Microsoft FastTrack](https://www.microsoft.com/fasttrack)を使用して接続要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="05966-136">When considering using Microsoft 365 for any of the included services such as Teams or Skype for Business Online voice, video, or meeting capabilities, customers should complete an end to end network assessment and meet connectivity requirements using [Microsoft FastTrack](https://www.microsoft.com/fasttrack).</span></span>

<span data-ttu-id="05966-137">Microsoft 365 を評価する場合や、ネットワーク評価の開始場所が不明な場合や、克服するための支援が必要なネットワーク設計上の課題が見つかった場合は、Microsoft アカウント チームと協力してください。</span><span class="sxs-lookup"><span data-stu-id="05966-137">If you're evaluating Microsoft 365 and aren't sure where to begin with your network assessment or have found network design challenges that you need assistance to overcome, please work with your Microsoft account team.</span></span>

## <a name="the-microsoft-365-connectivity-test"></a><span data-ttu-id="05966-138">接続Microsoft 365テスト</span><span class="sxs-lookup"><span data-stu-id="05966-138">The Microsoft 365 connectivity test</span></span>

<span data-ttu-id="05966-139">Microsoft 365[](https://aka.ms/netonboard)接続テストは概念実証 (POC) ネットワーク評価ツールであり、Microsoft 365 テナントに対して基本的な接続テストを実行し、最適な Microsoft 365 パフォーマンスを実現するために特定のネットワーク設計の推奨事項を作成します。</span><span class="sxs-lookup"><span data-stu-id="05966-139">The [Microsoft 365 connectivity test](https://aka.ms/netonboard) is a proof of concept (POC) network assessment tool that runs basic connectivity tests against your Microsoft 365 tenant and makes specific network design recommendations for optimal Microsoft 365 performance.</span></span> <span data-ttu-id="05966-140">このツールでは、インターネット Web ブラウズに役立つ一般的な大規模なエンタープライズ ネットワーク境界設計の選択肢が強調表示されますが、大規模な SaaS アプリケーション (Microsoft 365 など) のパフォーマンスに影響します。</span><span class="sxs-lookup"><span data-stu-id="05966-140">The tool highlights common large enterprise network perimeter design choices which are useful for Internet web browsing but impact the performance of large SaaS applications such as Microsoft 365.</span></span>

<span data-ttu-id="05966-141">ネットワーク オンボーディング ツールは、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="05966-141">The Network Onboarding tool does the following:</span></span>

- <span data-ttu-id="05966-142">場所を検出するか、テストする場所を指定できます</span><span class="sxs-lookup"><span data-stu-id="05966-142">Detects your location, or you can specify a location to test</span></span>
- <span data-ttu-id="05966-143">ネットワーク出力の場所を確認する</span><span class="sxs-lookup"><span data-stu-id="05966-143">Checks the location of your network egress</span></span>
- <span data-ttu-id="05966-144">最も近いサービス フロント ドアMicrosoft 365パスをテストする</span><span class="sxs-lookup"><span data-stu-id="05966-144">Tests the network path to the nearest Microsoft 365 service front door</span></span>
- <span data-ttu-id="05966-145">プロキシ サーバー、ファイアウォール、DNS に関連Windows 10境界ネットワーク設計の推奨事項を作成する、ダウンロード可能なアプリケーションを使用して高度なテストを提供します。</span><span class="sxs-lookup"><span data-stu-id="05966-145">Provides advanced tests using a downloadable Windows 10 application that makes perimeter network design recommendations related to proxy servers, firewalls, and DNS.</span></span> <span data-ttu-id="05966-146">また、このツールは、オンライン、オンライン、Skype for Business、Microsoft Teams、SharePointのパフォーマンス テストExchange Online。</span><span class="sxs-lookup"><span data-stu-id="05966-146">The tool also runs performance tests for Skype for Business Online, Microsoft Teams, SharePoint Online and Exchange Online.</span></span>

<span data-ttu-id="05966-147">このツールには、基本的な接続情報を収集するブラウザー ベースの UI と、高度なテストを実行し、追加の評価データを返すダウンロード可能な Windows 10 アプリケーションの 2 つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="05966-147">The tool has two components: a browser-based UI that collects basic connectivity information, and a downloadable Windows 10 application that runs advanced tests and returns additional assessment data.</span></span>

<span data-ttu-id="05966-148">ブラウザー ベースのツールには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="05966-148">The browser-based tool displays the following information:</span></span>

- <span data-ttu-id="05966-149">[結果と影響] タブ</span><span class="sxs-lookup"><span data-stu-id="05966-149">Results and impact tab</span></span>
  - <span data-ttu-id="05966-150">使用中のサービス フロント ドアのマップ上の場所</span><span class="sxs-lookup"><span data-stu-id="05966-150">The location on a map of the in-use service front door</span></span>
  - <span data-ttu-id="05966-151">最適な接続を提供する他のサービス フロント ドアのマップ上の場所</span><span class="sxs-lookup"><span data-stu-id="05966-151">The location on a map of other service front doors that would provide optimal connectivity</span></span>
  - <span data-ttu-id="05966-152">お近くの他の顧客と比較Microsoft 365相対的なパフォーマンス</span><span class="sxs-lookup"><span data-stu-id="05966-152">Relative performance compared to other Microsoft 365 customers near you</span></span>
- <span data-ttu-id="05966-153">[詳細とソリューション] タブ</span><span class="sxs-lookup"><span data-stu-id="05966-153">Details and solutions tab</span></span>
  - <span data-ttu-id="05966-154">都市と国別のユーザーの場所</span><span class="sxs-lookup"><span data-stu-id="05966-154">User location by city and country</span></span>
  - <span data-ttu-id="05966-155">都市、州、国別のネットワーク出力場所</span><span class="sxs-lookup"><span data-stu-id="05966-155">Network egress location by city, state and country</span></span>
  - <span data-ttu-id="05966-156">ユーザーからネットワークへの出力距離</span><span class="sxs-lookup"><span data-stu-id="05966-156">User to network egress distance</span></span>
  - <span data-ttu-id="05966-157">Microsoft 365 Exchange Onlineフロント ドアの場所</span><span class="sxs-lookup"><span data-stu-id="05966-157">Microsoft 365 Exchange Online service front door location</span></span>
  - <span data-ttu-id="05966-158">ユーザー Microsoft 365 Exchange Online最適なサービス フロント ドア</span><span class="sxs-lookup"><span data-stu-id="05966-158">Optimal Microsoft 365 Exchange Online service front door(s) for user location</span></span>
  - <span data-ttu-id="05966-159">パフォーマンスの向上を実現するメトロエリアのお客様</span><span class="sxs-lookup"><span data-stu-id="05966-159">Customers in your metro area with better performance</span></span>

<span data-ttu-id="05966-160">Advanced Tests ダウンロード可能アプリケーションには、次の追加情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="05966-160">The Advanced Tests downloadable application provides the following additional information:</span></span>

- <span data-ttu-id="05966-161">[詳細とソリューション] タブ (追加)</span><span class="sxs-lookup"><span data-stu-id="05966-161">Details and solutions tab (appended)</span></span>
  - <span data-ttu-id="05966-162">ユーザーの既定のゲートウェイ</span><span class="sxs-lookup"><span data-stu-id="05966-162">User's default gateway</span></span>
  - <span data-ttu-id="05966-163">クライアント DNS サーバー</span><span class="sxs-lookup"><span data-stu-id="05966-163">Client DNS Server</span></span>
  - <span data-ttu-id="05966-164">クライアント DNS 再帰的リゾルバー</span><span class="sxs-lookup"><span data-stu-id="05966-164">Client DNS Recursive Resolver</span></span>
  - <span data-ttu-id="05966-165">Exchange OnlineDNS サーバー</span><span class="sxs-lookup"><span data-stu-id="05966-165">Exchange Online DNS server</span></span>
  - <span data-ttu-id="05966-166">SharePointオンライン DNS サーバー</span><span class="sxs-lookup"><span data-stu-id="05966-166">SharePoint Online DNS server</span></span>
  - <span data-ttu-id="05966-167">プロキシ サーバーの ID</span><span class="sxs-lookup"><span data-stu-id="05966-167">Proxy server identification</span></span>
  - <span data-ttu-id="05966-168">メディア接続チェック</span><span class="sxs-lookup"><span data-stu-id="05966-168">Media connectivity check</span></span>
  - <span data-ttu-id="05966-169">メディア品質のパケット損失</span><span class="sxs-lookup"><span data-stu-id="05966-169">Media quality packet loss</span></span>
  - <span data-ttu-id="05966-170">メディア品質の待機時間</span><span class="sxs-lookup"><span data-stu-id="05966-170">Media quality latency</span></span>
  - <span data-ttu-id="05966-171">メディア品質ジッター</span><span class="sxs-lookup"><span data-stu-id="05966-171">Media quality jitter</span></span>
  - <span data-ttu-id="05966-172">メディア品質のパケットの並べ替え</span><span class="sxs-lookup"><span data-stu-id="05966-172">Media quality packet reorder</span></span>
- <span data-ttu-id="05966-173">複数の機能固有のエンドポイントへの接続テスト</span><span class="sxs-lookup"><span data-stu-id="05966-173">Connectivity tests to multiple feature-specific endpoints</span></span>
- <span data-ttu-id="05966-174">ネットワーク パスの診断:オンライン サービス、Exchange Onlineサービス、SharePointサービスTeams。</span><span class="sxs-lookup"><span data-stu-id="05966-174">Network path diagnostics that include tracert and latency data for the Exchange Online, SharePoint Online and Teams services</span></span>

<span data-ttu-id="05966-175">接続テストの詳細Microsoft 365、新しいネットワーク設計の推奨事項ブログ記事を含む更新された Microsoft 365 接続テスト[POC](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130)でフィードバックを提供できます。</span><span class="sxs-lookup"><span data-stu-id="05966-175">You can read about the Microsoft 365 connectivity test and provide feedback at the [Updated Microsoft 365 connectivity test POC with new network design recommendations](https://techcommunity.microsoft.com/t5/Office-365-Networking/Updated-Office-365-Network-Onboarding-Tool-POC-with-new-network/m-p/711130#M130) blog post.</span></span> <span data-ttu-id="05966-176">このツールの今後の更新やネットワーク更新プログラムMicrosoft 365に関する情報は、ネットワーク ブログのOffice 365[されます](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)。</span><span class="sxs-lookup"><span data-stu-id="05966-176">Information about future updates to this tool and other Microsoft 365 networking updates will be posted to the [Office 365 Networking](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking) blog.</span></span>
  
<span data-ttu-id="05966-177">戻って来るのに使用できる短いリンクを次に示します[ https://aka.ms/o365networkconnectivity 。](./microsoft-365-network-connectivity-principles.md)</span><span class="sxs-lookup"><span data-stu-id="05966-177">Here's a short link you can use to come back: [https://aka.ms/o365networkconnectivity.](./microsoft-365-network-connectivity-principles.md)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="05966-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="05966-178">Related topics</span></span>

[<span data-ttu-id="05966-179">Microsoft 365 ネットワーク接続の概要</span><span class="sxs-lookup"><span data-stu-id="05966-179">Microsoft 365 Network Connectivity Overview</span></span>](microsoft-365-networking-overview.md)

[<span data-ttu-id="05966-180">Microsoft 365 ネットワーク接続の原則</span><span class="sxs-lookup"><span data-stu-id="05966-180">Microsoft 365 Network Connectivity Principles</span></span>](./microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="05966-181">Office 365 エンドポイントの管理</span><span class="sxs-lookup"><span data-stu-id="05966-181">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="05966-182">Office 365 の URL および IP アドレスの範囲</span><span class="sxs-lookup"><span data-stu-id="05966-182">Office 365 URLs and IP address ranges</span></span>](urls-and-ip-address-ranges.md)

[<span data-ttu-id="05966-183">Office 365 IP アドレスと URL の Web サービス </span><span class="sxs-lookup"><span data-stu-id="05966-183">Office 365 IP Address and URL Web service</span></span>](microsoft-365-ip-web-service.md)

[<span data-ttu-id="05966-184">Microsoft 365とパフォーマンスの調整</span><span class="sxs-lookup"><span data-stu-id="05966-184">Microsoft 365 network and performance tuning</span></span>](network-planning-and-performance.md)

[<span data-ttu-id="05966-185">Microsoft 365 Enterprise の概要</span><span class="sxs-lookup"><span data-stu-id="05966-185">Microsoft 365 Enterprise overview</span></span>](microsoft-365-overview.md)