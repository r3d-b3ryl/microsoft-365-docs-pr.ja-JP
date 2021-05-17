---
title: Microsoft Defender for Endpoint のアラートを確認する
description: 視覚化されたアラート ストーリーやチェーンの各ステップの詳細など、アラート情報を確認します。
keywords: インシデント、インシデント、コンピューター、デバイス、ユーザー、アラート、アラート、調査、グラフ、証拠
ms.prod: m365-security
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: daniha
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.date: 5/1/2020
ms.technology: mde
ms.openlocfilehash: b791f2b62cb4a3f8062c80ceeb04ccfa72f704bc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062132"
---
# <a name="review-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="45182-104">Microsoft Defender for Endpoint のアラートを確認する</span><span class="sxs-lookup"><span data-stu-id="45182-104">Review alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="45182-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="45182-105">**Applies to:**</span></span>
- [<span data-ttu-id="45182-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="45182-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="45182-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="45182-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="45182-108">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="45182-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

<span data-ttu-id="45182-109">Microsoft Defender for Endpoint のアラート ページは、選択したアラートに関連する攻撃信号とアラートを組み合わせて、詳細なアラート ストーリーを作成することで、アラートに対する完全なコンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="45182-109">The alert page in Microsoft Defender for Endpoint provides full context to the alert, by combining attack signals and alerts related to the selected alert, to construct a detailed alert story.</span></span>

<span data-ttu-id="45182-110">組織に影響を与えるアラートに対して、迅速にトリアージ、調査、効果的なアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="45182-110">Quickly triage, investigate, and take effective action on alerts that affect your organization.</span></span> <span data-ttu-id="45182-111">トリガーされた理由と、1 つの場所からの影響を理解します。</span><span class="sxs-lookup"><span data-stu-id="45182-111">Understand why they were triggered, and their impact from one location.</span></span> <span data-ttu-id="45182-112">詳細については、この概要をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="45182-112">Learn more in this overview.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4yiO5]

## <a name="getting-started-with-an-alert"></a><span data-ttu-id="45182-113">アラートの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="45182-113">Getting started with an alert</span></span>

<span data-ttu-id="45182-114">Defender for Endpoint でアラートの名前を選択すると、アラート ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="45182-114">Selecting an alert's name in Defender for Endpoint will land you on its alert page.</span></span> <span data-ttu-id="45182-115">アラート ページでは、すべての情報が選択したアラートのコンテキストで表示されます。</span><span class="sxs-lookup"><span data-stu-id="45182-115">On the alert page, all the information will be shown in context of the selected alert.</span></span> <span data-ttu-id="45182-116">各アラート ページは、次の 4 つのセクションで構成されます。</span><span class="sxs-lookup"><span data-stu-id="45182-116">Each alert page consists of 4 sections:</span></span>

