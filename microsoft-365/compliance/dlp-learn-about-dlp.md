---
title: データ損失防止について
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: データ損失防止ポリシーとツールを使用Microsoft 365機密情報を保護し、DLP ライフサイクルを通じてツアーを行う方法について説明します。
ms.openlocfilehash: 9b449886e0856f7407fcd49b83192dd0c01474bd
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108261"
---
# <a name="learn-about-data-loss-prevention"></a><span data-ttu-id="38ee7-103">データ損失防止について</span><span class="sxs-lookup"><span data-stu-id="38ee7-103">Learn about data loss prevention</span></span>

<span data-ttu-id="38ee7-104">組織には、財務データ、専有データ、クレジット カード番号、健康記録、社会保障番号などの機密情報が管理されています。</span><span class="sxs-lookup"><span data-stu-id="38ee7-104">Organizations have sensitive information under their control such as financial data, proprietary data, credit card numbers, health records, or social security numbers.</span></span> <span data-ttu-id="38ee7-105">この機密データを保護し、リスクを軽減するために、ユーザーがそれを持つべきではないユーザーと不適切に共有するのを防ぐ方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="38ee7-105">To help protect this sensitive data and reduce risk, they need a way to prevent their users from inappropriately sharing it with people who shouldn't have it.</span></span> <span data-ttu-id="38ee7-106">この方法は、データ損失防止 (DLP) と呼ばれています。</span><span class="sxs-lookup"><span data-stu-id="38ee7-106">This practice is called data loss prevention (DLP).</span></span>

<span data-ttu-id="38ee7-107">このMicrosoft 365、DLP ポリシーを定義して適用することで、データ損失防止を実装します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-107">In Microsoft 365, you implement data loss prevention by defining and applying DLP policies.</span></span> <span data-ttu-id="38ee7-108">DLP ポリシーを使用すると、次に示す間で機密性の高いアイテムを特定、監視、および自動的に保護できます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-108">With a DLP policy, you can identify, monitor, and automatically protect sensitive items across:</span></span>

- <span data-ttu-id="38ee7-109">Microsoft 365、Teams、Exchange、SharePointなどのOneDrive</span><span class="sxs-lookup"><span data-stu-id="38ee7-109">Microsoft 365 services such as Teams, Exchange, SharePoint, and OneDrive</span></span>
- <span data-ttu-id="38ee7-110">Office、Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="38ee7-110">Office applications such as Word, Excel, and PowerPoint</span></span>
- <span data-ttu-id="38ee7-111">Windows 10エンドポイント</span><span class="sxs-lookup"><span data-stu-id="38ee7-111">Windows 10 endpoints</span></span>
- <span data-ttu-id="38ee7-112">Microsoft 以外のクラウド アプリ</span><span class="sxs-lookup"><span data-stu-id="38ee7-112">non-Microsoft cloud apps</span></span>
- <span data-ttu-id="38ee7-113">オンプレミスのファイル共有とオンプレミス のSharePoint。</span><span class="sxs-lookup"><span data-stu-id="38ee7-113">on-premises file shares and on-premises SharePoint.</span></span>

<span data-ttu-id="38ee7-114">Microsoft 365単純なテキスト スキャンではなく、ディープ コンテンツ分析を使用して機密性の高いアイテムを検出します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-114">Microsoft 365 detects sensitive items by using deep content analysis, not by just a simple text scan.</span></span> <span data-ttu-id="38ee7-115">コンテンツは、キーワードに一致するプライマリ データ、正規表現の評価、内部関数の検証、プライマリ データの一致に近いセカンダリ データの一致によって分析されます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-115">Content is analyzed for primary data matches to keywords, by the evaluation of regular expressions, by internal function validation, and by secondary data matches that are in proximity to the primary data match.</span></span> <span data-ttu-id="38ee7-116">その他の DLP では、機械学習アルゴリズムや他の方法を使用して、DLP ポリシーに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-116">Beyond that DLP also uses machine learning algorithms and other methods to detect content that matches your DLP policies.</span></span>
  
## <a name="dlp-is-part-of-the-larger-microsoft-365-compliance-offering"></a><span data-ttu-id="38ee7-117">DLP は、大規模なコンプライアンスMicrosoft 365の一部です</span><span class="sxs-lookup"><span data-stu-id="38ee7-117">DLP is part of the larger Microsoft 365 Compliance offering</span></span>

<span data-ttu-id="38ee7-118">Microsoft 365DLP は、機密性の高いMicrosoft 365場所や旅行場所の保護に役立つコンプライアンス ツールの 1 つにすすめることができます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-118">Microsoft 365 DLP is just one of the Microsoft 365 Compliance tools that you will use to help protect your sensitive items wherever they live or travel.</span></span> <span data-ttu-id="38ee7-119">コンプライアンス ツール セットの他のツールMicrosoft 365、そのツールがどのようにインテレートし、より良い作業を行うのかについて理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38ee7-119">You should understand the other tools in the Microsoft 365 Compliance tools set, how they interrelate, and work better together.</span></span>  <span data-ttu-id="38ee7-120">情報保護[プロセスMicrosoft 365詳細については、「](protect-information.md)コンプライアンス ツール」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38ee7-120">See, [Microsoft 365 compliance tools](protect-information.md) to learn more about the information protection process.</span></span>

