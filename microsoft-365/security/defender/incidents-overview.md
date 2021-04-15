---
title: Microsoft 365 Defender でのインシデント
description: デバイス、ユーザー、メールボックス全体で発生したインシデントを調査します。
keywords: インシデント、アラート、調査、相関、攻撃、マシン、デバイス、ユーザー、複数の ID、ID、メールボックス、メール、365、Microsoft、M365
search.product: eADQiWindows 10XVcnh
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
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5b2baa2041a8cffcea212eb449d40b9a9cbfc22a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759513"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="d74e3-104">Microsoft 365 Defender でのインシデント</span><span class="sxs-lookup"><span data-stu-id="d74e3-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d74e3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d74e3-105">**Applies to:**</span></span>
- <span data-ttu-id="d74e3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d74e3-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="d74e3-107">Microsoft 365 Defender を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="d74e3-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="d74e3-108">[ラボ環境で評価する](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)ことも、[実稼働環境でパイロット プロジェクトを実行する](m365d-pilot.md?ocid=cx-evalpilot)こともできます。</span><span class="sxs-lookup"><span data-stu-id="d74e3-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="d74e3-109">Microsoft 365 Defender のインシデントは、関連付けられたアラートと、攻撃のストーリーを構成する関連データのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="d74e3-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="d74e3-110">Microsoft 365 サービスとアプリは、疑わしいイベントや悪意のあるイベントやアクティビティを検出すると、アラートを作成します。</span><span class="sxs-lookup"><span data-stu-id="d74e3-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="d74e3-111">個々のアラートは、完了または継続的な攻撃に関する貴重な手がかりを提供します。</span><span class="sxs-lookup"><span data-stu-id="d74e3-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="d74e3-112">ただし、攻撃は通常、デバイス、ユーザー、メールボックスなど、さまざまな種類のエンティティに対してさまざまな手法を採用します。</span><span class="sxs-lookup"><span data-stu-id="d74e3-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="d74e3-113">結果は、テナント内の複数のエンティティに対する複数の通知になります。</span><span class="sxs-lookup"><span data-stu-id="d74e3-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="d74e3-114">個々のアラートを組み合わせて攻撃に関する洞察を得る場合は、困難で時間がかかる場合があります。Microsoft 365 Defender は自動的にアラートと関連情報をインシデントに集約します。</span><span class="sxs-lookup"><span data-stu-id="d74e3-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender がエンティティからのイベントをインシデントに関連付ける方法":::

<span data-ttu-id="d74e3-116">Microsoft 365 Defender でのインシデントのこの短い概要 (4 分) をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d74e3-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>
<br>
>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="d74e3-117">関連するアラートをインシデントにグループ化すると、攻撃の包括的なビューが得されます。</span><span class="sxs-lookup"><span data-stu-id="d74e3-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="d74e3-118">たとえば、次の情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="d74e3-118">For example, you can see:</span></span>

