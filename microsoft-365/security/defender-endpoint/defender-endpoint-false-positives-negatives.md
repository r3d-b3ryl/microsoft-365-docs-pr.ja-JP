---
title: Microsoft Defender for Endpoint での誤検出/検出漏れに対処する
description: Microsoft Defender for Endpoint で誤検知または誤検知を処理する方法について説明します。
keywords: ウイルス対策、例外、除外、Microsoft Defender for Endpoint、誤検知、偽陰性、ブロックされたファイル、ブロックされた URL
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
- m365solution-scenario
- m365scenario-fpfn
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs, yonghree, jcedola
ms.custom: FPFN
ms.openlocfilehash: 368de770f772dc75a366b2120c8824fda6a7ba11
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933591"
---
# <a name="address-false-positivesnegatives-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="39982-104">Microsoft Defender for Endpoint での誤検出/検出漏れに対処する</span><span class="sxs-lookup"><span data-stu-id="39982-104">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="39982-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="39982-105">**Applies to**</span></span>

- [<span data-ttu-id="39982-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="39982-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146806)

<span data-ttu-id="39982-107">エンドポイント保護ソリューションでは、誤検知とは、ファイルやプロセスなどのエンティティであり、実際には脅威ではないにもかかわらず、悪意のあるエンティティとして検出され、識別されました。</span><span class="sxs-lookup"><span data-stu-id="39982-107">In endpoint protection solutions, a false positive is an entity, such as a file or a process, that was detected and identified as malicious, even though the entity isn't actually a threat.</span></span> <span data-ttu-id="39982-108">偽陰性とは、実際には悪意があるにもかかわらず、脅威として検出されていないエンティティです。</span><span class="sxs-lookup"><span data-stu-id="39982-108">A false negative is an entity that was not detected as a threat, even though it actually is malicious.</span></span> <span data-ttu-id="39982-109">False positives/negatives は、Microsoft Defender for Endpoint を含む脅威保護 [ソリューションで発生する可能性があります](microsoft-defender-endpoint.md)。</span><span class="sxs-lookup"><span data-stu-id="39982-109">False positives/negatives can occur with any threat protection solution, including [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).</span></span>

![Defender for Endpoint での誤検知と負の定義](images/false-positives-overview.png)

<span data-ttu-id="39982-111">幸いなことに、これらの種類の問題に対処し、削減するための手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="39982-111">Fortunately, steps can be taken to address and reduce these kinds of issues.</span></span> <span data-ttu-id="39982-112">[Microsoft Defender](../defender/microsoft-365-security-center-mde.md)セキュリティ センターで誤検知/陰性が表示される場合、セキュリティ操作は、次のプロセスを使用して対処するための手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="39982-112">If you're seeing false positives/negatives in your [Microsoft Defender Security Center](../defender/microsoft-365-security-center-mde.md), your security operations can take steps to address them by using the following process:</span></span>

