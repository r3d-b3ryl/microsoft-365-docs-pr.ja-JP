---
title: ユーザーの多要素認証Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: 多要素認証 (MFA) は、強力なパスワードと追加の検証方法の両方を使用します。
ms.openlocfilehash: 9b3347f1a8e7b1f62c9bbfe77a7f14c221ef28b5
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393645"
---
# <a name="multifactor-authentication-for-microsoft-365"></a><span data-ttu-id="bf92c-103">ユーザーの多要素認証Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bf92c-103">Multifactor authentication for Microsoft 365</span></span>

<span data-ttu-id="bf92c-104">パスワードは、コンピューターまたはオンライン サービスへのサインインを認証する最も一般的な方法ですが、最も脆弱な方法でもあります。</span><span class="sxs-lookup"><span data-stu-id="bf92c-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="bf92c-105">ユーザーは、簡単なパスワードを選択して、異なるコンピューターやサービスに対して同じパスワードを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="bf92c-106">サインインに追加のレベルのセキュリティを提供するには、パスワードの両方を使用する多要素認証 (MFA) を使用する必要があります。これは強力である必要があります。また、次に基づく追加の検証方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="bf92c-106">To provide an additional level of security for sign-ins, you must use multifactor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="bf92c-107">容易に複製できないユーザーの所有物 (スマート フォンなど)。</span><span class="sxs-lookup"><span data-stu-id="bf92c-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="bf92c-108">ユーザーに固有の生物学的特徴 (指紋、顔、または他の生体認証属性など)。</span><span class="sxs-lookup"><span data-stu-id="bf92c-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="bf92c-109">追加の検証方法は、ユーザーのパスワードが確認されるまで使用されません。</span><span class="sxs-lookup"><span data-stu-id="bf92c-109">The additional verification method is not employed until after the user's password has been verified.</span></span> <span data-ttu-id="bf92c-110">MFA では、強力なユーザー パスワードが侵害された場合でも、攻撃者がスマート フォンや指紋を持っていないため、サインインを完了できません。</span><span class="sxs-lookup"><span data-stu-id="bf92c-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="bf92c-111">Microsoft 365 の MFA サポート</span><span class="sxs-lookup"><span data-stu-id="bf92c-111">MFA support in Microsoft 365</span></span>

