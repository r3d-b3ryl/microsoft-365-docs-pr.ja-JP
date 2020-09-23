---
title: Microsoft 365 テナントへのユーザー サインインの保護
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/16/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: ユーザーが多要素認証（MFA）およびその他の機能を使用して安全にサインインすることを要求します。
ms.openlocfilehash: 6c8f58e54ae21b4a5e1566dc72673e1d69152863
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2020
ms.locfileid: "48132247"
---
# <a name="secure-user-sign-ins-to-your-microsoft-365-tenant"></a><span data-ttu-id="1bfa8-103">Microsoft 365 テナントへのユーザー サインインの保護</span><span class="sxs-lookup"><span data-stu-id="1bfa8-103">Secure user sign-ins to your Microsoft 365 tenant</span></span>

<span data-ttu-id="1bfa8-104">ユーザー サインインのセキュリティを強化するには：</span><span class="sxs-lookup"><span data-stu-id="1bfa8-104">To increase the security of user sign-ins:</span></span>

- <span data-ttu-id="1bfa8-105">Azure Active Directory（Azure AD）パスワード保護を使用する</span><span class="sxs-lookup"><span data-stu-id="1bfa8-105">Use Azure Active Directory (Azure AD) Password Protection</span></span>
- <span data-ttu-id="1bfa8-106">多要素認証 (MFA) を使用する</span><span class="sxs-lookup"><span data-stu-id="1bfa8-106">Use multi-factor authentication (MFA)</span></span>
- <span data-ttu-id="1bfa8-107">ID とデバイス アクセス ポリシーを展開する</span><span class="sxs-lookup"><span data-stu-id="1bfa8-107">Deploy identity and device access policies</span></span>

## <a name="azure-ad-password-protection"></a><span data-ttu-id="1bfa8-108">Azure AD パスワード保護</span><span class="sxs-lookup"><span data-stu-id="1bfa8-108">Azure AD Password Protection</span></span>

<span data-ttu-id="1bfa8-109">Azure AD パスワード保護は、既知の脆弱なパスワードとそのバリアントを検出してブロックし、組織固有の脆弱な用語もブロックできます。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-109">Azure AD Password Protection detects and blocks known weak passwords and their variants, and can also block additional weak terms that are specific to your organization.</span></span> <span data-ttu-id="1bfa8-110">既定のグローバル禁止パスワード リストは、Azure AD テナントのすべてのユーザーに自動的に適用されます。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-110">Default global banned password lists are automatically applied to all users in an Azure AD tenant.</span></span> <span data-ttu-id="1bfa8-111">カスタムの禁止パスワード リストに追加のエントリを定義できます。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-111">You can define additional entries in a custom banned password list.</span></span> <span data-ttu-id="1bfa8-112">ユーザーがパスワードを変更またはリセットすると、これらの禁止パスワード リストがチェックされ、強力なパスワードの使用が強制されます。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-112">When users change or reset their passwords, these banned password lists are checked to enforce the use of strong passwords.</span></span>

