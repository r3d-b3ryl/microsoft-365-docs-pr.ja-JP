---
title: Advanced eDiscovery で分析の [テキストを無視する] オプションを設定する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: Advanced eDiscovery の分析モジュールとプロセス モジュールを使用するときに、特定のテキストを無視するルールを定義する方法について説明します。
ms.openlocfilehash: f61724e3964ff4ba7f099dbfb4411e19db258adc
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663472"
---
# <a name="set-ignore-text-option-for-analyze-in-advanced-ediscovery-classic"></a><span data-ttu-id="4a779-103">Advanced eDiscovery (クラシック) で分析の [テキストを無視する] オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="4a779-103">Set Ignore Text option for Analyze in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="4a779-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="4a779-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="4a779-106">テキストを無視する機能は、Advanced eDiscovery モジュールのすべてまたは任意に適用できます。分析 (近重複、電子メール スレッド、テーマ) および関連性。</span><span class="sxs-lookup"><span data-stu-id="4a779-106">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance.</span></span> <span data-ttu-id="4a779-107">無視されたテキストは、関連性に表示されるファイルには表示されません。分析/計算では、無視されたテキストは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="4a779-107">Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="4a779-108">既に実行されているモジュールに対して [テキストを無視] 機能が既に定義されている場合、[テキストを無視] 設定は変更されません。</span><span class="sxs-lookup"><span data-stu-id="4a779-108">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified.</span></span> <span data-ttu-id="4a779-109">ただし、関連性モジュールの [テキストを無視] 機能は、いつでも変更できます。</span><span class="sxs-lookup"><span data-stu-id="4a779-109">However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="4a779-110">[テキストを無視する] フィルターの適用方法</span><span class="sxs-lookup"><span data-stu-id="4a779-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="4a779-111">複数の無視テキスト フィルターが入力された順序で適用されます。</span><span class="sxs-lookup"><span data-stu-id="4a779-111">Multiple Ignore Text filters are applied in the order that they were entered.</span></span> <span data-ttu-id="4a779-112">適用する順序を変更するには、削除して目的の順序で再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a779-112">To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="4a779-113">たとえば、テキスト コンテンツが "DAVE BOB ALICE CAROLEVE" の場合、無視するテキスト エントリのサンプルと、これらのエントリによって生成される結果を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4a779-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results these entries produce:</span></span>

