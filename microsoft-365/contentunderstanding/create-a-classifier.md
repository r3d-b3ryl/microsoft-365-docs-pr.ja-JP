---
title: 分類子を作成する
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 分類子を作成する方法について説明します。
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294904"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="fbc93-103">Microsoft SharePoint の同期 Tex で分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="fbc93-103">Create a classifier in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="fbc93-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="fbc93-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="fbc93-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbc93-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="fbc93-106">分類子は、ドキュメントの種類の識別と分類を自動化するために使用できるモデルの種類です。</span><span class="sxs-lookup"><span data-stu-id="fbc93-106">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="fbc93-107">たとえば、次の図に示すように、ドキュメントライブラリに追加されたすべての *契約更新* ドキュメントを識別することができます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![契約更新ドキュメント](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="fbc93-109">分類子を作成すると、モデルに関連付けられる新しい [SharePoint コンテンツタイプ](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-109">Creating a classifier enables you to create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="fbc93-110">分類子を作成するときは、モデルを定義するための *説明* を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbc93-110">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="fbc93-111">これにより、このドキュメントの種類を一貫して見つけ出すことが予想される一般的なデータを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-111">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="fbc93-112">ドキュメントの種類 ("ファイル例") の例を使用して、同じコンテンツタイプのファイルを識別するために、モデルを "トレーニング" します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-112">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="fbc93-113">分類子を作成するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbc93-113">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="fbc93-114">モデルに名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-114">Name your model.</span></span>
2. <span data-ttu-id="fbc93-115">サンプルファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-115">Add your example files.</span></span>
3. <span data-ttu-id="fbc93-116">サンプルファイルにラベルを付けます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-116">Label your example files.</span></span>
4. <span data-ttu-id="fbc93-117">説明を作成します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-117">Create an explanation.</span></span>
5. <span data-ttu-id="fbc93-118">モデルをテストします。</span><span class="sxs-lookup"><span data-stu-id="fbc93-118">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="fbc93-119">モデルでは、分類子を使用してドキュメントタイプを識別および分類していますが、モデルによって識別される各ファイルから特定の情報を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-119">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="fbc93-120">これを行うには、モデルに追加する **抽出器** を作成します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-120">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="fbc93-121">「 [Create a 抽出器](create-an-extractor.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbc93-121">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="fbc93-122">モデルに名前をつける</span><span class="sxs-lookup"><span data-stu-id="fbc93-122">Name your model</span></span>

<span data-ttu-id="fbc93-123">モデルを作成するための最初の手順として、名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-123">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="fbc93-124">コンテンツセンターで、[ **新規**] を選択してから、 **モデルを作成**します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-124">From the Content Center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="fbc93-125">[ **新しいドキュメントのモデル** ] ウィンドウで、[ **名前** ] フィールドにモデルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-125">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="fbc93-126">たとえば、契約の更新ドキュメントを識別する場合は、モデル *契約の更新*に名前を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-126">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="fbc93-127">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-127">Choose **Create**.</span></span> <span data-ttu-id="fbc93-128">これにより、モデルのホームページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-128">This creates a home page for the model.</span></span></br>

    ![分類子モデルのホームページ](../media/content-understanding/model-home.png)

<span data-ttu-id="fbc93-130">モデルを作成するときに、新しい SharePoint コンテンツタイプも作成します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-130">When you create a model, you are also creating a new SharePoint content type.</span></span> <span data-ttu-id="fbc93-131">SharePoint コンテンツタイプは、共通の特性を持つドキュメントのカテゴリを表し、その特定のコンテンツの列またはメタデータプロパティのコレクションを共有します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-131">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="fbc93-132">SharePoint コンテンツタイプは、 [コンテンツタイプギャラリー](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f)を使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-132">SharePoint Content Types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="fbc93-133">この例では、モデルを作成するときに、新しい *契約更新* コンテンツタイプを作成します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-133">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="fbc93-134">このモデルを SharePoint コンテンツタイプギャラリーの既存のコンテンツタイプにマッピングして、そのスキーマを使用する場合は、[ **詳細設定** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-134">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="fbc93-135">既存のコンテンツタイプを使用してスキーマを活用し、識別と分類に役立てることができますが、識別されたファイルから情報を抽出するためにモデルをトレーニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbc93-135">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![詳細設定](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="fbc93-137">サンプルファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="fbc93-137">Add your example files</span></span>

<span data-ttu-id="fbc93-138">モデルのホームページで、ドキュメントの種類を識別するためにモデルをトレーニングするために必要なサンプルファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-138">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="fbc93-139">分類子と [抽出器トレーニング](create-an-extractor.md)の両方に同じファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbc93-139">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="fbc93-140">後で追加するオプションは常に用意されていますが、通常は、一連の完全なサンプルファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-140">You always have the option to add more later, but typically you add a full set of sample files.</span></span> <span data-ttu-id="fbc93-141">モデルを学習するために、いくつかのラベルを付け、残りの未ラベルのものをテストしてモデルの適合性を評価します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-141">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="fbc93-142">トレーニングセットについては、正と負の両方の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-142">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="fbc93-143">正の例: ドキュメントの種類を表すドキュメント。</span><span class="sxs-lookup"><span data-stu-id="fbc93-143">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="fbc93-144">これらには、常にこの種類のドキュメントに含まれる文字列と情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fbc93-144">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="fbc93-145">負の例: ドキュメントの種類を表していないドキュメント。</span><span class="sxs-lookup"><span data-stu-id="fbc93-145">Negative example: Documents that do not represent the document type.</span></span> <span data-ttu-id="fbc93-146">このようなドキュメントの種類には、文字列と情報が含まれていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fbc93-146">These are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="fbc93-147">モデルを学習するには、少なくとも5つの正の例と、少なくとも1つの負の例を使用してください。</span><span class="sxs-lookup"><span data-stu-id="fbc93-147">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="fbc93-148">トレーニングプロセスの後、モデルをテストするための追加のを作成する。</span><span class="sxs-lookup"><span data-stu-id="fbc93-148">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="fbc93-149">サンプルファイルを追加するには:</span><span class="sxs-lookup"><span data-stu-id="fbc93-149">To add sample files:</span></span>

1. <span data-ttu-id="fbc93-150">モデルのホームページで、[ **サンプルライブラリのビルド** ] タイルの [ **ファイルの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fbc93-150">From the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="fbc93-151">[ **モデルのサンプルファイルを選択** してください] ページで、コンテンツセンターのサンプルファイルライブラリからサンプルファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-151">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="fbc93-152">まだアップロードしていない場合は、[ **アップロード** ] をクリックして、サンプルファイルライブラリに移動することによって、今すぐアップロードします。</span><span class="sxs-lookup"><span data-stu-id="fbc93-152">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="fbc93-153">モデルのトレーニングに使用するサンプルファイルを選択したら、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fbc93-153">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![サンプルファイルの選択](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="fbc93-155">サンプルファイルにラベルを付ける</span><span class="sxs-lookup"><span data-stu-id="fbc93-155">Label your example files</span></span>

<span data-ttu-id="fbc93-156">サンプルファイルを追加した後、そのファイルに正または負の例のいずれかを付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbc93-156">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="fbc93-157">モデルのホームページで、[ **ファイルの分類] および [トレーニングの実行** ] タイルの [ **分類子のトレーニング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fbc93-157">From the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="fbc93-158">これにより、最初のファイルが viewer に表示された状態で、サンプルファイルの一覧を示すラベルページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-158">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="fbc93-159">最初のサンプルファイルの先頭にあるビューアーに、作成したモデルの例としてファイルがあるかどうかを確認するテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-159">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="fbc93-160">正の例の場合は、[ **はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-160">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="fbc93-161">負の例の場合は、[ **いいえ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-161">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="fbc93-162">左側の **ラベル付きの例** リストから、例として使用する追加のファイルを選択し、それらにラベルを付けます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-162">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![分類子ホームページ](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="fbc93-164">少なくとも5つの正の例と1つの負の例をラベル付けします。</span><span class="sxs-lookup"><span data-stu-id="fbc93-164">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="fbc93-165">説明を作成する</span><span class="sxs-lookup"><span data-stu-id="fbc93-165">Create an explanation</span></span>

<span data-ttu-id="fbc93-166">次の手順では、[教育] ページで説明を作成します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-166">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="fbc93-167">説明により、モデルでドキュメントを認識する方法が理解されます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-167">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="fbc93-168">たとえば、契約更新ドキュメントには、常に *追加の開示テキスト文字列に対する要求* が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fbc93-168">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="fbc93-169">抽出機能を使用する場合、説明では、文書から抽出する文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-169">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="fbc93-170">説明を作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="fbc93-170">To create an explanation:</span></span>

1. <span data-ttu-id="fbc93-171">モデルのホームページで、[ **列車** ] タブを選択して [列車] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-171">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="fbc93-172">[トレーニング] ページの [ **トレーニングファイル** ] セクションに、以前にラベル付けしたサンプルファイルの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-172">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="fbc93-173">リストから、ポジファイルのいずれかを選択すると、ビューアーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-173">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="fbc93-174">[説明] セクションで、[ **新規** ] を選択し、[ **空白**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fbc93-174">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="fbc93-175">[ **説明の作成** ] ページで、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="fbc93-175">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="fbc93-176">a. </span><span class="sxs-lookup"><span data-stu-id="fbc93-176">a.</span></span> <span data-ttu-id="fbc93-177">**名前**を入力します ("暴露ブロック" など)。</span><span class="sxs-lookup"><span data-stu-id="fbc93-177">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="fbc93-178">b. </span><span class="sxs-lookup"><span data-stu-id="fbc93-178">b.</span></span> <span data-ttu-id="fbc93-179">**種類**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-179">Select the **Type**.</span></span> <span data-ttu-id="fbc93-180">サンプルの場合は、テキスト文字列を追加するので、[ **語句リスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-180">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="fbc93-181">c. </span><span class="sxs-lookup"><span data-stu-id="fbc93-181">c.</span></span> <span data-ttu-id="fbc93-182">[ **ここに入力** ] ボックスに、文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-182">In the **Type here** box, type the string.</span></span> <span data-ttu-id="fbc93-183">サンプルについては、「追加情報開示のための要求」を追加してください。</span><span class="sxs-lookup"><span data-stu-id="fbc93-183">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="fbc93-184">文字列が大文字小文字を区別する必要がある場合は、 **大文字小文字を区別** することができます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-184">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="fbc93-185">d. </span><span class="sxs-lookup"><span data-stu-id="fbc93-185">d.</span></span> <span data-ttu-id="fbc93-186">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fbc93-186">Click **Save**.</span></span>

    ![説明を作成する](../media/content-understanding/explanation.png) 
    
 
5. <span data-ttu-id="fbc93-188">モデルでは、作成した説明が、正と負の例として、残りのラベル付きサンプルファイルを正確に識別するのに十分であるかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-188">The model now checks to see if the explanation you created was good enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="fbc93-189">[トレーニングファイル] セクションで、トレーニングの完了後に [ **評価** ] 列をチェックして、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-189">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="fbc93-190">作成した説明が正または負のラベルと一致している場合は、ファイルに **一致**する値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-190">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![一致する値](../media/content-understanding/match.png) 

<span data-ttu-id="fbc93-192">ラベル付きファイルに **不一致** が発生した場合は、ドキュメントの種類を識別するための詳細な情報をモデルに提供するために追加の説明を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbc93-192">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="fbc93-193">その場合は、ファイルをクリックして、不一致が発生した理由に関する詳細情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-193">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="fbc93-194">モデルをテストする</span><span class="sxs-lookup"><span data-stu-id="fbc93-194">Test your model</span></span>

<span data-ttu-id="fbc93-195">ラベル付けされたサンプルファイルに一致するものを受信した場合、残りのラベルのないサンプルファイルでモデルをテストできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fbc93-195">If you received a match on your labeled sample files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="fbc93-196">モデルのホームページで、[ **テスト** ] タブを選択します。 これにより、ラベルのないサンプルファイルでモデルが実行されます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="fbc93-197">[ **テストファイル** ] リストでは、サンプルファイルが表示され、モデルが正または負のどちらになるかが示されます。</span><span class="sxs-lookup"><span data-stu-id="fbc93-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="fbc93-198">この情報を使用して、ドキュメントを識別する際に、分類子の有効性を判断します。</span><span class="sxs-lookup"><span data-stu-id="fbc93-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![ラベルのないファイルのテスト](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="fbc93-200">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbc93-200">See Also</span></span>
[<span data-ttu-id="fbc93-201">抽出器を作成する</span><span class="sxs-lookup"><span data-stu-id="fbc93-201">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="fbc93-202">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="fbc93-202">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="fbc93-203">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="fbc93-203">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="fbc93-204">モデルを適用する</span><span class="sxs-lookup"><span data-stu-id="fbc93-204">Apply a model</span></span>](apply-a-model.md) 
