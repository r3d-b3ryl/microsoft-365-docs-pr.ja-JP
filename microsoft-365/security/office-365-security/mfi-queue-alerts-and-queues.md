---
title: メール フロー ダッシュボードのキューインインサイト
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードでキュー ウィジェットを使用して、社内組織またはパートナー組織に対する送信コネクタ経由のメール フローが正常に実行されていないかどうかを監視する方法を学習できます。
ms.openlocfilehash: 79523533306e847988fa0d4e2dd70eca22f7c76c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826907"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="fd422-103">コンプライアンス センターのセキュリティ&分析情報</span><span class="sxs-lookup"><span data-stu-id="fd422-103">Queues insight in the Security & Compliance Center</span></span>

<span data-ttu-id="fd422-104">コネクタを使用して、組織からオンプレミスまたはパートナーのメール サーバーにメッセージを送信しなけなけなけない場合、メッセージは Microsoft 365 でキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="fd422-104">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="fd422-105">この状態の原因となされる一般的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fd422-105">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="fd422-106">コネクタが正しく構成されていません。</span><span class="sxs-lookup"><span data-stu-id="fd422-106">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="fd422-107">オンプレミス環境にネットワークやファイアウォールの変更がある。</span><span class="sxs-lookup"><span data-stu-id="fd422-107">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="fd422-108">Microsoft 365 は、24 時間おりに引き続き配信を試行します。</span><span class="sxs-lookup"><span data-stu-id="fd422-108">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="fd422-109">24 時間後、メッセージは期限切れになってから配信不能レポート (NDR またはバウンス メッセージとも呼ばれる) で送信者に返されます。</span><span class="sxs-lookup"><span data-stu-id="fd422-109">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="fd422-110">キュー内のメール ボリュームが事前に定義されたしきい値 (既定値は 200 メッセージ) を超えた場合、情報は次の場所で入手できます。</span><span class="sxs-lookup"><span data-stu-id="fd422-110">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="fd422-111">コンプライアンス **センター** のメール フロー ダッシュボード [のキュー](mail-flow-insights-v2.md) &のインサイトです。</span><span class="sxs-lookup"><span data-stu-id="fd422-111">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center.</span></span> <span data-ttu-id="fd422-112">詳細については、このトピック [のメール フロー ダッシュボード セクションのキューのインサイト](#queues-insight-in-the-mail-flow-dashboard) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd422-112">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this topic.</span></span>
  
