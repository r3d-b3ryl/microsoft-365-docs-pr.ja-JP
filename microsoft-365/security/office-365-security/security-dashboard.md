---
title: セキュリティ ダッシュボードの概要
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 新しいセキュリティ ダッシュボードを使用して、脅威Office 365状態を確認し、セキュリティアラートを表示して処理します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8c9a49b9b8fc1edd9b2928250e8cae135acb75f4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274414"
---
# <a name="security-dashboard"></a><span data-ttu-id="ec6c3-103">セキュリティ ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="ec6c3-103">Security Dashboard</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a><span data-ttu-id="ec6c3-104">基本的な機能とセキュリティ ダッシュボードを開く方法</span><span class="sxs-lookup"><span data-stu-id="ec6c3-104">Basic functions and how to open Security Dashboard</span></span>

<span data-ttu-id="ec6c3-105">セキュリティ [& コンプライアンス センターを使用](../../compliance/microsoft-365-compliance-center.md) すると、組織はデータ保護とコンプライアンスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-105">The [Security & Compliance Center](../../compliance/microsoft-365-compliance-center.md) enables your organization to manage data protection and compliance.</span></span> <span data-ttu-id="ec6c3-106">必要なアクセス許可を持っている場合、セキュリティ ダッシュボードを使用すると、脅威保護の状態を確認し、セキュリティアラートを表示して操作できます。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-106">Assuming you have the necessary permissions, the Security Dashboard enables you to review your Threat Protection Status, as well as view and act on security alerts.</span></span>

<span data-ttu-id="ec6c3-107">ビデオを見て概要を確認し、この記事を読んで詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-107">Watch the video to get an overview, and then read this article to learn more.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

<span data-ttu-id="ec6c3-108">組織のサブスクリプションに含まれる内容に応じて、セキュリティ ダッシュボードには、次のセクションで説明するように、脅威管理の概要、脅威保護の状態、グローバル週間脅威検出、マルウェアなど、いくつかのウィジェットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-108">Depending on what your organization's subscription includes, the Security Dashboard includes several widgets, such as Threat Management Summary, Threat Protection Status, Global Weekly Threat Detections, Malware, and more, as described in the following sections.</span></span>

<span data-ttu-id="ec6c3-109">セキュリティ ダッシュボードを表示するには、セキュリティ & [コンプライアンス センター](../../compliance/microsoft-365-compliance-center.md)で、[脅威管理 **ダッシュボード] に移動** \> **します**。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-109">To view the Security Dashboard, in the [Security & Compliance Center](../../compliance/microsoft-365-compliance-center.md), go to **Threat management** \> **Dashboard**.</span></span>

