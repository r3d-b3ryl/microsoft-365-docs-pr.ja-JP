---
title: Trainable 分類子を作成する (プレビュー)
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: '[使用準備完了] ボックス分類子のいずれかがニーズに合わない場合は、trainable 分類子を使用します。 Microsoft 365 の分類子は、さまざまな種類のコンテンツを認識するためにトレーニングできるツールです。そのためのサンプルを参照してください。 このトピックでは、カスタム分類子を作成する方法について説明します。'
ms.openlocfilehash: 1d62b70d821593ff7d8d3889c0da0e0b5cc9809f
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38690750"
---
# <a name="creating-a-trainable-classifier-preview"></a><span data-ttu-id="a963c-105">Trainable 分類子を作成する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="a963c-105">Creating a trainable classifier (preview)</span></span>

<span data-ttu-id="a963c-106">Trainable 分類子のいずれかがニーズに合わない場合は、分類子を使用します。</span><span class="sxs-lookup"><span data-stu-id="a963c-106">Use trainable classifiers when one of the out of the box classifiers won't meet your needs.</span></span> <span data-ttu-id="a963c-107">Microsoft 365 の分類子は、さまざまな種類のコンテンツを認識するためにトレーニングできるツールです。そのためのサンプルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a963c-107">A Microsoft 365 classifier is a tool you can train to recognize various types of content by giving it samples to look at.</span></span> <span data-ttu-id="a963c-108">分類子のトレーニングでは、まず、人間が選択され、カテゴリに対してプラスに一致するサンプルを提供します。</span><span class="sxs-lookup"><span data-stu-id="a963c-108">Training the classifier involves first giving it samples that are human picked and positively match the category.</span></span> <span data-ttu-id="a963c-109">その後、それらを処理した後、正と負の両方のサンプルを組み合わせて予測をテストします。</span><span class="sxs-lookup"><span data-stu-id="a963c-109">Then, after it has processed those, you test the predictions by giving it a mix of positive and negative samples.</span></span>

