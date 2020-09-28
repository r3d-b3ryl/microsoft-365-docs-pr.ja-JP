---
title: フォーム処理モデルを作成する
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
description: Microsoft SharePoint の同期 Tex でフォーム処理モデルを作成します。
ms.openlocfilehash: f61dbad837173c412daefb7285c4abff10a01817
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295480"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="a6749-103">Microsoft SharePoint の同期 Tex でフォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="a6749-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="a6749-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="a6749-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="a6749-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6749-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

<span data-ttu-id="a6749-106">[AI ビルダー](https://docs.microsoft.com/ai-builder/overview)を使用する-Microsoft PowerApps のフィーチャー-プロジェクト cortex ユーザーは、SharePoint ドキュメントライブラリから直接[フォーム処理モデル](form-processing-overview.md)を作成できます。</span><span class="sxs-lookup"><span data-stu-id="a6749-106">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - Project Cortex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="a6749-107">フォーム処理モデルを作成するには、以下の作業を行います。</span><span class="sxs-lookup"><span data-stu-id="a6749-107">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="a6749-108">手順 1: コンテンツタイプを作成するための from 処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="a6749-108">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="a6749-109">手順 2: サンプルファイルを追加して分析する</span><span class="sxs-lookup"><span data-stu-id="a6749-109">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="a6749-110">手順 3: フォームフィールドを選択する</span><span class="sxs-lookup"><span data-stu-id="a6749-110">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="a6749-111">手順 4: モデルをトレーニングおよびテストする</span><span class="sxs-lookup"><span data-stu-id="a6749-111">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="a6749-112">手順 5: モデルを発行する</span><span class="sxs-lookup"><span data-stu-id="a6749-112">Step 5: Publish your model</span></span>
 - <span data-ttu-id="a6749-113">手順 6: モデルを使用する</span><span class="sxs-lookup"><span data-stu-id="a6749-113">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="a6749-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="a6749-114">Requirements</span></span>

<span data-ttu-id="a6749-115">フォーム処理モデルは、それが有効になっている SharePoint ドキュメントライブラリでのみ作成できます。</span><span class="sxs-lookup"><span data-stu-id="a6749-115">You can only create a form processing model in SharePoint document libraries for which it is enabled.</span></span> <span data-ttu-id="a6749-116">フォーム処理が有効になっている場合は、ドキュメントライブラリの [**自動化**] メニューの [**フォーム処理モデルを作成**する] という**AI ビルダー**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6749-116">If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="a6749-117">ドキュメントライブラリで処理を有効にする必要がある場合は、SharePoint 管理者に連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6749-117">If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![AI ビルダーモデルを作成する](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="a6749-119">手順 1: フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="a6749-119">Step 1: Create a form Processing model</span></span>

<span data-ttu-id="a6749-120">フォーム処理モデルを作成する最初の手順は、その名前を作成して、新しいコンテンツタイプを定義し、それに対応する新しいドキュメントライブラリビューを作成することです。</span><span class="sxs-lookup"><span data-stu-id="a6749-120">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="a6749-121">ドキュメントライブラリで、[ **自動化** ] メニューの [ **AI ビルダー**] を選択し、[ **フォーム処理モデルの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6749-121">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![モデルを作成する](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="a6749-123">[ **新しいフォーム処理モデル** ] ウィンドウの [  **名前** ] フィールドに、モデルの名前を入力します (例: *発注書*)。</span><span class="sxs-lookup"><span data-stu-id="a6749-123">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![新しいフォーム処理モデル](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="a6749-125">フォーム処理モデルを作成する場合は、新しい SharePoint コンテンツタイプを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6749-125">When you create a form processing model, you create a new SharePoint content type.</span></span> <span data-ttu-id="a6749-126">SharePoint コンテンツタイプは、共通の特性を持つドキュメントのカテゴリを表し、その特定のコンテンツの列またはメタデータプロパティのコレクションを共有します。</span><span class="sxs-lookup"><span data-stu-id="a6749-126">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="a6749-127">SharePoint コンテンツタイプは、 [コンテンツタイプギャラリー]()を使用して管理されます。</span><span class="sxs-lookup"><span data-stu-id="a6749-127">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="a6749-128">このモデルを SharePoint コンテンツタイプギャラリーの既存のコンテンツタイプにマッピングして、そのスキーマを使用する場合は、[ **詳細設定** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6749-128">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="a6749-129">モデルでは、抽出したデータ用のドキュメントライブラリに新しいビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="a6749-129">Your model creates a new view in your document library for your extracted data.</span></span> <span data-ttu-id="a6749-130">これを既定のビューにしない場合は、[ **既定としてビューを設定**する] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="a6749-130">If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="a6749-131">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6749-131">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="a6749-132">手順 2: ドキュメントを追加して分析する</span><span class="sxs-lookup"><span data-stu-id="a6749-132">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="a6749-133">新しいフォーム処理モデルを作成すると、ブラウザーに新しい PowerApps AI ビルダーフォーム処理モデルページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6749-133">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="a6749-134">このページでは、サンプルドキュメントを追加して分析することができます。</span><span class="sxs-lookup"><span data-stu-id="a6749-134">On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="a6749-135">使用するファイルの例については、「 [フォーム処理モデルの入力文書の要件」と「最適化のヒント](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6749-135">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI ビルダー](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="a6749-137">[ **ドキュメントの追加** ] を選択して、分析するサンプルドキュメントの追加を開始し、抽出できる名前付きの値のペアを決定します。</span><span class="sxs-lookup"><span data-stu-id="a6749-137">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted.</span></span> <span data-ttu-id="a6749-138">その後、[ローカルストレージ、 **SharePoint**、または**Azure Blob ストレージ\*\*\*\*からのアップロード**] を選択できます。</span><span class="sxs-lookup"><span data-stu-id="a6749-138">You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="a6749-139">トレーニングには、少なくとも5つのファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6749-139">You need to use at least five files for training.</span></span>

2. <span data-ttu-id="a6749-140">ファイルを追加した後、[ **分析** ] を選択して、よく使用される情報がすべてファイルであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="a6749-140">After adding files, select **Analyze** to check for any information common is all files.</span></span> <span data-ttu-id="a6749-141">この処理が完了するまで数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a6749-141">This may take several minutes to complete.</span></span></br> 
 
    ![ファイルを分析する](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="a6749-143">ファイルを分析した後、 **[保存するフォームフィールドを選択** してください] ページでファイルを選択して、検出されたフィールドを表示します。</span><span class="sxs-lookup"><span data-stu-id="a6749-143">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![フォームフィールドの選択](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="a6749-145">手順 3: フォームフィールドを選択する</span><span class="sxs-lookup"><span data-stu-id="a6749-145">Step 3: Select your form fields</span></span>

<span data-ttu-id="a6749-146">フィールドのドキュメントを分析した後、検索されたフィールドを確認し、保存するフィールドを識別できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a6749-146">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save.</span></span> <span data-ttu-id="a6749-147">保存されたフィールドは、モデルのドキュメントライブラリビューで列として表示され、各ドキュメントから抽出された値を表示します。</span><span class="sxs-lookup"><span data-stu-id="a6749-147">Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="a6749-148">次のページには、サンプルファイルの1つが表示され、システムによって自動的に検出されたすべての共通フィールドが強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6749-148">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![[フィールドの選択] ページ](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="a6749-150">保存するフィールドを選択して、選択内容を確認するチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a6749-150">Select the fields that you want to save and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="a6749-151">たとえば、[購入注文] モデルでは、 *日付*、 *PO*、および *集計* フィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="a6749-151">For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="a6749-152">また、選択した場合は、フィールドの名前を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="a6749-152">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![PO の選択#](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="a6749-154">分析でフィールドが検出されなかった場合でも、追加することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a6749-154">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="a6749-155">抽出する情報を選択し、[名前] ボックスに目的の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a6749-155">Highlight the information you want to extract, and in the name box type in the name you want.</span></span> <span data-ttu-id="a6749-156">次に、チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a6749-156">Then select the check box.</span></span> <span data-ttu-id="a6749-157">その他のサンプルファイルの検出されていないフィールドを確認する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6749-157">Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="a6749-158">保存するフィールドを選択したら、[ **フィールドの確認** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6749-158">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![フィールドを選択した後にフィールドを確認する](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="a6749-160">[ **保存するフォームフィールドを選択** してください] ページで、選択したフィールドの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6749-160">On the **Select the form fields you want to save** page, it shows the number of fields you have selected.</span></span> <span data-ttu-id="a6749-161">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6749-161">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="a6749-162">手順 4: モデルをトレーニングおよびテストする</span><span class="sxs-lookup"><span data-stu-id="a6749-162">Step 4: Train and test your model</span></span>

<span data-ttu-id="a6749-163">保存するフィールドを選択すると、[ **モデルの概要** ] ページでモデルのトレーニングとテストを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a6749-163">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="a6749-164">[ **モデルの概要** ] ページの [ **選択したフィールド** ] セクションに、保存したフィールドが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6749-164">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="a6749-165">サンプルファイルのトレーニングを開始するには、[ **Train** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6749-165">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="a6749-166">この処理が完了するまで数分かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6749-166">Note that this may take a few minutes to complete.</span></span></br>

     ![フィールドを選択する列車](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="a6749-168">トレーニングが完了したことを示す通知が表示されたら、[ **詳細ページに移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6749-168">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="a6749-169">[ **モデルの詳細** ] ページで、[ **クイックテスト**] を選択してモデルの動作をテストできます。</span><span class="sxs-lookup"><span data-stu-id="a6749-169">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="a6749-170">これにより、ファイルをページにドラッグアンドドロップして、フィールドが検出されたかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a6749-170">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![確認フィールド](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="a6749-172">トレーニングが完了したことを示す通知が表示されたら、[ **詳細ページに移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6749-172">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="a6749-173">[ **モデルの詳細** ] ページで、[ **クイックテスト**] を選択してモデルの動作をテストします。</span><span class="sxs-lookup"><span data-stu-id="a6749-173">On the **Model details** page, choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="a6749-174">これにより、ファイルをページにドラッグアンドドロップして、フィールドが検出されたかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="a6749-174">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="a6749-175">手順 5: モデルを発行する</span><span class="sxs-lookup"><span data-stu-id="a6749-175">Step 5: Publish your model</span></span>

1. <span data-ttu-id="a6749-176">モデルの結果に問題がなければ、[ **発行** ] を選択して使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a6749-176">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="a6749-177">モデルが公開されたら、[ **Use model**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a6749-177">After the model is published, select **Use model**.</span></span> <span data-ttu-id="a6749-178">これにより、SharePoint ドキュメントライブラリで実行してモデルで識別されたフィールドを抽出し、[ **フローの作成**] を選択することができる powerautomate フローが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a6749-178">This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="a6749-179">完了すると、 **フローが正常に作成され**たことをメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a6749-179">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="a6749-180">手順 6: モデルを使用する</span><span class="sxs-lookup"><span data-stu-id="a6749-180">Step 6: Use your model</span></span>

<span data-ttu-id="a6749-181">モデルを発行して、そのモデルの PowerAutomate フローを作成した後、モデルを SharePoint ドキュメントライブラリで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a6749-181">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="a6749-182">モデルを公開した後、[ **SharePoint に移動** ] を選択してドキュメントライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="a6749-182">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="a6749-183">[ドキュメントライブラリモデル] ビューで、選択したフィールドが列として表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6749-183">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![ドキュメントライブラリモデルの適用](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="a6749-185">**ドキュメント**の横の情報リンクは、フォーム処理モデルがこのドキュメントライブラリに適用されていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a6749-185">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![[情報] ボタン](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="a6749-187">ファイルをドキュメントライブラリにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="a6749-187">Upload files to your document library.</span></span> <span data-ttu-id="a6749-188">モデルがコンテンツタイプとして識別するすべてのファイルは、ビュー内のファイルを一覧表示して、列に抽出されたデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="a6749-188">Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![完了](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="a6749-190">関連項目</span><span class="sxs-lookup"><span data-stu-id="a6749-190">See Also</span></span>
  
[<span data-ttu-id="a6749-191">電力の自動化に関するドキュメント</span><span class="sxs-lookup"><span data-stu-id="a6749-191">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)</br>
[<span data-ttu-id="a6749-192">トレーニング: AI ビルダーを使用してビジネスパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="a6749-192">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
