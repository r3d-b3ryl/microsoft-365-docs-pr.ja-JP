---
title: 一般的な id およびデバイスアクセスポリシー-Microsoft 365 Enterprise |Microsoft Docs
description: ID およびデバイス アクセス ポリシーと構成を適用する方法に関する Microsoft の推奨事項のポリシーを説明します。
author: BrendaCarter
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: b2e9670d700d8c09caf861f5a24b0570e0f74256
ms.sourcegitcommit: 237589a0c8a24510e5c8f3b8b4747d944ad0afbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2019
ms.locfileid: "37746553"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="9b10c-103">共通 ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="9b10c-103">Common identity and device access policies</span></span>
<span data-ttu-id="9b10c-104">この記事では、Azure AD Application Proxy で公開されているオンプレミスアプリケーションを含む、クラウドサービスへのアクセスを保護するための一般的な推奨ポリシーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="9b10c-105">このガイダンスでは、新しくプロビジョニングされた環境に推奨されるポリシーを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-105">This guidance discusses how to deploy the recommended policies in a newly-provisioned environment.</span></span> <span data-ttu-id="9b10c-106">個別のラボ環境でこれらのポリシーを設定することにより、展開をステージングおよび運用環境にステージングする前に、推奨ポリシーを理解し、評価することができます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-106">Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your preproduction and production environments.</span></span> <span data-ttu-id="9b10c-107">新しくプロビジョニングされた環境は、クラウド専用またはハイブリッドの場合があります。</span><span class="sxs-lookup"><span data-stu-id="9b10c-107">Your newly provisioned environment may be cloud-only or hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="9b10c-108">ポリシーセット</span><span class="sxs-lookup"><span data-stu-id="9b10c-108">Policy set</span></span> 

<span data-ttu-id="9b10c-109">次の図は、推奨されるポリシーセットを示しています。</span><span class="sxs-lookup"><span data-stu-id="9b10c-109">The following diagram illustrates the recommended set of policies.</span></span> <span data-ttu-id="9b10c-110">この図は、各ポリシーが適用される保護層と、それらのポリシーが Pc、電話、タブレット、または両方のカテゴリのデバイスに適用されるかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="9b10c-110">It shows which tier of protections each policy applies to and whether the policies apply to PCs or phones and tablets, or both categories of devices.</span></span> <span data-ttu-id="9b10c-111">また、これらのポリシーが構成されている場所も示されます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-111">It also indicates where these policies are configured.</span></span>

