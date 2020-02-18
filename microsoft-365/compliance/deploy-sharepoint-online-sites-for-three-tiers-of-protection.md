---
title: 3 層の保護用に SharePoint Online サイトを展開する
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: '概要: SharePoint Online チーム サイトを作成し、さまざまなレベルの情報保護用に構成します。'
ms.openlocfilehash: 1827c4a19cfd31a236dfbd58e454c610cae14477
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42075531"
---
# <a name="deploy-sharepoint-online-sites-for-three-tiers-of-protection"></a><span data-ttu-id="360c2-103">3 層の保護用に SharePoint Online サイトを展開する</span><span class="sxs-lookup"><span data-stu-id="360c2-103">Deploy SharePoint Online sites for three tiers of protection</span></span>

<span data-ttu-id="360c2-p101">ベースライン、機密、および非常に機密性の高い社外秘の SharePoint Online チーム サイトを設計および展開するには、この記事の手順を実行してください。 これらの 3 層の保護の詳細については、「[Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md)」(SharePoint Online サイトとファイルのセキュリティ保護) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="360c2-p101">Use the steps in this article to design and deploy baseline, sensitive, and highly confidential SharePoint Online team sites. For more information about these three tiers of protection, see [Secure SharePoint Online sites and files](../security/office-365-security/secure-sharepoint-online-sites-and-files.md).</span></span>
  
## <a name="baseline-sharepoint-online-team-sites"></a><span data-ttu-id="360c2-106">ベースラインの SharePoint Online チーム サイト</span><span class="sxs-lookup"><span data-stu-id="360c2-106">Baseline SharePoint Online team sites</span></span>

<span data-ttu-id="360c2-p102">ベースラインの保護には、パブリックおよびプライベートのチーム サイトが含まれます。 パブリック チーム サイトは、組織内の全ユーザーが検出し、アクセスすることができます。 プライベート サイトは、チーム サイトに関連付けられている Office 365 グループのメンバーのみが検出し、アクセスすることができます。 いずれの種類のチーム サイトも、メンバーがサイトを他のユーザーと共有することを許可しています。</span><span class="sxs-lookup"><span data-stu-id="360c2-p102">Baseline protection includes both public and private team sites. Public team sites can be discovered and accessed by anybody in the organization. Private sites can only be discovered and accessed by members of the Office 365 group associated with the team site. Both of these types of team sites allow members to share the site with others.</span></span>
  
### <a name="public"></a><span data-ttu-id="360c2-111">パブリック</span><span class="sxs-lookup"><span data-stu-id="360c2-111">Public</span></span>

<span data-ttu-id="360c2-112">パブリック アクセスとアクセス許可を使用するベースライン SharePoint Online チーム サイトを作成するには、[次の指示](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)に従います。</span><span class="sxs-lookup"><span data-stu-id="360c2-112">To create a baseline SharePoint Online team site with public access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="360c2-113">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="360c2-113">Here is your resulting configuration.</span></span>
  
![パブリック SharePoint Online チーム サイトのベースライン レベルの保護。](../media/bcd46b8d-3f89-4398-80ce-4da17ee85e03.png)
  
### <a name="private"></a><span data-ttu-id="360c2-115">プライベート</span><span class="sxs-lookup"><span data-stu-id="360c2-115">Private</span></span>

