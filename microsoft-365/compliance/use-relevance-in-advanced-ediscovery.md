---
title: Advanced eDiscovery の関連度モジュールを使用する
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
ms.assetid: 5d671821-d188-42da-a9ce-9cfe92beedfd
description: Advanced eDiscovery の関連性モジュールについて説明します。ワークフロー、ガイドライン、トレーニングおよびファイル レビューの手順が含まれます。
ms.openlocfilehash: 0319ac378fb891d96437f53931213429b111d61d
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663286"
---
# <a name="use-the-relevance-module-in-advanced-ediscovery-classic"></a><span data-ttu-id="e7a51-103">Advanced eDiscovery (クラシック) の関連モジュールを使用する</span><span class="sxs-lookup"><span data-stu-id="e7a51-103">Use the Relevance module in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="e7a51-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="e7a51-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="e7a51-106">Advanced eDiscovery では、関連度モジュールに関連トレーニングとケースに関連するファイルのレビューが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e7a51-106">In Advanced eDiscovery, the Relevance module includes the Relevance training and review of files related to a case.</span></span> <span data-ttu-id="e7a51-107">関連性ワークフローは次のように表示され、説明されます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-107">The Relevance workflow is shown and described as follows:</span></span>
  
![関連性のワークフロー](../media/44c67dd2-7a20-40a9-b0ed-784364845c77.gif)
  
- <span data-ttu-id="e7a51-109">**評価と追跡のサイクル**:</span><span class="sxs-lookup"><span data-stu-id="e7a51-109">**Cycles of assessment and tracking**:</span></span>
    
  - <span data-ttu-id="e7a51-110">**Assessment**: Advanced eDiscovery は、ファイルのランダム なサンプルに基づいて早期評価を有効にし、この評価を使用して決定を適用し、予測コーディング プロセスのパフォーマンスを判断します。</span><span class="sxs-lookup"><span data-stu-id="e7a51-110">**Assessment**: Advanced eDiscovery enables early assessment based on a random sample of files and uses this assessment to apply decisions to determine the performance of the predictive coding process.</span></span> 
    
  - <span data-ttu-id="e7a51-111">**追跡**: Advanced eDiscovery は、プロセスの統計的有効性を監視しながら、評価の中間結果を計算して表示します。</span><span class="sxs-lookup"><span data-stu-id="e7a51-111">**Track**: Advanced eDiscovery calculates and displays interim results of the assessment while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="e7a51-112">**トレーニングと追跡のサイクル**:</span><span class="sxs-lookup"><span data-stu-id="e7a51-112">**Cycles of training and tracking**:</span></span>
    
  - <span data-ttu-id="e7a51-113">**タグ**: Advanced eDiscovery は、専門家の反復的なレビューと個々のファイルのタグ付けに基づいて、各問題に固有の関連性条件を学習します。</span><span class="sxs-lookup"><span data-stu-id="e7a51-113">**Tag**: Advanced eDiscovery learns Relevance criteria specific to each issue based on the expert's iterative review and tagging of individual files.</span></span>
    
  - <span data-ttu-id="e7a51-114">**追跡**: Advanced eDiscovery は、プロセスの統計的有効性を監視しながら、関連性トレーニングの中間結果を計算して表示します。</span><span class="sxs-lookup"><span data-stu-id="e7a51-114">**Track**: Advanced eDiscovery calculates and displays interim results of the Relevance training while monitoring statistical validity of the process.</span></span> 
    
- <span data-ttu-id="e7a51-115">**バッチ計算**: Advanced eDiscovery は、蓄積および学習された関連性の条件を取得し、ファイル コレクション全体に適用して、各ファイルの関連性スコアを生成します。</span><span class="sxs-lookup"><span data-stu-id="e7a51-115">**Batch calculation**: Advanced eDiscovery takes the accumulated and learned Relevance criteria, applies it to the entire file collection, and generates Relevance scores for each file.</span></span>
    
- <span data-ttu-id="e7a51-116">**決定**: Advanced eDiscovery は、バッチ計算後にケース全体に適用された分析の結果を表示し、ドキュメント レビューの決定を行うデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="e7a51-116">**Decide**: Advanced eDiscovery displays the results of the analysis applied to the entire case after Batch calculation and displays data for making document review decisions.</span></span>
    
- <span data-ttu-id="e7a51-117">**テスト**: Advanced eDiscovery の結果をテストして、Advanced eDiscovery 処理の有効性と有効性を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-117">**Test**: Advanced eDiscovery results can be tested to verify the validity and effectiveness of the Advanced eDiscovery processing.</span></span>
    
