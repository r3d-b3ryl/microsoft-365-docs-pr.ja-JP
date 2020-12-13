---
title: Advanced eDiscovery での高速分析の使用
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: Advanced eDiscovery の高速分析モードを実行し、結果をエクスポートする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de637df426d38da2863a65eea67c65a3f66953a7
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663326"
---
# <a name="use-express-analysis-in-advanced-ediscovery-classic"></a><span data-ttu-id="6e6cc-103">Advanced eDiscovery での高速分析の使用 (クラシック)</span><span class="sxs-lookup"><span data-stu-id="6e6cc-103">Use Express Analysis in Advanced eDiscovery (classic)</span></span> 

> [!NOTE]
> <span data-ttu-id="6e6cc-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="6e6cc-106">高速分析を **使用すると、** ケースをすばやく分析し、結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-106">You can use **Express analysis** to quickly analyze a case and export the results.</span></span> 
  
<span data-ttu-id="6e6cc-107">高速分析を使用すると、ほぼ重複しているスレッドと電子メール スレッドを計算し、テーマを計算できます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-107">You can use express analysis to calculate near-duplicates and email threads and calculate themes.</span></span> <span data-ttu-id="6e6cc-108">また、高速分析の詳細設定で、テーマ、ドキュメントの類似性、およびエクスポート ファイルの [特定のパラメーターを設定することもできます](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings)。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-108">You can also set certain parameters for themes, document similarity and the export files in the [Advanced settings for Express analysis](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).</span></span>
  
## <a name="run-express-analysis"></a><span data-ttu-id="6e6cc-109">高速分析の実行</span><span class="sxs-lookup"><span data-stu-id="6e6cc-109">Run Express analysis</span></span>

