---
title: 抽出器を作成する
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
description: Microsoft SharePoint の同期 Tex で抽出器を作成する方法について説明します。
ms.openlocfilehash: 740df6769b3a1675e4e1691f84d164312b15567c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295458"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="22ee6-103">抽出器を作成する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="22ee6-103">Create an extractor (Preview)</span></span>

<span data-ttu-id="22ee6-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="22ee6-104">The content in this article is for the Project Cortex Private Preview.</span></span> <span data-ttu-id="22ee6-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22ee6-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="22ee6-106">特定のドキュメントの種類の識別と分類を自動化する分類子モデルを作成する前または後に、必要に応じて、モデルに抽出器を追加して、これらのドキュメントから特定の情報を引き出すことができます。</span><span class="sxs-lookup"><span data-stu-id="22ee6-106">Before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="22ee6-107">たとえば、ドキュメントライブラリに追加されたすべての契約の *更新* ドキュメントを識別するだけでなく、各ドキュメントのサービスの *開始日* をドキュメントライブラリ内の列として表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="22ee6-107">For example, you may want your model not only to identify all *Contract Renewal* documents added to your document library, but also to display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="22ee6-108">抽出するドキュメント内の各エンティティに対して抽出器を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22ee6-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="22ee6-109">サンプルでは、モデルによって識別される各*契約更新*ドキュメントの*サービス開始日*を抽出します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-109">In the sample, you want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="22ee6-110">これは、すべての *契約更新* ドキュメントのドキュメントライブラリに、各ドキュメントのサービス開始日の値を示す列を含むビューを表示する場合に発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22ee6-110">This must happen when you want to see a view in the document library of all the *Contract Renewal* documents with a column showing the Service Start date value for each document.</span></span>

> [!NOTE]
> <span data-ttu-id="22ee6-111">抽出器を作成する前に、 [サンプルファイルを追加して](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) 、抽出する情報を識別するためにモデルを学習させることができます。</span><span class="sxs-lookup"><span data-stu-id="22ee6-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="22ee6-112">分類子の作成に使用したのと同じサンプルファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-112">Use the same sample files you used to create your classifier.</span></span>

## <a name="name-your-extractor"></a><span data-ttu-id="22ee6-113">抽出器の名前</span><span class="sxs-lookup"><span data-stu-id="22ee6-113">Name your extractor</span></span>

1. <span data-ttu-id="22ee6-114">モデルのホームページで、[ **作成とトレーニング** ] の [抽出] タイルで、[ **train**tile] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22ee6-114">From the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="22ee6-115">**新しいエンティティ抽出**画面で、[**新しい抽出器名**] フィールドに抽出器の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="22ee6-116">たとえば、各契約更新文書からサービス開始日を抽出する場合は、「 **サービス開始日** 」という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-116">For example, name it **Service Start Date** if you want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="22ee6-117">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22ee6-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="22ee6-118">ラベルを追加する</span><span class="sxs-lookup"><span data-stu-id="22ee6-118">Add a label</span></span>

<span data-ttu-id="22ee6-119">次の手順では、サンプルのトレーニングファイルで抽出する情報のラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-119">The next step is to label the information you want to extract in your sample training files.</span></span>

