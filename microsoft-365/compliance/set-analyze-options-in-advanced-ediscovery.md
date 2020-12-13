---
title: Advanced eDiscovery で分析オプションを設定する
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: Advanced eDiscovery の分析プロセス (ほぼ重複、電子メール スレッド、テーマなど) のオプションを設定する手順を確認します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ff51402cd79f2966730677a982fa5173b7e9b98
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663502"
---
# <a name="set-analyze-options-in-advanced-ediscovery-classic"></a><span data-ttu-id="21ccf-103">Advanced eDiscovery (クラシック) で分析オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="21ccf-103">Set Analyze options in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="21ccf-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="21ccf-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="21ccf-106">Advanced eDiscovery で、分析を実行する前に分析オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="21ccf-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="21ccf-107">分析オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="21ccf-107">Set Analyze options</span></span>

<span data-ttu-id="21ccf-108">Open **Prepare \> Analyze** \> **Setup**.</span><span class="sxs-lookup"><span data-stu-id="21ccf-108">Open **Prepare \> Analyze** \> **Setup**.</span></span> <span data-ttu-id="21ccf-109">次のウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="21ccf-109">The following window is displayed.</span></span>
  
![[分析設定] のオプション](../media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="21ccf-111">**ほぼ重複しているスレッドと電子メール スレッド** 分析を実行する場合は、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="21ccf-111">**Near-duplicates and email threads** Check this box if you want to run the analysis.</span></span> <span data-ttu-id="21ccf-112">既定では選択されています。</span><span class="sxs-lookup"><span data-stu-id="21ccf-112">It is selected by default.</span></span> 
  
 <span data-ttu-id="21ccf-113">**ドキュメントの類似性** [近重複] しきい値を入力するか、既定値の 65% を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="21ccf-113">**Document similarity** Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="21ccf-114">**テーマ** すべてのファイルを処理し、テーマを割り当てるには、このチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="21ccf-114">**Themes** Check this box to process all files and assign themes to them.</span></span> <span data-ttu-id="21ccf-115">既定では、このチェック ボックスはオンではありません。</span><span class="sxs-lookup"><span data-stu-id="21ccf-115">By default, this check box is not selected.</span></span> <span data-ttu-id="21ccf-116">テーマ処理を実行する場合は、次のオプションを入力します。</span><span class="sxs-lookup"><span data-stu-id="21ccf-116">Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="21ccf-117">**テーマの最大数** 作成するテーマの数の値を入力または選択します。</span><span class="sxs-lookup"><span data-stu-id="21ccf-117">**Max number of themes** Enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="21ccf-118">既定値は 200 です。</span><span class="sxs-lookup"><span data-stu-id="21ccf-118">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="21ccf-119">テーマの数を増やすと、パフォーマンスに影響を与えるだけでなく、テーマを一般化する機能にも影響します。</span><span class="sxs-lookup"><span data-stu-id="21ccf-119">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="21ccf-120">テーマの数が多いほど、細かく設定できます。</span><span class="sxs-lookup"><span data-stu-id="21ccf-120">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="21ccf-121">たとえば、一連の 50 のテーマに 「バスケス、ボールズ、クリッパー、レイカー」などのテーマが含まれる場合です。300 のテーマには、"1 つのテーマ"、"Clippers"、"Lakers" が含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="21ccf-121">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="21ccf-122">ECA に対してこの機能を使用する場合は、"バスケト" というテーマを認識する必要がない場合に役立つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="21ccf-122">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="21ccf-123">ただし、処理のテーマが多すぎる場合は、"バスケ" という単語が表示されない可能性があります。また、ブートしてヘアに使用されるアイテムではなく、スクリッパーとクリッパーがレビューに優れたバスケト テーマであるというのを知らない場合があります。</span><span class="sxs-lookup"><span data-stu-id="21ccf-123">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="21ccf-124">**推奨されるテーマ** テーマの処理を制御するテーマの単語を提案できます。</span><span class="sxs-lookup"><span data-stu-id="21ccf-124">**Suggested themes** You can suggest theme words to control Themes processing.</span></span> <span data-ttu-id="21ccf-125">Advanced eDiscovery は、これらの推奨される単語に焦点を当て、"テーマの最大数" 設定に基づいて、1 つ以上の関連するテーマを作成します。</span><span class="sxs-lookup"><span data-stu-id="21ccf-125">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="21ccf-126">たとえば、候補の単語が "computer" で、"2" を "最大テーマ数" として指定した場合、Advanced eDiscovery は単語 "computer" に関連する 2 つのテーマの生成を試みる。</span><span class="sxs-lookup"><span data-stu-id="21ccf-126">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="21ccf-127">たとえば、"コンピューター ソフトウェア" と "コンピューター ハードウェア" という 2 つのテーマがあります。</span><span class="sxs-lookup"><span data-stu-id="21ccf-127">The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![提示されたテーマの追加](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="21ccf-129">推奨されるテーマを表示、追加、または編集するには、[変更] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="21ccf-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="21ccf-130">[推奨 **されるテーマ] パネル** で、[追加] アイコン アイコンをクリックして ![ ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) テーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="21ccf-130">In the **Suggested themes** panel, click the **Add** ![add icon](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme.</span></span> <span data-ttu-id="21ccf-131">[推奨 **されるテーマの追加] パネル** で、単語をコンマで区切って追加します。</span><span class="sxs-lookup"><span data-stu-id="21ccf-131">In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="21ccf-132">[ **テーマの数**] で値を選択して、Advanced eDiscovery がこれらの単語に対して生成しようとするテーマの数を決定します (既定値は 1 テーマです)。</span><span class="sxs-lookup"><span data-stu-id="21ccf-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="21ccf-133">[ **保存] を** クリックし、ダイアログを閉じます。</span><span class="sxs-lookup"><span data-stu-id="21ccf-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="21ccf-134">テーマの総数には、推奨されるテーマが含まれます。</span><span class="sxs-lookup"><span data-stu-id="21ccf-134">The total number of themes includes Suggested Themes.</span></span> <span data-ttu-id="21ccf-135">推奨されるテーマの合計がテーマの合計を超えすることはできません。</span><span class="sxs-lookup"><span data-stu-id="21ccf-135">The total Suggested Themes cannot exceed the total themes.</span></span> <span data-ttu-id="21ccf-136">テーマ全体に対して推奨テーマが多数ある場合、そのテーマのほとんどが推奨テーマ専用なので、システムによって検出される "新しい" テーマはわずかです。</span><span class="sxs-lookup"><span data-stu-id="21ccf-136">If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="21ccf-137">**モード** ドロップダウン リストからテーマ オプションを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="21ccf-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="21ccf-138">**モデルの作成と適用**: ファイルのセグメントからモデル別にテーマを計算し、その間でファイルを配布します。</span><span class="sxs-lookup"><span data-stu-id="21ccf-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="21ccf-139">**モデルの** 作成 : ファイルのセグメントからテーマ モデルを計算します。</span><span class="sxs-lookup"><span data-stu-id="21ccf-139">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="21ccf-140">ファイルを分割する適用プロセスは、別の時点で個別に実行されます。</span><span class="sxs-lookup"><span data-stu-id="21ccf-140">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="21ccf-141">**モデルの** 適用 : このオプションは、モデルが以前に作成され、まだ適用されていない場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="21ccf-141">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="21ccf-142">これにより、テーマに基づいてファイルが分割されます。</span><span class="sxs-lookup"><span data-stu-id="21ccf-142">This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="21ccf-143">テキストの無視 [を設定し、分析](set-ignore-text-in-advanced-ediscovery.md) の [詳細設定を分析に](set-analyze-advanced-settings-in-advanced-ediscovery.md) 設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="21ccf-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="21ccf-144">これらのオプションを設定した後、[分析] をクリック **して** 実行します。</span><span class="sxs-lookup"><span data-stu-id="21ccf-144">After you've set these options, click **Analyze** to run.</span></span> <span data-ttu-id="21ccf-145">[分析結果の表示が](view-analyze-results-in-advanced-ediscovery.md) 表示されます。</span><span class="sxs-lookup"><span data-stu-id="21ccf-145">[View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="21ccf-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="21ccf-146">Related topics</span></span>

[<span data-ttu-id="21ccf-147">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="21ccf-147">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="21ccf-148">ドキュメントの類似性について</span><span class="sxs-lookup"><span data-stu-id="21ccf-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
<span data-ttu-id="21ccf-149">[[テキストを無視する] を設定する ](set-ignore-text-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="21ccf-149">[Set Ignore text ](set-ignore-text-in-advanced-ediscovery.md)</span></span>
  
[<span data-ttu-id="21ccf-150">分析設定の拡張設定</span><span class="sxs-lookup"><span data-stu-id="21ccf-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="21ccf-151">結果の分析を表示する</span><span class="sxs-lookup"><span data-stu-id="21ccf-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