## <a name="protective-actions-of-dlp-policies"></a><span data-ttu-id="38ee7-121">DLP ポリシーの保護アクション</span><span class="sxs-lookup"><span data-stu-id="38ee7-121">Protective actions of DLP policies</span></span>

<span data-ttu-id="38ee7-122">Microsoft 365DLP ポリシーは、ユーザーが安静時に機密性の高いアイテム、転送中の機密性の高いアイテム、または使用されている機密性の高いアイテムに対して行うアクティビティを監視し、保護アクションを実行する方法です。</span><span class="sxs-lookup"><span data-stu-id="38ee7-122">Microsoft 365 DLP policies are how you monitor the activities that users take on sensitive items at rest, sensitive items in transit, or sensitive items in use and take protective actions.</span></span> <span data-ttu-id="38ee7-123">たとえば、ユーザーが機密アイテムを未承認の場所にコピーしたり、ポリシーに記載されている電子メールや他の条件で医療情報を共有したりなど、禁止されたアクションを実行しようとすると、DLP は次の処理を実行できます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-123">For example, when a user attempts to take a prohibited action, like copying a sensitive item to an unapproved location or sharing medical information in an email or other conditions laid out in a policy, DLP can:</span></span>

- <span data-ttu-id="38ee7-124">機密性の高いアイテムを不適切に共有しようとしている可能性があるという警告を表示するポップアップ ポリシー ヒントをユーザーに表示する</span><span class="sxs-lookup"><span data-stu-id="38ee7-124">show a pop-up policy tip to the user that warns them that they may be trying to share a sensitive item inappropriately</span></span>
- <span data-ttu-id="38ee7-125">共有をブロックし、ポリシー ヒントを使用して、ユーザーがブロックを上書きしてユーザーの正当性を取得できます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-125">block the sharing and, via a policy tip, allow the user to override the block and capture the users' justification</span></span>
- <span data-ttu-id="38ee7-126">オーバーライド オプションなしで共有をブロックする</span><span class="sxs-lookup"><span data-stu-id="38ee7-126">block the sharing without the override option</span></span>
- <span data-ttu-id="38ee7-127">保存中のデータの場合、機密アイテムをロックして安全な検疫場所に移動できます</span><span class="sxs-lookup"><span data-stu-id="38ee7-127">for data at rest, sensitive items can be locked and moved to a secure quarantine location</span></span>
- <span data-ttu-id="38ee7-128">チャットTeams、機密情報は表示されません</span><span class="sxs-lookup"><span data-stu-id="38ee7-128">for Teams chat, the sensitive information will not be displayed</span></span>

