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
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、特定のスプーフィング送信者を許可またはブロックできる Exchange Online Protection (EOP) でスプーフィング インテリジェンスについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bdc68f5a7e1f21969f5cd787cfdb0b58bc26cd83
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926914"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="39f91-103">EOP でスプーフィング インテリジェンスを構成する</span><span class="sxs-lookup"><span data-stu-id="39f91-103">Configure spoof intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="39f91-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="39f91-104">**Applies to**</span></span>
- [<span data-ttu-id="39f91-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="39f91-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="39f91-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="39f91-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="39f91-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="39f91-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="39f91-108">Exchange Online メールボックスのない Exchange Online またはスタンドアロンの Exchange Online Protection (EOP) 組織のメールボックスを持つ Microsoft 365 組織では、受信電子メール メッセージは 2018 年 10 月現在、EOP によるスプーフィングから自動的に保護されます。</span><span class="sxs-lookup"><span data-stu-id="39f91-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="39f91-109">EOP は、フィッシングに対する組織の全体的な防御の一環としてスプーフィング インテリジェンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="39f91-109">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="39f91-110">詳細については、「EOP でのスプーフィング防止 [保護」を参照してください](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="39f91-110">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="39f91-111">送信者が電子メール アドレスをスプーフィングすると、その送信者は組織のドメインの 1 つのユーザー、または組織に電子メールを送信する外部ドメインのユーザーのように見える。</span><span class="sxs-lookup"><span data-stu-id="39f91-111">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="39f91-112">送信者をスプーフィングしてスパムメールやフィッシングメールを送信する攻撃者をブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="39f91-112">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="39f91-113">しかし、正当な送信者がスプーフィングを行うシナリオがあります。</span><span class="sxs-lookup"><span data-stu-id="39f91-113">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="39f91-114">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="39f91-114">For example:</span></span>

- <span data-ttu-id="39f91-115">内部ドメインをスプーフィングする正当なシナリオ:</span><span class="sxs-lookup"><span data-stu-id="39f91-115">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="39f91-116">サードパーティの送信者は、ドメインを使用して、会社の投票のために自分の従業員にバルク メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="39f91-116">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="39f91-117">外部企業は、お客様に代わって広告や製品の更新プログラムを生成して送信します。</span><span class="sxs-lookup"><span data-stu-id="39f91-117">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="39f91-118">アシスタントは、組織内の別のユーザーのメールを定期的に送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39f91-118">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="39f91-119">内部アプリケーションが電子メール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="39f91-119">An internal application sends email notifications.</span></span>

- <span data-ttu-id="39f91-120">外部ドメインをスプーフィングする正当なシナリオ:</span><span class="sxs-lookup"><span data-stu-id="39f91-120">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="39f91-121">送信者はメーリングリスト (ディスカッション リストとも呼ばれる) に登録され、メーリングリストは元の送信者からメーリングリストのすべての参加者にメールを中継します。</span><span class="sxs-lookup"><span data-stu-id="39f91-121">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="39f91-122">外部企業は、別の会社に代わって電子メールを送信します (たとえば、自動レポートやサービスとしてのソフトウェア会社など)。</span><span class="sxs-lookup"><span data-stu-id="39f91-122">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="39f91-123">スプーフィング インテリジェンス(特に既定のスプーフィング インテリジェンス ポリシー)は、正当な送信者から送信されるスプーフィングされたメールが EOP スパム フィルターや外部メール システムに巻き込まれたり、スパムやフィッシング攻撃からユーザーを保護したりすることを防ごうのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="39f91-123">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="39f91-124">スプーフィング インテリジェンスは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織の Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell) で管理できます。</span><span class="sxs-lookup"><span data-stu-id="39f91-124">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="39f91-125">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="39f91-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="39f91-126"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="39f91-126">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="39f91-127">**[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。</span><span class="sxs-lookup"><span data-stu-id="39f91-127">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="39f91-128">フィッシング対策ページに直接 **移動するには** 、 を使用します <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="39f91-128">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="39f91-129">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39f91-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="39f91-130">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39f91-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="39f91-131">この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="39f91-131">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="39f91-132">スプーフィング インテリジェンス ポリシーを変更したり、スプーフィング インテリジェンスを有効または無効にするには、組織の管理またはセキュリティ管理者の役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="39f91-132">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="39f91-133">スプーフィング インテリジェンス ポリシーへの読み取り専用アクセスでは、グローバルリーダーまたはセキュリティ リーダーの役割グループのメンバー **である** 必要があります。</span><span class="sxs-lookup"><span data-stu-id="39f91-133">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="39f91-134">詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39f91-134">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="39f91-135">**注**:</span><span class="sxs-lookup"><span data-stu-id="39f91-135">**Notes**:</span></span>

  - <span data-ttu-id="39f91-136">Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="39f91-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="39f91-137">詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39f91-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="39f91-138">[Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。</span><span class="sxs-lookup"><span data-stu-id="39f91-138">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="39f91-139">スプーフィング インテリジェンスの推奨設定については [、「EOP の既定のフィッシング対策ポリシー設定」を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="39f91-139">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="39f91-140">セキュリティ コンプライアンス センター&を使用して、スプーフィングされた送信者を管理する</span><span class="sxs-lookup"><span data-stu-id="39f91-140">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="39f91-141">Microsoft 365 Enterprise E5 サブスクリプションを持っている場合、または Office 365 アドオン用の Microsoft Defender を個別に購入している場合は、スプーフィング インテリジェンス[](walkthrough-spoof-intelligence-insight.md)の分析情報を使用してドメインをスプーフィングしている送信者を管理できます。</span><span class="sxs-lookup"><span data-stu-id="39f91-141">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased a Microsoft Defender for Office 365 add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="39f91-142">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="39f91-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="39f91-143">[スパム対策 **の設定] ページで、[** 展開] アイコン ![ をクリックして [ス ](../../media/scc-expand-icon.png) プーフィング インテリジェンス ポリシー **] を展開します**。</span><span class="sxs-lookup"><span data-stu-id="39f91-143">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![スプーフィング インテリジェンス ポリシーの選択](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="39f91-145">次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="39f91-145">Make one of the following selections:</span></span>

   - <span data-ttu-id="39f91-146">**新しい送信者を確認する**</span><span class="sxs-lookup"><span data-stu-id="39f91-146">**Review new senders**</span></span>
   - <span data-ttu-id="39f91-147">**既に確認した送信者を表示する**</span><span class="sxs-lookup"><span data-stu-id="39f91-147">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="39f91-148">[表示 **されるユーザーのスプー** フィングを許可する送信者を決定する] フライアウトで、次のいずれかのタブを選択します。</span><span class="sxs-lookup"><span data-stu-id="39f91-148">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="39f91-149">**[ドメイン]:** 内部ドメイン内のユーザーをスプーフィングする送信者。</span><span class="sxs-lookup"><span data-stu-id="39f91-149">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="39f91-150">**外部ドメイン**: 外部ドメイン内のユーザーをスプーフィングする送信者。</span><span class="sxs-lookup"><span data-stu-id="39f91-150">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="39f91-151">[ス ![ プーフィングを ](../../media/scc-expand-icon.png) 許可する] **列の [展開] アイコンをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="39f91-151">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="39f91-152">ス **プーフィング** された送信者を許可するには [はい] を選択し、メッセージをスプーフィングとしてマークするには **[いいえ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="39f91-152">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="39f91-153">アクションは、既定のフィッシング対策ポリシーまたはカスタムのフィッシング対策ポリシーによって制御されます (既定値は [メッセージを迷惑メール フォルダーに移動する] **です**)。</span><span class="sxs-lookup"><span data-stu-id="39f91-153">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="39f91-154">詳細については、「フィッシング対策ポリシー [のスプーフィング設定」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="39f91-154">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![スプーフィングされた送信者の飛び出し、送信者がスプーフィングを許可されているかどうかを示すスクリーンショット](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="39f91-156">表示される列と値については、次の一覧で説明します。</span><span class="sxs-lookup"><span data-stu-id="39f91-156">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="39f91-157">**スプーフィング** されたユーザー: スプーフィングされているユーザー アカウント。</span><span class="sxs-lookup"><span data-stu-id="39f91-157">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="39f91-158">これは、メール クライアントに表示される差出人アドレス (アドレスとも呼ばれる) のメッセージ `5322.From` 送信者です。</span><span class="sxs-lookup"><span data-stu-id="39f91-158">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="39f91-159">このアドレスの有効性は SPF によってチェックされません。</span><span class="sxs-lookup"><span data-stu-id="39f91-159">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="39f91-160">[ドメイン **] タブ** で、値に 1 つの電子メール アドレスが含まれているか、送信元メール サーバーが複数のユーザー アカウントをスプーフィングしている場合は、複数のユーザー アカウントが **含まれる。**</span><span class="sxs-lookup"><span data-stu-id="39f91-160">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="39f91-161">[外部 **ドメイン] タブ** の値には、完全なメール アドレスではなく、スプーフィングされたユーザーのドメインが含まれる。</span><span class="sxs-lookup"><span data-stu-id="39f91-161">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="39f91-162">**送信インフラストラクチャ**: 送信元電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン。</span><span class="sxs-lookup"><span data-stu-id="39f91-162">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="39f91-163">送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは \<source IP\> /24 として識別されます (たとえば、192.168.100.100/24 など)。</span><span class="sxs-lookup"><span data-stu-id="39f91-163">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="39f91-164">メッセージ ソースとメッセージ送信者の詳細については、「電子メール メッセージ標準の概要 [」を参照してください](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。</span><span class="sxs-lookup"><span data-stu-id="39f91-164">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="39f91-165">**メッセージ数**: 過去 30 日以内に、指定されたスプーフィングされた送信者または送信者を含む、送信側インフラストラクチャから組織へのメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="39f91-165">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="39f91-166">**ユーザーからの苦情の** 数 : 過去 30 日以内にこの送信者に対してユーザーが申し立てした苦情。</span><span class="sxs-lookup"><span data-stu-id="39f91-166">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="39f91-167">苦情は通常、Microsoft への迷惑メール申請の形式です。</span><span class="sxs-lookup"><span data-stu-id="39f91-167">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="39f91-168">**認証結果**: 次のいずれかの値を指定します。</span><span class="sxs-lookup"><span data-stu-id="39f91-168">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="39f91-169">**合格**: 送信者が送信者の電子メール認証チェック (SPF または DKIM) を渡しました。</span><span class="sxs-lookup"><span data-stu-id="39f91-169">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="39f91-170">**Failed**: 送信者が EOP 送信者認証のチェックに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="39f91-170">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="39f91-171">**不明**: これらのチェックの結果は不明です。</span><span class="sxs-lookup"><span data-stu-id="39f91-171">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="39f91-172">**決定セット :** 送信インフラストラクチャがユーザーのスプーフィングを許可されるユーザーを示します。</span><span class="sxs-lookup"><span data-stu-id="39f91-172">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="39f91-173">**スプーフィング インテリジェンス ポリシー** (自動)</span><span class="sxs-lookup"><span data-stu-id="39f91-173">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="39f91-174">**管理者** (手動)</span><span class="sxs-lookup"><span data-stu-id="39f91-174">**Admin** (manual)</span></span>

   - <span data-ttu-id="39f91-175">**最後に** 表示される : スプーフィングされたユーザーを含む送信インフラストラクチャからメッセージを受信した最後の日付。</span><span class="sxs-lookup"><span data-stu-id="39f91-175">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="39f91-176">**スプーフィングを許可しますか。**: ここに表示される値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="39f91-176">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="39f91-177">**は** い : スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージは許可され、スプーフィングされた電子メールとして扱われるのではありません。</span><span class="sxs-lookup"><span data-stu-id="39f91-177">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="39f91-178">**いいえ**: スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージは、スプーフィングとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="39f91-178">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="39f91-179">アクションは、既定のフィッシング対策ポリシーまたはカスタムのフィッシング対策ポリシーによって制御されます (既定値は [メッセージを迷惑メール フォルダーに移動する] **です**)。</span><span class="sxs-lookup"><span data-stu-id="39f91-179">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="39f91-180">詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39f91-180">See the next section for more information.</span></span>

     - <span data-ttu-id="39f91-181">**一部** のユーザー (**[ドメイン** ] タブのみ): 送信インフラストラクチャは複数のユーザーをスプーフィングしています。スプーフィングされたユーザーの中には許可されているユーザーと許可されていないユーザーがあります。</span><span class="sxs-lookup"><span data-stu-id="39f91-181">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="39f91-182">[詳細] **タブを使用** して、特定のアドレスを表示します。</span><span class="sxs-lookup"><span data-stu-id="39f91-182">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="39f91-183">ページの下部にある [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39f91-183">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="39f91-184">PowerShell を使用してスプーフィングされた送信者を管理する</span><span class="sxs-lookup"><span data-stu-id="39f91-184">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="39f91-185">スプーフィング インテリジェンスで許可送信者とブロック送信者を表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="39f91-185">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="39f91-186">この例では、ドメイン内のユーザーをスプーフィングできるすべての送信者に関する詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="39f91-186">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="39f91-187">構文とパラメーターの詳細については [、「Get-PhishFilterPolicy」を参照してください](/powershell/module/exchange/get-phishfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="39f91-187">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="39f91-188">スプーフィング インテリジェンスで許可送信者とブロック送信者を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="39f91-188">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="39f91-189">**Get-PhishFilterPolicy** コマンドレットの出力を CSV ファイルに書き込み、検出されたスプーフィングされた送信者の現在のリストをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="39f91-189">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="39f91-190">CSV ファイルを編集して、スプーフィング **ユーザー** (電子メール アドレス) と **AllowedToSpoof (Yes** または No) の値を追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="39f91-190">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="39f91-191">ファイルを保存し、ファイルを読み取り、内容を次の名前の変数として格納します `$UpdateSpoofedSenders` 。</span><span class="sxs-lookup"><span data-stu-id="39f91-191">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="39f91-192">変数を `$UpdateSpoofedSenders` 使用してスプーフィング インテリジェンス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="39f91-192">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="39f91-193">構文とパラメーターの詳細については [、「Set-PhishFilterPolicy」を参照してください](/powershell/module/exchange/set-phishfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="39f91-193">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="39f91-194">コンプライアンス センターのセキュリティ &を使用してスプーフィング インテリジェンスを構成する</span><span class="sxs-lookup"><span data-stu-id="39f91-194">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="39f91-195">スプーフィング インテリジェンスの構成オプションについては、「フィッシング対策ポリシーのスプーフィング [設定」を参照してください](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="39f91-195">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="39f91-196">スプーフィング インテリジェンス設定は、既定のフィッシング対策ポリシーとカスタム ポリシーで構成できます。</span><span class="sxs-lookup"><span data-stu-id="39f91-196">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="39f91-197">サブスクリプションに基づく手順については、次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="39f91-197">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="39f91-198">[EOP でフィッシング対策ポリシーを構成します](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="39f91-198">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="39f91-199">[Microsoft Defender でフィッシング対策ポリシーを構成して、Office 365 に設定します](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="39f91-199">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="39f91-200">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="39f91-200">How do you know these procedures worked?</span></span>

<span data-ttu-id="39f91-201">スプーフィングが許可され、許可されていない送信者とスプーフィング インテリジェンスを構成し、スプーフィング インテリジェンス設定が構成されていることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="39f91-201">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="39f91-202">セキュリティ & コンプライアンス センターで、[脅威管理ポリシースパム対策] [スプーフィング インテリジェンス ポリシー] の [送信者を表示する] を選択し、[ドメインまたは外部ドメイン] タブを選択し、送信者の [スプーフィングを許可する \>  \>  \>  \>  \> **]** 値を確認します。</span><span class="sxs-lookup"><span data-stu-id="39f91-202">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="39f91-203">PowerShell で、次のコマンドを実行して、スプーフィングが許可されている送信者とスプーフィングが許可されていない送信者を表示します。</span><span class="sxs-lookup"><span data-stu-id="39f91-203">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="39f91-204">PowerShell で、次のコマンドを実行して、すべてのスプーフィングされた送信者の一覧を CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="39f91-204">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="39f91-205">[セキュリティ & コンプライアンス センター] で、[脅威管理ポリシー] [フィッシング対策] または [ATP フィッシング対策] に移動し、次のいずれかの手順 \>  \> を実行します。   </span><span class="sxs-lookup"><span data-stu-id="39f91-205">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="39f91-206">一覧からポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="39f91-206">Select a policy from the list.</span></span> <span data-ttu-id="39f91-207">表示されるフライアウトで、[スプーフィング] セクションの値を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="39f91-207">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="39f91-208">[既定 **のポリシー] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="39f91-208">Click **Default policy**.</span></span> <span data-ttu-id="39f91-209">表示されるフライアウトで、[スプーフィング] セクションの値を **確認** します。</span><span class="sxs-lookup"><span data-stu-id="39f91-209">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="39f91-210">Exchange Online PowerShell で、Office365 AntiPhish Default またはカスタム ポリシーの名前に置き換え、次のコマンドを実行して設定 \<Name\> を確認します。</span><span class="sxs-lookup"><span data-stu-id="39f91-210">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="39f91-211">スプーフィングとフィッシングを管理するその他の方法</span><span class="sxs-lookup"><span data-stu-id="39f91-211">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="39f91-212">スプーフィングとフィッシング保護について詳しく知る。</span><span class="sxs-lookup"><span data-stu-id="39f91-212">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="39f91-213">ドメインをスプーフィングする送信者を確認し、組織に損害を与えないよう、関連する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="39f91-213">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="39f91-214">スプーフィン **グ メール レポートを確認します**。</span><span class="sxs-lookup"><span data-stu-id="39f91-214">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="39f91-215">このレポートを頻繁に使用して、スプーフィングされた送信者を表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="39f91-215">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="39f91-216">詳細については、「スプーフィング [検出レポート」を参照してください](view-email-security-reports.md#spoof-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="39f91-216">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="39f91-217">送信者ポリシー フレームワーク (SPF) 構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="39f91-217">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="39f91-218">SPF の概要と SPF を迅速に構成する方法については、「[スプーフィングを防止するために Microsoft 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39f91-218">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="39f91-219">Office 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="39f91-219">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="39f91-220">DomainKeys Identified Mail (DKIM) 構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="39f91-220">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="39f91-221">SPF と DMARC に加えて DKIM を使用して、攻撃者が自分のドメインから送信されたようなメッセージを送信するのを防ぐ必要があります。</span><span class="sxs-lookup"><span data-stu-id="39f91-221">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="39f91-222">DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="39f91-222">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="39f91-223">詳細については [、「Use DKIM to validate outbound email](use-dkim-to-validate-outbound-email.md)from your custom domain in your custom domain in Office 365 .</span><span class="sxs-lookup"><span data-stu-id="39f91-223">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="39f91-224">ドメイン ベースのメッセージ認証、レポート、および準拠 (DMARC) 構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="39f91-224">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="39f91-225">SPF および DKIM と共に DMARC を実装すると、メールのスプーフィングやフィッシングに対抗する追加の保護が得られます。</span><span class="sxs-lookup"><span data-stu-id="39f91-225">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="39f91-226">DMARC は、電子メールを受信するシステムが、ドメインから送信された SPF チェックまたは DKIM チェックに失敗したメッセージに対して、どのように対応するかを判断する際に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="39f91-226">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="39f91-227">詳細については [、「Use DMARC to validate email in Office 365」を参照してください](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="39f91-227">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>