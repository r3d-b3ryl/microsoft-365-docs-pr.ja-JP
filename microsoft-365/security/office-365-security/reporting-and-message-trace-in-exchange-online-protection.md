---
title: レポート作成とメッセージ追跡
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: この記事では、Microsoft Exchange Online Protection (EOP) 管理者が利用できるレポートとトラブルシューティングツールについて説明します。
ms.openlocfilehash: 9a8eb8e35ef73eb27604eef4bf701982b1d51710
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845554"
---
# <a name="reporting-and-message-trace-in-eop"></a><span data-ttu-id="51273-103">EOP でのレポート作成とメッセージ追跡</span><span class="sxs-lookup"><span data-stu-id="51273-103">Reporting and message trace in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="51273-104">Exchange online メールボックスを使用しない Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織内にメールボックスを持つ Microsoft 365 組織では、EOP によって、組織の全体的な状態と正常性を特定するのに役立つさまざまなレポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="51273-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="51273-105">特定イベント (目的の受信者に届かなかったメッセージなど) のトラブルシューティングを支援するツール、さらに法令遵守の要件のための監査レポートもあります。</span><span class="sxs-lookup"><span data-stu-id="51273-105">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span>

## <a name="usage-reports"></a><span data-ttu-id="51273-106">利用状況レポート</span><span class="sxs-lookup"><span data-stu-id="51273-106">Usage reports</span></span>

<span data-ttu-id="51273-107">**Microsoft 365 groups activity** : 作成および使用されている microsoft 365 グループの数に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="51273-107">**Microsoft 365 groups activity** : View information about the number of Microsoft 365 groups that are created and used.</span></span>

<span data-ttu-id="51273-108">**電子メールアクティビティ** : 組織全体で送受信されたメッセージの数と、特定のユーザーに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="51273-108">**Email activity** : View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>

<span data-ttu-id="51273-109">**電子メールアプリの使用状況** : 使用されている電子メールアプリに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="51273-109">**Email app usage** : View information about the email apps that are used.</span></span> <span data-ttu-id="51273-110">これには、各アプリの合計接続数、および接続している Outlook のバージョンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="51273-110">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>

<span data-ttu-id="51273-111">**メールボックスの使用状況** : メールボックスの使用済み記憶域、クォータ消費、アイテム数、最後のアクティビティ (送信または読み取りアクティビティ) に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="51273-111">**Mailbox usage** : View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="51273-112">詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51273-112">See the following resources for more information:</span></span>