<span data-ttu-id="bf92c-112">既定では、Microsoft 365 および Office 365 は、ユーザー アカウントに対する MFA を次の方法でサポートします。</span><span class="sxs-lookup"><span data-stu-id="bf92c-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="bf92c-113">電話に送信される、確認コードの入力に必要なテキスト メッセージ。</span><span class="sxs-lookup"><span data-stu-id="bf92c-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="bf92c-114">電話呼び出し。</span><span class="sxs-lookup"><span data-stu-id="bf92c-114">A phone call.</span></span>
- <span data-ttu-id="bf92c-115">Microsoft Authenticator スマート フォン アプリ。</span><span class="sxs-lookup"><span data-stu-id="bf92c-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="bf92c-116">どちらの場合も、MFA サインインでは、追加の検証に "重複しがちではない" メソッドを使用しています。</span><span class="sxs-lookup"><span data-stu-id="bf92c-116">In both cases, the MFA sign-in is using the "something you have with you that is not easily duplicated" method for the additional verification.</span></span> <span data-ttu-id="bf92c-117">Microsoft 365 および Office 365 の MFA は、次の複数の方法で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="bf92c-118">セキュリティの既定値を使用する</span><span class="sxs-lookup"><span data-stu-id="bf92c-118">With security defaults</span></span>
- <span data-ttu-id="bf92c-119">条件付きアクセス ポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="bf92c-119">With Conditional Access policies</span></span>
- <span data-ttu-id="bf92c-120">個別のユーザー アカウントごとに設定する (推奨されません)</span><span class="sxs-lookup"><span data-stu-id="bf92c-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="bf92c-121">これらの方法は、ご利用の Microsoft 365 プランに応じて決まります。</span><span class="sxs-lookup"><span data-stu-id="bf92c-121">These ways are based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="bf92c-122">計画</span><span class="sxs-lookup"><span data-stu-id="bf92c-122">Plan</span></span>|<span data-ttu-id="bf92c-123">推奨事項</span><span class="sxs-lookup"><span data-stu-id="bf92c-123">Recommendation</span></span>|<span data-ttu-id="bf92c-124">お客様の種類</span><span class="sxs-lookup"><span data-stu-id="bf92c-124">Type of customer</span></span>|
|---|---|---|
|<span data-ttu-id="bf92c-125">すべての Microsoft 365 プラン</span><span class="sxs-lookup"><span data-stu-id="bf92c-125">All Microsoft 365 plans</span></span>|<span data-ttu-id="bf92c-126">すべてのユーザー アカウントに対して MFA を要求する、セキュリティの既定値を使用します。</span><span class="sxs-lookup"><span data-stu-id="bf92c-126">Use security defaults, which require MFA for all user accounts.</span></span> <p> <span data-ttu-id="bf92c-127">個々のユーザー アカウントでユーザーごとの MFA を構成することもできますが、これはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="bf92c-127">You can also configure per-user MFA on individual user accounts, but this is not recommended.</span></span>|<span data-ttu-id="bf92c-128">小規模企業</span><span class="sxs-lookup"><span data-stu-id="bf92c-128">Small business</span></span>|
|<span data-ttu-id="bf92c-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="bf92c-129">Microsoft 365 Business Premium</span></span> <p> <span data-ttu-id="bf92c-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="bf92c-130">Microsoft 365 E3</span></span> <p> <span data-ttu-id="bf92c-131">Azure Active Directory (Azure AD) Premium P1 ライセンス</span><span class="sxs-lookup"><span data-stu-id="bf92c-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span>|<span data-ttu-id="bf92c-132">条件付きアクセス ポリシーを使用して、グループ メンバーシップ、アプリ、その他の条件に基づいてユーザー アカウントに MFA を要求します。</span><span class="sxs-lookup"><span data-stu-id="bf92c-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span>|<span data-ttu-id="bf92c-133">小規模企業から大規模企業まで</span><span class="sxs-lookup"><span data-stu-id="bf92c-133">Small business to enterprise</span></span>|
|<span data-ttu-id="bf92c-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bf92c-134">Microsoft 365 E5</span></span> <p> <span data-ttu-id="bf92c-135">Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="bf92c-135">Azure AD Premium P2 licenses</span></span>|<span data-ttu-id="bf92c-136">Azure AD Identity Protection を使用して、サインイン リスクの条件に基づいて MFA を要求します。</span><span class="sxs-lookup"><span data-stu-id="bf92c-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span>|<span data-ttu-id="bf92c-137">大規模企業</span><span class="sxs-lookup"><span data-stu-id="bf92c-137">Enterprise</span></span>|
||||

### <a name="security-defaults"></a><span data-ttu-id="bf92c-138">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="bf92c-138">Security defaults</span></span>

