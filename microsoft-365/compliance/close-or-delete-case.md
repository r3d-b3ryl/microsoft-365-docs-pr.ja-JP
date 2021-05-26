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
ms.openlocfilehash: 7b11faa2ccdb44fca916b2f602d5120adadf1739
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657653"
---
# <a name="close-or-delete-an-advanced-ediscovery-case"></a><span data-ttu-id="e82a7-103">ケースを閉じるAdvanced eDiscovery削除する</span><span class="sxs-lookup"><span data-stu-id="e82a7-103">Close or delete an Advanced eDiscovery case</span></span>

<span data-ttu-id="e82a7-104">ケースがサポートする法的ケースまたは調査Advanced eDiscovery、ケースを閉じるか削除できます。</span><span class="sxs-lookup"><span data-stu-id="e82a7-104">When the legal case or investigation supported by an Advanced eDiscovery case is completed, you can close or delete a case.</span></span> <span data-ttu-id="e82a7-105">閉じたケースを再度開く方法も可能です。</span><span class="sxs-lookup"><span data-stu-id="e82a7-105">You can also reopen a closed case.</span></span>

## <a name="close-a-case"></a><span data-ttu-id="e82a7-106">ケースを閉じる</span><span class="sxs-lookup"><span data-stu-id="e82a7-106">Close a case</span></span>

<span data-ttu-id="e82a7-107">ケースを閉じると、次Advanced eDiscoveryされます。</span><span class="sxs-lookup"><span data-stu-id="e82a7-107">Here's what happens when you close an Advanced eDiscovery case:</span></span>

- <span data-ttu-id="e82a7-108">ケースに保留されているコンテンツの場所が含まれている場合、それらの保留は無効になります。</span><span class="sxs-lookup"><span data-stu-id="e82a7-108">If the case contains any content locations on hold, those holds will be turned off.</span></span> <span data-ttu-id="e82a7-109">保留がオフになった後、保留状態だったコンテンツの場所に 30 日間の猶予期間 (遅延保留と呼 *ばれる)* が適用されます。</span><span class="sxs-lookup"><span data-stu-id="e82a7-109">After the hold is turned off, a 30-day grace period (called a *delay hold*) is applied to content locations that were on hold.</span></span> <span data-ttu-id="e82a7-110">これにより、コンテンツが直ちに削除されるのを防ぎ、遅延保持期間が経過した後に完全に削除されるコンテンツを検索または回復する機会が管理者に与えます。</span><span class="sxs-lookup"><span data-stu-id="e82a7-110">This helps prevent content from being immediately deleted and gives admins an opportunity to search for or recover content that will be permanently deleted after the delay hold period expires.</span></span> <span data-ttu-id="e82a7-111">詳細については、「電子情報開示 [ホールドからコンテンツの場所を削除する」を参照してください](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold)。</span><span class="sxs-lookup"><span data-stu-id="e82a7-111">For more information, see [Removing content locations from an eDiscovery hold](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).</span></span>

