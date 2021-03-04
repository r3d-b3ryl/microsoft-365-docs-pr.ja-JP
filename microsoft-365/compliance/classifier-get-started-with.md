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
description: Microsoft 365 分類子は、さまざまな種類のコンテンツを認識するためにトレーニングできるツールです。 この記事では、カスタム分類子を作成してトレーニングする方法と、それらを再トレーニングして精度を高める方法について説明します。
ms.openlocfilehash: a73acd7665cd23f13329bb5db4e890b0f3b0d861
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423296"
---
# <a name="get-started-with-trainable-classifiers"></a><span data-ttu-id="30b79-104">トレーニング可能な分類子の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="30b79-104">Get started with trainable classifiers</span></span>

<span data-ttu-id="30b79-105">Microsoft 365 トレーニング可能な分類子は、さまざまな種類のコンテンツを認識するようにトレーニングできるツールです。</span><span class="sxs-lookup"><span data-stu-id="30b79-105">A Microsoft 365 trainable classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="30b79-106">トレーニングが完了したら、このラベルを使用して、Office、通信コンプライアンス ポリシー、および保持ラベル ポリシーを適用するためのアイテムを識別できます。</span><span class="sxs-lookup"><span data-stu-id="30b79-106">Once trained, you can use it to identify item for application of Office sensitivity labels, Communications compliance policies, and retention label policies.</span></span>

<span data-ttu-id="30b79-107">カスタムトレーニング可能な分類子を作成するには、まず、人間が選んだサンプルを与え、カテゴリに正の一致を与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="30b79-107">Creating a custom trainable classifier first involves giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="30b79-108">次に、これらのサンプルを処理した後、正のサンプルと負のサンプルを組み合わせ、分類子が予測する能力をテストします。</span><span class="sxs-lookup"><span data-stu-id="30b79-108">Then, after it has processed those, you test the classifiers ability to predict by giving it a mix of positive and negative samples.</span></span> <span data-ttu-id="30b79-109">この記事では、カスタム分類子を作成してトレーニングする方法と、再トレーニングを通じてカスタムトレーニング可能な分類子と事前トレーニング済みの分類子のパフォーマンスを向上させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="30b79-109">This article shows you how to create and train a custom classifier and how to improve the performance of custom trainable classifiers and pre-trained classifiers over their lifetime through retraining.</span></span>

<span data-ttu-id="30b79-110">分類子の種類の詳細については、「トレーニング可能な分類子について」 [を参照してください](classifier-learn-about.md)。</span><span class="sxs-lookup"><span data-stu-id="30b79-110">To learn more about the different types of classifiers, see [Learn about trainable classifiers](classifier-learn-about.md).</span></span>

<span data-ttu-id="30b79-111">トレーニング可能な分類子の作成の概要については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="30b79-111">Watch this video for a quick summary of creating a trainable classifier.</span></span> <span data-ttu-id="30b79-112">詳細を取得するには、この記事の全文を読む必要があります。</span><span class="sxs-lookup"><span data-stu-id="30b79-112">You'll still need to read this full article to get the details.</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyGL7]


## <a name="prerequisites"></a><span data-ttu-id="30b79-113">前提条件</span><span class="sxs-lookup"><span data-stu-id="30b79-113">Prerequisites</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="30b79-114">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="30b79-114">Licensing requirements</span></span>

<span data-ttu-id="30b79-115">分類子は、Microsoft 365 E5 または E5 コンプライアンス機能です。</span><span class="sxs-lookup"><span data-stu-id="30b79-115">Classifiers are a Microsoft 365 E5, or E5 Compliance feature.</span></span> <span data-ttu-id="30b79-116">それらを使用するには、これらのサブスクリプションのいずれかが必要です。</span><span class="sxs-lookup"><span data-stu-id="30b79-116">You must have one of these subscriptions to make use of them.</span></span>

### <a name="permissions"></a><span data-ttu-id="30b79-117">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="30b79-117">Permissions</span></span>

<span data-ttu-id="30b79-118">UI で分類子にアクセスするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="30b79-118">To access classifiers in the UI:</span></span> 

- <span data-ttu-id="30b79-119">グローバル管理者は、カスタム分類子を作成するためにテナントをオプトインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="30b79-119">the Global admin needs to opt in for the tenant to create custom classifiers.</span></span>
- <span data-ttu-id="30b79-120">分類子をトレーニングするには、コンプライアンス管理者の役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="30b79-120">Compliance Administrator role is required to train a classifier.</span></span>

