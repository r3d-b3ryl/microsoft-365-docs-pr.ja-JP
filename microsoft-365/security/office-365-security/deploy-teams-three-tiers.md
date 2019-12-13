---
title: ファイルの 3 層の保護用にチームを展開する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: Microsoft Teams でチームを作成し、さまざまなレベルのファイルの情報保護用に構成します。
ms.openlocfilehash: 3b90a1b084f7cd7e56d1d6448d74a7d2c2469a4d
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971825"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a><span data-ttu-id="fcf92-103">ファイルの 3 層の保護用にチームを展開する</span><span class="sxs-lookup"><span data-stu-id="fcf92-103">Deploy teams for three tiers of protection for files</span></span>

<span data-ttu-id="fcf92-104">この記事にある手順を使用して、ベースライン、機密、高機密のチームを設計し、展開します。</span><span class="sxs-lookup"><span data-stu-id="fcf92-104">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential teams.</span></span> <span data-ttu-id="fcf92-105">この 3 層の保護の詳細については、「[Microsoft Teams のファイルを保護する](secure-files-in-teams.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fcf92-105">For more information about these three tiers of protection, see [Secure files in Microsoft Teams](secure-files-in-teams.md).</span></span>

## <a name="baseline-teams"></a><span data-ttu-id="fcf92-106">ベースライン チーム</span><span class="sxs-lookup"><span data-stu-id="fcf92-106">Baseline teams</span></span>

<span data-ttu-id="fcf92-107">ベースライン保護には、パブリックとプライベートの両方のチームが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fcf92-107">Baseline protection includes both public and private teams.</span></span> <span data-ttu-id="fcf92-108">パブリック チームは、組織内のだれでも検出およびアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fcf92-108">Public teams can be discovered and accessed by anybody in the organization.</span></span> <span data-ttu-id="fcf92-109">プライベート サイトは、チームと関連付けられた Office 365 グループのメンバーのみが検出とアクセスを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fcf92-109">Private sites can only be discovered and accessed by members of the Office 365 group associated with the team.</span></span> <span data-ttu-id="fcf92-110">これらのどちらの種類のチームでも、メンバーは他のユーザーとサイトを共有できます。</span><span class="sxs-lookup"><span data-stu-id="fcf92-110">Both of these types of teams allow members to share the site with others.</span></span>

### <a name="public"></a><span data-ttu-id="fcf92-111">パブリック</span><span class="sxs-lookup"><span data-stu-id="fcf92-111">Public</span></span>

<span data-ttu-id="fcf92-112">[この記事](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)の手順を実行して、パブリック アクセスとアクセス許可を使用するベースライン チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="fcf92-112">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline team with public access and permissions.</span></span>

<span data-ttu-id="fcf92-113">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="fcf92-113">Here is your resulting configuration.</span></span>

![パブリック チームのベースライン レベルの保護。](../media/baseline-public-team.png)

### <a name="private"></a><span data-ttu-id="fcf92-115">プライベート</span><span class="sxs-lookup"><span data-stu-id="fcf92-115">Private</span></span>

<span data-ttu-id="fcf92-116">[この記事](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)の手順を実行して、プライベート アクセスとアクセス許可を使用するベースライン チームを作成します。</span><span class="sxs-lookup"><span data-stu-id="fcf92-116">Follow the instructions in [this article](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) to create a baseline team with private access and permissions.</span></span>

<span data-ttu-id="fcf92-117">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="fcf92-117">Here is your resulting configuration.</span></span>

![プライベート チーム サイトのベースライン レベルの保護。](../media/baseline-private-team.png)

## <a name="sensitive-teams"></a><span data-ttu-id="fcf92-119">機密性の高いチーム</span><span class="sxs-lookup"><span data-stu-id="fcf92-119">Sensitive teams</span></span>

<span data-ttu-id="fcf92-120">機密性の高いチームの場合は、まず、[プライベート チームを作成](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)します。</span><span class="sxs-lookup"><span data-stu-id="fcf92-120">For a sensitive team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="fcf92-121">次に、基となる SharePoint サイトを構成して、チーム メンバーによる共有を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="fcf92-121">Next, you configure the underlying SharePoint site to prevent sharing by team members.</span></span>

1. <span data-ttu-id="fcf92-122">チームのツール バーで、**[ファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcf92-122">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="fcf92-123">省略記号をクリックし、**[SharePoint で開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcf92-123">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="fcf92-124">基となる SharePoint サイトのツール バーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcf92-124">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="fcf92-125">**[サイトの権限]** ウィンドウで、**[共有の設定]** の **[共有設定を変更します]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcf92-125">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="fcf92-126">**[共有アクセス許可]** で、**[サイト所有者のみが、ファイル、フォルダー、およびサイトを共有できます]** を選択して、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcf92-126">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="fcf92-127">結果の構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fcf92-127">Here is your resulting configuration.</span></span>

![チームの機密の保護。](../media/sensitive-team.png)

## <a name="highly-confidential-teams"></a><span data-ttu-id="fcf92-129">非常に機密性の高いチーム。</span><span class="sxs-lookup"><span data-stu-id="fcf92-129">Highly confidential teams</span></span>

<span data-ttu-id="fcf92-130">非常に機密性の高いチームの場合は、まず、[プライベート チームを作成](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b)します。</span><span class="sxs-lookup"><span data-stu-id="fcf92-130">With a highly confidential team, you start by [creating a private team](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).</span></span>

<span data-ttu-id="fcf92-131">次に、基となる SharePoint サイトを構成して、チーム メンバーによる共有とチーム メンバー以外からのアクセス要求を防ぎます。</span><span class="sxs-lookup"><span data-stu-id="fcf92-131">Next, you configure the underlying SharePoint site to prevent sharing by team members and the requesting of access by non-members of the team.</span></span>

1. <span data-ttu-id="fcf92-132">チームのツール バーで、**[ファイル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcf92-132">In the tool bar for the team, click **Files**.</span></span>

2. <span data-ttu-id="fcf92-133">省略記号をクリックし、**[SharePoint で開く]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcf92-133">Click the ellipsis, and then click **Open in SharePoint**.</span></span>

3. <span data-ttu-id="fcf92-134">基となる SharePoint サイトのツール バーで、設定アイコンをクリックしてから、**[サイトの権限]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcf92-134">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>

4. <span data-ttu-id="fcf92-135">[**サイトの権限**] ウィンドウで、[**共有の設定**] の [**共有設定を変更します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcf92-135">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>

5. <span data-ttu-id="fcf92-136">[**共有アクセス許可**] で、[**ファイル、フォルダー、およびサイトを共有できるのはサイトの所有者だけです**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fcf92-136">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>

6. <span data-ttu-id="fcf92-137">[**アクセス要求の許可**] をオフにし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fcf92-137">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="fcf92-138">結果の構成は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="fcf92-138">Here is your resulting configuration.</span></span>

![チームの非常に機密性の高い社外秘の保護。](../media/highly-confidential-team.png)

## <a name="next-step"></a><span data-ttu-id="fcf92-140">次の手順</span><span class="sxs-lookup"><span data-stu-id="fcf92-140">Next step</span></span>

[<span data-ttu-id="fcf92-141">保持ラベルと DLP を使用してチーム内のファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="fcf92-141">Protect files in teams with retention labels and DLP</span></span>](deploy-teams-retention-DLP.md)

## <a name="see-also"></a><span data-ttu-id="fcf92-142">関連項目</span><span class="sxs-lookup"><span data-stu-id="fcf92-142">See also</span></span>

[<span data-ttu-id="fcf92-143">Microsoft Teams のファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="fcf92-143">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)

[<span data-ttu-id="fcf92-144">クラウド導入およびハイブリッド ソリューション</span><span class="sxs-lookup"><span data-stu-id="fcf92-144">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
