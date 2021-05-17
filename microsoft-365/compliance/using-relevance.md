---
title: 関連性モジュールを使用して、データを分析Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 関連性モジュールがエビデンスのデータを分析する方法について、関連性ワークフローとトレーニング手順の説明を参照Advanced eDiscovery。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4a05ec47a4a6b2100c062912e7668c2bf785caf7
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2020
ms.locfileid: "48286063"
---
# <a name="use-the-relevance-module-to-analyze-data-in-advanced-ediscovery"></a><span data-ttu-id="92432-103">関連性モジュールを使用して、データを分析Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="92432-103">Use the Relevance module to analyze data in Advanced eDiscovery</span></span>

<span data-ttu-id="92432-104">関連Advanced eDiscoveryには、関連性のトレーニングとケースに関連するファイルのレビューが含まれています。</span><span class="sxs-lookup"><span data-stu-id="92432-104">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="92432-105">関連性ワークフローを使用するには、[レビュー セット内のレビュー セットの管理] に移動し、[関連性の表示] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92432-105">In order to use the Relevance workflow, go to Manage review set within a review set and click on Show Relevance.</span></span> <span data-ttu-id="92432-106">ワークフローを開始する前に、いくつかの手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92432-106">There are a couple of steps you need to complete before you can start the workflow:</span></span>

- <span data-ttu-id="92432-107">プロセス: レビュー セットに追加された各負荷セットは、ここに "コンテナー" として表示されます。</span><span class="sxs-lookup"><span data-stu-id="92432-107">Process: each load set added to the review set will show up as a "container" here.</span></span> <span data-ttu-id="92432-108">これらのドキュメントを関連性モジュールに追加する前に、これらのドキュメントを処理する必要があります。これはまた、シードとしてマークするか、特定の問題に対して事前にタグ付けできる場所です。</span><span class="sxs-lookup"><span data-stu-id="92432-108">You need to process these documents before you can add them to Relevance module; this is also where you can mark them as seed or pre-tagged for a specific issue.</span></span>

- <span data-ttu-id="92432-109">関連性に追加: [関連性の読み込み] で、関連性に処理されたドキュメントを追加して、トレーニング \> に使用できます。</span><span class="sxs-lookup"><span data-stu-id="92432-109">Add to Relevance: Under Relevance \> Loads, you can add documents that have been processed to Relevance to make them available for training.</span></span>

<span data-ttu-id="92432-110">関連性ワークフローは、次のように表示および説明されます。</span><span class="sxs-lookup"><span data-stu-id="92432-110">The Relevance workflow is shown and described as follows:</span></span>
  