1. <span data-ttu-id="45182-117">**アラート タイトルには** アラートの名前が表示され、ページで選択した情報に関係なく、現在の調査を開始したアラートを通知します。</span><span class="sxs-lookup"><span data-stu-id="45182-117">**The alert title** shows the alert's name and is there to remind you which alert started your current investigation regardless of what you have selected on the page.</span></span>
2. <span data-ttu-id="45182-118">[**影響を受けるアセット**](#review-affected-assets) には、このアラートの影響を受けるデバイスとユーザーのカードが一覧表示され、詳細とアクションをクリックできます。</span><span class="sxs-lookup"><span data-stu-id="45182-118">[**Affected assets**](#review-affected-assets) lists cards of devices and users affected by this alert that are clickable for further information and actions.</span></span>
3. <span data-ttu-id="45182-119">アラート **ストーリーには、** ツリー ビューによって相互接続されたアラートに関連するエンティティすべてが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45182-119">The **alert story** displays all entities related to the alert, interconnected by a tree view.</span></span> <span data-ttu-id="45182-120">タイトル内のアラートは、選択したアラートのページに最初に移動するときにフォーカスが入ったアラートです。</span><span class="sxs-lookup"><span data-stu-id="45182-120">The alert in the title will be the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="45182-121">アラート ストーリー内のエンティティは展開可能でクリック可能で、アラート ページのコンテキストでアクションを実行することで、追加情報を提供し、応答を迅速に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="45182-121">Entities in the alert story are expandable and clickable, to provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> <span data-ttu-id="45182-122">アラート ストーリーを使用して調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="45182-122">Use the alert story to start your investigation.</span></span> <span data-ttu-id="45182-123">詳細については [、「Microsoft Defender for Endpoint のアラートを調査する」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)。</span><span class="sxs-lookup"><span data-stu-id="45182-123">Learn how in [Investigate alerts in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>
4. <span data-ttu-id="45182-124">詳細 **ウィンドウには、** 最初に選択したアラートの詳細が表示され、このアラートに関連する詳細とアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45182-124">The **details pane** will show the details of the selected alert at first, with details and actions related to this alert.</span></span> <span data-ttu-id="45182-125">アラート ストーリーで影響を受けるアセットまたはエンティティを選択すると、詳細ウィンドウが変更され、選択したオブジェクトのコンテキスト情報とアクションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="45182-125">If you select any of the affected assets or entities in the alert story, the details pane will change to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="45182-126">アラートの検出状態に注意してください。</span><span class="sxs-lookup"><span data-stu-id="45182-126">Note the detection status for your alert.</span></span> 
- <span data-ttu-id="45182-127">[防止] – 不審なアクションが回避されました。</span><span class="sxs-lookup"><span data-stu-id="45182-127">Prevented – The attempted suspicious action was avoided.</span></span> <span data-ttu-id="45182-128">たとえば、ファイルがディスクに書き込まれたり、実行された場合などです。</span><span class="sxs-lookup"><span data-stu-id="45182-128">For example, a file either wasn’t written to disk or executed.</span></span>
<span data-ttu-id="45182-129">![脅威を示すアラート ページが防止されました](images/detstat-prevented.png)</span><span class="sxs-lookup"><span data-stu-id="45182-129">![An alert page showing threat was prevented](images/detstat-prevented.png)</span></span>
- <span data-ttu-id="45182-130">Blocked – 疑わしい動作が実行され、ブロックされました。</span><span class="sxs-lookup"><span data-stu-id="45182-130">Blocked – Suspicious behavior was executed and then blocked.</span></span> <span data-ttu-id="45182-131">たとえば、プロセスは実行されましたが、その後疑わしい動作が発生したため、プロセスは終了しました。</span><span class="sxs-lookup"><span data-stu-id="45182-131">For example, a process was executed but because it subsequently exhibited suspicious behaviors, the process was terminated.</span></span>
<span data-ttu-id="45182-132">![脅威がブロックされたという警告ページ](images/detstat-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="45182-132">![An alert page showing threat was blocked](images/detstat-blocked.png)</span></span>
- <span data-ttu-id="45182-133">検出された – 攻撃が検出され、現在もアクティブな可能性があります。</span><span class="sxs-lookup"><span data-stu-id="45182-133">Detected – An attack was detected and is possibly still active.</span></span>
<span data-ttu-id="45182-134">![脅威を示すアラート ページが検出されました](images/detstat-detected.png)</span><span class="sxs-lookup"><span data-stu-id="45182-134">![An alert page showing threat was detected](images/detstat-detected.png)</span></span>




<span data-ttu-id="45182-135">その後、アラートの詳細ウィンドウで自動調査の詳細を確認し、既に実行されたアクションを確認し、推奨されるアクションに関するアラートの説明を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="45182-135">You can then also review the *automated investigation details* in your alert's details pane, to see which actions were already taken, as well as reading the alert's description for recommended actions.</span></span>

![警告の説明と自動調査セクションが強調表示された詳細ウィンドウのスニペット](images/alert-air-and-alert-description.png)

<span data-ttu-id="45182-137">アラートが開いた場合に詳細ウィンドウで使用できるその他の情報には、MITRE の手法、ソース、その他のコンテキストの詳細が含まれます。</span><span class="sxs-lookup"><span data-stu-id="45182-137">Other information available in the details pane when the alert opens includes MITRE techniques, source, and additional contextual details.</span></span>




## <a name="review-affected-assets"></a><span data-ttu-id="45182-138">影響を受けるアセットを確認する</span><span class="sxs-lookup"><span data-stu-id="45182-138">Review affected assets</span></span>

<span data-ttu-id="45182-139">影響を受けるアセット セクションでデバイスまたはユーザー カードを選択すると、詳細ウィンドウでデバイスまたはユーザーの詳細に切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="45182-139">Selecting a device or a user card in the affected assets sections will switch to the details of the device or user in the details pane.</span></span>

- <span data-ttu-id="45182-140">**デバイスの** 場合、詳細ウィンドウには、ドメイン、オペレーティング システム、IP など、デバイス自体に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45182-140">**For devices**, the details pane will display information about the device itself, like Domain, Operating System, and IP.</span></span> <span data-ttu-id="45182-141">アクティブな通知と、そのデバイス上のログオンしているユーザーも利用できます。</span><span class="sxs-lookup"><span data-stu-id="45182-141">Active alerts and the logged on users on that device are also available.</span></span> <span data-ttu-id="45182-142">デバイスを分離したり、アプリの実行を制限したり、ウイルス対策スキャンを実行したりすることで、すぐにアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="45182-142">You can take immediate action by isolating the device, restricting app execution, or running an antivirus scan.</span></span> <span data-ttu-id="45182-143">または、調査パッケージを収集したり、自動調査を開始したり、デバイス ページに移動してデバイスの観点から調査することもできます。</span><span class="sxs-lookup"><span data-stu-id="45182-143">Alternatively, you could collect an investigation package, initiate an automated investigation, or go to the device page to investigate from the device's point of view.</span></span>

   ![デバイスが選択されている場合の詳細ウィンドウのスニペット](images/device-page-details.png)

- <span data-ttu-id="45182-145">**ユーザーの** 場合、詳細ウィンドウには、ユーザーの SAM 名や SID などの詳細なユーザー情報と、このユーザーが実行するログオンの種類、およびユーザーに関連するアラートとインシデントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45182-145">**For users**, the details pane will display detailed user information, such as the user's SAM name and SID, as well as logon types performed by this user and any alerts and incidents related to it.</span></span> <span data-ttu-id="45182-146">[ユーザー ページを *開く]* を選択すると、そのユーザーの視点から調査を続行できます。</span><span class="sxs-lookup"><span data-stu-id="45182-146">You can select *Open user page* to continue the investigation from that user's point of view.</span></span>

   ![ユーザーが選択されている場合の詳細ウィンドウのスニペット](images/user-page-details.png)


## <a name="related-topics"></a><span data-ttu-id="45182-148">関連項目</span><span class="sxs-lookup"><span data-stu-id="45182-148">Related topics</span></span>

- [<span data-ttu-id="45182-149">インシデント キューの表示と整理</span><span class="sxs-lookup"><span data-stu-id="45182-149">View and organize the incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="45182-150">インシデントの調査</span><span class="sxs-lookup"><span data-stu-id="45182-150">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="45182-151">インシデントの管理</span><span class="sxs-lookup"><span data-stu-id="45182-151">Manage incidents</span></span>](manage-incidents.md)