1. <span data-ttu-id="6e6cc-110">In the **Express analysis** (1) tab, select a container to enable the \*\* Express analysis \*\* (2), and **Advanced settings** buttons.</span><span class="sxs-lookup"><span data-stu-id="6e6cc-110">In the **Express analysis** (1) tab, select a container to enable the \*\* Express analysis \*\* (2), and **Advanced settings** buttons.</span></span> 
    
    ![[高速分析] ページのスクリーンショット](../media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. <span data-ttu-id="6e6cc-112">[**分析] パラメーターの下:**</span><span class="sxs-lookup"><span data-stu-id="6e6cc-112">Under **Analyze parameters**:</span></span>
    
  - <span data-ttu-id="6e6cc-113">分析 **を実行する場合は、[近重複** データとメール スレッドの計算] チェック ボックスをオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-113">Check **Calculate near-duplicates and email threads** if you want to run the analysis.</span></span> <span data-ttu-id="6e6cc-114">既定では選択されています。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-114">It is selected by default.</span></span> 
    
  - <span data-ttu-id="6e6cc-115">[テーマ **の計算] チェック** ボックスをオンにし、すべてのファイルを処理し、テーマを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-115">Check **Calculate Themes** to process all files and assign themes to them.</span></span> <span data-ttu-id="6e6cc-116">既定では選択されています。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-116">It is selected by default.</span></span> 
    
3. <span data-ttu-id="6e6cc-117">エクスポート **先の下**:</span><span class="sxs-lookup"><span data-stu-id="6e6cc-117">Under **Export destination**:</span></span>
    
  - <span data-ttu-id="6e6cc-118">[ **ローカル コンピューターにダウンロード] をオン** にし、ローカル コンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-118">Check **Download to local machine** to download to your local computer.</span></span> 
    
  - <span data-ttu-id="6e6cc-119">[ユーザー定義 **の Azure BLOB への** エクスポート] チェック ボックスをオンにした場合は、コンテナー URL と SAS トークンを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-119">If you check **Export to user-defined Azure blob** then you can also specify a container URL and SAS token.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="6e6cc-120">エクスポート パッケージをユーザー定義の Azure BLOB に保存すると、データは Advanced eDiscovery によって管理されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-120">Once an export package is stored to the user defined Azure blob, the data is no longer managed by Advanced eDiscovery.</span></span> <span data-ttu-id="6e6cc-121">Azure BLOB によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-121">it is managed by the Azure blob.</span></span> <span data-ttu-id="6e6cc-122">つまり、ケースを削除しても、エクスポートされたファイルは Azure BLOB に残ります。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-122">This means if you delete the case, the exported files will still remain on the Azure blob.</span></span> 
  
  - <span data-ttu-id="6e6cc-123">**将来のエクスポート セッション** 用に SAS トークンを保存する : チェックされている場合、SAS トークンは将来使用するために Advanced eDiscovery の内部データベースで暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-123">**Save SAS token for future export session**: If checked, the SAS token will be encrypted in the Advanced eDiscovery's internal database for future use.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6e6cc-124">現在、SAS トークンの有効期限は 1 か月後です。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-124">Currently the SAS token expires after a month.</span></span> <span data-ttu-id="6e6cc-125">1 か月以上後にダウンロードする場合は、最後のセッションを元に戻す必要があります。その後、もう一度エクスポートします。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-125">If you try to download after more than a month you have to undo last session, then export again.</span></span> 
  
4. <span data-ttu-id="6e6cc-126">既定の設定で高速分析を開始するには、[高速分析] を選択すると、[タスクの状態]**ページが** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-126">To start the express analysis with default settings, choose **Express analysis**, and the **Task status** page will display</span></span> 
    
    <span data-ttu-id="6e6cc-127">[タスクの **状態]** ページで、[プロセス]、[分析]、および [エクスポート] タブを展開して、高速実行に関する詳細を表示できます。 </span><span class="sxs-lookup"><span data-stu-id="6e6cc-127">On the **Task status** page you can expand the **Process**, **Analyze** and **Export** tabs to display details about the express run.</span></span> 
    
    ![Advanced eDiscovery Express 分析タスクの状態ページのスクリーンショット](../media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. <span data-ttu-id="6e6cc-129">[高速分析 **の概要] ページを選択** して、実行に関する詳細情報を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-129">Choose the **Express analysis summary** page to list detailed information about the run.</span></span> 
    
    <span data-ttu-id="6e6cc-130">[高速分析の概要] ページの下部にある[最後のセッションのダウンロード] を選択し、ローカル コンピューターから分析ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-130">On the bottom of the **Express analysis summary** page, choose **Download last session** to download the analysis files tp your local computer.</span></span> <span data-ttu-id="6e6cc-131">まず、電子情報開示のエクスポート ツールをダウンロードし、電子情報開示のエクスポート ツールにエクスポート キーを貼り付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-131">You will first have to download eDiscovery Export tool and paste the Export key to the eDiscovery Export tool.</span></span> 
    
## <a name="advanced-settings-for-express-analysis"></a><span data-ttu-id="6e6cc-132">高速分析の詳細設定</span><span class="sxs-lookup"><span data-stu-id="6e6cc-132">Advanced settings for Express analysis</span></span>
<span data-ttu-id="6e6cc-133"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="6e6cc-133"><a name="BK_AdvancedSettings"> </a></span></span>

<span data-ttu-id="6e6cc-134">必要に応じて、[詳細設定] **を設定して** 、既定の高速分析パラメーターを変更できます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-134">You can optionally set **Advanced settings** to change the default Express analysis parameters.</span></span> 
  
1. <span data-ttu-id="6e6cc-135">[分析] セクションで、次の **情報を** 確認します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-135">In the **Analyze** section:</span></span> 
    
  - <span data-ttu-id="6e6cc-136">[近 **くの重複] と [電子メール** のスレッド] で、[ **ドキュメント** の類似性] の値を入力するか、既定値の 65% を受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-136">In the **Near duplicates and email threads**, enter the **Document similarity** value, or accept the default of 65%.</span></span> 
    
  - <span data-ttu-id="6e6cc-137">[最大 **テーマ数] で** 、作成するテーマの数の値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-137">In the **Max number of themes** enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="6e6cc-138">既定値は 200 です。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-138">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="6e6cc-139">テーマの数を増やすと、パフォーマンスに影響を与えるだけでなく、テーマを一般化する機能にも影響します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-139">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="6e6cc-140">テーマの数が多いほど、細かく設定できます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-140">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="6e6cc-141">たとえば、一連の 50 のテーマに 「バスケス、ボールズ、クリッパー、レイカー」などのテーマが含まれる場合です。300 のテーマには、"1 つのテーマ"、"Clippers"、"Lakers" が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-141">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="6e6cc-142">ECA に対してこの機能を使用する場合は、"バスケト" というテーマを認識する必要がない場合に役立つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-142">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="6e6cc-143">ただし、処理のテーマが多すぎる場合は、"バスケ" という単語が表示されない可能性があります。また、ブートしてヘアに使用されるアイテムではなく、スクリッパーとクリッパーがレビューに優れたバスケト テーマであるというのを知らない場合があります。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-143">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
  - <span data-ttu-id="6e6cc-144">[候補テーマ **] で[変更]** **を** 選択し、テーマの処理を制御するテーマの単語を提案します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-144">In the **Suggested themes** choose **Modify** to suggest theme words to control Themes processing.</span></span> <span data-ttu-id="6e6cc-145">Advanced eDiscovery は、これらの推奨される単語に焦点を当て、"テーマの最大数" 設定に基づいて、1 つ以上の関連するテーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-145">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="6e6cc-146">たとえば、候補の単語が "computer" で、"2" を "最大テーマ数" として指定した場合、Advanced eDiscovery は単語 "computer" に関連する 2 つのテーマの生成を試みる。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-146">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="6e6cc-147">たとえば、"コンピューター ソフトウェア" と "コンピューター ハードウェア" という 2 つのテーマがあります。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-147">The two themes might be "computer software" and "computer hardware", for example.</span></span>
    
    ![提示されたテーマの追加](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - <span data-ttu-id="6e6cc-149">**モード** ドロップダウン リストからテーマ オプションを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-149">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="6e6cc-150">**モデルの作成と適用**: ファイルのセグメントからモデル別にテーマを計算し、その間でファイルを配布します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-150">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="6e6cc-151">**モデルの** 作成 : ファイルのセグメントからテーマ モデルを計算します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-151">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="6e6cc-152">ファイルを分割する適用プロセスは、別の時点で個別に実行されます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-152">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="6e6cc-153">**モデルの** 適用 : このオプションは、モデルが以前に作成され、まだ適用されていない場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-153">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="6e6cc-154">これにより、テーマに基づいてファイルが分割されます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-154">This will divide the files based on the themes.</span></span>
    
2. <span data-ttu-id="6e6cc-155">[エクスポート] セクションで、次 **の情報を** 確認します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-155">In the **Export** section:</span></span> 
    
1. <span data-ttu-id="6e6cc-156">[エクスポート **バッチの選択] で、次の操作を行います**。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-156">In the **Select export batch**:</span></span>
    
  - <span data-ttu-id="6e6cc-157">[バッチ **のエクスポート] ボックス** の一覧で、バッチ名を選択するか、結果をエクスポート バッチ 01 (既定のバッチ) にエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-157">From the **Export batch** list, select the batch name or export results to Export batch 01, (the default batch).</span></span> 
    
  - <span data-ttu-id="6e6cc-158">既存のケースに追加した新しいファイルの結果をエクスポートするには、現在のバッチを続行します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-158">To export results for new files that you added to an existing case, continue with your current batch.</span></span> <span data-ttu-id="6e6cc-159">バッチでセッションを作成するには、同じバッチ番号を選択し、[エクスポート セッションの作成] をクリックします。このオプションを使用すると、前のバッチと同じパラメーターを増分形式でエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-159">To create a session in the batch, select the same batch number and click **Create export session** You can use this option to export the same parameters as the previous batch, in an incremental manner.</span></span> 
    
  - <span data-ttu-id="6e6cc-160">新しいバッチにエクスポートするには、[追加] アイコンをクリックし、バッチ名に新しい名前を入力 (または既定の名前を受け入れる) と、Batch の説明に説明 ![ ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) **を入力します**。 </span><span class="sxs-lookup"><span data-stu-id="6e6cc-160">To export to a new batch, click **Add** ![add icon](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) and enter a new name in **Batch name** (or accept the default) and a description in **Batch description**.</span></span> <span data-ttu-id="6e6cc-161">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-161">Click **OK**.</span></span>
    
  - <span data-ttu-id="6e6cc-162">バッチ名または説明を編集するには、エクスポート バッチで名前を選択し、[編集] アイコンをクリックして、 ![ ](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png) フィールドを変更します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-162">To edit a batch name or description, select the name in **Export batch**, click **Edit** ![Edit icon](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png), and then modify the fields.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6e6cc-163">エクスポート バッチのセッションを実行した後は、削除できません。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-163">After you've run sessions for an export batch, they cannot be deleted.</span></span> <span data-ttu-id="6e6cc-164">また、最初のセッションが実行された後は、一部のパラメーターのみを編集できます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-164">In addition, only some parameters can be edited once the first session is run.</span></span> 
  
  - <span data-ttu-id="6e6cc-165">重複するエクスポート バッチを作成するには、[重複するエクスポート バッチ] を選択して、重複するエクスポート バッチ アイコンを作成し、パネルに重複するバッチの名前と説明 ![ ](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-165">To create a duplicate export batch, choose **Duplicate export batch** ![Create a duplicate export batch icon](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) and enter a name and a description for the duplicate batch in the panel.</span></span> 
    
  - <span data-ttu-id="6e6cc-166">エクスポート バッチを削除するには、[エクスポート バッチの **削除**] ![ アイコンを選択します ](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg) 。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-166">To delete an export batch, choose **Delete** ![Delete an export batch icon](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg).</span></span>
    
  - <span data-ttu-id="6e6cc-167">バッチの履歴を表示するには、[バッチ履歴の表示 **履歴**] ![ アイコンを選択します ](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg) 。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-167">To view the history of a batch, choose **Batch history** ![View history icon](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg).</span></span>
    
2. <span data-ttu-id="6e6cc-168">[処理の定義 **]:** エクスポートバッチの設定を微調整する場合は、[関連カットオフスコアの上のファイルのみを含める] または [エクスポート バッチの絞り込み] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-168">Under Define p **opulation:** Select **Include only files above Relevance cut-off score** and/or **Refine export batch** if you want to fine-tune the settings for your export batch.</span></span> <span data-ttu-id="6e6cc-169">[関連度カットオフ スコアより上のファイルのみを含める]を選択すると、問題が有効になります。選択した問題のカットオフ スコアよりもファイルの関連性スコアが高い場合は、ファイルがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-169">If you select **Include only files above Relevance cut-off score**, then the **Issue** is enabled, and if the file's relevance score is higher than the cut-off score for the selected issue, then the file is exported.</span></span> <span data-ttu-id="6e6cc-170">[レビュー用] フィルターによって除外されていない限り、ファイル **はエクスポート** されます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-170">The file will be exported unless it's excluded by the ' **For review** filter.</span></span> <span data-ttu-id="6e6cc-171">[エクスポート バッチの **絞** り込み] を選択した場合、[レビュー用] フィールドのラジオ ボタンで **De-dupe** と **Filter** を有効にします。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-171">If you select **Refine export batch**, then the **De-dupe** and **Filter by 'For review' field** radio buttons are enabled.</span></span> <span data-ttu-id="6e6cc-172">**De-dupe** を選択すると、定義されているポリシーに従って重複するファイルがフィルター処理されます。[ケース レベル (既定): 大文字と小文字を区別して重複するファイルのすべてのセットから、1 つのファイルを含むすべてのファイルが重複排除されます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-172">If you choose **De-dupe**, then duplicates files will be filtered-out according to the policy defined: [Case level (default): from every set of duplicate files in the entire case, all but one file will be de-duped.</span></span> <span data-ttu-id="6e6cc-173">保管担当者レベル: 同じ保管担当者の重複するファイルのすべてのセットから、1 つのファイルを含むすべてのファイルが重複を排除します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-173">Custodian level: from every set of duplicate files of the same custodian, all but one file will be de-duped.</span></span> <span data-ttu-id="6e6cc-174">すべての重複ファイルのレコードをエクスポート出力で使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-174">A record of all duplicate files is available in export output.</span></span> <span data-ttu-id="6e6cc-175">[確認用 **] フィールドでフィルターを** 選択した場合は、[メタデータ] の下の [変更] を選択して **[レビュー用]** フィールドの設定を入力します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-175">If you choose **Filter by 'For review'** field, select **Modify under Metadata** to enter your **'For review'** field settings.</span></span> <span data-ttu-id="6e6cc-176">パッケージ **コンテンツにソース ファイルを含** めるには、[入力ファイルを含める] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-176">Select **Include input files** to include source files in the package content.</span></span> <span data-ttu-id="6e6cc-177">このオプションをオフにすると、エクスポート プロセスを高速化できます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-177">You can clear this option to speed up the export process.</span></span> <span data-ttu-id="6e6cc-178">ネイティブ ファイルは、いずれにしてもエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-178">Note that the Native files will be exported in any case.</span></span>
    
3. <span data-ttu-id="6e6cc-179">[**メタデータの定義]** で、[エクスポート テンプレート] ボックスの一覧から次のオプションを選択します (セッションごとに 1 回)。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-179">Under **Define metadata**, select from the following options in the **Export template** list (once per session).</span></span> 
    
  - <span data-ttu-id="6e6cc-180">**標準**: データ項目、メタデータ、およびプロパティの基本セット。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-180">**Standard**: Basic set of data items, metadata, and properties.</span></span> <span data-ttu-id="6e6cc-181">このオプションは、インポート データが Advanced eDiscovery で既に処理され、エクスポート データがファイルが既に含まれているシステムにアップロードされる場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-181">Use this option when import data was already processed in Advanced eDiscovery and export data is uploaded to a system that already contains the files.</span></span> <span data-ttu-id="6e6cc-182">既定では、エクスポート テンプレート列が作成され、設定されます。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-182">By default, export template columns are created and filled.</span></span>
    
  - <span data-ttu-id="6e6cc-183">**すべて**: すべての処理データ、分析スコア、関連性スコアを含む標準メタデータの完全なセット。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-183">**All**: Full set of standard metadata including all processing data, as well as Analyze and Relevance scores.</span></span> <span data-ttu-id="6e6cc-184">このテンプレートは、Advanced eDiscovery が処理を実行し、ファイル データが初めて外部システムにアップロードされる場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-184">This template is required when Advanced eDiscovery performs the processing and file data is uploaded to an external system for the first time.</span></span>
    
  - <span data-ttu-id="6e6cc-185">**問題 :**[ **すべての問題] を選択するか** 、作成した特定の問題を選択します。</span><span class="sxs-lookup"><span data-stu-id="6e6cc-185">**Issues**: Select **All Issues** or select a particular issue you have created.</span></span> 
    
<span data-ttu-id="6e6cc-186">[OK] を選択して詳細設定を保存し、既定値を使用して既定値を復元するか、[キャンセル] を選択して詳細設定の設定を取り消します。 </span><span class="sxs-lookup"><span data-stu-id="6e6cc-186">Choose **OK** to save the advanced settings, **Restore defaults** to use default values, or **Cancel** to cancel setting the advanced settings.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="6e6cc-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e6cc-187">See also</span></span>
<span data-ttu-id="6e6cc-188"><a name="BK_AdvancedSettings"> </a></span><span class="sxs-lookup"><span data-stu-id="6e6cc-188"><a name="BK_AdvancedSettings"> </a></span></span>

[<span data-ttu-id="6e6cc-189">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="6e6cc-189">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)

