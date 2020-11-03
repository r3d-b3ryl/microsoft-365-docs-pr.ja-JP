---
title: 新機能管理を使用して新機能を表示または非表示にする
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Office デスクトップアプリの新機能である office デスクトップアプリのエンドユーザーに対して表示または非表示にする新コンテンツを決定します。
ms.openlocfilehash: 8a7511845dbcce56848834178ed81cd7b919de42
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841413"
---
# <a name="show-or-hide-new-features-using-whats-new-management"></a><span data-ttu-id="c2b35-103">新機能管理を使用して新機能を表示または非表示にする</span><span class="sxs-lookup"><span data-stu-id="c2b35-103">Show or hide new features using What's New Management</span></span>

<span data-ttu-id="c2b35-104">**Office の新機能 Windows の管理** により、組織は office デスクトップアプリのエンドユーザーに表示される機能を決定することができます。</span><span class="sxs-lookup"><span data-stu-id="c2b35-104">**Office What's New Management for Windows** allows your organization to decide which features are shown to end users in the Office desktop apps.</span></span> <span data-ttu-id="c2b35-105">コンテンツプレビューでは、リリースバージョンおよびチャネルごとに新しいコンテンツを表示できます。</span><span class="sxs-lookup"><span data-stu-id="c2b35-105">The content preview allows you to view new content for each release version and channel.</span></span> <span data-ttu-id="c2b35-106">その後、エンドユーザーに対して、各機能の新しいコンテンツを非表示にするか、表示するかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c2b35-106">You can then choose whether to hide or show what's new content for each feature to end users.</span></span> 

<span data-ttu-id="c2b35-107">「 **Office デスクトップアプリの新機能」で** は、アプリケーションのためにリリースされた新機能の一覧を示しています。</span><span class="sxs-lookup"><span data-stu-id="c2b35-107">The **What's new content in the Office desktop apps** highlights a list of new features that is released for an application.</span></span> <span data-ttu-id="c2b35-108">また、簡単な説明と、多くの場合、ユーザーが機能の使用方法を理解するのに役立つ画像またはビデオを含んでいます。</span><span class="sxs-lookup"><span data-stu-id="c2b35-108">It also contains a short description, and often a picture or a video to help customers learn how to use the feature.</span></span> 

