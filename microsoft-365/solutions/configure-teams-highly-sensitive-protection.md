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
description: 機密データに対する保護機能を使用してチームを展開する方法について説明します。
ms.openlocfilehash: 6354de5a37547d14b16a4d6a0857ddc390d531e6
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750811"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a><span data-ttu-id="9131b-103">機密データに対する保護機能を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="9131b-103">Configure teams with protection for highly sensitive data</span></span>

<span data-ttu-id="9131b-104">この記事では、機密レベルの保護機能を使用してチームをセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9131b-104">In this article, we look at setting up a team for a highly sensitive level of protection.</span></span> <span data-ttu-id="9131b-105">この記事の手順を実行する前に、「[基本保護機能を使用してチームを展開する](configure-teams-baseline-protection.md)」の手順を完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9131b-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span>

<span data-ttu-id="9131b-106">この保護層では、機密性の高いチームとファイルに対して組織全体で使用できる秘密度ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9131b-106">For this tier of protection, we create a sensitivity label that can be used across your organization for highly sensitive teams and files.</span></span> <span data-ttu-id="9131b-107">このラベルを使用するファイルを復号化できるのは、指定した組織のメンバーとゲストのみです。</span><span class="sxs-lookup"><span data-stu-id="9131b-107">Only members of your organization and guests that you have specified will be able to decrypt files that use this label.</span></span> <span data-ttu-id="9131b-108">特定のチームのメンバーのみがファイルを復号化できるように権限をさらに分離する必要がある場合は、「[セキュリティ分離を使用してチームを展開する](secure-teams-security-isolation.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9131b-108">If you need to further isolate permissions so that only members of a specific team can decrypt files, see  [Deploy a team with security isolation](secure-teams-security-isolation.md).</span></span>

<span data-ttu-id="9131b-109">機密層は、基本層の上に次のような追加保護機能を実現します。</span><span class="sxs-lookup"><span data-stu-id="9131b-109">The highly sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="9131b-110">ゲスト共有を有効または無効にし、管理されていないデバイスの SharePoint コンテンツへのアクセスを Web のみに制限するチームの秘密度ラベル。</span><span class="sxs-lookup"><span data-stu-id="9131b-110">A sensitivity label for the team that allows you to turn guest sharing on or off and limits access to SharePoint content to web-only for unmanaged devices.</span></span> <span data-ttu-id="9131b-111">このラベルは、ファイルを暗号化して分類するためにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="9131b-111">This label can also be used to classify and encrypt files.</span></span>
- <span data-ttu-id="9131b-112">より制限の厳しい既定の共有リンクの種類</span><span class="sxs-lookup"><span data-stu-id="9131b-112">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="9131b-113">チーム所有者のみがプライベート チャネルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="9131b-113">Only team owners can create private channels.</span></span>
- <span data-ttu-id="9131b-114">関連付けられた SharePoint サイトへのアクセス要求はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="9131b-114">Access requests for the associated SharePoint site are turned off.</span></span>

## <a name="guest-sharing"></a><span data-ttu-id="9131b-115">ゲスト共有</span><span class="sxs-lookup"><span data-stu-id="9131b-115">Guest sharing</span></span>

<span data-ttu-id="9131b-116">会社の性質に応じて、機密データを含むチームのゲスト共有を有効または無効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9131b-116">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain highly sensitive data.</span></span> <span data-ttu-id="9131b-117">チーム内の組織外のユーザーと共同作業する場合は、ゲスト共有を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9131b-117">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="9131b-118">Microsoft 365 には、セキュリティとコンプライアンスのためのさまざまな機能が含まれており、機密コンテンツを安全に共有できます。</span><span class="sxs-lookup"><span data-stu-id="9131b-118">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="9131b-119">通常、組織外のユーザーに直接コンテンツを電子メールで送信するよりも、セキュリティが強化されています。</span><span class="sxs-lookup"><span data-stu-id="9131b-119">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="9131b-120">ゲストと安全に共有する方法の詳細については、次のリソースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9131b-120">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="9131b-121">組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する</span><span class="sxs-lookup"><span data-stu-id="9131b-121">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [<span data-ttu-id="9131b-122">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="9131b-122">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