<span data-ttu-id="bf92c-139">セキュリティの既定値は、2019 年 10 月 21 日以降に作成された Microsoft 365 および Office 365 の有料または試用版サブスクリプションの新機能です。</span><span class="sxs-lookup"><span data-stu-id="bf92c-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="bf92c-140">これらのサブスクリプションでは、次のセキュリティの既定値が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="bf92c-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="bf92c-141">すべてのユーザーが Microsoft Authenticator アプリで MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf92c-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="bf92c-142">従来の認証をブロックします。</span><span class="sxs-lookup"><span data-stu-id="bf92c-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="bf92c-143">ユーザーは、スマートフォンから Microsoft Authenticator アプリを使用して MFA に 14 日間登録できます。これは、セキュリティの既定値が有効になった後、初めてサインインしたときから始まります。</span><span class="sxs-lookup"><span data-stu-id="bf92c-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="bf92c-144">14 日が経過すると、ユーザーは MFA 登録が完了するまでサインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="bf92c-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="bf92c-145">セキュリティの既定値では、すべての組織が、既定で有効になっているユーザー サインインの基本レベルのセキュリティを確保しています。</span><span class="sxs-lookup"><span data-stu-id="bf92c-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="bf92c-146">条件付きアクセス ポリシーを使用する MFA を優先して、セキュリティの既定値を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="bf92c-147">Azure ポータル内の Azure AD の **プロパティ** ウィンドウで、セキュリティの既定値を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="bf92c-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![[ディレクトリのプロパティ] ページの図。](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="bf92c-149">すべての Microsoft 365 プランで、セキュリティの既定値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-149">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="bf92c-150">詳細については、こちらの「[セキュリティの既定値の概要](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bf92c-150">For more information, see this [overview of security defaults](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="bf92c-151">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="bf92c-151">Conditional Access policies</span></span>

<span data-ttu-id="bf92c-152">条件付きアクセス ポリシーは、サインインが評価および許可される条件を指定する一連のルールです。</span><span class="sxs-lookup"><span data-stu-id="bf92c-152">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="bf92c-153">たとえば、次のような条件付きアクセス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-153">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="bf92c-154">ユーザー アカウント名が Exchange、ユーザー、パスワード、セキュリティ、SharePoint、またはグローバル管理者の役割を割り当てられたユーザーのグループのメンバーである場合、アクセスを許可する前に MFA が必要です。</span><span class="sxs-lookup"><span data-stu-id="bf92c-154">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="bf92c-155">このポリシーを使用すると、これらの管理者の役割から割り当てられたり、または割り当てられなかったりした場合に、個別のユーザー アカウントを MFA 用に構成しようとするのではなく、グループ メンバーシップに基づいて MFA を要求することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="bf92c-155">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="bf92c-156">また、条件付きアクセス ポリシーを使用して、特定のアプリに対して MFA を要求する、または Windows 10 を実行しているノート PC などの準拠デバイスからのサインインを要求するなど、より高度な機能を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-156">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="bf92c-157">Azure ポータル内の Azure AD の **セキュリティ** ウィンドウで、条件付きアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="bf92c-157">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![条件付きアクセスのメニュー オプションの画像](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="bf92c-159">条件付きアクセス ポリシーは、次のプランで使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-159">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="bf92c-160">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="bf92c-160">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="bf92c-161">Microsoft 365 E3 および E5</span><span class="sxs-lookup"><span data-stu-id="bf92c-161">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="bf92c-162">Azure AD Premium P1、Azure AD Premium P2 ライセンス</span><span class="sxs-lookup"><span data-stu-id="bf92c-162">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="bf92c-163">Microsoft 365 Business Premium を使用している小規模企業の場合、次の手順で、条件付きアクセス ポリシーを簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-163">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="bf92c-164">MFA を必要とするユーザー アカウントを含むグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="bf92c-164">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="bf92c-165">**グローバル管理者に対して MFA を要求する** ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bf92c-165">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="bf92c-166">次の設定を使用して、グループ ベースの条件付きアクセス ポリシーを作成します</span><span class="sxs-lookup"><span data-stu-id="bf92c-166">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="bf92c-167">割り当て > ユーザーとグループ: 上記の手順 1 で作成したグループの名前。</span><span class="sxs-lookup"><span data-stu-id="bf92c-167">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="bf92c-168">割り当て > クラウド アプリまたは操作: すべてのクラウド アプリ。</span><span class="sxs-lookup"><span data-stu-id="bf92c-168">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="bf92c-169">アクセス制御 > 許可 > アクセス権の付与 > 多要素認証を要求する。</span><span class="sxs-lookup"><span data-stu-id="bf92c-169">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="bf92c-170">ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="bf92c-170">Enable the policy.</span></span>
5. <span data-ttu-id="bf92c-171">上記の手順 1 で作成したグループにユーザー アカウントを追加してテストします。</span><span class="sxs-lookup"><span data-stu-id="bf92c-171">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="bf92c-172">追加のユーザー アカウントに MFA を要求するには、手順 1 で作成したグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="bf92c-172">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="bf92c-173">この条件付きアクセス ポリシーを使用すると、お客様のペースでユーザーに MFA の要件を展開できます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-173">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="bf92c-174">大規模企業は、[一般的な条件付きアクセス ポリシー](/azure/active-directory/conditional-access/concept-conditional-access-policy-common)を使用して、次のポリシーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf92c-174">Enterprises should use [Common Conditional Access policies](/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="bf92c-175">管理者に対して MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="bf92c-175">Require MFA for administrators</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="bf92c-176">すべてのユーザーに対して MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="bf92c-176">Require MFA for all users</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="bf92c-177">従来の認証をブロックする</span><span class="sxs-lookup"><span data-stu-id="bf92c-177">Block legacy authentication</span></span>](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="bf92c-178">詳細については、こちらの[条件付きアクセスの概要](/azure/active-directory/conditional-access/overview)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bf92c-178">For more information, see this [overview of Conditional Access](/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="bf92c-179">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="bf92c-179">Azure AD Identity Protection</span></span>

<span data-ttu-id="bf92c-180">Azure AD Identity Protection を使用すると、追加の条件付きアクセス ポリシーを作成して、[サインインのリスクが中以上のとき MFA を要求する](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)ことができます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-180">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](../../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="bf92c-181">Azure AD Identity Protection とリスク ベースの条件付きアクセス ポリシーは、次のプランで使用できます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-181">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="bf92c-182">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bf92c-182">Microsoft 365 E5</span></span>
- <span data-ttu-id="bf92c-183">Azure AD Premium P2</span><span class="sxs-lookup"><span data-stu-id="bf92c-183">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="bf92c-184">詳細については、こちらの [Azure AD Identity Protection の概要](/azure/active-directory/identity-protection/overview-identity-protection)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="bf92c-184">For more information, see this [overview of Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="legacy-per-user-mfa-not-recommended"></a><span data-ttu-id="bf92c-185">従来のユーザーごとの MFA (推奨されません)</span><span class="sxs-lookup"><span data-stu-id="bf92c-185">Legacy per-user MFA (not recommended)</span></span>

<span data-ttu-id="bf92c-186">ユーザー アカウントのサインインに MFA を要求するには、セキュリティの既定値または条件付きアクセス ポリシーを使用する必要があります。これらのいずれも使用できない場合は、あらゆるサイズのサブスクリプションについて、管理者ロール、特にグローバル管理者ロールを持つユーザー アカウントに対する MFA を強く推奨します。</span><span class="sxs-lookup"><span data-stu-id="bf92c-186">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span>

<span data-ttu-id="bf92c-187">Microsoft 365 管理センターの **アクティブなユーザー** ウィンドウで、各ユーザー アカウントに対して MFA を有効にします。</span><span class="sxs-lookup"><span data-stu-id="bf92c-187">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![[アクティブ ユーザー] ページの [多要素認証オプションの画像]](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="bf92c-189">有効にすると、ユーザーが次回サインインしたときに、MFA に登録し、追加の確認方法を選択してテストするように求められます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-189">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="bf92c-190">これらの方法を組み合わせて使用する</span><span class="sxs-lookup"><span data-stu-id="bf92c-190">Using these methods together</span></span>

<span data-ttu-id="bf92c-191">この表は、セキュリティの既定値、条件付きアクセス ポリシー、およびユーザーごとのアカウント設定で MFA を有効にした結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="bf92c-191">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|<span data-ttu-id="bf92c-192">*アイテム*</span><span class="sxs-lookup"><span data-stu-id="bf92c-192">*Item*</span></span>|<span data-ttu-id="bf92c-193">Enabled</span><span class="sxs-lookup"><span data-stu-id="bf92c-193">Enabled</span></span>|<span data-ttu-id="bf92c-194">無効</span><span class="sxs-lookup"><span data-stu-id="bf92c-194">Disabled</span></span>|<span data-ttu-id="bf92c-195">第 2 の認証方法</span><span class="sxs-lookup"><span data-stu-id="bf92c-195">Secondary authentication method</span></span>|
|---|---|---|---|
|<span data-ttu-id="bf92c-196">**セキュリティの既定値**</span><span class="sxs-lookup"><span data-stu-id="bf92c-196">**Security defaults**</span></span>|<span data-ttu-id="bf92c-197">条件付きアクセス ポリシーを使用できない</span><span class="sxs-lookup"><span data-stu-id="bf92c-197">Can't use Conditional Access policies</span></span>|<span data-ttu-id="bf92c-198">条件付きアクセス ポリシーを使用できる</span><span class="sxs-lookup"><span data-stu-id="bf92c-198">Can use Conditional Access policies</span></span>|<span data-ttu-id="bf92c-199">Microsoft Authenticator アプリ</span><span class="sxs-lookup"><span data-stu-id="bf92c-199">Microsoft Authenticator app</span></span>|
|<span data-ttu-id="bf92c-200">**条件付きアクセス ポリシー**</span><span class="sxs-lookup"><span data-stu-id="bf92c-200">**Conditional Access policies**</span></span>|<span data-ttu-id="bf92c-201">有効になっている場合は、セキュリティの既定値を有効にできません</span><span class="sxs-lookup"><span data-stu-id="bf92c-201">If any are enabled, you can't enable security defaults</span></span>|<span data-ttu-id="bf92c-202">すべてが無効になっている場合は、セキュリティの既定値を有効にすることができます</span><span class="sxs-lookup"><span data-stu-id="bf92c-202">If all are disabled, you can enable security defaults</span></span>|<span data-ttu-id="bf92c-203">MFA 登録中にユーザーが指定</span><span class="sxs-lookup"><span data-stu-id="bf92c-203">User-specified during MFA registration</span></span>|
|<span data-ttu-id="bf92c-204">**従来のユーザーごとの MFA (推奨されません)**</span><span class="sxs-lookup"><span data-stu-id="bf92c-204">**Legacy per-user MFA (not recommended)**</span></span>|<span data-ttu-id="bf92c-205">毎回のサインインで MFA を要求して、セキュリティの既定値と条件付きアクセス ポリシーを上書きします</span><span class="sxs-lookup"><span data-stu-id="bf92c-205">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span>|<span data-ttu-id="bf92c-206">セキュリティの既定値と条件付きアクセス ポリシーによって上書きされます</span><span class="sxs-lookup"><span data-stu-id="bf92c-206">Overridden by security defaults and Conditional Access policies</span></span>|<span data-ttu-id="bf92c-207">MFA 登録中にユーザーが指定</span><span class="sxs-lookup"><span data-stu-id="bf92c-207">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="bf92c-208">セキュリティの既定値が有効になっている場合、すべての新しいユーザーは、次回のサインイン時に MFA 登録と Microsoft Authenticator アプリの使用を求められます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-208">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="bf92c-209">MFA 設定を管理する方法</span><span class="sxs-lookup"><span data-stu-id="bf92c-209">Ways to manage MFA settings</span></span>

<span data-ttu-id="bf92c-210">以下の 2 種類の方法で MFA 設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-210">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="bf92c-211">Azure ポータルでは、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-211">In the Azure portal, you can:</span></span>

- <span data-ttu-id="bf92c-212">セキュリティの既定値を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="bf92c-212">Enable and disable security defaults</span></span>
- <span data-ttu-id="bf92c-213">条件付きアクセス ポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="bf92c-213">Configure Conditional Access policies</span></span>

<span data-ttu-id="bf92c-214">Microsoft 365 管理センターでは、ユーザー単位およびサービス用の MFA 設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="bf92c-214">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bf92c-215">次の手順</span><span class="sxs-lookup"><span data-stu-id="bf92c-215">Next steps</span></span>

[<span data-ttu-id="bf92c-216">Microsoft 365 の MFA を設定する</span><span class="sxs-lookup"><span data-stu-id="bf92c-216">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

## <a name="related-content"></a><span data-ttu-id="bf92c-217">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="bf92c-217">Related content</span></span>

<span data-ttu-id="bf92c-218">[多要素認証 (ビデオ](../../business-video/turn-on-mfa.md) ) を有効にする</span><span class="sxs-lookup"><span data-stu-id="bf92c-218">[Turn on multifactor authentication](../../business-video/turn-on-mfa.md) (video)</span></span>\
<span data-ttu-id="bf92c-219">[電話の多要素認証を有効にする](../../business-video/set-up-mfa.md) (ビデオ)</span><span class="sxs-lookup"><span data-stu-id="bf92c-219">[Turn on multifactor authentication for your phone](../../business-video/set-up-mfa.md) (video)</span></span>