---
title: コンテンツ検索を再試行してコンテンツの場所のエラーを解決する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 調査中に、[再試行] ボタンを使用して、コンテンツの場所にエラーがあるコンテンツ検索を解決できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb85a882ef111aa38a73dbe155a9ad0ef57dd3de
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311822"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a><span data-ttu-id="bb8b5-103">コンテンツ検索を再試行してコンテンツの場所のエラーを解決する</span><span class="sxs-lookup"><span data-stu-id="bb8b5-103">Retry a Content Search to resolve a content location error</span></span>

<span data-ttu-id="bb8b5-104">セキュリティとコンプライアンス センターでコンテンツ検索を使用して多数のメールボックスを検索すると、次のような検索エラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-104">When you use Content Search in the security and compliance center to search a large number of mailboxes, you may get search errors that are similar to the  error:</span></span>

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

<span data-ttu-id="bb8b5-105">これらのエラー (CS001-002、CS003-002、CS008-009、CS012-002、および CS0XX-0XX という形式の他のエラーのエラーを含む) は、コンテンツ検索が特定のコンテンツの場所を検索できなかったかどうかを示します。この例では、2 つのメールボックスが検索されません。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-105">These errors (with error codes of CS001-002, CS003-002, CS008-009, CS012-002, and other errors of the form CS0XX-0XX) indicate that Content Search failed to search specific content locations; in this example, two mailboxes weren't searched.</span></span> <span data-ttu-id="bb8b5-106">これらのエラーは、コンテンツ検索の [状態の詳細] フライアウト ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-106">These errors are displayed on the status details flyout page of the Content Search.</span></span>

## <a name="cause-of-content-location-errors"></a><span data-ttu-id="bb8b5-107">コンテンツの場所エラーの原因</span><span class="sxs-lookup"><span data-stu-id="bb8b5-107">Cause of content location errors</span></span>

<span data-ttu-id="bb8b5-108">多数のメールボックスを検索する場合、検索は Microsoft データセンター内の何千ものサーバーに分散されます。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-108">When searching a large number of mailboxes, the search is distributed across thousands of servers in a Microsoft datacenter.</span></span> <span data-ttu-id="bb8b5-109">一度に、特定のサーバーが再起動状態にあるか、冗長コピーにフェールオーバーする過程にある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-109">At any one time, specific servers could be in reboot state or in the process of failing over to redundant copies.</span></span> <span data-ttu-id="bb8b5-110">どちらの場合も、データを取得するコンテンツ検索の要求はタイム アウトします。前の例では、失敗したメールボックスのエラーは、検索のタイミングアウトの結果です。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-110">In either of these cases, the Content Search's request to retrieve data will time out. In the previous example, the errors for the mailboxes that failed were the result of the search timing out.</span></span>

## <a name="resolving-content-location-errors"></a><span data-ttu-id="bb8b5-111">コンテンツの場所のエラーの解決</span><span class="sxs-lookup"><span data-stu-id="bb8b5-111">Resolving content location errors</span></span>

<span data-ttu-id="bb8b5-112">検索を再開すると、多くの場合、異なるサーバーで同様のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-112">Restarting the search will often result in similar errors on different servers.</span></span> <span data-ttu-id="bb8b5-113">検索を再開する代わりに、検索結果ページの上部に表示される [再試行] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-113">Instead of restarting the search, click the **Retry** button that is displayed at the top of the search results page.</span></span>

![[再試行] ボタンをクリックしてコンテンツの場所のエラーを解決する](../media/retrycontentsearch3.png)

<span data-ttu-id="bb8b5-115">これにより、失敗したメールボックスの検索のみを再試行します。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-115">This will result in the retrying the search only for the mailboxes that failed.</span></span> <span data-ttu-id="bb8b5-116">検索を再試行すると、正常に返された他の結果は保持されます。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-116">When you retry the search, the other results that were successfully returned are retained.</span></span>

## <a name="tips-to-avoid-content-location-errors"></a><span data-ttu-id="bb8b5-117">ヒント場所のエラーを回避する方法</span><span class="sxs-lookup"><span data-stu-id="bb8b5-117">Tips to avoid content location errors</span></span>

