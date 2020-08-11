---
title: フォーム処理モデルを作成する (プレビュー)
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
description: プロジェクト Cortex でフォーム処理モデルを作成します。
ms.openlocfilehash: 733baf24d8a484571ba9882fdda2633dc2ce0504
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612776"
---
# <a name="create-a-form-processing-model-preview"></a><span data-ttu-id="8326f-103">フォーム処理モデルを作成する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="8326f-103">Create a form processing model (Preview)</span></span>

> [!Note] 
> <span data-ttu-id="8326f-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="8326f-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="8326f-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8326f-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="8326f-106">[AI ビルダー](https://docs.microsoft.com/ai-builder/overview)を使用する-Microsoft PowerApps のフィーチャー-プロジェクト cortex ユーザーは、SharePoint ドキュメントライブラリから直接[フォーム処理モデル](form-processing-overview.md)を作成できます。</span><span class="sxs-lookup"><span data-stu-id="8326f-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="8326f-107">フォーム処理モデルを作成するには、以下の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="8326f-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="8326f-108">手順 1: コンテンツタイプを作成するための from 処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="8326f-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="8326f-109">手順 2: サンプルファイルを追加して分析する</span><span class="sxs-lookup"><span data-stu-id="8326f-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="8326f-110">手順 3: フォームフィールドを選択する</span><span class="sxs-lookup"><span data-stu-id="8326f-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="8326f-111">手順 4: モデルをトレーニングおよびテストする</span><span class="sxs-lookup"><span data-stu-id="8326f-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="8326f-112">手順 5: モデルを発行する</span><span class="sxs-lookup"><span data-stu-id="8326f-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="8326f-113">手順 6: モデルを使用する</span><span class="sxs-lookup"><span data-stu-id="8326f-113">Step 6: Use your model</span></span>


## <a name="requirements"></a><span data-ttu-id="8326f-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="8326f-114">Requirements</span></span>

