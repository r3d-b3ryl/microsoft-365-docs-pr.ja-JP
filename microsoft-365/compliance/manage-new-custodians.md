---
title: Advanced eDiscovery ケースでカストディアンを管理する
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
description: Advanced eDiscovery ケースで保管担当者のリストの詳細の表示、編集、一括編集を行う方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/30/2020
ms.locfileid: "49739870"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="691a5-103">Advanced eDiscovery ケースでカストディアンを管理する</span><span class="sxs-lookup"><span data-stu-id="691a5-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="691a5-104">Advanced eDiscovery ケースの[ソース] タブの [保管担当者] ページには、ケースに追加された保管担当者の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="691a5-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="691a5-105">ケースにカストディアンを追加すると、各保管担当者に関する詳細が Azure Active Directory から自動的に収集され、Advanced eDiscovery で表示できます。</span><span class="sxs-lookup"><span data-stu-id="691a5-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![保管担当者を管理する](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="691a5-107">カストディアンの詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="691a5-107">View custodian details</span></span>

<span data-ttu-id="691a5-108">カストディアンの詳細を表示するには、[保管担当者] タブの一覧から **カストディアンをクリック** します。フライアウト ページが表示され、保管担当者に関する次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="691a5-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="691a5-109">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="691a5-109">Contact information</span></span>

  - <span data-ttu-id="691a5-110">**表示名** - 保管担当者のアドレス帳に表示される名前。</span><span class="sxs-lookup"><span data-stu-id="691a5-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="691a5-111">これは通常、保管担当者の名、ミドル ネームのイニシャル、および氏名の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="691a5-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="691a5-112">**Mail/SMTP** - 保管担当者のプライマリ SMTP アドレス (たとえば、brianj@contoso.onmicrosoft.com。</span><span class="sxs-lookup"><span data-stu-id="691a5-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="691a5-113">保管担当者のユーザー プリンシパル名 (UPN) も一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="691a5-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="691a5-114">**Title:** カストディアンの役職名を指定します。</span><span class="sxs-lookup"><span data-stu-id="691a5-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="691a5-115">**部署** : 保管担当者が働く部署の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="691a5-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="691a5-116">**マネージャー** - 保管担当者のマネージャー。</span><span class="sxs-lookup"><span data-stu-id="691a5-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="691a5-117">指定されたマネージャーは、このカストディアンのエスカレーション通信を受信します。</span><span class="sxs-lookup"><span data-stu-id="691a5-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="691a5-118">場所情報</span><span class="sxs-lookup"><span data-stu-id="691a5-118">Location information</span></span>

  - <span data-ttu-id="691a5-119">**市** 区町町良人 : 保管担当者が置かれる都市。</span><span class="sxs-lookup"><span data-stu-id="691a5-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="691a5-120">**[州** ] - 保管担当者の住所の州または州。</span><span class="sxs-lookup"><span data-stu-id="691a5-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="691a5-121">**国/地域** : 保管担当者が置かっている国/地域。</span><span class="sxs-lookup"><span data-stu-id="691a5-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="691a5-122">**Office** - 保管担当者の所在地のオフィスの場所。</span><span class="sxs-lookup"><span data-stu-id="691a5-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="691a5-123">ケース情報</span><span class="sxs-lookup"><span data-stu-id="691a5-123">Case information</span></span>

  - <span data-ttu-id="691a5-124">**保留状態** - 保管担当者が保留にされたかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="691a5-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="691a5-125">**通信状態**: 保管担当者が保留通知を発行したかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="691a5-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="691a5-126">保管担当者が通知を発行した場合、このプロパティの値は発行 **されます**。</span><span class="sxs-lookup"><span data-stu-id="691a5-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="691a5-127">保管担当者が通知を発行されていない場合、ステータスは **未公開です**。</span><span class="sxs-lookup"><span data-stu-id="691a5-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="691a5-128">**Status** : ケース内の保管担当者の状態。</span><span class="sxs-lookup"><span data-stu-id="691a5-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="691a5-129">状態が **[アクティブ] の** 場合は、保管担当者がケースの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="691a5-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="691a5-130">カストディアンがケースから解放された場合、ステータスは [リリース済み] に変更 **されます**。</span><span class="sxs-lookup"><span data-stu-id="691a5-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="691a5-131">データ ソースとインデックス情報</span><span class="sxs-lookup"><span data-stu-id="691a5-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="691a5-132">**データ ソース** - 保管担当者に関連付けられた、ケースの一部であるデータ ソース (メールボックス、サイト、Teams) の数と種類を示します。</span><span class="sxs-lookup"><span data-stu-id="691a5-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="691a5-133">**インデックス更新時刻** - 高度なインデックス ジョブが最後にトリガーされた日時を示します。</span><span class="sxs-lookup"><span data-stu-id="691a5-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="691a5-134">このプロパティは、高度なインデックス作成プロセスが現在進行中である場合も示します。</span><span class="sxs-lookup"><span data-stu-id="691a5-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="691a5-135">カストディアンを編集する</span><span class="sxs-lookup"><span data-stu-id="691a5-135">Edit a custodian</span></span>

<span data-ttu-id="691a5-136">ケースが進行すると、ケース内の特定の保管担当者に関連する追加のデータ ソース&可能性があります。</span><span class="sxs-lookup"><span data-stu-id="691a5-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="691a5-137">その他のシナリオでは、レビューされ、関連性なしと見なされた特定のデータ ソースを削除できます。</span><span class="sxs-lookup"><span data-stu-id="691a5-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="691a5-138">保管担当者に関連付けられているデータ ソースを更新するには、</span><span class="sxs-lookup"><span data-stu-id="691a5-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="691a5-139">Advanced  **eDiscovery の電子情報開示>に移動し** 、ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="691a5-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="691a5-140">[ソース **] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="691a5-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="691a5-141">[**保管担当者] ページ** で、一覧からカストディアンを選択し、フライアウト ページで [編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="691a5-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![データ ソースの編集](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="691a5-143">[ **データ ソースの選択]** タブをクリックして保管担当者の Exchange メールボックスと OneDrive アカウントの設定を変更し、[データ ソースの選択 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="691a5-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="691a5-144">[その他 **のデータ ソースの選択** ] タブをクリックして、保管担当者に関連付けられている Teams、SharePoint、または Exchange メールボックスを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="691a5-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="691a5-145">カストディアンに関連付けられているデータ ソースの詳細については、「カストディアンをケースに追加する」 [を参照してください](add-custodians-to-case.md)。</span><span class="sxs-lookup"><span data-stu-id="691a5-145">For more information about data sources associated with a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span> 
  
6. <span data-ttu-id="691a5-146">[ **保管担当者の保留を配置] をクリック** して、保管担当者の保留を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="691a5-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="691a5-147">保管担当者データのインデックスを再設定する</span><span class="sxs-lookup"><span data-stu-id="691a5-147">Re-index custodian data</span></span>

<span data-ttu-id="691a5-148">法的調査のためのほとんどの電子情報開示ワークフローでは、保管担当者が法的事例に追加された後、保管担当者のデータのサブセットが検索されます。</span><span class="sxs-lookup"><span data-stu-id="691a5-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="691a5-149">ファイル サイズが非常に大きいか、データが破損する可能性が高いので、保管担当者に関連付けられているデータ ソース内の一部のアイテムに部分的にインデックスが作成される場合があります。</span><span class="sxs-lookup"><span data-stu-id="691a5-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="691a5-150">Advanced eDiscovery [の](indexing-custodian-data.md) 高度なインデックス機能を使用すると、ほとんどの部分的にインデックスが作成されたアイテムを、必要に応じてインデックスを再作成することで自動的に修復できます。</span><span class="sxs-lookup"><span data-stu-id="691a5-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="691a5-151">カストディアンがケースに追加された場合、保管担当者に関連付けられたデータ ソースにあるデータは、(高度なインデックス作成プロセスによって) 自動的にインデックスが再作成されます。</span><span class="sxs-lookup"><span data-stu-id="691a5-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="691a5-152">つまり、データをダウンロードして修復してからオフラインで検索する代わりに、データをインサイトに残しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="691a5-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="691a5-153">ただし、法的事例のライフサイクル中に、新しいデータ ソースが保管担当者に関連付けられている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="691a5-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="691a5-154">この場合、高度なインデックス作成プロセスを再実行して部分的にインデックスが作成されたアイテムを修復し、保管担当者のデータのインデックスを更新することで、保管担当者のデータのインデックスを再設定できます。</span><span class="sxs-lookup"><span data-stu-id="691a5-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="691a5-155">部分的にインデックスが作成されたアイテムに対処するために、インデックスの再作成プロセスをトリガーするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="691a5-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="691a5-156">Advanced  **eDiscovery の電子情報開示>に移動し** 、ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="691a5-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="691a5-157">[ソース **] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="691a5-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="691a5-158">[ **保管担当者] ページ** で、データのインデックスを再作成する必要がある保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="691a5-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="691a5-159">[フライアウト] ページで、[インデックスの更新] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="691a5-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="691a5-160">インデックス ジョブが作成されたというダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="691a5-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="691a5-161">保管担当者データの再インデックス化は、長時間実行されるプロセスです。作成された対応するジョブの名前は、保管担当者データ **の再インデックス化です**。</span><span class="sxs-lookup"><span data-stu-id="691a5-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="691a5-162">[ジョブ] タブまたは[保管担当者]タブで進行状況を追跡するには、[インデックス ジョブの状態] 列の状態 **を監視** します。</span><span class="sxs-lookup"><span data-stu-id="691a5-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="691a5-163">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="691a5-163">For more information, see:</span></span>

- [<span data-ttu-id="691a5-164">処理中のエラーの操作</span><span class="sxs-lookup"><span data-stu-id="691a5-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="691a5-165">ジョブを管理する</span><span class="sxs-lookup"><span data-stu-id="691a5-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="691a5-166">ケースからカストディアンを解放する</span><span class="sxs-lookup"><span data-stu-id="691a5-166">Release a custodian from a case</span></span>

<span data-ttu-id="691a5-167">カストディアンは、ケースが閉じている場合、保管担当者がケースのコンテンツを保持する義務がなくなった場合、または保管担当者がケースに関連しなくなったと判断された場合に解放されます。</span><span class="sxs-lookup"><span data-stu-id="691a5-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="691a5-168">保留通知の公開後に保管担当者を解放すると、リリース通知が保管担当者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="691a5-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="691a5-169">さらに、保管担当者に関連付けられたデータ ソースに対する保留は削除されます。</span><span class="sxs-lookup"><span data-stu-id="691a5-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="691a5-170">保管担当者がサイレント ホールド (法的情報保留通知を発行していない) 場合、リリース通知は送信されませんが、その保管担当者に関連付けられたデータ ソースに設定された保留は削除されます。</span><span class="sxs-lookup"><span data-stu-id="691a5-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="691a5-171">カストディアンを解放するには:</span><span class="sxs-lookup"><span data-stu-id="691a5-171">To release a custodian:</span></span> 

1. <span data-ttu-id="691a5-172">Advanced  **eDiscovery の電子情報開示>に移動し** 、ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="691a5-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="691a5-173">[ソース **] タブをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="691a5-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="691a5-174">[ **保管担当者] ページ** で、ケースから解放されるカストディアンを選択します。</span><span class="sxs-lookup"><span data-stu-id="691a5-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="691a5-175">[フライアウト] ページで、[カストディアンの解放 **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="691a5-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="691a5-176">保管担当者に関連付けられているデータ ソースに保留が設定されている場合、保留は削除され、別の Advanced eDiscovery ケースに関連付けられているその他の保留は引き続き適用されるという警告ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="691a5-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="691a5-177">これには、その他の種類の保持機能 (Microsoft 365 アイテム保持ポリシーなど) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="691a5-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="691a5-178">[ **はい]** をクリックして、カストディアンを解放します。</span><span class="sxs-lookup"><span data-stu-id="691a5-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="691a5-179">[保管担当者] タブのこのユーザーの状態が [解放済み] に設定され、フライアウト ページの保留状態が False に変更 **されます**。 </span><span class="sxs-lookup"><span data-stu-id="691a5-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="691a5-180">カストディアンは、複数の法的事例に同時に関与する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="691a5-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="691a5-181">カストディアンがケースから解放された場合、他の問題の保留と通知は影響を受け取らない。</span><span class="sxs-lookup"><span data-stu-id="691a5-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="691a5-182">カストディアンの一括編集</span><span class="sxs-lookup"><span data-stu-id="691a5-182">Bulk-edit custodians</span></span>

<span data-ttu-id="691a5-183">一括エディターを使用して、複数の保管担当者を同時に編集できます。</span><span class="sxs-lookup"><span data-stu-id="691a5-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="691a5-184">これを行うには、[保管担当者] タブで 2人以上のカストディアンを選択して、一括エディターを表示し、タスクの 1 つをクリックします。</span><span class="sxs-lookup"><span data-stu-id="691a5-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![複数のカストディアンの設定を編集するフライアウト ページ](../media/AeDBulkEditCustodians.png)