## <a name="guidelines-for-relevance-training-and-review"></a><span data-ttu-id="e7a51-118">関連性トレーニングとレビューのガイドライン</span><span class="sxs-lookup"><span data-stu-id="e7a51-118">Guidelines for Relevance training and review</span></span>

<span data-ttu-id="e7a51-119">関連性トレーニングとレビューのガイドラインの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e7a51-119">Following is an overview of guidelines for Relevance training and review:</span></span>
  
- <span data-ttu-id="e7a51-120">**エラーと不整合**: トレーニング中にタグ付けエラーが発生した場合は、以前のファイル サンプルに戻って修正します。</span><span class="sxs-lookup"><span data-stu-id="e7a51-120">**Errors and inconsistencies**: If tagging errors are made during training, return to previous file samples to correct them.</span></span> <span data-ttu-id="e7a51-121">修正するエラーが多すぎる場合や、ケースまたは問題に関する新しい視点がある場合は、管理者によって関連性の基準を再定義し、関連性トレーニングを再開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7a51-121">If there are too many errors to correct or there is a new perspective of the case or issue, the Relevance criteria should be redefined by the Administrator, and the Relevance training restarted.</span></span>
    
- <span data-ttu-id="e7a51-122">**タグ付けとトレーニング**:</span><span class="sxs-lookup"><span data-stu-id="e7a51-122">**Tagging and training**:</span></span> 
    
  - <span data-ttu-id="e7a51-123">ファイルは、コンテンツにのみ基づいてタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7a51-123">Files should be tagged based on content only.</span></span> <span data-ttu-id="e7a51-124">保管担当者、日付、ファイル パスなどのメタデータは考慮しない。</span><span class="sxs-lookup"><span data-stu-id="e7a51-124">Do not consider metadata, such as custodian, date, or file path.</span></span> 
    
  - <span data-ttu-id="e7a51-125">ファイルにタグを付ける場合は、テキスト内の日付範囲の指示を考慮に入ねない。</span><span class="sxs-lookup"><span data-stu-id="e7a51-125">Do not consider date range indications in the text when tagging files.</span></span>
    
  - <span data-ttu-id="e7a51-126">ファイルのタグ付け時に埋め込みグラフィカルイメージを考慮しない。</span><span class="sxs-lookup"><span data-stu-id="e7a51-126">Do not consider embedded graphical images when tagging files.</span></span>
    
  - <span data-ttu-id="e7a51-127">タグ付け中に書式設定 **されたテキスト** ビュー アイコンを使用してファイルを表示する場合は、テキストの書式設定を考慮しない。</span><span class="sxs-lookup"><span data-stu-id="e7a51-127">If viewing a file using the **formatted text view** icon while tagging, do not consider the formatting of text.</span></span> <span data-ttu-id="e7a51-128">たとえば、取り消し線付きの単語 (削除を示す中央を通る水平線) は、分析されたテキストの一部として関連性によって引き続き考慮されます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-128">For example, a word displayed with a strikethrough (a horizontal line through its center indicating deletion) is still considered by Relevance as part of the analyzed text.</span></span> 
    
  - <span data-ttu-id="e7a51-129">(ケース マネージャーまたは管理者が設定した) 関連性に適用されたテキストは、[関連性] のテキスト ビューに表示されるファイル コンテンツから削除されます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-129">Ignore text applied to Relevance (as set by the Case Manager or Administrator) will be removed in the displayed file content in the text view in Relevance.</span></span> <span data-ttu-id="e7a51-130">関連度トレーニングの開始後に無視テキストの値が定義されている場合、新しい無視されたテキストは、定義されたポイントから作成されたサンプル ファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-130">If the values for Ignore text were defined after Relevance training already started, the new ignored text will be applied to sample files created from the point in which it was defined.</span></span> <span data-ttu-id="e7a51-131">テキストを無視する機能は、ファイル分析のパフォーマンスを低下させる可能性があるので、慎重に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7a51-131">The Ignore Text feature should be used cautiously, as its use may reduce the performance of file analysis</span></span>
    
  - <span data-ttu-id="e7a51-132">[タグ **付けをスキップする] オプション** は、必要な場合にのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="e7a51-132">Use the **Skip tagging** option only when necessary.</span></span> <span data-ttu-id="e7a51-133">Advanced eDiscovery は、スキップされたファイルに基づいてトレーニングを行うのではありません。</span><span class="sxs-lookup"><span data-stu-id="e7a51-133">Advanced eDiscovery does not train based on skipped files.</span></span> <span data-ttu-id="e7a51-134">評価では、ファイルが関連するかどうかを判断するのは難しい場合は、[スキップ] を選択するのではなく、可能な限り関連 (R) または Not relevant (NR) としてタグ付けする方が適切 **です。**</span><span class="sxs-lookup"><span data-stu-id="e7a51-134">In assessment, if it's hard to tell whether a file is relevant, it is better to tag as Relevant (R) or Not relevant (NR) whenever possible rather than selecting **Skip**.</span></span> <span data-ttu-id="e7a51-135">Advanced eDiscovery がトレーニングを評価すると、これらの種類のファイルがどれだけ処理されたのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-135">When Advanced eDiscovery evaluates training, it can then be seen how well these types of files were processed.</span></span>
    
  - <span data-ttu-id="e7a51-136">抽出されたテキストが非常に少ないファイルでも、可能な場合は"Skip" ではなく R/NR としてトレーニングでタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7a51-136">Even files with a very small amount of extracted text should be tagged in training as R/NR, rather than as "Skip", when possible.</span></span> 
    
  - <span data-ttu-id="e7a51-137">ファイルが読み取り可能で R/NR としてタグ付けできる限り、タグ付けは分類子に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e7a51-137">Tagging can impact the classifier as long as the file is readable and can be tagged as R/NR.</span></span>
    
  - <span data-ttu-id="e7a51-138">[タグ] タブに表示されるサンプル ファイルの一覧のファイル シーケンス番号を使用すると、ユーザーはファイルの元の表示順序に戻る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e7a51-138">The file sequence number on the displayed Sample files list on the **Tag** tab allows the user to return to the original displayed order of the files.</span></span> 
    
  - <span data-ttu-id="e7a51-139">任意のサンプルに戻り、評価およびトレーニング セット ファイルのタグ付けを変更できます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-139">You can go back to any sample and change the tagging of the assessment and training set files.</span></span> <span data-ttu-id="e7a51-140">変更は、次のサンプルを作成するときに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-140">The changes will be applied when creating the next sample.</span></span>
    
  - <span data-ttu-id="e7a51-141">PDF 形式のスキャンされた Excel ファイルは、ファイルのタグ付け時にネイティブの Excel ファイルと同じように扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7a51-141">Scanned Excel files in PDF format should be treated the same as native Excel files when tagging files.</span></span>
    
  - <span data-ttu-id="e7a51-142">ファイルの関連性のタグ付けに関して疑問がある場合は、専門家に相談してください。</span><span class="sxs-lookup"><span data-stu-id="e7a51-142">When in doubt regarding the Relevance tagging of a file, consult an expert.</span></span> <span data-ttu-id="e7a51-143">関連性トレーニング中のタグ付けが正しくないと、プロセスの後半で時間が失われる可能性があります。また、全体的な結果の品質に悪影響を及ぼす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e7a51-143">Incorrect tagging during the Relevance training can lead to lost time later in the process and may also have a negative impact on the quality of the overall results.</span></span>
    
  - <span data-ttu-id="e7a51-144">キーワード リストで定義されたキーワードは、タグ付け中にユーザーが関連ファイルを識別するのに役立つ色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-144">Keywords that were defined in Keyword lists will be displayed in colors to help the user identify relevant files while tagging.</span></span>
    
