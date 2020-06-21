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
ms.openlocfilehash: 7b9522a901078d6e235e295c184fec65c251338b
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717177"
---
# <a name="show-or-hide-new-features-using-whats-new-management"></a><span data-ttu-id="eb073-103">新機能管理を使用して新機能を表示または非表示にする</span><span class="sxs-lookup"><span data-stu-id="eb073-103">Show or hide new features using What's New Management</span></span>

<span data-ttu-id="eb073-104">Office の新機能 Windows では、Office デスクトップアプリでエンドユーザーに対して表示または非表示にする機能を組織が決定できます。</span><span class="sxs-lookup"><span data-stu-id="eb073-104">Office What's New Management for Windows allows your organization to decide which features are shown to or hidden from end users in the Office desktop app.</span></span> <span data-ttu-id="eb073-105">Office の各リリースには新機能と強化された機能が含まれており、コンテンツプレビューを使用すると、各リリースバージョンおよびチャネルの新しいコンテンツを表示したり、各機能に関する新しいコンテンツをエンドユーザーに対して表示するかどうかを選択したりできます。</span><span class="sxs-lookup"><span data-stu-id="eb073-105">Each release of Office includes new and improved features, and the content preview allows you to view new content for each release version and channel, and choose whether to hide or show What's new content for each feature to end users.</span></span> 

<span data-ttu-id="eb073-106">「Office デスクトップアプリの新機能の内容」には、そのアプリケーションでリリースされている新機能のリスト (簡単な説明を含む) と、お客様が機能を使用する方法を説明するために機能をリリースした画像またはビデオが含まれています。</span><span class="sxs-lookup"><span data-stu-id="eb073-106">The What's new content in the Office desktop apps highlights a curated list of new features being released for that application, with a short description, and often a picture or a video created by the team releasing the feature to help customers learn how to use the feature.</span></span> 

