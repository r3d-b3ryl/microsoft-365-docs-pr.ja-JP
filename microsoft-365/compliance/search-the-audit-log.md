---
title: Office 365 のユーザーおよび管理者のアクティビティについて監査ログを検索する
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
description: Office 365 監査ログは、統合監査ログです。 なぜ統合監査ログが必要なのでしょうか。 組織が加入しているほとんどの Office 365 サービスからのイベントは、検索可能な単一の監査ログに記録されるためです。 つまり、次のサービスでユーザーおよび管理者のアクティビティを検索できます。
ms.openlocfilehash: 82ed3c1afd4f59136b04120982ddb1433f4dd0eb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597534"
---
# <a name="search-the-audit-log-for-user-and-admin-activity-in-office-365"></a><span data-ttu-id="fabec-106">Office 365 のユーザーおよび管理者のアクティビティについて監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="fabec-106">Search the audit log for user and admin activity in Office 365</span></span>

<span data-ttu-id="fabec-107">Office 365 監査ログは、統合監査ログです。</span><span class="sxs-lookup"><span data-stu-id="fabec-107">The Office 365 audit log is a unified audit log.</span></span> <span data-ttu-id="fabec-108">なぜ統合監査ログが必要なのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="fabec-108">Why a unified audit log?</span></span> <span data-ttu-id="fabec-109">組織が加入しているほとんどの Office 365 サービスからのイベントは、検索可能な単一の監査ログに記録されるためです。</span><span class="sxs-lookup"><span data-stu-id="fabec-109">Because events from most Office 365 services that you're organization subscribes to are recorded in a single audit log that you can search.</span></span> <span data-ttu-id="fabec-110">つまり、次のサービスでユーザーおよび管理者のアクティビティを検索できます。</span><span class="sxs-lookup"><span data-stu-id="fabec-110">That means you can search for user and admin activity in these services:</span></span> 
  
- <span data-ttu-id="fabec-111">SharePoint</span><span class="sxs-lookup"><span data-stu-id="fabec-111">SharePoint</span></span>
- <span data-ttu-id="fabec-112">OneDrive</span><span class="sxs-lookup"><span data-stu-id="fabec-112">OneDrive</span></span>
- <span data-ttu-id="fabec-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="fabec-113">Exchange</span></span>
- <span data-ttu-id="fabec-114">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fabec-114">Azure Active Directory</span></span>
- <span data-ttu-id="fabec-115">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fabec-115">Microsoft Teams</span></span>
- <span data-ttu-id="fabec-116">電子情報開示</span><span class="sxs-lookup"><span data-stu-id="fabec-116">eDiscovery</span></span>
- <span data-ttu-id="fabec-117">Power BI</span><span class="sxs-lookup"><span data-stu-id="fabec-117">Power BI</span></span>
- <span data-ttu-id="fabec-118">Yammer</span><span class="sxs-lookup"><span data-stu-id="fabec-118">Yammer</span></span>
- <span data-ttu-id="fabec-119">Sway</span><span class="sxs-lookup"><span data-stu-id="fabec-119">Sway</span></span>
- <span data-ttu-id="fabec-120">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="fabec-120">Microsoft Stream</span></span>
   
 ## <a name="set-up-auditing"></a><span data-ttu-id="fabec-121">監査の設定</span><span class="sxs-lookup"><span data-stu-id="fabec-121">Set up auditing</span></span>
  
<span data-ttu-id="fabec-122">Office 365 監査ログを検索するには、いくつかの作業を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fabec-122">There's few things you have to do before you can search the Office 365 audit log.</span></span>
  
- <span data-ttu-id="fabec-123">[監査ログの検索を有効](turn-audit-log-search-on-or-off.md)にして、検索可能なイベントの記録を開始する</span><span class="sxs-lookup"><span data-stu-id="fabec-123">[Turn on audit log search](turn-audit-log-search-on-or-off.md) to start recording events that you can search for</span></span> 
    
- <span data-ttu-id="fabec-124">メールボックスに関連するイベントを検索できるように、[メールボックスの監査を有効に](enable-mailbox-auditing.md)します。ユーザーが自分のメールボックスにサインインした場合や、回復可能なアイテムフォルダーからアイテムを削除した場合などです。</span><span class="sxs-lookup"><span data-stu-id="fabec-124">[Enable mailbox auditing](enable-mailbox-auditing.md) so you can search for mailbox-related events; such as when a user signs in to their mailbox or purges items from their Recoverable Items folder</span></span> 
    
 ## <a name="search-the-audit-log"></a><span data-ttu-id="fabec-125">監査ログの検索</span><span class="sxs-lookup"><span data-stu-id="fabec-125">Search the audit log</span></span>
  
<span data-ttu-id="fabec-126">監査を有効にした後は、複数の Office 365 サービスから、何百もの種類のイベントを検索します。</span><span class="sxs-lookup"><span data-stu-id="fabec-126">After you turn on auditing, you search for hundreds of individual types of events from multiple Office 365 services.</span></span>
  
- <span data-ttu-id="fabec-127">ユーザーおよび管理者のアクティビティの[監査ログを検索する](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="fabec-127">[Search the audit log](search-the-audit-log-in-security-and-compliance.md) for user and admin activities</span></span> 
    
- <span data-ttu-id="fabec-128">検索結果に含まれる各監査レコードの[詳細なプロパティを理解する](detailed-properties-in-the-office-365-audit-log.md)</span><span class="sxs-lookup"><span data-stu-id="fabec-128">[Understand the detailed properties](detailed-properties-in-the-office-365-audit-log.md) in each auditing record included in the search results</span></span> 
    
- <span data-ttu-id="fabec-129">管理者およびコンプライアンスマネージャーによって実行された[電子情報開示関連アクティビティを検索](search-for-ediscovery-activities-in-the-audit-log.md)する</span><span class="sxs-lookup"><span data-stu-id="fabec-129">[Search for eDiscovery-related activities](search-for-ediscovery-activities-in-the-audit-log.md) performed by admins and compliance managers</span></span> 
