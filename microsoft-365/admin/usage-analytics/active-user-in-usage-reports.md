---
title: 使用状況レポートのMicrosoft 365ユーザー
ms.author: efrene
author: efrene
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
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: 使用状況分析、アクティビティ レポート、導入Microsoft 365のアクティブ ユーザーについて学習します。
ms.openlocfilehash: 21663722d1a3850389db2ad79321daf363d314c6
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579076"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a><span data-ttu-id="09425-103">使用状況レポートのMicrosoft 365ユーザー</span><span class="sxs-lookup"><span data-stu-id="09425-103">Active user in Microsoft 365 usage reports</span></span>

## <a name="active-user-in-usage-reports"></a><span data-ttu-id="09425-104">利用状況レポートのアクティブ ユーザー</span><span class="sxs-lookup"><span data-stu-id="09425-104">Active user in usage reports</span></span>

<span data-ttu-id="09425-105">管理センターの利用状況分析Microsoft 365アクティビティ Microsoft 365[](usage-analytics.md)のアクティブ なユーザーは、[次のように定義](../activity-reports/activity-reports.md)されます。</span><span class="sxs-lookup"><span data-stu-id="09425-105">An active user of Microsoft 365 products for [Microsoft 365 usage analytics](usage-analytics.md) and the [Activity Reports in the admin center](../activity-reports/activity-reports.md) is defined as follows.</span></span> 
  
