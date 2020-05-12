---
title: 手順 1. MFA を使用してリモート ワーカーのサインイン セキュリティを強化する
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: リモート ワーカーが多要素認証 (MFA) でサインインすることを要求します。
ms.openlocfilehash: f8154f35baaf693bb51c523cfe4c44374437de02
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003581"
---
# <a name="step-1-increase-sign-in-security-for-remote-workers-with-mfa"></a><span data-ttu-id="ef22d-104">手順 1.</span><span class="sxs-lookup"><span data-stu-id="ef22d-104">Step 1.</span></span> <span data-ttu-id="ef22d-105">MFA を使用してリモート ワーカーのサインイン セキュリティを強化する</span><span class="sxs-lookup"><span data-stu-id="ef22d-105">Increase sign-in security for remote workers with MFA</span></span>

<span data-ttu-id="ef22d-106">リモート ワーカーのサインインのセキュリティを強化するには、多要素認証 (MFA) を使用します。</span><span class="sxs-lookup"><span data-stu-id="ef22d-106">To increase the security of sign-ins of your remote workers, use multi-factor authentication (MFA).</span></span> <span data-ttu-id="ef22d-107">MFA では、ユーザーのサインインは、ユーザー アカウントのパスワード以外に追加の検証を受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef22d-107">MFA requires that user sign-ins be subject to an additional verification beyond the user account password.</span></span> <span data-ttu-id="ef22d-108">悪意のあるユーザーがユーザー アカウントのパスワードを決定した場合でも、アクセスが許可される前にスマートフォンに送信されるテキスト メッセージなど、追加の検証に応答できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef22d-108">Even if a malicious user determines a user account password, they must also be able to respond to an additional verification, such as a text message sent to a smartphone before access is granted.</span></span>

<span data-ttu-id="ef22d-109">リモート ワーカー、特に管理者を含むすべてのユーザーに対して、Microsoft は MFA を強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ef22d-109">For all users, including remote workers and especially admins, Microsoft strongly recommends MFA.</span></span>

<span data-ttu-id="ef22d-110">Microsoft 365 プランに基づいてユーザーに MFA の使用を要求する方法は 3 つあります。</span><span class="sxs-lookup"><span data-stu-id="ef22d-110">There are three ways to require your users to use MFA based on your Microsoft 365 plan.</span></span>

