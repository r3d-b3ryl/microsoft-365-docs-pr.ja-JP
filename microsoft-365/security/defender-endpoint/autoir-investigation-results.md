---
title: 自動調査の詳細と結果を表示する
description: 自動調査の結果と主な検出事項は、調査の実行中および実行後に表示できます。
keywords: 自動化、調査、結果、分析、詳細、修復、autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 8ecf39090d368427c103c7ec78e22bc13f7c339f
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591770"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a><span data-ttu-id="dce19-104">自動調査の詳細と結果を表示する</span><span class="sxs-lookup"><span data-stu-id="dce19-104">View the details and results of an automated investigation</span></span>

<span data-ttu-id="dce19-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="dce19-105">**Applies to:**</span></span>
- <span data-ttu-id="dce19-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dce19-106">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="dce19-107">Microsoft Defender for Endpoint[](automated-investigations.md)では、自動調査が実行されると、その調査に関する詳細は、自動調査プロセスの間と後の両方で利用できます。</span><span class="sxs-lookup"><span data-stu-id="dce19-107">With Microsoft Defender for Endpoint, when an [automated investigation](automated-investigations.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="dce19-108">必要なアクセス許可を持っている場合は、調査の詳細ビューでこれらの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="dce19-108">If you have the necessary permissions, you can view those details in an investigation details view.</span></span> <span data-ttu-id="dce19-109">調査の詳細ビューでは最新の状態が表示され、保留中のアクションを承認する機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="dce19-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

## <a name="new-unified-investigation-page"></a><span data-ttu-id="dce19-110">(NEW!)統合された調査ページ</span><span class="sxs-lookup"><span data-stu-id="dce19-110">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="dce19-111">調査ページが最近更新され、デバイス、電子メール、およびコラボレーション コンテンツ全体の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dce19-111">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="dce19-112">新しい統合された調査ページでは、共通言語が定義され [、Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)  および Microsoft Defender for Office 365 全体で自動調査 [を行う一元的なエクスペリエンスが](/microsoft-365/security/office-365-security/office-365-atp)提供されます。</span><span class="sxs-lookup"><span data-stu-id="dce19-112">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)  and [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp).</span></span> 

> [!TIP]
> <span data-ttu-id="dce19-113">変更の詳細については [、「(NEW!) 」を参照してください。統合された調査ページ](/microsoft-365/security/mtp/mtp-autoir-results)。</span><span class="sxs-lookup"><span data-stu-id="dce19-113">To learn more about what's changing, see [(NEW!) Unified investigation page](/microsoft-365/security/mtp/mtp-autoir-results).</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="dce19-114">調査の詳細ビューを開く</span><span class="sxs-lookup"><span data-stu-id="dce19-114">Open the investigation details view</span></span>

<span data-ttu-id="dce19-115">調査の詳細ビューを開くには、次のいずれかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="dce19-115">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="dce19-116">アクション センターでアイテムを選択する</span><span class="sxs-lookup"><span data-stu-id="dce19-116">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="dce19-117">インシデントの詳細ページから調査を選択する</span><span class="sxs-lookup"><span data-stu-id="dce19-117">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="dce19-118">アクション センターでアイテムを選択する</span><span class="sxs-lookup"><span data-stu-id="dce19-118">Select an item in the Action center</span></span>

<span data-ttu-id="dce19-119">改善された[アクション センターでは](auto-investigation-action-center.md)、デバイス[](manage-auto-investigation.md#remediation-actions)全体の修復アクション、電子メール、コラボレーション & ID がまとめされます。</span><span class="sxs-lookup"><span data-stu-id="dce19-119">The improved [Action center](auto-investigation-action-center.md) brings together [remediation actions](manage-auto-investigation.md#remediation-actions) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="dce19-120">リストされているアクションには、自動的または手動で実行された修復アクションが含まれます。</span><span class="sxs-lookup"><span data-stu-id="dce19-120">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="dce19-121">アクション センターでは、承認を待っているアクションと、既に承認または完了したアクションを表示できます。</span><span class="sxs-lookup"><span data-stu-id="dce19-121">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="dce19-122">調査ページなどの詳細に移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="dce19-122">You can also navigate to more details, such as an investigation page.</span></span>

1. <span data-ttu-id="dce19-123">[https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="dce19-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="dce19-124">ナビゲーション ウィンドウで、[**アクション センター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dce19-124">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="dce19-125">[**保留中**] タブまたは [**履歴**] タブのいずれかでアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="dce19-125">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="dce19-126">そのフライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="dce19-126">Its flyout pane opens.</span></span>
4. <span data-ttu-id="dce19-127">フライアウト ウィンドウで情報を確認し、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="dce19-127">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="dce19-128">[ **調査ページを開く]** を選択して、調査の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="dce19-128">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="dce19-129">[承認 **] を** 選択して保留中のアクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="dce19-129">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="dce19-130">保留中 **のアクション** が実行されるのを防ぐには、[拒否] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dce19-130">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="dce19-131">[Go **hunt] を** 選択して高度な [ハンティングに入る](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="dce19-131">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="dce19-132">インシデントの詳細ページから調査を開く</span><span class="sxs-lookup"><span data-stu-id="dce19-132">Open an investigation from an incident details page</span></span>

<span data-ttu-id="dce19-133">インシデントの詳細ページを使用して、インシデントに関する詳細情報を表示します。これには、影響を受けたデバイス、ユーザー アカウント、またはメールボックスに関する情報がトリガーされた警告が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dce19-133">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="dce19-134">[https://security.microsoft.com](https://security.microsoft.com) にアクセスし、サインインします。</span><span class="sxs-lookup"><span data-stu-id="dce19-134">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="dce19-135">ナビゲーション ウィンドウで、[インシデント] を選択 **し、[インシデント&通知**  >  **します**。</span><span class="sxs-lookup"><span data-stu-id="dce19-135">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 
3. <span data-ttu-id="dce19-136">リストでアイテムを選択し、[インシデント ページを開 **く] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dce19-136">Select an item in the list, and then choose **Open incident page**.</span></span>
4. <span data-ttu-id="dce19-137">[調査 **] タブを** 選択し、一覧で調査を選択します。</span><span class="sxs-lookup"><span data-stu-id="dce19-137">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="dce19-138">そのフライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="dce19-138">Its flyout pane opens.</span></span>
5. <span data-ttu-id="dce19-139">[調査 **ページを開く] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="dce19-139">Select **Open investigation page**.</span></span> 

## <a name="investigation-details"></a><span data-ttu-id="dce19-140">調査の詳細</span><span class="sxs-lookup"><span data-stu-id="dce19-140">Investigation details</span></span>

<span data-ttu-id="dce19-141">調査の詳細ビューを使用して、調査に関連する過去、現在、保留中のアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="dce19-141">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="dce19-142">調査の詳細ビューの画像は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dce19-142">The investigation details view resembles the following image:</span></span>

<span data-ttu-id="dce19-143">調査の詳細ビューでは、次の表で説明する [**Investigation graph (調査のグラフ)**]、[**Alerts (警告)**]、[**Device (デバイス)**]、[**Identities (ID)**]、[**Key findings (主な検出事項)**]、[**Entities (エンティティ)**]、[**Log (ログ)**]、[**Pending actions (保留中のアクション)**] の各タブに情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dce19-143">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="dce19-144">調査の詳細ページに表示される特定のタブは、サブスクリプションに含まれる内容によって異なります。</span><span class="sxs-lookup"><span data-stu-id="dce19-144">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="dce19-145">たとえば、サブスクリプションに Microsoft Defender for Office 365 プラン 2 が含まれる場合、[メールボックス] タブ **は表示** されません。</span><span class="sxs-lookup"><span data-stu-id="dce19-145">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="dce19-146">タブ</span><span class="sxs-lookup"><span data-stu-id="dce19-146">Tab</span></span> | <span data-ttu-id="dce19-147">説明</span><span class="sxs-lookup"><span data-stu-id="dce19-147">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="dce19-148">**Investigation graph (調査グラフ)**</span><span class="sxs-lookup"><span data-stu-id="dce19-148">**Investigation graph**</span></span>   | <span data-ttu-id="dce19-149">調査を視覚的に表します。</span><span class="sxs-lookup"><span data-stu-id="dce19-149">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="dce19-150">エンティティと検出された脅威のほか、警告、承認を待っているアクションがあるかどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="dce19-150">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="dce19-151">グラフ上のアイテムを選択すると、詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="dce19-151">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="dce19-152">たとえば、[証拠]**アイコンを** 選択すると、[証拠]タブに移動し、検出されたエンティティとその評決を確認できます。</span><span class="sxs-lookup"><span data-stu-id="dce19-152">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="dce19-153">**Alerts**</span><span class="sxs-lookup"><span data-stu-id="dce19-153">**Alerts**</span></span>    | <span data-ttu-id="dce19-154">調査に関連する警告を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="dce19-154">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="dce19-155">アラートは、ユーザーのデバイス、Office アプリ、Cloud App Security、その他の Microsoft 365 Defender 機能の脅威保護機能から発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dce19-155">Alerts can come from threat protection features on a user's device, in Office apps, Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="dce19-156">**デバイス**</span><span class="sxs-lookup"><span data-stu-id="dce19-156">**Devices**</span></span> | <span data-ttu-id="dce19-157">調査に含まれるデバイスとその修復レベルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="dce19-157">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="dce19-158">(修復レベルは、デバイス グループ [のオートメーション レベルに対応します](automation-levels.md)。)</span><span class="sxs-lookup"><span data-stu-id="dce19-158">(Remediation levels correspond to the [automation level for device groups](automation-levels.md).)</span></span> |
| <span data-ttu-id="dce19-159">**メールボックス**</span><span class="sxs-lookup"><span data-stu-id="dce19-159">**Mailboxes**</span></span> |<span data-ttu-id="dce19-160">検出された脅威の影響を受けたメールボックスを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="dce19-160">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="dce19-161">**Users**</span><span class="sxs-lookup"><span data-stu-id="dce19-161">**Users**</span></span>  | <span data-ttu-id="dce19-162">検出された脅威の影響を受けたユーザー アカウントを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="dce19-162">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="dce19-163">**証拠**</span><span class="sxs-lookup"><span data-stu-id="dce19-163">**Evidence**</span></span> | <span data-ttu-id="dce19-164">アラート/調査によって発生した証拠の一部を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="dce19-164">Lists pieces of evidence raised by alerts/investigations.</span></span> <span data-ttu-id="dce19-165">評決 (悪意のある、疑 *わしい、* または脅威が見 *つからない*) と修復の状態が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dce19-165">Includes verdicts (*Malicious*, *Suspicious*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="dce19-166">**Entities**</span><span class="sxs-lookup"><span data-stu-id="dce19-166">**Entities**</span></span>  | <span data-ttu-id="dce19-167">各エンティティの種類 (悪意のある、疑わしい、または脅威が見つからない)の評決を含む、分析された各エンティティの詳細 *を提供します*。</span><span class="sxs-lookup"><span data-stu-id="dce19-167">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="dce19-168">**Log**</span><span class="sxs-lookup"><span data-stu-id="dce19-168">**Log**</span></span>    | <span data-ttu-id="dce19-169">アラートがトリガーされた後に行ったすべての調査アクションの時系列的で詳細なビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="dce19-169">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="dce19-170">**Pending actions (保留中のアクション)**</span><span class="sxs-lookup"><span data-stu-id="dce19-170">**Pending actions**</span></span> | <span data-ttu-id="dce19-171">続けるには承認を必要とするアイテムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="dce19-171">Lists items that require approval to proceed.</span></span> <span data-ttu-id="dce19-172">アクション センター ( ) に移動 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) して、保留中のアクションを承認します。</span><span class="sxs-lookup"><span data-stu-id="dce19-172">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="see-also"></a><span data-ttu-id="dce19-173">関連項目</span><span class="sxs-lookup"><span data-stu-id="dce19-173">See also</span></span>

- [<span data-ttu-id="dce19-174">自動調査後の修復アクションの確認</span><span class="sxs-lookup"><span data-stu-id="dce19-174">Review remediation actions following an automated investigation</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="dce19-175">Microsoft Defender for Endpoint Incidents キューの表示と整理</span><span class="sxs-lookup"><span data-stu-id="dce19-175">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>](view-incidents-queue.md)