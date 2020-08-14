---
title: Microsoft 365 グループ、Teams、SharePoint でのアクセスの管理
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365 グループ、Teams、SharePoint でのアクセス管理について説明します。
ms.openlocfilehash: 8b58016ffa421328e3c1442d4ed2364f2eedc37b
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662723"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a><span data-ttu-id="7f609-103">Microsoft 365 グループ、Teams、SharePoint でのアクセスの管理</span><span class="sxs-lookup"><span data-stu-id="7f609-103">Governing access in Microsoft 365 groups, Teams, and SharePoint</span></span>

<span data-ttu-id="7f609-104">ユーザーがグループ、teams、および SharePoint でリソースにアクセスする方法を制御できるようになるコントロールは多数あります。</span><span class="sxs-lookup"><span data-stu-id="7f609-104">There are many controls that enable you to govern how people access resources in groups, teams, and SharePoint.</span></span> <span data-ttu-id="7f609-105">これらのオプションを確認し、ビジネスニーズへの対応方法、データの機密性、およびユーザーが共同作業する必要のあるユーザーの範囲を検討してください。</span><span class="sxs-lookup"><span data-stu-id="7f609-105">Review these options and consider how they map to your business needs, the sensitivity of your data, and the scope of people that your users need to collaborate with.</span></span>

<span data-ttu-id="7f609-106">次の表に、Microsoft 365 で利用可能なアクセス制御のクイックリファレンスを示します。</span><span class="sxs-lookup"><span data-stu-id="7f609-106">The following table provides a quick reference for the access controls available in Microsoft 365.</span></span> <span data-ttu-id="7f609-107">詳細については、以下のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f609-107">Further information is provided in the following sections.</span></span>

