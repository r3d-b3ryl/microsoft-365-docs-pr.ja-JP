---
title: 分離した SharePoint Online チーム サイトの設計
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 775a4e9e-3135-4a48-b32f-bbdd9f2bd0aa
description: アクセス許可レベルの決定、アクセスグループを持つユーザーへのアクセス許可の割り当て、およびネストされた Azure AD グループを含む、分離した SharePoint Online チームサイトを設計します。
ms.openlocfilehash: 035952c1921443d86602eb94e3965acee86ae3e8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203121"
---
# <a name="design-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="25ce5-103">分離した SharePoint Online チーム サイトの設計</span><span class="sxs-lookup"><span data-stu-id="25ce5-103">Design an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="25ce5-104">**概要:** 分離した SharePoint Online チーム サイトの設計プロセスをステップごとに示します。</span><span class="sxs-lookup"><span data-stu-id="25ce5-104">**Summary:** Step through the design process for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="25ce5-105">この記事では、分離した SharePoint Online チーム サイトを作成する前に行う必要がある設計上の主要な決定事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="25ce5-105">This article takes you through the key design decisions you must make before creating an isolated SharePoint Online team site.</span></span>

## <a name="phase-1-determine-your-sharepoint-groups-and-permission-levels"></a><span data-ttu-id="25ce5-106">フェーズ 1:SharePoint グループおよびアクセス許可レベルを決定します。</span><span class="sxs-lookup"><span data-stu-id="25ce5-106">Phase 1: Determine your SharePoint groups and permission levels</span></span>

<span data-ttu-id="25ce5-107">既定では、すべての SharePoint Online チーム サイトは次の SharePoint グループを使用して作成されます。</span><span class="sxs-lookup"><span data-stu-id="25ce5-107">Every SharePoint Online team site by default is created with the following SharePoint groups:</span></span>

- <span data-ttu-id="25ce5-108">\<site name> スタッフ</span><span class="sxs-lookup"><span data-stu-id="25ce5-108">\<site name> Members</span></span>

- <span data-ttu-id="25ce5-109">\<site name> 書き込む</span><span class="sxs-lookup"><span data-stu-id="25ce5-109">\<site name> Visitors</span></span>

- <span data-ttu-id="25ce5-110">\<site name> 経営</span><span class="sxs-lookup"><span data-stu-id="25ce5-110">\<site name> Owners</span></span>

<span data-ttu-id="25ce5-111">これらのグループは、Microsoft 365 および Azure Active Directory (AD) グループとは別のものであり、サイトのリソースに対するアクセス許可を割り当てるための基礎となります。</span><span class="sxs-lookup"><span data-stu-id="25ce5-111">These groups are separate from Microsoft 365 and Azure Active Directory (AD) groups and are the basis for assigning permissions for the resources of the site.</span></span>

<span data-ttu-id="25ce5-p101">SharePoint グループのメンバーがサイトで実行できる内容を決定する特定のアクセス許可のセットが、アクセス許可レベルになります。SharePoint Online チーム サイトでは、既定では次の 3 つのアクセス許可レベルがあります。編集、読み取り、フル コントロールです。次の表は、SharePoint グループと割り当てられるアクセス許可レベルとの既定の相関関係を示しています。</span><span class="sxs-lookup"><span data-stu-id="25ce5-p101">The set of specific permissions that determines what a member of a SharePoint group can do in a site is a permission level. There are three permission levels by default for a SharePoint Online team site: Edit, Read, and Full control. The following table shows the default correlation of SharePoint groups and assigned permission levels:</span></span>

****

