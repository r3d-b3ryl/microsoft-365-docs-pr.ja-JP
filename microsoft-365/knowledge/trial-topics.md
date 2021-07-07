---
title: Microsoft Viva Topics の試用版を実行する
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: ''
search.appverid: ''
localization_priority: Normal
description: 組織の Microsoft Viva Topics の試用版パイロット プログラムを計画して実行する方法について説明します。
ms.openlocfilehash: 128e82e7664a76baa55d37e983319c9f344624fd
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327115"
---
# <a name="run-a-trial-of-microsoft-viva-topics"></a><span data-ttu-id="04b30-103">Microsoft Viva Topics の試用版を実行する</span><span class="sxs-lookup"><span data-stu-id="04b30-103">Run a trial of Microsoft Viva Topics</span></span>

<span data-ttu-id="04b30-104">この記事では、組織にビバ トピックを展開する試用版パイロット プログラムをセットアップして実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="04b30-104">This article describes how to set up and run a trial pilot program to deploy Viva Topics to your organization.</span></span> <span data-ttu-id="04b30-105">この記事では、試用版のベスト プラクティスも推奨します。</span><span class="sxs-lookup"><span data-stu-id="04b30-105">This article also recommends best practices for the trial.</span></span>

## <a name="sign-up-for-a-trial"></a><span data-ttu-id="04b30-106">試用版にサインアップする</span><span class="sxs-lookup"><span data-stu-id="04b30-106">Sign up for a trial</span></span>

<span data-ttu-id="04b30-107">試用版は、次のいずれかのソースから一般公開されています。</span><span class="sxs-lookup"><span data-stu-id="04b30-107">Trials are publicly available from one of the following sources.</span></span> <span data-ttu-id="04b30-108">これらの試用版では、25 人のユーザーが 30 日間、ビバ トピックスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="04b30-108">These trials offer 25 users access to Viva Topics for 30 days.</span></span>

- <span data-ttu-id="04b30-109">[Viva Topics 製品ページ](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)</span><span class="sxs-lookup"><span data-stu-id="04b30-109">The [Viva Topics product page](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)</span></span>

