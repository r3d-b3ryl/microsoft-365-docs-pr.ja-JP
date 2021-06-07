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
ms.openlocfilehash: 3e98b1a52e698d52eba16d4296c062d7347759d0
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788357"
---
# <a name="configure-teams-with-protection-for-highly-sensitive-data"></a><span data-ttu-id="541c7-103">機密データに対する保護機能を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="541c7-103">Configure teams with protection for highly sensitive data</span></span>

<span data-ttu-id="541c7-104">この記事では、機密レベルの保護機能を使用してチームをセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="541c7-104">In this article, we look at setting up a team for a highly sensitive level of protection.</span></span> <span data-ttu-id="541c7-105">この記事の手順を実行する前に、「[基本保護機能を使用してチームを展開する](configure-teams-baseline-protection.md)」の手順を完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="541c7-105">Be sure you've completed the steps in [Deploy teams with baseline protection](configure-teams-baseline-protection.md) before following the steps in this article.</span></span>

<span data-ttu-id="541c7-106">この保護層では、機密性の高いチームとファイルに対して組織全体で使用できる秘密度ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="541c7-106">For this tier of protection, we create a sensitivity label that can be used across your organization for highly sensitive teams and files.</span></span> <span data-ttu-id="541c7-107">このラベルを使用するファイルを復号化できるのは、指定した組織のメンバーとゲストのみです。</span><span class="sxs-lookup"><span data-stu-id="541c7-107">Only members of your organization and guests that you have specified will be able to decrypt files that use this label.</span></span> <span data-ttu-id="541c7-108">特定のチームのメンバーのみがファイルを復号化できるように権限をさらに分離する必要がある場合は、「[セキュリティ分離を使用してチームを展開する](secure-teams-security-isolation.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="541c7-108">If you need to further isolate permissions so that only members of a specific team can decrypt files, see  [Deploy a team with security isolation](secure-teams-security-isolation.md).</span></span>

<span data-ttu-id="541c7-109">機密層は、基本層の上に次のような追加保護機能を実現します。</span><span class="sxs-lookup"><span data-stu-id="541c7-109">The highly sensitive tier offers the following additional protections over the baseline tier:</span></span>

- <span data-ttu-id="541c7-p103">ゲスト共有を有効または無効にし、管理されていないデバイスの SharePoint コンテンツへのアクセスをブロックするチームの秘密度ラベル。このラベルは、ファイルの分類や暗号化にも使用できます。</span><span class="sxs-lookup"><span data-stu-id="541c7-p103">A sensitivity label for the team that allows you to turn guest sharing on or off and blocks access to SharePoint content for unmanaged devices. This label can also be used to classify and encrypt files.</span></span>
- <span data-ttu-id="541c7-112">より制限の厳しい既定の共有リンクの種類</span><span class="sxs-lookup"><span data-stu-id="541c7-112">A more restrictive default sharing link type</span></span>
- <span data-ttu-id="541c7-113">チーム所有者のみがプライベート チャネルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="541c7-113">Only team owners can create private channels.</span></span>
- <span data-ttu-id="541c7-114">関連付けられた SharePoint サイトへのアクセス要求はオフになっています。</span><span class="sxs-lookup"><span data-stu-id="541c7-114">Access requests for the associated SharePoint site are turned off.</span></span>

## <a name="video-demonstration"></a><span data-ttu-id="541c7-115">ビデオ デモンストレーション</span><span class="sxs-lookup"><span data-stu-id="541c7-115">Video demonstration</span></span>

<span data-ttu-id="541c7-116">この記事で説明されている手続きのチュートリアルに関するビデオを見ます。</span><span class="sxs-lookup"><span data-stu-id="541c7-116">Watch this video for a walkthrough of the procedures described in this article.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4NzI7]

## <a name="guest-sharing"></a><span data-ttu-id="541c7-117">ゲスト共有</span><span class="sxs-lookup"><span data-stu-id="541c7-117">Guest sharing</span></span>

