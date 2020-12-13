---
title: Advanced eDiscovery ユーティリティを使用する
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
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: ケース ログ、データのクリア、エラーの処理、関連性の変更、透明性分析など、Advanced eDiscovery のユーティリティについて説明します。
ms.openlocfilehash: 745b81609d73ec88525c3348cc4d582c7d5d7b30
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663296"
---
# <a name="use-advanced-ediscovery-classic-utilities"></a><span data-ttu-id="e48ef-103">Advanced eDiscovery (クラシック) ユーティリティを使用する</span><span class="sxs-lookup"><span data-stu-id="e48ef-103">Use Advanced eDiscovery (classic) utilities</span></span>

> [!NOTE]
> <span data-ttu-id="e48ef-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="e48ef-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="e48ef-106">Advanced eDiscovery で表示および使用可能なユーティリティは、コンテキストロールとユーザー ロールによって異なっています。</span><span class="sxs-lookup"><span data-stu-id="e48ef-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="e48ef-107">ケース ログ</span><span class="sxs-lookup"><span data-stu-id="e48ef-107">Case log</span></span>

<span data-ttu-id="e48ef-108">ケース ログには、アプリケーション処理アクティビティの詳細な一覧が示されます。このアクティビティは、追跡、トラブルシューティング、およびエラーと警告の解決に使用できます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-108">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings.</span></span> <span data-ttu-id="e48ef-109">ログは、ホストまたはサーバー上でローカルに生成および保存するか、電子メール アドレスに直接送信できます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-109">The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="e48ef-110">ログ ファイルは、クライアントのコンピューターにダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-110">The log file can also be downloaded to the client's computer.</span></span> <span data-ttu-id="e48ef-111">クライアントのダウンロード オプションは、構成とユーザー ロールに応じて有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-111">The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="e48ef-112">メニュー バーで、[ホイール] アイコン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="e48ef-113">[設定と **ユーティリティ ユーティリティ] タブ \> で** 、[ケース ログのセットアップ **] を選択 \> します**。</span><span class="sxs-lookup"><span data-stu-id="e48ef-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="e48ef-114">ログ レベル **を次のように** 選択します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="e48ef-115">**標準**: 基本的なログ データが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-115">**Standard**: Includes the basic log data.</span></span> <span data-ttu-id="e48ef-116">通常、このオプションは監視に必要であり、推奨されない限り使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e48ef-116">This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="e48ef-117">**Minimal**: 非常に大きなケースで使用され、最新のデータのみを返します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="e48ef-118">[ケース **ログの実行] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e48ef-118">Click **Run Case log**.</span></span> <span data-ttu-id="e48ef-119">ログが生成され、パスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-119">The log is generated and path is displayed.</span></span> <span data-ttu-id="e48ef-120">現在のタスクと最後のタスクのタスク進捗状況情報が [作業状況] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-120">The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="e48ef-121">データをクリアする</span><span class="sxs-lookup"><span data-stu-id="e48ef-121">Clear data</span></span>

<span data-ttu-id="e48ef-122">ケース データを削除または再初期化する必要がある場合は、データベース インスタンスを初期化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e48ef-122">If it is necessary to delete or reinitialize case data, the database instance must be initialized.</span></span> <span data-ttu-id="e48ef-123">Clear data ユーティリティは、ケース データベース、テキスト ファイル、ケース フォルダー、および蓄積された結果から、指定されたエントリをすべて削除します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-123">The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results.</span></span> <span data-ttu-id="e48ef-124">この関数は管理者だけが実行できます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-124">The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e48ef-125">このアクションは元に戻すのではなく、エキスパートによって実行された関連性のタグ付けと分析はすべてクリアされます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-125">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert.</span></span> <span data-ttu-id="e48ef-126">必要に応じて、データのバックアップを保存します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-126">Save a backup of data, if necessary.</span></span> <span data-ttu-id="e48ef-127">このオプションは、非常に注意して使用してください。</span><span class="sxs-lookup"><span data-stu-id="e48ef-127">Use this option with extreme care.</span></span> <span data-ttu-id="e48ef-128">タグ付けされたファイルとランク付けされたファイルを削除すると、関連性の結果に影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e48ef-128">Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="e48ef-129">メニュー バーで、[ホイール] アイコン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="e48ef-130">[設定と **ユーティリティ ユーティリティ \> ] タブで** 、[データのセットアップのクリア **] を \> 選択します**。</span><span class="sxs-lookup"><span data-stu-id="e48ef-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="e48ef-131">初期化する情報のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="e48ef-132">**関連性 :** 読み込み時の定義や読み込むファイルの関連付けなど、関連性で行われたすべての作業を削除します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-132">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads.</span></span> <span data-ttu-id="e48ef-133">すべてのサンプルとタグ付けを削除します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-133">It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="e48ef-134">**近重複および電子メール スレッド**: 近重複および電子メール スレッドのすべての分析情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="e48ef-135">**テーマ**: テーマに関連するデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="e48ef-136">**エクスポート履歴**: エクスポート バッチの履歴情報を削除します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="e48ef-137">[データの **クリア] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e48ef-137">Click **Clear data**.</span></span> <span data-ttu-id="e48ef-138">ケース データがクリアされます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-138">The case data is cleared.</span></span> <span data-ttu-id="e48ef-139">現在のタスクと最後のタスクのタスク進捗状況情報が [作業状況] **ウィンドウに表示** されます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-139">The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="e48ef-140">関連性の変更</span><span class="sxs-lookup"><span data-stu-id="e48ef-140">Modify Relevance</span></span>

