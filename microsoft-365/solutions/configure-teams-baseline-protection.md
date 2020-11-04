---
title: ベースライン保護を使用してチームを構成する
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: ベースライン レベルの保護を使用してチームを展開する方法について説明します。
ms.openlocfilehash: 76b60a61812c4d30884825b41ee7220d6686b58b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845302"
---
# <a name="configure-teams-with-baseline-protection"></a><span data-ttu-id="c7e87-103">ベースライン保護を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="c7e87-103">Configure teams with baseline protection</span></span>

<span data-ttu-id="c7e87-104">この記事では、ベースライン レベルの保護を使用してチームを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c7e87-104">In this article, we look at how to deploy teams with a baseline level of protection.</span></span> <span data-ttu-id="c7e87-105">このレベルでは、アクセス許可管理を強化し、過度な共有に対する基本的な保護を提供しながら、コラボレーションのための幅広いオプションをユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="c7e87-105">This level allows users a wide range of options for collaboration while enhancing permissions management and providing basic protection against oversharing.</span></span> <span data-ttu-id="c7e87-106">このレベルに推奨される保護には、ID とデバイス アクセス ポリシーとマルウェアに対する保護が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c7e87-106">Recommended protections for this level include identity and device access policies and protection against malware.</span></span> <span data-ttu-id="c7e87-107">さらに、必要に応じて条件付きアクセス ポリシーやデータ損失保護を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="c7e87-107">Additionally, you can apply conditional access policies and data loss protections as needed.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="c7e87-108">初期保護</span><span class="sxs-lookup"><span data-stu-id="c7e87-108">Initial protections</span></span>

<span data-ttu-id="c7e87-109">最初のステップとして、基本的な ID とデバイス アクセス ポリシーの構成をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-109">As a first step, we recommend that you configure basic identity and device-access policies.</span></span> <span data-ttu-id="c7e87-110">詳細については、「[Policy recommendations for securing Teams chats, groups, and files (Teams チャット、グループ、ファイルをセキュリティで保護するためのポリシーの推奨事項)](../security/office-365-security/teams-access-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c7e87-110">See [Policy recommendations for securing Teams chats, groups, and files](../security/office-365-security/teams-access-policies.md) for details.</span></span>

<span data-ttu-id="c7e87-111">また、ドキュメント、添付ファイル、リンクなどに含まれているマルウェアから保護するために、基本的な Defender for Office 365 機能をオンにすることもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-111">We also recommend turning on basic Defender for Office 365 features to guard against malware in documents, attachments, and links.</span></span> <span data-ttu-id="c7e87-112">次の表の各オプションをオンにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-112">We recommend turning on each of the options in the following table.</span></span>

