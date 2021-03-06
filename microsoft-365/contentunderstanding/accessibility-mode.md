---
title: 'SharePoint Syntex アクセシビリティ モード '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: SharePoint Syntex でモデルをトレーニングするときにアクセシビリティ モードを使用する方法について説明します。
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515150"
---
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="4c8ef-103">SharePoint Syntex アクセシビリティ モード</span><span class="sxs-lookup"><span data-stu-id="4c8ef-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="4c8ef-104">[SharePoint Syntex](index.md)では、サンプル ドキュメントを操作するときに、モデル トレーニングのすべての段階 (ラベル、トレーニング、テスト) でアクセシビリティ モードを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="4c8ef-105">アクセシビリティ モードを使用すると、ユーザーがドキュメント ビューアーで項目を移動およびラベル付けする場合に、ユーザーがキーボードのアクセシビリティを簡単に行えるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="4c8ef-106">これにより、ユーザーはキーボードを使用してドキュメント ビューアー内のテキスト内を移動したり、選択した値だけでなく、アクション (選択したテキストからのラベル付けや削除など) のナレーションや、追加のサンプル ドキュメントを使用してモデルをトレーニングする場合の予測ラベル値を聞くことができます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![アクセシビリティ モード](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="4c8ef-108">要件</span><span class="sxs-lookup"><span data-stu-id="4c8ef-108">Requirements</span></span>

<span data-ttu-id="4c8ef-109">ナレーションの音声を聞く場合は、Windows 10[](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1)システムのナレーター設定でナレーター アプリをオンにしてください。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![ナレーターを有効にする](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="4c8ef-111">キーボード ユーザーのラベル付け</span><span class="sxs-lookup"><span data-stu-id="4c8ef-111">Labeling for keyboard users</span></span>

<span data-ttu-id="4c8ef-112">アクセシビリティ モードを使用するキーボード ユーザーの場合、ビューアーでサンプル ドキュメントのテキストにラベルを付けする場合は、次のキーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="4c8ef-113">Tab: 前方に移動し、次の単語を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="4c8ef-114">Tab + Shift: 前に移動し、前の単語を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="4c8ef-115">Enter: 選択した単語にラベルを付け、またはラベルを削除します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="4c8ef-116">右矢印: 選択した単語の個々の文字を移動します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-116">Right arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="4c8ef-117">左矢印: 選択した単語の個々の文字を後方に移動します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-117">Left arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="4c8ef-118">1 つのラベルに複数の単語をラベル付けする場合は、各単語にラベルを付けする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="4c8ef-119">ナレーション</span><span class="sxs-lookup"><span data-stu-id="4c8ef-119">Narration</span></span>

<span data-ttu-id="4c8ef-120">ユーザー補助モードを使用するナレーター ユーザーの場合は、キーボード ユーザーがビューアーのサンプル ドキュメントを通過するために説明されているのと同じキーボード ナビゲーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="4c8ef-121">サンプル ドキュメントとラベル文字列値を移動すると、ナレーターはユーザーに次の音声プロンプトを表示します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="4c8ef-122">キーボードを使用してドキュメント ビューアー内を移動すると、ナレーターオーディオに選択した文字列が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="4c8ef-123">選択した文字列内で、ナレーターオーディオは、左矢印キーまたは右矢印キーを使用して選択すると、文字列内の各文字を表示します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the left or right arrow keys.</span></span>
- <span data-ttu-id="4c8ef-124">ラベルが付いた文字列を選択すると、ナレーターは値を表示し、"ラベル付け" します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="4c8ef-125">たとえば、ラベル値が "Contoso" の場合、"Costoso labeled" と表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="4c8ef-126">[トレーニング] タブで、予測されただけの文字列をドキュメント ビューアーで選択すると、ナレーターのオーディオに値が表示され、"予測" されます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="4c8ef-127">これは、トレーニングによって、ユーザーがラベル付けされた値と一致しないファイル内の値を予測するときに発生します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="4c8ef-128">[トレーニング] タブで、ラベル付けおよび予測されたドキュメント ビューアーで文字列を選択すると、ナレーターオーディオに値が表示され、[ラベル付けおよび予測] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="4c8ef-129">これは、トレーニングが成功し、予測値とユーザー ラベルの間に一致する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="4c8ef-130">文字列にラベルが付けられているか、ビューアーでラベルが削除されると、ナレーターオーディオは終了する前に変更を保存する警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="4c8ef-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="4c8ef-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="4c8ef-131">See Also</span></span>

[<span data-ttu-id="4c8ef-132">エクストラクターを作成する</span><span class="sxs-lookup"><span data-stu-id="4c8ef-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="4c8ef-133">分類子を作成する</span><span class="sxs-lookup"><span data-stu-id="4c8ef-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



