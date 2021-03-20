---
title: Microsoft 365 クライアントとサービス アプリのサポート
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: この記事では、Microsoft 365 クライアントとサービス アプリのサポートに関する詳細を確認します。
ms.openlocfilehash: e380efffc1bf29cbd4d3a77d32e4d1f8b2994da3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905010"
---
# <a name="microsoft-365-client-and-services-app-support"></a><span data-ttu-id="89716-103">Microsoft 365 クライアントとサービス アプリのサポート</span><span class="sxs-lookup"><span data-stu-id="89716-103">Microsoft 365 client and services app support</span></span>

<span data-ttu-id="89716-104">Microsoft は、お客様のデータを安全に保つために、幅広いセキュリティ、認証、コンプライアンス機能をサポートし、IT 管理者はユーザーのために Microsoft 365 管理センター内のポリシーをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="89716-104">Microsoft supports a wide range of security, authentication, and compliance features to keep customer data safe and allows IT administrators to customize policies within the Microsoft 365 admin center for their users.</span></span> <span data-ttu-id="89716-105">次の機能は、Microsoft 365 サブスクリプションに応じて構成できる多数のエンタープライズ機能のサブセットにすら異なる機能です。</span><span class="sxs-lookup"><span data-stu-id="89716-105">The following features are just a subset of the many enterprise features that you can configure depending on your Microsoft 365 subscription.</span></span>

## <a name="client-and-service-support"></a><span data-ttu-id="89716-106">クライアントとサービスのサポート</span><span class="sxs-lookup"><span data-stu-id="89716-106">Client and service support</span></span>

### <a name="continuous-access-evaluation-preview"></a><span data-ttu-id="89716-107">継続的アクセス評価 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="89716-107">Continuous access evaluation (preview)</span></span>

<span data-ttu-id="89716-108">継続的なアクセス評価は、Exchange Online、SharePoint Online、Teams などのサービスが Azure Active Directory の重要なイベントをサブスクライブして、それらのイベントをほぼリアルタイムで評価および適用できる状態にすることで実装されます。</span><span class="sxs-lookup"><span data-stu-id="89716-108">Continuous access evaluation is implemented by enabling services, like Exchange Online, SharePoint Online, and Teams, to subscribe to critical events in Azure Active Directory so that those events can be evaluated and enforced near real time.</span></span> <span data-ttu-id="89716-109">重要なイベント評価は条件付きアクセス ポリシーに依存しないので、どのテナントでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="89716-109">Critical event evaluation does not rely on Conditional Access policies so is available in any tenant.</span></span>

<span data-ttu-id="89716-110">現在、次のイベントが評価されています。</span><span class="sxs-lookup"><span data-stu-id="89716-110">The following events are currently evaluated:</span></span>

- <span data-ttu-id="89716-111">ユーザー アカウントが削除または無効になっている</span><span class="sxs-lookup"><span data-stu-id="89716-111">A user account is deleted or disabled</span></span>
- <span data-ttu-id="89716-112">ユーザーのパスワードが変更またはリセットされる</span><span class="sxs-lookup"><span data-stu-id="89716-112">The password for a user is changed or reset</span></span>
- <span data-ttu-id="89716-113">ユーザーに対して多要素認証が有効になっている</span><span class="sxs-lookup"><span data-stu-id="89716-113">Multi-factor authentication is enabled for the user</span></span>
- <span data-ttu-id="89716-114">管理者がユーザーのすべての更新トークンを明示的に取り消す</span><span class="sxs-lookup"><span data-stu-id="89716-114">Administrator explicitly revokes all refresh tokens for a user</span></span>
- <span data-ttu-id="89716-115">Azure id Protection によって検出されたユーザー ADリスクの上昇</span><span class="sxs-lookup"><span data-stu-id="89716-115">Elevated user risk detected by Azure AD Identity Protection</span></span>

<span data-ttu-id="89716-116">クライアントおよびサービス アプリのサポートに対する継続的アクセス評価の詳細については、「継続的アクセス評価 [(プレビュー)」を参照してください](/azure/active-directory/conditional-access/concept-continuous-access-evaluation)。</span><span class="sxs-lookup"><span data-stu-id="89716-116">For more information about continuous access evaluation for client and services app support, see [Continuous access evaluation (preview)](/azure/active-directory/conditional-access/concept-continuous-access-evaluation).</span></span>

