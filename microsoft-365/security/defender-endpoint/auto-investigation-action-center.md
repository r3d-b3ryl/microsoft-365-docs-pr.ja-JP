---
title: アクション センターにアクセスして修復アクションを確認する
description: アクション センターを使用して、自動調査後の詳細と結果を表示する
keywords: action, center, autoir, 自動, 調査, 応答, 修復
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: f8dd48364f60da789ac95638018245cf46434822
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197639"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a><span data-ttu-id="ebb4a-104">アクション センターにアクセスして修復アクションを確認する</span><span class="sxs-lookup"><span data-stu-id="ebb4a-104">Visit the Action center to see remediation actions</span></span>

<span data-ttu-id="ebb4a-105">自動調査中および自動調査後に、脅威検出に対する修復アクションが識別されます。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-105">During and after an automated investigation, remediation actions for threat detections are identified.</span></span> <span data-ttu-id="ebb4a-106">特定の脅威と [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) の組織の構成方法に応じて、一部の修復アクションが自動的に実行され、承認が必要な修復アクションもあります。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-106">Depending on the particular threat and how [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) is configured for your organization, some remediation actions are taken automatically, and others require approval.</span></span> <span data-ttu-id="ebb4a-107">組織のセキュリティ運用チームの一員である場合は、アクション センターで保留中の修復アクションと完了 [](manage-auto-investigation.md#remediation-actions)済み修復アクションを **表示できます**。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-107">If you're part of your organization's security operations team, you can view pending and completed [remediation actions](manage-auto-investigation.md#remediation-actions) in the **Action center**.</span></span> 


<span data-ttu-id="ebb4a-108">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ebb4a-108">**Applies to:**</span></span>
- [<span data-ttu-id="ebb4a-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ebb4a-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ebb4a-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ebb4a-110">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a><span data-ttu-id="ebb4a-111">(NEW!)統合アクション センター</span><span class="sxs-lookup"><span data-stu-id="ebb4a-111">(NEW!) A unified Action center</span></span>


<span data-ttu-id="ebb4a-112">新しい統合アクション センター ( )を発表します [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-112">We are pleased to announce a new, unified Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center))!</span></span>

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Microsoft 365 セキュリティ センターのアクション センター":::

<span data-ttu-id="ebb4a-114">次の表は、新しい統合アクション センターと前のアクション センターを比較します。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-114">The following table compares the new, unified Action center to the previous Action center.</span></span>

|<span data-ttu-id="ebb4a-115">統合された新しいアクション センター</span><span class="sxs-lookup"><span data-stu-id="ebb4a-115">The new, unified Action center</span></span>  |<span data-ttu-id="ebb4a-116">前のアクション センター</span><span class="sxs-lookup"><span data-stu-id="ebb4a-116">The previous Action center</span></span>  |
|---------|---------|
|<span data-ttu-id="ebb4a-117">デバイスと電子メールの保留中のアクションと完了したアクションを 1 つの場所に一覧表示する</span><span class="sxs-lookup"><span data-stu-id="ebb4a-117">Lists pending and completed actions for devices and email in one location</span></span> <br/><span data-ttu-id="ebb4a-118">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) plus Microsoft Defender for Office [365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp))</span><span class="sxs-lookup"><span data-stu-id="ebb4a-118">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) plus [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp))</span></span>|<span data-ttu-id="ebb4a-119">デバイスの保留中のアクションと完了したアクションの一覧</span><span class="sxs-lookup"><span data-stu-id="ebb4a-119">Lists pending and completed actions for devices</span></span> <br/> <span data-ttu-id="ebb4a-120">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) のみ)</span><span class="sxs-lookup"><span data-stu-id="ebb4a-120">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) only)</span></span>   |
|<span data-ttu-id="ebb4a-121">場所は次の場所です。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-121">Is located at:</span></span><br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |<span data-ttu-id="ebb4a-122">場所は次の場所です。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-122">Is located at:</span></span><br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| <span data-ttu-id="ebb4a-123">Microsoft 365 セキュリティ センターで、[アクション センター] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-123">In the Microsoft 365 security center, choose **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Microsoft 365 セキュリティ センターのアクション センターへの移動"::: | <span data-ttu-id="ebb4a-125">Microsoft Defender セキュリティ センターで、[自動調査 **] アクション センター**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-125">In the Microsoft Defender Security Center, choose **Automated investigations** > **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Microsoft Defender セキュリティ センターからアクション センターに移動する":::  |