|<span data-ttu-id="4a779-114">**テキスト のエントリを無視する**</span><span class="sxs-lookup"><span data-stu-id="4a779-114">**Ignore Text entries**</span></span> <br/> |<span data-ttu-id="4a779-115">**結果**</span><span class="sxs-lookup"><span data-stu-id="4a779-115">**Results**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="4a779-116">"ALICE"、"BOB CAROL"</span><span class="sxs-lookup"><span data-stu-id="4a779-116">"ALICE", "BOB CAROL"</span></span>  <br/> |<span data-ttu-id="4a779-117">"DAVEEVE"</span><span class="sxs-lookup"><span data-stu-id="4a779-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="4a779-118">"ALICE"、"BOB ALICE CAROL"</span><span class="sxs-lookup"><span data-stu-id="4a779-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |<span data-ttu-id="4a779-119">"DAVE BOB CAROLEVE"</span><span class="sxs-lookup"><span data-stu-id="4a779-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="4a779-120">2 番目の Ignore Text エントリは、最初の無視テキストが適用された後にこのような文字列が見つからないため、実装されていません。</span><span class="sxs-lookup"><span data-stu-id="4a779-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="4a779-121">無視するテキストを定義するときに正規表現を使用する</span><span class="sxs-lookup"><span data-stu-id="4a779-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="4a779-122">Ignore Text を定義する場合は、正規表現がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4a779-122">Regular expressions are supported for use when defining Ignore Text.</span></span> <span data-ttu-id="4a779-123">正規表現の構文と使用方法の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="4a779-123">The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="4a779-124">行の末尾まで Begin からテキストを削除 (無視) するには:</span><span class="sxs-lookup"><span data-stu-id="4a779-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="4a779-125">ここで、"Begin" は行内でこの文字列が最初に出現します。</span><span class="sxs-lookup"><span data-stu-id="4a779-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="4a779-126">たとえば、次のテキストの場合:</span><span class="sxs-lookup"><span data-stu-id="4a779-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="4a779-127">**"これは最初の文と最初の行です。**</span><span class="sxs-lookup"><span data-stu-id="4a779-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="4a779-128">**これは 2 番目の文と 2 行目です"**</span><span class="sxs-lookup"><span data-stu-id="4a779-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="4a779-129">正規表現 first(. \* )$ を指定すると、次の結果が返されます。</span><span class="sxs-lookup"><span data-stu-id="4a779-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="4a779-130">**"これは次の場合です。**</span><span class="sxs-lookup"><span data-stu-id="4a779-130">**"This is**</span></span>
    
    <span data-ttu-id="4a779-131">**これは 2 番目の文と 2 行目です"**</span><span class="sxs-lookup"><span data-stu-id="4a779-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="4a779-132">電子メール スレッドの末尾に自動的に挿入される免責事項と法的声明を削除するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4a779-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="4a779-133">ここで、"Begin" と "End" は、ラップされたテキスト段落の先頭と末尾に一意の文字列です。</span><span class="sxs-lookup"><span data-stu-id="4a779-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="4a779-134">たとえば、次の正規表現は、Begin 文字列と End 文字列の間の電子メール スレッドに含めらた免責事項と法的ステートメントを削除します。</span><span class="sxs-lookup"><span data-stu-id="4a779-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="4a779-135">**このメッセージには機密情報 (.|\s) \* 検証が必要な場合は、ハード コピー バージョンを要求してください**</span><span class="sxs-lookup"><span data-stu-id="4a779-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="4a779-136">免責事項 (特殊文字を含む) を削除するには:</span><span class="sxs-lookup"><span data-stu-id="4a779-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="4a779-137">たとえば、次のテキストの場合 (ここで x で表される免責事項を含む)。</span><span class="sxs-lookup"><span data-stu-id="4a779-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="4a779-138">**/\*\ このメッセージには機密情報が含まれている。xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="4a779-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="4a779-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="4a779-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="4a779-140">\**xxxx xxxx 検証が必要な場合は、ハード コピー バージョンを要求してください。/\*\**</span><span class="sxs-lookup"><span data-stu-id="4a779-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="4a779-141">上記の免責事項を削除する正規表現は次のようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a779-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="4a779-142">**\/\\*\\このメッセージには機密情報 \. (.|\s) \* 検証が必要な場合は、ハード コピー バージョンを要求してください \.\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="4a779-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="4a779-143">正規表現ルール:</span><span class="sxs-lookup"><span data-stu-id="4a779-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="4a779-144">スペース、"_"、および "-" 以外のアルファベットの一部ではない文字の前に " が必要です \" 。</span><span class="sxs-lookup"><span data-stu-id="4a779-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="4a779-145">通常の eExpression フィールドの長さは無制限です。</span><span class="sxs-lookup"><span data-stu-id="4a779-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="4a779-146">正規表現の説明と詳細な構文については、「正規表現言語 - クイック [リファレンス」を参照してください](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4a779-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="4a779-147">テキスト無視ルールの定義</span><span class="sxs-lookup"><span data-stu-id="4a779-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="4a779-148">[分析 **の \> 管理 \> ] オプション タブ** の[テキストを無視] セクションで、アイコンをクリックして **+** ルールを追加します。</span><span class="sxs-lookup"><span data-stu-id="4a779-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="4a779-149">[テキスト **を無視して** 追加] ダイアログの **[名前** ] フィールドに、無視するテキスト ルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4a779-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![無視されたテキストの追加](../media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="4a779-151">[テキスト **] ボックス** に、無視するテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="4a779-151">In the **Text** box, type the text to be ignored.</span></span> <span data-ttu-id="4a779-152">テキスト フィールドでは、文字数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="4a779-152">The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="4a779-153">上のウィンドウに示すように、ライト ライト ライト **を** クリックすると、テキストを無視するルールの一般的な構文ガイドラインが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a779-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="4a779-154">必要に応 **じて、[** 大文字と小文字を区別する] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4a779-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="4a779-155">[適用 **先] ボックスの** 一覧で、定義を適用する Advanced eDiscovery モジュールを選択します。</span><span class="sxs-lookup"><span data-stu-id="4a779-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="4a779-156">サンプル テキストでテストを実行する場合は、[入力] テキストボックスにサンプル テキストを入力し、[テスト] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="4a779-156">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**.</span></span> <span data-ttu-id="4a779-157">結果が [出力] テキスト **ボックスに** 表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a779-157">The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="4a779-158">**[OK] を** クリックして [テキストを無視] ルールを保存します。</span><span class="sxs-lookup"><span data-stu-id="4a779-158">Click **OK** to save the Ignore Text rule.</span></span> <span data-ttu-id="4a779-159">定義されている無視テキスト ルールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a779-159">The defined Ignore Text rule is displayed.</span></span> 
    
    ![無視されたテキスト名を設定する](../media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="4a779-161">関連項目</span><span class="sxs-lookup"><span data-stu-id="4a779-161">See also</span></span>

[<span data-ttu-id="4a779-162">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="4a779-162">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="4a779-163">ドキュメントの類似性について</span><span class="sxs-lookup"><span data-stu-id="4a779-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4a779-164">分析オプションの設定</span><span class="sxs-lookup"><span data-stu-id="4a779-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4a779-165">分析の詳細設定の設定</span><span class="sxs-lookup"><span data-stu-id="4a779-165">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="4a779-166">分析結果の表示</span><span class="sxs-lookup"><span data-stu-id="4a779-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

