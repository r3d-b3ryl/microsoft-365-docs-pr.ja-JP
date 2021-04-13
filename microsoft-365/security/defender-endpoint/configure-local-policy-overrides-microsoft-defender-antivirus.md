---
title: Microsoft Defender AV 設定のローカルオーバーライドを構成する
description: Microsoft Defender AV でユーザーがローカルで変更する設定を有効または無効にします。
keywords: ローカル オーバーライド, ローカル ポリシー, グループ ポリシー, gpo, lockdown,merge, lists
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 02/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 045cadf06533197fda09baa7352bf03f14dd5ba2
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690802"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a><span data-ttu-id="dbd3f-104">ユーザーによる Microsoft Defender ウイルス対策ポリシー設定のローカル変更を防止または許可する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-104">Prevent or allow users to locally modify Microsoft Defender Antivirus policy settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="dbd3f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="dbd3f-105">**Applies to:**</span></span>

- [<span data-ttu-id="dbd3f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dbd3f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="dbd3f-107">既定では、グループ ポリシー オブジェクトを介してネットワーク内のエンドポイントに展開される Microsoft Defender ウイルス対策設定では、ユーザーがローカルで設定を変更できません。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-107">By default, Microsoft Defender Antivirus settings that are deployed via a Group Policy Object to the endpoints in your network will prevent users from locally changing the settings.</span></span> <span data-ttu-id="dbd3f-108">これは、一部のインスタンスで変更できます。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-108">You can change this in some instances.</span></span>

<span data-ttu-id="dbd3f-109">たとえば、特定のユーザー グループ (セキュリティ研究者や脅威調査者など) が、使用するエンドポイントの個々の設定をさらに制御できる必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-109">For example, it may be necessary to allow certain user groups (such as security researchers and threat investigators) further control over individual settings on the endpoints they use.</span></span>

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a><span data-ttu-id="dbd3f-110">Microsoft Defender ウイルス対策設定のローカルオーバーライドを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-110">Configure local overrides for Microsoft Defender Antivirus settings</span></span>

<span data-ttu-id="dbd3f-111">これらのポリシーの既定の設定は [無効] **です**。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-111">The default setting for these policies is **Disabled**.</span></span>

<span data-ttu-id="dbd3f-112">[有効] に設定 **されている** 場合、エンドポイントのユーザーは、Windows セキュリティ アプリ、ローカル グループ ポリシー設定、 [および PowerShell](microsoft-defender-security-center-antivirus.md) コマンドレット (必要に応じて) に関連付けられた設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-112">If they are set to **Enabled**, users on endpoints can make changes to the associated setting with the [Windows Security](microsoft-defender-security-center-antivirus.md) app, local Group Policy settings, and PowerShell cmdlets (where appropriate).</span></span>

<span data-ttu-id="dbd3f-113">次の表に、各上書きポリシー設定と、関連する機能または設定の構成手順を示します。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-113">The following table lists each of the override policy setting and the configuration instructions for the associated feature or setting.</span></span>

<span data-ttu-id="dbd3f-114">これらの設定を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-114">To configure these settings:</span></span>

1. <span data-ttu-id="dbd3f-115">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-115">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="dbd3f-116">グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-116">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="dbd3f-117">ツリーを **Microsoft Defender** ウイルス対策> Windows コンポーネントに展開し、次の表で指定した場所を展開します。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-117">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

4. <span data-ttu-id="dbd3f-118">下の表で指定 **したポリシー設定** をダブルクリックし、オプションを目的の構成に設定します。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-118">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> <span data-ttu-id="dbd3f-119">**[OK] を** クリックし、他の設定を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-119">Click **OK**, and repeat for any other settings.</span></span>

5. <span data-ttu-id="dbd3f-120">グループ ポリシー オブジェクトを通常どおり展開します。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-120">Deploy the Group Policy Object as usual.</span></span>

<span data-ttu-id="dbd3f-121">場所</span><span class="sxs-lookup"><span data-stu-id="dbd3f-121">Location</span></span> | <span data-ttu-id="dbd3f-122">設定</span><span class="sxs-lookup"><span data-stu-id="dbd3f-122">Setting</span></span> | <span data-ttu-id="dbd3f-123">記事</span><span class="sxs-lookup"><span data-stu-id="dbd3f-123">Article</span></span>
---|---|---|---
<span data-ttu-id="dbd3f-124">MAPS</span><span class="sxs-lookup"><span data-stu-id="dbd3f-124">MAPS</span></span> | <span data-ttu-id="dbd3f-125">Microsoft MAPS へのレポート用にローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-125">Configure local setting override for reporting to Microsoft MAPS</span></span> | [<span data-ttu-id="dbd3f-126">クラウドによる保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="dbd3f-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="dbd3f-127">検疫する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-127">Quarantine</span></span> | <span data-ttu-id="dbd3f-128">検疫フォルダーからアイテムを削除するローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-128">Configure local setting override for the removal of items from Quarantine folder</span></span> | [<span data-ttu-id="dbd3f-129">スキャンの修復を構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-129">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
<span data-ttu-id="dbd3f-130">リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="dbd3f-130">Real-time protection</span></span> | <span data-ttu-id="dbd3f-131">コンピューター上のファイルとプログラムのアクティビティを監視するローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-131">Configure local setting override for monitoring file and program activity on your computer</span></span> | [<span data-ttu-id="dbd3f-132">Microsoft Defender ウイルス対策の常時オン保護と監視を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-132">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="dbd3f-133">リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="dbd3f-133">Real-time protection</span></span> | <span data-ttu-id="dbd3f-134">受信および送信ファイルのアクティビティを監視するローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-134">Configure local setting override for monitoring for incoming and outgoing file activity</span></span> | [<span data-ttu-id="dbd3f-135">Microsoft Defender ウイルス対策の常時オン保護と監視を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-135">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="dbd3f-136">リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="dbd3f-136">Real-time protection</span></span> | <span data-ttu-id="dbd3f-137">ダウンロードしたファイルと添付ファイルをスキャンするローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-137">Configure local setting override for scanning all downloaded files and attachments</span></span> | [<span data-ttu-id="dbd3f-138">Microsoft Defender ウイルス対策の常時オン保護と監視を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-138">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="dbd3f-139">リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="dbd3f-139">Real-time protection</span></span> | <span data-ttu-id="dbd3f-140">オンの動作監視用にローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-140">Configure local setting override for turn on behavior monitoring</span></span> | [<span data-ttu-id="dbd3f-141">Microsoft Defender ウイルス対策の常時オン保護と監視を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-141">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="dbd3f-142">リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="dbd3f-142">Real-time protection</span></span> | <span data-ttu-id="dbd3f-143">ローカル設定の上書きを構成してリアルタイム保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="dbd3f-143">Configure local setting override to turn on real-time protection</span></span> | [<span data-ttu-id="dbd3f-144">Microsoft Defender ウイルス対策の常時オン保護と監視を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-144">Enable and configure Microsoft Defender Antivirus always-on protection and monitoring</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md)
<span data-ttu-id="dbd3f-145">修復</span><span class="sxs-lookup"><span data-stu-id="dbd3f-145">Remediation</span></span> | <span data-ttu-id="dbd3f-146">スケジュールされたフル スキャンを実行して修復を完了するために、時刻のローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-146">Configure local setting override for the time of day to run a scheduled full scan to complete remediation</span></span> | [<span data-ttu-id="dbd3f-147">スキャンの修復を構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-147">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md)
<span data-ttu-id="dbd3f-148">スキャン</span><span class="sxs-lookup"><span data-stu-id="dbd3f-148">Scan</span></span> | <span data-ttu-id="dbd3f-149">CPU 使用率の最大割合に対するローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-149">Configure local setting override for maximum percentage of CPU utilization</span></span> | [<span data-ttu-id="dbd3f-150">スキャンの構成と実行</span><span class="sxs-lookup"><span data-stu-id="dbd3f-150">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md)
<span data-ttu-id="dbd3f-151">スキャン</span><span class="sxs-lookup"><span data-stu-id="dbd3f-151">Scan</span></span> | <span data-ttu-id="dbd3f-152">スケジュール スキャン日のローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-152">Configure local setting override for schedule scan day</span></span> | [<span data-ttu-id="dbd3f-153">スケジュールされたスキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-153">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="dbd3f-154">スキャン</span><span class="sxs-lookup"><span data-stu-id="dbd3f-154">Scan</span></span> | <span data-ttu-id="dbd3f-155">スケジュールされたクイック スキャン時間のローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-155">Configure local setting override for scheduled quick scan time</span></span> | [<span data-ttu-id="dbd3f-156">スケジュールされたスキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-156">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="dbd3f-157">スキャン</span><span class="sxs-lookup"><span data-stu-id="dbd3f-157">Scan</span></span> | <span data-ttu-id="dbd3f-158">スケジュールされたスキャン時間のローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-158">Configure local setting override for scheduled scan time</span></span> | [<span data-ttu-id="dbd3f-159">スケジュールされたスキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-159">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
<span data-ttu-id="dbd3f-160">スキャン</span><span class="sxs-lookup"><span data-stu-id="dbd3f-160">Scan</span></span> | <span data-ttu-id="dbd3f-161">スケジュールされたスキャンに使用するスキャンの種類のローカル設定の上書きを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-161">Configure local setting override for the scan type to use for a scheduled scan</span></span> | [<span data-ttu-id="dbd3f-162">スケジュールされたスキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-162">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a><span data-ttu-id="dbd3f-163">ローカルおよびグローバルに定義された脅威の修復と除外リストの結合方法を構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-163">Configure how locally and globally defined threat remediation and exclusions lists are merged</span></span>

<span data-ttu-id="dbd3f-164">ローカルに定義されたリストをグローバルに定義されたリストと結合または結合する方法を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-164">You can also configure how locally defined lists are combined or merged with globally defined lists.</span></span> <span data-ttu-id="dbd3f-165">この設定は、除外リスト[、指定された](configure-exclusions-microsoft-defender-antivirus.md)修復リスト、攻撃表面[](configure-remediation-microsoft-defender-antivirus.md)[の縮小に適用されます](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-165">This setting applies to [exclusion lists](configure-exclusions-microsoft-defender-antivirus.md), [specified remediation lists](configure-remediation-microsoft-defender-antivirus.md), and [attack surface reduction](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction).</span></span>

<span data-ttu-id="dbd3f-166">既定では、ローカル グループ ポリシーと Windows セキュリティ アプリで構成されているリストは、ネットワークに展開した適切なグループ ポリシー オブジェクトによって定義されたリストと結合されます。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-166">By default, lists that have been configured in local group policy and the Windows Security app are merged with lists that are defined by the appropriate Group Policy Object that you have deployed on your network.</span></span> <span data-ttu-id="dbd3f-167">競合がある場合は、グローバルに定義されたリストが優先されます。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-167">Where there are conflicts, the globally-defined list takes precedence.</span></span>

<span data-ttu-id="dbd3f-168">この設定を無効にすると、グローバルに定義されたリスト (展開された GPO のリストなど) だけが使用されます。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-168">You can disable this setting to ensure that only globally-defined lists (such as those from any deployed GPOs) are used.</span></span>

### <a name="use-group-policy-to-disable-local-list-merging"></a><span data-ttu-id="dbd3f-169">グループ ポリシーを使用してローカル リストのマージを無効にする</span><span class="sxs-lookup"><span data-stu-id="dbd3f-169">Use Group Policy to disable local list merging</span></span>

1. <span data-ttu-id="dbd3f-170">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-170">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="dbd3f-171">グループ ポリシー **管理エディターで、[コンピューター** の構成] に **移動し、[** 管理用 **テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-171">In the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="dbd3f-172">ツリーを **Microsoft Defender ウイルス対策の Windows コンポーネント>展開します**。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-172">Expand the tree to **Windows components > Microsoft Defender Antivirus**.</span></span>

4. <span data-ttu-id="dbd3f-173">[リストのローカル **管理者の差し込み動作を構成** する] をダブルクリックし、オプションを [無効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-173">Double-click **Configure local administrator merge behavior for lists** and set the option to **Disabled**.</span></span> <span data-ttu-id="dbd3f-174">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-174">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="dbd3f-175">ローカル リストの結合を無効にすると、フォルダー アクセスの制御設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-175">If you disable local list merging, it will override controlled folder access settings.</span></span> <span data-ttu-id="dbd3f-176">また、ローカル管理者が設定した保護されたフォルダーまたは許可されたアプリも上書きされます。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-176">It also overrides any protected folders or allowed apps set by the local administrator.</span></span> <span data-ttu-id="dbd3f-177">フォルダー アクセスの制御設定の詳細については [、「Windows セキュリティでブロックされたアプリを許可する」を参照してください](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security)。</span><span class="sxs-lookup"><span data-stu-id="dbd3f-177">For more information about controlled folder access settings, see [Allow a blocked app in Windows Security](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dbd3f-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="dbd3f-178">Related topics</span></span>

- [<span data-ttu-id="dbd3f-179">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="dbd3f-179">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="dbd3f-180">Microsoft Defender ウイルス対策とのエンド ユーザー操作を構成する</span><span class="sxs-lookup"><span data-stu-id="dbd3f-180">Configure end-user interaction with Microsoft Defender Antivirus</span></span>](configure-end-user-interaction-microsoft-defender-antivirus.md)