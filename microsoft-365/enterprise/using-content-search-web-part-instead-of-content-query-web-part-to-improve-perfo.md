---
title: コンテンツ クエリ Web パーツの代わりにコンテンツ検索 Web パーツを使用してオンラインでのパフォーマンスSharePointする
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: e8ce6b72-745b-464a-85c7-cbf6eb53391b
description: コンテンツ クエリ Web パーツを SharePoint Server 2013 および SharePoint Online のコンテンツ検索 Web パーツに置き換えてパフォーマンスを向上させる方法について説明します。
ms.openlocfilehash: e5f57e59a421d79302f447e229091fdfc96f1237
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692221"
---
# <a name="using-content-search-web-part-instead-of-content-query-web-part-to-improve-performance-in-sharepoint-online"></a><span data-ttu-id="42c3a-103">コンテンツ クエリ Web パーツの代わりにコンテンツ検索 Web パーツを使用してオンラインでのパフォーマンスSharePointする</span><span class="sxs-lookup"><span data-stu-id="42c3a-103">Using Content Search Web Part instead of Content Query Web Part to improve performance in SharePoint Online</span></span>

<span data-ttu-id="42c3a-104">この記事では、コンテンツ クエリ Web パーツを SharePoint Server 2013 および SharePoint Online のコンテンツ検索 Web パーツに置き換えてパフォーマンスを向上させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="42c3a-104">This article describes how to increase performance by replacing the Content Query Web Part with the Content Search Web Part in SharePoint Server 2013 and SharePoint Online.</span></span>
  
<span data-ttu-id="42c3a-105">SharePoint Server 2013 および SharePoint の最も強力な新機能の 1 つは、コンテンツ検索 Web パーツ (CSWP) です。</span><span class="sxs-lookup"><span data-stu-id="42c3a-105">One of the most powerful new features of SharePoint Server 2013 and SharePoint Online is the Content Search Web Part (CSWP).</span></span> <span data-ttu-id="42c3a-106">この Web パーツは、検索インデックスを使用して、ユーザーに表示される結果をすばやく取得します。</span><span class="sxs-lookup"><span data-stu-id="42c3a-106">This Web Part uses the search index to quickly retrieve results which are shown to the user.</span></span> <span data-ttu-id="42c3a-107">ユーザーのパフォーマンスを向上させるために、ページ内のコンテンツ クエリ Web パーツ (CQWP) の代わりにコンテンツ検索 Web パーツを使用します。</span><span class="sxs-lookup"><span data-stu-id="42c3a-107">Use the Content Search Web Part instead of the Content Query Web Part (CQWP) in your pages to improve performance for your users.</span></span>
  
<span data-ttu-id="42c3a-108">コンテンツ クエリ Web パーツに対してコンテンツ検索 Web パーツを使用すると、ほとんどの場合、オンラインでのページ読み込みパフォーマンスがSharePointになります。</span><span class="sxs-lookup"><span data-stu-id="42c3a-108">Using a Content Search Web Part over a Content Query Web Part will almost always result in significantly better page load performance on SharePoint Online.</span></span> <span data-ttu-id="42c3a-109">適切なクエリを取得するために少し追加の構成がありますが、報酬はパフォーマンスが向上し、ユーザーが幸せです。</span><span class="sxs-lookup"><span data-stu-id="42c3a-109">There is a little additional configuration to get the right query, but the rewards are improved performance and happier users.</span></span>
  
## <a name="comparing-the-performance-gain-you-get-from-using-content-search-web-part-instead-of-content-query-web-part"></a><span data-ttu-id="42c3a-110">コンテンツ クエリ Web パーツの代わりにコンテンツ検索 Web パーツを使用して得られるパフォーマンスの向上を比較する</span><span class="sxs-lookup"><span data-stu-id="42c3a-110">Comparing the performance gain you get from using Content Search Web Part instead of Content Query Web Part</span></span>

<span data-ttu-id="42c3a-111">次の例は、コンテンツ クエリ Web パーツの代わりにコンテンツ検索 Web パーツを使用するときに受け取る可能性がある相対的なパフォーマンス向上を示しています。</span><span class="sxs-lookup"><span data-stu-id="42c3a-111">The following examples show the relative performance gains you may receive when you use a Content Search Web Part instead of a Content Query Web Part.</span></span> <span data-ttu-id="42c3a-112">複雑なサイト構造と非常に広範なコンテンツ クエリにより、効果が明らかになります。</span><span class="sxs-lookup"><span data-stu-id="42c3a-112">The effects are more obvious with a complex site structure and very broad content queries.</span></span>
  
<span data-ttu-id="42c3a-113">このサイトの例には、次の特性があります。</span><span class="sxs-lookup"><span data-stu-id="42c3a-113">This example site has the following characteristics:</span></span>
  
- <span data-ttu-id="42c3a-114">8 レベルのサブサイト。</span><span class="sxs-lookup"><span data-stu-id="42c3a-114">8 levels of subsites.</span></span>
    
- <span data-ttu-id="42c3a-115">カスタムの "フルーツ" コンテンツ タイプを使用するリスト。</span><span class="sxs-lookup"><span data-stu-id="42c3a-115">Lists using a custom "fruit" content type.</span></span>
    
- <span data-ttu-id="42c3a-116">Web パーツでは、コンテンツ クエリは広範で、コンテンツ タイプが "fruit" のすべてのアイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="42c3a-116">In the Web Part, the content query is broad, returning all items with the content type of "fruit".</span></span>
    
