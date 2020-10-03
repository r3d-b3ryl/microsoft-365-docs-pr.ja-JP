---
title: エクストラクターを作成する
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Microsoft SharePoint Syntex でエクストラクターを作成する方法について説明します。
ms.openlocfilehash: 260486c128ce76c31fe5f4a0994b4e103687b829
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338651"
---
# <a name="create-an-extractor-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="01c3e-103">Microsoft SharePoint Syntex でエクストラクターを作成する</span><span class="sxs-lookup"><span data-stu-id="01c3e-103">Create an extractor in Microsoft SharePoint Syntex</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="01c3e-104">特定のドキュメントの種類の識別および分類を自動化するために、分類子モデルを作成する前または後に、必要に応じて、ドキュメントから特定の情報を抽出するために、エクストラクターをモデルに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-104">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="01c3e-105">たとえば、ドキュメントライブラリに追加されたドキュメントのすべての *契約更新*ドキュメントを特定するだけでなく、ドキュメントライブラリの列値として各ドキュメントの *サービスの開始日* を表示するようにモデルを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-105">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column value in the document library.</span></span>

<span data-ttu-id="01c3e-106">抽出するドキュメント内の各エンティティに、エクストラクターを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01c3e-106">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="01c3e-107">この例では、モデルによって識別された それぞれの **契約更新** ドキュメントについて **サービスの開始日**を抽出します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-107">In our example, we want to extract the **Service Start Date** for each **Contract Renewal** document that is identified by the model.</span></span> <span data-ttu-id="01c3e-108">すべての **コントラクト更新** ドキュメントのドキュメントライブラリのビューが表示され、各ドキュメントの **サービス開始日** の値を示す列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-108">We want to be able to see a view in the document library of all **Contract Renewal** documents, with a column that shows the **Service Start** date value of each document.</span></span> 

> [!NOTE]
> <span data-ttu-id="01c3e-109">エクストラクターを作成するには、先ほど分類子にトレーニングを行う目的でアップロードしたものと同ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-109">In order to create an extractor, you use the same files you previously uploaded to train the classifier.</span></span> 

## <a name="name-your-extractor"></a><span data-ttu-id="01c3e-110">エクストラクターに名前を付ける</span><span class="sxs-lookup"><span data-stu-id="01c3e-110">Name your extractor</span></span>

