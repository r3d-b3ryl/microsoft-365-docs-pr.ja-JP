---
title: ユーザーおよび管理者のアクティビティの監査ログを検索する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/18/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
search.appverid: MOE150
ms.assetid: 57ca5138-0ae0-4d34-bd40-240441ef2fb6
description: 監査ログは、統合監査ログです。 なぜ統合監査ログが必要なのでしょうか。 組織がサブスクライブしているほとんどのサービスからのイベントは、検索可能な単一の監査ログに記録されるためです。 つまり、次のサービスでユーザーおよび管理者のアクティビティを検索できます。
ms.openlocfilehash: 95f5025e4831223c93251c7c22d1f43d44086d48
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43625097"
---
# <a name="search-the-audit-log-for-user-and-admin-activity"></a><span data-ttu-id="25f14-106">ユーザーおよび管理者のアクティビティの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="25f14-106">Search the audit log for user and admin activity</span></span>

<span data-ttu-id="25f14-107">監査ログは、統合監査ログです。</span><span class="sxs-lookup"><span data-stu-id="25f14-107">The audit log is a unified audit log.</span></span> <span data-ttu-id="25f14-108">なぜ統合監査ログが必要なのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="25f14-108">Why a unified audit log?</span></span> <span data-ttu-id="25f14-109">組織が加入しているほとんどのサービスからのイベントは、検索可能な単一の監査ログに記録されるためです。</span><span class="sxs-lookup"><span data-stu-id="25f14-109">Because events from most services that you're organization subscribes to are recorded in a single audit log that you can search.</span></span> <span data-ttu-id="25f14-110">つまり、次のサービスでユーザーおよび管理者のアクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="25f14-110">That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="25f14-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="25f14-111">SharePoint</span></span>
- <span data-ttu-id="25f14-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="25f14-112">OneDrive</span></span>
- <span data-ttu-id="25f14-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="25f14-113">Exchange</span></span>
- <span data-ttu-id="25f14-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="25f14-114">Azure Active Directory</span></span>
- <span data-ttu-id="25f14-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25f14-115">Microsoft Teams</span></span>
- <span data-ttu-id="25f14-116">電子情報開示</span><span class="sxs-lookup"><span data-stu-id="25f14-116">eDiscovery</span></span>
- <span data-ttu-id="25f14-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="25f14-117">Power BI</span></span>
- <span data-ttu-id="25f14-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="25f14-118">Yammer</span></span>
- <span data-ttu-id="25f14-119">Sway</span><span class="sxs-lookup"><span data-stu-id="25f14-119">Sway</span></span>
- <span data-ttu-id="25f14-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="25f14-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="25f14-121">監査の設定</span><span class="sxs-lookup"><span data-stu-id="25f14-121">Set up auditing</span></span>
  
<span data-ttu-id="25f14-122">監査ログを検索するには、いくつかの作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="25f14-122">There's few things you have to do before you can search the audit log.</span></span>
  
- <span data-ttu-id="25f14-123">[監査ログの検索を有効](turn-audit-log-search-on-or-off.md)にして、検索可能なイベントの記録を開始する</span><span class="sxs-lookup"><span data-stu-id="25f14-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="25f14-124">メールボックスに関連するイベントを検索できるように、[メールボックスの監査を有効に](enable-mailbox-auditing.md)します。ユーザーが自分のメールボックスにサインインした場合や、回復可能なアイテムフォルダーからアイテムを削除した場合などです。</span><span class="sxs-lookup"><span data-stu-id="25f14-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="25f14-125">監査ログの検索</span><span class="sxs-lookup"><span data-stu-id="25f14-125">Search the audit log</span></span>
  
<span data-ttu-id="25f14-126">監査を有効にした後は、複数の Microsoft 365 サービスから、何百もの種類のイベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="25f14-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Microsoft 365 services.</span></span>
  
- <span data-ttu-id="25f14-127">ユーザーおよび管理者のアクティビティの[監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="25f14-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="25f14-128">検索結果に含まれる各監査レコードの[詳細なプロパティを理解する](detailed-properties-in-the-office-365-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="25f14-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="25f14-129">管理者およびコンプライアンスマネージャーによって実行された[電子情報開示関連アクティビティを検索](search-for-ediscovery-activities-in-the-audit-log.md)する</span><span class="sxs-lookup"><span data-stu-id="25f14-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 