![関連性のワークフロー](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="92432-112">**評価と追跡のサイクル**:</span><span class="sxs-lookup"><span data-stu-id="92432-112">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="92432-113">**評価**: ファイルのランダム なサンプルに基づいて早期評価を有効にし、この評価を使用して決定を適用して予測コーディング プロセスのパフォーマンスを判断します。</span><span class="sxs-lookup"><span data-stu-id="92432-113">**Assessment**: Enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="92432-114">**追跡**: プロセスの統計的妥当性を監視しながら、評価の中間結果を計算して表示します。</span><span class="sxs-lookup"><span data-stu-id="92432-114">**Track**: Calculate and display interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="92432-115">**トレーニングと追跡のサイクル**</span><span class="sxs-lookup"><span data-stu-id="92432-115">**Cycles of training and tracking**</span></span>
    
  - <span data-ttu-id="92432-116">**タグ**: Advanced eDiscoveryの反復レビューと個々のファイルのタグ付けに基づいて、各問題に固有の関連性の基準を学習します。</span><span class="sxs-lookup"><span data-stu-id="92432-116">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="92432-117">**追跡**: プロセスの統計的妥当性を監視しながら、関連性トレーニングの中間結果を計算して表示します。</span><span class="sxs-lookup"><span data-stu-id="92432-117">**Track**: Calculate and display interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="92432-118">**バッチ計算**: 累積および学習された関連性の条件がファイル コレクション全体に適用され、ファイルごとに関連性スコアが生成されます。</span><span class="sxs-lookup"><span data-stu-id="92432-118">**Batch calculation**: The accumulated and learned Relevance criteria is applied to the entire file collection, and a Relevance score is generated for each file.</span></span>
    
- <span data-ttu-id="92432-119">**決定**: ケース全体に適用された分析の結果は、バッチ計算の後に表示され、ドキュメントレビューの決定に使用されるデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="92432-119">**Decide**: The results of the analysis applied to the entire case is displayed after Batch calculation, and data used to make document review decisions is displayed.</span></span>
    
- <span data-ttu-id="92432-120">**テスト**: 結果をテストして、処理の有効性と有効性をAdvanced eDiscoveryできます。</span><span class="sxs-lookup"><span data-stu-id="92432-120">**Test**: Results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>

- <span data-ttu-id="92432-121">**検索**: 関連性ワークフローが完了したら、レビュー セット内でクエリを実行するときに、問題のドキュメントの読み取りパーセントなどの出力を使用できます。</span><span class="sxs-lookup"><span data-stu-id="92432-121">**Search**: Once the Relevance workflow is complete, you can use the output such as read percentile of a document for your issue when you run a query within your review set.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="92432-122">関連性のトレーニングとレビューのガイドライン</span><span class="sxs-lookup"><span data-stu-id="92432-122">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="92432-123">関連性のトレーニングとレビューのガイドラインの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="92432-123">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="92432-124">**エラーと不整合**: トレーニング中にタグ付けエラーが発生した場合は、以前のファイル サンプルに戻って修正します。</span><span class="sxs-lookup"><span data-stu-id="92432-124">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="92432-125">修正するエラーが多すぎる場合、またはケースまたは問題に関する新しい視点がある場合は、関連性の基準を管理者によって再定義し、関連性トレーニングを再開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="92432-125">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="92432-126">**タグ付けとトレーニング**:</span><span class="sxs-lookup"><span data-stu-id="92432-126">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="92432-127">ファイルは、コンテンツにのみ基づいてタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92432-127">Files should be tagged based on content only.</span></span> <span data-ttu-id="92432-128">保管担当者、日付、ファイル パスなどのメタデータは考慮しない。</span><span class="sxs-lookup"><span data-stu-id="92432-128">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="92432-129">ファイルにタグを付ける場合は、テキスト内の日付範囲の表示は考慮しない。</span><span class="sxs-lookup"><span data-stu-id="92432-129">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="92432-130">ファイルにタグを付ける場合は、埋め込みグラフィカル イメージは考慮されません。</span><span class="sxs-lookup"><span data-stu-id="92432-130">Do not consider embedded graphical images when tagging files.</span></span>
     
  - <span data-ttu-id="92432-131">関連性に適用されるテキストを無視すると、[関連性] のテキスト ビューに表示されるファイル コンテンツが削除されます。</span><span class="sxs-lookup"><span data-stu-id="92432-131">Ignore text applied to Relevance will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="92432-132">関連性トレーニングが既に開始された後にテキストを無視する値が定義されている場合、新しい無視されたテキストは、定義されたポイントから作成されたサンプル ファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="92432-132">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="92432-133">テキストの無視機能は、ファイル分析のパフォーマンスを低下させる可能性があるので、慎重に使用する必要があります</span><span class="sxs-lookup"><span data-stu-id="92432-133">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="92432-134">[タグ付 **けをスキップする] オプション** は、必要な場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="92432-134">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="92432-135">Advanced eDiscoveryは、スキップされたファイルに基づいてトレーニングされません。</span><span class="sxs-lookup"><span data-stu-id="92432-135">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="92432-136">評価では、ファイルが関連するかどうかを判断できない場合は、[スキップ] を選択するのではなく、可能な限り関連 (R) または関連性の低い (NR) としてタグ付けする方が良 **いです**。</span><span class="sxs-lookup"><span data-stu-id="92432-136">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="92432-137">トレーニングAdvanced eDiscovery評価すると、これらの種類のファイルがどのレベルで処理されたのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="92432-137">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="92432-138">抽出されたテキストの量が非常に少ないファイルでも、可能な場合は"Skip"ではなく、R/NR としてトレーニングでタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92432-138">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="92432-139">タグ付けは、ファイルが読み取り可能で、R/NR としてタグ付けできる限り、分類子に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92432-139">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="92432-140">[タグ] タブに表示される [サンプルファイル] リストのファイル シーケンス番号を使用すると、ユーザーはファイルの元の表示順序に戻る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92432-140">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="92432-141">任意のサンプルに戻り、評価およびトレーニング セット ファイルのタグ付けを変更できます。</span><span class="sxs-lookup"><span data-stu-id="92432-141">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="92432-142">変更は、次のサンプルを作成するときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="92432-142">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="92432-143">PDF 形式Excelスキャンされたファイルは、ファイルのタグ付け時にネイティブ ファイルExcel扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="92432-143">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="92432-144">ファイルの関連性のタグ付けに疑問がある場合は、専門家に相談してください。</span><span class="sxs-lookup"><span data-stu-id="92432-144">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="92432-145">関連性トレーニング中のタグ付けが正しくないと、プロセスの後半で時間が失われる可能性があります。また、全体的な結果の品質に悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="92432-145">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="92432-146">キーワード リストで定義されたキーワードは、タグ付け中に関連するファイルを識別するのに役立つ色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="92432-146">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="92432-147">**バッチ計算**: エキスパートによって R/NR としてタグ付けされたファイルには、0 または 100 のスコアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="92432-147">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="92432-148">これは、バッチ計算の前に行われたタグ付けに適用されます。</span><span class="sxs-lookup"><span data-stu-id="92432-148">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="92432-149">専門家がバッチ計算後に問題をアイドル状態に切り替えて、この問題のタグ付けを続けた場合、新しくタグ付けされたスコアは 100/0 ではなく、元のスコアになります。</span><span class="sxs-lookup"><span data-stu-id="92432-149">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="92432-150">**問題** とサンプリング モード : 通常、問題の作業が完了するとオフになります (関連性トレーニングが安定し、バッチ計算が実行されました)、問題が取り消された場合、または別のユーザーが問題に取り組む場合。</span><span class="sxs-lookup"><span data-stu-id="92432-150">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="92432-151">関連性トレーニングの手順</span><span class="sxs-lookup"><span data-stu-id="92432-151">Steps in Relevance training</span></span>

<span data-ttu-id="92432-152">[関連性 **の追跡 \> ]** タブでAdvanced eDiscovery手順に関する推奨事項が表示されます。次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="92432-152">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="92432-153">以下に、関連性トレーニング プロセスで次の各手順を推奨する場合の意味について説明します。</span><span class="sxs-lookup"><span data-stu-id="92432-153">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="92432-154">タグ付け/タグ付けの続行: サンプル内のファイルと問題ごとに専門家が実行するファイルレビューと関連性のタグ付け。</span><span class="sxs-lookup"><span data-stu-id="92432-154">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="92432-155">意味: 既存のサンプルにタグを付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92432-155">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="92432-156">評価/継続評価: ケースの問題の関連性の早期検証と、現在のケースにインポートされたファイルの母集団の関連性の予備的なビューを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="92432-156">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="92432-157">意味: より多くの評価が必要または推奨されます。</span><span class="sxs-lookup"><span data-stu-id="92432-157">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="92432-158">トレーニング/トレーニングの継続: Advanced eDiscovery がファイル サンプルにタグを付ける専門家から学習し、各ケースのコンテキスト内の各問題に関連する関連性の基準を特定する機能を取得するプロセス。</span><span class="sxs-lookup"><span data-stu-id="92432-158">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="92432-159">意味: この問題には、より多くのトレーニングが必要です。次のサンプルを作成してタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="92432-159">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="92432-160">バッチ計算: トレーニング段階でAdvanced eDiscovery知識を取得し、ファイルの母集団全体に適用する関連性プロセス。</span><span class="sxs-lookup"><span data-stu-id="92432-160">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="92432-161">関連するファイル グループ内のすべてのファイルが関連性について評価され、関連性スコアが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="92432-161">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="92432-162">意味: 問題が安定し、バッチ計算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="92432-162">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="92432-163">キャッチアップ: 関連性は、ローリング ロード シナリオ中に、追加のファイル読み込みから選択されたファイルのサンプルを専門家がレビューしてタグ付けする場合を示します。</span><span class="sxs-lookup"><span data-stu-id="92432-163">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="92432-164">意味: 新しい負荷が追加され、作業を続けるにはキャッチアップが必要です。</span><span class="sxs-lookup"><span data-stu-id="92432-164">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="92432-165">タグの不整合: プロセスは、Advanced eDiscoveryアルゴリズムを使用して、分析に悪影響を及ぼす可能性があるファイルタグ付けプロセスの不整合を識別します。</span><span class="sxs-lookup"><span data-stu-id="92432-165">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="92432-166">意味: 次のサンプルには、以前のサンプルでタグ付けされたファイルが含まれます。タグ付けをやり直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="92432-166">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="92432-167">分類子の更新: ユーザーがタグ付けまたはシードの変更を適用できます。</span><span class="sxs-lookup"><span data-stu-id="92432-167">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="92432-168">意味: タグ付けとシードの変更は、別の関連性サンプルを手動で実行する必要なく適用できます。</span><span class="sxs-lookup"><span data-stu-id="92432-168">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="92432-169">保留: 関連性のトレーニング プロセスが完了しました。</span><span class="sxs-lookup"><span data-stu-id="92432-169">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="92432-170">意味: この時点で関連性のトレーニングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="92432-170">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="92432-171">Advanced eDiscovery では、プロセスをガイドしますが、推奨される次の手順は異なる段階で行えますが、タブとページ間を移動したり、個々のケース、問題、またはドキュメントレビュー プロセスに関連する状況に対処したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="92432-171">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="92432-172">[次のステップの処理] のAdvanced eDiscoveryを受け入れるか、上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="92432-172">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="92432-173">推奨される [次へ] 以外の手順を実行する場合は、ダイアログの [展開された問題] 画面に表示されている [次の手順] をクリックし、[次へ] の横にある [変更] ボタンをクリックして、別の [次のステップ] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="92432-173">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="92432-174">一部のオプションは、ロック解除後も無効にされる場合があります。このオプションは、プロセスのその時点では使用できません。</span><span class="sxs-lookup"><span data-stu-id="92432-174">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="92432-175">詳細情報</span><span class="sxs-lookup"><span data-stu-id="92432-175">More information</span></span>

[<span data-ttu-id="92432-176">関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="92432-176">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="92432-177">タグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="92432-177">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="92432-178">タグ付けと関連性のトレーニング</span><span class="sxs-lookup"><span data-stu-id="92432-178">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="92432-179">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="92432-179">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="92432-180">結果に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="92432-180">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="92432-181">関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="92432-181">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

[<span data-ttu-id="92432-182">レビュー セット内のデータをクエリする</span><span class="sxs-lookup"><span data-stu-id="92432-182">Query the data in a review set</span></span>](review-set-search.md)