|<span data-ttu-id="7f609-108">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="7f609-108">Category</span></span>|<span data-ttu-id="7f609-109">説明</span><span class="sxs-lookup"><span data-stu-id="7f609-109">Description</span></span>|<span data-ttu-id="7f609-110">リファレンス</span><span class="sxs-lookup"><span data-stu-id="7f609-110">Reference</span></span>|
|:-------|:----------|:--------|
|<span data-ttu-id="7f609-111">メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="7f609-111">Membership</span></span>|||
||<span data-ttu-id="7f609-112">プライベートチームの検出</span><span class="sxs-lookup"><span data-stu-id="7f609-112">Discovery of private teams</span></span>|[<span data-ttu-id="7f609-113">Microsoft Teams でプライベートチームの検出を管理する</span><span class="sxs-lookup"><span data-stu-id="7f609-113">Manage discovery of private teams in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||<span data-ttu-id="7f609-114">ルールに基づく動的なグループメンバーシップ</span><span class="sxs-lookup"><span data-stu-id="7f609-114">Dynamic group membership based on rules</span></span>|[<span data-ttu-id="7f609-115">Azure Active Directory で動的グループを作成または更新する</span><span class="sxs-lookup"><span data-stu-id="7f609-115">Create or update a dynamic group in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||<span data-ttu-id="7f609-116">ファイル、フォルダー、サイトを共有できるユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="7f609-116">Control who can share files, folders, and sites.</span></span>|[<span data-ttu-id="7f609-117">アクセス要求の設定と管理</span><span class="sxs-lookup"><span data-stu-id="7f609-117">Set up and manage access requests</span></span>](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|<span data-ttu-id="7f609-118">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="7f609-118">Conditional access</span></span>|||
||<span data-ttu-id="7f609-119">多要素認証</span><span class="sxs-lookup"><span data-stu-id="7f609-119">Multi-Factor Authentication</span></span>|[<span data-ttu-id="7f609-120">Azure 多要素認証</span><span class="sxs-lookup"><span data-stu-id="7f609-120">Azure Multi-Factor Authentication</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||<span data-ttu-id="7f609-121">グループ、チーム、またはサイトの秘密度に基づいてデバイスアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="7f609-121">Control device access based on group, team, or site sensitivity.</span></span>|[<span data-ttu-id="7f609-122">秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する</span><span class="sxs-lookup"><span data-stu-id="7f609-122">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||<span data-ttu-id="7f609-123">管理されていないデバイスのサイトアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="7f609-123">Limit site access for unmanaged devices.</span></span>|[<span data-ttu-id="7f609-124">非管理対象デバイスから SharePoint へのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="7f609-124">Control SharePoint access from unmanaged devices</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||<span data-ttu-id="7f609-125">場所に基づいてサイトアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="7f609-125">Control site access based on location</span></span>|[<span data-ttu-id="7f609-126">ネットワークの場所に基づいて SharePoint と OneDrive のデータへのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="7f609-126">Control access to SharePoint and OneDrive data based on network location</span></span>](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|<span data-ttu-id="7f609-127">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="7f609-127">Guest access</span></span>|||
||<span data-ttu-id="7f609-128">指定したドメインからの SharePoint の共有を許可または禁止します。</span><span class="sxs-lookup"><span data-stu-id="7f609-128">Allow or block SharePoint sharing from specified domains.</span></span>|[<span data-ttu-id="7f609-129">ドメイン別の SharePoint および OneDrive コンテンツの共有を制限する</span><span class="sxs-lookup"><span data-stu-id="7f609-129">Restrict sharing of SharePoint and OneDrive content by domain</span></span>](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||<span data-ttu-id="7f609-130">指定したドメインからのチームまたはグループメンバーシップを許可または禁止します。</span><span class="sxs-lookup"><span data-stu-id="7f609-130">Allow or block team or group membership from specified domains.</span></span>|[<span data-ttu-id="7f609-131">特定の組織からの B2B ユーザーへの招待を許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="7f609-131">Allow or block invitations to B2B users from specific organizations</span></span>](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||<span data-ttu-id="7f609-132">匿名での共有を禁止します。</span><span class="sxs-lookup"><span data-stu-id="7f609-132">Prevent anonymous sharing.</span></span>|<span data-ttu-id="7f609-133">[[すべてのユーザー] リンクをオフにする](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)</span><span class="sxs-lookup"><span data-stu-id="7f609-133">[Turn off Anyone links](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)</span></span>|
||<span data-ttu-id="7f609-134">匿名アクセスリンクのアクセス許可を制御します。</span><span class="sxs-lookup"><span data-stu-id="7f609-134">Control the permissions for anonymous access links.</span></span>|[<span data-ttu-id="7f609-135">すべてのリンクのリンクのアクセス許可を設定する</span><span class="sxs-lookup"><span data-stu-id="7f609-135">Set link permissions for Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||<span data-ttu-id="7f609-136">匿名の共有リンクの有効期限を制御します。</span><span class="sxs-lookup"><span data-stu-id="7f609-136">Control the expiration of anonymous sharing links.</span></span>|<span data-ttu-id="7f609-137">[[すべてのユーザー] リンクの有効期限を設定する](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)</span><span class="sxs-lookup"><span data-stu-id="7f609-137">[Set an expiration date for Anyone links](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)</span></span>|
||<span data-ttu-id="7f609-138">既定でユーザーに表示される共有リンクの種類を制御します。</span><span class="sxs-lookup"><span data-stu-id="7f609-138">Control the type of sharing link shown to users by default.</span></span>|[<span data-ttu-id="7f609-139">サイトの既定のリンクの種類を変更する</span><span class="sxs-lookup"><span data-stu-id="7f609-139">Change the default link type for a site</span></span>](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||<span data-ttu-id="7f609-140">特定のユーザーに対する外部共有を制限します。</span><span class="sxs-lookup"><span data-stu-id="7f609-140">Limit external sharing to specific people.</span></span>|[<span data-ttu-id="7f609-141">指定したセキュリティグループへの外部共有を制限する</span><span class="sxs-lookup"><span data-stu-id="7f609-141">Limit external sharing to specified security groups</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||<span data-ttu-id="7f609-142">情報の秘密度に基づいて、グループ、チーム、またはサイトへのゲストアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="7f609-142">Control guest access to a group, team, or site based on information sensitivity.</span></span>|[<span data-ttu-id="7f609-143">秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する</span><span class="sxs-lookup"><span data-stu-id="7f609-143">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||<span data-ttu-id="7f609-144">共有オプションをオフにします。</span><span class="sxs-lookup"><span data-stu-id="7f609-144">Turn off sharing options.</span></span>|[<span data-ttu-id="7f609-145">Microsoft 365 の共有を制限する</span><span class="sxs-lookup"><span data-stu-id="7f609-145">Limit sharing in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|<span data-ttu-id="7f609-146">ユーザーの管理</span><span class="sxs-lookup"><span data-stu-id="7f609-146">User management</span></span>|||
||<span data-ttu-id="7f609-147">チームおよびグループのメンバーシップを定期的に確認します。</span><span class="sxs-lookup"><span data-stu-id="7f609-147">Review team and group membership on a regular basis.</span></span>|[<span data-ttu-id="7f609-148">Azure AD のアクセスレビューとは</span><span class="sxs-lookup"><span data-stu-id="7f609-148">What are Azure AD access reviews?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||<span data-ttu-id="7f609-149">グループとチームへのアクセス管理を自動化します。</span><span class="sxs-lookup"><span data-stu-id="7f609-149">Automate access management to groups and teams.</span></span>|[<span data-ttu-id="7f609-150">Azure AD 受給管理とは</span><span class="sxs-lookup"><span data-stu-id="7f609-150">What is Azure AD entitlement management?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||<span data-ttu-id="7f609-151">ユーザーが Teams でプライベートチャネルを作成することを許可または禁止します。</span><span class="sxs-lookup"><span data-stu-id="7f609-151">Allow or block people from creating private channels in Teams.</span></span>|[<span data-ttu-id="7f609-152">Microsoft Teams のプライベートチャネルのライフサイクルを管理する</span><span class="sxs-lookup"><span data-stu-id="7f609-152">Manage the life cycle of private channels in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a><span data-ttu-id="7f609-153">メンバーシップ</span><span class="sxs-lookup"><span data-stu-id="7f609-153">Membership</span></span>

<span data-ttu-id="7f609-154">Teams およびグループのメンバーシップは、所有者によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="7f609-154">Membership of teams and groups is controlled by owners.</span></span> <span data-ttu-id="7f609-155">メンバーは他のユーザーを招待できますが、承認のために招待状が所有者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="7f609-155">Members can invite others, but the invitations are sent to owners for approval.</span></span> <span data-ttu-id="7f609-156">パブリックチームとグループは、組織内のすべてのユーザーが検出できますが、プライベートチームとグループを検出可能にするかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="7f609-156">While public teams and groups are discoverable by anyone in the organization, you can control whether private teams and groups are discoverable:</span></span>

- [<span data-ttu-id="7f609-157">Microsoft Teams でプライベートチームの検出を管理する</span><span class="sxs-lookup"><span data-stu-id="7f609-157">Manage discovery of private teams in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

<span data-ttu-id="7f609-158">部署などの条件に基づいて、グループまたはチームのメンバーシップを動的に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="7f609-158">You can manage membership of a group or team dynamically based on some criteria, such as department.</span></span> <span data-ttu-id="7f609-159">この場合、メンバーと所有者はチームに人を招待できません。</span><span class="sxs-lookup"><span data-stu-id="7f609-159">In this case, members and owners cannot invite people to the team.</span></span>

- [<span data-ttu-id="7f609-160">Azure Active Directory で動的グループを作成または更新する</span><span class="sxs-lookup"><span data-stu-id="7f609-160">Create or update a dynamic group in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

<span data-ttu-id="7f609-161">SharePoint サイトには、グループまたはチームメンバーシップとの間で所有者、メンバー、および訪問者を追加する機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="7f609-161">SharePoint sites provide the ability to add owners, members, and visitors apart from group or team membership.</span></span> <span data-ttu-id="7f609-162">要件に応じて、ユーザーをサイトに招待できるユーザーを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="7f609-162">Depending on your requirements, you may want to restrict who can invite people to the site.</span></span> <span data-ttu-id="7f609-163">また、特定のサイトの情報の機密性に応じて、ファイルとフォルダーを共有できるユーザーを制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="7f609-163">Also, depending on the sensitivity of the information in a given site, you may want to restrict who can share files and folder.</span></span> <span data-ttu-id="7f609-164">これらの制限は、チーム、グループ、またはサイトの所有者によって構成されます。</span><span class="sxs-lookup"><span data-stu-id="7f609-164">These restrictions are configured by the team, group, or site owner:</span></span>

- [<span data-ttu-id="7f609-165">アクセス要求の設定と管理</span><span class="sxs-lookup"><span data-stu-id="7f609-165">Set up and manage access requests</span></span>](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a><span data-ttu-id="7f609-166">条件付きアクセス</span><span class="sxs-lookup"><span data-stu-id="7f609-166">Conditional access</span></span>

<span data-ttu-id="7f609-167">Microsoft 365 では、組織の内部および外部の両方のユーザーに多要素認証を要求できます。</span><span class="sxs-lookup"><span data-stu-id="7f609-167">With Microsoft 365, you can require multi-factor authentication for both people inside and outside your organization.</span></span> <span data-ttu-id="7f609-168">2番目の認証のためにユーザーにメッセージが表示される場合、さまざまな状況に対応するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="7f609-168">There are many options for the circumstances when people are prompted for a second factor of authentication.</span></span> <span data-ttu-id="7f609-169">組織には、多要素認証を展開することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f609-169">We highly recommend that you deploy multi-factor authentication for your organization:</span></span>

- [<span data-ttu-id="7f609-170">Azure 多要素認証</span><span class="sxs-lookup"><span data-stu-id="7f609-170">Azure Multi-Factor Authentication</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

<span data-ttu-id="7f609-171">一部のグループとチームに機密情報がある場合は、グループまたはチームの機密ラベルに基づいてデバイス管理ポリシーを適用できます。</span><span class="sxs-lookup"><span data-stu-id="7f609-171">If you have sensitive information in some of your groups and teams, you can enforce device management policies based on a group or team's sensitivity label.</span></span> <span data-ttu-id="7f609-172">管理されていないデバイスからのアクセスを完全にブロックしたり、制限された web のみのアクセスを許可したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="7f609-172">You can block access entirely from unmanaged devices, or allow limited, web only access:</span></span>

- [<span data-ttu-id="7f609-173">秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する</span><span class="sxs-lookup"><span data-stu-id="7f609-173">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

<span data-ttu-id="7f609-174">SharePoint では、指定したネットワークの場所からサイトへのアクセスを制限できます。</span><span class="sxs-lookup"><span data-stu-id="7f609-174">In SharePoint, you can restrict access to sites from specified network locations.</span></span>

- [<span data-ttu-id="7f609-175">ネットワークの場所に基づいて SharePoint と OneDrive のデータへのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="7f609-175">Control access to SharePoint and OneDrive data based on network location</span></span>](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


<span data-ttu-id="7f609-176">追加情報:</span><span class="sxs-lookup"><span data-stu-id="7f609-176">Additional resources:</span></span>

- [<span data-ttu-id="7f609-177">条件付きアクセスの展開を計画する</span><span class="sxs-lookup"><span data-stu-id="7f609-177">Plan a Conditional Access deployment</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [<span data-ttu-id="7f609-178">Microsoft Intune の概要</span><span class="sxs-lookup"><span data-stu-id="7f609-178">Microsoft Intune overview</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [<span data-ttu-id="7f609-179">非管理対象デバイスから SharePoint へのアクセスを制御する</span><span class="sxs-lookup"><span data-stu-id="7f609-179">Control SharePoint access from unmanaged devices</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a><span data-ttu-id="7f609-180">ゲスト アクセス</span><span class="sxs-lookup"><span data-stu-id="7f609-180">Guest access</span></span>

<span data-ttu-id="7f609-181">電子メールアドレスのドメインに基づいてゲストを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="7f609-181">You can restrict guests based on the domain of their email address.</span></span> <span data-ttu-id="7f609-182">SharePoint では、組織全体およびサイト固有のドメイン制限の設定を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="7f609-182">SharePoint offers organization-wide and site-specific domain restriction settings.</span></span> <span data-ttu-id="7f609-183">グループとチームは、Azure AD のドメインの許可リストと拒否リストを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f609-183">Groups and Teams use the domain allow and deny lists in Azure AD.</span></span> <span data-ttu-id="7f609-184">不要な共有を回避し、一貫したユーザー環境を確保するために、両方の設定を構成してください。</span><span class="sxs-lookup"><span data-stu-id="7f609-184">Be sure to configure both settings to avoid unwanted sharing and ensure a consistent user experience:</span></span>

- [<span data-ttu-id="7f609-185">ドメイン別の SharePoint および OneDrive コンテンツの共有を制限する</span><span class="sxs-lookup"><span data-stu-id="7f609-185">Restrict sharing of SharePoint and OneDrive content by domain</span></span>](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [<span data-ttu-id="7f609-186">特定の組織からの B2B ユーザーへの招待を許可またはブロックする</span><span class="sxs-lookup"><span data-stu-id="7f609-186">Allow or block invitations to B2B users from specific organizations</span></span>](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

<span data-ttu-id="7f609-187">Microsoft 365 では、 *すべて* の共有リンクを使用して、ファイルとフォルダーを匿名で共有できます。</span><span class="sxs-lookup"><span data-stu-id="7f609-187">Microsoft 365 allows anonymous sharing of files and folders by using *Anyone* sharing links.</span></span> <span data-ttu-id="7f609-188">*すべて* のリンクを転送でき、リンクを持つすべてのユーザーが共有アイテムにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="7f609-188">*Anyone* links can be forwarded and anyone with the link can access the shared item.</span></span> <span data-ttu-id="7f609-189">データの機密性に応じて、 *すべて* のリンクの使用方法を制御します。これには、完全にオフにしたり、リンクのアクセス許可を読み取り専用に制限したり、有効期限を設定したりすることも含まれます。</span><span class="sxs-lookup"><span data-stu-id="7f609-189">Depending on the sensitivity of your data, consider governing how *Anyone* links are used - including turning them off entirely, restricting link permissions to read-only, or setting an expiration time for them:</span></span>

- <span data-ttu-id="7f609-190">[[すべてのユーザー] リンクをオフにする](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)</span><span class="sxs-lookup"><span data-stu-id="7f609-190">[Turn off Anyone links](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)</span></span>

- [<span data-ttu-id="7f609-191">すべてのリンクのリンクのアクセス許可を設定する</span><span class="sxs-lookup"><span data-stu-id="7f609-191">Set link permissions for Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- <span data-ttu-id="7f609-192">[[すべてのユーザー] リンクの有効期限を設定する](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)</span><span class="sxs-lookup"><span data-stu-id="7f609-192">[Set an expiration date for Anyone links](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)</span></span>

<span data-ttu-id="7f609-193">ファイルまたはフォルダーを共有する場合、ユーザーはさまざまなリンクの種類を選択できます。</span><span class="sxs-lookup"><span data-stu-id="7f609-193">When sharing files or folders, users have several link types to choose from.</span></span> <span data-ttu-id="7f609-194">偶発的な適切でない共有の危険性を軽減するために、ユーザーが共有するときに表示される既定のリンクの種類を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="7f609-194">To reduce the risk of accidental inappropriate sharing, you can change the default link type presented to users when they share.</span></span> <span data-ttu-id="7f609-195">たとえば、*組織リンク内のユーザー*に匿名アクセスを許可する、[*すべて*のユーザー] リンクから既定の設定を変更すると、機密情報の不必要な外部共有のリスクを軽減できます。</span><span class="sxs-lookup"><span data-stu-id="7f609-195">For example, changing the default from *Anyone* links - which allow anonymous access - to *People in your organization* links can reduce the risk of unwanted external sharing of sensitive information:</span></span>

- [<span data-ttu-id="7f609-196">サイトの既定のリンクの種類を変更する</span><span class="sxs-lookup"><span data-stu-id="7f609-196">Change the default link type for a site</span></span>](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

<span data-ttu-id="7f609-197">組織に機密データがあり、ゲストと共有する必要があるが、不適切な共有について懸念している場合は、ファイルとフォルダーの外部共有を、指定したセキュリティグループのメンバーに制限できます。</span><span class="sxs-lookup"><span data-stu-id="7f609-197">If your organization has sensitive data that you need to share with guests, but you're concerned about inappropriate sharing, you can limit external sharing of files and folders to the members of specified security groups.</span></span> <span data-ttu-id="7f609-198">この方法では、特定のユーザーグループに対して外部共有を制限したり、ユーザーをセキュリティグループに追加する前に、適切な外部共有についてトレーニングを受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f609-198">In this way, you can restrict sharing externally to a specific group of people, or require your users to take training around appropriate external sharing before adding them to the security group:</span></span>

- [<span data-ttu-id="7f609-199">指定したセキュリティグループへの外部共有を制限する</span><span class="sxs-lookup"><span data-stu-id="7f609-199">Limit external sharing to specified security groups</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

<span data-ttu-id="7f609-200">グループとチームには、ゲストアクセスを許可または拒否する組織レベルの設定があります。</span><span class="sxs-lookup"><span data-stu-id="7f609-200">Groups and Teams have organization-level setting that allow or deny guest access.</span></span> <span data-ttu-id="7f609-201">[Microsoft PowerShell を使用して特定のチームまたはグループへのゲストアクセスを制限](per-group-guest-access.md)することができますが、これは機密ラベルを使用して行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f609-201">While you can [restrict guest access to specific teams or groups by using Microsoft PowerShell](per-group-guest-access.md), we recommend doing this by means of a sensitivity label.</span></span> <span data-ttu-id="7f609-202">機密ラベルを使用すると、適用されたラベルに基づいてゲストアクセスを自動的に許可または拒否することができます。</span><span class="sxs-lookup"><span data-stu-id="7f609-202">With sensitivity labels you can automatically allow or deny guest access based on the label applied:</span></span>

- [<span data-ttu-id="7f609-203">秘密度ラベルを使用して、Microsoft Teams、Microsoft 365 グループ、SharePoint サイトのコンテンツを保護する</span><span class="sxs-lookup"><span data-stu-id="7f609-203">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

<span data-ttu-id="7f609-204">Microsoft 365 では、さまざまな方法で情報を共有できます。</span><span class="sxs-lookup"><span data-stu-id="7f609-204">Microsoft 365 offers many different methods of sharing information.</span></span> <span data-ttu-id="7f609-205">機密情報があり、その共有方法を制限する場合は、共有を制限するためのオプションを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f609-205">If you have sensitive information and you want to restrict how it's shared, review the options for limiting sharing:</span></span>

- [<span data-ttu-id="7f609-206">Microsoft 365 の共有を制限する</span><span class="sxs-lookup"><span data-stu-id="7f609-206">Limit sharing in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

<span data-ttu-id="7f609-207">追加情報:</span><span class="sxs-lookup"><span data-stu-id="7f609-207">Additional resources:</span></span>

- [<span data-ttu-id="7f609-208">Microsoft 365 とセキュリティで保護された共同作業を設定する</span><span class="sxs-lookup"><span data-stu-id="7f609-208">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [<span data-ttu-id="7f609-209">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="7f609-209">Best practices for sharing files and folders with unauthenticated users</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [<span data-ttu-id="7f609-210">組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する</span><span class="sxs-lookup"><span data-stu-id="7f609-210">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [<span data-ttu-id="7f609-211">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="7f609-211">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [<span data-ttu-id="7f609-212">B2B 外部コラボレーションを有効にし、ゲストを招待できるユーザーを管理する</span><span class="sxs-lookup"><span data-stu-id="7f609-212">Enable B2B external collaboration and manage who can invite guests</span></span>](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a><span data-ttu-id="7f609-213">ユーザーの管理</span><span class="sxs-lookup"><span data-stu-id="7f609-213">User management</span></span>

<span data-ttu-id="7f609-214">組織でのグループとチームの発展と同様に、チームとグループのメンバーシップを定期的に確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f609-214">As groups and teams evolve in your organization, a good practice is to review team and group membership on a regular basis.</span></span> <span data-ttu-id="7f609-215">これは、変更されたメンバーシップを持つ teams やグループに対して、機密情報を含む、またはゲストを含むグループに対して特に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7f609-215">This may be particularly useful for teams and groups with a changing membership, those that contain sensitive information, or those that include guests.</span></span> <span data-ttu-id="7f609-216">これらのチームおよびグループのアクセスレビューを設定することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="7f609-216">Consider setting up access reviews for these teams and groups:</span></span>

- [<span data-ttu-id="7f609-217">Azure AD のアクセスレビューとは</span><span class="sxs-lookup"><span data-stu-id="7f609-217">What are Azure AD access reviews?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

<span data-ttu-id="7f609-218">多くの組織では、他の組織または重要なベンダーとのビジネスパートナーシップがあります。</span><span class="sxs-lookup"><span data-stu-id="7f609-218">Many organizations have business partnerships with other organizations or key vendors with whom they collaborate in depth.</span></span> <span data-ttu-id="7f609-219">ユーザー管理とリソースへのアクセスは、これらのシナリオで管理するのが困難な場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f609-219">User management and access to resources can be challenging to manage in these scenarios.</span></span> <span data-ttu-id="7f609-220">一部のユーザー管理タスクを自動化し、一部のユーザー管理タスクをパートナー組織に移行することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="7f609-220">Consider automating some of the user management tasks and even transitioning some of them to your partner organization:</span></span>

- [<span data-ttu-id="7f609-221">Azure AD 受給管理とは</span><span class="sxs-lookup"><span data-stu-id="7f609-221">What is Azure AD entitlement management?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

<span data-ttu-id="7f609-222">Teams のプライベートチャネルでは、チームメンバーのサブセット間でのスレッドの範囲指定とファイル共有が許可されます。</span><span class="sxs-lookup"><span data-stu-id="7f609-222">Private channels in Teams allow for scoped conversations and file sharing between a subset of team members.</span></span> <span data-ttu-id="7f609-223">特定のビジネスニーズに応じて、この機能を許可またはブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="7f609-223">Depending on your specific business needs, you may want to allow or block this capability.</span></span>

- [<span data-ttu-id="7f609-224">Microsoft Teams のプライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="7f609-224">Private channels in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [<span data-ttu-id="7f609-225">Microsoft Teams のプライベートチャネルのライフサイクルを管理する</span><span class="sxs-lookup"><span data-stu-id="7f609-225">Manage the life cycle of private channels in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

<span data-ttu-id="7f609-226">追加情報:</span><span class="sxs-lookup"><span data-stu-id="7f609-226">Additional resources:</span></span>

- [<span data-ttu-id="7f609-227">Azure Active Directory Id ガバナンス</span><span class="sxs-lookup"><span data-stu-id="7f609-227">Azure Active Directory Identity Governance</span></span>](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a><span data-ttu-id="7f609-228">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f609-228">Related topics</span></span>

[<span data-ttu-id="7f609-229">Microsoft Teams のセキュリティとコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="7f609-229">Security and compliance in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[<span data-ttu-id="7f609-230">SharePoint で共有設定を管理する</span><span class="sxs-lookup"><span data-stu-id="7f609-230">Manage sharing settings in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[<span data-ttu-id="7f609-231">Yammer で外部ネットワークを作成して管理する</span><span class="sxs-lookup"><span data-stu-id="7f609-231">Create and manage an external network in Yammer</span></span>](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[<span data-ttu-id="7f609-232">3 層の保護を使ってチームを構成する</span><span class="sxs-lookup"><span data-stu-id="7f609-232">Configure Teams with three tiers of protection</span></span>](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
