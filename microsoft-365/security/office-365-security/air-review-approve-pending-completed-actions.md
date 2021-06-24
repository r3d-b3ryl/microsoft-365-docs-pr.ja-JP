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
ms.date: 06/10/2021
ms.openlocfilehash: 987771616acfd2f2faf425e525505b320155388e
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108537"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="4eec8-104">修復アクションを確認および管理Office 365</span><span class="sxs-lookup"><span data-stu-id="4eec8-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="4eec8-105">**適用対象**</span><span class="sxs-lookup"><span data-stu-id="4eec8-105">**Applies to**</span></span>
- [<span data-ttu-id="4eec8-106">Microsoft Defender for Office 365 プラン 2</span><span class="sxs-lookup"><span data-stu-id="4eec8-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="4eec8-107">電子メール の自動調査や&コンテンツの結果として、悪意のある、疑わしいなど、特定の修復アクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4eec8-107">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="4eec8-108">Microsoft Defender for Office 365修復アクションには、次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4eec8-108">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="4eec8-109">電子メール メッセージまたはクラスターのソフト削除</span><span class="sxs-lookup"><span data-stu-id="4eec8-109">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="4eec8-110">外部メール転送を無効にする</span><span class="sxs-lookup"><span data-stu-id="4eec8-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="4eec8-111">これらの修復アクションは、セキュリティ運用チームが承認しない限り、実行しません。</span><span class="sxs-lookup"><span data-stu-id="4eec8-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="4eec8-112">保留中のアクションをできるだけ早く確認して承認し、自動化された調査がリアルタイムで完了することを推奨します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="4eec8-113">場合によっては、送信されたアクションを再考できます。</span><span class="sxs-lookup"><span data-stu-id="4eec8-113">In some cases, you can reconsider submitted actions.</span></span>  <span data-ttu-id="4eec8-114">アクションを実行する前に、検索&役割の一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4eec8-114">You need to be part of Search & purge role before taking any actions.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="4eec8-115">保留中のアクションを承認 (または拒否) する</span><span class="sxs-lookup"><span data-stu-id="4eec8-115">Approve (or reject) pending actions</span></span>
<span data-ttu-id="4eec8-116">自動調査アクションを検索して実行するには、次の 4 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="4eec8-116">There are four different ways to find and take auto investigation actions:</span></span>

- [<span data-ttu-id="4eec8-117">インシデント キュー</span><span class="sxs-lookup"><span data-stu-id="4eec8-117">Incident queue</span></span>](https://security.microsoft.com/incidents)
- [<span data-ttu-id="4eec8-118">アクション センター</span><span class="sxs-lookup"><span data-stu-id="4eec8-118">Action center</span></span>](https://security.microsoft.com/action-center/pending)
- <span data-ttu-id="4eec8-119">調査自体 (インシデントまたはアラートからアクセス)</span><span class="sxs-lookup"><span data-stu-id="4eec8-119">Investigation itself (accessed via Incident or from an alert)</span></span>
- [<span data-ttu-id="4eec8-120">調査と修復の調査キュー</span><span class="sxs-lookup"><span data-stu-id="4eec8-120">Investigation and remediation investigations queue</span></span>](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a><span data-ttu-id="4eec8-121">インシデント キュー</span><span class="sxs-lookup"><span data-stu-id="4eec8-121">Incident queue</span></span>

1. <span data-ttu-id="4eec8-122">ポータル ( ) Microsoft 365 Defender開 <https://security.microsoft.com> き、サインインします。</span><span class="sxs-lookup"><span data-stu-id="4eec8-122">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="4eec8-123">ナビゲーション ウィンドウで、[インシデント] を選択 **し、[インシデント&通知>選択します**。</span><span class="sxs-lookup"><span data-stu-id="4eec8-123">In the navigation pane, select **Incidents & alerts > Incidents**.</span></span>
3. <span data-ttu-id="4eec8-124">インシデント名を選択して、概要ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="4eec8-124">Select an incident name to open its summary page.</span></span>
4. <span data-ttu-id="4eec8-125">[証拠と **応答] タブを選択** します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-125">Select the **Evidence and Response** tab.</span></span>
5. <span data-ttu-id="4eec8-126">リストからアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-126">Select an item in the list.</span></span> <span data-ttu-id="4eec8-127">サイド ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="4eec8-127">Its side pane opens.</span></span>
6. <span data-ttu-id="4eec8-128">サイド ウィンドウで、承認または拒否のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-128">In the side pane, take approve or reject actions.</span></span>

## <a name="investigation-queue"></a><span data-ttu-id="4eec8-129">調査キュー</span><span class="sxs-lookup"><span data-stu-id="4eec8-129">Investigation queue</span></span>

1. <span data-ttu-id="4eec8-130">ポータル ( ) Microsoft 365 Defender開 <https://security.microsoft.com> き、サインインします。</span><span class="sxs-lookup"><span data-stu-id="4eec8-130">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="4eec8-131">[アラート/インシデント] ページから移動します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-131">Navigate from the alerts/incident page.</span></span>
3. <span data-ttu-id="4eec8-132">[調査] ページで、[保留中のアクション **] タブに移動** します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-132">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="4eec8-133">リストからアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-133">Select an item in the list.</span></span> <span data-ttu-id="4eec8-134">サイド ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="4eec8-134">Its side pane opens.</span></span>
5. <span data-ttu-id="4eec8-135">サイド ウィンドウで、承認または拒否のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-135">In the side pane, take approve or reject actions.</span></span>

## <a name="action-center"></a><span data-ttu-id="4eec8-136">アクション センター</span><span class="sxs-lookup"><span data-stu-id="4eec8-136">Action center</span></span>

1. <span data-ttu-id="4eec8-137">ポータル ( ) Microsoft 365 Defender開 <https://security.microsoft.com> き、サインインします。</span><span class="sxs-lookup"><span data-stu-id="4eec8-137">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="4eec8-138">ナビゲーション ウィンドウで、[アクション センター] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4eec8-138">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="4eec8-139">[保留中 **] タブ** で、承認を待っているアクションの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-139">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
   - <span data-ttu-id="4eec8-140">[ **調査ページを開く]** を選択して、調査の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-140">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="4eec8-141">[承認 **] を** 選択して保留中のアクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-141">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="4eec8-142">保留中 **のアクション** が実行されるのを防ぐには、[拒否] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-142">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="investigation-and-remediation-investigations-queue"></a><span data-ttu-id="4eec8-143">調査と修復の調査キュー</span><span class="sxs-lookup"><span data-stu-id="4eec8-143">Investigation and remediation investigations queue</span></span>

1. <span data-ttu-id="4eec8-144">ポータル ( ) Microsoft 365 Defender開 <https://security.microsoft.com> き、サインインします。</span><span class="sxs-lookup"><span data-stu-id="4eec8-144">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="4eec8-145">保留中の調査を開きます。</span><span class="sxs-lookup"><span data-stu-id="4eec8-145">Open pending investigations.</span></span>
3. <span data-ttu-id="4eec8-146">[調査] ページで、[保留中のアクション **] タブに移動** します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-146">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="4eec8-147">リストからアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-147">Select an item in the list.</span></span> <span data-ttu-id="4eec8-148">サイド ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="4eec8-148">Its side pane opens.</span></span>
5. <span data-ttu-id="4eec8-149">サイド ウィンドウで、承認または拒否のアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-149">In the side pane, take approve or reject actions.</span></span>

## <a name="change-or-undo-one-remediation-action"></a><span data-ttu-id="4eec8-150">1 つの修復アクションを変更または元に戻す</span><span class="sxs-lookup"><span data-stu-id="4eec8-150">Change or undo one remediation action</span></span>

<span data-ttu-id="4eec8-151">送信されたアクションを再考するには、次の 2 つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="4eec8-151">There are two different ways to reconsider submitted actions:</span></span>

- <span data-ttu-id="4eec8-152">統合アクション [センターを介して](https://security.microsoft.com/action-center)。</span><span class="sxs-lookup"><span data-stu-id="4eec8-152">Through the [unified action center](https://security.microsoft.com/action-center).</span></span>
- <span data-ttu-id="4eec8-153">しかし[、Officeアクション センター](https://security.microsoft.com/threatincidents)です。</span><span class="sxs-lookup"><span data-stu-id="4eec8-153">Though the [Office action center](https://security.microsoft.com/threatincidents).</span></span>

## <a name="change-or-undo-through-the-unified-action-center"></a><span data-ttu-id="4eec8-154">統合アクション センターで変更または元に戻す</span><span class="sxs-lookup"><span data-stu-id="4eec8-154">Change or undo through the unified action center</span></span>

1. <span data-ttu-id="4eec8-155">統合アクション センター [に移動し、](https://security.microsoft.com/action-center) サインインします。</span><span class="sxs-lookup"><span data-stu-id="4eec8-155">Go to the [unified action center](https://security.microsoft.com/action-center) and sign in.</span></span>
2. <span data-ttu-id="4eec8-156">[履歴 **] タブ** で、変更または元に戻すアクションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-156">On the **History** tab, select an action that you want to change or undo.</span></span>
3. <span data-ttu-id="4eec8-157">画面の右側のウィンドウで、適切なアクション **(受信** トレイに移動、迷惑メールへの移動、削除済みアイテムへの移動、ソフト削除、またはハード削除) を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="4eec8-157">In the pane on the right side of the screen, select the appropriate action (**move to inbox**, **move to junk**, **move to deleted items**, **soft delete**, or **hard delete**).</span></span>

## <a name="change-or-undo-through-the-office-action-center"></a><span data-ttu-id="4eec8-158">変更または元に戻す操作センター Office操作センター</span><span class="sxs-lookup"><span data-stu-id="4eec8-158">Change or undo through the Office action center</span></span>

1. <span data-ttu-id="4eec8-159">[アクション センター] [Officeに移動し](https://security.microsoft.com/threatincidents)、サインインします。</span><span class="sxs-lookup"><span data-stu-id="4eec8-159">Go to the [Office action center](https://security.microsoft.com/threatincidents) and sign in.</span></span>
2. <span data-ttu-id="4eec8-160">適切な修復を選択します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-160">Select the appropriate remediation.</span></span>
3. <span data-ttu-id="4eec8-161">サイド ウィンドウで、メール送信エントリをクリックし、リストが読み込むのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="4eec8-161">In the side pane, click on the mail submissions entry and wait for the list to load.</span></span>
4. <span data-ttu-id="4eec8-162">上部の [アクション] ボタンが有効なのを待ち、[アクション] ボタンを選択してアクションの種類を変更します。</span><span class="sxs-lookup"><span data-stu-id="4eec8-162">Wait for the Action button at the top to enable and select the Action button to change the action type.</span></span>
5. <span data-ttu-id="4eec8-163">これにより、適切なアクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4eec8-163">This will create the appropriate actions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4eec8-164">次の手順</span><span class="sxs-lookup"><span data-stu-id="4eec8-164">Next steps</span></span>

- [<span data-ttu-id="4eec8-165">脅威エクスプローラーの使用</span><span class="sxs-lookup"><span data-stu-id="4eec8-165">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="4eec8-166">管理者/手動アクション</span><span class="sxs-lookup"><span data-stu-id="4eec8-166">Admin /Manual Actions</span></span>](remediate-malicious-email-delivered-office-365.md)
- [<span data-ttu-id="4eec8-167">自動調査および応答機能で誤検知/陰性を報告する方法</span><span class="sxs-lookup"><span data-stu-id="4eec8-167">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="4eec8-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="4eec8-168">See also</span></span>

- [<span data-ttu-id="4eec8-169">自動調査の詳細と結果を表示Office 365</span><span class="sxs-lookup"><span data-stu-id="4eec8-169">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)
