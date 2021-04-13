---
title: Microsoft Defender ウイルス対策で定期的なクイック スキャンとフル スキャンをスケジュールする
description: 定期的な (スケジュールされた) スキャンのセットアップ (実行する必要がある場合、フル スキャンとクイック スキャンの実行のかどうかなど)
keywords: クイック スキャン、フル スキャン、クイックスキャン、フル スキャン、スケジュール スキャン、毎日、毎週、時刻、スケジュール済み、定期的、定期的
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/02/2020
ms.reviewer: pauhijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 66907fca7a117eeba7ca0b9bd95d59af24c31341
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691300"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="e4966-104">スケジュールされたクイック スキャンまたはフル Microsoft Defender ウイルス対策スキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="e4966-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e4966-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="e4966-105">**Applies to:**</span></span>

- [<span data-ttu-id="e4966-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e4966-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="e4966-107">既定では、Microsoft Defender ウイルス対策は、スケジュールされたスキャンの 15 分前に更新プログラムをチェックします。</span><span class="sxs-lookup"><span data-stu-id="e4966-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="e4966-108">保護更新 [プログラムをダウンロードして適用するスケジュール](manage-protection-update-schedule-microsoft-defender-antivirus.md) を管理して、この既定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="e4966-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="e4966-109">常時オンのリアルタイム保護とオンデマンド スキャンに加[](run-scan-microsoft-defender-antivirus.md)えて、定期的にスケジュールされたスキャンを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4966-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="e4966-110">スキャンの種類、スキャンが実行される時間、および保護更新後にスキャンが実行される場合、または[](manage-protection-updates-microsoft-defender-antivirus.md)エンドポイントが使用されている場合に構成できます。</span><span class="sxs-lookup"><span data-stu-id="e4966-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="e4966-111">修復を完了するための特別なスキャンがいつ行われるのかも指定できます。</span><span class="sxs-lookup"><span data-stu-id="e4966-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="e4966-112">この記事では、グループ ポリシー、PowerShell コマンドレット、WMI を使用してスケジュールされたスキャンを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e4966-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="e4966-113">Microsoft Endpoint [Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) または Microsoft Intune を使用してスケジュール スキャンを [構成することもできます](/mem/intune/configuration/device-restrictions-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="e4966-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="e4966-114">この記事で説明されているグループ ポリシー設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="e4966-114">To configure the Group Policy settings described in this article</span></span>

1.  <span data-ttu-id="e4966-115">グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="e4966-115">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="e4966-116">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="e4966-116">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="e4966-117">[管理 **用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e4966-117">Click **Administrative templates**.</span></span>

5.  <span data-ttu-id="e4966-118">ツリーを **Microsoft Defender** ウイルス対策> Windows コンポーネントに展開し、次の表で指定した場所を展開します。</span><span class="sxs-lookup"><span data-stu-id="e4966-118">Expand the tree to **Windows components > Microsoft Defender Antivirus** and then the **Location** specified in the table below.</span></span>

6. <span data-ttu-id="e4966-119">下の表で指定 **したポリシー設定** をダブルクリックし、オプションを目的の構成に設定します。</span><span class="sxs-lookup"><span data-stu-id="e4966-119">Double-click the policy **Setting** as specified in the table below, and set the option to your desired configuration.</span></span> 

7. <span data-ttu-id="e4966-120">**[OK] を** クリックし、他の設定を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="e4966-120">Click **OK**, and repeat for any other settings.</span></span>

<span data-ttu-id="e4966-121">また、「保護更新プログラム [をダウンロードして](manage-protection-update-schedule-microsoft-defender-antivirus.md) 適用する必要がある場合の管理」および「ユーザーによるポリシー設定のローカル変更を防止または許可する」 [のトピックも参照](configure-local-policy-overrides-microsoft-defender-antivirus.md) してください。</span><span class="sxs-lookup"><span data-stu-id="e4966-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="e4966-122">クイック スキャンとフル スキャン、およびカスタム スキャン</span><span class="sxs-lookup"><span data-stu-id="e4966-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="e4966-123">スケジュールされたスキャンをセットアップするときに、スキャンを完全スキャンとクイック スキャンのかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4966-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>

<span data-ttu-id="e4966-124">クイック スキャンでは、レジストリ キーや既知の Windows スタートアップ フォルダーなど、システムで起動するマルウェアが登録されている可能性があるすべての場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="e4966-124">Quick scans look at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="e4966-125">ファイルを[](configure-real-time-protection-microsoft-defender-antivirus.md)開いて閉じたときに確認する常時オンのリアルタイム保護機能と組み合わせると、ユーザーがフォルダーに移動するたびに、クイック スキャンを実行すると、システムとカーネル レベルのマルウェアから始まるマルウェアの両方を強力にカバーできます。</span><span class="sxs-lookup"><span data-stu-id="e4966-125">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md) - which reviews files when they are opened and closed, and whenever a user navigates to a folder - a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="e4966-126">ほとんどの場合、クイック スキャンは、リアルタイム保護によって検出されていないマルウェアを見つけるのに十分な手段です。</span><span class="sxs-lookup"><span data-stu-id="e4966-126">In most instances, this means a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="e4966-127">フル スキャンは、マルウェアの脅威が発生したエンドポイントで、より完全なクリーンアップを必要とする非アクティブなコンポーネントが含めらな場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e4966-127">A full scan can be useful on endpoints that have encountered a malware threat to identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="e4966-128">この例では、オンデマンド スキャンを実行するときにフル スキャン [を使用できます](run-scan-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="e4966-128">In this instance, you may want to use a full scan when running an [on-demand scan](run-scan-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="e4966-129">カスタム スキャンを使用すると、スキャンするファイルとフォルダー (USB ドライブなど) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="e4966-129">A custom scan allows you to specify the files and folders to scan, such as a USB drive.</span></span> 

>[!NOTE]
><span data-ttu-id="e4966-130">既定では、USB ドライブなどのマウントされたリムーバブル デバイスでクイック スキャンが実行されます。</span><span class="sxs-lookup"><span data-stu-id="e4966-130">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="e4966-131">スケジュールされたスキャンのセットアップ</span><span class="sxs-lookup"><span data-stu-id="e4966-131">Set up scheduled scans</span></span>

<span data-ttu-id="e4966-132">スケジュールされたスキャンは、指定した日と時刻に実行されます。</span><span class="sxs-lookup"><span data-stu-id="e4966-132">Scheduled scans will run at the day and time you specify.</span></span> <span data-ttu-id="e4966-133">グループ ポリシー、PowerShell、WMI を使用して、スケジュールされたスキャンを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e4966-133">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

>[!NOTE]
><span data-ttu-id="e4966-134">予約済みフル スキャン中にコンピューターがプラグを抜いてバッテリーで実行されている場合、スケジュールされたスキャンはイベント 1002 で停止し、完了前にスキャンが停止したと示されます。</span><span class="sxs-lookup"><span data-stu-id="e4966-134">If a computer is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="e4966-135">Microsoft Defender ウイルス対策は、次回のスケジュールされた時刻にフル スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="e4966-135">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="e4966-136">グループ ポリシーを使用してスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="e4966-136">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="e4966-137">場所</span><span class="sxs-lookup"><span data-stu-id="e4966-137">Location</span></span> | <span data-ttu-id="e4966-138">設定</span><span class="sxs-lookup"><span data-stu-id="e4966-138">Setting</span></span> | <span data-ttu-id="e4966-139">説明</span><span class="sxs-lookup"><span data-stu-id="e4966-139">Description</span></span> | <span data-ttu-id="e4966-140">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="e4966-140">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="e4966-141">スキャン</span><span class="sxs-lookup"><span data-stu-id="e4966-141">Scan</span></span> | <span data-ttu-id="e4966-142">スケジュールされたスキャンに使用するスキャンの種類を指定する</span><span class="sxs-lookup"><span data-stu-id="e4966-142">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="e4966-143">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="e4966-143">Quick scan</span></span> |
|<span data-ttu-id="e4966-144">スキャン</span><span class="sxs-lookup"><span data-stu-id="e4966-144">Scan</span></span> | <span data-ttu-id="e4966-145">スケジュールされたスキャンを実行する週の日を指定する</span><span class="sxs-lookup"><span data-stu-id="e4966-145">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="e4966-146">スキャンを実行する日 (または実行しない) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4966-146">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="e4966-147">Never</span><span class="sxs-lookup"><span data-stu-id="e4966-147">Never</span></span> |
|<span data-ttu-id="e4966-148">スキャン</span><span class="sxs-lookup"><span data-stu-id="e4966-148">Scan</span></span> | <span data-ttu-id="e4966-149">スケジュールされたスキャンを実行する時刻を指定する</span><span class="sxs-lookup"><span data-stu-id="e4966-149">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="e4966-150">午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。</span><span class="sxs-lookup"><span data-stu-id="e4966-150">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="e4966-151">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="e4966-151">2 a.m.</span></span> |
|<span data-ttu-id="e4966-152">ルート</span><span class="sxs-lookup"><span data-stu-id="e4966-152">Root</span></span> | <span data-ttu-id="e4966-153">スケジュールされたタスク時間をランダム化する</span><span class="sxs-lookup"><span data-stu-id="e4966-153">Randomize scheduled task times</span></span> |<span data-ttu-id="e4966-154">Microsoft Defender ウイルス対策: スキャンの開始時刻を 0 ~ 4 時間の任意の間隔にランダム化します。</span><span class="sxs-lookup"><span data-stu-id="e4966-154">In Microsoft Defender Antivirus: Randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <br><span data-ttu-id="e4966-155">FEP/SCEP: 任意の間隔にプラスまたはマイナス 30 分にランダム化します。</span><span class="sxs-lookup"><span data-stu-id="e4966-155">In FEP/SCEP: randomize to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="e4966-156">これは、VM または VDI の展開で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e4966-156">This can be useful in VM or VDI deployments.</span></span> | <span data-ttu-id="e4966-157">Enabled</span><span class="sxs-lookup"><span data-stu-id="e4966-157">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="e4966-158">PowerShell コマンドレットを使用してスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="e4966-158">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="e4966-159">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4966-159">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="e4966-160">[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4966-160">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="e4966-161">Windows 管理命令 (WMI) を使用してスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="e4966-161">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="e4966-162">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4966-162">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="e4966-163">詳細と許可されるパラメーターについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4966-163">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="e4966-164">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="e4966-164">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="e4966-165">エンドポイントが使用されていない場合にのみ、スケジュールされたスキャンを開始する</span><span class="sxs-lookup"><span data-stu-id="e4966-165">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="e4966-166">スケジュールされたスキャンは、エンドポイントがオンになっているが、グループ ポリシー、PowerShell、または WMI で使用されていない場合にのみ発生する設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4966-166">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="e4966-167">これらのスキャンは、CPU 調整構成を尊重し、可能な限り速くスキャンを完了するために利用可能なリソースをフルに活用します。</span><span class="sxs-lookup"><span data-stu-id="e4966-167">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="e4966-168">グループ ポリシーを使用してスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="e4966-168">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="e4966-169">場所</span><span class="sxs-lookup"><span data-stu-id="e4966-169">Location</span></span> | <span data-ttu-id="e4966-170">設定</span><span class="sxs-lookup"><span data-stu-id="e4966-170">Setting</span></span> | <span data-ttu-id="e4966-171">説明</span><span class="sxs-lookup"><span data-stu-id="e4966-171">Description</span></span> | <span data-ttu-id="e4966-172">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="e4966-172">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="e4966-173">スキャン</span><span class="sxs-lookup"><span data-stu-id="e4966-173">Scan</span></span> | <span data-ttu-id="e4966-174">コンピューターがオンで、使用されていない場合にのみ、スケジュールされたスキャンを開始する</span><span class="sxs-lookup"><span data-stu-id="e4966-174">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="e4966-175">コンピューターがオンで使用されていない場合、スケジュールされたスキャンは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e4966-175">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="e4966-176">Enabled</span><span class="sxs-lookup"><span data-stu-id="e4966-176">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="e4966-177">PowerShell コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="e4966-177">Use PowerShell cmdlets</span></span>

<span data-ttu-id="e4966-178">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4966-178">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="e4966-179">[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4966-179">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="e4966-180">Windows 管理命令 (WMI) の使用</span><span class="sxs-lookup"><span data-stu-id="e4966-180">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="e4966-181">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4966-181">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="e4966-182">詳細と許可されるパラメーターについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4966-182">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="e4966-183">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="e4966-183">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="e4966-184">修復を完了するためにフル スキャンを実行する必要がある場合の構成</span><span class="sxs-lookup"><span data-stu-id="e4966-184">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="e4966-185">一部の脅威では、削除と修復を完了するためにフル スキャンが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="e4966-185">Some threats may require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="e4966-186">これらのスキャンをグループ ポリシー、PowerShell、または WMI で実行するスケジュールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="e4966-186">You can schedule when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="e4966-187">グループ ポリシーを使用して修復に必要なスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="e4966-187">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="e4966-188">場所</span><span class="sxs-lookup"><span data-stu-id="e4966-188">Location</span></span> | <span data-ttu-id="e4966-189">設定</span><span class="sxs-lookup"><span data-stu-id="e4966-189">Setting</span></span> | <span data-ttu-id="e4966-190">説明</span><span class="sxs-lookup"><span data-stu-id="e4966-190">Description</span></span> | <span data-ttu-id="e4966-191">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="e4966-191">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="e4966-192">修復</span><span class="sxs-lookup"><span data-stu-id="e4966-192">Remediation</span></span> | <span data-ttu-id="e4966-193">スケジュールされたフル スキャンを実行して修復を完了する日を指定する</span><span class="sxs-lookup"><span data-stu-id="e4966-193">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="e4966-194">スキャンを実行する日 (または実行しない) を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4966-194">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="e4966-195">Never</span><span class="sxs-lookup"><span data-stu-id="e4966-195">Never</span></span> |
|<span data-ttu-id="e4966-196">修復</span><span class="sxs-lookup"><span data-stu-id="e4966-196">Remediation</span></span> | <span data-ttu-id="e4966-197">スケジュールされたフル スキャンを実行して修復を完了する時刻を指定する</span><span class="sxs-lookup"><span data-stu-id="e4966-197">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="e4966-198">午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。</span><span class="sxs-lookup"><span data-stu-id="e4966-198">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="e4966-199">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="e4966-199">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="e4966-200">PowerShell コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="e4966-200">Use PowerShell cmdlets</span></span>

<span data-ttu-id="e4966-201">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4966-201">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="e4966-202">[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4966-202">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="e4966-203">Windows 管理命令 (WMI) の使用</span><span class="sxs-lookup"><span data-stu-id="e4966-203">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="e4966-204">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4966-204">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="e4966-205">詳細と許可されるパラメーターについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4966-205">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="e4966-206">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="e4966-206">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)




## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="e4966-207">毎日のクイック スキャンをセットアップする</span><span class="sxs-lookup"><span data-stu-id="e4966-207">Set up daily quick scans</span></span>

<span data-ttu-id="e4966-208">グループ ポリシー、PowerShell、または WMI を使用して、他のスケジュールされたスキャンに加えて実行できる毎日のクイック スキャンを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="e4966-208">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>


### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="e4966-209">グループ ポリシーを使用して毎日のスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="e4966-209">Use Group Policy to schedule daily scans</span></span>


|<span data-ttu-id="e4966-210">場所</span><span class="sxs-lookup"><span data-stu-id="e4966-210">Location</span></span> | <span data-ttu-id="e4966-211">設定</span><span class="sxs-lookup"><span data-stu-id="e4966-211">Setting</span></span> | <span data-ttu-id="e4966-212">説明</span><span class="sxs-lookup"><span data-stu-id="e4966-212">Description</span></span> | <span data-ttu-id="e4966-213">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="e4966-213">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="e4966-214">スキャン</span><span class="sxs-lookup"><span data-stu-id="e4966-214">Scan</span></span> | <span data-ttu-id="e4966-215">1 日あたりのクイック スキャンを実行する間隔を指定する</span><span class="sxs-lookup"><span data-stu-id="e4966-215">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="e4966-216">次のクイック スキャンの前に経過する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="e4966-216">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="e4966-217">たとえば、2 時間ごとに実行するには **、「2」と入力し、1** 日 1 回は **24 と入力します**。</span><span class="sxs-lookup"><span data-stu-id="e4966-217">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="e4966-218">**0 と入力** すると、毎日のクイック スキャンは実行されません。</span><span class="sxs-lookup"><span data-stu-id="e4966-218">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="e4966-219">Never</span><span class="sxs-lookup"><span data-stu-id="e4966-219">Never</span></span> |
|<span data-ttu-id="e4966-220">スキャン</span><span class="sxs-lookup"><span data-stu-id="e4966-220">Scan</span></span> | <span data-ttu-id="e4966-221">毎日のクイック スキャンの時間を指定する</span><span class="sxs-lookup"><span data-stu-id="e4966-221">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="e4966-222">午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。</span><span class="sxs-lookup"><span data-stu-id="e4966-222">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="e4966-223">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="e4966-223">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="e4966-224">PowerShell コマンドレットを使用して毎日のスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="e4966-224">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="e4966-225">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4966-225">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="e4966-226">[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4966-226">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="e4966-227">Windows 管理命令 (WMI) を使用して毎日のスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="e4966-227">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="e4966-228">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="e4966-228">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="e4966-229">詳細と許可されるパラメーターについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4966-229">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="e4966-230">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="e4966-230">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="e4966-231">保護更新後にスキャンを有効にする</span><span class="sxs-lookup"><span data-stu-id="e4966-231">Enable scans after protection updates</span></span>

<span data-ttu-id="e4966-232">グループ ポリシーを使用してすべての保護更新後にスキャン [を強制的](manage-protection-updates-microsoft-defender-antivirus.md) に実行できます。</span><span class="sxs-lookup"><span data-stu-id="e4966-232">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="e4966-233">グループ ポリシーを使用して保護の更新後にスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="e4966-233">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="e4966-234">場所</span><span class="sxs-lookup"><span data-stu-id="e4966-234">Location</span></span> | <span data-ttu-id="e4966-235">設定</span><span class="sxs-lookup"><span data-stu-id="e4966-235">Setting</span></span> | <span data-ttu-id="e4966-236">説明</span><span class="sxs-lookup"><span data-stu-id="e4966-236">Description</span></span> | <span data-ttu-id="e4966-237">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="e4966-237">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="e4966-238">署名の更新</span><span class="sxs-lookup"><span data-stu-id="e4966-238">Signature updates</span></span> | <span data-ttu-id="e4966-239">セキュリティ インテリジェンスの更新後にスキャンを有効にする</span><span class="sxs-lookup"><span data-stu-id="e4966-239">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="e4966-240">新しい保護更新プログラムがダウンロードされた直後にスキャンが実行されます</span><span class="sxs-lookup"><span data-stu-id="e4966-240">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="e4966-241">Enabled</span><span class="sxs-lookup"><span data-stu-id="e4966-241">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="e4966-242">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4966-242">See also</span></span>
- [<span data-ttu-id="e4966-243">ユーザーによるポリシー設定のローカル変更を防止または許可する</span><span class="sxs-lookup"><span data-stu-id="e4966-243">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e4966-244">Microsoft Defender ウイルス対策スキャンの構成と実行</span><span class="sxs-lookup"><span data-stu-id="e4966-244">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e4966-245">Microsoft Defender ウイルス対策スキャン オプションの構成</span><span class="sxs-lookup"><span data-stu-id="e4966-245">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e4966-246">Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する</span><span class="sxs-lookup"><span data-stu-id="e4966-246">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e4966-247">保護更新プログラムをダウンロードして適用する場合の管理</span><span class="sxs-lookup"><span data-stu-id="e4966-247">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="e4966-248">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="e4966-248">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)