<span data-ttu-id="360c2-116">プライベート アクセスとアクセス許可を使用するベースライン SharePoint Online チーム サイトを作成するには、[次の指示](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)に従います。</span><span class="sxs-lookup"><span data-stu-id="360c2-116">To create a baseline SharePoint Online team site with private access and permissions, follow [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>
  
<span data-ttu-id="360c2-117">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="360c2-117">Here is your resulting configuration.</span></span>
  
![プライベート SharePoint Online チーム サイトのベースライン レベルの保護。](../media/91769026-37e3-4383-ac3c-dbf7aca98e41.png)
  
## <a name="sensitive-sharepoint-online-team-sites"></a><span data-ttu-id="360c2-119">機密 SharePoint Online チーム サイト</span><span class="sxs-lookup"><span data-stu-id="360c2-119">Sensitive SharePoint Online team sites</span></span>

<span data-ttu-id="360c2-120">機密 SharePoint Online チーム サイトは、プライベート チーム サイトとして開始します。</span><span class="sxs-lookup"><span data-stu-id="360c2-120">A sensitive SharePoint Online team site starts as a private team site.</span></span>
  
<span data-ttu-id="360c2-121">最初に、[次の指示](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)でプライベート SharePoint Online チーム サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="360c2-121">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="360c2-122">次に、新しい SharePoint Online チーム サイトから、これらの手順で追加のアクセス許可の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="360c2-122">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="360c2-123">SharePoint チーム サイトのツール バーで、設定アイコンをクリックしてから、[**サイトの権限**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="360c2-123">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="360c2-124">[**サイトの権限**] ウィンドウで、[**共有の設定**] の [**共有設定を変更します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="360c2-124">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="360c2-125">**[共有アクセス許可]** で、**[サイト所有者のみが、ファイル、フォルダー、およびサイトを共有できます]** を選択して、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="360c2-125">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>

<span data-ttu-id="360c2-126">これらのアクセス権の設定の結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="360c2-126">The results of these permission settings are:</span></span>

- <span data-ttu-id="360c2-127">メンバーが他のメンバーと共有する機能は無効にされています。</span><span class="sxs-lookup"><span data-stu-id="360c2-127">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="360c2-128">メンバー以外がアクセスを要求する機能は有効にされています。</span><span class="sxs-lookup"><span data-stu-id="360c2-128">The ability for non-members to request access is enabled.</span></span>

<span data-ttu-id="360c2-129">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="360c2-129">Here is your resulting configuration.</span></span>
  
![独立した SharePoint Online チーム サイトの機密レベルの保護。](../media/7a6ab9c6-560a-4674-ac39-8175644dbe6f.png)
  
<span data-ttu-id="360c2-131">サイトのメンバーは、いずれかのアクセス グループのグループ メンバーシップを使用して、サイトのリソースについて安全に共同作業できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="360c2-131">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="highly-confidential-sharepoint-online-team-sites"></a><span data-ttu-id="360c2-132">非常に機密性の高い社外秘 SharePoint Online チーム サイト</span><span class="sxs-lookup"><span data-stu-id="360c2-132">Highly confidential SharePoint Online team sites</span></span>

<span data-ttu-id="360c2-133">機密 SharePoint Online チーム サイトは、追加のアクセス許可の設定を使用するプライベート チーム サイトです。</span><span class="sxs-lookup"><span data-stu-id="360c2-133">A highly confidential SharePoint Online team site is a private team site with additional permissions settings.</span></span>

<span data-ttu-id="360c2-134">最初に、[次の指示](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d)でプライベート SharePoint Online チーム サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="360c2-134">First, create the private SharePoint Online team site with [these instructions](https://support.office.com/article/create-a-team-site-in-sharepoint-ef10c1e7-15f3-42a3-98aa-b5972711777d).</span></span>

<span data-ttu-id="360c2-135">次に、新しい SharePoint Online チーム サイトから、これらの手順で追加のアクセス許可の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="360c2-135">Next, from the new SharePoint Online team site, configure additional permission settings with these steps.</span></span>

1.  <span data-ttu-id="360c2-136">SharePoint チーム サイトのツール バーで、設定アイコンをクリックしてから、[**サイトの権限**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="360c2-136">In the tool bar of the SharePoint team site, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="360c2-137">[**サイトの権限**] ウィンドウで、[**共有の設定**] の [**共有設定を変更します**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="360c2-137">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3.  <span data-ttu-id="360c2-138">[**共有アクセス許可**] で、[**ファイル、フォルダー、およびサイトを共有できるのはサイトの所有者だけです**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="360c2-138">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="360c2-139">[**アクセス要求の許可**] をオフにし、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="360c2-139">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="360c2-140">これらのアクセス権の設定の結果は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="360c2-140">The results of these permission settings are:</span></span>

- <span data-ttu-id="360c2-141">メンバーが他のメンバーと共有する機能は無効にされています。</span><span class="sxs-lookup"><span data-stu-id="360c2-141">The ability for members to share with other members is disabled.</span></span>
- <span data-ttu-id="360c2-142">メンバー以外がアクセスを要求する機能は無効にされています。</span><span class="sxs-lookup"><span data-stu-id="360c2-142">The ability for non-members to request access is disabled.</span></span>

<span data-ttu-id="360c2-143">最終的な構成をここに示します。</span><span class="sxs-lookup"><span data-stu-id="360c2-143">Here is your resulting configuration.</span></span>
  
![独立した SharePoint Online チーム サイトの高機密レベルの保護。](../media/196359ab-d7ed-4fcf-97b4-61820a74aca4.png)
  
<span data-ttu-id="360c2-145">サイトのメンバーは、いずれかのアクセス グループのグループ メンバーシップを使用して、サイトのリソースについて安全に共同作業できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="360c2-145">The members of the site, through group membership in one of the access groups, can now securely collaborate on the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="360c2-146">次の手順</span><span class="sxs-lookup"><span data-stu-id="360c2-146">Next step</span></span>

[<span data-ttu-id="360c2-147">Office 365 ラベルと DLP による SharePoint ファイルの保護</span><span class="sxs-lookup"><span data-stu-id="360c2-147">Protect SharePoint Online files with Office 365 labels and DLP</span></span>](protect-sharepoint-online-files-with-office-365-labels-and-dlp.md)

## <a name="see-also"></a><span data-ttu-id="360c2-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="360c2-148">See also</span></span>

[<span data-ttu-id="360c2-149">選挙運動、非営利組織、およびその他のアジャイル組織のための Microsoft Security ガイダンス</span><span class="sxs-lookup"><span data-stu-id="360c2-149">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](../security/office-365-security/microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)
  
[<span data-ttu-id="360c2-150">クラウド導入およびハイブリッド ソリューション</span><span class="sxs-lookup"><span data-stu-id="360c2-150">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