<span data-ttu-id="1bfa8-113">詳細については、[Azure AD パスワード保護の設定](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-113">For more information, see [Configure Azure AD password protection](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad).</span></span>

## <a name="mfa"></a><span data-ttu-id="1bfa8-114">MFA</span><span class="sxs-lookup"><span data-stu-id="1bfa8-114">MFA</span></span>

<span data-ttu-id="1bfa8-115">MFA では、ユーザーのサインインは、ユーザー アカウントのパスワード以外に追加の検証を受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-115">MFA requires that user sign-ins be subject to an additional verification beyond the user account password.</span></span> <span data-ttu-id="1bfa8-116">悪意のあるユーザーがユーザー アカウントのパスワードを決定した場合でも、アクセスが許可される前にスマートフォンに送信されるテキスト メッセージなど、追加の検証に応答できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-116">Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.</span></span>

![正しいパスワードと追加認証によりサインインが成功する](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

<span data-ttu-id="1bfa8-118">MFA を使用するための最初の手順は、***すべての管理者アカウント（特権アカウント）に MFA を要求する***ことです。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-118">Your first step in using MFA is to ***require it for all administrator accounts***, also known as privileged accounts.</span></span>

<span data-ttu-id="1bfa8-119">この最初の手順以外にも、マイクロソフトはすべてのユーザーに MFA を強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-119">Beyond this first step, Microsoft strongly recommends MFA For all users.</span></span>

<span data-ttu-id="1bfa8-120">Microsoft 365 プランに基づき管理者またはユーザーに MFA の使用を要求する方法は3つあります。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-120">There are three ways to require your administrators or users to use MFA based on your Microsoft 365 plan.</span></span>

| <span data-ttu-id="1bfa8-121">プラン</span><span class="sxs-lookup"><span data-stu-id="1bfa8-121">Plan</span></span> | <span data-ttu-id="1bfa8-122">推奨事項</span><span class="sxs-lookup"><span data-stu-id="1bfa8-122">Recommendation</span></span> |
|---------|---------|
|<span data-ttu-id="1bfa8-123">Microsoft 365 のすべてのプラン (Azure AD Premium P1 または P2 ライセンスなし)</span><span class="sxs-lookup"><span data-stu-id="1bfa8-123">All Microsoft 365 plans (without Azure AD Premium P1 or P2 licenses)</span></span>     |<span data-ttu-id="1bfa8-124">[Azure AD でセキュリティの既定値を有効にします](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-124">[Enable Security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> <span data-ttu-id="1bfa8-125">Azure AD のセキュリティの既定値には、ユーザーと管理者用の MFA が含まれています。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-125">Security defaults in Azure AD include MFA for users and administrators.</span></span>   |
|<span data-ttu-id="1bfa8-126">Microsoft 365 E3 (Azure AD Premium P1 ライセンスを含む)</span><span class="sxs-lookup"><span data-stu-id="1bfa8-126">Microsoft 365 E3 (includes Azure AD Premium P1 licenses)</span></span>     | <span data-ttu-id="1bfa8-127">[一般的な条件付きアクセス ポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)を使用して、次のポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-127">Use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span> <br><span data-ttu-id="1bfa8-128">- [管理者に MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span><span class="sxs-lookup"><span data-stu-id="1bfa8-128">- [Require MFA for administrators](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span></span> <br><span data-ttu-id="1bfa8-129">- [すべてのユーザーに MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="1bfa8-129">- [Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span></span> <br> <span data-ttu-id="1bfa8-130">- [従来の認証をブロックする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span><span class="sxs-lookup"><span data-stu-id="1bfa8-130">- [Block legacy authentication](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span></span>       |
|<span data-ttu-id="1bfa8-131">Microsoft 365 E5 (Azure AD Premium P2 ライセンスを含む)</span><span class="sxs-lookup"><span data-stu-id="1bfa8-131">Microsoft 365 E5 (includes Azure AD Premium P2 licenses)</span></span>     | <span data-ttu-id="1bfa8-132">Azure AD Identity Protection を利用して、次の 2 つのポリシーを作成して、Microsoft の[条件付きアクセスと関連ポリシーの推奨されるセット](../enterprise/identity-access-policies.md)の実装を開始します。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-132">Taking advantage of Azure AD Identity Protection, begin to implement Microsoft's [recommended set of conditional access and related policies](../enterprise/identity-access-policies.md) by creating these two policies:</span></span><br> <span data-ttu-id="1bfa8-133">- [サインインのリスクが中、または高のときに MFA を要求する](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="1bfa8-133">- [Require MFA when sign-in risk is medium or high](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span> <br><span data-ttu-id="1bfa8-134">- [高リスク ユーザーはパスワードを変更する必要がある](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span><span class="sxs-lookup"><span data-stu-id="1bfa8-134">- [High risk users must change password](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span></span>       |
| | |

### <a name="security-defaults"></a><span data-ttu-id="1bfa8-135">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="1bfa8-135">Security defaults</span></span>

<span data-ttu-id="1bfa8-136">セキュリティの既定値は、2019 年 10 月 21 日以降に作成された Microsoft 365 および Office 365 の有料または試用版サブスクリプションの新機能です。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-136">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="1bfa8-137">これらのサブスクリプションではセキュリティの既定値がオンになっており、***すべてのユーザーが Microsoft Authenticator アプリで MFA を使用する必要があります***。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-137">These subscriptions have security defaults turned on, which ***requires all of your users to use MFA with the Microsoft Authenticator app***.</span></span>
 
<span data-ttu-id="1bfa8-138">ユーザーは、スマートフォンから Microsoft Authenticator アプリを使用して MFA に 14 日間登録できます。これは、セキュリティの既定値が有効になった後、初めてサインインしたときから始まります。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-138">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="1bfa8-139">14 日が経過すると、ユーザーは MFA 登録が完了するまでサインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-139">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="1bfa8-140">セキュリティの既定値では、すべての組織が、既定で有効になっているユーザー サインインの基本レベルのセキュリティを確保しています。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-140">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="1bfa8-141">条件付きアクセス ポリシーを使用する MFA を優先して、または個々のアカウントに対して、セキュリティの既定値を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-141">You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.</span></span>

<span data-ttu-id="1bfa8-142">詳細については、こちらの「[セキュリティの既定値の概要](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-142">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="1bfa8-143">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="1bfa8-143">Conditional Access policies</span></span>

<span data-ttu-id="1bfa8-144">条件付きアクセス ポリシーとは、サインインが評価され、アクセスが許可される条件を指定する一連のルールです。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-144">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and access is granted.</span></span> <span data-ttu-id="1bfa8-145">たとえば、次のような条件付きアクセス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-145">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="1bfa8-146">ユーザー アカウント名が Exchange、ユーザー、パスワード、セキュリティ、SharePoint、またはグローバル管理者の役割を割り当てられたユーザーのグループのメンバーである場合、アクセスを許可する前に MFA が必要です。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-146">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="1bfa8-147">このポリシーを使用すると、これらの管理者の役割から割り当てられたり、または割り当てられなかったりした場合に、個別のユーザー アカウントを MFA 用に構成しようとするのではなく、グループ メンバーシップに基づいて MFA を要求することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-147">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="1bfa8-148">条件付きアクセス ポリシーを使用して、Windows 10 を実行しているノート PC などの準拠デバイスからサインインする必要があるなど、より高度な機能を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-148">You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="1bfa8-149">条件付きアクセスには、Microsoft 365 E3 および E5 に含まれている Azure AD Premium P1 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-149">Conditional Access requires Azure AD Premium P1 licenses, which are included with Microsoft 365 E3 and E5.</span></span>

<span data-ttu-id="1bfa8-150">詳細については、こちらの[条件付きアクセスの概要](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-150">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

### <a name="using-these-methods-together"></a><span data-ttu-id="1bfa8-151">これらの方法を組み合わせて使用する</span><span class="sxs-lookup"><span data-stu-id="1bfa8-151">Using these methods together</span></span>

<span data-ttu-id="1bfa8-152">以下の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-152">Keep the following in mind:</span></span>

- <span data-ttu-id="1bfa8-153">条件付きアクセス ポリシーを有効にしている場合、セキュリティの既定値を有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-153">You cannot enable security defaults if you have any Conditional Access policies enabled.</span></span>
- <span data-ttu-id="1bfa8-154">セキュリティの既定値を有効にしている場合は、条件付きアクセス ポリシーを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-154">You cannot enable any Conditional Access policies if you have security defaults enabled.</span></span>

<span data-ttu-id="1bfa8-155">セキュリティの既定値が有効になっている場合、すべての新しいユーザーは MFA 登録と Microsoft Authenticator アプリの使用を求められます。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-155">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app.</span></span> 

<span data-ttu-id="1bfa8-156">この表は、セキュリティの既定値と条件付きアクセス ポリシーで MFA を有効にした結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-156">This table shows the results of enabling MFA with security defaults and Conditional Access policies.</span></span>

| <span data-ttu-id="1bfa8-157">メソッド</span><span class="sxs-lookup"><span data-stu-id="1bfa8-157">Method</span></span> | <span data-ttu-id="1bfa8-158">Enabled</span><span class="sxs-lookup"><span data-stu-id="1bfa8-158">Enabled</span></span> | <span data-ttu-id="1bfa8-159">無効</span><span class="sxs-lookup"><span data-stu-id="1bfa8-159">Disabled</span></span> | <span data-ttu-id="1bfa8-160">追加の認証方法</span><span class="sxs-lookup"><span data-stu-id="1bfa8-160">Additional authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="1bfa8-161">**セキュリティの既定値**</span><span class="sxs-lookup"><span data-stu-id="1bfa8-161">**Security defaults**</span></span>  | <span data-ttu-id="1bfa8-162">条件付きアクセス ポリシーを使用できない</span><span class="sxs-lookup"><span data-stu-id="1bfa8-162">Can’t use Conditional Access policies</span></span> | <span data-ttu-id="1bfa8-163">条件付きアクセス ポリシーを使用できる</span><span class="sxs-lookup"><span data-stu-id="1bfa8-163">Can use Conditional Access policies</span></span> | <span data-ttu-id="1bfa8-164">Microsoft Authenticator アプリ</span><span class="sxs-lookup"><span data-stu-id="1bfa8-164">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="1bfa8-165">**条件付きアクセス ポリシー**</span><span class="sxs-lookup"><span data-stu-id="1bfa8-165">**Conditional Access policies**</span></span> | <span data-ttu-id="1bfa8-166">いずれかが有効になっている場合、セキュリティの既定値を有効にすることはできません</span><span class="sxs-lookup"><span data-stu-id="1bfa8-166">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="1bfa8-167">すべてが無効になっている場合は、セキュリティの既定値を有効にすることができます</span><span class="sxs-lookup"><span data-stu-id="1bfa8-167">If all are disabled, you can enable security defaults</span></span>  | <span data-ttu-id="1bfa8-168">MFA 登録中にユーザーが指定</span><span class="sxs-lookup"><span data-stu-id="1bfa8-168">User specifies during MFA registration</span></span>  |
||||

## <a name="identity-and-device-access-policies"></a><span data-ttu-id="1bfa8-169">ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="1bfa8-169">Identity and device access policies</span></span>

<span data-ttu-id="1bfa8-170">ID とデバイス アクセスの設定とポリシーとは、特定のアクセス要求を許可するかどうか、およびどのような条件下で許可するかを決定する条件付きアクセス、Intune、およびAzure AD Identity Protection ポリシーと組み合わせて推奨される必須機能とその設定です。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-170">Identity and device access settings and policies are recommended prerequisite features and their settings combined with Conditional Access, Intune, and Azure AD Identity Protection policies that determine whether a given access request should be granted and under what conditions.</span></span> <span data-ttu-id="1bfa8-171">この決定は、サインインのユーザーアカウント、使用しているデバイス、ユーザーがアクセスに使用しているアプリ、アクセス要求が行われた場所、および要求のリスクの評価に基づいています。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-171">This determination is based on the user account of the sign-in, the device being used, the app the user is using for access, the location from which the access request is made, and an assessment of the risk of the request.</span></span> <span data-ttu-id="1bfa8-172">この機能により、承認されたユーザーとデバイスのみが重要なリソースにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-172">This capability helps ensure that only approved users and devices can access your critical resources.</span></span>

>[!Note]
><span data-ttu-id="1bfa8-173">Azure AD Identity Protection には、Microsoft 365 E5 に含まれている Azure AD Premium P2 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-173">Azure AD Identity Protection requires Azure AD Premium P2 licenses, which are included with Microsoft 365 E5.</span></span>
>

<span data-ttu-id="1bfa8-174">ID とデバイスのアクセス ポリシーは、3つの層で使用するように定義されています。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-174">Identity and device access policies are defined to be used in three tiers:</span></span> 

- <span data-ttu-id="1bfa8-175">ベースライン保護とは、アプリとデータにアクセスするID とデバイスの最小レベルのセキュリティです。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-175">Baseline protection is a minimum level of security for your identities and devices that access your apps and data.</span></span>
- <span data-ttu-id="1bfa8-176">機密保護は、特定のデータに追加のセキュリティを提供します。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-176">Sensitive protection provides additional security for specific data.</span></span> <span data-ttu-id="1bfa8-177">ID とデバイスは、より高いレベルのセキュリティとデバイスの正常性要件の対象です。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-177">Identities and devices are subject to higher levels of security and device health requirements.</span></span>
- <span data-ttu-id="1bfa8-178">高度に規制または分類されたデータが存在する環境の保護は、通常、高度に分類されている、企業秘密が含まれている、またはデータ規制の対象となる少量のデータ用です。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-178">Protection for environments with highly regulated or classified data is for typically small amounts of data that are highly classified, contain trade secrets, or is subject to data regulations.</span></span> <span data-ttu-id="1bfa8-179">ID とデバイスは、より高いレベルのセキュリティとデバイスの正常性用件の対象です。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-179">Identities and devices are subject to much higher levels of security and device health requirements.</span></span> 

<span data-ttu-id="1bfa8-180">これらの層とそれに対応する構成は、データ、ID、およびデバイス全体で一貫したレベルの保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-180">These tiers and their corresponding configurations provide consistent levels of protection across your data, identities, and devices.</span></span>

<span data-ttu-id="1bfa8-181">マイクロソフトは、Microsoft Teams、Exchange Online、SharePointの特定の設定を含む、組織内のID とデバイスのアクセス ポリシーを構成および展開することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-181">Microsoft highly recommends configuring and rolling out identity and device access policies in your organization, including specific settings for Microsoft Teams, Exchange Online, and SharePoint.</span></span> <span data-ttu-id="1bfa8-182">詳細については、[ID とデバイスのアクセス設定](microsoft-365-policies-configurations.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1bfa8-182">For more information, see [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<!--

## Let your users reset their own passwords

Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff. Users can quickly reset their passwords at any time and from any place. Watch [this video](https://go.microsoft.com/fwlink/?linkid=2128524) to set up SSPR.

## Sign in to SaaS apps with Azure AD

In addition to providing cloud authentication for users, Azure AD can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud. By [integrating your apps into Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for your users to discover the applications they need and sign into them securely.

## Results of deployment of secure sign-ins

After deployment of MFA, your users:

- Are required to use MFA for sign-ins.
- Have completed the MFA registration process and are using MFA for all sign-ins.
- Can use SSPR to reset their own passwords.

- [Plan an Azure AD self-service password reset deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)

--> 

## <a name="admin-technical-resources-for-mfa-and-secure-sign-ins"></a><span data-ttu-id="1bfa8-183">MFA と安全なサインインのための管理技術リソース</span><span class="sxs-lookup"><span data-stu-id="1bfa8-183">Admin technical resources for MFA and secure sign-ins</span></span>

- [<span data-ttu-id="1bfa8-184">MFA for Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1bfa8-184">MFA for Microsoft 365</span></span>](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)
- [<span data-ttu-id="1bfa8-185">Microsoft 365 の ID ロードマップ</span><span class="sxs-lookup"><span data-stu-id="1bfa8-185">Identity roadmap for Microsoft 365</span></span>](identity-roadmap-microsoft-365.md)
- [<span data-ttu-id="1bfa8-186">Azure Academy Azure AD トレーニング ビデオ</span><span class="sxs-lookup"><span data-stu-id="1bfa8-186">Azure Academy Azure AD training videos</span></span>](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [<span data-ttu-id="1bfa8-187">Azure 多要素認証の登録ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="1bfa8-187">Configure the Azure Multi-Factor Authentication registration policy</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)
- [<span data-ttu-id="1bfa8-188">ID とデバイスのアクセス構成</span><span class="sxs-lookup"><span data-stu-id="1bfa8-188">Identity and device access configurations</span></span>](microsoft-365-policies-configurations.md)

