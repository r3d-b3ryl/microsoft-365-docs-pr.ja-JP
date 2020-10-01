---
title: Microsoft 365 でのディレクトリ同期状態の表示
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: この記事では、Office 365 でディレクトリ同期の状態を確認する方法について説明します。
ms.openlocfilehash: 7577ed358a262d5b0ef2932bc73cf61941bec31b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326951"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="138bb-103">Microsoft 365 でのディレクトリ同期状態の表示</span><span class="sxs-lookup"><span data-stu-id="138bb-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="138bb-104">オンプレミス環境と Microsoft 365 を同期することによって、オンプレミスの Active Directory ドメインサービス (AD DS) と Azure Active Directory (Azure AD) が統合されている場合は、同期の状態を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="138bb-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="138bb-105">ディレクトリ同期の状態を表示する</span><span class="sxs-lookup"><span data-stu-id="138bb-105">View directory synchronization status</span></span>

- <span data-ttu-id="138bb-106">[Microsoft 365 管理センター](https://admin.microsoft.com)にサインインし、ホームページの [ **DirSync Status** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="138bb-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="138bb-107">または、[アクティブなユーザー] ページ**に移動**し、[ \> **Active users\*\*\*\*アクティブなユーザー** ] ページで、[ディレクトリ同期の**追加**] を選択し \> **Directory synchronization**ます。</span><span class="sxs-lookup"><span data-stu-id="138bb-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="138bb-108">[ **ディレクトリ同期** ] ウィンドウで、[ **DirSync management に移動] を**選択します。</span><span class="sxs-lookup"><span data-stu-id="138bb-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="138bb-109">[ディレクトリ同期の管理] ページの情報</span><span class="sxs-lookup"><span data-stu-id="138bb-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="138bb-110">次の表に、ページの情報を取得できる機能を示します。</span><span class="sxs-lookup"><span data-stu-id="138bb-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="138bb-111">ディレクトリ同期に問題がある場合は、このページにもエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="138bb-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="138bb-112">発生する可能性のあるさまざまなエラーの詳細については、「 [Microsoft 365 でのディレクトリ同期エラーの識別](identify-directory-synchronization-errors.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="138bb-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="138bb-113">アイテム</span><span class="sxs-lookup"><span data-stu-id="138bb-113">Item</span></span>|<span data-ttu-id="138bb-114">目的</span><span class="sxs-lookup"><span data-stu-id="138bb-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="138bb-115">**確認されたドメイン**</span><span class="sxs-lookup"><span data-stu-id="138bb-115">**Domains verified**</span></span> | <span data-ttu-id="138bb-116">自分が所有していることを確認した Microsoft 365 テナント内のドメインの数。</span><span class="sxs-lookup"><span data-stu-id="138bb-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="138bb-117">**確認されていないドメイン**</span><span class="sxs-lookup"><span data-stu-id="138bb-117">**Domains not verified**</span></span> | <span data-ttu-id="138bb-118">追加されたが確認されていないドメイン。</span><span class="sxs-lookup"><span data-stu-id="138bb-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="138bb-119">**ディレクトリ同期の有効化**</span><span class="sxs-lookup"><span data-stu-id="138bb-119">**Directory sync enabled**</span></span> |<span data-ttu-id="138bb-120">True または False。</span><span class="sxs-lookup"><span data-stu-id="138bb-120">True or False.</span></span> <span data-ttu-id="138bb-121">ディレクトリ同期を有効にしたかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="138bb-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="138bb-122">**最新のディレクトリ同期**</span><span class="sxs-lookup"><span data-stu-id="138bb-122">**Latest directory sync**</span></span> | <span data-ttu-id="138bb-123">ディレクトリ同期が最後に実行した時刻。</span><span class="sxs-lookup"><span data-stu-id="138bb-123">Last time directory sync ran.</span></span> <span data-ttu-id="138bb-124">前回の同期が3日以上前の場合は、警告とトラブルシューティングツールへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="138bb-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="138bb-125">**パスワード同期の有効化**</span><span class="sxs-lookup"><span data-stu-id="138bb-125">**Password sync enabled**</span></span> | <span data-ttu-id="138bb-126">True または False。</span><span class="sxs-lookup"><span data-stu-id="138bb-126">True or False.</span></span> <span data-ttu-id="138bb-127">オンプレミスと Microsoft 365 テナント間でパスワードハッシュを同期するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="138bb-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="138bb-128">**前回のパスワード同期**</span><span class="sxs-lookup"><span data-stu-id="138bb-128">**Last Password Sync**</span></span> | <span data-ttu-id="138bb-129">前回のパスワードハッシュ同期を実行した時刻。</span><span class="sxs-lookup"><span data-stu-id="138bb-129">Last time password hash sync ran.</span></span> <span data-ttu-id="138bb-130">前回の同期が3日以上前の場合は、警告とトラブルシューティングツールへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="138bb-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="138bb-131">**ディレクトリ同期クライアントバージョン**</span><span class="sxs-lookup"><span data-stu-id="138bb-131">**Directory sync client version**</span></span> | <span data-ttu-id="138bb-132">Azure AD Connect の新しいバージョンがリリースされた場合のダウンロードリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="138bb-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="138bb-133">**ディレクトリ同期サービスアカウント**</span><span class="sxs-lookup"><span data-stu-id="138bb-133">**Directory sync service account**</span></span> | <span data-ttu-id="138bb-134">Microsoft 365 ディレクトリ同期サービスアカウントの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="138bb-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="138bb-135">同期の状態を監視する</span><span class="sxs-lookup"><span data-stu-id="138bb-135">Monitor synchronization health</span></span>

<span data-ttu-id="138bb-136">このセクションでは、Azure AD Connect Health エージェントを各オンプレミス AD DS ドメイン コントローラーにインストールして、Azure AD Connect によって提供されている ID インフラストラクチャと 同期サービスを監視します。</span><span class="sxs-lookup"><span data-stu-id="138bb-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="138bb-137">監視情報は Azure AD Connect Health ポータルで使用可能になります。このポータルでは、アラート、パフォーマンス監視、使用状況分析などの情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="138bb-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="138bb-138">Azure AD Connect Health の使用法に関する重要な設計上の決定は、Azure AD Connect をどのように使用しているかに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="138bb-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="138bb-139">**管理認証**オプションを使用している場合は、最初に「[Azure AD Connect Health を使用した Azure AD Connect の同期の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)」を参照し、Azure AD Connect Health について理解し、構成します。</span><span class="sxs-lookup"><span data-stu-id="138bb-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="138bb-140">Active Directory フェデレーション サービス (AD FS) で**フェデレーション認証**を使用してアカウントとグループの名前だけを同期している場合は、最初に「[Azure AD Connect Health を使用した AD FS の監視](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)」を参照し Azure AD Connect Health について理解し、構成します。</span><span class="sxs-lookup"><span data-stu-id="138bb-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="138bb-141">完了すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="138bb-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="138bb-142">Azure AD Connect Health エージェントがオンプレミス ID プロバイダー サーバーにインストールされている。</span><span class="sxs-lookup"><span data-stu-id="138bb-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="138bb-143">Azure AD Connect Health ポータルでは、Microsoft 365 サブスクリプションの Azure AD テナントでオンプレミス インフラストラクチャの現在の状態と同期アクティビティを表示しています。</span><span class="sxs-lookup"><span data-stu-id="138bb-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>

