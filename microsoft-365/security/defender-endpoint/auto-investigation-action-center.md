---
title: アクション センターにアクセスして修復アクションを確認する
description: アクション センターを使用して、自動調査後の詳細と結果を表示する
keywords: action, center, autoir, 自動, 調査, 応答, 修復
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
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
ms.openlocfilehash: cc806678bbb5ac19f7c4e035efb52b6ba7d1edb1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844912"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a><span data-ttu-id="daaad-104">アクション センターにアクセスして修復アクションを確認する</span><span class="sxs-lookup"><span data-stu-id="daaad-104">Visit the Action center to see remediation actions</span></span>

<span data-ttu-id="daaad-105">自動調査中および自動調査後に、脅威検出に対する修復アクションが識別されます。</span><span class="sxs-lookup"><span data-stu-id="daaad-105">During and after an automated investigation, remediation actions for threat detections are identified.</span></span> <span data-ttu-id="daaad-106">特定の脅威と [Microsoft Defender for Endpoint](/windows/security/threat-protection) の組織の構成方法に応じて、一部の修復アクションが自動的に実行され、承認が必要な修復アクションもあります。</span><span class="sxs-lookup"><span data-stu-id="daaad-106">Depending on the particular threat and how [Microsoft Defender for Endpoint](/windows/security/threat-protection) is configured for your organization, some remediation actions are taken automatically, and others require approval.</span></span> <span data-ttu-id="daaad-107">組織のセキュリティ運用チームの一員である場合は、アクション センターで保留中の修復アクションと完了 [](manage-auto-investigation.md#remediation-actions)済み修復アクションを **表示できます**。</span><span class="sxs-lookup"><span data-stu-id="daaad-107">If you're part of your organization's security operations team, you can view pending and completed [remediation actions](manage-auto-investigation.md#remediation-actions) in the **Action center**.</span></span> 


<span data-ttu-id="daaad-108">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="daaad-108">**Applies to:**</span></span>
- [<span data-ttu-id="daaad-109">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="daaad-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="daaad-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="daaad-110">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a><span data-ttu-id="daaad-111">(NEW!)統合アクション センター</span><span class="sxs-lookup"><span data-stu-id="daaad-111">(NEW!) A unified Action center</span></span>


<span data-ttu-id="daaad-112">新しい統合アクション センター ( )を発表します [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) 。</span><span class="sxs-lookup"><span data-stu-id="daaad-112">We are pleased to announce a new, unified Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center))!</span></span>

:::image type="content" source="images/mde-action-center-unified.png" alt-text="セキュリティ センター Microsoft 365センター":::

<span data-ttu-id="daaad-114">次の表は、新しい統合アクション センターと前のアクション センターを比較します。</span><span class="sxs-lookup"><span data-stu-id="daaad-114">The following table compares the new, unified Action center to the previous Action center.</span></span>

|<span data-ttu-id="daaad-115">統合された新しいアクション センター</span><span class="sxs-lookup"><span data-stu-id="daaad-115">The new, unified Action center</span></span>  |<span data-ttu-id="daaad-116">前のアクション センター</span><span class="sxs-lookup"><span data-stu-id="daaad-116">The previous Action center</span></span>  |
|---------|---------|
|<span data-ttu-id="daaad-117">デバイスと電子メールの保留中のアクションと完了したアクションを 1 つの場所に一覧表示する</span><span class="sxs-lookup"><span data-stu-id="daaad-117">Lists pending and completed actions for devices and email in one location</span></span> <br/><span data-ttu-id="daaad-118">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) plus Microsoft Defender for [Office 365](/microsoft-365/security/office-365-security/office-365-atp))</span><span class="sxs-lookup"><span data-stu-id="daaad-118">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) plus [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp))</span></span>|<span data-ttu-id="daaad-119">デバイスの保留中のアクションと完了したアクションの一覧</span><span class="sxs-lookup"><span data-stu-id="daaad-119">Lists pending and completed actions for devices</span></span> <br/> <span data-ttu-id="daaad-120">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) のみ)</span><span class="sxs-lookup"><span data-stu-id="daaad-120">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) only)</span></span>   |
|<span data-ttu-id="daaad-121">場所は次の場所です。</span><span class="sxs-lookup"><span data-stu-id="daaad-121">Is located at:</span></span><br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |<span data-ttu-id="daaad-122">場所は次の場所です。</span><span class="sxs-lookup"><span data-stu-id="daaad-122">Is located at:</span></span><br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| <span data-ttu-id="daaad-123">[セキュリティ センター Microsoft 365] で、[アクション センター]**を選択します**。</span><span class="sxs-lookup"><span data-stu-id="daaad-123">In the Microsoft 365 security center, choose **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="セキュリティ センターのアクション センター Microsoft 365移動する"::: | <span data-ttu-id="daaad-125">[自動調査Microsoft Defender セキュリティ センター] で、[**自動調査] アクション** センター  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="daaad-125">In the Microsoft Defender Security Center, choose **Automated investigations** > **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="[アクション] ウィンドウからアクション センターに移動Microsoft Defender セキュリティ センター":::  |

