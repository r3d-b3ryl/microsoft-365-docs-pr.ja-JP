---
title: 共通の id とデバイスのアクセス ポリシーの Microsoft 365 エンタープライズ |マイクロソフトのドキュメント
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
ms.openlocfilehash: ab8454c27cd57b6bd5cc8df6e1526ee2950ac998
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869634"
---
# <a name="common-identity-and-device-access-policies"></a><span data-ttu-id="cd5d3-103">共通 ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="cd5d3-103">Common identity and device access policies</span></span>
<span data-ttu-id="cd5d3-104">この資料では、Azure AD アプリケーション プロキシを使用してなどの設置型のアプリケーションが公開されたクラウド サービスへのアクセスをセキュリティで保護するためのポリシーをお勧めする一般的なを説明します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-104">This article describes the common recommended policies for securing access to cloud services, including on-premises applications published with Azure AD Application Proxy.</span></span> 

<span data-ttu-id="cd5d3-p101">このガイドでは、新たにプロビジョニングされた環境で推奨されるポリシーを展開する方法について説明します。独立したラボ環境でこれらのポリシーの設定を使用すると、理解し、運用環境と本番環境への展開をステージングする前に推奨されるポリシーを評価します。クラウドのみを新しくプロビジョニングされた環境として使用することがありますまたはハイブリッド。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p101">This guidance discusses how to deploy the recommended policies in a newly-provisioned environment. Setting up these policies in a separate lab environment allows you to understand and evaluate the recommended policies before staging the rollout to your preproduction and production environments. Your newly provisioned environment may be cloud-only or hybrid.</span></span>  

## <a name="policy-set"></a><span data-ttu-id="cd5d3-108">ポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="cd5d3-108">Policy set</span></span> 

<span data-ttu-id="cd5d3-p102">次の図は、推奨される一連のポリシーを示しています。保護のためのどの層は、各ポリシーが適用され、Pc や電話、タブレット、またはデバイスの両方のカテゴリに、ポリシーを適用するかどうかを示しています。これらのポリシーが構成されていることも示しています。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p102">The following diagram illustrates the recommended set of policies. It shows which tier of protections each policy applies to and whether the policies apply to PCs or phones and tablets, or both categories of devices. It also indicates where these policies are configured.</span></span>

![Id とデバイスのアクセスを構成するための共通のポリシー](../images/Identity_device_access_policies_byplan.png)


<span data-ttu-id="cd5d3-113">この資料の残りの部分では、これらのポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-113">The rest of this article describes how to configure these policies.</span></span> 

<span data-ttu-id="cd5d3-p103">Intune に確実に目的のユーザーの所有していることには、デバイスのデバイスを登録する前に、多要素認証を使用することをお勧めします。Intune にデバイスのコンプライアンス ・ ポリシーを適用する前にデバイスを登録する必要がありますもします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p103">Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user. You must also enroll devices into Intune before enforcing device compliance policies.</span></span>

<span data-ttu-id="cd5d3-p104">提供するこれらのタスクを実行する時間を次の表に記載されている順序で、ベースライン ポリシーを実装することをお勧めします。ただし、規制の厳しい機密保護の MFA のポリシーは、いつでも実装できます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p104">To give you time to accomplish these tasks, we recommend implementing the baseline policies in the order listed in this table. However, the MFA policies for sensitive and highly regulated protection can be implemented at any time.</span></span>