<span data-ttu-id="ebb4a-127">統合アクション センターでは、365 用の Defender for Endpoint と Defender 全体で修復Officeされます。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-127">The unified Action center brings together remediation actions across Defender for Endpoint and Defender for Office 365.</span></span> <span data-ttu-id="ebb4a-128">すべての修復アクションの共通言語を定義し、統合された調査エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-128">It defines a common language for all remediation actions, and provides a unified investigation experience.</span></span> 

<span data-ttu-id="ebb4a-129">適切なアクセス許可と次のサブスクリプションの 1 つ以上がある場合は、統合アクション センターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-129">You can use the unified Action center if you have appropriate permissions and one or more of the following subscriptions:</span></span>
- [<span data-ttu-id="ebb4a-130">Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ebb4a-130">Defender for Endpoint</span></span>](microsoft-defender-endpoint.md)
- [<span data-ttu-id="ebb4a-131">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ebb4a-131">Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="ebb4a-132">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ebb4a-132">Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> <span data-ttu-id="ebb4a-133">詳細については、「要件」 [を参照してください](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-133">To learn more, see [Requirements](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).</span></span>

## <a name="using-the-action-center"></a><span data-ttu-id="ebb4a-134">アクション センターの使用</span><span class="sxs-lookup"><span data-stu-id="ebb4a-134">Using the Action center</span></span>

<span data-ttu-id="ebb4a-135">強化された Microsoft 365 セキュリティ センターで統合アクション センターにアクセスするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-135">To get to the unified Action center in the improved Microsoft 365 security center:</span></span>
1. <span data-ttu-id="ebb4a-136">Microsoft 365 セキュリティ センター ( ) に移動し [https://security.microsoft.com](https://security.microsoft.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-136">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="ebb4a-137">ナビゲーション ウィンドウで、[アクション センター] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-137">In the navigation pane, select **Action center**.</span></span> 

<span data-ttu-id="ebb4a-138">アクション センターにアクセスすると、[保留中のアクション] と [履歴] **の 2 つのタブ** が **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-138">When you visit the Action center, you see two tabs: **Pending actions** and **History**.</span></span> <span data-ttu-id="ebb4a-139">次の表に、各タブに表示される内容の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-139">The following table summarizes what you'll see on each tab:</span></span>

|<span data-ttu-id="ebb4a-140">タブ</span><span class="sxs-lookup"><span data-stu-id="ebb4a-140">Tab</span></span>  |<span data-ttu-id="ebb4a-141">説明</span><span class="sxs-lookup"><span data-stu-id="ebb4a-141">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="ebb4a-142">**Pending**</span><span class="sxs-lookup"><span data-stu-id="ebb4a-142">**Pending**</span></span>     | <span data-ttu-id="ebb4a-143">注意が必要なアクションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-143">Displays a list of actions that require attention.</span></span> <span data-ttu-id="ebb4a-144">アクションを一度に 1 つ承認または拒否するか、同じ種類のアクション (検疫ファイルなど) がある場合は複数のアクション **を選択できます**。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-144">You can approve or reject actions one at a time, or select multiple actions if they have the same type of action (such as **Quarantine file**).</span></span> <br/><span data-ttu-id="ebb4a-145">**ヒント**: 保留中のアクションをできるだけ早く確認し、承認 (または拒否 [)](manage-auto-investigation.md) して、自動調査が正時に完了するようにします。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-145">**TIP**: Make sure to [review and approve (or reject) pending actions](manage-auto-investigation.md) as soon as possible so that your automated investigations can complete in a timely manner.</span></span> |
|<span data-ttu-id="ebb4a-146">**履歴**</span><span class="sxs-lookup"><span data-stu-id="ebb4a-146">**History**</span></span>     | <span data-ttu-id="ebb4a-147">次のようなアクションの監査ログとして機能します。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-147">Serves as an audit log for actions that were taken, such as:</span></span> <br/><span data-ttu-id="ebb4a-148">- 自動調査の結果として実行された修復アクション</span><span class="sxs-lookup"><span data-stu-id="ebb4a-148">- Remediation actions that were taken as a result of automated investigations</span></span> <br><span data-ttu-id="ebb4a-149">- セキュリティ運用チームによって承認された修復アクション</span><span class="sxs-lookup"><span data-stu-id="ebb4a-149">- Remediation actions that were approved by your security operations team</span></span>  <br/><span data-ttu-id="ebb4a-150">- Live Response セッション中に適用された、実行されたコマンドと修復アクション</span><span class="sxs-lookup"><span data-stu-id="ebb4a-150">- Commands that were run and remediation actions that were applied during Live Response sessions</span></span>  <br/><span data-ttu-id="ebb4a-151">- Microsoft Defender ウイルス対策の脅威保護機能によって実行された修復アクション</span><span class="sxs-lookup"><span data-stu-id="ebb4a-151">- Remediation actions that were taken by threat protection features in Microsoft Defender Antivirus</span></span>  <p><span data-ttu-id="ebb4a-152">特定のアクションを元に戻す方法を提供します (「完了した操作を元に戻[す」を参照)。](manage-auto-investigation.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="ebb4a-152">Provides a way to undo certain actions (see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions)).</span></span>       |

<span data-ttu-id="ebb4a-153">アクション センターでデータをカスタマイズ、並べ替え、フィルター処理、およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-153">You can customize, sort, filter, and export data in the Action center.</span></span>

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="アクション センターの列とフィルター":::

- <span data-ttu-id="ebb4a-155">列見出しを選択して、アイテムを昇順または降順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-155">Select a column heading to sort items in ascending or descending order.</span></span>
- <span data-ttu-id="ebb4a-156">期間フィルターを使用して、過去の日、週、30 日、または 6 か月のデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-156">Use the time period filter to view data for the past day, week, 30 days, or 6 months.</span></span>
- <span data-ttu-id="ebb4a-157">表示する列を選択します。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-157">Choose the columns that you want to view.</span></span>
- <span data-ttu-id="ebb4a-158">データの各ページに含めるアイテムの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-158">Specify how many items to include on each page of data.</span></span>
- <span data-ttu-id="ebb4a-159">フィルターを使用して、表示するアイテムを表示します。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-159">Use filters to view just the items you want to see.</span></span>
- <span data-ttu-id="ebb4a-160">[エクスポート **] を** 選択して、結果を .csv ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="ebb4a-160">Select **Export** to export results to a .csv file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="ebb4a-161">次の手順</span><span class="sxs-lookup"><span data-stu-id="ebb4a-161">Next steps</span></span>

- [<span data-ttu-id="ebb4a-162">修復アクションの表示と承認</span><span class="sxs-lookup"><span data-stu-id="ebb4a-162">View and approve remediation actions</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="ebb4a-163">対話型ガイドを参照してください。 Microsoft Defender for Endpoint を使用して脅威を調査して修復する</span><span class="sxs-lookup"><span data-stu-id="ebb4a-163">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a><span data-ttu-id="ebb4a-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="ebb4a-164">See also</span></span>

- [<span data-ttu-id="ebb4a-165">エンドポイント向け Microsoft Defender で誤検知/負に対処する</span><span class="sxs-lookup"><span data-stu-id="ebb4a-165">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
