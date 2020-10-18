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
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- Ent_Solutions
description: セキュリティ固有の秘密度ラベルを使用してチームを作成する方法について説明します。
ms.openlocfilehash: 46bc63bab52bf75dc7c215510d49b4d985ff07c3
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487484"
---
# <a name="configure-a-team-with-security-isolation"></a><span data-ttu-id="119c4-103">セキュリティの分離を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="119c4-103">Configure a team with security isolation</span></span>

<span data-ttu-id="119c4-104">この記事では、Microsoft Teams でプライベート チームを構成し、固有の秘密度ラベルを使用してファイルを暗号化して、チーム メンバーのみがファイルを復号化できるようにするための推奨事項と手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="119c4-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams and use a unique sensitivity label to encrypt files so that only team members can decrypt them.</span></span>

<span data-ttu-id="119c4-105">この記事では、プライベート アクセスの他にも、チーム チャネルの [**ファイル**] セクションからアクセスできる関連付けられた SharePoint サイトを構成して厳しく規制されたデータの保存で必要な追加のセキュリティを提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="119c4-105">Beyond the private access, this article describes how to configure the associated SharePoint site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span>

<span data-ttu-id="119c4-106">セキュリティの分離を使用するチームの構成における要素は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="119c4-106">The elements of configuration for a team with security isolation are:</span></span>

- <span data-ttu-id="119c4-107">プライベート チーム</span><span class="sxs-lookup"><span data-stu-id="119c4-107">A private team</span></span>
- <span data-ttu-id="119c4-108">チームに関連付けられた SharePoint サイトでの以下の追加のセキュリティ:</span><span class="sxs-lookup"><span data-stu-id="119c4-108">Additional security on the associated SharePoint site for the team that:</span></span>
  - <span data-ttu-id="119c4-109">サイトのメンバーがサイトを他のユーザーと共有することの防止。</span><span class="sxs-lookup"><span data-stu-id="119c4-109">Prevents members of the site from sharing the site with others.</span></span>
  - <span data-ttu-id="119c4-110">サイトのメンバーではないユーザーがサイトへのアクセス権を要求することの防止。</span><span class="sxs-lookup"><span data-stu-id="119c4-110">Prevents non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="119c4-111">このチーム専用の秘密度ラベル:</span><span class="sxs-lookup"><span data-stu-id="119c4-111">A sensitivity label specifically for this team that:</span></span>
    - <span data-ttu-id="119c4-112">非管理対象デバイスから SharePoint コンテンツにアクセスできないようにする</span><span class="sxs-lookup"><span data-stu-id="119c4-112">Prevents access to SharePoint content from unmanaged devices</span></span>
    - <span data-ttu-id="119c4-113">要求に応じて、チームのゲストアクセスを許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="119c4-113">Allows or denies guest access to the team, depending on your requirements</span></span>
    - <span data-ttu-id="119c4-114">ラベルを適用するドキュメントを暗号化する</span><span class="sxs-lookup"><span data-stu-id="119c4-114">Encrypts documents to which the label is applied</span></span>

> [!IMPORTANT]
> <span data-ttu-id="119c4-115">この記事の手順に進む前に、「[Microsoft Teams、Office 365 グループ、SharePoint サイトのコンテンツを保護するために秘密度ラベル](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)を有効にしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="119c4-115">Be sure you have enabled [sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites) before you proceed with the steps in this article.</span></span>

