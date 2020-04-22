---
title: Exchange Online Protection でのレポート作成とメッセージ追跡
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) には、組織の全体的な状態と正常性を判断するのに役立つさまざまなレポートが用意されています。 特定イベント (目的の受信者に届かなかったメッセージなど) のトラブルシューティングを支援するツール、さらに法令遵守の要件のための監査レポートもあります。 次の表には、EOP 管理者が利用できるレポートおよびトラブルシューティングのツールを示します。
ms.openlocfilehash: e961c76daaad72fbd1ddede5651cb49fd66d48be
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634354"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="bd9ca-105">Exchange Online Protection でのレポート作成とメッセージ追跡</span><span class="sxs-lookup"><span data-stu-id="bd9ca-105">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="bd9ca-106">Microsoft Exchange Online Protection (EOP) には、組織の全体的な状態と正常性を判断するのに役立つさまざまなレポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-106">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="bd9ca-107">特定イベント (目的の受信者に届かなかったメッセージなど) のトラブルシューティングを支援するツール、さらに法令遵守の要件のための監査レポートもあります。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-107">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="bd9ca-108">利用状況レポート</span><span class="sxs-lookup"><span data-stu-id="bd9ca-108">Usage reports</span></span>

<span data-ttu-id="bd9ca-109">**Microsoft 365 groups activity**: 作成および使用されている microsoft 365 グループの数に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-109">**Microsoft 365 groups activity**: View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="bd9ca-110">**電子メールアクティビティ**: 組織全体で送受信されたメッセージの数と、特定のユーザーに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-110">**Email activity**: View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="bd9ca-111">**電子メールアプリの使用状況**: 使用されている電子メールアプリに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-111">**Email app usage**: View information about the email apps that are used.</span></span> <span data-ttu-id="bd9ca-112">これには、各アプリの合計接続数、および接続している Outlook のバージョンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-112">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="bd9ca-113">**メールボックスの使用状況**: メールボックスの使用済み記憶域、クォータ消費、アイテム数、最後のアクティビティ (送信または読み取りアクティビティ) に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-113">**Mailbox usage**: View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="bd9ca-114">詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-114">See the following resources for more information:</span></span>

- [<span data-ttu-id="bd9ca-115">管理センターの microsoft 365 レポート-Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="bd9ca-115">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="bd9ca-116">管理センターの Microsoft 365 レポート-電子メールアクティビティ</span><span class="sxs-lookup"><span data-stu-id="bd9ca-116">Microsoft 365 Reports in the Admin Center - Email activity</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-activity)

