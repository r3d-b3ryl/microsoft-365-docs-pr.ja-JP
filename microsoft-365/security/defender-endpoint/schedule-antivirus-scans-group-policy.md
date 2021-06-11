---
title: グループ ポリシーを使用してウイルス対策スキャンをスケジュールする
description: グループ ポリシーを使用してウイルス対策スキャンをセットアップする
keywords: クイック スキャン、フル スキャン、スケジュール、グループ ポリシー、ウイルス対策
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
ms.openlocfilehash: 6f6018ec8b514234ab4f98e3d5416b472ff88739
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879747"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a><span data-ttu-id="2869c-104">グループ ポリシーを使用してウイルス対策スキャンをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="2869c-104">Schedule antivirus scans using Group Policy</span></span>

<span data-ttu-id="2869c-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2869c-105">**Applies to:**</span></span>

- [<span data-ttu-id="2869c-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2869c-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="2869c-107">この記事では、グループ ポリシーを使用してスケジュールされたスキャンを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2869c-107">This article describes how to configure scheduled scans using Group Policy.</span></span> <span data-ttu-id="2869c-108">スキャンのスケジュール設定とスキャンの種類の詳細については、「スケジュールされたクイック スキャンまたはフル スキャンの構成[」をMicrosoft Defender ウイルス対策してください](schedule-antivirus-scans.md)。</span><span class="sxs-lookup"><span data-stu-id="2869c-108">To learn more about scheduling scans and about scan types, see [Configure scheduled quick or full Microsoft Defender Antivirus scans](schedule-antivirus-scans.md).</span></span> 

## <a name="configure-antivirus-scans-using-group-policy"></a><span data-ttu-id="2869c-109">グループ ポリシーを使用してウイルス対策スキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="2869c-109">Configure antivirus scans using Group Policy</span></span>

1. <span data-ttu-id="2869c-110">グループ ポリシー管理マシンのグループ ポリシー エディターで、[コンピューター構成] [管理用テンプレート] Windows [スキャンMicrosoft Defender ウイルス対策  >    >    >    >  **します**。</span><span class="sxs-lookup"><span data-stu-id="2869c-110">On your Group Policy management machine, in the Group Policy Editor, go to **Computer configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="2869c-111">構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="2869c-111">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="2869c-112">グループ ポリシー オブジェクトの設定を指定し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2869c-112">Specify settings for the Group Policy Object, and then select **OK**.</span></span> 

4. <span data-ttu-id="2869c-113">構成する設定ごとに手順 1 ~ 4 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="2869c-113">Repeat steps 1-4 for each setting you want to configure.</span></span>

5. <span data-ttu-id="2869c-114">通常と同じ方法でグループ ポリシー オブジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="2869c-114">Deploy your Group Policy Object as you normally do.</span></span> <span data-ttu-id="2869c-115">グループ ポリシー オブジェクトのヘルプが必要な場合は、「 [グループ ポリシー オブジェクトの作成」を参照してください](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)。</span><span class="sxs-lookup"><span data-stu-id="2869c-115">If you need help with Group Policy Objects, see [Create a Group Policy Object](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object).</span></span>

> [!TIP]
> <span data-ttu-id="2869c-116">「保護更新 [プログラムをダウンロードして](manage-protection-update-schedule-microsoft-defender-antivirus.md) 適用する必要がある場合の管理」および「ユーザーによるポリシー設定のローカル変更を防止または許可する」 [のトピックを参照](configure-local-policy-overrides-microsoft-defender-antivirus.md) してください。</span><span class="sxs-lookup"><span data-stu-id="2869c-116">See the [Manage when protection updates should be downloaded and applied](manage-protection-update-schedule-microsoft-defender-antivirus.md) and [Prevent or allow users to locally modify policy settings](configure-local-policy-overrides-microsoft-defender-antivirus.md) topics.</span></span>

## <a name="group-policy-settings-for-scheduling-scans"></a><span data-ttu-id="2869c-117">スキャンのスケジュール設定のグループ ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="2869c-117">Group Policy settings for scheduling scans</span></span>

| <span data-ttu-id="2869c-118">Location</span><span class="sxs-lookup"><span data-stu-id="2869c-118">Location</span></span> | <span data-ttu-id="2869c-119">設定</span><span class="sxs-lookup"><span data-stu-id="2869c-119">Setting</span></span> | <span data-ttu-id="2869c-120">説明</span><span class="sxs-lookup"><span data-stu-id="2869c-120">Description</span></span> | <span data-ttu-id="2869c-121">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="2869c-121">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
| <span data-ttu-id="2869c-122">スキャン</span><span class="sxs-lookup"><span data-stu-id="2869c-122">Scan</span></span> | <span data-ttu-id="2869c-123">スケジュールされたスキャンに使用するスキャンの種類を指定する</span><span class="sxs-lookup"><span data-stu-id="2869c-123">Specify the scan type to use for a scheduled scan</span></span> | <span data-ttu-id="2869c-124">クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="2869c-124">Quick scan</span></span> |
| <span data-ttu-id="2869c-125">スキャン</span><span class="sxs-lookup"><span data-stu-id="2869c-125">Scan</span></span> | <span data-ttu-id="2869c-126">スケジュールされたスキャンを実行する週の日を指定する</span><span class="sxs-lookup"><span data-stu-id="2869c-126">Specify the day of the week to run a scheduled scan</span></span> | <span data-ttu-id="2869c-127">スキャンを実行する日 (または実行しない) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2869c-127">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="2869c-128">Never</span><span class="sxs-lookup"><span data-stu-id="2869c-128">Never</span></span> |
| <span data-ttu-id="2869c-129">スキャン</span><span class="sxs-lookup"><span data-stu-id="2869c-129">Scan</span></span> | <span data-ttu-id="2869c-130">スケジュールされたスキャンを実行する時刻を指定する</span><span class="sxs-lookup"><span data-stu-id="2869c-130">Specify the time of day to run a scheduled scan</span></span> | <span data-ttu-id="2869c-131">午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。</span><span class="sxs-lookup"><span data-stu-id="2869c-131">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.).</span></span> | <span data-ttu-id="2869c-132">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="2869c-132">2 a.m.</span></span> |
| <span data-ttu-id="2869c-133">ルート</span><span class="sxs-lookup"><span data-stu-id="2869c-133">Root</span></span> | <span data-ttu-id="2869c-134">スケジュールされたタスク時間をランダム化する</span><span class="sxs-lookup"><span data-stu-id="2869c-134">Randomize scheduled task times</span></span> |<span data-ttu-id="2869c-135">このMicrosoft Defender ウイルス対策、スキャンの開始時刻を 0 ~ 4 時間の任意の間隔にランダム化します。</span><span class="sxs-lookup"><span data-stu-id="2869c-135">In Microsoft Defender Antivirus, randomize the start time of the scan to any interval from 0 to 4 hours.</span></span> <p><span data-ttu-id="2869c-136">[SCEP では](/mem/intune/protect/certificates-scep-configure)、スキャンを任意の間隔にプラスまたはマイナス 30 分にランダム化します。</span><span class="sxs-lookup"><span data-stu-id="2869c-136">In [SCEP](/mem/intune/protect/certificates-scep-configure), randomize scans to any interval plus or minus 30 minutes.</span></span> <span data-ttu-id="2869c-137">これは、仮想マシンまたは VDI 展開で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2869c-137">This can be useful in virtual machines or VDI deployments.</span></span> | <span data-ttu-id="2869c-138">Enabled</span><span class="sxs-lookup"><span data-stu-id="2869c-138">Enabled</span></span> |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a><span data-ttu-id="2869c-139">エンドポイントが使用されていないときにスキャンをスケジュールするグループ ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="2869c-139">Group Policy settings for scheduling scans for when an endpoint is not in use</span></span>

| <span data-ttu-id="2869c-140">Location</span><span class="sxs-lookup"><span data-stu-id="2869c-140">Location</span></span> | <span data-ttu-id="2869c-141">設定</span><span class="sxs-lookup"><span data-stu-id="2869c-141">Setting</span></span> | <span data-ttu-id="2869c-142">説明</span><span class="sxs-lookup"><span data-stu-id="2869c-142">Description</span></span> | <span data-ttu-id="2869c-143">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="2869c-143">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
| <span data-ttu-id="2869c-144">スキャン</span><span class="sxs-lookup"><span data-stu-id="2869c-144">Scan</span></span> | <span data-ttu-id="2869c-145">コンピューターがオンで、使用されていない場合にのみ、スケジュールされたスキャンを開始する</span><span class="sxs-lookup"><span data-stu-id="2869c-145">Start the scheduled scan only when computer is on but not in use</span></span> | <span data-ttu-id="2869c-146">コンピューターがオンで使用されていない場合、スケジュールされたスキャンは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2869c-146">Scheduled scans will not run, unless the computer is on but not in use</span></span> | <span data-ttu-id="2869c-147">Enabled</span><span class="sxs-lookup"><span data-stu-id="2869c-147">Enabled</span></span> |

> [!NOTE]
> <span data-ttu-id="2869c-148">エンドポイントが使用されていない時間のスキャンをスケジュールする場合、スキャンは CPU 調整構成を尊重し、可能な限り高速にスキャンを完了するために利用可能なリソースを活用します。</span><span class="sxs-lookup"><span data-stu-id="2869c-148">When you schedule scans for times when endpoints are not in use, scans do not honor the CPU throttling configuration and will take full advantage of the resources available to complete the scan as fast as possible.</span></span>

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a><span data-ttu-id="2869c-149">修復に必要なスキャンをスケジュールするためのグループ ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="2869c-149">Group Policy settings for scheduling remediation-required scans</span></span>

| <span data-ttu-id="2869c-150">Location</span><span class="sxs-lookup"><span data-stu-id="2869c-150">Location</span></span> | <span data-ttu-id="2869c-151">設定</span><span class="sxs-lookup"><span data-stu-id="2869c-151">Setting</span></span> | <span data-ttu-id="2869c-152">説明</span><span class="sxs-lookup"><span data-stu-id="2869c-152">Description</span></span> | <span data-ttu-id="2869c-153">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="2869c-153">Default setting (if not configured)</span></span> |
|---|---|---|---|
| <span data-ttu-id="2869c-154">修復</span><span class="sxs-lookup"><span data-stu-id="2869c-154">Remediation</span></span> | <span data-ttu-id="2869c-155">スケジュールされたフル スキャンを実行して修復を完了する日を指定する</span><span class="sxs-lookup"><span data-stu-id="2869c-155">Specify the day of the week to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="2869c-156">スキャンを実行する日 (または実行しない) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2869c-156">Specify the day (or never) to run a scan.</span></span> | <span data-ttu-id="2869c-157">Never</span><span class="sxs-lookup"><span data-stu-id="2869c-157">Never</span></span> |
| <span data-ttu-id="2869c-158">修復</span><span class="sxs-lookup"><span data-stu-id="2869c-158">Remediation</span></span> | <span data-ttu-id="2869c-159">スケジュールされたフル スキャンを実行して修復を完了する時刻を指定する</span><span class="sxs-lookup"><span data-stu-id="2869c-159">Specify the time of day to run a scheduled full scan to complete remediation</span></span> | <span data-ttu-id="2869c-160">午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。</span><span class="sxs-lookup"><span data-stu-id="2869c-160">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="2869c-161">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="2869c-161">2 a.m.</span></span> |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a><span data-ttu-id="2869c-162">毎日のスキャンをスケジュールするグループ ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="2869c-162">Group Policy settings for scheduling daily scans</span></span>

| <span data-ttu-id="2869c-163">Location</span><span class="sxs-lookup"><span data-stu-id="2869c-163">Location</span></span> | <span data-ttu-id="2869c-164">設定</span><span class="sxs-lookup"><span data-stu-id="2869c-164">Setting</span></span> | <span data-ttu-id="2869c-165">説明</span><span class="sxs-lookup"><span data-stu-id="2869c-165">Description</span></span> | <span data-ttu-id="2869c-166">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="2869c-166">Default setting (if not configured)</span></span> |
|:---|:---|:---|:---|
| <span data-ttu-id="2869c-167">スキャン</span><span class="sxs-lookup"><span data-stu-id="2869c-167">Scan</span></span> | <span data-ttu-id="2869c-168">1 日あたりのクイック スキャンを実行する間隔を指定する</span><span class="sxs-lookup"><span data-stu-id="2869c-168">Specify the interval to run quick scans per day</span></span> | <span data-ttu-id="2869c-169">次のクイック スキャンの前に経過する時間を指定します。</span><span class="sxs-lookup"><span data-stu-id="2869c-169">Specify how many hours should elapse before the next quick scan.</span></span> <span data-ttu-id="2869c-170">たとえば、2 時間ごとに実行するには **、「2」と入力し、1** 日 1 回は **24 と入力します**。</span><span class="sxs-lookup"><span data-stu-id="2869c-170">For example, to run every two hours, enter **2**, for once a day, enter **24**.</span></span> <span data-ttu-id="2869c-171">**0 と入力** すると、毎日のクイック スキャンは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2869c-171">Enter **0** to never run a daily quick scan.</span></span> | <span data-ttu-id="2869c-172">Never</span><span class="sxs-lookup"><span data-stu-id="2869c-172">Never</span></span> |
| <span data-ttu-id="2869c-173">スキャン</span><span class="sxs-lookup"><span data-stu-id="2869c-173">Scan</span></span> | <span data-ttu-id="2869c-174">毎日のクイック スキャンの時間を指定する</span><span class="sxs-lookup"><span data-stu-id="2869c-174">Specify the time for a daily quick scan</span></span> | <span data-ttu-id="2869c-175">午前 0 時以降の分数を指定します (たとえば、 **午前 1 時に 60** と入力します)。</span><span class="sxs-lookup"><span data-stu-id="2869c-175">Specify the number of minutes after midnight (for example, enter **60** for 1 a.m.)</span></span> | <span data-ttu-id="2869c-176">2 a.m.</span><span class="sxs-lookup"><span data-stu-id="2869c-176">2 a.m.</span></span> |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a><span data-ttu-id="2869c-177">保護更新後にスキャンをスケジュールするグループ ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="2869c-177">Group Policy settings for scheduling scans after protection updates</span></span>

| <span data-ttu-id="2869c-178">Location</span><span class="sxs-lookup"><span data-stu-id="2869c-178">Location</span></span> | <span data-ttu-id="2869c-179">設定</span><span class="sxs-lookup"><span data-stu-id="2869c-179">Setting</span></span> | <span data-ttu-id="2869c-180">説明</span><span class="sxs-lookup"><span data-stu-id="2869c-180">Description</span></span> | <span data-ttu-id="2869c-181">既定の設定 (構成されていない場合)</span><span class="sxs-lookup"><span data-stu-id="2869c-181">Default setting (if not configured)</span></span>|
|:---|:---|:---|:---|
| <span data-ttu-id="2869c-182">署名の更新</span><span class="sxs-lookup"><span data-stu-id="2869c-182">Signature updates</span></span> | <span data-ttu-id="2869c-183">セキュリティ インテリジェンスの更新後にスキャンを有効にする</span><span class="sxs-lookup"><span data-stu-id="2869c-183">Turn on scan after Security intelligence update</span></span> | <span data-ttu-id="2869c-184">新しい保護更新プログラムがダウンロードされた直後にスキャンが実行されます</span><span class="sxs-lookup"><span data-stu-id="2869c-184">A scan will occur immediately after a new protection update is downloaded</span></span> | <span data-ttu-id="2869c-185">Enabled</span><span class="sxs-lookup"><span data-stu-id="2869c-185">Enabled</span></span> |

