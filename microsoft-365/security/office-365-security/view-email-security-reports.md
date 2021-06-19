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
description: 管理者は、Microsoft 365 Defender ポータルで使用できる電子メール セキュリティ レポートを検索して使用する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ad5a9f0d87902deb1985daebfa61cd733d22cbec
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029574"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="5dcac-103">Microsoft 365 Defender ポータルで電子メール セキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="5dcac-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5dcac-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="5dcac-104">**Applies to**</span></span>
- [<span data-ttu-id="5dcac-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5dcac-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5dcac-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="5dcac-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5dcac-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5dcac-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5dcac-108">Microsoft 365 Defender ポータルでは、Microsoft 365 のスパム対策、マルウェア対策、暗号化機能などの電子メール セキュリティ機能が組織を保護している方法を確認できます。 <https://security.microsoft.com></span><span class="sxs-lookup"><span data-stu-id="5dcac-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="5dcac-109">必要な [アクセス許可を](#what-permissions-are-needed-to-view-these-reports)持っている場合は、[電子メールのレポート] & コラボレーション レポートにアクセスして、Microsoft 365 Defender ポータルでこれらのレポート \>  \> **&表示できます**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5dcac-110">[コラボレーション レポートの電子メール] **ページ&移動するには、** を開きます <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="5dcac-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Microsoft 365 Defender &の [コラボレーション レポート] ページにメールを送信する](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="5dcac-112">[電子メール と共同作業レポート] ページ& **一部のレポートでは** 、Microsoft Defender が 365 Office必要です。</span><span class="sxs-lookup"><span data-stu-id="5dcac-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="5dcac-113">これらのレポートの詳細については [、「View Defender for Office 365 レポート」を参照してください](view-reports-for-mdo.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="5dcac-114">メール フローに関連するレポートが Exchange 管理センター (EAC) に追加されました。</span><span class="sxs-lookup"><span data-stu-id="5dcac-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="5dcac-115">これらのレポートの詳細については、「新しい Exchange 管理センターのメール フロー [レポート」を参照してください](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="5dcac-116">侵害されたユーザー レポート</span><span class="sxs-lookup"><span data-stu-id="5dcac-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="5dcac-117">このレポートは、Exchange Online メールボックスを持つ Microsoft 365 組織で利用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="5dcac-118">スタンドアロンの Exchange Online Protection (EOP) 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="5dcac-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="5dcac-119">[**侵害されたユーザー] レポート** には、過去 7 日以内に[疑わしい] または [制限付き] とマークされたユーザー アカウントの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="5dcac-120">これらの状態のどちらかのアカウントは、問題が発生したり、侵害された場合もあります。</span><span class="sxs-lookup"><span data-stu-id="5dcac-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="5dcac-121">頻繁に使用すると、レポートを使用して、疑わしいアカウントや制限付きアカウントのスパイクや傾向を見つけるのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="5dcac-122">侵害されたユーザーの詳細については、「侵害されたメール アカウントへの [応答」を参照してください](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![[コラボレーション レポートの電子メール] ページの [侵害&ユーザー] ウィジェット](../../media/compromised-users-report-widget.png)

<span data-ttu-id="5dcac-124">集計ビューには過去 90 日間のデータが表示され、詳細ビューには過去 30 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="5dcac-125">Microsoft 365 Defender ポータルでレポートを表示するには、「Reports  \> **Email &コラボレーション** レポート \> **&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5dcac-126">[コラボレーション **レポートのメール&] ページで**、[侵害されたユーザー] を探し、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="5dcac-127">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="5dcac-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="5dcac-128">[侵害された **ユーザー** ] ページで、[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択することで、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="5dcac-129">**日付 (UTC)**:**開始日と\*\*\*\*終了日**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="5dcac-130">**アクティビティ**:</span><span class="sxs-lookup"><span data-stu-id="5dcac-130">**Activity**:</span></span>
  - <span data-ttu-id="5dcac-131">**疑** わしい : ユーザー アカウントが不審なメールを送信し、電子メールの送信を制限される危険性があります。</span><span class="sxs-lookup"><span data-stu-id="5dcac-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="5dcac-132">**制限**: 不審なパターンが多く、ユーザー アカウントが電子メールの送信を制限されています。</span><span class="sxs-lookup"><span data-stu-id="5dcac-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="5dcac-133">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![[侵害されたユーザー] レポートのレポート ビュー](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="5dcac-135">グラフの下の詳細テーブルで、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="5dcac-136">**作成時間**</span><span class="sxs-lookup"><span data-stu-id="5dcac-136">**Creation time**</span></span>
- <span data-ttu-id="5dcac-137">**[ユーザー ID]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-137">**User ID**</span></span>
- <span data-ttu-id="5dcac-138">**Action**</span><span class="sxs-lookup"><span data-stu-id="5dcac-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="5dcac-139">Exchange トランスポート ルール レポート</span><span class="sxs-lookup"><span data-stu-id="5dcac-139">Exchange transport rule report</span></span>

<span data-ttu-id="5dcac-140">**Exchange トランスポート ルール レポートには**、組織内の受信メッセージと送信メッセージに対するメール フロー ルール (トランスポート ルールとも呼ばれる) の影響が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="5dcac-141">Microsoft 365 Defender ポータルでレポートを表示するには、「Reports  \> **Email &コラボレーション** レポート \> **&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5dcac-142">[電子メール **&コラボレーション レポート] ページで\*\*\*\*、Exchange トランスポート ルールを検索し**、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="5dcac-143">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="5dcac-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![[電子メール] コラボレーション レポート ページ& Exchange トランスポート ルール ウィジェット](../../media/transport-rule-report-widget.png)

<span data-ttu-id="5dcac-145">[Exchange トランスポート **ルール レポート] ページ** で、使用可能なグラフとデータについて、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="5dcac-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="5dcac-146">[方向] によるグラフの内訳</span><span class="sxs-lookup"><span data-stu-id="5dcac-146">Chart breakdown by Direction</span></span>

![Exchange トランスポート ルール レポートの Exchange トランスポート ルールの方向ビュー](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="5dcac-148">[方向によるグラフ **の内訳] を選択すると**、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="5dcac-149">**Exchange トランスポート ルールによるデータの表示**  : メールフロー ルールの影響を受けた受信メッセージと送信メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="5dcac-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="5dcac-150">**DLP Exchange トランスポート ルールによる** データの表示:データ損失防止 (DLP) メール フロー ルールの影響を受けた受信メッセージと送信メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="5dcac-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="5dcac-151">次の情報は、グラフの下の詳細テーブルに示されています。</span><span class="sxs-lookup"><span data-stu-id="5dcac-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="5dcac-152">**Date**</span><span class="sxs-lookup"><span data-stu-id="5dcac-152">**Date**</span></span>
- <span data-ttu-id="5dcac-153">**DLP ポリシー** (**DLP Exchange トランスポート ルールによるデータの表示** のみ)</span><span class="sxs-lookup"><span data-stu-id="5dcac-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="5dcac-154">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="5dcac-154">**Transport rule**</span></span>
- <span data-ttu-id="5dcac-155">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-155">**Subject**</span></span>
- <span data-ttu-id="5dcac-156">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-156">**Sender address**</span></span>
- <span data-ttu-id="5dcac-157">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="5dcac-157">**Recipient address**</span></span>
- <span data-ttu-id="5dcac-158">**重大度**</span><span class="sxs-lookup"><span data-stu-id="5dcac-158">**Severity**</span></span>
- <span data-ttu-id="5dcac-159">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-159">**Direction**</span></span>

<span data-ttu-id="5dcac-160">[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="5dcac-161">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="5dcac-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5dcac-162">**方向**:**送信と\*\*\*\*受信**</span><span class="sxs-lookup"><span data-stu-id="5dcac-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="5dcac-163">**重大度**:**重大度が高い、\*\*\*\*中程度の重大度**、**および低重大度**</span><span class="sxs-lookup"><span data-stu-id="5dcac-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="5dcac-164">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="5dcac-165">重大度別のグラフの内訳</span><span class="sxs-lookup"><span data-stu-id="5dcac-165">Chart breakdown by Severity</span></span>

![Exchange トランスポート ルール レポートの Exchange トランスポート ルールの重大度ビュー](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="5dcac-167">[重要度による **グラフの内訳] を選択した場合** は、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="5dcac-168">**Exchange トランスポート ルール別にデータ** を表示する: 重大度の高いメッセージ、中程度の重大度、および **低重大度メッセージの** 数。</span><span class="sxs-lookup"><span data-stu-id="5dcac-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="5dcac-169">重大度レベルは、ルールのアクションとして設定します **(重大度** レベルまたは _SetAuditSeverity_ でこのルールを監査します)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="5dcac-170">詳細については [、「Exchange Online のメール フロー ルールアクション」を参照してください](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="5dcac-171">**DLP Exchange トランスポート ルール** でデータを表示する : DLP メール フロールールの影響を受けた重大度の高いメッセージ、中程度の重大度、および低重大度メッセージの数。 </span><span class="sxs-lookup"><span data-stu-id="5dcac-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="5dcac-172">次の情報は、グラフの下の詳細テーブルに示されています。</span><span class="sxs-lookup"><span data-stu-id="5dcac-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="5dcac-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="5dcac-173">**Date**</span></span>
- <span data-ttu-id="5dcac-174">**DLP ポリシー** (**DLP Exchange トランスポート ルールによるデータの表示** のみ)</span><span class="sxs-lookup"><span data-stu-id="5dcac-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="5dcac-175">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="5dcac-175">**Transport rule**</span></span>
- <span data-ttu-id="5dcac-176">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-176">**Subject**</span></span>
- <span data-ttu-id="5dcac-177">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-177">**Sender address**</span></span>
- <span data-ttu-id="5dcac-178">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="5dcac-178">**Recipient address**</span></span>
- <span data-ttu-id="5dcac-179">**重大度**</span><span class="sxs-lookup"><span data-stu-id="5dcac-179">**Severity**</span></span>
- <span data-ttu-id="5dcac-180">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-180">**Direction**</span></span>

<span data-ttu-id="5dcac-181">[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="5dcac-182">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="5dcac-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5dcac-183">**方向**:**送信と\*\*\*\*受信**</span><span class="sxs-lookup"><span data-stu-id="5dcac-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="5dcac-184">**重大度**:**重大度が高い、\*\*\*\*中程度の重大度**、**および低重大度**</span><span class="sxs-lookup"><span data-stu-id="5dcac-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="5dcac-185">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="5dcac-186">転送レポート</span><span class="sxs-lookup"><span data-stu-id="5dcac-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="5dcac-187">転送 **レポートは** EAC で利用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="5dcac-188">詳細については、「新しい [EAC の自動転送メッセージ レポート」を参照してください](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="5dcac-189">メールフローの状態レポート</span><span class="sxs-lookup"><span data-stu-id="5dcac-189">Mailflow status report</span></span>

<span data-ttu-id="5dcac-190">**Mailflow 状態** レポートは、受信および送信メール、スパム検出、マルウェア、"良い" と識別される電子メール、およびエッジで許可またはブロックされた電子メールに関する情報を示すスマート レポートです。</span><span class="sxs-lookup"><span data-stu-id="5dcac-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="5dcac-191">これはエッジ保護情報を含む唯一のレポートであり、Exchange Online Protection (EOP) による評価のためにサービスに許可される前にブロックされる電子メールの量のみを示します。</span><span class="sxs-lookup"><span data-stu-id="5dcac-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="5dcac-192">メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="5dcac-193">Microsoft 365 Defender ポータルでレポートを表示するには、「Reports  \> **Email &コラボレーション** レポート \> **&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5dcac-194">[メール **の送信&] ページ** で、[ **メールフロー** の状態の概要] を探し、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="5dcac-195">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="5dcac-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![[メール] グループ作業レポート ページの [メールフロー&概要] ウィジェット](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="5dcac-197">メールフロー状態レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="5dcac-197">Type view for the Mailflow status report</span></span>

![メールフローの状態レポートにビューを入力する](../../media/mail-flow-status-report-type-view.png)

<span data-ttu-id="5dcac-199">[メール **フローの状態] レポート ページで** 、[種類] **タブ** が既定で選択されています。</span><span class="sxs-lookup"><span data-stu-id="5dcac-199">On the **Mailflow status report** page, the **Type** tab is selected by default.</span></span> <span data-ttu-id="5dcac-200">既定では、このビューにはグラフと、次のフィルターで構成された詳細テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-200">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="5dcac-201">**日付 (UTC)** 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="5dcac-201">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="5dcac-202">**メールの方向**:</span><span class="sxs-lookup"><span data-stu-id="5dcac-202">**Mail direction**:</span></span>
  - <span data-ttu-id="5dcac-203">**受信**</span><span class="sxs-lookup"><span data-stu-id="5dcac-203">**Inbound**</span></span>
  - <span data-ttu-id="5dcac-204">**送信**</span><span class="sxs-lookup"><span data-stu-id="5dcac-204">**Outbound**</span></span>
  - <span data-ttu-id="5dcac-205">**組織内**: この数は、テナント内のメッセージ 、つまり</span><span class="sxs-lookup"><span data-stu-id="5dcac-205">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="5dcac-206">送信者 abc@domain.com 受信者に送信 xyz@domain.com (受信および送信とは別 **に\*\*\*\*カウント)**</span><span class="sxs-lookup"><span data-stu-id="5dcac-206">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="5dcac-207">**種類**:</span><span class="sxs-lookup"><span data-stu-id="5dcac-207">**Type**:</span></span>
  - <span data-ttu-id="5dcac-208">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="5dcac-208">**Good mail**</span></span>
  - <span data-ttu-id="5dcac-209">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="5dcac-209">**Malware**</span></span>
  - <span data-ttu-id="5dcac-210">**スパム**</span><span class="sxs-lookup"><span data-stu-id="5dcac-210">**Spam**</span></span>
  - <span data-ttu-id="5dcac-211">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="5dcac-211">**Edge protection**</span></span>
  - <span data-ttu-id="5dcac-212">**ルール メッセージ**</span><span class="sxs-lookup"><span data-stu-id="5dcac-212">**Rule messages**</span></span>
  - <span data-ttu-id="5dcac-213">**フィッシング詐欺メール**</span><span class="sxs-lookup"><span data-stu-id="5dcac-213">**Phishing email**</span></span>
- <span data-ttu-id="5dcac-214">**ドメイン**: **すべて**</span><span class="sxs-lookup"><span data-stu-id="5dcac-214">**Domain**: **All**</span></span>

<span data-ttu-id="5dcac-215">グラフは、Type 値によって **整理** されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-215">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="5dcac-216">これらのフィルターは、[フィルター] をクリックして **変更できます**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-216">You can change these filters by clicking **Filter**.</span></span>

<span data-ttu-id="5dcac-217">次の情報は、グラフの下の詳細テーブルに示されています。</span><span class="sxs-lookup"><span data-stu-id="5dcac-217">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="5dcac-218">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-218">**Direction**</span></span>
- <span data-ttu-id="5dcac-219">**種類**</span><span class="sxs-lookup"><span data-stu-id="5dcac-219">**Type**</span></span>
- <span data-ttu-id="5dcac-220">**24 時間**</span><span class="sxs-lookup"><span data-stu-id="5dcac-220">**24 hours**</span></span>
- <span data-ttu-id="5dcac-221">**3 日間**</span><span class="sxs-lookup"><span data-stu-id="5dcac-221">**3 days**</span></span>
- <span data-ttu-id="5dcac-222">**7 日間**</span><span class="sxs-lookup"><span data-stu-id="5dcac-222">**7 days**</span></span>
- <span data-ttu-id="5dcac-223">**15 日**</span><span class="sxs-lookup"><span data-stu-id="5dcac-223">**15 days**</span></span>
- <span data-ttu-id="5dcac-224">**30 日間**</span><span class="sxs-lookup"><span data-stu-id="5dcac-224">**30 days**</span></span>

<span data-ttu-id="5dcac-225">詳細については、[ **カテゴリの選択] をクリックすると**、次の値から選択できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-225">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="5dcac-226">**フィッシングメール**: この選択によって、脅威保護の [状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-226">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="5dcac-227">**電子メール内のマルウェア**: この選択によって、脅威保護 [の状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-227">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="5dcac-228">**スパム検出**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-228">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="5dcac-229">**エッジブロックスパム**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-229">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="5dcac-230">[種類] ビューからエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5dcac-230">Export from Type view</span></span>

<span data-ttu-id="5dcac-231">詳細ビューでは、1 日のデータのみをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-231">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="5dcac-232">したがって、7 日間データをエクスポートする場合は、7 つの異なるエクスポート アクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dcac-232">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="5dcac-233">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-233">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="5dcac-234">その日のデータに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-234">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="5dcac-235">メールフロー状態レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="5dcac-235">Direction view for the Mailflow status report</span></span>

![メールフロー状態レポートの方向ビュー](../../media/mail-flow-status-report-direction-view.png)

<span data-ttu-id="5dcac-237">[方向] タブ **をクリックすると** 、[種類] ビューの同じ既定 **のフィルター** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-237">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="5dcac-238">グラフは、方向の値 **によって整理** されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-238">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="5dcac-239">これらのフィルターは、[フィルター] をクリックして **変更できます**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-239">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="5dcac-240">[種類] ビューの同 **じフィルターが** 使用されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-240">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="5dcac-241">詳細テーブルには、Type ビューと同じ情報 **が含** まれている。</span><span class="sxs-lookup"><span data-stu-id="5dcac-241">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="5dcac-242">[ **使用可能な選択と動作** の詳細については、カテゴリを選択する] は、[種類] ビューと **同** じです。</span><span class="sxs-lookup"><span data-stu-id="5dcac-242">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="5dcac-243">方向ビューからエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5dcac-243">Export from Direction view</span></span>

<span data-ttu-id="5dcac-244">詳細ビューでは、1 日のデータのみをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-244">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="5dcac-245">したがって、7 日間データをエクスポートする場合は、7 つの異なるエクスポート アクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dcac-245">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="5dcac-246">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-246">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="5dcac-247">その日のデータに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-247">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="5dcac-248">メールフロー状態レポートのファネル ビュー</span><span class="sxs-lookup"><span data-stu-id="5dcac-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="5dcac-249">[ **ファネル** ] ビューには、Microsoft の電子メール脅威防止機能が組織内の受信メールと送信メールをフィルター処理する方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="5dcac-250">電子メールの総数と、エッジ保護、マルウェア対策、フィッシング対策、スパム対策、スプーフィング対策などの構成済みの脅威保護機能が、この数に与える影響の詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="5dcac-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

![メールフロー状態レポートのファネル ビュー](../../media/mail-flow-status-report-funnel-view.png)

<span data-ttu-id="5dcac-252">[ファネル] タブ **を** クリックすると、既定では、次のフィルターで構成されたグラフと詳細テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-252">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="5dcac-253">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="5dcac-253">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="5dcac-254">**方向**:</span><span class="sxs-lookup"><span data-stu-id="5dcac-254">**Direction**:</span></span>
  - <span data-ttu-id="5dcac-255">**受信**</span><span class="sxs-lookup"><span data-stu-id="5dcac-255">**Inbound**</span></span>
  - <span data-ttu-id="5dcac-256">**送信**</span><span class="sxs-lookup"><span data-stu-id="5dcac-256">**Outbound**</span></span>
  - <span data-ttu-id="5dcac-257">**組織内**: この数は、テナント内で送信されるメッセージを示します。つまり、送信者は abc@domain.com に送信 xyz@domain.com (受信と送信とは別にカウントされます)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-257">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="5dcac-258">集計ビューと詳細テーブル ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="5dcac-258">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="5dcac-259">これらのフィルターは、[フィルター] をクリックして **変更できます**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-259">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="5dcac-260">[種類] ビューの同 **じフィルターが** 使用されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-260">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="5dcac-261">このグラフは、次の方法で整理されたメール数を示しています。</span><span class="sxs-lookup"><span data-stu-id="5dcac-261">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="5dcac-262">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="5dcac-262">**Total email**</span></span>
- <span data-ttu-id="5dcac-263">**エッジ保護後のメール**</span><span class="sxs-lookup"><span data-stu-id="5dcac-263">**Email after edge protection**</span></span>
- <span data-ttu-id="5dcac-264">**トランスポート ルールの後のメール** (メール フロー ルール)</span><span class="sxs-lookup"><span data-stu-id="5dcac-264">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="5dcac-265">**マルウェア対策、ファイル評価、ファイルの種類ブロック後のメール**</span><span class="sxs-lookup"><span data-stu-id="5dcac-265">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="5dcac-266">**フィッシング対策、URL 評価、ブランド偽装、スプーフィング対策の後のメール**</span><span class="sxs-lookup"><span data-stu-id="5dcac-266">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="5dcac-267">**スパム対策、バルク メール フィルター処理後のメール**</span><span class="sxs-lookup"><span data-stu-id="5dcac-267">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="5dcac-268">**ユーザーとドメインの偽装後のメール**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dcac-268">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="5dcac-269">**ファイルと URL の削除後のメール**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dcac-269">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="5dcac-270">**配信後の保護後に良性として検出された電子メール (URL クリック時間保護)**</span><span class="sxs-lookup"><span data-stu-id="5dcac-270">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="5dcac-271"><sup>\*</sup>Defender for Office 365のみ</span><span class="sxs-lookup"><span data-stu-id="5dcac-271"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="5dcac-272">EOP または Defender でフィルター処理されたメールを個別Office 365表示するには、グラフの凡例の値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5dcac-272">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="5dcac-273">詳細テーブルには、降順に表示される次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-273">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="5dcac-274">**Date**</span><span class="sxs-lookup"><span data-stu-id="5dcac-274">**Date**</span></span>
- <span data-ttu-id="5dcac-275">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="5dcac-275">**Total email**</span></span>
- <span data-ttu-id="5dcac-276">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="5dcac-276">**Edge protection**</span></span>
- <span data-ttu-id="5dcac-277">**マルウェア対策、ファイル評価、ファイルの種類ブロック**:</span><span class="sxs-lookup"><span data-stu-id="5dcac-277">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="5dcac-278">**ファイル評価**: 他の Microsoft のお客様が添付ファイルを識別するためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5dcac-278">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="5dcac-279">**ファイルの種類のブロック**: メッセージで識別された悪意のあるファイルの種類によってフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5dcac-279">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="5dcac-280">**フィッシング対策、URL レピュテーション、ブランド偽装、スプーフィング対策**:</span><span class="sxs-lookup"><span data-stu-id="5dcac-280">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="5dcac-281">**URL レピュ** テーション : 他の Microsoft のお客様による URL の識別のためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5dcac-281">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="5dcac-282">**ブランド偽装**: よく知られているブランド偽装送信者からのメッセージが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5dcac-282">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="5dcac-283">**スプーフィング** 対策: 受信者が属するドメイン、またはメッセージ送信者が所有していないドメインをスプーフィングしようとするメッセージが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5dcac-283">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="5dcac-284">**スパム対策、バルク メール フィルター**:</span><span class="sxs-lookup"><span data-stu-id="5dcac-284">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="5dcac-285">**バルク メール フィルター :** スパム対策ポリシーの一括不平レベル (BCL) しきい値に基づいてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5dcac-285">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="5dcac-286">**ユーザーとドメインの偽装 (Defender for Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="5dcac-286">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="5dcac-287">**ユーザー偽装**: フィッシング対策ポリシーの偽装保護設定で定義されているユーザー (メッセージ送信者) を偽装しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5dcac-287">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="5dcac-288">**ドメイン偽装**: フィッシング対策ポリシーの偽装保護設定で定義されているドメインを偽装しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5dcac-288">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="5dcac-289">**ファイルと URL のデトレーション (Defender for Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="5dcac-289">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="5dcac-290">**ファイルの削除**: 添付ファイル ポリシーでフィルターセーフメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5dcac-290">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="5dcac-291">**URL の削除**: リンク ポリシーでフィルターセーフメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5dcac-291">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="5dcac-292">**配信後の保護と ZAP (ATP)、または ZAP (EOP)**: マルウェア、スパム、フィッシングのゼロ時間自動削除 (ZAP)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-292">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="5dcac-293">詳細テーブルで行を選択すると、メール数の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-293">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="5dcac-294">ファネル ビューからエクスポートする</span><span class="sxs-lookup"><span data-stu-id="5dcac-294">Export from Funnel view</span></span>

<span data-ttu-id="5dcac-295">[オプション] で **[エクスポート]** **をクリック** すると、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-295">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="5dcac-296">**概要 (最大で過去 90 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="5dcac-296">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="5dcac-297">**詳細 (最大で過去 30 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="5dcac-297">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="5dcac-298">[ **日付] で** 範囲を選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-298">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="5dcac-299">現在のフィルターのデータは、特定のファイルに.csvされます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-299">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="5dcac-300">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-300">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="5dcac-301">データに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-301">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="5dcac-302">メールフローの状態レポートの技術ビュー</span><span class="sxs-lookup"><span data-stu-id="5dcac-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="5dcac-303">Tech **ビューは、** ファネル **ビューに** 似ています。構成済みの脅威保護機能の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="5dcac-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="5dcac-304">グラフから、脅威保護の異なる段階でメッセージがどのように分類されるのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="5dcac-305">[Tech view] **タブを** クリックすると、既定では、このビューにはグラフと、次のフィルターで構成された詳細テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="5dcac-306">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="5dcac-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="5dcac-307">**方向**:</span><span class="sxs-lookup"><span data-stu-id="5dcac-307">**Direction**:</span></span>
  - <span data-ttu-id="5dcac-308">**受信**</span><span class="sxs-lookup"><span data-stu-id="5dcac-308">**Inbound**</span></span>
  - <span data-ttu-id="5dcac-309">**送信**</span><span class="sxs-lookup"><span data-stu-id="5dcac-309">**Outbound**</span></span>
  - <span data-ttu-id="5dcac-310">**組織内**: この数は、テナント内のメッセージ 、つまり</span><span class="sxs-lookup"><span data-stu-id="5dcac-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="5dcac-311">送信者 abc@domain.com 受信者に送信 xyz@domain.com (受信および送信とは別にカウントされます)</span><span class="sxs-lookup"><span data-stu-id="5dcac-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="5dcac-312">集計ビューと詳細テーブル ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="5dcac-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="5dcac-313">これらのフィルターは、[フィルター] をクリックして **変更できます**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="5dcac-314">[種類] ビューの同 **じフィルターが** 使用されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="5dcac-315">このグラフには、次のカテゴリに分類されたメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="5dcac-316">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="5dcac-316">**Total email**</span></span>
- <span data-ttu-id="5dcac-317">**エッジ許可** と **フィルター処理されたエッジ**</span><span class="sxs-lookup"><span data-stu-id="5dcac-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="5dcac-318">**トランスポート ルールの許可** と **トランスポート ルールのフィルター** 処理 (メール フロー ルール)</span><span class="sxs-lookup"><span data-stu-id="5dcac-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="5dcac-319">**マルウェアではない\*\*\*\*、セーフ添付ファイルの検出、** <sup>\*</sup> **マルウェア対策エンジンの検出**</span><span class="sxs-lookup"><span data-stu-id="5dcac-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="5dcac-320">**フィッシング** **、DMARC 障害、\*\*\*\*偽装検出、ス** プーフィング <sup>\*</sup> **検出**、**およびフィッシングの検出を行う**</span><span class="sxs-lookup"><span data-stu-id="5dcac-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="5dcac-321">**URL のデトレーションと URL の** デトレーション **検出による検出なし**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dcac-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="5dcac-322">**スパムとスパム\*\*\*\*ではない**</span><span class="sxs-lookup"><span data-stu-id="5dcac-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="5dcac-323">**悪意のあるメール以外の電子\*\*\*\*メール、セーフリンクの検出** <sup>\*</sup> 、**および ZAP**</span><span class="sxs-lookup"><span data-stu-id="5dcac-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="5dcac-324"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="5dcac-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="5dcac-325">グラフ内のカテゴリにカーソルを合わせると、そのカテゴリ内のメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="5dcac-326">詳細テーブルには、降順に表示される次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="5dcac-327">**日付 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="5dcac-327">**Date (UTC)**</span></span>
- <span data-ttu-id="5dcac-328">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="5dcac-328">**Total email**</span></span>
- <span data-ttu-id="5dcac-329">**フィルター処理されたエッジ**</span><span class="sxs-lookup"><span data-stu-id="5dcac-329">**Edge filtered**</span></span>
- <span data-ttu-id="5dcac-330">**ルール メッセージ**: メール フロー ルール (トランスポート ルールとも呼ばれる) が原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5dcac-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="5dcac-331">**マルウェア対策エンジン、セーフ\*\*\*\*添付** <sup>\*</sup> ファイル:</span><span class="sxs-lookup"><span data-stu-id="5dcac-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="5dcac-332">**DMARC、 偽装** <sup>\*</sup> 、 ス **プーフィング**、**フィッシング フィルター**:</span><span class="sxs-lookup"><span data-stu-id="5dcac-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="5dcac-333">**DMARC**: DMARC 認証チェックに失敗したメッセージが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="5dcac-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="5dcac-334">**URL のデトレーション検出**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dcac-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="5dcac-335">**フィルター処理されたスパム対策**</span><span class="sxs-lookup"><span data-stu-id="5dcac-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="5dcac-336">**ZAP が削除されました**</span><span class="sxs-lookup"><span data-stu-id="5dcac-336">**ZAP removed**</span></span>
- <span data-ttu-id="5dcac-337">**リンクによるセーフ検出**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dcac-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="5dcac-338"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="5dcac-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="5dcac-339">詳細テーブルで行を選択すると、メール数の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="5dcac-340">Tech ビューからのエクスポート</span><span class="sxs-lookup"><span data-stu-id="5dcac-340">Export from Tech view</span></span>

<span data-ttu-id="5dcac-341">[エクスポート] **をクリックすると**、[ **オプション] で** 、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="5dcac-342">**概要 (最大で過去 90 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="5dcac-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="5dcac-343">**詳細 (最大で過去 30 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="5dcac-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="5dcac-344">[ **日付] で** 範囲を選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="5dcac-345">現在のフィルターのデータは、特定のファイルに.csvされます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="5dcac-346">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="5dcac-347">データに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![メールフロー状態レポートの技術ビュー](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="5dcac-349">マルウェア検出レポート</span><span class="sxs-lookup"><span data-stu-id="5dcac-349">Malware detections report</span></span>

<span data-ttu-id="5dcac-350">[**マルウェア検出] レポート レポートには**、受信および送信電子メール メッセージ (マルウェアが受信または EOP によって検出Exchange Online Protection情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="5dcac-351">EOP のマルウェア保護の詳細については、「EOP の [マルウェア対策保護」を参照してください](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="5dcac-352">集計ビュー フィルターでは 90 日間、詳細テーブル フィルターでは 10 日間のみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="5dcac-353">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5dcac-354">[電子メール **の共有&] ページで** 、[ **電子メールで** 検出されたマルウェア] を探し、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="5dcac-355">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="5dcac-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![[メール と共同作業レポート] ページの電子メール ウィジェット&検出](../../media/malware-detections-widget.png)

<span data-ttu-id="5dcac-357">[マルウェア **検出] レポート** ページで、[フィルター] をクリックし、次のいずれかの値を選択して、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="5dcac-358">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="5dcac-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5dcac-359">**方向**:**受信および\*\*\*\*送信**</span><span class="sxs-lookup"><span data-stu-id="5dcac-359">**Direction**: **Inbound** and **Outbound**</span></span>

![電子メール レポートのマルウェア検出のレポート ビュー](../../media/malware-detections-report-view.png)

<span data-ttu-id="5dcac-361">グラフの下の詳細テーブルで、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="5dcac-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="5dcac-362">**Date**</span></span>
- <span data-ttu-id="5dcac-363">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-363">**Sender address**</span></span>
- <span data-ttu-id="5dcac-364">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="5dcac-364">**Recipient address**</span></span>
- <span data-ttu-id="5dcac-365">**メッセージ ID**: メッセージ ヘッダーの **[Message-ID** ヘッダー] フィールドで使用できます。一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5dcac-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="5dcac-366">値の例は `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次のようになります (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="5dcac-367">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-367">**Subject**</span></span>
- <span data-ttu-id="5dcac-368">**Filename**</span><span class="sxs-lookup"><span data-stu-id="5dcac-368">**Filename**</span></span>
- <span data-ttu-id="5dcac-369">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="5dcac-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="5dcac-370">メール遅延レポート</span><span class="sxs-lookup"><span data-stu-id="5dcac-370">Mail latency report</span></span>

<span data-ttu-id="5dcac-371">Defender **for Office 365** のメール待機時間レポートには、組織内で発生したメール配信と発Office 365に関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="5dcac-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="5dcac-372">詳細については、「メール遅延 [レポート」を参照してください](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="5dcac-373">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="5dcac-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="5dcac-374">スパム **検出レポートは最終的** に消え去る。</span><span class="sxs-lookup"><span data-stu-id="5dcac-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="5dcac-375">脅威保護の状態レポートでも同 [じ情報を使用できます](#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="5dcac-376">スプーフィング検出レポート</span><span class="sxs-lookup"><span data-stu-id="5dcac-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="5dcac-377">この記事で説明するように改善されたスプーフィング検出レポートはプレビューで、変更される可能性があります。また、すべての組織で利用できるとは限られません。</span><span class="sxs-lookup"><span data-stu-id="5dcac-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="5dcac-378">レポートの以前のバージョンでは、良いメール **だけが表示され** 、スパム **としてキャッチされます**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="5dcac-379">ス **プーフィング検出レポート** には、スプーフィングによってブロックまたは許可されたメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="5dcac-380">スプーフィングの詳細については、「EOP でのスプーフィング防止 [保護」を参照してください](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="5dcac-381">レポートの集計ビューでは 45 日間のフィルター処理が可能ですが、詳細ビューでは 10 日間のフィルター <sup>\*</sup> 処理のみ可能です。</span><span class="sxs-lookup"><span data-stu-id="5dcac-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="5dcac-382"><sup>\*</sup> 最終的には、最大 90 日間のフィルター処理を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="5dcac-383">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5dcac-384">[メール **の共有&] ページで** 、[スプーフィングの検出] **を探** し、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="5dcac-385">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/SpoofMailReportV2> 。</span><span class="sxs-lookup"><span data-stu-id="5dcac-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![[メール と共同作業レポート] ページ&スプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

<span data-ttu-id="5dcac-387">グラフには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-387">The chart shows the following information:</span></span>

- <span data-ttu-id="5dcac-388">**Pass**</span><span class="sxs-lookup"><span data-stu-id="5dcac-388">**Pass**</span></span>
- <span data-ttu-id="5dcac-389">**Fail/失敗**</span><span class="sxs-lookup"><span data-stu-id="5dcac-389">**Fail**</span></span>
- <span data-ttu-id="5dcac-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="5dcac-390">**SoftPass**</span></span>
- <span data-ttu-id="5dcac-391">**なし**</span><span class="sxs-lookup"><span data-stu-id="5dcac-391">**None**</span></span>
- <span data-ttu-id="5dcac-392">**その他**</span><span class="sxs-lookup"><span data-stu-id="5dcac-392">**Other**</span></span>

<span data-ttu-id="5dcac-393">グラフの 1 日 (データ ポイント) にカーソルを合わせると、スプーフィングされたメッセージの検出数と理由を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="5dcac-394">[スプー **フィング** メール レポート] ページで、[フィルター] をクリックし、次の値の 1 つ以上を選択して、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="5dcac-395">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="5dcac-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5dcac-396">**結果**:</span><span class="sxs-lookup"><span data-stu-id="5dcac-396">**Result**:</span></span>
  - <span data-ttu-id="5dcac-397">**Pass**</span><span class="sxs-lookup"><span data-stu-id="5dcac-397">**Pass**</span></span>
  - <span data-ttu-id="5dcac-398">**Fail/失敗**</span><span class="sxs-lookup"><span data-stu-id="5dcac-398">**Fail**</span></span>
  - <span data-ttu-id="5dcac-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="5dcac-399">**SoftPass**</span></span>
  - <span data-ttu-id="5dcac-400">**なし**</span><span class="sxs-lookup"><span data-stu-id="5dcac-400">**None**</span></span>
  - <span data-ttu-id="5dcac-401">**その他**</span><span class="sxs-lookup"><span data-stu-id="5dcac-401">**Other**</span></span>
- <span data-ttu-id="5dcac-402">**スプーフィングの** 種類 :**内部と\*\*\*\*外部**</span><span class="sxs-lookup"><span data-stu-id="5dcac-402">**Spoof type**: **Internal** and **External**</span></span>

![[メール レポートのスプーフィング] ページ (Microsoft 365 Defender ポータル)](../../media/spoof-detections-report-page.png)

<span data-ttu-id="5dcac-404">グラフの下の詳細テーブルで、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="5dcac-405">**Date**</span><span class="sxs-lookup"><span data-stu-id="5dcac-405">**Date**</span></span>
- <span data-ttu-id="5dcac-406">**スプーフィングされたユーザー**</span><span class="sxs-lookup"><span data-stu-id="5dcac-406">**Spoofed user**</span></span>
- <span data-ttu-id="5dcac-407">**インフラストラクチャの送信**</span><span class="sxs-lookup"><span data-stu-id="5dcac-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="5dcac-408">**スプーフィングの種類**</span><span class="sxs-lookup"><span data-stu-id="5dcac-408">**Spoof type**</span></span>
- <span data-ttu-id="5dcac-409">**結果**</span><span class="sxs-lookup"><span data-stu-id="5dcac-409">**Result**</span></span>
- <span data-ttu-id="5dcac-410">**結果コード**</span><span class="sxs-lookup"><span data-stu-id="5dcac-410">**Result code**</span></span>
- <span data-ttu-id="5dcac-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="5dcac-411">**SPF**</span></span>
- <span data-ttu-id="5dcac-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="5dcac-412">**DKIM**</span></span>
- <span data-ttu-id="5dcac-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="5dcac-413">**DMARC**</span></span>
- <span data-ttu-id="5dcac-414">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="5dcac-414">**Message count**</span></span>

<span data-ttu-id="5dcac-415">複合認証結果コードの詳細については、「スパム対策メッセージ ヘッダー」を参照[Microsoft 365。](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="5dcac-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="5dcac-416">申請レポート</span><span class="sxs-lookup"><span data-stu-id="5dcac-416">Submissions report</span></span>

<span data-ttu-id="5dcac-417">申請 **レポートには** 、管理者が分析のために Microsoft に報告したアイテムに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="5dcac-418">詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dcac-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="5dcac-419">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5dcac-420">[コラボレーション **レポートのメール&] ページで**、[申請] を探し、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="5dcac-421">レポートに直接移動するには、を開きます <https://security.microsoft.com/adminSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="5dcac-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="5dcac-422">ポータルで [管理者の申請に移動するには、[Microsoft 365 Defender提出](admin-submission.md)に移動 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![[コラボレーション レポートの電子メール] ページ&提出ウィジェット](../../media/submissions-report-widget.png)

<span data-ttu-id="5dcac-424">グラフには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-424">The chart shows the following information:</span></span>

- <span data-ttu-id="5dcac-425">**Pending**</span><span class="sxs-lookup"><span data-stu-id="5dcac-425">**Pending**</span></span>
- <span data-ttu-id="5dcac-426">**Completed**</span><span class="sxs-lookup"><span data-stu-id="5dcac-426">**Completed**</span></span>

<span data-ttu-id="5dcac-427">[申請 **] ページ** で、[フィルター] をクリックし、次の値の1 つ以上を選択して、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="5dcac-428">**報告日**: **開始時刻** と **終了時刻**</span><span class="sxs-lookup"><span data-stu-id="5dcac-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="5dcac-429">**申請の種類**:</span><span class="sxs-lookup"><span data-stu-id="5dcac-429">**Submission type**:</span></span>
  - <span data-ttu-id="5dcac-430">**電子メール**</span><span class="sxs-lookup"><span data-stu-id="5dcac-430">**Email**</span></span>
  - <span data-ttu-id="5dcac-431">**URL**</span><span class="sxs-lookup"><span data-stu-id="5dcac-431">**URL**</span></span>
  - <span data-ttu-id="5dcac-432">**ファイル**</span><span class="sxs-lookup"><span data-stu-id="5dcac-432">**File**</span></span>
- <span data-ttu-id="5dcac-433">**申請 ID**</span><span class="sxs-lookup"><span data-stu-id="5dcac-433">**Submission ID**</span></span>
- <span data-ttu-id="5dcac-434">**ネットワーク メッセージ ID**</span><span class="sxs-lookup"><span data-stu-id="5dcac-434">**Network Message ID**</span></span>
- <span data-ttu-id="5dcac-435">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5dcac-435">**Sender**</span></span>
- <span data-ttu-id="5dcac-436">**名前**</span><span class="sxs-lookup"><span data-stu-id="5dcac-436">**Name**</span></span>
- <span data-ttu-id="5dcac-437">**提出者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-437">**Submitted by**</span></span>
- <span data-ttu-id="5dcac-438">**提出の理由**:</span><span class="sxs-lookup"><span data-stu-id="5dcac-438">**Reason for submitting**:</span></span>
  - <span data-ttu-id="5dcac-439">**迷惑メールではない**</span><span class="sxs-lookup"><span data-stu-id="5dcac-439">**Not junk**</span></span>
  - <span data-ttu-id="5dcac-440">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="5dcac-440">**Phish**</span></span>
  - <span data-ttu-id="5dcac-441">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="5dcac-441">**Malware**</span></span>
  - <span data-ttu-id="5dcac-442">**スパム**</span><span class="sxs-lookup"><span data-stu-id="5dcac-442">**Spam**</span></span>
- <span data-ttu-id="5dcac-443">**再スキャンの状態**:</span><span class="sxs-lookup"><span data-stu-id="5dcac-443">**Rescan status**:</span></span>
  - <span data-ttu-id="5dcac-444">**Pending**</span><span class="sxs-lookup"><span data-stu-id="5dcac-444">**Pending**</span></span>
  - <span data-ttu-id="5dcac-445">**Completed**</span><span class="sxs-lookup"><span data-stu-id="5dcac-445">**Completed**</span></span>

<span data-ttu-id="5dcac-446">グラフの下の詳細テーブルは、同じ情報を示し、[グループ] または [グループのカスタマイズ] 列のオプションは、[電子メール と共同作業の申請] の [分析用に送信済み] タブと同 **&です** \> 。</span><span class="sxs-lookup"><span data-stu-id="5dcac-446">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="5dcac-447">詳細については [、「View admin submissions to Microsoft」を参照してください](admin-submission.md#view-admin-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-447">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![ポータルの申請レポート ページMicrosoft 365 Defenderページ](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="5dcac-449">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="5dcac-449">Threat protection status report</span></span>

<span data-ttu-id="5dcac-450">脅威 **保護の状態レポート** は、EOP と Defender の両方Office 365。ただし、レポートには異なるデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="5dcac-450">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="5dcac-451">たとえば、EOP のお客様は、電子メールで検出されたマルウェアに関する情報を表示できますが[、SharePoint、OneDrive、](mdo-for-spo-odb-and-teams.md)および Microsoft Teams の セーフ 添付ファイルによって検出された悪意のあるファイルに関する情報は表示できません。</span><span class="sxs-lookup"><span data-stu-id="5dcac-451">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="5dcac-452">このレポートには、マルウェア対策エンジンによってブロックされたファイルや Web サイト アドレス (URL)、ゼロ時間自動削除[(ZAP)、セーフ](zero-hour-auto-purge.md)[リンク、セーフ](safe-links.md)[添付](safe-attachments.md)ファイル、フィッシング対策ポリシーの偽装保護機能などの Office 365 機能の Defender などの悪意のあるコンテンツを含[](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)む電子メール メッセージの数が提供されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-452">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="5dcac-453">この情報を使用して、傾向を特定したり、組織のポリシーで調整が必要かどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-453">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="5dcac-454">**注**: メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-454">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="5dcac-455">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-455">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5dcac-456">[電子 **メール &コラボレーション レポート]** ページで、[脅威保護の状態] **を探し** 、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-456">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="5dcac-457">レポートに直接移動するには、次のいずれかの URL を開きます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-457">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="5dcac-458">Defender for Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="5dcac-458">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="5dcac-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="5dcac-459">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![[メール] グループの [コラボレーション レポート] ページ&の脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="5dcac-461">既定では、グラフには過去 7 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-461">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="5dcac-462">[脅威保護状態 **レポート]\*\*\*\*ページで**[フィルター] をクリックすると、90 日間の日付範囲を選択できます (試用版サブスクリプションは 30 日間に制限される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-462">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="5dcac-463">詳細テーブルでは、30 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="5dcac-463">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="5dcac-464">使用可能なビューについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="5dcac-464">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="5dcac-465">概要でデータを表示する</span><span class="sxs-lookup"><span data-stu-id="5dcac-465">View data by Overview</span></span>

![脅威保護の状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="5dcac-467">[概要で **データを表示]** ビューでは、次の検出情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-467">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="5dcac-468">**電子メール マルウェア**</span><span class="sxs-lookup"><span data-stu-id="5dcac-468">**Email malware**</span></span>
- <span data-ttu-id="5dcac-469">**メールフィッシング**</span><span class="sxs-lookup"><span data-stu-id="5dcac-469">**Email phish**</span></span>
- <span data-ttu-id="5dcac-470">**コンテンツ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="5dcac-470">**Content malware**</span></span>

<span data-ttu-id="5dcac-471">グラフの下に詳細テーブルはありません。</span><span class="sxs-lookup"><span data-stu-id="5dcac-471">No details table is available below the chart.</span></span>

<span data-ttu-id="5dcac-472">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-472">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="5dcac-473">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="5dcac-473">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5dcac-474">**検出**: **電子メール マルウェア**、 **メールフィッシング**、 **またはコンテンツ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="5dcac-474">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="5dcac-475">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="5dcac-475">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="5dcac-476">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5dcac-476">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="5dcac-477">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-477">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="5dcac-478">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-478">**Direction**</span></span>
- <span data-ttu-id="5dcac-479">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5dcac-479">**Domain**</span></span>
- <span data-ttu-id="5dcac-480">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="5dcac-480">**Policy type**</span></span>

<span data-ttu-id="5dcac-481">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-481">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="5dcac-482">検出テクノロジによってメール \> フィッシングとグラフの内訳でデータを表示する</span><span class="sxs-lookup"><span data-stu-id="5dcac-482">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![脅威保護状態レポートでのフィッシングメールの検出テクノロジ ビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="5dcac-484">[**メール フィッシングによるデータの表示 \> ] ビューと\*\*\*\*[検出** テクノロジによるグラフの内訳] ビューでは、次の情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-484">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="5dcac-485">**URL 悪意のある評判**: Defender から生成された悪意のある URL レピュテーションOffice 365他のユーザーのMicrosoft 365 <sup>\*</sup> です。</span><span class="sxs-lookup"><span data-stu-id="5dcac-485">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="5dcac-486">**高度なフィルター**: 機械学習に基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="5dcac-486">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="5dcac-487">**一般的なフィルター**: アナリスト ルールに基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="5dcac-487">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="5dcac-488">**組織内のスプーフィング**: 送信者が受信者ドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="5dcac-488">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="5dcac-489">**スプーフィング外部ドメイン**: 送信者が他のドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="5dcac-489">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="5dcac-490">**スプーフィング DMARC**: メッセージの DMARC 認証エラー。</span><span class="sxs-lookup"><span data-stu-id="5dcac-490">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="5dcac-491">**偽装ブランド**: 送信者に基づく既知のブランドの偽装。</span><span class="sxs-lookup"><span data-stu-id="5dcac-491">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="5dcac-492">**複合分析の検出**</span><span class="sxs-lookup"><span data-stu-id="5dcac-492">**Mixed analysis detection**</span></span>
- <span data-ttu-id="5dcac-493">**ファイルの評価**</span><span class="sxs-lookup"><span data-stu-id="5dcac-493">**File reputation**</span></span>
- <span data-ttu-id="5dcac-494">**指紋の一致**</span><span class="sxs-lookup"><span data-stu-id="5dcac-494">**Fingerprint matching**</span></span>
- <span data-ttu-id="5dcac-495">**URL のデトレーション評価**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dcac-495">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="5dcac-496">**URL のデトナレーション**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dcac-496">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="5dcac-497">**偽装ユーザー**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dcac-497">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="5dcac-498">**偽装ドメイン** <sup>\*</sup> : 顧客が所有または定義するドメインの偽装。</span><span class="sxs-lookup"><span data-stu-id="5dcac-498">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="5dcac-499">**メールボックス インテリジェンスの偽装**: 管理者によって定義されたユーザー、またはメールボックス インテリジェンスによって学習された <sup>\*</sup> ユーザーの偽装。</span><span class="sxs-lookup"><span data-stu-id="5dcac-499">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="5dcac-500">**ファイルのデトレーション**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dcac-500">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="5dcac-501">**キャンペーン**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dcac-501">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="5dcac-502">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-502">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="5dcac-503">**Date**</span><span class="sxs-lookup"><span data-stu-id="5dcac-503">**Date**</span></span>
- <span data-ttu-id="5dcac-504">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-504">**Subject**</span></span>
- <span data-ttu-id="5dcac-505">**送信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-505">**Sender**</span></span>
- <span data-ttu-id="5dcac-506">**受信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-506">**Recipients**</span></span>
- <span data-ttu-id="5dcac-507">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="5dcac-507">**Detected by**</span></span>
- <span data-ttu-id="5dcac-508">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="5dcac-508">**Delivery Status**</span></span>
- <span data-ttu-id="5dcac-509">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="5dcac-509">**Source of Compromise**</span></span>
- <span data-ttu-id="5dcac-510">**Tags**</span><span class="sxs-lookup"><span data-stu-id="5dcac-510">**Tags**</span></span>

<span data-ttu-id="5dcac-511">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-511">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="5dcac-512">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="5dcac-512">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5dcac-513">**検出**</span><span class="sxs-lookup"><span data-stu-id="5dcac-513">**Detection**</span></span>
- <span data-ttu-id="5dcac-514">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="5dcac-514">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="5dcac-515">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-515">**Direction**</span></span>
- <span data-ttu-id="5dcac-516">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5dcac-516">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="5dcac-517">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-517">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="5dcac-518">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5dcac-518">**Domain**</span></span>
- <span data-ttu-id="5dcac-519">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="5dcac-519">**Policy type**</span></span>
- <span data-ttu-id="5dcac-520">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="5dcac-520">**Policy name** (details table only)</span></span>
- <span data-ttu-id="5dcac-521">**受信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-521">**Recipients**</span></span>

<span data-ttu-id="5dcac-522">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-522">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="5dcac-523">検出テクノロジによってメール \> マルウェアとグラフの内訳でデータを表示する</span><span class="sxs-lookup"><span data-stu-id="5dcac-523">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![脅威保護状態レポートのマルウェアの検出テクノロジ ビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="5dcac-525">[電子メール **マルウェアによる \> データの** 表示] ビューと **[検出** テクノロジによるグラフの内訳] ビューでは、次の情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-525">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="5dcac-526">**ファイルの削除** <sup>\*</sup> : 添付ファイルセーフ検出。</span><span class="sxs-lookup"><span data-stu-id="5dcac-526">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="5dcac-527">**ファイルの削除評価**: すべての悪意のあるファイルレピュテーションが Defender によって生成され、Office 365 <sup>\*</sup> されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-527">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="5dcac-528">**ファイルの評価**</span><span class="sxs-lookup"><span data-stu-id="5dcac-528">**File reputation**</span></span>
- <span data-ttu-id="5dcac-529">**マルウェア対策エンジン** <sup>\*</sup> : マルウェア対策エンジンからの検出。</span><span class="sxs-lookup"><span data-stu-id="5dcac-529">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="5dcac-530">**マルウェア対策ポリシー ファイルの種類ブロック**: これらは、メッセージで識別された悪意のあるファイルの種類によってフィルター処理された電子メール メッセージです。</span><span class="sxs-lookup"><span data-stu-id="5dcac-530">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="5dcac-531">**URL に悪意があるとする評価**</span><span class="sxs-lookup"><span data-stu-id="5dcac-531">**URL malicious reputation**</span></span>
- <span data-ttu-id="5dcac-532">**URL のデトネーション**</span><span class="sxs-lookup"><span data-stu-id="5dcac-532">**URL detonation**</span></span>
- <span data-ttu-id="5dcac-533">**URL のデトネーションの評価**</span><span class="sxs-lookup"><span data-stu-id="5dcac-533">**URL detonation reputation**</span></span>
- <span data-ttu-id="5dcac-534">**キャンペーン**</span><span class="sxs-lookup"><span data-stu-id="5dcac-534">**Campaign**</span></span>

<span data-ttu-id="5dcac-535">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-535">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="5dcac-536">**Date**</span><span class="sxs-lookup"><span data-stu-id="5dcac-536">**Date**</span></span>
- <span data-ttu-id="5dcac-537">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-537">**Subject**</span></span>
- <span data-ttu-id="5dcac-538">**送信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-538">**Sender**</span></span>
- <span data-ttu-id="5dcac-539">**受信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-539">**Recipients**</span></span>
- <span data-ttu-id="5dcac-540">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="5dcac-540">**Detected by**</span></span>
- <span data-ttu-id="5dcac-541">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="5dcac-541">**Delivery Status**</span></span>
- <span data-ttu-id="5dcac-542">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="5dcac-542">**Source of Compromise**</span></span>
- <span data-ttu-id="5dcac-543">**Tags**</span><span class="sxs-lookup"><span data-stu-id="5dcac-543">**Tags**</span></span>

<span data-ttu-id="5dcac-544">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-544">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="5dcac-545">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="5dcac-545">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5dcac-546">**検出**</span><span class="sxs-lookup"><span data-stu-id="5dcac-546">**Detection**</span></span>
- <span data-ttu-id="5dcac-547">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="5dcac-547">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="5dcac-548">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-548">**Direction**</span></span>
- <span data-ttu-id="5dcac-549">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5dcac-549">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="5dcac-550">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-550">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="5dcac-551">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5dcac-551">**Domain**</span></span>
- <span data-ttu-id="5dcac-552">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="5dcac-552">**Policy type**</span></span>
- <span data-ttu-id="5dcac-553">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="5dcac-553">**Policy name** (details table only)</span></span>
- <span data-ttu-id="5dcac-554">**受信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-554">**Recipients**</span></span>

<span data-ttu-id="5dcac-555">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-555">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="5dcac-556">ポリシーの種類別のグラフの内訳とメールフィッシングによるデータの表示 \> またはメール マルウェアによるデータの \> 表示</span><span class="sxs-lookup"><span data-stu-id="5dcac-556">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![脅威保護状態レポートのフィッシングメールまたはマルウェアメールのポリシーの種類の表示](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="5dcac-558">[ポリシーの **種類別グラフ] ビューと**[メール フィッシングによるデータの表示] ビューまたは [メール マルウェアによるデータの表示] ビューでは、次の情報がグラフに表示されます。 **\>** **\>**</span><span class="sxs-lookup"><span data-stu-id="5dcac-558">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="5dcac-559">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="5dcac-559">**Anti-malware**</span></span>
- <span data-ttu-id="5dcac-560">**セーフ添付ファイル**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5dcac-560">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="5dcac-561">**フィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="5dcac-561">**Anti-phish**</span></span>
- <span data-ttu-id="5dcac-562">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="5dcac-562">**Anti-spam**</span></span>
- <span data-ttu-id="5dcac-563">**メール フロー ルール** (トランスポート ルールとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="5dcac-563">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="5dcac-564">**Others**</span><span class="sxs-lookup"><span data-stu-id="5dcac-564">**Others**</span></span>

<span data-ttu-id="5dcac-565">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-565">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="5dcac-566">**Date**</span><span class="sxs-lookup"><span data-stu-id="5dcac-566">**Date**</span></span>
- <span data-ttu-id="5dcac-567">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-567">**Subject**</span></span>
- <span data-ttu-id="5dcac-568">**送信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-568">**Sender**</span></span>
- <span data-ttu-id="5dcac-569">**受信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-569">**Recipients**</span></span>
- <span data-ttu-id="5dcac-570">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="5dcac-570">**Detected by**</span></span>
- <span data-ttu-id="5dcac-571">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="5dcac-571">**Delivery Status**</span></span>
- <span data-ttu-id="5dcac-572">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="5dcac-572">**Source of Compromise**</span></span>
- <span data-ttu-id="5dcac-573">**Tags**</span><span class="sxs-lookup"><span data-stu-id="5dcac-573">**Tags**</span></span>

<span data-ttu-id="5dcac-574">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="5dcac-575">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="5dcac-575">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5dcac-576">**検出**</span><span class="sxs-lookup"><span data-stu-id="5dcac-576">**Detection**</span></span>
- <span data-ttu-id="5dcac-577">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="5dcac-577">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="5dcac-578">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-578">**Direction**</span></span>
- <span data-ttu-id="5dcac-579">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5dcac-579">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="5dcac-580">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-580">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="5dcac-581">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5dcac-581">**Domain**</span></span>
- <span data-ttu-id="5dcac-582">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="5dcac-582">**Policy type**</span></span>
- <span data-ttu-id="5dcac-583">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="5dcac-583">**Policy name** (details table only)</span></span>
- <span data-ttu-id="5dcac-584">**受信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-584">**Recipients**</span></span>

<span data-ttu-id="5dcac-585">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-585">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="5dcac-586">[配信の状態] と [メールフィッシングによるデータの表示] または [ \> メール マルウェアによるデータの表示] によるグラフの \> 内訳</span><span class="sxs-lookup"><span data-stu-id="5dcac-586">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![脅威保護状態レポートのフィッシングメールとマルウェアメールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="5dcac-588">[配信 **状態別グラフの内訳]** ビューと [メール フィッシングによるデータの表示] ビューまたは [メール マルウェアによるデータの表示] ビューでは、次の情報がグラフに表示されます。 **\>** **\>**</span><span class="sxs-lookup"><span data-stu-id="5dcac-588">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="5dcac-589">**ホストされたメールボックス: 受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="5dcac-589">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="5dcac-590">**ホストされたメールボックス: 迷惑メール**</span><span class="sxs-lookup"><span data-stu-id="5dcac-590">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="5dcac-591">**ホストされたメールボックス: カスタム フォルダー**</span><span class="sxs-lookup"><span data-stu-id="5dcac-591">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="5dcac-592">**ホストされたメールボックス: 削除済みアイテム**</span><span class="sxs-lookup"><span data-stu-id="5dcac-592">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="5dcac-593">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="5dcac-593">**Forwarded**</span></span>
- <span data-ttu-id="5dcac-594">**オンプレミス サーバー: 配信**</span><span class="sxs-lookup"><span data-stu-id="5dcac-594">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="5dcac-595">**検疫**</span><span class="sxs-lookup"><span data-stu-id="5dcac-595">**Quarantine**</span></span>
- <span data-ttu-id="5dcac-596">**配信に失敗しました**</span><span class="sxs-lookup"><span data-stu-id="5dcac-596">**Delivery failed**</span></span>
- <span data-ttu-id="5dcac-597">**ドロップ**</span><span class="sxs-lookup"><span data-stu-id="5dcac-597">**Dropped**</span></span>

<span data-ttu-id="5dcac-598">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-598">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="5dcac-599">**Date**</span><span class="sxs-lookup"><span data-stu-id="5dcac-599">**Date**</span></span>
- <span data-ttu-id="5dcac-600">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-600">**Subject**</span></span>
- <span data-ttu-id="5dcac-601">**送信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-601">**Sender**</span></span>
- <span data-ttu-id="5dcac-602">**受信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-602">**Recipients**</span></span>
- <span data-ttu-id="5dcac-603">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="5dcac-603">**Detected by**</span></span>
- <span data-ttu-id="5dcac-604">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="5dcac-604">**Delivery Status**</span></span>
- <span data-ttu-id="5dcac-605">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="5dcac-605">**Source of Compromise**</span></span>
- <span data-ttu-id="5dcac-606">**Tags**</span><span class="sxs-lookup"><span data-stu-id="5dcac-606">**Tags**</span></span>

<span data-ttu-id="5dcac-607">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-607">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="5dcac-608">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="5dcac-608">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5dcac-609">**検出**</span><span class="sxs-lookup"><span data-stu-id="5dcac-609">**Detection**</span></span>
- <span data-ttu-id="5dcac-610">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="5dcac-610">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="5dcac-611">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-611">**Direction**</span></span>
- <span data-ttu-id="5dcac-612">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5dcac-612">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="5dcac-613">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-613">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="5dcac-614">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5dcac-614">**Domain**</span></span>
- <span data-ttu-id="5dcac-615">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="5dcac-615">**Policy type**</span></span>
- <span data-ttu-id="5dcac-616">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="5dcac-616">**Policy name** (details table only)</span></span>
- <span data-ttu-id="5dcac-617">**受信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-617">**Recipients**</span></span>

<span data-ttu-id="5dcac-618">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-618">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="5dcac-619">コンテンツ マルウェアによるデータの \> 表示</span><span class="sxs-lookup"><span data-stu-id="5dcac-619">View data by Content \> Malware</span></span>

![脅威保護状態レポートのコンテンツ マルウェア ビュー](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="5dcac-621">[コンテンツ **マルウェアによるデータ \> の** 表示] ビューでは、組織の Microsoft Defender のグラフに次のOffice 365示されています。</span><span class="sxs-lookup"><span data-stu-id="5dcac-621">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="5dcac-622">**マルウェア対策エンジン**: Sharepoint、OneDrive、および Microsoft Teams で組み込みのウイルス検出によって検出された悪意のある [Microsoft 365。](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="5dcac-622">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="5dcac-623">**ファイルの削除**: 添付ファイルによって検出された悪意のある [セーフ、SharePoint、OneDrive、](mdo-for-spo-odb-and-teams.md)およびMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="5dcac-623">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="5dcac-624">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-624">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="5dcac-625">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="5dcac-625">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5dcac-626">**場所**</span><span class="sxs-lookup"><span data-stu-id="5dcac-626">**Location**</span></span>
- <span data-ttu-id="5dcac-627">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="5dcac-627">**Detected by**</span></span>
- <span data-ttu-id="5dcac-628">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="5dcac-628">**Malware name**</span></span>

<span data-ttu-id="5dcac-629">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-629">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="5dcac-630">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="5dcac-630">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5dcac-631">**検出**:**マルウェア対策エンジンまたは\*\*\*\*ファイルの削除**</span><span class="sxs-lookup"><span data-stu-id="5dcac-631">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="5dcac-632">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-632">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="5dcac-633">システムオーバーライドによるデータの表示</span><span class="sxs-lookup"><span data-stu-id="5dcac-633">View data by System override</span></span>

![脅威保護状態レポートのメッセージの上書きビュー](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="5dcac-635">[システムによる **データの表示] オーバーライド** ビューでは、次のオーバーライド理由情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-635">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="5dcac-636">**オンプレミスのスキップ**</span><span class="sxs-lookup"><span data-stu-id="5dcac-636">**On-premises skip**</span></span>
- <span data-ttu-id="5dcac-637">**IP 許可**</span><span class="sxs-lookup"><span data-stu-id="5dcac-637">**IP allow**</span></span>
- <span data-ttu-id="5dcac-638">**Exchange トランスポート ルール**(メール フロー ルール)</span><span class="sxs-lookup"><span data-stu-id="5dcac-638">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="5dcac-639">**組織で許可されている送信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-639">**Organization allowed senders**</span></span>
- <span data-ttu-id="5dcac-640">**組織で許可されているドメイン**</span><span class="sxs-lookup"><span data-stu-id="5dcac-640">**Organization allowed domains**</span></span>
- <span data-ttu-id="5dcac-641">**ZAP が有効になっていません**</span><span class="sxs-lookup"><span data-stu-id="5dcac-641">**ZAP not enabled**</span></span>
- <span data-ttu-id="5dcac-642">**迷惑メール フォルダーが有効になっていない**</span><span class="sxs-lookup"><span data-stu-id="5dcac-642">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="5dcac-643">**ユーザーセーフ送信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-643">**User Safe Sender**</span></span>
- <span data-ttu-id="5dcac-644">**ユーザー セーフ ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5dcac-644">**User Safe Domain**</span></span>

<span data-ttu-id="5dcac-645">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-645">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="5dcac-646">**Date**</span><span class="sxs-lookup"><span data-stu-id="5dcac-646">**Date**</span></span>
- <span data-ttu-id="5dcac-647">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-647">**Subject**</span></span>
- <span data-ttu-id="5dcac-648">**送信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-648">**Sender**</span></span>
- <span data-ttu-id="5dcac-649">**受信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-649">**Recipients**</span></span>
- <span data-ttu-id="5dcac-650">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="5dcac-650">**Detected by**</span></span>
- <span data-ttu-id="5dcac-651">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="5dcac-651">**Delivery Status**</span></span>
- <span data-ttu-id="5dcac-652">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="5dcac-652">**Source of Compromise**</span></span>
- <span data-ttu-id="5dcac-653">**Tags**</span><span class="sxs-lookup"><span data-stu-id="5dcac-653">**Tags**</span></span>

<span data-ttu-id="5dcac-654">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-654">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="5dcac-655">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="5dcac-655">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="5dcac-656">**検出**</span><span class="sxs-lookup"><span data-stu-id="5dcac-656">**Detection**</span></span>
- <span data-ttu-id="5dcac-657">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="5dcac-657">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="5dcac-658">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="5dcac-658">**Direction**</span></span>
- <span data-ttu-id="5dcac-659">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5dcac-659">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="5dcac-660">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-660">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="5dcac-661">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="5dcac-661">**Domain**</span></span>
- <span data-ttu-id="5dcac-662">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="5dcac-662">**Policy type**</span></span>
- <span data-ttu-id="5dcac-663">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="5dcac-663">**Policy name** (details table only)</span></span>
- <span data-ttu-id="5dcac-664">**受信者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-664">**Recipients**</span></span>

<span data-ttu-id="5dcac-665">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-665">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="5dcac-666"><sup>\*</sup>Defender for Office 365のみ</span><span class="sxs-lookup"><span data-stu-id="5dcac-666"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="5dcac-667">トップ マルウェア レポート</span><span class="sxs-lookup"><span data-stu-id="5dcac-667">Top malware report</span></span>

<span data-ttu-id="5dcac-668">[ **トップ マルウェア]** レポートには、EOP のマルウェア対策保護によって検出されたさまざまな種類 [のマルウェアが表示されます](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-668">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="5dcac-669">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-669">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5dcac-670">[電子メール **&コラボレーション レポート] ページで** 、[トップ マルウェア] を探 **し** 、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-670">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="5dcac-671">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="5dcac-671">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![[メール と共同作業レポート] ページの&のトップ マルウェア ウィジェット](../../media/top-malware-report-widget.png)

<span data-ttu-id="5dcac-673">円グラフのくさびの上にマウス ポインターを置くと、マルウェアの種類の名前と、そのマルウェアが検出されたメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-673">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="5dcac-674">[上位 **マルウェア レポート] ページ** で、より大きなバージョンの円グラフがレポート ページに表示されます。グラフの下の詳細テーブルは、次の情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="5dcac-674">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="5dcac-675">**トップ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="5dcac-675">**Top malware**</span></span>
- <span data-ttu-id="5dcac-676">**Count**</span><span class="sxs-lookup"><span data-stu-id="5dcac-676">**Count**</span></span>

<span data-ttu-id="5dcac-677">[フィルター]**をクリック** すると、[開始日] と [終了日] で **日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-677">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![トップ マルウェア レポート ビュー](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="5dcac-679">URL 脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="5dcac-679">URL threat protection report</span></span>

<span data-ttu-id="5dcac-680">URL **の脅威保護レポートは**、Microsoft Defender でのみ使用できます。Office 365。</span><span class="sxs-lookup"><span data-stu-id="5dcac-680">The **URL threat protection report** is available only in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="5dcac-681">詳細については、「URL 脅威保護 [レポート」を参照してください](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-681">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="5dcac-682">ユーザーが報告したメッセージ レポート</span><span class="sxs-lookup"><span data-stu-id="5dcac-682">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5dcac-683">ユーザーが報告した **メッセージ レポート** が正しく動作するには、ユーザーの環境で監査ログを有効にするMicrosoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="5dcac-683">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="5dcac-684">これは通常、監査ログの役割が管理者に割り当てられているユーザー Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="5dcac-684">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="5dcac-685">詳細については、「監査ログの[検索を有効またはMicrosoft 365を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-685">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="5dcac-686">[**ユーザーレポート メッセージ]** レポートには、ユーザーが迷惑メール、フィッシング詐欺の試み、または良いメールとして報告した [](enable-the-report-message-add-in.md)電子メール メッセージに関する情報が、レポート メッセージ アドインまたはレポート フィッシング アドインを使用して表示 [されます](enable-the-report-phish-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-686">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="5dcac-687">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-687">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="5dcac-688">[コラボレーション **レポートのメール&] ページで**、[ユーザーが報告したメッセージ] を探し、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-688">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="5dcac-689">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/userSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="5dcac-689">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="5dcac-690">ポータルで [管理者の申請に移動するには、[Microsoft 365 Defender提出](admin-submission.md)に移動 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-690">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![[メール] ページの [コラボレーション レポート] ページ&報告されたメッセージ ウィジェット](../../media/user-reported-messages-widget.png)

<span data-ttu-id="5dcac-692">[ユーザー **が報告した** メッセージ] ページで、[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択して、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-692">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="5dcac-693">**報告日**: **開始時刻** と **終了時刻**</span><span class="sxs-lookup"><span data-stu-id="5dcac-693">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="5dcac-694">[**レポート作成者**]</span><span class="sxs-lookup"><span data-stu-id="5dcac-694">**Reported by**</span></span>
- <span data-ttu-id="5dcac-695">**メールの件名**</span><span class="sxs-lookup"><span data-stu-id="5dcac-695">**Email subject**</span></span>
- <span data-ttu-id="5dcac-696">**メッセージの報告 ID**</span><span class="sxs-lookup"><span data-stu-id="5dcac-696">**Message reported ID**</span></span>
- <span data-ttu-id="5dcac-697">**ネットワーク メッセージ ID**</span><span class="sxs-lookup"><span data-stu-id="5dcac-697">**Network Message ID**</span></span>
- <span data-ttu-id="5dcac-698">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5dcac-698">**Sender**</span></span>
- <span data-ttu-id="5dcac-699">**報告された理由**</span><span class="sxs-lookup"><span data-stu-id="5dcac-699">**Reported reason**</span></span>
  - <span data-ttu-id="5dcac-700">**迷惑メールではない**</span><span class="sxs-lookup"><span data-stu-id="5dcac-700">**Not junk**</span></span>
  - <span data-ttu-id="5dcac-701">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="5dcac-701">**Phish**</span></span>
  - <span data-ttu-id="5dcac-702">**スパム**</span><span class="sxs-lookup"><span data-stu-id="5dcac-702">**Spam**</span></span>
- <span data-ttu-id="5dcac-703">**フィッシングシミュレーション**:**はいまたは\*\*\*\*いいえ**</span><span class="sxs-lookup"><span data-stu-id="5dcac-703">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="5dcac-704">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5dcac-704">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="5dcac-705">エントリをグループ化するには、[グループ] を **クリック** し、ドロップダウン リストから次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="5dcac-705">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="5dcac-706">**なし**</span><span class="sxs-lookup"><span data-stu-id="5dcac-706">**None**</span></span>
- <span data-ttu-id="5dcac-707">**理由**</span><span class="sxs-lookup"><span data-stu-id="5dcac-707">**Reason**</span></span>
- <span data-ttu-id="5dcac-708">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5dcac-708">**Sender**</span></span>
- <span data-ttu-id="5dcac-709">[**レポート作成者**]</span><span class="sxs-lookup"><span data-stu-id="5dcac-709">**Reported by**</span></span>
- <span data-ttu-id="5dcac-710">**再スキャンの結果**</span><span class="sxs-lookup"><span data-stu-id="5dcac-710">**Rescan result**</span></span>
- <span data-ttu-id="5dcac-711">**フィッシング シミュレーション**</span><span class="sxs-lookup"><span data-stu-id="5dcac-711">**Phish simulation**</span></span>

![ユーザーが報告したメッセージ レポート](../../media/user-reported-messages-report.png)

<span data-ttu-id="5dcac-713">グラフの下の詳細テーブルで、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-713">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="5dcac-714">**メールの件名**</span><span class="sxs-lookup"><span data-stu-id="5dcac-714">**Email subject**</span></span>
- <span data-ttu-id="5dcac-715">[**レポート作成者**]</span><span class="sxs-lookup"><span data-stu-id="5dcac-715">**Reported by**</span></span>
- <span data-ttu-id="5dcac-716">**報告日**</span><span class="sxs-lookup"><span data-stu-id="5dcac-716">**Date reported**</span></span>
- <span data-ttu-id="5dcac-717">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5dcac-717">**Sender**</span></span>
- <span data-ttu-id="5dcac-718">**報告された理由**</span><span class="sxs-lookup"><span data-stu-id="5dcac-718">**Reported reason**</span></span>
- <span data-ttu-id="5dcac-719">**再スキャンの結果**</span><span class="sxs-lookup"><span data-stu-id="5dcac-719">**Rescan result**</span></span>
- <span data-ttu-id="5dcac-720">**Tags**</span><span class="sxs-lookup"><span data-stu-id="5dcac-720">**Tags**</span></span>

<span data-ttu-id="5dcac-721">分析のために Microsoft にメッセージを送信するには、表からメッセージ エントリを選択し、[分析のために **Microsoft** に送信] をクリックし、ドロップダウン リストから次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="5dcac-721">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="5dcac-722">**クリーンレポート**</span><span class="sxs-lookup"><span data-stu-id="5dcac-722">**Report clean**</span></span>
- <span data-ttu-id="5dcac-723">**フィッシングの報告**</span><span class="sxs-lookup"><span data-stu-id="5dcac-723">**Report phishing**</span></span>
- <span data-ttu-id="5dcac-724">**マルウェアの報告**</span><span class="sxs-lookup"><span data-stu-id="5dcac-724">**Report malware**</span></span>
- <span data-ttu-id="5dcac-725">**[スパムを報告する**]</span><span class="sxs-lookup"><span data-stu-id="5dcac-725">**Report spam**'</span></span>
- <span data-ttu-id="5dcac-726">**トリガー調査**(Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="5dcac-726">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="5dcac-727">これらのレポートを表示するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="5dcac-727">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="5dcac-728">この記事で説明するレポートを表示して使用するには、ポータルで次のいずれかの役割グループのメンバー Microsoft 365 Defenderがあります。</span><span class="sxs-lookup"><span data-stu-id="5dcac-728">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="5dcac-729">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="5dcac-729">**Organization Management**</span></span>
- <span data-ttu-id="5dcac-730">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="5dcac-730">**Security Administrator**</span></span>
- <span data-ttu-id="5dcac-731">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="5dcac-731">**Security Reader**</span></span>
- <span data-ttu-id="5dcac-732">**グローバル リーダー**</span><span class="sxs-lookup"><span data-stu-id="5dcac-732">**Global Reader**</span></span>

<span data-ttu-id="5dcac-733">詳細については、「ポータルの[アクセス許可」をMicrosoft 365 Defenderしてください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-733">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="5dcac-734">**注**: Microsoft 365 管理センター の対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="5dcac-734">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="5dcac-735">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5dcac-735">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="5dcac-736">レポートにデータが表示されない場合は、</span><span class="sxs-lookup"><span data-stu-id="5dcac-736">What if the reports aren't showing data?</span></span>

<span data-ttu-id="5dcac-737">レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5dcac-737">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="5dcac-738">詳細については、「脅威から保護 [する」を参照してください](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcac-738">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5dcac-739">関連項目</span><span class="sxs-lookup"><span data-stu-id="5dcac-739">Related topics</span></span>

[<span data-ttu-id="5dcac-740">EOP でのスパム対策およびマルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="5dcac-740">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="5dcac-741">スマート レポートと分析情報 (Microsoft 365 Defenderポータル)</span><span class="sxs-lookup"><span data-stu-id="5dcac-741">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="5dcac-742">メール フロー レポートをポータルでMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="5dcac-742">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="5dcac-743">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="5dcac-743">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
