---
title: 手順 1. MFA を使用してリモート ワーカーのサインイン セキュリティを強化する
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: リモート ワーカーが多要素認証 (MFA) でサインインすることを要求します。
ms.openlocfilehash: aa9b122ca18c4d8a8123914ee2d29d41c9ec789e
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681458"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a><span data-ttu-id="4e1eb-104">手順 1.</span><span class="sxs-lookup"><span data-stu-id="4e1eb-104">Step 1.</span></span> <span data-ttu-id="4e1eb-105">MFA を使用してリモート ワーカーのサインイン セキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="4e1eb-105">Increase sign-in security for remote workers with MFA</span></span>

<span data-ttu-id="4e1eb-106">リモート ワーカーのサインインのセキュリティを強化するには、多要素認証 (MFA) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-106">To increase the security of sign-ins of your remote workers, use multi-factor authentication (MFA).</span></span> <span data-ttu-id="4e1eb-107">MFA では、ユーザーのサインインは、ユーザー アカウントのパスワード以外に追加の検証を受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-107">MFA requires that user sign-ins be subject to an additional verification beyond the user account password.</span></span> <span data-ttu-id="4e1eb-108">悪意のあるユーザーがユーザー アカウントのパスワードを決定した場合でも、アクセスが許可される前にスマートフォンに送信されるテキスト メッセージなど、追加の検証に応答できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-108">Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.</span></span>

![正しいパスワードと追加認証によりサインインが成功する](../media/empower-people-to-work-remotely/remote-workers-mfa.png)

<span data-ttu-id="4e1eb-110">リモート ワーカー、特に管理者を含むすべてのユーザーに対して、Microsoft は MFA を強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-110">For all users, including remote workers and especially admins, Microsoft strongly recommends MFA.</span></span>

