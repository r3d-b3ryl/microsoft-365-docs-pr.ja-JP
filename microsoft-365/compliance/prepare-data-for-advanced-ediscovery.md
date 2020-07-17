---
title: Advanced eDiscovery 用のデータを作成する
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
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
ms.assetid: 2fb94c23-1846-4a0e-994d-da6d02445f15
description: セキュリティコンプライアンスセンターを使用して、 &amp; 高度な電子情報開示を使用して分析のためにデータを準備する方法について説明します。
ms.openlocfilehash: 3c9d237a3a9c04a443730143998324a7831f2998
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936332"
---
# <a name="prepare-data-for-advanced-ediscovery-classic"></a><span data-ttu-id="c478d-103">高度な電子情報開示用のデータを準備する (クラシック)</span><span class="sxs-lookup"><span data-stu-id="c478d-103">Prepare data for Advanced eDiscovery (classic)</span></span>

<span data-ttu-id="c478d-104">このトピックでは、高度な電子情報開示 (クラシック) のケースにコンテンツ検索の結果を読み込む方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c478d-104">This topic describes how to load the results of a Content Search in to a case in Advanced eDiscovery (classic).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c478d-105">新しいバージョンの Advanced eDiscovery に投資し続ける中で、Advanced eDiscovery (*Advanced eDiscovery (クラッシック)* または *Advanced eDiscovery v1.0* とも呼ばれる) のサポート終了を発表しました。</span><span class="sxs-lookup"><span data-stu-id="c478d-105">As we continue to invest in newer versions of Advanced eDiscovery, we are announcing the retirement of Advanced eDiscovery, also known as *Advanced eDiscovery (classic)* or *Advanced eDiscovery v1.0*.</span></span> <span data-ttu-id="c478d-106">まだ Advanced eDiscovery v1.0 を使用している場合は、できるだけ早く [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (*Microsoft 365 では Advanced eDiscovery ソリューション*とも呼ばれる) に移行してください。</span><span class="sxs-lookup"><span data-stu-id="c478d-106">If you're still using Advanced eDiscovery v1.0, please transition to [Advanced eDiscovery v2.0](overview-ediscovery-20.md) (also known as the *Advanced eDiscovery solution in Microsoft 365*) as soon as possible.</span></span> <span data-ttu-id="c478d-107">Advanced eDiscovery 2.0 には Advanced eDiscovery v1.0 の同様の機能が搭載されていますが、保管担当者管理、通信管理、レビュー セットなど、多くの新機能も搭載されています。</span><span class="sxs-lookup"><span data-stu-id="c478d-107">Advanced eDiscovery 2.0 contains similar functionality found in Advanced eDiscovery v1.0, but also offers many new features such as custodian management, communications management, and review sets.</span></span> <span data-ttu-id="c478d-108">Advanced eDiscovery v1.0 のサポート終了の詳細については、「[従来版の電子情報開示ツールのサポート終了](legacy-ediscovery-retirement.md#advanced-ediscovery-v10)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c478d-108">To learn more about the retirement of Advanced eDiscovery v1.0, see [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md#advanced-ediscovery-v10).</span></span>  
  
## <a name="step-1-prepare-data-for-advanced-ediscovery"></a><span data-ttu-id="c478d-109">手順 1: 高度な電子情報開示のためのデータを準備する</span><span class="sxs-lookup"><span data-stu-id="c478d-109">Step 1: Prepare data for Advanced eDiscovery</span></span>

<span data-ttu-id="c478d-110">上級電子情報開示を使用してデータを分析するには、Microsoft 365 セキュリティ &amp; コンプライアンスセンター (microsoft 365 セキュリティコンプライアンスセンターの**コンテンツ検索**ページにリストされて &amp; います) または電子情報開示ケースに関連付けられた検索 (セキュリティコンプライアンスセンターの [**電子情報開示**] ページに一覧表示) で実行するコンテンツ検索の結果を使用でき &amp; ます。</span><span class="sxs-lookup"><span data-stu-id="c478d-110">To analyze data with Advanced eDiscovery, you can use the results of a Content Search that you run in the Microsoft 365 Security &amp; Compliance Center (listed on the **Content search** page in the Microsoft 365 Security &amp; Compliance Center) or a search associated with an eDiscovery case (listed on the **eDiscovery** page in the Security &amp; Compliance Center).</span></span> 
  
<span data-ttu-id="c478d-111">高度な電子情報開示で分析のために検索結果を準備する詳細な手順については、「 [Advanced ediscovery の検索結果を準備](prepare-search-results-for-advanced-ediscovery.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c478d-111">For the detailed steps on preparing search results for analysis in Advanced eDiscovery, see [Prepare search results for Advanced eDiscovery](prepare-search-results-for-advanced-ediscovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c478d-112">Microsoft 365 の外部にデータがあり、それを Microsoft 365 にインポートして、高度な電子情報開示で準備および分析できるようにする場合は、「 [microsoft 365 への PST ファイルのインポート](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365)と[サードパーティデータのアーカイブ](https://www.microsoft.com/?ref=go)の概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c478d-112">If you have data outside of Microsoft 365 and want to import it to Microsoft 365 so that you can prepare and analyze it in Advanced eDiscovery, a see [Overview of importing PST files to Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/importing-pst-files-to-office-365) and [Archiving third-party data](https://www.microsoft.com/?ref=go).</span></span> 
  
## <a name="step-2-load-search-result-data-in-to-a-case-in-advanced-ediscovery"></a><span data-ttu-id="c478d-113">手順 2: 高度な電子情報開示のケースに検索結果データを読み込む</span><span class="sxs-lookup"><span data-stu-id="c478d-113">Step 2: Load search result data in to a case in Advanced eDiscovery</span></span>

<span data-ttu-id="c478d-114">分析のためにセキュリティコンプライアンスセンターで検索結果を準備した後、 &amp; 次の手順では、高度な電子情報開示のケースに検索結果を読み込みます。</span><span class="sxs-lookup"><span data-stu-id="c478d-114">After you prepare the search results in the Security &amp; Compliance Center for analysis, the next step is to load the search results in to a case in Advanced eDiscovery.</span></span> <span data-ttu-id="c478d-115">詳細については、「 [Process module を実行する](run-the-process-module-in-advanced-ediscovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c478d-115">For more detailed information, see [Run the Process module](run-the-process-module-in-advanced-ediscovery.md).</span></span>
  
1. <span data-ttu-id="c478d-116">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="c478d-116">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="c478d-117">職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="c478d-117">Sign in using your work or school account.</span></span>
    
3. <span data-ttu-id="c478d-118">セキュリティ&amp;コンプライアンス センターで、**[検索&amp;調査]** \> **[電子情報開示]** の順にクリックし、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c478d-118">In the Security &amp; Compliance Center, click **Search &amp; investigation** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
4. <span data-ttu-id="c478d-119">高度な電子情報開示でにデータを読み込むケースの横にある [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c478d-119">Click **Open** next to the case that you want to load data in to in Advanced eDiscovery.</span></span> 
    
5. <span data-ttu-id="c478d-120">ケースの [**ホーム**] ページで、[**Advanced eDiscovery に切り替え**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c478d-120">On the **Home** page for the case, click **Switch to Advanced eDiscovery**.</span></span> 
    
    ![[高度な電子情報開示に切り替え] をクリックして、高度な電子情報開示でケースを開きます。](../media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    <span data-ttu-id="c478d-122">**[高度な電子情報開示**の進行状況バーへの接続] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c478d-122">The **Connecting to Advanced eDiscovery** progress bar is displayed.</span></span> <span data-ttu-id="c478d-123">上級電子情報開示に接続されている場合は、ケースのセットアップページにコンテナーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c478d-123">When you're connected to Advanced eDiscovery, a list of containers is displayed on the setup page for the case.</span></span> 
    
    ![詳細な電子情報開示でケースが表示される](../media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
     <span data-ttu-id="c478d-125">これらのコンテナーは、手順1でアドバンスト eDiscovery で分析するために準備した検索結果を表します。</span><span class="sxs-lookup"><span data-stu-id="c478d-125">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 1.</span></span> <span data-ttu-id="c478d-126">セキュリティ/コンプライアンスセンターでは、コンテナーの名前がコンテンツ検索と同じ名前になっていることに注意して &amp; ください。</span><span class="sxs-lookup"><span data-stu-id="c478d-126">Note that the name of the container has the same name as the Content Search in the case in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="c478d-127">リスト内のコンテナーは、準備したものです。</span><span class="sxs-lookup"><span data-stu-id="c478d-127">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="c478d-128">上級電子情報開示のために別のユーザーが検索結果を準備している場合、対応するコンテナーはリストに含まれません。</span><span class="sxs-lookup"><span data-stu-id="c478d-128">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span> 
    
6. <span data-ttu-id="c478d-129">高度な電子情報開示のケースに、コンテナーからの検索結果データを読み込むには、コンテナーを選択し、[**処理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c478d-129">To load the search result data from a container in to the case in Advanced eDiscovery, select a container and then click **Process**.</span></span>
    
<span data-ttu-id="c478d-130">&amp;上級電子情報開示のケースにセキュリティコンプライアンスセンターからの検索結果が追加された後、次の手順では、[Advanced ediscovery] のツールを使用して、ケースに関連するデータを分析し、選別します。</span><span class="sxs-lookup"><span data-stu-id="c478d-130">After the search results from the Security &amp; Compliance Center are added to the case in Advanced eDiscovery, the next step is to use the tools in Advanced eDiscovery to analyze and cull the data that's relevant to the case.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c478d-131">関連項目</span><span class="sxs-lookup"><span data-stu-id="c478d-131">See also</span></span>

[<span data-ttu-id="c478d-132">Advanced eDiscovery (クラシック)</span><span class="sxs-lookup"><span data-stu-id="c478d-132">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="c478d-133">ユーザーおよびケースをセットアップする</span><span class="sxs-lookup"><span data-stu-id="c478d-133">Set up users and cases</span></span>](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c478d-134">ケース データの分析</span><span class="sxs-lookup"><span data-stu-id="c478d-134">Analyzing case data</span></span>](analyze-case-data-with-advanced-ediscovery.md)
  
[<span data-ttu-id="c478d-135">関連性の設定の管理</span><span class="sxs-lookup"><span data-stu-id="c478d-135">Managing Relevance setup</span></span>](manage-relevance-setup-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c478d-136">関連度モジュールの使用</span><span class="sxs-lookup"><span data-stu-id="c478d-136">Using the Relevance module</span></span>](use-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="c478d-137">ケース データのエクスポート</span><span class="sxs-lookup"><span data-stu-id="c478d-137">Exporting case data</span></span>](export-case-data-in-advanced-ediscovery.md)

