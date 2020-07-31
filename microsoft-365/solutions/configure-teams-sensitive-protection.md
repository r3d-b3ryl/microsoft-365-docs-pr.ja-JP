---
title: 機密データに対する保護機能を使用してチームを構成する
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
description: 機密データに対する保護機能を使用してチームを展開する方法について説明します。
ms.openlocfilehash: 3c68e6690d9fdab28a5dd1369876bec5b3fd9bc7
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46528196"
---
# <a name="configure-teams-with-protection-for-sensitive-data"></a><span data-ttu-id="ecb1b-103">機密データに対する保護機能を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="ecb1b-103">Configure teams with protection for sensitive data</span></span>

<span data-ttu-id="ecb1b-104">この記事では、機密レベルの保護機能を使用してチームをセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-104">In this article, we look at setting up a team for a sensitive level of protection.</span></span> <span data-ttu-id="ecb1b-105">この記事の手順を実行する前に、「[基本保護機能を使用してチームを展開する](configure-teams-baseline-protection.md)」の手順を完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span> <span data-ttu-id="ecb1b-106">機密層は、基本層の上に次のような追加保護機能を実現します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-106">The sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="ecb1b-107">ゲスト共有を有効または無効にし、管理されていないデバイスの SharePoint コンテンツへのアクセスを Web のみに制限するチームの秘密度ラベル。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-107">A sensitivity label for the team that allows you to turn guest sharing on or off and limits access to SharePoint content to web-only for unmanaged devices.</span></span> <span data-ttu-id="ecb1b-108">このラベルは、ファイルを分類するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-108">This label can also be used to classify files.</span></span>
- <span data-ttu-id="ecb1b-109">より制限の厳しい既定の共有リンクの種類</span><span class="sxs-lookup"><span data-stu-id="ecb1b-109">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="ecb1b-110">チーム所有者のみがプライベート チャネルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-110">Only team owners can create private channels.</span></span>

## <a name="guest-sharing"></a><span data-ttu-id="ecb1b-111">ゲスト共有</span><span class="sxs-lookup"><span data-stu-id="ecb1b-111">Guest sharing</span></span>

<span data-ttu-id="ecb1b-112">会社の性質に応じて、機密データを含むチームのゲスト共有を有効または無効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-112">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain sensitive data.</span></span> <span data-ttu-id="ecb1b-113">チーム内の組織外のユーザーと共同作業する場合は、ゲスト共有を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-113">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="ecb1b-114">Microsoft 365 には、セキュリティとコンプライアンスのためのさまざまな機能が含まれており、機密コンテンツを安全に共有できます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-114">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="ecb1b-115">通常、組織外のユーザーに直接コンテンツを電子メールで送信するよりも、セキュリティが強化されています。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-115">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="ecb1b-116">ゲストと安全に共有する方法の詳細については、次のリソースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-116">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="ecb1b-117">組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する</span><span class="sxs-lookup"><span data-stu-id="ecb1b-117">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [<span data-ttu-id="ecb1b-118">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="ecb1b-118">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

<span data-ttu-id="ecb1b-119">ゲスト共有を許可または禁止するには、関連付けられている SharePoint サイトのチーム レベルとサイト レベルの共有コントロールに対して、秘密度ラベルを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-119">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="ecb1b-120">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="ecb1b-120">Sensitivity labels</span></span>

<span data-ttu-id="ecb1b-121">機密保護レベルについては、秘密度ラベルを使用してチームを分類します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-121">For the sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="ecb1b-122">このラベルは、このチームまたは他のチームの個別のファイル、または SharePoint や OneDrive などのその他の場所にあるファイルを分類するために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-122">This label can also be used to classify individual files in this or other teams, or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="ecb1b-123">最初の手順では、Teams の秘密度ラベルを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-123">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="ecb1b-124">詳細は、「[秘密度ラベルを使用して、Microsoft Teams、Office 365 グループ、SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-124">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) for details.</span></span>