- <span data-ttu-id="fd422-113">アラートは、セキュリティ/ **コンプライアンス センター (** アラート ダッシュボードまたは& [) の [最近のアラート](https://protection.office.com) ]**ダッシュボード** \> **に表示** されます <https://protection.office.com/alertsdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="fd422-113">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![セキュリティ/コンプライアンス センターのアラート ダッシュボードの最近の&通知](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="fd422-115">管理者は、Messages という名前の既定のアラート ポリシーの構成に基づいて **メール通知を受信します**。</span><span class="sxs-lookup"><span data-stu-id="fd422-115">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="fd422-116">このアラートの通知設定を構成するには、次のセクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fd422-116">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="fd422-117">アラート ポリシーの詳細については、セキュリティ センター [とコンプライアンス センターのアラート ポリシー&を参照してください](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="fd422-117">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="fd422-118">キュー通知をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="fd422-118">Customize queue alerts</span></span>

1. <span data-ttu-id="fd422-119">セキュリティ コンプライアンス センター [で&、[アラート](https://protection.office.com)] アラート **ポリシーに** \> **移動するか、開** きます <https://protection.office.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="fd422-119">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="fd422-120">[アラート **ポリシー] ページ** で、メッセージという名前のポリシー **が遅延したポリシーを探して選択します**。</span><span class="sxs-lookup"><span data-stu-id="fd422-120">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="fd422-121">表示される **遅延ポップアップが** メッセージに登録されたら、アラートをオンまたはオフにしたり、通知設定を構成したりできます。</span><span class="sxs-lookup"><span data-stu-id="fd422-121">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![警告ポリシーの延期に関する警告ポリシーに関する &詳細](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="fd422-123">**Status**: アラートをオンまたはオフに切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="fd422-123">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="fd422-124">**メールの受信者** と **日次通知制限**: [編集] **をクリック** して、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="fd422-124">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="fd422-125">通知設定を構成するには、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="fd422-125">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="fd422-126">表示される **ポリシーの** 編集ポップアップで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="fd422-126">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="fd422-127">**電子メール通知**を送信: 既定値はオンになっています。</span><span class="sxs-lookup"><span data-stu-id="fd422-127">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="fd422-128">**Email recipients**: The default value is **TenantAdmins**.</span><span class="sxs-lookup"><span data-stu-id="fd422-128">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="fd422-129">**1 日の通知の制限**: 既定値は **No です**。</span><span class="sxs-lookup"><span data-stu-id="fd422-129">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="fd422-130">**し**きい値: 既定値は 200 です。</span><span class="sxs-lookup"><span data-stu-id="fd422-130">**Threshold**: The default value is 200.</span></span>

   ![メッセージの通知設定によってアラート ポリシーが遅延されたため、セキュリティ/コンプライアンス センターの&詳細情報](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="fd422-132">完了したら、[保存して閉じる] **を** クリック **します**。</span><span class="sxs-lookup"><span data-stu-id="fd422-132">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="fd422-133">メール フロー ダッシュボードのキューインインサイト</span><span class="sxs-lookup"><span data-stu-id="fd422-133">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="fd422-134">キューに入れられておりのメッセージ量がしきい値を超えておらず、警告を生成した場合でも引き続き、[[メール フロー](mail-flow-insights-v2.md) ] ダッシュボードの**キュー**から受信したメッセージを確認して、キューに入れられていないメッセージ数が多くなりすぎる前にアクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="fd422-134">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![セキュリティ コンプライアンス センターのメール フロー ダッシュボードのキュー&のキュー](../../media/mfi-queues-widget.png)

<span data-ttu-id="fd422-136">ウィジェット上のメッセージ数をクリックすると、 **キューに入れて** 表示されたメッセージ ポップアップが次の情報と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd422-136">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="fd422-137">**キューに入れ済みメッセージの数**</span><span class="sxs-lookup"><span data-stu-id="fd422-137">**Number of queued messages**</span></span>
- <span data-ttu-id="fd422-138">**コネクタ名**: Exchange 管理センター (EAC) でコネクタを管理するコネクタ名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd422-138">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="fd422-139">**キューの開始時刻**</span><span class="sxs-lookup"><span data-stu-id="fd422-139">**Queue started time**</span></span>
- <span data-ttu-id="fd422-140">**最も古いメッセージの有効期限が切れた**</span><span class="sxs-lookup"><span data-stu-id="fd422-140">**Oldest messages expired**</span></span>
- <span data-ttu-id="fd422-141">**送信先サーバー**</span><span class="sxs-lookup"><span data-stu-id="fd422-141">**Destination server**</span></span>
- <span data-ttu-id="fd422-142">**最後の IP アドレス**</span><span class="sxs-lookup"><span data-stu-id="fd422-142">**Last IP address**</span></span>
- <span data-ttu-id="fd422-143">**[最後のエラー]**</span><span class="sxs-lookup"><span data-stu-id="fd422-143">**Last error**</span></span>
- <span data-ttu-id="fd422-144">**方法の修正 :** 一般的な問題と解決策を利用できます。</span><span class="sxs-lookup"><span data-stu-id="fd422-144">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="fd422-145">If is a **Fix it now** link is available, click it to fix the problem.</span><span class="sxs-lookup"><span data-stu-id="fd422-145">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="fd422-146">それ以外の場合は、使用可能なリンクをクリックして、エラーと考えられる解決方法の詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="fd422-146">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![[メール フロー] ダッシュボードでキューのインサイトをクリックした後の詳細](../../media/mfi-queues-details.png)

<span data-ttu-id="fd422-148">メッセージの詳細で [表示] **をクリックすると** 、同じポ **ップアップが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="fd422-148">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![セキュリティ/コンプライアンス センターのメッセージのアラートの&された](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="fd422-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="fd422-150">See also</span></span>

<span data-ttu-id="fd422-151">メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="fd422-151">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
