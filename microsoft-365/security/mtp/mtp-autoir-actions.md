---
title: 自動調査後に保留中のアクションを承認または拒否する
description: アクション センターを使用して、自動調査と応答に関連するアクションを管理する
keywords: アクション、センター、autoair、自動、調査、応答、修復
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: edc952a0361ee8cfa6ed3df2eaf80f0fc4bf7fd5
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808462"
---
# <a name="approve-or-reject-pending-actions-from-automated-investigations"></a><span data-ttu-id="a917f-104">自動調査による保留中のアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="a917f-104">Approve or reject pending actions from automated investigations</span></span>

<span data-ttu-id="a917f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a917f-105">**Applies to:**</span></span>
- <span data-ttu-id="a917f-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a917f-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="a917f-107">自動調査が実行されたときに、調査を続行するには承認を必要とする 1 つまたは複数の[修復](mtp-action-center.md#remediation-actions)アクションが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="a917f-107">When an automated investigation runs, it can result in one or more [remediation actions](mtp-action-center.md#remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="a917f-108">たとえば、一連のメール メッセージを削除する必要がある場合や、検疫されたファイルを削除する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a917f-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="a917f-109">自動調査を続行し適時完了できるよう、保留中のアクションはできるだけ早く承認 (または拒否) することが重要です。</span><span class="sxs-lookup"><span data-stu-id="a917f-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

<span data-ttu-id="a917f-110">保留中のアクションを確認して承認する方法には、いくつかあります。</span><span class="sxs-lookup"><span data-stu-id="a917f-110">Pending actions can be reviewed and approved by using one of several methods:</span></span>
- [<span data-ttu-id="a917f-111">アクション センターを使用する</span><span class="sxs-lookup"><span data-stu-id="a917f-111">Use the Action center</span></span>](#review-a-pending-action-in-the-action-center)
- <span data-ttu-id="a917f-112">[[Investigation details (調査の詳細)] ビューを使用する](#review-a-pending-action-in-the-investigation-details-view)</span><span class="sxs-lookup"><span data-stu-id="a917f-112">[Use the investigation details view](#review-a-pending-action-in-the-investigation-details-view)</span></span>

> [!NOTE]
> <span data-ttu-id="a917f-113">修復アクションを承認または拒否するには、[適切なアクセス許可](mtp-action-center.md#required-permissions-for-action-center-tasks)が必要です。</span><span class="sxs-lookup"><span data-stu-id="a917f-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="a917f-114">保留中のアクションをアクション センターで確認する</span><span class="sxs-lookup"><span data-stu-id="a917f-114">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="a917f-115">[https://security.microsoft.com](https://security.microsoft.com) にアクセスし、サインインします。</span><span class="sxs-lookup"><span data-stu-id="a917f-115">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="a917f-116">ナビゲーション ウィンドウで、[**アクション センター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a917f-116">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="a917f-117">アクション センターの [**Pending (保留中)**] タブで、リスト内のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="a917f-117">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="a917f-118">[**Investigation number (調査番号)**] 列でアイテムを選択すると、[Investigation details (調査の詳細)] ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="a917f-118">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="a917f-119">このページでは、調査の結果を表示し、推奨されるアクションを承認または拒否できます。</span><span class="sxs-lookup"><span data-stu-id="a917f-119">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="a917f-120">リスト内の行を選択すると、ポップアップが開き、そのアイテムに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a917f-120">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![アクションを承認または拒否する](../images/air-actioncenter-itemselected.png)<br/><span data-ttu-id="a917f-122">リンクを使用して関連付けられている警告または調査を表示し、アクションを承認または拒否します。</span><span class="sxs-lookup"><span data-stu-id="a917f-122">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="a917f-123">保留中のアクションを調査の詳細ビューで確認する</span><span class="sxs-lookup"><span data-stu-id="a917f-123">Review a pending action in the investigation details view</span></span>

![調査の詳細](../images/mtp-air-investdetails.png)

1. <span data-ttu-id="a917f-125">[[Investigation details (調査の詳細)](mtp-autoir-results.md)] ページで、[**Pending actions (保留中のアクション)**] (または [**Actions (アクション)**]) タブを選択します。承認待ちのアイテムがそこに表示されます。</span><span class="sxs-lookup"><span data-stu-id="a917f-125">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="a917f-126">リスト内のアイテムを選択し、[**Approve (承認)**] または [**Reject (拒否)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a917f-126">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a917f-127">次のステップ</span><span class="sxs-lookup"><span data-stu-id="a917f-127">Next steps</span></span>

- [<span data-ttu-id="a917f-128">アクション センターの詳細</span><span class="sxs-lookup"><span data-stu-id="a917f-128">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="a917f-129">インシデントの詳細</span><span class="sxs-lookup"><span data-stu-id="a917f-129">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="a917f-130">捜索の詳細</span><span class="sxs-lookup"><span data-stu-id="a917f-130">Learn about hunting</span></span>](advanced-hunting-overview.md)
