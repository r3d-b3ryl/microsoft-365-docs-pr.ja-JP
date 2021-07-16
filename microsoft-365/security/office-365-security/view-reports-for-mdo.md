---
title: Microsoft Defender for Office 365 レポートを表示する
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理者は、管理者ポータルで使用できるレポートのOffice 365 Defender を検索して使用するMicrosoft 365 Defenderできます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e8bb03202139137adf55c4c10230b1c4e99253ba
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454723"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="cc91f-103">ポータルでレポートOffice 365 Defender をMicrosoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="cc91f-103">View Defender for Office 365 reports in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cc91f-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="cc91f-104">**Applies to**</span></span>
- [<span data-ttu-id="cc91f-105">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="cc91f-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cc91f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc91f-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="cc91f-107">Office 365 組織向け Microsoft Defender (Microsoft 365 E5 サブスクリプション、Office 365 プラン 1 の Microsoft Defender、Office 365 プラン 2 アドオンの Microsoft Defender など) には、さまざまなセキュリティ関連レポートが含まれる。</span><span class="sxs-lookup"><span data-stu-id="cc91f-107">Microsoft Defender for Office 365 organizations (for example, Microsoft 365 E5 subscriptions or Microsoft Defender for Office 365 Plan 1 or Microsoft Defender for Office 365 Plan 2 add-ons) contain a variety of security-related reports.</span></span> <span data-ttu-id="cc91f-108">必要な [アクセス許可を](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)持っている場合は、[レポートの電子メール] Microsoft 365 Defender コラボレーション レポートにアクセスして、Microsoft 365 Defender ポータルでこれらのレポート& \> **を** \> **表示&できます**。</span><span class="sxs-lookup"><span data-stu-id="cc91f-108">If you have the [necessary permissions](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports), you can view these reports in the Microsoft 365 Defender portal by going to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="cc91f-109">[コラボレーション レポートの電子メール] **ページ&移動するには、** を開きます <https://security.microsoft.com/emailandcollabreport> 。</span><span class="sxs-lookup"><span data-stu-id="cc91f-109">To go directly to the **Email & collaboration reports** page, open <https://security.microsoft.com/emailandcollabreport>.</span></span>

![[&] ポータルの [コラボレーション レポート] ページMicrosoft 365 Defenderメール](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> <span data-ttu-id="cc91f-111">Defender を必要としない電子メール セキュリティ レポートについては、「Office 365 ポータルの電子メール セキュリティ レポートの表示」[でMicrosoft 365 Defenderされています](view-email-security-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="cc91f-111">Email security reports that don't require Defender for Office 365 are described in [View email security reports in the Microsoft 365 Defender portal](view-email-security-reports.md).</span></span>
>
> <span data-ttu-id="cc91f-112">メール フローに関連するレポートは、現在、Exchangeセンター (EAC) に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-112">Reports that are related to mail flow are now in the Exchange admin center (EAC).</span></span> <span data-ttu-id="cc91f-113">これらのレポートの詳細については、「新しい管理センターのメール フロー レポート[Exchange参照してください](/exchange/monitoring/mail-flow-reports/mail-flow-reports)。</span><span class="sxs-lookup"><span data-stu-id="cc91f-113">For more information about these reports, see [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).</span></span>

## <a name="safe-attachments-file-types-report"></a><span data-ttu-id="cc91f-114">セーフ添付ファイルの種類レポート</span><span class="sxs-lookup"><span data-stu-id="cc91f-114">Safe Attachments file types report</span></span>

> [!NOTE]
> <span data-ttu-id="cc91f-115">[**添付セーフファイルの種類] レポートは**、最終的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-115">The **Safe Attachments file types report** will eventually go away.</span></span> <span data-ttu-id="cc91f-116">脅威保護の状態レポートでも同 [じ情報を使用できます](#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="cc91f-116">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="safe-attachments-message-disposition-report"></a><span data-ttu-id="cc91f-117">セーフ添付ファイル メッセージの廃棄レポート</span><span class="sxs-lookup"><span data-stu-id="cc91f-117">Safe Attachments message disposition report</span></span>

> [!NOTE]
> <span data-ttu-id="cc91f-118">添付 **セーフメッセージ廃棄レポートは**、最終的に消え去ります。</span><span class="sxs-lookup"><span data-stu-id="cc91f-118">The **Safe Attachments message disposition report** will eventually go away.</span></span> <span data-ttu-id="cc91f-119">脅威保護の状態レポートでも同 [じ情報を使用できます](#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="cc91f-119">The same information is available in the [Threat protection status report](#threat-protection-status-report).</span></span>

## <a name="mail-latency-report"></a><span data-ttu-id="cc91f-120">メール遅延レポート</span><span class="sxs-lookup"><span data-stu-id="cc91f-120">Mail latency report</span></span>

<span data-ttu-id="cc91f-121">[ **メール待機時間] レポートには** 、組織内で発生したメール配信とデトレーションの待機時間の集計ビューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-121">The **Mail latency report** shows you an aggregate view of the mail delivery and detonation latency experienced within your organization.</span></span> <span data-ttu-id="cc91f-122">サービス内のメール配信時間は、多くの要因によって影響を受け、絶対配信時間 (秒) は成功または問題を示す良い指標ではない場合が多いです。</span><span class="sxs-lookup"><span data-stu-id="cc91f-122">Mail delivery times in the service are affected by a number of factors, and the absolute delivery time in seconds is often not a good indicator of success or a problem.</span></span> <span data-ttu-id="cc91f-123">ある日の配信時間が遅い場合は、別の日の平均配信時間、またはその逆と見なされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="cc91f-123">A slow delivery time on one day might be considered an average delivery time on another day, or vice-versa.</span></span> <span data-ttu-id="cc91f-124">これにより、他のメッセージの観測配信時間に関する統計データに基づいて、メッセージ配信を修飾します。</span><span class="sxs-lookup"><span data-stu-id="cc91f-124">This tries to qualify message delivery based on statistical data about the observed delivery times of other messages.</span></span>

<span data-ttu-id="cc91f-125">クライアント側とネットワークの待機時間は含まれません。</span><span class="sxs-lookup"><span data-stu-id="cc91f-125">Client side and network latency are not included.</span></span>

<span data-ttu-id="cc91f-126">レポートを表示するには、Microsoft 365 Defender ポータル [を開き、[](https://security.microsoft.com)レポートの電子メール] & \> **グループ**& \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="cc91f-126">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="cc91f-127">[電子メール **&コラボレーション レポート] ページ** で、[ **メール遅延レポート** ] を探し、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cc91f-127">On the **Email & collaboration reports** page, find **Mail latency report** and then click **View details**.</span></span> <span data-ttu-id="cc91f-128">レポートに直接移動するには、を開きます <https://security.microsoft.com/mailLatencyReport> 。</span><span class="sxs-lookup"><span data-stu-id="cc91f-128">To go directly to the report, open <https://security.microsoft.com/mailLatencyReport>.</span></span>

![[メールの遅延レポート] ページの [メールの&レポート] ウィジェット](../../media/mail-latency-report-widget.png)

<span data-ttu-id="cc91f-130">[メール **の待機時間レポート] ページで** 、[メールの待機時間] レポート ページで次 **のタブを使用** できます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-130">On the **Mail latency report** page, the following tabs are available on the **Mail latency report** page:</span></span>

- <span data-ttu-id="cc91f-131">**50 パーセント :** これは、メッセージの配信時間の中央です。</span><span class="sxs-lookup"><span data-stu-id="cc91f-131">**50th percentile**: This is the middle for message delivery times.</span></span> <span data-ttu-id="cc91f-132">この値は、平均配信時間と見なされます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-132">You can consider this value as an average delivery time.</span></span> <span data-ttu-id="cc91f-133">このタブは既定で選択されています。</span><span class="sxs-lookup"><span data-stu-id="cc91f-133">This tab is selected by default.</span></span>
- <span data-ttu-id="cc91f-134">**90 パーセント :** これは、メッセージ配信の待機時間が長いを示します。</span><span class="sxs-lookup"><span data-stu-id="cc91f-134">**90th percentile**: This indicates a high latency for message delivery.</span></span> <span data-ttu-id="cc91f-135">配信にこの値を超える時間がかかったメッセージはわずか 10% です。</span><span class="sxs-lookup"><span data-stu-id="cc91f-135">Only 10% of messages took longer than this value to deliver.</span></span>
- <span data-ttu-id="cc91f-136">**99 パーセント :** メッセージ配信の最大待機時間を示します。</span><span class="sxs-lookup"><span data-stu-id="cc91f-136">**99th percentile**: This indicates the highest latency for message delivery.</span></span>

<span data-ttu-id="cc91f-137">選択したタブに関係なく、グラフには次のカテゴリに分類されたメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-137">Regardless of the tab you select, the chart shows messages organized into the following categories:</span></span>

- <span data-ttu-id="cc91f-138">**メール配信の待機時間**</span><span class="sxs-lookup"><span data-stu-id="cc91f-138">**Mail delivery latency**</span></span>
- <span data-ttu-id="cc91f-139">**Detonations**</span><span class="sxs-lookup"><span data-stu-id="cc91f-139">**Detonations**</span></span>

<span data-ttu-id="cc91f-140">グラフのカテゴリにカーソルを合わせると、各カテゴリの待機時間の内訳を確認できます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-140">When you hover over a category in the chart, you can see a breakdown of the latency in each category.</span></span>

![メール待機時間レポートの 50 パーセント表示](../../media/mail-latency-report-50th-percentile-view.png)

<span data-ttu-id="cc91f-142">[フィルター] **をクリック** すると、グラフと詳細テーブルの両方を次の値でフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-142">If you click **Filter**, you can filter both the chart and the details table by the following values:</span></span>

- <span data-ttu-id="cc91f-143">**日付 (UTC)**:**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="cc91f-143">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="cc91f-144">**メッセージ ビュー**: 次のいずれかの値。</span><span class="sxs-lookup"><span data-stu-id="cc91f-144">**Message view**: One of the following values:</span></span>
  - <span data-ttu-id="cc91f-145">**すべてのメッセージ**</span><span class="sxs-lookup"><span data-stu-id="cc91f-145">**All messages**</span></span>
  - <span data-ttu-id="cc91f-146">**添付ファイルまたは URL を含むメッセージ**</span><span class="sxs-lookup"><span data-stu-id="cc91f-146">**Messages that contain attachments or URLs**</span></span>
  - <span data-ttu-id="cc91f-147">**削除されたメッセージ**</span><span class="sxs-lookup"><span data-stu-id="cc91f-147">**Detonated messages**</span></span>

<span data-ttu-id="cc91f-148">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cc91f-148">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="cc91f-149">グラフの下の詳細テーブルでは、次の情報を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-149">In the details table below the chart, the following information is available:</span></span>

- <span data-ttu-id="cc91f-150">**日付 (UTC)**</span><span class="sxs-lookup"><span data-stu-id="cc91f-150">**Date (UTC)**</span></span>
- <span data-ttu-id="cc91f-151">**パーセント :** **50** **、90、\*\*\*\*または 99**</span><span class="sxs-lookup"><span data-stu-id="cc91f-151">**Percentiles**: **50**, **90**, or **99**</span></span>
- <span data-ttu-id="cc91f-152">**メッセージ数**</span><span class="sxs-lookup"><span data-stu-id="cc91f-152">**Message count**</span></span>
- <span data-ttu-id="cc91f-153">**全体的な待機時間**</span><span class="sxs-lookup"><span data-stu-id="cc91f-153">**Overall latency**</span></span>

## <a name="threat-protection-status-report"></a><span data-ttu-id="cc91f-154">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="cc91f-154">Threat protection status report</span></span>

<span data-ttu-id="cc91f-155">脅威 **保護の状態** レポートは [、Exchange Online Protection](exchange-online-protection-overview.md) (EOP) と Microsoft Defender for Office 365 によって検出およびブロックされた悪意のあるコンテンツと悪意のある電子メールに関する情報をまとめる単一のビューです。</span><span class="sxs-lookup"><span data-stu-id="cc91f-155">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) and Microsoft Defender for Office 365.</span></span> <span data-ttu-id="cc91f-156">詳細については、「脅威保護の [状態レポート」を参照してください](view-email-security-reports.md#threat-protection-status-report)。</span><span class="sxs-lookup"><span data-stu-id="cc91f-156">For more information, see [Threat protection status report](view-email-security-reports.md#threat-protection-status-report).</span></span>

## <a name="url-threat-protection-report"></a><span data-ttu-id="cc91f-157">URL 脅威保護レポート</span><span class="sxs-lookup"><span data-stu-id="cc91f-157">URL threat protection report</span></span>

<span data-ttu-id="cc91f-158">**URL 脅威保護レポートには、** 検出された脅威の概要と傾向ビュー、および URL クリックに対するアクションが[リンク] リンクの一部としてセーフ [されます](safe-links.md)。</span><span class="sxs-lookup"><span data-stu-id="cc91f-158">The **URL threat protection report** provides summary and trend views for threats detected and actions taken on URL clicks as part of [Safe Links](safe-links.md).</span></span> <span data-ttu-id="cc91f-159">このレポートには、[リンク] ポリシーが適用されているユーザーセーフクリックデータが含まれる場合は、[ユーザーのクリックを追跡しない]**オプションが** 選択されています。</span><span class="sxs-lookup"><span data-stu-id="cc91f-159">This report will not have click data from users where the Safe Links policy applied has the **Do not track user clicks** option selected.</span></span>

<span data-ttu-id="cc91f-160">レポートを表示するには、Microsoft 365 Defender ポータル [を開き、[](https://security.microsoft.com)レポートの電子メール] & \> **グループ**& \> **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="cc91f-160">To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** \> **Email & collaboration** \> **Email & collaboration reports**.</span></span> <span data-ttu-id="cc91f-161">[コラボレーション **レポートのメール&] ページ** で **、[URL 保護] ページ** を探し、[詳細の表示] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cc91f-161">On the **Email & collaboration reports** page, find **URL protection page** and then click **View details**.</span></span> <span data-ttu-id="cc91f-162">レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/URLProtectionActionReport> 。</span><span class="sxs-lookup"><span data-stu-id="cc91f-162">To go directly to the report, open <https://security.microsoft.com/reports/URLProtectionActionReport>.</span></span>

![[コラボレーション レポートの電子メール] ページ& URL 保護レポート ウィジェット](../../media/url-protection-report-widget.png)

<span data-ttu-id="cc91f-164">[URL 脅威保護レポート] **ページで** 使用可能なビューについては、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="cc91f-164">The available views on the **URL threat protection** report page are described in the following sections.</span></span>

> [!NOTE]
> <span data-ttu-id="cc91f-165">これは保護傾向 *レポートで、* データは大きなデータセットの傾向を表します。</span><span class="sxs-lookup"><span data-stu-id="cc91f-165">This is a *protection trend report*, meaning data represents trends in a larger dataset.</span></span> <span data-ttu-id="cc91f-166">その結果、グラフ内のデータはリアルタイムでは使用できませんが、詳細テーブルのデータは次の値なので、2 つのデータの間に若干の不一致が見られます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-166">As a result, the data in the charts is not available in real time here, but the data in the details table is, so you may see a slight discrepancy between the two.</span></span> <span data-ttu-id="cc91f-167">グラフは 4 時間に 1 回更新され、過去 90 日間のデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc91f-167">The charts are refreshed once every four hours and contain data for the last 90 days.</span></span>

### <a name="view-data-by-url-click-protection-action"></a><span data-ttu-id="cc91f-168">URL クリック保護アクションによるデータの表示</span><span class="sxs-lookup"><span data-stu-id="cc91f-168">View data by URL click protection action</span></span>

![URL 脅威保護レポートの URL クリック保護アクション ビュー](../../media/url-threat-protection-report-url-click-protection-action-view.png)

<span data-ttu-id="cc91f-170">[URL **によるデータの表示] クリック保護アクション** ビューには、組織内のユーザーによる URL クリックの数と、クリックの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-170">The **View data by URL click protection action** view shows the number of URL clicks by users in the organization and the results of the click:</span></span>

- <span data-ttu-id="cc91f-171">**許可 :** ユーザーは URL に移動できます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-171">**Allowed**: The user was allowed to navigate to the URL.</span></span>
- <span data-ttu-id="cc91f-172">**ブロック :** ユーザーが URL への移動をブロックされました。</span><span class="sxs-lookup"><span data-stu-id="cc91f-172">**Blocked**: The user was blocked from navigating to the URL.</span></span>
- <span data-ttu-id="cc91f-173">**ブロックおよびクリックスルー**: ユーザーが URL への移動を続行する選択をしました。</span><span class="sxs-lookup"><span data-stu-id="cc91f-173">**Blocked and clicked through**: The user has chosen to continue navigating to the URL.</span></span>
- <span data-ttu-id="cc91f-174">**スキャン中にクリックスルー**: スキャンが完了する前に、ユーザーがリンクをクリックしました。</span><span class="sxs-lookup"><span data-stu-id="cc91f-174">**Clicked through during scan**: The user has clicked on the link before the scan was complete.</span></span>

<span data-ttu-id="cc91f-175">クリックすると、ユーザーがブロック ページをクリックして悪意のある Web サイトに移動した (管理者は、[リンク] ポリシーでクリックセーフ無効にできます)。</span><span class="sxs-lookup"><span data-stu-id="cc91f-175">A click indicates that the user has clicked through the block page to the malicious website (admins can disable click through in Safe Links policies).</span></span>

<span data-ttu-id="cc91f-176">[フィルター] **をクリック** すると、表示されるフライアウトで次の値の 1 つ以上を選択して、レポートと詳細テーブルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-176">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="cc91f-177">**日付 (UTC)**:**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="cc91f-177">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="cc91f-178">**検出**:</span><span class="sxs-lookup"><span data-stu-id="cc91f-178">**Detection**:</span></span>
  - <span data-ttu-id="cc91f-179">**可**</span><span class="sxs-lookup"><span data-stu-id="cc91f-179">**Allowed**</span></span>
  - <span data-ttu-id="cc91f-180">**ブロック済み**</span><span class="sxs-lookup"><span data-stu-id="cc91f-180">**Blocked**</span></span>
  - <span data-ttu-id="cc91f-181">**ブロックおよびクリックスルー**</span><span class="sxs-lookup"><span data-stu-id="cc91f-181">**Blocked and clicked through**</span></span>
  - <span data-ttu-id="cc91f-182">**スキャン中にクリックスルー**</span><span class="sxs-lookup"><span data-stu-id="cc91f-182">**Clicked through during scan**</span></span>
- <span data-ttu-id="cc91f-183">**Domains**: レポートの結果に表示される URL ドメイン。</span><span class="sxs-lookup"><span data-stu-id="cc91f-183">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="cc91f-184">**受信者**</span><span class="sxs-lookup"><span data-stu-id="cc91f-184">**Recipients**</span></span>

<span data-ttu-id="cc91f-185">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cc91f-185">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="cc91f-186">グラフの下の詳細テーブルには、過去 7 日間に組織内で発生したすべてのクリックのほぼリアルタイム ビューが示されています。</span><span class="sxs-lookup"><span data-stu-id="cc91f-186">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="cc91f-187">**クリック時間**</span><span class="sxs-lookup"><span data-stu-id="cc91f-187">**Click time**</span></span>
- <span data-ttu-id="cc91f-188">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="cc91f-188">**User**</span></span>
- <span data-ttu-id="cc91f-189">**URL**</span><span class="sxs-lookup"><span data-stu-id="cc91f-189">**URL**</span></span>
- <span data-ttu-id="cc91f-190">**Action**</span><span class="sxs-lookup"><span data-stu-id="cc91f-190">**Action**</span></span>
- <span data-ttu-id="cc91f-191">**アプリ**</span><span class="sxs-lookup"><span data-stu-id="cc91f-191">**App**</span></span>

### <a name="view-data-by-url-click-by-application"></a><span data-ttu-id="cc91f-192">アプリケーション別の URL クリックによるデータの表示</span><span class="sxs-lookup"><span data-stu-id="cc91f-192">View data by URL click by application</span></span>

![URL 脅威保護レポートのアプリケーション ビューによる URL クリック](../../media/url-threat-protection-report-url-click-by-application-view.png)

<span data-ttu-id="cc91f-194">[URL **によるデータの表示] アプリケーション** によるクリックビューには、リンクをサポートするアプリによる URL クリック数セーフ表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-194">The **View data by URL click by application** view shows the number of URL clicks by apps that support Safe Links:</span></span>

- <span data-ttu-id="cc91f-195">**電子メール クライアント**</span><span class="sxs-lookup"><span data-stu-id="cc91f-195">**Email client**</span></span>
- <span data-ttu-id="cc91f-196">**PowerPoint**</span><span class="sxs-lookup"><span data-stu-id="cc91f-196">**PowerPoint**</span></span>
- <span data-ttu-id="cc91f-197">**Word**</span><span class="sxs-lookup"><span data-stu-id="cc91f-197">**Word**</span></span>
- <span data-ttu-id="cc91f-198">**Excel**</span><span class="sxs-lookup"><span data-stu-id="cc91f-198">**Excel**</span></span>
- <span data-ttu-id="cc91f-199">**OneNote**</span><span class="sxs-lookup"><span data-stu-id="cc91f-199">**OneNote**</span></span>
- <span data-ttu-id="cc91f-200">**Visio**</span><span class="sxs-lookup"><span data-stu-id="cc91f-200">**Visio**</span></span>
- <span data-ttu-id="cc91f-201">**Teams**</span><span class="sxs-lookup"><span data-stu-id="cc91f-201">**Teams**</span></span>
- <span data-ttu-id="cc91f-202">**Others**</span><span class="sxs-lookup"><span data-stu-id="cc91f-202">**Others**</span></span>

<span data-ttu-id="cc91f-203">[フィルター] **をクリック** すると、表示されるフライアウトで次の値の 1 つ以上を選択して、レポートと詳細テーブルを変更できます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-203">If you click **Filters**, you can modify the report and the details table by selecting one or more of the following values in the flyout that appears:</span></span>

- <span data-ttu-id="cc91f-204">**日付 (UTC)**:**開始日と\*\*\*\*終了日**</span><span class="sxs-lookup"><span data-stu-id="cc91f-204">**Date (UTC)**: **Start date** and **End date**</span></span>
- <span data-ttu-id="cc91f-205">**検出**: グラフから使用可能なアプリ。</span><span class="sxs-lookup"><span data-stu-id="cc91f-205">**Detection**: Available apps from the chart.</span></span>
- <span data-ttu-id="cc91f-206">**Domains**: レポートの結果に表示される URL ドメイン。</span><span class="sxs-lookup"><span data-stu-id="cc91f-206">**Domains**: The URL domains listed in the report results.</span></span>
- <span data-ttu-id="cc91f-207">**受信者**</span><span class="sxs-lookup"><span data-stu-id="cc91f-207">**Recipients**</span></span>

<span data-ttu-id="cc91f-208">フィルターの構成が完了したら、[適用]、[**キャンセル**]、または [フィルターのクリア]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="cc91f-208">When you're finished configuring the filters, click **Apply**, **Cancel**, or **Clear filters**.</span></span>

<span data-ttu-id="cc91f-209">グラフの下の詳細テーブルには、過去 7 日間に組織内で発生したすべてのクリックのほぼリアルタイム ビューが示されています。</span><span class="sxs-lookup"><span data-stu-id="cc91f-209">The details table below the chart provides the following near-real-time view of all clicks that happened within the organization for the last 7 days:</span></span>

- <span data-ttu-id="cc91f-210">**クリック時間**</span><span class="sxs-lookup"><span data-stu-id="cc91f-210">**Click time**</span></span>
- <span data-ttu-id="cc91f-211">**ユーザー**</span><span class="sxs-lookup"><span data-stu-id="cc91f-211">**User**</span></span>
- <span data-ttu-id="cc91f-212">**URL**</span><span class="sxs-lookup"><span data-stu-id="cc91f-212">**URL**</span></span>
- <span data-ttu-id="cc91f-213">**Action**</span><span class="sxs-lookup"><span data-stu-id="cc91f-213">**Action**</span></span>
- <span data-ttu-id="cc91f-214">**アプリ**</span><span class="sxs-lookup"><span data-stu-id="cc91f-214">**App**</span></span>

## <a name="additional-reports-to-view"></a><span data-ttu-id="cc91f-215">表示するその他のレポート</span><span class="sxs-lookup"><span data-stu-id="cc91f-215">Additional reports to view</span></span>

<span data-ttu-id="cc91f-216">この記事で説明するレポートに加えて、次の表で説明するように、いくつかの他のレポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-216">In addition to the reports described in this article, several other reports are available, as described in the following table:</span></span>

<br>

****

|<span data-ttu-id="cc91f-217">レポート</span><span class="sxs-lookup"><span data-stu-id="cc91f-217">Report</span></span>|<span data-ttu-id="cc91f-218">トピック</span><span class="sxs-lookup"><span data-stu-id="cc91f-218">Topic</span></span>|
|---|---|
|<span data-ttu-id="cc91f-219">**エクスプローラー** (Microsoft Defender for Office 365 プラン 2) またはリアルタイム検出 **(Microsoft** Defender for Office 365 プラン 1)</span><span class="sxs-lookup"><span data-stu-id="cc91f-219">**Explorer** (Microsoft Defender for Office 365 Plan 2) or **real-time detections** (Microsoft Defender for Office 365 Plan 1)</span></span>|[<span data-ttu-id="cc91f-220">脅威エクスプローラー (およびリアルタイムの検出)</span><span class="sxs-lookup"><span data-stu-id="cc91f-220">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)|
|<span data-ttu-id="cc91f-221">Defender を必要としない電子メール セキュリティ Office 365</span><span class="sxs-lookup"><span data-stu-id="cc91f-221">Email security reports that don't require Defender for Office 365</span></span>|[<span data-ttu-id="cc91f-222">電子メール セキュリティ レポートを Microsoft 365 Defenderする</span><span class="sxs-lookup"><span data-stu-id="cc91f-222">View email security reports in the Microsoft 365 Defender portal</span></span>](view-email-security-reports.md)|
|<span data-ttu-id="cc91f-223">管理センター (EAC) Exchangeフロー レポート</span><span class="sxs-lookup"><span data-stu-id="cc91f-223">Mail flow reports in the Exchange admin center (EAC)</span></span>|[<span data-ttu-id="cc91f-224">新しい管理センターのメール フロー Exchangeレポート</span><span class="sxs-lookup"><span data-stu-id="cc91f-224">Mail flow reports in the new Exchange admin center</span></span>](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|

<span data-ttu-id="cc91f-225">PowerShell レポートコマンドレット:</span><span class="sxs-lookup"><span data-stu-id="cc91f-225">PowerShell reporting cmdlets:</span></span>

<br>

****

|<span data-ttu-id="cc91f-226">レポート</span><span class="sxs-lookup"><span data-stu-id="cc91f-226">Report</span></span>|<span data-ttu-id="cc91f-227">トピック</span><span class="sxs-lookup"><span data-stu-id="cc91f-227">Topic</span></span>|
|---|---|
|<span data-ttu-id="cc91f-228">上位送信者および受信者</span><span class="sxs-lookup"><span data-stu-id="cc91f-228">Top senders and recipients</span></span>|[<span data-ttu-id="cc91f-229">Get-MailTrafficTopReport</span><span class="sxs-lookup"><span data-stu-id="cc91f-229">Get-MailTrafficTopReport</span></span>](/powershell/module/exchange/get-mailtraffictopreport) <p> [<span data-ttu-id="cc91f-230">Get-MailTrafficSummaryReport</span><span class="sxs-lookup"><span data-stu-id="cc91f-230">Get-MailTrafficSummaryReport</span></span>](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|<span data-ttu-id="cc91f-231">トップ マルウェア</span><span class="sxs-lookup"><span data-stu-id="cc91f-231">Top malware</span></span>|[<span data-ttu-id="cc91f-232">Get-MailTrafficSummaryReport</span><span class="sxs-lookup"><span data-stu-id="cc91f-232">Get-MailTrafficSummaryReport</span></span>](/powershell/module/exchange/get-mailtrafficsummaryreport)|
|<span data-ttu-id="cc91f-233">メール トラフィック</span><span class="sxs-lookup"><span data-stu-id="cc91f-233">Mail traffic</span></span>|[<span data-ttu-id="cc91f-234">Get-MailTrafficATPReport</span><span class="sxs-lookup"><span data-stu-id="cc91f-234">Get-MailTrafficATPReport</span></span>](/powershell/module/exchange/get-mailtrafficatpreport) <p> [<span data-ttu-id="cc91f-235">Get-MailDetailATPReport</span><span class="sxs-lookup"><span data-stu-id="cc91f-235">Get-MailDetailATPReport</span></span>](/powershell/module/exchange/get-maildetailatpreport)|
|<span data-ttu-id="cc91f-236">安全なリンク</span><span class="sxs-lookup"><span data-stu-id="cc91f-236">Safe Links</span></span>|[<span data-ttu-id="cc91f-237">Get-SafeLinksAggregateReport</span><span class="sxs-lookup"><span data-stu-id="cc91f-237">Get-SafeLinksAggregateReport</span></span>](/powershell/module/exchange/get-safelinksaggregatereport) <p> [<span data-ttu-id="cc91f-238">Get-SafeLinksDetailReport</span><span class="sxs-lookup"><span data-stu-id="cc91f-238">Get-SafeLinksDetailReport</span></span>](/powershell/module/exchange/get-safelinksdetailreport)|
|<span data-ttu-id="cc91f-239">侵害されたユーザー</span><span class="sxs-lookup"><span data-stu-id="cc91f-239">Compromised users</span></span>|[<span data-ttu-id="cc91f-240">Get-CompromisedUserAggregateReport</span><span class="sxs-lookup"><span data-stu-id="cc91f-240">Get-CompromisedUserAggregateReport</span></span>](/powershell/module/exchange/get-compromiseduseraggregatereport) <p> [<span data-ttu-id="cc91f-241">Get-CompromisedUserDetailReport</span><span class="sxs-lookup"><span data-stu-id="cc91f-241">Get-CompromisedUserDetailReport</span></span>](/powershell/module/exchange/get-compromiseduserdetailreport)|
|<span data-ttu-id="cc91f-242">メール フローの状態</span><span class="sxs-lookup"><span data-stu-id="cc91f-242">Mail flow status</span></span>|[<span data-ttu-id="cc91f-243">Get-MailflowStatusReport</span><span class="sxs-lookup"><span data-stu-id="cc91f-243">Get-MailflowStatusReport</span></span>](/powershell/module/exchange/get-mailflowstatusreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a><span data-ttu-id="cc91f-244">レポートの Defender を表示するために必要なアクセス許可Office 365ですか?</span><span class="sxs-lookup"><span data-stu-id="cc91f-244">What permissions are needed to view the Defender for Office 365 reports?</span></span>

<span data-ttu-id="cc91f-245">この記事で説明するレポートを表示して使用するには、ポータルで次のいずれかの役割グループのメンバー Microsoft 365 Defenderがあります。</span><span class="sxs-lookup"><span data-stu-id="cc91f-245">In order to view and use the reports described in this article, you need to be a member of one of the following role groups in the Microsoft 365 Defender portal:</span></span>

- <span data-ttu-id="cc91f-246">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="cc91f-246">**Organization Management**</span></span>
- <span data-ttu-id="cc91f-247">**セキュリティ管理者**</span><span class="sxs-lookup"><span data-stu-id="cc91f-247">**Security Administrator**</span></span>
- <span data-ttu-id="cc91f-248">**セキュリティ閲覧者**</span><span class="sxs-lookup"><span data-stu-id="cc91f-248">**Security Reader**</span></span>
- <span data-ttu-id="cc91f-249">**グローバル閲覧者**</span><span class="sxs-lookup"><span data-stu-id="cc91f-249">**Global Reader**</span></span>

<span data-ttu-id="cc91f-250">詳細については、「[Microsoft 365 Defender ポータルのアクセス許可](permissions-microsoft-365-security-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc91f-250">For more information, see [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>

<span data-ttu-id="cc91f-251">**注**: Microsoft 365 管理センター の対応する Azure Active Directory ロールにユーザーを追加すると、Microsoft 365 Defender ポータルで必要なアクセス許可と、Microsoft 365 の他の機能に対するアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="cc91f-251">**Note**: Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Microsoft 365 Defender portal _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="cc91f-252">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc91f-252">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="cc91f-253">レポートにデータが表示されない場合は、</span><span class="sxs-lookup"><span data-stu-id="cc91f-253">What if the reports aren't showing data?</span></span>

<span data-ttu-id="cc91f-254">レポートのデータが Defender に表示されない場合Office 365ポリシーが正しく設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cc91f-254">If you are not seeing data in your Defender for Office 365 reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="cc91f-255">Defender for セーフ[保護](set-up-safe-links-policies.md)を有効セーフするために、[](set-up-safe-attachments-policies.md)組織にリンク ポリシーと添付ファイル Office 365が定義されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc91f-255">Your organization must have [Safe Links policies](set-up-safe-links-policies.md) and [Safe Attachments policies](set-up-safe-attachments-policies.md) defined in order for Defender for Office 365 protection to be in place.</span></span> <span data-ttu-id="cc91f-256">「スパム [対策とマルウェア対策の保護」も参照してください](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="cc91f-256">Also see [Anti-spam and anti-malware protection](anti-spam-and-anti-malware-protection.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc91f-257">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc91f-257">Related topics</span></span>

[<span data-ttu-id="cc91f-258">スマート レポートと分析情報 (Microsoft 365 Defenderポータル)</span><span class="sxs-lookup"><span data-stu-id="cc91f-258">Smart reports and insights in the Microsoft 365 Defender portal</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="cc91f-259">役割のアクセス許可 (Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cc91f-259">Role permissions (Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
