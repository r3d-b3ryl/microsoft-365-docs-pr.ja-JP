---
title: サイトとファイルをゲスト ユーザーと共有する
f1.keywords: NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 89502322-bfbb-43d6-9207-4030f8ce26e0
ROBOTS: NOINDEX
description: '組織外のユーザーとサイトやファイルを共有する方法を説明します。 '
ms.openlocfilehash: 79760f662ec68d2ac9089586fd9cbf38b0bd9897
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780051"
---
# <a name="share-sites-and-files-with-guest-users"></a><span data-ttu-id="ad34b-103">サイトとファイルをゲスト ユーザーと共有する</span><span class="sxs-lookup"><span data-stu-id="ad34b-103">Share sites and files with guest users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="ad34b-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="ad34b-104">The admin center is changing.</span></span> <span data-ttu-id="ad34b-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad34b-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="ad34b-106">組織外のユーザーと共同作業するために、サイト全体または特定のファイルを外部で共有できます。</span><span class="sxs-lookup"><span data-stu-id="ad34b-106">To collaborate with people outside your organization, you can share entire sites or specific files externally.</span></span> <span data-ttu-id="ad34b-107">共有を直接セットアップする場合は、有効にするシナリオを選択します。</span><span class="sxs-lookup"><span data-stu-id="ad34b-107">If you want to get straight to setting up sharing, choose the scenario you want to enable:</span></span>

- [<span data-ttu-id="ad34b-108">ゲストと共同でドキュメントの作業をする</span><span class="sxs-lookup"><span data-stu-id="ad34b-108">Collaborate with guests on a document</span></span>](../../solutions/collaborate-on-documents.md)
- [<span data-ttu-id="ad34b-109">サイトでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="ad34b-109">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="ad34b-110">チームでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="ad34b-110">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)
  
## <a name="deciding-how-to-share-your-content"></a><span data-ttu-id="ad34b-111">コンテンツの共有方法の決定</span><span class="sxs-lookup"><span data-stu-id="ad34b-111">Deciding how to share your content</span></span>

<span data-ttu-id="ad34b-112">コンテンツを外部と共有するかどうか、そしてどのように共有を有効にするかを検討している場合には、次のことを考えます。</span><span class="sxs-lookup"><span data-stu-id="ad34b-112">When considering if and how you want to share content externally, think about the following:</span></span>
  
- <span data-ttu-id="ad34b-113">だれにサイトとそのサブサイトのコンテンツへのアクセス許可を与えるか、そしてそのユーザーたちが何をできるようにしたいのか。</span><span class="sxs-lookup"><span data-stu-id="ad34b-113">To whom do you want to grant access to content on the site and any subsites, and what do you want them to be able to do?</span></span>
    
- <span data-ttu-id="ad34b-114">組織内のだれに外部とコンテンツを共有する権限を与えるか?</span><span class="sxs-lookup"><span data-stu-id="ad34b-114">To whom in your organization do you want to grant permission to share content externally?</span></span> 
    
- <span data-ttu-id="ad34b-115">組織外の人々には決して閲覧されてはいけないコンテンツがあるかどうか。</span><span class="sxs-lookup"><span data-stu-id="ad34b-115">Is there content you want to ensure is never available to be viewed by people external to your organization?</span></span>
    
<span data-ttu-id="ad34b-116">これらの質問への回答は、コンテンツ共有への戦略を立案するのに役立つはずです。</span><span class="sxs-lookup"><span data-stu-id="ad34b-116">The answers to these questions will help you plan your strategy for content sharing.</span></span>
  
|<span data-ttu-id="ad34b-117">**次の操作を試してください。**</span><span class="sxs-lookup"><span data-stu-id="ad34b-117">**Try this:**</span></span>|<span data-ttu-id="ad34b-118">**目的**</span><span class="sxs-lookup"><span data-stu-id="ad34b-118">**If you need to…**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ad34b-119">グループにゲストを追加する</span><span class="sxs-lookup"><span data-stu-id="ad34b-119">Add a guest to a group</span></span>  <br/> |<span data-ttu-id="ad34b-120">チーム サイト上の情報とコンテンツへの継続的なアクセスを組織外のだれかに提供する。</span><span class="sxs-lookup"><span data-stu-id="ad34b-120">Provide someone outside your organization with ongoing access to information and content on a team site.</span></span> <span data-ttu-id="ad34b-121">これらの人々は、サイトの正式ユーザーのように実行し、コンテンツを作成、編集、表示する必要がある。</span><span class="sxs-lookup"><span data-stu-id="ad34b-121">They need the ability to perform like a full user of your site and create, edit, and view content.</span></span>  <br/> |
|<span data-ttu-id="ad34b-122">ドキュメントを共有し、ゲストに認証を要求する。</span><span class="sxs-lookup"><span data-stu-id="ad34b-122">Share a document and require guests to authenticate.</span></span>  <br/> |<span data-ttu-id="ad34b-123">確認または共同作業のために、組織外の特定のユーザーにドキュメントへの安全なアクセスを提供する。これらのユーザーはサイトの他のコンテンツにアクセスを行う必要はない。</span><span class="sxs-lookup"><span data-stu-id="ad34b-123">Provide specific people outside your organization with secure access to a document for review or collaboration, but these people do not require access to other content on the site.</span></span>  <br/> |
|<span data-ttu-id="ad34b-124">ドキュメントを共有するが、認証を要求しない。</span><span class="sxs-lookup"><span data-stu-id="ad34b-124">Share a document, but don't require authentication.</span></span>  <br/> |<span data-ttu-id="ad34b-125">機密でも極秘でもないドキュメントへのリンクを組織外の人々と共有し、これを表示したり、フィードバックで更新したりできるようにする。</span><span class="sxs-lookup"><span data-stu-id="ad34b-125">Share a link to a non-sensitive or non-confidential document with people outside your organization so that they can either view it or update it with feedback.</span></span> <span data-ttu-id="ad34b-126">これらのユーザーは、サイト上のコンテンツへのアクセスを必要としない。</span><span class="sxs-lookup"><span data-stu-id="ad34b-126">These people do not require access to content on the site.</span></span>  <br/> |
   
