---
title: Microsoft 365 Apps for enterprise
description: アプリを展開Microsoft 365 Apps、更新方法、および設定の管理方法
keywords: 変更履歴
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: c3928b5814332f2585adc613e1e84cbe5cc883a0
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925613"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="10daa-104">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="10daa-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="10daa-105">初期展開</span><span class="sxs-lookup"><span data-stu-id="10daa-105">Initial deployment</span></span>

<span data-ttu-id="10daa-106">Microsoft マネージド デスクトップ (64 ビット) Microsoft 365 Apps for enterprise(64 ビット) がすべてのプログラム デバイスにイメージの一部としてインストールされていることを[確認します](../service-description/device-list.md)。</span><span class="sxs-lookup"><span data-stu-id="10daa-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="10daa-107">次のアプリケーションはすべて、配信時にデバイスに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10daa-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="10daa-108">Word</span><span class="sxs-lookup"><span data-stu-id="10daa-108">Word</span></span>
- <span data-ttu-id="10daa-109">Excel</span><span class="sxs-lookup"><span data-stu-id="10daa-109">Excel</span></span>
- <span data-ttu-id="10daa-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="10daa-110">PowerPoint</span></span>
- <span data-ttu-id="10daa-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="10daa-111">Outlook</span></span>
- <span data-ttu-id="10daa-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="10daa-112">Publisher</span></span>
- <span data-ttu-id="10daa-113">Access</span><span class="sxs-lookup"><span data-stu-id="10daa-113">Access</span></span>
- <span data-ttu-id="10daa-114">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="10daa-114">Skype for Business</span></span>
- <span data-ttu-id="10daa-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="10daa-115">OneNote</span></span>

<span data-ttu-id="10daa-116">この方法では、ネットワークへの影響を最小限に抑え、ユーザーがデバイスを受け取り次第、生産性を高めることができます。</span><span class="sxs-lookup"><span data-stu-id="10daa-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="10daa-117">その後、使用するアプリケーションをセットアップするために、管理対象デバイスにさらに多くのポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="10daa-117">We then deploy more policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="10daa-118">Microsoft Teamsは、Microsoft 365 Apps for enterpriseに展開され、基本イメージには含まれません。</span><span class="sxs-lookup"><span data-stu-id="10daa-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="10daa-119">ユーザーが利用可能な展開</span><span class="sxs-lookup"><span data-stu-id="10daa-119">Available deployment to users</span></span>