<span data-ttu-id="4e1eb-111">Microsoft 365 プランに基づいてユーザーに MFA の使用を要求する方法は 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-111">There are three ways to require your users to use MFA based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="4e1eb-112">プラン</span><span class="sxs-lookup"><span data-stu-id="4e1eb-112">Plan</span></span>  |<span data-ttu-id="4e1eb-113">推奨事項</span><span class="sxs-lookup"><span data-stu-id="4e1eb-113">Recommendation</span></span>  |
|---------|---------|
|<span data-ttu-id="4e1eb-114">Microsoft 365 のすべてのプラン (Azure AD Premium P1 または P2 ライセンスなし)</span><span class="sxs-lookup"><span data-stu-id="4e1eb-114">All Microsoft 365 plans (without Azure AD Premium P1 or P2 licenses)</span></span>     |<span data-ttu-id="4e1eb-115">[Azure AD でセキュリティの既定値を有効にします](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-115">[Enable Security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> <span data-ttu-id="4e1eb-116">Azure AD のセキュリティの既定値には、ユーザーと管理者用の MFA が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-116">Security defaults in Azure AD include MFA for users and administrators.</span></span>   |
|<span data-ttu-id="4e1eb-117">Microsoft 365 E3 (Azure AD Premium P1 ライセンスを含む)</span><span class="sxs-lookup"><span data-stu-id="4e1eb-117">Microsoft 365 E3 (includes Azure AD Premium P1 licenses)</span></span>     | <span data-ttu-id="4e1eb-118">[一般的な条件付きアクセス ポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)を使用して、次のポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-118">Use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span> <br><span data-ttu-id="4e1eb-119">- [管理者に MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span><span class="sxs-lookup"><span data-stu-id="4e1eb-119">- [Require MFA for administrators](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span></span> <br><span data-ttu-id="4e1eb-120">- [すべてのユーザーに MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="4e1eb-120">- [Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span></span> <br> <span data-ttu-id="4e1eb-121">- [従来の認証をブロックする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span><span class="sxs-lookup"><span data-stu-id="4e1eb-121">- [Block legacy authentication](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span></span>       |
|<span data-ttu-id="4e1eb-122">Microsoft 365 E5 (Azure AD Premium P2 ライセンスを含む)</span><span class="sxs-lookup"><span data-stu-id="4e1eb-122">Microsoft 365 E5 (includes Azure AD Premium P2 licenses)</span></span>     | <span data-ttu-id="4e1eb-123">Azure AD Identity Protection を活用して、次のポリシーを作成することで、Microsoft の[条件付きアクセスと関連ポリシーの推奨セット](../security/office-365-security/identity-access-policies.md)の実装を開始します。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-123">Taking advantage of Azure AD Identity Protection, begin to implement Microsoft's [recommended set of Conditional Access and related policies](../security/office-365-security/identity-access-policies.md) by creating these policies:</span></span><br> <span data-ttu-id="4e1eb-124">- [サインインのリスクが中、または高のときに MFA を要求する](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="4e1eb-124">- [Require MFA when sign-in risk is medium or high](../security/office-365-security/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span> <br><span data-ttu-id="4e1eb-125">- [先進認証をサポートしないクライアントはブロックする](../security/office-365-security/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)</span><span class="sxs-lookup"><span data-stu-id="4e1eb-125">- [Block clients that don't support modern authentication](../security/office-365-security/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)</span></span><br><span data-ttu-id="4e1eb-126">- [高リスク ユーザーはパスワードを変更する必要がある](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)</span><span class="sxs-lookup"><span data-stu-id="4e1eb-126">- [High risk users must change password](../security/office-365-security/identity-access-policies.md#high-risk-users-must-change-password)</span></span>       |
| | |

## <a name="security-defaults"></a><span data-ttu-id="4e1eb-127">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="4e1eb-127">Security defaults</span></span>

<span data-ttu-id="4e1eb-128">セキュリティの既定値は、2019 年 10 月 21 日以降に作成された Microsoft 365 および Office 365 の有料または試用版サブスクリプションの新機能です。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-128">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="4e1eb-129">これらのサブスクリプションではセキュリティの既定値がオンになっており、\***すべてのユーザーが Microsoft Authenticator アプリで MFA を使用する必要があります**_。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-129">These subscriptions have security defaults turned on, which \***requires all of your users to use MFA with the Microsoft Authenticator app**_.</span></span>
 
<span data-ttu-id="4e1eb-130">ユーザーは、スマートフォンから Microsoft Authenticator アプリを使用して MFA に 14 日間登録できます。これは、セキュリティの既定値が有効になった後、初めてサインインしたときから始まります。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-130">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="4e1eb-131">14 日が経過すると、ユーザーは MFA 登録が完了するまでサインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-131">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="4e1eb-132">セキュリティの既定値では、すべての組織が、既定で有効になっているユーザー サインインの基本レベルのセキュリティを確保しています。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-132">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="4e1eb-133">条件付きアクセス ポリシーを使用する MFA を優先して、または個々のアカウントに対して、セキュリティの既定値を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-133">You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.</span></span>

<span data-ttu-id="4e1eb-134">詳細については、こちらの「[セキュリティの既定値の概要](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-134">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

## <a name="conditional-access-policies"></a><span data-ttu-id="4e1eb-135">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="4e1eb-135">Conditional Access policies</span></span>

<span data-ttu-id="4e1eb-136">条件付きアクセス ポリシーは、サインインが評価および許可される条件を指定する一連のルールです。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-136">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="4e1eb-137">たとえば、次のような条件付きアクセス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-137">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="4e1eb-138">ユーザー アカウント名が Exchange、ユーザー、パスワード、セキュリティ、SharePoint、またはグローバル管理者の役割を割り当てられたユーザーのグループのメンバーである場合、アクセスを許可する前に MFA が必要です。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-138">If the user account name is a member of a group for users that are assigned the Exchange, user, password, security, SharePoint, or global administrator roles, require MFA before allowing access.</span></span>

<span data-ttu-id="4e1eb-139">このポリシーを使用すると、これらの管理者の役割から割り当てられたり、または割り当てられなかったりした場合に、個別のユーザー アカウントを MFA 用に構成しようとするのではなく、グループ メンバーシップに基づいて MFA を要求することができるようになります。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-139">This policy allows you to require MFA based on group membership, rather than trying to configure individual user accounts for MFA when they are assigned or unassigned from these administrator roles.</span></span>

<span data-ttu-id="4e1eb-140">条件付きアクセス ポリシーを使用して、Windows 10 を実行しているノート PC などの準拠デバイスからサインインする必要があるなど、より高度な機能を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-140">You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="4e1eb-141">条件付きアクセスには、Microsoft 365 E3 および E5 に含まれている Azure AD Premium P1 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-141">Conditional Access requires Azure AD Premium P1 licenses, which are included with Microsoft 365 E3 and E5.</span></span>

<span data-ttu-id="4e1eb-142">詳細については、こちらの「[条件付きアクセスの概要](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-142">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

## <a name="azure-ad-identity-protection-support"></a><span data-ttu-id="4e1eb-143">Azure AD Identity Protection のサポート</span><span class="sxs-lookup"><span data-stu-id="4e1eb-143">Azure AD Identity Protection support</span></span>

<span data-ttu-id="4e1eb-144">Azure AD Identity Protection を使用すると、次のような追加の条件付きアクセス ポリシーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-144">With Azure AD Identity Protection, you can create an additional Conditional Access policy that states:</span></span>

- <span data-ttu-id="4e1eb-145">サインインのリスクが中または高であると判断された場合、MFA が必要です。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-145">If the risk of the sign-in is determined to be medium or high, require MFA.</span></span>

<span data-ttu-id="4e1eb-146">Azure AD Identity Protection には、Microsoft 365 E5 に含まれている Azure AD Premium P2 ライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-146">Azure AD Identity Protection requires Azure AD Premium P2 licenses, which are included with Microsoft 365 E5.</span></span>

<span data-ttu-id="4e1eb-147">詳細については、「[Risk-based Conditional Access (リスク ベースの条件付きアクセス)](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-147">For more information, see [Risk-based Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk#require-mfa-medium-or-high-sign-in-risk-users).</span></span>

<span data-ttu-id="4e1eb-148">Azure AD Identity Protection を使用すると、ユーザーに MFA への登録を要求するポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-148">With Azure AD Identity Protection, you can also create a policy to require your users to register for MFA.</span></span> <span data-ttu-id="4e1eb-149">詳細については、「[Azure 多要素認証の登録ポリシーの構成](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-149">For more information, see [Configure the Azure Multi-Factor Authentication registration policy](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)</span></span>


## <a name="using-these-methods-together"></a><span data-ttu-id="4e1eb-150">これらの方法を組み合わせて使用する</span><span class="sxs-lookup"><span data-stu-id="4e1eb-150">Using these methods together</span></span>

<span data-ttu-id="4e1eb-151">以下の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-151">Keep the following in mind:</span></span>

- <span data-ttu-id="4e1eb-152">条件付きアクセス ポリシーを有効にしている場合、セキュリティの既定値を有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-152">You cannot enable security defaults if you have any Conditional Access policies enabled.</span></span>
- <span data-ttu-id="4e1eb-153">セキュリティの既定値を有効にしている場合は、条件付きアクセス ポリシーを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-153">You cannot enable any Conditional Access policies if you have security defaults enabled.</span></span>

<span data-ttu-id="4e1eb-154">セキュリティの既定値が有効になっている場合、すべての新しいユーザーは MFA 登録と Microsoft Authenticator アプリの使用を求められます。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-154">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app.</span></span> 

<span data-ttu-id="4e1eb-155">この表は、セキュリティの既定値と条件付きアクセス ポリシーで MFA を有効にした結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-155">This table shows the results of enabling MFA with security defaults and Conditional Access policies.</span></span>

| <span data-ttu-id="4e1eb-156">メソッド</span><span class="sxs-lookup"><span data-stu-id="4e1eb-156">Method</span></span> | <span data-ttu-id="4e1eb-157">Enabled</span><span class="sxs-lookup"><span data-stu-id="4e1eb-157">Enabled</span></span> | <span data-ttu-id="4e1eb-158">無効</span><span class="sxs-lookup"><span data-stu-id="4e1eb-158">Disabled</span></span> | <span data-ttu-id="4e1eb-159">追加の認証方法</span><span class="sxs-lookup"><span data-stu-id="4e1eb-159">Additional authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="4e1eb-160">_*セキュリティの既定値*\*</span><span class="sxs-lookup"><span data-stu-id="4e1eb-160">_*Security defaults*\*</span></span>  | <span data-ttu-id="4e1eb-161">条件付きアクセス ポリシーを使用できない</span><span class="sxs-lookup"><span data-stu-id="4e1eb-161">Can’t use Conditional Access policies</span></span> | <span data-ttu-id="4e1eb-162">条件付きアクセス ポリシーを使用できる</span><span class="sxs-lookup"><span data-stu-id="4e1eb-162">Can use Conditional Access policies</span></span> | <span data-ttu-id="4e1eb-163">Microsoft Authenticator アプリ</span><span class="sxs-lookup"><span data-stu-id="4e1eb-163">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="4e1eb-164">**条件付きアクセス ポリシー**</span><span class="sxs-lookup"><span data-stu-id="4e1eb-164">**Conditional Access policies**</span></span> | <span data-ttu-id="4e1eb-165">いずれかが有効になっている場合、セキュリティの既定値を有効にすることはできません</span><span class="sxs-lookup"><span data-stu-id="4e1eb-165">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="4e1eb-166">すべてが無効になっている場合は、セキュリティの既定値を有効にすることができます</span><span class="sxs-lookup"><span data-stu-id="4e1eb-166">If all are disabled, you can enable security defaults</span></span>  | <span data-ttu-id="4e1eb-167">MFA 登録中にユーザーが指定</span><span class="sxs-lookup"><span data-stu-id="4e1eb-167">User specifies during MFA registration</span></span>  |
||||

## <a name="let-your-users-reset-their-own-passwords"></a><span data-ttu-id="4e1eb-168">ユーザーが自分でパスワードをリセットできるようにする</span><span class="sxs-lookup"><span data-stu-id="4e1eb-168">Let your users reset their own passwords</span></span>

<span data-ttu-id="4e1eb-169">セルフサービスによるパスワードのリセット (SSPR) は、IT スタッフに影響を与えることなく、ユーザーが自分のパスワードをリセットできるようにします。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-169">Self-Service Password Reset (SSPR) enables users to reset their own passwords without impacting IT staff.</span></span> <span data-ttu-id="4e1eb-170">ユーザーは、いつでもどこからでも自分のパスワードをすばやくリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-170">Users can quickly reset their passwords at any time and from any place.</span></span> <span data-ttu-id="4e1eb-171">詳細については、「[Azure AD のセルフサービスによるパスワードのリセットの展開を計画する](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-171">For more information, see [Plan an Azure AD self-service password reset deployment](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

## <a name="sign-in-to-saas-apps-with-azure-ad"></a><span data-ttu-id="4e1eb-172">Azure AD で SaaS アプリにサインインする</span><span class="sxs-lookup"><span data-stu-id="4e1eb-172">Sign in to SaaS apps with Azure AD</span></span>

<span data-ttu-id="4e1eb-173">クラウド認証をユーザーに提供するだけでなく、Azure AD はすべてのアプリをオンプレミスにしているか、Microsoft のクラウドにあるか、または別のクラウドにあるかどうかに関係なく、全てのアプリを保護する中心的な方法にもなります。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-173">In addition to providing cloud authentication for users, Azure AD can also be your central way to secure all your apps, whether they’re on-premises, in Microsoft’s cloud, or in another cloud.</span></span> <span data-ttu-id="4e1eb-174">[アプリケーションを Azure AD - Microsoft Azure Actuve Directoryに統合する](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration)と、リモートワーカーが必要なアプリケーションを見つけて安全にサインインするのが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-174">By [integrating your apps into Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-an-application-integration), you can make it easy for remote workers to discover the applications they need and sign into them securely.</span></span>

## <a name="admin-technical-resources-for-mfa-and-identity"></a><span data-ttu-id="4e1eb-175">MFA と ID のための管理技術リソース</span><span class="sxs-lookup"><span data-stu-id="4e1eb-175">Admin technical resources for MFA and identity</span></span>

- [<span data-ttu-id="4e1eb-176">Azure AD がリモート作業を可能にするのに役立つ 5 つの方法</span><span class="sxs-lookup"><span data-stu-id="4e1eb-176">Top 5 ways your Azure AD can help you enable remote work</span></span>](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [<span data-ttu-id="4e1eb-177">Microsoft 365 の ID ロードマップ</span><span class="sxs-lookup"><span data-stu-id="4e1eb-177">Identity roadmap for Microsoft 365</span></span>](../enterprise/identity-roadmap-microsoft-365.md)
- [<span data-ttu-id="4e1eb-178">Azure Academy Azure AD トレーニング ビデオ</span><span class="sxs-lookup"><span data-stu-id="4e1eb-178">Azure Academy Azure AD training videos</span></span>](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)

## <a name="results-of-step-1"></a><span data-ttu-id="4e1eb-179">手順 1 の結果</span><span class="sxs-lookup"><span data-stu-id="4e1eb-179">Results of Step 1</span></span>

<span data-ttu-id="4e1eb-180">MFA の展開後、ユーザーは次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-180">After deployment of MFA, your users:</span></span>

- <span data-ttu-id="4e1eb-181">サインインに MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-181">Are required to use MFA for sign-ins.</span></span>
- <span data-ttu-id="4e1eb-182">MFA 登録プロセスを完了し、すべてのサインインに MFA を使用します。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-182">Have completed the MFA registration process and are using MFA for all sign-ins.</span></span>
- <span data-ttu-id="4e1eb-183">SSPR を使用して自分のパスワードをリセットすることができます。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-183">Can use SSPR to reset their own passwords.</span></span>

## <a name="next-step"></a><span data-ttu-id="4e1eb-184">次のステップ</span><span class="sxs-lookup"><span data-stu-id="4e1eb-184">Next step</span></span>

<span data-ttu-id="4e1eb-185">[![手順 2: オンプレミスのアプリとサービスへのリモート アクセスを提供する](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)</span><span class="sxs-lookup"><span data-stu-id="4e1eb-185">[![Step 2: Provide remote access to on-premises apps and services](../media/empower-people-to-work-remotely/remote-workers-step-grid-2.png)](empower-people-to-work-remotely-remote-access.md)</span></span>

<span data-ttu-id="4e1eb-186">[手順 2](empower-people-to-work-remotely-remote-access.md) に進み、オンプレミスのアプリとサービスへのリモート アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="4e1eb-186">Continue with [Step 2](empower-people-to-work-remotely-remote-access.md) to provide remote access to on-premises apps and services.</span></span>
