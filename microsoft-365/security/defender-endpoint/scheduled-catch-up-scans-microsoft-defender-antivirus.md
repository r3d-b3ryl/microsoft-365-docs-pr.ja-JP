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
ms.date: 05/05/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 1748a33be2c27123eb0437784dcdb2cb7905616a
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274690"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="8886d-104">スケジュールされたクイックまたは完全な Microsoft Defender ウイルス スキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="8886d-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="8886d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8886d-105">**Applies to:**</span></span>

- [<span data-ttu-id="8886d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8886d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


> [!NOTE]
> <span data-ttu-id="8886d-107">既定では、Microsoft Defender ウイルス対策スキャンの時刻の 15 分前に更新プログラムがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="8886d-107">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="8886d-108">保護更新 [プログラムをダウンロードして適用するスケジュール](manage-protection-update-schedule-microsoft-defender-antivirus.md) を管理して、この既定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="8886d-108">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

<span data-ttu-id="8886d-109">常時オンのリアルタイム保護とオンデマンド スキャンに加[](run-scan-microsoft-defender-antivirus.md)えて、定期的にスケジュールされたスキャンを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8886d-109">In addition to always-on real-time protection and [on-demand](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled scans.</span></span> 

<span data-ttu-id="8886d-110">スキャンの種類、スキャンが実行される時間、および保護更新後にスキャンが実行される場合、または[](manage-protection-updates-microsoft-defender-antivirus.md)エンドポイントが使用されている場合に構成できます。</span><span class="sxs-lookup"><span data-stu-id="8886d-110">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or if the endpoint is being used.</span></span> <span data-ttu-id="8886d-111">修復を完了するための特別なスキャンがいつ行われるのかも指定できます。</span><span class="sxs-lookup"><span data-stu-id="8886d-111">You can also specify when special scans to complete remediation should occur.</span></span>

<span data-ttu-id="8886d-112">この記事では、グループ ポリシー、PowerShell コマンドレット、WMI を使用してスケジュールされたスキャンを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8886d-112">This article describes how to configure scheduled scans with Group Policy, PowerShell cmdlets, and WMI.</span></span> <span data-ttu-id="8886d-113">また、スケジュール スキャンを構成するには[、Microsoft Endpoint Configuration Managerまたは](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings)Microsoft Intune。 [](/mem/intune/configuration/device-restrictions-windows-10)</span><span class="sxs-lookup"><span data-stu-id="8886d-113">You can also configure schedules scans with [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#scheduled-scans-settings) or [Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10).</span></span>

## <a name="to-configure-the-group-policy-settings-described-in-this-article"></a><span data-ttu-id="8886d-114">この記事で説明されているグループ ポリシー設定を構成するには</span><span class="sxs-lookup"><span data-stu-id="8886d-114">To configure the Group Policy settings described in this article</span></span>

1. <span data-ttu-id="8886d-115">グループ ポリシー管理マシンのグループ ポリシー エディターで、[コンピューター構成] [管理用テンプレート] Windows [スキャンMicrosoft Defender ウイルス対策  >    >    >    >  **します**。</span><span class="sxs-lookup"><span data-stu-id="8886d-115">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="8886d-116">構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="8886d-116">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="8886d-117">グループ ポリシー オブジェクトの設定を指定し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="8886d-117">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="8886d-118">構成する設定ごとに手順 1 ~ 4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="8886d-118">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="8886d-119">通常と同じ方法でグループ ポリシー オブジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="8886d-119">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="8886d-120">グループ ポリシー オブジェクトのヘルプが必要な場合は、「 [グループ ポリシー オブジェクトの作成」を参照してください](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)。</span><span class="sxs-lookup"><span data-stu-id="8886d-120">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

<span data-ttu-id="8886d-121">また、「保護更新プログラム [をダウンロードして](manage-protection-update-schedule-microsoft-defender-antivirus.md) 適用する必要がある場合の管理」および「ユーザーによるポリシー設定のローカル変更を防止または許可する」 [のトピックも参照](configure-local-policy-overrides-microsoft-defender-antivirus.md) してください。</span><span class="sxs-lookup"><span data-stu-id="8886d-121">Also see the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="quick-scan-versus-full-scan-and-custom-scan"></a><span data-ttu-id="8886d-122">クイック スキャンとフル スキャン、およびカスタム スキャン</span><span class="sxs-lookup"><span data-stu-id="8886d-122">Quick scan versus full scan and custom scan</span></span>

<span data-ttu-id="8886d-123">スケジュールされたスキャンをセットアップするときに、スキャンを完全スキャンとクイック スキャンのかどうかを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8886d-123">When you set up scheduled scans, you can set up whether the scan should be a full or quick scan.</span></span>


|<span data-ttu-id="8886d-124">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="8886d-124">Quick scan</span></span>  |<span data-ttu-id="8886d-125">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="8886d-125">Full scan</span></span>  | <span data-ttu-id="8886d-126">カスタム スキャン</span><span class="sxs-lookup"><span data-stu-id="8886d-126">Custom scan</span></span> |
|---------|---------|---------|
|<span data-ttu-id="8886d-127">クイック スキャンでは、レジストリ キーや既知のスタートアップ フォルダーなど、システムで起動するマルウェアが登録されている可能性があるすべての場所Windowsします。</span><span class="sxs-lookup"><span data-stu-id="8886d-127">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="8886d-128">ほとんどの場合、クイック スキャンで十分であり、スケジュールされたスキャンに推奨されます。</span><span class="sxs-lookup"><span data-stu-id="8886d-128">In most cases, a quick scan is sufficient and is recommended for scheduled scans.</span></span> |<span data-ttu-id="8886d-129">フル スキャンは、クイック スキャンを実行して開始し、すべてのマウントされた固定ディスクとリムーバブル/ネットワーク ドライブのシーケンシャル ファイル スキャンを続行します (フル スキャンが構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="8886d-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="8886d-130">フル スキャンは、スキャンする必要があるデータの量と種類に応じて、完了に数時間または数日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8886d-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="8886d-131">完全スキャンが完了すると、新しいセキュリティ インテリジェンスが利用できます。新しいセキュリティ インテリジェンスで他の脅威が検出されない場合は、新しいスキャンが必要です。</span><span class="sxs-lookup"><span data-stu-id="8886d-131">When the full scan is complete, new security intelligence is available, and a new scan is required to make sure that no other threats are detected with the new security intelligence.</span></span>   | <span data-ttu-id="8886d-132">カスタム スキャンは、指定したファイルとフォルダーで実行されるクイック スキャンです。</span><span class="sxs-lookup"><span data-stu-id="8886d-132">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="8886d-133">たとえば、USB ドライブ、またはデバイスのローカル ドライブ上の特定のフォルダーをスキャンすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="8886d-133">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

>[!NOTE]
><span data-ttu-id="8886d-134">既定では、USB ドライブなどのマウントされたリムーバブル デバイスでクイック スキャンが実行されます。</span><span class="sxs-lookup"><span data-stu-id="8886d-134">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

### <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="8886d-135">選択するスキャンの種類を知る方法</span><span class="sxs-lookup"><span data-stu-id="8886d-135">How do I know which scan type to choose?</span></span>

<span data-ttu-id="8886d-136">次の表を使用して、スキャンの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="8886d-136">Use the following table to choose a scan type.</span></span>


|<span data-ttu-id="8886d-137">シナリオ</span><span class="sxs-lookup"><span data-stu-id="8886d-137">Scenario</span></span>  |<span data-ttu-id="8886d-138">推奨されるスキャンの種類</span><span class="sxs-lookup"><span data-stu-id="8886d-138">Recommended scan type</span></span>  |
|---------|---------|
|<span data-ttu-id="8886d-139">定期的なスケジュールされたスキャンを設定する</span><span class="sxs-lookup"><span data-stu-id="8886d-139">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="8886d-140">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="8886d-140">Quick scan</span></span> <p><span data-ttu-id="8886d-141">クイック スキャンは、デバイス上のプロセス、メモリ、プロファイル、および特定の場所をチェックします。</span><span class="sxs-lookup"><span data-stu-id="8886d-141">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="8886d-142">常時オン [のリアルタイム保護と](configure-real-time-protection-microsoft-defender-antivirus.md)組み合わせると、クイック スキャンによって、システムから始まるマルウェアとカーネル レベルのマルウェアの両方に強力な範囲を提供できます。</span><span class="sxs-lookup"><span data-stu-id="8886d-142">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="8886d-143">リアルタイム保護は、ファイルを開いて閉じたときに、およびユーザーがフォルダーに移動するたびに、ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="8886d-143">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
|<span data-ttu-id="8886d-144">マルウェアなどの脅威がデバイスで検出される</span><span class="sxs-lookup"><span data-stu-id="8886d-144">Threats, such as malware, are detected on a device</span></span>     | <span data-ttu-id="8886d-145">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="8886d-145">Full scan</span></span> <p><span data-ttu-id="8886d-146">完全スキャンは、より完全なクリーンアップを必要とする非アクティブなコンポーネントが含されているかどうかを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8886d-146">A full scan can help identify whether there are any inactive components that require a more thorough clean-up.</span></span>         |
|<span data-ttu-id="8886d-147">オンデマンド スキャンを [実行する](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="8886d-147">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="8886d-148">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="8886d-148">Full scan</span></span>  <p><span data-ttu-id="8886d-149">フル スキャンでは、デバイス ディスク上のすべてのファイル (古いファイル、アーカイブ済みファイル、毎日アクセスされていないファイルなど) が検索されます。</span><span class="sxs-lookup"><span data-stu-id="8886d-149">A full scan looks at all files on the device disk, including files that are stale, archived, and not accessed on a daily basis.</span></span>      |
| <span data-ttu-id="8886d-150">USB ドライブなどのポータブル デバイスにマルウェアが含まれているのを確認する</span><span class="sxs-lookup"><span data-stu-id="8886d-150">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="8886d-151">カスタム スキャン</span><span class="sxs-lookup"><span data-stu-id="8886d-151">Custom scan</span></span> <p><span data-ttu-id="8886d-152">カスタム スキャンを使用すると、特定の場所、フォルダー、またはファイルを選択し、クイック スキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8886d-152">A custom scan enables you to select specific locations, folders, or files and runs a quick scan.</span></span> |

### <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="8886d-153">クイック スキャンとフル スキャンについて他に何を知る必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="8886d-153">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="8886d-154">悪意のあるファイルは、クイック スキャンに含まれていない場所に保存できます。</span><span class="sxs-lookup"><span data-stu-id="8886d-154">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="8886d-155">ただし、常時オンのリアルタイム保護は、開いて閉じているすべてのファイルと、ユーザーがアクセスするフォルダー内のすべてのファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="8886d-155">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="8886d-156">リアルタイム保護とクイック スキャンの組み合わせは、マルウェアに対する強力な保護を提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8886d-156">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="8886d-157">クラウドによる保護によるオン[](cloud-protection-microsoft-defender-antivirus.md)アクセス保護により、システム上でアクセスされるすべてのファイルが最新のセキュリティ インテリジェンスとクラウド 機械学習モデルでスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="8886d-157">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="8886d-158">リアルタイム保護でマルウェアが検出され、影響を受けるファイルの範囲が最初に決定されない場合、Microsoft Defender ウイルス対策 は修復プロセスの一環としてフル スキャンを開始します。</span><span class="sxs-lookup"><span data-stu-id="8886d-158">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="8886d-159">フル スキャンでは、クイック スキャンなど、他のスキャンで検出されていない悪意のあるファイルを検出できます。</span><span class="sxs-lookup"><span data-stu-id="8886d-159">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="8886d-160">ただし、フル スキャンには時間がかかる場合があります。また、貴重なシステム リソースを使用して完了できます。</span><span class="sxs-lookup"><span data-stu-id="8886d-160">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="8886d-161">デバイスがオフラインで長期に及ばない場合、フル スキャンの完了に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8886d-161">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

## <a name="set-up-scheduled-scans"></a><span data-ttu-id="8886d-162">スケジュールされたスキャンのセットアップ</span><span class="sxs-lookup"><span data-stu-id="8886d-162">Set up scheduled scans</span></span>

<span data-ttu-id="8886d-163">スケジュールされたスキャンは、指定した日と時刻に実行されます。</span><span class="sxs-lookup"><span data-stu-id="8886d-163">Scheduled scans run on the day and time that you specify.</span></span> <span data-ttu-id="8886d-164">グループ ポリシー、PowerShell、WMI を使用して、スケジュールされたスキャンを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8886d-164">You can use Group Policy, PowerShell, and WMI to configure scheduled scans.</span></span>

> [!NOTE]
> <span data-ttu-id="8886d-165">スケジュールされたフル スキャン中にデバイスがプラグを抜いてバッテリーで実行されている場合、スケジュールされたスキャンはイベント 1002 で停止し、完了前にスキャンが停止したと示されます。</span><span class="sxs-lookup"><span data-stu-id="8886d-165">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="8886d-166">Microsoft Defender ウイルス対策は、次にスケジュールされた時刻にフル スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="8886d-166">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="8886d-167">グループ ポリシーを使用してスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="8886d-167">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="8886d-168">Location</span><span class="sxs-lookup"><span data-stu-id="8886d-168">Location</span></span> | <span data-ttu-id="8886d-169">Setting</span><span class="sxs-lookup"><span data-stu-id="8886d-169">Setting</span></span> | <span data-ttu-id="8886d-170">説明</span><span class="sxs-lookup"><span data-stu-id="8886d-170">Description</span></span> | <span data-ttu-id="8886d-171">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="8886d-171">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="8886d-172">スキャン</span><span class="sxs-lookup"><span data-stu-id="8886d-172">Scan</span></span> | <span data-ttu-id="8886d-173">スケジュールされたスキャンに使用するスキャンの種類を指定する</span><span class="sxs-lookup"><span data-stu-id="8886d-173">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="8886d-174">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="8886d-174">Quick scan</span></span> |
|<span data-ttu-id="8886d-175">スキャン</span><span class="sxs-lookup"><span data-stu-id="8886d-175">Scan</span></span> | <span data-ttu-id="8886d-176">スケジュールされたスキャンを実行する週の日を指定する</span><span class="sxs-lookup"><span data-stu-id="8886d-176">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="8886d-177">スキャンを実行する日 (または実行しない) を指定します。</span><span class="sxs-lookup"><span data-stu-id="8886d-177">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="8886d-178">Never</span><span class="sxs-lookup"><span data-stu-id="8886d-178">Never</span></span> |
|<span data-ttu-id="8886d-179">スキャン</span><span class="sxs-lookup"><span data-stu-id="8886d-179">Scan</span></span> | <span data-ttu-id="8886d-180">スケジュールされたスキャンを実行する時刻を指定する</span><span class="sxs-lookup"><span data-stu-id="8886d-180">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="8886d-181">午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。</span><span class="sxs-lookup"><span data-stu-id="8886d-181">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="8886d-182">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="8886d-182">2 a.m.</span></span> |
|<span data-ttu-id="8886d-183">ルート</span><span class="sxs-lookup"><span data-stu-id="8886d-183">Root</span></span> | <span data-ttu-id="8886d-184">スケジュールされたタスク時間をランダム化する</span><span class="sxs-lookup"><span data-stu-id="8886d-184">Randomize scheduled task times</span></span> |<span data-ttu-id="8886d-185">このMicrosoft Defender ウイルス対策、スキャンの開始時刻を 0 ~ 4 時間の任意の間隔にランダム化します。</span><span class="sxs-lookup"><span data-stu-id="8886d-185">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="8886d-186">[SCEP では](/mem/intune/protect/certificates-scep-configure)、スキャンを任意の間隔にプラスまたはマイナス 30 分にランダム化します。</span><span class="sxs-lookup"><span data-stu-id="8886d-186">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="8886d-187">これは、仮想マシンまたは VDI 展開で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8886d-187">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="8886d-188">有効</span><span class="sxs-lookup"><span data-stu-id="8886d-188">Enabled</span></span> |


### <a name="use-powershell-cmdlets-to-schedule-scans"></a><span data-ttu-id="8886d-189">PowerShell コマンドレットを使用してスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="8886d-189">Use PowerShell cmdlets to schedule scans</span></span>

<span data-ttu-id="8886d-190">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8886d-190">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanParameters
Set-MpPreference -ScanScheduleDay
Set-MpPreference -ScanScheduleTime
Set-MpPreference -RandomizeScheduleTaskTimes

```

<span data-ttu-id="8886d-191">詳細については[、「PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して powerShell コマンドレットを構成し、Microsoft Defender ウイルス対策 コマンドレットと Microsoft Defender ウイルス対策[Defender](/powershell/module/defender/)コマンドレットを実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8886d-191">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-scans"></a><span data-ttu-id="8886d-192">スキャンをWindowsする場合は、管理命令 (WMI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="8886d-192">Use Windows Management Instruction (WMI) to schedule scans</span></span>

<span data-ttu-id="8886d-193">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8886d-193">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanParameters
ScanScheduleDay
ScanScheduleTime
RandomizeScheduleTaskTimes
```

<span data-ttu-id="8886d-194">詳細および許可されるパラメーターについては[、「WMIv2 API のWindows Defender参照してください。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="8886d-194">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>


## <a name="start-scheduled-scans-only-when-the-endpoint-is-not-in-use"></a><span data-ttu-id="8886d-195">エンドポイントが使用されていない場合にのみ、スケジュールされたスキャンを開始する</span><span class="sxs-lookup"><span data-stu-id="8886d-195">Start scheduled scans only when the endpoint is not in use</span></span>

<span data-ttu-id="8886d-196">スケジュールされたスキャンは、エンドポイントがオンになっているが、グループ ポリシー、PowerShell、または WMI で使用されていない場合にのみ発生する設定できます。</span><span class="sxs-lookup"><span data-stu-id="8886d-196">You can set the scheduled scan to only occur when the endpoint is turned on but not in use with Group Policy, PowerShell, or WMI.</span></span>

> [!NOTE]
> <span data-ttu-id="8886d-197">これらのスキャンは、CPU 調整構成を尊重し、可能な限り速くスキャンを完了するために利用可能なリソースをフルに活用します。</span><span class="sxs-lookup"><span data-stu-id="8886d-197">These scans will not honor the CPU throttling configuration and take full advantage of the resources available to complete the scan as fast as possible.</span></span>

### <a name="use-group-policy-to-schedule-scans"></a><span data-ttu-id="8886d-198">グループ ポリシーを使用してスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="8886d-198">Use Group Policy to schedule scans</span></span>

|<span data-ttu-id="8886d-199">Location</span><span class="sxs-lookup"><span data-stu-id="8886d-199">Location</span></span> | <span data-ttu-id="8886d-200">Setting</span><span class="sxs-lookup"><span data-stu-id="8886d-200">Setting</span></span> | <span data-ttu-id="8886d-201">説明</span><span class="sxs-lookup"><span data-stu-id="8886d-201">Description</span></span> | <span data-ttu-id="8886d-202">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="8886d-202">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="8886d-203">スキャン</span><span class="sxs-lookup"><span data-stu-id="8886d-203">Scan</span></span> | <span data-ttu-id="8886d-204">コンピューターがオンで、使用されていない場合にのみ、スケジュールされたスキャンを開始する</span><span class="sxs-lookup"><span data-stu-id="8886d-204">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="8886d-205">コンピューターがオンで使用されていない場合、スケジュールされたスキャンは実行されません。</span><span class="sxs-lookup"><span data-stu-id="8886d-205">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="8886d-206">有効</span><span class="sxs-lookup"><span data-stu-id="8886d-206">Enabled</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="8886d-207">PowerShell コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="8886d-207">Use PowerShell cmdlets</span></span>

<span data-ttu-id="8886d-208">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8886d-208">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanOnlyIfIdleEnabled
```

<span data-ttu-id="8886d-209">詳細については[、「Use PowerShell コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)使用して、PowerShell コマンドレットと Defender コマンドレットを構成Microsoft Defender ウイルス対策実行する」[を参照してください](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="8886d-209">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="8886d-210">管理Windows使用 (WMI)</span><span class="sxs-lookup"><span data-stu-id="8886d-210">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="8886d-211">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8886d-211">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanOnlyIfIdleEnabled
```

<span data-ttu-id="8886d-212">API と許可パラメーターの詳細については[、「WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)のWindows Defender参照してください。</span><span class="sxs-lookup"><span data-stu-id="8886d-212">For more information about APIs and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="remed"></a>
## <a name="configure-when-full-scans-should-be-run-to-complete-remediation"></a><span data-ttu-id="8886d-213">修復を完了するためにフル スキャンを実行する必要がある場合の構成</span><span class="sxs-lookup"><span data-stu-id="8886d-213">Configure when full scans should be run to complete remediation</span></span>

<span data-ttu-id="8886d-214">一部の脅威では、削除と修復を完了するためにフル スキャンが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8886d-214">Some threats might require a full scan to complete their removal and remediation.</span></span> <span data-ttu-id="8886d-215">これらのスキャンをグループ ポリシー、PowerShell、または WMI で実行する必要がある場合に指定できます。</span><span class="sxs-lookup"><span data-stu-id="8886d-215">You can specify when these scans should occur with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-remediation-required-scans"></a><span data-ttu-id="8886d-216">グループ ポリシーを使用して修復に必要なスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="8886d-216">Use Group Policy to schedule remediation-required scans</span></span>

| <span data-ttu-id="8886d-217">Location</span><span class="sxs-lookup"><span data-stu-id="8886d-217">Location</span></span> | <span data-ttu-id="8886d-218">Setting</span><span class="sxs-lookup"><span data-stu-id="8886d-218">Setting</span></span> | <span data-ttu-id="8886d-219">説明</span><span class="sxs-lookup"><span data-stu-id="8886d-219">Description</span></span> | <span data-ttu-id="8886d-220">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="8886d-220">Default setting (if not configured)</span></span> |
|---|---|---|---|
|<span data-ttu-id="8886d-221">修復</span><span class="sxs-lookup"><span data-stu-id="8886d-221">Remediation</span></span> | <span data-ttu-id="8886d-222">スケジュールされたフル スキャンを実行して修復を完了する日を指定する</span><span class="sxs-lookup"><span data-stu-id="8886d-222">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="8886d-223">スキャンを実行する日 (または実行しない) を指定します。</span><span class="sxs-lookup"><span data-stu-id="8886d-223">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="8886d-224">Never</span><span class="sxs-lookup"><span data-stu-id="8886d-224">Never</span></span> |
|<span data-ttu-id="8886d-225">修復</span><span class="sxs-lookup"><span data-stu-id="8886d-225">Remediation</span></span> | <span data-ttu-id="8886d-226">スケジュールされたフル スキャンを実行して修復を完了する時刻を指定する</span><span class="sxs-lookup"><span data-stu-id="8886d-226">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="8886d-227">午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。</span><span class="sxs-lookup"><span data-stu-id="8886d-227">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="8886d-228">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="8886d-228">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets"></a><span data-ttu-id="8886d-229">PowerShell コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="8886d-229">Use PowerShell cmdlets</span></span>

<span data-ttu-id="8886d-230">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8886d-230">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -RemediationScheduleDay
Set-MpPreference -RemediationScheduleTime
```

<span data-ttu-id="8886d-231">PowerShell[コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)構成して実行する方法の詳細については、「powerShell コマンドレットを使用して Microsoft Defender ウイルス対策 および[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照Microsoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="8886d-231">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi"></a><span data-ttu-id="8886d-232">管理Windows使用 (WMI)</span><span class="sxs-lookup"><span data-stu-id="8886d-232">Use Windows Management Instruction (WMI)</span></span>

<span data-ttu-id="8886d-233">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8886d-233">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
RemediationScheduleDay
RemediationScheduleTime
```

<span data-ttu-id="8886d-234">詳細および許可されるパラメーターについては[、「WMIv2 API Windows Defender参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="8886d-234">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="set-up-daily-quick-scans"></a><span data-ttu-id="8886d-235">毎日のクイック スキャンをセットアップする</span><span class="sxs-lookup"><span data-stu-id="8886d-235">Set up daily quick scans</span></span>

<span data-ttu-id="8886d-236">グループ ポリシー、PowerShell、または WMI を使用して、他のスケジュールされたスキャンに加えて実行できる毎日のクイック スキャンを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="8886d-236">You can enable a daily quick scan that can be run in addition to your other scheduled scans with Group Policy, PowerShell, or WMI.</span></span>

### <a name="use-group-policy-to-schedule-daily-scans"></a><span data-ttu-id="8886d-237">グループ ポリシーを使用して毎日のスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="8886d-237">Use Group Policy to schedule daily scans</span></span>

|<span data-ttu-id="8886d-238">Location</span><span class="sxs-lookup"><span data-stu-id="8886d-238">Location</span></span> | <span data-ttu-id="8886d-239">Setting</span><span class="sxs-lookup"><span data-stu-id="8886d-239">Setting</span></span> | <span data-ttu-id="8886d-240">説明</span><span class="sxs-lookup"><span data-stu-id="8886d-240">Description</span></span> | <span data-ttu-id="8886d-241">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="8886d-241">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="8886d-242">スキャン</span><span class="sxs-lookup"><span data-stu-id="8886d-242">Scan</span></span> | <span data-ttu-id="8886d-243">1 日あたりのクイック スキャンを実行する間隔を指定する</span><span class="sxs-lookup"><span data-stu-id="8886d-243">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="8886d-244">次のクイック スキャンの前に経過する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="8886d-244">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="8886d-245">たとえば、2 時間ごとに実行するには **、「2」と入力し、1** 日 1 回は **24 と入力します**。</span><span class="sxs-lookup"><span data-stu-id="8886d-245">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="8886d-246">**0 と入力** すると、毎日のクイック スキャンは実行されません。</span><span class="sxs-lookup"><span data-stu-id="8886d-246">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="8886d-247">Never</span><span class="sxs-lookup"><span data-stu-id="8886d-247">Never</span></span> |
|<span data-ttu-id="8886d-248">スキャン</span><span class="sxs-lookup"><span data-stu-id="8886d-248">Scan</span></span> | <span data-ttu-id="8886d-249">毎日のクイック スキャンの時間を指定する</span><span class="sxs-lookup"><span data-stu-id="8886d-249">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="8886d-250">午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。</span><span class="sxs-lookup"><span data-stu-id="8886d-250">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="8886d-251">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="8886d-251">2 a.m.</span></span> |

### <a name="use-powershell-cmdlets-to-schedule-daily-scans"></a><span data-ttu-id="8886d-252">PowerShell コマンドレットを使用して毎日のスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="8886d-252">Use PowerShell cmdlets to schedule daily scans</span></span>

<span data-ttu-id="8886d-253">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8886d-253">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -ScanScheduleQuickScanTime
```

<span data-ttu-id="8886d-254">PowerShell を Microsoft Defender ウイルス対策 と一緒に使用する方法の詳細については[、「Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して、PowerShell コマンドレットと Defender コマンドレットを構成Microsoft Defender ウイルス対策実行する」を[参照してください](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="8886d-254">For more information about how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-schedule-daily-scans"></a><span data-ttu-id="8886d-255">毎日のWindowsをスケジュールするには、WMI 管理命令 (WMI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="8886d-255">Use Windows Management Instruction (WMI) to schedule daily scans</span></span>

<span data-ttu-id="8886d-256">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="8886d-256">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
ScanScheduleQuickScanTime
```

<span data-ttu-id="8886d-257">詳細および許可されるパラメーターについては[、「WMIv2 API Windows Defender参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="8886d-257">For more information and allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>


## <a name="enable-scans-after-protection-updates"></a><span data-ttu-id="8886d-258">保護更新後にスキャンを有効にする</span><span class="sxs-lookup"><span data-stu-id="8886d-258">Enable scans after protection updates</span></span>

<span data-ttu-id="8886d-259">グループ ポリシーを使用してすべての保護更新後にスキャン [を強制的](manage-protection-updates-microsoft-defender-antivirus.md) に実行できます。</span><span class="sxs-lookup"><span data-stu-id="8886d-259">You can force a scan to occur after every [protection update](manage-protection-updates-microsoft-defender-antivirus.md) with Group Policy.</span></span>

### <a name="use-group-policy-to-schedule-scans-after-protection-updates"></a><span data-ttu-id="8886d-260">グループ ポリシーを使用して保護の更新後にスキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="8886d-260">Use Group Policy to schedule scans after protection updates</span></span>

|<span data-ttu-id="8886d-261">Location</span><span class="sxs-lookup"><span data-stu-id="8886d-261">Location</span></span> | <span data-ttu-id="8886d-262">Setting</span><span class="sxs-lookup"><span data-stu-id="8886d-262">Setting</span></span> | <span data-ttu-id="8886d-263">説明</span><span class="sxs-lookup"><span data-stu-id="8886d-263">Description</span></span> | <span data-ttu-id="8886d-264">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="8886d-264">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
|<span data-ttu-id="8886d-265">署名の更新</span><span class="sxs-lookup"><span data-stu-id="8886d-265">Signature updates</span></span> | <span data-ttu-id="8886d-266">セキュリティ インテリジェンスの更新後にスキャンを有効にする</span><span class="sxs-lookup"><span data-stu-id="8886d-266">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="8886d-267">新しい保護更新プログラムがダウンロードされた直後にスキャンが実行されます</span><span class="sxs-lookup"><span data-stu-id="8886d-267">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="8886d-268">有効</span><span class="sxs-lookup"><span data-stu-id="8886d-268">Enabled</span></span> |

## <a name="see-also"></a><span data-ttu-id="8886d-269">関連項目</span><span class="sxs-lookup"><span data-stu-id="8886d-269">See also</span></span>

- [<span data-ttu-id="8886d-270">ユーザーによるポリシー設定のローカル変更を防止または許可する</span><span class="sxs-lookup"><span data-stu-id="8886d-270">Prevent or allow users to locally modify policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8886d-271">オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する</span><span class="sxs-lookup"><span data-stu-id="8886d-271">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>](run-scan-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8886d-272">Microsoft Defender ウイルス対策スキャン オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="8886d-272">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8886d-273">更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する</span><span class="sxs-lookup"><span data-stu-id="8886d-273">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="8886d-274">保護更新プログラムをダウンロードして適用する場合の管理</span><span class="sxs-lookup"><span data-stu-id="8886d-274">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="8886d-275">Microsoft Defender ウイルス対策のWindows 10</span><span class="sxs-lookup"><span data-stu-id="8886d-275">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)