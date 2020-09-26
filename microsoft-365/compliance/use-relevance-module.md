---
title: 適合性モジュールを使用して証拠でデータを分析する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 関連性ワークフローについての説明と、データ調査 (プレビュー) でのトレーニング手順について、関連性のモジュールが証拠のデータを分析する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fcfe651402b123ac6ec918c4c8a7170c78e78bd3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286073"
---
# <a name="use-the-relevance-module-to-analyze-data-in-evidence"></a><span data-ttu-id="6d771-103">適合性モジュールを使用して証拠でデータを分析する</span><span class="sxs-lookup"><span data-stu-id="6d771-103">Use the Relevance module to analyze data in evidence</span></span>

<span data-ttu-id="6d771-104">データ調査 (プレビュー) で、関連性モジュールには、調査に関連するファイルの関連性トレーニングとレビューが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6d771-104">In Data Investigations (preview), the Relevance module includes the Relevance training and review of files related to an investigation.</span></span> <span data-ttu-id="6d771-105">関連性ワークフローが表示され、次のように説明されています。</span><span class="sxs-lookup"><span data-stu-id="6d771-105">The Relevance workflow is shown and described as follows:</span></span>
  
![関連性のワークフロー](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="6d771-107">**評価と追跡のサイクル**:</span><span class="sxs-lookup"><span data-stu-id="6d771-107">**Cycles of assessment and tracking**:</span></span>

  - <span data-ttu-id="6d771-108">**評価**: ファイルのランダムなサンプルに基づく早期評価を有効にし、この評価を使用して、予測コーディングプロセスのパフォーマンスを判断するための決定を適用します。</span><span class="sxs-lookup"><span data-stu-id="6d771-108">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 

  - <span data-ttu-id="6d771-109">**Track**: 評価の中間結果を計算して表示し、プロセスの統計的な有効性を監視します。</span><span class="sxs-lookup"><span data-stu-id="6d771-109">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 

- <span data-ttu-id="6d771-110">**トレーニングと追跡のサイクル**</span><span class="sxs-lookup"><span data-stu-id="6d771-110">**Cycles of training and tracking**</span></span>

  - <span data-ttu-id="6d771-111">**タグ**: データ調査 (プレビュー) は、専門家による個々のファイルの反復的なレビューとタグ付けに基づいて、各問題に固有の関連性基準を学習します。</span><span class="sxs-lookup"><span data-stu-id="6d771-111">**Tag**: Data Investigations (preview) learns the Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="6d771-112">**追跡**: プロセスの統計的な有効性を監視しながら、関連性トレーニングの一時的な結果を計算して表示します。</span><span class="sxs-lookup"><span data-stu-id="6d771-112">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="6d771-113">**バッチ計算**: 累積および学習した関連性の条件がファイルコレクション全体に適用され、各ファイルに対して関連性スコアが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6d771-113">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="6d771-114">**決定**: バッチ計算の後にケース全体に適用される分析の結果が表示され、ドキュメントのレビューの決定に使用されるデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d771-114">**Decide**: The results of the analysis applied to the entire case are displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="6d771-115">**テスト**: 結果をテストして、データ調査 (プレビュー) 処理の有効性と有効性を検証することができます。</span><span class="sxs-lookup"><span data-stu-id="6d771-115">**Test**: Results can be tested to verify the validity and effectiveness of the Data Investigations (preview) processing.</span></span>

- <span data-ttu-id="6d771-116">**検索**: 関連性ワークフローが完了すると、作業セット内でクエリを実行するときに、ドキュメントの読み取りの百分位などの出力を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6d771-116">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your working set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="6d771-117">関連性のトレーニングとレビューに関するガイドライン</span><span class="sxs-lookup"><span data-stu-id="6d771-117">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="6d771-118">関連のトレーニングとレビューのガイドラインの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6d771-118">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="6d771-119">**エラーと不整合**: トレーニング中にタグ付けエラーが発生した場合は、以前のファイルサンプルに戻って修正してください。</span><span class="sxs-lookup"><span data-stu-id="6d771-119">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="6d771-120">修正するエラーが多すぎる場合や、ケースまたは問題の新しいパースペクティブがある場合は、管理者が関連性の条件を再定義して、関連性トレーニングを再開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d771-120">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="6d771-121">**タグ付けとトレーニング**:</span><span class="sxs-lookup"><span data-stu-id="6d771-121">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="6d771-122">ファイルは、コンテンツのみに基づいてタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d771-122">Files should be tagged based on content only.</span></span> <span data-ttu-id="6d771-123">保管担当者、日付、ファイルパスなどのメタデータは考慮しません。</span><span class="sxs-lookup"><span data-stu-id="6d771-123">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="6d771-124">ファイルにタグ付けするときに、テキストに日付範囲が表示されないようにします。</span><span class="sxs-lookup"><span data-stu-id="6d771-124">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="6d771-125">ファイルへのタグ付け時に埋め込まれた画像を考慮しません。</span><span class="sxs-lookup"><span data-stu-id="6d771-125">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="6d771-126">[無視] 関連性に適用されたテキストは、[関連性] のテキストビューに表示されているファイルの内容から削除されます。</span><span class="sxs-lookup"><span data-stu-id="6d771-126">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="6d771-127">関連性トレーニングが既に開始された後に、Ignore text の値が定義されていた場合、新しい無視されたテキストは、定義された時点から作成されたサンプルファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6d771-127">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="6d771-128">ファイル分析のパフォーマンスが低下する可能性があるため、[テキストを無視する] 機能は慎重に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d771-128">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="6d771-129">[ **タグをスキップ** する] オプションは必要な場合にのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="6d771-129">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="6d771-130">データ調査 (プレビュー) は、スキップされたファイルに基づいてトレーニングを行いません。</span><span class="sxs-lookup"><span data-stu-id="6d771-130">Data Investigations (preview) doesn't train based on skipped files.</span></span> <span data-ttu-id="6d771-131">評価では、ファイルが関連しているかどうかを判断するのが難しい場合は、 **Skip**を選択するのではなく、可能な限り、関連性のある (R) または関連していない (NR) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6d771-131">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="6d771-132">データ調査 (プレビュー) でトレーニングを評価すると、これらの種類のファイルがどのように処理されたかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="6d771-132">When Data Investigations (preview) evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="6d771-133">抽出されたテキストが少量のファイルでも、可能な場合には "Skip" ではなく、R/NR としてのトレーニングでタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d771-133">Even files with a small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="6d771-134">タグ付けは、ファイルが読みやすく、R/NR としてタグ付けできる限り、分類子に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6d771-134">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="6d771-135">[ **タグ** ] タブの表示されているサンプルファイルの一覧のファイルシーケンス番号を使用すると、ユーザーは、表示されている元のファイルの順序に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="6d771-135">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="6d771-136">すべてのサンプルに戻って、評価およびトレーニングセットファイルのタグ付けを変更できます。</span><span class="sxs-lookup"><span data-stu-id="6d771-136">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="6d771-137">変更は、次のサンプルを作成するときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6d771-137">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="6d771-138">PDF 形式でスキャンした Excel ファイルは、ファイルにタグ付けするときに、ネイティブの Excel ファイルと同じように処理されます。</span><span class="sxs-lookup"><span data-stu-id="6d771-138">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="6d771-139">ファイルの関連性のタグ付けに関して疑わしい場合は、専門家に相談してください。</span><span class="sxs-lookup"><span data-stu-id="6d771-139">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="6d771-140">関連性トレーニング中に誤ったタグ付けを行うと、プロセスの後期に時間が失われることがあり、結果全体の品質に悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6d771-140">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="6d771-141">キーワードリストで定義されたキーワードは、タグ付け中にユーザーが関連ファイルを識別するのに役立つ色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d771-141">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="6d771-142">**バッチ計算**: 専門家による R/NR としてタグ付けされたファイルのスコアは0または100のいずれかとなります。</span><span class="sxs-lookup"><span data-stu-id="6d771-142">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="6d771-143">これは、バッチ計算前に行われるタグ付けに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6d771-143">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="6d771-144">上級者が一括計算した後に問題をアイドルに切り替えて、この問題のタグ付けを続行した場合、新しくタグ付けされたスコアは100/0 にならず、元のスコアになります。</span><span class="sxs-lookup"><span data-stu-id="6d771-144">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="6d771-145">**問題とサンプリングモード**: 操作が完了すると、問題が発生し、問題が取り消されたとき、または別のユーザーが問題に対処しているときに、問題がオフになります。</span><span class="sxs-lookup"><span data-stu-id="6d771-145">**Issues and sampling mode**: Issues are turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="6d771-146">関連性トレーニングの手順</span><span class="sxs-lookup"><span data-stu-id="6d771-146">Steps in Relevance training</span></span>

<span data-ttu-id="6d771-147">[ **関連性の \> 追跡** ] タブでは、データ調査で、処理を進める方法に関する推奨事項が提供されます。次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6d771-147">In the **Relevance \> Track** tab, Data investigations provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="6d771-148">関連トレーニングプロセスで以下の各手順を実行する場合は、次に示す影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="6d771-148">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="6d771-149">タグ付け/続行のタグ付け: サンプル内のファイルと問題について、エキスパートによってファイルのレビューと関連性のタグ付けが実行されます。</span><span class="sxs-lookup"><span data-stu-id="6d771-149">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="6d771-150">暗黙: 既存のサンプルは、タグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d771-150">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="6d771-151">評価/続行評価: ケース上の問題の関連性と、現在のケースに対してインポートされたファイルの作成の関連性を事前に検証できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6d771-151">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="6d771-152">暗示: より多くの評価が必要または推奨されています。</span><span class="sxs-lookup"><span data-stu-id="6d771-152">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="6d771-153">トレーニング/続行トレーニング: データ調査がファイルサンプルにタグ付けする専門家から情報を取得するプロセス。また、各案件のコンテキスト内で各問題に関連する関連性基準を特定する機能を取得します。</span><span class="sxs-lookup"><span data-stu-id="6d771-153">Training / Continue training: Process during which Data investigations learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="6d771-154">意味: 問題により多くのトレーニングが必要になります。次のサンプルを作成し、タグを付ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d771-154">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="6d771-155">バッチ計算: データ調査がトレーニング段階で取得されたナレッジを取得し、ファイルの作成全体に適用する関連性プロセス。</span><span class="sxs-lookup"><span data-stu-id="6d771-155">Batch calculation: Relevance process in which Data investigations take the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="6d771-156">関連するファイルグループ内のすべてのファイルに関連性があることが評価され、関連性スコアが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="6d771-156">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="6d771-157">意味: 問題が安定しており、バッチ計算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6d771-157">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="6d771-158">キャッチアップ: 関連性は、エキスパートが、ローリングロードシナリオで追加のファイルロードから選択されたファイルのサンプルをレビューし、タグ付けするタイミングを示します。</span><span class="sxs-lookup"><span data-stu-id="6d771-158">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="6d771-159">暗黙: 新しい読み込みが追加され、作業を続行するにはキャッチアップが必要です。</span><span class="sxs-lookup"><span data-stu-id="6d771-159">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="6d771-160">タグの不整合: プロセスは、データ調査アルゴリズムを使用して、分析に悪影響を及ぼす可能性のあるファイルのタグ付けプロセスの不整合を識別します。</span><span class="sxs-lookup"><span data-stu-id="6d771-160">Tag inconsistencies: Process identifies, via a Data investigations algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="6d771-161">意味: 次のサンプルには、前のサンプルでタグ付けされたファイルが含まれており、タグ付けをやり直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d771-161">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="6d771-162">Update クラシファイア: ユーザーがタグ付けまたはシード変更を適用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6d771-162">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="6d771-163">暗黙: 別の関連性サンプルを手動で実行しなくても、タグ付けとシードによる変更を適用できます。</span><span class="sxs-lookup"><span data-stu-id="6d771-163">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="6d771-164">保留中: 関連トレーニングプロセスが完了します。</span><span class="sxs-lookup"><span data-stu-id="6d771-164">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="6d771-165">意味: この時点では、関連性トレーニングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6d771-165">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="6d771-166">データ調査では、さまざまな段階で推奨される次の手順に従ってプロセスを進めていますが、タブとページ間を移動したり、個別のケース、問題、またはドキュメントのレビュープロセスに関係する状況に対処するための選択を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6d771-166">Although Data investigations guide you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="6d771-167">データ調査の次のステップ処理の選択を承諾または上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="6d771-167">It is possible to accept or override Data investigations Next step processing choices.</span></span> <span data-ttu-id="6d771-168">次の推奨手順以外の手順を実行する場合は、ダイアログボックスの展開された問題の表示で **次の手順** をクリックし、次の手順の横にある [ **変更** ] ボタンをクリックして、別の [次の手順] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="6d771-168">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6d771-169">一部のオプションは、プロセスのその時点で使用することがサポートされていないため、ロックを解除した後も無効になることがあります。</span><span class="sxs-lookup"><span data-stu-id="6d771-169">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="6d771-170">詳細情報</span><span class="sxs-lookup"><span data-stu-id="6d771-170">More information</span></span>

[<span data-ttu-id="6d771-171">関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="6d771-171">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6d771-172">タグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="6d771-172">Tagging and assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6d771-173">タグ付けと関連性トレーニング</span><span class="sxs-lookup"><span data-stu-id="6d771-173">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6d771-174">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="6d771-174">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6d771-175">結果に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="6d771-175">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="6d771-176">関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="6d771-176">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="6d771-177">証拠でデータを照会する</span><span class="sxs-lookup"><span data-stu-id="6d771-177">Query the data in evidence</span></span>](evidence-query.md)
