---
title: Microsoft 365 の多要素認証
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 での多要素認証について説明します。
ms.openlocfilehash: eba9ae38dbc17a22abb5d5ef92b8cd30a827ae11
ms.sourcegitcommit: 87eff6e8a08cec3cb0464a3b765434717584a4a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2020
ms.locfileid: "44371454"
---
# <a name="multi-factor-authentication-for-microsoft-365"></a><span data-ttu-id="ccfc3-103">Microsoft 365 の多要素認証</span><span class="sxs-lookup"><span data-stu-id="ccfc3-103">Multi-factor authentication for Microsoft 365</span></span>

<span data-ttu-id="ccfc3-104">パスワードは、コンピューターまたはオンラインサービスへのサインインを認証する最も一般的な方法ですが、最も脆弱なものでもあります。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-104">Passwords are the most common method of authenticating a sign-in to a computer or online service, but they are also the most vulnerable.</span></span> <span data-ttu-id="ccfc3-105">ユーザーは、簡単なパスワードを選択したり、複数のサインインに同じパスワードを使用して異なるコンピュータやサービスに対して使用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-105">People can choose easy passwords and use the same passwords for multiple sign-ins to different computers and services.</span></span>

<span data-ttu-id="ccfc3-106">サインインのセキュリティレベルを追加するには、多要素認証 (MFA) を使用する必要があります。これには、パスワード (強力なものにする必要があります) と、次のものに基づく追加の検証方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-106">To provide an additional level of security for sign-ins, you must use multi-factor authentication (MFA), which uses both a password, which should be strong, and an additional verification method based on:</span></span>

- <span data-ttu-id="ccfc3-107">スマートフォンなどの、簡単には再現できないものがあります。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-107">Something you have with you that is not easily duplicated, such as a smart phone.</span></span>
- <span data-ttu-id="ccfc3-108">個人で biologically したもの、指紋、顔、その他のバイオメトリクス属性など。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-108">Something you uniquely and biologically have, such as your fingerprints, face, or other biometric attribute.</span></span>

<span data-ttu-id="ccfc3-109">追加の認証方法は、ユーザーのパスワードが確認されるまで使用されません。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-109">The additional verification method is not employed until after the user’s password has been verified.</span></span> <span data-ttu-id="ccfc3-110">MFA では、強力なユーザーパスワードが侵害された場合でも、攻撃者はスマートフォンや指紋を持ってサインインを完了できません。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-110">With MFA, even if a strong user password is compromised, the attacker does not have your smart phone or your fingerprint to complete the sign-in.</span></span>

## <a name="mfa-support-in-microsoft-365"></a><span data-ttu-id="ccfc3-111">Microsoft 365 での MFA サポート</span><span class="sxs-lookup"><span data-stu-id="ccfc3-111">MFA support in Microsoft 365</span></span>
<span data-ttu-id="ccfc3-112">既定では、Microsoft 365 と Office 365 はどちらも、次のものを使用するユーザーアカウントに対して MFA をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-112">By default, both Microsoft 365 and Office 365 support MFA for user accounts using:</span></span>

- <span data-ttu-id="ccfc3-113">ユーザーが確認コードを入力する必要がある、電話に送信されるテキストメッセージ。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-113">A text message sent to a phone that requires the user to type a verification code.</span></span>
- <span data-ttu-id="ccfc3-114">通話。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-114">A phone call.</span></span>
- <span data-ttu-id="ccfc3-115">Microsoft Authenticator スマートフォンアプリ。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-115">The Microsoft Authenticator smart phone app.</span></span>

<span data-ttu-id="ccfc3-116">いずれの場合も、MFA サインインは、追加の確認のための "簡単には複製されていないものがあります" という方法を使用しています。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-116">In both cases, the MFA sign-in is using the “something you have with you that is not easily duplicated” method for the additional verification.</span></span>
<span data-ttu-id="ccfc3-117">Microsoft 365 および Office 365 で MFA を有効にするには、複数の方法があります。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-117">There are multiple ways in which you can enable MFA for Microsoft 365 and Office 365:</span></span>

- <span data-ttu-id="ccfc3-118">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="ccfc3-118">With security defaults</span></span>
- <span data-ttu-id="ccfc3-119">条件付きアクセスポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="ccfc3-119">With Conditional Access policies</span></span>
- <span data-ttu-id="ccfc3-120">個別のユーザーアカウントごと (推奨されません)</span><span class="sxs-lookup"><span data-stu-id="ccfc3-120">For each individual user account (not recommended)</span></span>

