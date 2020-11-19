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
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: 55a84fa8ba31cfd4f981f2820811b541ae340a27
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357625"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="dd4ed-103">ゲストおよび外部の B2B アクセスを許可するためのポリシー</span><span class="sxs-lookup"><span data-stu-id="dd4ed-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="dd4ed-104">この記事では、Azure Active Directory (Azure AD) の企業間 (B2B) アカウントを持つゲストユーザーと外部ユーザーにアクセスを許可するための、推奨される共通 id およびデバイスアクセスポリシーを調整する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-104">This article describes how to adjust the recommended common identity and device access policies to allow access for guest and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="dd4ed-105">このガイダンスは、 [共通の id およびデバイスアクセスポリシー](identity-access-policies.md)に基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="dd4ed-106">これらの推奨事項は、保護の **ベースライン** 層に適用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="dd4ed-107">ただし、 **機密性** の **高い規制** 保護に対するニーズの粒度に基づいて、推奨事項を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="dd4ed-108">Azure AD テナントを使用して認証するための B2B アカウントのパスを指定しても、これらのアカウントは環境全体にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="dd4ed-109">B2B ユーザーおよびそのアカウントは、条件付きアクセスポリシーに付与されたサービス内で、ファイルと一緒に共有されているリソースにのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-109">B2B users and their accounts only have access to resources that are shared with them (such as files) within the services granted in Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="dd4ed-110">ゲストおよび外部アクセスを許可および保護するための共通ポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="dd4ed-110">Updating the common policies to allow and protect guest and external access</span></span>

<span data-ttu-id="dd4ed-111">Azure AD B2B アカウントを使用してゲストおよび外部アクセスを保護するために、次の図では、共通 id およびデバイスアクセスポリシーで追加または更新するポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-111">To protect guest and external access with Azure AD B2B accounts, the following diagram illustrates which policies to add or update from the the common identity and device access policies.</span></span>

