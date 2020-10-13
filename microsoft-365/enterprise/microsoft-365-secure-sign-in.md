---
title: Microsoft 365 テナントへのユーザー サインインの保護
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/30/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365initiative-coredeploy
ms.custom: ''
description: ユーザーが多要素認証（MFA）およびその他の機能を使用して安全にサインインすることを要求します。
ms.openlocfilehash: a3a63dfc06f5470c2151cd2ff140ad5dee19b0ce
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446079"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a><span data-ttu-id="0f046-103">Microsoft 365 テナントへのユーザー サインインの保護</span><span class="sxs-lookup"><span data-stu-id="0f046-103">Secure user sign-ins to your Microsoft 365 tenant</span></span>

<span data-ttu-id="0f046-104">ユーザー サインインのセキュリティを強化するには：</span><span class="sxs-lookup"><span data-stu-id="0f046-104">To increase the security of user sign-ins:</span></span>

- <span data-ttu-id="0f046-105">Windows Hello for Business を使用する</span><span class="sxs-lookup"><span data-stu-id="0f046-105">Use Windows Hello for Business</span></span>
- <span data-ttu-id="0f046-106">Azure Active Directory（Azure AD）パスワード保護を使用する</span><span class="sxs-lookup"><span data-stu-id="0f046-106">Use Azure Active Directory (Azure AD) Password Protection</span></span>
- <span data-ttu-id="0f046-107">多要素認証 (MFA) を使用する</span><span class="sxs-lookup"><span data-stu-id="0f046-107">Use multi-factor authentication (MFA)</span></span>
- <span data-ttu-id="0f046-108">ID とデバイスのアクセス構成を展開する</span><span class="sxs-lookup"><span data-stu-id="0f046-108">Deploy identity and device access configurations</span></span>
- <span data-ttu-id="0f046-109">Azure AD Identity Protection で資格情報を侵害から保護する</span><span class="sxs-lookup"><span data-stu-id="0f046-109">Protect against credential compromise with Azure AD Identity Protection</span></span>

## <a name="windows-hello-for-business"></a><span data-ttu-id="0f046-110">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="0f046-110">Windows Hello for Business</span></span>

<span data-ttu-id="0f046-111">Windows 10 Enterprise の Windows Hello for Business では、Windows デバイスにサインオンするときのパスワードを強力な 2 要素認証に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="0f046-111">Windows Hello for Business in Windows 10 Enterprise replaces passwords with strong two-factor authentication when signing on a Windows device.</span></span> <span data-ttu-id="0f046-112">この 2 要素認証は、デバイスと生体認証または PIN に関連付けられる新しい種類のユーザー資格情報です。</span><span class="sxs-lookup"><span data-stu-id="0f046-112">The two factors are a new type of user credential that is tied to a device and a biometric or PIN.</span></span>