- <span data-ttu-id="e7a51-145">**バッチ計算**: エキスパートによって R/NR としてタグ付けされたファイルは、0 または 100 のスコアを受け取る。</span><span class="sxs-lookup"><span data-stu-id="e7a51-145">**Batch calculation**: Files that were tagged as R/NR by the expert will receive a score of either 0 or 100.</span></span> <span data-ttu-id="e7a51-146">これは、バッチ計算の前に行われたタグ付けに適用されます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-146">This applies to tagging made before Batch calculation.</span></span> <span data-ttu-id="e7a51-147">専門家がバッチ計算後に問題をアイドル状態に切り替え、この問題のタグ付けを続けた場合、新しくタグ付けされたスコアは 100/0 ではなく、元のスコアになります。</span><span class="sxs-lookup"><span data-stu-id="e7a51-147">If the expert switched the issue to Idle after Batch Calculation and continued tagging this issue, the newly tagged scores will not be 100/0 but rather the original score.</span></span>
    
- <span data-ttu-id="e7a51-148">**問題** とサンプリング モード : 問題は、通常、作業が完了するとオフになります (関連性トレーニングが安定し、バッチ計算が実行された場合)、問題が取り消された場合、または別のユーザーが問題に取り組む場合です。</span><span class="sxs-lookup"><span data-stu-id="e7a51-148">**Issues and sampling mode**: Issues are usually turned Off when work on them is completed (Relevance training is stabilized and Batch calculation was performed), when the issues are canceled, or when another user is working on the issues.</span></span>
    
