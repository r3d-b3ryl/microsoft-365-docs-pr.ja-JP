---
title: 管理ケースで保管担当者をAdvanced eDiscoveryする
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
description: 詳細を表示し、編集し、一括編集する方法については、Advanced eDiscoveryしてください。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739870"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="0af95-103">管理ケースで保管担当者をAdvanced eDiscoveryする</span><span class="sxs-lookup"><span data-stu-id="0af95-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="0af95-104">ケース内の [ソース]タブAdvanced eDiscoveryには、ケースに追加されたすべての保管担当者の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0af95-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="0af95-105">カストディアンをケースに追加すると、各保管担当者に関する詳細が Azure Active Directory から自動的に収集され、Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="0af95-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![保管担当者の管理](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="0af95-107">保管担当者の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="0af95-107">View custodian details</span></span>

<span data-ttu-id="0af95-108">保管担当者に関する詳細を表示するには、[保管担当者] タブの一覧からカストディアン **をクリック** します。フライアウト ページが表示され、保管担当者に関する次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0af95-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="0af95-109">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="0af95-109">Contact information</span></span>

  - <span data-ttu-id="0af95-110">**[表示名** ] - 保管担当者のアドレス帳に表示される名前。</span><span class="sxs-lookup"><span data-stu-id="0af95-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="0af95-111">これは通常、保管担当者の名、ミドル イニシャル、および名の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="0af95-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="0af95-112">**Mail/SMTP** - 保管担当者のプライマリ SMTP アドレス (たとえば、brianj@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="0af95-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="0af95-113">保管担当者のユーザー プリンシパル名 (UPN) も一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="0af95-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="0af95-114">**Title** - 保管担当者の役職。</span><span class="sxs-lookup"><span data-stu-id="0af95-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="0af95-115">**Department** - 保管担当者が動作する部署の名前。</span><span class="sxs-lookup"><span data-stu-id="0af95-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="0af95-116">**マネージャー** - 保管担当者のマネージャー。</span><span class="sxs-lookup"><span data-stu-id="0af95-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="0af95-117">指定された管理者は、この保管担当者のエスカレーション通信を受け取る。</span><span class="sxs-lookup"><span data-stu-id="0af95-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="0af95-118">場所情報</span><span class="sxs-lookup"><span data-stu-id="0af95-118">Location information</span></span>

  - <span data-ttu-id="0af95-119">**City** - 保管担当者が置かれる都市。</span><span class="sxs-lookup"><span data-stu-id="0af95-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="0af95-120">**State** - 保管担当者の住所の州または州。</span><span class="sxs-lookup"><span data-stu-id="0af95-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="0af95-121">**国/地域** - 保管担当者が置かれる国/地域。</span><span class="sxs-lookup"><span data-stu-id="0af95-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="0af95-122">**Office** - 保管担当者の所在地。</span><span class="sxs-lookup"><span data-stu-id="0af95-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="0af95-123">ケース情報</span><span class="sxs-lookup"><span data-stu-id="0af95-123">Case information</span></span>

  - <span data-ttu-id="0af95-124">**保留状態** - 保管担当者が保留にされたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0af95-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="0af95-125">**通信状態**: 保管担当者が保留通知を発行したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0af95-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="0af95-126">保管担当者が通知を発行した場合、このプロパティのこの値は発行 **済みです**。</span><span class="sxs-lookup"><span data-stu-id="0af95-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="0af95-127">保管担当者が通知を発行されていない場合、状態は未公開 **です**。</span><span class="sxs-lookup"><span data-stu-id="0af95-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="0af95-128">**Status** - ケース内の保管担当者の状態。</span><span class="sxs-lookup"><span data-stu-id="0af95-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="0af95-129">Active の状態 **は** 、保管担当者がケースの一部である場合を示します。</span><span class="sxs-lookup"><span data-stu-id="0af95-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="0af95-130">カストディアンがケースから解放された場合、ステータスは [リリース済み] に **変更されます**。</span><span class="sxs-lookup"><span data-stu-id="0af95-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="0af95-131">データ ソースとインデックス情報</span><span class="sxs-lookup"><span data-stu-id="0af95-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="0af95-132">**データ ソース**- 保管担当者に関連付けられた、ケースの一部であるデータ ソース (メールボックス、サイト、および Teams) の数と種類を示します。</span><span class="sxs-lookup"><span data-stu-id="0af95-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="0af95-133">**インデックス更新時刻** - 高度なインデックス ジョブが最後にトリガーされた日時を示します。</span><span class="sxs-lookup"><span data-stu-id="0af95-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="0af95-134">このプロパティは、高度なインデックス作成プロセスが現在進行中の場合も示します。</span><span class="sxs-lookup"><span data-stu-id="0af95-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="0af95-135">カストディアンの編集</span><span class="sxs-lookup"><span data-stu-id="0af95-135">Edit a custodian</span></span>

<span data-ttu-id="0af95-136">ケースが進むにつれて、特定の保管担当者に関連する追加のデータ ソース&可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0af95-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="0af95-137">その他のシナリオでは、確認され、関連性が高いとみなされた特定のデータ ソースを削除できます。</span><span class="sxs-lookup"><span data-stu-id="0af95-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="0af95-138">保管担当者に関連付けられているデータ ソースを更新するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="0af95-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="0af95-139">[電子情報開示 **] に> Advanced eDiscovery** ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="0af95-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="0af95-140">[ソース] **タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="0af95-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="0af95-141">[カ **ストディアン] ページで** 、リストからカストディアンを選択し、フライアウト ページの **[編集** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0af95-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![データ ソースの編集](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="0af95-143">[**データ ソースの選択**] タブをクリックして、保管担当者のメールボックスとアカウントのExchangeを変更OneDrive、[データ ソースの選択] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="0af95-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="0af95-144">[追加の **データ ソースの** 選択] タブをクリックして、保管担当者Teams、SharePoint、Exchangeメールボックスを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="0af95-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="0af95-145">保管担当者に関連付けられたデータ ソースの詳細については、「ケースに保管担当者を追加する」 [を参照してください](add-custodians-to-case.md)。</span><span class="sxs-lookup"><span data-stu-id="0af95-145">For more information about data sources associated with a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span> 
  
6. <span data-ttu-id="0af95-146">[ **保管ホールドの配置] をクリック** して、保管担当者の保留を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="0af95-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="0af95-147">保管担当者データの再インデックス</span><span class="sxs-lookup"><span data-stu-id="0af95-147">Re-index custodian data</span></span>

<span data-ttu-id="0af95-148">法的調査のためのほとんどの電子情報開示ワークフローでは、保管担当者が法的ケースに追加された後、保管担当者のデータのサブセットが検索されます。</span><span class="sxs-lookup"><span data-stu-id="0af95-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="0af95-149">ファイル サイズが非常に大きいか、データが破損する可能性があるため、保管担当者に関連付けられたデータ ソース内の一部のアイテムに部分的にインデックスが作成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0af95-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="0af95-150">Advanced eDiscovery の[高度](indexing-custodian-data.md)なインデックス作成機能を使用すると、ほとんどの部分的にインデックス付きアイテムをオンデマンドで再インデックス化することで自動的に修復できます。</span><span class="sxs-lookup"><span data-stu-id="0af95-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="0af95-151">カストディアンがケースに追加された場合、保管担当者に関連付けられたデータ ソースにあるデータは、(高度なインデックス作成プロセスによって) 自動的に再インデックス化されます。</span><span class="sxs-lookup"><span data-stu-id="0af95-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="0af95-152">つまり、データをダウンロードして修復してからオフラインで検索する代わりに、データを一所に残しておくことができます)。</span><span class="sxs-lookup"><span data-stu-id="0af95-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="0af95-153">ただし、法的ケースのライフサイクル中に、新しいデータ ソースが保管担当者に関連付けられている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0af95-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="0af95-154">この場合、高度なインデックス処理を実行して、部分的にインデックス付けされたアイテムを修復し、保管担当者のデータのインデックスを更新することで、保管担当者のデータを再インデックス化できます。</span><span class="sxs-lookup"><span data-stu-id="0af95-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="0af95-155">部分的にインデックス付けされたアイテムに対処するために再インデックスプロセスをトリガーするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0af95-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="0af95-156">[電子情報開示 **] に> Advanced eDiscovery** ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="0af95-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="0af95-157">[ソース] **タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="0af95-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="0af95-158">[保管 **担当者] ページで** 、データのインデックスを再作成する必要がある保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="0af95-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="0af95-159">[フライアウト] ページで、[インデックスの更新] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0af95-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="0af95-160">インデックス ジョブが作成されたというダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0af95-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="0af95-161">保管担当者データの再インデックスは、長時間実行されるプロセスです。作成された対応するジョブの名前は、保管 **担当者データの再インデックス化です**。</span><span class="sxs-lookup"><span data-stu-id="0af95-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="0af95-162">[ジョブ] タブまたは[カストディアン]タブで進行状況を追跡するには、[インデックスジョブの状態] 列の状態 **を監視** します。</span><span class="sxs-lookup"><span data-stu-id="0af95-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="0af95-163">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0af95-163">For more information, see:</span></span>

- [<span data-ttu-id="0af95-164">処理中のエラーの操作</span><span class="sxs-lookup"><span data-stu-id="0af95-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="0af95-165">ジョブを管理する</span><span class="sxs-lookup"><span data-stu-id="0af95-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="0af95-166">ケースから保管担当者を解放する</span><span class="sxs-lookup"><span data-stu-id="0af95-166">Release a custodian from a case</span></span>

<span data-ttu-id="0af95-167">カストディアンは、ケースが閉じている場合、保管担当者がケースのコンテンツを保持する義務がなくなった場合、または保管担当者がケースに関連しなくなったと判断された場合に解放されます。</span><span class="sxs-lookup"><span data-stu-id="0af95-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="0af95-168">保留通知が公開された後に保管担当者を解放すると、リリース通知が保管担当者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="0af95-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="0af95-169">さらに、保管担当者に関連付けられたデータ ソースに配置された保留は削除されます。</span><span class="sxs-lookup"><span data-stu-id="0af95-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="0af95-170">保管担当者がサイレント ホールドに置かれた場合 、法的保留通知は発行されませんが、その保管担当者に関連付けられたデータ ソースに対する保留は削除されます。</span><span class="sxs-lookup"><span data-stu-id="0af95-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="0af95-171">保管担当者を解放するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="0af95-171">To release a custodian:</span></span> 

1. <span data-ttu-id="0af95-172">[電子情報開示 **] に> Advanced eDiscovery** ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="0af95-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="0af95-173">[ソース] **タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="0af95-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="0af95-174">[保管 **担当者] ページ** で、ケースから解放される保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="0af95-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="0af95-175">[フライアウト] ページで、[カストディアン **の解放] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="0af95-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="0af95-176">保管担当者に関連付けられたデータ ソースに保留が設定されている場合、保留は削除され、別の Advanced eDiscovery ケースに関連付けられているその他の保留は引き続き適用されるという警告ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0af95-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="0af95-177">これには、その他の種類の保持機能 (アイテム保持ポリシー Microsoft 365含まれます。</span><span class="sxs-lookup"><span data-stu-id="0af95-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="0af95-178">[ **はい]** をクリックして、保管担当者を解放する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0af95-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="0af95-179">[保管担当者] タブのこのユーザーの状態が [リリース済み] に設定され、フライアウト ページの保留状態が False に **変更されます**。 </span><span class="sxs-lookup"><span data-stu-id="0af95-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="0af95-180">保管担当者が複数の法的ケースに同時に関与している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0af95-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="0af95-181">カストディアンがケースから解放されると、他の事項の保留と通知は影響を受け取らない。</span><span class="sxs-lookup"><span data-stu-id="0af95-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="0af95-182">保管担当者の一括編集</span><span class="sxs-lookup"><span data-stu-id="0af95-182">Bulk-edit custodians</span></span>

<span data-ttu-id="0af95-183">一括エディターを使用して、複数の保管担当者を同時に編集できます。</span><span class="sxs-lookup"><span data-stu-id="0af95-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="0af95-184">これを行うには、[保管担当者] タブで 2つ以上のカストディアンを選択して、一括エディターを表示し、タスクの 1 つをクリックします。</span><span class="sxs-lookup"><span data-stu-id="0af95-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![複数の保管担当者の設定を編集するフライアウト ページ](../media/AeDBulkEditCustodians.png)