<span data-ttu-id="22ee6-120">抽出器を作成すると、抽出ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="22ee6-120">Creating the extractor opens the extractor page.</span></span> <span data-ttu-id="22ee6-121">ここには、サンプルファイルの一覧が表示され、最初のファイルは viewer に表示されるリストにあります。</span><span class="sxs-lookup"><span data-stu-id="22ee6-121">Here you see a list of your sample files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="22ee6-122">ビューアーから、ファイルから抽出するデータを選択します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-122">From the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="22ee6-123">たとえば、 *サービス開始日*を抽出する場合は、最初のファイル (*2019 年10月14日 (月)*) の日付の値を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-123">For example, if you want to extract the *Start Service Date*, you highlight the date value in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="22ee6-124">[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22ee6-124">and then click **Save**.</span></span>  <span data-ttu-id="22ee6-125">[ラベル] 列の下の [ **ラベル** 付きの例] の一覧に、ファイルからの値が表示されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22ee6-125">You should see the value display from the file in the Labeled examples list, under the **Label** column.</span></span>
2. <span data-ttu-id="22ee6-126">[ **次のファイル** ] を選択して、自動保存し、ビューアーのリストで次のファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="22ee6-126">Select **Next file** to auto save and open the next file in the list in the viewer.</span></span> <span data-ttu-id="22ee6-127">または、[ **保存** ] を選択し、[ **ラベル付きの例** ] の一覧から別のファイルを選択します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-127">Or select **Save** and then select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="22ee6-128">ビューアーで手順1と2を繰り返し、5つのファイルすべてにラベルが保存されるまで繰り返します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-128">In the viewer, repeat steps 1 and 2, then repeat until you saved the label in all five files.</span></span>

    ![詳細設定](../media/content-understanding/select-service-start-date.png) 

### <a name="add-a-negative-example"></a><span data-ttu-id="22ee6-130">負の例を追加する</span><span class="sxs-lookup"><span data-stu-id="22ee6-130">Add a negative example</span></span>

<span data-ttu-id="22ee6-131">分類子を作成するときに負のサンプルファイルを追加するのと同様に、抽出器に負の標本を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22ee6-131">Similar to how you add a negative sample file when creating a classifier, you need to add a negative sample for the extractor.</span></span> <span data-ttu-id="22ee6-132">"サービス開始" の日付の値が含まれていないファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="22ee6-132">It should be a file that does not contain a "Service Start" date value.</span></span>

1. <span data-ttu-id="22ee6-133">**ラベル付きの例**のリストから、負の例を選択します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-133">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="22ee6-134">記事の上部にあるビューアーで、[ **ラベルが存在しません**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-134">In the viewer on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="22ee6-135">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="22ee6-135">Click **Save**.</span></span>
 
<span data-ttu-id="22ee6-136">5つのファイルがラベル付けされると、トレーニングに移行するように通知バナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="22ee6-136">Once you labeled five files, a notification banner displays informing you to move to training.</span></span> <span data-ttu-id="22ee6-137">その他のドキュメントを選択したり、トレーニングを進めることができます。</span><span class="sxs-lookup"><span data-stu-id="22ee6-137">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="22ee6-138">説明を追加する</span><span class="sxs-lookup"><span data-stu-id="22ee6-138">Add an explanation</span></span>

<span data-ttu-id="22ee6-139">この例では、エンティティ形式自体とサンプルドキュメントに含まれるバリエーションに関するヒントを提供する説明を作成します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-139">For the example, you create an explanation that provides a hint about the entity format itself and variations it may have in the sample documents.</span></span> <span data-ttu-id="22ee6-140">たとえば、日付値は次のようなさまざまな形式で指定できます。</span><span class="sxs-lookup"><span data-stu-id="22ee6-140">For example, a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="22ee6-141">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="22ee6-141">10/14/2019</span></span>
- <span data-ttu-id="22ee6-142">2019 年 10 月 14 日</span><span class="sxs-lookup"><span data-stu-id="22ee6-142">October 14, 2019</span></span>
- <span data-ttu-id="22ee6-143">2019年10月14日 (月)</span><span class="sxs-lookup"><span data-stu-id="22ee6-143">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="22ee6-144">*サービスの開始日*を特定するために、パターンの説明を作成します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-144">To help identify the *Service Start Date* you create a pattern explanation.</span></span>

1. <span data-ttu-id="22ee6-145">[説明] セクションで、[ **新規** ] を選択し、名前 (たとえば、[ *日付*]) を入力します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-145">In the Explanation section, select **New** and type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="22ee6-146">[種類] で、[ **パターンリスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-146">For Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="22ee6-147">[値] で、サンプルファイルに表示される日付のバリエーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-147">For Value, provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="22ee6-148">たとえば、0/00/0000 として表示される日付形式がある場合は、ドキュメントに表示される次のようなバリエーションを入力します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-148">For example, if you have date formats that appear as 0/00/0000, you enter any variations that appear in your documents, such as:</span></span>
    - <span data-ttu-id="22ee6-149">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="22ee6-149">0/0/0000</span></span>
    - <span data-ttu-id="22ee6-150">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="22ee6-150">0/00/0000</span></span>
    - <span data-ttu-id="22ee6-151">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="22ee6-151">00/0/0000</span></span>
    - <span data-ttu-id="22ee6-152">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="22ee6-152">00/00/0000</span></span>
4. <span data-ttu-id="22ee6-153">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-153">Select **Save**.</span></span>

### <a name="use-the-explanation-library"></a><span data-ttu-id="22ee6-154">説明ライブラリを使用する</span><span class="sxs-lookup"><span data-stu-id="22ee6-154">Use the Explanation library</span></span>

<span data-ttu-id="22ee6-155">日付などのアイテムの説明を作成するには、説明ライブラリを使用する方が、すべてのバリエーションを手動で入力するよりも簡単です。</span><span class="sxs-lookup"><span data-stu-id="22ee6-155">For creating explanations for items such as dates, it is easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="22ee6-156">説明ライブラリは、あらかじめ用意された語句とパターンの説明のセットです。</span><span class="sxs-lookup"><span data-stu-id="22ee6-156">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="22ee6-157">ライブラリは、日付、電話番号、郵便番号など、一般的な語句やパターンリストのすべての書式を提供します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-157">The library provides all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, etc.</span></span> 

<span data-ttu-id="22ee6-158">サービスの *開始日* のサンプルの場合、説明ライブラリの *日付* についてあらかじめ用意されている説明を使用する方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="22ee6-158">For the *Service Start Date* sample, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="22ee6-159">[ **説明] セクション**で、[ **新規**] を選択し、[ **説明ライブラリから**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-159">In the **Explanation section**, select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="22ee6-160">説明ライブラリで、[ **日付**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-160">From the explanation library, select **Date**.</span></span> <span data-ttu-id="22ee6-161">認識される日付のバリエーションをすべて表示できます。</span><span class="sxs-lookup"><span data-stu-id="22ee6-161">You can view all variations of date that are recognized.</span></span>
3. <span data-ttu-id="22ee6-162">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-162">Select **Add**.</span></span></br>

    ![説明ライブラリ](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="22ee6-164">[ **説明の作成** ] ページでは、説明ライブラリからの *日付* 情報がフィールドに自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="22ee6-164">On the **Create an explanation** page, the *Date* information from the explanation library auto fills the fields.</span></span> <span data-ttu-id="22ee6-165">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-165">Select **Save**.</span></span></br>

    ![日付](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a><span data-ttu-id="22ee6-167">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="22ee6-167">Train the model</span></span> 

<span data-ttu-id="22ee6-168">説明を保存するトレーニングを開始します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-168">Saving your explanation start the training.</span></span> <span data-ttu-id="22ee6-169">ラベル付けされたサンプルファイルからデータを抽出するのに十分な情報がモデルにある場合は、各ファイルに **一致**するというラベルが付いています。</span><span class="sxs-lookup"><span data-stu-id="22ee6-169">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![Match](../media/content-understanding/match2.png) 

<span data-ttu-id="22ee6-171">抽出するデータを検索するのに十分な情報が説明にない場合、各ファイルには **不一致**というラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="22ee6-171">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="22ee6-172">不一致ファイルをクリックし **て、不一致** が発生した理由に関する詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="22ee6-172">You can click on the **Mismatched** files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="22ee6-173">別の説明を追加する</span><span class="sxs-lookup"><span data-stu-id="22ee6-173">Add another explanation</span></span>

<span data-ttu-id="22ee6-174">多くの場合、不一致は、指定された説明には、サービスの開始日の値を抽出して、ラベル付きファイルと一致させるために十分な情報が提供されなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="22ee6-174">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="22ee6-175">編集または別の説明を追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="22ee6-175">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="22ee6-176">サンプルの場合は、[ *サービス開始日] の日付* が実際の値よりも前になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="22ee6-176">For the sample, notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="22ee6-177">サービスの開始日を識別するために、語句の説明を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22ee6-177">To help identify the Service Start Date, you need ot create a phrase explanation.</span></span>

1. <span data-ttu-id="22ee6-178">[説明] セクションで、[ **新規**] を選択し、名前 (たとえば、 *プレフィックス文字列*) を入力します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-178">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="22ee6-179">[種類] で、[ **語句リスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-179">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="22ee6-180">*のサービス開始日*を値として使用します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-180">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="22ee6-181">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-181">Select **Save**.</span></span>

    ![プレフィックス文字列](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a><span data-ttu-id="22ee6-183">モデルを再トレーニングする</span><span class="sxs-lookup"><span data-stu-id="22ee6-183">Train the model again</span></span>

<span data-ttu-id="22ee6-184">説明を保存すると、トレーニングが再度開始されます。今回はサンプルの両方の説明を使用します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-184">Saving the explanation starts the training again, this time using both explanations in the sample.</span></span> <span data-ttu-id="22ee6-185">ラベル付きのサンプルファイルからデータを抽出するために十分な情報がモデルにある場合は、各ファイルに **一致**するというラベルが付いています。</span><span class="sxs-lookup"><span data-stu-id="22ee6-185">If your model has enough information to extract the data from the labeled sample files, you see each file labeled with **Match**.</span></span> 

<span data-ttu-id="22ee6-186">ラベル付きファイルの **不一致** を再度受信した場合は、ドキュメントの種類を識別するためにモデルに詳細情報を提供するために別の説明を作成する必要があります。または、サンプルモデルに変更を加えることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="22ee6-186">If you again receive a **Mismatch** on your labeled files, you likely need to create another explanation to provide the model more information to identify the document type, or consider making changes to your sample model.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="22ee6-187">モデルをテストする</span><span class="sxs-lookup"><span data-stu-id="22ee6-187">Test your model</span></span>

<span data-ttu-id="22ee6-188">ラベル付けされたサンプルファイルに一致するものがあれば、残りのラベルのないサンプルファイルでモデルをテストできるようになります。</span><span class="sxs-lookup"><span data-stu-id="22ee6-188">If you receive a match on your labeled sample files, you can now test your model on the remaining unlabeled sample files.</span></span>

1. <span data-ttu-id="22ee6-189">モデルのホームページで、[ **テスト** ] タブをクリックします。 これにより、ラベルのないサンプルファイルでモデルが実行されます。</span><span class="sxs-lookup"><span data-stu-id="22ee6-189">From the model home page, click the **Test** tab.  This runs the model on your unlabeled sample files.</span></span>
2. <span data-ttu-id="22ee6-190">[ **テストファイル** ] の一覧に、モデルが必要な情報を抽出できるかどうかを示すサンプルファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="22ee6-190">In the **Test files** list, your example files display to show if the model is able to extract the information you need.</span></span> <span data-ttu-id="22ee6-191">この情報を使用して、ドキュメントを識別する際に、分類子の有効性を判断します。</span><span class="sxs-lookup"><span data-stu-id="22ee6-191">Use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![ファイルのテスト](../media/content-understanding/test-filies-extractor.png) 
