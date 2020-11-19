---
title: 推奨される Teams ポリシー-エンタープライズ向け Microsoft 365 |Microsoft Docs
description: Teams の通信とファイルアクセスをセキュリティで保護する方法に関する Microsoft の推奨事項のポリシーを説明します。
author: MicrosoftHeidi
manager: serdars
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: fa22d445b0e4517bedd1c04378271e561ecb6703
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357505"
---
# <a name="policy-recommendations-for-securing-teams-chats-groups-and-files"></a><span data-ttu-id="811c5-103">Teams のチャット、グループ、およびファイルを保護するためのポリシーの推奨事項</span><span class="sxs-lookup"><span data-stu-id="811c5-103">Policy recommendations for securing Teams chats, groups, and files</span></span>

<span data-ttu-id="811c5-104">この記事では、推奨される id とデバイスアクセスポリシーを実装して、Microsoft Teams のチャット、グループ、およびファイルや予定表などのコンテンツを保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="811c5-104">This article describes how to implement the recommended identity and device-access policies to protect Microsoft Teams chats, groups, and content such as files and calendars.</span></span> <span data-ttu-id="811c5-105">このガイダンスでは、 [共通の id およびデバイスアクセスポリシー](identity-access-policies.md)と、Teams 固有の追加情報を作成します。</span><span class="sxs-lookup"><span data-stu-id="811c5-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md), with additional information that's Teams-specific.</span></span> <span data-ttu-id="811c5-106">Teams は他の製品と統合されているため、 [SharePoint サイトとファイルをセキュリティで保護するためのポリシー推奨事項](sharepoint-file-access-policies.md) と、 [電子メールをセキュリティ保護するためのポリシー推奨](secure-email-recommended-policies.md)事項も参照してください。</span><span class="sxs-lookup"><span data-stu-id="811c5-106">Because Teams integrates with our other products, also see [Policy recommendations for securing SharePoint sites and files](sharepoint-file-access-policies.md) and [Policy recommendations for securing email](secure-email-recommended-policies.md).</span></span>

