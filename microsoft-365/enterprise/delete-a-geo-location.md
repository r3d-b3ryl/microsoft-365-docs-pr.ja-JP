---
title: サテライトの場所を削除する
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: Office 365 Multi-Geo でサテライトの場所を削除する方法を説明します。 サテライトの場所を削除すると、すべてのユーザー データも完全に削除されます。
ms.openlocfilehash: 7a58ed91a0bb801fc41ed0a89889ede5e65b4a21
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691989"
---
# <a name="delete-a-satellite-location-in-microsoft-365-multi-geo"></a><span data-ttu-id="57473-104">Office 365 Multi-Geo でサテライトの場所を削除する</span><span class="sxs-lookup"><span data-stu-id="57473-104">Delete a satellite location in Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="57473-105">サテライトの場所が不要になった場合は、SharePoint 管理センターのテナントから削除できます。</span><span class="sxs-lookup"><span data-stu-id="57473-105">If you no longer need a satellite location, you can delete it from your tenant from the SharePoint admin center.</span></span>

> [!WARNING]
> <span data-ttu-id="57473-106">すべてのサテライトの場所のユーザー データは永久に削除されます。</span><span class="sxs-lookup"><span data-stu-id="57473-106">All user data in the satellite location will be permanently deleted.</span></span> <span data-ttu-id="57473-107">これには、すべての OneDrive for Business コンテンツ、SharePoint サイトと Exchange メールボックス (Microsoft 365 グループ メールボックスを含む) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="57473-107">This includes all OneDrive for Business content, SharePoint sites and Exchange mailboxes including Microsoft 365 Group mailboxes.</span></span> <span data-ttu-id="57473-108">サテライトの場所を削除する前に、データを別のサテライトの場所または集中管理する場所に移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57473-108">You must migrate any data to another satellite location or the central location before you delete the satellite location.</span></span> <span data-ttu-id="57473-109">この操作は元に戻せません。</span><span class="sxs-lookup"><span data-stu-id="57473-109">This action cannot be undone.</span></span>

<span data-ttu-id="57473-110">サテライトの場所はグローバル管理者のみが削除できます。</span><span class="sxs-lookup"><span data-stu-id="57473-110">Only global administrators can delete satellite locations.</span></span>

![地理的位置の削除の UI を表示する Multi-Geo 管理センターのスクリーンショット](../media/multi-geo-delete-satellite-location.png)

<span data-ttu-id="57473-112">サテライトの場所を削除するには</span><span class="sxs-lookup"><span data-stu-id="57473-112">To delete a satellite location</span></span>

1. <span data-ttu-id="57473-113">SharePoint 管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="57473-113">Open the SharePoint admin center</span></span>

2. <span data-ttu-id="57473-114">**[地理的位置]** タブを開きます。</span><span class="sxs-lookup"><span data-stu-id="57473-114">Navigate to the **Geo locations** tab.</span></span>

3. <span data-ttu-id="57473-115">マップ上で削除する地理的位置をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57473-115">On the map, click the geo location that you want to delete.</span></span>

4. <span data-ttu-id="57473-116">**[場所の削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57473-116">Click **Delete location**.</span></span>

5. <span data-ttu-id="57473-117">確認のチェック ボックスをオンにして、削除を確認します。</span><span class="sxs-lookup"><span data-stu-id="57473-117">Confirm the deletion by selecting the confirmation check boxes.</span></span>

6. <span data-ttu-id="57473-118">**[削除]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57473-118">Click **Delete**.</span></span>