- [<span data-ttu-id="bd9ca-117">管理センターの Microsoft 365 レポート-電子メールアプリの使用状況</span><span class="sxs-lookup"><span data-stu-id="bd9ca-117">Microsoft 365 Reports in the Admin Center - Email apps usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="bd9ca-118">管理センターでの Microsoft 365 レポート-メールボックスの使用状況</span><span class="sxs-lookup"><span data-stu-id="bd9ca-118">Microsoft 365 Reports in the Admin Center - Mailbox usage</span></span>](https://docs.microsoft.com/office365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="bd9ca-119">Microsoft 365 管理センターのセキュリティ & コンプライアンスレポート</span><span class="sxs-lookup"><span data-stu-id="bd9ca-119">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="bd9ca-120">これらの拡張されたレポートは EOP 管理者向けの対話型レポート エクスペリエンスを提供します。これには概要情報、および詳細についてドリルダウンする機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-120">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="bd9ca-121">**Advanced Threat Protection (atp)**: atp の一部である安全なリンクと安全な添付ファイルに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-121">**Advanced Threat Protection (ATP)**: View information about safe links and safe attachments that are part of ATP.</span></span>

<span data-ttu-id="bd9ca-122">**EOP**: マルウェアの検出、スプーフィングされたメール、スパム検出、組織との間のメールフローに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-122">**EOP**: View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="bd9ca-123">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="bd9ca-123">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="bd9ca-124">Microsoft Graph を使用するカスタムレポート</span><span class="sxs-lookup"><span data-stu-id="bd9ca-124">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="bd9ca-125">Microsoft Graph を使用して、Microsoft 365 管理センターで利用可能なレポートをプログラムで作成します。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-125">Programmatically create reports that are available in the Microsoft 365 admin center by using Microsoft Graph.</span></span> <span data-ttu-id="bd9ca-126">「 [Microsoft Graph で Office 365 の使用状況レポートを](https://docs.microsoft.com/graph/api/resources/report)使用する」のサブトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-126">See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="bd9ca-127">Microsoft Graph を使用するカスタムレポート</span><span class="sxs-lookup"><span data-stu-id="bd9ca-127">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="bd9ca-128">プログラムでレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-128">Programmatically create reports.</span></span> <span data-ttu-id="bd9ca-129">[Microsoft Graph の概要を](https://docs.microsoft.com/graph/overview)参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-129">See [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview).</span></span>

## <a name="message-trace"></a><span data-ttu-id="bd9ca-130">メッセージの追跡</span><span class="sxs-lookup"><span data-stu-id="bd9ca-130">Message trace</span></span>

<span data-ttu-id="bd9ca-p106">EOP を通過する電子メール メッセージを追跡します。電子メール メッセージがサービスで受信、拒否、延期、配信されたか確認できます。メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-p106">Follows email messages as they travel through EOP. You can determine if an email message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="bd9ca-134">この情報を使用して、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-134">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="bd9ca-135">「 [Trace an email message」を](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-135">See [Trace an email message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message)</span></span>

## <a name="audit-logging"></a><span data-ttu-id="bd9ca-136">監査ログ</span><span class="sxs-lookup"><span data-stu-id="bd9ca-136">Audit logging</span></span>

<span data-ttu-id="bd9ca-137">組織の管理者によって行われた特定の変更を追跡します。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-137">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="bd9ca-138">これらのレポートの構成に関する問題のトラブルシューティングを行うか、セキュリティやコンプライアンス関連の問題の原因を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-138">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="bd9ca-139">「 [EOP の監査レポート」を](auditing-reports-in-eop.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-139">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="bd9ca-140">レポート機能とメッセージ トレース データの使用可能性と遅延</span><span class="sxs-lookup"><span data-stu-id="bd9ca-140">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="bd9ca-141">EOP のレポート機能とメッセージ トレース データが使用可能なタイミングと期間を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-141">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

||||
|:-----|:-----|:-----|
|<span data-ttu-id="bd9ca-142">**レポートの種類**</span><span class="sxs-lookup"><span data-stu-id="bd9ca-142">**Report type**</span></span>|<span data-ttu-id="bd9ca-143">**データ使用可能期間 (遡及期間)**</span><span class="sxs-lookup"><span data-stu-id="bd9ca-143">**Data available for (look back period)**</span></span>|<span data-ttu-id="bd9ca-144">**待機時間**</span><span class="sxs-lookup"><span data-stu-id="bd9ca-144">**Latency**</span></span>|
|<span data-ttu-id="bd9ca-145">メール保護概要レポート</span><span class="sxs-lookup"><span data-stu-id="bd9ca-145">Mail protection summary reports</span></span>|<span data-ttu-id="bd9ca-146">90 日間</span><span class="sxs-lookup"><span data-stu-id="bd9ca-146">90 days</span></span>|<span data-ttu-id="bd9ca-p108">メッセージ データの集計は 24 ～ 48 時間以内にほぼ完了します。最大 5 日間のマイナーな増分集計変更が実施される場合があります。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-p108">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="bd9ca-149">メール保護詳細レポート</span><span class="sxs-lookup"><span data-stu-id="bd9ca-149">Mail protection detail reports</span></span>|<span data-ttu-id="bd9ca-150">90 日</span><span class="sxs-lookup"><span data-stu-id="bd9ca-150">90 days</span></span>|<span data-ttu-id="bd9ca-p109">生成後 7 日未満の詳細データに関しては、24 時間以内に表示されるはずですが、48 時間まで完成しない場合があります。最大 5 日分のマイナーな増分変更が実施される場合があります。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-p109">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="bd9ca-153">7 日以上前のメッセージに関する詳細レポートを表示するには、結果が出るまでに最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-153">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="bd9ca-154">メッセージ追跡データ</span><span class="sxs-lookup"><span data-stu-id="bd9ca-154">Message trace data</span></span>|<span data-ttu-id="bd9ca-155">90 日</span><span class="sxs-lookup"><span data-stu-id="bd9ca-155">90 days</span></span>|<span data-ttu-id="bd9ca-156">生成後 7 日未満のメッセージのメッセージ追跡を実施した場合は、メッセージが 5 ～ 30 分で表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-156">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="bd9ca-157">7 日以上前のメッセージのメッセージ追跡を実施した場合は、結果が出るまでに最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-157">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|

> [!NOTE]
> <span data-ttu-id="bd9ca-158">データの可用性と待機時間は、Microsoft 365 管理センターまたはリモート PowerShell を介して要求された場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="bd9ca-158">Data availability and latency is the same whether requested via the Microsoft 365 admin center or remote PowerShell.</span></span>