|<span data-ttu-id="25ce5-115">SharePoint グループ</span><span class="sxs-lookup"><span data-stu-id="25ce5-115">SharePoint group</span></span>|<span data-ttu-id="25ce5-116">アクセス許可レベル</span><span class="sxs-lookup"><span data-stu-id="25ce5-116">Permission level</span></span>|
|---|---|
|<span data-ttu-id="25ce5-117">\<site name> スタッフ</span><span class="sxs-lookup"><span data-stu-id="25ce5-117">\<site name> Members</span></span>|<span data-ttu-id="25ce5-118">Edit</span><span class="sxs-lookup"><span data-stu-id="25ce5-118">Edit</span></span>|
|<span data-ttu-id="25ce5-119">\<site name> 書き込む</span><span class="sxs-lookup"><span data-stu-id="25ce5-119">\<site name> Visitors</span></span>|<span data-ttu-id="25ce5-120">読み取り</span><span class="sxs-lookup"><span data-stu-id="25ce5-120">Read</span></span>|
|<span data-ttu-id="25ce5-121">\<site name> 経営</span><span class="sxs-lookup"><span data-stu-id="25ce5-121">\<site name> Owners</span></span>|<span data-ttu-id="25ce5-122">フル コントロール</span><span class="sxs-lookup"><span data-stu-id="25ce5-122">Full control</span></span>|
|

 <span data-ttu-id="25ce5-p102">**ベスト プラクティス:** 追加の SharePoint グループおよびアクセス許可レベルを作成できます。ただし、分離した SharePoint Online サイトには、既定の SharePoint グループおよびアクセス許可レベルを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="25ce5-p102">**Best practice:** You can create additional SharePoint groups and permission levels. However, we recommend using the default SharePoint groups and permission levels for your isolated SharePoint Online site.</span></span>

<span data-ttu-id="25ce5-125">既定の SharePoint グループとアクセス許可レベルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="25ce5-125">Here are the default SharePoint groups and permission levels.</span></span>

![SharePoint Online サイトの既定の SharePoint グループとアクセス許可レベル。](../../media/3f892ab4-6479-42f0-a505-1ba0ef94b9c6.png)

## <a name="phase-2-assign-permissions-to-users-with-access-groups"></a><span data-ttu-id="25ce5-127">フェーズ 2:アクセス グループを使用してアクセス許可をユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="25ce5-127">Phase 2: Assign permissions to users with access groups</span></span>

<span data-ttu-id="25ce5-128">ユーザーにアクセス許可を割り当てるには、そのユーザーアカウント、またはユーザーアカウントがメンバーになっている Microsoft 365 または Azure AD グループを SharePoint グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="25ce5-128">You can assign permissions to users by adding their user account, or a Microsoft 365 or Azure AD group of which the user account is a member, to the SharePoint groups.</span></span> <span data-ttu-id="25ce5-129">追加されたユーザーアカウントには、Microsoft 365 または Azure AD グループのメンバーシップ経由で直接的または間接的に、SharePoint グループに関連付けられているアクセス許可レベルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="25ce5-129">Once added, the user accounts, either directly or indirectly via membership in a Microsoft 365 or Azure AD group, are assigned the permission level associated with the SharePoint group.</span></span>

<span data-ttu-id="25ce5-130">既定の SharePoint グループを使用した例:</span><span class="sxs-lookup"><span data-stu-id="25ce5-130">Using the default SharePoint groups as an example:</span></span>

- <span data-ttu-id="25ce5-131">\*\* \<site name> メンバー**の SharePoint グループのメンバーには、ユーザーアカウントとグループの両方を含めることができます。このグループには、**編集\*\*アクセス許可レベルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="25ce5-131">Members of the **\<site name> Members** SharePoint group, which can include both user accounts and groups, are assigned the **Edit** permission level</span></span>

- <span data-ttu-id="25ce5-132">\*\* \<site name> 閲覧**者の SharePoint グループのメンバーには、ユーザーアカウントとグループの両方を含めることができます。**読み取り\*\*アクセス許可レベルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="25ce5-132">Members of the **\<site name> Visitors** SharePoint group, which can include both user accounts and groups, are assigned the **Read** permission level</span></span>

