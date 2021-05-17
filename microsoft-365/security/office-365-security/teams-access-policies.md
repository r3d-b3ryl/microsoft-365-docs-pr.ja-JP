---
title: 推奨Teamsポリシー - エンタープライズ Microsoft 365の|Microsoft Docs
description: 通信とファイル アクセスをセキュリティで保護する方法に関する Microsoft Teamsについて説明します。
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.author: heidip
ms.date: 09/30/2020
ms.reviewer: anmorgan
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 52e6709d18bd5ecbc91755a6c0e7be336d346f0c
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599605"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a><span data-ttu-id="22e5a-103">チャット、グループ、ファイルTeamsセキュリティ保護に関するポリシーの推奨事項</span><span class="sxs-lookup"><span data-stu-id="22e5a-103">Policy recommendations for securing Teams chats, groups, and files</span></span>

<span data-ttu-id="22e5a-104">この記事では、推奨される ID ポリシーとデバイス アクセス ポリシーを実装して、Microsoft Teams チャット、グループ、およびファイルや予定表などのコンテンツを保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="22e5a-104">This article describes how to implement the recommended identity and device-access policies to protect Microsoft Teams chats, groups, and content such as files and calendars.</span></span> <span data-ttu-id="22e5a-105">このガイダンスは、一般的な[ID](identity-access-policies.md)とデバイス アクセス ポリシーに基Teamsです。</span><span class="sxs-lookup"><span data-stu-id="22e5a-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md), with additional information that's Teams-specific.</span></span> <span data-ttu-id="22e5a-106">このTeams他の製品と統合される場合は、「セキュリティ保護に関[](sharepoint-file-access-policies.md)するポリシー SharePoint、電子メールのセキュリティ保護に関するポリシーの推奨事項」も[参照してください](secure-email-recommended-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="22e5a-106">Because Teams integrates with our other products, also see [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md) and [Policy recommendations for securing email](secure-email-recommended-policies.md).</span></span>

