---
title: モデルに保持ラベルを適用する
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: この記事では、保持ラベルを SharePoint Syntex のモデルに適用する方法について説明します
ms.openlocfilehash: 48c0b983316cfe29019d09cb20546fa4b325b3b0
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242773"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a><span data-ttu-id="5826a-103">SharePoint Syntex のモデルに保持ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="5826a-103">Apply a retention label to a model in SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


<span data-ttu-id="5826a-104">Microsoft SharePoint Syntex のモデルに[保持ラベル](https://docs.microsoft.com/microsoft-365/compliance/retention)を簡単に適用できます。</span><span class="sxs-lookup"><span data-stu-id="5826a-104">You can easily apply a [retention label](https://docs.microsoft.com/microsoft-365/compliance/retention) to a model in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="5826a-105">これは、ドキュメント理解モデルとフォーム処理モデルの両方で実行できます。</span><span class="sxs-lookup"><span data-stu-id="5826a-105">You can do this for both document understanding and form processing models.</span></span>

<span data-ttu-id="5826a-106">保持ラベルを使用すると、モデルが識別するドキュメントに保持設定を適用できます。</span><span class="sxs-lookup"><span data-stu-id="5826a-106">Retention labels let you apply retention settings to the documents that your models identify.</span></span>  <span data-ttu-id="5826a-107">たとえば、モデルで、ドキュメント ライブラリにアップロードされた *保険通知* ドキュメントを識別するだけでなく、*ビジネス* 保持タグを適用して、これらのドキュメントを指定された期間 ( たとえば、次の5か月) ドキュメント ライブラリから削除できないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5826a-107">For example, you want your model to not only identify any *Insurance notice* documents that are uploaded to your document library, but to also apply a *Business* retention tag to them so that these documents cannot be deleted from the document library for the specified time period (the next five months, for example).</span></span>

<span data-ttu-id="5826a-108">モデルのホーム ページのモデル設定を使用して、既存の保持ラベルをモデルに適用できます。</span><span class="sxs-lookup"><span data-stu-id="5826a-108">You can apply a pre-existing retention label to your model through your model settings on your model's home page.</span></span> 

> [!Important]
> <span data-ttu-id="5826a-109">保持ラベルをドキュメント理解モデルに適用できるようにするには、保持ラベルを[作成して Microsoft 365 コンプライアンス センターで公開する](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)必要があります。</span><span class="sxs-lookup"><span data-stu-id="5826a-109">For retention labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a><span data-ttu-id="5826a-110">保持ラベルをドキュメント理解モデルに追加する</span><span class="sxs-lookup"><span data-stu-id="5826a-110">To add a retention label to a document understanding model</span></span>

1. <span data-ttu-id="5826a-111">モデルのホーム ページから、[**モデルの設定**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="5826a-111">From the model home page, select **Model settings**.</span></span></br>
2. <span data-ttu-id="5826a-112">[**モデルの設定**] の [**セキュリティとコンプライアンス**] セクションで、[**保持ラベル**] メニューを選択して、モデルに適用できる保持ラベルのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="5826a-112">In **Model settings**, in the **Security and compliance** section, select the **Retention label** menu to see a list of retention labels that are available for your to apply to the model.</span></span></br>
 <span data-ttu-id="5826a-113">![保持ラベル メニュー](../media/content-understanding/retention-labels-menu.png)</span><span class="sxs-lookup"><span data-stu-id="5826a-113">![Retention label menu](../media/content-understanding/retention-labels-menu.png)</span></span></br> 
3. <span data-ttu-id="5826a-114">モデルに適用する保持ラベルを選択し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5826a-114">Select the retention label you want to apply to the model, and then select **Save**.</span></span></br>

<span data-ttu-id="5826a-115">モデルに保持ラベルを適用した後、次のものに適用できます。</span><span class="sxs-lookup"><span data-stu-id="5826a-115">After applying the retention label to your model, you are able to apply it to a:</span></span>
- <span data-ttu-id="5826a-116">新しいドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="5826a-116">New document library</span></span>
- <span data-ttu-id="5826a-117">モデルがすでに適用されているドキュメント ライブラリ</span><span class="sxs-lookup"><span data-stu-id="5826a-117">Document library to which the model is already applied</span></span>
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="5826a-118">モデルがすでに適用されているドキュメント ライブラリに保持ラベルを適用します</span><span class="sxs-lookup"><span data-stu-id="5826a-118">Apply the retention label to a document library to which the model is already applied</span></span>

<span data-ttu-id="5826a-119">ドキュメント理解モデルがすでにドキュメント ライブラリに適用されている場合は、次の手順を実行して、保持ラベルの更新を同期し、ドキュメント ライブラリに適用できます。</span><span class="sxs-lookup"><span data-stu-id="5826a-119">If your document understanding model has already been applied to a document library, you can do the following to sync your retention label update to apply it to the document library:</span></span></br>

1. <span data-ttu-id="5826a-120">モデルホームページの [**このモデルのあるライブラリ**] セクションで、保持ラベルの更新を適用するドキュメントライブラリを選択します。</span><span class="sxs-lookup"><span data-stu-id="5826a-120">On your model home page, in the **Libraries with this model** section, select the document library to which you want to apply the retention label update.</span></span> </br> 
2. <span data-ttu-id="5826a-121">[**同期**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5826a-121">Select **Sync**.</span></span> </br>
 <span data-ttu-id="5826a-122">![同期モデル](../media/content-understanding/sync-model.png)</span><span class="sxs-lookup"><span data-stu-id="5826a-122">![Sync model](../media/content-understanding/sync-model.png)</span></span></br> 


<span data-ttu-id="5826a-123">更新を適用してモデルに同期した後、次の手順を実行して、更新が適用されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="5826a-123">After applying the update and syncing it to your model, you can confirm that it has been applied by doing the following:</span></span>

1. <span data-ttu-id="5826a-124">コンテンツ センターの [**このモデルのあるライブラリ**] セクションで、更新したモデルが適用されたライブラリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5826a-124">In the content center, in the **Libraries with this model** section, click on the library to which your updated model was applied.</span></span> </br>
2. <span data-ttu-id="5826a-125">ドキュメント ライブラリ ビューで、情報アイコンを選択してモデルのプロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="5826a-125">In your document library view, select the information icon to check the model properties.</span></span></br>  
3. <span data-ttu-id="5826a-126">[**アクティブモデル**] リストで、更新したモデルを選択します。</span><span class="sxs-lookup"><span data-stu-id="5826a-126">In the **Active models** list, select your updated model.</span></span></br>
4. <span data-ttu-id="5826a-127">[**保持ラベル**] セクションに、適用された保持ラベルの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5826a-127">In the **Retention label** section you will see the name of the applied retention label.</span></span></br>


<span data-ttu-id="5826a-128">ドキュメント ライブラリのモデルの表示ページに、新しい **保持ラベル** 列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5826a-128">On your model's view page in your document library, a new **Retention label** column will display.</span></span>  <span data-ttu-id="5826a-129">モデルがそのコンテンツ タイプに属するものとして識別したファイルを分類し、それらをライブラリ ビューに一覧表示すると、[保持ラベル]列には、モデルを通じてモデルに適用された保持ラベルの名前も表示されます。</span><span class="sxs-lookup"><span data-stu-id="5826a-129">As your model classifies files it identifies as belonging to it's content type and lists them in the library view, the Retention label column will also display the name of the retention label that has been applied to it through the model.</span></span>


<span data-ttu-id="5826a-130">たとえば、モデルが識別するすべての *保険通知* ドキュメントには、*ビジネス* 保持ラベルも適用され、ドキュメント ライブラリから5か月間削除されないようにします。</span><span class="sxs-lookup"><span data-stu-id="5826a-130">For example, all *Insurance notice* documents that your model identifies will also have the *Business* retention label applied to them, preventing them from being deleted from the document library for five months.</span></span> <span data-ttu-id="5826a-131">ドキュメント ライブラリからファイルを削除しようとすると、保持ラベルが適用されているため許可されていないというエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5826a-131">If an attempt is made to delete the file from the document library, an error will display saying it is not allowed because of the applied retention label.</span></span>

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a><span data-ttu-id="5826a-132">保持ラベルをフォーム処理モデルに追加するには</span><span class="sxs-lookup"><span data-stu-id="5826a-132">To add a retention label to a form processing model</span></span>

> [!Important]
> <span data-ttu-id="5826a-133">保持ラベルをフォーム処理モデルに適用できるようにするには、保持ラベルを[作成して Microsoft 365 コンプライアンス センターで公開する](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels)必要があります。</span><span class="sxs-lookup"><span data-stu-id="5826a-133">For retention labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).</span></span>

<span data-ttu-id="5826a-134">モデルの作成時にフォーム処理モデルに保持ラベルを適用するか、既存のモデルに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="5826a-134">You can either apply a retention label to a form processing model when you are creating a model, or apply it to an existing model.</span></span>

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a><span data-ttu-id="5826a-135">フォーム処理モデルを作成するときに保持ラベルを追加するには</span><span class="sxs-lookup"><span data-stu-id="5826a-135">To add a retention label when you create a form processing model</span></span>

1. <span data-ttu-id="5826a-136">[新しいフォーム処理モデルを作成する](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-form-processing-model)場合は、<b>[詳細設定]</b> を選択します。</span><span class="sxs-lookup"><span data-stu-id="5826a-136">When you are [creating a new form processing model](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-form-processing-model), select <b>Advanced settings.</b></span></span>
2. <span data-ttu-id="5826a-137"><b>[詳細設定]</b> の <b>[保持ラベル]</b> セクションで、メニューを選択してから、モデルに適用する保持ラベルを選択します。</b></span><span class="sxs-lookup"><span data-stu-id="5826a-137">In <b>Advanced settings</b>, in the <b>Retention label</b> section, select the menu and then select the retention label you want to apply to the model.</b></span></span>

 
     ![新しいフォーム処理モデルに追加する](../media/content-understanding/retention-label-forms.png)</br>

3.  <span data-ttu-id="5826a-139">残りのモデル設定が完了したら、<b>[作成]</b> を選択してモデルを作成します。</span><span class="sxs-lookup"><span data-stu-id="5826a-139">After you've completed your remaining model settings, select <b>Create</b> to build your model.</span></span>

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a><span data-ttu-id="5826a-140">保持ラベルを既存のフォーム処理モデルに追加するには</span><span class="sxs-lookup"><span data-stu-id="5826a-140">To add a retention label to an existing form processing model</span></span>

<span data-ttu-id="5826a-141">さまざまな方法で、保持ラベルを既存のフォーム処理モデルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="5826a-141">You can add a retention label to an existing form processing model in different ways:</span></span>
- <span data-ttu-id="5826a-142">ドキュメント ライブラリの [自動化] メニューから</span><span class="sxs-lookup"><span data-stu-id="5826a-142">Through the Automate menu in the document library</span></span>
- <span data-ttu-id="5826a-143">ドキュメント ライブラリの [アクティブなモデル] の設定から</span><span class="sxs-lookup"><span data-stu-id="5826a-143">Through the Active model settings in the document library</span></span> 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a><span data-ttu-id="5826a-144">[自動化] メニューを使用して、既存のフォーム処理モデルに保持ラベルを追加するには</span><span class="sxs-lookup"><span data-stu-id="5826a-144">To add a retention label to an existing form processing model through the Automate menu</span></span>

<span data-ttu-id="5826a-145">モデルが適用されているドキュメント ライブラリの [自動化] メニューから、所有している既存のフォーム処理モデルに保持ラベルを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5826a-145">You can add a retention label to an existing form processing model that you own through the Automate menu in the document library in which the model is applied.</span></span>


1. <span data-ttu-id="5826a-146">フォーム処理モデルが適用されているドキュメント ライブラリで、<b>[自動化]</b> メニューを選択し、<b>[AI Builder]</b> を選択してから、<b>[フォーム処理モデルの詳細を表示する]</b> を選択します。</span><span class="sxs-lookup"><span data-stu-id="5826a-146">In your document library to which the form processing model is applied, select the <b>Automate</b> menu, select <b>AI Builder</b>, then select <b>View form processing model details</b>.</span></span>

   ![[自動化] メニュー](../media/content-understanding/automate-menu.png)</br>

2. <span data-ttu-id="5826a-148">モデルの詳細の <b>[保持ラベル]</b> セクションで、適用する保持ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="5826a-148">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="5826a-149">その後、<b>[保存]</b> を選択します。</span><span class="sxs-lookup"><span data-stu-id="5826a-149">Then select <b>Save</b>.</span></span>

     ![既存のフォーム処理モデルに追加する](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a><span data-ttu-id="5826a-151">[アクティブなモデル] の設定で既存のフォーム処理モデルに保持ラベルを追加するには</span><span class="sxs-lookup"><span data-stu-id="5826a-151">To add a retention label to an existing form processing model in the active model settings</span></span>

<span data-ttu-id="5826a-152">モデルが適用されているドキュメント ライブラリの [アクティブなモデル] の設定から、所有している既存のフォーム処理モデルに保持ラベルを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5826a-152">You can add a retention label to an existing form processing model that you own through the Active model settings in the document library in which the model is applied.</span></span>

1. <span data-ttu-id="5826a-153">モデルが適用されている SharePoint ドキュメント ライブラリで、<b>[アクティブなモデルを表示する]</b> アイコンを選択し、<b>[アクティブなモデルを表示する]</b> を選択します。</b></span><span class="sxs-lookup"><span data-stu-id="5826a-153">In the SharePoint document library in which the model is applied, select the <b>View active models</b> icon, and then select <b>View active models</b>.</b></span></span>

   ![アクティブなモデルを表示する](../media/content-understanding/info-du.png)</br> 

2. <span data-ttu-id="5826a-155"><b>[アクティブなモデル]</b> で、保持ラベルを適用するフォーム処理モデルを選択します。</span><span class="sxs-lookup"><span data-stu-id="5826a-155">In <b>Active models</b>, select the form processing model to which you want to apply the retention label.</span></span>

     ![モデルの詳細](../media/content-understanding/retention-label-model-details.png)</br> 


3. <span data-ttu-id="5826a-157">モデルの詳細の <b>[保持ラベル]</b> セクションで、適用する保持ラベルを選択します。</span><span class="sxs-lookup"><span data-stu-id="5826a-157">In the model details, in the <b>Retention Label</b> section, select the retention label you want to apply.</span></span>  <span data-ttu-id="5826a-158">その後、<b>[保存]</b> を選択します。</span><span class="sxs-lookup"><span data-stu-id="5826a-158">Then select <b>Save</b>.</span></span>

> [!NOTE]
> <span data-ttu-id="5826a-159">モデル設定ウィンドウを編集可能にするには、モデルの所有者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5826a-159">You must be the model owner for the model settings pane to be editable.</span></span> 


## <a name="see-also"></a><span data-ttu-id="5826a-160">関連項目</span><span class="sxs-lookup"><span data-stu-id="5826a-160">See Also</span></span>
[<span data-ttu-id="5826a-161">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="5826a-161">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="5826a-162">抽出子を作成する</span><span class="sxs-lookup"><span data-stu-id="5826a-162">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="5826a-163">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="5826a-163">Document Understanding overview</span></span>](document-understanding-overview.md)


