---
title: 高度な電子情報開示ケースに保管担当者を追加する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: fc8002d900c38dee1b8487bbc0167b956f63b97f
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/25/2019
ms.locfileid: "39257055"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="4c72f-102">高度な電子情報開示ケースに保管担当者を追加する</span><span class="sxs-lookup"><span data-stu-id="4c72f-102">Add custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="4c72f-103">Advanced 電子情報開示の組み込みの保管担当者管理ツールを使用して、保管担当者の管理に関するワークフローを調整し、ケースに関連付けられている関連する custodial データソースを特定します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-103">Use the built-in custodian management tool in Advanced eDiscovery to coordinate your workflows around managing custodians and identifying relevant, custodial data sources associated with a case.</span></span> <span data-ttu-id="4c72f-104">保管担当者を追加すると、システムは自動的に Exchange メールボックスと OneDrive for Business アカウントを自動的に識別して保持することができます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-104">When you add a custodian, the system can automatically identify and place a hold on their Exchange mailbox and OneDrive for Business account.</span></span> <span data-ttu-id="4c72f-105">調査の検出プロセスでは、保管担当者がアクセスまたは投稿されたその他のデータソース (メールボックス、サイト、チームなど) を特定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-105">During the discovery process of your investigation, you might also identify additional data sources (such as mailboxes, sites, or Teams) that a custodian accessed or contributed to.</span></span> <span data-ttu-id="4c72f-106">このような状況では、保管担当者管理ツールを使用して、これらのデータソースを特定の保管担当者に関連付けることができます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-106">In this situation, you can use the custodian management tool to associate those data sources will a specific custodian.</span></span> <span data-ttu-id="4c72f-107">保管担当者をケースに追加して、その他のデータソースをそのケースに関連付けると、データをすばやく保持して、custodial データを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-107">After you add custodians to a case and associate other data source with them, you can quickly preserve data and search the custodial data.</span></span>

<span data-ttu-id="4c72f-108">次のワークフローを使用して、高度な電子情報開示ケースで保管担当者を追加して管理します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-108">Use the following workflow to add and manage custodians in Advanced eDiscovery cases.</span></span> 

![[保管担当者の管理] タブ](media/CustodianMgtPage.png)

## <a name="before-you-begin"></a><span data-ttu-id="4c72f-110">始める前に</span><span class="sxs-lookup"><span data-stu-id="4c72f-110">Before you begin</span></span>

<span data-ttu-id="4c72f-111">ケースに保管担当者を追加するには、電子情報開示マネージャーの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c72f-111">To add custodians to a case, you must be a member of the eDiscovery Manager role group.</span></span> <span data-ttu-id="4c72f-112">これにより、ケースに保管担当者を追加し、custodial データソースにホールドを配置するために必要なアクセス許可が提供されます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-112">This will provide you with the necessary permissions to add custodians to a case and place a hold on the custodial data sources.</span></span>


## <a name="step-1-add-potential-custodians"></a><span data-ttu-id="4c72f-113">手順 1: 潜在的な保管担当者を追加する</span><span class="sxs-lookup"><span data-stu-id="4c72f-113">Step 1: Add potential custodians</span></span>

<span data-ttu-id="4c72f-114">最初の手順として、保管担当者を識別し、ケースに追加します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-114">The first step is to identify and add custodians to the case.</span></span>

1. <span data-ttu-id="4c72f-115">[ **Advanced eDiscovery**ホーム] ページで、保管担当者を追加するケースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c72f-115">On the **Advanced eDiscovery** home page, click the case that you want to add custodians to.</span></span> 
 