<span data-ttu-id="30b79-121">次のシナリオで分類子を使用するには、次のアクセス許可を持つアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="30b79-121">You'll need accounts with these permissions to use classifiers in these scenarios:</span></span>

- <span data-ttu-id="30b79-122">アイテム保持ラベル ポリシーのシナリオ: レコード管理と保持管理の役割</span><span class="sxs-lookup"><span data-stu-id="30b79-122">Retention label policy scenario: Record Management and Retention Management roles</span></span> 
- <span data-ttu-id="30b79-123">感度ラベル ポリシーのシナリオ: セキュリティ管理者、コンプライアンス管理者、コンプライアンス データ管理者</span><span class="sxs-lookup"><span data-stu-id="30b79-123">Sensitivity label policy scenario: Security Administrator, Compliance Administrator, Compliance Data Administrator</span></span>
- <span data-ttu-id="30b79-124">コミュニケーション コンプライアンス ポリシーのシナリオ: Insider Risk Management Admin、Supervisory Review Administrator</span><span class="sxs-lookup"><span data-stu-id="30b79-124">Communication compliance policy scenario: Insider Risk Management Admin, Supervisory Review Administrator</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="30b79-125">既定では、カスタム分類子を作成するユーザーだけが、その分類子によって行われた予測をトレーニングおよび確認できます。</span><span class="sxs-lookup"><span data-stu-id="30b79-125">By default, only the user who creates a custom classifier can train and review predictions made by that classifier.</span></span>

## <a name="prepare-for-a-custom-trainable-classifier"></a><span data-ttu-id="30b79-126">カスタムトレーニング可能な分類子の準備</span><span class="sxs-lookup"><span data-stu-id="30b79-126">Prepare for a custom trainable classifier</span></span> 

<span data-ttu-id="30b79-127">カスタムトレーニング可能な分類子を作成する際に何が関係しているのかを理解した上で、飛び込む前に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="30b79-127">It's helpful to understand what's involved in creating a custom trainable classifier before you dive in.</span></span> 

### <a name="timeline"></a><span data-ttu-id="30b79-128">タイムライン</span><span class="sxs-lookup"><span data-stu-id="30b79-128">Timeline</span></span>

<span data-ttu-id="30b79-129">このタイムラインは、トレーニング可能な分類子の展開例を反映しています。</span><span class="sxs-lookup"><span data-stu-id="30b79-129">This timeline reflects a sample deployment of trainable classifiers.</span></span>

![トレーニング可能な分類子-タイムライン](../media/trainable-classifier-deployment-timeline_border.png)

> [!TIP]
> <span data-ttu-id="30b79-131">トレーニング可能な分類子には、オプトインが初めて必要です。</span><span class="sxs-lookup"><span data-stu-id="30b79-131">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="30b79-132">Microsoft 365 が組織のコンテンツのベースライン評価を完了するには、12 日かかります。</span><span class="sxs-lookup"><span data-stu-id="30b79-132">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span> <span data-ttu-id="30b79-133">オプトイン プロセスを開始するには、グローバル管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="30b79-133">Contact your global administrator to kick off the opt-in process.</span></span>

### <a name="overall-workflow"></a><span data-ttu-id="30b79-134">全体的なワークフロー</span><span class="sxs-lookup"><span data-stu-id="30b79-134">Overall workflow</span></span>

