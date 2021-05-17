---
title: 管理者をケースに追加Advanced eDiscoveryする
f1.keywords:
- NOCSH
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
description: 組み込みのカストディアン管理ツールを使用して、Advanced eDiscoveryを調整し、関連するデータ ソースを特定する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740344"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a><span data-ttu-id="d5b1c-103">管理者をケースに追加Advanced eDiscoveryする</span><span class="sxs-lookup"><span data-stu-id="d5b1c-103">Add custodians to an Advanced eDiscovery case</span></span>

<span data-ttu-id="d5b1c-104">Advanced eDiscovery の組み込みのカストディアン管理ツールを使用して、保管担当者の管理とケースに関連する関連する保管データ ソースの特定に関するワークフローを調整します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-104">Use the built-in custodian management tool in Advanced eDiscovery to coordinate your workflows around managing custodians and identifying relevant, custodial data sources associated with a case.</span></span> <span data-ttu-id="d5b1c-105">保管担当者を追加すると、システムは自動的に自分のメールボックスとユーザー アカウントExchange保持OneDrive for Businessできます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-105">When you add a custodian, the system can automatically identify and place a hold on their Exchange mailbox and OneDrive for Business account.</span></span> <span data-ttu-id="d5b1c-106">調査の検出プロセス中に、保管担当者がアクセスまたは投稿した他のデータ ソース (メールボックス、サイト、Teams など) を特定する場合もあります。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-106">During the discovery process of your investigation, you might also identify other data sources (such as mailboxes, sites, or Teams) that a custodian accessed or contributed to.</span></span> <span data-ttu-id="d5b1c-107">このような場合は、保管担当者管理ツールを使用して、特定の保管担当者に関連付けるデータ ソースを関連付けできます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-107">In this situation, you can use the custodian management tool to associate those data sources will a specific custodian.</span></span> <span data-ttu-id="d5b1c-108">カストディアンをケースに追加し、他のデータ ソースを関連付けると、データをすばやく保持し、保管データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-108">After you add custodians to a case and associate other data source with them, you can quickly preserve data and search the custodial data.</span></span>

<span data-ttu-id="d5b1c-109">次の 4 つの手順で、Advanced eDiscoveryにカストディアンを追加および管理できます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-109">You can add and manage custodians in Advanced eDiscovery cases in four steps:</span></span>

1. <span data-ttu-id="d5b1c-110">保管担当者を特定します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-110">Identify the custodians.</span></span>

2. <span data-ttu-id="d5b1c-111">カストディアン データの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-111">Choose custodian data locations.</span></span>

3. <span data-ttu-id="d5b1c-112">保留設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-112">Configure hold settings.</span></span>

