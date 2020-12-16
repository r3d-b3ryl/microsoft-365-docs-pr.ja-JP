---
title: ゲストと外部の B2B アクセスを許可する ID とデバイスのアクセス ポリシー - Microsoft 365 for enterprise |Microsoft Docs
description: ゲストユーザーと外部ユーザーのアクセスを保護するための、推奨される条件付きアクセスと関連するポリシーについて説明します。
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
ms.openlocfilehash: 376845d8e3657b91b9efe0357e94f4bec3a84078
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688287"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="47faa-103">ゲストと外部の B2B アクセスを許可するポリシー</span><span class="sxs-lookup"><span data-stu-id="47faa-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="47faa-104">この記事では、Azure Active Directory (Azure AD) Business-to-Business (B2B) アカウントを持つゲストユーザーと外部ユーザーにアクセスを許可するように、推奨される共通 ID およびデバイス アクセス ポリシーを調整する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="47faa-104">This article describes how to adjust the recommended common identity and device access policies to allow access for guest and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="47faa-105">このガイダンスは、共通の [ID ポリシーとデバイス アクセス ポリシーに基っています](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="47faa-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="47faa-106">これらの推奨事項は、保護のベースライン層 **に** 適用するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="47faa-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="47faa-107">ただし、機密性の高い厳しく規制された保護のニーズの粒度に基づいて推奨事項 **を調整** することもできます。</span><span class="sxs-lookup"><span data-stu-id="47faa-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="47faa-108">Azure AD テナントで認証する B2B アカウントのパスを指定しても、これらのアカウントは環境全体にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="47faa-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="47faa-109">B2B ユーザーとそのアカウントは、条件付きアクセス ポリシーで付与されたサービス内で共有されているリソース (ファイルなど) にのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="47faa-109">B2B users and their accounts only have access to resources that are shared with them (such as files) within the services granted in Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="47faa-110">ゲストアクセスと外部アクセスを許可および保護するための共通ポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="47faa-110">Updating the common policies to allow and protect guest and external access</span></span>

<span data-ttu-id="47faa-111">Azure AD B2B アカウントを使用してゲストおよび外部アクセスを保護するために、次の図は、共通の ID およびデバイス アクセス ポリシーに対して追加または更新するポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="47faa-111">To protect guest and external access with Azure AD B2B accounts, the following diagram illustrates which policies to add or update from the the common identity and device access policies.</span></span>

<span data-ttu-id="47faa-112">[![ゲスト アクセスを保護するためのポリシー更新プログラムの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="47faa-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="47faa-113">このイメージのより大きなバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="47faa-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="47faa-114">次の表に、作成および更新する必要があるポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="47faa-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="47faa-115">共通ポリシーは、共通 ID とデバイス アクセス ポリシーに関する記事に関連する構成手順 [にリンク](identity-access-policies.md) しています。</span><span class="sxs-lookup"><span data-stu-id="47faa-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="47faa-116">保護レベル</span><span class="sxs-lookup"><span data-stu-id="47faa-116">Protection level</span></span>|<span data-ttu-id="47faa-117">Policies</span><span class="sxs-lookup"><span data-stu-id="47faa-117">Policies</span></span>|<span data-ttu-id="47faa-118">詳細情報</span><span class="sxs-lookup"><span data-stu-id="47faa-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="47faa-119">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="47faa-119">**Baseline**</span></span>|[<span data-ttu-id="47faa-120">ゲストユーザーと外部ユーザーに対して常に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="47faa-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="47faa-121">この新しいポリシーを作成し、次の構成を行います。</span><span class="sxs-lookup"><span data-stu-id="47faa-121">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="47faa-122">[ **Assignments > Users and groups > Include**] で、[ **ユーザー** とグループの選択] を選択し、[ All guest and external users ] (すべてのゲスト ユーザーと外部ユーザー **) を選択します**。</span><span class="sxs-lookup"><span data-stu-id="47faa-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="47faa-123">**[Assignments > Conditions > サインイン**] では、すべてのオプションをオフのままにして、常に多要素認証 (MFA) を適用します。</span><span class="sxs-lookup"><span data-stu-id="47faa-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="47faa-124">サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*</span><span class="sxs-lookup"><span data-stu-id="47faa-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="47faa-125">ゲスト ユーザーと外部ユーザーを除外するには、このポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="47faa-125">Modify this policy to exclude guest and external users.</span></span>|
||[<span data-ttu-id="47faa-126">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="47faa-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="47faa-127">ゲスト ユーザーと外部ユーザーを除外するには、このポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="47faa-127">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="47faa-128">条件付きアクセス ポリシーにゲスト ユーザーと外部ユーザーを含める、または除外するには、[割り当て] >  **[** ユーザーとグループ] > [含める] または [除外] を選択し、[すべてのゲスト ユーザーと外部ユーザー] をオン **にしてください**。</span><span class="sxs-lookup"><span data-stu-id="47faa-128">To include or exclude guest and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![ゲストユーザーと外部ユーザーを除外するコントロールの画面キャプチャ](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="47faa-130">詳細情報</span><span class="sxs-lookup"><span data-stu-id="47faa-130">More information</span></span>

### <a name="guest-and-external-access-with-microsoft-teams"></a><span data-ttu-id="47faa-131">Microsoft Teams を使用したゲストおよび外部アクセス</span><span class="sxs-lookup"><span data-stu-id="47faa-131">Guest and external access with Microsoft Teams</span></span>

<span data-ttu-id="47faa-132">Microsoft Teams では、次の定義を行います。</span><span class="sxs-lookup"><span data-stu-id="47faa-132">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="47faa-133">**ゲスト アクセス** では、Azure AD B2B アカウントを使用します。このアカウントは、チームのメンバーとして追加され、チームの通信とリソースへのアクセス許可を持つすべてのアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="47faa-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have all permissioned access to the communications and resources of the team.</span></span>

- <span data-ttu-id="47faa-134">**外部アクセス** は、B2B アカウントを持つ外部ユーザー用です。</span><span class="sxs-lookup"><span data-stu-id="47faa-134">**External access** is for an external user that does not have a B2B account.</span></span> <span data-ttu-id="47faa-135">外部アクセスには、招待と通話、チャット、会議への参加を含めできますが、チーム メンバーシップとチームのリソースへのアクセスは含め込めではありません。</span><span class="sxs-lookup"><span data-stu-id="47faa-135">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="47faa-136">詳細については、チームのゲスト [アクセスと外部アクセスの比較を参照してください](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="47faa-136">For more information, see the [comparison between guest and external access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="47faa-137">Teams [の ID とデバイス アクセス](teams-access-policies.md) ポリシーのセキュリティ保護の詳細については、Teams のチャット、グループ、ファイルをセキュリティ保護するためのポリシーの推奨事項を参照してください。</span><span class="sxs-lookup"><span data-stu-id="47faa-137">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access policies for Teams.</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="47faa-138">ゲストユーザーと外部ユーザーに対して常に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="47faa-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="47faa-139">このポリシーは、ゲストがホーム テナントで MFA に登録されているかどうかに関係なく、テナントで MFA を登録するように求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="47faa-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="47faa-140">テナント内のリソースにアクセスする場合、ゲスト ユーザーと外部ユーザーは要求ごとに MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47faa-140">When accessing resources in your tenant, guest and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="47faa-141">ゲストユーザーと外部ユーザーをリスクベースの MFA から除外する</span><span class="sxs-lookup"><span data-stu-id="47faa-141">Excluding guest and external users from risk-based MFA</span></span>

<span data-ttu-id="47faa-142">組織は Azure AD Identity Protection を使用して B2B ユーザーにリスクベースのポリシーを適用することができますが、ホーム ディレクトリに存在する ID のため、リソース ディレクトリに B2B コラボレーション ユーザー用の Azure AD Identity Protection を実装する場合には制限があります。</span><span class="sxs-lookup"><span data-stu-id="47faa-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="47faa-143">これらの制限により、Microsoft ではゲスト ユーザーをリスクベースの MFA ポリシーから除外し、常に MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="47faa-143">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="47faa-144">詳細については [、「B2B コラボレーション ユーザーの Id 保護の制限事項」を参照してください](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。</span><span class="sxs-lookup"><span data-stu-id="47faa-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="47faa-145">ゲスト ユーザーと外部ユーザーをデバイス管理から除外する</span><span class="sxs-lookup"><span data-stu-id="47faa-145">Excluding guest and external users from device management</span></span>

<span data-ttu-id="47faa-146">デバイスを管理できるのは 1 つの組織のみです。</span><span class="sxs-lookup"><span data-stu-id="47faa-146">Only one organization can manage a device.</span></span> <span data-ttu-id="47faa-147">デバイスの準拠を必要とするポリシーからゲスト ユーザーと外部ユーザーを除外しない場合、これらのポリシーによってこれらのユーザーがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="47faa-147">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="47faa-148">次の手順</span><span class="sxs-lookup"><span data-stu-id="47faa-148">Next step</span></span>

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="47faa-150">次の条件に合ったアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="47faa-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="47faa-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47faa-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="47faa-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="47faa-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="47faa-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="47faa-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