<span data-ttu-id="daaad-127">統合アクション センターでは、エンドポイント用の Defender と Defender の修復アクションが統合され、Office 365。</span><span class="sxs-lookup"><span data-stu-id="daaad-127">The unified Action center brings together remediation actions across Defender for Endpoint and Defender for Office 365.</span></span> <span data-ttu-id="daaad-128">すべての修復アクションの共通言語を定義し、統合された調査エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="daaad-128">It defines a common language for all remediation actions, and provides a unified investigation experience.</span></span> 

<span data-ttu-id="daaad-129">適切なアクセス許可と次のサブスクリプションの 1 つ以上がある場合は、統合アクション センターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="daaad-129">You can use the unified Action center if you have appropriate permissions and one or more of the following subscriptions:</span></span>
- [<span data-ttu-id="daaad-130">Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="daaad-130">Defender for Endpoint</span></span>](microsoft-defender-endpoint.md)
- [<span data-ttu-id="daaad-131">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="daaad-131">Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="daaad-132">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="daaad-132">Microsoft 365 Defender</span></span>](/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> <span data-ttu-id="daaad-133">詳細については、「要件」 [を参照してください](/microsoft-365/security/mtp/prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="daaad-133">To learn more, see [Requirements](/microsoft-365/security/mtp/prerequisites).</span></span>

## <a name="using-the-action-center"></a><span data-ttu-id="daaad-134">アクション センターの使用</span><span class="sxs-lookup"><span data-stu-id="daaad-134">Using the Action center</span></span>

<span data-ttu-id="daaad-135">強化されたセキュリティ センターで統合アクション センター Microsoft 365するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="daaad-135">To get to the unified Action center in the improved Microsoft 365 security center:</span></span>
1. <span data-ttu-id="daaad-136">セキュリティ センター ( ) Microsoft 365に移動し [https://security.microsoft.com](https://security.microsoft.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="daaad-136">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="daaad-137">ナビゲーション ウィンドウで、[アクション センター] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="daaad-137">In the navigation pane, select **Action center**.</span></span> 

<span data-ttu-id="daaad-138">アクション センターにアクセスすると、[保留中のアクション] と [履歴] **の 2 つのタブ** が **表示されます**。</span><span class="sxs-lookup"><span data-stu-id="daaad-138">When you visit the Action center, you see two tabs: **Pending actions** and **History**.</span></span> <span data-ttu-id="daaad-139">次の表に、各タブに表示される内容の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="daaad-139">The following table summarizes what you'll see on each tab:</span></span>

|<span data-ttu-id="daaad-140">タブ</span><span class="sxs-lookup"><span data-stu-id="daaad-140">Tab</span></span>  |<span data-ttu-id="daaad-141">説明</span><span class="sxs-lookup"><span data-stu-id="daaad-141">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="daaad-142">**Pending**</span><span class="sxs-lookup"><span data-stu-id="daaad-142">**Pending**</span></span>     | <span data-ttu-id="daaad-143">注意が必要なアクションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="daaad-143">Displays a list of actions that require attention.</span></span> <span data-ttu-id="daaad-144">アクションを一度に 1 つ承認または拒否するか、同じ種類のアクション (検疫ファイルなど) がある場合は複数のアクション **を選択できます**。</span><span class="sxs-lookup"><span data-stu-id="daaad-144">You can approve or reject actions one at a time, or select multiple actions if they have the same type of action (such as **Quarantine file**).</span></span> <br/><span data-ttu-id="daaad-145">**ヒント**: 保留中のアクションをできるだけ早く確認し、承認 (または拒否 [)](manage-auto-investigation.md) して、自動調査が正時に完了するようにします。</span><span class="sxs-lookup"><span data-stu-id="daaad-145">**TIP**: Make sure to [review and approve (or reject) pending actions](manage-auto-investigation.md) as soon as possible so that your automated investigations can complete in a timely manner.</span></span> |
|<span data-ttu-id="daaad-146">**履歴**</span><span class="sxs-lookup"><span data-stu-id="daaad-146">**History**</span></span>     | <span data-ttu-id="daaad-147">次のようなアクションの監査ログとして機能します。</span><span class="sxs-lookup"><span data-stu-id="daaad-147">Serves as an audit log for actions that were taken, such as:</span></span> <br/><span data-ttu-id="daaad-148">- 自動調査の結果として実行された修復アクション</span><span class="sxs-lookup"><span data-stu-id="daaad-148">- Remediation actions that were taken as a result of automated investigations</span></span> <br><span data-ttu-id="daaad-149">- セキュリティ運用チームによって承認された修復アクション</span><span class="sxs-lookup"><span data-stu-id="daaad-149">- Remediation actions that were approved by your security operations team</span></span>  <br/><span data-ttu-id="daaad-150">- Live Response セッション中に適用された、実行されたコマンドと修復アクション</span><span class="sxs-lookup"><span data-stu-id="daaad-150">- Commands that were run and remediation actions that were applied during Live Response sessions</span></span>  <br/><span data-ttu-id="daaad-151">- 脅威保護機能によって実行された修復Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="daaad-151">- Remediation actions that were taken by threat protection features in Microsoft Defender Antivirus</span></span>  <p><span data-ttu-id="daaad-152">特定のアクションを元に戻す方法を提供します (「完了した操作を元に戻[す」を参照)。](manage-auto-investigation.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="daaad-152">Provides a way to undo certain actions (see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions)).</span></span>       |

<span data-ttu-id="daaad-153">アクション センターでデータをカスタマイズ、並べ替え、フィルター処理、およびエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="daaad-153">You can customize, sort, filter, and export data in the Action center.</span></span>

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="アクション センターの列とフィルター":::

- <span data-ttu-id="daaad-155">列見出しを選択して、アイテムを昇順または降順に並べ替えます。</span><span class="sxs-lookup"><span data-stu-id="daaad-155">Select a column heading to sort items in ascending or descending order.</span></span>
- <span data-ttu-id="daaad-156">期間フィルターを使用して、過去の日、週、30 日、または 6 か月のデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="daaad-156">Use the time period filter to view data for the past day, week, 30 days, or 6 months.</span></span>
- <span data-ttu-id="daaad-157">表示する列を選択します。</span><span class="sxs-lookup"><span data-stu-id="daaad-157">Choose the columns that you want to view.</span></span>
- <span data-ttu-id="daaad-158">データの各ページに含めるアイテムの数を指定します。</span><span class="sxs-lookup"><span data-stu-id="daaad-158">Specify how many items to include on each page of data.</span></span>
- <span data-ttu-id="daaad-159">フィルターを使用して、表示するアイテムを表示します。</span><span class="sxs-lookup"><span data-stu-id="daaad-159">Use filters to view just the items you want to see.</span></span>
- <span data-ttu-id="daaad-160">[エクスポート **] を** 選択して、結果を.csvします。</span><span class="sxs-lookup"><span data-stu-id="daaad-160">Select **Export** to export results to a .csv file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="daaad-161">次の手順</span><span class="sxs-lookup"><span data-stu-id="daaad-161">Next steps</span></span>

- [<span data-ttu-id="daaad-162">修復アクションを表示および承認する</span><span class="sxs-lookup"><span data-stu-id="daaad-162">View and approve remediation actions</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="daaad-163">対話型ガイドを参照してください。 Microsoft Defender for Endpoint を使用して脅威を調査して修復する</span><span class="sxs-lookup"><span data-stu-id="daaad-163">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a><span data-ttu-id="daaad-164">関連項目</span><span class="sxs-lookup"><span data-stu-id="daaad-164">See also</span></span>

- [<span data-ttu-id="daaad-165">Microsoft Defender for Endpoint での誤検出/検出漏れに対処する</span><span class="sxs-lookup"><span data-stu-id="daaad-165">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)
