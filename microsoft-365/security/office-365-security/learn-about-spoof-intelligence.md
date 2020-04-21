---
title: スプーフィング インテリジェンスを設定する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online および Exchange Online Protection (EOP) で、スプーフィングされた送信者を許可または禁止し、その他のスプーフィングインテリジェンス設定を構成する方法について説明します。
ms.openlocfilehash: 958f27d190748ee12976a6b47794a23e025172cf
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630493"
---
# <a name="configure-spoof-intelligence-in-microsoft-365"></a><span data-ttu-id="0b08a-103">Microsoft 365 でスプーフィングインテリジェンスを構成する</span><span class="sxs-lookup"><span data-stu-id="0b08a-103">Configure spoof intelligence in Microsoft 365</span></span>

<span data-ttu-id="0b08a-104">Exchange Online または exchange online メールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) のお客様のために、メールボックスが含まれる Microsoft 365 顧客は、受信電子メールメッセージが EOP 年 10 2018 月現在のスプーフィングから自動的に保護されます。</span><span class="sxs-lookup"><span data-stu-id="0b08a-104">If you're an Microsoft 365 customer with mailboxes in Exchange Online or a standalone Exchange Online Protection (EOP) customer without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="0b08a-105">EOP は、組織のフィッシングに対する全体的な防衛の一環としてスプーフィングインテリジェンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="0b08a-106">詳細については、「 [Microsoft 365 のスプーフィング対策保護](anti-spoofing-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-106">For more information, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="0b08a-107">送信者が電子メールアドレスをスプーフすると、組織のドメインのいずれかのユーザー、または組織に電子メールを送信する外部ドメインのユーザーのように見えます。</span><span class="sxs-lookup"><span data-stu-id="0b08a-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="0b08a-108">スパムやフィッシング詐欺メールを送信するための送信者スプーフィングを行う攻撃者は、ブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b08a-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="0b08a-109">しかし、正当な送信者がスプーフィングになっているシナリオもあります。</span><span class="sxs-lookup"><span data-stu-id="0b08a-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="0b08a-110">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-110">For example:</span></span>

