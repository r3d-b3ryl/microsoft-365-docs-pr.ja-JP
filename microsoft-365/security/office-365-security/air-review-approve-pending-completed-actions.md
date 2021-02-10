---
title: Microsoft Defender for Office 365 での修復アクションの確認と管理
keywords: AIR, autoIR, ATP, 自動化, 調査, 対応, 修復, 脅威, 高度, 脅威, 保護
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft Defender for Office 365 プラン 2 の自動調査および対応機能の修復アクションについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: 3fb77fa41ff3e9af995cf80b9f4024aa92a51212
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176017"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="30e7e-104">Office 365 での修復アクションの確認と管理</span><span class="sxs-lookup"><span data-stu-id="30e7e-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="30e7e-105">メールやグループ作業のコンテンツ&調査を自動化すると、悪意のある、疑わしいなど、特定の修復アクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="30e7e-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="30e7e-106">Microsoft Defender for Office 365 では、修復アクションには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="30e7e-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="30e7e-107">URL のブロック (クリック時)</span><span class="sxs-lookup"><span data-stu-id="30e7e-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="30e7e-108">メール メッセージまたはクラスターのソフト削除</span><span class="sxs-lookup"><span data-stu-id="30e7e-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="30e7e-109">電子メールまたはメールの添付ファイルを確認する</span><span class="sxs-lookup"><span data-stu-id="30e7e-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="30e7e-110">外部メール転送を無効にする</span><span class="sxs-lookup"><span data-stu-id="30e7e-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="30e7e-111">これらの修復アクションは、セキュリティ運用チームが承認しない限り、実行されるのではありません。</span><span class="sxs-lookup"><span data-stu-id="30e7e-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="30e7e-112">保留中のアクションをできるだけ早く確認して承認し、自動調査が時間内に完了することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="30e7e-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="30e7e-113">場合によっては、修復アクションを元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="30e7e-113">In some cases, you can undo a remediation action.</span></span>

<span data-ttu-id="30e7e-114">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="30e7e-114">**Applies to**</span></span>
- [<span data-ttu-id="30e7e-115">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="30e7e-115">Microsoft Defender for Office 365 plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="30e7e-116">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30e7e-116">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="30e7e-117">保留中のアクションを承認 (または拒否) する</span><span class="sxs-lookup"><span data-stu-id="30e7e-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="30e7e-118">Microsoft 365 セキュリティ センターに移動し [https://security.microsoft.com](https://security.microsoft.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="30e7e-118">Go to the Microsoft 365 security center [https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="30e7e-119">ナビゲーション ウィンドウで、アクション センターを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="30e7e-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="30e7e-120">[ **保留中] タブ** で、承認待ちアクションの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="30e7e-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="30e7e-121">リストからアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="30e7e-121">Select an item in the list.</span></span> <span data-ttu-id="30e7e-122">そのフライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="30e7e-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="30e7e-123">フライアウト ウィンドウで情報を確認し、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="30e7e-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="30e7e-124">[ **調査を開く] ページを選択** して、調査の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="30e7e-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="30e7e-125">[ **承認] を** 選択して保留中のアクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="30e7e-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="30e7e-126">保留中 **のアクション** が実行されるのを防ぐには、[拒否] を選択します。</span><span class="sxs-lookup"><span data-stu-id="30e7e-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="30e7e-127">1 つの修復アクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="30e7e-127">Undo one remediation action</span></span>

1. <span data-ttu-id="30e7e-128">アクション センター ( ) に移動 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="30e7e-128">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="30e7e-129">[履歴 **] タブ** で、元に戻す操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="30e7e-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="30e7e-130">画面の右側のウィンドウで、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="30e7e-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="30e7e-131">複数の修復操作を元に戻す</span><span class="sxs-lookup"><span data-stu-id="30e7e-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="30e7e-132">アクション センター ( ) に移動 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="30e7e-132">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="30e7e-133">[履歴 **] タブ** で、元に戻す操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="30e7e-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="30e7e-134">同じアクションの種類を持つアイテムを選択してください。</span><span class="sxs-lookup"><span data-stu-id="30e7e-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="30e7e-135">フライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="30e7e-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="30e7e-136">フライアウト ウィンドウで、[元に戻す] を選択します。</span><span class="sxs-lookup"><span data-stu-id="30e7e-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="30e7e-137">複数のデバイスにわたる検疫からファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="30e7e-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="30e7e-138">アクション センター ( ) に移動 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="30e7e-138">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="30e7e-139">[履歴 **] タブ** で、操作の種類が検疫ファイルであるファイルを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="30e7e-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="30e7e-140">画面の右側のウィンドウで、[このファイルのインスタンスを **X** に適用する] を選択し、[元に戻す] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="30e7e-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="30e7e-141">次の手順</span><span class="sxs-lookup"><span data-stu-id="30e7e-141">Next steps</span></span>

- [<span data-ttu-id="30e7e-142">脅威エクスプローラーの使用</span><span class="sxs-lookup"><span data-stu-id="30e7e-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="30e7e-143">自動調査および対応機能で誤検知/陰性を報告する方法</span><span class="sxs-lookup"><span data-stu-id="30e7e-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="30e7e-144">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="30e7e-144">See also</span></span>

- [<span data-ttu-id="30e7e-145">Office 365 で自動調査の詳細と結果を表示する</span><span class="sxs-lookup"><span data-stu-id="30e7e-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
