---
title: Microsoft 脅威エキスパートの機能を構成および管理する
ms.reviewer: ''
description: Microsoft Threats Experts に登録して、毎日のセキュリティ操作とセキュリティ管理作業で構成、管理、および使用します。
keywords: Microsoft 脅威エキスパート、管理された脅威ハンティング サービス、MTE、Microsoft マネージ ハンティング サービス
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 226fc389aab24dda2425a17f5fb8d49da93e35d8
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770663"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities"></a><span data-ttu-id="847b7-104">Microsoft 脅威エキスパートの機能を構成および管理する</span><span class="sxs-lookup"><span data-stu-id="847b7-104">Configure and manage Microsoft Threat Experts capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="847b7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="847b7-105">**Applies to:**</span></span>
- [<span data-ttu-id="847b7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="847b7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="847b7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="847b7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="847b7-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="847b7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="847b7-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="847b7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="before-you-begin"></a><span data-ttu-id="847b7-110">はじめに</span><span class="sxs-lookup"><span data-stu-id="847b7-110">Before you begin</span></span> 
> [!NOTE]
> <span data-ttu-id="847b7-111">Microsoft 脅威エキスパート - ターゲット攻撃通知管理脅威検出サービスに適用する前に、Microsoft Technical Service プロバイダーおよびアカウント チームと適格性要件について話し合います。</span><span class="sxs-lookup"><span data-stu-id="847b7-111">Discuss the eligibility requirements with your Microsoft Technical Service provider and account team before you apply to Microsoft Threat Experts - Targeted Attack Notification managed threat hunting service.</span></span>

<span data-ttu-id="847b7-112">ラボのセットアップではなく、デバイスが登録された環境に Defender for Endpoint が展開されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="847b7-112">Ensure that you have Defender for Endpoint deployed in your environment with devices enrolled, and not just on a laboratory set-up.</span></span>

<span data-ttu-id="847b7-113">Defender for Endpoint のお客様の場合は **、Microsoft 脅威エキスパート -** ターゲット攻撃通知を申請して、最も重大な脅威を特定するのに役立つ特別な分析情報と分析を取得し、迅速に対応する必要があります。</span><span class="sxs-lookup"><span data-stu-id="847b7-113">If you're a Defender for Endpoint customer, you need to apply for **Microsoft Threat Experts - Targeted Attack Notifications** to get special insights and analysis to help identify the most critical threats, so you can respond to them quickly.</span></span> <span data-ttu-id="847b7-114">アカウント チームまたは Microsoft 担当者に問 **い合わせ、Microsoft 脅威エキスパート - Experts on Demand** を購読し、関連する検出および敵対者に関する脅威の専門家と相談してください。</span><span class="sxs-lookup"><span data-stu-id="847b7-114">Contact your account team or Microsoft representative to subscribe to **Microsoft Threat Experts - Experts on Demand** to consult with our threat experts on relevant detections and adversaries.</span></span>

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a><span data-ttu-id="847b7-115">[ターゲット攻撃通知Microsoft 脅威エキスパートを適用する]</span><span class="sxs-lookup"><span data-stu-id="847b7-115">Apply for Microsoft Threat Experts - Targeted Attack Notifications service</span></span> 
<span data-ttu-id="847b7-116">Defender for Endpoint のお客様が既に存在する場合は、アプリケーションを使用してMicrosoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="847b7-116">If you're already a Defender for Endpoint customer, you can apply through the Microsoft Defender Security Center.</span></span> 

1. <span data-ttu-id="847b7-117">ナビゲーション ウィンドウから、[全般] 設定 > [ > - ターゲット攻撃通知> Microsoft 脅威エキスパート **] に移動します**。</span><span class="sxs-lookup"><span data-stu-id="847b7-117">From the navigation pane, go to **Settings > General > Advanced features > Microsoft Threat Experts - Targeted Attack Notifications**.</span></span>

2. <span data-ttu-id="847b7-118">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="847b7-118">Click **Apply**.</span></span>

    ![ユーザー設定Microsoft 脅威エキスパートイメージ](images/mte-collaboratewithmte.png)

3. <span data-ttu-id="847b7-120">自分の名前とメール アドレスを入力して、Microsoft がアプリケーションに戻ってきます。</span><span class="sxs-lookup"><span data-stu-id="847b7-120">Enter your name and email address so that Microsoft can get back to you on your application.</span></span>

    ![アプリケーションのMicrosoft 脅威エキスパート画像](images/mte-apply.png)

4. <span data-ttu-id="847b7-122">プライバシーに [関する声明を読み](https://privacy.microsoft.com/en-us/privacystatement)、完了 **したら [送信** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="847b7-122">Read the [privacy statement](https://privacy.microsoft.com/en-us/privacystatement), then click **Submit** when you're done.</span></span> <span data-ttu-id="847b7-123">アプリケーションが承認されると、ウェルカム メールが届きます。</span><span class="sxs-lookup"><span data-stu-id="847b7-123">You will receive a welcome email once your application is approved.</span></span>

    ![アプリケーションのMicrosoft 脅威エキスパートのイメージ](images/mte-applicationconfirmation.png)

<span data-ttu-id="847b7-125">受け入れられると、ウェルカム メールが届き、[ **適用** ] ボタンが "オン" のトグルに変更されます。</span><span class="sxs-lookup"><span data-stu-id="847b7-125">When accepted, you will receive a welcome email and you will see the **Apply** button change to a toggle that is “on”.</span></span> <span data-ttu-id="847b7-126">ターゲット攻撃通知サービスから自分を取り出す場合は、トグルをスライド "off" にし、ページの下部にある [設定の保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="847b7-126">In case you want to take yourself out of the Targeted Attack Notifications service, slide the toggle “off” and click **Save preferences** at the bottom of the page.</span></span> 

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a><span data-ttu-id="847b7-127">ユーザーからのターゲット攻撃通知が表示Microsoft 脅威エキスパート</span><span class="sxs-lookup"><span data-stu-id="847b7-127">Where you'll see the targeted attack notifications from Microsoft Threat Experts</span></span> 
<span data-ttu-id="847b7-128">Microsoft 脅威エキスパートから、以下の媒体を通じて、標的型攻撃通知を受信できます。</span><span class="sxs-lookup"><span data-stu-id="847b7-128">You can receive targeted attack notification from Microsoft Threat Experts through the following medium:</span></span>  
- <span data-ttu-id="847b7-129">Defender for Endpoint portal's **Incidents page**</span><span class="sxs-lookup"><span data-stu-id="847b7-129">The Defender for Endpoint portal's **Incidents** page</span></span> 
- <span data-ttu-id="847b7-130">Defender for Endpoint ポータルの **アラート** ダッシュボード</span><span class="sxs-lookup"><span data-stu-id="847b7-130">The Defender for Endpoint portal's **Alerts** dashboard</span></span>  
- <span data-ttu-id="847b7-131">OData アラート [API と](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) REST [API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span><span class="sxs-lookup"><span data-stu-id="847b7-131">OData alerting [API](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) and [REST API](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)</span></span>
- <span data-ttu-id="847b7-132">[高度な検索の DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) テーブル</span><span class="sxs-lookup"><span data-stu-id="847b7-132">[DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) table in Advanced hunting</span></span>
- <span data-ttu-id="847b7-133">ユーザーのメール(構成することにした場合)</span><span class="sxs-lookup"><span data-stu-id="847b7-133">Your email, if you choose to configure it</span></span> 

<span data-ttu-id="847b7-134">メールにて標的型攻撃通知を受信するには、メール通知ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="847b7-134">To receive targeted attack notifications through email, create an email notification rule.</span></span>

### <a name="create-an-email-notification-rule"></a><span data-ttu-id="847b7-135">電子メール通知ルールの作成</span><span class="sxs-lookup"><span data-stu-id="847b7-135">Create an email notification rule</span></span> 
<span data-ttu-id="847b7-136">通知受信者の電子メール通知を送信するルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="847b7-136">You can create rules to send email notifications for notification recipients.</span></span> <span data-ttu-id="847b7-137">詳細  [については、「アラート通知を構成](configure-email-notifications.md) して電子メール通知を作成、編集、削除、またはトラブルシューティングする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="847b7-137">See  [Configure alert notifications](configure-email-notifications.md) to create, edit, delete, or troubleshoot email notification, for details.</span></span>

## <a name="view-the-targeted-attack-notification"></a><span data-ttu-id="847b7-138">ターゲット攻撃の通知を表示する</span><span class="sxs-lookup"><span data-stu-id="847b7-138">View the targeted attack notification</span></span>  
<span data-ttu-id="847b7-139">電子メール通知を受信するようにシステムを構成したMicrosoft 脅威エキスパートから、電子メール内のターゲット攻撃通知の受信を開始します。</span><span class="sxs-lookup"><span data-stu-id="847b7-139">You'll start receiving targeted attack notification from Microsoft Threat Experts in your email after you have configured your system to receive email notification.</span></span>  

1. <span data-ttu-id="847b7-140">メール内のリンクをクリックして、脅威の専門家とタグ付けされたダッシュボードの対応するアラート コンテキスト **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="847b7-140">Click the link in the email to go to the corresponding alert context in the dashboard tagged with **Threat experts**.</span></span> 

2. <span data-ttu-id="847b7-141">ダッシュボードから、メールから受け取ったのと同じアラート トピックを選択して、詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="847b7-141">From the dashboard, select the same alert topic that you got from the email, to view the details.</span></span>  

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="847b7-142">ユーザー登録Microsoft 脅威エキスパート - エキスパート オンデマンド</span><span class="sxs-lookup"><span data-stu-id="847b7-142">Subscribe to Microsoft Threat Experts - Experts on Demand</span></span>
<span data-ttu-id="847b7-143">これはサブスクリプション サービスとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="847b7-143">This is available as a subscription service.</span></span> <span data-ttu-id="847b7-144">すでに Defender for Endpoint のお客様である場合は、Microsoft の担当者に連絡して、Microsoft 脅威エキスパート - エキスパート オンデマンドに登録することができます。</span><span class="sxs-lookup"><span data-stu-id="847b7-144">If you're already a Defender for Endpoint customer, you can contact your Microsoft representative to subscribe to Microsoft Threat Experts - Experts on Demand.</span></span> 

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a><span data-ttu-id="847b7-145">組織内の疑わしいサイバーセキュリティアクティビティについて Microsoft の脅威専門家に相談する</span><span class="sxs-lookup"><span data-stu-id="847b7-145">Consult a Microsoft threat expert about suspicious cybersecurity activities in your organization</span></span> 
<span data-ttu-id="847b7-146">迅速かつ正確なMicrosoft 脅威エキスパート対応を行う場合は、Microsoft Defender セキュリティ センター内から直接関与できるユーザーと提携できます。</span><span class="sxs-lookup"><span data-stu-id="847b7-146">You can partner with Microsoft Threat Experts who can be engaged directly from within the Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="847b7-147">エキスパートは、複雑な脅威、取得した標的型攻撃通知、またはポータル ダッシュボードに表示されるアラート、潜在的に侵害されたデバイス、または脅威インテリジェンス コンテキストに関する詳細が必要な場合について、より深く理解するために分析情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="847b7-147">Experts provide insights to better understand complex threats, targeted attack notifications that you get, or if you need more information about the alerts, a potentially compromised device, or a threat intelligence context that you see on your portal dashboard.</span></span> 

> [!NOTE]
> - <span data-ttu-id="847b7-148">組織のカスタマイズされた脅威インテリジェンス データに関連するアラートの問い合わせは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="847b7-148">Alert inquiries related to your organization's customized threat intelligence data are currently not supported.</span></span> <span data-ttu-id="847b7-149">詳細については、セキュリティ操作またはインシデント対応チームに問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="847b7-149">Consult your security operations or incident response team for details.</span></span>
> - <span data-ttu-id="847b7-150">「脅威の専門家に相談 **する** 」問い合わせを提出するには、セキュリティ センター ポータルの [セキュリティ設定の管理] アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="847b7-150">You need to have the **Manage security settings** permission in the Security Center portal to be able to submit a "Consult a threat expert" inquiry.</span></span>

1. <span data-ttu-id="847b7-151">調査する関連情報 (インシデント ページなど) を含むポータル ページ **に移動** します。</span><span class="sxs-lookup"><span data-stu-id="847b7-151">Navigate to the portal page with the relevant information that you'd like to investigate, for example, the **Incident** page.</span></span> <span data-ttu-id="847b7-152">調査要求を送信する前に、関連するアラートまたはデバイスのページが表示されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="847b7-152">Ensure that the page for the relevant alert or device is in view before you send an investigation request.</span></span> 

2. <span data-ttu-id="847b7-153">右上のメニューから 、 をクリックします **。**</span><span class="sxs-lookup"><span data-stu-id="847b7-153">From the upper right-hand menu, click the **?**</span></span> <span data-ttu-id="847b7-154">選択します。</span><span class="sxs-lookup"><span data-stu-id="847b7-154">icon.</span></span> <span data-ttu-id="847b7-155">次に、[脅威 **の専門家に相談する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="847b7-155">Then, select **Consult a threat expert**.</span></span> 

    ![メニューからMicrosoft 脅威エキスパートエキスパートオンデマンドのイメージ](images/mte-eod-menu.png)

    <span data-ttu-id="847b7-157">フライアウト画面が開きます。</span><span class="sxs-lookup"><span data-stu-id="847b7-157">A flyout screen opens.</span></span> <span data-ttu-id="847b7-158">次の画面は、試用版サブスクリプションの場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="847b7-158">The following screen shows when you are on a trial subscription.</span></span>

    ![オンデマンド画面Microsoft 脅威エキスパートエキスパートの画像](images/mte-eod.png)

    <span data-ttu-id="847b7-160">次の画面は、完全なサブスクリプションを使用している場合Microsoft 脅威エキスパートエキスパート オンデマンド サブスクリプションを表示します。</span><span class="sxs-lookup"><span data-stu-id="847b7-160">The following screen shows when you are on a full Microsoft Threat Experts - Experts on-Demand subscription.</span></span>

    ![オンデマンドのMicrosoft 脅威エキスパートの完全なサブスクリプション画面の画像](images/mte-eod-fullsubscription.png)

    <span data-ttu-id="847b7-162">[ **問い合わせ** ] トピック フィールドには、調査要求の関連ページへのリンクが事前に入力されています。</span><span class="sxs-lookup"><span data-stu-id="847b7-162">The **Inquiry topic** field is pre-populated with the link to the relevant page for your investigation request.</span></span> <span data-ttu-id="847b7-163">たとえば、要求を行った時点で発生したインシデント、アラート、またはデバイスの詳細ページへのリンクです。</span><span class="sxs-lookup"><span data-stu-id="847b7-163">For example, a link to the incident, alert, or device details page that you were at when you made the request.</span></span>

3.  <span data-ttu-id="847b7-164">次のフィールドで、調査を開始するのに十分なコンテキストMicrosoft 脅威エキスパート情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="847b7-164">In the next field, provide enough information to give the Microsoft Threat Experts enough context to start the investigation.</span></span>
  
4. <span data-ttu-id="847b7-165">メール アドレスに対応するために使用するメール アドレスを入力Microsoft 脅威エキスパート。</span><span class="sxs-lookup"><span data-stu-id="847b7-165">Enter the email address that you'd like to use to correspond with Microsoft Threat Experts.</span></span>

> [!NOTE]
> <span data-ttu-id="847b7-166">Microsoft Services Hub を通じてエキスパート オンデマンド ケースの状態を追跡する場合は、テクニカル アカウント マネージャーに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="847b7-166">If you would like to track the status of your Experts on Demand cases through Microsoft Services Hub, reach out to your Technical Account Manager.</span></span> 

<span data-ttu-id="847b7-167">Microsoft Services Hub の概要については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="847b7-167">Watch this video for a quick overview of the Microsoft Services Hub.</span></span>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f] 


   
## <a name="sample-investigation-topics-that-you-can-consult-with-microsoft-threat-experts---experts-on-demand"></a><span data-ttu-id="847b7-168">調査に関するトピックのサンプルを参照Microsoft 脅威エキスパート - Experts on Demand</span><span class="sxs-lookup"><span data-stu-id="847b7-168">Sample investigation topics that you can consult with Microsoft Threat Experts - Experts on Demand</span></span> 

<span data-ttu-id="847b7-169">**アラート情報**</span><span class="sxs-lookup"><span data-stu-id="847b7-169">**Alert information**</span></span>
- <span data-ttu-id="847b7-170">新しい種類のアラートが、生きている土地のバイナリ ([AlertID]) に表示されます。</span><span class="sxs-lookup"><span data-stu-id="847b7-170">We see a new type of alert for a living-off-the-land binary: [AlertID].</span></span> <span data-ttu-id="847b7-171">このアラートの詳細と、さらに調査する方法について教えてください。</span><span class="sxs-lookup"><span data-stu-id="847b7-171">Can you tell us something more about this alert and how we can investigate further?</span></span>
- <span data-ttu-id="847b7-172">悪意のある PowerShell スクリプトを実行しようとして、異なるアラートを生成する 2 つの同様の攻撃を確認しました。</span><span class="sxs-lookup"><span data-stu-id="847b7-172">We’ve observed two similar attacks, which try to execute malicious PowerShell scripts but generate different alerts.</span></span> <span data-ttu-id="847b7-173">1 つは "不審な PowerShell コマンド ライン" で、もう 1 つは "O365 によって提供される指示に基づいて悪意のあるファイルが検出されました" です。</span><span class="sxs-lookup"><span data-stu-id="847b7-173">One is "Suspicious PowerShell command line" and the other is "A malicious file was detected based on indication provided by O365".</span></span> <span data-ttu-id="847b7-174">違いは何ですか?</span><span class="sxs-lookup"><span data-stu-id="847b7-174">What is the difference?</span></span>
- <span data-ttu-id="847b7-175">プロファイルの高いユーザーのデバイスから失敗したログインの数が異常な場合、今日は奇数の警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="847b7-175">I receive an odd alert today for abnormal number of failed logins from a high profile user’s device.</span></span> <span data-ttu-id="847b7-176">これらのサインイン試行に関するそれ以上の証拠は見つからなっています。</span><span class="sxs-lookup"><span data-stu-id="847b7-176">I cannot find any further evidence around these sign-in attempts.</span></span> <span data-ttu-id="847b7-177">Defender for Endpoint では、これらの試行を確認する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="847b7-177">How can Defender for Endpoint see these attempts?</span></span> <span data-ttu-id="847b7-178">監視対象のサインインの種類</span><span class="sxs-lookup"><span data-stu-id="847b7-178">What type of sign-ins are being monitored?</span></span>
- <span data-ttu-id="847b7-179">このアラートに関するコンテキストや分析情報を追加できます。"システム ユーティリティによる疑わしい動作が観察されました"。</span><span class="sxs-lookup"><span data-stu-id="847b7-179">Can you give more context or insights about this alert: “Suspicious behavior by a system utility was observed”.</span></span> 

<span data-ttu-id="847b7-180">**コンピューターの侵害の可能性**</span><span class="sxs-lookup"><span data-stu-id="847b7-180">**Possible machine compromise**</span></span>
- <span data-ttu-id="847b7-181">「不明なプロセスが観察された」と表示される理由に答えるのに役立ちますか?</span><span class="sxs-lookup"><span data-stu-id="847b7-181">Can you help answer why we see “Unknown process observed?”</span></span> <span data-ttu-id="847b7-182">このメッセージまたはアラートは、多くのデバイスで頻繁に表示されます。</span><span class="sxs-lookup"><span data-stu-id="847b7-182">This message or alert is seen frequently on many devices.</span></span> <span data-ttu-id="847b7-183">このメッセージまたはアラートが悪意のあるアクティビティに関連するかどうかを明確にするための任意の入力に感謝します。</span><span class="sxs-lookup"><span data-stu-id="847b7-183">We appreciate any input to clarify whether this message or alert is related to malicious activity.</span></span>
- <span data-ttu-id="847b7-184">[月] の同じシステムで以前の [マルウェア名] マルウェア検出と同様の動作を使用して、次のシステムで侵害の可能性を検証できますか?</span><span class="sxs-lookup"><span data-stu-id="847b7-184">Can you help validate a possible compromise on the following system on [date] with similar behaviors as the previous [malware name] malware detection on the same system in [month]?</span></span>

<span data-ttu-id="847b7-185">**脅威インテリジェンスの詳細**</span><span class="sxs-lookup"><span data-stu-id="847b7-185">**Threat intelligence details**</span></span>
- <span data-ttu-id="847b7-186">悪意のある Word 文書をユーザーに配信したフィッシングメールが検出されました。</span><span class="sxs-lookup"><span data-stu-id="847b7-186">We detected a phishing email that delivered a malicious Word document to a user.</span></span> <span data-ttu-id="847b7-187">悪意のある Word ドキュメントによって、一連の疑わしいイベントが発生し、[マルウェア名] マルウェアに対する複数の Microsoft Defender アラートがトリガーされました。</span><span class="sxs-lookup"><span data-stu-id="847b7-187">The malicious Word document caused a series of suspicious events, which triggered multiple Microsoft Defender alerts for [malware name] malware.</span></span> <span data-ttu-id="847b7-188">このマルウェアに関する情報はありますか?</span><span class="sxs-lookup"><span data-stu-id="847b7-188">Do you have any information on this malware?</span></span> <span data-ttu-id="847b7-189">はいの場合、リンクを送信できますか?</span><span class="sxs-lookup"><span data-stu-id="847b7-189">If yes, can you send me a link?</span></span>
- <span data-ttu-id="847b7-190">最近、自分の業界を標的にしている脅威に関する [ソーシャル メディア参照( Twitter やブログなど) の投稿を見ました。</span><span class="sxs-lookup"><span data-stu-id="847b7-190">I recently saw a [social media reference, for example, Twitter or blog] post about a threat that is targeting my industry.</span></span> <span data-ttu-id="847b7-191">この脅威アクターに対して Defender for Endpoint が提供する保護を理解するのに役立ちますか?</span><span class="sxs-lookup"><span data-stu-id="847b7-191">Can you help me understand what protection Defender for Endpoint provides against this threat actor?</span></span> 

<span data-ttu-id="847b7-192">**Microsoft 脅威エキスパートのアラート通信**</span><span class="sxs-lookup"><span data-stu-id="847b7-192">**Microsoft Threat Experts’ alert communications**</span></span> 
- <span data-ttu-id="847b7-193">インシデント対応チームは、対象となる攻撃通知に対処するのに役立ちますか?</span><span class="sxs-lookup"><span data-stu-id="847b7-193">Can your incident response team help us address the targeted attack notification that we got?</span></span>
- <span data-ttu-id="847b7-194">この標的型攻撃の通知を受け取ったのは、Microsoft 脅威エキスパート。</span><span class="sxs-lookup"><span data-stu-id="847b7-194">I received this targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="847b7-195">独自のインシデント対応チームは持ち合わせください。</span><span class="sxs-lookup"><span data-stu-id="847b7-195">We don’t have our own incident response team.</span></span> <span data-ttu-id="847b7-196">ここで何を行い、インシデントを含めるのか。</span><span class="sxs-lookup"><span data-stu-id="847b7-196">What can we do now, and how can we contain the incident?</span></span>
- <span data-ttu-id="847b7-197">ターゲット攻撃の通知を受け取ったのは、Microsoft 脅威エキスパート。</span><span class="sxs-lookup"><span data-stu-id="847b7-197">I received a targeted attack notification from Microsoft Threat Experts.</span></span> <span data-ttu-id="847b7-198">インシデント対応チームに渡すデータを提供できますか?</span><span class="sxs-lookup"><span data-stu-id="847b7-198">What data can you provide to us that we can pass on to our incident response team?</span></span>

  >[!NOTE]
  ><span data-ttu-id="847b7-199">Microsoft 脅威エキスパートは、インシデント対応サービスではなく、管理されたサイバーセキュリティハンティング サービスです。</span><span class="sxs-lookup"><span data-stu-id="847b7-199">Microsoft Threat Experts is a managed cybersecurity hunting service and not an incident response service.</span></span> <span data-ttu-id="847b7-200">ただし、専門家は必要に応じて、調査を Microsoft サイバーセキュリティ ソリューション グループ (CSG) の検出および応答チーム (DART) サービスにシームレスに移行できます。</span><span class="sxs-lookup"><span data-stu-id="847b7-200">However, the experts can seamlessly transition the investigation to Microsoft Cybersecurity Solutions Group (CSG)'s  Detection and Response Team (DART) services, when necessary.</span></span> <span data-ttu-id="847b7-201">また、インシデント対応チームと関わり、インシデント対応が必要な問題に対処できます。</span><span class="sxs-lookup"><span data-stu-id="847b7-201">You can also opt to engage with your own incident response team to address issues that requires an incident response.</span></span> 

## <a name="scenario"></a><span data-ttu-id="847b7-202">シナリオ</span><span class="sxs-lookup"><span data-stu-id="847b7-202">Scenario</span></span>

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a><span data-ttu-id="847b7-203">管理された狩猟に関する問い合わせに関する進行状況レポートを受け取る</span><span class="sxs-lookup"><span data-stu-id="847b7-203">Receive a progress report about your managed hunting inquiry</span></span> 
<span data-ttu-id="847b7-204">お問い合Microsoft 脅威エキスパート、お問い合わせに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="847b7-204">Response from Microsoft Threat Experts varies according to your inquiry.</span></span> <span data-ttu-id="847b7-205">2 日以内に脅威専門家の問い合わせに問い合わせて、次のカテゴリから調査状況を伝える進行状況レポートを電子メールで送信します。</span><span class="sxs-lookup"><span data-stu-id="847b7-205">They will email a progress report to you about your **Consult a threat expert** inquiry within two days, to communicate the investigation status from the following categories:</span></span> 
- <span data-ttu-id="847b7-206">調査を続行するには、さらに詳しい情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="847b7-206">More information is needed to continue with the investigation</span></span> 
- <span data-ttu-id="847b7-207">技術的なコンテキストを決定するには、ファイルまたは複数のファイル サンプルが必要です</span><span class="sxs-lookup"><span data-stu-id="847b7-207">A file or several file samples are needed to determine the technical context</span></span> 
- <span data-ttu-id="847b7-208">調査にはより多くの時間が必要</span><span class="sxs-lookup"><span data-stu-id="847b7-208">Investigation requires more time</span></span>   
- <span data-ttu-id="847b7-209">最初の情報は、調査を終了するのに十分でした</span><span class="sxs-lookup"><span data-stu-id="847b7-209">Initial information was enough to conclude the investigation</span></span> 

<span data-ttu-id="847b7-210">調査を動かし続けるには、迅速に対応することが重要です。</span><span class="sxs-lookup"><span data-stu-id="847b7-210">It is crucial to respond in quickly to keep the investigation moving.</span></span> 

## <a name="related-topic"></a><span data-ttu-id="847b7-211">関連トピック</span><span class="sxs-lookup"><span data-stu-id="847b7-211">Related topic</span></span>
- [<span data-ttu-id="847b7-212">Microsoft 脅威エキスパートの概要</span><span class="sxs-lookup"><span data-stu-id="847b7-212">Microsoft Threat Experts overview</span></span>](microsoft-threat-experts.md)
- [<span data-ttu-id="847b7-213">Microsoft 脅威エキスパートのMicrosoft 365概要</span><span class="sxs-lookup"><span data-stu-id="847b7-213">Microsoft Threat Experts in Microsoft 365 Overview</span></span>](/microsoft-365/security/mtp/microsoft-threat-experts)
