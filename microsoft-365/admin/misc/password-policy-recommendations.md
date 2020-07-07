---
title: パスワード ポリシーの推奨事項
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: パスワード攻撃に対する組織のセキュリティを強化する方法と、一般的なパスワードを禁止し、リスク ベースの多要素認証を有効にする理由について説明します。
ms.openlocfilehash: 1d6e399acb83751ec6a45eb0c811dedec394127e
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015925"
---
# <a name="password-policy-recommendations"></a>パスワード ポリシーの推奨事項
 
As the admin of an organization, you're responsible for setting password policy for users in your organization. Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.
  
組織で Microsoft 365 パスワードが期限切れとなる頻度を決める場合は、「[Microsoft 365 のパスワード有効期限ポリシーを設定する](../manage/set-password-expiration-policy.md)」を参照してください。

Microsoft 365 パスワードの詳細については、これらの[関連記事](#related-articles)を参照してください。
  
## <a name="understanding-password-recommendations"></a>パスワードの推奨事項について

適切なパスワード手法は、次のようないくつかのカテゴリに大きく分けられます。
  
- **一般的な攻撃に対抗する** これは、ユーザーがパスワードを入力する場所 (マルウェアを適切に検出できる既知の信頼できるデバイス、検証済みサイト) の選択、およびパスワード (長さと一意性) の選択に関係します。

- **Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen. For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.

- **Understanding human nature** Many valid password practices fail in the face of natural human behaviors. Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality. Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.

## <a name="password-guidelines-for-administrators"></a>管理者向けのパスワード ガイドライン

The primary goal of a more secure password system is password diversity. You want your password policy to contain lots of different and hard to guess passwords. Here are a few recommendations for keeping your organization as secure as possible.
  
- 8 桁の最小長要件を維持する (長ければよいとは限りません)

- Don't require character composition requirements. For example, \*&amp;(^%$

- ユーザー アカウントの必須の定期的なパスワード リセットを求めない

- 最も脆弱なパスワードがシステムで使用されないように、よく使われるパスワードを禁止する

- 業務以外の目的で組織のパスワードを再利用しないようにユーザーを教育する

- 
            [多要素認証](../security-and-compliance/set-up-multi-factor-authentication.md)の登録を適用する

- リスク ベースの多要素認証チャレンジを有効にする

### <a name="password-guidance-for-your-users"></a>ユーザー向けパスワード ガイダンス

Here's some password guidance for users in your organization. Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.
  
- 他の Web サイトで使用しているものと同じ、または似たようなパスワードは使用しない

- 1 単語 (たとえば、 **password** や、 **Iloveyou** などのよく使われるフレーズ) は使用しない

- 友だちと家族の名前と誕生日、お気に入りのバンド、使用しそうなフレーズなど、自分のことをよく知る人でもパスワードを簡単に推測できないようにする

## <a name="some-common-approaches-and-their-negative-impacts"></a>一般的ないくつかの方法とその悪影響

以下は最もよく使われるパスワードの管理手法の一部ですが、調査ではその悪影響について警告しています。
  
### <a name="password-expiration-requirements-for-users"></a>ユーザー向けパスワードの有効期限の要件

Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other. In these cases, the next password can be predicted based on the previous password. Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.
  
### <a name="requiring-long-passwords"></a>長いパスワードを要求する

Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable. For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess. Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents. To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement. 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>複数の文字セットの使用を要求する

Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good. Most systems enforce some level of password complexity requirements. For example, passwords need characters from all three of the following categories:
  
- 大文字

- 小文字

- 英数字以外の文字

Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2. Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l". Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect. Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.
  
## <a name="successful-patterns"></a>成功パターン

上記のものとは対照的に、パスワードに多様性を持たせる推奨事項をいくつか以下に示します。
  
### <a name="ban-common-passwords"></a>よく使われるパスワードを禁止する

The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks. Common user passwords include, **abdcefg**, **password**, **monkey**.
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>組織のパスワードを他の場所で再利用しないようにユーザーを教育する

One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else. The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.
  
### <a name="enforce-multi-factor-authentication-registration"></a>多要素認証の登録を適用する

Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events. Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account. It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords. 
  
詳細については、「[Office 365 ユーザー用の多要素認証を設定する](../security-and-compliance/set-up-multi-factor-authentication.md)」を参照してください。
  
### <a name="enable-risk-based-multi-factor-authentication"></a>リスク ベースの多要素認証を有効にする

リスク ベースの多要素認証では、Microsoft のシステムで不審な動作が検出されたときに、正当なアカウント所有者であることを確認するためにユーザーに対してチャレンジを実行することができます。 
  
## <a name="want-to-know-more-recommended-reading"></a>詳細については、 以下のお勧めの資料を参照してください。

- [Do Strong Web Passwords Accomplish Anything?](https://go.microsoft.com/fwlink/p/?linkid=861008) (強力な Web パスワードでできること)

- [Password Portfolios and the Finite-Effort User](https://go.microsoft.com/fwlink/p/?linkid=861014) (パスワード ポートフォリオとユーザーの有限労力)

- [Preventing Weak Passwords by Reading Users' Minds](https://go.microsoft.com/fwlink/p/?linkid=861015) (ユーザーの心を読み取り、脆弱なパスワードの使用を防ぐ)

- [Choosing Secure Passwords](https://go.microsoft.com/fwlink/p/?linkid=861016) (セキュリティで保護されたパスワードの選択)

- [Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018) (必須パスワードの変更を再検討する時間)

- [Worst Passwords of 2015](https://go.microsoft.com/fwlink/p/?linkid=861020) (2015 年のワースト パスワード)

- [Web からファイルをダウンロードする](https://go.microsoft.com/fwlink/p/?linkid=861029)

## <a name="related-articles"></a>関連記事

[パスワードをリセットする](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

[個別のユーザーのパスワードを無期限に設定する](https://docs.microsoft.com/microsoft-365/admin/add-users/set-password-to-never-expire)

[ユーザーが自分でパスワードをリセットできるようにする](https://docs.microsoft.com/microsoft-365/admin/add-users/let-users-reset-passwords)

[ユーザーのパスワードを再送信する - 管理者向けヘルプ](https://docs.microsoft.com/microsoft-365/admin/add-users/resend-user-password)