<span data-ttu-id="e48ef-141">このセクションでは、関連性サンプルをスキップまたはロールバックする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="e48ef-142">メニュー バーで、[ホイール] アイコン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="e48ef-143">[設定と **ユーティリティ ユーティリティ] タブ \> で** 、[関連性の変更] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="e48ef-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="e48ef-144">オプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="e48ef-145">**現在のユーザーの現在の** サンプルをスキップします。これにより、ユーティリティを実行しているユーザーのオープン ケース サンプル内のすべてのタグ付けされていないファイルが **Skip** としてタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-145">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility.</span></span> <span data-ttu-id="e48ef-146">Skip としてタグ付けされたファイルに対して関連性処理は実行 **されません**。</span><span class="sxs-lookup"><span data-stu-id="e48ef-146">Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="e48ef-147">**現在のサンプル (開いているすべてのサンプル**) をスキップします。これにより、すべてのユーザーの開いているすべてのサンプルでタグ付けされていないファイルが **Skip** としてタグ付けされます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-147">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users.</span></span> <span data-ttu-id="e48ef-148">ユーザーが現在サンプルにタグ付けしている場合、このオプションは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="e48ef-148">This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="e48ef-149">**最後のサンプルの** ロールバック : 最後に完了した関連性トレーニング サンプルは、"Calculate" プロセスの前か後かにかかわらずロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-149">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process.</span></span> <span data-ttu-id="e48ef-150">キャッチアップ サンプルのロールバックは許可されません。</span><span class="sxs-lookup"><span data-stu-id="e48ef-150">Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="e48ef-151">[ **実行] をクリック** して実行します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="e48ef-152">透明度の分析</span><span class="sxs-lookup"><span data-stu-id="e48ef-152">Transparency analysis</span></span>

<span data-ttu-id="e48ef-153">透過性分析ユーティリティを使用すると、ファイルの詳細ビューと、ファイルに割り当てられた関連性スコアを表示できます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-153">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score.</span></span> <span data-ttu-id="e48ef-154">レポートは、サニティ チェックとして使用したり、Advanced eDiscovery によって割り当てられた関連性と比較して、人間のレビューアーによって定義されたファイルの関連性を比較したりするために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-154">The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="e48ef-155">Advanced eDiscovery は、関連性スコアに加えて、キーワード コンテキストを考慮するキーワードの重みを計算して割り当てします。</span><span class="sxs-lookup"><span data-stu-id="e48ef-155">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context.</span></span> <span data-ttu-id="e48ef-156">ファイル内の同じ単語に、コンテキストと場所に応じて異なる重みを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-156">The same word in a file can be assigned different weights, depending on context and location.</span></span> <span data-ttu-id="e48ef-157">各キーワードは、黄色から濃いオレンジ色、さまざまな灰色の網掛けまで、色の強さを増すスケールを使用してマークされます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-157">Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray.</span></span> <span data-ttu-id="e48ef-158">色分けは、関連性スコアに対する単語の相対的な正または負の貢献度を視覚的に示すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-158">Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="e48ef-159">複数の問題が発生するシナリオでは、問題ごとに透明性分析レポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="e48ef-160">メニュー バーで、[ホイール] アイコン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="e48ef-161">[設定と **ユーティリティ ユーティリティ] タブ \> で** 、[透過性分析の **セットアップ] を選択 \> します**。</span><span class="sxs-lookup"><span data-stu-id="e48ef-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="e48ef-162">In \*\* File ID \*\*, enter the file ID of the file of the file to process.</span><span class="sxs-lookup"><span data-stu-id="e48ef-162">In \*\* File ID \*\*, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="e48ef-163">[問題 **] ボックス** の一覧で、関連する問題を選択します。</span><span class="sxs-lookup"><span data-stu-id="e48ef-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="e48ef-164">[透過性 **の分析] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e48ef-164">Click **Transparency analysis**.</span></span> <span data-ttu-id="e48ef-165">完了すると、ファイルの透明性分析レポートが表示されます。このレポートには、マークされたキーワードの色と全体的な関連性スコアとの相関関係が示されます。</span><span class="sxs-lookup"><span data-stu-id="e48ef-165">Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e48ef-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="e48ef-166">See also</span></span>

[<span data-ttu-id="e48ef-167">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="e48ef-167">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="e48ef-168">ケースとテナントの設定の定義</span><span class="sxs-lookup"><span data-stu-id="e48ef-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

