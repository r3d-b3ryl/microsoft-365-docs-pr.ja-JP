---
title: Microsoft 365 Apps for enterprise
description: Microsoft 365 アプリの展開方法、更新方法、および設定の管理方法
keywords: 変更履歴
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: 767489ba9f9ac63bc1a2d8b4999b6634335b1aef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547748"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="b1091-104">Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="b1091-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="b1091-105">初期展開</span><span class="sxs-lookup"><span data-stu-id="b1091-105">Initial deployment</span></span>

<span data-ttu-id="b1091-106">Microsoft マネージドデスクトップでは、Microsoft 365 Apps for enterprise (64 ビット) は、すべての [プログラムデバイス](../service-description/device-list.md)上のイメージの一部としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b1091-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="b1091-107">次のすべてのアプリケーションが、配信時にデバイス上に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1091-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="b1091-108">Word</span><span class="sxs-lookup"><span data-stu-id="b1091-108">Word</span></span>
- <span data-ttu-id="b1091-109">Excel</span><span class="sxs-lookup"><span data-stu-id="b1091-109">Excel</span></span>
- <span data-ttu-id="b1091-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="b1091-110">PowerPoint</span></span>
- <span data-ttu-id="b1091-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="b1091-111">Outlook</span></span>
- <span data-ttu-id="b1091-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="b1091-112">Publisher</span></span>
- <span data-ttu-id="b1091-113">Access</span><span class="sxs-lookup"><span data-stu-id="b1091-113">Access</span></span>
- <span data-ttu-id="b1091-114">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b1091-114">Skype for Business</span></span>
- <span data-ttu-id="b1091-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="b1091-115">OneNote</span></span>

<span data-ttu-id="b1091-116">この方法では、ネットワークへの影響を最小限に抑え、ユーザーがデバイスを受信するとすぐに生産性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="b1091-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="b1091-117">その後、管理対象デバイスに追加のポリシーを展開して、使用するアプリケーションを設定します。</span><span class="sxs-lookup"><span data-stu-id="b1091-117">We then deploy additional policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="b1091-118">Microsoft Teams は、Microsoft 365 enterprise 用アプリとは別に展開され、基本イメージには含まれていません。</span><span class="sxs-lookup"><span data-stu-id="b1091-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="b1091-119">ユーザーに対して使用可能な展開</span><span class="sxs-lookup"><span data-stu-id="b1091-119">Available deployment to users</span></span>