- <span data-ttu-id="25ce5-133">\*\* \<site name> 所有者**SharePoint グループのメンバーには、ユーザーアカウントとグループの両方を含めることができます。このグループには、**フルコントロール\*\*のアクセス許可レベルが割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="25ce5-133">Members of the **\<site name> Owners** SharePoint group, which can include both user accounts and groups, are assigned the **Full control** permission level</span></span>

 <span data-ttu-id="25ce5-p104">**ベスト プラクティス:** 個々のユーザー アカウントを使用してアクセス許可を管理することもできますが、代わりにアクセス グループと呼ばれる 1 つの Azure AD グループを使用することをお勧めします。この方法は、SharePoint グループごとにユーザー アカウントのリストを管理するのではなく、アクセス グループのメンバーシップでアクセス許可の管理を簡略化するものです。</span><span class="sxs-lookup"><span data-stu-id="25ce5-p104">**Best practice:** Although you can manage permissions through individual user accounts, we recommend that you use a single Azure AD group, known as an access group, instead. This simplifies the management of permissions through membership in the access group, rather than managing the list of user accounts for each SharePoint group.</span></span>

<span data-ttu-id="25ce5-136">Microsoft 365 の Azure AD グループは、で Microsoft 365 のグループとは異なります。</span><span class="sxs-lookup"><span data-stu-id="25ce5-136">Azure AD groups for Microsoft 365 are different tha Microsoft 365 groups.</span></span> <span data-ttu-id="25ce5-137">Azure AD グループは、その **種類** が [ **セキュリティ** ] に設定され、電子メールアドレスを持たない Microsoft 365 管理センターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="25ce5-137">Azure AD groups appear in the Microsoft 365 admin center with their **Type** set to **Security** and do not have an email address.</span></span> <span data-ttu-id="25ce5-138">以下で Azure AD グループを管理できます。</span><span class="sxs-lookup"><span data-stu-id="25ce5-138">Azure AD groups can be managed within:</span></span>

- <span data-ttu-id="25ce5-139">Active Directory Domain Services (AD DS)</span><span class="sxs-lookup"><span data-stu-id="25ce5-139">Active Directory Domain Services (AD DS)</span></span>

    <span data-ttu-id="25ce5-140">これらは、オンプレミスの AD DS インフラストラクチャで作成され、Microsoft 365 サブスクリプションに同期されているグループです。</span><span class="sxs-lookup"><span data-stu-id="25ce5-140">These are groups that have been created in your on-premises AD DS infrastructure and synchronized to your Microsoft 365 subscription.</span></span> <span data-ttu-id="25ce5-141">Microsoft 365 管理センターでは、これらのグループの **状態** は **Active directory と同期**しています。</span><span class="sxs-lookup"><span data-stu-id="25ce5-141">In the Microsoft 365 admin center, these groups have a **Status** of **Synched with active directory**.</span></span>

- <span data-ttu-id="25ce5-142">Office 365</span><span class="sxs-lookup"><span data-stu-id="25ce5-142">Office 365</span></span>

    <span data-ttu-id="25ce5-143">これらは、Microsoft 365 管理センター、Azure ポータル、または Microsoft PowerShell のいずれかを使用して作成されたグループです。</span><span class="sxs-lookup"><span data-stu-id="25ce5-143">These are groups that have been created using either the Microsoft 365 admin center, the Azure portal, or Microsoft PowerShell.</span></span> <span data-ttu-id="25ce5-144">Microsoft 365 管理センターでは、これらのグループには**クラウド**の**状態**があります。</span><span class="sxs-lookup"><span data-stu-id="25ce5-144">In the Microsoft 365 admin center, these groups have a **Status** of **Cloud**.</span></span>

 <span data-ttu-id="25ce5-145">**ベストプラクティス:** オンプレミスの AD DS を使用していて、Microsoft 365 サブスクリプションと同期している場合は、AD DS でユーザーとグループの管理を実行します。</span><span class="sxs-lookup"><span data-stu-id="25ce5-145">**Best practice:** If you are using AD DS on-premises and synchronizing with your Microsoft 365 subscription, perform your user and group management with AD DS.</span></span>

