---
title: 侵害された電子メール アカウントへの対応
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.custom: TopSMBIssues
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 侵害された Microsoft 365 電子メール アカウントを認識して対処する方法について説明します
ms.openlocfilehash: 65e3827b578eec2f851c45d9acc69fb7132d01b8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634342"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="6b4a2-103">侵害された電子メール アカウントへの対応</span><span class="sxs-lookup"><span data-stu-id="6b4a2-103">Responding to a Compromised Email Account</span></span>

<span data-ttu-id="6b4a2-104">**概要** 侵害された Microsoft 365 電子メール アカウントを認識して対処する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-104">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="6b4a2-105">侵害された Microsoft 365 電子メール アカウントとは何か?</span><span class="sxs-lookup"><span data-stu-id="6b4a2-105">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="6b4a2-p101">Microsoft 365 のメールボックス、データ、およびその他のサービスへのアクセスは、ユーザー名とパスワードや暗証番号 (PIN) などの資格情報を使用して制御されます。意図したユーザー以外の何者かがこれらの資格情報を盗んだ場合、盗まれた資格情報は侵害されたと見なされます。攻撃者は盗んだ資格情報を使用して、正規のユーザーとしてサインインし、不正な操作を行うことができます。また、攻撃者は盗んだ資格情報を使用して、ユーザーの Microsoft 365 メールボックス、SharePoint フォルダー、または OneDrive 内のファイルにアクセスできます。よく見られるのは、組織の内外の受信者に正規のユーザーとして電子メールを送り付ける攻撃者です。データが攻撃者によって外部の受信者に電子メールで送信される事象をデータ流出と言います。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-p101">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN. When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised. With them the attacker can sign in as the original user and perform illicit actions. Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive. One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization. When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="6b4a2-112">侵害された Microsoft メール アカウントの兆候</span><span class="sxs-lookup"><span data-stu-id="6b4a2-112">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="6b4a2-p102">ユーザーが自分の Microsoft 365 メールボックスでの異常な活動に気付いて報告してくる場合があります。よく見られる兆候を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-p102">Users might notice and report unusual activity in their Microsoft 365 mailboxes. Here are some common symptoms:</span></span>

- <span data-ttu-id="6b4a2-115">電子メールの消失や削除などの不審な活動。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-115">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="6b4a2-116">侵害されたアカウントから電子メールを受信したが、その送信者の**送信済みアイテム** フォルダーに対応する電子メールが存在しない。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="6b4a2-p103">意図したユーザーまたは管理者が作成していない受信トレイ ルールの存在。このようなルールによって、自動的に不明なアドレスに電子メールが転送されたり、**メモ** フォルダー、**迷惑メール** フォルダー、または **RSS 購読**フォルダーに移動されたりする場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-p103">The presence of inbox rules that weren't created by the intended user or the administrator. These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="6b4a2-119">グローバル アドレス一覧内のユーザーの表示名が変更される。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-119">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="6b4a2-120">ユーザーのメールボックスが電子メールの送信をブロックされる。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-120">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="6b4a2-121">Microsoft Outlook または Outlook on the web (旧名称は Outlook Web App) の送信済みアイテム フォルダーまたは削除済みアイテム フォルダーに "I'm stuck in London, send money" などのハッキングされたアカウント メッセージが格納される。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="6b4a2-122">名前、電話番号、郵便番号などのめったに変更されないプロフィールが更新される。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="6b4a2-123">複数のパスワードの変更など、異常な資格情報の変更が要求される。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-123">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="6b4a2-124">メールの転送が最近追加された。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-124">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="6b4a2-125">偽の銀行署名や処方薬署名など、通常とは異なる署名が最近追加された。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="6b4a2-126">ユーザーが上記の兆候のいずれかを報告してきた場合は、詳しい調査を実施する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-126">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="6b4a2-127">Microsoft 365 セキュリティ/コンプライアンス センターと Azure ポータルには、侵害が疑われるユーザー アカウントの活動を調査するためのツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-127">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="6b4a2-p105">**セキュリティ/コンプライアンス センターの統合監査ログ**: 不審な活動が発生する直前から現在の日付までの範囲で結果をフィルター処理することにより、疑わしいアカウントのすべての活動を確認します。 検索中に活動をフィルタリングしないでください。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-p105">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date. Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="6b4a2-130">**EAC の管理監査ログ**: Exchange Online では、Exchange 管理センター (EAC) を使用して管理者監査ログ内のエントリを検索および表示できます。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-130">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="6b4a2-131">管理者監査ログには、管理者や管理者特権を割り当てられたユーザーが実行する、Exchange Online PowerShell コマンドレットに基づく特定の操作が記録されます。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-131">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="6b4a2-132">管理者監査ログのエントリは、実行されたコマンドレット、使われたパラメーター、コマンドレットを実行したユーザー、および影響を受けたオブジェクトに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-132">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="6b4a2-133">**Azure AD ポータルの Azure AD サインイン ログおよびその他のリスク レポート**: 次の列の値を調査します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-133">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="6b4a2-134">IP アドレスの確認</span><span class="sxs-lookup"><span data-stu-id="6b4a2-134">Review IP address</span></span>

  - <span data-ttu-id="6b4a2-135">サインインの場所</span><span class="sxs-lookup"><span data-stu-id="6b4a2-135">sign-in locations</span></span>

  - <span data-ttu-id="6b4a2-136">サインインの時刻</span><span class="sxs-lookup"><span data-stu-id="6b4a2-136">sign-in times</span></span>

  - <span data-ttu-id="6b4a2-137">サインインの成功/失敗</span><span class="sxs-lookup"><span data-stu-id="6b4a2-137">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="6b4a2-138">電子メール機能をセキュリティで保護し、侵害が疑われる Microsoft 365 アカウントとメールボックスを復元する方法</span><span class="sxs-lookup"><span data-stu-id="6b4a2-138">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="6b4a2-139">アカウントへのアクセスが回復されても、攻撃者がアカウントの制御を再開できるようなバック ドア エントリを追加している場合があります。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-139">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="6b4a2-p107">次の手順を最後まで実行して、できるだけ早くアカウントへのアクセスを回復し、乗っ取り犯がアカウントの制御を再開できないことを確認する必要があります。次の手順は、乗っ取り犯がアカウントに追加したかもしれないバック ドア エントリを削除できるように支援します。この手順を完了したら、ウイルス スキャンを実行してコンピューターが侵害されていないことを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-p107">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account. These steps help you remove any back-door entries that the hijacker may have added to your account. After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="6b4a2-143">ステップ 1 ユーザーのパスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="6b4a2-143">Step 1 Reset the user's password</span></span>

