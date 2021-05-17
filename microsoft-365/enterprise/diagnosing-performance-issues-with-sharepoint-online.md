---
title: SharePoint Online のパフォーマンスの問題の診断
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: この記事では、開発者ツールを使用してオンライン サイトで一般的なSharePointを診断Internet Explorer示します。
ms.openlocfilehash: 6a29b8b2df54d74d8237418828a7aa89efdbcfaf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927614"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a><span data-ttu-id="99505-103">SharePoint Online のパフォーマンスの問題の診断</span><span class="sxs-lookup"><span data-stu-id="99505-103">Diagnosing performance issues with SharePoint Online</span></span>

<span data-ttu-id="99505-104">この記事では、開発者ツールを使用してオンライン サイトで一般的なSharePointを診断Internet Explorer示します。</span><span class="sxs-lookup"><span data-stu-id="99505-104">This article shows you how you can diagnose common issues with your SharePoint Online site using Internet Explorer developer tools.</span></span>
  
<span data-ttu-id="99505-105">オンライン サイト上のページにカスタマイズのパフォーマンス上SharePoint、3 つの異なる方法があります。</span><span class="sxs-lookup"><span data-stu-id="99505-105">There are three different ways that you can identify that a page on a SharePoint Online site has a performance problem with the customizations.</span></span>
  
- <span data-ttu-id="99505-106">F12 ツール バー ネットワーク モニター</span><span class="sxs-lookup"><span data-stu-id="99505-106">The F12 tool bar network monitor</span></span>

- <span data-ttu-id="99505-107">カスタマイズされていないベースラインとの比較</span><span class="sxs-lookup"><span data-stu-id="99505-107">Comparison to a non-customized baseline</span></span>

- <span data-ttu-id="99505-108">SharePointオンライン応答ヘッダーのメトリック</span><span class="sxs-lookup"><span data-stu-id="99505-108">SharePoint Online response header metrics</span></span>

<span data-ttu-id="99505-109">このトピックでは、これらの各メソッドを使用してパフォーマンスの問題を診断する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="99505-109">This topic describes how to use each of these methods to diagnose performance issues.</span></span> <span data-ttu-id="99505-110">問題の原因を把握したら、見つけ出すパフォーマンスの向上に関する記事をSharePointソリューションに取り組む必要があります https://aka.ms/tune 。</span><span class="sxs-lookup"><span data-stu-id="99505-110">Once you've figured out the cause of the problem, you can work toward a solution using the articles about improving SharePoint performance that you can find on https://aka.ms/tune.</span></span>
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a><span data-ttu-id="99505-111">F12 ツール バーを使用してオンラインでのパフォーマンスをSharePointする</span><span class="sxs-lookup"><span data-stu-id="99505-111">Using the F12 tool bar to diagnose performance in SharePoint Online</span></span>
<span data-ttu-id="99505-112"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="99505-112"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="99505-113">この記事では、11 Internet Explorer使用します。</span><span class="sxs-lookup"><span data-stu-id="99505-113">In this article we use Internet Explorer 11.</span></span> <span data-ttu-id="99505-114">他のブラウザーの F12 開発者ツールのバージョンは、若干異なって見える場合があります。同様の機能があります。</span><span class="sxs-lookup"><span data-stu-id="99505-114">Versions of the F12 developer tools on other browsers have similar features though they may look slightly different.</span></span> <span data-ttu-id="99505-115">F12 開発者ツールの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99505-115">For information on the F12 developer tools, see:</span></span>
  