<span data-ttu-id="9131b-123">ゲスト共有を許可または禁止するには、関連付けられている SharePoint サイトのチーム レベルとサイト レベルの共有コントロールに対して、秘密度ラベルを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="9131b-123">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="9131b-124">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="9131b-124">Sensitivity labels</span></span>

<span data-ttu-id="9131b-125">機密性の高いレベルで保護するために、機密ラベルを使用してチームを分類します。</span><span class="sxs-lookup"><span data-stu-id="9131b-125">For the highly sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="9131b-126">このラベルは、このチームまたは他のチームの個別のファイル、または SharePoint や OneDrive などのその他の場所にあるファイルを暗号化して分類するために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="9131b-126">This label can also be used to classify and encrypt individual files in this or other teams or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="9131b-127">最初の手順では、Teams の秘密度ラベルを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9131b-127">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="9131b-128">詳細は、「[秘密度ラベルを使用して、Microsoft Teams、Office 365 グループ、SharePoint サイトのコンテンツを保護する](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9131b-128">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) for details.</span></span>

<span data-ttu-id="9131b-129">組織に既に秘密度ラベルを展開している場合は、ラベル戦略全体にこのラベルがどのように適合しているかを検討してください。</span><span class="sxs-lookup"><span data-stu-id="9131b-129">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="9131b-130">組織のニーズを満たす必要がある場合、名前または設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="9131b-130">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="9131b-131">Teams の秘密度ラベルを有効にしたら、次の手順ではラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="9131b-131">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="9131b-132">秘密度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="9131b-132">To create a sensitivity label</span></span>
1. <span data-ttu-id="9131b-133">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="9131b-133">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="9131b-134">**[ソリューション]** で、**[情報保護]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-134">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="9131b-135">**[ラベルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-135">Click **Create a label**.</span></span>
4. <span data-ttu-id="9131b-136">ラベルに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="9131b-136">Give the label a name.</span></span> <span data-ttu-id="9131b-137">**Sensitive** をお勧めしますが、既に使用されている別の名前を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="9131b-137">We suggest **Sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="9131b-138">表示名と説明を追加し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-138">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="9131b-139">**Define the scope for this label** (このラベルの範囲の定義) ページで、**[Files & emails]** (ファイルとメール) と **[Groups & sites]** (グループとサイト) を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-139">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="9131b-140">**[ファイルとメールの保護設定の選択]** ページで、**[ファイルとメールの暗号化]** を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-140">On the **Choose protection settings for files and emails** page, select **Encrypt files and emails**, and then click **Next**.</span></span>
8. <span data-ttu-id="9131b-141">**[暗号化]** ページで、**[暗号化設定を構成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9131b-141">On the **Encryption** page, choose **Configure encryption settings**.</span></span>
9. <span data-ttu-id="9131b-142">[**特定のユーザーとグループにアクセス許可を付与する**] で、[**アクセス許可の割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-142">Under **Assign permissions to specific users and groups**, click **Assign permissions**.</span></span>
10. <span data-ttu-id="9131b-143">**[組織内のすべてのユーザーとグループを追加する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-143">Click **Add all users and groups in your organization**.</span></span>
11. <span data-ttu-id="9131b-144">ファイルを復号化する権限を持つゲストがいる場合は、**[ユーザーまたはグループを追加する]** をクリックして追加します。</span><span class="sxs-lookup"><span data-stu-id="9131b-144">If there are guests who should have permissions to decrypt files, click **Add users or groups** and add them.</span></span>
12.  <span data-ttu-id="9131b-145">**[保存]** をクリックし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-145">Click **Save**, and then click **Next**.</span></span>
13. <span data-ttu-id="9131b-146">*[ファイルやメールの自動ラベル付け]* ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-146">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
14. <span data-ttu-id="9131b-147">**[Define protection settings for groups and sites]** (グループやサイトの保護の設定の定義) ページで、**[プライバシーと外部ユーザー アクセス設定]** と **[デバイス アクセスと外部共有設定]** を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-147">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
15. <span data-ttu-id="9131b-148">**[Define privacy and external user access settings]** (プライバシーと外部ユーザー アクセス設定の定義) ページの **[プライバシー]** で、**[プライベート]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="9131b-148">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
16. <span data-ttu-id="9131b-149">ゲスト アクセスを許可する場合は、**[外部ユーザーのアクセス]** で、**[Let Microsoft 365 Group owners add people outside your organization to the group as guests]** (Microsoft 365 グループ所有者が組織外のユーザーをグループに追加できるようにする) を選択します。</span><span class="sxs-lookup"><span data-stu-id="9131b-149">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
17. <span data-ttu-id="9131b-150">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-150">Click **Next**.</span></span>
18. <span data-ttu-id="9131b-151">**[Define external sharing and device access settings]** (外部共有とデバイス アクセス設定の定義) ページで、**[Control external sharing from labeled SharePoint sites]** (ラベル付き SharePoint サイトからの外部共有の制御) を選択します。</span><span class="sxs-lookup"><span data-stu-id="9131b-151">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
19. <span data-ttu-id="9131b-152">**[Content can be shared with]** (コンテンツの共有先) で、ゲスト アクセスを許可する場合には **[新規および既存のゲスト]** を選択し、許可しない場合には **[組織内のユーザーのみ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="9131b-152">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
20. <span data-ttu-id="9131b-153">**[非管理対象デバイスからのアクセス]** で、**[アクセスをブロックする]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9131b-153">Under **Access from unmanaged devices**, choose **Block access**.</span></span>
21. <span data-ttu-id="9131b-154">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-154">Click **Next**.</span></span>
22. <span data-ttu-id="9131b-155">**[Auto-labeling for database columns]** (データベースの列の自動ラベル付け) ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-155">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
23. <span data-ttu-id="9131b-156">**[ラベルの作成]** をクリックし、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-156">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="9131b-157">ラベルを作成したら、それを使用するユーザーに発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9131b-157">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="9131b-158">機密保護のために、すべてのユーザーがラベルを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="9131b-158">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="9131b-159">**[情報保護]** ページの [**ラベルポリシー**] タブで、ラベルを Microsoft 365 コンプライアンス センターに発行します。</span><span class="sxs-lookup"><span data-stu-id="9131b-159">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="9131b-160">すべてのユーザーに適用する既存のポリシーがある場合は、そのポリシーにこのラベルを追加します。</span><span class="sxs-lookup"><span data-stu-id="9131b-160">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="9131b-161">新しいポリシーを作成する必要がある場合は、「[ラベル ポリシーを作成して秘密度ラベルを発行する](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9131b-161">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="9131b-162">チームを作成する</span><span class="sxs-lookup"><span data-stu-id="9131b-162">Create a team</span></span>

<span data-ttu-id="9131b-163">機密のシナリオの詳細な構成は、チームに関連付けられている SharePoint サイトで行います。次の手順では、チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="9131b-163">Further configuration of the highly sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="9131b-164">機密情報のチームを作成するには</span><span class="sxs-lookup"><span data-stu-id="9131b-164">To create a team for highly sensitive information</span></span>
1. <span data-ttu-id="9131b-165">Teams で、アプリの左側にある **[Teams]** をクリックして、チーム リストの下部にある **[チームに参加またはチームの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-165">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="9131b-166">**[チームの作成]** (最初のカード、左上隅) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-166">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="9131b-167">**[初めからチームを作成する]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9131b-167">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="9131b-168">**[秘密度]** リストで、作成した **秘密度** ラベルを選びます。</span><span class="sxs-lookup"><span data-stu-id="9131b-168">In the **Sensitivity** list, choose the **Highly sensitive** label that you just created.</span></span>
5. <span data-ttu-id="9131b-169">**[プライバシー]** で、**[プライベート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-169">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="9131b-170">チームの名前を入力し、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-170">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="9131b-171">チームにユーザーを追加し、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-171">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="9131b-172">プライベート チャネルの設定</span><span class="sxs-lookup"><span data-stu-id="9131b-172">Private channel settings</span></span>

<span data-ttu-id="9131b-173">この層では、プライベート チャネルの作成権限をチームの所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="9131b-173">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="9131b-174">プライベート チャネルの作成を制限するには</span><span class="sxs-lookup"><span data-stu-id="9131b-174">To restrict private channel creation</span></span>
1. <span data-ttu-id="9131b-175">チームで、**[その他のオプション]** をクリックしてから、**[チームの管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-175">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="9131b-176">**[設定]** タブで、**[メンバーのアクセス許可]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="9131b-176">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="9131b-177">**[プライベート チャネルを作成する]** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="9131b-177">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="9131b-178">[チーム ポリシー](https://docs.microsoft.com/MicrosoftTeams/teams-policies)を使用して、プライベート チャネルを作成できるユーザーを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="9131b-178">You can also use [teams policies](https://docs.microsoft.com/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="9131b-179">SharePoint の設定</span><span class="sxs-lookup"><span data-stu-id="9131b-179">SharePoint settings</span></span>

<span data-ttu-id="9131b-180">秘密度ラベルを使用して新しいチームを作成するたびに、SharePoint で次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9131b-180">Each time you create a new team with the highly sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="9131b-181">ラベルを作成したときに選択したものと一致するように、SharePoint 管理センターでサイトのゲスト共有設定を更新し、*既存のアクセス権を持つユーザー* に対して、既定の共有リンクを更新します。</span><span class="sxs-lookup"><span data-stu-id="9131b-181">Update the guest sharing settings for the site in the SharePoint admin center to match what you chose when you created the label, and update the default sharing link to *People with existing access*.</span></span>
- <span data-ttu-id="9131b-182">サイト自体の共有設定を更新し、メンバーがファイル、フォルダー、サイトを共有できないようにし、アクセス要求を無効にします。</span><span class="sxs-lookup"><span data-stu-id="9131b-182">Update the site sharing settings in the site itself to prevent members from sharing files, folders, or the site, and turn off access requests.</span></span>

### <a name="site-guest-sharing-settings"></a><span data-ttu-id="9131b-183">サイトのゲスト共有設定</span><span class="sxs-lookup"><span data-stu-id="9131b-183">Site guest sharing settings</span></span>

<span data-ttu-id="9131b-184">ラベルを作成したときに選択したゲスト共有設定 (チーム メンバーシップのみに影響します) は、以下のように関連付けられている SharePoint サイトのゲスト共有設定と一致します。</span><span class="sxs-lookup"><span data-stu-id="9131b-184">The guest sharing setting that you chose when you created the label (which only affects team membership) should match the guest sharing settings for the associated SharePoint site as follows:</span></span>

|<span data-ttu-id="9131b-185">ラベルの設定</span><span class="sxs-lookup"><span data-stu-id="9131b-185">Label setting</span></span>|<span data-ttu-id="9131b-186">SharePoint サイトの設定</span><span class="sxs-lookup"><span data-stu-id="9131b-186">SharePoint site setting</span></span>|
|:------------|:----------------------|
|<span data-ttu-id="9131b-187">**Ofﬁce 365 グループ所有者が組織外のユーザーをグループに追加できるようにする** が選択されている</span><span class="sxs-lookup"><span data-stu-id="9131b-187">**Let Office 365 group owners add people outside the organization to the group** selected</span></span>|<span data-ttu-id="9131b-188">**新規および既存のゲスト** (新規チームの既定値)</span><span class="sxs-lookup"><span data-stu-id="9131b-188">**New and existing guests** (default for new teams)</span></span>|
|<span data-ttu-id="9131b-189">**Ofﬁce 365 グループ所有者が組織外のユーザーをグループに追加できるようにする** が選択されていない</span><span class="sxs-lookup"><span data-stu-id="9131b-189">**Let Office 365 group owners add people outside the organization to the group** not selected</span></span>|<span data-ttu-id="9131b-190">**組織内のユーザーのみ**</span><span class="sxs-lookup"><span data-stu-id="9131b-190">**Only people in your organization**</span></span>|

<span data-ttu-id="9131b-191">サイトの設定を更新するには</span><span class="sxs-lookup"><span data-stu-id="9131b-191">To update site settings</span></span>
1. <span data-ttu-id="9131b-192">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="9131b-192">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="9131b-193">**[サイト]** で、**[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-193">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="9131b-194">チームに関連付けられているサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-194">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="9131b-195">**[ポリシー]** タブで、**[外部共有]** の下側にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-195">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="9131b-196">秘密度ラベルを作成したときにゲスト共有が許可されていた場合は、**[新規および既存のゲスト]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9131b-196">If you allowed guest sharing when you created the Highly sensitive label, ensure that **New and existing guests** is selected.</span></span> <span data-ttu-id="9131b-197">秘密度ラベルを作成したときにゲスト共有が許可されていなかった場合は、**[組織内のユーザーのみ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9131b-197">If you didn't allow sharing when you created the label, choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="9131b-198">[既定の共有リンクの種類] で、**[組織レベルの設定と同じ]** チェック ボックスをオフにして、**[既存のアクセス権を持つユーザー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="9131b-198">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="9131b-199">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-199">Click **Save**.</span></span>

<span data-ttu-id="9131b-200">これをチーム作成プロセスの一部としてスクリプト化する場合は、次のパラメーターを指定して [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) を使用します。</span><span class="sxs-lookup"><span data-stu-id="9131b-200">If you want to script this as part of your team creation process, you can use [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) with the following parameters:</span></span>

- <span data-ttu-id="9131b-201">`-SharingCapability Disabled` ゲスト共有を無効にするには (既定では有効です)</span><span class="sxs-lookup"><span data-stu-id="9131b-201">`-SharingCapability Disabled` to turn off guest sharing (it's on by default)</span></span>
- <span data-ttu-id="9131b-202">`-DefaultSharingLinkType Internal` 既定の共有リンクを *特定のユーザー* に変更するには</span><span class="sxs-lookup"><span data-stu-id="9131b-202">`-DefaultSharingLinkType Internal` to change the default sharing link to *Specific people*</span></span>

#### <a name="private-channels"></a><span data-ttu-id="9131b-203">プライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="9131b-203">Private channels</span></span>

<span data-ttu-id="9131b-204">チームにプライベート チャネルを追加する場合、各プライベート チャネルは、既定の共有設定を使用して新しい SharePoint サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="9131b-204">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="9131b-205">これらのサイトは SharePoint 管理センターでは表示されないので、Set-sposite PowerShell コマンドレットを使用して、ゲスト共有設定を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9131b-205">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="9131b-206">サイト共有設定</span><span class="sxs-lookup"><span data-stu-id="9131b-206">Site sharing settings</span></span>

<span data-ttu-id="9131b-207">SharePoint サイトがチーム メンバーではないユーザーと共有されないようにするには、SharePoint サイトの共有を所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="9131b-207">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span> <span data-ttu-id="9131b-208">また、ファイルとフォルダーの共有をチームの所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="9131b-208">We also limit sharing of files and folders to team owners.</span></span> <span data-ttu-id="9131b-209">これにより、ファイルがチーム外のユーザーと共有されるたびに所有者が認識できます。</span><span class="sxs-lookup"><span data-stu-id="9131b-209">This helps ensure that owners are aware whenever a file is shared with someone outside the team.</span></span>

<span data-ttu-id="9131b-210">所有者のみのサイト共有を構成する</span><span class="sxs-lookup"><span data-stu-id="9131b-210">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="9131b-211">Teams で、更新するチームの **[全般]** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="9131b-211">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="9131b-212">チームのツール バーで、**[ファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-212">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="9131b-213">省略記号をクリックし、**[SharePoint で開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-213">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="9131b-214">基となる SharePoint サイトのツール バーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-214">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="9131b-215">[サイトの権限] ウィンドウで、**[共有設定]** の **[共有設定の変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-215">In the Site permissions pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
6. <span data-ttu-id="9131b-216">[**共有アクセス許可**] で、[**ファイル、フォルダー、およびサイトを共有できるのはサイトの所有者だけです**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9131b-216">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
7. <span data-ttu-id="9131b-217">[**アクセス要求の許可**] を [**オフ**] に設定し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9131b-217">Set **Allow access requests** to **Off**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="9131b-218">関連項目</span><span class="sxs-lookup"><span data-stu-id="9131b-218">See Also</span></span>

[<span data-ttu-id="9131b-219">秘密度ラベルとそのポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="9131b-219">Create and configure sensitivity labels and their policies</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels)

