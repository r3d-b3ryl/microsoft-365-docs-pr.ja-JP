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
ms.openlocfilehash: 94e8a1f3b54c3738c21e94ba85ae4f1d3f953498
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150173"
---
# <a name="queues-insight-in-the-security--compliance-center"></a><span data-ttu-id="3a7c5-103">セキュリティ/コンプライアンス センターでの&の分析情報</span><span class="sxs-lookup"><span data-stu-id="3a7c5-103">Queues insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3a7c5-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="3a7c5-104">**Applies to**</span></span>
- [<span data-ttu-id="3a7c5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3a7c5-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="3a7c5-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="3a7c5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="3a7c5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3a7c5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="3a7c5-108">コネクタを使用して組織からオンプレミスまたはパートナーの電子メール サーバーにメッセージを送信できない場合、メッセージは Microsoft 365 でキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-108">When messages can't be sent from your organization to your on-premises or partner email servers using connectors, the messages are queued in Microsoft 365.</span></span> <span data-ttu-id="3a7c5-109">この状態を引き起こす一般的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-109">Common examples that cause this condition are:</span></span>

- <span data-ttu-id="3a7c5-110">コネクタが正しく構成されていません。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-110">The connector is incorrectly configured.</span></span>
- <span data-ttu-id="3a7c5-111">オンプレミス環境でネットワークまたはファイアウォールの変更が行いました。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-111">There have been networking or firewall changes in your on-premises environment.</span></span>

<span data-ttu-id="3a7c5-112">Microsoft 365 は引き続き配信を 24 時間再試行します。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-112">Microsoft 365 will continue to retry to delivery for 24 hours.</span></span> <span data-ttu-id="3a7c5-113">24 時間後、メッセージは有効期限が切れ、配信拒否レポート (NDRs またはバウンス メッセージとも呼ばれる) で送信者に返されます。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-113">After 24 hours, the messages will expire and will be returned to the senders in non-delivery reports (also known as a NDRs or bounce messages).</span></span>

<span data-ttu-id="3a7c5-114">キューに入った電子メール ボリュームが定義済みのしきい値 (既定値は 200 メッセージ) を超える場合、情報は次の場所で使用できます。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-114">If the queued email volume exceeds the pre-defined threshold (the default value is 200 messages), the information is available in the following locations:</span></span>

- <span data-ttu-id="3a7c5-115">セキュリティ **/コンプライアンス** センターの [メール](mail-flow-insights-v2.md) フロー ダッシュボード& [インサイト](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-115">The **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="3a7c5-116">詳細については、この記事の「メール フロー ダッシュボード」セクションの [「](#queues-insight-in-the-mail-flow-dashboard) キュー」の分析情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-116">For more information, see the [Queues insight in the Mail flow dashboard](#queues-insight-in-the-mail-flow-dashboard) section in this article.</span></span>

- <span data-ttu-id="3a7c5-117">アラートは、セキュリティ/**コンプライアンス** センター (アラート ダッシュボードまたは) の [[最近&](https://protection.office.com)**アラート]** \> **ダッシュボードに表示** されます <https://protection.office.com/alertsdashboard> 。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-117">An alert is displayed in **Recent alerts** the Alerts dashboard in the [Security & Compliance Center](https://protection.office.com) (**Alerts** \> **Dashboard** or <https://protection.office.com/alertsdashboard>).</span></span>

  ![セキュリティ/コンプライアンス センターのアラート ダッシュボード&最近のアラート](../../media/mfi-queued-messages-alert.png)

- <span data-ttu-id="3a7c5-119">管理者は、"メッセージ" という名前の既定のアラート ポリシーの構成に基づいて、電子 **メール通知を受信します**。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-119">Admins will receive an email notification based on the configuration of the default alert policy named **Messages have been delayed**.</span></span> <span data-ttu-id="3a7c5-120">このアラートの通知設定を構成するには、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-120">To configure the notification settings for this alert, see the next section.</span></span>

  <span data-ttu-id="3a7c5-121">アラート ポリシーの詳細については、セキュリティ/コンプライアンス センターの「アラート [&参照してください](../../compliance/alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-121">For more information about alert policies, see [Alert policies in the Security & Compliance Center](../../compliance/alert-policies.md).</span></span>

## <a name="customize-queue-alerts"></a><span data-ttu-id="3a7c5-122">キュー通知をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="3a7c5-122">Customize queue alerts</span></span>

1. <span data-ttu-id="3a7c5-123">セキュリティ センター [コンプライアンス センターで&](https://protection.office.com)アラート **ポリシー** に移動 \> **するか、開** きます <https://protection.office.com/alertpolicies> 。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-123">In the [Security & Compliance Center](https://protection.office.com), go to **Alerts** \> **Alert policies** or open <https://protection.office.com/alertpolicies>.</span></span>

2. <span data-ttu-id="3a7c5-124">[アラート **ポリシー] ページで** 、[メッセージ] という名前のポリシーを見つけて **選択します**。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-124">On the **Alert policies** page, find and select the policy named **Messages have been delayed**.</span></span>

3. <span data-ttu-id="3a7c5-125">メッセージが **遅延して表示される** フライアウトで、通知をオンまたはオフにし、通知設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-125">In the **Message have been delayed** flyout that opens, you can turn the alert on or off and configure the notification settings.</span></span>

   ![メッセージは、セキュリティ/コンプライアンス センターの警告ポリシー&遅れています](../../media/mfi-queued-messages-alert-policy.png)

   - <span data-ttu-id="3a7c5-127">**状態**: アラートのオンとオフを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-127">**Status**: You can toggle the alert on or off.</span></span>

   - <span data-ttu-id="3a7c5-128">**電子メールの受信者と** **1 日の通知の制限**: [編集 **]** をクリックして、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-128">**Email recipients** and **Daily notification limit**: Click **Edit** to configure the following settings:</span></span>

4. <span data-ttu-id="3a7c5-129">通知設定を構成するには、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-129">To configure the notification settings, click **Edit**.</span></span> <span data-ttu-id="3a7c5-130">表示される **ポリシーの** 編集フライアウトで、次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-130">In the **Edit policy** flyout that appears, configure the following settings:</span></span>

   - <span data-ttu-id="3a7c5-131">**電子メール通知の** 送信 : 既定値はオンです。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-131">**Send email notifications**: The default value is on.</span></span>
   - <span data-ttu-id="3a7c5-132">**メール受信者**: 既定値は **TenantAdmins です**。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-132">**Email recipients**: The default value is **TenantAdmins**.</span></span>
   - <span data-ttu-id="3a7c5-133">**1 日の通知の** 制限 : 既定値は **[制限なし] です**。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-133">**Daily notification limit**: The default value is **No limit**.</span></span>
   - <span data-ttu-id="3a7c5-134">**しきい** 値 : 既定値は 200 です。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-134">**Threshold**: The default value is 200.</span></span>

   ![メッセージの通知設定は、セキュリティ/コンプライアンス センターの警告ポリシーの&されています。](../../media/mfi-queued-messages-alert-policy-notification-settings.png)

5. <span data-ttu-id="3a7c5-136">完了したら、[保存して閉じる] **を** クリック **します**。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-136">When you're finished, click **Save** and **Close**.</span></span>

## <a name="queues-insight-in-the-mail-flow-dashboard"></a><span data-ttu-id="3a7c5-137">メール フロー ダッシュボードでのキューの分析情報</span><span class="sxs-lookup"><span data-stu-id="3a7c5-137">Queues insight in the Mail flow dashboard</span></span>

<span data-ttu-id="3a7c5-138">キューに入っているメッセージ ボリュームがしきい値を超えていてアラートを生成していなくても、メール フローダッシュボードでキューの分析[](mail-flow-insights-v2.md)情報を使用して、1 時間以上キューに入っているメッセージを確認し、キューに入っているメッセージの数が多くなりすぎる前にアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-138">Even if the queued message volume hasn't exceeded the threshold and generated an alert, you can still use the **Queues** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) to see messages that have been queued for more than one hour, and take action before the number of queued messages becomes too large.</span></span>

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボード&ウィジェット](../../media/mfi-queues-widget.png)

<span data-ttu-id="3a7c5-140">ウィジェット上のメッセージ数をクリックすると、キューに入ったメッセージ **のフライ** アウトが次の情報と一緒に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-140">If you click the number of messages on the widget, a **Messages queued** flyout appears with the following information:</span></span>

- <span data-ttu-id="3a7c5-141">**キューに入ったメッセージの数**</span><span class="sxs-lookup"><span data-stu-id="3a7c5-141">**Number of queued messages**</span></span>
- <span data-ttu-id="3a7c5-142">**コネクタ名**: コネクタ名をクリックして、Exchange 管理センター (EAC) でコネクタを管理します。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-142">**Connector name**: Click on the connector name to manage the connector in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="3a7c5-143">**キューの開始時刻**</span><span class="sxs-lookup"><span data-stu-id="3a7c5-143">**Queue started time**</span></span>
- <span data-ttu-id="3a7c5-144">**最も古いメッセージの有効期限が切れています**</span><span class="sxs-lookup"><span data-stu-id="3a7c5-144">**Oldest messages expired**</span></span>
- <span data-ttu-id="3a7c5-145">**送信先サーバー**</span><span class="sxs-lookup"><span data-stu-id="3a7c5-145">**Destination server**</span></span>
- <span data-ttu-id="3a7c5-146">**最後の IP アドレス**</span><span class="sxs-lookup"><span data-stu-id="3a7c5-146">**Last IP address**</span></span>
- <span data-ttu-id="3a7c5-147">**最後のエラー**</span><span class="sxs-lookup"><span data-stu-id="3a7c5-147">**Last error**</span></span>
- <span data-ttu-id="3a7c5-148">**解決方法**: 一般的な問題と解決策を利用できます。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-148">**How to fix**: Common issues and solutions are available.</span></span> <span data-ttu-id="3a7c5-149">If is a **Fix it now** link is available, click it to fix the problem.</span><span class="sxs-lookup"><span data-stu-id="3a7c5-149">If is a **Fix it now** link is available, click it to fix the problem.</span></span> <span data-ttu-id="3a7c5-150">それ以外の場合は、エラーと考えられる解決策の詳細については、利用可能なリンクをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-150">Otherwise, click on any available links for more information about the error and possible solutions.</span></span>

![メール フロー ダッシュボードでキューの分析情報をクリックした後の詳細](../../media/mfi-queues-details.png)

<span data-ttu-id="3a7c5-152">メッセージが遅延アラートの詳細で [キューの表示] をクリックすると、同 **じフライアウトが表示** されます。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-152">The same flyout is displayed after you click **View queue** in the details of a **Messages have been delayed** alert.</span></span>

![セキュリティ/コンプライアンス センターでメッセージの警告の&が遅れています](../../media/mfi-queued-messages-alert-details.png)

## <a name="see-also"></a><span data-ttu-id="3a7c5-154">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="3a7c5-154">See also</span></span>

<span data-ttu-id="3a7c5-155">メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。</span><span class="sxs-lookup"><span data-stu-id="3a7c5-155">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