<span data-ttu-id="38ee7-129">DLP 監視対象のすべてのアクティビティは、既定で監査Microsoft 365[に記録され](search-the-audit-log-in-security-and-compliance.md)、アクティビティ エクスプローラー[にルーティングされます](data-classification-activity-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="38ee7-129">All DLP monitored activities are recorded to the [Microsoft 365 Audit log](search-the-audit-log-in-security-and-compliance.md) by default and routed to [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="38ee7-130">ユーザーが DLP ポリシーの条件を満たすアクションを実行し、アラートが構成されている場合、DLP は DLP アラート管理ダッシュボードにアラート [を提供します](dlp-configure-view-alerts-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="38ee7-130">When a user performs an action that meets the criteria of a DLP policy, and you have alerts configured, DLP provides alerts in the [DLP alert management dashboard](dlp-configure-view-alerts-policies.md).</span></span>

## <a name="dlp-lifecycle"></a><span data-ttu-id="38ee7-131">DLP ライフサイクル</span><span class="sxs-lookup"><span data-stu-id="38ee7-131">DLP lifecycle</span></span>

<span data-ttu-id="38ee7-132">DLP の実装は、通常、これらの主要なフェーズに従います。</span><span class="sxs-lookup"><span data-stu-id="38ee7-132">A DLP implementation typically follows these major phases.</span></span>

- [<span data-ttu-id="38ee7-133">DLP を計画する</span><span class="sxs-lookup"><span data-stu-id="38ee7-133">Plan for DLP</span></span>](#plan-for-dlp)
- [<span data-ttu-id="38ee7-134">DLP の準備</span><span class="sxs-lookup"><span data-stu-id="38ee7-134">Prepare for DLP</span></span>](#prepare-for-dlp)
- [<span data-ttu-id="38ee7-135">実稼働環境でのポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="38ee7-135">Deploy your policies in production</span></span>](#deploy-your-policies-in-production)


<!--ADD DIAGRAM OF THE DLP LIFECYCLE WORK ON WITH MAS-->

### <a name="plan-for-dlp"></a><span data-ttu-id="38ee7-136">DLP を計画する</span><span class="sxs-lookup"><span data-stu-id="38ee7-136">Plan for DLP</span></span>

<span data-ttu-id="38ee7-137">Microsoft 365DLP の監視と保護は、ユーザーが毎日使用するアプリケーションにネイティブです。</span><span class="sxs-lookup"><span data-stu-id="38ee7-137">Microsoft 365 DLP monitoring and protection are native to the applications that users use every day.</span></span> <span data-ttu-id="38ee7-138">これにより、ユーザーがデータ損失防止の考え方やプラクティスに慣れていなくても、組織の機密性の高いアイテムを危険なアクティビティから保護できます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-138">This helps to protect your organizations' sensitive items from risky activities even if your users are unaccustomed to data loss prevention thinking and practices.</span></span> <span data-ttu-id="38ee7-139">組織とユーザーがデータ損失防止の実践に新しい場合、DLP の導入にはビジネス プロセスの変更が必要になる場合があります。また、ユーザーにはカルチャの変化が生じます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-139">If your organization and your users are new to data loss prevention practices, the adoption of DLP may require a change to your business processes and there will be a culture shift for your users.</span></span> <span data-ttu-id="38ee7-140">ただし、適切な計画、テスト、チューニングを行う場合、DLP ポリシーは機密アイテムを保護し、ビジネス プロセスの中断を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-140">But, with proper planning, testing and tuning, your DLP policies will protect your sensitive items while minimizing any potential business process disruptions.</span></span>

<span data-ttu-id="38ee7-141">**DLP のテクノロジ計画**</span><span class="sxs-lookup"><span data-stu-id="38ee7-141">**Technology planning for DLP**</span></span>

<span data-ttu-id="38ee7-142">テクノロジとしての DLP は、Microsoft 365 サービス、Windows 10 デバイス、オンプレミスのファイル共有、およびオンプレミス SharePoint 全体で、保存中のデータ、使用中のデータ、および動作中のデータを監視および保護できます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-142">Keep in mind that DLP as a technology can monitor and protect your data at rest, data in use and data in motion across Microsoft 365 services, Windows 10 devices, on-premises file shares, and on-premises SharePoint.</span></span> <span data-ttu-id="38ee7-143">さまざまな場所、監視および保護するデータの種類、およびポリシーの一致が発生した場合に実行するアクションに対する計画上の影響があります。</span><span class="sxs-lookup"><span data-stu-id="38ee7-143">There are planning implications for the different locations, the type of data you want to monitor and protect, and the actions to be taken when a policy match occurs.</span></span>  

<span data-ttu-id="38ee7-144">**DLP のビジネス プロセス計画**</span><span class="sxs-lookup"><span data-stu-id="38ee7-144">**Business processes planning for DLP**</span></span>

<span data-ttu-id="38ee7-145">DLP ポリシーでは、電子メールによる機密情報の不適切な共有など、禁止されているアクティビティをブロックできます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-145">DLP policies can block prohibited activities, like inappropriate sharing of sensitive information via email.</span></span> <span data-ttu-id="38ee7-146">DLP ポリシーを計画する場合は、機密性の高いアイテムに触れるビジネス プロセスを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38ee7-146">As you plan your DLP policies, you must identify the business processes that touch your sensitive items.</span></span> <span data-ttu-id="38ee7-147">ビジネス プロセスの所有者は、許可する必要がある適切なユーザーの動作と、保護すべき不適切なユーザーの動作を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-147">The business process owners can help you identify appropriate user behaviors that should be allowed and inappropriate user behaviors that should be protected against.</span></span> <span data-ttu-id="38ee7-148">ポリシーを計画し、テスト モードで展開し、より制限の厳しいモード[](data-classification-activity-explorer.md)で適用する前に、まずアクティビティ エクスプローラーを介して影響を評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38ee7-148">You should plan your policies and deploy them in test mode, and evaluate their impact via [activity explorer](data-classification-activity-explorer.md) first, before applying them in more restrictive modes.</span></span>

<span data-ttu-id="38ee7-149">**DLP の組織のカルチャ計画**</span><span class="sxs-lookup"><span data-stu-id="38ee7-149">**Organizational culture planning for DLP**</span></span>

<span data-ttu-id="38ee7-150">DLP の実装の成功は、ユーザーが十分に計画され調整されたポリシーと同じ量のデータ損失防止プラクティスをトレーニングし、慣れ親しんだものに依存します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-150">A successful DLP implementation is as much dependent on getting your users trained and acclimated to data loss prevention practices as it is on well planned and tuned policies.</span></span> <span data-ttu-id="38ee7-151">ユーザーの関与が大きすぎるので、ユーザーのトレーニングも計画してください。</span><span class="sxs-lookup"><span data-stu-id="38ee7-151">Since your users are heavily involved, be sure to plan for training for them too.</span></span> <span data-ttu-id="38ee7-152">ポリシーの適用をテスト モードから制限の厳しいモードに変更する前に、ポリシー ヒントを戦略的に使用してユーザーに対する認識を高めます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-152">You can strategically use policy tips to raise awareness with your users before changing the policy enforcement from test mode to more restrictive modes.</span></span>

<!--For more information on planning for DLP, including suggestions for deployment based on your needs and resources, see [Planning for Microsoft 365 data loss prevention](dlp-plan-for-dlp.md).-->

### <a name="prepare-for-dlp"></a><span data-ttu-id="38ee7-153">DLP の準備</span><span class="sxs-lookup"><span data-stu-id="38ee7-153">Prepare for DLP</span></span>

<span data-ttu-id="38ee7-154">DLP ポリシーは、保存中のデータ、使用されているデータ、次のような場所で動作中のデータに適用できます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-154">You can apply DLP policies to data at rest, data in use, and data in motion in locations, such as:</span></span>

- <span data-ttu-id="38ee7-155">Exchange Onlineメール</span><span class="sxs-lookup"><span data-stu-id="38ee7-155">Exchange Online email</span></span>
- <span data-ttu-id="38ee7-156">SharePoint Online サイト</span><span class="sxs-lookup"><span data-stu-id="38ee7-156">SharePoint Online sites</span></span>
- <span data-ttu-id="38ee7-157">OneDrive アカウント</span><span class="sxs-lookup"><span data-stu-id="38ee7-157">OneDrive accounts</span></span>
- <span data-ttu-id="38ee7-158">Teams チャットおよびチャネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="38ee7-158">Teams chat and channel messages</span></span>
- <span data-ttu-id="38ee7-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="38ee7-159">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="38ee7-160">Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="38ee7-160">Windows 10 devices</span></span>
- <span data-ttu-id="38ee7-161">オンプレミス リポジトリ</span><span class="sxs-lookup"><span data-stu-id="38ee7-161">On-premises repositories</span></span>

<span data-ttu-id="38ee7-162">それぞれの前提条件は異なります。</span><span class="sxs-lookup"><span data-stu-id="38ee7-162">Each one has different pre-requisites.</span></span> <span data-ttu-id="38ee7-163">一部の場所 (Exchange オンラインなど) の機密性の高いアイテムは、該当するポリシーを構成するだけで DLP の傘下に持ち込む可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38ee7-163">Sensitive items in some locations, like Exchange online, can be brought under the DLP umbrella by just configuring a policy that applies to them.</span></span> <span data-ttu-id="38ee7-164">オンプレミスのファイル リポジトリなど、他のユーザーには Azure Information Protection (AIP) スキャナーの展開が必要です。</span><span class="sxs-lookup"><span data-stu-id="38ee7-164">Others, such as on-premises file repositories require a deployment of Azure Information Protection (AIP) scanner.</span></span> <span data-ttu-id="38ee7-165">ブロックアクションをアクティブ化する前に、環境を準備し、下書きポリシーをコード化し、それらを徹底的にテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="38ee7-165">You'll need to prepare your environment, code draft policies, and test them thoroughly before activating any blocking actions.</span></span>

### <a name="deploy-your-policies-in-production"></a><span data-ttu-id="38ee7-166">実稼働環境でのポリシーの展開</span><span class="sxs-lookup"><span data-stu-id="38ee7-166">Deploy your policies in production</span></span>

#### <a name="design-your-policies"></a><span data-ttu-id="38ee7-167">ポリシーを設計する</span><span class="sxs-lookup"><span data-stu-id="38ee7-167">Design your policies</span></span>

<span data-ttu-id="38ee7-168">まず、コントロールの目標を定義し、それぞれのワークロードに適用する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-168">Start by defining your control objectives, and how they apply across each respective workload.</span></span> <span data-ttu-id="38ee7-169">目標を具現化するポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-169">Draft a policy that embodies your objectives.</span></span> <span data-ttu-id="38ee7-170">一度に 1 つのワークロードから、またはすべてのワークロードで自由に開始できます。まだ影響はありません。</span><span class="sxs-lookup"><span data-stu-id="38ee7-170">Feel free to start with one workload at a time, or across all workloads - there's no impact yet.</span></span>

#### <a name="implement-policy-in-test-mode"></a><span data-ttu-id="38ee7-171">テスト モードでのポリシーの実装</span><span class="sxs-lookup"><span data-stu-id="38ee7-171">Implement policy in test mode</span></span>

<span data-ttu-id="38ee7-172">コントロールをテスト モードで DLP ポリシーで実装して、コントロールの影響を評価します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-172">Evaluate the impact of the controls by implementing them with a DLP policy in test mode.</span></span> <span data-ttu-id="38ee7-173">テスト モードですべてのワークロードにポリシーを適用して、結果を得ることができますが、必要に応じて 1 つのワークロードから開始できます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-173">It's ok to apply the policy to all workloads in test mode, so that you can get the full breadth of results, but you can start with one workload if you need to.</span></span>

#### <a name="monitor-outcomes-and-fine-tune-the-policy"></a><span data-ttu-id="38ee7-174">結果を監視し、ポリシーを微調整する</span><span class="sxs-lookup"><span data-stu-id="38ee7-174">Monitor outcomes and fine-tune the policy</span></span>

<span data-ttu-id="38ee7-175">テスト モードでは、ポリシーの結果を監視し、コントロールの目標を満たして調整しながら、有効なユーザー ワークフローと生産性に悪影響を及ぼしたり、不注意に影響を与えなかったりします。</span><span class="sxs-lookup"><span data-stu-id="38ee7-175">While in test mode, monitor the outcomes of the policy and fine-tune it so that it meets your control objectives while ensuring you aren't adversely or inadvertently impacting valid user workflows and productivity.</span></span> <span data-ttu-id="38ee7-176">微調整する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-176">Here are some examples of things to fine-tune:</span></span>

- <span data-ttu-id="38ee7-177">スコープ内またはスコープ外の場所と人/場所を調整する</span><span class="sxs-lookup"><span data-stu-id="38ee7-177">adjusting the locations and people/places that are in or out of scope</span></span>
- <span data-ttu-id="38ee7-178">アイテムがポリシーと一致するかどうかを判断するために使用される条件と例外を調整する</span><span class="sxs-lookup"><span data-stu-id="38ee7-178">tune the conditions and exceptions that are used to determine if an item and what is being done with it matches the policy</span></span>
- <span data-ttu-id="38ee7-179">機密情報の定義/s</span><span class="sxs-lookup"><span data-stu-id="38ee7-179">the sensitive information definition/s</span></span>
- <span data-ttu-id="38ee7-180">アクション</span><span class="sxs-lookup"><span data-stu-id="38ee7-180">the actions</span></span>
- <span data-ttu-id="38ee7-181">制限のレベル</span><span class="sxs-lookup"><span data-stu-id="38ee7-181">the level of restrictions</span></span>
- <span data-ttu-id="38ee7-182">新しいコントロールを追加する</span><span class="sxs-lookup"><span data-stu-id="38ee7-182">add new controls</span></span>
- <span data-ttu-id="38ee7-183">新しいユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="38ee7-183">add new people</span></span>
- <span data-ttu-id="38ee7-184">新しい制限付きアプリを追加する</span><span class="sxs-lookup"><span data-stu-id="38ee7-184">add new restricted apps</span></span>
- <span data-ttu-id="38ee7-185">新しい制限付きサイトを追加する</span><span class="sxs-lookup"><span data-stu-id="38ee7-185">add new restricted sites</span></span>

#### <a name="enable-the-control-and-tune-your-policies"></a><span data-ttu-id="38ee7-186">コントロールを有効にしてポリシーを調整する</span><span class="sxs-lookup"><span data-stu-id="38ee7-186">Enable the control and tune your policies</span></span>

<span data-ttu-id="38ee7-187">ポリシーがすべての目標を満たしたら、有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="38ee7-187">Once the policy meets all your objectives, turn it on.</span></span> <span data-ttu-id="38ee7-188">引き続きポリシー アプリケーションの結果を監視し、必要に応じて調整します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-188">Continue to monitor the outcomes of the policy application and tune as needed.</span></span> <span data-ttu-id="38ee7-189">一般に、ポリシーは有効になってから約 1 時間後に有効になります。</span><span class="sxs-lookup"><span data-stu-id="38ee7-189">In general, policies take effect about an hour after being turned on.</span></span> 

<!--See, LINK TO topic for SLAs for location specific  details-->

## <a name="dlp-policy-configuration-overview"></a><span data-ttu-id="38ee7-190">DLP ポリシー構成の概要</span><span class="sxs-lookup"><span data-stu-id="38ee7-190">DLP policy configuration overview</span></span>

<span data-ttu-id="38ee7-191">DLP ポリシーを作成および構成する方法に柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="38ee7-191">You have flexibility in how you create and configure your DLP policies.</span></span> <span data-ttu-id="38ee7-192">定義済みのテンプレートから開始し、わずか数クリックでポリシーを作成するか、最初から独自のテンプレートを設計できます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-192">You can start from a predefined template and create a policy in just a few clicks or you can design your own from the ground up.</span></span> <span data-ttu-id="38ee7-193">どちらを選んでも、すべての DLP ポリシーは、ユーザーから同じ情報を必要とします。</span><span class="sxs-lookup"><span data-stu-id="38ee7-193">No matter which you choose, all DLP policies require the same information from you.</span></span>

1. <span data-ttu-id="38ee7-194">**監視対象を選択します**。 - Microsoft 365に役立つ多くの定義済みポリシー テンプレートが付属しているか、カスタム ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-194">**Choose what you want to monitor** - Microsoft 365 comes with many predefined policy templates to help you get started or you can create a custom policy.</span></span>
    - <span data-ttu-id="38ee7-195">定義済みのポリシー テンプレート: 財務データ、医療および健康データ、さまざまな国および地域のプライバシー データ。</span><span class="sxs-lookup"><span data-stu-id="38ee7-195">A predefined policy template: Financial data, Medical and health data, Privacy data all for various countries and regions.</span></span>
    - <span data-ttu-id="38ee7-196">使用可能な機密情報の種類、保持ラベル、および機密ラベルを使用するカスタム ポリシー。</span><span class="sxs-lookup"><span data-stu-id="38ee7-196">A custom policy that uses the available sensitive information types, retention labels, and sensitivity labels.</span></span>
2. <span data-ttu-id="38ee7-197">**監視する場所を選択する** - DLP で機密情報を監視する 1 つ以上の場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-197">**Choose where you want to monitor** - You pick one or more locations that you want DLP to monitor for sensitive information.</span></span> <span data-ttu-id="38ee7-198">次の情報を監視できます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-198">You can monitor:</span></span>
    
<span data-ttu-id="38ee7-199">場所</span><span class="sxs-lookup"><span data-stu-id="38ee7-199">location</span></span> | <span data-ttu-id="38ee7-200">包含 / 除外</span><span class="sxs-lookup"><span data-stu-id="38ee7-200">include/exclude by</span></span>|
|---------|---------|
|<span data-ttu-id="38ee7-201">Exchange メール</span><span class="sxs-lookup"><span data-stu-id="38ee7-201">Exchange email</span></span>| <span data-ttu-id="38ee7-202">配布グループ</span><span class="sxs-lookup"><span data-stu-id="38ee7-202">distribution groups</span></span>|
|<span data-ttu-id="38ee7-203">SharePoint サイト</span><span class="sxs-lookup"><span data-stu-id="38ee7-203">SharePoint sites</span></span> |<span data-ttu-id="38ee7-204">sites</span><span class="sxs-lookup"><span data-stu-id="38ee7-204">sites</span></span> |
|<span data-ttu-id="38ee7-205">OneDrive アカウント</span><span class="sxs-lookup"><span data-stu-id="38ee7-205">OneDrive accounts</span></span> |<span data-ttu-id="38ee7-206">アカウントまたは配布グループ</span><span class="sxs-lookup"><span data-stu-id="38ee7-206">accounts or distribution groups</span></span> |
|<span data-ttu-id="38ee7-207">Teams チャットおよびチャネル メッセージ</span><span class="sxs-lookup"><span data-stu-id="38ee7-207">Teams chat and channel messages</span></span> |<span data-ttu-id="38ee7-208">アカウント</span><span class="sxs-lookup"><span data-stu-id="38ee7-208">accounts</span></span> |
|<span data-ttu-id="38ee7-209">Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="38ee7-209">Windows 10 devices</span></span> |<span data-ttu-id="38ee7-210">ユーザーまたはグループ</span><span class="sxs-lookup"><span data-stu-id="38ee7-210">user or group</span></span> |
|<span data-ttu-id="38ee7-211">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="38ee7-211">Microsoft Cloud App Security</span></span> |<span data-ttu-id="38ee7-212">インスタンス</span><span class="sxs-lookup"><span data-stu-id="38ee7-212">instance</span></span> |
|<span data-ttu-id="38ee7-213">オンプレミス リポジトリ</span><span class="sxs-lookup"><span data-stu-id="38ee7-213">On-premises repositories</span></span>| <span data-ttu-id="38ee7-214">リポジトリ ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="38ee7-214">repository file path</span></span>|

3. <span data-ttu-id="38ee7-215">**アイテムに適用する** ポリシーに一致する必要がある条件を選択します。事前に構成された条件を受け入れるか、カスタム条件を定義できます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-215">**Choose the conditions that must be matched for a policy to be applied to an item** - you can accept pre-configured conditions or define custom conditions.</span></span> <span data-ttu-id="38ee7-216">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-216">Some examples are:</span></span>

- <span data-ttu-id="38ee7-217">アイテムには、特定のコンテキストで使用されている特定の種類の機密情報が含まれる。</span><span class="sxs-lookup"><span data-stu-id="38ee7-217">item contains a specified kind of sensitive information that is being used in a certain context.</span></span> <span data-ttu-id="38ee7-218">たとえば、組織外の受信者に電子メールで送信される 95 の社会保障番号。</span><span class="sxs-lookup"><span data-stu-id="38ee7-218">For example, 95 social security numbers being emailed to recipient outside your org.</span></span>
- <span data-ttu-id="38ee7-219">アイテムの感度ラベルが指定されている</span><span class="sxs-lookup"><span data-stu-id="38ee7-219">item has a specified sensitivity label</span></span>
- <span data-ttu-id="38ee7-220">機密情報を含むアイテムは、内部または外部で共有されます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-220">item with sensitive information is shared either internally or externally</span></span>

4. <span data-ttu-id="38ee7-221">**ポリシー条件が満たされた場合** に実行するアクションを選択します。アクションは、アクティビティが発生している場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="38ee7-221">**Choose the action to take when the policy conditions are met** - The actions depend on the location where the activity is happening.</span></span>  <span data-ttu-id="38ee7-222">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-222">Some examples are:</span></span>

- <span data-ttu-id="38ee7-223">SharePoint/Exchange/OneDrive: コンテンツにアクセスする組織フォーム外のユーザーをブロックします。</span><span class="sxs-lookup"><span data-stu-id="38ee7-223">SharePoint/Exchange/OneDrive: Block people who are outside your organization form accessing the content.</span></span> <span data-ttu-id="38ee7-224">ヒントをユーザーに表示し、DLP ポリシーで禁止されているアクションを実行しているという電子メール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-224">Show the user a tip and send them an email notification that they are taking an action that is prohibited by the DLP policy.</span></span>
- <span data-ttu-id="38ee7-225">Teamsチャットとチャネル: 機密情報がチャットまたはチャネルで共有されるのをブロックする</span><span class="sxs-lookup"><span data-stu-id="38ee7-225">Teams Chat and Channel: Block sensitive information from being shared in the chat or channel</span></span>
- <span data-ttu-id="38ee7-226">Windows 10デバイス: 機密性の高いアイテムの削除可能な USB デバイスへのコピーを監査または制限する</span><span class="sxs-lookup"><span data-stu-id="38ee7-226">Windows 10 Devices: Audit or restrict copying a sensitive item to a removeable USB device</span></span> 
- <span data-ttu-id="38ee7-227">Officeアプリ: 危険な動作を行っているユーザーに通知するポップアップを表示し、オーバーライドをブロックまたはブロックします。</span><span class="sxs-lookup"><span data-stu-id="38ee7-227">Office Apps: Show a popup notifying the user that they are engaging in a risky behavior and block or block but allow override.</span></span>
- <span data-ttu-id="38ee7-228">オンプレミスのファイル共有: ファイルを保存場所から検疫フォルダーに移動する</span><span class="sxs-lookup"><span data-stu-id="38ee7-228">On-premises file shares: move the file from where it is stored to a quarantine folder</span></span>

> [!NOTE]
> <span data-ttu-id="38ee7-229">条件と実行するアクションは、Rule と呼ばれるオブジェクトで定義されます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-229">The conditions and the actions to take are defined in an object called a Rule.</span></span>

<!--## Create a DLP policy

All DLP policies are created and maintained in the Microsoft 365 Compliance center. See, INSERT LINK TO ARTICLE THAT WILL START WALKING THEM THROUGH THE POLICY CREATION PROCEDURES for more information.-->

<span data-ttu-id="38ee7-230">コンプライアンス センターで DLP ポリシーを作成すると、そのポリシーは中央ポリシー ストアに格納され、次に示すさまざまなコンテンツ ソースに同期されます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-230">After you create a DLP policy in the Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="38ee7-231">Exchange Online、そこから Outlook on the web、Outlook。</span><span class="sxs-lookup"><span data-stu-id="38ee7-231">Exchange Online, and from there to Outlook on the web and Outlook.</span></span>
- <span data-ttu-id="38ee7-232">OneDrive for Business サイト。</span><span class="sxs-lookup"><span data-stu-id="38ee7-232">OneDrive for Business sites.</span></span>
- <span data-ttu-id="38ee7-233">SharePoint Online サイト。</span><span class="sxs-lookup"><span data-stu-id="38ee7-233">SharePoint Online sites.</span></span>
- <span data-ttu-id="38ee7-234">Office デスクトップ プログラム (Excel、PowerPoint、Word)。</span><span class="sxs-lookup"><span data-stu-id="38ee7-234">Office desktop programs (Excel, PowerPoint, and Word).</span></span>
- <span data-ttu-id="38ee7-235">Microsoft Teams チャネルおよびチャット メッセージ。</span><span class="sxs-lookup"><span data-stu-id="38ee7-235">Microsoft Teams channels and chat messages.</span></span>
    
<span data-ttu-id="38ee7-236">ポリシーが適切な場所に同期されると、コンテンツの評価とアクションの適用が開始されます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-236">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>

## <a name="viewing-policy-application-results"></a><span data-ttu-id="38ee7-237">ポリシー アプリケーションの結果の表示</span><span class="sxs-lookup"><span data-stu-id="38ee7-237">Viewing policy application results</span></span>

<span data-ttu-id="38ee7-238">DLP は、監視、ポリシーの一致Microsoft 365アクション、およびユーザー アクティビティから、膨大な量の情報をレポートします。</span><span class="sxs-lookup"><span data-stu-id="38ee7-238">DLP reports a vast amount of information into Microsoft 365 from monitoring, policy matches and actions, and user activities.</span></span> <span data-ttu-id="38ee7-239">機密アイテムに対して行うポリシーとトリアージアクションを調整するには、その情報を使用して処理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38ee7-239">You'll need to consume and act on that information to tune your policies and triage actions taken on sensitive items.</span></span> <span data-ttu-id="38ee7-240">テレメトリは、コンプライアンス センター[](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center)監査ログMicrosoft 365最初に処理され、さまざまなレポート ツールに移動します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-240">The telemetry goes into the [Microsoft 365 Compliance center Audit Logs](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center) first, is processed, and makes its way to different reporting tools.</span></span> <span data-ttu-id="38ee7-241">各レポート ツールの目的は異なります。</span><span class="sxs-lookup"><span data-stu-id="38ee7-241">Each reporting tool has a different purpose.</span></span>  

### <a name="dlp-alerts-dashboard"></a><span data-ttu-id="38ee7-242">DLP アラート ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="38ee7-242">DLP Alerts Dashboard</span></span>

<span data-ttu-id="38ee7-243">DLP が機密性の高いアイテムに対してアクションを実行すると、構成可能なアラートを介してそのアクションの通知を受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38ee7-243">When DLP takes an action on a sensitive item, you can be notified of that action via a configurable alert.</span></span> <span data-ttu-id="38ee7-244">コンプライアンス センターでは、これらのアラートをメールボックスに重ね合せするのではなく [、DLP アラート](dlp-configure-view-alerts-policies.md)管理ダッシュボードで利用できます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-244">Rather than having these alerts pile up in a mailbox for you to sift through, the Compliance center makes them available in the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span> <span data-ttu-id="38ee7-245">DLP アラート ダッシュボードを使用して、アラートの構成、確認、トリアージ、DLP アラートの解決の追跡を行います。</span><span class="sxs-lookup"><span data-stu-id="38ee7-245">Use the DLP Alerts dashboard to configure alerts, review them, triage them and track resolution of DLP Alerts.</span></span> <span data-ttu-id="38ee7-246">ポリシーの一致と、デバイスからのアクティビティによって生成されるアラートのWindows 10します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-246">Here's an example of alerts generated by policy matches and activities from Windows 10 devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="38ee7-247">![警告情報](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="38ee7-247">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="38ee7-248">同じダッシュボードで、リッチ メタデータに関連付けられたイベントの詳細を表示することもできます</span><span class="sxs-lookup"><span data-stu-id="38ee7-248">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="38ee7-249">![イベント情報](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="38ee7-249">![event info](../media/Event-info-1.png)</span></span>

### <a name="reports"></a><span data-ttu-id="38ee7-250">レポート</span><span class="sxs-lookup"><span data-stu-id="38ee7-250">Reports</span></span>

<span data-ttu-id="38ee7-251">[DLP レポートは、時間](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention)の流れによって広い傾向を示し、以下に関する具体的な分析情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-251">The [DLP reports](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention) show broad trends over time and give specific insights into:</span></span>

- <span data-ttu-id="38ee7-252">**DLP ポリシー 時間の間に** 一致し、日付範囲、場所、ポリシー、またはアクションでフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="38ee7-252">**DLP Policy Matches** over time and filter by date range, location, policy, or action</span></span>
- <span data-ttu-id="38ee7-253">**DLP インシデントの一致** では、時間の長い間一致が表示されますが、ポリシー ルールではなくアイテムのピボットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38ee7-253">**DLP incident matches** also shows matches over time, but pivots on the items rather than the policy rules.</span></span>
- <span data-ttu-id="38ee7-254">**DLP の誤検知と上書** きは、誤検知の数と、構成されている場合は、ユーザーの正当性と共にユーザーオーバーライドを示します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-254">**DLP false positives and overrides** shows the count of false positives and, if configured, user-overrides along with the user justification.</span></span>

### <a name="dlp-activity-explorer"></a><span data-ttu-id="38ee7-255">DLP アクティビティ エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="38ee7-255">DLP Activity Explorer</span></span>

<span data-ttu-id="38ee7-256">DLP ページの [アクティビティ エクスプローラー]タブには *、DLPRuleMatch に対するアクティビティ フィルターのプリセットがあります*。</span><span class="sxs-lookup"><span data-stu-id="38ee7-256">The Activity explorer tab on the DLP page has the *Activity* filter preset to *DLPRuleMatch*.</span></span> <span data-ttu-id="38ee7-257">このツールを使用して、機密情報を含むコンテンツやラベルが適用されているコンテンツに関連するアクティビティ (ラベルの変更、ファイルの変更、ルールの一致など) を確認します。</span><span class="sxs-lookup"><span data-stu-id="38ee7-257">Use this tool to review activity related to content that contains sensitive info or has labels applied, such as what labels were changed, files were modified, and matched a rule.</span></span>

![<span data-ttu-id="38ee7-258">DLPRuleMatch スコープアクティビティ エクスプローラーのスクリーンショット</span><span class="sxs-lookup"><span data-stu-id="38ee7-258">screenshot of the DLPRuleMatch scoped activity explorer</span></span> ](../media/dlp-activity-explorer.png)

<span data-ttu-id="38ee7-259">詳細については、「アクティビティ エクスプローラーの [使用を開始する」を参照してください。](data-classification-activity-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="38ee7-259">For more information, see [Get started with activity explorer](data-classification-activity-explorer.md)</span></span>

<span data-ttu-id="38ee7-260">DLP の詳細についてはMicrosoft 365参照してください。</span><span class="sxs-lookup"><span data-stu-id="38ee7-260">To learn more about Microsoft 365 DLP, see:</span></span>

- [<span data-ttu-id="38ee7-261">Microsoft 365 のエンドポイントのデータ損失防止についての詳細情報</span><span class="sxs-lookup"><span data-stu-id="38ee7-261">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="38ee7-262">Microsoft Teams の既定のデータ損失防止ポリシーについての詳細情報 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="38ee7-262">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>](dlp-teams-default-policy.md)
- [<span data-ttu-id="38ee7-263">Microsoft 365 のエンドポイントのデータ損失防止について学ぶ (プレビュー) </span><span class="sxs-lookup"><span data-stu-id="38ee7-263">Learn about the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="38ee7-264">Microsoft Compliance Extension (プレビュー) の詳細情報</span><span class="sxs-lookup"><span data-stu-id="38ee7-264">Learn about the Microsoft Compliance Extension (preview)</span></span>](dlp-chrome-learn-about.md)
- [<span data-ttu-id="38ee7-265">データ損失防止の警告ダッシュボードについて</span><span class="sxs-lookup"><span data-stu-id="38ee7-265">Learn about the data loss prevention Alerts dashboard</span></span>](dlp-alerts-dashboard-learn.md)

<span data-ttu-id="38ee7-266">データ損失防止を使用してデータ プライバシー規制に準拠する方法については、「[](../solutions/information-protection-deploy.md)データプライバシー規制に関する情報保護を展開する (Microsoft 365 (aka.ms/m365dataprivacy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38ee7-266">To learn how to use data loss prevention to comply with data privacy regulations, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).</span></span>