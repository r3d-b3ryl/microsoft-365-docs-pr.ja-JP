---
title: スプーフィング インテリジェンスを設定する
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
description: 管理者は、特定のスプーフィングされた送信者を許可またはブロックできる、Exchange Online Protection (EOP) のスプーフィング インテリジェンスについて学習することができます。
ms.openlocfilehash: 66cfc419c3e2f3a5dd8ad45cdb9fe651b613679b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826579"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="94f6b-103">EOP でスプーフィング インテリジェンスを構成する</span><span class="sxs-lookup"><span data-stu-id="94f6b-103">Configure spoof intelligence in EOP</span></span>

<span data-ttu-id="94f6b-104">Exchange Online にメールボックスがある Microsoft 365 組織や、Exchange Online のメールボックスを使用しないスタンドアロン Exchange Online Protection (EOP) 組織では、受信電子メール メッセージは、2018 年 10 月の EOP によりスプーフィングから自動的に保護されます。</span><span class="sxs-lookup"><span data-stu-id="94f6b-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="94f6b-105">EOP は、フィッシングに対する組織の全体的な防が層となって、スプーフィング インテリジェンスを使用します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="94f6b-106">詳細については [、EOP のスプーフィング対策保護を参照してください](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="94f6b-106">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="94f6b-107">送信者がメール アドレスを偽フィングする際、組織のドメインの 1 つに含むユーザー、または組織に電子メールを送信する外部ドメインのユーザーのように見えるように見える。</span><span class="sxs-lookup"><span data-stu-id="94f6b-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="94f6b-108">スパムまたはフィッシング メールを送信するために偽の送信者を偽プする攻撃者はブロックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94f6b-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="94f6b-109">ただし、正当な送信者がスプーフィングしている場合があります。</span><span class="sxs-lookup"><span data-stu-id="94f6b-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="94f6b-110">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="94f6b-110">For example:</span></span>

