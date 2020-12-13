---
title: Advanced eDiscovery で分析の詳細設定を設定する
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
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: Advanced eDiscovery の分析プロセスで、近重複、電子メール スレッド、テーマなどの高度な設定を構成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ac1300eb26338691722d9ccd15269ccf7f964f58
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663492"
---
# <a name="set-analyze-advanced-settings-in-advanced-ediscovery"></a><span data-ttu-id="53e52-103">Advanced eDiscovery で分析の詳細設定を設定する</span><span class="sxs-lookup"><span data-stu-id="53e52-103">Set Analyze advanced settings in Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="53e52-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="53e52-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="53e52-106">Advanced eDiscovery は、分析モジュール設定の既定の高度なパラメーターを提供します。</span><span class="sxs-lookup"><span data-stu-id="53e52-106">Advanced eDiscovery provides default advanced parameters for Analyze module settings.</span></span> <span data-ttu-id="53e52-107">以下の手順では、指定できる設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="53e52-107">The following procedure describes settings that can be specified.</span></span>
  
1. <span data-ttu-id="53e52-108">[セットアップ **の \> 分析 \> の** 準備] タブで、[詳細設定] **(ページ** の下部) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53e52-108">In the **Prepare \> Analyze \> Setup** tab, click **Advanced settings** (at the bottom of the page).</span></span> <span data-ttu-id="53e52-109">次のパネルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="53e52-109">The following panel is displayed.</span></span> 
    
    ![分析設定の拡張設定](../media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. <span data-ttu-id="53e52-111">[ **近重複] および [電子メール** スレッド] パラメーターで、必要に応じて次の値を選択します。</span><span class="sxs-lookup"><span data-stu-id="53e52-111">In **Near-duplicates and Email threads parameters**, select values for the following as necessary:</span></span>
    
  - <span data-ttu-id="53e52-112">**最小単語数**: 単語の最小数。その下のファイルは、ほぼ重複分析のために送信されません。</span><span class="sxs-lookup"><span data-stu-id="53e52-112">**Minimum number of words**: Minimum number for words, below which a file is not submitted for Near-duplicate analysis.</span></span> 
    
  - <span data-ttu-id="53e52-113">**単語の最大数**: ほぼ重複分析のためにファイルが送信されない単語の最大数。</span><span class="sxs-lookup"><span data-stu-id="53e52-113">**Maximum number of words**: Maximum number for words, above which a file is not submitted for Near-duplicate analysis.</span></span>
    
  - <span data-ttu-id="53e52-114">**メールの類似** 性 : 2 つのメールが類似と見なされる最小限のレベルの再送信。</span><span class="sxs-lookup"><span data-stu-id="53e52-114">**Email similarity**: Minimal level of resemblance for two emails to be considered similar.</span></span> <span data-ttu-id="53e52-115">値は常にドキュメントの類似性と等しいか、ドキュメントの類似性よりも大きくなります。</span><span class="sxs-lookup"><span data-stu-id="53e52-115">Value is always equal to, or larger than document similarity.</span></span> <span data-ttu-id="53e52-116">既定値は 90% です。</span><span class="sxs-lookup"><span data-stu-id="53e52-116">Default is 90%.</span></span>
    
3. <span data-ttu-id="53e52-117">**Themes パラメーターで、[** テーマ分析に数値を含める] チェック ボックスをオンにして、分析中のテーマの処理に数値を含める。</span><span class="sxs-lookup"><span data-stu-id="53e52-117">In **Themes parameters**, select the **Include numbers in theme analysis** check box to include numbers in the processing of Themes during Analyze.</span></span> 
    
4. <span data-ttu-id="53e52-118">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53e52-118">Click **Save**.</span></span> 
    
## <a name="related-topics"></a><span data-ttu-id="53e52-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="53e52-119">Related topics</span></span>

[<span data-ttu-id="53e52-120">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="53e52-120">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="53e52-121">ドキュメントの類似性について</span><span class="sxs-lookup"><span data-stu-id="53e52-121">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="53e52-122">分析オプションの設定</span><span class="sxs-lookup"><span data-stu-id="53e52-122">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="53e52-123">テキストを無視する設定</span><span class="sxs-lookup"><span data-stu-id="53e52-123">Setting ignore text</span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="53e52-124">分析結果の表示</span><span class="sxs-lookup"><span data-stu-id="53e52-124">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

