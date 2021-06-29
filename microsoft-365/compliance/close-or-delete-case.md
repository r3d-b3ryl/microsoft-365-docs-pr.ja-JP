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
description: ケースが閉じたり削除された場合に、調査または法的ケースがサポートAdvanced eDiscoveryどうなるかを確認します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: efbcbe34e6d7d8b564bcfa0cf9bbd8a1fbb59709
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194634"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="14b8e-103">ケースを閉じるAdvanced eDiscovery削除する</span><span class="sxs-lookup"><span data-stu-id="14b8e-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="14b8e-104">ケースがサポートする法的ケースまたは調査Advanced eDiscovery、ケースを閉じるか削除できます。</span><span class="sxs-lookup"><span data-stu-id="14b8e-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="14b8e-105">閉じたケースを再度開く方法も可能です。</span><span class="sxs-lookup"><span data-stu-id="14b8e-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="14b8e-106">ケースを閉じる</span><span class="sxs-lookup"><span data-stu-id="14b8e-106">Close a case</span></span>

<span data-ttu-id="14b8e-107">ケースを閉じると、次Advanced eDiscoveryされます。</span><span class="sxs-lookup"><span data-stu-id="14b8e-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="14b8e-108">ケースに保留されているコンテンツの場所が含まれている場合、それらの保留は無効になります。</span><span class="sxs-lookup"><span data-stu-id="14b8e-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="14b8e-109">保留がオフになった後、保留状態だったコンテンツの場所に 30 日間の猶予期間 (遅延保留と呼 *ばれる)* が適用されます。</span><span class="sxs-lookup"><span data-stu-id="14b8e-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="14b8e-110">これにより、コンテンツが直ちに削除されるのを防ぎ、遅延保持期間が経過した後に完全に削除されるコンテンツを検索または回復する機会が管理者に与えます。</span><span class="sxs-lookup"><span data-stu-id="14b8e-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="14b8e-111">詳細については、「電子情報開示 [ホールドからコンテンツの場所を削除する」を参照してください](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)。</span><span class="sxs-lookup"><span data-stu-id="14b8e-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="14b8e-112">ケースを閉じると、そのケースに関連付けられている保留だけが無効になります。</span><span class="sxs-lookup"><span data-stu-id="14b8e-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="14b8e-113">他の保留リストがコンテンツの場所 (訴訟ホールド、コア電子情報開示ホールド、または別の Advanced eDiscovery ケースからの保留など) に配置されている場合、それらの保持は維持されます。</span><span class="sxs-lookup"><span data-stu-id="14b8e-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="14b8e-114">ケースは、このページの [電子情報開示] ページに引き続きMicrosoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="14b8e-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="14b8e-115">詳細、保有、検索、閉じたケースのメンバーは保持されます。</span><span class="sxs-lookup"><span data-stu-id="14b8e-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="14b8e-116">ケースを閉じた後で編集できます。</span><span class="sxs-lookup"><span data-stu-id="14b8e-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="14b8e-117">たとえば、メンバーの追加または削除、検索の作成、検索結果のエクスポート、分析用の検索結果の準備を行Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="14b8e-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="14b8e-118">アクティブ ケースと閉じたケースの主な違いは、ケースを閉じると保留が無効になることです。</span><span class="sxs-lookup"><span data-stu-id="14b8e-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="14b8e-119">ケースを閉じるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="14b8e-119">To close a case:</span></span>

1. <span data-ttu-id="14b8e-120">**Advanced eDiscovery** ページで、閉じたいケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="14b8e-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="14b8e-121">[**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14b8e-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

   ![ケースのケース情報のフライアウト ページにアクセスAdvanced eDiscoveryする](..\media\AeDSelectCaseInformation.png) 

3. <span data-ttu-id="14b8e-123">[ケース情報] フライアウト ページ **の** 下部にある[アクション] をクリックし、[ケースを閉じる]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="14b8e-123">At the bottom of the **Case Information** flyout page, click **Actions**, and then click **Close case**.</span></span>

   <span data-ttu-id="14b8e-124">閉じられるには最大で 60 分かかります。</span><span class="sxs-lookup"><span data-stu-id="14b8e-124">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="14b8e-125">閉じたケースを再度開く</span><span class="sxs-lookup"><span data-stu-id="14b8e-125">Reopen a closed case</span></span>