- <span data-ttu-id="0b08a-111">内部ドメインのスプーフィングの正当なシナリオ:</span><span class="sxs-lookup"><span data-stu-id="0b08a-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="0b08a-112">サードパーティの送信者は、ドメインを使用して、会社の投票のために自分の従業員に一括メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>

  - <span data-ttu-id="0b08a-113">外部企業は、ユーザーの代わりに広告や製品の更新を生成して送信します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-113">An external company generates and sends advertising or product updates on your behalf.</span></span>

  - <span data-ttu-id="0b08a-114">アシスタントは、組織内の他のユーザーに対して定期的に電子メールを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b08a-114">An assistant regularly needs to send email for another person within your organization.</span></span>

  - <span data-ttu-id="0b08a-115">内部アプリケーションが電子メール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="0b08a-116">外部ドメインをスプーフィングするための正当なシナリオ:</span><span class="sxs-lookup"><span data-stu-id="0b08a-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="0b08a-117">送信者は、メーリングリスト (ディスカッションリストとも呼ばれます) 上にあり、メーリングリストは元の送信者からメーリングリストのすべての参加者に電子メールを中継します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>

  - <span data-ttu-id="0b08a-118">外部企業は、別の会社に代わって電子メールを送信します (たとえば、自動化されたレポートや、サービスとしてのソフトウェア会社など)。</span><span class="sxs-lookup"><span data-stu-id="0b08a-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="0b08a-119">スプーフィングインテリジェンス、特に既定の (および唯一の) スプーフィングインテリジェンスポリシーにより、正当な送信者が送信した偽造メールは、Microsoft 365 または外部の電子メールシステムのスパムフィルターでキャッチされることはなく、スパムまたはフィッシング攻撃からユーザーを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="0b08a-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in spam filters in Microsoft 365 or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="0b08a-120">スプーフィングインテリジェンスは、Microsoft 365 Security & コンプライアンスセンターまたは PowerShell (Microsoft 365 お客様向けの Exchange Online PowerShell) で管理できます。Exchange Online Protection PowerShell (スタンドアロン EOP のお客様向け)。</span><span class="sxs-lookup"><span data-stu-id="0b08a-120">You can manage spoof intelligence in the Microsoft 365 Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0b08a-121">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="0b08a-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0b08a-122"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="0b08a-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="0b08a-123">**[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="0b08a-124">**フィッシング対策**ページに直接移動するには、を<https://protection.office.com/antiphishing>使用します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="0b08a-125">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="0b08a-126">スタンドアロンの Exchange Online Protection PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-126">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="0b08a-127">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b08a-127">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="0b08a-128">スプーフィングインテリジェンスポリシーを変更したり、スプーフィングインテリジェンスを有効または無効にしたりするには、**組織の管理**役割グループまたは**セキュリティ管理者**役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b08a-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="0b08a-129">スプーフィングインテリジェンスポリシーへの読み取り専用アクセスでは、**セキュリティリーダー**役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b08a-129">For read-only access to the spoof intelligence policy, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="0b08a-130">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[Office 365 セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-130">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="0b08a-131">スプーフィングインテリジェンスの推奨設定については、 [EOP の既定のフィッシング対策ポリシー設定](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-131">For our recommended settings for spoof intelligence, [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="0b08a-132">セキュリティ & コンプライアンスセンターを使用してスプーフィングされた送信者を管理する</span><span class="sxs-lookup"><span data-stu-id="0b08a-132">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="0b08a-133">Office 365 Enterprise E5 サブスクリプションを使用している場合、または個別に購入して高度な脅威保護 (ATP) アドオンを使用している場合は、[スプーフィングインテリジェンスの洞察](walkthrough-spoof-intelligence-insight.md)を通じてドメインをスプーフィングしている送信者を管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b08a-133">If you have an Office 365 Enterprise E5 subscription or have separately purchased and Advanced Threat Protection (ATP) add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="0b08a-134">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="0b08a-135">[**スパム対策設定**] ページで、[ ![展開]](../../media/scc-expand-icon.png)アイコンをクリックして [**スプーフィングインテリジェンスポリシー**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-135">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![スプーフィングインテリジェンスポリシーを選択する](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="0b08a-137">次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="0b08a-137">Make one of the following selections:</span></span>

   - <span data-ttu-id="0b08a-138">**新しい送信者を確認する**</span><span class="sxs-lookup"><span data-stu-id="0b08a-138">**Review new senders**</span></span>
   - <span data-ttu-id="0b08a-139">**レビュー済みの送信者を表示する**</span><span class="sxs-lookup"><span data-stu-id="0b08a-139">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="0b08a-140">表示される [ユーザー] ポップアップの**スプーフィングを許可するかどう**かを決定するには、次のタブのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-140">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="0b08a-141">**ドメイン**: 送信者が内部ドメイン内のユーザーを偽装します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-141">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="0b08a-142">**外部ドメイン**: 送信者は外部ドメインのユーザーを偽装します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-142">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="0b08a-143">[ ![](../../media/scc-expand-icon.png) **スプーフィングが許可さ**れていますか?] 列の [展開] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b08a-143">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="0b08a-144">スプーフィングされた送信者を許可する場合は [**はい]** を選択し、メッセージをスプーフィングとしてマークする場合は [**いいえ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-144">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="0b08a-145">このアクションは、既定のフィッシング対策ポリシーまたはカスタムの ATP のフィッシング対策ポリシーによって制御されます (既定値は **[迷惑メールフォルダーにメッセージを移動**します)]。</span><span class="sxs-lookup"><span data-stu-id="0b08a-145">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="0b08a-146">詳細については、「[フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-146">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![スプーフィングされた送信者のポップアップと、送信者がスプーフィングを許可するかどうかを示すスクリーンショット](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="0b08a-148">表示される列と値については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-148">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="0b08a-149">**偽装ユーザー**: スプーフィングされているユーザーアカウント。</span><span class="sxs-lookup"><span data-stu-id="0b08a-149">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="0b08a-150">これは、電子メールクライアントに表示される差出人アドレス ( `5322.From`アドレスとも呼ばれます) のメッセージ送信者です。</span><span class="sxs-lookup"><span data-stu-id="0b08a-150">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="0b08a-151">このアドレスの有効性は、SPF によってチェックされません。</span><span class="sxs-lookup"><span data-stu-id="0b08a-151">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="0b08a-152">[**自分のドメイン**] タブの値に1つの電子メールアドレスが含まれている場合、または送信元の電子メールサーバーが複数のユーザーアカウントを偽装している場合は、複数のユーザーアカウントが含ま**れています。**</span><span class="sxs-lookup"><span data-stu-id="0b08a-152">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="0b08a-153">[**外部ドメイン**] タブの値には、完全な電子メールアドレスではなく、偽装されたユーザーのドメインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0b08a-153">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="0b08a-154">[**インフラストラクチャの送信**]: 送信元の電子メールサーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) にあるドメイン、またはソースに PTR レコードがない場合は ip アドレス。</span><span class="sxs-lookup"><span data-stu-id="0b08a-154">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="0b08a-155">メッセージソースとメッセージ送信者の詳細については、「[電子メールメッセージの標準の概要](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-155">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="0b08a-156">**メッセージ数**: 過去30日間に、指定したスプーフィングされた送信者または送信者を含む組織への送信インフラストラクチャからのメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="0b08a-156">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="0b08a-157">**ユーザーの苦情**: 過去30日間にこの送信者に対してユーザーが提出した苦情。</span><span class="sxs-lookup"><span data-stu-id="0b08a-157">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="0b08a-158">通常、苦情は Microsoft への迷惑メール送信の形式です。</span><span class="sxs-lookup"><span data-stu-id="0b08a-158">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="0b08a-159">**認証結果**: 次のいずれかの値です。</span><span class="sxs-lookup"><span data-stu-id="0b08a-159">**Authentication result**: One of the following values:</span></span>

      - <span data-ttu-id="0b08a-160">**成功**: 送信者が送信者の電子メール認証チェック (SPF または dkim) を通過しました。</span><span class="sxs-lookup"><span data-stu-id="0b08a-160">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="0b08a-161">**失敗**しました。送信者は EOP の認証チェックに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="0b08a-161">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="0b08a-162">**Unknown**: これらのチェックの結果は不明です。</span><span class="sxs-lookup"><span data-stu-id="0b08a-162">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="0b08a-163">**Decision set by**: 送信インフラストラクチャがユーザーのスプーフィングを許可されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-163">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="0b08a-164">**スプーフィングインテリジェンスポリシー** (自動)</span><span class="sxs-lookup"><span data-stu-id="0b08a-164">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="0b08a-165">**管理者**(手動)</span><span class="sxs-lookup"><span data-stu-id="0b08a-165">**Admin** (manual)</span></span>

   - <span data-ttu-id="0b08a-166">**最終表示**日: 偽装されたユーザーを含む送信元インフラストラクチャからメッセージが受信された最後の日付。</span><span class="sxs-lookup"><span data-stu-id="0b08a-166">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="0b08a-167">**スプーフィングが許可されますか?**: ここに表示される値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0b08a-167">**Allowed to spoof?**: The values that you see here are:</span></span>

     - <span data-ttu-id="0b08a-168">**Yes**: スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージが許可され、スプーフィングされた電子メールとして扱われることはありません。</span><span class="sxs-lookup"><span data-stu-id="0b08a-168">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="0b08a-169">**いいえ**: スプーフィングされたユーザーと送信元インフラストラクチャの組み合わせからのメッセージは、スプーフィングとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="0b08a-169">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="0b08a-170">このアクションは、既定のフィッシング対策ポリシーまたはカスタムの ATP のフィッシング対策ポリシーによって制御されます (既定値は **[迷惑メールフォルダーにメッセージを移動**します)]。</span><span class="sxs-lookup"><span data-stu-id="0b08a-170">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="0b08a-171">詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-171">See the next section for more information.</span></span>

     - <span data-ttu-id="0b08a-172">**一部のユーザー** ([**自分のドメイン**] タブのみ): 送信元のインフラストラクチャは複数のユーザーをスプーフィングしています。これには、一部のスプーフィングされたユーザーが許可されています。</span><span class="sxs-lookup"><span data-stu-id="0b08a-172">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="0b08a-173">特定のアドレスを表示するには、[**詳細**] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-173">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="0b08a-174">ページの下部にある [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b08a-174">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="0b08a-175">PowerShell を使用してスプーフィングされた送信者を管理する</span><span class="sxs-lookup"><span data-stu-id="0b08a-175">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="0b08a-176">スプーフィングインテリジェンスで許可された送信者と受信拒否送信者を表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-176">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="0b08a-177">この例では、ドメイン内のユーザーのスプーフィングを許可されているすべての送信者に関する詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-177">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilter -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="0b08a-178">構文およびパラメーターの詳細については、「 [get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-178">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy).</span></span>

<span data-ttu-id="0b08a-179">許可およびブロックされる送信者をスプーフィングインテリジェンスで構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-179">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="0b08a-180">検出されたスプーフィングされた送信者の現在のリストを取得するには、 **get-phishfilterpolicy**コマンドレットの出力を CSV ファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="0b08a-180">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="0b08a-181">CSV ファイルを編集して、 **SpoofedUser** (メールアドレス) および**allowedtospoof** (Yes または No) の値を追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-181">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="0b08a-182">ファイルを保存し、ファイルを読み取って、コンテンツをという名前`$UpdateSpoofedSenders`の変数として保存します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-182">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="0b08a-183">`$UpdateSpoofedSenders`変数を使用して、スプーフィングインテリジェンスポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-183">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="0b08a-184">構文およびパラメーターの詳細については、「 [get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-184">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="0b08a-185">セキュリティ & コンプライアンスセンターを使用してスプーフィングインテリジェンスを構成する</span><span class="sxs-lookup"><span data-stu-id="0b08a-185">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="0b08a-186">スプーフィングインテリジェンスの構成オプションの詳細については、「[フィッシング対策ポリシー」の「スプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-186">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="0b08a-187">利用可能なオプションは、サブスクリプションによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0b08a-187">Your available options depend on your subscription:</span></span>

- <span data-ttu-id="0b08a-188">Exchange Online メールボックスを使用しないスタンドアロン EOP 組織では、スプーフィングインテリジェンス設定を構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="0b08a-188">Standalone EOP organizations without Exchange Online mailboxes can't configure spoof intelligence settings.</span></span>

- <span data-ttu-id="0b08a-189">Microsoft 365 組織の Exchange Online メールボックスでは、既定の (のみの) フィッシング対策ポリシーでスプーフィングインテリジェンス設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0b08a-189">Microsoft 365 organizations with Exchange Online mailboxes can configure spoof intelligence settings in the default (and only) anti-phishing policy.</span></span> <span data-ttu-id="0b08a-190">手順については、 [EOP の「既定のフィッシング対策ポリシーを構成する](configure-anti-phishing-policies-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-190">For instructions, see [Configure the default anti-phishing policy in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="0b08a-191">ATP を使用している Microsoft 365 組織は、既定の ATP のフィッシング対策ポリシーで、およびカスタムの ATP のフィッシング対策ポリシーでも、スプーフィングインテリジェンスの設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0b08a-191">Microsoft 365 organizations with ATP can configure spoof intelligence settings in the default ATP anti-phishing policy, and also in custom ATP anti-phishing policies.</span></span> <span data-ttu-id="0b08a-192">手順については、「 [Microsoft 365 で ATP のフィッシング対策ポリシーを構成する](configure-atp-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-192">For instructions, see [Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="0b08a-193">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="0b08a-193">How do you know these procedures worked?</span></span>

<span data-ttu-id="0b08a-194">許可されている送信者とスプーフィングが許可されていない送信者、およびスプーフィングインテリジェンスの設定が構成済みであるというスプーフィングインテリジェンスが構成されていることを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-194">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="0b08a-195">[セキュリティ & コンプライアンスセンター] で、[**脅威\*\*\*\*の** \>管理\> **ポリシー** \>のスパム対策]、[**スプーフィングインテリジェンスポリシー** \>の選択] の順**に** \>選択します。 [**ドメイン**または**外部ドメイン**] タブを選択し、[**スプーフィングを許可する**] の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-195">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="0b08a-196">PowerShell で、次のコマンドを実行して、許可されている、またはスプーフィングが許可されていない送信者を表示します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-196">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilter -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="0b08a-197">PowerShell で次のコマンドを実行して、すべてのスプーフィングされた送信者の一覧を CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="0b08a-197">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="0b08a-198">Exchange Online メールボックスを使用する Microsoft 365 の組織では、次の手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-198">In Microsoft 365 organizations with Exchange Online mailboxes, do either of the following steps:</span></span>

  - <span data-ttu-id="0b08a-199">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \>の**フィッシング** \>対策] に移動し、[**既定のポリシー** ] をクリックして、フライアウトの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-199">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

  - <span data-ttu-id="0b08a-200">Exchange Online PowerShell で次のコマンドを実行し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-200">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

    ```PowerShell
    Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
    ```

- <span data-ttu-id="0b08a-201">Microsoft 365 ATP 組織で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-201">In Microsoft 365 ATP organizations, do either of the following steps:</span></span>

  - <span data-ttu-id="0b08a-202">セキュリティ & コンプライアンスセンターで、[**脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動し、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-202">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** and do either of the following steps:</span></span>

    - <span data-ttu-id="0b08a-203">リストからポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-203">Select a policy from the list.</span></span> <span data-ttu-id="0b08a-204">表示されたポップアップで、[**スプーフ**] セクションの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-204">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
    - <span data-ttu-id="0b08a-205">[**既定のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0b08a-205">Click **Default policy**.</span></span> <span data-ttu-id="0b08a-206">表示されたポップアップで、[**スプーフ**] セクションの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-206">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

  - <span data-ttu-id="0b08a-207">Exchange Online PowerShell で、Name \<\>を Office365 フィッシング対策 Default またはカスタムの ATP のフィッシング対策ポリシーの名前に置き換え、次のコマンドを実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-207">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom ATP anti-phishing policy, and run the following command and verify the settings:</span></span>

    ```PowerShell
    Get-AntiPhishPolicy -Identity "<Name>"
    ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="0b08a-208">スプーフィングとフィッシングを管理するその他の方法</span><span class="sxs-lookup"><span data-stu-id="0b08a-208">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="0b08a-209">スプーフィングとフィッシングの保護については、入念に行ってください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-209">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="0b08a-210">ここでは、ドメインをスプーフィングしている送信者をチェックして、組織の損害を防ぐ方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-210">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="0b08a-211">**スプーフィングメールレポート**を確認します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-211">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="0b08a-212">このレポートは多くの場合、スプーフィングされた送信者を表示して管理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="0b08a-212">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="0b08a-213">詳細については、「[スプーフィング検出レポート](view-email-security-reports.md#spoof-detections-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-213">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="0b08a-214">Sender Policy Framework (SPF) 構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-214">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="0b08a-215">SPF の簡単な説明と、すぐに構成を構成する方法については、「 [Microsoft 365 で spf を設定する」を](set-up-spf-in-office-365-to-help-prevent-spoofing.md)参照して、スプーフィングを防止してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-215">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="0b08a-216">Office 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-216">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="0b08a-217">DomainKeys が識別されたメール (DKIM) 構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-217">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="0b08a-218">SPF および DMARC に加えて DKIM を使用して、攻撃者がドメインから受信したように見えるメッセージを送信できないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b08a-218">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="0b08a-219">DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加できます。</span><span class="sxs-lookup"><span data-stu-id="0b08a-219">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="0b08a-220">詳細については、「 [DKIM を使用して、Office 365 でカスタムドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-220">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="0b08a-221">ドメインベースのメッセージ認証、レポート、および準拠 (DMARC) 構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="0b08a-221">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="0b08a-222">SPF および DKIM と共に DMARC を実装すると、メールのスプーフィングやフィッシングに対抗する追加の保護が得られます。</span><span class="sxs-lookup"><span data-stu-id="0b08a-222">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="0b08a-223">DMARC は、電子メールを受信するシステムが、ドメインから送信された SPF チェックまたは DKIM チェックに失敗したメッセージに対して、どのように対応するかを判断する際に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="0b08a-223">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="0b08a-224">詳細については、「 [USE DMARC to validate email In Office 365](use-dmarc-to-validate-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0b08a-224">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>