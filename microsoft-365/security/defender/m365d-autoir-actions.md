---
title: アクション センターでのアクションの表示と管理
description: アクション センターを使用して修復アクションを表示および管理する
keywords: アクション、センター、autoair、自動、調査、応答、修復
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: f3dba2116e0f13f265937ef65fd3b69bcb1e725b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274654"
---
# <a name="view-and-manage-actions-in-the-action-center"></a><span data-ttu-id="c1a17-104">アクション センターでのアクションの表示と管理</span><span class="sxs-lookup"><span data-stu-id="c1a17-104">View and manage actions in the Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c1a17-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c1a17-105">**Applies to:**</span></span>
- <span data-ttu-id="c1a17-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1a17-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c1a17-107">Microsoft 365 Defender の脅威保護機能により、特定の修復アクションが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c1a17-107">Threat protection features in Microsoft 365 Defender can result in certain remediation actions.</span></span> <span data-ttu-id="c1a17-108">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c1a17-108">Here are some examples:</span></span>

- <span data-ttu-id="c1a17-109">[自動調査によって、](m365d-autoir.md) 修復アクションが自動的に実行される、または承認を待つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c1a17-109">[Automated investigations](m365d-autoir.md) can result in remediation actions that are taken automatically or await your approval.</span></span>
- <span data-ttu-id="c1a17-110">ウイルス対策、マルウェア対策、その他の脅威保護機能により、ファイル、URL、プロセスのブロック、検疫への成果物の送信など、修復アクションが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c1a17-110">Antivirus, antimalware, and other threat protection features can result in remediation actions, such as blocking a file, URL, or process, or sending an artifact to quarantine.</span></span>
- <span data-ttu-id="c1a17-111">セキュリティ運用チームは、高度な検索中やアラートやインシデント[](advanced-hunting-overview.md)の調査中など、手動で修復[アクション](investigate-alerts.md)を[実行できます](investigate-incidents.md)。</span><span class="sxs-lookup"><span data-stu-id="c1a17-111">Your security operations team can take remediation actions manually, such as during [advanced hunting](advanced-hunting-overview.md) or while investigating [alerts](investigate-alerts.md) or [incidents](investigate-incidents.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c1a17-112">修復アクションを承認または拒否するには、[適切なアクセス許可](m365d-action-center.md#required-permissions-for-action-center-tasks)が必要です。</span><span class="sxs-lookup"><span data-stu-id="c1a17-112">You must have [appropriate permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="c1a17-113">詳細については、「前提条件」を [参照してください](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)。</span><span class="sxs-lookup"><span data-stu-id="c1a17-113">For more information, see the [prerequisites](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-pending-actions-in-the-action-center"></a><span data-ttu-id="c1a17-114">アクション センターで保留中のアクションを確認する</span><span class="sxs-lookup"><span data-stu-id="c1a17-114">Review pending actions in the Action center</span></span>

<span data-ttu-id="c1a17-115">自動調査を続行し適時完了できるよう、保留中のアクションはできるだけ早く承認 (または拒否) することが重要です。</span><span class="sxs-lookup"><span data-stu-id="c1a17-115">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

1. <span data-ttu-id="c1a17-116">[https://security.microsoft.com](https://security.microsoft.com) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="c1a17-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="c1a17-117">ナビゲーション ウィンドウで、[**アクション センター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a17-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="c1a17-118">アクション センターの [**Pending (保留中)**] タブで、リスト内のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a17-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> <span data-ttu-id="c1a17-119">そのフライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="c1a17-119">Its flyout pane opens.</span></span> <span data-ttu-id="c1a17-120">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="c1a17-120">Here's an example.</span></span>

   ![アクションを承認または拒否する](../../media/air-actioncenter-itemselected.png)

4. <span data-ttu-id="c1a17-122">フライアウト ウィンドウで情報を確認し、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="c1a17-122">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="c1a17-123">[ **調査ページを開く]** を選択して、調査の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="c1a17-123">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="c1a17-124">[承認 **] を** 選択して保留中のアクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="c1a17-124">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="c1a17-125">保留中 **のアクション** が実行されるのを防ぐには、[拒否] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a17-125">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="c1a17-126">[Go **hunt] を** 選択して高度な [ハンティングに入る](advanced-hunting-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c1a17-126">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="undo-completed-actions"></a><span data-ttu-id="c1a17-127">完了した操作を元に戻す</span><span class="sxs-lookup"><span data-stu-id="c1a17-127">Undo completed actions</span></span>

<span data-ttu-id="c1a17-128">デバイスまたはファイルが脅威ではないと判断した場合は、これらのアクションが自動的または手動で実行されたかどうかに関わり、実行された修復アクションを元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="c1a17-128">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="c1a17-129">[アクション センター] の [履歴] **タブ** で、次の操作を元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="c1a17-129">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="c1a17-130">アクション ソース</span><span class="sxs-lookup"><span data-stu-id="c1a17-130">Action source</span></span> | <span data-ttu-id="c1a17-131">サポートされているアクション</span><span class="sxs-lookup"><span data-stu-id="c1a17-131">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="c1a17-132">- 自動調査</span><span class="sxs-lookup"><span data-stu-id="c1a17-132">- Automated investigation</span></span> <br/><span data-ttu-id="c1a17-133">- Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="c1a17-133">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="c1a17-134">- 手動応答アクション</span><span class="sxs-lookup"><span data-stu-id="c1a17-134">- Manual response actions</span></span> | <span data-ttu-id="c1a17-135">- デバイスの分離</span><span class="sxs-lookup"><span data-stu-id="c1a17-135">- Isolate device</span></span> <br/><span data-ttu-id="c1a17-136">- コードの実行を制限する</span><span class="sxs-lookup"><span data-stu-id="c1a17-136">- Restrict code execution</span></span> <br/><span data-ttu-id="c1a17-137">- ファイルを検疫する</span><span class="sxs-lookup"><span data-stu-id="c1a17-137">- Quarantine a file</span></span> <br/><span data-ttu-id="c1a17-138">- レジストリ キーを削除する</span><span class="sxs-lookup"><span data-stu-id="c1a17-138">- Remove a registry key</span></span> <br/><span data-ttu-id="c1a17-139">- サービスを停止する</span><span class="sxs-lookup"><span data-stu-id="c1a17-139">- Stop a service</span></span> <br/><span data-ttu-id="c1a17-140">- ドライバーを無効にする</span><span class="sxs-lookup"><span data-stu-id="c1a17-140">- Disable a driver</span></span> <br/><span data-ttu-id="c1a17-141">- スケジュールされたタスクを削除する</span><span class="sxs-lookup"><span data-stu-id="c1a17-141">- Remove a scheduled task</span></span> |

### <a name="undo-one-remediation-action"></a><span data-ttu-id="c1a17-142">1 つの修復アクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="c1a17-142">Undo one remediation action</span></span>

1. <span data-ttu-id="c1a17-143">アクション センター ( ) に移動 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="c1a17-143">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="c1a17-144">[履歴 **] タブ** で、元に戻す操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a17-144">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="c1a17-145">画面の右側のウィンドウで、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c1a17-145">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="c1a17-146">複数の修復アクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="c1a17-146">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="c1a17-147">[アクション センター] に移動し https://security.microsoft.com/action-center) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="c1a17-147">Go to the Action center (https://security.microsoft.com/action-center) and sign in.</span></span>

2. <span data-ttu-id="c1a17-148">[履歴 **] タブ** で、元に戻す操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a17-148">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="c1a17-149">同じアクションの種類を持つアイテムを選択してください。</span><span class="sxs-lookup"><span data-stu-id="c1a17-149">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="c1a17-150">フライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="c1a17-150">A flyout pane opens.</span></span>

3. <span data-ttu-id="c1a17-151">フライアウト ウィンドウで、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c1a17-151">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="c1a17-152">複数のデバイス間で検疫からファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="c1a17-152">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="c1a17-153">アクション センター ( ) に移動 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="c1a17-153">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="c1a17-154">[履歴 **] タブ** で、検疫ファイルのアクションの **種類を持つファイルを** 選択します。</span><span class="sxs-lookup"><span data-stu-id="c1a17-154">On the **History** tab, select a file that has a **Quarantine file** Action type.</span></span>

3. <span data-ttu-id="c1a17-155">画面の右側のウィンドウで、[このファイルのインスタンスを **X** に適用する] を選択し、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="c1a17-155">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c1a17-156">次の手順</span><span class="sxs-lookup"><span data-stu-id="c1a17-156">Next steps</span></span>

- [<span data-ttu-id="c1a17-157">自動調査の詳細と結果を表示する</span><span class="sxs-lookup"><span data-stu-id="c1a17-157">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="c1a17-158">誤検知または誤検知に対処する)</span><span class="sxs-lookup"><span data-stu-id="c1a17-158">Address false positives or false negatives)</span></span>](m365d-autoir-report-false-positives-negatives.md)
