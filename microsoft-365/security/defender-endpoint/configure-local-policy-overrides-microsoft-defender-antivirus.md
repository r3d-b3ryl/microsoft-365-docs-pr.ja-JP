---
title: Microsoft Defender AV 設定のローカルオーバーライドを構成する
description: Microsoft Defender AV でユーザーがローカルで変更する設定を有効または無効にします。
keywords: ローカル オーバーライド, ローカル ポリシー, グループ ポリシー, gpo, lockdown,merge, lists
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 02/13/2020
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 2d23ca6d98d86666d72b75723a2205fcd83b08d7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924245"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a><span data-ttu-id="9fd6c-104">ユーザーがポリシー設定をローカルで変更Microsoft Defender ウイルス対策または許可する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-104">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>


<span data-ttu-id="9fd6c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9fd6c-105">**Applies to:**</span></span>

- [<span data-ttu-id="9fd6c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9fd6c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="9fd6c-107">既定ではMicrosoft Defender ウイルス対策グループ ポリシー オブジェクトを介してネットワーク内のエンドポイントに展開される設定を使用すると、ユーザーはローカルで設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-107">By default, Microsoft Defender Antivirus settings that are deployed via a Group Policy Object to the endpoints in your network will prevent users from locally changing the settings.</span></span> <span data-ttu-id="9fd6c-108">これは、一部のインスタンスで変更できます。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-108">You can change this in some instances.</span></span>

<span data-ttu-id="9fd6c-109">たとえば、特定のユーザー グループ (セキュリティ研究者や脅威調査者など) が、使用するエンドポイントの個々の設定をさらに制御できる必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-109">For example, it may be necessary to allow certain user groups (such as security researchers and threat investigators) further control over individual settings on the endpoints they use.</span></span>

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a><span data-ttu-id="9fd6c-110">ユーザー設定のローカルオーバーライドをMicrosoft Defender ウイルス対策する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-110">Configure local overrides for Microsoft Defender Antivirus settings</span></span>

<span data-ttu-id="9fd6c-111">これらのポリシーの既定の設定は [無効] **です**。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-111">The default setting for these policies is **Disabled**.</span></span>

<span data-ttu-id="9fd6c-112">[有効] に設定 **されている** 場合、エンドポイントのユーザーは、Windows セキュリティ アプリ、ローカル グループ ポリシー設定、および [PowerShell](microsoft-defender-security-center-antivirus.md)コマンドレット (必要に応じて) に関連付けられた設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-112">If they are set to **Enabled**, users on endpoints can make changes to the associated setting with the [Windows Security](microsoft-defender-security-center-antivirus.md) app, local Group Policy settings, and PowerShell cmdlets (where appropriate).</span></span>

<span data-ttu-id="9fd6c-113">次の表に、各上書きポリシー設定と、関連する機能または設定の構成手順を示します。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-113">The following table lists each of the override policy setting and the configuration instructions for the associated feature or setting.</span></span>

<span data-ttu-id="9fd6c-114">これらの設定を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-114">To configure these settings:</span></span>

1. <span data-ttu-id="9fd6c-115">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="9fd6c-116">グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="9fd6c-117">ツリーを展開して **、Windowsコンポーネント> Microsoft Defender ウイルス対策** 次に、次の表で指定した **場所** を指定します。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-117">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

4. <span data-ttu-id="9fd6c-118">下の表で指定 **したポリシー設定** をダブルクリックし、オプションを目的の構成に設定します。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-118">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> <span data-ttu-id="9fd6c-119">**[OK] を** クリックし、他の設定を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-119">Click **OK**, and repeat for any other settings.</span></span>

5. <span data-ttu-id="9fd6c-120">グループ ポリシー オブジェクトを通常どおり展開します。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-120">Deploy the Group Policy Object as usual.</span></span>

<span data-ttu-id="9fd6c-121">場所</span><span class="sxs-lookup"><span data-stu-id="9fd6c-121">Location</span></span> | <span data-ttu-id="9fd6c-122">Setting</span><span class="sxs-lookup"><span data-stu-id="9fd6c-122">Setting</span></span> | <span data-ttu-id="9fd6c-123">記事</span><span class="sxs-lookup"><span data-stu-id="9fd6c-123">Article</span></span>
---|---|---|---
<span data-ttu-id="9fd6c-124">MAPS</span><span class="sxs-lookup"><span data-stu-id="9fd6c-124">MAPS</span></span> | <span data-ttu-id="9fd6c-125">Microsoft MAPS へのレポート用にローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-125">Configure local setting override for reporting to Microsoft MAPS</span></span> | [<span data-ttu-id="9fd6c-126">クラウドによる保護の有効化</span><span class="sxs-lookup"><span data-stu-id="9fd6c-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="9fd6c-127">検疫する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-127">Quarantine</span></span> | <span data-ttu-id="9fd6c-128">検疫フォルダーからアイテムを削除するローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-128">Configure local setting override for the removal of items from Quarantine folder</span></span> | [<span data-ttu-id="9fd6c-129">スキャンの修復を構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-129">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
<span data-ttu-id="9fd6c-130">リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="9fd6c-130">Real-time protection</span></span> | <span data-ttu-id="9fd6c-131">コンピューター上のファイルとプログラムのアクティビティを監視するローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-131">Configure local setting override for monitoring file and program activity on your computer</span></span> | [<span data-ttu-id="9fd6c-132">常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-132">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="9fd6c-133">リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="9fd6c-133">Real-time protection</span></span> | <span data-ttu-id="9fd6c-134">受信および送信ファイルのアクティビティを監視するローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-134">Configure local setting override for monitoring for incoming and outgoing file activity</span></span> | [<span data-ttu-id="9fd6c-135">常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-135">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="9fd6c-136">リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="9fd6c-136">Real-time protection</span></span> | <span data-ttu-id="9fd6c-137">ダウンロードしたファイルと添付ファイルをスキャンするローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-137">Configure local setting override for scanning all downloaded files and attachments</span></span> | [<span data-ttu-id="9fd6c-138">常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-138">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="9fd6c-139">リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="9fd6c-139">Real-time protection</span></span> | <span data-ttu-id="9fd6c-140">オンの動作監視用にローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-140">Configure local setting override for turn on behavior monitoring</span></span> | [<span data-ttu-id="9fd6c-141">常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-141">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="9fd6c-142">リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="9fd6c-142">Real-time protection</span></span> | <span data-ttu-id="9fd6c-143">ローカル設定の上書きを構成してリアルタイム保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="9fd6c-143">Configure local setting override to turn on real-time protection</span></span> | [<span data-ttu-id="9fd6c-144">常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-144">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="9fd6c-145">修復</span><span class="sxs-lookup"><span data-stu-id="9fd6c-145">Remediation</span></span> | <span data-ttu-id="9fd6c-146">スケジュールされたフル スキャンを実行して修復を完了するために、時刻のローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-146">Configure local setting override for the time of day to run a scheduled full scan to complete remediation</span></span> | [<span data-ttu-id="9fd6c-147">スキャンの修復を構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-147">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
<span data-ttu-id="9fd6c-148">スキャン</span><span class="sxs-lookup"><span data-stu-id="9fd6c-148">Scan</span></span> | <span data-ttu-id="9fd6c-149">CPU 使用率の最大割合に対するローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-149">Configure local setting override for maximum percentage of CPU utilization</span></span> | [<span data-ttu-id="9fd6c-150">スキャンの構成と実行</span><span class="sxs-lookup"><span data-stu-id="9fd6c-150">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md)
<span data-ttu-id="9fd6c-151">スキャン</span><span class="sxs-lookup"><span data-stu-id="9fd6c-151">Scan</span></span> | <span data-ttu-id="9fd6c-152">スケジュール スキャン日のローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-152">Configure local setting override for schedule scan day</span></span> | [<span data-ttu-id="9fd6c-153">スケジュールされたスキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-153">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="9fd6c-154">スキャン</span><span class="sxs-lookup"><span data-stu-id="9fd6c-154">Scan</span></span> | <span data-ttu-id="9fd6c-155">スケジュールされたクイック スキャン時間のローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-155">Configure local setting override for scheduled quick scan time</span></span> | [<span data-ttu-id="9fd6c-156">スケジュールされたスキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-156">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="9fd6c-157">スキャン</span><span class="sxs-lookup"><span data-stu-id="9fd6c-157">Scan</span></span> | <span data-ttu-id="9fd6c-158">スケジュールされたスキャン時間のローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-158">Configure local setting override for scheduled scan time</span></span> | [<span data-ttu-id="9fd6c-159">スケジュールされたスキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-159">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="9fd6c-160">スキャン</span><span class="sxs-lookup"><span data-stu-id="9fd6c-160">Scan</span></span> | <span data-ttu-id="9fd6c-161">スケジュールされたスキャンに使用するスキャンの種類のローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-161">Configure local setting override for the scan type to use for a scheduled scan</span></span> | [<span data-ttu-id="9fd6c-162">スケジュールされたスキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-162">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a><span data-ttu-id="9fd6c-163">ローカルおよびグローバルに定義された脅威の修復と除外リストの結合方法を構成する</span><span class="sxs-lookup"><span data-stu-id="9fd6c-163">Configure how locally and globally defined threat remediation and exclusions lists are merged</span></span>

<span data-ttu-id="9fd6c-164">ローカルに定義されたリストをグローバルに定義されたリストと結合または結合する方法を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-164">You can also configure how locally defined lists are combined or merged with globally defined lists.</span></span> <span data-ttu-id="9fd6c-165">この設定は、除外リスト[、指定された](configure-exclusions-microsoft-defender-antivirus.md)修復リスト、攻撃表面[](configure-remediation-microsoft-defender-antivirus.md)[の縮小に適用されます](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-165">This setting applies to [exclusion lists](configure-exclusions-microsoft-defender-antivirus.md), [specified remediation lists](configure-remediation-microsoft-defender-antivirus.md), and [attack surface reduction](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction).</span></span>

<span data-ttu-id="9fd6c-166">既定では、ローカル グループ ポリシーと Windows セキュリティ アプリで構成されているリストは、ネットワークに展開した適切なグループ ポリシー オブジェクトによって定義されたリストと結合されます。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-166">By default, lists that have been configured in local group policy and the Windows Security app are merged with lists that are defined by the appropriate Group Policy Object that you have deployed on your network.</span></span> <span data-ttu-id="9fd6c-167">競合がある場合は、グローバルに定義されたリストが優先されます。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-167">Where there are conflicts, the globally-defined list takes precedence.</span></span>

<span data-ttu-id="9fd6c-168">この設定を無効にすると、グローバルに定義されたリスト (展開された GPO のリストなど) だけが使用されます。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-168">You can disable this setting to ensure that only globally-defined lists (such as those from any deployed GPOs) are used.</span></span>

### <a name="use-group-policy-to-disable-local-list-merging"></a><span data-ttu-id="9fd6c-169">グループ ポリシーを使用してローカル リストのマージを無効にする</span><span class="sxs-lookup"><span data-stu-id="9fd6c-169">Use Group Policy to disable local list merging</span></span>

1. <span data-ttu-id="9fd6c-170">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-170">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="9fd6c-171">グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-171">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="9fd6c-172">ツリーを展開して **、Windowsコンポーネント> Microsoft Defender ウイルス対策。**</span><span class="sxs-lookup"><span data-stu-id="9fd6c-172">Expand the tree to **Windows components > Microsoft Defender Antivirus**.</span></span>

4. <span data-ttu-id="9fd6c-173">[リストのローカル **管理者の差し込み動作を構成** する] をダブルクリックし、オプションを [無効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-173">Double-click **Configure local administrator merge behavior for lists** and set the option to **Disabled**.</span></span> <span data-ttu-id="9fd6c-174">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-174">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="9fd6c-175">ローカル リストの結合を無効にすると、フォルダー アクセスの制御設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-175">If you disable local list merging, it will override controlled folder access settings.</span></span> <span data-ttu-id="9fd6c-176">また、ローカル管理者が設定した保護されたフォルダーまたは許可されたアプリも上書きされます。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-176">It also overrides any protected folders or allowed apps set by the local administrator.</span></span> <span data-ttu-id="9fd6c-177">フォルダー アクセスの制御設定の詳細については、「アプリでブロック[されたアプリ](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security)を許可する」を参照Windows セキュリティ。</span><span class="sxs-lookup"><span data-stu-id="9fd6c-177">For more information about controlled folder access settings, see [Allow a blocked app in Windows Security](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9fd6c-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="9fd6c-178">Related topics</span></span>

- [<span data-ttu-id="9fd6c-179">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="9fd6c-179">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="9fd6c-180">ユーザーとのエンド ユーザー操作を構成Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="9fd6c-180">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)
