---
title: グループ、グループ、Microsoft 365、およびTeamsのアクセスを管理SharePoint
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: グループ、グループ、グループ、Microsoft 365、およびTeamsアクセスの管理SharePoint。
ms.openlocfilehash: 3e0485813a264fe9042e0de9596ba07e50ef72a3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538149"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a><span data-ttu-id="a8382-103">グループ、グループ、Microsoft 365、およびTeamsのアクセスを管理SharePoint</span><span class="sxs-lookup"><span data-stu-id="a8382-103">Governing access in Microsoft 365 groups, Teams, and SharePoint</span></span>

<span data-ttu-id="a8382-104">ユーザーがグループ、チーム、およびグループ内のリソースにアクセスする方法を管理できる多くのコントロールSharePoint。</span><span class="sxs-lookup"><span data-stu-id="a8382-104">There are many controls that enable you to govern how people access resources in groups, teams, and SharePoint.</span></span> <span data-ttu-id="a8382-105">これらのオプションを確認し、ビジネス ニーズ、データの感度、ユーザーが共同作業に必要なユーザーの範囲にマップする方法を検討します。</span><span class="sxs-lookup"><span data-stu-id="a8382-105">Review these options and consider how they map to your business needs, the sensitivity of your data, and the scope of people that your users need to collaborate with.</span></span>

<span data-ttu-id="a8382-106">次の表は、次の表で使用できるアクセス制御のクイック リファレンスを示Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="a8382-106">The following table provides a quick reference for the access controls available in Microsoft 365.</span></span> <span data-ttu-id="a8382-107">詳細については、次のセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="a8382-107">Further information is provided in the following sections.</span></span>