<span data-ttu-id="541c7-118">会社の性質に応じて、機密データを含むチームのゲスト共有を有効または無効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="541c7-118">Depending on the nature of your business, you may or may not want to enable guest sharing for teams that contain highly sensitive data.</span></span> <span data-ttu-id="541c7-119">チーム内の組織外のユーザーと共同作業する場合は、ゲスト共有を有効にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="541c7-119">If you do plan to collaborate with people outside your organization in the team, we recommend enabling guest sharing.</span></span> <span data-ttu-id="541c7-120">Microsoft 365 には、セキュリティとコンプライアンスのためのさまざまな機能が含まれており、機密コンテンツを安全に共有できます。</span><span class="sxs-lookup"><span data-stu-id="541c7-120">Microsoft 365 includes a variety of security and compliance features to help you share sensitive content securely.</span></span> <span data-ttu-id="541c7-121">通常、組織外のユーザーに直接コンテンツを電子メールで送信するよりも、セキュリティが強化されています。</span><span class="sxs-lookup"><span data-stu-id="541c7-121">This is generally a more secure option than emailing content directly to people outside your organization.</span></span>

<span data-ttu-id="541c7-122">ゲストと安全に共有する方法の詳細については、次のリソースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="541c7-122">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="541c7-123">組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する</span><span class="sxs-lookup"><span data-stu-id="541c7-123">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)
- [<span data-ttu-id="541c7-124">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="541c7-124">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

<span data-ttu-id="541c7-125">ゲスト共有を許可または禁止するには、関連付けられている SharePoint サイトのチーム レベルとサイト レベルの共有コントロールに対して、秘密度ラベルを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="541c7-125">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="sensitivity-labels"></a><span data-ttu-id="541c7-126">秘密度ラベル</span><span class="sxs-lookup"><span data-stu-id="541c7-126">Sensitivity labels</span></span>

<span data-ttu-id="541c7-127">機密性の高いレベルで保護するために、機密ラベルを使用してチームを分類します。</span><span class="sxs-lookup"><span data-stu-id="541c7-127">For the highly sensitive level of protection, we'll be using a sensitivity label to classify the team.</span></span> <span data-ttu-id="541c7-128">このラベルは、このチームまたは他のチームの個別のファイル、または SharePoint や OneDrive などのその他の場所にあるファイルを暗号化して分類するために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="541c7-128">This label can also be used to classify and encrypt individual files in this or other teams or in other file locations such as SharePoint or OneDrive.</span></span> 

<span data-ttu-id="541c7-129">最初の手順では、Teams の秘密度ラベルを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="541c7-129">As a first step, you must enable sensitivity labels for Teams.</span></span> <span data-ttu-id="541c7-130">詳細は、「[秘密度ラベルを使用して、Microsoft Teams、Office 365 グループ、SharePoint サイトのコンテンツを保護する](../compliance/sensitivity-labels-teams-groups-sites.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="541c7-130">See [Use sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md) for details.</span></span>

<span data-ttu-id="541c7-131">組織に既に秘密度ラベルを展開している場合は、ラベル戦略全体にこのラベルがどのように適合しているかを検討してください。</span><span class="sxs-lookup"><span data-stu-id="541c7-131">If you already have sensitivity labels deployed in your organization, consider how this label fits with your overall label strategy.</span></span> <span data-ttu-id="541c7-132">組織のニーズを満たす必要がある場合、名前または設定を変更できます。</span><span class="sxs-lookup"><span data-stu-id="541c7-132">You can change the name or settings if needed to meet the needs of your organization.</span></span>

<span data-ttu-id="541c7-133">Teams の秘密度ラベルを有効にしたら、次の手順ではラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="541c7-133">Once you have enabled sensitivity labels for Teams, the next step is to create the label.</span></span>

<span data-ttu-id="541c7-134">秘密度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="541c7-134">To create a sensitivity label</span></span>
1. <span data-ttu-id="541c7-135">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="541c7-135">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="541c7-136">**[ソリューション]** で、**[情報保護]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-136">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="541c7-137">**[ラベルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-137">Click **Create a label**.</span></span>
4. <span data-ttu-id="541c7-138">ラベルに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="541c7-138">Give the label a name.</span></span> <span data-ttu-id="541c7-139">[**高機密性**] をお勧めしますが、既に使用されている別の名前を選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="541c7-139">We suggest **Highly sensitive**, but you can choose a different name if that one is already in use.</span></span>
5. <span data-ttu-id="541c7-140">表示名と説明を追加し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-140">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="541c7-141">**Define the scope for this label** (このラベルの範囲の定義) ページで、**[Files & emails]** (ファイルとメール) と **[Groups & sites]** (グループとサイト) を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-141">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="541c7-142">**[ファイルとメールの保護設定の選択]** ページで、**[ファイルとメールの暗号化]** を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-142">On the **Choose protection settings for files and emails** page, select **Encrypt files and emails**, and then click **Next**.</span></span>
8. <span data-ttu-id="541c7-143">**[暗号化]** ページで、**[暗号化設定を構成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="541c7-143">On the **Encryption** page, choose **Configure encryption settings**.</span></span>
9. <span data-ttu-id="541c7-144">[**特定のユーザーとグループにアクセス許可を付与する**] で、[**アクセス許可の割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-144">Under **Assign permissions to specific users and groups**, click **Assign permissions**.</span></span>
10. <span data-ttu-id="541c7-145">**[組織内のすべてのユーザーとグループを追加する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-145">Click **Add all users and groups in your organization**.</span></span>
11. <span data-ttu-id="541c7-146">ファイルを復号化する権限を持つゲストがいる場合は、**[ユーザーまたはグループを追加する]** をクリックして追加します。</span><span class="sxs-lookup"><span data-stu-id="541c7-146">If there are guests who should have permissions to decrypt files, click **Add users or groups** and add them.</span></span>
12.  <span data-ttu-id="541c7-147">**[保存]** をクリックし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-147">Click **Save**, and then click **Next**.</span></span>
13. <span data-ttu-id="541c7-148">*[ファイルやメールの自動ラベル付け]* ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-148">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
14. <span data-ttu-id="541c7-149">**[Define protection settings for groups and sites]** (グループやサイトの保護の設定の定義) ページで、**[プライバシーと外部ユーザー アクセス設定]** と **[デバイス アクセスと外部共有設定]** を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-149">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
15. <span data-ttu-id="541c7-150">**[Define privacy and external user access settings]** (プライバシーと外部ユーザー アクセス設定の定義) ページの **[プライバシー]** で、**[プライベート]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="541c7-150">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
16. <span data-ttu-id="541c7-151">ゲスト アクセスを許可する場合は、**[外部ユーザーのアクセス]** で、**[Let Microsoft 365 Group owners add people outside your organization to the group as guests]** (Microsoft 365 グループ所有者が組織外のユーザーをグループに追加できるようにする) を選択します。</span><span class="sxs-lookup"><span data-stu-id="541c7-151">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
17. <span data-ttu-id="541c7-152">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-152">Click **Next**.</span></span>
18. <span data-ttu-id="541c7-153">**[Define external sharing and device access settings]** (外部共有とデバイス アクセス設定の定義) ページで、**[Control external sharing from labeled SharePoint sites]** (ラベル付き SharePoint サイトからの外部共有の制御) を選択します。</span><span class="sxs-lookup"><span data-stu-id="541c7-153">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
19. <span data-ttu-id="541c7-154">**[Content can be shared with]** (コンテンツの共有先) で、ゲスト アクセスを許可する場合には **[新規および既存のゲスト]** を選択し、許可しない場合には **[組織内のユーザーのみ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="541c7-154">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
20. <span data-ttu-id="541c7-155">**[非管理対象デバイスからのアクセス]** で、**[アクセスをブロックする]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="541c7-155">Under **Access from unmanaged devices**, choose **Block access**.</span></span> <span data-ttu-id="541c7-156">(ゲストを許可し、管理されているデバイスを持たない場合は、**[制限された、Web のみのアクセスを許可する]** を選択できます。)</span><span class="sxs-lookup"><span data-stu-id="541c7-156">(If you're allowing guests and they don't have managed devices, you may want to choose **Allow limited, web-only access**.)</span></span>
21. <span data-ttu-id="541c7-157">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-157">Click **Next**.</span></span>
22. <span data-ttu-id="541c7-158">**[Auto-labeling for database columns]** (データベースの列の自動ラベル付け) ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-158">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
23. <span data-ttu-id="541c7-159">**[ラベルの作成]** をクリックし、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-159">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="541c7-160">ラベルを作成したら、それを使用するユーザーに発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="541c7-160">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="541c7-161">機密保護のために、すべてのユーザーがラベルを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="541c7-161">For sensitive protection, we'll make the label available to all users.</span></span> <span data-ttu-id="541c7-162">**[情報保護]** ページの [**ラベルポリシー**] タブで、ラベルを Microsoft 365 コンプライアンス センターに発行します。</span><span class="sxs-lookup"><span data-stu-id="541c7-162">You publish the label in the Microsoft 365 compliance center, on the **Label policies** tab of the **Information protection** page.</span></span> <span data-ttu-id="541c7-163">すべてのユーザーに適用する既存のポリシーがある場合は、そのポリシーにこのラベルを追加します。</span><span class="sxs-lookup"><span data-stu-id="541c7-163">If you have an existing policy that applies to all users, add this label to that policy.</span></span> <span data-ttu-id="541c7-164">新しいポリシーを作成する必要がある場合は、「[ラベル ポリシーを作成して秘密度ラベルを発行する](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="541c7-164">If you need to create a new policy, see [Publish sensitivity labels by creating a label policy](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy).</span></span>

## <a name="create-a-team"></a><span data-ttu-id="541c7-165">チームを作成する</span><span class="sxs-lookup"><span data-stu-id="541c7-165">Create a team</span></span>

<span data-ttu-id="541c7-166">機密のシナリオの詳細な構成は、チームに関連付けられている SharePoint サイトで行います。次の手順では、チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="541c7-166">Further configuration of the highly sensitive scenario is done in the SharePoint site associated with the team, so the next step is to create a team.</span></span>

<span data-ttu-id="541c7-167">機密情報のチームを作成するには</span><span class="sxs-lookup"><span data-stu-id="541c7-167">To create a team for highly sensitive information</span></span>
1. <span data-ttu-id="541c7-168">Teams で、アプリの左側にある **[Teams]** をクリックして、チーム リストの下部にある **[チームに参加またはチームの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-168">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="541c7-169">**[チームの作成]** (最初のカード、左上隅) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-169">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="541c7-170">**[初めからチームを作成する]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="541c7-170">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="541c7-171">**[秘密度]** リストで、作成した **秘密度** ラベルを選びます。</span><span class="sxs-lookup"><span data-stu-id="541c7-171">In the **Sensitivity** list, choose the **Highly sensitive** label that you just created.</span></span>
5. <span data-ttu-id="541c7-172">**[プライバシー]** で、**[プライベート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-172">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="541c7-173">チームの名前を入力し、**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-173">Type a name for the team, and then click **Create**.</span></span>
7. <span data-ttu-id="541c7-174">チームにユーザーを追加し、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-174">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="541c7-175">プライベート チャネルの設定</span><span class="sxs-lookup"><span data-stu-id="541c7-175">Private channel settings</span></span>

<span data-ttu-id="541c7-176">この層では、プライベート チャネルの作成権限をチームの所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="541c7-176">In this tier, we restrict creating private channels to team owners.</span></span>

<span data-ttu-id="541c7-177">プライベート チャネルの作成を制限するには</span><span class="sxs-lookup"><span data-stu-id="541c7-177">To restrict private channel creation</span></span>
1. <span data-ttu-id="541c7-178">チームで、**[その他のオプション]** をクリックしてから、**[チームの管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-178">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="541c7-179">**[設定]** タブで、**[メンバーのアクセス許可]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="541c7-179">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="541c7-180">**[プライベート チャネルを作成する]** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="541c7-180">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="541c7-181">[チーム ポリシー](/MicrosoftTeams/teams-policies)を使用して、プライベート チャネルを作成できるユーザーを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="541c7-181">You can also use [teams policies](/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="541c7-182">SharePoint の設定</span><span class="sxs-lookup"><span data-stu-id="541c7-182">SharePoint settings</span></span>

<span data-ttu-id="541c7-183">秘密度ラベルを使用して新しいチームを作成するたびに、SharePoint で次の 2 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="541c7-183">Each time you create a new team with the highly sensitive label, there are two steps to do in SharePoint:</span></span>

- <span data-ttu-id="541c7-184">SharePoint 管理センターでサイトのゲスト共有設定を更新して、*既存のアクセス権を持つユーザー* に対して既定の共有リンクを更新します。</span><span class="sxs-lookup"><span data-stu-id="541c7-184">Update the guest sharing settings for the site in the SharePoint admin center to update the default sharing link to *People with existing access*.</span></span>
- <span data-ttu-id="541c7-185">サイト自体の共有設定を更新し、メンバーがファイル、フォルダー、サイトを共有できないようにし、アクセス要求を無効にします。</span><span class="sxs-lookup"><span data-stu-id="541c7-185">Update the site sharing settings in the site itself to prevent members from sharing files, folders, or the site, and turn off access requests.</span></span>

### <a name="site-default-sharing-link-settings"></a><span data-ttu-id="541c7-186">サイトの既定の共有リンク設定</span><span class="sxs-lookup"><span data-stu-id="541c7-186">Site default sharing link settings</span></span>

<span data-ttu-id="541c7-187">サイトの既定の共有リンクの種類を更新するには</span><span class="sxs-lookup"><span data-stu-id="541c7-187">To update the site default sharing link type</span></span>

1. <span data-ttu-id="541c7-188">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="541c7-188">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="541c7-189">**[サイト]** で、**[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-189">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="541c7-190">チームに関連付けられているサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-190">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="541c7-191">**[ポリシー]** タブで、**[外部共有]** の下側にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-191">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="541c7-192">[既定の共有リンクの種類] で、**[組織レベルの設定と同じ]** チェック ボックスをオフにして、**[既存のアクセス権を持つユーザー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="541c7-192">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
6. <span data-ttu-id="541c7-193">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-193">Click **Save**.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="541c7-194">プライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="541c7-194">Private channels</span></span>

<span data-ttu-id="541c7-195">チームにプライベート チャネルを追加する場合、各プライベート チャネルは、既定の共有設定を使用して新しい SharePoint サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="541c7-195">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="541c7-196">これらのサイトは SharePoint 管理センターでは表示されないので、Set-sposite PowerShell コマンドレットを使用して、ゲスト共有設定を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="541c7-196">These sites are not visible in the SharePoint admin center, so you must use the Set-SPOSite PowerShell cmdlet to update the guest sharing settings.</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="541c7-197">サイト共有設定</span><span class="sxs-lookup"><span data-stu-id="541c7-197">Site sharing settings</span></span>

<span data-ttu-id="541c7-198">SharePoint サイトがチーム メンバーではないユーザーと共有されないようにするには、SharePoint サイトの共有を所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="541c7-198">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span> <span data-ttu-id="541c7-199">また、ファイルとフォルダーの共有をチームの所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="541c7-199">We also limit sharing of files and folders to team owners.</span></span> <span data-ttu-id="541c7-200">これにより、ファイルがチーム外のユーザーと共有されるたびに所有者が認識できます。</span><span class="sxs-lookup"><span data-stu-id="541c7-200">This helps ensure that owners are aware whenever a file is shared with someone outside the team.</span></span>

<span data-ttu-id="541c7-201">所有者のみのサイト共有を構成する</span><span class="sxs-lookup"><span data-stu-id="541c7-201">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="541c7-202">Teams で、更新するチームの **[全般]** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="541c7-202">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="541c7-203">チームのツール バーで、**[ファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-203">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="541c7-204">省略記号をクリックし、**[SharePoint で開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-204">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="541c7-205">基となる SharePoint サイトのツール バーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-205">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="541c7-206">**[サイトの権限]** ウィンドウで、**[サイトの共有]** の **[メンバーが共有する方法を変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-206">In the **Site permissions** pane, under **Site sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="541c7-207">[**共有アクセス許可**] で、[**ファイル、フォルダー、およびサイトを共有できるのはサイトの所有者だけです**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="541c7-207">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
7. <span data-ttu-id="541c7-208">[**アクセス要求の許可**] を [**オフ**] に設定し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="541c7-208">Set **Allow access requests** to **Off**, and then click **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="541c7-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="541c7-209">See Also</span></span>

[<span data-ttu-id="541c7-210">秘密度ラベルとそのポリシーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="541c7-210">Create and configure sensitivity labels and their policies</span></span>](../compliance/create-sensitivity-labels.md)
