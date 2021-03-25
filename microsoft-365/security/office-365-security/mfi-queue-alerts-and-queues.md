---
title: メール フロー ダッシュボードのキューの分析情報
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37640c80-ce6f-47e2-afd1-bc1d3c50e637
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードでキュー ウィジェットを使用して、送信コネクタを超えるオンプレミスまたはパートナー組織への失敗したメール フローを監視する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 14cadd0e8611fbbc65c3bdc9849beebf3a3eb34d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206945"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="9557c-103">コンプライアンス センターのセキュリティ &キューの分析情報</span><span class="sxs-lookup"><span data-stu-id="9557c-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9557c-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="9557c-104">**Applies to**</span></span>
- [<span data-ttu-id="9557c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="9557c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9557c-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="9557c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="9557c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9557c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="9557c-108">コネクタを使用して組織からオンプレミスまたはパートナーの電子メール サーバーにメッセージを送信できない場合、メッセージは Microsoft 365 でキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="9557c-108">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="9557c-109">この条件の原因となる一般的な例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="9557c-109">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="9557c-110">コネクタが正しく構成されていません。</span><span class="sxs-lookup"><span data-stu-id="9557c-110">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="9557c-111">オンプレミス環境でネットワークまたはファイアウォールの変更が行いました。</span><span class="sxs-lookup"><span data-stu-id="9557c-111">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="9557c-112">Microsoft 365 は引き続き 24 時間配信を再試行します。</span><span class="sxs-lookup"><span data-stu-id="9557c-112">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="9557c-113">24 時間が経過すると、メッセージは有効期限が切れ、配信不可レポート (NDRs またはバウンス メッセージとも呼ばれる) の送信者に返されます。</span><span class="sxs-lookup"><span data-stu-id="9557c-113">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="9557c-114">キューに入った電子メール ボリュームが定義済みのしきい値 (既定値は 200 メッセージ) を超えた場合、情報は次の場所で使用できます。</span><span class="sxs-lookup"><span data-stu-id="9557c-114">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="9557c-115">セキュリティ **コンプライアンス センター** の [[メール](mail-flow-insights-v2.md) フロー] ダッシュボードの [ [キュー&分析情報](https://protection.office.com)です。</span><span class="sxs-lookup"><span data-stu-id="9557c-115">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="9557c-116">詳細については、この記事の [「メール フロー ダッシュボード」セクションの「Queues insight」](#queues-insight-in-the-mail-flow-dashboard) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9557c-116">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="9557c-117">[最近のアラート]**には**、[セキュリティ] コンプライアンス センター ([アラート ダッシュボード] または ) の [[&]](https://protection.office.com)ダッシュボードにアラート \> **が表示** されます <https://protection.office.com/alertsdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="9557c-117">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![セキュリティ コンプライアンス センターの [アラート] ダッシュボードの&アラート](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="9557c-119">管理者は、[メッセージ] という名前の既定のアラート ポリシーの構成に基づいて電子メール通知 **を受信します**。</span><span class="sxs-lookup"><span data-stu-id="9557c-119">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="9557c-120">このアラートの通知設定を構成するには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9557c-120">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="9557c-121">アラート ポリシーの詳細については、「Security & コンプライアンス センター」 [を参照してください](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9557c-121">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="9557c-122">キュー通知のカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="9557c-122">Customize queue alerts</span></span>

1. <span data-ttu-id="9557c-123">セキュリティ コンプライアンス [センターで&アラート](https://protection.office.com)ポリシーに移動するか \> **、** 開きます <https://protection.office.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="9557c-123">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="9557c-124">[アラート **ポリシー] ページで** 、[メッセージが遅延している] という名前のポリシー **を見つけて選択します**。</span><span class="sxs-lookup"><span data-stu-id="9557c-124">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="9557c-125">[メッセージ **が遅延された] フライ** アウトが開いたら、通知をオンまたはオフにし、通知設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="9557c-125">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![メッセージの遅延アラート ポリシーの詳細は、コンプライアンス センター&詳細です](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="9557c-127">**状態**: アラートをオンまたはオフに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="9557c-127">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="9557c-128">**メール受信者と日\*\*\*\*次通知の制限**: [**編集**] をクリックして、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="9557c-128">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="9557c-129">通知設定を構成するには、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9557c-129">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="9557c-130">表示される **[ポリシーの編集]** フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="9557c-130">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="9557c-131">**電子メール通知の送信**: 既定値はオンです。</span><span class="sxs-lookup"><span data-stu-id="9557c-131">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="9557c-132">**メール受信者**: 既定値は **TenantAdmins です**。</span><span class="sxs-lookup"><span data-stu-id="9557c-132">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="9557c-133">**1 日の通知の** 制限 : 既定値は [制限 **なし] です**。</span><span class="sxs-lookup"><span data-stu-id="9557c-133">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="9557c-134">**しきい** 値 : 既定値は 200 です。</span><span class="sxs-lookup"><span data-stu-id="9557c-134">**Threshold**: The default value is 200.</span></span>

   ![メッセージの通知設定が遅延アラート ポリシーの詳細、セキュリティ &コンプライアンス センター](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="9557c-136">完了したら、[保存して閉じる]を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="9557c-136">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="9557c-137">メール フロー ダッシュボードのキューの分析情報</span><span class="sxs-lookup"><span data-stu-id="9557c-137">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="9557c-138">キューに入っているメッセージ ボリュームがしきい値を超えてアラートを生成した場合でも、メール フロー ダッシュボードの **Queues** [](mail-flow-insights-v2.md)インサイトを使用して、1 時間以上キューに入っているメッセージを確認し、キューに入っているメッセージの数が大きすぎる前にアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="9557c-138">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![セキュリティ センターコンプライアンス センターのメール フロー ダッシュボード&キュー](../../media/mfi-queues-widget.png)

<span data-ttu-id="9557c-140">ウィジェット上のメッセージ数をクリックすると **、キューに** 入ったメッセージ のフライアウトが次の情報で表示されます。</span><span class="sxs-lookup"><span data-stu-id="9557c-140">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="9557c-141">**キューに入ったメッセージの数**</span><span class="sxs-lookup"><span data-stu-id="9557c-141">**Number of queued messages**</span></span>
- <span data-ttu-id="9557c-142">**コネクタ名**: コネクタ名をクリックして、Exchange 管理センター (EAC) でコネクタを管理します。</span><span class="sxs-lookup"><span data-stu-id="9557c-142">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="9557c-143">**キューの開始時刻**</span><span class="sxs-lookup"><span data-stu-id="9557c-143">**Queue started time**</span></span>
- <span data-ttu-id="9557c-144">**最も古いメッセージの有効期限が切れています**</span><span class="sxs-lookup"><span data-stu-id="9557c-144">**Oldest messages expired**</span></span>
- <span data-ttu-id="9557c-145">**宛先サーバー**</span><span class="sxs-lookup"><span data-stu-id="9557c-145">**Destination server**</span></span>
- <span data-ttu-id="9557c-146">**最後の IP アドレス**</span><span class="sxs-lookup"><span data-stu-id="9557c-146">**Last IP address**</span></span>
- <span data-ttu-id="9557c-147">**最後のエラー**</span><span class="sxs-lookup"><span data-stu-id="9557c-147">**Last error**</span></span>
- <span data-ttu-id="9557c-148">**修正方法**: 一般的な問題とソリューションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="9557c-148">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="9557c-149">[今すぐ **修正] リンクが** 利用可能な場合は、それをクリックして問題を解決します。</span><span class="sxs-lookup"><span data-stu-id="9557c-149">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="9557c-150">それ以外の場合は、エラーと考えられる解決策の詳細については、利用可能なリンクをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="9557c-150">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![メール フロー ダッシュボードの [キュー] インサイトをクリックした後の詳細](../../media/mfi-queues-details.png)

<span data-ttu-id="9557c-152">[メッセージの遅延通知] の詳細で [キューの表示] をクリックすると、同じ **フライアウトが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="9557c-152">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![セキュリティ コンプライアンス センターでメッセージが遅延通知&されている](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="9557c-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="9557c-154">See also</span></span>

<span data-ttu-id="9557c-155">メール フロー ダッシュボードの他の分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="9557c-155">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
