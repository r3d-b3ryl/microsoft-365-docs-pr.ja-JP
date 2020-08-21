---
title: フィッシング詐欺対策ポリシー
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) と Office 365 Advanced Threat Protection (Office 365 ATP) で使用可能なフィッシング対策ポリシーについて学習できます。
ms.openlocfilehash: f671588ff4232c6ca1c1342475f48802bf1a0076
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825103"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a><span data-ttu-id="b6ce8-103">Microsoft 365 でのフィッシング対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="b6ce8-103">Anti-phishing policies in Microsoft 365</span></span>

<span data-ttu-id="b6ce8-104">フィッシング対策保護設定を構成するポリシーは、Exchange Online メールボックスを持つ Microsoft 365 組織、Exchange Online メールボックスを含まないスタンドアロン Exchange Online Protection (EOP) 組織、および Office 365 Advanced Threat Protection (Office 365 ATP) 組織で使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-104">Policies to configure anti-phishing protection settings are available in Microsoft 365 organizations with Exchange Online mailboxes, standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, and Office 365 Advanced Threat Protection (Office 365 ATP) organizations.</span></span>

<span data-ttu-id="b6ce8-105">ATP フィッシング対策ポリシーは、365 ATP をOffice組織でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-105">ATP anti-phishing policies are only available in organizations that have Office 365 ATP.</span></span> <span data-ttu-id="b6ce8-106">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-106">For example:</span></span>