- <span data-ttu-id="42c3a-117">この例では、8 つのサイト全体で 50 アイテムのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="42c3a-117">The example only uses 50 items across the 8 sites.</span></span> <span data-ttu-id="42c3a-118">コンテンツが多いサイトでは、さらに効果が顕著に表示されます。</span><span class="sxs-lookup"><span data-stu-id="42c3a-118">The effects will be even more pronounced for sites with more content.</span></span>
    
<span data-ttu-id="42c3a-119">コンテンツ クエリ Web パーツの結果のスクリーン ショットを次に示します。</span><span class="sxs-lookup"><span data-stu-id="42c3a-119">Here is a screen shot of the results of the Content Query Web Part.</span></span>
  
![Web パーツのクエリ結果を示すグラフィック](../media/b3d41f20-dfe5-46ed-9c0a-31057e82de33.png)
  
<span data-ttu-id="42c3a-121">このInternet Explorer、F12開発者ツールの [ネットワーク] タブを使用して、応答ヘッダーの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="42c3a-121">In Internet Explorer, use the **Network** tab of the F12 developer tools to look at the details for the response header.</span></span> <span data-ttu-id="42c3a-122">次のスクリーン ショットでは、このページ読み込み時の **SPRequestDuration** の値は 924 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="42c3a-122">In the following screen shot, the value for the **SPRequestDuration** for this page load is 924 milliseconds.</span></span> 
  
![924 の要求時間が表示されているスクリーンショット](../media/343571f2-a249-4de2-bc11-2cee93498aea.png)
  
 <span data-ttu-id="42c3a-124">**SPRequestDuration は** 、ページを準備するためにサーバーで実行される作業量を示します。</span><span class="sxs-lookup"><span data-stu-id="42c3a-124">**SPRequestDuration** indicates the amount of work that is done on the server to prepare the page.</span></span> <span data-ttu-id="42c3a-125">クエリによってコンテンツを切りWeb パーツ検索でコンテンツを切りWeb パーツ、ページのレンダリングにかかる時間が大幅に短縮されます。</span><span class="sxs-lookup"><span data-stu-id="42c3a-125">Switching Content by Query Web Parts with Content by Search Web Parts dramatically reduces the time it takes to render the page.</span></span> <span data-ttu-id="42c3a-126">対照的に、同等のコンテンツ検索 Web パーツを持つページで、同じ数の結果を返す場合、このスクリーン ショットに示すように **SPRequestDuration** 値は 106 ミリ秒です。</span><span class="sxs-lookup"><span data-stu-id="42c3a-126">By contrast, a page with an equivalent Content Search Web Part, returning the same number of results has an **SPRequestDuration** value of 106 milliseconds as shown in this screen shot:</span></span> 
  
![106 の要求時間が表示されているスクリーンショット](../media/b46387ac-660d-4e5e-a11c-cc430e912962.png)
  
## <a name="adding-a-content-search-web-part-in-sharepoint-online"></a><span data-ttu-id="42c3a-128">オンラインでのコンテンツ検索 Web パーツSharePointする</span><span class="sxs-lookup"><span data-stu-id="42c3a-128">Adding a Content Search Web Part in SharePoint Online</span></span>

<span data-ttu-id="42c3a-129">コンテンツ検索 Web パーツの追加は、通常のコンテンツ クエリ Web パーツと非常に似ています。</span><span class="sxs-lookup"><span data-stu-id="42c3a-129">Adding a Content Search Web Part is very similar to a regular Content Query Web Part.</span></span> <span data-ttu-id="42c3a-130">「コンテンツ検索 *Web パーツを構成する*」のセクション「コンテンツ検索 [Web](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)パーツの追加」を参照SharePoint。</span><span class="sxs-lookup"><span data-stu-id="42c3a-130">See the section  *"Add a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="creating-the-right-search-query-for-your-content-search-web-part"></a><span data-ttu-id="42c3a-131">コンテンツ検索 Web パーツの適切な検索クエリを作成する</span><span class="sxs-lookup"><span data-stu-id="42c3a-131">Creating the right search query for your Content Search Web Part</span></span>

<span data-ttu-id="42c3a-132">コンテンツ検索 Web パーツを追加したら、検索を絞り込んで、必要なアイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="42c3a-132">Once you have added a Content Search Web Part, you can refine the search and return the items you want.</span></span> <span data-ttu-id="42c3a-133">これを行う方法の詳細については、「SharePoint でコンテンツ検索 Webパーツを構成する」のセクション「コンテンツ検索 Web パーツで高度なクエリを構成してコンテンツを表示する[」を参照してください](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a)。</span><span class="sxs-lookup"><span data-stu-id="42c3a-133">For detailed instructions on how to do this, see the section,  *"Display content by configuring an advanced query in a Content Search Web Part"*  in [Configure a Content Search Web Part in SharePoint](https://support.office.com/article/Configure-a-Content-Search-Web-Part-in-SharePoint-0dc16de1-dbe4-462b-babb-bf8338c36c9a).</span></span>
  
## <a name="query-building-and-testing-tool"></a><span data-ttu-id="42c3a-134">クエリの作成とテスト ツール</span><span class="sxs-lookup"><span data-stu-id="42c3a-134">Query building and testing tool</span></span>

<span data-ttu-id="42c3a-135">複雑なクエリをビルドしてテストするツールについては、「Codeplex の [検索クエリ ツール」](https://sp2013searchtool.codeplex.com/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="42c3a-135">For a tool to build and test complex queries, see the [Search Query Tool](https://sp2013searchtool.codeplex.com/) on Codeplex.</span></span> 
  

