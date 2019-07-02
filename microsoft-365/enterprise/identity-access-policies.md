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
ms.openlocfilehash: 322da1ccfbd0cf8b5070894580b06fb5b0283f40
ms.sourcegitcommit: 1d5fc181036b673c4f0b9e161e19395dbfe5a304
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2019
ms.locfileid: "35411651"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="38275-103">共通 ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="38275-103">Common identity and device access policies</span></span>
<span data-ttu-id="38275-104">この記事では、Azure AD Application Proxy で公開されているオンプレミスアプリケーションを含む、クラウドサービスへのアクセスを保護するための一般的な推奨ポリシーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="38275-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="38275-105">このガイダンスでは、新しくプロビジョニングされた環境に推奨されるポリシーを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="38275-105">This guidance discusses how to deploy the recommended policies in a newly-provisioned environment.</span></span> <span data-ttu-id="38275-106">個別のラボ環境でこれらのポリシーを設定することにより、展開をステージングおよび運用環境にステージングする前に、推奨ポリシーを理解し、評価することができます。</span><span class="sxs-lookup"><span data-stu-id="38275-106">Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your preproduction and production environments.</span></span> <span data-ttu-id="38275-107">新しくプロビジョニングされた環境は、クラウド専用またはハイブリッドの場合があります。</span><span class="sxs-lookup"><span data-stu-id="38275-107">Your newly provisioned environment may be cloud-only or hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="38275-108">ポリシーセット</span><span class="sxs-lookup"><span data-stu-id="38275-108">Policy set</span></span> 

<span data-ttu-id="38275-109">次の図は、推奨されるポリシーセットを示しています。</span><span class="sxs-lookup"><span data-stu-id="38275-109">The following diagram illustrates the recommended set of policies.</span></span> <span data-ttu-id="38275-110">この図は、各ポリシーが適用される保護層と、それらのポリシーが Pc、電話、タブレット、または両方のカテゴリのデバイスに適用されるかどうかを示しています。</span><span class="sxs-lookup"><span data-stu-id="38275-110">It shows which tier of protections each policy applies to and whether the policies apply to PCs or phones and tablets, or both categories of devices.</span></span> <span data-ttu-id="38275-111">また、これらのポリシーが構成されている場所も示されます。</span><span class="sxs-lookup"><span data-stu-id="38275-111">It also indicates where these policies are configured.</span></span>

