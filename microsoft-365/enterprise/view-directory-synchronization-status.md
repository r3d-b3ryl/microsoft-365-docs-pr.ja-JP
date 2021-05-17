---
title: '[ディレクトリ同期の状態を表示する] Microsoft 365'
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
description: この記事では、ディレクトリ同期の状態を確認する方法について、Office 365。
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924662"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="aed60-103">[ディレクトリ同期の状態を表示する] Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aed60-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="aed60-104">オンプレミスの Active Directory ドメイン サービス (AD DS) を Azure Active Directory (Azure AD) と統合した場合は、オンプレミス環境と Microsoft 365 を同期することで、同期の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="aed60-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="aed60-105">ディレクトリ同期の状態を表示する</span><span class="sxs-lookup"><span data-stu-id="aed60-105">View directory synchronization status</span></span>

- <span data-ttu-id="aed60-106">管理センターにサインイン [Microsoft 365ホーム](https://admin.microsoft.com)ページで **[DirSync Status]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="aed60-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="aed60-107">または、[ユーザー] [アクティブな **ユーザー]** に移動し、[アクティブなユーザー] ページで [その他のディレクトリ \> 同期] \> **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="aed60-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="aed60-108">[ディレクトリ同期 **] ウィンドウで\*\*\*\*、[DirSync 管理に移動] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="aed60-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="aed60-109">[ディレクトリ同期の管理] ページの情報</span><span class="sxs-lookup"><span data-stu-id="aed60-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="aed60-110">次の表に、ページで情報を取得できる機能の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="aed60-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="aed60-111">ディレクトリ同期に問題がある場合は、このページにもエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aed60-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="aed60-112">発生する可能性のあるさまざまなエラーの詳細については、「ディレクトリ同期エラーを特定する」を参照[Microsoft 365。](identify-directory-synchronization-errors.md)</span><span class="sxs-lookup"><span data-stu-id="aed60-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="aed60-113">アイテム</span><span class="sxs-lookup"><span data-stu-id="aed60-113">Item</span></span>|<span data-ttu-id="aed60-114">目的</span><span class="sxs-lookup"><span data-stu-id="aed60-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="aed60-115">**ドメインが検証済み**</span><span class="sxs-lookup"><span data-stu-id="aed60-115">**Domains verified**</span></span> | <span data-ttu-id="aed60-116">ユーザーが所有しているMicrosoft 365しているドメインの数。</span><span class="sxs-lookup"><span data-stu-id="aed60-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="aed60-117">**ドメインが検証されていない**</span><span class="sxs-lookup"><span data-stu-id="aed60-117">**Domains not verified**</span></span> | <span data-ttu-id="aed60-118">追加したが、検証されていないドメイン。</span><span class="sxs-lookup"><span data-stu-id="aed60-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="aed60-119">**ディレクトリ同期が有効**</span><span class="sxs-lookup"><span data-stu-id="aed60-119">**Directory sync enabled**</span></span> |<span data-ttu-id="aed60-120">True または False。</span><span class="sxs-lookup"><span data-stu-id="aed60-120">True or False.</span></span> <span data-ttu-id="aed60-121">ディレクトリ同期を有効にしたかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="aed60-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="aed60-122">**最新のディレクトリ同期**</span><span class="sxs-lookup"><span data-stu-id="aed60-122">**Latest directory sync**</span></span> | <span data-ttu-id="aed60-123">ディレクトリ同期が実行された最後の時間。</span><span class="sxs-lookup"><span data-stu-id="aed60-123">Last time directory sync ran.</span></span> <span data-ttu-id="aed60-124">前回の同期が 3 日以上前の場合は、警告とトラブルシューティング ツールへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aed60-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="aed60-125">**パスワード同期が有効**</span><span class="sxs-lookup"><span data-stu-id="aed60-125">**Password sync enabled**</span></span> | <span data-ttu-id="aed60-126">True または False。</span><span class="sxs-lookup"><span data-stu-id="aed60-126">True or False.</span></span> <span data-ttu-id="aed60-127">オンプレミステナントとテナント間でパスワード ハッシュ同期を行うかどうかをMicrosoft 365します。</span><span class="sxs-lookup"><span data-stu-id="aed60-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="aed60-128">**最後のパスワード同期**</span><span class="sxs-lookup"><span data-stu-id="aed60-128">**Last Password Sync**</span></span> | <span data-ttu-id="aed60-129">前回のパスワード ハッシュ同期が実行された時間。</span><span class="sxs-lookup"><span data-stu-id="aed60-129">Last time password hash sync ran.</span></span> <span data-ttu-id="aed60-130">前回の同期が 3 日以上前の場合は、警告とトラブルシューティング ツールへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="aed60-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="aed60-131">**ディレクトリ同期クライアントのバージョン**</span><span class="sxs-lookup"><span data-stu-id="aed60-131">**Directory sync client version**</span></span> | <span data-ttu-id="aed60-132">新しいバージョンの Azure アプリケーションがリリースされている場合はAD Connectリンクが含まれる。</span><span class="sxs-lookup"><span data-stu-id="aed60-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="aed60-133">**ディレクトリ同期サービス アカウント**</span><span class="sxs-lookup"><span data-stu-id="aed60-133">**Directory sync service account**</span></span> | <span data-ttu-id="aed60-134">ディレクトリ同期サービス アカウントMicrosoft 365を表示します。</span><span class="sxs-lookup"><span data-stu-id="aed60-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="aed60-135">同期の状態を監視する</span><span class="sxs-lookup"><span data-stu-id="aed60-135">Monitor synchronization health</span></span>

<span data-ttu-id="aed60-136">このセクションでは、Azure AD Connect Health エージェントを各オンプレミス AD DS ドメイン コントローラーにインストールして、Azure AD Connect によって提供されている ID インフラストラクチャと 同期サービスを監視します。</span><span class="sxs-lookup"><span data-stu-id="aed60-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="aed60-137">監視情報は Azure AD Connect Health ポータルで使用可能になります。このポータルでは、アラート、パフォーマンス監視、使用状況分析などの情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="aed60-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="aed60-138">Azure AD Connect Health の使用法に関する重要な設計上の決定は、Azure AD Connect をどのように使用しているかに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="aed60-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="aed60-139">**管理認証** オプションを使用している場合は、最初に「[Azure AD Connect Health を使用した Azure AD Connect の同期の監視](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)」を参照し、Azure AD Connect Health について理解し、構成します。</span><span class="sxs-lookup"><span data-stu-id="aed60-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="aed60-140">Active Directory フェデレーション サービス (AD FS) で **フェデレーション認証** を使用してアカウントとグループの名前だけを同期している場合は、最初に「[Azure AD Connect Health を使用した AD FS の監視](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)」を参照し Azure AD Connect Health について理解し、構成します。</span><span class="sxs-lookup"><span data-stu-id="aed60-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="aed60-141">完了すると、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="aed60-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="aed60-142">Azure AD Connect Health エージェントがオンプレミス ID プロバイダー サーバーにインストールされている。</span><span class="sxs-lookup"><span data-stu-id="aed60-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="aed60-143">Azure AD Connect Health ポータルでは、Microsoft 365 サブスクリプションの Azure AD テナントでオンプレミス インフラストラクチャの現在の状態と同期アクティビティを表示しています。</span><span class="sxs-lookup"><span data-stu-id="aed60-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>