---
title: 定期的なクイック スキャンとフル スキャンのスケジュールを設定Microsoft Defender ウイルス対策
description: 定期的な (スケジュールされた) スキャンのセットアップ (実行する必要がある場合、フル スキャンとクイック スキャンの実行のかどうかなど)
keywords: クイック スキャン、フル スキャン、クイックスキャン、フル スキャン、スケジュール スキャン、毎日、毎週、時刻、スケジュール済み、定期的、定期的
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: f1344026878b7fbd6242d82b1afb0e6671c32073
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789270"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="eb608-104">スケジュールされたクイックまたは完全な Microsoft Defender ウイルス スキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="eb608-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="eb608-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="eb608-105">**Applies to:**</span></span>

- [<span data-ttu-id="eb608-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="eb608-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="eb608-107">既定では、Microsoft Defender ウイルス対策スキャンの時刻の 15 分前に更新プログラムがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="eb608-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="eb608-108">保護更新 [プログラムをダウンロードして適用するスケジュール](manage-protection-update-schedule-microsoft-defender-antivirus.md) を管理して、この既定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="eb608-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="eb608-109">常時オンのリアルタイム保護とオンデマンド スキャンに加[](run-scan-microsoft-defender-antivirus.md)えて、定期的にスケジュールされたスキャンを設定できます。</span><span class="sxs-lookup"><span data-stu-id="eb608-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="eb608-110">スキャンの種類、スキャンが実行される時間、および保護更新後にスキャンが実行される場合、または[](manage-protection-updates-microsoft-defender-antivirus.md)エンドポイントが使用されている場合に構成できます。</span><span class="sxs-lookup"><span data-stu-id="eb608-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="eb608-111">修復を完了するための特別なスキャンがいつ行われるのかも指定できます。</span><span class="sxs-lookup"><span data-stu-id="eb608-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="eb608-112">この記事では、グループ ポリシー、PowerShell コマンドレット、WMI を使用してスケジュールされたスキャンを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb608-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="eb608-113">また、スケジュール スキャンを構成するには[、Microsoft Endpoint Configuration Managerまたは](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings)Microsoft Intune。 [](/mem/intune/configuration/device-restrictions-windows-10)</span><span class="sxs-lookup"><span data-stu-id="eb608-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="eb608-114">この記事で説明されているグループ ポリシー設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="eb608-114">To configure the Group Policy settings described in this article</span></span>

1. <span data-ttu-id="eb608-115">グループ ポリシー管理マシンのグループ ポリシー エディターで、[コンピューター構成] [管理用テンプレート] Windows [スキャンMicrosoft Defender ウイルス対策  >    >    >    >  **します**。</span><span class="sxs-lookup"><span data-stu-id="eb608-115">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="eb608-116">構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb608-116">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="eb608-117">グループ ポリシー オブジェクトの設定を指定し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="eb608-117">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="eb608-118">構成する設定ごとに手順 1 ~ 4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="eb608-118">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="eb608-119">通常と同じ方法でグループ ポリシー オブジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="eb608-119">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="eb608-120">グループ ポリシー オブジェクトのヘルプが必要な場合は、「 [グループ ポリシー オブジェクトの作成」を参照してください](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)。</span><span class="sxs-lookup"><span data-stu-id="eb608-120">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

<span data-ttu-id="eb608-121">また、「保護更新プログラム [をダウンロードして](manage-protection-update-schedule-microsoft-defender-antivirus.md) 適用する必要がある場合の管理」および「ユーザーによるポリシー設定のローカル変更を防止または許可する」 [のトピックも参照](configure-local-policy-overrides-microsoft-defender-antivirus.md) してください。</span><span class="sxs-lookup"><span data-stu-id="eb608-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="eb608-122">クイック スキャンとフル スキャン、およびカスタム スキャン</span><span class="sxs-lookup"><span data-stu-id="eb608-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="eb608-123">スケジュールされたスキャンをセットアップするときに、スキャンを完全スキャンとクイック スキャンのかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="eb608-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>


|<span data-ttu-id="eb608-124">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="eb608-124">Quick scan</span></span>  |<span data-ttu-id="eb608-125">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="eb608-125">Full scan</span></span>  | <span data-ttu-id="eb608-126">カスタム スキャン</span><span class="sxs-lookup"><span data-stu-id="eb608-126">Custom scan</span></span> |
|---------|---------|---------|
|<span data-ttu-id="eb608-127">クイック スキャンでは、レジストリ キーや既知のスタートアップ フォルダーなど、システムで起動するマルウェアが登録されている可能性があるすべての場所Windowsします。</span><span class="sxs-lookup"><span data-stu-id="eb608-127">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="eb608-128">ほとんどの場合、クイック スキャンで十分であり、スケジュールされたスキャンに推奨されます。</span><span class="sxs-lookup"><span data-stu-id="eb608-128">In most cases, a quick scan is sufficient and is recommended for scheduled scans.</span></span> |<span data-ttu-id="eb608-129">フル スキャンは、クイック スキャンを実行して開始し、すべてのマウントされた固定ディスクとリムーバブル/ネットワーク ドライブのシーケンシャル ファイル スキャンを続行します (フル スキャンが構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="eb608-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="eb608-130">フル スキャンは、スキャンする必要があるデータの量と種類に応じて、完了に数時間または数日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb608-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="eb608-131">完全スキャンが完了すると、新しいセキュリティ インテリジェンスが利用できます。新しいセキュリティ インテリジェンスで他の脅威が検出されない場合は、新しいスキャンが必要です。</span><span class="sxs-lookup"><span data-stu-id="eb608-131">When the full scan is complete, new security intelligence is available, and a new scan is required to make sure that no other threats are detected with the new security intelligence.</span></span>   | <span data-ttu-id="eb608-132">カスタム スキャンは、指定したファイルとフォルダーで実行されるクイック スキャンです。</span><span class="sxs-lookup"><span data-stu-id="eb608-132">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="eb608-133">たとえば、USB ドライブ、またはデバイスのローカル ドライブ上の特定のフォルダーをスキャンすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="eb608-133">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

>[!NOTE]
><span data-ttu-id="eb608-134">既定では、USB ドライブなどのマウントされたリムーバブル デバイスでクイック スキャンが実行されます。</span><span class="sxs-lookup"><span data-stu-id="eb608-134">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

### <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="eb608-135">選択するスキャンの種類を知る方法</span><span class="sxs-lookup"><span data-stu-id="eb608-135">How do I know which scan type to choose?</span></span>

<span data-ttu-id="eb608-136">次の表を使用して、スキャンの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb608-136">Use the following table to choose a scan type.</span></span>


|<span data-ttu-id="eb608-137">シナリオ</span><span class="sxs-lookup"><span data-stu-id="eb608-137">Scenario</span></span>  |<span data-ttu-id="eb608-138">推奨されるスキャンの種類</span><span class="sxs-lookup"><span data-stu-id="eb608-138">Recommended scan type</span></span>  |
|---------|---------|
|<span data-ttu-id="eb608-139">定期的なスケジュールされたスキャンを設定する</span><span class="sxs-lookup"><span data-stu-id="eb608-139">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="eb608-140">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="eb608-140">Quick scan</span></span> <p><span data-ttu-id="eb608-141">クイック スキャンは、デバイス上のプロセス、メモリ、プロファイル、および特定の場所をチェックします。</span><span class="sxs-lookup"><span data-stu-id="eb608-141">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="eb608-142">常時オン [のリアルタイム保護と](configure-real-time-protection-microsoft-defender-antivirus.md)組み合わせると、クイック スキャンによって、システムから始まるマルウェアとカーネル レベルのマルウェアの両方に強力な範囲を提供できます。</span><span class="sxs-lookup"><span data-stu-id="eb608-142">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="eb608-143">リアルタイム保護は、ファイルを開いて閉じたときに、およびユーザーがフォルダーに移動するたびに、ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="eb608-143">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
|<span data-ttu-id="eb608-144">マルウェアなどの脅威が個々のデバイスで検出される</span><span class="sxs-lookup"><span data-stu-id="eb608-144">Threats, such as malware, are detected on an individual device</span></span>     | <span data-ttu-id="eb608-145">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="eb608-145">Quick scan</span></span> <p><span data-ttu-id="eb608-146">ほとんどの場合、クイック スキャンは検出されたマルウェアをキャッチしてクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="eb608-146">In most cases, a quick scan will catch and clean up detected malware.</span></span>   |
|<span data-ttu-id="eb608-147">オンデマンド スキャンを [実行する](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="eb608-147">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="eb608-148">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="eb608-148">Quick scan</span></span>       |
| <span data-ttu-id="eb608-149">USB ドライブなどのポータブル デバイスにマルウェアが含まれているのを確認する</span><span class="sxs-lookup"><span data-stu-id="eb608-149">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="eb608-150">カスタム スキャン</span><span class="sxs-lookup"><span data-stu-id="eb608-150">Custom scan</span></span> <p><span data-ttu-id="eb608-151">カスタム スキャンを使用すると、特定の場所、フォルダー、またはファイルを選択し、クイック スキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="eb608-151">A custom scan enables you to select specific locations, folders, or files and runs a quick scan.</span></span> |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="eb608-152">クイック スキャンとフル スキャンについて他に何を知る必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="eb608-152">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="eb608-153">悪意のあるファイルは、クイック スキャンに含まれていない場所に保存できます。</span><span class="sxs-lookup"><span data-stu-id="eb608-153">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="eb608-154">ただし、常時オンのリアルタイム保護は、開いて閉じているすべてのファイルと、ユーザーがアクセスするフォルダー内のすべてのファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="eb608-154">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="eb608-155">リアルタイム保護とクイック スキャンの組み合わせは、マルウェアに対する強力な保護を提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="eb608-155">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="eb608-156">クラウドによる保護によるオン[](cloud-protection-microsoft-defender-antivirus.md)アクセス保護により、システム上でアクセスされるすべてのファイルが最新のセキュリティ インテリジェンスとクラウド 機械学習モデルでスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="eb608-156">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="eb608-157">リアルタイム保護でマルウェアが検出され、影響を受けるファイルの範囲が最初に決定されない場合、Microsoft Defender ウイルス対策 は修復プロセスの一環としてフル スキャンを開始します。</span><span class="sxs-lookup"><span data-stu-id="eb608-157">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="eb608-158">フル スキャンでは、クイック スキャンなど、他のスキャンで検出されていない悪意のあるファイルを検出できます。</span><span class="sxs-lookup"><span data-stu-id="eb608-158">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="eb608-159">ただし、フル スキャンには時間がかかる場合があります。また、貴重なシステム リソースを使用して完了できます。</span><span class="sxs-lookup"><span data-stu-id="eb608-159">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="eb608-160">デバイスがオフラインで長期に及ばない場合、フル スキャンの完了に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb608-160">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="eb608-161">スケジュールされたスキャンのセットアップ</span><span class="sxs-lookup"><span data-stu-id="eb608-161">Set up scheduled scans</span></span>

<span data-ttu-id="eb608-162">スケジュールされたスキャンは、指定した日と時刻に実行されます。</span><span class="sxs-lookup"><span data-stu-id="eb608-162">Scheduled scans run on the day and time that you specify.</span></span> <span data-ttu-id="eb608-163">グループ ポリシー、PowerShell、WMI を使用して、スケジュールされたスキャンを構成できます。</span><span class="sxs-lookup"><span data-stu-id="eb608-163">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

> [!NOTE]
> <span data-ttu-id="eb608-164">スケジュールされたフル スキャン中にデバイスがプラグを抜いてバッテリーで実行されている場合、スケジュールされたスキャンはイベント 1002 で停止し、完了前にスキャンが停止したと示されます。</span><span class="sxs-lookup"><span data-stu-id="eb608-164">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="eb608-165">Microsoft Defender ウイルス対策は、次にスケジュールされた時刻にフル スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="eb608-165">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="eb608-166">グループ ポリシーを使用してスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="eb608-166">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="eb608-167">Location</span><span class="sxs-lookup"><span data-stu-id="eb608-167">Location</span></span> | <span data-ttu-id="eb608-168">設定</span><span class="sxs-lookup"><span data-stu-id="eb608-168">Setting</span></span> | <span data-ttu-id="eb608-169">説明</span><span class="sxs-lookup"><span data-stu-id="eb608-169">Description</span></span> | <span data-ttu-id="eb608-170">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="eb608-170">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="eb608-171">スキャン</span><span class="sxs-lookup"><span data-stu-id="eb608-171">Scan</span></span> | <span data-ttu-id="eb608-172">スケジュールされたスキャンに使用するスキャンの種類を指定する</span><span class="sxs-lookup"><span data-stu-id="eb608-172">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="eb608-173">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="eb608-173">Quick scan</span></span> |
|<span data-ttu-id="eb608-174">スキャン</span><span class="sxs-lookup"><span data-stu-id="eb608-174">Scan</span></span> | <span data-ttu-id="eb608-175">スケジュールされたスキャンを実行する週の日を指定する</span><span class="sxs-lookup"><span data-stu-id="eb608-175">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="eb608-176">スキャンを実行する日 (または実行しない) を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb608-176">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="eb608-177">Never</span><span class="sxs-lookup"><span data-stu-id="eb608-177">Never</span></span> |
|<span data-ttu-id="eb608-178">スキャン</span><span class="sxs-lookup"><span data-stu-id="eb608-178">Scan</span></span> | <span data-ttu-id="eb608-179">スケジュールされたスキャンを実行する時刻を指定する</span><span class="sxs-lookup"><span data-stu-id="eb608-179">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="eb608-180">午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。</span><span class="sxs-lookup"><span data-stu-id="eb608-180">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="eb608-181">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="eb608-181">2 a.m.</span></span> |
|<span data-ttu-id="eb608-182">ルート</span><span class="sxs-lookup"><span data-stu-id="eb608-182">Root</span></span> | <span data-ttu-id="eb608-183">スケジュールされたタスク時間をランダム化する</span><span class="sxs-lookup"><span data-stu-id="eb608-183">Randomize scheduled task times</span></span> |<span data-ttu-id="eb608-184">このMicrosoft Defender ウイルス対策、スキャンの開始時刻を 0 ~ 4 時間の任意の間隔にランダム化します。</span><span class="sxs-lookup"><span data-stu-id="eb608-184">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="eb608-185">[SCEP では](/mem/intune/protect/certificates-scep-configure)、スキャンを任意の間隔にプラスまたはマイナス 30 分にランダム化します。</span><span class="sxs-lookup"><span data-stu-id="eb608-185">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="eb608-186">これは、仮想マシンまたは VDI 展開で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="eb608-186">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="eb608-187">Enabled</span><span class="sxs-lookup"><span data-stu-id="eb608-187">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="eb608-188">PowerShell コマンドレットを使用してスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="eb608-188">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="eb608-189">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb608-189">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="eb608-190">詳細については[、「PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して powerShell コマンドレットを構成し、Microsoft Defender ウイルス対策 コマンドレットと Microsoft Defender ウイルス対策[Defender](/powershell/module/defender/)コマンドレットを実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb608-190">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="eb608-191">スキャンをWindowsする場合は、管理命令 (WMI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="eb608-191">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="eb608-192">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb608-192">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="eb608-193">詳細および許可されるパラメーターについては[、「WMIv2 API のWindows Defender参照してください。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="eb608-193">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="eb608-194">エンドポイントが使用されていない場合にのみ、スケジュールされたスキャンを開始する</span><span class="sxs-lookup"><span data-stu-id="eb608-194">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="eb608-195">スケジュールされたスキャンは、エンドポイントがオンになっているが、グループ ポリシー、PowerShell、または WMI で使用されていない場合にのみ発生する設定できます。</span><span class="sxs-lookup"><span data-stu-id="eb608-195">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="eb608-196">これらのスキャンは、CPU 調整構成を尊重し、可能な限り速くスキャンを完了するために利用可能なリソースをフルに活用します。</span><span class="sxs-lookup"><span data-stu-id="eb608-196">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="eb608-197">グループ ポリシーを使用してスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="eb608-197">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="eb608-198">Location</span><span class="sxs-lookup"><span data-stu-id="eb608-198">Location</span></span> | <span data-ttu-id="eb608-199">設定</span><span class="sxs-lookup"><span data-stu-id="eb608-199">Setting</span></span> | <span data-ttu-id="eb608-200">説明</span><span class="sxs-lookup"><span data-stu-id="eb608-200">Description</span></span> | <span data-ttu-id="eb608-201">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="eb608-201">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="eb608-202">スキャン</span><span class="sxs-lookup"><span data-stu-id="eb608-202">Scan</span></span> | <span data-ttu-id="eb608-203">コンピューターがオンで、使用されていない場合にのみ、スケジュールされたスキャンを開始する</span><span class="sxs-lookup"><span data-stu-id="eb608-203">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="eb608-204">コンピューターがオンで使用されていない場合、スケジュールされたスキャンは実行されません。</span><span class="sxs-lookup"><span data-stu-id="eb608-204">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="eb608-205">Enabled</span><span class="sxs-lookup"><span data-stu-id="eb608-205">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="eb608-206">PowerShell コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="eb608-206">Use PowerShell cmdlets</span></span>

<span data-ttu-id="eb608-207">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb608-207">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="eb608-208">詳細については、「[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および実行する](use-powershell-cmdlets-microsoft-defender-antivirus.md)」および「[Defender コマンドレット](/powershell/module/defender/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb608-208">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="eb608-209">管理Windows使用 (WMI)</span><span class="sxs-lookup"><span data-stu-id="eb608-209">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="eb608-210">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb608-210">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="eb608-211">API と許可パラメーターの詳細については[、「WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)のWindows Defender参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb608-211">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="eb608-212">修復を完了するためにフル スキャンを実行する必要がある場合の構成</span><span class="sxs-lookup"><span data-stu-id="eb608-212">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="eb608-213">一部の脅威では、削除と修復を完了するためにフル スキャンが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb608-213">Some threats might require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="eb608-214">これらのスキャンをグループ ポリシー、PowerShell、または WMI で実行する必要がある場合に指定できます。</span><span class="sxs-lookup"><span data-stu-id="eb608-214">You can specify when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="eb608-215">グループ ポリシーを使用して修復に必要なスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="eb608-215">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="eb608-216">Location</span><span class="sxs-lookup"><span data-stu-id="eb608-216">Location</span></span> | <span data-ttu-id="eb608-217">設定</span><span class="sxs-lookup"><span data-stu-id="eb608-217">Setting</span></span> | <span data-ttu-id="eb608-218">説明</span><span class="sxs-lookup"><span data-stu-id="eb608-218">Description</span></span> | <span data-ttu-id="eb608-219">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="eb608-219">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="eb608-220">修復</span><span class="sxs-lookup"><span data-stu-id="eb608-220">Remediation</span></span> | <span data-ttu-id="eb608-221">スケジュールされたフル スキャンを実行して修復を完了する日を指定する</span><span class="sxs-lookup"><span data-stu-id="eb608-221">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="eb608-222">スキャンを実行する日 (または実行しない) を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb608-222">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="eb608-223">Never</span><span class="sxs-lookup"><span data-stu-id="eb608-223">Never</span></span> |
|<span data-ttu-id="eb608-224">修復</span><span class="sxs-lookup"><span data-stu-id="eb608-224">Remediation</span></span> | <span data-ttu-id="eb608-225">スケジュールされたフル スキャンを実行して修復を完了する時刻を指定する</span><span class="sxs-lookup"><span data-stu-id="eb608-225">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="eb608-226">午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。</span><span class="sxs-lookup"><span data-stu-id="eb608-226">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="eb608-227">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="eb608-227">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="eb608-228">PowerShell コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="eb608-228">Use PowerShell cmdlets</span></span>

<span data-ttu-id="eb608-229">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb608-229">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="eb608-230">PowerShell[コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)構成して実行する方法の詳細については、「powerShell コマンドレットを使用して Microsoft Defender ウイルス対策 および[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照Microsoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="eb608-230">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="eb608-231">管理Windows使用 (WMI)</span><span class="sxs-lookup"><span data-stu-id="eb608-231">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="eb608-232">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb608-232">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="eb608-233">詳細および許可されるパラメーターについては[、「WMIv2 API Windows Defender参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="eb608-233">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="eb608-234">毎日のクイック スキャンをセットアップする</span><span class="sxs-lookup"><span data-stu-id="eb608-234">Set up daily quick scans</span></span>

<span data-ttu-id="eb608-235">グループ ポリシー、PowerShell、または WMI を使用して、他のスケジュールされたスキャンに加えて実行できる毎日のクイック スキャンを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="eb608-235">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="eb608-236">グループ ポリシーを使用して毎日のスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="eb608-236">Use Group Policy to schedule daily scans</span></span>

|<span data-ttu-id="eb608-237">Location</span><span class="sxs-lookup"><span data-stu-id="eb608-237">Location</span></span> | <span data-ttu-id="eb608-238">設定</span><span class="sxs-lookup"><span data-stu-id="eb608-238">Setting</span></span> | <span data-ttu-id="eb608-239">説明</span><span class="sxs-lookup"><span data-stu-id="eb608-239">Description</span></span> | <span data-ttu-id="eb608-240">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="eb608-240">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="eb608-241">スキャン</span><span class="sxs-lookup"><span data-stu-id="eb608-241">Scan</span></span> | <span data-ttu-id="eb608-242">1 日あたりのクイック スキャンを実行する間隔を指定する</span><span class="sxs-lookup"><span data-stu-id="eb608-242">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="eb608-243">次のクイック スキャンの前に経過する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb608-243">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="eb608-244">たとえば、2 時間ごとに実行するには **、「2」と入力し、1** 日 1 回は **24 と入力します**。</span><span class="sxs-lookup"><span data-stu-id="eb608-244">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="eb608-245">**0 と入力** すると、毎日のクイック スキャンは実行されません。</span><span class="sxs-lookup"><span data-stu-id="eb608-245">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="eb608-246">Never</span><span class="sxs-lookup"><span data-stu-id="eb608-246">Never</span></span> |
|<span data-ttu-id="eb608-247">スキャン</span><span class="sxs-lookup"><span data-stu-id="eb608-247">Scan</span></span> | <span data-ttu-id="eb608-248">毎日のクイック スキャンの時間を指定する</span><span class="sxs-lookup"><span data-stu-id="eb608-248">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="eb608-249">午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。</span><span class="sxs-lookup"><span data-stu-id="eb608-249">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="eb608-250">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="eb608-250">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="eb608-251">PowerShell コマンドレットを使用して毎日のスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="eb608-251">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="eb608-252">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb608-252">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="eb608-253">PowerShell を Microsoft Defender ウイルス対策 と一緒に使用する方法の詳細については[、「Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して、PowerShell コマンドレットと Defender コマンドレットを構成Microsoft Defender ウイルス対策実行する」を[参照してください](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="eb608-253">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="eb608-254">毎日のWindowsをスケジュールするには、WMI 管理命令 (WMI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="eb608-254">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="eb608-255">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="eb608-255">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="eb608-256">詳細および許可されるパラメーターについては[、「WMIv2 API Windows Defender参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="eb608-256">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="eb608-257">保護更新後にスキャンを有効にする</span><span class="sxs-lookup"><span data-stu-id="eb608-257">Enable scans after protection updates</span></span>

<span data-ttu-id="eb608-258">グループ ポリシーを使用してすべての保護更新後にスキャン [を強制的](manage-protection-updates-microsoft-defender-antivirus.md) に実行できます。</span><span class="sxs-lookup"><span data-stu-id="eb608-258">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="eb608-259">グループ ポリシーを使用して保護の更新後にスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="eb608-259">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="eb608-260">Location</span><span class="sxs-lookup"><span data-stu-id="eb608-260">Location</span></span> | <span data-ttu-id="eb608-261">設定</span><span class="sxs-lookup"><span data-stu-id="eb608-261">Setting</span></span> | <span data-ttu-id="eb608-262">説明</span><span class="sxs-lookup"><span data-stu-id="eb608-262">Description</span></span> | <span data-ttu-id="eb608-263">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="eb608-263">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="eb608-264">署名の更新</span><span class="sxs-lookup"><span data-stu-id="eb608-264">Signature updates</span></span> | <span data-ttu-id="eb608-265">セキュリティ インテリジェンスの更新後にスキャンを有効にする</span><span class="sxs-lookup"><span data-stu-id="eb608-265">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="eb608-266">新しい保護更新プログラムがダウンロードされた直後にスキャンが実行されます</span><span class="sxs-lookup"><span data-stu-id="eb608-266">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="eb608-267">Enabled</span><span class="sxs-lookup"><span data-stu-id="eb608-267">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="eb608-268">関連項目</span><span class="sxs-lookup"><span data-stu-id="eb608-268">See also</span></span>

- [<span data-ttu-id="eb608-269">ユーザーによるポリシー設定のローカル変更を防止または許可する</span><span class="sxs-lookup"><span data-stu-id="eb608-269">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eb608-270">オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する</span><span class="sxs-lookup"><span data-stu-id="eb608-270">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eb608-271">Microsoft Defender ウイルス対策スキャン オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="eb608-271">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eb608-272">更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する</span><span class="sxs-lookup"><span data-stu-id="eb608-272">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="eb608-273">保護更新プログラムをダウンロードして適用する場合の管理</span><span class="sxs-lookup"><span data-stu-id="eb608-273">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="eb608-274">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="eb608-274">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)