---
title: 脅威と脆弱性の管理による脆弱性の修復
description: セキュリティの推奨事項によって検出されたセキュリティの弱点を修復し、必要に応じて脅威と脆弱性の管理で例外を作成します。
keywords: microsoft Defender atp tvm 修復、mdatp tvm、脅威と脆弱性管理、脅威 & 脆弱性管理、脅威 & 脆弱性管理修復、tvm 修復 intune、tvm 修復 sccm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0a0f70d81c3060f14f917cac49851af2e9dae210
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068684"
---
# <a name="remediate-vulnerabilities-with-threat-and-vulnerability-management"></a><span data-ttu-id="239ce-104">脅威と脆弱性の管理による脆弱性の修復</span><span class="sxs-lookup"><span data-stu-id="239ce-104">Remediate vulnerabilities with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="239ce-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="239ce-105">**Applies to:**</span></span>
- [<span data-ttu-id="239ce-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="239ce-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="239ce-107">脅威と脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="239ce-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="239ce-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="239ce-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="239ce-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="239ce-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="239ce-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="239ce-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="request-remediation"></a><span data-ttu-id="239ce-111">修復の要求</span><span class="sxs-lookup"><span data-stu-id="239ce-111">Request remediation</span></span>

<span data-ttu-id="239ce-112">Microsoft Defender for Endpoint の脅威と脆弱性管理機能は、修復要求ワークフローを通じてセキュリティ管理者と IT 管理者の間のギャップを埋め合わせています。</span><span class="sxs-lookup"><span data-stu-id="239ce-112">The threat and vulnerability management capability in Microsoft Defender for Endpoint bridges the gap between Security and IT administrators through the remediation request workflow.</span></span> <span data-ttu-id="239ce-113">IT 管理者に対してセキュリティの推奨事項ページから Intune への脆弱性の修復を要求できるセキュリティ管理者。</span><span class="sxs-lookup"><span data-stu-id="239ce-113">Security admins like you can request for the IT Administrator to remediate a vulnerability from the **Security recommendation** pages to Intune.</span></span>

### <a name="enable-microsoft-intune-connection"></a><span data-ttu-id="239ce-114">Microsoft Intune 接続を有効にする</span><span class="sxs-lookup"><span data-stu-id="239ce-114">Enable Microsoft Intune connection</span></span>

<span data-ttu-id="239ce-115">この機能を使用するには、Microsoft Intune 接続を有効にします。</span><span class="sxs-lookup"><span data-stu-id="239ce-115">To use this capability, enable your Microsoft Intune connections.</span></span> <span data-ttu-id="239ce-116">Microsoft Defender セキュリティ センターで、[設定] [全般高度な  >  **機能]**  >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="239ce-116">In the Microsoft Defender Security Center, navigate to **Settings** > **General** > **Advanced features**.</span></span> <span data-ttu-id="239ce-117">下にスクロールして **、Microsoft Intune 接続を探します**。</span><span class="sxs-lookup"><span data-stu-id="239ce-117">Scroll down and look for **Microsoft Intune connection**.</span></span> <span data-ttu-id="239ce-118">既定では、トグルはオフになっています。</span><span class="sxs-lookup"><span data-stu-id="239ce-118">By default, the toggle is turned off.</span></span> <span data-ttu-id="239ce-119">Microsoft **Intune 接続トグルをオン\*\*\*\*にします**。</span><span class="sxs-lookup"><span data-stu-id="239ce-119">Turn your **Microsoft Intune connection** toggle **On**.</span></span>

<span data-ttu-id="239ce-120">**注**: Intune 接続が有効になっている場合は、修復要求を作成するときに Intune セキュリティ タスクを作成するオプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="239ce-120">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="239ce-121">接続が設定されていない場合、このオプションは表示されません。</span><span class="sxs-lookup"><span data-stu-id="239ce-121">This option does not appear if the connection is not set.</span></span>

<span data-ttu-id="239ce-122">詳細 [については、「Intune を使用して Microsoft Defender for Endpoint](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) で特定された脆弱性を修復する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="239ce-122">See [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) for details.</span></span>

### <a name="remediation-request-steps"></a><span data-ttu-id="239ce-123">修復要求の手順</span><span class="sxs-lookup"><span data-stu-id="239ce-123">Remediation request steps</span></span>

1. <span data-ttu-id="239ce-124">Microsoft Defender セキュリティ センターの [脅威と脆弱性管理] ナビゲーション メニューに移動し、[セキュリティの推奨事項] [**を選択します**](tvm-security-recommendation.md)。</span><span class="sxs-lookup"><span data-stu-id="239ce-124">Go to the threat and vulnerability management navigation menu in the Microsoft Defender Security Center, and select [**Security recommendations**](tvm-security-recommendation.md).</span></span>

2. <span data-ttu-id="239ce-125">修復を要求するセキュリティ推奨事項を選択し、[修復オプション] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="239ce-125">Select a security recommendation you would like to request remediation for, and then select **Remediation options**.</span></span>

3. <span data-ttu-id="239ce-126">修復を要求する項目、該当するデバイス グループ、優先度、期限、オプションのメモなど、フォームに入力します。</span><span class="sxs-lookup"><span data-stu-id="239ce-126">Fill out the form, including what you are requesting remediation for, applicable device groups, priority, due date, and optional notes.</span></span>
    1. <span data-ttu-id="239ce-127">[注意が必要] 修復オプションを選択した場合、特定のアクションが実行されないので、期日を選択できません。</span><span class="sxs-lookup"><span data-stu-id="239ce-127">If you choose the "attention required" remediation option, selecting a due date will not be available since there is no specific action.</span></span>

4. <span data-ttu-id="239ce-128">[要求 **の送信] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="239ce-128">Select **Submit request**.</span></span> <span data-ttu-id="239ce-129">修復要求を送信すると、脅威と脆弱性の管理内に修復アクティビティ アイテムが作成され、この推奨事項の修復の進行状況を監視するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="239ce-129">Submitting a remediation request creates a remediation activity item within threat and vulnerability management, which can be used for monitoring the remediation progress for this recommendation.</span></span> <span data-ttu-id="239ce-130">これにより、修復がトリガーされないか、デバイスに変更が適用されません。</span><span class="sxs-lookup"><span data-stu-id="239ce-130">This will not trigger a remediation or apply any changes to devices.</span></span>

5. <span data-ttu-id="239ce-131">IT 管理者に新しい要求について通知し、Intune にログインして要求を承認または拒否し、パッケージの展開を開始します。</span><span class="sxs-lookup"><span data-stu-id="239ce-131">Notify your IT Administrator about the new request and have them log into Intune to approve or reject the request and start a package deployment.</span></span>

6. <span data-ttu-id="239ce-132">[修復] [**ページに**](tvm-remediation.md) 移動して、修復要求の状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="239ce-132">Go to the [**Remediation**](tvm-remediation.md) page to view the status of your remediation request.</span></span>

<span data-ttu-id="239ce-133">Intune でチケットがどのように表示されるのか確認する場合は、「Use Intune to [remediate vulnerabilited by Microsoft Defender for Endpoint」](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="239ce-133">If you want to check how the ticket shows up in Intune, see [Use Intune to remediate vulnerabilities identified by Microsoft Defender for Endpoint](https://docs.microsoft.com/intune/atp-manage-vulnerabilities) for details.</span></span>

>[!NOTE]
><span data-ttu-id="239ce-134">要求で 10,000 台を超えるデバイスの修復が必要な場合は、Intune に修復のために 10,000 台のデバイスのみを送信できます。</span><span class="sxs-lookup"><span data-stu-id="239ce-134">If your request involves remediating more than 10,000 devices, we can only send 10,000 devices for remediation to Intune.</span></span>

<span data-ttu-id="239ce-135">組織のサイバーセキュリティの弱点が特定され、アクション可能なセキュリティ推奨事項にマップされた後、[](tvm-security-recommendation.md)セキュリティ タスクの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="239ce-135">After your organization's cybersecurity weaknesses are identified and mapped to actionable [security recommendations](tvm-security-recommendation.md), start creating security tasks.</span></span> <span data-ttu-id="239ce-136">修復チケットが作成される Microsoft Intune との統合を通じてタスクを作成できます。</span><span class="sxs-lookup"><span data-stu-id="239ce-136">You can create tasks through the integration with Microsoft Intune where remediation tickets are created.</span></span>

<span data-ttu-id="239ce-137">セキュリティに関する推奨事項を修復することで、組織の脆弱性による露出を低くし、セキュリティ構成を強化します。</span><span class="sxs-lookup"><span data-stu-id="239ce-137">Lower your organization's exposure from vulnerabilities and increase your security configuration by remediating the security recommendations.</span></span>

## <a name="view-your-remediation-activities"></a><span data-ttu-id="239ce-138">修復アクティビティの表示</span><span class="sxs-lookup"><span data-stu-id="239ce-138">View your remediation activities</span></span>

<span data-ttu-id="239ce-139">[セキュリティの推奨事項] ページから修復要求を送信すると、修復アクティビティが開始されます。</span><span class="sxs-lookup"><span data-stu-id="239ce-139">When you submit a remediation request from the Security recommendations page, it kicks-off a remediation activity.</span></span> <span data-ttu-id="239ce-140">脅威と脆弱性管理の修復ページで追跡できるセキュリティ タスクが作成され、修復チケットが Microsoft Intune に作成されます。</span><span class="sxs-lookup"><span data-stu-id="239ce-140">A security task is created that can be tracked in the threat and vulnerability management **Remediation** page, and a remediation ticket is created in Microsoft Intune.</span></span>

<span data-ttu-id="239ce-141">[注意が必要] 修復オプションを選択した場合は、監視できる実際のアクションが行われなかから、進行状況バー、チケットの状態、または期限はありません。</span><span class="sxs-lookup"><span data-stu-id="239ce-141">If you chose the "attention required" remediation option, there will be no progress bar, ticket status, or due date since there is no actual action we can monitor.</span></span>

<span data-ttu-id="239ce-142">[修復] ページに移動したら、表示する修復アクティビティを選択します。</span><span class="sxs-lookup"><span data-stu-id="239ce-142">Once you are in the Remediation page, select the remediation activity that you want to view.</span></span> <span data-ttu-id="239ce-143">修復手順を実行したり、進行状況を追跡したり、関連する推奨事項を表示したり、CSV にエクスポートしたり、完了としてマークすることができます。</span><span class="sxs-lookup"><span data-stu-id="239ce-143">You can follow the remediation steps, track progress, view the related recommendation, export to CSV, or mark as complete.</span></span>
<span data-ttu-id="239ce-144">![選択した修復アクティビティを含む [修復] ページの例と、そのアクティビティのフライアウトには、説明、IT サービスとデバイス管理ツール、およびデバイス修復の進行状況が一覧されます。](images/remediation_flyouteolsw.png)</span><span class="sxs-lookup"><span data-stu-id="239ce-144">![Example of the Remediation page, with a selected remediation activity, and that activity's flyout listing the description, IT service and device management tools, and device remediation progress.](images/remediation_flyouteolsw.png)</span></span>

>[!NOTE]
> <span data-ttu-id="239ce-145">完了した修復アクティビティには 180 日間の保持期間があります。</span><span class="sxs-lookup"><span data-stu-id="239ce-145">There is a 180 day retention period for completed remediation activities.</span></span> <span data-ttu-id="239ce-146">修復ページのパフォーマンスを最適に維持するために、修復アクティビティは完了から 6 か月後に削除されます。</span><span class="sxs-lookup"><span data-stu-id="239ce-146">To keep the Remediation page performing optimally, the remediation activity will be removed 6 months after its completion.</span></span>

### <a name="completed-by-column"></a><span data-ttu-id="239ce-147">列で完了</span><span class="sxs-lookup"><span data-stu-id="239ce-147">Completed by column</span></span>

<span data-ttu-id="239ce-148">[修復] ページの [完了者] 列を使用して、修復アクティビティを閉じたユーザーを追跡します。</span><span class="sxs-lookup"><span data-stu-id="239ce-148">Track who closed the remediation activity with the "Completed by" column on the Remediation page.</span></span>

- <span data-ttu-id="239ce-149">**電子メール アドレス**: タスクを手動で完了したユーザーのメール</span><span class="sxs-lookup"><span data-stu-id="239ce-149">**Email address**: The email of the person who manually completed the task</span></span>
- <span data-ttu-id="239ce-150">**システム確認**: タスクが自動的に完了しました (すべてのデバイスが修復されました)</span><span class="sxs-lookup"><span data-stu-id="239ce-150">**System confirmation**: The task was automatically completed (all devices remediated)</span></span>
- <span data-ttu-id="239ce-151">**N/A**: この古いタスクがどのように完了したのか分からないので、情報は利用できません</span><span class="sxs-lookup"><span data-stu-id="239ce-151">**N/A**: Information is not available because we don't know how this older task was completed</span></span>

![2 行の列によって作成され、完了します。](images/tvm-completed-by.png)

### <a name="top-remediation-activities-in-the-dashboard"></a><span data-ttu-id="239ce-154">ダッシュボードの上位修復アクティビティ</span><span class="sxs-lookup"><span data-stu-id="239ce-154">Top remediation activities in the dashboard</span></span>

<span data-ttu-id="239ce-155">脅威 **と脆弱性管理ダッシュボードで** 上位 [の修復アクティビティを表示します](tvm-dashboard-insights.md)。</span><span class="sxs-lookup"><span data-stu-id="239ce-155">View **Top remediation activities** in the [threat and vulnerability management dashboard](tvm-dashboard-insights.md).</span></span> <span data-ttu-id="239ce-156">[修復] ページに移動するエントリを **選択** します。</span><span class="sxs-lookup"><span data-stu-id="239ce-156">Select any of the entries to go to the **Remediation** page.</span></span> <span data-ttu-id="239ce-157">IT 管理者チームがタスクを修復した後、修復アクティビティを完了としてマークできます。</span><span class="sxs-lookup"><span data-stu-id="239ce-157">You can mark the remediation activity as completed after the IT admin team remediates the task.</span></span>

![セキュリティの推奨事項から生成された上位のアクティビティを一覧表示するテーブルを持つトップ修復アクティビティ カードの例。](images/tvm-remediation-activities-card.png)

## <a name="related-articles"></a><span data-ttu-id="239ce-159">関連記事</span><span class="sxs-lookup"><span data-stu-id="239ce-159">Related articles</span></span>

- [<span data-ttu-id="239ce-160">脅威と脆弱性の管理の概要</span><span class="sxs-lookup"><span data-stu-id="239ce-160">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="239ce-161">ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="239ce-161">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="239ce-162">セキュリティ上の推奨事項</span><span class="sxs-lookup"><span data-stu-id="239ce-162">Security recommendations</span></span>](tvm-security-recommendation.md)