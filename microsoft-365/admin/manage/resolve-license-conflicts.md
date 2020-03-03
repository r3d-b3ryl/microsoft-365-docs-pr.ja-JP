---
title: 一般法人向け Office 365 のライセンスの競合を解決する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: Office 365 for business サブスクリプションのライセンスの競合を解決する方法について説明します。
ms.openlocfilehash: 63464951c4f1fd568248ca5c43da9f8c94347711
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361782"
---
# <a name="resolve-license-conflicts-in-office-365-for-business"></a><span data-ttu-id="bc2c7-103">一般法人向け Office 365 のライセンスの競合を解決する</span><span class="sxs-lookup"><span data-stu-id="bc2c7-103">Resolve license conflicts in Office 365 for business</span></span>

<span data-ttu-id="bc2c7-104">新しいユーザーを作成する前に、サブスクリプションに必要なライセンスを購入することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bc2c7-104">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="bc2c7-105">ユーザー アカウントを作成したとき、新しい ユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="bc2c7-105">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="bc2c7-106">すべてのライセンスをユーザーに既に割り当てているが、一部のライセンスの期限が切れている場合、あるいは既にユーザーに割り当てられているライセンスを削除するとき、ライセンスの競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="bc2c7-106">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="bc2c7-107">詳細については、「[サブスクリプションからライセンスを削除する](../../commerce/licenses/remove-licenses-from-subscription.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc2c7-107">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="bc2c7-108">ライセンスの競合を確認する方法</span><span class="sxs-lookup"><span data-stu-id="bc2c7-108">How do I view license conflicts?</span></span>

1. <span data-ttu-id="bc2c7-109">管理センターで、[**課金** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="bc2c7-109">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

    <span data-ttu-id="bc2c7-110">Office 365 ドイツを使用している場合は、[この<a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">ライセンス</a>] ページにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="bc2c7-110">If you're using Office 365 Germany, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

    <span data-ttu-id="bc2c7-111">21Vianet が運用している Office 365 を使用している場合は、[この<a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">ライセンス</a>] ページにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="bc2c7-111">If you're using Office 365 operated by 21Vianet, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="bc2c7-112">競合に関する情報については、[**状態**] 列を確認してください。</span><span class="sxs-lookup"><span data-stu-id="bc2c7-112">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="bc2c7-113">競合がある場合は、1人以上のユーザーが有効なライセンスを必要としているという警告メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc2c7-113">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bc2c7-114">競合がない場合は [ **状態**] 列が表示されません。</span><span class="sxs-lookup"><span data-stu-id="bc2c7-114">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="bc2c7-115">ライセンスの競合を解決する方法</span><span class="sxs-lookup"><span data-stu-id="bc2c7-115">How do I resolve license conflicts?</span></span>

<span data-ttu-id="bc2c7-116">ライセンスの競合を解決するには、[より多くのライセンスを購入](../../commerce/licenses/buy-licenses.md)するか、不要に[なったユーザーからライセンスを削除](remove-licenses-from-users.md)します。</span><span class="sxs-lookup"><span data-stu-id="bc2c7-116">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="bc2c7-117">任意で、[ユーザー アカウントを削除してライセンスを解放する](../add-users/delete-a-user.md)こともできます。</span><span class="sxs-lookup"><span data-stu-id="bc2c7-117">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="bc2c7-118">関連記事</span><span class="sxs-lookup"><span data-stu-id="bc2c7-118">Related articles</span></span> 

[<span data-ttu-id="bc2c7-119">ユーザーにライセンスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="bc2c7-119">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="bc2c7-120">ユーザーからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="bc2c7-120">Remove licenses from users</span></span>](remove-licenses-from-users.md)
