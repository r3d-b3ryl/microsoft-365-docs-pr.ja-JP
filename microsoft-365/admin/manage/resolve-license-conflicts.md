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
description: Microsoft 365 for business サブスクリプションとのライセンスの競合を解決する方法について説明します。
ms.openlocfilehash: 284a6b169c02314dd2bbd0e13c10c081cb50f58d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114455"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="5f5b1-103">ライセンスの競合を解決する</span><span class="sxs-lookup"><span data-stu-id="5f5b1-103">Resolve license conflicts</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="5f5b1-104">管理センターは変更中です。</span><span class="sxs-lookup"><span data-stu-id="5f5b1-104">The admin center is changing.</span></span> <span data-ttu-id="5f5b1-105">エクスペリエンスがここで説明されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5f5b1-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="5f5b1-106">新しいユーザーを作成する前に、サブスクリプションに必要なライセンスを購入することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5f5b1-106">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="5f5b1-107">ユーザー アカウントを作成したとき、新しい ユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="5f5b1-107">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="5f5b1-108">すべてのライセンスをユーザーに既に割り当てているが、一部のライセンスの期限が切れている場合、あるいは既にユーザーに割り当てられているライセンスを削除するとき、ライセンスの競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="5f5b1-108">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="5f5b1-109">詳細については、「サブスクリプションからライセンス [を削除する」を参照してください](../../commerce/licenses/remove-licenses-from-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="5f5b1-109">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="5f5b1-110">ライセンスの競合を確認する方法</span><span class="sxs-lookup"><span data-stu-id="5f5b1-110">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="5f5b1-111">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="5f5b1-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="5f5b1-112">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="5f5b1-112">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="5f5b1-113">管理センターで、[**課金**] > [<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="5f5b1-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="5f5b1-114">競合に **関する** 情報については、[状態] 列を確認します。</span><span class="sxs-lookup"><span data-stu-id="5f5b1-114">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="5f5b1-115">競合がある場合は、1 人または複数のユーザーに有効なライセンスが必要なという警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5f5b1-115">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5f5b1-116">競合がない場合は [ **状態**] 列が表示されません。</span><span class="sxs-lookup"><span data-stu-id="5f5b1-116">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="5f5b1-117">ライセンスの競合を解決する方法</span><span class="sxs-lookup"><span data-stu-id="5f5b1-117">How do I resolve license conflicts?</span></span>

<span data-ttu-id="5f5b1-118">ライセンスの競合を解決するには [、ライセンスを](../../commerce/licenses/buy-licenses.md) 追加購入するか、ライセンスが不要になったユーザーからライセンス [を削除します](remove-licenses-from-users.md)。</span><span class="sxs-lookup"><span data-stu-id="5f5b1-118">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="5f5b1-119">任意で、[ユーザー アカウントを削除してライセンスを解放する](../add-users/delete-a-user.md)こともできます。</span><span class="sxs-lookup"><span data-stu-id="5f5b1-119">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="5f5b1-120">関連記事</span><span class="sxs-lookup"><span data-stu-id="5f5b1-120">Related articles</span></span>

[<span data-ttu-id="5f5b1-121">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="5f5b1-121">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="5f5b1-122">ユーザーからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="5f5b1-122">Remove licenses from users</span></span>](remove-licenses-from-users.md)