<span data-ttu-id="119c4-116">このビデオでは、展開プロセスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="119c4-116">Watch this video for an overview of the deployment process.</span></span>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a> <span data-ttu-id="119c4-117">このシナリオを 2 ページにまとめた、「[セキュリティの分離ポスター を使用した Microsoft Teams](../downloads/team-security-isolation-poster.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="119c4-117">For a 2-page summary of this scenario, see the [Microsoft Teams with security isolation poster](../downloads/team-security-isolation-poster.pdf).</span></span>

<span data-ttu-id="119c4-118">[![セキュリティの分離ポスター を使用した Microsoft Teams](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)</span><span class="sxs-lookup"><span data-stu-id="119c4-118">[![Microsoft Teams with security isolation poster](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)</span></span>

<span data-ttu-id="119c4-119">このポスターを [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) 形式でダウンロードし、レター、リーガル、タブロイド (11 x 17) のサイズの用紙に印刷することもできます。</span><span class="sxs-lookup"><span data-stu-id="119c4-119">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

## <a name="initial-protections"></a><span data-ttu-id="119c4-120">初期保護</span><span class="sxs-lookup"><span data-stu-id="119c4-120">Initial protections</span></span>

<span data-ttu-id="119c4-121">チームおよび基になる SharePoint サイトへのアクセスを保護するためには、次のベスト プラクティスを確認します。</span><span class="sxs-lookup"><span data-stu-id="119c4-121">To help protect access to the team and its underlying SharePoint site, review the following best practices:</span></span>
- [<span data-ttu-id="119c4-122">ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="119c4-122">Identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="119c4-123">SharePoint Online アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="119c4-123">SharePoint Online access policies</span></span>](../security/office-365-security/sharepoint-file-access-policies.md)
- [<span data-ttu-id="119c4-124">ベースライン保護を使用してチームを展開する</span><span class="sxs-lookup"><span data-stu-id="119c4-124">Deploy teams with baseline protection</span></span>](configure-teams-baseline-protection.md)

## <a name="guest-sharing"></a><span data-ttu-id="119c4-125">ゲスト共有</span><span class="sxs-lookup"><span data-stu-id="119c4-125">Guest sharing</span></span>

<span data-ttu-id="119c4-126">会社の性質に応じて、このチームのゲスト共有を有効または無効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="119c4-126">Depending on the nature of your business, you may or may not want to enable guest sharing for this team.</span></span> <span data-ttu-id="119c4-127">チーム内の組織外のユーザーと共同作業する場合は、ゲスト共有を有効にします。</span><span class="sxs-lookup"><span data-stu-id="119c4-127">If you do plan to collaborate with people outside your organization in the team, enable guest sharing.</span></span> 

<span data-ttu-id="119c4-128">ゲストと安全に共有する方法の詳細については、次のリソースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="119c4-128">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="119c4-129">組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する</span><span class="sxs-lookup"><span data-stu-id="119c4-129">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)
- [<span data-ttu-id="119c4-130">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="119c4-130">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

<span data-ttu-id="119c4-131">ゲスト共有を許可または禁止するには、関連付けられている SharePoint サイトのチーム レベルとサイト レベルの共有コントロールに対して、秘密度ラベルを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="119c4-131">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="create-a-private-team"></a><span data-ttu-id="119c4-132">プライベート チームを作成する</span><span class="sxs-lookup"><span data-stu-id="119c4-132">Create a private team</span></span>

<span data-ttu-id="119c4-133">このチーム専用の秘密度ラベルを作成しています。次の手順では、チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="119c4-133">Since we are creating a sensitivity label specifically for this team, the next step is to create the team.</span></span> <span data-ttu-id="119c4-134">既存のチームがある場合は、それを使用できます。</span><span class="sxs-lookup"><span data-stu-id="119c4-134">If you have an existing team, you can use that.</span></span>

<span data-ttu-id="119c4-135">機密情報のチームを作成するには</span><span class="sxs-lookup"><span data-stu-id="119c4-135">To create a team for sensitive information</span></span>
1. <span data-ttu-id="119c4-136">Teams で、アプリの左側にある **[Teams]** をクリックして、チーム リストの下部にある **[チームに参加またはチームの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-136">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="119c4-137">**[チームの作成]** (最初のカード、左上隅) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-137">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="119c4-138">**[初めからチームを作成する]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="119c4-138">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="119c4-139">**[秘密度]**] リストで、既定のままにします。</span><span class="sxs-lookup"><span data-stu-id="119c4-139">In the **Sensitivity** list, keep the default.</span></span>
5. <span data-ttu-id="119c4-140">**[プライバシー]** で、**[プライベート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-140">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="119c4-141">機密プロジェクトに関連するチームの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="119c4-141">Type a name for the team that is related to your sensitive project.</span></span> <span data-ttu-id="119c4-142">たとえば、**Project Saturn**。</span><span class="sxs-lookup"><span data-stu-id="119c4-142">For example, **Project Saturn**.</span></span>
7. <span data-ttu-id="119c4-143">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-143">Click **Create**.</span></span>
8. <span data-ttu-id="119c4-144">チームにユーザーを追加し、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-144">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="119c4-145">プライベート チャネルの設定</span><span class="sxs-lookup"><span data-stu-id="119c4-145">Private channel settings</span></span>

<span data-ttu-id="119c4-146">プライベート チャネルの作成権限をチームの所有者に制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="119c4-146">We recommend restricting creating private channels to team owners.</span></span>

<span data-ttu-id="119c4-147">プライベート チャネルの作成を制限するには</span><span class="sxs-lookup"><span data-stu-id="119c4-147">To restrict private channel creation</span></span>
1. <span data-ttu-id="119c4-148">チームで、**[その他のオプション]** をクリックしてから、**[チームの管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-148">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="119c4-149">**[設定]** タブで、**[メンバーのアクセス許可]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="119c4-149">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="119c4-150">**[プライベート チャネルを作成する]** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="119c4-150">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="119c4-151">[チーム ポリシー](https://docs.microsoft.com/MicrosoftTeams/teams-policies)を使用して、プライベート チャネルを作成できるユーザーを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="119c4-151">You can also use [teams policies](https://docs.microsoft.com/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="create-a-sensitivity-label"></a><span data-ttu-id="119c4-152">秘密度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="119c4-152">Create a sensitivity label</span></span>

<span data-ttu-id="119c4-153">チームをセキュリティ分離用に構成するには、このチーム専用に作成された秘密度ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="119c4-153">To configure a team for security isolation, we'll be using a sensitivity label created specifically for this team.</span></span> <span data-ttu-id="119c4-154">このラベルは、ゲスト共有を制御し、非管理対象デバイスからのアクセスを禁止するために、チーム レベルで使用されます。</span><span class="sxs-lookup"><span data-stu-id="119c4-154">This label is used at the team level to control guest sharing and to block access from unmanaged devices.</span></span> <span data-ttu-id="119c4-155">チームの所有者とメンバーだけが開くことができるように、チーム内の個々のファイルを分類および暗号化するために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="119c4-155">It can also be used to classify and encrypt individual files in the team so that only team owners and members can open them.</span></span>

<span data-ttu-id="119c4-156">暗号化されたドキュメントを表示できますが、編集することはできない内部のパートナーや関係者のグループがある場合は、閲覧専用のアクセス許可を使用して、ラベルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="119c4-156">If you have an internal partner or stakeholder group who should be able to view encrypted documents but not edit them, you can add them to the label with view-only permissions.</span></span> <span data-ttu-id="119c4-157">閲覧者のアクセス許可を持つチームの SharePoint サイトにこれらのユーザーを追加することができます。また、これらのユーザーには、チーム自体ではなく、ドキュメントが保持されるサイトに対する読み取り専用のアクセス権が与えられます。</span><span class="sxs-lookup"><span data-stu-id="119c4-157">You can then add these people to the team's SharePoint site with Reader permissions, and they will have read-only access to the site where the documents are kept, but not the team itself.</span></span>

<span data-ttu-id="119c4-158">秘密度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="119c4-158">To create a sensitivity label</span></span>
1. <span data-ttu-id="119c4-159">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="119c4-159">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="119c4-160">**[ソリューション]** で、**[情報保護]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-160">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="119c4-161">**[ラベルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-161">Click **Create a label**.</span></span>
4. <span data-ttu-id="119c4-162">チーム名に似たラベルの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="119c4-162">Type a name for the label that is similar to your team name.</span></span> <span data-ttu-id="119c4-163">たとえば、**Highly sensitive - Project Saturn** です。</span><span class="sxs-lookup"><span data-stu-id="119c4-163">For example, **Highly sensitive - Project Saturn**.</span></span>
5. <span data-ttu-id="119c4-164">ツール ヒントを追加し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-164">Add a tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="119c4-165">**[暗号化]** ページの **[暗号化]** ドロップダウンで、**[適用]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="119c4-165">On the **Encryption** page, in the **Encryption** dropdown, choose **Apply**.</span></span>
7. <span data-ttu-id="119c4-166">チームのアクセス許可を追加するには:</span><span class="sxs-lookup"><span data-stu-id="119c4-166">To add the team permissions:</span></span><br>
  <span data-ttu-id="119c4-167">a.</span><span class="sxs-lookup"><span data-stu-id="119c4-167">a.</span></span> <span data-ttu-id="119c4-168">**[アクセス許可の割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-168">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="119c4-169">b.</span><span class="sxs-lookup"><span data-stu-id="119c4-169">b.</span></span> <span data-ttu-id="119c4-170">**[ユーザーまたはグループの追加]** をクリックして、作成したチームを選択し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-170">Click **Add users or groups**, select the team that you created, and then click **Add**</span></span><br>
  <span data-ttu-id="119c4-171">c. </span><span class="sxs-lookup"><span data-stu-id="119c4-171">c.</span></span> <span data-ttu-id="119c4-172">**[アクセス許可の選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-172">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="119c4-173">d. </span><span class="sxs-lookup"><span data-stu-id="119c4-173">d.</span></span> <span data-ttu-id="119c4-174">ドロップダウン リストから **[共同編集者]** を選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-174">Choose **Co-Author** from the dropdown list, and then click **Save**.</span></span><br>
8. <span data-ttu-id="119c4-175">ラベルを使用してファイルに読み取り専用アクセス権を持つユーザーまたはグループを含める場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="119c4-175">If you want to include users or groups with read-only access to files with the label:</span></span><br>
  <span data-ttu-id="119c4-176">a.</span><span class="sxs-lookup"><span data-stu-id="119c4-176">a.</span></span> <span data-ttu-id="119c4-177">**[アクセス許可の割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-177">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="119c4-178">b.</span><span class="sxs-lookup"><span data-stu-id="119c4-178">b.</span></span> <span data-ttu-id="119c4-179">**[ユーザーまたはグループの追加]** をクリックして、追加するユーザーまたはグループを選択し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-179">Click **Add users or groups**, select the users or groups that you want to add, and then click **Add**.</span></span><br>
  <span data-ttu-id="119c4-180">c. </span><span class="sxs-lookup"><span data-stu-id="119c4-180">c.</span></span> <span data-ttu-id="119c4-181">**[アクセス許可の選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-181">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="119c4-182">d. </span><span class="sxs-lookup"><span data-stu-id="119c4-182">d.</span></span> <span data-ttu-id="119c4-183">ドロップダウン リストから **[閲覧者]** を選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-183">Choose **Viewer** from the dropdown list, and then click **Save**.</span></span><br>
  <span data-ttu-id="119c4-184">e. </span><span class="sxs-lookup"><span data-stu-id="119c4-184">e.</span></span> <span data-ttu-id="119c4-185">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-185">Click **Save**.</span></span>
9. <span data-ttu-id="119c4-186">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-186">Click **Next**.</span></span>
10. <span data-ttu-id="119c4-187">このラベルで分類されているファイルにヘッダー、フッター、またはウォーターマークを自動的に追加するには、**[コンテンツのマーキング]** ページで、[コンテンツのマーキング] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="119c4-187">On the **Content marking** page, turn on content marking if you want to automatically add a header, footer, or watermark to files that are classified with this label.</span></span>
11. <span data-ttu-id="119c4-188">**[サイトとグループの設定]** ページで、**[サイトとグループの設定]** を **[オン]** に設定します。</span><span class="sxs-lookup"><span data-stu-id="119c4-188">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
12. <span data-ttu-id="119c4-189">**[Office 365 グループに接続されているチーム サイトのプライバシー]** ドロップダウンで、**[非公開 - メンバーのみがサイトにアクセス可能]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="119c4-189">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
13. <span data-ttu-id="119c4-190">ゲスト アクセスを許可する場合は、**[Ofﬁce 365 グループ所有者が組織外のユーザーをグループに追加できるようにする**] チェック ボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="119c4-190">If you want to allow guest access, select the **Let Office 365 group owners add people outside the organization to the group** check box.</span></span> 
14. <span data-ttu-id="119c4-191">**[非管理対象デバイス]** で、**[アクセスをブロックする]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="119c4-191">Under **Unmanaged devices**, choose **Block access**.</span></span>
15. <span data-ttu-id="119c4-192">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-192">Click **Next**.</span></span>
16. <span data-ttu-id="119c4-193">**[Office アプリの自動ラベル付け]** ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-193">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
17. <span data-ttu-id="119c4-194">**[送信]** をクリックしてから、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-194">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="119c4-195">ラベルを作成したら、それを使用するユーザーに発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="119c4-195">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="119c4-196">この場合、ラベルをチーム内のユーザーのみが使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="119c4-196">In this case, we'll make the label available only to people in the team.</span></span>

<span data-ttu-id="119c4-197">秘密度ラベルを発行する</span><span class="sxs-lookup"><span data-stu-id="119c4-197">To publish a sensitivity label</span></span>
1. <span data-ttu-id="119c4-198">Microsoft 365 コンプライアンス センターまたは **[情報保護]** ページで、**[ラベル ポリシー]** タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="119c4-198">In the Microsoft 365 compliance center, on the **Information protection** page, choose the **Label policies** tab.</span></span>
2. <span data-ttu-id="119c4-199">**[ラベルの発行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-199">Click **Publish labels**.</span></span>
3. <span data-ttu-id="119c4-200">**[発行する秘密度ラベルの選択]** ページで、**[発行する秘密度ラベルの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-200">On the **Choose sensitivity labels to publish** page, click **Choose sensitivity labels to publish**.</span></span>
4. <span data-ttu-id="119c4-201">作成したラベルを選択し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-201">Select the label that you created, and then click **Add**.</span></span>
5. <span data-ttu-id="119c4-202">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-202">Click **Next**.</span></span>
6. <span data-ttu-id="119c4-203">[ユーザーとグループに発行] ページで、**[ユーザーとグループの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-203">On the Publish to users and groups page, click **Choose users and groups**.</span></span>
7. <span data-ttu-id="119c4-204">**[追加]** をクリックし、作成したチームを選びます。</span><span class="sxs-lookup"><span data-stu-id="119c4-204">Click **Add**, and then select the team that you created.</span></span>
8. <span data-ttu-id="119c4-205">**[追加]** をクリックし、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-205">Click **Add**, and then click **Done**.</span></span>
9. <span data-ttu-id="119c4-206">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-206">Click **Next**.</span></span>
10. <span data-ttu-id="119c4-207">[ポリシーの設定] ページで、**[ユーザーはラベルを削除するか、分類ラベルを下げるために正当な理由を提供する必要がある]** チェック ボックスをオンにし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-207">On the Policy settings page, select the **Users must provide justification to remove a label or lower classification label** check box, and then click **Next**.</span></span>
11. <span data-ttu-id="119c4-208">ポリシーの名前を入力し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-208">Type a name for the policy, and then click **Next**.</span></span>
12. <span data-ttu-id="119c4-209">**[送信]** をクリックしてから、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-209">Click **Submit** and then click **Done**.</span></span>

## <a name="apply-the-label-to-the-team"></a><span data-ttu-id="119c4-210">チームにラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="119c4-210">Apply the label to the team</span></span>

<span data-ttu-id="119c4-211">ラベルを発行したら、ゲスト共有および管理対象デバイスの設定を有効にするために、ラベルをチームに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="119c4-211">Once the label has been published, you must apply it to the team in order for the guest sharing and managed devices settings to take effect.</span></span> <span data-ttu-id="119c4-212">この操作は SharePoint 管理センターで行います。</span><span class="sxs-lookup"><span data-stu-id="119c4-212">This is done in the SharePoint admin center.</span></span> <span data-ttu-id="119c4-213">発行後にラベルが使用可能になるまでに、しばらく時間がかかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="119c4-213">Note, it may take some time for the label to become available after it's been published.</span></span>

<span data-ttu-id="119c4-214">秘密度ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="119c4-214">To apply the sensitivity label</span></span>
1. <span data-ttu-id="119c4-215">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="119c4-215">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="119c4-216">**[サイト]** で、**[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-216">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="119c4-217">チームに関連付けられているサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-217">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="119c4-218">**[ポリシー]** タブで、**[秘密度]** の下側にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-218">On the **Policies** tab, under **Sensitivity**, click **Edit**.</span></span>
5. <span data-ttu-id="119c4-219">作成したラベルを選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-219">Select the label that you created, and then click **Save**.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="119c4-220">SharePoint の設定</span><span class="sxs-lookup"><span data-stu-id="119c4-220">SharePoint settings</span></span>

<span data-ttu-id="119c4-221">SharePoint では、次の 3 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="119c4-221">There are three steps to do in SharePoint:</span></span>

- <span data-ttu-id="119c4-222">ラベルを作成したときに選択したものと一致するように、SharePoint 管理センターでサイトのゲスト共有設定を更新し、*既存のアクセス権を持つユーザー*に対して、既定の共有リンクを更新します。</span><span class="sxs-lookup"><span data-stu-id="119c4-222">Update the guest sharing settings for the site in the SharePoint admin center to match what you chose when you created the label, and update the default sharing link to *People with existing access*.</span></span>
- <span data-ttu-id="119c4-223">サイト自体の共有設定を更新し、メンバーがファイル、フォルダー、サイトを共有できないようにし、アクセス要求を無効にします。</span><span class="sxs-lookup"><span data-stu-id="119c4-223">Update the site sharing settings in the site itself to prevent members from sharing files, folders, or the site, and turn off access requests.</span></span>
- <span data-ttu-id="119c4-224">閲覧者アクセス許可を持つラベルにユーザーまたはグループを追加した場合は、それらを読み取りアクセス許可を持つ SharePoint サイトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="119c4-224">If you added people or groups to the label with Viewer permissions, you can add them to the SharePoint site with Read permissions.</span></span>

### <a name="sharepoint-guest-settings"></a><span data-ttu-id="119c4-225">SharePoint ゲストの設定</span><span class="sxs-lookup"><span data-stu-id="119c4-225">SharePoint guest settings</span></span>

<span data-ttu-id="119c4-226">ラベルを作成したときに選択したゲスト共有設定 (チーム メンバーシップのみに影響します) は、以下のように関連付けられている SharePoint サイトのゲスト共有設定と一致します。</span><span class="sxs-lookup"><span data-stu-id="119c4-226">The guest sharing setting that you chose when you created the label (which only affects team membership) should match the guest sharing settings for the associated SharePoint site as follows:</span></span>

|<span data-ttu-id="119c4-227">ラベルの設定</span><span class="sxs-lookup"><span data-stu-id="119c4-227">Label setting</span></span>|<span data-ttu-id="119c4-228">SharePoint サイトの設定</span><span class="sxs-lookup"><span data-stu-id="119c4-228">SharePoint site setting</span></span>|
|:------------|:----------------------|
|<span data-ttu-id="119c4-229">**Ofﬁce 365 グループ所有者が組織外のユーザーをグループに追加できるようにする**が選択されている</span><span class="sxs-lookup"><span data-stu-id="119c4-229">**Let Office 365 group owners add people outside the organization to the group** selected</span></span>|<span data-ttu-id="119c4-230">**新規および既存のゲスト** (新規チームの既定値)</span><span class="sxs-lookup"><span data-stu-id="119c4-230">**New and existing guests** (default for new teams)</span></span>|
|<span data-ttu-id="119c4-231">**Ofﬁce 365 グループ所有者が組織外のユーザーをグループに追加できるようにする**が選択されていない</span><span class="sxs-lookup"><span data-stu-id="119c4-231">**Let Office 365 group owners add people outside the organization to the group** not selected</span></span>|<span data-ttu-id="119c4-232">**組織内のユーザーのみ**</span><span class="sxs-lookup"><span data-stu-id="119c4-232">**Only people in your organization**</span></span>|

<span data-ttu-id="119c4-233">また、既定の共有リンクの種類を更新して、意図したよりも広い対象ユーザーにファイルやフォルダーが不用意に共有されるリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="119c4-233">We'll also update the default sharing link type to reduce the risk of accidentally sharing files and folders to a wider audience than intended.</span></span>

<span data-ttu-id="119c4-234">サイトの設定を更新する</span><span class="sxs-lookup"><span data-stu-id="119c4-234">To update site settings</span></span>
1. <span data-ttu-id="119c4-235">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="119c4-235">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="119c4-236">**[サイト]** で、**[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-236">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="119c4-237">チームに関連付けられているサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-237">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="119c4-238">**[ポリシー]** タブで、**[外部共有]** の下側にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-238">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="119c4-239">秘密度ラベルを作成したときにゲスト共有が許可されていた場合は、**[新規および既存のゲスト]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="119c4-239">If you allowed guest sharing when you created the sensitive label, ensure that **New and existing guests** is selected.</span></span> <span data-ttu-id="119c4-240">秘密度ラベルを作成したときにゲスト共有が許可されていなかった場合は、**[組織内のユーザーのみ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="119c4-240">If you didn't allow sharing when you created the label, choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="119c4-241">[既定の共有リンクの種類] で、**[組織レベルの設定と同じ]** チェック ボックスをオフにして、**[既存のアクセス権を持つユーザー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="119c4-241">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="119c4-242">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-242">Click **Save**.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="119c4-243">プライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="119c4-243">Private channels</span></span>

<span data-ttu-id="119c4-244">チームにプライベート チャネルを追加する場合、各プライベート チャネルは、既定の共有設定を使用して新しい SharePoint サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="119c4-244">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="119c4-245">これらのサイトは SharePoint 管理センターでは表示されないので、次のパラメーターと共に [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) PowerShell コマンドレットを使用して、ゲスト共有設定を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="119c4-245">These sites are not visible in the SharePoint admin center, so you must use the [Set-SPOSite](https://docs.microsoft.com/powershell/module/sharepoint-online/set-sposite) PowerShell cmdlet with the following parameters to update the guest sharing settings:</span></span>

- <span data-ttu-id="119c4-246">`-SharingCapability Disabled` ゲスト共有を無効にするには (既定では有効です)</span><span class="sxs-lookup"><span data-stu-id="119c4-246">`-SharingCapability Disabled` to turn off guest sharing (it's on by default)</span></span>
- <span data-ttu-id="119c4-247">`-DefaultSharingLinkType Internal` 既定の共有リンクを*特定のユーザー*に変更するには</span><span class="sxs-lookup"><span data-stu-id="119c4-247">`-DefaultSharingLinkType Internal` to change the default sharing link to *Specific people*</span></span>

<span data-ttu-id="119c4-248">チームでプライベート チャネルを使用する予定がない場合は、[[チーム設定]](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc) の **[メンバーのアクセス許可]** で、チーム メンバーがチームを作成する権限を無効にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="119c4-248">If you don't plan to use private channels with your team, consider turning off the ability for team members to create them under **Member permissions** in [team settings](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc).</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="119c4-249">サイト共有設定</span><span class="sxs-lookup"><span data-stu-id="119c4-249">Site sharing settings</span></span>

<span data-ttu-id="119c4-250">SharePoint サイトがチーム メンバーではないユーザーと共有されないようにするには、SharePoint サイトの共有を所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="119c4-250">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span> <span data-ttu-id="119c4-251">また、ファイルとフォルダーの共有をチームの所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="119c4-251">We also limit sharing of files and folders to team owners.</span></span> <span data-ttu-id="119c4-252">これにより、ファイルがチーム外のユーザーと共有されるたびに所有者が認識できます。</span><span class="sxs-lookup"><span data-stu-id="119c4-252">This helps ensure that owners are aware whenever a file is shared with someone outside the team.</span></span>

<span data-ttu-id="119c4-253">所有者のみのサイト共有を構成する</span><span class="sxs-lookup"><span data-stu-id="119c4-253">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="119c4-254">Teams で、更新するチームの **[全般]** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="119c4-254">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="119c4-255">チームのツール バーで、**[ファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-255">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="119c4-256">省略記号をクリックし、**[SharePoint で開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-256">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="119c4-257">基となる SharePoint サイトのツール バーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-257">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="119c4-258">[サイトの権限] ウィンドウで、**[共有設定]** の **[共有設定の変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-258">In the Site permissions pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
6. <span data-ttu-id="119c4-259">**[共有アクセス許可]** で、**[サイト所有者のみが、ファイル、フォルダー、およびサイトを共有できます]** を選択して、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-259">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

### <a name="custom-site-permissions"></a><span data-ttu-id="119c4-260">カスタム サイトのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="119c4-260">Custom site permissions</span></span>

<span data-ttu-id="119c4-261">閲覧者のアクセス許可を持つユーザーを秘密度ラベルに追加した場合は、それらを読み取りアクセス権を持つ SharePoint サイトに追加し、ファイルに簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="119c4-261">If you added people with Viewer permissions to the sensitivity label, you can add them to the SharePoint site with Read access so they have easy access to the files.</span></span>

<span data-ttu-id="119c4-262">サイトにユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="119c4-262">To add users to the site</span></span>
1. <span data-ttu-id="119c4-263">サイトの設定アイコンをクリックし、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-263">In the site, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="119c4-264">**[ユーザーの招待]** をクリックして、**[サイトのみ共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-264">Click **Invite people**, and then click **Share site only**.</span></span>
3. <span data-ttu-id="119c4-265">招待するユーザーとグループの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="119c4-265">Type the names of the users and groups that you want to invite.</span></span>
4. <span data-ttu-id="119c4-266">追加するユーザーまたはグループごとに、そのアクセス許可を **[編集]** から **[読み取り]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="119c4-266">For each person or group that you add, change their permissions from **Edit** to **Read**.</span></span>
5. <span data-ttu-id="119c4-267">サイトへのリンクを含むメールを送信するかどうかを選びます。</span><span class="sxs-lookup"><span data-stu-id="119c4-267">Choose if you want to send them an email with a link to the site.</span></span>
6. <span data-ttu-id="119c4-268">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="119c4-268">Click **Add**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="119c4-269">追加の保護</span><span class="sxs-lookup"><span data-stu-id="119c4-269">Additional protections</span></span>

<span data-ttu-id="119c4-270">Microsoft 365 は、コンテンツを保護するための追加の方法を提供しています。</span><span class="sxs-lookup"><span data-stu-id="119c4-270">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="119c4-271">次のオプションを使用して、組織のセキュリティを強化することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="119c4-271">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="119c4-272">ゲスト ユーザーを[使用条件](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)に同意させる。</span><span class="sxs-lookup"><span data-stu-id="119c4-272">Have your guest users agree to a [terms of use](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="119c4-273">ゲストに[セッション タイムアウト ポリシー](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)を構成する。</span><span class="sxs-lookup"><span data-stu-id="119c4-273">Configure a [session timeout policy](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="119c4-274">[機密情報の種類](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types)を作成し、[データ損失防止](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)を使用して、機密情報にアクセスするポリシーを設定する。</span><span class="sxs-lookup"><span data-stu-id="119c4-274">Create [sensitive information types](https://docs.microsoft.com/microsoft-365/compliance/custom-sensitive-info-types) and use [data loss protection](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) to set policies around accessing sensitive information.</span></span>
- <span data-ttu-id="119c4-275">[Azure Active Directory アクセス](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) レビューを使用して、チームのアクセス権とメンバーシップを定期的に確認する。</span><span class="sxs-lookup"><span data-stu-id="119c4-275">Use [Azure Active Directory access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) reviews to periodically review team access and membership.</span></span>

## <a name="drive-user-adoption-for-team-members"></a><span data-ttu-id="119c4-276">チーム メンバーのユーザーによる導入を促す</span><span class="sxs-lookup"><span data-stu-id="119c4-276">Drive user adoption for team members</span></span>

<span data-ttu-id="119c4-277">チームを設置したら、このチームの導入とチーム メンバーへの追加のセキュリティを促します。</span><span class="sxs-lookup"><span data-stu-id="119c4-277">With the team in place, it's time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="train-your-users"></a><span data-ttu-id="119c4-278">ユーザーをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="119c4-278">Train your users</span></span>

<span data-ttu-id="119c4-279">チームのメンバーは、チームおよびそのすべてのリソース (チャット、会議、およびその他のアプリなど) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="119c4-279">Members of the team can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="119c4-280">チャネルの [**ファイル**] セクションにあるファイルで作業をする場合、チームのメンバーは、作成したファイルに秘密度ラベルを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="119c4-280">When working with files from the **Files** section of a channel, members of the team should assign the sensitivity label to the files they create.</span></span>

<span data-ttu-id="119c4-281">ラベルがファイルに適用されると、ファイルは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="119c4-281">When the label gets applied to the file, it is encrypted.</span></span> <span data-ttu-id="119c4-282">チームのメンバーは、ファイルを開いてリアルタイムで共同作業を行えます。</span><span class="sxs-lookup"><span data-stu-id="119c4-282">Members of the team can open it and collaborate in real time.</span></span> <span data-ttu-id="119c4-283">ファイルがサイトを離れて悪意のあるユーザーに転送された場合、そのようなユーザーがファイルを開いて内容を表示するには、チーム メンバーのユーザー アカウントの資格情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="119c4-283">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the team to open the file and view its contents.</span></span> 

<span data-ttu-id="119c4-284">チーム メンバーをトレーニングする:</span><span class="sxs-lookup"><span data-stu-id="119c4-284">Train your team members:</span></span>

- <span data-ttu-id="119c4-285">SharePoint サイトのチャット、会議、ファイル、その他のリソースに新しいチームを使用することの重要性と、厳しく規制されたデータのリークによって生じる事態 (法的影響、規制上の罰金、ランサムウェア、競争力の低下など)。</span><span class="sxs-lookup"><span data-stu-id="119c4-285">On the importance of using the new team for chats, meetings, files, and the other resources of the SharePoint site and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="119c4-286">チームにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="119c4-286">How to access the team.</span></span>
- <span data-ttu-id="119c4-287">サイトに新しいファイルを作成し、ローカルに保存された新しいファイルをアップロードする方法。</span><span class="sxs-lookup"><span data-stu-id="119c4-287">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="119c4-288">チームの正しい秘密度ラベルでファイルにラベルを付ける方法。</span><span class="sxs-lookup"><span data-stu-id="119c4-288">How to label files with the correct sensitivity label for the team.</span></span>
- <span data-ttu-id="119c4-289">ファイルがサイトからリークされてもラベルによって保護されるしくみ。</span><span class="sxs-lookup"><span data-stu-id="119c4-289">How the label protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="119c4-290">このトレーニングには、チーム メンバーが上記の機能とその結果を体感できるように、実践的な演習を組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="119c4-290">This training should include hands-on exercises so that your team members can experience these capabilities and their results.</span></span>

### <a name="conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="119c4-291">使用状況を定期的にレビューし、チーム メンバーのフィードバックに対処する</span><span class="sxs-lookup"><span data-stu-id="119c4-291">Conduct periodic reviews of usage and address team member feedback</span></span>

<span data-ttu-id="119c4-292">トレーニング後の数週間、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="119c4-292">In the weeks after training:</span></span>

- <span data-ttu-id="119c4-293">チーム メンバーのフィードバックに迅速に対応し、ポリシーと構成を微調整します。</span><span class="sxs-lookup"><span data-stu-id="119c4-293">Quickly address team member feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="119c4-294">チームの使用状況を分析し、それが期待された使用法と一致しているかを比較する。</span><span class="sxs-lookup"><span data-stu-id="119c4-294">Analyze usage for the team and compare it with usage expectations.</span></span>
- <span data-ttu-id="119c4-295">厳しく規制されたファイルが秘密度ラベルを使用して正しくラベル付けされていることを確認する。</span><span class="sxs-lookup"><span data-stu-id="119c4-295">Verify that highly regulated files have been properly labeled with the sensitivity label.</span></span> <span data-ttu-id="119c4-296">(ラベルが割り当てられているファイルがわかるようにするには、SharePoint のフォルダーを表示し、[**列の追加**] で [**列の表示/非表示**] オプションを使用して [**秘密度**] 列を追加します。)</span><span class="sxs-lookup"><span data-stu-id="119c4-296">(You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="119c4-297">必要に応じて、ユーザーの再トレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="119c4-297">Retrain your users as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="119c4-298">関連項目</span><span class="sxs-lookup"><span data-stu-id="119c4-298">See also</span></span>

[<span data-ttu-id="119c4-299">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="119c4-299">Azure AD Privileged Identity Management</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-configure)