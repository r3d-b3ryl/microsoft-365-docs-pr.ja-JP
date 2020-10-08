---
title: フォーム処理モデルを作成する
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Microsoft SharePoint Syntexでフォーム処理モデルを作成します。
ms.openlocfilehash: 784a3e0a918424e599e87852d2a36b613867f62e
ms.sourcegitcommit: 7e8151ff74cb1cfc0dd59fadcac423c338415d77
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/08/2020
ms.locfileid: "48390187"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="0ec25-103">Microsoft SharePoint Syntexでフォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="0ec25-103">Create a form processing model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>

<span data-ttu-id="0ec25-104">[AI ビルダー](https://docs.microsoft.com/ai-builder/overview)-Microsoft PowerApps の a 機能-SharePoint Syntex のユーザーは、SharePoint ドキュメントライブラリから直接 [フォームプ処理モデル](form-processing-overview.md)を作成できます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-104">Using [AI Builder](https://docs.microsoft.com/ai-builder/overview) - a feature in Microsoft PowerApps - SharePoint Syntex users can create a [form processing model](form-processing-overview.md) directly from a SharePoint document library.</span></span> 

<span data-ttu-id="0ec25-105">フォーム処理モデルを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0ec25-105">Creating a form processing model involves the following:</span></span>
 - <span data-ttu-id="0ec25-106">手順 1: コンテンツタイプを作成するために、フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="0ec25-106">Step 1: Create the from processing model to create the content type</span></span>
 - <span data-ttu-id="0ec25-107">手順 2: サンプルファイルを追加して分析する</span><span class="sxs-lookup"><span data-stu-id="0ec25-107">Step 2: Add and analyze example files</span></span>
 - <span data-ttu-id="0ec25-108">手順 3: フォームフィールドを選択する</span><span class="sxs-lookup"><span data-stu-id="0ec25-108">Step 3: Select your form fields</span></span>
 - <span data-ttu-id="0ec25-109">手順 4: モデルをトレーニングしてテストする</span><span class="sxs-lookup"><span data-stu-id="0ec25-109">Step 4: Train and test your model</span></span>
 - <span data-ttu-id="0ec25-110">手順 5:モデルを発行する</span><span class="sxs-lookup"><span data-stu-id="0ec25-110">Step 5: Publish your model</span></span>
 - <span data-ttu-id="0ec25-111">手順 6: モデルを使う</span><span class="sxs-lookup"><span data-stu-id="0ec25-111">Step 6: Use your model</span></span>

## <a name="requirements"></a><span data-ttu-id="0ec25-112">要件</span><span class="sxs-lookup"><span data-stu-id="0ec25-112">Requirements</span></span>

<span data-ttu-id="0ec25-113">フォームを作成するには、それが有効になっている SharePoint ドキュメントライブラリを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ec25-113">You can only create a form processing model in SharePoint document libraries for which it is enabled.</span></span> <span data-ttu-id="0ec25-114">フォームの処理が有効になっている場合は、ドキュメントライブラリの **自動化** メニューの [**フォームの処理モデルを作成する** "**AI ビルダー**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-114">If form processing is enabled, you are able to see the **AI Builder** **"Create a form processing model'** under the **Automate** menu in your document library.</span></span>  <span data-ttu-id="0ec25-115">ドキュメントライブラリで処理を有効にする必要がある場合は、SharePoint 管理者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="0ec25-115">If you need processing enabled on your document library, you must contact your SharePoint administrator.</span></span>

 ![AI ビルダーモデルを作成する](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a><span data-ttu-id="0ec25-117">手順 1: フォーム処理モデルを作成する</span><span class="sxs-lookup"><span data-stu-id="0ec25-117">Step 1: Create a form Processing model</span></span>

<span data-ttu-id="0ec25-118">フォーム処理モデルを作成するには、最初に、名前を付けて、新しいコンテンツタイプを定義して、それに対応する新しいドキュメントライブラリビューを作成します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-118">The first step in creating a form processing model is to name it and create the define the new content type and create a new document library view for it.</span></span>

1. <span data-ttu-id="0ec25-119">ドキュメントライブラリで、 **オートメーションの** メニューを選択し、 **AI ビルダー**それから、**フォームの処理モデルを作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-119">From the document library, select the **Automate** menu, select **AI Builder**, and then select **Create a Form Processing model**.</span></span>

    ![モデルを作成する](../media/content-understanding/create-ai-builder-model.png)</br>

2. <span data-ttu-id="0ec25-121">[ **新しいフォームの処理モデル** ]  ウィンドウで、[  **名前の** ] フィールドにモデルの名前を入力します (たとえば、 *発注書*)。</span><span class="sxs-lookup"><span data-stu-id="0ec25-121">In the **New form processing model** pane, in the  **Name** field, type a name for your model (for example, *Purchase Orders*).</span></span>

    ![フォーム処理モデルを作成する](../media/content-understanding/new-form-model.png)</br> 

3. <span data-ttu-id="0ec25-123">フォーム処理モデルを作成する場合は、新しい SharePoint コンテンツタイプを作成します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-123">When you create a form processing model, you create a new SharePoint content type.</span></span> <span data-ttu-id="0ec25-124">SharePointコンテンツタイプは、共通の特徴を持つドキュメントのカテゴリを表し、特定のコンテンツの列またはメタデータプロパティのコレクションを共有します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-124">A SharePoint content type represents a category of documents that have common characteristics and share a collection of columns or metadata properties for that particular content.</span></span> <span data-ttu-id="0ec25-125">SharePoint コンテンツタイプは、 [コンテンツタイプギャラリー]()で管理されます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-125">SharePoint Content Types are managed through the [Content types gallery]().</span></span>

    <span data-ttu-id="0ec25-126">このモデルを SharePoint コンテンツタイプギャラリーの既存のエンタープライズコンテンツタイプにマッピングして、そのスキーマを使用するには、[ **詳細設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-126">Select **Advanced settings** if you want to map this model to an existing content type in the SharePoint Content types gallery to use its schema.</span></span> 

4. <span data-ttu-id="0ec25-127">モデルでは、抽出されたデータ用に、ドキュメントライブラリに新しいビューが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-127">Your model creates a new view in your document library for your extracted data.</span></span> <span data-ttu-id="0ec25-128">既定のビューを表示しない場合は、[**既定のとしてビューを設定する**] の選択を解除 ます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-128">If you do not want it to the default view, deselect **Set the view as default**.</span></span>

5. <span data-ttu-id="0ec25-129">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-129">Select **Create**.</span></span>

## <a name="step-2-add-and-analyze-documents"></a><span data-ttu-id="0ec25-130">手順 2: ドキュメントを追加して分析する</span><span class="sxs-lookup"><span data-stu-id="0ec25-130">Step 2: Add and analyze documents</span></span>

<span data-ttu-id="0ec25-131">新しいフォーム処理モデルを作成すると、ブラウザーに新しい PowerApps AI ビルダーフォームプロセスモデルページが開きます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-131">After you create your new form processing model, your browser opens a new PowerApps AI Builder forms processing model page.</span></span> <span data-ttu-id="0ec25-132">このページでは、サンプルドキュメントを追加して分析できます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-132">On this page you can add and analyze your example documents.</span></span> </br>

> [!NOTE]
> <span data-ttu-id="0ec25-133">使用するサンプルファイルを探すには、「 [フォームプロセッシングモデルインプットの要件および最適化のヒント](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ec25-133">When looking for example files to use, see the [form processing model input document requirements and optimization tips](https://docs.microsoft.com/ai-builder/form-processing-model-requirements).</span></span> 

   ![Power Apps AI ビルダー](../media/content-understanding/powerapps.png)</br> 
 
1. <span data-ttu-id="0ec25-135">[**ドキュメントの追加** ] を選択して、名前付き値のペアを判断するために分析するサンプルドキュメントの追加を開始 ます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-135">Select **Add documents** to begin adding example documents analyzed to determine the named value pairs that can be extracted.</span></span> <span data-ttu-id="0ec25-136">その後、[**ローカルストレージからの アップロード**]、**SharePoint**または **Azure Blob ストレージ**のいずれかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-136">You can then choose either **Upload from local storage**, **SharePoint**, or **Azure Blob storage**.</span></span> <span data-ttu-id="0ec25-137">トレーニングには少なくとも5つのファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="0ec25-137">You need to use at least five files for training.</span></span>

2. <span data-ttu-id="0ec25-138">ファイルを追加した後は、[ **分析** ] を選択して、共通の情報があるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-138">After adding files, select **Analyze** to check for any information common is all files.</span></span> <span data-ttu-id="0ec25-139">このアクションは、完了するのに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="0ec25-139">This may take several minutes to complete.</span></span></br> 
 
    ![ファイルを分析する](../media/content-understanding/analyze.png)</br> 

3. <span data-ttu-id="0ec25-141">ファイルの分析が完了したら、[ **保存するフォームフィールドの選択** ページで、検出されたフィールドを表示するファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-141">After the files have been analyzed, in the **Select the form fields you want to save** page select the file to view the detected fields.</span></span></br>

    ![フォームのフィールドを選択する](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a><span data-ttu-id="0ec25-143">手順 3: フォームフィールドを選択する</span><span class="sxs-lookup"><span data-stu-id="0ec25-143">Step 3: Select your form fields</span></span>

<span data-ttu-id="0ec25-144">フィールドのドキュメントの分析が完了すると、見つかったフィールドが表示され、保存するフィールドが特定されます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-144">After analyzing the documents for fields, you can now see the fields that were found, and identify the ones that you want to save.</span></span> <span data-ttu-id="0ec25-145">保存されたフィールドは、モデルのドキュメントライブラリビューに列として表示され、各ドキュメントから抽出された値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-145">Saved fields display as columns in your model's document library view and show the values extracted from each document.</span></span>

1. <span data-ttu-id="0ec25-146">次のページには、サンプルファイルの1つが表示され、システムによって自動的に検出された共通のフィールドがすべて強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-146">The next page displays one of your sample files and will highlight all common fields that were automatically detected by the system.</span></span> </br>

    ![[フィールドの選択] ページ](../media/content-understanding/select-fields-page.png)</br> 

2. <span data-ttu-id="0ec25-148">保存するフィールドを選択し、チェックボックスをオンにして選択を確定します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-148">Select the fields that you want to save and select the checkbox to confirm your selection.</span></span> <span data-ttu-id="0ec25-149">たとえば、発注書モデルでは、*日付*、*PO*、\*合計 \*フィールドを選択します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-149">For example, in the Purchase Order model, choose to select the *Date*, *PO*, and *Total* fields.</span></span>  <span data-ttu-id="0ec25-150">選択した場合、フィールドの名前を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-150">Note that you can also choose to rename a field if you choose.</span></span> </br>

    ![PO#の選択](../media/content-understanding/po.png)</br> 

3. <span data-ttu-id="0ec25-152">分析でフィールドが検出されなかった場合は、追加することができます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-152">If a field was not detected by analysis, you can still choose to add it.</span></span> <span data-ttu-id="0ec25-153">抽出する情報を強調表示し、[名前] ボックスに名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-153">Highlight the information you want to extract, and in the name box type in the name you want.</span></span> <span data-ttu-id="0ec25-154">チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="0ec25-154">Then select the check box.</span></span> <span data-ttu-id="0ec25-155">残りのサンプルファイルでは、検出されないフィールドを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ec25-155">Note that you need to confirm undetected fields in your remaining sample files.</span></span>

4. <span data-ttu-id="0ec25-156">保存するフィールドを選択した後、[ **フィールドの確認** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ec25-156">Click **Confirm fields** after you have selected the fields that you want to save.</span></span> </br>
 
    ![フィールドを選択した後にフィールドを確認する](../media/content-understanding/confirm-fields.png)</br> 
 
5. <span data-ttu-id="0ec25-158">[ **保存するフォームフィールド選択** ページに、選択したフィールド数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-158">On the **Select the form fields you want to save** page, it shows the number of fields you have selected.</span></span> <span data-ttu-id="0ec25-159">[**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-159">Select **Done**.</span></span>

## <a name="step-4-train-and-test-your-model"></a><span data-ttu-id="0ec25-160">手順 4: モデルをトレーニングしてテストする</span><span class="sxs-lookup"><span data-stu-id="0ec25-160">Step 4: Train and test your model</span></span>

<span data-ttu-id="0ec25-161">保存するフィールドを選択した後に、[ **モデルの概要** ] ページが表示され、モデルをトレーニングしてテストするよう促します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-161">After selecting the fields you want to save, the **Model Summary** page lets you train and test your model.</span></span>

1. <span data-ttu-id="0ec25-162">**モデルの概要** ページでは、保存したフィールドが、[**選択されたフィールド**] セクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-162">On the **Model Summary** page, the saved fields will show in the **Selected fields** section.</span></span> <span data-ttu-id="0ec25-163">[**トレーニング** ] を選択して、サンプルファイル上でトレーニングを開始します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-163">Select **Train** to begin training on your example files.</span></span> <span data-ttu-id="0ec25-164">これには数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0ec25-164">Note that this may take a few minutes to complete.</span></span></br>

     ![フィールドの選択トレーニング](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="0ec25-166">トレーニングが完了したことを示す通知が表示されたら、[ **詳細ページに移動します**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-166">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="0ec25-167">[**モデルの詳細**] ページで、[**クイックテスト**] を 選択して、モデルの動作の速さを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-167">On the **Model details** page, you can choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="0ec25-168">これにより、ファイルをページにドラッグアンドドロップして、フィールドが検出されているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-168">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

    ![フィールドの確認](../media/content-understanding/select-fields-train.png)</br> 

2. <span data-ttu-id="0ec25-170">トレーニングが完了したことを示す通知が表示されたら、[ **詳細ページに移動します**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-170">When you see the notification that training has completed, select **Go to details page**.</span></span> 

3. <span data-ttu-id="0ec25-171">[**モデルの詳細**] ページで、[**クイックテスト**] を 選択して、モデルの動作の速さを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-171">On the **Model details** page, choose to test how your model works by selecting **Quick test**.</span></span> <span data-ttu-id="0ec25-172">これにより、ファイルをページにドラッグアンドドロップして、フィールドが検出されているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-172">This lets you drag and drop files to the page and see if the fields are detected.</span></span>

## <a name="step-5-publish-your-model"></a><span data-ttu-id="0ec25-173">手順 5:モデルを発行する</span><span class="sxs-lookup"><span data-stu-id="0ec25-173">Step 5: Publish your model</span></span>

1. <span data-ttu-id="0ec25-174">モデルの結果に問題がなければ、[ **発行**] を選択して、使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0ec25-174">If you are satisfied with the results of your model, select **Publish** to make it available for use.</span></span>

2. <span data-ttu-id="0ec25-175">モデルが発行されたら、[**モデルを使用**] を選択 します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-175">After the model is published, select **Use model**.</span></span> <span data-ttu-id="0ec25-176">これにより、SharePoint ドキュメントライブラリで実行できる PowerAutomate フローが作成され、モデルで識別されたフィールドが抽出されます。次に、[ **フローを作成**] を選択 します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-176">This creates a PowerAutomate flow that can run in your SharePoint document library and extracts the fields that have been identified in the model, then select **Create Flow**.</span></span>
  
3. <span data-ttu-id="0ec25-177">完了すると、**フローが正常に作成された** メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-177">When completed, you will see the message **Your flow has been successfully created**.</span></span>
 
## <a name="step-6-use-your-model"></a><span data-ttu-id="0ec25-178">手順 6: モデルを使う</span><span class="sxs-lookup"><span data-stu-id="0ec25-178">Step 6: Use your model</span></span>

<span data-ttu-id="0ec25-179">モデルを公開して、PowerAutomate フローを作成したら、SharePoint ドキュメントライブラリでモデルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-179">After publishing your model and creating it's PowerAutomate flow, you can use your model in your SharePoint document library.</span></span>

1. <span data-ttu-id="0ec25-180">モデルを発行した後は、[**SharePointへ行く**] を選択して、ドキュメントライブラリに移動します。</span><span class="sxs-lookup"><span data-stu-id="0ec25-180">After publishing your model, select **Go to SharePoint** to go to your document library.</span></span>

2. <span data-ttu-id="0ec25-181">[ドキュメントライブラリモデル] ビューで、選択したフィールドが列として表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="0ec25-181">In the document library model view, notice that the fields you selected now display as columns.</span></span></br>

    ![適用されたドキュメントライブラリモデル](../media/content-understanding/doc-lib-view.png)</br> 

3. <span data-ttu-id="0ec25-183">\*\* ドキュメント\*\*の横にある [情報] リンクは、フォームプロセッシングモデルがこのドキュメントライブラリに適用されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="0ec25-183">Notice that the information link next to **Documents** notes that a forms processing model is applied to this document library.</span></span>

    ![[情報] ボタン](../media/content-understanding/info-button.png)</br>  

4. <span data-ttu-id="0ec25-185">ファイルをドキュメント ライブラリにアップロードする</span><span class="sxs-lookup"><span data-stu-id="0ec25-185">Upload files to your document library.</span></span> <span data-ttu-id="0ec25-186">モデルがコンテンツタイプとして識別するファイルには、ビュー内のファイルが一覧表示され、列に抽出されたデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ec25-186">Any files that the model identifies as it's content type lists the files in your view and displays the extracted data in the columns.</span></span></br>

    ![完了](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a><span data-ttu-id="0ec25-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ec25-188">See Also</span></span>
  
[<span data-ttu-id="0ec25-189">Power 自動化 ドキュメント</span><span class="sxs-lookup"><span data-stu-id="0ec25-189">Power Automate documentation</span></span>](https://docs.microsoft.com/power-automate/)

[<span data-ttu-id="0ec25-190">トレーニング: AI ビルダーを使用してビジネスの実績を高める</span><span class="sxs-lookup"><span data-stu-id="0ec25-190">Training: Improve business performance with AI Builder</span></span>](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
