---
title: コア電子情報開示ケースのクローズ、再オープン、削除
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: この記事では、コア電子情報開示ケースを管理する方法について説明します。 これには、ケースをクローズする、クローズしたケースを再度開く、ケースを削除することが含まれます。
ms.openlocfilehash: 45282486c2c3b1d00b99a1cda5968b3bb042f6c2
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208419"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="7e67d-104">コア電子情報開示ケースのクローズ、再オープン、削除</span><span class="sxs-lookup"><span data-stu-id="7e67d-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="7e67d-105">この記事では、Microsoft 365 でコア電子情報開示ケースをクローズ、再オープン、および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7e67d-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="7e67d-106">ケースをクローズする</span><span class="sxs-lookup"><span data-stu-id="7e67d-106">Close a case</span></span>

<span data-ttu-id="7e67d-107">コア電子情報開示ケースでサポートされている訴訟や調査が完了したら、ケースを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="7e67d-108">ケースをクローズすると、次のような結果になります。</span><span class="sxs-lookup"><span data-stu-id="7e67d-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="7e67d-109">ケースに電子情報開示の保留になっているコンテンツの場所が含まれている場合、それらの保持はオフになります。</span><span class="sxs-lookup"><span data-stu-id="7e67d-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="7e67d-110">これにより、ユーザーまたは削除ポリシーなどの自動プロセスによって、コンテンツが完全に削除されるか、削除される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7e67d-110">This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="7e67d-111">ケースを閉じるだけで、そのケースに関連付けられている保留がオフになります。</span><span class="sxs-lookup"><span data-stu-id="7e67d-111">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="7e67d-112">他のホールドがコンテンツの場所 (訴訟ホールド、保持ポリシー、別のコア電子情報開示ケースの保留など) に設定されている場合でも、その保持は維持されます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-112">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="7e67d-113">ケースは、Microsoft 365 コンプライアンスセンターのコア電子情報開示ページに引き続き記載されています。</span><span class="sxs-lookup"><span data-stu-id="7e67d-113">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="7e67d-114">クローズしたケースの詳細、保持、検索、メンバーは保持されます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-114">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="7e67d-115">クローズされた case を編集できます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-115">You can edit a case after it's closed.</span></span> <span data-ttu-id="7e67d-116">たとえば、メンバーを追加または削除したり、検索を作成したり、検索結果をエクスポートしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-116">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="7e67d-117">アクティブなケースとクローズされたケースの主な違いは、ケースがクローズされたときに電子情報開示の保留がオフになっていることです。</span><span class="sxs-lookup"><span data-stu-id="7e67d-117">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="7e67d-118">ケースを閉じるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="7e67d-118">To close a case:</span></span>
  
