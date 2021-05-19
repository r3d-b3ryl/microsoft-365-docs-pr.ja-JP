---
title: コア電子情報開示ケースを閉じる、再度開く、削除する
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
description: この記事では、コア電子情報開示ケースを管理する方法について説明します。 これには、ケースの終了、閉じたケースの再オープン、ケースの削除が含まれます。
ms.openlocfilehash: 8a54d5c8f93d36351538bc235a6dbeaaa602c3e9
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532448"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a><span data-ttu-id="c1bc6-104">Core 電子情報開示ケースを閉じる、再度開く、削除する</span><span class="sxs-lookup"><span data-stu-id="c1bc6-104">Close, reopen, and delete a Core eDiscovery case</span></span>

<span data-ttu-id="c1bc6-105">この記事では、電子情報開示のコア ケースを閉じて、再度開き、削除する方法についてMicrosoft 365。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-105">This article describes how to close, reopen, and delete Core eDiscovery cases in Microsoft 365.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="c1bc6-106">ケースを閉じる</span><span class="sxs-lookup"><span data-stu-id="c1bc6-106">Close a case</span></span>

<span data-ttu-id="c1bc6-107">コア電子情報開示ケースでサポートされている法的ケースまたは調査が完了したら、ケースを閉じできます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-107">When the legal case or investigation supported by a Core eDiscovery case is completed, you can close the case.</span></span> <span data-ttu-id="c1bc6-108">ケースを閉じると、次のことが起こります。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-108">Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="c1bc6-109">ケースに電子情報開示ホールドが含まれている場合は、無効になります。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-109">If the case contains any eDiscovery holds, they will be turned off.</span></span> <span data-ttu-id="c1bc6-110">保留がオフになった後、保留状態だったコンテンツの場所に 30 日間の猶予期間 (遅延保留と呼 *ばれる)* が適用されます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-110">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="c1bc6-111">これにより、コンテンツが直ちに削除されるのを防ぎ、遅延保持期間が経過した後にコンテンツを完全に削除する前に、コンテンツを検索して復元する機会を管理者に提供します。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-111">This helps prevent content from being immediately deleted and provides admins the opportunity to search for and restore content before it may be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="c1bc6-112">詳細については、「電子情報開示 [ホールドからコンテンツの場所を削除する」を参照してください](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-112">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="c1bc6-113">ケースを閉じると、そのケースに関連付けられている保留だけが無効になります。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-113">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="c1bc6-114">他の保留リストがコンテンツの場所 (訴訟ホールド、保持ポリシー、または別の Core 電子情報開示ケースからの保留など) に配置されている場合、それらの保持は維持されます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-114">If other holds are placed on a content location (such as a Litigation Hold, a retention policy, or a hold from a different Core eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="c1bc6-115">ケースは、コンプライアンス センターの [コア電子情報開示] ページMicrosoft 365表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-115">The case is still listed on the Core eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="c1bc6-116">詳細、保有、検索、閉じたケースのメンバーは保持されます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-116">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="c1bc6-117">ケースを閉じた後で編集できます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-117">You can edit a case after it's closed.</span></span> <span data-ttu-id="c1bc6-118">たとえば、メンバーの追加または削除、検索の作成、検索結果のエクスポートを行います。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-118">For example, you can add or remove members, create searches, and export search results.</span></span> <span data-ttu-id="c1bc6-119">アクティブなケースと閉じたケースの主な違いは、ケースが閉じているときに電子情報開示ホールドがオフになっている点です。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-119">The primary difference between active and closed cases is that eDiscovery holds are turned off when a case is closed.</span></span>

<span data-ttu-id="c1bc6-120">ケースを閉じるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-120">To close a case:</span></span>
  
1. <span data-ttu-id="c1bc6-121">コンプライアンス センターでMicrosoft 365[**電子** 情報開示コア] をクリックして、組織内のコア電子情報開示ケースの一  >  覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-121">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="c1bc6-122">閉じるケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-122">Click the name of the case that you want to close.</span></span>

   ![ケースのホーム ページでケースを閉じる](../media/eDiscoveryCaseHomePage.png)

3. <span data-ttu-id="c1bc6-124">ホーム ページの [状態] **で、[ケース** を閉じる] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-124">On the home page, under **Status**, click **Close case**.</span></span>

    <span data-ttu-id="c1bc6-125">ケースに関連付けられた保留が無効になることを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-125">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>

4. <span data-ttu-id="c1bc6-126">[**はい**] をクリックしてケースを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-126">Click **Yes** to close the case.</span></span>

    <span data-ttu-id="c1bc6-127">ケース のホーム ページの状態が [アクティブ] から [**閉じる] に\*\*\*\*変更されます**。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-127">The status on the case home page is changed from **Active** to **Closing**.</span></span>

5. <span data-ttu-id="c1bc6-128">[コア電子 **情報開示] ページで** 、[ **更新]** をクリックして、閉じたケースの状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-128">On the **Core eDiscovery** page, click **Refresh** to update the status of the closed case.</span></span> <span data-ttu-id="c1bc6-129">閉じられるには最大で 60 分かかります。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-129">It might take up to 60 minutes for the closing process to complete.</span></span>

    <span data-ttu-id="c1bc6-130">プロセスが完了すると、ケースの状態が [コア電子情報開示] ページ **の [** 閉じた **] に変更** されます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-130">When the process is complete, the status of the case is changed to **Closed** on the **Core eDiscovery** page.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="c1bc6-131">閉じたケースを再度開く</span><span class="sxs-lookup"><span data-stu-id="c1bc6-131">Reopen a closed case</span></span>

<span data-ttu-id="c1bc6-132">ケースを再び開くと、ケースが閉じらされたときに配置された電子情報開示ホールドは自動的には元に戻されません。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-132">When you reopen a case, any eDiscovery holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="c1bc6-133">ケースを再度開いた後、[保留] ページに移動し、前の保留リストをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-133">After the case is reopened, you'll have to go to the **Holds** page and turn on the previous holds.</span></span> <span data-ttu-id="c1bc6-134">保留を有効にするには、選択してポップアップ ページを表示し、[**状態**] を[**On**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-134">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>
  
1. <span data-ttu-id="c1bc6-135">コンプライアンス センターでMicrosoft 365[**電子** 情報開示コア] をクリックして、組織内のコア電子情報開示ケースの一  >  覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-135">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="c1bc6-136">再度開くケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-136">Click the name of the case that you want to reopen.</span></span>

   ![閉じたケースを再度開く](../media/eDiscoveryCaseHomePageReopen.png)

3. <span data-ttu-id="c1bc6-138">ホーム ページの [状態] **で、[ケース** を再度開く] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-138">On the home page, under **Status**, click **Reopen case**.</span></span>

    <span data-ttu-id="c1bc6-139">ケースを閉じたときに関連付けられていた保留は自動的に有効にならないことを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-139">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>

4. <span data-ttu-id="c1bc6-140">[**はい**] をクリックしてケースを再度開きます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-140">Click **Yes** to reopen the case.</span></span>

    <span data-ttu-id="c1bc6-141">ケースのホーム ページ のフライアウト ページの状態が [閉じた] から [**アクティブ] に\*\*\*\*変更されます**。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-141">The status on the case home page flyout page is changed from **Closed** to **Active**.</span></span>

5. <span data-ttu-id="c1bc6-142">[コア電子 **情報開示] ページで** 、[ **更新]** をクリックして、再び開いたケースの状態を更新します。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-142">On the **Core eDiscovery** page, click **Refresh** to update the status of the reopened case.</span></span> <span data-ttu-id="c1bc6-143">再開プロセスが完了するには、最大で 60 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-143">It might take up to 60 minutes for the reopening process to complete.</span></span> 

    <span data-ttu-id="c1bc6-144">プロセスが完了すると、ケースの状態が [コア電子情報開示] ページ **の [アクティブ\*\*\*\*] に変更** されます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-144">When the process is complete, the status of the case is changed to **Active** on the **Core eDiscovery** page.</span></span>

6. <span data-ttu-id="c1bc6-145">(省略可能)再び開いたケースに関連付けられている保留リストを有効にする場合は、[保留] タブに移動し、保留リストを選択し、[保留] フライアウト ページの [状態] の下にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-145">(Optional) To turn on any holds associated with the reopened case, go to **Holds** tab, select a hold, and then select the checkbox under **Status** on the hold flyout page.</span></span>
  
## <a name="delete-a-case"></a><span data-ttu-id="c1bc6-146">ケースの削除</span><span class="sxs-lookup"><span data-stu-id="c1bc6-146">Delete a case</span></span>

<span data-ttu-id="c1bc6-147">アクティブな電子情報開示ケースと閉じたコア電子情報開示ケースを削除できます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-147">You can also delete active and closed Core eDiscovery cases.</span></span> <span data-ttu-id="c1bc6-148">ケースを削除すると、ケース内のすべての検索とエクスポートが削除され、ケースは Microsoft 365 コンプライアンス センターの [コア電子情報開示] ページのケースの一覧から削除されます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-148">When you delete a case, all searches and exports in the case are deleted, and the case is removed from the list of cases on the **Core eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="c1bc6-149">削除されたケースを再度開く事はできない。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-149">You can't reopen a deleted case.</span></span>

<span data-ttu-id="c1bc6-150">ケースを削除する前に (ケースがアクティブか閉じているか)、最初にケースに関連付 *けられているすべての電子* 情報開示ホールドを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-150">Before you can delete a case (whether it's active or closed), you must first delete *all* eDiscovery holds associated with the case.</span></span> <span data-ttu-id="c1bc6-151">これには、状態が Off の保留リストの削除が含 **まれます**。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-151">That includes deleting holds with a status of **Off**.</span></span> 

<span data-ttu-id="c1bc6-152">電子情報開示ホールドを削除するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-152">To delete an eDiscovery hold:</span></span>

1. <span data-ttu-id="c1bc6-153">削除 **する場合** は、[保持] タブを移動します。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-153">Go the **Holds** tab in the case that you want to delete.</span></span>

2. <span data-ttu-id="c1bc6-154">削除する保留リストを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-154">Select the hold that you want to delete.</span></span>

3. <span data-ttu-id="c1bc6-155">[フライアウト] ページで、[削除] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-155">On the flyout page, click **Delete**.</span></span>

      ![電子情報開示ホールドの削除](../media/DeleteeDiscoveryHold.png)

<span data-ttu-id="c1bc6-157">ケースを削除する方法は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-157">To delete a case:</span></span>

1. <span data-ttu-id="c1bc6-158">コンプライアンス センターでMicrosoft 365[**電子** 情報開示コア] をクリックして、組織内のコア電子情報開示ケースの一  >  覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-158">In the Microsoft 365 compliance center, click **eDiscovery** > **Core** to display the list of Core eDiscovery cases in your organization.</span></span>

2. <span data-ttu-id="c1bc6-159">削除するケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-159">Click the name of the case that you want to delete.</span></span>

3. <span data-ttu-id="c1bc6-160">ケース ホーム ページの [状態] **で、[ケース** の削除] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-160">On the case home page, under **Status**, click **Delete case**.</span></span>

      ![ケースの削除](../media/eDiscoveryCaseHomePageDelete.png)

<span data-ttu-id="c1bc6-162">削除しようとしているケースに電子情報開示ホールドがまだ含まれている場合は、エラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-162">If the case you're trying to delete still contains eDiscovery holds, you'll receive an error message.</span></span> <span data-ttu-id="c1bc6-163">ケースに関連付けられているすべての保留リストを削除してから、もう一度ケースを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1bc6-163">You'll have to delete all holds associated with the case and then try again to delete the case.</span></span>