## <a name="steps-in-relevance-training"></a><span data-ttu-id="e7a51-149">関連性トレーニングの手順</span><span class="sxs-lookup"><span data-stu-id="e7a51-149">Steps in Relevance training</span></span>

<span data-ttu-id="e7a51-150">Advanced eDiscovery は、[関連性 **\> トラック** ] タブで、次の手順に従って処理を続行する方法に関する推奨事項を提供します。</span><span class="sxs-lookup"><span data-stu-id="e7a51-150">In the **Relevance \> Track** tab, Advanced eDiscovery provides recommendations on how to proceed in the processing, with the following next steps.</span></span> <span data-ttu-id="e7a51-151">関連度トレーニング プロセスで次の各手順が推奨される場合、以下に影響について説明します。</span><span class="sxs-lookup"><span data-stu-id="e7a51-151">The implications are described below when each of the following steps is recommended in the Relevance training process.</span></span> 
  
- <span data-ttu-id="e7a51-152">タグ付け/タグ付けの続行: ファイル レビューと関連タグ付けは、サンプル内の各ファイルと問題について、専門家によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-152">Tagging / Continue tagging: File review and Relevance tagging performed by an expert for each file and issue within a sample.</span></span>
    
  - <span data-ttu-id="e7a51-153">意味: 既存のサンプルにタグを付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7a51-153">Implication: An existing sample needs to be tagged.</span></span>
    
- <span data-ttu-id="e7a51-154">評価/継続評価: ケースの問題の関連性を早期に検証し、現在のケースにインポートされたファイルの母集団の関連性を暫定的に確認できます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-154">Assessment / Continue assessment: Enables early validation of case issue relevance and a preliminary view of the relevance of the file population imported for the current case.</span></span>
    
  - <span data-ttu-id="e7a51-155">意味: より多くの評価が必要または推奨されます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-155">Implication: More assessment is required or recommended.</span></span>
    
- <span data-ttu-id="e7a51-156">トレーニング/継続トレーニング: Advanced eDiscovery がファイル サンプルにタグ付けしているエキスパートから学習し、各ケースのコンテキスト内で各問題に関連する関連性条件を識別する機能を取得するプロセス。</span><span class="sxs-lookup"><span data-stu-id="e7a51-156">Training / Continue training: Process during which Advanced eDiscovery learns from the expert who is tagging the file samples and acquires the ability to identify Relevance criteria pertinent to each issue within the context of each case.</span></span>
    
  - <span data-ttu-id="e7a51-157">意味: この問題には、より多くのトレーニングが必要です。次のサンプルを作成してタグ付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7a51-157">Implication: The issue needs more training; the next sample should be created and tagged.</span></span> 
    
- <span data-ttu-id="e7a51-158">バッチ計算: Advanced eDiscovery がトレーニング ステージで取得した知識を取得し、ファイルの母集団全体に適用する関連性プロセス。</span><span class="sxs-lookup"><span data-stu-id="e7a51-158">Batch calculation: Relevance process in which Advanced eDiscovery takes the knowledge acquired during the training stage and applies it to the entire file population.</span></span> <span data-ttu-id="e7a51-159">関連するファイル グループ内のすべてのファイルが関連性について評価され、関連性スコアが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-159">All files in the pertinent file group are assessed for relevance and assigned a Relevance score.</span></span>
    
  - <span data-ttu-id="e7a51-160">意味: 問題は安定し、バッチ計算を実行できます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-160">Implication: The issue has stabilized, and Batch calculation can be performed.</span></span>
    
- <span data-ttu-id="e7a51-161">キャッチアップ: 関連性は、ローリング ロード シナリオ中に、専門家が追加のファイル負荷から選択したファイルのサンプルをレビューしてタグ付けする場合を示します。</span><span class="sxs-lookup"><span data-stu-id="e7a51-161">Catch-up: Relevance indicates when an expert reviews and tags a sample of files selected from an additional file load during a Rolling Loads scenario.</span></span>
    
  - <span data-ttu-id="e7a51-162">意味: 新しい負荷が追加され、引き続き動作するにはキャッチアップが必要です。</span><span class="sxs-lookup"><span data-stu-id="e7a51-162">Implication: A new load has been added, and Catch-up is required to continue working.</span></span>
    
