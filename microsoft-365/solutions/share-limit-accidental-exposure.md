---
title: 偶発的な公開を制限する
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
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: 組織外のユーザーとファイルを共有する場合、情報が偶発的に公開されることを防止する方法を説明します。
ms.openlocfilehash: 1dffa40a0c21f5f611492d5a098a98f8aaa726a5
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2021
ms.locfileid: "53326989"
---
# <a name="limit-accidental-exposure-to-files-when-sharing-with-people-outside-your-organization"></a><span data-ttu-id="436f5-103">組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する</span><span class="sxs-lookup"><span data-stu-id="436f5-103">Limit accidental exposure to files when sharing with people outside your organization</span></span>

<span data-ttu-id="436f5-104">ファイルやフォルダーを組織外のユーザーと共有する場合、機密情報を誤って共有する可能性を減らすことができるさまざまなオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="436f5-104">When sharing files and folders with people outside your organization, there are various options to reduce the chances of accidentally sharing sensitive information.</span></span> <span data-ttu-id="436f5-105">組織のニーズに合わせて、この記事のオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="436f5-105">You can choose from the options in this article to best meet the needs of your organization.</span></span>

## <a name="use-best-practices-for-anyone-links"></a><span data-ttu-id="436f5-106">[すべてのユーザー] リンクのベスト プラクティスを使用する</span><span class="sxs-lookup"><span data-stu-id="436f5-106">Use best practices for Anyone links</span></span>

