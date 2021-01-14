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
description: この記事では、ポータル起動スケジューラを使用してポータルを起動する方法について説明します。
ms.openlocfilehash: 66912f5730c580bd75282a64124fefcdf262d738
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864878"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="0add5-103">ポータル起動スケジューラを使用してポータルを起動する</span><span class="sxs-lookup"><span data-stu-id="0add5-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="0add5-104">ポータルは、イントラネット上の SharePoint サイトであり、サイト上のコンテンツを使用する多数のサイト ビューアーがいます。</span><span class="sxs-lookup"><span data-stu-id="0add5-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="0add5-105">ユーザーが新しい SharePoint Online ポータルにアクセスするスムーズで高パフォーマンスのエクスペリエンスを得る上で重要な部分は、ポータルをウェーブで起動する重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="0add5-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="0add5-106">「SharePoint Online でのポータルの立ち上げロールアウト計画の計画」で詳しく説明されている、ポータルを展開するための重要な方法は、ウェーブで起動 [する方法です](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="0add5-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> <span data-ttu-id="0add5-107">ポータル起動スケジューラは、新しいポータルのリダイレクトを管理することで、ウェーブ/段階的なロールアウトアプローチに従うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0add5-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="0add5-108">各ウェーブの間に、ユーザーフィードバックを収集し、展開の各ウェーブ中のパフォーマンスを監視できます。</span><span class="sxs-lookup"><span data-stu-id="0add5-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="0add5-109">これには、ポータルの導入が遅いという利点があります。次のウェーブに進む前に問題を一時停止して解決するオプションを提供し、最終的にはユーザーに良いエクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="0add5-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="0add5-110">リダイレクトには、次の 2 種類があります。</span><span class="sxs-lookup"><span data-stu-id="0add5-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="0add5-111">双方向: 新しいモダン SharePoint Online ポータルを起動して、既存の SharePoint クラシック ポータルまたはモダン ポータルを置き換える</span><span class="sxs-lookup"><span data-stu-id="0add5-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="0add5-112">一時ページリダイレクト: 既存の SharePoint ポータルがない新しい最新の SharePoint Online ポータルを起動する</span><span class="sxs-lookup"><span data-stu-id="0add5-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="0add5-113">ポータル起動スケジューラは、最新の SharePoint Online ポータル (コミュニケーション サイト) を起動する場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="0add5-113">The portal launch scheduler is only available to launch modern SharePoint Online portals (i.e. communication sites).</span></span> <span data-ttu-id="0add5-114">起動は少なくとも 7 日前にスケジュールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0add5-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="0add5-115">必要なウェーブの数は、予想されるユーザー数によって決まります。</span><span class="sxs-lookup"><span data-stu-id="0add5-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="0add5-116">ポータルの起動をスケジュールする前に [、SharePoint](https://aka.ms/perftool) 用ページ診断ツールを実行して、ポータルのホーム ページが正常な状態を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0add5-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="0add5-117">ポータルの起動の最後に、サイトへのアクセス許可を持つすべてのユーザーが新しいサイトにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0add5-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="0add5-118">成功したポータルの起動の詳細については、「正常なポータルの作成、起動、保守」で説明されている基本原則、プラクティス、推奨事項に [従ってください](https://docs.microsoft.com/sharepoint/portal-health)。</span><span class="sxs-lookup"><span data-stu-id="0add5-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](https://docs.microsoft.com/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="0add5-119">この機能は、Office 365 Germany、21Vianet が運用している Office 365 (中国)、または Microsoft 365 US Government プランでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="0add5-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="0add5-120">アプリのセットアップと SharePoint Online への接続</span><span class="sxs-lookup"><span data-stu-id="0add5-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="0add5-121">[最新の SharePoint Online 管理シェルをダウンロードします](https://go.microsoft.com/fwlink/p/?LinkId=255251)。</span><span class="sxs-lookup"><span data-stu-id="0add5-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="0add5-p104">SharePoint Online 管理シェルの以前のバージョンがインストールされている場合は、[プログラムの追加と削除] に移動して、"SharePoint Online 管理シェル" をアンインストールします。 </span><span class="sxs-lookup"><span data-stu-id="0add5-p104">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell." </span></span><br><span data-ttu-id="0add5-123">ダウンロード センター ページで言語を選択して、[ダウンロード] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0add5-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="0add5-124">x64 .msi ファイルまたは x86 .msi ファイルのどちらをダウンロードするかを選択するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="0add5-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="0add5-125">Windows の 64 ビット版を実行している場合は x64 ファイルを、32 ビット版を実行している場合は x86 ファイルをそれぞれダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="0add5-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="0add5-126">不明な場合には、「[実行している Windows オペレーティング システムの確認方法](https://support.microsoft.com/help/13443/windows-which-operating-system)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0add5-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="0add5-127">ファイルをダウンロードしたら、それを実行して、セットアップ ウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0add5-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="0add5-128">Microsoft 365 の[グローバル管理者または SharePoint 管理者](/sharepoint/sharepoint-admin-role)として SharePoint Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="0add5-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="0add5-129">方法の詳細については、「[SharePoint Online 管理シェルの使用を開始する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0add5-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="0add5-130">既存のポータル起動セットアップを表示する</span><span class="sxs-lookup"><span data-stu-id="0add5-130">View any existing portal launch setups</span></span>

<span data-ttu-id="0add5-131">既存のポータル起動構成が表示される場合は、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="0add5-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="0add5-132">サイトでポータルの起動をスケジュールする</span><span class="sxs-lookup"><span data-stu-id="0add5-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="0add5-133">必要なウェーブの数は、予想される起動サイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0add5-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="0add5-134">10k 未満のユーザー: 1 ウェーブ</span><span class="sxs-lookup"><span data-stu-id="0add5-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="0add5-135">10k から 30k ユーザー: 3 ウェーブ</span><span class="sxs-lookup"><span data-stu-id="0add5-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="0add5-136">30k+ ~ 100,000 ユーザー: 5 ウェーブ</span><span class="sxs-lookup"><span data-stu-id="0add5-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="0add5-137">100,000 人を超えるユーザー: 5 ウェーブ、Microsoft アカウント チームに問い合わせ</span><span class="sxs-lookup"><span data-stu-id="0add5-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="0add5-138">双方向リダイレクトの手順</span><span class="sxs-lookup"><span data-stu-id="0add5-138">Steps for bidirectional redirection</span></span>

<span data-ttu-id="0add5-139">双方向リダイレクトでは、新しい最新の SharePoint Online ポータルを起動して、既存の SharePoint クラシック ポータルまたはモダン ポータルを置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="0add5-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="0add5-140">アクティブなウェーブのユーザーは、古いサイトに移動するか新しいサイトに移動するかに関係なく、新しいサイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="0add5-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="0add5-141">起動されていないウェーブで新しいサイトにアクセスしようとするユーザーは、Wave が起動されるまで古いサイトにリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="0add5-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="0add5-142">古いサイトの既定のホーム ページと新しいサイトの既定のホーム ページとの間のリダイレクトのみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0add5-142">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="0add5-143">リダイレクトせずに古いサイトと新しいサイトにアクセスする必要がある管理者または所有者が必要な場合は、そのサイトがパラメーターを使用して一覧に表示されている必要 `WaveOverrideUsers` があります。</span><span class="sxs-lookup"><span data-stu-id="0add5-143">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="0add5-144">既存の SharePoint サイトから新しい SharePoint サイトにユーザーを段階的に移行するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="0add5-144">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="0add5-145">次のコマンドを実行して、ポータル起動ウェーブを指定します。</span><span class="sxs-lookup"><span data-stu-id="0add5-145">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="0add5-146">例:</span><span class="sxs-lookup"><span data-stu-id="0add5-146">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="0add5-147">完全な検証。</span><span class="sxs-lookup"><span data-stu-id="0add5-147">Complete validation.</span></span> <span data-ttu-id="0add5-148">リダイレクトがサービス全体で構成を完了するには、5 ~ 10 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0add5-148">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="0add5-149">一時ページへのリダイレクトの手順</span><span class="sxs-lookup"><span data-stu-id="0add5-149">Steps for redirection to temporary page</span></span>

<span data-ttu-id="0add5-150">既存の SharePoint ポータルが存在しない場合は、一時的なページ リダイレクトを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0add5-150">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="0add5-151">ユーザーは、新しい最新の SharePoint Online ポータルに、段階を通して指示されます。</span><span class="sxs-lookup"><span data-stu-id="0add5-151">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="0add5-152">起動されていないウェーブ内のユーザーは、一時ページ (任意の URL) にリダイレクトされます。</span><span class="sxs-lookup"><span data-stu-id="0add5-152">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="0add5-153">次のコマンドを実行して、ポータル起動ウェーブを指定します。</span><span class="sxs-lookup"><span data-stu-id="0add5-153">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="0add5-154">例:</span><span class="sxs-lookup"><span data-stu-id="0add5-154">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="0add5-155">完全な検証。</span><span class="sxs-lookup"><span data-stu-id="0add5-155">Complete validation.</span></span> <span data-ttu-id="0add5-156">リダイレクトがサービス全体で構成を完了するには、5 ~ 10 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="0add5-156">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="0add5-157">サイトでポータルの起動を一時停止または再開する</span><span class="sxs-lookup"><span data-stu-id="0add5-157">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="0add5-158">進行中のポータルの起動を一時停止し、今後のウェーブの進行を一時的に防ぐには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0add5-158">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="0add5-159">すべてのユーザーが古いサイトにリダイレクトされるのを検証します。</span><span class="sxs-lookup"><span data-stu-id="0add5-159">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="0add5-160">一時停止したポータルの起動を再開するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0add5-160">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="0add5-161">リダイレクトが復元された状態を検証します。</span><span class="sxs-lookup"><span data-stu-id="0add5-161">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="0add5-162">サイトでポータルの起動を削除する</span><span class="sxs-lookup"><span data-stu-id="0add5-162">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="0add5-163">次のコマンドを実行して、サイトのポータル起動のスケジュールまたは進行中を削除します。</span><span class="sxs-lookup"><span data-stu-id="0add5-163">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="0add5-164">すべてのユーザーに対してリダイレクトが実行されなにかを検証します。</span><span class="sxs-lookup"><span data-stu-id="0add5-164">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="0add5-165">詳細情報</span><span class="sxs-lookup"><span data-stu-id="0add5-165">Learn more</span></span>
[<span data-ttu-id="0add5-166">SharePoint Online でポータルの起動のロールアウト計画を計画する</span><span class="sxs-lookup"><span data-stu-id="0add5-166">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
