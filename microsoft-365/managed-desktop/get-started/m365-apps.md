---
title: Microsoft 365 Apps for enterprise
description: Microsoft 365 Apps の展開方法、更新方法、設定の管理方法
keywords: 変更履歴
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 98995084fb7de9ecb434b70b5d38793a20675f19
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840351"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="be10d-104">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="be10d-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="be10d-105">初期展開</span><span class="sxs-lookup"><span data-stu-id="be10d-105">Initial deployment</span></span>

<span data-ttu-id="be10d-106">Microsoft マネージド デスクトップを使用すると、Microsoft 365 Apps for enterprise (64 ビット) がすべてのプログラム デバイスにイメージの一部として [インストールされます](../service-description/device-list.md)。</span><span class="sxs-lookup"><span data-stu-id="be10d-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="be10d-107">次のアプリケーションはすべて、配信時にデバイスに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be10d-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="be10d-108">Word</span><span class="sxs-lookup"><span data-stu-id="be10d-108">Word</span></span>
- <span data-ttu-id="be10d-109">Excel</span><span class="sxs-lookup"><span data-stu-id="be10d-109">Excel</span></span>
- <span data-ttu-id="be10d-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="be10d-110">PowerPoint</span></span>
- <span data-ttu-id="be10d-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="be10d-111">Outlook</span></span>
- <span data-ttu-id="be10d-112">発行者</span><span class="sxs-lookup"><span data-stu-id="be10d-112">Publisher</span></span>
- <span data-ttu-id="be10d-113">Access</span><span class="sxs-lookup"><span data-stu-id="be10d-113">Access</span></span>
- <span data-ttu-id="be10d-114">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="be10d-114">Skype for Business</span></span>
- <span data-ttu-id="be10d-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="be10d-115">OneNote</span></span>

<span data-ttu-id="be10d-116">この方法では、ネットワークへの影響を最小限に抑え、ユーザーがデバイスを受け取り次第、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="be10d-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="be10d-117">その後、管理対象デバイスにさらに多くのポリシーを展開して、使用するアプリケーションをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="be10d-117">We then deploy more policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="be10d-118">Microsoft Teams は、Microsoft 365 Apps for enterprise とは別に展開され、基本イメージには含まれません。</span><span class="sxs-lookup"><span data-stu-id="be10d-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="be10d-119">ユーザーが利用可能な展開</span><span class="sxs-lookup"><span data-stu-id="be10d-119">Available deployment to users</span></span>

