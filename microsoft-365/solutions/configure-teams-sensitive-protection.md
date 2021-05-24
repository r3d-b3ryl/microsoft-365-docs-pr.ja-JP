---
title: 機密データに対する保護機能を使用してチームを構成する
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
recommendations: false
description: 機密データに対する保護機能を使用してチームを展開する方法について説明します。
ms.openlocfilehash: 0590e63aa0feb5b699eca98c0056604fe09b77f5
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583654"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a><span data-ttu-id="890e5-103">機密データに対する保護機能を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="890e5-103">Configure teams with protection for sensitive data</span></span>

<span data-ttu-id="890e5-104">この記事では、機密レベルの保護機能を使用してチームをセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="890e5-104">In this article, we look at setting up a team for a sensitive level of protection.</span></span> <span data-ttu-id="890e5-105">この記事の手順を実行する前に、「[基本保護機能を使用してチームを展開する](configure-teams-baseline-protection.md)」の手順を完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="890e5-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span> <span data-ttu-id="890e5-106">機密層は、基本層の上に次のような追加保護機能を実現します。</span><span class="sxs-lookup"><span data-stu-id="890e5-106">The sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="890e5-p102">ゲスト共有を有効または無効にし、管理されていないデバイスの SharePoint コンテンツへのアクセスを Web のみに制限するチームの秘密度ラベル。このラベルは、ファイルの分類にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="890e5-p102">A sensitivity label for the team that allows you to turn guest sharing on or off and limits access to SharePoint content to web-only for unmanaged devices. This label can also be used to classify files.</span></span>
- <span data-ttu-id="890e5-109">より制限の厳しい既定の共有リンクの種類</span><span class="sxs-lookup"><span data-stu-id="890e5-109">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="890e5-110">チーム所有者のみがプライベート チャネルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="890e5-110">Only team owners can create private channels.</span></span>

## <a name="guest-sharing"></a><span data-ttu-id="890e5-111">ゲスト共有</span><span class="sxs-lookup"><span data-stu-id="890e5-111">Guest sharing</span></span>