- <span data-ttu-id="e7a51-163">タグの不整合: プロセスは、Advanced eDiscovery アルゴリズムを使用して、分析に悪影響を及ぼす可能性があるファイル タグ付けプロセスの不整合を識別します。</span><span class="sxs-lookup"><span data-stu-id="e7a51-163">Tag inconsistencies: Process identifies, via an Advanced eDiscovery algorithm, inconsistencies in the file tagging process that may negatively impact the analysis.</span></span>
    
  - <span data-ttu-id="e7a51-164">意味: 次のサンプルには、前のサンプルでタグ付けされたファイルが含まれるので、タグ付けをやり直す必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7a51-164">Implication: The next sample will include files that have been tagged in previous samples, and their tagging must be redone.</span></span>
    
- <span data-ttu-id="e7a51-165">分類子の更新: ユーザーがタグ付けまたはシードの変更を適用できます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-165">Update classifier: Allows the user to apply tagging or seeding changes.</span></span>
    
  - <span data-ttu-id="e7a51-166">意味: タグ付けとシードの変更は、別の関連性サンプルを手動で実行する必要なく適用できます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-166">Implication: Tagging and seeding changes can be applied without needing to manually run another Relevance sample.</span></span>
    
- <span data-ttu-id="e7a51-167">保留: 関連性トレーニング プロセスが完了しました。</span><span class="sxs-lookup"><span data-stu-id="e7a51-167">On hold: The Relevance training process is completed.</span></span>
    
  - <span data-ttu-id="e7a51-168">意味: この時点では関連性トレーニングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e7a51-168">Implication: No Relevance training is required at this point.</span></span>
    
<span data-ttu-id="e7a51-169">Advanced eDiscovery はプロセスをガイドしますが、推奨される次の手順は異なる段階で説明しますが、タブとページ間を移動したり、個々のケース、問題、またはドキュメントレビュー プロセスに関連する可能性のある状況に対処したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-169">Although Advanced eDiscovery guides you through the process, with recommended Next steps at different stages, it also allows you to navigate between tabs and pages, and to make choices to address situations that may be pertinent to your individual case, issue, or document review process.</span></span> 
  
<span data-ttu-id="e7a51-170">Advanced eDiscovery の次の手順の処理の選択肢を受け入れるか、上書きすることができます。</span><span class="sxs-lookup"><span data-stu-id="e7a51-170">It is possible to accept or override Advanced eDiscovery Next step processing choices.</span></span> <span data-ttu-id="e7a51-171">推奨される次の手順以外の手順を実行する場合は、ダイアログの展開された問題の表示にリストされている次の手順をクリックし、次の手順の横にある [変更] ボタンをクリックして、別の [次のステップ] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e7a51-171">If you want to perform a step other than the recommended Next step, click the **Next step** listed in the expanded issue display in the dialog, click the **Modify** button next to the Next step, and select another Next step option.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e7a51-172">一部のオプションは、ロック解除後も無効なままになっている場合があります。これらのオプションは、プロセスのその時点での使用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e7a51-172">Some options may remain disabled after unlocking as they are not supported for use at that point in the process.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e7a51-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7a51-173">See also</span></span>

[<span data-ttu-id="e7a51-174">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="e7a51-174">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="e7a51-175">関連性の評価について</span><span class="sxs-lookup"><span data-stu-id="e7a51-175">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e7a51-176">タグ付けと評価</span><span class="sxs-lookup"><span data-stu-id="e7a51-176">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e7a51-177">タグ付けと関連性のトレーニング</span><span class="sxs-lookup"><span data-stu-id="e7a51-177">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e7a51-178">関連性分析の追跡</span><span class="sxs-lookup"><span data-stu-id="e7a51-178">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e7a51-179">結果に基づいて決定する</span><span class="sxs-lookup"><span data-stu-id="e7a51-179">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)
  
[<span data-ttu-id="e7a51-180">関連性分析のテスト</span><span class="sxs-lookup"><span data-stu-id="e7a51-180">Testing Relevance analysis</span></span>](test-relevance-analysis-in-advanced-ediscovery.md)

