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
ms.openlocfilehash: a88fc5f46a6dafda72a24ba5e80587b24a216955
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546482"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="a8da0-103">ゲストおよび外部の B2B アクセスを許可するためのポリシー</span><span class="sxs-lookup"><span data-stu-id="a8da0-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="a8da0-104">この記事では、ビジネス間 (B2B) アカウントアクセス (ゲストおよび外部ユーザー) を許可するために、推奨される一般的な id およびデバイスアクセスポリシーを調整する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8da0-104">This article describes how to adjust the recommended common identity and device access policies to allow Business-to-Business (B2B) account access (guest and external users).</span></span> <span data-ttu-id="a8da0-105">このガイダンスは、 [共通の id およびデバイスアクセスポリシー](identity-access-policies.md)に基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="a8da0-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="a8da0-106">これらの推奨事項は、保護の **ベースライン** 層に適用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="a8da0-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="a8da0-107">ただし、 **機密性** の **高い規制** 保護に対するニーズの粒度に基づいて、推奨事項を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="a8da0-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="a8da0-108">B2B ユーザーが Azure Active Directory (Azure AD) テナントを使用して認証するためのパスを指定しても、ユーザーは環境全体にアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="a8da0-108">Providing a path for B2B users to authenticate with your Azure Active Directory (Azure AD) tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="a8da0-109">B2B ユーザーは、条件付きアクセスポリシーに付与されているサービス内のファイルと共有されているリソースにのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a8da0-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="a8da0-110">ゲストおよび外部アクセスを許可および保護するための共通ポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="a8da0-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="a8da0-111">ゲストおよび外部アクセスを保護するために、次の図は、共通 id およびデバイスアクセスポリシーで追加または更新するポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="a8da0-111">To protect guest and external access, the following diagram illustrates which policies to add or update from the the common identity and device access policies .</span></span> 