<span data-ttu-id="890e5-112">会社の性質に応じて、機密データを含むチームのゲスト共有を有効または無効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="890e5-112">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain sensitive data.</span></span> <span data-ttu-id="890e5-113">チーム内の組織外のユーザーと共同作業する場合は、ゲスト共有を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="890e5-113">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="890e5-114">Microsoft 365 には、セキュリティとコンプライアンスのためのさまざまな機能が含まれており、機密コンテンツを安全に共有できます。</span><span class="sxs-lookup"><span data-stu-id="890e5-114">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="890e5-115">通常、組織外のユーザーに直接コンテンツを電子メールで送信するよりも、セキュリティが強化されています。</span><span class="sxs-lookup"><span data-stu-id="890e5-115">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="890e5-116">ゲストと安全に共有する方法の詳細については、次のリソースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="890e5-116">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="890e5-117">組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する</span><span class="sxs-lookup"><span data-stu-id="890e5-117">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)
- [<span data-ttu-id="890e5-118">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="890e5-118">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

<span data-ttu-id="890e5-119">ゲスト共有を許可または禁止するには、関連付けられている SharePoint サイトのチーム レベルとサイト レベルの共有コントロールに対して、秘密度ラベルを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="890e5-119">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="890e5-120">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="890e5-120">Sensitivity labels</span></span>

<span data-ttu-id="890e5-121">機密保護レベルについては、秘密度ラベルを使用してチームを分類します。</span><span class="sxs-lookup"><span data-stu-id="890e5-121">For the sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="890e5-122">このラベルは、このチームまたは他のチームの個別のファイル、または SharePoint や OneDrive などのその他の場所にあるファイルを分類するために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="890e5-122">This label can also be used to classify individual files in this or other teams, or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="890e5-123">最初の手順では、Teams の秘密度ラベルを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="890e5-123">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="890e5-124">詳細は、「[秘密度ラベルを使用して、Microsoft Teams、Office 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="890e5-124">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md) for details.</span></span>

<span data-ttu-id="890e5-125">組織に既に秘密度ラベルを展開している場合は、ラベル戦略全体にこのラベルがどのように適合しているかを検討してください。</span><span class="sxs-lookup"><span data-stu-id="890e5-125">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="890e5-126">組織のニーズを満たす必要がある場合、名前または設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="890e5-126">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="890e5-127">Teams の秘密度ラベルを有効にしたら、次の手順ではラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="890e5-127">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="890e5-128">秘密度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="890e5-128">To create a sensitivity label</span></span>
1. <span data-ttu-id="890e5-129">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="890e5-129">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="890e5-130">**[ソリューション]** で、**[情報保護]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-130">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="890e5-131">**[ラベルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-131">Click **Create a label**.</span></span>
4. <span data-ttu-id="890e5-132">ラベルに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="890e5-132">Give the label a name.</span></span> <span data-ttu-id="890e5-133">**Sensitive** をお勧めしますが、既に使用されている別の名前を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="890e5-133">We suggest **Sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="890e5-134">表示名と説明を追加し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-134">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="890e5-135">**Define the scope for this label** (このラベルの範囲の定義) ページで、**[Files & emails]** (ファイルとメール) と **[Groups & sites]** (グループとサイト) を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-135">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="890e5-136">**[Choose protection settings for files and emails]** (ファイルやメールの保護の設定の選択) ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-136">On the **Choose protection settings for files and emails** page, click **Next**.</span></span>
8. <span data-ttu-id="890e5-137">*[ファイルやメールの自動ラベル付け]* ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-137">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
9. <span data-ttu-id="890e5-138">**[Define protection settings for groups and sites]** (グループやサイトの保護の設定の定義) ページで、**[プライバシーと外部ユーザー アクセス設定]** と **[デバイス アクセスと外部共有設定]** を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-138">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
10. <span data-ttu-id="890e5-139">**[Define privacy and external user access settings]** (プライバシーと外部ユーザー アクセス設定の定義) ページの **[プライバシー]** で、**[プライベート]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="890e5-139">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
11. <span data-ttu-id="890e5-140">ゲスト アクセスを許可する場合は、**[外部ユーザーのアクセス]** で、**[Let Microsoft 365 Group owners add people outside your organization to the group as guests]** (Microsoft 365 グループ所有者が組織外のユーザーをグループに追加できるようにする) を選択します。</span><span class="sxs-lookup"><span data-stu-id="890e5-140">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
12. <span data-ttu-id="890e5-141">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-141">Click **Next**.</span></span>
13. <span data-ttu-id="890e5-142">**[Define external sharing and device access settings]** (外部共有とデバイス アクセス設定の定義) ページで、**[Control external sharing from labeled SharePoint sites]** (ラベル付き SharePoint サイトからの外部共有の制御) を選択します。</span><span class="sxs-lookup"><span data-stu-id="890e5-142">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
14. <span data-ttu-id="890e5-143">**[Content can be shared with]** (コンテンツの共有先) で、ゲスト アクセスを許可する場合には **[新規および既存のゲスト]** を選択し、許可しない場合には **[組織内のユーザーのみ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="890e5-143">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
15. <span data-ttu-id="890e5-144">**[非管理対象デバイスからのアクセス]** で、**[制限付きの、Web のみのアクセスを許可する]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="890e5-144">Under **Access from unmanaged devices**, choose **Allow limited, web-only access**.</span></span>
16. <span data-ttu-id="890e5-145">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-145">Click **Next**.</span></span>
17. <span data-ttu-id="890e5-146">**[Auto-labeling for database columns]** (データベースの列の自動ラベル付け) ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-146">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
18. <span data-ttu-id="890e5-147">**[ラベルの作成]** をクリックし、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-147">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="890e5-148">ラベルを作成したら、それを使用するユーザーに発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="890e5-148">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="890e5-149">機密保護のために、すべてのユーザーがラベルを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="890e5-149">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="890e5-150">**[情報保護]** ページの [**ラベルポリシー**] タブで、ラベルを Microsoft 365 コンプライアンス センターに発行します。</span><span class="sxs-lookup"><span data-stu-id="890e5-150">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="890e5-151">すべてのユーザーに適用する既存のポリシーがある場合は、そのポリシーにこのラベルを追加します。</span><span class="sxs-lookup"><span data-stu-id="890e5-151">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="890e5-152">新しいポリシーを作成する必要がある場合は、「[ラベル ポリシーを作成して秘密度ラベルを発行する](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="890e5-152">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="890e5-153">チームを作成する</span><span class="sxs-lookup"><span data-stu-id="890e5-153">Create a team</span></span>

<span data-ttu-id="890e5-154">機密のシナリオの詳細な構成は、チームに関連付けられている SharePoint サイトで行います。次の手順では、チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="890e5-154">Further configuration of the sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="890e5-155">機密情報のチームを作成するには</span><span class="sxs-lookup"><span data-stu-id="890e5-155">To create a team for sensitive information</span></span>
1. <span data-ttu-id="890e5-156">Teams で、アプリの左側にある **[Teams]** をクリックして、チーム リストの下部にある **[チームに参加またはチームの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-156">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="890e5-157">**[チームの作成]** (最初のカード、左上隅) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-157">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="890e5-158">**[初めからチームを作成する]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="890e5-158">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="890e5-159">**[秘密度]** リストで、作成した **秘密度** ラベルを選びます。</span><span class="sxs-lookup"><span data-stu-id="890e5-159">In the **Sensitivity** list, choose the **sensitive** label that you just created.</span></span>
5. <span data-ttu-id="890e5-160">**[プライバシー]** で、**[プライベート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-160">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="890e5-161">チームの名前を入力し、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-161">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="890e5-162">チームにユーザーを追加し、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-162">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="890e5-163">プライベート チャネルの設定</span><span class="sxs-lookup"><span data-stu-id="890e5-163">Private channel settings</span></span>

<span data-ttu-id="890e5-164">この層では、プライベート チャネルの作成権限をチームの所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="890e5-164">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="890e5-165">プライベート チャネルの作成を制限するには</span><span class="sxs-lookup"><span data-stu-id="890e5-165">To restrict private channel creation</span></span>
1. <span data-ttu-id="890e5-166">チームで、**[その他のオプション]** をクリックしてから、**[チームの管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-166">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="890e5-167">**[設定]** タブで、**[メンバーのアクセス許可]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="890e5-167">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="890e5-168">**[プライベート チャネルを作成する]** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="890e5-168">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="890e5-169">[チーム ポリシー](/MicrosoftTeams/teams-policies)を使用して、プライベート チャネルを作成できるユーザーを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="890e5-169">You can also use [teams policies](/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="890e5-170">SharePoint の設定</span><span class="sxs-lookup"><span data-stu-id="890e5-170">SharePoint settings</span></span>

<span data-ttu-id="890e5-171">秘密度ラベルを使用して新しいチームを作成するたびに、SharePoint で次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="890e5-171">Each time you create a new team with the sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="890e5-172">SharePoint 管理センターでサイトのゲスト共有設定を更新して、*特定のユーザー* に対して既定の共有リンクを更新します。</span><span class="sxs-lookup"><span data-stu-id="890e5-172">Update the guest sharing settings for the site in the SharePoint admin center to update the default sharing link to *Specific people*.</span></span>
- <span data-ttu-id="890e5-173">サイト自体の共有設定を更新し、メンバーがサイトを共有できないようにします。</span><span class="sxs-lookup"><span data-stu-id="890e5-173">Update the site sharing settings in the site itself to prevent members from sharing the site.</span></span>

### <a name="site-default-sharing-link-settings"></a><span data-ttu-id="890e5-174">サイトの既定の共有リンク設定</span><span class="sxs-lookup"><span data-stu-id="890e5-174">Site default sharing link settings</span></span>

<span data-ttu-id="890e5-175">サイトの既定の共有リンクの種類を更新するには</span><span class="sxs-lookup"><span data-stu-id="890e5-175">To update the site default sharing link type</span></span>

1. <span data-ttu-id="890e5-176">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="890e5-176">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="890e5-177">**[サイト]** で、**[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-177">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="890e5-178">チームに関連付けられているサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-178">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="890e5-179">**[ポリシー]** タブで、**[外部共有]** の下側にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-179">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="890e5-180">[既定の共有リンクの種類] で、**[組織レベルの設定と同じ]** チェック ボックスをオフにして、**[特定のユーザー (ユーザーが指定したユーザー人物のみ)]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="890e5-180">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **Specific people (only the people the user specifies)**.</span></span>
6. <span data-ttu-id="890e5-181">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-181">Click **Save**.</span></span>

<span data-ttu-id="890e5-182">チーム作成プロセスの一環としてスクリプトを実行する場合は、`-DefaultSharingLinkType Direct` パラメーターで [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) を使用して、既定の共有リンクを *特定のユーザー* に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="890e5-182">If you want to script this as part of your team creation process, you can use [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) with the `-DefaultSharingLinkType Direct` parameter to change the default sharing link to *Specific people*.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="890e5-183">プライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="890e5-183">Private channels</span></span>

<span data-ttu-id="890e5-184">チームにプライベート チャネルを追加する場合、各プライベート チャネルは、既定の共有設定を使用して新しい SharePoint サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="890e5-184">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="890e5-185">これらのサイトは SharePoint 管理センターでは表示されないので、Set-sposite PowerShell コマンドレットを使用して、ゲスト共有設定を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="890e5-185">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="890e5-186">サイト共有設定</span><span class="sxs-lookup"><span data-stu-id="890e5-186">Site sharing settings</span></span>

<span data-ttu-id="890e5-187">SharePoint サイトがチーム メンバーではないユーザーと共有されないようにするには、SharePoint サイトの共有を所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="890e5-187">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span>

<span data-ttu-id="890e5-188">所有者のみのサイト共有を構成するには</span><span class="sxs-lookup"><span data-stu-id="890e5-188">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="890e5-189">Teams で、更新するチームの **[全般]** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="890e5-189">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="890e5-190">チームのツール バーで、**[ファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-190">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="890e5-191">省略記号をクリックし、**[SharePoint で開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-191">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="890e5-192">基となる SharePoint サイトのツール バーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-192">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="890e5-193">**[サイトの権限]** ウィンドウで、**[サイトの共有]** の **[メンバーが共有する方法を変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-193">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="890e5-194">**[共有アクセス許可**] で、**[サイトの所有者とメンバー、および編集アクセス許可を持つユーザーは、ファイルとフォルダーを共有できますが、サイトの所有者のみがサイトを共有できます]** を選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="890e5-194">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>


## <a name="see-also"></a><span data-ttu-id="890e5-195">関連項目</span><span class="sxs-lookup"><span data-stu-id="890e5-195">See Also</span></span>

[<span data-ttu-id="890e5-196">秘密度ラベルとそのポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="890e5-196">Create and configure sensitivity labels and their policies</span></span>](../compliance/create-sensitivity-labels.md)