<span data-ttu-id="b1091-120">ユーザーが何らかの理由で、デバイス上に Microsoft 365 アプリを持っていない場合は、パッケージを使用してデバイスを予期した状態に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="b1091-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="b1091-121">**モダンワークプレース-Office Office365_Install**グループにユーザーを追加すると、会社のポータルでアプリを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b1091-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="b1091-122">Microsoft 365 enterprise 用アプリ (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="b1091-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="b1091-123">Microsoft マネージドデスクトップでは、32ビットバージョンの M365 Apps for enterprise を展開することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b1091-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="b1091-124">Microsoft 365 アプリの更新</span><span class="sxs-lookup"><span data-stu-id="b1091-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="b1091-125">Microsoft 365 アプリは [月次エンタープライズチャネル](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview)で更新するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="b1091-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](https://docs.microsoft.com/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="b1091-126">この方法では、ユーザーに毎月新しい Office の機能が提供されますが、予測可能なリリーススケジュールに従って1か月あたりの更新プログラムを1つだけ受け取ることができます。</span><span class="sxs-lookup"><span data-stu-id="b1091-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="b1091-127">更新プログラムは月の第2火曜日にリリースされます。これらの更新プログラムには、機能、セキュリティ、および品質の更新が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b1091-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="b1091-128">これらの更新プログラムは自動的に実行され、その特定のチャネルの Office CDN から直接プルされます。</span><span class="sxs-lookup"><span data-stu-id="b1091-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="b1091-129">Microsoft マネージドデスクトップでは、各リリースが環境内の潜在的な問題を識別するために staggers れます。</span><span class="sxs-lookup"><span data-stu-id="b1091-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="b1091-130">Microsoft 365 App product グループからのリリース後、28日以内に公開を完了します。</span><span class="sxs-lookup"><span data-stu-id="b1091-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="b1091-131">Microsoft マネージドデスクトップでは、次のように、別のグループにリリースを更新して、検証とテストの時間を確保します。</span><span class="sxs-lookup"><span data-stu-id="b1091-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="b1091-132">テスト: 0 日</span><span class="sxs-lookup"><span data-stu-id="b1091-132">Test: 0 days</span></span>
- <span data-ttu-id="b1091-133">最初: 0 日</span><span class="sxs-lookup"><span data-stu-id="b1091-133">First: 0 days</span></span>
- <span data-ttu-id="b1091-134">Fast: 7 日間</span><span class="sxs-lookup"><span data-stu-id="b1091-134">Fast: 7 days</span></span>
- <span data-ttu-id="b1091-135">広範:21 日</span><span class="sxs-lookup"><span data-stu-id="b1091-135">Broad: 21 days</span></span>

<span data-ttu-id="b1091-136">Microsoft マネージドデスクトップでは、デバイスの [更新期限](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) が7日間に設定されています。</span><span class="sxs-lookup"><span data-stu-id="b1091-136">Microsoft Managed Desktop sets a seven-day [update deadline](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="b1091-137">更新プログラムが利用可能になったら、7日以内にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1091-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="b1091-138">ユーザーには、いくつかの場所で更新が必要であることが [通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) されます。これは、システムトレイの期限よりも12時間前に、その期限よりも前に警告を表示します。</span><span class="sxs-lookup"><span data-stu-id="b1091-138">Users are [notified](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="b1091-139">更新を完了するには、すべての Microsoft 365 アプリを閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1091-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="b1091-140">更新プログラムの一時停止またはロールバック</span><span class="sxs-lookup"><span data-stu-id="b1091-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="b1091-141">何らかの理由で Microsoft 365 アプリの更新を一時停止またはロールバックする必要がある場合は、Microsoft マネージドデスクトップポータルを使用して [管理者サポート要求](../working-with-managed-desktop/admin-support.md) をファイルします。</span><span class="sxs-lookup"><span data-stu-id="b1091-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="b1091-142">Microsoft マネージドデスクトップでは、リリース中にすべての Microsoft 365 アプリのエラー率が監視されます。</span><span class="sxs-lookup"><span data-stu-id="b1091-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="b1091-143">新しいリリースとその先行タスクの間で品質に著しい違いがある場合は、Microsoft Managed Desktop 管理ポータルにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="b1091-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="b1091-144">重要度によっては、リリースを一時停止するかどうかを確認するか、問題を緩和するための処置が行われたことを知らせます。</span><span class="sxs-lookup"><span data-stu-id="b1091-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="b1091-145">配信の最適化</span><span class="sxs-lookup"><span data-stu-id="b1091-145">Delivery optimization</span></span>

<span data-ttu-id="b1091-146">配信の最適化は、Windows 10 で使用できるピアツーピアの配布テクノロジです。</span><span class="sxs-lookup"><span data-stu-id="b1091-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="b1091-147">これにより、デバイスがインターネット経由で Microsoft からダウンロードしたコンテンツ (更新プログラムなど) を共有できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b1091-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="b1091-148">これにより、デバイスは、Microsoft から更新プログラムを完全にダウンロードするのではなく、ローカルネットワーク上の別のデバイスから更新プログラムの一部を取得できるので、ネットワーク帯域幅を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="b1091-148">This can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="b1091-149">既定では、[配信の最適化](https://docs.microsoft.com/deployoffice/delivery-optimization)は、Windows 10 Enterprise または windows 10 のエデュケーションエディションを実行しているデバイスで有効になっています。</span><span class="sxs-lookup"><span data-stu-id="b1091-149">[Delivery Optimization](https://docs.microsoft.com/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="b1091-150">Microsoft マネージドデスクトップによって管理される設定</span><span class="sxs-lookup"><span data-stu-id="b1091-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="b1091-151">Microsoft では、一部の設定をサービスの一部として管理しています。</span><span class="sxs-lookup"><span data-stu-id="b1091-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="b1091-152">Microsoft マネージドデスクトップは Office セキュリティベースラインを管理していませんが、自分で設定するには、[ [管理の設定](#settings-you-manage) ] セクションのガイダンスに従ってください。</span><span class="sxs-lookup"><span data-stu-id="b1091-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="b1091-153">設定を更新する</span><span class="sxs-lookup"><span data-stu-id="b1091-153">Update settings</span></span>

<span data-ttu-id="b1091-154">Microsoft マネージドデスクトップでは、管理対象デバイスのすべての [更新設定](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) が保持されており、これらの設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1091-154">Microsoft Managed Desktop maintains all [update settings](https://docs.microsoft.com/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="b1091-155">更新が自動的に発生するように設定する</span><span class="sxs-lookup"><span data-stu-id="b1091-155">Set updates to occur automatically</span></span>

<span data-ttu-id="b1091-156">**既定値**: 有効</span><span class="sxs-lookup"><span data-stu-id="b1091-156">**Default value**: Enabled</span></span>

<span data-ttu-id="b1091-157">このポリシーは、クラウドからすべての Office デバイスを最新の状態に保つために構成されます。</span><span class="sxs-lookup"><span data-stu-id="b1091-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="b1091-158">更新プログラムを適用する期限を設定する</span><span class="sxs-lookup"><span data-stu-id="b1091-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="b1091-159">**既定値**は次のとおりです。7日</span><span class="sxs-lookup"><span data-stu-id="b1091-159">**Default value**: 7 days</span></span>

<span data-ttu-id="b1091-160">**Updatedeadline 期限**ポリシーは、更新がデバイスに適用されるまでのユーザーの猶予期間を構成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b1091-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="b1091-161">この期限ポリシーでは、ユーザーに対して、デバイスで必要な変更について [通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) することもトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="b1091-161">This deadline policy also triggers [notifications](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="b1091-162">デバイス上の更新プログラムを一定期間保留する</span><span class="sxs-lookup"><span data-stu-id="b1091-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="b1091-163">このポリシーは、更新管理デバイスグループごとに異なる方法で構成されており、更新の対象を満たすために Microsoft マネージドデスクトップに必要です。</span><span class="sxs-lookup"><span data-stu-id="b1091-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="b1091-164">テスト: 0 日</span><span class="sxs-lookup"><span data-stu-id="b1091-164">Test: 0 days</span></span>
- <span data-ttu-id="b1091-165">最初: 0 日</span><span class="sxs-lookup"><span data-stu-id="b1091-165">First: 0 days</span></span>
- <span data-ttu-id="b1091-166">ファスト7日</span><span class="sxs-lookup"><span data-stu-id="b1091-166">Fast 7 days</span></span>
- <span data-ttu-id="b1091-167">広範:21 日</span><span class="sxs-lookup"><span data-stu-id="b1091-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="b1091-168">通知の設定を更新する</span><span class="sxs-lookup"><span data-stu-id="b1091-168">Update notifications settings</span></span>

<span data-ttu-id="b1091-169">**既定値**: False</span><span class="sxs-lookup"><span data-stu-id="b1091-169">**Default value**: False</span></span>

<span data-ttu-id="b1091-170">Microsoft マネージドデスクトップデバイスで [更新通知を表示しない] 設定が **False** に設定されている場合は、更新が必要なときに [通知](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) することで、ユーザーに最高の更新プログラムを提供します。</span><span class="sxs-lookup"><span data-stu-id="b1091-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](https://docs.microsoft.com/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="b1091-171">更新プログラムを検索する場所を指定する</span><span class="sxs-lookup"><span data-stu-id="b1091-171">Specify a location to look for updates</span></span>

<span data-ttu-id="b1091-172">**既定値**: 月次エンタープライズチャネル</span><span class="sxs-lookup"><span data-stu-id="b1091-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="b1091-173">更新スケジュールを設定するには、必要に応じて、 **Updatepath** ポリシーと **UpdateChannel** ポリシーの組み合わせを使用します。</span><span class="sxs-lookup"><span data-stu-id="b1091-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="b1091-174">これらのポリシーは、すべての Office デバイスが毎月のエンタープライズチャネルの CDN から直接更新を受信するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="b1091-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="b1091-175">Microsoft 365 アプリのターゲットバージョンを指定する</span><span class="sxs-lookup"><span data-stu-id="b1091-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="b1091-176">ターゲットバージョンポリシーは、特定のバージョンの Office をロールバックまたは pin するために Microsoft マネージドデスクトップによって使用される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b1091-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="b1091-177">Office 自動更新を有効または無効にするオプションを非表示にする</span><span class="sxs-lookup"><span data-stu-id="b1091-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="b1091-178">**既定値**: 有効</span><span class="sxs-lookup"><span data-stu-id="b1091-178">**Default value**: Enabled</span></span>

<span data-ttu-id="b1091-179">Microsoft マネージドデスクトップでは、Microsoft 365 アプリケーションの更新対象を満たすために、この設定が必要になります。</span><span class="sxs-lookup"><span data-stu-id="b1091-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="b1091-180">最初の実行時の設定</span><span class="sxs-lookup"><span data-stu-id="b1091-180">First run settings</span></span> 

<span data-ttu-id="b1091-181">Office の初回実行時の動作に影響を与える設定がいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="b1091-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="b1091-182">エンドユーザーの代わりにライセンス条項に同意する</span><span class="sxs-lookup"><span data-stu-id="b1091-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="b1091-183">**既定値**: 無効</span><span class="sxs-lookup"><span data-stu-id="b1091-183">**Default value**: Disabled</span></span>

<span data-ttu-id="b1091-184">ユーザーが Microsoft 365 アプリを初めて開いたときに、ライセンス条項に同意するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1091-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="b1091-185">ユーザーの代わりにライセンス条項に同意する場合は、この設定を有効にするように Microsoft Managed Desktop Operations team にサービス要求をファイルします。</span><span class="sxs-lookup"><span data-stu-id="b1091-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="b1091-186">Outlook mobile の非表示のチェックボックス</span><span class="sxs-lookup"><span data-stu-id="b1091-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="b1091-187">**既定値**: 無効</span><span class="sxs-lookup"><span data-stu-id="b1091-187">**Default value**: Disabled</span></span>

<span data-ttu-id="b1091-188">ユーザーが初めて Outlook を開いたときに、Outlook Mobile をインストールするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b1091-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="b1091-189">このチェックボックスが表示されないようにするには、Microsoft Managed Desktop Operations team に対してサービス要求を実行し、デバイスでこの設定を有効にするように求めます。</span><span class="sxs-lookup"><span data-stu-id="b1091-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="b1091-190">その他の設定</span><span class="sxs-lookup"><span data-stu-id="b1091-190">Other settings</span></span>

<span data-ttu-id="b1091-191">Microsoft のマネージドデスクトップは、必要に応じて、お客様365の代わりに設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="b1091-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="b1091-192">個人用 OneDrive を無効にする</span><span class="sxs-lookup"><span data-stu-id="b1091-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="b1091-193">**既定値**: 無効</span><span class="sxs-lookup"><span data-stu-id="b1091-193">**Default value**: Disabled</span></span>

<span data-ttu-id="b1091-194">組織によっては、デバイス上の企業および個人の両方のファイルにアクセスするユーザーに懸念があります。</span><span class="sxs-lookup"><span data-stu-id="b1091-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="b1091-195">この設定を有効にするには、Microsoft Managed Desktop Operations teams を使用してサービス要求をファイルにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b1091-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="b1091-196">管理する設定</span><span class="sxs-lookup"><span data-stu-id="b1091-196">Settings you manage</span></span>

<span data-ttu-id="b1091-197">Microsoft Managed Desktop がまだサービスの一部として設定されていないその他のポリシーが多数あります。</span><span class="sxs-lookup"><span data-stu-id="b1091-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="b1091-198">これらは、 [Office Cloud Policy](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service を使用する Microsoft Intune を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="b1091-198">You can configure these by using Microsoft Intune, which uses the [Office Cloud Policy](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="b1091-199">これを行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b1091-199">To do this, follow these steps:</span></span>

1.  <span data-ttu-id="b1091-200">Microsoft エンドポイントマネージャー管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="b1091-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2.  <span data-ttu-id="b1091-201">**Office アプリのアプリ > ポリシーの選択 > 作成**</span><span class="sxs-lookup"><span data-stu-id="b1091-201">Select **Apps > Policies for Office apps > Create**</span></span>
3.  <span data-ttu-id="b1091-202">[ポリシー構成の **作成** ] ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b1091-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="b1091-203">名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="b1091-203">Enter a name.</span></span>
    - <span data-ttu-id="b1091-204">説明を入力します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="b1091-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="b1091-205">[ **割り当て**] で、このポリシーを Microsoft 365 Apps のすべてのユーザーに適用するか、または web 用に Office を使用してドキュメントに匿名でアクセスするユーザーに対して行うかを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1091-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="b1091-206">ポリシー構成に割り当てられている AAD ベースのセキュリティグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1091-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="b1091-207">各ポリシー構成は1つのグループにのみ割り当てることができ、各グループには1つのポリシー構成しか割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="b1091-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="b1091-208">ポリシーの構成に含めるポリシー設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="b1091-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="b1091-209">ポリシー設定名を検索して、構成するポリシー設定を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="b1091-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="b1091-210">また、ポリシーが推奨セキュリティベースラインであるかどうか、およびポリシーが構成されているかどうかについて、アプリケーションに対してフィルター処理することもできます。</span><span class="sxs-lookup"><span data-stu-id="b1091-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="b1091-211">[プラットフォーム] 列は、ポリシーが Microsoft 365 アプリ for enterprise for Windows のデバイス、web 用の Office、またはすべてに適用されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b1091-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4.  <span data-ttu-id="b1091-212">選択を行った後、[ **作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b1091-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="b1091-213">Office 構成ポリシーは、ユーザーベースの展開のみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="b1091-213">Office Configuration Policies only support user-based deployment</span></span>