|<span data-ttu-id="09425-106">**製品**</span><span class="sxs-lookup"><span data-stu-id="09425-106">**Product**</span></span>|<span data-ttu-id="09425-107">**アクティブ ユーザーの定義**</span><span class="sxs-lookup"><span data-stu-id="09425-107">**Definition of an active user**</span></span>|<span data-ttu-id="09425-108">**注**</span><span class="sxs-lookup"><span data-stu-id="09425-108">**Notes**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="09425-109">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="09425-109">Exchange Online</span></span>  <br/> |<span data-ttu-id="09425-110">次のアクションを実行したユーザー: [読み取りとしてマークする]、メッセージを送信する、予定を作成する、会議出席依頼を送信する、(仮として) 承諾する、または会議出席依頼を辞退する、会議をキャンセルする。</span><span class="sxs-lookup"><span data-stu-id="09425-110">Any user who has performed any of the following actions: Mark as read, send messages, create appointments, send meeting requests, accept (as tentative) or decline meeting requests, cancel meetings.</span></span>  <br/> |<span data-ttu-id="09425-111">予定表の情報は表示されません。これは今後の更新プログラムで追加される予定です。</span><span class="sxs-lookup"><span data-stu-id="09425-111">No calendar information is represented, this will be added in an upcoming update.</span></span>  <br/> |
|<span data-ttu-id="09425-112">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="09425-112">SharePoint Online</span></span>  <br/> |<span data-ttu-id="09425-113">作成、変更、表示、削除、内部または外部との共有、サイトのクライアントとの同期、サイトのページの閲覧により、ファイルを操作したあらゆるユーザー。</span><span class="sxs-lookup"><span data-stu-id="09425-113">Any user who has interacted with a file by creating, modifying, viewing, deleting, sharing internally or externally, or synchronizing to clients on any site or viewed a page on any site.</span></span>  <br/> |<span data-ttu-id="09425-114">Microsoft 365 Usage Analytics テンプレート アプリの SharePoint Online のアクティブなユーザー メトリックは、SharePoint チーム サイトまたはグループ サイトに対してファイルアクティビティを行ったユーザーのみを反映します。</span><span class="sxs-lookup"><span data-stu-id="09425-114">The active user metric for SharePoint Online in the Microsoft 365 Usage Analytics template app only reflect users who did file activity against a SharePoint Team site or a Group site.</span></span> <span data-ttu-id="09425-115">テンプレート アプリが更新され、管理センターの利用状況レポートと同じ定義に同期されます。</span><span class="sxs-lookup"><span data-stu-id="09425-115">The template app will be updated to synchronize the definition to the same as that on the usage reports in the admin center.</span></span>  <br/> |
|<span data-ttu-id="09425-116">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="09425-116">OneDrive for Business</span></span>  <br/> |<span data-ttu-id="09425-117">作成、変更、表示、削除、内部または外部との共有、クライアントとの同期により、ファイルを操作したあらゆるユーザー。</span><span class="sxs-lookup"><span data-stu-id="09425-117">Any user who has interacted with a file by creating, modifying, viewing, deleting, sharing internally or externally, or synchronizing to clients.</span></span>  <br/> ||
|<span data-ttu-id="09425-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="09425-118">Yammer</span></span>  <br/> |<span data-ttu-id="09425-119">Yammer でメッセージを読んだり、投稿したり、「いいね」を付けたりしたあらゆるユーザー。</span><span class="sxs-lookup"><span data-stu-id="09425-119">Any user who has read, posted, or liked a message on Yammer.</span></span>  <br/> ||
|<span data-ttu-id="09425-120">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="09425-120">Skype for Business</span></span>  <br/> |<span data-ttu-id="09425-121">ピアツーピアのセッション (インスタント メッセージ、通話、テレビ電話、アプリケーション共有、ファイル転送など) に参加した、あるいは会議を手配したか、会議に参加したあらゆるユーザー。</span><span class="sxs-lookup"><span data-stu-id="09425-121">Any user who has participated in a peer-to-peer session (including instant messaging, audio and video calls, application sharing, and file transfers) or who has organized or participated in a conference.</span></span>  <br/> ||
|<span data-ttu-id="09425-122">Office</span><span class="sxs-lookup"><span data-stu-id="09425-122">Office</span></span>  <br/> |<span data-ttu-id="09425-123">少なくとも 1 つのデバイスで、Microsoft 365 Pro Plus、Visio Pro、Project Proサブスクリプションをアクティブ化したユーザー。</span><span class="sxs-lookup"><span data-stu-id="09425-123">Any user who has activated their Microsoft 365 Pro Plus, Visio Pro or Project Pro subscription on at least one device.</span></span>  <br/> ||
|<span data-ttu-id="09425-124">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="09425-124">Microsoft 365 Groups</span></span>  <br/> |<span data-ttu-id="09425-125">(メッセージがグループに送信されている場合) メールボックスを操作するあらゆるグループ メンバー。</span><span class="sxs-lookup"><span data-stu-id="09425-125">Any group member that has mailbox activity (if a message has been sent to the group)</span></span>  <br/> |<span data-ttu-id="09425-126">この定義は、グループ サイト ファイルアクティビティとグループ アクティビティ (Yammer サイトでのファイル アクティビティと、グループに関連付けられた Yammer グループに投稿されたメッセージ) で拡張されます。このデータは現在、利用状況分析テンプレート アプリMicrosoft 365使用できません</span><span class="sxs-lookup"><span data-stu-id="09425-126">This definition will be enhanced with group site file activity and Yammer group activity (file activity on group site and message posted to Yammer group associated with the group.) This data is currently not available in the Microsoft 365 Usage Analytics template app</span></span>  <br/> |
|<span data-ttu-id="09425-127">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="09425-127">Microsoft Teams</span></span>  <br/> |<span data-ttu-id="09425-128">チャット メッセージ、プライベート チャット メッセージ、通話、会議、その他のアクティビティに参加したユーザー。</span><span class="sxs-lookup"><span data-stu-id="09425-128">Any user who has participated in chat messages, private chat messages, calls,meetings or other activity.</span></span> <span data-ttu-id="09425-129">その他のアクティビティは、メッセージ、アプリ、ファイルの作業、検索、チームとチャネルの後処理、および好意など、ユーザーによる他のチーム アクティビティの数として定義されます。これらに限定されません。</span><span class="sxs-lookup"><span data-stu-id="09425-129">Other activity is defined as the number of other team activities by the user some of which include, and not limited to: liking messages, apps, working on files, searching, following teams and channel and favoriting them.</span></span>  <br/> ||
   
## <a name="adoption-metrics"></a><span data-ttu-id="09425-130">導入指標</span><span class="sxs-lookup"><span data-stu-id="09425-130">Adoption Metrics</span></span>

