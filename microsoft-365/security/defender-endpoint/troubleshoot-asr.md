---
title: 攻撃表面の縮小ルールに関する問題のトラブルシューティング
description: Microsoft Defender for Endpoint の攻撃表面縮小ルールに関する問題のトラブルシューティングを行うリソースとサンプル コード。
keywords: トラブルシューティング、エラー、修正、Windows Defender 例、asr、ルール、ヒップ、トラブルシューティング、監査、除外、誤検知、破損、ブロック、Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 9ff00c706b0fb336c178e227b1cb33eff9e9ebbc
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935223"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a><span data-ttu-id="4a63f-104">攻撃表面の縮小ルールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4a63f-104">Troubleshoot attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4a63f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4a63f-105">**Applies to:**</span></span>
- [<span data-ttu-id="4a63f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4a63f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4a63f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4a63f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4a63f-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="4a63f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4a63f-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="4a63f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="4a63f-110">攻撃表面の [縮小ルールを使用すると、](attack-surface-reduction.md) 次のような問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4a63f-110">When you use [attack surface reduction rules](attack-surface-reduction.md) you may run into issues, such as:</span></span>

- <span data-ttu-id="4a63f-111">ルールは、ファイル、プロセス、または実行すべきではない他のアクションをブロックします (誤検知)</span><span class="sxs-lookup"><span data-stu-id="4a63f-111">A rule blocks a file, process, or performs some other action that it shouldn't (false positive)</span></span>

- <span data-ttu-id="4a63f-112">ルールが説明に従って機能しないか、ファイルまたはプロセスをブロックしない (false 負の値)</span><span class="sxs-lookup"><span data-stu-id="4a63f-112">A rule doesn't work as described, or doesn't block a file or process that it should (false negative)</span></span>

<span data-ttu-id="4a63f-113">これらの問題のトラブルシューティングには、次の 4 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="4a63f-113">There are four steps to troubleshooting these problems:</span></span>

1. [<span data-ttu-id="4a63f-114">前提条件の確認</span><span class="sxs-lookup"><span data-stu-id="4a63f-114">Confirm prerequisites</span></span>](#confirm-prerequisites)

2. [<span data-ttu-id="4a63f-115">監査モードを使用してルールをテストする</span><span class="sxs-lookup"><span data-stu-id="4a63f-115">Use audit mode to test the rule</span></span>](#use-audit-mode-to-test-the-rule)

3. <span data-ttu-id="4a63f-116">[指定したルールの除外を追加](#add-exclusions-for-a-false-positive) する (誤検知の場合)</span><span class="sxs-lookup"><span data-stu-id="4a63f-116">[Add exclusions for the specified rule](#add-exclusions-for-a-false-positive) (for false positives)</span></span>

4. [<span data-ttu-id="4a63f-117">サポート ログの送信</span><span class="sxs-lookup"><span data-stu-id="4a63f-117">Submit support logs</span></span>](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a><span data-ttu-id="4a63f-118">前提条件の確認</span><span class="sxs-lookup"><span data-stu-id="4a63f-118">Confirm prerequisites</span></span>

<span data-ttu-id="4a63f-119">攻撃表面の縮小ルールは、次の条件を持つデバイスでのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="4a63f-119">Attack surface reduction rules will only work on devices with the following conditions:</span></span>

- <span data-ttu-id="4a63f-120">エンドポイントは、Windows 10 Enterprise バージョン 1709 (Fall Creators Update とも呼ばれる) を実行しています。</span><span class="sxs-lookup"><span data-stu-id="4a63f-120">Endpoints are running Windows 10 Enterprise, version 1709 (also known as the Fall Creators Update).</span></span>

- <span data-ttu-id="4a63f-121">エンドポイントは、Microsoft Defender Antivirus を唯一のウイルス対策保護アプリとして使用しています。</span><span class="sxs-lookup"><span data-stu-id="4a63f-121">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="4a63f-122">[他のウイルス対策アプリを使用すると、Microsoft Defender AV がそれ自体を無効にします](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="4a63f-122">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>

- <span data-ttu-id="4a63f-123">[リアルタイム保護が](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) 有効になっています。</span><span class="sxs-lookup"><span data-stu-id="4a63f-123">[Real-time protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is enabled.</span></span>

- <span data-ttu-id="4a63f-124">監査モードが有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="4a63f-124">Audit mode isn't enabled.</span></span> <span data-ttu-id="4a63f-125">「攻撃表面の縮小ルールを有効にする」の説明に従って、グループ ポリシーを使用してルールを無効 **(値**: **0)**[に設定します](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="4a63f-125">Use Group Policy to set the rule to **Disabled** (value: **0**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

<span data-ttu-id="4a63f-126">これらの前提条件が満たされている場合は、次の手順に進み、監査モードでルールをテストします。</span><span class="sxs-lookup"><span data-stu-id="4a63f-126">If these prerequisites have all been met, proceed to the next step to test the rule in audit mode.</span></span>

## <a name="use-audit-mode-to-test-the-rule"></a><span data-ttu-id="4a63f-127">監査モードを使用してルールをテストする</span><span class="sxs-lookup"><span data-stu-id="4a63f-127">Use audit mode to test the rule</span></span>

<span data-ttu-id="4a63f-128">demo.wd.microsoft.com の [Windows Defender](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) テスト グラウンド Web サイトにアクセスして、攻撃表面の縮小ルールが一般的にデバイス上の事前構成されたシナリオとプロセスで機能しているか、または監査モードを使用して、レポートのルールのみを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4a63f-128">You can visit the Windows Defender Test ground website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm attack surface reduction rules are generally working for pre-configured scenarios and processes on a device, or you can use audit mode, which enables rules for reporting only.</span></span>

<span data-ttu-id="4a63f-129">「デモ ツールを使用 [する」の](evaluate-attack-surface-reduction.md) 手順に従って、問題が発生している特定のルールをテストするために攻撃表面の縮小ルールがどのように機能するのか確認します。</span><span class="sxs-lookup"><span data-stu-id="4a63f-129">Follow these instructions in [Use the demo tool to see how attack surface reduction rules work](evaluate-attack-surface-reduction.md) to test the specific rule you're encountering problems with.</span></span>

1. <span data-ttu-id="4a63f-130">テストする特定のルールの監査モードを有効にします。</span><span class="sxs-lookup"><span data-stu-id="4a63f-130">Enable audit mode for the specific rule you want to test.</span></span> <span data-ttu-id="4a63f-131">グループ ポリシーを使用してルールを **監査モード** (値: **2)** に設定します 。「攻撃表面の縮小ルールを有効にする [」の説明に従います](enable-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="4a63f-131">Use Group Policy to set the rule to **Audit mode** (value: **2**) as described in [Enable attack surface reduction rules](enable-attack-surface-reduction.md).</span></span> <span data-ttu-id="4a63f-132">監査モードでは、ルールはファイルまたはプロセスを報告できますが、実行は許可されます。</span><span class="sxs-lookup"><span data-stu-id="4a63f-132">Audit mode allows the rule to report the file or process, but will still allow it to run.</span></span>

2. <span data-ttu-id="4a63f-133">問題の原因となっているアクティビティを実行します (たとえば、ブロックする必要があるが許可されているファイルまたはプロセスを開く、または実行する)。</span><span class="sxs-lookup"><span data-stu-id="4a63f-133">Perform the activity that is causing an issue (for example, open or execute the file or process that should be blocked but is being allowed).</span></span>

3. <span data-ttu-id="4a63f-134">[ルールが [有効] に](attack-surface-reduction.md) 設定されている場合、ルールがファイルまたはプロセスをブロックした可能性がある場合は、攻撃表面縮小ルールイベント ログを確認 **します**。</span><span class="sxs-lookup"><span data-stu-id="4a63f-134">[Review the attack surface reduction rule event logs](attack-surface-reduction.md) to see if the rule would have blocked the file or process if the rule had been set to **Enabled**.</span></span>

<span data-ttu-id="4a63f-135">ルールがブロックするファイルまたはプロセスをブロックしない場合は、まず監査モードが有効になっているか確認します。</span><span class="sxs-lookup"><span data-stu-id="4a63f-135">If a rule isn't blocking a file or process that you're expecting it should block, first check if audit mode is enabled.</span></span>

<span data-ttu-id="4a63f-136">監査モードは、別の機能のテスト、または自動化された PowerShell スクリプトによって有効になっている可能性があります。テストが完了した後は無効になっていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4a63f-136">Audit mode may have been enabled for testing another feature, or by an automated PowerShell script, and may not have been disabled after the tests were completed.</span></span>

<span data-ttu-id="4a63f-137">デモ ツールと監査モードでルールをテストし、攻撃表面の縮小ルールが構成済みのシナリオで動作しているが、ルールが期待通り動作しない場合は、状況に基づいて次のいずれかのセクションに進みます。</span><span class="sxs-lookup"><span data-stu-id="4a63f-137">If you've tested the rule with the demo tool and with audit mode, and attack surface reduction rules are working on pre-configured scenarios, but the rule isn't working as expected, proceed to either of the following sections based on your situation:</span></span>

1. <span data-ttu-id="4a63f-138">攻撃表面の縮小ルールがブロックしないブロック (誤検知とも呼ばれる) をブロックしている場合は、最初に攻撃表面の縮小ルールの除外を [追加できます](#add-exclusions-for-a-false-positive)。</span><span class="sxs-lookup"><span data-stu-id="4a63f-138">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can [first add an attack surface reduction rule exclusion](#add-exclusions-for-a-false-positive).</span></span>

2. <span data-ttu-id="4a63f-139">攻撃表面の縮小ルールがブロックする必要があるもの (偽陰性とも呼ばれる) をブロックしない場合は、直ちに最後の手順に進み、診断データを収集し、問題を提出[することができます。](#collect-diagnostic-data-for-file-submissions)</span><span class="sxs-lookup"><span data-stu-id="4a63f-139">If the attack surface reduction rule isn't blocking something that it should block (also known as a false negative), you can proceed immediately to the last step, [collecting diagnostic data and submitting the issue to us](#collect-diagnostic-data-for-file-submissions).</span></span>

## <a name="add-exclusions-for-a-false-positive"></a><span data-ttu-id="4a63f-140">誤検知の除外を追加する</span><span class="sxs-lookup"><span data-stu-id="4a63f-140">Add exclusions for a false positive</span></span>

<span data-ttu-id="4a63f-141">攻撃表面の縮小ルールがブロックしてはならないものをブロックしている場合 (誤検知とも呼ばれる)、除外を追加して、攻撃表面の縮小ルールが除外されたファイルまたはフォルダーを評価してはならないことを防止できます。</span><span class="sxs-lookup"><span data-stu-id="4a63f-141">If the attack surface reduction rule is blocking something that it shouldn't block (also known as a false positive), you can add exclusions to prevent attack surface reduction rules from evaluating the excluded files or folders.</span></span>

<span data-ttu-id="4a63f-142">除外を追加するには、「攻撃表面の [縮小をカスタマイズする」を参照してください](customize-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="4a63f-142">To add an exclusion, see [Customize Attack surface reduction](customize-attack-surface-reduction.md).</span></span>

>[!IMPORTANT]
><span data-ttu-id="4a63f-143">除外する個々のファイルとフォルダーを指定できますが、個々のルールを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4a63f-143">You can specify individual files and folders to be excluded, but you cannot specify individual rules.</span></span>
><span data-ttu-id="4a63f-144">つまり、除外されるファイルまたはフォルダーは、すべての ASR ルールから除外されます。</span><span class="sxs-lookup"><span data-stu-id="4a63f-144">This means any files or folders that are excluded will be excluded from all ASR rules.</span></span>

## <a name="report-a-false-positive-or-false-negative"></a><span data-ttu-id="4a63f-145">誤検知または偽陰性を報告する</span><span class="sxs-lookup"><span data-stu-id="4a63f-145">Report a false positive or false negative</span></span>

<span data-ttu-id="4a63f-146">ネットワーク保護用 [Windows Defender偽](https://www.microsoft.com/wdsi/filesubmission) 陰性または誤検知を報告するには、[セキュリティ インテリジェンス] Web ベースの送信フォームを使用します。</span><span class="sxs-lookup"><span data-stu-id="4a63f-146">Use the [Windows Defender Security Intelligence web-based submission form](https://www.microsoft.com/wdsi/filesubmission) to report a false negative or false positive for network protection.</span></span> <span data-ttu-id="4a63f-147">Windows E5 サブスクリプションを使用すると、関連付けられたアラート [へのリンクを提供できます](alerts-queue.md)。</span><span class="sxs-lookup"><span data-stu-id="4a63f-147">With a Windows E5 subscription, you can also [provide a link to any associated alert](alerts-queue.md).</span></span>

## <a name="collect-diagnostic-data-for-file-submissions"></a><span data-ttu-id="4a63f-148">ファイル提出の診断データを収集する</span><span class="sxs-lookup"><span data-stu-id="4a63f-148">Collect diagnostic data for file submissions</span></span>

<span data-ttu-id="4a63f-149">攻撃表面の縮小ルールに関する問題を報告する場合は、Microsoft のサポートチームとエンジニアリング チームが問題のトラブルシューティングに役立つ診断データを収集して提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a63f-149">When you report a problem with attack surface reduction rules, you're asked to collect and submit diagnostic data that can be used by Microsoft support and engineering teams to help troubleshoot issues.</span></span>

1. <span data-ttu-id="4a63f-150">管理者特権のコマンド プロンプトを開き、次のディレクトリWindows Defenderします。</span><span class="sxs-lookup"><span data-stu-id="4a63f-150">Open an elevated command prompt and change to the Windows Defender directory:</span></span>

   ```console
   cd "c:\program files\windows defender"
   ```

2. <span data-ttu-id="4a63f-151">次のコマンドを実行して、診断ログを生成します。</span><span class="sxs-lookup"><span data-stu-id="4a63f-151">Run this command to generate the diagnostic logs:</span></span>

   ```console
   mpcmdrun -getfiles
   ```

3. <span data-ttu-id="4a63f-152">既定では、 に保存されます `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` 。</span><span class="sxs-lookup"><span data-stu-id="4a63f-152">By default, they're saved to `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab`.</span></span> <span data-ttu-id="4a63f-153">提出フォームにファイルを添付します。</span><span class="sxs-lookup"><span data-stu-id="4a63f-153">Attach the file to the submission form.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4a63f-154">関連記事</span><span class="sxs-lookup"><span data-stu-id="4a63f-154">Related articles</span></span>

- [<span data-ttu-id="4a63f-155">攻撃面の減少ルール</span><span class="sxs-lookup"><span data-stu-id="4a63f-155">Attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="4a63f-156">攻撃面の減少ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="4a63f-156">Enable attack surface reduction rules</span></span>](enable-attack-surface-reduction.md)

- [<span data-ttu-id="4a63f-157">攻撃面の減少ルールを評価する</span><span class="sxs-lookup"><span data-stu-id="4a63f-157">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
