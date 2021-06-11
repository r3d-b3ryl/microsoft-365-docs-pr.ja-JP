---
title: Microsoft Defender で修復アクションを確認および管理Office 365
keywords: AIR、autoIR、Microsoft Defender for Endpoint、自動化、調査、対応、修復、脅威、高度、脅威、保護
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
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
description: Microsoft Defender for microsoft Defender for Office 365プラン 2 の自動調査および応答機能の修復アクションについて説明します。
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: 525f6cf922f80067219f6c33a2c11559e9e58a39
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878774"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="50352-104">修復アクションを確認および管理Office 365</span><span class="sxs-lookup"><span data-stu-id="50352-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="50352-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="50352-105">**Applies to**</span></span>
- [<span data-ttu-id="50352-106">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="50352-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="50352-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="50352-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="50352-108">電子メール の自動調査や&コンテンツの結果として、悪意のある、疑わしいなど、特定の修復アクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="50352-108">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="50352-109">Microsoft Defender for Office 365修復アクションには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="50352-109">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="50352-110">URL のブロック (クリック時)</span><span class="sxs-lookup"><span data-stu-id="50352-110">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="50352-111">電子メール メッセージまたはクラスターのソフト削除</span><span class="sxs-lookup"><span data-stu-id="50352-111">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="50352-112">メールまたはメールの添付ファイルを Quarantining する</span><span class="sxs-lookup"><span data-stu-id="50352-112">Quarantining email or email attachments</span></span>
- <span data-ttu-id="50352-113">外部メール転送を無効にする</span><span class="sxs-lookup"><span data-stu-id="50352-113">Turning off external mail forwarding</span></span>

<span data-ttu-id="50352-114">これらの修復アクションは、セキュリティ運用チームが承認しない限り、実行しません。</span><span class="sxs-lookup"><span data-stu-id="50352-114">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="50352-115">保留中のアクションをできるだけ早く確認して承認し、自動化された調査がリアルタイムで完了することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="50352-115">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="50352-116">場合によっては、修復アクションを元に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="50352-116">In some cases, you can undo a remediation action.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="50352-117">保留中のアクションを承認 (または拒否) する</span><span class="sxs-lookup"><span data-stu-id="50352-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="50352-118">Defender ポータル ( ) Microsoft 365に移動 <https://security.microsoft.com> し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="50352-118">Go to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="50352-119">ナビゲーション ウィンドウで、[アクション センター] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="50352-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="50352-120">[保留中 **] タブ** で、承認を待っているアクションの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="50352-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="50352-121">リストからアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="50352-121">Select an item in the list.</span></span> <span data-ttu-id="50352-122">そのフライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="50352-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="50352-123">フライアウト ウィンドウで情報を確認し、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="50352-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="50352-124">[ **調査ページを開く]** を選択して、調査の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="50352-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="50352-125">[承認 **] を** 選択して保留中のアクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="50352-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="50352-126">保留中 **のアクション** が実行されるのを防ぐには、[拒否] を選択します。</span><span class="sxs-lookup"><span data-stu-id="50352-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="50352-127">1 つの修復アクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="50352-127">Undo one remediation action</span></span>

1. <span data-ttu-id="50352-128">アクション センター ( ) に移動 <https://security.microsoft.com/action-center> し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="50352-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="50352-129">[履歴 **] タブ** で、元に戻す操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="50352-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="50352-130">画面の右側のウィンドウで、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="50352-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="50352-131">複数の修復アクションを元に戻す</span><span class="sxs-lookup"><span data-stu-id="50352-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="50352-132">アクション センター ( ) に移動 <https://security.microsoft.com/action-center> し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="50352-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="50352-133">[履歴 **] タブ** で、元に戻す操作を選択します。</span><span class="sxs-lookup"><span data-stu-id="50352-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="50352-134">同じアクションの種類を持つアイテムを選択してください。</span><span class="sxs-lookup"><span data-stu-id="50352-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="50352-135">フライアウト ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="50352-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="50352-136">フライアウト ウィンドウで、[元に戻す] を選択します。</span><span class="sxs-lookup"><span data-stu-id="50352-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="50352-137">複数のデバイス間で検疫からファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="50352-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="50352-138">アクション センター ( ) に移動 <https://security.microsoft.com/action-center> し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="50352-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="50352-139">[履歴 **] タブ** で、アクションの種類が [検疫ファイル] のファイルを **選択します**。</span><span class="sxs-lookup"><span data-stu-id="50352-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="50352-140">画面の右側のウィンドウで、[このファイルのインスタンスを **X** に適用する] を選択し、[元に戻す] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="50352-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="50352-141">次のステップ</span><span class="sxs-lookup"><span data-stu-id="50352-141">Next steps</span></span>

- [<span data-ttu-id="50352-142">脅威エクスプローラーの使用</span><span class="sxs-lookup"><span data-stu-id="50352-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="50352-143">自動調査および応答機能で誤検知/陰性を報告する方法</span><span class="sxs-lookup"><span data-stu-id="50352-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="50352-144">関連項目</span><span class="sxs-lookup"><span data-stu-id="50352-144">See also</span></span>

- [<span data-ttu-id="50352-145">自動調査の詳細と結果を表示Office 365</span><span class="sxs-lookup"><span data-stu-id="50352-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