1. <span data-ttu-id="7e67d-119">Microsoft 365 コンプライアンスセンターで、[**電子情報開示**コア] をクリックして、  >  **Core**組織内のコア電子情報開示ケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="7e67d-119">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="7e67d-120">閉じるケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e67d-120">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="7e67d-121">[**このケースを管理**] ポップアップ ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-121">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="7e67d-122">[**ケースの状態の管理**] で、[ **case を閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e67d-122">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="7e67d-123">ケースに関連付けられた保留が無効になることを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-123">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="7e67d-124">[**はい**] をクリックしてケースを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-124">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="7e67d-125">[**このケースを管理**] ポップアップ ページの状態が [**アクティブ**] から [**閉じています**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="7e67d-125">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="7e67d-126">[**このケースを管理**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-126">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="7e67d-127">[**コア電子情報開示**] ページで、[**更新**] をクリックして、クローズされたケースの状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="7e67d-127">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="7e67d-128">決算プロセスが完了するまでに最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e67d-128">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="7e67d-129">プロセスが完了すると、そのケースの状態が [**コア電子情報開示**] ページで [**終了**] に変更されます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-129">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="7e67d-130">ケースの名前をもう一度クリックして、ケースがクローズされた場合とクローズしたユーザーに関する情報が含まれている [**このケースの管理**] ポップアップページを表示します。</span><span class="sxs-lookup"><span data-stu-id="7e67d-130">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="7e67d-131">クローズしたケースを再度開く</span><span class="sxs-lookup"><span data-stu-id="7e67d-131">Reopen a closed case</span></span>

<span data-ttu-id="7e67d-132">ケースを再度開くと、ケースが閉じられたときに設定されていた電子情報開示保持は自動的に再開されません。</span><span class="sxs-lookup"><span data-stu-id="7e67d-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="7e67d-133">ケースを再度開いた後、**ホールド**ページに移動して、前のホールドをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e67d-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="7e67d-134">保留リストを有効にするには、それを選択して、フライアウトページを表示した後、**状態**の切り替えを **[オン**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="7e67d-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="7e67d-135">Microsoft 365 コンプライアンスセンターで、[**電子情報開示**コア] をクリックして、  >  **Core**組織内のコア電子情報開示ケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="7e67d-135">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="7e67d-136">再度開くケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e67d-136">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="7e67d-137">[**このケースを管理**] ポップアップ ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-137">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="7e67d-138">[**ケースの状態を管理する**] で、[**ケースを再度開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e67d-138">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="7e67d-139">ケースを閉じたときに関連付けられていた保留は自動的に有効にならないことを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="7e67d-140">[**はい**] をクリックしてケースを再度開きます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="7e67d-141">[**このケースを管理**] ポップアップ ページの状態が [**閉じる**] から [**アクティブ**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="7e67d-141">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="7e67d-142">[**このケースを管理**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-142">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="7e67d-143">[**コア電子情報開示**] ページで、[**更新**] をクリックして、再度開くケースの状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="7e67d-143">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="7e67d-144">再起動プロセスが完了するまでに最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7e67d-144">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="7e67d-145">プロセスが完了すると、**コア電子情報開示**ページでケースの状態が [**アクティブ**] に変更されます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-145">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="7e67d-146">ケースを削除する</span><span class="sxs-lookup"><span data-stu-id="7e67d-146">Delete a case</span></span>

<span data-ttu-id="7e67d-147">また、アクティブおよびクローズされたコア電子情報開示ケースを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="7e67d-148">ケースを削除すると、ケース内のすべての検索とエクスポートが削除され、Microsoft 365 コンプライアンスセンターの**コア電子情報開示**ページのケースのリストからケースが削除されます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="7e67d-149">削除したケースを再度開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="7e67d-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="7e67d-150">ケース (アクティブかクローズか) を削除する前に、最初にケースに関連付けられている*すべて*の電子情報保持ホールドを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e67d-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="7e67d-151">これには、状態が**Off**のホールドの削除が含まれます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="7e67d-152">電子情報開示ホールドを削除するには:</span><span class="sxs-lookup"><span data-stu-id="7e67d-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="7e67d-153">削除する場合は、[**保留**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="7e67d-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="7e67d-154">削除するホールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e67d-154">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="7e67d-155">[フライアウト] ページで、[**ホールドの削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e67d-155">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="7e67d-156">ケースを削除するには:</span><span class="sxs-lookup"><span data-stu-id="7e67d-156">To delete a case:</span></span>

1. <span data-ttu-id="7e67d-157">Microsoft 365 コンプライアンスセンターで、[**電子情報開示**コア] をクリックして、  >  **Core**組織内のコア電子情報開示ケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="7e67d-157">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="7e67d-158">削除するケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e67d-158">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="7e67d-159">[ポップアップページの**ケース状態の管理**] で、[ **case の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7e67d-159">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="7e67d-160">削除しようとしているケースに電子情報開示の保留が含まれている場合は、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="7e67d-160">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="7e67d-161">ケースに関連付けられているすべての保留リストを削除してから、ケースを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7e67d-161">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