- <span data-ttu-id="d74e3-119">攻撃が開始された場所。</span><span class="sxs-lookup"><span data-stu-id="d74e3-119">Where the attack started.</span></span>
- <span data-ttu-id="d74e3-120">どのような戦術が使用されたのか。</span><span class="sxs-lookup"><span data-stu-id="d74e3-120">What tactics were used.</span></span>
- <span data-ttu-id="d74e3-121">攻撃がテナントにどれくらいまで入ったか。</span><span class="sxs-lookup"><span data-stu-id="d74e3-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="d74e3-122">攻撃の範囲 (影響を受けたデバイス、ユーザー、メールボックスの数など)。</span><span class="sxs-lookup"><span data-stu-id="d74e3-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="d74e3-123">攻撃に関連付けられているすべてのデータ。</span><span class="sxs-lookup"><span data-stu-id="d74e3-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="d74e3-124">有効 [にすると、Microsoft](m365d-enable.md)365 Defender は自動化と人工知能を通じて自動的にアラートを調査および解決できます。</span><span class="sxs-lookup"><span data-stu-id="d74e3-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="d74e3-125">また、追加の修復手順を実行して攻撃を解決することもできます。</span><span class="sxs-lookup"><span data-stu-id="d74e3-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="d74e3-126">Microsoft 365 セキュリティ センターのインシデントとアラート</span><span class="sxs-lookup"><span data-stu-id="d74e3-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="d74e3-127">Microsoft 365 セキュリティ センター (& >) のクイック 起動時に、インシデント とアラートのインシデントを[管理 security.microsoft.com。](https://security.microsoft.com) </span><span class="sxs-lookup"><span data-stu-id="d74e3-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="d74e3-128">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="d74e3-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 セキュリティ センターの [インシデント] ページ":::

<span data-ttu-id="d74e3-130">インシデント名を選択すると、インシデントの概要が表示され、追加情報を含むタブにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d74e3-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 セキュリティ センターのインシデントの概要ページの例":::

<span data-ttu-id="d74e3-132">インシデントの追加タブは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d74e3-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="d74e3-133">アラート</span><span class="sxs-lookup"><span data-stu-id="d74e3-133">Alerts</span></span> 

  <span data-ttu-id="d74e3-134">インシデントとその情報に関連するすべてのアラート。</span><span class="sxs-lookup"><span data-stu-id="d74e3-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="d74e3-135">デバイス</span><span class="sxs-lookup"><span data-stu-id="d74e3-135">Devices</span></span>

  <span data-ttu-id="d74e3-136">インシデントの一部または関連付けとして識別されたすべてのデバイス。</span><span class="sxs-lookup"><span data-stu-id="d74e3-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="d74e3-137">ユーザー</span><span class="sxs-lookup"><span data-stu-id="d74e3-137">Users</span></span>

  <span data-ttu-id="d74e3-138">インシデントの一部または関連付けとして識別されたすべてのユーザー。</span><span class="sxs-lookup"><span data-stu-id="d74e3-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="d74e3-139">メールボックス</span><span class="sxs-lookup"><span data-stu-id="d74e3-139">Mailboxes</span></span>

  <span data-ttu-id="d74e3-140">インシデントの一部または関連付けとして識別されたすべてのメールボックス。</span><span class="sxs-lookup"><span data-stu-id="d74e3-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="d74e3-141">調査</span><span class="sxs-lookup"><span data-stu-id="d74e3-141">Investigations</span></span>

  <span data-ttu-id="d74e3-142">インシデント内のアラートによってトリガーされる、すべての自動調査。</span><span class="sxs-lookup"><span data-stu-id="d74e3-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="d74e3-143">証拠と対応</span><span class="sxs-lookup"><span data-stu-id="d74e3-143">Evidence and Response</span></span>

  <span data-ttu-id="d74e3-144">インシデント内のアラートでサポートされているイベントと疑わしいエンティティすべて。</span><span class="sxs-lookup"><span data-stu-id="d74e3-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="d74e3-145">Microsoft 365 セキュリティ センターのインシデントとそのデータとインシデントのタブの関係を次に示します。</span><span class="sxs-lookup"><span data-stu-id="d74e3-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="インシデントとそのデータと Microsoft 365 セキュリティ センターのインシデントのタブとの関係":::

## <a name="next-step"></a><span data-ttu-id="d74e3-147">次の手順</span><span class="sxs-lookup"><span data-stu-id="d74e3-147">Next step</span></span>

<span data-ttu-id="d74e3-148">[インシデント] ページの **インシデント キュー** には、最新のインシデントが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="d74e3-148">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="d74e3-149">ここから、以下の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d74e3-149">From here, you can:</span></span>

- <span data-ttu-id="d74e3-150">重大度などの要因に基 [づいて優先順位](incident-queue.md) を付ける必要があるインシデントを確認します。</span><span class="sxs-lookup"><span data-stu-id="d74e3-150">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="d74e3-151">インシデントの [調査](investigate-incidents.md) を実行します。</span><span class="sxs-lookup"><span data-stu-id="d74e3-151">Perform an [investigation](investigate-incidents.md) of an incident.</span></span>
- <span data-ttu-id="d74e3-152">[インシデントの名前の変更](manage-incidents.md)、割り当て、分類、インシデント管理ワークフローのタグの追加など、インシデントを管理します。</span><span class="sxs-lookup"><span data-stu-id="d74e3-152">[Manage incidents](manage-incidents.md), which includes renaming, assigning them, classifying, and adding tags for your incident management workflow.</span></span>
