---
title: ドキュメントのラベル アクティビティを表示する
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 5/9/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Microsoft 365 セキュリティ/コンプライアンス センターのラベル アクティビティ エクスプローラーを使用して、ラベル アクティビティを検索して表示する方法について説明します。
ms.openlocfilehash: 9cf505575a17c8f6eb4d48e609d358f9c988965f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819027"
---
# <a name="view-label-activity-for-documents"></a><span data-ttu-id="a8eea-103">ドキュメントのラベル アクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="a8eea-103">View label activity for documents</span></span>

<span data-ttu-id="a8eea-104">After you create your labels, you'll want to verify that they're being applied to content as you intended.</span><span class="sxs-lookup"><span data-stu-id="a8eea-104">After you create your labels, you'll want to verify that they're being applied to content as you intended.</span></span> <span data-ttu-id="a8eea-105">With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days.</span><span class="sxs-lookup"><span data-stu-id="a8eea-105">With the Label Activity Explorer in the Security &amp; Compliance Center, you can quickly search and view label activity for all content across SharePoint and OneDrive for Business over the past 30 days.</span></span> <span data-ttu-id="a8eea-106">This is real-time data that gives you a clear view into what's happening in your tenant.</span><span class="sxs-lookup"><span data-stu-id="a8eea-106">This is real-time data that gives you a clear view into what's happening in your tenant.</span></span>
  
<span data-ttu-id="a8eea-107">たとえば、ラベル アクティビティ エクスプローラーで以下のことができます:</span><span class="sxs-lookup"><span data-stu-id="a8eea-107">For example, with the Label Activity Explorer, you can:</span></span>
  
- <span data-ttu-id="a8eea-108">それぞれのラベルが適用された回数を日ごとに表示 (最大 30 日間)。</span><span class="sxs-lookup"><span data-stu-id="a8eea-108">View how many times each label was applied on each day (up to 30 days).</span></span>
    
- <span data-ttu-id="a8eea-109">誰がいつ、どのファイルにラベルを付けたかを正確に表示。ファイルが存在するサイトへのリンクも表示。</span><span class="sxs-lookup"><span data-stu-id="a8eea-109">See who labeled exactly which file on which date, along with a link to the site where that file resides.</span></span>
    
- <span data-ttu-id="a8eea-110">ラベルが変更されたり削除されたりしたファイル、古いラベルおよび新しいラベル、変更を行ったユーザーの表示。</span><span class="sxs-lookup"><span data-stu-id="a8eea-110">View which files had labels changed or removed, what the old and new labels are, and who made the change.</span></span>
    
- <span data-ttu-id="a8eea-111">Filter the data to see all the label activity for a specific label, file, or user.</span><span class="sxs-lookup"><span data-stu-id="a8eea-111">Filter the data to see all the label activity for a specific label, file, or user.</span></span> <span data-ttu-id="a8eea-112">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span><span class="sxs-lookup"><span data-stu-id="a8eea-112">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
    
- <span data-ttu-id="a8eea-113">View label activity for folders as well as individual documents.</span><span class="sxs-lookup"><span data-stu-id="a8eea-113">View label activity for folders as well as individual documents.</span></span> <span data-ttu-id="a8eea-114">Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span><span class="sxs-lookup"><span data-stu-id="a8eea-114">Coming soon is the ability to show how many files inside that folder got labeled as a result of the folder getting labeled.</span></span>
    
