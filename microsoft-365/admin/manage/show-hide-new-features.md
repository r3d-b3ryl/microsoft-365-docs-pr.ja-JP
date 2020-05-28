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
description: Office デスクトップアプリの新機能である office デスクトップアプリのエンドユーザーに対して、どの機能とその新しいコンテンツを表示するか、または非表示にするかを決定します。
ms.openlocfilehash: 0723823e76be2baf15273d23ad343d91bcec8d60
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399544"
---
# <a name="show-or-hide-new-features-using-whats-new-management"></a><span data-ttu-id="4b980-103">新機能管理を使用して新機能を表示または非表示にする</span><span class="sxs-lookup"><span data-stu-id="4b980-103">Show or hide new features using What's New Management</span></span>

<span data-ttu-id="4b980-104">Office の新機能 Win 32 では、組織は Office デスクトップアプリのエンドユーザーに対して表示する機能を決定することができます。</span><span class="sxs-lookup"><span data-stu-id="4b980-104">Office What's New Management for Win 32 allows your organization to decide which features are shown to or hidden from end users in the Office desktop app.</span></span> <span data-ttu-id="4b980-105">Office の各リリースには新機能と強化された機能が含まれており、コンテンツプレビューを使用すると、各リリースバージョンおよびチャネルの新しいコンテンツを表示したり、各機能に関する新しいコンテンツをエンドユーザーに対して表示するかどうかを選択したりできます。</span><span class="sxs-lookup"><span data-stu-id="4b980-105">Each release of Office includes new and improved features, and the content preview allows you to view new content for each release version and channel, and choose whether to hide or show What's new content for each feature to end users.</span></span> 

<span data-ttu-id="4b980-106">「Office デスクトップアプリの新機能の内容」には、そのアプリケーションでリリースされている新機能のリスト (簡単な説明を含む) と、お客様が機能を使用する方法を説明するために機能をリリースした画像またはビデオが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b980-106">The What's new content in the Office desktop apps highlights a curated list of new features being released for that application, with a short description, and often a picture or a video created by the team releasing the feature to help customers learn how to use the feature.</span></span> 

