---
title: Advanced eDiscovery で結果の分析を表示する
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
ms.assetid: 5974f3c2-89fe-4c5f-ac7b-57f214437f7e
description: 表示されるタスク オプションの定義など、Advanced eDiscovery の分析プロセスの結果を表示する場所を理解します。
ms.openlocfilehash: 64c91cb5929a7a74e53d653faff98d5792d3f131
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663261"
---
# <a name="view-analyze-results-in-advanced-ediscovery-classic"></a><span data-ttu-id="91e85-103">Advanced eDiscovery (クラシック) で結果の分析を表示する</span><span class="sxs-lookup"><span data-stu-id="91e85-103">View Analyze results in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="91e85-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="91e85-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="91e85-106">Advanced eDiscovery では、分析プロセスの進行状況と結果を、次に示すさまざまな表示で表示できます。</span><span class="sxs-lookup"><span data-stu-id="91e85-106">In Advanced eDiscovery, progress and results for the Analyze process can be viewed in a variety of displays as described below.</span></span>
  
## <a name="view-analyze-task-status"></a><span data-ttu-id="91e85-107">タスクの状態の分析を表示する</span><span class="sxs-lookup"><span data-stu-id="91e85-107">View Analyze task status</span></span>

<span data-ttu-id="91e85-108">[ **結果 \> の分析 \> の \> 準備] タスクの状態では**、分析プロセスの実行中および実行後に状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="91e85-108">In **Prepare \> Analyze \> Results \> Task status**, the status is displayed during and after Analyze process execution.</span></span> 
  
![タスクの進捗状況の分析](../media/d0372978-ce08-4f4e-a1fc-aa918ae44364.png)
  
<span data-ttu-id="91e85-110">表示されるタスクは、選択したオプションによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="91e85-110">The tasks displayed may vary depending on the options selected.</span></span> 
  
- <span data-ttu-id="91e85-111">**ND/ET: setup**: 実行の準備 (実行パラメーターやケース パラメーターなど) を設定します。</span><span class="sxs-lookup"><span data-stu-id="91e85-111">**ND/ET: setup**: Prepares for the run, for example, sets run and case parameters.</span></span>
    
- <span data-ttu-id="91e85-112">**ND/ET: ND 計算**: ファイルのほぼ重複した分析を処理します。</span><span class="sxs-lookup"><span data-stu-id="91e85-112">**ND/ET: ND calculation**: Processes Near-duplicate analysis of files.</span></span>
    
- <span data-ttu-id="91e85-113">**ND/ET: ET 計算**: 電子メール セット全体に対して電子メール スレッド分析を実行します。</span><span class="sxs-lookup"><span data-stu-id="91e85-113">**ND/ET: ET calculation**: Performs Email Thread analysis on the entire email set.</span></span>
    
- <span data-ttu-id="91e85-114">**ND/ET: ピボットと類似** 性 : ピボットとファイルの類似処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="91e85-114">**ND/ET: pivots and similarities**: Performs pivot and file similarity processing.</span></span>
    
- <span data-ttu-id="91e85-115">**ND/ET: メタデータ更新**: データベース内のファイルに収集された新しいデータを最終処理します。</span><span class="sxs-lookup"><span data-stu-id="91e85-115">**ND/ET: metadata update**: Finalizes the new data collected on the files in the database.</span></span>
    
