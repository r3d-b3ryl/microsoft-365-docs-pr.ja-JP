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
ms.openlocfilehash: bcff8f12133ea16e3d91e293943be1593eaf9659
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142695"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="e6ed1-104">Office 365 での修復アクションの確認と管理</span><span class="sxs-lookup"><span data-stu-id="e6ed1-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="e6ed1-105">メールやグループ作業のコンテンツ&調査を自動化すると、悪意のある、疑わしいなど、特定の修復アクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="e6ed1-106">Microsoft Defender for Office 365 では、修復アクションには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="e6ed1-107">URL のブロック (クリック時)</span><span class="sxs-lookup"><span data-stu-id="e6ed1-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="e6ed1-108">メール メッセージまたはクラスターのソフト削除</span><span class="sxs-lookup"><span data-stu-id="e6ed1-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="e6ed1-109">電子メールまたはメールの添付ファイルを確認する</span><span class="sxs-lookup"><span data-stu-id="e6ed1-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="e6ed1-110">外部メール転送を無効にする</span><span class="sxs-lookup"><span data-stu-id="e6ed1-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="e6ed1-111">これらの修復アクションは、セキュリティ運用チームが承認しない限り、実行されるのではありません。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="e6ed1-112">保留中のアクションをできるだけ早く確認して承認し、自動調査が時間内に完了することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="e6ed1-113">場合によっては、修復アクションを元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-113">In some cases, you can undo a remediation action.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="e6ed1-114">保留中のアクションを承認 (または拒否) する</span><span class="sxs-lookup"><span data-stu-id="e6ed1-114">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="e6ed1-115">Microsoft 365 セキュリティ センターに移動し [https://security.microsoft.com](https://security.microsoft.com) 、サインインします。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-115">Go to the Microsoft 365 security center [https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="e6ed1-116">ナビゲーション ウィンドウで、アクション センターを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-116">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="e6ed1-117">[ **保留中] タブ** で、承認待ちアクションの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-117">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="e6ed1-118">リストからアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-118">Select an item in the list.</span></span> <span data-ttu-id="e6ed1-119">そのフライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-119">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="e6ed1-120">フライアウト ウィンドウで情報を確認し、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-120">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="e6ed1-121">[ **調査を開く] ページを選択** して、調査の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-121">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="e6ed1-122">[ **承認] を** 選択して保留中のアクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-122">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="e6ed1-123">保留中 **のアクション** が実行されるのを防ぐには、[拒否] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-123">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="e6ed1-124">1 つの修復アクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="e6ed1-124">Undo one remediation action</span></span>

1. <span data-ttu-id="e6ed1-125">アクション センター ( ) に移動 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-125">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="e6ed1-126">[履歴 **] タブ** で、元に戻す操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-126">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="e6ed1-127">画面の右側のウィンドウで、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-127">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="e6ed1-128">複数の修復操作を元に戻す</span><span class="sxs-lookup"><span data-stu-id="e6ed1-128">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="e6ed1-129">アクション センター ( ) に移動 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-129">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="e6ed1-130">[履歴 **] タブ** で、元に戻す操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-130">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="e6ed1-131">同じアクションの種類を持つアイテムを選択してください。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-131">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="e6ed1-132">フライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-132">A flyout pane opens.</span></span>
3. <span data-ttu-id="e6ed1-133">フライアウト ウィンドウで、[元に戻す] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-133">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="e6ed1-134">複数のデバイスにわたる検疫からファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="e6ed1-134">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="e6ed1-135">アクション センター ( ) に移動 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-135">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="e6ed1-136">[履歴 **] タブ** で、操作の種類が検疫ファイルであるファイルを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-136">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="e6ed1-137">画面の右側のウィンドウで、[このファイルのインスタンスを **X** に適用する] を選択し、[元に戻す] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="e6ed1-137">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e6ed1-138">次の手順</span><span class="sxs-lookup"><span data-stu-id="e6ed1-138">Next steps</span></span>

- [<span data-ttu-id="e6ed1-139">脅威エクスプローラーの使用</span><span class="sxs-lookup"><span data-stu-id="e6ed1-139">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="e6ed1-140">自動調査および対応機能で誤検知/陰性を報告する方法</span><span class="sxs-lookup"><span data-stu-id="e6ed1-140">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="e6ed1-141">こちらもご覧ください</span><span class="sxs-lookup"><span data-stu-id="e6ed1-141">See also</span></span>

- [<span data-ttu-id="e6ed1-142">Office 365 で自動調査の詳細と結果を表示する</span><span class="sxs-lookup"><span data-stu-id="e6ed1-142">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
