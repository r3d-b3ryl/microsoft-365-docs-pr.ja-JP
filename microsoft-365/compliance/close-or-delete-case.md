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
ms.openlocfilehash: ffdd93351325be0c4b5d6d8cdfb78e55b710c0be
ms.sourcegitcommit: 6746fae2f68400fd985711b1945b66766d2a59a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2020
ms.locfileid: "44419063"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="dc664-103">高度な電子情報開示ケースをクローズまたは削除する</span><span class="sxs-lookup"><span data-stu-id="dc664-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="dc664-104">高度な電子情報開示ケースでサポートされている訴訟や調査が完了すると、ケースをクローズまたは削除することができます。</span><span class="sxs-lookup"><span data-stu-id="dc664-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="dc664-105">クローズしたケースを再度開くこともできます。</span><span class="sxs-lookup"><span data-stu-id="dc664-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="dc664-106">ケースをクローズする</span><span class="sxs-lookup"><span data-stu-id="dc664-106">Close a case</span></span>

<span data-ttu-id="dc664-107">高度な電子情報開示ケースをクローズすると、次のような結果になります。</span><span class="sxs-lookup"><span data-stu-id="dc664-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="dc664-108">ケースに、保留中のコンテンツの場所が含まれている場合は、それらの保持がオフになります。</span><span class="sxs-lookup"><span data-stu-id="dc664-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="dc664-109">保留がオフになると、保留中のコンテンツの場所に対して30日間の猶予期間 (*遅延ホールド*と呼ばれます) が適用されます。</span><span class="sxs-lookup"><span data-stu-id="dc664-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="dc664-110">これにより、コンテンツがすぐに削除されないようにすることができ、遅延保持期間が経過した後に完全に削除されるコンテンツを検索したり、復元したりする機会を管理者に与えることができます。</span><span class="sxs-lookup"><span data-stu-id="dc664-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="dc664-111">詳細については、「[電子情報開示の保留リストからコンテンツの場所を削除する](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dc664-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="dc664-112">ケースを閉じるだけで、そのケースに関連付けられている保留がオフになります。</span><span class="sxs-lookup"><span data-stu-id="dc664-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="dc664-113">他のホールドがコンテンツの場所 (訴訟ホールド、コア電子情報開示の保持、または別の高度な電子情報開示ケースからの保留など) に設定されている場合でも、その保持は保持されます。</span><span class="sxs-lookup"><span data-stu-id="dc664-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="dc664-114">ケースは、Microsoft 365 コンプライアンスセンターの [電子情報開示] ページに表示されたままになっています。</span><span class="sxs-lookup"><span data-stu-id="dc664-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="dc664-115">クローズしたケースの詳細、保持、検索、メンバーは保持されます。</span><span class="sxs-lookup"><span data-stu-id="dc664-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="dc664-116">クローズされた case を編集できます。</span><span class="sxs-lookup"><span data-stu-id="dc664-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="dc664-117">たとえば、メンバーを追加または削除したり、検索を作成したり、検索結果をエクスポートしたり、高度な電子情報開示で分析のために検索結果を準備したりできます。</span><span class="sxs-lookup"><span data-stu-id="dc664-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="dc664-118">アクティブなケースとクローズケースの主な違いは、ケースがクローズされたときに保留がオフになっていることです。</span><span class="sxs-lookup"><span data-stu-id="dc664-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="dc664-119">ケースを閉じるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="dc664-119">To close a case:</span></span>

1. <span data-ttu-id="dc664-120">[**高度な電子情報開示**] ページで、クローズするケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc664-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="dc664-121">[**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc664-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="dc664-122">[ **Case を閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc664-122">Click **Close case**.</span></span>

   <span data-ttu-id="dc664-123">決算プロセスが完了するまでに最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dc664-123">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="dc664-124">クローズしたケースを再度開く</span><span class="sxs-lookup"><span data-stu-id="dc664-124">Reopen a closed case</span></span>

<span data-ttu-id="dc664-125">高度な電子情報開示ケースを再度開くと、ケースが閉じられたときに行われていた保留リストは自動的に再開されません。</span><span class="sxs-lookup"><span data-stu-id="dc664-125">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="dc664-126">ケースを再度開いた後、[**保留**] タブに移動し、前のホールドをオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc664-126">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="dc664-127">保留リストを有効にするには、それを選択して、フライアウトページを表示した後、**状態**の切り替えを **[オン**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="dc664-127">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="dc664-128">クローズしたケースを再度開くには:</span><span class="sxs-lookup"><span data-stu-id="dc664-128">To reopen a closed case:</span></span>

1. <span data-ttu-id="dc664-129">[**高度な電子情報開示**] ページで、再開するケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc664-129">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="dc664-130">[**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc664-130">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="dc664-131">[再**オープンケース**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc664-131">Click **Reopen case**.</span></span>

   <span data-ttu-id="dc664-132">再起動プロセスが完了するまでに最大60分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dc664-132">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="dc664-133">ケースを削除する</span><span class="sxs-lookup"><span data-stu-id="dc664-133">Delete a case</span></span>

<span data-ttu-id="dc664-134">アクティブおよびクローズされた上級電子情報開示ケースの両方を削除できます。</span><span class="sxs-lookup"><span data-stu-id="dc664-134">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="dc664-135">ケースを削除すると、保管担当者、通信、検索、レビューセット、エクスポートジョブのリストなど、ケースに関連付けられているすべてのコンポーネントが削除されます。</span><span class="sxs-lookup"><span data-stu-id="dc664-135">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="dc664-136">ケースは、Microsoft 365 コンプライアンスセンターの **[高度な電子情報開示**] ページのケースのリストから削除されています。</span><span class="sxs-lookup"><span data-stu-id="dc664-136">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="dc664-137">削除したケースを回復したり、再度開くことはできません。</span><span class="sxs-lookup"><span data-stu-id="dc664-137">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="dc664-138">データ流出のシナリオでは、レビューセット内のアイテムを削除する唯一の方法は、高度な電子情報開示ケースを削除することです。</span><span class="sxs-lookup"><span data-stu-id="dc664-138">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="dc664-139">他の「検索と削除」の方法では、レビューセットからアイテムが削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="dc664-139">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="dc664-140">ケース (アクティブかクローズか) を削除するには、まず、ケースに関連付けられている*すべて*の保留リストを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc664-140">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="dc664-141">これには、状態が**Off**のホールドの削除が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dc664-141">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="dc664-142">ケースに関連付けられている保留リストを削除するには:</span><span class="sxs-lookup"><span data-stu-id="dc664-142">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="dc664-143">削除するアドバンスド電子情報開示ケースの [**保留**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="dc664-143">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="dc664-144">削除するホールドをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc664-144">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="dc664-145">[フライアウト] ページで、[**ホールドの削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc664-145">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="dc664-146">ケースを削除するには:</span><span class="sxs-lookup"><span data-stu-id="dc664-146">To delete a case:</span></span>

1. <span data-ttu-id="dc664-147">[**高度な電子情報開示**] ページで、削除するケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="dc664-147">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="dc664-148">[**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc664-148">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="dc664-149">[ **Case の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc664-149">Click **Delete case**.</span></span>