<span data-ttu-id="25ce5-146">分離した SharePoint Online チーム サイトの場合、推奨されるグループ構造は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="25ce5-146">For isolated SharePoint Online team sites, the recommended group structure looks like this:</span></span>

****

|<span data-ttu-id="25ce5-147">SharePoint グループ</span><span class="sxs-lookup"><span data-stu-id="25ce5-147">SharePoint group</span></span>|<span data-ttu-id="25ce5-148">Azure AD ベースのアクセス グループ</span><span class="sxs-lookup"><span data-stu-id="25ce5-148">Azure AD-based access group</span></span>|<span data-ttu-id="25ce5-149">権限レベル</span><span class="sxs-lookup"><span data-stu-id="25ce5-149">Permission level</span></span>|
|---|---|---|
|<span data-ttu-id="25ce5-150">\<site name> スタッフ</span><span class="sxs-lookup"><span data-stu-id="25ce5-150">\<site name> Members</span></span>|<span data-ttu-id="25ce5-151">\<site name> スタッフ</span><span class="sxs-lookup"><span data-stu-id="25ce5-151">\<site name> Members</span></span>|<span data-ttu-id="25ce5-152">Edit</span><span class="sxs-lookup"><span data-stu-id="25ce5-152">Edit</span></span>|
|<span data-ttu-id="25ce5-153">\<site name> 書き込む</span><span class="sxs-lookup"><span data-stu-id="25ce5-153">\<site name> Visitors</span></span>|<span data-ttu-id="25ce5-154">\<site name> 見る</span><span class="sxs-lookup"><span data-stu-id="25ce5-154">\<site name> Viewers</span></span>|<span data-ttu-id="25ce5-155">読み取り</span><span class="sxs-lookup"><span data-stu-id="25ce5-155">Read</span></span>|
|<span data-ttu-id="25ce5-156">\<site name> 経営</span><span class="sxs-lookup"><span data-stu-id="25ce5-156">\<site name> Owners</span></span>|<span data-ttu-id="25ce5-157">\<site name> 管理</span><span class="sxs-lookup"><span data-stu-id="25ce5-157">\<site name> Admins</span></span>|<span data-ttu-id="25ce5-158">フル コントロール</span><span class="sxs-lookup"><span data-stu-id="25ce5-158">Full control</span></span>|
|

 <span data-ttu-id="25ce5-159">**ベストプラクティス:** Microsoft 365 または Azure AD グループは SharePoint グループのメンバーとして使用できますが、Azure AD グループを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="25ce5-159">**Best practice:** Although you can use either Microsoft 365 or Azure AD groups as members of SharePoint groups, we recommend that you use Azure AD groups.</span></span> <span data-ttu-id="25ce5-160">AD DS または Microsoft 365 によって管理される Azure AD グループでは、ネストされたグループを使用してアクセス許可を割り当てる方が柔軟性があります。</span><span class="sxs-lookup"><span data-stu-id="25ce5-160">Azure AD groups, managed either through AD DS or Microsoft 365, give you more flexibility to use nested groups to assign permissions.</span></span>

<span data-ttu-id="25ce5-161">Azure AD ベースのアクセスグループを使用するように構成された既定の SharePoint グループを次に示します。</span><span class="sxs-lookup"><span data-stu-id="25ce5-161">Here are the default SharePoint groups configured to use Azure AD-based access groups.</span></span>

![Access グループを既定の SharePoint Online サイトグループのメンバーとして使用します。](../../media/50a76328-ae69-483e-9029-ac4e7357b5ef.png)

<span data-ttu-id="25ce5-163">3 つのアクセス グループを設計するときは、以下の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="25ce5-163">When designing the three access groups, keep the following in mind:</span></span>