- <span data-ttu-id="99505-116">[F12 ツールの新機能](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="99505-116">[What's new in F12 Tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))</span></span>

- <span data-ttu-id="99505-117">[F12 開発者ツールの使用](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span><span class="sxs-lookup"><span data-stu-id="99505-117">[Using the F12 developer tools](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))</span></span>

<span data-ttu-id="99505-118">開発者ツールを表示するには **、F12** キーを押し、次のアイコンWi-Fiクリックします。</span><span class="sxs-lookup"><span data-stu-id="99505-118">To bring up the developer tools press **F12** and then click the Wi-Fi icon:</span></span>
  
![F12 開発者ツールの Wi-Fi アイコンのスクリーンショット](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
<span data-ttu-id="99505-120">[ネットワーク **] タブ** で、緑色の再生ボタンを押してページを読み込む。</span><span class="sxs-lookup"><span data-stu-id="99505-120">On the **Network** tab, press the green play button to load a page.</span></span> <span data-ttu-id="99505-121">このツールは、要求したページを取得するためにブラウザーが要求するファイルをすべて返します。</span><span class="sxs-lookup"><span data-stu-id="99505-121">The tool returns all of the files that the browser requests in order to get the page you asked for.</span></span> <span data-ttu-id="99505-122">次のスクリーン ショットは、そのようなリストを 1 つ示しています。</span><span class="sxs-lookup"><span data-stu-id="99505-122">The following screen shot shows one such list.</span></span>
  
![ページ要求で返されるファイル リストのスクリーンショット。](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
<span data-ttu-id="99505-124">また、このスクリーン ショットに示すように、右側にファイルのダウンロード時間を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="99505-124">You can also see the download times of the files on the right side as shown in this screen shot.</span></span>
  
![SharePoint から要求されたページを読み込むのにかかる時間を示す図](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
<span data-ttu-id="99505-126">これにより、ファイルの読み込み時間が視覚的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="99505-126">This gives you a visual representation of how long the file took to load.</span></span> <span data-ttu-id="99505-127">緑の線は、ページをブラウザーでレンダリングする準備が整った状態を表します。</span><span class="sxs-lookup"><span data-stu-id="99505-127">The green line represents when the page is ready to be rendered by the browser.</span></span> <span data-ttu-id="99505-128">これにより、サイトのページ読み込み速度が遅くなる可能性があるさまざまなファイルを簡単に確認できます。</span><span class="sxs-lookup"><span data-stu-id="99505-128">This can give you a quick view of the different files that might be causing slow page loads on your site.</span></span>
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a><span data-ttu-id="99505-129">オンライン用にカスタマイズされていないベースラインをSharePointする</span><span class="sxs-lookup"><span data-stu-id="99505-129">Setting up a non-customized baseline for SharePoint Online</span></span>
<span data-ttu-id="99505-130"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="99505-130"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="99505-131">サイトのパフォーマンスの弱点を特定する最善の方法は、オンラインで完全に使い切れたサイト コレクションをSharePointすることです。</span><span class="sxs-lookup"><span data-stu-id="99505-131">The best way to determine your site's performance weak points is to set up a completely out-of-the-box site collection in SharePoint Online.</span></span> <span data-ttu-id="99505-132">この方法では、サイトのさまざまな側面と、ページ上のカスタマイズを行う必要がないものとを比較できます。</span><span class="sxs-lookup"><span data-stu-id="99505-132">This way you can compare all the various aspects of your site with what you would get with no customization on the page.</span></span> <span data-ttu-id="99505-133">ホーム OneDrive for Businessは、カスタマイズを行う可能性が低い別のサイト コレクションの良い例です。</span><span class="sxs-lookup"><span data-stu-id="99505-133">The OneDrive for Business home page is a good example of a separate site collection that is unlikely to have any customizations.</span></span>
  
## <a name="viewing-sharepoint-response-header-information"></a><span data-ttu-id="99505-134">応答SharePoint情報の表示</span><span class="sxs-lookup"><span data-stu-id="99505-134">Viewing SharePoint response header information</span></span>
<span data-ttu-id="99505-135"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="99505-135"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="99505-136">[SharePointオンライン] では、各ファイルの応答ヘッダーでブラウザーに返される情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="99505-136">In SharePoint Online, you can access the information that is sent back to the browser in the response header for each file.</span></span> <span data-ttu-id="99505-137">パフォーマンスの問題を診断する最も有用な値は **SPRequestDuration** です。これは、要求が処理されるサーバーにかかった時間を表示します。</span><span class="sxs-lookup"><span data-stu-id="99505-137">The most useful value for diagnosing performance issues is **SPRequestDuration**, which displays the amount of time that the request took on the server to be processed.</span></span> <span data-ttu-id="99505-138">これは、要求が非常に重く、リソースが多いかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="99505-138">This can help determine if the request is very heavy and resource intensive.</span></span> <span data-ttu-id="99505-139">これは、サーバーがページにサービスを提供するために実行している作業の量に関する最良の洞察です。</span><span class="sxs-lookup"><span data-stu-id="99505-139">This is the best insight you have into how much work the server is doing to serve the page.</span></span>

### <a name="to-view-sharepoint-response-header-information"></a><span data-ttu-id="99505-140">応答ヘッダー SharePointを表示するには</span><span class="sxs-lookup"><span data-stu-id="99505-140">To view SharePoint response header information</span></span>
  
1. <span data-ttu-id="99505-141">F12 ツールがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="99505-141">Ensure that you have the F12 tools installed.</span></span> <span data-ttu-id="99505-142">これらのツールのダウンロードとインストールの詳細については [、「F12 ツールの新機能」を参照してください](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))。</span><span class="sxs-lookup"><span data-stu-id="99505-142">For more information on downloading and installing these tools, see [What's new in F12 tools](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85)).</span></span>

2. <span data-ttu-id="99505-143">F12 ツールの [ネットワーク] **タブで、** 緑色の再生ボタンを押してページを読み込む。</span><span class="sxs-lookup"><span data-stu-id="99505-143">In the F12 tools, on the **Network** tab, press the green play button to load a page.</span></span>

3. <span data-ttu-id="99505-144">ツールによって返される .aspx ファイルのいずれかをクリックし、[詳細] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="99505-144">Click one of the .aspx files returned by the tool and then click **DETAILS**.</span></span>

    ![応答ヘッダーの詳細を示しています](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. <span data-ttu-id="99505-146">[**応答ヘッダー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="99505-146">Click **Response headers**.</span></span>

    ![応答ヘッダーの URL を示す図](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a><span data-ttu-id="99505-148">オンラインでのパフォーマンスの問題の原因SharePoint?</span><span class="sxs-lookup"><span data-stu-id="99505-148">What's causing performance issues in SharePoint Online?</span></span>
<span data-ttu-id="99505-149"><a name="F12ToolInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="99505-149"><a name="F12ToolInfo"> </a></span></span>

<span data-ttu-id="99505-150">SharePoint [Online](navigation-options-for-sharepoint-online.md)のナビゲーション オプションの記事では、SPRequestDuration 値を使用して、複雑な構造ナビゲーションが原因でページがサーバー上で処理に長い時間がかかると判断する例を示します。</span><span class="sxs-lookup"><span data-stu-id="99505-150">The article [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) shows an example of using the SPRequestDuration value to determine that the complicated structural navigation was causing the page to take a long time to process on the server.</span></span> <span data-ttu-id="99505-151">ベースライン サイトの値を取得することで (カスタマイズなし)、特定のファイルの読み込みに時間がかかっているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="99505-151">By taking a value for a baseline site (without customization), it is possible to determine if any given file is taking a long time to load.</span></span> <span data-ttu-id="99505-152">オンラインのナビゲーション オプションで[使用SharePointは](navigation-options-for-sharepoint-online.md)、メインの .aspx ファイルです。</span><span class="sxs-lookup"><span data-stu-id="99505-152">The example used in [Navigation options for SharePoint Online](navigation-options-for-sharepoint-online.md) is the main .aspx file.</span></span> <span data-ttu-id="99505-153">このファイルには、ページの読み込み ASP.NET 実行されるコードのほとんどが含まれている。</span><span class="sxs-lookup"><span data-stu-id="99505-153">That file contains most of the ASP.NET code that runs for your page load.</span></span> <span data-ttu-id="99505-154">使用するサイト テンプレートに応じて、ホーム ページをカスタマイズする場合は、start.aspx、home.aspx、default.aspx、または別の名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="99505-154">Depending on the site template you use, this could be start.aspx, home.aspx, default.aspx, or another name if you customize the home page.</span></span> <span data-ttu-id="99505-155">この数がベースライン サイトよりかなり高い場合は、パフォーマンスの問題を引き起こしている複雑な問題がページに発生しているという良い兆候です。</span><span class="sxs-lookup"><span data-stu-id="99505-155">If this number is considerably higher than your baseline site, then it's a good indication that there is something complex going on in your page that is causing performance issues.</span></span>
  
<span data-ttu-id="99505-156">サイト固有の問題を特定したら、パフォーマンスの低下の原因を把握するために推奨される方法は、ページのカスタマイズなど、考えられるすべての原因を排除し、それらをサイトに 1 つ 1 つ追加し戻すことです。</span><span class="sxs-lookup"><span data-stu-id="99505-156">Once you have identified that an issue specific to your site, the recommended way to figure out what is causing poor performance is to eliminate all of the possible causes, like page customizations, and then add them back to the site one by one.</span></span> <span data-ttu-id="99505-157">ページがうまく機能する十分なカスタマイズを削除したら、特定のカスタマイズを 1 つ 1 つ追加できます。</span><span class="sxs-lookup"><span data-stu-id="99505-157">Once you have removed enough customizations that the page is performing well, you can then add back specific customizations one by one.</span></span>
  
<span data-ttu-id="99505-158">たとえば、非常に複雑なナビゲーションを使用している場合は、ナビゲーションを変更してサブサイトを表示しない場合は、開発者ツールをチェックして、これが違いを生み出すのか確認してください。</span><span class="sxs-lookup"><span data-stu-id="99505-158">For example, if you have a very complex navigation try changing the navigation to not show sub-sites then check the developer tools to see if this makes a difference.</span></span> <span data-ttu-id="99505-159">または、コンテンツのロールアップが大量にある場合は、ページから削除して、問題が改善されるのか確認してください。</span><span class="sxs-lookup"><span data-stu-id="99505-159">Or if you have a large amount of content roll-ups try removing them from your page and see if this improves things.</span></span> <span data-ttu-id="99505-160">考えられるすべての原因を排除し、一度に 1 つで追加し戻す場合、最大の問題である機能を簡単に特定し、ソリューションに向けて作業できます。</span><span class="sxs-lookup"><span data-stu-id="99505-160">If you eliminate all of the possible causes and add them back in one at a time, you can easily identify which features are the biggest problem and then work towards a solution.</span></span>