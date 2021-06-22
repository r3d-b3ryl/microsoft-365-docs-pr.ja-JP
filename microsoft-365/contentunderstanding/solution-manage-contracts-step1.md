---
title: 手順 1. 契約ファイルSharePoint Syntexデータの抽出に使用する方法
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: ソリューションを使用して、SharePoint Syntexファイルを識別し、データを抽出する方法についてMicrosoft 365します。
ms.openlocfilehash: c66e46aaaacd5000f1e0d18aa07df527ca8ab7dd
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054498"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a><span data-ttu-id="98b8e-104">手順 1。</span><span class="sxs-lookup"><span data-stu-id="98b8e-104">Step 1.</span></span> <span data-ttu-id="98b8e-105">契約ファイルSharePoint Syntexデータの抽出に使用する方法</span><span class="sxs-lookup"><span data-stu-id="98b8e-105">Use SharePoint Syntex to identify contract files and extract data</span></span>

<span data-ttu-id="98b8e-106">組織では、受信した多数のファイルからすべての契約ドキュメントを識別して分類する方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="98b8e-106">Your organization needs a way to identify and classify all contract documents from the many files you receive.</span></span> <span data-ttu-id="98b8e-107">また、特定された各コントラクト ファイル内のいくつかの重要な要素 (クライアント、契約者、手数料金額など)をすばやく *表示できます*。</span><span class="sxs-lookup"><span data-stu-id="98b8e-107">You also want to be able to quickly view several key elements in each of the contract files identified (for example, *Client*, *Contractor*, and *Fee amount*).</span></span> <span data-ttu-id="98b8e-108">この操作を行うには、SharePoint Syntex[を使用](index.md)してドキュメント理解モデルを作成し、それをドキュメント ライブラリに適用します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-108">You can do this by using [SharePoint Syntex](index.md) to create a document understanding model and applying it to a document library.</span></span>

## <a name="overview-of-the-process"></a><span data-ttu-id="98b8e-109">プロセスの概要</span><span class="sxs-lookup"><span data-stu-id="98b8e-109">Overview of the process</span></span>

<span data-ttu-id="98b8e-110">[ドキュメントの理解](document-understanding-overview.md) では、人工知能 (AI) モデルを使用して、ファイルの分類と情報の抽出を自動化します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-110">[Document understanding](document-understanding-overview.md) uses artificial intelligence (AI) models to automate classification of files and extraction of information.</span></span> <span data-ttu-id="98b8e-111">ドキュメント理解モデルは、必要な情報がテーブルやフォーム (コントラクトなど) に含まれている必要のない非構造化ドキュメントや半構造化ドキュメントから情報を抽出する場合にも最適です。</span><span class="sxs-lookup"><span data-stu-id="98b8e-111">Document understanding models are also optimal in extracting information from unstructured and semi-structured documents where the information you need isn't contained in tables or forms, such as contracts.</span></span>

1. <span data-ttu-id="98b8e-112">最初に、モデルを "トレーニング" して、識別しようとしているコンテンツ タイプ (契約) に固有の特性を検索するために使用できる少なくとも 5 つのサンプル ファイルを見つける必要があります。</span><span class="sxs-lookup"><span data-stu-id="98b8e-112">First, you need to find at least five example files that you can use to "train" the model to search for characteristics that are specific to the content type you're trying to identify (a contract).</span></span> 

2. <span data-ttu-id="98b8e-113">このSharePoint Syntexを使用して、新しいドキュメント理解モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-113">Using SharePoint Syntex, create a new document understanding model.</span></span> <span data-ttu-id="98b8e-114">サンプル ファイルを使用して、分類子 [を作成する必要があります](create-a-classifier.md)。</span><span class="sxs-lookup"><span data-stu-id="98b8e-114">Using your example files, you need to [create a classifier](create-a-classifier.md).</span></span> <span data-ttu-id="98b8e-115">サンプル ファイルを使用して分類子をトレーニングすると、会社の契約に表示される特性に固有の特性を検索できます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-115">By training the classifier with your example files, you teach it to search for characteristics that are specific to what you would see in your company's contracts.</span></span> <span data-ttu-id="98b8e-116">たとえば、サービス契約、契約条件、報酬など、契約内の特定の文字列を検索する "説明 ["](create-a-classifier.md#create-an-explanation)を作成 *します*。</span><span class="sxs-lookup"><span data-stu-id="98b8e-116">For example, [create an "explanation"](create-a-classifier.md#create-an-explanation) that searches for specific strings that are in your contracts, such as *Service Agreement*, *Terms of Agreement*, and *Compensation*.</span></span> <span data-ttu-id="98b8e-117">説明をトレーニングして、ドキュメントの特定のセクションでこれらの文字列を探したり、他の文字列の横に位置したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-117">You can even train your explanation to look for these strings in specific sections of the document, or located next to other strings.</span></span> <span data-ttu-id="98b8e-118">分類子に必要な情報をトレーニングしたと思う場合は、サンプル ファイルのサンプル セットでモデルをテストして、その効率を確認できます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-118">When you think you have trained your classifier with the information it needs, you can test your model on a sample set of example files to see how efficient it is.</span></span> <span data-ttu-id="98b8e-119">テスト後、必要に応じて説明を変更して、より効率的に行えます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-119">After testing, if needed you can choose to make changes to your explanations to make them more efficient.</span></span> 

