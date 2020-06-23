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
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Microsoft 365 で利用可能なツールを使用して、侵害された電子メール アカウントを認識して対処する方法について説明します。
ms.openlocfilehash: 8a7bb98432529bfca70764314d251810d3cdb2a4
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819487"
---
# <a name="responding-to-a-compromised-email-account"></a>侵害された電子メール アカウントへの対応

**概要** 侵害された Microsoft 365 電子メール アカウントを認識して対処する方法について説明します。

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a>侵害された Microsoft 365 電子メール アカウントとは何か?

Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN. When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised. With them the attacker can sign in as the original user and perform illicit actions.
Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive. One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization. When the attacker emails data to external recipients, this is called data exfiltration.

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a>侵害された Microsoft メール アカウントの兆候

Users might notice and report unusual activity in their Microsoft 365 mailboxes. Here are some common symptoms:

- 電子メールの消失や削除などの不審な活動。

- 侵害されたアカウントから電子メールを受信したが、その送信者の**送信済みアイテム** フォルダーに対応する電子メールが存在しない。

- The presence of inbox rules that weren't created by the intended user or the administrator. These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.

- グローバル アドレス一覧内のユーザーの表示名が変更される。

- ユーザーのメールボックスが電子メールの送信をブロックされる。

- Microsoft Outlook または Outlook on the web (旧名称は Outlook Web App) の送信済みアイテム フォルダーまたは削除済みアイテム フォルダーに "I'm stuck in London, send money" などのハッキングされたアカウント メッセージが格納される。

- 名前、電話番号、郵便番号などのめったに変更されないプロフィールが更新される。

- 複数のパスワードの変更など、異常な資格情報の変更が要求される。

- メールの転送が最近追加された。

- 偽の銀行署名や処方薬署名など、通常とは異なる署名が最近追加された。

ユーザーが上記の兆候のいずれかを報告してきた場合は、詳しい調査を実施する必要があります。 Microsoft 365 セキュリティ/コンプライアンス センターと Azure ポータルには、侵害が疑われるユーザー アカウントの活動を調査するためのツールが用意されています。

- **Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date. Do not filter on the activities during the search.

- **EAC の管理監査ログ**: Exchange Online では、Exchange 管理センター (EAC) を使用して管理者監査ログ内のエントリを検索および表示できます。 管理者監査ログには、管理者や管理者特権を割り当てられたユーザーが実行する、Exchange Online PowerShell コマンドレットに基づく特定の操作が記録されます。 管理者監査ログのエントリは、実行されたコマンドレット、使われたパラメーター、コマンドレットを実行したユーザー、および影響を受けたオブジェクトに関する情報を提供します。

- **Azure AD ポータルの Azure AD サインイン ログおよびその他のリスク レポート**: 次の列の値を調査します。

  - IP アドレスの確認

  - サインインの場所

  - サインインの時刻

  - サインインの成功/失敗

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a>電子メール機能をセキュリティで保護し、侵害が疑われる Microsoft 365 アカウントとメールボックスを復元する方法

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

アカウントへのアクセスが回復されても、攻撃者がアカウントの制御を再開できるようなバック ドア エントリを追加している場合があります。

You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account. These steps help you remove any back-door entries that the hijacker may have added to your account. After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.

### <a name="step-1-reset-the-users-password"></a>ステップ 1 ユーザーのパスワードをリセットする

> [!WARNING]
> この時点ではまだ攻撃者がメールボックスへのアクセス権を握っている可能性があるため、意図したユーザーに新しいパスワードを電子メールで送信しないでください。

1. 「[Microsoft 365 Apps for business のパスワードをリセットする](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)」にある、他のユーザーの Microsoft 365 Apps for business パスワードをリセットする手順に従います。

**注**:

- パスワードは、強力で、大文字と小文字、少なくとも 1 つの数字、および少なくとも 1 つの特殊文字が含まれていることを確認してください。

- Don't reuse any of your last five passwords. Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.

- オンプレミス ID が Microsoft 365 とフェデレーションされている場合は、パスワードをオンプレミスで変更してから、侵害を管理者に報告する必要があります。

> [!TIP]
> 特に、管理者特権を持っているアカウントの侵害を避けるために、多要素認証 (MFA) を有効にすることを強くお勧めします。  MFAの詳細については、[多要素認証をセットアップする]を参照してくださいhttps://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)。

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>ステップ 2 不審な電子メール転送アドレスを削除する

1. **[Microsoft 365 管理センター] > [アクティブなユーザー]** を開きます。

2. 対象のユーザー アカウントを探して、**[メール設定]** を展開します。

3. **[メールの転送]** で、**[編集]** をクリックします。

4. 不審な転送アドレスを削除します。

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>ステップ 3 不審な受信トレイ ルールを無効にする

1. Outlook on the web を使用して、ユーザーのメールボックスにサインインします。

2. 歯車アイコンをクリックして、**[メール]** をクリックします。

