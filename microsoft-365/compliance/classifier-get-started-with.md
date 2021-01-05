---
title: トレーニング可能な分類子の使用を開始する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 分類子は、さまざまな種類のコンテンツを見るサンプルを提供することで、さまざまな種類のコンテンツを認識するようにトレーニングできるツールです。 この記事では、カスタム分類子を作成してトレーニングする方法と、それらを再トレーニングして精度を高める方法について説明します。
ms.openlocfilehash: bca1de5edc3efd38f943b02091c3f47d832e6a19
ms.sourcegitcommit: 54d1a2f363b2d5b63aae258c3cec0573a08f2866
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49752661"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="417c7-104">トレーニング可能な分類子の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="417c7-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="417c7-105">Microsoft 365 トレーニング可能な分類子は、さまざまな種類のコンテンツを見るサンプルを提供することで、さまざまな種類のコンテンツを認識するようにトレーニングできるツールです。</span><span class="sxs-lookup"><span data-stu-id="417c7-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="417c7-106">トレーニングを受けたら、それを使用して、Office の区別ラベル、通信コンプライアンス ポリシー、および保持ラベル ポリシーの適用項目を識別できます。</span><span class="sxs-lookup"><span data-stu-id="417c7-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="417c7-107">最初に、トレーニング可能なカスタム分類子を作成するには、ユーザーが選択し、カテゴリに積極的に一致するサンプルを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="417c7-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="417c7-108">次に、分類子を処理した後、正と負のサンプルを組み合わせ、分類子の予測能力をテストします。</span><span class="sxs-lookup"><span data-stu-id="417c7-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="417c7-109">この記事では、カスタム分類子を作成してトレーニングする方法と、トレーニング可能なカスタム分類子と事前トレーニング済みの分類子の有効期間中のパフォーマンスを再トレーニングによって改善する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="417c7-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="417c7-110">さまざまな種類の分類子の詳細については、「トレーニング可能な分類子について [」を参照してください](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="417c7-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="417c7-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="417c7-111">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="417c7-112">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="417c7-112">Licensing requirements</span></span>

<span data-ttu-id="417c7-113">分類子は、Microsoft 365 E5 または E5 コンプライアンス機能です。</span><span class="sxs-lookup"><span data-stu-id="417c7-113">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="417c7-114">それらを使用するには、これらのサブスクリプションのいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="417c7-114">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="417c7-115">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="417c7-115">Permissions</span></span>

<span data-ttu-id="417c7-116">UI で分類子にアクセスするには:</span><span class="sxs-lookup"><span data-stu-id="417c7-116">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="417c7-117">グローバル管理者は、カスタム分類子を作成するためにテナントをオプトインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="417c7-117">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="417c7-118">分類子をトレーニングするには、コンプライアンス管理者の役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="417c7-118">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="417c7-119">次のシナリオで分類子を使用するには、次のアクセス許可を持つアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="417c7-119">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="417c7-120">保持ラベル ポリシー のシナリオ: レコード管理とアイテム保持管理の役割</span><span class="sxs-lookup"><span data-stu-id="417c7-120">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="417c7-121">[Sensitivity label policy scenario]: セキュリティ管理者、コンプライアンス管理者、コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="417c7-121">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="417c7-122">通信コンプライアンス ポリシー シナリオ: Insider Risk Management Admin、Supervisory Review Administrator</span><span class="sxs-lookup"><span data-stu-id="417c7-122">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="417c7-123">既定では、カスタム分類子を作成したユーザーだけが、その分類子によって行われた予測をトレーニングおよび確認できます。</span><span class="sxs-lookup"><span data-stu-id="417c7-123">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="417c7-124">カスタムのトレーニング可能な分類子を準備する</span><span class="sxs-lookup"><span data-stu-id="417c7-124">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="417c7-125">カスタムのトレーニング可能な分類子を作成する際に何が関係するのかを理解してから、理解を深めておくのが便利です。</span><span class="sxs-lookup"><span data-stu-id="417c7-125">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="417c7-126">タイムライン</span><span class="sxs-lookup"><span data-stu-id="417c7-126">Timeline</span></span>

