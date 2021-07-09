---
title: 認証されていない共有のベスト プラクティス
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: この記事では、認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティスを説明します。
ms.openlocfilehash: 2c89ca319ba79d6f0463cc6d244c8d91928d6e42
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327025"
---
# <a name="best-practices-for-sharing-files-and-folders-with-unauthenticated-users"></a><span data-ttu-id="9159b-103">認証されていないユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="9159b-103">Best practices for sharing files and folders with unauthenticated users</span></span>

<span data-ttu-id="9159b-104">認証されていない共有 ([*すべてのユーザー*] リンク) は便利で、さまざまなシナリオで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9159b-104">Unauthenticated sharing (*Anyone* links) can be convenient and is useful in various scenarios.</span></span> <span data-ttu-id="9159b-105">[*すべてのユーザー*] リンクは、最も簡単な共有方法です。ユーザーは認証なしでリンクを開くことができ、そのリンクを他のユーザーに自由に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="9159b-105">*Anyone* links are the easiest way to share: people can open the link without authentication and are free to pass it on to others.</span></span>

<span data-ttu-id="9159b-p102">通常、組織内のすべてのコンテンツが認証されていない共有に適しているわけではありません。この記事では、ユーザーがファイルやフォルダーの認証されていない共有を使用できるものの、組織のコンテンツを保護するのに役立つセーフガードが設定されている環境を作成するのに利用できるオプションを説明します。</span><span class="sxs-lookup"><span data-stu-id="9159b-p102">Usually, not all content in an organization is appropriate for unauthenticated sharing. This article covers the options available to help you create an environment where your users can use unauthenticated sharing of files and folders, but where there are safeguards in place to help protect your organization's content.</span></span>

> [!NOTE]
> <span data-ttu-id="9159b-108">認証されていない共有を機能させるには、お客様の組織、および使用する予定の個々のサイトやチームに対して認証されていない共有を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9159b-108">For unauthenticated sharing to work, you must enable it for your organization and for the individual site or team that you'll be using.</span></span> <span data-ttu-id="9159b-109">有効にするシナリオについては、「[組織外のユーザーとの共同作業](collaborate-with-people-outside-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9159b-109">See [Collaborating with people outside your organization](collaborate-with-people-outside-your-organization.md) for the scenario that you want to enable.</span></span>

## <a name="set-an-expiration-date-for-anyone-links"></a><span data-ttu-id="9159b-110">[すべてのユーザー] リンクの有効期限を設定する</span><span class="sxs-lookup"><span data-stu-id="9159b-110">Set an expiration date for Anyone links</span></span>

<span data-ttu-id="9159b-111">ファイルは、サイト、グループ、チーム内に長期間保存されることがよくあります。</span><span class="sxs-lookup"><span data-stu-id="9159b-111">Files are often stored in sites, groups, and teams for long periods of time.</span></span> <span data-ttu-id="9159b-112">データ保持ポリシーによってファイルを数年間保持するように要求されている場合もあります。</span><span class="sxs-lookup"><span data-stu-id="9159b-112">Occasionally there are data retention policies that require files to be retained for years.</span></span> <span data-ttu-id="9159b-113">そのようなファイルが認証されていない人と共有されている場合、ファイルへの予期しないアクセスや変更の原因となる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9159b-113">If such files are shared with unauthenticated people, this could lead to unexpected access and changes to files in the future.</span></span> <span data-ttu-id="9159b-114">このような可能性を軽減するため、*[すべてのユーザー]* リンクの有効期限を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="9159b-114">To mitigate this possibility, you can configure an expiration time for *Anyone* links.</span></span>

<span data-ttu-id="9159b-115">*[すべてのユーザー]* リンクの期限が切れると、そのリンクを使用してコンテンツにアクセスすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="9159b-115">Once an *Anyone* link expires, it can no longer be used to access content.</span></span>

<span data-ttu-id="9159b-116">組織全体で [すべてのユーザー] リンクの有効期限を設定するには</span><span class="sxs-lookup"><span data-stu-id="9159b-116">To set an expiration date for Anyone links across the organization</span></span>

