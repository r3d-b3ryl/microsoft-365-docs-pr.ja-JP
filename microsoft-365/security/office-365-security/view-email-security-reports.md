---
title: Microsoft 365 Defender ポータルで電子メール セキュリティ レポートを表示する
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
description: 組織の電子メール セキュリティ レポートを検索して使用する方法について学習します。 電子メール セキュリティ レポートは、Microsoft 365 Defender ポータルで利用できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d46aec8601d19234eed8682955ffef27b7e9b467
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985305"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="4d990-104">Microsoft 365 Defender ポータルで電子メール セキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="4d990-104">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4d990-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="4d990-105">**Applies to**</span></span>
- [<span data-ttu-id="4d990-106">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4d990-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4d990-107">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="4d990-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="4d990-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d990-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="4d990-109">Microsoft 365 Defender ポータルでは、Microsoft 365 のスパム対策、マルウェア対策、暗号化機能などの電子メール セキュリティ機能が組織を保護している方法を確認できます。 <https://security.microsoft.com></span><span class="sxs-lookup"><span data-stu-id="4d990-109">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="4d990-110">必要な [アクセス許可を](#what-permissions-are-needed-to-view-these-reports)持っている場合は、[電子メールのレポート] & コラボレーション レポートにアクセスして、Microsoft 365 Defender ポータルでこれらのレポート \>  \> **&表示できます**。</span><span class="sxs-lookup"><span data-stu-id="4d990-110">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d990-111">[コラボレーション レポートの電子メール] **ページ&移動するには、** を開きます <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="4d990-111">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Microsoft 365 Defender &の [コラボレーション レポート] ページにメールを送信する](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="4d990-113">[電子メール と共同作業レポート] ページ& **一部のレポートでは** 、Microsoft Defender が 365 Office必要です。</span><span class="sxs-lookup"><span data-stu-id="4d990-113">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="4d990-114">これらのレポートの詳細については [、「View Defender for Office 365 レポート」を参照してください](view-reports-for-mdo.md)。</span><span class="sxs-lookup"><span data-stu-id="4d990-114">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="4d990-115">メール フローに関連するレポートが Exchange 管理センター (EAC) に追加されました。</span><span class="sxs-lookup"><span data-stu-id="4d990-115">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="4d990-116">これらのレポートの詳細については、「新しい Exchange 管理センターのメール フロー [レポート」を参照してください](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。</span><span class="sxs-lookup"><span data-stu-id="4d990-116">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="4d990-117">侵害されたユーザー レポート</span><span class="sxs-lookup"><span data-stu-id="4d990-117">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="4d990-118">このレポートは、Exchange Online メールボックスを持つ Microsoft 365 組織で利用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-118">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="4d990-119">スタンドアロンの Exchange Online Protection (EOP) 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="4d990-119">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="4d990-120">[**侵害されたユーザー] レポート** には、過去 7 日以内に[疑わしい] または [制限付き] とマークされたユーザー アカウントの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-120">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="4d990-121">これらの状態のどちらかのアカウントは、問題が発生したり、侵害された場合もあります。</span><span class="sxs-lookup"><span data-stu-id="4d990-121">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="4d990-122">頻繁に使用すると、レポートを使用して、疑わしいアカウントや制限付きアカウントのスパイクや傾向を見つけるのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-122">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="4d990-123">侵害されたユーザーの詳細については、「侵害されたメール アカウントへの [応答」を参照してください](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="4d990-123">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![[コラボレーション レポートの電子メール] ページの [侵害&ユーザー] ウィジェット](../../media/compromised-users-report-widget.png)

<span data-ttu-id="4d990-125">集計ビューには過去 90 日間のデータが表示され、詳細ビューには過去 30 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-125">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="4d990-126">Microsoft 365 Defender ポータルでレポートを表示するには、「Reports  \> **Email &コラボレーション** レポート \> **&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="4d990-126">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d990-127">[侵害 **されたユーザー] で、[** 詳細の表示 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-127">On **Compromised users**, click **View details**.</span></span> <span data-ttu-id="4d990-128">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="4d990-128">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="4d990-129">[詳細の **表示]** をクリックすると、[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択して、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-129">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="4d990-130">**日付 (UTC)**:**開始日と\*\*\*\*終了日**。</span><span class="sxs-lookup"><span data-stu-id="4d990-130">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="4d990-131">**アクティビティ**:</span><span class="sxs-lookup"><span data-stu-id="4d990-131">**Activity**:</span></span>
  - <span data-ttu-id="4d990-132">**疑** わしい : ユーザー アカウントが不審なメールを送信し、電子メールの送信を制限される危険性があります。</span><span class="sxs-lookup"><span data-stu-id="4d990-132">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="4d990-133">**制限**: 不審なパターンが多く、ユーザー アカウントが電子メールの送信を制限されています。</span><span class="sxs-lookup"><span data-stu-id="4d990-133">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="4d990-134">フィルター処理が完了したら、[適用] または [**キャンセル] を\*\*\*\*クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-134">When you're finished filtering, click **Apply** or **Cancel**.</span></span>

![[侵害されたユーザー] レポートのレポート ビュー](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="4d990-136">グラフの下の表で、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-136">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="4d990-137">**作成時間**</span><span class="sxs-lookup"><span data-stu-id="4d990-137">**Creation time**</span></span>
- <span data-ttu-id="4d990-138">**[ユーザー ID]**</span><span class="sxs-lookup"><span data-stu-id="4d990-138">**User ID**</span></span>
- <span data-ttu-id="4d990-139">**Action**</span><span class="sxs-lookup"><span data-stu-id="4d990-139">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="4d990-140">Exchange トランスポート ルール レポート</span><span class="sxs-lookup"><span data-stu-id="4d990-140">Exchange transport rule report</span></span>

<span data-ttu-id="4d990-141">**Exchange トランスポート ルール レポートには**、組織内の受信メッセージと送信メッセージに対するメール フロー ルール (トランスポート ルールとも呼ばれる) の影響が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-141">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="4d990-142">Microsoft 365 Defender ポータルでレポートを表示するには、「Reports  \> **Email &コラボレーション** レポート \> **&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="4d990-142">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d990-143">**Exchange トランスポート ルールで、[詳細** の表示 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-143">On **Exchange transport rule**, click **View details**.</span></span> <span data-ttu-id="4d990-144">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="4d990-144">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![[電子メール] コラボレーション レポート ページ& Exchange トランスポート ルール ウィジェット](../../media/transport-rule-report-widget.png)

<span data-ttu-id="4d990-146">[詳細の表示 **] をクリック** すると、次のグラフとデータを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-146">After you click **View details**, the following charts and data are available:</span></span>

- <span data-ttu-id="4d990-147">**Exchange トランスポート ルールによるデータの表示** \>**[方向別のグラフの** 内訳] :このグラフは、メール フロー ルールの影響を受けた受信メッセージと送信メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="4d990-147">**View data by Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>

- <span data-ttu-id="4d990-148">**Exchange トランスポート ルールによるデータの表示** \>**重大度別グラフの内訳**: このグラフは、重大度の高いメッセージ、中程度の重大度、および **低重大度メッセージの数を示** します。</span><span class="sxs-lookup"><span data-stu-id="4d990-148">**View data by Exchange transport rules** \> **Chart breakdown by Severity**: This chart shows the number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="4d990-149">重大度レベルは、ルールのアクションとして設定します **(重大度** レベルまたは _SetAuditSeverity_ でこのルールを監査します)。</span><span class="sxs-lookup"><span data-stu-id="4d990-149">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="4d990-150">詳細については [、「Exchange Online のメール フロー ルールアクション」を参照してください](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="4d990-150">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="4d990-151">**DLP Exchange トランスポート ルールによるデータの表示** \>**方向によるグラフの内訳**: このグラフは、データ損失防止 (DLP) メール フロー ルールの影響を受けた受信メッセージと送信メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="4d990-151">**View data by DLP Exchange transport rules** \> **Chart breakdown by Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

- <span data-ttu-id="4d990-152">**DLP Exchange トランスポート ルールによるデータの表示** \>**重大度別のグラフの** 内訳 : このビューには、DLP メールフロー ルールの影響を受けた重大度の高いメッセージ、中程度の重大度、および低重大度メッセージの数が表示されます。 </span><span class="sxs-lookup"><span data-stu-id="4d990-152">**View data by DLP Exchange transport rules** \> **Chart breakdown by Severity**: This view shows the number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="4d990-153">[Exchange **トランスポート ルールによるデータの表示** ] の選択では、次の情報がグラフの下の詳細テーブルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-153">For **View data by Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="4d990-154">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d990-154">**Date**</span></span>
- <span data-ttu-id="4d990-155">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="4d990-155">**Transport rule**</span></span>
- <span data-ttu-id="4d990-156">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="4d990-156">**Subject**</span></span>
- <span data-ttu-id="4d990-157">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="4d990-157">**Sender address**</span></span>
- <span data-ttu-id="4d990-158">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="4d990-158">**Recipient address**</span></span>
- <span data-ttu-id="4d990-159">**重大度**</span><span class="sxs-lookup"><span data-stu-id="4d990-159">**Severity**</span></span>
- <span data-ttu-id="4d990-160">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="4d990-160">**Direction**</span></span>

<span data-ttu-id="4d990-161">[DLP **Exchange トランスポート ルールによるデータ** の表示] の選択では、次の情報がグラフの下の詳細テーブルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-161">For **View data by DLP Exchange transport rules** selections, the following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="4d990-162">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d990-162">**Date**</span></span>
- <span data-ttu-id="4d990-163">**DLP ポリシー**</span><span class="sxs-lookup"><span data-stu-id="4d990-163">**DLP policy**</span></span>
- <span data-ttu-id="4d990-164">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="4d990-164">**Transport rule**</span></span>
- <span data-ttu-id="4d990-165">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="4d990-165">**Subject**</span></span>
- <span data-ttu-id="4d990-166">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="4d990-166">**Sender address**</span></span>
- <span data-ttu-id="4d990-167">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="4d990-167">**Recipient address**</span></span>
- <span data-ttu-id="4d990-168">**重大度**</span><span class="sxs-lookup"><span data-stu-id="4d990-168">**Severity**</span></span>
- <span data-ttu-id="4d990-169">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="4d990-169">**Direction**</span></span>

<span data-ttu-id="4d990-170">[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-170">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="4d990-171">**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="4d990-171">**Start date** and **End date**</span></span>
- <span data-ttu-id="4d990-172">**方向**:**送信と\*\*\*\*受信**</span><span class="sxs-lookup"><span data-stu-id="4d990-172">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="4d990-173">**重大度**:**重大度が高い、\*\*\*\*中程度の重大度**、**および低重大度**</span><span class="sxs-lookup"><span data-stu-id="4d990-173">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

![Exchange トランスポート ルール レポートのレポート ビュー](../../media/transport-rule-report-report-view.png)

## <a name="mailflow-status-report"></a><span data-ttu-id="4d990-175">メールフローの状態レポート</span><span class="sxs-lookup"><span data-stu-id="4d990-175">Mailflow status report</span></span>

<span data-ttu-id="4d990-176">**Mailflow 状態** レポートは、受信および送信メール、スパム検出、マルウェア、"良い" と識別される電子メール、およびエッジで許可またはブロックされた電子メールに関する情報を示すスマート レポートです。</span><span class="sxs-lookup"><span data-stu-id="4d990-176">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="4d990-177">これはエッジ保護情報を含む唯一のレポートであり、Exchange Online Protection (EOP) による評価のためにサービスに許可される前にブロックされる電子メールの量のみを示します。</span><span class="sxs-lookup"><span data-stu-id="4d990-177">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="4d990-178">メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="4d990-178">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="4d990-179">Microsoft 365 Defender ポータルでレポートを表示するには、「Reports  \> **Email &コラボレーション** レポート \> **&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="4d990-179">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d990-180">[ **メールフローの状態の概要] で、[** 詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-180">On **Mailflow status summary**, click **View details**.</span></span> <span data-ttu-id="4d990-181">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="4d990-181">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![[メール] グループ作業レポート ページの [メールフロー&概要] ウィジェット](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="4d990-183">メールフロー状態レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="4d990-183">Type view for the Mailflow status report</span></span>

<span data-ttu-id="4d990-184">レポートを開いた場合、[種類] **タブ** が既定で選択されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-184">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="4d990-185">既定では、このビューにはグラフと、次のフィルターで構成されたデータ テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d990-185">By default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="4d990-186">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="4d990-186">**Date**: The last 7 days.</span></span>
- <span data-ttu-id="4d990-187">**メールの方向**:</span><span class="sxs-lookup"><span data-stu-id="4d990-187">**Mail direction**:</span></span>
  - <span data-ttu-id="4d990-188">**受信**</span><span class="sxs-lookup"><span data-stu-id="4d990-188">**Inbound**</span></span>
  - <span data-ttu-id="4d990-189">**送信**</span><span class="sxs-lookup"><span data-stu-id="4d990-189">**Outbound**</span></span>
  - <span data-ttu-id="4d990-190">**組織内**: この数は、テナント内のメッセージ 、つまり</span><span class="sxs-lookup"><span data-stu-id="4d990-190">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="4d990-191">送信者 abc@domain.com 受信者に送信 xyz@domain.com (受信および送信とは別 **に\*\*\*\*カウント)**</span><span class="sxs-lookup"><span data-stu-id="4d990-191">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="4d990-192">**種類**:</span><span class="sxs-lookup"><span data-stu-id="4d990-192">**Type**:</span></span>
  - <span data-ttu-id="4d990-193">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="4d990-193">**Good mail**</span></span>
  - <span data-ttu-id="4d990-194">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="4d990-194">**Malware**</span></span>
  - <span data-ttu-id="4d990-195">**スパム**</span><span class="sxs-lookup"><span data-stu-id="4d990-195">**Spam**</span></span>
  - <span data-ttu-id="4d990-196">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="4d990-196">**Edge protection**</span></span>
  - <span data-ttu-id="4d990-197">**ルール メッセージ**</span><span class="sxs-lookup"><span data-stu-id="4d990-197">**Rule messages**</span></span>
  - <span data-ttu-id="4d990-198">**フィッシング詐欺メール**</span><span class="sxs-lookup"><span data-stu-id="4d990-198">**Phishing email**</span></span>
- <span data-ttu-id="4d990-199">**ドメイン**: **すべて**</span><span class="sxs-lookup"><span data-stu-id="4d990-199">**Domain**: **All**</span></span>

<span data-ttu-id="4d990-200">グラフは、Type 値によって **整理** されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-200">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="4d990-201">これらのフィルターは、[フィルター] を **クリックするか** 、グラフの凡例の値をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-201">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="4d990-202">データ テーブルには、次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d990-202">The data table contains the following information:</span></span>

- <span data-ttu-id="4d990-203">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="4d990-203">**Direction**</span></span>
- <span data-ttu-id="4d990-204">**種類**</span><span class="sxs-lookup"><span data-stu-id="4d990-204">**Type**</span></span>
- <span data-ttu-id="4d990-205">**24 時間**</span><span class="sxs-lookup"><span data-stu-id="4d990-205">**24 hours**</span></span>
- <span data-ttu-id="4d990-206">**3 日間**</span><span class="sxs-lookup"><span data-stu-id="4d990-206">**3 days**</span></span>
- <span data-ttu-id="4d990-207">**7 日間**</span><span class="sxs-lookup"><span data-stu-id="4d990-207">**7 days**</span></span>
- <span data-ttu-id="4d990-208">**15 日**</span><span class="sxs-lookup"><span data-stu-id="4d990-208">**15 days**</span></span>
- <span data-ttu-id="4d990-209">**30 日間**</span><span class="sxs-lookup"><span data-stu-id="4d990-209">**30 days**</span></span>

<span data-ttu-id="4d990-210">詳細については、[ **カテゴリの選択] をクリックすると**、次の値から選択できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-210">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="4d990-211">**フィッシングメール**: この選択によって、脅威保護の [状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="4d990-211">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="4d990-212">**電子メール内のマルウェア**: この選択によって、脅威保護 [の状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="4d990-212">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="4d990-213">**スパム検出**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="4d990-213">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="4d990-214">**エッジブロックスパム**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="4d990-214">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="4d990-215">[種類] ビューからエクスポートする</span><span class="sxs-lookup"><span data-stu-id="4d990-215">Export from Type view</span></span>

<span data-ttu-id="4d990-216">詳細ビューでは、1 日のデータのみをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="4d990-216">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="4d990-217">したがって、7 日間データをエクスポートする場合は、7 つの異なるエクスポート アクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d990-217">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="4d990-218">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-218">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="4d990-219">その日のデータに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-219">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![メールフローの状態レポートにビューを入力する](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="4d990-221">メールフロー状態レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="4d990-221">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="4d990-222">[方向] タブ **をクリックすると** 、[種類] ビューの同じ既定 **のフィルター** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-222">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="4d990-223">グラフは、方向の値 **によって整理** されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-223">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="4d990-224">これらのフィルターは、[フィルター] を **クリックするか** 、グラフの凡例の値をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-224">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span> <span data-ttu-id="4d990-225">[種類] ビューの同 **じフィルターが** 使用されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-225">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="4d990-226">データ テーブルには、Type ビューの同じ情報 **が含** まれている。</span><span class="sxs-lookup"><span data-stu-id="4d990-226">The data table contains same information from the **Type** view.</span></span>

<span data-ttu-id="4d990-227">[ **使用可能な選択と動作** の詳細については、カテゴリを選択する] は、[種類] ビューと **同** じです。</span><span class="sxs-lookup"><span data-stu-id="4d990-227">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="4d990-228">方向ビューからエクスポートする</span><span class="sxs-lookup"><span data-stu-id="4d990-228">Export from Direction view</span></span>

<span data-ttu-id="4d990-229">詳細ビューでは、1 日のデータのみをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="4d990-229">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="4d990-230">したがって、7 日間データをエクスポートする場合は、7 つの異なるエクスポート アクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d990-230">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="4d990-231">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-231">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="4d990-232">その日のデータに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-232">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![メールフロー状態レポートの方向ビュー](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="4d990-234">メールフロー状態レポートのファネル ビュー</span><span class="sxs-lookup"><span data-stu-id="4d990-234">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="4d990-235">[ **ファネル** ] ビューには、Microsoft の電子メール脅威防止機能が組織内の受信メールと送信メールをフィルター処理する方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-235">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="4d990-236">電子メールの総数と、エッジ保護、マルウェア対策、フィッシング対策、スパム対策、スプーフィング対策などの構成済みの脅威保護機能が、この数に与える影響の詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="4d990-236">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="4d990-237">[ファネル] タブ **を** クリックすると、既定では、次のフィルターで構成されたグラフとデータ テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-237">If you click the **Funnel** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="4d990-238">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="4d990-238">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="4d990-239">**方向**:</span><span class="sxs-lookup"><span data-stu-id="4d990-239">**Direction**:</span></span>

  - <span data-ttu-id="4d990-240">**受信**</span><span class="sxs-lookup"><span data-stu-id="4d990-240">**Inbound**</span></span>
  - <span data-ttu-id="4d990-241">**送信**</span><span class="sxs-lookup"><span data-stu-id="4d990-241">**Outbound**</span></span>
  - <span data-ttu-id="4d990-242">**組織内**: この数は、テナント内で送信されるメッセージを示します。つまり、送信者は abc@domain.com に送信 xyz@domain.com (受信と送信とは別にカウントされます)。</span><span class="sxs-lookup"><span data-stu-id="4d990-242">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="4d990-243">集計ビューとデータ テーブル ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="4d990-243">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="4d990-244">[フィルター] **をクリック** すると、グラフとデータ テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-244">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="4d990-245">このグラフは、次の方法で整理されたメール数を示しています。</span><span class="sxs-lookup"><span data-stu-id="4d990-245">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="4d990-246">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="4d990-246">**Total email**</span></span>
- <span data-ttu-id="4d990-247">**エッジ保護後のメール**</span><span class="sxs-lookup"><span data-stu-id="4d990-247">**Email after edge protection**</span></span>
- <span data-ttu-id="4d990-248">**トランスポート ルールの後のメール** (メール フロー ルール)</span><span class="sxs-lookup"><span data-stu-id="4d990-248">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="4d990-249">**マルウェア対策、ファイル評価、ファイルの種類ブロック後のメール**</span><span class="sxs-lookup"><span data-stu-id="4d990-249">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="4d990-250">**フィッシング対策、URL 評価、ブランド偽装、スプーフィング対策の後のメール**</span><span class="sxs-lookup"><span data-stu-id="4d990-250">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="4d990-251">**スパム対策、バルク メール フィルター処理後のメール**</span><span class="sxs-lookup"><span data-stu-id="4d990-251">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="4d990-252">**ユーザーとドメインの偽装後のメール**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d990-252">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="4d990-253">**ファイルと URL の削除後のメール**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d990-253">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="4d990-254">**配信後の保護後に良性として検出された電子メール (URL クリック時間保護)**</span><span class="sxs-lookup"><span data-stu-id="4d990-254">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="4d990-255"><sup>\*</sup>Defender for Office 365のみ</span><span class="sxs-lookup"><span data-stu-id="4d990-255"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="4d990-256">EOP または Defender でフィルター処理されたメールを個別Office 365表示するには、グラフの凡例の値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4d990-256">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="4d990-257">データ テーブルには、降順に表示される次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d990-257">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="4d990-258">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d990-258">**Date**</span></span>
- <span data-ttu-id="4d990-259">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="4d990-259">**Total email**</span></span>
- <span data-ttu-id="4d990-260">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="4d990-260">**Edge protection**</span></span>
- <span data-ttu-id="4d990-261">**マルウェア対策、ファイル評価、ファイルの種類ブロック**:</span><span class="sxs-lookup"><span data-stu-id="4d990-261">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="4d990-262">**ファイル評価**: 他の Microsoft のお客様が添付ファイルを識別するためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4d990-262">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="4d990-263">**ファイルの種類のブロック**: メッセージで識別された悪意のあるファイルの種類によってフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4d990-263">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="4d990-264">**フィッシング対策、URL レピュテーション、ブランド偽装、スプーフィング対策**:</span><span class="sxs-lookup"><span data-stu-id="4d990-264">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="4d990-265">**URL レピュ** テーション : 他の Microsoft のお客様による URL の識別のためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4d990-265">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="4d990-266">**ブランド偽装**: よく知られているブランド偽装送信者からのメッセージが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4d990-266">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="4d990-267">**スプーフィング** 対策: 受信者が属するドメイン、またはメッセージ送信者が所有していないドメインをスプーフィングしようとするメッセージが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4d990-267">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="4d990-268">**スパム対策、バルク メール フィルター**:</span><span class="sxs-lookup"><span data-stu-id="4d990-268">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="4d990-269">**バルク メール フィルター :** スパム対策ポリシーの一括不平レベル (BCL) しきい値に基づいてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4d990-269">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="4d990-270">**ユーザーとドメインの偽装 (Defender for Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="4d990-270">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="4d990-271">**ユーザー偽装**: フィッシング対策ポリシーの偽装保護設定で定義されているユーザー (メッセージ送信者) を偽装しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4d990-271">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="4d990-272">**ドメイン偽装**: フィッシング対策ポリシーの偽装保護設定で定義されているドメインを偽装しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4d990-272">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="4d990-273">**ファイルと URL のデトレーション (Defender for Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="4d990-273">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="4d990-274">**ファイルの削除**: 添付ファイル ポリシーでフィルターセーフメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4d990-274">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="4d990-275">**URL の削除**: リンク ポリシーでフィルターセーフメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4d990-275">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="4d990-276">**配信後の保護と ZAP (ATP)、または ZAP (EOP)**: マルウェア、スパム、フィッシングのゼロ時間自動削除 (ZAP)。</span><span class="sxs-lookup"><span data-stu-id="4d990-276">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="4d990-277">データ テーブルで行を選択すると、メール数の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-277">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="4d990-278">ファネル ビューからエクスポートする</span><span class="sxs-lookup"><span data-stu-id="4d990-278">Export from Funnel view</span></span>

<span data-ttu-id="4d990-279">[オプション] で **[エクスポート]** **をクリック** すると、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-279">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="4d990-280">**概要 (最大で過去 90 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="4d990-280">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="4d990-281">**詳細 (最大で過去 30 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="4d990-281">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="4d990-282">[ **日付] で** 範囲を選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-282">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="4d990-283">現在のフィルターのデータは、特定のファイルに.csvされます。</span><span class="sxs-lookup"><span data-stu-id="4d990-283">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="4d990-284">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-284">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="4d990-285">データに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-285">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![メールフロー状態レポートのファネル ビュー](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="4d990-287">メールフローの状態レポートの技術ビュー</span><span class="sxs-lookup"><span data-stu-id="4d990-287">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="4d990-288">Tech **ビューは、** ファネル **ビューに** 似ています。構成済みの脅威保護機能の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="4d990-288">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="4d990-289">グラフから、脅威保護の異なる段階でメッセージがどのように分類されるのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-289">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="4d990-290">[Tech view] **タブを** クリックすると、既定では、このビューにはグラフと、次のフィルターで構成されたデータ テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d990-290">If you click the **Tech view** tab, by default, this view contains a chart and a data table that's configured with the following filters:</span></span>

- <span data-ttu-id="4d990-291">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="4d990-291">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="4d990-292">**方向**:</span><span class="sxs-lookup"><span data-stu-id="4d990-292">**Direction**:</span></span>

  - <span data-ttu-id="4d990-293">**受信**</span><span class="sxs-lookup"><span data-stu-id="4d990-293">**Inbound**</span></span>
  - <span data-ttu-id="4d990-294">**送信**</span><span class="sxs-lookup"><span data-stu-id="4d990-294">**Outbound**</span></span>
  - <span data-ttu-id="4d990-295">**組織内**: この数は、テナント内のメッセージ 、つまり</span><span class="sxs-lookup"><span data-stu-id="4d990-295">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="4d990-296">送信者 abc@domain.com 受信者に送信 xyz@domain.com (受信および送信とは別にカウントされます)</span><span class="sxs-lookup"><span data-stu-id="4d990-296">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="4d990-297">集計ビューとデータ テーブル ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="4d990-297">The aggregate view and data table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="4d990-298">[フィルター] **をクリック** すると、グラフとデータ テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-298">If you click **Filter**, you can filter both the chart and the data table.</span></span>

<span data-ttu-id="4d990-299">このグラフには、次のカテゴリに分類されたメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-299">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="4d990-300">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="4d990-300">**Total email**</span></span>
- <span data-ttu-id="4d990-301">**エッジ許可** と **フィルター処理されたエッジ**</span><span class="sxs-lookup"><span data-stu-id="4d990-301">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="4d990-302">**トランスポート ルールの許可** と **トランスポート ルールのフィルター** 処理 (メール フロー ルール)</span><span class="sxs-lookup"><span data-stu-id="4d990-302">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="4d990-303">**マルウェアではない\*\*\*\*、セーフ添付ファイルの検出、** <sup>\*</sup> **マルウェア対策エンジンの検出**</span><span class="sxs-lookup"><span data-stu-id="4d990-303">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="4d990-304">**フィッシング** **、DMARC 障害、\*\*\*\*偽装検出、ス** プーフィング <sup>\*</sup> **検出**、**およびフィッシングの検出を行う**</span><span class="sxs-lookup"><span data-stu-id="4d990-304">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="4d990-305">**URL のデトレーションと URL の** デトレーション **検出による検出なし**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d990-305">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="4d990-306">**スパムとスパム\*\*\*\*ではない**</span><span class="sxs-lookup"><span data-stu-id="4d990-306">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="4d990-307">**悪意のあるメール以外の電子\*\*\*\*メール、セーフリンクの検出** <sup>\*</sup> 、**および ZAP**</span><span class="sxs-lookup"><span data-stu-id="4d990-307">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="4d990-308"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4d990-308"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="4d990-309">グラフ内のカテゴリにカーソルを合わせると、そのカテゴリ内のメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-309">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="4d990-310">データ テーブルには、降順に表示される次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d990-310">The data table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="4d990-311">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d990-311">**Date**</span></span>
- <span data-ttu-id="4d990-312">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="4d990-312">**Total email**</span></span>
- <span data-ttu-id="4d990-313">**フィルター処理されたエッジ**</span><span class="sxs-lookup"><span data-stu-id="4d990-313">**Edge filtered**</span></span>
- <span data-ttu-id="4d990-314">**ルール メッセージ**: メール フロー ルール (トランスポート ルールとも呼ばれる) が原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4d990-314">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="4d990-315">**マルウェア対策エンジン、セーフ\*\*\*\*添付** <sup>\*</sup> ファイル:</span><span class="sxs-lookup"><span data-stu-id="4d990-315">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="4d990-316">**DMARC、 偽装** <sup>\*</sup> 、 ス **プーフィング**、**フィッシング フィルター**:</span><span class="sxs-lookup"><span data-stu-id="4d990-316">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="4d990-317">**DMARC**: DMARC 認証チェックに失敗したメッセージが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="4d990-317">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="4d990-318">**URL のデトレーション検出**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d990-318">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="4d990-319">**フィルター処理されたスパム対策**</span><span class="sxs-lookup"><span data-stu-id="4d990-319">**Anti-spam filtered**</span></span>
- <span data-ttu-id="4d990-320">**ZAP が削除されました**</span><span class="sxs-lookup"><span data-stu-id="4d990-320">**ZAP removed**</span></span>
- <span data-ttu-id="4d990-321">**リンクによるセーフ検出**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d990-321">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="4d990-322"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4d990-322"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="4d990-323">データ テーブルで行を選択すると、メール数の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-323">If you select a row in the data table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="4d990-324">Tech ビューからのエクスポート</span><span class="sxs-lookup"><span data-stu-id="4d990-324">Export from Tech view</span></span>

<span data-ttu-id="4d990-325">[エクスポート] **をクリックすると**、[ **オプション] で** 、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-325">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="4d990-326">**概要 (最大で過去 90 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="4d990-326">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="4d990-327">**詳細 (最大で過去 30 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="4d990-327">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="4d990-328">[ **日付] で** 範囲を選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-328">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="4d990-329">現在のフィルターのデータは、特定のファイルに.csvされます。</span><span class="sxs-lookup"><span data-stu-id="4d990-329">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="4d990-330">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-330">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="4d990-331">データに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-331">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![メールフロー状態レポートの技術ビュー](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="4d990-333">マルウェア検出レポート</span><span class="sxs-lookup"><span data-stu-id="4d990-333">Malware detections report</span></span>

<span data-ttu-id="4d990-334">[**マルウェア検出] レポート レポートには**、受信および送信電子メール メッセージ (マルウェアが受信または EOP によって検出Exchange Online Protection情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-334">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="4d990-335">EOP のマルウェア保護の詳細については、「EOP の [マルウェア対策保護」を参照してください](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="4d990-335">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="4d990-336">集計ビュー フィルターでは 90 日間、詳細テーブル フィルターでは 10 日間のみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-336">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="4d990-337">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="4d990-337">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d990-338">[メール **で検出されたマルウェア] で、[** 詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-338">On **Malware detected in email**, click **View details**.</span></span> <span data-ttu-id="4d990-339">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="4d990-339">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![[メール と共同作業レポート] ページの電子メール ウィジェット&検出](../../media/malware-detections-widget.png)

<span data-ttu-id="4d990-341">[詳細の表示 **] をクリック** すると、[フィルター] をクリックして、グラフと詳細テーブル **の両方** をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-341">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting:</span></span>

- <span data-ttu-id="4d990-342">**日付**: **開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4d990-342">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="4d990-343">**方向**:**受信および\*\*\*\*送信**</span><span class="sxs-lookup"><span data-stu-id="4d990-343">**Direction**: **Inbound** and **Outbound**</span></span>

![電子メール レポートのマルウェア検出のレポート ビュー](../../media/malware-detections-report-view.png)

<span data-ttu-id="4d990-345">グラフの下の詳細テーブルで、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-345">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="4d990-346">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d990-346">**Date**</span></span>
- <span data-ttu-id="4d990-347">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="4d990-347">**Sender address**</span></span>
- <span data-ttu-id="4d990-348">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="4d990-348">**Recipient address**</span></span>
- <span data-ttu-id="4d990-349">**メッセージ ID**: メッセージ ヘッダーの **[Message-ID** ヘッダー] フィールドで使用できます。一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4d990-349">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="4d990-350">値の例は `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次のようになります (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="4d990-350">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="4d990-351">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="4d990-351">**Subject**</span></span>
- <span data-ttu-id="4d990-352">**Filename**</span><span class="sxs-lookup"><span data-stu-id="4d990-352">**Filename**</span></span>
- <span data-ttu-id="4d990-353">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="4d990-353">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="4d990-354">メール遅延レポート</span><span class="sxs-lookup"><span data-stu-id="4d990-354">Mail latency report</span></span>

<span data-ttu-id="4d990-355">Defender **for Office 365** のメール待機時間レポートには、組織内で発生したメール配信と発Office 365に関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="4d990-355">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="4d990-356">詳細については、「メール遅延 [レポート」を参照してください](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="4d990-356">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="4d990-357">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="4d990-357">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="4d990-358">スパム **検出レポートは** 、2021 年 6 月 30 日に削除されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-358">The **Spam detections report** will go away on June 30, 2021.</span></span> <span data-ttu-id="4d990-359">脅威保護の状態レポートでも同 [じ情報を使用できます](#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="4d990-359">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="4d990-360">スプーフィング検出レポート</span><span class="sxs-lookup"><span data-stu-id="4d990-360">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="4d990-361">この記事で説明するように改善されたスプーフィング検出レポートはプレビューで、変更される可能性があります。また、すべての組織で利用できるとは限られません。</span><span class="sxs-lookup"><span data-stu-id="4d990-361">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="4d990-362">レポートの以前のバージョンでは、良いメール **だけが表示され** 、スパム **としてキャッチされます**。</span><span class="sxs-lookup"><span data-stu-id="4d990-362">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="4d990-363">ス **プーフィング検出レポート** には、スプーフィングによってブロックまたは許可されたメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-363">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="4d990-364">スプーフィングの詳細については、「EOP でのスプーフィング防止 [保護」を参照してください](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="4d990-364">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="4d990-365">レポートの集計ビューでは 45 日間のフィルター処理が可能ですが、詳細ビューでは 10 日間のフィルター <sup>\*</sup> 処理のみ可能です。</span><span class="sxs-lookup"><span data-stu-id="4d990-365">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="4d990-366"><sup>\*</sup> 最終的には、最大 90 日間のフィルター処理を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-366"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="4d990-367">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="4d990-367">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d990-368">[ス **プーフィングの検出] で**、[詳細の表示 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-368">On **Spoof detections**, click **View details**.</span></span> <span data-ttu-id="4d990-369">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/SpoofMailReportV2> 。</span><span class="sxs-lookup"><span data-stu-id="4d990-369">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![[メール と共同作業レポート] ページ&スプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

<span data-ttu-id="4d990-371">グラフの 1 日 (データ ポイント) にカーソルを合わせると、スプーフィングされたメッセージの検出数と理由を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-371">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="4d990-372">[詳細の **表示] をクリック** すると、[フィルター] をクリックして、次の値の 1 つ以上を選択して、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-372">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="4d990-373">**日付**: **開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4d990-373">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="4d990-374">**結果**:</span><span class="sxs-lookup"><span data-stu-id="4d990-374">**Result**:</span></span>
  - <span data-ttu-id="4d990-375">**Pass**</span><span class="sxs-lookup"><span data-stu-id="4d990-375">**Pass**</span></span>
  - <span data-ttu-id="4d990-376">**Fail/失敗**</span><span class="sxs-lookup"><span data-stu-id="4d990-376">**Fail**</span></span>
  - <span data-ttu-id="4d990-377">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="4d990-377">**SoftPass**</span></span>
  - <span data-ttu-id="4d990-378">**なし**</span><span class="sxs-lookup"><span data-stu-id="4d990-378">**None**</span></span>
  - <span data-ttu-id="4d990-379">**その他**</span><span class="sxs-lookup"><span data-stu-id="4d990-379">**Other**</span></span>
- <span data-ttu-id="4d990-380">**スプーフィングの** 種類 :**内部と\*\*\*\*外部**</span><span class="sxs-lookup"><span data-stu-id="4d990-380">**Spoof type**: **Internal** and **External**</span></span>

![[メール レポートのスプーフィング] ページ (Microsoft 365 Defender ポータル)](../../media/spoof-detections-report-page.png)

<span data-ttu-id="4d990-382">グラフの下の表で、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-382">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="4d990-383">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d990-383">**Date**</span></span>
- <span data-ttu-id="4d990-384">**スプーフィングされたユーザー**</span><span class="sxs-lookup"><span data-stu-id="4d990-384">**Spoofed user**</span></span>
- <span data-ttu-id="4d990-385">**インフラストラクチャの送信**</span><span class="sxs-lookup"><span data-stu-id="4d990-385">**Sending infrastructure**</span></span>
- <span data-ttu-id="4d990-386">**スプーフィングの種類**</span><span class="sxs-lookup"><span data-stu-id="4d990-386">**Spoof type**</span></span>
- <span data-ttu-id="4d990-387">**結果**</span><span class="sxs-lookup"><span data-stu-id="4d990-387">**Result**</span></span>
- <span data-ttu-id="4d990-388">**結果コード**</span><span class="sxs-lookup"><span data-stu-id="4d990-388">**Result code**</span></span>
- <span data-ttu-id="4d990-389">**SPF**</span><span class="sxs-lookup"><span data-stu-id="4d990-389">**SPF**</span></span>
- <span data-ttu-id="4d990-390">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="4d990-390">**DKIM**</span></span>
- <span data-ttu-id="4d990-391">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="4d990-391">**DMARC**</span></span>
- <span data-ttu-id="4d990-392">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="4d990-392">**Message count**</span></span>

<span data-ttu-id="4d990-393">複合認証結果コードの詳細については、「スパム対策メッセージ ヘッダー」を参照[Microsoft 365。](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="4d990-393">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="4d990-394">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="4d990-394">Threat protection status report</span></span>

<span data-ttu-id="4d990-395">脅威 **保護の状態レポート** は、EOP と Defender の両方Office 365。ただし、レポートには異なるデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="4d990-395">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="4d990-396">たとえば、EOP のお客様は、電子メールで検出されたマルウェアに関する情報を表示できますが[、SharePoint、OneDrive、](mdo-for-spo-odb-and-teams.md)および Microsoft Teams の セーフ 添付ファイルによって検出された悪意のあるファイルに関する情報は表示できません。</span><span class="sxs-lookup"><span data-stu-id="4d990-396">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="4d990-397">このレポートには、マルウェア対策エンジンによってブロックされたファイルや Web サイト アドレス (URL)、ゼロ時間自動削除[(ZAP)、セーフ](zero-hour-auto-purge.md)[リンク、セーフ](safe-links.md)[添付](safe-attachments.md)ファイル、フィッシング対策ポリシーの偽装保護機能などの Office 365 機能の Defender などの悪意のあるコンテンツを含[](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)む電子メール メッセージの数が提供されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-397">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="4d990-398">この情報を使用して、傾向を特定したり、組織のポリシーで調整が必要かどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-398">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="4d990-399">**注**: メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="4d990-399">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="4d990-400">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="4d990-400">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d990-401">[脅威 **保護の状態] で、[** 詳細の表示 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-401">On **Threat protection status**, click **View details**.</span></span> <span data-ttu-id="4d990-402">レポートに直接移動するには、次のいずれかの URL を開きます。</span><span class="sxs-lookup"><span data-stu-id="4d990-402">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="4d990-403">Defender for Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="4d990-403">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="4d990-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="4d990-404">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![[メール] グループの [コラボレーション レポート] ページ&の脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="4d990-406">既定では、[詳細の表示] **をクリック** すると、グラフに過去 7 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-406">By default, after you click **View details**, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="4d990-407">[フィルター] **をクリック** すると、90 日間の日付範囲を選択できます (試用版サブスクリプションは 30 日間に制限される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="4d990-407">If you click **Filter**, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="4d990-408">詳細テーブルでは、30 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="4d990-408">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="4d990-409">使用可能なビューについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="4d990-409">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="4d990-410">概要でデータを表示する</span><span class="sxs-lookup"><span data-stu-id="4d990-410">View data by Overview</span></span>

![脅威保護の状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="4d990-412">[概要で **データを表示]** ビューでは、次の検出情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-412">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="4d990-413">**電子メール マルウェア**</span><span class="sxs-lookup"><span data-stu-id="4d990-413">**Email malware**</span></span>
- <span data-ttu-id="4d990-414">**メールフィッシング**</span><span class="sxs-lookup"><span data-stu-id="4d990-414">**Email phish**</span></span>
- <span data-ttu-id="4d990-415">**コンテンツ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="4d990-415">**Content malware**</span></span>

<span data-ttu-id="4d990-416">グラフの下に詳細テーブルはありません。</span><span class="sxs-lookup"><span data-stu-id="4d990-416">No details table is available below the chart.</span></span>

<span data-ttu-id="4d990-417">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-417">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="4d990-418">**日付**: **開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4d990-418">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="4d990-419">**検出**: **電子メール マルウェア**、 **メールフィッシング**、 **またはコンテンツ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="4d990-419">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="4d990-420">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="4d990-420">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="4d990-421">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="4d990-421">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="4d990-422">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="4d990-422">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="4d990-423">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="4d990-423">**Direction**</span></span>
- <span data-ttu-id="4d990-424">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="4d990-424">**Domain**</span></span>
- <span data-ttu-id="4d990-425">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="4d990-425">**Policy type**</span></span>

<span data-ttu-id="4d990-426">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-426">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="4d990-427">検出テクノロジによってメール \> フィッシングとグラフの内訳でデータを表示する</span><span class="sxs-lookup"><span data-stu-id="4d990-427">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![脅威保護状態レポートでのフィッシングメールの検出テクノロジ ビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="4d990-429">[**メール フィッシングによるデータの表示 \> ] ビューと\*\*\*\*[検出** テクノロジによるグラフの内訳] ビューでは、次の情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-429">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="4d990-430">**URL 悪意のある評判**: Defender から生成された悪意のある URL レピュテーションOffice 365他のユーザーのMicrosoft 365 <sup>\*</sup> です。</span><span class="sxs-lookup"><span data-stu-id="4d990-430">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="4d990-431">**高度なフィルター**: 機械学習に基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="4d990-431">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="4d990-432">**一般的なフィルター**: アナリスト ルールに基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="4d990-432">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="4d990-433">**組織内のスプーフィング**: 送信者が受信者ドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="4d990-433">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="4d990-434">**スプーフィング外部ドメイン**: 送信者が他のドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="4d990-434">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="4d990-435">**スプーフィング DMARC**: メッセージの DMARC 認証エラー。</span><span class="sxs-lookup"><span data-stu-id="4d990-435">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="4d990-436">**偽装ブランド**: 送信者に基づく既知のブランドの偽装。</span><span class="sxs-lookup"><span data-stu-id="4d990-436">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="4d990-437">**複合分析の検出**</span><span class="sxs-lookup"><span data-stu-id="4d990-437">**Mixed analysis detection**</span></span>
- <span data-ttu-id="4d990-438">**ファイルの評価**</span><span class="sxs-lookup"><span data-stu-id="4d990-438">**File reputation**</span></span>
- <span data-ttu-id="4d990-439">**指紋の一致**</span><span class="sxs-lookup"><span data-stu-id="4d990-439">**Fingerprint matching**</span></span>
- <span data-ttu-id="4d990-440">**URL のデトレーション評価**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d990-440">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="4d990-441">**URL のデトナレーション**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d990-441">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="4d990-442">**偽装ユーザー**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d990-442">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="4d990-443">**偽装ドメイン** <sup>\*</sup> : 顧客が所有または定義するドメインの偽装。</span><span class="sxs-lookup"><span data-stu-id="4d990-443">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="4d990-444">**メールボックス インテリジェンスの偽装**: 管理者によって定義されたユーザー、またはメールボックス インテリジェンスによって学習された <sup>\*</sup> ユーザーの偽装。</span><span class="sxs-lookup"><span data-stu-id="4d990-444">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="4d990-445">**ファイルのデトレーション**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d990-445">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="4d990-446">**キャンペーン**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d990-446">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="4d990-447">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-447">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="4d990-448">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d990-448">**Date**</span></span>
- <span data-ttu-id="4d990-449">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="4d990-449">**Subject**</span></span>
- <span data-ttu-id="4d990-450">**送信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-450">**Sender**</span></span>
- <span data-ttu-id="4d990-451">**受信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-451">**Recipients**</span></span>
- <span data-ttu-id="4d990-452">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="4d990-452">**Detected by**</span></span>
- <span data-ttu-id="4d990-453">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="4d990-453">**Delivery Status**</span></span>
- <span data-ttu-id="4d990-454">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="4d990-454">**Source of Compromise**</span></span>
- <span data-ttu-id="4d990-455">**Tags**</span><span class="sxs-lookup"><span data-stu-id="4d990-455">**Tags**</span></span>

<span data-ttu-id="4d990-456">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-456">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="4d990-457">**日付**: **開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4d990-457">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="4d990-458">**検出**</span><span class="sxs-lookup"><span data-stu-id="4d990-458">**Detection**</span></span>
- <span data-ttu-id="4d990-459">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="4d990-459">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="4d990-460">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="4d990-460">**Direction**</span></span>
- <span data-ttu-id="4d990-461">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="4d990-461">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="4d990-462">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="4d990-462">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="4d990-463">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="4d990-463">**Domain**</span></span>
- <span data-ttu-id="4d990-464">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="4d990-464">**Policy type**</span></span>
- <span data-ttu-id="4d990-465">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="4d990-465">**Policy name** (details table only)</span></span>
- <span data-ttu-id="4d990-466">**受信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-466">**Recipients**</span></span>

<span data-ttu-id="4d990-467">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-467">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="4d990-468">検出テクノロジによってメール \> マルウェアとグラフの内訳でデータを表示する</span><span class="sxs-lookup"><span data-stu-id="4d990-468">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![脅威保護状態レポートのマルウェアの検出テクノロジ ビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="4d990-470">[電子メール **マルウェアによる \> データの** 表示] ビューと **[検出** テクノロジによるグラフの内訳] ビューでは、次の情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-470">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="4d990-471">**ファイルの削除** <sup>\*</sup> : 添付ファイルセーフ検出。</span><span class="sxs-lookup"><span data-stu-id="4d990-471">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="4d990-472">**ファイルの削除評価**: すべての悪意のあるファイルレピュテーションが Defender によって生成され、Office 365 <sup>\*</sup> されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-472">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="4d990-473">**ファイルの評価**</span><span class="sxs-lookup"><span data-stu-id="4d990-473">**File reputation**</span></span>
- <span data-ttu-id="4d990-474">**マルウェア対策エンジン** <sup>\*</sup> : マルウェア対策エンジンからの検出。</span><span class="sxs-lookup"><span data-stu-id="4d990-474">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="4d990-475">**マルウェア対策ポリシー ファイルの種類ブロック**: これらは、メッセージで識別された悪意のあるファイルの種類によってフィルター処理された電子メール メッセージです。</span><span class="sxs-lookup"><span data-stu-id="4d990-475">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="4d990-476">**URL に悪意があるとする評価**</span><span class="sxs-lookup"><span data-stu-id="4d990-476">**URL malicious reputation**</span></span>
- <span data-ttu-id="4d990-477">**URL のデトネーション**</span><span class="sxs-lookup"><span data-stu-id="4d990-477">**URL detonation**</span></span>
- <span data-ttu-id="4d990-478">**URL のデトネーションの評価**</span><span class="sxs-lookup"><span data-stu-id="4d990-478">**URL detonation reputation**</span></span>
- <span data-ttu-id="4d990-479">**キャンペーン**</span><span class="sxs-lookup"><span data-stu-id="4d990-479">**Campaign**</span></span>

<span data-ttu-id="4d990-480">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-480">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="4d990-481">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d990-481">**Date**</span></span>
- <span data-ttu-id="4d990-482">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="4d990-482">**Subject**</span></span>
- <span data-ttu-id="4d990-483">**送信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-483">**Sender**</span></span>
- <span data-ttu-id="4d990-484">**受信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-484">**Recipients**</span></span>
- <span data-ttu-id="4d990-485">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="4d990-485">**Detected by**</span></span>
- <span data-ttu-id="4d990-486">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="4d990-486">**Delivery Status**</span></span>
- <span data-ttu-id="4d990-487">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="4d990-487">**Source of Compromise**</span></span>
- <span data-ttu-id="4d990-488">**Tags**</span><span class="sxs-lookup"><span data-stu-id="4d990-488">**Tags**</span></span>

<span data-ttu-id="4d990-489">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-489">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="4d990-490">**日付**: **開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4d990-490">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="4d990-491">**検出**</span><span class="sxs-lookup"><span data-stu-id="4d990-491">**Detection**</span></span>
- <span data-ttu-id="4d990-492">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="4d990-492">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="4d990-493">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="4d990-493">**Direction**</span></span>
- <span data-ttu-id="4d990-494">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="4d990-494">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="4d990-495">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="4d990-495">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="4d990-496">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="4d990-496">**Domain**</span></span>
- <span data-ttu-id="4d990-497">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="4d990-497">**Policy type**</span></span>
- <span data-ttu-id="4d990-498">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="4d990-498">**Policy name** (details table only)</span></span>
- <span data-ttu-id="4d990-499">**受信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-499">**Recipients**</span></span>

<span data-ttu-id="4d990-500">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-500">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="4d990-501">ポリシーの種類別のグラフの内訳とメールフィッシングによるデータの表示 \> またはメール マルウェアによるデータの \> 表示</span><span class="sxs-lookup"><span data-stu-id="4d990-501">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![脅威保護状態レポートのフィッシングメールまたはマルウェアメールのポリシーの種類の表示](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="4d990-503">[ポリシーの **種類別グラフ] ビューと**[メール フィッシングによるデータの表示] ビューまたは [メール マルウェアによるデータの表示] ビューでは、次の情報がグラフに表示されます。 **\>** **\>**</span><span class="sxs-lookup"><span data-stu-id="4d990-503">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="4d990-504">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="4d990-504">**Anti-malware**</span></span>
- <span data-ttu-id="4d990-505">**セーフ添付ファイル**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="4d990-505">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="4d990-506">**フィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="4d990-506">**Anti-phish**</span></span>
- <span data-ttu-id="4d990-507">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="4d990-507">**Anti-spam**</span></span>
- <span data-ttu-id="4d990-508">**メール フロー ルール** (トランスポート ルールとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="4d990-508">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="4d990-509">**Others**</span><span class="sxs-lookup"><span data-stu-id="4d990-509">**Others**</span></span>

<span data-ttu-id="4d990-510">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-510">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="4d990-511">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d990-511">**Date**</span></span>
- <span data-ttu-id="4d990-512">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="4d990-512">**Subject**</span></span>
- <span data-ttu-id="4d990-513">**送信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-513">**Sender**</span></span>
- <span data-ttu-id="4d990-514">**受信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-514">**Recipients**</span></span>
- <span data-ttu-id="4d990-515">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="4d990-515">**Detected by**</span></span>
- <span data-ttu-id="4d990-516">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="4d990-516">**Delivery Status**</span></span>
- <span data-ttu-id="4d990-517">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="4d990-517">**Source of Compromise**</span></span>
- <span data-ttu-id="4d990-518">**Tags**</span><span class="sxs-lookup"><span data-stu-id="4d990-518">**Tags**</span></span>

<span data-ttu-id="4d990-519">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-519">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="4d990-520">**日付**: **開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4d990-520">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="4d990-521">**検出**</span><span class="sxs-lookup"><span data-stu-id="4d990-521">**Detection**</span></span>
- <span data-ttu-id="4d990-522">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="4d990-522">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="4d990-523">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="4d990-523">**Direction**</span></span>
- <span data-ttu-id="4d990-524">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="4d990-524">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="4d990-525">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="4d990-525">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="4d990-526">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="4d990-526">**Domain**</span></span>
- <span data-ttu-id="4d990-527">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="4d990-527">**Policy type**</span></span>
- <span data-ttu-id="4d990-528">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="4d990-528">**Policy name** (details table only)</span></span>
- <span data-ttu-id="4d990-529">**受信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-529">**Recipients**</span></span>

<span data-ttu-id="4d990-530">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-530">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="4d990-531">[配信の状態] と [メールフィッシングによるデータの表示] または [ \> メール マルウェアによるデータの表示] によるグラフの \> 内訳</span><span class="sxs-lookup"><span data-stu-id="4d990-531">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![脅威保護状態レポートのフィッシングメールとマルウェアメールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="4d990-533">[配信 **状態別グラフの内訳]** ビューと [メール フィッシングによるデータの表示] ビューまたは [メール マルウェアによるデータの表示] ビューでは、次の情報がグラフに表示されます。 **\>** **\>**</span><span class="sxs-lookup"><span data-stu-id="4d990-533">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="4d990-534">**ホストされたメールボックス: 受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="4d990-534">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="4d990-535">**ホストされたメールボックス: 迷惑メール**</span><span class="sxs-lookup"><span data-stu-id="4d990-535">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="4d990-536">**ホストされたメールボックス: カスタム フォルダー**</span><span class="sxs-lookup"><span data-stu-id="4d990-536">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="4d990-537">**ホストされたメールボックス: 削除済みアイテム**</span><span class="sxs-lookup"><span data-stu-id="4d990-537">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="4d990-538">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="4d990-538">**Forwarded**</span></span>
- <span data-ttu-id="4d990-539">**オンプレミス サーバー: 配信**</span><span class="sxs-lookup"><span data-stu-id="4d990-539">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="4d990-540">**検疫**</span><span class="sxs-lookup"><span data-stu-id="4d990-540">**Quarantine**</span></span>
- <span data-ttu-id="4d990-541">**配信に失敗しました**</span><span class="sxs-lookup"><span data-stu-id="4d990-541">**Delivery failed**</span></span>
- <span data-ttu-id="4d990-542">**ドロップ**</span><span class="sxs-lookup"><span data-stu-id="4d990-542">**Dropped**</span></span>

<span data-ttu-id="4d990-543">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-543">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="4d990-544">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d990-544">**Date**</span></span>
- <span data-ttu-id="4d990-545">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="4d990-545">**Subject**</span></span>
- <span data-ttu-id="4d990-546">**送信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-546">**Sender**</span></span>
- <span data-ttu-id="4d990-547">**受信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-547">**Recipients**</span></span>
- <span data-ttu-id="4d990-548">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="4d990-548">**Detected by**</span></span>
- <span data-ttu-id="4d990-549">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="4d990-549">**Delivery Status**</span></span>
- <span data-ttu-id="4d990-550">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="4d990-550">**Source of Compromise**</span></span>
- <span data-ttu-id="4d990-551">**Tags**</span><span class="sxs-lookup"><span data-stu-id="4d990-551">**Tags**</span></span>

<span data-ttu-id="4d990-552">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-552">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="4d990-553">**日付**: **開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4d990-553">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="4d990-554">**検出**</span><span class="sxs-lookup"><span data-stu-id="4d990-554">**Detection**</span></span>
- <span data-ttu-id="4d990-555">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="4d990-555">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="4d990-556">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="4d990-556">**Direction**</span></span>
- <span data-ttu-id="4d990-557">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="4d990-557">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="4d990-558">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="4d990-558">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="4d990-559">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="4d990-559">**Domain**</span></span>
- <span data-ttu-id="4d990-560">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="4d990-560">**Policy type**</span></span>
- <span data-ttu-id="4d990-561">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="4d990-561">**Policy name** (details table only)</span></span>
- <span data-ttu-id="4d990-562">**受信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-562">**Recipients**</span></span>

<span data-ttu-id="4d990-563">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-563">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="4d990-564">コンテンツ マルウェアによるデータの \> 表示</span><span class="sxs-lookup"><span data-stu-id="4d990-564">View data by Content \> Malware</span></span>

![脅威保護状態レポートのコンテンツ マルウェア ビュー](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="4d990-566">[コンテンツ **マルウェアによるデータ \> の** 表示] ビューでは、組織の Microsoft Defender のグラフに次のOffice 365示されています。</span><span class="sxs-lookup"><span data-stu-id="4d990-566">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="4d990-567">**マルウェア対策エンジン**: Sharepoint、OneDrive、および Microsoft Teams で組み込みのウイルス検出によって検出された悪意のある [Microsoft 365。](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="4d990-567">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="4d990-568">**ファイルの削除**: 添付ファイルによって検出された悪意のある [セーフ、SharePoint、OneDrive、](mdo-for-spo-odb-and-teams.md)およびMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="4d990-568">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="4d990-569">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-569">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="4d990-570">**日付**: **開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4d990-570">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="4d990-571">**場所**</span><span class="sxs-lookup"><span data-stu-id="4d990-571">**Location**</span></span>
- <span data-ttu-id="4d990-572">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="4d990-572">**Detected by**</span></span>
- <span data-ttu-id="4d990-573">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="4d990-573">**Malware name**</span></span>

<span data-ttu-id="4d990-574">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-574">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="4d990-575">**日付**: **開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4d990-575">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="4d990-576">**検出**:**マルウェア対策エンジンまたは\*\*\*\*ファイルの削除**</span><span class="sxs-lookup"><span data-stu-id="4d990-576">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="4d990-577">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-577">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="4d990-578">システムオーバーライドによるデータの表示</span><span class="sxs-lookup"><span data-stu-id="4d990-578">View data by System override</span></span>

![脅威保護状態レポートのメッセージの上書きビュー](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="4d990-580">[システムによる **データの表示] オーバーライド** ビューでは、次のオーバーライド理由情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-580">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="4d990-581">**オンプレミスのスキップ**</span><span class="sxs-lookup"><span data-stu-id="4d990-581">**On-premises skip**</span></span>
- <span data-ttu-id="4d990-582">**IP 許可**</span><span class="sxs-lookup"><span data-stu-id="4d990-582">**IP allow**</span></span>
- <span data-ttu-id="4d990-583">**Exchange トランスポート ルール**(メール フロー ルール)</span><span class="sxs-lookup"><span data-stu-id="4d990-583">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="4d990-584">**組織で許可されている送信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-584">**Organization allowed senders**</span></span>
- <span data-ttu-id="4d990-585">**組織で許可されているドメイン**</span><span class="sxs-lookup"><span data-stu-id="4d990-585">**Organization allowed domains**</span></span>
- <span data-ttu-id="4d990-586">**ZAP が有効になっていません**</span><span class="sxs-lookup"><span data-stu-id="4d990-586">**ZAP not enabled**</span></span>
- <span data-ttu-id="4d990-587">**迷惑メール フォルダーが有効になっていない**</span><span class="sxs-lookup"><span data-stu-id="4d990-587">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="4d990-588">**ユーザーセーフ送信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-588">**User Safe Sender**</span></span>
- <span data-ttu-id="4d990-589">**ユーザー セーフ ドメイン**</span><span class="sxs-lookup"><span data-stu-id="4d990-589">**User Safe Domain**</span></span>

<span data-ttu-id="4d990-590">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-590">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="4d990-591">**Date**</span><span class="sxs-lookup"><span data-stu-id="4d990-591">**Date**</span></span>
- <span data-ttu-id="4d990-592">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="4d990-592">**Subject**</span></span>
- <span data-ttu-id="4d990-593">**送信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-593">**Sender**</span></span>
- <span data-ttu-id="4d990-594">**受信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-594">**Recipients**</span></span>
- <span data-ttu-id="4d990-595">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="4d990-595">**Detected by**</span></span>
- <span data-ttu-id="4d990-596">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="4d990-596">**Delivery Status**</span></span>
- <span data-ttu-id="4d990-597">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="4d990-597">**Source of Compromise**</span></span>
- <span data-ttu-id="4d990-598">**Tags**</span><span class="sxs-lookup"><span data-stu-id="4d990-598">**Tags**</span></span>

<span data-ttu-id="4d990-599">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-599">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="4d990-600">**日付**: **開始日** と **終了日**</span><span class="sxs-lookup"><span data-stu-id="4d990-600">**Date**: **Start date** and **End date**</span></span>
- <span data-ttu-id="4d990-601">**検出**</span><span class="sxs-lookup"><span data-stu-id="4d990-601">**Detection**</span></span>
- <span data-ttu-id="4d990-602">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="4d990-602">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="4d990-603">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="4d990-603">**Direction**</span></span>
- <span data-ttu-id="4d990-604">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="4d990-604">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="4d990-605">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="4d990-605">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="4d990-606">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="4d990-606">**Domain**</span></span>
- <span data-ttu-id="4d990-607">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="4d990-607">**Policy type**</span></span>
- <span data-ttu-id="4d990-608">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="4d990-608">**Policy name** (details table only)</span></span>
- <span data-ttu-id="4d990-609">**受信者**</span><span class="sxs-lookup"><span data-stu-id="4d990-609">**Recipients**</span></span>

<span data-ttu-id="4d990-610">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-610">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="4d990-611"><sup>\*</sup>Defender for Office 365のみ</span><span class="sxs-lookup"><span data-stu-id="4d990-611"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="4d990-612">トップ マルウェア レポート</span><span class="sxs-lookup"><span data-stu-id="4d990-612">Top malware report</span></span>

<span data-ttu-id="4d990-613">[ **トップ マルウェア]** レポートには、EOP のマルウェア対策保護によって検出されたさまざまな種類 [のマルウェアが表示されます](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="4d990-613">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="4d990-614">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="4d990-614">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="4d990-615">[トップ **マルウェア] で、[** 詳細の表示 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-615">On **Top malware**, click **View details**.</span></span> <span data-ttu-id="4d990-616">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="4d990-616">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![[メール と共同作業レポート] ページの&のトップ マルウェア ウィジェット](../../media/top-malware-report-widget.png)

<span data-ttu-id="4d990-618">円グラフのくさびの上にマウス ポインターを置くと、マルウェアの種類の名前と、そのマルウェアが検出されたメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-618">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="4d990-619">[詳細の **表示] をクリック** すると、より大きなバージョンの円グラフがレポート ページに表示されます。グラフの下の詳細テーブルは、次の情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="4d990-619">After you click **View details**, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="4d990-620">**トップ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="4d990-620">**Top malware**</span></span>
- <span data-ttu-id="4d990-621">**Count**</span><span class="sxs-lookup"><span data-stu-id="4d990-621">**Count**</span></span>

<span data-ttu-id="4d990-622">[フィルター]**をクリック** すると、[開始日] と [終了日] で **日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="4d990-622">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![トップ マルウェア レポート ビュー](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="4d990-624">URL 脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="4d990-624">URL threat protection report</span></span>

<span data-ttu-id="4d990-625">URL **の脅威保護レポートは**、Microsoft Defender で使用できるOffice 365。</span><span class="sxs-lookup"><span data-stu-id="4d990-625">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="4d990-626">詳細については、「URL 脅威保護 [レポート」を参照してください](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="4d990-626">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="4d990-627">ユーザーが報告したメッセージ レポート</span><span class="sxs-lookup"><span data-stu-id="4d990-627">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d990-628">ユーザーが報告した **メッセージ レポート** が正しく動作するには、ユーザーの環境で監査ログを有効にするMicrosoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="4d990-628">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="4d990-629">これは通常、監査ログの役割が管理者に割り当てられているユーザー Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="4d990-629">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="4d990-630">詳細については、「監査ログの[検索を有効またはMicrosoft 365を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="4d990-630">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="4d990-631">[**ユーザーレポート メッセージ]** レポートには、ユーザーが迷惑メール、フィッシング詐欺の試み、または良いメールとして報告した [](enable-the-report-message-add-in.md)電子メール メッセージに関する情報が、レポート メッセージ アドインまたはレポート フィッシング アドインを使用して表示 [されます](enable-the-report-phish-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="4d990-631">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="4d990-632">ポータルでレポートを表示するにはMicrosoft 365 Defender[メールのレポート] &[グループ& \>  \> **レポート**] [ユーザーが報告した \> **メッセージ] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="4d990-632">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \>**Email & collaboration reports** \> **User reported messages**.</span></span> <span data-ttu-id="4d990-633">[ユーザー **が報告したメッセージ] で**、[詳細の表示 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-633">On **User reported messages**, click **View details**.</span></span> <span data-ttu-id="4d990-634">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/userSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="4d990-634">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="4d990-635">ポータルで [管理者の申請に移動するには、[Microsoft 365 Defender提出](admin-submission.md)に移動 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-635">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![[メール] ページの [コラボレーション レポート] ページ&報告されたメッセージ ウィジェット](../../media/user-reported-messages-widget.png)

<span data-ttu-id="4d990-637">[詳細の **表示]** をクリックすると、[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択して、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-637">After you click **View details**, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="4d990-638">**報告日**: **開始時刻** と **終了時刻**</span><span class="sxs-lookup"><span data-stu-id="4d990-638">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="4d990-639">[**レポート作成者**]</span><span class="sxs-lookup"><span data-stu-id="4d990-639">**Reported by**</span></span>
- <span data-ttu-id="4d990-640">**メールの件名**</span><span class="sxs-lookup"><span data-stu-id="4d990-640">**Email subject**</span></span>
- <span data-ttu-id="4d990-641">**メッセージの報告 ID**</span><span class="sxs-lookup"><span data-stu-id="4d990-641">**Message reported ID**</span></span>
- <span data-ttu-id="4d990-642">**ネットワーク メッセージ ID**</span><span class="sxs-lookup"><span data-stu-id="4d990-642">**Network Message ID**</span></span>
- <span data-ttu-id="4d990-643">**Sender**</span><span class="sxs-lookup"><span data-stu-id="4d990-643">**Sender**</span></span>
- <span data-ttu-id="4d990-644">**報告された理由**</span><span class="sxs-lookup"><span data-stu-id="4d990-644">**Reported reason**</span></span>
  - <span data-ttu-id="4d990-645">**迷惑メールではない**</span><span class="sxs-lookup"><span data-stu-id="4d990-645">**Not junk**</span></span>
  - <span data-ttu-id="4d990-646">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="4d990-646">**Phish**</span></span>
  - <span data-ttu-id="4d990-647">**スパム**</span><span class="sxs-lookup"><span data-stu-id="4d990-647">**Spam**</span></span>
- <span data-ttu-id="4d990-648">**フィッシングシミュレーション**:**はいまたは\*\*\*\*いいえ**</span><span class="sxs-lookup"><span data-stu-id="4d990-648">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="4d990-649">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="4d990-649">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="4d990-650">エントリをグループ化するには、[グループ] を **クリック** し、ドロップダウン リストから次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d990-650">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="4d990-651">**なし**</span><span class="sxs-lookup"><span data-stu-id="4d990-651">**None**</span></span>
- <span data-ttu-id="4d990-652">**理由**</span><span class="sxs-lookup"><span data-stu-id="4d990-652">**Reason**</span></span>
- <span data-ttu-id="4d990-653">**Sender**</span><span class="sxs-lookup"><span data-stu-id="4d990-653">**Sender**</span></span>
- <span data-ttu-id="4d990-654">[**レポート作成者**]</span><span class="sxs-lookup"><span data-stu-id="4d990-654">**Reported by**</span></span>
- <span data-ttu-id="4d990-655">**再スキャンの結果**</span><span class="sxs-lookup"><span data-stu-id="4d990-655">**Rescan result**</span></span>
- <span data-ttu-id="4d990-656">**フィッシング シミュレーション**</span><span class="sxs-lookup"><span data-stu-id="4d990-656">**Phish simulation**</span></span>

![ユーザーが報告したメッセージ レポート](../../media/user-reported-messages-report.png)

<span data-ttu-id="4d990-658">グラフの下の表で、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="4d990-658">In the table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="4d990-659">**メールの件名**</span><span class="sxs-lookup"><span data-stu-id="4d990-659">**Email subject**</span></span>
- <span data-ttu-id="4d990-660">[**レポート作成者**]</span><span class="sxs-lookup"><span data-stu-id="4d990-660">**Reported by**</span></span>
- <span data-ttu-id="4d990-661">**報告日**</span><span class="sxs-lookup"><span data-stu-id="4d990-661">**Date reported**</span></span>
- <span data-ttu-id="4d990-662">**Sender**</span><span class="sxs-lookup"><span data-stu-id="4d990-662">**Sender**</span></span>
- <span data-ttu-id="4d990-663">**報告された理由**</span><span class="sxs-lookup"><span data-stu-id="4d990-663">**Reported reason**</span></span>
- <span data-ttu-id="4d990-664">**再スキャンの結果**</span><span class="sxs-lookup"><span data-stu-id="4d990-664">**Rescan result**</span></span>
- <span data-ttu-id="4d990-665">**Tags**</span><span class="sxs-lookup"><span data-stu-id="4d990-665">**Tags**</span></span>

<span data-ttu-id="4d990-666">分析のために Microsoft にメッセージを送信するには、表からメッセージ エントリを選択し、[分析のために **Microsoft** に送信] をクリックし、ドロップダウン リストから次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="4d990-666">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="4d990-667">**クリーンレポート**</span><span class="sxs-lookup"><span data-stu-id="4d990-667">**Report clean**</span></span>
- <span data-ttu-id="4d990-668">**フィッシングの報告**</span><span class="sxs-lookup"><span data-stu-id="4d990-668">**Report phishing**</span></span>
- <span data-ttu-id="4d990-669">**マルウェアの報告**</span><span class="sxs-lookup"><span data-stu-id="4d990-669">**Report malware**</span></span>
- <span data-ttu-id="4d990-670">**[スパムを報告する**]</span><span class="sxs-lookup"><span data-stu-id="4d990-670">**Report spam**'</span></span>
- <span data-ttu-id="4d990-671">**トリガー調査**(Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="4d990-671">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="4d990-672">これらのレポートを表示するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="4d990-672">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="4d990-673">この記事で説明するレポートを表示して使用するには、ポータルで次のいずれかの役割グループのメンバー Microsoft 365 Defenderがあります。</span><span class="sxs-lookup"><span data-stu-id="4d990-673">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="4d990-674">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="4d990-674">**Organization Management**</span></span>
- <span data-ttu-id="4d990-675">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="4d990-675">**Security Administrator**</span></span>
- <span data-ttu-id="4d990-676">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="4d990-676">**Security Reader**</span></span>
- <span data-ttu-id="4d990-677">**グローバル リーダー**</span><span class="sxs-lookup"><span data-stu-id="4d990-677">**Global Reader**</span></span>

<span data-ttu-id="4d990-678">詳細については、「ポータルの[アクセス許可」をMicrosoft 365 Defenderしてください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="4d990-678">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="4d990-679">**注**: Microsoft 365 管理センター の対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="4d990-679">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="4d990-680">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4d990-680">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="4d990-681">レポートにデータが表示されない場合は、</span><span class="sxs-lookup"><span data-stu-id="4d990-681">What if the reports aren't showing data?</span></span>

<span data-ttu-id="4d990-682">レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4d990-682">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="4d990-683">詳細については、「脅威から保護 [する」を参照してください](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="4d990-683">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4d990-684">関連項目</span><span class="sxs-lookup"><span data-stu-id="4d990-684">Related topics</span></span>

[<span data-ttu-id="4d990-685">EOP でのスパム対策およびマルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="4d990-685">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="4d990-686">スマート レポートと分析情報 (Microsoft 365 Defenderポータル)</span><span class="sxs-lookup"><span data-stu-id="4d990-686">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="4d990-687">メール フロー レポートをポータルでMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="4d990-687">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="4d990-688">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="4d990-688">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
