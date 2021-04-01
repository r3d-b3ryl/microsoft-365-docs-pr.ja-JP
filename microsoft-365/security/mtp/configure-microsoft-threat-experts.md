---
title: Microsoft 365 Defender を使用して Microsoft Threat Experts の機能を構成および管理する
description: Microsoft 365 Defender を通じて Microsoft Threats Experts にサブスクライブし、毎日のセキュリティ操作とセキュリティ管理作業で構成、管理、および使用します。
keywords: Microsoft Threat Experts, managed Threat Hunting Service, MTE, Microsoft マネージ ハンティング サービス
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-maave
author: martyav
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.topic: article
ms.openlocfilehash: e1ccd4404eb94193695239def7f26ba64e70d51d
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476579"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a><span data-ttu-id="b6ca3-104">Microsoft 365 Defender を使用して Microsoft Threat Experts の機能を構成および管理する</span><span class="sxs-lookup"><span data-stu-id="b6ca3-104">Configure and manage Microsoft Threat Experts capabilities through Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="b6ca3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="b6ca3-105">**Applies to:**</span></span>

- [<span data-ttu-id="b6ca3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b6ca3-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="b6ca3-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b6ca3-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a><span data-ttu-id="b6ca3-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="b6ca3-108">Before you begin</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6ca3-109">適用する前に、Microsoft Technical Service プロバイダーとアカウント チームと一緒に、Microsoft Threat Experts - Targeted Attack Notifications マネージ脅威ハンティング サービスの適格性要件について説明してください。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-109">Before you apply, make sure to discuss the eligibility requirements for the Microsoft Threat Experts – Targeted Attack Notifications managed threat hunting service with your Microsoft Technical Service provider and account team.</span></span>

<span data-ttu-id="b6ca3-110">標的型攻撃通知を受信するには、デバイスが登録された Microsoft 365 Defender を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-110">To receive targeted attack notifications, you'll need to have Microsoft 365 Defender deployed with devices enrolled.</span></span> <span data-ttu-id="b6ca3-111">次に、M365 ポータルから Microsoft Threat Experts - ターゲット攻撃通知のアプリケーションを送信します。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-111">Then, submit an application through the M365 portal for Microsoft Threat Experts - Targeted Attack Notifications.</span></span>

<span data-ttu-id="b6ca3-112">Microsoft Threat Experts - Experts on Demand を購読するには、アカウント チームまたは Microsoft 担当者にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-112">Contact your account team or Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span> <span data-ttu-id="b6ca3-113">オンデマンドの専門家は、関連する検出や敵対者から組織を保護する方法について、脅威の専門家と相談できます。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-113">Experts on Demand lets you consult with our threat experts on how to protect your organization from relevant detections and adversaries.</span></span>

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a><span data-ttu-id="b6ca3-114">Microsoft Threat Experts - ターゲット攻撃通知サービスに適用する</span><span class="sxs-lookup"><span data-stu-id="b6ca3-114">Apply for Microsoft Threat Experts - Targeted Attack Notifications service</span></span>

<span data-ttu-id="b6ca3-115">Microsoft Defender for Endpoint と Microsoft 365 Defender を既に持っている場合は、Microsoft 365 Defender ポータルを通じて Microsoft Threat Experts – Targeted Attack Notifications を申請できます。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-115">If you already have Microsoft Defender for Endpoint and Microsoft 365 Defender, you can apply for Microsoft Threat Experts – Targeted Attack Notifications through their Microsoft 365 Defender portal.</span></span>  <span data-ttu-id="b6ca3-116">標的型攻撃通知は、組織にとって最も重要な脅威を特定するのに役立つ特別な洞察と分析を提供し、迅速に対応できます。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-116">Targeted attack notifications grant you special insight and analysis to help identify the most critical threats to your organization, so you can respond to them quickly.</span></span>

1. <span data-ttu-id="b6ca3-117">ナビゲーション ウィンドウから、[エンドポイントの設定] > Microsoft Threat Experts > **>高度>に移動します**。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-117">From the navigation pane, go to **Settings > Endpoints > General > Advanced features > Microsoft Threat Experts - Targeted Attack Notifications**.</span></span>

2. <span data-ttu-id="b6ca3-118">**[適用]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-118">Select **Apply**.</span></span>

    ![Microsoft Threat Experts の設定のイメージ](../../media/mte/mte-collaboratewithmte.png)

3. <span data-ttu-id="b6ca3-120">Microsoft がアプリケーションについて連絡できるよう、名前とメール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-120">Enter your name and email address so that Microsoft can contact you about your application.</span></span>

    ![Microsoft Threat Experts アプリケーションのイメージ](../../media/mte/mte-apply.png)

4. <span data-ttu-id="b6ca3-122">プライバシーに [関する声明を読み](https://privacy.microsoft.com/en-us/privacystatement)、完了 **したら [送信** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-122">Read the [privacy statement](https://privacy.microsoft.com/en-us/privacystatement), then select **Submit** when you're done.</span></span> <span data-ttu-id="b6ca3-123">アプリケーションが承認されると、ウェルカム メールが届きます。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-123">You'll receive a welcome email once your application is approved.</span></span>

    ![Microsoft Threat Experts アプリケーション確認のイメージ](../../media/mte/mte-applicationconfirmation.png)

5. <span data-ttu-id="b6ca3-125">ウェルカム メールを受信すると、ターゲット攻撃通知の受信が自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-125">After you receive your welcome email, you'll automatically start receiving targeted attack notifications.</span></span>

6. <span data-ttu-id="b6ca3-126">[設定] ページの [エンドポイント] ページの [全般> **詳細>を>確認できます**。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-126">You can verify your status by visiting **Settings > Endpoints > General > Advanced features**.</span></span> <span data-ttu-id="b6ca3-127">承認されると **、Microsoft Threat Experts - ターゲット攻撃通知** トグルが表示され、[オン] に切り替 **わるようになります**。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-127">Once approved, the **Microsoft Threat Experts - Targeted Attack Notification** toggle will be visible and switched **On**.</span></span>

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a><span data-ttu-id="b6ca3-128">Microsoft Threat Experts からのターゲット攻撃通知が表示される場所</span><span class="sxs-lookup"><span data-stu-id="b6ca3-128">Where you'll see the targeted attack notifications from Microsoft Threat Experts</span></span>

<span data-ttu-id="b6ca3-129">次のメディアを使用して、Microsoft Threat Experts から標的型攻撃通知を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-129">You can receive targeted attack notification from Microsoft Threat Experts through the following mediums:</span></span>

- <span data-ttu-id="b6ca3-130">Microsoft 365 Defender ポータルの **[インシデント] ページ**</span><span class="sxs-lookup"><span data-stu-id="b6ca3-130">The Microsoft 365 Defender portal's **Incidents** page</span></span>
- <span data-ttu-id="b6ca3-131">Microsoft 365 Defender ポータルの **アラート** ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="b6ca3-131">The Microsoft 365 Defender portal's **Alerts** dashboard</span></span>
- <span data-ttu-id="b6ca3-132">OData アラート [API と](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts) REST [API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span><span class="sxs-lookup"><span data-stu-id="b6ca3-132">OData alerting [API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/get-alerts) and [REST API](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span></span>
- <span data-ttu-id="b6ca3-133">[高度な検索の DeviceAlertEvents](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) テーブル</span><span class="sxs-lookup"><span data-stu-id="b6ca3-133">[DeviceAlertEvents](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) table in Advanced hunting</span></span>
- <span data-ttu-id="b6ca3-134">電子メールを介してターゲット攻撃通知を送信する場合は、受信トレイ。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-134">Your inbox, if you choose to have targeted attack notifications sent to you via email.</span></span> <span data-ttu-id="b6ca3-135">以下の [「電子メール通知ルールを作成する」を](#create-an-email-notification-rule) 参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-135">See [Create an email notification rule](#create-an-email-notification-rule) below.</span></span>

### <a name="create-an-email-notification-rule"></a><span data-ttu-id="b6ca3-136">電子メール通知ルールの作成</span><span class="sxs-lookup"><span data-stu-id="b6ca3-136">Create an email notification rule</span></span>

<span data-ttu-id="b6ca3-137">通知受信者の電子メール通知を送信するルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-137">You can create rules to send email notifications for notification recipients.</span></span> <span data-ttu-id="b6ca3-138">詳細については、「アラート通知を  [構成して](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) 電子メール通知を作成、編集、削除、またはトラブルシューティングする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-138">For full details, see  [Configure alert notifications](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) to create, edit, delete, or troubleshoot email notification.</span></span>

## <a name="view-targeted-attack-notifications"></a><span data-ttu-id="b6ca3-139">ターゲット攻撃の通知を表示する</span><span class="sxs-lookup"><span data-stu-id="b6ca3-139">View targeted attack notifications</span></span>

<span data-ttu-id="b6ca3-140">電子メール通知を受信するようにシステムを構成した後、電子メールで Microsoft Threat Experts から標的型攻撃通知の受信を開始します。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-140">You'll start receiving targeted attack notification from Microsoft Threat Experts in your email after you have configured your system to receive email notification.</span></span>

1. <span data-ttu-id="b6ca3-141">メール内のリンクを選択して、脅威の専門家とタグ付けされたダッシュボードの対応するアラート コンテキスト **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-141">Select the link in the email to go to the corresponding alert context in the dashboard tagged with **Threat experts**.</span></span>

2. <span data-ttu-id="b6ca3-142">[アラート **] ページ** で、電子メールで受信したアラート トピックと同じアラート トピックを選択して、詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-142">From the **Alerts** page, select the same alert topic as the one you received in the email, to view further details.</span></span>

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="b6ca3-143">Microsoft Threat Experts の購読 - エキスパート オンデマンド</span><span class="sxs-lookup"><span data-stu-id="b6ca3-143">Subscribe to Microsoft Threat Experts - Experts on Demand</span></span>

<span data-ttu-id="b6ca3-144">Microsoft Defender for Endpoint のお客様が既に存在する場合は、Microsoft の担当者に問い合わせ、Microsoft Threat Experts - Experts on Demand を購読できます。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-144">If you're already a Microsoft Defender for Endpoint customer, you can contact your Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span>

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a><span data-ttu-id="b6ca3-145">組織内の疑わしいサイバーセキュリティアクティビティについて Microsoft の脅威専門家に相談する</span><span class="sxs-lookup"><span data-stu-id="b6ca3-145">Consult a Microsoft threat expert about suspicious cybersecurity activities in your organization</span></span>

<span data-ttu-id="b6ca3-146">Microsoft 365 Defender ポータル内から Microsoft Threat Experts に問い合わせできます。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-146">You can contact Microsoft Threat Experts from inside the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="b6ca3-147">専門家は、複雑な脅威や標的型攻撃の通知を理解するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-147">Experts can help you understand complex threats and targeted attack notifications.</span></span> <span data-ttu-id="b6ca3-148">アラートやインシデントに関する詳細、または侵害の処理に関するアドバイスについては、専門家と提携してください。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-148">Partner with experts for further details about alerts and incidents, or advice on handling compromise.</span></span> <span data-ttu-id="b6ca3-149">ポータル ダッシュボードで説明されている脅威インテリジェンス コンテキストに関する分析情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-149">Gain insight into the threat intelligence context described by your portal dashboard.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="b6ca3-150">組織のカスタマイズされた脅威インテリジェンス データに関連するアラートの問い合わせは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-150">Alert inquiries related to your organization's customized threat intelligence data are not currently supported.</span></span> <span data-ttu-id="b6ca3-151">詳細については、セキュリティ操作またはインシデント対応チームに問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-151">Consult with your security operations or incident response team for details.</span></span>
> - <span data-ttu-id="b6ca3-152">Microsoft 365 Defender ポータルの [セキュリティ センターのセキュリティ設定の管理] アクセス許可を持って、[脅威の専門家に相談する] フォームから問い合わせを **送信する必要** があります。 </span><span class="sxs-lookup"><span data-stu-id="b6ca3-152">You need to have the **Manage security settings in Security Center** permission in the Microsoft 365 Defender portal to submit an inquiry through the **Consult a threat expert** form.</span></span>

1. <span data-ttu-id="b6ca3-153">調査する情報 (デバイス、アラート、インシデントなど) に関連するポータル **ページに移動\*\*\*\*します**。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-153">Navigate to the portal page related to the information that you'd like to investigate: for example, **Device**, **Alert**, or **Incident**.</span></span> <span data-ttu-id="b6ca3-154">調査要求を送信する前に、問い合わせに関連するポータル ページが表示されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-154">Make sure that the portal page related to your inquiry is in view before you send an investigation request.</span></span>

2. <span data-ttu-id="b6ca3-155">トップ メニューから **[?脅威の専門家に相談してください**。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-155">From the top menu, select **? Consult a threat expert**.</span></span>

    ![メニューから Microsoft Threat Experts Experts on Demand のイメージ](../../media/mte/incidents-action-mte-highlighted.png)

    <span data-ttu-id="b6ca3-157">フライアウト画面が開きます。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-157">A flyout screen will open.</span></span>

    <span data-ttu-id="b6ca3-158">このヘッダーには、試用版サブスクリプションか、Microsoft Threat Experts - Experts on-Demand サブスクリプションの完全版が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-158">The header will indicate if you are on a trial subscription, or a full Microsoft Threat Experts - Experts on-Demand subscription.</span></span>

    ![Microsoft Threat Experts Experts on Demand 試用版サブスクリプション画面の画像](../../media/mte/mte-trial.png)

    <span data-ttu-id="b6ca3-160">[ **調査] トピック** フィールドには、要求の関連ページへのリンクが既に入力されています。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-160">The **Investigation topic** field will already be populated with the link to the relevant page for your request.</span></span>

3. <span data-ttu-id="b6ca3-161">次のフィールドで、調査を開始するのに十分なコンテキストを Microsoft Threat Experts に提供するのに十分な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-161">In the next field, provide enough information to give the Microsoft Threat Experts enough context to start the investigation.</span></span>

4. <span data-ttu-id="b6ca3-162">Microsoft Threat Experts に対応するために使用するメール アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-162">Enter the email address that you'd like to use to correspond with Microsoft Threat Experts.</span></span>

> [!NOTE]
> <span data-ttu-id="b6ca3-163">Microsoft Services Hub を通じてエキスパート オンデマンド ケースの状態を追跡する場合は、テクニカル アカウント マネージャーに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-163">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your technical account manager.</span></span>

<span data-ttu-id="b6ca3-164">Microsoft Services Hub の概要については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-164">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a><span data-ttu-id="b6ca3-165">調査のサンプル トピック</span><span class="sxs-lookup"><span data-stu-id="b6ca3-165">Sample investigation topics</span></span>

### <a name="alert-information"></a><span data-ttu-id="b6ca3-166">アラート情報</span><span class="sxs-lookup"><span data-stu-id="b6ca3-166">Alert information</span></span>

- <span data-ttu-id="b6ca3-167">新しい種類のアラートが、生きている土地のバイナリに対して表示されます。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-167">We saw a new type of alert for a living-off-the-land binary.</span></span> <span data-ttu-id="b6ca3-168">アラート ID を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-168">We can provide the alert ID.</span></span> <span data-ttu-id="b6ca3-169">このアラートの詳細と、さらに詳しく調査する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-169">Can you tell us more about this alert and how we can investigate it further?</span></span>
- <span data-ttu-id="b6ca3-170">同様の攻撃が 2 つ見られたので、どちらも悪意のある PowerShell スクリプトを実行しようとするが、異なるアラートを生成します。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-170">We've observed two similar attacks, which both try to execute malicious PowerShell scripts but generate different alerts.</span></span> <span data-ttu-id="b6ca3-171">1 つは "不審な PowerShell コマンド ライン" で、もう 1 つは "O365 によって提供される指示に基づいて悪意のあるファイルが検出されました" です。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-171">One is "Suspicious PowerShell command line" and the other is "A malicious file was detected based on indication provided by O365".</span></span> <span data-ttu-id="b6ca3-172">違いは何ですか?</span><span class="sxs-lookup"><span data-stu-id="b6ca3-172">What is the difference?</span></span>
- <span data-ttu-id="b6ca3-173">今日、知名度の高いユーザーのデバイスから失敗したログインの異常数に関する奇数の警告を受け取りました。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-173">We received an odd alert today about an abnormal number of failed logins from a high profile user’s device.</span></span> <span data-ttu-id="b6ca3-174">これらの試みについてのそれ以上の証拠は見つからん。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-174">We can't find any further evidence for these attempts.</span></span> <span data-ttu-id="b6ca3-175">Microsoft 365 Defender でこれらの試みを確認する方法</span><span class="sxs-lookup"><span data-stu-id="b6ca3-175">How can Microsoft 365 Defender see these attempts?</span></span> <span data-ttu-id="b6ca3-176">監視対象のログインの種類</span><span class="sxs-lookup"><span data-stu-id="b6ca3-176">What type of logins are being monitored?</span></span>
- <span data-ttu-id="b6ca3-177">「システム ユーティリティによる疑わしい動作が観察されました」というアラートに関するコンテキストや分析情報を追加できますか?</span><span class="sxs-lookup"><span data-stu-id="b6ca3-177">Can you give more context or insight about the alert, "Suspicious behavior by a system utility was observed"?</span></span>
- <span data-ttu-id="b6ca3-178">"転送/リダイレクト ルールの作成" というタイトルのアラートが表示されました。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-178">I observed an alert titled "Creation of forwarding/redirect rule".</span></span> <span data-ttu-id="b6ca3-179">アクティビティは良性だと思います。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-179">I believe the activity is benign.</span></span> <span data-ttu-id="b6ca3-180">通知を受け取った理由を教えてください。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-180">Can you tell me why I received an alert?</span></span>

### <a name="possible-machine-compromise"></a><span data-ttu-id="b6ca3-181">コンピューターの侵害の可能性</span><span class="sxs-lookup"><span data-stu-id="b6ca3-181">Possible machine compromise</span></span>

- <span data-ttu-id="b6ca3-182">組織内の多くのデバイスで「不明なプロセスが観察された」というメッセージや警告が表示される理由を説明できますか?</span><span class="sxs-lookup"><span data-stu-id="b6ca3-182">Can you help explain why we see a message or alert for "Unknown process observed" on many devices in our organization?</span></span> <span data-ttu-id="b6ca3-183">このメッセージまたはアラートが悪意のあるアクティビティに関連するかどうかを明確にするための任意の入力に感謝します。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-183">We appreciate any input to clarify whether this message or alert is related to malicious activity.</span></span>
- <span data-ttu-id="b6ca3-184">次のシステムで、先週から発生した可能性がある侵害の検証に役立ちますか?</span><span class="sxs-lookup"><span data-stu-id="b6ca3-184">Can you help validate a possible compromise on the following system, dating from last week?</span></span> <span data-ttu-id="b6ca3-185">これは、6 か月前に同じシステムで以前のマルウェア検出と同様に動作します。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-185">It's behaving similarly as a previous malware detection on the same system six months ago.</span></span>

### <a name="threat-intelligence-details"></a><span data-ttu-id="b6ca3-186">脅威インテリジェンスの詳細</span><span class="sxs-lookup"><span data-stu-id="b6ca3-186">Threat intelligence details</span></span>

- <span data-ttu-id="b6ca3-187">悪意のある Word 文書をユーザーに配信したフィッシングメールが検出されました。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-187">We detected a phishing email that delivered a malicious Word document to a user.</span></span> <span data-ttu-id="b6ca3-188">このドキュメントでは、一連の疑わしいイベントが発生し、特定のマルウェア ファミリに対して複数のアラートが発生しました。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-188">The document caused a series of suspicious events, which triggered multiple alerts for a particular malware family.</span></span> <span data-ttu-id="b6ca3-189">このマルウェアに関する情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="b6ca3-189">Do you have any information on this malware?</span></span> <span data-ttu-id="b6ca3-190">はいの場合、リンクを送信できますか?</span><span class="sxs-lookup"><span data-stu-id="b6ca3-190">If yes, can you send us a link?</span></span>
- <span data-ttu-id="b6ca3-191">最近、業界をターゲットにしている脅威に関するブログ投稿を見ました。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-191">We recently saw a blog post about a threat that is targeting our industry.</span></span> <span data-ttu-id="b6ca3-192">この脅威アクターに対して Microsoft 365 Defender が提供する保護を理解するのに役立ちますか?</span><span class="sxs-lookup"><span data-stu-id="b6ca3-192">Can you help us understand what protection Microsoft 365 Defender provides against this threat actor?</span></span>
- <span data-ttu-id="b6ca3-193">最近、組織に対して行われたフィッシング キャンペーンを確認しました。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-193">We recently observed a phishing campaign conducted against our organization.</span></span> <span data-ttu-id="b6ca3-194">これは、特に当社または垂直に対象とされたのか教えてください。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-194">Can you tell us if this was targeted specifically to our company or vertical?</span></span>

### <a name="microsoft-threat-experts-alert-communications"></a><span data-ttu-id="b6ca3-195">Microsoft Threat Experts のアラート通信</span><span class="sxs-lookup"><span data-stu-id="b6ca3-195">Microsoft Threat Experts’ alert communications</span></span>

- <span data-ttu-id="b6ca3-196">インシデント対応チームは、対象となる攻撃通知に対処するのに役立ちますか?</span><span class="sxs-lookup"><span data-stu-id="b6ca3-196">Can your incident response team help us address the targeted attack notification that we got?</span></span>
- <span data-ttu-id="b6ca3-197">Microsoft Threat Experts からこの標的型攻撃の通知を受け取った。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-197">We received this targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="b6ca3-198">独自のインシデント対応チームは持ち合わせください。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-198">We don’t have our own incident response team.</span></span> <span data-ttu-id="b6ca3-199">ここで何を行い、インシデントを含めるのか。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-199">What can we do now, and how can we contain the incident?</span></span>
- <span data-ttu-id="b6ca3-200">Microsoft Threat Experts から標的型攻撃の通知を受け取った。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-200">We received a targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="b6ca3-201">インシデント対応チームに渡すデータを提供できますか?</span><span class="sxs-lookup"><span data-stu-id="b6ca3-201">What data can you provide to us that we can pass on to our incident response team?</span></span>

> [!NOTE]
> <span data-ttu-id="b6ca3-202">Microsoft Threat Experts は、インシデント対応サービスではなく、管理された脅威検出サービスです。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-202">Microsoft Threat Experts is a managed threat hunting service and not an incident response service.</span></span> <span data-ttu-id="b6ca3-203">ただし、専門家は必要に応じて、調査を Microsoft サイバーセキュリティ ソリューション グループ (CSG) の検出および応答チーム (DART) サービスにシームレスに移行できます。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-203">However, the experts can seamlessly transition the investigation to Microsoft Cybersecurity Solutions Group (CSG)'s Detection and Response Team (DART) services, when necessary.</span></span> <span data-ttu-id="b6ca3-204">また、インシデント対応チームと関わり、インシデント対応が必要な問題に対処できます。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-204">You can also opt to engage with your own incident response team to address issues that requires an incident response.</span></span>

## <a name="scenario"></a><span data-ttu-id="b6ca3-205">シナリオ</span><span class="sxs-lookup"><span data-stu-id="b6ca3-205">Scenario</span></span>

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a><span data-ttu-id="b6ca3-206">管理された狩猟に関する問い合わせに関する進行状況レポートを受け取る</span><span class="sxs-lookup"><span data-stu-id="b6ca3-206">Receive a progress report about your managed hunting inquiry</span></span>

<span data-ttu-id="b6ca3-207">Microsoft Threat Experts からの応答は、お問い合わせに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-207">The response from Microsoft Threat Experts will vary according to your inquiry.</span></span> <span data-ttu-id="b6ca3-208">通常、次のいずれかの応答を受け取る必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-208">You'll generally receive one of the following responses:</span></span>

- <span data-ttu-id="b6ca3-209">調査を続行するには、さらに詳しい情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-209">More information is needed to continue with the investigation</span></span>
- <span data-ttu-id="b6ca3-210">技術的なコンテキストを決定するには、ファイルまたは複数のファイル サンプルが必要です</span><span class="sxs-lookup"><span data-stu-id="b6ca3-210">A file or several file samples are needed to determine the technical context</span></span>
- <span data-ttu-id="b6ca3-211">調査にはより多くの時間が必要</span><span class="sxs-lookup"><span data-stu-id="b6ca3-211">Investigation requires more time</span></span>
- <span data-ttu-id="b6ca3-212">最初の情報は、調査を終了するのに十分でした</span><span class="sxs-lookup"><span data-stu-id="b6ca3-212">Initial information was enough to conclude the investigation</span></span>

<span data-ttu-id="b6ca3-213">専門家が詳細な情報やファイル サンプルを要求する場合は、調査の動きを維持するために迅速に対応することが重要です。</span><span class="sxs-lookup"><span data-stu-id="b6ca3-213">If an expert requests more information or file samples, it's crucial to respond quickly to keep the investigation moving.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6ca3-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="b6ca3-214">See also</span></span>

- [<span data-ttu-id="b6ca3-215">Microsoft Threat Experts の概要</span><span class="sxs-lookup"><span data-stu-id="b6ca3-215">Microsoft Threat Experts overview</span></span>](microsoft-threat-experts.md)