- <span data-ttu-id="e82a7-112">ケースを閉じると、そのケースに関連付けられている保留だけが無効になります。</span><span class="sxs-lookup"><span data-stu-id="e82a7-112">Closing a case only turns off the holds that are associated with that case.</span></span> <span data-ttu-id="e82a7-113">他の保留リストがコンテンツの場所 (訴訟ホールド、コア電子情報開示ホールド、または別の Advanced eDiscovery ケースからの保留など) に配置されている場合、それらの保持は維持されます。</span><span class="sxs-lookup"><span data-stu-id="e82a7-113">If other holds are place on a content location (such as a Litigation Hold, Core eDiscovery hold, or a hold from a different Advanced eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="e82a7-114">ケースは、コンプライアンス センターの電子情報開示ページMicrosoft 365されます。</span><span class="sxs-lookup"><span data-stu-id="e82a7-114">The case is still listed on the eDiscovery page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e82a7-115">詳細、保有、検索、閉じたケースのメンバーは保持されます。</span><span class="sxs-lookup"><span data-stu-id="e82a7-115">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="e82a7-116">ケースを閉じた後で編集できます。</span><span class="sxs-lookup"><span data-stu-id="e82a7-116">You can edit a case after it's closed.</span></span> <span data-ttu-id="e82a7-117">たとえば、メンバーの追加または削除、検索の作成、検索結果のエクスポート、分析用の検索結果の準備を行Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="e82a7-117">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="e82a7-118">アクティブ ケースと閉じたケースの主な違いは、ケースを閉じると保留が無効になることです。</span><span class="sxs-lookup"><span data-stu-id="e82a7-118">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="e82a7-119">ケースを閉じるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="e82a7-119">To close a case:</span></span>

1. <span data-ttu-id="e82a7-120">**Advanced eDiscovery** ページで、閉じたいケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="e82a7-120">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="e82a7-121">[**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e82a7-121">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="e82a7-122">[ケース情報] フライアウト **ページ** の下部で、[( ... ) を **クリックします。\*\*\*\*[その他のオプション**] をクリックし、[ケースを **閉じる] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e82a7-122">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Close case**.</span></span>

   ![[その他のオプション] メニューのオプションを使用してケースAdvanced eDiscoveryします。](..\Media\CloseAdvancedeDiscoveryCase.png)

   <span data-ttu-id="e82a7-124">閉じられるには最大で 60 分かかります。</span><span class="sxs-lookup"><span data-stu-id="e82a7-124">It might take up to 60 minutes for the closing process to complete.</span></span>

## <a name="reopen-a-closed-case"></a><span data-ttu-id="e82a7-125">閉じたケースを再度開く</span><span class="sxs-lookup"><span data-stu-id="e82a7-125">Reopen a closed case</span></span>

<span data-ttu-id="e82a7-126">ケースを再度開Advanced eDiscovery、ケースを閉じたときに保持されたホールドは自動的には元に戻されません。</span><span class="sxs-lookup"><span data-stu-id="e82a7-126">When you reopen an Advanced eDiscovery case, any holds that were in place when the case was closed won't be automatically reinstated.</span></span> <span data-ttu-id="e82a7-127">ケースを再度開いた後、[保留] タブに移動し、前の保留をオンにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e82a7-127">After the case is reopened, you'll have to go to the **Holds** tab and turn on the previous holds.</span></span> <span data-ttu-id="e82a7-128">保留を有効にするには、選択してポップアップ ページを表示し、[**状態**] を[**On**] に切り替えます。</span><span class="sxs-lookup"><span data-stu-id="e82a7-128">To turn on a hold, select it to display the flyout page, and then set the **Status** toggle to **On**.</span></span>

<span data-ttu-id="e82a7-129">閉じたケースを再度開く方法は次の通り。</span><span class="sxs-lookup"><span data-stu-id="e82a7-129">To reopen a closed case:</span></span>

1. <span data-ttu-id="e82a7-130">**Advanced eDiscovery** ページで、再び開きたいケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="e82a7-130">On the **Advanced eDiscovery** page, select the case that you want to reopen.</span></span>

2. <span data-ttu-id="e82a7-131">[**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e82a7-131">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="e82a7-132">[ケース情報] フライアウト **ページ** の下部で、[( ... ) を **クリックします。\*\*\*\*その他のオプション** を選択し、[大文字と小文字を **再度開く] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e82a7-132">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Reopen case**.</span></span>

   ![[その他のオプション] メニューのオプションを使用して、Advanced eDiscoveryします。](..\Media\ReopenAdvancedeDiscoveryCase.png)

   <span data-ttu-id="e82a7-134">再開プロセスが完了するには、最大で 60 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e82a7-134">It might take up to 60 minutes for the reopening process to complete.</span></span>

## <a name="delete-a-case"></a><span data-ttu-id="e82a7-135">ケースの削除</span><span class="sxs-lookup"><span data-stu-id="e82a7-135">Delete a case</span></span>

<span data-ttu-id="e82a7-136">アクティブなケースと閉じているケースの両方をAdvanced eDiscoveryできます。</span><span class="sxs-lookup"><span data-stu-id="e82a7-136">You can delete both active and closed Advanced eDiscovery cases.</span></span> <span data-ttu-id="e82a7-137">ケースを削除すると、カストディアンのリスト、通信、検索、レビュー セット、エクスポート ジョブなど、そのケースに関連付けられているすべてのコンポーネントが削除されます。</span><span class="sxs-lookup"><span data-stu-id="e82a7-137">When you delete a case, all components associated with the case, such as the list of custodians, communications, searches, review sets, and export job are deleted.</span></span> <span data-ttu-id="e82a7-138">ケースは、コンプライアンス センターの [Advanced eDiscovery]ページMicrosoft 365削除されます。</span><span class="sxs-lookup"><span data-stu-id="e82a7-138">The case is removed from the list of cases on the **Advanced eDiscovery** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="e82a7-139">削除されたケースを回復または再び開く方法は使用できません。</span><span class="sxs-lookup"><span data-stu-id="e82a7-139">You can't recover or reopen a deleted case.</span></span>

> [!NOTE]
> <span data-ttu-id="e82a7-140">データ流出のシナリオでは、レビュー セット内のアイテムを削除する唯一の方法は、Advanced eDiscoveryすることです。</span><span class="sxs-lookup"><span data-stu-id="e82a7-140">In data spillage scenarios, the only way to remove items in a review set is to delete the Advanced eDiscovery case.</span></span> <span data-ttu-id="e82a7-141">他の "検索と削除" メソッドでは、レビュー セットからアイテムを削除しない。</span><span class="sxs-lookup"><span data-stu-id="e82a7-141">Other "search and purge" methods don't remove items from a review set.</span></span>

<span data-ttu-id="e82a7-142">ケースを削除する前に (アクティブまたはクローズの場合)、ケースに関連付けられているすべての保留リストを最初に削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e82a7-142">Before you can delete a case (whether it's active or closed), you must first delete *all* holds associated with the case.</span></span> <span data-ttu-id="e82a7-143">これには、状態が Off の保留リストの削除が含 **まれます**。</span><span class="sxs-lookup"><span data-stu-id="e82a7-143">That includes deleting holds with a status of **Off**.</span></span>

<span data-ttu-id="e82a7-144">ケースに関連付けられている保留リストを削除するには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="e82a7-144">To delete holds associated with a case:</span></span>

1. <span data-ttu-id="e82a7-145">削除 **する場合** は、Advanced eDiscoveryタブに移動します。</span><span class="sxs-lookup"><span data-stu-id="e82a7-145">Go the **Holds** tab in the Advanced eDiscovery case that you want to delete.</span></span>

2. <span data-ttu-id="e82a7-146">削除する保留リストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e82a7-146">Click the hold that you want to delete.</span></span>

3. <span data-ttu-id="e82a7-147">[フライアウト] ページで、[保留リストの削除] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e82a7-147">On the flyout page, click **Delete hold**.</span></span>

<span data-ttu-id="e82a7-148">ケースを削除する方法は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e82a7-148">To delete a case:</span></span>

1. <span data-ttu-id="e82a7-149">**Advanced eDiscovery** ページで、削除したいケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="e82a7-149">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="e82a7-150">[**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e82a7-150">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="e82a7-151">[ケース情報] フライアウト **ページ** の下部で、[( ... ) を **クリックします。\*\*\*\*[その他のオプション**] をクリックし、[大文字と小文字 **の削除] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="e82a7-151">At the bottom of the **Case Information** flyout page, click (**...**) **More options**, and then click **Delete case**.</span></span>

   ![[その他のオプション] メニューのオプションで、大文字と小文字をAdvanced eDiscoveryする](..\Media\DeleteAdvancedeDiscoveryCase.png)
