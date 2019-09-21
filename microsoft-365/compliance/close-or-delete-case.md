---
title: ケースを閉じるか、ケースを削除する
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
description: ''
ms.openlocfilehash: 30697bfafdd7db69444b97345733f3d8ec5be92a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2019
ms.locfileid: "37085443"
---
# <a name="close-or-delete-a-case"></a><span data-ttu-id="094ed-102">ケースを閉じるか、ケースを削除する</span><span class="sxs-lookup"><span data-stu-id="094ed-102">Close or delete a case</span></span>

<span data-ttu-id="094ed-p101">電子情報開示ケースでサポートされる訴訟や捜査が完了したら、ケースを閉じることができます。ケースを閉じたときの動作を示します。</span><span class="sxs-lookup"><span data-stu-id="094ed-p101">When the legal case or investigation supported by an eDiscovery case is completed, you can close the case. Here's what happens when you close a case:</span></span>

- <span data-ttu-id="094ed-p102">ケースに保留中の任意のコンテンツの場所が含まれている場合、これらの保留が無効になります。この結果、ユーザーまたは自動プロセス (削除ポリシーなど) によってコンテンツが完全に削除または消去される場合があります。  </span><span class="sxs-lookup"><span data-stu-id="094ed-p102">If the case contains any content locations on hold, those holds will be turned off. This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="094ed-p103">ケースを閉じると、そのケースに関連付けられている保留だけが無効になります。コンテンツの場所に他の保留 (訴訟ホールド、保持ポリシー、別の電子情報開示ケースからの保留など) がある場合、これらの保留はそのまま保持されます。</span><span class="sxs-lookup"><span data-stu-id="094ed-p103">Closing a case only turns off the holds that are associated with that case. If other holds are place on a content location (such as a Litigation Hold. a Preservation Policy, or a hold from a different eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="094ed-110">ケースは、セキュリティ & コンプライアンスセンターの [電子情報開示] ページに表示されたままになっています。</span><span class="sxs-lookup"><span data-stu-id="094ed-110">The case is still listed on the eDiscovery page in the Security & Compliance Center.</span></span> <span data-ttu-id="094ed-111">クローズしたケースの詳細、保持、検索、メンバーは保持されます。</span><span class="sxs-lookup"><span data-stu-id="094ed-111">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="094ed-p105">ケースは閉じた後でも編集できます。たとえば、メンバーの追加または削除、検索の作成、検索結果のエクスポート、Advanced eDiscovery で分析するための検索結果の準備が行えます。アクティブ ケースと閉じたケースの主な違いは、ケースを閉じると保留が無効になることです。</span><span class="sxs-lookup"><span data-stu-id="094ed-p105">You can edit a case after it's closed. For example, you can add or removing members, create searches, export search results, and prepare search result for analysis in Advanced eDiscovery. The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="094ed-115">ケースを閉じるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="094ed-115">To close a case:</span></span>

1. <span data-ttu-id="094ed-116">**[高度な電子情報開示**] ページで、ケースに移動します。</span><span class="sxs-lookup"><span data-stu-id="094ed-116">From the **Advanced eDiscovery** page, go to your case.</span></span>

2. <span data-ttu-id="094ed-117">[**設定**] に移動し、[**ケース情報**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="094ed-117">Go to **Settings** and select **Case Information**.</span></span> 

3. <span data-ttu-id="094ed-118">[ **Case を閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="094ed-118">Click **Close Case**.</span></span> 

<span data-ttu-id="094ed-119">ケースを削除するには:</span><span class="sxs-lookup"><span data-stu-id="094ed-119">To delete a case:</span></span>

1. <span data-ttu-id="094ed-120">**[高度な電子情報開示**] ページで、ケースに移動します。</span><span class="sxs-lookup"><span data-stu-id="094ed-120">From the **Advanced eDiscovery** page, go to your case.</span></span>

2. <span data-ttu-id="094ed-121">[**設定**] に移動し、[**ケース情報**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="094ed-121">Go to **Settings** and select **Case Information**.</span></span> 

3. <span data-ttu-id="094ed-122">[ **Case の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="094ed-122">Click **Delete Case**.</span></span> 