<span data-ttu-id="417c7-127">このタイムラインは、トレーニング可能な分類子のサンプル展開を反映しています。</span><span class="sxs-lookup"><span data-stu-id="417c7-127">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![trainable-classifier-timeline](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="417c7-129">トレーニング可能な分類子では、初めてオプトインが必要です。</span><span class="sxs-lookup"><span data-stu-id="417c7-129">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="417c7-130">組織のコンテンツのベースライン評価を完了するには、Microsoft 365 に 12 日かかります。</span><span class="sxs-lookup"><span data-stu-id="417c7-130">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="417c7-131">オプトイン プロセスを開始するには、グローバル管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="417c7-131">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="417c7-132">ワークフロー全体</span><span class="sxs-lookup"><span data-stu-id="417c7-132">Overall workflow</span></span>

<span data-ttu-id="417c7-133">カスタムのトレーニング可能な分類子を作成する全体的なワークフローの詳細については、「顧客のトレーニング可能な分類子を作成するためのプロセス フロー」を [参照してください](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)。</span><span class="sxs-lookup"><span data-stu-id="417c7-133">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="417c7-134">シード コンテンツ</span><span class="sxs-lookup"><span data-stu-id="417c7-134">Seed content</span></span>

<span data-ttu-id="417c7-135">トレーニング可能な分類子が、アイテムを特定のカテゴリのコンテンツとして独立して正確に識別するには、まず、そのカテゴリに含むコンテンツの種類の多くのサンプルを表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="417c7-135">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="417c7-136">このトレーニング可能な分類子へのサンプルのフィードは、シード処理と *呼ばれる方法です*。</span><span class="sxs-lookup"><span data-stu-id="417c7-136">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="417c7-137">シード コンテンツは人間によって選択され、コンテンツのカテゴリを表すと判断されます。</span><span class="sxs-lookup"><span data-stu-id="417c7-137">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="417c7-138">50 以上の正のサンプルと最大 500 のサンプルが必要です。</span><span class="sxs-lookup"><span data-stu-id="417c7-138">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="417c7-139">トレーニング可能な分類子は、(ファイル作成日時スタンプにより) 作成された最新のサンプルを最大 500 件処理します。</span><span class="sxs-lookup"><span data-stu-id="417c7-139">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="417c7-140">サンプルを提供する数が多い場合、分類子が予測する精度が高くなっています。</span><span class="sxs-lookup"><span data-stu-id="417c7-140">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="417c7-141">コンテンツのテスト</span><span class="sxs-lookup"><span data-stu-id="417c7-141">Testing content</span></span>

<span data-ttu-id="417c7-142">トレーニング可能な分類子が予測モデルを構築するのに十分な正のサンプルを処理したら、予測をテストして、分類子がカテゴリに一致するアイテムと一致しないアイテムを正しく区別することができるか確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="417c7-142">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="417c7-143">これを行うには、カテゴリに分類する必要があるサンプルと、分類しないサンプルで構成される、人が選んだ別の大きなコンテンツのセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="417c7-143">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="417c7-144">最初に指定した初期シード データとは異なるデータでテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="417c7-144">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="417c7-145">これらの予測を処理したら、手動で結果を確認し、各予測が正しいか、正しくないか、または不確かかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="417c7-145">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="417c7-146">トレーニング可能な分類子は、このフィードバックを使用して予測モデルを改善します。</span><span class="sxs-lookup"><span data-stu-id="417c7-146">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="417c7-147">最適な結果を得る場合は、テスト サンプル セット内に、正と負の一致が 200 以上のアイテムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="417c7-147">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="417c7-148">トレーニング可能な分類子を作成する方法</span><span class="sxs-lookup"><span data-stu-id="417c7-148">How to create a trainable classifier</span></span>

1. <span data-ttu-id="417c7-149">50 ~ 500 のシード コンテンツ アイテムを収集します。</span><span class="sxs-lookup"><span data-stu-id="417c7-149">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="417c7-150">これらは、トレーニング可能な分類子が分類カテゴリ内にあると肯定的に識別するコンテンツの種類を強く表すサンプルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="417c7-150">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="417c7-151">サポートされている [ファイルの種類については、SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) の既定のクロールされたファイル名の拡張子と解析されたファイルの種類を参照してください。</span><span class="sxs-lookup"><span data-stu-id="417c7-151">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="417c7-152">シードとテストのサンプル アイテムは暗号化し、英語である必要があります。</span><span class="sxs-lookup"><span data-stu-id="417c7-152">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="417c7-153">シード セット内のアイテムがカテゴリの強力 **な** 例である必要があります。</span><span class="sxs-lookup"><span data-stu-id="417c7-153">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="417c7-154">トレーニング可能な分類子は、最初に、そのモデルのシードに基づいてモデルを構築します。</span><span class="sxs-lookup"><span data-stu-id="417c7-154">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="417c7-155">分類子は、すべてのシード サンプルが強い陽性と見なし、サンプルがカテゴリに対して弱い一致か負の一致かを知る方法はありません。</span><span class="sxs-lookup"><span data-stu-id="417c7-155">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="417c7-156">シード コンテンツのみを保持する専用の SharePoint Online フォルダー *にシード コンテンツを配置します*。</span><span class="sxs-lookup"><span data-stu-id="417c7-156">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="417c7-157">サイト、ライブラリ、およびフォルダーの URL をメモします。</span><span class="sxs-lookup"><span data-stu-id="417c7-157">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="417c7-158">シード データ用の新しいサイトとフォルダーを作成する場合は、そのシード データを使用するトレーニング可能な分類子を作成する前に、その場所のインデックスが作成されるのに少なくとも 1 時間は必要です。</span><span class="sxs-lookup"><span data-stu-id="417c7-158">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="417c7-159">コンプライアンス管理者またはセキュリティ管理者の役割にアクセスして Microsoft 365 コンプライアンス センターにサインインし **、Microsoft 365** コンプライアンス センターまたは **Microsoft 365** セキュリティ センターのデータ分類を開  >  **きます**。</span><span class="sxs-lookup"><span data-stu-id="417c7-159">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="417c7-160">[ **トレーニング可能な分類子] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="417c7-160">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="417c7-161">[ **トレーニング可能な分類子の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="417c7-161">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="417c7-162">このトレーニング可能な分類子で識別するアイテムのカテゴリとフィールドに適切な値 `Name` `Description` を入力します。</span><span class="sxs-lookup"><span data-stu-id="417c7-162">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="417c7-163">手順 2 のシード コンテンツ サイトの SharePoint Online サイト、ライブラリ、およびフォルダー URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="417c7-163">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="417c7-164">Choose `Add` .</span><span class="sxs-lookup"><span data-stu-id="417c7-164">Choose `Add`.</span></span>

8. <span data-ttu-id="417c7-165">設定を確認し、選択します `Create trainable classifier` 。</span><span class="sxs-lookup"><span data-stu-id="417c7-165">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="417c7-166">トレーニング可能な分類子は、24 時間以内にシード データを処理し、予測モデルを構築します。</span><span class="sxs-lookup"><span data-stu-id="417c7-166">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="417c7-167">分類子の状態は、 `In progress` シード データの処理中です。</span><span class="sxs-lookup"><span data-stu-id="417c7-167">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="417c7-168">分類子がシード データの処理を完了すると、状態は次の状態に変わります `Need test items` 。</span><span class="sxs-lookup"><span data-stu-id="417c7-168">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="417c7-169">分類子を選択して詳細ページを表示できます。</span><span class="sxs-lookup"><span data-stu-id="417c7-169">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="417c7-170">![テストの準備が整ったトレーニング可能な分類子](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="417c7-170">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="417c7-171">最適な結果を得る場合は、少なくとも 200 のテスト コンテンツ アイテム (最大 10,000 アイテム) を収集します。</span><span class="sxs-lookup"><span data-stu-id="417c7-171">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="417c7-172">これらは、強い陽性、強い陰性、および性質が少し明らかではない項目の組み合わせである必要があります。</span><span class="sxs-lookup"><span data-stu-id="417c7-172">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="417c7-173">サポートされている [ファイルの種類については、SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) の既定のクロールされたファイル名の拡張子と解析されたファイルの種類を参照してください。</span><span class="sxs-lookup"><span data-stu-id="417c7-173">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="417c7-174">サンプルアイテムは暗号化し、英語である必要があります。</span><span class="sxs-lookup"><span data-stu-id="417c7-174">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="417c7-175">テスト コンテンツのみを保持する専用の SharePoint Online フォルダー *にテスト コンテンツを配置します*。</span><span class="sxs-lookup"><span data-stu-id="417c7-175">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="417c7-176">SharePoint Online サイト、ライブラリ、およびフォルダーの URL をメモします。</span><span class="sxs-lookup"><span data-stu-id="417c7-176">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="417c7-177">テスト データ用に新しいサイトとフォルダーを作成する場合は、そのシード データを使用するトレーニング可能な分類子を作成する前に、その場所のインデックスが作成されるのに少なくとも 1 時間は必要です。</span><span class="sxs-lookup"><span data-stu-id="417c7-177">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="417c7-178">Choose `Add items to test` .</span><span class="sxs-lookup"><span data-stu-id="417c7-178">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="417c7-179">手順 12. で、テスト コンテンツ サイトの SharePoint Online サイト、ライブラリ、およびフォルダー URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="417c7-179">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="417c7-180">Choose `Add` .</span><span class="sxs-lookup"><span data-stu-id="417c7-180">Choose `Add`.</span></span>

15. <span data-ttu-id="417c7-181">選択してウィザードを終了します `Done` 。</span><span class="sxs-lookup"><span data-stu-id="417c7-181">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="417c7-182">トレーニング可能な分類子は、テスト ファイルの処理に最大 1 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="417c7-182">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="417c7-183">トレーニング可能な分類子がテスト ファイルの処理を完了すると、詳細ページの状態が次に変わります `Ready to review` 。</span><span class="sxs-lookup"><span data-stu-id="417c7-183">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="417c7-184">テスト サンプルのサイズを増やす必要がある場合は、トレーニング可能な分類子が追加のアイテムを処理 `Add items to test` する方法を選択して許可します。</span><span class="sxs-lookup"><span data-stu-id="417c7-184">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="417c7-185">![スクリーンショットを確認する準備](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="417c7-185">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="417c7-186">アイテム `Tested items to review` を確認するタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="417c7-186">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="417c7-187">Microsoft 365 では、一度に 30 アイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="417c7-187">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="417c7-188">それらを確認し、ボックス `We predict this item is "Relevant". Do you agree?` でどちらかまたは `Yes` 選択 `No` します `Not sure, skip to next item` 。</span><span class="sxs-lookup"><span data-stu-id="417c7-188">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="417c7-189">モデルの精度は、30 項目ごとに自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="417c7-189">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="417c7-190">![[アイテムの確認] ボックス](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="417c7-190">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="417c7-191">少 *なくとも* 200 アイテムを確認します。</span><span class="sxs-lookup"><span data-stu-id="417c7-191">Review *at least* 200 items.</span></span> <span data-ttu-id="417c7-192">精度スコアが安定すると、発行 **オプション** が使用可能になり、分類子の状態が表示されます `Ready to use` 。</span><span class="sxs-lookup"><span data-stu-id="417c7-192">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="417c7-193">![精度スコアと公開準備完了](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="417c7-193">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="417c7-194">分類子を発行します。</span><span class="sxs-lookup"><span data-stu-id="417c7-194">Publish the classifier.</span></span>

21. <span data-ttu-id="417c7-195">公開された分類子は[、Office](apply-sensitivity-label-automatically.md)の条件として、機度ラベルによる自動ラベル付け、条件と通信コンプライアンスに[](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)基づいて保持ラベル ポリシーを自動適用[できます。](communication-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="417c7-195">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
