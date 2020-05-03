---
title: セキュリティの分離を使用してチームを構成する
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- M365solutions
description: セキュリティ固有の秘密度ラベルを使用してチームを作成する方法について説明します。
ms.openlocfilehash: cfb05bdfe791289cef7af480397802a3e11271a1
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "44003058"
---
# <a name="configure-a-team-with-security-isolation"></a><span data-ttu-id="63003-103">セキュリティの分離を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="63003-103">Configure a team with security isolation</span></span>

<span data-ttu-id="63003-104">この記事では、Microsoft Teams でプライベート チームを構成し、固有の秘密度ラベルを使用してファイルを暗号化して、チーム メンバーのみがファイルを復号化できるようにするための推奨事項と手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="63003-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams and use a unique sensitivity label to encrypt files so that only team members can decrypt them.</span></span>

<span data-ttu-id="63003-105">この記事では、プライベート アクセスの他にも、チーム チャネルの [**ファイル**] セクションからアクセスできる関連付けられた SharePoint サイトを構成して厳しく規制されたデータの保存で必要な追加のセキュリティを提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="63003-105">Beyond the private access, this article describes how to configure the associated SharePoint site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span>

<span data-ttu-id="63003-106">規制の厳しいデータ用にチームを構成する場合の要素は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="63003-106">The elements of configuration for a team for highly regulated data are:</span></span>

- <span data-ttu-id="63003-107">プライベート チーム</span><span class="sxs-lookup"><span data-stu-id="63003-107">A private team</span></span>
- <span data-ttu-id="63003-108">チームに関連付けられた SharePoint サイトでの以下の追加のセキュリティ:</span><span class="sxs-lookup"><span data-stu-id="63003-108">Additional security on the associated SharePoint site for the team that:</span></span>
  - <span data-ttu-id="63003-109">サイトのメンバーがサイトを他のユーザーと共有することの防止。</span><span class="sxs-lookup"><span data-stu-id="63003-109">Prevents members of the site from sharing the site with others.</span></span>
  - <span data-ttu-id="63003-110">サイトのメンバーではないユーザーがサイトへのアクセス権を要求することの防止。</span><span class="sxs-lookup"><span data-stu-id="63003-110">Prevents non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="63003-111">このチーム専用の秘密度ラベル:</span><span class="sxs-lookup"><span data-stu-id="63003-111">A sensitivity label specifically for this team that:</span></span>
    - <span data-ttu-id="63003-112">非管理対象デバイスから SharePoint コンテンツにアクセスできないようにする</span><span class="sxs-lookup"><span data-stu-id="63003-112">Prevents access to SharePoint content from unmanaged devices</span></span>
    - <span data-ttu-id="63003-113">要求に応じて、チームのゲストアクセスを許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="63003-113">Allows or denies guest access to the team, depending on your requirements</span></span>
    - <span data-ttu-id="63003-114">ラベルを適用するドキュメントを暗号化する</span><span class="sxs-lookup"><span data-stu-id="63003-114">Encrypts documents to which the label is applied</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63003-115">この記事の手順に進む前に、「[Microsoft Teams、Office 365 グループ、SharePoint サイトのコンテンツを保護するために秘密度ラベル](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)を有効にしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63003-115">Be sure you have enabled [sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) before you proceed with the steps in this article.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="63003-116">初期保護</span><span class="sxs-lookup"><span data-stu-id="63003-116">Initial protections</span></span>

