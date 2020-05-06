---
title: 高度な電子情報開示ケースで保管担当者を管理する
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
description: 高度な電子情報開示ケースで、保管担当者の一覧の詳細、編集、および一括編集を表示する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 895383f72259fa5e46a46df35925bcc73f62e3a5
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034179"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="8cbbc-103">高度な電子情報開示ケースで保管担当者を管理する</span><span class="sxs-lookup"><span data-stu-id="8cbbc-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="8cbbc-104">Advanced eDiscovery の [保管担当者] タブには、ケースに追加されているすべての保管担当者の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-104">The Custodians tab in Advanced eDiscovery contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="8cbbc-105">保管担当者をケースに追加すると、各保管担当者の詳細が Azure Active Directory から自動的に収集され、高度な電子情報開示で表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![保管担当者の管理](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="8cbbc-107">保管担当者の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="8cbbc-107">View custodian details</span></span>

<span data-ttu-id="8cbbc-108">保管担当者の詳細を表示するには、[**保管担当者**] タブのリストで保管担当者をクリックします。ポップアップページが表示され、保管担当者に関する次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="8cbbc-109">連絡先情報</span><span class="sxs-lookup"><span data-stu-id="8cbbc-109">Contact information</span></span>

  - <span data-ttu-id="8cbbc-110">[**表示名**保管担当者のアドレス帳に表示される名前。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="8cbbc-111">通常は、保管担当者の名、ミドルネーム、姓の組み合わせになります。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="8cbbc-112">**Mail/SMTP** -保管担当者のプライマリ SMTP アドレス (例: brianj@contoso.onmicrosoft.com)。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="8cbbc-113">保管担当者のユーザープリンシパル名 (UPN) も一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="8cbbc-114">**Title** -保管担当者の役職。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="8cbbc-115">**Department** -保管担当者が機能する部署の名前。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="8cbbc-116">**上司**-保管担当者の上司。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="8cbbc-117">指定した上司は、この保管担当者のエスカレーション情報を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="8cbbc-118">場所情報</span><span class="sxs-lookup"><span data-stu-id="8cbbc-118">Location information</span></span>

  - <span data-ttu-id="8cbbc-119">**City** -保管担当者が配置されている市区町村。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="8cbbc-120">**State** -保管担当者の住所の都道府県を示します。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="8cbbc-121">**国/地域**-保管担当者が配置されている国/地域。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="8cbbc-122">**Office** -保管担当者の事業所のオフィスの場所。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="8cbbc-123">ケース情報</span><span class="sxs-lookup"><span data-stu-id="8cbbc-123">Case information</span></span>

  - <span data-ttu-id="8cbbc-124">**ホールド状態**-保管担当者が保留中であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="8cbbc-125">**通信の状態**: 保管担当者に保留通知が発行されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="8cbbc-126">保管担当者に通知が発行されている場合は、このプロパティの値が**公開**されます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="8cbbc-127">保管担当者に通知が発行されていない場合、状態**は未発行になります。**</span><span class="sxs-lookup"><span data-stu-id="8cbbc-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="8cbbc-128">**状態**-ケース内の保管担当者の状態。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="8cbbc-129">状態が "**アクティブ**" は、保管担当者がケースの一部であることを示します。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="8cbbc-130">保管担当者がケースからリリースされている場合は、ステータスが [**リリース**済み] に変更されます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="8cbbc-131">データソースとインデックス作成に関する情報</span><span class="sxs-lookup"><span data-stu-id="8cbbc-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="8cbbc-132">**データソース**-保管担当者に関連付けられていて、ケースの一部であるデータソース (メールボックス、サイト、およびチーム) の数と種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="8cbbc-133">**インデックスの更新時刻**-高度なインデックス作成ジョブが最後にトリガーされた日時を示します。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="8cbbc-134">このプロパティは、高度なインデックス処理が現在進行中であることも示します。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="8cbbc-135">保管担当者を編集する</span><span class="sxs-lookup"><span data-stu-id="8cbbc-135">Edit a custodian</span></span>

<span data-ttu-id="8cbbc-136">ケースの進行状況に応じて、特定の保管担当者に関連する追加のデータソースが存在する可能性があることがわかっている場合があり &。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="8cbbc-137">その他のシナリオでは、確認され、関連性がないと見なされた特定のデータソースを削除することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="8cbbc-138">保管担当者に関連付けられているデータソースを更新するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="8cbbc-139">**電子情報開示 > Advanced ediscovery**に移動し、ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="8cbbc-140">[**保管担当者**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-140">Click the **Custodians** tab.</span></span>
  
3. <span data-ttu-id="8cbbc-141">リストから保管担当者を選択し、フライアウトページの [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-141">Select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![データソースの編集](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="8cbbc-143">[**データソースの選択**] タブをクリックして、保管担当者の Exchange メールボックスと OneDrive アカウントの設定を変更し、[**データソースの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="8cbbc-144">保管担当者に関連付けられている Teams、SharePoint、または Exchange メールボックスを追加または削除するには、[**その他のデータソースの選択**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="8cbbc-145">保管担当者に関連付けられているデータソースの詳細については、「 [Add 保管担当者 to case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian)」の「手順 3: 追加のデータソースを保管担当者に関連付ける」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-145">For more information about data sources associated with a custodian, see "Step 3: Associate additional data sources to a custodian" in [Add custodians to a case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian).</span></span> 
  
6. <span data-ttu-id="8cbbc-146">保管担当者のホールドを有効または無効にするには、[ **custodial ホールドを配置**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="8cbbc-147">保管担当者データを再インデックス化する</span><span class="sxs-lookup"><span data-stu-id="8cbbc-147">Re-index custodian data</span></span>

<span data-ttu-id="8cbbc-148">法的調査のためのほとんどの電子情報開示ワークフローでは、保管担当者が訴訟に追加された後、保管担当者のデータのサブセットが検索されます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="8cbbc-149">非常に大きなファイルサイズまたはデータの破損が原因で、保管担当者に関連付けられているデータソース内の一部のアイテムが部分的にインデックス処理されることがあります。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="8cbbc-150">高度な電子情報開示の[高度なインデックス](indexing-custodian-data.md)機能を使用すると、ほとんどのインデックス付きアイテムは、必要に応じてこれらのアイテムのインデックスを再作成することで、自動的に修復できます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="8cbbc-151">保管担当者がケースに追加されると、保管担当者に関連付けられているデータソース内のデータは自動的に再インデックス化されます (高度なインデックス作成プロセスによって)。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="8cbbc-152">つまり、データをダウンロードして修復してからオフラインで検索する代わりに、データをインプレースのままにしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="8cbbc-153">ただし、訴訟のライフサイクルの間に、新しいデータソースが保管担当者に関連付けられる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="8cbbc-154">この場合は、高度なインデックス処理を再実行して、部分的にインデックス付けされたアイテムを修復し、保管担当者のデータのインデックスを更新することで、保管担当者のデータのインデックスを再作成できます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="8cbbc-155">部分的なインデックスが作成されたアイテムを処理するために、再インデックス処理をトリガーするには</span><span class="sxs-lookup"><span data-stu-id="8cbbc-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="8cbbc-156">**電子情報開示 > Advanced ediscovery**に移動し、ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="8cbbc-157">[**保管担当者] タブ**をクリックし、データが再インデックス化にする必要がある保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-157">Click to **Custodians tab**, and then select a custodian whose data must be reindexed.</span></span> 

3. <span data-ttu-id="8cbbc-158">[フライアウト] ページで、[**インデックスの更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-158">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="8cbbc-159">インデックスジョブが作成されたことを示すダイアログが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-159">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="8cbbc-160">保管担当者データの再インデックス作成は、長時間実行されるプロセスです。作成された対応するジョブには、**保管担当者データの再インデックス**という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-160">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="8cbbc-161">[**ジョブ**] タブまたは [**保管担当者**] タブで進行状況を追跡するには、[**インデックス作成ジョブの状態**] 列の状態を監視します。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-161">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="8cbbc-162">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-162">For more information, see:</span></span>

- [<span data-ttu-id="8cbbc-163">処理中のエラーの操作</span><span class="sxs-lookup"><span data-stu-id="8cbbc-163">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="8cbbc-164">ジョブを管理する</span><span class="sxs-lookup"><span data-stu-id="8cbbc-164">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="8cbbc-165">ケースからの保管担当者のリリース</span><span class="sxs-lookup"><span data-stu-id="8cbbc-165">Release a custodian from a case</span></span>

<span data-ttu-id="8cbbc-166">保管担当者がリリースされるのは、ケースがクローズされた場合、保管担当者がケースのコンテンツを保持する義務がなくなった場合、または保管担当者がケースに関連していないと判断された場合です。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-166">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="8cbbc-167">保留通知が公開された後に保管担当者をリリースした場合は、リリース通知が保管担当者に送信されます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-167">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="8cbbc-168">さらに、保管担当者に関連付けられたデータソースに配置されたすべての保留リストが削除されます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-168">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="8cbbc-169">保管担当者が、法的情報保留通知を発行していない*サイレントホールド*に配置されていた場合、リリース通知は送信されませんが、その保管担当者に関連付けられていたデータソースに配置された保留リストは削除されます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-169">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="8cbbc-170">保管担当者をリリースするには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-170">To release a custodian:</span></span> 

1. <span data-ttu-id="8cbbc-171">**電子情報開示 > Advanced ediscovery**に移動し、ケースを開きます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-171">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2.    <span data-ttu-id="8cbbc-172">[**保管担当者**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-172">Go to the **Custodians** tab.</span></span>

3.    <span data-ttu-id="8cbbc-173">[**保管担当者] タブ**をクリックし、ケースからリリースされる保管担当者を選択します。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-173">Click to **Custodians tab**, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="8cbbc-174">[フライアウト] ページで、[ **Release 保管担当者**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-174">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="8cbbc-175">保管担当者に関連付けられたデータソースにホールドが設定されている場合、保留が解除され、別の高度な電子情報開示ケースに関連付けられている他のすべての保留が引き続き適用されることを説明する警告ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-175">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="8cbbc-176">その他の種類の保持および保持機能 (Microsoft 365 アイテム保持ポリシーなど) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-176">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="8cbbc-177">[**はい**] をクリックして、保管担当者を解放することを確認します。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-177">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="8cbbc-178">[**保管担当者**] タブでこのユーザーの状態が [**リリース**済み] に設定されており、フライアウトページの**保持状態**が**False**に変更されます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-178">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="8cbbc-179">保管担当者は、いくつかの法的なケースに同時に関与する場合があります。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-179">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="8cbbc-180">保管担当者がケースからリリースされた場合、他の事柄の保留と通知は影響を受けません。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-180">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="8cbbc-181">一括編集保管担当者</span><span class="sxs-lookup"><span data-stu-id="8cbbc-181">Bulk-edit custodians</span></span>

<span data-ttu-id="8cbbc-182">一括エディターを使用して、同時に複数の保管担当者を編集できます。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-182">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="8cbbc-183">これを行うには、[**保管担当者**] タブで2つ以上の保管担当者を選択して一括エディターを表示し、タスクの1つをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8cbbc-183">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![複数の保管担当者の設定を編集するためのフライアウトページ](../media/AeDBulkEditCustodians.png)