3. <span data-ttu-id="98b8e-120">モデルでは、抽出プログラム [を作成して](create-an-extractor.md) 、各コントラクトから特定のデータを抽出できます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-120">In your model, you can [create an extractor](create-an-extractor.md) to pull out specific pieces of data from each contract.</span></span> <span data-ttu-id="98b8e-121">たとえば、契約ごとに、最も懸念される情報は、クライアントが誰か、契約者の名前、および総コストです。</span><span class="sxs-lookup"><span data-stu-id="98b8e-121">For example, for each contract, the information you're most concerned about is who the client is, the name of the contractor, and the total cost.</span></span>

4. <span data-ttu-id="98b8e-122">モデルを正常に作成したら、そのモデルを[ドキュメント ライブラリSharePoint適用します](apply-a-model.md)。</span><span class="sxs-lookup"><span data-stu-id="98b8e-122">After you successfully create your model, [apply it to a SharePoint document library](apply-a-model.md).</span></span> <span data-ttu-id="98b8e-123">ドキュメントをドキュメント ライブラリにアップロードすると、ドキュメント理解モデルが実行され、モデルで定義したコントラクト コンテンツ タイプに一致するファイルすべてが識別され、分類されます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-123">As you upload documents to the document library, your document understanding model will run and will identify and classify all files that match the contracts content type you defined in your model.</span></span> <span data-ttu-id="98b8e-124">コントラクトとして分類されたファイルはすべて、カスタム ライブラリ ビューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-124">All files that are classified as contracts will display in a custom library view.</span></span> <span data-ttu-id="98b8e-125">ファイルには、抽出プログラムで定義した各コントラクトの値も表示されます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-125">The files will also display the values from each contract that you defined in your extractor.</span></span>

   ![ドキュメント ライブラリ内のコントラクト](../media/content-understanding/doc-lib-solution.png)

5. <span data-ttu-id="98b8e-127">契約の保持要件またはセキュリティ要件がある場合は、モデルを使用して保持ラベルまたは感度ラベルを適用[](apply-a-retention-label-to-a-model.md)して、指定した[](apply-a-sensitivity-label-to-a-model.md)期間契約が削除されるのを防ぐか、契約にアクセスできるユーザーを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-127">If you have retention or security requirements for your contracts, you can also use your model to apply a [retention label](apply-a-retention-label-to-a-model.md) or a [sensitivity label](apply-a-sensitivity-label-to-a-model.md) that will prevent your contracts from being deleted for a specified period of time or to restrict who can access the contracts.</span></span>

## <a name="steps-to-create-and-train-your-model"></a><span data-ttu-id="98b8e-128">モデルを作成してトレーニングする手順</span><span class="sxs-lookup"><span data-stu-id="98b8e-128">Steps to create and train your model</span></span>

> [!NOTE]
> <span data-ttu-id="98b8e-129">これらの手順では、Contracts Management Solution Assets リポジトリのサンプル [ファイルを使用できます](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management)。</span><span class="sxs-lookup"><span data-stu-id="98b8e-129">For these steps, you can use the example files in the [Contracts Management Solution Assets repository](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management).</span></span> <span data-ttu-id="98b8e-130">このリポジトリの例には、ドキュメント理解モデル ファイルと、モデルのトレーニングに使用されるファイルの両方が含まれています。</span><span class="sxs-lookup"><span data-stu-id="98b8e-130">The examples in this repository contain both the document understanding model files and the files used to train the model.</span></span>