- <span data-ttu-id="04b30-110">この[Microsoft 365 管理センター](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="04b30-110">The [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
    1.  <span data-ttu-id="04b30-111">[Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="04b30-111">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    2.  <span data-ttu-id="04b30-112">[課金購入 **サービス**  >  **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="04b30-112">Go to **Billing** > **Purchase Services**.</span></span>
    3.  <span data-ttu-id="04b30-113">**[アドオン]** セクションまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="04b30-113">Scroll down to the **Add-Ons** section.</span></span>
    4.  <span data-ttu-id="04b30-114">[トピック エクスペリエンス **] タイルで** 、[詳細] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="04b30-114">On the **Topic Experiences** tile, select **Details**.</span></span>
    5.  <span data-ttu-id="04b30-115">**[無料試用版を取得]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="04b30-115">Select **Get free trial**.</span></span>
    6.  <span data-ttu-id="04b30-116">残りのウィザードの手順に従って、試用版を確認します。</span><span class="sxs-lookup"><span data-stu-id="04b30-116">Follow the remaining wizard steps to confirm the trial.</span></span>

<span data-ttu-id="04b30-117">試用版をアクティブにするには、Microsoft 365管理者または課金管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="04b30-117">You must be a Microsoft 365 global administrator or billing administrator to activate a trial.</span></span>

> [!NOTE]
> <span data-ttu-id="04b30-118">パブリック 試用版は、テナントごとに 1 回のみMicrosoft 365できます。</span><span class="sxs-lookup"><span data-stu-id="04b30-118">Public trials can only be added once for each Microsoft 365 tenant.</span></span>

### <a name="who-should-be-involved-in-a-trial"></a><span data-ttu-id="04b30-119">Whoに関与する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="04b30-119">Who should be involved in a trial</span></span>

|<span data-ttu-id="04b30-120">役割</span><span class="sxs-lookup"><span data-stu-id="04b30-120">Role</span></span>  |<span data-ttu-id="04b30-121">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="04b30-121">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="04b30-122">Microsoft 365管理者または請求管理者</span><span class="sxs-lookup"><span data-stu-id="04b30-122">Microsoft 365 global admin or billing admin</span></span>  |   <span data-ttu-id="04b30-123">試用版をアクティブ化し、ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="04b30-123">Activate the trial and assign licenses</span></span>      |
|<span data-ttu-id="04b30-124">Microsoft 365管理者または管理者SharePointする</span><span class="sxs-lookup"><span data-stu-id="04b30-124">Microsoft 365 global admin or SharePoint admin</span></span>    |       <span data-ttu-id="04b30-125">ビバ トピックの構成とトピック センターの作成</span><span class="sxs-lookup"><span data-stu-id="04b30-125">Configure  Viva Topics and create topic centers</span></span>  |
|<span data-ttu-id="04b30-126">ビジネス ユーザー</span><span class="sxs-lookup"><span data-stu-id="04b30-126">Business user</span></span>     |   <span data-ttu-id="04b30-127">ナレッジ マネージャー、トピック投稿者、トピックコンシューマーの役割を実行する</span><span class="sxs-lookup"><span data-stu-id="04b30-127">Perform knowledge manager, topic contributor, and topic consumer roles</span></span>      |

### <a name="before-you-activate-a-trial"></a><span data-ttu-id="04b30-128">試用版をアクティブにする前に</span><span class="sxs-lookup"><span data-stu-id="04b30-128">Before you activate a trial</span></span>

<span data-ttu-id="04b30-129">計画は、ビバ トピックスの効果的な試用に不可欠です。</span><span class="sxs-lookup"><span data-stu-id="04b30-129">Planning is essential for an effective trial of Viva Topics.</span></span> <span data-ttu-id="04b30-130">試用期間には制限があり、トピックの検出とトピックの品質、管理、およびエンド ユーザー エクスペリエンスの探索を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="04b30-130">The trial period is limited and must include topic discovery and exploring topic quality, management, and end-user experiences.</span></span>

#### <a name="discovery"></a><span data-ttu-id="04b30-131">Discovery</span><span class="sxs-lookup"><span data-stu-id="04b30-131">Discovery</span></span>

<span data-ttu-id="04b30-132">試用版中のトピック検出の構成には、次の 2 つの大きな戦略オプションがあります。</span><span class="sxs-lookup"><span data-stu-id="04b30-132">There are two high-level strategy options for configuration of topic discovery during a trial:</span></span>

- <span data-ttu-id="04b30-133">オンライン コンテンツのすべてまたは大部分SharePointインデックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="04b30-133">Index all or most of your SharePoint Online content.</span></span>
   - <span data-ttu-id="04b30-134">大規模なテナントは、完全にインデックスを作成するために最大 2 週間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="04b30-134">Large tenants can take up to two weeks to fully index.</span></span> <span data-ttu-id="04b30-135">この期間を通じてトピックが段階的に生成される一方で、完全なインデックス作成では試用期間の半分まで消費される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04b30-135">While topics will be generated incrementally throughout this period, full indexing could consume up to half the trial period.</span></span>
   - <span data-ttu-id="04b30-136">大量のデータを持つテナントの場合、このオプションを使用すると、非常に多くのトピック (数万件) が生成される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04b30-136">For tenants with a significant volume of data, this option can produce a very large number of topics, perhaps tens of thousands.</span></span>

- <span data-ttu-id="04b30-137">インデックス作成用のサイトSharePointを特定します。</span><span class="sxs-lookup"><span data-stu-id="04b30-137">Identify a subset of your SharePoint sites for indexing.</span></span>

<span data-ttu-id="04b30-138">これらの戦略の選択は、次の 2 つの要因のバランスです。</span><span class="sxs-lookup"><span data-stu-id="04b30-138">The choice of these strategies is a balance of the following two factors:</span></span>

- <span data-ttu-id="04b30-139">意味のあるトピックを生成するのに十分なデータを持つ。</span><span class="sxs-lookup"><span data-stu-id="04b30-139">Having enough data to generate meaningful topics.</span></span> <span data-ttu-id="04b30-140">ビバ トピックの AI は、10,000 を超えるドキュメントを持つ大規模なデータセットに対応するために調整されています。</span><span class="sxs-lookup"><span data-stu-id="04b30-140">The AI in Viva Topics is tuned to work on large datasets, ideally ones that have more than 10,000 documents.</span></span>
- <span data-ttu-id="04b30-141">試用期間中に多くのトピックが生成されないので、利用可能な期間中に評価する方が圧倒的です。</span><span class="sxs-lookup"><span data-stu-id="04b30-141">Not generating so many topics during the trial period that evaluating them during the available time period is overwhelming.</span></span>

<span data-ttu-id="04b30-142">ほとんどの組織では、2 つ目の戦略が最適な結果を生み出します。</span><span class="sxs-lookup"><span data-stu-id="04b30-142">For most organizations, the second strategy produces the best outcome.</span></span>

> [!NOTE]
> <span data-ttu-id="04b30-143">AI で必要なドキュメントの数が原因で、実稼働テナントでビバ トピックスの試用版を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="04b30-143">Due to the number of documents required by the AI, we recommend that you run Viva Topics trials on a production tenant.</span></span> <span data-ttu-id="04b30-144">この期間中のテナントのパフォーマンスに影響はありません。</span><span class="sxs-lookup"><span data-stu-id="04b30-144">There’s no impact on the performance of the tenant during this period.</span></span> <span data-ttu-id="04b30-145">試用版ライセンスを持つユーザーだけが、Viva Topics ユーザー エクスペリエンスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="04b30-145">Only users who have a trial license can access Viva Topics user experiences.</span></span>

#### <a name="roles"></a><span data-ttu-id="04b30-146">Roles</span><span class="sxs-lookup"><span data-stu-id="04b30-146">Roles</span></span>

<span data-ttu-id="04b30-147">試用版では、次の表に示す 3 つの役割をアクティブにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="04b30-147">During the trial, there are three roles that must be active, which are described in the following table.</span></span>

|<span data-ttu-id="04b30-148">役割</span><span class="sxs-lookup"><span data-stu-id="04b30-148">Role</span></span>  |<span data-ttu-id="04b30-149">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="04b30-149">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="04b30-150">知識マネージャー</span><span class="sxs-lookup"><span data-stu-id="04b30-150">Knowledge manager</span></span>     |   <span data-ttu-id="04b30-151">トピックのライフサイクル ステージを制御する。トピックの確認と削除。トピック投稿者のコミュニティ マネージャーとして機能する</span><span class="sxs-lookup"><span data-stu-id="04b30-151">Control the lifecycle stages of topics; confirm and remove topics; act as a community manager for topic contributors</span></span>      |
|<span data-ttu-id="04b30-152">トピック共同作成者</span><span class="sxs-lookup"><span data-stu-id="04b30-152">Topic contributor</span></span>    |      <span data-ttu-id="04b30-153">コンテンツの主題の専門家は、次の処理を行います。</span><span class="sxs-lookup"><span data-stu-id="04b30-153">Content subject matter experts, who can:</span></span><br> <span data-ttu-id="04b30-154">トピックを確認して AI 定義コンテンツの品質を評価する</span><span class="sxs-lookup"><span data-stu-id="04b30-154">Review topics to evaluate the quality of AI-defined content</span></span><br><span data-ttu-id="04b30-155">追加のコンテンツで検出されたトピックを管理する</span><span class="sxs-lookup"><span data-stu-id="04b30-155">Curate discovered topics with additional content</span></span><br><span data-ttu-id="04b30-156">AI によって検出されなかった追加のトピックを作成する</span><span class="sxs-lookup"><span data-stu-id="04b30-156">Create additional topics that weren’t discovered by AI</span></span>   |
|<span data-ttu-id="04b30-157">トピックコンシューマ</span><span class="sxs-lookup"><span data-stu-id="04b30-157">Topic consumer</span></span>    |     <span data-ttu-id="04b30-158">ページのハイライトと検索でトピックを使用する</span><span class="sxs-lookup"><span data-stu-id="04b30-158">Consume topics through page highlights and search</span></span><br><span data-ttu-id="04b30-159">提示されたトピックの値に関するフィードバックを提供する</span><span class="sxs-lookup"><span data-stu-id="04b30-159">Provide feedback on the value of the topics presented</span></span>    |

#### <a name="expected-topics"></a><span data-ttu-id="04b30-160">予想されるトピック</span><span class="sxs-lookup"><span data-stu-id="04b30-160">Expected topics</span></span>

<span data-ttu-id="04b30-161">これは前提にのみ基づいていなくても、AI によって生成されるトピックを文書化する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="04b30-161">It can be useful to document the topics you expect to be generated by the AI, even if this is based only on assumptions.</span></span> <span data-ttu-id="04b30-162">このタスクは、中小企業を簡単に識別できるSharePointサイトの定義されたサブセットをインデックス化するときに最も簡単に完了します。</span><span class="sxs-lookup"><span data-stu-id="04b30-162">This task is most easily completed when you index a defined subset of your SharePoint sites for which SMEs can be easily identified.</span></span>

<span data-ttu-id="04b30-163">文書化されたリストを使用すると、次の情報を得るのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="04b30-163">Having a documented list will help you to:</span></span>

- <span data-ttu-id="04b30-164">AI で生成されたトピックの一覧を確認します。予想よりも大きい場合があります。</span><span class="sxs-lookup"><span data-stu-id="04b30-164">Review the list of AI-generated topics, which might be larger than you expect.</span></span>
- <span data-ttu-id="04b30-165">手動で作成する必要があるトピック、またはキュレーションの優先順位を知る。</span><span class="sxs-lookup"><span data-stu-id="04b30-165">Know the topics you might need to manually create or that are priorities for curation.</span></span>

<span data-ttu-id="04b30-166">ビバ トピックの展開または試用版の成功には、AI 定義のトピックと人間が作成したトピックが常に組み合う必要があります。</span><span class="sxs-lookup"><span data-stu-id="04b30-166">There will always be a need for a mixture of AI-defined and human-created topics in a successful deployment or trial of Viva Topics.</span></span>

## <a name="activate-a-trial"></a><span data-ttu-id="04b30-167">試用版をアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="04b30-167">Activate a trial</span></span>

<span data-ttu-id="04b30-168">試用版を開始する場合は、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="04b30-168">When you initiate a trial, you need to:</span></span>

- <span data-ttu-id="04b30-169">関連するユーザーにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="04b30-169">Assign licenses to the relevant users.</span></span>
- <span data-ttu-id="04b30-170">ビ [バ トピックの追加](set-up-topic-experiences.md) セットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="04b30-170">Perform [additional setup](set-up-topic-experiences.md) of Viva Topics.</span></span>

<span data-ttu-id="04b30-171">試用版がアクティブ化されると、トピックの検出プロセスが開始されます。</span><span class="sxs-lookup"><span data-stu-id="04b30-171">When the trial is activated, the topic discovery process begins.</span></span>

## <a name="during-a-trial"></a><span data-ttu-id="04b30-172">試用版中</span><span class="sxs-lookup"><span data-stu-id="04b30-172">During a trial</span></span>

<span data-ttu-id="04b30-173">試用期間は、Viva Topics の次のコンポーネントを評価するために使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04b30-173">The trial period should be used to evaluate the following components of Viva Topics:</span></span>

- <span data-ttu-id="04b30-174">AI が推奨するトピックとトピック コンテンツ</span><span class="sxs-lookup"><span data-stu-id="04b30-174">The AI-suggested topics and topic content</span></span>
- <span data-ttu-id="04b30-175">エンド ユーザー エクスペリエンス、最新のページ、およびページ内SharePointトピック カードのMicrosoft Search</span><span class="sxs-lookup"><span data-stu-id="04b30-175">The end-user experiences, surfacing topic cards on modern SharePoint pages and in Microsoft Search</span></span>

<span data-ttu-id="04b30-176">計画では、次の要因を考慮します。</span><span class="sxs-lookup"><span data-stu-id="04b30-176">Consider these factors:</span></span>

- <span data-ttu-id="04b30-177">Viva Topics が最大値を提供するには、トピック内のコンテンツが AI で定義されたコンテンツと人間が管理するコンテンツの組み合わせである必要があります。</span><span class="sxs-lookup"><span data-stu-id="04b30-177">For Viva Topics to deliver the maximum value, the content in topics needs to be a combination of AI-defined content and human-curated content.</span></span>
- <span data-ttu-id="04b30-178">すべてのユーザー エクスペリエンスは "アクセス許可がトリミングされました" ([トピックの管理] ページのナレッジ マネージャーのビュー **を含** む)。</span><span class="sxs-lookup"><span data-stu-id="04b30-178">All user experiences are “permission trimmed” (including the knowledge manager’s view on the **Manage topics** page).</span></span> <span data-ttu-id="04b30-179">ユーザーは、トピックの生成に使用されたリソースの一部を表示するためのアクセス許可がある場合にのみ、トピックを表示します。</span><span class="sxs-lookup"><span data-stu-id="04b30-179">Users will only see a topic if they have permissions to view some of the resources that were used to generate the topic.</span></span> <span data-ttu-id="04b30-180">つまり、異なるユーザーが同じトピック ページに異なるコンテンツを表示する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04b30-180">This means that different users might see different content on the same topic page.</span></span>
- <span data-ttu-id="04b30-181">ユーザーには、[トピックの管理] ページに同じ名前のトピック **が複数表示される場合** があります。</span><span class="sxs-lookup"><span data-stu-id="04b30-181">Users might see multiple topics that have the same name in the **Manage topics** page.</span></span> <span data-ttu-id="04b30-182">これらのトピックは必ずしも重複しているわけではないが、2 つの異なるプロジェクトで使用されるプロジェクト コード名など、データ内の複数のコンテキストで使用される単一の用語が理由である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="04b30-182">These topics aren't necessarily duplicates but might be because of a single term that’s used in multiple contexts in the data, such as a project code name that’s used by two distinct projects.</span></span>

## <a name="after-a-trial"></a><span data-ttu-id="04b30-183">試用版の後</span><span class="sxs-lookup"><span data-stu-id="04b30-183">After a trial</span></span>

<span data-ttu-id="04b30-184">試用版の結果に基づいて、ビバ トピックスの生産使用に進むかどうかを決定できます。</span><span class="sxs-lookup"><span data-stu-id="04b30-184">Based on the outcome of the trial, you can decide whether to proceed to production use of Viva Topics.</span></span>

### <a name="proceed-to-production-use"></a><span data-ttu-id="04b30-185">実稼働環境の使用に進む</span><span class="sxs-lookup"><span data-stu-id="04b30-185">Proceed to production use</span></span>

<span data-ttu-id="04b30-186">サービスの継続性を確保するには、必要な数のライセンスを購入し、それらのライセンスをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="04b30-186">To ensure continuity of service, you must purchase the required number of licenses and assign those licenses to users.</span></span> <span data-ttu-id="04b30-187">試用期間の最後に完全なライセンスを持ってない試用版ユーザーは、ビバトピックスのエクスペリエンスにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="04b30-187">Trial users who don’t have a full license at the end of the trial period won’t be able to access any Viva Topics experiences.</span></span>

### <a name="dont-proceed-to-production-use"></a><span data-ttu-id="04b30-188">実稼働環境での使用に進む</span><span class="sxs-lookup"><span data-stu-id="04b30-188">Don’t proceed to production use</span></span>

<span data-ttu-id="04b30-189">試用版に従ってライセンスを購入しない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="04b30-189">If you don’t purchase licenses following the trial:</span></span>

- <span data-ttu-id="04b30-190">トピックの検出が停止します。</span><span class="sxs-lookup"><span data-stu-id="04b30-190">Topic discovery will stop.</span></span>
- <span data-ttu-id="04b30-191">トピックのハイライトやカードは表示されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="04b30-191">Users will no longer see topic highlights or cards.</span></span>
- <span data-ttu-id="04b30-192">トピック センターは削除されませんが、推奨されるトピックとトピックの管理エクスペリエンスは使用できません。</span><span class="sxs-lookup"><span data-stu-id="04b30-192">The topic center won’t be deleted, but the suggested topics and manage topics experiences won’t be available.</span></span>
- <span data-ttu-id="04b30-193">AI で定義されたトピックは失われます。</span><span class="sxs-lookup"><span data-stu-id="04b30-193">Any AI-defined topics will be lost.</span></span>
- <span data-ttu-id="04b30-194">トピック投稿者によって編集されたトピックは、トピック センター ページ ライブラリに残ります。</span><span class="sxs-lookup"><span data-stu-id="04b30-194">Topics that have been edited by a topic contributor will remain in the topic center pages library.</span></span> <span data-ttu-id="04b30-195">手動で提供されたコンテンツだけがこれらのページに残りますが、AI が推奨するコンテンツは残されません。</span><span class="sxs-lookup"><span data-stu-id="04b30-195">Only the manually provided content will remain on these pages, not any AI-suggested content.</span></span>

## <a name="see-also"></a><span data-ttu-id="04b30-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="04b30-196">See also</span></span>

[<span data-ttu-id="04b30-197">Microsoft Viva Topics の導入を開始する</span><span class="sxs-lookup"><span data-stu-id="04b30-197">Get started driving adoption of Microsoft Viva Topics</span></span>](topics-adoption-getstarted.md)