<span data-ttu-id="eb073-107">Office の新機能 Microsoft 365 管理センターと[クライアント構成サービス](https://config.office.com)を利用できます。</span><span class="sxs-lookup"><span data-stu-id="eb073-107">Office What's New management is available in the Microsoft 365 admin center and through the [Client Configuration Service](https://config.office.com).</span></span>

> [!NOTE]
> <span data-ttu-id="eb073-108">グローバル管理者と Office アプリ管理者の役割は、ユーザーが Office アプリに表示する新しいコンテンツを管理します。</span><span class="sxs-lookup"><span data-stu-id="eb073-108">Global admin and Office Apps admin roles manage the What's new content that users see in their Office apps.</span></span>

##  <a name="show-or-hide-new-features"></a><span data-ttu-id="eb073-109">新機能の表示と非表示を切り替える</span><span class="sxs-lookup"><span data-stu-id="eb073-109">Show or hide new features</span></span> 

<span data-ttu-id="eb073-110">管理者は、チャネルの最新情報をプレビューしたり、Office の新機能を使用してコンテンツのリリースを管理したりできます。</span><span class="sxs-lookup"><span data-stu-id="eb073-110">Admins can preview the What's new content for a channel, and manage the release of the content using Office What's New management.</span></span>

1. <span data-ttu-id="eb073-111">Microsoft 365 管理センターの [**設定**] で、[**組織の設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb073-111">In the Microsoft 365 admin center, under **Settings**, choose **Org settings**.</span></span>

2. <span data-ttu-id="eb073-112">[**サービス**] タブで、[ **Office の新機能**] [管理] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb073-112">On the **Services** tab, choose **Office What's New management**.</span></span>

3. <span data-ttu-id="eb073-113">機能名、短い説明、アプリケーション、および各機能のリリースバージョンを、フライアウトパネルに表示するには、1つまたは複数の機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb073-113">Select one or more features to view the feature name, a short description, the application, and the release version for each feature on the flyout panel.</span></span>

4. <span data-ttu-id="eb073-114">[**ユーザーに表示**しない] または [**ユーザーに表示] を**選択します。</span><span class="sxs-lookup"><span data-stu-id="eb073-114">Choose **Hide from users** or **Show to users**.</span></span>  

    <span data-ttu-id="eb073-115">既定で**表示**される状態は、管理者が機能の状態を**非表示**または**表示**に設定するまで、ユーザーに既定で機能の情報が表示されることを示します。</span><span class="sxs-lookup"><span data-stu-id="eb073-115">The status **Shown by default** indicates feature information is shown by default to users until the admin sets the status for a feature to **Hidden** or **Shown**.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="eb073-116">機能が複数の Office アプリで利用できる場合は、この機能を [非表示] に設定すると、すべての Office アプリの機能アナウンスが非表示になります。</span><span class="sxs-lookup"><span data-stu-id="eb073-116">If a feature is available in multiple Office apps, setting the feature to hidden hides the feature announcement in all of the Office apps.</span></span>

<span data-ttu-id="eb073-117">Office には、このスケジュールに基づいて新しい機能が追加されています。</span><span class="sxs-lookup"><span data-stu-id="eb073-117">New features appear in Office What's New Management based on this schedule:</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="eb073-118">**チャネル**</span><span class="sxs-lookup"><span data-stu-id="eb073-118">**Channel**</span></span> <br/> |<span data-ttu-id="eb073-119">**管理プレビュー**</span><span class="sxs-lookup"><span data-stu-id="eb073-119">**In management preview**</span></span> <br/> |<span data-ttu-id="eb073-120">**アクションを実行する**</span><span class="sxs-lookup"><span data-stu-id="eb073-120">**Take action**</span></span> <br/> |
|<span data-ttu-id="eb073-121">**Current**</span><span class="sxs-lookup"><span data-stu-id="eb073-121">**Current**</span></span> <br/> |<span data-ttu-id="eb073-122">月の15日</span><span class="sxs-lookup"><span data-stu-id="eb073-122">15th of the month</span></span>  <br/> |<span data-ttu-id="eb073-123">毎月のリリースの 1-3 週間</span><span class="sxs-lookup"><span data-stu-id="eb073-123">1 - 3 weeks before the monthly release</span></span> <br/> |
|<span data-ttu-id="eb073-124">**月次 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="eb073-124">**Monthly Enterprise**</span></span> <br/> |<span data-ttu-id="eb073-125">月の1日</span><span class="sxs-lookup"><span data-stu-id="eb073-125">1st of the month</span></span>  <br/> |<span data-ttu-id="eb073-126">新機能をもたらすメジャーリリースの2週間前</span><span class="sxs-lookup"><span data-stu-id="eb073-126">2 weeks before the major release that brings new features</span></span> |
|<span data-ttu-id="eb073-127">**半期エンタープライズ (プレビュー)**</span><span class="sxs-lookup"><span data-stu-id="eb073-127">**Semi-Annual Enterprise (Preview)**</span></span> <br/> |<span data-ttu-id="eb073-128">9月1日と3月1日</span><span class="sxs-lookup"><span data-stu-id="eb073-128">Sept 1 and March 1</span></span> <br/> | <span data-ttu-id="eb073-129">新機能をもたらすメジャーリリースの2週間前</span><span class="sxs-lookup"><span data-stu-id="eb073-129">2 weeks before the major release that brings new features</span></span>|
|<span data-ttu-id="eb073-130">**半期エンタープライズ**</span><span class="sxs-lookup"><span data-stu-id="eb073-130">**Semi-Annual Enterprise**</span></span> <br/> |<span data-ttu-id="eb073-131">1月1日と7月1日</span><span class="sxs-lookup"><span data-stu-id="eb073-131">Jan 1 and July 1</span></span> <br/> | <span data-ttu-id="eb073-132">新機能をもたらすメジャーリリースの2週間前</span><span class="sxs-lookup"><span data-stu-id="eb073-132">2 weeks before the major release that brings new features</span></span><br/> |

<span data-ttu-id="eb073-133">チャネル更新スケジュールの詳細については、「 [Microsoft 365 アプリの更新履歴 (日付別の一覧)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb073-133">For more information about channel update schedules, see [Update history for Microsoft 365 Apps (listed by date)](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date).</span></span>

## <a name="related-articles"></a><span data-ttu-id="eb073-134">関連記事</span><span class="sxs-lookup"><span data-stu-id="eb073-134">Related articles</span></span>

[<span data-ttu-id="eb073-135">Office の新機能が一般公開されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="eb073-135">Office What's New management is now generally available</span></span>](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)