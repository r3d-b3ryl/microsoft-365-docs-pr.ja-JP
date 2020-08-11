---
title: 抽出器を作成する (プレビュー)
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
description: 抽出器を作成する方法について
ms.openlocfilehash: 64dede9f6613da82c65ca12c6c335a25301f5b9e
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612764"
---
# <a name="create-an-extractor-preview"></a><span data-ttu-id="33b98-103">抽出器を作成する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="33b98-103">Create an extractor (Preview)</span></span>
> [!Note] 
> <span data-ttu-id="33b98-104">この記事の内容は、Project Cortex のプライベートプレビュー用です。</span><span class="sxs-lookup"><span data-stu-id="33b98-104">The content in this article is for Project Cortex Private Preview.</span></span> <span data-ttu-id="33b98-105">[詳細については、「Project Cortex](https://aka.ms/projectcortex)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33b98-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

<span data-ttu-id="33b98-106">特定のドキュメントの種類の識別と分類を自動化するために、分類子モデルを作成する前または作成した後で、必要に応じて、モデルに抽出器を追加して、これらのドキュメントから特定の情報を取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="33b98-106">Either before or after you create a classifier model to automate identification and classification of specific document types, you can optionally choose to add extractors to your model to pull out specific information from these documents.</span></span> <span data-ttu-id="33b98-107">たとえば、ドキュメントライブラリに追加されたすべての*契約更新*ドキュメントを識別するだけでなく、ドキュメントライブラリの列として各ドキュメントの*サービスの開始日*も表示する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="33b98-107">For example, you may want your model not only to identify all *Contract Renewal* documents that are added to your document library, but to also display the *Service Start date* for each document as a column in the document library.</span></span>

<span data-ttu-id="33b98-108">抽出するドキュメント内の各エンティティに対して抽出器を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33b98-108">You need to create an extractor for each entity in the document that you want to extract.</span></span> <span data-ttu-id="33b98-109">この例では、モデルによって識別される各*契約更新*ドキュメントの*サービス開始日*を抽出します。</span><span class="sxs-lookup"><span data-stu-id="33b98-109">In our example, we want to extract the *Service Start Date* for each *Contract Renewal* document that is identified by the model.</span></span> <span data-ttu-id="33b98-110">すべての*契約更新*ドキュメントのドキュメントライブラリにビューを表示できるようにし、各ドキュメントのサービス開始日の値を示す列を追加します。</span><span class="sxs-lookup"><span data-stu-id="33b98-110">We want to be able to see a view in the document library of all *Contract Renewal* documents, with a column that shows the Service Start date value of each document.</span></span>

> [!Note]
> <span data-ttu-id="33b98-111">抽出器を作成する前に、[サンプルファイルを追加](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files)する必要があります。これは、モデルをトレーニングして抽出する情報を識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="33b98-111">Before creating an extractor, you need to [add your example files](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) you will need to help train the model to identify the information you want to extract.</span></span> <span data-ttu-id="33b98-112">分類子の作成に使用したのと同じサンプルファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="33b98-112">Use the same example files you used to create your classifier.</span></span>


## <a name="name-your-extractor"></a><span data-ttu-id="33b98-113">抽出器の名前</span><span class="sxs-lookup"><span data-stu-id="33b98-113">Name your extractor</span></span>

1. <span data-ttu-id="33b98-114">モデルのホームページで、[**作成とトレーニング**] [抽出] タイルの [[トレーニング] [**抽出**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33b98-114">On the model home page, in the **Create and train extractors** tile, click **Train extractor**.</span></span>
2. <span data-ttu-id="33b98-115">**新しいエンティティ抽出**画面で、[**新しい抽出器名**] フィールドに抽出器の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="33b98-115">On the **New entity extractor** screen, type the name of your extractor in the **New extractor name** field.</span></span> <span data-ttu-id="33b98-116">たとえば、各契約更新文書からサービスの開始日を抽出する場合は、**サービスの開始日**に名前を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="33b98-116">For example, we can name it **Service Start Date** if we want to extract the service start date from each Contract Renewal document.</span></span>
3. <span data-ttu-id="33b98-117">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33b98-117">Click **Create**.</span></span>

## <a name="add-a-label"></a><span data-ttu-id="33b98-118">ラベルを追加する</span><span class="sxs-lookup"><span data-stu-id="33b98-118">Add a label</span></span>

<span data-ttu-id="33b98-119">次の手順では、サンプルのトレーニングファイルで抽出する情報のラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="33b98-119">The next step is to label the information you want to extract in your example training files.</span></span>

<span data-ttu-id="33b98-120">抽出器を作成すると、抽出器ページが開きます。このページには、サンプルファイルの一覧が表示されます。このページには、ビューアーに表示されるリストの最初のファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="33b98-120">Creating the extractor will open the extractor page in which you will see a list of your example files, with the first file on the list displayed in the viewer.</span></span>

1. <span data-ttu-id="33b98-121">ビューアーで、ファイルから抽出するデータを選択します。</span><span class="sxs-lookup"><span data-stu-id="33b98-121">In the viewer, select the data that you want to extract from the files.</span></span> <span data-ttu-id="33b98-122">たとえば、*開始サービスの日付*を抽出する場合は、最初のファイル (*2019 年10月 14*日) に日付の値を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="33b98-122">For example, if you want to extract the *Start Service Date*, you will highlight the date value for it in the first file (*Monday, October 14, 2019*).</span></span> <span data-ttu-id="33b98-123">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33b98-123">Then click **Save**.</span></span>  <span data-ttu-id="33b98-124">[**ラベル**] 列の [ラベル付きの例] の一覧に、ファイルの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="33b98-124">You will see the value display for the file in the Labeled examples list under the **Label** column.</span></span>
2. <span data-ttu-id="33b98-125">[**次のファイル**] を選択して、ビューアーのリストで次のファイルを開きます。または、[**保存**] を選択して、**ラベル付きの例**のリストから別のファイルを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="33b98-125">Select **Next file** to autosave and open the next file in the list in the viewer, or you can select **Save** and select another file from the **Labeled examples** list.</span></span>
3. <span data-ttu-id="33b98-126">ビューアーで手順1と手順2を繰り返し、ラベルを5つのファイルに保存するまでこれを実行します。</span><span class="sxs-lookup"><span data-stu-id="33b98-126">In the viewer, repeat steps 1 and 2, and do this until you have saved the label in five files.</span></span>

    ![詳細設定](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a><span data-ttu-id="33b98-128">負の例を追加する</span><span class="sxs-lookup"><span data-stu-id="33b98-128">Add a negative example</span></span>

<span data-ttu-id="33b98-129">分類子を作成するときに負の例のファイルを追加するのと同じように、抽出器には負の例を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33b98-129">Similar to how you would add a negative example file when creating a classifier, you need to add a negative example for the extractor.</span></span> <span data-ttu-id="33b98-130">この例では、サービスの開始日の値が含まれていないファイルを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33b98-130">For our example, it should be a file that does not contain a Service Start Date value.</span></span>

1. <span data-ttu-id="33b98-131">**ラベル付きの例**のリストから、負の例を選択します。</span><span class="sxs-lookup"><span data-stu-id="33b98-131">From the **Labeled examples** list, select a negative example.</span></span>
2. <span data-ttu-id="33b98-132">ビューアーで、記事の上部にある [**ラベルなし**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33b98-132">In the viewer, on the top of the article, select **No label present**.</span></span>
3. <span data-ttu-id="33b98-133">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33b98-133">Click **Save**.</span></span>
 
<span data-ttu-id="33b98-134">5つのファイルをラベル付けしたら、トレーニングに移動するように通知バナーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="33b98-134">Once you have labeled five files, a notification banner will display informing you to move to training.</span></span> <span data-ttu-id="33b98-135">その他のドキュメントを選択したり、トレーニングを進めることができます。</span><span class="sxs-lookup"><span data-stu-id="33b98-135">You can choose to more documents or advance to training.</span></span> 

## <a name="add-an-explanation"></a><span data-ttu-id="33b98-136">説明を追加する</span><span class="sxs-lookup"><span data-stu-id="33b98-136">Add an explanation</span></span>

<span data-ttu-id="33b98-137">この例では、エンティティ形式自体とそのバリエーションに関するヒントを提供する説明を作成します。この説明は、サンプルドキュメントに記載されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="33b98-137">For our example, we are going to create an explanation that provides a hint about the entity format itself and variations it may have in the example documents.</span></span> <span data-ttu-id="33b98-138">たとえば、日付値は次のようなさまざまな形式で指定できます。</span><span class="sxs-lookup"><span data-stu-id="33b98-138">For example,a date value can be in a number of different formats, such as:</span></span>
- <span data-ttu-id="33b98-139">10/14/2019</span><span class="sxs-lookup"><span data-stu-id="33b98-139">10/14/2019</span></span>
- <span data-ttu-id="33b98-140">2019 年 10 月 14 日</span><span class="sxs-lookup"><span data-stu-id="33b98-140">October 14, 2019</span></span>
- <span data-ttu-id="33b98-141">2019年10月14日 (月)</span><span class="sxs-lookup"><span data-stu-id="33b98-141">Monday, October 14, 2019</span></span>
 

<span data-ttu-id="33b98-142">*サービスの開始日*を特定するために、パターンの説明を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="33b98-142">To help identify the *Service Start Date* you can create a pattern explanation.</span></span>

1. <span data-ttu-id="33b98-143">[説明] セクションで、[**新規**] を選択し、名前 (たとえば、 *Date*) を入力します。</span><span class="sxs-lookup"><span data-stu-id="33b98-143">In the Explanation section, select **New**, and then type a name (for example, *Date*).</span></span>
2. <span data-ttu-id="33b98-144">[種類] で、[**パターンリスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33b98-144">For the Type, select **Pattern list**.</span></span>
3. <span data-ttu-id="33b98-145">値については、サンプルファイルに表示される日付のバリエーションを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33b98-145">For the value, you need to provide the date variation as they appear in the sample files.</span></span> <span data-ttu-id="33b98-146">たとえば、0/00/0000 として表示される日付形式がある場合は、ドキュメントに表示される可能性のある次のようなバリエーションを入力します。</span><span class="sxs-lookup"><span data-stu-id="33b98-146">For example, if you have date formats that appear as 0/00/0000, you would enter any variations that might appear in your documents, such as:</span></span>
    - <span data-ttu-id="33b98-147">0/0/0000</span><span class="sxs-lookup"><span data-stu-id="33b98-147">0/0/0000</span></span>
    - <span data-ttu-id="33b98-148">0/00/0000</span><span class="sxs-lookup"><span data-stu-id="33b98-148">0/00/0000</span></span>
    - <span data-ttu-id="33b98-149">00/0/0000</span><span class="sxs-lookup"><span data-stu-id="33b98-149">00/0/0000</span></span>
    - <span data-ttu-id="33b98-150">00/00/0000</span><span class="sxs-lookup"><span data-stu-id="33b98-150">00/00/0000</span></span>
4. <span data-ttu-id="33b98-151">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33b98-151">Select **Save**.</span></span>


### <a name="use-the-explanation-library"></a><span data-ttu-id="33b98-152">説明ライブラリを使用する</span><span class="sxs-lookup"><span data-stu-id="33b98-152">Use the Explanation library</span></span>

<span data-ttu-id="33b98-153">日付などの事柄についての説明を作成するには、すべてのバリエーションを手動で入力するよりも、説明ライブラリを使用する方がはるかに簡単です。</span><span class="sxs-lookup"><span data-stu-id="33b98-153">For creating explanations for things such as dates, it is much easier to use the explanation library than to manually enter all variations.</span></span> <span data-ttu-id="33b98-154">説明ライブラリは、あらかじめ用意された語句とパターンの説明のセットです。</span><span class="sxs-lookup"><span data-stu-id="33b98-154">The explanation library is a set of pre-built phrase and pattern explanations.</span></span> <span data-ttu-id="33b98-155">ライブラリは、日付、電話番号、郵便番号など、一般的な語句やパターンリストのすべての書式を提供しようとします。</span><span class="sxs-lookup"><span data-stu-id="33b98-155">The library tries to provide all formats for common phrase or pattern lists, such as dates, phone numbers, zip code, and many others.</span></span> 

<span data-ttu-id="33b98-156">サービスの*開始日*の例では、説明ライブラリの*日付*の事前構築された説明を使用する方が効率的です。</span><span class="sxs-lookup"><span data-stu-id="33b98-156">For our *Service Start Date* example, it is more efficient to use the pre-built explanation for *Date* in the explanation library:</span></span>

1. <span data-ttu-id="33b98-157">[**説明] セクション**で、\* \* [**新規**] を選択し、[**説明ライブラリから**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33b98-157">In the **Explanation section**,\*\* select **New**, and then select **From explanation library**.</span></span>
2. <span data-ttu-id="33b98-158">説明ライブラリで、[**日付**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33b98-158">From the explanation library, select **Date**.</span></span> <span data-ttu-id="33b98-159">認識される日付のバリエーションをすべて表示できます。</span><span class="sxs-lookup"><span data-stu-id="33b98-159">You can view all variations of date that will be recognized.</span></span>
3. <span data-ttu-id="33b98-160">**[追加]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33b98-160">Select **Add**.</span></span></br>

    ![説明ライブラリ](../media/content-understanding/explanation-library.png) 

4. <span data-ttu-id="33b98-162">[**説明の作成**] ページで、説明ライブラリからの*日付*情報がフィールドにオートフィルされます。</span><span class="sxs-lookup"><span data-stu-id="33b98-162">On the **Create an explanation** page, the *Date* information from the explanation library will autofill the fields.</span></span> <span data-ttu-id="33b98-163">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33b98-163">Select **Save**.</span></span></br>

    ![説明ライブラリ](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a><span data-ttu-id="33b98-165">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="33b98-165">Train the model</span></span> 

<span data-ttu-id="33b98-166">説明を保存すると、トレーニングが開始されます。</span><span class="sxs-lookup"><span data-stu-id="33b98-166">Saving your explanation will start the training.</span></span> <span data-ttu-id="33b98-167">ラベル付けされたサンプルファイルからデータを抽出するのに十分な情報がモデルにある場合は、各ファイルに**一致**するというラベルが付いています。</span><span class="sxs-lookup"><span data-stu-id="33b98-167">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span>  

![説明ライブラリ](../media/content-understanding/match2.png) 

<span data-ttu-id="33b98-169">抽出するデータを検索するのに十分な情報が説明にない場合、各ファイルには**不一致**というラベルが付けられます。</span><span class="sxs-lookup"><span data-stu-id="33b98-169">If the explanation does not have enough information to find the data you want to extract, each file will be labeled with **Mismatch**.</span></span> <span data-ttu-id="33b98-170">不一致ファイルをクリックして、不一致が発生した理由に関する詳細情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="33b98-170">You can click on the Mismatched files to see more information about why there was a mismatch.</span></span>


## <a name="add-another-explanation"></a><span data-ttu-id="33b98-171">別の説明を追加する</span><span class="sxs-lookup"><span data-stu-id="33b98-171">Add another explanation</span></span>

<span data-ttu-id="33b98-172">多くの場合、不一致は、指定された説明には、サービスの開始日の値を抽出して、ラベル付きファイルと一致させるために十分な情報が提供されなかったことを示しています。</span><span class="sxs-lookup"><span data-stu-id="33b98-172">Often the mismatch is an indication that the explanation we provided did not provide enough information to extract the service start date value to match our labeled files.</span></span> <span data-ttu-id="33b98-173">編集または別の説明を追加する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="33b98-173">You may need to edit it, or add another explanation.</span></span>

<span data-ttu-id="33b98-174">この例では、「*サービス開始日*」というテキスト文字列は、常に実際の値よりも前になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="33b98-174">For our example, we notice that the text string *Start Service date of* always precedes the actual value.</span></span> <span data-ttu-id="33b98-175">サービスの開始日を特定するために、語句の説明を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="33b98-175">To help identify the Service Start Date we can create a phrase explanation.</span></span>

1. <span data-ttu-id="33b98-176">[説明] セクションで、[**新規**] を選択し、名前 (たとえば、*プレフィックス文字列*) を入力します。</span><span class="sxs-lookup"><span data-stu-id="33b98-176">In the Explanation section, select **New**, and then type a name (for example, *Prefix String*).</span></span>
2. <span data-ttu-id="33b98-177">[種類] で、[**語句リスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33b98-177">For the Type, select **Phrase list**.</span></span>
3. <span data-ttu-id="33b98-178">*のサービス開始日*を値として使用します。</span><span class="sxs-lookup"><span data-stu-id="33b98-178">Use *Service Start Date of* as the value.</span></span>
4. <span data-ttu-id="33b98-179">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="33b98-179">Select **Save**.</span></span>

    ![説明ライブラリ](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a><span data-ttu-id="33b98-181">モデルをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="33b98-181">Train the model</span></span>

<span data-ttu-id="33b98-182">説明を保存するとトレーニングが再度開始されます。今回は、この例の説明に従ってください。</span><span class="sxs-lookup"><span data-stu-id="33b98-182">Saving your explanation will start the training again, this time using both explanations in our example.</span></span> <span data-ttu-id="33b98-183">ラベル付けされたサンプルファイルからデータを抽出するのに十分な情報がモデルにある場合は、各ファイルに**一致**するというラベルが付いています。</span><span class="sxs-lookup"><span data-stu-id="33b98-183">If your model has enough information to extract the data from your labeled example files, you will see each file labeled with **Match**.</span></span> 

<span data-ttu-id="33b98-184">ラベル付きファイルの**不一致**を再度受信した場合は、ドキュメントの種類を識別するためにモデルに詳細情報を提供するために別の説明を作成するか、既存のファイルに変更を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="33b98-184">If you again receive a **Mismatch** on your labeled files, you may need to create another explanation to provide the model more information to identify the document type, or look at making changes to your existing ones.</span></span>

## <a name="test-your-model"></a><span data-ttu-id="33b98-185">モデルをテストする</span><span class="sxs-lookup"><span data-stu-id="33b98-185">Test your model</span></span>

<span data-ttu-id="33b98-186">ラベル付けされたサンプルファイルで一致するものを受信した場合、残りのラベルのないサンプルファイルでモデルをテストできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="33b98-186">If you received a match on your labeled example files, you can now test your model on your remaining unlabeled example files.</span></span>

1. <span data-ttu-id="33b98-187">モデルのホームページで、[**テスト**] タブをクリックします。 これにより、ラベルのないサンプルファイルでモデルが実行されます。</span><span class="sxs-lookup"><span data-stu-id="33b98-187">On the model home page, click the **Test** tab.  This will run the model on your unlabeled example files.</span></span>
2. <span data-ttu-id="33b98-188">[**テストファイル**] リストには、サンプルファイルが表示され、モデルで必要な情報を抽出できるかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="33b98-188">In the **Test files** list, your example files will display and will show if the model is able to extract the information you need from them.</span></span> <span data-ttu-id="33b98-189">この情報を使用して、ドキュメントを識別する際に、分類子の有効性を判断することができます。</span><span class="sxs-lookup"><span data-stu-id="33b98-189">You can use this information to help determine the effectiveness of your classifier in identifying your documents.</span></span>

    ![ファイルのテスト](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a><span data-ttu-id="33b98-191">関連項目</span><span class="sxs-lookup"><span data-stu-id="33b98-191">See Also</span></span>
  




