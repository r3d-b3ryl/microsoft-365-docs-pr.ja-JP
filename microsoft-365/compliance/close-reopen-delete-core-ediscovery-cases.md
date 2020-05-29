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
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412796"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="95ae3-104">コア電子情報開示ケースのクローズ、再オープン、削除</span><span class="sxs-lookup"><span data-stu-id="95ae3-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="95ae3-105">この記事では、Microsoft 365 でコア電子情報開示ケースをクローズ、再オープン、および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="95ae3-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="95ae3-106">ケースをクローズする</span><span class="sxs-lookup"><span data-stu-id="95ae3-106">Close a case</span></span>

<span data-ttu-id="95ae3-107">コア電子情報開示ケースでサポートされている訴訟や調査が完了したら、ケースを閉じることができます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="95ae3-108">ケースをクローズすると、次のような結果になります。</span><span class="sxs-lookup"><span data-stu-id="95ae3-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="95ae3-109">ケースに電子情報開示の保留になっているコンテンツの場所が含まれている場合、それらの保持はオフになります。</span><span class="sxs-lookup"><span data-stu-id="95ae3-109">If the case contains any content locations on eDiscovery hold, those holds will be turned off.</span></span> <span data-ttu-id="95ae3-110">保留がオフになると、保留中のコンテンツの場所に対して30日間の猶予期間 (*遅延ホールド*と呼ばれます) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="95ae3-111">これにより、コンテンツがすぐに削除されないようにすることができ、遅延保持期間が経過した後にコンテンツを完全に削除できるようにするために、管理者はコンテンツを検索して復元する機会を得ることができます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="95ae3-112">詳細については、「[電子情報開示の保留リストからコンテンツの場所を削除する](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95ae3-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="95ae3-113">ケースを閉じるだけで、そのケースに関連付けられている保留がオフになります。</span><span class="sxs-lookup"><span data-stu-id="95ae3-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="95ae3-114">他のホールドがコンテンツの場所 (訴訟ホールド、保持ポリシー、別のコア電子情報開示ケースの保留など) に設定されている場合でも、その保持は維持されます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="95ae3-115">ケースは、Microsoft 365 コンプライアンスセンターのコア電子情報開示ページに引き続き記載されています。</span><span class="sxs-lookup"><span data-stu-id="95ae3-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="95ae3-116">クローズしたケースの詳細、保持、検索、メンバーは保持されます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="95ae3-117">クローズされた case を編集できます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="95ae3-118">たとえば、メンバーを追加または削除したり、検索を作成したり、検索結果をエクスポートしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-118">For example, you can add or removing members, create searches, and export search results.</span></span> <span data-ttu-id="95ae3-119">アクティブなケースとクローズされたケースの主な違いは、ケースがクローズされたときに電子情報開示の保留がオフになっていることです。</span><span class="sxs-lookup"><span data-stu-id="95ae3-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="95ae3-120">ケースを閉じるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="95ae3-120">To close a case:</span></span>
  
1. <span data-ttu-id="95ae3-121">Microsoft 365 コンプライアンスセンターで、[**電子情報開示**コア] をクリックして、  >  **Core**組織内のコア電子情報開示ケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="95ae3-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="95ae3-122">閉じるケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95ae3-122">Click the name of the case that you want to close.</span></span>

    <span data-ttu-id="95ae3-123">[**このケースを管理**] ポップアップ ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-123">The **Manage this case** flyout page is displayed.</span></span>

