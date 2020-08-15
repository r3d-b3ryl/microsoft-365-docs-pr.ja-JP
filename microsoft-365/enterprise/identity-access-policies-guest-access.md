---
title: ゲストおよび外部の B2B アクセスを許可するための id およびデバイスアクセスポリシー-Microsoft 365 for enterprise |Microsoft Docs
description: ゲストおよび外部ユーザーのアクセスを保護するために推奨される条件付きアクセスと関連ポリシーについて説明します。
author: BrendaCarter
manager: johmar
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 0ab4a2d48a1ac90f48bbfee82239fc0c4c1d55d5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686828"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="99e3a-103">ゲストおよび外部の B2B アクセスを許可するためのポリシー</span><span class="sxs-lookup"><span data-stu-id="99e3a-103">Policies for allowing guest and external B2B access</span></span>
<span data-ttu-id="99e3a-104">この記事では、推奨される一般的な id およびデバイスアクセスポリシーを調整して、B2B アカウントアクセス (ゲストおよび外部ユーザー) を許可する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="99e3a-104">This article describes how to adjust the recommended common identity and device access policies to allow B2B account access (guest and external users).</span></span> <span data-ttu-id="99e3a-105">このガイダンスは、 [共通の id およびデバイスアクセスポリシー](identity-access-policies.md)に基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="99e3a-105">This guidance builds on the [Common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="99e3a-106">これらの推奨事項は、保護の **ベースライン** 層に適用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="99e3a-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="99e3a-107">ただし、 **機密性** の **高い規制** 保護に対するニーズの粒度に基づいて、推奨事項を調整することができます。</span><span class="sxs-lookup"><span data-stu-id="99e3a-107">However, you can adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span> 

<span data-ttu-id="99e3a-108">Azure AD テナントを使用して認証するための B2B ユーザーのパスを指定しても、ユーザーは環境全体にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="99e3a-108">Providing a path for B2B users to authenticate with your Azure AD tenant doesn't give these users access to your entire environment.</span></span> <span data-ttu-id="99e3a-109">B2B ユーザーは、条件付きアクセスポリシーに付与されているサービス内のファイルと共有されているリソースにのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="99e3a-109">B2B users only have access to resources that are shared with them (such as files) within the services granted in the conditional access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="99e3a-110">ゲストおよび外部アクセスを許可および保護するための共通ポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="99e3a-110">Updating the common policies to allow and protect guest and external access</span></span> 

<span data-ttu-id="99e3a-111">次の図は、一般的な id とデバイスのアクセスポリシーと、ゲストおよび外部アクセスを保護するために追加または更新するポリシー (鉛筆アイコン) を示しています。</span><span class="sxs-lookup"><span data-stu-id="99e3a-111">The following diagram illustrates the common identity and device access policies and indicates (with a pencil icon) which policies to add or update to protect guest and external access.</span></span> 

![ゲストアクセスを保護するためのポリシー更新の概要](../media/identity-access-ruleset-guest.png)

<span data-ttu-id="99e3a-113">次の表に、更新または新規作成のどちらかを行う必要があるポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="99e3a-113">The following table lists the policies you either need to update or create new.</span></span> <span data-ttu-id="99e3a-114">共通のポリシーは、 [一般的な id とデバイスアクセスポリシー](identity-access-policies.md) の記事に記載されている関連する構成手順にリンクしています。</span><span class="sxs-lookup"><span data-stu-id="99e3a-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="99e3a-115">保護レベル</span><span class="sxs-lookup"><span data-stu-id="99e3a-115">Protection level</span></span>|<span data-ttu-id="99e3a-116">ポリシー</span><span class="sxs-lookup"><span data-stu-id="99e3a-116">Policies</span></span>|<span data-ttu-id="99e3a-117">詳細情報</span><span class="sxs-lookup"><span data-stu-id="99e3a-117">More information</span></span>|
|:---------------|:-------|:----------------|
|<span data-ttu-id="99e3a-118">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="99e3a-118">**Baseline**</span></span>|[<span data-ttu-id="99e3a-119">ゲストおよび外部ユーザーに対して MFA を常に要求する</span><span class="sxs-lookup"><span data-stu-id="99e3a-119">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="99e3a-120">この新しいルールを作成し、ゲストおよび外部ユーザーにのみ適用します。</span><span class="sxs-lookup"><span data-stu-id="99e3a-120">Create this new rule and apply it only to guests and external users.</span></span> <span data-ttu-id="99e3a-121">[サインインリスク] で、[すべてのオプション] をオフのままにして、常に MFA を適用します。</span><span class="sxs-lookup"><span data-stu-id="99e3a-121">Under sign-in risk, leave all options unchecked to always enforce MFA.</span></span>|
|        |[<span data-ttu-id="99e3a-122">サインインリスクが*中*または*高*の場合は MFA を必須にする</span><span class="sxs-lookup"><span data-stu-id="99e3a-122">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="99e3a-123">ゲストユーザーと外部ユーザーを除外するには、このルールを変更します。</span><span class="sxs-lookup"><span data-stu-id="99e3a-123">Modify this rule to exclude guest and external users.</span></span>|
|        |[<span data-ttu-id="99e3a-124">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="99e3a-124">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="99e3a-125">ゲストユーザーと外部ユーザーを除外するには、このルールを変更します。</span><span class="sxs-lookup"><span data-stu-id="99e3a-125">Modify this rule to exclude guest and external users.</span></span>|

<span data-ttu-id="99e3a-126">条件付きアクセスルールにゲストと外部ユーザーを含めたり、除外したりするには、[包含または除外] タブをクリックして、 **すべてのゲストと外部ユーザー**をチェックします。</span><span class="sxs-lookup"><span data-stu-id="99e3a-126">To include or exclude guests and external users in conditional access rules, click the include or exclude tab and check **All guests and external users**.</span></span>

![ゲストを除外するためのコントロールの画面キャプチャ](../media/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="99e3a-128">詳細情報</span><span class="sxs-lookup"><span data-stu-id="99e3a-128">More information</span></span>

### <a name="guests-vs-external-users"></a><span data-ttu-id="99e3a-129">ゲストおよび外部ユーザー</span><span class="sxs-lookup"><span data-stu-id="99e3a-129">Guests vs. external users</span></span>
<span data-ttu-id="99e3a-130">Azure AD では、ゲストユーザーと外部ユーザーは同じです。</span><span class="sxs-lookup"><span data-stu-id="99e3a-130">In Azure AD, guest and external users are the same.</span></span> <span data-ttu-id="99e3a-131">これらの両方のユーザーの種類は Guest です。</span><span class="sxs-lookup"><span data-stu-id="99e3a-131">The user type for both of these is Guest.</span></span> <span data-ttu-id="99e3a-132">ゲストユーザーは B2B ユーザーです。</span><span class="sxs-lookup"><span data-stu-id="99e3a-132">Guest users are B2B users.</span></span>

<span data-ttu-id="99e3a-133">Microsoft Teams では、アプリ内のゲストユーザーと外部ユーザーを区別しますが、認証時には B2B ユーザーになります。</span><span class="sxs-lookup"><span data-stu-id="99e3a-133">Microsoft Teams differentiates between guest users and external users within the app, but these are both B2B users when authenticating.</span></span> <span data-ttu-id="99e3a-134">Teams ゲストおよび外部ユーザーの詳細については、「 [teams のゲストおよび外部アクセスを有効にする](teams-access-policies.md#enabling-guest-and-external-access-for-teams)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99e3a-134">For more information about Teams guest and external users, see [Enabling guest and external access for Teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="99e3a-135">ゲストおよび外部ユーザーに対して MFA を常に要求する</span><span class="sxs-lookup"><span data-stu-id="99e3a-135">Require MFA always for guest and external users</span></span>
<span data-ttu-id="99e3a-136">このルールは、ゲストのホームテナントに MFA が登録されているかどうかに関係なく、ゲストをテナントに登録することを確認します。</span><span class="sxs-lookup"><span data-stu-id="99e3a-136">This rule prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="99e3a-137">テナント内のリソースにアクセスする場合、ゲストおよび外部ユーザーはすべての要求に対して MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="99e3a-137">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span> 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="99e3a-138">リスクベースの MFA からゲストユーザーと外部ユーザーを除外する</span><span class="sxs-lookup"><span data-stu-id="99e3a-138">Excluding guest and external users from risk-based MFA</span></span>
<span data-ttu-id="99e3a-139">組織では Id 保護を使用して B2B ユーザーに対してリスクベースのポリシーを適用することができますが、ホームディレクトリに存在する id があるため、リソースディレクトリでの B2B コラボレーションユーザーの Id 保護の実装には制限があります。</span><span class="sxs-lookup"><span data-stu-id="99e3a-139">While organizations can enforce risk-based policies for B2B users using Identity Protection, there are limitations in the implementation of Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="99e3a-140">これらの制限により、ゲストユーザーをリスクベースの MFA ポリシーから除外し、これらのユーザーが常に MFA を使用するようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="99e3a-140">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span> 

<span data-ttu-id="99e3a-141">詳細については、「 [B2B コラボレーションユーザーの Id 保護の制限事項](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="99e3a-141">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span> 

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="99e3a-142">デバイス管理からゲストユーザーと外部ユーザーを除外する</span><span class="sxs-lookup"><span data-stu-id="99e3a-142">Excluding guest and external users from device management</span></span> 
<span data-ttu-id="99e3a-143">1つの組織のみがデバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="99e3a-143">Only one organization can manage a device.</span></span> <span data-ttu-id="99e3a-144">デバイスコンプライアンスを必要とするポリシーからゲストおよび外部ユーザーを除外しない場合、これらのポリシーによってこれらのユーザーがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="99e3a-144">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="99e3a-145">次の手順</span><span class="sxs-lookup"><span data-stu-id="99e3a-145">Next steps</span></span>

[<span data-ttu-id="99e3a-146">Teams の条件付きアクセスを有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="99e3a-146">Learn how to enable Teams conditional access</span></span>](teams-access-policies.md)