<span data-ttu-id="a963c-110">さまざまな分類子の詳細については、「 [trainable 分類子の概要 (プレビュー)](classifier-getting-started-with.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a963c-110">To learn more about the different types of classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md)</span></span>

<span data-ttu-id="a963c-111">このタイムラインには、サンプルの展開が反映されています。</span><span class="sxs-lookup"><span data-stu-id="a963c-111">This timeline reflects a sample deployment.</span></span>

![trainable-クラシファイア-タイムライン](media/trainable-classifier-deployment-timeline_border.png)

## <a name="seed-content"></a><span data-ttu-id="a963c-113">Seed コンテンツ</span><span class="sxs-lookup"><span data-stu-id="a963c-113">Seed content</span></span>

<span data-ttu-id="a963c-114">Trainable 分類子を個別に特定のカテゴリのコンテンツにする必要がある場合は、まず、カテゴリに含まれるコンテンツの種類の多くのサンプルを提示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a963c-114">When you want a trainable classifier to independently and accurately identify an item as being in particular category of content, you first have to present it with many samples of the type of content that are in the category.</span></span> <span data-ttu-id="a963c-115">Trainable 分類子へのこのサンプルのフィードは、*シード*と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a963c-115">This feeding of samples to the trainable classifier is known as *seeding*.</span></span> <span data-ttu-id="a963c-116">Seed コンテンツは人間が選択し、コンテンツのカテゴリを表すことを判断します。</span><span class="sxs-lookup"><span data-stu-id="a963c-116">Seed content is selected by a human and is judged to represent the category of content.</span></span>

> [!TIP]
> <span data-ttu-id="a963c-117">少なくとも50の正のサンプルと最大500が必要です。</span><span class="sxs-lookup"><span data-stu-id="a963c-117">You need to have at least 50 positive samples and as many as 500.</span></span> <span data-ttu-id="a963c-118">Trainable 分類子は、最新の作成済みサンプル (ファイル作成日時スタンプ) を500まで処理します。</span><span class="sxs-lookup"><span data-stu-id="a963c-118">The trainable classifier will process up to the 500 most recent created samples (by file created date/time stamp).</span></span> <span data-ttu-id="a963c-119">指定したサンプル数が多いほど、分類子が実行する予測がより正確になります。</span><span class="sxs-lookup"><span data-stu-id="a963c-119">The more samples you provide, the more accurate the predictions the classifier will make.</span></span>

## <a name="testing-content"></a><span data-ttu-id="a963c-120">コンテンツのテスト</span><span class="sxs-lookup"><span data-stu-id="a963c-120">Testing content</span></span>

<span data-ttu-id="a963c-121">Trainable 分類子が、予測モデルを構築するために十分な正のサンプルを処理した後は、その分類をテストして、分類項目と一致するアイテムがカテゴリと一致するアイテムを正しく区別できるかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a963c-121">Once the trainable classifier has processed enough positive samples to build a prediction model, you need to test the predictions it makes to see if the classifier can correctly distinguish between items that match the category and items that do not.</span></span> <span data-ttu-id="a963c-122">これを行うには、より大きなユーザーが選択したコンテンツセットを別のものにします。これは、カテゴリとサンプルに分類される必要のあるサンプルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="a963c-122">You do this by feeding it another, hopefully larger, set of human picked content that consists of samples that should fall into the category and samples that won't.</span></span> <span data-ttu-id="a963c-123">それらを処理した後、結果を手動で調べ、各予測が正しいかどうか、または正しくないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a963c-123">Once it processes those, you will manually go through the results and verify if each prediction is correct, incorrect or you are not sure.</span></span> <span data-ttu-id="a963c-124">Trainable 分類子は、このフィードバックを使用して予測モデルを改善します。</span><span class="sxs-lookup"><span data-stu-id="a963c-124">The trainable classifier uses this feedback to improve its prediction model.</span></span>

> [!TIP]
> <span data-ttu-id="a963c-125">最良の結果を得るには、正と負の一致が均等に分配された1万アイテムをテストサンプルセットに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="a963c-125">For best results, have 10,000 items in your test sample set with an even distribution of positive and negative matches.</span></span>

> [!TIP]
> <span data-ttu-id="a963c-126">Trainable 分類子では、最初にオプトインが必要です。</span><span class="sxs-lookup"><span data-stu-id="a963c-126">Opt-in is required the first time for trainable classifiers.</span></span> <span data-ttu-id="a963c-127">Microsoft 365 で組織のコンテンツのベースライン評価を完了するには、12日間かかります。</span><span class="sxs-lookup"><span data-stu-id="a963c-127">It takes twelve days for Microsoft 365 to complete a baseline evaluation of your organizations content.</span></span>

## <a name="how-to-create-a-trainable-classifier"></a><span data-ttu-id="a963c-128">Trainable 分類子を作成する方法</span><span class="sxs-lookup"><span data-stu-id="a963c-128">How to create a trainable classifier</span></span>

1. <span data-ttu-id="a963c-129">50-500 の seed コンテンツ項目の間で収集します。</span><span class="sxs-lookup"><span data-stu-id="a963c-129">Collect between 50-500 seed content items.</span></span> <span data-ttu-id="a963c-130">これらは、trainable 分類子が分類カテゴリに含まれるコンテンツの種類を厳密に表すサンプルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="a963c-130">These must be only samples that strongly represent the type of content you want the trainable classifier to positively identify as being in the classification category.</span></span> <span data-ttu-id="a963c-131">サポートされているファイルの種類については、「 [SharePoint Server での既定のクロール対象ファイル名拡張子および解析済みファイルの種類](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a963c-131">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a963c-132">シードおよびテストサンプルアイテムは、暗号化する必要があり、英語である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a963c-132">The seed and test sample items must not be encrypted and they must be in English.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a963c-133">Seed セット内のアイテムがカテゴリの**強力な**例であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a963c-133">Make sure the items in your seed set are **strong** examples of the category.</span></span> <span data-ttu-id="a963c-134">Trainable 分類子は、最初にそのモデルをシードしたものに基づいてモデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a963c-134">The trainable classifier initially builds its model based on what you seed it with.</span></span> <span data-ttu-id="a963c-135">この分類子は、すべてのシードサンプルが強力なものであることを前提としていますが、サンプルがカテゴリに対して弱いまたは否定的一致であるかどうかを知ることはできません。</span><span class="sxs-lookup"><span data-stu-id="a963c-135">The classifier assumes all seed samples are strong positives and has no way of knowing if a sample is a weak or negative match to the category.</span></span>

2. <span data-ttu-id="a963c-136">Seed*コンテンツを保持する*専用の SharePoint Online フォルダーにシードコンテンツを配置します。</span><span class="sxs-lookup"><span data-stu-id="a963c-136">Place the seed content in a SharePoint Online folder that is dedicated to holding *the seed content only*.</span></span> <span data-ttu-id="a963c-137">サイト、ライブラリ、およびフォルダーの url をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="a963c-137">Make note of the site, library, and folder url.</span></span>

> [!TIP]
> <span data-ttu-id="a963c-138">Seed データ用の新しいサイトとフォルダーを作成する場合は、そのシードデータを使用する trainable 分類子を作成する前に、少なくとも1時間、その場所にインデックスを作成するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="a963c-138">If you create a new site and folder for your seed data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

3. <span data-ttu-id="a963c-139">コンプライアンス管理者またはセキュリティ管理者の役割アクセスを使用して microsoft 365 コンプライアンスセンターにサインインし、 **microsoft 365 コンプライアンスセンター**または**microsoft 365 セキュリティセンター** > の**データ分類**を開く</span><span class="sxs-lookup"><span data-stu-id="a963c-139">Sign in to Microsoft 365 compliance center with compliance admin or security admin role access and open **Microsoft 365 compliance center** or **Microsoft 365 security center** > **Data classification**</span></span>

4. <span data-ttu-id="a963c-140">[ **Trainable 分類子**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="a963c-140">Choose the **Trainable classifiers** tab.</span></span>

5. <span data-ttu-id="a963c-141">[ **Create trainable クラシファイア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a963c-141">Choose **Create trainable classifier**.</span></span>

6. <span data-ttu-id="a963c-142">この trainable 分類子`Name`で識別するアイテム`Description`のカテゴリのフィールドに適切な値を入力します。</span><span class="sxs-lookup"><span data-stu-id="a963c-142">Fill in appropriate values for the `Name`, and `Description` fields of the category of items you want this trainable classifier to identify.</span></span>

7. <span data-ttu-id="a963c-143">手順2で、seed コンテンツサイトの正確な SharePoint Online サイト、ライブラリ、およびフォルダーの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a963c-143">Enter the exact SharePoint Online site, library, and folder URL for the seed content site from step 2.</span></span> <span data-ttu-id="a963c-144">[ `Add`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a963c-144">Choose `Add`.</span></span>

8. <span data-ttu-id="a963c-145">設定を確認し、 `Create trainable classifier`[] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a963c-145">Review the settings and choose `Create trainable classifier`.</span></span>

9. <span data-ttu-id="a963c-146">24時間以内、trainable クラシファイアはシードデータを処理し、予測モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a963c-146">Within 24 hours the trainable classifier will process the seed data and build a prediction model.</span></span> <span data-ttu-id="a963c-147">分類子の状態`In progress`は、シードデータを処理している間になります。</span><span class="sxs-lookup"><span data-stu-id="a963c-147">The classifier status is `In progress` while it processes the seed data.</span></span> <span data-ttu-id="a963c-148">分類子がシードデータの処理を完了すると、状態は`Need test items`に変わります。</span><span class="sxs-lookup"><span data-stu-id="a963c-148">When the classifier is finished processing the seed data, the status changes to `Need test items`.</span></span>

10. <span data-ttu-id="a963c-149">分類子を選択することによって、[詳細] ページを表示できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a963c-149">You can now view the details page by choosing the classifier.</span></span>


![テストの準備が整った trainable クラシファイア](media/classifier-trainable-ready-to-test-detail.png)

11. <span data-ttu-id="a963c-151">少なくとも200のテストコンテンツアイテムを収集します。</span><span class="sxs-lookup"><span data-stu-id="a963c-151">Collect at least 200 test content items.</span></span> <span data-ttu-id="a963c-152">Microsoft では、最適な結果を得るために1万をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a963c-152">Microsoft recommends 10,000 for best results.</span></span> <span data-ttu-id="a963c-153">これらのアイテムは、強力な陽性、強力なネガ、およびそれらの性質上の明確にわかりにくい項目を組み合わせたものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a963c-153">These should be a mix of items that are strong positives, strong negatives and some that are a little less obvious in their nature.</span></span> <span data-ttu-id="a963c-154">サポートされているファイルの種類については、「 [SharePoint Server での既定のクロール対象ファイル名拡張子および解析済みファイルの種類](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a963c-154">See, [Default crawled file name extensions and parsed file types in SharePoint Server](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types) for the supported file types.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a963c-155">サンプルアイテムは、暗号化する必要がなく、英語でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="a963c-155">The sample items must not be encrypted and they must be in English.</span></span>

12. <span data-ttu-id="a963c-156">テストコンテンツ*のみ*を保持する専用の SharePoint Online フォルダーにテストコンテンツを配置します。</span><span class="sxs-lookup"><span data-stu-id="a963c-156">Place the test content in a SharePoint Online folder that is dedicated to holding *the test content only*.</span></span> <span data-ttu-id="a963c-157">SharePoint Online サイト、ライブラリ、およびフォルダーの url をメモしておきます。</span><span class="sxs-lookup"><span data-stu-id="a963c-157">Make note of the SharePoint Online site, library and folder url.</span></span>

> [!TIP]
> <span data-ttu-id="a963c-158">テストデータ用に新しいサイトとフォルダーを作成する場合は、そのシードデータを使用する trainable 分類子を作成する前に、少なくとも1時間、その場所にインデックスを設定するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="a963c-158">If you create a new site and folder for your test data, allow at least an hour for that location to be indexed before creating the trainable classifier that will use that seed data.</span></span>

13. <span data-ttu-id="a963c-159">[ `Add items to test`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a963c-159">Choose `Add items to test`.</span></span>

14. <span data-ttu-id="a963c-160">手順12から、テストコンテンツサイトの正確な SharePoint Online サイト、ライブラリ、およびフォルダーの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="a963c-160">Enter the exact SharePoint Online site, library and folder URL for the test content site from step 12.</span></span> <span data-ttu-id="a963c-161">[ `Add`] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a963c-161">Choose `Add`.</span></span>

15. <span data-ttu-id="a963c-162">を選択`Done`してウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="a963c-162">Finish the wizard by choosing `Done`.</span></span> <span data-ttu-id="a963c-163">Trainable の分類子は、テストファイルの処理に最大1時間かかります。</span><span class="sxs-lookup"><span data-stu-id="a963c-163">Your trainable classifier will take up to an hour to process the test files.</span></span>

16. <span data-ttu-id="a963c-164">Trainable クラシファイアがテストファイルの処理を完了すると、詳細ページの状態はに`Ready to review`変わります。</span><span class="sxs-lookup"><span data-stu-id="a963c-164">When the trainable classifier is done processing your test files, the status on the details page will change to `Ready to review`.</span></span> <span data-ttu-id="a963c-165">テストサンプルサイズを増やす必要がある場合は、 `Add items to test` trainable クラシファイアが追加のアイテムを処理することを選択して許可します。</span><span class="sxs-lookup"><span data-stu-id="a963c-165">If you need to increase the test sample size, choose `Add items to test` and allow the trainable classifier to process the additional items.</span></span>

![スクリーンショットを確認する準備ができました](media/classifier-trainable-ready-to-review-detail.png)

17. <span data-ttu-id="a963c-167">[ `Tested items to review`タブ] を選択してアイテムを確認します。</span><span class="sxs-lookup"><span data-stu-id="a963c-167">Choose `Tested items to review` tab to review items.</span></span>

18. <span data-ttu-id="a963c-168">Microsoft 365 は、一度に30個のアイテムを提示します。</span><span class="sxs-lookup"><span data-stu-id="a963c-168">Microsoft 365 will present 30 items at a time.</span></span> <span data-ttu-id="a963c-169">それらを確認し、 `We predict this item is "Relevant". Do you agree?`ボックスで、 `Yes`また`No`は`Not sure, skip to next item`のどちらかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a963c-169">Review them and in the `We predict this item is "Relevant". Do you agree?` box choose either `Yes` or `No` or `Not sure, skip to next item`.</span></span> <span data-ttu-id="a963c-170">モデル精度は30アイテムごとに自動的に更新されます。</span><span class="sxs-lookup"><span data-stu-id="a963c-170">Model accuracy is automatically updated after every 30 items.</span></span>

![[アイテムの確認] ボックス](media/classifier-trainable-review-detail.png)

19. <span data-ttu-id="a963c-172">*少なく*とも200のアイテムを確認します。</span><span class="sxs-lookup"><span data-stu-id="a963c-172">Review *at least* 200 items.</span></span>

20. <span data-ttu-id="a963c-173">精度が少なくとも70% に達するまで確認を続け`Publish the classifier` 、状態`Ready to use`はになります。</span><span class="sxs-lookup"><span data-stu-id="a963c-173">Continue to review until the accuracy reaches at least 70% and the `Publish the classifier` status is `Ready to use`.</span></span>

![精度と発行の準備ができている](media/classifier-trainable-review-ready-to-publish.png)

21. <span data-ttu-id="a963c-175">分類子を発行します。</span><span class="sxs-lookup"><span data-stu-id="a963c-175">Publish the classifier.</span></span>

22. <span data-ttu-id="a963c-176">発行された分類子は、条件および[通信のコンプライアンス](communication-compliance.md)に基づいて、[自動適用の保持ラベルポリシー](labels.md#applying-a-retention-label-automatically-based-on-conditions)の条件として使用できます。</span><span class="sxs-lookup"><span data-stu-id="a963c-176">Once published your classifier will be available as a condition in the [auto-apply retention label policy based on a condition](labels.md#applying-a-retention-label-automatically-based-on-conditions) and in [Communication compliance](communication-compliance.md).</span></span>

> [!CAUTION]
> <span data-ttu-id="a963c-177">分類子が公開されると、追加のトレーニングを受けることはできません。そのため、できるだけ多くのアイテムをテストして確認し、その精度が可能な限り高くなることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a963c-177">Once a classifier is published, it can't go through any additional training, so be very sure that you have tested and reviewed as many items as possible to ensure that the accuracy is as high as possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="a963c-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="a963c-178">See also</span></span>

- [<span data-ttu-id="a963c-179">トレーニング可能な分類子の使用を開始する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="a963c-179">Getting started with trainable classifiers (preview)</span></span>](classifier-getting-started-with.md)
- [<span data-ttu-id="a963c-180">SharePoint Server での既定のクロール対象ファイル名拡張子および解析対象ファイルの種類</span><span class="sxs-lookup"><span data-stu-id="a963c-180">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](https://docs.microsoft.com/sharepoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)