3. <span data-ttu-id="95ae3-124">[**ケースの状態の管理**] で、[ **case を閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95ae3-124">Under **Manage case status**, click **Close case**.</span></span>

    <span data-ttu-id="95ae3-125">ケースに関連付けられた保留が無効になることを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="95ae3-126">[**はい**] をクリックしてケースを閉じます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="95ae3-127">[**このケースを管理**] ポップアップ ページの状態が [**アクティブ**] から [**閉じています**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="95ae3-127">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="95ae3-128">[**このケースを管理**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-128">Close the **Manage this case** page.</span></span>

6. <span data-ttu-id="95ae3-129">[**コア電子情報開示**] ページで、[**更新**] をクリックして、クローズされたケースの状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="95ae3-129">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="95ae3-130">決算プロセスが完了するまでに最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="95ae3-130">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="95ae3-131">プロセスが完了すると、そのケースの状態が [**コア電子情報開示**] ページで [**終了**] に変更されます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-131">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span> <span data-ttu-id="95ae3-132">ケースの名前をもう一度クリックして、ケースがクローズされた場合とクローズしたユーザーに関する情報が含まれている [**このケースの管理**] ポップアップページを表示します。</span><span class="sxs-lookup"><span data-stu-id="95ae3-132">Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="95ae3-133">クローズしたケースを再度開く</span><span class="sxs-lookup"><span data-stu-id="95ae3-133">Reopen a closed case</span></span>

<span data-ttu-id="95ae3-134">ケースを再度開くと、ケースが閉じられたときに設定されていた電子情報開示保持は自動的に再開されません。</span><span class="sxs-lookup"><span data-stu-id="95ae3-134">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="95ae3-135">ケースを再度開いた後、**ホールド**ページに移動して、前のホールドをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="95ae3-135">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="95ae3-136">保留リストを有効にするには、それを選択して、フライアウトページを表示した後、**状態**の切り替えを **[オン**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="95ae3-136">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="95ae3-137">Microsoft 365 コンプライアンスセンターで、[**電子情報開示**コア] をクリックして、  >  **Core**組織内のコア電子情報開示ケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="95ae3-137">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="95ae3-138">再度開くケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95ae3-138">Click the name of the case that you want to reopen.</span></span>

    <span data-ttu-id="95ae3-139">[**このケースを管理**] ポップアップ ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-139">The **Manage this case** flyout page is displayed.</span></span> 

3. <span data-ttu-id="95ae3-140">[**ケースの状態を管理する**] で、[**ケースを再度開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95ae3-140">Under **Manage case status**, click **Reopen case**.</span></span>

    <span data-ttu-id="95ae3-141">ケースを閉じたときに関連付けられていた保留は自動的に有効にならないことを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-141">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="95ae3-142">[**はい**] をクリックしてケースを再度開きます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-142">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="95ae3-143">[**このケースを管理**] ポップアップ ページの状態が [**閉じる**] から [**アクティブ**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="95ae3-143">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="95ae3-144">[**このケースを管理**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-144">Close the **Manage this case** page.</span></span> 

6. <span data-ttu-id="95ae3-145">[**コア電子情報開示**] ページで、[**更新**] をクリックして、再度開くケースの状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="95ae3-145">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="95ae3-146">再起動プロセスが完了するまでに最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="95ae3-146">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="95ae3-147">プロセスが完了すると、**コア電子情報開示**ページでケースの状態が [**アクティブ**] に変更されます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-147">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span> 
  
## <a name="delete-a-case"></a><span data-ttu-id="95ae3-148">ケースを削除する</span><span class="sxs-lookup"><span data-stu-id="95ae3-148">Delete a case</span></span>

<span data-ttu-id="95ae3-149">また、アクティブおよびクローズされたコア電子情報開示ケースを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-149">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="95ae3-150">ケースを削除すると、ケース内のすべての検索とエクスポートが削除され、Microsoft 365 コンプライアンスセンターの**コア電子情報開示**ページのケースのリストからケースが削除されます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-150">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="95ae3-151">削除したケースを再度開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="95ae3-151">You can't reopen a deleted case.</span></span>

<span data-ttu-id="95ae3-152">ケース (アクティブかクローズか) を削除する前に、最初にケースに関連付けられている*すべて*の電子情報保持ホールドを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95ae3-152">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="95ae3-153">これには、状態が**Off**のホールドの削除が含まれます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-153">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="95ae3-154">電子情報開示ホールドを削除するには:</span><span class="sxs-lookup"><span data-stu-id="95ae3-154">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="95ae3-155">削除する場合は、[**保留**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="95ae3-155">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="95ae3-156">削除するホールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="95ae3-156">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="95ae3-157">[フライアウト] ページで、[**ホールドの削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95ae3-157">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="95ae3-158">ケースを削除するには:</span><span class="sxs-lookup"><span data-stu-id="95ae3-158">To delete a case:</span></span>

1. <span data-ttu-id="95ae3-159">Microsoft 365 コンプライアンスセンターで、[**電子情報開示**コア] をクリックして、  >  **Core**組織内のコア電子情報開示ケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="95ae3-159">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="95ae3-160">削除するケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95ae3-160">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="95ae3-161">[ポップアップページの**ケース状態の管理**] で、[ **case の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95ae3-161">Under **Manage case status** on the flyout page, click **Delete case**.</span></span>

<span data-ttu-id="95ae3-162">削除しようとしているケースに電子情報開示の保留が含まれている場合は、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95ae3-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="95ae3-163">ケースに関連付けられているすべての保留リストを削除してから、ケースを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95ae3-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