<span data-ttu-id="ccfc3-121">これらの方法は、Microsoft 365 プランに基づいています。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-121">These ways are based on your Microsoft 365 plan.</span></span>
    
|<span data-ttu-id="ccfc3-122">プラン</span><span class="sxs-lookup"><span data-stu-id="ccfc3-122">Plan</span></span>  |<span data-ttu-id="ccfc3-123">推奨事項</span><span class="sxs-lookup"><span data-stu-id="ccfc3-123">Recommendation</span></span>  | <span data-ttu-id="ccfc3-124">顧客の種類</span><span class="sxs-lookup"><span data-stu-id="ccfc3-124">Type of customer</span></span> |
|---------|---------|----------|
| <span data-ttu-id="ccfc3-125">すべての Microsoft 365 プラン</span><span class="sxs-lookup"><span data-stu-id="ccfc3-125">All Microsoft 365 plans</span></span> | <span data-ttu-id="ccfc3-126">セキュリティの既定値を使用します。これには、すべてのユーザーアカウントに対して MFA が必要です。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-126">Use security defaults, which require MFA for all user accounts.</span></span> <br> <span data-ttu-id="ccfc3-127">ユーザーごとのアカウントごとに MFA を要求することもできますが、この方法はお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-127">You can also require MFA on a per-user account basis, but this is not recommended.</span></span> | <span data-ttu-id="ccfc3-128">Small Business</span><span class="sxs-lookup"><span data-stu-id="ccfc3-128">Small business</span></span> |
| <span data-ttu-id="ccfc3-129">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="ccfc3-129">Microsoft 365 Business Premium</span></span> <br><br> <span data-ttu-id="ccfc3-130">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="ccfc3-130">Microsoft 365 E3</span></span> <br><br> <span data-ttu-id="ccfc3-131">Azure Active Directory (Azure AD) プレミアム P1 ライセンス</span><span class="sxs-lookup"><span data-stu-id="ccfc3-131">Azure Active Directory (Azure AD) Premium P1 licenses</span></span> | <span data-ttu-id="ccfc3-132">条件付きアクセスポリシーを使用して、グループメンバーシップ、アプリ、またはその他の条件に基づいてユーザーアカウントに MFA を要求します。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-132">Use Conditional Access policies to require MFA for user accounts based on group membership, apps, or other criteria.</span></span> | <span data-ttu-id="ccfc3-133">小規模企業からエンタープライズへ</span><span class="sxs-lookup"><span data-stu-id="ccfc3-133">Small business to enterprise</span></span> |
| <span data-ttu-id="ccfc3-134">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ccfc3-134">Microsoft 365 E5</span></span> <br><br> <span data-ttu-id="ccfc3-135">Azure AD Premium P2 ライセンス</span><span class="sxs-lookup"><span data-stu-id="ccfc3-135">Azure AD Premium P2 licenses</span></span> | <span data-ttu-id="ccfc3-136">Azure AD Identity Protection を使用して、サインインリスク基準に基づいて MFA を要求します。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-136">Use Azure AD Identity Protection to require MFA based on sign-in risk criteria.</span></span> |  <span data-ttu-id="ccfc3-137">Enterprise</span><span class="sxs-lookup"><span data-stu-id="ccfc3-137">Enterprise</span></span> |
||||

### <a name="security-defaults"></a><span data-ttu-id="ccfc3-138">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="ccfc3-138">Security defaults</span></span>

<span data-ttu-id="ccfc3-139">セキュリティの既定値は、2019 年 10 月 21 日以降に作成された Microsoft 365 および Office 365 の有料または試用版サブスクリプションの新機能です。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-139">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="ccfc3-140">これらのサブスクリプションのセキュリティの既定値は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-140">These subscriptions have security defaults turned on, which:</span></span>

- <span data-ttu-id="ccfc3-141">すべてのユーザーに対して、Microsoft Authenticator アプリで MFA を使用することを要求します。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-141">Requires all of your users to use MFA with the Microsoft Authenticator app.</span></span>
- <span data-ttu-id="ccfc3-142">従来の認証をブロックします。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-142">Blocks legacy authentication.</span></span>

<span data-ttu-id="ccfc3-143">ユーザーは、スマートフォンから Microsoft Authenticator アプリを使用して MFA に 14 日間登録できます。これは、セキュリティの既定値が有効になった後、初めてサインインしたときから始まります。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-143">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="ccfc3-144">14 日が経過すると、ユーザーは MFA 登録が完了するまでサインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-144">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="ccfc3-145">セキュリティの既定値では、すべての組織が、既定で有効になっているユーザー サインインの基本レベルのセキュリティを確保しています。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-145">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="ccfc3-146">セキュリティの既定値を無効にして、条件付きアクセスポリシーを使用して MFA を優先させることができます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-146">You can disable security defaults in favor of MFA with Conditional Access policies.</span></span>