<span data-ttu-id="811c5-107">これらの推奨事項は、ニーズの粒度 (基準、機密、高規制) に基づいて適用できる、3つの異なるレベルのセキュリティと、Teams の保護に基づいています。</span><span class="sxs-lookup"><span data-stu-id="811c5-107">These recommendations are based on three different tiers of security and protection for Teams that can be applied based on the granularity of your needs: baseline, sensitive, and highly regulated.</span></span> <span data-ttu-id="811c5-108">これらのセキュリティ層および推奨されるポリシーの詳細については、「 [id とデバイスのアクセス構成](microsoft-365-policies-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="811c5-108">You can learn more about these security tiers and the recommended policies referenced by these recommendations in the [Identity and device access configurations](microsoft-365-policies-configurations.md).</span></span>

<span data-ttu-id="811c5-109">この記事には、Teams の展開に関するその他の推奨事項が含まれており、組織外のユーザーを含む特定の認証状況について説明しています。</span><span class="sxs-lookup"><span data-stu-id="811c5-109">Additional recommendations specific to Teams deployment are included in this article to cover specific authentication circumstances, including for users outside your organization.</span></span> <span data-ttu-id="811c5-110">セキュリティを完全に向上させるには、このガイダンスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="811c5-110">You will need to follow this guidance for a complete security experience.</span></span>

## <a name="getting-started-with-teams-before-other-dependent-services"></a><span data-ttu-id="811c5-111">他の依存サービスの前に Teams を使い始める</span><span class="sxs-lookup"><span data-stu-id="811c5-111">Getting started with Teams before other dependent services</span></span>

<span data-ttu-id="811c5-112">Microsoft Teams の使用を開始するために、依存サービスを有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="811c5-112">You don't need to enable dependent services to get started with Microsoft Teams.</span></span> <span data-ttu-id="811c5-113">これらはすべて "機能します" ということになります。</span><span class="sxs-lookup"><span data-stu-id="811c5-113">These will all "just work."</span></span> <span data-ttu-id="811c5-114">ただし、次のものを管理するための準備が必要です。</span><span class="sxs-lookup"><span data-stu-id="811c5-114">However, you do need to be prepared to manage the following:</span></span>

- <span data-ttu-id="811c5-115">Microsoft 365 グループ</span><span class="sxs-lookup"><span data-stu-id="811c5-115">Microsoft 365 groups</span></span>
- <span data-ttu-id="811c5-116">SharePoint チーム サイト</span><span class="sxs-lookup"><span data-stu-id="811c5-116">SharePoint team sites</span></span>
- <span data-ttu-id="811c5-117">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="811c5-117">OneDrive for Business</span></span>
- <span data-ttu-id="811c5-118">Exchange メールボックス</span><span class="sxs-lookup"><span data-stu-id="811c5-118">Exchange mailboxes</span></span>
- <span data-ttu-id="811c5-119">ストリーミングビデオおよび Planner プラン (これらのサービスが有効になっている場合)</span><span class="sxs-lookup"><span data-stu-id="811c5-119">Stream videos and Planner plans (if these services are enabled)</span></span>

## <a name="updating-common-policies-to-include-teams"></a><span data-ttu-id="811c5-120">共通ポリシーを更新して Teams を含める</span><span class="sxs-lookup"><span data-stu-id="811c5-120">Updating common policies to include Teams</span></span>

<span data-ttu-id="811c5-121">Teams のチャット、グループ、およびコンテンツを保護するために、次の図は、共通 id およびデバイスアクセスポリシーから更新するポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="811c5-121">To protect chat, groups and content in Teams, the following diagram illustrates which policies to update from the the common identity and device access policies.</span></span> <span data-ttu-id="811c5-122">更新するポリシーごとに、Teams および依存サービスがクラウドアプリの割り当てに含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="811c5-122">For each policy to update, make sure that Teams and dependent services are included in the assignment of cloud apps.</span></span>

<span data-ttu-id="811c5-123">[![Teams およびその依存サービスへのアクセスを保護するためのポリシー更新の概要](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span><span class="sxs-lookup"><span data-stu-id="811c5-123">[![Summary of policy updates for protecting access to Teams and its dependent services](../../media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)</span></span>

[<span data-ttu-id="811c5-124">この画像のより大きいバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="811c5-124">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-teams.png)

<span data-ttu-id="811c5-125">Teams のクラウドアプリの割り当てに含める依存サービスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="811c5-125">These are the dependent services to include in the assignment of cloud apps for Teams:</span></span>

- <span data-ttu-id="811c5-126">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="811c5-126">Microsoft Teams</span></span>
- <span data-ttu-id="811c5-127">SharePoint および OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="811c5-127">SharePoint and OneDrive for Business</span></span>
- <span data-ttu-id="811c5-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="811c5-128">Exchange Online</span></span>
- <span data-ttu-id="811c5-129">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="811c5-129">Skype for Business Online</span></span>
- <span data-ttu-id="811c5-130">Microsoft Stream (会議のレコーディング)</span><span class="sxs-lookup"><span data-stu-id="811c5-130">Microsoft Stream (meeting recordings)</span></span>
- <span data-ttu-id="811c5-131">Microsoft Planner (Planner タスクおよびプランデータ)</span><span class="sxs-lookup"><span data-stu-id="811c5-131">Microsoft Planner (Planner tasks and plan data)</span></span>

<span data-ttu-id="811c5-132">次の表に、すべての Office アプリケーションに対して、より広範なポリシーが設定されている [共通の id およびデバイスアクセスポリシー](identity-access-policies.md)で、再検討する必要があるポリシーと各ポリシーへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="811c5-132">This table lists the policies that need to be revisited and links to each policy in the [common identity and device access policies](identity-access-policies.md), which has the wider policy set for all Office applications.</span></span>

|<span data-ttu-id="811c5-133">保護レベル</span><span class="sxs-lookup"><span data-stu-id="811c5-133">Protection level</span></span>|<span data-ttu-id="811c5-134">Policies</span><span class="sxs-lookup"><span data-stu-id="811c5-134">Policies</span></span>|<span data-ttu-id="811c5-135">Teams の実装に関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="811c5-135">Further information for Teams implementation</span></span>|
|---|---|---|
|<span data-ttu-id="811c5-136">**Baseline**</span><span class="sxs-lookup"><span data-stu-id="811c5-136">**Baseline**</span></span>|[<span data-ttu-id="811c5-137">サインインリスクが *中* または *高* の場合は MFA を必須にする</span><span class="sxs-lookup"><span data-stu-id="811c5-137">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="811c5-138">アプリの一覧に Teams および依存サービスが含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="811c5-138">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="811c5-139">Teams にはゲストアクセスと外部アクセスのルールが含まれています。これについては、この記事の後半で説明します。</span><span class="sxs-lookup"><span data-stu-id="811c5-139">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these later in this article.</span></span>|
||[<span data-ttu-id="811c5-140">先進認証をサポートしないクライアントはブロックする</span><span class="sxs-lookup"><span data-stu-id="811c5-140">Block clients that don't support modern authentication</span></span>](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|<span data-ttu-id="811c5-141">クラウドアプリの割り当てに Teams および依存するサービスを含めます。</span><span class="sxs-lookup"><span data-stu-id="811c5-141">Include Teams and dependent services in the assignment of cloud apps.</span></span>|
||[<span data-ttu-id="811c5-142">高リスク ユーザーはパスワードを変更する必要がある</span><span class="sxs-lookup"><span data-stu-id="811c5-142">High risk users must change password</span></span>](identity-access-policies.md#high-risk-users-must-change-password)|<span data-ttu-id="811c5-143">リスクの高いアクティビティがアカウントに対して検出された場合に、サインイン時に Teams ユーザーがパスワードを変更することを強制します。</span><span class="sxs-lookup"><span data-stu-id="811c5-143">Forces Teams users to change their password when signing in if high-risk activity is detected for their account.</span></span> <span data-ttu-id="811c5-144">アプリの一覧に Teams および依存サービスが含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="811c5-144">Be sure Teams and dependent services are included in the list of apps.</span></span>|
||[<span data-ttu-id="811c5-145">アプリデータ保護ポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="811c5-145">Apply APP data protection policies</span></span>](identity-access-policies.md#apply-app-data-protection-policies)|<span data-ttu-id="811c5-146">アプリの一覧に Teams および依存サービスが含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="811c5-146">Be sure Teams and dependent services are included in the list of apps.</span></span> <span data-ttu-id="811c5-147">各プラットフォーム (iOS、Android、Windows) のポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="811c5-147">Update the policy for each platform (iOS, Android, Windows).</span></span>|
||[<span data-ttu-id="811c5-148">デバイスコンプライアンスポリシーの定義</span><span class="sxs-lookup"><span data-stu-id="811c5-148">Define device compliance policies</span></span>](identity-access-policies.md#define-device-compliance-policies)|<span data-ttu-id="811c5-149">このポリシーに Teams および依存するサービスを含めます。</span><span class="sxs-lookup"><span data-stu-id="811c5-149">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="811c5-150">準拠 PC が必要</span><span class="sxs-lookup"><span data-stu-id="811c5-150">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="811c5-151">このポリシーに Teams および依存するサービスを含めます。</span><span class="sxs-lookup"><span data-stu-id="811c5-151">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="811c5-152">**機密**</span><span class="sxs-lookup"><span data-stu-id="811c5-152">**Sensitive**</span></span>|[<span data-ttu-id="811c5-153">サインインリスクが *低*、*中*、*高* のときに MFA を必要とする</span><span class="sxs-lookup"><span data-stu-id="811c5-153">Require MFA when sign-in risk is *low*, *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="811c5-154">Teams にはゲストアクセスと外部アクセスのルールが含まれています。これについては、この記事の後半で説明します。</span><span class="sxs-lookup"><span data-stu-id="811c5-154">Teams has Guest Access and External Access rules to consider as well, you'll learn more about these later in this article.</span></span> <span data-ttu-id="811c5-155">このポリシーに Teams および依存するサービスを含めます。</span><span class="sxs-lookup"><span data-stu-id="811c5-155">Include Teams and dependent services in this policy.</span></span>|
||[<span data-ttu-id="811c5-156">準拠 *して* いる pc とモバイルデバイスが必要</span><span class="sxs-lookup"><span data-stu-id="811c5-156">Require compliant PCs *and* mobile devices</span></span>](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|<span data-ttu-id="811c5-157">このポリシーに Teams および依存するサービスを含めます。</span><span class="sxs-lookup"><span data-stu-id="811c5-157">Include Teams and dependent services in this policy.</span></span>|
|<span data-ttu-id="811c5-158">**厳しく規制**</span><span class="sxs-lookup"><span data-stu-id="811c5-158">**Highly regulated**</span></span>|[<span data-ttu-id="811c5-159">*常に* MFA が必要</span><span class="sxs-lookup"><span data-stu-id="811c5-159">*Always* require MFA</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="811c5-160">ユーザー id に関係なく、MFA は組織によって使用されます。</span><span class="sxs-lookup"><span data-stu-id="811c5-160">Regardless of user identity, MFA will be used by your organization.</span></span> <span data-ttu-id="811c5-161">このポリシーに Teams および依存するサービスを含めます。</span><span class="sxs-lookup"><span data-stu-id="811c5-161">Include Teams and dependent services in this policy.</span></span> |
|

## <a name="teams-dependent-services-architecture"></a><span data-ttu-id="811c5-162">Teams 依存サービスのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="811c5-162">Teams dependent services architecture</span></span>

<span data-ttu-id="811c5-163">参考として、次の図は、サービスチームが依存していることを示しています。</span><span class="sxs-lookup"><span data-stu-id="811c5-163">For reference, the following diagram illustrates the services Teams relies on.</span></span> <span data-ttu-id="811c5-164">詳細とその他の図については、「microsoft [Teams and related プロダクティビティ service In microsoft 365 IN IT アーキテクト](../../solutions/productivity-illustrations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="811c5-164">For more information and additional illustrations, see [Microsoft Teams and related productivity services in Microsoft 365 for IT architects](../../solutions/productivity-illustrations.md).</span></span>

<span data-ttu-id="811c5-165">[![SharePoint、OneDrive for Business、および Exchange への Teams の依存関係を示す図](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span><span class="sxs-lookup"><span data-stu-id="811c5-165">[![Diagram showing Teams dependencies on SharePoint, OneDrive for Business, and Exchange](../../media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)</span></span>

[<span data-ttu-id="811c5-166">この画像のより大きいバージョンを表示する</span><span class="sxs-lookup"><span data-stu-id="811c5-166">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-logical-architecture-teams.png)

## <a name="guest-and-external-access-for-teams"></a><span data-ttu-id="811c5-167">Teams のゲストおよび外部アクセス</span><span class="sxs-lookup"><span data-stu-id="811c5-167">Guest and external access for Teams</span></span>

<span data-ttu-id="811c5-168">Microsoft Teams では、以下を定義します。</span><span class="sxs-lookup"><span data-stu-id="811c5-168">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="811c5-169">**ゲストアクセス** では、チームのメンバーとして追加し、すべての権限がチームのコミュニケーションとリソースにアクセスできるようにする、ゲストまたは外部ユーザーに対して AZURE AD B2B アカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="811c5-169">**Guest access** uses an Azure AD B2B account for a guest or external user that can be added as a member of a team and have all permissioned access to the communication and resources of the team.</span></span>

- <span data-ttu-id="811c5-170">Azure AD B2B アカウントを持たない外部ユーザーに対して **外部アクセス** を行います。</span><span class="sxs-lookup"><span data-stu-id="811c5-170">**External access** is for an external user that does not have an Azure AD B2B account.</span></span> <span data-ttu-id="811c5-171">外部アクセスには、通話、チャット、および会議への招待と参加を含めることができますが、チームのメンバーシップやチームのリソースへのアクセスは含まれません。</span><span class="sxs-lookup"><span data-stu-id="811c5-171">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="811c5-172">条件付きアクセスポリシーは、対応する Azure AD B2B アカウントがあるため、Teams でのゲストアクセスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="811c5-172">Conditional Access policies only apply to guest access in Teams because there is a corresponding Azure AD B2B account.</span></span>

<!--
In Azure AD, guest and external users are the same. The user type for both of these is Guest. Guest users are B2B users. Microsoft Teams differentiates between guest users and external users in the app. While it's important to understand how each of these are treated in Teams, both types of users are B2B users in Azure AD and the recommended policies for B2B users apply to both.

-->

<span data-ttu-id="811c5-173">Azure AD B2B アカウントを使用してゲストユーザーと外部ユーザーにアクセスを許可するために推奨されるポリシーについては、「 [ゲストおよび外部 B2B アカウントのアクセスを許可するためのポリシー](identity-access-policies-guest-access.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="811c5-173">For recommended policies to allow access for guest and external users with an Azure AD B2B account, see [Policies for allowing guest and external B2B account access](identity-access-policies-guest-access.md).</span></span>

### <a name="guest-access-in-teams"></a><span data-ttu-id="811c5-174">Teams でのゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="811c5-174">Guest access in Teams</span></span>

<span data-ttu-id="811c5-175">企業または組織の内部にあるユーザーのポリシーに加えて、管理者はゲストアクセスを有効にして、ユーザーごとに、組織外のユーザーが Teams のリソースにアクセスしたり、グループの会話、チャット、会議などの内部ユーザーと対話したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="811c5-175">In addition to the policies for users who are internal to your business or organization, administrators may enable guest access to allow, on a user-by-user basis, people who are external to your business or organization to access Teams resources and interact with internal people for things like group conversations, chat, and meetings.</span></span>

<span data-ttu-id="811c5-176">ゲストアクセスおよびその実装方法の詳細については、「  [Teams ゲストアクセス](https://docs.microsoft.com/microsoftteams/guest-access)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="811c5-176">For more information about guest access and how to implement it, see  [Teams guest access](https://docs.microsoft.com/microsoftteams/guest-access).</span></span>

### <a name="external-access-in-teams"></a><span data-ttu-id="811c5-177">Teams での外部アクセス</span><span class="sxs-lookup"><span data-stu-id="811c5-177">External access in Teams</span></span>

<span data-ttu-id="811c5-178">外部アクセスは、ゲストアクセスと混同されることがあるため、これらの2つの非内部アクセスメカニズムが実際に大きく異なることを明確にすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="811c5-178">External access is sometimes confused with guest access, so it's important to be clear that these two non-internal access mechanisms are actually quite different.</span></span>

<span data-ttu-id="811c5-179">外部アクセスは、teams のユーザーとの間で、外部ドメイン全体の Teams ユーザーが会議を検索、呼び出し、チャット、セットアップするための方法です。</span><span class="sxs-lookup"><span data-stu-id="811c5-179">External access is a way for Teams users from an entire external domain to find, call, chat, and set up meetings with your users in Teams.</span></span> <span data-ttu-id="811c5-180">Teams 管理者は、組織レベルで外部アクセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="811c5-180">Teams administrators configure external access at the organization level.</span></span> <span data-ttu-id="811c5-181">詳細については、「 [Microsoft Teams で外部アクセスを管理](https://docs.microsoft.com/microsoftteams/manage-external-access)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="811c5-181">For more information, see [Manage external access in Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-external-access).</span></span>

<span data-ttu-id="811c5-182">外部アクセスユーザーのアクセス権と機能は、ゲストアクセスで追加された個人数よりも少なくなります。</span><span class="sxs-lookup"><span data-stu-id="811c5-182">External access users have less access and functionality than an individual who's been added via guest access.</span></span> <span data-ttu-id="811c5-183">たとえば、外部アクセスユーザーは、Teams を使用して内部ユーザーとチャットすることはできますが、チームチャネル、ファイル、またはその他のリソースにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="811c5-183">For example, external access users can chat with your internal users with Teams but cannot access team channels, files, or other resources.</span></span>

<span data-ttu-id="811c5-184">外部アクセスでは、Azure AD B2B ユーザーアカウントを使用しないため、条件付きアクセスポリシーを使用しません。</span><span class="sxs-lookup"><span data-stu-id="811c5-184">External access does not use Azure AD B2B user accounts and therefore does not use Conditional Access policies.</span></span>

## <a name="teams-policies"></a><span data-ttu-id="811c5-185">Teams ポリシー</span><span class="sxs-lookup"><span data-stu-id="811c5-185">Teams policies</span></span>

<span data-ttu-id="811c5-186">上記の一般的なポリシーの範囲外では、さまざまなチームの機能を管理するために構成できる Teams 固有のポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="811c5-186">Outside of the common policies listed above, there are Teams-specific policies that can and should be configured to manage various Teams functionalities.</span></span>

### <a name="teams-and-channels-policies"></a><span data-ttu-id="811c5-187">Teams およびチャネルのポリシー</span><span class="sxs-lookup"><span data-stu-id="811c5-187">Teams and channels policies</span></span>

<span data-ttu-id="811c5-188">Teams とチャネルは、Microsoft Teams でよく使用される2つの要素であり、teams やチャネルを使用する際にユーザーが実行できることとできないことを制御するために配置できるポリシーがあります。</span><span class="sxs-lookup"><span data-stu-id="811c5-188">Teams and channels are two commonly used elements in Microsoft Teams, and there are policies you can put in place to control what users can and cannot do when using teams and channels.</span></span> <span data-ttu-id="811c5-189">グローバルチームを作成することはできますが、組織のユーザーが5000人以下の場合は、組織のニーズに合わせて、特定の目的のためにチームとチャネルを小さくした方が便利な場合があります。</span><span class="sxs-lookup"><span data-stu-id="811c5-189">While you can create a global team, if your organization has 5000 users or less, you are likely to find it helpful to have smaller teams and channels for specific purposes, in-line with your organizational needs.</span></span>

<span data-ttu-id="811c5-190">既定のポリシーを変更するか、カスタムポリシーを作成することをお勧めします。このリンクでは、「 [Microsoft teams で teams ポリシーを管理する」に記載](https://docs.microsoft.com/microsoftteams/teams-policies)されているポリシーの管理について説明します。</span><span class="sxs-lookup"><span data-stu-id="811c5-190">Changing the default policy or creating custom policies would be recommended, and you can learn more about managing your policies at this link: [Manage teams policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-policies).</span></span>

### <a name="messaging-policies"></a><span data-ttu-id="811c5-191">メッセージングポリシー</span><span class="sxs-lookup"><span data-stu-id="811c5-191">Messaging policies</span></span>

<span data-ttu-id="811c5-192">メッセージングやチャットは、既定のグローバルポリシーまたはカスタムポリシーを使用して管理することもできます。これにより、ユーザーは自分の組織に適した方法で相互に通信することができます。</span><span class="sxs-lookup"><span data-stu-id="811c5-192">Messaging, or chat, can also be managed through the default global policy, or through custom policies, and this can help your users communicate with one another in a way that's appropriate for your organization.</span></span> <span data-ttu-id="811c5-193">この情報は、「 [Teams でのメッセージングポリシーの管理」](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams)で確認できます。</span><span class="sxs-lookup"><span data-stu-id="811c5-193">This information can be reviewed at [Managing messaging policies in Teams](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams).</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="811c5-194">ミーティング ポリシー</span><span class="sxs-lookup"><span data-stu-id="811c5-194">Meeting policies</span></span>

<span data-ttu-id="811c5-195">Teams の会議に関するポリシーを計画して実装しなくても、チームの討議は完了しません。</span><span class="sxs-lookup"><span data-stu-id="811c5-195">No discussion of Teams would be complete without planning and implementing policies around Teams meetings.</span></span> <span data-ttu-id="811c5-196">会議は、Teams の重要なコンポーネントであり、会議に関連するコンテンツの共有だけでなく、複数のユーザーに対して、ユーザーが正式に会うことができるようにしたり、一度に表示したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="811c5-196">Meetings are an essential component of Teams, allowing people to formally meet and present to many users at once, as well as share content relevant to the meeting.</span></span> <span data-ttu-id="811c5-197">組織に適したポリシーを会議に沿って設定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="811c5-197">Setting the right policies for your organization around meetings is essential.</span></span>

<span data-ttu-id="811c5-198">詳細については、「 [Teams での会議ポリシーの管理」](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="811c5-198">Please review [Manage meeting policies in Teams](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) for more information.</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="811c5-199">アプリのアクセス許可ポリシー</span><span class="sxs-lookup"><span data-stu-id="811c5-199">App permission policies</span></span>

<span data-ttu-id="811c5-200">Teams では、チャネルや個人のチャットなど、さまざまな場所でアプリを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="811c5-200">Teams also allows you to use apps in various places, such as channels or personal chats.</span></span> <span data-ttu-id="811c5-201">セキュリティで保護されたコンテンツリッチな環境を維持するには、追加および使用できるアプリケーションに関するポリシーが必要です。</span><span class="sxs-lookup"><span data-stu-id="811c5-201">Having policies around what apps can be added and used, and where, is essential to maintaining a content-rich environment that is also secure.</span></span>

<span data-ttu-id="811c5-202">アプリのアクセス許可ポリシーの詳細については、「 [Microsoft Teams でアプリのアクセス許可ポリシーを管理](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="811c5-202">For more reading about App Permission Policies, check out [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-app-permission-policies).</span></span>

## <a name="next-steps"></a><span data-ttu-id="811c5-203">次の手順</span><span class="sxs-lookup"><span data-stu-id="811c5-203">Next steps</span></span>

![手順 4: Microsoft 365 クラウドアプリのポリシー](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="811c5-205">次の条件付きアクセスポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="811c5-205">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="811c5-206">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="811c5-206">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="811c5-207">SharePoint</span><span class="sxs-lookup"><span data-stu-id="811c5-207">SharePoint</span></span>](sharepoint-file-access-policies.md)