|<span data-ttu-id="c7e87-113">オプション</span><span class="sxs-lookup"><span data-stu-id="c7e87-113">Option</span></span>|<span data-ttu-id="c7e87-114">情報</span><span class="sxs-lookup"><span data-stu-id="c7e87-114">Information</span></span>|
|:------|:-----------|
|<span data-ttu-id="c7e87-115">SPO、OneDrive、Teams 用の安全な添付ファイル機能</span><span class="sxs-lookup"><span data-stu-id="c7e87-115">Safe Attachments for SPO, OneDrive and Teams</span></span>|[<span data-ttu-id="c7e87-116">添付ファイル保護</span><span class="sxs-lookup"><span data-stu-id="c7e87-116">Safe Attachments</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments)<br>[<span data-ttu-id="c7e87-117">Defender for Office 365 - SharePoint、OneDrive、Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c7e87-117">Defender for Office 365 - SharePoint, OneDrive, and Microsoft Teams</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)|
|<span data-ttu-id="c7e87-118">安全なドキュメント</span><span class="sxs-lookup"><span data-stu-id="c7e87-118">Safe Documents</span></span>|[<span data-ttu-id="c7e87-119">Microsoft Defender for Office 365 の安全なドキュメント</span><span class="sxs-lookup"><span data-stu-id="c7e87-119">Safe Documents in Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/safe-docs)|
|<span data-ttu-id="c7e87-120">Teams 用の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="c7e87-120">Safe Links for Teams</span></span>|[<span data-ttu-id="c7e87-121">Teams での Office 365 の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="c7e87-121">Office 365 Safe Links in Teams</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams)<br>[<span data-ttu-id="c7e87-122">リンク保護</span><span class="sxs-lookup"><span data-stu-id="c7e87-122">Safe Links</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)|

## <a name="teams-guest-sharing"></a><span data-ttu-id="c7e87-123">Teams ゲスト共有</span><span class="sxs-lookup"><span data-stu-id="c7e87-123">Teams guest sharing</span></span>

<span data-ttu-id="c7e87-124">それぞれの階層には、組織外のユーザーと共有するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="c7e87-124">In each of the tiers, we have the option of sharing with people outside your organization.</span></span> <span data-ttu-id="c7e87-125">機密性の高い階層については、秘密度ラベルを使用してチーム レベルでゲスト共有をオフにするオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="c7e87-125">For the sensitive and highly sensitive tiers, we will have the option to turn guest sharing off at the team level by using sensitivity labels.</span></span> <span data-ttu-id="c7e87-126">ただし、Teams でゲスト共有を完全に行うには、組織レベルのゲスト共有設定をオンにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7e87-126">But the organization-level guest sharing setting must be turned on for guest sharing to work at all in Teams.</span></span>

![Teams ゲスト アクセスのトグルのスクリーンショット](../media/teams-guest-access-toggle-on.png)

<span data-ttu-id="c7e87-128">Teams ゲスト アクセスの設定を行うには</span><span class="sxs-lookup"><span data-stu-id="c7e87-128">To set Teams guest access settings</span></span>

1. <span data-ttu-id="c7e87-129">[https://admin.microsoft.com](https://admin.microsoft.com) で、Microsoft 365 管理センターにログインします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-129">Log in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
2. <span data-ttu-id="c7e87-130">左側のナビゲーションで [ **すべて表示** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-130">In the left navigation, click **Show all**.</span></span>
3. <span data-ttu-id="c7e87-131">[ **管理センター** ] で、[ **Teams** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-131">Under **Admin centers** , click **Teams**.</span></span>
4. <span data-ttu-id="c7e87-132">Teams 管理センターの左側のナビゲーションで、[ **組織全体の設定** ] を展開して [ **ゲスト アクセス** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-132">In the Teams admin center, in the left navigation, expand **Org-wide settings** and click **Guest access**.</span></span>
5. <span data-ttu-id="c7e87-133">[ **Teams でのゲスト アクセスを許可する** ] が [ **オン** ] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c7e87-133">Ensure that **Allow guest access in Teams** is set to **On**.</span></span>
6. <span data-ttu-id="c7e87-134">追加のゲスト設定に必要な変更を加えて、[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-134">Make any desired changes to the additional guest settings, and then click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="c7e87-135">Teams のゲスト設定をオンにした後、有効になるまでには、最大で 24 時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c7e87-135">It may take up to twenty-four hours for the Teams guest setting to become active after you turn it on.</span></span>

<span data-ttu-id="c7e87-136">Office 365 グループや SharePoint では既定でゲスト共有がオンになっていますが、組織のゲスト共有設定を以前変更したことがある場合には、Teams でゲスト共有が利用できるように「[チームでゲストと共同で作業する](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)」を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-136">Guest sharing is turned on by default for Office 365 groups and SharePoint, however if you have previously changed any of the guest sharing settings for your organization, we recommend that you review [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team) to ensure that guest sharing will be available in Teams.</span></span>

## <a name="site-and-file-sharing"></a><span data-ttu-id="c7e87-137">サイトとファイル共有</span><span class="sxs-lookup"><span data-stu-id="c7e87-137">Site and file sharing</span></span>

<span data-ttu-id="c7e87-138">誤って組織外のユーザーとファイルやフォルダを共有してしまうリスクを減らすために、SharePoint の既定の共有リンクを [ *自分の組織内のユーザーのみ* ] に変更することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-138">To reduce the risk of accidentally sharing files or folders with people outside your organization, we recommend changing the default sharing link for SharePoint to *Only people in your organization*.</span></span> <span data-ttu-id="c7e87-139">(ユーザーが外部との共有を行う必要があり、ゲスト共有を有効にしている場合、ユーザーは共有時にリンクの種類を変更することができます。)</span><span class="sxs-lookup"><span data-stu-id="c7e87-139">(If users need to share externally, and you have enabled guest sharing, they can still change the link type when they share.)</span></span>

<span data-ttu-id="c7e87-140">既定の共有リンクを変更するには</span><span class="sxs-lookup"><span data-stu-id="c7e87-140">To change the default sharing link</span></span>
1. <span data-ttu-id="c7e87-141">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="c7e87-141">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="c7e87-142">[ **ポリシー** ] で、[ **共有** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-142">Under **Policies** , click **Sharing**.</span></span>
3. <span data-ttu-id="c7e87-143">[ **ファイルとフォルダーのリンク** ] で、[ **自分の組織内のユーザーのみ** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7e87-143">Under **File and folder links** , select **Only people in your organization**.</span></span>
4. <span data-ttu-id="c7e87-144">[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-144">Click **Save**.</span></span>

<span data-ttu-id="c7e87-145">最高のゲスト共有エクスペリエンスのために、[SharePoint および OneDrive の Azure AD B2B との統合](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)を有効にすることもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-145">For the best guest sharing experience, we also recommend that you enable [SharePoint and OneDrive integration with Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="c7e87-146">チームを作成する</span><span class="sxs-lookup"><span data-stu-id="c7e87-146">Create a team</span></span>

<span data-ttu-id="c7e87-147">ベースライン レベルの保護の追加構成は、チームに関連付けられている SharePoint サイトで行います。</span><span class="sxs-lookup"><span data-stu-id="c7e87-147">Additional configuration for the baseline level of protection is done in the SharePoint site associated with a team.</span></span> <span data-ttu-id="c7e87-148">次のセクションへと進む前に、[パブリックまたはプライベート チームを作成](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)します。</span><span class="sxs-lookup"><span data-stu-id="c7e87-148">[Create a public or private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) before proceeding to the next section.</span></span>

## <a name="site-sharing-settings"></a><span data-ttu-id="c7e87-149">サイト共有設定</span><span class="sxs-lookup"><span data-stu-id="c7e87-149">Site sharing settings</span></span>

<span data-ttu-id="c7e87-150">既定では、SharePoint サイトのメンバーは、他のユーザーをサイトに招待することができます。</span><span class="sxs-lookup"><span data-stu-id="c7e87-150">By default, members of a SharePoint site can invite others to the site.</span></span> <span data-ttu-id="c7e87-151">サイトがチームの一部である場合、チーム メンバーはサイト メンバーとして含まれます。</span><span class="sxs-lookup"><span data-stu-id="c7e87-151">When a site is part of a team, team members are included as site members.</span></span> <span data-ttu-id="c7e87-152">ただし、直接サイトに追加されたユーザーは、残りのチームにはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="c7e87-152">However, people added directly to the site don't have access to the rest of the team.</span></span> <span data-ttu-id="c7e87-153">そのため、アクセス許可の管理はチームを通してのみ行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-153">For this reason, we recommend managing permissions exclusively through the team.</span></span>

<span data-ttu-id="c7e87-154">アクセス許可の管理をサポートするために、関連付けられたサイトを構成して、所有者のみがサイトを単独で共有できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-154">To help with permissions management, we recommend configuring the associated site to only allow owners to share the site by itself.</span></span> <span data-ttu-id="c7e87-155">これにより、アクセス許可の管理が簡素化され、チームの所有者が知らないユーザーによるアクセスを防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="c7e87-155">This simplifies permissions management and helps prevent access by people without a team owner's knowledge.</span></span> <span data-ttu-id="c7e87-156">ベースライン保護を必要とするチームごとに、この操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c7e87-156">Do this for each team that requires baseline protection.</span></span>

<span data-ttu-id="c7e87-157">サイト共有設定を更新するには</span><span class="sxs-lookup"><span data-stu-id="c7e87-157">To update the site sharing settings</span></span>
1. <span data-ttu-id="c7e87-158">チームのツール バーで、[ **ファイル** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-158">In the tool bar for the team, click **Files**.</span></span>
2. <span data-ttu-id="c7e87-159">[ **SharePoint で開く** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-159">Click **Open in SharePoint**.</span></span>
3. <span data-ttu-id="c7e87-160">SharePoint サイトのツール バーで、設定アイコンをクリックしてから、[ **サイトの権限** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-160">In the tool bar of the SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
4. <span data-ttu-id="c7e87-161">[ **サイトの権限** ] ウィンドウで、[ **共有設定** ] の [ **共有設定の変更** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-161">In the **Site permissions** pane, under **Sharing settings** , click **Change sharing settings**.</span></span>
5. <span data-ttu-id="c7e87-162">[ **共有アクセス許可** ] で、[ **サイトの所有者とメンバー、および編集権限を持つユーザーはファイルとフォルダを共有できますが、サイトを共有できるのはサイト所有者だけです** ] を選択し、[ **保存** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e87-162">Under **Sharing permissions** , choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site** , and then click **Save**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="c7e87-163">追加の保護</span><span class="sxs-lookup"><span data-stu-id="c7e87-163">Additional protections</span></span>

<span data-ttu-id="c7e87-164">Microsoft 365 は、コンテンツを保護するための追加の方法を提供しています。</span><span class="sxs-lookup"><span data-stu-id="c7e87-164">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="c7e87-165">次のオプションを使用して、組織のセキュリティを強化することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c7e87-165">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="c7e87-166">ゲスト ユーザーを[使用条件](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)に同意させる。</span><span class="sxs-lookup"><span data-stu-id="c7e87-166">Have your guest users agree to a [terms of use](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="c7e87-167">ゲストに[セッション タイムアウト ポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)を構成する。</span><span class="sxs-lookup"><span data-stu-id="c7e87-167">Configure a [session timeout policy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="c7e87-168">[機密情報の種類](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)を作成し、[データ損失防止](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)を使用して、機密情報にアクセスするポリシーを設定する。</span><span class="sxs-lookup"><span data-stu-id="c7e87-168">Create [sensitive information types](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) and use [data loss protection](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to set policies around accessing sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7e87-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="c7e87-169">See Also</span></span>

[<span data-ttu-id="c7e87-170">Teams での会議ポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="c7e87-170">Manage meeting policies in Teams</span></span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams)

[<span data-ttu-id="c7e87-171">インサイダー リスクの管理の概要</span><span class="sxs-lookup"><span data-stu-id="c7e87-171">Get started with insider risk management</span></span>](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure)
