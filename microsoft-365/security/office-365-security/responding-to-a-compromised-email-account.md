---
title: 侵害された電子メール アカウントへの対応
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
search.appverid:
- MET150
description: Microsoft 365 で利用可能なツールを使用して、侵害された電子メール アカウントを認識して対処する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1bf2a5dbc7e1fdd447baf76fd051abff88b4b30
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205715"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="c0485-103">侵害された電子メール アカウントへの対応</span><span class="sxs-lookup"><span data-stu-id="c0485-103">Responding to a Compromised Email Account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c0485-104">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="c0485-104">**Applies to**</span></span>
- [<span data-ttu-id="c0485-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c0485-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c0485-106">Microsoft Defender for Office 365 プラン 1 およびプラン 2</span><span class="sxs-lookup"><span data-stu-id="c0485-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c0485-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0485-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c0485-108">**概要** 侵害された Microsoft 365 電子メール アカウントを認識して対処する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0485-108">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="c0485-109">侵害された Microsoft 365 電子メール アカウントとは何か?</span><span class="sxs-lookup"><span data-stu-id="c0485-109">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="c0485-p101">Microsoft 365 のメールボックス、データ、およびその他のサービスへのアクセスは、ユーザー名とパスワードや暗証番号 (PIN) などの資格情報を使用して制御されます。意図したユーザー以外の何者かがこれらの資格情報を盗んだ場合、盗まれた資格情報は侵害されたと見なされます。攻撃者は盗んだ資格情報を使用して、正規のユーザーとしてサインインし、不正な操作を行うことができます。また、攻撃者は盗んだ資格情報を使用して、ユーザーの Microsoft 365 メールボックス、SharePoint フォルダー、または OneDrive 内のファイルにアクセスできます。よく見られるのは、組織の内外の受信者に正規のユーザーとして電子メールを送り付ける攻撃者です。データが攻撃者によって外部の受信者に電子メールで送信される事象をデータ流出と言います。</span><span class="sxs-lookup"><span data-stu-id="c0485-p101">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN. When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised. With them the attacker can sign in as the original user and perform illicit actions. Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive. One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization. When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="c0485-116">侵害された Microsoft メール アカウントの兆候</span><span class="sxs-lookup"><span data-stu-id="c0485-116">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="c0485-p102">ユーザーが自分の Microsoft 365 メールボックスでの異常な活動に気付いて報告してくる場合があります。よく見られる兆候を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="c0485-p102">Users might notice and report unusual activity in their Microsoft 365 mailboxes. Here are some common symptoms:</span></span>

- <span data-ttu-id="c0485-119">電子メールの消失や削除などの不審な活動。</span><span class="sxs-lookup"><span data-stu-id="c0485-119">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="c0485-120">侵害されたアカウントから電子メールを受信したが、その送信者の **送信済みアイテム** フォルダーに対応する電子メールが存在しない。</span><span class="sxs-lookup"><span data-stu-id="c0485-120">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="c0485-p103">意図したユーザーまたは管理者が作成していない受信トレイ ルールの存在。このようなルールによって、自動的に不明なアドレスに電子メールが転送されたり、**メモ** フォルダー、**迷惑メール** フォルダー、または **RSS 購読** フォルダーに移動されたりする場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0485-p103">The presence of inbox rules that weren't created by the intended user or the administrator. These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="c0485-123">グローバル アドレス一覧内のユーザーの表示名が変更される。</span><span class="sxs-lookup"><span data-stu-id="c0485-123">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="c0485-124">ユーザーのメールボックスが電子メールの送信をブロックされる。</span><span class="sxs-lookup"><span data-stu-id="c0485-124">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="c0485-125">Microsoft Outlook または Outlook on the web (旧名称は Outlook Web App) の送信済みアイテム フォルダーまたは削除済みアイテム フォルダーに "I'm stuck in London, send money" などのハッキングされたアカウント メッセージが格納される。</span><span class="sxs-lookup"><span data-stu-id="c0485-125">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="c0485-126">名前、電話番号、郵便番号などのめったに変更されないプロフィールが更新される。</span><span class="sxs-lookup"><span data-stu-id="c0485-126">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="c0485-127">複数のパスワードの変更など、異常な資格情報の変更が要求される。</span><span class="sxs-lookup"><span data-stu-id="c0485-127">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="c0485-128">メールの転送が最近追加された。</span><span class="sxs-lookup"><span data-stu-id="c0485-128">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="c0485-129">偽の銀行署名や処方薬署名など、通常とは異なる署名が最近追加された。</span><span class="sxs-lookup"><span data-stu-id="c0485-129">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="c0485-130">ユーザーが上記の兆候のいずれかを報告してきた場合は、詳しい調査を実施する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0485-130">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="c0485-131">Microsoft 365 セキュリティ/コンプライアンス センターと Azure ポータルには、侵害が疑われるユーザー アカウントの活動を調査するためのツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c0485-131">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="c0485-p105">**セキュリティ/コンプライアンス センターの統合監査ログ**: 不審な活動が発生する直前から現在の日付までの範囲で結果をフィルター処理することにより、疑わしいアカウントのすべての活動を確認します。 検索中に活動をフィルタリングしないでください。</span><span class="sxs-lookup"><span data-stu-id="c0485-p105">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date. Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="c0485-134">**EAC の管理監査ログ**: Exchange Online では、Exchange 管理センター (EAC) を使用して管理者監査ログ内のエントリを検索および表示できます。</span><span class="sxs-lookup"><span data-stu-id="c0485-134">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="c0485-135">管理者監査ログには、管理者や管理者特権を割り当てられたユーザーが実行する、Exchange Online PowerShell コマンドレットに基づく特定の操作が記録されます。</span><span class="sxs-lookup"><span data-stu-id="c0485-135">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="c0485-136">管理者監査ログのエントリは、実行されたコマンドレット、使われたパラメーター、コマンドレットを実行したユーザー、および影響を受けたオブジェクトに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="c0485-136">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="c0485-137">**Azure AD ポータルの Azure AD サインイン ログおよびその他のリスク レポート**: 次の列の値を調査します。</span><span class="sxs-lookup"><span data-stu-id="c0485-137">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="c0485-138">IP アドレスの確認</span><span class="sxs-lookup"><span data-stu-id="c0485-138">Review IP address</span></span>
  - <span data-ttu-id="c0485-139">サインインの場所</span><span class="sxs-lookup"><span data-stu-id="c0485-139">sign-in locations</span></span>
  - <span data-ttu-id="c0485-140">サインインの時刻</span><span class="sxs-lookup"><span data-stu-id="c0485-140">sign-in times</span></span>
  - <span data-ttu-id="c0485-141">サインインの成功/失敗</span><span class="sxs-lookup"><span data-stu-id="c0485-141">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="c0485-142">電子メール機能をセキュリティで保護し、侵害が疑われる Microsoft 365 アカウントとメールボックスを復元する方法</span><span class="sxs-lookup"><span data-stu-id="c0485-142">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="c0485-143">アカウントへのアクセスが回復されても、攻撃者がアカウントの制御を再開できるようなバック ドア エントリを追加している場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0485-143">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="c0485-p107">次の手順を最後まで実行して、できるだけ早くアカウントへのアクセスを回復し、乗っ取り犯がアカウントの制御を再開できないことを確認する必要があります。次の手順は、乗っ取り犯がアカウントに追加したかもしれないバック ドア エントリを削除できるように支援します。完了したら、ウイルス スキャンを実行してコンピューターが侵害されていないことを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0485-p107">You must do all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account. These steps help you remove any back-door entries that the hijacker may have added to your account. After you do these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="c0485-147">ステップ 1 ユーザーのパスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="c0485-147">Step 1 Reset the user's password</span></span>

<span data-ttu-id="c0485-148">「[誰かのビジネス パスワードをリセットする](../../admin/add-users/reset-passwords.md#reset-my-admin-password)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c0485-148">Follow the procedures in [Reset a business password for someone](../../admin/add-users/reset-passwords.md#reset-my-admin-password).</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="c0485-149">この時点ではまだ攻撃者がメールボックスへのアクセス権を握っている可能性があるため、意図したユーザーに新しいパスワードを電子メールで送信しないでください。</span><span class="sxs-lookup"><span data-stu-id="c0485-149">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>
>
> - <span data-ttu-id="c0485-150">パスワードは、強力で、大文字と小文字、少なくとも 1 つの数字、および少なくとも 1 つの特殊文字が含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="c0485-150">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>
>
> - <span data-ttu-id="c0485-p108">直近の 5 つのパスワードのいずれかを再利用しないでください。パスワードの履歴要件によって最近のパスワードを再利用できる場合でも、攻撃者が推測できないパスワードを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0485-p108">Don't reuse any of your last five passwords. Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
>
> - <span data-ttu-id="c0485-153">オンプレミス ID が Microsoft 365 とフェデレーションされている場合は、パスワードをオンプレミスで変更してから、侵害を管理者に報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0485-153">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>
>
> - <span data-ttu-id="c0485-154">アプリのパスワードは必ず更新してください。</span><span class="sxs-lookup"><span data-stu-id="c0485-154">Be sure to update app passwords.</span></span> <span data-ttu-id="c0485-155">ユーザー アカウントのパスワードをリセットしても、アプリのパスワードは自動的に取り消されません。</span><span class="sxs-lookup"><span data-stu-id="c0485-155">App passwords aren't automatically revoked when a user account password reset.</span></span> <span data-ttu-id="c0485-156">ユーザーは既存のアプリ パスワードを削除し、新しいパスワードを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0485-156">The user should delete existing app passwords and create new ones.</span></span> <span data-ttu-id="c0485-157">手順については、「[追加セキュリティの検証ページでアプリのパスワードを作成して削除する](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0485-157">For instructions, see [Create and delete app passwords from the Additional security verification page](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span></span>
>
> - <span data-ttu-id="c0485-158">特に、管理者特権を持っているアカウントの侵害を避けるために、多要素認証 (MFA) を有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0485-158">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span> <span data-ttu-id="c0485-159">MFAの詳細については、[[多要素認証をセットアップする](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)] を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0485-159">To learn more about MFA, go to [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="c0485-160">ステップ 2 不審な電子メール転送アドレスを削除する</span><span class="sxs-lookup"><span data-stu-id="c0485-160">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="c0485-161"><https://admin.microsoft.com> で Microsoft 365 管理センターを開く</span><span class="sxs-lookup"><span data-stu-id="c0485-161">Open the Microsoft 365 admin center at <https://admin.microsoft.com></span></span>

2. <span data-ttu-id="c0485-162">[**ユーザー**]\>[**アクティブなユーザー**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c0485-162">Go to **Users** \> **Active users**.</span></span> <span data-ttu-id="c0485-163">問題のユーザ アカウントを検索し、チェックボックスをオンにせずにユーザー (行) を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0485-163">Find the user account in question, and select the user (row) without selecting the checkbox.</span></span>

3. <span data-ttu-id="c0485-164">表示される詳細のポップアップで [**メール**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="c0485-164">In the details flyout that appears, select the **Mail** tab.</span></span>

4. <span data-ttu-id="c0485-165">[**メール転送**] セクションの値が [**適用済み**] の場合、[**メールの転送を管理する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0485-165">If the value in the **Email forwarding** section is **Applied**, click **Manage email forwarding**.</span></span> <span data-ttu-id="c0485-166">表示される [**メールの転送を管理する**] ポップアップで、[**このメールボックスに送信されたすべてのメールを転送する**] をオフにして、[**変更の保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0485-166">In the **Manage email forwarding** flyout that appears, clear **Forward all email sent to this mailbox**, and then click **Save changes**.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="c0485-167">ステップ 3 不審な受信トレイ ルールを無効にする</span><span class="sxs-lookup"><span data-stu-id="c0485-167">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="c0485-168">Outlook on the web を使用して、ユーザーのメールボックスにサインインします。</span><span class="sxs-lookup"><span data-stu-id="c0485-168">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="c0485-169">歯車アイコンをクリックして、**[メール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0485-169">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="c0485-170">**[受信トレイと一括処理ルール (Inbox and sweep rules)]** をクリックして、ルールを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0485-170">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="c0485-171">不審なルールを無効にするか、削除します。</span><span class="sxs-lookup"><span data-stu-id="c0485-171">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="c0485-172">ステップ 4 ユーザーのメールの送信をブロック解除する</span><span class="sxs-lookup"><span data-stu-id="c0485-172">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="c0485-173">侵害が疑われるメールボックスがスパム メールを送信するために不正に使用された場合は、メールボックスのメールの送信がブロックされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c0485-173">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="c0485-174">メールボックスのメールの送信をブロック解除するには、「[迷惑メールを送信した後で制限付きユーザー ポータルからユーザーを削除する](removing-user-from-restricted-users-portal-after-spam.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="c0485-174">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="c0485-175">ステップ 5 オプション: ユーザー アカウントのサインインをブロックする</span><span class="sxs-lookup"><span data-stu-id="c0485-175">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c0485-176">アクセスを有効に戻しても安全なことが確認されるまでは、侵害が疑われるアカウントのサインインをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="c0485-176">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="c0485-177">Microsoft 365 管理センターを開き、[**ユーザー**]\>[**アクティブ ユーザー**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c0485-177">Open the Microsoft 365 admin center and go to **Users** \> **Active users**.</span></span>

2. <span data-ttu-id="c0485-178">ユーザー アカウントを見つけて選択し、![[その他] のアイコン](../../media/ITPro-EAC-MoreOptionsIcon.png)をクリックして、**[サインイン状態の編集]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0485-178">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Edit sign-in status**.</span></span>

3. <span data-ttu-id="c0485-179">表示される [**サインインをブロック**] ウィンドウで、[**このユーザーのサインインをブロックする**] を選択し、[**変更の保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0485-179">On the **Block sign-in** pane that appears, select **Block this user from signing in**, and then click **Save changes**.</span></span>

4. <span data-ttu-id="c0485-180"><admin.protection.outlook.com/ecp/> で Exchange 管理センター (EAC) を開きます。**[受信者]、[メールボックス]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="c0485-180">Open the Exchange admin center (EAC) at <admin.protection.outlook.com/ecp/>, and go to **Recipients > Mailboxes**.</span></span>

5. <span data-ttu-id="c0485-181">ユーザを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="c0485-181">Find and select the select the user.</span></span> <span data-ttu-id="c0485-182">詳細ウィンドウで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0485-182">In the details pane, do the following steps:</span></span>

   - <span data-ttu-id="c0485-183">**[電話と音声の機能]** セクションで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0485-183">In the **Phone and voice features** section, do the following steps:</span></span>

     - <span data-ttu-id="c0485-184">**[Exchange ActiveSync を無効にする]** を選択し、表示される警告で **[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0485-184">Select **Disable Exchange ActiveSync** and then click **Yes** in the warning that appears.</span></span>
     - <span data-ttu-id="c0485-185">**[デバイス用 OWA を無効にする]** を選択し、表示される警告で **[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0485-185">Select **Disable OWA for Devices** and then click **Yes** in the warning that appears.</span></span>

   - <span data-ttu-id="c0485-186">Outlook on the web の **[メール接続]** セクションで **[無効にする]** をクリックして、表示される警告で **[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0485-186">In the **Email Connectivity** section for Outlook on the web, click **Disable** and then click **Yes** in the warning that appears.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="c0485-187">ステップ 6 オプション: すべての管理者役割グループから侵害が疑われるアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="c0485-187">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="c0485-188">管理者役割グループ メンバーシップは、アカウントをセキュリティで保護した後に復元できます。</span><span class="sxs-lookup"><span data-stu-id="c0485-188">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="c0485-189">全体管理者アカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="c0485-189">Sign in with a global administrator account:</span></span>

2. <span data-ttu-id="c0485-190">Microsoft 365 管理センターで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0485-190">In the Microsoft 365 admin center, do the following steps:</span></span>

   1. <span data-ttu-id="c0485-191">[**ユーザー**]\>[**アクティブなユーザー**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="c0485-191">Go to **Users** \> **Active users**.</span></span>
   2. <span data-ttu-id="c0485-192">ユーザー アカウントを見つけて選択し、![[その他] のアイコン](../../media/ITPro-EAC-MoreOptionsIcon.png)をクリックして、**[役割の管理]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="c0485-192">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Manage roles**.</span></span>
   3. <span data-ttu-id="c0485-193">アカウントに割り当てられているすべての管理者の役割を削除します。</span><span class="sxs-lookup"><span data-stu-id="c0485-193">Remove any administrative roles that are assigned to the account.</span></span> <span data-ttu-id="c0485-194">完了したら、[**変更の保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0485-194">When you're finished, click **Save changes**.</span></span>

3. <span data-ttu-id="c0485-195"><https://protection.office.com> のセキュリティ/コンプライアンス センターで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0485-195">In the Security & Compliance Center at <https://protection.office.com>, do the following steps:</span></span>

   <span data-ttu-id="c0485-196">**[アクセス許可]** を選択し、リストから各役割グループを選択して、表示される詳細ポップアップの **[メンバー]** セクションでユーザー アカウントを検索します。</span><span class="sxs-lookup"><span data-stu-id="c0485-196">Select **Permissions**, select each role group in the list and look for the user account in the **Members** section of the details flyout that appears.</span></span> <span data-ttu-id="c0485-197">役割グループにユーザー アカウントが含まれている場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0485-197">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="c0485-198">a.</span><span class="sxs-lookup"><span data-stu-id="c0485-198">a.</span></span> <span data-ttu-id="c0485-199">**[メンバー]** の横にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0485-199">Click **Edit** next to **Members**.</span></span>
   <span data-ttu-id="c0485-200">b.</span><span class="sxs-lookup"><span data-stu-id="c0485-200">b.</span></span> <span data-ttu-id="c0485-201">**[メンバーの選択の編集]** のポップアップが表示されたら、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0485-201">On the **Editing Choose members** flyout that appears, click **Edit**.</span></span>
   <span data-ttu-id="c0485-202">c.</span><span class="sxs-lookup"><span data-stu-id="c0485-202">c.</span></span> <span data-ttu-id="c0485-203">**[メンバーの選択]** のポップアップが表示されたら、ユーザー アカウントを選択し、**[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0485-203">In the **Choose members** flyout that appears, select the user account, and then click **Remove**.</span></span> <span data-ttu-id="c0485-204">完了したら、**[完了]**、**[保存]**、**[閉じる]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0485-204">When you're finished, click **Done**, **Save**, and then **Close**.</span></span>

4. <span data-ttu-id="c0485-205"><admin.protection.outlook.com/ecp/> の EAC で、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0485-205">In the EAC at <admin.protection.outlook.com/ecp/>, do the following steps:</span></span>

   <span data-ttu-id="c0485-206">**[アクセス許可]** を選択して、各役割ループを手動で選択し、詳細ウィンドウの **[メンバー]** セクションでユーザー アカウントを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0485-206">Select **Permissions**, manually select each role group, and in the details pane, verify the user accounts in the **Members** section.</span></span>  <span data-ttu-id="c0485-207">役割グループにユーザー アカウントが含まれている場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0485-207">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="c0485-208">a.</span><span class="sxs-lookup"><span data-stu-id="c0485-208">a.</span></span> <span data-ttu-id="c0485-209">役割グループを選択して、**[編集]**、![[編集] アイコン](../../media/ITPro-EAC-EditIcon.png)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0485-209">Select the role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>
   <span data-ttu-id="c0485-210">b.</span><span class="sxs-lookup"><span data-stu-id="c0485-210">b.</span></span> <span data-ttu-id="c0485-211">**[メンバー]** セクションで、ユーザー アカウントを選択して、**[削除]**、![[削除] アイコン](../../media/ITPro-EAC-RemoveIcon.gif)をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0485-211">In the **Member** section, select the user account, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span> <span data-ttu-id="c0485-212">完了したら、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0485-212">When you're finished, click **Save**.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="c0485-213">ステップ 7 オプション: その他の予防手順</span><span class="sxs-lookup"><span data-stu-id="c0485-213">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="c0485-p119">送信済みアイテムを確認します。連絡先リストに掲載されている人にアカウントが侵害されたことを通知する必要があります。攻撃者は、彼らにお金を要求したり、あなたが外国で足留めされ、お金が必要だなどと偽ったり、彼らにウイルスを送り付けて彼らのコンピューターも乗っ取ろうとしたりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c0485-p119">Make sure that you verify your sent items. You may have to inform people on your contacts list that your account was compromised. The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="c0485-p120">この Exchange アカウントを代替電子メール アカウントとして使用していた他のサービスが侵害されている場合があります。まず、Microsoft 365 サブスクリプションに対してこれらの手順を実行してから、その他のアカウントに対してこれらの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c0485-p120">Any other service that used this Exchange account as its alternative email account may have been compromised. First, do these steps for your Microsoft 365 subscription, and then do these steps for your other accounts.</span></span>

3. <span data-ttu-id="c0485-219">電話番号や住所などの連絡先情報が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0485-219">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="c0485-220">サイバー セキュリティの専門家のように、Microsoft 365 のセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="c0485-220">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="c0485-221">Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c0485-221">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="c0485-222">[Microsoft 365 セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)を使用して、Microsoft 365 テナントをセキュリティで保護するために Microsoft が推奨するベスト プラクティスを実装します。</span><span class="sxs-lookup"><span data-stu-id="c0485-222">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="c0485-p122">最初の 30 日間で完了すべき作業。すぐにユーザーに影響しますが、それほど大きな影響ではありません。</span><span class="sxs-lookup"><span data-stu-id="c0485-p122">Tasks to accomplish in the first 30 days.  These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="c0485-p123">最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="c0485-p123">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="c0485-p124">90 日以降。最初の 90 日間の作業で保護が強化されます。</span><span class="sxs-lookup"><span data-stu-id="c0485-p124">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0485-229">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0485-229">See also</span></span>

- [<span data-ttu-id="c0485-230">Microsoft 365 で Outlook のルールとカスタム フォーム インジェクション攻撃の検出と修復を行う</span><span class="sxs-lookup"><span data-stu-id="c0485-230">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="c0485-231">米国インターネット犯罪苦情センター</span><span class="sxs-lookup"><span data-stu-id="c0485-231">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/Home/Ransomware)

- [<span data-ttu-id="c0485-232">米国証券取引委員会 - "フィッシング" 詐欺</span><span class="sxs-lookup"><span data-stu-id="c0485-232">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="c0485-233">迷惑メールを Microsoft および管理者に直接報告する場合に[迷惑メール報告アドインを使用する](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="c0485-233">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>