<span data-ttu-id="be10d-120">何らかの理由でユーザーのデバイスに Microsoft 365 アプリがインストールされていない場合は、パッケージを使ってデバイスを予期した状態に戻します。</span><span class="sxs-lookup"><span data-stu-id="be10d-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="be10d-121">モダン **Workplace-Office-Office365_Install** グループにユーザーを追加すると、ポータル サイトでアプリが利用できます。</span><span class="sxs-lookup"><span data-stu-id="be10d-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="be10d-122">Microsoft 365 Apps for enterprise (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="be10d-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="be10d-123">Microsoft マネージド デスクトップでは、M365 Apps for enterprise の 32 ビット バージョンの展開はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="be10d-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="be10d-124">Microsoft 365 アプリの更新プログラム</span><span class="sxs-lookup"><span data-stu-id="be10d-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="be10d-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span><span class="sxs-lookup"><span data-stu-id="be10d-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="be10d-126">この方法では、毎月新しい Office 機能をユーザーに提供しますが、予測可能なリリース スケジュールで毎月 1 回の更新プログラムを受信します。</span><span class="sxs-lookup"><span data-stu-id="be10d-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="be10d-127">更新プログラムは、毎月第 2 火曜日にリリースされます。これらの更新プログラムには、機能更新プログラム、セキュリティ更新プログラム、品質更新プログラムが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="be10d-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="be10d-128">これらの更新は自動的に行われるので、その特定のチャネルの Office CDN から直接取得されます。</span><span class="sxs-lookup"><span data-stu-id="be10d-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="be10d-129">Microsoft マネージド デスクトップは、各リリースをずらして、環境内の潜在的な問題を特定します。</span><span class="sxs-lookup"><span data-stu-id="be10d-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="be10d-130">Microsoft 365 アプリ製品グループからのリリースの 28 日後にロールアウトが完了します。</span><span class="sxs-lookup"><span data-stu-id="be10d-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="be10d-131">Microsoft マネージド デスクトップでは、更新プログラムのリリースをさまざまなグループにスケジュールして、次のように検証とテストに時間を割きます。</span><span class="sxs-lookup"><span data-stu-id="be10d-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="be10d-132">テスト: ゼロ日</span><span class="sxs-lookup"><span data-stu-id="be10d-132">Test: zero days</span></span>
- <span data-ttu-id="be10d-133">最初: ゼロ日</span><span class="sxs-lookup"><span data-stu-id="be10d-133">First: zero days</span></span>
- <span data-ttu-id="be10d-134">高速: 7 日</span><span class="sxs-lookup"><span data-stu-id="be10d-134">Fast: 7 days</span></span>
- <span data-ttu-id="be10d-135">広範: 21 日</span><span class="sxs-lookup"><span data-stu-id="be10d-135">Broad: 21 days</span></span>

<span data-ttu-id="be10d-136">Microsoft マネージド デスクトップは、デバイスの 7 日間 [の更新期限](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) を設定します。</span><span class="sxs-lookup"><span data-stu-id="be10d-136">Microsoft Managed Desktop sets a seven-day [update deadline](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="be10d-137">更新プログラムが利用可能な場合は、7 日以内にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="be10d-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="be10d-138">ユーザーには[](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)、期限の 12 時間前にシステム トレイにあるアプリケーションの複数の場所で更新が必要なという通知が表示され、期限の 15 分前に警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="be10d-138">Users are [notified](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="be10d-139">更新を完了するには、すべての Microsoft 365 アプリを終了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be10d-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="be10d-140">更新プログラムの一時停止またはロールバック</span><span class="sxs-lookup"><span data-stu-id="be10d-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="be10d-141">何らかの理由で Microsoft 365 アプリの更新プログラムを一時停止またはロールバック[](../working-with-managed-desktop/admin-support.md)する必要がある場合は、Microsoft マネージド デスクトップ ポータルから管理者サポート要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="be10d-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="be10d-142">リリース中、Microsoft マネージド デスクトップは、すべての Microsoft 365 アプリのエラー率を監視します。</span><span class="sxs-lookup"><span data-stu-id="be10d-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="be10d-143">新しいリリースと先行リリースの品質に大きな違いがある場合は、Microsoft マネージド デスクトップ管理ポータルを通じてお客様にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="be10d-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="be10d-144">重大度に応じて、リリースを一時停止するか、問題を軽減するための処置を行ったか通知されます。</span><span class="sxs-lookup"><span data-stu-id="be10d-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="be10d-145">配信の最適化</span><span class="sxs-lookup"><span data-stu-id="be10d-145">Delivery optimization</span></span>

<span data-ttu-id="be10d-146">配信の最適化は、Windows 10 で利用できるピアツーピアの配布テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="be10d-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="be10d-147">これにより、デバイスは、インターネットを通して Microsoft からダウンロードした更新プログラムなどのコンテンツを共有できます。</span><span class="sxs-lookup"><span data-stu-id="be10d-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="be10d-148">デバイスは、Microsoft から更新プログラムを完全にダウンロードする代わりに、ローカル ネットワーク上の別のデバイスから更新プログラムの一部を取得することができるため、ネットワーク帯域幅の削減に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="be10d-148">Using it can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="be10d-149">[配信の](https://docs.microsoft.com/deployoffice/delivery-optimization) 最適化は、Windows 10 Enterprise または Windows 10 Education エディションを実行しているデバイスで既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="be10d-149">[Delivery Optimization](https://docs.microsoft.com/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="be10d-150">Microsoft マネージド デスクトップで管理される設定</span><span class="sxs-lookup"><span data-stu-id="be10d-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="be10d-151">Microsoft は、サービスの一部としていくつかの設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="be10d-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="be10d-152">Microsoft マネージド デスクトップは、Office セキュリティ基本計画を管理しますが、「管理する設定」セクションのガイダンスに従って自分で[設定できます。](#settings-you-manage)</span><span class="sxs-lookup"><span data-stu-id="be10d-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="be10d-153">設定を更新する</span><span class="sxs-lookup"><span data-stu-id="be10d-153">Update settings</span></span>

<span data-ttu-id="be10d-154">Microsoft マネージド デスクトップでは、 [管理対象デバイスのすべての](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) 更新設定が維持されます。これらの設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be10d-154">Microsoft Managed Desktop maintains all [update settings](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="be10d-155">更新が自動的に発生するように設定する</span><span class="sxs-lookup"><span data-stu-id="be10d-155">Set updates to occur automatically</span></span>

<span data-ttu-id="be10d-156">**既定値 :** 有効</span><span class="sxs-lookup"><span data-stu-id="be10d-156">**Default value**: Enabled</span></span>

<span data-ttu-id="be10d-157">このポリシーは、すべてのデバイスOfficeクラウドから最新の状態に保つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="be10d-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="be10d-158">更新プログラムを適用する必要がある期限を設定する</span><span class="sxs-lookup"><span data-stu-id="be10d-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="be10d-159">**既定値 :** 7 日</span><span class="sxs-lookup"><span data-stu-id="be10d-159">**Default value**: 7 days</span></span>

<span data-ttu-id="be10d-160">**UpdateDeadline ポリシーは**、更新プログラムがデバイスに適用される前にユーザーが持っている猶予期間を構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="be10d-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="be10d-161">この期限ポリシーは、ユーザー [に通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) をトリガーして、デバイスに必要な変更をユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="be10d-161">This deadline policy also triggers [notifications](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="be10d-162">デバイスの更新プログラムを一期間延期する</span><span class="sxs-lookup"><span data-stu-id="be10d-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="be10d-163">このポリシーは、更新プログラム管理デバイス グループごとに異なる方法で構成され、Microsoft マネージド デスクトップが更新ターゲットを満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="be10d-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="be10d-164">テスト: ゼロ日</span><span class="sxs-lookup"><span data-stu-id="be10d-164">Test: zero days</span></span>
- <span data-ttu-id="be10d-165">最初: ゼロ日</span><span class="sxs-lookup"><span data-stu-id="be10d-165">First: zero days</span></span>
- <span data-ttu-id="be10d-166">ファスト 7 日間</span><span class="sxs-lookup"><span data-stu-id="be10d-166">Fast 7 days</span></span>
- <span data-ttu-id="be10d-167">広範: 21 日</span><span class="sxs-lookup"><span data-stu-id="be10d-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="be10d-168">通知設定を更新する</span><span class="sxs-lookup"><span data-stu-id="be10d-168">Update notifications settings</span></span>

<span data-ttu-id="be10d-169">**既定値 :** False</span><span class="sxs-lookup"><span data-stu-id="be10d-169">**Default value**: False</span></span>

<span data-ttu-id="be10d-170">Microsoft マネージド デスクトップ デバイスでは、"更新通知を非表示にする" 設定が **False** に設定され、[](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)更新が必要なときにユーザーに通知することで、ユーザーに最適な更新エクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="be10d-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="be10d-171">更新プログラムを検索する場所を指定する</span><span class="sxs-lookup"><span data-stu-id="be10d-171">Specify a location to look for updates</span></span>

<span data-ttu-id="be10d-172">**既定値**: 月次エンタープライズ チャネル</span><span class="sxs-lookup"><span data-stu-id="be10d-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="be10d-173">**UpdatePath** ポリシーと **UpdateChannel** ポリシーの組み合わせは、更新スケジュールを達成するために必要に応じて使用されます。</span><span class="sxs-lookup"><span data-stu-id="be10d-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="be10d-174">これらのポリシーは、すべての Office デバイスが月次エンタープライズ チャネルの更新プログラムを CDN から直接受信するための設定です。</span><span class="sxs-lookup"><span data-stu-id="be10d-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="be10d-175">Microsoft 365 アプリのターゲット バージョンを指定する</span><span class="sxs-lookup"><span data-stu-id="be10d-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="be10d-176">ターゲット バージョン ポリシーは、特定のバージョンのアプリをロールバックまたはピン留めするために、Microsoft マネージド デスクトップで使用される場合Office。</span><span class="sxs-lookup"><span data-stu-id="be10d-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="be10d-177">自動更新を有効または無効にするオプションOffice非表示にする</span><span class="sxs-lookup"><span data-stu-id="be10d-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="be10d-178">**既定値 :** 有効</span><span class="sxs-lookup"><span data-stu-id="be10d-178">**Default value**: Enabled</span></span>

<span data-ttu-id="be10d-179">この設定は、Microsoft 365 アプリケーションの更新ターゲットを Microsoft マネージド デスクトップが満たすために必要です。</span><span class="sxs-lookup"><span data-stu-id="be10d-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="be10d-180">最初の実行の設定</span><span class="sxs-lookup"><span data-stu-id="be10d-180">First run settings</span></span> 

<span data-ttu-id="be10d-181">初回実行時の動作に影響を与える設定Officeがあります。</span><span class="sxs-lookup"><span data-stu-id="be10d-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="be10d-182">エンド ユーザーの代わりにライセンス条項に同意する</span><span class="sxs-lookup"><span data-stu-id="be10d-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="be10d-183">**既定値 :** 無効</span><span class="sxs-lookup"><span data-stu-id="be10d-183">**Default value**: Disabled</span></span>

<span data-ttu-id="be10d-184">ユーザーが初めて Microsoft 365 アプリを開くと、ライセンス条項に同意するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be10d-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="be10d-185">ユーザーの代わりにライセンス条項に同意する場合は、Microsoft マネージド デスクトップ 操作チームにサービス要求を送信し、この設定を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="be10d-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="be10d-186">Outlook モバイルのチェック ボックスを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="be10d-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="be10d-187">**既定値 :** 無効</span><span class="sxs-lookup"><span data-stu-id="be10d-187">**Default value**: Disabled</span></span>

<span data-ttu-id="be10d-188">ユーザーが初めて Outlook を開くと、Outlook Mobile のインストールを求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="be10d-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="be10d-189">ユーザーにこのチェック ボックスを表示したくない場合は、Microsoft マネージド デスクトップ操作チームにサービス要求を送信し、デバイスでこの設定を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="be10d-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="be10d-190">その他の設定</span><span class="sxs-lookup"><span data-stu-id="be10d-190">Other settings</span></span>

<span data-ttu-id="be10d-191">Microsoft マネージド デスクトップでは、必要に応じてユーザーに代わって構成できる他の Microsoft 365 アプリ設定があります。</span><span class="sxs-lookup"><span data-stu-id="be10d-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="be10d-192">個人用 OneDrive を無効にする</span><span class="sxs-lookup"><span data-stu-id="be10d-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="be10d-193">**既定値 :** 無効</span><span class="sxs-lookup"><span data-stu-id="be10d-193">**Default value**: Disabled</span></span>

<span data-ttu-id="be10d-194">一部の組織では、ユーザーがデバイス上の企業ファイルと個人用ファイルの両方にアクセスできると懸念しています。</span><span class="sxs-lookup"><span data-stu-id="be10d-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="be10d-195">Microsoft マネージド デスクトップ操作チームにサービス要求を送信して、この設定を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="be10d-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="be10d-196">管理する設定</span><span class="sxs-lookup"><span data-stu-id="be10d-196">Settings you manage</span></span>

<span data-ttu-id="be10d-197">Microsoft マネージド デスクトップがサービスの一部としてまだ設定していないポリシーは他にも多数存在します。</span><span class="sxs-lookup"><span data-stu-id="be10d-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="be10d-198">これらのポリシーは、Microsoft Intune を使用して構成できます。この Intune では、Office [クラウド ポリシー サービスを使用](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) します。</span><span class="sxs-lookup"><span data-stu-id="be10d-198">You can configure these policies by using Microsoft Intune, which uses the [Office Cloud Policy](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="be10d-199">これらのポリシーを設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="be10d-199">To set these policies, follow these steps:</span></span>

1.  <span data-ttu-id="be10d-200">Microsoft Endpoint Manager 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="be10d-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2.  <span data-ttu-id="be10d-201">[ **作成] >アプリの [アプリOfficeポリシー>選択する**</span><span class="sxs-lookup"><span data-stu-id="be10d-201">Select **Apps > Policies for Office apps > Create**</span></span>
3.  <span data-ttu-id="be10d-202">[ポリシー **構成の作成]** ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="be10d-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="be10d-203">名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="be10d-203">Enter a name.</span></span>
    - <span data-ttu-id="be10d-204">説明を入力します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="be10d-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="be10d-205">割 **り** 当てで、このポリシーを Microsoft 365 Apps for enterprise のすべてのユーザーに適用するか、Office for the web を使用してドキュメントに匿名でアクセスするユーザーに適用するか選択します。</span><span class="sxs-lookup"><span data-stu-id="be10d-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="be10d-206">ポリシー構成に割り当てられている AAD ベースのセキュリティ グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="be10d-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="be10d-207">各ポリシー構成は 1 つのグループにのみ割り当て、各グループには 1 つのポリシー構成のみを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="be10d-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="be10d-208">ポリシー構成に含めるポリシー設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="be10d-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="be10d-209">ポリシー設定名を検索して、構成するポリシー設定を検索できます。</span><span class="sxs-lookup"><span data-stu-id="be10d-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="be10d-210">また、ポリシーが推奨されるセキュリティベースラインかどうか、およびポリシーが構成されているかどうかを基に、アプリケーションをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="be10d-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="be10d-211">プラットフォーム列は、ポリシーが Microsoft 365 Apps for enterprise for Windows デバイス、Office for the web、またはすべてに適用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="be10d-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4.  <span data-ttu-id="be10d-212">選択が行われたら、[作成] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="be10d-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="be10d-213">Officeポリシーは、ユーザー ベースの展開のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="be10d-213">Office Configuration Policies only support user-based deployment</span></span>