> [!WARNING]
> <span data-ttu-id="6b4a2-144">この時点ではまだ攻撃者がメールボックスへのアクセス権を握っている可能性があるため、意図したユーザーに新しいパスワードを電子メールで送信しないでください。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-144">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>

1. <span data-ttu-id="6b4a2-145">「[Microsoft 365 Apps for business のパスワードをリセットする](https://docs.microsoft.com/office365/admin/add-users/reset-passwords)」にある、他のユーザーの Microsoft 365 Apps for business パスワードをリセットする手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-145">Follow the Reset a Microsoft 365 Apps for business password for someone else procedures in [Reset Microsoft 365 Apps for business passwords](https://docs.microsoft.com/office365/admin/add-users/reset-passwords)</span></span>

<span data-ttu-id="6b4a2-146">**注**:</span><span class="sxs-lookup"><span data-stu-id="6b4a2-146">**Notes**:</span></span>

- <span data-ttu-id="6b4a2-147">パスワードは、強力で、大文字と小文字、少なくとも 1 つの数字、および少なくとも 1 つの特殊文字が含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-147">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>

- <span data-ttu-id="6b4a2-p108">直近の 5 つのパスワードのいずれかを再利用しないでください。パスワードの履歴要件によって最近のパスワードを再利用できる場合でも、攻撃者が推測できないパスワードを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-p108">Don't reuse any of your last five passwords. Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>

- <span data-ttu-id="6b4a2-150">オンプレミス ID が Microsoft 365 とフェデレーションされている場合は、パスワードをオンプレミスで変更してから、侵害を管理者に報告する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-150">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>

> [!TIP]
> <span data-ttu-id="6b4a2-151">特に、管理者特権を持っているアカウントの侵害を避けるために、多要素認証 (MFA) を有効にすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-151">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span>  <span data-ttu-id="6b4a2-152">MFA の詳細については、[こちら](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-152">You can learn more about MFA [here](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="6b4a2-153">ステップ 2 不審な電子メール転送アドレスを削除する</span><span class="sxs-lookup"><span data-stu-id="6b4a2-153">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="6b4a2-154">**[Microsoft 365 管理センター] > [アクティブなユーザー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-154">Open the **Microsoft 365 admin center > Active Users**.</span></span>

2. <span data-ttu-id="6b4a2-155">対象のユーザー アカウントを探して、**[メール設定]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-155">Find the user account in question and expand **Mail Settings**.</span></span>

3. <span data-ttu-id="6b4a2-156">**[メールの転送]** で、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-156">For **Email forwarding**, click **Edit**.</span></span>

4. <span data-ttu-id="6b4a2-157">不審な転送アドレスを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-157">Remove any suspicious forwarding addresses.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="6b4a2-158">ステップ 3 不審な受信トレイ ルールを無効にする</span><span class="sxs-lookup"><span data-stu-id="6b4a2-158">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="6b4a2-159">Outlook on the web を使用して、ユーザーのメールボックスにサインインします。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-159">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="6b4a2-160">歯車アイコンをクリックして、**[メール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-160">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="6b4a2-161">**[受信トレイと一括処理ルール (Inbox and sweep rules)]** をクリックして、ルールを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-161">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="6b4a2-162">不審なルールを無効にするか、削除します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-162">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="6b4a2-163">ステップ 4 ユーザーのメールの送信をブロック解除する</span><span class="sxs-lookup"><span data-stu-id="6b4a2-163">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="6b4a2-164">侵害が疑われるメールボックスがスパム メールを送信するために不正に使用された場合は、メールボックスのメールの送信がブロックされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-164">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="6b4a2-165">メールボックスのメールの送信をブロック解除するには、「[迷惑メールを送信した後で制限付きユーザー ポータルからユーザーを削除する](removing-user-from-restricted-users-portal-after-spam.md)」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-165">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="6b4a2-166">ステップ 5 オプション: ユーザー アカウントのサインインをブロックする</span><span class="sxs-lookup"><span data-stu-id="6b4a2-166">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b4a2-167">アクセスを有効に戻しても安全なことが確認されるまでは、侵害が疑われるアカウントのサインインをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-167">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="6b4a2-168">Microsoft 365 管理センターに移動します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-168">Go to the Microsoft 365 admin center.</span></span>

2. <span data-ttu-id="6b4a2-169">Microsoft 365 管理センターで、**[ユーザー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-169">In the Microsoft 365 admin center, select **Users**.</span></span>

3. <span data-ttu-id="6b4a2-170">アクセスをブロックする従業員を選択し、ユーザー ウィンドウの [**サインイン状態**] の横の [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-170">Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane.</span></span>

4. <span data-ttu-id="6b4a2-171">**[サインイン状態]** ウィンドウで、**[サインインを許可されていない]** を選択してから、**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-171">On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**.</span></span>

5. <span data-ttu-id="6b4a2-172">管理センターの左下のナビゲーション ウィンドウで、**[管理センター]** を展開し、**[Exchange]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-172">In the Admin center, in the lower-left navigation pane, expand **Admin Centers** and select **Exchange**.</span></span>

6. <span data-ttu-id="6b4a2-173">Exchange 管理センターで、**[受信者] > [メールボックス]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-173">In the Exchange admin center, navigate to **Recipients > Mailboxes**.</span></span>

7. <span data-ttu-id="6b4a2-174">ユーザーを選択して、そのユーザーのプロパティ ページの **[モバイル デバイス]** で、**[Exchange ActivcSync を無効にする]** と \*\*[デバイス用の OWA を無効にする] \*\* をクリックし、両方に **[はい]** と答えます。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-174">Select the user, and on the user properties page, under **Mobile Devices**, click **Disable Exchange ActivcSync** and **Disable OWA for Devices** and answer **yes** to both.</span></span>

8. <span data-ttu-id="6b4a2-175">**[電子メールの接続性]** で、**[無効にする]** を選択し、**[はい]** と答えます。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-175">Under **Email Connectivity**, **Disable** and answer **yes**.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="6b4a2-176">ステップ 6 オプション: すべての管理者役割グループから侵害が疑われるアカウントを削除する</span><span class="sxs-lookup"><span data-stu-id="6b4a2-176">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="6b4a2-177">管理者役割グループ メンバーシップは、アカウントをセキュリティで保護した後に復元できます。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-177">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="6b4a2-178">グローバル管理者アカウントで Microsoft 365 管理センターにサインインし、**[アクティブなユーザー]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-178">Sign in to the Microsoft 365 admin center with a global administrator account and open **Active Users**.</span></span>

2. <span data-ttu-id="6b4a2-179">侵害が疑われるアカウントを探して、そのアカウントに割り当てられた管理者役割が存在するかどうかを手動で確認します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-179">Find the suspected compromised account and manually check to see if there are any administrative roles assigned to the account.</span></span>

3. <span data-ttu-id="6b4a2-180">**[セキュリティとコンプライアンス センター]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-180">Open the **Security & Compliance Center**.</span></span>

4. <span data-ttu-id="6b4a2-181">**[アクセス許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-181">Click **Permissions**.</span></span>

5. <span data-ttu-id="6b4a2-p110">役割グループを手動で確認して、侵害された疑いのあるアカウントがいずれかのメンバーであるかどうかを確認します。もしそれが:</span><span class="sxs-lookup"><span data-stu-id="6b4a2-p110">Manually review the role groups to see if the suspected compromised account is a member of any of them.  If it is:</span></span>

   <span data-ttu-id="6b4a2-184">a.</span><span class="sxs-lookup"><span data-stu-id="6b4a2-184">a.</span></span> <span data-ttu-id="6b4a2-185">役割グループをクリックし、[**役割グループの編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-185">Click the role group and click **Edit Role Group**.</span></span>

   <span data-ttu-id="6b4a2-186">b.</span><span class="sxs-lookup"><span data-stu-id="6b4a2-186">b.</span></span> <span data-ttu-id="6b4a2-187">[**メンバーの選択**] と [**編集**] をクリックして、役割グループからユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-187">Click **Chose Members** and **Edit** to remove the user from the role group.</span></span>

6. <span data-ttu-id="6b4a2-188">**[Exchange 管理センター]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-188">Open the **Exchange admin center**.</span></span>

7. <span data-ttu-id="6b4a2-189">**[アクセス許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-189">Click **Permissions**.</span></span>

8. <span data-ttu-id="6b4a2-190">役割グループを手動で確認して、侵害された疑いのあるアカウントがいずれかのメンバーであるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-190">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span> <span data-ttu-id="6b4a2-191">もしそれが:</span><span class="sxs-lookup"><span data-stu-id="6b4a2-191">If it is:</span></span>

   <span data-ttu-id="6b4a2-192">a.</span><span class="sxs-lookup"><span data-stu-id="6b4a2-192">a.</span></span> <span data-ttu-id="6b4a2-193">役割グループをクリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-193">Click the role group and click **Edit**.</span></span>

   <span data-ttu-id="6b4a2-194">b.</span><span class="sxs-lookup"><span data-stu-id="6b4a2-194">b.</span></span> <span data-ttu-id="6b4a2-195">[**メンバー**] セクションを使用して、役割グループからユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-195">Use the **members** section to remove the user from the role group.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="6b4a2-196">ステップ 7 オプション: その他の予防手順</span><span class="sxs-lookup"><span data-stu-id="6b4a2-196">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="6b4a2-p116">送信済みアイテムを確認します。連絡先リストに掲載されている人にアカウントが侵害されたことを通知する必要があります。攻撃者は、彼らにお金を要求したり、あなたが外国で足留めされ、お金が必要だなどと偽ったり、彼らにウイルスを送り付けて彼らのコンピューターも乗っ取ろうとしたりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-p116">Make sure that you verify your sent items. You may have to inform people on your contacts list that your account was compromised. The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="6b4a2-p117">この Exchange アカウントを代替電子メール アカウントとして使用していた他のサービスが侵害されている場合があります。まず、Microsoft 365 サブスクリプションに対してこれらの手順を実行してから、その他のアカウントに対してこれらの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-p117">Any other service that used this Exchange account as its alternative email account may have been compromised. First, perform these steps for your Microsoft 365 subscription, and then perform these steps for your other accounts.</span></span>

3. <span data-ttu-id="6b4a2-202">電話番号や住所などの連絡先情報が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-202">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="6b4a2-203">サイバー セキュリティの専門家のように、Microsoft 365 のセキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="6b4a2-203">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="6b4a2-204">Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能のセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-204">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="6b4a2-205">[Microsoft 365 セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)を使用して、Microsoft 365 テナントをセキュリティで保護するために Microsoft が推奨するベスト プラクティスを実装します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-205">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="6b4a2-p119">最初の 30 日間で完了すべき作業。すぐにユーザーに影響しますが、それほど大きな影響ではありません。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-p119">Tasks to accomplish in the first 30 days.  These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="6b4a2-p120">最初の 90 日間で完了すべき作業。作業の計画と実装に少し時間がかかりますが、セキュリティ体制は大幅に向上します。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-p120">Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="6b4a2-p121">90 日以降。最初の 90 日間の作業で保護が強化されます。</span><span class="sxs-lookup"><span data-stu-id="6b4a2-p121">Beyond 90 days. These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b4a2-212">関連項目</span><span class="sxs-lookup"><span data-stu-id="6b4a2-212">See also</span></span>

- [<span data-ttu-id="6b4a2-213">Microsoft 365 で Outlook のルールとカスタム フォーム インジェクション攻撃の検出と修復を行う</span><span class="sxs-lookup"><span data-stu-id="6b4a2-213">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="6b4a2-214">米国インターネット犯罪苦情センター</span><span class="sxs-lookup"><span data-stu-id="6b4a2-214">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="6b4a2-215">米国証券取引委員会 - "フィッシング" 詐欺</span><span class="sxs-lookup"><span data-stu-id="6b4a2-215">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="6b4a2-216">迷惑メールを Microsoft および管理者に直接報告する場合に[迷惑メール報告アドインを使用する](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="6b4a2-216">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
