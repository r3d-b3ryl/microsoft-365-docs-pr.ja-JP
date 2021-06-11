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
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 5566050e4a64713f6f8b4ac2cb4a7188d3a241c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879727"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a><span data-ttu-id="a0c68-104">スケジュールされたクイックまたは完全な Microsoft Defender ウイルス スキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="a0c68-104">Configure scheduled quick or full Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="a0c68-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a0c68-105">**Applies to:**</span></span>

- [<span data-ttu-id="a0c68-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a0c68-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="a0c68-107">常時オン、リアルタイム保護、オンデマンドウイルス対策スキャンに加[](run-scan-microsoft-defender-antivirus.md)えて、定期的にスケジュールされたウイルス対策スキャンを設定できます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-107">In addition to always-on, real-time protection and [on-demand antivirus](run-scan-microsoft-defender-antivirus.md) scans, you can set up regular, scheduled antivirus scans.</span></span> <span data-ttu-id="a0c68-108">スキャンの種類、スキャンが実行される場合、および保護更新後にスキャンが実行される場合、または[](manage-protection-updates-microsoft-defender-antivirus.md)エンドポイントが使用されていない場合に構成できます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-108">You can configure the type of scan, when the scan should occur, and if the scan should occur after a [protection update](manage-protection-updates-microsoft-defender-antivirus.md) or when an endpoint is not being used.</span></span> <span data-ttu-id="a0c68-109">必要に応じて、特別なスキャンを設定して修復アクションを完了することもできます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-109">You can also set up special scans to complete remediation actions if needed.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="a0c68-110">目的に合ったトピックをクリックしてください</span><span class="sxs-lookup"><span data-stu-id="a0c68-110">What do you want to do?</span></span>

- [<span data-ttu-id="a0c68-111">クイック スキャン、フル スキャン、およびカスタム スキャンの詳細</span><span class="sxs-lookup"><span data-stu-id="a0c68-111">Learn about quick scans, full scans, and custom scans</span></span>](#quick-scan-full-scan-and-custom-scan)
- [<span data-ttu-id="a0c68-112">グループ ポリシーを使用してウイルス対策スキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="a0c68-112">Use Group Policy to schedule antivirus scans</span></span>](schedule-antivirus-scans-group-policy.md)
- <span data-ttu-id="a0c68-113">[[ウイルスWindows PowerShellスキャンのスケジュール設定] を使用する](schedule-antivirus-scans-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="a0c68-113">[Use Windows PowerShell to Schedule antivirus scans](schedule-antivirus-scans-powershell.md)</span></span>
- [<span data-ttu-id="a0c68-114">管理Windowsを使用してウイルス対策スキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="a0c68-114">Use Windows Management Instrumentation to schedule antivirus scans</span></span>](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a><span data-ttu-id="a0c68-115">以下の点に気を付ける</span><span class="sxs-lookup"><span data-stu-id="a0c68-115">Keep the following points in mind</span></span>

- <span data-ttu-id="a0c68-116">既定では、Microsoft Defender ウイルス対策スキャンの時刻の 15 分前に更新プログラムがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-116">By default, Microsoft Defender Antivirus checks for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="a0c68-117">保護更新 [プログラムをダウンロードして適用するスケジュール](manage-protection-update-schedule-microsoft-defender-antivirus.md) を管理して、この既定を上書きできます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-117">You can [Manage the schedule for when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) to override this default.</span></span> 

- <span data-ttu-id="a0c68-118">スケジュールされたフル スキャン中にデバイスがプラグを抜いてバッテリーで実行されている場合、スケジュールされたスキャンはイベント 1002 で停止し、完了前にスキャンが停止したと示されます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-118">If a device is unplugged and running on battery during a scheduled full scan, the scheduled scan will stop with event 1002, which states that the scan stopped before completion.</span></span> <span data-ttu-id="a0c68-119">Microsoft Defender ウイルス対策は、次にスケジュールされた時刻にフル スキャンを実行します。</span><span class="sxs-lookup"><span data-stu-id="a0c68-119">Microsoft Defender Antivirus will run a full scan at the next scheduled time.</span></span>

## <a name="quick-scan-full-scan-and-custom-scan"></a><span data-ttu-id="a0c68-120">クイック スキャン、フル スキャン、およびカスタム スキャン</span><span class="sxs-lookup"><span data-stu-id="a0c68-120">Quick scan, full scan, and custom scan</span></span>

<span data-ttu-id="a0c68-121">スケジュールされたスキャンを設定する場合は、スキャンを完全スキャンまたはクイック スキャンにするかどうかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-121">When you set up scheduled scans, you can specify whether the scan should be a full or quick scan.</span></span> <span data-ttu-id="a0c68-122">ほとんどの場合、クイック スキャンをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a0c68-122">In most cases, a quick scan is recommended.</span></span> 

| <span data-ttu-id="a0c68-123">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="a0c68-123">Quick scan</span></span>  | <span data-ttu-id="a0c68-124">フル スキャン</span><span class="sxs-lookup"><span data-stu-id="a0c68-124">Full scan</span></span>  | <span data-ttu-id="a0c68-125">カスタム スキャン</span><span class="sxs-lookup"><span data-stu-id="a0c68-125">Custom scan</span></span> |
|---------|---------|---------|
| <span data-ttu-id="a0c68-126">(推奨)クイック スキャンでは、レジストリ キーや既知のスタートアップ フォルダーなど、システムで起動するマルウェアが登録されている可能性があるすべての場所Windowsします。</span><span class="sxs-lookup"><span data-stu-id="a0c68-126">(Recommended) A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> <p><span data-ttu-id="a0c68-127">ファイルを開いて閉じたときに確認する常時オンのリアルタイム保護と組み合わせて、ユーザーがフォルダーに移動するたびに、クイック スキャンを実行すると、システムとカーネル レベルのマルウェアから始まるマルウェアに対する強力な保護を提供できます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-127">Combined with always-on, real-time protection, which reviews files when they are opened and closed, and whenever a user navigates to a folder, a quick scan helps provide strong protection against malware that starts with the system and kernel-level malware.</span></span> <p><span data-ttu-id="a0c68-128">ほとんどの場合、クイック スキャンで十分であり、スケジュールされたスキャンに推奨されるオプションです。</span><span class="sxs-lookup"><span data-stu-id="a0c68-128">In most cases, a quick scan is sufficient and is the recommended option for scheduled scans.</span></span> | <span data-ttu-id="a0c68-129">フル スキャンは、クイック スキャンを実行して開始し、すべてのマウントされた固定ディスクとリムーバブル/ネットワーク ドライブのシーケンシャル ファイル スキャンを続行します (フル スキャンが構成されている場合)。</span><span class="sxs-lookup"><span data-stu-id="a0c68-129">A full scan starts by running a quick scan and then continues with a sequential file scan of all mounted fixed disks and removable/network drives (if the full scan is configured to do so).</span></span> <p><span data-ttu-id="a0c68-130">フル スキャンは、スキャンする必要があるデータの量と種類に応じて、完了に数時間または数日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a0c68-130">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span><p><span data-ttu-id="a0c68-131">完全スキャンが完了すると、新しいセキュリティ インテリジェンスが利用できます。新しいセキュリティ インテリジェンスで他の脅威が検出されない場合は、新しいスキャンが必要になります。</span><span class="sxs-lookup"><span data-stu-id="a0c68-131">When the full scan is complete, new security intelligence is available, and a new scan is then required to make sure that no other threats are detected with the new security intelligence.</span></span> <p><span data-ttu-id="a0c68-132">フル スキャンに関連する時間とリソースのため、一般に、Microsoft はフル スキャンのスケジュール設定を推奨しません。</span><span class="sxs-lookup"><span data-stu-id="a0c68-132">Because of the time and resources involved in a full scan, in general, Microsoft does not recommend scheduling full scans.</span></span>  | <span data-ttu-id="a0c68-133">カスタム スキャンは、指定したファイルとフォルダーで実行されるクイック スキャンです。</span><span class="sxs-lookup"><span data-stu-id="a0c68-133">A custom scan is a quick scan that runs on the files and folders you specify.</span></span> <span data-ttu-id="a0c68-134">たとえば、USB ドライブ、またはデバイスのローカル ドライブ上の特定のフォルダーをスキャンすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-134">For example, you can opt to scan a USB drive, or a specific folder on your device's local drive.</span></span> <p> | 

> [!NOTE]
> <span data-ttu-id="a0c68-135">既定では、USB ドライブなどのマウントされたリムーバブル デバイスでクイック スキャンが実行されます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-135">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="how-do-i-know-which-scan-type-to-choose"></a><span data-ttu-id="a0c68-136">選択するスキャンの種類を知る方法</span><span class="sxs-lookup"><span data-stu-id="a0c68-136">How do I know which scan type to choose?</span></span>

<span data-ttu-id="a0c68-137">次の表を使用して、スキャンの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="a0c68-137">Use the following table to choose a scan type.</span></span>

| <span data-ttu-id="a0c68-138">シナリオ</span><span class="sxs-lookup"><span data-stu-id="a0c68-138">Scenario</span></span>  | <span data-ttu-id="a0c68-139">推奨されるスキャンの種類</span><span class="sxs-lookup"><span data-stu-id="a0c68-139">Recommended scan type</span></span>  |
|---------|---------|
| <span data-ttu-id="a0c68-140">定期的なスケジュールされたスキャンを設定する</span><span class="sxs-lookup"><span data-stu-id="a0c68-140">You want to set up regular, scheduled scans</span></span>     | <span data-ttu-id="a0c68-141">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="a0c68-141">Quick scan</span></span> <p><span data-ttu-id="a0c68-142">クイック スキャンは、デバイス上のプロセス、メモリ、プロファイル、および特定の場所をチェックします。</span><span class="sxs-lookup"><span data-stu-id="a0c68-142">A quick scan checks the processes, memory, profiles, and certain locations on the device.</span></span> <span data-ttu-id="a0c68-143">常時オン [のリアルタイム保護と](configure-real-time-protection-microsoft-defender-antivirus.md)組み合わせると、クイック スキャンによって、システムから始まるマルウェアとカーネル レベルのマルウェアの両方に強力な範囲を提供できます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-143">Combined with [always-on real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="a0c68-144">リアルタイム保護は、ファイルを開いて閉じたときに、およびユーザーがフォルダーに移動するたびに、ファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="a0c68-144">Real-time protection reviews files when they are opened and closed, and whenever a user navigates to a folder.</span></span>         |
| <span data-ttu-id="a0c68-145">マルウェアなどの脅威が個々のデバイスで検出される</span><span class="sxs-lookup"><span data-stu-id="a0c68-145">Threats, such as malware, are detected on an individual device</span></span>     | <span data-ttu-id="a0c68-146">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="a0c68-146">Quick scan</span></span> <p><span data-ttu-id="a0c68-147">ほとんどの場合、クイック スキャンは検出されたマルウェアをキャッチしてクリーンアップします。</span><span class="sxs-lookup"><span data-stu-id="a0c68-147">In most cases, a quick scan will catch and clean up detected malware.</span></span>   |
| <span data-ttu-id="a0c68-148">オンデマンド スキャンを [実行する](run-scan-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="a0c68-148">You want to run an [on-demand scan](run-scan-microsoft-defender-antivirus.md)</span></span>     | <span data-ttu-id="a0c68-149">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="a0c68-149">Quick scan</span></span>       |
| <span data-ttu-id="a0c68-150">USB ドライブなどのポータブル デバイスにマルウェアが含まれているのを確認する</span><span class="sxs-lookup"><span data-stu-id="a0c68-150">You want to make sure a portable device, such as a USB drive, does not contain malware</span></span> | <span data-ttu-id="a0c68-151">カスタム スキャン</span><span class="sxs-lookup"><span data-stu-id="a0c68-151">Custom scan</span></span> <p><span data-ttu-id="a0c68-152">カスタム スキャンを使用すると、特定の場所、フォルダー、またはファイルを選択し、クイック スキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-152">A custom scan enables you to select specific locations, folders, or files, and runs a quick scan.</span></span> |

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a><span data-ttu-id="a0c68-153">クイック スキャンとフル スキャンについて他に何を知る必要がありますか?</span><span class="sxs-lookup"><span data-stu-id="a0c68-153">What else do I need to know about quick and full scans?</span></span>

- <span data-ttu-id="a0c68-154">悪意のあるファイルは、クイック スキャンに含まれていない場所に保存できます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-154">Malicious files can be stored in locations that are not included in a quick scan.</span></span> <span data-ttu-id="a0c68-155">ただし、常時オンのリアルタイム保護は、開いて閉じているすべてのファイルと、ユーザーがアクセスするフォルダー内のすべてのファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="a0c68-155">However, always-on real-time protection reviews all files that are opened and closed, and any files that are in folders that are accessed by a user.</span></span> <span data-ttu-id="a0c68-156">リアルタイム保護とクイック スキャンの組み合わせは、マルウェアに対する強力な保護を提供するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-156">The combination of real-time protection and a quick scan helps provide strong protection against malware.</span></span>

- <span data-ttu-id="a0c68-157">クラウドによる保護によるオン[](cloud-protection-microsoft-defender-antivirus.md)アクセス保護により、システム上でアクセスされるすべてのファイルが最新のセキュリティ インテリジェンスとクラウド 機械学習モデルでスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-157">On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) helps ensure that all the files accessed on the system are being scanned with the latest security intelligence and cloud machine learning models.</span></span>

- <span data-ttu-id="a0c68-158">リアルタイム保護でマルウェアが検出され、影響を受けるファイルの範囲が最初に決定されない場合、Microsoft Defender ウイルス対策 は修復プロセスの一環としてフル スキャンを開始します。</span><span class="sxs-lookup"><span data-stu-id="a0c68-158">When real-time protection detects malware and the extent of the affected files is not determined initially, Microsoft Defender Antivirus initiates a full scan as part of the remediation process.</span></span>

- <span data-ttu-id="a0c68-159">フル スキャンでは、クイック スキャンなど、他のスキャンで検出されていない悪意のあるファイルを検出できます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-159">A full scan can detect malicious files that were not detected by other scans, such as a quick scan.</span></span> <span data-ttu-id="a0c68-160">ただし、フル スキャンには時間がかかる場合があります。また、貴重なシステム リソースを使用して完了できます。</span><span class="sxs-lookup"><span data-stu-id="a0c68-160">However, a full scan can take a while and use valuable system resources to complete.</span></span>

- <span data-ttu-id="a0c68-161">デバイスがオフラインで長期に及ばない場合、フル スキャンの完了に時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a0c68-161">If a device is offline for an extended period of time, a full scan can take longer to complete.</span></span> 