<span data-ttu-id="63003-117">チームおよび基になる SharePoint サイトへのアクセスを保護するためには、次のベスト プラクティスを確認します。</span><span class="sxs-lookup"><span data-stu-id="63003-117">To help protect access to the team and its underlying SharePoint site, review the following best practices:</span></span>
- [<span data-ttu-id="63003-118">ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="63003-118">Identity and device access policies</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-policies)
- <span data-ttu-id="63003-119">[SharePoint Online アクセス ポリシー](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies)。</span><span class="sxs-lookup"><span data-stu-id="63003-119">[SharePoint Online access policies](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>
- [<span data-ttu-id="63003-120">ベースライン保護を使用してチームを展開する</span><span class="sxs-lookup"><span data-stu-id="63003-120">Deploy teams with baseline protection</span></span>](configure-teams-baseline-protection.md)

## <a name="guest-sharing"></a><span data-ttu-id="63003-121">ゲスト共有</span><span class="sxs-lookup"><span data-stu-id="63003-121">Guest sharing</span></span>

<span data-ttu-id="63003-122">会社の性質に応じて、このチームのゲスト共有を有効または無効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="63003-122">Depending on the nature of your business, you may or may not want to enable guest sharing for this team.</span></span> <span data-ttu-id="63003-123">チーム内の組織外のユーザーと共同作業する場合は、ゲスト共有を有効にします。</span><span class="sxs-lookup"><span data-stu-id="63003-123">If you do plan to collaborate with people outside your organization in the team, enable guest sharing.</span></span> 

<span data-ttu-id="63003-124">ゲストと安全に共有する方法の詳細については、次のリソースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63003-124">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="63003-125">組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する</span><span class="sxs-lookup"><span data-stu-id="63003-125">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [<span data-ttu-id="63003-126">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="63003-126">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

<span data-ttu-id="63003-127">ゲスト共有を許可または禁止するには、関連付けられている SharePoint サイトのチーム レベルとサイト レベルの共有コントロールに対して、秘密度ラベルを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="63003-127">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="create-a-private-team"></a><span data-ttu-id="63003-128">プライベート チームを作成する</span><span class="sxs-lookup"><span data-stu-id="63003-128">Create a private team</span></span>

<span data-ttu-id="63003-129">このチーム専用の秘密度ラベルを作成しています。次の手順では、チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="63003-129">Since we are creating a sensitivity label specifically for this team, the next step is to create the team.</span></span> <span data-ttu-id="63003-130">既存のチームがある場合は、それを使用できます。</span><span class="sxs-lookup"><span data-stu-id="63003-130">If you have an existing team, you can use that.</span></span>

<span data-ttu-id="63003-131">機密情報のチームを作成するには</span><span class="sxs-lookup"><span data-stu-id="63003-131">To create a team for sensitive information</span></span>
1. <span data-ttu-id="63003-132">Teams で、アプリの左側にある **[Teams]** をクリックして、チーム リストの下部にある **[チームに参加またはチームの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-132">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="63003-133">**[チームの作成]** (最初のカード、左上隅) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-133">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="63003-134">**[初めからチームを作成する]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="63003-134">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="63003-135">**[秘密度]**] リストで、既定のままにします。</span><span class="sxs-lookup"><span data-stu-id="63003-135">In the **Sensitivity** list, keep the default.</span></span>
5. <span data-ttu-id="63003-136">**[プライバシー]** で、**[プライベート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-136">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="63003-137">機密プロジェクトに関連するチームの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="63003-137">Type a name for the team that is related to your sensitive project.</span></span> <span data-ttu-id="63003-138">たとえば、**Project Saturn**。</span><span class="sxs-lookup"><span data-stu-id="63003-138">For example, **Project Saturn**.</span></span>
7. <span data-ttu-id="63003-139">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-139">Click **Create**.</span></span>
8. <span data-ttu-id="63003-140">チームにユーザーを追加し、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-140">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="63003-141">プライベート チャネルの設定</span><span class="sxs-lookup"><span data-stu-id="63003-141">Private channel settings</span></span>

<span data-ttu-id="63003-142">プライベート チャネルの作成権限をチームの所有者に制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="63003-142">We recommend restricting creating private channels to team owners.</span></span>

<span data-ttu-id="63003-143">プライベート チャネルの作成を制限するには</span><span class="sxs-lookup"><span data-stu-id="63003-143">To restrict private channel creation</span></span>
1. <span data-ttu-id="63003-144">チームで、**[その他のオプション]** をクリックしてから、**[チームの管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-144">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="63003-145">**[設定]** タブで、**[メンバーのアクセス許可]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="63003-145">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="63003-146">**[プライベート チャネルを作成する]** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="63003-146">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="63003-147">[チーム ポリシー](https://docs.microsoft.com/MicrosoftTeams/teams-policies)を使用して、プライベート チャネルを作成できるユーザーを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="63003-147">You can also use [teams policies](https://docs.microsoft.com/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="create-a-sensitivity-label"></a><span data-ttu-id="63003-148">秘密度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="63003-148">Create a sensitivity label</span></span>

<span data-ttu-id="63003-149">チームをセキュリティ分離用に構成するには、このチーム専用に作成された秘密度ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="63003-149">To configure a team for security isolation, we'll be using a sensitivity label created specifically for this team.</span></span> <span data-ttu-id="63003-150">このラベルは、ゲスト共有を制御し、非管理対象デバイスからのアクセスを禁止するために、チーム レベルで使用されます。</span><span class="sxs-lookup"><span data-stu-id="63003-150">This label is used at the team level to control guest sharing and to block access from unmanaged devices.</span></span> <span data-ttu-id="63003-151">チームの所有者とメンバーだけが開くことができるように、チーム内の個々のファイルを分類および暗号化するために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="63003-151">It can also be used to classify and encrypt individual files in the team so that only team owners and members can open them.</span></span>

<span data-ttu-id="63003-152">暗号化されたドキュメントを表示できますが、編集することはできない内部のパートナーや関係者のグループがある場合は、閲覧専用のアクセス許可を使用して、ラベルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="63003-152">If you have an internal partner or stakeholder group who should be able to view encrypted documents but not edit them, you can add them to the label with view-only permissions.</span></span> <span data-ttu-id="63003-153">閲覧者のアクセス許可を持つチームの SharePoint サイトにこれらのユーザーを追加することができます。また、これらのユーザーには、チーム自体ではなく、ドキュメントが保持されるサイトに対する読み取り専用のアクセス権が与えられます。</span><span class="sxs-lookup"><span data-stu-id="63003-153">You can then add these people to the team's SharePoint site with Reader permissions, and they will have read-only access to the site where the documents are kept, but not the team itself.</span></span>

<span data-ttu-id="63003-154">秘密度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="63003-154">To create a sensitivity label</span></span>
1. <span data-ttu-id="63003-155">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="63003-155">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="63003-156">**[ソリューション]** で、**[情報保護]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-156">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="63003-157">**[ラベルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-157">Click **Create a label**.</span></span>
4. <span data-ttu-id="63003-158">チーム名に似たラベルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="63003-158">Type a name for the label that is similar to your team name.</span></span> <span data-ttu-id="63003-159">たとえば、**Highly sensitive - Project Saturn** です。</span><span class="sxs-lookup"><span data-stu-id="63003-159">For example, **Highly sensitive - Project Saturn**.</span></span>
5. <span data-ttu-id="63003-160">ツール ヒントを追加し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-160">Add a tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="63003-161">**[暗号化]** ページの **[暗号化]** ドロップダウンで、**[適用]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="63003-161">On the **Encryption** page, in the **Encryption** dropdown, choose **Apply**.</span></span>
7. <span data-ttu-id="63003-162">チームのアクセス許可を追加するには:</span><span class="sxs-lookup"><span data-stu-id="63003-162">To add the team permissions:</span></span><br>
  <span data-ttu-id="63003-163">a.</span><span class="sxs-lookup"><span data-stu-id="63003-163">a.</span></span> <span data-ttu-id="63003-164">**[アクセス許可の割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-164">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="63003-165">b.</span><span class="sxs-lookup"><span data-stu-id="63003-165">b.</span></span> <span data-ttu-id="63003-166">**[ユーザーまたはグループの追加]** をクリックして、作成したチームを選択し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-166">Click **Add users or groups**, select the team that you created, and then click **Add**</span></span><br>
  <span data-ttu-id="63003-167">c. </span><span class="sxs-lookup"><span data-stu-id="63003-167">c.</span></span> <span data-ttu-id="63003-168">**[アクセス許可の選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-168">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="63003-169">d. </span><span class="sxs-lookup"><span data-stu-id="63003-169">d.</span></span> <span data-ttu-id="63003-170">ドロップダウン リストから **[共同編集者]** を選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-170">Choose **Co-Author** from the dropdown list, and then click **Save**.</span></span><br>
8. <span data-ttu-id="63003-171">ラベルを使用してファイルに読み取り専用アクセス権を持つユーザーまたはグループを含める場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="63003-171">If you want to include users or groups with read-only access to files with the label:</span></span><br>
  <span data-ttu-id="63003-172">a.</span><span class="sxs-lookup"><span data-stu-id="63003-172">a.</span></span> <span data-ttu-id="63003-173">**[アクセス許可の割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-173">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="63003-174">b.</span><span class="sxs-lookup"><span data-stu-id="63003-174">b.</span></span> <span data-ttu-id="63003-175">**[ユーザーまたはグループの追加]** をクリックして、追加するユーザーまたはグループを選択し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-175">Click **Add users or groups**, select the users or groups that you want to add, and then click **Add**.</span></span><br>
  <span data-ttu-id="63003-176">c. </span><span class="sxs-lookup"><span data-stu-id="63003-176">c.</span></span> <span data-ttu-id="63003-177">**[アクセス許可の選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-177">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="63003-178">d. </span><span class="sxs-lookup"><span data-stu-id="63003-178">d.</span></span> <span data-ttu-id="63003-179">ドロップダウン リストから **[閲覧者]** を選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-179">Choose **Viewer** from the dropdown list, and then click **Save**.</span></span><br>
  <span data-ttu-id="63003-180">e. </span><span class="sxs-lookup"><span data-stu-id="63003-180">e.</span></span> <span data-ttu-id="63003-181">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-181">Click **Save**.</span></span>
9. <span data-ttu-id="63003-182">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-182">Click **Next**.</span></span>
10. <span data-ttu-id="63003-183">このラベルで分類されているファイルにヘッダー、フッター、またはウォーターマークを自動的に追加するには、**[コンテンツのマーキング]** ページで、[コンテンツのマーキング] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="63003-183">On the **Content marking** page, turn on content marking if you want to automatically add a header, footer, or watermark to files that are classified with this label.</span></span>
11. <span data-ttu-id="63003-184">**[サイトとグループの設定]** ページで、**[サイトとグループの設定]** を **[オン]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="63003-184">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
12. <span data-ttu-id="63003-185">**[Office 365 グループに接続されているチーム サイトのプライバシー]** ドロップダウンで、**[非公開 - メンバーのみがサイトにアクセス可能]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="63003-185">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
13. <span data-ttu-id="63003-186">ゲスト アクセスを許可する場合は、**[Ofﬁce 365 グループ所有者が組織外のユーザーをグループに追加できるようにする**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="63003-186">If you want to allow guest access, select the **Let Office 365 group owners add people outside the organization to the group** check box.</span></span> 
14. <span data-ttu-id="63003-187">**[非管理対象デバイス]** で、**[アクセスをブロックする]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="63003-187">Under **Unmanaged devices**, choose **Block access**.</span></span>
15. <span data-ttu-id="63003-188">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-188">Click **Next**.</span></span>
16. <span data-ttu-id="63003-189">**[Office アプリの自動ラベル付け]** ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-189">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
17. <span data-ttu-id="63003-190">**[送信]** をクリックしてから、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-190">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="63003-191">ラベルを作成したら、それを使用するユーザーに発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63003-191">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="63003-192">この場合、ラベルをチーム内のユーザーのみが使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="63003-192">In this case, we'll make the label available only to people in the team.</span></span>

<span data-ttu-id="63003-193">秘密度ラベルを発行する</span><span class="sxs-lookup"><span data-stu-id="63003-193">To publish a sensitivity label</span></span>
1. <span data-ttu-id="63003-194">Microsoft 365 コンプライアンス センターまたは **[情報保護]** ページで、**[ラベル ポリシー]** タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="63003-194">In the Microsoft 365 compliance center, on the **Information protection** page, choose the **Label policies** tab.</span></span>
2. <span data-ttu-id="63003-195">**[ラベルの発行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-195">Click **Publish labels**.</span></span>
3. <span data-ttu-id="63003-196">**[発行する秘密度ラベルの選択]** ページで、**[発行する秘密度ラベルの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-196">On the **Choose sensitivity labels to publish** page, click **Choose sensitivity labels to publish**.</span></span>
4. <span data-ttu-id="63003-197">作成したラベルを選択し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-197">Select the label that you created, and then click **Add**.</span></span>
5. <span data-ttu-id="63003-198">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-198">Click **Next**.</span></span>
6. <span data-ttu-id="63003-199">[ユーザーとグループに発行] ページで、**[ユーザーとグループの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-199">On the Publish to users and groups page, click **Choose users and groups**.</span></span>
7. <span data-ttu-id="63003-200">**[追加]** をクリックし、作成したチームを選びます。</span><span class="sxs-lookup"><span data-stu-id="63003-200">Click **Add**, and then select the team that you created.</span></span>
8. <span data-ttu-id="63003-201">**[追加]** をクリックし、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-201">Click **Add**, and then click **Done**.</span></span>
9. <span data-ttu-id="63003-202">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-202">Click **Next**.</span></span>
10. <span data-ttu-id="63003-203">[ポリシーの設定] ページで、**[ユーザーはラベルを削除するか、分類ラベルを下げるために正当な理由を提供する必要がある]** チェック ボックスをオンにし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-203">On the Policy settings page, select the **Users must provide justification to remove a label or lower classification label** check box, and then click **Next**.</span></span>
11. <span data-ttu-id="63003-204">ポリシーの名前を入力し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-204">Type a name for the policy, and then click **Next**.</span></span>
12. <span data-ttu-id="63003-205">**[送信]** をクリックしてから、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-205">Click **Submit** and then click **Done**.</span></span>

## <a name="apply-the-label-to-the-team"></a><span data-ttu-id="63003-206">チームにラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="63003-206">Apply the label to the team</span></span>

<span data-ttu-id="63003-207">ラベルを発行したら、ゲスト共有および管理対象デバイスの設定を有効にするために、ラベルをチームに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63003-207">Once the label has been published, you must apply it to the team in order for the guest sharing and managed devices settings to take effect.</span></span> <span data-ttu-id="63003-208">この操作は SharePoint 管理センターで行います。</span><span class="sxs-lookup"><span data-stu-id="63003-208">This is done in the SharePoint admin center.</span></span> <span data-ttu-id="63003-209">発行後にラベルが使用可能になるまでに、しばらく時間がかかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="63003-209">Note, it may take some time for the label to become available after it's been published.</span></span>

<span data-ttu-id="63003-210">秘密度ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="63003-210">To apply the sensitivity label</span></span>
1. <span data-ttu-id="63003-211">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="63003-211">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="63003-212">**[サイト]** で、**[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-212">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="63003-213">チームに関連付けられているサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-213">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="63003-214">**[ポリシー]** タブで、**[秘密度]** の下側にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-214">On the **Policies** tab, under **Sensitivity**, click **Edit**.</span></span>
5. <span data-ttu-id="63003-215">作成したラベルを選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-215">Select the label that you created, and then click **Save**.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="63003-216">SharePoint の設定</span><span class="sxs-lookup"><span data-stu-id="63003-216">SharePoint settings</span></span>

<span data-ttu-id="63003-217">SharePoint では、次の 3 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="63003-217">There are three steps to do in SharePoint:</span></span>

- <span data-ttu-id="63003-218">ラベルを作成したときに選択したものと一致するように、SharePoint 管理センターでサイトのゲスト共有設定を更新し、*既存のアクセス権を持つユーザー*に対して、既定の共有リンクを更新します。</span><span class="sxs-lookup"><span data-stu-id="63003-218">Update the guest sharing settings for the site in the SharePoint admin center to match what you chose when you created the label, and update the default sharing link to *People with existing access*.</span></span>
- <span data-ttu-id="63003-219">サイト自体の共有設定を更新し、メンバーがファイル、フォルダー、サイトを共有できないようにし、アクセス要求を無効にします。</span><span class="sxs-lookup"><span data-stu-id="63003-219">Update the site sharing settings in the site itself to prevent members from sharing files, folders, or the site, and turn off access requests.</span></span>
- <span data-ttu-id="63003-220">閲覧者アクセス許可を持つラベルにユーザーまたはグループを追加した場合は、それらを読み取りアクセス許可を持つ SharePoint サイトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="63003-220">If you added people or groups to the label with Viewer permissions, you can add them to the SharePoint site with Read permissions.</span></span>

### <a name="sharepoint-guest-settings"></a><span data-ttu-id="63003-221">SharePoint ゲストの設定</span><span class="sxs-lookup"><span data-stu-id="63003-221">SharePoint guest settings</span></span>

<span data-ttu-id="63003-222">ラベルを作成したときに選択したゲスト共有設定 (チーム メンバーシップのみに影響します) は、以下のように関連付けられている SharePoint サイトのゲスト共有設定と一致します。</span><span class="sxs-lookup"><span data-stu-id="63003-222">The guest sharing setting that you chose when you created the label (which only affects team membership) should match the guest sharing settings for the associated SharePoint site as follows:</span></span>

|<span data-ttu-id="63003-223">ラベルの設定</span><span class="sxs-lookup"><span data-stu-id="63003-223">Label setting</span></span>|<span data-ttu-id="63003-224">SharePoint サイトの設定</span><span class="sxs-lookup"><span data-stu-id="63003-224">SharePoint site setting</span></span>|
|:------------|:----------------------|
|<span data-ttu-id="63003-225">**Ofﬁce 365 グループ所有者が組織外のユーザーをグループに追加できるようにする**が選択されている</span><span class="sxs-lookup"><span data-stu-id="63003-225">**Let Office 365 group owners add people outside the organization to the group** selected</span></span>|<span data-ttu-id="63003-226">**新規および既存のゲスト** (新規チームの既定値)</span><span class="sxs-lookup"><span data-stu-id="63003-226">**New and existing guests** (default for new teams)</span></span>|
|<span data-ttu-id="63003-227">**Ofﬁce 365 グループ所有者が組織外のユーザーをグループに追加できるようにする**が選択されていない</span><span class="sxs-lookup"><span data-stu-id="63003-227">**Let Office 365 group owners add people outside the organization to the group** not selected</span></span>|<span data-ttu-id="63003-228">**組織内のユーザーのみ**</span><span class="sxs-lookup"><span data-stu-id="63003-228">**Only people in your organization**</span></span>|

<span data-ttu-id="63003-229">また、既定の共有リンクの種類を更新して、意図したよりも広い対象ユーザーにファイルやフォルダーが不用意に共有されるリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="63003-229">We'll also update the default sharing link type to reduce the risk of accidentally sharing files and folders to a wider audience than intended.</span></span>

<span data-ttu-id="63003-230">サイトの設定を更新する</span><span class="sxs-lookup"><span data-stu-id="63003-230">To update site settings</span></span>
1. <span data-ttu-id="63003-231">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="63003-231">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="63003-232">**[サイト]** で、**[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-232">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="63003-233">チームに関連付けられているサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-233">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="63003-234">**[ポリシー]** タブで、**[外部共有]** の下側にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-234">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="63003-235">秘密度ラベルを作成したときにゲスト共有が許可されていた場合は、**[新規および既存のゲスト]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="63003-235">If you allowed guest sharing when you created the sensitive label, ensure that **New and existing guests** is selected.</span></span> <span data-ttu-id="63003-236">秘密度ラベルを作成したときにゲスト共有が許可されていなかった場合は、**[組織内のユーザーのみ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="63003-236">If you didn't allow sharing when you created the label, choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="63003-237">[既定の共有リンクの種類] で、**[組織レベルの設定と同じ]** チェック ボックスをオフにして、**[既存のアクセス権を持つユーザー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="63003-237">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="63003-238">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-238">Click **Save**.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="63003-239">プライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="63003-239">Private channels</span></span>

<span data-ttu-id="63003-240">チームにプライベート チャネルを追加する場合、各プライベート チャネルは、既定の共有設定を使用して新しい SharePoint サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="63003-240">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="63003-241">これらのサイトは SharePoint 管理センターでは表示されないので、次のパラメーターと共に [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) PowerShell コマンドレットを使用して、ゲスト共有設定を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63003-241">These sites are not visible in the SharePoint admin center, so you must use the [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) PowerShell cmdlet with the following parameters to update the guest sharing settings:</span></span>

- <span data-ttu-id="63003-242">`-SharingCapability Disabled` ゲスト共有を無効にするには (既定では有効です)</span><span class="sxs-lookup"><span data-stu-id="63003-242">`-SharingCapability Disabled` to turn off guest sharing (it's on by default)</span></span>
- <span data-ttu-id="63003-243">`-DefaultSharingLinkType Internal` 既定の共有リンクを*特定のユーザー*に変更するには</span><span class="sxs-lookup"><span data-stu-id="63003-243">`-DefaultSharingLinkType Internal` to change the default sharing link to *Specific people*</span></span>

<span data-ttu-id="63003-244">チームでプライベート チャネルを使用する予定がない場合は、[[チーム設定]](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc) の **[メンバーのアクセス許可]** で、チーム メンバーがチームを作成する権限を無効にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="63003-244">If you don't plan to use private channels with your team, consider turning off the ability for team members to create them under **Member permissions** in [team settings](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc).</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="63003-245">サイト共有設定</span><span class="sxs-lookup"><span data-stu-id="63003-245">Site sharing settings</span></span>

<span data-ttu-id="63003-246">SharePoint サイトがチーム メンバーではないユーザーと共有されないようにするには、SharePoint サイトの共有を所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="63003-246">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span> <span data-ttu-id="63003-247">また、ファイルとフォルダーの共有をチームの所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="63003-247">We also limit sharing of files and folders to team owners.</span></span> <span data-ttu-id="63003-248">これにより、ファイルがチーム外のユーザーと共有されるたびに所有者が認識できます。</span><span class="sxs-lookup"><span data-stu-id="63003-248">This helps ensure that owners are aware whenever a file is shared with someone outside the team.</span></span>

<span data-ttu-id="63003-249">所有者のみのサイト共有を構成する</span><span class="sxs-lookup"><span data-stu-id="63003-249">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="63003-250">Teams で、更新するチームの **[全般]** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="63003-250">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="63003-251">チームのツール バーで、**[ファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-251">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="63003-252">省略記号をクリックし、**[SharePoint で開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-252">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="63003-253">基となる SharePoint サイトのツール バーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-253">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="63003-254">[サイトの権限] ウィンドウで、**[共有設定]** の **[共有設定の変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-254">In the Site permissions pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
6. <span data-ttu-id="63003-255">**[共有アクセス許可]** で、**[サイト所有者のみが、ファイル、フォルダー、およびサイトを共有できます]** を選択して、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-255">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

### <a name="custom-site-permissions"></a><span data-ttu-id="63003-256">カスタム サイトのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="63003-256">Custom site permissions</span></span>

<span data-ttu-id="63003-257">閲覧者のアクセス許可を持つユーザーを秘密度ラベルに追加した場合は、それらを読み取りアクセス権を持つ SharePoint サイトに追加し、ファイルに簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="63003-257">If you added people with Viewer permissions to the sensitivity label, you can add them to the SharePoint site with Read access so they have easy access to the files.</span></span>

<span data-ttu-id="63003-258">サイトにユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="63003-258">To add users to the site</span></span>
1. <span data-ttu-id="63003-259">サイトの設定アイコンをクリックし、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-259">In the site, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="63003-260">**[ユーザーの招待]** をクリックして、**[サイトのみ共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-260">Click **Invite people**, and then click **Share site only**.</span></span>
3. <span data-ttu-id="63003-261">招待するユーザーとグループの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="63003-261">Type the names of the users and groups that you want to invite.</span></span>
4. <span data-ttu-id="63003-262">追加するユーザーまたはグループごとに、そのアクセス許可を **[編集]** から **[読み取り]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="63003-262">For each person or group that you add, change their permissions from **Edit** to **Read**.</span></span>
5. <span data-ttu-id="63003-263">サイトへのリンクを含むメールを送信するかどうかを選びます。</span><span class="sxs-lookup"><span data-stu-id="63003-263">Choose if you want to send them an email with a link to the site.</span></span>
6. <span data-ttu-id="63003-264">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63003-264">Click **Add**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="63003-265">追加の保護</span><span class="sxs-lookup"><span data-stu-id="63003-265">Additional protections</span></span>

<span data-ttu-id="63003-266">Microsoft 365 は、コンテンツを保護するための追加の方法を提供しています。</span><span class="sxs-lookup"><span data-stu-id="63003-266">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="63003-267">次のオプションを使用して、組織のセキュリティを強化することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="63003-267">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="63003-268">ゲスト ユーザーを[使用条件](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)に同意させる。</span><span class="sxs-lookup"><span data-stu-id="63003-268">Have your guest users agree to a [terms of use](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="63003-269">ゲストに[セッション タイムアウト ポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)を設定する。</span><span class="sxs-lookup"><span data-stu-id="63003-269">Configure a [session timeout policy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="63003-270">[機密情報の種類](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)を作成し、[データ損失防止](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)を使用して、機密情報にアクセスするポリシーを設定する。</span><span class="sxs-lookup"><span data-stu-id="63003-270">Create [sensitive information types](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) and use [data loss protection](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to set policies around accessing sensitive information.</span></span>
- <span data-ttu-id="63003-271">[Azure Active Directory アクセス](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) レビューを使用して、チームのアクセス権とメンバーシップを定期的に確認する。</span><span class="sxs-lookup"><span data-stu-id="63003-271">Use [Azure Active Directory access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) reviews to periodically review team access and membership.</span></span>

## <a name="drive-user-adoption-for-team-members"></a><span data-ttu-id="63003-272">チーム メンバーのユーザーによる導入を促す</span><span class="sxs-lookup"><span data-stu-id="63003-272">Drive user adoption for team members</span></span>

<span data-ttu-id="63003-273">チームを設置したら、このチームの導入とチーム メンバーへの追加のセキュリティを促します。</span><span class="sxs-lookup"><span data-stu-id="63003-273">With the team in place, it's time to drive the adoption of this team and its additional security to team members.</span></span>

## <a name="train-your-users"></a><span data-ttu-id="63003-274">ユーザーをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="63003-274">Train your users</span></span>

<span data-ttu-id="63003-275">チームのメンバーは、チームおよびそのすべてのリソース (チャット、会議、およびその他のアプリなど) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="63003-275">Members of the team can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="63003-276">チャネルの [**ファイル**] セクションにあるファイルで作業をする場合、チームのメンバーは、作成したファイルに秘密度ラベルを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="63003-276">When working with files from the **Files** section of a channel, members of the team should assign the sensitivity label to the files they create.</span></span>

<span data-ttu-id="63003-277">ラベルがファイルに適用されると、ファイルは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="63003-277">When the label gets applied to the file, it is encrypted.</span></span> <span data-ttu-id="63003-278">チームのメンバーは、ファイルを開いてリアルタイムで共同作業を行えます。</span><span class="sxs-lookup"><span data-stu-id="63003-278">Members of the team can open it and collaborate in real time.</span></span> <span data-ttu-id="63003-279">ファイルがサイトを離れて悪意のあるユーザーに転送された場合、そのようなユーザーがファイルを開いて内容を表示するには、チーム メンバーのユーザー アカウントの資格情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="63003-279">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the team to open the file and view its contents.</span></span> 

<span data-ttu-id="63003-280">チーム メンバーをトレーニングする:</span><span class="sxs-lookup"><span data-stu-id="63003-280">Train your team members:</span></span>

- <span data-ttu-id="63003-281">SharePoint サイトのチャット、会議、ファイル、その他のリソースに新しいチームを使用することの重要性と、厳しく規制されたデータのリークによって生じる事態 (法的影響、規制上の罰金、ランサムウェア、競争力の低下など)。</span><span class="sxs-lookup"><span data-stu-id="63003-281">On the importance of using the new team for chats, meetings, files, and the other resources of the SharePoint site and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="63003-282">チームにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="63003-282">How to access the team.</span></span>
- <span data-ttu-id="63003-283">サイトに新しいファイルを作成し、ローカルに保存された新しいファイルをアップロードする方法。</span><span class="sxs-lookup"><span data-stu-id="63003-283">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="63003-284">チームの正しい秘密度ラベルでファイルにラベルを付ける方法。</span><span class="sxs-lookup"><span data-stu-id="63003-284">How to label files with the correct sensitivity label for the team.</span></span>
- <span data-ttu-id="63003-285">ファイルがサイトからリークされてもラベルによって保護されるしくみ。</span><span class="sxs-lookup"><span data-stu-id="63003-285">How the label protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="63003-286">このトレーニングには、チーム メンバーが上記の機能とその結果を体感できるように、実践的な演習を組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="63003-286">This training should include hands-on exercises so that your team members can experience these capabilities and their results.</span></span>

### <a name="conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="63003-287">使用状況を定期的にレビューし、チーム メンバーのフィードバックに対処する</span><span class="sxs-lookup"><span data-stu-id="63003-287">Conduct periodic reviews of usage and address team member feedback</span></span>

<span data-ttu-id="63003-288">トレーニング後の数週間、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="63003-288">In the weeks after training:</span></span>

- <span data-ttu-id="63003-289">チーム メンバーのフィードバックに迅速に対応し、ポリシーと構成を微調整します。</span><span class="sxs-lookup"><span data-stu-id="63003-289">Quickly address team member feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="63003-290">チームの使用状況を分析し、それが期待された使用法と一致しているかを比較する。</span><span class="sxs-lookup"><span data-stu-id="63003-290">Analyze usage for the team and compare it with usage expectations.</span></span>
- <span data-ttu-id="63003-291">厳しく規制されたファイルが秘密度ラベルを使用して正しくラベル付けされていることを確認する。</span><span class="sxs-lookup"><span data-stu-id="63003-291">Verify that highly regulated files have been properly labeled with the sensitivity label.</span></span> <span data-ttu-id="63003-292">(ラベルが割り当てられているファイルがわかるようにするには、SharePoint のフォルダーを表示し、[**列の追加**] で [**列の表示/非表示**] オプションを使用して [**秘密度**] 列を追加します。)</span><span class="sxs-lookup"><span data-stu-id="63003-292">(You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="63003-293">必要に応じて、ユーザーの再トレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="63003-293">Retrain your users as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="63003-294">関連項目</span><span class="sxs-lookup"><span data-stu-id="63003-294">See also</span></span>

[<span data-ttu-id="63003-295">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="63003-295">Azure AD Privileged Identity Management</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)