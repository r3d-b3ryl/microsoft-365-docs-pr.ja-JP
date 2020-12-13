---
title: Advanced eDiscovery でインポートしたファイルを追加する読み込み設定
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
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: Advanced eDiscovery で関連度トレーニングを実行する前に、インポートしたファイルを最後に定義したファイルの読み込み (バッチ) に追加する手順を確認します。
ms.openlocfilehash: 7cd244ba1ba516c2b7376b71e809b4c01ff5df8b
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663482"
---
# <a name="set-up-loads-to-add-imported-files-in-advanced-ediscovery-classic"></a><span data-ttu-id="8bfbd-103">Advanced eDiscovery (クラシック) でインポートしたファイルを追加する読み込み設定</span><span class="sxs-lookup"><span data-stu-id="8bfbd-103">Set up loads to add imported files in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="8bfbd-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="8bfbd-106">Advanced eDiscovery では、読み込みとは、ケースに追加されたファイルの新しいバッチです。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-106">In Advanced eDiscovery, a load is a new batch of files added to a case.</span></span> <span data-ttu-id="8bfbd-107">既定では、1 つの読み込みが定義され、インポートされたファイルすべてが追加されます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-107">By default, one load is defined and all imported files are added to it.</span></span> <span data-ttu-id="8bfbd-108">関連性トレーニングを実行する前に、インポートしたファイルを負荷に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-108">Before performing Relevance training, imported files must be added to the load.</span></span> 
  
<span data-ttu-id="8bfbd-109">次のようなシナリオを考えてみましょう。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-109">Consider the following scenarios:</span></span>
  
- <span data-ttu-id="8bfbd-110">新しいファイルは、ケース データベースに読み込まれた以前のファイルと似ています。または、ファイルの以前の読み込みは、ファイル コレクションからランダムに設定されています。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-110">New files are known to be similar to the previous files loaded to the case database, or the previous load of files was a random set from the file collection.</span></span> <span data-ttu-id="8bfbd-111">この例では、インポートしたファイルを現在のファイルの読み込みに追加します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-111">In this instance, add the imported files to the current file load.</span></span>
    
- <span data-ttu-id="8bfbd-112">新しいファイルは、以前のファイルとは異なる (たとえば、別のソースから) 異なるか、以前の読み込みと似ているか、異なっているという事前の知識がない。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-112">New files are different from previous ones (for example, from a different source), or you have no prior knowledge that they're similar or different to the previous loads.</span></span> <span data-ttu-id="8bfbd-113">このシナリオでは、インポートしたファイルを新しいファイルの読み込みに追加します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-113">In this scenario, add the imported files to a new file load.</span></span> <span data-ttu-id="8bfbd-114">Advanced eDiscovery はこれをローリング ロード シナリオとして認識し、キャッチアップ プロセスを呼び出し、キャッチアップが完了するまで関連性トレーニングとバッチ計算をロックし、新しい負荷を統合してトレーニングします。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-114">Advanced eDiscovery recognizes this as a Rolling loads scenario, invokes a Catch-up process, locks Relevance training and Batch calculations until Catch-up is completed, and the new load is integrated and trained.</span></span> 
    
## <a name="adding-imported-files-to-the-current-load"></a><span data-ttu-id="8bfbd-115">インポートしたファイルを現在の読み込み状態に追加する</span><span class="sxs-lookup"><span data-stu-id="8bfbd-115">Adding imported files to the current load</span></span>

<span data-ttu-id="8bfbd-116">Advanced eDiscovery で処理するには、インポートしたファイルをロードに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-116">All imported files must be added to a load to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="8bfbd-117">インポートされたファイルは、最後に定義された読み込みに追加されます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-117">Imported files are added to the last defined load.</span></span> <span data-ttu-id="8bfbd-118">後で追加のファイルをインポートする場合は、読み込みにも追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-118">If you import additional files later, they also must be added to the load.</span></span>
  
