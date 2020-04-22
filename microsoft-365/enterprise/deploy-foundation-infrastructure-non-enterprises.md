---
title: 非エンタープライズ組織のためのエンタープライズ向け Microsoft 365 の基礎インフラストラクチャ
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/08/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 非エンタープライズ組織向けの、エンタープライズ向け Microsoft 365 基礎インフラストラクチャの簡略化されたフェーズを説明します。
ms.openlocfilehash: cad142f2f26eb999431eb5bb531cb4520e4d6102
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638262"
---
# <a name="microsoft-365-for-enterprise-foundation-infrastructure-for-non-enterprises"></a><span data-ttu-id="ac542-103">非エンタープライズ組織のためのエンタープライズ向け Microsoft 365 の基礎インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="ac542-103">Microsoft 365 for enterprise foundation infrastructure for non-enterprises</span></span>

<span data-ttu-id="ac542-104">エンタープライズ以外の組織でも、エンタープライズ向け Microsoft 365 を展開することで、チームワークを可能にして創造性を解き放つ、統合された安全なインフラストラクチャがもたらすビジネス価値を実現することができます。</span><span class="sxs-lookup"><span data-stu-id="ac542-104">Non-enterprise organizations can also deploy Microsoft 365 for enterprise and realize the business value of an integrated and secure infrastructure that enables teamwork and unlocks creativity.</span></span> <span data-ttu-id="ac542-105">通常、エンタープライズ以外の組織では以下が一般的です。</span><span class="sxs-lookup"><span data-stu-id="ac542-105">A non-enterprise typically has:</span></span>

- <span data-ttu-id="ac542-106">メール サーバー、ファイル サーバー、Active Directory Domain Services (AD DS) ドメインなど、小規模のオンプレミスの IT インフラストラクチャを装備している。または IT インフラストラクチャがまったく装備されていない。</span><span class="sxs-lookup"><span data-stu-id="ac542-106">A small amount of on-premises IT infrastructure, such as email and file servers and an Active Directory Domain Services (AD DS) domain, or none at all.</span></span>
- <span data-ttu-id="ac542-107">IT スタッフは少人数であり、そのほとんどが IT ゼネラリストであって、ネットワークや電子メールなどの特定のテクノロジやワークロードのスペシャリストではない。</span><span class="sxs-lookup"><span data-stu-id="ac542-107">A small IT staff, most of whom are IT generalists, rather than specialists in a specific technology or workload such as networking or email.</span></span>