## <a name="client-support"></a><span data-ttu-id="89716-117">クライアント サポート</span><span class="sxs-lookup"><span data-stu-id="89716-117">Client support</span></span>

### <a name="certificate-based-authentication"></a><span data-ttu-id="89716-118">証明書ベースの認証</span><span class="sxs-lookup"><span data-stu-id="89716-118">Certificate-based authentication</span></span>

<span data-ttu-id="89716-119">証明書ベース認証 (CBA) は、リソース、ネットワーク、アプリケーション、またはサービスへのアクセスを許可する前に、デジタル証明書を使用してユーザー、コンピューター、またはデバイスを識別します。</span><span class="sxs-lookup"><span data-stu-id="89716-119">Certificate-based authentication (CBA) is the use of a digital certificate to identify a user, machine, or device before granting access to a resource, network, application, or service.</span></span> <span data-ttu-id="89716-120">ユーザー認証では、ユーザー名やパスワードなどの従来の方法と連携して展開される場合が多い。</span><span class="sxs-lookup"><span data-stu-id="89716-120">In user authentication, it is often deployed in coordination with traditional methods such as usernames and passwords.</span></span>

<span data-ttu-id="89716-121">一部の従来のソリューションは、生体認証やワンタイム パスワード (OTP) など、ユーザーにのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="89716-121">Some traditional solutions only work for users, such as biometrics and one-time passwords (OTP).</span></span> <span data-ttu-id="89716-122">証明書ベースの認証では、すべてのエンドポイントで同じソリューションを使用できます。ユーザー、デバイス、および増大するモノのインターネット (IoT)</span><span class="sxs-lookup"><span data-stu-id="89716-122">With certificate-based authentication, the same solution can be used for all endpoints; users, devices, and the growing Internet of Things (IoT).</span></span>