1.  [<span data-ttu-id="39982-113">アラートの確認と分類</span><span class="sxs-lookup"><span data-stu-id="39982-113">Review and classify alerts</span></span>](#part-1-review-and-classify-alerts) 
2.  [<span data-ttu-id="39982-114">実行された修復アクションを確認する</span><span class="sxs-lookup"><span data-stu-id="39982-114">Review remediation actions that were taken</span></span>](#part-2-review-remediation-actions)
3.  [<span data-ttu-id="39982-115">除外の確認と定義</span><span class="sxs-lookup"><span data-stu-id="39982-115">Review and define exclusions</span></span>](#part-3-review-or-define-exclusions)
4.  [<span data-ttu-id="39982-116">分析のためにエンティティを送信する</span><span class="sxs-lookup"><span data-stu-id="39982-116">Submit an entity for analysis</span></span>](#part-4-submit-a-file-for-analysis)
5.  [<span data-ttu-id="39982-117">脅威保護の設定を確認して調整する</span><span class="sxs-lookup"><span data-stu-id="39982-117">Review and adjust your threat protection settings</span></span>](#part-5-review-and-adjust-your-threat-protection-settings)

<span data-ttu-id="39982-118">この記事で説明するタスクを実行した後も、誤検知/負の問題がある場合は、ヘルプを受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="39982-118">You can get help if you still have issues with false positives/negatives after performing the tasks described in this article.</span></span> <span data-ttu-id="39982-119">「引 [き続きヘルプが必要か」を参照してください。](#still-need-help)</span><span class="sxs-lookup"><span data-stu-id="39982-119">See [Still need help?](#still-need-help)</span></span>

![誤検知と負に対処する手順](images/false-positives-step-diagram.png)

> [!NOTE]
> <span data-ttu-id="39982-121">この記事は、Microsoft Defender for Endpoint を使用しているセキュリティオペレーターおよびセキュリティ管理者向 [けガイダンスです](microsoft-defender-endpoint.md)。</span><span class="sxs-lookup"><span data-stu-id="39982-121">This article is intended as guidance for security operators and security administrators who are using [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md).</span></span>

## <a name="part-1-review-and-classify-alerts"></a><span data-ttu-id="39982-122">パート 1: アラートの確認と分類</span><span class="sxs-lookup"><span data-stu-id="39982-122">Part 1: Review and classify alerts</span></span>

<span data-ttu-id="39982-123">悪意 [のある、または](alerts.md) 疑わしいと検出されたためトリガーされたアラートが表示された場合は、そのエンティティのアラートを抑制できます。</span><span class="sxs-lookup"><span data-stu-id="39982-123">If you see an [alert](alerts.md) that was triggered because something was detected as malicious or suspicious that should not have been, you can suppress the alert for that entity.</span></span> <span data-ttu-id="39982-124">また、必ずしも誤検知ではないが重要ではないアラートを抑制することもできます。</span><span class="sxs-lookup"><span data-stu-id="39982-124">You can also suppress alerts that are not necessarily false positives, but are unimportant.</span></span> <span data-ttu-id="39982-125">アラートも分類することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39982-125">We recommend that you classify alerts as well.</span></span> 

<span data-ttu-id="39982-126">アラートを管理し、true/false positive を分類すると、脅威保護ソリューションのトレーニングに役立ち、時間の間に誤検知または誤検知の数を減らします。</span><span class="sxs-lookup"><span data-stu-id="39982-126">Managing your alerts and classifying true/false positives helps to train your threat protection solution and can reduce the number of false positives or false negatives over time.</span></span> <span data-ttu-id="39982-127">これらの手順を実行すると、セキュリティ運用ダッシュボードのノイズを軽減し、セキュリティ チームが優先度の高い作業項目に集中できます。</span><span class="sxs-lookup"><span data-stu-id="39982-127">Taking these steps also helps reduce noise in your security operations dashboard so that your security team can focus on higher priority work items.</span></span>

### <a name="determine-whether-an-alert-is-accurate"></a><span data-ttu-id="39982-128">アラートが正確かどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="39982-128">Determine whether an alert is accurate</span></span>

<span data-ttu-id="39982-129">アラートを分類または抑制する前に、アラートが正確か、誤検知か良性かを判断します。</span><span class="sxs-lookup"><span data-stu-id="39982-129">Before you classify or suppress an alert, determine whether the alert is accurate, a false positive, or benign.</span></span>

1. <span data-ttu-id="39982-130">Microsoft Defender セキュリティ センター ( ) に移動 [https://securitycenter.windows.com](https://securitycenter.windows.com) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="39982-130">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="39982-131">ナビゲーション ウィンドウで、[通知キュー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-131">In the navigation pane, choose **Alerts queue**.</span></span>

3. <span data-ttu-id="39982-132">アラートの詳細については、アラートを選択します。</span><span class="sxs-lookup"><span data-stu-id="39982-132">Select an alert to more details about the alert.</span></span> <span data-ttu-id="39982-133">[(「Microsoft Defender for Endpoint でアラートを確認する」を参照](review-alerts.md)してください。</span><span class="sxs-lookup"><span data-stu-id="39982-133">(See [Review alerts in Microsoft Defender for Endpoint](review-alerts.md).)</span></span>

4. <span data-ttu-id="39982-134">アラートの状態に応じて、次の表に示す手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="39982-134">Depending on the alert status, take the steps described in the following table:</span></span> 

| <span data-ttu-id="39982-135">アラートの状態</span><span class="sxs-lookup"><span data-stu-id="39982-135">Alert status</span></span> | <span data-ttu-id="39982-136">操作</span><span class="sxs-lookup"><span data-stu-id="39982-136">What to do</span></span> |
|:---|:---|
| <span data-ttu-id="39982-137">アラートは正確です</span><span class="sxs-lookup"><span data-stu-id="39982-137">The alert is accurate</span></span> | <span data-ttu-id="39982-138">アラートを割り当て、さらに [調査](investigate-alerts.md) します。</span><span class="sxs-lookup"><span data-stu-id="39982-138">Assign the alert, and then [investigate it](investigate-alerts.md) further.</span></span> |
| <span data-ttu-id="39982-139">アラートは誤検知です</span><span class="sxs-lookup"><span data-stu-id="39982-139">The alert is a false positive</span></span> | <span data-ttu-id="39982-140">1. [アラートを誤検知](#classify-an-alert) として分類します。</span><span class="sxs-lookup"><span data-stu-id="39982-140">1. [Classify the alert](#classify-an-alert) as a false positive.</span></span> <br/><span data-ttu-id="39982-141">2. [アラートを抑制します](#suppress-an-alert)。</span><span class="sxs-lookup"><span data-stu-id="39982-141">2. [Suppress the alert](#suppress-an-alert).</span></span> <br/> <span data-ttu-id="39982-142">3. [Microsoft](#indicators-for-microsoft-defender-for-endpoint) Defender for Endpoint のインジケーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="39982-142">3. [Create an indicator](#indicators-for-microsoft-defender-for-endpoint) for Microsoft Defender for Endpoint.</span></span> <br/> <span data-ttu-id="39982-143">4. [分析のためにファイルを Microsoft に提出します](#part-4-submit-a-file-for-analysis)。</span><span class="sxs-lookup"><span data-stu-id="39982-143">4. [Submit a file to Microsoft for analysis](#part-4-submit-a-file-for-analysis).</span></span> |
| <span data-ttu-id="39982-144">アラートは正確ですが、良性 (重要ではない)</span><span class="sxs-lookup"><span data-stu-id="39982-144">The alert is accurate, but benign (unimportant)</span></span> | <span data-ttu-id="39982-145">[アラートを正の](#classify-an-alert) 値として分類し、アラート [を抑制します](#suppress-an-alert)。</span><span class="sxs-lookup"><span data-stu-id="39982-145">[Classify the alert](#classify-an-alert) as a true positive, and then [suppress the alert](#suppress-an-alert).</span></span> |

### <a name="classify-an-alert"></a><span data-ttu-id="39982-146">アラートの分類</span><span class="sxs-lookup"><span data-stu-id="39982-146">Classify an alert</span></span>

<span data-ttu-id="39982-147">アラートは、Microsoft Defender セキュリティ センターで誤検知または真陽性として分類できます。</span><span class="sxs-lookup"><span data-stu-id="39982-147">Alerts can be classified as false positives or true positives in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="39982-148">アラートを分類すると、Microsoft Defender for Endpoint のトレーニングに役立ちます。これにより、時間がたつ間に、より多くの真のアラートと少ない誤ったアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="39982-148">Classifying alerts helps train Microsoft Defender for Endpoint so that, over time, you'll see more true alerts and fewer false alerts.</span></span>

1. <span data-ttu-id="39982-149">Microsoft Defender セキュリティ センター ( ) に移動 [https://securitycenter.windows.com](https://securitycenter.windows.com) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="39982-149">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="39982-150">[ **アラート キュー] を** 選択し、アラートを選択します。</span><span class="sxs-lookup"><span data-stu-id="39982-150">Select **Alerts queue**, and then select an alert.</span></span>

3. <span data-ttu-id="39982-151">選択したアラートに対して、[アクションの管理 **]**  >  **アラートを選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-151">For the selected alert, select **Actions** > **Manage alert**.</span></span> <span data-ttu-id="39982-152">フライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="39982-152">A flyout pane opens.</span></span>

4. <span data-ttu-id="39982-153">[警告の **管理] セクション** で、[True アラート] または **[False アラート** ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-153">In the **Manage alert** section, select either **True alert** or **False alert**.</span></span> <span data-ttu-id="39982-154">(False **アラートを使用して** 誤検知を分類します)。</span><span class="sxs-lookup"><span data-stu-id="39982-154">(Use **False alert** to classify a false positive.)</span></span>

> [!TIP]
> <span data-ttu-id="39982-155">アラートの抑制の詳細については [、「Manage Microsoft Defender for Endpoint alerts」を参照してください](/microsoft-365/security/defender-endpoint/manage-alerts)。</span><span class="sxs-lookup"><span data-stu-id="39982-155">For more information about suppressing alerts, see [Manage Microsoft Defender for Endpoint alerts](/microsoft-365/security/defender-endpoint/manage-alerts).</span></span> <span data-ttu-id="39982-156">また、組織でセキュリティ情報とイベント管理 (SIEM) サーバーを使用している場合は、抑制ルールも必ず定義してください。</span><span class="sxs-lookup"><span data-stu-id="39982-156">And, if your organization is using a security information and event management (SIEM) server, make sure to define a suppression rule there, too.</span></span> 

### <a name="suppress-an-alert"></a><span data-ttu-id="39982-157">アラートを抑制する</span><span class="sxs-lookup"><span data-stu-id="39982-157">Suppress an alert</span></span>

<span data-ttu-id="39982-158">誤検知または正陽性のアラートがあるが、重要ではないイベントの場合は、Microsoft Defender セキュリティ センターでそれらのアラートを抑制できます。</span><span class="sxs-lookup"><span data-stu-id="39982-158">If you have alerts that are either false positives or that are true positives but for unimportant events, you can suppress those alerts in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="39982-159">アラートを抑制すると、セキュリティ操作ダッシュボードのノイズを軽減できます。</span><span class="sxs-lookup"><span data-stu-id="39982-159">Suppressing alerts helps reduce noise in your security operations dashboard.</span></span> 

1. <span data-ttu-id="39982-160">Microsoft Defender セキュリティ センター ( ) に移動 [https://securitycenter.windows.com](https://securitycenter.windows.com) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="39982-160">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="39982-161">ナビゲーション ウィンドウで、[アラート キュー] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-161">In the navigation pane, select **Alerts queue**.</span></span>

3. <span data-ttu-id="39982-162">非表示にしたいアラートを選択して、[詳細] ウィンドウ **を開** きます。</span><span class="sxs-lookup"><span data-stu-id="39982-162">Select an alert that you want to suppress to open its **Details** pane.</span></span>

4. <span data-ttu-id="39982-163">[詳細 **] ウィンドウ** で省略記号 (**...**) を選択し、[抑制 **ルールの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-163">In the **Details** pane, choose the ellipsis (**...**), and then **Create a suppression rule**.</span></span>

5. <span data-ttu-id="39982-164">抑制ルールのすべての設定を指定し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-164">Specify all the settings for your suppression rule, and then choose **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="39982-165">抑制ルールのヘルプが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="39982-165">Need help with suppression rules?</span></span> <span data-ttu-id="39982-166">「アラート [を抑制し、新しい抑制ルールを作成する」を参照してください](/microsoft-365/security/defender-endpoint/manage-alerts#suppress-an-alert-and-create-a-new-suppression-rule)。</span><span class="sxs-lookup"><span data-stu-id="39982-166">See [Suppress an alert and create a new suppression rule](/microsoft-365/security/defender-endpoint/manage-alerts#suppress-an-alert-and-create-a-new-suppression-rule).</span></span>

## <a name="part-2-review-remediation-actions"></a><span data-ttu-id="39982-167">パート 2: 修復アクションの確認</span><span class="sxs-lookup"><span data-stu-id="39982-167">Part 2: Review remediation actions</span></span>

<span data-ttu-id="39982-168">[ファイルの](manage-auto-investigation.md#remediation-actions)検疫やプロセスの停止などの修復アクションは、脅威として検出されたエンティティ (ファイルなど) に対して実行されます。</span><span class="sxs-lookup"><span data-stu-id="39982-168">[Remediation actions](manage-auto-investigation.md#remediation-actions), such as sending a file to quarantine or stopping a process, are taken on entities (such as files) that are detected as threats.</span></span> <span data-ttu-id="39982-169">いくつかの種類の修復アクションは、自動調査と Microsoft Defender ウイルス対策によって自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="39982-169">Several types of remediation actions occur automatically through automated investigation and Microsoft Defender Antivirus:</span></span>   
- <span data-ttu-id="39982-170">ファイルの検疫</span><span class="sxs-lookup"><span data-stu-id="39982-170">Quarantine a file</span></span>
- <span data-ttu-id="39982-171">レジストリ キーを削除する</span><span class="sxs-lookup"><span data-stu-id="39982-171">Remove a registry key</span></span>
- <span data-ttu-id="39982-172">プロセスを終了する</span><span class="sxs-lookup"><span data-stu-id="39982-172">Kill a process</span></span>
- <span data-ttu-id="39982-173">サービスを停止する</span><span class="sxs-lookup"><span data-stu-id="39982-173">Stop a service</span></span>
- <span data-ttu-id="39982-174">ドライバーを無効にする</span><span class="sxs-lookup"><span data-stu-id="39982-174">Disable a driver</span></span>
- <span data-ttu-id="39982-175">スケジュールされたタスクを削除する</span><span class="sxs-lookup"><span data-stu-id="39982-175">Remove a scheduled task</span></span>

<span data-ttu-id="39982-176">ウイルス対策スキャンの開始や調査パッケージの収集などのその他のアクションは、手動で、または Live Response を介して [実行されます](live-response.md)。</span><span class="sxs-lookup"><span data-stu-id="39982-176">Other actions, such as starting an antivirus scan or collecting an investigation package, occur manually or through [Live Response](live-response.md).</span></span> <span data-ttu-id="39982-177">Live Response を使用して実行されるアクションは元に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="39982-177">Actions taken through Live Response cannot be undone.</span></span>

<span data-ttu-id="39982-178">アラートを確認した後、次に修復アクション [を確認します](manage-auto-investigation.md)。</span><span class="sxs-lookup"><span data-stu-id="39982-178">After you have reviewed your alerts, your next step is to [review remediation actions](manage-auto-investigation.md).</span></span> <span data-ttu-id="39982-179">誤検知の結果として何かアクションが実行された場合は、ほとんどの種類の修復アクションを元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="39982-179">If any actions were taken as a result of false positives, you can undo most kinds of remediation actions.</span></span> <span data-ttu-id="39982-180">具体的には、次の方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="39982-180">Specifically, you can:</span></span>

- [<span data-ttu-id="39982-181">アクション センターから検疫済みファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="39982-181">Restore a quarantined file from the Action Center</span></span>](#restore-a-quarantined-file-from-the-action-center)
- [<span data-ttu-id="39982-182">複数の操作を一度に元に戻す</span><span class="sxs-lookup"><span data-stu-id="39982-182">Undo multiple actions at one time</span></span>](#undo-multiple-actions-at-one-time)
- <span data-ttu-id="39982-183">[複数のデバイス間で検疫からファイルを削除します](#remove-a-file-from-quarantine-across-multiple-devices)。</span><span class="sxs-lookup"><span data-stu-id="39982-183">[Remove a file from quarantine across multiple devices](#remove-a-file-from-quarantine-across-multiple-devices).</span></span>  <span data-ttu-id="39982-184">and</span><span class="sxs-lookup"><span data-stu-id="39982-184">and</span></span> 
- [<span data-ttu-id="39982-185">検疫からファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="39982-185">Restore file from quarantine</span></span>](#restore-file-from-quarantine)

<span data-ttu-id="39982-186">誤検知の結果として実行されたアクションの確認と元に戻す操作が完了したら、除外の確認または [定義に進みます](#part-3-review-or-define-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="39982-186">When you're done reviewing and undoing actions that were taken as a result of false positives, proceed to [review or define exclusions](#part-3-review-or-define-exclusions).</span></span>

### <a name="review-completed-actions"></a><span data-ttu-id="39982-187">完了したアクションを確認する</span><span class="sxs-lookup"><span data-stu-id="39982-187">Review completed actions</span></span>

1. <span data-ttu-id="39982-188">アクション センター ( ) に移動 [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="39982-188">Go to the Action center ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) and sign in.</span></span> 

2. <span data-ttu-id="39982-189">[履歴] **タブを** 選択して、実行されたアクションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="39982-189">Select the **History** tab to view a list of actions that were taken.</span></span>  

3. <span data-ttu-id="39982-190">アイテムを選択すると、実行された修復アクションの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39982-190">Select an item to view more details about the remediation action that was taken.</span></span>

### <a name="restore-a-quarantined-file-from-the-action-center"></a><span data-ttu-id="39982-191">アクション センターから検疫済みファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="39982-191">Restore a quarantined file from the Action Center</span></span>

1. <span data-ttu-id="39982-192">アクション センター ( ) に移動 [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="39982-192">Go to the Action center ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="39982-193">[履歴 **] タブ** で、元に戻す操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="39982-193">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="39982-194">フライアウト ウィンドウで、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-194">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="39982-195">このメソッドで操作を元に戻すことができない場合は、[元に戻す] ボタン **は表示** できません。</span><span class="sxs-lookup"><span data-stu-id="39982-195">If the action cannot be undone with this method, you will not see an **Undo** button.</span></span> <span data-ttu-id="39982-196">(詳細については、「完了した操作を [元に戻す」を参照](manage-auto-investigation.md#undo-completed-actions)してください。</span><span class="sxs-lookup"><span data-stu-id="39982-196">(To learn more, see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions).)</span></span>

### <a name="undo-multiple-actions-at-one-time"></a><span data-ttu-id="39982-197">複数の操作を一度に元に戻す</span><span class="sxs-lookup"><span data-stu-id="39982-197">Undo multiple actions at one time</span></span>

1. <span data-ttu-id="39982-198">アクション センター ( ) に移動 [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="39982-198">Go to the Action center ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="39982-199">[履歴 **] タブ** で、元に戻す操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="39982-199">On the **History** tab, select the actions that you want to undo.</span></span>

3. <span data-ttu-id="39982-200">画面の右側のウィンドウで、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-200">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="39982-201">複数のデバイスで検疫からファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="39982-201">Remove a file from quarantine across multiple devices</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="39982-202">![ファイルの検疫](images/autoir-quarantine-file-1.png)</span><span class="sxs-lookup"><span data-stu-id="39982-202">![Quarantine file](images/autoir-quarantine-file-1.png)</span></span>

1. <span data-ttu-id="39982-203">アクション センター ( ) に移動 [https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="39982-203">Go to the Action center ([https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="39982-204">[履歴 **] タブ** で、アクションの種類が [検疫ファイル] のファイルを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-204">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="39982-205">画面の右側のウィンドウで、[このファイルのインスタンスを **X** に適用する] を選択し、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-205">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

### <a name="restore-file-from-quarantine"></a><span data-ttu-id="39982-206">検疫からファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="39982-206">Restore file from quarantine</span></span>

<span data-ttu-id="39982-207">調査後にファイルがクリーンだと判断した場合は、ファイルをロールバックして検疫から削除できます。</span><span class="sxs-lookup"><span data-stu-id="39982-207">You can roll back and remove a file from quarantine if you’ve determined that it’s clean after an investigation.</span></span> <span data-ttu-id="39982-208">ファイルが検疫された各デバイスで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="39982-208">Run the following command on each device where the file was quarantined.</span></span>

1. <span data-ttu-id="39982-209">デバイスで管理者特権のコマンド ライン プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="39982-209">Open an elevated command–line prompt on the device:</span></span>

   1. <span data-ttu-id="39982-210">**[スタート]** をクリックし、「_cmd_」と入力します。</span><span class="sxs-lookup"><span data-stu-id="39982-210">Go to **Start** and type _cmd_.</span></span>

   1. <span data-ttu-id="39982-211">[コマンド プロンプト] を **右クリックし、[** 管理者として **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-211">Right–click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="39982-212">次のコマンドを入力し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="39982-212">Enter the following command, and press **Enter**:</span></span>

    ```console
    "ProgramFiles%\Windows Defender\MpCmdRun.exe" –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
    ```

    > [!NOTE]
    > <span data-ttu-id="39982-213">シナリオによっては **、ThreatName が** 次のように表示される場合があります `EUS:Win32/
CustomEnterpriseBlock!cl` 。</span><span class="sxs-lookup"><span data-stu-id="39982-213">In some scenarios, the **ThreatName** may appear as: `EUS:Win32/
CustomEnterpriseBlock!cl`.</span></span> <span data-ttu-id="39982-214">Defender for Endpoint は、過去 30 日間にこのデバイスで検疫されたカスタム ブロックされたファイルを復元します。</span><span class="sxs-lookup"><span data-stu-id="39982-214">Defender for Endpoint will restore all custom blocked files that were quarantined on this device in the last 30 days.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="39982-215">潜在的なネットワーク脅威として検疫されたファイルは、回復できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39982-215">A file that was quarantined as a potential network threat might not be recoverable.</span></span> <span data-ttu-id="39982-216">検疫後にユーザーがファイルを復元しようとすると、そのファイルにアクセスできない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39982-216">If a user attempts to restore the file after quarantine, that file might not be accessible.</span></span> <span data-ttu-id="39982-217">これは、システムがファイルにアクセスするためのネットワーク資格情報を持たなくなった場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39982-217">This can be due to the system no longer having network credentials to access the file.</span></span> <span data-ttu-id="39982-218">通常、これはシステムまたは共有フォルダーに一時的にログオンし、アクセス トークンの有効期限が切れた結果です。</span><span class="sxs-lookup"><span data-stu-id="39982-218">Typically, this is a result of a temporary log on to a system or shared folder and the access tokens expired.</span></span>

3. <span data-ttu-id="39982-219">画面の右側のウィンドウで、[このファイルのインスタンスを **X** に適用する] を選択し、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-219">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span> 


## <a name="part-3-review-or-define-exclusions"></a><span data-ttu-id="39982-220">パート 3: 除外を確認または定義する</span><span class="sxs-lookup"><span data-stu-id="39982-220">Part 3: Review or define exclusions</span></span>

<span data-ttu-id="39982-221">除外とは、修復アクションの例外として指定するファイルや URL などのエンティティです。</span><span class="sxs-lookup"><span data-stu-id="39982-221">An exclusion is an entity, such as a file or URL, that you specify as an exception to remediation actions.</span></span> <span data-ttu-id="39982-222">除外されたエンティティは引き続き検出できますが、そのエンティティに対して修復アクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="39982-222">The excluded entity can still get detected, but no remediation actions are taken on that entity.</span></span> <span data-ttu-id="39982-223">つまり、検出されたファイルまたはプロセスは、Microsoft Defender for Endpoint によって停止、検疫、削除、または変更に送信されません。</span><span class="sxs-lookup"><span data-stu-id="39982-223">That is, the detected file or process won’t be stopped, sent to quarantine, removed, or otherwise changed by Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="39982-224">Microsoft Defender for Endpoint 全体で除外を定義するには、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="39982-224">To define exclusions across Microsoft Defender for Endpoint, perform the following tasks:</span></span>
- [<span data-ttu-id="39982-225">Microsoft Defender ウイルス対策の除外を定義する</span><span class="sxs-lookup"><span data-stu-id="39982-225">Define exclusions for Microsoft Defender Antivirus</span></span>](#exclusions-for-microsoft-defender-antivirus)
- [<span data-ttu-id="39982-226">Microsoft Defender for Endpoint の "許可" インジケーターを作成する</span><span class="sxs-lookup"><span data-stu-id="39982-226">Create “allow” indicators for Microsoft Defender for Endpoint</span></span>](#indicators-for-microsoft-defender-for-endpoint)

> [!NOTE]
> <span data-ttu-id="39982-227">Microsoft Defender ウイルス対策の除外はウイルス対策保護にのみ適用されます。他の Microsoft Defender for Endpoint 機能には適用されません。</span><span class="sxs-lookup"><span data-stu-id="39982-227">Microsoft Defender Antivirus exclusions apply only to antivirus protection, not across other Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="39982-228">ファイルを広く除外するには、Microsoft Defender ウイルス対策の[](/microsoft-365/security/defender-endpoint/manage-indicators)除外と、Microsoft Defender for Endpoint のカスタム インジケーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="39982-228">To exclude files broadly, use exclusions for Microsoft Defender Antivirus and [custom indicators](/microsoft-365/security/defender-endpoint/manage-indicators) for Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="39982-229">このセクションの手順では、除外とインジケーターを定義する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="39982-229">The procedures in this section describe how to define exclusions and indicators.</span></span>

### <a name="exclusions-for-microsoft-defender-antivirus"></a><span data-ttu-id="39982-230">Microsoft Defender ウイルス対策の除外</span><span class="sxs-lookup"><span data-stu-id="39982-230">Exclusions for Microsoft Defender Antivirus</span></span>

<span data-ttu-id="39982-231">一般に、Microsoft Defender ウイルス対策の除外を定義する必要はない必要があります。</span><span class="sxs-lookup"><span data-stu-id="39982-231">In general, you should not need to define exclusions for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="39982-232">除外を定義し、誤検知の結果として生じるファイル、フォルダー、プロセス、およびプロセスで開いたファイルのみを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="39982-232">Make sure that you define exclusions sparingly, and that you only include the files, folders, processes, and process-opened files that are resulting in false positives.</span></span> <span data-ttu-id="39982-233">また、定義済みの除外を定期的に確認してください。</span><span class="sxs-lookup"><span data-stu-id="39982-233">In addition, make sure to review your defined exclusions regularly.</span></span> <span data-ttu-id="39982-234">Microsoft Endpoint [Manager を使用してウイルス](/mem/endpoint-manager-overview)対策の除外を定義または編集することをお勧めします。ただし、グループ ポリシーなどの他のメソッドを使用[](/azure/active-directory-domain-services/manage-group-policy)できます (「Manage [Microsoft Defender for Endpoint」を参照)。](manage-atp-post-migration.md)</span><span class="sxs-lookup"><span data-stu-id="39982-234">We recommend using [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to define or edit your antivirus exclusions; however, you can use other methods, such as [Group Policy](/azure/active-directory-domain-services/manage-group-policy) (see [Manage Microsoft Defender for Endpoint](manage-atp-post-migration.md)).</span></span>

> [!TIP]
> <span data-ttu-id="39982-235">ウイルス対策の除外に関するヘルプが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="39982-235">Need help with antivirus exclusions?</span></span> <span data-ttu-id="39982-236">「Microsoft [Defender ウイルス対策スキャンの除外の構成と検証」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="39982-236">See [Configure and validate exclusions for Microsoft Defender Antivirus scans](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span>

#### <a name="use-microsoft-endpoint-manager-to-manage-antivirus-exclusions-for-existing-policies"></a><span data-ttu-id="39982-237">Microsoft Endpoint Manager を使用してウイルス対策の除外を管理する (既存のポリシーの場合)</span><span class="sxs-lookup"><span data-stu-id="39982-237">Use Microsoft Endpoint Manager to manage antivirus exclusions (for existing policies)</span></span>

1. <span data-ttu-id="39982-238">Microsoft Endpoint Manager 管理センター ( ) に移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="39982-238">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="39982-239">[**エンドポイント セキュリティ**  >  **ウイルス対策]** を選択し、既存のポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="39982-239">Choose **Endpoint security** > **Antivirus**, and then select an existing policy.</span></span> <span data-ttu-id="39982-240">(既存のポリシーを使用しない場合、または新しいポリシーを作成する場合は、次の手順[に進む)。](#use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions)</span><span class="sxs-lookup"><span data-stu-id="39982-240">(If you don’t have an existing policy, or you want to create a new policy, skip to [the next procedure](#use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions)).</span></span>

3. <span data-ttu-id="39982-241">[プロパティ **] を** 選択し、[構成設定] **の横にある [** 編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-241">Choose **Properties**, and next to **Configuration settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="39982-242">[Microsoft **Defender ウイルス対策の除外] を** 展開し、除外を指定します。</span><span class="sxs-lookup"><span data-stu-id="39982-242">Expand **Microsoft Defender Antivirus Exclusions** and then specify your exclusions.</span></span>

5. <span data-ttu-id="39982-243">[ **確認] + [保存] の** 順に選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-243">Choose **Review + save**, and then choose **Save**.</span></span>

#### <a name="use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions"></a><span data-ttu-id="39982-244">Microsoft Endpoint Manager を使用して、除外を含む新しいウイルス対策ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="39982-244">Use Microsoft Endpoint Manager to create a new antivirus policy with exclusions</span></span>

1. <span data-ttu-id="39982-245">Microsoft Endpoint Manager 管理センター ( ) に移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="39982-245">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="39982-246">[エンドポイント **セキュリティウイルス**  >  **対策**  >  **] + [ポリシーの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-246">Choose **Endpoint security** > **Antivirus** > **+ Create Policy**.</span></span> 

3. <span data-ttu-id="39982-247">プラットフォーム **(Windows 10** 以降 **、macOS、Windows** 10 および Windows Server など **) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-247">Select a platform (such as **Windows 10 and later**, **macOS**, or **Windows 10 and Windows Server**).</span></span>

4. <span data-ttu-id="39982-248">[**プロファイル] で\*\*\*\*、[Microsoft Defender ウイルス対策の除外**] を選択し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-248">For **Profile**, select **Microsoft Defender Antivirus exclusions**, and then choose **Create**.</span></span>

5. <span data-ttu-id="39982-249">プロファイルの名前と説明を指定し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-249">Specify a name and description for the profile, and then choose **Next**.</span></span>

6. <span data-ttu-id="39982-250">[構成 **設定] タブ** で、ウイルス対策の除外を指定し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-250">On the **Configuration settings** tab, specify your antivirus exclusions, and then choose **Next**.</span></span>

7. <span data-ttu-id="39982-251">[スコープ **タグ] タブ** で、組織でスコープ タグを使用している場合は、作成するポリシーのスコープ タグを指定します。</span><span class="sxs-lookup"><span data-stu-id="39982-251">On the **Scope tags** tab, if you are using scope tags in your organization, specify scope tags for the policy you are creating.</span></span> <span data-ttu-id="39982-252">[(「Scope tags .」を](/mem/intune/fundamentals/scope-tags)参照)</span><span class="sxs-lookup"><span data-stu-id="39982-252">(See [Scope tags](/mem/intune/fundamentals/scope-tags).)</span></span>

8. <span data-ttu-id="39982-253">[割 **り当て]** タブで、ポリシーを適用するユーザーとグループを指定し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-253">On the **Assignments** tab, specify the users and groups to whom your policy should be applied, and then choose **Next**.</span></span> <span data-ttu-id="39982-254">(割り当てのヘルプが必要な場合は [、「Assign user and device profiles in Microsoft Intune 」を参照](/mem/intune/configuration/device-profile-assign)してください。</span><span class="sxs-lookup"><span data-stu-id="39982-254">(If you need help with assignments, see [Assign user and device profiles in Microsoft Intune](/mem/intune/configuration/device-profile-assign).)</span></span>

9. <span data-ttu-id="39982-255">[確認 **と作成] タブで** 設定を確認し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-255">On the **Review + create** tab, review the settings, and then choose **Create**.</span></span>

### <a name="indicators-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="39982-256">エンドポイント用 Microsoft Defender のインジケーター</span><span class="sxs-lookup"><span data-stu-id="39982-256">Indicators for Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="39982-257">[インジケーター](/microsoft-365/security/defender-endpoint/manage-indicators) (特に、侵害の指標、または IoC) を使用すると、セキュリティ運用チームはエンティティの検出、防止、除外を定義できます。</span><span class="sxs-lookup"><span data-stu-id="39982-257">[Indicators](/microsoft-365/security/defender-endpoint/manage-indicators) (specifically, indicators of compromise, or IoCs) enable your security operations team to define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="39982-258">たとえば、Microsoft Defender for Endpoint のスキャンおよび修復アクションから除外する特定のファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="39982-258">For example, you can specify certain files to be omitted from scans and remediation actions in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="39982-259">または、インジケーターを使用して、特定のファイル、IP アドレス、または URL に対するアラートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="39982-259">Or, indicators can be used to generate alerts for certain files, IP addresses, or URLs.</span></span>

<span data-ttu-id="39982-260">Microsoft Defender for Endpoint の除外としてエンティティを指定するには、それらのエンティティの "許可" インジケーターを作成します。</span><span class="sxs-lookup"><span data-stu-id="39982-260">To specify entities as exclusions for Microsoft Defender for Endpoint, create "allow" indicators for those entities.</span></span> <span data-ttu-id="39982-261">Microsoft Defender for Endpoint のこのような "[](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)許可" インジケーターは[](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)、次世代の保護、エンドポイントの検出と応答、および修復の自動化された調査&[適用されます](/microsoft-365/security/defender-endpoint/automated-investigations)。</span><span class="sxs-lookup"><span data-stu-id="39982-261">Such "allow" indicators in Microsoft Defender for Endpoint apply to [next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), [endpoint detection and response](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response), and [automated investigation & remediation](/microsoft-365/security/defender-endpoint/automated-investigations).</span></span>

<span data-ttu-id="39982-262">"許可" インジケーターは、次の場合に作成できます。</span><span class="sxs-lookup"><span data-stu-id="39982-262">"Allow" indicators can be created for:</span></span>

- [<span data-ttu-id="39982-263">Files</span><span class="sxs-lookup"><span data-stu-id="39982-263">Files</span></span>](#indicators-for-files)
- [<span data-ttu-id="39982-264">IP アドレス、URL、およびドメイン</span><span class="sxs-lookup"><span data-stu-id="39982-264">IP addresses, URLs, and domains</span></span>](#indicators-for-ip-addresses-urls-or-domains)
- [<span data-ttu-id="39982-265">アプリケーション証明書</span><span class="sxs-lookup"><span data-stu-id="39982-265">Application certificates</span></span>](#indicators-for-application-certificates)

![インジケーターの種類の図](images/false-positives-indicators.png)

#### <a name="indicators-for-files"></a><span data-ttu-id="39982-267">ファイルのインジケーター</span><span class="sxs-lookup"><span data-stu-id="39982-267">Indicators for files</span></span>

<span data-ttu-id="39982-268">実行可能ファイル [などのファイルの "許可"](/microsoft-365/security/defender-endpoint/indicator-file)インジケーターを作成すると、組織で使用しているファイルがブロックされるのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39982-268">When you [create an "allow" indicator for a file, such as an executable](/microsoft-365/security/defender-endpoint/indicator-file), it helps prevent files that your organization is using from being blocked.</span></span> <span data-ttu-id="39982-269">ファイルには、ポータブル実行可能ファイル (PE) ファイル (ファイルなど) `.exe` を含 `.dll` めることもできます。</span><span class="sxs-lookup"><span data-stu-id="39982-269">Files can include portable executable (PE) files, such as `.exe` and `.dll` files.</span></span> 

<span data-ttu-id="39982-270">ファイルのインジケーターを作成する前に、次の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="39982-270">Before you create indicators for files, make sure the following requirements are met:</span></span>
- <span data-ttu-id="39982-271">Microsoft Defender ウイルス対策は、クラウドベースの保護が有効に設定されています (「クラウドベースの保護の管理[」を参照)](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="39982-271">Microsoft Defender Antivirus is configured with cloud-based protection enabled (see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus))</span></span>
- <span data-ttu-id="39982-272">マルウェア対策クライアントのバージョンは 4.18.1901.x 以降です</span><span class="sxs-lookup"><span data-stu-id="39982-272">Antimalware client version is 4.18.1901.x or later</span></span> 
- <span data-ttu-id="39982-273">デバイスは Windows 10 バージョン 1703 以降を実行しています。Windows Server 2016;または Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="39982-273">Devices are running Windows 10, version 1703 or later; Windows Server 2016; or Windows Server 2019</span></span> 
- <span data-ttu-id="39982-274">[ [ブロックまたは許可] 機能がオンになっている](/microsoft-365/security/defender-endpoint/advanced-features)</span><span class="sxs-lookup"><span data-stu-id="39982-274">The [Block or allow feature is turned on](/microsoft-365/security/defender-endpoint/advanced-features)</span></span> 

#### <a name="indicators-for-ip-addresses-urls-or-domains"></a><span data-ttu-id="39982-275">IP アドレス、URL、またはドメインのインジケーター</span><span class="sxs-lookup"><span data-stu-id="39982-275">Indicators for IP addresses, URLs, or domains</span></span>

<span data-ttu-id="39982-276">IP アドレス [、URL、](/microsoft-365/security/defender-endpoint/indicator-ip-domain)またはドメインの "許可" インジケーターを作成すると、組織が使用するサイトまたは IP アドレスがブロックされるのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39982-276">When you [create an "allow" indicator for an IP address, URL, or domain](/microsoft-365/security/defender-endpoint/indicator-ip-domain), it helps prevent the sites or IP addresses your organization uses from being blocked.</span></span>

<span data-ttu-id="39982-277">IP アドレス、URL、またはドメインのインジケーターを作成する前に、次の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="39982-277">Before you create indicators for IP addresses, URLs, or domains, make sure the following requirements are met:</span></span>
- <span data-ttu-id="39982-278">Defender for Endpoint のネットワーク保護がブロック モードで有効になっている (「ネットワーク保護を有効[にする」を参照)](/microsoft-365/security/defender-endpoint/enable-network-protection)</span><span class="sxs-lookup"><span data-stu-id="39982-278">Network protection in Defender for Endpoint is enabled in block mode (see [Enable network protection](/microsoft-365/security/defender-endpoint/enable-network-protection))</span></span>
- <span data-ttu-id="39982-279">マルウェア対策クライアントのバージョンは 4.18.1906.x 以降です</span><span class="sxs-lookup"><span data-stu-id="39982-279">Antimalware client version is 4.18.1906.x or later</span></span> 
- <span data-ttu-id="39982-280">デバイスが Windows 10 バージョン 1709 以降を実行している</span><span class="sxs-lookup"><span data-stu-id="39982-280">Devices are running Windows 10, version 1709, or later</span></span> 

<span data-ttu-id="39982-281">Microsoft Defender セキュリティ センターでカスタム ネットワーク インジケーターが有効になっている (「高度な[機能」を参照)](/microsoft-365/security/defender-endpoint/advanced-features)</span><span class="sxs-lookup"><span data-stu-id="39982-281">Custom network indicators are turned on in the Microsoft Defender Security Center (see [Advanced features](/microsoft-365/security/defender-endpoint/advanced-features))</span></span>   

#### <a name="indicators-for-application-certificates"></a><span data-ttu-id="39982-282">アプリケーション証明書のインジケーター</span><span class="sxs-lookup"><span data-stu-id="39982-282">Indicators for application certificates</span></span> 

<span data-ttu-id="39982-283">アプリケーション証明書 [の "許可"](/microsoft-365/security/defender-endpoint/indicator-certificates)インジケーターを作成すると、組織が使用する内部開発アプリケーションなどのアプリケーションがブロックされるのを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39982-283">When you [create an "allow" indicator for an application certificate](/microsoft-365/security/defender-endpoint/indicator-certificates), it helps prevent applications, such as internally developed applications, that your organization uses from being blocked.</span></span> <span data-ttu-id="39982-284">`.CER` または `.PEM` ファイル拡張子がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="39982-284">`.CER` or `.PEM` file extensions are supported.</span></span>   

<span data-ttu-id="39982-285">アプリケーション証明書のインジケーターを作成する前に、次の要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="39982-285">Before you create indicators for application certificates, make sure the following requirements are met:</span></span>
- <span data-ttu-id="39982-286">Microsoft Defender ウイルス対策は、クラウドベースの保護が有効に設定されています (「クラウドベースの保護の管理[」を参照)](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="39982-286">Microsoft Defender Antivirus is configured with cloud-based protection enabled (see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus))</span></span>
- <span data-ttu-id="39982-287">マルウェア対策クライアントのバージョンは 4.18.1901.x 以降です</span><span class="sxs-lookup"><span data-stu-id="39982-287">Antimalware client version is 4.18.1901.x or later</span></span> 
- <span data-ttu-id="39982-288">デバイスは Windows 10 バージョン 1703 以降を実行しています。Windows Server 2016;または Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="39982-288">Devices are running Windows 10, version 1703 or later; Windows Server 2016; or Windows Server 2019</span></span> 
- <span data-ttu-id="39982-289">ウイルスと脅威の保護の定義が最新</span><span class="sxs-lookup"><span data-stu-id="39982-289">Virus and threat protection definitions are up to date</span></span>  

> [!TIP]
> <span data-ttu-id="39982-290">インジケーターを作成する場合は、それらを 1 つ 1 つ定義するか、複数のアイテムを一度にインポートできます。</span><span class="sxs-lookup"><span data-stu-id="39982-290">When you create indicators, you can define them one by one, or import multiple items at once.</span></span> <span data-ttu-id="39982-291">1 つのテナントには 15,000 のインジケーターの制限があります。</span><span class="sxs-lookup"><span data-stu-id="39982-291">Keep in mind there's a limit of 15,000 indicators for a single tenant.</span></span> <span data-ttu-id="39982-292">また、ファイル ハッシュ情報など、特定の詳細を最初に収集する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="39982-292">And, you might need to gather certain details first, such as file hash information.</span></span> <span data-ttu-id="39982-293">インジケーターを作成する前に前提条件を確認 [してください](manage-indicators.md)。</span><span class="sxs-lookup"><span data-stu-id="39982-293">Make sure to review the prerequisites before you [create indicators](manage-indicators.md).</span></span> 

## <a name="part-4-submit-a-file-for-analysis"></a><span data-ttu-id="39982-294">パート 4: 分析用にファイルを送信する</span><span class="sxs-lookup"><span data-stu-id="39982-294">Part 4: Submit a file for analysis</span></span>

<span data-ttu-id="39982-295">分析のために、ファイルやファイルレス検出などのエンティティを Microsoft に送信できます。</span><span class="sxs-lookup"><span data-stu-id="39982-295">You can submit entities, such as files and fileless detections, to Microsoft for analysis.</span></span> <span data-ttu-id="39982-296">Microsoft セキュリティ研究者は、すべての申請を分析し、その結果は Microsoft Defender for Endpoint の脅威保護機能を知らせるのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39982-296">Microsoft security researchers analyze all submissions, and their results help inform Microsoft Defender for Endpoint threat protection capabilities.</span></span> <span data-ttu-id="39982-297">申請サイトでサインインすると、申請を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="39982-297">When you sign in at the submission site, you can track your submissions.</span></span>

### <a name="submit-a-file-for-analysis"></a><span data-ttu-id="39982-298">分析用にファイルを送信する</span><span class="sxs-lookup"><span data-stu-id="39982-298">Submit a file for analysis</span></span>

<span data-ttu-id="39982-299">悪意のあるファイルとして誤って検出された、または見つからないファイルがある場合は、次の手順に従ってファイルを送信して分析します。</span><span class="sxs-lookup"><span data-stu-id="39982-299">If you have a file that was either wrongly detected as malicious or was missed, follow these steps to submit the file for analysis.</span></span>

1. <span data-ttu-id="39982-300">「分析用にファイルを [送信する」のガイドラインを確認します](/windows/security/threat-protection/intelligence/submission-guide)。</span><span class="sxs-lookup"><span data-stu-id="39982-300">Review the guidelines here: [Submit files for analysis](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="39982-301">Microsoft Security Intelligence 申請サイト ( ) にアクセス [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) し、ファイルを提出します。</span><span class="sxs-lookup"><span data-stu-id="39982-301">Visit the Microsoft Security Intelligence submission site ([https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission)), and submit your file(s).</span></span>

### <a name="submit-a-fileless-detection-for-analysis"></a><span data-ttu-id="39982-302">分析用にファイルレス検出を送信する</span><span class="sxs-lookup"><span data-stu-id="39982-302">Submit a fileless detection for analysis</span></span>

<span data-ttu-id="39982-303">動作に基づいてマルウェアとして検出され、ファイルを持ってない場合は、ファイルを送信して分析 `Mpsupport.cab` することができます。</span><span class="sxs-lookup"><span data-stu-id="39982-303">If something was detected as malware based on behavior, and you don’t have a file, you can submit your `Mpsupport.cab` file for analysis.</span></span> <span data-ttu-id="39982-304">Windows 10 の Microsoft Malware Protection Command-Lineユーティリティ (MPCmdRun.exe) ツールを使用して *、.cab* ファイルを取得できます。</span><span class="sxs-lookup"><span data-stu-id="39982-304">You can get the *.cab* file by using the Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) tool on Windows 10.</span></span>

1.  <span data-ttu-id="39982-305">に移動 ` C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` し、管理者 `MpCmdRun.exe` として実行します。</span><span class="sxs-lookup"><span data-stu-id="39982-305">Go to ` C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`, and then run `MpCmdRun.exe` as an administrator.</span></span>

2.  <span data-ttu-id="39982-306">を `mpcmdrun.exe -GetFiles` 入力し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="39982-306">Type `mpcmdrun.exe -GetFiles`, and then press **Enter**.</span></span>
   <span data-ttu-id="39982-307">さまざまな診断ログを含む .cab ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="39982-307">A .cab file is generated that contains various diagnostic logs.</span></span> <span data-ttu-id="39982-308">ファイルの場所は、コマンド プロンプトの出力で指定されます。</span><span class="sxs-lookup"><span data-stu-id="39982-308">The location of the file is specified in the output of the command prompt.</span></span> <span data-ttu-id="39982-309">既定では、場所は `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` .</span><span class="sxs-lookup"><span data-stu-id="39982-309">By default, the location is `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab`.</span></span>

3.  <span data-ttu-id="39982-310">「分析用にファイルを [送信する」のガイドラインを確認します](/windows/security/threat-protection/intelligence/submission-guide)。</span><span class="sxs-lookup"><span data-stu-id="39982-310">Review the guidelines here: [Submit files for analysis](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

4.  <span data-ttu-id="39982-311">Microsoft Security Intelligence 申請サイト ( ) にアクセスし [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) 、.cab ファイルを提出します。</span><span class="sxs-lookup"><span data-stu-id="39982-311">Visit the Microsoft Security Intelligence submission site ([https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission)), and submit your .cab files.</span></span>

### <a name="what-happens-after-a-file-is-submitted"></a><span data-ttu-id="39982-312">ファイルが送信された後は何が起こりますか?</span><span class="sxs-lookup"><span data-stu-id="39982-312">What happens after a file is submitted?</span></span>

<span data-ttu-id="39982-313">アナリストがケースの処理を開始する前に、お客様の提出が直ちにシステムによってスキャンされ、最新の判断が下されます。</span><span class="sxs-lookup"><span data-stu-id="39982-313">Your submission is immediately scanned by our systems to give you the latest determination even before an analyst starts handling your case.</span></span> <span data-ttu-id="39982-314">ファイルがアナリストによって既に送信および処理されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39982-314">It’s possible that a file might have already been submitted and processed by an analyst.</span></span> <span data-ttu-id="39982-315">そのような場合、決定は迅速に行います。</span><span class="sxs-lookup"><span data-stu-id="39982-315">In those cases, a determination is made quickly.</span></span>

<span data-ttu-id="39982-316">処理されていない申請の場合、次のように分析の優先順位が設定されます。</span><span class="sxs-lookup"><span data-stu-id="39982-316">For submissions that were not already processed, they are prioritized for analysis as follows:</span></span>

- <span data-ttu-id="39982-317">多数のコンピューターに影響を与える可能性のある一般的なファイルの優先度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39982-317">Prevalent files with the potential to impact large numbers of computers are given a higher priority.</span></span>
- <span data-ttu-id="39982-318">認証された顧客、特に有効なソフトウェア アシュアランス [ID (SAID)](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx)を持つエンタープライズのお客様には、優先度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="39982-318">Authenticated customers, especially enterprise customers with valid [Software Assurance IDs (SAIDs)](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx), are given a higher priority.</span></span>
- <span data-ttu-id="39982-319">SAID 所有者による優先度の高いフラグが付いた申請は、直ちに注意を払います。</span><span class="sxs-lookup"><span data-stu-id="39982-319">Submissions flagged as high priority by SAID holders are given immediate attention.</span></span>

<span data-ttu-id="39982-320">申請に関する更新プログラムを確認するには、Microsoft セキュリティ インテリジェンス申請サイト [でサインインします](https://www.microsoft.com/wdsi/filesubmission)。</span><span class="sxs-lookup"><span data-stu-id="39982-320">To check for updates regarding your submission, sign in at the [Microsoft Security Intelligence submission site](https://www.microsoft.com/wdsi/filesubmission).</span></span> 

> [!TIP]
> <span data-ttu-id="39982-321">詳細については、「分析用に [ファイルを送信する」を参照してください](/windows/security/threat-protection/intelligence/submission-guide#how-does-microsoft-prioritize-submissions)。</span><span class="sxs-lookup"><span data-stu-id="39982-321">To learn more, see [Submit files for analysis](/windows/security/threat-protection/intelligence/submission-guide#how-does-microsoft-prioritize-submissions).</span></span>

## <a name="part-5-review-and-adjust-your-threat-protection-settings"></a><span data-ttu-id="39982-322">パート 5: 脅威保護の設定を確認して調整する</span><span class="sxs-lookup"><span data-stu-id="39982-322">Part 5: Review and adjust your threat protection settings</span></span>

<span data-ttu-id="39982-323">Microsoft Defender for Endpoint には、さまざまな機能や機能の設定を微調整する機能など、さまざまなオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="39982-323">Microsoft Defender for Endpoint offers a wide variety of options, including the ability to fine-tune settings for various features and capabilities.</span></span> <span data-ttu-id="39982-324">多数の誤検知が発生している場合は、必ず組織の脅威保護設定を確認してください。</span><span class="sxs-lookup"><span data-stu-id="39982-324">If you’re getting numerous false positives, make sure to review your organization’s threat protection settings.</span></span> <span data-ttu-id="39982-325">次の調整が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="39982-325">You might need to make some adjustments to:</span></span>

- [<span data-ttu-id="39982-326">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="39982-326">Cloud-delivered protection</span></span>](#cloud-delivered-protection)
- [<span data-ttu-id="39982-327">望ましくない可能性のあるアプリケーションの修復</span><span class="sxs-lookup"><span data-stu-id="39982-327">Remediation for potentially unwanted applications</span></span>](#remediation-for-potentially-unwanted-applications)
- [<span data-ttu-id="39982-328">調査と修復の自動化</span><span class="sxs-lookup"><span data-stu-id="39982-328">Automated investigation and remediation</span></span>](#automated-investigation-and-remediation)

### <a name="cloud-delivered-protection"></a><span data-ttu-id="39982-329">クラウドによる保護</span><span class="sxs-lookup"><span data-stu-id="39982-329">Cloud-delivered protection</span></span>

<span data-ttu-id="39982-330">Microsoft Defender ウイルス対策のクラウド配信の保護レベルを確認します。</span><span class="sxs-lookup"><span data-stu-id="39982-330">Check your cloud-delivered protection level for Microsoft Defender Antivirus.</span></span> <span data-ttu-id="39982-331">既定では、クラウド配信の保護は [ **構成** されていません] に設定されています。これは、ほとんどの組織の通常のレベルの保護に対応します。</span><span class="sxs-lookup"><span data-stu-id="39982-331">By default, cloud-delivered protection is set to **Not configured**, which corresponds to a normal level of protection for most organizations.</span></span> <span data-ttu-id="39982-332">クラウド配信の保護が高、高 **+、** またはゼロ許容値に設定されている場合は、誤検知の数が多くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39982-332">If your cloud-delivered protection is set to **High**, **High +**, or **Zero tolerance**, you might experience a higher number of false positives.</span></span>

> [!TIP]
> <span data-ttu-id="39982-333">クラウド配信保護の構成の詳細については、「クラウド配信の保護レベルを指定する [」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="39982-333">To learn more about configuring your cloud-delivered protection, see [Specify the cloud-delivered protection level](/windows/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="39982-334">Microsoft Endpoint Manager を[使用して](/mem/endpoint-manager-overview)、クラウド配信の保護設定を編集または設定することをお勧めします。ただし、グループ ポリシーなどの他のメソッドを使用[](/azure/active-directory-domain-services/manage-group-policy)できます (「Manage [Microsoft Defender for Endpoint」を参照)。](manage-atp-post-migration.md)</span><span class="sxs-lookup"><span data-stu-id="39982-334">We recommend using [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to edit or set your cloud-delivered protection settings; however, you can use other methods, such as [Group Policy](/azure/active-directory-domain-services/manage-group-policy) (see [Manage Microsoft Defender for Endpoint](manage-atp-post-migration.md)).</span></span>

#### <a name="use-microsoft-endpoint-manager-to-review-and-edit-cloud-delivered-protection-settings-for-existing-policies"></a><span data-ttu-id="39982-335">Microsoft Endpoint Manager を使用してクラウド配信の保護設定を確認および編集する (既存のポリシーの場合)</span><span class="sxs-lookup"><span data-stu-id="39982-335">Use Microsoft Endpoint Manager to review and edit cloud-delivered protection settings (for existing policies)</span></span>

1. <span data-ttu-id="39982-336">Microsoft Endpoint Manager 管理センター ( ) に移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="39982-336">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="39982-337">[**エンドポイント セキュリティウイルス**  >  **対策] を** 選択し、既存のポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="39982-337">Choose **Endpoint security** > **Antivirus** and then select an existing policy.</span></span> <span data-ttu-id="39982-338">(既存のポリシーを使用しない場合、または新しいポリシーを作成する場合は、次の手順[に進む)。](#use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy)</span><span class="sxs-lookup"><span data-stu-id="39982-338">(If you don’t have an existing policy, or you want to create a new policy, skip to [the next procedure](#use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy)).</span></span>

3. <span data-ttu-id="39982-339">[管理 **] で**、[プロパティ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-339">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="39982-340">次に、[構成設定] **の横にある**[編集] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-340">Then, next to **Configuration settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="39982-341">[ **クラウド保護] を** 展開し、[クラウド配信の保護レベル] 行で現在 **の設定を確認** します。</span><span class="sxs-lookup"><span data-stu-id="39982-341">Expand **Cloud protection**, and review your current setting in the **Cloud-delivered protection level** row.</span></span> <span data-ttu-id="39982-342">クラウド配信の保護を **[構成** されていない] に設定することをお勧めします。これは強力な保護を提供し、誤検知を受け取る可能性を減らします。</span><span class="sxs-lookup"><span data-stu-id="39982-342">We recommend setting cloud-delivered protection to **Not configured**, which provides strong protection while reducing the chances of getting false positives.</span></span>

5. <span data-ttu-id="39982-343">[ **確認] + [保存] の** 順に選択し、[保存] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-343">Choose **Review + save**, and then **Save**.</span></span>

#### <a name="use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy"></a><span data-ttu-id="39982-344">Microsoft Endpoint Manager を使用してクラウド配信の保護設定を設定する (新しいポリシーの場合)</span><span class="sxs-lookup"><span data-stu-id="39982-344">Use Microsoft Endpoint Manager to set cloud-delivered protection settings (for a new policy)</span></span>

1. <span data-ttu-id="39982-345">Microsoft Endpoint Manager 管理センター ( ) に移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="39982-345">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="39982-346">[エンドポイント **セキュリティの**  >  **ウイルス対策**  >  **] + [ポリシーの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-346">Choose **Endpoint security** > **Antivirus** > **+ Create policy**.</span></span>

3. <span data-ttu-id="39982-347">[**プラットフォーム]** でオプションを選択し、[プロファイル]で **[ウイルス** 対策] または **[Microsoft Defender ウイルス** 対策] を選択します (特定のオプションは、プラットフォームで選択した内容によって **異** なります)。次に、[作成]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-347">For **Platform**, select an option, and then for **Profile**, select **Antivirus** or **Microsoft Defender Antivirus** (the specific option depends on what you selected for **Platform**.) Then choose **Create**.</span></span>

4. <span data-ttu-id="39982-348">[基本 **] タブで** 、ポリシーの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="39982-348">On the **Basics** tab, specify a name and description for the policy.</span></span> <span data-ttu-id="39982-349">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39982-349">Then choose **Next**.</span></span>

5. <span data-ttu-id="39982-350">[構成設定 **] タブで** 、[クラウド保護] **を展開** し、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="39982-350">On the **Configuration settings** tab, expand **Cloud protection**, and specify the following settings:</span></span>
   - <span data-ttu-id="39982-351">[クラウド **配信の保護を有効にする] を [はい** ] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="39982-351">Set **Turn on cloud-delivered protection** to **Yes**.</span></span>
   - <span data-ttu-id="39982-352">[ **クラウド配信の保護レベル] を [** 構成されていません **] に設定します**。</span><span class="sxs-lookup"><span data-stu-id="39982-352">Set **Cloud-delivered protection level** to **Not configured**.</span></span> <span data-ttu-id="39982-353">(このレベルは、既定では強力なレベルの保護を提供し、誤検知を受け取る可能性を減らします)。</span><span class="sxs-lookup"><span data-stu-id="39982-353">(This level provides a strong level of protection by default while reducing the chances of getting false positives.)</span></span>

6. <span data-ttu-id="39982-354">[スコープ **タグ] タブ** で、組織でスコープ タグを使用している場合は、ポリシーのスコープ タグを指定します。</span><span class="sxs-lookup"><span data-stu-id="39982-354">On the **Scope tags** tab, if you are using scope tags in your organization, specify scope tags for the policy.</span></span> <span data-ttu-id="39982-355">[(「Scope tags .」を](/mem/intune/fundamentals/scope-tags)参照)</span><span class="sxs-lookup"><span data-stu-id="39982-355">(See [Scope tags](/mem/intune/fundamentals/scope-tags).)</span></span>

7. <span data-ttu-id="39982-356">[割 **り当て]** タブで、ポリシーを適用するユーザーとグループを指定し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-356">On the **Assignments** tab, specify the users and groups to whom your policy should be applied, and then choose **Next**.</span></span> <span data-ttu-id="39982-357">(割り当てのヘルプが必要な場合は [、「Assign user and device profiles in Microsoft Intune 」を参照](/mem/intune/configuration/device-profile-assign)してください。</span><span class="sxs-lookup"><span data-stu-id="39982-357">(If you need help with assignments, see [Assign user and device profiles in Microsoft Intune](/mem/intune/configuration/device-profile-assign).)</span></span>

8. <span data-ttu-id="39982-358">[確認 **と作成] タブで** 設定を確認し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-358">On the **Review + create** tab, review the settings, and then choose **Create**.</span></span>  

### <a name="remediation-for-potentially-unwanted-applications"></a><span data-ttu-id="39982-359">望ましくない可能性のあるアプリケーションの修復</span><span class="sxs-lookup"><span data-stu-id="39982-359">Remediation for potentially unwanted applications</span></span>

<span data-ttu-id="39982-360">望ましくない可能性のあるアプリケーション (PUA) は、デバイスの動作が遅くなる、予期しない広告を表示する、または予期しない、または望ましくない可能性のある他のソフトウェアをインストールするソフトウェアのカテゴリです。</span><span class="sxs-lookup"><span data-stu-id="39982-360">Potentially unwanted applications (PUA) are a category of software that can cause devices to run slowly, display unexpected ads, or install other software that might be unexpected or unwanted.</span></span> <span data-ttu-id="39982-361">PUA の例としては、広告ソフトウェア、バンドル ソフトウェア、セキュリティ製品の動作が異なる回避ソフトウェアがあります。</span><span class="sxs-lookup"><span data-stu-id="39982-361">Examples of PUA include advertising software, bundling software, and evasion software that behaves differently with security products.</span></span> <span data-ttu-id="39982-362">PUA はマルウェアとは見なされませんが、一部の種類のソフトウェアは、その動作と評判に基づいて PUA です。</span><span class="sxs-lookup"><span data-stu-id="39982-362">Although PUA is not considered malware, some kinds of software are PUA based on their behavior and reputation.</span></span>

> [!TIP]
> <span data-ttu-id="39982-363">PUA の詳細については、「望ましくない可能性のあるアプリケーションを検出して [ブロックする」を参照してください](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)。</span><span class="sxs-lookup"><span data-stu-id="39982-363">To learn more about PUA, see [Detect and block potentially unwanted applications](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus).</span></span>
 
<span data-ttu-id="39982-364">組織が使用しているアプリによっては、PUA 保護設定の結果として誤検知が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="39982-364">Depending on the apps your organization is using, you might be getting false positives as a result of your PUA protection settings.</span></span> <span data-ttu-id="39982-365">必要に応じて、監査モードで PUA 保護をしばらく実行するか、組織内のデバイスのサブセットに PUA 保護を適用します。</span><span class="sxs-lookup"><span data-stu-id="39982-365">If necessary, consider running PUA protection in audit mode for a while, or apply PUA protection to a subset of devices in your organization.</span></span> <span data-ttu-id="39982-366">PUA 保護は、Microsoft Edge ブラウザーと Microsoft Defender ウイルス対策用に構成できます。</span><span class="sxs-lookup"><span data-stu-id="39982-366">PUA protection can be configured for the Microsoft Edge browser and for Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="39982-367">Microsoft Endpoint Manager を[使用して PUA](/mem/endpoint-manager-overview)保護設定を編集または設定することをお勧めします。ただし、グループ ポリシーなどの他のメソッドを使用[](/azure/active-directory-domain-services/manage-group-policy)できます (「Manage [Microsoft Defender for Endpoint」を参照)。](manage-atp-post-migration.md)</span><span class="sxs-lookup"><span data-stu-id="39982-367">We recommend using [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to edit or set PUA protection settings; however, you can use other methods, such as [Group Policy](/azure/active-directory-domain-services/manage-group-policy) (see [Manage Microsoft Defender for Endpoint](manage-atp-post-migration.md)).</span></span>

#### <a name="use-microsoft-endpoint-manager-to-edit-pua-protection-for-existing-configuration-profiles"></a><span data-ttu-id="39982-368">Microsoft Endpoint Manager を使用して PUA 保護を編集する (既存の構成プロファイルの場合)</span><span class="sxs-lookup"><span data-stu-id="39982-368">Use Microsoft Endpoint Manager to edit PUA protection (for existing configuration profiles)</span></span>

1. <span data-ttu-id="39982-369">Microsoft Endpoint Manager 管理センター ( ) に移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="39982-369">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="39982-370">[**デバイス**  >  **構成プロファイル] を選択** し、既存のポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="39982-370">Choose **Devices** > **Configuration profiles**, and then select an existing policy.</span></span> <span data-ttu-id="39982-371">(既存のポリシーを使用しない場合、または新しいポリシーを作成する場合は、次の手順 [に進む必要があります](#use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile)。)</span><span class="sxs-lookup"><span data-stu-id="39982-371">(If you don’t have an existing policy, or you want to create a new policy, skip to [the next procedure](#use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile).)</span></span>

3. <span data-ttu-id="39982-372">[ **管理] で**、[ **プロパティ]** を選択し、[構成設定] の横にある **[編集**] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-372">Under **Manage**, choose **Properties**, and then, next to **Configuration settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="39982-373">[構成設定 **] タブで** 、下にスクロールし **、[Microsoft Defender ウイルス対策] を展開します**。</span><span class="sxs-lookup"><span data-stu-id="39982-373">On the **Configuration settings** tab, scroll down and expand **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="39982-374">[望 **ましくない可能性のあるアプリケーションを検出する] を [監査]** に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="39982-374">Set **Detect potentially unwanted applications** to **Audit**.</span></span> <span data-ttu-id="39982-375">(オフにできますが、監査モードを使用すると、検出を確認できます)。</span><span class="sxs-lookup"><span data-stu-id="39982-375">(You can turn it off, but by using audit mode, you will be able to see detections.)</span></span>

6. <span data-ttu-id="39982-376">[ **確認] + [保存] の** 順に選択し、[保存] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-376">Choose **Review + save**, and then choose **Save**.</span></span>

#### <a name="use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile"></a><span data-ttu-id="39982-377">Microsoft Endpoint Manager を使用して PUA 保護を設定する (新しい構成プロファイルの場合)</span><span class="sxs-lookup"><span data-stu-id="39982-377">Use Microsoft Endpoint Manager to set PUA protection (for a new configuration profile)</span></span>

1. <span data-ttu-id="39982-378">Microsoft Endpoint Manager 管理センター ( ) に移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="39982-378">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="39982-379">[デバイス  >  **構成プロファイル] +**  >  **[プロファイルの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-379">Choose **Devices** > **Configuration profiles** > **+ Create profile**.</span></span>

3. <span data-ttu-id="39982-380">[プラットフォーム **]** で **、[Windows 10 以降**] を選択し、[プロファイル] で [ **デバイス** の制限 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-380">For the **Platform**, choose **Windows 10 and later**, and for **Profile**, select **Device restrictions**.</span></span>

4. <span data-ttu-id="39982-381">[基本 **] タブで** 、ポリシーの名前と説明を指定します。</span><span class="sxs-lookup"><span data-stu-id="39982-381">On the **Basics** tab, specify a name and description for your policy.</span></span> <span data-ttu-id="39982-382">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39982-382">Then choose **Next**.</span></span>

5. <span data-ttu-id="39982-383">[構成設定 **] タブで** 、下にスクロールし **、[Microsoft Defender ウイルス対策] を展開します**。</span><span class="sxs-lookup"><span data-stu-id="39982-383">On the **Configuration settings** tab, scroll down and expand **Microsoft Defender Antivirus**.</span></span>

6. <span data-ttu-id="39982-384">[ **望ましくない可能性のあるアプリケーションを検出する] を** **[監査**] に設定し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-384">Set **Detect potentially unwanted applications** to **Audit**, and then choose **Next**.</span></span> <span data-ttu-id="39982-385">(PUA 保護をオフにできますが、監査モードを使用すると、検出を確認できます)。</span><span class="sxs-lookup"><span data-stu-id="39982-385">(You can turn off PUA protection, but by using audit mode, you will be able to see detections.)</span></span>

7. <span data-ttu-id="39982-386">[割 **り当て]** タブで、ポリシーを適用するユーザーとグループを指定し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-386">On the **Assignments** tab, specify the users and groups to whom your policy should be applied, and then choose **Next**.</span></span> <span data-ttu-id="39982-387">(割り当てのヘルプが必要な場合は [、「Assign user and device profiles in Microsoft Intune 」を参照](/mem/intune/configuration/device-profile-assign)してください。</span><span class="sxs-lookup"><span data-stu-id="39982-387">(If you need help with assignments, see [Assign user and device profiles in Microsoft Intune](/mem/intune/configuration/device-profile-assign).)</span></span>

8. <span data-ttu-id="39982-388">[適用 **ルール] タブ** で、ポリシーに含めるか除外する OS エディションまたはバージョンを指定します。</span><span class="sxs-lookup"><span data-stu-id="39982-388">On the **Applicability Rules** tab, specify the OS editions or versions to include or exclude from the policy.</span></span> <span data-ttu-id="39982-389">たとえば、Windows 10 の特定のエディションのすべてのデバイスに適用するポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="39982-389">For example, you can set the policy to be applied to all devices certain editions of Windows 10.</span></span> <span data-ttu-id="39982-390">**[次へ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="39982-390">Then choose **Next**.</span></span>

9. <span data-ttu-id="39982-391">[確認 **と作成] タブ** で、設定を確認し、[作成] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-391">On the **Review + create** tab, review your settings, and, and then choose **Create**.</span></span>

### <a name="automated-investigation-and-remediation"></a><span data-ttu-id="39982-392">調査と修復の自動化</span><span class="sxs-lookup"><span data-stu-id="39982-392">Automated investigation and remediation</span></span>

<span data-ttu-id="39982-393">[自動調査と修復](automated-investigations.md) (AIR) 機能は、アラートを調べ、侵害を解決するために直ちに対応するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="39982-393">[Automated investigation and remediation](automated-investigations.md) (AIR) capabilities are designed to examine alerts and take immediate action to resolve breaches.</span></span> <span data-ttu-id="39982-394">アラートがトリガーされ、自動調査が実行されると、調査された証拠ごとに評決が生成されます。</span><span class="sxs-lookup"><span data-stu-id="39982-394">As alerts are triggered, and an automated investigation runs, a verdict is generated for each piece of evidence investigated.</span></span> <span data-ttu-id="39982-395">評決には、悪意のある *、疑わしい、* または検出 *された脅威がない可能性があります*。 </span><span class="sxs-lookup"><span data-stu-id="39982-395">Verdicts can be *Malicious*, *Suspicious*, or *No threats found*.</span></span> 

<span data-ttu-id="39982-396">組織およびその他の [セキュリティ](/microsoft-365/security/defender-endpoint/automation-levels) 設定のオートメーション セットのレベルに応じて、悪意のあるまたは疑わしいと見なされるアーティファクトに対して修復 *アクションが* 実行 *されます*。</span><span class="sxs-lookup"><span data-stu-id="39982-396">Depending on the [level of automation](/microsoft-365/security/defender-endpoint/automation-levels) set for your organization and other security settings, remediation actions are taken on artifacts that are considered to be *Malicious* or *Suspicious*.</span></span> <span data-ttu-id="39982-397">修復アクションが自動的に実行される場合があります。それ以外の場合、修復アクションは手動で実行するか、セキュリティ運用チームの承認を得た場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="39982-397">In some cases, remediation actions occur automatically; in other cases, remediation actions are taken manually or only upon approval by your security operations team.</span></span> 

- <span data-ttu-id="39982-398">[オートメーション レベルについて詳しくは、次の情報を参照してください](/microsoft-365/security/defender-endpoint/automation-levels)。それから</span><span class="sxs-lookup"><span data-stu-id="39982-398">[Learn more about automation levels](/microsoft-365/security/defender-endpoint/automation-levels); and then</span></span> 
- <span data-ttu-id="39982-399">[Defender for Endpoint で AIR 機能を構成します](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation)。</span><span class="sxs-lookup"><span data-stu-id="39982-399">[Configure AIR capabilities in Defender for Endpoint](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="39982-400">自動調査と *修復には、* 完全自動化を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="39982-400">We recommend using *Full automation* for automated investigation and remediation.</span></span> <span data-ttu-id="39982-401">誤検知のため、これらの機能をオフにしない。</span><span class="sxs-lookup"><span data-stu-id="39982-401">Don't turn these capabilities off because of a false positive.</span></span> <span data-ttu-id="39982-402">代わりに [、"許可"](#indicators-for-microsoft-defender-for-endpoint)インジケーターを使用して例外を定義し、自動的に適切なアクションを実行するために自動調査と修復を設定します。</span><span class="sxs-lookup"><span data-stu-id="39982-402">Instead, use ["allow" indicators to define exceptions](#indicators-for-microsoft-defender-for-endpoint), and keep automated investigation and remediation set to take appropriate actions automatically.</span></span> <span data-ttu-id="39982-403">この [ガイダンスに従って](automation-levels.md#levels-of-automation) 、セキュリティ運用チームが処理する必要があるアラートの数を減らすのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39982-403">Following [this guidance](automation-levels.md#levels-of-automation) helps reduce the number of alerts your security operations team must handle.</span></span> 

## <a name="still-need-help"></a><span data-ttu-id="39982-404">さらにサポートが必要な場合</span><span class="sxs-lookup"><span data-stu-id="39982-404">Still need help?</span></span>

<span data-ttu-id="39982-405">この記事のすべての手順を実行し、引き続きヘルプが必要な場合は、テクニカル サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="39982-405">If you have worked through all the steps in this article and still need help, contact technical support.</span></span>

1. <span data-ttu-id="39982-406">Microsoft Defender セキュリティ センター ( ) に移動 [https://securitycenter.windows.com](https://securitycenter.windows.com) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="39982-406">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)) and sign in.</span></span>

2. <span data-ttu-id="39982-407">右上隅で、疑問符 (**?**) を選択し、[Microsoft サポート] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="39982-407">In the upper right corner, select the question mark (**?**), and then select **Microsoft support**.</span></span>

3. <span data-ttu-id="39982-408">[サポート **アシスタント] ウィンドウ** で、問題について説明し、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="39982-408">In the **Support Assistant** window, describe your issue, and then send your message.</span></span> <span data-ttu-id="39982-409">そこから、サービス要求を開きます。</span><span class="sxs-lookup"><span data-stu-id="39982-409">From there, you can open a service request.</span></span>  

## <a name="see-also"></a><span data-ttu-id="39982-410">関連項目</span><span class="sxs-lookup"><span data-stu-id="39982-410">See also</span></span>

[<span data-ttu-id="39982-411">エンドポイント用 Microsoft Defender の管理</span><span class="sxs-lookup"><span data-stu-id="39982-411">Manage Microsoft Defender for Endpoint</span></span>](manage-atp-post-migration.md)

[<span data-ttu-id="39982-412">Microsoft Defender セキュリティ センターの概要</span><span class="sxs-lookup"><span data-stu-id="39982-412">Overview of Microsoft Defender Security Center</span></span>](/microsoft-365/security/defender-endpoint/use) 