<span data-ttu-id="c2b35-109">**Office の新機能** Microsoft 365 管理センターと [クライアント構成サービス](https://config.office.com)を利用できます。</span><span class="sxs-lookup"><span data-stu-id="c2b35-109">**Office What's New** management is available in the Microsoft 365 admin center and through the [Client Configuration Service](https://config.office.com).</span></span>

> [!NOTE]
> <span data-ttu-id="c2b35-110">グローバル管理者と Office アプリ管理者の役割は、ユーザーが Office アプリに表示する新しいコンテンツを管理します。</span><span class="sxs-lookup"><span data-stu-id="c2b35-110">Global admin and Office Apps admin roles manage the What's new content that users see in their Office apps.</span></span>

##  <a name="show-or-hide-new-features"></a><span data-ttu-id="c2b35-111">新機能の表示と非表示を切り替える</span><span class="sxs-lookup"><span data-stu-id="c2b35-111">Show or hide new features</span></span> 

<span data-ttu-id="c2b35-112">管理者は、チャネルの **最新情報** をプレビューしたり、 **Office の新機能** を使用してコンテンツのリリースを管理したりできます。</span><span class="sxs-lookup"><span data-stu-id="c2b35-112">Admins can preview the **what's new** content for a channel, and manage the release of the content by using the **Office What's New** management.</span></span>

1. <span data-ttu-id="c2b35-113">Microsoft 365 管理センターの [ **設定** ] で、[ **組織の設定** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2b35-113">In the Microsoft 365 admin center, under **Settings** , choose **Org settings** .</span></span>
2. <span data-ttu-id="c2b35-114">[ **サービス** ] タブで、[ **Office の新機能** ] [管理] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2b35-114">On the **Services** tab, choose **Office What's New management** .</span></span>
3. <span data-ttu-id="c2b35-115">機能名、短い説明、ターゲットアプリケーション、および各機能のリリースバージョンを表示する1つ以上のフィーチャーを、フライアウトパネルに表示します。</span><span class="sxs-lookup"><span data-stu-id="c2b35-115">Select one or more features to view the feature name, a short description, the target application, and the release version for each feature on the fly-out panel.</span></span>
4. <span data-ttu-id="c2b35-116">[ **ユーザーに表示** しない] または [ **ユーザーに表示] を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="c2b35-116">Choose **Hide from users** or **Show to users** .</span></span>  
    <span data-ttu-id="c2b35-117">既定で **表示** される状態は、管理者が機能の状態を **非表示** または **表示** に設定するまで、ユーザーに既定で機能の情報が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="c2b35-117">The status **Shown by default** indicates feature information is shown by default to users until the admin sets the status for a feature to **Hidden** or **Shown** .</span></span>  

    > [!NOTE]
    > <span data-ttu-id="c2b35-118">機能が複数の Office アプリで利用できる場合は、この機能を [非表示] に設定すると、すべての Office アプリの機能アナウンスが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="c2b35-118">If a feature is available in multiple Office apps, setting the feature to hidden hides the feature announcement in all of the Office apps.</span></span>

<span data-ttu-id="c2b35-119">Office には、このスケジュールに基づいて新しい機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="c2b35-119">New features appear in Office What's New Management based on this schedule:</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="c2b35-120">**チャネル**</span><span class="sxs-lookup"><span data-stu-id="c2b35-120">**Channel**</span></span> <br/> |<span data-ttu-id="c2b35-121">**管理プレビュー**</span><span class="sxs-lookup"><span data-stu-id="c2b35-121">**In management preview**</span></span> <br/> |<span data-ttu-id="c2b35-122">**アクションを実行する**</span><span class="sxs-lookup"><span data-stu-id="c2b35-122">**Take action**</span></span> <br/> |
|<span data-ttu-id="c2b35-123">**Current**</span><span class="sxs-lookup"><span data-stu-id="c2b35-123">**Current**</span></span> <br/> |<span data-ttu-id="c2b35-124">月の15日</span><span class="sxs-lookup"><span data-stu-id="c2b35-124">15th of the month</span></span>  <br/> |<span data-ttu-id="c2b35-125">毎月のリリースの 1-3 週間</span><span class="sxs-lookup"><span data-stu-id="c2b35-125">1 - 3 weeks before the monthly release</span></span> <br/> |
|<span data-ttu-id="c2b35-126">**月次 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="c2b35-126">**Monthly Enterprise**</span></span> <br/> |<span data-ttu-id="c2b35-127">月の最初</span><span class="sxs-lookup"><span data-stu-id="c2b35-127">First of the month</span></span>  <br/> |<span data-ttu-id="c2b35-128">新機能をもたらすメジャーリリースの2週間前</span><span class="sxs-lookup"><span data-stu-id="c2b35-128">Two weeks before the major release that brings new features</span></span> |
|<span data-ttu-id="c2b35-129">**半期エンタープライズ (プレビュー)**</span><span class="sxs-lookup"><span data-stu-id="c2b35-129">**Semi-Annual Enterprise (Preview)**</span></span> <br/> |<span data-ttu-id="c2b35-130">9月1日と3月1日</span><span class="sxs-lookup"><span data-stu-id="c2b35-130">Sept 1 and March 1</span></span> <br/> | <span data-ttu-id="c2b35-131">新機能をもたらすメジャーリリースの2週間前</span><span class="sxs-lookup"><span data-stu-id="c2b35-131">2 weeks before the major release that brings new features</span></span>|
|<span data-ttu-id="c2b35-132">**半期エンタープライズ**</span><span class="sxs-lookup"><span data-stu-id="c2b35-132">**Semi-Annual Enterprise**</span></span> <br/> |<span data-ttu-id="c2b35-133">1月1日と7月1日</span><span class="sxs-lookup"><span data-stu-id="c2b35-133">Jan 1 and July 1</span></span> <br/> | <span data-ttu-id="c2b35-134">新機能をもたらすメジャーリリースの2週間前</span><span class="sxs-lookup"><span data-stu-id="c2b35-134">2 weeks before the major release that brings new features</span></span><br/> |

<span data-ttu-id="c2b35-135">チャネル更新スケジュールの詳細については、「 [Microsoft 365 アプリの更新履歴 (日付別の一覧)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2b35-135">For more information about channel update schedules, see [Update history for Microsoft 365 Apps (listed by date)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date).</span></span>

## <a name="add-office-whats-new-management-card-to-the-admin-center-home-page"></a><span data-ttu-id="c2b35-136">Office の新しい管理カードを管理センターのホームページに追加する</span><span class="sxs-lookup"><span data-stu-id="c2b35-136">Add Office What's New Management card to the admin center home page</span></span>

1. <span data-ttu-id="c2b35-137">[Microsoft 365 admin] ページで、ページの上部にある [ **カードの追加** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c2b35-137">On the Microsoft 365 admin page, choose **Add card** on top of the page</span></span>
2. <span data-ttu-id="c2b35-138">[ **Office アプリの新機能** ] を一覧で見つけ、それを選択します。</span><span class="sxs-lookup"><span data-stu-id="c2b35-138">Locate **What's New in Office Apps** in the list and choose it.</span></span>
3. <span data-ttu-id="c2b35-139">カードがホームページに表示されたら、[ **管理** ] を選択して、組織の [機能を表示または非](#show-or-hide-new-features) 表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c2b35-139">Once the card is on our home page, you can choose **Manage** to [show or hide the features](#show-or-hide-new-features) for your organization.</span></span> 


## <a name="related-articles"></a><span data-ttu-id="c2b35-140">関連記事</span><span class="sxs-lookup"><span data-stu-id="c2b35-140">Related articles</span></span>

[<span data-ttu-id="c2b35-141">Office の新機能が一般公開されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c2b35-141">Office What's New management is now generally available</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)