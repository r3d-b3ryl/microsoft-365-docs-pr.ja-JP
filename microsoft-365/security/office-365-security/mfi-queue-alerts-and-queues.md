---
title: メールフローダッシュボードでのキューの把握
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードにあるキューウィジェットを使用して、送信コネクタを介して社内組織またはパートナー組織への失敗したメールフローを監視する方法を学習できます。
ms.openlocfilehash: fdc3f44041990e3860deb04a36a69a3d506d334a
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577309"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="feccc-103">セキュリティ & コンプライアンスセンターでのキューの把握</span><span class="sxs-lookup"><span data-stu-id="feccc-103">Queues insight in the Security & Compliance Center</span></span>

<span data-ttu-id="feccc-104">コネクタを使用して組織からオンプレミスまたはパートナーの電子メールサーバーにメッセージを送信できない場合、メッセージは Microsoft 365 でキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="feccc-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="feccc-105">このような状態になる一般的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="feccc-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="feccc-106">コネクタが正しく構成されていません。</span><span class="sxs-lookup"><span data-stu-id="feccc-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="feccc-107">オンプレミス環境でネットワークまたはファイアウォールの変更が行われています。</span><span class="sxs-lookup"><span data-stu-id="feccc-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="feccc-108">Microsoft 365 は、24時間、引き続き配信を再試行します。</span><span class="sxs-lookup"><span data-stu-id="feccc-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="feccc-109">24時間後、メッセージは期限切れになり、配信不能レポート (Ndr またはバウンスメッセージとも呼ばれる) で送信者に返されます。</span><span class="sxs-lookup"><span data-stu-id="feccc-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="feccc-110">キューに入っている電子メールのボリュームが事前に定義されたしきい値 (既定値は200メッセージ) を超えている場合、情報は次の場所で利用できます。</span><span class="sxs-lookup"><span data-stu-id="feccc-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="feccc-111">セキュリティ & コンプライアンスセンターの[メールフローダッシュボード](mail-flow-insights-v2.md)で洞察を得る**キュー** 。</span><span class="sxs-lookup"><span data-stu-id="feccc-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center.</span></span> <span data-ttu-id="feccc-112">詳細については、このトピックの「[メールフローダッシュボード](#queues-insight-in-the-mail-flow-dashboard)」セクションの「キューの洞察」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="feccc-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this topic.</span></span>
  
- <span data-ttu-id="feccc-113">[[セキュリティ & コンプライアンスセンター](https://protection.office.com) (**alerts** dashboard または) のアラート**ダッシュボードに通知**が表示され \> **Dashboard** <https://protection.office.com/alertsdashboard> ます。</span><span class="sxs-lookup"><span data-stu-id="feccc-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![セキュリティ & コンプライアンスセンターのアラートダッシュボードでの最近の通知](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="feccc-115">管理者は、**メッセージが遅延**した既定の警告ポリシーの構成に基づいて電子メール通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="feccc-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="feccc-116">この通知の通知設定を構成するには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="feccc-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="feccc-117">アラートポリシーの詳細については、「[セキュリティ & コンプライアンスセンターのアラートポリシー](../../compliance/alert-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="feccc-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="feccc-118">キューの通知をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="feccc-118">Customize queue alerts</span></span>

1. <span data-ttu-id="feccc-119">[[セキュリティ & コンプライアンスセンター](https://protection.office.com)] で、[ **alerts** \> **Alert policies** ] または [open] に移動し <https://protection.office.com/alertpolicies> ます。</span><span class="sxs-lookup"><span data-stu-id="feccc-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="feccc-120">[**通知ポリシー** ] ページで、[**メッセージが遅延して**います] という名前のポリシーを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="feccc-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="feccc-121">メッセージが開く遅延ポップアップが表示**されて**いる場合は、アラートをオンまたはオフにして通知設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="feccc-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![メッセージが遅延していますアラートポリシーの詳細セキュリティ & コンプライアンスセンター](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="feccc-123">**状態**: アラートをオンまたはオフに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="feccc-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="feccc-124">**電子メール受信者**および**毎日の通知制限**: [**編集**] をクリックして、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="feccc-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="feccc-125">通知設定を構成するには、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="feccc-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="feccc-126">表示される [**ポリシーの編集**] ポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="feccc-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="feccc-127">**電子メール通知の送信**: 既定値は on です。</span><span class="sxs-lookup"><span data-stu-id="feccc-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="feccc-128">**電子メール受信者**: 既定値は**tenantadmins**です。</span><span class="sxs-lookup"><span data-stu-id="feccc-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="feccc-129">**毎日の通知制限**: 既定値は**無制限**です。</span><span class="sxs-lookup"><span data-stu-id="feccc-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="feccc-130">**しきい**値: 既定値は200です。</span><span class="sxs-lookup"><span data-stu-id="feccc-130">**Threshold**: The default value is 200.</span></span>

   ![メッセージの通知設定が遅延していますアラートポリシーの詳細セキュリティ & コンプライアンスセンター](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="feccc-132">完了したら、[**保存**して**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="feccc-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="feccc-133">メールフローダッシュボードでのキューの把握</span><span class="sxs-lookup"><span data-stu-id="feccc-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="feccc-134">キュー内のメッセージボリュームがしきい値を超えていない場合でも、[メールフローダッシュボード](mail-flow-insights-v2.md)の [**キュー** ] 洞察を使用して、キューに入れられたメッセージ数が多すぎることを確認してから、キューに入れられたメッセージ数が大きくなる前に処理を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="feccc-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードのキューウィジェット](../../media/mfi-queues-widget.png)

<span data-ttu-id="feccc-136">ウィジェットのメッセージ数をクリックすると、キューに**置か**れたメッセージが次の情報と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="feccc-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="feccc-137">**キューに入れられたメッセージ数**</span><span class="sxs-lookup"><span data-stu-id="feccc-137">**Number of queued messages**</span></span>
- <span data-ttu-id="feccc-138">**コネクタ名**: コネクタ名をクリックして、Exchange 管理センター (EAC) でコネクタを管理します。</span><span class="sxs-lookup"><span data-stu-id="feccc-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="feccc-139">**キューの開始時刻**</span><span class="sxs-lookup"><span data-stu-id="feccc-139">**Queue started time**</span></span>
- <span data-ttu-id="feccc-140">**期限切れの古いメッセージ**</span><span class="sxs-lookup"><span data-stu-id="feccc-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="feccc-141">**移行先サーバー**</span><span class="sxs-lookup"><span data-stu-id="feccc-141">**Destination server**</span></span>
- <span data-ttu-id="feccc-142">**最後の IP アドレス**</span><span class="sxs-lookup"><span data-stu-id="feccc-142">**Last IP address**</span></span>
- <span data-ttu-id="feccc-143">**最後のエラー**</span><span class="sxs-lookup"><span data-stu-id="feccc-143">**Last error**</span></span>
- <span data-ttu-id="feccc-144">**修正方法**: 一般的な問題と解決策を入手できます。</span><span class="sxs-lookup"><span data-stu-id="feccc-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="feccc-145">[**今すぐ修正**する] リンクが利用可能な場合は、それをクリックして問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="feccc-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="feccc-146">エラーおよび可能な解決方法の詳細については、使用可能なリンクをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="feccc-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![メールフローダッシュボードでのキューの洞察をクリックした後の詳細](../../media/mfi-queues-details.png)

<span data-ttu-id="feccc-148">メッセージの詳細で [**キューの表示**] をクリックした後に、同じポップアップが表示されるアラート**が遅延して**います。</span><span class="sxs-lookup"><span data-stu-id="feccc-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![セキュリティ & コンプライアンスセンターでのメッセージの遅延アラートの詳細](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="feccc-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="feccc-150">See also</span></span>

<span data-ttu-id="feccc-151">メールフローダッシュボードの他の洞察の詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="feccc-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
