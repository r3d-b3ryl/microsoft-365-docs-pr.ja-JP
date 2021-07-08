---
title: Microsoft SharePoint Syntex の試用版を実行SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: 組織のユーザー向け試用版パイロット プログラムを計画SharePoint Syntexする方法について学習します。
ms.openlocfilehash: 2668c0c85d6b8c73d377ac9efffc7f777fc7add6
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327116"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a><span data-ttu-id="b8c1f-103">Microsoft SharePoint Syntex の試用版を実行SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="b8c1f-103">Run a trial of Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="b8c1f-104">この記事では、試用版パイロット プログラムをセットアップして実行して、組織にSharePoint Syntexする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-104">This article describes how to set up and run a trial pilot program to deploy SharePoint Syntex in your organization.</span></span> <span data-ttu-id="b8c1f-105">また、試用版のベスト プラクティスも推奨します。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-105">It also recommends best practices for the trial.</span></span>

## <a name="sign-up-for-a-trial"></a><span data-ttu-id="b8c1f-106">試用版にサインアップする</span><span class="sxs-lookup"><span data-stu-id="b8c1f-106">Sign up for a trial</span></span>

<span data-ttu-id="b8c1f-107">この試用版では、SharePoint Syntex 30 日間、300 人のユーザーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-107">The trial of SharePoint Syntex gives access to 300 users for 30 days.</span></span>

> [!NOTE]
> <span data-ttu-id="b8c1f-108">最大 300 人のユーザーが試用版に含まれており、100 万の AI ビルダー クレジットが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-108">Up to 300 users are included in the trial to ensure the automatic addition of 1 million AI Builder credits.</span></span> <span data-ttu-id="b8c1f-109">試用版を成功するには、300 人のユーザーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-109">You do not have to include 300 users for a trial to succeed.</span></span>

<span data-ttu-id="b8c1f-110">試用版は、次のいずれかのソースから取得できます。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-110">You can get the trial version from one of the following sources:</span></span>

- <span data-ttu-id="b8c1f-111">[[SharePoint Syntex] ページ](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)</span><span class="sxs-lookup"><span data-stu-id="b8c1f-111">The [SharePoint Syntex product page](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)</span></span>

