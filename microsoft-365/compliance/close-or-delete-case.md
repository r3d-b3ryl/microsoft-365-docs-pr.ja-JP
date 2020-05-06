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
description: 電子情報開示ケースでサポートされている調査または訴訟のケースがクローズまたは削除されたときに行われる処理について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f91755e6d2aeba89e795a623cd1268af0a53e675
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035639"
---
# <a name="close-or-delete-a-case"></a><span data-ttu-id="963bd-103">ケースを閉じるか、ケースを削除する</span><span class="sxs-lookup"><span data-stu-id="963bd-103">Close or delete a case</span></span>

<span data-ttu-id="963bd-p101">電子情報開示ケースでサポートされる訴訟や捜査が完了したら、ケースを閉じることができます。ケースを閉じたときの動作を示します。</span><span class="sxs-lookup"><span data-stu-id="963bd-p101">When the legal case or investigation supported by an eDiscovery case is completed, you can close the case. Here's what happens when you close a case:</span></span>

- <span data-ttu-id="963bd-p102">ケースに保留中の任意のコンテンツの場所が含まれている場合、これらの保留が無効になります。この結果、ユーザーまたは自動プロセス (削除ポリシーなど) によってコンテンツが完全に削除または消去される場合があります。  </span><span class="sxs-lookup"><span data-stu-id="963bd-p102">If the case contains any content locations on hold, those holds will be turned off. This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>

- <span data-ttu-id="963bd-p103">ケースを閉じると、そのケースに関連付けられている保留だけが無効になります。コンテンツの場所に他の保留 (訴訟ホールド、保持ポリシー、別の電子情報開示ケースからの保留など) がある場合、これらの保留はそのまま保持されます。</span><span class="sxs-lookup"><span data-stu-id="963bd-p103">Closing a case only turns off the holds that are associated with that case. If other holds are place on a content location (such as a Litigation Hold. a Preservation Policy, or a hold from a different eDiscovery case) those holds will still be maintained.</span></span>

- <span data-ttu-id="963bd-111">ケースは、セキュリティ & コンプライアンスセンターの [電子情報開示] ページに表示されたままになっています。</span><span class="sxs-lookup"><span data-stu-id="963bd-111">The case is still listed on the eDiscovery page in the Security & Compliance Center.</span></span> <span data-ttu-id="963bd-112">クローズしたケースの詳細、保持、検索、メンバーは保持されます。</span><span class="sxs-lookup"><span data-stu-id="963bd-112">The details, holds, searches, and members of a closed case are retained.</span></span>

- <span data-ttu-id="963bd-113">クローズされた case を編集できます。</span><span class="sxs-lookup"><span data-stu-id="963bd-113">You can edit a case after it's closed.</span></span> <span data-ttu-id="963bd-114">たとえば、メンバーを追加または削除したり、検索を作成したり、検索結果をエクスポートしたり、高度な電子情報開示で分析のために検索結果を準備したりできます。</span><span class="sxs-lookup"><span data-stu-id="963bd-114">For example, you can add or removing members, create searches, export search results, and prepare search results for analysis in Advanced eDiscovery.</span></span> <span data-ttu-id="963bd-115">アクティブなケースとクローズケースの主な違いは、ケースがクローズされたときに保留がオフになっていることです。</span><span class="sxs-lookup"><span data-stu-id="963bd-115">The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>

<span data-ttu-id="963bd-116">ケースを閉じるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="963bd-116">To close a case:</span></span>

1. <span data-ttu-id="963bd-117">[**高度な電子情報開示**] ページで、クローズするケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="963bd-117">On the **Advanced eDiscovery** page, select the case that you want to close.</span></span>

2. <span data-ttu-id="963bd-118">[**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="963bd-118">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="963bd-119">[ **Case を閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="963bd-119">Click **Close case**.</span></span>

<span data-ttu-id="963bd-120">ケースを削除するには:</span><span class="sxs-lookup"><span data-stu-id="963bd-120">To delete a case:</span></span>

1. <span data-ttu-id="963bd-121">[**高度な電子情報開示**] ページで、削除するケースを選択します。</span><span class="sxs-lookup"><span data-stu-id="963bd-121">On the **Advanced eDiscovery** page, select the case that you want to delete.</span></span>

2. <span data-ttu-id="963bd-122">[**設定**] タブの [**ケース情報**] で、[**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="963bd-122">On the **Settings** tab, under **Case Information**, click **Select**.</span></span>

3. <span data-ttu-id="963bd-123">[ **Case の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="963bd-123">Click **Delete case**.</span></span> 
