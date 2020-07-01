---
title: 高度な電子情報開示で強調表示されたキーワードと詳細オプションを定義する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 03cc4387-2c7d-4058-8a44-0deefb58f011
description: ユーザー定義のキーワードを関連性に追加して、上級電子情報開示でのタグ付けの際に関連ファイルを特定し、コストパラメータを指定する方法について説明します。
ms.openlocfilehash: 61ec74109f13d8056047e0aaf14aaa87c846e17f
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936456"
---
# <a name="define-highlighted-keywords-and-advanced-options-in-advanced-ediscovery-classic"></a><span data-ttu-id="7449e-103">高度な電子情報開示で強調表示されたキーワードと詳細オプションを定義する (クラシック)</span><span class="sxs-lookup"><span data-stu-id="7449e-103">Define highlighted keywords and advanced options in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="7449e-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span><span class="sxs-lookup"><span data-stu-id="7449e-104">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization.</span></span> <span data-ttu-id="7449e-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="7449e-105">If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="7449e-106">詳細な電子情報開示では、ユーザー定義のキーワードを関連性に追加して、タグ付けの際に関連ファイルを識別するのに役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="7449e-106">In Advanced eDiscovery, it's possible to add user-defined keywords to Relevance in order to help you identify relevant files while tagging.</span></span> <span data-ttu-id="7449e-107">キーワードは、**関連性 \> タグ**の指定した色で表示されます。</span><span class="sxs-lookup"><span data-stu-id="7449e-107">Keywords will be displayed in the specified colors in **Relevance \> Tag**.</span></span> 
  
<span data-ttu-id="7449e-108">以下に示すように、キーワードリストを追加したり、キーワードリストに割り当てられている色や関連する問題を追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="7449e-108">As described below, keyword lists can be added, and colors assigned to the Keywords list and the related issues.</span></span> <span data-ttu-id="7449e-109">ヒントには、キーワードの説明 (存在する場合) が、二重下線で示されます。</span><span class="sxs-lookup"><span data-stu-id="7449e-109">A tooltip displays the keyword's description, if one exists, as indicated by a double underline.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7449e-110">関連性のタグ付け時にドキュメント内の関連性の強調表示とキーワードヒット結果の表示は、日本語、中国語、韓国語の2バイト文字セットでは機能しません。</span><span class="sxs-lookup"><span data-stu-id="7449e-110">Hit highlighting in Relevance and viewing keyword hit results within documents during Relevance tagging does not work for the Japanese, Chinese, and Korean double-byte character sets.</span></span> 
  
## <a name="adding-highlighted-keywords"></a><span data-ttu-id="7449e-111">強調表示されたキーワードの追加</span><span class="sxs-lookup"><span data-stu-id="7449e-111">Adding highlighted keywords</span></span>

1. <span data-ttu-id="7449e-112">[**関連性の \> 関連性の設定**] タブで、[**強調表示**されたキーワード] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7449e-112">In the **Relevance \> Relevance setup** tab, select **Highlighted keywords**.</span></span>
    
2. <span data-ttu-id="7449e-113">アイコンをクリックして **+** キーワードを追加します。</span><span class="sxs-lookup"><span data-stu-id="7449e-113">Click the **+** icon to add keywords.</span></span> <span data-ttu-id="7449e-114">[**新しいキーワードの追加**] ダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7449e-114">The **Add new keywords** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="7449e-115">[**キーワード**] にキーワードリストを入力します。キーワードはコンマで区切ります。</span><span class="sxs-lookup"><span data-stu-id="7449e-115">In **Keywords**, type the keywords list, separating keywords with commas.</span></span> 
    
4. <span data-ttu-id="7449e-116">[**色**] ボックスの一覧で色を選択し、[入力したキーワード] ボックスの一覧を強調表示にします。</span><span class="sxs-lookup"><span data-stu-id="7449e-116">In the **Color** list, select the color to highlight the entered keywords list.</span></span> 
    