|<span data-ttu-id="cd5d3-118">保護レベル</span><span class="sxs-lookup"><span data-stu-id="cd5d3-118">Protection level</span></span>|<span data-ttu-id="cd5d3-119">[Policies]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-119">Policies</span></span>|<span data-ttu-id="cd5d3-120">詳細情報</span><span class="sxs-lookup"><span data-stu-id="cd5d3-120">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="cd5d3-121">**基準**</span><span class="sxs-lookup"><span data-stu-id="cd5d3-121">**Baseline**</span></span>|[<span data-ttu-id="cd5d3-122">サインインのリスクが*中*または*高*の場合は、MFA を必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|        |[<span data-ttu-id="cd5d3-123">現代の認証をサポートしていないクライアントをブロック</span><span class="sxs-lookup"><span data-stu-id="cd5d3-123">Block clients that don't support modern authentication</span></span>](#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="cd5d3-124">現代の認証を使用しないクライアントは条件付きのアクセス規則をバイパスできますので、これらをブロックすることが重要</span><span class="sxs-lookup"><span data-stu-id="cd5d3-124">Clients that do not use modern authentication can bypass conditional access rules, so it's important to block these</span></span>|
|        |[<span data-ttu-id="cd5d3-125">危険度の高いユーザーがパスワードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-125">High risk users must change password</span></span>](#high-risk-users-must-change-password)|<span data-ttu-id="cd5d3-126">自分のアカウントにリスクの高いアクティビティが検出された場合は、サインイン時にパスワードの変更をユーザーに強制</span><span class="sxs-lookup"><span data-stu-id="cd5d3-126">Forces users to change their password when signing in if high-risk activity is detected for their account</span></span>|
|        |[<span data-ttu-id="cd5d3-127">アプリケーション保護のポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-127">Define app protection policies</span></span>](#define-app-protection-policies)|<span data-ttu-id="cd5d3-128">プラットフォーム (iOS、Android、Windows) あたり 1 つのポリシーです。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-128">One policy per platform (iOS, Android, Windows).</span></span>|
|        |[<span data-ttu-id="cd5d3-129">承認済みのアプリケーションを必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-129">Require approved apps</span></span>](#require-approved-apps)|<span data-ttu-id="cd5d3-130">フォンやタブレットのモバイル アプリケーションの保護を適用します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-130">Enforces mobile app protection for phones and tablets</span></span>|
|        |[<span data-ttu-id="cd5d3-131">デバイスのコンプライアンス ・ ポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-131">Define device compliance policies</span></span>](#define-device-compliance-policies)|<span data-ttu-id="cd5d3-132">プラットフォームごとに 1 つのポリシー</span><span class="sxs-lookup"><span data-stu-id="cd5d3-132">One policy for each platform</span></span>|
|        |[<span data-ttu-id="cd5d3-133">準拠の Pc を必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-133">Require compliant PCs</span></span>](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="cd5d3-134">Pc の Intune 管理を実施します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-134">Enforces Intune management of PCs</span></span>|
|<span data-ttu-id="cd5d3-135">**機密**</span><span class="sxs-lookup"><span data-stu-id="cd5d3-135">**Sensitive**</span></span>|[<span data-ttu-id="cd5d3-136">サインインのリスクとは、*低*、*中*または*高*の場合は、MFA を必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-136">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](#require-mfa-based-on-sign-in-risk)| |
|         |[<span data-ttu-id="cd5d3-137">準拠の Pc*と*モバイル デバイスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-137">Require compliant PCs *and* mobile devices</span></span>](#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="cd5d3-138">Pc と電話とタブレットの Intune 管理を実施します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-138">Enforces Intune management for PCs and phone/tablets</span></span>|
|<span data-ttu-id="cd5d3-139">**高度な規制**</span><span class="sxs-lookup"><span data-stu-id="cd5d3-139">**Highly regulated**</span></span>|[<span data-ttu-id="cd5d3-140">*常に*MFA を必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-140">*Always* require MFA</span></span>](#require-mfa-based-on-sign-in-risk)|
| | |

## <a name="assigning-policies-to-users"></a><span data-ttu-id="cd5d3-141">ユーザーにポリシーを割り当てる</span><span class="sxs-lookup"><span data-stu-id="cd5d3-141">Assigning policies to users</span></span>
<span data-ttu-id="cd5d3-p105">ポリシーを構成する前に、保護の各階層を使用している Azure AD グループを識別します。通常、基準計画の保護は、組織の全員に適用されます。ベースラインと機密保護の両方に含まれているユーザーには、適用されるすべてのベースライン ポリシーと機密性の高いポリシーがあります。保護は累積的で、最も制限の厳しいポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p105">Before configuring policies, identify the Azure AD groups you are using for each tier of protection. Typically, baseline protection applies to everybody in the organization. A user who is included for both baseline and sensitive protection will have all the baseline policies applied plus the sensitive policies. Protection is cumulative and the most restrictive policy is enforced.</span></span> 

<span data-ttu-id="cd5d3-p106">Azure AD グループの条件付きアクセスの除外を作成することをお勧めします。「除外」の下の条件付きのアクセス規則のすべてにこのグループを追加します。これは、アクセスに関する問題のトラブルシューティングを行う間、ユーザーにアクセスを提供する方法を示します。一時的なソリューションとしてのみお勧めします。変更するには、このグループを監視し、除外グループが意図したとおりにのみ使用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p106">A recommended practice is to create an Azure AD group for conditional access exclusion. Add this group to all of your conditional access rules under "Exclude". This gives you a method to provide access to a user while you troubleshoot access issues. This is recommended as a temporary solution only. Monitor this group for changes and be sure the exclusion group is being used only as intended.</span></span> 

<span data-ttu-id="cd5d3-151">ユーザーの割り当て] および [除外リストの例を次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-151">The following diagram provides an example of user assignment and exclusions.</span></span>

![例ユーザーの割り当てと MFA のルールの除外](../images/identity-access-policies-assignment.png)

<span data-ttu-id="cd5d3-p107">図は、「トップ シークレット プロジェクト X チーム」には MFA*常に*必要な条件付きのアクセス ポリシーが割り当てられます。ユーザーに高いレベルの保護を適用するときに多用します。このプロジェクト チームのメンバーは、規制の多いコンテンツを表示していない場合でも、ログオンするたびに 2 つの形式の認証を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p107">In the illustration the "Top secret project X team" is assigned a conditional access policy that requires MFA *always*. Be judicious when applying higher levels of protection to users. Members of this project team will be required to provide two forms of authentication every time they log on, even if they are not viewing highly-regulated content.</span></span>  

<span data-ttu-id="cd5d3-p108">これらの推奨事項の一部として作成されたすべての Azure AD グループは、Office 365 のグループとして作成する必要があります。これは、SharePoint Online のドキュメントをセキュリティで保護すると、Azure 情報保護 (AIP) の展開で特に重要です。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p108">All Azure AD groups created as part of these recommendations must be created as Office 365 groups. This is specifically important for the deployment of Azure Information Protection (AIP) when securing documents in SharePoint Online.</span></span>

![Office 365 のグループを作成するための画面キャプチャ](../images/identity-device-AAD-groups.png)


## <a name="require-mfa-based-on-sign-in-risk"></a><span data-ttu-id="cd5d3-159">サインインのリスクに基づく MFA を必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-159">Require MFA based on sign-in risk</span></span>
<span data-ttu-id="cd5d3-p109">MFA を必要とする前に MFA のユーザーを登録するのには、識別情報の保護の MFA の登録ポリシーを使用します。ユーザーが登録された後は、サインインの MFA を適用できます。MFA を持つすべてのユーザーを登録する[作業の前提条件](identity-access-prerequisites.md)が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p109">Before requiring MFA, first use an Identity Protection MFA registration policy to register users for MFA. After users are registered you can enforce MFA for sign-in. The [prerequisite work](identity-access-prerequisites.md) includes registering all users with MFA.</span></span>

<span data-ttu-id="cd5d3-163">条件付きアクセス ポリシーを作成するには:</span><span class="sxs-lookup"><span data-stu-id="cd5d3-163">To create a new conditional access policy:</span></span> 

1. <span data-ttu-id="cd5d3-p110">[Azure ポータル](https://portal.azure.com)に移動し、ユーザーの資格情報を使用してサインインします。正常にサインインして後、は、Azure のダッシュ ボードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p110">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="cd5d3-166">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-166">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="cd5d3-167">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-167">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="cd5d3-168">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-168">Choose **New policy**.</span></span>

![ベースラインとなる CA ポリシー](./media/secure-email/CA-EXO-policy-1.png)

 <span data-ttu-id="cd5d3-170">次の表では、このポリシーを実装するために条件付きのアクセス ポリシーの設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-170">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="cd5d3-171">**割り当て**</span><span class="sxs-lookup"><span data-stu-id="cd5d3-171">**Assignments**</span></span>

|<span data-ttu-id="cd5d3-172">型</span><span class="sxs-lookup"><span data-stu-id="cd5d3-172">Type</span></span>|<span data-ttu-id="cd5d3-173">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-173">Properties</span></span>|<span data-ttu-id="cd5d3-174">値</span><span class="sxs-lookup"><span data-stu-id="cd5d3-174">Values</span></span>|<span data-ttu-id="cd5d3-175">メモ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-175">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="cd5d3-176">ユーザーとグループ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-176">Users and groups</span></span>|<span data-ttu-id="cd5d3-177">含める</span><span class="sxs-lookup"><span data-stu-id="cd5d3-177">Include</span></span>|<span data-ttu-id="cd5d3-178">ユーザーとグループの選択 – 対象ユーザーを含む特定のセキュリティ グループを選択します</span><span class="sxs-lookup"><span data-stu-id="cd5d3-178">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="cd5d3-179">パイロット ユーザーを含むセキュリティ グループから開始します</span><span class="sxs-lookup"><span data-stu-id="cd5d3-179">Start with security group including pilot users</span></span>|
||<span data-ttu-id="cd5d3-180">除外</span><span class="sxs-lookup"><span data-stu-id="cd5d3-180">Exclude</span></span>|<span data-ttu-id="cd5d3-181">例外セキュリティ グループ、サービス アカウント (アプリ ID)</span><span class="sxs-lookup"><span data-stu-id="cd5d3-181">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="cd5d3-182">メンバーシップは、必要に応じて一時的に変更</span><span class="sxs-lookup"><span data-stu-id="cd5d3-182">Membership modified on an as-needed temporary basis</span></span>|
|<span data-ttu-id="cd5d3-183">クラウド アプリ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-183">Cloud apps</span></span>|<span data-ttu-id="cd5d3-184">含める</span><span class="sxs-lookup"><span data-stu-id="cd5d3-184">Include</span></span>|<span data-ttu-id="cd5d3-p111">この規則を適用しアプリケーションを選択します。たとえば、Office 365 Exchange Online を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p111">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="cd5d3-187">条件</span><span class="sxs-lookup"><span data-stu-id="cd5d3-187">Conditions</span></span>|<span data-ttu-id="cd5d3-188">構成済み</span><span class="sxs-lookup"><span data-stu-id="cd5d3-188">Configured</span></span>|<span data-ttu-id="cd5d3-189">はい</span><span class="sxs-lookup"><span data-stu-id="cd5d3-189">Yes</span></span>|<span data-ttu-id="cd5d3-190">使用環境およびニーズに合わせて構成します</span><span class="sxs-lookup"><span data-stu-id="cd5d3-190">Configure specific to your environment and needs</span></span>|
|<span data-ttu-id="cd5d3-191">サインイン リスク</span><span class="sxs-lookup"><span data-stu-id="cd5d3-191">Sign-in risk</span></span>|<span data-ttu-id="cd5d3-192">リスク レベル</span><span class="sxs-lookup"><span data-stu-id="cd5d3-192">Risk level</span></span>||<span data-ttu-id="cd5d3-193">次の表のガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-193">See the guidance in the following table</span></span>|

<span data-ttu-id="cd5d3-194">**サインイン リスク**</span><span class="sxs-lookup"><span data-stu-id="cd5d3-194">**Sign-in risk**</span></span>

<span data-ttu-id="cd5d3-195">対象とする保護レベルの設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-195">Apply the settings based on the protection level you are targeting.</span></span>

|<span data-ttu-id="cd5d3-196">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-196">Property</span></span>|<span data-ttu-id="cd5d3-197">レベルの保護</span><span class="sxs-lookup"><span data-stu-id="cd5d3-197">Level of protection</span></span>|<span data-ttu-id="cd5d3-198">値</span><span class="sxs-lookup"><span data-stu-id="cd5d3-198">Values</span></span>|<span data-ttu-id="cd5d3-199">メモ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-199">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="cd5d3-200">リスク レベル</span><span class="sxs-lookup"><span data-stu-id="cd5d3-200">Risk level</span></span>|<span data-ttu-id="cd5d3-201">基準</span><span class="sxs-lookup"><span data-stu-id="cd5d3-201">Baseline</span></span>|<span data-ttu-id="cd5d3-202">高、中</span><span class="sxs-lookup"><span data-stu-id="cd5d3-202">High, medium</span></span>|<span data-ttu-id="cd5d3-203">両方をチェック</span><span class="sxs-lookup"><span data-stu-id="cd5d3-203">Check both</span></span>|
| |<span data-ttu-id="cd5d3-204">機密</span><span class="sxs-lookup"><span data-stu-id="cd5d3-204">Sensitive</span></span>|<span data-ttu-id="cd5d3-205">高、中、低</span><span class="sxs-lookup"><span data-stu-id="cd5d3-205">High, medium, low</span></span>|<span data-ttu-id="cd5d3-206">3 つすべてチェック</span><span class="sxs-lookup"><span data-stu-id="cd5d3-206">Check all three</span></span>|
| |<span data-ttu-id="cd5d3-207">高度な規制</span><span class="sxs-lookup"><span data-stu-id="cd5d3-207">Highly regulated</span></span>| |<span data-ttu-id="cd5d3-208">MFA を常に適用するすべてのオプションをオフします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-208">Leave all options unchecked to always enforce MFA</span></span>|

<span data-ttu-id="cd5d3-209">**アクセス制御**</span><span class="sxs-lookup"><span data-stu-id="cd5d3-209">**Access controls**</span></span>

|<span data-ttu-id="cd5d3-210">型</span><span class="sxs-lookup"><span data-stu-id="cd5d3-210">Type</span></span>|<span data-ttu-id="cd5d3-211">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-211">Properties</span></span>|<span data-ttu-id="cd5d3-212">値</span><span class="sxs-lookup"><span data-stu-id="cd5d3-212">Values</span></span>|<span data-ttu-id="cd5d3-213">メモ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-213">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="cd5d3-214">許可</span><span class="sxs-lookup"><span data-stu-id="cd5d3-214">Grant</span></span>|<span data-ttu-id="cd5d3-215">アクセスの許可</span><span class="sxs-lookup"><span data-stu-id="cd5d3-215">Grant access</span></span>|<span data-ttu-id="cd5d3-216">True</span><span class="sxs-lookup"><span data-stu-id="cd5d3-216">True</span></span>|<span data-ttu-id="cd5d3-217">オン</span><span class="sxs-lookup"><span data-stu-id="cd5d3-217">Selected</span></span>|
||<span data-ttu-id="cd5d3-218">MFA を要求</span><span class="sxs-lookup"><span data-stu-id="cd5d3-218">Require MFA</span></span>|<span data-ttu-id="cd5d3-219">True</span><span class="sxs-lookup"><span data-stu-id="cd5d3-219">True</span></span>|<span data-ttu-id="cd5d3-220">Check</span><span class="sxs-lookup"><span data-stu-id="cd5d3-220">Check</span></span>|
||<span data-ttu-id="cd5d3-221">準拠としてマークするデバイスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-221">Require device to be marked as compliant</span></span>|<span data-ttu-id="cd5d3-222">False</span><span class="sxs-lookup"><span data-stu-id="cd5d3-222">False</span></span>||
||<span data-ttu-id="cd5d3-223">ハイブリッド Azure AD に参加しているデバイスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-223">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="cd5d3-224">False</span><span class="sxs-lookup"><span data-stu-id="cd5d3-224">False</span></span>||
||<span data-ttu-id="cd5d3-225">承認されたクライアント アプリケーションを必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-225">Require approved client app</span></span>|<span data-ttu-id="cd5d3-226">False</span><span class="sxs-lookup"><span data-stu-id="cd5d3-226">False</span></span>||
||<span data-ttu-id="cd5d3-227">選択したコントロールすべてが必要</span><span class="sxs-lookup"><span data-stu-id="cd5d3-227">Require all the selected controls</span></span>|<span data-ttu-id="cd5d3-228">True</span><span class="sxs-lookup"><span data-stu-id="cd5d3-228">True</span></span>|<span data-ttu-id="cd5d3-229">オン</span><span class="sxs-lookup"><span data-stu-id="cd5d3-229">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="cd5d3-p112">\*\*\*\* 選択することで、このポリシーを有効にすることを確認します。また、ポリシーをテストする[場合](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)ツールを使用してを検討します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p112">Be sure to enable this policy, by choosing **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="block-clients-that-dont-support-modern-authentication"></a><span data-ttu-id="cd5d3-232">現代の認証をサポートしていないクライアントをブロック</span><span class="sxs-lookup"><span data-stu-id="cd5d3-232">Block clients that don't support modern authentication</span></span>
1. <span data-ttu-id="cd5d3-p113">[Azure ポータル](https://portal.azure.com)に移動し、ユーザーの資格情報を使用してサインインします。正常にサインインして後、は、Azure のダッシュ ボードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p113">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="cd5d3-235">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-235">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="cd5d3-236">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-236">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="cd5d3-237">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-237">Choose **New policy**.</span></span>

<span data-ttu-id="cd5d3-238">次の表では、このポリシーを実装するために条件付きのアクセス ポリシーの設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-238">The following tables describes the conditional access policy settings to implement for this policy.</span></span>

<span data-ttu-id="cd5d3-239">**割り当て**</span><span class="sxs-lookup"><span data-stu-id="cd5d3-239">**Assignments**</span></span>

|<span data-ttu-id="cd5d3-240">型</span><span class="sxs-lookup"><span data-stu-id="cd5d3-240">Type</span></span>|<span data-ttu-id="cd5d3-241">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-241">Properties</span></span>|<span data-ttu-id="cd5d3-242">値</span><span class="sxs-lookup"><span data-stu-id="cd5d3-242">Values</span></span>|<span data-ttu-id="cd5d3-243">メモ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-243">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="cd5d3-244">ユーザーとグループ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-244">Users and groups</span></span>|<span data-ttu-id="cd5d3-245">含める</span><span class="sxs-lookup"><span data-stu-id="cd5d3-245">Include</span></span>|<span data-ttu-id="cd5d3-246">ユーザーとグループの選択 – 対象ユーザーを含む特定のセキュリティ グループを選択します</span><span class="sxs-lookup"><span data-stu-id="cd5d3-246">Select users and groups – Select specific security group containing targeted users</span></span>|<span data-ttu-id="cd5d3-247">パイロット ユーザーを含むセキュリティ グループから開始します</span><span class="sxs-lookup"><span data-stu-id="cd5d3-247">Start with security group including pilot users</span></span>|
||<span data-ttu-id="cd5d3-248">除外</span><span class="sxs-lookup"><span data-stu-id="cd5d3-248">Exclude</span></span>|<span data-ttu-id="cd5d3-249">例外セキュリティ グループ、サービス アカウント (アプリ ID)</span><span class="sxs-lookup"><span data-stu-id="cd5d3-249">Exception security group; service accounts (app identities)</span></span>|<span data-ttu-id="cd5d3-250">必要に応じて一時的にメンバーシップを変更します</span><span class="sxs-lookup"><span data-stu-id="cd5d3-250">Membership modified on an as needed temporary basis</span></span>|
|<span data-ttu-id="cd5d3-251">クラウド アプリ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-251">Cloud apps</span></span>|<span data-ttu-id="cd5d3-252">含める</span><span class="sxs-lookup"><span data-stu-id="cd5d3-252">Include</span></span>|<span data-ttu-id="cd5d3-p114">この規則を適用しアプリケーションを選択します。たとえば、Office 365 Exchange Online を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p114">Select the apps you want this rule to apply to. For example, select Office 365 Exchange Online</span></span>||
|<span data-ttu-id="cd5d3-255">条件</span><span class="sxs-lookup"><span data-stu-id="cd5d3-255">Conditions</span></span>|<span data-ttu-id="cd5d3-256">構成済み</span><span class="sxs-lookup"><span data-stu-id="cd5d3-256">Configured</span></span>|<span data-ttu-id="cd5d3-257">はい</span><span class="sxs-lookup"><span data-stu-id="cd5d3-257">Yes</span></span>|<span data-ttu-id="cd5d3-258">クライアント アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-258">Configure Client apps</span></span>|
|<span data-ttu-id="cd5d3-259">クライアント アプリケーション</span><span class="sxs-lookup"><span data-stu-id="cd5d3-259">Client apps</span></span>|<span data-ttu-id="cd5d3-260">構成済み</span><span class="sxs-lookup"><span data-stu-id="cd5d3-260">Configured</span></span>|<span data-ttu-id="cd5d3-261">はい</span><span class="sxs-lookup"><span data-stu-id="cd5d3-261">Yes</span></span>|<span data-ttu-id="cd5d3-262">モバイル アプリケーションとデスクトップ クライアント、その他の (両方を選択)</span><span class="sxs-lookup"><span data-stu-id="cd5d3-262">Mobile apps and desktop clients, Other clients (select both)</span></span>|

<span data-ttu-id="cd5d3-263">**アクセス制御**</span><span class="sxs-lookup"><span data-stu-id="cd5d3-263">**Access controls**</span></span>

|<span data-ttu-id="cd5d3-264">型</span><span class="sxs-lookup"><span data-stu-id="cd5d3-264">Type</span></span>|<span data-ttu-id="cd5d3-265">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-265">Properties</span></span>|<span data-ttu-id="cd5d3-266">値</span><span class="sxs-lookup"><span data-stu-id="cd5d3-266">Values</span></span>|<span data-ttu-id="cd5d3-267">メモ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-267">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="cd5d3-268">許可</span><span class="sxs-lookup"><span data-stu-id="cd5d3-268">Grant</span></span>|<span data-ttu-id="cd5d3-269">アクセスの禁止</span><span class="sxs-lookup"><span data-stu-id="cd5d3-269">Block access</span></span>|<span data-ttu-id="cd5d3-270">True</span><span class="sxs-lookup"><span data-stu-id="cd5d3-270">True</span></span>|<span data-ttu-id="cd5d3-271">オン</span><span class="sxs-lookup"><span data-stu-id="cd5d3-271">Selected</span></span>|
||<span data-ttu-id="cd5d3-272">MFA を要求</span><span class="sxs-lookup"><span data-stu-id="cd5d3-272">Require MFA</span></span>|<span data-ttu-id="cd5d3-273">False</span><span class="sxs-lookup"><span data-stu-id="cd5d3-273">False</span></span>||
||<span data-ttu-id="cd5d3-274">準拠としてマークするデバイスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-274">Require device to be marked as compliant</span></span>|<span data-ttu-id="cd5d3-275">False</span><span class="sxs-lookup"><span data-stu-id="cd5d3-275">False</span></span>||
||<span data-ttu-id="cd5d3-276">ハイブリッド Azure AD に参加しているデバイスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-276">Require hybrid Azure AD-joined device</span></span>|<span data-ttu-id="cd5d3-277">False</span><span class="sxs-lookup"><span data-stu-id="cd5d3-277">False</span></span>||
||<span data-ttu-id="cd5d3-278">承認されたクライアント アプリケーションを必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-278">Require approved client app</span></span>|<span data-ttu-id="cd5d3-279">False</span><span class="sxs-lookup"><span data-stu-id="cd5d3-279">False</span></span>||
||<span data-ttu-id="cd5d3-280">選択したコントロールすべてが必要</span><span class="sxs-lookup"><span data-stu-id="cd5d3-280">Require all the selected controls</span></span>|<span data-ttu-id="cd5d3-281">True</span><span class="sxs-lookup"><span data-stu-id="cd5d3-281">True</span></span>|<span data-ttu-id="cd5d3-282">オン</span><span class="sxs-lookup"><span data-stu-id="cd5d3-282">Selected</span></span>|

> [!NOTE]
> <span data-ttu-id="cd5d3-p115">\*\*\*\* 選択することで、このポリシーを有効にすることを確認します。また、ポリシーをテストする[場合](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)ツールを使用してを検討します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p115">Be sure to enable this policy, by choosing **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy.</span></span>



## <a name="high-risk-users-must-change-password"></a><span data-ttu-id="cd5d3-285">危険度の高いユーザーがパスワードを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-285">High risk users must change password</span></span>
<span data-ttu-id="cd5d3-286">署名のときにパスワードの変更を実行するのには強制的にすべての危険度の高いユーザーのセキュリティを侵害されたアカウントがあることを確認、次のポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-286">To ensure that all high-risk users' compromised accounts are forced to perform a password change when signing-in, you must apply the following policy.</span></span>

<span data-ttu-id="cd5d3-287">ログイン、 [Microsoft Azure ポータル (http://portal.azure.com) ](http://portal.azure.com/) 、管理者の資格情報に移動**Azure AD Id 保護 > リスクのポリシーをユーザー**。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-287">Log in to the [Microsoft Azure portal (http://portal.azure.com)](http://portal.azure.com/) with your administrator credentials, and then navigate to **Azure AD Identity Protection > User Risk Policy**.</span></span>

<span data-ttu-id="cd5d3-288">**割り当て**</span><span class="sxs-lookup"><span data-stu-id="cd5d3-288">**Assignments**</span></span>

|<span data-ttu-id="cd5d3-289">型</span><span class="sxs-lookup"><span data-stu-id="cd5d3-289">Type</span></span>|<span data-ttu-id="cd5d3-290">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-290">Properties</span></span>|<span data-ttu-id="cd5d3-291">値</span><span class="sxs-lookup"><span data-stu-id="cd5d3-291">Values</span></span>|<span data-ttu-id="cd5d3-292">メモ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-292">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="cd5d3-293">Users</span><span class="sxs-lookup"><span data-stu-id="cd5d3-293">Users</span></span>|<span data-ttu-id="cd5d3-294">含める</span><span class="sxs-lookup"><span data-stu-id="cd5d3-294">Include</span></span>|<span data-ttu-id="cd5d3-295">[すべてのユーザー]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-295">All users</span></span>|<span data-ttu-id="cd5d3-296">オン</span><span class="sxs-lookup"><span data-stu-id="cd5d3-296">Selected</span></span>|
||<span data-ttu-id="cd5d3-297">除外</span><span class="sxs-lookup"><span data-stu-id="cd5d3-297">Exclude</span></span>|<span data-ttu-id="cd5d3-298">なし</span><span class="sxs-lookup"><span data-stu-id="cd5d3-298">None</span></span>||
|<span data-ttu-id="cd5d3-299">条件</span><span class="sxs-lookup"><span data-stu-id="cd5d3-299">Conditions</span></span>|<span data-ttu-id="cd5d3-300">ユーザーのリスク</span><span class="sxs-lookup"><span data-stu-id="cd5d3-300">User risk</span></span>|<span data-ttu-id="cd5d3-301">高</span><span class="sxs-lookup"><span data-stu-id="cd5d3-301">High</span></span>|<span data-ttu-id="cd5d3-302">オン</span><span class="sxs-lookup"><span data-stu-id="cd5d3-302">Selected</span></span>|

<span data-ttu-id="cd5d3-303">**コントロール**</span><span class="sxs-lookup"><span data-stu-id="cd5d3-303">**Controls**</span></span>

| <span data-ttu-id="cd5d3-304">型</span><span class="sxs-lookup"><span data-stu-id="cd5d3-304">Type</span></span> | <span data-ttu-id="cd5d3-305">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-305">Properties</span></span> | <span data-ttu-id="cd5d3-306">値</span><span class="sxs-lookup"><span data-stu-id="cd5d3-306">Values</span></span>                  | <span data-ttu-id="cd5d3-307">メモ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-307">Notes</span></span> |
|:-----|:-----------|:------------------------|:------|
|      | <span data-ttu-id="cd5d3-308">アクセス</span><span class="sxs-lookup"><span data-stu-id="cd5d3-308">Access</span></span>     | <span data-ttu-id="cd5d3-309">SSL 経由でのみ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-309">Allow access</span></span>            | <span data-ttu-id="cd5d3-310">True</span><span class="sxs-lookup"><span data-stu-id="cd5d3-310">True</span></span>  |
|      | <span data-ttu-id="cd5d3-311">アクセス</span><span class="sxs-lookup"><span data-stu-id="cd5d3-311">Access</span></span>     | <span data-ttu-id="cd5d3-312">パスワードの変更を必須とする</span><span class="sxs-lookup"><span data-stu-id="cd5d3-312">Require password change</span></span> | <span data-ttu-id="cd5d3-313">True</span><span class="sxs-lookup"><span data-stu-id="cd5d3-313">True</span></span>  |

<span data-ttu-id="cd5d3-314">**レビュー:** 該当なし</span><span class="sxs-lookup"><span data-stu-id="cd5d3-314">**Review:** not applicable</span></span>

> [!NOTE]
> <span data-ttu-id="cd5d3-p116">\*\*\*\* 選択することで、このポリシーを有効にすることを確認します。ポリシーをテストする[場合](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif)このツールを使用して検討してください。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p116">Be sure to enable this policy, by choosing **On**. Also consider using the [What if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) tool to test the policy</span></span>

## <a name="define-app-protection-policies"></a><span data-ttu-id="cd5d3-317">アプリケーション保護のポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-317">Define app protection policies</span></span>
<span data-ttu-id="cd5d3-p117">どのアプリが許可されたアプリケーション保護ポリシーの定義し、アクション組織のデータを取得することができます。Intune アプリケーションに、Azure ポータル内からの保護ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p117">App protection policies define which apps are allowed and the actions they can take with your organization's data. Create Intune app protection policies from within the Azure portal.</span></span> 

<span data-ttu-id="cd5d3-320">プラットフォームごとにポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-320">Create a policy for each platform:</span></span>
- <span data-ttu-id="cd5d3-321">iOS</span><span class="sxs-lookup"><span data-stu-id="cd5d3-321">iOS</span></span>
- <span data-ttu-id="cd5d3-322">Android</span><span class="sxs-lookup"><span data-stu-id="cd5d3-322">Android</span></span>
- <span data-ttu-id="cd5d3-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="cd5d3-323">Windows 10</span></span>

<span data-ttu-id="cd5d3-p118">新しいアプリケーションの保護ポリシーを作成するのには、管理者の資格情報を使用して、Microsoft Azure ポータルにログインしに移動**モバイル アプリケーション > アプリケーションの保護ポリシー**。**ポリシーの追加**」を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p118">To create a new app protection policy, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Mobile apps > App protection policies**. Choose **Add a policy**.</span></span>

<span data-ttu-id="cd5d3-p119">アプリケーション保護でわずかな違いポリシー オプションは iOS および Android の間です。Android 用に特別には、ポリシーの下。その他のポリシーのガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p119">There are slight differences in the app protection policy options between iOS and Android. The below policy is specifically for Android. Use this as a guide for your other policies.</span></span>

<span data-ttu-id="cd5d3-329">推奨アプリケーションのリストには次のものが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-329">The recommended list of apps includes the following:</span></span>
- <span data-ttu-id="cd5d3-330">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="cd5d3-330">PowerPoint</span></span>
- <span data-ttu-id="cd5d3-331">Excel</span><span class="sxs-lookup"><span data-stu-id="cd5d3-331">Excel</span></span>
- <span data-ttu-id="cd5d3-332">Word</span><span class="sxs-lookup"><span data-stu-id="cd5d3-332">Word</span></span>
- <span data-ttu-id="cd5d3-333">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd5d3-333">Microsoft Teams</span></span>
- <span data-ttu-id="cd5d3-334">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="cd5d3-334">Microsoft SharePoint</span></span>
- <span data-ttu-id="cd5d3-335">Microsoft Visio ビューアー</span><span class="sxs-lookup"><span data-stu-id="cd5d3-335">Microsoft Visio Viewer</span></span>
- <span data-ttu-id="cd5d3-336">OneDrive</span><span class="sxs-lookup"><span data-stu-id="cd5d3-336">OneDrive</span></span>
- <span data-ttu-id="cd5d3-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="cd5d3-337">OneNote</span></span>
- <span data-ttu-id="cd5d3-338">Outlook</span><span class="sxs-lookup"><span data-stu-id="cd5d3-338">Outlook</span></span>

<span data-ttu-id="cd5d3-339">次の表では、推奨される設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-339">The following tables describe the recommended settings:</span></span>

|<span data-ttu-id="cd5d3-340">型</span><span class="sxs-lookup"><span data-stu-id="cd5d3-340">Type</span></span>|<span data-ttu-id="cd5d3-341">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-341">Properties</span></span>|<span data-ttu-id="cd5d3-342">値</span><span class="sxs-lookup"><span data-stu-id="cd5d3-342">Values</span></span>|<span data-ttu-id="cd5d3-343">メモ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-343">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="cd5d3-344">データ再配置</span><span class="sxs-lookup"><span data-stu-id="cd5d3-344">Data relocation</span></span>|<span data-ttu-id="cd5d3-345">[Android でのバックアップを禁止する]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-345">Prevent Android backup</span></span>|<span data-ttu-id="cd5d3-346">はい</span><span class="sxs-lookup"><span data-stu-id="cd5d3-346">Yes</span></span>|<span data-ttu-id="cd5d3-347">iOS では、特に iTunes と iCloud が呼び出されます</span><span class="sxs-lookup"><span data-stu-id="cd5d3-347">On iOS this will specifically call out iTunes and iCloud</span></span>|
||<span data-ttu-id="cd5d3-348">[アプリで他のアプリへのデータ転送を許可する]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-348">Allow app to transfer data to other apps</span></span>|<span data-ttu-id="cd5d3-349">ポリシーで管理されているアプリ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-349">Policy managed apps</span></span>||
||<span data-ttu-id="cd5d3-350">このアプリで他のアプリからデータを受信できるようにする</span><span class="sxs-lookup"><span data-stu-id="cd5d3-350">Allow app to receive data from other apps</span></span>|<span data-ttu-id="cd5d3-351">ポリシーで管理されているアプリ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-351">Policy managed apps</span></span>||
||<span data-ttu-id="cd5d3-352">[名前を付けて保存] を禁止する</span><span class="sxs-lookup"><span data-stu-id="cd5d3-352">Prevent "Save As"</span></span>|<span data-ttu-id="cd5d3-353">はい</span><span class="sxs-lookup"><span data-stu-id="cd5d3-353">Yes</span></span>||
||<span data-ttu-id="cd5d3-354">会社のデータを保存できるストレージ サービスの選択</span><span class="sxs-lookup"><span data-stu-id="cd5d3-354">Select which storage services corporate data can be saved to</span></span>|<span data-ttu-id="cd5d3-355">ビジネスでは、SharePoint の OneDrive</span><span class="sxs-lookup"><span data-stu-id="cd5d3-355">OneDrive for Business, SharePoint</span></span>||
||<span data-ttu-id="cd5d3-356">他のアプリとの間で切り取り、コピー、貼り付けを制限する</span><span class="sxs-lookup"><span data-stu-id="cd5d3-356">Restrict cut, copy, and paste with other apps</span></span>|<span data-ttu-id="cd5d3-357">ポリシー管理対象のアプリケーションでの貼り付けで</span><span class="sxs-lookup"><span data-stu-id="cd5d3-357">Policy managed apps with paste in</span></span>||
||<span data-ttu-id="cd5d3-358">Web コンテンツを管理対象ブラウザーで表示するように制限する</span><span class="sxs-lookup"><span data-stu-id="cd5d3-358">Restrict web content to display in the managed browser</span></span>|<span data-ttu-id="cd5d3-359">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-359">No</span></span>||
||<span data-ttu-id="cd5d3-360">[アプリ データの暗号化]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-360">Encrypt app data</span></span>|<span data-ttu-id="cd5d3-361">はい</span><span class="sxs-lookup"><span data-stu-id="cd5d3-361">Yes</span></span>|<span data-ttu-id="cd5d3-362">iOS では、[デバイスがロックされている場合] オプションを選択します</span><span class="sxs-lookup"><span data-stu-id="cd5d3-362">On iOS select option: When device is locked</span></span>|
||<span data-ttu-id="cd5d3-363">デバイスが有効になっているときに、アプリケーションの暗号化を無効にします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-363">Disable app encryption when device is enabled</span></span>|<span data-ttu-id="cd5d3-364">はい</span><span class="sxs-lookup"><span data-stu-id="cd5d3-364">Yes</span></span>|<span data-ttu-id="cd5d3-365">二重の暗号化を回避するには、この設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-365">Disable this setting to avoid double encryption</span></span>|
||<span data-ttu-id="cd5d3-366">連絡先の同期を無効にする</span><span class="sxs-lookup"><span data-stu-id="cd5d3-366">Disable contacts sync</span></span>|<span data-ttu-id="cd5d3-367">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-367">No</span></span>||
||<span data-ttu-id="cd5d3-368">印刷を無効にします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-368">Disable printing</span></span>|<span data-ttu-id="cd5d3-369">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-369">No</span></span>||
|<span data-ttu-id="cd5d3-370">アクセス</span><span class="sxs-lookup"><span data-stu-id="cd5d3-370">Access</span></span>|<span data-ttu-id="cd5d3-371">アクセスのために PIN を要求する</span><span class="sxs-lookup"><span data-stu-id="cd5d3-371">Require PIN for access</span></span>|<span data-ttu-id="cd5d3-372">はい</span><span class="sxs-lookup"><span data-stu-id="cd5d3-372">Yes</span></span>||
||<span data-ttu-id="cd5d3-373">タイプを選択します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-373">Select Type</span></span>|<span data-ttu-id="cd5d3-374">数値</span><span class="sxs-lookup"><span data-stu-id="cd5d3-374">Numeric</span></span>||
||<span data-ttu-id="cd5d3-375">単純な PIN を許可する</span><span class="sxs-lookup"><span data-stu-id="cd5d3-375">Allow simple PIN</span></span>|<span data-ttu-id="cd5d3-376">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-376">No</span></span>||
||<span data-ttu-id="cd5d3-377">PIN の長さ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-377">PIN length</span></span>|<span data-ttu-id="cd5d3-378">6</span><span class="sxs-lookup"><span data-stu-id="cd5d3-378">6</span></span>||
||<span data-ttu-id="cd5d3-379">PIN の代わりに指紋を要求する</span><span class="sxs-lookup"><span data-stu-id="cd5d3-379">Allow fingerprint instead of PIN</span></span>|<span data-ttu-id="cd5d3-380">はい</span><span class="sxs-lookup"><span data-stu-id="cd5d3-380">Yes</span></span>||
||<span data-ttu-id="cd5d3-381">デバイスの暗証番号 (pin) が管理されている場合は、暗証番号 (pin) のアプリケーションを無効にします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-381">Disable app PIN when device PIN is managed</span></span>|<span data-ttu-id="cd5d3-382">はい</span><span class="sxs-lookup"><span data-stu-id="cd5d3-382">Yes</span></span>||
||<span data-ttu-id="cd5d3-383">アクセスのために企業の資格情報を必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-383">Require corporate credentials for access</span></span>|<span data-ttu-id="cd5d3-384">いいえ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-384">No</span></span>||
||<span data-ttu-id="cd5d3-385">[(分数) 後に、アクセス要件を再確認する]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-385">Recheck the access requirement after (minutes)</span></span>|<span data-ttu-id="cd5d3-386">30</span><span class="sxs-lookup"><span data-stu-id="cd5d3-386">30</span></span>||
||<span data-ttu-id="cd5d3-387">[スクリーン キャプチャと Android Assistant をブロックする]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-387">Block screen capture and Android assistant</span></span>|<span data-ttu-id="cd5d3-388">[いいえ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-388">No</span></span>|<span data-ttu-id="cd5d3-389">iOS では、このオプションは使用できません</span><span class="sxs-lookup"><span data-stu-id="cd5d3-389">On iOS this is not an available option</span></span>|
|<span data-ttu-id="cd5d3-390">サインインのセキュリティ要件</span><span class="sxs-lookup"><span data-stu-id="cd5d3-390">Sign-in security requirements</span></span>|<span data-ttu-id="cd5d3-391">最大 PIN の試行</span><span class="sxs-lookup"><span data-stu-id="cd5d3-391">Max PIN attempts</span></span>|<span data-ttu-id="cd5d3-392">5</span><span class="sxs-lookup"><span data-stu-id="cd5d3-392">5</span></span>|<span data-ttu-id="cd5d3-393">Pin をリセットします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-393">Reset Pin</span></span>|
||<span data-ttu-id="cd5d3-394">[オフラインの猶予期間]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-394">Offline grace period</span></span>|<span data-ttu-id="cd5d3-395">720</span><span class="sxs-lookup"><span data-stu-id="cd5d3-395">720</span></span>|<span data-ttu-id="cd5d3-396">アクセスの禁止</span><span class="sxs-lookup"><span data-stu-id="cd5d3-396">Block access</span></span>|
||<span data-ttu-id="cd5d3-397">アプリのデータがワイプされるまでのオフライン期間 (日数)</span><span class="sxs-lookup"><span data-stu-id="cd5d3-397">Offline interval (days) before app data is wiped</span></span>|<span data-ttu-id="cd5d3-398">90</span><span class="sxs-lookup"><span data-stu-id="cd5d3-398">90</span></span>|<span data-ttu-id="cd5d3-399">データを消去します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-399">Wipe data</span></span>|
||<span data-ttu-id="cd5d3-400">Jailbroken とルート デバイス</span><span class="sxs-lookup"><span data-stu-id="cd5d3-400">Jailbroken/rooted devices</span></span>| |<span data-ttu-id="cd5d3-401">データを消去します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-401">Wipe data</span></span>|

<span data-ttu-id="cd5d3-p120">完了したら、「作成」を選択するには注意してください。この手順を繰り返し、選択したプラットフォーム (ドロップダウン リスト) を iOS に置き換えます。ので、ポリシーを作成したら、ポリシーをグループに割り当てるし、展開、この 2 つのアプリケーション ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p120">When complete, remember to select "Create". Repeat the above steps and replace the selected platform (dropdown) with iOS. This creates two app policies, so once you create the policy, then assign groups to the policy and deploy it.</span></span>

<span data-ttu-id="cd5d3-405">ポリシーを編集し、ユーザーにこれらのポリシーを割り当て、[作成し、アプリケーションの保護ポリシーを割り当てる方法](https://docs.microsoft.com/intune/app-protection-policies)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-405">To edit the policies and assign these policies to users, see [How to create and assign app protection policies](https://docs.microsoft.com/intune/app-protection-policies).</span></span> 

## <a name="require-approved-apps"></a><span data-ttu-id="cd5d3-406">承認済みのアプリケーションを必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-406">Require approved apps</span></span>
<span data-ttu-id="cd5d3-407">必要とするには、アプリケーションを承認します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-407">To require approved apps:</span></span>

1. <span data-ttu-id="cd5d3-p121">[Azure ポータル](https://portal.azure.com)に移動し、ユーザーの資格情報を使用してサインインします。正常にサインインして後、は、Azure のダッシュ ボードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p121">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="cd5d3-410">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-410">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="cd5d3-411">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-411">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="cd5d3-412">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-412">Choose **New policy**.</span></span>

5. <span data-ttu-id="cd5d3-413">ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-413">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="cd5d3-414">**[クラウド アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-414">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="cd5d3-p122">**アプリケーションの選択**を選択して、**クラウドのアプリ**一覧から目的のアプリケーションを選択します。たとえば、Office 365 の Exchange のオンラインを選択します。**選択**し、**実行**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p122">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="cd5d3-418">**[アクセス制御]** セクションから **[許可]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-418">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="cd5d3-p123">**クライアント アプリケーションの承認を必要とする**を選択して、**アクセスを許可する**を選択します。複数のコントロールでは、**選択したコントロールを必要と**するを選択し、**選択**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p123">Choose **Grant access**, select **Require approved client app**. For multiple controls, select **Require the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="cd5d3-421">[ **Create**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-421">Choose **Create**.</span></span>

## <a name="define-device-compliance-policies"></a><span data-ttu-id="cd5d3-422">デバイスのコンプライアンス ・ ポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-422">Define device-compliance policies</span></span>

<span data-ttu-id="cd5d3-p124">デバイスのコンプライアンス ・ ポリシーは、デバイス準拠としてマークするために従う必要がある要件を定義します。Intune デバイスから Azure ポータル内でのコンプライアンス ・ ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p124">Device-compliance policies define the requirements that devices must adhere to in order to be marked as compliant. Create Intune device compliance policies from within the Azure portal.</span></span> 

<span data-ttu-id="cd5d3-425">プラットフォームごとにポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-425">Create a policy for each platform:</span></span>
- <span data-ttu-id="cd5d3-426">Android</span><span class="sxs-lookup"><span data-stu-id="cd5d3-426">Android</span></span>
- <span data-ttu-id="cd5d3-427">Android エンタープライズ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-427">Android enterprise</span></span>
- <span data-ttu-id="cd5d3-428">iOS</span><span class="sxs-lookup"><span data-stu-id="cd5d3-428">iOS</span></span>
- <span data-ttu-id="cd5d3-429">macOS</span><span class="sxs-lookup"><span data-stu-id="cd5d3-429">macOS</span></span>
- <span data-ttu-id="cd5d3-430">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="cd5d3-430">Windows Phone 8.1</span></span>
- <span data-ttu-id="cd5d3-431">およびそれ以降の Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="cd5d3-431">Windows 8.1 and later</span></span>
- <span data-ttu-id="cd5d3-432">Windows 10 以降</span><span class="sxs-lookup"><span data-stu-id="cd5d3-432">Windows 10 and later</span></span>

<span data-ttu-id="cd5d3-p125">デバイスのコンプライアンス ・ ポリシーを作成するに、管理者の資格情報を使用して、Microsoft Azure ポータルにログインしに移動**Intune > デバイス対応**です。**作成ポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p125">To create device compliance policies, log in to the Microsoft Azure portal with your administer credentials, and then navigate to **Intune > Device compliance**. Select **Create policy**.</span></span>

<span data-ttu-id="cd5d3-435">次の設定は、Windows の 10 に適しています。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-435">The following settings are recommended for Windows 10.</span></span>

<span data-ttu-id="cd5d3-436">**デバイス状態: Windows の稼働状態の認証サービスの評価の規則**</span><span class="sxs-lookup"><span data-stu-id="cd5d3-436">**Device health: Windows Health Attestation Service evaluation rules**</span></span>

|<span data-ttu-id="cd5d3-437">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-437">Properties</span></span>|<span data-ttu-id="cd5d3-438">値</span><span class="sxs-lookup"><span data-stu-id="cd5d3-438">Values</span></span>|<span data-ttu-id="cd5d3-439">メモ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-439">Notes</span></span>|
|:---------|:-----|:----|
|<span data-ttu-id="cd5d3-440">BitLocker を必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-440">Require BitLocker</span></span>|<span data-ttu-id="cd5d3-441">必須</span><span class="sxs-lookup"><span data-stu-id="cd5d3-441">Require</span></span>||
|<span data-ttu-id="cd5d3-442">デバイスで有効にする、セキュリティで保護されたブートを必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-442">Require Secure Boot to be enabled on the device</span></span>|<span data-ttu-id="cd5d3-443">必須</span><span class="sxs-lookup"><span data-stu-id="cd5d3-443">Require</span></span>||
|<span data-ttu-id="cd5d3-444">コードの整合性を必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-444">Require code integrity</span></span>|<span data-ttu-id="cd5d3-445">必須</span><span class="sxs-lookup"><span data-stu-id="cd5d3-445">Require</span></span>||


<span data-ttu-id="cd5d3-446">**デバイスのプロパティ**</span><span class="sxs-lookup"><span data-stu-id="cd5d3-446">**Device properties**</span></span>

|<span data-ttu-id="cd5d3-447">型</span><span class="sxs-lookup"><span data-stu-id="cd5d3-447">Type</span></span>|<span data-ttu-id="cd5d3-448">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-448">Properties</span></span>|<span data-ttu-id="cd5d3-449">値</span><span class="sxs-lookup"><span data-stu-id="cd5d3-449">Values</span></span>|<span data-ttu-id="cd5d3-450">メモ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-450">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="cd5d3-451">オペレーティング システムのバージョン</span><span class="sxs-lookup"><span data-stu-id="cd5d3-451">Operating system version</span></span>|<span data-ttu-id="cd5d3-452">すべて</span><span class="sxs-lookup"><span data-stu-id="cd5d3-452">All</span></span>|<span data-ttu-id="cd5d3-453">未構成</span><span class="sxs-lookup"><span data-stu-id="cd5d3-453">Not configured</span></span>||

<span data-ttu-id="cd5d3-p126">すべてを考慮する上のポリシーは、展開にする必要がありますを対象にユーザー グループ。ポリシーを作成することによってこれを行う (保存時) 以降 (追加と同じレベル) の [**ポリシー** ] セクションで **[展開の管理**を選択するとします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p126">For all the above policies to be considered deployed, they must be targeted at user groups. You can do this by creating the policy (on Save) or later by selecting **Manage Deployment** in the **Policy** section (same level as Add).</span></span>

<span data-ttu-id="cd5d3-456">**システム セキュリティ**</span><span class="sxs-lookup"><span data-stu-id="cd5d3-456">**System security**</span></span>

|<span data-ttu-id="cd5d3-457">型</span><span class="sxs-lookup"><span data-stu-id="cd5d3-457">Type</span></span>|<span data-ttu-id="cd5d3-458">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-458">Properties</span></span>|<span data-ttu-id="cd5d3-459">値</span><span class="sxs-lookup"><span data-stu-id="cd5d3-459">Values</span></span>|<span data-ttu-id="cd5d3-460">メモ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-460">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="cd5d3-461">Password</span><span class="sxs-lookup"><span data-stu-id="cd5d3-461">Password</span></span>|<span data-ttu-id="cd5d3-462">モバイル デバイスのロックを解除するパスワードを要求します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-462">Require a password to unlock mobile devices</span></span>|<span data-ttu-id="cd5d3-463">必須</span><span class="sxs-lookup"><span data-stu-id="cd5d3-463">Require</span></span>||
||<span data-ttu-id="cd5d3-464">単純なパスワード</span><span class="sxs-lookup"><span data-stu-id="cd5d3-464">Simple passwords</span></span>|<span data-ttu-id="cd5d3-465">ブロック</span><span class="sxs-lookup"><span data-stu-id="cd5d3-465">Block</span></span>||
||<span data-ttu-id="cd5d3-466">パスワードの種類</span><span class="sxs-lookup"><span data-stu-id="cd5d3-466">Password type</span></span>|<span data-ttu-id="cd5d3-467">デバイスの既定値</span><span class="sxs-lookup"><span data-stu-id="cd5d3-467">Device default</span></span>||
||<span data-ttu-id="cd5d3-468">パスワードの最小文字数</span><span class="sxs-lookup"><span data-stu-id="cd5d3-468">Minimum password length</span></span>|<span data-ttu-id="cd5d3-469">6</span><span class="sxs-lookup"><span data-stu-id="cd5d3-469">6</span></span>||
||<span data-ttu-id="cd5d3-470">パスワードが要求される前にアクティブでない最大の分</span><span class="sxs-lookup"><span data-stu-id="cd5d3-470">Maximum minutes of inactivity before password is required</span></span>|<span data-ttu-id="cd5d3-471">15 </span><span class="sxs-lookup"><span data-stu-id="cd5d3-471">15</span></span>|<span data-ttu-id="cd5d3-p127">Android バージョン 4.0 以降では、この設定はサポートされてまたは連盟ノックス ・ 4.0 およびそれ以上。IOS デバイスは、サポートされている iOS 8.0 以降で</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p127">This setting is supported for Android versions 4.0 and above or KNOX 4.0 and above. For iOS devices, it’s supported for iOS 8.0 and above</span></span>|
||<span data-ttu-id="cd5d3-474">パスワードの有効期限 (日)</span><span class="sxs-lookup"><span data-stu-id="cd5d3-474">Password expiration (days)</span></span>|<span data-ttu-id="cd5d3-475">41</span><span class="sxs-lookup"><span data-stu-id="cd5d3-475">41</span></span>||
||<span data-ttu-id="cd5d3-476">再利用を防ぐために以前のパスワードの数</span><span class="sxs-lookup"><span data-stu-id="cd5d3-476">Number of previous passwords to prevent reuse</span></span>|<span data-ttu-id="cd5d3-477">5</span><span class="sxs-lookup"><span data-stu-id="cd5d3-477">5</span></span>||
||<span data-ttu-id="cd5d3-478">デバイス (モバイルおよび Holographic)、アイドル状態から制御が戻るときにパスワードを必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-478">Require password when device returns from idle state (Mobile and Holographic)</span></span>|<span data-ttu-id="cd5d3-479">必須</span><span class="sxs-lookup"><span data-stu-id="cd5d3-479">Require</span></span>|<span data-ttu-id="cd5d3-480">Windows の 10 の利用可能であり、後で</span><span class="sxs-lookup"><span data-stu-id="cd5d3-480">Available for Windows 10 and later</span></span>|
|<span data-ttu-id="cd5d3-481">暗号化</span><span class="sxs-lookup"><span data-stu-id="cd5d3-481">Encryption</span></span>|<span data-ttu-id="cd5d3-482">デバイス上のデータ ・ ストレージの暗号化</span><span class="sxs-lookup"><span data-stu-id="cd5d3-482">Encryption of data storage on device</span></span>|<span data-ttu-id="cd5d3-483">必須</span><span class="sxs-lookup"><span data-stu-id="cd5d3-483">Require</span></span>||
|<span data-ttu-id="cd5d3-484">デバイスのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-484">Device Security</span></span>|<span data-ttu-id="cd5d3-485">ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="cd5d3-485">Firewall</span></span>|<span data-ttu-id="cd5d3-486">必須</span><span class="sxs-lookup"><span data-stu-id="cd5d3-486">Require</span></span>||
||<span data-ttu-id="cd5d3-487">ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="cd5d3-487">Antivirus</span></span>|<span data-ttu-id="cd5d3-488">必須</span><span class="sxs-lookup"><span data-stu-id="cd5d3-488">Require</span></span>||
||<span data-ttu-id="cd5d3-489">スパイウェア対策</span><span class="sxs-lookup"><span data-stu-id="cd5d3-489">Antispyware</span></span>|<span data-ttu-id="cd5d3-490">必須</span><span class="sxs-lookup"><span data-stu-id="cd5d3-490">Require</span></span>|<span data-ttu-id="cd5d3-491">この設定には、Windows セキュリティ センターに登録されている、スパイウェア対策ソリューションが必要です。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-491">This setting requires an Anti-Spyware solution registered with Windows Security Center</span></span>|
|<span data-ttu-id="cd5d3-492">Defender</span><span class="sxs-lookup"><span data-stu-id="cd5d3-492">Defender</span></span>|<span data-ttu-id="cd5d3-493">Windows Defender のウイルス対策</span><span class="sxs-lookup"><span data-stu-id="cd5d3-493">Windows Defender Antimalware</span></span>|<span data-ttu-id="cd5d3-494">必須</span><span class="sxs-lookup"><span data-stu-id="cd5d3-494">Require</span></span>||
||<span data-ttu-id="cd5d3-495">Windows Defender マルウェア対策用の最小バージョン</span><span class="sxs-lookup"><span data-stu-id="cd5d3-495">Windows Defender Antimalware minimum version</span></span>||<span data-ttu-id="cd5d3-p128">10 の Windows デスクトップでのみサポートされています。推奨バージョン以上の最新のバージョン 5 の背後にあります。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p128">Only supported for Windows 10 desktop. Microsoft recommends versions no more than five behind from the most recent version</span></span>|
||<span data-ttu-id="cd5d3-498">Windows Defender のウイルス対策署名を最新の状態</span><span class="sxs-lookup"><span data-stu-id="cd5d3-498">Windows Defender Antimalware signature up to date</span></span>|<span data-ttu-id="cd5d3-499">必須</span><span class="sxs-lookup"><span data-stu-id="cd5d3-499">Require</span></span>||
||<span data-ttu-id="cd5d3-500">リアルタイム保護</span><span class="sxs-lookup"><span data-stu-id="cd5d3-500">Real-time protection</span></span>|<span data-ttu-id="cd5d3-501">必須</span><span class="sxs-lookup"><span data-stu-id="cd5d3-501">Require</span></span>|<span data-ttu-id="cd5d3-502">10 の Windows デスクトップでのみサポート</span><span class="sxs-lookup"><span data-stu-id="cd5d3-502">Only supported for Windows 10 desktop</span></span>|

<span data-ttu-id="cd5d3-503">**Windows Defender ATP**</span><span class="sxs-lookup"><span data-stu-id="cd5d3-503">**Windows Defender ATP**</span></span>

|<span data-ttu-id="cd5d3-504">型</span><span class="sxs-lookup"><span data-stu-id="cd5d3-504">Type</span></span>|<span data-ttu-id="cd5d3-505">[プロパティ]</span><span class="sxs-lookup"><span data-stu-id="cd5d3-505">Properties</span></span>|<span data-ttu-id="cd5d3-506">値</span><span class="sxs-lookup"><span data-stu-id="cd5d3-506">Values</span></span>|<span data-ttu-id="cd5d3-507">メモ</span><span class="sxs-lookup"><span data-stu-id="cd5d3-507">Notes</span></span>|
|:---|:---------|:-----|:----|
|<span data-ttu-id="cd5d3-508">Windows Defender の高度な脅威保護のルール</span><span class="sxs-lookup"><span data-stu-id="cd5d3-508">Windows Defender Advanced Threat Protection rules</span></span>|<span data-ttu-id="cd5d3-509">またはマシン ・ リスク ・ スコアの下にデバイスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-509">Require the device to be at or under the machine-risk score</span></span>|<span data-ttu-id="cd5d3-510">中</span><span class="sxs-lookup"><span data-stu-id="cd5d3-510">Medium</span></span>||

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a><span data-ttu-id="cd5d3-511">準拠の Pc (ですが、準拠していないフォンやタブレット) を必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-511">Require compliant PCs (but not compliant phones and tablets)</span></span>
<span data-ttu-id="cd5d3-p129">準拠の Pc を必要とするポリシーを追加する前に必ず Intune への管理用のデバイスを登録してください。Intune に確実に目的のユーザーの所有していることには、デバイスのデバイスを登録する前に、多要素認証を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p129">Before adding a policy to require compliant PCs, be sure to enroll devices for management into Intune. Using multi-factor authentication is recommended before enrolling devices into Intune for assurance that the device is in the possession of the intended user.</span></span> 

<span data-ttu-id="cd5d3-514">適合した Pc が必要です。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-514">To require compliant PCs:</span></span>

1. <span data-ttu-id="cd5d3-p130">[Azure ポータル](https://portal.azure.com)に移動し、ユーザーの資格情報を使用してサインインします。正常にサインインして後、は、Azure のダッシュ ボードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p130">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="cd5d3-517">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-517">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="cd5d3-518">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-518">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="cd5d3-519">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-519">Choose **New policy**.</span></span>

5. <span data-ttu-id="cd5d3-520">ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-520">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="cd5d3-521">**[クラウド アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-521">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="cd5d3-p131">**アプリケーションの選択**を選択して、**クラウドのアプリ**一覧から目的のアプリケーションを選択します。たとえば、Office 365 の Exchange のオンラインを選択します。**選択**し、**実行**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p131">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="cd5d3-p132">準拠を必要とするには、Pc が、準拠していないフォンやタブレット、**条件**と**デバイスのプラットフォーム**を選択します。**デバイスのプラットフォーム**を選択し、 **Windows**と**macOS**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p132">To require compliant PCs, but not compliant phones and tablets, choose **Conditions** and **Device platforms**. Choose **Select device platforms** and select **Windows** and **macOS**.</span></span>

9. <span data-ttu-id="cd5d3-527">**[アクセス制御]** セクションから **[許可]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-527">Choose **Grant** from the **Access controls** section.</span></span>

10. <span data-ttu-id="cd5d3-p133">**準拠としてマークするデバイスを必要とする**を選択して、**アクセスを許可する**を選択します。複数のコントロールには、**選択したすべてのコントロールを必要と**するを選択し、**選択**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p133">Choose **Grant access**, select **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

11. <span data-ttu-id="cd5d3-530">[ **Create**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-530">Choose **Create**.</span></span>

<span data-ttu-id="cd5d3-p134">準拠の Pc*と*モバイル デバイスを必要とする目的がある場合、プラットフォームを選択することはしません。これは、すべてのデバイスの法令遵守を強制します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p134">If your objective is to require compliant PCs *and* mobile devices, do not select platforms. This enforces compliance for all devices.</span></span> 

## <a name="require-compliant-pcs-and-mobile-devices"></a><span data-ttu-id="cd5d3-533">準拠の Pc*と*モバイル デバイスを必要とします。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-533">Require compliant PCs *and* mobile devices</span></span>

<span data-ttu-id="cd5d3-534">すべてのデバイスのコンプライアンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-534">To require compliance for all devices:</span></span>

1. <span data-ttu-id="cd5d3-p135">[Azure ポータル](https://portal.azure.com)に移動し、ユーザーの資格情報を使用してサインインします。正常にサインインして後、は、Azure のダッシュ ボードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p135">Go to the [Azure portal](https://portal.azure.com), and sign in with your credentials. After you've successfully signed in, you see the Azure dashboard.</span></span>

2. <span data-ttu-id="cd5d3-537">左側のメニューから **[Azure Active Directory]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-537">Choose **Azure Active Directory** from the left menu.</span></span>

3. <span data-ttu-id="cd5d3-538">**[セキュリティ]** セクションで、**[条件付きアクセス]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-538">Under the **Security** section, choose **Conditional access**.</span></span>

4. <span data-ttu-id="cd5d3-539">**[新しいポリシー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-539">Choose **New policy**.</span></span>

5. <span data-ttu-id="cd5d3-540">ポリシー名を入力し、ポリシーを適用する **[ユーザーとグループ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-540">Enter a policy name, then choose the **Users and groups** you want to apply the policy for.</span></span>

6. <span data-ttu-id="cd5d3-541">**[クラウド アプリ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-541">Choose **Cloud apps**.</span></span>

7. <span data-ttu-id="cd5d3-p136">**アプリケーションの選択**を選択して、**クラウドのアプリ**一覧から目的のアプリケーションを選択します。たとえば、Office 365 の Exchange のオンラインを選択します。**選択**し、**実行**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p136">Choose **Select apps**, select the desired apps from the **Cloud apps** list. For example, select Office 365 Exchange Online. Choose **Select** and **Done**.</span></span>

8. <span data-ttu-id="cd5d3-545">**[アクセス制御]** セクションから **[許可]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-545">Choose **Grant** from the **Access controls** section.</span></span>

9. <span data-ttu-id="cd5d3-p137">**準拠としてマークするデバイスを必要とする**を選択して、**アクセスを許可する**を選択します。複数のコントロールには、**選択したすべてのコントロールを必要と**するを選択し、**選択**を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p137">Choose **Grant access**, select **Require device to be marked as compliant**. For multiple controls, select **Require all the selected controls**, then choose **Select**.</span></span> 

10. <span data-ttu-id="cd5d3-548">[ **Create**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-548">Choose **Create**.</span></span>

<span data-ttu-id="cd5d3-p138">このポリシーを作成する場合、プラットフォームを選択することはしません。これは、デバイスの準拠を強制します。</span><span class="sxs-lookup"><span data-stu-id="cd5d3-p138">When creating this policy, do not select platforms. This enforces compliant devices.</span></span>




<!---
#### Data loss prevention
The goal for your device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain or enroll their PCs into management with Microsoft Intune or System Center Configuration Manager.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact

For most organizations, it is important to be able to set user expectations around when and for which conditions they will be expected to sign into Office 365 to access their email.  

Users typically benefit from single sign-on (SSO) except during the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users may be asked to MFA whenever a **medium or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Sensitive
This section describes the recommendations for the sensitive tier of data, identity, and device protection. These recommendations are for customers who have a subset of data that must be protected at higher levels or require all data to be protected at these higher levels.

You can apply increased protection to all or specific data sets in your Office 365 environment. For example, you can apply policies to ensure sensitive data is only shared between protected apps to prevent data loss. We recommend protecting identities and devices that access sensitive data with comparable levels of security.

### Conditional access policy settings
#### Identity protection

You can give users single sign-on (SSO) experience as described in earlier sections. You only need to intervene when necessary based on [risk events](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-risk-events).   

* Require MFA on **low or above** risk sessions
* Require secure password change for high risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data loss prevention

The goal for these device and app management policies is to protect data loss in the event of a lost or stolen device. You can do this by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their PCs to an Active Directory Domain or enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that user devices used to access email are managed by Intune **or** company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and if available, require devices that are **low** risk as determined by a third-party MTP like Lookout or SkyCure.|
|**Apply an Intune App Protection Policy for managed apps running on unmanaged devices**|Apply an Intune App Protection Policy for managed apps running on unmanaged, personal mobile devices to require: a PIN with minimum length 6, device encryption, and that the device is healthy (is not jailbroken, rooted; passes health attestation).|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 email.

Users typically benefit from single sign-on (SSO) except under the following situations:
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to MFA whenever a **low or above** sign-in risk is detected and users has not yet performed MFA in their current sessions.  
  * Users will be required to either use email apps that support the Intune App Protection SDK or access emails from Intune compliant or AD domain-joined devices.
* When users at risk sign-in, and successfully complete MFA, they will be asked to change their password.

## Highly regulated
This section describes the recommendations for the highly regulated tier of data, identity, and device protection. These recommendations are for customers who may have a very small amount of data that is highly classified, trade secret, or regulated data. Microsoft provides capabilities to help organizations meet these requirements, including added protection for identities and devices.

### Conditional access policy settings
#### Identity protection

For the highly regulated tier Microsoft recommends enforcing MFA for all new sessions.
* Require MFA for all new sessions
* Require secure password change for **high** risk users

>[!IMPORTANT]
>[Password synchronization](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization) and [self-service password reset](https://docs.microsoft.com/azure/active-directory/active-directory-passwords) are required for this policy recommendation.
>

#### Data Loss Prevention
The goal for these device and app management policies is to prevent data loss in the event of a lost or stolen device. This is done by ensuring that access to data is protected by a PIN, that the data is encrypted on the device, and that the device is not compromised.

For the highly regulated tier, we recommend requiring apps that support Intune App Protection policy running only on Intune compliant or domain-joined devices.

|Policy recommendation|Description|
|:--------------------|:----------|
|**Require user PC management**|Require users to join their Windows PCs to an Active Directory Domain, **or** enroll their PCs into management with Intune or Configuration Manager and ensure those devices are compliant with policies before allowing email access.|
|**Apply security settings via group policy objects (GPO) or Configuration Manager policies for domain joined PCs**|Deploy policies that configure managed PCs to enable BitLocker, enable anti-virus, and enable firewall.|
|**Require user mobile device management**|Require that devices used to access Office 365 email and files are managed by Intune or company email is accessed only through mobile email apps protected by Intune App Protection policies such as Outlook for iOS or Android.|
|**Apply an Intune Device Compliance Policy on managed devices**|Apply an Intune Device Compliance Policy for managed corporate mobile devices and Intune-managed PCs that requires: a PIN with minimum length 6, device encryption, a healthy device (is not jailbroken, rooted; passes health attestation), and, if available, require devices that are Low risk as determined by a third-party MTP like Lookout or SkyCure.|

### User impact
For most organizations, it is important to be able to set expectations for users specific to when and under what conditions they will be expected to sign into Office 365 files.

* Users configured as highly regulated will be required to re-authenticate with MFA after their session expires.
* When users at risk sign-in they will be asked to change their password after completing MFA.
* When requesting authentication tokens for Exchange Online:
  * Users will be asked to perform MFA whenever they begin a new session.  
  * Users will be required to use email apps that support the Intune App Protection SDK
  * Users will be required to access emails from Intune compliant or AD domain-joined devices.
--->
## <a name="next-steps"></a><span data-ttu-id="cd5d3-551">次の手順</span><span class="sxs-lookup"><span data-stu-id="cd5d3-551">Next steps</span></span>

[<span data-ttu-id="cd5d3-552">電子メールをセキュリティで保護するためのポリシーの推奨事項について学びます</span><span class="sxs-lookup"><span data-stu-id="cd5d3-552">Learn about policy recommendations for securing email</span></span>](secure-email-recommended-policies.md)