<span data-ttu-id="89716-123">クライアントおよびサービス アプリのサポートに対する証明書ベースの認証の詳細については [、「Microsoft 365 Client App Support: Certificate-based Authentication」を参照してください](microsoft-365-client-support-certificate-based-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="89716-123">For more information about certificate-based authentication for client and services app support, see [Microsoft 365 Client App Support: Certificate-based Authentication](microsoft-365-client-support-certificate-based-authentication.md).</span></span>

### <a name="conditional-access"></a><span data-ttu-id="89716-124">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="89716-124">Conditional Access</span></span>

<span data-ttu-id="89716-125">条件付きアクセスは、Azure Active Directory が信号をまとめ、決定を下し、組織のアクセス ポリシーを適用するために使用するツールです。</span><span class="sxs-lookup"><span data-stu-id="89716-125">Conditional Access is the tool used by Azure Active Directory to bring signals together, to make decisions, and enforce organizational access policies.</span></span> <span data-ttu-id="89716-126">条件付きアクセスは、新しい ID 駆動型コントロール モデルの中心です。</span><span class="sxs-lookup"><span data-stu-id="89716-126">Conditional Access is at the heart of the new identity-driven control model.</span></span>

<span data-ttu-id="89716-127">条件付きアクセス ポリシーは、リソースへのアクセスを許可する if-then ステートメントです。</span><span class="sxs-lookup"><span data-stu-id="89716-127">Conditional Access policies are if-then statements for granting access to resources.</span></span> <span data-ttu-id="89716-128">ユーザーがリソースにアクセスする場合、ユーザーはアクションを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89716-128">If a user wants to access a resource, then the user must complete an action.</span></span> <span data-ttu-id="89716-129">ポリシー アクセスの決定を行う際に条件付きアクセスで使用できる一般的な信号は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="89716-129">Common signals that Conditional Access can use when making a policy access decision include:</span></span>

- <span data-ttu-id="89716-130">ユーザーまたはグループのメンバーシップ</span><span class="sxs-lookup"><span data-stu-id="89716-130">User or group membership</span></span>
- <span data-ttu-id="89716-131">IP の場所情報</span><span class="sxs-lookup"><span data-stu-id="89716-131">IP location information</span></span>
- <span data-ttu-id="89716-132">デバイス情報</span><span class="sxs-lookup"><span data-stu-id="89716-132">Device information</span></span>
- <span data-ttu-id="89716-133">アプリケーション情報</span><span class="sxs-lookup"><span data-stu-id="89716-133">Application information</span></span>
- <span data-ttu-id="89716-134">リアルタイムおよび計算されたリスク検出</span><span class="sxs-lookup"><span data-stu-id="89716-134">Real-time and calculated risk detection</span></span>
- <span data-ttu-id="89716-135">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="89716-135">Microsoft Cloud App Security (MCAS)</span></span>

<span data-ttu-id="89716-136">これらのアクセス決定を行う場合、ポリシーは次の異なるアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="89716-136">When making these access decisions, the policies can take different actions:</span></span>

- <span data-ttu-id="89716-137">ポリシーはアクセスをブロックできます。この構成は最も制限の厳しいアクションであり、ユーザーがリソースにアクセスするのを防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="89716-137">The policy can block access: This configuration is the most restrictive action and prevents the user from accessing the resource.</span></span>
- <span data-ttu-id="89716-138">ポリシーはアクセスを許可できます。この構成は制限の少ない決定であり、次のオプションの 1 つ以上が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="89716-138">The policy can grant access: This configuration is a less restrictive decision and may still require one or more of the following options:</span></span>

    - <span data-ttu-id="89716-139">多要素認証</span><span class="sxs-lookup"><span data-stu-id="89716-139">Multi-factor authentication</span></span>
    - <span data-ttu-id="89716-140">準拠としてマークするデバイス</span><span class="sxs-lookup"><span data-stu-id="89716-140">The device to be marked as compliant</span></span>
    - <span data-ttu-id="89716-141">デバイスはハイブリッド Azure ADです</span><span class="sxs-lookup"><span data-stu-id="89716-141">The device is hybrid Azure AD joined</span></span>
    - <span data-ttu-id="89716-142">承認済みクライアント アプリ</span><span class="sxs-lookup"><span data-stu-id="89716-142">An approved client app</span></span>
    - <span data-ttu-id="89716-143">構成されたアプリ保護ポリシー (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="89716-143">App protection policy configured (preview)</span></span>

<span data-ttu-id="89716-144">クライアントおよびサービス アプリのサポートに対する条件付きアクセスの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89716-144">For more information about Conditional Access for client and services app support, see:</span></span>

- [<span data-ttu-id="89716-145">Microsoft 365 クライアント アプリのサポート: デバイス ベースの条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="89716-145">Microsoft 365 Client App Support: Device-based Conditional Access</span></span>](microsoft-365-client-support-conditional-access.md)

### <a name="mobile-application-management"></a><span data-ttu-id="89716-146">モバイル アプリケーション管理</span><span class="sxs-lookup"><span data-stu-id="89716-146">Mobile application management</span></span>

<span data-ttu-id="89716-147">ユーザーは、多くの場合、同じモバイル デバイスから組織と個人のドキュメント、電子メール、およびデータの両方にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="89716-147">Users often access both organization and personal documents, email, and data from the same mobile device.</span></span> <span data-ttu-id="89716-148">これらのデバイスは、多くの場合、個人所有であり、組織データとユーザーの個人プライバシーの両方を保護するように構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89716-148">Those devices are often personally owned and should be configured to protect both organization data and the user's personal privacy.</span></span>

<span data-ttu-id="89716-149">ユーザーが組織データにアクセスする場合、組織は、構成ポリシーや保護ポリシーなどの組織ポリシーがデバイス上の組織データを保護するために適用されるという確信を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="89716-149">When a user accesses organization data, the organization must be confident that organization policies, such as configuration policies and protection policies, are applied to help protect organization data on the device.</span></span> <span data-ttu-id="89716-150">さらに、デバイス上のユーザーの個人コンテンツは、組織の制御の外に残る必要があります。</span><span class="sxs-lookup"><span data-stu-id="89716-150">Additionally, the user's personal content on the device should remain outside of the organization's control.</span></span>

<span data-ttu-id="89716-151">組織で管理されるコンテンツの場合は、アプリケーション管理ポリシーを適用して、Microsoft Intune を使用してデータにアクセス、共有、および使用する方法を制御できます。</span><span class="sxs-lookup"><span data-stu-id="89716-151">For organization-managed content, you can apply application management policies to control how data is accessed, shared, and used by using Microsoft Intune.</span></span> <span data-ttu-id="89716-152">たとえば、次のアクションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="89716-152">For example, the following actions are supported:</span></span>

- <span data-ttu-id="89716-153">管理された組織のコンテンツをリモートワイプする (組織データとも呼ばれます)</span><span class="sxs-lookup"><span data-stu-id="89716-153">Remote wipe the managed organization content (also referred to org data)</span></span>
- <span data-ttu-id="89716-154">組織のコンテンツを組織以外の場所に貼り付け防止する</span><span class="sxs-lookup"><span data-stu-id="89716-154">Prevent pasting organization content into non-organization locations</span></span>
- <span data-ttu-id="89716-155">組織のコンテンツにアクセスするために PIN を要求する</span><span class="sxs-lookup"><span data-stu-id="89716-155">Require a PIN to access organization content</span></span>
- <span data-ttu-id="89716-156">管理対象アプリが脱獄またはルートデバイスで実行されるのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="89716-156">Prevent managed apps from running on jailbroken or rooted devices</span></span>
- <span data-ttu-id="89716-157">組織のコンテンツが未承認のクラウド ストレージ プロバイダーに保存されるのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="89716-157">Prevent organization content from being saved to unapproved cloud storage providers</span></span>
- <span data-ttu-id="89716-158">未承認のコンテンツが管理アプリケーションに転送されるのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="89716-158">Prevent unapproved content from being transferred into managed applications</span></span>
- <span data-ttu-id="89716-159">ポリシーが適用された後にのみ、組織のコンテンツへのアクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="89716-159">Allow access to organization content only after policies have been applied</span></span>
- <span data-ttu-id="89716-160">アプリケーションの動作と設定を管理するためのアプリケーション構成を提供する</span><span class="sxs-lookup"><span data-stu-id="89716-160">Deliver application configuration to manage the application's behavior and settings</span></span>
- <span data-ttu-id="89716-161">マルチ ID 機能または個人用の使用を無効にして、管理アプリケーションを定義済みの ID に制限する</span><span class="sxs-lookup"><span data-stu-id="89716-161">Restrict the managed application to a defined identity by disabling multi-identity capabilities or personal usage</span></span>

<span data-ttu-id="89716-162">Microsoft Intune でのモバイル アプリケーション管理の詳細については、「Microsoft Intune アプリ管理とは [」を参照してください。](/mem/intune/apps/app-management)</span><span class="sxs-lookup"><span data-stu-id="89716-162">For more information about mobile application management with Microsoft Intune, see [What is Microsoft Intune app management?](/mem/intune/apps/app-management)</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="89716-163">多要素認証</span><span class="sxs-lookup"><span data-stu-id="89716-163">Multi-factor authentication</span></span>

<span data-ttu-id="89716-164">[多要素認証 (MFA) は、複数の個別の証拠を認証メカニズムに正常に提示した後にのみ、ユーザーにアクセスを許可するコンピューター アクセス制御の方法です。</span><span class="sxs-lookup"><span data-stu-id="89716-164">[Multi-factor authentication (MFA) is a method of computer access control in which a user is granted access only after successfully presenting several separate pieces of evidence to an authentication mechanism.</span></span> <span data-ttu-id="89716-165">このメソッドは通常、次のカテゴリのうち少なくとも 2 つを使用します。</span><span class="sxs-lookup"><span data-stu-id="89716-165">This method typically uses at least two of the following categories:</span></span>

- <span data-ttu-id="89716-166">知識 (知っているもの)</span><span class="sxs-lookup"><span data-stu-id="89716-166">Knowledge (something they know)</span></span>
- <span data-ttu-id="89716-167">所有 (持っているもの)</span><span class="sxs-lookup"><span data-stu-id="89716-167">Possession (something they have)</span></span>
- <span data-ttu-id="89716-168">インヘレンス (何か)</span><span class="sxs-lookup"><span data-stu-id="89716-168">Inherence (something they are)</span></span>

<span data-ttu-id="89716-169">クライアントおよびサービス アプリのサポートに対する多要素認証の詳細については [、「Microsoft 365 Client App Support: 多要素認証」を参照してください](microsoft-365-client-support-multi-factor-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="89716-169">For more information about multi-factor authentication for client and services app support, see [Microsoft 365 Client App Support: Multi-factor authentication](microsoft-365-client-support-multi-factor-authentication.md).</span></span>

### <a name="single-sign-on"></a><span data-ttu-id="89716-170">シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="89716-170">Single sign-on</span></span>

<span data-ttu-id="89716-171">シングル サインオン (SSO) は、ユーザーが Azure Active Directory のアプリケーションにサインオンするときにセキュリティと利便性を向上します。</span><span class="sxs-lookup"><span data-stu-id="89716-171">Single sign-on (SSO) adds security and convenience when your users sign-on to applications in Azure Active Directory.</span></span> <span data-ttu-id="89716-172">シングル サインオンでは、ユーザーは 1 つのアカウントで 1 回サインインして、組織内のオンプレミスの Active Directory ドメイン サービス (AD DS) ドメインに参加しているデバイス、サービスとしてのソフトウェア (SaaS) アプリケーション、および Web アプリケーションにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="89716-172">With single sign-on, users sign in once with one account to access on-premises Active Directory Domain Services (AD DS) domain-joined devices, software as a service (SaaS) applications, and web applications in your organization.</span></span>

<span data-ttu-id="89716-173">クライアントおよびサービス アプリサポートのシングル サインオンの詳細については [、「Microsoft 365 Client App Support: Single sign-on」を参照してください](microsoft-365-client-support-single-sign-on.md)。</span><span class="sxs-lookup"><span data-stu-id="89716-173">For more information about single sign-on for client and services app support, see [Microsoft 365 Client App Support: Single sign-on](microsoft-365-client-support-single-sign-on.md).</span></span>

## <a name="services-support"></a><span data-ttu-id="89716-174">サービスのサポート</span><span class="sxs-lookup"><span data-stu-id="89716-174">Services support</span></span>

### <a name="modern-authentication"></a><span data-ttu-id="89716-175">先進認証</span><span class="sxs-lookup"><span data-stu-id="89716-175">Modern authentication</span></span>

<span data-ttu-id="89716-176">最新の認証では、Office 365 に対して認証を行い、テナント管理者が Office 365 テナント全体で次のような特定の認証要件を適用するための新しいシナリオを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89716-176">Modern authentication enables new scenarios for customers to authenticate against Office 365 and for tenant admins to enforce specific authentication requirements across the Office 365 tenancy, such as:</span></span>

- <span data-ttu-id="89716-177">テナントとサービスとの管理操作、およびアプリケーションとそのデータとのエンド ユーザーの対話に対する多要素認証のサポート</span><span class="sxs-lookup"><span data-stu-id="89716-177">Multi-factor authentication support for administrative interaction with the tenancy and services, and end-user interaction with applications and their data</span></span>
- <span data-ttu-id="89716-178">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="89716-178">Conditional access</span></span>
- <span data-ttu-id="89716-179">SAML ベースのサード パーティ ID プロバイダーのサインイン</span><span class="sxs-lookup"><span data-stu-id="89716-179">SAML-based third-party identity provider sign-in</span></span>
- <span data-ttu-id="89716-180">パーソナル コンピューター上のスマートカード ログ</span><span class="sxs-lookup"><span data-stu-id="89716-180">Smartcard log on personal computers</span></span>
- <span data-ttu-id="89716-181">モバイル デバイスでの証明書ベースの認証</span><span class="sxs-lookup"><span data-stu-id="89716-181">Certificate-based authentication on mobile devices</span></span>
- <span data-ttu-id="89716-182">基本認証を使用して資格情報を送信する必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="89716-182">No longer require the transmission of credentials over basic authentication.</span></span>

<span data-ttu-id="89716-183">最新の認証サービスのサポートの詳細については、「認証と [承認」を参照してください](/azure/active-directory/develop/authentication-vs-authorization)。</span><span class="sxs-lookup"><span data-stu-id="89716-183">For more information about modern authentication services support, see [Authentication vs. authorization](/azure/active-directory/develop/authentication-vs-authorization).</span></span>

### <a name="azure-active-directory-conditional-access"></a><span data-ttu-id="89716-184">Azure Active Directory の条件付きアクセスとは</span><span class="sxs-lookup"><span data-stu-id="89716-184">Azure Active Directory Conditional Access</span></span>

<span data-ttu-id="89716-185">Azure Active Directory (Azure AD) 条件付きアクセス ルールを使用すると、デバイスコンプライアンスやネットワークの場所などの属性に基づいて、オンライン サービスへのアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="89716-185">Azure Active Directory (Azure AD) Conditional Access rules allow customers to control access to online services, based on attributes such as device compliance or network location.</span></span> <span data-ttu-id="89716-186">次のソリューションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="89716-186">The following solutions may be used:</span></span>

- <span data-ttu-id="89716-187">Azure AD多要素認証ベースの条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="89716-187">Azure AD multi-factor authentication-based Conditional Access</span></span>
- <span data-ttu-id="89716-188">Azure ADベースの条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="89716-188">Azure AD location-based Conditional Access</span></span>
- <span data-ttu-id="89716-189">Azure ADベースの条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="89716-189">Azure AD device-based Conditional Access</span></span>

<span data-ttu-id="89716-190">Azure AD条件付きアクセス ルールはアプリケーションごとに適用され、さまざまな条件に基づいてアクセスを制御できます。</span><span class="sxs-lookup"><span data-stu-id="89716-190">Azure AD Conditional access rules are applied per-application and are available for customers to control access based on different conditions.</span></span> <span data-ttu-id="89716-191">モバイル [デバイス管理 (MDM)](/mem/intune/fundamentals/what-is-device-management)または Intune を使用すると、組織のデバイスを使用しているユーザー、または管理のために個人用デバイスを登録したユーザーにのみ、Microsoft 365 へのアクセスを制限できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="89716-191">Using [Mobile Device Management (MDM) or Intune](/mem/intune/fundamentals/what-is-device-management), customers must be able to restrict access to Microsoft 365 to only those users who are using an organization device or who have enrolled their personal device for management.</span></span> <span data-ttu-id="89716-192">たとえば、次のようなコントロールを適用するために条件付きアクセス ルールを構成できます。</span><span class="sxs-lookup"><span data-stu-id="89716-192">For example, customers may configure Conditional Access rules to enforce controls such as:</span></span>

- <span data-ttu-id="89716-193">ドメインに参加しているデバイスまたはドメインに準拠しているデバイスからのアクセスのみを許可する</span><span class="sxs-lookup"><span data-stu-id="89716-193">Only allow access from devices that are domain joined or domain compliant</span></span>
- <span data-ttu-id="89716-194">Exchange Online サービスへのすべてのアクセスに対して多要素認証を適用する</span><span class="sxs-lookup"><span data-stu-id="89716-194">Enforce multi-factor authentication for all access to Exchange Online services</span></span>

<span data-ttu-id="89716-195">Azure Active Directory 条件付きアクセスの詳細については、「条件付きアクセス [とは」を参照してください。](/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="89716-195">For more information about Azure Active Directory Conditional Access, see [What is Conditional Access?](/azure/active-directory/conditional-access/overview)</span></span>

### <a name="tls-12-support"></a><span data-ttu-id="89716-196">TLS 1.2 のサポート</span><span class="sxs-lookup"><span data-stu-id="89716-196">TLS 1.2 support</span></span>

<span data-ttu-id="89716-197">Microsoft は、クラス最高の暗号化をお客様に提供するために、Office 365 および Office 365 GCC のトランスポート層セキュリティ (TLS) バージョン 1.0 および 1.1 のサポートを中止する予定です。</span><span class="sxs-lookup"><span data-stu-id="89716-197">To provide the best-in-class encryption to our customers, Microsoft plans to discontinue support for Transport Layer Security (TLS) versions 1.0 and 1.1 in Office 365 and Office 365 GCC.</span></span>

<span data-ttu-id="89716-198">お客様のデータに対するセキュリティの重要性を理解すると共に、お客様が利用しているサービスに影響を及ぼす可能性のある変更については、その情報を公開することをお約束いたします。</span><span class="sxs-lookup"><span data-stu-id="89716-198">We understand that the security of your data is important, and we're committed to transparency about changes that may affect your use of the TLS service.</span></span> <span data-ttu-id="89716-199">すべてのクライアント サーバーとブラウザー サーバーの組み合わせでは、TLS 1.2 (または以降のバージョン) を使用して、365 サービスへの接続Officeすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="89716-199">We recommend that all client-server and browser-server combinations use TLS 1.2 (or a later version) to maintain connection to Office 365 services.</span></span> <span data-ttu-id="89716-200">クライアントとサーバー間、ブラウザーとサーバー間の特定の組み合わせについては、更新が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="89716-200">You might have to update certain client-server and browser-server combinations.</span></span>

<span data-ttu-id="89716-201">TLS 1.2 のサポートとサービスのサポートの詳細については [、「Office 365 および Office 365 GCC での TLS 1.2](../compliance/prepare-tls-1.2-in-office-365.md)の準備」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="89716-201">For more information about TLS 1.2 support and services support, see [Preparing for TLS 1.2 in Office 365 and Office 365 GCC](../compliance/prepare-tls-1.2-in-office-365.md).</span></span>