<span data-ttu-id="09425-131">[Microsoft 365分析には](usage-analytics.md)、アクティブ ユーザーに関連する追加の導入指標が含まれているので、時間の過ぎた製品の採用を示します。</span><span class="sxs-lookup"><span data-stu-id="09425-131">[Microsoft 365 usage analytics](usage-analytics.md) contains additional adoption metrics related to active users to show adoption of the products over time.</span></span> <span data-ttu-id="09425-132">これらの指標は、選択した月、年、および製品に対して有効であり、次のように定義されます。</span><span class="sxs-lookup"><span data-stu-id="09425-132">These metrics are valid for the month, year, and product selected and are defined as follows.</span></span> 
  
|<span data-ttu-id="09425-133">**測定基準**</span><span class="sxs-lookup"><span data-stu-id="09425-133">**Metric**</span></span>|<span data-ttu-id="09425-134">**説明**</span><span class="sxs-lookup"><span data-stu-id="09425-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="09425-135">EnabledUsers</span><span class="sxs-lookup"><span data-stu-id="09425-135">EnabledUsers</span></span>  <br/> |<span data-ttu-id="09425-136">その月に製品を使用できるユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="09425-136">Number of users enabled to use the product in the month.</span></span>  <br/> |
|<span data-ttu-id="09425-137">ActiveUsers</span><span class="sxs-lookup"><span data-stu-id="09425-137">ActiveUsers</span></span>  <br/> |<span data-ttu-id="09425-138">月にアクティブなユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="09425-138">Number of users active in the month.</span></span>  <br/> |
|<span data-ttu-id="09425-139">MoMReturningUsers</span><span class="sxs-lookup"><span data-stu-id="09425-139">MoMReturningUsers</span></span>  <br/> |<span data-ttu-id="09425-140">前の月にもアクティブだった月にアクティブなユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="09425-140">Number of users active in the month that were also active in the preceding month.</span></span>  <br/> |
|<span data-ttu-id="09425-141">FirstTimeUsers</span><span class="sxs-lookup"><span data-stu-id="09425-141">FirstTimeUsers</span></span>  <br/> |<span data-ttu-id="09425-142">以前にサービスを使用したことがない月にアクティブなユーザーの数。</span><span class="sxs-lookup"><span data-stu-id="09425-142">Number of users active in the month that had never used the service before.</span></span>  <br/> |
|<span data-ttu-id="09425-143">CumulativeActiveUsers</span><span class="sxs-lookup"><span data-stu-id="09425-143">CumulativeActiveUsers</span></span>  <br/> |<span data-ttu-id="09425-144">月にアクティブなユーザーの数と前の月の数。</span><span class="sxs-lookup"><span data-stu-id="09425-144">Number of users active in the month plus any preceding month.</span></span>  <br/> |
|<span data-ttu-id="09425-145">ActiveUsers(%)</span><span class="sxs-lookup"><span data-stu-id="09425-145">ActiveUsers(%)</span></span>  <br/> |<span data-ttu-id="09425-146">ユーザーの割合は、その月に有効になっているユーザーの数と比較して、その月にアクティブな最も近い 10 分の 1 に四捨五入されます。</span><span class="sxs-lookup"><span data-stu-id="09425-146">Percent of users, rounded to the nearest tenth, active in the month compared to the number of users enabled in that month.</span></span>  <br/> |
|<span data-ttu-id="09425-147">MoMReturningUsers(%)</span><span class="sxs-lookup"><span data-stu-id="09425-147">MoMReturningUsers(%)</span></span>  <br/> |<span data-ttu-id="09425-148">ユーザーの割合 (最も近い 10 分の 1 に四捨五入) は、前の月にもアクティブであった月にアクティブで、アクティブなユーザーの数と比較します。</span><span class="sxs-lookup"><span data-stu-id="09425-148">Percent of users, rounded to the nearest tenth, active in the month that were also active in the preceding month compared to the number of active users.</span></span>  <br/> |
   
<span data-ttu-id="09425-149">MoMReturningUsers、FirstTimeUsers、CumulativeActiveUsers は、2018 年 1 月 1 日からリセットされ &amp; 、Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="09425-149">MoMReturningUsers, FirstTimeUsers, &amp; CumulativeActiveUsers were reset starting January 1st 2018 with the inclusion of Microsoft Teams.</span></span>
  