2. <span data-ttu-id="4c72f-116">[**保管担当者**] タブをクリックし、[ **+ Add 保管担当者**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c72f-116">Click the **Custodians** tab and then click **+ Add custodians**.</span></span>

3. <span data-ttu-id="4c72f-117">ケースに追加する保管担当者を見つけます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-117">Find the custodians to add  to the case.</span></span> <span data-ttu-id="4c72f-118">ユーザー名の最初の部分を入力して、組織の Azure Active Directory のユーザーを表示します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-118">Type the first part of a person's name to display users from your organization's Azure Active Directory.</span></span> <span data-ttu-id="4c72f-119">適切な人物が見つかったら、その名前をクリックして一覧に追加します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-119">When you find the correct person, click their name to add them to the list.</span></span>

   ![潜在的な保管担当者を特定する](media/AddCustodianStep1.png)
 
4. <span data-ttu-id="4c72f-121">関連するすべての保管担当者を追加した後、[**次**へ] をクリックして、保管担当者のプライマリデータソースを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-121">After added all the relevant custodians, click **Next** to select the custodians' primary data sources.</span></span>
  
## <a name="step-2-select-custodian-data-sources"></a><span data-ttu-id="4c72f-122">手順 2: 保管担当者データソースを選択する</span><span class="sxs-lookup"><span data-stu-id="4c72f-122">Step 2: Select custodian data sources</span></span>

<span data-ttu-id="4c72f-123">保管担当者を追加した後、保管担当者ツールを使用すると、各保管担当者が所有するプライマリデータソースを識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-123">After adding custodians, the custodian tool will help you identify the primary data sources owned by each custodian.</span></span> <span data-ttu-id="4c72f-124">これらのデータの場所は、保管担当者の Exchange メールボックスおよび OneDrive アカウントです。</span><span class="sxs-lookup"><span data-stu-id="4c72f-124">These data locations are the custodian's Exchange mailbox and OneDrive account.</span></span> 

<span data-ttu-id="4c72f-125">保管担当者データソースを識別するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="4c72f-125">To identify custodian data sources:</span></span> 

1. <span data-ttu-id="4c72f-126">すべての保管担当者の Exchange メールボックスを選択するには、列の上部にある [ **exchange** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4c72f-126">To select the Exchange mailbox for all custodians, select the **Exchange** check box at the top of the column.</span></span> <span data-ttu-id="4c72f-127">その後、特定の保管担当者のチェックボックスをオフにして、メールボックスを custodial の場所として削除することができます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-127">You can then clear the check box for any specific custodian to remove a mailbox as a custodial location.</span></span> <span data-ttu-id="4c72f-128">または、列の選択が解除された状態で**Exchange**チェックボックスをオンのままにして、個々の保管担当者のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4c72f-128">Alternatively, you can leave the **Exchange** check box at the top of the column unselected and then select the check box for individual custodians.</span></span> 
 
   ![Custodial データソースの選択](media/AddCustodianStep2.png)
 
2. <span data-ttu-id="4c72f-130">保管担当者の OneDrive アカウントに対して同じことを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-130">Repeat the same thing for the custodians' OneDrive accounts.</span></span> 

    <span data-ttu-id="4c72f-131">保管担当者データソースを選択すると、システムは自動的にこれらのデータソースを識別して確認し、それを保管担当者に関連付けられたデータソースとしてケースに追加します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-131">After you select the custodian data sources, the system automatically attempts to identify and verify these data sources, and then adds them to the case as data sources associated with the custodians.</span></span>
 
4. <span data-ttu-id="4c72f-132">[**次**へ] をクリックして、追加のデータソースの保管担当者への関連付けを開始します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-132">Click **Next** to begin associating additional data sources to the custodians in the case.</span></span>

## <a name="step-3-associate-additional-data-sources-to-a-custodian"></a><span data-ttu-id="4c72f-133">手順 3: 追加のデータソースを保管担当者に関連付ける</span><span class="sxs-lookup"><span data-stu-id="4c72f-133">Step 3: Associate additional data sources to a custodian</span></span>

<span data-ttu-id="4c72f-134">調査しているケースによっては、特定の保管担当者がアクセスしている可能性のあるメールボックス、保管担当者が現在メンバーになっている Office 365 グループ、または保管担当者によってアクセスされたサイトも検索 (保持) する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c72f-134">Depending on the case you're investigating, you may also need to search (and preserve content in) mailboxes that a specific custodian may have accessed, Office 365 groups that a custodian is currently a member of, or sites that a custodian has also accessed.</span></span> <span data-ttu-id="4c72f-135">そのため、前の手順で指定したプライマリ保管担当者データソースに加えて、追加の Office 365 データソースを保管担当者に関連付けることもできます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-135">So in addition to the primary custodian data sources that you specified in the previous step, you can also associate additional Office 365 data sources with a custodian in the case.</span></span> 

<span data-ttu-id="4c72f-136">メールボックス、サイト、またはチームを特定の保管担当者にマップするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="4c72f-136">To map mailboxes, sites, or teams to a specific custodian:</span></span>

1. <span data-ttu-id="4c72f-137">[**追加データソースの選択**] ページで、特定の保管担当者の行にある [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c72f-137">On the **Select additional data sources** page, click **Add** in the row for the specific custodian.</span></span> 
  
   ![追加のデータソースをマップする](media/AddCustodianStep3.PNG)

2. <span data-ttu-id="4c72f-139">フライアウトページでは、次のいずれかの Office 365 サービスからデータソースを指定できます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-139">On the flyout page, you can specify a data source from any of the following Office 365 services:</span></span>
  
   -  <span data-ttu-id="4c72f-140">**Exchange 電子メール**-[**ユーザー、グループ、またはチームの選択**] をクリックし、[**ユーザー、グループ、またはチームの選択**] をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="4c72f-140">**Exchange email** - Click **Choose users, groups, or Teams** and then click **Choose users, groups, or teams** again.</span></span> <span data-ttu-id="4c72f-141">検索ボックスを使用して、保管担当者に関連付けるメールボックスを検索します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-141">Use the search box to find mailboxes to associate with the custodian.</span></span> <span data-ttu-id="4c72f-142">選択した保管担当者に割り当てるメールボックスを指定するには、検索ボックスを使用してユーザーのメールボックスと配布グループを検索します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-142">To specify mailboxes to assign to the selected custodian, use the search box to find user mailboxes and distribution groups.</span></span> <span data-ttu-id="4c72f-143">Office 365 グループまたは Microsoft チームに関連付けられているメールボックスを割り当てることもできます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-143">You can also assign the associated mailbox for an Office 365 group or a Microsoft Team.</span></span> <span data-ttu-id="4c72f-144">[ユーザー、グループ、チーム] チェックボックスをオンにし、[**選択**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c72f-144">Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>

        > [!NOTE]
        > <span data-ttu-id="4c72f-145">[ユーザー、グループ、またはチームの選択] をクリックしてメールボックスを指定すると、表示されているメールボックスピッカーが空になります。</span><span class="sxs-lookup"><span data-stu-id="4c72f-145">When you click Choose users, groups, or teams to specify mailboxes, the mailbox picker that's displayed is empty.</span></span> <span data-ttu-id="4c72f-146">これは、パフォーマンスを向上させるための仕様です。</span><span class="sxs-lookup"><span data-stu-id="4c72f-146">This is by design to enhance performance.</span></span> <span data-ttu-id="4c72f-147">このリストにメールボックスを追加するには、検索ボックスに名前またはエイリアス (少なくとも3文字) を入力します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-147">To add mailbox to this list, type a name or alias (a minimum of 3 characters) in the search box.</span></span>
     
     - <span data-ttu-id="4c72f-148">**Sharepoint サイト**-[**サイトの選択**] をクリックし、[**サイトの選択**] をもう一度クリックして、組織内の SharePoint サイトのリストを表示します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-148">**SharePoint sites** - Click **Choose sites** and then click **Choose sites** again to display a list of SharePoint sites in your organization.</span></span> <span data-ttu-id="4c72f-149">サイトを保管担当者に関連付けるには、一覧からサイトを選択するか、または Office 365 グループ、Microsoft teams、または OneDrive アカウントに関連付けられているサイトまたはサイトの URL を入力できます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-149">To associate a site with the custodian, you can select a site in the list or you can type the URL of a different site or a site associated with an Office 365 group, Microsoft Team, or a OneDrive account.</span></span>
     
     - <span data-ttu-id="4c72f-150">**Teams** – [**チームの選択**] をクリックし、[ **teams の選択**] をもう一度クリックして、保管担当者が現在メンバーになっている Microsoft teams の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-150">**Teams** – Click **Choose teams** and then click **Choose teams** again to display a list of Microsoft Teams that the custodian is currently a member of.</span></span> <span data-ttu-id="4c72f-151">保管担当者に追加する Teams を選択します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-151">Select the Teams that you would like to add to your custodian.</span></span> <span data-ttu-id="4c72f-152">このチェックボックスをオンにすると、関連付けられた SharePoint サイトと、その Microsoft teams に関連付けられているグループメールボックスを選択 & が自動的に識別されます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-152">Once selected, the system will automatically identify & select the associated SharePoint site and Group Mailbox associated to that Microsoft Team.</span></span> <span data-ttu-id="4c72f-153">[**選択**] をクリックし、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c72f-153">Click **Choose**, and then click **Done**.</span></span>

       ![データソースのマップ](media/AddCustodianStep4.PNG)
        
      > [!NOTE]
      > <span data-ttu-id="4c72f-155">追加のチームを保管担当者に関連付けるには、 **Exchange メール**および**SharePoint サイト**の場所を使用して、チームに関連付けられているメールボックスとサイトを個別に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c72f-155">To associate an additional team with a custodian, you have to separately add the mailbox and site associated with the team by using the **Exchange mail** and **SharePoint sites** locations.</span></span>

<span data-ttu-id="4c72f-156">保管担当者での追加のデータソースの関連付けを終了すると、 **[その他のデータソースの選択] ページ**の各保管担当者に関連付けられているメールボックス、サイト、およびチームの合計数を表示できます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-156">After you've finished associating additional data sources with the custodians, you can view the total number of mailboxes, sites, and teams associated with each custodian on the **Select additional data sources page**.</span></span> <span data-ttu-id="4c72f-157">特定の保管担当者に関連するデータソースを完成させると、この関連付けは電子情報開示ワークフローのコレクション、処理、およびレビューの各ステージで維持され、使用されます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-157">When you've finalized the relevant data sources for a specific custodian, this association will be maintained and used during the collection, processing, and review stages in eDiscovery workflow.</span></span>

## <a name="step-4-place-custodians-on-hold"></a><span data-ttu-id="4c72f-158">手順 4: 保管担当者を保留にする</span><span class="sxs-lookup"><span data-stu-id="4c72f-158">Step 4: Place custodians on hold</span></span>

<span data-ttu-id="4c72f-159">保管担当者およびケースに追加するデータソースの最終処理が完了したら、必要に応じて、一部またはすべての保管担当者を保留にすることができます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-159">After you've finalized the custodians and data sources to add to the case, you can optionally place some or all of the custodians on hold.</span></span> <span data-ttu-id="4c72f-160">保管担当者を保持すると、保管担当者に関連付けられているすべてのコンテンツの場所にあるすべてのコンテンツが保持されます。保留を解除するか、保留リストから保管担当者を解放します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-160">When you place a custodian on hold, all content in all content locations that are associated with the custodian is preserved until you remove the hold or release the custodian from the hold.</span></span> <span data-ttu-id="4c72f-161">場合によっては、保管担当者をホールドの対象にしないで、ケースに追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-161">In some cases, you may want to add custodians to a case without placing them on hold.</span></span>

<span data-ttu-id="4c72f-162">保管担当者とデータソースを保持するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="4c72f-162">To place the custodians and data sources on hold:</span></span>

1. <span data-ttu-id="4c72f-163">[選択した**保管担当者ページにホールドを配置**する] で、列の上部にある [**保留**] チェックボックスをオンにして、すべての保管担当者を保留にします。</span><span class="sxs-lookup"><span data-stu-id="4c72f-163">On the **Place a hold on the selected custodians** page, select the **Hold** check box at the top of the column to place all custodians on hold.</span></span> <span data-ttu-id="4c72f-164">保持から削除する特定の保管担当者のチェックボックスをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-164">You can then clear the check box for any specific custodian to remove from the hold.</span></span> <span data-ttu-id="4c72f-165">または、列の選択が解除されている状態で**保持**チェックボックスをオンのままにして、個々の保管担当者のチェックボックスをオンにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-165">Alternatively, you can leave the **Hold** check box at the top of the column unselected and then select the check box for individual custodians.</span></span> 
 
   ![インプレースホールド](media/AddCustodianStep5.PNG)

2. <span data-ttu-id="4c72f-167">保管担当者ホールドの選択を確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c72f-167">Verify the custodian hold selections and then click **Complete**.</span></span>

<span data-ttu-id="4c72f-168">保管担当者にホールドを設定しない場合、保管担当者と関連データソースがケースに追加されますが、それらのデータソースのコンテンツは保持されません。</span><span class="sxs-lookup"><span data-stu-id="4c72f-168">If you don't place a hold on a custodian, the custodian and their associated data sources will be added to the case but the content in those data sources won't be placed on hold.</span></span>

<span data-ttu-id="4c72f-169">保管担当者が保留になると、すべての custodial ソースを含む保管担当者保持ポリシーが自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="4c72f-169">After a custodian is placed on hold, a custodian hold policy that contains all custodial sources will be automatically created.</span></span> <span data-ttu-id="4c72f-170">このポリシーを表示するには</span><span class="sxs-lookup"><span data-stu-id="4c72f-170">To view this policy:</span></span>

1. <span data-ttu-id="4c72f-171">ケースの**ホーム**ページで、[**保留**] タブをクリックし、[ **Custodianhold-Guid**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4c72f-171">On the **Home** page of the case, click the **Holds** tab and then click **CustodianHold-Guid**,</span></span>  

2. <span data-ttu-id="4c72f-172">[ポップアップ] ページで、[**保留リストの編集**] をクリックして、保留になっているすべての保管担当者データソースを表示します。</span><span class="sxs-lookup"><span data-stu-id="4c72f-172">On the flyout page, click **Edit hold** to view all the custodian data sources that are placed on hold.</span></span>

