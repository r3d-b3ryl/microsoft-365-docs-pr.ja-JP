---
title: 自動調査後に保留中のアクションを承認または拒否する
description: アクション センターを使用して、自動調査と応答に関連するアクションを管理する
keywords: アクション、センター、autoair、自動、調査、応答、修復
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930380"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="29f27-104">自動調査後に保留中のアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="29f27-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="29f27-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="29f27-105">**Applies to:**</span></span>
- <span data-ttu-id="29f27-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29f27-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="29f27-107">自動調査が実行されたときに、調査を続行するには承認を必要とする 1 つまたは複数の[修復](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)アクションが発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="29f27-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="29f27-108">たとえば、一連のメール メッセージを削除する必要がある場合や、検疫されたファイルを削除する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="29f27-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="29f27-109">自動調査を続行し適時完了できるよう、保留中のアクションはできるだけ早く承認 (または拒否) することが重要です。</span><span class="sxs-lookup"><span data-stu-id="29f27-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="29f27-110">Microsoft 365 Defender の自動調査および対応機能によって何かが見逃された、または誤って検出されたと思う場合は、お知らせします。</span><span class="sxs-lookup"><span data-stu-id="29f27-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="29f27-111">[Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md)の自動調査および対応 (AIR) 機能で誤検知/陰性を報告する方法をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="29f27-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="29f27-112">保留中のアクションは、アクション センターまたは調査の詳細ビュー[](#review-a-pending-action-in-the-action-center)を使用して確認[および承認できます](#review-a-pending-action-in-the-investigation-details-view)。</span><span class="sxs-lookup"><span data-stu-id="29f27-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="29f27-113">修復アクションを承認または拒否するには、[適切なアクセス許可](mtp-action-center.md#required-permissions-for-action-center-tasks)が必要です。</span><span class="sxs-lookup"><span data-stu-id="29f27-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="29f27-114">詳しくは、Microsoft 365 Defender での自動調査と対応の [前提条件に関するページをご覧ください](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。</span><span class="sxs-lookup"><span data-stu-id="29f27-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="29f27-115">保留中のアクションをアクション センターで確認する</span><span class="sxs-lookup"><span data-stu-id="29f27-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="29f27-116">[https://security.microsoft.com](https://security.microsoft.com) にアクセスし、サインインします。</span><span class="sxs-lookup"><span data-stu-id="29f27-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="29f27-117">ナビゲーション ウィンドウで、[**アクション センター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29f27-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="29f27-118">アクション センターの [**Pending (保留中)**] タブで、リスト内のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="29f27-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="29f27-119">[**Investigation number (調査番号)**] 列でアイテムを選択すると、[Investigation details (調査の詳細)] ページが開きます。</span><span class="sxs-lookup"><span data-stu-id="29f27-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="29f27-120">このページでは、調査の結果を表示し、推奨されるアクションを承認または拒否できます。</span><span class="sxs-lookup"><span data-stu-id="29f27-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="29f27-121">リスト内の行を選択すると、ポップアップが開き、そのアイテムに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="29f27-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![アクションを承認または拒否する](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="29f27-123">リンクを使用して関連付けられている警告または調査を表示し、アクションを承認または拒否します。</span><span class="sxs-lookup"><span data-stu-id="29f27-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="29f27-124">保留中のアクションを調査の詳細ビューで確認する</span><span class="sxs-lookup"><span data-stu-id="29f27-124">Review a pending action in the investigation details view</span></span>

![調査の詳細](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="29f27-126">[[Investigation details (調査の詳細)](mtp-autoir-results.md)] ページで、[**Pending actions (保留中のアクション)**] (または [**Actions (アクション)**]) タブを選択します。承認待ちのアイテムがそこに表示されます。</span><span class="sxs-lookup"><span data-stu-id="29f27-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="29f27-127">リスト内のアイテムを選択し、[**Approve (承認)**] または [**Reject (拒否)**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="29f27-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="undo-completed-actions"></a><span data-ttu-id="29f27-128">完了した操作を元に戻す</span><span class="sxs-lookup"><span data-stu-id="29f27-128">Undo completed actions</span></span>

<span data-ttu-id="29f27-129">デバイスまたはファイルが脅威ではないと判断した場合は、実行された修復アクションを、それらのアクションが自動的に実行されたのか手動で実行されたのかに関わり合って元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="29f27-129">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="29f27-130">アクション センターの [履歴] **タブでは、** 次の操作を元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="29f27-130">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="29f27-131">アクション ソース</span><span class="sxs-lookup"><span data-stu-id="29f27-131">Action source</span></span> | <span data-ttu-id="29f27-132">サポートされるアクション</span><span class="sxs-lookup"><span data-stu-id="29f27-132">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="29f27-133">- 自動調査</span><span class="sxs-lookup"><span data-stu-id="29f27-133">- Automated investigation</span></span> <br/><span data-ttu-id="29f27-134">- Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="29f27-134">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="29f27-135">- 手動対応アクション</span><span class="sxs-lookup"><span data-stu-id="29f27-135">- Manual response actions</span></span> | <span data-ttu-id="29f27-136">- デバイスを分離する</span><span class="sxs-lookup"><span data-stu-id="29f27-136">- Isolate device</span></span> <br/><span data-ttu-id="29f27-137">- コードの実行を制限する</span><span class="sxs-lookup"><span data-stu-id="29f27-137">- Restrict code execution</span></span> <br/><span data-ttu-id="29f27-138">- ファイルを検疫する</span><span class="sxs-lookup"><span data-stu-id="29f27-138">- Quarantine a file</span></span> <br/><span data-ttu-id="29f27-139">- レジストリ キーを削除する</span><span class="sxs-lookup"><span data-stu-id="29f27-139">- Remove a registry key</span></span> <br/><span data-ttu-id="29f27-140">- サービスを停止する</span><span class="sxs-lookup"><span data-stu-id="29f27-140">- Stop a service</span></span> <br/><span data-ttu-id="29f27-141">- ドライバーを無効にする</span><span class="sxs-lookup"><span data-stu-id="29f27-141">- Disable a driver</span></span> <br/><span data-ttu-id="29f27-142">- スケジュールされたタスクを削除する</span><span class="sxs-lookup"><span data-stu-id="29f27-142">- Remove a scheduled task</span></span> |

### <a name="to-undo-a-remediation-action"></a><span data-ttu-id="29f27-143">修復アクションを元に戻すには</span><span class="sxs-lookup"><span data-stu-id="29f27-143">To undo a remediation action</span></span>

1. <span data-ttu-id="29f27-144">アクション センター ( ) に移動 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="29f27-144">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="29f27-145">[履歴 **]** タブで、元に戻す操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="29f27-145">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="29f27-146">画面の右側のウィンドウで、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="29f27-146">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="29f27-147">複数のデバイスにわたる検疫からファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="29f27-147">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="29f27-148">アクション センター ( ) に移動 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="29f27-148">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="29f27-149">[履歴 **] タブ** で、操作の種類が検疫ファイルであるファイルを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="29f27-149">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="29f27-150">画面の右側のウィンドウで、[このファイルのインスタンスを **X** に適用する] を選択し、[元に戻す] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="29f27-150">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="29f27-151">次の手順</span><span class="sxs-lookup"><span data-stu-id="29f27-151">Next steps</span></span>

- [<span data-ttu-id="29f27-152">自動調査の詳細と結果を表示する</span><span class="sxs-lookup"><span data-stu-id="29f27-152">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="29f27-153">自動調査および対応機能で誤検知/陰性を処理する</span><span class="sxs-lookup"><span data-stu-id="29f27-153">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)