<span data-ttu-id="14b8e-126">ケースを再度開Advanced eDiscovery、ケースを閉じたときに保持されたホールドは自動的には元に戻されません。</span><span class="sxs-lookup"><span data-stu-id="14b8e-126">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="14b8e-127">ケースを再度開いた後、[保留] タブに移動し、前の保留をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="14b8e-127">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="14b8e-128">保留を有効にするには、選択してポップアップ ページを表示し、[**状態**] を[**On**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="14b8e-128">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="14b8e-129">閉じたケースを再度開く方法は次の通り。</span><span class="sxs-lookup"><span data-stu-id="14b8e-129">To reopen a closed case:</span></span>

1. <span data-ttu-id="14b8e-130">**Advanced eDiscovery** ページで、再び開きたいケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="14b8e-130">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="14b8e-131">[**設定**] タブの [**ケース情報**] の下で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14b8e-131">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="14b8e-132">[ケース情報] フライアウト **ページの** 下部にある[アクション] をクリックし、[ケースを再度開く]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="14b8e-132">At the bottom of the **Case Information** flyout page, click **Actions**, and then click **Reopen case**.</span></span>

   <span data-ttu-id="14b8e-133">再開プロセスが完了するには、最大で 60 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="14b8e-133">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="14b8e-134">ケースの削除</span><span class="sxs-lookup"><span data-stu-id="14b8e-134">Delete a case</span></span>

<span data-ttu-id="14b8e-135">アクティブなケースと閉じているケースの両方をAdvanced eDiscoveryできます。</span><span class="sxs-lookup"><span data-stu-id="14b8e-135">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="14b8e-136">ケースを削除すると、カストディアンのリスト、通信、検索、レビュー セット、エクスポート ジョブなど、そのケースに関連付けられているすべてのコンポーネントが削除されます。</span><span class="sxs-lookup"><span data-stu-id="14b8e-136">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="14b8e-137">ケースは、このページの [Advanced eDiscovery] ページのケースの一覧から削除Microsoft 365 コンプライアンス センター。</span><span class="sxs-lookup"><span data-stu-id="14b8e-137">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="14b8e-138">削除されたケースを回復または再び開く方法は使用できません。</span><span class="sxs-lookup"><span data-stu-id="14b8e-138">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="14b8e-139">データ流出のシナリオでは、レビュー セット内のアイテムを削除する唯一の方法は、Advanced eDiscoveryすることです。</span><span class="sxs-lookup"><span data-stu-id="14b8e-139">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="14b8e-140">他の "検索と削除" メソッドでは、レビュー セットからアイテムを削除しない。</span><span class="sxs-lookup"><span data-stu-id="14b8e-140">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="14b8e-141">ケースを削除する前に (アクティブまたはクローズの場合)、ケースに関連付けられているすべての保留リストを最初に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14b8e-141">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="14b8e-142">これには、状態が Off の保留リストの削除が含 **まれます**。</span><span class="sxs-lookup"><span data-stu-id="14b8e-142">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="14b8e-143">ケースに関連付けられている保留リストを削除するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="14b8e-143">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="14b8e-144">削除 **する場合** は、Advanced eDiscoveryタブに移動します。</span><span class="sxs-lookup"><span data-stu-id="14b8e-144">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="14b8e-145">削除する保留リストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="14b8e-145">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="14b8e-146">[フライアウト] ページで、[保留リストの削除] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="14b8e-146">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="14b8e-147">ケースを削除する方法は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="14b8e-147">To delete a case:</span></span>

1. <span data-ttu-id="14b8e-148">**Advanced eDiscovery** ページで、削除したいケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="14b8e-148">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="14b8e-149">[**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="14b8e-149">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="14b8e-150">[ケース情報] フライアウト ページ **の** 下部にある[アクション] をクリックし、[ケースの削除]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="14b8e-150">At the bottom of the **Case Information** flyout page, click **Actions**, and then click **Delete case**.</span></span>

