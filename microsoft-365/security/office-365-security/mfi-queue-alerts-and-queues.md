---
title: メール フロー ダッシュボードでのキューの分析情報
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードでキュー ウィジェットを使用して、送信コネクタを使用してオンプレミスまたはパートナー組織への失敗したメール フローを監視する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 73e97cbbd05e298013e9e686053a969d587ad5cf
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029152"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="e4921-103">セキュリティ/コンプライアンス センターでの&の分析情報</span><span class="sxs-lookup"><span data-stu-id="e4921-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e4921-104">コネクタを使用して組織からオンプレミスまたはパートナーの電子メール サーバーにメッセージを送信できない場合、メッセージは Microsoft 365 でキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="e4921-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="e4921-105">この状態を引き起こす一般的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="e4921-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="e4921-106">コネクタが正しく構成されていません。</span><span class="sxs-lookup"><span data-stu-id="e4921-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="e4921-107">オンプレミス環境でネットワークまたはファイアウォールの変更が行いました。</span><span class="sxs-lookup"><span data-stu-id="e4921-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="e4921-108">Microsoft 365 は引き続き配信を 24 時間再試行します。</span><span class="sxs-lookup"><span data-stu-id="e4921-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="e4921-109">24 時間後、メッセージは有効期限が切れ、配信拒否レポート (NDRs またはバウンス メッセージとも呼ばれる) で送信者に返されます。</span><span class="sxs-lookup"><span data-stu-id="e4921-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="e4921-110">キューに入った電子メール ボリュームが定義済みのしきい値 (既定値は 200 メッセージ) を超える場合、情報は次の場所で使用できます。</span><span class="sxs-lookup"><span data-stu-id="e4921-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="e4921-111">セキュリティ **/コンプライアンス** センターの [メール](mail-flow-insights-v2.md) フロー ダッシュボードの [キュー&表示されます](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="e4921-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="e4921-112">詳細については、この記事の「メール フロー ダッシュボード」セクションの [「](#queues-insight-in-the-mail-flow-dashboard) キュー」の分析情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4921-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="e4921-113">アラートは、セキュリティ/**コンプライアンス** センター (アラート ダッシュボードまたは) の [[最近&](https://protection.office.com)**アラート]** \> **ダッシュボードに表示** されます <https://protection.office.com/alertsdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="e4921-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![セキュリティ/コンプライアンス センターのアラート ダッシュボード&最近のアラート](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="e4921-115">管理者は、"メッセージ" という名前の既定のアラート ポリシーの構成に基づいて、電子メール通知 **を受信します**。</span><span class="sxs-lookup"><span data-stu-id="e4921-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="e4921-116">このアラートの通知設定を構成するには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4921-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="e4921-117">アラート ポリシーの詳細については、セキュリティ/コンプライアンス センターの「アラート [&参照してください](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e4921-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="e4921-118">キュー通知をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="e4921-118">Customize queue alerts</span></span>

1. <span data-ttu-id="e4921-119">セキュリティ/ [コンプライアンス センターで&](https://protection.office.com)アラート **ポリシー** に移動するか \> **、開** きます <https://protection.office.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="e4921-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="e4921-120">[アラート **ポリシー] ページで** 、[メッセージ] という名前のポリシーを見つけて **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e4921-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="e4921-121">メッセージが **遅延して表示される** フライアウトで、通知をオンまたはオフにし、通知設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="e4921-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![メッセージは、セキュリティ/コンプライアンス センターの警告ポリシー&遅れています](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="e4921-123">**状態**: アラートのオンとオフを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="e4921-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="e4921-124">**電子メールの受信者と** **1 日の通知の制限**: [編集 **]** をクリックして、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="e4921-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="e4921-125">通知設定を構成するには、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="e4921-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="e4921-126">表示される **ポリシーの** 編集フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="e4921-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="e4921-127">**電子メール通知の** 送信 : 既定値はオンです。</span><span class="sxs-lookup"><span data-stu-id="e4921-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="e4921-128">**電子メールの受信者**: 既定値は **TenantAdmins です**。</span><span class="sxs-lookup"><span data-stu-id="e4921-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="e4921-129">**1 日の通知の** 制限 : 既定値は **[制限なし] です**。</span><span class="sxs-lookup"><span data-stu-id="e4921-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="e4921-130">**しきい** 値 : 既定値は 200 です。</span><span class="sxs-lookup"><span data-stu-id="e4921-130">**Threshold**: The default value is 200.</span></span>

   ![メッセージの通知設定は、セキュリティ/コンプライアンス センターの警告ポリシーの&されています。](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="e4921-132">完了したら、[保存して閉じる] **を** クリック **します**。</span><span class="sxs-lookup"><span data-stu-id="e4921-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="e4921-133">メール フロー ダッシュボードでのキューの分析情報</span><span class="sxs-lookup"><span data-stu-id="e4921-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="e4921-134">キューに入っているメッセージ ボリュームがしきい値を超えていてアラートが生成されていない場合でも、メール フローダッシュボードでキューの分析[](mail-flow-insights-v2.md)情報を使用して、1 時間以上キューに入っているメッセージを確認し、キューに入っているメッセージの数が多くなりすぎる前にアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="e4921-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボード&ウィジェット](../../media/mfi-queues-widget.png)

<span data-ttu-id="e4921-136">ウィジェット上のメッセージ数をクリックすると、キューに入った **メッセージ** のフライアウトが次の情報と一緒に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e4921-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="e4921-137">**キューに入ったメッセージの数**</span><span class="sxs-lookup"><span data-stu-id="e4921-137">**Number of queued messages**</span></span>
- <span data-ttu-id="e4921-138">**コネクタ名**: コネクタ名をクリックして、Exchange 管理センター (EAC) でコネクタを管理します。</span><span class="sxs-lookup"><span data-stu-id="e4921-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="e4921-139">**キューの開始時刻**</span><span class="sxs-lookup"><span data-stu-id="e4921-139">**Queue started time**</span></span>
- <span data-ttu-id="e4921-140">**最も古いメッセージの有効期限が切れています**</span><span class="sxs-lookup"><span data-stu-id="e4921-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="e4921-141">**送信先サーバー**</span><span class="sxs-lookup"><span data-stu-id="e4921-141">**Destination server**</span></span>
- <span data-ttu-id="e4921-142">**最後の IP アドレス**</span><span class="sxs-lookup"><span data-stu-id="e4921-142">**Last IP address**</span></span>
- <span data-ttu-id="e4921-143">**最後のエラー**</span><span class="sxs-lookup"><span data-stu-id="e4921-143">**Last error**</span></span>
- <span data-ttu-id="e4921-144">**解決方法**: 一般的な問題と解決策を利用できます。</span><span class="sxs-lookup"><span data-stu-id="e4921-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="e4921-145">If is a **Fix it now** link is available, click it to fix the problem.</span><span class="sxs-lookup"><span data-stu-id="e4921-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="e4921-146">それ以外の場合は、使用可能なリンクをクリックして、エラーと考えられる解決策の詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="e4921-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![メール フロー ダッシュボードでキューの分析情報をクリックした後の詳細](../../media/mfi-queues-details.png)

<span data-ttu-id="e4921-148">メッセージが遅延アラートの詳細で [キューの表示] をクリックすると、同じ **フライアウトが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="e4921-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![セキュリティ/コンプライアンス センターでメッセージの警告の&されています](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="e4921-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="e4921-150">See also</span></span>

<span data-ttu-id="e4921-151">メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="e4921-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
