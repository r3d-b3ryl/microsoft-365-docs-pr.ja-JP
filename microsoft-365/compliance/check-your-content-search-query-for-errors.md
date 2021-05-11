---
title: 検索クエリでエラーを確認する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
ms.custom: seo-marvel-apr2020
description: 検索を実行する前に、電子情報開示検索のキーワード クエリでエラーと入力ミスを検出する方法について説明します。
ms.openlocfilehash: 9c041ca690df3306347cbca77df3ba9639801245
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311690"
---
# <a name="check-your-search-query-for-errors"></a><span data-ttu-id="ca705-103">検索クエリでエラーを確認する</span><span class="sxs-lookup"><span data-stu-id="ca705-103">Check your search query for errors</span></span>
  
<span data-ttu-id="ca705-104">コンテンツ検索と Core 電子情報開示の検索クエリで確認するサポートされていない文字の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ca705-104">Here's a list of the unsupported characters that we check for in search queries for Content search and Core eDiscovery.</span></span> <span data-ttu-id="ca705-105">サポートされていない文字は非表示の場合が多く、通常、検索エラーが発生したり、意図しない結果を返したりします。</span><span class="sxs-lookup"><span data-stu-id="ca705-105">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="ca705-106">**スマート引用符** - スマートな単一引用符と二重引用符 (巻き引用符とも呼ばれる) はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="ca705-106">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="ca705-107">検索クエリでは、ストレート引用符のみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="ca705-107">Only straight quotation marks can be used in a search query.</span></span> 

- <span data-ttu-id="ca705-108">**印刷不能文字および制御文字** - 印刷不能文字および制御文字は、英数字などの書き込み記号を表しません。</span><span class="sxs-lookup"><span data-stu-id="ca705-108">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as an alpha-numeric character.</span></span> <span data-ttu-id="ca705-109">印刷不可能な文字と制御文字には、テキストを書式設定する文字や個別のテキスト行などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ca705-109">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 

- <span data-ttu-id="ca705-110">**左から右** 、右から左のマーク - これらのマークは、左から右の言語 (英語、スペイン語など) および右から左へ (アラビア語、ヘブライ語など) 言語のテキスト方向を示すために使用されるコントロール文字です。</span><span class="sxs-lookup"><span data-stu-id="ca705-110">**Left-to-right and right-to-left marks** - These marks are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>

- <span data-ttu-id="ca705-111">**小文字のブール演算子**- 検索クエリでAND、OR、NOT などのブール演算子を使用する場合は、大文字にする必要があります。 </span><span class="sxs-lookup"><span data-stu-id="ca705-111">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="ca705-112">クエリで入力ミスが確認された場合、小文字の演算子が使用される場合でも、ブール演算子が使用されているというクエリ構文がよく示されます。たとえば、  `(WordA or WordB) and (WordC or WordD)` .</span><span class="sxs-lookup"><span data-stu-id="ca705-112">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>

## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="ca705-113">クエリにサポートされていない文字がある場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="ca705-113">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="ca705-114">クエリでサポートされていない文字が見つかった場合は、サポートされていない文字が見つかったことを示す警告メッセージが表示され、代替手段が提案されます。</span><span class="sxs-lookup"><span data-stu-id="ca705-114">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters were found and suggests an alternative.</span></span> <span data-ttu-id="ca705-115">次に、元のクエリを保持するか、修正候補クエリに置き換えるオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ca705-115">You then have the option keep the original query or replace it with the suggested revised query.</span></span>

<span data-ttu-id="ca705-116">前のスクリーンショットで検索クエリの入力ミスのクエリを確認するをクリックした後に表示される警告メッセージの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ca705-116">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="ca705-117">元のクエリでスマート引用符と小文字のブール演算子を使用した点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ca705-117">Note the original query used smart quotes and lowercase Boolean operators.</span></span>
  
![クエリの修正候補と一緒に警告メッセージが表示される](../media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="ca705-119">検索クエリでサポートされていない文字を防ぐ方法</span><span class="sxs-lookup"><span data-stu-id="ca705-119">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="ca705-120">サポートされていない文字は、通常、クエリまたはクエリの一部を他のアプリケーション (Microsoft Word や Microsoft Excel など) からコピーし、それらをコンテンツ検索のクエリ ページのキーワード ボックスに貼り付けるときに追加されます。</span><span class="sxs-lookup"><span data-stu-id="ca705-120">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and paste them in the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="ca705-121">サポートされていない文字を使用しないようにする最善の方法は、キーワード ボックスにクエリを入力することです。</span><span class="sxs-lookup"><span data-stu-id="ca705-121">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="ca705-122">または、Word または Web サイトからクエリをコピー Excel、Microsoft ファイルなどのプレーン テキスト エディターに貼り付メモ帳。</span><span class="sxs-lookup"><span data-stu-id="ca705-122">Or you can copy a query from Word or Excel, and then paste it in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="ca705-123">テキスト ファイルを保存し、[エンコード] ドロップダウン **リストで\*\*\*\*[ANSI]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ca705-123">Save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="ca705-124">これにより、すべての書式設定とサポートされない文字が削除されます。</span><span class="sxs-lookup"><span data-stu-id="ca705-124">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="ca705-125">その後、テキスト ファイルからクエリをコピーして、キーワード クエリ ボックスに貼り付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ca705-125">Then you can copy and paste the query from the text file to the keyword query box.</span></span>