<span data-ttu-id="0f046-113">詳しくは、「[Windows Hello for Business の概要](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0f046-113">For more information, see [Windows Hello for Business Overview](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-overview).</span></span>


## <a name="azure-ad-password-protection"></a><span data-ttu-id="0f046-114">Azure AD パスワード保護</span><span class="sxs-lookup"><span data-stu-id="0f046-114">Azure AD Password Protection</span></span>

<span data-ttu-id="0f046-115">Azure AD パスワード保護は、既知の脆弱なパスワードとそのバリアントを検出してブロックし、組織固有の脆弱な用語もブロックできます。</span><span class="sxs-lookup"><span data-stu-id="0f046-115">Azure AD Password Protection detects and blocks known weak passwords and their variants and can also block additional weak terms that are specific to your organization.</span></span> <span data-ttu-id="0f046-116">既定のグローバル禁止パスワード リストは、Azure AD テナントのすべてのユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0f046-116">Default global banned password lists are automatically applied to all users in an Azure AD tenant.</span></span> <span data-ttu-id="0f046-117">カスタムの禁止パスワード リストに追加のエントリを定義できます。</span><span class="sxs-lookup"><span data-stu-id="0f046-117">You can define additional entries in a custom banned password list.</span></span> <span data-ttu-id="0f046-118">ユーザーがパスワードを変更またはリセットすると、これらの禁止パスワード リストがチェックされ、強力なパスワードの使用が強制されます。</span><span class="sxs-lookup"><span data-stu-id="0f046-118">When users change or reset their passwords, these banned password lists are checked to enforce the use of strong passwords.</span></span>

<span data-ttu-id="0f046-119">詳細については、[Azure AD パスワード保護の設定](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f046-119">For more information, see [Configure Azure AD password protection](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).</span></span>

## <a name="mfa"></a><span data-ttu-id="0f046-120">MFA</span><span class="sxs-lookup"><span data-stu-id="0f046-120">MFA</span></span>

<span data-ttu-id="0f046-121">MFA では、ユーザーのサインインは、ユーザー アカウントのパスワード以外に追加の検証を受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f046-121">MFA requires that user sign-ins be subject to an additional verification beyond the user account password.</span></span> <span data-ttu-id="0f046-122">悪意のあるユーザーがユーザー アカウントのパスワードを決定した場合でも、アクセスが許可される前にスマートフォンに送信されるテキスト メッセージなど、追加の検証に応答できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f046-122">Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.</span></span>

![正しいパスワードと追加認証によりサインインが成功する](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

<span data-ttu-id="0f046-124">MFA を使用するための最初の手順は、***すべての管理者アカウント（特権アカウント）に MFA を要求する***ことです。</span><span class="sxs-lookup"><span data-stu-id="0f046-124">Your first step in using MFA is to ***require it for all administrator accounts***, also known as privileged accounts.</span></span>

<span data-ttu-id="0f046-125">この最初の手順以外にも、Microsoft はすべてのユーザーに MFA をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0f046-125">Beyond this first step, Microsoft recommends MFA For all users.</span></span>

<span data-ttu-id="0f046-126">Microsoft 365 プランに基づき管理者またはユーザーに MFA の使用を要求する方法は3つあります。</span><span class="sxs-lookup"><span data-stu-id="0f046-126">There are three ways to require your administrators or users to use MFA based on your Microsoft 365 plan.</span></span>

| <span data-ttu-id="0f046-127">プラン</span><span class="sxs-lookup"><span data-stu-id="0f046-127">Plan</span></span> | <span data-ttu-id="0f046-128">推奨事項</span><span class="sxs-lookup"><span data-stu-id="0f046-128">Recommendation</span></span> |
|---------|---------|
|<span data-ttu-id="0f046-129">Microsoft 365 のすべてのプラン (Azure AD Premium P1 または P2 ライセンスなし)</span><span class="sxs-lookup"><span data-stu-id="0f046-129">All Microsoft 365 plans (without Azure AD Premium P1 or P2 licenses)</span></span>     |<span data-ttu-id="0f046-130">[Azure AD でセキュリティの既定値を有効にします](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="0f046-130">[Enable Security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> <span data-ttu-id="0f046-131">Azure AD のセキュリティの既定値には、ユーザーと管理者用の MFA が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0f046-131">Security defaults in Azure AD include MFA for users and administrators.</span></span>   |
|<span data-ttu-id="0f046-132">Microsoft 365 E3 (Azure AD Premium P1 ライセンスを含む)</span><span class="sxs-lookup"><span data-stu-id="0f046-132">Microsoft 365 E3 (includes Azure AD Premium P1 licenses)</span></span>     | <span data-ttu-id="0f046-133">[一般的な条件付きアクセス ポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)を使用して、次のポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="0f046-133">Use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span> <br><span data-ttu-id="0f046-134">- [管理者に MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span><span class="sxs-lookup"><span data-stu-id="0f046-134">- [Require MFA for administrators](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span></span> <br><span data-ttu-id="0f046-135">- [すべてのユーザーに MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="0f046-135">- [Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span></span> <br> <span data-ttu-id="0f046-136">- [従来の認証をブロックする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span><span class="sxs-lookup"><span data-stu-id="0f046-136">- [Block legacy authentication](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span></span>       |
|<span data-ttu-id="0f046-137">Microsoft 365 E5 (Azure AD Premium P2 ライセンスを含む)</span><span class="sxs-lookup"><span data-stu-id="0f046-137">Microsoft 365 E5 (includes Azure AD Premium P2 licenses)</span></span>     | <span data-ttu-id="0f046-138">Azure AD Identity Protection を利用して、次の 2 つのポリシーを作成して、Microsoft の[条件付きアクセスと関連ポリシーの推奨されるセット](../security/office-365-security/identity-access-policies.md)の実装を開始します。</span><span class="sxs-lookup"><span data-stu-id="0f046-138">Taking advantage of Azure AD Identity Protection, begin to implement Microsoft's [recommended set of conditional access and related policies](../security/office-365-security/identity-access-policies.md) by creating these two policies:</span></span><br> <span data-ttu-id="0f046-139">- [サインインのリスクが中、または高のときに MFA を要求する](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="0f046-139">- [Require MFA when sign-in risk is medium or high](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span> <br><span data-ttu-id="0f046-140">- [高リスク ユーザーはパスワードを変更する必要がある](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)</span><span class="sxs-lookup"><span data-stu-id="0f046-140">- [High risk users must change password](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)</span></span>       |
| | |

### <a name="security-defaults"></a><span data-ttu-id="0f046-141">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="0f046-141">Security defaults</span></span>

<span data-ttu-id="0f046-142">セキュリティの既定値は、2019 年 10 月 21 日以降に作成された Microsoft 365 および Office 365 の有料または試用版サブスクリプションの新機能です。</span><span class="sxs-lookup"><span data-stu-id="0f046-142">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="0f046-143">これらのサブスクリプションではセキュリティの既定値がオンになっており、***すべてのユーザーが Microsoft Authenticator アプリで MFA を使用する必要があります***。</span><span class="sxs-lookup"><span data-stu-id="0f046-143">These subscriptions have security defaults turned on, which ***requires all of your users to use MFA with the Microsoft Authenticator app***.</span></span>
 
<span data-ttu-id="0f046-144">ユーザーは、スマートフォンから Microsoft Authenticator アプリを使用して MFA に 14 日間登録できます。これは、セキュリティの既定値が有効になった後、初めてサインインしたときから始まります。</span><span class="sxs-lookup"><span data-stu-id="0f046-144">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="0f046-145">14 日が経過すると、ユーザーは MFA 登録が完了するまでサインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="0f046-145">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="0f046-146">セキュリティの既定値では、すべての組織が、既定で有効になっているユーザー サインインの基本レベルのセキュリティを確保しています。</span><span class="sxs-lookup"><span data-stu-id="0f046-146">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="0f046-147">条件付きアクセス ポリシーを使用する MFA を優先して、または個々のアカウントに対して、セキュリティの既定値を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0f046-147">You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.</span></span>

<span data-ttu-id="0f046-148">詳細については、「[セキュリティの既定値の概要](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f046-148">For more information, see the [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="0f046-149">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="0f046-149">Conditional Access policies</span></span>

<span data-ttu-id="0f046-150">条件付きアクセス ポリシーとは、サインインが評価され、アクセスが許可される条件を指定する一連のルールです。</span><span class="sxs-lookup"><span data-stu-id="0f046-150">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and access is granted.</span></span> <span data-ttu-id="0f046-151">たとえば、次のような条件付きアクセス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0f046-151">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="0f046-152">ユーザー アカウント名が Exchange、ユーザー、パスワード、セキュリティ、SharePoint、またはグローバル管理者の役割を割り当てられたユーザーのグループのメンバーである場合、アクセスを許可する前に MFA が必要です。</span><span class="sxs-lookup"><span data-stu-id="0f046-152">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="0f046-153">このポリシーを使用すると、これらの管理者の役割から割り当てられたり、または割り当てられなかったりした場合に、個別のユーザー アカウントを MFA 用に構成しようとするのではなく、グループ メンバーシップに基づいて MFA を要求することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="0f046-153">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="0f046-154">条件付きアクセス ポリシーを使用して、Windows 10 を実行しているノート PC などの準拠デバイスからサインインする必要があるなど、より高度な機能を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="0f046-154">You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="0f046-155">条件付きアクセスには、Microsoft 365 E3 および E5 に含まれている Azure AD Premium P1 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0f046-155">Conditional Access requires Azure AD Premium P1 licenses, which are included with Microsoft 365 E3 and E5.</span></span>

<span data-ttu-id="0f046-156">詳細については、「[条件付きアクセスの概要](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f046-156">For more information, see the [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="0f046-157">これらの方法を組み合わせて使用する</span><span class="sxs-lookup"><span data-stu-id="0f046-157">Using these methods together</span></span>

<span data-ttu-id="0f046-158">以下の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="0f046-158">Keep the following in mind:</span></span>

- <span data-ttu-id="0f046-159">条件付きアクセス ポリシーを有効にしている場合、セキュリティの既定値を有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0f046-159">You cannot enable security defaults if you have any Conditional Access policies enabled.</span></span>
- <span data-ttu-id="0f046-160">セキュリティの既定値を有効にしている場合は、条件付きアクセス ポリシーを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0f046-160">You cannot enable any Conditional Access policies if you have security defaults enabled.</span></span>

<span data-ttu-id="0f046-161">セキュリティの既定値が有効になっている場合、すべての新しいユーザーは MFA 登録と Microsoft Authenticator アプリの使用を求められます。</span><span class="sxs-lookup"><span data-stu-id="0f046-161">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app.</span></span> 

<span data-ttu-id="0f046-162">この表は、セキュリティの既定値と条件付きアクセス ポリシーで MFA を有効にした結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="0f046-162">This table shows the results of enabling MFA with security defaults and Conditional Access policies.</span></span>

| <span data-ttu-id="0f046-163">メソッド</span><span class="sxs-lookup"><span data-stu-id="0f046-163">Method</span></span> | <span data-ttu-id="0f046-164">Enabled</span><span class="sxs-lookup"><span data-stu-id="0f046-164">Enabled</span></span> | <span data-ttu-id="0f046-165">無効</span><span class="sxs-lookup"><span data-stu-id="0f046-165">Disabled</span></span> | <span data-ttu-id="0f046-166">追加の認証方法</span><span class="sxs-lookup"><span data-stu-id="0f046-166">Additional authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="0f046-167">**セキュリティの既定値**</span><span class="sxs-lookup"><span data-stu-id="0f046-167">**Security defaults**</span></span>  | <span data-ttu-id="0f046-168">条件付きアクセス ポリシーを使用できない</span><span class="sxs-lookup"><span data-stu-id="0f046-168">Can’t use Conditional Access policies</span></span> | <span data-ttu-id="0f046-169">条件付きアクセス ポリシーを使用できる</span><span class="sxs-lookup"><span data-stu-id="0f046-169">Can use Conditional Access policies</span></span> | <span data-ttu-id="0f046-170">Microsoft Authenticator アプリ</span><span class="sxs-lookup"><span data-stu-id="0f046-170">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="0f046-171">**条件付きアクセス ポリシー**</span><span class="sxs-lookup"><span data-stu-id="0f046-171">**Conditional Access policies**</span></span> | <span data-ttu-id="0f046-172">いずれかが有効になっている場合、セキュリティの既定値を有効にすることはできません</span><span class="sxs-lookup"><span data-stu-id="0f046-172">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="0f046-173">すべてが無効になっている場合は、セキュリティの既定値を有効にすることができます</span><span class="sxs-lookup"><span data-stu-id="0f046-173">If all are disabled, you can enable security defaults</span></span>  | <span data-ttu-id="0f046-174">MFA 登録中にユーザーが指定</span><span class="sxs-lookup"><span data-stu-id="0f046-174">User specifies during MFA registration</span></span>  |
||||

## <a name="identity-and-device-access-configurations"></a><span data-ttu-id="0f046-175">ID とデバイスのアクセス構成</span><span class="sxs-lookup"><span data-stu-id="0f046-175">Identity and device access configurations</span></span>

<span data-ttu-id="0f046-176">ID とデバイス アクセスの設定とポリシーとは、特定のアクセス要求を許可するかどうか、およびどのような条件下で許可するかを決定する条件付きアクセス、Intune、およびAzure AD Identity Protection ポリシーと組み合わせて推奨される必須機能とその設定です。</span><span class="sxs-lookup"><span data-stu-id="0f046-176">Identity and device access settings and policies are recommended prerequisite features and their settings combined with Conditional Access, Intune, and Azure AD Identity Protection policies that determine whether a given access request should be granted and under what conditions.</span></span> <span data-ttu-id="0f046-177">この決定は、サインインのユーザーアカウント、使用しているデバイス、ユーザーがアクセスに使用しているアプリ、アクセス要求が行われた場所、および要求のリスクの評価に基づいています。</span><span class="sxs-lookup"><span data-stu-id="0f046-177">This determination is based on the user account of the sign-in, the device being used, the app the user is using for access, the location from which the access request is made, and an assessment of the risk of the request.</span></span> <span data-ttu-id="0f046-178">この機能により、承認されたユーザーとデバイスのみが重要なリソースにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="0f046-178">This capability helps ensure that only approved users and devices can access your critical resources.</span></span>

>[!Note]
><span data-ttu-id="0f046-179">Azure AD Identity Protection には、Microsoft 365 E5 に含まれている Azure AD Premium P2 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="0f046-179">Azure AD Identity Protection requires Azure AD Premium P2 licenses, which are included with Microsoft 365 E5.</span></span>
>

<span data-ttu-id="0f046-180">ID とデバイスのアクセス ポリシーは、3つの層で使用するように定義されています。</span><span class="sxs-lookup"><span data-stu-id="0f046-180">Identity and device access policies are defined to be used in three tiers:</span></span> 

- <span data-ttu-id="0f046-181">ベースライン保護とは、アプリとデータにアクセスするID とデバイスの最小レベルのセキュリティです。</span><span class="sxs-lookup"><span data-stu-id="0f046-181">Baseline protection is a minimum level of security for your identities and devices that access your apps and data.</span></span>
- <span data-ttu-id="0f046-182">機密保護は、特定のデータに追加のセキュリティを提供します。</span><span class="sxs-lookup"><span data-stu-id="0f046-182">Sensitive protection provides additional security for specific data.</span></span> <span data-ttu-id="0f046-183">ID とデバイスは、より高いレベルのセキュリティとデバイスの正常性要件の対象です。</span><span class="sxs-lookup"><span data-stu-id="0f046-183">Identities and devices are subject to higher levels of security and device health requirements.</span></span>
- <span data-ttu-id="0f046-184">高度に規制または分類されたデータが存在する環境の保護は、通常、高度に分類されている、企業秘密が含まれている、またはデータ規制の対象となる少量のデータ用です。</span><span class="sxs-lookup"><span data-stu-id="0f046-184">Protection for environments with highly regulated or classified data is for typically small amounts of data that are highly classified, contain trade secrets, or is subject to data regulations.</span></span> <span data-ttu-id="0f046-185">ID とデバイスは、より高いレベルのセキュリティとデバイスの正常性用件の対象です。</span><span class="sxs-lookup"><span data-stu-id="0f046-185">Identities and devices are subject to much higher levels of security and device health requirements.</span></span> 

<span data-ttu-id="0f046-186">これらの層とそれに対応する構成は、データ、ID、およびデバイス全体で一貫したレベルの保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="0f046-186">These tiers and their corresponding configurations provide consistent levels of protection across your data, identities, and devices.</span></span>

<span data-ttu-id="0f046-187">マイクロソフトは、Microsoft Teams、Exchange Online、SharePointの特定の設定を含む、組織内のID とデバイスのアクセス ポリシーを構成および展開することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0f046-187">Microsoft highly recommends configuring and rolling out identity and device access policies in your organization, including specific settings for Microsoft Teams, Exchange Online, and SharePoint.</span></span> <span data-ttu-id="0f046-188">詳細については、[ID とデバイスのアクセス設定](../security/office-365-security/microsoft-365-policies-configurations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f046-188">For more information, see [Identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md).</span></span>

## <a name="azure-ad-identity-protection"></a><span data-ttu-id="0f046-189">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="0f046-189">Azure AD Identity Protection</span></span>

<span data-ttu-id="0f046-190">このセクションでは、資格情報が侵害されないように保護するポリシーを構成する方法を学習します。攻撃者は組織のクラウド サービスとデータにアクセスするため、ユーザーのアカウント名とパスワードを突き止めて、資格情報を侵害しようとします。</span><span class="sxs-lookup"><span data-stu-id="0f046-190">In this section, you'll learn how to configure policies that protect against credential compromise, where an attacker determines a user’s account name and password to gain access to an organization’s cloud services and data.</span></span> <span data-ttu-id="0f046-191">Azure AD Identity Protection は、攻撃者によるユーザー アカウントの資格情報の侵害を防ぐさまざまな方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="0f046-191">Azure AD Identity Protection provides a number of ways to help prevent an attacker from compromising a user account's credentials.</span></span>

<span data-ttu-id="0f046-192">Azure AD Identity Protection では次の作業を実行できます。</span><span class="sxs-lookup"><span data-stu-id="0f046-192">With Azure AD Identity Protection, you can:</span></span>

|<span data-ttu-id="0f046-193">機能</span><span class="sxs-lookup"><span data-stu-id="0f046-193">Capability</span></span>|<span data-ttu-id="0f046-194">説明</span><span class="sxs-lookup"><span data-stu-id="0f046-194">Description</span></span>|
|:---------|:---------|
| <span data-ttu-id="0f046-195">組織の ID における潜在的な脆弱性の洗い出しと対処</span><span class="sxs-lookup"><span data-stu-id="0f046-195">Determine and address potential vulnerabilities in your organization’s identities</span></span> | <span data-ttu-id="0f046-196">Azure AD では機械学習を使用して、サインインやサインイン後のアクティビティなどの異常や不審なアクティビティを検出します。</span><span class="sxs-lookup"><span data-stu-id="0f046-196">Azure AD uses machine learning to detect anomalies and suspicious activity, such as sign-ins and post-sign-in activities.</span></span> <span data-ttu-id="0f046-197">このデータを使用して、Azure AD Identity Protection でレポートとアラートを生成すると、ユーザーによる問題の評価と措置に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0f046-197">Using this data, Azure AD Identity Protection generates reports and alerts that help you evaluate the issues and take action.</span></span>|
|<span data-ttu-id="0f046-198">組織の ID に関連する不審なアクションの検出と自動対応</span><span class="sxs-lookup"><span data-stu-id="0f046-198">Detect suspicious actions that are related to your organization’s identities and respond to them automatically</span></span>|<span data-ttu-id="0f046-199">特定のリスク レベルに到達すると自動的に検出された問題に対処するよう、リスクベースのポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="0f046-199">You can configure risk-based policies that automatically respond to detected issues when a specified risk level has been reached.</span></span> <span data-ttu-id="0f046-200">Azure AD および Microsoft Intune で提供されている他の条件付きアクセス コントロールにこれらのポリシーが加わると、その次のサインイン用のパスワードのリセットや Azure Multi-Factor Authentication を含め、自動的にアクセスをブロックしたり、修正処置を取ったりすることができます。</span><span class="sxs-lookup"><span data-stu-id="0f046-200">These policies, in addition to other Conditional Access controls provided by Azure AD and Microsoft Intune, can either automatically block access or take corrective actions, including password resets and requiring Azure Multi-Factor Authentication for subsequent sign-ins.</span></span> |
| <span data-ttu-id="0f046-201">不審なインシデントを調査し、管理操作によって解決する</span><span class="sxs-lookup"><span data-stu-id="0f046-201">Investigate suspicious incidents and resolve them with administrative actions</span></span> | <span data-ttu-id="0f046-p116">セキュリティ インシデントに関する情報を使用して、リスク イベントを調査できます。調査の追跡と修復処理 (パスワードのリセットなど) の開始のための基本的なワークフローを利用できます。</span><span class="sxs-lookup"><span data-stu-id="0f046-p116">You can investigate risk events using information about the security incident. Basic workflows are available to track investigations and initiate remediation actions, such as password resets.</span></span> |
|||

<span data-ttu-id="0f046-204">[Azure AD Identity Protection の詳細情報](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f046-204">See [more information about Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection).</span></span>

<span data-ttu-id="0f046-205">[Azure AD Identity Protection を有効にする手順](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f046-205">See the [steps to enable Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable).</span></span>

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a><span data-ttu-id="0f046-206">MFA と安全なサインインのための管理技術リソース</span><span class="sxs-lookup"><span data-stu-id="0f046-206">Admin technical resources for MFA and secure sign-ins</span></span>

- [<span data-ttu-id="0f046-207">MFA for Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0f046-207">MFA for Microsoft 365</span></span>](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [<span data-ttu-id="0f046-208">Microsoft 365 の ID ロードマップ</span><span class="sxs-lookup"><span data-stu-id="0f046-208">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)
- [<span data-ttu-id="0f046-209">Azure Academy Azure AD トレーニング ビデオ</span><span class="sxs-lookup"><span data-stu-id="0f046-209">Azure Academy Azure AD training videos</span></span>](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [<span data-ttu-id="0f046-210">Azure 多要素認証の登録ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="0f046-210">Configure the Azure Multi-Factor Authentication registration policy</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [<span data-ttu-id="0f046-211">ID とデバイスのアクセス構成</span><span class="sxs-lookup"><span data-stu-id="0f046-211">Identity and device access configurations</span></span>](../security/office-365-security/microsoft-365-policies-configurations.md)

## <a name="next-step"></a><span data-ttu-id="0f046-212">次のステップ</span><span class="sxs-lookup"><span data-stu-id="0f046-212">Next step</span></span>

[<span data-ttu-id="0f046-213">ユーザー アカウントを管理する</span><span class="sxs-lookup"><span data-stu-id="0f046-213">Manage your user accounts</span></span>](manage-microsoft-365-accounts.md)