<span data-ttu-id="ecb1b-125">組織に既に秘密度ラベルを展開している場合は、ラベル戦略全体にこのラベルがどのように適合しているかを検討してください。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-125">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="ecb1b-126">組織のニーズを満たす必要がある場合、名前または設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-126">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="ecb1b-127">Teams の秘密度ラベルを有効にしたら、次の手順ではラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-127">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="ecb1b-128">秘密度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="ecb1b-128">To create a sensitivity label</span></span>
1. <span data-ttu-id="ecb1b-129">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-129">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="ecb1b-130">**[ソリューション]** で、**[情報保護]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-130">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="ecb1b-131">**[ラベルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-131">Click **Create a label**.</span></span>
4. <span data-ttu-id="ecb1b-132">ラベルに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-132">Give the label a name.</span></span> <span data-ttu-id="ecb1b-133">**sensitive** をお勧めしますが、既に使用されている別の名前を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-133">We suggest **sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="ecb1b-134">ツール ヒントを追加し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-134">Add a tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="ecb1b-135">**[暗号化]** ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-135">On the **Encryption** page, click **Next**.</span></span>
7. <span data-ttu-id="ecb1b-136">このラベルで分類されているファイルにヘッダー、フッター、またはウォーターマークを自動的に追加するには、**[コンテンツのマーキング]** ページで、[コンテンツのマーキング] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-136">On the **Content marking** page, turn on content marking if you want to automatically add a header, footer, or watermark to files that are classified with this label.</span></span>
8. <span data-ttu-id="ecb1b-137">**[サイトとグループの設定]** ページで、**[サイトとグループの設定]** を **[オン]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-137">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
9. <span data-ttu-id="ecb1b-138">**[Office 365 グループに接続されているチーム サイトのプライバシー]** ドロップダウンで、**[非公開 - メンバーのみがサイトにアクセス可能]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-138">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
10. <span data-ttu-id="ecb1b-139">ゲスト アクセスを許可する場合は、**[Ofﬁce 365 グループ所有者が組織外のユーザーをグループに追加できるようにする**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-139">If you want to allow guest access, select the **Let Office 365 group owners add people outside the organization to the group** check box.</span></span> 
11. <span data-ttu-id="ecb1b-140">**[非管理対象デバイス]** で、**[制限付きの、Web のみのアクセスを許可する]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-140">Under **Unmanaged devices**, choose **Allow limited, web-only access**.</span></span>
12. <span data-ttu-id="ecb1b-141">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-141">Click **Next**.</span></span>
13. <span data-ttu-id="ecb1b-142">**[Office アプリの自動ラベル付け]** ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-142">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
14. <span data-ttu-id="ecb1b-143">**[送信]** をクリックしてから、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-143">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="ecb1b-144">ラベルを作成したら、それを使用するユーザーに発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-144">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="ecb1b-145">機密保護のために、すべてのユーザーがラベルを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-145">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="ecb1b-146">**[情報保護]** ページの [**ラベルポリシー**] タブで、ラベルを Microsoft 365 コンプライアンス センターに発行します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-146">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="ecb1b-147">すべてのユーザーに適用する既存のポリシーがある場合は、そのポリシーにこのラベルを追加します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-147">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="ecb1b-148">新しいポリシーを作成する必要がある場合は、「[ラベル ポリシーを作成して秘密度ラベルを発行する](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-148">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="ecb1b-149">チームを作成する</span><span class="sxs-lookup"><span data-stu-id="ecb1b-149">Create a team</span></span>

<span data-ttu-id="ecb1b-150">機密のシナリオの詳細な構成は、チームに関連付けられている SharePoint サイトで行います。次の手順では、チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-150">Further configuration of the sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="ecb1b-151">機密情報のチームを作成するには</span><span class="sxs-lookup"><span data-stu-id="ecb1b-151">To create a team for sensitive information</span></span>
1. <span data-ttu-id="ecb1b-152">Teams で、アプリの左側にある **[Teams]** をクリックして、チーム リストの下部にある **[チームに参加またはチームの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-152">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="ecb1b-153">**[チームの作成]** (最初のカード、左上隅) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-153">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="ecb1b-154">**[初めからチームを作成する]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-154">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="ecb1b-155">**[秘密度]** リストで、作成した**秘密度**ラベルを選びます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-155">In the **Sensitivity** list, choose the **sensitive** label that you just created.</span></span>
5. <span data-ttu-id="ecb1b-156">**[プライバシー]** で、**[プライベート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-156">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="ecb1b-157">チームの名前を入力し、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-157">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="ecb1b-158">チームにユーザーを追加し、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-158">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="ecb1b-159">プライベート チャネルの設定</span><span class="sxs-lookup"><span data-stu-id="ecb1b-159">Private channel settings</span></span>

<span data-ttu-id="ecb1b-160">この層では、プライベート チャネルの作成権限をチームの所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-160">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="ecb1b-161">プライベート チャネルの作成を制限するには</span><span class="sxs-lookup"><span data-stu-id="ecb1b-161">To restrict private channel creation</span></span>
1. <span data-ttu-id="ecb1b-162">チームで、**[その他のオプション]** をクリックしてから、**[チームの管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-162">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="ecb1b-163">**[設定]** タブで、**[メンバーのアクセス許可]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-163">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="ecb1b-164">**[プライベート チャネルを作成する]** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-164">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="ecb1b-165">[チーム ポリシー](https://docs.microsoft.com/MicrosoftTeams/teams-policies)を使用して、プライベート チャネルを作成できるユーザーを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-165">You can also use [teams policies](https://docs.microsoft.com/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="ecb1b-166">SharePoint の設定</span><span class="sxs-lookup"><span data-stu-id="ecb1b-166">SharePoint settings</span></span>

<span data-ttu-id="ecb1b-167">秘密度ラベルを使用して新しいチームを作成するたびに、SharePoint で次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-167">Each time you create a new team with the sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="ecb1b-168">ラベルを作成したときに選択したものと一致するように、SharePoint 管理センターでサイトのゲスト共有設定を更新し、*特定のユーザー*に対して、既定の共有リンクを更新します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-168">Update the guest sharing settings for the site in the SharePoint admin center to match what you chose when you created the label, and update the default sharing link to *Specific people*.</span></span>
- <span data-ttu-id="ecb1b-169">サイト自体の共有の設定を更新し、メンバーがサイトを共有できないようにします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-169">Update the site sharing settings in the site itself to prevent members from sharing the site.</span></span>

### <a name="site-guest-sharing-settings"></a><span data-ttu-id="ecb1b-170">サイトのゲスト共有設定</span><span class="sxs-lookup"><span data-stu-id="ecb1b-170">Site guest sharing settings</span></span>

<span data-ttu-id="ecb1b-171">ラベルを作成したときに選択したゲスト共有設定 (チーム メンバーシップのみに影響します) は、以下のように関連付けられている SharePoint サイトのゲスト共有設定と一致します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-171">The guest sharing setting that you chose when you created the label (which only affects team membership) should match the guest sharing settings for the associated SharePoint site as follows:</span></span>

|<span data-ttu-id="ecb1b-172">ラベルの設定</span><span class="sxs-lookup"><span data-stu-id="ecb1b-172">Label setting</span></span>|<span data-ttu-id="ecb1b-173">SharePoint サイトの設定</span><span class="sxs-lookup"><span data-stu-id="ecb1b-173">SharePoint site setting</span></span>|
|:------------|:----------------------|
|<span data-ttu-id="ecb1b-174">**Ofﬁce 365 グループ所有者が組織外のユーザーをグループに追加できるようにする**が選択されている</span><span class="sxs-lookup"><span data-stu-id="ecb1b-174">**Let Office 365 group owners add people outside the organization to the group** selected</span></span>|<span data-ttu-id="ecb1b-175">**新規および既存のゲスト** (新規チームの既定値)</span><span class="sxs-lookup"><span data-stu-id="ecb1b-175">**New and existing guests** (default for new teams)</span></span>|
|<span data-ttu-id="ecb1b-176">**Ofﬁce 365 グループ所有者が組織外のユーザーをグループに追加できるようにする**が選択されていない</span><span class="sxs-lookup"><span data-stu-id="ecb1b-176">**Let Office 365 group owners add people outside the organization to the group** not selected</span></span>|<span data-ttu-id="ecb1b-177">**組織内のユーザーのみ**</span><span class="sxs-lookup"><span data-stu-id="ecb1b-177">**Only people in your organization**</span></span>|

<span data-ttu-id="ecb1b-178">サイトの設定を更新するには</span><span class="sxs-lookup"><span data-stu-id="ecb1b-178">To update site settings</span></span>
1. <span data-ttu-id="ecb1b-179">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-179">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="ecb1b-180">**[サイト]** で、**[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-180">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="ecb1b-181">チームに関連付けられているサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-181">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="ecb1b-182">**[ポリシー]** タブで、**[外部共有]** の下側にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-182">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="ecb1b-183">秘密度ラベルを作成したときにゲスト共有が許可されていた場合は、**[新規および既存のゲスト]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-183">If you allowed guest sharing when you created the sensitive label, ensure that **New and existing guests** is selected.</span></span> <span data-ttu-id="ecb1b-184">秘密度ラベルを作成したときにゲスト共有が許可されていなかった場合は、**[組織内のユーザーのみ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-184">If you didn't allow sharing when you created the label, choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="ecb1b-185">[既定の共有リンクの種類] で、**[組織レベルの設定と同じ]** チェック ボックスをオフにして、**[特定のユーザー (ユーザーが指定したユーザー人物のみ)]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-185">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **Specific people (only the people the user specifies)**.</span></span>
7. <span data-ttu-id="ecb1b-186">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-186">Click **Save**.</span></span>

<span data-ttu-id="ecb1b-187">これをチーム作成プロセスの一部としてスクリプト化する場合は、次のパラメーターを指定して [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) を使用します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-187">If you want to script this as part of your team creation process, you can use [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) with the following parameters:</span></span>

- <span data-ttu-id="ecb1b-188">`-SharingCapability Disabled` ゲスト共有を無効にするには (既定では有効です)</span><span class="sxs-lookup"><span data-stu-id="ecb1b-188">`-SharingCapability Disabled` to turn off guest sharing (it's on by default)</span></span>
- <span data-ttu-id="ecb1b-189">`-DefaultSharingLinkType Internal` 既定の共有リンクを*特定のユーザー*に変更するには</span><span class="sxs-lookup"><span data-stu-id="ecb1b-189">`-DefaultSharingLinkType Internal` to change the default sharing link to *Specific people*</span></span>

#### <a name="private-channels"></a><span data-ttu-id="ecb1b-190">プライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="ecb1b-190">Private channels</span></span>

<span data-ttu-id="ecb1b-191">チームにプライベート チャネルを追加する場合、各プライベート チャネルは、既定の共有設定を使用して新しい SharePoint サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-191">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="ecb1b-192">これらのサイトは SharePoint 管理センターでは表示されないので、Set-sposite PowerShell コマンドレットを使用して、ゲスト共有設定を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-192">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="ecb1b-193">サイト共有設定</span><span class="sxs-lookup"><span data-stu-id="ecb1b-193">Site sharing settings</span></span>

<span data-ttu-id="ecb1b-194">SharePoint サイトがチーム メンバーではないユーザーと共有されないようにするには、SharePoint サイトの共有を所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-194">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span>

<span data-ttu-id="ecb1b-195">所有者のみのサイト共有を構成するには</span><span class="sxs-lookup"><span data-stu-id="ecb1b-195">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="ecb1b-196">Teams で、更新するチームの **[全般]** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-196">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="ecb1b-197">チームのツール バーで、**[ファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-197">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="ecb1b-198">省略記号をクリックし、**[SharePoint で開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-198">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="ecb1b-199">基となる SharePoint サイトのツール バーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-199">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="ecb1b-200">[サイトの権限] ウィンドウで、**[共有設定]** の **[共有設定の変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-200">In the Site permissions pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
6. <span data-ttu-id="ecb1b-201">**[共有アクセス許可**] で、**[サイトの所有者とメンバー、および編集アクセス許可を持つユーザーは、ファイルとフォルダーを共有できますが、サイトの所有者のみがサイトを共有できます]** を選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ecb1b-201">Under **Sharing permissions**, choose **Site owners and members, and people with Edit permissions can share files and folders, but only site owners can share the site**, and then click **Save**.</span></span>


## <a name="see-also"></a><span data-ttu-id="ecb1b-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="ecb1b-202">See Also</span></span>

[<span data-ttu-id="ecb1b-203">秘密度ラベルとそのポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="ecb1b-203">Create and configure sensitivity labels and their policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels)