> [!NOTE]
> <span data-ttu-id="ec6c3-110">セキュリティ ダッシュボードを表示するには、グローバル管理者、セキュリティ管理者、またはセキュリティ リーダーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-110">You must be a global administrator, a security administrator, or a security reader to view the Security Dashboard.</span></span> <span data-ttu-id="ec6c3-111">一部のウィジェットでは、表示に追加のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-111">Some widgets require additional permissions to view.</span></span> <span data-ttu-id="ec6c3-112">詳細については、「セキュリティ コンプライアンス センターのアクセス許可 [」&参照してください](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-112">To learn more, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="threat-management-summary"></a><span data-ttu-id="ec6c3-113">脅威管理の概要</span><span class="sxs-lookup"><span data-stu-id="ec6c3-113">Threat Management Summary</span></span>

<span data-ttu-id="ec6c3-114">脅威管理の概要ウィジェットは、組織が過去 7 日間の脅威から保護された方法を一目で示します。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-114">The Threat Management Summary widget tells you at a glance how your organization was protected from threats over the past seven (7) days.</span></span>

![セキュリティ ダッシュボード - 脅威管理の概要ウィジェット](../../media/SecDash-ThreatMgmtSummary.png)

<span data-ttu-id="ec6c3-116">脅威管理の概要に表示される情報は、サブスクリプションに含まれる内容によって異なります。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-116">The information you'll see in the Threat Management Summary depends on what you subscription includes.</span></span> <span data-ttu-id="ec6c3-117">次の表に、E3 および E5 に含Office 365情報Office 365します。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-117">The following table describes what information is included for Office 365 E3 and Office 365 E5.</span></span>

|<span data-ttu-id="ec6c3-118">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="ec6c3-118">Office 365 E3</span></span>|<span data-ttu-id="ec6c3-119">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="ec6c3-119">Office 365 E5</span></span>|
|---|---|
|<span data-ttu-id="ec6c3-120">マルウェア メッセージがブロックされている</span><span class="sxs-lookup"><span data-stu-id="ec6c3-120">Malware messages blocked</span></span><br><span data-ttu-id="ec6c3-121">フィッシング メッセージがブロックされる</span><span class="sxs-lookup"><span data-stu-id="ec6c3-121">Phishing messages blocked</span></span><br><span data-ttu-id="ec6c3-122">ユーザーによって報告されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="ec6c3-122">Messages reported by users</span></span><br><br><br><br>|<span data-ttu-id="ec6c3-123">マルウェア メッセージがブロックされている</span><span class="sxs-lookup"><span data-stu-id="ec6c3-123">Malware messages blocked</span></span><br><span data-ttu-id="ec6c3-124">フィッシング メッセージがブロックされる</span><span class="sxs-lookup"><span data-stu-id="ec6c3-124">Phishing messages blocked</span></span><br><span data-ttu-id="ec6c3-125">ユーザーによって報告されたメッセージ</span><span class="sxs-lookup"><span data-stu-id="ec6c3-125">Messages reported by users</span></span><br><span data-ttu-id="ec6c3-126">ゼロデイマルウェアがブロックされる</span><span class="sxs-lookup"><span data-stu-id="ec6c3-126">Zero-day malware blocked</span></span><br><span data-ttu-id="ec6c3-127">高度なフィッシング メッセージが検出されました</span><span class="sxs-lookup"><span data-stu-id="ec6c3-127">Advanced phishing messages detected</span></span><br><span data-ttu-id="ec6c3-128">ブロックされた悪意のある URL</span><span class="sxs-lookup"><span data-stu-id="ec6c3-128">Malicious URLs blocked</span></span>|

<span data-ttu-id="ec6c3-129">脅威管理の概要ウィジェットを表示またはアクセスするには、レポートの Defender を表示するためのアクセス許可Office 365があります。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-129">To view or access the Threat Management Summary widget, you must have permissions to view Defender for Office 365 reports.</span></span> <span data-ttu-id="ec6c3-130">詳細については、「レポートの Defender を表示するために必要なアクセス許可[Office 365」を参照してください](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-130">To learn more, see [What permissions are needed to view the Defender for Office 365 reports?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).</span></span>

## <a name="threat-protection-status"></a><span data-ttu-id="ec6c3-131">脅威保護の状態</span><span class="sxs-lookup"><span data-stu-id="ec6c3-131">Threat Protection Status</span></span>

<span data-ttu-id="ec6c3-132">脅威保護の状態ウィジェットは、フィッシングとマルウェアの傾向と詳細なビューで脅威保護の有効性を示します。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-132">The Threat Protection Status widget shows threat protection effectiveness with a trending and detailed view of phish and malware.</span></span>

![脅威保護状態ウィジェット](../../media/tpswidget.png)

<span data-ttu-id="ec6c3-134">詳細は、Microsoft Defender のMicrosoft 365のMicrosoft 365 [](exchange-online-protection-overview.md) (EOP) Exchange Online Protectionが含まれるかどうか[によって異Office 365。](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="ec6c3-134">The details depend on whether your Microsoft 365 subscription includes [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) with or without [Microsoft Defender for Office 365](defender-for-office-365.md).</span></span>

|<span data-ttu-id="ec6c3-135">サブスクリプションに含まれる場合。.</span><span class="sxs-lookup"><span data-stu-id="ec6c3-135">If your subscription includes...</span></span>|<span data-ttu-id="ec6c3-136">これらの詳細が表示されます</span><span class="sxs-lookup"><span data-stu-id="ec6c3-136">You'll see these details</span></span>|
|---|---|
|<span data-ttu-id="ec6c3-137">EOP ではなく Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ec6c3-137">EOP but not Microsoft Defender for Office 365</span></span>|<span data-ttu-id="ec6c3-138">EOP によって検出およびブロックされた悪意のある電子メール。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-138">Malicious email that was detected and blocked by EOP.</span></span><p> <span data-ttu-id="ec6c3-139">「Threat [Protection Status report (EOP)」を参照してください](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-139">See [Threat Protection Status report (EOP)](view-email-security-reports.md#threat-protection-status-report).</span></span>|
|<span data-ttu-id="ec6c3-140">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ec6c3-140">Microsoft Defender for Office 365</span></span>|<span data-ttu-id="ec6c3-141">悪意のあるコンテンツと悪意のある電子メールが EOP と Defender によって検出およびブロックOffice 365</span><span class="sxs-lookup"><span data-stu-id="ec6c3-141">Malicious content and malicious email detected and blocked by EOP and Defender for Office 365</span></span> <p> <span data-ttu-id="ec6c3-142">マルウェア対策エンジン、ゼロ時間自動削除、および Office 365 機能[(セーフ](safe-links.md)リンク[](zero-hour-auto-purge.md)[、セーフ 添付](safe-attachments.md)ファイル、および Office 365 の Defender でのフィッシング対策を含む) によってブロックされた悪意のあるコンテンツを含む一意の電子メール メッセージの集計[数](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-142">Aggregated count of unique email messages with malicious content blocked by the anti-malware engine, [zero-hour auto purge](zero-hour-auto-purge.md), and Defender for Office 365 features (including [Safe Links](safe-links.md), [Safe Attachments](safe-attachments.md), and [Anti-phishing in Defender for Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span> <p> <span data-ttu-id="ec6c3-143">「 [脅威保護の状態レポート」を参照してください](view-reports-for-mdo.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-143">See [Threat protection status report](view-reports-for-mdo.md#threat-protection-status-report).</span></span>|

<span data-ttu-id="ec6c3-144">脅威保護状態ウィジェットを表示またはアクセスするには、レポートの Defender を表示するためのアクセス許可Office 365があります。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-144">To view or access the Threat Protection Status widget, you must have permissions to view Defender for Office 365 reports.</span></span> <span data-ttu-id="ec6c3-145">詳細については、「レポートの Defender を表示するために必要なアクセス許可[Office 365してください。](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)</span><span class="sxs-lookup"><span data-stu-id="ec6c3-145">To learn more, see [What permissions are needed to view the Defender for Office 365 reports?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)</span></span>

## <a name="global-weekly-threat-detections"></a><span data-ttu-id="ec6c3-146">グローバル週次脅威検出</span><span class="sxs-lookup"><span data-stu-id="ec6c3-146">Global Weekly Threat Detections</span></span>

<span data-ttu-id="ec6c3-147">グローバル週間脅威検出ウィジェットは、過去 7 日間に電子メール メッセージで検出された脅威の数を示します。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-147">The Global Weekly Threat Detections widget shows how many threats were detected in email messages over the past seven (7) days.</span></span>

![グローバル週間脅威検出ウィジェット](../../media/globalweeklythreatdetections.png)

<span data-ttu-id="ec6c3-149">メトリックは、次の表で説明するように計算されます。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-149">The metrics are calculated as described in the following table:</span></span>

|<span data-ttu-id="ec6c3-150">測定基準</span><span class="sxs-lookup"><span data-stu-id="ec6c3-150">Metric</span></span>|<span data-ttu-id="ec6c3-151">計算方法</span><span class="sxs-lookup"><span data-stu-id="ec6c3-151">How it's calculated</span></span>|
|---|---|
|<span data-ttu-id="ec6c3-152">スキャンされたメッセージ</span><span class="sxs-lookup"><span data-stu-id="ec6c3-152">Messages scanned</span></span>|<span data-ttu-id="ec6c3-153">スキャンされた電子メール メッセージの数に受信者の数を掛けた数</span><span class="sxs-lookup"><span data-stu-id="ec6c3-153">Number of email messages scanned multiplied by the number of recipients</span></span>|
|<span data-ttu-id="ec6c3-154">脅威の停止</span><span class="sxs-lookup"><span data-stu-id="ec6c3-154">Threats stopped</span></span>|<span data-ttu-id="ec6c3-155">マルウェアが含まれていると識別された電子メール メッセージの数に受信者の数を掛けた数</span><span class="sxs-lookup"><span data-stu-id="ec6c3-155">Number of email messages identified as containing malware multiplied by the number of recipients</span></span>|
|<span data-ttu-id="ec6c3-156">Defender によって[ブロックOffice 365](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="ec6c3-156">Blocked by [Defender for Office 365](defender-for-office-365.md)</span></span>|<span data-ttu-id="ec6c3-157">Defender によってブロックされた電子メール メッセージの数Office 365受信者の数を乗算します。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-157">Number of email messages blocked by Defender for Office 365 multiplied by the number of recipients</span></span>|
|<span data-ttu-id="ec6c3-158">配信後に削除</span><span class="sxs-lookup"><span data-stu-id="ec6c3-158">Removed after delivery</span></span>|<span data-ttu-id="ec6c3-159">0 時間自動削除 [によって削除](zero-hour-auto-purge.md) されたメッセージの数に受信者の数を掛けた数</span><span class="sxs-lookup"><span data-stu-id="ec6c3-159">Number of messages removed by [zero-hour auto purge](zero-hour-auto-purge.md) multiplied by the number of recipients</span></span>|

## <a name="malware"></a><span data-ttu-id="ec6c3-160">マルウェア</span><span class="sxs-lookup"><span data-stu-id="ec6c3-160">Malware</span></span>

<span data-ttu-id="ec6c3-161">マルウェア ウィジェットには、過去 7 日間のマルウェアの傾向とマルウェア ファミリの種類に関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-161">Malware widgets show details about malware trends and malware family types over the past seven (7) days.</span></span>

![マルウェアの傾向とファミリの種類](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a><span data-ttu-id="ec6c3-163">分析情報</span><span class="sxs-lookup"><span data-stu-id="ec6c3-163">Insights</span></span>

<span data-ttu-id="ec6c3-164">分析情報には、確認する必要がある重要な問題だけでなく、考慮すべき推奨事項やアクションも含まれます。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-164">Insights not only surface key issues you should review, they also include recommendations and actions to consider.</span></span>

![スマートな分析情報](../../media/smartinsights.png)

<span data-ttu-id="ec6c3-166">たとえば、一部のユーザーが迷惑メール オプションを無効にしたため、フィッシングメール メッセージが配信されている場合があります。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-166">For example, you might see that phishing email messages are being delivered because some users have disabled their junk mail options.</span></span> <span data-ttu-id="ec6c3-167">分析情報の動作の詳細については、「Security &コンプライアンス センター」 [を参照してください](reports-and-insights-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-167">To learn more about how insights work, see [Reports and insights in the Security & Compliance Center](reports-and-insights-in-security-and-compliance.md).</span></span>

## <a name="threat-investigation-and-response"></a><span data-ttu-id="ec6c3-168">脅威の調査および対応</span><span class="sxs-lookup"><span data-stu-id="ec6c3-168">Threat investigation and response</span></span>

<span data-ttu-id="ec6c3-169">組織のサブスクリプションに Microsoft [Defender for Office 365プラン 2](office-365-ti.md)が含まれる場合、セキュリティ ダッシュボードには高度な脅威調査と対応ツールを含むセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-169">If your organization's subscription includes  [Microsoft Defender for Office 365 Plan 2](office-365-ti.md), your Security Dashboard has a section that includes advanced threat investigation and response tools.</span></span> <span data-ttu-id="ec6c3-170">これらのツールには、 [自動調査および応答機能が含まれます](automated-investigation-response-office.md)。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-170">These tools include [automated investigation and response capabilities](automated-investigation-response-office.md).</span></span> <span data-ttu-id="ec6c3-171">侵害されたユーザー アカウントに迅速に対処するなどのシナリオでは、自動調査と対応 [が役立ちます](address-compromised-users-quickly.md)。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-171">Automated investigation and response can be helpful in scenarios such as [addressing compromised user accounts quickly](address-compromised-users-quickly.md).</span></span>

<span data-ttu-id="ec6c3-172">詳細については、「自動調査と応答[(AIR)](office-365-air.md)の使用を開始する」を参照Office 365。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-172">To learn more, see [Get started using Automated investigation and response (AIR) in Office 365](office-365-air.md).</span></span>

## <a name="trends"></a><span data-ttu-id="ec6c3-173">傾向</span><span class="sxs-lookup"><span data-stu-id="ec6c3-173">Trends</span></span>

<span data-ttu-id="ec6c3-174">セキュリティ ダッシュボードの下部に [傾向] セクションがあります。組織のメール フローの傾向を要約します。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-174">Near the bottom of the Security Dashboard is a **Trends** section, which summarizes email flow trends for your organization.</span></span> <span data-ttu-id="ec6c3-175">レポートは、スパム、マルウェア、フィッシング詐欺、および優れたメールとして分類された電子メールに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-175">Reports provide information about email categorized as spam, malware, phishing attempts, and good email.</span></span> <span data-ttu-id="ec6c3-176">タイルをクリックすると、レポートの詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-176">Click a tile to view more detailed information in the report.</span></span>

![[傾向] セクションでは、組織の電子メール フローの傾向を要約します。](../../media/trends.png)

<span data-ttu-id="ec6c3-178">また、組織のサブスクリプションに defender [for Office 365 Plan 2](office-365-ti.md)が含まれる場合は、セキュリティ チームが優先度の高いセキュリティ アラートを表示してアクションを実行できる[最近の脅威管理アラート] レポートもこのセクションに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-178">And, if your organization's subscription includes [Defender for Office 365 Plan 2](office-365-ti.md), you will also have a **Recent threat management alerts** report in this section that enables your security team to view and take action on high-priority security alerts.</span></span>

<span data-ttu-id="ec6c3-179">送信電子メール ウィジェットと受信メール ウィジェットを表示またはアクセスするには、レポートの Defender を表示するためのアクセス許可Office 365があります。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-179">To view or access the Sent and Received Email widget, you must have permissions to view Defender for Office 365 reports.</span></span> <span data-ttu-id="ec6c3-180">詳細については、「レポートの Defender を表示するために必要なアクセス許可[Office 365」を参照してください](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-180">To learn more, see [What permissions are needed to view the Defender for Office 365 reports?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).</span></span>

<span data-ttu-id="ec6c3-181">最近の脅威管理アラート ウィジェットを表示またはアクセスするには、アラートを表示するためのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-181">To view or access the Recent Threat Management Alerts widget, you must have permissions to view alerts.</span></span> <span data-ttu-id="ec6c3-182">詳細については、「アラートを表示するために [必要な RBAC アクセス許可」を参照してください](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)。</span><span class="sxs-lookup"><span data-stu-id="ec6c3-182">To learn more, see [RBAC permissions required to view alerts](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ec6c3-183">関連項目</span><span class="sxs-lookup"><span data-stu-id="ec6c3-183">Related topics</span></span>

[<span data-ttu-id="ec6c3-184">セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する</span><span class="sxs-lookup"><span data-stu-id="ec6c3-184">View email security reports in the Security & Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="ec6c3-185">Microsoft Defender for microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ec6c3-185">View reports for Microsoft Defender for Office 365</span></span>](view-reports-for-mdo.md)

[<span data-ttu-id="ec6c3-186">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="ec6c3-186">Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="ec6c3-187">Office 365脅威の調査と対応</span><span class="sxs-lookup"><span data-stu-id="ec6c3-187">Office 365 Threat investigation and response</span></span>](office-365-ti.md)