- <span data-ttu-id="b6ce8-107">Microsoft 365 Enterprise E5、Microsoft 365 Education A5 など</span><span class="sxs-lookup"><span data-stu-id="b6ce8-107">Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.</span></span>
- [<span data-ttu-id="b6ce8-108">Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b6ce8-108">Microsoft 365 Enterprise</span></span>](https://www.microsoft.com/microsoft-365/enterprise/home)
- [<span data-ttu-id="b6ce8-109">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="b6ce8-109">Microsoft 365 Business</span></span>](https://www.microsoft.com/microsoft-365/business)
- [<span data-ttu-id="b6ce8-110">Officeとしての 365 ATP</span><span class="sxs-lookup"><span data-stu-id="b6ce8-110">Office 365 ATP as an add-on</span></span>](https://products.office.com/exchange/advance-threat-protection)

<span data-ttu-id="b6ce8-111">その他すべての組織にはフィッシング対策ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-111">All other organizations have anti-phishing policies.</span></span>

<span data-ttu-id="b6ce8-112">フィッシング対策ポリシーと ATP フィッシング対策ポリシーは、次の表でまとまりまい、大まかな違いを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-112">The high-level differences between anti-phishing policies and ATP anti-phishing policies are described in the following table:</span></span>

****

|<span data-ttu-id="b6ce8-113">機能</span><span class="sxs-lookup"><span data-stu-id="b6ce8-113">Feature</span></span>|<span data-ttu-id="b6ce8-114">フィッシング詐欺対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="b6ce8-114">Anti-phishing policies</span></span>|<span data-ttu-id="b6ce8-115">ATP フィッシング対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="b6ce8-115">ATP anti-phishing policies</span></span>|
|---|:---:|:---:|
|<span data-ttu-id="b6ce8-116">自動作成される既定のポリシー</span><span class="sxs-lookup"><span data-stu-id="b6ce8-116">Automatically created default policy</span></span>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b6ce8-119">カスタム ポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="b6ce8-119">Create custom policies</span></span>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b6ce8-122">ポリシー設定<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="b6ce8-122">Policy settings<sup>\*</sup></span></span>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b6ce8-125">偽装の設定</span><span class="sxs-lookup"><span data-stu-id="b6ce8-125">Impersonation settings</span></span>||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b6ce8-127">スプーフィング設定</span><span class="sxs-lookup"><span data-stu-id="b6ce8-127">Spoof settings</span></span>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="b6ce8-130">高度なフィッシングしきい値</span><span class="sxs-lookup"><span data-stu-id="b6ce8-130">Advanced phishing thresholds</span></span>||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<span data-ttu-id="b6ce8-132"><sup>\*</sup> 既定のポリシーでは、ポリシーの名前と説明は読み取り専用です (説明は空白)、ポリシーの適用先は指定できません (既定のポリシーはすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-132"><sup>\*</sup> In the default policy, the policy name and description are read-only (the description is blank), and you can't specify who the policy applies to (the default policy applies to all recipients).</span></span>

<span data-ttu-id="b6ce8-133">フィッシング対策ポリシーを構成するには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-133">To configure anti-phishing policies, see the following articles:</span></span>

- [<span data-ttu-id="b6ce8-134">EOP でフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="b6ce8-134">Configure anti-phishing policies in EOP</span></span>](configure-anti-phishing-policies-eop.md)

- [<span data-ttu-id="b6ce8-135">Microsoft 365 で ATP フィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="b6ce8-135">Configure ATP anti-phishing policies in Microsoft 365</span></span>](configure-atp-anti-phishing-policies.md)

<span data-ttu-id="b6ce8-136">この記事の残りの部分では、フィッシング対策ポリシーと ATP フィッシング対策ポリシーで使用可能な設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-136">The rest of this article describes the settings that are available in anti-phishing policies and ATP anti-phishing policies.</span></span>

## <a name="policy-settings"></a><span data-ttu-id="b6ce8-137">ポリシー設定</span><span class="sxs-lookup"><span data-stu-id="b6ce8-137">Policy settings</span></span>

<span data-ttu-id="b6ce8-138">フィッシング対策ポリシーと ATP フィッシング対策ポリシーでは、次のポリシー設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-138">The following policy settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="b6ce8-139">**Name**: 既定のフィッシング対策ポリシーの名前は変更できませんが、作成するカスタム ポリシーの名前や名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-139">**Name**: You can't rename the default anti-phishing policy, but you can name and rename custom policies that you create.</span></span>

- <span data-ttu-id="b6ce8-140">**説明** 既定のフィッシング対策ポリシーに説明を追加することはできませんが、作成するカスタム ポリシーの説明を追加および変更できます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-140">**Description** You can't add a description to the default anti-phishing policy, but you can add and change the description for custom policies that you create.</span></span>

- <span data-ttu-id="b6ce8-141">**適用先**: フィッシング対策ポリシーが適用される内部受信者を識別します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-141">**Applied to**: Identifies internal recipients that the anti-phishing policy applies to.</span></span> <span data-ttu-id="b6ce8-142">この値は、カスタム ポリシーでは必須ですが、既定のポリシーでは使用できません (既定のポリシーはすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-142">This value is required in custom policies, and not available in the default policy (the default policy applies to all recipients).</span></span>

  <span data-ttu-id="b6ce8-143">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-143">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="b6ce8-144">同じ条件や例外に複数の値がある場合、OR ロジック (たとえば、_\<recipient1\>_ または _\<recipient2\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-144">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="b6ce8-145">a別の条件や例外がある場合は AND ロジック (たとえば、_\<recipient1\>_ かつ _\<member of group 1\>_) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-145">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

  - <span data-ttu-id="b6ce8-146">**受信者は次**のとおりです。組織内の 1 つ以上のメールボックス、メール ユーザー、メール連絡先。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-146">**Recipient is**: One or more mailboxes, mail users, or mail contacts in your organization.</span></span>
  - <span data-ttu-id="b6ce8-147">**受信者は [** 組織内の 1 つ以上のグループ] のメンバーです。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-147">**Recipient is a member of**: One or more groups in your organization.</span></span>
  - <span data-ttu-id="b6ce8-148">**受信者のドメインが、Microsoft**365 で構成済みの承認済みドメインの 1 つ以上です。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-148">**The recipient domain is**: One or more of the configured accepted domains in Microsoft 365.</span></span>

  - <span data-ttu-id="b6ce8-149">**ただし、適用**する場合は、ルールで例外が発生します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-149">**Except when**: Exceptions for the rule.</span></span> <span data-ttu-id="b6ce8-150">設定と動作は、次の条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-150">The settings and behavior are exactly like the conditions:</span></span>

    - <span data-ttu-id="b6ce8-151">**受信者が**</span><span class="sxs-lookup"><span data-stu-id="b6ce8-151">**Recipient is**</span></span>
    - <span data-ttu-id="b6ce8-152">**受信者が次のメンバーの場合**</span><span class="sxs-lookup"><span data-stu-id="b6ce8-152">**Recipient is a member of**</span></span>
    - <span data-ttu-id="b6ce8-153">**受信者のドメインが次である場合**</span><span class="sxs-lookup"><span data-stu-id="b6ce8-153">**The recipient domain is**</span></span>

## <a name="spoof-settings"></a><span data-ttu-id="b6ce8-154">スプーフィング設定</span><span class="sxs-lookup"><span data-stu-id="b6ce8-154">Spoof settings</span></span>

<span data-ttu-id="b6ce8-155">スプーフィングは、電子メール メッセージの差出人アドレス (電子メール クライアントに表示される送信者アドレス) が、電子メール ソースのドメインと一致しない場合です。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-155">Spoofing is when the From address in an email message (the sender address that's show in email clients) doesn't match the domain of the email source.</span></span> <span data-ttu-id="b6ce8-156">スプーフィングの詳細については [、Microsoft 365 のスプーフィング対策保護を参照してください](anti-spoofing-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-156">For more information about spoofing, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="b6ce8-157">フィッシング対策ポリシーと ATP フィッシング対策ポリシーでは、次のスプーフィング設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-157">The following spoof settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="b6ce8-158">**スプーフィング対策保護**: スプーフィング対策保護を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-158">**Anti-spoofing protection**: Enables or disables anti-spoofing protection.</span></span> <span data-ttu-id="b6ce8-159">この機能は有効のままにしておき、お勧めします。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-159">We recommend that you leave it enabled.</span></span> <span data-ttu-id="b6ce8-160">スプーフ **ィング インテリジェンス ポリシーを使用して、** 特定のスプーフィングされた内部および外部の送信者を許可または禁止します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-160">You use the **spoof intelligence policy** to allow or block specific spoofed internal and external senders.</span></span> <span data-ttu-id="b6ce8-161">詳細については、「[Microsoft 365 でのスプーフィング インテリジェンスの構成](learn-about-spoof-intelligence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-161">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="b6ce8-162">スプーフィング設定は、既定の EOP フィッシング対策ポリシー、およびユーザーが作成した新しいカスタムフィッシング対策ポリシーまたは ATP フィッシング対策ポリシーで、既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-162">Spoof settings are enabled by default in the default anti-phishing policy in EOP, the default ATP anti-phishing policy, and in new custom anti-phishing policies or ATP anti-phishing policies that you create.</span></span> <br/><br/> <span data-ttu-id="b6ce8-163">MX レコードが Microsoft 365 をポイントしていない場合は、スプーフィング対策保護を無効にする必要がありです。コネクタの拡張フィルター処理を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-163">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="b6ce8-164">手順については [、「Exchange Online のコネクタ用の拡張フィルター処理」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-164">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

  <span data-ttu-id="b6ce8-165">ブロックされるスプーフィングされた送信者からのメッセージの場合は、メッセージに対して実行するアクションも指定できます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-165">For messages from blocked spoofed senders, you can also specify the action to take on the messages:</span></span>

  - <span data-ttu-id="b6ce8-166">**メッセージを [迷惑メール] フォルダーに**移動します。これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-166">**Move message to Junk Email folder**: This is the default value.</span></span> <span data-ttu-id="b6ce8-167">メッセージはメールボックスに配信され、[迷惑メール] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-167">The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="b6ce8-168">Exchange Online では、メールボックスで迷惑メール ルールが有効になっている場合、メッセージは [迷惑メール] フォルダーに移動されます (既定では有効)。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-168">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="b6ce8-169">詳細については [、「Microsoft 365 の Exchange Online メールボックスで迷惑メール設定を構成する」を参照してください](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-169">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="b6ce8-170">**メッセージを検疫**: メッセージを目的の受信者に代わって検疫に送信します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-170">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="b6ce8-171">検疫の詳細については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-171">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="b6ce8-172">Microsoft 365 の検疫</span><span class="sxs-lookup"><span data-stu-id="b6ce8-172">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="b6ce8-173">Microsoft 365 の管理者として検疫済みメッセージとファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="b6ce8-173">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="b6ce8-174">Microsoft 365 のユーザーとして検疫済みメッセージを検索して解放する</span><span class="sxs-lookup"><span data-stu-id="b6ce8-174">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- <span data-ttu-id="b6ce8-175">**認証されていない送信者**: 次のセクションの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-175">**Unauthenticated Sender**: See the description in the next section.</span></span>

### <a name="unauthenticated-sender"></a><span data-ttu-id="b6ce8-176">認証されていない送信者</span><span class="sxs-lookup"><span data-stu-id="b6ce8-176">Unauthenticated Sender</span></span>

<span data-ttu-id="b6ce8-177">認証されていない送信者識別は、前のセクションで説明したフィ[Spoof settings](#spoof-settings)ッシング対策ポリシーと ATP フィッシング対策ポリシーで使用できるスプーフィング設定の一部です。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-177">Unauthenticated sender identification is part of the [Spoof settings](#spoof-settings) that are available in anti-phishing policies and ATP anti-phishing policies as described in the previous section.</span></span>

<span data-ttu-id="b6ce8-178">[ **認証されていない送信者]** 設定では、Outlook での未識別の送信者識別情報が有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-178">The **Unauthenticated Sender** setting enables or disables unidentified sender identification in Outlook.</span></span> <span data-ttu-id="b6ce8-179">具体的には次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-179">Specifically:</span></span>

- <span data-ttu-id="b6ce8-180">メッセージが SPF チェックまたは DKIM チェックに合格せず、メッセージが DMARC**and**または複合認証に合格しない場合には、疑問符 (?) が送信者の[写真に追加されます](email-validation-and-authentication.md#composite-authentication)。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-180">A question mark (?) is added to the sender's photo if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>

- <span data-ttu-id="b6ce8-181">経由のタグ (michelle@fabrikam.com <u>経由</u> の chris@contoso.com) は、From アドレスのドメイン (電子メール クライアントに表示されるメッセージ送信者) が、DKIM 署名または MAIL FROM アドレスのドメインと異なる場合 **に追加** されます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-181">The via tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) is added if the domain in the From address (the message sender that's displayed in email clients) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="b6ce8-182">これらの住所について詳しくは、電子 [メール メッセージ標準の概要をご覧ください。](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span><span class="sxs-lookup"><span data-stu-id="b6ce8-182">For more information about these addresses, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span></span>

<span data-ttu-id="b6ce8-183">特定の送信者からのメッセージにこれらの識別子が追加されるのを防ぐには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-183">To prevent these identifiers from being added to messages from specific senders, you have the following options:</span></span>

- <span data-ttu-id="b6ce8-184">なりすみインテリジェンス ポリシーで送信者にスプーフィングを許可します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-184">Allow the sender to spoof in the spoof intelligence policy.</span></span> <span data-ttu-id="b6ce8-185">手順については [、「Microsoft 365 でのスプーフィング インテリジェンスを構成する」を参照してください](learn-about-spoof-intelligence.md)。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-185">For instructions, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

- <span data-ttu-id="b6ce8-186">[送信者ドメインのメール](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) 認証を構成します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-186">[Configure email authentication](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) for the sender domain.</span></span>
  
  - <span data-ttu-id="b6ce8-187">送信者の写真の疑問符については、SPF または DKIM が最も重要です。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-187">For the question mark in the sender's photo, SPF or DKIM are the most important.</span></span>
  - <span data-ttu-id="b6ce8-188">Via the via tag, confirm the domain in the DKIM signature or the **MAIL FROM** address matches (or a subdomain of) the domain in the From address.</span><span class="sxs-lookup"><span data-stu-id="b6ce8-188">For the via tag, confirm the domain in the DKIM signature or the **MAIL FROM** address matches (or is a subdomain of) the domain in the From address.</span></span>

<span data-ttu-id="b6ce8-189">詳細については、「Outlook.com および [Outlook on the web の不審なメッセージを特定する」を参照してください。](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span><span class="sxs-lookup"><span data-stu-id="b6ce8-189">For more information, see [Identify suspicious messages in Outlook.com and Outlook on the web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span></span>

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="b6ce8-190">ATP フィッシング対策ポリシーの排他的設定</span><span class="sxs-lookup"><span data-stu-id="b6ce8-190">Exclusive settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="b6ce8-191">ここでは、ATP フィッシング対策ポリシーでのみ使用可能なポリシー設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-191">This section describes the policy settings that are only available in ATP anti-phishing policies.</span></span>

> [!NOTE]
> <span data-ttu-id="b6ce8-192">既定では、既定のポリシーであっても、ATP 排他的設定は構成され、有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-192">By default, the ATP exclusive settings are not configured or turned on, even in the default policy.</span></span> <span data-ttu-id="b6ce8-193">これらの機能を利用するには、既定の ATP フィッシング対策ポリシーで有効化および構成するか、カスタムの ATP フィッシング対策ポリシーを作成して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-193">To take advantage of these features, you need to enable and configure them in the default ATP anti-phishing policy, or create and configure custom ATP anti-phishing policies.</span></span>

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="b6ce8-194">ATP フィッシング対策ポリシーの偽装設定</span><span class="sxs-lookup"><span data-stu-id="b6ce8-194">Impersonation settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="b6ce8-195">偽装とは、メッセージ内の送信者または送信者のメール ドメインが実際の送信者やドメインと似ていない場合のことです。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-195">Impersonation is where the sender or the sender's email domain in a message looks similar to a real sender or domain:</span></span>

- <span data-ttu-id="b6ce8-196">ドメイン contoso.com のなりすまし例は óntoso.com です。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-196">An example impersonation of the domain contoso.com is ćóntoso.com.</span></span>
- <span data-ttu-id="b6ce8-197">ユーザー michelle@contoso.com のなりすまし例は、michele@contoso.com です。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-197">An example impersonation of the user michelle@contoso.com is michele@contoso.com.</span></span>

<span data-ttu-id="b6ce8-198">なりすましされたドメインは、受信者を欺くことを目的とする場合を除いて、正規のドメイン（登録済みドメイン、構成済みの電子メール認証レコードなど）と見なされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-198">An impersonated domain might otherwise be considered legitimate (registered domain, configured email authentication records, etc.), except its intent is to deceive recipients.</span></span>

<span data-ttu-id="b6ce8-199">以下の偽装設定は、ATP フィッシング対策ポリシーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-199">The following impersonation settings are only available in ATP anti-phishing policies:</span></span>

- <span data-ttu-id="b6ce8-200">**保護するユーザー**: 指定した内部または外部ユーザーが偽装されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-200">**Users to protect**: Prevents the specified internal or external users from being impersonated.</span></span> <span data-ttu-id="b6ce8-201">たとえば、役員 (内部) と取り込みメンバー (外部) など。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-201">For example, executives (internal) and board members (external).</span></span> <span data-ttu-id="b6ce8-202">最大 60 の内部アドレスと外部アドレスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-202">You can add up to 60 internal and external addresses.</span></span> <span data-ttu-id="b6ce8-203">この保護されるユーザーのリストは、[適用先] 設定でポリシーが適用される受信者の **リストとは異** なります。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-203">This list of protected users is different from the list of recipients that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="b6ce8-204">たとえば、Executives という名前のグループに適用されるポリシー内で、Felipe Apodaca (felipea@contoso.com) を保護されたユーザーとして指定します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-204">For example, you specify Felipe Apodaca (felipea@contoso.com) as a protected user in a policy that applies to the group named Executives.</span></span> <span data-ttu-id="b6ce8-205">エグゼクティブ グループのメンバーに送信された受信メッセージ (Felipe Apodaca が偽装される) はポリシーによって処理されます (偽装されたユーザーに対して構成したアクション)。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-205">Inbound messages sent to members of the Executives group where Felipe Apodaca is impersonated will be acted on by the policy (the action you configure for impersonated users).</span></span>

- <span data-ttu-id="b6ce8-206">**保護するドメイン**: 指定したドメインが偽装されるのを防ぐ。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-206">**Domains to protect**: Prevent the specified domains from being impersonated.</span></span> <span data-ttu-id="b6ce8-207">たとえば、自分が所有しているすべてのドメイン (承認済[み](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)ドメイン) や特定のドメイン (所有しているドメインまたはパートナーのドメイン) などです。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-207">For example, all domains that you own ([accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) or specific domains (domains you own or partner domains).</span></span> <span data-ttu-id="b6ce8-208">この保護ドメインのリストは、[適用済み] の設定でポリシーが適用されるドメインの **リストとは異** なります。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-208">This list of protected domains is different from the list of domains that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="b6ce8-209">たとえば、エグゼtailspintoys.comグループのメンバーに適用されるポリシー内の保護済みドメインとして指定します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-209">For example, you specify tailspintoys.com as a protected domain in a policy that applies to members of the group named Executives.</span></span> <span data-ttu-id="b6ce8-210">エグゼクティブ グループのメンバーに送信された受信メッセージ。tailspintoys.com が偽装された場合、ポリシーによって実行される処理 (偽装ドメインに対して構成したアクション)。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-210">Inbound messages sent to members of the Executives group where tailspintoys.com is impersonated will be acted on by the policy (the action you configure for impersonated domains).</span></span>

- <span data-ttu-id="b6ce8-211">**保護されたユーザーまたはドメインのアクション**: ポリシーで保護されたユーザーおよび保護ドメインに対する偽装を含む受信メッセージに対して実行するアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-211">**Actions for protected users or domains**: Choose the action to take on inbound messages that contain impersonation attempts against the protected users and protected domains in the policy.</span></span> <span data-ttu-id="b6ce8-212">保護されたユーザーの偽装と保護されたドメインの偽装に対して、さまざまなアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-212">You can specify different actions for impersonation of protected users vs. impersonation of protected domains:</span></span>

  - <span data-ttu-id="b6ce8-213">**アクションを適用しない**</span><span class="sxs-lookup"><span data-stu-id="b6ce8-213">**Don't apply any action**</span></span>

  - <span data-ttu-id="b6ce8-214">**メッセージを他のメール アドレスにリダイレクト**する: メッセージを、指定された受信者ではなく、指定した受信者に送信します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-214">**Redirect message to other email addresses**: Sends the message to the specified recipients instead of the intended recipients.</span></span>

  - <span data-ttu-id="b6ce8-215">**メッセージを [迷惑メール] フォルダーに**移動: メッセージはメールボックスに配信され、[迷惑メール] フォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-215">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="b6ce8-216">Exchange Online では、メールボックスで迷惑メール ルールが有効になっている場合、メッセージは [迷惑メール] フォルダーに移動されます (既定では有効)。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-216">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="b6ce8-217">詳細については [、「Microsoft 365 の Exchange Online メールボックスで迷惑メール設定を構成する」を参照してください](configure-junk-email-settings-on-exo-mailboxes.md)。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-217">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

    - <span data-ttu-id="b6ce8-218">**メッセージを検疫**: メッセージを目的の受信者に代わって検疫に送信します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-218">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="b6ce8-219">検疫の詳細については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-219">For information about quarantine, see the following articles:</span></span>

    - [<span data-ttu-id="b6ce8-220">Microsoft 365 の検疫</span><span class="sxs-lookup"><span data-stu-id="b6ce8-220">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="b6ce8-221">Microsoft 365 の管理者として検疫済みメッセージとファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="b6ce8-221">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="b6ce8-222">Microsoft 365 のユーザーとして検疫済みメッセージを検索して解放する</span><span class="sxs-lookup"><span data-stu-id="b6ce8-222">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

  - <span data-ttu-id="b6ce8-223">**メッセージを配信し、その他のアドレスを BCC 行に追加します**。メッセージを指定された受信者に配信し、指定された受信者にメッセージをサイレントモードで配信します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-223">**Deliver the message and add other addresses to the Bcc line**: Deliver the message to the intended recipients and silently deliver the message to the specified recipients.</span></span>

  - <span data-ttu-id="b6ce8-224">**配信される前にメッセージを削除する**: 添付ファイルすべてを含む、メッセージ全体が確認しなけら削除します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-224">**Delete the message before it's delivered**: Silently deletes the entire message, including all attachments.</span></span>

- <span data-ttu-id="b6ce8-225">**安全性に関するヒント**: 偽装チェックに失敗したメッセージとして表示される次の偽装の安全性のヒントが有効または無効になります。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-225">**Safety tips**: Enables or disables the following impersonation safety tips that will appear messages that fail impersonation checks:</span></span>

  - <span data-ttu-id="b6ce8-226">**偽装されたユーザー**: From アドレスには保護されたユーザーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-226">**Impersonated users**: The From address contains a protected user.</span></span>
  - <span data-ttu-id="b6ce8-227">**偽装ドメイン: From**アドレスには保護されたドメインが含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-227">**Impersonated domains**: The From address contains a protected domain.</span></span>
  - <span data-ttu-id="b6ce8-228">**特殊文字**: 保護された送信者またはドメインでの、無制限の文字セット (数学的な記号、テキスト、または大文字と小文字の混在など) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-228">**Unusual characters**: The From address contains unusual character sets (for example, mathematical symbols and text or a mix of uppercase and lowercase letters) in a protected sender or domain.</span></span>

- <span data-ttu-id="b6ce8-229">**メールボックス インテリジェンス**: ユーザーのメール パターンと頻繁に連絡先が発生するように決定する、特定のインテリジェンス (AI) を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-229">**Mailbox intelligence**: Enables or disables artificial intelligence (AI) that determines user email patterns with their frequent contacts.</span></span> <span data-ttu-id="b6ce8-230">この設定により、正当なメールとなりすりすきメールをそれらの連絡先と区別できます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-230">This setting helps the AI distinguish between legitimate and spoofed email from those contacts.</span></span> <span data-ttu-id="b6ce8-231">メールボックス インテリジェンスは Exchange Online メールボックスに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-231">Mailbox intelligence is only available for Exchange Online mailboxes.</span></span>

- <span data-ttu-id="b6ce8-232">**メールボックス インテリジェンス ベースの偽装保護**: 各ユーザーの個々の送信者マップに基づいて、拡張された偽装結果を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-232">**Mailbox intelligence based impersonation protection**: Enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="b6ce8-233">このインテリジェンスにより、Microsoft 365 はユーザー偽装検出をカスタマイズし、誤検知をより良く処理できます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-233">This intelligence allows Microsoft 365 to customize user impersonation detection and better handle false positives.</span></span> <span data-ttu-id="b6ce8-234">ユーザーの偽装が検出された場合、メッセージに対して実行する特定のアクションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-234">When user impersonation is detected, you can define a specific action to take on the message:</span></span>

  - <span data-ttu-id="b6ce8-235">**アクションを適用しない**</span><span class="sxs-lookup"><span data-stu-id="b6ce8-235">**Don't apply any action**</span></span>
  - <span data-ttu-id="b6ce8-236">**他の電子メール アドレスへのメッセージのリダイレクト**</span><span class="sxs-lookup"><span data-stu-id="b6ce8-236">**Redirect message to other email addresses**</span></span>
  - <span data-ttu-id="b6ce8-237">**迷惑メール フォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="b6ce8-237">**Move message to Junk Email folder**</span></span>
  - <span data-ttu-id="b6ce8-238">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="b6ce8-238">**Quarantine the message**</span></span>
  - <span data-ttu-id="b6ce8-239">**メッセージを配信して、他のアドレスを BCC 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="b6ce8-239">**Deliver the message and add other addresses to the Bcc line**</span></span>
  - <span data-ttu-id="b6ce8-240">**配信される前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="b6ce8-240">**Delete the message before it's delivered**</span></span>

- <span data-ttu-id="b6ce8-241">**信頼できる送信者とドメイン**: 偽装保護設定の例外。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-241">**Trusted senders and domains**: Exceptions to the impersonation protection settings.</span></span> <span data-ttu-id="b6ce8-242">指定された送信者と送信者のドメインからのメッセージは、ポリシーによって偽装ベースの攻撃として分類されません。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-242">Messages from the specified senders and sender domains are never classified as impersonation-based attacks by the policy.</span></span> <span data-ttu-id="b6ce8-243">つまり、保護された送信者、保護されたドメイン、またはメールボックス インテリジェンス保護のアクションは、これらの信頼できる送信者または送信者のドメインには適用されません。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-243">In other words, the action for protected senders, protected domains, or mailbox intelligence protection aren't applied to these trusted senders or sender domains.</span></span> <span data-ttu-id="b6ce8-244">このリストの最大数は約 1000 エントリです。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-244">The maximum limit for these lists is approximately 1000 entries.</span></span>

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a><span data-ttu-id="b6ce8-245">ATP フィッシング対策ポリシーの高度なフィッシングしきい値</span><span class="sxs-lookup"><span data-stu-id="b6ce8-245">Advanced phishing thresholds in ATP anti-phishing policies</span></span>

<span data-ttu-id="b6ce8-246">以下の高度なフィッシングしきい値は、フィッシング対策を判断するために、メッセージに機械学習モデルを適用するセンシビリティを制御する ATP フィッシング対策ポリシーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-246">The following advanced phishing thresholds are only available in ATP anti-phishing policies to control the sensitivity for applying machine learning models to messages for determining a phishing verdict:</span></span>

- <span data-ttu-id="b6ce8-247">**1 - 標準**: これは既定値です。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-247">**1 - Standard**: This is the default value.</span></span> <span data-ttu-id="b6ce8-248">メッセージに対して実行される処理の重大度は、メッセージがフィッシングの重要度 (低、中、高、または非常に高い信頼度) によって異なる。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-248">The severity of the action that's taken on the message depends on the degree of confidence that the message is phishing (low, medium, high, or very high confidence).</span></span> <span data-ttu-id="b6ce8-249">たとえば、信頼度が非常に高いフィッシングとして識別されたメッセージには最も厳しいアクションが適用される一方で、信頼度の低いフィッシングであると識別されたメッセージに対しては重大な処理の適用が低くなっています。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-249">For example, messages that are identified as phishing with a very high degree of confidence have the most severe actions applied, while messages that are identified as phishing with a low degree of confidence have less severe actions applied.</span></span>

- <span data-ttu-id="b6ce8-250">**2 - Aggressive:** 信頼度が高いフィッシングと識別されたメッセージは、非常に高い信頼度で識別されたかのように処理されます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-250">**2 - Aggressive**: Messages that are identified as phishing with a high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="b6ce8-251">**3 - より厳しい**性値: 信頼度が中度または高いフィッシングと識別されたメッセージは、きわめ細かい信頼度で識別されたかのように処理されます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-251">**3 - More aggressive**: Messages that are identified as phishing with a medium or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="b6ce8-252">**4 - 最も厳しい**: 信頼度が低、中、または高い信頼度のフィッシングと識別されたメッセージは、きわめ細い信頼度で識別されたかのように処理されます。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-252">**4 - Most aggressive**: Messages that are identified as phishing with a low, medium, or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

<span data-ttu-id="b6ce8-253">誤検知 (悪くマークされた) 誤検知の発生は、この設定を増やすと増加します。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-253">The chance of false positives (good messages marked as bad) increases as you increase this setting.</span></span> <span data-ttu-id="b6ce8-254">推奨される設定の詳細については [、ATP フィッシング対策Officeの設定を参照してください](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)。</span><span class="sxs-lookup"><span data-stu-id="b6ce8-254">For information about the recommended settings, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>