<span data-ttu-id="dd4ed-112">[![ゲストアクセスを保護するためのポリシー更新の概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="dd4ed-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="dd4ed-113">この画像のより大きいバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="dd4ed-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="dd4ed-114">次の表に、作成および更新する必要があるポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="dd4ed-115">共通のポリシーは、 [一般的な id とデバイスアクセスポリシー](identity-access-policies.md) の記事に記載されている関連する構成手順にリンクしています。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="dd4ed-116">保護レベル</span><span class="sxs-lookup"><span data-stu-id="dd4ed-116">Protection level</span></span>|<span data-ttu-id="dd4ed-117">Policies</span><span class="sxs-lookup"><span data-stu-id="dd4ed-117">Policies</span></span>|<span data-ttu-id="dd4ed-118">詳細情報</span><span class="sxs-lookup"><span data-stu-id="dd4ed-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="dd4ed-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="dd4ed-119">**Baseline**</span></span>|[<span data-ttu-id="dd4ed-120">ゲストおよび外部ユーザーに対して MFA を常に要求する</span><span class="sxs-lookup"><span data-stu-id="dd4ed-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="dd4ed-121">この新しいポリシーを作成し、以下を構成します。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-121">Create this new policy and configure:</span></span> <ul><li> <span data-ttu-id="dd4ed-122">**> > ユーザーとグループの割り当て** については、[**ユーザーとグループの選択**] を選択し、[すべての **ゲストおよび外部ユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span> </li><li> <span data-ttu-id="dd4ed-123">**> > の割り当て** については、「多要素認証 (MFA) を常に適用するために、すべてのオプションをオフにしておきます。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li>|
||[<span data-ttu-id="dd4ed-124">サインインリスクが *中* または *高* の場合は MFA を必須にする</span><span class="sxs-lookup"><span data-stu-id="dd4ed-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="dd4ed-125">ゲストユーザーと外部ユーザーを除外するには、このポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-125">Modify this policy to exclude guest and external users.</span></span>|
||[<span data-ttu-id="dd4ed-126">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="dd4ed-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="dd4ed-127">ゲストユーザーと外部ユーザーを除外するには、このポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-127">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="dd4ed-128">条件付きアクセスポリシーにゲストおよび外部ユーザーを含めたり、除外したりするには > 含めるまたは **除外** する **割り当て > ユーザーおよびグループ** の場合は、**すべてのゲストユーザーと外部ユーザー** をチェックします。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-128">To include or exclude guest and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![ゲストおよび外部ユーザーを除外するためのコントロールの画面キャプチャ](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="dd4ed-130">詳細情報</span><span class="sxs-lookup"><span data-stu-id="dd4ed-130">More information</span></span>

### <a name="guest-and-external-access-with-microsoft-teams"></a><span data-ttu-id="dd4ed-131">Microsoft Teams を使用したゲストおよび外部アクセス</span><span class="sxs-lookup"><span data-stu-id="dd4ed-131">Guest and external access with Microsoft Teams</span></span>

<span data-ttu-id="dd4ed-132">Microsoft Teams では、以下を定義します。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-132">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="dd4ed-133">**ゲストアクセス** では、チームのメンバーとして追加でき、すべての権限がチームの通信とリソースにアクセスできる AZURE AD B2B アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have all permissioned access to the communications and resources of the team.</span></span>

- <span data-ttu-id="dd4ed-134">**外部アクセス** は、B2B アカウントを持たない外部ユーザーに対して行われます。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-134">**External access** is for an external user that does not have a B2B account.</span></span> <span data-ttu-id="dd4ed-135">外部アクセスには、通話、チャット、および会議への招待と参加を含めることができますが、チームのメンバーシップやチームのリソースへのアクセスは含まれません。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-135">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="dd4ed-136">詳細については、「 [teams のゲストアクセスと外部アクセスの比較](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-136">For more information, see the [comparison between guest and external access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="dd4ed-137">条件付きアクセスポリシーは、対応する Azure AD B2B アカウントがあるため、Teams でのゲストアクセスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-137">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<span data-ttu-id="dd4ed-138">Teams の id およびデバイスアクセスポリシーの保護の詳細については、「 [teams のチャット、グループ、ファイルを保護するためのポリシーの推奨事項](teams-access-policies.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-138">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access policies for Teams.</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="dd4ed-139">ゲストおよび外部ユーザーに対して MFA を常に要求する</span><span class="sxs-lookup"><span data-stu-id="dd4ed-139">Require MFA always for guest and external users</span></span>

<span data-ttu-id="dd4ed-140">このポリシーにより、ゲストがホームテナントで MFA に登録されているかどうかにかかわらず、テナント内の MFA を登録するように求められます。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-140">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="dd4ed-141">テナント内のリソースにアクセスするとき、ゲストユーザーと外部ユーザーはすべての要求に対して MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-141">When accessing resources in your tenant, guest and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="dd4ed-142">リスクベースの MFA からゲストユーザーと外部ユーザーを除外する</span><span class="sxs-lookup"><span data-stu-id="dd4ed-142">Excluding guest and external users from risk-based MFA</span></span>

<span data-ttu-id="dd4ed-143">組織は、Azure AD Id 保護を使用して B2B ユーザーに対してリスクベースのポリシーを適用できますが、ホームディレクトリに存在する id があるため、リソースディレクトリでの B2B コラボレーションユーザーの Azure AD Id 保護の実装には制限があります。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-143">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="dd4ed-144">これらの制限により、ゲストユーザーをリスクベースの MFA ポリシーから除外し、これらのユーザーが常に MFA を使用するようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-144">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="dd4ed-145">詳細については、「 [B2B コラボレーションユーザーの Id 保護の制限事項](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-145">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="dd4ed-146">デバイス管理からゲストユーザーと外部ユーザーを除外する</span><span class="sxs-lookup"><span data-stu-id="dd4ed-146">Excluding guest and external users from device management</span></span>

<span data-ttu-id="dd4ed-147">1つの組織のみがデバイスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-147">Only one organization can manage a device.</span></span> <span data-ttu-id="dd4ed-148">デバイスコンプライアンスを必要とするポリシーからゲストおよび外部ユーザーを除外しない場合、これらのポリシーによってこれらのユーザーがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-148">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="dd4ed-149">次の手順</span><span class="sxs-lookup"><span data-stu-id="dd4ed-149">Next step</span></span>

![手順 4: Microsoft 365 クラウドアプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="dd4ed-151">次の条件付きアクセスポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="dd4ed-151">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="dd4ed-152">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dd4ed-152">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="dd4ed-153">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dd4ed-153">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="dd4ed-154">SharePoint</span><span class="sxs-lookup"><span data-stu-id="dd4ed-154">SharePoint</span></span>](sharepoint-file-access-policies.md)