- [<span data-ttu-id="51273-113">管理センターの microsoft 365 レポート-Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="51273-113">Microsoft 365 Reports in the admin center - Microsoft 365 groups</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [<span data-ttu-id="51273-114">管理センターの Microsoft 365 レポート-電子メールアクティビティ</span><span class="sxs-lookup"><span data-stu-id="51273-114">Microsoft 365 Reports in the admin center - Email activity</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [<span data-ttu-id="51273-115">管理センターの Microsoft 365 レポート-電子メールアプリの使用状況</span><span class="sxs-lookup"><span data-stu-id="51273-115">Microsoft 365 Reports in the admin center - Email apps usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [<span data-ttu-id="51273-116">管理センターでの Microsoft 365 レポート-メールボックスの使用状況</span><span class="sxs-lookup"><span data-stu-id="51273-116">Microsoft 365 Reports in the admin center - Mailbox usage</span></span>](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="51273-117">Microsoft 365 管理センターのセキュリティ & コンプライアンスレポート</span><span class="sxs-lookup"><span data-stu-id="51273-117">Security & compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="51273-118">これらの拡張されたレポートは EOP 管理者向けの対話型レポート エクスペリエンスを提供します。これには概要情報、および詳細についてドリルダウンする機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="51273-118">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>

<span data-ttu-id="51273-119">**Office 用 Defender defender 365** : Microsoft Defender for office 365 の一部である安全なリンクと安全な添付ファイルに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="51273-119">**Defender for Office 365** : View information about Safe Links and Safe Attachments that are part of Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="51273-120">**EOP** : マルウェアの検出、スプーフィングされたメール、スパム検出、組織との間のメールフローに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="51273-120">**EOP** : View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>

[<span data-ttu-id="51273-121">Defender for Office 365 のレポートの表示</span><span class="sxs-lookup"><span data-stu-id="51273-121">View reports for Defender for Office 365</span></span>](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="51273-122">Microsoft Graph を使用するカスタムレポート</span><span class="sxs-lookup"><span data-stu-id="51273-122">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="51273-123">Microsoft Graph を使用して、管理センターで利用可能なレポートをプログラムで作成します。</span><span class="sxs-lookup"><span data-stu-id="51273-123">Programmatically create reports that are available in the admin center by using Microsoft Graph.</span></span> <span data-ttu-id="51273-124">詳細については、「microsoft [graph の概要](https://docs.microsoft.com/graph/overview) 」および「 [Microsoft graph で Office 365 の使用状況レポート](https://docs.microsoft.com/graph/api/resources/report)を使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51273-124">For more information, see [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) and [Working with Office 365 usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).</span></span>

## <a name="message-trace"></a><span data-ttu-id="51273-125">メッセージの追跡</span><span class="sxs-lookup"><span data-stu-id="51273-125">Message trace</span></span>

<span data-ttu-id="51273-p104">EOP を通過する電子メール メッセージを追跡します。電子メール メッセージがサービスで受信、拒否、延期、配信されたか確認できます。メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。</span><span class="sxs-lookup"><span data-stu-id="51273-p104">Follows email messages as they travel through EOP. You can determine if an email message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="51273-129">この情報を使用して、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。</span><span class="sxs-lookup"><span data-stu-id="51273-129">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>

<span data-ttu-id="51273-130">[セキュリティ & コンプライアンスセンターのメッセージ追跡を](message-trace-scc.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="51273-130">See [Message trace in the Security & Compliance Center](message-trace-scc.md).</span></span>

## <a name="audit-logging"></a><span data-ttu-id="51273-131">監査ログ</span><span class="sxs-lookup"><span data-stu-id="51273-131">Audit logging</span></span>

<span data-ttu-id="51273-132">組織の管理者によって行われた特定の変更を追跡します。</span><span class="sxs-lookup"><span data-stu-id="51273-132">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="51273-133">これらのレポートの構成に関する問題のトラブルシューティングを行うか、セキュリティやコンプライアンス関連の問題の原因を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="51273-133">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span> <span data-ttu-id="51273-134">「 [EOP の監査レポート」を](auditing-reports-in-eop.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="51273-134">See [Auditing reports in EOP](auditing-reports-in-eop.md).</span></span>

## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="51273-135">レポート機能とメッセージ トレース データの使用可能性と遅延</span><span class="sxs-lookup"><span data-stu-id="51273-135">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="51273-136">EOP のレポート機能とメッセージ トレース データが使用可能なタイミングと期間を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="51273-136">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>

****

|<span data-ttu-id="51273-137">レポートの種類</span><span class="sxs-lookup"><span data-stu-id="51273-137">Report type</span></span>|<span data-ttu-id="51273-138">データ使用可能期間 (遡及期間)</span><span class="sxs-lookup"><span data-stu-id="51273-138">Data available for (look back period)</span></span>|<span data-ttu-id="51273-139">遅延</span><span class="sxs-lookup"><span data-stu-id="51273-139">Latency</span></span>|
|---|---|---|
|<span data-ttu-id="51273-140">メール保護概要レポート</span><span class="sxs-lookup"><span data-stu-id="51273-140">Mail protection summary reports</span></span>|<span data-ttu-id="51273-141">90 日</span><span class="sxs-lookup"><span data-stu-id="51273-141">90 days</span></span>|<span data-ttu-id="51273-p106">メッセージ データの集計は 24 ～ 48 時間以内にほぼ完了します。最大 5 日間のマイナーな増分集計変更が実施される場合があります。</span><span class="sxs-lookup"><span data-stu-id="51273-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>|
|<span data-ttu-id="51273-144">メール保護詳細レポート</span><span class="sxs-lookup"><span data-stu-id="51273-144">Mail protection detail reports</span></span>|<span data-ttu-id="51273-145">90 日</span><span class="sxs-lookup"><span data-stu-id="51273-145">90 days</span></span>|<span data-ttu-id="51273-p107">生成後 7 日未満の詳細データに関しては、24 時間以内に表示されるはずですが、48 時間まで完成しない場合があります。最大 5 日分のマイナーな増分変更が実施される場合があります。</span><span class="sxs-lookup"><span data-stu-id="51273-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span> <br/><br/> <span data-ttu-id="51273-148">7 日以上前のメッセージに関する詳細レポートを表示するには、結果が出るまでに最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="51273-148">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|<span data-ttu-id="51273-149">メッセージ追跡データ</span><span class="sxs-lookup"><span data-stu-id="51273-149">Message trace data</span></span>|<span data-ttu-id="51273-150">90 日</span><span class="sxs-lookup"><span data-stu-id="51273-150">90 days</span></span>|<span data-ttu-id="51273-151">生成後 7 日未満のメッセージのメッセージ追跡を実施した場合は、メッセージが 5 ～ 30 分で表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="51273-151">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span><br/><br/> <span data-ttu-id="51273-152">7 日以上前のメッセージのメッセージ追跡を実施した場合は、結果が出るまでに最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="51273-152">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>|
|

> [!NOTE]
> <span data-ttu-id="51273-153">データの可用性と待機時間は、管理センターとリモート PowerShell のどちらで要求されても同じです。</span><span class="sxs-lookup"><span data-stu-id="51273-153">Data availability and latency is the same whether requested via the admin center or remote PowerShell.</span></span>
