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
ms.openlocfilehash: f3dcf533c232a89adf0dc1ff3fcc7c2ca4fc5d8f
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022934"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="35148-103">Microsoft 365 Defender ポータルで電子メール セキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="35148-103">View email security reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="35148-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="35148-104">**Applies to**</span></span>
- [<span data-ttu-id="35148-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="35148-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="35148-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="35148-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="35148-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35148-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="35148-108">Microsoft 365 Defender ポータルでは、Microsoft 365 のスパム対策、マルウェア対策、暗号化機能などの電子メール セキュリティ機能が組織を保護している方法を確認できます。 <https://security.microsoft.com></span><span class="sxs-lookup"><span data-stu-id="35148-108">A variety of reports are available in the Microsoft 365 Defender portal at <https://security.microsoft.com> to help you see how email security features, such as anti-spam, anti-malware, and encryption features in Microsoft 365 are protecting your organization.</span></span> <span data-ttu-id="35148-109">必要な [アクセス許可を](#what-permissions-are-needed-to-view-these-reports)持っている場合は、[電子メールのレポート] & コラボレーション レポートにアクセスして、Microsoft 365 Defender ポータルでこれらのレポート \>  \> **&表示できます**。</span><span class="sxs-lookup"><span data-stu-id="35148-109">If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="35148-110">[コラボレーション レポートの電子メール] **ページ&移動するには、** を開きます <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="35148-110">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![Microsoft 365 Defender &の [コラボレーション レポート] ページにメールを送信する](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="35148-112">[電子メール と共同作業レポート] ページ& **一部のレポートでは** 、Microsoft Defender が 365 Office必要です。</span><span class="sxs-lookup"><span data-stu-id="35148-112">Some of the reports on the **Email & collaboration reports** page require Microsoft Defender for Office 365.</span></span> <span data-ttu-id="35148-113">これらのレポートの詳細については [、「View Defender for Office 365 レポート」を参照してください](view-reports-for-mdo.md)。</span><span class="sxs-lookup"><span data-stu-id="35148-113">For information about these reports, see [View Defender for Office 365 reports in the Microsoft 365 Defender portal](view-reports-for-mdo.md).</span></span>
>
> <span data-ttu-id="35148-114">メール フローに関連するレポートが Exchange 管理センター (EAC) に追加されました。</span><span class="sxs-lookup"><span data-stu-id="35148-114">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="35148-115">これらのレポートの詳細については、「新しい Exchange 管理センターのメール フロー [レポート」を参照してください](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。</span><span class="sxs-lookup"><span data-stu-id="35148-115">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="compromised-users-report"></a><span data-ttu-id="35148-116">侵害されたユーザー レポート</span><span class="sxs-lookup"><span data-stu-id="35148-116">Compromised users report</span></span>

> [!NOTE]
> <span data-ttu-id="35148-117">このレポートは、Exchange Online メールボックスを持つ Microsoft 365 組織で利用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-117">This report is available in Microsoft 365 organizations with Exchange Online mailboxes.</span></span> <span data-ttu-id="35148-118">スタンドアロンの Exchange Online Protection (EOP) 組織では使用できません。</span><span class="sxs-lookup"><span data-stu-id="35148-118">It's not available in standalone Exchange Online Protection (EOP) organizations.</span></span>

<span data-ttu-id="35148-119">[**侵害されたユーザー] レポート** には、過去 7 日以内に[疑わしい] または [制限付き] とマークされたユーザー アカウントの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-119">The **Compromised users** report shows shows the number of user accounts that were marked as **Suspicious** or **Restricted** within the last 7 days.</span></span> <span data-ttu-id="35148-120">これらの状態のどちらかのアカウントは、問題が発生したり、侵害された場合もあります。</span><span class="sxs-lookup"><span data-stu-id="35148-120">Accounts in either of these states are problematic or even compromised.</span></span> <span data-ttu-id="35148-121">頻繁に使用すると、レポートを使用して、疑わしいアカウントや制限付きアカウントのスパイクや傾向を見つけるのに使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-121">With frequent use, you can use the report to spot spikes, and even trends, in suspicious or restricted accounts.</span></span> <span data-ttu-id="35148-122">侵害されたユーザーの詳細については、「侵害されたメール アカウントへの [応答」を参照してください](responding-to-a-compromised-email-account.md)。</span><span class="sxs-lookup"><span data-stu-id="35148-122">For more information about compromised users, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

![[コラボレーション レポートの電子メール] ページの [侵害&ユーザー] ウィジェット](../../media/compromised-users-report-widget.png)

<span data-ttu-id="35148-124">集計ビューには過去 90 日間のデータが表示され、詳細ビューには過去 30 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-124">The aggregate view shows data for the last 90 days and the detail view shows data for the last 30 days.</span></span>

<span data-ttu-id="35148-125">Microsoft 365 Defender ポータルでレポートを表示するには、「Reports  \> **Email &コラボレーション** レポート \> **&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="35148-125">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="35148-126">[コラボレーション **レポートのメール&] ページで**、[侵害されたユーザー] を探し、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-126">On the **Email & collaboration reports** page, find **Compromised users** and then click **View details**.</span></span> <span data-ttu-id="35148-127">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/CompromisedUsers> 。</span><span class="sxs-lookup"><span data-stu-id="35148-127">To go directly to the report, open <https://security.microsoft.com/reports/CompromisedUsers>.</span></span>

<span data-ttu-id="35148-128">[侵害された **ユーザー** ] ページで、[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択することで、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="35148-128">On the **Compromised users** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="35148-129">**日付 (UTC)**:**開始日と\*\*\*\*終了日**。</span><span class="sxs-lookup"><span data-stu-id="35148-129">**Date (UTC)**: **Start date** and **End date**.</span></span>
- <span data-ttu-id="35148-130">**アクティビティ**:</span><span class="sxs-lookup"><span data-stu-id="35148-130">**Activity**:</span></span>
  - <span data-ttu-id="35148-131">**疑** わしい : ユーザー アカウントが不審なメールを送信し、電子メールの送信を制限される危険性があります。</span><span class="sxs-lookup"><span data-stu-id="35148-131">**Suspicious**: The user account has sent suspicious email and is at risk of being restricted from sending email.</span></span>
  - <span data-ttu-id="35148-132">**制限**: 不審なパターンが多く、ユーザー アカウントが電子メールの送信を制限されています。</span><span class="sxs-lookup"><span data-stu-id="35148-132">**Restricted**: The user account has been restricted from sending email due to highly suspicious patterns.</span></span>

<span data-ttu-id="35148-133">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-133">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

![[侵害されたユーザー] レポートのレポート ビュー](../../media/compromised-users-report-activity-view.png)

<span data-ttu-id="35148-135">グラフの下の詳細テーブルで、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="35148-135">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="35148-136">**作成時間**</span><span class="sxs-lookup"><span data-stu-id="35148-136">**Creation time**</span></span>
- <span data-ttu-id="35148-137">**[ユーザー ID]**</span><span class="sxs-lookup"><span data-stu-id="35148-137">**User ID**</span></span>
- <span data-ttu-id="35148-138">**Action**</span><span class="sxs-lookup"><span data-stu-id="35148-138">**Action**</span></span>

## <a name="exchange-transport-rule-report"></a><span data-ttu-id="35148-139">Exchange トランスポート ルール レポート</span><span class="sxs-lookup"><span data-stu-id="35148-139">Exchange transport rule report</span></span>

<span data-ttu-id="35148-140">**Exchange トランスポート ルール レポートには**、組織内の受信メッセージと送信メッセージに対するメール フロー ルール (トランスポート ルールとも呼ばれる) の影響が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-140">The **Exchange transport rule** report shows the effect of mail flow rules (also known as transport rules) on incoming and outgoing messages in your organization.</span></span>

<span data-ttu-id="35148-141">Microsoft 365 Defender ポータルでレポートを表示するには、「Reports  \> **Email &コラボレーション** レポート \> **&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="35148-141">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="35148-142">[電子メール **&コラボレーション レポート] ページで\*\*\*\*、Exchange トランスポート ルールを検索し**、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-142">On the **Email & collaboration reports** page, find **Exchange transport rule** and then click **View details**.</span></span> <span data-ttu-id="35148-143">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/ETRRuleReport> 。</span><span class="sxs-lookup"><span data-stu-id="35148-143">To go directly to the report, open <https://security.microsoft.com/reports/ETRRuleReport>.</span></span>

![[電子メール] コラボレーション レポート ページ& Exchange トランスポート ルール ウィジェット](../../media/transport-rule-report-widget.png)

<span data-ttu-id="35148-145">[Exchange トランスポート **ルール レポート] ページ** で、使用可能なグラフとデータについて、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="35148-145">On the **Exchange transport rule report** page, the available charts and data are described in the following sections.</span></span>

### <a name="chart-breakdown-by-direction"></a><span data-ttu-id="35148-146">[方向] によるグラフの内訳</span><span class="sxs-lookup"><span data-stu-id="35148-146">Chart breakdown by Direction</span></span>

![Exchange トランスポート ルール レポートの Exchange トランスポート ルールの方向ビュー](../../media/transport-rule-report-etr-direction-view.png)

<span data-ttu-id="35148-148">[方向によるグラフ **の内訳] を選択すると**、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-148">If you select **Chart breakdown by Direction**, the follow charts are available:</span></span>

- <span data-ttu-id="35148-149">**Exchange トランスポート ルールによるデータの表示**  : メールフロー ルールの影響を受けた受信メッセージと送信メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="35148-149">**View data by Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by mail flow rules.</span></span>
- <span data-ttu-id="35148-150">**DLP Exchange トランスポート ルールによる** データの表示:データ損失防止 (DLP) メール フロー ルールの影響を受けた受信メッセージと送信メッセージの数。</span><span class="sxs-lookup"><span data-stu-id="35148-150">**View data by DLP Exchange transport rules**: The number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) mail flow rules.</span></span>

<span data-ttu-id="35148-151">次の情報は、グラフの下の詳細テーブルに示されています。</span><span class="sxs-lookup"><span data-stu-id="35148-151">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="35148-152">**Date**</span><span class="sxs-lookup"><span data-stu-id="35148-152">**Date**</span></span>
- <span data-ttu-id="35148-153">**DLP ポリシー** (**DLP Exchange トランスポート ルールによるデータの表示** のみ)</span><span class="sxs-lookup"><span data-stu-id="35148-153">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="35148-154">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="35148-154">**Transport rule**</span></span>
- <span data-ttu-id="35148-155">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="35148-155">**Subject**</span></span>
- <span data-ttu-id="35148-156">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="35148-156">**Sender address**</span></span>
- <span data-ttu-id="35148-157">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="35148-157">**Recipient address**</span></span>
- <span data-ttu-id="35148-158">**重大度**</span><span class="sxs-lookup"><span data-stu-id="35148-158">**Severity**</span></span>
- <span data-ttu-id="35148-159">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="35148-159">**Direction**</span></span>

<span data-ttu-id="35148-160">[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="35148-160">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="35148-161">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="35148-161">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="35148-162">**方向**:**送信と\*\*\*\*受信**</span><span class="sxs-lookup"><span data-stu-id="35148-162">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="35148-163">**重大度**:**重大度が高い、\*\*\*\*中程度の重大度**、**および低重大度**</span><span class="sxs-lookup"><span data-stu-id="35148-163">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="35148-164">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-164">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-severity"></a><span data-ttu-id="35148-165">重大度別のグラフの内訳</span><span class="sxs-lookup"><span data-stu-id="35148-165">Chart breakdown by Severity</span></span>

![Exchange トランスポート ルール レポートの Exchange トランスポート ルールの重大度ビュー](../../media/transport-rule-report-etr-severity-view.png)

<span data-ttu-id="35148-167">[重要度による **グラフの内訳] を選択した場合** は、次のグラフを使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-167">If you select **Chart breakdown by Severity**, the follow charts are available:</span></span>

- <span data-ttu-id="35148-168">**Exchange トランスポート ルール別にデータ** を表示する: 重大度の高いメッセージ、中程度の重大度、および **低重大度メッセージの** 数。</span><span class="sxs-lookup"><span data-stu-id="35148-168">**View data by Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages.</span></span> <span data-ttu-id="35148-169">重大度レベルは、ルールのアクションとして設定します **(重大度** レベルまたは _SetAuditSeverity_ でこのルールを監査します)。</span><span class="sxs-lookup"><span data-stu-id="35148-169">You set the severity level as an action in the rule (**Audit this rule with severity level** or _SetAuditSeverity_).</span></span> <span data-ttu-id="35148-170">詳細については [、「Exchange Online のメール フロー ルールアクション」を参照してください](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)。</span><span class="sxs-lookup"><span data-stu-id="35148-170">For more information, see [Mail flow rule actions in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span>

- <span data-ttu-id="35148-171">**DLP Exchange トランスポート ルール** でデータを表示する : DLP メール フロールールの影響を受けた重大度の高いメッセージ、中程度の重大度、および低重大度メッセージの数。 </span><span class="sxs-lookup"><span data-stu-id="35148-171">**View data by DLP Exchange transport rules**: The number of **High severity**, **Medium severity**, and **Low severity** messages that were affected by DLP mail flow rules.</span></span>

<span data-ttu-id="35148-172">次の情報は、グラフの下の詳細テーブルに示されています。</span><span class="sxs-lookup"><span data-stu-id="35148-172">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="35148-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="35148-173">**Date**</span></span>
- <span data-ttu-id="35148-174">**DLP ポリシー** (**DLP Exchange トランスポート ルールによるデータの表示** のみ)</span><span class="sxs-lookup"><span data-stu-id="35148-174">**DLP policy** (**View data by DLP Exchange transport rules** only)</span></span>
- <span data-ttu-id="35148-175">**トランスポート ルール**</span><span class="sxs-lookup"><span data-stu-id="35148-175">**Transport rule**</span></span>
- <span data-ttu-id="35148-176">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="35148-176">**Subject**</span></span>
- <span data-ttu-id="35148-177">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="35148-177">**Sender address**</span></span>
- <span data-ttu-id="35148-178">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="35148-178">**Recipient address**</span></span>
- <span data-ttu-id="35148-179">**重大度**</span><span class="sxs-lookup"><span data-stu-id="35148-179">**Severity**</span></span>
- <span data-ttu-id="35148-180">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="35148-180">**Direction**</span></span>

<span data-ttu-id="35148-181">[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択すると、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="35148-181">You can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="35148-182">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="35148-182">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="35148-183">**方向**:**送信と\*\*\*\*受信**</span><span class="sxs-lookup"><span data-stu-id="35148-183">**Direction**: **Outbound** and **Inbound**</span></span>
- <span data-ttu-id="35148-184">**重大度**:**重大度が高い、\*\*\*\*中程度の重大度**、**および低重大度**</span><span class="sxs-lookup"><span data-stu-id="35148-184">**Severity**: **High severity**, **Medium severity**, and **Low severity**</span></span>

<span data-ttu-id="35148-185">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

## <a name="forwarding-report"></a><span data-ttu-id="35148-186">転送レポート</span><span class="sxs-lookup"><span data-stu-id="35148-186">Forwarding report</span></span>

> [!NOTE]
> <span data-ttu-id="35148-187">転送 **レポートは** EAC で利用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-187">The **Forwarding report** is now available in the EAC.</span></span> <span data-ttu-id="35148-188">詳細については、「新しい [EAC の自動転送メッセージ レポート」を参照してください](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)。</span><span class="sxs-lookup"><span data-stu-id="35148-188">For more information, see [Auto forwarded messages report in the new EAC](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report).</span></span>

## <a name="mailflow-status-report"></a><span data-ttu-id="35148-189">メールフローの状態レポート</span><span class="sxs-lookup"><span data-stu-id="35148-189">Mailflow status report</span></span>

<span data-ttu-id="35148-190">**Mailflow 状態** レポートは、受信および送信メール、スパム検出、マルウェア、"良い" と識別される電子メール、およびエッジで許可またはブロックされた電子メールに関する情報を示すスマート レポートです。</span><span class="sxs-lookup"><span data-stu-id="35148-190">The **Mailflow status report** is a smart report that shows information about incoming and outgoing email, spam detections, malware, email identified as "good", and information about email allowed or blocked on the edge.</span></span> <span data-ttu-id="35148-191">これはエッジ保護情報を含む唯一のレポートであり、Exchange Online Protection (EOP) による評価のためにサービスに許可される前にブロックされる電子メールの量のみを示します。</span><span class="sxs-lookup"><span data-stu-id="35148-191">This is the only report that contains edge protection information, and shows just how much email is blocked before being allowed into the service for evaluation by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="35148-192">メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="35148-192">It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="35148-193">Microsoft 365 Defender ポータルでレポートを表示するには、「Reports  \> **Email &コラボレーション** レポート \> **&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="35148-193">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="35148-194">[メール **の送信&] ページ** で、[ **メールフロー** の状態の概要] を探し、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-194">On the **Email & collaboration reports** page, find **Mailflow status summary** and then click **View details**.</span></span> <span data-ttu-id="35148-195">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/mailflowStatusReport> 。</span><span class="sxs-lookup"><span data-stu-id="35148-195">To go directly to the report, open <https://security.microsoft.com/reports/mailflowStatusReport>.</span></span>

![[メール] グループ作業レポート ページの [メールフロー&概要] ウィジェット](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a><span data-ttu-id="35148-197">メールフロー状態レポートの種類ビュー</span><span class="sxs-lookup"><span data-stu-id="35148-197">Type view for the Mailflow status report</span></span>

<span data-ttu-id="35148-198">レポートを開いた場合、[種類] **タブ** が既定で選択されます。</span><span class="sxs-lookup"><span data-stu-id="35148-198">When you open the report, the **Type** tab is selected by default.</span></span> <span data-ttu-id="35148-199">既定では、このビューにはグラフと、次のフィルターで構成された詳細テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="35148-199">By default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="35148-200">**日付 (UTC)** 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="35148-200">**Date (UTC)** The last 7 days.</span></span>
- <span data-ttu-id="35148-201">**メールの方向**:</span><span class="sxs-lookup"><span data-stu-id="35148-201">**Mail direction**:</span></span>
  - <span data-ttu-id="35148-202">**受信**</span><span class="sxs-lookup"><span data-stu-id="35148-202">**Inbound**</span></span>
  - <span data-ttu-id="35148-203">**送信**</span><span class="sxs-lookup"><span data-stu-id="35148-203">**Outbound**</span></span>
  - <span data-ttu-id="35148-204">**組織内**: この数は、テナント内のメッセージ 、つまり</span><span class="sxs-lookup"><span data-stu-id="35148-204">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="35148-205">送信者 abc@domain.com 受信者に送信 xyz@domain.com (受信および送信とは別 **に\*\*\*\*カウント)**</span><span class="sxs-lookup"><span data-stu-id="35148-205">sender abc@domain.com sends to recipient xyz@domain.com  (counted separately from **Inbound** and **Outbound**)</span></span>
- <span data-ttu-id="35148-206">**種類**:</span><span class="sxs-lookup"><span data-stu-id="35148-206">**Type**:</span></span>
  - <span data-ttu-id="35148-207">**良いメール**</span><span class="sxs-lookup"><span data-stu-id="35148-207">**Good mail**</span></span>
  - <span data-ttu-id="35148-208">**マルウェア**</span><span class="sxs-lookup"><span data-stu-id="35148-208">**Malware**</span></span>
  - <span data-ttu-id="35148-209">**スパム**</span><span class="sxs-lookup"><span data-stu-id="35148-209">**Spam**</span></span>
  - <span data-ttu-id="35148-210">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="35148-210">**Edge protection**</span></span>
  - <span data-ttu-id="35148-211">**ルール メッセージ**</span><span class="sxs-lookup"><span data-stu-id="35148-211">**Rule messages**</span></span>
  - <span data-ttu-id="35148-212">**フィッシング詐欺メール**</span><span class="sxs-lookup"><span data-stu-id="35148-212">**Phishing email**</span></span>
- <span data-ttu-id="35148-213">**ドメイン**: **すべて**</span><span class="sxs-lookup"><span data-stu-id="35148-213">**Domain**: **All**</span></span>

<span data-ttu-id="35148-214">グラフは、Type 値によって **整理** されます。</span><span class="sxs-lookup"><span data-stu-id="35148-214">The chart is organized by the **Type** values.</span></span>

<span data-ttu-id="35148-215">これらのフィルターは、[フィルター] を **クリックするか** 、グラフの凡例の値をクリックして変更できます。</span><span class="sxs-lookup"><span data-stu-id="35148-215">You can change these filters by clicking **Filter** or by clicking a value in the chart legend.</span></span>

<span data-ttu-id="35148-216">次の情報は、グラフの下の詳細テーブルに示されています。</span><span class="sxs-lookup"><span data-stu-id="35148-216">The following information is shown in the details table below the graph:</span></span>

- <span data-ttu-id="35148-217">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="35148-217">**Direction**</span></span>
- <span data-ttu-id="35148-218">**種類**</span><span class="sxs-lookup"><span data-stu-id="35148-218">**Type**</span></span>
- <span data-ttu-id="35148-219">**24 時間**</span><span class="sxs-lookup"><span data-stu-id="35148-219">**24 hours**</span></span>
- <span data-ttu-id="35148-220">**3 日間**</span><span class="sxs-lookup"><span data-stu-id="35148-220">**3 days**</span></span>
- <span data-ttu-id="35148-221">**7 日間**</span><span class="sxs-lookup"><span data-stu-id="35148-221">**7 days**</span></span>
- <span data-ttu-id="35148-222">**15 日**</span><span class="sxs-lookup"><span data-stu-id="35148-222">**15 days**</span></span>
- <span data-ttu-id="35148-223">**30 日間**</span><span class="sxs-lookup"><span data-stu-id="35148-223">**30 days**</span></span>

<span data-ttu-id="35148-224">詳細については、[ **カテゴリの選択] をクリックすると**、次の値から選択できます。</span><span class="sxs-lookup"><span data-stu-id="35148-224">If you click **Choose a category for more details**, you can select from the following values:</span></span>

- <span data-ttu-id="35148-225">**フィッシングメール**: この選択によって、脅威保護の [状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="35148-225">**Phishing email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="35148-226">**電子メール内のマルウェア**: この選択によって、脅威保護 [の状態レポートが表示されます](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="35148-226">**Malware in email**: This selection takes you to the [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>
- <span data-ttu-id="35148-227">**スパム検出**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="35148-227">**Spam detections**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>
- <span data-ttu-id="35148-228">**エッジブロックスパム**: この選択により、スパム検出 [レポートに移動します](view-email-security-reports.md#spam-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="35148-228">**Edge blocked spam**: This selection takes you to the [Spam Detections report](view-email-security-reports.md#spam-detections-report).</span></span>

#### <a name="export-from-type-view"></a><span data-ttu-id="35148-229">[種類] ビューからエクスポートする</span><span class="sxs-lookup"><span data-stu-id="35148-229">Export from Type view</span></span>

<span data-ttu-id="35148-230">詳細ビューでは、1 日のデータのみをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="35148-230">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="35148-231">したがって、7 日間データをエクスポートする場合は、7 つの異なるエクスポート アクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35148-231">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="35148-232">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="35148-232">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="35148-233">その日のデータに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="35148-233">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![メールフローの状態レポートにビューを入力する](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a><span data-ttu-id="35148-235">メールフロー状態レポートの方向ビュー</span><span class="sxs-lookup"><span data-stu-id="35148-235">Direction view for the Mailflow status report</span></span>

<span data-ttu-id="35148-236">[方向] タブ **をクリックすると** 、[種類] ビューの同じ既定 **のフィルター** が使用されます。</span><span class="sxs-lookup"><span data-stu-id="35148-236">If you click the **Direction** tab, the same default filters from the **Type** view are used.</span></span>

<span data-ttu-id="35148-237">グラフは、方向の値 **によって整理** されます。</span><span class="sxs-lookup"><span data-stu-id="35148-237">The chart is organized by **Direction** values.</span></span>

<span data-ttu-id="35148-238">これらのフィルターは、[フィルター] をクリックして **変更できます**。</span><span class="sxs-lookup"><span data-stu-id="35148-238">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="35148-239">[種類] ビューの同 **じフィルターが** 使用されます。</span><span class="sxs-lookup"><span data-stu-id="35148-239">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="35148-240">詳細テーブルには、Type ビューと同じ情報 **が含** まれている。</span><span class="sxs-lookup"><span data-stu-id="35148-240">The details table contains same information from the **Type** view.</span></span>

<span data-ttu-id="35148-241">[ **使用可能な選択と動作** の詳細については、カテゴリを選択する] は、[種類] ビューと **同** じです。</span><span class="sxs-lookup"><span data-stu-id="35148-241">The **Choose a category for more details** available selections and behavior are the same as the **Type** view.</span></span>

#### <a name="export-from-direction-view"></a><span data-ttu-id="35148-242">方向ビューからエクスポートする</span><span class="sxs-lookup"><span data-stu-id="35148-242">Export from Direction view</span></span>

<span data-ttu-id="35148-243">詳細ビューでは、1 日のデータのみをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="35148-243">For the detail view, you can only export data for one day.</span></span> <span data-ttu-id="35148-244">したがって、7 日間データをエクスポートする場合は、7 つの異なるエクスポート アクションを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="35148-244">So, if you want to export data for 7 days, you need to do 7 different export actions.</span></span>

<span data-ttu-id="35148-245">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="35148-245">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="35148-246">その日のデータに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="35148-246">If the data for that day contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![メールフロー状態レポートの方向ビュー](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a><span data-ttu-id="35148-248">メールフロー状態レポートのファネル ビュー</span><span class="sxs-lookup"><span data-stu-id="35148-248">Funnel view for the Mailflow status report</span></span>

<span data-ttu-id="35148-249">[ **ファネル** ] ビューには、Microsoft の電子メール脅威防止機能が組織内の受信メールと送信メールをフィルター処理する方法が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-249">The **Funnel** view shows you how Microsoft's email threat protection features filter incoming and outgoing email in your organization.</span></span> <span data-ttu-id="35148-250">電子メールの総数と、エッジ保護、マルウェア対策、フィッシング対策、スパム対策、スプーフィング対策などの構成済みの脅威保護機能が、この数に与える影響の詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="35148-250">It provides details on the total email count, and how the configured threat protection features, including edge protection, anti-malware, anti-phishing, anti-spam, and anti-spoofing affect this count.</span></span>

<span data-ttu-id="35148-251">[ファネル] タブ **を** クリックすると、既定では、次のフィルターで構成されたグラフと詳細テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-251">If you click the **Funnel** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="35148-252">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="35148-252">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="35148-253">**方向**:</span><span class="sxs-lookup"><span data-stu-id="35148-253">**Direction**:</span></span>
  - <span data-ttu-id="35148-254">**受信**</span><span class="sxs-lookup"><span data-stu-id="35148-254">**Inbound**</span></span>
  - <span data-ttu-id="35148-255">**送信**</span><span class="sxs-lookup"><span data-stu-id="35148-255">**Outbound**</span></span>
  - <span data-ttu-id="35148-256">**組織内**: この数は、テナント内で送信されるメッセージを示します。つまり、送信者は abc@domain.com に送信 xyz@domain.com (受信と送信とは別にカウントされます)。</span><span class="sxs-lookup"><span data-stu-id="35148-256">**Intra-org**: This count is for messages sent within a tenant; i.e, sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound).</span></span>

<span data-ttu-id="35148-257">集計ビューと詳細テーブル ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="35148-257">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="35148-258">これらのフィルターは、[フィルター] をクリックして **変更できます**。</span><span class="sxs-lookup"><span data-stu-id="35148-258">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="35148-259">[種類] ビューの同 **じフィルターが** 使用されます。</span><span class="sxs-lookup"><span data-stu-id="35148-259">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="35148-260">このグラフは、次の方法で整理されたメール数を示しています。</span><span class="sxs-lookup"><span data-stu-id="35148-260">This chart shows the email count organized by:</span></span>

- <span data-ttu-id="35148-261">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="35148-261">**Total email**</span></span>
- <span data-ttu-id="35148-262">**エッジ保護後のメール**</span><span class="sxs-lookup"><span data-stu-id="35148-262">**Email after edge protection**</span></span>
- <span data-ttu-id="35148-263">**トランスポート ルールの後のメール** (メール フロー ルール)</span><span class="sxs-lookup"><span data-stu-id="35148-263">**Email after transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="35148-264">**マルウェア対策、ファイル評価、ファイルの種類ブロック後のメール**</span><span class="sxs-lookup"><span data-stu-id="35148-264">**Email after anti-malware, file reputation, file type block**</span></span>
- <span data-ttu-id="35148-265">**フィッシング対策、URL 評価、ブランド偽装、スプーフィング対策の後のメール**</span><span class="sxs-lookup"><span data-stu-id="35148-265">**Email after anti-phish, URL reputation, brand impersonation, anti-spoof**</span></span>
- <span data-ttu-id="35148-266">**スパム対策、バルク メール フィルター処理後のメール**</span><span class="sxs-lookup"><span data-stu-id="35148-266">**Email after anti-spam, bulk mail filtering**</span></span>
- <span data-ttu-id="35148-267">**ユーザーとドメインの偽装後のメール**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35148-267">**Email after user and domain impersonation**<sup>\*</sup></span></span>
- <span data-ttu-id="35148-268">**ファイルと URL の削除後のメール**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35148-268">**Email after file and URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="35148-269">**配信後の保護後に良性として検出された電子メール (URL クリック時間保護)**</span><span class="sxs-lookup"><span data-stu-id="35148-269">**Email detected as benign after post-delivery protection (URL click time protection)**</span></span>

<span data-ttu-id="35148-270"><sup>\*</sup>Defender for Office 365のみ</span><span class="sxs-lookup"><span data-stu-id="35148-270"><sup>\*</sup> Defender for Office 365 only</span></span>

<span data-ttu-id="35148-271">EOP または Defender でフィルター処理されたメールを個別Office 365表示するには、グラフの凡例の値をクリックします。</span><span class="sxs-lookup"><span data-stu-id="35148-271">To view the email filtered by EOP or Defender for Office 365 separately, click on the value in the chart legend.</span></span>

<span data-ttu-id="35148-272">詳細テーブルには、降順に表示される次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="35148-272">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="35148-273">**Date**</span><span class="sxs-lookup"><span data-stu-id="35148-273">**Date**</span></span>
- <span data-ttu-id="35148-274">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="35148-274">**Total email**</span></span>
- <span data-ttu-id="35148-275">**エッジ保護**</span><span class="sxs-lookup"><span data-stu-id="35148-275">**Edge protection**</span></span>
- <span data-ttu-id="35148-276">**マルウェア対策、ファイル評価、ファイルの種類ブロック**:</span><span class="sxs-lookup"><span data-stu-id="35148-276">**Anti-malware, file reputation, file type block**:</span></span>
  - <span data-ttu-id="35148-277">**ファイル評価**: 他の Microsoft のお客様が添付ファイルを識別するためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="35148-277">**File reputation**: Messages filtered due to identification of an attached file by other Microsoft customers.</span></span>
  - <span data-ttu-id="35148-278">**ファイルの種類のブロック**: メッセージで識別された悪意のあるファイルの種類によってフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="35148-278">**File type block**: Messages filtered due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="35148-279">**フィッシング対策、URL レピュテーション、ブランド偽装、スプーフィング対策**:</span><span class="sxs-lookup"><span data-stu-id="35148-279">**Anti-phish, URL reputation, Brand impersonation, anti-spoof**:</span></span>
  - <span data-ttu-id="35148-280">**URL レピュ** テーション : 他の Microsoft のお客様による URL の識別のためにフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="35148-280">**URL reputation**: Messages filtered due to the identification of the URL by other Microsoft customers.</span></span>
  - <span data-ttu-id="35148-281">**ブランド偽装**: よく知られているブランド偽装送信者からのメッセージが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="35148-281">**Brand impersonation**: Messages filtered due to the message coming from well-known brand impersonating senders.</span></span>
  - <span data-ttu-id="35148-282">**スプーフィング** 対策: 受信者が属するドメイン、またはメッセージ送信者が所有していないドメインをスプーフィングしようとするメッセージが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="35148-282">**Anti-spoof**: Messages filtered due to the message attempting to spoof a domain that the recipient belongs to, or a domain that the message sender doesn't own.</span></span>
- <span data-ttu-id="35148-283">**スパム対策、バルク メール フィルター**:</span><span class="sxs-lookup"><span data-stu-id="35148-283">**Anti-spam, bulk mail filtering**:</span></span>
  - <span data-ttu-id="35148-284">**バルク メール フィルター :** スパム対策ポリシーの一括不平レベル (BCL) しきい値に基づいてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="35148-284">**Bulk mail filtering**: Messages filtered based on the bulk complain level (BCL) threshold in an anti-spam policy.</span></span>
- <span data-ttu-id="35148-285">**ユーザーとドメインの偽装 (Defender for Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="35148-285">**User and domain impersonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="35148-286">**ユーザー偽装**: フィッシング対策ポリシーの偽装保護設定で定義されているユーザー (メッセージ送信者) を偽装しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="35148-286">**User impersonation**: Messages filtered due to an attempt to impersonate a user (message sender) that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
  - <span data-ttu-id="35148-287">**ドメイン偽装**: フィッシング対策ポリシーの偽装保護設定で定義されているドメインを偽装しようとしてフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="35148-287">**Domain impersonation**: Messages filtered due to an attempt to impersonate a domain that's defined in the impersonation protection settings of an anti-phishing policy.</span></span>
- <span data-ttu-id="35148-288">**ファイルと URL のデトレーション (Defender for Office 365)**:</span><span class="sxs-lookup"><span data-stu-id="35148-288">**File and URL detonation (Defender for Office 365)**:</span></span>
  - <span data-ttu-id="35148-289">**ファイルの削除**: 添付ファイル ポリシーでフィルターセーフメッセージ。</span><span class="sxs-lookup"><span data-stu-id="35148-289">**File detonation**: Messages filtered by a Safe Attachments policy.</span></span>
  - <span data-ttu-id="35148-290">**URL の削除**: リンク ポリシーでフィルターセーフメッセージ。</span><span class="sxs-lookup"><span data-stu-id="35148-290">**URL detonation**: Message filtered by a Safe Links policy.</span></span>
- <span data-ttu-id="35148-291">**配信後の保護と ZAP (ATP)、または ZAP (EOP)**: マルウェア、スパム、フィッシングのゼロ時間自動削除 (ZAP)。</span><span class="sxs-lookup"><span data-stu-id="35148-291">**Post-delivery protection and ZAP (ATP), or ZAP (EOP)**: Zero-hour auto purge (ZAP) for malware, spam, and phishing.</span></span>

<span data-ttu-id="35148-292">詳細テーブルで行を選択すると、メール数の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-292">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-funnel-view"></a><span data-ttu-id="35148-293">ファネル ビューからエクスポートする</span><span class="sxs-lookup"><span data-stu-id="35148-293">Export from Funnel view</span></span>

<span data-ttu-id="35148-294">[オプション] で **[エクスポート]** **をクリック** すると、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="35148-294">After you click **Export** under **Options**, you can select one of the following values:</span></span>

- <span data-ttu-id="35148-295">**概要 (最大で過去 90 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="35148-295">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="35148-296">**詳細 (最大で過去 30 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="35148-296">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="35148-297">[ **日付] で** 範囲を選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-297">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="35148-298">現在のフィルターのデータは、特定のファイルに.csvされます。</span><span class="sxs-lookup"><span data-stu-id="35148-298">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="35148-299">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="35148-299">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="35148-300">データに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="35148-300">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![メールフロー状態レポートのファネル ビュー](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a><span data-ttu-id="35148-302">メールフローの状態レポートの技術ビュー</span><span class="sxs-lookup"><span data-stu-id="35148-302">Tech view for the Mailflow status report</span></span>

<span data-ttu-id="35148-303">Tech **ビューは、** ファネル **ビューに** 似ています。構成済みの脅威保護機能の詳細を提供します。</span><span class="sxs-lookup"><span data-stu-id="35148-303">The **Tech view** is similar to the **Funnel** view, providing more granular details for the configured threat protections features.</span></span> <span data-ttu-id="35148-304">グラフから、脅威保護の異なる段階でメッセージがどのように分類されるのか確認できます。</span><span class="sxs-lookup"><span data-stu-id="35148-304">From the chart, you can see how messages are categorized at the different stages of threat protection.</span></span>

<span data-ttu-id="35148-305">[Tech view] **タブを** クリックすると、既定では、このビューにはグラフと、次のフィルターで構成された詳細テーブルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="35148-305">If you click the **Tech view** tab, by default, this view contains a chart and a details table that's configured with the following filters:</span></span>

- <span data-ttu-id="35148-306">**日付**: 過去 7 日間。</span><span class="sxs-lookup"><span data-stu-id="35148-306">**Date**: The last 7 days.</span></span>

- <span data-ttu-id="35148-307">**方向**:</span><span class="sxs-lookup"><span data-stu-id="35148-307">**Direction**:</span></span>
  - <span data-ttu-id="35148-308">**受信**</span><span class="sxs-lookup"><span data-stu-id="35148-308">**Inbound**</span></span>
  - <span data-ttu-id="35148-309">**送信**</span><span class="sxs-lookup"><span data-stu-id="35148-309">**Outbound**</span></span>
  - <span data-ttu-id="35148-310">**組織内**: この数は、テナント内のメッセージ 、つまり</span><span class="sxs-lookup"><span data-stu-id="35148-310">**Intra-org**: this count is for messages within a tenant i.e</span></span> <span data-ttu-id="35148-311">送信者 abc@domain.com 受信者に送信 xyz@domain.com (受信および送信とは別にカウントされます)</span><span class="sxs-lookup"><span data-stu-id="35148-311">sender abc@domain.com sends to recipient xyz@domain.com (counted separately from Inbound and Outbound)</span></span>

<span data-ttu-id="35148-312">集計ビューと詳細テーブル ビューでは、90 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="35148-312">The aggregate view and details table view allow for 90 days of filtering.</span></span>

<span data-ttu-id="35148-313">これらのフィルターは、[フィルター] をクリックして **変更できます**。</span><span class="sxs-lookup"><span data-stu-id="35148-313">You can change these filters by clicking **Filter**.</span></span> <span data-ttu-id="35148-314">[種類] ビューの同 **じフィルターが** 使用されます。</span><span class="sxs-lookup"><span data-stu-id="35148-314">The same filters from the **Type** view are used.</span></span>

<span data-ttu-id="35148-315">このグラフには、次のカテゴリに分類されたメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-315">This chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="35148-316">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="35148-316">**Total email**</span></span>
- <span data-ttu-id="35148-317">**エッジ許可** と **フィルター処理されたエッジ**</span><span class="sxs-lookup"><span data-stu-id="35148-317">**Edge allow** and **Edge filtered**</span></span>
- <span data-ttu-id="35148-318">**トランスポート ルールの許可** と **トランスポート ルールのフィルター** 処理 (メール フロー ルール)</span><span class="sxs-lookup"><span data-stu-id="35148-318">**Transport rule allow** and **Transport rule filtered** (mail flow rules)</span></span>
- <span data-ttu-id="35148-319">**マルウェアではない\*\*\*\*、セーフ添付ファイルの検出、** <sup>\*</sup> **マルウェア対策エンジンの検出**</span><span class="sxs-lookup"><span data-stu-id="35148-319">**Not malware**, **Safe Attachments detection**<sup>\*</sup>, and **Anti-malware engine detection**</span></span>
- <span data-ttu-id="35148-320">**フィッシング** **、DMARC 障害、\*\*\*\*偽装検出、ス** プーフィング <sup>\*</sup> **検出**、**およびフィッシングの検出を行う**</span><span class="sxs-lookup"><span data-stu-id="35148-320">**Not phish**, **DMARC failure**, **Impersonation detection**<sup>\*</sup>, **Spoof detection**, and **Phish detection**</span></span>
- <span data-ttu-id="35148-321">**URL のデトレーションと URL の** デトレーション **検出による検出なし**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35148-321">**No detection with URL detonation** and **URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="35148-322">**スパムとスパム\*\*\*\*ではない**</span><span class="sxs-lookup"><span data-stu-id="35148-322">**Not spam** and  **Spam**</span></span>
- <span data-ttu-id="35148-323">**悪意のあるメール以外の電子\*\*\*\*メール、セーフリンクの検出** <sup>\*</sup> 、**および ZAP**</span><span class="sxs-lookup"><span data-stu-id="35148-323">**Non-malicious email**, **Safe Links detection**<sup>\*</sup>, and **ZAP**</span></span>

<span data-ttu-id="35148-324"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="35148-324"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="35148-325">グラフ内のカテゴリにカーソルを合わせると、そのカテゴリ内のメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-325">When you hover over a category in the chart, you can see the number of messages in that category.</span></span>

<span data-ttu-id="35148-326">詳細テーブルには、降順に表示される次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="35148-326">The details table contains the following information, shown in descending date order:</span></span>

- <span data-ttu-id="35148-327">**日付 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="35148-327">**Date (UTC)**</span></span>
- <span data-ttu-id="35148-328">**メールの総数**</span><span class="sxs-lookup"><span data-stu-id="35148-328">**Total email**</span></span>
- <span data-ttu-id="35148-329">**フィルター処理されたエッジ**</span><span class="sxs-lookup"><span data-stu-id="35148-329">**Edge filtered**</span></span>
- <span data-ttu-id="35148-330">**ルール メッセージ**: メール フロー ルール (トランスポート ルールとも呼ばれる) が原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="35148-330">**Rule messages**: Messages filtered due to  mail flow rules (also known as transport rules).</span></span>
- <span data-ttu-id="35148-331">**マルウェア対策エンジン、セーフ\*\*\*\*添付** <sup>\*</sup> ファイル:</span><span class="sxs-lookup"><span data-stu-id="35148-331">**Anti-malware engine**, **Safe Attachments**<sup>\*</sup>:</span></span>
- <span data-ttu-id="35148-332">**DMARC、 偽装** <sup>\*</sup> 、 ス **プーフィング**、**フィッシング フィルター**:</span><span class="sxs-lookup"><span data-stu-id="35148-332">**DMARC, impersonation**<sup>\*</sup>, **spoof**, **phish filtered**:</span></span>
  - <span data-ttu-id="35148-333">**DMARC**: DMARC 認証チェックに失敗したメッセージが原因でフィルター処理されたメッセージ。</span><span class="sxs-lookup"><span data-stu-id="35148-333">**DMARC**: Messages filtered due to the message failing its DMARC authentication check.</span></span>
- <span data-ttu-id="35148-334">**URL のデトレーション検出**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35148-334">**URL detonation detection**<sup>\*</sup></span></span>
- <span data-ttu-id="35148-335">**フィルター処理されたスパム対策**</span><span class="sxs-lookup"><span data-stu-id="35148-335">**Anti-spam filtered**</span></span>
- <span data-ttu-id="35148-336">**ZAP が削除されました**</span><span class="sxs-lookup"><span data-stu-id="35148-336">**ZAP removed**</span></span>
- <span data-ttu-id="35148-337">**リンクによるセーフ検出**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35148-337">**Detection by Safe Links**<sup>\*</sup></span></span>

<span data-ttu-id="35148-338"><sup>\*</sup>Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="35148-338"><sup>\*</sup> Defender for Office 365</span></span>

<span data-ttu-id="35148-339">詳細テーブルで行を選択すると、メール数の詳細がフライアウトに表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-339">If you select a row in the details table, a further breakdown of the email counts are shown in the flyout.</span></span>

#### <a name="export-from-tech-view"></a><span data-ttu-id="35148-340">Tech ビューからのエクスポート</span><span class="sxs-lookup"><span data-stu-id="35148-340">Export from Tech view</span></span>

<span data-ttu-id="35148-341">[エクスポート] **をクリックすると**、[ **オプション] で** 、次のいずれかの値を選択できます。</span><span class="sxs-lookup"><span data-stu-id="35148-341">On clicking **Export**, under **Options** you can select one of the following values:</span></span>

- <span data-ttu-id="35148-342">**概要 (最大で過去 90 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="35148-342">**Summary (with data for last 90 days at most)**</span></span>
- <span data-ttu-id="35148-343">**詳細 (最大で過去 30 日間のデータを含む)**</span><span class="sxs-lookup"><span data-stu-id="35148-343">**Details (with data for last 30 days at most)**</span></span>

<span data-ttu-id="35148-344">[ **日付] で** 範囲を選択し、[適用] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-344">Under **Date**, choose a range, and then click **Apply**.</span></span> <span data-ttu-id="35148-345">現在のフィルターのデータは、特定のファイルに.csvされます。</span><span class="sxs-lookup"><span data-stu-id="35148-345">Data for the current filters will be exported to a .csv file.</span></span>

<span data-ttu-id="35148-346">エクスポートされたファイル.csv、150,000 行に制限されます。</span><span class="sxs-lookup"><span data-stu-id="35148-346">Each exported .csv file is limited to 150,000 rows.</span></span> <span data-ttu-id="35148-347">データに 150,000 行を超える行が含まれている場合は、複数.csvファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="35148-347">If the data contains more than 150,000 rows, then multiple .csv files will be created.</span></span>

![メールフロー状態レポートの技術ビュー](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a><span data-ttu-id="35148-349">マルウェア検出レポート</span><span class="sxs-lookup"><span data-stu-id="35148-349">Malware detections report</span></span>

<span data-ttu-id="35148-350">[**マルウェア検出] レポート レポートには**、受信および送信電子メール メッセージ (マルウェアが受信または EOP によって検出Exchange Online Protection情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-350">The **Malware detections report** report shows information about malware detections in incoming and outgoing email messages (malware detected by Exchange Online Protection or EOP).</span></span> <span data-ttu-id="35148-351">EOP のマルウェア保護の詳細については、「EOP の [マルウェア対策保護」を参照してください](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="35148-351">For more information about malware protection in EOP, see [Anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="35148-352">集計ビュー フィルターでは 90 日間、詳細テーブル フィルターでは 10 日間のみ許可されます。</span><span class="sxs-lookup"><span data-stu-id="35148-352">The aggregate view filter allows for 90 days, while the details table filter only allows for 10 days.</span></span>

<span data-ttu-id="35148-353">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="35148-353">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="35148-354">[電子メール **の共有&] ページで** 、[ **電子メールで** 検出されたマルウェア] を探し、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-354">On the **Email & collaboration reports** page, find **Malware detected in email** and then click **View details**.</span></span> <span data-ttu-id="35148-355">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/MalwareDetections> 。</span><span class="sxs-lookup"><span data-stu-id="35148-355">To go directly to the report, open <https://security.microsoft.com/reports/MalwareDetections>.</span></span>

![[メール と共同作業レポート] ページの電子メール ウィジェット&検出](../../media/malware-detections-widget.png)

<span data-ttu-id="35148-357">[マルウェア **検出] レポート** ページで、[フィルター] をクリックし、次のいずれかの値を選択して、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="35148-357">On the **Malware detections report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one of the following values:</span></span>

- <span data-ttu-id="35148-358">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="35148-358">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="35148-359">**方向**:**受信および\*\*\*\*送信**</span><span class="sxs-lookup"><span data-stu-id="35148-359">**Direction**: **Inbound** and **Outbound**</span></span>

![電子メール レポートのマルウェア検出のレポート ビュー](../../media/malware-detections-report-view.png)

<span data-ttu-id="35148-361">グラフの下の詳細テーブルで、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="35148-361">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="35148-362">**Date**</span><span class="sxs-lookup"><span data-stu-id="35148-362">**Date**</span></span>
- <span data-ttu-id="35148-363">**[送信者のアドレス]**</span><span class="sxs-lookup"><span data-stu-id="35148-363">**Sender address**</span></span>
- <span data-ttu-id="35148-364">**受信者のアドレス**</span><span class="sxs-lookup"><span data-stu-id="35148-364">**Recipient address**</span></span>
- <span data-ttu-id="35148-365">**メッセージ ID**: メッセージ ヘッダーの **[Message-ID** ヘッダー] フィールドで使用できます。一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="35148-365">**Message ID**: Available in the **Message-ID** header field in the message header and should be unique.</span></span> <span data-ttu-id="35148-366">値の例は `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` 次のようになります (角かっこに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="35148-366">An example value is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (note the angle brackets).</span></span>
- <span data-ttu-id="35148-367">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="35148-367">**Subject**</span></span>
- <span data-ttu-id="35148-368">**Filename**</span><span class="sxs-lookup"><span data-stu-id="35148-368">**Filename**</span></span>
- <span data-ttu-id="35148-369">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="35148-369">**Malware name**</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="35148-370">メール遅延レポート</span><span class="sxs-lookup"><span data-stu-id="35148-370">Mail latency report</span></span>

<span data-ttu-id="35148-371">Defender **for Office 365** のメール待機時間レポートには、組織内で発生したメール配信と発Office 365に関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="35148-371">The **Mail latency report** in Defender for Office 365 contains information on the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="35148-372">詳細については、「メール遅延 [レポート」を参照してください](view-reports-for-mdo.md#mail-latency-report)。</span><span class="sxs-lookup"><span data-stu-id="35148-372">For more information, see [Mail latency report](view-reports-for-mdo.md#mail-latency-report).</span></span>

## <a name="spam-detections-report"></a><span data-ttu-id="35148-373">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="35148-373">Spam detections report</span></span>

> [!NOTE]
> <span data-ttu-id="35148-374">スパム **検出レポートは最終的** に消え去る。</span><span class="sxs-lookup"><span data-stu-id="35148-374">The **Spam detections report** will eventually go away.</span></span> <span data-ttu-id="35148-375">脅威保護の状態レポートでも同 [じ情報を使用できます](#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="35148-375">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="spoof-detections-report"></a><span data-ttu-id="35148-376">スプーフィング検出レポート</span><span class="sxs-lookup"><span data-stu-id="35148-376">Spoof detections report</span></span>

> [!NOTE]
> <span data-ttu-id="35148-377">この記事で説明するように改善されたスプーフィング検出レポートはプレビューで、変更される可能性があります。また、すべての組織で利用できるとは限られません。</span><span class="sxs-lookup"><span data-stu-id="35148-377">The improved Spoof detections report as described in this article is in Preview, is subject to change, and is not available in all organizations.</span></span> <span data-ttu-id="35148-378">レポートの以前のバージョンでは、良いメール **だけが表示され** 、スパム **としてキャッチされます**。</span><span class="sxs-lookup"><span data-stu-id="35148-378">The older version of the report shows only **Good mail** and **Caught as spam**.</span></span>

<span data-ttu-id="35148-379">ス **プーフィング検出レポート** には、スプーフィングによってブロックまたは許可されたメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-379">The **Spoof detections** report shows information about messages that were blocked or allowed due to spoofing.</span></span> <span data-ttu-id="35148-380">スプーフィングの詳細については、「EOP でのスプーフィング防止 [保護」を参照してください](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="35148-380">For more information about spoofing, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="35148-381">レポートの集計ビューでは 45 日間のフィルター処理が可能ですが、詳細ビューでは 10 日間のフィルター <sup>\*</sup> 処理のみ可能です。</span><span class="sxs-lookup"><span data-stu-id="35148-381">The aggregate view of the report allows for 45 days of filtering<sup>\*</sup>, while the detail view only allows for ten days of filtering.</span></span>

<span data-ttu-id="35148-382"><sup>\*</sup> 最終的には、最大 90 日間のフィルター処理を使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-382"><sup>\*</sup> Eventually, you'll be able to use up to 90 days of filtering.</span></span>

<span data-ttu-id="35148-383">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="35148-383">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="35148-384">[メール **の共有&] ページで** 、[スプーフィングの検出] **を探** し、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-384">On the **Email & collaboration reports** page, find **Spoof detections** and then click **View details**.</span></span> <span data-ttu-id="35148-385">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/SpoofMailReportV2> 。</span><span class="sxs-lookup"><span data-stu-id="35148-385">To go directly to the report, open <https://security.microsoft.com/reports/SpoofMailReportV2>.</span></span>

![[メール と共同作業レポート] ページ&スプーフィング検出ウィジェット](../../media/spoof-detections-widget.png)

<span data-ttu-id="35148-387">グラフには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-387">The chart shows the following information:</span></span>

- <span data-ttu-id="35148-388">**Pass**</span><span class="sxs-lookup"><span data-stu-id="35148-388">**Pass**</span></span>
- <span data-ttu-id="35148-389">**Fail/失敗**</span><span class="sxs-lookup"><span data-stu-id="35148-389">**Fail**</span></span>
- <span data-ttu-id="35148-390">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="35148-390">**SoftPass**</span></span>
- <span data-ttu-id="35148-391">**なし**</span><span class="sxs-lookup"><span data-stu-id="35148-391">**None**</span></span>
- <span data-ttu-id="35148-392">**その他**</span><span class="sxs-lookup"><span data-stu-id="35148-392">**Other**</span></span>

<span data-ttu-id="35148-393">グラフの 1 日 (データ ポイント) にカーソルを合わせると、スプーフィングされたメッセージの検出数と理由を確認できます。</span><span class="sxs-lookup"><span data-stu-id="35148-393">When you hover over a day (data point) in the chart, you can see how many spoofed messages were detected and why.</span></span>

<span data-ttu-id="35148-394">[スプー **フィング** メール レポート] ページで、[フィルター] をクリックし、次の値の 1 つ以上を選択して、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="35148-394">On the **Spoof mail report** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="35148-395">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="35148-395">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="35148-396">**結果**:</span><span class="sxs-lookup"><span data-stu-id="35148-396">**Result**:</span></span>
  - <span data-ttu-id="35148-397">**Pass**</span><span class="sxs-lookup"><span data-stu-id="35148-397">**Pass**</span></span>
  - <span data-ttu-id="35148-398">**Fail/失敗**</span><span class="sxs-lookup"><span data-stu-id="35148-398">**Fail**</span></span>
  - <span data-ttu-id="35148-399">**SoftPass**</span><span class="sxs-lookup"><span data-stu-id="35148-399">**SoftPass**</span></span>
  - <span data-ttu-id="35148-400">**なし**</span><span class="sxs-lookup"><span data-stu-id="35148-400">**None**</span></span>
  - <span data-ttu-id="35148-401">**その他**</span><span class="sxs-lookup"><span data-stu-id="35148-401">**Other**</span></span>
- <span data-ttu-id="35148-402">**スプーフィングの** 種類 :**内部と\*\*\*\*外部**</span><span class="sxs-lookup"><span data-stu-id="35148-402">**Spoof type**: **Internal** and **External**</span></span>

![[メール レポートのスプーフィング] ページ (Microsoft 365 Defender ポータル)](../../media/spoof-detections-report-page.png)

<span data-ttu-id="35148-404">グラフの下の詳細テーブルで、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="35148-404">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="35148-405">**Date**</span><span class="sxs-lookup"><span data-stu-id="35148-405">**Date**</span></span>
- <span data-ttu-id="35148-406">**スプーフィングされたユーザー**</span><span class="sxs-lookup"><span data-stu-id="35148-406">**Spoofed user**</span></span>
- <span data-ttu-id="35148-407">**インフラストラクチャの送信**</span><span class="sxs-lookup"><span data-stu-id="35148-407">**Sending infrastructure**</span></span>
- <span data-ttu-id="35148-408">**スプーフィングの種類**</span><span class="sxs-lookup"><span data-stu-id="35148-408">**Spoof type**</span></span>
- <span data-ttu-id="35148-409">**結果**</span><span class="sxs-lookup"><span data-stu-id="35148-409">**Result**</span></span>
- <span data-ttu-id="35148-410">**結果コード**</span><span class="sxs-lookup"><span data-stu-id="35148-410">**Result code**</span></span>
- <span data-ttu-id="35148-411">**SPF**</span><span class="sxs-lookup"><span data-stu-id="35148-411">**SPF**</span></span>
- <span data-ttu-id="35148-412">**DKIM**</span><span class="sxs-lookup"><span data-stu-id="35148-412">**DKIM**</span></span>
- <span data-ttu-id="35148-413">**DMARC**</span><span class="sxs-lookup"><span data-stu-id="35148-413">**DMARC**</span></span>
- <span data-ttu-id="35148-414">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="35148-414">**Message count**</span></span>

<span data-ttu-id="35148-415">複合認証結果コードの詳細については、「スパム対策メッセージ ヘッダー」を参照[Microsoft 365。](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="35148-415">For more information about composite authentication result codes, see [Anti-spam message headers in Microsoft 365](anti-spam-message-headers.md).</span></span>

## <a name="submissions-report"></a><span data-ttu-id="35148-416">申請レポート</span><span class="sxs-lookup"><span data-stu-id="35148-416">Submissions report</span></span>

<span data-ttu-id="35148-417">申請 **レポートには** 、管理者が分析のために Microsoft に報告したアイテムに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-417">The **Submissions** report shows information about items that admins have reported to Microsoft for analysis.</span></span> <span data-ttu-id="35148-418">詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35148-418">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="35148-419">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="35148-419">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="35148-420">[コラボレーション **レポートのメール&] ページで**、[申請] を探し、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-420">On the **Email & collaboration reports** page, find **Submissions** and then click **View details**.</span></span> <span data-ttu-id="35148-421">レポートに直接移動するには、を開きます <https://security.microsoft.com/adminSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="35148-421">To go directly to the report, open <https://security.microsoft.com/adminSubmissionReport>.</span></span> <span data-ttu-id="35148-422">ポータルで [管理者の申請に移動するには、[Microsoft 365 Defender提出](admin-submission.md)に移動 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-422">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![[コラボレーション レポートの電子メール] ページ&提出ウィジェット](../../media/submissions-report-widget.png)

<span data-ttu-id="35148-424">グラフには、次の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-424">The chart shows the following information:</span></span>

- <span data-ttu-id="35148-425">**Pending**</span><span class="sxs-lookup"><span data-stu-id="35148-425">**Pending**</span></span>
- <span data-ttu-id="35148-426">**Completed**</span><span class="sxs-lookup"><span data-stu-id="35148-426">**Completed**</span></span>

<span data-ttu-id="35148-427">[申請 **] ページ** で、[フィルター] をクリックし、次の値の1 つ以上を選択して、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="35148-427">On the **Submissions** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values:</span></span>

- <span data-ttu-id="35148-428">**報告日**: **開始時刻** と **終了時刻**</span><span class="sxs-lookup"><span data-stu-id="35148-428">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="35148-429">**申請の種類**:**電子メール\*\*\*\*、URL、\*\*\*\*またはファイル**</span><span class="sxs-lookup"><span data-stu-id="35148-429">**Submission type**: **Email**, **URL**, or **File**</span></span>
- <span data-ttu-id="35148-430">**申請 ID**</span><span class="sxs-lookup"><span data-stu-id="35148-430">**Submission ID**</span></span>
- <span data-ttu-id="35148-431">**ネットワーク メッセージ ID**</span><span class="sxs-lookup"><span data-stu-id="35148-431">**Network Message ID**</span></span>
- <span data-ttu-id="35148-432">**Sender**</span><span class="sxs-lookup"><span data-stu-id="35148-432">**Sender**</span></span>
- <span data-ttu-id="35148-433">**名前**</span><span class="sxs-lookup"><span data-stu-id="35148-433">**Name**</span></span>
- <span data-ttu-id="35148-434">**提出者**</span><span class="sxs-lookup"><span data-stu-id="35148-434">**Submitted by**</span></span>
- <span data-ttu-id="35148-435">**送信の理由**:**迷惑メール、フィッシング\*\*\*\*、マルウェア**、**スパム\*\*\*\*ではない**</span><span class="sxs-lookup"><span data-stu-id="35148-435">**Reason for submitting**: **Not junk**, **Phish**, **Malware**, or **Spam**</span></span>
- <span data-ttu-id="35148-436">**再スキャンの状態**:**保留中または\*\*\*\*完了**</span><span class="sxs-lookup"><span data-stu-id="35148-436">**Rescan status**: **Pending** or **Completed**</span></span>

<span data-ttu-id="35148-437">グラフの下の詳細テーブルは、同じ情報を示し、[グループ] または [グループのカスタマイズ] 列のオプションは、[電子メール と共同作業の申請] の [分析用に送信済み] タブと同 **&です** \> 。</span><span class="sxs-lookup"><span data-stu-id="35148-437">The details table below the graph shows the same information and has the same **Group** or **Customize columns** options as on the **Submitted for analysis** tab at **Email & collaboration** \> **Submissions**.</span></span> <span data-ttu-id="35148-438">詳細については [、「View admin submissions to Microsoft」を参照してください](admin-submission.md#view-admin-submissions-to-microsoft)。</span><span class="sxs-lookup"><span data-stu-id="35148-438">For more information, see [View admin submissions to Microsoft](admin-submission.md#view-admin-submissions-to-microsoft).</span></span>

![ポータルの申請レポート ページMicrosoft 365 Defenderページ](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a><span data-ttu-id="35148-440">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="35148-440">Threat protection status report</span></span>

<span data-ttu-id="35148-441">脅威 **保護の状態レポート** は、EOP と Defender の両方Office 365。ただし、レポートには異なるデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="35148-441">The **Threat protection status** report is available in both EOP and Defender for Office 365; however, the reports contain different data.</span></span> <span data-ttu-id="35148-442">たとえば、EOP のお客様は、電子メールで検出されたマルウェアに関する情報を表示できますが[、SharePoint、OneDrive、](mdo-for-spo-odb-and-teams.md)および Microsoft Teams の セーフ 添付ファイルによって検出された悪意のあるファイルに関する情報は表示できません。</span><span class="sxs-lookup"><span data-stu-id="35148-442">For example, EOP customers can view information about malware detected in email, but not information about malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="35148-443">このレポートには、マルウェア対策エンジンによってブロックされたファイルや Web サイト アドレス (URL)、ゼロ時間自動削除[(ZAP)、セーフ](zero-hour-auto-purge.md)[リンク、セーフ](safe-links.md)[添付](safe-attachments.md)ファイル、フィッシング対策ポリシーの偽装保護機能などの Office 365 機能の Defender などの悪意のあるコンテンツを含[](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)む電子メール メッセージの数が提供されます。</span><span class="sxs-lookup"><span data-stu-id="35148-443">The report provides the count of email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Defender for Office 365 features like [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [impersonation protection features in anti-phishing policies](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).</span></span> <span data-ttu-id="35148-444">この情報を使用して、傾向を特定したり、組織のポリシーで調整が必要かどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="35148-444">You can use this information to identify trends or determine whether organization policies need adjustment.</span></span>

<span data-ttu-id="35148-445">**注**: メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="35148-445">**Note**: It's important to understand that if a message is sent to five recipients we count it as five different messages and not one message.</span></span>

<span data-ttu-id="35148-446">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="35148-446">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="35148-447">[電子 **メール &コラボレーション レポート]** ページで、[脅威保護の状態] **を探し** 、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-447">On the **Email & collaboration reports** page, find **Threat protection status** and then click **View details**.</span></span> <span data-ttu-id="35148-448">レポートに直接移動するには、次のいずれかの URL を開きます。</span><span class="sxs-lookup"><span data-stu-id="35148-448">To go directly to the report, open one of the following URLs:</span></span>

- <span data-ttu-id="35148-449">Defender for Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP></span><span class="sxs-lookup"><span data-stu-id="35148-449">Defender for Office 365: <https://security.microsoft.com/reports/TPSAggregateReportATP></span></span>
- <span data-ttu-id="35148-450">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span><span class="sxs-lookup"><span data-stu-id="35148-450">EOP: <https://security.microsoft.com/reports/TPSAggregateReport></span></span>

![[メール] グループの [コラボレーション レポート] ページ&の脅威保護状態ウィジェット](../../media/threat-protection-status-report-widget.png)

<span data-ttu-id="35148-452">既定では、グラフには過去 7 日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-452">By default, the chart shows data for the past 7 days.</span></span> <span data-ttu-id="35148-453">[脅威保護状態 **レポート]\*\*\*\*ページで**[フィルター] をクリックすると、90 日間の日付範囲を選択できます (試用版サブスクリプションは 30 日間に制限される場合があります)。</span><span class="sxs-lookup"><span data-stu-id="35148-453">If you click **Filter** on the **Threat protection status report** page, you can select a 90 day date range (trial subscriptions might be limited to 30 days).</span></span> <span data-ttu-id="35148-454">詳細テーブルでは、30 日間のフィルター処理が可能です。</span><span class="sxs-lookup"><span data-stu-id="35148-454">The details table allows filtering for 30 days.</span></span>

<span data-ttu-id="35148-455">使用可能なビューについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="35148-455">The available views are described in the following sections.</span></span>

### <a name="view-data-by-overview"></a><span data-ttu-id="35148-456">概要でデータを表示する</span><span class="sxs-lookup"><span data-stu-id="35148-456">View data by Overview</span></span>

![脅威保護の状態レポートの概要ビュー](../../media/threat-protection-status-report-overview-view.png)

<span data-ttu-id="35148-458">[概要で **データを表示]** ビューでは、次の検出情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-458">In the **View data by Overview** view, the following detection information is shown in the chart:</span></span>

- <span data-ttu-id="35148-459">**電子メール マルウェア**</span><span class="sxs-lookup"><span data-stu-id="35148-459">**Email malware**</span></span>
- <span data-ttu-id="35148-460">**メールフィッシング**</span><span class="sxs-lookup"><span data-stu-id="35148-460">**Email phish**</span></span>
- <span data-ttu-id="35148-461">**コンテンツ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="35148-461">**Content malware**</span></span>

<span data-ttu-id="35148-462">グラフの下に詳細テーブルはありません。</span><span class="sxs-lookup"><span data-stu-id="35148-462">No details table is available below the chart.</span></span>

<span data-ttu-id="35148-463">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-463">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="35148-464">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="35148-464">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="35148-465">**検出**: **電子メール マルウェア**、 **メールフィッシング**、 **またはコンテンツ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="35148-465">**Detection**: **Email malware**, **Email phish**, or **Content malware**</span></span>
- <span data-ttu-id="35148-466">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="35148-466">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="35148-467">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="35148-467">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="35148-468">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="35148-468">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="35148-469">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="35148-469">**Direction**</span></span>
- <span data-ttu-id="35148-470">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="35148-470">**Domain**</span></span>
- <span data-ttu-id="35148-471">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="35148-471">**Policy type**</span></span>

<span data-ttu-id="35148-472">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-472">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="35148-473">検出テクノロジによってメール \> フィッシングとグラフの内訳でデータを表示する</span><span class="sxs-lookup"><span data-stu-id="35148-473">View data by Email \> Phish and Chart breakdown by Detection Technology</span></span>

![脅威保護状態レポートでのフィッシングメールの検出テクノロジ ビュー](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

<span data-ttu-id="35148-475">[**メール フィッシングによるデータの表示 \> ] ビューと\*\*\*\*[検出** テクノロジによるグラフの内訳] ビューでは、次の情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-475">In the **View data by Email \> Phish** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="35148-476">**URL 悪意のある評判**: Defender から生成された悪意のある URL レピュテーションOffice 365他のユーザーのMicrosoft 365 <sup>\*</sup> です。</span><span class="sxs-lookup"><span data-stu-id="35148-476">**URL malicious reputation**<sup>\*</sup>: Malicious URL reputation generated from Defender for Office 365 detonations in other Microsoft 365 customers.</span></span>
- <span data-ttu-id="35148-477">**高度なフィルター**: 機械学習に基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="35148-477">**Advanced filter**: Phishing signals based on machine learning.</span></span>
- <span data-ttu-id="35148-478">**一般的なフィルター**: アナリスト ルールに基づくフィッシングシグナル。</span><span class="sxs-lookup"><span data-stu-id="35148-478">**General filter**: Phishing signals based on analyst rules.</span></span>
- <span data-ttu-id="35148-479">**組織内のスプーフィング**: 送信者が受信者ドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="35148-479">**Spoof intra-org**: Sender is trying to spoof the recipient domain.</span></span>
- <span data-ttu-id="35148-480">**スプーフィング外部ドメイン**: 送信者が他のドメインをスプーフィングしようとしている。</span><span class="sxs-lookup"><span data-stu-id="35148-480">**Spoof external domain**: Sender is trying to spoof some other domain.</span></span>
- <span data-ttu-id="35148-481">**スプーフィング DMARC**: メッセージの DMARC 認証エラー。</span><span class="sxs-lookup"><span data-stu-id="35148-481">**Spoof DMARC**: DMARC authentication failure on messages.</span></span>
- <span data-ttu-id="35148-482">**偽装ブランド**: 送信者に基づく既知のブランドの偽装。</span><span class="sxs-lookup"><span data-stu-id="35148-482">**Impersonation brand**: Impersonation of well-known brands based on senders.</span></span>
- <span data-ttu-id="35148-483">**複合分析の検出**</span><span class="sxs-lookup"><span data-stu-id="35148-483">**Mixed analysis detection**</span></span>
- <span data-ttu-id="35148-484">**ファイルの評価**</span><span class="sxs-lookup"><span data-stu-id="35148-484">**File reputation**</span></span>
- <span data-ttu-id="35148-485">**指紋の一致**</span><span class="sxs-lookup"><span data-stu-id="35148-485">**Fingerprint matching**</span></span>
- <span data-ttu-id="35148-486">**URL のデトレーション評価**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35148-486">**URL detonation reputation**<sup>\*</sup></span></span>
- <span data-ttu-id="35148-487">**URL のデトナレーション**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35148-487">**URL detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="35148-488">**偽装ユーザー**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35148-488">**Impersonation user**<sup>\*</sup></span></span>
- <span data-ttu-id="35148-489">**偽装ドメイン** <sup>\*</sup> : 顧客が所有または定義するドメインの偽装。</span><span class="sxs-lookup"><span data-stu-id="35148-489">**Impersonation domain**<sup>\*</sup>: Impersonation of domains that the customer owns or defines.</span></span>
- <span data-ttu-id="35148-490">**メールボックス インテリジェンスの偽装**: 管理者によって定義されたユーザー、またはメールボックス インテリジェンスによって学習された <sup>\*</sup> ユーザーの偽装。</span><span class="sxs-lookup"><span data-stu-id="35148-490">**Mailbox intelligence impersonation**<sup>\*</sup>: Impersonation of users defined by admin or learned through mailbox intelligence.</span></span>
- <span data-ttu-id="35148-491">**ファイルのデトレーション**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35148-491">**File detonation**<sup>\*</sup></span></span>
- <span data-ttu-id="35148-492">**キャンペーン**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35148-492">**Campaign**<sup>\*</sup></span></span>

<span data-ttu-id="35148-493">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-493">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="35148-494">**Date**</span><span class="sxs-lookup"><span data-stu-id="35148-494">**Date**</span></span>
- <span data-ttu-id="35148-495">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="35148-495">**Subject**</span></span>
- <span data-ttu-id="35148-496">**送信者**</span><span class="sxs-lookup"><span data-stu-id="35148-496">**Sender**</span></span>
- <span data-ttu-id="35148-497">**受信者**</span><span class="sxs-lookup"><span data-stu-id="35148-497">**Recipients**</span></span>
- <span data-ttu-id="35148-498">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="35148-498">**Detected by**</span></span>
- <span data-ttu-id="35148-499">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="35148-499">**Delivery Status**</span></span>
- <span data-ttu-id="35148-500">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="35148-500">**Source of Compromise**</span></span>
- <span data-ttu-id="35148-501">**Tags**</span><span class="sxs-lookup"><span data-stu-id="35148-501">**Tags**</span></span>

<span data-ttu-id="35148-502">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-502">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="35148-503">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="35148-503">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="35148-504">**検出**</span><span class="sxs-lookup"><span data-stu-id="35148-504">**Detection**</span></span>
- <span data-ttu-id="35148-505">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="35148-505">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="35148-506">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="35148-506">**Direction**</span></span>
- <span data-ttu-id="35148-507">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="35148-507">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="35148-508">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="35148-508">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="35148-509">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="35148-509">**Domain**</span></span>
- <span data-ttu-id="35148-510">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="35148-510">**Policy type**</span></span>
- <span data-ttu-id="35148-511">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="35148-511">**Policy name** (details table only)</span></span>
- <span data-ttu-id="35148-512">**受信者**</span><span class="sxs-lookup"><span data-stu-id="35148-512">**Recipients**</span></span>

<span data-ttu-id="35148-513">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-513">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a><span data-ttu-id="35148-514">検出テクノロジによってメール \> マルウェアとグラフの内訳でデータを表示する</span><span class="sxs-lookup"><span data-stu-id="35148-514">View data by Email \> Malware and Chart breakdown by Detection Technology</span></span>

![脅威保護状態レポートのマルウェアの検出テクノロジ ビュー](../../media/threat-protection-status-report-malware-detection-tech-view.png)

<span data-ttu-id="35148-516">[電子メール **マルウェアによる \> データの** 表示] ビューと **[検出** テクノロジによるグラフの内訳] ビューでは、次の情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-516">In the **View data by Email \> Malware** and **Chart breakdown by Detection Technology** view, the following information is shown in the chart:</span></span>

- <span data-ttu-id="35148-517">**ファイルの削除** <sup>\*</sup> : 添付ファイルセーフ検出。</span><span class="sxs-lookup"><span data-stu-id="35148-517">**File detonation**<sup>\*</sup>: Detection by Safe Attachments.</span></span>
- <span data-ttu-id="35148-518">**ファイルの削除評価**: すべての悪意のあるファイルレピュテーションが Defender によって生成され、Office 365 <sup>\*</sup> されます。</span><span class="sxs-lookup"><span data-stu-id="35148-518">**File detonation reputation**<sup>\*</sup>: All malicious file reputation generated by Defender for Office 365 detonations.</span></span>
- <span data-ttu-id="35148-519">**ファイルの評価**</span><span class="sxs-lookup"><span data-stu-id="35148-519">**File reputation**</span></span>
- <span data-ttu-id="35148-520">**マルウェア対策エンジン** <sup>\*</sup> : マルウェア対策エンジンからの検出。</span><span class="sxs-lookup"><span data-stu-id="35148-520">**Anti-malware engine**<sup>\*</sup>: Detection from anti-malware engines.</span></span>
- <span data-ttu-id="35148-521">**マルウェア対策ポリシー ファイルの種類ブロック**: これらは、メッセージで識別された悪意のあるファイルの種類によってフィルター処理された電子メール メッセージです。</span><span class="sxs-lookup"><span data-stu-id="35148-521">**Anti-malware policy file type block**: These are email messages filtered out due to the type of malicious file identified in the message.</span></span>
- <span data-ttu-id="35148-522">**URL に悪意があるとする評価**</span><span class="sxs-lookup"><span data-stu-id="35148-522">**URL malicious reputation**</span></span>
- <span data-ttu-id="35148-523">**URL のデトネーション**</span><span class="sxs-lookup"><span data-stu-id="35148-523">**URL detonation**</span></span>
- <span data-ttu-id="35148-524">**URL のデトネーションの評価**</span><span class="sxs-lookup"><span data-stu-id="35148-524">**URL detonation reputation**</span></span>
- <span data-ttu-id="35148-525">**キャンペーン**</span><span class="sxs-lookup"><span data-stu-id="35148-525">**Campaign**</span></span>

<span data-ttu-id="35148-526">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-526">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="35148-527">**Date**</span><span class="sxs-lookup"><span data-stu-id="35148-527">**Date**</span></span>
- <span data-ttu-id="35148-528">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="35148-528">**Subject**</span></span>
- <span data-ttu-id="35148-529">**送信者**</span><span class="sxs-lookup"><span data-stu-id="35148-529">**Sender**</span></span>
- <span data-ttu-id="35148-530">**受信者**</span><span class="sxs-lookup"><span data-stu-id="35148-530">**Recipients**</span></span>
- <span data-ttu-id="35148-531">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="35148-531">**Detected by**</span></span>
- <span data-ttu-id="35148-532">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="35148-532">**Delivery Status**</span></span>
- <span data-ttu-id="35148-533">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="35148-533">**Source of Compromise**</span></span>
- <span data-ttu-id="35148-534">**Tags**</span><span class="sxs-lookup"><span data-stu-id="35148-534">**Tags**</span></span>

<span data-ttu-id="35148-535">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-535">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="35148-536">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="35148-536">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="35148-537">**検出**</span><span class="sxs-lookup"><span data-stu-id="35148-537">**Detection**</span></span>
- <span data-ttu-id="35148-538">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="35148-538">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="35148-539">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="35148-539">**Direction**</span></span>
- <span data-ttu-id="35148-540">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="35148-540">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="35148-541">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="35148-541">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="35148-542">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="35148-542">**Domain**</span></span>
- <span data-ttu-id="35148-543">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="35148-543">**Policy type**</span></span>
- <span data-ttu-id="35148-544">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="35148-544">**Policy name** (details table only)</span></span>
- <span data-ttu-id="35148-545">**受信者**</span><span class="sxs-lookup"><span data-stu-id="35148-545">**Recipients**</span></span>

<span data-ttu-id="35148-546">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-546">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="35148-547">ポリシーの種類別のグラフの内訳とメールフィッシングによるデータの表示 \> またはメール マルウェアによるデータの \> 表示</span><span class="sxs-lookup"><span data-stu-id="35148-547">Chart breakdown by Policy type and View data by Email \> Phish or View data by Email \> Malware</span></span>

![脅威保護状態レポートのフィッシングメールまたはマルウェアメールのポリシーの種類の表示](../../media/threat-protection-status-report-phishing-policy-type-view.png)

<span data-ttu-id="35148-549">[ポリシーの **種類別グラフ] ビューと**[メール フィッシングによるデータの表示] ビューまたは [メール マルウェアによるデータの表示] ビューでは、次の情報がグラフに表示されます。 **\>** **\>**</span><span class="sxs-lookup"><span data-stu-id="35148-549">In the **Chart breakdown by Policy type** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="35148-550">**マルウェア対策**</span><span class="sxs-lookup"><span data-stu-id="35148-550">**Anti-malware**</span></span>
- <span data-ttu-id="35148-551">**セーフ添付ファイル**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="35148-551">**Safe Attachments**<sup>\*</sup></span></span>
- <span data-ttu-id="35148-552">**フィッシング対策**</span><span class="sxs-lookup"><span data-stu-id="35148-552">**Anti-phish**</span></span>
- <span data-ttu-id="35148-553">**スパム対策**</span><span class="sxs-lookup"><span data-stu-id="35148-553">**Anti-spam**</span></span>
- <span data-ttu-id="35148-554">**メール フロー ルール** (トランスポート ルールとも呼ばれる)</span><span class="sxs-lookup"><span data-stu-id="35148-554">**Mail flow rule** (also known as a transport rule)</span></span>
- <span data-ttu-id="35148-555">**Others**</span><span class="sxs-lookup"><span data-stu-id="35148-555">**Others**</span></span>

<span data-ttu-id="35148-556">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-556">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="35148-557">**Date**</span><span class="sxs-lookup"><span data-stu-id="35148-557">**Date**</span></span>
- <span data-ttu-id="35148-558">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="35148-558">**Subject**</span></span>
- <span data-ttu-id="35148-559">**送信者**</span><span class="sxs-lookup"><span data-stu-id="35148-559">**Sender**</span></span>
- <span data-ttu-id="35148-560">**受信者**</span><span class="sxs-lookup"><span data-stu-id="35148-560">**Recipients**</span></span>
- <span data-ttu-id="35148-561">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="35148-561">**Detected by**</span></span>
- <span data-ttu-id="35148-562">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="35148-562">**Delivery Status**</span></span>
- <span data-ttu-id="35148-563">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="35148-563">**Source of Compromise**</span></span>
- <span data-ttu-id="35148-564">**Tags**</span><span class="sxs-lookup"><span data-stu-id="35148-564">**Tags**</span></span>

<span data-ttu-id="35148-565">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-565">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="35148-566">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="35148-566">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="35148-567">**検出**</span><span class="sxs-lookup"><span data-stu-id="35148-567">**Detection**</span></span>
- <span data-ttu-id="35148-568">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="35148-568">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="35148-569">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="35148-569">**Direction**</span></span>
- <span data-ttu-id="35148-570">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="35148-570">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="35148-571">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="35148-571">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="35148-572">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="35148-572">**Domain**</span></span>
- <span data-ttu-id="35148-573">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="35148-573">**Policy type**</span></span>
- <span data-ttu-id="35148-574">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="35148-574">**Policy name** (details table only)</span></span>
- <span data-ttu-id="35148-575">**受信者**</span><span class="sxs-lookup"><span data-stu-id="35148-575">**Recipients**</span></span>

<span data-ttu-id="35148-576">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-576">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a><span data-ttu-id="35148-577">[配信の状態] と [メールフィッシングによるデータの表示] または [ \> メール マルウェアによるデータの表示] によるグラフの \> 内訳</span><span class="sxs-lookup"><span data-stu-id="35148-577">Chart breakdown by Delivery status and View data by Email \> Phish or View data by Email \> Malware</span></span>

![脅威保護状態レポートのフィッシングメールとマルウェアメールの配信状態ビュー](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<span data-ttu-id="35148-579">[配信 **状態別グラフの内訳]** ビューと [メール フィッシングによるデータの表示] ビューまたは [メール マルウェアによるデータの表示] ビューでは、次の情報がグラフに表示されます。 **\>** **\>**</span><span class="sxs-lookup"><span data-stu-id="35148-579">In the **Chart breakdown by Delivery status** and **View data by Email \> Phish** or **View data by Email \> Malware** views, the following information is shown in the charts:</span></span>

- <span data-ttu-id="35148-580">**ホストされたメールボックス: 受信トレイ**</span><span class="sxs-lookup"><span data-stu-id="35148-580">**Hosted mailbox: Inbox**</span></span>
- <span data-ttu-id="35148-581">**ホストされたメールボックス: 迷惑メール**</span><span class="sxs-lookup"><span data-stu-id="35148-581">**Hosted mailbox: Junk**</span></span>
- <span data-ttu-id="35148-582">**ホストされたメールボックス: カスタム フォルダー**</span><span class="sxs-lookup"><span data-stu-id="35148-582">**Hosted mailbox: Custom folder**</span></span>
- <span data-ttu-id="35148-583">**ホストされたメールボックス: 削除済みアイテム**</span><span class="sxs-lookup"><span data-stu-id="35148-583">**Hosted mailbox: Deleted items**</span></span>
- <span data-ttu-id="35148-584">**Forwarded**</span><span class="sxs-lookup"><span data-stu-id="35148-584">**Forwarded**</span></span>
- <span data-ttu-id="35148-585">**オンプレミス サーバー: 配信**</span><span class="sxs-lookup"><span data-stu-id="35148-585">**On-premises server: Delivered**</span></span>
- <span data-ttu-id="35148-586">**検疫**</span><span class="sxs-lookup"><span data-stu-id="35148-586">**Quarantine**</span></span>
- <span data-ttu-id="35148-587">**配信に失敗しました**</span><span class="sxs-lookup"><span data-stu-id="35148-587">**Delivery failed**</span></span>
- <span data-ttu-id="35148-588">**ドロップ**</span><span class="sxs-lookup"><span data-stu-id="35148-588">**Dropped**</span></span>

<span data-ttu-id="35148-589">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-589">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="35148-590">**Date**</span><span class="sxs-lookup"><span data-stu-id="35148-590">**Date**</span></span>
- <span data-ttu-id="35148-591">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="35148-591">**Subject**</span></span>
- <span data-ttu-id="35148-592">**送信者**</span><span class="sxs-lookup"><span data-stu-id="35148-592">**Sender**</span></span>
- <span data-ttu-id="35148-593">**受信者**</span><span class="sxs-lookup"><span data-stu-id="35148-593">**Recipients**</span></span>
- <span data-ttu-id="35148-594">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="35148-594">**Detected by**</span></span>
- <span data-ttu-id="35148-595">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="35148-595">**Delivery Status**</span></span>
- <span data-ttu-id="35148-596">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="35148-596">**Source of Compromise**</span></span>
- <span data-ttu-id="35148-597">**Tags**</span><span class="sxs-lookup"><span data-stu-id="35148-597">**Tags**</span></span>

<span data-ttu-id="35148-598">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-598">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="35148-599">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="35148-599">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="35148-600">**検出**</span><span class="sxs-lookup"><span data-stu-id="35148-600">**Detection**</span></span>
- <span data-ttu-id="35148-601">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="35148-601">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="35148-602">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="35148-602">**Direction**</span></span>
- <span data-ttu-id="35148-603">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="35148-603">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="35148-604">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="35148-604">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="35148-605">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="35148-605">**Domain**</span></span>
- <span data-ttu-id="35148-606">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="35148-606">**Policy type**</span></span>
- <span data-ttu-id="35148-607">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="35148-607">**Policy name** (details table only)</span></span>
- <span data-ttu-id="35148-608">**受信者**</span><span class="sxs-lookup"><span data-stu-id="35148-608">**Recipients**</span></span>

<span data-ttu-id="35148-609">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-609">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-content--malware"></a><span data-ttu-id="35148-610">コンテンツ マルウェアによるデータの \> 表示</span><span class="sxs-lookup"><span data-stu-id="35148-610">View data by Content \> Malware</span></span>

![脅威保護状態レポートのコンテンツ マルウェア ビュー](../../media/threat-protection-status-report-content-malware-view.png)

<span data-ttu-id="35148-612">[コンテンツ **マルウェアによるデータ \> の** 表示] ビューでは、組織の Microsoft Defender のグラフに次のOffice 365示されています。</span><span class="sxs-lookup"><span data-stu-id="35148-612">In the **View data by Content \> Malware** view, the following information is shown in the chart for Microsoft Defender for Office 365 organizations:</span></span>

- <span data-ttu-id="35148-613">**マルウェア対策エンジン**: Sharepoint、OneDrive、および Microsoft Teams で組み込みのウイルス検出によって検出された悪意のある [Microsoft 365。](virus-detection-in-spo.md)</span><span class="sxs-lookup"><span data-stu-id="35148-613">**Anti-malware engine**: Malicious files detected in Sharepoint, OneDrive, and Microsoft Teams by the [built-in virus detection in Microsoft 365](virus-detection-in-spo.md).</span></span>
- <span data-ttu-id="35148-614">**ファイルの削除**: 添付ファイルによって検出された悪意のある [セーフ、SharePoint、OneDrive、](mdo-for-spo-odb-and-teams.md)およびMicrosoft Teams。</span><span class="sxs-lookup"><span data-stu-id="35148-614">**File detonation**: Malicious files detected by [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="35148-615">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-615">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="35148-616">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="35148-616">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="35148-617">**場所**</span><span class="sxs-lookup"><span data-stu-id="35148-617">**Location**</span></span>
- <span data-ttu-id="35148-618">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="35148-618">**Detected by**</span></span>
- <span data-ttu-id="35148-619">**マルウェア名**</span><span class="sxs-lookup"><span data-stu-id="35148-619">**Malware name**</span></span>

<span data-ttu-id="35148-620">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-620">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="35148-621">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="35148-621">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="35148-622">**検出**:**マルウェア対策エンジンまたは\*\*\*\*ファイルの削除**</span><span class="sxs-lookup"><span data-stu-id="35148-622">**Detection**: **Anti-malware engine** or **File detonation**</span></span>

<span data-ttu-id="35148-623">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-623">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

### <a name="view-data-by-system-override"></a><span data-ttu-id="35148-624">システムオーバーライドによるデータの表示</span><span class="sxs-lookup"><span data-stu-id="35148-624">View data by System override</span></span>

![脅威保護状態レポートのメッセージの上書きビュー](../../media/threat-protection-status-report-message-override-view.png)

<span data-ttu-id="35148-626">[システムによる **データの表示] オーバーライド** ビューでは、次のオーバーライド理由情報がグラフに表示されます。</span><span class="sxs-lookup"><span data-stu-id="35148-626">In the **View data by System override** view, the following override reason information is shown in the chart:</span></span>

- <span data-ttu-id="35148-627">**オンプレミスのスキップ**</span><span class="sxs-lookup"><span data-stu-id="35148-627">**On-premises skip**</span></span>
- <span data-ttu-id="35148-628">**IP 許可**</span><span class="sxs-lookup"><span data-stu-id="35148-628">**IP allow**</span></span>
- <span data-ttu-id="35148-629">**Exchange トランスポート ルール**(メール フロー ルール)</span><span class="sxs-lookup"><span data-stu-id="35148-629">**Exchange mail transport rule** (mail flow rule)</span></span>
- <span data-ttu-id="35148-630">**組織で許可されている送信者**</span><span class="sxs-lookup"><span data-stu-id="35148-630">**Organization allowed senders**</span></span>
- <span data-ttu-id="35148-631">**組織で許可されているドメイン**</span><span class="sxs-lookup"><span data-stu-id="35148-631">**Organization allowed domains**</span></span>
- <span data-ttu-id="35148-632">**ZAP が有効になっていません**</span><span class="sxs-lookup"><span data-stu-id="35148-632">**ZAP not enabled**</span></span>
- <span data-ttu-id="35148-633">**迷惑メール フォルダーが有効になっていない**</span><span class="sxs-lookup"><span data-stu-id="35148-633">**Junk Mail folder not enabled**</span></span>
- <span data-ttu-id="35148-634">**ユーザーセーフ送信者**</span><span class="sxs-lookup"><span data-stu-id="35148-634">**User Safe Sender**</span></span>
- <span data-ttu-id="35148-635">**ユーザー セーフ ドメイン**</span><span class="sxs-lookup"><span data-stu-id="35148-635">**User Safe Domain**</span></span>

<span data-ttu-id="35148-636">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-636">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="35148-637">**Date**</span><span class="sxs-lookup"><span data-stu-id="35148-637">**Date**</span></span>
- <span data-ttu-id="35148-638">**[件名]**</span><span class="sxs-lookup"><span data-stu-id="35148-638">**Subject**</span></span>
- <span data-ttu-id="35148-639">**送信者**</span><span class="sxs-lookup"><span data-stu-id="35148-639">**Sender**</span></span>
- <span data-ttu-id="35148-640">**受信者**</span><span class="sxs-lookup"><span data-stu-id="35148-640">**Recipients**</span></span>
- <span data-ttu-id="35148-641">**によって検出される**</span><span class="sxs-lookup"><span data-stu-id="35148-641">**Detected by**</span></span>
- <span data-ttu-id="35148-642">**配信状態**</span><span class="sxs-lookup"><span data-stu-id="35148-642">**Delivery Status**</span></span>
- <span data-ttu-id="35148-643">**侵害のソース**</span><span class="sxs-lookup"><span data-stu-id="35148-643">**Source of Compromise**</span></span>
- <span data-ttu-id="35148-644">**Tags**</span><span class="sxs-lookup"><span data-stu-id="35148-644">**Tags**</span></span>

<span data-ttu-id="35148-645">[フィルター] を **クリックすると**、次のフィルターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="35148-645">If you click **Filter**, the following filters are available:</span></span>

- <span data-ttu-id="35148-646">**日付 (UTC)** **開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="35148-646">**Date (UTC)** **Start date** and **End date**</span></span>
- <span data-ttu-id="35148-647">**検出**</span><span class="sxs-lookup"><span data-stu-id="35148-647">**Detection**</span></span>
- <span data-ttu-id="35148-648">**保護:** **MDO** (Defender for Office 365)**または EOP**</span><span class="sxs-lookup"><span data-stu-id="35148-648">**Protected by**: **MDO** (Defender for Office 365) or **EOP**</span></span>
- <span data-ttu-id="35148-649">**[方向]**</span><span class="sxs-lookup"><span data-stu-id="35148-649">**Direction**</span></span>
- <span data-ttu-id="35148-650">**タグ**: 指定したユーザー タグが適用されているユーザーまたはグループ (優先度アカウントを含む) によって結果をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="35148-650">**Tag**: Filter the results by users or groups that have had the specified user tag applied (including priority accounts).</span></span> <span data-ttu-id="35148-651">ユーザー タグの詳細については、「ユーザー タグ」 [を参照してください](user-tags.md)。</span><span class="sxs-lookup"><span data-stu-id="35148-651">For more information about user tags, see [User tags](user-tags.md).</span></span>
- <span data-ttu-id="35148-652">**ドメイン**</span><span class="sxs-lookup"><span data-stu-id="35148-652">**Domain**</span></span>
- <span data-ttu-id="35148-653">**ポリシーの種類**</span><span class="sxs-lookup"><span data-stu-id="35148-653">**Policy type**</span></span>
- <span data-ttu-id="35148-654">**ポリシー名** (詳細テーブルのみ)</span><span class="sxs-lookup"><span data-stu-id="35148-654">**Policy name** (details table only)</span></span>
- <span data-ttu-id="35148-655">**受信者**</span><span class="sxs-lookup"><span data-stu-id="35148-655">**Recipients**</span></span>

<span data-ttu-id="35148-656">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-656">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="35148-657"><sup>\*</sup>Defender for Office 365のみ</span><span class="sxs-lookup"><span data-stu-id="35148-657"><sup>\*</sup> Defender for Office 365 only</span></span>

## <a name="top-malware-report"></a><span data-ttu-id="35148-658">トップ マルウェア レポート</span><span class="sxs-lookup"><span data-stu-id="35148-658">Top malware report</span></span>

<span data-ttu-id="35148-659">[ **トップ マルウェア]** レポートには、EOP のマルウェア対策保護によって検出されたさまざまな種類 [のマルウェアが表示されます](anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="35148-659">The **Top malware** report shows the various kinds of malware that was detected by [anti-malware protection in EOP](anti-malware-protection.md).</span></span>

<span data-ttu-id="35148-660">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="35148-660">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="35148-661">[電子メール **&コラボレーション レポート] ページで** 、[トップ マルウェア] を探 **し** 、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-661">On the **Email & collaboration reports** page, find **Top malware** and then click **View details**.</span></span> <span data-ttu-id="35148-662">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/TopMalware> 。</span><span class="sxs-lookup"><span data-stu-id="35148-662">To go directly to the report, open <https://security.microsoft.com/reports/TopMalware>.</span></span>

![[メール と共同作業レポート] ページの&のトップ マルウェア ウィジェット](../../media/top-malware-report-widget.png)

<span data-ttu-id="35148-664">円グラフのくさびの上にマウス ポインターを置くと、マルウェアの種類の名前と、そのマルウェアが検出されたメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="35148-664">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>

<span data-ttu-id="35148-665">[上位 **マルウェア レポート] ページ** で、より大きなバージョンの円グラフがレポート ページに表示されます。グラフの下の詳細テーブルは、次の情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="35148-665">On the **Top malware report** page, a larger version of the pie chart is displayed on the report page.The details table below the chart shows the following information:</span></span>

- <span data-ttu-id="35148-666">**トップ マルウェア**</span><span class="sxs-lookup"><span data-stu-id="35148-666">**Top malware**</span></span>
- <span data-ttu-id="35148-667">**Count**</span><span class="sxs-lookup"><span data-stu-id="35148-667">**Count**</span></span>

<span data-ttu-id="35148-668">[フィルター]**をクリック** すると、[開始日] と [終了日] で **日付範囲\*\*\*\*を指定できます**。</span><span class="sxs-lookup"><span data-stu-id="35148-668">If you click **Filter**, you can specify a date range with **Start date** and **End date**.</span></span>

![トップ マルウェア レポート ビュー](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a><span data-ttu-id="35148-670">URL 脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="35148-670">URL threat protection report</span></span>

<span data-ttu-id="35148-671">URL **の脅威保護レポートは**、Microsoft Defender で使用できるOffice 365。</span><span class="sxs-lookup"><span data-stu-id="35148-671">The **URL threat protection report** is available in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="35148-672">詳細については、「URL 脅威保護 [レポート」を参照してください](view-reports-for-mdo.md#url-threat-protection-report)。</span><span class="sxs-lookup"><span data-stu-id="35148-672">For more information, see [URL threat protection report](view-reports-for-mdo.md#url-threat-protection-report).</span></span>

## <a name="user-reported-messages-report"></a><span data-ttu-id="35148-673">ユーザーが報告したメッセージ レポート</span><span class="sxs-lookup"><span data-stu-id="35148-673">User reported messages report</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35148-674">ユーザーが報告した **メッセージ レポート** が正しく動作するには、ユーザーの環境で監査ログを有効にするMicrosoft 365があります。</span><span class="sxs-lookup"><span data-stu-id="35148-674">In order for the **User reported messages** report to work correctly, **audit logging must be turned on** for your Microsoft 365 environment.</span></span> <span data-ttu-id="35148-675">これは通常、監査ログの役割が管理者に割り当てられているユーザー Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="35148-675">This is typically done by someone who has the Audit Logs role assigned in Exchange Online.</span></span> <span data-ttu-id="35148-676">詳細については、「監査ログの[検索を有効またはMicrosoft 365を有効またはオフにする」を参照してください](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="35148-676">For more information, see [Turn Microsoft 365 audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

<span data-ttu-id="35148-677">[**ユーザーレポート メッセージ]** レポートには、ユーザーが迷惑メール、フィッシング詐欺の試み、または良いメールとして報告した [](enable-the-report-message-add-in.md)電子メール メッセージに関する情報が、レポート メッセージ アドインまたはレポート フィッシング アドインを使用して表示 [されます](enable-the-report-phish-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="35148-677">The **User reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="35148-678">ポータルでレポートを表示するにはMicrosoft 365 Defender[レポートの電子メール]  & \>  \> **グループ&に移動します**。</span><span class="sxs-lookup"><span data-stu-id="35148-678">To view the report in the Microsoft 365 Defender portal, go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="35148-679">[コラボレーション **レポートのメール&] ページで**、[ユーザーが報告したメッセージ] を探し、[詳細の表示]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-679">On the **Email & collaboration reports** page, find **User reported messages** and then click **View details**.</span></span> <span data-ttu-id="35148-680">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/userSubmissionReport> 。</span><span class="sxs-lookup"><span data-stu-id="35148-680">To go directly to the report, open <https://security.microsoft.com/reports/userSubmissionReport>.</span></span> <span data-ttu-id="35148-681">ポータルで [管理者の申請に移動するには、[Microsoft 365 Defender提出](admin-submission.md)に移動 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-681">To go to [admin submissions in the Microsoft 365 Defender portal](admin-submission.md), click **Go to Submissions**.</span></span>

![[メール] ページの [コラボレーション レポート] ページ&報告されたメッセージ ウィジェット](../../media/user-reported-messages-widget.png)

<span data-ttu-id="35148-683">[ユーザー **が報告した** メッセージ] ページで、[フィルター] をクリックし、表示されるフライアウトで次の値の 1 つ以上を選択して、グラフと詳細テーブルの両方をフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="35148-683">On the **User reported messages** page, you can filter both the chart and the details table by clicking **Filter** and selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="35148-684">**報告日**: **開始時刻** と **終了時刻**</span><span class="sxs-lookup"><span data-stu-id="35148-684">**Date reported**: **Start time** and **End time**</span></span>
- <span data-ttu-id="35148-685">[**レポート作成者**]</span><span class="sxs-lookup"><span data-stu-id="35148-685">**Reported by**</span></span>
- <span data-ttu-id="35148-686">**メールの件名**</span><span class="sxs-lookup"><span data-stu-id="35148-686">**Email subject**</span></span>
- <span data-ttu-id="35148-687">**メッセージの報告 ID**</span><span class="sxs-lookup"><span data-stu-id="35148-687">**Message reported ID**</span></span>
- <span data-ttu-id="35148-688">**ネットワーク メッセージ ID**</span><span class="sxs-lookup"><span data-stu-id="35148-688">**Network Message ID**</span></span>
- <span data-ttu-id="35148-689">**Sender**</span><span class="sxs-lookup"><span data-stu-id="35148-689">**Sender**</span></span>
- <span data-ttu-id="35148-690">**報告された理由**</span><span class="sxs-lookup"><span data-stu-id="35148-690">**Reported reason**</span></span>
  - <span data-ttu-id="35148-691">**迷惑メールではない**</span><span class="sxs-lookup"><span data-stu-id="35148-691">**Not junk**</span></span>
  - <span data-ttu-id="35148-692">**フィッシング**</span><span class="sxs-lookup"><span data-stu-id="35148-692">**Phish**</span></span>
  - <span data-ttu-id="35148-693">**スパム**</span><span class="sxs-lookup"><span data-stu-id="35148-693">**Spam**</span></span>
- <span data-ttu-id="35148-694">**フィッシングシミュレーション**:**はいまたは\*\*\*\*いいえ**</span><span class="sxs-lookup"><span data-stu-id="35148-694">**Phish simulation**: **Yes** or **No**</span></span>

<span data-ttu-id="35148-695">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="35148-695">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="35148-696">エントリをグループ化するには、[グループ] を **クリック** し、ドロップダウン リストから次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="35148-696">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="35148-697">**なし**</span><span class="sxs-lookup"><span data-stu-id="35148-697">**None**</span></span>
- <span data-ttu-id="35148-698">**理由**</span><span class="sxs-lookup"><span data-stu-id="35148-698">**Reason**</span></span>
- <span data-ttu-id="35148-699">**Sender**</span><span class="sxs-lookup"><span data-stu-id="35148-699">**Sender**</span></span>
- <span data-ttu-id="35148-700">[**レポート作成者**]</span><span class="sxs-lookup"><span data-stu-id="35148-700">**Reported by**</span></span>
- <span data-ttu-id="35148-701">**再スキャンの結果**</span><span class="sxs-lookup"><span data-stu-id="35148-701">**Rescan result**</span></span>
- <span data-ttu-id="35148-702">**フィッシング シミュレーション**</span><span class="sxs-lookup"><span data-stu-id="35148-702">**Phish simulation**</span></span>

![ユーザーが報告したメッセージ レポート](../../media/user-reported-messages-report.png)

<span data-ttu-id="35148-704">グラフの下の詳細テーブルで、次の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="35148-704">In the details table below the graph, you can see the following details:</span></span>

- <span data-ttu-id="35148-705">**メールの件名**</span><span class="sxs-lookup"><span data-stu-id="35148-705">**Email subject**</span></span>
- <span data-ttu-id="35148-706">[**レポート作成者**]</span><span class="sxs-lookup"><span data-stu-id="35148-706">**Reported by**</span></span>
- <span data-ttu-id="35148-707">**報告日**</span><span class="sxs-lookup"><span data-stu-id="35148-707">**Date reported**</span></span>
- <span data-ttu-id="35148-708">**Sender**</span><span class="sxs-lookup"><span data-stu-id="35148-708">**Sender**</span></span>
- <span data-ttu-id="35148-709">**報告された理由**</span><span class="sxs-lookup"><span data-stu-id="35148-709">**Reported reason**</span></span>
- <span data-ttu-id="35148-710">**再スキャンの結果**</span><span class="sxs-lookup"><span data-stu-id="35148-710">**Rescan result**</span></span>
- <span data-ttu-id="35148-711">**Tags**</span><span class="sxs-lookup"><span data-stu-id="35148-711">**Tags**</span></span>

<span data-ttu-id="35148-712">分析のために Microsoft にメッセージを送信するには、表からメッセージ エントリを選択し、[分析のために **Microsoft** に送信] をクリックし、ドロップダウン リストから次のいずれかの値を選択します。</span><span class="sxs-lookup"><span data-stu-id="35148-712">To submit a message to Microsoft for analysis, select the message entry from the table, click **Submit to Microsoft for analysis** and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="35148-713">**クリーンレポート**</span><span class="sxs-lookup"><span data-stu-id="35148-713">**Report clean**</span></span>
- <span data-ttu-id="35148-714">**フィッシングの報告**</span><span class="sxs-lookup"><span data-stu-id="35148-714">**Report phishing**</span></span>
- <span data-ttu-id="35148-715">**マルウェアの報告**</span><span class="sxs-lookup"><span data-stu-id="35148-715">**Report malware**</span></span>
- <span data-ttu-id="35148-716">**[スパムを報告する**]</span><span class="sxs-lookup"><span data-stu-id="35148-716">**Report spam**'</span></span>
- <span data-ttu-id="35148-717">**トリガー調査**(Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="35148-717">**Trigger investigation** (Defender for Office 365)</span></span>

## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="35148-718">これらのレポートを表示するために必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="35148-718">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="35148-719">この記事で説明するレポートを表示して使用するには、ポータルで次のいずれかの役割グループのメンバー Microsoft 365 Defenderがあります。</span><span class="sxs-lookup"><span data-stu-id="35148-719">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="35148-720">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="35148-720">**Organization Management**</span></span>
- <span data-ttu-id="35148-721">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="35148-721">**Security Administrator**</span></span>
- <span data-ttu-id="35148-722">**セキュリティ リーダー**</span><span class="sxs-lookup"><span data-stu-id="35148-722">**Security Reader**</span></span>
- <span data-ttu-id="35148-723">**グローバル リーダー**</span><span class="sxs-lookup"><span data-stu-id="35148-723">**Global Reader**</span></span>

<span data-ttu-id="35148-724">詳細については、「ポータルの[アクセス許可」をMicrosoft 365 Defenderしてください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="35148-724">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="35148-725">**注**: Microsoft 365 管理センター の対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="35148-725">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="35148-726">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35148-726">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="35148-727">レポートにデータが表示されない場合は、</span><span class="sxs-lookup"><span data-stu-id="35148-727">What if the reports aren't showing data?</span></span>

<span data-ttu-id="35148-728">レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="35148-728">If you are not seeing data in your reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="35148-729">詳細については、「脅威から保護 [する」を参照してください](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="35148-729">To learn more, see [Protect against threats](protect-against-threats.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="35148-730">関連項目</span><span class="sxs-lookup"><span data-stu-id="35148-730">Related topics</span></span>

[<span data-ttu-id="35148-731">EOP でのスパム対策およびマルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="35148-731">Anti-spam and anti-malware protection in EOP</span></span>](anti-spam-and-anti-malware-protection.md)

[<span data-ttu-id="35148-732">スマート レポートと分析情報 (Microsoft 365 Defenderポータル)</span><span class="sxs-lookup"><span data-stu-id="35148-732">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="35148-733">メール フロー レポートをポータルでMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="35148-733">View mail flow reports in the Microsoft 365 Defender portal</span></span>](view-mail-flow-reports.md)

[<span data-ttu-id="35148-734">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="35148-734">View reports for Defender for Office 365</span></span>](view-reports-for-mdo.md)