<span data-ttu-id="a8eea-115">ラベル アクティビティ エクスプローラーにアクセスするには、セキュリティ &amp; コンプライアンス センターで **[情報ガバナンス]** > **[ラベル アクティビティ エクスプローラー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="a8eea-115">You can find the Label Activity Explorer in the Security &amp; Compliance Center > **Information governance** > **Label activity explorer**.</span></span>
  
<span data-ttu-id="a8eea-116">なお、ラベル アクティビティ エクスプローラーには、Office 365 Enterprise E5 サブスクリプションが必要となります。</span><span class="sxs-lookup"><span data-stu-id="a8eea-116">Note that the Label Activity Explorer requires an Office 365 Enterprise E5 subscription.</span></span>
  
![ラベル アクティビティ エクスプローラー](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="view-label-activities-for-files-or-folders"></a><span data-ttu-id="a8eea-118">ファイルまたはフォルダーのラベル アクティビティの表示</span><span class="sxs-lookup"><span data-stu-id="a8eea-118">View label activities for files or folders</span></span>

<span data-ttu-id="a8eea-119">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders.</span><span class="sxs-lookup"><span data-stu-id="a8eea-119">At the top of the Label Activity Explorer, you can choose whether to view activities for files or folders.</span></span> <span data-ttu-id="a8eea-120">Note that folder activity includes only the folder itself, not the files inside the folder.</span><span class="sxs-lookup"><span data-stu-id="a8eea-120">Note that folder activity includes only the folder itself, not the files inside the folder.</span></span>
  
<span data-ttu-id="a8eea-121">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them).</span><span class="sxs-lookup"><span data-stu-id="a8eea-121">You might want to see label activity for folders because if you label a folder, all files inside that folder also get that label (except for files that have had a label applied explicitly to them).</span></span> <span data-ttu-id="a8eea-122">Therefore, labeling folders might affect a significant number of files.</span><span class="sxs-lookup"><span data-stu-id="a8eea-122">Therefore, labeling folders might affect a significant number of files.</span></span> <span data-ttu-id="a8eea-123">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="a8eea-123">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
  
![ファイルとフォルダーのラベル アクティビティを表示するドロップダウン メニュー](../media/11030584-f52d-49eb-86f3-7ead16a3b704.png)
  
### <a name="label-activities"></a><span data-ttu-id="a8eea-125">ラベル アクティビティ</span><span class="sxs-lookup"><span data-stu-id="a8eea-125">Label activities</span></span>

 <span data-ttu-id="a8eea-126">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label.</span><span class="sxs-lookup"><span data-stu-id="a8eea-126">**Label activities** includes all label actions: **adding**, **removing**, or **changing** a label.</span></span> <span data-ttu-id="a8eea-127">You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span><span class="sxs-lookup"><span data-stu-id="a8eea-127">You can use this view to get a comprehensive look at how many files each label's been applied to per day.</span></span> 
  
### <a name="label-changes"></a><span data-ttu-id="a8eea-128">ラベルの変更</span><span class="sxs-lookup"><span data-stu-id="a8eea-128">Label changes</span></span>

 <span data-ttu-id="a8eea-129">**Label changes** includes the potentially risky actions of **removing** or **changing** a label.</span><span class="sxs-lookup"><span data-stu-id="a8eea-129">**Label changes** includes the potentially risky actions of **removing** or **changing** a label.</span></span> <span data-ttu-id="a8eea-130">You can use this view to quickly see such risky actions and the user who performed them.</span><span class="sxs-lookup"><span data-stu-id="a8eea-130">You can use this view to quickly see such risky actions and the user who performed them.</span></span> <span data-ttu-id="a8eea-131">In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span><span class="sxs-lookup"><span data-stu-id="a8eea-131">In the activity list below the chart, you can select a file, and then click a link to that file in the details pane on the right.</span></span> 
  
![ラベル アクティビティの詳細ウィンドウ](../media/eb580fd4-b5be-4fda-9ba5-c1256777310d.png)
  
## <a name="filter-label-activity"></a><span data-ttu-id="a8eea-133">ラベル アクティビティのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="a8eea-133">Filter label activity</span></span>

<span data-ttu-id="a8eea-134">You can quickly filter the data to see all the label activity for a specific label, file, or user.</span><span class="sxs-lookup"><span data-stu-id="a8eea-134">You can quickly filter the data to see all the label activity for a specific label, file, or user.</span></span> <span data-ttu-id="a8eea-135">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span><span class="sxs-lookup"><span data-stu-id="a8eea-135">You can also filter label activity by location (SharePoint or OneDrive for Business) and whether the label was applied manually or auto-applied.</span></span>
  
![ラベル アクティビティのフィルター](../media/9de92985-120f-48b4-96a7-ef7ec8a71ff0.png)
  

