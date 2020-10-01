---
title: 分類子を作成する
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: 分類子を作成する方法を説明します
ms.openlocfilehash: 1225a4e57969b507ddd2ca7260050605c0db955e
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321859"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="1fd34-103">Microsoft SharePoint Syntexで分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="1fd34-103">Create a classifier in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

<span data-ttu-id="1fd34-104">分類子は、ドキュメントの種類の識別および分類を自動化するために使用できるモデルの種類です。</span><span class="sxs-lookup"><span data-stu-id="1fd34-104">A classifier is a type of model that you can use to automate identification and classification of a document type.</span></span> <span data-ttu-id="1fd34-105">たとえば、次の図に示すように、ドキュメントライブラリに追加されたすべての *契約更新* ドキュメントを特定することができます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-105">For example, you may want to identify all *Contract Renewal* documents that are added to your document library, such as is shown in the following illustration.</span></span>

![契約更新ドキュメント](../media/content-understanding/contract-renewal.png)

<span data-ttu-id="1fd34-107">分類子を作成すると、モデルに関連付けられる新しい [SharePoint コンテンツタイプ](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-107">Creating a classifier enables you to create a new [SharePoint Content Type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) that will be associated to the model.</span></span>

<span data-ttu-id="1fd34-108">分類子を作成するときに、モデルを定義するために *説明* を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fd34-108">When creating the classifier, you need to create *explanations* to define the model.</span></span> <span data-ttu-id="1fd34-109">これにより、このドキュメントの種類に一貫して見つける共通のデータがあることが分かります。</span><span class="sxs-lookup"><span data-stu-id="1fd34-109">This enables you to note common data that you would expect to consistently find this document type.</span></span> 

<span data-ttu-id="1fd34-110">コンテンツタイプが同じファイルを特定できるように、モデルに "トレーニング" するには、ドキュメントの種類 ("ファイルの例") の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-110">Use examples of the document type ("example files") to "train" your model to identify files that have the same content type.</span></span>

<span data-ttu-id="1fd34-111">分類子を作成するには、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fd34-111">To create a classifier, you need to:</span></span>
1. <span data-ttu-id="1fd34-112">モデルに名前をつけます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-112">Name your model.</span></span>
2. <span data-ttu-id="1fd34-113">サンプルファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-113">Add your example files.</span></span>
3. <span data-ttu-id="1fd34-114">サンプルファイルにラベルを付けます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-114">Label your example files.</span></span>
4. <span data-ttu-id="1fd34-115">説明を作成します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-115">Create an explanation.</span></span>
5. <span data-ttu-id="1fd34-116">モデルをテストします。</span><span class="sxs-lookup"><span data-stu-id="1fd34-116">Test your model.</span></span>

> [!NOTE]
> <span data-ttu-id="1fd34-117">モデルでは、ドキュメントタイプを特定して分類するために分類子を使用していますが、モデルで識別された各ファイルから特定の情報を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-117">While your model uses a classifier to identify and classify document types, you can also choose to pull specific pieces of information from each file identified by the model.</span></span> <span data-ttu-id="1fd34-118">これを行うには、モデルに追加する **抽出機能** を作成します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-118">Do this by creating an **extractor** to add to your model.</span></span> <span data-ttu-id="1fd34-119">「[抽出機能を作成](create-an-extractor.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1fd34-119">See [Create an extractor](create-an-extractor.md).</span></span>

## <a name="name-your-model"></a><span data-ttu-id="1fd34-120">モデルに名前を付けます</span><span class="sxs-lookup"><span data-stu-id="1fd34-120">Name your model</span></span>

<span data-ttu-id="1fd34-121">モデルを作成する最初の手順は、名前を付けることです。</span><span class="sxs-lookup"><span data-stu-id="1fd34-121">The first step to create your model is to give it a name:</span></span>

1. <span data-ttu-id="1fd34-122">コンテンツセンターで、[**新しい**]を選択し、**モデルを作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-122">From the Content Center, select **New**, and then **Create a model**.</span></span>
2. <span data-ttu-id="1fd34-123">[ **新しいドキュメント理解モデル** ] ウィンドウで、[ **名前** ] フィールドにモデル名を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-123">In the **New document understanding model** pane, in the **Name** field type the name of the model.</span></span> <span data-ttu-id="1fd34-124">たとえば、契約更新ドキュメントを特定する場合、モデルに*契約更新*と名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-124">For example, if you want to identify contract renewal documents, you could name the model *Contract Renewal*.</span></span>
3. <span data-ttu-id="1fd34-125">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-125">Choose **Create**.</span></span> <span data-ttu-id="1fd34-126">これにより、モデルのホームページが作成されます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-126">This creates a home page for the model.</span></span></br>

    ![分類子モデルのホームページ](../media/content-understanding/model-home.png)

<span data-ttu-id="1fd34-128">モデルを作成するときに、新しいサイトコンテンツタイプも作成します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-128">When you create a model, you are also creating a new site content type.</span></span> <span data-ttu-id="1fd34-129">コンテンツタイプは、共通の特徴を持つドキュメントのカテゴリを表し、特定のコンテンツの列またはメタデータプロパティのコレクションを共有します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-129">A content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="1fd34-130">SharePoint コンテンツタイプは、 [コンテンツタイプギャラリー](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f)で管理されます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-130">SharePoint Content Types are managed through the [Content types gallery](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f).</span></span> <span data-ttu-id="1fd34-131">この例では、モデルを作成するときに、新しい *契約更新* コンテンツタイプを作成します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-131">For this example, when you create the model, you are creating a new *Contract Renewal* content type.</span></span>

<span data-ttu-id="1fd34-132">このモデルを SharePoint コンテンツタイプギャラリーの既存のエンタープライズコンテンツタイプにマッピングして、そのスキーマを使用するには、[ **詳細設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-132">Select **Advanced settings** if you want to map this model to an existing enterprise content type in the SharePoint Content types gallery to use its schema.</span></span> <span data-ttu-id="1fd34-133">エンタープライズコンテンツタイプは、SharePoint 管理センターのコンテンツタイプハブに格納され、テナントのすべてのサイトにシンジケートされます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-133">Enterprise content types are stored in the Content Type Hub in the SharePoint admin center and are syndicated to all sites in the tenant.</span></span> <span data-ttu-id="1fd34-134">ただし、既存のコンテンツタイプを使用して、スキーマを利用し、特定および分類を行うことができますが、特定のファイルから情報を抽出するためにモデルをトレーニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fd34-134">Note that while you can use an existing content type to leverage its schema to help with identification and classification, you still need to train your model to extract information from files it identifies.</span></span></br>

![詳細設定](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a><span data-ttu-id="1fd34-136">サンプルファイルを追加する</span><span class="sxs-lookup"><span data-stu-id="1fd34-136">Add your example files</span></span>

<span data-ttu-id="1fd34-137">モデルホームページで、ドキュメントの種類を識別できるようにモデルをトレーニングするのに役立つサンプルファイルを追加します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-137">On the model home page, add your examples files you will need to help train the model to identify your document type.</span></span> </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> <span data-ttu-id="1fd34-138">分類子と [抽出機能トレーニング](create-an-extractor.md)に同じファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fd34-138">You should use the same files for both classifier and [extractor training](create-an-extractor.md).</span></span> <span data-ttu-id="1fd34-139">後で追加するオプションは常に用意されていますが、通常はサンプルファイルすべてを追加します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-139">You always have the option to add more later, but typically you add a full set of example files.</span></span> <span data-ttu-id="1fd34-140">モデルを学習させるためにラベルを付け、残りのラベルのないものをテストして、モデルの適合性を評価します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-140">Label some to train your model, and test the remaining unlabeled ones to evaluate model fitness.</span></span> 

<span data-ttu-id="1fd34-141">トレーニングセットについては、ポジティブなものとネガティブなものと両方のサンプルを使用します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-141">For your training set, you want to use both positive and negative examples:</span></span>
- <span data-ttu-id="1fd34-142">ポジティブな例: ドキュメントの種類を表すドキュメント。</span><span class="sxs-lookup"><span data-stu-id="1fd34-142">Positive example: Documents that represent the document type.</span></span> <span data-ttu-id="1fd34-143">これらには、この種類のドキュメントに常に存在する文字列と情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-143">These contain strings and information that would always be in this type of document.</span></span>
- <span data-ttu-id="1fd34-144">ネガティブな例: 分類するドキュメントを表さない他のドキュメント。</span><span class="sxs-lookup"><span data-stu-id="1fd34-144">Negative example: Any other document that does not represent the document you want to classify.</span></span> 

<span data-ttu-id="1fd34-145">モデルをトレーニングする場合は、少なくとも1つのポジティブな例と少なくとも1つのネガティブな例を使用してください。</span><span class="sxs-lookup"><span data-stu-id="1fd34-145">Be sure to use at least five positive examples and at least one negative example to train your model.</span></span>  <span data-ttu-id="1fd34-146">トレーニングプロセスの後にモデルをテストするために、追加の作成をするかもしれません。</span><span class="sxs-lookup"><span data-stu-id="1fd34-146">You want to create additional ones to test your model after the training process.</span></span>

<span data-ttu-id="1fd34-147">サンプルファイルを追加するには:</span><span class="sxs-lookup"><span data-stu-id="1fd34-147">To add example files:</span></span>

1. <span data-ttu-id="1fd34-148">[モデルのホーム] ページにある [**サンプルファイル の追加**タイル]で 、[**ファイルの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fd34-148">On the model home page, in the **Add example files** tile, click **Add files**.</span></span>
2. <span data-ttu-id="1fd34-149">[ **モデル 用にサンプルファイルを選択してください**] ページで、コンテンツセンターのトレーニングファイルライブラリからサンプルファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-149">On the **Select example files for your model** page, select your example files from the Training files library in the content center.</span></span> <span data-ttu-id="1fd34-150">まだアップロードしていない場合は、[ **アップロード** ] をクリックして [アップロード] をクリックし、トレーニングファイルライブラリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="1fd34-150">If you had not already uploaded them there, choose to upload them now by clicking **Upload** to copy them to the Training files library.</span></span>
3. <span data-ttu-id="1fd34-151">モデルのトレーニングに使用するサンプルファイルを選択したら、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fd34-151">After selecting your example files to use to train the model, click **Add**.</span></span>

    ![サンプルファイルを選ぶ](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a><span data-ttu-id="1fd34-153">サンプルファイルにラベルを付ける</span><span class="sxs-lookup"><span data-stu-id="1fd34-153">Label your example files</span></span>

<span data-ttu-id="1fd34-154">サンプルファイルを追加した後は、ポジティブまたはネガティブのラベルを付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fd34-154">After adding your example files, you need to label them as either positive or negative examples.</span></span>

1. <span data-ttu-id="1fd34-155">モデルのホームページの [**ファイルを分類してトレーニングを行う**] をクリックして、[**分類子のトレーニング**] を行います。</span><span class="sxs-lookup"><span data-stu-id="1fd34-155">From the model home page, on the **Classify files and run training** tile, click **Train Classifier**.</span></span>
   <span data-ttu-id="1fd34-156">これにより、サンプルファイル名の一覧が表示されるラベルページが表示され、最初のファイルがビューアーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-156">This displays the label page that shows a listing of your example files, with the first file visible in the viewer.</span></span>
2. <span data-ttu-id="1fd34-157">最初のサンプルファイルの一番上にあるビューアーで、作成したモデルの例として、そのファイルが適切かどうかをテキストを見て確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fd34-157">In the viewer on the top of the first example file, you should see text asking if the file is an example of the model you just created.</span></span> <span data-ttu-id="1fd34-158">この例がポジティブの場合は、[ **はい**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-158">If it is a positive example, select **Yes**.</span></span> <span data-ttu-id="1fd34-159">ネガティブの例の場合は、[ **いいえ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-159">If it is a negative example, select **No**.</span></span>
3. <span data-ttu-id="1fd34-160">左側にある **ラベル付きのサンプル** リストで、サンプルとして使用する追加のファイルを選択し、ラベルを付けます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-160">From the **Labeled examples** list on the left, select additional files that you want to use as examples, and label them.</span></span> 

    ![分類子ホームページ](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> <span data-ttu-id="1fd34-162">少なくとも5個のポジティブな例にラベルを付けます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-162">Label at least five positive examples.</span></span> <span data-ttu-id="1fd34-163">少なくとも1つのネガティブな例にラベルを付けます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-163">You must also label at least one negative example.</span></span> 

## <a name="create-an-explanation"></a><span data-ttu-id="1fd34-164">説明を作成する</span><span class="sxs-lookup"><span data-stu-id="1fd34-164">Create an explanation</span></span>

<span data-ttu-id="1fd34-165">次の手順では、トレーニングページに説明を作成します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-165">The next step is for you to create an explanation on the Train page.</span></span> <span data-ttu-id="1fd34-166">詳細を使用すると、モデルがドキュメントの識別をしやすくなります。</span><span class="sxs-lookup"><span data-stu-id="1fd34-166">An explanation helps the model understand how to recognize the document.</span></span> <span data-ttu-id="1fd34-167">たとえば、契約更新ドキュメントには常に、テキスト文字列*追加の開示要求*が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-167">For example, the Contract Renewal documents always contain a *Request for additional disclosure* text string.</span></span>

> [!Note]
> <span data-ttu-id="1fd34-168">エクストラクターを使用する場合、説明を使用すると、文書から抽出する文字列を特定します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-168">When used with extractors, an explanation identifies the string that you want to extract from the document.</span></span> 

<span data-ttu-id="1fd34-169">説明を作成するには:</span><span class="sxs-lookup"><span data-stu-id="1fd34-169">To create an explanation:</span></span>

1. <span data-ttu-id="1fd34-170">[モデルのホーム] ページで、[**トレーニング**] タブを選択し、[トレーニング] ページに移動します。 </span><span class="sxs-lookup"><span data-stu-id="1fd34-170">From the model home page, select the **Train** tab to go to the Train page.</span></span>
2. <span data-ttu-id="1fd34-171">[トレーニング] ページの [**トレーニング済みファイル**] セクション には、以前にラベルが付けられたサンプルファイルの一覧が表示されています。</span><span class="sxs-lookup"><span data-stu-id="1fd34-171">On the Train page, in the **Trained files** section you should see a list of the sample files that you previously labeled.</span></span> <span data-ttu-id="1fd34-172">一覧からいずれかのポジファイルを選び、viewer で表示します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-172">Select one of the positive files from the list, and it displays in the viewer.</span></span>
3. <span data-ttu-id="1fd34-173">[説明] セクションで、[**新しい** ] を選択し、[**空**を選択し ます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-173">In the Explanation section, select **New** and then **Blank**.</span></span>
4. <span data-ttu-id="1fd34-174">[ **説明を作成する** ] ページで：</span><span class="sxs-lookup"><span data-stu-id="1fd34-174">On the **Create an explanation** page:</span></span></br>
    <span data-ttu-id="1fd34-175">a.</span><span class="sxs-lookup"><span data-stu-id="1fd34-175">a.</span></span> <span data-ttu-id="1fd34-176">**名前** を入力します (たとえば、"暴露ブロック")。</span><span class="sxs-lookup"><span data-stu-id="1fd34-176">Type the **Name** (for example, "Disclosure Block").</span></span></br>
    <span data-ttu-id="1fd34-177">b.</span><span class="sxs-lookup"><span data-stu-id="1fd34-177">b.</span></span> <span data-ttu-id="1fd34-178">[ **種類**]を選びます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-178">Select the **Type**.</span></span> <span data-ttu-id="1fd34-179">この例では、文字列を追加するので、[ **語句のリスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-179">For the sample, select **Phrase list**, since you add a text string.</span></span></br>
    <span data-ttu-id="1fd34-180">c.</span><span class="sxs-lookup"><span data-stu-id="1fd34-180">c.</span></span> <span data-ttu-id="1fd34-181">[ **ここに入力してください**] ボックスに、文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-181">In the **Type here** box, type the string.</span></span> <span data-ttu-id="1fd34-182">このサンプルには、"追加情報開示の要求" を追加します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-182">For the sample, add "Request for additional disclosure".</span></span> <span data-ttu-id="1fd34-183">文字列に大文字と小文字を区別する必要がある場合は、**大文字と小文字の区別**を選択することができます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-183">You can select **Case sensitive** if the string needs to be case sensitive.</span></span></br>
    <span data-ttu-id="1fd34-184">d. </span><span class="sxs-lookup"><span data-stu-id="1fd34-184">d.</span></span> <span data-ttu-id="1fd34-185">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1fd34-185">Click **Save**.</span></span>

    ![説明を作成する](../media/content-understanding/explanation.png) 
    
 
5. <span data-ttu-id="1fd34-187">モデルでは、作成した説明が、ポジティブまたはネガティブの例として、残りのラベル付きファイルの例を正しく識別するのに適しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-187">The model now checks to see if the explanation you created was good enough to identify the remaining labeled example files correctly, as positive and negative examples.</span></span> <span data-ttu-id="1fd34-188">[トレーニング済みファイル] セクションで、トレーニングが完了した後で結果を確認するため、[ **評価** ] 列をチェックします。</span><span class="sxs-lookup"><span data-stu-id="1fd34-188">In the Trained Files section, check the **Evaluation** column after the training has completed to see the results.</span></span> <span data-ttu-id="1fd34-189">ファイルには、ユーザーがポジティブまたはネガティブとラベルをつけたものと一致させるために作成した説明が適切であった場合、**一致**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-189">The files show a value of **Match**, if the explanations you created was enough to match what you labeled as positive or negative.</span></span>

    ![Match 値](../media/content-understanding/match.png) 

<span data-ttu-id="1fd34-191">ラベルが付けられたファイルの**不一致** を受信した場合は、モデルがドキュメントの種類を識別できるように、追加の説明を作成し提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1fd34-191">If you receive a **Mismatch** on the labeled files, you may need to create an additional explanation to provide the model more information to identify the document type.</span></span> <span data-ttu-id="1fd34-192">この場合は、ファイルをクリックして、不一致が発生した理由に関する詳細情報を入手します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-192">If this happens, click on the file to get more information about why the mismatch occurred.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="1fd34-193">モデルをテストする</span><span class="sxs-lookup"><span data-stu-id="1fd34-193">Test your model</span></span>

<span data-ttu-id="1fd34-194">ラベル付きのサンプルファイルに対して一致が返された場合は、このモデルがまだ扱っていないその他のラベルのないサンプルファイルで、モデルをテストできます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-194">If you received a match on your labeled sample files, you can now  test your model on your remaining unlabeled example files that the model has not seen before.</span></span>  <span data-ttu-id="1fd34-195">この手順は省略できます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-195">This step is optional.</span></span>

1. <span data-ttu-id="1fd34-196">[モデルのホーム] ページで、[ **テスト** ] タブを選択します。 ラベルなしのサンプルファイル上でモデルが実行されます。</span><span class="sxs-lookup"><span data-stu-id="1fd34-196">From the model home page, select the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="1fd34-197">[ **テストファイル** ] の一覧では、サンプルファイルが表示され、モデルがポジティブかネガティブであるかを予測します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-197">In the **Test files** list, your example files display and shows if the model predicted them to be positive or negative.</span></span> <span data-ttu-id="1fd34-198">この情報を使用して、ドキュメントを特定するときの分類子の有効性を判断します。</span><span class="sxs-lookup"><span data-stu-id="1fd34-198">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![ラベルなしファイルのテスト](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a><span data-ttu-id="1fd34-200">関連項目</span><span class="sxs-lookup"><span data-stu-id="1fd34-200">See Also</span></span>
[<span data-ttu-id="1fd34-201">エクストラクターを作成する</span><span class="sxs-lookup"><span data-stu-id="1fd34-201">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="1fd34-202">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="1fd34-202">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="1fd34-203">フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="1fd34-203">Create a form processing model</span></span>](create-a-form-processing-model.md)

[<span data-ttu-id="1fd34-204">モデルを適用する</span><span class="sxs-lookup"><span data-stu-id="1fd34-204">Apply a model</span></span>](apply-a-model.md) 
