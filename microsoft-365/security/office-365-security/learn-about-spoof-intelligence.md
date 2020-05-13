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
ms.custom:
- seo-marvel-apr2020
description: 管理者は、特定のスプーフィングされた送信者を許可またはブロックする Exchange Online Protection (EOP) のスプーフィングインテリジェンスについて学ぶことができます。
ms.openlocfilehash: 607c11d82a145828af736d8d1ecab1dff367f94d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206642"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="8f0e5-103">EOP でスプーフィングインテリジェンスを構成する</span><span class="sxs-lookup"><span data-stu-id="8f0e5-103">Configure spoof intelligence in EOP</span></span>

<span data-ttu-id="8f0e5-104">Exchange online またはスタンドアロンの exchange Online Protection (EOP) 組織にメールボックスがあり、Exchange Online メールボックスを使用していない場合、受信電子メールメッセージは2018年10月の間に EOP によって自動的に保護されます。365</span><span class="sxs-lookup"><span data-stu-id="8f0e5-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="8f0e5-105">EOP は、組織のフィッシングに対する全体的な防衛の一環としてスプーフィングインテリジェンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="8f0e5-106">詳細については、「 [EOP でのスプーフィング対策保護](anti-spoofing-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-106">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="8f0e5-107">送信者が電子メールアドレスをスプーフすると、組織のドメインのいずれかのユーザー、または組織に電子メールを送信する外部ドメインのユーザーのように見えます。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="8f0e5-108">スパムやフィッシング詐欺メールを送信するための送信者スプーフィングを行う攻撃者は、ブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="8f0e5-109">しかし、正当な送信者がスプーフィングになっているシナリオもあります。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="8f0e5-110">例:</span><span class="sxs-lookup"><span data-stu-id="8f0e5-110">For example:</span></span>

