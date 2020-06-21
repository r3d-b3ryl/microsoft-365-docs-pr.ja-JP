---
title: フィッシング詐欺対策ポリシー
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 5a6f2d7f-d998-4f31-b4f5-f7cbf6f38578
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) および Office 365 Advanced Threat Protection (Office 365 ATP) で使用可能なフィッシング対策ポリシーについて学習できます。
ms.openlocfilehash: a61123e3d90a4125bf5a8303654973e1b478fc4c
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754666"
---
# <a name="anti-phishing-policies-in-microsoft-365"></a><span data-ttu-id="a7326-103">Microsoft 365 のフィッシング対策ポリシー</span><span class="sxs-lookup"><span data-stu-id="a7326-103">Anti-phishing policies in Microsoft 365</span></span>

<span data-ttu-id="a7326-104">フィッシング対策保護設定を構成するポリシーは、Microsoft 365 組織の exchange online メールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) 組織、および Office 365 Advanced Threat Protection (Office 365 ATP) 組織で使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7326-104">Policies to configure anti-phishing protection settings are available in Microsoft 365 organizations with Exchange Online mailboxes, standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, and Office 365 Advanced Threat Protection (Office 365 ATP) organizations.</span></span>

<span data-ttu-id="a7326-105">ATP のフィッシング対策ポリシーは、Office 365 ATP がインストールされている組織でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7326-105">ATP anti-phishing policies are only available in organizations that have Office 365 ATP.</span></span> <span data-ttu-id="a7326-106">たとえば、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="a7326-106">For example:</span></span>