<span data-ttu-id="ccfc3-147">Azure ポータルの Azure AD の [**プロパティ**] ウィンドウで、セキュリティの既定値を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-147">You enable or disable security defaults from the **Properties** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/security-defaults-mfa.png)

<span data-ttu-id="ccfc3-148">Microsoft 365 プランでは、セキュリティの既定値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-148">You can use security defaults with any Microsoft 365 plan.</span></span>

<span data-ttu-id="ccfc3-149">詳細については、こちらの「[セキュリティの既定値の概要](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-149">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> 

### <a name="conditional-access-policies"></a><span data-ttu-id="ccfc3-150">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="ccfc3-150">Conditional Access policies</span></span>

<span data-ttu-id="ccfc3-151">条件付きアクセス ポリシーは、サインインが評価および許可される条件を指定する一連のルールです。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-151">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="ccfc3-152">たとえば、次のような条件付きアクセス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-152">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="ccfc3-153">ユーザーアカウント名が、Exchange、user、password、security、SharePoint、または全体管理者の役割を割り当てられているユーザーのグループのメンバーである場合は、アクセスを許可する前に MFA を必要とします。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-153">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="ccfc3-154">このポリシーを使用すると、これらの管理者の役割に割り当てられるか、または割り当てが解除された場合に、MFA の個々のユーザーアカウントを構成しなくても、グループのメンバーシップに基づいて MFA を要求できます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-154">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="ccfc3-155">また、条件付きアクセスポリシーを使用して、特定のアプリに MFA を要求したり、準拠デバイス (Windows 10 を実行しているラップトップなど) からサインインしたりするなど、より高度な機能を提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-155">You can also use Conditional Access policies for more advanced capabilities, such as requiring MFA for specific apps or that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="ccfc3-156">Azure portal で Azure AD の [**セキュリティ**] ウィンドウから条件付きアクセスポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-156">You configure Conditional Access policies from the **Security** pane for Azure AD in the Azure portal.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/conditional-access-mfa.png)

<span data-ttu-id="ccfc3-157">条件付きアクセスポリシーは、次の方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-157">You can use Conditional Access policies with:</span></span>

- <span data-ttu-id="ccfc3-158">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="ccfc3-158">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="ccfc3-159">Microsoft 365 E3 および E5</span><span class="sxs-lookup"><span data-stu-id="ccfc3-159">Microsoft 365 E3 and E5</span></span>
- <span data-ttu-id="ccfc3-160">Azure AD Premium P1 と Azure AD プレミアム P2 ライセンス</span><span class="sxs-lookup"><span data-stu-id="ccfc3-160">Azure AD Premium P1 and Azure AD Premium P2 licenses</span></span> 

<span data-ttu-id="ccfc3-161">Microsoft 365 Business Premium を使用する小規模な企業では、次の手順を使用して、条件付きアクセスポリシーを簡単に使用できます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-161">For small businesses with Microsoft 365 Business Premium, you can easily use Conditional Access policies with the following steps:</span></span>

1. <span data-ttu-id="ccfc3-162">MFA を必要とするユーザーアカウントを含むグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-162">Create a group to contain the user accounts that require MFA.</span></span>
2. <span data-ttu-id="ccfc3-163">[**グローバル管理者の MFA を必要と**する] ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-163">Enable the **Require MFA for global admins** policy.</span></span>
3. <span data-ttu-id="ccfc3-164">次の設定を使用して、グループベースの条件付きアクセスポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-164">Create a group-based Conditional Access policy with these settings:</span></span>
    - <span data-ttu-id="ccfc3-165">ユーザーおよびグループ > の割り当て: 上記の手順1でグループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-165">Assignments > Users and groups: The name of your group from Step 1 above.</span></span>
    - <span data-ttu-id="ccfc3-166">クラウドアプリまたはアクション > の割り当て: すべてのクラウドアプリ。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-166">Assignments > Cloud apps or actions: All cloud apps.</span></span>
    - <span data-ttu-id="ccfc3-167">アクセス権の付与には、多要素認証を必要と > アクセス許可 > 付与する > を制御します。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-167">Access controls > Grant > Grant access > Require multi-factor authentication.</span></span>