3. **[受信トレイと一括処理ルール (Inbox and sweep rules)]** をクリックして、ルールを確認します。

4. 不審なルールを無効にするか、削除します。

### <a name="step-4-unblock-the-user-from-sending-mail"></a>ステップ 4 ユーザーのメールの送信をブロック解除する

侵害が疑われるメールボックスがスパム メールを送信するために不正に使用された場合は、メールボックスのメールの送信がブロックされている可能性があります。

メールボックスのメールの送信をブロック解除するには、「[迷惑メールを送信した後で制限付きユーザー ポータルからユーザーを削除する](removing-user-from-restricted-users-portal-after-spam.md)」の手順に従います。

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>ステップ 5 オプション: ユーザー アカウントのサインインをブロックする

> [!IMPORTANT]
> アクセスを有効に戻しても安全なことが確認されるまでは、侵害が疑われるアカウントのサインインをブロックすることができます。

1. Microsoft 365 管理センターに移動します。

2. Microsoft 365 管理センターで、**[ユーザー]** を選択します。

3. アクセスをブロックする従業員を選択し、ユーザー ウィンドウの [**サインイン状態**] の横の [**編集**] を選択します。

4. **[サインイン状態]** ウィンドウで、**[サインインを許可されていない]** を選択してから、**[保存]** を選択します。

5. 管理センターの左下のナビゲーション ウィンドウで、**[管理センター]** を展開し、**[Exchange]** を選択します。

6. Exchange 管理センターで、**[受信者] > [メールボックス]** に移動します。

7. ユーザーを選択して、そのユーザーのプロパティ ページの **[モバイル デバイス]** で、**[Exchange ActivcSync を無効にする]** と **[デバイス用の OWA を無効にする] ** をクリックし、両方に **[はい]** と答えます。

8. **[電子メールの接続性]** で、**[無効にする]** を選択し、**[はい]** と答えます。

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>ステップ 6 オプション: すべての管理者役割グループから侵害が疑われるアカウントを削除する

> [!NOTE]
> 管理者役割グループ メンバーシップは、アカウントをセキュリティで保護した後に復元できます。

1. グローバル管理者アカウントで Microsoft 365 管理センターにサインインし、**[アクティブなユーザー]** を開きます。

2. 侵害が疑われるアカウントを探して、そのアカウントに割り当てられた管理者役割が存在するかどうかを手動で確認します。

3. **[セキュリティとコンプライアンス センター]** を開きます。

4. **[アクセス許可]** をクリックします。

5. Manually review the role groups to see if the suspected compromised account is a member of any of them.  If it is:

   a. 役割グループをクリックし、[**役割グループの編集**] をクリックします。

   b. [**メンバーの選択**] と [**編集**] をクリックして、役割グループからユーザーを削除します。

6. **[Exchange 管理センター]** を開きます。

7. **[アクセス許可]** をクリックします。

8. 役割グループを手動で確認して、侵害された疑いのあるアカウントがいずれかのメンバーであるかどうかを確認します。 もしそれが:

   a. 役割グループをクリックし、[**編集**] をクリックします。

   b. [**メンバー**] セクションを使用して、役割グループからユーザーを削除します。

### <a name="step-7-optional-additional-precautionary-steps"></a>ステップ 7 オプション: その他の予防手順

1. Make sure that you verify your sent items. You may have to inform people on your contacts list that your account was compromised. The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.

2. Any other service that used this Exchange account as its alternative email account may have been compromised. First, perform these steps for your Microsoft 365 subscription, and then perform these steps for your other accounts.

3. 電話番号や住所などの連絡先情報が正しいことを確認します。

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>サイバー セキュリティの専門家のように、Microsoft 365 のセキュリティを強化する

Microsoft 365 サブスクリプションには、データとユーザーを保護するために使用できる強力なセキュリティ機能のセットが用意されています。  [Microsoft 365 セキュリティ ロードマップ - 最初の 30 日間、90 日間、およびそれ以降の最優先事項](security-roadmap.md)を使用して、Microsoft 365 テナントをセキュリティで保護するために Microsoft が推奨するベスト プラクティスを実装します。

- Tasks to accomplish in the first 30 days.  These have immediate affect and are low-impact to your users.

- Tasks to accomplish in 90 days. These take a bit more time to plan and implement but greatly improve your security posture.

- Beyond 90 days. These enhancements build in your first 90 days work.

## <a name="see-also"></a>関連項目

- [Microsoft 365 で Outlook のルールとカスタム フォーム インジェクション攻撃の検出と修復を行う](detect-and-remediate-outlook-rules-forms-attack.md)

- [米国インターネット犯罪苦情センター](https://www.ic3.gov/preventiontips.aspx)

- [米国証券取引委員会 - "フィッシング" 詐欺](https://www.sec.gov/investor/pubs/phishing.htm)

- 迷惑メールを Microsoft および管理者に直接報告する場合に[迷惑メール報告アドインを使用する](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