1. <span data-ttu-id="9159b-117">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="9159b-117">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="9159b-118">左側のナビゲーションで、**[ポリシー]** を展開し、**[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-118">In the left navigation, expand **Policies**, and then click **Sharing**.</span></span>
3. <span data-ttu-id="9159b-119">**[[すべてのユーザー] リンクの有効期限とアクセス許可のオプションを選択する]** で、**[これらのリンクは、次の日数以内に期限切れにする必要があります]** チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="9159b-119">Under **Choose expiration and permissions options for Anyone links**, select the **These links must expire within this many days** check box.</span></span></br>
   <span data-ttu-id="9159b-120">![SharePoint における組織レベルの [すべてのユーザー] リンクの有効期限設定のスクリーンショット](../media/sharepoint-organization-anyone-link-expiration.png)</span><span class="sxs-lookup"><span data-stu-id="9159b-120">![Screenshot of SharePoint organization-level Anyone link expiration settings](../media/sharepoint-organization-anyone-link-expiration.png)</span></span>
4. <span data-ttu-id="9159b-121">このボックスに日数を入力し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-121">Type a number of days in the box, and then click **Save**.</span></span>

<span data-ttu-id="9159b-122">特定のサイトで [すべてのユーザー] リンクの有効期限を設定するには</span><span class="sxs-lookup"><span data-stu-id="9159b-122">To set an expiration date for Anyone links on a specific site</span></span>

1. <span data-ttu-id="9159b-123">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="9159b-123">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="9159b-124">左側のナビゲーションで、**[サイト]** を展開し、**[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-124">In the left navigation, expand **Sites**, and then click **Active sites**.</span></span>
3. <span data-ttu-id="9159b-125">変更するサイトを選択し、**[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-125">Select the site you want to change, and then click **Sharing**.</span></span>
4. <span data-ttu-id="9159b-126">**[[すべてのユーザー] リンクの詳細設定]** で、**[Expiration of Anyone links]** ([すべてのユーザー] リンクの有効期限) にある **[組織レベルの設定と同じ]** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="9159b-126">Under **Advanced settings for Anyone links**, under **Expiration of Anyone links**, clear the **Same as organization-level setting** check box.</span></span></br>
   <span data-ttu-id="9159b-127">![SharePoint におけるサイトレベルの [すべてのユーザー] リンクの有効期限設定のスクリーンショット](../media/sharepoint-organization-anyone-link-expiration-site.png)</span><span class="sxs-lookup"><span data-stu-id="9159b-127">![Screenshot of SharePoint site-level Anyone link expiration settings](../media/sharepoint-organization-anyone-link-expiration-site.png)</span></span>
5. <span data-ttu-id="9159b-128">**[これらのリンクは、次の日数以内に期限切れにする必要があります]** オプションを選択し、ボックスに日数を入力します。</span><span class="sxs-lookup"><span data-stu-id="9159b-128">Select the **These links must expire within this many days** option, and type a number of days in the box.</span></span>
6. <span data-ttu-id="9159b-129">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-129">Click **Save**.</span></span>

<span data-ttu-id="9159b-130">*[すべてのユーザー]* リンクの有効期限が切れても、新しい *[すべてのユーザー]* リンクを使用してファイルやフォルダーを再共有できることにご注意ください。</span><span class="sxs-lookup"><span data-stu-id="9159b-130">Note that once an *Anyone* link expires, the file or folder can be re-shared with a new *Anyone* link.</span></span>

<span data-ttu-id="9159b-131">[Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) を使用して、特定の OneDrive での *[すべてのユーザー]* リンクの有効期限を設定できます。</span><span class="sxs-lookup"><span data-stu-id="9159b-131">You can set *Anyone* link expiration for a specific OneDrive by using [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite).</span></span>

## <a name="set-link-permissions"></a><span data-ttu-id="9159b-132">リンクのアクセス許可を設定する</span><span class="sxs-lookup"><span data-stu-id="9159b-132">Set link permissions</span></span>

<span data-ttu-id="9159b-133">既定では、ファイルに対して *[すべてのユーザー]* リンクを使用すると、ユーザーはそのファイルを編集することができます。また、フォルダーに対して *[すべてのユーザー]* リンクを使用すると、ユーザーはファイルの編集と表示に加えて、そのフォルダーに新しいファイルをアップロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="9159b-133">By default, *Anyone* links for a file allow people to edit the file, and *Anyone* links for a folder allow people to edit and view files, and upload new files to the folder.</span></span> <span data-ttu-id="9159b-134">ファイルやフォルダーに対するこれらのアクセス許可は、表示のみに個別に変更できます。</span><span class="sxs-lookup"><span data-stu-id="9159b-134">You can change these permissions for files and for folders independently to view-only.</span></span>

<span data-ttu-id="9159b-135">認証されていない共有を許可したい一方で、認証されていない人によって組織のコンテンツが変更されることへの懸念がある場合は、ファイルとフォルダーのアクセス許可を [**表示**] に設定することをご検討ください。</span><span class="sxs-lookup"><span data-stu-id="9159b-135">If you want to allow unauthenticated sharing, but are concerned about unauthenticated people modifying your organization's content, consider setting the file and folder permissions to **View**.</span></span>

<span data-ttu-id="9159b-136">組織全体で [すべてのユーザー] リンクのアクセス許可を設定するには</span><span class="sxs-lookup"><span data-stu-id="9159b-136">To set permissions for Anyone links across the organization</span></span>

1. <span data-ttu-id="9159b-137">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="9159b-137">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="9159b-138">左側のナビゲーションで **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-138">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="9159b-139">**[[すべてのユーザー] リンクの詳細設定]** で、使用するファイルとフォルダーのアクセス許可を選択します。</span><span class="sxs-lookup"><span data-stu-id="9159b-139">Under **Advanced settings for "Anyone" links**, select the file and folder permissions that you want to use.</span></span></br>
   <span data-ttu-id="9159b-140">![SharePoint における組織レベルの [すべてのユーザー] リンクのアクセス許可設定のスクリーンショット](../media/sharepoint-organization-anyone-link-permissions.png)</span><span class="sxs-lookup"><span data-stu-id="9159b-140">![Screenshot of SharePoint organization-level Anyone link permissions settings](../media/sharepoint-organization-anyone-link-permissions.png)</span></span>

<span data-ttu-id="9159b-141">*[すべてのユーザー]* リンクが **[表示]** に設定されていても、*[特定のユーザー]* リンクを使用することにより、ユーザーはファイルやフォルダーをゲストと共有して、ゲストに編集するアクセス許可を付与できます。</span><span class="sxs-lookup"><span data-stu-id="9159b-141">With *Anyone* links set to **View**, users can still share files and folders with guests and give them edit permissions by using *Specific people* links.</span></span> <span data-ttu-id="9159b-142">[特定のユーザー] リンクでは組織外のユーザーにゲストとしての認証が要求されるため、これらのリンクを使用して共有されているファイルやフォルダーに対するゲストのアクティビティを追跡および監査できます。</span><span class="sxs-lookup"><span data-stu-id="9159b-142">These links require people outside your organization to authenticate as guests, and you can track and audit guest activity on files and folders shared with these links.</span></span>

## <a name="set-default-link-type-to-only-work-for-people-in-your-organization"></a><span data-ttu-id="9159b-143">既定のリンクの種類が組織内のユーザーに対してのみ有効になるように設定する</span><span class="sxs-lookup"><span data-stu-id="9159b-143">Set default link type to only work for people in your organization</span></span>

<span data-ttu-id="9159b-144">組織で *[すべてのユーザー]* 共有が有効になっている場合、既定の共有リンクは通常 **[すべてのユーザー]** に設定されています。</span><span class="sxs-lookup"><span data-stu-id="9159b-144">When *Anyone* sharing is enabled for your organization, the default sharing link is normally set to **Anyone**.</span></span> <span data-ttu-id="9159b-145">これはユーザーにとって便利である反面、意図せずに認証されていない共有のリスクを高める可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9159b-145">While this can be convenient for users, it can increase the risk of unintentional unauthenticated sharing.</span></span> <span data-ttu-id="9159b-146">機密性の高いドキュメントを共有する際にユーザーがリンクの種類を変更し忘れると、認証を必要としない共有リンクが誤って作成される恐れがあります。</span><span class="sxs-lookup"><span data-stu-id="9159b-146">If a user forgets to change the link type while sharing a sensitive document, they might accidentally create a sharing link that doesn't require authentication.</span></span>

<span data-ttu-id="9159b-147">既定のリンク設定を組織内のユーザーに対してのみ有効なリンクに変更することにより、このようなリスクを軽減できます。</span><span class="sxs-lookup"><span data-stu-id="9159b-147">You can mitigate this risk by changing the default link setting to a link that only works for people inside your organization.</span></span> <span data-ttu-id="9159b-148">認証されていない人と共有したいユーザーは、そのオプションを意図的に選択することが必要になります。</span><span class="sxs-lookup"><span data-stu-id="9159b-148">Users who want to share with unauthenticated people would then have to specifically select that option.</span></span>

<span data-ttu-id="9159b-149">組織の既定のファイルやフォルダーの共有リンクを設定するには</span><span class="sxs-lookup"><span data-stu-id="9159b-149">To set the default file and folder sharing link for the organization</span></span>
1. <span data-ttu-id="9159b-150">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="9159b-150">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="9159b-151">左側のナビゲーションで **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-151">In the left navigation, click **Sharing**.</span></span>
3. <span data-ttu-id="9159b-152">**[ファイルとフォルダーのリンク]** で、**[自分の組織内のユーザーのみ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9159b-152">Under **File and folder links**, select **Only people in your organization**.</span></span>

   ![SharePoint の既定のリンクの種類設定のスクリーンショット](../media/sharepoint-default-sharing-link-company-link.png)

4. <span data-ttu-id="9159b-154">**[保存]** をクリックします</span><span class="sxs-lookup"><span data-stu-id="9159b-154">Click **Save**</span></span>

<span data-ttu-id="9159b-155">特定のサイトの既定のファイルやフォルダーの共有リンクを設定するには</span><span class="sxs-lookup"><span data-stu-id="9159b-155">To set the default file and folder sharing link for a specific site</span></span>
1. <span data-ttu-id="9159b-156">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="9159b-156">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="9159b-157">左側のナビゲーションで、**[サイト]** を展開し、**[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-157">In the left navigation, expand **Sites**, and then click **Active sites**.</span></span>
3. <span data-ttu-id="9159b-158">変更するサイトを選択し、**[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-158">Select the site you want to change, and then click **Sharing**.</span></span>
4. <span data-ttu-id="9159b-159">**[既定の共有リンクの種類]** で、**[組織レベルの設定と同じ]** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="9159b-159">Under **Default sharing link type**,  clear the **Same as organization-level setting** check box.</span></span>

   ![SharePoint のサイトレベルの既定のリンクの種類設定のスクリーンショット](../media/sharepoint-organization-anyone-link-permissions-site.png)

5. <span data-ttu-id="9159b-161">**[組織内のユーザーのみ]** オプションを選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-161">Select the **Only people in your organization** option and click **Save**.</span></span>

## <a name="prevent-unauthenticated-sharing-of-sensitive-content"></a><span data-ttu-id="9159b-162">機密コンテンツの認証されていない共有を防止する</span><span class="sxs-lookup"><span data-stu-id="9159b-162">Prevent unauthenticated sharing of sensitive content</span></span>

<span data-ttu-id="9159b-163">[データ損失防止 (DLP)](../compliance/dlp-learn-about-dlp.md) を使用して、機密コンテンツの認証されていない共有を防止することができます。</span><span class="sxs-lookup"><span data-stu-id="9159b-163">You can use [data loss prevention (DLP)](../compliance/dlp-learn-about-dlp.md) to prevent unauthenticated sharing of sensitive content.</span></span> <span data-ttu-id="9159b-164">データ損失防止は、ファイルの秘密度ラベル、保持ラベル、ファイル自体に含まれている機密情報に基づいてアクションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="9159b-164">Data loss prevention can take action based on a file's sensitivity label, retention label, or sensitive information in the file itself.</span></span>

<span data-ttu-id="9159b-165">DLP ルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="9159b-165">To create a DLP rule</span></span>
1. <span data-ttu-id="9159b-166">Microsoft 365 コンプライアンス管理センターで、[[データ損失防止] ページ](https://compliance.microsoft.com/datalossprevention)に移動します。</span><span class="sxs-lookup"><span data-stu-id="9159b-166">In the Microsoft 365 compliance admin center, go to the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention).</span></span>
2. <span data-ttu-id="9159b-167">**[ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-167">Click **Create policy**.</span></span>
3. <span data-ttu-id="9159b-168">**[カスタム]** を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-168">Choose **Custom** and click **Next**.</span></span>
4. <span data-ttu-id="9159b-169">ポリシーの名前を入力し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-169">Type a name for the policy and click **Next**.</span></span>
5. <span data-ttu-id="9159b-170">**[ポリシーを適用する場所]** ページで、**SharePoint サイト** と **OneDrive アカウント** 以外のすべての設定をオフにし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-170">On the **Locations to apply the policy** page turn off all settings except **SharePoint sites** and **OneDrive accounts**, and then click **Next**.</span></span>
6. <span data-ttu-id="9159b-171">**[ポリシーの設定を定義]** ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-171">On the **Define policy settings** page, click **Next**.</span></span>
7. <span data-ttu-id="9159b-172">**[高度な DLP ルールのカスタマイズ]** ページで **[ルールの作成]** をクリックし、ルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="9159b-172">On the **Customize advanced DLP rules** page, click **Create rule** and type a name for the rule.</span></span>
8. <span data-ttu-id="9159b-173">[ **条件** で、[ **条件の追加**] をクリックし、[ **コンテンツを含む** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9159b-173">Under **Conditions**, click **Add condition**, and choose **Content contains**.</span></span>
9. <span data-ttu-id="9159b-174">**[追加]** をクリックして、認証されていない共有を防止する情報の種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="9159b-174">Click **Add** and choose the type of information for which you want to prevent unauthenticated sharing.</span></span>

   ![条件オプション、機密情報の種類、機密情報ラベル、保持ラベルのスクリーンショット。](../media/limit-accidental-exposure-dlp-conditions.png)

10. <span data-ttu-id="9159b-176">[ **アクション** ] で、[ **アクションの追加**] をクリックし [ **アクセスを制限する、またはMicrosoft 365のロケーションでコンテンツを暗号化する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9159b-176">Under **Actions** click **Add an action** and choose **Restrict access or encrypt the content in Microsoft 365 locations**.</span></span>
11. <span data-ttu-id="9159b-177">**[アクセスを制限する、または Microsoft 365 のロケーションでコンテンツを暗号化する]** チェック ボックスをオンにし、**[Only people who were given access to the content through the "Anyone withe the link" options]** ([リンクを知っているすべてのユーザー] オプションを通してコンテンツへのアクセス権を付与されたユーザーのみ) オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9159b-177">Select the **Restrict access or encrypt the content in Microsoft 365 locations** check box and then choose the **Only people who were given access to the content through the "Anyone withe the link" options** option.</span></span>

      ![DLP ルールのアクションオプションのスクリーンショット](../media/limit-accidental-exposure-dlp-anyone-links.png)

12. <span data-ttu-id="9159b-179">**[保存]** をクリックし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-179">Click **Save** and then click **Next**.</span></span>
13. <span data-ttu-id="9159b-180">テスト オプションを選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-180">Choose your test options and click **Next**.</span></span>
14. <span data-ttu-id="9159b-181">**[送信]** をクリックしてから、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-181">Click **Submit**, and then click **Done**.</span></span>

## <a name="protect-against-malicious-files"></a><span data-ttu-id="9159b-182">悪意のあるファイルから保護する</span><span class="sxs-lookup"><span data-stu-id="9159b-182">Protect against malicious files</span></span>

<span data-ttu-id="9159b-183">匿名ユーザーにファイルのアップロードを許可する場合、悪意のあるファイルをアップロードされるリスクが高くなります。</span><span class="sxs-lookup"><span data-stu-id="9159b-183">When you allow anonymous users to upload files, you're at an increased risk of someone uploading a malicious file.</span></span> <span data-ttu-id="9159b-184">Microsoft 365 では、Defender for Office 365 の *安全な添付ファイル* 機能を使用することにより、アップロードされたファイルを自動的にスキャンし、安全でないことが判明したファイルを検疫できます。</span><span class="sxs-lookup"><span data-stu-id="9159b-184">In Microsoft 365, you can use the *Safe Attachments* feature in Defender for Office 365 to automatically scan uploaded files and quarantine files that are found to be unsafe.</span></span>

<span data-ttu-id="9159b-185">安全な添付ファイル機能をオンにするには</span><span class="sxs-lookup"><span data-stu-id="9159b-185">To turn on safe attachments</span></span>
1. <span data-ttu-id="9159b-186">セキュリティ/コンプライアンス管理センターで、[ATP 安全な添付ファイル ページ](https://protection.office.com/safeattachmentv2)を開きます。</span><span class="sxs-lookup"><span data-stu-id="9159b-186">Open the [ATP Safe Attachments page](https://protection.office.com/safeattachmentv2) in the Security and Compliance admin center.</span></span>
2. <span data-ttu-id="9159b-187">**[グローバル設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-187">Click **Global settings**.</span></span>
3. <span data-ttu-id="9159b-188">SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9159b-188">Turn on ATP for SharePoint, OneDrive, and Microsoft Teams.</span></span>

   ![セキュリティ/コンプライアンス センターの安全な添付ファイル設定のスクリーンショット](../media/safe-attachments-setting.png)

4. <span data-ttu-id="9159b-190">必要に応じて安全なドキュメントもオンにし、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-190">Optionally turn on Safe Documents as well, and then click **Save**</span></span>

<span data-ttu-id="9159b-191">その他のガイドについては、「[SharePoint、OneDrive、Microsoft Teams 用の ATP](../security/office-365-security/mdo-for-spo-odb-and-teams.md)」と「[SharePoint、OneDrive、Microsoft Teams 用の ATP を有効にする](../security/office-365-security/turn-on-mdo-for-spo-odb-and-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9159b-191">See [ATP for SharePoint, OneDrive, and Microsoft Teams](../security/office-365-security/mdo-for-spo-odb-and-teams.md) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](../security/office-365-security/turn-on-mdo-for-spo-odb-and-teams.md) for additional guidance.</span></span>

## <a name="add-copyright-information-to-your-files"></a><span data-ttu-id="9159b-192">ファイルに著作権情報を追加する</span><span class="sxs-lookup"><span data-stu-id="9159b-192">Add copyright information to your files</span></span>

<span data-ttu-id="9159b-193">Microsoft 365 コンプライアンス管理センターで秘密度ラベルを使用する場合、組織の Office ドキュメントに透かしやヘッダーかフッターが自動的に追加されるようにラベルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="9159b-193">If you use sensitivity labels in the Microsoft 365 Compliance admin center, you can configure your labels to add a watermark or a header or footer automatically to your organization's Office documents.</span></span> <span data-ttu-id="9159b-194">このようにすることで、共有ファイルに著作権などの所有者情報が確実に含められるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9159b-194">In this way, you can make sure that shared files contain copyright or other ownership information.</span></span>

<span data-ttu-id="9159b-195">ラベルが付けられたファイルにフッターを追加するには</span><span class="sxs-lookup"><span data-stu-id="9159b-195">To add a footer to a labeled file</span></span>

1. <span data-ttu-id="9159b-196">[Microsoft 365 コンプライアンス管理センター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="9159b-196">Open the [Microsoft 365 compliance admin center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="9159b-197">左側のナビゲーションにある **[ソリューション]** で、**[情報の保護]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-197">In the left navigation, under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="9159b-198">フッターを追加するラベルをクリックし、**[ラベルの編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-198">Click the label that you want to have add a footer, and then click **Edit label**.</span></span>
4. <span data-ttu-id="9159b-199">**[次へ]** をクリックして **[コンテンツのマーキング]** タブに移動し、コンテンツのマーキングを **オン** にします。</span><span class="sxs-lookup"><span data-stu-id="9159b-199">Click **Next** to reach the **Content marking** tab, and then turn **On** content marking.</span></span>
5. <span data-ttu-id="9159b-200">追加するテキストの種類のチェック ボックスをオンにして、**[テキストをカスタマイズする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-200">Select the check box for the type of text you want to add, and then click **Customize text**.</span></span>
6. <span data-ttu-id="9159b-201">ドキュメントに追加するテキストを入力し、目的のテキスト オプションを選択して、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-201">Type the text that you want added to your documents, select the text options that you want, and then click **Save**.</span></span></br>
   <span data-ttu-id="9159b-202">![秘密度ラベルのコンテンツのマーキング設定のスクリーンショット](../media/content-marking-for-anonymous-sharing.png)</span><span class="sxs-lookup"><span data-stu-id="9159b-202">![Screenshot of the content marking settings for a sensitivity label](../media/content-marking-for-anonymous-sharing.png)</span></span>
7. <span data-ttu-id="9159b-203">**[次へ]** をクリックしてウィザードの最後に移動し、**[Save label]** (ラベルの保存) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9159b-203">Click **Next** to reach the end of the wizard, and then click **Save label**.</span></span>

<span data-ttu-id="9159b-204">コンテンツのマーキングがラベルに対して有効になっている状態で、そのラベルをユーザーが適用すると、Office ドキュメントに指定したテキストが追加されます。</span><span class="sxs-lookup"><span data-stu-id="9159b-204">With content marking enabled for the label, the text you specified will be added to Office documents when a user applies that label.</span></span>

## <a name="see-also"></a><span data-ttu-id="9159b-205">関連項目</span><span class="sxs-lookup"><span data-stu-id="9159b-205">See Also</span></span>

[<span data-ttu-id="9159b-206">秘密度ラベルの概要</span><span class="sxs-lookup"><span data-stu-id="9159b-206">Overview of sensitivity labels</span></span>](/Office365/SecurityCompliance/sensitivity-labels)

[<span data-ttu-id="9159b-207">ゲストと共有するときにファイルの偶発的な公開を制限する</span><span class="sxs-lookup"><span data-stu-id="9159b-207">Limit accidental exposure to files when sharing with guests</span></span>](share-limit-accidental-exposure.md)

[<span data-ttu-id="9159b-208">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="9159b-208">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)