<span data-ttu-id="a8da0-112">[![ゲストアクセスを保護するためのポリシー更新の概要](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="a8da0-112">[![Summary of policy updates for protecting guest access](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="a8da0-113">この画像のより大きいバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="a8da0-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="a8da0-114">次の表に、更新または新規作成のどちらかを行う必要があるポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="a8da0-114">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="a8da0-115">共通のポリシーは、 [一般的な id とデバイスアクセスポリシー](identity-access-policies.md) の記事に記載されている関連する構成手順にリンクしています。</span><span class="sxs-lookup"><span data-stu-id="a8da0-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="a8da0-116">保護レベル</span><span class="sxs-lookup"><span data-stu-id="a8da0-116">Protection level</span></span>|<span data-ttu-id="a8da0-117">ポリシー</span><span class="sxs-lookup"><span data-stu-id="a8da0-117">Policies</span></span>|<span data-ttu-id="a8da0-118">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a8da0-118">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="a8da0-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="a8da0-119">**Baseline**</span></span>|[<span data-ttu-id="a8da0-120">ゲストおよび外部ユーザーに対して MFA を常に要求する</span><span class="sxs-lookup"><span data-stu-id="a8da0-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="a8da0-121">この新しいポリシーを作成し、ゲストおよび外部ユーザーにのみ適用します。</span><span class="sxs-lookup"><span data-stu-id="a8da0-121">Create this new policy and apply it only to guests and external users.</span></span> <span data-ttu-id="a8da0-122">[ **サインインリスク**] で、[多要素認証 (MFA) を常に適用する] チェックボックスをオフのままにします。</span><span class="sxs-lookup"><span data-stu-id="a8da0-122">Under **Sign-in risk**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span>|
|        |[<span data-ttu-id="a8da0-123">サインインリスクが*中*または*高*の場合は MFA を必須にする</span><span class="sxs-lookup"><span data-stu-id="a8da0-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="a8da0-124">ゲストユーザーと外部ユーザーを除外するには、このポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="a8da0-124">Modify this policy to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="a8da0-125">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="a8da0-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="a8da0-126">ゲストユーザーと外部ユーザーを除外するには、このポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="a8da0-126">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="a8da0-127">条件付きアクセスポリシーにゲストおよび外部ユーザーを含めたり、除外したりするには、[ **包含** または **除外** ] タブをクリックして、 **すべてのゲストと外部ユーザー**をチェックします。</span><span class="sxs-lookup"><span data-stu-id="a8da0-127">To include or exclude guests and external users in Conditional Access policies, click the **Include** or **Exclude** tab and check **All guests and external users**.</span></span>

![ゲストを除外するためのコントロールの画面キャプチャ](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="a8da0-129">詳細情報</span><span class="sxs-lookup"><span data-stu-id="a8da0-129">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="a8da0-130">ゲストおよび外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="a8da0-130">Guests vs. external users</span></span>
<span data-ttu-id="a8da0-131">Azure AD では、ゲストユーザーと外部ユーザーは同じです。</span><span class="sxs-lookup"><span data-stu-id="a8da0-131">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="a8da0-132">これらの両方のユーザーの種類は Guest です。</span><span class="sxs-lookup"><span data-stu-id="a8da0-132">The user type for both of these is Guest.</span></span> <span data-ttu-id="a8da0-133">ゲストユーザーは B2B ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="a8da0-133">Guest users are B2B users.</span></span>

<span data-ttu-id="a8da0-134">Microsoft Teams では、アプリ内のゲストユーザーと外部ユーザーを区別しますが、認証時には B2B ユーザーになります。</span><span class="sxs-lookup"><span data-stu-id="a8da0-134">Microsoft Teams differentiates between guest users and external users within the app, but these are both B2B users when authenticating.</span></span> <span data-ttu-id="a8da0-135">Teams ゲストおよび外部ユーザーの詳細については、「 [teams のゲストおよび外部アクセスを有効にする](teams-access-policies.md#enabling-guest-and-external-access-for-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8da0-135">For more information about Teams guest and external users, see [Enabling guest and external access for Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="a8da0-136">ゲストおよび外部ユーザーに対して MFA を常に要求する</span><span class="sxs-lookup"><span data-stu-id="a8da0-136">Require MFA always for guest and external users</span></span>
<span data-ttu-id="a8da0-137">このポリシーにより、ゲストがホームテナントで MFA に登録されているかどうかにかかわらず、テナント内の MFA を登録するように求められます。</span><span class="sxs-lookup"><span data-stu-id="a8da0-137">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="a8da0-138">テナント内のリソースにアクセスする場合、ゲストおよび外部ユーザーはすべての要求に対して MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a8da0-138">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="a8da0-139">リスクベースの MFA からゲストユーザーと外部ユーザーを除外する</span><span class="sxs-lookup"><span data-stu-id="a8da0-139">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="a8da0-140">組織は、Azure AD Id 保護を使用して B2B ユーザーに対してリスクベースのポリシーを適用できますが、ホームディレクトリに存在する id があるため、リソースディレクトリでの B2B コラボレーションユーザーの Azure AD Id 保護の実装には制限があります。</span><span class="sxs-lookup"><span data-stu-id="a8da0-140">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="a8da0-141">これらの制限により、ゲストユーザーをリスクベースの MFA ポリシーから除外し、これらのユーザーが常に MFA を使用するようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a8da0-141">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="a8da0-142">詳細については、「 [B2B コラボレーションユーザーの Id 保護の制限事項](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a8da0-142">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="a8da0-143">デバイス管理からゲストユーザーと外部ユーザーを除外する</span><span class="sxs-lookup"><span data-stu-id="a8da0-143">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="a8da0-144">1つの組織のみがデバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="a8da0-144">Only one organization can manage a device.</span></span> <span data-ttu-id="a8da0-145">デバイスコンプライアンスを必要とするポリシーからゲストおよび外部ユーザーを除外しない場合、これらのポリシーによってこれらのユーザーがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="a8da0-145">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-step"></a><span data-ttu-id="a8da0-146">次の手順</span><span class="sxs-lookup"><span data-stu-id="a8da0-146">Next step</span></span>

![手順 4: Microsoft 365 クラウドアプリのポリシー](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="a8da0-148">次の条件付きアクセスポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="a8da0-148">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="a8da0-149">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8da0-149">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="a8da0-150">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a8da0-150">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="a8da0-151">SharePoint</span><span class="sxs-lookup"><span data-stu-id="a8da0-151">SharePoint</span></span>](secure-email-recommended-policies.md)

