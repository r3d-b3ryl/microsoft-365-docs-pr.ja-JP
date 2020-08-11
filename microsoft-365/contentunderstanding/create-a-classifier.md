---
title: 分類子を作成する (プレビュー)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: 分類子を作成する方法について説明します。
ms.openlocfilehash: 088770ace8914b583b184c78c3ce110d9d68b4c7
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612610"
---
# <a name="create-a-classifier-preview"></a><span data-ttu-id="be399-103">分類子を作成する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="be399-103">Create a classifier (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="be399-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="be399-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="be399-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be399-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="be399-106">分類子は、ドキュメントの種類の識別と分類を自動化するモデルの種類です。</span><span class="sxs-lookup"><span data-stu-id="be399-106">A classifier is a type of model that automates identification and classification of a document type.</span></span> <span data-ttu-id="be399-107">たとえば、次のような、ドキュメントライブラリに追加されたすべての*契約の更新*ドキュメントを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="be399-107">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as the following.</span></span>

![契約更新ドキュメント](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="be399-109">分類子を作成すると、モデルに関連付けられる新しい[SharePoint コンテンツタイプ](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview)が作成されます。</span><span class="sxs-lookup"><span data-stu-id="be399-109">Creating a classifier will create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="be399-110">分類子を作成するときには、このドキュメントの種類に対して一貫して検索すると予想される一般的なデータを記録してモデルを定義するのに役立つ*説明*を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be399-110">When creating the classifier, you need to create *explanations* that help to define the model by noting common data that you would expect to find consistently for this document type.</span></span> 

<span data-ttu-id="be399-111">ドキュメントの種類 ("ファイルの例") の例を使用して、同じコンテンツタイプのファイルを識別するために、モデルを "トレーニング" します。</span><span class="sxs-lookup"><span data-stu-id="be399-111">You use examples of the document type ("example files") to help "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="be399-112">分類子を作成するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="be399-112">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="be399-113">モデルに名前をつける</span><span class="sxs-lookup"><span data-stu-id="be399-113">Name your model</span></span>
2. <span data-ttu-id="be399-114">サンプルファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="be399-114">Add your example files</span></span>
3. <span data-ttu-id="be399-115">サンプルファイルにラベルを付ける</span><span class="sxs-lookup"><span data-stu-id="be399-115">Label your example files</span></span>
4. <span data-ttu-id="be399-116">説明を作成する</span><span class="sxs-lookup"><span data-stu-id="be399-116">Create an explanation</span></span>
5. <span data-ttu-id="be399-117">モデルをテストする</span><span class="sxs-lookup"><span data-stu-id="be399-117">Test your model</span></span> 

> [!Note]
> <span data-ttu-id="be399-118">分類子は、ドキュメントの種類を識別して分類するためにモデルによって使用されますが、モデルによって識別される各ファイルから特定の情報を取得するよう選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="be399-118">While a classifier is used by your model to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="be399-119">これを行うには、モデルに追加する**抽出器**を作成します。これについては、「 [Create a エクストラクター](create-an-extractor.md)」で説明されています。</span><span class="sxs-lookup"><span data-stu-id="be399-119">You do this by creating an **extractor** to add to your model, and this is described in [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="be399-120">モデルに名前をつける</span><span class="sxs-lookup"><span data-stu-id="be399-120">Name your model</span></span>

<span data-ttu-id="be399-121">最初の手順として、名前を指定して、コンテンツセンターにモデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="be399-121">The first step is to create your model in your Content Center by giving it a name:</span></span>

1. <span data-ttu-id="be399-122">コンテンツセンターで、[**新規**] をクリックし、[**モデルの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be399-122">In your Content Center, click **New**, and then click **Create a model**.</span></span>
2. <span data-ttu-id="be399-123">[**新しいドキュメントのモデル**] ウィンドウで、[**名前**] フィールドにモデルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="be399-123">In the **New document understanding model** pane, in the **Name** field, type the name of the model.</span></span> <span data-ttu-id="be399-124">この例では、契約の更新ドキュメントを特定する場合、このモデル契約の*更新*の名前を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="be399-124">For our example, if we want to identify contract renewal documents, we might name this model *Contract Renewal*.</span></span>
3. <span data-ttu-id="be399-125">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be399-125">Click **Create**.</span></span> <span data-ttu-id="be399-126">これにより、モデルのホームページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="be399-126">This will create a home page for the model.</span></span></br>

    ![分類子モデルのホームページ](../media/content-understanding/model-home.png)

<span data-ttu-id="be399-128">モデルを作成するときには、新しい SharePoint コンテンツタイプを作成します。</span><span class="sxs-lookup"><span data-stu-id="be399-128">When you create a model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="be399-129">SharePoint コンテンツタイプは、共通の特性を持つドキュメントのカテゴリを表し、その特定のコンテンツの列またはメタデータプロパティのコレクションを共有します。</span><span class="sxs-lookup"><span data-stu-id="be399-129">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="be399-130">SharePoint コンテンツタイプは、[コンテンツタイプギャラリー]()を使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="be399-130">SharePoint Content Types are managed through the [Content types gallery]().</span></span> <span data-ttu-id="be399-131">この例では、モデルを作成するときに、新しい*契約更新*コンテンツタイプを作成します。</span><span class="sxs-lookup"><span data-stu-id="be399-131">For our example, when we create the model, we will be creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="be399-132">このモデルを SharePoint コンテンツタイプギャラリーの既存のコンテンツタイプにマッピングして、そのスキーマを使用する場合は、[**詳細設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be399-132">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="be399-133">既存のコンテンツタイプを使用してスキーマを活用し、識別と分類に役立てることができますが、識別されたファイルから情報を抽出するためにモデルをトレーニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="be399-133">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you will still need to train your model to extract information from files it identifies.</span></span></br>

![詳細設定](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="be399-135">サンプルファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="be399-135">Add your example files</span></span>

<span data-ttu-id="be399-136">モデルのホームページでは、ドキュメントの種類を識別するためにモデルをトレーニングするのに役立つサンプルファイルを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="be399-136">On the model home page, you can add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> <span data-ttu-id="be399-137">分類子と[抽出器トレーニング](create-an-extractor.md)の両方に同じファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be399-137">The same files should be used for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="be399-138">後で追加するオプションは常に用意されていますが、通常は、サンプルファイルの完全なセットを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be399-138">You always have the option to add more later, but typically you should add a full set of example files.</span></span> <span data-ttu-id="be399-139">モデルの適合性を評価するために、いくつかのラベルを付けて、モデルを学習し、残りの未ラベルのものをテストします。</span><span class="sxs-lookup"><span data-stu-id="be399-139">You will label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="be399-140">トレーニングセットについては、正の例と負の例の両方を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be399-140">For your training set, you will want to use both positive examples, and negative examples:</span></span>
- <span data-ttu-id="be399-141">正の例: ドキュメントの種類を表すドキュメント。</span><span class="sxs-lookup"><span data-stu-id="be399-141">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="be399-142">これらには、常にこの種類のドキュメントに含まれる文字列と情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="be399-142">They contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="be399-143">負の例: ドキュメントの種類を表していないドキュメント。</span><span class="sxs-lookup"><span data-stu-id="be399-143">Negative example: Documents that do not represent the document type.</span></span>  <span data-ttu-id="be399-144">このドキュメントでは、文字列と情報が含まれていない必要があります。</span><span class="sxs-lookup"><span data-stu-id="be399-144">They are missing strings and information that needs to be present in this type of document.</span></span>

<span data-ttu-id="be399-145">モデルを学習するには、少なくとも5つの正の例と1つの負の例を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be399-145">You will want to use at least five positive examples and one negative examples to train your model.</span></span>  <span data-ttu-id="be399-146">トレーニング後に、モデルをテストするための追加のものが必要になります。</span><span class="sxs-lookup"><span data-stu-id="be399-146">You will want to have additional ones to test your model after training.</span></span>

<span data-ttu-id="be399-147">サンプルファイルを追加するには:</span><span class="sxs-lookup"><span data-stu-id="be399-147">To add sample files:</span></span>

1. <span data-ttu-id="be399-148">モデルのホームページで、[**サンプルライブラリのビルド**] タイルの [**ファイルの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be399-148">On the model home page, in the **Build sample library** tile, click **Add files**.</span></span>
2. <span data-ttu-id="be399-149">[**モデルのサンプルファイルを選択**してください] ページで、コンテンツセンターのサンプルファイルライブラリからサンプルファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="be399-149">On the **Select sample files for your model** page, select your example files from the Sample files library in the Content Center.</span></span> <span data-ttu-id="be399-150">まだアップロードしていない場合は、[**アップロード**] をクリックしてサンプルファイルライブラリに移動することによって、今すぐアップロードすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="be399-150">If you had not already uploaded them there, you can choose to upload them now by clicking **Upload** to move them the Sample file library.</span></span>
3. <span data-ttu-id="be399-151">モデルのトレーニングに使用するサンプルファイルを選択したら、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be399-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![サンプルファイルの選択](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="be399-153">サンプルファイルにラベルを付ける</span><span class="sxs-lookup"><span data-stu-id="be399-153">Label your example files</span></span>

<span data-ttu-id="be399-154">サンプルファイルを追加した後、そのファイルに正の例または負の例のいずれかとしてラベルを付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="be399-154">After adding your example files, you then need to label them as either positive examples or negative examples.</span></span>

1. <span data-ttu-id="be399-155">モデルのホームページで、[**ファイルの分類] および [トレーニングの実行**] タイルの [**分類子のトレーニング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be399-155">On the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="be399-156">これにより、最初のファイルが viewer に表示された状態で、サンプルファイルの一覧を示すラベルページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be399-156">This will display the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="be399-157">Viewer の最初のサンプルファイルの先頭に、作成したモデルの例としてファイルがあるかどうかを確認するテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be399-157">In the viewer, on the top of the first example file, you will see text asking you if the file is an example of the model you just created.</span></span> <span data-ttu-id="be399-158">正の例の場合は、[**はい]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="be399-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="be399-159">負の例の場合は、[**いいえ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be399-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="be399-160">左側の**ラベル付きの例**リストから、例として使用する追加のファイルを選択して、それらにラベルを付けます。</span><span class="sxs-lookup"><span data-stu-id="be399-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them as well.</span></span> 

    ![分類子モデルのホームページ](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> <span data-ttu-id="be399-162">少なくとも5つの正の例と1つの負の例をラベル付けします。</span><span class="sxs-lookup"><span data-stu-id="be399-162">Label at least five positive examples, and one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="be399-163">説明を作成する</span><span class="sxs-lookup"><span data-stu-id="be399-163">Create an explanation</span></span>

<span data-ttu-id="be399-164">次の手順では、[Train] ページで説明を作成します。</span><span class="sxs-lookup"><span data-stu-id="be399-164">The next step is to create an explanation on the Train page.</span></span>  <span data-ttu-id="be399-165">説明は、モデルでこのドキュメントを認識する方法を理解するためのヒントまたは手掛かりです。</span><span class="sxs-lookup"><span data-stu-id="be399-165">An explanation is a hint or clue to help the model understand how to recognize this document.</span></span> <span data-ttu-id="be399-166">たとえば、契約の更新ドキュメントには、常に*追加の開示テキスト文字列の要求*が含まれています。</span><span class="sxs-lookup"><span data-stu-id="be399-166">For example, our Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="be399-167">抽出機能を使用する場合、文書から抽出する文字列を識別するために説明を使用します。</span><span class="sxs-lookup"><span data-stu-id="be399-167">When used with extractors, an explanation is use to identify the string that you want to extract from the document.</span></span> 

<span data-ttu-id="be399-168">説明を作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="be399-168">To create an explanation:</span></span>

1. <span data-ttu-id="be399-169">モデルのホームページで、[**列車**] タブをクリックして [列車] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="be399-169">On the model home page, click the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="be399-170">[トレーニング] ページの [**トレーニングファイル**] セクションに、以前にラベル付けしたサンプルファイルの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be399-170">On the Train page, in the **Trained files** section, you will see a list of the example files that you had labeled previously.</span></span> <span data-ttu-id="be399-171">リストから1つのポジファイルを選択すると、ビューアーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="be399-171">Select one of your positive files from the list, and it will display in the viewer.</span></span>
3. <span data-ttu-id="be399-172">[説明] セクションで、[**新規**] をクリックし、[**空白**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be399-172">In the Explanation section, click **New**, then click **Blank**.</span></span>
4. <span data-ttu-id="be399-173">[**説明の作成**] ページで、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="be399-173">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="be399-174">a.</span><span class="sxs-lookup"><span data-stu-id="be399-174">a.</span></span> <span data-ttu-id="be399-175">**名前**を入力します ("暴露ブロック" など)。</span><span class="sxs-lookup"><span data-stu-id="be399-175">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="be399-176">b.</span><span class="sxs-lookup"><span data-stu-id="be399-176">b.</span></span> <span data-ttu-id="be399-177">**種類**を選択します。</span><span class="sxs-lookup"><span data-stu-id="be399-177">Select the **Type**.</span></span> <span data-ttu-id="be399-178">この例では、テキスト文字列を追加しているため、**語句リスト**を選択します。</span><span class="sxs-lookup"><span data-stu-id="be399-178">For our example, we'll select **Phrase list**, since we are adding a text string.</span></span></br>
    <span data-ttu-id="be399-179">c. </span><span class="sxs-lookup"><span data-stu-id="be399-179">c.</span></span> <span data-ttu-id="be399-180">[**ここに入力**] ボックスに、文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="be399-180">In the **Type here** box, type the string.</span></span>  <span data-ttu-id="be399-181">この例では、「追加情報開示のための要求」を追加します。</span><span class="sxs-lookup"><span data-stu-id="be399-181">For our example, we'll add "Request for additional disclosure".</span></span> <span data-ttu-id="be399-182">文字列が大文字小文字を区別する必要がある場合は、**大文字小文字を区別**することができます。</span><span class="sxs-lookup"><span data-stu-id="be399-182">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="be399-183">d. </span><span class="sxs-lookup"><span data-stu-id="be399-183">d.</span></span> <span data-ttu-id="be399-184">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be399-184">Click **Save**.</span></span>

    ![説明を作成する](../media/content-understanding/explanation.png) 
    
 
5.  <span data-ttu-id="be399-186">モデルでは、作成した説明が、正の例および負の例のように、ラベル付けされた残りのサンプルファイルを正確に識別できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="be399-186">The model will now check to see if the explanation you created was good enough to identify your remaining labeled example files correctly as positive and negative examples.</span></span> <span data-ttu-id="be399-187">[トレーニングされたファイル] セクションで、トレーニングの完了後に [**評価**] 列をチェックして、結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="be399-187">In Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span>  <span data-ttu-id="be399-188">作成した説明が、ラベル付けした内容 (正または負) と一致するように十分に一致した場合は、ファイルに**一致**する値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be399-188">The files will show a value of **Match** if the explanation you created was enough to match what you had labeled them as (positive or negative).</span></span>

    ![説明を作成する](../media/content-understanding/match.png) 

<span data-ttu-id="be399-190">ラベル付けされたファイルに**不一致**が発生した場合は、ドキュメントの種類を識別するための詳細な情報をモデルに提供するために追加の説明を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be399-190">If you receive a **Mismatch** on your labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="be399-191">このファイルをクリックすると、不一致が発生した理由に関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be399-191">You can click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="be399-192">モデルをテストする</span><span class="sxs-lookup"><span data-stu-id="be399-192">Test your model</span></span>

<span data-ttu-id="be399-193">ラベル付けされたサンプルファイルで一致するものを受信した場合、残りのラベルのないサンプルファイルでモデルをテストできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="be399-193">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="be399-194">モデルのホームページで、[**テスト**] タブをクリックします。 これにより、ラベルのないサンプルファイルでモデルが実行されます。</span><span class="sxs-lookup"><span data-stu-id="be399-194">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="be399-195">[**テストファイル**] リストでは、サンプルファイルが表示され、モデルが正または負の例として予測されているかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be399-195">In the **Test files** list, your example files will display and will show if the model predicted them to be positive or negative examples.</span></span> <span data-ttu-id="be399-196">この情報を使用して、ドキュメントを識別する際に、分類子の有効性を判断することができます。</span><span class="sxs-lookup"><span data-stu-id="be399-196">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![ラベルのないファイルのテスト](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a><span data-ttu-id="be399-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="be399-198">See Also</span></span>
[<span data-ttu-id="be399-199">抽出器を作成する</span><span class="sxs-lookup"><span data-stu-id="be399-199">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="be399-200">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="be399-200">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="be399-201">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="be399-201">Create a form processing model</span></span>](create-a-form-processing-model.md)</br>
[<span data-ttu-id="be399-202">モデルを適用する</span><span class="sxs-lookup"><span data-stu-id="be399-202">Apply a model</span></span>](apply-a-model.md) 




