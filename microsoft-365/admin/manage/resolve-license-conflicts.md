---
title: ライセンスの競合を解決する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Microsoft 365 for business サブスクリプションとのライセンス競合を解決する方法について説明します。
ms.openlocfilehash: e2b5daa71164b41825282bd5652549347b8307c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915184"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="e2310-103">ライセンスの競合を解決する</span><span class="sxs-lookup"><span data-stu-id="e2310-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e2310-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="e2310-104">The admin center is changing.</span></span> <span data-ttu-id="e2310-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2310-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e2310-106">新しいユーザーを作成する前に、サブスクリプションに必要なライセンスを購入することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="e2310-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="e2310-107">ユーザー アカウントを作成したとき、新しい ユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="e2310-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="e2310-108">すべてのライセンスをユーザーに既に割り当てているが、一部のライセンスの期限が切れている場合、あるいは既にユーザーに割り当てられているライセンスを削除するとき、ライセンスの競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="e2310-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="e2310-109">詳細については、「サブスクリプションからライセンス [を削除する」を参照してください](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="e2310-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="e2310-110">ライセンスの競合を確認する方法</span><span class="sxs-lookup"><span data-stu-id="e2310-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e2310-111">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e2310-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e2310-112">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e2310-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e2310-113">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="e2310-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="e2310-114">競合に **関する** 情報については、[状態] 列を確認します。</span><span class="sxs-lookup"><span data-stu-id="e2310-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="e2310-115">競合がある場合は、1 人または複数のユーザーに有効なライセンスが必要という警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2310-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e2310-116">競合がない場合は [ **状態**] 列が表示されません。</span><span class="sxs-lookup"><span data-stu-id="e2310-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="e2310-117">ライセンスの競合を解決する方法</span><span class="sxs-lookup"><span data-stu-id="e2310-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="e2310-118">ライセンスの競合を解決するには [、ライセンスを](../../commerce/licenses/buy-licenses.md) 購入するか、不要になったユーザーからライセンス [を削除します](remove-licenses-from-users.md)。</span><span class="sxs-lookup"><span data-stu-id="e2310-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="e2310-119">任意で、[ユーザー アカウントを削除してライセンスを解放する](../add-users/delete-a-user.md)こともできます。</span><span class="sxs-lookup"><span data-stu-id="e2310-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="e2310-120">関連記事</span><span class="sxs-lookup"><span data-stu-id="e2310-120">Related articles</span></span>

[<span data-ttu-id="e2310-121">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="e2310-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="e2310-122">ユーザーからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="e2310-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)