<span data-ttu-id="436f5-107">組織内のユーザーが認証されていない共有を行う必要があるが、認証されていないユーザーがコンテンツを変更することを懸念している場合は、組織で認証されていない共有を行う方法のガイダンスについて、「[認証されていない共有のベスト プラクティス](best-practices-anonymous-sharing.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="436f5-107">If people in your organization need to do unauthenticated sharing, but you're concerned about unauthenticated people modifying content, read [Best practices for unauthenticated sharing](best-practices-anonymous-sharing.md) for guidance on how to work with unauthenticated sharing in your organization.</span></span>

## <a name="turn-off-anyone-links"></a><span data-ttu-id="436f5-108">[すべてのユーザー] リンクをオフにする</span><span class="sxs-lookup"><span data-stu-id="436f5-108">Turn off Anyone links</span></span>

<span data-ttu-id="436f5-109">適切なコンテンツに対して [*すべてのユーザー*] リンクを有効にしておくことをお勧めします。これは、共有の最も簡単な方法であり、ユーザーが IT 部門の管理外にある他のソリューションを求めるリスクを軽減できるためです。</span><span class="sxs-lookup"><span data-stu-id="436f5-109">We recommend leaving *Anyone* links enabled for appropriate content because it's the easiest way to share and can help reduce the risk of users seeking other solutions that are outside the control of your IT department.</span></span> <span data-ttu-id="436f5-110">[*すべてのユーザー*] リンクを他の人に転送できますが、リンクを持っているユーザーのみファイルへアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="436f5-110">*Anyone* links can be forwarded to others, but file access is only available to those who have the link.</span></span>

<span data-ttu-id="436f5-111">SharePoint、グループ、または Teams のコンテンツにアクセスするとき、組織外のユーザーに常に認証を要求する場合、[*すべてのユーザー*] 共有をオフにできます。</span><span class="sxs-lookup"><span data-stu-id="436f5-111">If you always want people outside your organization to authenticate when accessing content in SharePoint, Groups, or Teams, you can turn off *Anyone* sharing.</span></span> <span data-ttu-id="436f5-112">これにより、ユーザーは認証されていないコンテンツを共有することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="436f5-112">This will prevent users from unauthenticated sharing of content.</span></span>

<span data-ttu-id="436f5-113">[*すべてのユーザー*] リンクを無効にしても、ユーザーは [*特定のユーザー*] リンクを使用してゲストと簡単に共有できます。</span><span class="sxs-lookup"><span data-stu-id="436f5-113">If you disable *Anyone* links, users can still easily share with guests using *Specific people* links.</span></span> <span data-ttu-id="436f5-114">この場合、すべての組織外のユーザーは、共有コンテンツにアクセスする前に認証を受ける必要があります。</span><span class="sxs-lookup"><span data-stu-id="436f5-114">In this case, all people outside your organization will be required to authenticate before they can access the shared content.</span></span>

<span data-ttu-id="436f5-115">ニーズに応じて、特定のサイトまたは組織全体の [*すべてのユーザー*] リンクを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="436f5-115">Depending on your needs, you can disable *Anyone* links for specific sites, or for your whole organization.</span></span>

<span data-ttu-id="436f5-116">組織の [*すべてのユーザー*] リンクをオフにするには</span><span class="sxs-lookup"><span data-stu-id="436f5-116">To turn off *Anyone* links for your organization</span></span>
1. <span data-ttu-id="436f5-117">SharePoint 管理センターの左側のナビゲーションで、[**共有**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="436f5-117">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="436f5-118">SharePoint 外部共有設定を [**新規および既存のゲスト**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="436f5-118">Set the SharePoint external sharing settings to **New and existing guests**.</span></span>

   ![組織レベルの SharePoint サイトの外部共有設定のスクリーンショット](../media/sharepoint-organization-external-sharing-controls-new-users.png)

3. <span data-ttu-id="436f5-120">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="436f5-120">Click **Save**.</span></span>

<span data-ttu-id="436f5-121">サイトの [*すべてのユーザー*] リンクをオフにするには</span><span class="sxs-lookup"><span data-stu-id="436f5-121">To turn off *Anyone* links for a site</span></span>
1. <span data-ttu-id="436f5-122">SharePoint 管理センターの左側のナビゲーションで、[**サイト**] を展開して [**アクティブなサイト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="436f5-122">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="436f5-123">構成するサイトを選択します。</span><span class="sxs-lookup"><span data-stu-id="436f5-123">Select the site that you want to configure.</span></span>
3. <span data-ttu-id="436f5-124">リボンで [**共有**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="436f5-124">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="436f5-125">共有が [**新規および既存のゲスト**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="436f5-125">Ensure that sharing is set to **New and existing guests**.</span></span>

   ![サイト レベルの SharePoint サイトの外部共有設定のスクリーンショット](../media/sharepoint-site-external-sharing-settings.png)

5. <span data-ttu-id="436f5-127">変更を加えた場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="436f5-127">If you made changes, click **Save**.</span></span>

## <a name="domain-filtering"></a><span data-ttu-id="436f5-128">ドメインのフィルター処理</span><span class="sxs-lookup"><span data-stu-id="436f5-128">Domain filtering</span></span>

<span data-ttu-id="436f5-129">ドメイン許可または拒否リストを使用して、ユーザーが組織外のユーザーとの共有を行うときに使用できるドメインを指定できます。</span><span class="sxs-lookup"><span data-stu-id="436f5-129">You can use domain allow or deny lists to specify which domains your users can use when sharing with people outside your organization.</span></span>

<span data-ttu-id="436f5-130">許可リストを使用すると、組織内のユーザーが組織外のユーザーと共有できるドメインのリストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="436f5-130">With an allow list, you can specify a list of domains where users in your organization can share with people outside your organization.</span></span> <span data-ttu-id="436f5-131">他のドメインとの共有はブロックされています。</span><span class="sxs-lookup"><span data-stu-id="436f5-131">Sharing with other domains is blocked.</span></span> <span data-ttu-id="436f5-132">組織が特定のドメイン リストのユーザーとのみ共同作業を行う場合、この機能を使用して他のドメインとの共有を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="436f5-132">If your organization only collaborates with people from a list of specific domains, you can use this feature to prevent sharing with other domains.</span></span>

<span data-ttu-id="436f5-133">拒否リストを使用すると、組織内のユーザーが組織外のユーザーと共有できないドメインのリストを指定できます。</span><span class="sxs-lookup"><span data-stu-id="436f5-133">With a deny list, you can specify a list of domains from which users in your organization cannot share with people outside your organization.</span></span> <span data-ttu-id="436f5-134">リストのドメインとの共有はブロックされています。</span><span class="sxs-lookup"><span data-stu-id="436f5-134">Sharing with the listed domains is blocked.</span></span> <span data-ttu-id="436f5-135">これは、たとえば、組織内のコンテンツへのアクセスを禁止したい競合相手がいる場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="436f5-135">This can be useful if you have competitors, for example, who you want to prevent from accessing content in your organization.</span></span>

<span data-ttu-id="436f5-136">許可リストと拒否リストは、ゲストとの共有にのみ影響します。</span><span class="sxs-lookup"><span data-stu-id="436f5-136">The allow and deny lists only affect sharing with guests.</span></span> <span data-ttu-id="436f5-137">禁止されたドメインのユーザーは、無効にしていない場合は、[*すべてのユーザー*] リンクを使用して共有できます。</span><span class="sxs-lookup"><span data-stu-id="436f5-137">Users can still share with people from prohibited domains by using *Anyone* links if you haven't disabled them.</span></span> <span data-ttu-id="436f5-138">ドメインの許可リストと拒否リストで最良の結果を得るには、上記のように [*すべてのユーザー*] リンクを無効にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="436f5-138">For best results with domain allow and deny lists, consider disabling *Anyone* links as described above.</span></span>

<span data-ttu-id="436f5-139">ドメイン許可リストまたは拒否リストを設定するには</span><span class="sxs-lookup"><span data-stu-id="436f5-139">To set up a domain allow or deny list</span></span>
1. <span data-ttu-id="436f5-140">SharePoint 管理センターの左側のナビゲーションで、**[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="436f5-140">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="436f5-141">[**外部共有の詳細設定**] で、[**ドメインごとに外部共有を制限する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="436f5-141">Under **Advanced settings for external sharing**, select the **Limit external sharing by domain** check box.</span></span>
3. <span data-ttu-id="436f5-142">[**ドメインを追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="436f5-142">Click **Add domains**.</span></span>
4. <span data-ttu-id="436f5-143">ドメインをブロックするかどうかを選択し、ドメインを入力して、[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="436f5-143">Select whether you want to block domains, type the domains, and click **OK**.</span></span>

   ![ドメイン設定による SharePoint 制限外部共有のスクリーンショット](../media/sharepoint-sharing-block-domain.png)

5. <span data-ttu-id="436f5-145">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="436f5-145">Click **Save**.</span></span>

<span data-ttu-id="436f5-146">SharePoint および OneDrive よりも高いレベルでドメインによる共有を制限する場合、Azure Active Directory で「[B2B ユーザーに対する特定組織からの招待を許可またはブロック](/azure/active-directory/b2b/allow-deny-list)」できます。</span><span class="sxs-lookup"><span data-stu-id="436f5-146">If you want to limit sharing by domain at a higher level than SharePoint and OneDrive, you can [allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list) in Azure Active Directory.</span></span> <span data-ttu-id="436f5-147">(これらの設定を SharePoint と OneDrive に反映させるには、[SharePoint および OneDrive の Azure AD B2B プレビューとの統合](/sharepoint/sharepoint-azureb2b-integration-preview)を構成する必要があります。)</span><span class="sxs-lookup"><span data-stu-id="436f5-147">(You must configure the [SharePoint and OneDrive integration with Azure AD B2B Preview](/sharepoint/sharepoint-azureb2b-integration-preview) for these settings to affect SharePoint and OneDrive.)</span></span>

## <a name="limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups"></a><span data-ttu-id="436f5-148">組織外のユーザーとのファイル、フォルダー、およびサイトの共有を特定のセキュリティ グループに制限する</span><span class="sxs-lookup"><span data-stu-id="436f5-148">Limit sharing of files, folders, and sites with people outside your organization to specified security groups</span></span>

<span data-ttu-id="436f5-149">組織外のユーザーとのファイル、フォルダー、およびサイトの共有を特定のセキュリティ グループのメンバーに制限できます。</span><span class="sxs-lookup"><span data-stu-id="436f5-149">You can restrict sharing of files, folders, and sites with people outside your organization to members of a specific security group.</span></span> <span data-ttu-id="436f5-150">これは、外部共有を有効にしたいが、承認ワークフローまたは要求プロセスを使用する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="436f5-150">This is useful if you want to enable external sharing, but with an approval workflow or request process.</span></span> <span data-ttu-id="436f5-151">あるいは、ユーザーがセキュリティ グループに追加され、外部との共有が許可される前に、ユーザーにトレーニング コースの完了を要求する可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="436f5-151">Alternatively, you might require your users to complete a training course before they're added to the security group and are allowed to share externally.</span></span>

<span data-ttu-id="436f5-152">セキュリティ グループのメンバーに外部共有を制限するには</span><span class="sxs-lookup"><span data-stu-id="436f5-152">To limit external sharing to members of a security group</span></span>
1. <span data-ttu-id="436f5-153">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)の左側のナビゲーションにある **[ポリシー]** で、**[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="436f5-153">In the [SharePoint admin center](https://admin.microsoft.com/sharepoint), in the left navigation, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="436f5-154">**[外部共有]** で、**[その他の外部共有の設定]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="436f5-154">Under **External sharing**, expand **More external sharing settings**.</span></span>

3. <span data-ttu-id="436f5-155">**[特定のセキュリティ グループ内のユーザーにのみ、外部との共有を許可する]** を選択し、**[セキュリティ グループを管理する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="436f5-155">Select **Allow only users in specific security groups to share externally**, and then select **Manage security groups**.</span></span>

    ![[セキュリティグループを管理する] パネルのスクリーンショット](/sharepoint/sharepointonline/media/manage-security-groups.png)

4. <span data-ttu-id="436f5-157">**[セキュリティ グループを追加する]** ボックスに、セキュリティ グループの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="436f5-157">In the **Add a security group** box, enter a name for a security group.</span></span> <span data-ttu-id="436f5-158">[セキュリティ グループ] ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="436f5-158">The security group box appears.</span></span>

5. <span data-ttu-id="436f5-159">セキュリティ グループ名の横にある **[共有可能]** ドロップダウンから、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="436f5-159">Next to the security group name, from the **Can share with** dropdown, select either:</span></span>

    - <span data-ttu-id="436f5-160">**認証されたゲストのみ** (既定値)</span><span class="sxs-lookup"><span data-stu-id="436f5-160">**Authenticated guests only** (default)</span></span>
    - <span data-ttu-id="436f5-161">**すべてのユーザー**</span><span class="sxs-lookup"><span data-stu-id="436f5-161">**Anyone**</span></span>

6. <span data-ttu-id="436f5-162">**[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="436f5-162">Select **Save**.</span></span>

<span data-ttu-id="436f5-163">これは、ファイル、フォルダー、およびサイトに影響しますが、Microsoft 365 グループまたは Teams には影響しません。</span><span class="sxs-lookup"><span data-stu-id="436f5-163">Note that this affects files, folders, and sites, but not Microsoft 365 groups or Teams.</span></span> <span data-ttu-id="436f5-164">メンバーがゲストを非公開 Microsoft 365 グループまたは Microsoft Teams の非公開チームに招待すると、招待は認証のためにグループまたはチームの所有者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="436f5-164">When members invite guests to a private Microsoft 365 group or a private team in Microsoft Teams, the invitation is sent to the group or team owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="436f5-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="436f5-165">See Also</span></span>

[<span data-ttu-id="436f5-166">セキュリティで保護されたゲスト共有の環境を作成する</span><span class="sxs-lookup"><span data-stu-id="436f5-166">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="436f5-167">匿名ユーザーとファイルおよびフォルダーを共有するためのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="436f5-167">Best practices for sharing files and folders with anonymous users</span></span>](best-practices-anonymous-sharing.md)