<span data-ttu-id="4b980-107">Office の新機能 Microsoft 365 管理センターと[クライアント構成サービス](https://config.office.com)を利用できます。</span><span class="sxs-lookup"><span data-stu-id="4b980-107">Office What's New management is available in the Microsoft 365 admin center and through the [Client Configuration Service](https://config.office.com).</span></span>

> [!NOTE]
> <span data-ttu-id="4b980-108">グローバル管理者と Office アプリ管理者の役割は、ユーザーが Office アプリに表示する新しいコンテンツを管理します。</span><span class="sxs-lookup"><span data-stu-id="4b980-108">Global admin and Office Apps admin roles manage the What's new content that users see in their Office apps.</span></span>

##  <a name="show-or-hide-new-features"></a><span data-ttu-id="4b980-109">新機能を表示または非表示にする</span><span class="sxs-lookup"><span data-stu-id="4b980-109">Show or hide new features</span></span> 

<span data-ttu-id="4b980-110">管理者は、チャネルの最新情報をプレビューしたり、Office の新機能を使用してコンテンツのリリースを管理したりできます。</span><span class="sxs-lookup"><span data-stu-id="4b980-110">Admins can preview the What's new content for a channel, and manage the release of the content using Office What's New Management.</span></span>

1. <span data-ttu-id="4b980-111">Microsoft 365 管理センターの [**設定**] で、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b980-111">In the Microsoft 365 admin center, under **Settings**, choose **Settings**.</span></span>

2. <span data-ttu-id="4b980-112">[**サービス**] タブで、[ **Office の新機能**] [管理] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b980-112">On the **Services** tab, choose **Office What's New Management**.</span></span>

3. <span data-ttu-id="4b980-113">機能名、短い説明、アプリケーション、および各機能のリリースバージョンを、フライアウトパネルに表示するには、1つまたは複数の機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="4b980-113">Select one or more features to view the feature name, a short description, the application, and the release version for each feature on the flyout panel.</span></span>

4. <span data-ttu-id="4b980-114">[**ユーザーに表示**しない] または [**ユーザーに表示] を**選択します。</span><span class="sxs-lookup"><span data-stu-id="4b980-114">Choose **Hide from users** or **Show to users**.</span></span>  

    <span data-ttu-id="4b980-115">既定で**表示**される状態は、管理者が機能の状態を**非表示**または**表示**に設定するまで、ユーザーに既定で機能の情報が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="4b980-115">The status **Shown by default** indicates feature information is shown by default to users until the admin sets the status for a feature to **Hidden** or **Shown**.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="4b980-116">機能が複数の Office アプリで利用できる場合は、この機能を [非表示] に設定すると、すべての Office アプリの機能アナウンスが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="4b980-116">If a feature is available in multiple Office apps, setting the feature to hidden hides the feature announcement in all of the Office apps.</span></span>

<span data-ttu-id="4b980-117">Office には、このスケジュールに基づいて新しい機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="4b980-117">New features appear in Office What's New Management based on this schedule:</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="4b980-118">**チャネル**</span><span class="sxs-lookup"><span data-stu-id="4b980-118">**Channel**</span></span> <br/> |<span data-ttu-id="4b980-119">**管理プレビュー**</span><span class="sxs-lookup"><span data-stu-id="4b980-119">**In management preview**</span></span> <br/> |<span data-ttu-id="4b980-120">**アクションを実行する**</span><span class="sxs-lookup"><span data-stu-id="4b980-120">**Take action**</span></span> <br/> |
|<span data-ttu-id="4b980-121">**毎月**</span><span class="sxs-lookup"><span data-stu-id="4b980-121">**Monthly**</span></span> <br/> |<span data-ttu-id="4b980-122">月の15日</span><span class="sxs-lookup"><span data-stu-id="4b980-122">15th of the month</span></span>  <br/> |<span data-ttu-id="4b980-123">毎月のリリースの 1-3 週間</span><span class="sxs-lookup"><span data-stu-id="4b980-123">1 - 3 weeks before the monthly release</span></span> <br/> |
|<span data-ttu-id="4b980-124">**半期 (対象指定)**</span><span class="sxs-lookup"><span data-stu-id="4b980-124">**Semi-annual (Targeted)**</span></span> <br/> |<span data-ttu-id="4b980-125">9月1日と3月1日</span><span class="sxs-lookup"><span data-stu-id="4b980-125">Sept 1 and March 1</span></span> <br/> | <span data-ttu-id="4b980-126">新機能をもたらすメジャーリリースの2週間前</span><span class="sxs-lookup"><span data-stu-id="4b980-126">2 weeks before the major release that brings new features</span></span>
|<span data-ttu-id="4b980-127">**半期**</span><span class="sxs-lookup"><span data-stu-id="4b980-127">**Semi-annual**</span></span> <br/> |<span data-ttu-id="4b980-128">1月1日と7月1日</span><span class="sxs-lookup"><span data-stu-id="4b980-128">Jan 1 and July 1</span></span> <br/> | <span data-ttu-id="4b980-129">新機能をもたらすメジャーリリースの2週間前</span><span class="sxs-lookup"><span data-stu-id="4b980-129">2 weeks before the major release that brings new features</span></span><br/> |

<span data-ttu-id="4b980-130">チャネル更新スケジュールの詳細については、「 [Microsoft 365 アプリの更新履歴 (日付別の一覧)](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4b980-130">For more information about channel update schedules, see [Update history for Microsoft 365 Apps (listed by date)](https://docs.microsoft.com/officeupdates/update-history-office365-proplus-by-date).</span></span>

## <a name="related-articles"></a><span data-ttu-id="4b980-131">関連記事</span><span class="sxs-lookup"><span data-stu-id="4b980-131">Related articles</span></span>

[<span data-ttu-id="4b980-132">Office の新機能が一般公開されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4b980-132">Office What's New management is now generally available</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)