---
title: 推奨される Teams ポリシー - エンタープライズ向け Microsoft 365 |Microsoft Docs
description: Teams の通信とファイル アクセスをセキュリティで保護する方法に関する Microsoft の推奨事項に関するポリシーについて説明します。
author: MicrosoftHeidi
manager: serdars
ms.prod: m365-security
ms.topic: article
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
ms.openlocfilehash: 12bdf0df1a5b2f616c5b2bed61d69e8226fa5844
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097188"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a><span data-ttu-id="c695c-103">Teams のチャット、グループ、およびファイルをセキュリティ保護するためのポリシーの推奨事項</span><span class="sxs-lookup"><span data-stu-id="c695c-103">Policy recommendations for securing Teams chats, groups, and files</span></span>

<span data-ttu-id="c695c-104">この記事では、推奨される ID とデバイス アクセス ポリシーを実装して、Microsoft Teams のチャット、グループ、ファイルや予定表などのコンテンツを保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c695c-104">This article describes how to implement the recommended identity and device-access policies to protect Microsoft Teams chats, groups, and content such as files and calendars.</span></span> <span data-ttu-id="c695c-105">このガイダンスは、Teams [固有の](identity-access-policies.md)追加情報を含む、共通の ID ポリシーとデバイス アクセス ポリシーに基っています。</span><span class="sxs-lookup"><span data-stu-id="c695c-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md), with additional information that's Teams-specific.</span></span> <span data-ttu-id="c695c-106">Teams は他の製品と統合されます。このため [、SharePoint](sharepoint-file-access-policies.md) サイトとファイルをセキュリティ保護するためのポリシーの推奨事項、および電子メールをセキュリティ保護するためのポリシーの推奨事項 [も参照してください](secure-email-recommended-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="c695c-106">Because Teams integrates with our other products, also see [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md) and [Policy recommendations for securing email](secure-email-recommended-policies.md).</span></span>