- <span data-ttu-id="25ce5-164">管理者アクセスグループには、チームサイト\*\* \<site name> \*\*を管理している少数の SharePoint Online 管理者に対応する少数のメンバーのみが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="25ce5-164">There should be only a few members in the **\<site name> Admins** access group, corresponding to a small number of SharePoint Online administrators who are managing the team site.</span></span>

- <span data-ttu-id="25ce5-165">サイトメンバーの大部分は、 \*\* \<site name> メンバー**または** \<site name> 閲覧\*\*者のアクセスグループに含まれています。</span><span class="sxs-lookup"><span data-stu-id="25ce5-165">Most of your site members are in the **\<site name> Members** or **\<site name> Viewers** access groups.</span></span> <span data-ttu-id="25ce5-166">\*\* \<site name> メンバー\*\*アクセスグループのサイトメンバーは、サイト内のリソースを削除または変更できるので、そのメンバーシップを慎重に検討してください。</span><span class="sxs-lookup"><span data-stu-id="25ce5-166">Because site members in the **\<site name> Members** access group have the ability to delete or modify resources in the site, carefully consider its membership.</span></span> <span data-ttu-id="25ce5-167">疑わしい場合は、サイトメンバーを\*\* \<site name> 閲覧\*\*者のアクセスグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="25ce5-167">When in doubt, add the site member to the **\<site name> Viewers** access group.</span></span>

<span data-ttu-id="25ce5-168">ここでは、ProjectX という名前の分離されたサイトの SharePoint グループとアクセスグループの例を示します。</span><span class="sxs-lookup"><span data-stu-id="25ce5-168">Here is an example of the SharePoint groups and access groups for an isolated site named ProjectX.</span></span>

![ProjectX という名前の SharePoint Online サイトのアクセスグループを使用する例。](../../media/13afe542-9ffd-4671-9f48-210a0e2a502a.png)

## <a name="phase-3-use-nested-azure-ad-groups"></a><span data-ttu-id="25ce5-170">フェーズ 3: ネストされた Azure AD グループを使用する</span><span class="sxs-lookup"><span data-stu-id="25ce5-170">Phase 3: Use nested Azure AD groups</span></span>

<span data-ttu-id="25ce5-p110">少数のユーザーに限定されるプロジェクトの場合、ほとんどのシナリオはサイトの SharePoint グループに追加される単一レベルの Azure AD ベースのアクセス グループに収まります。ただし、多数のユーザーがおり、それらのユーザーが既に確立された Azure AD グループのメンバーである場合、ネストされたグループ、つまり他のグループがメンバーとして含まれるグループを使用することで簡単に SharePoint アクセス許可を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="25ce5-p110">For a project confined to a small number of people, a single level of Azure AD-based access groups added to the SharePoint groups of the site will fit most scenarios. However, if you have a large number of people and those people are already members of established Azure AD groups, you can more easily assign SharePoint permissions by using nested groups, or groups that contain other groups as members.</span></span>

<span data-ttu-id="25ce5-p111">たとえば、営業部門、マーケティング部門、エンジニアリング部門、法律部門の役員間でコラボレーションするための分離した SharePoint Online チーム サイトを作成したいと考えており、それらの部門には既に役員のユーザー アカウントのメンバーシップを持つ独自のグループが存在するとします。この場合、新しいサイト メンバー用に新しいグループを作成して、それぞれの役員ユーザー アカウントをすべてそこに含めるのではなく、各部門の既存の役員グループを新しいグループに入れます。</span><span class="sxs-lookup"><span data-stu-id="25ce5-p111">For example, you want to create an isolated SharePoint online team site for collaboration among the executives of the sales, marketing, engineering, legal, and support departments and those departments already their own groups with executive user account membership. Rather than creating a new group for the new site members and placing all the individual executive user accounts in it, put the existing executive groups for each department in the new group.</span></span>

 <span data-ttu-id="25ce5-175">複数の組織間で Microsoft 365 サブスクリプションを共有している場合は、ユーザーアカウント数が非常に多くなるため、1つの組織の分離されたサイトに対して1つのレベルのグループメンバーシップを管理するのが困難になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="25ce5-175">If you are sharing a Microsoft 365 subscription between multiple organizations, a single level of group membership for an isolated site for an organization might become difficult to manage due to the sheer number of user accounts.</span></span> <span data-ttu-id="25ce5-176">この場合、組織内のグループが含まれるネストされた Azure AD グループを組織ごとに使用して、アクセス許可を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="25ce5-176">In this case, you can use nested Azure AD groups for each organization that contain the groups within their organizations to manage the permissions.</span></span>