|<span data-ttu-id="a8382-108">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="a8382-108">Category</span></span>|<span data-ttu-id="a8382-109">説明</span><span class="sxs-lookup"><span data-stu-id="a8382-109">Description</span></span>|<span data-ttu-id="a8382-110">参照</span><span class="sxs-lookup"><span data-stu-id="a8382-110">Reference</span></span>|
|:-------|:----------|:--------|
|<span data-ttu-id="a8382-111">メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="a8382-111">Membership</span></span>|||
||<span data-ttu-id="a8382-112">プライベート チームの検出</span><span class="sxs-lookup"><span data-stu-id="a8382-112">Discovery of private teams</span></span>|[<span data-ttu-id="a8382-113">プライベート チームの検出を管理Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8382-113">Manage discovery of private teams in Microsoft Teams</span></span>](/microsoftteams/manage-discovery-of-private-teams)|
||<span data-ttu-id="a8382-114">ルールに基づく動的グループ メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="a8382-114">Dynamic group membership based on rules</span></span>|[<span data-ttu-id="a8382-115">グループ内で動的グループを作成または更新Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a8382-115">Create or update a dynamic group in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-create-rule)|
||<span data-ttu-id="a8382-116">ファイル、フォルダー、サイトを共有できるユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="a8382-116">Control who can share files, folders, and sites.</span></span>|[<span data-ttu-id="a8382-117">アクセス要求の設定と管理</span><span class="sxs-lookup"><span data-stu-id="a8382-117">Set up and manage access requests</span></span>](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|<span data-ttu-id="a8382-118">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="a8382-118">Conditional access</span></span>|||
||<span data-ttu-id="a8382-119">多要素認証</span><span class="sxs-lookup"><span data-stu-id="a8382-119">Multi-Factor Authentication</span></span>|[<span data-ttu-id="a8382-120">Azure AD 多要素認証</span><span class="sxs-lookup"><span data-stu-id="a8382-120">Azure AD Multi-Factor Authentication</span></span>](/azure/active-directory/authentication/concept-mfa-howitworks)|
||<span data-ttu-id="a8382-121">グループ、チーム、またはサイトの感度に基づいてデバイス アクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="a8382-121">Control device access based on group, team, or site sensitivity.</span></span>|[<span data-ttu-id="a8382-122">秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する</span><span class="sxs-lookup"><span data-stu-id="a8382-122">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](../compliance/sensitivity-labels-teams-groups-sites.md)|
||<span data-ttu-id="a8382-123">管理されていないデバイスのサイト アクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="a8382-123">Limit site access for unmanaged devices.</span></span>|[<span data-ttu-id="a8382-124">管理SharePointデバイスからのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="a8382-124">Control SharePoint access from unmanaged devices</span></span>](/sharepoint/control-access-from-unmanaged-devices)|
||<span data-ttu-id="a8382-125">場所に基づいてサイト アクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="a8382-125">Control site access based on location</span></span>|[<span data-ttu-id="a8382-126">ネットワークの場所に基づいて SharePoint と OneDrive のデータへのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="a8382-126">Control access to SharePoint and OneDrive data based on network location</span></span>](/sharepoint/control-access-based-on-network-location)|
|<span data-ttu-id="a8382-127">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="a8382-127">Guest access</span></span>|||
||<span data-ttu-id="a8382-128">指定したドメインSharePoint共有を許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="a8382-128">Allow or block SharePoint sharing from specified domains.</span></span>|[<span data-ttu-id="a8382-129">ドメイン別の SharePoint および OneDrive コンテンツの共有を制限する</span><span class="sxs-lookup"><span data-stu-id="a8382-129">Restrict sharing of SharePoint and OneDrive content by domain</span></span>](/sharepoint/restricted-domains-sharing)|
||<span data-ttu-id="a8382-130">指定したドメインからチームまたはグループのメンバーシップを許可またはブロックします。</span><span class="sxs-lookup"><span data-stu-id="a8382-130">Allow or block team or group membership from specified domains.</span></span>|[<span data-ttu-id="a8382-131">特定の組織からの B2B ユーザーへの招待を許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="a8382-131">Allow or block invitations to B2B users from specific organizations</span></span>](/azure/active-directory/b2b/allow-deny-list)|
||<span data-ttu-id="a8382-132">匿名共有を防止します。</span><span class="sxs-lookup"><span data-stu-id="a8382-132">Prevent anonymous sharing.</span></span>|<span data-ttu-id="a8382-133">[[すべてのユーザー] リンクをオフにする](./share-limit-accidental-exposure.md#turn-off-anyone-links)</span><span class="sxs-lookup"><span data-stu-id="a8382-133">[Turn off Anyone links](./share-limit-accidental-exposure.md#turn-off-anyone-links)</span></span>|
||<span data-ttu-id="a8382-134">匿名アクセス リンクのアクセス許可を制御します。</span><span class="sxs-lookup"><span data-stu-id="a8382-134">Control the permissions for anonymous access links.</span></span>|<span data-ttu-id="a8382-135">[[ユーザー] リンクのリンクのアクセス許可を設定する](./best-practices-anonymous-sharing.md#set-link-permissions)</span><span class="sxs-lookup"><span data-stu-id="a8382-135">[Set link permissions for Anyone links](./best-practices-anonymous-sharing.md#set-link-permissions)</span></span>|
||<span data-ttu-id="a8382-136">匿名共有リンクの有効期限を制御します。</span><span class="sxs-lookup"><span data-stu-id="a8382-136">Control the expiration of anonymous sharing links.</span></span>|<span data-ttu-id="a8382-137">[[すべてのユーザー] リンクの有効期限を設定する](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)</span><span class="sxs-lookup"><span data-stu-id="a8382-137">[Set an expiration date for Anyone links](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)</span></span>|
||<span data-ttu-id="a8382-138">既定では、ユーザーに表示される共有リンクの種類を制御します。</span><span class="sxs-lookup"><span data-stu-id="a8382-138">Control the type of sharing link shown to users by default.</span></span>|[<span data-ttu-id="a8382-139">サイトの既定のリンクの種類を変更する</span><span class="sxs-lookup"><span data-stu-id="a8382-139">Change the default link type for a site</span></span>](/sharepoint/change-default-sharing-link)|
||<span data-ttu-id="a8382-140">外部共有を特定のユーザーに制限します。</span><span class="sxs-lookup"><span data-stu-id="a8382-140">Limit external sharing to specific people.</span></span>|[<span data-ttu-id="a8382-141">外部共有を指定したセキュリティ グループに制限する</span><span class="sxs-lookup"><span data-stu-id="a8382-141">Limit external sharing to specified security groups</span></span>](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||<span data-ttu-id="a8382-142">情報の感度に基づいて、グループ、チーム、またはサイトへのゲスト アクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="a8382-142">Control guest access to a group, team, or site based on information sensitivity.</span></span>|[<span data-ttu-id="a8382-143">秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する</span><span class="sxs-lookup"><span data-stu-id="a8382-143">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](../compliance/sensitivity-labels-teams-groups-sites.md)|
||<span data-ttu-id="a8382-144">共有オプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a8382-144">Turn off sharing options.</span></span>|[<span data-ttu-id="a8382-145">Microsoft 365 の共有を制限する</span><span class="sxs-lookup"><span data-stu-id="a8382-145">Limit sharing in Microsoft 365</span></span>](./microsoft-365-limit-sharing.md)|
|<span data-ttu-id="a8382-146">ユーザーの管理</span><span class="sxs-lookup"><span data-stu-id="a8382-146">User management</span></span>|||
||<span data-ttu-id="a8382-147">チームとグループのメンバーシップを定期的に確認します。</span><span class="sxs-lookup"><span data-stu-id="a8382-147">Review team and group membership on a regular basis.</span></span>|[<span data-ttu-id="a8382-148">Azure ADレビューとは?</span><span class="sxs-lookup"><span data-stu-id="a8382-148">What are Azure AD access reviews?</span></span>](/azure/active-directory/governance/access-reviews-overview)|
||<span data-ttu-id="a8382-149">グループとチームへのアクセス管理を自動化します。</span><span class="sxs-lookup"><span data-stu-id="a8382-149">Automate access management to groups and teams.</span></span>|[<span data-ttu-id="a8382-150">Azure のライセンスADとは?</span><span class="sxs-lookup"><span data-stu-id="a8382-150">What is Azure AD entitlement management?</span></span>](/azure/active-directory/governance/entitlement-management-overview)|
||<span data-ttu-id="a8382-151">ユーザーによるプライベート チャネルの作成を許可またはブロックTeams。</span><span class="sxs-lookup"><span data-stu-id="a8382-151">Allow or block people from creating private channels in Teams.</span></span>|[<span data-ttu-id="a8382-152">プライベート チャネルのライフ サイクルを管理Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8382-152">Manage the life cycle of private channels in Microsoft Teams</span></span>](/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a><span data-ttu-id="a8382-153">メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="a8382-153">Membership</span></span>

<span data-ttu-id="a8382-154">チームとグループのメンバーシップは、所有者によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="a8382-154">Membership of teams and groups is controlled by owners.</span></span> <span data-ttu-id="a8382-155">メンバーは他のユーザーを招待できますが、招待は承認のために所有者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="a8382-155">Members can invite others, but the invitations are sent to owners for approval.</span></span> <span data-ttu-id="a8382-156">パブリック チームとグループは組織内の誰でも見つけられますが、プライベート チームとグループを検出できるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="a8382-156">While public teams and groups are discoverable by anyone in the organization, you can control whether private teams and groups are discoverable:</span></span>

- [<span data-ttu-id="a8382-157">プライベート チームの検出を管理Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8382-157">Manage discovery of private teams in Microsoft Teams</span></span>](/microsoftteams/manage-discovery-of-private-teams)

<span data-ttu-id="a8382-158">グループまたはチームのメンバーシップは、部署などの一部の条件に基づいて動的に管理できます。</span><span class="sxs-lookup"><span data-stu-id="a8382-158">You can manage membership of a group or team dynamically based on some criteria, such as department.</span></span> <span data-ttu-id="a8382-159">この場合、メンバーと所有者はチームにユーザーを招待できません。</span><span class="sxs-lookup"><span data-stu-id="a8382-159">In this case, members and owners cannot invite people to the team.</span></span> <span data-ttu-id="a8382-160">動的グループは、グループ内で定義したメタデータAzure Active Directoryグループのメンバーを制御します。</span><span class="sxs-lookup"><span data-stu-id="a8382-160">Dynamic groups uses metadata that you define in Azure Active Directory to control who is a member of the group.</span></span> <span data-ttu-id="a8382-161">使用しているメタデータが完全で、メタデータが正しくないと、ユーザーがグループから抜け出したり、正しくないユーザーが追加される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a8382-161">Be sure the metadata that you're using is complete and up to date as incorrect metadata can lead to users being left out of groups or incorrect users being added.</span></span>

- [<span data-ttu-id="a8382-162">グループ内で動的グループを作成または更新Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a8382-162">Create or update a dynamic group in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-create-rule)

<span data-ttu-id="a8382-163">SharePointサイトでは、グループまたはチームのメンバーシップとは別に、所有者、メンバー、および訪問者を追加できます。</span><span class="sxs-lookup"><span data-stu-id="a8382-163">SharePoint sites provide the ability to add owners, members, and visitors apart from group or team membership.</span></span> <span data-ttu-id="a8382-164">要件に応じて、ユーザーをサイトに招待できるユーザーを制限できます。</span><span class="sxs-lookup"><span data-stu-id="a8382-164">Depending on your requirements, you may want to restrict who can invite people to the site.</span></span> <span data-ttu-id="a8382-165">また、特定のサイト内の情報の感度に応じて、ファイルとフォルダーを共有できるユーザーを制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="a8382-165">Also, depending on the sensitivity of the information in a given site, you may want to restrict who can share files and folder.</span></span> <span data-ttu-id="a8382-166">これらの制限は、チーム、グループ、またはサイトの所有者によって構成されます。</span><span class="sxs-lookup"><span data-stu-id="a8382-166">These restrictions are configured by the team, group, or site owner:</span></span>

- [<span data-ttu-id="a8382-167">アクセス要求の設定と管理</span><span class="sxs-lookup"><span data-stu-id="a8382-167">Set up and manage access requests</span></span>](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a><span data-ttu-id="a8382-168">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="a8382-168">Conditional access</span></span>

<span data-ttu-id="a8382-169">このMicrosoft 365、組織内外の両方のユーザーに多要素認証を要求できます。</span><span class="sxs-lookup"><span data-stu-id="a8382-169">With Microsoft 365, you can require multi-factor authentication for both people inside and outside your organization.</span></span> <span data-ttu-id="a8382-170">ユーザーに認証の第 2 の要素を求めるメッセージが表示される状況には、多くのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="a8382-170">There are many options for the circumstances when people are prompted for a second factor of authentication.</span></span> <span data-ttu-id="a8382-171">組織に多要素認証を展開することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a8382-171">We highly recommend that you deploy multi-factor authentication for your organization:</span></span>

- [<span data-ttu-id="a8382-172">Azure AD 多要素認証</span><span class="sxs-lookup"><span data-stu-id="a8382-172">Azure AD Multi-Factor Authentication</span></span>](/azure/active-directory/authentication/concept-mfa-howitworks)

<span data-ttu-id="a8382-173">一部のグループやチームに機密情報がある場合は、グループまたはチームの機密ラベルに基づいてデバイス管理ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="a8382-173">If you have sensitive information in some of your groups and teams, you can enforce device management policies based on a group or team's sensitivity label.</span></span> <span data-ttu-id="a8382-174">管理されていないデバイスからのアクセスを完全にブロックするか、制限付き Web アクセスのみを許可できます。</span><span class="sxs-lookup"><span data-stu-id="a8382-174">You can block access entirely from unmanaged devices, or allow limited, web only access:</span></span>

- [<span data-ttu-id="a8382-175">秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する</span><span class="sxs-lookup"><span data-stu-id="a8382-175">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](../compliance/sensitivity-labels-teams-groups-sites.md)

<span data-ttu-id="a8382-176">このSharePoint、指定したネットワークの場所からのサイトへのアクセスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="a8382-176">In SharePoint, you can restrict access to sites from specified network locations.</span></span>

- [<span data-ttu-id="a8382-177">ネットワークの場所に基づいて SharePoint と OneDrive のデータへのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="a8382-177">Control access to SharePoint and OneDrive data based on network location</span></span>](/sharepoint/control-access-based-on-network-location)


<span data-ttu-id="a8382-178">追加情報:</span><span class="sxs-lookup"><span data-stu-id="a8382-178">Additional resources:</span></span>

- [<span data-ttu-id="a8382-179">条件付きアクセスの展開を計画する</span><span class="sxs-lookup"><span data-stu-id="a8382-179">Plan a Conditional Access deployment</span></span>](/azure/active-directory/conditional-access/plan-conditional-access)

- [<span data-ttu-id="a8382-180">Microsoft Intune概要</span><span class="sxs-lookup"><span data-stu-id="a8382-180">Microsoft Intune overview</span></span>](/mem/intune/fundamentals/what-is-intune)

- [<span data-ttu-id="a8382-181">管理SharePointデバイスからのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="a8382-181">Control SharePoint access from unmanaged devices</span></span>](/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a><span data-ttu-id="a8382-182">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="a8382-182">Guest access</span></span>

<span data-ttu-id="a8382-183">電子メール アドレスのドメインに基づいてゲストを制限できます。</span><span class="sxs-lookup"><span data-stu-id="a8382-183">You can restrict guests based on the domain of their email address.</span></span> <span data-ttu-id="a8382-184">SharePointは、組織全体およびサイト固有のドメイン制限設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="a8382-184">SharePoint offers organization-wide and site-specific domain restriction settings.</span></span> <span data-ttu-id="a8382-185">グループとグループTeams Azure サーバーでドメイン許可リストと拒否リストを使用AD。</span><span class="sxs-lookup"><span data-stu-id="a8382-185">Groups and Teams use the domain allow and deny lists in Azure AD.</span></span> <span data-ttu-id="a8382-186">望ましくない共有を避け、一貫性のあるユーザー エクスペリエンスを確保するために、両方の設定を必ず構成してください。</span><span class="sxs-lookup"><span data-stu-id="a8382-186">Be sure to configure both settings to avoid unwanted sharing and ensure a consistent user experience:</span></span>

- [<span data-ttu-id="a8382-187">ドメイン別の SharePoint および OneDrive コンテンツの共有を制限する</span><span class="sxs-lookup"><span data-stu-id="a8382-187">Restrict sharing of SharePoint and OneDrive content by domain</span></span>](/sharepoint/restricted-domains-sharing)

- [<span data-ttu-id="a8382-188">特定の組織からの B2B ユーザーへの招待を許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="a8382-188">Allow or block invitations to B2B users from specific organizations</span></span>](/azure/active-directory/b2b/allow-deny-list)

<span data-ttu-id="a8382-189">Microsoft 365リンクを使用して、ファイルとフォルダーの匿名共有 *を* 許可します。</span><span class="sxs-lookup"><span data-stu-id="a8382-189">Microsoft 365 allows anonymous sharing of files and folders by using *Anyone* sharing links.</span></span> <span data-ttu-id="a8382-190">*リンク* は誰でも転送可能で、リンクを持つユーザーは共有アイテムにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a8382-190">*Anyone* links can be forwarded and anyone with the link can access the shared item.</span></span> <span data-ttu-id="a8382-191">データの感度に応じて、リンクを完全にオフにしたり、リンクのアクセス許可を読み取り専用に制限したり、そのリンクの有効期限を設定したりなど、すべてのユーザーのリンクの使用方法を管理する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="a8382-191">Depending on the sensitivity of your data, consider governing how *Anyone* links are used - including turning them off entirely, restricting link permissions to read-only, or setting an expiration time for them:</span></span>

- <span data-ttu-id="a8382-192">[[すべてのユーザー] リンクをオフにする](./share-limit-accidental-exposure.md#turn-off-anyone-links)</span><span class="sxs-lookup"><span data-stu-id="a8382-192">[Turn off Anyone links](./share-limit-accidental-exposure.md#turn-off-anyone-links)</span></span>

- <span data-ttu-id="a8382-193">[[ユーザー] リンクのリンクのアクセス許可を設定する](./best-practices-anonymous-sharing.md#set-link-permissions)</span><span class="sxs-lookup"><span data-stu-id="a8382-193">[Set link permissions for Anyone links](./best-practices-anonymous-sharing.md#set-link-permissions)</span></span>

- <span data-ttu-id="a8382-194">[[すべてのユーザー] リンクの有効期限を設定する](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)</span><span class="sxs-lookup"><span data-stu-id="a8382-194">[Set an expiration date for Anyone links](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)</span></span>

<span data-ttu-id="a8382-195">ファイルまたはフォルダーを共有する場合、ユーザーは複数のリンクの種類から選択できます。</span><span class="sxs-lookup"><span data-stu-id="a8382-195">When sharing files or folders, users have several link types to choose from.</span></span> <span data-ttu-id="a8382-196">不適切な共有が誤って発生するリスクを軽減するために、ユーザーが共有するときに表示される既定のリンクの種類を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a8382-196">To reduce the risk of accidental inappropriate sharing, you can change the default link type presented to users when they share.</span></span> <span data-ttu-id="a8382-197">たとえば、匿名アクセスを許可する[すべてのユーザー] リンクから[組織内のユーザー] リンクに既定値を変更すると、機密情報の望ましくない外部共有のリスクが軽減されます。</span><span class="sxs-lookup"><span data-stu-id="a8382-197">For example, changing the default from *Anyone* links - which allow anonymous access - to *People in your organization* links can reduce the risk of unwanted external sharing of sensitive information:</span></span>

- [<span data-ttu-id="a8382-198">サイトの既定のリンクの種類を変更する</span><span class="sxs-lookup"><span data-stu-id="a8382-198">Change the default link type for a site</span></span>](/sharepoint/change-default-sharing-link)

<span data-ttu-id="a8382-199">組織にゲストと共有する必要がある機密データがあるが、不適切な共有が懸念されている場合は、ファイルとフォルダーの外部共有を指定したセキュリティ グループのメンバーに制限できます。</span><span class="sxs-lookup"><span data-stu-id="a8382-199">If your organization has sensitive data that you need to share with guests, but you're concerned about inappropriate sharing, you can limit external sharing of files and folders to the members of specified security groups.</span></span> <span data-ttu-id="a8382-200">この方法で、外部での共有を特定のユーザー グループに制限したり、セキュリティ グループに追加する前に、適切な外部共有に関するトレーニングをユーザーに要求することができます。</span><span class="sxs-lookup"><span data-stu-id="a8382-200">In this way, you can restrict sharing externally to a specific group of people, or require your users to take training around appropriate external sharing before adding them to the security group:</span></span>

- [<span data-ttu-id="a8382-201">外部共有を指定したセキュリティ グループに制限する</span><span class="sxs-lookup"><span data-stu-id="a8382-201">Limit external sharing to specified security groups</span></span>](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

<span data-ttu-id="a8382-202">グループとグループTeams、ゲスト アクセスを許可または拒否する組織レベルの設定があります。</span><span class="sxs-lookup"><span data-stu-id="a8382-202">Groups and Teams have organization-level settings that allow or deny guest access.</span></span> <span data-ttu-id="a8382-203">[Microsoft PowerShell を使用](per-group-guest-access.md)して、特定のチームまたはグループへのゲスト アクセスを制限することができますが、これを行う際には、感度ラベルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a8382-203">While you can [restrict guest access to specific teams or groups by using Microsoft PowerShell](per-group-guest-access.md), we recommend doing this by means of a sensitivity label.</span></span> <span data-ttu-id="a8382-204">感度ラベルを使用すると、適用されたラベルに基づいてゲスト アクセスを自動的に許可または拒否できます。</span><span class="sxs-lookup"><span data-stu-id="a8382-204">With sensitivity labels you can automatically allow or deny guest access based on the label applied:</span></span>

- [<span data-ttu-id="a8382-205">秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する</span><span class="sxs-lookup"><span data-stu-id="a8382-205">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](../compliance/sensitivity-labels-teams-groups-sites.md)

<span data-ttu-id="a8382-206">グループやチームにゲストを頻繁に招待する環境では、定期的にスケジュールされたゲスト アクセス レビューの設定を検討してください。</span><span class="sxs-lookup"><span data-stu-id="a8382-206">In an environment where you frequently invite guests to groups and teams, consider setting up regularly scheduled guest access reviews.</span></span> <span data-ttu-id="a8382-207">所有者は、グループとチームのゲストを確認し、アクセスを承認または拒否するように求めるメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="a8382-207">Owners can be prompted to review guests in their groups and teams and approve or deny access.</span></span>

- [<span data-ttu-id="a8382-208">ゲスト アクセス レビューを設定する</span><span class="sxs-lookup"><span data-stu-id="a8382-208">Set up guest access reviews</span></span>](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

<span data-ttu-id="a8382-209">Microsoft 365は、情報を共有するさまざまな方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="a8382-209">Microsoft 365 offers many different methods of sharing information.</span></span> <span data-ttu-id="a8382-210">機密情報を持ち、共有方法を制限する場合は、共有を制限するためのオプションを確認します。</span><span class="sxs-lookup"><span data-stu-id="a8382-210">If you have sensitive information and you want to restrict how it's shared, review the options for limiting sharing:</span></span>

- [<span data-ttu-id="a8382-211">Microsoft 365 の共有を制限する</span><span class="sxs-lookup"><span data-stu-id="a8382-211">Limit sharing in Microsoft 365</span></span>](./microsoft-365-limit-sharing.md)

<span data-ttu-id="a8382-212">追加情報:</span><span class="sxs-lookup"><span data-stu-id="a8382-212">Additional resources:</span></span>

- [<span data-ttu-id="a8382-213">Microsoft 365 を使用してセキュリティで保護された共同作業を設定する</span><span class="sxs-lookup"><span data-stu-id="a8382-213">Set up secure collaboration with Microsoft 365</span></span>](./setup-secure-collaboration-with-teams.md)

- [<span data-ttu-id="a8382-214">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="a8382-214">Best practices for sharing files and folders with unauthenticated users</span></span>](./best-practices-anonymous-sharing.md)

- [<span data-ttu-id="a8382-215">組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する</span><span class="sxs-lookup"><span data-stu-id="a8382-215">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)

- [<span data-ttu-id="a8382-216">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="a8382-216">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

- [<span data-ttu-id="a8382-217">B2B の外部コラボレーションを有効にしてゲストを招待できるユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="a8382-217">Enable B2B external collaboration and manage who can invite guests</span></span>](/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a><span data-ttu-id="a8382-218">ユーザーの管理</span><span class="sxs-lookup"><span data-stu-id="a8382-218">User management</span></span>

<span data-ttu-id="a8382-219">グループとチームが組織内で進化するにつれて、チームとグループのメンバーシップを定期的に確認する方法をお試しください。</span><span class="sxs-lookup"><span data-stu-id="a8382-219">As groups and teams evolve in your organization, a good practice is to review team and group membership on a regular basis.</span></span> <span data-ttu-id="a8382-220">これは、メンバーシップが変更されたチームやグループ、機密情報を含むチーム、またはゲストを含むグループに特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a8382-220">This may be particularly useful for teams and groups with a changing membership, those that contain sensitive information, or those that include guests.</span></span> <span data-ttu-id="a8382-221">これらのチームとグループのアクセス レビューを設定する方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="a8382-221">Consider setting up access reviews for these teams and groups:</span></span>

- [<span data-ttu-id="a8382-222">Azure ADレビューとは?</span><span class="sxs-lookup"><span data-stu-id="a8382-222">What are Azure AD access reviews?</span></span>](/azure/active-directory/governance/access-reviews-overview)

<span data-ttu-id="a8382-223">多くの組織は、他の組織や主要ベンダーとビジネス パートナーシップを結び、詳細に共同作業を行っています。</span><span class="sxs-lookup"><span data-stu-id="a8382-223">Many organizations have business partnerships with other organizations or key vendors with whom they collaborate in depth.</span></span> <span data-ttu-id="a8382-224">これらのシナリオでは、ユーザー管理とリソースへのアクセスを管理するには困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a8382-224">User management and access to resources can be challenging to manage in these scenarios.</span></span> <span data-ttu-id="a8382-225">ユーザー管理タスクの一部を自動化し、一部をパートナー組織に移行する場合も検討してください。</span><span class="sxs-lookup"><span data-stu-id="a8382-225">Consider automating some of the user management tasks and even transitioning some of them to your partner organization:</span></span>

- [<span data-ttu-id="a8382-226">Azure のライセンスADとは?</span><span class="sxs-lookup"><span data-stu-id="a8382-226">What is Azure AD entitlement management?</span></span>](/azure/active-directory/governance/entitlement-management-overview)

<span data-ttu-id="a8382-227">プライベート チャネルは、Teamsメンバーのサブセット間のスコープ付き会話とファイル共有を可能にします。</span><span class="sxs-lookup"><span data-stu-id="a8382-227">Private channels in Teams allow for scoped conversations and file sharing between a subset of team members.</span></span> <span data-ttu-id="a8382-228">特定のビジネス ニーズに応じて、この機能を許可またはブロックできます。</span><span class="sxs-lookup"><span data-stu-id="a8382-228">Depending on your specific business needs, you may want to allow or block this capability.</span></span>

- [<span data-ttu-id="a8382-229">Microsoft Teams のプライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="a8382-229">Private channels in Microsoft Teams</span></span>](/MicrosoftTeams/private-channels)

- [<span data-ttu-id="a8382-230">プライベート チャネルのライフ サイクルを管理Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8382-230">Manage the life cycle of private channels in Microsoft Teams</span></span>](/MicrosoftTeams/private-channels-life-cycle-management)

<span data-ttu-id="a8382-231">追加情報:</span><span class="sxs-lookup"><span data-stu-id="a8382-231">Additional resources:</span></span>

- [<span data-ttu-id="a8382-232">Azure Active DirectoryID ガバナンス</span><span class="sxs-lookup"><span data-stu-id="a8382-232">Azure Active Directory Identity Governance</span></span>](/azure/active-directory/governance)

## <a name="related-topics"></a><span data-ttu-id="a8382-233">関連項目</span><span class="sxs-lookup"><span data-stu-id="a8382-233">Related topics</span></span>

[<span data-ttu-id="a8382-234">コラボレーション ガバナンス計画のステップ バイ ステップ</span><span class="sxs-lookup"><span data-stu-id="a8382-234">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="a8382-235">コラボレーション ガバナンス 計画の作成</span><span class="sxs-lookup"><span data-stu-id="a8382-235">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="a8382-236">Microsoft Teams のセキュリティとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="a8382-236">Security and compliance in Microsoft Teams</span></span>](/microsoftteams/security-compliance-overview)

<span data-ttu-id="a8382-237">[[共有設定の管理] SharePoint](/sharepoint/turn-external-sharing-on-or-off)</span><span class="sxs-lookup"><span data-stu-id="a8382-237">[Manage sharing settings in SharePoint](/sharepoint/turn-external-sharing-on-or-off)</span></span>

[<span data-ttu-id="a8382-238">Yammer で外部ネットワークを作成して管理する</span><span class="sxs-lookup"><span data-stu-id="a8382-238">Create and manage an external network in Yammer</span></span>](/yammer/work-with-external-users/create-and-manage-an-external-network)

[<span data-ttu-id="a8382-239">3 層の保護を使って Teams を構成する</span><span class="sxs-lookup"><span data-stu-id="a8382-239">Configure Teams with three tiers of protection</span></span>](./configure-teams-three-tiers-protection.md)