<span data-ttu-id="c695c-107">これらの推奨事項は、ニーズの粒度に基づいて適用できる Teams のセキュリティと保護の 3 つの異なる層に基づいており、ベースライン、機密、厳しく規制されています。</span><span class="sxs-lookup"><span data-stu-id="c695c-107">These recommendations are based on three different tiers of security and protection for Teams that can be applied based on the granularity of your needs: baseline, sensitive, and highly regulated.</span></span> <span data-ttu-id="c695c-108">これらのセキュリティ層と、これらの推奨事項で参照される推奨ポリシーの詳細については、ID とデバイスのアクセス構成 [に関するページを参照してください](microsoft-365-policies-configurations.md)。</span><span class="sxs-lookup"><span data-stu-id="c695c-108">You can learn more about these security tiers and the recommended policies referenced by these recommendations in the [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="c695c-109">Teams の展開に固有の推奨事項については、組織外のユーザーを含め、特定の認証環境をカバーするために、この記事に含まれています。</span><span class="sxs-lookup"><span data-stu-id="c695c-109">More recommendations specific to Teams deployment are included in this article to cover specific authentication circumstances, including for users outside your organization.</span></span> <span data-ttu-id="c695c-110">完全なセキュリティ エクスペリエンスを提供するには、このガイダンスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c695c-110">You will need to follow this guidance for a complete security experience.</span></span>

## <a name="getting-started-with-teams-before-other-dependent-services"></a><span data-ttu-id="c695c-111">他の依存サービスの前に Teams を使い始める</span><span class="sxs-lookup"><span data-stu-id="c695c-111">Getting started with Teams before other dependent services</span></span>

<span data-ttu-id="c695c-112">Microsoft Teams を使い始めるには、依存サービスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c695c-112">You don't need to enable dependent services to get started with Microsoft Teams.</span></span> <span data-ttu-id="c695c-113">これらのサービスはすべて "機能するだけ" です。</span><span class="sxs-lookup"><span data-stu-id="c695c-113">These services will all "just work."</span></span> <span data-ttu-id="c695c-114">ただし、次のサービス関連の要素を管理する準備が必要です。</span><span class="sxs-lookup"><span data-stu-id="c695c-114">However, you do need to be prepared to manage the following service-related elements:</span></span>

- <span data-ttu-id="c695c-115">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="c695c-115">Microsoft 365 groups</span></span>
- <span data-ttu-id="c695c-116">SharePoint チーム サイト</span><span class="sxs-lookup"><span data-stu-id="c695c-116">SharePoint team sites</span></span>
- <span data-ttu-id="c695c-117">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="c695c-117">OneDrive for Business</span></span>
- <span data-ttu-id="c695c-118">Exchange メールボックス</span><span class="sxs-lookup"><span data-stu-id="c695c-118">Exchange mailboxes</span></span>
- <span data-ttu-id="c695c-119">Stream ビデオと Planner プラン (これらのサービスが有効な場合)</span><span class="sxs-lookup"><span data-stu-id="c695c-119">Stream videos and Planner plans (if these services are enabled)</span></span>

## <a name="updating-common-policies-to-include-teams"></a><span data-ttu-id="c695c-120">Teams を含める一般的なポリシーの更新</span><span class="sxs-lookup"><span data-stu-id="c695c-120">Updating common policies to include Teams</span></span>

<span data-ttu-id="c695c-121">Teams のチャット、グループ、コンテンツを保護するために、次の図は、共通の ID ポリシーとデバイス アクセス ポリシーから更新するポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="c695c-121">To protect chat, groups and content in Teams, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span> <span data-ttu-id="c695c-122">更新するポリシーごとに、Teams と依存するサービスがクラウド アプリの割り当てに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c695c-122">For each policy to update, make sure that Teams and dependent services are included in the assignment of cloud apps.</span></span>

<span data-ttu-id="c695c-123">[![Teams とその依存サービスへのアクセスを保護するためのポリシー更新の概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span><span class="sxs-lookup"><span data-stu-id="c695c-123">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span></span>

[<span data-ttu-id="c695c-124">このイメージのより大きなバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="c695c-124">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

<span data-ttu-id="c695c-125">これらのサービスは、Teams 用のクラウド アプリの割り当てに含める依存サービスです。</span><span class="sxs-lookup"><span data-stu-id="c695c-125">These services are the dependent services to include in the assignment of cloud apps for Teams:</span></span>

- <span data-ttu-id="c695c-126">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c695c-126">Microsoft Teams</span></span>
- <span data-ttu-id="c695c-127">SharePoint および OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="c695c-127">SharePoint and OneDrive for Business</span></span>
- <span data-ttu-id="c695c-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c695c-128">Exchange Online</span></span>
- <span data-ttu-id="c695c-129">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c695c-129">Skype for Business Online</span></span>
- <span data-ttu-id="c695c-130">Microsoft Stream (会議のレコーディング)</span><span class="sxs-lookup"><span data-stu-id="c695c-130">Microsoft Stream (meeting recordings)</span></span>
- <span data-ttu-id="c695c-131">Microsoft Planner (Planner のタスクと計画データ)</span><span class="sxs-lookup"><span data-stu-id="c695c-131">Microsoft Planner (Planner tasks and plan data)</span></span>

<span data-ttu-id="c695c-132">次の表に、再検討が必要なポリシーと、共通 ID ポリシーとデバイス[](identity-access-policies.md)アクセス ポリシー内の各ポリシーへのリンクを示します。このポリシーには、すべての Office アプリケーションに対して広範なポリシーが設定されています。</span><span class="sxs-lookup"><span data-stu-id="c695c-132">This table lists the policies that need to be revisited and links to each policy in the [common identity and device access policies](identity-access-policies.md), which has the wider policy set for all Office applications.</span></span>

|<span data-ttu-id="c695c-133">保護レベル</span><span class="sxs-lookup"><span data-stu-id="c695c-133">Protection level</span></span>|<span data-ttu-id="c695c-134">Policies</span><span class="sxs-lookup"><span data-stu-id="c695c-134">Policies</span></span>|<span data-ttu-id="c695c-135">Teams の実装に関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="c695c-135">Further information for Teams implementation</span></span>|
|---|---|---|
|<span data-ttu-id="c695c-136">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="c695c-136">**Baseline**</span></span>|[<span data-ttu-id="c695c-137">サインイン リスクが中程度または高の場合に MFA *を* 要求 *する*</span><span class="sxs-lookup"><span data-stu-id="c695c-137">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="c695c-138">Teams と依存するサービスがアプリの一覧に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c695c-138">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="c695c-139">Teams にはゲスト アクセスと外部アクセスのルールも考慮する必要があります。これらのルールの詳細については、この記事の後半で説明します。</span><span class="sxs-lookup"><span data-stu-id="c695c-139">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these rules later in this article.</span></span>|
||[<span data-ttu-id="c695c-140">先進認証をサポートしないクライアントはブロックする</span><span class="sxs-lookup"><span data-stu-id="c695c-140">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|<span data-ttu-id="c695c-141">クラウド アプリの割り当てに Teams と依存サービスを含める。</span><span class="sxs-lookup"><span data-stu-id="c695c-141">Include Teams and dependent services in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="c695c-142">高リスク ユーザーはパスワードを変更する必要がある</span><span class="sxs-lookup"><span data-stu-id="c695c-142">High risk users must change password</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="c695c-143">自分のアカウントで危険度の高いアクティビティが検出された場合、サインイン時に Teams ユーザーにパスワードの変更を強制的に行います。</span><span class="sxs-lookup"><span data-stu-id="c695c-143">Forces Teams users to change their password when signing in if high-risk activity is detected for their account.</span></span> <span data-ttu-id="c695c-144">Teams と依存するサービスがアプリの一覧に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c695c-144">Be sure Teams and dependent services are included in the list of apps.</span></span>|
||[<span data-ttu-id="c695c-145">アプリ データ保護ポリシーの適用</span><span class="sxs-lookup"><span data-stu-id="c695c-145">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="c695c-146">Teams と依存するサービスがアプリの一覧に含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c695c-146">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="c695c-147">各プラットフォーム (iOS、Android、Windows) のポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="c695c-147">Update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="c695c-148">デバイス コンプライアンス ポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="c695c-148">Define device compliance policies</span></span>](identity-access-policies.md#define-device-compliance-policies)|<span data-ttu-id="c695c-149">このポリシーに Teams と依存サービスを含める。</span><span class="sxs-lookup"><span data-stu-id="c695c-149">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="c695c-150">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="c695c-150">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="c695c-151">このポリシーに Teams と依存サービスを含める。</span><span class="sxs-lookup"><span data-stu-id="c695c-151">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="c695c-152">**機密**</span><span class="sxs-lookup"><span data-stu-id="c695c-152">**Sensitive**</span></span>|[<span data-ttu-id="c695c-153">サインインリスクが低、中、高 *の* 場合 *に* MFA を要求 *する*</span><span class="sxs-lookup"><span data-stu-id="c695c-153">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="c695c-154">Teams にはゲスト アクセスと外部アクセスのルールも考慮する必要があります。これらのルールの詳細については、この記事の後半で説明します。</span><span class="sxs-lookup"><span data-stu-id="c695c-154">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these rules later in this article.</span></span> <span data-ttu-id="c695c-155">このポリシーに Teams と依存サービスを含める。</span><span class="sxs-lookup"><span data-stu-id="c695c-155">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="c695c-156">準拠した PC とモバイル *デバイスが* 必要</span><span class="sxs-lookup"><span data-stu-id="c695c-156">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="c695c-157">このポリシーに Teams と依存サービスを含める。</span><span class="sxs-lookup"><span data-stu-id="c695c-157">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="c695c-158">**厳しく規制**</span><span class="sxs-lookup"><span data-stu-id="c695c-158">**Highly regulated**</span></span>|[<span data-ttu-id="c695c-159">*常に* MFA を要求する</span><span class="sxs-lookup"><span data-stu-id="c695c-159">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="c695c-160">ユーザー ID に関係なく、MFA は組織で使用されます。</span><span class="sxs-lookup"><span data-stu-id="c695c-160">Regardless of user identity, MFA will be used by your organization.</span></span> <span data-ttu-id="c695c-161">このポリシーに Teams と依存サービスを含める。</span><span class="sxs-lookup"><span data-stu-id="c695c-161">Include Teams and dependent services in this policy.</span></span> |
|

## <a name="teams-dependent-services-architecture"></a><span data-ttu-id="c695c-162">Teams 依存サービスのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="c695c-162">Teams dependent services architecture</span></span>

<span data-ttu-id="c695c-163">参考までに、次の図は Teams が依存するサービスを示しています。</span><span class="sxs-lookup"><span data-stu-id="c695c-163">For reference, the following diagram illustrates the services Teams relies on.</span></span> <span data-ttu-id="c695c-164">詳細と図については、IT アーキテクト向け [Microsoft 365 の Microsoft Teams](../../solutions/productivity-illustrations.md)および関連する生産性サービスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c695c-164">For more information and illustrations, see [Microsoft Teams and related productivity services in Microsoft 365 for IT architects](../../solutions/productivity-illustrations.md).</span></span>

<span data-ttu-id="c695c-165">[![SharePoint、OneDrive for Business、Exchange に対する Teams の依存関係を示す図](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span><span class="sxs-lookup"><span data-stu-id="c695c-165">[![Diagram showing Teams dependencies on SharePoint, OneDrive for Business, and Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span></span>

[<span data-ttu-id="c695c-166">このイメージのより大きなバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="c695c-166">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a><span data-ttu-id="c695c-167">Teams のゲストアクセスと外部アクセス</span><span class="sxs-lookup"><span data-stu-id="c695c-167">Guest and external access for Teams</span></span>

<span data-ttu-id="c695c-168">Microsoft Teams では、次のアクセスの種類を定義します。</span><span class="sxs-lookup"><span data-stu-id="c695c-168">Microsoft Teams defines the following access types:</span></span>

- <span data-ttu-id="c695c-169">**ゲスト** アクセスは、チームのメンバーとして追加できるゲストユーザーまたは外部ユーザーに対して Azure AD B2B アカウントを使用し、チームのコミュニケーションとリソースへのアクセス許可を持つすべてのアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="c695c-169">**Guest access** uses an Azure AD B2B account for a guest or external user that can be added as a member of a team and have all permissioned access to the communication and resources of the team.</span></span>

- <span data-ttu-id="c695c-170">**外部アクセス** は、Azure アカウントまたは B2B アカウントを持ADユーザー用です。</span><span class="sxs-lookup"><span data-stu-id="c695c-170">**External access** is for an external user that does not have an Azure AD B2B account.</span></span> <span data-ttu-id="c695c-171">外部アクセスには、招待と通話、チャット、会議への参加を含めできますが、チーム メンバーシップとチームのリソースへのアクセスは含め込めではありません。</span><span class="sxs-lookup"><span data-stu-id="c695c-171">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="c695c-172">条件付きアクセス ポリシーは、対応する Azure アカウントと B2B アカウントAD Teams のゲスト アクセスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="c695c-172">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

<span data-ttu-id="c695c-173">Azure AD B2B アカウントを持つゲスト ユーザーと外部ユーザーのアクセスを許可する推奨ポリシーについては、「ゲストと外部の [B2B](identity-access-policies-guest-access.md)アカウント アクセスを許可するポリシー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c695c-173">For recommended policies to allow access for guest and external users with an Azure AD B2B account, see [Policies for allowing guest and external B2B account access](identity-access-policies-guest-access.md).</span></span>

### <a name="guest-access-in-teams"></a><span data-ttu-id="c695c-174">Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="c695c-174">Guest access in Teams</span></span>

<span data-ttu-id="c695c-175">管理者は、企業や組織の内部に所属するユーザーのポリシーに加えて、ユーザー単位でゲスト アクセスを有効にし、ビジネスや組織の外部のユーザーが Teams リソースにアクセスしたり、グループ会話、チャット、会議などについて内部の人と対話したりできる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c695c-175">In addition to the policies for users who are internal to your business or organization, administrators may enable guest access to allow, on a user-by-user basis, people who are external to your business or organization to access Teams resources and interact with internal people for things like group conversations, chat, and meetings.</span></span>

<span data-ttu-id="c695c-176">ゲスト アクセスとゲスト アクセスの実装方法の詳細については、「Teams のゲスト アクセス」  [を参照してください](https://docs.microsoft.com/microsoftteams/guest-access)。</span><span class="sxs-lookup"><span data-stu-id="c695c-176">For more information about guest access and how to implement it, see  [Teams guest access](https://docs.microsoft.com/microsoftteams/guest-access).</span></span>

### <a name="external-access-in-teams"></a><span data-ttu-id="c695c-177">Teams での外部アクセス</span><span class="sxs-lookup"><span data-stu-id="c695c-177">External access in Teams</span></span>

<span data-ttu-id="c695c-178">外部アクセスはゲスト アクセスと混同される場合があります。そのため、これら 2 つの内部以外のアクセス メカニズムが異なる種類のアクセスであることに明確にすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="c695c-178">External access is sometimes confused with guest access, so it's important to be clear that these two non-internal access mechanisms are different types of access.</span></span>

<span data-ttu-id="c695c-179">外部アクセスは、外部ドメイン全体の Teams ユーザーが Teams のユーザーとの会議を検索、通話、チャット、およびセットアップするための方法です。</span><span class="sxs-lookup"><span data-stu-id="c695c-179">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with your users in Teams.</span></span> <span data-ttu-id="c695c-180">Teams 管理者は、組織レベルで外部アクセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="c695c-180">Teams administrators configure external access at the organization level.</span></span> <span data-ttu-id="c695c-181">詳細については [、「Microsoft Teams での外部アクセスの管理」を参照してください](https://docs.microsoft.com/microsoftteams/manage-external-access)。</span><span class="sxs-lookup"><span data-stu-id="c695c-181">For more information, see [Manage external access in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access).</span></span>

<span data-ttu-id="c695c-182">外部アクセス ユーザーは、ゲスト アクセスによって追加されたユーザーよりもアクセスと機能が低い。</span><span class="sxs-lookup"><span data-stu-id="c695c-182">External access users have less access and functionality than an individual who's been added via guest access.</span></span> <span data-ttu-id="c695c-183">たとえば、外部アクセス ユーザーは Teams を使用して内部ユーザーとチャットできますが、チーム チャネル、ファイル、その他のリソースにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="c695c-183">For example, external access users can chat with your internal users with Teams but cannot access team channels, files, or other resources.</span></span>

<span data-ttu-id="c695c-184">外部アクセスでは、B2B ユーザー AD Azure を使用し、条件付きアクセス ポリシーは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c695c-184">External access does not use Azure AD B2B user accounts and therefore does not use Conditional Access policies.</span></span>

## <a name="teams-policies"></a><span data-ttu-id="c695c-185">Teams ポリシー</span><span class="sxs-lookup"><span data-stu-id="c695c-185">Teams policies</span></span>

<span data-ttu-id="c695c-186">上記の一般的なポリシー以外にも、さまざまな Teams 機能を管理するために構成する必要がある Teams 固有のポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="c695c-186">Outside of the common policies listed above, there are Teams-specific policies that can and should be configured to manage various Teams functionalities.</span></span>

### <a name="teams-and-channels-policies"></a><span data-ttu-id="c695c-187">Teams とチャネルのポリシー</span><span class="sxs-lookup"><span data-stu-id="c695c-187">Teams and channels policies</span></span>

<span data-ttu-id="c695c-188">Teams とチャネルは、Microsoft Teams で一般的に使用される 2 つの要素であり、チームとチャネルを使用するときにユーザーが実行できる操作と実行できない操作を制御するポリシーを設定できます。</span><span class="sxs-lookup"><span data-stu-id="c695c-188">Teams and channels are two commonly used elements in Microsoft Teams, and there are policies you can put in place to control what users can and cannot do when using teams and channels.</span></span> <span data-ttu-id="c695c-189">グローバル チームを作成することもできますが、組織のユーザー数が 5,000 以下の場合は、組織のニーズに合った、特定の目的に合った小規模なチームとチャネルを持つ方が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c695c-189">While you can create a global team, if your organization has 5000 users or less, you are likely to find it helpful to have smaller teams and channels for specific purposes, in-line with your organizational needs.</span></span>

<span data-ttu-id="c695c-190">既定のポリシーの変更またはカスタム ポリシーの作成をお勧めします。ポリシーの管理の詳細については [、「Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies)でチーム ポリシーを管理する」のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c695c-190">Changing the default policy or creating custom policies would be recommended, and you can learn more about managing your policies at this link: [Manage teams policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="c695c-191">メッセージング ポリシー</span><span class="sxs-lookup"><span data-stu-id="c695c-191">Messaging policies</span></span>

<span data-ttu-id="c695c-192">メッセージング (チャット) は、既定のグローバル ポリシーまたはカスタム ポリシーを通じて管理することもできます。これにより、ユーザーは組織に適した方法で相互に通信できます。</span><span class="sxs-lookup"><span data-stu-id="c695c-192">Messaging, or chat, can also be managed through the default global policy, or through custom policies, and this can help your users communicate with one another in a way that's appropriate for your organization.</span></span> <span data-ttu-id="c695c-193">この情報は、「Teams でのメッセージング [ポリシーの管理」で確認できます](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="c695c-193">This information can be reviewed at [Managing messaging policies in Teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="c695c-194">ミーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="c695c-194">Meeting policies</span></span>

<span data-ttu-id="c695c-195">Teams 会議に関するポリシーを計画して実装しない場合、Teams の議論は完了しない。</span><span class="sxs-lookup"><span data-stu-id="c695c-195">No discussion of Teams would be complete without planning and implementing policies around Teams meetings.</span></span> <span data-ttu-id="c695c-196">会議は Teams の不可欠なコンポーネントであり、ユーザーは一度に多くのユーザーと公式に会議して発表し、会議に関連するコンテンツを共有できます。</span><span class="sxs-lookup"><span data-stu-id="c695c-196">Meetings are an essential component of Teams, allowing people to formally meet and present to many users at once, and to share content relevant to the meeting.</span></span> <span data-ttu-id="c695c-197">会議に関する組織に適切なポリシーを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c695c-197">Setting the right policies for your organization around meetings is essential.</span></span>

<span data-ttu-id="c695c-198">詳細については、「Teams での会議 [ポリシーの管理」を参照してください](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)。</span><span class="sxs-lookup"><span data-stu-id="c695c-198">For more information, review [Manage meeting policies in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams).</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="c695c-199">アプリのアクセス許可ポリシー</span><span class="sxs-lookup"><span data-stu-id="c695c-199">App permission policies</span></span>

<span data-ttu-id="c695c-200">Teams では、チャネルや個人用チャットなど、さまざまな場所でアプリを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="c695c-200">Teams also allows you to use apps in various places, such as channels or personal chats.</span></span> <span data-ttu-id="c695c-201">どのアプリを追加して使用できるのか、どこで、どこに追加できるのかというポリシーを持つことは、セキュリティも確保されたコンテンツが豊富な環境を維持するために不可欠です。</span><span class="sxs-lookup"><span data-stu-id="c695c-201">Having policies around what apps can be added and used, and where, is essential to maintaining a content-rich environment that is also secure.</span></span>

<span data-ttu-id="c695c-202">アプリのアクセス許可ポリシーの詳細については、「Microsoft Teams でアプリのアクセス許可ポリシーを [管理する」を参照してください](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies)。</span><span class="sxs-lookup"><span data-stu-id="c695c-202">For more reading about App Permission Policies, check out [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c695c-203">次の手順</span><span class="sxs-lookup"><span data-stu-id="c695c-203">Next steps</span></span>

![手順 4: Microsoft 365 クラウド アプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="c695c-205">次の条件に合ったアクセス ポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c695c-205">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="c695c-206">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c695c-206">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="c695c-207">SharePoint</span><span class="sxs-lookup"><span data-stu-id="c695c-207">SharePoint</span></span>](sharepoint-file-access-policies.md)