1. <span data-ttu-id="8bfbd-119">[関連性 **の関連性の設定 \> ] タブで、[** 読み込み] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-119">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
    ![[関連性の設定をロード] タブ](../media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. <span data-ttu-id="8bfbd-121">**ファイルを含** める : 含めるファイルのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-121">**Include files**: Select an option for files to include.</span></span> <span data-ttu-id="8bfbd-122">既定では、現在の読み込みへのファイルの追加は、"すべてのファイル" の母集団に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-122">By default, adding files to the current load is based on the "All files" population.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8bfbd-123">利用可能なすべてのカリング されたファイルを関連性に読み込む。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-123">Load all available culled files into Relevance.</span></span> <span data-ttu-id="8bfbd-124">利用可能なファイルのサブセットのみを読み込む場合は、サブセットの読み込みが関連性トレーニングに悪影響を及ぼす可能性があるとして、まずサポートに問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-124">If you plan to load only a subset of the available files, please first consult with Support, as loading subsets can adversely affect Relevance training.</span></span> 
  
3. <span data-ttu-id="8bfbd-125">[ **負荷管理] で**、負荷を選択します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-125">In **Loads management**, select a load.</span></span>
    
4. <span data-ttu-id="8bfbd-126">[ファイル **の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-126">Click **Add files**.</span></span> <span data-ttu-id="8bfbd-127">ファイルが読み込み時に追加され、確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-127">The files are added to the load and a confirmation message is displayed.</span></span> 
    
5. <span data-ttu-id="8bfbd-128">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-128">Click **OK**.</span></span>
    
<span data-ttu-id="8bfbd-129">これで、ファイルを Advanced eDiscovery の関連性で処理して、ファイルをトレーニングできます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-129">The files can now be processed in Advanced eDiscovery Relevance for training the files.</span></span>
  
## <a name="editing-a-load-name-within-a-case"></a><span data-ttu-id="8bfbd-130">ケース内での読み込み名の編集</span><span class="sxs-lookup"><span data-stu-id="8bfbd-130">Editing a load name within a case</span></span>

<span data-ttu-id="8bfbd-131">読み込み名を変更する場合は、大文字と小文字を区別する名前を使用してください。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-131">If changing the load name, it is recommended to use a name that is significant to the case.</span></span>
  
1. <span data-ttu-id="8bfbd-132">[関連性 **の関連性の設定 \> ] タブで、[** 読み込み] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-132">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="8bfbd-133">負荷管理 **リストから負荷を** 選択し、[編集] アイコン **をクリック** します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-133">From the **Loads management** list, select a load and click the **Edit** icon.</span></span> <span data-ttu-id="8bfbd-134">[読み込み編集] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-134">The Edit load window is displayed.</span></span> 
    
3. <span data-ttu-id="8bfbd-135">変更を入力し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-135">Enter the changes, and then click **OK**.</span></span>
    
## <a name="adding-imported-files-to-a-new-load"></a><span data-ttu-id="8bfbd-136">インポートしたファイルを新しい読み込みへの追加</span><span class="sxs-lookup"><span data-stu-id="8bfbd-136">Adding imported files to a new load</span></span>

<span data-ttu-id="8bfbd-137">関連性トレーニングを開始するか、バッチ計算を実行した後、追加のファイル セットをインポートして処理できます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-137">After starting Relevance training or performing Batch calculation, you may want to import and process an additional set of files.</span></span> 
  
<span data-ttu-id="8bfbd-138">キャッチアップ中は、キャッチアップ セットを作成、タグ付け、および分析できます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-138">During Catch-up, you can create, tag, and analyze the Catch-up set.</span></span> <span data-ttu-id="8bfbd-139">Advanced eDiscovery は、新しい読み込み時の関連ファイルと非関連ファイルの評価を、以前の読み込み時のファイルと比較します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-139">Advanced eDiscovery compares its assessment of Relevant and Non-Relevant files in the new load to those in previous loads.</span></span> <span data-ttu-id="8bfbd-140">結果に基づいて、必要に応じてキャッチアップの決定を求めるメッセージが表示され、Advanced eDiscovery は発生した関連性情報に基づいて推奨事項を提供します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-140">Based on the results, you are prompted to make Catch-up decisions, if necessary, and Advanced eDiscovery provides recommendations based on the accrued Relevance information.</span></span> 
  
<span data-ttu-id="8bfbd-141">ローリング ロードとキャッチアップ機能は、次のように異なります。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-141">Rolling Loads and Catch-up functionality varies as follows:</span></span> 
  
- <span data-ttu-id="8bfbd-142">バッチ計算後に新しいファイルの読み込み量をインポートすると、Advanced eDiscovery は、ファイルが次のいずれかのカテゴリにどの程度分類されるのかを判断します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-142">When you import a new file load after Batch calculation, Advanced eDiscovery determines to what extent the files fall into one of the following categories:</span></span>
    
  - <span data-ttu-id="8bfbd-143">類似 (同種): 新しいカスタムラウンドの関連性トレーニングは必要ありません。また、以前の負荷から得られる知識は、新しい負荷に "今まで通り" 適用できます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-143">Similar (homogeneous): A new, custom round of Relevance training is not required and the knowledge accrued from the previous load can be applied "as is" to the new load.</span></span> 
    
  - <span data-ttu-id="8bfbd-144">異なる (異種): 新しいカスタムラウンドの関連性トレーニングが必要であり、以前の負荷から得た知識は適用できません。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-144">Distinct (heterogeneous): A new, custom round of Relevance training is required, and the knowledge accrued from the previous load cannot be applied.</span></span> 
    
    <span data-ttu-id="8bfbd-145">これらの用語は、読み込み中ではなく、読み込みと読み込み間のファイルの類似度のレベルを表します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-145">These terms refer to the level of similarity of files between loads and not within the loads.</span></span> 
    
- <span data-ttu-id="8bfbd-146">関連度トレーニング中 (バッチ計算前) に新しいファイルの負荷をインポートする場合、キャッチアップを使用すると、United ファイル セットの関連度トレーニングを続行できます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-146">When importing a new file load during Relevance training (before Batch calculation), Catch-up enables you to continue Relevance training on the united file set.</span></span> <span data-ttu-id="8bfbd-147">Advanced eDiscovery では、新しい負荷が以前の負荷と類似しているのか、それとも異なるのかを予測する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-147">Advanced eDiscovery does not estimate whether the new load is similar to or distinct from the previous load.</span></span> <span data-ttu-id="8bfbd-148">新しい負荷に関する情報を収集するだけで、関連性トレーニングが新しいファイルと以前のファイルのセットで続行できます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-148">It simply collects information about the new load and enables Relevance training to continue on the new and previous sets of files.</span></span> 
    
- <span data-ttu-id="8bfbd-149">関連度トレーニングに複数の問題とバッチ計算後の問題がある場合は、キャッチアップ プロセスがすべての問題に対して 1 回実行され、結果が計算され、各問題に対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-149">When there are multiple issues in Relevance training as well as issues after Batch calculation, the Catch-up process is performed once for all issues, and the results are calculated and displayed for each issue.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8bfbd-150">キャッチアップ サンプルのサイズは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-150">The size of the Catch-up sample may vary.</span></span> <span data-ttu-id="8bfbd-151">前の負荷に対する新しい負荷のサイズと、新しい負荷を追加する前に完了したサンプルの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-151">It depends on the size of the new load relative to the previous loads, and on the number of samples completed before adding the new load.</span></span> <span data-ttu-id="8bfbd-152">キャッチアップ サンプルは、通常、新しい負荷から 200 ~ 2,000 のファイルのセットです。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-152">The Catch-up sample is typically a set of 200 to 2,000 files from the new load.</span></span> 
  
> [!TIP]
> <span data-ttu-id="8bfbd-153">キャッチアップは他のタスクを停止し、個々のファイルのタグ付けとレビューを必要とします。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-153">Catch-up stops any other tasks and requires individual file tagging and review.</span></span> <span data-ttu-id="8bfbd-154">したがって、大きなバッチで新しいファイルを追加すると、オーバーヘッドを削減できます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-154">Therefore, you can reduce overhead when you add new files in large batches.</span></span> 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a><span data-ttu-id="8bfbd-155">キャッチアップロードとローリング ロードを使用した新しいファイルロードの追加</span><span class="sxs-lookup"><span data-stu-id="8bfbd-155">Adding a new file load using Catch-up and Rolling loads</span></span>

1. <span data-ttu-id="8bfbd-156">[関連性 **の関連性の設定 \> ] タブで、[** 読み込み] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-156">In the **Relevance \> Relevance setup** tab, select **Loads**.</span></span>
    
2. <span data-ttu-id="8bfbd-157">[ **負荷の管理]** で、アイコン **+** をクリックして負荷を追加します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-157">Under **Loads management**, click the **+** icon to add a load.</span></span> <span data-ttu-id="8bfbd-158">確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-158">A confirmation message is displayed.</span></span> 
    
3. <span data-ttu-id="8bfbd-159">**[はい]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-159">Click **Yes** to continue.</span></span> <span data-ttu-id="8bfbd-160">[ **新しい読み込み追加] ダイアログ** が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-160">The **Add new load** dialog is displayed.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="8bfbd-161">新しい負荷を追加できるのは、操作が以前の負荷に対して実行された場合のみです。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-161">You can only add a new load if actions were performed to the previous load.</span></span> 
  
4. <span data-ttu-id="8bfbd-162">[新しい **読み込み追加] ダイアログ で** 、[読み込み名] と [説明] **に** 情報を **入力** し **、[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-162">In the **Add new load** dialog, type information in **Load name** and **Description** and then click **OK**.</span></span> <span data-ttu-id="8bfbd-163">Advanced eDiscovery では、新しい負荷が追加されます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-163">Advanced eDiscovery adds a new load.</span></span>
    
5. <span data-ttu-id="8bfbd-164">新しい読み込みファイルをインポートするには、[ファイルの追加] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-164">To import the new load file, click **Add files**.</span></span> <span data-ttu-id="8bfbd-165">この読み込みには、すべての新しいファイルが追加されます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-165">All new files are added to this load.</span></span> <span data-ttu-id="8bfbd-166">Advanced eDiscovery は、ファイルをインポートした後、ローリング ロード シナリオを認識し、次の手順としてキャッチアップを示します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-166">After Advanced eDiscovery imports the files, it recognizes the Rolling loads scenario and indicates Catch-up as the next step.</span></span>
    
6. <span data-ttu-id="8bfbd-167">ダイアログ **の下部にある [キャッチアップ** ] をクリックして、シナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-167">Click **Catch-up** at the bottom of the dialog to run the scenario.</span></span> 
    
    <span data-ttu-id="8bfbd-168">すべての問題に対して 200 ~ 2,000 のファイルを含む単一のキャッチアップ セットが作成され、同時ファイル のタグ付けが可能です。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-168">A single Catch-up set, typically containing 200 to 2,000 files from the new load, is created for all issues to allow concurrent file tagging.</span></span>
    
    <span data-ttu-id="8bfbd-169">負荷が類似しているのか、それとも異なるか、Advanced eDiscovery が自動的に読み込みと分割を行ったかどうか、および次の手順の処理に関する情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-169">Details are provided about whether loads are similar or distinct, whether Advanced eDiscovery merged or split the loads automatically, and information regarding processing in the next step.</span></span>
    
    <span data-ttu-id="8bfbd-170">その後、ファイルにタグを付け、計算操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-170">You can then tag files and run a calculate operation.</span></span> <span data-ttu-id="8bfbd-171">タグ付けにより、関連性によって読み込みが類似または明確かどうかを判断し、新しいファイル のセットに対する作業を続行できます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-171">The tagging enables Relevance to determine if loads are similar or distinct and enables you to continue working on the new set of files.</span></span>
    
7. <span data-ttu-id="8bfbd-172">キャッチアップ セットを確認した後、キャッチ **アップ結果の \> 関連性** トラックを表示します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-172">After the Catch-up set is reviewed, view **Relevance \> Track** for the Catch-up results.</span></span> 
    
1. <span data-ttu-id="8bfbd-173">関連性トレーニング中に新しいファイルの読み込み (問題がまだバッチ計算を行っていない) が追加された場合は、キャッチアップの結果に関係なく、次の手順としてトレーニングを続行します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-173">If the new file load was added during Relevance training (meaning, the issue has not yet gone through Batch calculation), **Continue training** is the next step, regardless of the Catch-up results.</span></span> 
    
    <span data-ttu-id="8bfbd-174">新しい読み込みと以前の読み込みは 1 つの負荷として処理され、関連性トレーニングは一連のセットで続行されます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-174">The new and previous loads are processed as one load and Relevance training continues on the united set.</span></span> <span data-ttu-id="8bfbd-175">これで、この手順が完了し、関連性トレーニングを続行できます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-175">You are now finished with this procedure and can continue Relevance training.</span></span> 
    
2. <span data-ttu-id="8bfbd-176">Batch 計算後に新しい負荷が追加された場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-176">If the new load was added after Batch calculation, proceed to the following steps.</span></span>
    
8. <span data-ttu-id="8bfbd-177">バッチ計算後に追加された新しい読み込みについて、Advanced eDiscovery は、次のように、新しい負荷が以前の負荷と類似しているのか、それとも異なるのか判断します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-177">For new loads added after Batch calculation, Advanced eDiscovery determines if the new load is similar to or distinct from previous loads, as follows:</span></span>
    
1. <span data-ttu-id="8bfbd-178">読み込み結果が類似している場合: 追加の関連性トレーニングは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-178">If loads were found to be similar: No additional Relevance training is necessary.</span></span> <span data-ttu-id="8bfbd-179">ダッシュボードでは、推奨される次の手順は、 \*\* Batch calculation \*\* again to calculate Relevance scores for the new load.</span><span class="sxs-lookup"><span data-stu-id="8bfbd-179">The dashboard shows the recommended next step is to run \*\* Batch calculation \*\* again to calculate Relevance scores for the new load.</span></span> <span data-ttu-id="8bfbd-180">読み込みは似ているので、以前の分類子分析を新しいファイルで実行できます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-180">Loads were found to be similar, so the previous classifier analysis can be run on the new files.</span></span> 
    
2. <span data-ttu-id="8bfbd-181">読み込みで明確な結果が見つかった場合: その他の関連性トレーニングが必要であり、次の手順はキャッチアップの決定です。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-181">If loads were found to be distinct: More Relevance training is necessary and the next step is Catch-up decision.</span></span> <span data-ttu-id="8bfbd-182">キャッチアップの決定を次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-182">Select a Catch-up decision as follows:</span></span>
    
    <span data-ttu-id="8bfbd-183">[読み込み **データの結合] を** 選択すると、Advanced eDiscovery はトレーニング セットの以前の読み込みと新しい負荷をマージします。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-183">If you select **Merge loads**, Advanced eDiscovery merges previous and new loads for the training set.</span></span> <span data-ttu-id="8bfbd-184">最初の負荷はバッチ計算を行いましたが、より多くのトレーニングが必要です。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-184">Although the first load went through Batch calculation, more training is needed.</span></span> <span data-ttu-id="8bfbd-185">新しい負荷と以前の負荷を一緒にトレーニングし続ける。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-185">Continue training new and previous loads together.</span></span> <span data-ttu-id="8bfbd-186">その後、バッチ計算が再度実行され、以前の Batch 計算スコアは無視されます。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-186">Batch calculation will then run again and the previous Batch calculation scores should be ignored.</span></span> <span data-ttu-id="8bfbd-187">既存の読み込みについての関連性スコアを再計算できる場合 (たとえば、既存のファイルの読み込みレビューが開始されていない場合など) に、この選択を選択します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-187">Choose this selection when Relevance scores for existing loads can be recalculated, for example, when review of existing file loads has not started.</span></span>
    
    <span data-ttu-id="8bfbd-188">[読み込み **分割] を選択した** 場合は、新しい負荷についてのみ関連性トレーニングを続行します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-188">If you select **Split loads**, continue Relevance training only on the new load.</span></span> <span data-ttu-id="8bfbd-189">この場合、以前のバッチ計算スコアはそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-189">In this instance, previous Batch calculation scores will remain as is.</span></span> <span data-ttu-id="8bfbd-190">たとえば、既存の読み込みのレビューが既に開始されている場合など、既存の読み込みの既存の関連性スコアを再計算できない場合は、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-190">Choose this option when existing Relevance scores for existing loads cannot be recalculated, for example, if review of existing loads has already started.</span></span> <span data-ttu-id="8bfbd-191">関連性スコアは、この時点以降とは別に管理され、マージすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-191">Relevance scores are managed separately from this point onward and cannot be merged.</span></span>
    
3. <span data-ttu-id="8bfbd-192">[続行] **トレーニングをクリックします**。</span><span class="sxs-lookup"><span data-stu-id="8bfbd-192">Click **Continue training**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8bfbd-193">関連項目</span><span class="sxs-lookup"><span data-stu-id="8bfbd-193">See also</span></span>

[<span data-ttu-id="8bfbd-194">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="8bfbd-194">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="8bfbd-195">問題の定義とユーザーの割り当て</span><span class="sxs-lookup"><span data-stu-id="8bfbd-195">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="8bfbd-196">強調表示されたキーワードと詳細オプションの定義</span><span class="sxs-lookup"><span data-stu-id="8bfbd-196">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