<span data-ttu-id="22e5a-107">これらの推奨事項は、ニーズの細分性に基づいて適用できる Teams のセキュリティと保護の 3 つの層に基づいて行います。ベースライン、機密性の高い、高度に規制されています。</span><span class="sxs-lookup"><span data-stu-id="22e5a-107">These recommendations are based on three different tiers of security and protection for Teams that can be applied based on the granularity of your needs: baseline, sensitive, and highly regulated.</span></span> <span data-ttu-id="22e5a-108">これらのセキュリティ層と、これらの推奨事項で参照される推奨ポリシーの詳細については、「Identity and [device access configurations」を参照してください](microsoft-365-policies-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="22e5a-108">You can learn more about these security tiers and the recommended policies referenced by these recommendations in the [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="22e5a-109">組織外のユーザーをTeams、特定の認証の状況をカバーするために、この記事では、展開に固有の推奨事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="22e5a-109">More recommendations specific to Teams deployment are included in this article to cover specific authentication circumstances, including for users outside your organization.</span></span> <span data-ttu-id="22e5a-110">完全なセキュリティ エクスペリエンスを提供するには、このガイダンスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e5a-110">You will need to follow this guidance for a complete security experience.</span></span>

## <a name="getting-started-with-teams-before-other-dependent-services"></a><span data-ttu-id="22e5a-111">他の依存サービスのTeamsの開始方法</span><span class="sxs-lookup"><span data-stu-id="22e5a-111">Getting started with Teams before other dependent services</span></span>

<span data-ttu-id="22e5a-112">依存サービスを有効にして、サービスを開始する必要Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="22e5a-112">You don't need to enable dependent services to get started with Microsoft Teams.</span></span> <span data-ttu-id="22e5a-113">これらのサービスはすべて "単なる動作" になります。</span><span class="sxs-lookup"><span data-stu-id="22e5a-113">These services will all "just work."</span></span> <span data-ttu-id="22e5a-114">ただし、次のサービス関連の要素を管理するために準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e5a-114">However, you do need to be prepared to manage the following service-related elements:</span></span>

- <span data-ttu-id="22e5a-115">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="22e5a-115">Microsoft 365 groups</span></span>
- <span data-ttu-id="22e5a-116">SharePoint チーム サイト</span><span class="sxs-lookup"><span data-stu-id="22e5a-116">SharePoint team sites</span></span>
- <span data-ttu-id="22e5a-117">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="22e5a-117">OneDrive for Business</span></span>
- <span data-ttu-id="22e5a-118">Exchange メールボックス</span><span class="sxs-lookup"><span data-stu-id="22e5a-118">Exchange mailboxes</span></span>
- <span data-ttu-id="22e5a-119">ビデオと Planner プランのストリーミング (これらのサービスが有効な場合)</span><span class="sxs-lookup"><span data-stu-id="22e5a-119">Stream videos and Planner plans (if these services are enabled)</span></span>

## <a name="updating-common-policies-to-include-teams"></a><span data-ttu-id="22e5a-120">一般的なポリシーを更新してポリシーを含Teams</span><span class="sxs-lookup"><span data-stu-id="22e5a-120">Updating common policies to include Teams</span></span>

<span data-ttu-id="22e5a-121">チャット、グループ、およびコンテンツを保護するために、Teamsの ID ポリシーとデバイス アクセス ポリシーから更新するポリシーを次の図に示します。</span><span class="sxs-lookup"><span data-stu-id="22e5a-121">To protect chat, groups and content in Teams, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span> <span data-ttu-id="22e5a-122">更新するポリシーごとに、クラウド アプリの割りTeamsサービスと依存サービスが含まれているか確認します。</span><span class="sxs-lookup"><span data-stu-id="22e5a-122">For each policy to update, make sure that Teams and dependent services are included in the assignment of cloud apps.</span></span>

<span data-ttu-id="22e5a-123">[![サービスとその依存サービスへのアクセスを保護するためのTeamsの概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span><span class="sxs-lookup"><span data-stu-id="22e5a-123">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span></span>

<span data-ttu-id="22e5a-124">これらのサービスは、クラウド アプリの割り当てに含める依存サービスTeams。</span><span class="sxs-lookup"><span data-stu-id="22e5a-124">These services are the dependent services to include in the assignment of cloud apps for Teams:</span></span>

- <span data-ttu-id="22e5a-125">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22e5a-125">Microsoft Teams</span></span>
- <span data-ttu-id="22e5a-126">SharePoint および OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="22e5a-126">SharePoint and OneDrive for Business</span></span>
- <span data-ttu-id="22e5a-127">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="22e5a-127">Exchange Online</span></span>
- <span data-ttu-id="22e5a-128">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="22e5a-128">Skype for Business Online</span></span>
- <span data-ttu-id="22e5a-129">Microsoft Stream (会議の記録)</span><span class="sxs-lookup"><span data-stu-id="22e5a-129">Microsoft Stream (meeting recordings)</span></span>
- <span data-ttu-id="22e5a-130">Microsoft Planner (Planner タスクと計画データ)</span><span class="sxs-lookup"><span data-stu-id="22e5a-130">Microsoft Planner (Planner tasks and plan data)</span></span>

<span data-ttu-id="22e5a-131">次の表に、再訪する必要があるポリシーと、共通 ID およびデバイス[](identity-access-policies.md)アクセス ポリシー内の各ポリシーへのリンクを示します。これは、すべての Office アプリケーションに対してより広いポリシーが設定されています。</span><span class="sxs-lookup"><span data-stu-id="22e5a-131">This table lists the policies that need to be revisited and links to each policy in the [common identity and device access policies](identity-access-policies.md), which has the wider policy set for all Office applications.</span></span>

|<span data-ttu-id="22e5a-132">保護レベル</span><span class="sxs-lookup"><span data-stu-id="22e5a-132">Protection level</span></span>|<span data-ttu-id="22e5a-133">ポリシー</span><span class="sxs-lookup"><span data-stu-id="22e5a-133">Policies</span></span>|<span data-ttu-id="22e5a-134">実装に関するTeams情報</span><span class="sxs-lookup"><span data-stu-id="22e5a-134">Further information for Teams implementation</span></span>|
|---|---|---|
|<span data-ttu-id="22e5a-135">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="22e5a-135">**Baseline**</span></span>|[<span data-ttu-id="22e5a-136">サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*</span><span class="sxs-lookup"><span data-stu-id="22e5a-136">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="22e5a-137">アプリのTeamsにサービスと依存サービスが含まれているか確認してください。</span><span class="sxs-lookup"><span data-stu-id="22e5a-137">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="22e5a-138">Teamsゲスト アクセスルールと外部アクセス ルールも考慮する必要がある場合は、この記事の後半でこれらのルールの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="22e5a-138">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these rules later in this article.</span></span>|
||[<span data-ttu-id="22e5a-139">先進認証をサポートしないクライアントはブロックする</span><span class="sxs-lookup"><span data-stu-id="22e5a-139">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="22e5a-140">クラウド Teams割り当てには、サービスと依存サービスを含める。</span><span class="sxs-lookup"><span data-stu-id="22e5a-140">Include Teams and dependent services in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="22e5a-141">高リスク ユーザーはパスワードを変更する必要がある</span><span class="sxs-lookup"><span data-stu-id="22e5a-141">High risk users must change password</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="22e5a-142">アカウントTeamsリスクの高いアクティビティが検出された場合、サインイン時にユーザーにパスワードの変更を強制的に行います。</span><span class="sxs-lookup"><span data-stu-id="22e5a-142">Forces Teams users to change their password when signing in if high-risk activity is detected for their account.</span></span> <span data-ttu-id="22e5a-143">アプリのTeamsにサービスと依存サービスが含まれているか確認してください。</span><span class="sxs-lookup"><span data-stu-id="22e5a-143">Be sure Teams and dependent services are included in the list of apps.</span></span>|
||[<span data-ttu-id="22e5a-144">APP データ保護ポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="22e5a-144">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="22e5a-145">アプリのTeamsにサービスと依存サービスが含まれているか確認してください。</span><span class="sxs-lookup"><span data-stu-id="22e5a-145">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="22e5a-146">各プラットフォームのポリシーを更新します (iOS、Android、Windows)。</span><span class="sxs-lookup"><span data-stu-id="22e5a-146">Update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="22e5a-147">デバイス コンプライアンス ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="22e5a-147">Define device compliance policies</span></span>](identity-access-policies.md#define-device-compliance-policies)|<span data-ttu-id="22e5a-148">このポリシー Teamsサービスと依存サービスを含める。</span><span class="sxs-lookup"><span data-stu-id="22e5a-148">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="22e5a-149">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="22e5a-149">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="22e5a-150">このポリシー Teamsサービスと依存サービスを含める。</span><span class="sxs-lookup"><span data-stu-id="22e5a-150">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="22e5a-151">**機密**</span><span class="sxs-lookup"><span data-stu-id="22e5a-151">**Sensitive**</span></span>|[<span data-ttu-id="22e5a-152">サインイン リスクが低い、中程度、または高い場合に MFA *を* 要求 *する*</span><span class="sxs-lookup"><span data-stu-id="22e5a-152">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="22e5a-153">Teamsゲスト アクセスルールと外部アクセス ルールも考慮する必要がある場合は、この記事の後半でこれらのルールの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="22e5a-153">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these rules later in this article.</span></span> <span data-ttu-id="22e5a-154">このポリシー Teamsサービスと依存サービスを含める。</span><span class="sxs-lookup"><span data-stu-id="22e5a-154">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="22e5a-155">準拠している PC とモバイル *デバイスを* 要求する</span><span class="sxs-lookup"><span data-stu-id="22e5a-155">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="22e5a-156">このポリシー Teamsサービスと依存サービスを含める。</span><span class="sxs-lookup"><span data-stu-id="22e5a-156">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="22e5a-157">**厳しく規制**</span><span class="sxs-lookup"><span data-stu-id="22e5a-157">**Highly regulated**</span></span>|[<span data-ttu-id="22e5a-158">*常に* MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="22e5a-158">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="22e5a-159">ユーザー ID に関係なく、MFA は組織で使用されます。</span><span class="sxs-lookup"><span data-stu-id="22e5a-159">Regardless of user identity, MFA will be used by your organization.</span></span> <span data-ttu-id="22e5a-160">このポリシー Teamsサービスと依存サービスを含める。</span><span class="sxs-lookup"><span data-stu-id="22e5a-160">Include Teams and dependent services in this policy.</span></span> |
|

## <a name="teams-dependent-services-architecture"></a><span data-ttu-id="22e5a-161">Teamsサービスアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="22e5a-161">Teams dependent services architecture</span></span>

<span data-ttu-id="22e5a-162">参考までに、次の図は、ユーザーがTeamsを示しています。</span><span class="sxs-lookup"><span data-stu-id="22e5a-162">For reference, the following diagram illustrates the services Teams relies on.</span></span> <span data-ttu-id="22e5a-163">詳細と図については、「it アーキテクト向けMicrosoft Teamsの生産性サービス[と関連Microsoft 365を参照してください](../../solutions/productivity-illustrations.md)。</span><span class="sxs-lookup"><span data-stu-id="22e5a-163">For more information and illustrations, see [Microsoft Teams and related productivity services in Microsoft 365 for IT architects](../../solutions/productivity-illustrations.md).</span></span>

<span data-ttu-id="22e5a-164">[![ユーザー、Teams、およびSharePointのOneDrive for Businessを示す図Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span><span class="sxs-lookup"><span data-stu-id="22e5a-164">[![Diagram showing Teams dependencies on SharePoint, OneDrive for Business, and Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span></span>

[<span data-ttu-id="22e5a-165">このイメージのより大きなバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="22e5a-165">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a><span data-ttu-id="22e5a-166">ユーザーのゲストおよび外部アクセスTeams</span><span class="sxs-lookup"><span data-stu-id="22e5a-166">Guest and external access for Teams</span></span>

<span data-ttu-id="22e5a-167">Microsoft Teamsアクセスの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="22e5a-167">Microsoft Teams defines the following access types:</span></span>

- <span data-ttu-id="22e5a-168">ゲスト **アクセス** は、チームのメンバーとして追加できるゲストまたは外部ユーザーに対して Azure AD B2B アカウントを使用し、チームの通信とリソースへのすべてのアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="22e5a-168">**Guest access** uses an Azure AD B2B account for a guest or external user that can be added as a member of a team and have all permissioned access to the communication and resources of the team.</span></span>

- <span data-ttu-id="22e5a-169">**外部アクセス** は、Azure アカウント B2B アカウントを持ADユーザー用です。</span><span class="sxs-lookup"><span data-stu-id="22e5a-169">**External access** is for an external user that does not have an Azure AD B2B account.</span></span> <span data-ttu-id="22e5a-170">外部アクセスには、招待と通話、チャット、会議への参加を含めできますが、チーム メンバーシップとチームのリソースへのアクセスは含めではありません。</span><span class="sxs-lookup"><span data-stu-id="22e5a-170">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="22e5a-171">条件付きアクセス ポリシーは、対応する Azure Teams B2B アカウントが存在ADゲスト アクセスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="22e5a-171">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

<span data-ttu-id="22e5a-172">Azure AD B2B アカウントを持つゲストユーザーと外部ユーザーのアクセスを許可する推奨ポリシーについては、「ゲストアカウントと外部 [B2B](identity-access-policies-guest-access.md)アカウントアクセスを許可するポリシー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="22e5a-172">For recommended policies to allow access for guest and external users with an Azure AD B2B account, see [Policies for allowing guest and external B2B account access](identity-access-policies-guest-access.md).</span></span>

### <a name="guest-access-in-teams"></a><span data-ttu-id="22e5a-173">Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="22e5a-173">Guest access in Teams</span></span>

<span data-ttu-id="22e5a-174">管理者は、ビジネスや組織の内部に所属するユーザーのポリシーに加えて、ビジネスや組織の外部のユーザーが Teams リソースにアクセスしたり、グループの会話、チャット、会議などについて内部のユーザーとやり取りしたりするためのゲスト アクセスをユーザー単位で許可できます。</span><span class="sxs-lookup"><span data-stu-id="22e5a-174">In addition to the policies for users who are internal to your business or organization, administrators may enable guest access to allow, on a user-by-user basis, people who are external to your business or organization to access Teams resources and interact with internal people for things like group conversations, chat, and meetings.</span></span>

<span data-ttu-id="22e5a-175">ゲスト アクセスとそれを実装する方法の詳細については、「ゲスト アクセスのTeams[を参照してください](/microsoftteams/guest-access)。</span><span class="sxs-lookup"><span data-stu-id="22e5a-175">For more information about guest access and how to implement it, see  [Teams guest access](/microsoftteams/guest-access).</span></span>

### <a name="external-access-in-teams"></a><span data-ttu-id="22e5a-176">外部アクセス (Teams</span><span class="sxs-lookup"><span data-stu-id="22e5a-176">External access in Teams</span></span>

<span data-ttu-id="22e5a-177">外部アクセスはゲスト アクセスと混同される場合があります。そのため、これら 2 つの内部以外のアクセス メカニズムが異なる種類のアクセスである点を明確にすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="22e5a-177">External access is sometimes confused with guest access, so it's important to be clear that these two non-internal access mechanisms are different types of access.</span></span>

<span data-ttu-id="22e5a-178">外部アクセスは、外部ドメインTeamsユーザーが会議を検索、呼び出し、チャット、および会議のセットアップを行う方法Teams。</span><span class="sxs-lookup"><span data-stu-id="22e5a-178">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with your users in Teams.</span></span> <span data-ttu-id="22e5a-179">Teams管理者は、組織レベルで外部アクセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="22e5a-179">Teams administrators configure external access at the organization level.</span></span> <span data-ttu-id="22e5a-180">詳細については、「外部アクセスを[管理する」を参照Microsoft Teams。](/microsoftteams/manage-external-access)</span><span class="sxs-lookup"><span data-stu-id="22e5a-180">For more information, see [Manage external access in Microsoft Teams](/microsoftteams/manage-external-access).</span></span>

<span data-ttu-id="22e5a-181">外部アクセス ユーザーは、ゲスト アクセスを介して追加された個人よりもアクセスと機能が少ない。</span><span class="sxs-lookup"><span data-stu-id="22e5a-181">External access users have less access and functionality than an individual who's been added via guest access.</span></span> <span data-ttu-id="22e5a-182">たとえば、外部アクセス ユーザーは内部ユーザーとチャットできますが、Teams、ファイル、その他のリソースにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="22e5a-182">For example, external access users can chat with your internal users with Teams but cannot access team channels, files, or other resources.</span></span>

<span data-ttu-id="22e5a-183">外部アクセスでは、Azure AD B2B ユーザー アカウントは使用されないので、条件付きアクセス ポリシーは使用できません。</span><span class="sxs-lookup"><span data-stu-id="22e5a-183">External access does not use Azure AD B2B user accounts and therefore does not use Conditional Access policies.</span></span>

## <a name="teams-policies"></a><span data-ttu-id="22e5a-184">Teams ポリシー</span><span class="sxs-lookup"><span data-stu-id="22e5a-184">Teams policies</span></span>

<span data-ttu-id="22e5a-185">上記の一般的なポリシーの外部には、Teams機能を管理するために構成できるポリシーと構成する必要があるTeamsがあります。</span><span class="sxs-lookup"><span data-stu-id="22e5a-185">Outside of the common policies listed above, there are Teams-specific policies that can and should be configured to manage various Teams functionalities.</span></span>

### <a name="teams-and-channels-policies"></a><span data-ttu-id="22e5a-186">Teamsチャネル ポリシー</span><span class="sxs-lookup"><span data-stu-id="22e5a-186">Teams and channels policies</span></span>

<span data-ttu-id="22e5a-187">Teamsチャネルは Microsoft Teams でよく使用される 2 つの要素であり、チームとチャネルを使用するときにユーザーが実行できる操作とできない操作を制御するポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="22e5a-187">Teams and channels are two commonly used elements in Microsoft Teams, and there are policies you can put in place to control what users can and cannot do when using teams and channels.</span></span> <span data-ttu-id="22e5a-188">グローバル チームを作成することもできますが、組織のユーザー数が 5,000 人以下の場合は、組織のニーズに合った、特定の目的で小規模なチームとチャネルを持つ方が役立つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22e5a-188">While you can create a global team, if your organization has 5000 users or less, you are likely to find it helpful to have smaller teams and channels for specific purposes, in-line with your organizational needs.</span></span>

<span data-ttu-id="22e5a-189">既定のポリシーを変更するか、カスタム ポリシーを作成する方法をお勧めします。ポリシーの管理の詳細については、「Microsoft Teams で teams ポリシーを管理する」[を参照してください](/microsoftteams/teams-policies)。</span><span class="sxs-lookup"><span data-stu-id="22e5a-189">Changing the default policy or creating custom policies would be recommended, and you can learn more about managing your policies at this link: [Manage teams policies in Microsoft Teams](/microsoftteams/teams-policies).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="22e5a-190">メッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="22e5a-190">Messaging policies</span></span>

<span data-ttu-id="22e5a-191">メッセージング (チャット) は、既定のグローバル ポリシーまたはカスタム ポリシーを使用して管理することもできます。これにより、ユーザーは組織に適した方法で相互に通信できます。</span><span class="sxs-lookup"><span data-stu-id="22e5a-191">Messaging, or chat, can also be managed through the default global policy, or through custom policies, and this can help your users communicate with one another in a way that's appropriate for your organization.</span></span> <span data-ttu-id="22e5a-192">この情報は、「メッセージング ポリシーの[管理」](/microsoftteams/messaging-policies-in-teams)で確認Teams。</span><span class="sxs-lookup"><span data-stu-id="22e5a-192">This information can be reviewed at [Managing messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="22e5a-193">ミーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="22e5a-193">Meeting policies</span></span>

<span data-ttu-id="22e5a-194">会議に関Teamsポリシーを計画して実装しない場合、この問題に関するTeamsはありません。</span><span class="sxs-lookup"><span data-stu-id="22e5a-194">No discussion of Teams would be complete without planning and implementing policies around Teams meetings.</span></span> <span data-ttu-id="22e5a-195">会議は、Teamsの重要なコンポーネントであり、ユーザーは一度に多くのユーザーと正式に会って提示し、会議に関連するコンテンツを共有できます。</span><span class="sxs-lookup"><span data-stu-id="22e5a-195">Meetings are an essential component of Teams, allowing people to formally meet and present to many users at once, and to share content relevant to the meeting.</span></span> <span data-ttu-id="22e5a-196">会議に関する組織に適切なポリシーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="22e5a-196">Setting the right policies for your organization around meetings is essential.</span></span>

<span data-ttu-id="22e5a-197">詳細については、「会議ポリシーの[管理」を参照Teams。](/microsoftteams/meeting-policies-in-teams)</span><span class="sxs-lookup"><span data-stu-id="22e5a-197">For more information, review [Manage meeting policies in Teams](/microsoftteams/meeting-policies-in-teams).</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="22e5a-198">アプリのアクセス許可ポリシー</span><span class="sxs-lookup"><span data-stu-id="22e5a-198">App permission policies</span></span>

<span data-ttu-id="22e5a-199">Teamsチャネルや個人用チャットなど、さまざまな場所でアプリを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="22e5a-199">Teams also allows you to use apps in various places, such as channels or personal chats.</span></span> <span data-ttu-id="22e5a-200">どのアプリを追加して使用できるのか、どこで使用できるのかというポリシーを持つことは、セキュリティで保護されたコンテンツ豊富な環境を維持するために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="22e5a-200">Having policies around what apps can be added and used, and where, is essential to maintaining a content-rich environment that is also secure.</span></span>

<span data-ttu-id="22e5a-201">アプリのアクセス許可ポリシーの詳細については、「アプリのアクセス許可ポリシーを管理する」を参照[Microsoft Teams。](/microsoftteams/teams-app-permission-policies)</span><span class="sxs-lookup"><span data-stu-id="22e5a-201">For more reading about App Permission Policies, check out [Manage app permission policies in Microsoft Teams](/microsoftteams/teams-app-permission-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="22e5a-202">次の手順</span><span class="sxs-lookup"><span data-stu-id="22e5a-202">Next steps</span></span>

![手順 4: クラウド アプリMicrosoft 365ポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="22e5a-204">次の条件付きアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="22e5a-204">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="22e5a-205">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="22e5a-205">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="22e5a-206">SharePoint</span><span class="sxs-lookup"><span data-stu-id="22e5a-206">SharePoint</span></span>](sharepoint-file-access-policies.md)