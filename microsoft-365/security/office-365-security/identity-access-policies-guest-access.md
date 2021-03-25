---
title: ゲストユーザーと外部ユーザー B2B アクセスを許可する ID およびデバイス アクセス ポリシー - Microsoft 365 for enterprise |Microsoft Docs
description: ゲストと外部ユーザーのアクセスを保護するための推奨される条件付きアクセスと関連するポリシーについて説明します。
ms.prod: m365-security
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
ms.technology: mdo
ms.openlocfilehash: 9d3a47752efc86c8ced32905bda851b7d8157f82
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205363"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="3b064-103">ゲスト アクセスと B2B 外部ユーザー アクセスを許可するポリシー</span><span class="sxs-lookup"><span data-stu-id="3b064-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="3b064-104">この記事では、Azure Active Directory (Azure AD) Business-to-Business (B2B) アカウントを持つゲストおよび外部ユーザーに対するアクセスを許可するように、推奨されるデバイスと ID アクセス ポリシーを調整する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b064-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="3b064-105">このガイダンスは、共通の [ID ポリシーとデバイス アクセス ポリシーを基にしています](identity-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3b064-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="3b064-106">これらの推奨事項は、ベースラインレベルの保護 **に適用** するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="3b064-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="3b064-107">ただし、機密性が高く規制の厳しい保護に関する特定のニーズに基づいて推奨事項 **を調整** することもできます。</span><span class="sxs-lookup"><span data-stu-id="3b064-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="3b064-108">B2B アカウントが Azure ADテナントで認証するためのパスを提供しても、これらのアカウントは環境全体にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="3b064-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="3b064-109">B2B ユーザーとそのアカウントは、条件付きアクセス ポリシーによって共有されるサービスやリソース (ファイルなど) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3b064-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="3b064-110">ゲストと外部ユーザー アクセスを許可および保護するための一般的なポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="3b064-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="3b064-111">次の図は、B2B ゲスト および外部ユーザー アクセスの共通 ID およびデバイス アクセス ポリシー間で追加または更新するポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="3b064-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="3b064-112">[![ゲスト アクセスを保護するためのポリシー更新プログラムの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="3b064-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

<span data-ttu-id="3b064-113">次の表に、作成および更新する必要があるポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="3b064-113">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="3b064-114">共通ポリシーは、「共通 ID とデバイス アクセス ポリシー」の記事に関連付けられた構成 [手順にリンク](identity-access-policies.md) します。</span><span class="sxs-lookup"><span data-stu-id="3b064-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="3b064-115">保護レベル</span><span class="sxs-lookup"><span data-stu-id="3b064-115">Protection level</span></span>|<span data-ttu-id="3b064-116">ポリシー</span><span class="sxs-lookup"><span data-stu-id="3b064-116">Policies</span></span>|<span data-ttu-id="3b064-117">詳細情報</span><span class="sxs-lookup"><span data-stu-id="3b064-117">More information</span></span>|
|---|---|---|
|<span data-ttu-id="3b064-118">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="3b064-118">**Baseline**</span></span>|[<span data-ttu-id="3b064-119">ゲストと外部ユーザーに対して常に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="3b064-119">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="3b064-120">この新しいポリシーを作成し、次の構成を行います。</span><span class="sxs-lookup"><span data-stu-id="3b064-120">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="3b064-121">[**割り>ユーザー** とグループ>含める] で、[ユーザーとグループの選択] を選択し、[すべてのゲストユーザーと外部ユーザー **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="3b064-121">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="3b064-122">[ **割り>条件**>サインイン] で、多要素認証 (MFA) を常に適用するには、すべてのオプションをオフのままにします。</span><span class="sxs-lookup"><span data-stu-id="3b064-122">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="3b064-123">サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*</span><span class="sxs-lookup"><span data-stu-id="3b064-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="3b064-124">ゲストと外部ユーザーを除外するには、このポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="3b064-124">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="3b064-125">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="3b064-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="3b064-126">ゲストと外部ユーザーを除外するには、このポリシーを変更します。</span><span class="sxs-lookup"><span data-stu-id="3b064-126">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="3b064-127">条件付きアクセス ポリシーにゲストと外部ユーザーを含めるか除外するには、[割り当て] > [ユーザーとグループ] > [含める] または **[** 除外] で、[すべてのゲストユーザーと外部ユーザー] をチェック **します**。</span><span class="sxs-lookup"><span data-stu-id="3b064-127">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![ゲストと外部ユーザーを除外するコントロールの画面キャプチャ](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="3b064-129">詳細情報</span><span class="sxs-lookup"><span data-stu-id="3b064-129">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="3b064-130">Microsoft Teams を使用したゲストと外部ユーザー アクセス</span><span class="sxs-lookup"><span data-stu-id="3b064-130">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="3b064-131">Microsoft Teams では、次のユーザーを定義します。</span><span class="sxs-lookup"><span data-stu-id="3b064-131">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="3b064-132">**ゲスト アクセス** では、Azure AD B2B アカウントを使用し、チームのメンバーとして追加し、チームの通信とリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3b064-132">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="3b064-133">**外部アクセス** は、B2B アカウントを持つ外部ユーザー用です。</span><span class="sxs-lookup"><span data-stu-id="3b064-133">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="3b064-134">外部ユーザー アクセスには、招待、通話、チャット、会議が含まれますが、チーム メンバーシップとチームのリソースへのアクセスは含まれます。</span><span class="sxs-lookup"><span data-stu-id="3b064-134">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="3b064-135">詳細については、「チームのゲストと外部ユーザー アクセスの [比較」を参照してください](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)。</span><span class="sxs-lookup"><span data-stu-id="3b064-135">For more information, see the [comparison between guests and external user access for teams](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="3b064-136">Teams の ID とデバイス アクセス ポリシーのセキュリティ保護の詳細については、「Teams のチャット、グループ、およびファイルをセキュリティ保護するためのポリシーの推奨事項」を [参照してください](teams-access-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3b064-136">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="3b064-137">ゲストユーザーと外部ユーザーに対して常に MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="3b064-137">Require MFA always for guest and external users</span></span>

<span data-ttu-id="3b064-138">このポリシーは、ゲストがホーム テナントで MFA に登録されているかどうかに関係なく、テナントに MFA を登録するように求めるプロンプトを表示します。</span><span class="sxs-lookup"><span data-stu-id="3b064-138">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="3b064-139">テナント内のリソースにアクセスする場合、ゲストと外部ユーザーは要求ごとに MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b064-139">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="3b064-140">ゲストと外部ユーザーをリスクベースの MFA から除外する</span><span class="sxs-lookup"><span data-stu-id="3b064-140">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="3b064-141">組織は Azure AD Identity Protection を使用して B2B ユーザーにリスクベースのポリシーを適用することができますが、Azure AD Identity Protection for B2B コラボレーション ユーザーのホーム ディレクトリに存在する ID が原因で、リソース ディレクトリに実装する場合に制限があります。</span><span class="sxs-lookup"><span data-stu-id="3b064-141">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="3b064-142">これらの制限により、リスクベースの MFA ポリシーからゲストを除外し、常に MFA を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b064-142">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="3b064-143">詳細については [、「B2B コラボレーション ユーザーの Id 保護の制限」を参照してください](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)。</span><span class="sxs-lookup"><span data-stu-id="3b064-143">For more information, see [Limitations of Identity Protection for B2B collaboration users](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="3b064-144">ゲストと外部ユーザーをデバイス管理から除外する</span><span class="sxs-lookup"><span data-stu-id="3b064-144">Excluding guests and external users from device management</span></span>

<span data-ttu-id="3b064-145">デバイスを管理できるのは 1 つの組織のみです。</span><span class="sxs-lookup"><span data-stu-id="3b064-145">Only one organization can manage a device.</span></span> <span data-ttu-id="3b064-146">ゲストと外部ユーザーをデバイスコンプライアンスを必要とするポリシーから除外しない場合、これらのポリシーはこれらのユーザーをブロックします。</span><span class="sxs-lookup"><span data-stu-id="3b064-146">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="3b064-147">次の手順</span><span class="sxs-lookup"><span data-stu-id="3b064-147">Next step</span></span>

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="3b064-149">次の条件付きアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3b064-149">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="3b064-150">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3b064-150">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="3b064-151">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3b064-151">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="3b064-152">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3b064-152">SharePoint</span></span>](sharepoint-file-access-policies.md)