> [!IMPORTANT]
> <span data-ttu-id="ad34b-127">外部共有を無効にすると、現在アクセスできる組織外のユーザーはアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="ad34b-127">When you disable external sharing, people outside the organization who currently have access will no longer have access.</span></span> <span data-ttu-id="ad34b-128">後で外部共有を再び有効にすると、これらのユーザーがアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="ad34b-128">If you later turn external sharing back on, access will be restored for these people.</span></span> <span data-ttu-id="ad34b-129">ユーザーが共有コンテンツにアクセスできないようにするには、そのユーザーを[Microsoft 365 グループから削除](/office365/admin/create-groups/add-or-remove-members-from-groups)するか、サイトからアクセス許可を削除するか、または[ファイルまたはフォルダーの共有を停止](https://support.microsoft.com/office/0a36470f-d7fe-40a0-bd74-0ac6c1e13323)します。</span><span class="sxs-lookup"><span data-stu-id="ad34b-129">To prevent a user from accessing a shared content, [remove them from the Microsoft 365 group](/office365/admin/create-groups/add-or-remove-members-from-groups), remove their permissions from the site, or [stop sharing the file or folder with them](https://support.microsoft.com/office/0a36470f-d7fe-40a0-bd74-0ac6c1e13323).</span></span> 
  
## <a name="enable-external-sharing-at-the-organization-level"></a><span data-ttu-id="ad34b-130">組織レベルで外部共有を有効にする</span><span class="sxs-lookup"><span data-stu-id="ad34b-130">Enable external sharing at the organization level</span></span>

<span data-ttu-id="ad34b-131">外部共有は組織レベルで既定で有効になっていますが、すべての新しいサイトで有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="ad34b-131">External sharing is turned on by default at the organization level, but not for all new sites.</span></span> <span data-ttu-id="ad34b-132">詳細については、「[外部共有の概要](/sharepoint/external-sharing-overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad34b-132">For info, see [External sharing overview](/sharepoint/external-sharing-overview).</span></span> 

> [!NOTE]
>  <span data-ttu-id="ad34b-133">任意のサイトで外部共有を許可するには、組織レベルでそれを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad34b-133">To allow external sharing for any site, you need to allow it at the organization level.</span></span> 
  
1. <span data-ttu-id="ad34b-134">[管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)で、[ホーム] ページの検索ボックスに「外部」と入力し、[**サイトの外部共有**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad34b-134">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), type "external" in the search box on the Home page, and choose **Sites external sharing**.</span></span>
  
2. <span data-ttu-id="ad34b-135">開いたページで、ユーザーが共有できる相手を、既存のゲストのみ、新規および既存のゲスト、またはすべてのユーザーの中から選択します。</span><span class="sxs-lookup"><span data-stu-id="ad34b-135">On the page that opens, choose whether users can share with existing guests only, new and existing guests, or anyone.</span></span> 
    
3. <span data-ttu-id="ad34b-136">[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad34b-136">Select **Save**.</span></span>
    
<span data-ttu-id="ad34b-137">組織レベルで外部共有を有効にした後、特定のサイトの外部共有を無効にするように共有設定を微調整できます。</span><span class="sxs-lookup"><span data-stu-id="ad34b-137">After you enable external sharing at the organization level, you can fine tune your sharing settings to disable external sharing for particular sites.</span></span> <span data-ttu-id="ad34b-138">詳細については、「[サイトの外部共有を有効または無効にする](/sharepoint/change-external-sharing-site)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad34b-138">For info, see [Turn external sharing on or off for a site](/sharepoint/change-external-sharing-site).</span></span>
  

  

    

