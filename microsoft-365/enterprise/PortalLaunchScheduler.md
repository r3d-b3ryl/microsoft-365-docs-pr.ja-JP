---
title: ポータル起動スケジューラを使用してポータルを起動する
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: この記事では、ポータルの起動スケジューラを使用してポータルを起動する方法について説明します。
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999598"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="ccc4c-103">ポータル起動スケジューラを使用してポータルを起動する</span><span class="sxs-lookup"><span data-stu-id="ccc4c-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="ccc4c-104">ポータルの起動スケジューラを使用してポータルを起動するには、最初にテナント管理者が新しいポータルのウェーブをセットアップできるかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-104">You can launch your portal using the Portal Launch Scheduler by first validating the tenant admin's ability to setup a waves for a new portal.</span></span> <span data-ttu-id="ccc4c-105">その後、管理者は、アクティブな wave 内のユーザーの存在に基づいて、要求のリダイレクトを検証できます。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-105">Then the admin can validate a redirection of requests, based on the existence of a user in the active waves.</span></span>

<span data-ttu-id="ccc4c-106">ポータルを正常に起動する方法の詳細については、「基本的な原則、プラクティス、および [正常なポータルの作成、起動](https://go.microsoft.com/fwlink/?linkid=2105838)、および保守」で詳細に説明されている手順を実行してください。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-106">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in the [Creating, launching and maintaining a healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838).</span></span> 

## <a name="app-setup"></a><span data-ttu-id="ccc4c-107">アプリのセットアップ</span><span class="sxs-lookup"><span data-stu-id="ccc4c-107">App setup</span></span>
1. <span data-ttu-id="ccc4c-108">コントロールパネルを使用してコンピューターに既存のがある場合は、アンインストール `Microsoft.Online.SharePoint.PowerShell` します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-108">Uninstall if there an existing `Microsoft.Online.SharePoint.PowerShell` from your machine through the control panel.</span></span>
2. <span data-ttu-id="ccc4c-109">PowerShell パス `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` 。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-109">On PowerShell pass `Install-Module -Name Microsoft.Online.SharePoint.PowerShell`.</span></span>

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="ccc4c-110">SharePoint Online に接続する</span><span class="sxs-lookup"><span data-stu-id="ccc4c-110">Connect to SharePoint Online</span></span>
1. <span data-ttu-id="ccc4c-111">Windows で [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) を開きます。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-111">Open the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.</span></span>
2. <span data-ttu-id="ccc4c-112">管理者としてテナントに接続します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-112">Connect to your tenant as an admin.</span></span>
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  <span data-ttu-id="ccc4c-113">プロンプトが表示されたら、パスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-113">Supply your password when prompted.</span></span>

## <a name="command-to-get-an-existing-setup"></a><span data-ttu-id="ccc4c-114">既存の設定を取得するコマンド</span><span class="sxs-lookup"><span data-stu-id="ccc4c-114">Command to get an existing setup</span></span>

<span data-ttu-id="ccc4c-115">既存のポータル起動構成を表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-115">To view existing portal launch configurations:</span></span>

1. <span data-ttu-id="ccc4c-116">合格 `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` です。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-116">Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite`.</span></span>
2. <span data-ttu-id="ccc4c-117">`-DisplayFormat Raw`生の入力形式として書式設定された wave コレクションを表示する場合は、追加のパラメーターを渡します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-117">Pass the additional parameter `-DisplayFormat Raw` if you wish to see the wave collection formatted as a raw input format.</span></span>

## <a name="commands-for-bi-directional-redirection"></a><span data-ttu-id="ccc4c-118">双方向リダイレクトのコマンド</span><span class="sxs-lookup"><span data-stu-id="ccc4c-118">Commands for bi-directional redirection</span></span>

<span data-ttu-id="ccc4c-119">古いサイトユーザーを段階的な方法で新しいサイトに移行するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-119">To migrate old site users to the new site in a staged manner:</span></span>

1. <span data-ttu-id="ccc4c-120">ポータルの発表波を作成します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-120">Create Portal launch waves.</span></span>
   - <span data-ttu-id="ccc4c-121">これは、早期リリースのテストフェーズでのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-121">This is only applicable in the early release test phase.</span></span>
   - <span data-ttu-id="ccc4c-122">変更の影響をすぐにテストするには、最初の wave `LaunchDateUtc` が現在の日付に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-122">To test the impact of the change immediately, make sure the first wave `LaunchDateUtc` is set to the current date.</span></span> <span data-ttu-id="ccc4c-123">このフラグを指定しないと、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-123">If you do not supply this flag, you get an error message.</span></span> <span data-ttu-id="ccc4c-124">このエラーは、運用環境での起動を少なくとも7日前にスケジュールする必要があるために発生します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-124">This error happens because launches in production must be scheduled at least 7 days in advance.</span></span>

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="ccc4c-125">検証を完了します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-125">Complete validation.</span></span>
  - <span data-ttu-id="ccc4c-126">リダイレクトがサービス全体にわたる構成を完了するには最大5分かかる場合があるため、続行する前にお待ちください。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-126">It can take up to 5 minutes for the redirection to complete its configuration across the service, so please wait before continuing.</span></span>
  - <span data-ttu-id="ccc4c-127">として指定されたユーザーでログインした場合は `WaveOverrideUsers` 、何も変更されません。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-127">If you login with the user specified as `WaveOverrideUsers`, then nothing changes.</span></span> <span data-ttu-id="ccc4c-128">移動先のサイトが表示されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-128">You should be staying at the site you navigated to.</span></span>
  - <span data-ttu-id="ccc4c-129">閲覧者の *SG1* の一部であるユーザーを使用してログインします。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-129">Login with a user who is part of *Viewers SG1*.</span></span>
    - <span data-ttu-id="ccc4c-130">古いサイトに移動し、新しいサイトにリダイレクトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-130">Navigate to the old site and you should be redirected to the new site.</span></span>
    - <span data-ttu-id="ccc4c-131">新しいサイトに移動して、新しいサイトにとどまる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-131">Navigate to the new site and you should be stay on the new site.</span></span>
    - <span data-ttu-id="ccc4c-132">*閲覧者 SG2* でユーザーと共にログオンし、古いサイトに移動して古いサイトを維持します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-132">Log with user in *Viewers SG2* and navigate to the old site and stay on the old site.</span></span>
    - <span data-ttu-id="ccc4c-133">新しいサイトに移動して、古いサイトにリダイレクトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-133">Navigate to the new site and you should be redirected to the old site.</span></span>

3. <span data-ttu-id="ccc4c-134">ポータルの起動を一時停止します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-134">Pause Portal launch.</span></span>
  - <span data-ttu-id="ccc4c-135">発表波を一時停止する必要がある場合は、[x] 個の日数の間、一時停止することができます。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-135">If you need to pause the launch waves, you can pause them for "x" number of days.</span></span> <span data-ttu-id="ccc4c-136">`Status`フラグを pause に設定すると、すべての今後の wave progressions が禁止されます。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-136">Setting the `Status` flag to pause prevents all upcoming wave progressions.</span></span> 
  - <span data-ttu-id="ccc4c-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="ccc4c-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="ccc4c-138">これにより、すべてのユーザーが古いサイトにリダイレクトされることを検証します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-138">This validates that all users are redirected to the old site.</span></span>

4. <span data-ttu-id="ccc4c-139">ポータルの起動の進行状況を再起動します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-139">Restart the portal launch progression.</span></span> 
  - <span data-ttu-id="ccc4c-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="ccc4c-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="ccc4c-141">リダイレクトが復元されるようになったことを検証します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-141">Validate that the redirection is now restored.</span></span>

5. <span data-ttu-id="ccc4c-142">ポータル起動セットアップを削除します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-142">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="ccc4c-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="ccc4c-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="ccc4c-144">すべてのユーザーに対してリダイレクトが発生しないことを検証します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-144">Validate that no redirection happens for all users.</span></span>

## <a name="commands-for-redirection-to-temporary-page"></a><span data-ttu-id="ccc4c-145">一時ページにリダイレクトするためのコマンド</span><span class="sxs-lookup"><span data-stu-id="ccc4c-145">Commands for redirection to temporary page</span></span>

<span data-ttu-id="ccc4c-146">以前のサイトがなく、新しいポータルページのランディングからのユーザーではないユーザーを省略する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-146">Follow these steps if you have no previous site and you want to omit users not in the wave from landing on the new portal page.</span></span>

<span data-ttu-id="ccc4c-147">任意のサイトに一時ページを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-147">To create a temporary page in any of the sites:</span></span>

1. <span data-ttu-id="ccc4c-148">ポータルの起動波形を作成します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-148">Create a Portal launch Wave.</span></span>
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="ccc4c-149">検証を完了します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-149">Complete validation.</span></span>

  - <span data-ttu-id="ccc4c-150">処理が完了するまでに最大5分かかる場合があるため、5分間待機してから続行します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-150">Wait five minutes before continuing, as the action can take up to five minutes to complete.</span></span>
  - <span data-ttu-id="ccc4c-151">*ビューアー* の一部であるユーザーとログを記録します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-151">Log with the user who is part of *Viewers SG1* and:</span></span>
     - <span data-ttu-id="ccc4c-152">新しいサイトに移動して、新しいサイトにとどまる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-152">Navigate to the new site, and you should be stay on the new site.</span></span>
     - <span data-ttu-id="ccc4c-153">Temp ページに移動すると、temp ページが表示されたままになります。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-153">Navigate to the temp page, and you should be stay on the temp page.</span></span>
  - <span data-ttu-id="ccc4c-154">*ビューアーの SG2* の一部であるユーザーとログを記録します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-154">Log with the user who is part of *Viewers SG2* and:</span></span>
     - <span data-ttu-id="ccc4c-155">新しいサイトに移動し、temp ページにリダイレクトされる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-155">Navigate to the new site, and you should be redirected to the temp page.</span></span>
     - <span data-ttu-id="ccc4c-156">Temp ページに移動すると、temp ページが表示されたままになります。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-156">Navigate to the temp page, and you should stay on the temp page.</span></span>

3. <span data-ttu-id="ccc4c-157">ポータル起動セットアップを削除します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-157">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="ccc4c-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="ccc4c-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="ccc4c-159">すべてのユーザーに対してリダイレクトが発生しないことを検証します。</span><span class="sxs-lookup"><span data-stu-id="ccc4c-159">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="ccc4c-160">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ccc4c-160">Learn more</span></span>
[<span data-ttu-id="ccc4c-161">SharePoint Online でポータルの起動ロールアウトプランを計画する</span><span class="sxs-lookup"><span data-stu-id="ccc4c-161">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)