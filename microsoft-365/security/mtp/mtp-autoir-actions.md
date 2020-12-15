---
title: 自動調査後に保留中のアクションを承認または拒否する
description: アクション センターを使用して、自動調査と応答に関連するアクションを管理する
keywords: アクション、センター、autoair、自動、調査、応答、修復
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.openlocfilehash: b34f4a532571d6215500ab2bec022489fd462d0f
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683369"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="df617-104">自動調査後に保留中のアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="df617-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="df617-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="df617-105">**Applies to:**</span></span>
- <span data-ttu-id="df617-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df617-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="df617-107">自動調査が実行されたときに、調査を続行するには承認を必要とする 1 つまたは複数の[修復](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)アクションが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="df617-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="df617-108">たとえば、一連のメール メッセージを削除する必要がある場合や、検疫されたファイルを削除する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="df617-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="df617-109">自動調査を続行し適時完了できるよう、保留中のアクションはできるだけ早く承認 (または拒否) することが重要です。</span><span class="sxs-lookup"><span data-stu-id="df617-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="df617-110">Microsoft 365 Defender の自動調査および対応機能によって何かが見逃された、または誤って検出されたと思う場合は、お知らせします。</span><span class="sxs-lookup"><span data-stu-id="df617-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="df617-111">[Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md)の自動調査および対応 (AIR) 機能で誤検知/陰性を報告する方法をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df617-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="df617-112">保留中のアクションは、アクション センターまたは調査の詳細ビュー[](#review-a-pending-action-in-the-action-center)を使用して確認[および承認できます](#review-a-pending-action-in-the-investigation-details-view)。</span><span class="sxs-lookup"><span data-stu-id="df617-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="df617-113">修復アクションを承認または拒否するには、[適切なアクセス許可](mtp-action-center.md#required-permissions-for-action-center-tasks)が必要です。</span><span class="sxs-lookup"><span data-stu-id="df617-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="df617-114">詳しくは、Microsoft 365 Defender での自動調査と対応の [前提条件に関するページをご覧ください](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。</span><span class="sxs-lookup"><span data-stu-id="df617-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="df617-115">保留中のアクションをアクション センターで確認する</span><span class="sxs-lookup"><span data-stu-id="df617-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="df617-116">[https://security.microsoft.com](https://security.microsoft.com) にアクセスし、サインインします。</span><span class="sxs-lookup"><span data-stu-id="df617-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="df617-117">ナビゲーション ウィンドウで、[**アクション センター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df617-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="df617-118">アクション センターの [**Pending (保留中)**] タブで、リスト内のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="df617-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="df617-119">[**Investigation number (調査番号)**] 列でアイテムを選択すると、[Investigation details (調査の詳細)] ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="df617-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="df617-120">このページでは、調査の結果を表示し、推奨されるアクションを承認または拒否できます。</span><span class="sxs-lookup"><span data-stu-id="df617-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="df617-121">リスト内の行を選択すると、ポップアップが開き、そのアイテムに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="df617-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![アクションを承認または拒否する](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="df617-123">リンクを使用して関連付けられている警告または調査を表示し、アクションを承認または拒否します。</span><span class="sxs-lookup"><span data-stu-id="df617-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="df617-124">保留中のアクションを調査の詳細ビューで確認する</span><span class="sxs-lookup"><span data-stu-id="df617-124">Review a pending action in the investigation details view</span></span>

![調査の詳細](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="df617-126">[[Investigation details (調査の詳細)](mtp-autoir-results.md)] ページで、[**Pending actions (保留中のアクション)**] (または [**Actions (アクション)**]) タブを選択します。承認待ちのアイテムがそこに表示されます。</span><span class="sxs-lookup"><span data-stu-id="df617-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="df617-127">リスト内のアイテムを選択し、[**Approve (承認)**] または [**Reject (拒否)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="df617-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="df617-128">次のステップ</span><span class="sxs-lookup"><span data-stu-id="df617-128">Next steps</span></span>

- [<span data-ttu-id="df617-129">自動調査の詳細と結果を表示する</span><span class="sxs-lookup"><span data-stu-id="df617-129">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="df617-130">自動調査および対応機能で誤検知/陰性を処理する</span><span class="sxs-lookup"><span data-stu-id="df617-130">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