- <span data-ttu-id="b8c1f-112">この[Microsoft 365 管理センター](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="b8c1f-112">The [Microsoft 365 admin center](https://admin.microsoft.com)</span></span>
    1.  <span data-ttu-id="b8c1f-113">[Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-113">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
    2.  <span data-ttu-id="b8c1f-114">[課金購入 **サービス**  >  **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-114">Go to **Billing** > **Purchase Services**.</span></span>
    3.  <span data-ttu-id="b8c1f-115">**[アドオン]** セクションまで下にスクロールします。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-115">Scroll down to the **Add-Ons** section.</span></span>
    4.  <span data-ttu-id="b8c1f-116">[詳細] タイルSharePoint Syntex[詳細] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-116">On the SharePoint Syntex tile, select **Details**.</span></span>
    5.  <span data-ttu-id="b8c1f-117">**[無料試用版を取得]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-117">Select **Get free trial**.</span></span>
    6.  <span data-ttu-id="b8c1f-118">試用版を確認するには、残りのウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-118">To confirm the trial, follow the remaining wizard steps.</span></span>

<span data-ttu-id="b8c1f-119">試用版をアクティブにするには、Microsoft 365管理者または課金管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-119">You must be a Microsoft 365 global administrator or billing administrator to activate a trial.</span></span>

### <a name="who-should-be-involved-in-a-trial"></a><span data-ttu-id="b8c1f-120">Whoに関与する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="b8c1f-120">Who should be involved in a trial</span></span>

|<span data-ttu-id="b8c1f-121">役割</span><span class="sxs-lookup"><span data-stu-id="b8c1f-121">Role</span></span>  |<span data-ttu-id="b8c1f-122">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="b8c1f-122">Activity</span></span>  |
|---------|---------|
|<span data-ttu-id="b8c1f-123">Microsoft 365管理者または請求管理者</span><span class="sxs-lookup"><span data-stu-id="b8c1f-123">Microsoft 365 global admin or billing admin</span></span>    |     <span data-ttu-id="b8c1f-124">試用版をアクティブ化し、ライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="b8c1f-124">Activate the trial and assign licenses</span></span>    |
|<span data-ttu-id="b8c1f-125">Microsoft 365管理者または管理者SharePointする</span><span class="sxs-lookup"><span data-stu-id="b8c1f-125">Microsoft 365 global admin or SharePoint admin</span></span>     |   <span data-ttu-id="b8c1f-126">コンテンツ センター SharePoint Syntex作成する方法を構成する</span><span class="sxs-lookup"><span data-stu-id="b8c1f-126">Configure SharePoint Syntex and create content centers</span></span>      |
|<span data-ttu-id="b8c1f-127">ビジネス ユーザー</span><span class="sxs-lookup"><span data-stu-id="b8c1f-127">Business users</span></span>     |    <span data-ttu-id="b8c1f-128">モデルの構築とテスト</span><span class="sxs-lookup"><span data-stu-id="b8c1f-128">Model building and testing</span></span>     |

### <a name="before-you-activate-a-trial"></a><span data-ttu-id="b8c1f-129">試用版をアクティブにする前に</span><span class="sxs-lookup"><span data-stu-id="b8c1f-129">Before you activate a trial</span></span>

<span data-ttu-id="b8c1f-130">試用版を正常に計画SharePoint Syntex、次の要因を検討してください。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-130">To successfully plan a SharePoint Syntex trial, consider the following factors:</span></span>

- <span data-ttu-id="b8c1f-131">最も意味のあるテストは、"現実世界" のシナリオとデータで完了します。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-131">The most meaningful testing is completed on “real world” scenarios and data.</span></span>
- <span data-ttu-id="b8c1f-132">ライセンス認証は、テナントごとに 1 SharePoint Syntex 1 回のみ有効にできます。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-132">You can only activate a SharePoint Syntex trial once per tenant.</span></span>

<span data-ttu-id="b8c1f-133">テストテナントまたはデモ テナントを "ドライ ラン" として使用して、ライセンス認証手順と管理コントロールを実行できます。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-133">A test or demo tenant can be used as a “dry run” to walk through the activation steps and administrative controls.</span></span> <span data-ttu-id="b8c1f-134">ただし、おそらく、実稼働テナントのモデル構築を評価する方が最適です。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-134">But it’s probably best to evaluate model building on a production tenant.</span></span>

<span data-ttu-id="b8c1f-135">実稼働テナントの試用版の価値を最大限に高めるには、計画とビジネスエンゲージメントが不可欠です。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-135">To maximize the value of a trial on a production tenant, planning and business engagement are essential.</span></span> <span data-ttu-id="b8c1f-136">1 つ以上のビジネス 領域を使用して、ユーザーが対処できる可能性のある 3 ~ 6 の使用例を特定SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-136">You should engage one or more business areas to identify three-to-six use cases that could potentially be addressed by SharePoint Syntex.</span></span> <span data-ttu-id="b8c1f-137">これらの使用例は、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-137">These use cases should:</span></span>

- <span data-ttu-id="b8c1f-138">フォーム処理モデルまたはドキュメント理解モデルで解決できるシナリオを含める。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-138">Include scenarios that could be solved by either the forms processing or document understanding model.</span></span>
- <span data-ttu-id="b8c1f-139">抽出されたメタデータの目的を明確に理解する。たとえば、書式設定やオートメーションを表示するには、次のPower Automate。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-139">Have a clear understanding of the purpose for any extracted metadata; for example, view formatting or automation by using Power Automate.</span></span> <span data-ttu-id="b8c1f-140">ドキュメントSharePoint Syntexメタデータの抽出に重点を置いて説明しますが、数値化する値は、このメタデータによって可能になります。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-140">While SharePoint Syntex is focused on classifying documents and extracting metadata, the value to quantify is what this metadata enables.</span></span>
- <span data-ttu-id="b8c1f-141">定義された一連のデータに基づく。たとえば、特定のサイトSharePointライブラリなどです。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-141">Be based on a defined set of data; for example, specific SharePoint sites or libraries.</span></span> <span data-ttu-id="b8c1f-142">一般的な誤解SharePoint Syntex、汎用モデルをすべての組織のコンテンツに適用できるという点です。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-142">A common misconception of SharePoint Syntex is that general purpose models can be applied across all organization content.</span></span> <span data-ttu-id="b8c1f-143">より正確なビューは、対象となる場所で特定のビジネス上の問題を解決するためにモデルが構築されているという考え方です。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-143">A more accurate view is that models are built to help solve specific business problems in targeted locations.</span></span>

<span data-ttu-id="b8c1f-144">これらのすべての使用例は、ユーザーに適していないSharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-144">All of these use cases might not be a good fit for SharePoint Syntex.</span></span> <span data-ttu-id="b8c1f-145">品質評価の目標は、すべてのシナリオに適合するSharePoint Syntex証明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-145">The goal of a quality trial isn't to prove that SharePoint Syntex will fit all the scenarios.</span></span> <span data-ttu-id="b8c1f-146">代わりに、試用版は製品の価値をよりよく理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-146">Instead, the trial should help you better understand the value of product.</span></span>

<span data-ttu-id="b8c1f-147">計画された各使用例について、関連するコンテンツまたはプロセスの専門家であるユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-147">For each of the planned use cases, identify users who are subject matter experts in the related content or process.</span></span> <span data-ttu-id="b8c1f-148">このモデルのSharePoint Syntexは、IT 専門家や開発者リソースではなく、コンテンツのドメイン専門家に焦点を当て、</span><span class="sxs-lookup"><span data-stu-id="b8c1f-148">The creation of SharePoint Syntex models is focused on domain experts in the content, rather than on IT professionals or developer resources.</span></span>

## <a name="activate-a-trial"></a><span data-ttu-id="b8c1f-149">試用版をアクティブ化する</span><span class="sxs-lookup"><span data-stu-id="b8c1f-149">Activate a trial</span></span>

<span data-ttu-id="b8c1f-150">試用版を開始する場合は、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-150">When you initiate a trial, you need to:</span></span>

- <span data-ttu-id="b8c1f-151">関連するユーザーにライセンスを割り当てる。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-151">Assign licenses to the relevant users.</span></span>
- <span data-ttu-id="b8c1f-152">追加[のセットアップを実行SharePoint Syntex。](set-up-content-understanding.md)</span><span class="sxs-lookup"><span data-stu-id="b8c1f-152">Perform [additional setup of SharePoint Syntex](set-up-content-understanding.md).</span></span>
    - <span data-ttu-id="b8c1f-153">追加のコンテンツ センター [を作成する場合があります](create-a-content-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-153">You might want to [create additional content centers](create-a-content-center.md).</span></span>

<span data-ttu-id="b8c1f-154">試用版をアクティブ化した後、モデルを作成し、ファイルを処理できます。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-154">After the trial is activated, you can create models and process files.</span></span> <span data-ttu-id="b8c1f-155">モデル作成 [のガイダンスを参照してください](create-a-content-center.md)。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-155">See [guidance for model creation](create-a-content-center.md).</span></span>

## <a name="during-a-trial"></a><span data-ttu-id="b8c1f-156">試用版中</span><span class="sxs-lookup"><span data-stu-id="b8c1f-156">During a trial</span></span>

<span data-ttu-id="b8c1f-157">試用期間は限られているので、SharePoint Syntex モデルがドキュメントを分類し、定義された使用例のメタデータを抽出できるかどうかに最初に焦点を当てるのが最善の方法です。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-157">Trial periods are limited, so it’s best to focus initially on whether SharePoint Syntex models can classify documents and extract metadata for the defined use cases.</span></span> <span data-ttu-id="b8c1f-158">試用期間が終了した後、メタデータの悪用方法を評価できます。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-158">After the trial period is over, you can evaluate how the metadata can be exploited.</span></span>

## <a name="after-a-trial"></a><span data-ttu-id="b8c1f-159">試用版の後</span><span class="sxs-lookup"><span data-stu-id="b8c1f-159">After a trial</span></span>

<span data-ttu-id="b8c1f-160">試用版の結果に基づいて、製品の生産使用に進むかどうかを決定SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-160">Based on the outcome of the trial, you can decide whether to proceed to production use of SharePoint Syntex.</span></span>

### <a name="proceed-to-production-use"></a><span data-ttu-id="b8c1f-161">実稼働環境の使用に進む</span><span class="sxs-lookup"><span data-stu-id="b8c1f-161">Proceed to production use</span></span>

<span data-ttu-id="b8c1f-162">サービスの継続性を確保するには、必要な数のライセンスを購入し、それらのライセンスをユーザーに割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-162">To ensure continuity of service, you need to purchase the required number of licenses and assign those licenses to users.</span></span> <span data-ttu-id="b8c1f-163">試用期間の最後に完全なライセンスを持ってない試用版ユーザーは、ライセンスを完全にSharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-163">Trial users who don’t have a full license at the end of the trial period won’t be able to fully utilize SharePoint Syntex.</span></span>

<span data-ttu-id="b8c1f-164">予想されるフォーム処理の使用を見積もり、予想される量の AI Builder クレジットを計画する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-164">You might have to estimate your projected use of forms processing and plan for the expected amount of AI Builder credits.</span></span> <span data-ttu-id="b8c1f-165">ヘルプについては、「 [自分に合った AI ビルダーの容量を見積もる」を参照してください](https://powerapps.microsoft.com/ai-builder-calculator/)。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-165">For help, see [Estimate the AI Builder capacity that’s right for you](https://powerapps.microsoft.com/ai-builder-calculator/).</span></span>

### <a name="dont-proceed-to-production-use"></a><span data-ttu-id="b8c1f-166">実稼働環境での使用に進む</span><span class="sxs-lookup"><span data-stu-id="b8c1f-166">Don't proceed to production use</span></span>

<span data-ttu-id="b8c1f-167">試用版に従ってライセンスを購入しない場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-167">If you don’t purchase licenses following the trial:</span></span>

- <span data-ttu-id="b8c1f-168">新しいモデルを作成できない。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-168">You won’t be able to create new models.</span></span>
- <span data-ttu-id="b8c1f-169">モデルを実行していたライブラリは、ファイルを自動的に分類したり、モデルを抽出したりしなくなりました。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-169">Libraries that were running models will no longer automatically classify files or extract models.</span></span>
- <span data-ttu-id="b8c1f-170">以前に分類されたファイルや抽出されたメタデータは影響を受け取らない。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-170">Any previously classified files or extracted metadata won’t be affected.</span></span> 
- <span data-ttu-id="b8c1f-171">コンテンツ センターとドキュメントを理解するモデルは自動的に削除されません。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-171">Content centers and any document-understanding models won’t be automatically deleted.</span></span> <span data-ttu-id="b8c1f-172">今後ライセンスを購入する場合は、これらは引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-172">These will remain available for use if you decide to purchase licenses in the future.</span></span>
- <span data-ttu-id="b8c1f-173">フォーム処理モデルは、既定の Power Platform 環境の Common Data Services (CDS) インスタンスに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-173">Forms-processing models will be stored in the Common Data Services (CDS) instance of the default Power Platform environment.</span></span> <span data-ttu-id="b8c1f-174">これらは、将来のライセンスや power プラットフォームSharePoint Syntex AI ビルダー機能で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b8c1f-174">These could be used with future licensing for SharePoint Syntex or with AI Builder capabilities in the Power Platform.</span></span>

## <a name="see-also"></a><span data-ttu-id="b8c1f-175">関連項目</span><span class="sxs-lookup"><span data-stu-id="b8c1f-175">See also</span></span>

[<span data-ttu-id="b8c1f-176">Microsoft SharePoint Syntex導入: 使い始める</span><span class="sxs-lookup"><span data-stu-id="b8c1f-176">Microsoft SharePoint Syntex adoption: Get started</span></span>](adoption-getstarted.md)