### <a name="create-a-contract-model"></a><span data-ttu-id="98b8e-131">コントラクト モデルの作成</span><span class="sxs-lookup"><span data-stu-id="98b8e-131">Create a Contract model</span></span>

<span data-ttu-id="98b8e-132">最初の手順は、コントラクト モデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-132">The first step is to create your Contract model.</span></span>

1. <span data-ttu-id="98b8e-133">コンテンツ センターで、**[新規]** を選択し、**[モデルを作成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-133">From the content center, select **New**, and then **Create a model**.</span></span>

2. <span data-ttu-id="98b8e-134">[新しい **ドキュメントの理解モデル] ウィンドウ** の [ **名前** ] フィールドに、モデルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-134">On the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="98b8e-135">このコントラクト管理ソリューションでは、モデルの Contract という名前を *付けできます*。</span><span class="sxs-lookup"><span data-stu-id="98b8e-135">For this contract management solution, you can name the model *Contract*.</span></span>

4. <span data-ttu-id="98b8e-136">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-136">Choose **Create**.</span></span> <span data-ttu-id="98b8e-137">これにより、モデルのホームページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-137">This creates a home page for the model.</span></span></br>

    ![契約のホーム ページのスクリーンショット。](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a><span data-ttu-id="98b8e-139">モデルをトレーニングしてファイルの種類を分類する</span><span class="sxs-lookup"><span data-stu-id="98b8e-139">Train your model to classify a type of file</span></span>

#### <a name="add-example-files-for-your-model"></a><span data-ttu-id="98b8e-140">モデルのサンプル ファイルの追加</span><span class="sxs-lookup"><span data-stu-id="98b8e-140">Add example files for your model</span></span>

<span data-ttu-id="98b8e-141">コントラクト ドキュメントである 5 つ以上のサンプル ファイルと、契約ドキュメントではない 1 つのサンプル ファイル (作業明細書など) を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="98b8e-141">You need to add at least five example files that are contract documents, and one example file that's not a contract document (for example, a statement of work).</span></span> 

1. <span data-ttu-id="98b8e-142">[モデルと **契約>] ページの [** キー アクションサンプル **ファイルの** 追加] で、[  >  ファイルの追加]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="98b8e-142">On the **Models > Contract** page, under **Key actions** > **Add example files**, select **Add files**.</span></span>

   ![[サンプル ファイルの追加] オプションが強調表示された [コントラクト] ページを示すスクリーンショット。](../media/content-understanding/key-actions-add-example-files.png)

2. <span data-ttu-id="98b8e-144">[モデルの **サンプル ファイルの選択]** ページで、Contract フォルダーを開き、使用するファイルを選択し、[追加] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="98b8e-144">On the **Select example files for your model** page, open the Contract folder, select files you want to use, and then select **Add**.</span></span> <span data-ttu-id="98b8e-145">そこにサンプル ファイルが含めなかった場合は、[**ファイルのアップロード** 選択して追加します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-145">If you don't have example files there, select **Upload** to add them.</span></span>

#### <a name="label-the-files-as-positive-or-negative-examples"></a><span data-ttu-id="98b8e-146">ファイルに正または負のラベルを付ける</span><span class="sxs-lookup"><span data-stu-id="98b8e-146">Label the files as positive or negative examples</span></span>

1. <span data-ttu-id="98b8e-147">[契約の **モデル>] ページの [キー** アクション ファイルの分類とトレーニングの実行] で、[トレーニング分類子  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="98b8e-147">On the **Models > Contract** page, under **Key actions** > **Classify files and run training**, select **Train classifier**.</span></span>

   ![[ファイルの分類とトレーニングの実行] オプションが強調表示された [契約] ページを示すスクリーンショット。](../media/content-understanding/key-actions-classify-files.png)

2. <span data-ttu-id="98b8e-149">[Model **> Contract > Contract classifier]** ページの最初のサンプル ファイルの上部にあるビューアーに、作成したコントラクト モデルの例を示すテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-149">On the **Models > Contract > Contract classifier** page, in the viewer on the top of the first example file, you'll see text asking if the file is an example of the Contract model you created.</span></span> <span data-ttu-id="98b8e-150">この例がポジティブの場合は、[ **はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-150">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="98b8e-151">ネガティブの例の場合は、[ **いいえ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-151">If it is a negative example, select **No**.</span></span>

3. <span data-ttu-id="98b8e-152">左側の **[ラベル付き例]** リストから、例として使用する他のファイルを選択し、ラベルを付ける。</span><span class="sxs-lookup"><span data-stu-id="98b8e-152">From the **Labeled examples** list on the left, select other files that you want to use as examples, and label them.</span></span> 

    ![分類子ホームページ](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier"></a><span data-ttu-id="98b8e-154">分類子をトレーニングするために少なくとも 1 つの説明を追加する</span><span class="sxs-lookup"><span data-stu-id="98b8e-154">Add at least one explanation to train the classifier</span></span> 

1. <span data-ttu-id="98b8e-155">[契約 **分類子>モデル>]** ページで、[Train] タブ **を選択** します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-155">On the **Models > Contract > Contract classifier** page, select the **Train** tab.</span></span>

2. <span data-ttu-id="98b8e-156">[トレーニング **済みファイル]** セクションには、以前にラベル付けしたサンプル ファイルの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-156">In the **Trained files** section, you'll see a list of the example files that you previously labeled.</span></span> <span data-ttu-id="98b8e-157">一覧から正のファイルのいずれかを選択して、ビューアーに表示します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-157">Select one of the positive files from the list to display it in the viewer.</span></span>

3. <span data-ttu-id="98b8e-158">[説明 **] セクションで、[** 新規] を選択 **し、[空白** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="98b8e-158">In the **Explanations** section, select **New** and then **Blank**.</span></span>

4. <span data-ttu-id="98b8e-159">[ **説明を作成する** ] ページで：</span><span class="sxs-lookup"><span data-stu-id="98b8e-159">On the **Create an explanation** page:</span></span>

    <span data-ttu-id="98b8e-160">a.</span><span class="sxs-lookup"><span data-stu-id="98b8e-160">a.</span></span> <span data-ttu-id="98b8e-161">[名前 **] フィールド** に、説明の名前 ("Agreement" など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-161">In the **Name** field, type the name of the explanation (such as "Agreement").</span></span>

    <span data-ttu-id="98b8e-162">b.</span><span class="sxs-lookup"><span data-stu-id="98b8e-162">b.</span></span> <span data-ttu-id="98b8e-163">[説明 **の種類]** フィールドで、[語句の一 **覧**] を選択します。テキスト文字列を追加します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-163">In the **Explanation type** field, select **Phrase list**, because you add a text string.</span></span>

    <span data-ttu-id="98b8e-164">c.</span><span class="sxs-lookup"><span data-stu-id="98b8e-164">c.</span></span> <span data-ttu-id="98b8e-165">[語句 **] リスト ボックス** に、文字列 ("AGREEMENT" など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-165">In the **Phrase list** box, type the string (such as "AGREEMENT").</span></span> <span data-ttu-id="98b8e-166">文字列で大文字 **と小文字を** 区別する必要がある場合は、[大文字と小文字を区別する] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-166">You can select **Case sensitive** if the string needs to be case-sensitive.</span></span>

    <span data-ttu-id="98b8e-167">d.</span><span class="sxs-lookup"><span data-stu-id="98b8e-167">d.</span></span> <span data-ttu-id="98b8e-168">[保存 **してトレーニング] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="98b8e-168">Select **Save and train**.</span></span>

    ![[説明の作成] パネルのスクリーンショット。](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a><span data-ttu-id="98b8e-170">モデルをテストする</span><span class="sxs-lookup"><span data-stu-id="98b8e-170">Test your model</span></span>

<span data-ttu-id="98b8e-171">コントラクト モデルは、前に見たことがないサンプル ファイルでテストできます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-171">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="98b8e-172">これはオプションですが、便利なベスト プラクティスになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="98b8e-172">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="98b8e-173">[契約 **分類子>モデル>] ページで** 、[テスト] タブ **を選択** します。これにより、ラベルが付いていないサンプル ファイルでモデルが実行されます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-173">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="98b8e-174">[テスト **ファイル] ボックスの** 一覧で、サンプル ファイルが表示され、モデルで正または負の値が予測された場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-174">In the **Test Files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="98b8e-175">この情報を使用して、ドキュメントを特定するときの分類子の有効性を判断します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-175">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![[テキスト ファイル] リストのラベル付けされていないファイルのスクリーンショット](../media/content-understanding/test-on-files.png) 

3. <span data-ttu-id="98b8e-177">完了したら、[トレーニングの終了 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="98b8e-177">When done, select **Exit Training**.</span></span>

### <a name="create-and-train-an-extractor"></a><span data-ttu-id="98b8e-178">抽出プログラムの作成とトレーニング</span><span class="sxs-lookup"><span data-stu-id="98b8e-178">Create and train an extractor</span></span>

1. <span data-ttu-id="98b8e-179">[契約の **モデル>] ページの** [キー アクション抽出プログラムの作成とトレーニング] で、[抽出  >  プログラムの作成 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="98b8e-179">On the **Models > Contract** page, under **Key actions** > **Create and train extractors**, select **Create extractor**.</span></span>

   ![[抽出プログラムの作成とトレーニング] オプションが強調表示された [契約] ページを示すスクリーンショット。](../media/content-understanding/key-actions-create-extractors.png)

2. <span data-ttu-id="98b8e-181">[新しい **エンティティ抽出プログラム] パネル** の [ **新しい名前** ] フィールドに、抽出プログラムの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-181">On the **New entity extractor** panel, in the **New name** field, type the name of your extractor.</span></span> <span data-ttu-id="98b8e-182">たとえば、各コントラクトから *クライアントの* 名前を抽出する場合は、[クライアント] という名前を付します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-182">For example, name it *Client* if you want to extract the name of the client from each contract.</span></span>

3. <span data-ttu-id="98b8e-183">完了したら、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="98b8e-183">When you're done, select **Create**.</span></span>

#### <a name="label-the-entity-you-want-to-extract"></a><span data-ttu-id="98b8e-184">抽出するエンティティにラベルを付け</span><span class="sxs-lookup"><span data-stu-id="98b8e-184">Label the entity you want to extract</span></span>

<span data-ttu-id="98b8e-185">抽出プログラムを作成すると、抽出ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-185">When you create the extractor, the extractor page opens.</span></span> <span data-ttu-id="98b8e-186">ここでは、サンプルファイルの一覧が表示されます。リストの最初のファイルは、viewer に表示されています。</span><span class="sxs-lookup"><span data-stu-id="98b8e-186">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

![[クライアント抽出プログラム] [ラベル付き例] ページのスクリーンショット。](../media/content-understanding/client-extractor-labeled-examples.png) 

<span data-ttu-id="98b8e-188">エンティティにラベルを付けするには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-188">To label the entity:</span></span>

1. <span data-ttu-id="98b8e-189">Viewer で、ファイルから抽出するデータを選択します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-189">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="98b8e-190">たとえば、クライアントを抽出する場合は、最初のファイル (この例では Best *For You Organics)* でクライアント値を強調表示し、[保存] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="98b8e-190">For example, if you want to extract the *Client*, you highlight the client value in the first file (in this example, *Best For You Organics*), and then select **Save**.</span></span> <span data-ttu-id="98b8e-191">[ラベル付き例] ボックスの一覧の [ **ラベル** ] 列に、ファイルの値が **表示** されます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-191">You'll see the value display from the file in the **Labeled examples** list, under the **Label** column.</span></span>

2. <span data-ttu-id="98b8e-192">[ **次のファイル]** を選択して自動保存し、ビューアーの一覧で次のファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-192">Select **Next file** to autosave and open the next file in the list in the viewer.</span></span> <span data-ttu-id="98b8e-193">または、[ **保存] を** 選択し、[ラベル付き例] リストから別 **のファイルを選択** します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-193">Or select **Save**, and then select another file from the **Labeled examples** list.</span></span>

3. <span data-ttu-id="98b8e-194">ビューアーで、手順 1 と 2 を繰り返し、すべてのファイルにラベルを保存するまで繰り返します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-194">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all the files.</span></span>

<span data-ttu-id="98b8e-195">ファイルのラベルが付いた後、トレーニングに移動する通知バナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-195">After you've labeled the files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="98b8e-196">より多くのドキュメントにラベルを付け、トレーニングに進むか選択できます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-196">You can choose to label more documents or advance to training.</span></span>

#### <a name="add-an-explanation"></a><span data-ttu-id="98b8e-197">説明を作成する</span><span class="sxs-lookup"><span data-stu-id="98b8e-197">Add an explanation</span></span>

<span data-ttu-id="98b8e-198">エンティティ形式自体と、サンプル ファイルに含め得るバリエーションに関するヒントを提供する説明を作成できます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-198">You can create an explanation that provides a hint about the entity format itself and variations it might have in the example files.</span></span> <span data-ttu-id="98b8e-199">たとえば、日付の値は、次のようなさまざまな形式で指定できます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-199">For example, a date value can be in many different formats, such as:</span></span>

- <span data-ttu-id="98b8e-200">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="98b8e-200">10/14/2019</span></span>
- <span data-ttu-id="98b8e-201">2019 年 10 月 14 日</span><span class="sxs-lookup"><span data-stu-id="98b8e-201">October 14, 2019</span></span>
- <span data-ttu-id="98b8e-202">2019 年 10 月 14 日、月曜日</span><span class="sxs-lookup"><span data-stu-id="98b8e-202">Monday, October 14, 2019</span></span>

<span data-ttu-id="98b8e-203">契約開始日を *特定するために*、パターンの説明を作成できます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-203">To help identify the *Contract Start Date*, you can create a pattern explanation.</span></span>

1. <span data-ttu-id="98b8e-204">[説明 **] セクションで、[** 新規] を選択 **し、[空白** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="98b8e-204">In the **Explanations** section, select **New** and then **Blank**.</span></span>

2. <span data-ttu-id="98b8e-205">[ **説明を作成する** ] ページで：</span><span class="sxs-lookup"><span data-stu-id="98b8e-205">On the **Create an explanation** page:</span></span>

    <span data-ttu-id="98b8e-206">a.</span><span class="sxs-lookup"><span data-stu-id="98b8e-206">a.</span></span> <span data-ttu-id="98b8e-207">[名前 **] フィールド** に、説明の名前 (Date など) を入力 *します*。</span><span class="sxs-lookup"><span data-stu-id="98b8e-207">In the **Name** field, type the name of the explanation (such as *Date*).</span></span>

    <span data-ttu-id="98b8e-208">b.</span><span class="sxs-lookup"><span data-stu-id="98b8e-208">b.</span></span> <span data-ttu-id="98b8e-209">[説明の **種類] フィールドで** 、[パターン一覧] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="98b8e-209">In the **Explanation type** field, select **Pattern list**.</span></span>

    <span data-ttu-id="98b8e-210">c.</span><span class="sxs-lookup"><span data-stu-id="98b8e-210">c.</span></span> <span data-ttu-id="98b8e-211">[値 **] フィールド** に、サンプル ファイルに表示される日付バリエーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-211">In the **Value** field, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="98b8e-212">たとえば、0/00/0000 として表示される日付形式がある場合は、次のようなドキュメントに表示されるバリエーションを入力します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-212">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>

    - <span data-ttu-id="98b8e-213">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="98b8e-213">0/0/0000</span></span>
    - <span data-ttu-id="98b8e-214">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="98b8e-214">0/00/0000</span></span>
    - <span data-ttu-id="98b8e-215">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="98b8e-215">00/0/0000</span></span>
    - <span data-ttu-id="98b8e-216">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="98b8e-216">00/00/0000</span></span>

4. <span data-ttu-id="98b8e-217">[保存 **してトレーニング] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="98b8e-217">Select **Save and train**.</span></span>

#### <a name="test-your-model-again"></a><span data-ttu-id="98b8e-218">モデルを再度テストする</span><span class="sxs-lookup"><span data-stu-id="98b8e-218">Test your model again</span></span>

<span data-ttu-id="98b8e-219">コントラクト モデルは、前に見たことがないサンプル ファイルでテストできます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-219">You can test your Contract model on example files it hasn’t seen before.</span></span> <span data-ttu-id="98b8e-220">これはオプションですが、便利なベスト プラクティスになる場合があります。</span><span class="sxs-lookup"><span data-stu-id="98b8e-220">This is optional, but it can be a useful best practice.</span></span>

1. <span data-ttu-id="98b8e-221">[契約 **分類子>モデル>] ページで** 、[テスト] タブ **を選択** します。これにより、ラベルが付いていないサンプル ファイルでモデルが実行されます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-221">On the **Models > Contract > Contract classifier** page, select the **Test** tab. This runs the model on your unlabeled example files.</span></span>

2. <span data-ttu-id="98b8e-222">テスト ファイル **の一覧** で、サンプル ファイルが表示され、モデルが必要な情報を抽出できる場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-222">In the **Test files** list, your example files display and shows if the model is able to extract the information you need.</span></span> <span data-ttu-id="98b8e-223">この情報を使用して、ドキュメントを特定するときの分類子の有効性を判断します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-223">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

3. <span data-ttu-id="98b8e-224">完了したら、[トレーニングの終了 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="98b8e-224">When done, select **Exit Training**.</span></span>

### <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="98b8e-225">ドキュメント ライブラリにモデルを適用する</span><span class="sxs-lookup"><span data-stu-id="98b8e-225">Apply your model to a document library</span></span>

<span data-ttu-id="98b8e-226">モデルをドキュメント ライブラリにSharePointするには、次のSharePoint使用します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-226">To apply your model to a SharePoint document library:</span></span>

1. <span data-ttu-id="98b8e-227">[モデルと **契約>] ページの [** キー アクション] の [モデルをライブラリに適用する] で、[  >  モデルの適用]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="98b8e-227">On the **Models > Contract** page, under **Key actions** > **Apply model to libraries**, select **Apply model**.</span></span>

   ![[ライブラリにモデルを適用する] オプションが強調表示された [コントラクト] ページを示すスクリーンショット。](../media/content-understanding/key-actions-apply-model.png)

2. <span data-ttu-id="98b8e-229">[契約 **の追加]** パネルで、モデルSharePointするドキュメント ライブラリを含むサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-229">On the **Add Contract** panel, select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="98b8e-230">リストにサイトが表示されない場合は、検索ボックスを使用して検索します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-230">If the site does not show in the list, use the search box to find it.</span></span> <span data-ttu-id="98b8e-231">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-231">Select **Add**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="98b8e-232">モデルを適用しようとしているドキュメントライブラリへの *リスト管理* 許可を持っているかまたは、*編集* 権限を持っていなければなりません。</span><span class="sxs-lookup"><span data-stu-id="98b8e-232">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span>

3. <span data-ttu-id="98b8e-233">サイトを選択した後、モデルを適用するドキュメント ライブラリを選択します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-233">After you select the site, select the document library to which you want to apply the model.</span></span>

4. <span data-ttu-id="98b8e-234">モデルはコンテンツ タイプに関連付けられているため、ライブラリに適用すると、抽出したラベルが列として表示されたコンテンツ タイプとそのビューが追加されます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-234">Because the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="98b8e-235">このビューは、既定ではライブラリの既定のビューですが、[詳細設定] を選択し、[この新しいビューを既定として設定する] チェック ボックスをオフにすることで、既定のビューにしないオプション **を選択できます**。</span><span class="sxs-lookup"><span data-stu-id="98b8e-235">This view is the library's default view by default, but you can optionally choose to have it not be the default view by selecting **Advanced settings** and clearing the **Set this new view as default** check box.</span></span>

5. <span data-ttu-id="98b8e-236">モデルをライブラリに適用するには、[ **追加** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-236">Select **Add** to apply the model to the library.</span></span>

6. <span data-ttu-id="98b8e-237">[モデル **>契約**] ページの [このモデルを含むライブラリ] セクションに、一覧に表示されるサイトの URL SharePoint表示されます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-237">On the **Models > Contract** page, in the **Libraries with this model** section, you'll see the URL to the SharePoint site listed.</span></span>

    ![[このモデルを使用したライブラリ] セクションを示すコントラクト ホーム ページのスクリーンショット。](../media/content-understanding/contract-libraries-with-this-model.png)

7. <span data-ttu-id="98b8e-239">[ライブラリ **設定**  >  **設定] の下:**</span><span class="sxs-lookup"><span data-stu-id="98b8e-239">Under **Settings** > **Library settings**:</span></span>

   - <span data-ttu-id="98b8e-240">Status という名前の列 **を追加し** 、列 **の種類として [選択肢** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-240">Add a column named **Status** and select **Choice** as the column type.</span></span>
   - <span data-ttu-id="98b8e-241">[確認中 **] 、[承認済\*\*\*\*み] 、および**[拒否済み]**の値を適用** します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-241">Apply the **In review**, **Approved**, and **Rejected** values.</span></span>

<span data-ttu-id="98b8e-242">モデルをドキュメント ライブラリに適用した後、サイトへのドキュメントのアップロードを開始し、結果を確認できます。</span><span class="sxs-lookup"><span data-stu-id="98b8e-242">After you apply the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

## <a name="next-step"></a><span data-ttu-id="98b8e-243">次の手順</span><span class="sxs-lookup"><span data-stu-id="98b8e-243">Next step</span></span>

[<span data-ttu-id="98b8e-244">手順 2.契約Microsoft Teamsチャネルを作成するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="98b8e-244">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)