4. <span data-ttu-id="ccfc3-168">ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-168">Enable the policy.</span></span>
5. <span data-ttu-id="ccfc3-169">上記の手順1で作成したグループにユーザーアカウントを追加してテストします。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-169">Add a user account to the group created in Step 1 above and test.</span></span>
6. <span data-ttu-id="ccfc3-170">追加のユーザーアカウントに MFA を要求するには、手順1で作成したグループに MFA を追加します。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-170">To require MFA for additional user accounts, add them to the group created in Step 1.</span></span>

<span data-ttu-id="ccfc3-171">この条件付きアクセスポリシーを使用すると、ユーザーに対して MFA の要件を自分のペースでロールアウトできます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-171">This Conditional Access policy allows you to roll out the MFA requirement to your users at your own pace.</span></span>

<span data-ttu-id="ccfc3-172">企業では、次のポリシーを構成するために、[一般的な条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-172">Enterprises should use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span>

- [<span data-ttu-id="ccfc3-173">管理者に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="ccfc3-173">Require MFA for administrators</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [<span data-ttu-id="ccfc3-174">すべてのユーザーに MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="ccfc3-174">Require MFA for all users</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [<span data-ttu-id="ccfc3-175">従来の認証をブロックする</span><span class="sxs-lookup"><span data-stu-id="ccfc3-175">Block legacy authentication</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)

<span data-ttu-id="ccfc3-176">詳細については、「[条件付きアクセスの概要](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-176">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="azure-ad-identity-protection"></a><span data-ttu-id="ccfc3-177">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="ccfc3-177">Azure AD Identity Protection</span></span>

<span data-ttu-id="ccfc3-178">Azure AD Identity Protection を使用すると、[サインインリスクが中または高の場合に、MFA を必要と](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk)する追加の条件付きアクセスポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-178">With Azure AD Identity Protection, you can create an additional Conditional Access policy to [require MFA when sign-in risk is medium or high](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies#require-mfa-based-on-sign-in-risk).</span></span>

<span data-ttu-id="ccfc3-179">Azure AD Id 保護とリスクベースの条件付きアクセスポリシーは、次の方法で使用できます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-179">You can use Azure AD Identity Protection and risk-based Conditional Access policies with:</span></span>

- <span data-ttu-id="ccfc3-180">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ccfc3-180">Microsoft 365 E5</span></span>
- <span data-ttu-id="ccfc3-181">Azure AD Premium P2 ライセンス</span><span class="sxs-lookup"><span data-stu-id="ccfc3-181">Azure AD Premium P2 licenses</span></span>

<span data-ttu-id="ccfc3-182">詳細については、この「[Azure AD Identity Protection の概要](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-182">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

### <a name="mfa-for-an-individual-user-account-not-recommended"></a><span data-ttu-id="ccfc3-183">個別のユーザーアカウントの MFA (推奨されません)</span><span class="sxs-lookup"><span data-stu-id="ccfc3-183">MFA for an individual user account (not recommended)</span></span>

<span data-ttu-id="ccfc3-184">ユーザーアカウントのサインインに MFA を必要とするには、セキュリティの既定値または条件付きアクセスポリシーを使用する必要があります。ただし、これらのいずれかを使用できない場合は、管理者の役割、特に全体管理者の役割を持つユーザーアカウントに対して、任意のサイズのサブスクリプションに対して MFA を強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-184">You should be using either security defaults or Conditional Access policies to require MFA for your user account sign-ins. However, if either of these cannot be used, Microsoft strongly recommends MFA for user accounts that have administrator roles, especially the global administrator role, for any size subscription.</span></span> 

<span data-ttu-id="ccfc3-185">Microsoft 365 管理センターの**アクティブなユーザー**ウィンドウから、個々のユーザーアカウントに対して MFA を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-185">You enable MFA for individual user accounts from the **Active user** pane of the Microsoft 365 admin center.</span></span>

![](../../media/multi-factor-authentication-microsoft-365/per-user-mfa.png)

<span data-ttu-id="ccfc3-186">有効にすると、ユーザーが次回サインインしたときに、MFA を登録し、追加の検証方法を選択してテストするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-186">After being enabled, the next time the user signs in, they will be prompted to register for MFA and to choose and test the additional verification method.</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="ccfc3-187">これらの方法を一緒に使用する</span><span class="sxs-lookup"><span data-stu-id="ccfc3-187">Using these methods together</span></span>

<span data-ttu-id="ccfc3-188">この表は、セキュリティの既定値、条件付きアクセス ポリシー、およびユーザーごとのアカウント設定で MFA を有効にした結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-188">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|| <span data-ttu-id="ccfc3-189">Enabled</span><span class="sxs-lookup"><span data-stu-id="ccfc3-189">Enabled</span></span> | <span data-ttu-id="ccfc3-190">無効</span><span class="sxs-lookup"><span data-stu-id="ccfc3-190">Disabled</span></span> | <span data-ttu-id="ccfc3-191">第 2 の認証方法</span><span class="sxs-lookup"><span data-stu-id="ccfc3-191">Secondary authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="ccfc3-192">**セキュリティの既定値**</span><span class="sxs-lookup"><span data-stu-id="ccfc3-192">**Security defaults**</span></span> | <span data-ttu-id="ccfc3-193">条件付きアクセス ポリシーを使用できない</span><span class="sxs-lookup"><span data-stu-id="ccfc3-193">Can’t use Conditional Access policies</span></span> |   <span data-ttu-id="ccfc3-194">条件付きアクセス ポリシーを使用できる</span><span class="sxs-lookup"><span data-stu-id="ccfc3-194">Can use Conditional Access policies</span></span> | <span data-ttu-id="ccfc3-195">Microsoft Authenticator アプリ</span><span class="sxs-lookup"><span data-stu-id="ccfc3-195">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="ccfc3-196">**条件付きアクセス ポリシー**</span><span class="sxs-lookup"><span data-stu-id="ccfc3-196">**Conditional Access policies**</span></span> |<span data-ttu-id="ccfc3-197">いずれかが有効になっている場合、セキュリティの既定値を有効にすることはできません</span><span class="sxs-lookup"><span data-stu-id="ccfc3-197">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="ccfc3-198">すべての設定が無効になっている場合は、セキュリティの既定値を有効にできます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-198">If all are disabled, you can enable security defaults</span></span> | <span data-ttu-id="ccfc3-199">MFA への登録時にユーザー指定</span><span class="sxs-lookup"><span data-stu-id="ccfc3-199">User-specified during MFA registration</span></span> |
| <span data-ttu-id="ccfc3-200">**ユーザーごとのアカウントの設定 (推奨されません)**</span><span class="sxs-lookup"><span data-stu-id="ccfc3-200">**Per-user account setting (not recommended)**</span></span> | <span data-ttu-id="ccfc3-201">各サインインで MFA を必要とするセキュリティの既定値と条件付きアクセスポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-201">Overrides security defaults and Conditional Access policies requiring MFA at each sign in</span></span> | <span data-ttu-id="ccfc3-202">セキュリティの既定値と条件付きアクセスポリシーによって上書きされます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-202">Overridden by security defaults and Conditional Access policies</span></span> | <span data-ttu-id="ccfc3-203">MFA への登録時にユーザー指定</span><span class="sxs-lookup"><span data-stu-id="ccfc3-203">User-specified during MFA registration</span></span>|
||||

<span data-ttu-id="ccfc3-204">セキュリティの既定値が有効になっている場合は、すべての新規ユーザーが MFA 登録を求め、次のサインイン時に Microsoft Authenticator アプリを使用するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-204">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app at their next sign-in.</span></span>

## <a name="ways-to-manage-mfa-settings"></a><span data-ttu-id="ccfc3-205">MFA 設定を管理する方法</span><span class="sxs-lookup"><span data-stu-id="ccfc3-205">Ways to manage MFA settings</span></span>

<span data-ttu-id="ccfc3-206">MFA の設定を管理する方法は2つあります。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-206">There are two ways to manage MFA settings.</span></span>

<span data-ttu-id="ccfc3-207">Azure portal では、次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-207">In the Azure portal, you can:</span></span>

- <span data-ttu-id="ccfc3-208">セキュリティの既定値を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="ccfc3-208">Enable and disable security defaults</span></span>
- <span data-ttu-id="ccfc3-209">条件付きアクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="ccfc3-209">Configure Conditional Access policies</span></span>

<span data-ttu-id="ccfc3-210">Microsoft 365 管理センターでは、ユーザー単位およびサービスの MFA 設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="ccfc3-210">In the Microsoft 365 admin center, you can configure per-user and service MFA settings.</span></span>

## <a name="your-next-step"></a><span data-ttu-id="ccfc3-211">次の手順</span><span class="sxs-lookup"><span data-stu-id="ccfc3-211">Your next step</span></span>

[<span data-ttu-id="ccfc3-212">Microsoft 365 の MFA をセットアップする</span><span class="sxs-lookup"><span data-stu-id="ccfc3-212">Set up MFA for Microsoft 365</span></span>](set-up-multi-factor-authentication.md)