![Id とデバイスのアクセスを構成するための一般的なポリシー](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="38275-113">この記事の残りの部分では、これらのポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="38275-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="38275-114">デバイスが目的のユーザーを所有していることを保証するために、デバイスを Intune に登録する前に、多要素認証を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="38275-114">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> <span data-ttu-id="38275-115">デバイスコンプライアンスポリシーを適用する前に、デバイスを Intune に登録する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="38275-115">You must also enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="38275-116">これらのタスクを実行するための時間を提供するために、この表に記載されている順序で基準ポリシーを実装することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="38275-116">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table.</span></span> <span data-ttu-id="38275-117">ただし、機密性が高く規制された保護のための MFA ポリシーは、いつでも実装できます。</span><span class="sxs-lookup"><span data-stu-id="38275-117">However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="38275-118">保護レベル</span><span class="sxs-lookup"><span data-stu-id="38275-118">Protection level</span></span>|<span data-ttu-id="38275-119">ポリシー</span><span class="sxs-lookup"><span data-stu-id="38275-119">Policies</span></span>|<span data-ttu-id="38275-120">詳細情報</span><span class="sxs-lookup"><span data-stu-id="38275-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="38275-121">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="38275-121">**Baseline**</span></span>|[<span data-ttu-id="38275-122">サインインリスクが*中*または*高*の場合は MFA を必須にする</span><span class="sxs-lookup"><span data-stu-id="38275-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|        |[<span data-ttu-id="38275-123">モダン認証をサポートしていないクライアントをブロックする</span><span class="sxs-lookup"><span data-stu-id="38275-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="38275-124">モダン認証を使用していないクライアントは、条件付きアクセスルールをバイパスすることができます。そのため、これらをブロックすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="38275-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these</span></span>|
|        |[<span data-ttu-id="38275-125">リスクの高いユーザーがパスワードを変更する必要がある</span><span class="sxs-lookup"><span data-stu-id="38275-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="38275-126">アカウントに対して高リスクのアクティビティが検出された場合に、サインイン時にユーザーにパスワードを変更することを強制します。</span><span class="sxs-lookup"><span data-stu-id="38275-126">Forces users to change their password when signing in if high-risk activity is detected for their account</span></span>|
|        |[<span data-ttu-id="38275-127">アプリ保護ポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="38275-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="38275-128">プラットフォームごとに1つのポリシー (iOS、Android、Windows)。</span><span class="sxs-lookup"><span data-stu-id="38275-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="38275-129">承認済みアプリの要求</span><span class="sxs-lookup"><span data-stu-id="38275-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="38275-130">携帯電話とタブレットにモバイルアプリの保護を適用する</span><span class="sxs-lookup"><span data-stu-id="38275-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="38275-131">デバイスコンプライアンスポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="38275-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="38275-132">プラットフォームごとに1つのポリシー</span><span class="sxs-lookup"><span data-stu-id="38275-132">One policy for each platform</span></span>|
|        |[<span data-ttu-id="38275-133">準拠している Pc が必要</span><span class="sxs-lookup"><span data-stu-id="38275-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="38275-134">Pc の Intune 管理を強制する</span><span class="sxs-lookup"><span data-stu-id="38275-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="38275-135">**機密**</span><span class="sxs-lookup"><span data-stu-id="38275-135">**Sensitive**</span></span>|[<span data-ttu-id="38275-136">サインインリスクが*低*、*中*、*高*のときに MFA を必要とする</span><span class="sxs-lookup"><span data-stu-id="38275-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="38275-137">準拠*して*いる pc とモバイルデバイスが必要</span><span class="sxs-lookup"><span data-stu-id="38275-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="38275-138">Pc と携帯電話/タブレットに Intune 管理を強制する</span><span class="sxs-lookup"><span data-stu-id="38275-138">Enforces Intune management for PCs and phone/tablets</span></span>|
|<span data-ttu-id="38275-139">**高度な規制**</span><span class="sxs-lookup"><span data-stu-id="38275-139">**Highly regulated**</span></span>|[<span data-ttu-id="38275-140">*常に*MFA が必要</span><span class="sxs-lookup"><span data-stu-id="38275-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="38275-141">ユーザーへのポリシーの割り当て</span><span class="sxs-lookup"><span data-stu-id="38275-141">Assigning policies to users</span></span>
<span data-ttu-id="38275-142">ポリシーを構成する前に、各層の保護に使用している Azure AD グループを特定します。</span><span class="sxs-lookup"><span data-stu-id="38275-142">Before configuring policies, identify the Azure AD groups you are using for each tier of protection.</span></span> <span data-ttu-id="38275-143">通常、ベースライン保護は組織内の全員に適用されます。</span><span class="sxs-lookup"><span data-stu-id="38275-143">Typically, baseline protection applies to everybody in the organization.</span></span> <span data-ttu-id="38275-144">ベースラインと機密保護の両方に含まれているユーザーには、適用されているすべてのベースラインポリシーと、機密ポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="38275-144">A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies.</span></span> <span data-ttu-id="38275-145">保護は累積され、最も制限の厳しいポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="38275-145">Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="38275-146">条件付きアクセスの除外に対して Azure AD グループを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="38275-146">A recommended practice is to create an Azure AD group for conditional access exclusion.</span></span> <span data-ttu-id="38275-147">[除外] の下にあるすべての条件付きアクセスルールにこのグループを追加します。</span><span class="sxs-lookup"><span data-stu-id="38275-147">Add this group to all of your conditional access rules under "Exclude".</span></span> <span data-ttu-id="38275-148">これにより、アクセスの問題のトラブルシューティングを行っている間、ユーザーにアクセス権を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="38275-148">This gives you a method to provide access to a user while you troubleshoot access issues.</span></span> <span data-ttu-id="38275-149">これは、一時的なソリューションとしてのみお勧めします。</span><span class="sxs-lookup"><span data-stu-id="38275-149">This is recommended as a temporary solution only.</span></span> <span data-ttu-id="38275-150">このグループを監視して変更を確認し、除外グループが意図したとおりにのみ使用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="38275-150">Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="38275-151">次の図は、ユーザーの割り当てと除外の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="38275-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![MFA ルールのユーザー割り当てと除外の例](../images/identity-access-policies-assignment.png)

<span data-ttu-id="38275-153">図では、"Top secret プロジェクト X teams" には、MFA を必要とする条件\*\* 付きアクセスポリシーが割り当てられています。</span><span class="sxs-lookup"><span data-stu-id="38275-153">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*.</span></span> <span data-ttu-id="38275-154">ユーザーにより高度な保護を適用する場合は、慎重に行います。</span><span class="sxs-lookup"><span data-stu-id="38275-154">Be judicious when applying higher levels of protection to users.</span></span> <span data-ttu-id="38275-155">このプロジェクトチームのメンバーは、厳しく規制されたコンテンツを表示していない場合でも、ログオンするたびに2つの形式の認証を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38275-155">Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly-regulated content.</span></span>  

<span data-ttu-id="38275-156">これらの推奨事項の一部として作成されたすべての Azure AD グループは、Office 365 グループとして作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38275-156">All Azure AD groups created as part of these recommendations must be created as Office 365 groups.</span></span> <span data-ttu-id="38275-157">これは、SharePoint Online のドキュメントをセキュリティで保護する場合の Azure Information Protection (AIP) の展開で特に重要です。</span><span class="sxs-lookup"><span data-stu-id="38275-157">This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![Office 365 グループを作成するための画面キャプチャ](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="38275-159">サインインリスクに基づいて MFA を必須にする</span><span class="sxs-lookup"><span data-stu-id="38275-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="38275-160">MFA を必要とする前に、まず Identity Protection MFA 登録ポリシーを使用して、MFA のユーザーを登録します。</span><span class="sxs-lookup"><span data-stu-id="38275-160">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA.</span></span> <span data-ttu-id="38275-161">ユーザーが登録されたら、サインインに MFA を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="38275-161">After users are registered you can enforce MFA for sign-in.</span></span> <span data-ttu-id="38275-162">[前提条件](identity-access-prerequisites.md)となるのは、すべてのユーザーを MFA で登録することです。</span><span class="sxs-lookup"><span data-stu-id="38275-162">The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="38275-163">条件付きアクセス ポリシーを作成するには:</span><span class="sxs-lookup"><span data-stu-id="38275-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="38275-164">[Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="38275-164">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="38275-165">サインインに成功すると、Azure ダッシュボードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38275-165">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="38275-166">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="38275-167">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="38275-168">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-168">Choose **New policy**.</span></span>

![ベースラインとなる CA ポリシー](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="38275-170">次の表では、このポリシーに対して実装する条件付きアクセスポリシー設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="38275-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="38275-171">**Assignments**</span><span class="sxs-lookup"><span data-stu-id="38275-171">**Assignments**</span></span>

|<span data-ttu-id="38275-172">型</span><span class="sxs-lookup"><span data-stu-id="38275-172">Type</span></span>|<span data-ttu-id="38275-173">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="38275-173">Properties</span></span>|<span data-ttu-id="38275-174">値</span><span class="sxs-lookup"><span data-stu-id="38275-174">Values</span></span>|<span data-ttu-id="38275-175">注</span><span class="sxs-lookup"><span data-stu-id="38275-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="38275-176">ユーザーとグループ</span><span class="sxs-lookup"><span data-stu-id="38275-176">Users and groups</span></span>|<span data-ttu-id="38275-177">含める</span><span class="sxs-lookup"><span data-stu-id="38275-177">Include</span></span>|<span data-ttu-id="38275-178">ユーザーとグループの選択 – 対象ユーザーを含む特定のセキュリティ グループを選択します</span><span class="sxs-lookup"><span data-stu-id="38275-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="38275-179">パイロット ユーザーを含むセキュリティ グループから開始します</span><span class="sxs-lookup"><span data-stu-id="38275-179">Start with security group including pilot users</span></span>|
||<span data-ttu-id="38275-180">除外</span><span class="sxs-lookup"><span data-stu-id="38275-180">Exclude</span></span>|<span data-ttu-id="38275-181">例外セキュリティ グループ、サービス アカウント (アプリ ID)</span><span class="sxs-lookup"><span data-stu-id="38275-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="38275-182">必要に応じて変更されたメンバーシップの一時的根拠</span><span class="sxs-lookup"><span data-stu-id="38275-182">Membership modified on an as-needed temporary basis</span></span>|
|<span data-ttu-id="38275-183">クラウド アプリ</span><span class="sxs-lookup"><span data-stu-id="38275-183">Cloud apps</span></span>|<span data-ttu-id="38275-184">含める</span><span class="sxs-lookup"><span data-stu-id="38275-184">Include</span></span>|<span data-ttu-id="38275-185">このルールを適用するアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-185">Select the apps you want this rule to apply to.</span></span> <span data-ttu-id="38275-186">たとえば、[Office 365 Exchange Online] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-186">For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="38275-187">条件</span><span class="sxs-lookup"><span data-stu-id="38275-187">Conditions</span></span>|<span data-ttu-id="38275-188">構成済み</span><span class="sxs-lookup"><span data-stu-id="38275-188">Configured</span></span>|<span data-ttu-id="38275-189">はい</span><span class="sxs-lookup"><span data-stu-id="38275-189">Yes</span></span>|<span data-ttu-id="38275-190">使用環境およびニーズに合わせて構成します</span><span class="sxs-lookup"><span data-stu-id="38275-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="38275-191">サインイン リスク</span><span class="sxs-lookup"><span data-stu-id="38275-191">Sign-in risk</span></span>|<span data-ttu-id="38275-192">リスク レベル</span><span class="sxs-lookup"><span data-stu-id="38275-192">Risk level</span></span>||<span data-ttu-id="38275-193">次の表のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38275-193">See the guidance in the following table</span></span>|

<span data-ttu-id="38275-194">**サインイン リスク**</span><span class="sxs-lookup"><span data-stu-id="38275-194">**Sign-in risk**</span></span>

<span data-ttu-id="38275-195">対象とする保護レベルに基づいて設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="38275-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="38275-196">プロパティ</span><span class="sxs-lookup"><span data-stu-id="38275-196">Property</span></span>|<span data-ttu-id="38275-197">保護レベル</span><span class="sxs-lookup"><span data-stu-id="38275-197">Level of protection</span></span>|<span data-ttu-id="38275-198">値</span><span class="sxs-lookup"><span data-stu-id="38275-198">Values</span></span>|<span data-ttu-id="38275-199">注</span><span class="sxs-lookup"><span data-stu-id="38275-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="38275-200">リスク レベル</span><span class="sxs-lookup"><span data-stu-id="38275-200">Risk level</span></span>|<span data-ttu-id="38275-201">基準</span><span class="sxs-lookup"><span data-stu-id="38275-201">Baseline</span></span>|<span data-ttu-id="38275-202">高、中</span><span class="sxs-lookup"><span data-stu-id="38275-202">High, medium</span></span>|<span data-ttu-id="38275-203">両方をチェック</span><span class="sxs-lookup"><span data-stu-id="38275-203">Check both</span></span>|
| |<span data-ttu-id="38275-204">機密</span><span class="sxs-lookup"><span data-stu-id="38275-204">Sensitive</span></span>|<span data-ttu-id="38275-205">高、中、低</span><span class="sxs-lookup"><span data-stu-id="38275-205">High, medium, low</span></span>|<span data-ttu-id="38275-206">3 つすべてチェック</span><span class="sxs-lookup"><span data-stu-id="38275-206">Check all three</span></span>|
| |<span data-ttu-id="38275-207">高度な規制</span><span class="sxs-lookup"><span data-stu-id="38275-207">Highly regulated</span></span>| |<span data-ttu-id="38275-208">すべてのオプションをオフのままにして、常に MFA を強制する</span><span class="sxs-lookup"><span data-stu-id="38275-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="38275-209">**アクセス制御**</span><span class="sxs-lookup"><span data-stu-id="38275-209">**Access controls**</span></span>

|<span data-ttu-id="38275-210">型</span><span class="sxs-lookup"><span data-stu-id="38275-210">Type</span></span>|<span data-ttu-id="38275-211">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="38275-211">Properties</span></span>|<span data-ttu-id="38275-212">値</span><span class="sxs-lookup"><span data-stu-id="38275-212">Values</span></span>|<span data-ttu-id="38275-213">注</span><span class="sxs-lookup"><span data-stu-id="38275-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="38275-214">許可</span><span class="sxs-lookup"><span data-stu-id="38275-214">Grant</span></span>|<span data-ttu-id="38275-215">アクセスの許可</span><span class="sxs-lookup"><span data-stu-id="38275-215">Grant access</span></span>|<span data-ttu-id="38275-216">はい</span><span class="sxs-lookup"><span data-stu-id="38275-216">True</span></span>|<span data-ttu-id="38275-217">選択</span><span class="sxs-lookup"><span data-stu-id="38275-217">Selected</span></span>|
||<span data-ttu-id="38275-218">MFA を要求</span><span class="sxs-lookup"><span data-stu-id="38275-218">Require MFA</span></span>|<span data-ttu-id="38275-219">True</span><span class="sxs-lookup"><span data-stu-id="38275-219">True</span></span>|<span data-ttu-id="38275-220">Check</span><span class="sxs-lookup"><span data-stu-id="38275-220">Check</span></span>|
||<span data-ttu-id="38275-221">デバイスを準拠としてマークする必要がある</span><span class="sxs-lookup"><span data-stu-id="38275-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="38275-222">False</span><span class="sxs-lookup"><span data-stu-id="38275-222">False</span></span>||
||<span data-ttu-id="38275-223">ハイブリッドの Azure AD に参加しているデバイスが必要</span><span class="sxs-lookup"><span data-stu-id="38275-223">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="38275-224">False</span><span class="sxs-lookup"><span data-stu-id="38275-224">False</span></span>||
||<span data-ttu-id="38275-225">承認済みクライアントアプリを必要とする</span><span class="sxs-lookup"><span data-stu-id="38275-225">Require approved client app</span></span>|<span data-ttu-id="38275-226">False</span><span class="sxs-lookup"><span data-stu-id="38275-226">False</span></span>||
||<span data-ttu-id="38275-227">選択したコントロールすべてが必要</span><span class="sxs-lookup"><span data-stu-id="38275-227">Require all the selected controls</span></span>|<span data-ttu-id="38275-228">True</span><span class="sxs-lookup"><span data-stu-id="38275-228">True</span></span>|<span data-ttu-id="38275-229">選択</span><span class="sxs-lookup"><span data-stu-id="38275-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="38275-230">**[**] を選択して、このポリシーを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="38275-230">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="38275-231">また、ポリシーをテストする場合は、[[対象](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)] ツールを使用してください。</span><span class="sxs-lookup"><span data-stu-id="38275-231">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="38275-232">モダン認証をサポートしていないクライアントをブロックする</span><span class="sxs-lookup"><span data-stu-id="38275-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="38275-233">[Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="38275-233">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="38275-234">サインインに成功すると、Azure ダッシュボードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38275-234">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="38275-235">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="38275-236">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="38275-237">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-237">Choose **New policy**.</span></span>

<span data-ttu-id="38275-238">次の表では、このポリシーに対して実装する条件付きアクセスポリシー設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="38275-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="38275-239">**Assignments**</span><span class="sxs-lookup"><span data-stu-id="38275-239">**Assignments**</span></span>

|<span data-ttu-id="38275-240">型</span><span class="sxs-lookup"><span data-stu-id="38275-240">Type</span></span>|<span data-ttu-id="38275-241">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="38275-241">Properties</span></span>|<span data-ttu-id="38275-242">値</span><span class="sxs-lookup"><span data-stu-id="38275-242">Values</span></span>|<span data-ttu-id="38275-243">注</span><span class="sxs-lookup"><span data-stu-id="38275-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="38275-244">ユーザーとグループ</span><span class="sxs-lookup"><span data-stu-id="38275-244">Users and groups</span></span>|<span data-ttu-id="38275-245">含める</span><span class="sxs-lookup"><span data-stu-id="38275-245">Include</span></span>|<span data-ttu-id="38275-246">ユーザーとグループの選択 – 対象ユーザーを含む特定のセキュリティ グループを選択します</span><span class="sxs-lookup"><span data-stu-id="38275-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="38275-247">パイロット ユーザーを含むセキュリティ グループから開始します</span><span class="sxs-lookup"><span data-stu-id="38275-247">Start with security group including pilot users</span></span>|
||<span data-ttu-id="38275-248">除外</span><span class="sxs-lookup"><span data-stu-id="38275-248">Exclude</span></span>|<span data-ttu-id="38275-249">例外セキュリティ グループ、サービス アカウント (アプリ ID)</span><span class="sxs-lookup"><span data-stu-id="38275-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="38275-250">必要に応じて一時的にメンバーシップを変更します</span><span class="sxs-lookup"><span data-stu-id="38275-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="38275-251">クラウド アプリ</span><span class="sxs-lookup"><span data-stu-id="38275-251">Cloud apps</span></span>|<span data-ttu-id="38275-252">含める</span><span class="sxs-lookup"><span data-stu-id="38275-252">Include</span></span>|<span data-ttu-id="38275-253">このルールを適用するアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-253">Select the apps you want this rule to apply to.</span></span> <span data-ttu-id="38275-254">たとえば、[Office 365 Exchange Online] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-254">For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="38275-255">条件</span><span class="sxs-lookup"><span data-stu-id="38275-255">Conditions</span></span>|<span data-ttu-id="38275-256">構成済み</span><span class="sxs-lookup"><span data-stu-id="38275-256">Configured</span></span>|<span data-ttu-id="38275-257">はい</span><span class="sxs-lookup"><span data-stu-id="38275-257">Yes</span></span>|<span data-ttu-id="38275-258">クライアントアプリを構成する</span><span class="sxs-lookup"><span data-stu-id="38275-258">Configure Client apps</span></span>|
|<span data-ttu-id="38275-259">クライアントアプリ</span><span class="sxs-lookup"><span data-stu-id="38275-259">Client apps</span></span>|<span data-ttu-id="38275-260">構成済み</span><span class="sxs-lookup"><span data-stu-id="38275-260">Configured</span></span>|<span data-ttu-id="38275-261">はい</span><span class="sxs-lookup"><span data-stu-id="38275-261">Yes</span></span>|<span data-ttu-id="38275-262">モバイルアプリとデスクトップクライアント、その他のクライアント (両方を選択する)</span><span class="sxs-lookup"><span data-stu-id="38275-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="38275-263">**アクセス制御**</span><span class="sxs-lookup"><span data-stu-id="38275-263">**Access controls**</span></span>

|<span data-ttu-id="38275-264">型</span><span class="sxs-lookup"><span data-stu-id="38275-264">Type</span></span>|<span data-ttu-id="38275-265">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="38275-265">Properties</span></span>|<span data-ttu-id="38275-266">値</span><span class="sxs-lookup"><span data-stu-id="38275-266">Values</span></span>|<span data-ttu-id="38275-267">注</span><span class="sxs-lookup"><span data-stu-id="38275-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="38275-268">許可</span><span class="sxs-lookup"><span data-stu-id="38275-268">Grant</span></span>|<span data-ttu-id="38275-269">アクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="38275-269">Block access</span></span>|<span data-ttu-id="38275-270">はい</span><span class="sxs-lookup"><span data-stu-id="38275-270">True</span></span>|<span data-ttu-id="38275-271">選択</span><span class="sxs-lookup"><span data-stu-id="38275-271">Selected</span></span>|
||<span data-ttu-id="38275-272">MFA を要求</span><span class="sxs-lookup"><span data-stu-id="38275-272">Require MFA</span></span>|<span data-ttu-id="38275-273">False</span><span class="sxs-lookup"><span data-stu-id="38275-273">False</span></span>||
||<span data-ttu-id="38275-274">デバイスを準拠としてマークする必要がある</span><span class="sxs-lookup"><span data-stu-id="38275-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="38275-275">False</span><span class="sxs-lookup"><span data-stu-id="38275-275">False</span></span>||
||<span data-ttu-id="38275-276">ハイブリッドの Azure AD に参加しているデバイスが必要</span><span class="sxs-lookup"><span data-stu-id="38275-276">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="38275-277">False</span><span class="sxs-lookup"><span data-stu-id="38275-277">False</span></span>||
||<span data-ttu-id="38275-278">承認済みクライアントアプリを必要とする</span><span class="sxs-lookup"><span data-stu-id="38275-278">Require approved client app</span></span>|<span data-ttu-id="38275-279">False</span><span class="sxs-lookup"><span data-stu-id="38275-279">False</span></span>||
||<span data-ttu-id="38275-280">選択したコントロールすべてが必要</span><span class="sxs-lookup"><span data-stu-id="38275-280">Require all the selected controls</span></span>|<span data-ttu-id="38275-281">True</span><span class="sxs-lookup"><span data-stu-id="38275-281">True</span></span>|<span data-ttu-id="38275-282">選択</span><span class="sxs-lookup"><span data-stu-id="38275-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="38275-283">**[**] を選択して、このポリシーを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="38275-283">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="38275-284">また、ポリシーをテストする場合は、[[対象](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)] ツールを使用してください。</span><span class="sxs-lookup"><span data-stu-id="38275-284">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="38275-285">リスクの高いユーザーがパスワードを変更する必要がある</span><span class="sxs-lookup"><span data-stu-id="38275-285">High risk users must change password</span></span>
<span data-ttu-id="38275-286">すべての危険度の高いユーザーが侵害されたアカウントが、サインイン時にパスワードの変更を強制的に実行するようにするには、次のポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="38275-286">To ensure that all high-risk users' compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="38275-287">管理者資格情報を使用して [Microsoft Azure ポータル (http://portal.azure.com)](http://portal.azure.com/) にログインしてから、**[Azure AD Identity Protection]、[ユーザーのリスク ポリシー]** の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="38275-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="38275-288">**Assignments**</span><span class="sxs-lookup"><span data-stu-id="38275-288">**Assignments**</span></span>

|<span data-ttu-id="38275-289">型</span><span class="sxs-lookup"><span data-stu-id="38275-289">Type</span></span>|<span data-ttu-id="38275-290">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="38275-290">Properties</span></span>|<span data-ttu-id="38275-291">値</span><span class="sxs-lookup"><span data-stu-id="38275-291">Values</span></span>|<span data-ttu-id="38275-292">注</span><span class="sxs-lookup"><span data-stu-id="38275-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="38275-293">Users</span><span class="sxs-lookup"><span data-stu-id="38275-293">Users</span></span>|<span data-ttu-id="38275-294">含める</span><span class="sxs-lookup"><span data-stu-id="38275-294">Include</span></span>|<span data-ttu-id="38275-295">[すべてのユーザー]</span><span class="sxs-lookup"><span data-stu-id="38275-295">All users</span></span>|<span data-ttu-id="38275-296">オン</span><span class="sxs-lookup"><span data-stu-id="38275-296">Selected</span></span>|
||<span data-ttu-id="38275-297">除外</span><span class="sxs-lookup"><span data-stu-id="38275-297">Exclude</span></span>|<span data-ttu-id="38275-298">なし</span><span class="sxs-lookup"><span data-stu-id="38275-298">None</span></span>||
|<span data-ttu-id="38275-299">条件</span><span class="sxs-lookup"><span data-stu-id="38275-299">Conditions</span></span>|<span data-ttu-id="38275-300">ユーザーのリスク</span><span class="sxs-lookup"><span data-stu-id="38275-300">User risk</span></span>|<span data-ttu-id="38275-301">高</span><span class="sxs-lookup"><span data-stu-id="38275-301">High</span></span>|<span data-ttu-id="38275-302">オン</span><span class="sxs-lookup"><span data-stu-id="38275-302">Selected</span></span>|

<span data-ttu-id="38275-303">**コントロール**</span><span class="sxs-lookup"><span data-stu-id="38275-303">**Controls**</span></span>

| <span data-ttu-id="38275-304">型</span><span class="sxs-lookup"><span data-stu-id="38275-304">Type</span></span> | <span data-ttu-id="38275-305">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="38275-305">Properties</span></span> | <span data-ttu-id="38275-306">値</span><span class="sxs-lookup"><span data-stu-id="38275-306">Values</span></span>                  | <span data-ttu-id="38275-307">注</span><span class="sxs-lookup"><span data-stu-id="38275-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="38275-308">Access</span><span class="sxs-lookup"><span data-stu-id="38275-308">Access</span></span>     | <span data-ttu-id="38275-309">SSL 経由でのみ</span><span class="sxs-lookup"><span data-stu-id="38275-309">Allow access</span></span>            | <span data-ttu-id="38275-310">はい</span><span class="sxs-lookup"><span data-stu-id="38275-310">True</span></span>  |
|      | <span data-ttu-id="38275-311">Access</span><span class="sxs-lookup"><span data-stu-id="38275-311">Access</span></span>     | <span data-ttu-id="38275-312">パスワードの変更を必須とする</span><span class="sxs-lookup"><span data-stu-id="38275-312">Require password change</span></span> | <span data-ttu-id="38275-313">True</span><span class="sxs-lookup"><span data-stu-id="38275-313">True</span></span>  |

<span data-ttu-id="38275-314">**レビュー:** 該当なし</span><span class="sxs-lookup"><span data-stu-id="38275-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="38275-315">**[**] を選択して、このポリシーを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="38275-315">Be sure to enable this policy, by choosing **On**.</span></span> <span data-ttu-id="38275-316">ポリシーをテストする[場合](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)は、[対象] ツールを使用することも検討してください。</span><span class="sxs-lookup"><span data-stu-id="38275-316">Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="38275-317">アプリ保護ポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="38275-317">Define app protection policies</span></span>
<span data-ttu-id="38275-318">アプリ保護ポリシーは、許可されるアプリと、組織のデータによって実行できるアクションを定義します。</span><span class="sxs-lookup"><span data-stu-id="38275-318">App protection policies define which apps are allowed and the actions they can take with your organization's data.</span></span> <span data-ttu-id="38275-319">Azure ポータル内から Intune アプリ保護ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="38275-319">Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="38275-320">プラットフォームごとにポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="38275-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="38275-321">iOS</span><span class="sxs-lookup"><span data-stu-id="38275-321">iOS</span></span>
- <span data-ttu-id="38275-322">Android</span><span class="sxs-lookup"><span data-stu-id="38275-322">Android</span></span>
- <span data-ttu-id="38275-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="38275-323">Windows 10</span></span>

<span data-ttu-id="38275-324">新しいアプリ保護ポリシーを作成するには、管理者の資格情報を使用して Microsoft Azure portal にログインしてから、[**モバイルアプリ] > [アプリ保護ポリシー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="38275-324">To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Mobile apps > App protection policies**.</span></span> <span data-ttu-id="38275-325">[**ポリシーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-325">Choose **Add a policy**.</span></span>

<span data-ttu-id="38275-326">iOS と Android では、アプリ保護ポリシーのオプションが若干異なります。</span><span class="sxs-lookup"><span data-stu-id="38275-326">There are slight differences in the app protection policy options between iOS and Android.</span></span> <span data-ttu-id="38275-327">以下のポリシーは Android 専用です。</span><span class="sxs-lookup"><span data-stu-id="38275-327">The below policy is specifically for Android.</span></span> <span data-ttu-id="38275-328">他のポリシーのガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="38275-328">Use this as a guide for your other policies.</span></span>

<span data-ttu-id="38275-329">推奨されるアプリの一覧には、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="38275-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="38275-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="38275-330">PowerPoint</span></span>
- <span data-ttu-id="38275-331">Excel</span><span class="sxs-lookup"><span data-stu-id="38275-331">Excel</span></span>
- <span data-ttu-id="38275-332">Word</span><span class="sxs-lookup"><span data-stu-id="38275-332">Word</span></span>
- <span data-ttu-id="38275-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38275-333">Microsoft Teams</span></span>
- <span data-ttu-id="38275-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="38275-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="38275-335">Microsoft Visio Viewer</span><span class="sxs-lookup"><span data-stu-id="38275-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="38275-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="38275-336">OneDrive</span></span>
- <span data-ttu-id="38275-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="38275-337">OneNote</span></span>
- <span data-ttu-id="38275-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="38275-338">Outlook</span></span>

<span data-ttu-id="38275-339">推奨される設定を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="38275-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="38275-340">型</span><span class="sxs-lookup"><span data-stu-id="38275-340">Type</span></span>|<span data-ttu-id="38275-341">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="38275-341">Properties</span></span>|<span data-ttu-id="38275-342">値</span><span class="sxs-lookup"><span data-stu-id="38275-342">Values</span></span>|<span data-ttu-id="38275-343">注</span><span class="sxs-lookup"><span data-stu-id="38275-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="38275-344">データ再配置</span><span class="sxs-lookup"><span data-stu-id="38275-344">Data relocation</span></span>|<span data-ttu-id="38275-345">[Android でのバックアップを禁止する]</span><span class="sxs-lookup"><span data-stu-id="38275-345">Prevent Android backup</span></span>|<span data-ttu-id="38275-346">はい</span><span class="sxs-lookup"><span data-stu-id="38275-346">Yes</span></span>|<span data-ttu-id="38275-347">iOS では、特に iTunes と iCloud が呼び出されます</span><span class="sxs-lookup"><span data-stu-id="38275-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="38275-348">[アプリで他のアプリへのデータ転送を許可する]</span><span class="sxs-lookup"><span data-stu-id="38275-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="38275-349">ポリシーで管理されているアプリ</span><span class="sxs-lookup"><span data-stu-id="38275-349">Policy managed apps</span></span>||
||<span data-ttu-id="38275-350">このアプリで他のアプリからデータを受信できるようにする</span><span class="sxs-lookup"><span data-stu-id="38275-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="38275-351">ポリシーで管理されているアプリ</span><span class="sxs-lookup"><span data-stu-id="38275-351">Policy managed apps</span></span>||
||<span data-ttu-id="38275-352">[名前を付けて保存] を禁止する</span><span class="sxs-lookup"><span data-stu-id="38275-352">Prevent "Save As"</span></span>|<span data-ttu-id="38275-353">はい</span><span class="sxs-lookup"><span data-stu-id="38275-353">Yes</span></span>||
||<span data-ttu-id="38275-354">会社のデータを保存できるストレージ サービスの選択</span><span class="sxs-lookup"><span data-stu-id="38275-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="38275-355">OneDrive for Business、SharePoint</span><span class="sxs-lookup"><span data-stu-id="38275-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="38275-356">他のアプリとの間で切り取り、コピー、貼り付けを制限する</span><span class="sxs-lookup"><span data-stu-id="38275-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="38275-357">貼り付けられたポリシー管理対象アプリ</span><span class="sxs-lookup"><span data-stu-id="38275-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="38275-358">Web コンテンツを管理対象ブラウザーで表示するように制限する</span><span class="sxs-lookup"><span data-stu-id="38275-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="38275-359">いいえ</span><span class="sxs-lookup"><span data-stu-id="38275-359">No</span></span>||
||<span data-ttu-id="38275-360">[アプリ データの暗号化]</span><span class="sxs-lookup"><span data-stu-id="38275-360">Encrypt app data</span></span>|<span data-ttu-id="38275-361">はい</span><span class="sxs-lookup"><span data-stu-id="38275-361">Yes</span></span>|<span data-ttu-id="38275-362">iOS では、[デバイスがロックされている場合] オプションを選択します</span><span class="sxs-lookup"><span data-stu-id="38275-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="38275-363">デバイスが有効な場合はアプリの暗号化を無効にする</span><span class="sxs-lookup"><span data-stu-id="38275-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="38275-364">はい</span><span class="sxs-lookup"><span data-stu-id="38275-364">Yes</span></span>|<span data-ttu-id="38275-365">二重暗号化を回避するためにこの設定を無効にする</span><span class="sxs-lookup"><span data-stu-id="38275-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="38275-366">連絡先の同期を無効にする</span><span class="sxs-lookup"><span data-stu-id="38275-366">Disable contacts sync</span></span>|<span data-ttu-id="38275-367">いいえ</span><span class="sxs-lookup"><span data-stu-id="38275-367">No</span></span>||
||<span data-ttu-id="38275-368">印刷を無効にする</span><span class="sxs-lookup"><span data-stu-id="38275-368">Disable printing</span></span>|<span data-ttu-id="38275-369">いいえ</span><span class="sxs-lookup"><span data-stu-id="38275-369">No</span></span>||
|<span data-ttu-id="38275-370">アクセス</span><span class="sxs-lookup"><span data-stu-id="38275-370">Access</span></span>|<span data-ttu-id="38275-371">アクセスのために PIN を要求する</span><span class="sxs-lookup"><span data-stu-id="38275-371">Require PIN for access</span></span>|<span data-ttu-id="38275-372">はい</span><span class="sxs-lookup"><span data-stu-id="38275-372">Yes</span></span>||
||<span data-ttu-id="38275-373">種類の選択</span><span class="sxs-lookup"><span data-stu-id="38275-373">Select Type</span></span>|<span data-ttu-id="38275-374">数値</span><span class="sxs-lookup"><span data-stu-id="38275-374">Numeric</span></span>||
||<span data-ttu-id="38275-375">単純な PIN を許可する</span><span class="sxs-lookup"><span data-stu-id="38275-375">Allow simple PIN</span></span>|<span data-ttu-id="38275-376">いいえ</span><span class="sxs-lookup"><span data-stu-id="38275-376">No</span></span>||
||<span data-ttu-id="38275-377">PIN の長さ</span><span class="sxs-lookup"><span data-stu-id="38275-377">PIN length</span></span>|<span data-ttu-id="38275-378">シックス</span><span class="sxs-lookup"><span data-stu-id="38275-378">6</span></span>||
||<span data-ttu-id="38275-379">PIN の代わりに指紋を要求する</span><span class="sxs-lookup"><span data-stu-id="38275-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="38275-380">はい</span><span class="sxs-lookup"><span data-stu-id="38275-380">Yes</span></span>||
||<span data-ttu-id="38275-381">デバイス PIN が管理されている場合はアプリ PIN を無効にする</span><span class="sxs-lookup"><span data-stu-id="38275-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="38275-382">はい</span><span class="sxs-lookup"><span data-stu-id="38275-382">Yes</span></span>||
||<span data-ttu-id="38275-383">アクセスのために会社の資格情報を要求する</span><span class="sxs-lookup"><span data-stu-id="38275-383">Require corporate credentials for access</span></span>|<span data-ttu-id="38275-384">いいえ</span><span class="sxs-lookup"><span data-stu-id="38275-384">No</span></span>||
||<span data-ttu-id="38275-385">[(分数) 後に、アクセス要件を再確認する]</span><span class="sxs-lookup"><span data-stu-id="38275-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="38275-386">31</span><span class="sxs-lookup"><span data-stu-id="38275-386">30</span></span>||
||<span data-ttu-id="38275-387">[スクリーン キャプチャと Android Assistant をブロックする]</span><span class="sxs-lookup"><span data-stu-id="38275-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="38275-388">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="38275-388">No</span></span>|<span data-ttu-id="38275-389">iOS では、このオプションは使用できません</span><span class="sxs-lookup"><span data-stu-id="38275-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="38275-390">サインインのセキュリティ要件</span><span class="sxs-lookup"><span data-stu-id="38275-390">Sign-in security requirements</span></span>|<span data-ttu-id="38275-391">PIN の最大試行回数</span><span class="sxs-lookup"><span data-stu-id="38275-391">Max PIN attempts</span></span>|<span data-ttu-id="38275-392">5</span><span class="sxs-lookup"><span data-stu-id="38275-392">5</span></span>|<span data-ttu-id="38275-393">Pin のリセット</span><span class="sxs-lookup"><span data-stu-id="38275-393">Reset Pin</span></span>|
||<span data-ttu-id="38275-394">[オフラインの猶予期間]</span><span class="sxs-lookup"><span data-stu-id="38275-394">Offline grace period</span></span>|<span data-ttu-id="38275-395">720</span><span class="sxs-lookup"><span data-stu-id="38275-395">720</span></span>|<span data-ttu-id="38275-396">アクセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="38275-396">Block access</span></span>|
||<span data-ttu-id="38275-397">アプリのデータがワイプされるまでのオフライン期間 (日数)</span><span class="sxs-lookup"><span data-stu-id="38275-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="38275-398">90</span><span class="sxs-lookup"><span data-stu-id="38275-398">90</span></span>|<span data-ttu-id="38275-399">データのワイプ</span><span class="sxs-lookup"><span data-stu-id="38275-399">Wipe data</span></span>|
||<span data-ttu-id="38275-400">脱獄/ルート化したデバイス</span><span class="sxs-lookup"><span data-stu-id="38275-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="38275-401">データのワイプ</span><span class="sxs-lookup"><span data-stu-id="38275-401">Wipe data</span></span>|

<span data-ttu-id="38275-402">完了したら、必ず [作成] を選択してください。</span><span class="sxs-lookup"><span data-stu-id="38275-402">When complete, remember to select "Create".</span></span> <span data-ttu-id="38275-403">上記の手順を繰り返し、選択したプラットフォーム (ドロップダウン) を iOS に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="38275-403">Repeat the above steps and replace the selected platform (dropdown) with iOS.</span></span> <span data-ttu-id="38275-404">これにより、ポリシーを作成した後にグループをポリシーに割り当てて展開することができるように、2つのアプリポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="38275-404">This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="38275-405">ポリシーを編集して、これらのポリシーをユーザーに割り当てるには、「[アプリ保護ポリシーを作成して割り当てる方法](https://docs.microsoft.com/intune/app-protection-policies)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38275-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="38275-406">承認済みアプリの要求</span><span class="sxs-lookup"><span data-stu-id="38275-406">Require approved apps</span></span>
<span data-ttu-id="38275-407">承認済みアプリを要求するには</span><span class="sxs-lookup"><span data-stu-id="38275-407">To require approved apps:</span></span>

1. <span data-ttu-id="38275-408">[Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="38275-408">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="38275-409">サインインに成功すると、Azure ダッシュボードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38275-409">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="38275-410">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="38275-411">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="38275-412">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="38275-413">ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="38275-414">**[クラウド アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="38275-415">**[アプリの選択**] を選択し、[**クラウドアプリ**] リストから目的のアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-415">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="38275-416">たとえば、[Office 365 Exchange Online] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-416">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="38275-417">**[選択**して**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-417">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="38275-418">[**条件**] を選択し、[**デバイスプラットフォーム**] を選択し、[**構成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-418">Choose **Conditions**, select **Device platforms**, then choose **Configure**</span></span>

9. <span data-ttu-id="38275-419">[**インクルード**] で、[**デバイスプラットフォームの選択**] を選択し、[ **Android**および**iOS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-419">Under **Include**, choose **Select device platforms**, select **Android** and **iOS**.</span></span> <span data-ttu-id="38275-420">[**完了**] をクリックし、もう一度**実行**します。</span><span class="sxs-lookup"><span data-stu-id="38275-420">Click **Done** and **Done** again</span></span>

10. <span data-ttu-id="38275-421">**[アクセス制御]** セクションから **[許可]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-421">Choose **Grant** from the **Access controls** section.</span></span>

11. <span data-ttu-id="38275-422">[**アクセス許可の付与**] を選択し、[**承認済みクライアントアプリの要求**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-422">Choose **Grant access**, select **Require approved client app**.</span></span> <span data-ttu-id="38275-423">複数のコントロールの場合は、[選択した**コントロールを必要とする**] を選択し、[**選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-423">For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

12. <span data-ttu-id="38275-424">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-424">Choose **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="38275-425">デバイスコンプライアンスポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="38275-425">Define device-compliance policies</span></span>

<span data-ttu-id="38275-426">デバイスコンプライアンスポリシーは、準拠としてマークするためにデバイスが従う必要がある要件を定義します。</span><span class="sxs-lookup"><span data-stu-id="38275-426">Device-compliance policies define the requirements that devices must adhere to in order to be marked as compliant.</span></span> <span data-ttu-id="38275-427">Azure ポータル内から Intune デバイスコンプライアンスポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="38275-427">Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="38275-428">プラットフォームごとにポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="38275-428">Create a policy for each platform:</span></span>
- <span data-ttu-id="38275-429">Android</span><span class="sxs-lookup"><span data-stu-id="38275-429">Android</span></span>
- <span data-ttu-id="38275-430">Android enterprise</span><span class="sxs-lookup"><span data-stu-id="38275-430">Android enterprise</span></span>
- <span data-ttu-id="38275-431">iOS</span><span class="sxs-lookup"><span data-stu-id="38275-431">iOS</span></span>
- <span data-ttu-id="38275-432">macOS</span><span class="sxs-lookup"><span data-stu-id="38275-432">macOS</span></span>
- <span data-ttu-id="38275-433">この設定は、次の種類のデバイスで使用できます。</span><span class="sxs-lookup"><span data-stu-id="38275-433">Windows Phone 8.1</span></span>
- <span data-ttu-id="38275-434">Windows 8.1 以降</span><span class="sxs-lookup"><span data-stu-id="38275-434">Windows 8.1 and later</span></span>
- <span data-ttu-id="38275-435">Windows 10 以降</span><span class="sxs-lookup"><span data-stu-id="38275-435">Windows 10 and later</span></span>

<span data-ttu-id="38275-436">デバイスコンプライアンスポリシーを作成するには、管理者の資格情報を使用して Microsoft Azure portal にログインしてから、[ **Intune > デバイスのコンプライアンス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="38275-436">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**.</span></span> <span data-ttu-id="38275-437">[**ポリシーの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-437">Select **Create policy**.</span></span>

<span data-ttu-id="38275-438">Windows 10 では、次の設定をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="38275-438">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="38275-439">**デバイス正常性: Windows Health 構成証明サービスの評価ルール**</span><span class="sxs-lookup"><span data-stu-id="38275-439">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="38275-440">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="38275-440">Properties</span></span>|<span data-ttu-id="38275-441">値</span><span class="sxs-lookup"><span data-stu-id="38275-441">Values</span></span>|<span data-ttu-id="38275-442">注</span><span class="sxs-lookup"><span data-stu-id="38275-442">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="38275-443">BitLocker を必須にする</span><span class="sxs-lookup"><span data-stu-id="38275-443">Require BitLocker</span></span>|<span data-ttu-id="38275-444">必須</span><span class="sxs-lookup"><span data-stu-id="38275-444">Require</span></span>||
|<span data-ttu-id="38275-445">デバイスでセキュアブートが有効になっていることが必要</span><span class="sxs-lookup"><span data-stu-id="38275-445">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="38275-446">必須</span><span class="sxs-lookup"><span data-stu-id="38275-446">Require</span></span>||
|<span data-ttu-id="38275-447">コードの整合性を必須にする</span><span class="sxs-lookup"><span data-stu-id="38275-447">Require code integrity</span></span>|<span data-ttu-id="38275-448">必須</span><span class="sxs-lookup"><span data-stu-id="38275-448">Require</span></span>||


<span data-ttu-id="38275-449">**デバイスのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="38275-449">**Device properties**</span></span>

|<span data-ttu-id="38275-450">型</span><span class="sxs-lookup"><span data-stu-id="38275-450">Type</span></span>|<span data-ttu-id="38275-451">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="38275-451">Properties</span></span>|<span data-ttu-id="38275-452">値</span><span class="sxs-lookup"><span data-stu-id="38275-452">Values</span></span>|<span data-ttu-id="38275-453">注</span><span class="sxs-lookup"><span data-stu-id="38275-453">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="38275-454">オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="38275-454">Operating system version</span></span>|<span data-ttu-id="38275-455">すべて</span><span class="sxs-lookup"><span data-stu-id="38275-455">All</span></span>|<span data-ttu-id="38275-456">未構成</span><span class="sxs-lookup"><span data-stu-id="38275-456">Not configured</span></span>||

<span data-ttu-id="38275-457">上記のすべてのポリシーを展開済みと見なすには、ユーザー グループを対象にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="38275-457">For all the above policies to be considered deployed, they must be targeted at user groups.</span></span> <span data-ttu-id="38275-458">これを行うには、ポリシーを (保存時に) [**ポリシー** ] セクションの [**展開の管理**] ([追加] と同じレベル) を選択して作成します。</span><span class="sxs-lookup"><span data-stu-id="38275-458">You can do this by creating the policy (on Save) or later by selecting **Manage Deployment** in the **Policy** section (same level as Add).</span></span>

<span data-ttu-id="38275-459">**システム セキュリティ**</span><span class="sxs-lookup"><span data-stu-id="38275-459">**System security**</span></span>

|<span data-ttu-id="38275-460">型</span><span class="sxs-lookup"><span data-stu-id="38275-460">Type</span></span>|<span data-ttu-id="38275-461">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="38275-461">Properties</span></span>|<span data-ttu-id="38275-462">値</span><span class="sxs-lookup"><span data-stu-id="38275-462">Values</span></span>|<span data-ttu-id="38275-463">注</span><span class="sxs-lookup"><span data-stu-id="38275-463">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="38275-464">パスワード</span><span class="sxs-lookup"><span data-stu-id="38275-464">Password</span></span>|<span data-ttu-id="38275-465">モバイルデバイスのロックを解除するためのパスワードを要求する</span><span class="sxs-lookup"><span data-stu-id="38275-465">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="38275-466">必須</span><span class="sxs-lookup"><span data-stu-id="38275-466">Require</span></span>||
||<span data-ttu-id="38275-467">単純なパスワード</span><span class="sxs-lookup"><span data-stu-id="38275-467">Simple passwords</span></span>|<span data-ttu-id="38275-468">Block</span><span class="sxs-lookup"><span data-stu-id="38275-468">Block</span></span>||
||<span data-ttu-id="38275-469">パスワードの種類</span><span class="sxs-lookup"><span data-stu-id="38275-469">Password type</span></span>|<span data-ttu-id="38275-470">既定のデバイス</span><span class="sxs-lookup"><span data-stu-id="38275-470">Device default</span></span>||
||<span data-ttu-id="38275-471">パスワードの最小文字数</span><span class="sxs-lookup"><span data-stu-id="38275-471">Minimum password length</span></span>|<span data-ttu-id="38275-472">シックス</span><span class="sxs-lookup"><span data-stu-id="38275-472">6</span></span>||
||<span data-ttu-id="38275-473">パスワードが必要になるまでの最大非アクティブ時間 (分)</span><span class="sxs-lookup"><span data-stu-id="38275-473">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="38275-474">約</span><span class="sxs-lookup"><span data-stu-id="38275-474">15</span></span>|<span data-ttu-id="38275-475">この設定は、Android バージョン4.0 以降、または KNOX 4.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="38275-475">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above.</span></span> <span data-ttu-id="38275-476">IOS デバイスでは、iOS 8.0 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="38275-476">For iOS devices, it’s supported for iOS 8.0 and above</span></span>|
||<span data-ttu-id="38275-477">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="38275-477">Password expiration (days)</span></span>|<span data-ttu-id="38275-478">41</span><span class="sxs-lookup"><span data-stu-id="38275-478">41</span></span>||
||<span data-ttu-id="38275-479">再利用を防止するための以前のパスワードの数</span><span class="sxs-lookup"><span data-stu-id="38275-479">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="38275-480">5</span><span class="sxs-lookup"><span data-stu-id="38275-480">5</span></span>||
||<span data-ttu-id="38275-481">デバイスがアイドル状態から戻るときにパスワードを要求する (Mobile および Holographic)</span><span class="sxs-lookup"><span data-stu-id="38275-481">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="38275-482">必須</span><span class="sxs-lookup"><span data-stu-id="38275-482">Require</span></span>|<span data-ttu-id="38275-483">Windows 10 以降で使用可能</span><span class="sxs-lookup"><span data-stu-id="38275-483">Available for Windows 10 and later</span></span>|
|<span data-ttu-id="38275-484">暗号化</span><span class="sxs-lookup"><span data-stu-id="38275-484">Encryption</span></span>|<span data-ttu-id="38275-485">デバイス上のデータストレージの暗号化</span><span class="sxs-lookup"><span data-stu-id="38275-485">Encryption of data storage on device</span></span>|<span data-ttu-id="38275-486">必須</span><span class="sxs-lookup"><span data-stu-id="38275-486">Require</span></span>||
|<span data-ttu-id="38275-487">デバイスのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="38275-487">Device Security</span></span>|<span data-ttu-id="38275-488">ウォール</span><span class="sxs-lookup"><span data-stu-id="38275-488">Firewall</span></span>|<span data-ttu-id="38275-489">必須</span><span class="sxs-lookup"><span data-stu-id="38275-489">Require</span></span>||
||<span data-ttu-id="38275-490">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="38275-490">Antivirus</span></span>|<span data-ttu-id="38275-491">必須</span><span class="sxs-lookup"><span data-stu-id="38275-491">Require</span></span>||
||<span data-ttu-id="38275-492">ウェア</span><span class="sxs-lookup"><span data-stu-id="38275-492">Antispyware</span></span>|<span data-ttu-id="38275-493">必須</span><span class="sxs-lookup"><span data-stu-id="38275-493">Require</span></span>|<span data-ttu-id="38275-494">この設定には、Windows セキュリティセンターに登録されたスパイウェア対策ソリューションが必要です</span><span class="sxs-lookup"><span data-stu-id="38275-494">This setting requires an Anti-Spyware solution registered with Windows Security Center</span></span>|
|<span data-ttu-id="38275-495">守護</span><span class="sxs-lookup"><span data-stu-id="38275-495">Defender</span></span>|<span data-ttu-id="38275-496">Windows Defender マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="38275-496">Windows Defender Antimalware</span></span>|<span data-ttu-id="38275-497">必須</span><span class="sxs-lookup"><span data-stu-id="38275-497">Require</span></span>||
||<span data-ttu-id="38275-498">Windows Defender マルウェア対策の最小バージョン</span><span class="sxs-lookup"><span data-stu-id="38275-498">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="38275-499">Windows 10 デスクトップでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="38275-499">Only supported for Windows 10 desktop.</span></span> <span data-ttu-id="38275-500">Microsoft では、最新バージョン以降のバージョンを5つ以下にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="38275-500">Microsoft recommends versions no more than five behind from the most recent version</span></span>|
||<span data-ttu-id="38275-501">Windows Defender マルウェア対策の署名が最新の状態になっています</span><span class="sxs-lookup"><span data-stu-id="38275-501">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="38275-502">必須</span><span class="sxs-lookup"><span data-stu-id="38275-502">Require</span></span>||
||<span data-ttu-id="38275-503">リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="38275-503">Real-time protection</span></span>|<span data-ttu-id="38275-504">必須</span><span class="sxs-lookup"><span data-stu-id="38275-504">Require</span></span>|<span data-ttu-id="38275-505">Windows 10 デスクトップでのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="38275-505">Only supported for Windows 10 desktop</span></span>|

<span data-ttu-id="38275-506">**Windows Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="38275-506">**Windows Defender ATP**</span></span>

|<span data-ttu-id="38275-507">型</span><span class="sxs-lookup"><span data-stu-id="38275-507">Type</span></span>|<span data-ttu-id="38275-508">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="38275-508">Properties</span></span>|<span data-ttu-id="38275-509">値</span><span class="sxs-lookup"><span data-stu-id="38275-509">Values</span></span>|<span data-ttu-id="38275-510">注</span><span class="sxs-lookup"><span data-stu-id="38275-510">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="38275-511">Windows Defender Advanced Threat Protection ルール</span><span class="sxs-lookup"><span data-stu-id="38275-511">Windows Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="38275-512">デバイスがコンピューターのリスクスコアの下または下にある必要があります。</span><span class="sxs-lookup"><span data-stu-id="38275-512">Require the device to be at or under the machine-risk score</span></span>|<span data-ttu-id="38275-513">中</span><span class="sxs-lookup"><span data-stu-id="38275-513">Medium</span></span>||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="38275-514">準拠 Pc を必要とする (ただし、準拠する電話やタブレットではない)</span><span class="sxs-lookup"><span data-stu-id="38275-514">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="38275-515">準拠している Pc を必要とするポリシーを追加する前に、管理するデバイスを Intune に登録してください。</span><span class="sxs-lookup"><span data-stu-id="38275-515">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune.</span></span> <span data-ttu-id="38275-516">デバイスが目的のユーザーを所有していることを保証するために、デバイスを Intune に登録する前に、多要素認証を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="38275-516">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="38275-517">準拠している Pc を要求するには:</span><span class="sxs-lookup"><span data-stu-id="38275-517">To require compliant PCs:</span></span>

1. <span data-ttu-id="38275-518">[Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="38275-518">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="38275-519">サインインに成功すると、Azure ダッシュボードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38275-519">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="38275-520">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-520">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="38275-521">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-521">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="38275-522">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-522">Choose **New policy**.</span></span>

5. <span data-ttu-id="38275-523">ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-523">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="38275-524">**[クラウド アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-524">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="38275-525">**[アプリの選択**] を選択し、[**クラウドアプリ**] リストから目的のアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-525">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="38275-526">たとえば、[Office 365 Exchange Online] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-526">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="38275-527">**[選択**して**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-527">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="38275-528">準拠している Pc を必要とするが、準拠している電話やタブレットではないものを要求するには、**条件**と**デバイスプラットフォーム**を選択します</span><span class="sxs-lookup"><span data-stu-id="38275-528">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**.</span></span> <span data-ttu-id="38275-529">**[Select device プラットフォーム]** を選択して、[ **Windows**と**macOS**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-529">Choose **Select device platforms** and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="38275-530">**[アクセス制御]** セクションから **[許可]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-530">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="38275-531">[**アクセス許可**] を選択し、[**デバイスが準拠していることをマークする必要がある**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-531">Choose **Grant access**, select **Require device to be marked as compliant**.</span></span> <span data-ttu-id="38275-532">複数のコントロールの場合は、[選択し**たすべてのコントロールを必要とする**] を選択し、[**選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-532">For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="38275-533">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-533">Choose **Create**.</span></span>

<span data-ttu-id="38275-534">準拠している Pc*と*モバイルデバイスを必要とする目的では、プラットフォームを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="38275-534">If your objective is to require compliant PCs *and* mobile devices, do not select platforms.</span></span> <span data-ttu-id="38275-535">これにより、すべてのデバイスのコンプライアンスを強制します。</span><span class="sxs-lookup"><span data-stu-id="38275-535">This enforces compliance for all devices.</span></span> 

## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="38275-536">準拠*して*いる pc とモバイルデバイスが必要</span><span class="sxs-lookup"><span data-stu-id="38275-536">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="38275-537">すべてのデバイスのコンプライアンスを要求するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="38275-537">To require compliance for all devices:</span></span>

1. <span data-ttu-id="38275-538">[Azure Portal](https://portal.azure.com) に移動し、資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="38275-538">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials.</span></span> <span data-ttu-id="38275-539">サインインに成功すると、Azure ダッシュボードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="38275-539">After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="38275-540">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-540">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="38275-541">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-541">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="38275-542">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-542">Choose **New policy**.</span></span>

5. <span data-ttu-id="38275-543">ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-543">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="38275-544">**[クラウド アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-544">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="38275-545">**[アプリの選択**] を選択し、[**クラウドアプリ**] リストから目的のアプリを選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-545">Choose **Select apps**, select the desired apps from the **Cloud apps** list.</span></span> <span data-ttu-id="38275-546">たとえば、[Office 365 Exchange Online] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-546">For example, select Office 365 Exchange Online.</span></span> <span data-ttu-id="38275-547">**[選択**して**完了**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-547">Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="38275-548">**[アクセス制御]** セクションから **[許可]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="38275-548">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="38275-549">[**アクセス許可**] を選択し、[**デバイスが準拠していることをマークする必要がある**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-549">Choose **Grant access**, select **Require device to be marked as compliant**.</span></span> <span data-ttu-id="38275-550">複数のコントロールの場合は、[選択し**たすべてのコントロールを必要とする**] を選択し、[**選択**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-550">For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="38275-551">**[作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="38275-551">Choose **Create**.</span></span>

<span data-ttu-id="38275-552">このポリシーを作成するときは、プラットフォームを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="38275-552">When creating this policy, do not select platforms.</span></span> <span data-ttu-id="38275-553">これにより、準拠しているデバイスが強制できます。</span><span class="sxs-lookup"><span data-stu-id="38275-553">This enforces compliant devices.</span></span>


## <a name="next-steps"></a><span data-ttu-id="38275-554">次のステップ</span><span class="sxs-lookup"><span data-stu-id="38275-554">Next steps</span></span>

[<span data-ttu-id="38275-555">電子メールをセキュリティで保護するためのポリシーの推奨事項について学びます</span><span class="sxs-lookup"><span data-stu-id="38275-555">Learn about policy recommendations for securing email</span></span>](secure-email-recommended-policies.md)