<span data-ttu-id="25ce5-177">ネストされた Azure AD グループを使用するには、以下を実行します。</span><span class="sxs-lookup"><span data-stu-id="25ce5-177">To use nested Azure AD groups:</span></span>

1. <span data-ttu-id="25ce5-178">ユーザー アカウントを含める Azure AD グループを特定するか作成し、適切なユーザー アカウントをメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="25ce5-178">Identify or create the Azure AD groups that will contain user accounts and add the appropriate user accounts as members.</span></span>

2. <span data-ttu-id="25ce5-179">他の Azure AD グループを含めるコンテナーとなる Azure AD ベースのアクセス グループを作成し、それらのグループをメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="25ce5-179">Create the container Azure AD-based access group that will contain the other Azure AD groups and add those groups as members.</span></span>

3. <span data-ttu-id="25ce5-180"> コンテナー アクセス グループの適切なアクセス レベルについては、SharePoint グループと、対応するアクセス許可レベルを識別します。</span><span class="sxs-lookup"><span data-stu-id="25ce5-180">For the appropriate level of access for the container access group, identify the SharePoint group and corresponding permission level.</span></span>

> [!NOTE]
> <span data-ttu-id="25ce5-181">ネストされた Microsoft 365 グループは使用できません。</span><span class="sxs-lookup"><span data-stu-id="25ce5-181">You cannot use nested Microsoft 365 groups.</span></span>

<span data-ttu-id="25ce5-182">ここでは、ProjectX メンバーアクセスグループのための、ネストされた Azure AD グループの例を示します。</span><span class="sxs-lookup"><span data-stu-id="25ce5-182">Here is an example of nested Azure AD groups for the ProjectX member access group.</span></span>

![ProjectX サイトのメンバーアクセスグループにネストされたアクセスグループを使用する例。](../../media/2abca710-bf9e-4ce8-9bcd-a8e128264fb1.png)

<span data-ttu-id="25ce5-184">リサーチ、エンジニアリング、プロジェクトリードの各チームのすべてのユーザーアカウントはサイトメンバーになることを目的としているため、Azure AD グループを ProjectX Members アクセスグループに追加するのが簡単です。</span><span class="sxs-lookup"><span data-stu-id="25ce5-184">Because all of the user accounts in the Research, Engineering, and Project leads teams are intended to be site members, it is easier to add their Azure AD groups to the ProjectX Members access group.</span></span>

## <a name="next-step"></a><span data-ttu-id="25ce5-185">次のステップ</span><span class="sxs-lookup"><span data-stu-id="25ce5-185">Next step</span></span>

<span data-ttu-id="25ce5-186">分離したサイトを運用環境で作成および構成する準備ができたら、「[Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="25ce5-186">When you are ready to create and configure an isolated site in production, see [Deploy an isolated SharePoint Online team site](deploy-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="25ce5-187">関連項目</span><span class="sxs-lookup"><span data-stu-id="25ce5-187">See Also</span></span>

[<span data-ttu-id="25ce5-188">分離した SharePoint Online チーム サイト</span><span class="sxs-lookup"><span data-stu-id="25ce5-188">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="25ce5-189">分離した SharePoint Online チーム サイトの管理</span><span class="sxs-lookup"><span data-stu-id="25ce5-189">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="25ce5-190">分離した SharePoint Online チーム サイトの展開</span><span class="sxs-lookup"><span data-stu-id="25ce5-190">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
