---
title: Microsoft Defender for Endpoint アラートの調査
description: 調査オプションを使用して、ネットワークに影響を与えるアラートの詳細、その意味、解決方法を確認します。
keywords: 調査、調査、デバイス、デバイス、アラート キュー、ダッシュボード、IP アドレス、ファイル、提出、提出、詳細分析、タイムライン、検索、ドメイン、URL、IP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 8b3b864e716957c24893d2097249440b0a90f10a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186103"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="fe26a-104">Microsoft Defender for Endpoint のアラートを調査する</span><span class="sxs-lookup"><span data-stu-id="fe26a-104">Investigate alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fe26a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="fe26a-105">**Applies to:**</span></span>
- [<span data-ttu-id="fe26a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="fe26a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fe26a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fe26a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="fe26a-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="fe26a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fe26a-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="fe26a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

<span data-ttu-id="fe26a-110">ネットワークに影響を与えるアラートを調査し、その意味と解決方法を理解します。</span><span class="sxs-lookup"><span data-stu-id="fe26a-110">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>

<span data-ttu-id="fe26a-111">アラート キューからアラートを選択して、アラート ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="fe26a-111">Select an alert from the alerts queue to go to alert page.</span></span> <span data-ttu-id="fe26a-112">このビューには、アラート タイトル、影響を受けるアセット、詳細サイド ウィンドウ、およびアラート ストーリーが含まれる。</span><span class="sxs-lookup"><span data-stu-id="fe26a-112">This view contains the alert title, the affected assets, the details side pane, and the alert story.</span></span>

<span data-ttu-id="fe26a-113">アラート ページから、影響を受けるアセットまたはアラート ストーリー ツリー ビューのエンティティを選択して調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="fe26a-113">From the alert page, begin your investigation by selecting the affected assets or any of the entities under the alert story tree view.</span></span> <span data-ttu-id="fe26a-114">詳細ウィンドウには、選択した内容に関する詳細情報が自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe26a-114">The details pane automatically populates with further information about what you selected.</span></span> <span data-ttu-id="fe26a-115">ここで表示できる情報の種類を確認するには、「エンドポイント用 Microsoft Defender でアラートを確認 [する」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts)。</span><span class="sxs-lookup"><span data-stu-id="fe26a-115">To see what kind of information you can view here, read [Review alerts in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts).</span></span>

## <a name="investigate-using-the-alert-story"></a><span data-ttu-id="fe26a-116">アラート ストーリーを使用して調査する</span><span class="sxs-lookup"><span data-stu-id="fe26a-116">Investigate using the alert story</span></span>

<span data-ttu-id="fe26a-117">アラート ストーリーは、アラートがトリガーされた理由、その前と後で発生した関連イベント、および他の関連エンティティの詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="fe26a-117">The alert story details why the alert was triggered, related events that happened before and after, as well as other related entities.</span></span>

<span data-ttu-id="fe26a-118">エンティティはクリック可能で、アラートではないすべてのエンティティは、そのエンティティのカードの右側にある展開アイコンを使用して展開できます。</span><span class="sxs-lookup"><span data-stu-id="fe26a-118">Entities are clickable and every entity that isn't an alert is expandable using the expand icon on the right side of that entity's card.</span></span> <span data-ttu-id="fe26a-119">フォーカスのエンティティは、そのエンティティのカードの左側に青いストライプで示され、最初はタイトルのアラートがフォーカスされます。</span><span class="sxs-lookup"><span data-stu-id="fe26a-119">The entity in focus will be indicated by a blue stripe to the left side of that entity's card, with the alert in the title being in focus at first.</span></span>

<span data-ttu-id="fe26a-120">エンティティを展開して詳細を一目で確認します。</span><span class="sxs-lookup"><span data-stu-id="fe26a-120">Expand entities to view details at a glance.</span></span> <span data-ttu-id="fe26a-121">エンティティを選択すると、詳細ウィンドウのコンテキストがこのエンティティに切り替わるので、詳細情報を確認し、そのエンティティを管理できます。</span><span class="sxs-lookup"><span data-stu-id="fe26a-121">Selecting an entity will switch the context of the details pane to this entity, and will allow you to review further information, as well as manage that entity.</span></span> <span data-ttu-id="fe26a-122">エンティティ カード *の右側にある ...* を選択すると、そのエンティティで使用可能なすべてのアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe26a-122">Selecting *...* to the right of the entity card will reveal all actions available for that entity.</span></span> <span data-ttu-id="fe26a-123">これらの同じアクションは、エンティティにフォーカスがある場合に詳細ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe26a-123">These same actions appear in the details pane when that entity is in focus.</span></span>

> [!NOTE]
> <span data-ttu-id="fe26a-124">[アラート ストーリー] セクションには複数のアラートが含まれている場合があります。選択したアラートの前または後に、同じ実行ツリーに関連する追加のアラートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe26a-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

![アラートにフォーカスがあるアラート ストーリーと、展開されたカードの例](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a><span data-ttu-id="fe26a-126">詳細ウィンドウからアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="fe26a-126">Take action from the details pane</span></span>

<span data-ttu-id="fe26a-127">目的のエンティティを選択すると、詳細ウィンドウが変更され、選択したエンティティの種類に関する情報、利用可能な場合の歴史的な情報が表示され、アラート ページから直接このエンティティに対してアクションを実行するコントロールが提供されます。</span><span class="sxs-lookup"><span data-stu-id="fe26a-127">Once you've selected an entity of interest, the details pane will change to display information about the selected entity type, historic information when it's available, and offer controls to **take action** on this entity directly from the alert page.</span></span>

<span data-ttu-id="fe26a-128">調査が完了したら、開始したアラートに戻り、アラートの状態を **[** 解決済み] としてマークし、False アラートまたはTrue アラートとして **分類します**。</span><span class="sxs-lookup"><span data-stu-id="fe26a-128">Once you're done investigating, go back to the alert you started with, mark the alert's status as **Resolved** and classify it as either **False alert** or **True alert**.</span></span> <span data-ttu-id="fe26a-129">アラートを分類すると、この機能を調整して、より真のアラートと誤ったアラートを減らします。</span><span class="sxs-lookup"><span data-stu-id="fe26a-129">Classifying alerts helps tune this capability to provide more true alerts and less false alerts.</span></span>

<span data-ttu-id="fe26a-130">真のアラートとして分類する場合は、下の図に示すように、決定を選択できます。</span><span class="sxs-lookup"><span data-stu-id="fe26a-130">If you classify it as a true alert, you can also select a determination, as shown in the image below.</span></span>

![解決済みアラートと判定ドロップダウンが展開された詳細ウィンドウのスニペット](images/alert-details-resolved-true.png)

<span data-ttu-id="fe26a-132">業務用アプリケーションで誤ったアラートが発生している場合は、この種類のアラートを今後回避するために抑制ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe26a-132">If you are experiencing a false alert with a line-of-business application, create a suppression rule to avoid this type of alert in the future.</span></span>

![抑制ルールが強調表示された詳細ウィンドウのアクションと分類](images/alert-false-suppression-rule.png)

> [!TIP]
> <span data-ttu-id="fe26a-134">上記に記載されていない問題が発生した場合は、ボタンを使用してフィードバックを提供するか、サポート 🙂 チケットを開きます。</span><span class="sxs-lookup"><span data-stu-id="fe26a-134">If you're experiencing any issues not described above, use the 🙂 button to provide feedback or open a support ticket.</span></span>


## <a name="related-topics"></a><span data-ttu-id="fe26a-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="fe26a-135">Related topics</span></span>
- [<span data-ttu-id="fe26a-136">Microsoft Defender for Endpoint Alerts キューの表示と整理</span><span class="sxs-lookup"><span data-stu-id="fe26a-136">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="fe26a-137">エンドポイント通知の Microsoft Defender の管理</span><span class="sxs-lookup"><span data-stu-id="fe26a-137">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="fe26a-138">Defender for Endpoint アラートに関連付けられたファイルを調査する</span><span class="sxs-lookup"><span data-stu-id="fe26a-138">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="fe26a-139">Defender for Endpoint Devices リストのデバイスを調査する</span><span class="sxs-lookup"><span data-stu-id="fe26a-139">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="fe26a-140">Defender for Endpoint アラートに関連付けられている IP アドレスを調査する</span><span class="sxs-lookup"><span data-stu-id="fe26a-140">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="fe26a-141">Defender for Endpoint アラートに関連付けられているドメインを調査する</span><span class="sxs-lookup"><span data-stu-id="fe26a-141">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="fe26a-142">Defender for Endpoint のユーザー アカウントを調査する</span><span class="sxs-lookup"><span data-stu-id="fe26a-142">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)