4. <span data-ttu-id="d5b1c-113">保管担当者を確認し、プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-113">Review the custodians and complete the process.</span></span>

   <span data-ttu-id="d5b1c-114">[![[ソース] タブ (Advanced eDiscoveryケース) ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d5b1c-114">[ ![Sources tab in Advanced eDiscovery case](../media/AeD-Sources-Tab.png) ](../media/AeD-Sources-Tab.png#lightbox)</span></span>

## <a name="make-sure-you-have-the-necessary-permissions"></a><span data-ttu-id="d5b1c-115">必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-115">Make sure you have the necessary permissions</span></span>

<span data-ttu-id="d5b1c-116">ケースに保管担当者を追加するには、電子情報開示マネージャーの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-116">To add custodians to a case, you must be a member of the eDiscovery Manager role group.</span></span> <span data-ttu-id="d5b1c-117">これにより、カストディアンをケースに追加し、保管データ ソースを保持するために必要なアクセス許可が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-117">This provides you with the necessary permissions to add custodians to a case and place a hold on the custodial data sources.</span></span> <span data-ttu-id="d5b1c-118">詳細については、「[電子情報開示のアクセス許可を割り当てる](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions)」を参照してください。電子情報開示のアクセス許可を割り当てる」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-118">For more information, see [Assign eDiscovery permissions](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions).</span></span>

## <a name="step-1-identify-custodians"></a><span data-ttu-id="d5b1c-119">手順 1: 保管担当者を特定する</span><span class="sxs-lookup"><span data-stu-id="d5b1c-119">Step 1: Identify custodians</span></span>

1. <span data-ttu-id="d5b1c-120">適切な [https://compliance.microsoft.com](https://compliance.microsoft.com) 電子情報開示アクセス許可が割り当てられているユーザー アカウントに移動してサインインします。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-120">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and sign in with a user account that has been assigned the appropriate eDiscovery permissions.</span></span>

2. <span data-ttu-id="d5b1c-121">Microsoft 365 コンプライアンス センターの左側のナビゲーション ウィンドウで、[**すべてを表示**] をクリックし、**[eDiscovery] > [Advanced]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-121">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **eDiscovery > Advanced**.</span></span>

3. <span data-ttu-id="d5b1c-122">[ユーザーの **Advanced eDiscovery]** ページで、[ケース] タブをクリックし、保管担当者を追加するケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-122">On the **Advanced eDiscovery** page, click the **Cases** tab, and then select the case that you want to add custodians to.</span></span>

4. <span data-ttu-id="d5b1c-123">[データ ソース **] タブをクリックし**、[データ ソースの追加] **[新しい** 保管  >  **担当者の追加] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-123">Click the **Data sources** tab and then click **Add data source** > **Add new custodians**.</span></span>

5. <span data-ttu-id="d5b1c-124">ユーザーの名前またはエイリアスの最初の部分を入力して、組織内の 1 人または複数のユーザーをカストディアンとしてケースに追加します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-124">Add one or more users in your organization as custodians to the case by typing the first part of a person's name or alias.</span></span> <span data-ttu-id="d5b1c-125">正しいユーザーを見つけたら、そのユーザーの名前を選択してリストに追加します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-125">After you find the correct person, select their name to add them to the list.</span></span>

## <a name="step-2-choose-custodian-data-locations"></a><span data-ttu-id="d5b1c-126">手順 2: 保管担当者のデータの場所を選択する</span><span class="sxs-lookup"><span data-stu-id="d5b1c-126">Step 2: Choose custodian data locations</span></span>

<span data-ttu-id="d5b1c-127">保管担当者を選択すると、システムは自動的にこれらのユーザーとそのデータ ソースを識別して確認します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-127">After you select custodians, the system automatically attempts to identify and verify these users and their data sources.</span></span> <span data-ttu-id="d5b1c-128">リストに保管担当者を追加すると、ツールには、各保管担当者のプライマリ メールボックスOneDriveアカウントが自動的に含まれます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-128">After adding custodians to the list, the tool automatically includes the primary mailbox and OneDrive account for each custodian.</span></span> <span data-ttu-id="d5b1c-129">ケースに保管担当者を追加する場合は、これらのデータ ソースを含めないを選択できます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-129">You can choose not to include these data sources when adding custodians to the case.</span></span>

<span data-ttu-id="d5b1c-130">保管担当者のメールボックスと OneDrive アカウントに加えて、保管担当者がメンバーである SharePoint サイトや Microsoft チームなど、他のデータの場所を保管担当者に関連付けすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-130">In addition to a custodian's mailbox and OneDrive account, you can also associate other data locations to a custodian, such as SharePoint site or a Microsoft Team the custodian is a member of.</span></span> <span data-ttu-id="d5b1c-131">これにより、ケースの保管担当者に関連付けられた他のデータ ソースのコンテンツを保持、収集、分析、および確認できます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-131">This allows you to preserve, collect, analyze, and review content in other data sources associated with the custodians of the case.</span></span>

<span data-ttu-id="d5b1c-132">保管担当者のプライマリ メールボックスOneDriveアカウントの選択を解除するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-132">To deselect the primary mailbox and OneDrive account for a custodian:</span></span>

1. <span data-ttu-id="d5b1c-133">保管担当者を展開して、各保管担当者に自動的に関連付けられたプライマリ データの場所を表示します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-133">Expand the custodian to view the primary data locations that have been automatically associated to each custodian.</span></span>

2. <span data-ttu-id="d5b1c-134">[**メールボックスまたはメールボックス**]**の横** にある **[OneDrive]** を選択して、保管担当者のメールボックスまたは OneDrive アカウントをこの保管担当者のデータの場所として関連付けから削除します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-134">Select **Clear** next to **Mailbox** or **OneDrive** to remove a custodian's mailbox or OneDrive account from being associated as a data location for this custodian.</span></span>

   ![保管担当者に関連付ける場所を構成する](../media/ConfigureCustodianLocations.png)

<span data-ttu-id="d5b1c-136">他のメールボックス、サイト、Teams、Yammerを特定の保管担当者に関連付けるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-136">To associate other mailboxes, sites, Teams, or Yammer groups to a specific custodian:</span></span>

1. <span data-ttu-id="d5b1c-137">保管担当者を展開して次のサービスを表示し、データの場所を保管担当者に関連付ける。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-137">Expand a custodian to display the following services to associate data locations with the custodian.</span></span> <span data-ttu-id="d5b1c-138">サービスの **横にある** [編集] をクリックして、データの場所を追加します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-138">Click **Edit** next to a service to add a data location.</span></span>

   - <span data-ttu-id="d5b1c-139">**Exchange**: 他のメールボックスを保管担当者に関連付ける場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-139">**Exchange**: Use to associate other mailboxes to the custodian.</span></span> <span data-ttu-id="d5b1c-140">ユーザー メールボックスまたは配布グループの名前またはエイリアス (最低 3 文字) を検索ボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-140">Type into the search box the name or alias (a minimum of three characters) of user mailboxes or distribution groups.</span></span> <span data-ttu-id="d5b1c-141">保管担当者に割り当てるメールボックスを選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-141">Select the mailboxes to assign to the custodian and then click **Add**.</span></span>

   - <span data-ttu-id="d5b1c-142">**SharePoint**: サイトを保管担当者SharePoint関連付ける場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-142">**SharePoint**: Use to associate SharePoint sites to the custodian.</span></span> <span data-ttu-id="d5b1c-143">リスト内のサイトを選択するか、検索ボックスに URL を入力してサイトを検索します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-143">Select a site in the list or search for a site by typing a URL in the search box.</span></span> <span data-ttu-id="d5b1c-144">保管担当者に割り当てるサイトを選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-144">Select the sites to assign to the custodian and then click **Add**.</span></span>

   - <span data-ttu-id="d5b1c-145">**Teams**: 保管担当者が現在のメンバー Microsoft Teamsを割り当てる場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-145">**Teams**: Use to assign the Microsoft Teams the custodian is currently a member of.</span></span> <span data-ttu-id="d5b1c-146">カストディアンに割り当てるチームを選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-146">Select the teams to assign to the custodian and then click **Add**.</span></span> <span data-ttu-id="d5b1c-147">チームを追加すると、システムは自動的に、そのチームに関連付SharePointサイトメールボックスとグループ メールボックスを識別し、そのメールボックスを保管担当者に割り当てる。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-147">After you add a team, the system automatically identifies and locates the SharePoint site and group mailbox associated to that team and assigns them to the custodian.</span></span>

   - <span data-ttu-id="d5b1c-148">**Yammer**: 保管担当者が現在メンバー Yammerグループを割り当てる場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-148">**Yammer**:  Use to assign the Yammer groups the custodian is currently a member of.</span></span> <span data-ttu-id="d5b1c-149">保管担当者に割り当てるグループを選択し、[追加] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-149">Select the groups to assign to the custodian and then click **Add**.</span></span> <span data-ttu-id="d5b1c-150">チームを追加すると、そのグループに関連付けられた SharePoint およびグループ メールボックスが自動的に識別され、見つけ出され、そのメールボックスが保管担当者に割り当てされます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-150">After you add a team, the system automatically identifies and locates the SharePoint site and group mailbox associated to that group and assigns them to the custodian.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d5b1c-151">Exchange および **SharePoint** 場所ピッカーを使用して、他のチームまたは Yammer グループ (保管担当者がメンバーではない) を保管担当者に関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-151">You can use the **Exchange** and **SharePoint** location pickers to associate other teams or Yammer groups (that a custodian is not a member of) to a custodian.</span></span> <span data-ttu-id="d5b1c-152">これを行うには、各チームまたはグループに関連付けられているメールボックスとサイトの両方を追加Yammerがあります。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-152">To do this, you have to add both the mailbox and site associated with each team or Yammer group.</span></span>

2. <span data-ttu-id="d5b1c-153">各保管担当者に割り当てられたメールボックス、サイト、Teams、Yammer グループの総数を表示するには、テーブル内の各保管担当者を展開します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-153">You can view the total number of mailboxes, sites, Teams, and Yammer groups assigned to each custodian by expanding each custodian in the table.</span></span> <span data-ttu-id="d5b1c-154">各保管担当者に割り当てられたデータの場所を確定すると、これらの関連付けは、Advanced eDiscovery ワークフローの収集、処理、およびレビューの段階で維持および使用されます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-154">When you've finalized the assigned data locations for each custodian, these associations will be maintained and used during the collection, processing, and review stages in the Advanced eDiscovery workflow.</span></span>

3. <span data-ttu-id="d5b1c-155">保管担当者を追加してデータの場所を構成したら、[次へ] **をクリックして** [保留設定] **ページに移動** します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-155">After adding custodians and configuring their data locations, click **Next** to go to the **Hold settings** page.</span></span>  

## <a name="step-3-configure-hold-settings"></a><span data-ttu-id="d5b1c-156">手順 3: 保留設定を構成する</span><span class="sxs-lookup"><span data-stu-id="d5b1c-156">Step 3: Configure hold settings</span></span>

 <span data-ttu-id="d5b1c-157">保管担当者とそのデータの場所を確定したら、一部またはすべての保管担当者を保留にできます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-157">After you've finalized the custodians and their data locations, you can place some or all of the custodians on hold.</span></span> <span data-ttu-id="d5b1c-158">保管担当者を保留にした場合、保管担当者に関連付けられているすべてのコンテンツの場所のすべてのコンテンツは、保留リストを削除するか保留リストから解放するまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-158">When you place a custodian on hold, all content in all content locations that are associated with the custodian is preserved until you remove the hold or release the custodian from the hold.</span></span> <span data-ttu-id="d5b1c-159">場合によっては、保管担当者を保留にせずにケースに追加できます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-159">In some cases, you may want to add custodians to a case without placing them on hold.</span></span>

<span data-ttu-id="d5b1c-160">保管担当者とデータ ソースを保留にするには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-160">To place the custodians and data sources on hold:</span></span>

1. <span data-ttu-id="d5b1c-161">[保留 **設定] ページ** で、[保持] 列の下にあるチェック ボックスをオンにして、個々の保管担当者に保留を **適用** できます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-161">On the **Hold settings** page, you can apply a hold to individual custodians by selecting the checkbox under the **Hold** column.</span></span>

   <span data-ttu-id="d5b1c-162">または、列の上部にある [保持] チェック ボックスをオンにして、すべての保管担当者を保留にできます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-162">Alternatively, you can place all custodians on hold by selecting the **Hold** checkbox at the top of the column.</span></span>

2. <span data-ttu-id="d5b1c-163">カストディアンホールドの選択内容を確認し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-163">Verify the custodian hold selections and then click **Next**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d5b1c-164">保管担当者に保留を設定しない場合、保管担当者とその関連データ ソースがケースに追加されますが、それらのデータ ソース内のコンテンツは、ケースに関連付けられた保留リストによって保持されません。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-164">If you don't place a hold on a custodian, the custodian and their associated data sources will be added to the case but the content in those data sources won't preserved by the hold that associated with the case.</span></span>

## <a name="step-4-review-the-custodians-and-complete-the-process"></a><span data-ttu-id="d5b1c-165">手順 4: 保管担当者を確認し、プロセスを完了する</span><span class="sxs-lookup"><span data-stu-id="d5b1c-165">Step 4: Review the custodians and complete the process</span></span>

<span data-ttu-id="d5b1c-166">ケースに実際に保管担当者を追加する前に、保管担当者の一覧、保管担当者に割り当てられたデータの場所、および保留設定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-166">Before you actually add the custodians to the case, you can review the list of custodians, the data locations assigned to them, and the hold settings.</span></span>

1. <span data-ttu-id="d5b1c-167">テーブル内の各保管担当者に関連付けられているすべてのデータ ソース数と保留設定を確認して確認します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-167">Verify and review all the data sources count and the hold setting associated with each custodian in the table.</span></span> <span data-ttu-id="d5b1c-168">必要に応じて、[保管担当者の特定] ページまたは **[保留設定** ] ページに **戻** り、変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-168">If necessary, go back to the **Identify custodian** or **Hold settings** pages to make any changes.</span></span>

2. <span data-ttu-id="d5b1c-169">[ **送信] を** クリックして保管担当者とそのデータの場所をケースに追加し、すべての保管ホールド設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-169">Click **Submit** to add custodians and their data locations to the case and apply all custodial hold settings.</span></span>

   <span data-ttu-id="d5b1c-170">新しい保管担当者がケースに追加され、[データ ソース] **タブに表示** されます。</span><span class="sxs-lookup"><span data-stu-id="d5b1c-170">The new custodians are added to the case and displayed on the **Data sources** tab.</span></span>

   <span data-ttu-id="d5b1c-171">[![[データ ソース] タブに表示される保管担当者 ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d5b1c-171">[ ![Custodians listed on the Data sources tab](../media/DataSourcesTab.png) ](../media/DataSourcesTab.png#lightbox)</span></span>