|<span data-ttu-id="ef22d-111">プラン</span><span class="sxs-lookup"><span data-stu-id="ef22d-111">Plan</span></span>  |<span data-ttu-id="ef22d-112">推奨事項</span><span class="sxs-lookup"><span data-stu-id="ef22d-112">Recommendation</span></span>  |
|---------|---------|
|<span data-ttu-id="ef22d-113">Microsoft 365 プラン (Azure AD Premium P1 または P2 なし)</span><span class="sxs-lookup"><span data-stu-id="ef22d-113">Microsoft 365 plans (without Azure AD Premium P1 or P2)</span></span>     |<span data-ttu-id="ef22d-114">[Azure AD でセキュリティの既定値を有効にします](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)。</span><span class="sxs-lookup"><span data-stu-id="ef22d-114">[Enable Security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span> <span data-ttu-id="ef22d-115">Azure AD のセキュリティの既定値には、ユーザーと管理者用の MFA が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ef22d-115">Security defaults in Azure AD include MFA for users and administrators.</span></span>   |
|<span data-ttu-id="ef22d-116">Microsoft 365 E3 (Azure AD Premium P1 搭載)</span><span class="sxs-lookup"><span data-stu-id="ef22d-116">Microsoft 365 E3 (with Azure AD Premium P1)</span></span>     | <span data-ttu-id="ef22d-117">[一般的な条件付きアクセス ポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common)を使用して、次のポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="ef22d-117">Use [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) to configure the following policies:</span></span> <br><span data-ttu-id="ef22d-118">- [管理者に MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span><span class="sxs-lookup"><span data-stu-id="ef22d-118">- [Require MFA for administrators](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)</span></span> <br><span data-ttu-id="ef22d-119">- [すべてのユーザーに MFA を要求する](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span><span class="sxs-lookup"><span data-stu-id="ef22d-119">- [Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)</span></span> <br> <span data-ttu-id="ef22d-120">- [従来の認証をブロックする](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span><span class="sxs-lookup"><span data-stu-id="ef22d-120">- [Block legacy authentication](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)</span></span>       |
|<span data-ttu-id="ef22d-121">Microsoft 365 E5 (Azure AD Premium P2 搭載)</span><span class="sxs-lookup"><span data-stu-id="ef22d-121">Microsoft 365 E5 (with Azure AD Premium P2)</span></span>     | <span data-ttu-id="ef22d-122">Azure AD Identity Protection を利用して、次の 2 つのポリシーを作成して、Microsoft の[条件付きアクセスと関連ポリシーの推奨されるセット](../enterprise/identity-access-policies.md)の実装を開始します。</span><span class="sxs-lookup"><span data-stu-id="ef22d-122">Taking advantage of Azure AD Identity Protection, begin to implement Microsoft's [recommended set of conditional access and related policies](../enterprise/identity-access-policies.md) by creating these two policies:</span></span><br> <span data-ttu-id="ef22d-123">- [サインインのリスクが中、または高のときに MFA を要求する](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span><span class="sxs-lookup"><span data-stu-id="ef22d-123">- [Require MFA when sign-in risk is medium or high](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk)</span></span> <br><span data-ttu-id="ef22d-124">- [先進認証をサポートしないクライアントはブロックする](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)</span><span class="sxs-lookup"><span data-stu-id="ef22d-124">- [Block clients that don't support modern authentication](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)</span></span><br><span data-ttu-id="ef22d-125">- [高リスク ユーザーはパスワードを変更する必要がある](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span><span class="sxs-lookup"><span data-stu-id="ef22d-125">- [High risk users must change password](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)</span></span>       |
| | |

## <a name="security-defaults"></a><span data-ttu-id="ef22d-126">セキュリティの既定値</span><span class="sxs-lookup"><span data-stu-id="ef22d-126">Security defaults</span></span>

<span data-ttu-id="ef22d-127">セキュリティの既定値は、2019 年 10 月 21 日以降に作成された Microsoft 365 および Office 365 の有料または試用版サブスクリプションの新機能です。</span><span class="sxs-lookup"><span data-stu-id="ef22d-127">Security defaults is a new feature for Microsoft 365 and Office 365 paid or trial subscriptions created after October 21, 2019.</span></span> <span data-ttu-id="ef22d-128">これらのサブスクリプションではセキュリティの既定値がオンになっており、***すべてのユーザーが Microsoft Authenticator アプリで MFA を使用する必要があります***。</span><span class="sxs-lookup"><span data-stu-id="ef22d-128">These subscriptions have security defaults turned on, which ***requires all of your users to use MFA with the Microsoft Authenticator app***.</span></span>
 
<span data-ttu-id="ef22d-129">ユーザーは、スマートフォンから Microsoft Authenticator アプリを使用して MFA に 14 日間登録できます。これは、セキュリティの既定値が有効になった後、初めてサインインしたときから始まります。</span><span class="sxs-lookup"><span data-stu-id="ef22d-129">Users have 14 days to register for MFA with the Microsoft Authenticator app from their smart phones, which begins from the first time they sign in after security defaults has been enabled.</span></span> <span data-ttu-id="ef22d-130">14 日が経過すると、ユーザーは MFA 登録が完了するまでサインインできなくなります。</span><span class="sxs-lookup"><span data-stu-id="ef22d-130">After 14 days have passed, the user won't be able to sign in until MFA registration is completed.</span></span>

<span data-ttu-id="ef22d-131">セキュリティの既定値では、すべての組織が、既定で有効になっているユーザー サインインの基本レベルのセキュリティを確保しています。</span><span class="sxs-lookup"><span data-stu-id="ef22d-131">Security defaults ensure that all organizations have a basic level of security for user sign-in that is enabled by default.</span></span> <span data-ttu-id="ef22d-132">条件付きアクセス ポリシーを使用する MFA を優先して、または個々のアカウントに対して、セキュリティの既定値を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ef22d-132">You can disable security defaults in favor of MFA with Conditional Access policies or for individual accounts.</span></span>

<span data-ttu-id="ef22d-133">詳細については、こちらの「[セキュリティの既定値の概要](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ef22d-133">For more information, see this [overview of security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults).</span></span>

## <a name="conditional-access-policies"></a><span data-ttu-id="ef22d-134">条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="ef22d-134">Conditional Access policies</span></span>

<span data-ttu-id="ef22d-135">条件付きアクセス ポリシーは、サインインが評価および許可される条件を指定する一連のルールです。</span><span class="sxs-lookup"><span data-stu-id="ef22d-135">Conditional Access policies are a set of rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="ef22d-136">たとえば、次のような条件付きアクセス ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ef22d-136">For example, you can create a Conditional Access policy that states:</span></span>

- <span data-ttu-id="ef22d-137">ユーザー アカウント名が Exchange、ユーザー、パスワード、セキュリティ、SharePoint、またはグローバル管理者のユーザーの場合、アクセスを許可する前に MFA が必要です。</span><span class="sxs-lookup"><span data-stu-id="ef22d-137">If the user account name is for a user that is an Exchange, user, password, security, SharePoint, or global administrator, require MFA before allowing access.</span></span>

<span data-ttu-id="ef22d-138">このポリシーは、これらの管理者の役割に追加または削除されたときに、MFA の個々のユーザー アカウントを忘れずに構成するよりも簡単です。</span><span class="sxs-lookup"><span data-stu-id="ef22d-138">This policy is easier than trying to remember to configure individual user accounts for MFA when they are added to or removed from these administrator roles.</span></span>

<span data-ttu-id="ef22d-139">条件付きアクセス ポリシーを使用して、Windows 10 を実行しているノート PC などの準拠デバイスからサインインする必要があるなど、より高度な機能を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ef22d-139">You can also use Conditional Access policies for more advanced capabilities, such as requiring that the sign-in is done from a compliant device, such as your laptop running Windows 10.</span></span>

<span data-ttu-id="ef22d-140">条件付きアクセスには、Microsoft 365 E3 および E5 に含まれている Azure AD Premium P1 が必要です。</span><span class="sxs-lookup"><span data-stu-id="ef22d-140">Conditional Access requires Azure AD Premium P1, which is included with Microsoft 365 E3 and E5.</span></span>

<span data-ttu-id="ef22d-141">詳細については、「[条件付きアクセスの概要](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ef22d-141">For more information, see this [overview of Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span>

## <a name="azure-ad-identity-protection-policies"></a><span data-ttu-id="ef22d-142">Azure AD Identity Protection ポリシー</span><span class="sxs-lookup"><span data-stu-id="ef22d-142">Azure AD Identity Protection policies</span></span>

<span data-ttu-id="ef22d-143">Azure AD Identity Protection ポリシーは、サインインが評価および許可される条件を指定するルールです。</span><span class="sxs-lookup"><span data-stu-id="ef22d-143">Azure AD Identity Protection policies are rules that specify the conditions under which sign-ins are evaluated and allowed.</span></span> <span data-ttu-id="ef22d-144">たとえば、次のような Azure AD Identity Protection ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ef22d-144">For example, you can create an Azure AD Identity Protection policy that states:</span></span>

- <span data-ttu-id="ef22d-145">サインインのリスクが中または高であると判断された場合、ユーザーは MFA を使用してサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef22d-145">If the risk of the sign-in is determined to be medium or high risk, the user must use MFA to sign in.</span></span>

<span data-ttu-id="ef22d-146">Azure AD Identity Protection には、Microsoft 365 E5 に含まれている Azure AD Premium P2 が必要です。</span><span class="sxs-lookup"><span data-stu-id="ef22d-146">Azure AD Identity Protection requires Azure AD Premium P2, which is included with Microsoft 365 E5.</span></span>

<span data-ttu-id="ef22d-147">詳細については、この「[Azure AD Identity Protection の概要](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ef22d-147">For more information, see this [overview of Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

## <a name="using-these-methods-together"></a><span data-ttu-id="ef22d-148">これらの方法を一緒に使用する</span><span class="sxs-lookup"><span data-stu-id="ef22d-148">Using these methods together</span></span>

<span data-ttu-id="ef22d-149">以下の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ef22d-149">Keep in mind the following:</span></span>

- <span data-ttu-id="ef22d-150">条件付きアクセス ポリシーを有効にしている場合、セキュリティの既定値を有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ef22d-150">You cannot enable security defaults if you have any Conditional Access policies enabled.</span></span>
- <span data-ttu-id="ef22d-151">セキュリティの既定値を有効にしている場合は、条件付きアクセス ポリシーを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ef22d-151">You cannot enable any Conditional Access policies if you have security defaults enabled.</span></span>

<span data-ttu-id="ef22d-152">セキュリティの既定値が有効になっている場合、すべての新しいユーザーは MFA 登録と Microsoft Authenticator アプリの使用を求められます。</span><span class="sxs-lookup"><span data-stu-id="ef22d-152">If security defaults are enabled, all new users are prompted for MFA registration and the use of the Microsoft Authenticator app.</span></span> 

<span data-ttu-id="ef22d-153">この表は、セキュリティの既定値、条件付きアクセス ポリシー、およびユーザーごとのアカウント設定で MFA を有効にした結果を示しています。</span><span class="sxs-lookup"><span data-stu-id="ef22d-153">This table shows the results of enabling MFA with security defaults, Conditional Access policies, and per-user account settings.</span></span>

|| <span data-ttu-id="ef22d-154">Enabled</span><span class="sxs-lookup"><span data-stu-id="ef22d-154">Enabled</span></span> | <span data-ttu-id="ef22d-155">無効</span><span class="sxs-lookup"><span data-stu-id="ef22d-155">Disabled</span></span> | <span data-ttu-id="ef22d-156">第 2 の認証方法</span><span class="sxs-lookup"><span data-stu-id="ef22d-156">Secondary authentication method</span></span> |
|:-------|:-----|:-------|:-------|
| <span data-ttu-id="ef22d-157">**セキュリティの既定値**</span><span class="sxs-lookup"><span data-stu-id="ef22d-157">**Security defaults**</span></span>  | <span data-ttu-id="ef22d-158">条件付きアクセス ポリシーを使用できない</span><span class="sxs-lookup"><span data-stu-id="ef22d-158">Can’t use Conditional Access policies</span></span> | <span data-ttu-id="ef22d-159">条件付きアクセス ポリシーを使用できる</span><span class="sxs-lookup"><span data-stu-id="ef22d-159">Can use Conditional Access policies</span></span> | <span data-ttu-id="ef22d-160">Microsoft Authenticator アプリ</span><span class="sxs-lookup"><span data-stu-id="ef22d-160">Microsoft Authenticator app</span></span> |
| <span data-ttu-id="ef22d-161">**条件付きアクセス ポリシー**</span><span class="sxs-lookup"><span data-stu-id="ef22d-161">**Conditional Access policies**</span></span> | <span data-ttu-id="ef22d-162">いずれかが有効になっている場合、セキュリティの既定値を有効にすることはできません</span><span class="sxs-lookup"><span data-stu-id="ef22d-162">If any are enabled, you can’t enable security defaults</span></span> | <span data-ttu-id="ef22d-163">すべてが有効になっていない場合は、セキュリティの既定値を有効にできます</span><span class="sxs-lookup"><span data-stu-id="ef22d-163">If all are not enabled, you can enable security defaults</span></span>  | <span data-ttu-id="ef22d-164">MFA への登録時にユーザー指定</span><span class="sxs-lookup"><span data-stu-id="ef22d-164">User-specified during MFA registration</span></span>  |
||||

## <a name="admin-training-and-technical-resources-for-mfa-and-identity"></a><span data-ttu-id="ef22d-165">MFA と ID の管理トレーニングと技術リソース</span><span class="sxs-lookup"><span data-stu-id="ef22d-165">Admin training and technical resources for MFA and identity</span></span>

- [<span data-ttu-id="ef22d-166">Microsoft 365 の MFA 計画</span><span class="sxs-lookup"><span data-stu-id="ef22d-166">MFA planning for Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-plan)
- [<span data-ttu-id="ef22d-167">Azure AD がリモート作業を可能にするのに役立つ 5 つの方法</span><span class="sxs-lookup"><span data-stu-id="ef22d-167">Top 5 ways your Azure AD can help you enable remote work</span></span>](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/top-5-ways-your-azure-ad-can-help-you-enable-remote-work/ba-p/1144691)
- [<span data-ttu-id="ef22d-168">Microsoft 365 の ID インフラストラクチャを計画および展開する</span><span class="sxs-lookup"><span data-stu-id="ef22d-168">Plan and deploy your Microsoft 365 identity infrastructure</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure?view=o365-worldwide#plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure)
- [<span data-ttu-id="ef22d-169">Azure Academy Azure AD トレーニング ビデオ</span><span class="sxs-lookup"><span data-stu-id="ef22d-169">Azure Academy Azure AD training videos</span></span>](https://www.youtube.com/watch?v=pN8o0owHfI0&list=PL-V4YVm6AmwUFpC3rXr2i2piRQ708q_ia)
- [<span data-ttu-id="ef22d-170">Azure 多要素認証の登録ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="ef22d-170">Configure the Azure Multi-Factor Authentication registration policy</span></span>](https://docs.microsoft.com/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy)

## <a name="results-of-step-1"></a><span data-ttu-id="ef22d-171">手順 1 の結果</span><span class="sxs-lookup"><span data-stu-id="ef22d-171">Results of Step 1</span></span>

<span data-ttu-id="ef22d-172">MFA の展開後、ユーザーは次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="ef22d-172">After deployment of MFA, your users:</span></span>

- <span data-ttu-id="ef22d-173">サインインに MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef22d-173">Are required to use MFA for sign-ins.</span></span>
- <span data-ttu-id="ef22d-174">MFA 登録プロセスを完了し、すべてのサインインに MFA を使用します。</span><span class="sxs-lookup"><span data-stu-id="ef22d-174">Have completed the MFA registration process and is using MFA for all sign-ins.</span></span>

## <a name="next-step"></a><span data-ttu-id="ef22d-175">次の手順</span><span class="sxs-lookup"><span data-stu-id="ef22d-175">Next step</span></span>

<span data-ttu-id="ef22d-176">[手順 2](empower-people-to-work-remotely-remote-access.md) に進み、オンプレミスのアプリとサービスへのリモート アクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ef22d-176">Continue with [Step 2](empower-people-to-work-remotely-remote-access.md) to provide remote access to on-premises apps and services.</span></span>
