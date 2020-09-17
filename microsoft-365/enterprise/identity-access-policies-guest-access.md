---
title: ゲストおよび外部の B2B アクセスを許可するための id およびデバイスアクセスポリシー-Microsoft 365 for enterprise |Microsoft Docs
description: ゲストおよび外部ユーザーのアクセスを保護するために推奨される条件付きアクセスと関連ポリシーについて説明します。
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: c61526139111885ec345bc4a4dd3cd6b147370e6
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950810"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="8e8a3-103">ゲストおよび外部の B2B アクセスを許可するためのポリシー</span><span class="sxs-lookup"><span data-stu-id="8e8a3-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="8e8a3-104">この記事では、ビジネス間 (B2B) アカウントアクセス (ゲストおよび外部ユーザー) を許可するために、推奨される一般的な id およびデバイスアクセスポリシーを調整する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-104">This article describes how to adjust the recommended common identity and device access policies to allow Business-to-Business (B2B) account access (guest and external users).</span></span> <span data-ttu-id="8e8a3-105">このガイダンスは、 [共通の id およびデバイスアクセスポリシー](identity-access-policies.md)に基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="8e8a3-106">これらの推奨事項は、保護の **ベースライン** 層に適用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="8e8a3-107">ただし、 **機密性** の **高い規制** 保護に対するニーズの粒度に基づいて、推奨事項を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="8e8a3-108">B2B ユーザーが Azure Active Directory (Azure AD) テナントを使用して認証するためのパスを指定しても、ユーザーは環境全体にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-108">Providing a path for B2B users to authenticate with your Azure Active Directory (Azure AD) tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="8e8a3-109">B2B ユーザーは、条件付きアクセスポリシーに付与されているサービス内のファイルと共有されているリソースにのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="8e8a3-110">ゲストおよび外部アクセスを許可および保護するための共通ポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="8e8a3-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="8e8a3-111">ゲストおよび外部アクセスを保護するために、次の図は、共通 id およびデバイスアクセスポリシーで追加または更新するポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-111">To protect guest and external access, the following diagram illustrates which policies to add or update from the the common identity and device access policies .</span></span> 