![Id とデバイスのアクセスを構成するための一般的なポリシー](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="9b10c-113">この記事の残りの部分では、これらのポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="9b10c-114">デバイスが目的のユーザーを所有していることを保証するために、デバイスを Intune に登録する前に、多要素認証を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b10c-114">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> <span data-ttu-id="9b10c-115">デバイスコンプライアンスポリシーを適用する前に、デバイスを Intune に登録する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="9b10c-115">You must also enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="9b10c-116">これらのタスクを実行するための時間を提供するために、この表に記載されている順序で基準ポリシーを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b10c-116">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table.</span></span> <span data-ttu-id="9b10c-117">ただし、機密性が高く規制された保護のための MFA ポリシーは、いつでも実装できます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-117">However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="9b10c-118">保護レベル</span><span class="sxs-lookup"><span data-stu-id="9b10c-118">Protection level</span></span>|<span data-ttu-id="9b10c-119">ポリシー</span><span class="sxs-lookup"><span data-stu-id="9b10c-119">Policies</span></span>|<span data-ttu-id="9b10c-120">詳細情報</span><span class="sxs-lookup"><span data-stu-id="9b10c-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="9b10c-121">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="9b10c-121">**Baseline**</span></span>|[<span data-ttu-id="9b10c-122">サインインリスクが*中*または*高*の場合は MFA を必須にする</span><span class="sxs-lookup"><span data-stu-id="9b10c-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|        |[<span data-ttu-id="9b10c-123">先進認証をサポートしないクライアントはブロックする</span><span class="sxs-lookup"><span data-stu-id="9b10c-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="9b10c-124">モダン認証を使用していないクライアントは、条件付きアクセスルールをバイパスすることができます。そのため、これらをブロックすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="9b10c-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these</span></span>|
|        |[<span data-ttu-id="9b10c-125">リスクの高いユーザーがパスワードを変更する必要がある</span><span class="sxs-lookup"><span data-stu-id="9b10c-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="9b10c-126">アカウントに対して高リスクのアクティビティが検出された場合に、サインイン時にユーザーにパスワードを変更することを強制します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-126">Forces users to change their password when signing in if high-risk activity is detected for their account</span></span>|
|        |[<span data-ttu-id="9b10c-127">アプリ保護ポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="9b10c-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="9b10c-128">プラットフォームごとに1つのポリシー (iOS、Android、Windows)。</span><span class="sxs-lookup"><span data-stu-id="9b10c-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="9b10c-129">承認済みアプリの要求</span><span class="sxs-lookup"><span data-stu-id="9b10c-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="9b10c-130">携帯電話とタブレットにモバイルアプリの保護を適用する</span><span class="sxs-lookup"><span data-stu-id="9b10c-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="9b10c-131">デバイスコンプライアンスポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="9b10c-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="9b10c-132">プラットフォームごとに1つのポリシー</span><span class="sxs-lookup"><span data-stu-id="9b10c-132">One policy for each platform</span></span>|
|        |[<span data-ttu-id="9b10c-133">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="9b10c-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="9b10c-134">Pc の Intune 管理を強制する</span><span class="sxs-lookup"><span data-stu-id="9b10c-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="9b10c-135">**機密**</span><span class="sxs-lookup"><span data-stu-id="9b10c-135">**Sensitive**</span></span>|[<span data-ttu-id="9b10c-136">サインインリスクが*低*、*中*、*高*のときに MFA を必要とする</span><span class="sxs-lookup"><span data-stu-id="9b10c-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="9b10c-137">準拠*して*いる pc とモバイルデバイスが必要</span><span class="sxs-lookup"><span data-stu-id="9b10c-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="9b10c-138">Pc と携帯電話/タブレットに Intune 管理を強制する</span><span class="sxs-lookup"><span data-stu-id="9b10c-138">Enforces Intune management for PCs and phone/tablets</span></span>|
|<span data-ttu-id="9b10c-139">**高度な規制**</span><span class="sxs-lookup"><span data-stu-id="9b10c-139">**Highly regulated**</span></span>|[<span data-ttu-id="9b10c-140">*常に*MFA が必要</span><span class="sxs-lookup"><span data-stu-id="9b10c-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="9b10c-141">ユーザーへのポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="9b10c-141">Assigning policies to users</span></span>
<span data-ttu-id="9b10c-142">ポリシーを構成する前に、各層の保護に使用している Azure AD グループを特定します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-142">Before configuring policies, identify the Azure AD groups you are using for each tier of protection.</span></span> <span data-ttu-id="9b10c-143">通常、ベースライン保護は組織内の全員に適用されます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-143">Typically, baseline protection applies to everybody in the organization.</span></span> <span data-ttu-id="9b10c-144">ベースラインと機密保護の両方に含まれているユーザーには、適用されているすべてのベースラインポリシーと、機密ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-144">A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies.</span></span> <span data-ttu-id="9b10c-145">保護は累積され、最も制限の厳しいポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-145">Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="9b10c-146">条件付きアクセスの除外に対して Azure AD グループを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b10c-146">A recommended practice is to create an Azure AD group for conditional access exclusion.</span></span> <span data-ttu-id="9b10c-147">[除外] の下にあるすべての条件付きアクセスルールにこのグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-147">Add this group to all of your conditional access rules under "Exclude".</span></span> <span data-ttu-id="9b10c-148">これにより、アクセスの問題のトラブルシューティングを行っている間、ユーザーにアクセス権を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-148">This gives you a method to provide access to a user while you troubleshoot access issues.</span></span> <span data-ttu-id="9b10c-149">これは、一時的なソリューションとしてのみお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b10c-149">This is recommended as a temporary solution only.</span></span> <span data-ttu-id="9b10c-150">このグループを監視して変更を確認し、除外グループが意図したとおりにのみ使用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-150">Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="9b10c-151">次の図は、ユーザーの割り当てと除外の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="9b10c-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![MFA ルールのユーザー割り当てと除外の例](../images/identity-access-policies-assignment.png)

<span data-ttu-id="9b10c-153">図では、"Top secret プロジェクト X teams *" には、MFA を*必要とする条件付きアクセスポリシーが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="9b10c-153">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*.</span></span> <span data-ttu-id="9b10c-154">ユーザーにより高度な保護を適用する場合は、慎重に行います。</span><span class="sxs-lookup"><span data-stu-id="9b10c-154">Be judicious when applying higher levels of protection to users.</span></span> <span data-ttu-id="9b10c-155">このプロジェクトチームのメンバーは、厳しく規制されたコンテンツを表示していない場合でも、ログオンするたびに2つの形式の認証を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b10c-155">Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly-regulated content.</span></span>  

<span data-ttu-id="9b10c-156">これらの推奨事項の一部として作成されたすべての Azure AD グループは、Office 365 グループとして作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b10c-156">All Azure AD groups created as part of these recommendations must be created as Office 365 groups.</span></span> <span data-ttu-id="9b10c-157">これは、SharePoint Online のドキュメントをセキュリティで保護する場合の Azure Information Protection (AIP) の展開で特に重要です。</span><span class="sxs-lookup"><span data-stu-id="9b10c-157">This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![Office 365 グループを作成するための画面キャプチャ](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="9b10c-159">サインインリスクに基づいて MFA を必須にする</span><span class="sxs-lookup"><span data-stu-id="9b10c-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="9b10c-160">MFA を必要とする前に、まず Identity Protection MFA 登録ポリシーを使用して、MFA のユーザーを登録します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-160">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA.</span></span> <span data-ttu-id="9b10c-161">ユーザーが登録されたら、サインインに MFA を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-161">After users are registered you can enforce MFA for sign-in.</span></span> <span data-ttu-id="9b10c-162">[前提条件](identity-access-prerequisites.md)となるのは、すべてのユーザーを MFA で登録することです。</span><span class="sxs-lookup"><span data-stu-id="9b10c-162">The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="9b10c-163">条件付きアクセス ポリシーを作成するには:</span><span class="sxs-lookup"><span data-stu-id="9b10c-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="9b10c-164">[Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="9b10c-164">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="9b10c-165">サインインに成功すると、Azure ダッシュボードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-165">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="9b10c-166">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="9b10c-167">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="9b10c-168">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-168">Choose **New policy**.</span></span>

![ベースラインとなる CA ポリシー](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="9b10c-170">次の表では、このポリシーに対して実装する条件付きアクセスポリシー設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="9b10c-171">**Assignments**</span><span class="sxs-lookup"><span data-stu-id="9b10c-171">**Assignments**</span></span>

|<span data-ttu-id="9b10c-172">型</span><span class="sxs-lookup"><span data-stu-id="9b10c-172">Type</span></span>|<span data-ttu-id="9b10c-173">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="9b10c-173">Properties</span></span>|<span data-ttu-id="9b10c-174">値</span><span class="sxs-lookup"><span data-stu-id="9b10c-174">Values</span></span>|<span data-ttu-id="9b10c-175">注</span><span class="sxs-lookup"><span data-stu-id="9b10c-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="9b10c-176">ユーザーとグループ</span><span class="sxs-lookup"><span data-stu-id="9b10c-176">Users and groups</span></span>|<span data-ttu-id="9b10c-177">含める</span><span class="sxs-lookup"><span data-stu-id="9b10c-177">Include</span></span>|<span data-ttu-id="9b10c-178">ユーザーとグループの選択 – 対象ユーザーを含む特定のセキュリティ グループを選択します</span><span class="sxs-lookup"><span data-stu-id="9b10c-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="9b10c-179">パイロット ユーザーを含むセキュリティ グループから開始します</span><span class="sxs-lookup"><span data-stu-id="9b10c-179">Start with security group including pilot users</span></span>|
||<span data-ttu-id="9b10c-180">除外</span><span class="sxs-lookup"><span data-stu-id="9b10c-180">Exclude</span></span>|<span data-ttu-id="9b10c-181">例外セキュリティ グループ、サービス アカウント (アプリ ID)</span><span class="sxs-lookup"><span data-stu-id="9b10c-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="9b10c-182">必要に応じて変更されたメンバーシップの一時的根拠</span><span class="sxs-lookup"><span data-stu-id="9b10c-182">Membership modified on an as-needed temporary basis</span></span>|
|<span data-ttu-id="9b10c-183">クラウド アプリ</span><span class="sxs-lookup"><span data-stu-id="9b10c-183">Cloud apps</span></span>|<span data-ttu-id="9b10c-184">含める</span><span class="sxs-lookup"><span data-stu-id="9b10c-184">Include</span></span>|<span data-ttu-id="9b10c-185">このルールを適用するアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-185">Select the apps you want this rule to apply to.</span></span> <span data-ttu-id="9b10c-186">たとえば、[Office 365 Exchange Online] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-186">For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="9b10c-187">条件</span><span class="sxs-lookup"><span data-stu-id="9b10c-187">Conditions</span></span>|<span data-ttu-id="9b10c-188">構成済み</span><span class="sxs-lookup"><span data-stu-id="9b10c-188">Configured</span></span>|<span data-ttu-id="9b10c-189">はい</span><span class="sxs-lookup"><span data-stu-id="9b10c-189">Yes</span></span>|<span data-ttu-id="9b10c-190">使用環境およびニーズに合わせて構成します</span><span class="sxs-lookup"><span data-stu-id="9b10c-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="9b10c-191">サインイン リスク</span><span class="sxs-lookup"><span data-stu-id="9b10c-191">Sign-in risk</span></span>|<span data-ttu-id="9b10c-192">リスク レベル</span><span class="sxs-lookup"><span data-stu-id="9b10c-192">Risk level</span></span>||<span data-ttu-id="9b10c-193">次の表のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b10c-193">See the guidance in the following table</span></span>|

<span data-ttu-id="9b10c-194">**サインイン リスク**</span><span class="sxs-lookup"><span data-stu-id="9b10c-194">**Sign-in risk**</span></span>

<span data-ttu-id="9b10c-195">対象とする保護レベルに基づいて設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="9b10c-196">プロパティ</span><span class="sxs-lookup"><span data-stu-id="9b10c-196">Property</span></span>|<span data-ttu-id="9b10c-197">保護レベル</span><span class="sxs-lookup"><span data-stu-id="9b10c-197">Level of protection</span></span>|<span data-ttu-id="9b10c-198">値</span><span class="sxs-lookup"><span data-stu-id="9b10c-198">Values</span></span>|<span data-ttu-id="9b10c-199">注</span><span class="sxs-lookup"><span data-stu-id="9b10c-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="9b10c-200">リスク レベル</span><span class="sxs-lookup"><span data-stu-id="9b10c-200">Risk level</span></span>|<span data-ttu-id="9b10c-201">基準</span><span class="sxs-lookup"><span data-stu-id="9b10c-201">Baseline</span></span>|<span data-ttu-id="9b10c-202">高、中</span><span class="sxs-lookup"><span data-stu-id="9b10c-202">High, medium</span></span>|<span data-ttu-id="9b10c-203">両方をチェック</span><span class="sxs-lookup"><span data-stu-id="9b10c-203">Check both</span></span>|
| |<span data-ttu-id="9b10c-204">機密</span><span class="sxs-lookup"><span data-stu-id="9b10c-204">Sensitive</span></span>|<span data-ttu-id="9b10c-205">高、中、低</span><span class="sxs-lookup"><span data-stu-id="9b10c-205">High, medium, low</span></span>|<span data-ttu-id="9b10c-206">3 つすべてチェック</span><span class="sxs-lookup"><span data-stu-id="9b10c-206">Check all three</span></span>|
| |<span data-ttu-id="9b10c-207">高度な規制</span><span class="sxs-lookup"><span data-stu-id="9b10c-207">Highly regulated</span></span>| |<span data-ttu-id="9b10c-208">すべてのオプションをオフのままにして、常に MFA を強制する</span><span class="sxs-lookup"><span data-stu-id="9b10c-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="9b10c-209">**アクセス制御**</span><span class="sxs-lookup"><span data-stu-id="9b10c-209">**Access controls**</span></span>

|<span data-ttu-id="9b10c-210">型</span><span class="sxs-lookup"><span data-stu-id="9b10c-210">Type</span></span>|<span data-ttu-id="9b10c-211">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="9b10c-211">Properties</span></span>|<span data-ttu-id="9b10c-212">値</span><span class="sxs-lookup"><span data-stu-id="9b10c-212">Values</span></span>|<span data-ttu-id="9b10c-213">注</span><span class="sxs-lookup"><span data-stu-id="9b10c-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="9b10c-214">許可</span><span class="sxs-lookup"><span data-stu-id="9b10c-214">Grant</span></span>|<span data-ttu-id="9b10c-215">アクセスの許可</span><span class="sxs-lookup"><span data-stu-id="9b10c-215">Grant access</span></span>|<span data-ttu-id="9b10c-216">はい</span><span class="sxs-lookup"><span data-stu-id="9b10c-216">True</span></span>|<span data-ttu-id="9b10c-217">選択</span><span class="sxs-lookup"><span data-stu-id="9b10c-217">Selected</span></span>|
||<span data-ttu-id="9b10c-218">MFA を要求</span><span class="sxs-lookup"><span data-stu-id="9b10c-218">Require MFA</span></span>|<span data-ttu-id="9b10c-219">True</span><span class="sxs-lookup"><span data-stu-id="9b10c-219">True</span></span>|<span data-ttu-id="9b10c-220">Check</span><span class="sxs-lookup"><span data-stu-id="9b10c-220">Check</span></span>|
||<span data-ttu-id="9b10c-221">デバイスを準拠としてマークする必要がある</span><span class="sxs-lookup"><span data-stu-id="9b10c-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="9b10c-222">False</span><span class="sxs-lookup"><span data-stu-id="9b10c-222">False</span></span>||
||<span data-ttu-id="9b10c-223">ハイブリッドの Azure AD に参加しているデバイスが必要</span><span class="sxs-lookup"><span data-stu-id="9b10c-223">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="9b10c-224">False</span><span class="sxs-lookup"><span data-stu-id="9b10c-224">False</span></span>||
||<span data-ttu-id="9b10c-225">承認済みクライアントアプリを必要とする</span><span class="sxs-lookup"><span data-stu-id="9b10c-225">Require approved client app</span></span>|<span data-ttu-id="9b10c-226">False</span><span class="sxs-lookup"><span data-stu-id="9b10c-226">False</span></span>||
||<span data-ttu-id="9b10c-227">選択したコントロールすべてが必要</span><span class="sxs-lookup"><span data-stu-id="9b10c-227">Require all the selected controls</span></span>|<span data-ttu-id="9b10c-228">True</span><span class="sxs-lookup"><span data-stu-id="9b10c-228">True</span></span>|<span data-ttu-id="9b10c-229">選択</span><span class="sxs-lookup"><span data-stu-id="9b10c-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="9b10c-230">**[**] を選択して、このポリシーを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="9b10c-230">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="9b10c-231">また、ポリシーをテストする場合は、[[対象](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)] ツールを使用してください。</span><span class="sxs-lookup"><span data-stu-id="9b10c-231">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="9b10c-232">先進認証をサポートしないクライアントはブロックする</span><span class="sxs-lookup"><span data-stu-id="9b10c-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="9b10c-233">[Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="9b10c-233">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="9b10c-234">サインインに成功すると、Azure ダッシュボードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-234">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="9b10c-235">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="9b10c-236">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="9b10c-237">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-237">Choose **New policy**.</span></span>

<span data-ttu-id="9b10c-238">次の表では、このポリシーに対して実装する条件付きアクセスポリシー設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="9b10c-239">**Assignments**</span><span class="sxs-lookup"><span data-stu-id="9b10c-239">**Assignments**</span></span>

|<span data-ttu-id="9b10c-240">型</span><span class="sxs-lookup"><span data-stu-id="9b10c-240">Type</span></span>|<span data-ttu-id="9b10c-241">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="9b10c-241">Properties</span></span>|<span data-ttu-id="9b10c-242">値</span><span class="sxs-lookup"><span data-stu-id="9b10c-242">Values</span></span>|<span data-ttu-id="9b10c-243">注</span><span class="sxs-lookup"><span data-stu-id="9b10c-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="9b10c-244">ユーザーとグループ</span><span class="sxs-lookup"><span data-stu-id="9b10c-244">Users and groups</span></span>|<span data-ttu-id="9b10c-245">含める</span><span class="sxs-lookup"><span data-stu-id="9b10c-245">Include</span></span>|<span data-ttu-id="9b10c-246">ユーザーとグループの選択 – 対象ユーザーを含む特定のセキュリティ グループを選択します</span><span class="sxs-lookup"><span data-stu-id="9b10c-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="9b10c-247">パイロット ユーザーを含むセキュリティ グループから開始します</span><span class="sxs-lookup"><span data-stu-id="9b10c-247">Start with security group including pilot users</span></span>|
||<span data-ttu-id="9b10c-248">除外</span><span class="sxs-lookup"><span data-stu-id="9b10c-248">Exclude</span></span>|<span data-ttu-id="9b10c-249">例外セキュリティ グループ、サービス アカウント (アプリ ID)</span><span class="sxs-lookup"><span data-stu-id="9b10c-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="9b10c-250">必要に応じて一時的にメンバーシップを変更します</span><span class="sxs-lookup"><span data-stu-id="9b10c-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="9b10c-251">クラウド アプリ</span><span class="sxs-lookup"><span data-stu-id="9b10c-251">Cloud apps</span></span>|<span data-ttu-id="9b10c-252">含める</span><span class="sxs-lookup"><span data-stu-id="9b10c-252">Include</span></span>|<span data-ttu-id="9b10c-253">このルールを適用するアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-253">Select the apps you want this rule to apply to.</span></span> <span data-ttu-id="9b10c-254">たとえば、[Office 365 Exchange Online] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-254">For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="9b10c-255">条件</span><span class="sxs-lookup"><span data-stu-id="9b10c-255">Conditions</span></span>|<span data-ttu-id="9b10c-256">構成済み</span><span class="sxs-lookup"><span data-stu-id="9b10c-256">Configured</span></span>|<span data-ttu-id="9b10c-257">はい</span><span class="sxs-lookup"><span data-stu-id="9b10c-257">Yes</span></span>|<span data-ttu-id="9b10c-258">クライアントアプリを構成する</span><span class="sxs-lookup"><span data-stu-id="9b10c-258">Configure Client apps</span></span>|
|<span data-ttu-id="9b10c-259">クライアント アプリ</span><span class="sxs-lookup"><span data-stu-id="9b10c-259">Client apps</span></span>|<span data-ttu-id="9b10c-260">構成済み</span><span class="sxs-lookup"><span data-stu-id="9b10c-260">Configured</span></span>|<span data-ttu-id="9b10c-261">はい</span><span class="sxs-lookup"><span data-stu-id="9b10c-261">Yes</span></span>|<span data-ttu-id="9b10c-262">モバイルアプリとデスクトップクライアント、その他のクライアント (両方を選択する)</span><span class="sxs-lookup"><span data-stu-id="9b10c-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="9b10c-263">**アクセス制御**</span><span class="sxs-lookup"><span data-stu-id="9b10c-263">**Access controls**</span></span>

|<span data-ttu-id="9b10c-264">型</span><span class="sxs-lookup"><span data-stu-id="9b10c-264">Type</span></span>|<span data-ttu-id="9b10c-265">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="9b10c-265">Properties</span></span>|<span data-ttu-id="9b10c-266">値</span><span class="sxs-lookup"><span data-stu-id="9b10c-266">Values</span></span>|<span data-ttu-id="9b10c-267">注</span><span class="sxs-lookup"><span data-stu-id="9b10c-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="9b10c-268">許可</span><span class="sxs-lookup"><span data-stu-id="9b10c-268">Grant</span></span>|<span data-ttu-id="9b10c-269">アクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="9b10c-269">Block access</span></span>|<span data-ttu-id="9b10c-270">はい</span><span class="sxs-lookup"><span data-stu-id="9b10c-270">True</span></span>|<span data-ttu-id="9b10c-271">選択</span><span class="sxs-lookup"><span data-stu-id="9b10c-271">Selected</span></span>|
||<span data-ttu-id="9b10c-272">MFA を要求</span><span class="sxs-lookup"><span data-stu-id="9b10c-272">Require MFA</span></span>|<span data-ttu-id="9b10c-273">False</span><span class="sxs-lookup"><span data-stu-id="9b10c-273">False</span></span>||
||<span data-ttu-id="9b10c-274">デバイスを準拠としてマークする必要がある</span><span class="sxs-lookup"><span data-stu-id="9b10c-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="9b10c-275">False</span><span class="sxs-lookup"><span data-stu-id="9b10c-275">False</span></span>||
||<span data-ttu-id="9b10c-276">ハイブリッドの Azure AD に参加しているデバイスが必要</span><span class="sxs-lookup"><span data-stu-id="9b10c-276">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="9b10c-277">False</span><span class="sxs-lookup"><span data-stu-id="9b10c-277">False</span></span>||
||<span data-ttu-id="9b10c-278">承認済みクライアントアプリを必要とする</span><span class="sxs-lookup"><span data-stu-id="9b10c-278">Require approved client app</span></span>|<span data-ttu-id="9b10c-279">False</span><span class="sxs-lookup"><span data-stu-id="9b10c-279">False</span></span>||
||<span data-ttu-id="9b10c-280">選択したコントロールすべてが必要</span><span class="sxs-lookup"><span data-stu-id="9b10c-280">Require all the selected controls</span></span>|<span data-ttu-id="9b10c-281">True</span><span class="sxs-lookup"><span data-stu-id="9b10c-281">True</span></span>|<span data-ttu-id="9b10c-282">選択</span><span class="sxs-lookup"><span data-stu-id="9b10c-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="9b10c-283">**[**] を選択して、このポリシーを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="9b10c-283">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="9b10c-284">また、ポリシーをテストする場合は、[[対象](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)] ツールを使用してください。</span><span class="sxs-lookup"><span data-stu-id="9b10c-284">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="9b10c-285">リスクの高いユーザーがパスワードを変更する必要がある</span><span class="sxs-lookup"><span data-stu-id="9b10c-285">High risk users must change password</span></span>
<span data-ttu-id="9b10c-286">すべての危険度の高いユーザーが侵害されたアカウントが、サインイン時にパスワードの変更を強制的に実行するようにするには、次のポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b10c-286">To ensure that all high-risk users' compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="9b10c-287">管理者資格情報を使用して [Microsoft Azure ポータル (https://portal.azure.com)](https://portal.azure.com/) にログインしてから、**[Azure AD Identity Protection]、[ユーザーのリスク ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-287">Log in to the [Microsoft Azure portal (https://portal.azure.com)](https://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="9b10c-288">**Assignments**</span><span class="sxs-lookup"><span data-stu-id="9b10c-288">**Assignments**</span></span>

|<span data-ttu-id="9b10c-289">型</span><span class="sxs-lookup"><span data-stu-id="9b10c-289">Type</span></span>|<span data-ttu-id="9b10c-290">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="9b10c-290">Properties</span></span>|<span data-ttu-id="9b10c-291">値</span><span class="sxs-lookup"><span data-stu-id="9b10c-291">Values</span></span>|<span data-ttu-id="9b10c-292">注</span><span class="sxs-lookup"><span data-stu-id="9b10c-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="9b10c-293">Users</span><span class="sxs-lookup"><span data-stu-id="9b10c-293">Users</span></span>|<span data-ttu-id="9b10c-294">含める</span><span class="sxs-lookup"><span data-stu-id="9b10c-294">Include</span></span>|<span data-ttu-id="9b10c-295">[すべてのユーザー]</span><span class="sxs-lookup"><span data-stu-id="9b10c-295">All users</span></span>|<span data-ttu-id="9b10c-296">オン</span><span class="sxs-lookup"><span data-stu-id="9b10c-296">Selected</span></span>|
||<span data-ttu-id="9b10c-297">除外</span><span class="sxs-lookup"><span data-stu-id="9b10c-297">Exclude</span></span>|<span data-ttu-id="9b10c-298">なし</span><span class="sxs-lookup"><span data-stu-id="9b10c-298">None</span></span>||
|<span data-ttu-id="9b10c-299">条件</span><span class="sxs-lookup"><span data-stu-id="9b10c-299">Conditions</span></span>|<span data-ttu-id="9b10c-300">ユーザーのリスク</span><span class="sxs-lookup"><span data-stu-id="9b10c-300">User risk</span></span>|<span data-ttu-id="9b10c-301">高</span><span class="sxs-lookup"><span data-stu-id="9b10c-301">High</span></span>|<span data-ttu-id="9b10c-302">オン</span><span class="sxs-lookup"><span data-stu-id="9b10c-302">Selected</span></span>|

<span data-ttu-id="9b10c-303">**コントロール**</span><span class="sxs-lookup"><span data-stu-id="9b10c-303">**Controls**</span></span>

| <span data-ttu-id="9b10c-304">型</span><span class="sxs-lookup"><span data-stu-id="9b10c-304">Type</span></span> | <span data-ttu-id="9b10c-305">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="9b10c-305">Properties</span></span> | <span data-ttu-id="9b10c-306">値</span><span class="sxs-lookup"><span data-stu-id="9b10c-306">Values</span></span>                  | <span data-ttu-id="9b10c-307">注</span><span class="sxs-lookup"><span data-stu-id="9b10c-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="9b10c-308">Access</span><span class="sxs-lookup"><span data-stu-id="9b10c-308">Access</span></span>     | <span data-ttu-id="9b10c-309">SSL 経由でのみ</span><span class="sxs-lookup"><span data-stu-id="9b10c-309">Allow access</span></span>            | <span data-ttu-id="9b10c-310">はい</span><span class="sxs-lookup"><span data-stu-id="9b10c-310">True</span></span>  |
|      | <span data-ttu-id="9b10c-311">Access</span><span class="sxs-lookup"><span data-stu-id="9b10c-311">Access</span></span>     | <span data-ttu-id="9b10c-312">パスワードの変更を必須とする</span><span class="sxs-lookup"><span data-stu-id="9b10c-312">Require password change</span></span> | <span data-ttu-id="9b10c-313">True</span><span class="sxs-lookup"><span data-stu-id="9b10c-313">True</span></span>  |

<span data-ttu-id="9b10c-314">**レビュー:** 該当なし</span><span class="sxs-lookup"><span data-stu-id="9b10c-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="9b10c-315">**[**] を選択して、このポリシーを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="9b10c-315">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="9b10c-316">ポリシーをテストする[場合](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)は、[対象] ツールを使用することも検討してください。</span><span class="sxs-lookup"><span data-stu-id="9b10c-316">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="9b10c-317">アプリ保護ポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="9b10c-317">Define app protection policies</span></span>
<span data-ttu-id="9b10c-318">アプリ保護ポリシーは、許可されるアプリと、組織のデータによって実行できるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-318">App protection policies define which apps are allowed and the actions they can take with your organization's data.</span></span> <span data-ttu-id="9b10c-319">Azure ポータル内から Intune アプリ保護ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-319">Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="9b10c-320">プラットフォームごとにポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="9b10c-321">iOS</span><span class="sxs-lookup"><span data-stu-id="9b10c-321">iOS</span></span>
- <span data-ttu-id="9b10c-322">Android</span><span class="sxs-lookup"><span data-stu-id="9b10c-322">Android</span></span>
- <span data-ttu-id="9b10c-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="9b10c-323">Windows 10</span></span>

<span data-ttu-id="9b10c-324">新しいアプリ保護ポリシーを作成するには、管理者の資格情報を使用して Microsoft Azure portal にサインインしてから、[**クライアントアプリ** > の**アプリ保護ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-324">To create a new app protection policy, sign in to the Microsoft Azure portal with your administrator credentials, and then navigate to **Client apps** > **App protection policies**.</span></span> <span data-ttu-id="9b10c-325">[**ポリシーの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-325">Choose **Create policy**.</span></span>

<span data-ttu-id="9b10c-326">iOS と Android では、アプリ保護ポリシーのオプションが若干異なります。</span><span class="sxs-lookup"><span data-stu-id="9b10c-326">There are slight differences in the app protection policy options between iOS and Android.</span></span> <span data-ttu-id="9b10c-327">以下のポリシーは Android 専用です。</span><span class="sxs-lookup"><span data-stu-id="9b10c-327">The below policy is specifically for Android.</span></span> <span data-ttu-id="9b10c-328">他のポリシーのガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-328">Use this as a guide for your other policies.</span></span>

<span data-ttu-id="9b10c-329">推奨されるアプリの一覧には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="9b10c-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="9b10c-330">PowerPoint</span></span>
- <span data-ttu-id="9b10c-331">Excel</span><span class="sxs-lookup"><span data-stu-id="9b10c-331">Excel</span></span>
- <span data-ttu-id="9b10c-332">Word</span><span class="sxs-lookup"><span data-stu-id="9b10c-332">Word</span></span>
- <span data-ttu-id="9b10c-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9b10c-333">Microsoft Teams</span></span>
- <span data-ttu-id="9b10c-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="9b10c-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="9b10c-335">Microsoft Visio Viewer</span><span class="sxs-lookup"><span data-stu-id="9b10c-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="9b10c-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="9b10c-336">OneDrive</span></span>
- <span data-ttu-id="9b10c-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="9b10c-337">OneNote</span></span>
- <span data-ttu-id="9b10c-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="9b10c-338">Outlook</span></span>

<span data-ttu-id="9b10c-339">推奨される設定を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="9b10c-340">型</span><span class="sxs-lookup"><span data-stu-id="9b10c-340">Type</span></span>|<span data-ttu-id="9b10c-341">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="9b10c-341">Properties</span></span>|<span data-ttu-id="9b10c-342">値</span><span class="sxs-lookup"><span data-stu-id="9b10c-342">Values</span></span>|<span data-ttu-id="9b10c-343">注</span><span class="sxs-lookup"><span data-stu-id="9b10c-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="9b10c-344">データ再配置</span><span class="sxs-lookup"><span data-stu-id="9b10c-344">Data relocation</span></span>|<span data-ttu-id="9b10c-345">[Android でのバックアップを禁止する]</span><span class="sxs-lookup"><span data-stu-id="9b10c-345">Prevent Android backup</span></span>|<span data-ttu-id="9b10c-346">はい</span><span class="sxs-lookup"><span data-stu-id="9b10c-346">Yes</span></span>|<span data-ttu-id="9b10c-347">iOS では、特に iTunes と iCloud が呼び出されます</span><span class="sxs-lookup"><span data-stu-id="9b10c-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="9b10c-348">[アプリで他のアプリへのデータ転送を許可する]</span><span class="sxs-lookup"><span data-stu-id="9b10c-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="9b10c-349">ポリシーで管理されているアプリ</span><span class="sxs-lookup"><span data-stu-id="9b10c-349">Policy managed apps</span></span>||
||<span data-ttu-id="9b10c-350">このアプリで他のアプリからデータを受信できるようにする</span><span class="sxs-lookup"><span data-stu-id="9b10c-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="9b10c-351">ポリシーで管理されているアプリ</span><span class="sxs-lookup"><span data-stu-id="9b10c-351">Policy managed apps</span></span>||
||<span data-ttu-id="9b10c-352">[名前を付けて保存] を禁止する</span><span class="sxs-lookup"><span data-stu-id="9b10c-352">Prevent "Save As"</span></span>|<span data-ttu-id="9b10c-353">はい</span><span class="sxs-lookup"><span data-stu-id="9b10c-353">Yes</span></span>||
||<span data-ttu-id="9b10c-354">会社のデータを保存できるストレージ サービスの選択</span><span class="sxs-lookup"><span data-stu-id="9b10c-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="9b10c-355">OneDrive for Business、SharePoint</span><span class="sxs-lookup"><span data-stu-id="9b10c-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="9b10c-356">他のアプリとの間で切り取り、コピー、貼り付けを制限する</span><span class="sxs-lookup"><span data-stu-id="9b10c-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="9b10c-357">貼り付けられたポリシー管理対象アプリ</span><span class="sxs-lookup"><span data-stu-id="9b10c-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="9b10c-358">Web コンテンツを管理対象ブラウザーで表示するように制限する</span><span class="sxs-lookup"><span data-stu-id="9b10c-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="9b10c-359">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b10c-359">No</span></span>||
||<span data-ttu-id="9b10c-360">[アプリ データの暗号化]</span><span class="sxs-lookup"><span data-stu-id="9b10c-360">Encrypt app data</span></span>|<span data-ttu-id="9b10c-361">はい</span><span class="sxs-lookup"><span data-stu-id="9b10c-361">Yes</span></span>|<span data-ttu-id="9b10c-362">iOS では、[デバイスがロックされている場合] オプションを選択します</span><span class="sxs-lookup"><span data-stu-id="9b10c-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="9b10c-363">デバイスが有効な場合はアプリの暗号化を無効にする</span><span class="sxs-lookup"><span data-stu-id="9b10c-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="9b10c-364">はい</span><span class="sxs-lookup"><span data-stu-id="9b10c-364">Yes</span></span>|<span data-ttu-id="9b10c-365">二重暗号化を回避するためにこの設定を無効にする</span><span class="sxs-lookup"><span data-stu-id="9b10c-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="9b10c-366">連絡先の同期を無効にする</span><span class="sxs-lookup"><span data-stu-id="9b10c-366">Disable contacts sync</span></span>|<span data-ttu-id="9b10c-367">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b10c-367">No</span></span>||
||<span data-ttu-id="9b10c-368">印刷を無効にする</span><span class="sxs-lookup"><span data-stu-id="9b10c-368">Disable printing</span></span>|<span data-ttu-id="9b10c-369">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b10c-369">No</span></span>||
|<span data-ttu-id="9b10c-370">アクセス</span><span class="sxs-lookup"><span data-stu-id="9b10c-370">Access</span></span>|<span data-ttu-id="9b10c-371">アクセスのために PIN を要求する</span><span class="sxs-lookup"><span data-stu-id="9b10c-371">Require PIN for access</span></span>|<span data-ttu-id="9b10c-372">はい</span><span class="sxs-lookup"><span data-stu-id="9b10c-372">Yes</span></span>||
||<span data-ttu-id="9b10c-373">種類の選択</span><span class="sxs-lookup"><span data-stu-id="9b10c-373">Select Type</span></span>|<span data-ttu-id="9b10c-374">数値</span><span class="sxs-lookup"><span data-stu-id="9b10c-374">Numeric</span></span>||
||<span data-ttu-id="9b10c-375">単純な PIN を許可する</span><span class="sxs-lookup"><span data-stu-id="9b10c-375">Allow simple PIN</span></span>|<span data-ttu-id="9b10c-376">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b10c-376">No</span></span>||
||<span data-ttu-id="9b10c-377">PIN の長さ</span><span class="sxs-lookup"><span data-stu-id="9b10c-377">PIN length</span></span>|<span data-ttu-id="9b10c-378">6 </span><span class="sxs-lookup"><span data-stu-id="9b10c-378">6</span></span>||
||<span data-ttu-id="9b10c-379">PIN の代わりに指紋を要求する</span><span class="sxs-lookup"><span data-stu-id="9b10c-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="9b10c-380">はい</span><span class="sxs-lookup"><span data-stu-id="9b10c-380">Yes</span></span>||
||<span data-ttu-id="9b10c-381">デバイス PIN が管理されている場合はアプリ PIN を無効にする</span><span class="sxs-lookup"><span data-stu-id="9b10c-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="9b10c-382">はい</span><span class="sxs-lookup"><span data-stu-id="9b10c-382">Yes</span></span>||
||<span data-ttu-id="9b10c-383">アクセスのために会社の資格情報を要求する</span><span class="sxs-lookup"><span data-stu-id="9b10c-383">Require corporate credentials for access</span></span>|<span data-ttu-id="9b10c-384">いいえ</span><span class="sxs-lookup"><span data-stu-id="9b10c-384">No</span></span>||
||<span data-ttu-id="9b10c-385">[(分数) 後に、アクセス要件を再確認する]</span><span class="sxs-lookup"><span data-stu-id="9b10c-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="9b10c-386">31</span><span class="sxs-lookup"><span data-stu-id="9b10c-386">30</span></span>||
||<span data-ttu-id="9b10c-387">[スクリーン キャプチャと Android Assistant をブロックする]</span><span class="sxs-lookup"><span data-stu-id="9b10c-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="9b10c-388">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="9b10c-388">No</span></span>|<span data-ttu-id="9b10c-389">iOS では、このオプションは使用できません</span><span class="sxs-lookup"><span data-stu-id="9b10c-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="9b10c-390">サインインのセキュリティ要件</span><span class="sxs-lookup"><span data-stu-id="9b10c-390">Sign-in security requirements</span></span>|<span data-ttu-id="9b10c-391">PIN の最大試行回数</span><span class="sxs-lookup"><span data-stu-id="9b10c-391">Max PIN attempts</span></span>|<span data-ttu-id="9b10c-392">5</span><span class="sxs-lookup"><span data-stu-id="9b10c-392">5</span></span>|<span data-ttu-id="9b10c-393">Pin のリセット</span><span class="sxs-lookup"><span data-stu-id="9b10c-393">Reset Pin</span></span>|
||<span data-ttu-id="9b10c-394">[オフラインの猶予期間]</span><span class="sxs-lookup"><span data-stu-id="9b10c-394">Offline grace period</span></span>|<span data-ttu-id="9b10c-395">720</span><span class="sxs-lookup"><span data-stu-id="9b10c-395">720</span></span>|<span data-ttu-id="9b10c-396">アクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="9b10c-396">Block access</span></span>|
||<span data-ttu-id="9b10c-397">アプリのデータがワイプされるまでのオフライン期間 (日数)</span><span class="sxs-lookup"><span data-stu-id="9b10c-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="9b10c-398">90</span><span class="sxs-lookup"><span data-stu-id="9b10c-398">90</span></span>|<span data-ttu-id="9b10c-399">データのワイプ</span><span class="sxs-lookup"><span data-stu-id="9b10c-399">Wipe data</span></span>|
||<span data-ttu-id="9b10c-400">脱獄/ルート化したデバイス</span><span class="sxs-lookup"><span data-stu-id="9b10c-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="9b10c-401">データのワイプ</span><span class="sxs-lookup"><span data-stu-id="9b10c-401">Wipe data</span></span>|

<span data-ttu-id="9b10c-402">完了したら、必ず [作成] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="9b10c-402">When complete, remember to select "Create".</span></span> <span data-ttu-id="9b10c-403">上記の手順を繰り返し、選択したプラットフォーム (ドロップダウン) を iOS に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-403">Repeat the above steps and replace the selected platform (dropdown) with iOS.</span></span> <span data-ttu-id="9b10c-404">これにより、ポリシーを作成した後にグループをポリシーに割り当てて展開することができるように、2つのアプリポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-404">This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="9b10c-405">ポリシーを編集して、これらのポリシーをユーザーに割り当てるには、「[アプリ保護ポリシーを作成して割り当てる方法](https://docs.microsoft.com/intune/app-protection-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b10c-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="9b10c-406">承認済みアプリの要求</span><span class="sxs-lookup"><span data-stu-id="9b10c-406">Require approved apps</span></span>
<span data-ttu-id="9b10c-407">承認済みアプリを要求するには</span><span class="sxs-lookup"><span data-stu-id="9b10c-407">To require approved apps:</span></span>

1. <span data-ttu-id="9b10c-408">[Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="9b10c-408">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="9b10c-409">サインインに成功すると、Azure ダッシュボードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-409">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="9b10c-410">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="9b10c-411">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="9b10c-412">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="9b10c-413">ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="9b10c-414">**[クラウド アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="9b10c-415">**[アプリの選択**] を選択し、[**クラウドアプリ**] リストから目的のアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-415">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="9b10c-416">たとえば、[Office 365 Exchange Online] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-416">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="9b10c-417">**[選択**して**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-417">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="9b10c-418">[**条件**] を選択し、[**デバイスプラットフォーム**] を選択し、[**構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-418">Choose **Conditions**, select **Device platforms**, then choose **Configure**</span></span>

9. <span data-ttu-id="9b10c-419">[**インクルード**] で、[**デバイスプラットフォームの選択**] を選択し、[ **Android**および**iOS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-419">Under **Include**, choose **Select device platforms**, select **Android** and **iOS**.</span></span> <span data-ttu-id="9b10c-420">[**完了**] をクリックし、もう一度**実行**します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-420">Click **Done** and **Done** again</span></span>

10. <span data-ttu-id="9b10c-421">**[アクセス制御]** セクションから **[許可]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-421">Choose **Grant** from the **Access controls** section.</span></span>

11. <span data-ttu-id="9b10c-422">[**アクセス許可の付与**] を選択し、[**承認済みクライアントアプリの要求**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-422">Choose **Grant access**, select **Require approved client app**.</span></span> <span data-ttu-id="9b10c-423">複数のコントロールの場合は、[選択した**コントロールを必要とする**] を選択し、[**選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-423">For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

12. <span data-ttu-id="9b10c-424">[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-424">Choose **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="9b10c-425">デバイスコンプライアンスポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="9b10c-425">Define device-compliance policies</span></span>

<span data-ttu-id="9b10c-426">デバイスコンプライアンスポリシーは、準拠としてマークするためにデバイスが従う必要がある要件を定義します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-426">Device-compliance policies define the requirements that devices must adhere to in order to be marked as compliant.</span></span> <span data-ttu-id="9b10c-427">Azure ポータル内から Intune デバイスコンプライアンスポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-427">Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="9b10c-428">プラットフォームごとにポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-428">Create a policy for each platform:</span></span>
- <span data-ttu-id="9b10c-429">Android</span><span class="sxs-lookup"><span data-stu-id="9b10c-429">Android</span></span>
- <span data-ttu-id="9b10c-430">Android enterprise</span><span class="sxs-lookup"><span data-stu-id="9b10c-430">Android enterprise</span></span>
- <span data-ttu-id="9b10c-431">iOS</span><span class="sxs-lookup"><span data-stu-id="9b10c-431">iOS</span></span>
- <span data-ttu-id="9b10c-432">macOS</span><span class="sxs-lookup"><span data-stu-id="9b10c-432">macOS</span></span>
- <span data-ttu-id="9b10c-433">この設定は、次の種類のデバイスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-433">Windows Phone 8.1</span></span>
- <span data-ttu-id="9b10c-434">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="9b10c-434">Windows 8.1 and later</span></span>
- <span data-ttu-id="9b10c-435">Windows 10 以降</span><span class="sxs-lookup"><span data-stu-id="9b10c-435">Windows 10 and later</span></span>

<span data-ttu-id="9b10c-436">デバイスコンプライアンスポリシーを作成するには、管理者の資格情報を使用して Microsoft Azure portal にログインしてから、[ **Intune > デバイスのコンプライアンス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-436">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**.</span></span> <span data-ttu-id="9b10c-437">[**ポリシーの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-437">Select **Create policy**.</span></span>

<span data-ttu-id="9b10c-438">Windows 10 では、次の設定をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b10c-438">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="9b10c-439">**デバイス正常性: Windows Health 構成証明サービスの評価ルール**</span><span class="sxs-lookup"><span data-stu-id="9b10c-439">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="9b10c-440">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="9b10c-440">Properties</span></span>|<span data-ttu-id="9b10c-441">値</span><span class="sxs-lookup"><span data-stu-id="9b10c-441">Values</span></span>|<span data-ttu-id="9b10c-442">注</span><span class="sxs-lookup"><span data-stu-id="9b10c-442">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="9b10c-443">BitLocker を必須にする</span><span class="sxs-lookup"><span data-stu-id="9b10c-443">Require BitLocker</span></span>|<span data-ttu-id="9b10c-444">必須</span><span class="sxs-lookup"><span data-stu-id="9b10c-444">Require</span></span>||
|<span data-ttu-id="9b10c-445">デバイスでセキュアブートが有効になっていることが必要</span><span class="sxs-lookup"><span data-stu-id="9b10c-445">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="9b10c-446">必須</span><span class="sxs-lookup"><span data-stu-id="9b10c-446">Require</span></span>||
|<span data-ttu-id="9b10c-447">コードの整合性を必須にする</span><span class="sxs-lookup"><span data-stu-id="9b10c-447">Require code integrity</span></span>|<span data-ttu-id="9b10c-448">必須</span><span class="sxs-lookup"><span data-stu-id="9b10c-448">Require</span></span>||


<span data-ttu-id="9b10c-449">**デバイスのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="9b10c-449">**Device properties**</span></span>

|<span data-ttu-id="9b10c-450">型</span><span class="sxs-lookup"><span data-stu-id="9b10c-450">Type</span></span>|<span data-ttu-id="9b10c-451">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="9b10c-451">Properties</span></span>|<span data-ttu-id="9b10c-452">値</span><span class="sxs-lookup"><span data-stu-id="9b10c-452">Values</span></span>|<span data-ttu-id="9b10c-453">注</span><span class="sxs-lookup"><span data-stu-id="9b10c-453">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="9b10c-454">オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="9b10c-454">Operating system version</span></span>|<span data-ttu-id="9b10c-455">すべて</span><span class="sxs-lookup"><span data-stu-id="9b10c-455">All</span></span>|<span data-ttu-id="9b10c-456">未構成</span><span class="sxs-lookup"><span data-stu-id="9b10c-456">Not configured</span></span>||

<span data-ttu-id="9b10c-457">上記のすべてのポリシーを展開済みと見なすには、ユーザー グループを対象にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b10c-457">For all the above policies to be considered deployed, they must be targeted at user groups.</span></span> <span data-ttu-id="9b10c-458">これを行うには、ポリシーを (保存時に) [**ポリシー** ] セクションの [**展開の管理**] ([追加] と同じレベル) を選択して作成します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-458">You can do this by creating the policy (on Save) or later by selecting **Manage Deployment** in the **Policy** section (same level as Add).</span></span>

<span data-ttu-id="9b10c-459">**システム セキュリティ**</span><span class="sxs-lookup"><span data-stu-id="9b10c-459">**System security**</span></span>

|<span data-ttu-id="9b10c-460">型</span><span class="sxs-lookup"><span data-stu-id="9b10c-460">Type</span></span>|<span data-ttu-id="9b10c-461">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="9b10c-461">Properties</span></span>|<span data-ttu-id="9b10c-462">値</span><span class="sxs-lookup"><span data-stu-id="9b10c-462">Values</span></span>|<span data-ttu-id="9b10c-463">注</span><span class="sxs-lookup"><span data-stu-id="9b10c-463">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="9b10c-464">Password</span><span class="sxs-lookup"><span data-stu-id="9b10c-464">Password</span></span>|<span data-ttu-id="9b10c-465">モバイルデバイスのロックを解除するためのパスワードを要求する</span><span class="sxs-lookup"><span data-stu-id="9b10c-465">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="9b10c-466">必須</span><span class="sxs-lookup"><span data-stu-id="9b10c-466">Require</span></span>||
||<span data-ttu-id="9b10c-467">単純なパスワード</span><span class="sxs-lookup"><span data-stu-id="9b10c-467">Simple passwords</span></span>|<span data-ttu-id="9b10c-468">Block</span><span class="sxs-lookup"><span data-stu-id="9b10c-468">Block</span></span>||
||<span data-ttu-id="9b10c-469">パスワードの種類</span><span class="sxs-lookup"><span data-stu-id="9b10c-469">Password type</span></span>|<span data-ttu-id="9b10c-470">既定のデバイス</span><span class="sxs-lookup"><span data-stu-id="9b10c-470">Device default</span></span>||
||<span data-ttu-id="9b10c-471">パスワードの最小文字数</span><span class="sxs-lookup"><span data-stu-id="9b10c-471">Minimum password length</span></span>|<span data-ttu-id="9b10c-472">6 </span><span class="sxs-lookup"><span data-stu-id="9b10c-472">6</span></span>||
||<span data-ttu-id="9b10c-473">パスワードが必要になるまでの最大非アクティブ時間 (分)</span><span class="sxs-lookup"><span data-stu-id="9b10c-473">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="9b10c-474">15 </span><span class="sxs-lookup"><span data-stu-id="9b10c-474">15</span></span>|<span data-ttu-id="9b10c-475">この設定は、Android バージョン4.0 以降、または KNOX 4.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9b10c-475">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above.</span></span> <span data-ttu-id="9b10c-476">IOS デバイスでは、iOS 8.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9b10c-476">For iOS devices, it’s supported for iOS 8.0 and above</span></span>|
||<span data-ttu-id="9b10c-477">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="9b10c-477">Password expiration (days)</span></span>|<span data-ttu-id="9b10c-478">41</span><span class="sxs-lookup"><span data-stu-id="9b10c-478">41</span></span>||
||<span data-ttu-id="9b10c-479">再利用を防止するための以前のパスワードの数</span><span class="sxs-lookup"><span data-stu-id="9b10c-479">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="9b10c-480">5</span><span class="sxs-lookup"><span data-stu-id="9b10c-480">5</span></span>||
||<span data-ttu-id="9b10c-481">デバイスがアイドル状態から戻るときにパスワードを要求する (Mobile および Holographic)</span><span class="sxs-lookup"><span data-stu-id="9b10c-481">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="9b10c-482">必須</span><span class="sxs-lookup"><span data-stu-id="9b10c-482">Require</span></span>|<span data-ttu-id="9b10c-483">Windows 10 以降で使用可能</span><span class="sxs-lookup"><span data-stu-id="9b10c-483">Available for Windows 10 and later</span></span>|
|<span data-ttu-id="9b10c-484">暗号化</span><span class="sxs-lookup"><span data-stu-id="9b10c-484">Encryption</span></span>|<span data-ttu-id="9b10c-485">デバイス上のデータストレージの暗号化</span><span class="sxs-lookup"><span data-stu-id="9b10c-485">Encryption of data storage on device</span></span>|<span data-ttu-id="9b10c-486">必須</span><span class="sxs-lookup"><span data-stu-id="9b10c-486">Require</span></span>||
|<span data-ttu-id="9b10c-487">デバイスのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="9b10c-487">Device Security</span></span>|<span data-ttu-id="9b10c-488">ウォール</span><span class="sxs-lookup"><span data-stu-id="9b10c-488">Firewall</span></span>|<span data-ttu-id="9b10c-489">必須</span><span class="sxs-lookup"><span data-stu-id="9b10c-489">Require</span></span>||
||<span data-ttu-id="9b10c-490">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="9b10c-490">Antivirus</span></span>|<span data-ttu-id="9b10c-491">必須</span><span class="sxs-lookup"><span data-stu-id="9b10c-491">Require</span></span>||
||<span data-ttu-id="9b10c-492">ウェア</span><span class="sxs-lookup"><span data-stu-id="9b10c-492">Antispyware</span></span>|<span data-ttu-id="9b10c-493">必須</span><span class="sxs-lookup"><span data-stu-id="9b10c-493">Require</span></span>|<span data-ttu-id="9b10c-494">この設定には、Windows セキュリティセンターに登録されたスパイウェア対策ソリューションが必要です</span><span class="sxs-lookup"><span data-stu-id="9b10c-494">This setting requires an Anti-Spyware solution registered with Windows Security Center</span></span>|
|<span data-ttu-id="9b10c-495">守護</span><span class="sxs-lookup"><span data-stu-id="9b10c-495">Defender</span></span>|<span data-ttu-id="9b10c-496">Windows Defender マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="9b10c-496">Windows Defender Antimalware</span></span>|<span data-ttu-id="9b10c-497">必須</span><span class="sxs-lookup"><span data-stu-id="9b10c-497">Require</span></span>||
||<span data-ttu-id="9b10c-498">Windows Defender マルウェア対策の最小バージョン</span><span class="sxs-lookup"><span data-stu-id="9b10c-498">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="9b10c-499">Windows 10 デスクトップでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9b10c-499">Only supported for Windows 10 desktop.</span></span> <span data-ttu-id="9b10c-500">Microsoft では、最新バージョン以降のバージョンを5つ以下にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b10c-500">Microsoft recommends versions no more than five behind from the most recent version</span></span>|
||<span data-ttu-id="9b10c-501">Windows Defender マルウェア対策の署名が最新の状態になっています</span><span class="sxs-lookup"><span data-stu-id="9b10c-501">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="9b10c-502">必須</span><span class="sxs-lookup"><span data-stu-id="9b10c-502">Require</span></span>||
||<span data-ttu-id="9b10c-503">リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="9b10c-503">Real-time protection</span></span>|<span data-ttu-id="9b10c-504">必須</span><span class="sxs-lookup"><span data-stu-id="9b10c-504">Require</span></span>|<span data-ttu-id="9b10c-505">Windows 10 デスクトップでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="9b10c-505">Only supported for Windows 10 desktop</span></span>|

<span data-ttu-id="9b10c-506">**Microsoft Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="9b10c-506">**Microsoft Defender ATP**</span></span>

|<span data-ttu-id="9b10c-507">型</span><span class="sxs-lookup"><span data-stu-id="9b10c-507">Type</span></span>|<span data-ttu-id="9b10c-508">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="9b10c-508">Properties</span></span>|<span data-ttu-id="9b10c-509">値</span><span class="sxs-lookup"><span data-stu-id="9b10c-509">Values</span></span>|<span data-ttu-id="9b10c-510">注</span><span class="sxs-lookup"><span data-stu-id="9b10c-510">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="9b10c-511">Microsoft Defender Advanced Threat Protection ルール</span><span class="sxs-lookup"><span data-stu-id="9b10c-511">Microsoft Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="9b10c-512">デバイスがコンピューターのリスクスコアの下または下にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b10c-512">Require the device to be at or under the machine-risk score</span></span>|<span data-ttu-id="9b10c-513">中</span><span class="sxs-lookup"><span data-stu-id="9b10c-513">Medium</span></span>||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="9b10c-514">準拠 Pc を必要とする (ただし、準拠する電話やタブレットではない)</span><span class="sxs-lookup"><span data-stu-id="9b10c-514">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="9b10c-515">準拠している Pc を必要とするポリシーを追加する前に、管理するデバイスを Intune に登録してください。</span><span class="sxs-lookup"><span data-stu-id="9b10c-515">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune.</span></span> <span data-ttu-id="9b10c-516">デバイスが目的のユーザーを所有していることを保証するために、デバイスを Intune に登録する前に、多要素認証を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b10c-516">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="9b10c-517">準拠している Pc を要求するには:</span><span class="sxs-lookup"><span data-stu-id="9b10c-517">To require compliant PCs:</span></span>

1. <span data-ttu-id="9b10c-518">[Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="9b10c-518">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="9b10c-519">サインインに成功すると、Azure ダッシュボードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-519">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="9b10c-520">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-520">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="9b10c-521">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-521">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="9b10c-522">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-522">Choose **New policy**.</span></span>

5. <span data-ttu-id="9b10c-523">ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-523">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="9b10c-524">**[クラウド アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-524">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="9b10c-525">**[アプリの選択**] を選択し、[**クラウドアプリ**] リストから目的のアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-525">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="9b10c-526">たとえば、[Office 365 Exchange Online] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-526">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="9b10c-527">**[選択**して**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-527">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="9b10c-528">準拠している Pc を必要とするが、準拠している電話やタブレットではないものを要求するには、**条件**と**デバイスプラットフォーム**を選択します</span><span class="sxs-lookup"><span data-stu-id="9b10c-528">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**.</span></span> <span data-ttu-id="9b10c-529">**[Select device プラットフォーム]** を選択して、[ **Windows**と**macOS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-529">Choose **Select device platforms** and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="9b10c-530">**[アクセス制御]** セクションから **[許可]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-530">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="9b10c-531">[**アクセス許可**] を選択し、[**デバイスが準拠していることをマークする必要がある**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-531">Choose **Grant access**, select **Require device to be marked as compliant**.</span></span> <span data-ttu-id="9b10c-532">複数のコントロールの場合は、[選択し**たすべてのコントロールを必要とする**] を選択し、[**選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-532">For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="9b10c-533">[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-533">Choose **Create**.</span></span>

<span data-ttu-id="9b10c-534">準拠している Pc*と*モバイルデバイスを必要とする目的では、プラットフォームを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="9b10c-534">If your objective is to require compliant PCs *and* mobile devices, do not select platforms.</span></span> <span data-ttu-id="9b10c-535">これにより、すべてのデバイスのコンプライアンスを強制します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-535">This enforces compliance for all devices.</span></span> 

## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="9b10c-536">準拠*して*いる pc とモバイルデバイスが必要</span><span class="sxs-lookup"><span data-stu-id="9b10c-536">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="9b10c-537">すべてのデバイスのコンプライアンスを要求するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="9b10c-537">To require compliance for all devices:</span></span>

1. <span data-ttu-id="9b10c-538">[Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="9b10c-538">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="9b10c-539">サインインに成功すると、Azure ダッシュボードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-539">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="9b10c-540">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-540">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="9b10c-541">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-541">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="9b10c-542">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-542">Choose **New policy**.</span></span>

5. <span data-ttu-id="9b10c-543">ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-543">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="9b10c-544">**[クラウド アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-544">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="9b10c-545">**[アプリの選択**] を選択し、[**クラウドアプリ**] リストから目的のアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-545">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="9b10c-546">たとえば、[Office 365 Exchange Online] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-546">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="9b10c-547">**[選択**して**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-547">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="9b10c-548">**[アクセス制御]** セクションから **[許可]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-548">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="9b10c-549">[**アクセス許可**] を選択し、[**デバイスが準拠していることをマークする必要がある**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-549">Choose **Grant access**, select **Require device to be marked as compliant**.</span></span> <span data-ttu-id="9b10c-550">複数のコントロールの場合は、[選択し**たすべてのコントロールを必要とする**] を選択し、[**選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-550">For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="9b10c-551">[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b10c-551">Choose **Create**.</span></span>

<span data-ttu-id="9b10c-552">このポリシーを作成するときは、プラットフォームを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="9b10c-552">When creating this policy, do not select platforms.</span></span> <span data-ttu-id="9b10c-553">これにより、準拠しているデバイスが強制できます。</span><span class="sxs-lookup"><span data-stu-id="9b10c-553">This enforces compliant devices.</span></span>


## <a name="next-steps"></a><span data-ttu-id="9b10c-554">次のステップ</span><span class="sxs-lookup"><span data-stu-id="9b10c-554">Next steps</span></span>

[<span data-ttu-id="9b10c-555">電子メールをセキュリティで保護するためのポリシーの推奨事項について学びます</span><span class="sxs-lookup"><span data-stu-id="9b10c-555">Learn about policy recommendations for securing email</span></span>](secure-email-recommended-policies.md)
