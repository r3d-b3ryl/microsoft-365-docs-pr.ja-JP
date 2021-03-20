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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: パスワード攻撃に対する組織のセキュリティを強化する方法と、一般的なパスワードを禁止し、リスク ベースの多要素認証を有効にする理由について説明します。
ms.openlocfilehash: ca9a88b0bb154416837254d785cf9cfee8876ae6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914728"
---
# <a name="password-policy-recommendations"></a><span data-ttu-id="f7d1d-103">パスワード ポリシーの推奨事項</span><span class="sxs-lookup"><span data-stu-id="f7d1d-103">Password policy recommendations</span></span>

<span data-ttu-id="f7d1d-p101">組織の管理者は、組織内のユーザー向けのパスワード ポリシーを設定する必要があります。パスワード ポリシーの設定は複雑でわかりにくい場合があります。この記事では、パスワード攻撃からの組織の保護を強化するための推奨事項を示します。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-p101">As the admin of an organization, you're responsible for setting password policy for users in your organization. Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span></span>
  
<span data-ttu-id="f7d1d-106">組織で Microsoft 365 パスワードが期限切れとなる頻度を決める場合は、「[Microsoft 365 のパスワード有効期限ポリシーを設定する](../manage/set-password-expiration-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-106">To determine how often Microsoft 365 passwords expire in your organization, see [Set password expiration policy for Microsoft 365](../manage/set-password-expiration-policy.md).</span></span>

<span data-ttu-id="f7d1d-107">Microsoft 365 パスワードの詳細については、これらの[関連記事](#related-articles)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-107">For more information about Microsoft 365 passwords, see these [related articles](#related-articles).</span></span>
  
## <a name="understanding-password-recommendations"></a><span data-ttu-id="f7d1d-108">パスワードの推奨事項について</span><span class="sxs-lookup"><span data-stu-id="f7d1d-108">Understanding password recommendations</span></span>

<span data-ttu-id="f7d1d-109">適切なパスワード手法は、次のようないくつかのカテゴリに大きく分けられます。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-109">Good password practices fall into a few broad categories:</span></span>
  
- <span data-ttu-id="f7d1d-110">**一般的な攻撃に対抗する** これは、ユーザーがパスワードを入力する場所 (マルウェアを適切に検出できる既知の信頼できるデバイス、検証済みサイト) の選択、およびパスワード (長さと一意性) の選択に関係します。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-110">**Resisting common attacks** This involves the choice of where users enter passwords (known and trusted devices with good malware detection, validated sites), and the choice of what password to choose (length and uniqueness).</span></span>

- <span data-ttu-id="f7d1d-p102">**成功した攻撃を含める** 成功したハッカーの攻撃を含めるのは、特定のサービスへの公開を制限するためです。また、ユーザーのパスワードが盗まれた場合に、その損害を完全に防ぐことにもなります。たとえば、ソーシャル ネットワーク資格情報の侵害により、銀行口座が攻撃を受けやすくならないようにしたり、十分に保護されていないアカウントで重要なアカウントのリセット リンクが受け入れられないようにしたりします。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-p102">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen. For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span></span>

- <span data-ttu-id="f7d1d-p103">**人間の性質を理解する** 多くの有効なパスワード手法では、自然な人間の行動には十分対応できません。調査により、ユーザーに適用されるほとんどすべてのルールはパスワードの品質を弱化することがわかっているため、人間の性質を理解することが重要です。長さの要件、特殊文字の要件、パスワード変更の要件はすべて、パスワードを正規化することになるため、攻撃者はパスワードを簡単に推測したり、解読したりすることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-p103">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors. Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality. Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span></span>

## <a name="password-guidelines-for-administrators"></a><span data-ttu-id="f7d1d-116">管理者向けのパスワード ガイドライン</span><span class="sxs-lookup"><span data-stu-id="f7d1d-116">Password guidelines for administrators</span></span>

<span data-ttu-id="f7d1d-p104">より安全なパスワード システムの最大の目的は、パスワードの多様性です。パスワードを推測しにくくするためのパスワード ポリシーが必要です。組織を可能な限り安全な状態に保つための推奨事項をいくつか以下に示します。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-p104">The primary goal of a more secure password system is password diversity. You want your password policy to contain lots of different and hard to guess passwords. Here are a few recommendations for keeping your organization as secure as possible.</span></span>
  
- <span data-ttu-id="f7d1d-120">8 桁の最小長要件を維持する (長ければよいとは限りません)</span><span class="sxs-lookup"><span data-stu-id="f7d1d-120">Maintain an 8-character minimum length requirement (longer isn't necessarily better)</span></span>

- <span data-ttu-id="f7d1d-p105">文字構成の要件を求めない。たとえば、\*&amp;(^%$ などです。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-p105">Don't require character composition requirements. For example, \*&amp;(^%$</span></span>

- <span data-ttu-id="f7d1d-123">ユーザー アカウントの必須の定期的なパスワード リセットを求めない</span><span class="sxs-lookup"><span data-stu-id="f7d1d-123">Don't require mandatory periodic password resets for user accounts</span></span>

- <span data-ttu-id="f7d1d-124">最も脆弱なパスワードがシステムで使用されないように、よく使われるパスワードを禁止する</span><span class="sxs-lookup"><span data-stu-id="f7d1d-124">Ban common passwords, to keep the most vulnerable passwords out of your system</span></span>

- <span data-ttu-id="f7d1d-125">業務以外の目的で組織のパスワードを再利用しないようにユーザーを教育する</span><span class="sxs-lookup"><span data-stu-id="f7d1d-125">Educate your users to not re-use their organization passwords for non-work related purposes</span></span>

- <span data-ttu-id="f7d1d-126">
            [多要素認証](../security-and-compliance/set-up-multi-factor-authentication.md)の登録を適用する</span><span class="sxs-lookup"><span data-stu-id="f7d1d-126">Enforce registration for [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)</span></span>

- <span data-ttu-id="f7d1d-127">リスク ベースの多要素認証チャレンジを有効にする</span><span class="sxs-lookup"><span data-stu-id="f7d1d-127">Enable risk-based multi-factor authentication challenges</span></span>

### <a name="password-guidance-for-your-users"></a><span data-ttu-id="f7d1d-128">ユーザー向けパスワード ガイダンス</span><span class="sxs-lookup"><span data-stu-id="f7d1d-128">Password guidance for your users</span></span>

<span data-ttu-id="f7d1d-p106">組織内のユーザー向けパスワード ガイダンスをいくつか以下に示します。ユーザーに以下の推奨事項を認識してもらい、組織レベルで推奨されるパスワード ポリシーを適用するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-p106">Here's some password guidance for users in your organization. Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span></span>
  
- <span data-ttu-id="f7d1d-131">他の Web サイトで使用しているものと同じ、または似たようなパスワードは使用しない</span><span class="sxs-lookup"><span data-stu-id="f7d1d-131">Don't use a password that is the same or similar to one you use on any other websites</span></span>

- <span data-ttu-id="f7d1d-132">1 単語 (たとえば、 **password** や、 **Iloveyou** などのよく使われるフレーズ) は使用しない</span><span class="sxs-lookup"><span data-stu-id="f7d1d-132">Don't use a single word, for example, **password**, or a commonly-used phrase like **Iloveyou**</span></span>

- <span data-ttu-id="f7d1d-133">友だちと家族の名前と誕生日、お気に入りのバンド、使用しそうなフレーズなど、自分のことをよく知る人でもパスワードを簡単に推測できないようにする</span><span class="sxs-lookup"><span data-stu-id="f7d1d-133">Make passwords hard to guess, even by those who know a lot about you, such as the names and birthdays of your friends and family, your favorite bands, and phrases you like to use</span></span>

## <a name="some-common-approaches-and-their-negative-impacts"></a><span data-ttu-id="f7d1d-134">一般的ないくつかの方法とその悪影響</span><span class="sxs-lookup"><span data-stu-id="f7d1d-134">Some common approaches and their negative impacts</span></span>

<span data-ttu-id="f7d1d-135">以下は最もよく使われるパスワードの管理手法の一部ですが、調査ではその悪影響について警告しています。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-135">These are some of the most commonly used password management practices, but research warns us about the negative impacts of them.</span></span>
  
### <a name="password-expiration-requirements-for-users"></a><span data-ttu-id="f7d1d-136">ユーザー向けパスワードの有効期限の要件</span><span class="sxs-lookup"><span data-stu-id="f7d1d-136">Password expiration requirements for users</span></span>

<span data-ttu-id="f7d1d-p107">パスワードの有効期限の要件にはメリットもありますがデメリットのほうが多くなります。これらの要件に従うと、ユーザーは互いに密接に関係している一連の単語と数字で構成される、予測可能なパスワードを選択することになるためです。このような場合、次のパスワードは前のパスワードに基づいて予測することができます。パスワードの有効期限の要件に抑制効果はありません。サイバー犯罪者は、ほとんどの場合、資格情報を侵害するとすぐに使用するためです。詳しくは、「[必須パスワードの変更を再検討する時間](https://go.microsoft.com/fwlink/p/?linkid=861018)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-p107">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other. In these cases, the next password can be predicted based on the previous password. Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them. Check out [Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018) for more info.</span></span>
  
### <a name="requiring-long-passwords"></a><span data-ttu-id="f7d1d-141">長いパスワードを要求する</span><span class="sxs-lookup"><span data-stu-id="f7d1d-141">Requiring long passwords</span></span>

<span data-ttu-id="f7d1d-p108">パスワードの長さ要件 (約 10 文字を超える) により、ユーザーの行動が予測可能で望ましくないものとなる可能性があります。たとえば、16 文字のパスワードを使用するよう求められたユーザーは、文字の長さ要件を満たすものの、推測しにくいものではない **fourfourfourfour** や **passwordpassword** などの繰り返しパターンを選ぶ可能性があります。さらに、長さ要件は、ユーザーがパスワードを書き留めたり、ドキュメントに暗号化されていないパスワードを保存するなど、他の安全でない手法を採用する機会を増やすことになります。ユーザーが一意のパスワードを考えるように、適切な 8 文字の最小長要件を維持することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-p108">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable. For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess. Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents. To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span></span>
  
### <a name="requiring-the-use-of-multiple-character-sets"></a><span data-ttu-id="f7d1d-146">複数の文字セットの使用を要求する</span><span class="sxs-lookup"><span data-stu-id="f7d1d-146">Requiring the use of multiple character sets</span></span>

<span data-ttu-id="f7d1d-p109">パスワードの複雑さ要件により、キー スペースが減り、ユーザーが予測可能な方法で行動することになり、これでは元も子もありません。ほとんどのシステムでは、ある程度のパスワードの複雑さ要件を適用します。たとえば、パスワードには、次のカテゴリの 3 つすべての文字が必要となります。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-p109">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good. Most systems enforce some level of password complexity requirements. For example, passwords need characters from all three of the following categories:</span></span>
  
- <span data-ttu-id="f7d1d-150">大文字</span><span class="sxs-lookup"><span data-stu-id="f7d1d-150">uppercase characters</span></span>

- <span data-ttu-id="f7d1d-151">小文字</span><span class="sxs-lookup"><span data-stu-id="f7d1d-151">lowercase characters</span></span>

- <span data-ttu-id="f7d1d-152">英数字以外の文字</span><span class="sxs-lookup"><span data-stu-id="f7d1d-152">non-alphanumeric characters</span></span>

<span data-ttu-id="f7d1d-p110">ほとんどのユーザーは似たようなパターンを使用します。たとえば、最初の位置が大文字、最後が記号、最後の 2 つが数字などです。サイバー犯罪者はこれを認識しているため、最も一般的な置換文字、つまり、"s" の場合は "$"、"a" の場合は "@"、"l" の場合は "1" を使用して辞書攻撃を実行します。ユーザーに大文字、小文字、数字、特殊文字の組み合わせを選択させるのは逆効果です。複雑さ要件によっては、セキュリティで保護された覚えやすいパスワードをユーザーが使用できないようにするものもあり、ユーザーにセキュリティ レベルの低い覚えにくいパスワードを思い付かせることになります。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-p110">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2. Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l". Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect. Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span></span>
  
## <a name="successful-patterns"></a><span data-ttu-id="f7d1d-157">成功パターン</span><span class="sxs-lookup"><span data-stu-id="f7d1d-157">Successful Patterns</span></span>

<span data-ttu-id="f7d1d-158">上記のものとは対照的に、パスワードに多様性を持たせる推奨事項をいくつか以下に示します。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-158">In contrast, here are some recommendations in encouraging password diversity.</span></span>
  
### <a name="ban-common-passwords"></a><span data-ttu-id="f7d1d-159">よく使われるパスワードを禁止する</span><span class="sxs-lookup"><span data-stu-id="f7d1d-159">Ban common passwords</span></span>

<span data-ttu-id="f7d1d-p111">ユーザーがパスワードを作成するときに認識させる最も重要なパスワード要件は、パスワードの総当たり攻撃に対する組織の脆弱性を減らすためによく使われるパスワードの使用を禁止することです。よく使われるユーザー パスワードには、 **abdcefg**、**password**、**monkey** などがあります。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-p111">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks. Common user passwords include, **abcdefg**, **password**, **monkey**.</span></span>
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a><span data-ttu-id="f7d1d-162">組織のパスワードを他の場所で再利用しないようにユーザーを教育する</span><span class="sxs-lookup"><span data-stu-id="f7d1d-162">Educate users to not re-use organization passwords anywhere else</span></span>

<span data-ttu-id="f7d1d-p112">組織内のユーザーに伝える最も重要なメッセージの 1 つは、組織のパスワードを他の場所で再利用しないということです。外部の Web サイトで組織のパスワードを使用すると、サイバー犯罪者がこれらのパスワードを侵害する可能性が高くなります。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-p112">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else. The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span></span>
  
### <a name="enforce-multi-factor-authentication-registration"></a><span data-ttu-id="f7d1d-165">多要素認証の登録を適用する</span><span class="sxs-lookup"><span data-stu-id="f7d1d-165">Enforce Multi-Factor Authentication registration</span></span>

<span data-ttu-id="f7d1d-p113">ユーザーが、代替メール アドレス、電話番号、プッシュ通知用に登録されたデバイスなどの連絡先とセキュリティ情報を更新し、セキュリティ チャレンジに応答して、セキュリティ イベントに関する通知を受け取れるようにします。更新された連絡先とセキュリティ情報は、ユーザーが万が一パスワードを忘れてしまった場合、または他のユーザーがアカウントを引き継ごうとした場合の本人確認に役立ちます。また、ログイン試行やパスワード変更など、セキュリティ イベントが発生した場合には、帯域外の通知チャネルが提供されます。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-p113">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events. Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account. It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span></span> 
  
<span data-ttu-id="f7d1d-169">詳細については、「[Office 365 ユーザー用の多要素認証を設定する](../security-and-compliance/set-up-multi-factor-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-169">To learn more, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>
  
### <a name="enable-risk-based-multi-factor-authentication"></a><span data-ttu-id="f7d1d-170">リスク ベースの多要素認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="f7d1d-170">Enable risk-based multi-factor authentication</span></span>

<span data-ttu-id="f7d1d-171">リスク ベースの多要素認証では、Microsoft のシステムで不審な動作が検出されたときに、正当なアカウント所有者であることを確認するためにユーザーに対してチャレンジを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-171">Risk-based multi-factor authentication ensures that when our system detects suspicious activity, it can challenge the user to ensure that they are the legitimate account owner.</span></span> 
  
## <a name="want-to-know-more-recommended-reading"></a><span data-ttu-id="f7d1d-172">詳細については、</span><span class="sxs-lookup"><span data-stu-id="f7d1d-172">Want to know more?</span></span> <span data-ttu-id="f7d1d-173">以下のお勧めの資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f7d1d-173">Recommended reading</span></span>

- <span data-ttu-id="f7d1d-174">[Do Strong Web Passwords Accomplish Anything?](https://go.microsoft.com/fwlink/p/?linkid=861008) (強力な Web パスワードでできること)</span><span class="sxs-lookup"><span data-stu-id="f7d1d-174">[Do Strong Web Passwords Accomplish Anything?](https://go.microsoft.com/fwlink/p/?linkid=861008)</span></span>

- <span data-ttu-id="f7d1d-175">[Password Portfolios and the Finite-Effort User](https://go.microsoft.com/fwlink/p/?linkid=861014) (パスワード ポートフォリオとユーザーの有限労力)</span><span class="sxs-lookup"><span data-stu-id="f7d1d-175">[Password Portfolios and the Finite-Effort User](https://go.microsoft.com/fwlink/p/?linkid=861014)</span></span>

- <span data-ttu-id="f7d1d-176">[Preventing Weak Passwords by Reading Users' Minds](https://go.microsoft.com/fwlink/p/?linkid=861015) (ユーザーの心を読み取り、脆弱なパスワードの使用を防ぐ)</span><span class="sxs-lookup"><span data-stu-id="f7d1d-176">[Preventing Weak Passwords by Reading Users' Minds](https://go.microsoft.com/fwlink/p/?linkid=861015)</span></span>

- <span data-ttu-id="f7d1d-177">[Choosing Secure Passwords](https://go.microsoft.com/fwlink/p/?linkid=861016) (セキュリティで保護されたパスワードの選択)</span><span class="sxs-lookup"><span data-stu-id="f7d1d-177">[Choosing Secure Passwords](https://go.microsoft.com/fwlink/p/?linkid=861016)</span></span>

- <span data-ttu-id="f7d1d-178">[Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018) (必須パスワードの変更を再検討する時間)</span><span class="sxs-lookup"><span data-stu-id="f7d1d-178">[Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018)</span></span>

- <span data-ttu-id="f7d1d-179">[Worst Passwords of 2015](https://go.microsoft.com/fwlink/p/?linkid=861020) (2015 年のワースト パスワード)</span><span class="sxs-lookup"><span data-stu-id="f7d1d-179">[Worst Passwords of 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)</span></span>

## <a name="related-articles"></a><span data-ttu-id="f7d1d-180">関連記事</span><span class="sxs-lookup"><span data-stu-id="f7d1d-180">Related articles</span></span>

[<span data-ttu-id="f7d1d-181">パスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="f7d1d-181">Reset passwords</span></span>](../add-users/reset-passwords.md)

[<span data-ttu-id="f7d1d-182">個別のユーザーのパスワードを無期限に設定する</span><span class="sxs-lookup"><span data-stu-id="f7d1d-182">Set an individual user's password to never expire</span></span>](../add-users/set-password-to-never-expire.md)

[<span data-ttu-id="f7d1d-183">ユーザーが自分でパスワードをリセットできるようにする</span><span class="sxs-lookup"><span data-stu-id="f7d1d-183">Let users reset their own passwords</span></span>](../add-users/let-users-reset-passwords.md)

[<span data-ttu-id="f7d1d-184">ユーザーのパスワードを再送信する - 管理者向けヘルプ</span><span class="sxs-lookup"><span data-stu-id="f7d1d-184">Resend a user's password - Admin Help</span></span>](../add-users/resend-user-password.md)