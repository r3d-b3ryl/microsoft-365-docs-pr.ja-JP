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
# <a name="password-policy-recommendations"></a><span data-ttu-id="cca96-103">パスワード ポリシーの推奨事項</span><span class="sxs-lookup"><span data-stu-id="cca96-103">Password policy recommendations</span></span>
 
<span data-ttu-id="cca96-104">As the admin of an organization, you're responsible for setting password policy for users in your organization.</span><span class="sxs-lookup"><span data-stu-id="cca96-104">As the admin of an organization, you're responsible for setting password policy for users in your organization.</span></span> <span data-ttu-id="cca96-105">Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span><span class="sxs-lookup"><span data-stu-id="cca96-105">Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span></span>
  
<span data-ttu-id="cca96-106">組織で Microsoft 365 パスワードが期限切れとなる頻度を決める場合は、「[Microsoft 365 のパスワード有効期限ポリシーを設定する](../manage/set-password-expiration-policy.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cca96-106">To determine how often Microsoft 365 passwords expire in your organization, see [Set password expiration policy for Microsoft 365](../manage/set-password-expiration-policy.md).</span></span>

<span data-ttu-id="cca96-107">Microsoft 365 パスワードの詳細については、これらの[関連記事](#related-articles)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cca96-107">For more information about Microsoft 365 passwords, see these [related articles](#related-articles).</span></span>
  
## <a name="understanding-password-recommendations"></a><span data-ttu-id="cca96-108">パスワードの推奨事項について</span><span class="sxs-lookup"><span data-stu-id="cca96-108">Understanding password recommendations</span></span>

<span data-ttu-id="cca96-109">適切なパスワード手法は、次のようないくつかのカテゴリに大きく分けられます。</span><span class="sxs-lookup"><span data-stu-id="cca96-109">Good password practices fall into a few broad categories:</span></span>
  
- <span data-ttu-id="cca96-110">**一般的な攻撃に対抗する** これは、ユーザーがパスワードを入力する場所 (マルウェアを適切に検出できる既知の信頼できるデバイス、検証済みサイト) の選択、およびパスワード (長さと一意性) の選択に関係します。</span><span class="sxs-lookup"><span data-stu-id="cca96-110">**Resisting common attacks** This involves the choice of where users enter passwords (known and trusted devices with good malware detection, validated sites), and the choice of what password to choose (length and uniqueness).</span></span>

- <span data-ttu-id="cca96-111">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen.</span><span class="sxs-lookup"><span data-stu-id="cca96-111">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen.</span></span> <span data-ttu-id="cca96-112">For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span><span class="sxs-lookup"><span data-stu-id="cca96-112">For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span></span>

- <span data-ttu-id="cca96-113">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors.</span><span class="sxs-lookup"><span data-stu-id="cca96-113">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors.</span></span> <span data-ttu-id="cca96-114">Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality.</span><span class="sxs-lookup"><span data-stu-id="cca96-114">Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality.</span></span> <span data-ttu-id="cca96-115">Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span><span class="sxs-lookup"><span data-stu-id="cca96-115">Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span></span>

## <a name="password-guidelines-for-administrators"></a><span data-ttu-id="cca96-116">管理者向けのパスワード ガイドライン</span><span class="sxs-lookup"><span data-stu-id="cca96-116">Password guidelines for administrators</span></span>

<span data-ttu-id="cca96-117">The primary goal of a more secure password system is password diversity.</span><span class="sxs-lookup"><span data-stu-id="cca96-117">The primary goal of a more secure password system is password diversity.</span></span> <span data-ttu-id="cca96-118">You want your password policy to contain lots of different and hard to guess passwords.</span><span class="sxs-lookup"><span data-stu-id="cca96-118">You want your password policy to contain lots of different and hard to guess passwords.</span></span> <span data-ttu-id="cca96-119">Here are a few recommendations for keeping your organization as secure as possible.</span><span class="sxs-lookup"><span data-stu-id="cca96-119">Here are a few recommendations for keeping your organization as secure as possible.</span></span>
  
- <span data-ttu-id="cca96-120">8 桁の最小長要件を維持する (長ければよいとは限りません)</span><span class="sxs-lookup"><span data-stu-id="cca96-120">Maintain an 8-character minimum length requirement (longer isn't necessarily better)</span></span>

- <span data-ttu-id="cca96-121">Don't require character composition requirements.</span><span class="sxs-lookup"><span data-stu-id="cca96-121">Don't require character composition requirements.</span></span> <span data-ttu-id="cca96-122">For example, \*&amp;(^%$</span><span class="sxs-lookup"><span data-stu-id="cca96-122">For example, \*&amp;(^%$</span></span>

- <span data-ttu-id="cca96-123">ユーザー アカウントの必須の定期的なパスワード リセットを求めない</span><span class="sxs-lookup"><span data-stu-id="cca96-123">Don't require mandatory periodic password resets for user accounts</span></span>

- <span data-ttu-id="cca96-124">最も脆弱なパスワードがシステムで使用されないように、よく使われるパスワードを禁止する</span><span class="sxs-lookup"><span data-stu-id="cca96-124">Ban common passwords, to keep the most vulnerable passwords out of your system</span></span>

- <span data-ttu-id="cca96-125">業務以外の目的で組織のパスワードを再利用しないようにユーザーを教育する</span><span class="sxs-lookup"><span data-stu-id="cca96-125">Educate your users to not re-use their organization passwords for non-work related purposes</span></span>

- <span data-ttu-id="cca96-126">
            [多要素認証](../security-and-compliance/set-up-multi-factor-authentication.md)の登録を適用する</span><span class="sxs-lookup"><span data-stu-id="cca96-126">Enforce registration for [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)</span></span>

- <span data-ttu-id="cca96-127">リスク ベースの多要素認証チャレンジを有効にする</span><span class="sxs-lookup"><span data-stu-id="cca96-127">Enable risk-based multi-factor authentication challenges</span></span>

### <a name="password-guidance-for-your-users"></a><span data-ttu-id="cca96-128">ユーザー向けパスワード ガイダンス</span><span class="sxs-lookup"><span data-stu-id="cca96-128">Password guidance for your users</span></span>

<span data-ttu-id="cca96-129">Here's some password guidance for users in your organization.</span><span class="sxs-lookup"><span data-stu-id="cca96-129">Here's some password guidance for users in your organization.</span></span> <span data-ttu-id="cca96-130">Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span><span class="sxs-lookup"><span data-stu-id="cca96-130">Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span></span>
  
- <span data-ttu-id="cca96-131">他の Web サイトで使用しているものと同じ、または似たようなパスワードは使用しない</span><span class="sxs-lookup"><span data-stu-id="cca96-131">Don't use a password that is the same or similar to one you use on any other websites</span></span>

- <span data-ttu-id="cca96-132">1 単語 (たとえば、 **password** や、 **Iloveyou** などのよく使われるフレーズ) は使用しない</span><span class="sxs-lookup"><span data-stu-id="cca96-132">Don't use a single word, for example, **password**, or a commonly-used phrase like **Iloveyou**</span></span>

- <span data-ttu-id="cca96-133">友だちと家族の名前と誕生日、お気に入りのバンド、使用しそうなフレーズなど、自分のことをよく知る人でもパスワードを簡単に推測できないようにする</span><span class="sxs-lookup"><span data-stu-id="cca96-133">Make passwords hard to guess, even by those who know a lot about you, such as the names and birthdays of your friends and family, your favorite bands, and phrases you like to use</span></span>

## <a name="some-common-approaches-and-their-negative-impacts"></a><span data-ttu-id="cca96-134">一般的ないくつかの方法とその悪影響</span><span class="sxs-lookup"><span data-stu-id="cca96-134">Some common approaches and their negative impacts</span></span>

<span data-ttu-id="cca96-135">以下は最もよく使われるパスワードの管理手法の一部ですが、調査ではその悪影響について警告しています。</span><span class="sxs-lookup"><span data-stu-id="cca96-135">These are some of the most commonly used password management practices, but research warns us about the negative impacts of them.</span></span>
  
### <a name="password-expiration-requirements-for-users"></a><span data-ttu-id="cca96-136">ユーザー向けパスワードの有効期限の要件</span><span class="sxs-lookup"><span data-stu-id="cca96-136">Password expiration requirements for users</span></span>

<span data-ttu-id="cca96-137">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other.</span><span class="sxs-lookup"><span data-stu-id="cca96-137">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other.</span></span> <span data-ttu-id="cca96-138">In these cases, the next password can be predicted based on the previous password.</span><span class="sxs-lookup"><span data-stu-id="cca96-138">In these cases, the next password can be predicted based on the previous password.</span></span> <span data-ttu-id="cca96-139">Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span><span class="sxs-lookup"><span data-stu-id="cca96-139">Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span></span>
  
### <a name="requiring-long-passwords"></a><span data-ttu-id="cca96-140">長いパスワードを要求する</span><span class="sxs-lookup"><span data-stu-id="cca96-140">Requiring long passwords</span></span>

<span data-ttu-id="cca96-141">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable.</span><span class="sxs-lookup"><span data-stu-id="cca96-141">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable.</span></span> <span data-ttu-id="cca96-142">For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess.</span><span class="sxs-lookup"><span data-stu-id="cca96-142">For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess.</span></span> <span data-ttu-id="cca96-143">Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents.</span><span class="sxs-lookup"><span data-stu-id="cca96-143">Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents.</span></span> <span data-ttu-id="cca96-144">To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span><span class="sxs-lookup"><span data-stu-id="cca96-144">To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span></span> 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a><span data-ttu-id="cca96-145">複数の文字セットの使用を要求する</span><span class="sxs-lookup"><span data-stu-id="cca96-145">Requiring the use of multiple character sets</span></span>

<span data-ttu-id="cca96-146">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good.</span><span class="sxs-lookup"><span data-stu-id="cca96-146">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good.</span></span> <span data-ttu-id="cca96-147">Most systems enforce some level of password complexity requirements.</span><span class="sxs-lookup"><span data-stu-id="cca96-147">Most systems enforce some level of password complexity requirements.</span></span> <span data-ttu-id="cca96-148">For example, passwords need characters from all three of the following categories:</span><span class="sxs-lookup"><span data-stu-id="cca96-148">For example, passwords need characters from all three of the following categories:</span></span>
  
- <span data-ttu-id="cca96-149">大文字</span><span class="sxs-lookup"><span data-stu-id="cca96-149">uppercase characters</span></span>

- <span data-ttu-id="cca96-150">小文字</span><span class="sxs-lookup"><span data-stu-id="cca96-150">lowercase characters</span></span>

- <span data-ttu-id="cca96-151">英数字以外の文字</span><span class="sxs-lookup"><span data-stu-id="cca96-151">non-alphanumeric characters</span></span>

<span data-ttu-id="cca96-152">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2.</span><span class="sxs-lookup"><span data-stu-id="cca96-152">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2.</span></span> <span data-ttu-id="cca96-153">Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l".</span><span class="sxs-lookup"><span data-stu-id="cca96-153">Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l".</span></span> <span data-ttu-id="cca96-154">Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect.</span><span class="sxs-lookup"><span data-stu-id="cca96-154">Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect.</span></span> <span data-ttu-id="cca96-155">Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span><span class="sxs-lookup"><span data-stu-id="cca96-155">Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span></span>
  
## <a name="successful-patterns"></a><span data-ttu-id="cca96-156">成功パターン</span><span class="sxs-lookup"><span data-stu-id="cca96-156">Successful Patterns</span></span>

<span data-ttu-id="cca96-157">上記のものとは対照的に、パスワードに多様性を持たせる推奨事項をいくつか以下に示します。</span><span class="sxs-lookup"><span data-stu-id="cca96-157">In contrast, here are some recommendations in encouraging password diversity.</span></span>
  
### <a name="ban-common-passwords"></a><span data-ttu-id="cca96-158">よく使われるパスワードを禁止する</span><span class="sxs-lookup"><span data-stu-id="cca96-158">Ban common passwords</span></span>

<span data-ttu-id="cca96-159">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks.</span><span class="sxs-lookup"><span data-stu-id="cca96-159">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks.</span></span> <span data-ttu-id="cca96-160">Common user passwords include, **abdcefg**, **password**, **monkey**.</span><span class="sxs-lookup"><span data-stu-id="cca96-160">Common user passwords include, **abdcefg**, **password**, **monkey**.</span></span>
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a><span data-ttu-id="cca96-161">組織のパスワードを他の場所で再利用しないようにユーザーを教育する</span><span class="sxs-lookup"><span data-stu-id="cca96-161">Educate users to not re-use organization passwords anywhere else</span></span>

<span data-ttu-id="cca96-162">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else.</span><span class="sxs-lookup"><span data-stu-id="cca96-162">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else.</span></span> <span data-ttu-id="cca96-163">The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span><span class="sxs-lookup"><span data-stu-id="cca96-163">The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span></span>
  
### <a name="enforce-multi-factor-authentication-registration"></a><span data-ttu-id="cca96-164">多要素認証の登録を適用する</span><span class="sxs-lookup"><span data-stu-id="cca96-164">Enforce Multi-Factor Authentication registration</span></span>

<span data-ttu-id="cca96-165">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events.</span><span class="sxs-lookup"><span data-stu-id="cca96-165">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events.</span></span> <span data-ttu-id="cca96-166">Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account.</span><span class="sxs-lookup"><span data-stu-id="cca96-166">Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account.</span></span> <span data-ttu-id="cca96-167">It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span><span class="sxs-lookup"><span data-stu-id="cca96-167">It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span></span> 
  
<span data-ttu-id="cca96-168">詳細については、「[Office 365 ユーザー用の多要素認証を設定する](../security-and-compliance/set-up-multi-factor-authentication.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cca96-168">To learn more, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>
  
### <a name="enable-risk-based-multi-factor-authentication"></a><span data-ttu-id="cca96-169">リスク ベースの多要素認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="cca96-169">Enable risk-based multi-factor authentication</span></span>

<span data-ttu-id="cca96-170">リスク ベースの多要素認証では、Microsoft のシステムで不審な動作が検出されたときに、正当なアカウント所有者であることを確認するためにユーザーに対してチャレンジを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="cca96-170">Risk-based multi-factor authentication ensures that when our system detects suspicious activity, it can challenge the user to ensure that they are the legitimate account owner.</span></span> 
  
## <a name="want-to-know-more-recommended-reading"></a><span data-ttu-id="cca96-171">詳細については、</span><span class="sxs-lookup"><span data-stu-id="cca96-171">Want to know more?</span></span> <span data-ttu-id="cca96-172">以下のお勧めの資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cca96-172">Recommended reading</span></span>

- <span data-ttu-id="cca96-173">[Do Strong Web Passwords Accomplish Anything?](https://go.microsoft.com/fwlink/p/?linkid=861008) (強力な Web パスワードでできること)</span><span class="sxs-lookup"><span data-stu-id="cca96-173">[Do Strong Web Passwords Accomplish Anything?](https://go.microsoft.com/fwlink/p/?linkid=861008)</span></span>

- <span data-ttu-id="cca96-174">[Password Portfolios and the Finite-Effort User](https://go.microsoft.com/fwlink/p/?linkid=861014) (パスワード ポートフォリオとユーザーの有限労力)</span><span class="sxs-lookup"><span data-stu-id="cca96-174">[Password Portfolios and the Finite-Effort User](https://go.microsoft.com/fwlink/p/?linkid=861014)</span></span>

- <span data-ttu-id="cca96-175">[Preventing Weak Passwords by Reading Users' Minds](https://go.microsoft.com/fwlink/p/?linkid=861015) (ユーザーの心を読み取り、脆弱なパスワードの使用を防ぐ)</span><span class="sxs-lookup"><span data-stu-id="cca96-175">[Preventing Weak Passwords by Reading Users' Minds](https://go.microsoft.com/fwlink/p/?linkid=861015)</span></span>

- <span data-ttu-id="cca96-176">[Choosing Secure Passwords](https://go.microsoft.com/fwlink/p/?linkid=861016) (セキュリティで保護されたパスワードの選択)</span><span class="sxs-lookup"><span data-stu-id="cca96-176">[Choosing Secure Passwords](https://go.microsoft.com/fwlink/p/?linkid=861016)</span></span>

- <span data-ttu-id="cca96-177">[Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018) (必須パスワードの変更を再検討する時間)</span><span class="sxs-lookup"><span data-stu-id="cca96-177">[Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018)</span></span>

- <span data-ttu-id="cca96-178">[Worst Passwords of 2015](https://go.microsoft.com/fwlink/p/?linkid=861020) (2015 年のワースト パスワード)</span><span class="sxs-lookup"><span data-stu-id="cca96-178">[Worst Passwords of 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)</span></span>

- [<span data-ttu-id="cca96-179">Web からファイルをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="cca96-179">Download files from the web</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861029)

## <a name="related-articles"></a><span data-ttu-id="cca96-180">関連記事</span><span class="sxs-lookup"><span data-stu-id="cca96-180">Related articles</span></span>

[<span data-ttu-id="cca96-181">パスワードをリセットする</span><span class="sxs-lookup"><span data-stu-id="cca96-181">Reset passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords)

[<span data-ttu-id="cca96-182">個別のユーザーのパスワードを無期限に設定する</span><span class="sxs-lookup"><span data-stu-id="cca96-182">Set an individual user's password to never expire</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/set-password-to-never-expire)

[<span data-ttu-id="cca96-183">ユーザーが自分でパスワードをリセットできるようにする</span><span class="sxs-lookup"><span data-stu-id="cca96-183">Let users reset their own passwords</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/let-users-reset-passwords)

[<span data-ttu-id="cca96-184">ユーザーのパスワードを再送信する - 管理者向けヘルプ</span><span class="sxs-lookup"><span data-stu-id="cca96-184">Resend a user's password - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/add-users/resend-user-password)
