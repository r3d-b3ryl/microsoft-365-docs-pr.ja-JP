---
title: セキュリティの分離を使用してチームを構成する
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
ms.openlocfilehash: 7c9b770c712d2468369482ba3a6256e57f621f74
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51042688"
---
# <a name="configure-a-team-with-security-isolation"></a><span data-ttu-id="a5cf8-103">セキュリティの分離を使用してチームを構成する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-103">Configure a team with security isolation</span></span>

<span data-ttu-id="a5cf8-104">この記事では、Microsoft Teams でプライベート チームを構成し、固有の秘密度ラベルを使用してファイルを暗号化して、チーム メンバーのみがファイルを復号化できるようにするための推奨事項と手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-104">This article provides you with recommendations and steps to configure a private team in Microsoft Teams and use a unique sensitivity label to encrypt files so that only team members can decrypt them.</span></span>

<span data-ttu-id="a5cf8-105">この記事では、プライベート アクセスの他にも、チーム チャネルの [**ファイル**] セクションからアクセスできる関連付けられた SharePoint サイトを構成して厳しく規制されたデータの保存で必要な追加のセキュリティを提供する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-105">Beyond the private access, this article describes how to configure the associated SharePoint site, which you can access from the **Files** section of a team channel, for the additional security needed to store highly regulated data.</span></span>

<span data-ttu-id="a5cf8-106">セキュリティの分離を使用するチームの構成における要素は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-106">The elements of configuration for a team with security isolation are:</span></span>

- <span data-ttu-id="a5cf8-107">プライベート チーム</span><span class="sxs-lookup"><span data-stu-id="a5cf8-107">A private team</span></span>
- <span data-ttu-id="a5cf8-108">チームに関連付けられた SharePoint サイトでの以下の追加のセキュリティ:</span><span class="sxs-lookup"><span data-stu-id="a5cf8-108">Additional security on the associated SharePoint site for the team that:</span></span>
  - <span data-ttu-id="a5cf8-109">サイトのメンバーがサイトを他のユーザーと共有することの防止。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-109">Prevents members of the site from sharing the site with others.</span></span>
  - <span data-ttu-id="a5cf8-110">サイトのメンバーではないユーザーがサイトへのアクセス権を要求することの防止。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-110">Prevents non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="a5cf8-111">このチーム専用の秘密度ラベル:</span><span class="sxs-lookup"><span data-stu-id="a5cf8-111">A sensitivity label specifically for this team that:</span></span>
    - <span data-ttu-id="a5cf8-112">非管理対象デバイスから SharePoint コンテンツにアクセスできないようにする</span><span class="sxs-lookup"><span data-stu-id="a5cf8-112">Prevents access to SharePoint content from unmanaged devices</span></span>
    - <span data-ttu-id="a5cf8-113">要求に応じて、チームのゲストアクセスを許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-113">Allows or denies guest access to the team, depending on your requirements</span></span>
    - <span data-ttu-id="a5cf8-114">ラベルを適用するドキュメントを暗号化する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-114">Encrypts documents to which the label is applied</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5cf8-115">この記事の手順に進む前に、「[Microsoft Teams、Office 365 グループ、SharePoint サイトのコンテンツを保護するために秘密度ラベル](../compliance/sensitivity-labels-teams-groups-sites.md)を有効にしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-115">Be sure you have enabled [sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md) before you proceed with the steps in this article.</span></span>

<span data-ttu-id="a5cf8-116">このビデオでは、展開プロセスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-116">Watch this video for an overview of the deployment process.</span></span>
<br>
<br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4mGHf]

<a name="poster"></a> <span data-ttu-id="a5cf8-117">このシナリオを 1 ページにまとめた、「[セキュリティの分離ポスター を使用した Microsoft Teams](../downloads/team-security-isolation-poster.pdf)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-117">For a 1-page summary of this scenario, see the [Microsoft Teams with security isolation poster](../downloads/team-security-isolation-poster.pdf).</span></span>

