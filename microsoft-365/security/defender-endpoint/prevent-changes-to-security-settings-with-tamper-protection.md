---
title: 改ざん防止でセキュリティ設定を保護する
ms.reviewer: shwjha, hayhov
manager: dansimp
description: タンパープロテクションを使用して、悪意のあるアプリが重要なセキュリティ設定を変更するのを防ぐ。
keywords: マルウェア、防御者、ウイルス対策、改ざん防止
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 84864965d7a18902a01307c1dcf373fa7c0534e8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765577"
---
# <a name="protect-security-settings-with-tamper-protection"></a><span data-ttu-id="a2513-104">改ざん防止でセキュリティ設定を保護する</span><span class="sxs-lookup"><span data-stu-id="a2513-104">Protect security settings with tamper protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a2513-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a2513-105">**Applies to:**</span></span>

- [<span data-ttu-id="a2513-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a2513-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a2513-107">タンパープロテクションは、次のいずれかのバージョンの Windows を実行しているデバイスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2513-107">Tamper protection is available for devices that are running one of the following versions of Windows:</span></span>

- <span data-ttu-id="a2513-108">Windows 10</span><span class="sxs-lookup"><span data-stu-id="a2513-108">Windows 10</span></span>
- <span data-ttu-id="a2513-109">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="a2513-109">Windows Server 2019</span></span>
- <span data-ttu-id="a2513-110">Windows Server バージョン 1803 以降</span><span class="sxs-lookup"><span data-stu-id="a2513-110">Windows Server, version 1803 or later</span></span>
- <span data-ttu-id="a2513-111">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="a2513-111">Windows Server 2016</span></span>

## <a name="overview"></a><span data-ttu-id="a2513-112">概要</span><span class="sxs-lookup"><span data-stu-id="a2513-112">Overview</span></span>

<span data-ttu-id="a2513-113">一部の種類のサイバー攻撃では、悪いアクターがコンピューターでウイルス対策保護などのセキュリティ機能を無効にしようとします。</span><span class="sxs-lookup"><span data-stu-id="a2513-113">During some kinds of cyber attacks, bad actors try to disable security features, such as anti-virus protection, on your machines.</span></span> <span data-ttu-id="a2513-114">悪いアクターは、データに簡単にアクセスしたり、マルウェアをインストールしたり、データ、ID、デバイスを悪用したりするために、セキュリティ機能を無効にしています。</span><span class="sxs-lookup"><span data-stu-id="a2513-114">Bad actors like to disable your security features to get easier access to your data, to install malware, or to otherwise exploit your data, identity, and devices.</span></span> <span data-ttu-id="a2513-115">タンパープロテクションは、このような事態が発生するのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a2513-115">Tamper protection helps prevent these kinds of things from occurring.</span></span>

<span data-ttu-id="a2513-116">タンパープロテクションを使用すると、悪意のあるアプリは次のようなアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a2513-116">With tamper protection, malicious apps are prevented from taking actions such as:</span></span>

- <span data-ttu-id="a2513-117">ウイルスおよび脅威の保護の無効化</span><span class="sxs-lookup"><span data-stu-id="a2513-117">Disabling virus and threat protection</span></span>
- <span data-ttu-id="a2513-118">リアルタイム保護の無効化</span><span class="sxs-lookup"><span data-stu-id="a2513-118">Disabling real-time protection</span></span>
- <span data-ttu-id="a2513-119">動作の監視の無効化</span><span class="sxs-lookup"><span data-stu-id="a2513-119">Turning off behavior monitoring</span></span>
- <span data-ttu-id="a2513-120">ウイルス対策(IOfficeAntivirus (IOAV) など) の無効化</span><span class="sxs-lookup"><span data-stu-id="a2513-120">Disabling antivirus (such as IOfficeAntivirus (IOAV))</span></span>
- <span data-ttu-id="a2513-121">クラウド配信の保護の無効化</span><span class="sxs-lookup"><span data-stu-id="a2513-121">Disabling cloud-delivered protection</span></span>
- <span data-ttu-id="a2513-122">セキュリティ インテリジェンスの更新プログラムの削除</span><span class="sxs-lookup"><span data-stu-id="a2513-122">Removing security intelligence updates</span></span>

### <a name="how-it-works"></a><span data-ttu-id="a2513-123">メカニズム</span><span class="sxs-lookup"><span data-stu-id="a2513-123">How it works</span></span>

<span data-ttu-id="a2513-124">タンパープロテクションは基本的に Microsoft Defender ウイルス対策をロックし、次のようなアプリやメソッドを通じてセキュリティ設定が変更されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="a2513-124">Tamper protection essentially locks Microsoft Defender Antivirus and prevents your security settings from being changed through apps and methods such as:</span></span>

- <span data-ttu-id="a2513-125">Windows デバイスのレジストリ エディターで設定を構成する</span><span class="sxs-lookup"><span data-stu-id="a2513-125">Configuring settings in Registry Editor on your Windows device</span></span>
- <span data-ttu-id="a2513-126">PowerShell コマンドレットによる設定の変更</span><span class="sxs-lookup"><span data-stu-id="a2513-126">Changing settings through PowerShell cmdlets</span></span>
- <span data-ttu-id="a2513-127">グループ ポリシーによるセキュリティ設定の編集または削除</span><span class="sxs-lookup"><span data-stu-id="a2513-127">Editing or removing security settings through group policies</span></span>

<span data-ttu-id="a2513-128">改ざん防止では、セキュリティ設定を表示できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2513-128">Tamper protection doesn't prevent you from viewing your security settings.</span></span> <span data-ttu-id="a2513-129">また、改ざん防止は、サードパーティのウイルス対策アプリが Windows セキュリティ アプリに登録する方法には影響を与えかねない。</span><span class="sxs-lookup"><span data-stu-id="a2513-129">And, tamper protection doesn't affect how third-party antivirus apps register with the Windows Security app.</span></span> <span data-ttu-id="a2513-130">組織で Windows 10 Enterprise E5 を使用している場合、個々のユーザーは改ざん防止設定を変更できます。このような場合、改ざん防止はセキュリティ チームによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="a2513-130">If your organization is using Windows 10 Enterprise E5, individual users can't change the tamper protection setting; in those cases, tamper protection is managed by your security team.</span></span>

### <a name="what-do-you-want-to-do"></a><span data-ttu-id="a2513-131">目的に合ったトピックをクリックしてください</span><span class="sxs-lookup"><span data-stu-id="a2513-131">What do you want to do?</span></span>

| <span data-ttu-id="a2513-132">このタスクを実行するには...</span><span class="sxs-lookup"><span data-stu-id="a2513-132">To perform this task...</span></span> | <span data-ttu-id="a2513-133">このセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2513-133">See this section...</span></span> |
|:---|:---|
| <span data-ttu-id="a2513-134">Microsoft Defender セキュリティ センターでタンパープロテクションをオン (またはオフ) にする</span><span class="sxs-lookup"><span data-stu-id="a2513-134">Turn tamper protection on (or off) in the Microsoft Defender Security Center</span></span> <p><span data-ttu-id="a2513-135">テナント全体の改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="a2513-135">Manage tamper protection across your tenant</span></span> | [<span data-ttu-id="a2513-136">Microsoft Defender セキュリティ センターを使用して組織の改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="a2513-136">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) |
| <span data-ttu-id="a2513-137">Intune を使用して組織のすべてまたは一部のタンパープロテクションをオン (またはオフ) にする</span><span class="sxs-lookup"><span data-stu-id="a2513-137">Turn tamper protection on (or off) for all or part of your organization using Intune</span></span> <p><span data-ttu-id="a2513-138">組織内の改ざん防止設定を微調整する</span><span class="sxs-lookup"><span data-stu-id="a2513-138">Fine-tune tamper protection settings in your organization</span></span> | [<span data-ttu-id="a2513-139">Intune を使用して組織の改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="a2513-139">Manage tamper protection for your organization using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune) |
| <span data-ttu-id="a2513-140">Configuration Manager を使用して組織の改ざん防止を有効 (または無効にする)</span><span class="sxs-lookup"><span data-stu-id="a2513-140">Turn tamper protection on (or off) for your organization with Configuration Manager</span></span> | [<span data-ttu-id="a2513-141">Configuration Manager バージョン 2006 でテナント接続を使用して組織の改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="a2513-141">Manage tamper protection for your organization using tenant attach with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006) |
| <span data-ttu-id="a2513-142">個々のデバイスのタンパープロテクションをオン (またはオフ) にする</span><span class="sxs-lookup"><span data-stu-id="a2513-142">Turn tamper protection on (or off) for an individual device</span></span> | [<span data-ttu-id="a2513-143">個々のデバイスで改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="a2513-143">Manage tamper protection on an individual device</span></span>](#manage-tamper-protection-on-an-individual-device) |
| <span data-ttu-id="a2513-144">デバイスでの改ざんの試みについての詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="a2513-144">View details about tampering attempts on devices</span></span> | [<span data-ttu-id="a2513-145">改ざんの試行に関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="a2513-145">View information about tampering attempts</span></span>](#view-information-about-tampering-attempts) |
| <span data-ttu-id="a2513-146">セキュリティに関する推奨事項を確認する</span><span class="sxs-lookup"><span data-stu-id="a2513-146">Review your security recommendations</span></span> | [<span data-ttu-id="a2513-147">セキュリティに関する推奨事項を確認する</span><span class="sxs-lookup"><span data-stu-id="a2513-147">Review security recommendations</span></span>](#review-your-security-recommendations) |
| <span data-ttu-id="a2513-148">よく寄せられる質問 (FAQ) の一覧を確認する</span><span class="sxs-lookup"><span data-stu-id="a2513-148">Review the list of frequently asked questions (FAQs)</span></span> | [<span data-ttu-id="a2513-149">FAQ を参照する</span><span class="sxs-lookup"><span data-stu-id="a2513-149">Browse the FAQs</span></span>](#view-information-about-tampering-attempts) |

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center"></a><span data-ttu-id="a2513-150">Microsoft Defender セキュリティ センターを使用して組織の改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="a2513-150">Manage tamper protection for your organization using the Microsoft Defender Security Center</span></span>

<span data-ttu-id="a2513-151">Microsoft Defender セキュリティ センター ( ) を使用して、テナントのタンパープロテクションを有効または無効にできます [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="a2513-151">Tamper protection can be turned on or off for your tenant using the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span> <span data-ttu-id="a2513-152">以下に注意点を示します。</span><span class="sxs-lookup"><span data-stu-id="a2513-152">Here are a few points to keep in mind:</span></span>

- <span data-ttu-id="a2513-153">現在、Microsoft Defender セキュリティ センターでタンパープロテクションを管理するオプションは、新しい展開では既定でオンになっています。</span><span class="sxs-lookup"><span data-stu-id="a2513-153">Currently, the option to manage tamper protection in the Microsoft Defender Security Center is on by default for new deployments.</span></span> <span data-ttu-id="a2513-154">既存の展開では、改ざん防止はオプトインベースで利用できます。近い将来、この方法を既定の方法にする予定です。</span><span class="sxs-lookup"><span data-stu-id="a2513-154">For existing deployments, tamper protection is available on an opt-in basis, with plans to make this the default method in the near future.</span></span> <span data-ttu-id="a2513-155">(オプトインするには、Microsoft Defender セキュリティ センターで、[設定] を **選択します。**  > **高度な機能**  > **タンパープロテクション**.)</span><span class="sxs-lookup"><span data-stu-id="a2513-155">(To opt in, in the Microsoft Defender Security Center, choose **Settings** > **Advanced features** > **Tamper protection**.)</span></span> 

- <span data-ttu-id="a2513-156">Microsoft Defender セキュリティ センターを使用してタンパープロテクションを管理する場合は、Intune またはテナント接続方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2513-156">When you use the Microsoft Defender Security Center to manage tamper protection, you do not have to use Intune or the tenant attach method.</span></span>

- <span data-ttu-id="a2513-157">Microsoft Defender セキュリティ センターで改ざん防止を管理する場合、この設定はテナント全体に適用され、Windows 10、Windows Server 2016、または Windows Server 2019 を実行しているすべてのデバイスに影響を与えます。</span><span class="sxs-lookup"><span data-stu-id="a2513-157">When you manage tamper protection in the Microsoft Defender Security Center, the setting is applied tenant wide, affecting all of your devices that are running Windows 10, Windows Server 2016, or Windows Server 2019.</span></span> <span data-ttu-id="a2513-158">タンパープロテクションを微調整するには (一部のデバイスではタンパープロテクションをオンにし、他のデバイスではオフにするなど [)、Intune](#manage-tamper-protection-for-your-organization-using-intune) または Configuration Manager をテナント接続で [使用します](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)。</span><span class="sxs-lookup"><span data-stu-id="a2513-158">To fine-tune tamper protection (such as having tamper protection on for some devices but off for others), use either [Intune](#manage-tamper-protection-for-your-organization-using-intune) or [Configuration Manager with tenant attach](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006).</span></span>

- <span data-ttu-id="a2513-159">ハイブリッド環境がある場合、Intune で構成されたタンパープロテクション設定は、Microsoft Defender セキュリティ センターで構成された設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="a2513-159">If you have a hybrid environment, tamper protection settings configured in Intune take precedence over settings configured in the Microsoft Defender Security Center.</span></span> 

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-defender-security-center"></a><span data-ttu-id="a2513-160">Microsoft Defender セキュリティ センターでタンパープロテクションを管理するための要件</span><span class="sxs-lookup"><span data-stu-id="a2513-160">Requirements for managing tamper protection in the Microsoft Defender Security Center</span></span>

- <span data-ttu-id="a2513-161">グローバル管理者、セキュリティ [管理者、](/microsoft-365/security/defender-endpoint/assign-portal-access)セキュリティ操作など、適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a2513-161">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="a2513-162">Windows デバイスは、次のいずれかのバージョンの Windows を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2513-162">Your Windows devices must be running one of the following versions of Windows:</span></span>
   - <span data-ttu-id="a2513-163">Windows 10</span><span class="sxs-lookup"><span data-stu-id="a2513-163">Windows 10</span></span>
   - [<span data-ttu-id="a2513-164">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="a2513-164">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)
   - <span data-ttu-id="a2513-165">Windows Server バージョン [1803](/windows/release-health/status-windows-10-1803) 以降</span><span class="sxs-lookup"><span data-stu-id="a2513-165">Windows Server, version [1803](/windows/release-health/status-windows-10-1803) or later</span></span>
   - [<span data-ttu-id="a2513-166">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="a2513-166">Windows Server 2016</span></span>](/windows-server/get-started/whats-new-in-windows-server-2016)
   - <span data-ttu-id="a2513-167">リリースの詳細については [、「Windows 10 リリース情報」を参照してください](/windows/release-health/release-information)。</span><span class="sxs-lookup"><span data-stu-id="a2513-167">For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).</span></span>

- <span data-ttu-id="a2513-168">デバイスは、Microsoft [Defender for Endpoint にオンボードされている必要があります](/microsoft-365/security/defender-endpoint/onboarding)。</span><span class="sxs-lookup"><span data-stu-id="a2513-168">Your devices must be [onboarded to Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/onboarding).</span></span>

- <span data-ttu-id="a2513-169">デバイスでマルウェア対策プラットフォーム バージョン 4.18.2010.7 (以上) とマルウェア対策エンジン バージョン 1.1.17600.5 (以上) を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2513-169">Your devices must be using anti-malware platform version 4.18.2010.7 (or above) and anti-malware engine version 1.1.17600.5 (or above).</span></span> <span data-ttu-id="a2513-170">([Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用](manage-updates-baselines-microsoft-defender-antivirus.md)します。)</span><span class="sxs-lookup"><span data-stu-id="a2513-170">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

- <span data-ttu-id="a2513-171">[クラウドによる保護を](enable-cloud-protection-microsoft-defender-antivirus.md) 有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2513-171">[Cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be turned on.</span></span>

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-defender-security-center"></a><span data-ttu-id="a2513-172">Microsoft Defender セキュリティ センターでタンパープロテクションをオン (またはオフ) にする</span><span class="sxs-lookup"><span data-stu-id="a2513-172">Turn tamper protection on (or off) in the Microsoft Defender Security Center</span></span> 

![Microsoft Defender セキュリティ センターでタンパープロテクションを有効にする](images/mde-turn-tamperprotect-on.png)

1. <span data-ttu-id="a2513-174">Microsoft Defender セキュリティ センター ( ) に移動 [https://securitycenter.windows.com](https://securitycenter.windows.com) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="a2513-174">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="a2513-175">[設定 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a2513-175">Choose **Settings**.</span></span>

3. <span data-ttu-id="a2513-176">[全般高度 **な**  >  **機能] に移動** し、タンパープロテクションを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="a2513-176">Go to **General** > **Advanced features**, and then turn tamper protection on.</span></span>

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a><span data-ttu-id="a2513-177">Intune を使用して組織の改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="a2513-177">Manage tamper protection for your organization using Intune</span></span>

<span data-ttu-id="a2513-178">組織のセキュリティ チームの一員であり、サブスクリプションに [Intune](/intune/fundamentals/what-is-intune)が含まれる場合は [、Microsoft Endpoint Manager](https://endpoint.microsoft.com) 管理センター ポータルで組織の改ざん防止を有効 (または無効) にできます。</span><span class="sxs-lookup"><span data-stu-id="a2513-178">If you are part of your organization's security team, and your subscription includes [Intune](/intune/fundamentals/what-is-intune), you can turn tamper protection on (or off) for your organization in the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com) portal.</span></span> <span data-ttu-id="a2513-179">タンパープロテクションの設定を微調整する場合は、Intune を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2513-179">Use Intune when you want to fine-tune tamper protection settings.</span></span> <span data-ttu-id="a2513-180">たとえば、一部のデバイスでタンパープロテクションを有効にするが、すべてではない場合は、Intune を使用します。</span><span class="sxs-lookup"><span data-stu-id="a2513-180">For example, if you want to enable tamper protection on some devices, but not all, use Intune.</span></span>

### <a name="requirements-for-managing-tamper-protection-in-intune"></a><span data-ttu-id="a2513-181">Intune でタンパープロテクションを管理するための要件</span><span class="sxs-lookup"><span data-stu-id="a2513-181">Requirements for managing tamper protection in Intune</span></span>

- <span data-ttu-id="a2513-182">グローバル管理者、セキュリティ [管理者、](/microsoft-365/security/defender-endpoint/assign-portal-access)セキュリティ操作など、適切なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a2513-182">You must have appropriate [permissions](/microsoft-365/security/defender-endpoint/assign-portal-access), such as global admin, security admin, or security operations.</span></span>

- <span data-ttu-id="a2513-183">組織は Intune を [使用してデバイスを管理します](/intune/fundamentals/what-is-device-management)。</span><span class="sxs-lookup"><span data-stu-id="a2513-183">Your organization uses [Intune to manage devices](/intune/fundamentals/what-is-device-management).</span></span> <span data-ttu-id="a2513-184">([Intune ライセンスが](/intune/fundamentals/licenses) 必要です。Intune は Microsoft 365 E5 に含まれています)。</span><span class="sxs-lookup"><span data-stu-id="a2513-184">([Intune licenses](/intune/fundamentals/licenses) are required; Intune is included in Microsoft 365 E5.)</span></span>

- <span data-ttu-id="a2513-185">Windows デバイスで Windows 10 OS [1709 、1803、1809](/windows/release-health/status-windows-10-1709)以降を実行している必要があります。 [](/windows/release-health/status-windows-10-1803) [](/windows/release-health/status-windows-10-1809-and-windows-server-2019)</span><span class="sxs-lookup"><span data-stu-id="a2513-185">Your Windows devices must be running Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) or later.</span></span> <span data-ttu-id="a2513-186">(リリースの詳細については [、「Windows 10 リリース情報」を参照してください](/windows/release-health/release-information))。</span><span class="sxs-lookup"><span data-stu-id="a2513-186">(For more information about releases, see [Windows 10 release information](/windows/release-health/release-information).)</span></span>

- <span data-ttu-id="a2513-187">Windows セキュリティを使用して、セキュリティ [インテリジェンスが](https://www.microsoft.com/wdsi/definitions) バージョン 1.287.60.0 (以上) に更新されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2513-187">You must be using Windows security with [security intelligence](https://www.microsoft.com/wdsi/definitions) updated to version 1.287.60.0 (or above).</span></span>

- <span data-ttu-id="a2513-188">デバイスでマルウェア対策プラットフォーム バージョン 4.18.1906.3 (以上) とマルウェア対策エンジン バージョン 1.1.15500.X (以上) を使用している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2513-188">Your devices must be using anti-malware platform version 4.18.1906.3 (or above) and anti-malware engine version 1.1.15500.X (or above).</span></span> <span data-ttu-id="a2513-189">([Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用](manage-updates-baselines-microsoft-defender-antivirus.md)します。)</span><span class="sxs-lookup"><span data-stu-id="a2513-189">([Manage Microsoft Defender Antivirus updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).)</span></span>

### <a name="turn-tamper-protection-on-or-off-in-intune"></a><span data-ttu-id="a2513-190">Intune でタンパープロテクションをオン (またはオフ) にする</span><span class="sxs-lookup"><span data-stu-id="a2513-190">Turn tamper protection on (or off) in Intune</span></span>

![Intune で改ざん防止を有効にする](images/turnontamperprotect-MEM.png)

1. <span data-ttu-id="a2513-192">Microsoft Endpoint Manager 管理 [センターに移動し](https://endpoint.microsoft.com) 、仕事または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="a2513-192">Go to the [Microsoft Endpoint Manager admin center](https://endpoint.microsoft.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="a2513-193">[**デバイス**  >  **構成プロファイル] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a2513-193">Select **Devices** > **Configuration Profiles**.</span></span>

3. <span data-ttu-id="a2513-194">次の設定を含むプロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2513-194">Create a profile that includes the following settings:</span></span>
    - <span data-ttu-id="a2513-195">**プラットフォーム: Windows 10 以降**</span><span class="sxs-lookup"><span data-stu-id="a2513-195">**Platform: Windows 10 and later**</span></span>
    - <span data-ttu-id="a2513-196">**プロファイルの種類: エンドポイント保護**</span><span class="sxs-lookup"><span data-stu-id="a2513-196">**Profile type: Endpoint protection**</span></span>
    - <span data-ttu-id="a2513-197">**カテゴリ: Microsoft Defender セキュリティ センター**</span><span class="sxs-lookup"><span data-stu-id="a2513-197">**Category: Microsoft Defender Security Center**</span></span>
    - <span data-ttu-id="a2513-198">**タンパープロテクション: 有効**</span><span class="sxs-lookup"><span data-stu-id="a2513-198">**Tamper Protection: Enabled**</span></span>

4. <span data-ttu-id="a2513-199">プロファイルを 1 つ以上のグループに割り当てる。</span><span class="sxs-lookup"><span data-stu-id="a2513-199">Assign the profile to one or more groups.</span></span>

### <a name="are-you-using-windows-os-1709-1803-or-1809"></a><span data-ttu-id="a2513-200">Windows OS 1709、1803、または 1809 を使用していますか?</span><span class="sxs-lookup"><span data-stu-id="a2513-200">Are you using Windows OS 1709, 1803, or 1809?</span></span>

<span data-ttu-id="a2513-201">Windows 10 OS  [1709、1803、](/windows/release-health/status-windows-10-1709)または[1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)を使用している場合、Windows セキュリティ アプリにタンパープロテクションは表示されます。 [](/windows/release-health/status-windows-10-1803)</span><span class="sxs-lookup"><span data-stu-id="a2513-201">If you are using Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), or [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), you won't see **Tamper Protection** in the Windows Security app.</span></span> <span data-ttu-id="a2513-202">代わりに、PowerShell を使用して、改ざん防止が有効になっているかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="a2513-202">Instead, you can use PowerShell to determine whether tamper protection is enabled.</span></span>

#### <a name="use-powershell-to-determine-whether-tamper-protection-is-turned-on"></a><span data-ttu-id="a2513-203">PowerShell を使用して、改ざん防止が有効になっているかどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="a2513-203">Use PowerShell to determine whether tamper protection is turned on</span></span>

1. <span data-ttu-id="a2513-204">アプリを開Windows PowerShellします。</span><span class="sxs-lookup"><span data-stu-id="a2513-204">Open the Windows PowerShell app.</span></span>

2. <span data-ttu-id="a2513-205">[Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a2513-205">Use the [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps) PowerShell cmdlet.</span></span>

3. <span data-ttu-id="a2513-206">結果の一覧で、 を探します `IsTamperProtected` 。</span><span class="sxs-lookup"><span data-stu-id="a2513-206">In the list of results, look for `IsTamperProtected`.</span></span> <span data-ttu-id="a2513-207">(true の値は *、改* ざん防止が有効になっているという意味です。</span><span class="sxs-lookup"><span data-stu-id="a2513-207">(A value of *true* means tamper protection is enabled.)</span></span>

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a><span data-ttu-id="a2513-208">Configuration Manager バージョン 2006 で組織の改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="a2513-208">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>

<span data-ttu-id="a2513-209">Configuration Manager の [バージョン 2006 を](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)使用している場合は、テナント接続というメソッドを使用して、Windows 10、Windows Server 2016、および Windows Server 2019 で改ざん防止設定を *管理できます*。</span><span class="sxs-lookup"><span data-stu-id="a2513-209">If you're using [version 2006 of Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006), you can manage tamper protection settings on Windows 10, Windows Server 2016, and Windows Server 2019 by using a method called *tenant attach*.</span></span> <span data-ttu-id="a2513-210">テナント接続を使用すると、オンプレミス専用の Configuration Manager デバイスを Microsoft Endpoint Manager 管理センターに同期し、エンドポイント セキュリティ構成ポリシーをデバイスのオンプレミス コレクション&できます。</span><span class="sxs-lookup"><span data-stu-id="a2513-210">Tenant attach enables you to sync your on-premises-only Configuration Manager devices into the Microsoft Endpoint Manager admin center, and then deliver endpoint security configuration policies to on-premises collections & devices.</span></span>

![エンドポイント マネージャーでの Windows セキュリティ エクスペリエンス](images/win-security- exp-policy-endpt-security.png)

> [!NOTE]
> <span data-ttu-id="a2513-212">この手順を使用して、Windows 10 および Windows Server 2019 を実行しているデバイスに改ざん防止を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="a2513-212">The procedure can be used to extend tamper protection to devices running Windows 10 and Windows Server 2019.</span></span> <span data-ttu-id="a2513-213">この手順で説明されているリソースの前提条件と他の情報を必ず確認してください。</span><span class="sxs-lookup"><span data-stu-id="a2513-213">Make sure to review the prerequisites and other information in the resources mentioned in this procedure.</span></span>

1. <span data-ttu-id="a2513-214">テナント接続を設定します。</span><span class="sxs-lookup"><span data-stu-id="a2513-214">Set up tenant attach.</span></span> <span data-ttu-id="a2513-215">このヘルプについては、「Microsoft Endpoint Manager テナント接続: デバイスの同期と [デバイスの操作」を参照してください](/mem/configmgr/tenant-attach/device-sync-actions)。</span><span class="sxs-lookup"><span data-stu-id="a2513-215">To get help with this, see [Microsoft Endpoint Manager tenant attach: Device sync and device actions](/mem/configmgr/tenant-attach/device-sync-actions).</span></span>

2. <span data-ttu-id="a2513-216">Microsoft [Endpoint Manager 管理センターで、[](https://go.microsoft.com/fwlink/?linkid=2109431)エンドポイント **セキュリティ** ウイルス対策] に移動し、[+ ポリシーの作成]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a2513-216">In the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Endpoint security** > **Antivirus**, and then choose **+ Create Policy**.</span></span><br/> 
   - <span data-ttu-id="a2513-217">[プラットフォーム **] ボックスの** 一覧で **、[Windows 10] と [Windows Server (ConfigMgr) ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a2513-217">In the **Platform** list, select **Windows 10 and Windows Server (ConfigMgr)**.</span></span>  
   - <span data-ttu-id="a2513-218">[プロファイル] **リストで** 、[Windows セキュリティ エクスペリエンス **(プレビュー) ] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a2513-218">In the **Profile** list, select **Windows Security experience (preview)**.</span></span> <br/>

3. <span data-ttu-id="a2513-219">デバイス コレクションにポリシーを展開します。</span><span class="sxs-lookup"><span data-stu-id="a2513-219">Deploy the policy to your device collection.</span></span>

### <a name="need-help-with-this-method"></a><span data-ttu-id="a2513-220">このメソッドのヘルプが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="a2513-220">Need help with this method?</span></span> 

<span data-ttu-id="a2513-221">以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2513-221">See the following resources:</span></span>

- [<span data-ttu-id="a2513-222">Microsoft Intune の Windows セキュリティ エクスペリエンス プロファイルの設定</span><span class="sxs-lookup"><span data-stu-id="a2513-222">Settings for the Windows Security experience profile in Microsoft Intune</span></span>](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [<span data-ttu-id="a2513-223">Tech Community Blog: Configuration Manager テナント接続クライアントのタンパープロテクションの発表</span><span class="sxs-lookup"><span data-stu-id="a2513-223">Tech Community Blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a><span data-ttu-id="a2513-224">個々のデバイスで改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="a2513-224">Manage tamper protection on an individual device</span></span>

> [!NOTE]
> <span data-ttu-id="a2513-225">改ざん防止ブロックは、レジストリを介して Microsoft Defender ウイルス対策の設定を変更しようと試みをブロックします。</span><span class="sxs-lookup"><span data-stu-id="a2513-225">Tamper protection blocks attempts to modify Microsoft Defender Antivirus settings through the registry.</span></span>
>
> <span data-ttu-id="a2513-226">これらの設定を変更するサードパーティのセキュリティ製品やエンタープライズ インストール スクリプトにタンパープロテクションが干渉しないようにするには **、「Windows Security」** に移動し、セキュリティ インテリジェンスをバージョン 1.287.60.0 以降に更新します。</span><span class="sxs-lookup"><span data-stu-id="a2513-226">To help ensure that tamper protection doesn’t interfere with third-party security products or enterprise installation scripts that modify these settings, go to **Windows Security** and update **Security intelligence** to version 1.287.60.0 or later.</span></span> <span data-ttu-id="a2513-227">(「セキュリティ [インテリジェンスの更新プログラム」を参照](https://www.microsoft.com/wdsi/definitions)してください。</span><span class="sxs-lookup"><span data-stu-id="a2513-227">(See [Security intelligence updates](https://www.microsoft.com/wdsi/definitions).)</span></span>
>
> <span data-ttu-id="a2513-228">この更新プログラムを作成すると、改ざん防止はレジストリ設定を保護し続け、ログはエラーを返さずに変更を試みる。</span><span class="sxs-lookup"><span data-stu-id="a2513-228">Once you’ve made this update, tamper protection continues to protect your registry settings, and logs attempts to modify them without returning errors.</span></span>

<span data-ttu-id="a2513-229">ホーム ユーザーである場合、またはセキュリティ チームが管理する設定の対象ではない場合は、Windows セキュリティ アプリを使用して改ざん防止を管理できます。</span><span class="sxs-lookup"><span data-stu-id="a2513-229">If you are a home user, or you are not subject to settings managed by a security team, you can use the Windows Security app to manage tamper protection.</span></span> <span data-ttu-id="a2513-230">改ざん防止などのセキュリティ設定を変更するには、デバイスに適切な管理者アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="a2513-230">You must have appropriate admin permissions on your device to do change security settings, such as tamper protection.</span></span>

<span data-ttu-id="a2513-231">Windows セキュリティ アプリに表示される情報を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a2513-231">Here's what you see in the Windows Security app:</span></span>

![Windows 10 Home でタンパープロテクションが有効になっている](images/tamperprotectionturnedon.png)

1. <span data-ttu-id="a2513-233">[スタート **] を選択** し、[セキュリティ] の入力 *を開始します*。</span><span class="sxs-lookup"><span data-stu-id="a2513-233">Select **Start**, and start typing *Security*.</span></span> <span data-ttu-id="a2513-234">検索結果で、[Windows セキュリティ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a2513-234">In the search results, select **Windows Security**.</span></span>

2. <span data-ttu-id="a2513-235">[**ウイルス対策&ウイルス**  >  **対策] を選択&の設定を選択します**。</span><span class="sxs-lookup"><span data-stu-id="a2513-235">Select **Virus & threat protection** > **Virus & threat protection settings**.</span></span>

3. <span data-ttu-id="a2513-236">タン **パープロテクションを** **On または** Off に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="a2513-236">Set **Tamper Protection** to **On** or **Off**.</span></span>



## <a name="view-information-about-tampering-attempts"></a><span data-ttu-id="a2513-237">改ざんの試行に関する情報を表示する</span><span class="sxs-lookup"><span data-stu-id="a2513-237">View information about tampering attempts</span></span>

<span data-ttu-id="a2513-238">改ざんの試みは、通常、より大きなサイバー攻撃を示します。</span><span class="sxs-lookup"><span data-stu-id="a2513-238">Tampering attempts typically indicate bigger cyberattacks.</span></span> <span data-ttu-id="a2513-239">悪いアクターは、セキュリティ設定を変更して、検出されない状態を維持します。</span><span class="sxs-lookup"><span data-stu-id="a2513-239">Bad actors try to change security settings as a way to persist and stay undetected.</span></span> <span data-ttu-id="a2513-240">組織のセキュリティ チームの一員である場合は、そのような試みについての情報を表示し、脅威を軽減するために適切なアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a2513-240">If you're part of your organization's security team, you can view information about such attempts, and then take appropriate actions to mitigate threats.</span></span>

<span data-ttu-id="a2513-241">改ざんの試行が検出されると、Microsoft Defender セキュリティ センター ( ) で [アラートが発生](/microsoft-365/security/defender-endpoint/portal-overview) します [https://securitycenter.windows.com](https://securitycenter.windows.com) 。</span><span class="sxs-lookup"><span data-stu-id="a2513-241">When a tampering attempt is detected, an alert is raised in the [Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/portal-overview) ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

![Microsoft Defender セキュリティ センター](images/tamperattemptalert.png)

<span data-ttu-id="a2513-243">Microsoft [](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) Defender for [](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) Endpoint のエンドポイント検出および応答機能と高度なハンティング機能を使用して、セキュリティ運用チームはそのような試みを調査し、対処できます。</span><span class="sxs-lookup"><span data-stu-id="a2513-243">Using [endpoint detection and response](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) and [advanced hunting](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) capabilities in Microsoft Defender for Endpoint, your security operations team can investigate and address such attempts.</span></span>

## <a name="review-your-security-recommendations"></a><span data-ttu-id="a2513-244">セキュリティに関する推奨事項を確認する</span><span class="sxs-lookup"><span data-stu-id="a2513-244">Review your security recommendations</span></span>

<span data-ttu-id="a2513-245">タンパープロテクションは [、脅威&管理機能と](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) 統合されます。</span><span class="sxs-lookup"><span data-stu-id="a2513-245">Tamper protection integrates with [Threat & Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) capabilities.</span></span> <span data-ttu-id="a2513-246">[セキュリティに関する推奨事項には](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) 、改ざん防止が有効になっていることを確認する方法が含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2513-246">[Security recommendations](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) include making sure tamper protection is turned on.</span></span> <span data-ttu-id="a2513-247">たとえば、次の図に示 *すように*、改ざん時に検索できます。</span><span class="sxs-lookup"><span data-stu-id="a2513-247">For example, you can search on *tamper*, as shown in the following image:</span></span>

![改ざん防止により、セキュリティに関する推奨事項が表示される](/images/securityrecs-tamperprotect.jpg)

<span data-ttu-id="a2513-249">結果では、[タンパープロテクションを **有効** にする] を選択して詳細を確認し、有効にできます。</span><span class="sxs-lookup"><span data-stu-id="a2513-249">In the results, you can select **Turn on Tamper Protection** to learn more and turn it on.</span></span>

![改ざん防止を有効にする](images/tamperprotectsecurityrecos.png)

<span data-ttu-id="a2513-251">脅威の脆弱性管理の詳細& Microsoft Defender セキュリティ センターの「脅威& [脆弱性管理」を参照してください](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center)。</span><span class="sxs-lookup"><span data-stu-id="a2513-251">To learn more about Threat & Vulnerability Management, see [Threat & Vulnerability Management in Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a2513-252">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="a2513-252">Frequently asked questions</span></span>

### <a name="to-which-windows-os-versions-is-configuring-tamper-protection-is-applicable"></a><span data-ttu-id="a2513-253">タンパープロテクションを構成している Windows OS のバージョンは、どのバージョンに適用されますか?</span><span class="sxs-lookup"><span data-stu-id="a2513-253">To which Windows OS versions is configuring tamper protection is applicable?</span></span>

<span data-ttu-id="a2513-254">Windows 10 OS [1709](/windows/release-health/status-windows-10-1709)、 [1803](/windows/release-health/status-windows-10-1803)、 [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)以降と [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span><span class="sxs-lookup"><span data-stu-id="a2513-254">Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019), or later together with [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

<span data-ttu-id="a2513-255">Configuration Manager バージョン 2006 をテナント接続で使用している場合は、改ざん防止を Windows Server 2019 に拡張できます。</span><span class="sxs-lookup"><span data-stu-id="a2513-255">If you are using Configuration Manager, version 2006, with tenant attach, tamper protection can be extended to Windows Server 2019.</span></span> <span data-ttu-id="a2513-256">「 [テナント接続: 管理センターからエンドポイント セキュリティ](/mem/configmgr/tenant-attach/deploy-antivirus-policy)ウイルス対策ポリシーを作成して展開する (プレビュー)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2513-256">See [Tenant attach: Create and deploy endpoint security Antivirus policy from the admin center (preview)](/mem/configmgr/tenant-attach/deploy-antivirus-policy).</span></span>

### <a name="will-tamper-protection-have-any-impact-on-third-party-antivirus-registration"></a><span data-ttu-id="a2513-257">改ざん防止はサードパーティのウイルス対策登録に影響しますか?</span><span class="sxs-lookup"><span data-stu-id="a2513-257">Will tamper protection have any impact on third-party antivirus registration?</span></span>

<span data-ttu-id="a2513-258">いいえ。</span><span class="sxs-lookup"><span data-stu-id="a2513-258">No.</span></span> <span data-ttu-id="a2513-259">サードパーティのウイルス対策製品は、引き続き Windows Security アプリケーションに登録されます。</span><span class="sxs-lookup"><span data-stu-id="a2513-259">Third-party antivirus offerings will continue to register with the Windows Security application.</span></span>

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a><span data-ttu-id="a2513-260">Microsoft Defender ウイルス対策がデバイスでアクティブではない場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="a2513-260">What happens if Microsoft Defender Antivirus is not active on a device?</span></span>

<span data-ttu-id="a2513-261">Microsoft Defender for Endpoint にオンボードされているデバイスでは、Microsoft Defender Antivirus がパッシブ モードで実行されます。</span><span class="sxs-lookup"><span data-stu-id="a2513-261">Devices that are onboarded to Microsoft Defender for Endpoint will have Microsoft Defender Antivirus running in passive mode.</span></span> <span data-ttu-id="a2513-262">改ざん防止は、サービスとその機能を引き続き保護します。</span><span class="sxs-lookup"><span data-stu-id="a2513-262">Tamper protection will continue to protect the service and its features.</span></span> 

### <a name="how-can-i-turn-tamper-protection-onoff"></a><span data-ttu-id="a2513-263">改ざん防止のオン/オフを切り替えますか?</span><span class="sxs-lookup"><span data-stu-id="a2513-263">How can I turn tamper protection on/off?</span></span>

<span data-ttu-id="a2513-264">ホーム ユーザーの場合は、「個々のデバイスで [タンパープロテクションを管理する」を参照してください](#manage-tamper-protection-on-an-individual-device)。</span><span class="sxs-lookup"><span data-stu-id="a2513-264">If you are a home user, see [Manage tamper protection on an individual device](#manage-tamper-protection-on-an-individual-device).</span></span>

<span data-ttu-id="a2513-265">Microsoft Defender for [Endpoint](/microsoft-365/security/defender-endpoint)を使用している組織の場合は、他のエンドポイント保護機能を管理する方法と同様に、Intune でタンパープロテクションを管理できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2513-265">If you are an organization using [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint), you should be able to manage tamper protection in Intune similar to how you manage other endpoint protection features.</span></span> <span data-ttu-id="a2513-266">この記事の以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2513-266">See the following sections of this article:</span></span> 

- [<span data-ttu-id="a2513-267">Intune を使用して改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="a2513-267">Manage tamper protection using Intune</span></span>](#manage-tamper-protection-for-your-organization-using-intune)
- [<span data-ttu-id="a2513-268">Configuration Manager バージョン 2006 を使用して改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="a2513-268">Manage tamper protection using Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- <span data-ttu-id="a2513-269">[Microsoft Defender セキュリティ センターを使用して改ざん防止を管理する](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) (現在プレビュー中)</span><span class="sxs-lookup"><span data-stu-id="a2513-269">[Manage tamper protection using the Microsoft Defender Security Center](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) (currently in preview)</span></span>

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-through-my-group-policy"></a><span data-ttu-id="a2513-270">Intune でタンパープロテクションを構成すると、グループ ポリシーを通じて Microsoft Defender ウイルス対策を管理する方法にどのような影響がありますか?</span><span class="sxs-lookup"><span data-stu-id="a2513-270">How does configuring tamper protection in Intune affect how I manage Microsoft Defender Antivirus through my group policy?</span></span>

<span data-ttu-id="a2513-271">通常のグループ ポリシーは改ざん防止には適用されません。改ざん防止がオンの場合、Microsoft Defender ウイルス対策の設定に対する変更は無視されます。</span><span class="sxs-lookup"><span data-stu-id="a2513-271">Your regular group policy doesn’t apply to tamper protection, and changes to Microsoft Defender Antivirus settings are ignored when tamper protection is on.</span></span> 

### <a name="for-microsoft-defender-for-endpoint-is-configuring-tamper-protection-in-intune-targeted-to-the-entire-organization-only"></a><span data-ttu-id="a2513-272">Microsoft Defender for Endpoint の場合、Intune でタンパープロテクションを組織全体のみを対象に構成していますか?</span><span class="sxs-lookup"><span data-stu-id="a2513-272">For Microsoft Defender for Endpoint, is configuring tamper protection in Intune targeted to the entire organization only?</span></span>

<span data-ttu-id="a2513-273">Intune または Microsoft Endpoint Manager でタンパープロテクションを構成するには、組織全体と特定のデバイスとユーザー グループを対象とすることができます。</span><span class="sxs-lookup"><span data-stu-id="a2513-273">Configuring tamper protection in Intune or Microsoft Endpoint Manager can be targeted to your entire organization and to specific devices and user groups.</span></span>

### <a name="can-i-configure-tamper-protection-in-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="a2513-274">Microsoft Endpoint Configuration Manager でタンパープロテクションを構成できますか?</span><span class="sxs-lookup"><span data-stu-id="a2513-274">Can I configure Tamper Protection in Microsoft Endpoint Configuration Manager?</span></span>

<span data-ttu-id="a2513-275">テナント接続を使用している場合は、Microsoft Endpoint Configuration Manager を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2513-275">If you are using tenant attach, you can use Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="a2513-276">以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2513-276">See the following resources:</span></span>
- [<span data-ttu-id="a2513-277">Configuration Manager バージョン 2006 で組織の改ざん防止を管理する</span><span class="sxs-lookup"><span data-stu-id="a2513-277">Manage tamper protection for your organization with Configuration Manager, version 2006</span></span>](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [<span data-ttu-id="a2513-278">Tech Community ブログ: Configuration Manager テナント接続クライアントのタンパープロテクションの発表</span><span class="sxs-lookup"><span data-stu-id="a2513-278">Tech Community blog: Announcing Tamper Protection for Configuration Manager Tenant Attach clients</span></span>](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a><span data-ttu-id="a2513-279">Windows E3 登録があります。</span><span class="sxs-lookup"><span data-stu-id="a2513-279">I have the Windows E3 enrollment.</span></span> <span data-ttu-id="a2513-280">Intune でタンパープロテクションの構成を使用できますか?</span><span class="sxs-lookup"><span data-stu-id="a2513-280">Can I use configuring tamper protection in Intune?</span></span>

<span data-ttu-id="a2513-281">現在、Intune でタンパープロテクションを構成できるのは [、Microsoft Defender for Endpoint をお持ちのお客様のみです](/microsoft-365/security/defender-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="a2513-281">Currently, configuring tamper protection in Intune is only available for customers who have [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint).</span></span>

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a><span data-ttu-id="a2513-282">デバイスでタンパープロテクションが有効になっているときに、Intune、Microsoft Endpoint Configuration Manager、および Windows 管理インストルメンテーションで Microsoft Defender for Endpoint の設定を変更すると、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="a2513-282">What happens if I try to change Microsoft Defender for Endpoint settings in Intune, Microsoft Endpoint Configuration Manager, and Windows Management Instrumentation when Tamper Protection is enabled on a device?</span></span>

<span data-ttu-id="a2513-283">改ざん防止によって保護されている機能を変更できない。このような変更要求は無視されます。</span><span class="sxs-lookup"><span data-stu-id="a2513-283">You won’t be able to change the features that are protected by tamper protection; such change requests are ignored.</span></span>

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a><span data-ttu-id="a2513-284">エンタープライズ顧客です。</span><span class="sxs-lookup"><span data-stu-id="a2513-284">I’m an enterprise customer.</span></span> <span data-ttu-id="a2513-285">ローカル管理者は、デバイスの改ざん防止を変更できますか?</span><span class="sxs-lookup"><span data-stu-id="a2513-285">Can local admins change tamper protection on their devices?</span></span>

<span data-ttu-id="a2513-286">いいえ。</span><span class="sxs-lookup"><span data-stu-id="a2513-286">No.</span></span> <span data-ttu-id="a2513-287">ローカル管理者は、改ざん防止の設定を変更または変更できません。</span><span class="sxs-lookup"><span data-stu-id="a2513-287">Local admins cannot change or modify tamper protection settings.</span></span>

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a><span data-ttu-id="a2513-288">デバイスが Microsoft Defender for Endpoint にオンボードされ、オフボード状態に入った場合は、どうなるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="a2513-288">What happens if my device is onboarded with Microsoft Defender for Endpoint and then goes into an off-boarded state?</span></span>

<span data-ttu-id="a2513-289">デバイスが Microsoft Defender for Endpoint からオフボードされている場合、タンパープロテクションが有効になります。これは管理されていないデバイスの既定の状態です。</span><span class="sxs-lookup"><span data-stu-id="a2513-289">If a device is off-boarded from Microsoft Defender for Endpoint, tamper protection is turned on, which is the default state for unmanaged devices.</span></span> 

### <a name="will-there-be-an-alert-about-tamper-protection-status-changing-in-the-microsoft-defender-security-center"></a><span data-ttu-id="a2513-290">Microsoft Defender セキュリティ センターで改ざん防止の状態が変更された場合、警告が表示されますか?</span><span class="sxs-lookup"><span data-stu-id="a2513-290">Will there be an alert about tamper protection status changing in the Microsoft Defender Security Center?</span></span>

<span data-ttu-id="a2513-291">はい。</span><span class="sxs-lookup"><span data-stu-id="a2513-291">Yes.</span></span> <span data-ttu-id="a2513-292">アラートは [アラート] の下 [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) に **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="a2513-292">The alert is shown in [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) under **Alerts**.</span></span>

<span data-ttu-id="a2513-293">セキュリティ運用チームは、次の例のような検索クエリも使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2513-293">Your security operations team can also use hunting queries, such as the following example:</span></span>

`DeviceAlertEvents | where Title == "Tamper Protection bypass"`

<span data-ttu-id="a2513-294">[改ざんの試行に関する情報を表示します](#view-information-about-tampering-attempts)。</span><span class="sxs-lookup"><span data-stu-id="a2513-294">[View information about tampering attempts](#view-information-about-tampering-attempts).</span></span>

## <a name="see-also"></a><span data-ttu-id="a2513-295">関連項目</span><span class="sxs-lookup"><span data-stu-id="a2513-295">See also</span></span>

[<span data-ttu-id="a2513-296">Microsoft Intune のエンドポイント保護を使用して Windows PC をセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="a2513-296">Help secure Windows PCs with Endpoint Protection for Microsoft Intune</span></span>](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[<span data-ttu-id="a2513-297">Microsoft Defender for Endpoint の概要を確認する</span><span class="sxs-lookup"><span data-stu-id="a2513-297">Get an overview of Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint)

[<span data-ttu-id="a2513-298">より良い一緒に:Microsoft Defender Antivirus と Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a2513-298">Better together: Microsoft Defender Antivirus and Microsoft Defender for Endpoint</span></span>](why-use-microsoft-defender-antivirus.md)