<span data-ttu-id="8e8a3-112">[![ゲストアクセスを保護するためのポリシー更新の概要](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="8e8a3-112">[![Summary of policy updates for protecting guest access](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="8e8a3-113">この画像のより大きいバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="8e8a3-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="8e8a3-114">次の表に、更新または新規作成のどちらかを行う必要があるポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-114">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="8e8a3-115">共通のポリシーは、 [一般的な id とデバイスアクセスポリシー](identity-access-policies.md) の記事に記載されている関連する構成手順にリンクしています。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="8e8a3-116">保護レベル</span><span class="sxs-lookup"><span data-stu-id="8e8a3-116">Protection level</span></span>|<span data-ttu-id="8e8a3-117">ポリシー</span><span class="sxs-lookup"><span data-stu-id="8e8a3-117">Policies</span></span>|<span data-ttu-id="8e8a3-118">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8e8a3-118">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="8e8a3-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="8e8a3-119">**Baseline**</span></span>|[<span data-ttu-id="8e8a3-120">ゲストおよび外部ユーザーに対して MFA を常に要求する</span><span class="sxs-lookup"><span data-stu-id="8e8a3-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="8e8a3-121">この新しいポリシーを作成し、ゲストおよび外部ユーザーにのみ適用します。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-121">Create this new policy and apply it only to guests and external users.</span></span> <span data-ttu-id="8e8a3-122">[ **サインインリスク**] で、[多要素認証 (MFA) を常に適用する] チェックボックスをオフのままにします。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-122">Under **Sign-in risk**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span>|
|        |[<span data-ttu-id="8e8a3-123">サインインリスクが*中*または*高*の場合は MFA を必須にする</span><span class="sxs-lookup"><span data-stu-id="8e8a3-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="8e8a3-124">ゲストユーザーと外部ユーザーを除外するには、このポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-124">Modify this policy to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="8e8a3-125">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="8e8a3-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="8e8a3-126">ゲストユーザーと外部ユーザーを除外するには、このポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-126">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="8e8a3-127">条件付きアクセスポリシーにゲストおよび外部ユーザーを含めたり、除外したりするには、[ **包含** または **除外** ] タブをクリックして、 **すべてのゲストと外部ユーザー**をチェックします。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-127">To include or exclude guests and external users in Conditional Access policies, click the **Include** or **Exclude** tab and check **All guests and external users**.</span></span>

![ゲストを除外するためのコントロールの画面キャプチャ](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="8e8a3-129">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8e8a3-129">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="8e8a3-130">ゲストおよび外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="8e8a3-130">Guests vs. external users</span></span>
<span data-ttu-id="8e8a3-131">Azure AD では、ゲストユーザーと外部ユーザーは同じです。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-131">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="8e8a3-132">これらの両方のユーザーの種類は Guest です。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-132">The user type for both of these is Guest.</span></span> <span data-ttu-id="8e8a3-133">ゲストユーザーは B2B ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-133">Guest users are B2B users.</span></span>

<span data-ttu-id="8e8a3-134">Microsoft Teams では、アプリ内のゲストユーザーと外部ユーザーを区別します。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-134">Microsoft Teams differentiates between guest users and external users within the app.</span></span> <span data-ttu-id="8e8a3-135">ゲストユーザーには Azure AD B2B アカウントがあり、teams に追加できます。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-135">Guest users have Azure AD B2B accounts and can be added to teams.</span></span> <span data-ttu-id="8e8a3-136">外部ユーザーは、通話、チャット、会議にのみ参加できます。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-136">External users can only participate in calls, chats, and meetings.</span></span> <span data-ttu-id="8e8a3-137">詳細については、「 [teams のゲストユーザーと外部ユーザーの比較](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-137">For more information, see [this comparison between guest and external users for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="8e8a3-138">Teams の id とデバイスへのアクセスの保護の詳細については、「 [teams のチャット、グループ、ファイルを保護するためのポリシーの推奨事項](teams-access-policies.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-138">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access for Teams</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="8e8a3-139">ゲストおよび外部ユーザーに対して MFA を常に要求する</span><span class="sxs-lookup"><span data-stu-id="8e8a3-139">Require MFA always for guest and external users</span></span>
<span data-ttu-id="8e8a3-140">このポリシーにより、ゲストがホームテナントで MFA に登録されているかどうかにかかわらず、テナント内の MFA を登録するように求められます。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-140">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="8e8a3-141">テナント内のリソースにアクセスする場合、ゲストおよび外部ユーザーはすべての要求に対して MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-141">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="8e8a3-142">リスクベースの MFA からゲストユーザーと外部ユーザーを除外する</span><span class="sxs-lookup"><span data-stu-id="8e8a3-142">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="8e8a3-143">組織は、Azure AD Id 保護を使用して B2B ユーザーに対してリスクベースのポリシーを適用できますが、ホームディレクトリに存在する id があるため、リソースディレクトリでの B2B コラボレーションユーザーの Azure AD Id 保護の実装には制限があります。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-143">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="8e8a3-144">これらの制限により、ゲストユーザーをリスクベースの MFA ポリシーから除外し、これらのユーザーが常に MFA を使用するようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-144">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="8e8a3-145">詳細については、「 [B2B コラボレーションユーザーの Id 保護の制限事項](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-145">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="8e8a3-146">デバイス管理からゲストユーザーと外部ユーザーを除外する</span><span class="sxs-lookup"><span data-stu-id="8e8a3-146">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="8e8a3-147">1つの組織のみがデバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-147">Only one organization can manage a device.</span></span> <span data-ttu-id="8e8a3-148">デバイスコンプライアンスを必要とするポリシーからゲストおよび外部ユーザーを除外しない場合、これらのポリシーによってこれらのユーザーがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-148">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-step"></a><span data-ttu-id="8e8a3-149">次の手順</span><span class="sxs-lookup"><span data-stu-id="8e8a3-149">Next step</span></span>

![手順 4: Microsoft 365 クラウドアプリのポリシー](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="8e8a3-151">次の条件付きアクセスポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="8e8a3-151">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="8e8a3-152">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8e8a3-152">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="8e8a3-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8e8a3-153">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="8e8a3-154">SharePoint</span><span class="sxs-lookup"><span data-stu-id="8e8a3-154">SharePoint</span></span>](secure-email-recommended-policies.md)