<span data-ttu-id="8326f-115">フォーム処理モデルは、それが有効になっている SharePoint ドキュメントライブラリでのみ作成できます。</span><span class="sxs-lookup"><span data-stu-id="8326f-115">You can only create a form processing model in SharePoint document libraries in which it is enabled.</span></span> <span data-ttu-id="8326f-116">フォーム処理が有効になっている場合は、ドキュメントライブラリの [**自動化**] メニューにある [**フォーム処理モデルを作成**する] という**AI ビルダー**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8326f-116">If form processing is enabled, you will be able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="8326f-117">ドキュメントライブラリで処理が有効になっている必要がある場合は、管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="8326f-117">If you need from processing enabled on your document library, contact your admin.</span></span>

 ![AI ビルダーモデルを作成する](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="8326f-119">手順 1: フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="8326f-119">Step 1: Create a Form Processing model</span></span>

<span data-ttu-id="8326f-120">フォーム処理モデルを作成する最初の手順は、新しいコンテンツタイプを定義して、そのコンテンツタイプに新しいドキュメントライブラリビューを作成するための名前を作成することです。</span><span class="sxs-lookup"><span data-stu-id="8326f-120">The first step in creating a form processing model is to name it to create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="8326f-121">ドキュメントライブラリで、[**自動化**] メニューの [ **AI ビルダー**] を選択し、[**フォーム処理モデルの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8326f-121">In your document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![AI ビルダーモデルを作成する](../media/content-understanding/create-ai-builder-model.png)</br>
2. <span data-ttu-id="8326f-123">[**新しいフォーム処理モデル**] ウィンドウの [**名前**] フィールドに、モデルの名前を入力します (例:*発注書*)。</span><span class="sxs-lookup"><span data-stu-id="8326f-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![新しいフォーム処理モデル](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="8326f-125">フォーム処理モデルを作成するときは、新しい SharePoint コンテンツタイプを作成します。</span><span class="sxs-lookup"><span data-stu-id="8326f-125">When you create a form processing model, you are creating a new SharePoint content type.</span></span> <span data-ttu-id="8326f-126">SharePoint コンテンツタイプは、共通の特性を持つドキュメントのカテゴリを表し、その特定のコンテンツの列またはメタデータプロパティのコレクションを共有します。</span><span class="sxs-lookup"><span data-stu-id="8326f-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="8326f-127">SharePoint コンテンツタイプは、[コンテンツタイプギャラリー]()を使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="8326f-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="8326f-128">このモデルを SharePoint コンテンツタイプギャラリーの既存のコンテンツタイプにマッピングして、そのスキーマを使用する場合は、[**詳細設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8326f-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="8326f-129">モデルによって、抽出されたデータ用のドキュメントライブラリに新しいビューが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8326f-129">Your model will create a new view in your document library for your extracted data.</span></span> <span data-ttu-id="8326f-130">これを既定のビューにしない場合は、[**既定としてビューを設定**する] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="8326f-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>
5. <span data-ttu-id="8326f-131">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8326f-131">Select **Create**.</span></span>


## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="8326f-132">手順 2: ドキュメントを追加して分析する</span><span class="sxs-lookup"><span data-stu-id="8326f-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="8326f-133">新しいフォーム処理モデルを作成すると、ブラウザーに新しい PowerApps AI ビルダーフォーム処理モデルページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8326f-133">After you create your new form processing model, your browser will open a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="8326f-134">このページでは、サンプルドキュメントを追加して分析することができます。</span><span class="sxs-lookup"><span data-stu-id="8326f-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!Note]
> <span data-ttu-id="8326f-135">使用するファイルの例については、「[フォーム処理モデルの入力文書の要件」と「最適化のヒント](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8326f-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI ビルダー](../media/content-understanding/powerapps.png)</br> 
 

1. <span data-ttu-id="8326f-137">[**ドキュメントの追加**] をクリックして、分析するサンプルドキュメントの追加を開始し、抽出できる名前付き値のペアを決定します。</span><span class="sxs-lookup"><span data-stu-id="8326f-137">Click **Add documents** to begin adding example documents that are analyzed to determine what named value pairs can be extracted.</span></span> <span data-ttu-id="8326f-138">[ローカルストレージ、 **SharePoint**、または**Azure Blob ストレージ\*\*\*\*からのアップロード**] のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8326f-138">You can choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="8326f-139">トレーニングには、少なくとも5つのファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8326f-139">You will need to use at least five files for training.</span></span>
2. <span data-ttu-id="8326f-140">ファイルを追加した後、[**分析**] を選択して、一般的な情報がすべてのファイルであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8326f-140">After adding your files, select **Analyze** to check for any information that is common is all files.</span></span> <span data-ttu-id="8326f-141">この処理が完了するまで数分かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8326f-141">Note that this may take several minutes to complete.</span></span></br> 
 
    ![ファイルを分析する](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="8326f-143">分析した後、[保存する**フォームフィールドを選択**してください] ページで、ファイルをクリックして検出されたフィールドを表示します。</span><span class="sxs-lookup"><span data-stu-id="8326f-143">After they have been analyzed, in the **Select the form fields you want to save** page, click the file to see the fields that were detected.</span></span></br>

    ![フォームフィールドの選択](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="8326f-145">手順 3: フォームフィールドを選択する</span><span class="sxs-lookup"><span data-stu-id="8326f-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="8326f-146">フィールドのドキュメントを分析すると、どのフィールドが検索されたか、どのフィールドが保存されるかを確認できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8326f-146">After analyzing your documents for fields, you can now see which fields were found, and which ones you want to save.</span></span> <span data-ttu-id="8326f-147">保存されたフィールドは、モデルのドキュメントライブラリビューで列として表示され、各ドキュメントから抽出された値を表示します。</span><span class="sxs-lookup"><span data-stu-id="8326f-147">Saved fields will display as columns in your model's document library view and will show the values extracted from each document.</span></span>

1. <span data-ttu-id="8326f-148">次のページは、サンプルファイルの1つを表示し、システムによって自動的に検出されたすべての共通フィールドを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="8326f-148">The next page will display one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![フォームフィールドの選択](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="8326f-150">保存するフィールドを選択し、チェックボックスをオンにして選択内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="8326f-150">Select the fields you want to save, and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="8326f-151">たとえば、発注書モデルでは、*日付*、 *PO*、および*集計*フィールドを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="8326f-151">For example, in the Purchase Order model, you can choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="8326f-152">また、選択した場合は、フィールドの名前を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="8326f-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![PO の選択#](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="8326f-154">分析でフィールドが検出されなかった場合でも、追加することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8326f-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="8326f-155">抽出する情報を選択し、[名前] ボックスに目的の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="8326f-155">Highlight the information you want to extract, and in the name box type in the name you want to give it.</span></span> <span data-ttu-id="8326f-156">次に、チェックを選択します。</span><span class="sxs-lookup"><span data-stu-id="8326f-156">Then select the check.</span></span> <span data-ttu-id="8326f-157">このようなファイルの例では、検出されていないフィールドを確認する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8326f-157">Note that you will need to confirm undetected fields in your remaining example files.</span></span>
4. <span data-ttu-id="8326f-158">保存するフィールドを選択したら、[**フィールドの確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8326f-158">Click **Confirm fields** after you have selected the fields you want to save.</span></span> </br>
 
    ![確認フィールド](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="8326f-160">[**保存するフォームフィールドを選択**してください] ページで、選択したフィールドの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8326f-160">On the **Select the form fields you want to save** page, it will show the number of fields you have selected.</span></span> <span data-ttu-id="8326f-161">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8326f-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="8326f-162">手順 4: モデルをトレーニングおよびテストする</span><span class="sxs-lookup"><span data-stu-id="8326f-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="8326f-163">保存するフィールドを選択すると、モデルの**概要**ページが表示され、モデルのトレーニングとテストができるようになります。</span><span class="sxs-lookup"><span data-stu-id="8326f-163">After selecting the fields you want to save, the **Model Summary** page will let you train and test your model.</span></span>

1. <span data-ttu-id="8326f-164">[**モデルの概要**] ページの [**選択したフィールド**] セクションに、保存したフィールドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8326f-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="8326f-165">サンプルファイルのトレーニングを開始するには、[ **Train** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8326f-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="8326f-166">この処理が完了するまで数分かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8326f-166">Note that this may take a few minutes to complete.</span></span></br>
    <span data-ttu-id="8326f-167">![確認フィールド](../media/content-understanding/select-fields-train.png)</span><span class="sxs-lookup"><span data-stu-id="8326f-167">![Confirm fields](../media/content-understanding/select-fields-train.png)</span></span></br> 
2. <span data-ttu-id="8326f-168">トレーニングが完了したことを示す通知が表示されたら、[**詳細ページに移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8326f-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 
3. <span data-ttu-id="8326f-169">[**モデルの詳細**] ページで、[**クイックテスト**] を選択してモデルの動作をテストできます。</span><span class="sxs-lookup"><span data-stu-id="8326f-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="8326f-170">これにより、ファイルをページにドラッグアンドドロップして、フィールドが検出されたかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="8326f-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="8326f-171">手順 5: モデルを発行する</span><span class="sxs-lookup"><span data-stu-id="8326f-171">Step 5: Publish your model</span></span>



1. <span data-ttu-id="8326f-172">モデルの結果に問題がなければ、[**発行**] を選択して使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8326f-172">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>
2. <span data-ttu-id="8326f-173">モデルが公開されたら、[ **Use model**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8326f-173">After the model published, select **Use model**.</span></span> <span data-ttu-id="8326f-174">これにより、SharePoint ドキュメントライブラリで実行され、モデルで識別されたフィールドが抽出される PowerAutomate フローが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8326f-174">This creates a PowerAutomate flow that will run in your SharePoint document library and will extract the fields that have been identified in the model.</span></span> <span data-ttu-id="8326f-175">[**フローの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8326f-175">Select **Create Flow**.</span></span>  
3. <span data-ttu-id="8326f-176">完了すると、**フローが正常に作成され**たことをメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8326f-176">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="8326f-177">手順 6: モデルを使用する</span><span class="sxs-lookup"><span data-stu-id="8326f-177">Step 6: Use your model</span></span>

<span data-ttu-id="8326f-178">モデルを発行して、そのモデルの PowerAutomate フローを作成した後、モデルを SharePoint ドキュメントライブラリで使用できます。</span><span class="sxs-lookup"><span data-stu-id="8326f-178">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="8326f-179">モデルを公開した後、[ **SharePoint に移動**] を選択してドキュメントライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="8326f-179">After publishing your model , select **Go to SharePoint** to go to your document library.</span></span>
2. <span data-ttu-id="8326f-180">[ドキュメントライブラリモデル] ビューで、選択したフィールドが列として表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8326f-180">On your document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![モデルが適用されたドキュメントライブラリ](../media/content-understanding/doc-lib-view.png)</br> 

    <span data-ttu-id="8326f-182">また、[**ドキュメント**] の横にある [情報] リンクは、フォーム処理モデルがこのドキュメントライブラリに適用されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8326f-182">Also notice that the information link next to **Documents** will note that a forms processing model is applied to this document library.</span></span>

    ![れる](../media/content-understanding/info-button.png)</br>  

3. <span data-ttu-id="8326f-184">ファイルをドキュメントライブラリにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="8326f-184">Upload files to your document library.</span></span> <span data-ttu-id="8326f-185">モデルがコンテンツタイプとして識別するすべてのファイルは、ビュー内のファイルを一覧表示し、抽出されたデータを列に表示します。</span><span class="sxs-lookup"><span data-stu-id="8326f-185">Any files that the model identifies as it's content type will list the files in your view, and will display the extracted data in the columns.</span></span></br>

    ![れる](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a><span data-ttu-id="8326f-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="8326f-187">See Also</span></span>
  
[<span data-ttu-id="8326f-188">電力の自動化に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="8326f-188">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="8326f-189">トレーニング: AI ビルダーを使用してビジネスパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="8326f-189">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




