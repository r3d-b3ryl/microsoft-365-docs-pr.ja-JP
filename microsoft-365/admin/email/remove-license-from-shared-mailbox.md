---
title: 共有メールボックスからライセンスを削除する
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
ms.reviewer: nicholak
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_licensing
search.appverid:
- BCS160
- MET150
- MOE150
description: '共有メールボックスからライセンスを削除して、別のユーザーに割り当てるか、ライセンスを返して支払いを行わない。 '
ms.openlocfilehash: d33487879506402c5f0de2f7942c3299c5698b73
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706288"
---
# <a name="remove-a-license-from-a-shared-mailbox"></a><span data-ttu-id="4fd3d-103">共有メールボックスからライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="4fd3d-103">Remove a license from a shared mailbox</span></span>

<span data-ttu-id="4fd3d-104">共有メールボックスには通常、ライセンスは必要とされません。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-104">Shared mailboxes usually don't require a license.</span></span> <span data-ttu-id="4fd3d-105">共有メールボックスからライセンスを削除するには、次の手順に従って、ユーザーに割り当てるか、不要なライセンスの支払いを行わない方法でライセンスを返します。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-105">Follow these instructions to remove a license from a shared mailbox so that you can either assign it to a user or return the license so that you aren't paying for a license you don't need.</span></span>

> [!NOTE]
>
> <span data-ttu-id="4fd3d-106">ライセンスは、次のシナリオで必要です。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-106">A license is required in the following scenarios:</span></span>
>
> 1. <span data-ttu-id="4fd3d-107">共有メールボックスには、50 GB を超えるストレージが使用されます。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-107">The shared mailbox has more than 50 GB of storage in use.</span></span>
> 2. <span data-ttu-id="4fd3d-108">共有メールボックスは、インプレイス アーカイブを使用します。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-108">The shared mailbox uses in-place archiving.</span></span>
> 3. <span data-ttu-id="4fd3d-109">共有メールボックスは訴訟ホールドに配置されます。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-109">The shared mailbox is placed in litigation hold.</span></span>
> 4. <span data-ttu-id="4fd3d-110">共有メールボックスには、Microsoft Defender ライセンスが割り当て済みです。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-110">The shared mailbox has a Microsoft Defender license assigned.</span></span>

## <a name="remove-the-license"></a><span data-ttu-id="4fd3d-111">ライセンスを削除する</span><span class="sxs-lookup"><span data-stu-id="4fd3d-111">Remove the license</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4fd3d-112">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-112">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="4fd3d-113">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-113">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="4fd3d-114">管理センターで、[**ユーザー**] \> [<a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">アクティブなユーザー</a>] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-114">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

   > [!NOTE]
   > <span data-ttu-id="4fd3d-115">[アクティブ ユーザー] ページからライセンスを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-115">You need to remove the license from the Active users page.</span></span> <span data-ttu-id="4fd3d-116">ライセンスはユーザー設定なので、[共有メールボックス] ページからライセンスを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-116">You can't remove the license from the Shared mailbox page because licenses are user settings.</span></span>
  
2. <span data-ttu-id="4fd3d-117">共有メールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-117">Select the shared mailbox.</span></span>

3. <span data-ttu-id="4fd3d-118">[ライセンス **とアプリ] タブの 1** つで、[ライセンス] **を展開** し、削除するライセンスのボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-118">One the **Licenses and Apps** tab, expand **Licenses** and uncheck the box for the license you want to remove.</span></span>

4. <span data-ttu-id="4fd3d-119">[**変更の保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-119">Select **Save changes**.</span></span>

5. <span data-ttu-id="4fd3d-120">[アクティブ ユーザー] ページ **に戻** った場合、共有メールボックスの状態は [ **ライセンス解除] になります**。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-120">When you return to the **Active users** page, the status of the shared mailbox will be **Unlicensed**.</span></span>

6. <span data-ttu-id="4fd3d-121">ライセンスの支払いは引き続き行います。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-121">You're still paying for the license.</span></span> <span data-ttu-id="4fd3d-122">支払いを停止するには、 [サブスクリプションからライセンスを削除します](../../commerce/licenses/buy-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="4fd3d-122">To stop paying for it, [remove the license from your subscription](../../commerce/licenses/buy-licenses.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="4fd3d-123">関連コンテンツ</span><span class="sxs-lookup"><span data-stu-id="4fd3d-123">Related content</span></span>

<span data-ttu-id="4fd3d-124">[共有メールボックスについて](about-shared-mailboxes.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4fd3d-124">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="4fd3d-125">[共有メールボックスの作成](create-a-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4fd3d-125">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="4fd3d-126">[共有メールボックスを構成する](configure-a-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4fd3d-126">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="4fd3d-127">[ユーザー メールボックスを共有メールボックスに変換する](convert-user-mailbox-to-shared-mailbox.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4fd3d-127">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="4fd3d-128">[共有メールボックスに関する問題を解決する](resolve-issues-with-shared-mailboxes.md) (記事)</span><span class="sxs-lookup"><span data-stu-id="4fd3d-128">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>