<span data-ttu-id="a5cf8-118">[![セキュリティの分離ポスター を使用した Microsoft Teams](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)</span><span class="sxs-lookup"><span data-stu-id="a5cf8-118">[![Microsoft Teams with security isolation poster](../media/secure-teams-security-isolation/team-security-isolation-poster.png)](../downloads/team-security-isolation-poster.pdf)</span></span>

<span data-ttu-id="a5cf8-119">このポスターを [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) または [PowerPoint](https://download.microsoft.com/download/8/0/5/8057fc16-c044-40b6-a652-7ed555ba2895/team-security-isolation-poster.pptx) 形式でダウンロードして、レター、リーガル、タブロイド (11 x 17) のサイズの紙に印刷することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-119">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/team-security-isolation-poster.pdf) or [PowerPoint](https://download.microsoft.com/download/8/0/5/8057fc16-c044-40b6-a652-7ed555ba2895/team-security-isolation-poster.pptx) formats and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="a5cf8-120">[これらの手順](team-security-isolation-dev-test.md)を使用して、独自のテスト ラボ環境でこの構成を試してください。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-120">Try this configuration in your own test lab environment with [these instructions](team-security-isolation-dev-test.md).</span></span>

<span data-ttu-id="a5cf8-121">[このケー ススタディ](contoso-team-for-top-secret-project.md)で、Contoso Corporation が独立したプロジェクトでどのように安全なチームを運用したかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-121">See how the Contoso Corporation used an isolated team for a top-secret project in [this case study](contoso-team-for-top-secret-project.md).</span></span>

## <a name="initial-protections"></a><span data-ttu-id="a5cf8-122">初期保護</span><span class="sxs-lookup"><span data-stu-id="a5cf8-122">Initial protections</span></span>

<span data-ttu-id="a5cf8-123">チームおよび基になる SharePoint サイトへのアクセスを保護するためには、次のベスト プラクティスを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-123">To help protect access to the team and its underlying SharePoint site, review the following best practices:</span></span>
- [<span data-ttu-id="a5cf8-124">ID とデバイスのアクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5cf8-124">Identity and device access policies</span></span>](../security/defender-365-security/identity-access-policies.md)
- [<span data-ttu-id="a5cf8-125">SharePoint Online アクセス ポリシー</span><span class="sxs-lookup"><span data-stu-id="a5cf8-125">SharePoint Online access policies</span></span>](../security/defender-365-security/sharepoint-file-access-policies.md)
- [<span data-ttu-id="a5cf8-126">ベースライン保護を使用してチームを展開する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-126">Deploy teams with baseline protection</span></span>](configure-teams-baseline-protection.md)

## <a name="guest-sharing"></a><span data-ttu-id="a5cf8-127">ゲスト共有</span><span class="sxs-lookup"><span data-stu-id="a5cf8-127">Guest sharing</span></span>

<span data-ttu-id="a5cf8-128">会社の性質に応じて、このチームのゲスト共有を有効または無効にする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-128">Depending on the nature of your business, you may or may not want to enable guest sharing for this team.</span></span> <span data-ttu-id="a5cf8-129">チーム内の組織外のユーザーと共同作業する場合は、ゲスト共有を有効にします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-129">If you do plan to collaborate with people outside your organization in the team, enable guest sharing.</span></span> 

<span data-ttu-id="a5cf8-130">ゲストと安全に共有する方法の詳細については、次のリソースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-130">For details about sharing with guests securely, see the following resources:</span></span>

- [<span data-ttu-id="a5cf8-131">組織外のユーザーと共有する場合、ファイルが偶発的に公開されることを制限する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-131">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)
- [<span data-ttu-id="a5cf8-132">セキュリティで保護されたゲスト共有環境を作成する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-132">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

<span data-ttu-id="a5cf8-133">ゲスト共有を許可または禁止するには、関連付けられている SharePoint サイトのチーム レベルとサイト レベルの共有コントロールに対して、秘密度ラベルを組み合わせて使用します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-133">To allow or block guest sharing, we use a combination of a sensitivity label for the team and site-level sharing controls for the associated SharePoint site, both discussed later.</span></span>

## <a name="create-a-private-team"></a><span data-ttu-id="a5cf8-134">プライベート チームを作成する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-134">Create a private team</span></span>

<span data-ttu-id="a5cf8-135">このチーム専用の秘密度ラベルを作成しています。次の手順では、チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-135">Since we are creating a sensitivity label specifically for this team, the next step is to create the team.</span></span> <span data-ttu-id="a5cf8-136">既存のチームがある場合は、それを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-136">If you have an existing team, you can use that.</span></span>

<span data-ttu-id="a5cf8-137">機密情報のチームを作成するには</span><span class="sxs-lookup"><span data-stu-id="a5cf8-137">To create a team for sensitive information</span></span>
1. <span data-ttu-id="a5cf8-138">Teams で、アプリの左側にある **[Teams]** をクリックして、チーム リストの下部にある **[チームに参加またはチームの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-138">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="a5cf8-139">**[チームの作成]** (最初のカード、左上隅) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-139">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="a5cf8-140">**[初めからチームを作成する]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-140">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="a5cf8-141">**[秘密度]**] リストで、既定のままにします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-141">In the **Sensitivity** list, keep the default.</span></span>
5. <span data-ttu-id="a5cf8-142">**[プライバシー]** で、**[プライベート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-142">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="a5cf8-143">機密プロジェクトに関連するチームの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-143">Type a name for the team that is related to your sensitive project.</span></span> <span data-ttu-id="a5cf8-144">たとえば、**Project Saturn**。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-144">For example, **Project Saturn**.</span></span>
7. <span data-ttu-id="a5cf8-145">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-145">Click **Create**.</span></span>
8. <span data-ttu-id="a5cf8-146">チームにユーザーを追加し、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-146">Add users to the team, and then click **Close**.</span></span>

## <a name="private-channel-settings"></a><span data-ttu-id="a5cf8-147">プライベート チャネルの設定</span><span class="sxs-lookup"><span data-stu-id="a5cf8-147">Private channel settings</span></span>

<span data-ttu-id="a5cf8-148">プライベート チャネルの作成権限をチームの所有者に制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-148">We recommend restricting creating private channels to team owners.</span></span>

<span data-ttu-id="a5cf8-149">プライベート チャネルの作成を制限するには</span><span class="sxs-lookup"><span data-stu-id="a5cf8-149">To restrict private channel creation</span></span>
1. <span data-ttu-id="a5cf8-150">チームで、**[その他のオプション]** をクリックしてから、**[チームの管理]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-150">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="a5cf8-151">**[設定]** タブで、**[メンバーのアクセス許可]** を展開します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-151">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="a5cf8-152">**[プライベート チャネルを作成する]** チェック ボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-152">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="a5cf8-153">[チーム ポリシー](/MicrosoftTeams/teams-policies)を使用して、プライベート チャネルを作成できるユーザーを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-153">You can also use [teams policies](/MicrosoftTeams/teams-policies) to control who can create private channels.</span></span>

## <a name="create-a-sensitivity-label"></a><span data-ttu-id="a5cf8-154">秘密度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-154">Create a sensitivity label</span></span>

<span data-ttu-id="a5cf8-155">チームをセキュリティ分離用に構成するには、このチーム専用に作成された秘密度ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-155">To configure a team for security isolation, we'll be using a sensitivity label created specifically for this team.</span></span> <span data-ttu-id="a5cf8-156">このラベルは、ゲスト共有を制御し、非管理対象デバイスからのアクセスを禁止するために、チーム レベルで使用されます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-156">This label is used at the team level to control guest sharing and to block access from unmanaged devices.</span></span> <span data-ttu-id="a5cf8-157">チームの所有者とメンバーだけが開くことができるように、チーム内の個々のファイルを分類および暗号化するために使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-157">It can also be used to classify and encrypt individual files in the team so that only team owners and members can open them.</span></span>

<span data-ttu-id="a5cf8-158">暗号化されたドキュメントを表示できますが、編集することはできない内部のパートナーや関係者のグループがある場合は、閲覧専用のアクセス許可を使用して、ラベルに追加できます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-158">If you have an internal partner or stakeholder group who should be able to view encrypted documents but not edit them, you can add them to the label with view-only permissions.</span></span> <span data-ttu-id="a5cf8-159">閲覧者のアクセス許可を持つチームの SharePoint サイトにこれらのユーザーを追加することができます。また、これらのユーザーには、チーム自体ではなく、ドキュメントが保持されるサイトに対する読み取り専用のアクセス権が与えられます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-159">You can then add these people to the team's SharePoint site with Reader permissions, and they will have read-only access to the site where the documents are kept, but not the team itself.</span></span>


<span data-ttu-id="a5cf8-160">秘密度ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-160">To create a sensitivity label</span></span>
1. <span data-ttu-id="a5cf8-161">[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com)を開きます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-161">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="a5cf8-162">**[ソリューション]** で、**[情報保護]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-162">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="a5cf8-163">**[ラベルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-163">Click **Create a label**.</span></span>
4. <span data-ttu-id="a5cf8-164">ラベルに名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-164">Give the label a name.</span></span> <span data-ttu-id="a5cf8-165">使用するチームにちなんで名前を付けることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-165">We suggest naming it after the team that you'll be using it with.</span></span>
5. <span data-ttu-id="a5cf8-166">表示名と説明を追加し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-166">Add a display name and description, and then click **Next**.</span></span>
6. <span data-ttu-id="a5cf8-167">**Define the scope for this label** (このラベルの範囲の定義) ページで、**[Files & emails]** (ファイルとメール) と **[Groups & sites]** (グループとサイト) を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-167">On the **Define the scope for this label page**, select **Files & emails** and **Groups & sites** and click **Next**.</span></span>
7. <span data-ttu-id="a5cf8-168">**[ファイルとメールの保護設定の選択]** ページで、**[ファイルとメールの暗号化]** を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-168">On the **Choose protection settings for files and emails** page, select **Encrypt files and emails**, and then click **Next**.</span></span>
8. <span data-ttu-id="a5cf8-169">**[暗号化]** ページで、**[暗号化設定を構成する]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-169">On the **Encryption** page, choose **Configure encryption settings**.</span></span>
9. <span data-ttu-id="a5cf8-170">**[ユーザーまたはグループの追加]** をクリックして、作成したチームを選択し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-170">Click **Add users or groups**, select the team that you created, and then click **Add**</span></span>
10. <span data-ttu-id="a5cf8-171">**[アクセス許可の選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-171">Click **Choose permissions**.</span></span>
11. <span data-ttu-id="a5cf8-172">ドロップダウン リストから **[共同編集者]** を選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-172">Choose **Co-Author** from the dropdown list, and then click **Save**.</span></span>
12. <span data-ttu-id="a5cf8-173">ラベルを使用してファイルに読み取り専用アクセス権を持つユーザーまたはグループを含める場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-173">If you want to include users or groups with read-only access to files with the label:</span></span>
    1. <span data-ttu-id="a5cf8-174">**[アクセス許可の割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-174">Click **Assign permissions**.</span></span>
    1. <span data-ttu-id="a5cf8-175">**[ユーザーまたはグループの追加]** をクリックして、追加するユーザーまたはグループを選択し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-175">Click **Add users or groups**, select the users or groups that you want to add, and then click **Add**.</span></span>
    1. <span data-ttu-id="a5cf8-176">**[アクセス許可の選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-176">Click **Choose permissions**.</span></span>
    1. <span data-ttu-id="a5cf8-177">ドロップダウン リストから **[閲覧者]** を選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-177">Choose **Viewer** from the dropdown list, and then click **Save**.</span></span>
13.  <span data-ttu-id="a5cf8-178">**[保存]** をクリックし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-178">Click **Save**, and then click **Next**.</span></span>
14. <span data-ttu-id="a5cf8-179">*[ファイルやメールの自動ラベル付け]* ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-179">On the *Auto-labeling for files and emails*\* page, click **Next**.</span></span>
15. <span data-ttu-id="a5cf8-180">**[Define protection settings for groups and sites]** (グループやサイトの保護の設定の定義) ページで、**[プライバシーと外部ユーザー アクセス設定]** と **[デバイス アクセスと外部共有設定]** を選択し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-180">On the **Define protection settings for groups and sites** page, select **Privacy and external user access settings** and **Device access and external sharing settings** and click **Next**.</span></span>
16. <span data-ttu-id="a5cf8-181">**[Define privacy and external user access settings]** (プライバシーと外部ユーザー アクセス設定の定義) ページの **[プライバシー]** で、**[プライベート]** オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-181">On the **Define privacy and external user access settings** page, under **Privacy**, select the **Private** option.</span></span>
17. <span data-ttu-id="a5cf8-182">ゲスト アクセスを許可する場合は、**[外部ユーザーのアクセス]** で、**[Let Microsoft 365 Group owners add people outside your organization to the group as guests]** (Microsoft 365 グループ所有者が組織外のユーザーをグループに追加できるようにする) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-182">If you want to allow guest access, under **External user access**, select **Let Microsoft 365 Group owners add people outside your organization to the group as guests**.</span></span>
18. <span data-ttu-id="a5cf8-183">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-183">Click **Next**.</span></span>
19. <span data-ttu-id="a5cf8-184">**[Define external sharing and device access settings]** (外部共有とデバイス アクセス設定の定義) ページで、**[Control external sharing from labeled SharePoint sites]** (ラベル付き SharePoint サイトからの外部共有の制御) を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-184">On the **Define external sharing and device access settings** page, select **Control external sharing from labeled SharePoint sites**.</span></span>
20. <span data-ttu-id="a5cf8-185">**[Content can be shared with]** (コンテンツの共有先) で、ゲスト アクセスを許可する場合には **[新規および既存のゲスト]** を選択し、許可しない場合には **[組織内のユーザーのみ]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-185">Under **Content can be shared with**, choose **New and existing guests** if you're allowing guest access or **Only people in your organization** if not.</span></span>
21. <span data-ttu-id="a5cf8-186">**[非管理対象デバイスからのアクセス]** で、**[アクセスをブロックする]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-186">Under **Access from unmanaged devices**, choose **Block access**.</span></span>
22. <span data-ttu-id="a5cf8-187">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-187">Click **Next**.</span></span>
23. <span data-ttu-id="a5cf8-188">**[Auto-labeling for database columns]** (データベースの列の自動ラベル付け) ページで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-188">On the **Auto-labeling for database columns** page, click **Next**.</span></span>
24. <span data-ttu-id="a5cf8-189">**[ラベルの作成]** をクリックし、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-189">Click **Create label**, and then click **Done**.</span></span>

<span data-ttu-id="a5cf8-190">ラベルを作成したら、それを使用するユーザーに発行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-190">Once you've created the label, you need to publish it to the users who will use it.</span></span> <span data-ttu-id="a5cf8-191">この場合、ラベルをチーム内のユーザーのみが使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-191">In this case, we'll make the label available only to people in the team.</span></span>

<span data-ttu-id="a5cf8-192">秘密度ラベルを発行する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-192">To publish a sensitivity label</span></span>
1. <span data-ttu-id="a5cf8-193">Microsoft 365 コンプライアンス センターまたは **[情報保護]** ページで、**[ラベル ポリシー]** タブを選びます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-193">In the Microsoft 365 compliance center, on the **Information protection** page, choose the **Label policies** tab.</span></span>
2. <span data-ttu-id="a5cf8-194">**[ラベルの発行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-194">Click **Publish labels**.</span></span>
3. <span data-ttu-id="a5cf8-195">**[発行する秘密度ラベルの選択]** ページで、**[発行する秘密度ラベルの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-195">On the **Choose sensitivity labels to publish** page, click **Choose sensitivity labels to publish**.</span></span>
4. <span data-ttu-id="a5cf8-196">作成したラベルを選択し、**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-196">Select the label that you created, and then click **Add**.</span></span>
5. <span data-ttu-id="a5cf8-197">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-197">Click **Next**.</span></span>
6. <span data-ttu-id="a5cf8-198">[ユーザーとグループに発行] ページで、**[ユーザーとグループの選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-198">On the Publish to users and groups page, click **Choose users and groups**.</span></span>
7. <span data-ttu-id="a5cf8-199">**[追加]** をクリックし、作成したチームを選びます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-199">Click **Add**, and then select the team that you created.</span></span>
8. <span data-ttu-id="a5cf8-200">**[追加]** をクリックし、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-200">Click **Add**, and then click **Done**.</span></span>
9. <span data-ttu-id="a5cf8-201">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-201">Click **Next**.</span></span>
10. <span data-ttu-id="a5cf8-202">[ポリシーの設定] ページで、**[ユーザーはラベルを削除するか、分類ラベルを下げるために正当な理由を提供する必要がある]** チェック ボックスをオンにし、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-202">On the Policy settings page, select the **Users must provide justification to remove a label or lower classification label** check box, and then click **Next**.</span></span>
11. <span data-ttu-id="a5cf8-203">ポリシーの名前を入力し、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-203">Type a name for the policy, and then click **Next**.</span></span>
12. <span data-ttu-id="a5cf8-204">**[送信]** をクリックしてから、**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-204">Click **Submit** and then click **Done**.</span></span>

## <a name="apply-the-label-to-the-team"></a><span data-ttu-id="a5cf8-205">チームにラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-205">Apply the label to the team</span></span>

<span data-ttu-id="a5cf8-206">ラベルを発行したら、ゲスト共有および管理対象デバイスの設定を有効にするために、ラベルをチームに適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-206">Once the label has been published, you must apply it to the team in order for the guest sharing and managed devices settings to take effect.</span></span> <span data-ttu-id="a5cf8-207">この操作は SharePoint 管理センターで行います。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-207">This is done in the SharePoint admin center.</span></span> <span data-ttu-id="a5cf8-208">発行後にラベルが使用可能になるまでに、しばらく時間がかかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-208">Note, it may take some time for the label to become available after it's been published.</span></span>

<span data-ttu-id="a5cf8-209">秘密度ラベルを適用する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-209">To apply the sensitivity label</span></span>
1. <span data-ttu-id="a5cf8-210">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-210">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="a5cf8-211">**[サイト]** で、**[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-211">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="a5cf8-212">チームに関連付けられているサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-212">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="a5cf8-213">**[ポリシー]** タブで、**[秘密度]** の下側にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-213">On the **Policies** tab, under **Sensitivity**, click **Edit**.</span></span>
5. <span data-ttu-id="a5cf8-214">作成したラベルを選択し、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-214">Select the label that you created, and then click **Save**.</span></span>

## <a name="sharepoint-settings"></a><span data-ttu-id="a5cf8-215">SharePoint の設定</span><span class="sxs-lookup"><span data-stu-id="a5cf8-215">SharePoint settings</span></span>

<span data-ttu-id="a5cf8-216">SharePoint では、次の 3 つの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-216">There are three steps to do in SharePoint:</span></span>

- <span data-ttu-id="a5cf8-217">ラベルを作成したときに選択したものと一致するように、SharePoint 管理センターでサイトのゲスト共有設定を更新し、*既存のアクセス権を持つユーザー* に対して、既定の共有リンクを更新します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-217">Update the guest sharing settings for the site in the SharePoint admin center to match what you chose when you created the label, and update the default sharing link to *People with existing access*.</span></span>
- <span data-ttu-id="a5cf8-218">サイト自体の共有設定を更新し、メンバーがファイル、フォルダー、サイトを共有できないようにし、アクセス要求を無効にします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-218">Update the site sharing settings in the site itself to prevent members from sharing files, folders, or the site, and turn off access requests.</span></span>
- <span data-ttu-id="a5cf8-219">閲覧者アクセス許可を持つラベルにユーザーまたはグループを追加した場合は、それらを読み取りアクセス許可を持つ SharePoint サイトに追加できます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-219">If you added people or groups to the label with Viewer permissions, you can add them to the SharePoint site with Read permissions.</span></span>

### <a name="sharepoint-guest-settings"></a><span data-ttu-id="a5cf8-220">SharePoint ゲストの設定</span><span class="sxs-lookup"><span data-stu-id="a5cf8-220">SharePoint guest settings</span></span>

<span data-ttu-id="a5cf8-221">ラベルを作成したときに選択したゲスト共有設定 (チーム メンバーシップのみに影響します) は、以下のように関連付けられている SharePoint サイトのゲスト共有設定と一致します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-221">The guest sharing setting that you chose when you created the label (which only affects team membership) should match the guest sharing settings for the associated SharePoint site as follows:</span></span>

|<span data-ttu-id="a5cf8-222">ラベルの設定</span><span class="sxs-lookup"><span data-stu-id="a5cf8-222">Label setting</span></span>|<span data-ttu-id="a5cf8-223">SharePoint サイトの設定</span><span class="sxs-lookup"><span data-stu-id="a5cf8-223">SharePoint site setting</span></span>|
|:------------|:----------------------|
|<span data-ttu-id="a5cf8-224">**Ofﬁce 365 グループ所有者が組織外のユーザーをグループに追加できるようにする** が選択されている</span><span class="sxs-lookup"><span data-stu-id="a5cf8-224">**Let Office 365 group owners add people outside the organization to the group** selected</span></span>|<span data-ttu-id="a5cf8-225">**新規および既存のゲスト** (新規チームの既定値)</span><span class="sxs-lookup"><span data-stu-id="a5cf8-225">**New and existing guests** (default for new teams)</span></span>|
|<span data-ttu-id="a5cf8-226">**Ofﬁce 365 グループ所有者が組織外のユーザーをグループに追加できるようにする** が選択されていない</span><span class="sxs-lookup"><span data-stu-id="a5cf8-226">**Let Office 365 group owners add people outside the organization to the group** not selected</span></span>|<span data-ttu-id="a5cf8-227">**組織内のユーザーのみ**</span><span class="sxs-lookup"><span data-stu-id="a5cf8-227">**Only people in your organization**</span></span>|

<span data-ttu-id="a5cf8-228">また、既定の共有リンクの種類を更新して、意図したよりも広い対象ユーザーにファイルやフォルダーが不用意に共有されるリスクを軽減します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-228">We'll also update the default sharing link type to reduce the risk of accidentally sharing files and folders to a wider audience than intended.</span></span>

<span data-ttu-id="a5cf8-229">サイトの設定を更新する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-229">To update site settings</span></span>
1. <span data-ttu-id="a5cf8-230">[SharePoint 管理センター](https://admin.microsoft.com/sharepoint)を開きます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-230">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="a5cf8-231">**[サイト]** で、**[アクティブなサイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-231">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="a5cf8-232">チームに関連付けられているサイトをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-232">Click the site that is associated with team.</span></span>
4. <span data-ttu-id="a5cf8-233">**[ポリシー]** タブで、**[外部共有]** の下側にある **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-233">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="a5cf8-234">秘密度ラベルを作成したときにゲスト共有が許可されていた場合は、**[新規および既存のゲスト]** が選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-234">If you allowed guest sharing when you created the sensitive label, ensure that **New and existing guests** is selected.</span></span> <span data-ttu-id="a5cf8-235">秘密度ラベルを作成したときにゲスト共有が許可されていなかった場合は、**[組織内のユーザーのみ]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-235">If you didn't allow sharing when you created the label, choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="a5cf8-236">[既定の共有リンクの種類] で、**[組織レベルの設定と同じ]** チェック ボックスをオフにして、**[既存のアクセス権を持つユーザー]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-236">Under Default sharing link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="a5cf8-237">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-237">Click **Save**.</span></span>

#### <a name="private-channels"></a><span data-ttu-id="a5cf8-238">プライベート チャネル</span><span class="sxs-lookup"><span data-stu-id="a5cf8-238">Private channels</span></span>

<span data-ttu-id="a5cf8-239">チームにプライベート チャネルを追加する場合、各プライベート チャネルは、既定の共有設定を使用して新しい SharePoint サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-239">If you add private channels to the team, each private channel creates a new SharePoint site with the default sharing settings.</span></span> <span data-ttu-id="a5cf8-240">これらのサイトは SharePoint 管理センターでは表示されないので、次のパラメーターと共に [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) PowerShell コマンドレットを使用して、ゲスト共有設定を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-240">These sites are not visible in the SharePoint admin center, so you must use the [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) PowerShell cmdlet with the following parameters to update the guest sharing settings:</span></span>

- <span data-ttu-id="a5cf8-241">`-SharingCapability Disabled` ゲスト共有を無効にするには (既定では有効です)</span><span class="sxs-lookup"><span data-stu-id="a5cf8-241">`-SharingCapability Disabled` to turn off guest sharing (it's on by default)</span></span>
- <span data-ttu-id="a5cf8-242">`-DefaultSharingLinkType Internal` 既定の共有リンクを *特定のユーザー* に変更するには</span><span class="sxs-lookup"><span data-stu-id="a5cf8-242">`-DefaultSharingLinkType Internal` to change the default sharing link to *Specific people*</span></span>

<span data-ttu-id="a5cf8-243">チームでプライベート チャネルを使用する予定がない場合は、[[チーム設定]](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc) の **[メンバーのアクセス許可]** で、チーム メンバーがチームを作成する権限を無効にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-243">If you don't plan to use private channels with your team, consider turning off the ability for team members to create them under **Member permissions** in [team settings](https://support.microsoft.com/office/ce053b04-1b8e-4796-baa8-90dc427b3acc).</span></span>

### <a name="site-sharing-settings"></a><span data-ttu-id="a5cf8-244">サイト共有設定</span><span class="sxs-lookup"><span data-stu-id="a5cf8-244">Site sharing settings</span></span>

<span data-ttu-id="a5cf8-245">SharePoint サイトがチーム メンバーではないユーザーと共有されないようにするには、SharePoint サイトの共有を所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-245">To help ensure that the SharePoint site does not get shared with people who are not members of the team, we limit such sharing to owners.</span></span> <span data-ttu-id="a5cf8-246">また、ファイルとフォルダーの共有をチームの所有者に制限します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-246">We also limit sharing of files and folders to team owners.</span></span> <span data-ttu-id="a5cf8-247">これにより、ファイルがチーム外のユーザーと共有されるたびに所有者が認識できます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-247">This helps ensure that owners are aware whenever a file is shared with someone outside the team.</span></span>

<span data-ttu-id="a5cf8-248">所有者のみのサイト共有を構成する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-248">To configure owners-only site sharing</span></span>
1. <span data-ttu-id="a5cf8-249">Teams で、更新するチームの **[全般]** タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-249">In Teams, navigate to the **General** tab of the team you want to update.</span></span>
2. <span data-ttu-id="a5cf8-250">チームのツール バーで、**[ファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-250">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="a5cf8-251">省略記号をクリックし、**[SharePoint で開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-251">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="a5cf8-252">基となる SharePoint サイトのツール バーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-252">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="a5cf8-253">[サイトの権限] ウィンドウで、**[共有設定]** の **[共有設定の変更]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-253">In the Site permissions pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
6. <span data-ttu-id="a5cf8-254">**[共有アクセス許可]** で、**[サイト所有者のみが、ファイル、フォルダー、およびサイトを共有できます]** を選択して、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-254">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

### <a name="custom-site-permissions"></a><span data-ttu-id="a5cf8-255">カスタム サイトのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="a5cf8-255">Custom site permissions</span></span>

<span data-ttu-id="a5cf8-256">閲覧者のアクセス許可を持つユーザーを秘密度ラベルに追加した場合は、それらを読み取りアクセス権を持つ SharePoint サイトに追加し、ファイルに簡単にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-256">If you added people with Viewer permissions to the sensitivity label, you can add them to the SharePoint site with Read access so they have easy access to the files.</span></span>

<span data-ttu-id="a5cf8-257">サイトにユーザーを追加する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-257">To add users to the site</span></span>
1. <span data-ttu-id="a5cf8-258">サイトの設定アイコンをクリックし、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-258">In the site, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="a5cf8-259">**[ユーザーの招待]** をクリックして、**[サイトのみ共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-259">Click **Invite people**, and then click **Share site only**.</span></span>
3. <span data-ttu-id="a5cf8-260">招待するユーザーとグループの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-260">Type the names of the users and groups that you want to invite.</span></span>
4. <span data-ttu-id="a5cf8-261">追加するユーザーまたはグループごとに、そのアクセス許可を **[編集]** から **[読み取り]** に変更します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-261">For each person or group that you add, change their permissions from **Edit** to **Read**.</span></span>
5. <span data-ttu-id="a5cf8-262">サイトへのリンクを含むメールを送信するかどうかを選びます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-262">Choose if you want to send them an email with a link to the site.</span></span>
6. <span data-ttu-id="a5cf8-263">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-263">Click **Add**.</span></span>

## <a name="additional-protections"></a><span data-ttu-id="a5cf8-264">追加の保護</span><span class="sxs-lookup"><span data-stu-id="a5cf8-264">Additional protections</span></span>

<span data-ttu-id="a5cf8-265">Microsoft 365 は、コンテンツを保護するための追加の方法を提供しています。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-265">Microsoft 365 offers additional methods for securing your content.</span></span> <span data-ttu-id="a5cf8-266">次のオプションを使用して、組織のセキュリティを強化することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-266">Consider if the following options would help improve security for your organization.</span></span>

- <span data-ttu-id="a5cf8-267">ゲストを[使用条件](/azure/active-directory/conditional-access/terms-of-use)に同意させる。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-267">Have your guests agree to a [terms of use](/azure/active-directory/conditional-access/terms-of-use).</span></span>
- <span data-ttu-id="a5cf8-268">ゲストに[セッション タイムアウト ポリシー](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime)を構成する。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-268">Configure a [session timeout policy](/azure/active-directory/conditional-access/howto-conditional-access-session-lifetime) for guests.</span></span>
- <span data-ttu-id="a5cf8-269">[機密情報の種類](../compliance/sensitive-information-type-learn-about.md)を作成し、[データ損失防止](../compliance/data-loss-prevention-policies.md)を使用して、機密情報にアクセスするポリシーを設定する。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-269">Create [sensitive information types](../compliance/sensitive-information-type-learn-about.md) and use [data loss protection](../compliance/data-loss-prevention-policies.md) to set policies around accessing sensitive information.</span></span>
- <span data-ttu-id="a5cf8-270">[Azure Active Directory アクセス](/azure/active-directory/governance/access-reviews-overview) レビューを使用して、チームのアクセス権とメンバーシップを定期的に確認する。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-270">Use [Azure Active Directory access](/azure/active-directory/governance/access-reviews-overview) reviews to periodically review team access and membership.</span></span>

## <a name="drive-user-adoption-for-team-members"></a><span data-ttu-id="a5cf8-271">チーム メンバーのユーザーによる導入を促す</span><span class="sxs-lookup"><span data-stu-id="a5cf8-271">Drive user adoption for team members</span></span>

<span data-ttu-id="a5cf8-272">チームを設置したら、このチームの導入とチーム メンバーへの追加のセキュリティを促します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-272">With the team in place, it's time to drive the adoption of this team and its additional security to team members.</span></span>

### <a name="train-your-users"></a><span data-ttu-id="a5cf8-273">ユーザーをトレーニングする</span><span class="sxs-lookup"><span data-stu-id="a5cf8-273">Train your users</span></span>

<span data-ttu-id="a5cf8-274">チームのメンバーは、チームおよびそのすべてのリソース (チャット、会議、およびその他のアプリなど) にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-274">Members of the team can access the team and all of its resources, including chats, meetings, and other apps.</span></span> <span data-ttu-id="a5cf8-275">チャネルの [**ファイル**] セクションにあるファイルで作業をする場合、チームのメンバーは、作成したファイルに秘密度ラベルを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-275">When working with files from the **Files** section of a channel, members of the team should assign the sensitivity label to the files they create.</span></span>

<span data-ttu-id="a5cf8-276">ラベルがファイルに適用されると、ファイルは暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-276">When the label gets applied to the file, it is encrypted.</span></span> <span data-ttu-id="a5cf8-277">チームのメンバーは、ファイルを開いてリアルタイムで共同作業を行えます。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-277">Members of the team can open it and collaborate in real time.</span></span> <span data-ttu-id="a5cf8-278">ファイルがサイトを離れて悪意のあるユーザーに転送された場合、そのようなユーザーがファイルを開いて内容を表示するには、チーム メンバーのユーザー アカウントの資格情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-278">If the file leaves the site and gets forwarded to a malicious user, they will have to supply credentials of a user account that is member of the team to open the file and view its contents.</span></span> 

<span data-ttu-id="a5cf8-279">チーム メンバーをトレーニングする:</span><span class="sxs-lookup"><span data-stu-id="a5cf8-279">Train your team members:</span></span>

- <span data-ttu-id="a5cf8-280">SharePoint サイトのチャット、会議、ファイル、その他のリソースに新しいチームを使用することの重要性と、厳しく規制されたデータのリークによって生じる事態 (法的影響、規制上の罰金、ランサムウェア、競争力の低下など)。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-280">On the importance of using the new team for chats, meetings, files, and the other resources of the SharePoint site and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="a5cf8-281">チームにアクセスする方法</span><span class="sxs-lookup"><span data-stu-id="a5cf8-281">How to access the team.</span></span>
- <span data-ttu-id="a5cf8-282">サイトに新しいファイルを作成し、ローカルに保存された新しいファイルをアップロードする方法。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-282">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="a5cf8-283">チームの正しい秘密度ラベルでファイルにラベルを付ける方法。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-283">How to label files with the correct sensitivity label for the team.</span></span>
- <span data-ttu-id="a5cf8-284">ファイルがサイトからリークされてもラベルによって保護されるしくみ。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-284">How the label protects files even when they are leaked off the site.</span></span>

<span data-ttu-id="a5cf8-285">このトレーニングには、チーム メンバーが上記の機能とその結果を体感できるように、実践的な演習を組み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-285">This training should include hands-on exercises so that your team members can experience these capabilities and their results.</span></span>

### <a name="conduct-periodic-reviews-of-usage-and-address-team-member-feedback"></a><span data-ttu-id="a5cf8-286">使用状況を定期的にレビューし、チーム メンバーのフィードバックに対処する</span><span class="sxs-lookup"><span data-stu-id="a5cf8-286">Conduct periodic reviews of usage and address team member feedback</span></span>

<span data-ttu-id="a5cf8-287">トレーニング後の数週間、次のことを行います。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-287">In the weeks after training:</span></span>

- <span data-ttu-id="a5cf8-288">チーム メンバーのフィードバックに迅速に対応し、ポリシーと構成を微調整します。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-288">Quickly address team member feedback and fine tune polices and configurations.</span></span>
- <span data-ttu-id="a5cf8-289">チームの使用状況を分析し、それが期待された使用法と一致しているかを比較する。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-289">Analyze usage for the team and compare it with usage expectations.</span></span>
- <span data-ttu-id="a5cf8-290">厳しく規制されたファイルが秘密度ラベルを使用して正しくラベル付けされていることを確認する。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-290">Verify that highly regulated files have been properly labeled with the sensitivity label.</span></span> <span data-ttu-id="a5cf8-291">(ラベルが割り当てられているファイルがわかるようにするには、SharePoint のフォルダーを表示し、[**列の追加**] で [**列の表示/非表示**] オプションを使用して [**秘密度**] 列を追加します。)</span><span class="sxs-lookup"><span data-stu-id="a5cf8-291">(You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>

<span data-ttu-id="a5cf8-292">必要に応じて、ユーザーの再トレーニングを行います。</span><span class="sxs-lookup"><span data-stu-id="a5cf8-292">Retrain your users as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5cf8-293">関連項目</span><span class="sxs-lookup"><span data-stu-id="a5cf8-293">See also</span></span>

[<span data-ttu-id="a5cf8-294">Azure AD Privileged Identity Management</span><span class="sxs-lookup"><span data-stu-id="a5cf8-294">Azure AD Privileged Identity Management</span></span>](/azure/active-directory/privileged-identity-management/pim-configure)