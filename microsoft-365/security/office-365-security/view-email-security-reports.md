---
title: メール セキュリティ レポートを表示する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: 管理者は、ポータルで使用できる電子メール セキュリティ レポートを検索して使用するMicrosoft 365 Defenderできます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ad90038ac818f9759768d0d00019393205b03f3
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083526"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="0ac7e-103">電子メール セキュリティ レポートを Microsoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="0ac7e-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0ac7e-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-104">**Applies to**</span></span>
- [<span data-ttu-id="0ac7e-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0ac7e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0ac7e-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="0ac7e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="0ac7e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ac7e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="0ac7e-108">Microsoft 365 Defender ポータルでは、Microsoft 365 のスパム対策、マルウェア対策、暗号化機能などの電子メール セキュリティ機能が組織を保護している方法を確認できます。 <https://security.microsoft.com></span><span class="sxs-lookup"><span data-stu-id="0ac7e-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="0ac7e-109">必要な [アクセス許可を](#what-permissions-are-needed-to-view-these-reports)持っている場合は、[レポートの電子メール] Microsoft 365 Defender コラボレーション レポートにアクセスして、Microsoft 365 Defender ポータルでこれらのレポート& \> **を** \> **表示&できます**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0ac7e-110">[コラボレーション レポートの電子メール] **ページ&移動するには、** を開きます <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![[&] ポータルの [コラボレーション レポート] ページMicrosoft 365 Defenderメール](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="0ac7e-112">[電子メール] コラボレーション レポート ページの一 **部のレポート&、Microsoft** Defender が必要です。Office 365。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="0ac7e-113">これらのレポートの詳細については[、「View Defender for Office 365ポータル」をMicrosoft 365 Defenderしてください](view-reports-for-mdo.md)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="0ac7e-114">メール フローに関連するレポートは、現在、Exchangeセンター (EAC) に表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="0ac7e-115">これらのレポートの詳細については、「新しい管理センターのメール フロー レポート[Exchange参照してください](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="0ac7e-116">侵害されたユーザー レポート</span><span class="sxs-lookup"><span data-stu-id="0ac7e-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="0ac7e-117">このレポートは、メールボックスを使用Microsoft 365組織Exchange Online使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="0ac7e-118">スタンドアロン 組織 (EOP) 組織ではExchange Online Protection使用できません。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="0ac7e-119">[**侵害されたユーザー] レポート** には、過去 7 日以内に[疑わしい] または [制限付き] とマークされたユーザー アカウントの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="0ac7e-120">これらの状態のどちらかのアカウントは、問題が発生したり、侵害された場合もあります。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="0ac7e-121">頻繁に使用すると、レポートを使用して、疑わしいアカウントや制限付きアカウントのスパイクや傾向を見つけるのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="0ac7e-122">侵害されたユーザーの詳細については、「侵害されたメール アカウントへの [応答」を参照してください](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![[コラボレーション レポートの電子メール] ページの [侵害&ユーザー] ウィジェット](../../media/compromised-users-report-widget.png)

<span data-ttu-id="0ac7e-124">集計ビューには過去 90 日間のデータが表示され、詳細ビューには過去 30 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="0ac7e-125">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0ac7e-126">[コラボレーション **レポートのメール&] ページで**、[侵害されたユーザー] を探し、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="0ac7e-127">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="0ac7e-128">[侵害された **ユーザー** ] ページで、[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択することで、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="0ac7e-129">**日付 (UTC)**:**開始日と\*\*\*\*終了日**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="0ac7e-130">**アクティビティ**:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-130">**Activity**:</span></span>
  - <span data-ttu-id="0ac7e-131">**疑** わしい : ユーザー アカウントが不審なメールを送信し、電子メールの送信を制限される危険性があります。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="0ac7e-132">**制限**: 不審なパターンが多く、ユーザー アカウントが電子メールの送信を制限されています。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="0ac7e-133">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![[侵害されたユーザー] レポートのレポート ビュー](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="0ac7e-135">グラフの下の詳細テーブルで、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="0ac7e-136">**作成時間**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-136">**Creation time**</span></span>
- <span data-ttu-id="0ac7e-137">**[ユーザー ID]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-137">**User ID**</span></span>
- <span data-ttu-id="0ac7e-138">**Action**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="0ac7e-139">Exchangeトランスポート ルール レポート</span><span class="sxs-lookup"><span data-stu-id="0ac7e-139">Exchange transport rule report</span></span>

<span data-ttu-id="0ac7e-140">トランスポート **Exchangeレポートには**、組織内の受信メッセージと送信メッセージに対するメール フロー ルール (トランスポート ルールとも呼ばれる) の影響が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="0ac7e-141">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0ac7e-142">[コラボレーション **レポートのメール&] ページ** で、トランスポート **Exchangeを見** つけて、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="0ac7e-143">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![Exchangeグループレポートページのトランスポート ルール &ウィジェット](../../media/transport-rule-report-widget.png)

<span data-ttu-id="0ac7e-145">[トランスポート **Exchangeレポート] ページ** で、使用可能なグラフとデータについて、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="0ac7e-146">[方向] によるグラフの内訳</span><span class="sxs-lookup"><span data-stu-id="0ac7e-146">Chart breakdown by Direction</span></span>

![トランスポート ルール レポートExchangeトランスポート ルールのExchange表示](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="0ac7e-148">[方向によるグラフ **の内訳] を選択すると**、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="0ac7e-149">**トランスポート ルールExchangeデータ** を表示する : メールフロー ルールの影響を受けた受信メッセージと送信メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="0ac7e-150">**データを DLP** Exchangeトランスポート ルールで表示する :データ損失防止 (DLP) メール フロー ルールの影響を受けた受信メッセージと送信メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="0ac7e-151">次の情報は、グラフの下の詳細テーブルに示されています。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="0ac7e-152">**Date**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-152">**Date**</span></span>
- <span data-ttu-id="0ac7e-153">**DLP ポリシー** (**DLP によるデータの表示Exchangeトランスポート ルールのみ**)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="0ac7e-154">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-154">**Transport rule**</span></span>
- <span data-ttu-id="0ac7e-155">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-155">**Subject**</span></span>
- <span data-ttu-id="0ac7e-156">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-156">**Sender address**</span></span>
- <span data-ttu-id="0ac7e-157">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-157">**Recipient address**</span></span>
- <span data-ttu-id="0ac7e-158">**重大度**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-158">**Severity**</span></span>
- <span data-ttu-id="0ac7e-159">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-159">**Direction**</span></span>

<span data-ttu-id="0ac7e-160">[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="0ac7e-161">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0ac7e-162">**方向**:**送信と\*\*\*\*受信**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="0ac7e-163">**重大度**:**重大度が高い、\*\*\*\*中程度の重大度**、**および低重大度**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="0ac7e-164">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="0ac7e-165">重大度別のグラフの内訳</span><span class="sxs-lookup"><span data-stu-id="0ac7e-165">Chart breakdown by Severity</span></span>

![トランスポート ルール レポートExchangeトランスポート ルールのExchange表示](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="0ac7e-167">[重要度による **グラフの内訳] を選択した場合** は、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="0ac7e-168">**トランスポート ルール別Exchange表示**: 重大度の高いメッセージ、中程度の重大度、および **低** 重大度メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="0ac7e-169">重大度レベルは、ルールのアクションとして設定します **(重大度** レベルまたは _SetAuditSeverity_ でこのルールを監査します)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="0ac7e-170">詳細については、「メール フロー ルール[のアクション」を参照Exchange Online。](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="0ac7e-171">**DLP メール フロー ルールExchange** 影響を受けた高重大度、中重大度、および低重大度メッセージの数。 </span><span class="sxs-lookup"><span data-stu-id="0ac7e-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="0ac7e-172">次の情報は、グラフの下の詳細テーブルに示されています。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="0ac7e-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-173">**Date**</span></span>
- <span data-ttu-id="0ac7e-174">**DLP ポリシー** (**DLP によるデータの表示Exchangeトランスポート ルールのみ**)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="0ac7e-175">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-175">**Transport rule**</span></span>
- <span data-ttu-id="0ac7e-176">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-176">**Subject**</span></span>
- <span data-ttu-id="0ac7e-177">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-177">**Sender address**</span></span>
- <span data-ttu-id="0ac7e-178">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-178">**Recipient address**</span></span>
- <span data-ttu-id="0ac7e-179">**重大度**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-179">**Severity**</span></span>
- <span data-ttu-id="0ac7e-180">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-180">**Direction**</span></span>

<span data-ttu-id="0ac7e-181">[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="0ac7e-182">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0ac7e-183">**方向**:**送信と\*\*\*\*受信**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="0ac7e-184">**重大度**:**重大度が高い、\*\*\*\*中程度の重大度**、**および低重大度**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="0ac7e-185">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="0ac7e-186">転送レポート</span><span class="sxs-lookup"><span data-stu-id="0ac7e-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="0ac7e-187">転送 **レポートは** EAC で利用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="0ac7e-188">詳細については、「新しい [EAC の自動転送メッセージ レポート」を参照してください](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="0ac7e-189">メールフローの状態レポート</span><span class="sxs-lookup"><span data-stu-id="0ac7e-189">Mailflow status report</span></span>

<span data-ttu-id="0ac7e-190">**Mailflow 状態** レポートは、受信および送信メール、スパム検出、マルウェア、"良い" と識別される電子メール、およびエッジで許可またはブロックされた電子メールに関する情報を示すスマート レポートです。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="0ac7e-191">これは、エッジ保護情報を含む唯一のレポートであり、EOP (EOP) による評価のためにサービスに許可される前にブロックされる電子メールの量を示Exchange Online Protectionです。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="0ac7e-192">メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="0ac7e-193">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0ac7e-194">[メール **の送信&] ページ** で、[ **メールフロー** の状態の概要] を探し、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="0ac7e-195">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![[メール] グループ作業レポート ページの [メールフロー&概要] ウィジェット](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="0ac7e-197">メールフロー状態レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="0ac7e-197">Type view for the Mailflow status report</span></span>

![メールフローの状態レポートにビューを入力する](../../media/mail-flow-status-report-type-view.png)

<span data-ttu-id="0ac7e-199">[メール **フローの状態] レポート ページで** 、[種類] **タブ** が既定で選択されています。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-199">On the **Mailflow status report** page, the **Type** tab is selected by default.</span></span> <span data-ttu-id="0ac7e-200">既定では、このビューにはグラフと、次のフィルターで構成された詳細テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-200">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="0ac7e-201">**日付 (UTC)** 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-201">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="0ac7e-202">**メールの方向**:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-202">**Mail direction**:</span></span>
  - <span data-ttu-id="0ac7e-203">**受信**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-203">**Inbound**</span></span>
  - <span data-ttu-id="0ac7e-204">**送信**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-204">**Outbound**</span></span>
  - <span data-ttu-id="0ac7e-205">**組織内**: この数は、テナント内のメッセージ 、つまり</span><span class="sxs-lookup"><span data-stu-id="0ac7e-205">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="0ac7e-206">送信者 abc@domain.com 受信者に送信 xyz@domain.com (受信および送信とは別 **に\*\*\*\*カウント)**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-206">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="0ac7e-207">**種類**:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-207">**Type**:</span></span>
  - <span data-ttu-id="0ac7e-208">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-208">**Good mail**</span></span>
  - <span data-ttu-id="0ac7e-209">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-209">**Malware**</span></span>
  - <span data-ttu-id="0ac7e-210">**[スパム]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-210">**Spam**</span></span>
  - <span data-ttu-id="0ac7e-211">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-211">**Edge protection**</span></span>
  - <span data-ttu-id="0ac7e-212">**ルール メッセージ**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-212">**Rule messages**</span></span>
  - <span data-ttu-id="0ac7e-213">**フィッシング詐欺メール**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-213">**Phishing email**</span></span>
- <span data-ttu-id="0ac7e-214">**ドメイン**: **すべて**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-214">**Domain**: **All**</span></span>

<span data-ttu-id="0ac7e-215">グラフは、Type 値によって **整理** されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-215">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="0ac7e-216">これらのフィルターは、[フィルター] をクリックして **変更できます**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-216">You can change these filters by clicking **Filter**.</span></span>

<span data-ttu-id="0ac7e-217">次の情報は、グラフの下の詳細テーブルに示されています。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-217">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="0ac7e-218">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-218">**Direction**</span></span>
- <span data-ttu-id="0ac7e-219">**型**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-219">**Type**</span></span>
- <span data-ttu-id="0ac7e-220">**24 時間**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-220">**24 hours**</span></span>
- <span data-ttu-id="0ac7e-221">**3 日間**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-221">**3 days**</span></span>
- <span data-ttu-id="0ac7e-222">**7 日間**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-222">**7 days**</span></span>
- <span data-ttu-id="0ac7e-223">**15 日**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-223">**15 days**</span></span>
- <span data-ttu-id="0ac7e-224">**30 日間**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-224">**30 days**</span></span>

<span data-ttu-id="0ac7e-225">詳細については、[ **カテゴリの選択] をクリックすると**、次の値から選択できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-225">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="0ac7e-226">**フィッシングメール**: この選択によって、脅威保護の [状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-226">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="0ac7e-227">**電子メール内のマルウェア**: この選択によって、脅威保護 [の状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-227">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="0ac7e-228">**スパム検出**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-228">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="0ac7e-229">**エッジブロックスパム**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-229">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="0ac7e-230">[種類] ビューからエクスポートする</span><span class="sxs-lookup"><span data-stu-id="0ac7e-230">Export from Type view</span></span>

<span data-ttu-id="0ac7e-231">詳細ビューでは、1 日のデータのみをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-231">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="0ac7e-232">したがって、7 日間データをエクスポートする場合は、7 つの異なるエクスポート アクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-232">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="0ac7e-233">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-233">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="0ac7e-234">その日のデータに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-234">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="0ac7e-235">メールフロー状態レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="0ac7e-235">Direction view for the Mailflow status report</span></span>

![メールフロー状態レポートの方向ビュー](../../media/mail-flow-status-report-direction-view.png)

<span data-ttu-id="0ac7e-237">[方向] タブ **をクリックすると** 、[種類] ビューの同じ既定 **のフィルター** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-237">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="0ac7e-238">グラフは、方向の値 **によって整理** されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-238">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="0ac7e-239">これらのフィルターは、[フィルター] をクリックして **変更できます**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-239">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="0ac7e-240">[種類] ビューの同 **じフィルターが** 使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-240">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="0ac7e-241">詳細テーブルには、Type ビューと同じ情報 **が含** まれている。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-241">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="0ac7e-242">[ **使用可能な選択と動作** の詳細については、カテゴリを選択する] は、[種類] ビューと **同** じです。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-242">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="0ac7e-243">方向ビューからエクスポートする</span><span class="sxs-lookup"><span data-stu-id="0ac7e-243">Export from Direction view</span></span>

<span data-ttu-id="0ac7e-244">詳細ビューでは、1 日のデータのみをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-244">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="0ac7e-245">したがって、7 日間データをエクスポートする場合は、7 つの異なるエクスポート アクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-245">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="0ac7e-246">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-246">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="0ac7e-247">その日のデータに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-247">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="0ac7e-248">メールフロー状態レポートのファネル ビュー</span><span class="sxs-lookup"><span data-stu-id="0ac7e-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="0ac7e-249">[ **ファネル** ] ビューには、Microsoft の電子メール脅威防止機能が組織内の受信メールと送信メールをフィルター処理する方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="0ac7e-250">電子メールの総数と、エッジ保護、マルウェア対策、フィッシング対策、スパム対策、スプーフィング対策などの構成済みの脅威保護機能が、この数に与える影響の詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

![メールフロー状態レポートのファネル ビュー](../../media/mail-flow-status-report-funnel-view.png)

<span data-ttu-id="0ac7e-252">[ファネル] タブ **を** クリックすると、既定では、次のフィルターで構成されたグラフと詳細テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-252">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="0ac7e-253">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-253">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="0ac7e-254">**方向**:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-254">**Direction**:</span></span>
  - <span data-ttu-id="0ac7e-255">**受信**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-255">**Inbound**</span></span>
  - <span data-ttu-id="0ac7e-256">**送信**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-256">**Outbound**</span></span>
  - <span data-ttu-id="0ac7e-257">**組織内**: この数は、テナント内で送信されるメッセージを示します。つまり、送信者は abc@domain.com に送信 xyz@domain.com (受信と送信とは別にカウントされます)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-257">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="0ac7e-258">集計ビューと詳細テーブル ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-258">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="0ac7e-259">これらのフィルターは、[フィルター] をクリックして **変更できます**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-259">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="0ac7e-260">[種類] ビューの同 **じフィルターが** 使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-260">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="0ac7e-261">このグラフは、次の方法で整理されたメール数を示しています。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-261">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="0ac7e-262">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-262">**Total email**</span></span>
- <span data-ttu-id="0ac7e-263">**エッジ保護後のメール**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-263">**Email after edge protection**</span></span>
- <span data-ttu-id="0ac7e-264">**トランスポート ルールの後のメール** (メール フロー ルール)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-264">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="0ac7e-265">**マルウェア対策、ファイル評価、ファイルの種類ブロック後のメール**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-265">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="0ac7e-266">**フィッシング対策、URL 評価、ブランド偽装、スプーフィング対策の後のメール**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-266">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="0ac7e-267">**スパム対策、バルク メール フィルター処理後のメール**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-267">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="0ac7e-268">**ユーザーとドメインの偽装後のメール**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0ac7e-268">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="0ac7e-269">**ファイルと URL の削除後のメール**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0ac7e-269">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="0ac7e-270">**配信後の保護後に良性として検出された電子メール (URL クリック時間保護)**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-270">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="0ac7e-271"><sup>\*</sup>Defender for Office 365のみ</span><span class="sxs-lookup"><span data-stu-id="0ac7e-271"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="0ac7e-272">EOP または Defender でフィルター処理されたメールを個別Office 365表示するには、グラフの凡例の値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-272">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="0ac7e-273">詳細テーブルには、降順に表示される次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-273">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="0ac7e-274">**Date**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-274">**Date**</span></span>
- <span data-ttu-id="0ac7e-275">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-275">**Total email**</span></span>
- <span data-ttu-id="0ac7e-276">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-276">**Edge protection**</span></span>
- <span data-ttu-id="0ac7e-277">**マルウェア対策、ファイル評価、ファイルの種類ブロック**:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-277">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="0ac7e-278">**ファイル評価**: 他の Microsoft のお客様が添付ファイルを識別するためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-278">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="0ac7e-279">**ファイルの種類のブロック**: メッセージで識別された悪意のあるファイルの種類によってフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-279">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="0ac7e-280">**フィッシング対策、URL レピュテーション、ブランド偽装、スプーフィング対策**:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-280">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="0ac7e-281">**URL レピュ** テーション : 他の Microsoft のお客様による URL の識別のためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-281">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="0ac7e-282">**ブランド偽装**: よく知られているブランド偽装送信者からのメッセージが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-282">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="0ac7e-283">**スプーフィング** 対策: 受信者が属するドメイン、またはメッセージ送信者が所有していないドメインをスプーフィングしようとするメッセージが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-283">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="0ac7e-284">**スパム対策、バルク メール フィルター**:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-284">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="0ac7e-285">**バルク メール フィルター :** スパム対策ポリシーの一括不平レベル (BCL) しきい値に基づいてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-285">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="0ac7e-286">**ユーザーとドメインの偽装 (Defender for Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-286">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="0ac7e-287">**ユーザー偽装**: フィッシング対策ポリシーの偽装保護設定で定義されているユーザー (メッセージ送信者) を偽装しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-287">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="0ac7e-288">**ドメイン偽装**: フィッシング対策ポリシーの偽装保護設定で定義されているドメインを偽装しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-288">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="0ac7e-289">**ファイルと URL のデトレーション (Defender for Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-289">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="0ac7e-290">**ファイルの削除**: 添付ファイル ポリシーでフィルターセーフメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-290">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="0ac7e-291">**URL の削除**: リンク ポリシーでフィルターセーフメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-291">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="0ac7e-292">**配信後の保護と ZAP (ATP)、または ZAP (EOP)**: マルウェア、スパム、フィッシングのゼロ時間自動削除 (ZAP)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-292">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="0ac7e-293">詳細テーブルで行を選択すると、メール数の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-293">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="0ac7e-294">ファネル ビューからエクスポートする</span><span class="sxs-lookup"><span data-stu-id="0ac7e-294">Export from Funnel view</span></span>

<span data-ttu-id="0ac7e-295">[オプション] で **[エクスポート]** **をクリック** すると、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-295">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="0ac7e-296">**概要 (最大で過去 90 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-296">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="0ac7e-297">**詳細 (最大で過去 30 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-297">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="0ac7e-298">[ **日付] で** 範囲を選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-298">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="0ac7e-299">現在のフィルターのデータは、特定のファイルに.csvされます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-299">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="0ac7e-300">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-300">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="0ac7e-301">データに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-301">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="0ac7e-302">メールフローの状態レポートの技術ビュー</span><span class="sxs-lookup"><span data-stu-id="0ac7e-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="0ac7e-303">Tech **ビューは、** ファネル **ビューに** 似ています。構成済みの脅威保護機能の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="0ac7e-304">グラフから、脅威保護の異なる段階でメッセージがどのように分類されるのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="0ac7e-305">[Tech view] **タブを** クリックすると、既定では、このビューにはグラフと、次のフィルターで構成された詳細テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="0ac7e-306">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="0ac7e-307">**方向**:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-307">**Direction**:</span></span>
  - <span data-ttu-id="0ac7e-308">**受信**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-308">**Inbound**</span></span>
  - <span data-ttu-id="0ac7e-309">**送信**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-309">**Outbound**</span></span>
  - <span data-ttu-id="0ac7e-310">**組織内**: この数は、テナント内のメッセージ 、つまり</span><span class="sxs-lookup"><span data-stu-id="0ac7e-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="0ac7e-311">送信者 abc@domain.com 受信者に送信 xyz@domain.com (受信および送信とは別にカウントされます)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="0ac7e-312">集計ビューと詳細テーブル ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="0ac7e-313">これらのフィルターは、[フィルター] をクリックして **変更できます**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="0ac7e-314">[種類] ビューの同 **じフィルターが** 使用されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="0ac7e-315">このグラフには、次のカテゴリに分類されたメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="0ac7e-316">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-316">**Total email**</span></span>
- <span data-ttu-id="0ac7e-317">**エッジ許可** と **フィルター処理されたエッジ**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="0ac7e-318">**トランスポート ルールの許可** と **トランスポート ルールのフィルター** 処理 (メール フロー ルール)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="0ac7e-319">**マルウェアではない\*\*\*\*、セーフ添付ファイルの検出、** <sup>\*</sup> **マルウェア対策エンジンの検出**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="0ac7e-320">**フィッシング** **、DMARC 障害、\*\*\*\*偽装検出、ス** プーフィング <sup>\*</sup> **検出**、**およびフィッシングの検出を行う**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="0ac7e-321">**URL のデトレーションと URL の** デトレーション **検出による検出なし**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0ac7e-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="0ac7e-322">**スパムとスパム\*\*\*\*ではない**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="0ac7e-323">**悪意のあるメール以外の電子\*\*\*\*メール、セーフリンクの検出** <sup>\*</sup> 、**および ZAP**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="0ac7e-324"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0ac7e-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="0ac7e-325">グラフ内のカテゴリにカーソルを合わせると、そのカテゴリ内のメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="0ac7e-326">詳細テーブルには、降順に表示される次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="0ac7e-327">**日付 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-327">**Date (UTC)**</span></span>
- <span data-ttu-id="0ac7e-328">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-328">**Total email**</span></span>
- <span data-ttu-id="0ac7e-329">**フィルター処理されたエッジ**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-329">**Edge filtered**</span></span>
- <span data-ttu-id="0ac7e-330">**ルール メッセージ**: メール フロー ルール (トランスポート ルールとも呼ばれる) が原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="0ac7e-331">**マルウェア対策エンジン、セーフ\*\*\*\*添付** <sup>\*</sup> ファイル:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="0ac7e-332">**DMARC、 偽装** <sup>\*</sup> 、 ス **プーフィング**、**フィッシング フィルター**:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="0ac7e-333">**DMARC**: DMARC 認証チェックに失敗したメッセージが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="0ac7e-334">**URL のデトレーション検出**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0ac7e-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="0ac7e-335">**フィルター処理されたスパム対策**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="0ac7e-336">**ZAP が削除されました**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-336">**ZAP removed**</span></span>
- <span data-ttu-id="0ac7e-337">**リンクによるセーフ検出**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0ac7e-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="0ac7e-338"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0ac7e-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="0ac7e-339">詳細テーブルで行を選択すると、メール数の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="0ac7e-340">Tech ビューからのエクスポート</span><span class="sxs-lookup"><span data-stu-id="0ac7e-340">Export from Tech view</span></span>

<span data-ttu-id="0ac7e-341">[エクスポート] **をクリックすると**、[ **オプション] で** 、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="0ac7e-342">**概要 (最大で過去 90 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="0ac7e-343">**詳細 (最大で過去 30 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="0ac7e-344">[ **日付] で** 範囲を選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="0ac7e-345">現在のフィルターのデータは、特定のファイルに.csvされます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="0ac7e-346">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="0ac7e-347">データに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![メールフロー状態レポートの技術ビュー](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="0ac7e-349">マルウェア検出レポート</span><span class="sxs-lookup"><span data-stu-id="0ac7e-349">Malware detections report</span></span>

<span data-ttu-id="0ac7e-350">[**マルウェア検出] レポート レポートには**、受信および送信電子メール メッセージ (マルウェアが受信または EOP によって検出Exchange Online Protection情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="0ac7e-351">EOP のマルウェア保護の詳細については、「EOP の [マルウェア対策保護」を参照してください](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="0ac7e-352">集計ビュー フィルターでは 90 日間、詳細テーブル フィルターでは 10 日間のみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="0ac7e-353">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0ac7e-354">[電子メール **の共有&] ページで** 、[ **電子メールで** 検出されたマルウェア] を探し、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="0ac7e-355">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![[メール と共同作業レポート] ページの電子メール ウィジェット&検出](../../media/malware-detections-widget.png)

<span data-ttu-id="0ac7e-357">[マルウェア **検出] レポート** ページで、[フィルター] をクリックし、次のいずれかの値を選択して、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="0ac7e-358">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0ac7e-359">**方向**:**受信および\*\*\*\*送信**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-359">**Direction**: **Inbound** and **Outbound**</span></span>

![電子メール レポートのマルウェア検出のレポート ビュー](../../media/malware-detections-report-view.png)

<span data-ttu-id="0ac7e-361">グラフの下の詳細テーブルで、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="0ac7e-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-362">**Date**</span></span>
- <span data-ttu-id="0ac7e-363">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-363">**Sender address**</span></span>
- <span data-ttu-id="0ac7e-364">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-364">**Recipient address**</span></span>
- <span data-ttu-id="0ac7e-365">**メッセージ ID**: メッセージ ヘッダーの **[Message-ID** ヘッダー] フィールドで使用できます。一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="0ac7e-366">値の例は `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次のようになります (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="0ac7e-367">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-367">**Subject**</span></span>
- <span data-ttu-id="0ac7e-368">**Filename**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-368">**Filename**</span></span>
- <span data-ttu-id="0ac7e-369">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="0ac7e-370">メール遅延レポート</span><span class="sxs-lookup"><span data-stu-id="0ac7e-370">Mail latency report</span></span>

<span data-ttu-id="0ac7e-371">Defender **for Office 365** のメール待機時間レポートには、組織内で発生したメール配信と発Office 365に関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="0ac7e-372">詳細については、「メール遅延 [レポート」を参照してください](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="0ac7e-373">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="0ac7e-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="0ac7e-374">スパム **検出レポートは最終的** に消え去る。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="0ac7e-375">脅威保護の状態レポートでも同 [じ情報を使用できます](#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="0ac7e-376">スプーフィング検出レポート</span><span class="sxs-lookup"><span data-stu-id="0ac7e-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="0ac7e-377">この記事で説明するように改善されたスプーフィング検出レポートはプレビューで、変更される可能性があります。また、すべての組織で利用できるとは限られません。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="0ac7e-378">レポートの以前のバージョンでは、良いメール **だけが表示され** 、スパム **としてキャッチされます**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="0ac7e-379">ス **プーフィング検出レポート** には、スプーフィングによってブロックまたは許可されたメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="0ac7e-380">スプーフィングの詳細については、「EOP でのスプーフィング防止 [保護」を参照してください](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="0ac7e-381">レポートの集計ビューでは 45 日間のフィルター処理が可能ですが、詳細ビューでは 10 日間のフィルター <sup>\*</sup> 処理のみ可能です。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="0ac7e-382"><sup>\*</sup> 最終的には、最大 90 日間のフィルター処理を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="0ac7e-383">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0ac7e-384">[メール **の共有&] ページで** 、[スプーフィングの検出] **を探** し、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="0ac7e-385">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/SpoofMailReportV2> 。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![[メール と共同作業レポート] ページ&スプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

<span data-ttu-id="0ac7e-387">グラフには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-387">The chart shows the following information:</span></span>

- <span data-ttu-id="0ac7e-388">**Pass**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-388">**Pass**</span></span>
- <span data-ttu-id="0ac7e-389">**Fail/失敗**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-389">**Fail**</span></span>
- <span data-ttu-id="0ac7e-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-390">**SoftPass**</span></span>
- <span data-ttu-id="0ac7e-391">**なし**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-391">**None**</span></span>
- <span data-ttu-id="0ac7e-392">**その他**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-392">**Other**</span></span>

<span data-ttu-id="0ac7e-393">グラフの 1 日 (データ ポイント) にカーソルを合わせると、スプーフィングされたメッセージの検出数と理由を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="0ac7e-394">[スプー **フィング** メール レポート] ページで、[フィルター] をクリックし、次の値の 1 つ以上を選択して、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="0ac7e-395">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0ac7e-396">**結果**:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-396">**Result**:</span></span>
  - <span data-ttu-id="0ac7e-397">**Pass**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-397">**Pass**</span></span>
  - <span data-ttu-id="0ac7e-398">**Fail/失敗**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-398">**Fail**</span></span>
  - <span data-ttu-id="0ac7e-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-399">**SoftPass**</span></span>
  - <span data-ttu-id="0ac7e-400">**なし**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-400">**None**</span></span>
  - <span data-ttu-id="0ac7e-401">**その他**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-401">**Other**</span></span>
- <span data-ttu-id="0ac7e-402">**スプーフィングの** 種類 :**内部と\*\*\*\*外部**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-402">**Spoof type**: **Internal** and **External**</span></span>

![[メール レポートのスプーフィング] ページ (Microsoft 365 Defender ポータル)](../../media/spoof-detections-report-page.png)

<span data-ttu-id="0ac7e-404">グラフの下の詳細テーブルで、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="0ac7e-405">**Date**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-405">**Date**</span></span>
- <span data-ttu-id="0ac7e-406">**スプーフィングされたユーザー**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-406">**Spoofed user**</span></span>
- <span data-ttu-id="0ac7e-407">**インフラストラクチャの送信**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="0ac7e-408">**スプーフィングの種類**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-408">**Spoof type**</span></span>
- <span data-ttu-id="0ac7e-409">**結果**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-409">**Result**</span></span>
- <span data-ttu-id="0ac7e-410">**結果コード**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-410">**Result code**</span></span>
- <span data-ttu-id="0ac7e-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-411">**SPF**</span></span>
- <span data-ttu-id="0ac7e-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-412">**DKIM**</span></span>
- <span data-ttu-id="0ac7e-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-413">**DMARC**</span></span>
- <span data-ttu-id="0ac7e-414">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-414">**Message count**</span></span>

<span data-ttu-id="0ac7e-415">複合認証結果コードの詳細については、「スパム対策メッセージ ヘッダー」を参照[Microsoft 365。](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="0ac7e-416">申請レポート</span><span class="sxs-lookup"><span data-stu-id="0ac7e-416">Submissions report</span></span>

<span data-ttu-id="0ac7e-417">申請 **レポートには** 、管理者が分析のために Microsoft に報告したアイテムに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="0ac7e-418">詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="0ac7e-419">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0ac7e-420">[コラボレーション **レポートのメール&] ページで**、[申請] を探し、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="0ac7e-421">レポートに直接移動するには、を開きます <https://security.microsoft.com/adminSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="0ac7e-422">ポータルで [管理者の申請に移動するには、[Microsoft 365 Defender提出](admin-submission.md)に移動 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![[コラボレーション レポートの電子メール] ページ&提出ウィジェット](../../media/submissions-report-widget.png)

<span data-ttu-id="0ac7e-424">グラフには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-424">The chart shows the following information:</span></span>

- <span data-ttu-id="0ac7e-425">**Pending**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-425">**Pending**</span></span>
- <span data-ttu-id="0ac7e-426">**Completed**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-426">**Completed**</span></span>

<span data-ttu-id="0ac7e-427">[申請 **] ページ** で、[フィルター] をクリックし、次の値の1 つ以上を選択して、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="0ac7e-428">**報告日**: **開始時刻** と **終了時刻**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="0ac7e-429">**申請の種類**:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-429">**Submission type**:</span></span>
  - <span data-ttu-id="0ac7e-430">**電子メール**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-430">**Email**</span></span>
  - <span data-ttu-id="0ac7e-431">**URL**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-431">**URL**</span></span>
  - <span data-ttu-id="0ac7e-432">**ファイル**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-432">**File**</span></span>
- <span data-ttu-id="0ac7e-433">**申請 ID**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-433">**Submission ID**</span></span>
- <span data-ttu-id="0ac7e-434">**ネットワーク メッセージ ID**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-434">**Network Message ID**</span></span>
- <span data-ttu-id="0ac7e-435">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-435">**Sender**</span></span>
- <span data-ttu-id="0ac7e-436">**名前**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-436">**Name**</span></span>
- <span data-ttu-id="0ac7e-437">**提出者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-437">**Submitted by**</span></span>
- <span data-ttu-id="0ac7e-438">**提出の理由**:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-438">**Reason for submitting**:</span></span>
  - <span data-ttu-id="0ac7e-439">**迷惑メールではない**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-439">**Not junk**</span></span>
  - <span data-ttu-id="0ac7e-440">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-440">**Phish**</span></span>
  - <span data-ttu-id="0ac7e-441">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-441">**Malware**</span></span>
  - <span data-ttu-id="0ac7e-442">**[スパム]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-442">**Spam**</span></span>
- <span data-ttu-id="0ac7e-443">**再スキャンの状態**:</span><span class="sxs-lookup"><span data-stu-id="0ac7e-443">**Rescan status**:</span></span>
  - <span data-ttu-id="0ac7e-444">**Pending**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-444">**Pending**</span></span>
  - <span data-ttu-id="0ac7e-445">**Completed**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-445">**Completed**</span></span>

<span data-ttu-id="0ac7e-446">グラフの下の詳細テーブルは、同じ情報を示し、[グループ] または [グループのカスタマイズ] 列のオプションは、[電子メール と共同作業の申請] の [分析用に送信済み] タブと同 **&です** \> 。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-446">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="0ac7e-447">詳細については [、「View admin submissions to Microsoft」を参照してください](admin-submission.md#view-admin-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-447">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![ポータルの申請レポート ページMicrosoft 365 Defenderページ](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="0ac7e-449">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="0ac7e-449">Threat protection status report</span></span>

<span data-ttu-id="0ac7e-450">脅威 **保護の状態レポート** は、EOP と Defender の両方Office 365。ただし、レポートには異なるデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-450">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="0ac7e-451">たとえば、EOP のお客様は、電子メールで検出されたマルウェアに関する情報を表示できますが[、SharePoint、OneDrive、](mdo-for-spo-odb-and-teams.md)および Microsoft Teams の セーフ 添付ファイルによって検出された悪意のあるファイルに関する情報は表示できません。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-451">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="0ac7e-452">このレポートには、マルウェア対策エンジンによってブロックされたファイルや Web サイト アドレス (URL)、ゼロ時間自動削除[(ZAP)、セーフ](zero-hour-auto-purge.md)[リンク、セーフ](safe-links.md)[添付](safe-attachments.md)ファイル、フィッシング対策ポリシーの偽装保護機能などの Office 365 機能の Defender などの悪意のあるコンテンツを含[](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)む電子メール メッセージの数が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-452">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="0ac7e-453">この情報を使用して、傾向を特定したり、組織のポリシーで調整が必要かどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-453">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="0ac7e-454">**注**: メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-454">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="0ac7e-455">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-455">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0ac7e-456">[電子 **メール &コラボレーション レポート]** ページで、[脅威保護の状態] **を探し** 、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-456">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="0ac7e-457">レポートに直接移動するには、次のいずれかの URL を開きます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-457">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="0ac7e-458">Defender for Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="0ac7e-458">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="0ac7e-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="0ac7e-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![[メール] グループの [コラボレーション レポート] ページ&の脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="0ac7e-461">既定では、グラフには過去 7 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-461">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="0ac7e-462">[脅威保護状態 **レポート]\*\*\*\*ページで**[フィルター] をクリックすると、90 日間の日付範囲を選択できます (試用版サブスクリプションは 30 日間に制限される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-462">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="0ac7e-463">詳細テーブルでは、30 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-463">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="0ac7e-464">使用可能なビューについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-464">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="0ac7e-465">概要でデータを表示する</span><span class="sxs-lookup"><span data-stu-id="0ac7e-465">View data by Overview</span></span>

![脅威保護の状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="0ac7e-467">[概要で **データを表示]** ビューでは、次の検出情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-467">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="0ac7e-468">**電子メール マルウェア**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-468">**Email malware**</span></span>
- <span data-ttu-id="0ac7e-469">**メールフィッシング**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-469">**Email phish**</span></span>
- <span data-ttu-id="0ac7e-470">**コンテンツ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-470">**Content malware**</span></span>

<span data-ttu-id="0ac7e-471">グラフの下に詳細テーブルはありません。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-471">No details table is available below the chart.</span></span>

<span data-ttu-id="0ac7e-472">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-472">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="0ac7e-473">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-473">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0ac7e-474">**検出**: **電子メール マルウェア**、 **メールフィッシング**、 **またはコンテンツ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-474">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="0ac7e-475">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-475">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="0ac7e-476">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-476">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="0ac7e-477">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-477">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="0ac7e-478">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-478">**Direction**</span></span>
- <span data-ttu-id="0ac7e-479">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-479">**Domain**</span></span>
- <span data-ttu-id="0ac7e-480">**[ポリシーの種類]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-480">**Policy type**</span></span>

<span data-ttu-id="0ac7e-481">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-481">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="0ac7e-482">検出テクノロジによってメール \> フィッシングとグラフの内訳でデータを表示する</span><span class="sxs-lookup"><span data-stu-id="0ac7e-482">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![脅威保護状態レポートでのフィッシングメールの検出テクノロジ ビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="0ac7e-484">[**メール フィッシングによるデータの表示 \> ] ビューと\*\*\*\*[検出** テクノロジによるグラフの内訳] ビューでは、次の情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-484">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="0ac7e-485">**URL 悪意のある評判**: Defender から生成された悪意のある URL レピュテーションOffice 365他のユーザーのMicrosoft 365 <sup>\*</sup> です。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-485">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="0ac7e-486">**高度なフィルター**: 機械学習に基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-486">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="0ac7e-487">**一般的なフィルター**: アナリスト ルールに基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-487">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="0ac7e-488">**組織内のスプーフィング**: 送信者が受信者ドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-488">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="0ac7e-489">**スプーフィング外部ドメイン**: 送信者が他のドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-489">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="0ac7e-490">**スプーフィング DMARC**: メッセージの DMARC 認証エラー。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-490">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="0ac7e-491">**偽装ブランド**: 送信者に基づく既知のブランドの偽装。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-491">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="0ac7e-492">**複合分析の検出**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-492">**Mixed analysis detection**</span></span>
- <span data-ttu-id="0ac7e-493">**ファイルの評価**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-493">**File reputation**</span></span>
- <span data-ttu-id="0ac7e-494">**指紋の一致**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-494">**Fingerprint matching**</span></span>
- <span data-ttu-id="0ac7e-495">**URL のデトレーション評価**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0ac7e-495">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="0ac7e-496">**URL のデトナレーション**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0ac7e-496">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="0ac7e-497">**偽装ユーザー**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0ac7e-497">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="0ac7e-498">**偽装ドメイン** <sup>\*</sup> : 顧客が所有または定義するドメインの偽装。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-498">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="0ac7e-499">**メールボックス インテリジェンスの偽装**: 管理者によって定義されたユーザー、またはメールボックス インテリジェンスによって学習された <sup>\*</sup> ユーザーの偽装。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-499">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="0ac7e-500">**ファイルのデトレーション**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0ac7e-500">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="0ac7e-501">**キャンペーン**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0ac7e-501">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="0ac7e-502">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-502">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="0ac7e-503">**Date**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-503">**Date**</span></span>
- <span data-ttu-id="0ac7e-504">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-504">**Subject**</span></span>
- <span data-ttu-id="0ac7e-505">**送信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-505">**Sender**</span></span>
- <span data-ttu-id="0ac7e-506">**受信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-506">**Recipients**</span></span>
- <span data-ttu-id="0ac7e-507">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-507">**Detected by**</span></span>
- <span data-ttu-id="0ac7e-508">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-508">**Delivery Status**</span></span>
- <span data-ttu-id="0ac7e-509">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-509">**Source of Compromise**</span></span>
- <span data-ttu-id="0ac7e-510">**Tags**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-510">**Tags**</span></span>

<span data-ttu-id="0ac7e-511">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-511">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="0ac7e-512">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-512">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0ac7e-513">**検出**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-513">**Detection**</span></span>
- <span data-ttu-id="0ac7e-514">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-514">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="0ac7e-515">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-515">**Direction**</span></span>
- <span data-ttu-id="0ac7e-516">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-516">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="0ac7e-517">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-517">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="0ac7e-518">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-518">**Domain**</span></span>
- <span data-ttu-id="0ac7e-519">**[ポリシーの種類]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-519">**Policy type**</span></span>
- <span data-ttu-id="0ac7e-520">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-520">**Policy name** (details table only)</span></span>
- <span data-ttu-id="0ac7e-521">**受信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-521">**Recipients**</span></span>

<span data-ttu-id="0ac7e-522">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-522">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="0ac7e-523">検出テクノロジによってメール \> マルウェアとグラフの内訳でデータを表示する</span><span class="sxs-lookup"><span data-stu-id="0ac7e-523">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![脅威保護状態レポートのマルウェアの検出テクノロジ ビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="0ac7e-525">[電子メール **マルウェアによる \> データの** 表示] ビューと **[検出** テクノロジによるグラフの内訳] ビューでは、次の情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-525">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="0ac7e-526">**ファイルの削除** <sup>\*</sup> : 添付ファイルセーフ検出。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-526">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="0ac7e-527">**ファイルの削除評価**: すべての悪意のあるファイルレピュテーションが Defender によって生成され、Office 365 <sup>\*</sup> されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-527">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="0ac7e-528">**ファイルの評価**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-528">**File reputation**</span></span>
- <span data-ttu-id="0ac7e-529">**マルウェア対策エンジン** <sup>\*</sup> : マルウェア対策エンジンからの検出。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-529">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="0ac7e-530">**マルウェア対策ポリシー ファイルの種類ブロック**: これらは、メッセージで識別された悪意のあるファイルの種類によってフィルター処理された電子メール メッセージです。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-530">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="0ac7e-531">**URL に悪意があるとする評価**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-531">**URL malicious reputation**</span></span>
- <span data-ttu-id="0ac7e-532">**URL のデトネーション**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-532">**URL detonation**</span></span>
- <span data-ttu-id="0ac7e-533">**URL のデトネーションの評価**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-533">**URL detonation reputation**</span></span>
- <span data-ttu-id="0ac7e-534">**キャンペーン**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-534">**Campaign**</span></span>

<span data-ttu-id="0ac7e-535">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-535">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="0ac7e-536">**Date**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-536">**Date**</span></span>
- <span data-ttu-id="0ac7e-537">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-537">**Subject**</span></span>
- <span data-ttu-id="0ac7e-538">**送信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-538">**Sender**</span></span>
- <span data-ttu-id="0ac7e-539">**受信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-539">**Recipients**</span></span>
- <span data-ttu-id="0ac7e-540">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-540">**Detected by**</span></span>
- <span data-ttu-id="0ac7e-541">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-541">**Delivery Status**</span></span>
- <span data-ttu-id="0ac7e-542">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-542">**Source of Compromise**</span></span>
- <span data-ttu-id="0ac7e-543">**Tags**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-543">**Tags**</span></span>

<span data-ttu-id="0ac7e-544">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-544">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="0ac7e-545">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-545">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0ac7e-546">**検出**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-546">**Detection**</span></span>
- <span data-ttu-id="0ac7e-547">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-547">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="0ac7e-548">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-548">**Direction**</span></span>
- <span data-ttu-id="0ac7e-549">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-549">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="0ac7e-550">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-550">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="0ac7e-551">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-551">**Domain**</span></span>
- <span data-ttu-id="0ac7e-552">**[ポリシーの種類]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-552">**Policy type**</span></span>
- <span data-ttu-id="0ac7e-553">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-553">**Policy name** (details table only)</span></span>
- <span data-ttu-id="0ac7e-554">**受信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-554">**Recipients**</span></span>

<span data-ttu-id="0ac7e-555">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-555">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="0ac7e-556">ポリシーの種類別のグラフの内訳とメールフィッシングによるデータの表示 \> またはメール マルウェアによるデータの \> 表示</span><span class="sxs-lookup"><span data-stu-id="0ac7e-556">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![脅威保護状態レポートのフィッシングメールまたはマルウェアメールのポリシーの種類の表示](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="0ac7e-558">[ポリシーの **種類別グラフ] ビューと**[メール フィッシングによるデータの表示] ビューまたは [メール マルウェアによるデータの表示] ビューでは、次の情報がグラフに表示されます。 **\>** **\>**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-558">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="0ac7e-559">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-559">**Anti-malware**</span></span>
- <span data-ttu-id="0ac7e-560">**セーフ添付ファイル**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="0ac7e-560">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="0ac7e-561">**フィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-561">**Anti-phish**</span></span>
- <span data-ttu-id="0ac7e-562">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-562">**Anti-spam**</span></span>
- <span data-ttu-id="0ac7e-563">**メール フロー ルール** (トランスポート ルールとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-563">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="0ac7e-564">**Others**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-564">**Others**</span></span>

<span data-ttu-id="0ac7e-565">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-565">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="0ac7e-566">**Date**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-566">**Date**</span></span>
- <span data-ttu-id="0ac7e-567">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-567">**Subject**</span></span>
- <span data-ttu-id="0ac7e-568">**送信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-568">**Sender**</span></span>
- <span data-ttu-id="0ac7e-569">**受信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-569">**Recipients**</span></span>
- <span data-ttu-id="0ac7e-570">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-570">**Detected by**</span></span>
- <span data-ttu-id="0ac7e-571">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-571">**Delivery Status**</span></span>
- <span data-ttu-id="0ac7e-572">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-572">**Source of Compromise**</span></span>
- <span data-ttu-id="0ac7e-573">**Tags**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-573">**Tags**</span></span>

<span data-ttu-id="0ac7e-574">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="0ac7e-575">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-575">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0ac7e-576">**検出**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-576">**Detection**</span></span>
- <span data-ttu-id="0ac7e-577">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-577">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="0ac7e-578">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-578">**Direction**</span></span>
- <span data-ttu-id="0ac7e-579">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-579">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="0ac7e-580">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-580">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="0ac7e-581">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-581">**Domain**</span></span>
- <span data-ttu-id="0ac7e-582">**[ポリシーの種類]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-582">**Policy type**</span></span>
- <span data-ttu-id="0ac7e-583">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-583">**Policy name** (details table only)</span></span>
- <span data-ttu-id="0ac7e-584">**受信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-584">**Recipients**</span></span>

<span data-ttu-id="0ac7e-585">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-585">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="0ac7e-586">[配信の状態] と [メールフィッシングによるデータの表示] または [ \> メール マルウェアによるデータの表示] によるグラフの \> 内訳</span><span class="sxs-lookup"><span data-stu-id="0ac7e-586">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![脅威保護状態レポートのフィッシングメールとマルウェアメールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="0ac7e-588">[配信 **状態別グラフの内訳]** ビューと [メール フィッシングによるデータの表示] ビューまたは [メール マルウェアによるデータの表示] ビューでは、次の情報がグラフに表示されます。 **\>** **\>**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-588">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="0ac7e-589">**ホストされたメールボックス: 受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-589">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="0ac7e-590">**ホストされたメールボックス: 迷惑メール**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-590">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="0ac7e-591">**ホストされたメールボックス: カスタム フォルダー**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-591">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="0ac7e-592">**ホストされたメールボックス: 削除済みアイテム**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-592">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="0ac7e-593">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-593">**Forwarded**</span></span>
- <span data-ttu-id="0ac7e-594">**オンプレミス サーバー: 配信**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-594">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="0ac7e-595">**検疫**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-595">**Quarantine**</span></span>
- <span data-ttu-id="0ac7e-596">**配信に失敗しました**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-596">**Delivery failed**</span></span>
- <span data-ttu-id="0ac7e-597">**ドロップ**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-597">**Dropped**</span></span>

<span data-ttu-id="0ac7e-598">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-598">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="0ac7e-599">**Date**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-599">**Date**</span></span>
- <span data-ttu-id="0ac7e-600">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-600">**Subject**</span></span>
- <span data-ttu-id="0ac7e-601">**送信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-601">**Sender**</span></span>
- <span data-ttu-id="0ac7e-602">**受信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-602">**Recipients**</span></span>
- <span data-ttu-id="0ac7e-603">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-603">**Detected by**</span></span>
- <span data-ttu-id="0ac7e-604">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-604">**Delivery Status**</span></span>
- <span data-ttu-id="0ac7e-605">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-605">**Source of Compromise**</span></span>
- <span data-ttu-id="0ac7e-606">**Tags**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-606">**Tags**</span></span>

<span data-ttu-id="0ac7e-607">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-607">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="0ac7e-608">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-608">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0ac7e-609">**検出**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-609">**Detection**</span></span>
- <span data-ttu-id="0ac7e-610">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-610">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="0ac7e-611">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-611">**Direction**</span></span>
- <span data-ttu-id="0ac7e-612">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-612">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="0ac7e-613">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-613">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="0ac7e-614">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-614">**Domain**</span></span>
- <span data-ttu-id="0ac7e-615">**[ポリシーの種類]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-615">**Policy type**</span></span>
- <span data-ttu-id="0ac7e-616">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-616">**Policy name** (details table only)</span></span>
- <span data-ttu-id="0ac7e-617">**受信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-617">**Recipients**</span></span>

<span data-ttu-id="0ac7e-618">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-618">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="0ac7e-619">コンテンツ マルウェアによるデータの \> 表示</span><span class="sxs-lookup"><span data-stu-id="0ac7e-619">View data by Content \> Malware</span></span>

![脅威保護状態レポートのコンテンツ マルウェア ビュー](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="0ac7e-621">[コンテンツ **マルウェアによるデータ \> の** 表示] ビューでは、組織の Microsoft Defender のグラフに次のOffice 365示されています。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-621">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="0ac7e-622">**マルウェア対策エンジン**: Sharepoint、OneDrive、および Microsoft Teams で組み込みのウイルス検出によって検出された悪意のある [Microsoft 365。](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-622">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="0ac7e-623">**ファイルの削除**: 添付ファイルによって検出された悪意のある [セーフ、SharePoint、OneDrive、](mdo-for-spo-odb-and-teams.md)およびMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-623">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="0ac7e-624">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-624">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="0ac7e-625">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-625">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0ac7e-626">**場所**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-626">**Location**</span></span>
- <span data-ttu-id="0ac7e-627">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-627">**Detected by**</span></span>
- <span data-ttu-id="0ac7e-628">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-628">**Malware name**</span></span>

<span data-ttu-id="0ac7e-629">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-629">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="0ac7e-630">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-630">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0ac7e-631">**検出**:**マルウェア対策エンジンまたは\*\*\*\*ファイルの削除**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-631">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="0ac7e-632">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-632">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="0ac7e-633">システムオーバーライドによるデータの表示</span><span class="sxs-lookup"><span data-stu-id="0ac7e-633">View data by System override</span></span>

![脅威保護状態レポートのメッセージの上書きビュー](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="0ac7e-635">[システムによる **データの表示] オーバーライド** ビューでは、次のオーバーライド理由情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-635">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="0ac7e-636">**オンプレミスのスキップ**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-636">**On-premises skip**</span></span>
- <span data-ttu-id="0ac7e-637">**IP 許可**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-637">**IP allow**</span></span>
- <span data-ttu-id="0ac7e-638">**Exchange トランスポート ルール**(メール フロー ルール)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-638">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="0ac7e-639">**組織で許可されている送信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-639">**Organization allowed senders**</span></span>
- <span data-ttu-id="0ac7e-640">**組織で許可されているドメイン**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-640">**Organization allowed domains**</span></span>
- <span data-ttu-id="0ac7e-641">**ZAP が有効になっていません**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-641">**ZAP not enabled**</span></span>
- <span data-ttu-id="0ac7e-642">**迷惑メール フォルダーが有効になっていない**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-642">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="0ac7e-643">**ユーザーセーフ送信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-643">**User Safe Sender**</span></span>
- <span data-ttu-id="0ac7e-644">**ユーザー セーフ ドメイン**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-644">**User Safe Domain**</span></span>

<span data-ttu-id="0ac7e-645">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-645">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="0ac7e-646">**Date**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-646">**Date**</span></span>
- <span data-ttu-id="0ac7e-647">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-647">**Subject**</span></span>
- <span data-ttu-id="0ac7e-648">**送信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-648">**Sender**</span></span>
- <span data-ttu-id="0ac7e-649">**受信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-649">**Recipients**</span></span>
- <span data-ttu-id="0ac7e-650">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-650">**Detected by**</span></span>
- <span data-ttu-id="0ac7e-651">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-651">**Delivery Status**</span></span>
- <span data-ttu-id="0ac7e-652">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-652">**Source of Compromise**</span></span>
- <span data-ttu-id="0ac7e-653">**Tags**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-653">**Tags**</span></span>

<span data-ttu-id="0ac7e-654">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-654">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="0ac7e-655">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-655">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="0ac7e-656">**検出**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-656">**Detection**</span></span>
- <span data-ttu-id="0ac7e-657">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-657">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="0ac7e-658">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-658">**Direction**</span></span>
- <span data-ttu-id="0ac7e-659">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-659">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="0ac7e-660">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-660">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="0ac7e-661">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-661">**Domain**</span></span>
- <span data-ttu-id="0ac7e-662">**[ポリシーの種類]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-662">**Policy type**</span></span>
- <span data-ttu-id="0ac7e-663">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-663">**Policy name** (details table only)</span></span>
- <span data-ttu-id="0ac7e-664">**受信者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-664">**Recipients**</span></span>

<span data-ttu-id="0ac7e-665">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-665">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="0ac7e-666"><sup>\*</sup>Defender for Office 365のみ</span><span class="sxs-lookup"><span data-stu-id="0ac7e-666"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="0ac7e-667">トップ マルウェア レポート</span><span class="sxs-lookup"><span data-stu-id="0ac7e-667">Top malware report</span></span>

<span data-ttu-id="0ac7e-668">[ **トップ マルウェア]** レポートには、EOP のマルウェア対策保護によって検出されたさまざまな種類 [のマルウェアが表示されます](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-668">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="0ac7e-669">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-669">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0ac7e-670">[電子メール **&コラボレーション レポート] ページで** 、[トップ マルウェア] を探 **し** 、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-670">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="0ac7e-671">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-671">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![[メール と共同作業レポート] ページの&のトップ マルウェア ウィジェット](../../media/top-malware-report-widget.png)

<span data-ttu-id="0ac7e-673">円グラフのくさびの上にマウス ポインターを置くと、マルウェアの種類の名前と、そのマルウェアが検出されたメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-673">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="0ac7e-674">[上位 **マルウェア レポート] ページ** で、より大きなバージョンの円グラフがレポート ページに表示されます。グラフの下の詳細テーブルは、次の情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-674">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="0ac7e-675">**トップ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-675">**Top malware**</span></span>
- <span data-ttu-id="0ac7e-676">**Count**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-676">**Count**</span></span>

<span data-ttu-id="0ac7e-677">[フィルター]**をクリック** すると、[開始日] と [終了日] で **日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-677">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![トップ マルウェア レポート ビュー](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="0ac7e-679">URL 脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="0ac7e-679">URL threat protection report</span></span>

<span data-ttu-id="0ac7e-680">URL **の脅威保護レポートは**、Microsoft Defender でのみ使用できます。Office 365。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-680">The **URL threat protection report** is available only in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="0ac7e-681">詳細については、「URL 脅威保護 [レポート」を参照してください](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-681">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="0ac7e-682">ユーザーが報告したメッセージ レポート</span><span class="sxs-lookup"><span data-stu-id="0ac7e-682">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0ac7e-683">ユーザーが報告した **メッセージ レポート** が正しく動作するには、ユーザーの環境で監査ログを有効にするMicrosoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-683">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="0ac7e-684">これは通常、監査ログの役割が管理者に割り当てられているユーザー Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-684">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="0ac7e-685">詳細については、「監査ログの[検索を有効またはMicrosoft 365を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-685">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="0ac7e-686">[**ユーザーレポート メッセージ]** レポートには、ユーザーが迷惑メール、フィッシング詐欺の試み、または良いメールとして報告した [](enable-the-report-message-add-in.md)電子メール メッセージに関する情報が、レポート メッセージ アドインまたはレポート フィッシング アドインを使用して表示 [されます](enable-the-report-phish-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-686">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="0ac7e-687">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-687">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="0ac7e-688">[コラボレーション **レポートのメール&] ページで**、[ユーザーが報告したメッセージ] を探し、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-688">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="0ac7e-689">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/userSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-689">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="0ac7e-690">ポータルで [管理者の申請に移動するには、[Microsoft 365 Defender提出](admin-submission.md)に移動 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-690">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![[メール] ページの [コラボレーション レポート] ページ&報告されたメッセージ ウィジェット](../../media/user-reported-messages-widget.png)

<span data-ttu-id="0ac7e-692">[ユーザー **が報告した** メッセージ] ページで、[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択して、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-692">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="0ac7e-693">**報告日**: **開始時刻** と **終了時刻**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-693">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="0ac7e-694">[**レポート作成者**]</span><span class="sxs-lookup"><span data-stu-id="0ac7e-694">**Reported by**</span></span>
- <span data-ttu-id="0ac7e-695">**メールの件名**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-695">**Email subject**</span></span>
- <span data-ttu-id="0ac7e-696">**メッセージの報告 ID**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-696">**Message reported ID**</span></span>
- <span data-ttu-id="0ac7e-697">**ネットワーク メッセージ ID**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-697">**Network Message ID**</span></span>
- <span data-ttu-id="0ac7e-698">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-698">**Sender**</span></span>
- <span data-ttu-id="0ac7e-699">**報告された理由**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-699">**Reported reason**</span></span>
  - <span data-ttu-id="0ac7e-700">**迷惑メールではない**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-700">**Not junk**</span></span>
  - <span data-ttu-id="0ac7e-701">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-701">**Phish**</span></span>
  - <span data-ttu-id="0ac7e-702">**[スパム]**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-702">**Spam**</span></span>
- <span data-ttu-id="0ac7e-703">**フィッシングシミュレーション**:**はいまたは\*\*\*\*いいえ**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-703">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="0ac7e-704">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-704">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="0ac7e-705">エントリをグループ化するには、[グループ] を **クリック** し、ドロップダウン リストから次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-705">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="0ac7e-706">**なし**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-706">**None**</span></span>
- <span data-ttu-id="0ac7e-707">**理由**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-707">**Reason**</span></span>
- <span data-ttu-id="0ac7e-708">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-708">**Sender**</span></span>
- <span data-ttu-id="0ac7e-709">[**レポート作成者**]</span><span class="sxs-lookup"><span data-stu-id="0ac7e-709">**Reported by**</span></span>
- <span data-ttu-id="0ac7e-710">**再スキャンの結果**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-710">**Rescan result**</span></span>
- <span data-ttu-id="0ac7e-711">**フィッシング シミュレーション**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-711">**Phish simulation**</span></span>

![ユーザーが報告したメッセージ レポート](../../media/user-reported-messages-report.png)

<span data-ttu-id="0ac7e-713">グラフの下の詳細テーブルで、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-713">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="0ac7e-714">**メールの件名**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-714">**Email subject**</span></span>
- <span data-ttu-id="0ac7e-715">[**レポート作成者**]</span><span class="sxs-lookup"><span data-stu-id="0ac7e-715">**Reported by**</span></span>
- <span data-ttu-id="0ac7e-716">**報告日**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-716">**Date reported**</span></span>
- <span data-ttu-id="0ac7e-717">**Sender**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-717">**Sender**</span></span>
- <span data-ttu-id="0ac7e-718">**報告された理由**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-718">**Reported reason**</span></span>
- <span data-ttu-id="0ac7e-719">**再スキャンの結果**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-719">**Rescan result**</span></span>
- <span data-ttu-id="0ac7e-720">**Tags**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-720">**Tags**</span></span>

<span data-ttu-id="0ac7e-721">分析のために Microsoft にメッセージを送信するには、表からメッセージ エントリを選択し、[分析のために **Microsoft** に送信] をクリックし、ドロップダウン リストから次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-721">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="0ac7e-722">**クリーンレポート**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-722">**Report clean**</span></span>
- <span data-ttu-id="0ac7e-723">**フィッシングの報告**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-723">**Report phishing**</span></span>
- <span data-ttu-id="0ac7e-724">**マルウェアの報告**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-724">**Report malware**</span></span>
- <span data-ttu-id="0ac7e-725">**[スパムを報告する**]</span><span class="sxs-lookup"><span data-stu-id="0ac7e-725">**Report spam**'</span></span>
- <span data-ttu-id="0ac7e-726">**トリガー調査**(Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-726">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="0ac7e-727">これらのレポートを表示するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0ac7e-727">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="0ac7e-728">この記事で説明するレポートを表示して使用するには、ポータルで次のいずれかの役割グループのメンバー Microsoft 365 Defenderがあります。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-728">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="0ac7e-729">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-729">**Organization Management**</span></span>
- <span data-ttu-id="0ac7e-730">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-730">**Security Administrator**</span></span>
- <span data-ttu-id="0ac7e-731">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-731">**Security Reader**</span></span>
- <span data-ttu-id="0ac7e-732">**グローバル リーダー**</span><span class="sxs-lookup"><span data-stu-id="0ac7e-732">**Global Reader**</span></span>

<span data-ttu-id="0ac7e-733">詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-733">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

<span data-ttu-id="0ac7e-734">**注**: Microsoft 365 管理センター の対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-734">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="0ac7e-735">詳細については、[「管理者の役割について」](../../admin/add-users/about-admin-roles.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-735">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="0ac7e-736">レポートにデータが表示されない場合は、</span><span class="sxs-lookup"><span data-stu-id="0ac7e-736">What if the reports aren't showing data?</span></span>

<span data-ttu-id="0ac7e-737">レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-737">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="0ac7e-738">詳細については、「脅威から保護 [する」を参照してください](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="0ac7e-738">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0ac7e-739">関連項目</span><span class="sxs-lookup"><span data-stu-id="0ac7e-739">Related topics</span></span>

[<span data-ttu-id="0ac7e-740">EOP でのスパム対策およびマルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="0ac7e-740">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="0ac7e-741">スマート レポートと分析情報 (Microsoft 365 Defenderポータル)</span><span class="sxs-lookup"><span data-stu-id="0ac7e-741">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="0ac7e-742">メール フロー レポートをポータルでMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="0ac7e-742">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="0ac7e-743">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="0ac7e-743">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