- <span data-ttu-id="94f6b-111">内部ドメインのスプーフィングに対する正当なシナリオ:</span><span class="sxs-lookup"><span data-stu-id="94f6b-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="94f6b-112">サード パーティの送信者は、ドメインを使って、会社のポーリングに対して自分の従業員にバルク メールを送信します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="94f6b-113">外部の会社が、ユーザーに代わって広告プログラムや製品更新プログラムを生成し、送信します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-113">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="94f6b-114">組織内の別のユーザーに対してアシスタントがメールを送信する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="94f6b-114">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="94f6b-115">内部アプリケーションが、電子メール通知を送信します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="94f6b-116">外部ドメインのスプーフィングに対する正当なシナリオ:</span><span class="sxs-lookup"><span data-stu-id="94f6b-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="94f6b-117">送信者が、メール リスト (ディスカッション リストとも呼ばれる) に登録され、その人は、元の送信者からの電子メールを、メール リストに登録されたすべての参加者に中継します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="94f6b-118">外部の会社が、他の会社 (自動化レポートやサービスとしてのソフトウェア会社など) の代わりに電子メールを送信する。</span><span class="sxs-lookup"><span data-stu-id="94f6b-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="94f6b-119">スプーフィング インテリジェンス(特にデフォルトのスプーフィング インテリジェンス ポリシー) は、正当な送信者によって送信されたなりすましメールが EOP スパム フィルターや外部電子メール システムで検出されないようにしながら、スパムやフィッシング攻撃からユーザーを保護できます。</span><span class="sxs-lookup"><span data-stu-id="94f6b-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="94f6b-120">スプーフィング インテリジェンスは、セキュリティ & コンプライアンス センター、または PowerShell (Exchange Online のメールボックスを持つ Microsoft 365 組織用の Exchange Online PowerShell、Exchange Online メールボックスを持たない組織の場合はスタンドアロン EOP PowerShell) で管理できます。</span><span class="sxs-lookup"><span data-stu-id="94f6b-120">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="94f6b-121">はじめに把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="94f6b-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="94f6b-122"><https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="94f6b-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="94f6b-123">**[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="94f6b-124">フィッシング **対策ページに直接移動するには** 、次の手順を使用します <https://protection.office.com/antiphishing> 。</span><span class="sxs-lookup"><span data-stu-id="94f6b-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="94f6b-125">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94f6b-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="94f6b-126">スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94f6b-126">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="94f6b-127">このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="94f6b-127">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="94f6b-128">スプーフィング インテリジェンス ポリシーを変更したり、スプーフィング インテリジェンスを有効または無効にしたりするには、次のいずれかの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="94f6b-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="94f6b-129">**組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。</span><span class="sxs-lookup"><span data-stu-id="94f6b-129">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="94f6b-130">**組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。</span><span class="sxs-lookup"><span data-stu-id="94f6b-130">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="94f6b-131">スプーフィング インテリジェンス ポリシーに読み取り専用アクセスするには、次の役割グループのいずれかのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="94f6b-131">For read-only access to the spoof intelligence policy, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="94f6b-132">[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。</span><span class="sxs-lookup"><span data-stu-id="94f6b-132">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="94f6b-133">[Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。</span><span class="sxs-lookup"><span data-stu-id="94f6b-133">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="94f6b-134">スプーフィング インテリジェンスについて推奨される設定については [、EOP の既定のフィッシング対策ポリシー設定を参照してください](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="94f6b-134">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="94f6b-135">セキュリティ コンプライアンス センターを&、スプーフィングされた送信者を管理する</span><span class="sxs-lookup"><span data-stu-id="94f6b-135">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="94f6b-136">Microsoft 365 Enterprise E5 サブスクリプションをお持つの場合、または Office 365 Advanced Threat Protection (Office 365 ATP) アドオンを別々に購入している場合は、なりすましインテリジェンス分析情報を使用してドメイン [偽の送信者を管理することもできます](walkthrough-spoof-intelligence-insight.md)。</span><span class="sxs-lookup"><span data-stu-id="94f6b-136">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased an Office 365 Advanced Threat Protection (Office 365 ATP) add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="94f6b-137">セキュリティ/コンプライアンス センターで、**[脅威の管理]** \> **[ポリシー]** \> **[迷惑メール対策]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-137">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="94f6b-138">[スパム対策 **の設定] ページで、[展開** ] アイコン ![ を ](../../media/scc-expand-icon.png) クリックして、ス **プーフィング インテリジェンス ポリシーを拡張します**。</span><span class="sxs-lookup"><span data-stu-id="94f6b-138">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![スプーフィング インテリジェンス ポリシーを選択する](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="94f6b-140">次のいずれかの選択を行います。</span><span class="sxs-lookup"><span data-stu-id="94f6b-140">Make one of the following selections:</span></span>

   - <span data-ttu-id="94f6b-141">**新しい送信者の確認**</span><span class="sxs-lookup"><span data-stu-id="94f6b-141">**Review new senders**</span></span>
   - <span data-ttu-id="94f6b-142">**既に確認済みの送信者を表示する**</span><span class="sxs-lookup"><span data-stu-id="94f6b-142">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="94f6b-143">表示される **ユーザーのポップアップを、これらの送信者** に対してスプーフィングが許可されているかどうかを決定するには、[次のいずれかのタブ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-143">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="94f6b-144">**Your Domains**: Senders spoofing users in your internal domains.</span><span class="sxs-lookup"><span data-stu-id="94f6b-144">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="94f6b-145">**外部ドメイン**: 外部ドメインのユーザースプーフィング ユーザー。</span><span class="sxs-lookup"><span data-stu-id="94f6b-145">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="94f6b-146">[ ![ スプー ](../../media/scc-expand-icon.png) フィングの **許可] 列の [展開] アイコンをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-146">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="94f6b-147">スプ **ー** フィングされた送信者を許可する場合は [はい] を、 **メッセージをスプー** フィングに指定するには [いいえ] を選んでください。</span><span class="sxs-lookup"><span data-stu-id="94f6b-147">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="94f6b-148">アクションは、既定のフィッシング対策ポリシー、またはカスタム ATP フィッシング対策ポリシーによって制御されます (既定値は **、[メッセージを迷惑メール フォルダーに移動] です**)。</span><span class="sxs-lookup"><span data-stu-id="94f6b-148">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="94f6b-149">詳細については、フィッ [シング対策ポリシーでのスプーフィング設定に関するトピックを参照してください](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="94f6b-149">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![なりすましたされた送信者のポップアップ、および送信者がスプーフィングを許可されているかどうかを示すスクリーンショット](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="94f6b-151">表示される列と値の一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-151">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="94f6b-152">**スプーフィング**されたユーザー: スプーフィングされているユーザー アカウント。</span><span class="sxs-lookup"><span data-stu-id="94f6b-152">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="94f6b-153">これは、電子メール クライアントに表示される差出人アドレス ( `5322.From` アドレスとも呼ばれる) のメッセージ送信者です。</span><span class="sxs-lookup"><span data-stu-id="94f6b-153">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="94f6b-154">このアドレスの有効性は SPF によってチェックされません。</span><span class="sxs-lookup"><span data-stu-id="94f6b-154">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="94f6b-155">[Your **Domains] タブでは** 、値に単一のメール アドレスが含まれます。または、ソース メール サーバーが複数のユーザー アカウントをスプーフィングしている場合は、複数 **の電子メール アドレスが含まれます**。</span><span class="sxs-lookup"><span data-stu-id="94f6b-155">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="94f6b-156">この値 **には、外部ドメイン** の完全な電子メール アドレスは含まれるのでない、スプーフィングされたユーザーのドメインが含まれます。</span><span class="sxs-lookup"><span data-stu-id="94f6b-156">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="94f6b-157">**Sending Infrastructure**(送信元インフラストラクチャ): 送信元の電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) にあるドメイン、またはソースに PTR レコードがない場合は IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="94f6b-157">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="94f6b-158">メッセージの送信元とメッセージ送信者の詳細については、「電子メール [メッセージの基準の概要」を参照してください](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。</span><span class="sxs-lookup"><span data-stu-id="94f6b-158">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="94f6b-159">**メッセージ数**: 過去 30 日間の指定されたなりすき送信者または送信者が含まれる、送信インフラストラクチャから組織内へのメッセージの数。</span><span class="sxs-lookup"><span data-stu-id="94f6b-159">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="94f6b-160">**ユーザーの補足の数**: 過去 30 日以内にユーザーによって行われた相割合</span><span class="sxs-lookup"><span data-stu-id="94f6b-160">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="94f6b-161">通常、補足は Microsoft への迷惑メールの提出の形式です。</span><span class="sxs-lookup"><span data-stu-id="94f6b-161">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="94f6b-162">**認証の結果**: 次のいずれかの値です。</span><span class="sxs-lookup"><span data-stu-id="94f6b-162">**Authentication result**: One of the following values:</span></span>

      - <span data-ttu-id="94f6b-163">**Passed:** 送信者が送信者のメール認証チェック (SPF または DKIM) をパスしました。</span><span class="sxs-lookup"><span data-stu-id="94f6b-163">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="94f6b-164">**失敗**: 送信者が EOP の送信者認証チェックに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="94f6b-164">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="94f6b-165">**Unknown:** これらのチェックの結果が不明です。</span><span class="sxs-lookup"><span data-stu-id="94f6b-165">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="94f6b-166">**Decision set by:** 送信元インフラストラクチャがユーザーのスプーフィングを許可されているかどうかを決定したユーザーを示します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-166">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="94f6b-167">**スプーフィング インテリジェンス ポリシー** (自動)</span><span class="sxs-lookup"><span data-stu-id="94f6b-167">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="94f6b-168">**管理者** (手動)</span><span class="sxs-lookup"><span data-stu-id="94f6b-168">**Admin** (manual)</span></span>

   - <span data-ttu-id="94f6b-169">**最後の確認日時**: スプーフィングされたユーザーを含む送信インフラストラクチャからメッセージを受信した日付です。</span><span class="sxs-lookup"><span data-stu-id="94f6b-169">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="94f6b-170">**スプーフィングは許可されていますか?**:次のような値があります。</span><span class="sxs-lookup"><span data-stu-id="94f6b-170">**Allowed to spoof?**: The values that you see here are:</span></span>

     - <span data-ttu-id="94f6b-171">**はい**: スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージは許可され、スプーフィングされたメールとしては処理されません。</span><span class="sxs-lookup"><span data-stu-id="94f6b-171">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="94f6b-172">**い**いえ: スプーフィングされたユーザーと送信インフラストラクチャの組み合わせからのメッセージは、スプーフィング済みとしてマークされます。</span><span class="sxs-lookup"><span data-stu-id="94f6b-172">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="94f6b-173">アクションは、既定のフィッシング対策ポリシー、またはカスタム ATP フィッシング対策ポリシーによって制御されます (既定値は **、[メッセージを迷惑メール フォルダーに移動] です**)。</span><span class="sxs-lookup"><span data-stu-id="94f6b-173">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="94f6b-174">詳細については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94f6b-174">See the next section for more information.</span></span>

     - <span data-ttu-id="94f6b-175">**一部の** ユーザー **([ドメイン]** タブのみ): 送信インフラストラクチャは複数のユーザーにスプーフィングを行う状態になり、スプーフィングされたユーザーの一部は許可され、他のユーザーは許可されません。</span><span class="sxs-lookup"><span data-stu-id="94f6b-175">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="94f6b-176">特定のアドレス **を確認するには** 、[詳細] タブを使用します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-176">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="94f6b-177">ページの下部にある [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94f6b-177">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="94f6b-178">PowerShell を使用して、スプーフィングされた送信者を管理する</span><span class="sxs-lookup"><span data-stu-id="94f6b-178">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="94f6b-179">スプーフィング インテリジェンスで許可またはブロックする差出人を表示するには、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-179">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="94f6b-180">この例では、ドメイン内のユーザーへのスプーフィングが許可されているすべての送信者に関する詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-180">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="94f6b-181">構文およびパラメーターの詳細については [、「Get-PhishFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="94f6b-181">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="94f6b-182">スプーフィング インテリジェンスで許可およびブロックする差出人を構成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-182">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="94f6b-183">**Get-PhishFilterPolicy**コマンドレットの出力を CSV ファイルに書き込み、検出されたスプーフィングされた送信者の現在のリストをキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="94f6b-183">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="94f6b-184">CSV ファイルを編集して **、SpoofedUser** (メール アドレス) と **AllowedToSpoof** (Yes または No) の値を追加または変更します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-184">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="94f6b-185">ファイルを保存してファイルを読み取り、その内容を次の名前の変数として保存します `$UpdateSpoofedSenders` 。</span><span class="sxs-lookup"><span data-stu-id="94f6b-185">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="94f6b-186">この変数を `$UpdateSpoofedSenders` 使用して、スプーフィング インテリジェンス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-186">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="94f6b-187">構文およびパラメーターの詳細については [、「Set-PhishFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)。</span><span class="sxs-lookup"><span data-stu-id="94f6b-187">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="94f6b-188">セキュリティ センター コンプライアンス センター&、スプーフィング インテリジェンスを構成する</span><span class="sxs-lookup"><span data-stu-id="94f6b-188">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="94f6b-189">スプーフィング インテリジェンスの構成オプションは、フィッシ [ング対策ポリシーのスプーフィング対策設定で説明されています](set-up-anti-phishing-policies.md#spoof-settings)。</span><span class="sxs-lookup"><span data-stu-id="94f6b-189">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="94f6b-190">スプーフィング インテリジェンス設定は、既定のフィッシング対策ポリシーで、さらにカスタム ポリシーで構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="94f6b-190">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="94f6b-191">サブスクリプションに基づく手順については、次のいずれかのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="94f6b-191">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="94f6b-192">[EOP でフィッシング対策ポリシーを構成する](configure-anti-phishing-policies-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="94f6b-192">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="94f6b-193">[Microsoft 365 で ATP フィッシング対策ポリシーを構成します](configure-atp-anti-phishing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="94f6b-193">[Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="94f6b-194">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="94f6b-194">How do you know these procedures worked?</span></span>

<span data-ttu-id="94f6b-195">スプーフィングが許可されている送信者およびスプーフィングが許可されていない送信者に対して、スプーフィング インテリジェンスを構成したことを確認するには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-195">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="94f6b-196">セキュリティ & コンプライアンス センターで、脅威管理ポリシーのスパム対策ポリシーに移動**し、[** なりすでに確認した送信者に通知する] を選択し、[既に \> **Policy** \> **Anti-spam** \> **Spoof intelligence policy** \> **Show me senders I already reviewed** \> **[ドメインまたは外部ドメイン]\*\*\*\*External Domains\*\*\*\*Allowed to spoof?** タブを選択した場合は、[スプーフィングの許可] を確認します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-196">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="94f6b-197">PowerShell で次のコマンドを実行して、許可される送信者とスプーフィングが許可されない送信者を表示します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-197">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="94f6b-198">PowerShell で次のコマンドを実行して、スプーフィングされたすべての送信者の一覧を CSV ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="94f6b-198">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="94f6b-199">Security & コンプライアンス センターで、**脅威管理**ポリシーのフィッシング対策または ATP フィッシング対策に \> **Policy** \> **Anti-phishing\*\*\*\*移動**し、次のいずれかの手順を実行します。  </span><span class="sxs-lookup"><span data-stu-id="94f6b-199">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="94f6b-200">一覧からポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-200">Select a policy from the list.</span></span> <span data-ttu-id="94f6b-201">表示されるポップアップで、Spoof セクションの値 **を確認** します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-201">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="94f6b-202">[既定 **のポリシー] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="94f6b-202">Click **Default policy**.</span></span> <span data-ttu-id="94f6b-203">表示されるポップアップで、Spoof セクションの値 **を確認** します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-203">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="94f6b-204">Exchange Online PowerShell で \<Name\> 、Office365 AntiPhish Default またはカスタム ポリシーの名前に置き換え、次のコマンドを実行して設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-204">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="94f6b-205">スプーフィングとフィッシングを管理するその他の方法</span><span class="sxs-lookup"><span data-stu-id="94f6b-205">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="94f6b-206">スプーフィングとフィッシング対策について詳しい説明を提供する。</span><span class="sxs-lookup"><span data-stu-id="94f6b-206">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="94f6b-207">ここでは、ドメインをなりすますようになり、組織を損な化しないようにする次のような関連する方法があります。</span><span class="sxs-lookup"><span data-stu-id="94f6b-207">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="94f6b-208">なりすみ **メッセージのレポートを確認します**。</span><span class="sxs-lookup"><span data-stu-id="94f6b-208">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="94f6b-209">このレポートは、多くの場合、スプーフィングされた送信者を表示して管理できます。</span><span class="sxs-lookup"><span data-stu-id="94f6b-209">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="94f6b-210">詳細については、「なり [すみ」レポートを参照してください](view-email-security-reports.md#spoof-detections-report)。</span><span class="sxs-lookup"><span data-stu-id="94f6b-210">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="94f6b-211">Sender Policy Framework (SPF) の構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-211">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="94f6b-212">SPF の概要と SPF を迅速に構成する方法については、「[スプーフィングを防止するために Microsoft 365 で SPF を設定する](set-up-spf-in-office-365-to-help-prevent-spoofing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94f6b-212">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="94f6b-213">Office 365 における SPF の使用方法についての詳細や、ハイブリッド展開などの非標準の展開のトラブルシューティングについては、「[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)」をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="94f6b-213">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="94f6b-214">DomainKeys Identified Mail (DKIM) の構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-214">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="94f6b-215">ドメインから送信されたように見えるメッセージを攻撃者が送信するのを防ぐには、SPF と DMARC に加え、DKIM を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94f6b-215">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="94f6b-216">DKIM では、電子メール メッセージのメッセージ ヘッダー内にデジタル署名を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="94f6b-216">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="94f6b-217">詳細については [、「DKIM を使用して、Office 365 のカスタム ドメインから送信される送信電子メールを検証する」を参照してください](use-dkim-to-validate-outbound-email.md)。</span><span class="sxs-lookup"><span data-stu-id="94f6b-217">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="94f6b-218">ドメイン ベースのメッセージ認証、レポート、および Conformance (DMARC) の構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="94f6b-218">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="94f6b-219">SPF および DKIM と共に DMARC を実装すると、メールのスプーフィングやフィッシングに対抗する追加の保護が得られます。</span><span class="sxs-lookup"><span data-stu-id="94f6b-219">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="94f6b-220">DMARC は、電子メールを受信するシステムが、ドメインから送信された SPF チェックまたは DKIM チェックに失敗したメッセージに対して、どのように対応するかを判断する際に役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="94f6b-220">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="94f6b-221">詳細については [、「DMARC を使用して、Office 365 で電子メールを検証する」を参照してください](use-dmarc-to-validate-email.md)。</span><span class="sxs-lookup"><span data-stu-id="94f6b-221">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