<span data-ttu-id="ac542-108">小規模な非エンタープライズ組織向けに、Microsoft は [Microsoft 365 for business](https://www.microsoft.com/microsoft-365/business) を提供しています。</span><span class="sxs-lookup"><span data-stu-id="ac542-108">For smaller, non-enterprise organizations, Microsoft offers [Microsoft 365 for business](https://www.microsoft.com/microsoft-365/business).</span></span> <span data-ttu-id="ac542-109">しかし、次のような理由で エンタープライズ向け Microsoft 365 が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ac542-109">However, there are reasons why you might need Microsoft 365 for enterprise, such as:</span></span>

- <span data-ttu-id="ac542-110">組織が現時点で、または将来的に、 Microsoft 365 for business の最大数である、300 を超えるMicrosoft 365 のライセンスを必要としている。</span><span class="sxs-lookup"><span data-stu-id="ac542-110">Your organization needs more or will need more than 300 Microsoft 365 licenses, which is the maximum for Microsoft 365 for business.</span></span>
- <span data-ttu-id="ac542-111">組織が、Microsoft 365 for business では利用できない高度な生産性、音声、セキュリティ、分析機能を必要としている。</span><span class="sxs-lookup"><span data-stu-id="ac542-111">Your organization needs the advanced productivity, voice, security, and analytics capabilities that are not available with Microsoft 365 for business.</span></span>

<span data-ttu-id="ac542-112">この記事では、非エンタープライズ組織に適した、エンタープライズ向け Microsoft 365 の基礎インフラストラクチャの簡略化された展開手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ac542-112">This article steps you through a simplified deployment of the foundation infrastructure of Microsoft 365 for enterprise suitable for your non-enterprise.</span></span>

## <a name="first-set-up-your-subscription"></a><span data-ttu-id="ac542-113">最初の手順: サブスクリプションのセットアップ</span><span class="sxs-lookup"><span data-stu-id="ac542-113">First, set up your subscription</span></span>

<span data-ttu-id="ac542-114">サブスクリプションのドメイン ネーム システム (DNS) ドメインをセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac542-114">You must set up the Domain Name System (DNS) domains for your subscription.</span></span> <span data-ttu-id="ac542-115">Microsoft 365 サブスクリプションが既にある場合、この手順は完了しています。</span><span class="sxs-lookup"><span data-stu-id="ac542-115">If you already have a Microsoft 365 subscription, this should have been done.</span></span> <span data-ttu-id="ac542-116">ない場合は、「[Office 365 にドメインを追加する](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="ac542-116">If not, follow the instructions in [Add a domain to Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain?view=o365-worldwide).</span></span>

<span data-ttu-id="ac542-117">次に、Microsoft 365 に対して追加のセキュリティを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac542-117">Next, you need to configure additional security for Microsoft 365.</span></span> <span data-ttu-id="ac542-118">「[セキュリティ強化を構成する](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)」の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="ac542-118">Follow the instructions in [Configure increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

## <a name="phase-1-networking"></a><span data-ttu-id="ac542-119">フェーズ 1: ネットワーク</span><span class="sxs-lookup"><span data-stu-id="ac542-119">Phase 1: Networking</span></span>

<span data-ttu-id="ac542-120">通常、エンタープライズ以外の組織の場合、各オフィスでローカル インターネット接続を使用しており、プロキシ サーバー、ファイアウォール、パケット検査デバイスは使用していません。</span><span class="sxs-lookup"><span data-stu-id="ac542-120">Non-enterprise organizations typically have local Internet connections in each office and do not use proxy servers, firewalls, or packet inspection devices.</span></span> <span data-ttu-id="ac542-121">各オフィスのインターネット サービス プロバイダー (ISP) は地域のローカル DNS サーバーを用意しているので、トラフィックは各自のオフィスとそのオフィスのオンプレミス ユーザーに最も近い Microsoft 365 のネットワークの場所に直接送信されます。</span><span class="sxs-lookup"><span data-stu-id="ac542-121">The Internet service provider (ISP) serving each office has a regionally local DNS server so that traffic is directed to the Microsoft 365 network location that is closest to your offices and their on-premises users.</span></span> <span data-ttu-id="ac542-122">詳細については、「[オフィスごとにローカルのインターネット接続を構成する](networking-dns-resolution-same-location.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-122">For more information, see [Configure local Internet connections for each office](networking-dns-resolution-same-location.md).</span></span>

<span data-ttu-id="ac542-123">したがって、各オフィスの所在地の接続について ISP に確認が必要なのは、以下の事項のみです。</span><span class="sxs-lookup"><span data-stu-id="ac542-123">Therefore, you only need to verify with your ISP that the connection at each of your office locations:</span></span>

- <span data-ttu-id="ac542-124">地域のローカル DNS サーバーを使用している。</span><span class="sxs-lookup"><span data-stu-id="ac542-124">Uses a regionally local DNS server.</span></span>
- <span data-ttu-id="ac542-125">ユーザーがより多くの Microsoft 365 クラウドサービスを使い始めても、現在および将来のニーズを十分に満たす能力がある。</span><span class="sxs-lookup"><span data-stu-id="ac542-125">Is adequate for current and future needs as your users begin using more Microsoft 365 cloud services.</span></span>

<span data-ttu-id="ac542-126">プロキシ サーバー、ファイアウォール、またはパケット検査デバイスを使用する場合、Microsoft 365 サービスのパフォーマンスを最適化する方法については、「[トラフィック バイパスを構成する](networking-configure-proxies-firewalls.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-126">If you do use proxy servers, firewalls, or packet inspection devices, see [Configure traffic bypass](networking-configure-proxies-firewalls.md) for information on how to optimize performance to Microsoft 365 services.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="ac542-127">これまでの構成</span><span class="sxs-lookup"><span data-stu-id="ac542-127">Your configuration so far</span></span>

<span data-ttu-id="ac542-128">以下は、フェーズ 1 の要素に注目して概要を視覚的に示したものです。</span><span class="sxs-lookup"><span data-stu-id="ac542-128">Here is a visual summary with the Phase 1 element highlighted.</span></span> <span data-ttu-id="ac542-129">**組織**には複数のオフィスがある場合があり、各オフィスには地域のローカル DNS サーバーを使用している ISP 経由のローカル インターネット接続があります。</span><span class="sxs-lookup"><span data-stu-id="ac542-129">**Your organization** can be multiple offices, each of which has a local Internet connection with an ISP that uses a regionally local DNS server.</span></span> <span data-ttu-id="ac542-130">ISP を介して、各オフィスのユーザーは、最も近い Microsoft 365 のネットワークの場所にアクセスして Microsoft 365 サブスクリプションのリソースを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ac542-130">Through the ISP, users in each office can reach the nearest Microsoft 365 network location and the resources of your Microsoft 365 subscription.</span></span>

![ネットワーク フェーズ後の組織](../media/deploy-foundation-infrastructure-non-enterprises/networking-config.png)

## <a name="phase-2-identity"></a><span data-ttu-id="ac542-132">フェーズ 2: ID</span><span class="sxs-lookup"><span data-stu-id="ac542-132">Phase 2: Identity</span></span>

<span data-ttu-id="ac542-133">組織の各従業員がサインインできる状態である必要があります。そのためには、エンタープライズ向け Microsoft 365 サブスクリプションの Azure Active Directory (Azure AD) テナントにユーザー アカウントがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac542-133">Each employee of your organization must be able to sign in, which requires a user account in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 for enterprise subscription.</span></span> <span data-ttu-id="ac542-134">次にグループが、SharePoint Online サイトやチームなどのアクセス許可が付与されたリソースと通信したり、それらにアクセスしたりするために、ユーザー アカウントやその他のグループをまとめるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="ac542-134">Groups are then used to contain user accounts and other groups to communicate or gain access to permissioned resources, such as a SharePoint Online site or a team.</span></span> 

### <a name="administrator-accounts"></a><span data-ttu-id="ac542-135">管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="ac542-135">Administrator accounts</span></span>

<span data-ttu-id="ac542-136">強力なパスワードや多要素認証 (MFA) を要求することで、グローバル管理者ユーザー アカウントを保護します。</span><span class="sxs-lookup"><span data-stu-id="ac542-136">Protect your global administrator user accounts by requiring strong passwords and multi-factor authentication (MFA).</span></span> <span data-ttu-id="ac542-137">詳細については、「[グローバル管理者アカウントを保護する](identity-create-protect-global-admins.md#protect-global-administrator-accounts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-137">See [Protect global administrator accounts](identity-create-protect-global-admins.md#protect-global-administrator-accounts) for more information.</span></span>

<span data-ttu-id="ac542-138">高度なセキュリティが要求される組織で Microsoft 365 E5 を使用している場合、Azure AD Privileged Identity Management を使用して、ジャストインタイムの管理者アクセスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ac542-138">If your organization requires high security and you have Microsoft 365 E5, use Azure AD Privileged Identity Management to enable just-in-time administrator access.</span></span> <span data-ttu-id="ac542-139">詳細については、「[オンデマンド グローバル管理者をセットアップする](identity-create-protect-global-admins.md#identity-pim)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-139">See [Set up on-demand global administrators](identity-create-protect-global-admins.md#identity-pim) for more information.</span></span>

### <a name="recommendations-for-groups"></a><span data-ttu-id="ac542-140">グループに関する推奨事項</span><span class="sxs-lookup"><span data-stu-id="ac542-140">Recommendations for groups</span></span>

<span data-ttu-id="ac542-141">オンプレミス AD DS ドメインがある場合、これらのグループは、Azure AD のグループとして引き続きエンタープライズ向け Microsoft 365 で使用します。</span><span class="sxs-lookup"><span data-stu-id="ac542-141">If you have an on-premises AD DS domain, continue to use those groups in Microsoft 365 for enterprise as groups in Azure AD.</span></span>

<span data-ttu-id="ac542-142">オンプレミスの AD DS ドメインがない場合は、以下のレベルのセキュリティを使用して、Azure AD でセキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac542-142">If you don't have an on-premises AD DS domain, create security groups in Azure AD using these levels of security.</span></span>

| <span data-ttu-id="ac542-143">セキュリティ レベル</span><span class="sxs-lookup"><span data-stu-id="ac542-143">Security level</span></span> | <span data-ttu-id="ac542-144">説明</span><span class="sxs-lookup"><span data-stu-id="ac542-144">Description</span></span> | <span data-ttu-id="ac542-145">例</span><span class="sxs-lookup"><span data-stu-id="ac542-145">Examples</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="ac542-146">ベースライン</span><span class="sxs-lookup"><span data-stu-id="ac542-146">Baseline</span></span> | <span data-ttu-id="ac542-147">これは、データ、データにアクセスする ID とデバイスを保護するための最低限の既定の基準です。</span><span class="sxs-lookup"><span data-stu-id="ac542-147">This is a minimum and default  standard for protecting data and the identities and devices that access your data.</span></span> <BR><BR> <span data-ttu-id="ac542-148">通常、ほとんどのユーザーによって管理されている組織の大部分のデータが対象になります。</span><span class="sxs-lookup"><span data-stu-id="ac542-148">This is typically most of your organization's data managed by most of your users.</span></span> | <span data-ttu-id="ac542-149">営業、マーケティング、サポート、管理、製造など、現場担当者を対象にしたグループ。</span><span class="sxs-lookup"><span data-stu-id="ac542-149">Groups for first line workers, such as sales, marketing, support, administration, and manufacturing.</span></span> |
| <span data-ttu-id="ac542-150">機密</span><span class="sxs-lookup"><span data-stu-id="ac542-150">Sensitive</span></span> | <span data-ttu-id="ac542-151">これは、ベースライン レベルを越えて保護する必要があるデータのサブセットに対する追加の保護です。</span><span class="sxs-lookup"><span data-stu-id="ac542-151">This is additional protection for a subset of your data that must be protected beyond the baseline level.</span></span> <span data-ttu-id="ac542-152">これらのグループには、すべてのユーザーが利用できるようには意図されていない、部署やプロジェクトに固有の機密性の高いデータを使用および作成するユーザーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ac542-152">These groups contain users that use and create sensitive data that is specific to departments and projects that are not meant to be available to everyone.</span></span> | <span data-ttu-id="ac542-153">今後導入予定の製品を開発している製品チームまたはマーケティング チーム</span><span class="sxs-lookup"><span data-stu-id="ac542-153">Product or marketing teams that are developing future products</span></span> |
| <span data-ttu-id="ac542-154">厳しく規制</span><span class="sxs-lookup"><span data-stu-id="ac542-154">Highly regulated</span></span> | <span data-ttu-id="ac542-155">これは、高度に分類され、知的財産または営業秘密と見なされる、通常は少量のデータ、またはセキュリティ規制に準拠する必要があるデータに対する最高レベルの保護です。</span><span class="sxs-lookup"><span data-stu-id="ac542-155">This is the highest level of protection for a typically small amount of data that is highly classified, considered intellectual property or trade secrets, or data that must adhere to security regulations.</span></span> |  <span data-ttu-id="ac542-156">研究チーム、法務チーム、財務チーム、あるいは顧客やパートナーのデータを保存または使用するチーム。</span><span class="sxs-lookup"><span data-stu-id="ac542-156">Research, legal, and financial teams, or teams storing or using customer or partner data.</span></span> |
||||

### <a name="hybrid-identity"></a><span data-ttu-id="ac542-157">ハイブリッド ID</span><span class="sxs-lookup"><span data-stu-id="ac542-157">Hybrid identity</span></span>

<span data-ttu-id="ac542-158">オンプレミスの AD DS ドメインがある場合は、ドメインのユーザー アカウント、グループ、連絡先一式をエンタープライズ向け Microsoft 365 サブスクリプションの Azure AD テナントと同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac542-158">If you have an on-premises AD DS domain, you need to synchronize the set of user accounts, groups, and contacts of your domain with the Azure AD tenant of your Microsoft 365 for enterprise subscription.</span></span> <span data-ttu-id="ac542-159">エンタープライズ以外の場合は、パスワード ハッシュ同期 (PHS) を使用してサーバー上に Azure AD Connect を構成します。</span><span class="sxs-lookup"><span data-stu-id="ac542-159">For your non-enterprise, you configure Azure AD Connect on a server with password hash synchronization (PHS).</span></span> <span data-ttu-id="ac542-160">詳細については、「[ID を同期する](identity-add-user-accounts.md#synchronize-identities-for-hybrid-identity)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-160">See [Synchronize identities](identity-add-user-accounts.md#synchronize-identities-for-hybrid-identity) for more information.</span></span>

### <a name="more-secure-user-access-with-conditional-access-policies"></a><span data-ttu-id="ac542-161">条件付きアクセスポリシーを使用したユーザー アクセスのセキュリティ強化</span><span class="sxs-lookup"><span data-stu-id="ac542-161">More secure user access with Conditional Access policies</span></span>

<span data-ttu-id="ac542-162">Azure AD では、ユーザーのサインインの条件が評価されます。また、条件付きアクセス ポリシーを使用して、アクセスを許可または拒否したり、サインインを完了するために必要なその他のアクションを適用したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac542-162">Azure AD evaluates the conditions of user sign-ins and can use Conditional Access policies to grant or deny access and impose further actions that must be taken to complete the sign-in.</span></span> <span data-ttu-id="ac542-163">たとえば、Azure AD によってサインインが中リスクまたは高リスクの条件下で行われていると判断された場合、ユーザーはサインインを完了するために MFA を実行するよう求められます。</span><span class="sxs-lookup"><span data-stu-id="ac542-163">For example, if Azure AD determines that the sign-in is happening under medium or high-risk conditions, it can require the user to perform MFA to complete the sign-in.</span></span>

<span data-ttu-id="ac542-164">条件付きアクセス ポリシーをユーザー アカウントまたはグループに適用します。</span><span class="sxs-lookup"><span data-stu-id="ac542-164">You apply Conditional Access policies to user accounts or groups.</span></span> <span data-ttu-id="ac542-165">条件付きアクセス ポリシーの割り当てを容易にするには、組織内に次の Azure AD セキュリティ グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac542-165">To facilitate an easier assignment of Conditional Access policies, create these Azure AD security groups in your organization:</span></span>

- <span data-ttu-id="ac542-166">ベースライン</span><span class="sxs-lookup"><span data-stu-id="ac542-166">BASELINE</span></span>

  <span data-ttu-id="ac542-167">ベースライン データにアクセスできるユーザーのグループまたはユーザー アカウントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ac542-167">Contains the groups or user accounts for users with access to baseline data.</span></span>

- <span data-ttu-id="ac542-168">機密</span><span class="sxs-lookup"><span data-stu-id="ac542-168">SENSITIVE</span></span>

  <span data-ttu-id="ac542-169">機密性の高いデータにアクセスできるユーザーのグループまたはユーザー アカウントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ac542-169">Contains the groups or user accounts for users with access to sensitive data.</span></span>

- <span data-ttu-id="ac542-170">厳しく規制</span><span class="sxs-lookup"><span data-stu-id="ac542-170">HIGHLY-REGULATED</span></span>

  <span data-ttu-id="ac542-171">厳しく規制されているデータにアクセスできるユーザーのグループまたはユーザー アカウントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ac542-171">Contains the groups or user accounts for users with access to highly regulated data.</span></span>

- <span data-ttu-id="ac542-172">条件付きアクセスの除外</span><span class="sxs-lookup"><span data-stu-id="ac542-172">COND-ACCESS-EXCLUDE</span></span>

  <span data-ttu-id="ac542-173">条件付きアクセス ポリシーから一時的にユーザーを除外するために使用できる空のグループ。</span><span class="sxs-lookup"><span data-stu-id="ac542-173">An empty group that you can use to temporarily exclude a user from Conditional Access policies.</span></span>

<span data-ttu-id="ac542-174">以下は、有効にする、または作成する Azure AD 条件付きアクセス ポリシーの一覧です。</span><span class="sxs-lookup"><span data-stu-id="ac542-174">Here is the list of Azure AD Conditional Access policies to enable or create.</span></span>

| <span data-ttu-id="ac542-175">Azure AD 条件付きアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="ac542-175">Azure AD Conditional Access policy</span></span> | <span data-ttu-id="ac542-176">適用対象のグループ</span><span class="sxs-lookup"><span data-stu-id="ac542-176">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="ac542-177">ベースライン ポリシー: 管理者に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="ac542-177">Baseline policy: Require MFA for admins</span></span> | <span data-ttu-id="ac542-178">このポリシーは管理者の役割に適用されるため、グループを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ac542-178">This policy applies to admin roles, so no groups need to be specified.</span></span> <span data-ttu-id="ac542-179">このポリシーは有効にするだけで済みます。</span><span class="sxs-lookup"><span data-stu-id="ac542-179">This policy just needs to be enabled.</span></span> <span data-ttu-id="ac542-180">以降のすべてのポリシーは、作成して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac542-180">All subsequent policies need to be created and enabled.</span></span> |
| <span data-ttu-id="ac542-181">先進認証をサポートしないクライアントはブロックする</span><span class="sxs-lookup"><span data-stu-id="ac542-181">Block clients that don't support modern authentication</span></span> | <span data-ttu-id="ac542-182">ポリシー設定で [すべてのユーザー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac542-182">Select "All users" in the policy settings.</span></span> |
| <span data-ttu-id="ac542-183">サインインのリスクが中または高のときに MFA が必要 (Microsoft 365 E5 が必要)</span><span class="sxs-lookup"><span data-stu-id="ac542-183">Require MFA when sign-in risk is medium or high (requires Microsoft 365 E5)</span></span> | <span data-ttu-id="ac542-184">ベースライン</span><span class="sxs-lookup"><span data-stu-id="ac542-184">BASELINE</span></span> |
| <span data-ttu-id="ac542-185">サインインのリスクが低、中、または高のときに MFA が必要 (Microsoft 365 E5 が必要)</span><span class="sxs-lookup"><span data-stu-id="ac542-185">Require MFA when sign-in risk is low, medium, or high (requires Microsoft 365 E5)</span></span> | <span data-ttu-id="ac542-186">機密</span><span class="sxs-lookup"><span data-stu-id="ac542-186">SENSITIVE</span></span> |
| <span data-ttu-id="ac542-187">常に MFA が必要</span><span class="sxs-lookup"><span data-stu-id="ac542-187">Always require MFA</span></span> | <span data-ttu-id="ac542-188">厳しく規制</span><span class="sxs-lookup"><span data-stu-id="ac542-188">HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="ac542-189">iOS と Android のデバイスで承認済みアプリが必要</span><span class="sxs-lookup"><span data-stu-id="ac542-189">Require approved apps on iOS and Android devices</span></span> | <span data-ttu-id="ac542-190">ベースライン、機密、厳しく規制</span><span class="sxs-lookup"><span data-stu-id="ac542-190">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="ac542-191">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="ac542-191">Require compliant PCs</span></span> | <span data-ttu-id="ac542-192">ベースライン</span><span class="sxs-lookup"><span data-stu-id="ac542-192">BASELINE</span></span> |
| <span data-ttu-id="ac542-193">準拠している PC、および iOS と Android のデバイスが必要</span><span class="sxs-lookup"><span data-stu-id="ac542-193">Require compliant PCs and iOS and Android devices</span></span> | <span data-ttu-id="ac542-194">機密、厳しく規制</span><span class="sxs-lookup"><span data-stu-id="ac542-194">SENSITIVE, HIGHLY-REGULATED</span></span> |
|||

<span data-ttu-id="ac542-195">以下は、作成して有効にする必要がある Azure AD Identity Protection (Microsoft 365 E5 が必要です) のユーザー リスク ポリシーです。</span><span class="sxs-lookup"><span data-stu-id="ac542-195">Here is the Azure AD Identity Protection (requires Microsoft 365 E5) user risk policy to create and enable.</span></span>

| <span data-ttu-id="ac542-196">Azure AD Identity Protection ユーザーのリスク ポリシー</span><span class="sxs-lookup"><span data-stu-id="ac542-196">Azure AD Identity Protection user risk policy</span></span> | <span data-ttu-id="ac542-197">適用対象のグループ</span><span class="sxs-lookup"><span data-stu-id="ac542-197">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="ac542-198">高リスク ユーザーはパスワードを変更する必要がある</span><span class="sxs-lookup"><span data-stu-id="ac542-198">High risk users must change passwords</span></span> | <span data-ttu-id="ac542-199">ポリシー設定で [すべてのユーザー] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ac542-199">Select "All users" in the policy settings.</span></span> |
|||

<span data-ttu-id="ac542-200">手順については、「[共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-200">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="groups-for-easier-management"></a><span data-ttu-id="ac542-201">管理を容易にするためのグループ</span><span class="sxs-lookup"><span data-stu-id="ac542-201">Groups for easier management</span></span>

<span data-ttu-id="ac542-202">以下は、グループとライセンスの管理をより簡単にするための機能の一部です。</span><span class="sxs-lookup"><span data-stu-id="ac542-202">Here are some features that can make group and licensing management easier for you.</span></span>

| <span data-ttu-id="ac542-203">機能</span><span class="sxs-lookup"><span data-stu-id="ac542-203">Feature</span></span> | <span data-ttu-id="ac542-204">使用法</span><span class="sxs-lookup"><span data-stu-id="ac542-204">Use</span></span> |
|:------|:-----|
| <span data-ttu-id="ac542-205">セルフサービスによるグループの管理</span><span class="sxs-lookup"><span data-stu-id="ac542-205">Self-service group management</span></span> | <span data-ttu-id="ac542-206">IT スタッフではなく、グループの所有者が Azure AD グループを管理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ac542-206">Allow management of Azure AD groups by group owners instead of IT staff.</span></span> <span data-ttu-id="ac542-207">詳細については、「[セルフサービスによるグループの管理](identity-use-group-management.md#allow-users-to-create-and-manage-their-own-groups)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-207">See [Self-service group management](identity-use-group-management.md#allow-users-to-create-and-manage-their-own-groups) for more information.</span></span> |
| <span data-ttu-id="ac542-208">動的グループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="ac542-208">Dynamic group membership</span></span> | <span data-ttu-id="ac542-209">部署や国などのユーザー アカウントの属性に基づいて、Azure AD グループに対するユーザー アカウントの自動追加または自動削除を構成します。</span><span class="sxs-lookup"><span data-stu-id="ac542-209">Configure automatic addition or removal of user accounts from Azure AD groups based on user account attributes, such as Department or Country.</span></span> <span data-ttu-id="ac542-210">詳細については、「[動的グループ メンバーシップ](identity-use-group-management.md#set-up-dynamic-group-membership)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-210">See [Dynamic group membership](identity-use-group-management.md#set-up-dynamic-group-membership) for more information.</span></span> |
| <span data-ttu-id="ac542-211">グループベースのライセンス</span><span class="sxs-lookup"><span data-stu-id="ac542-211">Group-based licensing</span></span> | <span data-ttu-id="ac542-212">グループ メンバーシップを使用して、ユーザー アカウントに対して自動的にライセンスの割り当てまたは割り当て解除を行います。</span><span class="sxs-lookup"><span data-stu-id="ac542-212">Use group membership to automatically assign or unassign licenses to user accounts.</span></span> <span data-ttu-id="ac542-213">詳細については、「[グループベースのライセンス](identity-use-group-management.md#set-up-automatic-licensing)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-213">See [Group-based licensing](identity-use-group-management.md#set-up-automatic-licensing) for more information.</span></span> |
|  |  |

<span data-ttu-id="ac542-214">グループベースのライセンスを使用している場合は、LICENSED という名前のグループを作成して、エンタープライズ向け Microsoft 365 ライセンスが割り当てられているユーザー アカウント名を含めます。</span><span class="sxs-lookup"><span data-stu-id="ac542-214">If you are using group-based licensing, create a group named LICENSED to contain user account names that are assigned a Microsoft 365 for enterprise license.</span></span>

### <a name="monitor-user-access"></a><span data-ttu-id="ac542-215">ユーザー アクセスの監視</span><span class="sxs-lookup"><span data-stu-id="ac542-215">Monitor user access</span></span>

<span data-ttu-id="ac542-216">Microsoft 365 E5 を利用している場合は、Azure AD Identity Protection を使用して、資格情報の侵害についてユーザーのサインインを監視および分析できます。</span><span class="sxs-lookup"><span data-stu-id="ac542-216">If you have Microsoft 365 E5, you can use Azure AD Identity Protection to monitor and analyze user sign-ins for credential compromise.</span></span> <span data-ttu-id="ac542-217">詳細については、「[資格情報が侵害されないように保護する](identity-secure-user-sign-ins.md#protect-against-credential-compromise)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-217">See [Protect against credential compromise](identity-secure-user-sign-ins.md#protect-against-credential-compromise) for more information.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="ac542-218">これまでの構成</span><span class="sxs-lookup"><span data-stu-id="ac542-218">Your configuration so far</span></span>

<span data-ttu-id="ac542-219">以下は、既存の要素と新しい要素に注目して、ハイブリッド ID の ID フェーズの概要を視覚的に示したものです。</span><span class="sxs-lookup"><span data-stu-id="ac542-219">Here is a visual summary of the Identity phase for hybrid identity, with existing and new elements highlighted.</span></span>

![ハイブリッド ID の ID フェーズ後の組織](../media/deploy-foundation-infrastructure-non-enterprises/identity-config.png)
 
<span data-ttu-id="ac542-221">新しく取り上げたハイブリッド ID の要素には次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="ac542-221">The new and highlighted hybrid identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![ユーザーのアカウントとグループを含むオンプレミスの AD DS ドメイン](../media/deploy-foundation-infrastructure-non-enterprises/identity-adds.png) | <span data-ttu-id="ac542-223">ユーザーのアカウントとグループを含むオンプレミスの AD DS ドメイン。</span><span class="sxs-lookup"><span data-stu-id="ac542-223">An on-premises AD DS domain with user accounts and groups.</span></span> |
| ![Azure AD Connect を実行している Windows ベースのサーバー](../media/deploy-foundation-infrastructure-non-enterprises/identity-aadconnect.png) | <span data-ttu-id="ac542-225">Azure AD Connect を実行している Windows ベースのサーバー。</span><span class="sxs-lookup"><span data-stu-id="ac542-225">A Windows-based server running Azure AD Connect.</span></span> |
| ![Azure AD 内の AD DS のユーザー アカウントとグループの同期セット](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts.png) | <span data-ttu-id="ac542-227">Azure AD 内の AD DS のユーザー アカウントとグループの同期セット。</span><span class="sxs-lookup"><span data-stu-id="ac542-227">The synchronized set of AD DS user accounts and groups in Azure AD.</span></span> |
| ![認証、グローバル アカウントのセキュリティ保護、グループとライセンスの管理の簡易化を行うための Azure AD 設定](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="ac542-229">認証、グローバル アカウントのセキュリティ保護、グループとライセンスの管理の簡易化を行うための Azure AD 設定。</span><span class="sxs-lookup"><span data-stu-id="ac542-229">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![Azure AD 条件付きアクセス ポリシー](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="ac542-231">Azure AD 条件付きアクセス ポリシー。</span><span class="sxs-lookup"><span data-stu-id="ac542-231">Azure AD Conditional Access policies.</span></span> |
|||

<span data-ttu-id="ac542-232">以下は、新しい要素に注目して、クラウド専用 ID の ID フェーズの概要を視覚的に示したものです。</span><span class="sxs-lookup"><span data-stu-id="ac542-232">Here is a visual summary of the Identity phase for cloud-only identity, with the new elements highlighted.</span></span>

![クラウド専用 ID の ID フェーズ後の組織](../media/deploy-foundation-infrastructure-non-enterprises/identity-config-cloud-only.png)
 
<span data-ttu-id="ac542-234">新しく取り上げたクラウド専用 ID の要素には次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="ac542-234">The new and highlighted cloud-only identity elements include:</span></span>
 
|||
|:------:|:-----|
| ![Azure AD のユーザー アカウントとグループ](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-accounts-cloud-only.png) | <span data-ttu-id="ac542-236">Azure AD のユーザー アカウントとグループ。</span><span class="sxs-lookup"><span data-stu-id="ac542-236">The user accounts and groups in Azure AD.</span></span> |
| ![認証、グローバル アカウントのセキュリティ保護、グループとライセンスの管理の簡易化を行うための Azure AD 設定](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-settings.png) | <span data-ttu-id="ac542-238">認証、グローバル アカウントのセキュリティ保護、グループとライセンスの管理の簡易化を行うための Azure AD 設定。</span><span class="sxs-lookup"><span data-stu-id="ac542-238">Azure AD settings for authentication, securing global accounts, and making it easier to manage groups and licenses.</span></span> |
| ![Azure AD 条件付きアクセス ポリシー](../media/deploy-foundation-infrastructure-non-enterprises/identity-aad-caps.png) | <span data-ttu-id="ac542-240">Azure AD 条件付きアクセス ポリシー。</span><span class="sxs-lookup"><span data-stu-id="ac542-240">Azure AD Conditional Access policies.</span></span> |
|||

## <a name="phase-3-windows-10-enterprise"></a><span data-ttu-id="ac542-241">フェーズ 3: Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ac542-241">Phase 3: Windows 10 Enterprise</span></span>

<span data-ttu-id="ac542-242">お使いの Windows 10 Enterprise デバイスをエンタープライズ向け Microsoft 365 の ID とセキュリティのインフラストラクチャに確実に統合する方法として、以下のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ac542-242">To ensure that your Windows 10 Enterprise devices are integrated into the identity and security infrastructure of Microsoft 365 for enterprise, here are your options:</span></span>

- <span data-ttu-id="ac542-243">ハイブリッド (オンプレミスの AD DS ドメインがある場合)</span><span class="sxs-lookup"><span data-stu-id="ac542-243">Hybrid (you have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="ac542-244">既に AD DS ドメインに参加している既存の Windows 10 Enterprise デバイスの場合は、各デバイスを Azure AD テナントに参加させます。</span><span class="sxs-lookup"><span data-stu-id="ac542-244">For each existing Windows 10 Enterprise device already joined to your AD DS domain, join them to the Azure AD tenant.</span></span> <span data-ttu-id="ac542-245">詳細については、「[ハイブリッド Azure Active Directory 参加済みデバイスの構成方法](https://go.microsoft.com/fwlink/p/?linkid=872870)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-245">See [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870) for the instructions.</span></span>

  <span data-ttu-id="ac542-246">Windows 10 Enterprise の新しいデバイスの場合は、各デバイスを AD DS ドメインに参加させてから、Azure AD テナントに参加させます。</span><span class="sxs-lookup"><span data-stu-id="ac542-246">For each new Windows 10 Enterprise device, join them to your AD DS domain, and then join them to the Azure AD tenant.</span></span>

  <span data-ttu-id="ac542-247">Windows 10 Enterprise デバイスは、各デバイスをモバイル デバイスの管理用に登録します。</span><span class="sxs-lookup"><span data-stu-id="ac542-247">For each Windows 10 Enterprise device, enroll them for mobile device management.</span></span> <span data-ttu-id="ac542-248">手順については、「[グループ ポリシーを使用して Intune に Windows 10 デバイスを登録する](https://go.microsoft.com/fwlink/p/?linkid=872871)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-248">See [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for the instructions.</span></span>

- <span data-ttu-id="ac542-249">クラウド専用 (オンプレミスの AD DS ドメインがない場合)</span><span class="sxs-lookup"><span data-stu-id="ac542-249">Cloud-only (you do not have an on-premises AD DS domain)</span></span>

  <span data-ttu-id="ac542-250">Windows 10 Enterprise の各デバイスをサブスクリプションの Azure AD テナントに参加させます。</span><span class="sxs-lookup"><span data-stu-id="ac542-250">Join each Windows 10 Enterprise device to the Azure AD tenant of your subscription.</span></span>

  <span data-ttu-id="ac542-251">詳細については、「[職場のデバイスを組織のネットワークに参加させる](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-251">See [Join your work device to your organization's network](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) for more information.</span></span>


<span data-ttu-id="ac542-252">インストールして参加させると、Windows 10 Enterprise の各デバイスには、Windows Update for Business クラウド サービスから更新プログラムが自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ac542-252">Once installed and joined, each Windows 10 Enterprise device automatically installs updates from the Windows Update for Business cloud service.</span></span> <span data-ttu-id="ac542-253">通常、エンタープライズ以外の組織では、Windows 10 更新プログラムの配布やインストール用にインフラストラクチャをセットアップする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ac542-253">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute and install Windows 10 updates.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="ac542-254">これまでの構成</span><span class="sxs-lookup"><span data-stu-id="ac542-254">Your configuration so far</span></span>

<span data-ttu-id="ac542-255">以下は、新しい要素に注目して、Windows 10 Enterprise フェーズの概要を視覚的に示したものです。</span><span class="sxs-lookup"><span data-stu-id="ac542-255">Here is a visual summary of the Windows 10 Enterprise phase with the new elements highlighted.</span></span>

![Windows 10 Enterprise フェーズ後の組織](../media/deploy-foundation-infrastructure-non-enterprises/win10-config.png)
 
<span data-ttu-id="ac542-257">新しく取り上げた Windows 10 Enterprise の要素には次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="ac542-257">The new and highlighted Windows 10 Enterprise elements include:</span></span>

|||
|:------:|:-----|
| ![Windows デバイスにインストールされている Windows 10 Enterprise](../media/deploy-foundation-infrastructure-non-enterprises/win10-device.png) | <span data-ttu-id="ac542-259">Windows デバイスにインストールされている Windows 10 Enterprise (例として、オンプレミスのノート PC を表示)。</span><span class="sxs-lookup"><span data-stu-id="ac542-259">Windows 10 Enterprise installed on Windows devices, with an on-premises laptop as an example.</span></span> |
| ![ボリューム ライセンス サービス センター](../media/deploy-foundation-infrastructure-non-enterprises/win10-cloud.png) | <span data-ttu-id="ac542-261">Windows 10 Enterprise の新規インストール用のイメージが用意されているボリューム ライセンス サービス センター、および最新の更新プログラムを提供する Windows Update for Business サービス。</span><span class="sxs-lookup"><span data-stu-id="ac542-261">The Volume Licensing Service Center, which provides images for new installations of Windows 10 Enterprise, and the Windows Update for Business service, which provides the latest updates.</span></span> |
|||

## <a name="phase-4-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="ac542-262">フェーズ 4: Microsoft 365 Apps for enterprise</span><span class="sxs-lookup"><span data-stu-id="ac542-262">Phase 4: Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="ac542-263">エンタープライズ向け Microsoft 365 には、Microsoft Office のサブスクリプション版である Microsoft 365 Apps for enterprise が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ac542-263">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, the subscription version of Microsoft Office.</span></span> <span data-ttu-id="ac542-264">Office 2016 または Office 2019 と同様に、Microsoft 365 Apps for enterprise はクライアント デバイスに直接インストールされます。</span><span class="sxs-lookup"><span data-stu-id="ac542-264">Like Office 2016 or Office 2019, Microsoft 365 Apps for enterprise is installed directly on your client devices.</span></span> <span data-ttu-id="ac542-265">ただし、Microsoft 365 Apps for enterprise には、新機能を含む更新プログラムが定期的に提供されます。</span><span class="sxs-lookup"><span data-stu-id="ac542-265">However, Microsoft 365 Apps for enterprise receives updates that include new features on a regular basis.</span></span> <span data-ttu-id="ac542-266">詳細については、[企業向けのMicrosoft 365 Apps for enterprise について](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-266">See [About Microsoft 365 Apps for enterprise in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) for more information.</span></span>

<span data-ttu-id="ac542-267">エンタープライズ以外の組織の場合は、 Microsoft 365 Apps for enterprise を Windows、iOS、Android デバイスを含むデバイスに手動でインストールします。</span><span class="sxs-lookup"><span data-stu-id="ac542-267">For your non-enterprise organization, you manually install Microsoft 365 Apps for enterprise on devices, which can include Windows, iOS, and Android devices.</span></span> <span data-ttu-id="ac542-268">これは、新しいデバイスを使用する準備の一環として実行することも、ユーザーがオンボード プロセスの一環として実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="ac542-268">This can be done as part of preparing a new device for use, or by the user as part of their onboarding process.</span></span>

<span data-ttu-id="ac542-269">いずれの場合でも、管理者またはユーザーは https://portal.office.com で Office 365 ポータルにサインインします。</span><span class="sxs-lookup"><span data-stu-id="ac542-269">In either case, the administrator or the user signs in to the Office 365 portal at https://portal.office.com.</span></span> <span data-ttu-id="ac542-270">**[Microsoft Office Home]** タブで、**[Office のインストール]** をクリックして、インストール プロセスを進めます。</span><span class="sxs-lookup"><span data-stu-id="ac542-270">On the **Microsoft Office Home** tab, click **Install Office** and step through the installation process.</span></span>

<span data-ttu-id="ac542-271">Microsoft 365 Apps for enterprise に対する機能更新プログラムは、インストールされているコンピューターごとに毎月ダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="ac542-271">Feature updates to Microsoft 365 Apps for enterprise are downloaded monthly by each computer on which it is installed.</span></span> <span data-ttu-id="ac542-272">通常、エンタープライズ以外の組織では、Microsoft 365 Apps for enterprise 更新プログラムの配布用にインフラストラクチャをセットアップする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ac542-272">There is typically no need in a non-enterprise organization to set up an infrastructure to distribute Microsoft 365 Apps for enterprise updates.</span></span> 

### <a name="your-configuration-so-far"></a><span data-ttu-id="ac542-273">これまでの構成</span><span class="sxs-lookup"><span data-stu-id="ac542-273">Your configuration so far</span></span>

<span data-ttu-id="ac542-274">以下は、新しい要素に注目して、Microsoft 365 Apps for enterprise フェーズの概要を視覚的に示したものです。</span><span class="sxs-lookup"><span data-stu-id="ac542-274">Here is a visual summary of the Microsoft 365 Apps for enterprise phase with the new elements highlighted.</span></span>

![Microsoft 365 Apps for enterprise フェーズ以降の組織](../media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-config.png)
 
<span data-ttu-id="ac542-276">新しく取り上げた Microsoft 365 Apps for enterprise の要素には次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="ac542-276">The new and highlighted Microsoft 365 Apps for enterprise elements include:</span></span>
 
|||
|:------:|:-----|
| ![デバイスにインストールされている Microsoft 365 Apps for enterprise ](../media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-device.png) | <span data-ttu-id="ac542-278">デバイスにインストールされているMicrosoft 365 Apps for enterprise (例として、オンプレミスのノート PC を表示)。</span><span class="sxs-lookup"><span data-stu-id="ac542-278">Microsoft 365 Apps for enterprise installed on devices, with an on-premises laptop as an example.</span></span> |
| ![Microsoft 365 Apps for enterprise 用の Office コンテンツ配信ネットワーク (CDN)](../media/deploy-foundation-infrastructure-non-enterprises/o365-proplus-cdn.png) | <span data-ttu-id="ac542-280">Microsoft 365 Apps for enterprise 用の Office コンテンツ配信ネットワーク (CDN)。デバイスはMicrosoft 365 Apps for enterprise 更新プログラムにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="ac542-280">The Office Content Delivery Network (CDN) for Microsoft 365 Apps for enterprise, which devices access for Microsoft 365 Apps for enterprise updates.</span></span> |
|||

## <a name="phase-5-mobile-device-management"></a><span data-ttu-id="ac542-281">フェーズ 5: モバイル デバイス管理</span><span class="sxs-lookup"><span data-stu-id="ac542-281">Phase 5: Mobile device management</span></span>

<span data-ttu-id="ac542-282">エンタープライズ向け Microsoft 365 には、モバイル デバイス管理用の Microsoft Intune が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ac542-282">Microsoft 365 for enterprise includes Microsoft Intune for mobile device management.</span></span> <span data-ttu-id="ac542-283">Intune を使用すると、Windows、iOS、Android、macOS の各デバイスを管理して、自分のデータを含む、組織のリソースへのアクセスを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="ac542-283">With Intune, you can manage Windows, iOS, Android, and macOS devices to protect access to your organization's resources, including your data.</span></span> <span data-ttu-id="ac542-284">Intune では、Azure AD のユーザー、グループ、コンピューター アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="ac542-284">Intune uses the user, group, and computer accounts of Azure AD.</span></span>

<span data-ttu-id="ac542-285">Intune には、次の 2 種類のモバイル デバイス管理が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ac542-285">Intune provides two types of mobile device management:</span></span>

- <span data-ttu-id="ac542-286">モバイル デバイス管理 (MDM) は、デバイスが Intune に登録された時点から行われます。</span><span class="sxs-lookup"><span data-stu-id="ac542-286">Mobile device management (MDM) is when devices get enrolled in Intune.</span></span> <span data-ttu-id="ac542-287">登録されると、デバイスはマネージド デバイスとなり、組織で使用されているポリシー、ルール、設定を受信できます。</span><span class="sxs-lookup"><span data-stu-id="ac542-287">Once enrolled, they are managed devices and can receive the policies, rules, and settings used by your organization.</span></span> <span data-ttu-id="ac542-288">これらの種類のデバイスは、通常、組織が所有し、従業員に支給されます。</span><span class="sxs-lookup"><span data-stu-id="ac542-288">These types of devices are typically owned by your organization and issued to your employees.</span></span>

- <span data-ttu-id="ac542-289">自分の個人用デバイスを使用しているユーザーの中には、自分のデバイスを登録したり、ポリシーや設定を使用して Intune で管理したりすることを望まないユーザーもいます。</span><span class="sxs-lookup"><span data-stu-id="ac542-289">Users with their own personal devices may not want to enroll their devices or be managed by Intune with your policies and settings.</span></span> <span data-ttu-id="ac542-290">しかし、そうであっても、組織のリソースとデータを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac542-290">However, you still need to protect your organization's resources and data.</span></span> <span data-ttu-id="ac542-291">このような場合は、モバイル アプリケーション管理 (MAM) を使用して、アプリを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="ac542-291">For this scenario, you can protect your apps with mobile application management (MAM).</span></span>  

<span data-ttu-id="ac542-292">Intune ポリシーでは、デバイス コンプライアンスとアプリ保護を適用できます。</span><span class="sxs-lookup"><span data-stu-id="ac542-292">Intune policies can enforce device compliance and app protection.</span></span> <span data-ttu-id="ac542-293">以下は、作成する Intune ポリシーの一覧です。</span><span class="sxs-lookup"><span data-stu-id="ac542-293">Here is the list of Intune policies to create.</span></span>

| <span data-ttu-id="ac542-294">Intune ポリシー</span><span class="sxs-lookup"><span data-stu-id="ac542-294">Intune policies</span></span> | <span data-ttu-id="ac542-295">適用対象のグループ</span><span class="sxs-lookup"><span data-stu-id="ac542-295">Groups to which it applies</span></span> |
|:------|:-----|
| <span data-ttu-id="ac542-296">Windows 用のデバイス コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="ac542-296">Device compliance policy for Windows</span></span> | <span data-ttu-id="ac542-297">ベースライン、機密、厳しく規制</span><span class="sxs-lookup"><span data-stu-id="ac542-297">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="ac542-298">iOS 用のデバイス コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="ac542-298">Device compliance policy for iOS</span></span> | <span data-ttu-id="ac542-299">機密、厳しく規制</span><span class="sxs-lookup"><span data-stu-id="ac542-299">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="ac542-300">macOS 用のデバイス コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="ac542-300">Device compliance for macOS</span></span> | <span data-ttu-id="ac542-301">機密、厳しく規制</span><span class="sxs-lookup"><span data-stu-id="ac542-301">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="ac542-302">Android と Android Enterprise 用のデバイス コンプライアンス ポリシー</span><span class="sxs-lookup"><span data-stu-id="ac542-302">Device compliance policy for Android and Android Enterprise</span></span> | <span data-ttu-id="ac542-303">機密、厳しく規制</span><span class="sxs-lookup"><span data-stu-id="ac542-303">SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="ac542-304">iOS 用のアプリ保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="ac542-304">App protection policy for iOS</span></span> | <span data-ttu-id="ac542-305">ベースライン、機密、厳しく規制</span><span class="sxs-lookup"><span data-stu-id="ac542-305">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="ac542-306">macOS 用のアプリ保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="ac542-306">App protection policy for macOS</span></span> | <span data-ttu-id="ac542-307">ベースライン、機密、厳しく規制</span><span class="sxs-lookup"><span data-stu-id="ac542-307">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
| <span data-ttu-id="ac542-308">Android と Android Enterprise 用のアプリ保護ポリシー</span><span class="sxs-lookup"><span data-stu-id="ac542-308">App protection policy for Android and Android Enterprise</span></span> | <span data-ttu-id="ac542-309">ベースライン、機密、厳しく規制</span><span class="sxs-lookup"><span data-stu-id="ac542-309">BASELINE, SENSITIVE, HIGHLY-REGULATED</span></span> |
|||
    
<span data-ttu-id="ac542-310">手順については、「[共通 ID とデバイスのアクセス ポリシー](identity-access-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-310">See [Common identity and device access policies](identity-access-policies.md) for the instructions.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="ac542-311">これまでの構成</span><span class="sxs-lookup"><span data-stu-id="ac542-311">Your configuration so far</span></span>

<span data-ttu-id="ac542-312">以下は、新しい要素に注目して、モバイル デバイス管理フェーズの概要を視覚的に示したものです。</span><span class="sxs-lookup"><span data-stu-id="ac542-312">Here is a visual summary of the Mobile Device Management phase with the new elements highlighted.</span></span>

![モバイル デバイス管理フェーズ後の組織](../media/deploy-foundation-infrastructure-non-enterprises/mdm-config.png)
 
<span data-ttu-id="ac542-314">新しく取り上げたモバイル デバイス管理の要素には次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="ac542-314">The new and highlighted mobile device management elements include:</span></span>

|||
|:------:|:-----|
| ![Intune に登録されているデバイス](../media/deploy-foundation-infrastructure-non-enterprises/mdm-device.png) | <span data-ttu-id="ac542-316">Intune に登録されているデバイス (例として、Windows 10 Enterprise を実行しているオンプレミスのノート PC を表示)。</span><span class="sxs-lookup"><span data-stu-id="ac542-316">Devices that are enrolled in Intune, showing an on-premises laptop running Windows 10 Enterprise as an example.</span></span> |
| ![デバイス コンプライアンスとアプリ保護のための Intune ポリシー](../media/deploy-foundation-infrastructure-non-enterprises/mdm-policies.png) | <span data-ttu-id="ac542-318">デバイス コンプライアンスとアプリ保護のための Intune ポリシー。</span><span class="sxs-lookup"><span data-stu-id="ac542-318">Intune policies for device compliance and app protection.</span></span> |
|||

## <a name="phase-6-information-protection"></a><span data-ttu-id="ac542-319">フェーズ 6: 情報保護</span><span class="sxs-lookup"><span data-stu-id="ac542-319">Phase 6: Information protection</span></span>

<span data-ttu-id="ac542-320">エンタープライズ向け Microsoft 365 には情報保護機能が備わっており、異なるレベルのガバナンス、セキュリティ、保護を適用することによって、データの分類を異なる方法で処理することが可能です。</span><span class="sxs-lookup"><span data-stu-id="ac542-320">Microsoft 365 for enterprise has a host of information protection features that allow you to treat classifications of data differently by applying different levels of governance, security, and protection.</span></span> 

<span data-ttu-id="ac542-321">たとえば、ほとんどの従業員とその従業員が作業しているドキュメント間における通常の通信には、一定のベースライン レベルの保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="ac542-321">For example, normal correspondence between most employees and the documents on which they work need a certain baseline level of protection.</span></span> <span data-ttu-id="ac542-322">財務レコード、顧客データ、知的財産には、より高いレベルの保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="ac542-322">Financial records, customer data, and your intellectual property need a higher level of protection.</span></span>

<span data-ttu-id="ac542-323">情報保護戦略の第一歩は、保護レベルを決定することです。</span><span class="sxs-lookup"><span data-stu-id="ac542-323">The first step to an information protection strategy is to determine the levels of protection.</span></span> <span data-ttu-id="ac542-324">多くの組織では以下のレベルが使用されています。これらは既に条件付きアクセス ポリシーに使用されています。</span><span class="sxs-lookup"><span data-stu-id="ac542-324">Many organizations use these levels, which are already being used for Conditional Access policies:</span></span>

- <span data-ttu-id="ac542-325">ベースライン</span><span class="sxs-lookup"><span data-stu-id="ac542-325">Baseline</span></span>

  <span data-ttu-id="ac542-326">通常のビジネス通信 (電子メール) や、管理、営業、サポートの各担当者用のファイルなどがあります。</span><span class="sxs-lookup"><span data-stu-id="ac542-326">Examples include normal business communications (email) and files for administrative, sales, and support workers.</span></span>

- <span data-ttu-id="ac542-327">機密</span><span class="sxs-lookup"><span data-stu-id="ac542-327">Sensitive</span></span>

  <span data-ttu-id="ac542-328">財務情報や法的情報、新しい製品やサービスに関する研究開発データなどがあります。</span><span class="sxs-lookup"><span data-stu-id="ac542-328">Examples include financial and legal information and research and development data for new products or services.</span></span>

- <span data-ttu-id="ac542-329">高度な規制</span><span class="sxs-lookup"><span data-stu-id="ac542-329">Highly regulated</span></span>

  <span data-ttu-id="ac542-330">顧客やパートナーの個人を特定できる情報、組織の戦略計画または知的財産などがあります。</span><span class="sxs-lookup"><span data-stu-id="ac542-330">Examples include customer and partner personally identifiable information and your organization's strategic plans or intellectual property.</span></span>

<span data-ttu-id="ac542-331">次の手順では、これらのレベルのデータ セキュリティに基づいて、以下を特定して実装します。</span><span class="sxs-lookup"><span data-stu-id="ac542-331">Based on these levels of data security, the next step is to identify and implement:</span></span>

- <span data-ttu-id="ac542-332">カスタムの機密情報の種類</span><span class="sxs-lookup"><span data-stu-id="ac542-332">Custom sensitive information types</span></span>

  <span data-ttu-id="ac542-333">Microsoft 365 では、医療サービスやクレジット カード番号など、さまざまな機密情報の種類を提供しています。</span><span class="sxs-lookup"><span data-stu-id="ac542-333">Microsoft 365 supplies a wide selection of sensitive information types, such as health service and credit card numbers.</span></span> <span data-ttu-id="ac542-334">提供される項目の一覧に必要なものが見つからない場合は、独自に作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ac542-334">If you do not find one that you need in the supplied list, you can create your own.</span></span>

- <span data-ttu-id="ac542-335">保持ラベル</span><span class="sxs-lookup"><span data-stu-id="ac542-335">Retention labels</span></span>

  <span data-ttu-id="ac542-336">組織のポリシーと地域の規制に準拠するには、必要に応じて、特定の種類のドキュメントまたは特定のコンテンツを含むドキュメントを保持する期間を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac542-336">To comply with organization policies and regional regulations, you might have to specify how long specific types of documents or documents with specific contents should be retained.</span></span> <span data-ttu-id="ac542-337">これは、保持ラベルを使用して電子メールとドキュメントに実装できます。</span><span class="sxs-lookup"><span data-stu-id="ac542-337">You can implement this for email and documents using retention labels.</span></span> <span data-ttu-id="ac542-338">保持ラベルは、組織外のファイルまたは電子メールの共有を制限できるデータ損失防止 (DLP) ポリシーと組み合わせて使用​​することもできます。</span><span class="sxs-lookup"><span data-stu-id="ac542-338">Retention labels can also be used in conjunction with Data Loss Prevention (DLP) policies that can restrict the sharing of files or email outside your organization.</span></span>

- <span data-ttu-id="ac542-339">機密度ラベル</span><span class="sxs-lookup"><span data-stu-id="ac542-339">Sensitivity labels</span></span>

  <span data-ttu-id="ac542-340">追加のセキュリティ レベルを適用できるように、名前付きの機密度ラベルを使用して、電子メールやドキュメントにラベルを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="ac542-340">You can label email or documents with a named sensitivity label so that additional levels of security can be applied.</span></span> <span data-ttu-id="ac542-341">例としては、透かし、暗号化、アクセス許可などがあります。これらを使用して、電子メールまたはドキュメントへのアクセスを許可されているユーザーとそのユーザーの許可されている操作を指定します。</span><span class="sxs-lookup"><span data-stu-id="ac542-341">Examples are watermarks, encryption, and permissions, which specify who is allowed to access the email or document and what they are allowed to do.</span></span>

<span data-ttu-id="ac542-342">詳細については、「[Microsoft 365 の分類の種類](infoprotect-configure-classification.md#microsoft-365-classification-types)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ac542-342">See [Microsoft 365 classification types](infoprotect-configure-classification.md#microsoft-365-classification-types) for more information.</span></span>

<span data-ttu-id="ac542-343">アクセス許可の機密度ラベルを使用する場合は、追加のセキュリティ グループを作成して、機密度ラベルが適用された電子メールとドキュメントに対してどのような操作を誰に許可するのかを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac542-343">If you use sensitivity labels with permissions, you might have to create additional security groups to define who is allowed to do what with email and documents that have the sensitivity label applied.</span></span> 

<span data-ttu-id="ac542-344">たとえば、リサーチ チームの電子メールとドキュメントを保護するには、「リサーチ」という機密度ラベルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac542-344">For example, you need to create a RESEARCH sensitivity label to protect the email and documents of your research team.</span></span> <span data-ttu-id="ac542-345">以下を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac542-345">You determine that:</span></span>

- <span data-ttu-id="ac542-346">リサーチを行う従業員は、機密度ラベル "リサーチ" が付けられたドキュメントを変更できなければならない。</span><span class="sxs-lookup"><span data-stu-id="ac542-346">Researchers must have the ability to change documents marked with the RESEARCH sensitivity label.</span></span>
- <span data-ttu-id="ac542-347">リサーチを行わない従業員に必要なのは、機密度ラベル "リサーチ" が付けられたドキュメントを表示する機能のみ。</span><span class="sxs-lookup"><span data-stu-id="ac542-347">Non-research employees only need to have the ability to view documents marked with the RESEARCH sensitivity label.</span></span> 

<span data-ttu-id="ac542-348">つまり、次の 2 つの Microsoft 365 グループを追加で作成して管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac542-348">This means you need to create and manage two additional Microsoft 365 groups:</span></span>

- <span data-ttu-id="ac542-349">リサーチ-すべて</span><span class="sxs-lookup"><span data-stu-id="ac542-349">RESEARCH-ALL</span></span>
- <span data-ttu-id="ac542-350">リサーチ-表示</span><span class="sxs-lookup"><span data-stu-id="ac542-350">RESEARCH-VIEW</span></span>

<span data-ttu-id="ac542-351">これらのグループとそのアクセス許可は、リサーチ機密度ラベルの構成の一部になります。</span><span class="sxs-lookup"><span data-stu-id="ac542-351">These groups and their permissions become part of the RESEARCH sensitivity label's configuration.</span></span>

<span data-ttu-id="ac542-352">グループベースのアクセス許可で構成された機密度ラベルの場合、これらのグループのメンバーシップを管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac542-352">For sensitivity labels configured with group-based permissions, you must manage the membership of these groups.</span></span>

### <a name="your-configuration-so-far"></a><span data-ttu-id="ac542-353">これまでの構成</span><span class="sxs-lookup"><span data-stu-id="ac542-353">Your configuration so far</span></span>

<span data-ttu-id="ac542-354">以下は、新しい要素に注目して、情報保護フェーズの概要を視覚的に示したものです。</span><span class="sxs-lookup"><span data-stu-id="ac542-354">Here is a visual summary of the Information Protection phase with the new elements highlighted.</span></span>

![情報保護フェーズ後の組織](../media/deploy-foundation-infrastructure-non-enterprises/info-protect-config.png)
 
<span data-ttu-id="ac542-356">新しく取り上げた情報保護の要素には次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="ac542-356">The new and highlighted information protection elements include:</span></span>
 
|||
|:------:|:-----|
| ![3 つのセキュリティ レベルの機密度ラベル。](../media/deploy-foundation-infrastructure-non-enterprises/info-protect-labels.png) | <span data-ttu-id="ac542-358">ユーザーがドキュメントと電子メールに適用できる 3 つのセキュリティ レベルの機密度ラベル。</span><span class="sxs-lookup"><span data-stu-id="ac542-358">Sensitivity labels for the three levels of security that users can apply to documents and email.</span></span> |
|||

<span data-ttu-id="ac542-359">カスタム情報の種類と保持ラベルは表示されません。</span><span class="sxs-lookup"><span data-stu-id="ac542-359">Custom information types and retention labels are not shown.</span></span>

## <a name="onboarding"></a><span data-ttu-id="ac542-360">オンボード</span><span class="sxs-lookup"><span data-stu-id="ac542-360">Onboarding</span></span>

<span data-ttu-id="ac542-361">エンタープライズ向け Microsoft 365 のインフラストラクチャがあれば、組織の従業員を簡単にオンボードすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac542-361">With your Microsoft 365 for enterprise infrastructure in place, you can easily onboard your employees.</span></span>

### <a name="a-new-windows-10-enterprise-device"></a><span data-ttu-id="ac542-362">新しい Windows 10 Enterprise デバイス</span><span class="sxs-lookup"><span data-stu-id="ac542-362">A new Windows 10 Enterprise device</span></span>

<span data-ttu-id="ac542-363">従業員に新しい Windows 10 Enterprise デバイスを提供する前に、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="ac542-363">Before giving an employee a new Windows 10 Enterprise device:</span></span>

- <span data-ttu-id="ac542-364">ハイブリッド ID の場合</span><span class="sxs-lookup"><span data-stu-id="ac542-364">For hybrid identity</span></span>

  <span data-ttu-id="ac542-365">デバイスを AD DS ドメイン、Azure AD テナントの順に参加させてから、Intune に登録します。</span><span class="sxs-lookup"><span data-stu-id="ac542-365">Join the device to your AD DS domain, join the device to your Azure AD tenant, and then enroll the device in Intune.</span></span>

- <span data-ttu-id="ac542-366">クラウド専用 ID の場合</span><span class="sxs-lookup"><span data-stu-id="ac542-366">For cloud-only identity</span></span>

  <span data-ttu-id="ac542-367">デバイスを Azure AD テナントに参加させます。</span><span class="sxs-lookup"><span data-stu-id="ac542-367">Join the device to your Azure AD tenant.</span></span>

### <a name="existing-employee-with-an-ad-ds-user-account"></a><span data-ttu-id="ac542-368">AD DS ユーザー アカウントを持っている既存の従業員</span><span class="sxs-lookup"><span data-stu-id="ac542-368">Existing employee with an AD DS user account</span></span>

<span data-ttu-id="ac542-369">ハイブリッド ID を使用する場合には、組織の初期のオンボードの一環として、次の Azure AD グループに AD DS ユーザー アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="ac542-369">As part of the initial onboarding for your organization when using hybrid identity, add the AD DS user account to these Azure AD groups:</span></span>

- <span data-ttu-id="ac542-370">ライセンス付与済み</span><span class="sxs-lookup"><span data-stu-id="ac542-370">LICENSED</span></span>
- <span data-ttu-id="ac542-371">ベースライン、機密、厳しく規制の各 Azure AD グループのメンバーである、適切な AD DS または Azure AD セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="ac542-371">The appropriate AD DS or Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="ac542-372">機密度ラベル グループ (必要な場合)</span><span class="sxs-lookup"><span data-stu-id="ac542-372">Sensitivity label groups (as needed)</span></span>

<span data-ttu-id="ac542-373">既存の従業員は、適切なワークグループ、部署、地域の AD DS グループに既に追加されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ac542-373">The existing employee should already be added to the appropriate workgroup, departmental, and regional AD DS groups.</span></span>

<span data-ttu-id="ac542-374">Microsoft 365 管理センターで、複数の Azure AD グループにユーザー アカウントを追加できます。</span><span class="sxs-lookup"><span data-stu-id="ac542-374">You can add a user account to multiple Azure AD groups in the Microsoft 365 admin center.</span></span> <span data-ttu-id="ac542-375">ユーザー アカウントのプロパティで、**[グループの管理] > [メンバーシップの追加]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ac542-375">From the properties of the user account, click **Manage groups > Add memberships**.</span></span>

<span data-ttu-id="ac542-376">Powershell を使用する場合は、この[ダウンロード可能な Excel ブック](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-foundation-infrastructure-non-enterprises/Group-License-Mgmt-PowerShell.xlsx)を参照してください。指定したユーザー アカウントと選択したグループ名に基づいて PowerShell コマンドが生成されます。</span><span class="sxs-lookup"><span data-stu-id="ac542-376">If you want to use PowerShell, see this [downloadable Excel workbook](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/deploy-foundation-infrastructure-non-enterprises/Group-License-Mgmt-PowerShell.xlsx), which generates the PowerShell commands based on a specified user account and selected group names.</span></span>

### <a name="new-employee-with-a-cloud-only-user-account"></a><span data-ttu-id="ac542-377">クラウド専用ユーザー アカウントを持っている新入社員</span><span class="sxs-lookup"><span data-stu-id="ac542-377">New employee with a cloud-only user account</span></span>

<span data-ttu-id="ac542-378">クラウド専用 ID を使用する場合には、組織の初期のオンボードの一環として、次のグループに新しいユーザー アカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="ac542-378">As part of the initial onboarding for your organization when using cloud-only identity, add the new user account to these groups:</span></span>

- <span data-ttu-id="ac542-379">ライセンス付与済み</span><span class="sxs-lookup"><span data-stu-id="ac542-379">LICENSED</span></span>
- <span data-ttu-id="ac542-380">ベースライン、機密、厳しく規制の各 Azure AD グループのメンバーである、適切な Azure AD セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="ac542-380">The appropriate Azure AD security groups that are members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span>
- <span data-ttu-id="ac542-381">ワークグループ、部署、地域の各グループ</span><span class="sxs-lookup"><span data-stu-id="ac542-381">Workgroup, departmental, and regional groups</span></span>
- <span data-ttu-id="ac542-382">機密度ラベル グループ (必要な場合)</span><span class="sxs-lookup"><span data-stu-id="ac542-382">Sensitivity label groups (as needed)</span></span>

### <a name="initial-sign-in-to-microsoft-365"></a><span data-ttu-id="ac542-383">Microsoft 365 への最初のサインイン</span><span class="sxs-lookup"><span data-stu-id="ac542-383">Initial sign-in to Microsoft 365</span></span>

<span data-ttu-id="ac542-384">従業員が初めて Microsoft 365 にサインインする場合は、以下を実施します。</span><span class="sxs-lookup"><span data-stu-id="ac542-384">For the first time employees sign in to Microsoft 365, instruct them to:</span></span>

1. <span data-ttu-id="ac542-385">ユーザー アカウントの資格情報を使用して、デバイスにサインインする。</span><span class="sxs-lookup"><span data-stu-id="ac542-385">Sign into their devices with their user account credentials.</span></span>
2. <span data-ttu-id="ac542-386">ブラウザーを使用して、https://portal.office.com で Office 365 ポータルにサインインする。</span><span class="sxs-lookup"><span data-stu-id="ac542-386">Using a browser, sign in to the Office 365 portal at https://portal.office.com.</span></span>
3. <span data-ttu-id="ac542-387">**[Office 365 Home]** タブから、**[Office のインストール]** をクリックして、デバイスにMicrosoft 365 Apps for enterprise をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ac542-387">From the **Office 365 Home** tab, click **Install Office** to install Microsoft 365 Apps for enterprise on their device.</span></span>

## <a name="end-results"></a><span data-ttu-id="ac542-388">最終的な結果</span><span class="sxs-lookup"><span data-stu-id="ac542-388">End results</span></span>

<span data-ttu-id="ac542-389">エンタープライズ向け Microsoft 365 の基礎インフラストラクチャを非エンタープライズ組織向けに構成すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ac542-389">Here are the results of configuring the Microsoft 365 for enterprise foundation infrastructure for your non-enterprise organization.</span></span>

### <a name="infrastructure-results"></a><span data-ttu-id="ac542-390">インフラストラクチャの結果</span><span class="sxs-lookup"><span data-stu-id="ac542-390">Infrastructure results</span></span>

<span data-ttu-id="ac542-391">エンタープライズ向け Microsoft 365 インフラストラクチャの構築および構成が完了すると、以下が装備されます。</span><span class="sxs-lookup"><span data-stu-id="ac542-391">After the build-out and configuration of your Microsoft 365 for enterprise infrastructure, you should have:</span></span>

- <span data-ttu-id="ac542-392">地域のローカル DNS サーバーを使用している ISP によって提供される十分な帯域幅を備えた、各オフィス用のローカル インターネット接続。</span><span class="sxs-lookup"><span data-stu-id="ac542-392">A local Internet connection for each of your offices with sufficient bandwidth supplied by an ISP that uses a regionally local DNS server.</span></span>
- <span data-ttu-id="ac542-393">ハイブリッド ID の場合は、オンプレミス AD DS ドメインと Azure AD テナントを同期するサーバーで実行される Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="ac542-393">For hybrid identity, Azure AD Connect running on a server that synchronizes your on-premises AD DS domain with your Azure AD tenant.</span></span>
- <span data-ttu-id="ac542-394">グループは以下の通りです。</span><span class="sxs-lookup"><span data-stu-id="ac542-394">These groups:</span></span>
  - <span data-ttu-id="ac542-395">ライセンス付与済み</span><span class="sxs-lookup"><span data-stu-id="ac542-395">LICENSED</span></span>
  - <span data-ttu-id="ac542-396">条件付きアクセスの除外</span><span class="sxs-lookup"><span data-stu-id="ac542-396">COND-ACCESS-EXCLUDE</span></span>
  - <span data-ttu-id="ac542-397">ベースライン、機密、厳しく規制の各 Azure AD グループのメンバーでもある、適切な AD DS または Azure AD セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="ac542-397">The appropriate AD DS or Azure AD security groups that are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups</span></span> 
  - <span data-ttu-id="ac542-398">ワークグループ、部署、地域の各グループ</span><span class="sxs-lookup"><span data-stu-id="ac542-398">Workgroup, departmental, and regional groups</span></span>
  - <span data-ttu-id="ac542-399">機密度ラベル Microsoft 365 グループ (必要な場合)</span><span class="sxs-lookup"><span data-stu-id="ac542-399">Sensitivity label Microsoft 365 groups (as needed)</span></span>
- <span data-ttu-id="ac542-400">ベースライン、機密、厳しく規制、条件付きアクセスの除外の各 Azure AD グループを使用する Azure AD サインイン条件付きアクセス ポリシー。</span><span class="sxs-lookup"><span data-stu-id="ac542-400">Azure AD sign-in Conditional Access policies that use the BASELINE, SENSITIVE, and HIGHLY-REGULATED, and COND-ACCESS-EXCLUDE Azure AD groups.</span></span>
- <span data-ttu-id="ac542-401">Intune アプリケーションとデバイスのコンプライアンス ポリシー。</span><span class="sxs-lookup"><span data-stu-id="ac542-401">Intune application and device compliance policies.</span></span>
- <span data-ttu-id="ac542-402">カスタムの機密情報の種類 (必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="ac542-402">Custom sensitive information types (as needed).</span></span>
- <span data-ttu-id="ac542-403">保持ラベル (必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="ac542-403">Retention labels (as needed).</span></span>
- <span data-ttu-id="ac542-404">機密度ラベル (必要な場合)。</span><span class="sxs-lookup"><span data-stu-id="ac542-404">Sensitivity labels (as needed).</span></span>

<span data-ttu-id="ac542-405">以下は、組織がハイブリッド ID を使用している場合のインフラストラクチャの概要を視覚的に示したものです。これには、AD DS ドメイン、Azure AD Connect サーバー、同期された AD DS のユーザーとグループが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ac542-405">Here is a visual summary of the infrastructure if your organization uses hybrid identity, which includes your AD DS domain, an Azure AD Connect server, and synchronized AD DS users and groups.</span></span>

![組織がハイブリッド ID を使用している場合のインフラストラクチャの概要](../media/deploy-foundation-infrastructure-non-enterprises/final-hybrid-config.png)
 
<span data-ttu-id="ac542-407">以下は、組織がクラウド専用の ID を使用している場合のインフラストラクチャの概要を視覚的に示したものです。</span><span class="sxs-lookup"><span data-stu-id="ac542-407">Here is a visual summary of the infrastructure if your organization uses cloud-only identity.</span></span>
 
![組織がクラウド専用の ID を使用している場合のインフラストラクチャの概要](../media/deploy-foundation-infrastructure-non-enterprises/final-cloud-only-config.png)

### <a name="employee-results"></a><span data-ttu-id="ac542-409">従業員の結果</span><span class="sxs-lookup"><span data-stu-id="ac542-409">Employee results</span></span>

<span data-ttu-id="ac542-410">オンボード後、各従業員には次のものが提供されます。</span><span class="sxs-lookup"><span data-stu-id="ac542-410">After their onboarding, each employee should have:</span></span>

- <span data-ttu-id="ac542-411">自分のデバイスから自分の地域の Microsoft 365 クラウド サービスへのパフォーマンスの高いオンプレミスのネットワーク パス。</span><span class="sxs-lookup"><span data-stu-id="ac542-411">A performant, on-premises network path from their device to the Microsoft 365 cloud services in their region.</span></span>
- <span data-ttu-id="ac542-412">以下のメンバーシップを持つユーザー アカウント。</span><span class="sxs-lookup"><span data-stu-id="ac542-412">A user account with these group memberships:</span></span>
   - <span data-ttu-id="ac542-413">ライセンス付与済み</span><span class="sxs-lookup"><span data-stu-id="ac542-413">LICENSED</span></span>
   - <span data-ttu-id="ac542-414">条件付きアクセス ポリシー用のベースライン、機密、厳しく規制の各 Azure AD グループのメンバーでもある、適切な AD DS または Azure AD セキュリティ グループ</span><span class="sxs-lookup"><span data-stu-id="ac542-414">The appropriate AD DS or Azure AD security groups, which are also members of the BASELINE, SENSITIVE, and HIGHLY-REGULATED Azure AD groups for Conditional Access policies</span></span> 
   - <span data-ttu-id="ac542-415">適切なワークグループ、部署、地域の各グループ</span><span class="sxs-lookup"><span data-stu-id="ac542-415">The appropriate workgroup, departmental, and regional groups</span></span>
   - <span data-ttu-id="ac542-416">機密度ラベル Microsoft 365 グループ (必要な場合)</span><span class="sxs-lookup"><span data-stu-id="ac542-416">Sensitivity label Microsoft 365 groups (as needed)</span></span>
- <span data-ttu-id="ac542-417">Windows 10 Enterprise デバイスは、以下のようになります。</span><span class="sxs-lookup"><span data-stu-id="ac542-417">A Windows 10 Enterprise device that:</span></span>
   - <span data-ttu-id="ac542-418">Azure AD テナント (クラウド専用) に参加している、または Azure AD テナントと AD DS ドメイン (ハイブリッド) の両方に参加している。</span><span class="sxs-lookup"><span data-stu-id="ac542-418">Is joined to the Azure AD tenant (cloud-only) or to both the Azure AD tenant and your AD DS domain (hybrid).</span></span>
   - <span data-ttu-id="ac542-419">Windows 10 Enterprise の最新の製品の品質向上とセキュリティ強化と共に自動的に更新される。</span><span class="sxs-lookup"><span data-stu-id="ac542-419">Automatically updates itself with the latest Windows 10 Enterprise product improvements and security enhancements.</span></span>
   - <span data-ttu-id="ac542-420">Microsoft 365 Apps for enterprise がインストールされ、これにより、最新の Office 製品の品質向上とセキュリティ強化と共に自動的に更新される。</span><span class="sxs-lookup"><span data-stu-id="ac542-420">Has Microsoft 365 Apps for enterprise installed, which automatically updates itself with the latest Office product improvements and security enhancements.</span></span>
   - <span data-ttu-id="ac542-421">Intune に登録され、Intune デバイス コンプライアンス ポリシーおよびアプリ保護ポリシーの対象となる。</span><span class="sxs-lookup"><span data-stu-id="ac542-421">Is enrolled in Intune and subject to Intune device compliance policies and app protection policies.</span></span>

## <a name="next-step"></a><span data-ttu-id="ac542-422">次の手順</span><span class="sxs-lookup"><span data-stu-id="ac542-422">Next step</span></span>

<span data-ttu-id="ac542-423">[ワークロードとシナリオ](deploy-workloads.md)を展開して、エンタープライズ向け Microsoft 365 の基礎インフラストラクチャの機能と構成を活用します。</span><span class="sxs-lookup"><span data-stu-id="ac542-423">Deploy your [workloads and scenarios](deploy-workloads.md) to take advantage of the features and configuration of your Microsoft 365 for enterprise foundation infrastructure.</span></span>
