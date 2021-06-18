---
title: 改ざん防止機能を使用してセキュリティ設定を保護する
ms.reviewer: pahuijbr, hayhov, oogunrinde
manager: dansimp
description: タンパープロテクションを使用して、悪意のあるアプリが重要なセキュリティ設定を変更するのを防ぐ。
keywords: マルウェア、防御者、ウイルス対策、改ざん防止
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.date: 06/17/2021
ms.openlocfilehash: 7050a1588b71ac106d5364f29c76d379072e9511
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007419"
---
# <a name="protect-security-settings-with-tamper-protection"></a><span data-ttu-id="31f8d-104">改ざん防止機能を使用してセキュリティ設定を保護する</span><span class="sxs-lookup"><span data-stu-id="31f8d-104">Protect security settings with tamper protection</span></span>

<span data-ttu-id="31f8d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="31f8d-105">**Applies to:**</span></span>

- [<span data-ttu-id="31f8d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="31f8d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="31f8d-107">タンパープロテクションは、次のバージョンのデバイスを実行しているデバイスWindows。</span><span class="sxs-lookup"><span data-stu-id="31f8d-107">Tamper protection is available for devices that are running one of the following versions of Windows:</span></span>

- <span data-ttu-id="31f8d-108">Windows 10</span><span class="sxs-lookup"><span data-stu-id="31f8d-108">Windows 10</span></span>
- <span data-ttu-id="31f8d-109">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31f8d-109">Windows Server 2019</span></span>
- <span data-ttu-id="31f8d-110">Windowsサーバー、バージョン 1803 以降</span><span class="sxs-lookup"><span data-stu-id="31f8d-110">Windows Server, version 1803 or later</span></span>
- <span data-ttu-id="31f8d-111">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="31f8d-111">Windows Server 2016</span></span>

## <a name="overview"></a><span data-ttu-id="31f8d-112">概要</span><span class="sxs-lookup"><span data-stu-id="31f8d-112">Overview</span></span>

<span data-ttu-id="31f8d-113">一部の種類のサイバー攻撃では、悪いアクターがコンピューターでウイルス対策保護などのセキュリティ機能を無効にしようとします。</span><span class="sxs-lookup"><span data-stu-id="31f8d-113">During some kinds of cyber attacks, bad actors try to disable security features, such as anti-virus protection, on your machines.</span></span> <span data-ttu-id="31f8d-114">悪いアクターは、データに簡単にアクセスしたり、マルウェアをインストールしたり、データ、ID、デバイスを悪用したりするために、セキュリティ機能を無効にしています。</span><span class="sxs-lookup"><span data-stu-id="31f8d-114">Bad actors like to disable your security features to get easier access to your data, to install malware, or to otherwise exploit your data, identity, and devices.</span></span> <span data-ttu-id="31f8d-115">タンパープロテクションは、このような事態が発生するのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-115">Tamper protection helps prevent these kinds of things from occurring.</span></span>

<span data-ttu-id="31f8d-116">タンパープロテクションを使用すると、悪意のあるアプリは次のようなアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-116">With tamper protection, malicious apps are prevented from taking actions such as:</span></span>

- <span data-ttu-id="31f8d-117">ウイルスおよび脅威の保護の無効化</span><span class="sxs-lookup"><span data-stu-id="31f8d-117">Disabling virus and threat protection</span></span>
- <span data-ttu-id="31f8d-118">リアルタイム保護の無効化</span><span class="sxs-lookup"><span data-stu-id="31f8d-118">Disabling real-time protection</span></span>
- <span data-ttu-id="31f8d-119">動作の監視の無効化</span><span class="sxs-lookup"><span data-stu-id="31f8d-119">Turning off behavior monitoring</span></span>
- <span data-ttu-id="31f8d-120">ウイルス対策(IOfficeAntivirus (IOAV) など) の無効化</span><span class="sxs-lookup"><span data-stu-id="31f8d-120">Disabling antivirus (such as IOfficeAntivirus (IOAV))</span></span>
- <span data-ttu-id="31f8d-121">クラウド配信の保護の無効化</span><span class="sxs-lookup"><span data-stu-id="31f8d-121">Disabling cloud-delivered protection</span></span>
- <span data-ttu-id="31f8d-122">セキュリティ インテリジェンスの更新プログラムの削除</span><span class="sxs-lookup"><span data-stu-id="31f8d-122">Removing security intelligence updates</span></span>

### <a name="how-it-works"></a><span data-ttu-id="31f8d-123">メカニズム</span><span class="sxs-lookup"><span data-stu-id="31f8d-123">How it works</span></span>

<span data-ttu-id="31f8d-124">タンパープロテクションは基本的Microsoft Defender ウイルス対策ロックし、次のようなアプリやメソッドを介してセキュリティ設定が変更されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="31f8d-124">Tamper protection essentially locks Microsoft Defender Antivirus and prevents your security settings from being changed through apps and methods such as:</span></span>

- <span data-ttu-id="31f8d-125">デバイスのレジストリ エディターで設定Windowsする</span><span class="sxs-lookup"><span data-stu-id="31f8d-125">Configuring settings in Registry Editor on your Windows device</span></span>
- <span data-ttu-id="31f8d-126">PowerShell コマンドレットによる設定の変更</span><span class="sxs-lookup"><span data-stu-id="31f8d-126">Changing settings through PowerShell cmdlets</span></span>
- <span data-ttu-id="31f8d-127">グループ ポリシーによるセキュリティ設定の編集または削除</span><span class="sxs-lookup"><span data-stu-id="31f8d-127">Editing or removing security settings through group policies</span></span>

<span data-ttu-id="31f8d-128">改ざん防止では、セキュリティ設定を表示できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="31f8d-128">Tamper protection doesn't prevent you from viewing your security settings.</span></span> <span data-ttu-id="31f8d-129">また、改ざん防止は、サードパーティのウイルス対策アプリがアプリに登録する方法Windows セキュリティではありません。</span><span class="sxs-lookup"><span data-stu-id="31f8d-129">And, tamper protection doesn't affect how third-party antivirus apps register with the Windows Security app.</span></span> <span data-ttu-id="31f8d-130">組織が E5 のWindows 10 Enterprise場合、個々のユーザーは改ざん防止の設定を変更できます。このような場合、改ざん防止はセキュリティ チームによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-130">If your organization is using Windows 10 Enterprise E5, individual users can't change the tamper protection setting; in those cases, tamper protection is managed by your security team.</span></span>

### <a name="what-do-you-want-to-do"></a><span data-ttu-id="31f8d-131">目的に合ったトピックをクリックしてください</span><span class="sxs-lookup"><span data-stu-id="31f8d-131">What do you want to do?</span></span>

| <span data-ttu-id="31f8d-132">このタスクを実行するには...</span><span class="sxs-lookup"><span data-stu-id="31f8d-132">To perform this task...</span></span> | <span data-ttu-id="31f8d-133">このセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31f8d-133">See this section...</span></span> |
|:---|:---|
| <span data-ttu-id="31f8d-134">テナント全体の改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="31f8d-134">Manage tamper protection across your tenant</span></span> <p><span data-ttu-id="31f8d-135">タンパープロテMicrosoft Defender セキュリティ センターオン/オフを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-135">Use the Microsoft Defender Security Center to turn tamper protection on or off</span></span> | [<span data-ttu-id="31f8d-136">サーバーを使用して組織の改ざん防止を管理Microsoft Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="31f8d-136">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) |
| <span data-ttu-id="31f8d-137">組織内の改ざん防止設定を微調整する</span><span class="sxs-lookup"><span data-stu-id="31f8d-137">Fine-tune tamper protection settings in your organization</span></span> <p><span data-ttu-id="31f8d-138">Intune (Microsoft エンドポイント マネージャー) を使用して、タンパープロテクションのオンとオフを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-138">Use Intune (Microsoft Endpoint Manager) to turn tamper protection on or off.</span></span> <span data-ttu-id="31f8d-139">この方法では、一部またはすべてのユーザーに対して改ざん防止を構成できます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-139">You can configure tamper protection for some or all users with this method.</span></span> | [<span data-ttu-id="31f8d-140">Intune を使用して組織の改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="31f8d-140">Manage tamper protection for your organization using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune) |
| <span data-ttu-id="31f8d-141">Configuration Manager を使用して組織の改ざん防止を有効 (または無効にする)</span><span class="sxs-lookup"><span data-stu-id="31f8d-141">Turn tamper protection on (or off) for your organization with Configuration Manager</span></span> | [<span data-ttu-id="31f8d-142">Configuration Manager バージョン 2006 でテナント接続を使用して組織の改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="31f8d-142">Manage tamper protection for your organization using tenant attach with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006) |
| <span data-ttu-id="31f8d-143">個々のデバイスのタンパープロテクションをオン (またはオフ) にする</span><span class="sxs-lookup"><span data-stu-id="31f8d-143">Turn tamper protection on (or off) for an individual device</span></span> | [<span data-ttu-id="31f8d-144">個々のデバイスで改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="31f8d-144">Manage tamper protection on an individual device</span></span>](#manage-tamper-protection-on-an-individual-device) |
| <span data-ttu-id="31f8d-145">デバイスでの改ざんの試みについての詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="31f8d-145">View details about tampering attempts on devices</span></span> | [<span data-ttu-id="31f8d-146">改ざんの試行に関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="31f8d-146">View information about tampering attempts</span></span>](#view-information-about-tampering-attempts) |
| <span data-ttu-id="31f8d-147">セキュリティに関する推奨事項を確認する</span><span class="sxs-lookup"><span data-stu-id="31f8d-147">Review your security recommendations</span></span> | [<span data-ttu-id="31f8d-148">セキュリティに関する推奨事項を確認する</span><span class="sxs-lookup"><span data-stu-id="31f8d-148">Review security recommendations</span></span>](#review-your-security-recommendations) |
| <span data-ttu-id="31f8d-149">よく寄せられる質問 (FAQ) の一覧を確認する</span><span class="sxs-lookup"><span data-stu-id="31f8d-149">Review the list of frequently asked questions (FAQs)</span></span> | [<span data-ttu-id="31f8d-150">FAQ を参照する</span><span class="sxs-lookup"><span data-stu-id="31f8d-150">Browse the FAQs</span></span>](#view-information-about-tampering-attempts) |

<span data-ttu-id="31f8d-151">タンパープロテクションを有効にするために使用する方法や管理ツールによっては、MAPS (クラウド配信保護) に依存している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31f8d-151">Depending on the method or management tool you use to enable Tamper protection, there might be a dependency on MAPS (cloud-delivered protection).</span></span> 

<span data-ttu-id="31f8d-152">次の表に、メソッド、ツール、依存関係の詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="31f8d-152">The following table provides details on the methods, tools, and dependencies.</span></span>

| <span data-ttu-id="31f8d-153">タンパープロテクションを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="31f8d-153">How Tamper protection is enabled</span></span>  | <span data-ttu-id="31f8d-154">MAPS への依存 (クラウドによる保護)</span><span class="sxs-lookup"><span data-stu-id="31f8d-154">Dependency on MAPS (cloud-delivered protection)</span></span>    |
|:----|:----|
| <span data-ttu-id="31f8d-155">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="31f8d-155">Microsoft Intune</span></span>  | <span data-ttu-id="31f8d-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="31f8d-156">No</span></span> |
| <span data-ttu-id="31f8d-157">Microsoft Endpoint Configuration Manager + テナント接続</span><span class="sxs-lookup"><span data-stu-id="31f8d-157">Microsoft Endpoint Configuration Manager + Tenant Attach</span></span>  |     <span data-ttu-id="31f8d-158">いいえ</span><span class="sxs-lookup"><span data-stu-id="31f8d-158">No</span></span>  |
| <span data-ttu-id="31f8d-159">Microsoft Defender セキュリティ センター ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )</span><span class="sxs-lookup"><span data-stu-id="31f8d-159">Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>    |     <span data-ttu-id="31f8d-160">必要</span><span class="sxs-lookup"><span data-stu-id="31f8d-160">Yes</span></span> |
| <span data-ttu-id="31f8d-161">Microsoft 365 Defender ポータル ( [https://security.microsoft.com](https://security.microsoft.com) )</span><span class="sxs-lookup"><span data-stu-id="31f8d-161">Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com))</span></span>  |     <span data-ttu-id="31f8d-162">必要</span><span class="sxs-lookup"><span data-stu-id="31f8d-162">Yes</span></span>  |

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center"></a><span data-ttu-id="31f8d-163">サーバーを使用して組織の改ざん防止を管理Microsoft Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="31f8d-163">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>

<span data-ttu-id="31f8d-164">タンパープロテクションは、テナントのパスワード () を使用してオンまたはMicrosoft Defender セキュリティ センターできます [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="31f8d-164">Tamper protection can be turned on or off for your tenant using the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span> <span data-ttu-id="31f8d-165">以下に注意点を示します。</span><span class="sxs-lookup"><span data-stu-id="31f8d-165">Here are a few points to keep in mind:</span></span>

- <span data-ttu-id="31f8d-166">現時点では、新しい展開では、Microsoft Defender セキュリティ センターでタンパープロテクションを管理するオプションがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="31f8d-166">Currently, the option to manage tamper protection in the Microsoft Defender Security Center is on by default for new deployments.</span></span> <span data-ttu-id="31f8d-167">既存の展開では、改ざん防止はオプトインベースで利用できます。近い将来、既定の方法でオプトインを行う予定です。</span><span class="sxs-lookup"><span data-stu-id="31f8d-167">For existing deployments, tamper protection is available on an opt-in basis, with plans to make opting in the default method in the near future.</span></span> <span data-ttu-id="31f8d-168">(オプトインするには、Microsoft Defender セキュリティ センターを選択 **設定**  > **高度な機能**  > **タンパープロテクション**.)</span><span class="sxs-lookup"><span data-stu-id="31f8d-168">(To opt in, in the Microsoft Defender Security Center, choose **Settings** > **Advanced features** > **Tamper protection**.)</span></span> 

- <span data-ttu-id="31f8d-169">改ざん防止を管理Microsoft Defender セキュリティ センター、Intune またはテナント接続方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31f8d-169">When you use the Microsoft Defender Security Center to manage tamper protection, you do not have to use Intune or the tenant attach method.</span></span>

- <span data-ttu-id="31f8d-170">Microsoft Defender セキュリティ センター でタンパープロテクションを管理すると、この設定はテナント全体に適用され、Windows 10、Windows Server 2016、または Windows Server 2019 を実行しているすべてのデバイスに影響します。</span><span class="sxs-lookup"><span data-stu-id="31f8d-170">When you manage tamper protection in the Microsoft Defender Security Center, the setting is applied tenant wide, affecting all of your devices that are running Windows 10, Windows Server 2016, or Windows Server 2019.</span></span> <span data-ttu-id="31f8d-171">タンパープロテクションを微調整するには (一部のデバイスではタンパープロテクションをオンにし、他のデバイスではオフにするなど [)、Intune](#manage-tamper-protection-for-your-organization-using-intune) または Configuration Manager をテナント接続で [使用します](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)。</span><span class="sxs-lookup"><span data-stu-id="31f8d-171">To fine-tune tamper protection (such as having tamper protection on for some devices but off for others), use either [Intune](#manage-tamper-protection-for-your-organization-using-intune) or [Configuration Manager with tenant attach](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006).</span></span>

- <span data-ttu-id="31f8d-172">ハイブリッド環境がある場合、Intune で構成されたタンパープロテクション設定は、Intune で構成された設定よりも優先Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="31f8d-172">If you have a hybrid environment, tamper protection settings configured in Intune take precedence over settings configured in the Microsoft Defender Security Center.</span></span> 

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-defender-security-center"></a><span data-ttu-id="31f8d-173">ユーザーの改ざん防止を管理するための要件Microsoft Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="31f8d-173">Requirements for managing tamper protection in the Microsoft Defender Security Center</span></span>

- <span data-ttu-id="31f8d-174">グローバル管理者、セキュリティ [管理者、](/microsoft-365/security/defender-endpoint/assign-portal-access)セキュリティ操作など、適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="31f8d-174">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="31f8d-175">デバイスWindows次のいずれかのバージョンのデバイスを実行している必要Windows。</span><span class="sxs-lookup"><span data-stu-id="31f8d-175">Your Windows devices must be running one of the following versions of Windows:</span></span>

   - <span data-ttu-id="31f8d-176">Windows 10</span><span class="sxs-lookup"><span data-stu-id="31f8d-176">Windows 10</span></span>
   - [<span data-ttu-id="31f8d-177">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="31f8d-177">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
   - <span data-ttu-id="31f8d-178">Windowsサーバー、バージョン[1803](/windows/release-health/status-windows-10-1803)以降</span><span class="sxs-lookup"><span data-stu-id="31f8d-178">Windows Server, version [1803](/windows/release-health/status-windows-10-1803) or later</span></span>
   - [<span data-ttu-id="31f8d-179">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="31f8d-179">Windows Server 2016</span></span>](/windows-server/get-started/whats-new-in-windows-server-2016)
   - <span data-ttu-id="31f8d-180">リリースの詳細については、「リリース情報Windows 10[参照してください](/windows/release-health/release-information)。</span><span class="sxs-lookup"><span data-stu-id="31f8d-180">For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).</span></span>

- <span data-ttu-id="31f8d-181">デバイスは、Microsoft [Defender for Endpoint にオンボードされている必要があります](/microsoft-365/security/defender-endpoint/onboarding)。</span><span class="sxs-lookup"><span data-stu-id="31f8d-181">Your devices must be [onboarded to Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/onboarding).</span></span>

- <span data-ttu-id="31f8d-182">デバイスでマルウェア対策プラットフォーム バージョン 4.18.2010.7 (以上) とマルウェア対策エンジン バージョン 1.1.17600.5 (以上) を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="31f8d-182">Your devices must be using anti-malware platform version 4.18.2010.7 (or above) and anti-malware engine version 1.1.17600.5 (or above).</span></span> <span data-ttu-id="31f8d-183">([更新プログラムMicrosoft Defender ウイルス対策管理し、基準計画を適用](manage-updates-baselines-microsoft-defender-antivirus.md)します。)</span><span class="sxs-lookup"><span data-stu-id="31f8d-183">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

- <span data-ttu-id="31f8d-184">[クラウドによる保護を](enable-cloud-protection-microsoft-defender-antivirus.md) 有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="31f8d-184">[Cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be turned on.</span></span>

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-defender-security-center"></a><span data-ttu-id="31f8d-185">タンパープロテクションをオン (またはオフ) にMicrosoft Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="31f8d-185">Turn tamper protection on (or off) in the Microsoft Defender Security Center</span></span> 

![タンパープロテクションをオンMicrosoft Defender セキュリティ センター](images/mde-turn-tamperprotect-on.png)

1. <span data-ttu-id="31f8d-187">[パスワード] ( ) にMicrosoft Defender セキュリティ センター [https://securitycenter.windows.com](https://securitycenter.windows.com) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="31f8d-187">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="31f8d-188">[設定]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="31f8d-188">Choose **Settings**.</span></span>

3. <span data-ttu-id="31f8d-189">[全般高度 **な**  >  **機能] に移動** し、タンパープロテクションを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="31f8d-189">Go to **General** > **Advanced features**, and then turn tamper protection on.</span></span>

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a><span data-ttu-id="31f8d-190">Intune を使用して組織の改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="31f8d-190">Manage tamper protection for your organization using Intune</span></span>

<span data-ttu-id="31f8d-191">組織のセキュリティ チームの一員であり、サブスクリプションに[Intune](/intune/fundamentals/what-is-intune)が含まれる場合は、Microsoft エンドポイント マネージャー 管理センター ( ) で組織の改ざん防止をオン (またはオフ) にできます [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="31f8d-191">If you are part of your organization's security team, and your subscription includes [Intune](/intune/fundamentals/what-is-intune), you can turn tamper protection on (or off) for your organization in the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)).</span></span> <span data-ttu-id="31f8d-192">タンパープロテクションの設定を微調整する場合は、Intune を使用します。</span><span class="sxs-lookup"><span data-stu-id="31f8d-192">Use Intune when you want to fine-tune tamper protection settings.</span></span> <span data-ttu-id="31f8d-193">たとえば、一部のデバイスでタンパープロテクションを有効にするが、すべてではない場合は、Intune を使用します。</span><span class="sxs-lookup"><span data-stu-id="31f8d-193">For example, if you want to enable tamper protection on some devices, but not all, use Intune.</span></span>

### <a name="requirements-for-managing-tamper-protection-in-intune"></a><span data-ttu-id="31f8d-194">Intune でタンパープロテクションを管理するための要件</span><span class="sxs-lookup"><span data-stu-id="31f8d-194">Requirements for managing tamper protection in Intune</span></span>

- <span data-ttu-id="31f8d-195">グローバル管理者、セキュリティ [管理者、](/microsoft-365/security/defender-endpoint/assign-portal-access)セキュリティ操作など、適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="31f8d-195">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="31f8d-196">組織は Intune を [使用してデバイスを管理します](/intune/fundamentals/what-is-device-management)。</span><span class="sxs-lookup"><span data-stu-id="31f8d-196">Your organization uses [Intune to manage devices](/intune/fundamentals/what-is-device-management).</span></span> <span data-ttu-id="31f8d-197">([Intune ライセンスが](/intune/fundamentals/licenses)必要です。Intune は、次のMicrosoft 365 E5)に含まれます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-197">([Intune licenses](/intune/fundamentals/licenses) are required; Intune is included in Microsoft 365 E5.)</span></span>

- <span data-ttu-id="31f8d-198">デバイスWindows OS [1709、1803、1809](/windows/release-health/status-windows-10-1709)以降Windows 10[](/windows/release-health/status-windows-10-1809-and-windows-server-2019)実行している必要があります。 [](/windows/release-health/status-windows-10-1803)</span><span class="sxs-lookup"><span data-stu-id="31f8d-198">Your Windows devices must be running Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) or later.</span></span> <span data-ttu-id="31f8d-199">(リリースの詳細については、「リリース情報Windows 10[参照してください](/windows/release-health/release-information)。)</span><span class="sxs-lookup"><span data-stu-id="31f8d-199">(For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).)</span></span>

- <span data-ttu-id="31f8d-200">セキュリティ インテリジェンスがバージョン 1.287.60.0 (または上記) に更新された場合は、Windowsセキュリティを使用している必要があります。 [](https://www.microsoft.com/wdsi/definitions)</span><span class="sxs-lookup"><span data-stu-id="31f8d-200">You must be using Windows security with [security intelligence](https://www.microsoft.com/wdsi/definitions) updated to version 1.287.60.0 (or above).</span></span>

- <span data-ttu-id="31f8d-201">デバイスでマルウェア対策プラットフォーム バージョン 4.18.1906.3 (以上) とマルウェア対策エンジン バージョン 1.1.15500.X (以上) を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="31f8d-201">Your devices must be using anti-malware platform version 4.18.1906.3 (or above) and anti-malware engine version 1.1.15500.X (or above).</span></span> <span data-ttu-id="31f8d-202">([更新プログラムMicrosoft Defender ウイルス対策管理し、基準計画を適用](manage-updates-baselines-microsoft-defender-antivirus.md)します。)</span><span class="sxs-lookup"><span data-stu-id="31f8d-202">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

### <a name="turn-tamper-protection-on-or-off-in-intune"></a><span data-ttu-id="31f8d-203">Intune でタンパープロテクションをオン (またはオフ) にする</span><span class="sxs-lookup"><span data-stu-id="31f8d-203">Turn tamper protection on (or off) in Intune</span></span>

![Intune で改ざん防止を有効にする](images/turnontamperprotect-MEM.png)

1. <span data-ttu-id="31f8d-205">管理センターの[Microsoft エンドポイント マネージャーに移動し](https://endpoint.microsoft.com)、仕事または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="31f8d-205">Go to the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="31f8d-206">[**デバイス**  >  **構成プロファイル] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="31f8d-206">Select **Devices** > **Configuration Profiles**.</span></span>

3. <span data-ttu-id="31f8d-207">次の設定を含むプロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="31f8d-207">Create a profile that includes the following settings:</span></span>

    - <span data-ttu-id="31f8d-208">**プラットフォーム: Windows 10以降**</span><span class="sxs-lookup"><span data-stu-id="31f8d-208">**Platform: Windows 10 and later**</span></span>
    - <span data-ttu-id="31f8d-209">**プロファイルの種類: エンドポイント保護**</span><span class="sxs-lookup"><span data-stu-id="31f8d-209">**Profile type: Endpoint protection**</span></span>
    - <span data-ttu-id="31f8d-210">**カテゴリ: Microsoft Defender セキュリティ センター**</span><span class="sxs-lookup"><span data-stu-id="31f8d-210">**Category: Microsoft Defender Security Center**</span></span>
    - <span data-ttu-id="31f8d-211">**タンパープロテクション: 有効**</span><span class="sxs-lookup"><span data-stu-id="31f8d-211">**Tamper Protection: Enabled**</span></span>

4. <span data-ttu-id="31f8d-212">プロファイルを 1 つ以上のグループに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="31f8d-212">Assign the profile to one or more groups.</span></span>

### <a name="are-you-using-windows-server-2016-or-windows-version-1709-1803-or-1809"></a><span data-ttu-id="31f8d-213">バージョン 1709 Windows Server 2016 1803、または 1809 Windowsバージョンを使用していますか?</span><span class="sxs-lookup"><span data-stu-id="31f8d-213">Are you using Windows Server 2016, or Windows version 1709, 1803, or 1809?</span></span>

<span data-ttu-id="31f8d-214">Windows Server 2016、Windows 10 バージョン 1709、1803、[または 1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)を使用している場合は、Windows セキュリティ アプリにタンパープロテクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-214">If you are using Windows Server 2016, Windows 10 version 1709, 1803, or [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), you won't see **Tamper Protection** in the Windows Security app.</span></span> <span data-ttu-id="31f8d-215">代わりに、PowerShell を使用して、改ざん防止が有効になっているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-215">Instead, you can use PowerShell to determine whether tamper protection is enabled.</span></span> 
   
<span data-ttu-id="31f8d-216">このWindows Server 2016、設定保護が有効になっていると、リアルタイム保護の状態が正確に反映されません。</span><span class="sxs-lookup"><span data-stu-id="31f8d-216">On Windows Server 2016, the Settings app will not accurately reflect the status of real-time protection when tamper protection is enabled.</span></span>
   
#### <a name="use-powershell-to-determine-whether-tamper-protection-andor-real-time-protection-are-turned-on"></a><span data-ttu-id="31f8d-217">PowerShell を使用して、タンパープロテクションまたはリアルタイム保護が有効になっているかどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="31f8d-217">Use PowerShell to determine whether tamper protection and/or real-time protection are turned on</span></span>

1. <span data-ttu-id="31f8d-218">アプリを開Windows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="31f8d-218">Open the Windows PowerShell app.</span></span>

2. <span data-ttu-id="31f8d-219">[Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="31f8d-219">Use the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell cmdlet.</span></span>

3. <span data-ttu-id="31f8d-220">結果の一覧で、 を探します `IsTamperProtected` 。</span><span class="sxs-lookup"><span data-stu-id="31f8d-220">In the list of results, look for `IsTamperProtected`.</span></span> <span data-ttu-id="31f8d-221">(true の値は *、改* ざん防止が有効になっているという意味です。結果の一覧で、 を探します `RealTimeProtectionEnabled` 。</span><span class="sxs-lookup"><span data-stu-id="31f8d-221">(A value of *true* means tamper protection is enabled.) In the list of results, look for `RealTimeProtectionEnabled`.</span></span> <span data-ttu-id="31f8d-222">(true の値は、改ざん防止が有効になっているという意味です。</span><span class="sxs-lookup"><span data-stu-id="31f8d-222">(A value of true means tamper protection is enabled.)</span></span>

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a><span data-ttu-id="31f8d-223">Configuration Manager バージョン 2006 で組織の改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="31f8d-223">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>

<span data-ttu-id="31f8d-224">Configuration Manager のバージョン [2006](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)を使用している場合は、テナント接続というメソッドを使用して、Windows 10、Windows Server 2016、および Windows Server 2019 のタンパープロテクション設定を *管理できます*。</span><span class="sxs-lookup"><span data-stu-id="31f8d-224">If you're using [version 2006 of Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006), you can manage tamper protection settings on Windows 10, Windows Server 2016, and Windows Server 2019 by using a method called *tenant attach*.</span></span> <span data-ttu-id="31f8d-225">テナント接続を使用すると、オンプレミス専用の Configuration Manager デバイスを Microsoft エンドポイント マネージャー 管理センターに同期し、エンドポイント セキュリティ構成ポリシーを & デバイスのオンプレミス コレクションに配信できます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-225">Tenant attach enables you to sync your on-premises-only Configuration Manager devices into the Microsoft Endpoint Manager admin center, and then deliver endpoint security configuration policies to on-premises collections & devices.</span></span>

:::image type="content" source="images/win-security- exp-policy-endpt-security.png" alt-text="Windows セキュリティの経験エンドポイント マネージャー":::

> [!NOTE]
> <span data-ttu-id="31f8d-227">この手順を使用して、サーバー 2019 で実行されているデバイスWindows 10、Windowsを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-227">The procedure can be used to extend tamper protection to devices running Windows 10 and Windows Server 2019.</span></span> <span data-ttu-id="31f8d-228">この手順で説明されているリソースの前提条件と他の情報を必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="31f8d-228">Make sure to review the prerequisites and other information in the resources mentioned in this procedure.</span></span>

1. <span data-ttu-id="31f8d-229">テナント接続を設定します。</span><span class="sxs-lookup"><span data-stu-id="31f8d-229">Set up tenant attach.</span></span> <span data-ttu-id="31f8d-230">詳細については、「テナント接続Microsoft エンドポイント マネージャー:デバイスの同期と[デバイスの操作」を参照してください](/mem/configmgr/tenant-attach/device-sync-actions)。</span><span class="sxs-lookup"><span data-stu-id="31f8d-230">To learn more, see [Microsoft Endpoint Manager tenant attach: Device sync and device actions](/mem/configmgr/tenant-attach/device-sync-actions).</span></span>

2. <span data-ttu-id="31f8d-231">管理センター [でMicrosoft エンドポイント マネージャー[](https://go.microsoft.com/fwlink/?linkid=2109431)**エンドポイント** セキュリティ ウイルス対策] に移動し、[+ ポリシーの作成  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="31f8d-231">In the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Endpoint security** > **Antivirus**, and then choose **+ Create Policy**.</span></span><br/> 
   - <span data-ttu-id="31f8d-232">[プラットフォーム **] ボックスの** 一覧で、[Windows 10] **Windows (ConfigMgr) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="31f8d-232">In the **Platform** list, select **Windows 10 and Windows Server (ConfigMgr)**.</span></span>  
   - <span data-ttu-id="31f8d-233">[プロファイル]**ボックスの** 一覧で、[Windows セキュリティ **エクスペリエンス (プレビュー) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="31f8d-233">In the **Profile** list, select **Windows Security experience (preview)**.</span></span> <br/>

3. <span data-ttu-id="31f8d-234">デバイス コレクションにポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="31f8d-234">Deploy the policy to your device collection.</span></span>

### <a name="need-help-with-this-method"></a><span data-ttu-id="31f8d-235">このメソッドのヘルプが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="31f8d-235">Need help with this method?</span></span> 

<span data-ttu-id="31f8d-236">以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31f8d-236">See the following resources:</span></span>

- [<span data-ttu-id="31f8d-237">設定のWindows セキュリティエクスペリエンス プロファイルのMicrosoft Intune</span><span class="sxs-lookup"><span data-stu-id="31f8d-237">Settings for the Windows Security experience profile in Microsoft Intune</span></span>](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [<span data-ttu-id="31f8d-238">Tech Community ブログ: Configuration Manager テナント接続クライアントのタンパープロテクションの発表</span><span class="sxs-lookup"><span data-stu-id="31f8d-238">Tech Community Blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a><span data-ttu-id="31f8d-239">個々のデバイスで改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="31f8d-239">Manage tamper protection on an individual device</span></span>

> [!NOTE]
> <span data-ttu-id="31f8d-240">タンパープロテクション ブロックは、レジストリMicrosoft Defender ウイルス対策設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="31f8d-240">Tamper protection blocks attempts to modify Microsoft Defender Antivirus settings through the registry.</span></span>
>
> <span data-ttu-id="31f8d-241">改ざん防止がサード パーティのセキュリティ製品や、これらの設定を変更するエンタープライズ インストール スクリプトを妨げないよう **、Windows セキュリティ** に移動し、セキュリティ インテリジェンスをバージョン 1.287.60.0 以降に更新します。</span><span class="sxs-lookup"><span data-stu-id="31f8d-241">To help ensure that tamper protection doesn’t interfere with third-party security products or enterprise installation scripts that modify these settings, go to **Windows Security** and update **Security intelligence** to version 1.287.60.0 or later.</span></span> <span data-ttu-id="31f8d-242">(「セキュリティ [インテリジェンスの更新プログラム」を参照](https://www.microsoft.com/wdsi/definitions)してください。</span><span class="sxs-lookup"><span data-stu-id="31f8d-242">(See [Security intelligence updates](https://www.microsoft.com/wdsi/definitions).)</span></span>
>
> <span data-ttu-id="31f8d-243">この更新プログラムを作成すると、改ざん防止はレジストリ設定を保護し続け、ログはエラーを返さずに変更を試みる。</span><span class="sxs-lookup"><span data-stu-id="31f8d-243">Once you’ve made this update, tamper protection continues to protect your registry settings, and logs attempts to modify them without returning errors.</span></span>

<span data-ttu-id="31f8d-244">ホーム ユーザーである場合、またはセキュリティ チームが管理する設定の対象ではない場合は、Windows セキュリティ アプリを使用して改ざん防止を管理できます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-244">If you are a home user, or you are not subject to settings managed by a security team, you can use the Windows Security app to manage tamper protection.</span></span> <span data-ttu-id="31f8d-245">改ざん防止などのセキュリティ設定を変更するには、デバイスに適切な管理者アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="31f8d-245">You must have appropriate admin permissions on your device to do change security settings, such as tamper protection.</span></span>

<span data-ttu-id="31f8d-246">アプリに表示されるWindows セキュリティします。</span><span class="sxs-lookup"><span data-stu-id="31f8d-246">Here's what you see in the Windows Security app:</span></span>

![タンパープロテクションがオンWindows 10 Home](images/tamperprotectionturnedon.png)

1. <span data-ttu-id="31f8d-248">[スタート **] を選択** し、[セキュリティ] の入力 *を開始します*。</span><span class="sxs-lookup"><span data-stu-id="31f8d-248">Select **Start**, and start typing *Security*.</span></span> <span data-ttu-id="31f8d-249">検索結果で、[検索] を **Windows セキュリティ** します。</span><span class="sxs-lookup"><span data-stu-id="31f8d-249">In the search results, select **Windows Security**.</span></span>

2. <span data-ttu-id="31f8d-250">[**ウイルス対策&ウイルス**  >  **対策] を選択&の設定を選択します**。</span><span class="sxs-lookup"><span data-stu-id="31f8d-250">Select **Virus & threat protection** > **Virus & threat protection settings**.</span></span>

3. <span data-ttu-id="31f8d-251">タン **パープロテクションを** **On または** Off に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="31f8d-251">Set **Tamper Protection** to **On** or **Off**.</span></span>

## <a name="view-information-about-tampering-attempts"></a><span data-ttu-id="31f8d-252">改ざんの試行に関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="31f8d-252">View information about tampering attempts</span></span>

<span data-ttu-id="31f8d-253">改ざんの試みは、通常、より大きなサイバー攻撃を示します。</span><span class="sxs-lookup"><span data-stu-id="31f8d-253">Tampering attempts typically indicate bigger cyberattacks.</span></span> <span data-ttu-id="31f8d-254">悪いアクターは、セキュリティ設定を変更して、検出されない状態を維持します。</span><span class="sxs-lookup"><span data-stu-id="31f8d-254">Bad actors try to change security settings as a way to persist and stay undetected.</span></span> <span data-ttu-id="31f8d-255">組織のセキュリティ チームの一員である場合は、そのような試みについての情報を表示し、脅威を軽減するために適切なアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-255">If you're part of your organization's security team, you can view information about such attempts, and then take appropriate actions to mitigate threats.</span></span>

<span data-ttu-id="31f8d-256">改ざんの試行が検出されると、警告がメッセージ () で[Microsoft Defender セキュリティ センター](/microsoft-365/security/defender-endpoint/portal-overview)されます [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="31f8d-256">When a tampering attempt is detected, an alert is raised in the [Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/portal-overview) ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

![Microsoft Defender セキュリティ センター](images/tamperattemptalert.png)

<span data-ttu-id="31f8d-258">Microsoft Defender[エンドポイントでの検出と対応](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)高度[な](/microsoft-365/security/defender-endpoint/advanced-hunting-overview)ハンティング機能を使用して、セキュリティ運用チームはそのような試みを調査し、対処できます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-258">Using [endpoint detection and response](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) and [advanced hunting](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) capabilities in Microsoft Defender for Endpoint, your security operations team can investigate and address such attempts.</span></span>

## <a name="review-your-security-recommendations"></a><span data-ttu-id="31f8d-259">セキュリティに関する推奨事項を確認する</span><span class="sxs-lookup"><span data-stu-id="31f8d-259">Review your security recommendations</span></span>

<span data-ttu-id="31f8d-260">タンパープロテクションは [、脅威&管理機能と](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) 統合されます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-260">Tamper protection integrates with [Threat & Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) capabilities.</span></span> <span data-ttu-id="31f8d-261">[セキュリティに関する推奨事項には](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) 、改ざん防止が有効になっていることを確認する方法が含まれます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-261">[Security recommendations](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) include making sure tamper protection is turned on.</span></span> <span data-ttu-id="31f8d-262">たとえば、改ざん時に検索 *できます*。</span><span class="sxs-lookup"><span data-stu-id="31f8d-262">For example, you can search on *tamper*.</span></span> <span data-ttu-id="31f8d-263">結果では、[タンパープロテクションを **有効** にする] を選択して詳細を確認し、有効にできます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-263">In the results, you can select **Turn on Tamper Protection** to learn more and turn it on.</span></span>

![改ざん防止を有効にする](images/tamperprotectsecurityrecos.png)

<span data-ttu-id="31f8d-265">脅威の脆弱性管理の詳細については&の「脅威の脆弱性&[管理」を参照Microsoft Defender セキュリティ センター。](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="31f8d-265">To learn more about Threat & Vulnerability Management, see [Threat & Vulnerability Management in Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="31f8d-266">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="31f8d-266">Frequently asked questions</span></span>

### <a name="to-which-windows-os-versions-is-configuring-tamper-protection-is-applicable"></a><span data-ttu-id="31f8d-267">改ざんWindows構成している OS のバージョンは、どのバージョンに適用されますか?</span><span class="sxs-lookup"><span data-stu-id="31f8d-267">To which Windows OS versions is configuring tamper protection is applicable?</span></span>

<span data-ttu-id="31f8d-268">Windows 10OS [1709](/windows/release-health/status-windows-10-1709)、 [1803](/windows/release-health/status-windows-10-1803)、 [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)以降と[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span><span class="sxs-lookup"><span data-stu-id="31f8d-268">Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), or later together with [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

<span data-ttu-id="31f8d-269">Configuration Manager バージョン 2006 をテナント接続で使用している場合は、改ざん防止をサーバー 2019 Windowsできます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-269">If you are using Configuration Manager, version 2006, with tenant attach, tamper protection can be extended to Windows Server 2019.</span></span> <span data-ttu-id="31f8d-270">「 [テナント接続: 管理センターからエンドポイント セキュリティ](/mem/configmgr/tenant-attach/deploy-antivirus-policy)ウイルス対策ポリシーを作成して展開する (プレビュー)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="31f8d-270">See [Tenant attach: Create and deploy endpoint security Antivirus policy from the admin center (preview)](/mem/configmgr/tenant-attach/deploy-antivirus-policy).</span></span>

### <a name="will-tamper-protection-have-any-impact-on-third-party-antivirus-registration"></a><span data-ttu-id="31f8d-271">改ざん防止はサードパーティのウイルス対策登録に影響しますか?</span><span class="sxs-lookup"><span data-stu-id="31f8d-271">Will tamper protection have any impact on third-party antivirus registration?</span></span>

<span data-ttu-id="31f8d-272">いいえ。</span><span class="sxs-lookup"><span data-stu-id="31f8d-272">No.</span></span> <span data-ttu-id="31f8d-273">サードパーティのウイルス対策製品は、引き続きアプリケーションにWindows セキュリティされます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-273">Third-party antivirus offerings will continue to register with the Windows Security application.</span></span>

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a><span data-ttu-id="31f8d-274">デバイスでMicrosoft Defender ウイルス対策がアクティブではない場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="31f8d-274">What happens if Microsoft Defender Antivirus is not active on a device?</span></span>

<span data-ttu-id="31f8d-275">Microsoft Defender for Endpoint にオンボードされているデバイスには、パッシブ Microsoft Defender ウイルス対策が実行されます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-275">Devices that are onboarded to Microsoft Defender for Endpoint will have Microsoft Defender Antivirus running in passive mode.</span></span> <span data-ttu-id="31f8d-276">改ざん防止は、サービスとその機能を引き続き保護します。</span><span class="sxs-lookup"><span data-stu-id="31f8d-276">Tamper protection will continue to protect the service and its features.</span></span> 

### <a name="how-can-i-turn-tamper-protection-onoff"></a><span data-ttu-id="31f8d-277">改ざん防止のオン/オフを切り替えますか?</span><span class="sxs-lookup"><span data-stu-id="31f8d-277">How can I turn tamper protection on/off?</span></span>

<span data-ttu-id="31f8d-278">ホーム ユーザーの場合は、「個々のデバイスで [タンパープロテクションを管理する」を参照してください](#manage-tamper-protection-on-an-individual-device)。</span><span class="sxs-lookup"><span data-stu-id="31f8d-278">If you are a home user, see [Manage tamper protection on an individual device](#manage-tamper-protection-on-an-individual-device).</span></span>

<span data-ttu-id="31f8d-279">Microsoft Defender for [Endpoint](/microsoft-365/security/defender-endpoint)を使用している組織の場合は、他のエンドポイント保護機能を管理する方法と同様に、Intune でタンパープロテクションを管理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="31f8d-279">If you are an organization using [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint), you should be able to manage tamper protection in Intune similar to how you manage other endpoint protection features.</span></span> <span data-ttu-id="31f8d-280">この記事の以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31f8d-280">See the following sections of this article:</span></span> 

- [<span data-ttu-id="31f8d-281">Intune を使用して改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="31f8d-281">Manage tamper protection using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune)
- [<span data-ttu-id="31f8d-282">Configuration Manager バージョン 2006 を使用して改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="31f8d-282">Manage tamper protection using Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [<span data-ttu-id="31f8d-283">アプリケーションを使用して改ざん防止を管理Microsoft Defender セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="31f8d-283">Manage tamper protection using the Microsoft Defender Security Center</span></span>](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) 

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-through-my-group-policy"></a><span data-ttu-id="31f8d-284">Intune でタンパープロテクションを構成すると、グループ ポリシーを通Microsoft Defender ウイルス対策管理する方法にどのような影響がありますか?</span><span class="sxs-lookup"><span data-stu-id="31f8d-284">How does configuring tamper protection in Intune affect how I manage Microsoft Defender Antivirus through my group policy?</span></span>

<span data-ttu-id="31f8d-285">通常のグループ ポリシーはタンパープロテクションには適用されません。タンパープロテクションがオンの場合、Microsoft Defender ウイルス対策設定への変更は無視されます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-285">Your regular group policy doesn’t apply to tamper protection, and changes to Microsoft Defender Antivirus settings are ignored when tamper protection is on.</span></span> 

### <a name="for-microsoft-defender-for-endpoint-is-configuring-tamper-protection-in-intune-targeted-to-the-entire-organization-only"></a><span data-ttu-id="31f8d-286">Microsoft Defender for Endpoint の場合、Intune でタンパープロテクションを組織全体のみを対象に構成していますか?</span><span class="sxs-lookup"><span data-stu-id="31f8d-286">For Microsoft Defender for Endpoint, is configuring tamper protection in Intune targeted to the entire organization only?</span></span>

<span data-ttu-id="31f8d-287">Intune またはアプリでタンパー Microsoft エンドポイント マネージャーを構成するには、組織全体と特定のデバイスとユーザー グループを対象とすることができます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-287">Configuring tamper protection in Intune or Microsoft Endpoint Manager can be targeted to your entire organization and to specific devices and user groups.</span></span>

### <a name="can-i-configure-tamper-protection-in-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="31f8d-288">タンパープロテクションを構成Microsoft Endpoint Configuration Manager?</span><span class="sxs-lookup"><span data-stu-id="31f8d-288">Can I configure Tamper Protection in Microsoft Endpoint Configuration Manager?</span></span>

<span data-ttu-id="31f8d-289">テナント接続を使用している場合は、テナント接続Microsoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="31f8d-289">If you are using tenant attach, you can use Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="31f8d-290">以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="31f8d-290">See the following resources:</span></span>
- [<span data-ttu-id="31f8d-291">Configuration Manager バージョン 2006 で組織の改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="31f8d-291">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [<span data-ttu-id="31f8d-292">Tech Communityブログ: Configuration Manager テナント接続クライアントのタンパープロテクションの発表</span><span class="sxs-lookup"><span data-stu-id="31f8d-292">Tech Community blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a><span data-ttu-id="31f8d-293">E3 登録Windowsがあります。</span><span class="sxs-lookup"><span data-stu-id="31f8d-293">I have the Windows E3 enrollment.</span></span> <span data-ttu-id="31f8d-294">Intune でタンパープロテクションの構成を使用できますか?</span><span class="sxs-lookup"><span data-stu-id="31f8d-294">Can I use configuring tamper protection in Intune?</span></span>

<span data-ttu-id="31f8d-295">現在、Intune でタンパープロテクションを構成できるのは [、Microsoft Defender for Endpoint をお持ちのお客様のみです](/microsoft-365/security/defender-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="31f8d-295">Currently, configuring tamper protection in Intune is only available for customers who have [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a><span data-ttu-id="31f8d-296">デバイスでタンパープロテクションが有効になっているときに Intune、Microsoft Endpoint Configuration Manager、および Windows 管理インストルメンテーションで Microsoft Defender for Endpoint の設定を変更すると、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="31f8d-296">What happens if I try to change Microsoft Defender for Endpoint settings in Intune, Microsoft Endpoint Configuration Manager, and Windows Management Instrumentation when Tamper Protection is enabled on a device?</span></span>

<span data-ttu-id="31f8d-297">改ざん防止によって保護されている機能を変更できない。このような変更要求は無視されます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-297">You won’t be able to change the features that are protected by tamper protection; such change requests are ignored.</span></span>

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a><span data-ttu-id="31f8d-298">エンタープライズ顧客です。</span><span class="sxs-lookup"><span data-stu-id="31f8d-298">I’m an enterprise customer.</span></span> <span data-ttu-id="31f8d-299">ローカル管理者は、デバイスの改ざん防止を変更できますか?</span><span class="sxs-lookup"><span data-stu-id="31f8d-299">Can local admins change tamper protection on their devices?</span></span>

<span data-ttu-id="31f8d-300">いいえ。</span><span class="sxs-lookup"><span data-stu-id="31f8d-300">No.</span></span> <span data-ttu-id="31f8d-301">ローカル管理者は、改ざん防止の設定を変更または変更できません。</span><span class="sxs-lookup"><span data-stu-id="31f8d-301">Local admins cannot change or modify tamper protection settings.</span></span>

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a><span data-ttu-id="31f8d-302">デバイスが Microsoft Defender for Endpoint にオンボードされ、オフボード状態に入った場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="31f8d-302">What happens if my device is onboarded with Microsoft Defender for Endpoint and then goes into an off-boarded state?</span></span>

<span data-ttu-id="31f8d-303">デバイスが Microsoft Defender for Endpoint からオフボードされている場合、タンパープロテクションが有効になります。これは管理されていないデバイスの既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="31f8d-303">If a device is off-boarded from Microsoft Defender for Endpoint, tamper protection is turned on, which is the default state for unmanaged devices.</span></span> 

### <a name="will-there-be-an-alert-about-tamper-protection-status-changing-in-the-microsoft-defender-security-center"></a><span data-ttu-id="31f8d-304">改ざん防止の状態が変更された場合、改ざん防止の状態に関する警告が表示Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="31f8d-304">Will there be an alert about tamper protection status changing in the Microsoft Defender Security Center?</span></span>

<span data-ttu-id="31f8d-305">はい。</span><span class="sxs-lookup"><span data-stu-id="31f8d-305">Yes.</span></span> <span data-ttu-id="31f8d-306">アラートは [アラート] の下 [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) に **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="31f8d-306">The alert is shown in [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) under **Alerts**.</span></span>

<span data-ttu-id="31f8d-307">セキュリティ運用チームは、次の例のような検索クエリも使用できます。</span><span class="sxs-lookup"><span data-stu-id="31f8d-307">Your security operations team can also use hunting queries, such as the following example:</span></span>

`DeviceAlertEvents | where Title == "Tamper Protection bypass"`

<span data-ttu-id="31f8d-308">[改ざんの試行に関する情報を表示します](#view-information-about-tampering-attempts)。</span><span class="sxs-lookup"><span data-stu-id="31f8d-308">[View information about tampering attempts](#view-information-about-tampering-attempts).</span></span>

## <a name="see-also"></a><span data-ttu-id="31f8d-309">関連項目</span><span class="sxs-lookup"><span data-stu-id="31f8d-309">See also</span></span>

[<span data-ttu-id="31f8d-310">デバイスを使用Windows PC のセキュリティをEndpoint ProtectionするMicrosoft Intune</span><span class="sxs-lookup"><span data-stu-id="31f8d-310">Help secure Windows PCs with Endpoint Protection for Microsoft Intune</span></span>](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[<span data-ttu-id="31f8d-311">Microsoft Defender for Endpoint の概要を確認する</span><span class="sxs-lookup"><span data-stu-id="31f8d-311">Get an overview of Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint)

[<span data-ttu-id="31f8d-312">ベストな組み合わせ: Microsoft Defender Antivirus および Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="31f8d-312">Better together: Microsoft Defender Antivirus and Microsoft Defender for Endpoint</span></span>](why-use-microsoft-defender-antivirus.md)