1. <span data-ttu-id="01c3e-111">[モデルのホーム] ページで、[ **エクストラクターの作成とトレーニング**] タイルの [**トレーニングを行う**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01c3e-111">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="01c3e-112">[**新しいエンティティエクストラクター** ] 画面で、[ **新しいエクストラクター 名**] フィールドにエクストラクターの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-112">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="01c3e-113">たとえば、契約更新の各ドキュメントからサービス開始日を抽出する場合は、「**サービスの開始日**と名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-113">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span> <span data-ttu-id="01c3e-114">以前に作成した列 (例えば[管理されたメタデータ] 列など) を再使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-114">You can also choose to reuse a previously created column (for example, a managed metadata column).</span></span>
3. <span data-ttu-id="01c3e-115">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01c3e-115">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="01c3e-116">ラベルを追加する</span><span class="sxs-lookup"><span data-stu-id="01c3e-116">Add a label</span></span>

<span data-ttu-id="01c3e-117">次の手順では、サンプルトレーニングファイルで抽出するエンティティにラベルを付けます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-117">The next step is to label the entity you want to extract in your example training files.</span></span>

<span data-ttu-id="01c3e-118">エクストラクターを作成すると、エクストラクターページが開きます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-118">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="01c3e-119">ここでは、サンプルファイルの一覧が表示されます。リストの最初のファイルは、viewer に表示されています。</span><span class="sxs-lookup"><span data-stu-id="01c3e-119">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="01c3e-120">Viewer で、ファイルから抽出するデータを選択します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-120">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="01c3e-121">たとえば、 *サービスの開始日*を抽出する場合は、最初のファイルの日付値を強調表示します (*月曜、2019年10月14日*)。</span><span class="sxs-lookup"><span data-stu-id="01c3e-121">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="01c3e-122">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01c3e-122">and then click **Save**.</span></span>  <span data-ttu-id="01c3e-123">ラベルの付いた [サンプル] リストにあるファイルの値を、[ **ラベル** ] 列で確認します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-123">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="01c3e-124">[ **次の ファイル**] を選択して、viewer の一覧で次のファイルを自動的に保存して開きます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-124">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="01c3e-125">または、[**保存**] を選択し [ **ラベルが付いた サンプル** ] の一覧から別のファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-125">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="01c3e-126">このビューアーで、手順1と2を繰り返し、5つのファイルすべてにラベルを保存します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-126">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![詳細設定](../media/content-understanding/select-service-start-date.png) 

 
<span data-ttu-id="01c3e-128">5個のファイルにラベルを付けたら、トレーニングに移動するように通知バナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-128">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="01c3e-129">ドキュメントのラベルを追加するか、トレーニングに進めるか、選択することができます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-129">You can choose to more label more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="01c3e-130">説明を作成する</span><span class="sxs-lookup"><span data-stu-id="01c3e-130">Add an explanation</span></span>

<span data-ttu-id="01c3e-131">この例では、エンティティ形式自体とサンプルドキュメントのバリエーションに関するヒントを提供する説明を作成します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-131">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="01c3e-132">たとえば、次のようなさまざまな形式の日付値を指定できます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-132">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="01c3e-133">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="01c3e-133">10/14/2019</span></span>
- <span data-ttu-id="01c3e-134">2019 年 10 月 14 日</span><span class="sxs-lookup"><span data-stu-id="01c3e-134">October 14, 2019</span></span>
- <span data-ttu-id="01c3e-135">2019 年 10 月 14 日、月曜日</span><span class="sxs-lookup"><span data-stu-id="01c3e-135">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="01c3e-136">*サービスの開始日*を特定するには パターンの説明を作成します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-136">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="01c3e-137">[説明] セクションで、[ **新しい**] を選択し、名前 (例えば*日付*) を入力します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-137">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="01c3e-138">[種類] で、[ **パターン一覧]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-138">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="01c3e-139">[値] には、サンプルファイルに表示される日付のバリエーションを入力します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-139">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="01c3e-140">たとえば、0/00/0000 として表示される日付形式がある場合は、次のようなドキュメントに表示されるバリエーションを入力します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-140">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="01c3e-141">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="01c3e-141">0/0/0000</span></span>
    - <span data-ttu-id="01c3e-142">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="01c3e-142">0/00/0000</span></span>
    - <span data-ttu-id="01c3e-143">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="01c3e-143">00/0/0000</span></span>
    - <span data-ttu-id="01c3e-144">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="01c3e-144">00/00/0000</span></span>
4. <span data-ttu-id="01c3e-145">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-145">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="01c3e-146">説明の種類の詳細については、「 [説明の種類](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="01c3e-146">For more learn more about explanation types, see [Explanation types](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview).</span></span>  


### <a name="use-the-explanation-library"></a><span data-ttu-id="01c3e-147">説明ライブラリ</span><span class="sxs-lookup"><span data-stu-id="01c3e-147">Use the Explanation library</span></span>

<span data-ttu-id="01c3e-148">日付などのアイテムの説明を作成するには、[説明ライブラリ を使用する](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library)方があらゆるバリエーションを手動で入力するより簡単です。</span><span class="sxs-lookup"><span data-stu-id="01c3e-148">For creating explanations for items such as dates, it is easier to [use the explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) than to manually enter all variations.</span></span> <span data-ttu-id="01c3e-149">説明ライブラリは、あらかじめ用意されている語句やパターンの説明のセットです。</span><span class="sxs-lookup"><span data-stu-id="01c3e-149">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="01c3e-150">ライブラリでは、日付、電話番号、郵便番号などの一般的な語句またはパターンリストのすべての書式設定を行います。</span><span class="sxs-lookup"><span data-stu-id="01c3e-150">The library tries to provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip codes, and many others.</span></span> 

<span data-ttu-id="01c3e-151">*サービスの開始日* サンプルでは、説明ライブラリの*日付* についての既成の説明を使用する方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="01c3e-151">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="01c3e-152">[ **の説明] セクション**で、[ **新規**] を選択し、[**説明ライブラリ から**]を選択します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-152">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="01c3e-153">[説明ライブラリ] で、[ **日付**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-153">From the explanation library, select **Date**.</span></span> <span data-ttu-id="01c3e-154">認識された日付のあらゆるバリエーションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-154">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="01c3e-155">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-155">Select **Add**.</span></span></br>

    ![説明ライブラリ](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="01c3e-157">[**説明を作成する** ページで、説明ライブラリの *日付*情報がフィールドに自動入力されます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-157">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="01c3e-158">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-158">Select **Save**.</span></span></br>

    ![日付](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="01c3e-160">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="01c3e-160">Train the model</span></span> 

<span data-ttu-id="01c3e-161">トレーニング開始の説明を保存します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-161">Saving your explanation start the training.</span></span> <span data-ttu-id="01c3e-162">モデルにラベル付けされたサンプルファイルからデータを抽出するための情報が十分にある場合は、各ファイルが **一致**とラベルを付けられたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-162">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![一致](../media/content-understanding/match2.png) 

<span data-ttu-id="01c3e-164">抽出するデータを検索するのに十分な情報が説明に表示されない場合は、各ファイルに **不一致**のラベルが付いています。</span><span class="sxs-lookup"><span data-stu-id="01c3e-164">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="01c3e-165">不一致があった理由の詳細については、 **不一致** ファイルをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="01c3e-165">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="01c3e-166">別の説明を追加する</span><span class="sxs-lookup"><span data-stu-id="01c3e-166">Add another explanation</span></span>

<span data-ttu-id="01c3e-167">不一致は多くの場合、指定した説明では、十分な情報がないため、[サービス開始日] の値を抽出して、ラベル付けされたファイルと一致させることができなかったことを意味します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-167">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="01c3e-168">編集するか、別の説明を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01c3e-168">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="01c3e-169">この例では、文字列 *サービス開始日* が実際の値より前になることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="01c3e-169">For our example, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="01c3e-170">サービスの開始日を特定を容易にするには、語句の説明を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01c3e-170">To help identify the Service Start Date, you need to create a phrase explanation.</span></span>

1. <span data-ttu-id="01c3e-171">[説明] セクションで、[**新しい**] を選択し、名前を入力します (例: *Prefix String*)。</span><span class="sxs-lookup"><span data-stu-id="01c3e-171">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="01c3e-172">[種類] で、[ **語句のリスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-172">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="01c3e-173">*サービス の開始日*を値として使用します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-173">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="01c3e-174">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-174">Select **Save**.</span></span>

    ![Prefix 文字列](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="01c3e-176">モデルを再トレーニングする</span><span class="sxs-lookup"><span data-stu-id="01c3e-176">Train the model again</span></span>

<span data-ttu-id="01c3e-177">説明を保存すると、トレーニングが開始されます。今回は、この2つの説明をサンプルファイルに使用します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-177">Saving the explanation starts the training again, this time using both explanations in the example.</span></span> <span data-ttu-id="01c3e-178">ラベル付けされたサンプルファイルからデータを抽出するのに十分な情報がモデルに含まれている場合は、 **一致**とファイルにラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-178">If your model has enough information to extract the data from the labeled example files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="01c3e-179">ラベルが付けられたファイルの **不一致**が再び表示された場合は、ドキュメントの種類を識別するための詳細な情報をさらに追加するか、または既存の説明を変更することをお考えください。</span><span class="sxs-lookup"><span data-stu-id="01c3e-179">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="01c3e-180">モデルをテストする</span><span class="sxs-lookup"><span data-stu-id="01c3e-180">Test your model</span></span>

<span data-ttu-id="01c3e-181">ラベル付きのサンプルファイルに対して一致が返された場合は、ラベルの付いていないその他のファイルの例でモデルをテストできます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-181">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled example files.</span></span> <span data-ttu-id="01c3e-182">これはオプションのですが、モデルを使用する前に、モデルが処理したことのないファイルでテストすることによって、モデルの「健全さ」をチェックし準備ができたかどうかを評価するのに便利な手順です。</span><span class="sxs-lookup"><span data-stu-id="01c3e-182">This is optional, but a useful step to evaluate the “fitness” or readiness of the model before using it, by testing it on files the model hasn’t seen before.</span></span>

1. <span data-ttu-id="01c3e-183">[モデルのホーム] ページで、[ **テスト** ] タブを選択します。 ラベル付けのされていないサンプルファイル上でモデルが実行されます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-183">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="01c3e-184">[ **テストファイル** ] の一覧で、サンプルファイルから必要な情報が抽出されているかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="01c3e-184">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="01c3e-185">この情報を使用して、ドキュメントを特定するときの分類子の有効性を判断します。</span><span class="sxs-lookup"><span data-stu-id="01c3e-185">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![ファイルに対してテストする](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="01c3e-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="01c3e-187">See Also</span></span>
[<span data-ttu-id="01c3e-188">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="01c3e-188">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="01c3e-189">説明の種類</span><span class="sxs-lookup"><span data-stu-id="01c3e-189">Explanation types</span></span>](explanation-types-overview.md)

[<span data-ttu-id="01c3e-190">エクストラクターの作成時に用語ストアの分類を活用する</span><span class="sxs-lookup"><span data-stu-id="01c3e-190">Leverage term store taxonomy when creating an extractor</span></span>](leverage-term-store-taxonomy.md)

[<span data-ttu-id="01c3e-191">ドキュメント理解の概要</span><span class="sxs-lookup"><span data-stu-id="01c3e-191">Document Understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="01c3e-192">モデルを適用する</span><span class="sxs-lookup"><span data-stu-id="01c3e-192">Apply a model</span></span>](apply-a-model.md) 