- <span data-ttu-id="8f0e5-111">内部ドメインのスプーフィングの正当なシナリオ:</span><span class="sxs-lookup"><span data-stu-id="8f0e5-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="8f0e5-112">サードパーティの送信者は、ドメインを使用して、会社の投票のために自分の従業員に一括メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>

  - <span data-ttu-id="8f0e5-113">外部企業は、ユーザーの代わりに広告や製品の更新を生成して送信します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-113">An external company generates and sends advertising or product updates on your behalf.</span></span>

  - <span data-ttu-id="8f0e5-114">アシスタントは、組織内の他のユーザーに対して定期的に電子メールを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-114">An assistant regularly needs to send email for another person within your organization.</span></span>

  - <span data-ttu-id="8f0e5-115">内部アプリケーションが電子メール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="8f0e5-116">外部ドメインをスプーフィングするための正当なシナリオ:</span><span class="sxs-lookup"><span data-stu-id="8f0e5-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="8f0e5-117">送信者は、メーリングリスト (ディスカッションリストとも呼ばれます) 上にあり、メーリングリストは元の送信者からメーリングリストのすべての参加者に電子メールを中継します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>

  - <span data-ttu-id="8f0e5-118">外部企業は、別の会社に代わって電子メールを送信します (たとえば、自動化されたレポートや、サービスとしてのソフトウェア会社など)。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="8f0e5-119">スプーフィングインテリジェンス、特に既定の (および唯一の) スプーフィングインテリジェンスポリシーにより、正当な送信者が送信した偽造メールは、Microsoft 365 または外部の電子メールシステムのスパムフィルターでキャッチされることはなく、スパムまたはフィッシング攻撃からユーザーを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in spam filters in Microsoft 365 or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="8f0e5-120">セキュリティ & コンプライアンスセンター、または PowerShell (exchange online のメールボックスを使用する Microsoft 365 組織の場合は exchange online PowerShell、exchange online メールボックスを使用していない組織の場合は、スタンドアロン EOP PowerShell) で、スプーフィングインテリジェンスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-120">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8f0e5-121">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="8f0e5-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8f0e5-122"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8f0e5-123">**[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="8f0e5-124">**フィッシング対策**ページに直接移動するには、を使用 <https://protection.office.com/antiphishing> します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="8f0e5-125">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="8f0e5-126">スタンドアロンの Exchange Online Protection PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-126">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="8f0e5-127">これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-127">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="8f0e5-128">スプーフィングインテリジェンスポリシーを変更したり、スプーフィングインテリジェンスを有効または無効にしたりするには、**組織の管理**役割グループまたは**セキュリティ管理者**役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="8f0e5-129">スプーフィングインテリジェンスポリシーへの読み取り専用アクセスでは、**セキュリティリーダー**役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-129">For read-only access to the spoof intelligence policy, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="8f0e5-130">セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-130">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="8f0e5-131">スプーフィングインテリジェンスの推奨設定については、 [EOP の既定のフィッシング対策ポリシー設定](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)を確認してください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-131">For our recommended settings for spoof intelligence, [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="8f0e5-132">セキュリティ & コンプライアンスセンターを使用してスプーフィングされた送信者を管理する</span><span class="sxs-lookup"><span data-stu-id="8f0e5-132">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="8f0e5-133">Microsoft 365 Enterprise E5 サブスクリプションを使用している場合、または Office 365 Advanced Threat Protection (Office 365 ATP) アドオンを個別に購入した場合は、[スプーフィングインテリジェンスの洞察](walkthrough-spoof-intelligence-insight.md)を通じてドメインをスプーフィングしている送信者を管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-133">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased an Office 365 Advanced Threat Protection (Office 365 ATP) add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="8f0e5-134">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="8f0e5-135">[**スパム対策設定**] ページで、[ ![ 展開] アイコンをクリックして [ ](../../media/scc-expand-icon.png) **スプーフィングインテリジェンスポリシー**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-135">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![スプーフィングインテリジェンスポリシーを選択する](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="8f0e5-137">次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-137">Make one of the following selections:</span></span>

   - <span data-ttu-id="8f0e5-138">**新しい送信者を確認する**</span><span class="sxs-lookup"><span data-stu-id="8f0e5-138">**Review new senders**</span></span>
   - <span data-ttu-id="8f0e5-139">**レビュー済みの送信者を表示する**</span><span class="sxs-lookup"><span data-stu-id="8f0e5-139">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="8f0e5-140">表示される [ユーザー] ポップアップの**スプーフィングを許可するかどう**かを決定するには、次のタブのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-140">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="8f0e5-141">**ドメイン**: 送信者が内部ドメイン内のユーザーを偽装します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-141">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="8f0e5-142">**外部ドメイン**: 送信者は外部ドメインのユーザーを偽装します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-142">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="8f0e5-143">[ ![ ](../../media/scc-expand-icon.png) **スプーフィングが許可さ**れていますか?] 列の [展開] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-143">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="8f0e5-144">スプーフィングされた送信者を許可する場合は [**はい]** を選択し、メッセージをスプーフィングとしてマークする場合は [**いいえ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-144">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="8f0e5-145">このアクションは、既定のフィッシング対策ポリシーまたはカスタムの ATP のフィッシング対策ポリシーによって制御されます (既定値は **[迷惑メールフォルダーにメッセージを移動**します)]。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-145">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="8f0e5-146">詳細については、「[フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-146">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![スプーフィングされた送信者のポップアップと、送信者がスプーフィングを許可するかどうかを示すスクリーンショット](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="8f0e5-148">表示される列と値については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-148">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="8f0e5-149">**偽装ユーザー**: スプーフィングされているユーザーアカウント。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-149">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="8f0e5-150">これは、 `5322.From` 電子メールクライアントに表示される差出人アドレス (アドレスとも呼ばれます) のメッセージ送信者です。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-150">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="8f0e5-151">このアドレスの有効性は、SPF によってチェックされません。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-151">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="8f0e5-152">[**自分のドメイン**] タブの値に1つの電子メールアドレスが含まれている場合、または送信元の電子メールサーバーが複数のユーザーアカウントを偽装している場合は、複数のユーザーアカウントが含ま**れています。**</span><span class="sxs-lookup"><span data-stu-id="8f0e5-152">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="8f0e5-153">[**外部ドメイン**] タブの値には、完全な電子メールアドレスではなく、偽装されたユーザーのドメインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-153">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="8f0e5-154">[**インフラストラクチャの送信**]: 送信元の電子メールサーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) にあるドメイン、またはソースに PTR レコードがない場合は ip アドレス。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-154">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="8f0e5-155">メッセージソースとメッセージ送信者の詳細については、「[電子メールメッセージの標準の概要](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-155">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="8f0e5-156">**メッセージ数**: 過去30日間に、指定したスプーフィングされた送信者または送信者を含む組織への送信インフラストラクチャからのメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-156">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="8f0e5-157">**ユーザーの苦情**: 過去30日間にこの送信者に対してユーザーが提出した苦情。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-157">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="8f0e5-158">通常、苦情は Microsoft への迷惑メール送信の形式です。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-158">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="8f0e5-159">**認証結果**: 次のいずれかの値です。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-159">**Authentication result**: One of the following values:</span></span>

      - <span data-ttu-id="8f0e5-160">**成功**: 送信者が送信者の電子メール認証チェック (SPF または dkim) を通過しました。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-160">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="8f0e5-161">**失敗**しました。送信者は EOP の認証チェックに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-161">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="8f0e5-162">**Unknown**: これらのチェックの結果は不明です。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-162">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="8f0e5-163">**Decision set by**: 送信インフラストラクチャがユーザーのスプーフィングを許可されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-163">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="8f0e5-164">**スプーフィングインテリジェンスポリシー** (自動)</span><span class="sxs-lookup"><span data-stu-id="8f0e5-164">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="8f0e5-165">**管理者**(手動)</span><span class="sxs-lookup"><span data-stu-id="8f0e5-165">**Admin** (manual)</span></span>

   - <span data-ttu-id="8f0e5-166">**最終表示**日: 偽装されたユーザーを含む送信元インフラストラクチャからメッセージが受信された最後の日付。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-166">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="8f0e5-167">**スプーフィングが許可されますか?**: ここに表示される値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-167">**Allowed to spoof?**: The values that you see here are:</span></span>

     - <span data-ttu-id="8f0e5-168">**Yes**: スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージが許可され、スプーフィングされた電子メールとして扱われることはありません。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-168">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="8f0e5-169">**いいえ**: スプーフィングされたユーザーと送信元インフラストラクチャの組み合わせからのメッセージは、スプーフィングとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-169">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="8f0e5-170">このアクションは、既定のフィッシング対策ポリシーまたはカスタムの ATP のフィッシング対策ポリシーによって制御されます (既定値は **[迷惑メールフォルダーにメッセージを移動**します)]。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-170">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="8f0e5-171">詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-171">See the next section for more information.</span></span>

     - <span data-ttu-id="8f0e5-172">**一部のユーザー** ([**自分のドメイン**] タブのみ): 送信元のインフラストラクチャは複数のユーザーをスプーフィングしています。これには、一部のスプーフィングされたユーザーが許可されています。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-172">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="8f0e5-173">特定のアドレスを表示するには、[**詳細**] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-173">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="8f0e5-174">ページの下部にある [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-174">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="8f0e5-175">PowerShell を使用してスプーフィングされた送信者を管理する</span><span class="sxs-lookup"><span data-stu-id="8f0e5-175">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="8f0e5-176">スプーフィングインテリジェンスで許可された送信者と受信拒否送信者を表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-176">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="8f0e5-177">この例では、ドメイン内のユーザーのスプーフィングを許可されているすべての送信者に関する詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-177">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilter -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="8f0e5-178">構文およびパラメーターの詳細については、「 [get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-178">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-phishfilterpolicy).</span></span>

<span data-ttu-id="8f0e5-179">許可およびブロックされる送信者をスプーフィングインテリジェンスで構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-179">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="8f0e5-180">検出されたスプーフィングされた送信者の現在のリストを取得するには、 **get-phishfilterpolicy**コマンドレットの出力を CSV ファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-180">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="8f0e5-181">CSV ファイルを編集して、 **SpoofedUser** (メールアドレス) および**allowedtospoof** (Yes または No) の値を追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-181">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="8f0e5-182">ファイルを保存し、ファイルを読み取って、コンテンツをという名前の変数として保存し `$UpdateSpoofedSenders` ます。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-182">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="8f0e5-183">変数を使用し `$UpdateSpoofedSenders` て、スプーフィングインテリジェンスポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-183">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="8f0e5-184">構文およびパラメーターの詳細については、「 [get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-184">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="8f0e5-185">セキュリティ & コンプライアンスセンターを使用してスプーフィングインテリジェンスを構成する</span><span class="sxs-lookup"><span data-stu-id="8f0e5-185">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="8f0e5-186">スプーフィングインテリジェンスの構成オプションの詳細については、「[フィッシング対策ポリシー」の「スプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-186">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="8f0e5-187">スプーフィングインテリジェンスの設定は、既定のフィッシング対策ポリシーとカスタムポリシーで構成できます。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-187">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="8f0e5-188">サブスクリプションに基づく手順については、以下のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-188">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="8f0e5-189">[EOP でフィッシング対策ポリシーを構成](configure-anti-phishing-policies-eop.md)します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-189">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="8f0e5-190">[Microsoft 365 で ATP のフィッシング対策ポリシーを構成](configure-atp-anti-phishing-policies.md)します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-190">[Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="8f0e5-191">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="8f0e5-191">How do you know these procedures worked?</span></span>

<span data-ttu-id="8f0e5-192">許可されている送信者とスプーフィングが許可されていない送信者、およびスプーフィングインテリジェンスの設定が構成済みであるというスプーフィングインテリジェンスが構成されていることを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-192">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="8f0e5-193">[セキュリティ & コンプライアンスセンター] で、[**脅威の管理**ポリシーのスパム対策]、 \> **Policy** \> **Anti-spam** \> [**スプーフィングインテリジェンスポリシー**の選択] の \> 順**に**選択します \> 。 [**ドメイン**または**外部ドメイン**] タブを選択し、[**スプーフィングを許可する**] の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-193">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="8f0e5-194">PowerShell で、次のコマンドを実行して、許可されている、またはスプーフィングが許可されていない送信者を表示します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-194">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilter -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilter -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="8f0e5-195">PowerShell で次のコマンドを実行して、すべてのスプーフィングされた送信者の一覧を CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-195">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="8f0e5-196">Exchange Online メールボックスを使用する Microsoft 365 の組織では、次の手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-196">In Microsoft 365 organizations with Exchange Online mailboxes, do either of the following steps:</span></span>

  - <span data-ttu-id="8f0e5-197">[セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー**の \> **フィッシング対策**] に移動し、 \> [既定の**ポリシー** ] をクリックして、フライアウトの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-197">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-phishing** \> click **Default policy** and view the details in the flyout.</span></span>

  - <span data-ttu-id="8f0e5-198">Exchange Online PowerShell で次のコマンドを実行し、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-198">In Exchange Online PowerShell, run the following command and verify the settings:</span></span>

    ```PowerShell
    Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
    ```

- <span data-ttu-id="8f0e5-199">Microsoft 365 ATP 組織で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-199">In Microsoft 365 ATP organizations, do either of the following steps:</span></span>

  - <span data-ttu-id="8f0e5-200">セキュリティ & コンプライアンスセンターで、[**脅威管理** \> **ポリシー** \> **ATP のフィッシング対策**] に移動し、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-200">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **ATP anti-phishing** and do either of the following steps:</span></span>

    - <span data-ttu-id="8f0e5-201">リストからポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-201">Select a policy from the list.</span></span> <span data-ttu-id="8f0e5-202">表示されたポップアップで、[**スプーフ**] セクションの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-202">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
    - <span data-ttu-id="8f0e5-203">[**既定のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-203">Click **Default policy**.</span></span> <span data-ttu-id="8f0e5-204">表示されたポップアップで、[**スプーフ**] セクションの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-204">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

  - <span data-ttu-id="8f0e5-205">Exchange Online PowerShell で、 \< Name を \> Office365 フィッシング対策 Default またはカスタムの ATP のフィッシング対策ポリシーの名前に置き換え、次のコマンドを実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-205">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom ATP anti-phishing policy, and run the following command and verify the settings:</span></span>

    ```PowerShell
    Get-AntiPhishPolicy -Identity "<Name>"
    ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="8f0e5-206">スプーフィングとフィッシングを管理するその他の方法</span><span class="sxs-lookup"><span data-stu-id="8f0e5-206">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="8f0e5-207">スプーフィングとフィッシングの保護については、入念に行ってください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-207">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="8f0e5-208">ここでは、ドメインをスプーフィングしている送信者をチェックして、組織の損害を防ぐ方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-208">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="8f0e5-209">**スプーフィングメールレポート**を確認します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-209">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="8f0e5-210">このレポートは多くの場合、スプーフィングされた送信者を表示して管理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-210">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="8f0e5-211">詳細については、「[スプーフィング検出レポート](view-email-security-reports.md#spoof-detections-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-211">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="8f0e5-212">Sender Policy Framework (SPF) 構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-212">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="8f0e5-213">SPF の概要と SPF を迅速に構成する方法については、「[スプーフィングを防止するために Microsoft 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-213">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="8f0e5-214">Office 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-214">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="8f0e5-215">DomainKeys が識別されたメール (DKIM) 構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-215">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="8f0e5-216">SPF および DMARC に加えて DKIM を使用して、攻撃者がドメインから受信したように見えるメッセージを送信できないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-216">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="8f0e5-217">DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-217">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="8f0e5-218">詳細については、「 [DKIM を使用して、Office 365 でカスタムドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-218">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="8f0e5-219">ドメインベースのメッセージ認証、レポート、および準拠 (DMARC) 構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-219">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="8f0e5-220">SPF および DKIM と共に DMARC を実装すると、メールのスプーフィングやフィッシングに対抗する追加の保護が得られます。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-220">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="8f0e5-221">DMARC は、電子メールを受信するシステムが、ドメインから送信された SPF チェックまたは DKIM チェックに失敗したメッセージに対して、どのように対応するかを判断する際に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-221">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="8f0e5-222">詳細については、「 [USE DMARC to validate email In Office 365](use-dmarc-to-validate-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f0e5-222">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>