5. <span data-ttu-id="7449e-117">**[問題の選択**] リストで、[キーワード] リストを [すべての問題] に適用するか、選択した案件に適用するかを選択します。</span><span class="sxs-lookup"><span data-stu-id="7449e-117">In the **Select issue** list, select whether to apply the keywords list to "All issues" or to selected issues.</span></span> 
    
6. <span data-ttu-id="7449e-118">[**説明**] に、キーワードリスト (省略可能) を入力します。</span><span class="sxs-lookup"><span data-stu-id="7449e-118">In **Description**, type the keywords list (optional).</span></span>
    
    ![新しいキーワードの追加](../media/1683a71f-0875-48fc-b4ef-01f3b0e8e8e9.png)
  
7. <span data-ttu-id="7449e-120">完了したら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7449e-120">Click **OK** when done.</span></span> <span data-ttu-id="7449e-121">作成したリストがキーワードリストテーブルに追加され、編集または削除できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7449e-121">The created list is added to the keywords list table and can be edited or deleted.</span></span> 
    
    ![関連性の設定のキーワードの一覧](../media/a05d5ec0-8bde-470d-97e2-456b169281d6.png)
  
<span data-ttu-id="7449e-123">ユーザー定義のキーワードが、[関連性] タグの指定した色で表示され \> ます。</span><span class="sxs-lookup"><span data-stu-id="7449e-123">The user-defined keywords will be displayed, in the specified colors in Relevance \> Tag.</span></span> 
  
## <a name="specifying-relevance-setup-advanced-settings"></a><span data-ttu-id="7449e-124">関連性セットアップの詳細設定の指定</span><span class="sxs-lookup"><span data-stu-id="7449e-124">Specifying Relevance setup advanced settings</span></span>

<span data-ttu-id="7449e-125">これらの設定は、関連性のあるトラックと判断グラフに影響します。</span><span class="sxs-lookup"><span data-stu-id="7449e-125">These settings affect the Track and Decide graphs in Relevance.</span></span>
  
1. <span data-ttu-id="7449e-126">[**関連性の \> 関連性の設定**] タブで、[**詳細設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="7449e-126">In the **Relevance \> Relevance setup** tab, select **Advanced settings**.</span></span>
    
2. <span data-ttu-id="7449e-127">[**コストパラメーター** ] ダイアログで、次のように選択します。</span><span class="sxs-lookup"><span data-stu-id="7449e-127">In the **Cost parameters** dialog, make the following selections:</span></span> 
    
1. <span data-ttu-id="7449e-128">1**時間あたりのコストレビュー ($)** の一覧で、[金額] を選択するか、既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="7449e-128">In the **Cost review per hour ($)** list, select the amount in dollars or accept the default.</span></span> 
    
2. <span data-ttu-id="7449e-129">[**時間で確認されたファイルの数**] ボックスの一覧で、金額を選択するか、既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="7449e-129">In the **Number of files reviewed by hour** list, select the amount or accept the default.</span></span> 
    
    ![関連性の設定のコストのパラメーター](../media/bab7b5b7-6297-4e7c-b0a6-ba5aa8b21787.png)
  
3. <span data-ttu-id="7449e-131">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7449e-131">Click **Save**.</span></span> <span data-ttu-id="7449e-132">選択した設定が保存されます。</span><span class="sxs-lookup"><span data-stu-id="7449e-132">The selected settings are saved.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7449e-133">関連項目</span><span class="sxs-lookup"><span data-stu-id="7449e-133">See also</span></span>

[<span data-ttu-id="7449e-134">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="7449e-134">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7449e-135">問題の定義とユーザーの割り当て</span><span class="sxs-lookup"><span data-stu-id="7449e-135">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="7449e-136">インポートしたファイルを追加するためのロードの設定</span><span class="sxs-lookup"><span data-stu-id="7449e-136">Setting up loads to add imported files</span></span>](set-up-loads-to-add-imported-files.md)

