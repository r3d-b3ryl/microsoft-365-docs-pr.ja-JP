---
title: Microsoft 365 でディレクトリ同期の状態を表示する
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
description: この記事では、365 でディレクトリ同期の状態を確認するOfficeします。
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924662"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="d469d-103">Microsoft 365 でディレクトリ同期の状態を表示する</span><span class="sxs-lookup"><span data-stu-id="d469d-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="d469d-104">オンプレミスの Active Directory ドメイン サービス (AD DS) を Azure Active Directory (Azure AD) と統合した場合は、オンプレミス環境を Microsoft 365 と同期することで、同期の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d469d-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="d469d-105">ディレクトリ同期の状態を表示する</span><span class="sxs-lookup"><span data-stu-id="d469d-105">View directory synchronization status</span></span>

- <span data-ttu-id="d469d-106">[Microsoft 365](https://admin.microsoft.com)管理センターにサインインし、ホーム ページで **[DirSync Status]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d469d-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="d469d-107">または、[ユーザー] [アクティブな **ユーザー]** に移動し、[アクティブなユーザー] ページで [その他のディレクトリ \> 同期] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d469d-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="d469d-108">[ディレクトリ同期 **] ウィンドウで\*\*\*\*、[DirSync 管理に移動] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d469d-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="d469d-109">[ディレクトリ同期の管理] ページの情報</span><span class="sxs-lookup"><span data-stu-id="d469d-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="d469d-110">次の表に、ページで情報を取得できる機能の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="d469d-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="d469d-111">ディレクトリ同期に問題がある場合は、このページにもエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d469d-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="d469d-112">発生する可能性のあるさまざまなエラーの詳細については [、「Microsoft 365 でディレクトリ同期エラーを識別する」を参照してください](identify-directory-synchronization-errors.md)。</span><span class="sxs-lookup"><span data-stu-id="d469d-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="d469d-113">アイテム</span><span class="sxs-lookup"><span data-stu-id="d469d-113">Item</span></span>|<span data-ttu-id="d469d-114">目的</span><span class="sxs-lookup"><span data-stu-id="d469d-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="d469d-115">**ドメインが検証済み**</span><span class="sxs-lookup"><span data-stu-id="d469d-115">**Domains verified**</span></span> | <span data-ttu-id="d469d-116">自分が所有している検証済みの Microsoft 365 テナント内のドメインの数。</span><span class="sxs-lookup"><span data-stu-id="d469d-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="d469d-117">**ドメインが検証されていない**</span><span class="sxs-lookup"><span data-stu-id="d469d-117">**Domains not verified**</span></span> | <span data-ttu-id="d469d-118">追加したが、検証されていないドメイン。</span><span class="sxs-lookup"><span data-stu-id="d469d-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="d469d-119">**ディレクトリ同期が有効**</span><span class="sxs-lookup"><span data-stu-id="d469d-119">**Directory sync enabled**</span></span> |<span data-ttu-id="d469d-120">True または False。</span><span class="sxs-lookup"><span data-stu-id="d469d-120">True or False.</span></span> <span data-ttu-id="d469d-121">ディレクトリ同期を有効にしたかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d469d-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="d469d-122">**最新のディレクトリ同期**</span><span class="sxs-lookup"><span data-stu-id="d469d-122">**Latest directory sync**</span></span> | <span data-ttu-id="d469d-123">ディレクトリ同期が実行された最後の時間。</span><span class="sxs-lookup"><span data-stu-id="d469d-123">Last time directory sync ran.</span></span> <span data-ttu-id="d469d-124">前回の同期が 3 日以上前の場合は、警告とトラブルシューティング ツールへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d469d-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="d469d-125">**パスワード同期が有効**</span><span class="sxs-lookup"><span data-stu-id="d469d-125">**Password sync enabled**</span></span> | <span data-ttu-id="d469d-126">True または False。</span><span class="sxs-lookup"><span data-stu-id="d469d-126">True or False.</span></span> <span data-ttu-id="d469d-127">オンプレミスと Microsoft 365 テナントの間でパスワード ハッシュ同期を行うかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d469d-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="d469d-128">**最後のパスワード同期**</span><span class="sxs-lookup"><span data-stu-id="d469d-128">**Last Password Sync**</span></span> | <span data-ttu-id="d469d-129">前回のパスワード ハッシュ同期が実行された時間。</span><span class="sxs-lookup"><span data-stu-id="d469d-129">Last time password hash sync ran.</span></span> <span data-ttu-id="d469d-130">前回の同期が 3 日以上前の場合は、警告とトラブルシューティング ツールへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d469d-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="d469d-131">**ディレクトリ同期クライアントのバージョン**</span><span class="sxs-lookup"><span data-stu-id="d469d-131">**Directory sync client version**</span></span> | <span data-ttu-id="d469d-132">Connect の新しいバージョンの Azure ADリンクが含まれる。</span><span class="sxs-lookup"><span data-stu-id="d469d-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="d469d-133">**ディレクトリ同期サービス アカウント**</span><span class="sxs-lookup"><span data-stu-id="d469d-133">**Directory sync service account**</span></span> | <span data-ttu-id="d469d-134">Microsoft 365 ディレクトリ同期サービス アカウントの名前を表示します。</span><span class="sxs-lookup"><span data-stu-id="d469d-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="d469d-135">同期の状態を監視する</span><span class="sxs-lookup"><span data-stu-id="d469d-135">Monitor synchronization health</span></span>

<span data-ttu-id="d469d-136">このセクションでは、Azure AD Connect Health エージェントを各オンプレミス AD DS ドメイン コントローラーにインストールして、Azure AD Connect によって提供されている ID インフラストラクチャと 同期サービスを監視します。</span><span class="sxs-lookup"><span data-stu-id="d469d-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="d469d-137">監視情報は Azure AD Connect Health ポータルで使用可能になります。このポータルでは、アラート、パフォーマンス監視、使用状況分析などの情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d469d-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="d469d-138">Azure AD Connect Health の使用法に関する重要な設計上の決定は、Azure AD Connect をどのように使用しているかに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="d469d-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="d469d-139">**管理認証** オプションを使用している場合は、最初に「[Azure AD Connect Health を使用した Azure AD Connect の同期の監視](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)」を参照し、Azure AD Connect Health について理解し、構成します。</span><span class="sxs-lookup"><span data-stu-id="d469d-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="d469d-140">Active Directory フェデレーション サービス (AD FS) で **フェデレーション認証** を使用してアカウントとグループの名前だけを同期している場合は、最初に「[Azure AD Connect Health を使用した AD FS の監視](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)」を参照し Azure AD Connect Health について理解し、構成します。</span><span class="sxs-lookup"><span data-stu-id="d469d-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="d469d-141">完了すると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d469d-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="d469d-142">Azure AD Connect Health エージェントがオンプレミス ID プロバイダー サーバーにインストールされている。</span><span class="sxs-lookup"><span data-stu-id="d469d-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="d469d-143">Azure AD Connect Health ポータルでは、Microsoft 365 サブスクリプションの Azure AD テナントでオンプレミス インフラストラクチャの現在の状態と同期アクティビティを表示しています。</span><span class="sxs-lookup"><span data-stu-id="d469d-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>