<span data-ttu-id="10daa-120">ユーザーが何らかの理由でデバイスにMicrosoft 365 Appsしていない場合は、パッケージを使用してデバイスを予期した状態に戻します。</span><span class="sxs-lookup"><span data-stu-id="10daa-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="10daa-121">ユーザーを **モダン Workplace-Office-Office365_Install グループ** に追加すると、アプリはユーザーがアクセスポータル サイト。</span><span class="sxs-lookup"><span data-stu-id="10daa-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="10daa-122">Microsoft 365 Apps for enterprise (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="10daa-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="10daa-123">Microsoft マネージド デスクトップ 32 ビット 版 M365 Apps for enterprise の展開はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="10daa-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="10daa-124">更新プログラムのMicrosoft 365 Apps</span><span class="sxs-lookup"><span data-stu-id="10daa-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="10daa-125">Microsoft 365 Apps月次チャネルで更新Enterprise[されます](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)。</span><span class="sxs-lookup"><span data-stu-id="10daa-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="10daa-126">この方法では、ユーザーは毎月新しいOffice機能を提供しますが、予測可能なリリース スケジュールで月に 1 回の更新プログラムを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="10daa-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="10daa-127">更新プログラムは、月の第 2 火曜日にリリースされます。これらの更新プログラムには、機能、セキュリティ、および品質更新プログラムが含まれます。</span><span class="sxs-lookup"><span data-stu-id="10daa-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="10daa-128">これらの更新プログラムは自動的に実行され、その特定のチャネルOffice CDNから直接取得されます。</span><span class="sxs-lookup"><span data-stu-id="10daa-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="10daa-129">Microsoft マネージド デスクトップ各リリースをずらして、環境内の潜在的な問題を特定します。</span><span class="sxs-lookup"><span data-stu-id="10daa-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="10daa-130">アプリ製品グループからのリリースから 28 日後にロールアウトMicrosoft 365完了します。</span><span class="sxs-lookup"><span data-stu-id="10daa-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="10daa-131">Microsoft マネージド デスクトップは、次のように検証とテストの時間を割り当て、リリースをさまざまなグループにスケジュールします。</span><span class="sxs-lookup"><span data-stu-id="10daa-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="10daa-132">テスト: ゼロ日</span><span class="sxs-lookup"><span data-stu-id="10daa-132">Test: zero days</span></span>
- <span data-ttu-id="10daa-133">最初: ゼロ日</span><span class="sxs-lookup"><span data-stu-id="10daa-133">First: zero days</span></span>
- <span data-ttu-id="10daa-134">高速: 3 日</span><span class="sxs-lookup"><span data-stu-id="10daa-134">Fast: 3 days</span></span>
- <span data-ttu-id="10daa-135">広範: 7 日間</span><span class="sxs-lookup"><span data-stu-id="10daa-135">Broad: 7 days</span></span>

<span data-ttu-id="10daa-136">Microsoft マネージド デスクトップデバイスの 7 日間の[更新期限を](/deployoffice/configure-update-settings-microsoft-365-apps)設定します。</span><span class="sxs-lookup"><span data-stu-id="10daa-136">Microsoft Managed Desktop sets a seven-day [update deadline](/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="10daa-137">更新プログラムが利用可能な場合は、7 日以内にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="10daa-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="10daa-138">ユーザーには[](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)、期限の 12 時間前にアプリケーション、システム トレイ内の複数の場所で更新プログラムが必要と通知され、期限の 15 分前に警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="10daa-138">Users are [notified](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="10daa-139">更新Microsoft 365 Apps完了するには、すべての更新プログラムを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="10daa-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="10daa-140">更新プログラムの一時停止またはロールバック</span><span class="sxs-lookup"><span data-stu-id="10daa-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="10daa-141">何らかの理由でアプリの更新プログラムMicrosoft 365一時停止またはロールバックする必要がある場合は、管理者[](../working-with-managed-desktop/admin-support.md)サポート要求をポータルからMicrosoft マネージド デスクトップしてください。</span><span class="sxs-lookup"><span data-stu-id="10daa-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="10daa-142">リリース中に、Microsoft マネージド デスクトップのエラー率を監視Microsoft 365 Apps。</span><span class="sxs-lookup"><span data-stu-id="10daa-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="10daa-143">新しいリリースと先行リリースの品質に大きな違いがある場合は、管理者ポータルからMicrosoft マネージド デスクトップがあります。</span><span class="sxs-lookup"><span data-stu-id="10daa-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="10daa-144">重大度に応じて、リリースを一時停止するか、問題を軽減するための措置を講じてお知らせします。</span><span class="sxs-lookup"><span data-stu-id="10daa-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="10daa-145">配信の最適化</span><span class="sxs-lookup"><span data-stu-id="10daa-145">Delivery optimization</span></span>

<span data-ttu-id="10daa-146">配信の最適化は、このサービスで利用できるピアツーピア配布Windows 10。</span><span class="sxs-lookup"><span data-stu-id="10daa-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="10daa-147">これにより、デバイスは、デバイスがインターネットを通して Microsoft からダウンロードした更新プログラムなどのコンテンツを共有できます。</span><span class="sxs-lookup"><span data-stu-id="10daa-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="10daa-148">デバイスが Microsoft から更新プログラムを完全にダウンロードする代わりに、ローカル ネットワーク上の別のデバイスから更新プログラムの一部を取得できるので、この機能を使用すると、ネットワーク帯域幅を削減できます。</span><span class="sxs-lookup"><span data-stu-id="10daa-148">Using it can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="10daa-149">[配信の最適化](/deployoffice/delivery-optimization)は、サービス エディションまたはサービス エディションをWindows 10 EnterpriseデバイスWindows 10 Education有効になっています。</span><span class="sxs-lookup"><span data-stu-id="10daa-149">[Delivery Optimization](/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="10daa-150">設定によって管理Microsoft マネージド デスクトップ</span><span class="sxs-lookup"><span data-stu-id="10daa-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="10daa-151">Microsoft は、サービスの一部としていくつかの設定を管理します。</span><span class="sxs-lookup"><span data-stu-id="10daa-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="10daa-152">Microsoft マネージド デスクトップセキュリティ ベースラインは管理Office、管理するセクションのガイダンスに従って、設定[設定](#settings-you-manage)できます。</span><span class="sxs-lookup"><span data-stu-id="10daa-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="10daa-153">設定を更新する</span><span class="sxs-lookup"><span data-stu-id="10daa-153">Update settings</span></span>

<span data-ttu-id="10daa-154">Microsoft マネージド デスクトップデバイスのすべての[更新設定](/deployoffice/configure-update-settings-microsoft-365-apps)が維持され、これらの設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10daa-154">Microsoft Managed Desktop maintains all [update settings](/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="10daa-155">更新が自動的に発生するように設定する</span><span class="sxs-lookup"><span data-stu-id="10daa-155">Set updates to occur automatically</span></span>

<span data-ttu-id="10daa-156">**既定値**: 有効</span><span class="sxs-lookup"><span data-stu-id="10daa-156">**Default value**: Enabled</span></span>

<span data-ttu-id="10daa-157">このポリシーは、すべてのデバイスOfficeクラウドから最新の状態に保つ必要がある場合に構成されます。</span><span class="sxs-lookup"><span data-stu-id="10daa-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="10daa-158">更新プログラムを適用する必要がある期限を設定する</span><span class="sxs-lookup"><span data-stu-id="10daa-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="10daa-159">**既定値**: 7 日間</span><span class="sxs-lookup"><span data-stu-id="10daa-159">**Default value**: 7 days</span></span>

<span data-ttu-id="10daa-160">**UpdateDeadline ポリシーは**、更新プログラムがデバイスに適用される前にユーザーが持つ猶予期間を構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="10daa-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="10daa-161">この期限ポリシーは、ユーザーに [通知](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) をトリガーして、デバイスで必要な変更をユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="10daa-161">This deadline policy also triggers [notifications](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="10daa-162">デバイスの更新プログラムを一期間延期する</span><span class="sxs-lookup"><span data-stu-id="10daa-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="10daa-163">このポリシーは、更新プログラム管理デバイス グループごとに異なる方法で構成され、更新プログラムのMicrosoft マネージド デスクトップを満たすために必要です。</span><span class="sxs-lookup"><span data-stu-id="10daa-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="10daa-164">テスト: ゼロ日</span><span class="sxs-lookup"><span data-stu-id="10daa-164">Test: zero days</span></span>
- <span data-ttu-id="10daa-165">最初: ゼロ日</span><span class="sxs-lookup"><span data-stu-id="10daa-165">First: zero days</span></span>
- <span data-ttu-id="10daa-166">高速 7 日</span><span class="sxs-lookup"><span data-stu-id="10daa-166">Fast 7 days</span></span>
- <span data-ttu-id="10daa-167">広範: 21 日</span><span class="sxs-lookup"><span data-stu-id="10daa-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="10daa-168">通知の設定を更新する</span><span class="sxs-lookup"><span data-stu-id="10daa-168">Update notifications settings</span></span>

<span data-ttu-id="10daa-169">**既定値**: False</span><span class="sxs-lookup"><span data-stu-id="10daa-169">**Default value**: False</span></span>

<span data-ttu-id="10daa-170">[更新通知を非表示にする] 設定は、Microsoft マネージド デスクトップ デバイスで **False** に設定され、更新が必要な [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps)ときにユーザーに通知することで、ユーザーに最適な更新エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="10daa-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="10daa-171">更新プログラムを検索する場所を指定する</span><span class="sxs-lookup"><span data-stu-id="10daa-171">Specify a location to look for updates</span></span>

<span data-ttu-id="10daa-172">**既定値**: 月次チャネルEnterpriseチャネル</span><span class="sxs-lookup"><span data-stu-id="10daa-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="10daa-173">**UpdatePath** ポリシーと **UpdateChannel** ポリシーの組み合わせは、更新スケジュールを達成するために必要に応じて使用されます。</span><span class="sxs-lookup"><span data-stu-id="10daa-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="10daa-174">これらのポリシーは、すべてのデバイスが月次OfficeチャネルのCDN更新プログラムを直接受信Enterprise設定されています。</span><span class="sxs-lookup"><span data-stu-id="10daa-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="10daa-175">ターゲット バージョンの指定Microsoft 365 Apps</span><span class="sxs-lookup"><span data-stu-id="10daa-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="10daa-176">ターゲット バージョン ポリシーは、特定のバージョンMicrosoft マネージド デスクトップをロールバックまたはピン留めするために、ユーザーが使用する場合Office。</span><span class="sxs-lookup"><span data-stu-id="10daa-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="10daa-177">自動更新を有効または無効にするオプションOffice非表示にする</span><span class="sxs-lookup"><span data-stu-id="10daa-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="10daa-178">**既定値**: 有効</span><span class="sxs-lookup"><span data-stu-id="10daa-178">**Default value**: Enabled</span></span>

<span data-ttu-id="10daa-179">この設定は、Microsoft マネージド デスクトップアプリケーションの更新ターゲットを満たすためにMicrosoft 365です。</span><span class="sxs-lookup"><span data-stu-id="10daa-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="10daa-180">最初の実行設定</span><span class="sxs-lookup"><span data-stu-id="10daa-180">First run settings</span></span> 

<span data-ttu-id="10daa-181">初回実行時の動作に影響を与える設定Officeがあります。</span><span class="sxs-lookup"><span data-stu-id="10daa-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="10daa-182">エンド ユーザーに代わってライセンス条項に同意する</span><span class="sxs-lookup"><span data-stu-id="10daa-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="10daa-183">**既定値**: 無効</span><span class="sxs-lookup"><span data-stu-id="10daa-183">**Default value**: Disabled</span></span>

<span data-ttu-id="10daa-184">ユーザーがアプリを初めて開Microsoft 365、ライセンス条項に同意するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10daa-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="10daa-185">ユーザーに代わってライセンス条項に同意する場合は、Microsoft マネージド デスクトップ Operations チームにサービス要求を送信し、この設定を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="10daa-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="10daa-186">[モバイルOutlookを抑制する] チェック ボックス</span><span class="sxs-lookup"><span data-stu-id="10daa-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="10daa-187">**既定値**: 無効</span><span class="sxs-lookup"><span data-stu-id="10daa-187">**Default value**: Disabled</span></span>

<span data-ttu-id="10daa-188">ユーザーがモバイルを初めて開Outlook、Mobile へのインストールを求Outlookされます。</span><span class="sxs-lookup"><span data-stu-id="10daa-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="10daa-189">ユーザーにこのチェック ボックスを表示しない場合は、Microsoft マネージド デスクトップ Operations チームにサービス要求を送信し、デバイスでこの設定を有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="10daa-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="10daa-190">その他の設定</span><span class="sxs-lookup"><span data-stu-id="10daa-190">Other settings</span></span>

<span data-ttu-id="10daa-191">他にも、Microsoft 365で構成Microsoft マネージド デスクトップできるアプリ設定があります。</span><span class="sxs-lookup"><span data-stu-id="10daa-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="10daa-192">個人用アカウントを無効OneDrive</span><span class="sxs-lookup"><span data-stu-id="10daa-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="10daa-193">**既定値**: 無効</span><span class="sxs-lookup"><span data-stu-id="10daa-193">**Default value**: Disabled</span></span>

<span data-ttu-id="10daa-194">一部の組織では、デバイス上の企業ファイルと個人ファイルの両方にアクセスできるユーザーを懸念しています。</span><span class="sxs-lookup"><span data-stu-id="10daa-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="10daa-195">この設定を有効にMicrosoft マネージド デスクトップするサービス要求を、運用チームに送信できます。</span><span class="sxs-lookup"><span data-stu-id="10daa-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="10daa-196">設定管理する方法</span><span class="sxs-lookup"><span data-stu-id="10daa-196">Settings you manage</span></span>

<span data-ttu-id="10daa-197">サービスの一部としてまだ設定Microsoft マネージド デスクトップポリシーは他にも多数存在します。</span><span class="sxs-lookup"><span data-stu-id="10daa-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="10daa-198">これらのポリシーは、クラウド ポリシー サービスMicrosoft Intune使用する Office[を使用して構成](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied)できます。</span><span class="sxs-lookup"><span data-stu-id="10daa-198">You can configure these policies by using Microsoft Intune, which uses the [Office Cloud Policy](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="10daa-199">これらのポリシーを設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="10daa-199">To set these policies, follow these steps:</span></span>

1.  <span data-ttu-id="10daa-200">Microsoft エンドポイント マネージャー管理センター</span><span class="sxs-lookup"><span data-stu-id="10daa-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2.  <span data-ttu-id="10daa-201">[**作成] >アプリの [アプリとOfficeポリシー>選択します。**</span><span class="sxs-lookup"><span data-stu-id="10daa-201">Select **Apps > Policies for Office apps > Create**</span></span>
3.  <span data-ttu-id="10daa-202">[ポリシー構成 **の作成]** ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="10daa-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="10daa-203">名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="10daa-203">Enter a name.</span></span>
    - <span data-ttu-id="10daa-204">説明を入力します (オプション)。</span><span class="sxs-lookup"><span data-stu-id="10daa-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="10daa-205">割 **り当** てで、このポリシーが Microsoft 365 Apps for enterprise のすべてのユーザーに適用されるのか、web 用の Office を使用してドキュメントに匿名でアクセスするユーザーに適用されるのかを選択します。</span><span class="sxs-lookup"><span data-stu-id="10daa-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="10daa-206">ポリシー構成に割り当てられている AAD ベースのセキュリティ グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="10daa-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="10daa-207">各ポリシー構成は 1 つのグループにのみ割り当て、各グループには 1 つのポリシー構成のみを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="10daa-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="10daa-208">ポリシー構成に含めるポリシー設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="10daa-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="10daa-209">ポリシー設定名を検索して、構成するポリシー設定を検索できます。</span><span class="sxs-lookup"><span data-stu-id="10daa-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="10daa-210">また、アプリケーション、ポリシーが推奨されるセキュリティ 基準かどうか、およびポリシーが構成されているかどうかをフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="10daa-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="10daa-211">[プラットフォーム] 列は、ポリシーが Microsoft 365 Apps for enterpriseデバイス、Windows、Officeに適用されるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="10daa-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4.  <span data-ttu-id="10daa-212">選択が行われたら、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="10daa-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="10daa-213">Office構成ポリシーは、ユーザー ベースの展開のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="10daa-213">Office Configuration Policies only support user-based deployment</span></span>