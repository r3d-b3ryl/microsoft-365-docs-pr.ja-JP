---
title: サイトでゲストと共同で作業する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: ゲストを使用したグループ作業のために SharePoint サイトをセットアップするために必要な Microsoft 365 構成手順について説明します。
ms.openlocfilehash: d5a868e57753a6eb05f74b4873ed64ef0a70878e
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171270"
---
# <a name="collaborate-with-guests-in-a-site"></a><span data-ttu-id="619a5-103">サイトでゲストと共同で作業する</span><span class="sxs-lookup"><span data-stu-id="619a5-103">Collaborate with guests in a site</span></span>

<span data-ttu-id="619a5-104">ドキュメント、データ、およびリスト間でゲストと共同作業を行う必要がある場合は、SharePoint サイトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="619a5-104">If you need to collaborate with guests across documents, data, and lists, you can use a SharePoint site.</span></span> <span data-ttu-id="619a5-105">モダン SharePoint サイトは、Microsoft 365 グループに接続されており、サイトメンバーシップを管理したり、共有されたメールボックスや予定表などのその他のコラボレーションツールを提供したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="619a5-105">Modern SharePoint sites are connected to Microsoft 365 Groups and can manage the site membership and provide additional collaboration tools such as a shared mailbox and calendar.</span></span>

<span data-ttu-id="619a5-106">この記事では、ゲストとのグループ作業のために SharePoint サイトをセットアップするために必要な Microsoft 365 の構成手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="619a5-106">In this article, we'll walk through the Microsoft 365 configuration steps necessary to set up a SharePoint site for collaboration with guests.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="619a5-107">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="619a5-107">Video demonstration</span></span>

<span data-ttu-id="619a5-108">このビデオでは、このドキュメントで説明されている構成手順を示します。</span><span class="sxs-lookup"><span data-stu-id="619a5-108">This video shows the configuration steps described in this document.</span></span></br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-organizational-relationships-settings"></a><span data-ttu-id="619a5-109">Azure の組織上の関係の設定</span><span class="sxs-lookup"><span data-stu-id="619a5-109">Azure Organizational relationships settings</span></span>

<span data-ttu-id="619a5-110">Microsoft 365 での共有は、 [Azure Active Directory の組織上の関係の設定](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations)によって最上位レベルで管理されます。</span><span class="sxs-lookup"><span data-stu-id="619a5-110">Sharing in Microsoft 365 is governed at its highest level by the [organizational relationships settings in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).</span></span> <span data-ttu-id="619a5-111">Azure AD でゲストの共有が無効または制限されている場合、これは Microsoft 365 で構成した共有設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="619a5-111">If guest sharing is disabled or restricted in Azure AD, this will override any sharing settings that you configure in Microsoft 365.</span></span>

<span data-ttu-id="619a5-112">外部のグループ作業設定を確認して、ゲストとの共有がブロックされないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="619a5-112">Check the external collaboration settings to ensure that sharing with guests is not blocked.</span></span>

![Azure Active Directory の外部コラボレーション設定ページのスクリーンショット](../media/azure-ad-organizational-relationships-settings.png)

<span data-ttu-id="619a5-114">外部コラボレーション設定を設定するには:</span><span class="sxs-lookup"><span data-stu-id="619a5-114">To set external collaboration settings:</span></span>