<span data-ttu-id="bb8b5-118">コンテンツの場所のエラーの追加の原因と、多数のメールボックスを検索するときにそれらを回避するためのヒントを次に示します。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-118">Here are some additional causes of content location errors and some tips to help you avoid them when searching large numbers of mailboxes.</span></span>

- <span data-ttu-id="bb8b5-119">ユーザーアクティビティが原因で、検索中のメールボックスがビジー状態になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-119">The mailbox being searched might be busy due to user activity.</span></span> <span data-ttu-id="bb8b5-120">この場合、検索サービスは、メールボックスが使用できなくなるのを防ぐために、それ自体を調整する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-120">In this case, the search service might throttle itself to prevent the mailbox from becoming unavailable.</span></span> <span data-ttu-id="bb8b5-121">これを回避するには、営業時間外に検索を実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-121">To avoid this, try running searches during non-business hours.</span></span>

- <span data-ttu-id="bb8b5-122">検索クエリがメールボックスからコンテンツを取得しすぎる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-122">The search query might be retrieving too much content from the mailbox.</span></span> <span data-ttu-id="bb8b5-123">可能であれば、キーワード、日付範囲、および検索条件を使用して検索範囲を絞り込もうとします。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-123">If possible, try to narrow the scope of the search by using keywords, date ranges, and search conditions.</span></span>

- <span data-ttu-id="bb8b5-124">キーワード リストを使用して検索クエリを作成すると、キーワードまたはキーワード 語句 [が多すぎます](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-124">Too many keywords or keyword phrases when you create a search query using the [keywords list](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).</span></span> <span data-ttu-id="bb8b5-125">キーワード リストを使用する検索クエリを実行すると、サービスは基本的にキーワード リスト内の各行に対して個別の検索を実行し、統計情報を生成できます。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-125">When you run a search query that uses the keywords list, the service essentially runs a separate search for each row in the keyword list so that statistics can be generated.</span></span> <span data-ttu-id="bb8b5-126">検索クエリでキーワード リストを使用している場合は、キーワード リスト内の行数を最小限にするか、数値キーワードを小さいリストに分割し、各キーワード リストに対して異なる検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-126">If you're using the keywords list in search queries, minimize the number of rows in the keyword list or divide the number keywords into smaller lists and create a different search for each keyword list.</span></span>

  > [!NOTE]
  > <span data-ttu-id="bb8b5-127">大規模なキーワード リストによって生じる問題を軽減するため、検索クエリのキーワード リストの行は最大 20 行に設定されています。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-127">To help reduce issues caused by large keyword lists, you're now limited to a maximum of 20 rows in the keyword list of a search query.</span></span>

- <span data-ttu-id="bb8b5-128">同じメールボックスで同時に実行される検索が多すぎます。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-128">Too many searches are being performed on the same mailbox at the same time.</span></span> <span data-ttu-id="bb8b5-129">可能であれば、任意の 1 つのメールボックスで一度に 1 つの検索を実行してみてください。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-129">If possible, try to run one search at a time on any one mailbox.</span></span>

- <span data-ttu-id="bb8b5-130">1 つの検索で多くのメールボックスを検索する。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-130">Searching too many mailboxes in a single search.</span></span> <span data-ttu-id="bb8b5-131">多数のメールボックスを検索すると、コンテンツの場所エラーの確率が高くなっています。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-131">The probability of content location errors increases when searching a large number of mailboxes.</span></span> <span data-ttu-id="bb8b5-132">可能であれば、複数の検索を実行して、各検索に組織内のメールボックスのサブセットが含まれるのを試してください。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-132">If possible, try to run multiple searches so that each search includes a subset of  mailboxes in your organization.</span></span>

- <span data-ttu-id="bb8b5-133">メールボックスで必要なメンテナンスが実行されています。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-133">Required maintenance is being performed on the mailbox.</span></span> <span data-ttu-id="bb8b5-134">この原因はおそらくまれに発生しますが、コンテンツの場所エラーを受け取った後少し待って、検索を再試行してください。</span><span class="sxs-lookup"><span data-stu-id="bb8b5-134">Though this cause probably occurs infrequently, wait a little while after receiving the content location error and then retry the search.</span></span>
