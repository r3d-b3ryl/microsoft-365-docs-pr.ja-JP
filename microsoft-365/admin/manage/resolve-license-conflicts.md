---
title: ライセンスの競合を解決する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Microsoft 365 for business サブスクリプションのライセンスの競合を解決する方法について説明します。
ms.openlocfilehash: 05efe9e75b051ece900ba9defe047f1244b713a9
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399670"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="e261c-103">ライセンスの競合を解決する</span><span class="sxs-lookup"><span data-stu-id="e261c-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e261c-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="e261c-104">The admin center is changing.</span></span> <span data-ttu-id="e261c-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e261c-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e261c-106">新しいユーザーを作成する前に、サブスクリプションに必要なライセンスを購入することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e261c-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="e261c-107">ユーザー アカウントを作成したとき、新しい ユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e261c-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="e261c-108">すべてのライセンスをユーザーに既に割り当てているが、一部のライセンスの期限が切れている場合、あるいは既にユーザーに割り当てられているライセンスを削除するとき、ライセンスの競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="e261c-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="e261c-109">詳細については、「[サブスクリプションからライセンスを削除する](../../commerce/licenses/remove-licenses-from-subscription.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e261c-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="e261c-110">ライセンスの競合を確認する方法</span><span class="sxs-lookup"><span data-stu-id="e261c-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e261c-111">管理センターで、[**課金** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e261c-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e261c-112">管理センターで、[**課金** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e261c-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e261c-113">管理センターで、[**課金** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e261c-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="e261c-114">競合に関する情報については、[**状態**] 列を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e261c-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="e261c-115">競合がある場合は、1人以上のユーザーが有効なライセンスを必要としているという警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e261c-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e261c-116">競合がない場合は [ **状態**] 列が表示されません。</span><span class="sxs-lookup"><span data-stu-id="e261c-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="e261c-117">ライセンスの競合を解決する方法</span><span class="sxs-lookup"><span data-stu-id="e261c-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="e261c-118">ライセンスの競合を解決するには、[より多くのライセンスを購入](../../commerce/licenses/buy-licenses.md)するか、不要に[なったユーザーからライセンスを削除](remove-licenses-from-users.md)します。</span><span class="sxs-lookup"><span data-stu-id="e261c-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="e261c-119">任意で、[ユーザー アカウントを削除してライセンスを解放する](../add-users/delete-a-user.md)こともできます。</span><span class="sxs-lookup"><span data-stu-id="e261c-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="e261c-120">関連記事</span><span class="sxs-lookup"><span data-stu-id="e261c-120">Related articles</span></span> 

[<span data-ttu-id="e261c-121">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e261c-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="e261c-122">ユーザーからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="e261c-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)
