---
title: ケースを閉じるか、ケースを削除する
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
description: 高度な電子情報開示ケースでサポートされている調査または訴訟のケースがクローズまたは削除されたときに行われる処理について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e64f5cc0483129396a28cbf657778001e5d372a7
ms.sourcegitcommit: 261d51b90a9ad53a6a42348c414b1b1e1230c37f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "44292413"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="b1c18-103">高度な電子情報開示ケースをクローズまたは削除する</span><span class="sxs-lookup"><span data-stu-id="b1c18-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="b1c18-104">高度な電子情報開示ケースでサポートされている訴訟や調査が完了すると、ケースをクローズまたは削除することができます。</span><span class="sxs-lookup"><span data-stu-id="b1c18-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="b1c18-105">クローズしたケースを再度開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="b1c18-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="b1c18-106">ケースをクローズする</span><span class="sxs-lookup"><span data-stu-id="b1c18-106">Close a case</span></span>

<span data-ttu-id="b1c18-107">高度な電子情報開示ケースをクローズすると、次のような結果になります。</span><span class="sxs-lookup"><span data-stu-id="b1c18-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="b1c18-p102">ケースに保留中の任意のコンテンツの場所が含まれている場合、これらの保留が無効になります。この結果、ユーザーまたは自動プロセス (削除ポリシーなど) によってコンテンツが完全に削除または消去される場合があります。  </span><span class="sxs-lookup"><span data-stu-id="b1c18-p102">If the case contains any content locations on hold, those holds will be turned off. This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="b1c18-110">ケースを閉じるだけで、そのケースに関連付けられている保留がオフになります。</span><span class="sxs-lookup"><span data-stu-id="b1c18-110">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="b1c18-111">他のホールドがコンテンツの場所 (訴訟ホールド、コア電子情報開示の保持、または別の高度な電子情報開示ケースからの保留など) に設定されている場合でも、その保持は保持されます。</span><span class="sxs-lookup"><span data-stu-id="b1c18-111">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="b1c18-112">ケースは、Microsoft 365 コンプライアンスセンターの [電子情報開示] ページに表示されたままになっています。</span><span class="sxs-lookup"><span data-stu-id="b1c18-112">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b1c18-113">クローズしたケースの詳細、保持、検索、メンバーは保持されます。</span><span class="sxs-lookup"><span data-stu-id="b1c18-113">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="b1c18-114">クローズされた case を編集できます。</span><span class="sxs-lookup"><span data-stu-id="b1c18-114">You can edit a case after it's closed.</span></span> <span data-ttu-id="b1c18-115">たとえば、メンバーを追加または削除したり、検索を作成したり、検索結果をエクスポートしたり、高度な電子情報開示で分析のために検索結果を準備したりできます。</span><span class="sxs-lookup"><span data-stu-id="b1c18-115">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="b1c18-116">アクティブなケースとクローズケースの主な違いは、ケースがクローズされたときに保留がオフになっていることです。</span><span class="sxs-lookup"><span data-stu-id="b1c18-116">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="b1c18-117">ケースを閉じるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="b1c18-117">To close a case:</span></span>

1. <span data-ttu-id="b1c18-118">[**高度な電子情報開示**] ページで、クローズするケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1c18-118">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="b1c18-119">[**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1c18-119">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="b1c18-120">[ **Case を閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1c18-120">Click **Close case**.</span></span>

   <span data-ttu-id="b1c18-121">決算プロセスが完了するまでに最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b1c18-121">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="b1c18-122">クローズしたケースを再度開く</span><span class="sxs-lookup"><span data-stu-id="b1c18-122">Reopen a closed case</span></span>

<span data-ttu-id="b1c18-123">高度な電子情報開示ケースを再度開くと、ケースが閉じられたときに行われていた保留リストは自動的に再開されません。</span><span class="sxs-lookup"><span data-stu-id="b1c18-123">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="b1c18-124">ケースを再度開いた後、[**保留**] タブに移動し、前のホールドをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1c18-124">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="b1c18-125">保留リストを有効にするには、それを選択して、フライアウトページを表示した後、**状態**の切り替えを **[オン**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="b1c18-125">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="b1c18-126">クローズしたケースを再度開くには:</span><span class="sxs-lookup"><span data-stu-id="b1c18-126">To reopen a closed case:</span></span>

1. <span data-ttu-id="b1c18-127">[**高度な電子情報開示**] ページで、削除するケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1c18-127">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="b1c18-128">[**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1c18-128">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="b1c18-129">[再**オープンケース**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1c18-129">Click **Reopen case**.</span></span>

   <span data-ttu-id="b1c18-130">再起動プロセスが完了するまでに最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="b1c18-130">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="b1c18-131">ケースを削除する</span><span class="sxs-lookup"><span data-stu-id="b1c18-131">Delete a case</span></span>

<span data-ttu-id="b1c18-132">アクティブおよびクローズされた上級電子情報開示ケースの両方を削除できます。</span><span class="sxs-lookup"><span data-stu-id="b1c18-132">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="b1c18-133">ケースを削除すると、保管担当者、通信、検索、レビューセット、エクスポートジョブのリストなど、ケースに関連付けられているすべてのコンポーネントが削除されます。</span><span class="sxs-lookup"><span data-stu-id="b1c18-133">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="b1c18-134">ケースは、Microsoft 365 コンプライアンスセンターの **[高度な電子情報開示**] ページのケースのリストから削除されています。</span><span class="sxs-lookup"><span data-stu-id="b1c18-134">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b1c18-135">削除したケースを回復したり、再度開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="b1c18-135">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="b1c18-136">データ流出のシナリオでは、レビューセット内のアイテムを削除する唯一の方法は、高度な電子情報開示ケースを削除することです。</span><span class="sxs-lookup"><span data-stu-id="b1c18-136">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="b1c18-137">他の「検索と削除」の方法では、レビューセットからアイテムが削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="b1c18-137">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="b1c18-138">ケース (アクティブかクローズか) を削除するには、まず、ケースに関連付けられている*すべて*の保留リストを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b1c18-138">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="b1c18-139">これには、状態が**Off**のホールドの削除が含まれます。</span><span class="sxs-lookup"><span data-stu-id="b1c18-139">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="b1c18-140">ケースに関連付けられている保留リストを削除するには:</span><span class="sxs-lookup"><span data-stu-id="b1c18-140">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="b1c18-141">削除するアドバンスド電子情報開示ケースの [**保留**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="b1c18-141">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="b1c18-142">削除するホールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1c18-142">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="b1c18-143">[フライアウト] ページで、[**ホールドの削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1c18-143">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="b1c18-144">ケースを削除するには:</span><span class="sxs-lookup"><span data-stu-id="b1c18-144">To delete a case:</span></span>

1. <span data-ttu-id="b1c18-145">[**高度な電子情報開示**] ページで、削除するケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="b1c18-145">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="b1c18-146">[**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1c18-146">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="b1c18-147">[ **Case の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b1c18-147">Click **Delete case**.</span></span>
