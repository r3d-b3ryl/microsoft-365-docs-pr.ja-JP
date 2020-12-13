---
title: Advanced eDiscovery でのドキュメントの類似性を理解する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: Advanced eDiscovery で、2 つのファイルの最小レベルであるドキュメントの類似性の値が類似度と見なされるしくみについて確認します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 22eb27e7afdc6ad37ea6fdcba9b64298906f1c35
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663316"
---
# <a name="understand-document-similarity-in-advanced-ediscovery-classic"></a><span data-ttu-id="7266f-103">Advanced eDiscovery (クラシック) でのドキュメントの類似性について理解する</span><span class="sxs-lookup"><span data-stu-id="7266f-103">Understand document similarity in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="7266f-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="7266f-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="7266f-106">Advanced eDiscovery では、ドキュメントの類似性は、2 つのドキュメントをほぼ重複と見なすのに必要な最小限のレベルの再送信です。</span><span class="sxs-lookup"><span data-stu-id="7266f-106">In Advanced eDiscovery, Document Similarity is the minimal level of resemblance required for two documents to be considered as near-duplicates.</span></span>
  
> [!TIP]
> <span data-ttu-id="7266f-107">ほとんどのビジネス アプリケーションでは、Similarity 値 60% ~ 75% を使用する方が推奨されます。</span><span class="sxs-lookup"><span data-stu-id="7266f-107">For most business applications, it is recommended to use a Similarity value of 60%-75%.</span></span> <span data-ttu-id="7266f-108">品質が非常に低い光学式文字認識 (OCR) マテリアルの場合は、低い Similarity 値を適用できます。</span><span class="sxs-lookup"><span data-stu-id="7266f-108">For very poor quality optical character recognition (OCR) material, lower Similarity values can be applied.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7266f-109">特定のケースに対して設定して実行した後、Similarity 値を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="7266f-109">After it's set and run for a given case, the Similarity value cannot be changed.</span></span> 
  
<span data-ttu-id="7266f-110">類似度のしきい値を下回るレベルのドキュメントが Near-duplicate (ND) セット内にある場合があります。</span><span class="sxs-lookup"><span data-stu-id="7266f-110">Within a Near-duplicate (ND) set, there may be documents with a level of resemblance below the Similarity threshold.</span></span> <span data-ttu-id="7266f-111">ND セットを結合するドキュメントの場合、ND セットには、レベルが Similarity を超えるレベルのドキュメントが少なくとも 1 つ必要です。</span><span class="sxs-lookup"><span data-stu-id="7266f-111">For a document to join an ND set, there must be at least one document in the ND set with a level of resemblance exceeding the Similarity.</span></span> 
  
<span data-ttu-id="7266f-112">たとえば、Similarity が 80% に設定され、ドキュメント F1 が 85% のレベルでドキュメント F2 に似ていて、ドキュメント F2 が 90% のレベルでドキュメント F3 に似ているとします。</span><span class="sxs-lookup"><span data-stu-id="7266f-112">For example, assume the Similarity is set to 80%, document F1 resembles document F2 at a level of 85%, and document F2 resembles document F3 at a level of 90%.</span></span> 
  
<span data-ttu-id="7266f-113">ただし、ドキュメント F1 は、しきい値を下回る 70% のレベルでドキュメント F3 に似ている場合があります。</span><span class="sxs-lookup"><span data-stu-id="7266f-113">However, document F1 may resemble document F3 at a level of only 70%, which is below the threshold.</span></span> <span data-ttu-id="7266f-114">ただし、この例では、ドキュメント F1、F2、および F3 はすべて 1 つの ND セットに表示されます。</span><span class="sxs-lookup"><span data-stu-id="7266f-114">Nonetheless, in this example, documents F1, F2, and F3 all appear in the one ND set.</span></span> <span data-ttu-id="7266f-115">同様に、Similarity 値 80% を使用して、EquiSet-1 と EquiSet-2 の 2 つのセットを作成した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7266f-115">Similarly, using a Similarity value of 80%, we may have created two sets, EquiSet-1 and EquiSet-2.</span></span> <span data-ttu-id="7266f-116">EquiSet-1 には、E1 および E2 のドキュメントが含まれる。</span><span class="sxs-lookup"><span data-stu-id="7266f-116">EquiSet-1 contains documents E1 and E2.</span></span> <span data-ttu-id="7266f-117">Equiset-2 には、F1、F2、および F3 のドキュメントが含まれる。</span><span class="sxs-lookup"><span data-stu-id="7266f-117">Equiset-2 contains documents F1, F2, and F3.</span></span> 
  
<span data-ttu-id="7266f-118">次に、再定義のレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="7266f-118">The levels of resemblance are illustrated as follows:</span></span>
  
![ドキュメントの類似性](../media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
<span data-ttu-id="7266f-120">別の文書 X1 が挿入されたとします。</span><span class="sxs-lookup"><span data-stu-id="7266f-120">Assume that another document, X1, is now inserted.</span></span> <span data-ttu-id="7266f-121">X1 と E3 の間の再送信は 87% です。</span><span class="sxs-lookup"><span data-stu-id="7266f-121">The resemblance between X1 and E3 is 87%.</span></span> <span data-ttu-id="7266f-122">同様に、X1 と F1 の間の再表示は 92% です。</span><span class="sxs-lookup"><span data-stu-id="7266f-122">Similarly, the resemblance between X1 and F1 is 92%.</span></span> <span data-ttu-id="7266f-123">その結果、EquiSet -1、EquiSet -2、X1 が 1 つの ND セットに結合されます。</span><span class="sxs-lookup"><span data-stu-id="7266f-123">As a result, EquiSet -1, EquiSet -2, and X1 are now combined into one ND set.</span></span>
  
![ドキュメントの類似性](../media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> <span data-ttu-id="7266f-125">2 つのドキュメントが 1 つの ND セットに割り当てられている場合、追加のドキュメントがセットに追加された場合や、セットが結合された場合でも、同じ ND セット内に 2 つのドキュメントが一緒に残ります。</span><span class="sxs-lookup"><span data-stu-id="7266f-125">If any two documents are assigned to one ND set, they will remain together in the same ND set, even if additional documents are added to the set or if the sets are merged.</span></span> 
  
<span data-ttu-id="7266f-126">セットを結合すると、ピボット ドキュメントは、新しいドキュメントがセットに追加される際に変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7266f-126">After sets are merged, the Pivot document can change when new documents are added to a set.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="7266f-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="7266f-127">Related topics</span></span>

[<span data-ttu-id="7266f-128">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="7266f-128">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7266f-129">分析オプションの設定</span><span class="sxs-lookup"><span data-stu-id="7266f-129">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7266f-130">テキストを無視する設定</span><span class="sxs-lookup"><span data-stu-id="7266f-130">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7266f-131">分析の詳細設定の設定</span><span class="sxs-lookup"><span data-stu-id="7266f-131">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="7266f-132">分析結果の表示</span><span class="sxs-lookup"><span data-stu-id="7266f-132">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