<span data-ttu-id="30b79-135">カスタムトレーニング可能な分類子を作成する全体的なワークフローの詳細については、「顧客のトレーニング可能な分類子を作成するためのプロセス フロー」 [を参照してください](classifier-learn-about.md#process-flow-for-creating-custom-classifiers)。</span><span class="sxs-lookup"><span data-stu-id="30b79-135">To understand more about the overall workflow of creating custom trainable classifiers, see [Process flow for creating customer trainable classifiers](classifier-learn-about.md#process-flow-for-creating-custom-classifiers).</span></span>

### <a name="seed-content"></a><span data-ttu-id="30b79-136">シード コンテンツ</span><span class="sxs-lookup"><span data-stu-id="30b79-136">Seed content</span></span>

<span data-ttu-id="30b79-137">トレーニング可能な分類子が、特定のカテゴリのコンテンツとしてアイテムを独立して正確に識別するには、まず、カテゴリ内のコンテンツの種類の多くのサンプルを示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="30b79-137">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="30b79-138">トレーニング可能な分類子へのサンプルのこの供給は、シード処理と *呼ばれる。*</span><span class="sxs-lookup"><span data-stu-id="30b79-138">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="30b79-139">シード コンテンツは人間によって選択され、コンテンツのカテゴリを表すと判断されます。</span><span class="sxs-lookup"><span data-stu-id="30b79-139">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="30b79-140">50 以上の正のサンプルと最大 500 のサンプルが必要です。</span><span class="sxs-lookup"><span data-stu-id="30b79-140">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="30b79-141">トレーニング可能な分類子は、最新に作成された 500 のサンプル (ファイル作成日時スタンプ) まで処理されます。</span><span class="sxs-lookup"><span data-stu-id="30b79-141">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="30b79-142">提供するサンプルが多い場合、分類子が行う予測の精度が高い。</span><span class="sxs-lookup"><span data-stu-id="30b79-142">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

### <a name="testing-content"></a><span data-ttu-id="30b79-143">コンテンツのテスト</span><span class="sxs-lookup"><span data-stu-id="30b79-143">Testing content</span></span>

<span data-ttu-id="30b79-144">トレーニング可能な分類子が予測モデルを構築するのに十分な正のサンプルを処理したら、分類子がカテゴリと一致しないアイテムを正しく区別できるのか、予測をテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="30b79-144">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that don't.</span></span> <span data-ttu-id="30b79-145">これを行うには、カテゴリに分類する必要があるサンプルと、選択しないサンプルで構成される、人間が選んだ別のより大きなコンテンツのセットを選択します。</span><span class="sxs-lookup"><span data-stu-id="30b79-145">You do this by selecting another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="30b79-146">最初に指定した初期シード データとは異なるデータでテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="30b79-146">You should test with different data than the initial seed data you first provided.</span></span> <span data-ttu-id="30b79-147">それを処理したら、手動で結果を確認し、各予測が正しいか、正しくないか、または確信が持てないかを確認します。</span><span class="sxs-lookup"><span data-stu-id="30b79-147">Once it processes those, you manually go through the results and verify whether each prediction is correct, incorrect, or you aren't sure.</span></span> <span data-ttu-id="30b79-148">トレーニング可能な分類子は、このフィードバックを使用して予測モデルを改善します。</span><span class="sxs-lookup"><span data-stu-id="30b79-148">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="30b79-149">最適な結果を得る場合は、テスト サンプル セット内に少なくとも 200 のアイテムを含め、正と負の一致の分布を示します。</span><span class="sxs-lookup"><span data-stu-id="30b79-149">For best results, have at least 200 items in your test sample set with an even distribution of positive and negative matches.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="30b79-150">トレーニング可能な分類子を作成する方法</span><span class="sxs-lookup"><span data-stu-id="30b79-150">How to create a trainable classifier</span></span>

1. <span data-ttu-id="30b79-151">50 ~ 500 のシード コンテンツ アイテムを収集します。</span><span class="sxs-lookup"><span data-stu-id="30b79-151">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="30b79-152">これらは、トレーニング可能な分類子が分類カテゴリにあると正に識別するコンテンツの種類を強く表すサンプルに限る必要があります。</span><span class="sxs-lookup"><span data-stu-id="30b79-152">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="30b79-153">サポートされている [ファイルの種類については、「SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) の既定のクロールされたファイル名の拡張子と解析されたファイルの種類」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30b79-153">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="30b79-154">シードとテストのサンプル アイテムは暗号化し、英語である必要があります。</span><span class="sxs-lookup"><span data-stu-id="30b79-154">The seed and test sample items must not be encrypted and they must be in English.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="30b79-155">シード セット内のアイテムがカテゴリの強力 **な** 例である必要があります。</span><span class="sxs-lookup"><span data-stu-id="30b79-155">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="30b79-156">トレーニング可能な分類子は、最初に、シード処理に基づいてモデルを構築します。</span><span class="sxs-lookup"><span data-stu-id="30b79-156">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="30b79-157">分類子は、すべてのシード サンプルが強い陽性であり、サンプルがカテゴリに対して弱い一致か負の一致かを知る方法はありません。</span><span class="sxs-lookup"><span data-stu-id="30b79-157">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="30b79-158">シード コンテンツのみを保持する専用の SharePoint Online フォルダー *にシード コンテンツを配置します*。</span><span class="sxs-lookup"><span data-stu-id="30b79-158">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="30b79-159">サイト、ライブラリ、およびフォルダーの URL をメモします。</span><span class="sxs-lookup"><span data-stu-id="30b79-159">Make note of the site, library, and folder URL.</span></span>

   > [!TIP]
   > <span data-ttu-id="30b79-160">シード データ用に新しいサイトとフォルダーを作成する場合は、そのシード データを使用するトレーニング可能な分類子を作成する前に、その場所のインデックス作成に少なくとも 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="30b79-160">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="30b79-161">コンプライアンス管理者またはセキュリティ管理者の役割アクセスを使用して Microsoft 365 コンプライアンス センターにサインインし **、Microsoft 365** コンプライアンス センターまたは **Microsoft 365** セキュリティ センターのデータ分類を  >  **開きます**。</span><span class="sxs-lookup"><span data-stu-id="30b79-161">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**.</span></span>

4. <span data-ttu-id="30b79-162">[トレーニング **可能な分類子] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="30b79-162">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="30b79-163">[トレーニング **可能な分類子の作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="30b79-163">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="30b79-164">このトレーニング可能な分類子で識別するアイテムのカテゴリのフィールドと、適切な値 `Name` `Description` を入力します。</span><span class="sxs-lookup"><span data-stu-id="30b79-164">Fill in appropriate values for the `Name` and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="30b79-165">手順 2 から、シード コンテンツ サイトの SharePoint Online サイト、ライブラリ、およびフォルダー URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="30b79-165">Pick the SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="30b79-166">を選択します `Add` 。</span><span class="sxs-lookup"><span data-stu-id="30b79-166">Choose `Add`.</span></span>

8. <span data-ttu-id="30b79-167">設定を確認し、[] を選択します `Create trainable classifier` 。</span><span class="sxs-lookup"><span data-stu-id="30b79-167">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="30b79-168">トレーニング可能な分類子は、24 時間以内にシード データを処理し、予測モデルを構築します。</span><span class="sxs-lookup"><span data-stu-id="30b79-168">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="30b79-169">分類子の状態は、 `In progress` シード データの処理中です。</span><span class="sxs-lookup"><span data-stu-id="30b79-169">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="30b79-170">分類子がシード データの処理を終了すると、状態は に変わります `Need test items` 。</span><span class="sxs-lookup"><span data-stu-id="30b79-170">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="30b79-171">分類子を選択して詳細ページを表示できます。</span><span class="sxs-lookup"><span data-stu-id="30b79-171">You can now view the details page by choosing the classifier.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="30b79-172">![テストの準備ができているトレーニング可能な分類子](../media/classifier-trainable-ready-to-test-detail.png)</span><span class="sxs-lookup"><span data-stu-id="30b79-172">![trainable classifier ready for testing](../media/classifier-trainable-ready-to-test-detail.png)</span></span>

11. <span data-ttu-id="30b79-173">最適な結果を得る場合は、少なくとも 200 のテスト コンテンツ アイテム (最大 10,000) を収集します。</span><span class="sxs-lookup"><span data-stu-id="30b79-173">Collect at least 200 test content items (10,000 max) for best results.</span></span> <span data-ttu-id="30b79-174">これらは、強い肯定的なアイテム、強い否定的なアイテム、およびそれらの性質で少し明白ではないアイテムの組み合わせである必要があります。</span><span class="sxs-lookup"><span data-stu-id="30b79-174">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="30b79-175">サポートされている [ファイルの種類については、「SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) の既定のクロールされたファイル名の拡張子と解析されたファイルの種類」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30b79-175">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="30b79-176">サンプル アイテムは暗号化し、英語である必要があります。</span><span class="sxs-lookup"><span data-stu-id="30b79-176">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="30b79-177">テスト コンテンツのみを保持する専用の SharePoint Online フォルダー *にテスト コンテンツを配置します*。</span><span class="sxs-lookup"><span data-stu-id="30b79-177">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="30b79-178">SharePoint Online サイト、ライブラリ、およびフォルダーの URL をメモします。</span><span class="sxs-lookup"><span data-stu-id="30b79-178">Make note of the SharePoint Online site, library, and folder URL.</span></span>

    > [!TIP]
    > <span data-ttu-id="30b79-179">テスト データ用に新しいサイトとフォルダーを作成する場合は、そのシード データを使用するトレーニング可能な分類子を作成する前に、その場所のインデックス作成に少なくとも 1 時間を許可します。</span><span class="sxs-lookup"><span data-stu-id="30b79-179">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="30b79-180">を選択します `Add items to test` 。</span><span class="sxs-lookup"><span data-stu-id="30b79-180">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="30b79-181">手順 12 から、テスト コンテンツ サイトの SharePoint Online サイト、ライブラリ、およびフォルダー URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="30b79-181">Pick the SharePoint Online site, library, and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="30b79-182">を選択します `Add` 。</span><span class="sxs-lookup"><span data-stu-id="30b79-182">Choose `Add`.</span></span>

15. <span data-ttu-id="30b79-183">を選択してウィザードを終了します `Done` 。</span><span class="sxs-lookup"><span data-stu-id="30b79-183">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="30b79-184">トレーニング可能な分類子は、テスト ファイルの処理に最大で 1 時間かかっています。</span><span class="sxs-lookup"><span data-stu-id="30b79-184">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="30b79-185">トレーニング可能な分類子がテスト ファイルの処理を完了すると、詳細ページの状態がに変わります `Ready to review` 。</span><span class="sxs-lookup"><span data-stu-id="30b79-185">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="30b79-186">テスト サンプルのサイズを大きくする必要がある場合は、トレーニング可能な分類子が追加のアイテムを処理するを `Add items to test` 選択して許可します。</span><span class="sxs-lookup"><span data-stu-id="30b79-186">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="30b79-187">![スクリーンショットを確認する準備ができました](../media/classifier-trainable-ready-to-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="30b79-187">![ready to review screenshot](../media/classifier-trainable-ready-to-review-detail.png)</span></span>

17. <span data-ttu-id="30b79-188">タブを `Tested items to review` 選択してアイテムを確認します。</span><span class="sxs-lookup"><span data-stu-id="30b79-188">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="30b79-189">Microsoft 365 では、一度に 30 アイテムが表示されます。</span><span class="sxs-lookup"><span data-stu-id="30b79-189">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="30b79-190">それらを確認し、ボックス `We predict this item is "Relevant". Do you agree?` でどちらかまたは `Yes` を `No` 選択します `Not sure, skip to next item` 。</span><span class="sxs-lookup"><span data-stu-id="30b79-190">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="30b79-191">モデルの精度は、30 アイテムごとに自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="30b79-191">Model accuracy is automatically updated after every 30 items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="30b79-192">![[アイテムの確認] ボックス](../media/classifier-trainable-review-detail.png)</span><span class="sxs-lookup"><span data-stu-id="30b79-192">![review items box](../media/classifier-trainable-review-detail.png)</span></span>

19. <span data-ttu-id="30b79-193">少 *なくとも* 200 アイテムを確認します。</span><span class="sxs-lookup"><span data-stu-id="30b79-193">Review *at least* 200 items.</span></span> <span data-ttu-id="30b79-194">精度スコアが安定すると **、発行オプション** が使用可能になり、分類子の状態が表示されます `Ready to use` 。</span><span class="sxs-lookup"><span data-stu-id="30b79-194">Once the accuracy score has stabilized, the **publish** option will become available and the classifier status will say `Ready to use`.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="30b79-195">![精度スコアと公開準備完了](../media/classifier-trainable-review-ready-to-publish.png)</span><span class="sxs-lookup"><span data-stu-id="30b79-195">![accuracy score and ready to publish](../media/classifier-trainable-review-ready-to-publish.png)</span></span>

20. <span data-ttu-id="30b79-196">分類子を発行します。</span><span class="sxs-lookup"><span data-stu-id="30b79-196">Publish the classifier.</span></span>

21. <span data-ttu-id="30b79-197">公開された分類子は[、Office](apply-sensitivity-label-automatically.md)自動ラベル付けと感度ラベル付き条件として使用できます。条件に基づいて[](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels)保持ラベル ポリシーを自動適用し、[通信コンプライアンスで保持](communication-compliance.md)ラベル ポリシーを自動的に適用します。</span><span class="sxs-lookup"><span data-stu-id="30b79-197">Once published your classifier will be available as a condition in [Office auto-labeling with sensitivity labels](apply-sensitivity-label-automatically.md), [auto-apply retention label policy based on a condition](apply-retention-labels-automatically.md#configuring-conditions-for-auto-apply-retention-labels) and in [Communication compliance](communication-compliance.md).</span></span>