1. <span data-ttu-id="619a5-115">Microsoft Azure にログイン [https://portal.azure.com](https://portal.azure.com) します。</span><span class="sxs-lookup"><span data-stu-id="619a5-115">Log in to Microsoft Azure at [https://portal.azure.com](https://portal.azure.com).</span></span>
2. <span data-ttu-id="619a5-116">左側のナビゲーションで、[ **Azure Active Directory**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-116">In the left navigation, click **Azure Active Directory**.</span></span>
3. <span data-ttu-id="619a5-117">[ **外部 id** ] を選択し、[ **外部のグループ作業設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-117">Select **External Identities** and click on **External collaboration settings**.</span></span>
4. <span data-ttu-id="619a5-118">[ **ゲスト招待の設定** ] ウィンドウで、 **guest 招待元役割の管理者とユーザーが招待できる** こと、および **メンバーが招待** できるユーザーが **[はい]** に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="619a5-118">In the **Guest invite settings** pane, ensure that **Admins and users in the guest inviter role can invite** and **Members can invite** are both set to **Yes**.</span></span>
5. <span data-ttu-id="619a5-119">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-119">If you made changes, click **Save**.</span></span>

<span data-ttu-id="619a5-120">[ **共同作業の制限** ] セクションの設定に注意してください。</span><span class="sxs-lookup"><span data-stu-id="619a5-120">Note the settings in the **Collaboration restrictions** section.</span></span> <span data-ttu-id="619a5-121">共同作業を行うゲストのドメインがブロックされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="619a5-121">Make sure that the domains of the guests that you want to collaborate with aren't blocked.</span></span>

<span data-ttu-id="619a5-122">複数の組織のゲストを使用している場合は、ディレクトリデータへのアクセスを制限することをお客様に許可します。</span><span class="sxs-lookup"><span data-stu-id="619a5-122">If you work with guests from multiple organizations, you may want to restrict their ability to access directory data.</span></span> <span data-ttu-id="619a5-123">これにより、他のユーザーがディレクトリ内のゲストであることを確認できなくなります。</span><span class="sxs-lookup"><span data-stu-id="619a5-123">This will prevent them from seeing who else is a guest in the directory.</span></span> <span data-ttu-id="619a5-124">これを行うには、[ **ゲストユーザーのアクセス制限**] で、[ゲストユーザー **がアクセスを制限しているのは、ディレクトリオブジェクトのプロパティとメンバーシップ] 設定** または **guest ユーザーアクセスが、自分のディレクトリオブジェクトのプロパティとメンバーシップに制限され**ています。</span><span class="sxs-lookup"><span data-stu-id="619a5-124">To do this, under **Guest user access restrictions**, select **Guest users have limited access to properties and membership of directory objects settings** or **Guest user access is restricted to properties and memberships of their own directory objects**.</span></span>

## <a name="microsoft-365-groups-guest-settings"></a><span data-ttu-id="619a5-125">Microsoft 365 グループのゲスト設定</span><span class="sxs-lookup"><span data-stu-id="619a5-125">Microsoft 365 Groups guest settings</span></span>

<span data-ttu-id="619a5-126">モダン SharePoint サイトでは、Microsoft 365 グループを使用してサイトアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="619a5-126">Modern SharePoint sites use Microsoft 365 Groups to control site access.</span></span> <span data-ttu-id="619a5-127">SharePoint サイトでゲストアクセスを機能させるには、Microsoft 365 グループのゲスト設定をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="619a5-127">The Microsoft 365 Groups guest settings must be turned on in order for guest access in SharePoint sites to work.</span></span>

![Microsoft 365 管理センターにおける Microsoft 365 グループのゲスト設定のスクリーンショット](../media/office-365-groups-guest-settings.png)

<span data-ttu-id="619a5-129">Microsoft 365 グループのゲスト設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="619a5-129">To set Microsoft 365 Groups guest settings</span></span>

1. <span data-ttu-id="619a5-130">Microsoft 365 管理センターの左側のナビゲーションで、[ **設定**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="619a5-130">In the Microsoft 365 admin center, in the left navigation, expand **Settings**.</span></span>
2. <span data-ttu-id="619a5-131">[ **サービス] [& アドイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-131">Click **Services & add-ins**.</span></span>
3. <span data-ttu-id="619a5-132">一覧で、[ **Microsoft 365 Groups**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-132">In the list, click **Microsoft 365 Groups**.</span></span>
4. <span data-ttu-id="619a5-133">[組織外のユーザーにグループの **コンテンツへのアクセス** を許可する] および [ **グループの所有者に組織外のユーザーをグループに追加する** ] チェックボックスの両方がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="619a5-133">Ensure that the **Let group members outside your organization access group content** and **Let group owners add people outside your organization to groups** check boxes are both checked.</span></span>
5. <span data-ttu-id="619a5-134">変更を加えた場合は、[ **変更の保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-134">If you made changes, click **Save changes**.</span></span>


## <a name="sharepoint-organization-level-sharing-settings"></a><span data-ttu-id="619a5-135">SharePoint 組織レベルの共有設定</span><span class="sxs-lookup"><span data-stu-id="619a5-135">SharePoint organization level sharing settings</span></span>

<span data-ttu-id="619a5-136">ゲストが SharePoint サイトにアクセスできるようにするには、SharePoint の組織レベルの共有設定でゲストとの共有が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="619a5-136">In order for guests to have access to SharePoint sites, the SharePoint organization-level sharing settings must allow for sharing with guests.</span></span>

<span data-ttu-id="619a5-137">組織レベルの設定によって、個々のサイトで使用可能な設定が決まります。</span><span class="sxs-lookup"><span data-stu-id="619a5-137">The organization-level settings determine what settings are available for individual sites.</span></span> <span data-ttu-id="619a5-138">サイトの設定は、組織レベルの設定よりも制限することはできません。</span><span class="sxs-lookup"><span data-stu-id="619a5-138">Site settings cannot be more permissive than the organization-level settings.</span></span>

<span data-ttu-id="619a5-139">認証されていないファイルとフォルダーの共有を許可する場合は、[ **すべてのユーザー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="619a5-139">If you want to allow unauthenticated file and folder sharing, choose **Anyone**.</span></span> <span data-ttu-id="619a5-140">組織外のすべてのユーザーが認証を受けることができるようにするには、[ **新規および既存のゲスト**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="619a5-140">If you want to ensure that all people outside your organization have to authenticate, choose **New and existing guests**.</span></span> <span data-ttu-id="619a5-141">組織内のすべてのサイトで必要とされる最も厳しい設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="619a5-141">Choose the most permissive setting that will be needed by any site in your organization.</span></span>

![SharePoint 組織レベルの共有設定のスクリーンショット](../media/sharepoint-organization-external-sharing-controls.png)


<span data-ttu-id="619a5-143">SharePoint 組織レベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="619a5-143">To set SharePoint organization level sharing settings</span></span>

1. <span data-ttu-id="619a5-144">Microsoft 365 管理センターで、左側のナビゲーションの [ **管理センター**] の下にある [ **SharePoint**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-144">In the Microsoft 365 admin center, in the left navigation, under **Admin centers**, click **SharePoint**.</span></span>
2. <span data-ttu-id="619a5-145">SharePoint 管理センターの左側のナビゲーションで、**[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-145">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="619a5-146">SharePoint の外部共有が [ **すべてのユーザー** ] または **[既存のゲスト**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="619a5-146">Ensure that external sharing for SharePoint is set to **Anyone** or **New and existing guests**.</span></span>
4. <span data-ttu-id="619a5-147">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-147">If you made changes, click **Save**.</span></span>

## <a name="create-a-site"></a><span data-ttu-id="619a5-148">サイトを作成する</span><span class="sxs-lookup"><span data-stu-id="619a5-148">Create a site</span></span>

<span data-ttu-id="619a5-149">次の手順では、ゲストとの共同作業に使用する予定のサイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="619a5-149">The next step is to create the site that you plan to use for collaborating with guests.</span></span>

<span data-ttu-id="619a5-150">サイトを作成するには</span><span class="sxs-lookup"><span data-stu-id="619a5-150">To create a site</span></span>
1. <span data-ttu-id="619a5-151">SharePoint 管理センターで、**[サイト]** の下側にある **[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-151">In the SharePoint admin center, under **Sites**, click **Active sites**.</span></span>
2. <span data-ttu-id="619a5-152">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-152">Click **Create**.</span></span>
3. <span data-ttu-id="619a5-153">[ **チームサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-153">Click **Team site**.</span></span>
4. <span data-ttu-id="619a5-154">サイト名を入力し、グループの所有者 (サイト所有者) の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="619a5-154">Type a site name and enter a name for the Group owner (site owner).</span></span>
5. <span data-ttu-id="619a5-155">[ **詳細設定**] で、これをパブリックサイトまたはプライベートサイトにするかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="619a5-155">Under **Advanced settings**, choose if you want this to be a public or private site.</span></span>
6. <span data-ttu-id="619a5-156">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-156">Click **Next**.</span></span>
7. <span data-ttu-id="619a5-157">[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-157">Click **Finish**.</span></span>

<span data-ttu-id="619a5-158">後でユーザーを招待します。</span><span class="sxs-lookup"><span data-stu-id="619a5-158">We'll invite users later.</span></span> <span data-ttu-id="619a5-159">次に、このサイトのサイトレベルでの共有設定を確認することが重要です。</span><span class="sxs-lookup"><span data-stu-id="619a5-159">Next, it's important to check the site-level sharing settings for this site.</span></span>

## <a name="sharepoint-site-level-sharing-settings"></a><span data-ttu-id="619a5-160">SharePoint サイトレベルの共有設定</span><span class="sxs-lookup"><span data-stu-id="619a5-160">SharePoint site level sharing settings</span></span>

<span data-ttu-id="619a5-161">サイトレベルの共有設定をチェックして、このサイトに必要なアクセスの種類が許可されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="619a5-161">Check the site-level sharing settings to make sure that they allow the type of access that you want for this site.</span></span> <span data-ttu-id="619a5-162">たとえば、組織レベルの設定をすべての **ユーザー**に設定した場合に、すべてのゲストがこのサイトの認証を行うようにするには、サイトレベルの共有設定が **新規および既存のゲスト**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="619a5-162">For example, if you set the organization-level settings to **Anyone**, but you want all guests to authenticate for this site, then make sure the site-level sharing settings are set to **New and existing guests**.</span></span>

<span data-ttu-id="619a5-163">サイトは、認証されていないユーザー (**すべてのユーザー** の設定) と共有できませんが、個別のファイルやフォルダーは使用できます。</span><span class="sxs-lookup"><span data-stu-id="619a5-163">Note that the site cannot be shared with unauthenticated people (**Anyone** setting), but individual files and folders can.</span></span>

![SharePoint サイトの外部共有設定のスクリーンショット](../media/sharepoint-site-external-sharing-settings.png)

<span data-ttu-id="619a5-165">サイトレベルの共有設定を設定するには</span><span class="sxs-lookup"><span data-stu-id="619a5-165">To set site-level sharing settings</span></span>
1. <span data-ttu-id="619a5-166">SharePoint 管理センターの左側のナビゲーションで、[**サイト**] を展開して [**アクティブなサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-166">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="619a5-167">作成したサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="619a5-167">Select the site that you just created.</span></span>
3. <span data-ttu-id="619a5-168">リボンで [**共有**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-168">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="619a5-169">共有が [ **すべてのユーザー** ] または **[既存のゲスト**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="619a5-169">Ensure that sharing is set to **Anyone** or **New and existing guests**.</span></span>
5. <span data-ttu-id="619a5-170">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-170">If you made changes, click **Save**.</span></span>

## <a name="invite-users"></a><span data-ttu-id="619a5-171">ユーザーを招待する</span><span class="sxs-lookup"><span data-stu-id="619a5-171">Invite users</span></span>

<span data-ttu-id="619a5-172">ゲスト共有の設定が構成されるようになったため、内部ユーザーとゲストのサイトへの追加を開始できます。</span><span class="sxs-lookup"><span data-stu-id="619a5-172">Guest sharing settings are now configured, so you can start adding internal users and guests to your site.</span></span> <span data-ttu-id="619a5-173">サイトアクセスは、関連付けられた Microsoft 365 グループによって制御されるため、ユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="619a5-173">Site access is controlled through the associated Microsoft 365 Group, so we'll be adding users there.</span></span>

<span data-ttu-id="619a5-174">内部ユーザーをグループに招待するには</span><span class="sxs-lookup"><span data-stu-id="619a5-174">To invite internal users to a group</span></span>
1. <span data-ttu-id="619a5-175">ユーザーを追加するサイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="619a5-175">Navigate to the site where you want to add users.</span></span>
2. <span data-ttu-id="619a5-176">右上の [ **メンバー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-176">Click **Members** in the upper right.</span></span>
3. <span data-ttu-id="619a5-177">**[メンバーの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-177">Click **Add members**.</span></span>
4. <span data-ttu-id="619a5-178">サイトに招待するユーザーの名前または電子メールアドレスを入力し、[ **保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-178">Type the names or email addresses of the users that you want to invite to the site, and then click **Save**.</span></span>

<span data-ttu-id="619a5-179">ゲストユーザーをサイトから追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="619a5-179">Guest users can't be added from the site.</span></span> <span data-ttu-id="619a5-180">Web 上の Outlook を使用してそれらを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="619a5-180">You need to add them using Outlook on the web.</span></span>

<span data-ttu-id="619a5-181">グループにゲストを招待するには</span><span class="sxs-lookup"><span data-stu-id="619a5-181">To invite guests to a group</span></span>
1. <span data-ttu-id="619a5-182">Web 上の Outlook の [ **グループ**] で、メンバーを追加するグループをクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-182">In Outlook on the web, under **Groups**, click the group where you want to add members.</span></span>
2. <span data-ttu-id="619a5-183">グループの連絡先カードを開いて、[ **その他のオプション** (...)] の下にある [ **メンバーの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-183">Open the group contact card, and then, under **More options** (...), click **Add members**.</span></span>
3. <span data-ttu-id="619a5-184">招待するゲストの電子メールアドレスを入力し、[ **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-184">Type the email addresses of the guests that you want to invite, and then click **Add**.</span></span>
4. <span data-ttu-id="619a5-185">[閉じる] \*\*\*\* をクリックします。</span><span class="sxs-lookup"><span data-stu-id="619a5-185">Click **Close**.</span></span>

## <a name="see-also"></a><span data-ttu-id="619a5-186">関連項目</span><span class="sxs-lookup"><span data-stu-id="619a5-186">See Also</span></span>

[<span data-ttu-id="619a5-187">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="619a5-187">Best practices for sharing files and folders with unauthenticated users</span></span>](best-practices-anonymous-sharing.md)

[<span data-ttu-id="619a5-188">ゲストと共有するときにファイルの偶発的な公開を制限する</span><span class="sxs-lookup"><span data-stu-id="619a5-188">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="619a5-189">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="619a5-189">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="619a5-190">管理されたゲストで B2B エクストラネットを作成する</span><span class="sxs-lookup"><span data-stu-id="619a5-190">Create a B2B extranet with managed guests</span></span>](b2b-extranet.md)
