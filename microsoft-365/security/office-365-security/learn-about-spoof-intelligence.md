---
title: スプーフィング インテリジェンスを構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
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
ms.openlocfilehash: 9168d43e6e5544ad3454729afc8140642deba0ef
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572731"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="e594f-103">EOP でスプーフィングインテリジェンスを構成する</span><span class="sxs-lookup"><span data-stu-id="e594f-103">Configure spoof intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e594f-104">Exchange online またはスタンドアロンの exchange Online Protection (EOP) 組織にメールボックスがあり、Exchange Online メールボックスを使用していない場合、受信電子メールメッセージは2018年10月の間に EOP によって自動的に保護されます。365</span><span class="sxs-lookup"><span data-stu-id="e594f-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="e594f-105">EOP は、組織のフィッシングに対する全体的な防衛の一環としてスプーフィングインテリジェンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="e594f-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="e594f-106">詳細については、「 [EOP でのスプーフィング対策保護](anti-spoofing-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-106">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="e594f-107">送信者が電子メールアドレスをスプーフすると、組織のドメインのいずれかのユーザー、または組織に電子メールを送信する外部ドメインのユーザーのように見えます。</span><span class="sxs-lookup"><span data-stu-id="e594f-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="e594f-108">スパムやフィッシング詐欺メールを送信するための送信者スプーフィングを行う攻撃者は、ブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e594f-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="e594f-109">しかし、正当な送信者がスプーフィングになっているシナリオもあります。</span><span class="sxs-lookup"><span data-stu-id="e594f-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="e594f-110">例:</span><span class="sxs-lookup"><span data-stu-id="e594f-110">For example:</span></span>

- <span data-ttu-id="e594f-111">内部ドメインのスプーフィングの正当なシナリオ:</span><span class="sxs-lookup"><span data-stu-id="e594f-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="e594f-112">サードパーティの送信者は、ドメインを使用して、会社の投票のために自分の従業員に一括メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="e594f-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="e594f-113">外部企業は、ユーザーの代わりに広告や製品の更新を生成して送信します。</span><span class="sxs-lookup"><span data-stu-id="e594f-113">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="e594f-114">アシスタントは、組織内の他のユーザーに対して定期的に電子メールを送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e594f-114">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="e594f-115">内部アプリケーションが電子メール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="e594f-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="e594f-116">外部ドメインをスプーフィングするための正当なシナリオ:</span><span class="sxs-lookup"><span data-stu-id="e594f-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="e594f-117">送信者は、メーリングリスト (ディスカッションリストとも呼ばれます) 上にあり、メーリングリストは元の送信者からメーリングリストのすべての参加者に電子メールを中継します。</span><span class="sxs-lookup"><span data-stu-id="e594f-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="e594f-118">外部企業は、別の会社に代わって電子メールを送信します (たとえば、自動化されたレポートや、サービスとしてのソフトウェア会社など)。</span><span class="sxs-lookup"><span data-stu-id="e594f-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="e594f-119">スプーフィングインテリジェンス、特に既定の (および唯一の) スプーフィングインテリジェンスポリシーにより、正当な送信者が送信したスプーフィングされた電子メールが EOP スパムフィルターや外部の電子メールシステムでキャッチされないようにしながら、スパムまたはフィッシング攻撃からユーザーを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="e594f-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="e594f-120">セキュリティ & コンプライアンスセンター、または PowerShell (exchange online のメールボックスを使用する Microsoft 365 組織の場合は exchange online PowerShell、exchange online メールボックスを使用していない組織の場合は、スタンドアロン EOP PowerShell) で、スプーフィングインテリジェンスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e594f-120">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e594f-121">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="e594f-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e594f-122"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="e594f-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e594f-123">**[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。</span><span class="sxs-lookup"><span data-stu-id="e594f-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="e594f-124">**フィッシング対策** ページに直接移動するには、を使用 <https://protection.office.com/antiphishing> します。</span><span class="sxs-lookup"><span data-stu-id="e594f-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="e594f-125">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e594f-126">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-126">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e594f-127">この記事の手順を実行する前に、セキュリティ & コンプライアンスセンターでアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e594f-127">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="e594f-128">スプーフィングインテリジェンスポリシーを変更したり、スプーフィングインテリジェンスを有効または無効にしたりするには、 **組織の管理** 役割グループまたは **セキュリティ管理者** 役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e594f-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="e594f-129">スプーフィングインテリジェンスポリシーへの読み取り専用アクセスでは、 **グローバル閲覧** 者または **セキュリティリーダー** の役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="e594f-129">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="e594f-130">詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-130">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="e594f-131">**注**:</span><span class="sxs-lookup"><span data-stu-id="e594f-131">**Notes**:</span></span>

  - <span data-ttu-id="e594f-132">Microsoft 365 管理センターで対応する Azure Active Directory の役割にユーザーを追加すると、セキュリティ & コンプライアンスセンター _および_ microsoft 365 の他の機能に対するアクセス許可で必要なアクセス許可がユーザーに付与されます。</span><span class="sxs-lookup"><span data-stu-id="e594f-132">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="e594f-133">詳細については、[「管理者の役割について」](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-133">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="e594f-134">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **表示のみの組織の管理** 役割グループは、機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="e594f-134">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="e594f-135">スプーフィングインテリジェンスに推奨される設定については、「 [EOP default フィッシング対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-135">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="e594f-136">セキュリティ & コンプライアンスセンターを使用してスプーフィングされた送信者を管理する</span><span class="sxs-lookup"><span data-stu-id="e594f-136">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="e594f-137">Microsoft 365 Enterprise E5 サブスクリプションを使用している場合、または Microsoft Defender for Office 365 アドオンを別途購入している場合は、 [スプーフィングインテリジェンスの洞察](walkthrough-spoof-intelligence-insight.md)を通じてドメインをスプーフィングしている送信者を管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="e594f-137">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased a Microsoft Defender for Office 365 add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="e594f-138">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e594f-138">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="e594f-139">[ **スパム対策設定** ] ページで、[ ![ 展開] アイコンをクリックして [ ](../../media/scc-expand-icon.png) **スプーフィングインテリジェンスポリシー**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="e594f-139">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![スプーフィングインテリジェンスポリシーを選択する](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="e594f-141">次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="e594f-141">Make one of the following selections:</span></span>

   - <span data-ttu-id="e594f-142">**新しい送信者を確認する**</span><span class="sxs-lookup"><span data-stu-id="e594f-142">**Review new senders**</span></span>
   - <span data-ttu-id="e594f-143">**レビュー済みの送信者を表示する**</span><span class="sxs-lookup"><span data-stu-id="e594f-143">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="e594f-144">表示される [ユーザー] ポップアップの **スプーフィングを許可するかどう** かを決定するには、次のタブのいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="e594f-144">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="e594f-145">**ドメイン**: 送信者が内部ドメイン内のユーザーを偽装します。</span><span class="sxs-lookup"><span data-stu-id="e594f-145">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="e594f-146">**外部ドメイン**: 送信者は外部ドメインのユーザーを偽装します。</span><span class="sxs-lookup"><span data-stu-id="e594f-146">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="e594f-147">[ ![ ](../../media/scc-expand-icon.png) **スプーフィングが許可さ** れていますか?] 列の [展開] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e594f-147">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="e594f-148">スプーフィングされた送信者を許可する場合は [ **はい]** を選択し、メッセージをスプーフィングとしてマークする場合は [ **いいえ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e594f-148">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="e594f-149">このアクションは、既定のフィッシング対策ポリシーまたはカスタムのマルウェア対策ポリシーによって制御されます (既定値は **[迷惑メールフォルダーにメッセージを移動** します)]。</span><span class="sxs-lookup"><span data-stu-id="e594f-149">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="e594f-150">詳細については、「 [フィッシング対策ポリシーのスプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-150">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![スプーフィングされた送信者のポップアップと、送信者がスプーフィングを許可するかどうかを示すスクリーンショット](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="e594f-152">表示される列と値については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="e594f-152">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="e594f-153">**偽装ユーザー**: スプーフィングされているユーザーアカウント。</span><span class="sxs-lookup"><span data-stu-id="e594f-153">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="e594f-154">これは、 `5322.From` 電子メールクライアントに表示される差出人アドレス (アドレスとも呼ばれます) のメッセージ送信者です。</span><span class="sxs-lookup"><span data-stu-id="e594f-154">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="e594f-155">このアドレスの有効性は、SPF によってチェックされません。</span><span class="sxs-lookup"><span data-stu-id="e594f-155">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="e594f-156">[**自分のドメイン**] タブの値に1つの電子メールアドレスが含まれている場合、または送信元の電子メールサーバーが複数のユーザーアカウントを偽装している場合は、複数のユーザーアカウントが含ま **れています。**</span><span class="sxs-lookup"><span data-stu-id="e594f-156">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="e594f-157">[ **外部ドメイン** ] タブの値には、完全な電子メールアドレスではなく、偽装されたユーザーのドメインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e594f-157">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="e594f-158">[**インフラストラクチャの送信**]: 送信元の電子メールサーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) にあるドメイン、またはソースに PTR レコードがない場合は ip アドレス。</span><span class="sxs-lookup"><span data-stu-id="e594f-158">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="e594f-159">メッセージソースとメッセージ送信者の詳細については、「 [電子メールメッセージの標準の概要](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-159">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="e594f-160">**メッセージ数**: 過去30日間に、指定したスプーフィングされた送信者または送信者を含む組織への送信インフラストラクチャからのメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="e594f-160">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="e594f-161">**ユーザーの苦情**: 過去30日間にこの送信者に対してユーザーが提出した苦情。</span><span class="sxs-lookup"><span data-stu-id="e594f-161">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="e594f-162">通常、苦情は Microsoft への迷惑メール送信の形式です。</span><span class="sxs-lookup"><span data-stu-id="e594f-162">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="e594f-163">**認証結果**: 次のいずれかの値です。</span><span class="sxs-lookup"><span data-stu-id="e594f-163">**Authentication result**: One of the following values:</span></span>

      - <span data-ttu-id="e594f-164">**成功**: 送信者が送信者の電子メール認証チェック (SPF または dkim) を通過しました。</span><span class="sxs-lookup"><span data-stu-id="e594f-164">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="e594f-165">**失敗** しました。送信者は EOP の認証チェックに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="e594f-165">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="e594f-166">**Unknown**: これらのチェックの結果は不明です。</span><span class="sxs-lookup"><span data-stu-id="e594f-166">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="e594f-167">**Decision set by**: 送信インフラストラクチャがユーザーのスプーフィングを許可されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="e594f-167">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="e594f-168">**スプーフィングインテリジェンスポリシー** (自動)</span><span class="sxs-lookup"><span data-stu-id="e594f-168">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="e594f-169">**管理者** (手動)</span><span class="sxs-lookup"><span data-stu-id="e594f-169">**Admin** (manual)</span></span>

   - <span data-ttu-id="e594f-170">**最終表示** 日: 偽装されたユーザーを含む送信元インフラストラクチャからメッセージが受信された最後の日付。</span><span class="sxs-lookup"><span data-stu-id="e594f-170">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="e594f-171">**スプーフィングが許可されますか?**: ここに表示される値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e594f-171">**Allowed to spoof?**: The values that you see here are:</span></span>

     - <span data-ttu-id="e594f-172">**Yes**: スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージが許可され、スプーフィングされた電子メールとして扱われることはありません。</span><span class="sxs-lookup"><span data-stu-id="e594f-172">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="e594f-173">**いいえ**: スプーフィングされたユーザーと送信元インフラストラクチャの組み合わせからのメッセージは、スプーフィングとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="e594f-173">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="e594f-174">このアクションは、既定のフィッシング対策ポリシーまたはカスタムのマルウェア対策ポリシーによって制御されます (既定値は **[迷惑メールフォルダーにメッセージを移動** します)]。</span><span class="sxs-lookup"><span data-stu-id="e594f-174">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="e594f-175">詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-175">See the next section for more information.</span></span>

     - <span data-ttu-id="e594f-176">**一部のユーザー** ([**自分のドメイン** ] タブのみ): 送信元のインフラストラクチャは複数のユーザーをスプーフィングしています。これには、一部のスプーフィングされたユーザーが許可されています。</span><span class="sxs-lookup"><span data-stu-id="e594f-176">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="e594f-177">特定のアドレスを表示するには、[ **詳細** ] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="e594f-177">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="e594f-178">ページの下部にある [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e594f-178">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="e594f-179">PowerShell を使用してスプーフィングされた送信者を管理する</span><span class="sxs-lookup"><span data-stu-id="e594f-179">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="e594f-180">スプーフィングインテリジェンスで許可された送信者と受信拒否送信者を表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="e594f-180">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="e594f-181">この例では、ドメイン内のユーザーのスプーフィングを許可されているすべての送信者に関する詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="e594f-181">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="e594f-182">構文およびパラメーターの詳細については、「 [get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-182">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="e594f-183">許可およびブロックされる送信者をスプーフィングインテリジェンスで構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e594f-183">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="e594f-184">検出されたスプーフィングされた送信者の現在のリストを取得するには、 **get-phishfilterpolicy** コマンドレットの出力を CSV ファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="e594f-184">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="e594f-185">CSV ファイルを編集して、 **SpoofedUser** (メールアドレス) および **allowedtospoof** (Yes または No) の値を追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="e594f-185">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="e594f-186">ファイルを保存し、ファイルを読み取って、コンテンツをという名前の変数として保存し `$UpdateSpoofedSenders` ます。</span><span class="sxs-lookup"><span data-stu-id="e594f-186">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="e594f-187">変数を使用し `$UpdateSpoofedSenders` て、スプーフィングインテリジェンスポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="e594f-187">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="e594f-188">構文およびパラメーターの詳細については、「 [get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-188">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="e594f-189">セキュリティ & コンプライアンスセンターを使用してスプーフィングインテリジェンスを構成する</span><span class="sxs-lookup"><span data-stu-id="e594f-189">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="e594f-190">スプーフィングインテリジェンスの構成オプションの詳細については、「 [フィッシング対策ポリシー」の「スプーフィング設定](set-up-anti-phishing-policies.md#spoof-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-190">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="e594f-191">スプーフィングインテリジェンスの設定は、既定のフィッシング対策ポリシーとカスタムポリシーで構成できます。</span><span class="sxs-lookup"><span data-stu-id="e594f-191">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="e594f-192">サブスクリプションに基づく手順については、以下のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-192">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="e594f-193">[EOP でフィッシング対策ポリシーを構成](configure-anti-phishing-policies-eop.md)します。</span><span class="sxs-lookup"><span data-stu-id="e594f-193">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="e594f-194">[Office 365 の Microsoft Defender でフィッシング対策ポリシーを構成](configure-atp-anti-phishing-policies.md)します。</span><span class="sxs-lookup"><span data-stu-id="e594f-194">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="e594f-195">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="e594f-195">How do you know these procedures worked?</span></span>

<span data-ttu-id="e594f-196">許可されている送信者とスプーフィングが許可されていない送信者、およびスプーフィングインテリジェンスの設定が構成済みであるというスプーフィングインテリジェンスが構成されていることを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e594f-196">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="e594f-197">[セキュリティ & コンプライアンスセンター] で、[**脅威の管理** ポリシーのスパム対策]、 \> **Policy** \> **Anti-spam** \> [**スプーフィングインテリジェンスポリシー** の選択] の \> 順 **に** 選択します \> 。 [**ドメイン** または **外部ドメイン**] タブを選択し、[**スプーフィングを許可する**] の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="e594f-197">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="e594f-198">PowerShell で、次のコマンドを実行して、許可されている、またはスプーフィングが許可されていない送信者を表示します。</span><span class="sxs-lookup"><span data-stu-id="e594f-198">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="e594f-199">PowerShell で次のコマンドを実行して、すべてのスプーフィングされた送信者の一覧を CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="e594f-199">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="e594f-200">セキュリティ & コンプライアンスセンターで、[**脅威管理** \> **ポリシー** \> の **フィッシング対策**] または [ **ATP のフィッシング対策**] に移動して、次のいずれかの手順を実行します。  </span><span class="sxs-lookup"><span data-stu-id="e594f-200">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="e594f-201">リストからポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="e594f-201">Select a policy from the list.</span></span> <span data-ttu-id="e594f-202">表示されたポップアップで、[ **スプーフ** ] セクションの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="e594f-202">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="e594f-203">[ **既定のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e594f-203">Click **Default policy**.</span></span> <span data-ttu-id="e594f-204">表示されたポップアップで、[ **スプーフ** ] セクションの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="e594f-204">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="e594f-205">Exchange Online PowerShell で、 \<Name\> Office365 フィッシング対策 Default またはカスタムポリシーの名前に置き換え、次のコマンドを実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="e594f-205">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="e594f-206">スプーフィングとフィッシングを管理するその他の方法</span><span class="sxs-lookup"><span data-stu-id="e594f-206">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="e594f-207">スプーフィングとフィッシングの保護については、入念に行ってください。</span><span class="sxs-lookup"><span data-stu-id="e594f-207">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="e594f-208">ここでは、ドメインをスプーフィングしている送信者をチェックして、組織の損害を防ぐ方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e594f-208">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="e594f-209">**スプーフィングメールレポート** を確認します。</span><span class="sxs-lookup"><span data-stu-id="e594f-209">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="e594f-210">このレポートは多くの場合、スプーフィングされた送信者を表示して管理するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="e594f-210">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="e594f-211">詳細については、「 [スプーフィング検出レポート](view-email-security-reports.md#spoof-detections-report)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-211">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="e594f-212">Sender Policy Framework (SPF) 構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="e594f-212">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="e594f-213">SPF の概要と SPF を迅速に構成する方法については、「[スプーフィングを防止するために Microsoft 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-213">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="e594f-214">Office 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="e594f-214">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="e594f-215">DomainKeys が識別されたメール (DKIM) 構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="e594f-215">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="e594f-216">SPF および DMARC に加えて DKIM を使用して、攻撃者がドメインから受信したように見えるメッセージを送信できないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e594f-216">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="e594f-217">DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="e594f-217">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="e594f-218">詳細については、「 [DKIM を使用して、Office 365 でカスタムドメインから送信される送信電子メールを検証する](use-dkim-to-validate-outbound-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-218">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="e594f-219">ドメインベースのメッセージ認証、レポート、および準拠 (DMARC) 構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="e594f-219">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="e594f-220">SPF および DKIM と共に DMARC を実装すると、メールのスプーフィングやフィッシングに対抗する追加の保護が得られます。</span><span class="sxs-lookup"><span data-stu-id="e594f-220">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="e594f-221">DMARC は、電子メールを受信するシステムが、ドメインから送信された SPF チェックまたは DKIM チェックに失敗したメッセージに対して、どのように対応するかを判断する際に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="e594f-221">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="e594f-222">詳細については、「 [USE DMARC to validate email In Office 365](use-dmarc-to-validate-email.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e594f-222">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