- <span data-ttu-id="a7326-107">Microsoft 365 Enterprise E5、Microsoft 365 エデュケーション A5 など。</span><span class="sxs-lookup"><span data-stu-id="a7326-107">Microsoft 365 Enterprise E5, Microsoft 365 Education A5, etc.</span></span>
- [<span data-ttu-id="a7326-108">Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a7326-108">Microsoft 365 Enterprise</span></span>](https://www.microsoft.com/microsoft-365/enterprise/home)
- [<span data-ttu-id="a7326-109">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="a7326-109">Microsoft 365 Business</span></span>](https://www.microsoft.com/microsoft-365/business)
- [<span data-ttu-id="a7326-110">Office 365 の ATP をアドオンとして作成する</span><span class="sxs-lookup"><span data-stu-id="a7326-110">Office 365 ATP as an add-on</span></span>](https://products.office.com/exchange/advance-threat-protection)

<span data-ttu-id="a7326-111">他のすべての組織には、フィッシング対策ポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="a7326-111">All other organizations have anti-phishing policies.</span></span>

<span data-ttu-id="a7326-112">次の表では、フィッシング対策ポリシーと ATP のフィッシング対策ポリシーの大まかな違いについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a7326-112">The high-level differences between anti-phishing policies and ATP anti-phishing policies are described in the following table:</span></span>

||||
|---|:---:|:---:|
|<span data-ttu-id="a7326-113">**機能**</span><span class="sxs-lookup"><span data-stu-id="a7326-113">**Feature**</span></span>|<span data-ttu-id="a7326-114">**フィッシング詐欺対策ポリシー**</span><span class="sxs-lookup"><span data-stu-id="a7326-114">**Anti-phishing policies**</span></span>|<span data-ttu-id="a7326-115">**ATP のフィッシング対策ポリシー**</span><span class="sxs-lookup"><span data-stu-id="a7326-115">**ATP anti-phishing policies**</span></span>|
|<span data-ttu-id="a7326-116">自動的に作成される既定のポリシー</span><span class="sxs-lookup"><span data-stu-id="a7326-116">Automatically created default policy</span></span>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="a7326-119">カスタムポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="a7326-119">Create custom policies</span></span>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="a7326-122">ポリシー設定<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a7326-122">Policy settings<sup>\*</sup></span></span>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="a7326-125">偽装設定</span><span class="sxs-lookup"><span data-stu-id="a7326-125">Impersonation settings</span></span>||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="a7326-127">スプーフィング設定</span><span class="sxs-lookup"><span data-stu-id="a7326-127">Spoof settings</span></span>|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|<span data-ttu-id="a7326-130">高度なフィッシングしきい値</span><span class="sxs-lookup"><span data-stu-id="a7326-130">Advanced phishing thresholds</span></span>||![チェック マーク](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|

<span data-ttu-id="a7326-132"><sup>\*</sup>既定のポリシーでは、ポリシーの名前と説明は読み取り専用 (説明が空白) なので、ポリシーを適用するユーザーを指定することはできません (既定のポリシーはすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="a7326-132"><sup>\*</sup> In the default policy, the policy name and description are read-only (the description is blank), and you can't specify who the policy applies to (the default policy applies to all recipients).</span></span>

<span data-ttu-id="a7326-133">フィッシング対策ポリシーを構成するには、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7326-133">To configure anti-phishing policies, see the following topics:</span></span>

- [<span data-ttu-id="a7326-134">EOP でフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="a7326-134">Configure anti-phishing policies in EOP</span></span>](configure-anti-phishing-policies-eop.md)

- [<span data-ttu-id="a7326-135">Microsoft 365 で ATP のフィッシング対策ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="a7326-135">Configure ATP anti-phishing policies in Microsoft 365</span></span>](configure-atp-anti-phishing-policies.md)

<span data-ttu-id="a7326-136">このトピックの残りの部分では、フィッシング対策ポリシーと ATP のフィッシング対策ポリシーで使用可能な設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="a7326-136">The rest of this topic describes the settings that are available in anti-phishing policies and ATP anti-phishing policies.</span></span>

## <a name="spoof-settings"></a><span data-ttu-id="a7326-137">スプーフィング設定</span><span class="sxs-lookup"><span data-stu-id="a7326-137">Spoof settings</span></span>

<span data-ttu-id="a7326-138">スプーフィングとは、電子メールメッセージの差出人アドレス (電子メールクライアントに表示される送信者アドレス) が電子メールソースのドメインと一致しない場合です。</span><span class="sxs-lookup"><span data-stu-id="a7326-138">Spoofing is when the From address in an email message (the sender address that's show in email clients) doesn't match the domain of the email source.</span></span> <span data-ttu-id="a7326-139">スプーフィングの詳細については、「 [Microsoft 365 のスプーフィング対策保護](anti-spoofing-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7326-139">For more information about spoofing, see [Anti-spoofing protection in Microsoft 365](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="a7326-140">フィッシング対策ポリシーおよび ATP のフィッシング対策ポリシーでは、次のスプーフィング設定を使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7326-140">The following spoof settings are available in anti-phishing policies and ATP anti-phishing policies:</span></span>

- <span data-ttu-id="a7326-141">**スプーフィング防止保護**: スプーフィング対策保護を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="a7326-141">**Anti-spoofing protection**: Enables or disables anti-spoofing protection.</span></span> <span data-ttu-id="a7326-142">有効にしておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a7326-142">We recommend that you leave it enabled.</span></span> <span data-ttu-id="a7326-143">**スプーフィングインテリジェンスポリシー**を使用して、特定のスプーフィングされた内部および外部の送信者を許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="a7326-143">You use the **spoof intelligence policy** to allow or block specific spoofed internal and external senders.</span></span> <span data-ttu-id="a7326-144">詳細については、「[Microsoft 365 でのスプーフィング インテリジェンスの構成](learn-about-spoof-intelligence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7326-144">For more information, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a7326-145">スプーフィングの設定は、既定では、EOP の既定のフィッシング対策ポリシー、既定の ATP のフィッシング対策ポリシー、および作成した新しいカスタムのフィッシング対策ポリシーまたは ATP のフィッシング対策ポリシーで有効になっています。</span><span class="sxs-lookup"><span data-stu-id="a7326-145">Spoof settings are enabled by default in the default anti-phishing policy in EOP, the default ATP anti-phishing policy, and in new custom anti-phishing policies or ATP anti-phishing policies that you create.</span></span> <br/><br/> <span data-ttu-id="a7326-146">MX レコードが Microsoft 365 をポイントしていない場合は、スプーフィング防止保護を無効にする必要はありません。代わりに、コネクタの拡張フィルターを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a7326-146">You don't need to disable anti-spoofing protection if your MX record doesn't point to Microsoft 365; you enable Enhanced Filtering for Connectors instead.</span></span> <span data-ttu-id="a7326-147">手順については、「 [Exchange Online のコネクタの拡張フィルター処理](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7326-147">For instructions, see [Enhanced Filtering for Connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).</span></span>

  <span data-ttu-id="a7326-148">スプーフィングされた送信者からのメッセージでは、メッセージに対して実行するアクションを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a7326-148">For messages from blocked spoofed senders, you can also specify the action to take on the messages:</span></span>

  - <span data-ttu-id="a7326-149">**[迷惑メールフォルダーにメッセージを移動する**]: これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="a7326-149">**Move message to Junk Email folder**: This is the default value.</span></span> <span data-ttu-id="a7326-150">メッセージがメールボックスに配信され、迷惑メールフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="a7326-150">The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="a7326-151">Exchange Online では、メールボックスで迷惑メールルールが有効になっている場合、メッセージは [迷惑メール] フォルダーに移動されます (既定で有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="a7326-151">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="a7326-152">詳細については、「 [Microsoft 365 の「Exchange Online メールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7326-152">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

  - <span data-ttu-id="a7326-153">**メッセージを検疫**する: 目的の受信者ではなく、検疫にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="a7326-153">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="a7326-154">検疫の詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7326-154">For information about quarantine, see the following topics:</span></span>

    - [<span data-ttu-id="a7326-155">Microsoft 365 での検疫</span><span class="sxs-lookup"><span data-stu-id="a7326-155">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="a7326-156">Microsoft 365 の管理者として検疫済みメッセージおよびファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="a7326-156">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="a7326-157">Microsoft 365 のユーザーとして検疫済みメッセージを検索して解放する</span><span class="sxs-lookup"><span data-stu-id="a7326-157">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

- <span data-ttu-id="a7326-158">**認証**されていない送信者: Outlook での未識別の送信者識別を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="a7326-158">**Unauthenticated Sender**: Enables or disables unidentified sender identification in Outlook.</span></span> <span data-ttu-id="a7326-159">具体的には次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a7326-159">Specifically:</span></span>

  - <span data-ttu-id="a7326-160">メッセージが SPF または DKIM のチェックに合格せず、メッセージが DMARC または[コンポジット認証](email-validation-and-authentication.md#composite-authentication)に**合格しない**場合、送信者の写真に疑問符 (?) が追加されます。</span><span class="sxs-lookup"><span data-stu-id="a7326-160">A question mark (?) is added to the sender's photo if the message does not pass SPF or DKIM checks **and** the message does not pass DMARC or [composite authentication](email-validation-and-authentication.md#composite-authentication).</span></span>

  - <span data-ttu-id="a7326-161">Via タグ (chris@contoso.com <u>via</u> michelle@fabrikam.com) は、From アドレスのドメイン (電子メールクライアントに表示されるメッセージの送信者) が dkim シグネチャまたは**MAIL From**アドレスのドメインと異なる場合に追加されます。</span><span class="sxs-lookup"><span data-stu-id="a7326-161">The via tag (chris@contoso.com <u>via</u> michelle@fabrikam.com) is added if the domain in the From address (the message sender that's displayed in email clients) is different from the domain in the DKIM signature or the **MAIL FROM** address.</span></span> <span data-ttu-id="a7326-162">これらのアドレスの詳細については、「[電子メールメッセージの標準の概要](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7326-162">For more information about these addresses, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)</span></span>

  <span data-ttu-id="a7326-163">特定の送信者からのメッセージにこれらの識別子が追加されないようにするには、次のオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7326-163">To prevent these identifiers from being added to messages from specific senders, you have the following options:</span></span>

  - <span data-ttu-id="a7326-164">スプーフィングインテリジェンスポリシーで、送信者にスプーフィングすることを許可します。</span><span class="sxs-lookup"><span data-stu-id="a7326-164">Allow the sender to spoof in the spoof intelligence policy.</span></span> <span data-ttu-id="a7326-165">手順については、「 [Microsoft 365 でスプーフィングインテリジェンスを構成する](learn-about-spoof-intelligence.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7326-165">For instructions, see [Configure spoof intelligence in Microsoft 365](learn-about-spoof-intelligence.md).</span></span>

  - <span data-ttu-id="a7326-166">送信者ドメインの[電子メール認証を構成](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own)します。</span><span class="sxs-lookup"><span data-stu-id="a7326-166">[Configure email authentication](email-validation-and-authentication.md#configure-email-authentication-for-domains-you-own) for the sender domain.</span></span>
  
    - <span data-ttu-id="a7326-167">送信者の写真の疑問符の場合は、SPF または DKIM が最も重要です。</span><span class="sxs-lookup"><span data-stu-id="a7326-167">For the question mark in the sender's photo, SPF or DKIM are the most important.</span></span>
    - <span data-ttu-id="a7326-168">Via タグの場合は、d KIM 署名のドメイン、または From アドレスのドメインの**メール**アドレスが一致する (またはサブドメインである) ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7326-168">For the via tag, confirm the domain in the DKIM signature or the **MAIL FROM** address matches (or is a subdomain of) the domain in the From address.</span></span>

  <span data-ttu-id="a7326-169">詳細については、「 [Outlook.com および Outlook on the web」の「疑わしいメッセージを特定](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7326-169">For more information, see [Identify suspicious messages in Outlook.com and Outlook on the web](https://support.microsoft.com/office/3d44102b-6ce3-4f7c-a359-b623bec82206)</span></span>

## <a name="exclusive-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="a7326-170">ATP のフィッシング対策ポリシーの排他的な設定</span><span class="sxs-lookup"><span data-stu-id="a7326-170">Exclusive settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="a7326-171">このセクションでは、ATP のフィッシング対策ポリシーでのみ使用可能なポリシー設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="a7326-171">This section describes the policy settings that are only available in ATP anti-phishing policies.</span></span>

> [!NOTE]
> <span data-ttu-id="a7326-172">既定では、既定のポリシーの場合でも、ATP の排他的な設定は構成されていないか、有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="a7326-172">By default, the ATP exclusive settings are not configured or turned on, even in the default policy.</span></span> <span data-ttu-id="a7326-173">これらの機能を利用するには、既定の ATP のフィッシング対策ポリシーでそれらを有効にして構成するか、カスタムの ATP のフィッシング対策ポリシーを作成して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7326-173">To take advantage of these features, you need to enable and configure them in the default ATP anti-phishing policy, or create and configure custom ATP anti-phishing policies.</span></span>

### <a name="policy-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="a7326-174">ATP のフィッシング対策ポリシーのポリシー設定</span><span class="sxs-lookup"><span data-stu-id="a7326-174">Policy settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="a7326-175">次のポリシー設定は、ATP のフィッシング対策ポリシーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7326-175">The following policy settings are only available in ATP anti-phishing policies:</span></span>

- <span data-ttu-id="a7326-176">**Name**: 既定のフィッシング対策ポリシーの名前を変更することはできませんが、作成したカスタムポリシーの名前と名前を変更することはできます。</span><span class="sxs-lookup"><span data-stu-id="a7326-176">**Name**: You can't rename the default anti-phishing policy, but you can name and rename custom policies that you create.</span></span>

- <span data-ttu-id="a7326-177">**説明**既定のフィッシング対策ポリシーに説明を追加することはできませんが、作成したカスタムポリシーの説明を追加したり変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a7326-177">**Description** You can't add a description to the default anti-phishing policy, but you can add and change the description for custom policies that you create.</span></span>

- <span data-ttu-id="a7326-178">**適用対象**: ATP のフィッシング対策ポリシーが適用される内部の受信者を識別します。</span><span class="sxs-lookup"><span data-stu-id="a7326-178">**Applied to**: Identifies internal recipients that the ATP anti-phishing policy applies to.</span></span> <span data-ttu-id="a7326-179">この値は、カスタムポリシーでは必須であり、既定のポリシーでは使用できません (既定のポリシーはすべての受信者に適用されます)。</span><span class="sxs-lookup"><span data-stu-id="a7326-179">This value is required in custom policies, and not available in the default policy (the default policy applies to all recipients).</span></span>

    <span data-ttu-id="a7326-180">各条件や例外は 1 回しか使用できませんが、条件や例外には複数の値を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="a7326-180">You can only use a condition or exception once, but you can specify multiple values for the condition or exception.</span></span> <span data-ttu-id="a7326-181">同じ条件または例外の複数の値を使用するか、ロジック (たとえば、 _\<recipient1\>_ または) を使用 _\<recipient2\>_ します。</span><span class="sxs-lookup"><span data-stu-id="a7326-181">Multiple values of the same condition or exception use OR logic (for example, _\<recipient1\>_ or _\<recipient2\>_).</span></span> <span data-ttu-id="a7326-182">さまざまな条件や例外、およびロジック (およびなど) を使用し _\<recipient1\>_ _\<member of group 1\>_ ます。</span><span class="sxs-lookup"><span data-stu-id="a7326-182">Different conditions or exceptions use AND logic (for example, _\<recipient1\>_ and _\<member of group 1\>_).</span></span>

  - <span data-ttu-id="a7326-183">**受信者は**、組織内の1つ以上のメールボックス、メールユーザー、またはメール連絡先です。</span><span class="sxs-lookup"><span data-stu-id="a7326-183">**Recipient is**: One or more mailboxes, mail users, or mail contacts in your organization.</span></span>
  - <span data-ttu-id="a7326-184">**受信者が**組織内の1つまたは複数のグループのメンバーである。</span><span class="sxs-lookup"><span data-stu-id="a7326-184">**Recipient is a member of**: One or more groups in your organization.</span></span>
  - <span data-ttu-id="a7326-185">**受信者のドメインは、** Microsoft 365 で構成された1つ以上の承認済みドメインです。</span><span class="sxs-lookup"><span data-stu-id="a7326-185">**The recipient domain is**: One or more of the configured accepted domains in Microsoft 365.</span></span>

  - <span data-ttu-id="a7326-186">例外を**除く**: ルールの例外。</span><span class="sxs-lookup"><span data-stu-id="a7326-186">**Except when**: Exceptions for the rule.</span></span> <span data-ttu-id="a7326-187">設定と動作は、次の条件とまったく同じです。</span><span class="sxs-lookup"><span data-stu-id="a7326-187">The settings and behavior are exactly like the conditions:</span></span>

    - <span data-ttu-id="a7326-188">**受信者が**</span><span class="sxs-lookup"><span data-stu-id="a7326-188">**Recipient is**</span></span>
    - <span data-ttu-id="a7326-189">**受信者がメンバーである**</span><span class="sxs-lookup"><span data-stu-id="a7326-189">**Recipient is a member of**</span></span>
    - <span data-ttu-id="a7326-190">**受信者のドメインが**</span><span class="sxs-lookup"><span data-stu-id="a7326-190">**The recipient domain is**</span></span>

### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a><span data-ttu-id="a7326-191">ATP のフィッシング対策ポリシーの偽装設定</span><span class="sxs-lookup"><span data-stu-id="a7326-191">Impersonation settings in ATP anti-phishing policies</span></span>

<span data-ttu-id="a7326-192">偽装は、メッセージ内の送信者または送信者の電子メールドメインが、実際の送信者またはドメインに似ているように見えます。</span><span class="sxs-lookup"><span data-stu-id="a7326-192">Impersonation is where the sender or the sender's email domain in a message looks similar to a real sender or domain:</span></span>

- <span data-ttu-id="a7326-193">ドメイン contoso.com の偽装の例は、ćóntoso.com です。</span><span class="sxs-lookup"><span data-stu-id="a7326-193">An example impersonation of the domain contoso.com is ćóntoso.com.</span></span>

- <span data-ttu-id="a7326-194">ユーザー michelle@contoso.com の偽装の例は、michele@contoso.com です。</span><span class="sxs-lookup"><span data-stu-id="a7326-194">An example impersonation of the user michelle@contoso.com is michele@contoso.com.</span></span>

<span data-ttu-id="a7326-195">偽装ドメインは、受信者を deceive することを除けば、正当 (登録済みドメイン、構成済みの電子メール認証レコードなど) であると見なされる場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7326-195">An impersonated domain might otherwise be considered legitimate (registered domain, configured email authentication records, etc.), except its intent is to deceive recipients.</span></span>

<span data-ttu-id="a7326-196">次の偽装設定は、ATP のフィッシング対策ポリシーでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7326-196">The following impersonation settings are only available in ATP anti-phishing policies:</span></span>

- <span data-ttu-id="a7326-197">**保護するユーザー**: 指定された内部または外部のユーザーが偽装されないようにします。</span><span class="sxs-lookup"><span data-stu-id="a7326-197">**Users to protect**: Prevents the specified internal or external users from being impersonated.</span></span> <span data-ttu-id="a7326-198">たとえば、重役 (internal) メンバーと掲示板メンバー (外部) があります。</span><span class="sxs-lookup"><span data-stu-id="a7326-198">For example, executives (internal) and board members (external).</span></span> <span data-ttu-id="a7326-199">最大60の内部および外部アドレスを追加できます。</span><span class="sxs-lookup"><span data-stu-id="a7326-199">You can add up to 60 internal and external addresses.</span></span> <span data-ttu-id="a7326-200">この保護されたユーザーの一覧は、[**適用先**] 設定でポリシーが適用される受信者の一覧とは異なります。</span><span class="sxs-lookup"><span data-stu-id="a7326-200">This list of protected users is different from the list of recipients that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="a7326-201">たとえば、"重役" という名前のグループに適用されるポリシーでは、保護されたユーザーとして Felipe アポストロフィ (felipea@contoso.com) を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7326-201">For example, you specify Felipe Apodaca (felipea@contoso.com) as a protected user in a policy that applies to the group named Executives.</span></span> <span data-ttu-id="a7326-202">Felipe アポストロフィが偽装されているエグゼクティブグループのメンバーに送信される受信メッセージは、ポリシー (偽装ユーザーに対して構成するアクション) によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="a7326-202">Inbound messages sent to members of the Executives group where Felipe Apodaca is impersonated will be acted on by the policy (the action you configure for impersonated users).</span></span>

- <span data-ttu-id="a7326-203">**保護するドメイン**: 指定されたドメインが偽装されないようにします。</span><span class="sxs-lookup"><span data-stu-id="a7326-203">**Domains to protect**: Prevent the specified domains from being impersonated.</span></span> <span data-ttu-id="a7326-204">たとえば、所有しているすべてのドメイン ([承認済みドメイン](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) または特定のドメイン (自分が所有しているドメインまたはパートナードメイン)。</span><span class="sxs-lookup"><span data-stu-id="a7326-204">For example, all domains that you own ([accepted domains](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) or specific domains (domains you own or partner domains).</span></span> <span data-ttu-id="a7326-205">この保護されたドメインの一覧は、[**適用先**] 設定でポリシーが適用されるドメインの一覧とは異なります。</span><span class="sxs-lookup"><span data-stu-id="a7326-205">This list of protected domains is different from the list of domains that the policy applies to in the **Applied to** setting.</span></span>

  <span data-ttu-id="a7326-206">たとえば、"重役" というグループのメンバーに適用されるポリシーで、保護されたドメインとして tailspintoys.com を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7326-206">For example, you specify tailspintoys.com as a protected domain in a policy that applies to members of the group named Executives.</span></span> <span data-ttu-id="a7326-207">Tailspintoys.com が偽装されるエグゼクティブグループのメンバーに送信される受信メッセージは、ポリシー (偽装ドメインに対して構成するアクション) によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="a7326-207">Inbound messages sent to members of the Executives group where tailspintoys.com is impersonated will be acted on by the policy (the action you configure for impersonated domains).</span></span>

- <span data-ttu-id="a7326-208">**保護されたユーザーまたはドメインのアクション**: ポリシー内の保護されたユーザーと保護されたドメインに対する偽装試行を含む受信メッセージに対して実行するアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a7326-208">**Actions for protected users or domains**: Choose the action to take on inbound messages that contain impersonation attempts against the protected users and protected domains in the policy.</span></span> <span data-ttu-id="a7326-209">保護されたユーザーと保護されたドメインの偽装に対して、さまざまなアクションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a7326-209">You can specify different actions for impersonation of protected users vs. impersonation of protected domains:</span></span>

  - <span data-ttu-id="a7326-210">**どの操作も適用しない**</span><span class="sxs-lookup"><span data-stu-id="a7326-210">**Don't apply any action**</span></span>

  - <span data-ttu-id="a7326-211">**他の電子メールアドレスへのメッセージのリダイレクト**: 目的の受信者の代わりに、指定された受信者にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="a7326-211">**Redirect message to other email addresses**: Sends the message to the specified recipients instead of the intended recipients.</span></span>

  - <span data-ttu-id="a7326-212">**[迷惑メールフォルダーにメッセージを移動する**]: メッセージはメールボックスに配信され、迷惑メールフォルダーに移動されます。</span><span class="sxs-lookup"><span data-stu-id="a7326-212">**Move message to Junk Email folder**: The message is delivered to the mailbox and moved to the Junk Email folder.</span></span> <span data-ttu-id="a7326-213">Exchange Online では、メールボックスで迷惑メールルールが有効になっている場合、メッセージは [迷惑メール] フォルダーに移動されます (既定で有効になっています)。</span><span class="sxs-lookup"><span data-stu-id="a7326-213">In Exchange Online, the message is moved to the Junk Email folder if the junk email rule is enabled on the mailbox (it's enabled by default).</span></span> <span data-ttu-id="a7326-214">詳細については、「 [Microsoft 365 の「Exchange Online メールボックスの迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7326-214">For more information, see [Configure junk email settings on Exchange Online mailboxes in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).</span></span>

    - <span data-ttu-id="a7326-215">**メッセージを検疫**する: 目的の受信者ではなく、検疫にメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="a7326-215">**Quarantine the message**: Sends the message to quarantine instead of the intended recipients.</span></span> <span data-ttu-id="a7326-216">検疫の詳細については、以下のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7326-216">For information about quarantine, see the following topics:</span></span>

    - [<span data-ttu-id="a7326-217">Microsoft 365 での検疫</span><span class="sxs-lookup"><span data-stu-id="a7326-217">Quarantine in Microsoft 365</span></span>](quarantine-email-messages.md)
    - [<span data-ttu-id="a7326-218">Microsoft 365 の管理者として検疫済みメッセージおよびファイルを管理する</span><span class="sxs-lookup"><span data-stu-id="a7326-218">Manage quarantined messages and files as an admin in Microsoft 365</span></span>](manage-quarantined-messages-and-files.md)
    - [<span data-ttu-id="a7326-219">Microsoft 365 のユーザーとして検疫済みメッセージを検索して解放する</span><span class="sxs-lookup"><span data-stu-id="a7326-219">Find and release quarantined messages as a user in Microsoft 365</span></span>](find-and-release-quarantined-messages-as-a-user.md)

  - <span data-ttu-id="a7326-220">**メッセージを配信し、その他のアドレスを Bcc 行に追加**します。メッセージを目的の受信者に配信し、メッセージを指定された受信者に通知せずに配信します。</span><span class="sxs-lookup"><span data-stu-id="a7326-220">**Deliver the message and add other addresses to the Bcc line**: Deliver the message to the intended recipients and silently deliver the message to the specified recipients.</span></span>

  - <span data-ttu-id="a7326-221">**メッセージが配信される前に削除**する: すべての添付ファイルを含むメッセージ全体を警告なしで削除します。</span><span class="sxs-lookup"><span data-stu-id="a7326-221">**Delete the message before it's delivered**: Silently deletes the entire message, including all attachments.</span></span>

- <span data-ttu-id="a7326-222">**安全性に関するヒント**: 偽装の確認に失敗した場合に表示される偽装に関する次のような安全のヒントを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="a7326-222">**Safety tips**: Enables or disables the following impersonation safety tips that will appear messages that fail impersonation checks:</span></span>

  - <span data-ttu-id="a7326-223">**偽装ユーザー**: 差出人アドレスに保護されたユーザーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a7326-223">**Impersonated users**: The From address contains a protected user.</span></span>
  - <span data-ttu-id="a7326-224">**偽装ドメイン**: 差出人アドレスには保護されたドメインが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a7326-224">**Impersonated domains**: The From address contains a protected domain.</span></span>
  - <span data-ttu-id="a7326-225">**通常の文字**: 差出人アドレスには、保護された送信者またはドメインに、一般的でない文字セット (数学記号、文字、大文字と小文字の組み合わせなど) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a7326-225">**Unusual characters**: The From address contains unusual character sets (for example, mathematical symbols and text or a mix of uppercase and lowercase letters) in a protected sender or domain.</span></span>

- <span data-ttu-id="a7326-226">**メールボックスインテリジェンス**: 頻繁に使用する連絡先とユーザーの電子メールのパターンを決定する人工知能 (AI) を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="a7326-226">**Mailbox intelligence**: Enables or disables artificial intelligence (AI) that determines user email patterns with their frequent contacts.</span></span> <span data-ttu-id="a7326-227">この設定により、AI は、これらの連絡先からの正当な電子メールとスプーフィングされたメールを区別します。</span><span class="sxs-lookup"><span data-stu-id="a7326-227">This setting helps the AI distinguish between legitimate and spoofed email from those contacts.</span></span> <span data-ttu-id="a7326-228">メールボックスインテリジェンスは、Exchange Online メールボックスに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a7326-228">Mailbox intelligence is only available for Exchange Online mailboxes.</span></span>

- <span data-ttu-id="a7326-229">**メールボックスインテリジェンスベースの偽装保護**: 各ユーザーの個々の送信者マップに基づいて、強化された偽装結果を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="a7326-229">**Mailbox intelligence based impersonation protection**: Enables or disables enhanced impersonation results based on each user's individual sender map.</span></span> <span data-ttu-id="a7326-230">このインテリジェンスにより、Microsoft 365 はユーザー偽装検出をカスタマイズし、誤検知を適切に処理することができます。</span><span class="sxs-lookup"><span data-stu-id="a7326-230">This intelligence allows Microsoft 365 to customize user impersonation detection and better handle false positives.</span></span> <span data-ttu-id="a7326-231">ユーザー偽装が検出された場合、メッセージに対して実行する特定のアクションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="a7326-231">When user impersonation is detected, you can define a specific action to take on the message:</span></span>

  - <span data-ttu-id="a7326-232">**どの操作も適用しない**</span><span class="sxs-lookup"><span data-stu-id="a7326-232">**Don't apply any action**</span></span>
  - <span data-ttu-id="a7326-233">**他の電子メールアドレスへのメッセージのリダイレクト**</span><span class="sxs-lookup"><span data-stu-id="a7326-233">**Redirect message to other email addresses**</span></span>
  - <span data-ttu-id="a7326-234">**迷惑メールフォルダーにメッセージを移動する**</span><span class="sxs-lookup"><span data-stu-id="a7326-234">**Move message to Junk Email folder**</span></span>
  - <span data-ttu-id="a7326-235">**メッセージを検疫する**</span><span class="sxs-lookup"><span data-stu-id="a7326-235">**Quarantine the message**</span></span>
  - <span data-ttu-id="a7326-236">**メッセージを配信し、その他のアドレスを Bcc 行に追加する**</span><span class="sxs-lookup"><span data-stu-id="a7326-236">**Deliver the message and add other addresses to the Bcc line**</span></span>
  - <span data-ttu-id="a7326-237">**配信前にメッセージを削除する**</span><span class="sxs-lookup"><span data-stu-id="a7326-237">**Delete the message before it's delivered**</span></span>

- <span data-ttu-id="a7326-238">**信頼できる送信者とドメイン**: 偽装保護設定の例外。</span><span class="sxs-lookup"><span data-stu-id="a7326-238">**Trusted senders and domains**: Exceptions to the impersonation protection settings.</span></span> <span data-ttu-id="a7326-239">指定した送信者と送信者のドメインからのメッセージは、ポリシーによって偽装ベースの攻撃として分類されることはありません。</span><span class="sxs-lookup"><span data-stu-id="a7326-239">Messages from the specified senders and sender domains are never classified as impersonation-based attacks by the policy.</span></span> <span data-ttu-id="a7326-240">つまり、保護された送信者、保護されたドメイン、またはメールボックスインテリジェンス保護のアクションは、これらの信頼できる送信者または送信者ドメインには適用されません。</span><span class="sxs-lookup"><span data-stu-id="a7326-240">In other words, the action for protected senders, protected domains, or mailbox intelligence protection aren't applied to these trusted senders or sender domains.</span></span> <span data-ttu-id="a7326-241">これらのリストの最大数は、約1000エントリです。</span><span class="sxs-lookup"><span data-stu-id="a7326-241">The maximum limit for these lists is approximately 1000 entries.</span></span>

### <a name="advanced-phishing-thresholds-in-atp-anti-phishing-policies"></a><span data-ttu-id="a7326-242">ATP のフィッシング対策ポリシーの高度なフィッシングしきい値</span><span class="sxs-lookup"><span data-stu-id="a7326-242">Advanced phishing thresholds in ATP anti-phishing policies</span></span>

<span data-ttu-id="a7326-243">次の詳細なフィッシングしきい値は、ATP のフィッシング対策ポリシーでのみ使用可能で、フィッシング verdict を決定するためのコンピューター学習モデルをメッセージに適用する際の感度を制御します。</span><span class="sxs-lookup"><span data-stu-id="a7326-243">The following advanced phishing thresholds are only available in ATP anti-phishing policies to control the sensitivity for applying machine learning models to messages for determining a phishing verdict:</span></span>

- <span data-ttu-id="a7326-244">**1-標準**: これが既定値です。</span><span class="sxs-lookup"><span data-stu-id="a7326-244">**1 - Standard**: This is the default value.</span></span> <span data-ttu-id="a7326-245">メッセージに対して実行されるアクションの重要度は、メッセージがフィッシングであること (低、中、高、または非常に高い信頼度) によって異なります。</span><span class="sxs-lookup"><span data-stu-id="a7326-245">The severity of the action that's taken on the message depends on the degree of confidence that the message is phishing (low, medium, high, or very high confidence).</span></span> <span data-ttu-id="a7326-246">たとえば、非常に高い確実性を持つフィッシングとして識別されたメッセージには、最も重大なアクションが適用されますが、信頼度が低いと判断されたメッセージには、非常に厳しいアクションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="a7326-246">For example, messages that are identified as phishing with a very high degree of confidence have the most severe actions applied, while messages that are identified as phishing with a low degree of confidence have less severe actions applied.</span></span>

- <span data-ttu-id="a7326-247">**2-アグレッシブ**: 信頼度の高いフィッシングとして識別されたメッセージは、非常に高い精度で識別されたものとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="a7326-247">**2 - Aggressive**: Messages that are identified as phishing with a high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="a7326-248">**3 つ以上のアグレッシブ**: 中または高レベルの信頼度でフィッシングとして識別されたメッセージは、非常に高い信頼度で識別された場合と同様に扱われます。</span><span class="sxs-lookup"><span data-stu-id="a7326-248">**3 - More aggressive**: Messages that are identified as phishing with a medium or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

- <span data-ttu-id="a7326-249">**4-最も積極的**な状態: 低、中、高のいずれかの信頼度を持つフィッシングとして識別されたメッセージは、非常に高い信頼度で識別された場合と同様に扱われます。</span><span class="sxs-lookup"><span data-stu-id="a7326-249">**4 - Most aggressive**: Messages that are identified as phishing with a low, medium, or high degree of confidence are treated as if they were identified with a very high degree of confidence.</span></span>

<span data-ttu-id="a7326-250">この設定値を大きくすると、誤検知 (不良としてマークされている正常なメッセージ) の可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="a7326-250">The chance of false positives (good messages marked as bad) increases as you increase this setting.</span></span> <span data-ttu-id="a7326-251">推奨される設定の詳細については、「 [OFFICE ATP のフィッシング対策ポリシーの設定](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7326-251">For information about the recommended settings, see [Office ATP anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#office-atp-anti-phishing-policy-settings).</span></span>