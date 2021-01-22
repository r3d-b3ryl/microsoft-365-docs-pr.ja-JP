---
title: 自動調査の詳細と結果
description: 自動調査の結果と主な検出事項は、調査の実行中および実行後に表示できます。
keywords: 自動化、調査、結果、分析、詳細、修復、autoair
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
ms.date: 09/16/2020
ms.technology: m365d
ms.openlocfilehash: c050683bb3ed052ae4752ffdee66fe51fb99b88b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930368"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="38f4b-104">自動調査の詳細と結果</span><span class="sxs-lookup"><span data-stu-id="38f4b-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="38f4b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="38f4b-105">**Applies to:**</span></span>
- <span data-ttu-id="38f4b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="38f4b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="38f4b-107">Microsoft 365 Defender で自動調査が行われると、その調査に関する詳細は、自動調査プロセス中および自動調査後に確認できます。</span><span class="sxs-lookup"><span data-stu-id="38f4b-107">When an automated investigation occurs in Microsoft 365 Defender, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="38f4b-108">[必要なアクセス許可](mtp-action-center.md#required-permissions-for-action-center-tasks)を持っている場合は、調査の詳細ビューでこれらの詳細を表示できます。</span><span class="sxs-lookup"><span data-stu-id="38f4b-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="38f4b-109">調査の詳細ビューでは最新の状態が表示され、保留中のアクションを承認する機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="38f4b-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![調査の詳細](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="38f4b-111">調査の詳細ビューを開く</span><span class="sxs-lookup"><span data-stu-id="38f4b-111">Open the investigation details view</span></span>

<span data-ttu-id="38f4b-112">調査の詳細ビューを開くには、次のいずれかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="38f4b-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="38f4b-113">アクション センターでアイテムを選択する</span><span class="sxs-lookup"><span data-stu-id="38f4b-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="38f4b-114">インシデントの詳細ページから調査を選択する</span><span class="sxs-lookup"><span data-stu-id="38f4b-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="38f4b-115">アクション センターでアイテムを選択する</span><span class="sxs-lookup"><span data-stu-id="38f4b-115">Select an item in the Action center</span></span>

<span data-ttu-id="38f4b-116">アクション センターを使用して、承認が保留中のアクション ([**保留中**] タブで) または既に承認されているアクション ([**履歴**] タブで) を表示します。</span><span class="sxs-lookup"><span data-stu-id="38f4b-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="38f4b-117">[https://security.microsoft.com](https://security.microsoft.com) にアクセスし、サインインします。</span><span class="sxs-lookup"><span data-stu-id="38f4b-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="38f4b-118">ナビゲーション ウィンドウで、[**アクション センター**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38f4b-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="38f4b-119">[**保留中**] タブまたは [**履歴**] タブのいずれかでアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="38f4b-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="38f4b-120">[必要なアクセス許可](mtp-action-center.md#required-permissions-for-action-center-tasks)を持っている場合は、保留中のアクションを承認 (または拒否) できます。</span><span class="sxs-lookup"><span data-stu-id="38f4b-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="38f4b-121">インシデントの詳細ページから調査を開く</span><span class="sxs-lookup"><span data-stu-id="38f4b-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="38f4b-122">インシデントの詳細ページを使用して、インシデントに関する詳細情報を表示します。これには、影響を受けたデバイス、ユーザー アカウント、またはメールボックスに関する情報がトリガーされた警告が含まれます。</span><span class="sxs-lookup"><span data-stu-id="38f4b-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="38f4b-123">[https://security.microsoft.com](https://security.microsoft.com) にアクセスし、サインインします。</span><span class="sxs-lookup"><span data-stu-id="38f4b-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="38f4b-124">ナビゲーション ウィンドウで、[**インシデント**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="38f4b-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="38f4b-125">リスト内のアイテムを選択してインシデントの詳細ビューを開きます。</span><span class="sxs-lookup"><span data-stu-id="38f4b-125">Select an item in the list to open the incident details view.</span></span><br/>![インシデントの詳細](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="38f4b-127">[**調査**] タブで、一覧から調査を選択します。</span><span class="sxs-lookup"><span data-stu-id="38f4b-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="38f4b-128">調査の詳細</span><span class="sxs-lookup"><span data-stu-id="38f4b-128">Investigation details</span></span>

<span data-ttu-id="38f4b-129">調査の詳細ビューを使用して、調査に関連する過去、現在、保留中のアクティビティを表示します。</span><span class="sxs-lookup"><span data-stu-id="38f4b-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="38f4b-130">調査の詳細ビューの画像は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="38f4b-130">The investigation details view resembles the following image:</span></span>

![調査の詳細](../../media/mtp-air-investdetails.png)

<span data-ttu-id="38f4b-132">調査の詳細ビューでは、次の表で説明する [**Investigation graph (調査のグラフ)**]、[**Alerts (警告)**]、[**Device (デバイス)**]、[**Identities (ID)**]、[**Key findings (主な検出事項)**]、[**Entities (エンティティ)**]、[**Log (ログ)**]、[**Pending actions (保留中のアクション)**] の各タブに情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38f4b-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

| <span data-ttu-id="38f4b-133">タブ</span><span class="sxs-lookup"><span data-stu-id="38f4b-133">Tab</span></span> | <span data-ttu-id="38f4b-134">説明</span><span class="sxs-lookup"><span data-stu-id="38f4b-134">Description</span></span> |
|--------|--------|
| <span data-ttu-id="38f4b-135">**Investigation graph (調査グラフ)**</span><span class="sxs-lookup"><span data-stu-id="38f4b-135">**Investigation graph**</span></span>   | <span data-ttu-id="38f4b-136">調査を視覚的に表します。</span><span class="sxs-lookup"><span data-stu-id="38f4b-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="38f4b-137">エンティティと検出された脅威のほか、警告、承認を待っているアクションがあるかどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="38f4b-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="38f4b-138">グラフ上のアイテムをクリックすると、詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38f4b-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="38f4b-139">たとえば、[**Threats found (見つかった脅威)**] アイコンをクリックすると、[**Key findings (主な検出事項)**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="38f4b-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
| <span data-ttu-id="38f4b-140">**Alerts**</span><span class="sxs-lookup"><span data-stu-id="38f4b-140">**Alerts**</span></span>    | <span data-ttu-id="38f4b-141">調査に関連する警告を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="38f4b-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="38f4b-142">アラートは、ユーザーのコンピューター、Office アプリ、Cloud App Security、その他の Microsoft 365 Defender 機能の脅威保護機能から発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38f4b-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="38f4b-143">**デバイス**</span><span class="sxs-lookup"><span data-stu-id="38f4b-143">**Devices**</span></span> | <span data-ttu-id="38f4b-144">調査に含まれるコンピューターと修復レベルを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="38f4b-144">Lists machines included in the investigation along with remediation level.</span></span>|
| <span data-ttu-id="38f4b-145">**Key findings (主な検出事項)**</span><span class="sxs-lookup"><span data-stu-id="38f4b-145">**Key findings**</span></span>  | <span data-ttu-id="38f4b-146">調査の結果と共に、状態と実行または保留されているアクションを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="38f4b-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="38f4b-147">このタブでは、デバイスおよび ID に対する保留中のアクションを承認できます。</span><span class="sxs-lookup"><span data-stu-id="38f4b-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
| <span data-ttu-id="38f4b-148">**Entities**</span><span class="sxs-lookup"><span data-stu-id="38f4b-148">**Entities**</span></span>  | <span data-ttu-id="38f4b-149">調査に関連付けられているユーザー アクティビティ、ファイル、プロセス、サービス、ドライバー、IP アドレス、および永続化の方法と共に、状態と実行されたアクションが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="38f4b-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="38f4b-150">**Log**</span><span class="sxs-lookup"><span data-stu-id="38f4b-150">**Log**</span></span>    | <span data-ttu-id="38f4b-151">調査中に実行されたすべてのステップの詳細および状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="38f4b-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
| <span data-ttu-id="38f4b-152">**Pending actions (保留中のアクション)**</span><span class="sxs-lookup"><span data-stu-id="38f4b-152">**Pending actions**</span></span> | <span data-ttu-id="38f4b-153">続けるには承認を必要とするアイテムを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="38f4b-153">Lists items that require approval to proceed.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="38f4b-154">次のステップ</span><span class="sxs-lookup"><span data-stu-id="38f4b-154">Next steps</span></span>

- [<span data-ttu-id="38f4b-155">自動調査と対応に関連するアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="38f4b-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="38f4b-156">修復アクションを確認する</span><span class="sxs-lookup"><span data-stu-id="38f4b-156">Review remediation actions</span></span>](mtp-remediation-actions.md)