- <span data-ttu-id="91e85-116">**テーマ: テーマの計算**: テーマ分析を実行します。</span><span class="sxs-lookup"><span data-stu-id="91e85-116">**Themes: themes calculation**: Runs themes analysis.</span></span> <span data-ttu-id="91e85-117">(選択されている場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="91e85-117">(Displayed only if selected.)</span></span>
    
- <span data-ttu-id="91e85-118">**タスクの状態**: この行は、タスクの完了後に表示されます。</span><span class="sxs-lookup"><span data-stu-id="91e85-118">**Task status**: This line is displayed after task completion.</span></span> <span data-ttu-id="91e85-119">タスクの実行中は、実行期間が表示されます。</span><span class="sxs-lookup"><span data-stu-id="91e85-119">While tasks are running, run duration is displayed.</span></span>
    
> [!NOTE]
> <span data-ttu-id="91e85-120">近重複および電子メール スレッド (ND および ED) の分析結果は、処理するドキュメントの数に適用されます。</span><span class="sxs-lookup"><span data-stu-id="91e85-120">The Analyze results of Near-duplicates and Email Threads (ND and ED) applies to the number of documents to be processed.</span></span> <span data-ttu-id="91e85-121">このファイルには、完全に重複するファイルは含まれます。</span><span class="sxs-lookup"><span data-stu-id="91e85-121">It does not include Exact duplicate files.</span></span> 
  
## <a name="view-near-duplicates-and-email-threads-status"></a><span data-ttu-id="91e85-122">近重複および電子メール スレッドの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="91e85-122">View Near-duplicates and Email Threads status</span></span>

<span data-ttu-id="91e85-123">ターゲット **母** 集団の結果には、ターゲット母集団内のドキュメント、電子メール、添付ファイル、およびエラーの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="91e85-123">The **Target** population results display the number of documents, emails, attachments, and errors in the target population.</span></span> 
  
<span data-ttu-id="91e85-124">ドキュメント **の結果には** 、ピボットの数、一意の近くの重複、および正確な重複ファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="91e85-124">The **Documents** results display the number of pivots, unique near-duplicates, and exact duplicate files.</span></span> 
  
<span data-ttu-id="91e85-125">電子 **メールの結果** には、包括性を含む負の数、一意の包括的コピー、および電子メール メッセージの残りの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="91e85-125">The **Emails** results display the number of inclusive, inclusive minus, unique inclusive copies, and the rest of the email messages.</span></span> <span data-ttu-id="91e85-126">電子メールの結果の種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="91e85-126">The different types of email results are:</span></span> 
  
- <span data-ttu-id="91e85-127">**包括**: 包括的な電子メールは、電子メール スレッドの終了ノードであり、そのスレッドの以前のすべての履歴が含まれています。</span><span class="sxs-lookup"><span data-stu-id="91e85-127">**Inclusive**: An inclusive email is the terminating node in an email thread and contains all the previous history of that thread.</span></span> <span data-ttu-id="91e85-128">その結果、レビューアーはスレッド内の以前のメッセージを読む必要なく、包括的なメールに安全に集中できます。</span><span class="sxs-lookup"><span data-stu-id="91e85-128">As a result, the reviewer can safely focus on the inclusive email, without the need to read the previous messages in the thread.</span></span> 
    
- <span data-ttu-id="91e85-129">**包括的なマイナス**: 包括的なメッセージの親に関連付けられている添付ファイルが 1 つ以上ある場合、包括的な電子メールは包括的なマイナスとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="91e85-129">**Inclusive minus**: An inclusive email is designated as inclusive minus if there are one or more different attachments associated with the parents of the inclusive message.</span></span> <span data-ttu-id="91e85-130">このコンテキストでは、Parent という用語は、電子メール スレッド上のメッセージ、または特定の包括的な電子メールに含まれる会話に使用されます。</span><span class="sxs-lookup"><span data-stu-id="91e85-130">In this context, the term Parent is used for messages located upwards on the email thread or conversations included in that specific inclusive email.</span></span> <span data-ttu-id="91e85-131">レビュー者は、包括的なメールの親のコンテンツを確認する必要はないが、包括的なパスの親に関連付けられている添付ファイルを確認すると役立つ可能性があるというシグナルとして、包括的な負符号を使用できます。</span><span class="sxs-lookup"><span data-stu-id="91e85-131">A reviewer can use the inclusive minus indication as a signal that although it might not be necessary to review the content of the inclusive email parents, it may be useful to review the attachments associated with the inclusive path parents.</span></span> 
    
- <span data-ttu-id="91e85-132">**包括コピー**: 包括的または包括的なマイナスとしてマークされている別のメッセージのコピーである場合、包括的な電子メールが包括コピーとして指定されます。</span><span class="sxs-lookup"><span data-stu-id="91e85-132">**Inclusive copy**: An inclusive email is designated as inclusive copy if it's the copy of another message marked as inclusive or inclusive minus.</span></span> <span data-ttu-id="91e85-133">つまり、このメッセージの件名と本文は別の包括的なメッセージと同じであり、同じノードに存在します。</span><span class="sxs-lookup"><span data-stu-id="91e85-133">In other words, this message has the same subject and body as another inclusive message and, as such, co-resides in the same node.</span></span> <span data-ttu-id="91e85-134">包括コピー メッセージには同じコンテンツが含まれるため、通常はレビュー プロセスでスキップできます。</span><span class="sxs-lookup"><span data-stu-id="91e85-134">Because inclusive copy messages contain the same content, they can usually be skipped in the review process.</span></span> 
    
- <span data-ttu-id="91e85-135">**残り**: これは、一意のコンテンツが含まれているので、前の 3 つのカテゴリに分類できないメールを示します。</span><span class="sxs-lookup"><span data-stu-id="91e85-135">**The rest**: This indicates email that doesn't contain any unique content, and therefore doesn't fall into any of the previous three categories.</span></span> <span data-ttu-id="91e85-136">これらの電子メール メッセージを確認する必要はない。</span><span class="sxs-lookup"><span data-stu-id="91e85-136">These email messages don't need to be reviewed.</span></span> <span data-ttu-id="91e85-137">後の包括的な電子メールに含まれている添付ファイルがメッセージに含まれている場合は、添付ファイルの確認が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="91e85-137">If a message contains an attachment that isn't on a later inclusive email, then the attachment might need to be reviewed.</span></span> <span data-ttu-id="91e85-138">これは、スレッド内に包括的なマイナス電子メールが存在することで示されます。</span><span class="sxs-lookup"><span data-stu-id="91e85-138">This is indicated by the existence of an inclusive minus email within the thread.</span></span>
    
<span data-ttu-id="91e85-139">添付 **ファイルの** 結果には、一意の添付ファイルや重複ファイルなどの種類に従って、添付ファイルの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="91e85-139">The **Attachments** results display the number of attachments, according to such type as unique and duplicates.</span></span> 
  
![類似および電子メールのスレッド](../media/54491303-0ee3-4739-b42e-d1ee486842fd.png)
  
## <a name="see-also"></a><span data-ttu-id="91e85-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="91e85-141">See also</span></span>

[<span data-ttu-id="91e85-142">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="91e85-142">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="91e85-143">ドキュメントの類似性について</span><span class="sxs-lookup"><span data-stu-id="91e85-143">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="91e85-144">分析オプションの設定</span><span class="sxs-lookup"><span data-stu-id="91e85-144">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="91e85-145">テキストを無視する設定</span><span class="sxs-lookup"><span data-stu-id="91e85-145">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="91e85-146">分析の詳細設定の設定</span><span class="sxs-lookup"><span data-stu-id="91e85-146">Setting Analyze advanced settings</span></span>](view-analyze-results-in-advanced-ediscovery.md)

