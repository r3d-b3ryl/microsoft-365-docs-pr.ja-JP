---
title: Microsoft 365 セキュリティセンターで ServiceNow チケットを作成および追跡する
description: Microsoft 365 セキュリティセンターから ServiceNow のチケットを作成および追跡する方法について説明します。
keywords: security, Microsoft 365, M365, secure score, security center, ServiceNow, チケット, tasks
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: f57fc83f9102e5eeea61deaaadc17203bad030ac
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195537"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="aadf6-104">Microsoft 365 セキュリティセンターで ServiceNow チケットを作成および追跡する</span><span class="sxs-lookup"><span data-stu-id="aadf6-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="aadf6-105">[Microsoft 365 セキュリティセンター](overview-security-center.md)は、ServiceNow のチケットをネイティブに作成および追跡する機能によって強化されました。</span><span class="sxs-lookup"><span data-stu-id="aadf6-105">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="aadf6-106">ServiceNow の詳細情報</span><span class="sxs-lookup"><span data-stu-id="aadf6-106">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="aadf6-107">セキュリティセンターでは、セキュリティ管理者が Microsoft のセキュリティ [で保護されたスコア](microsoft-secure-score.md) 向上アクションを ServiceNow に直接送信して、チケットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="aadf6-107">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="aadf6-108">インシデント管理チケットと変更管理チケットの両方を作成できます。</span><span class="sxs-lookup"><span data-stu-id="aadf6-108">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="aadf6-109">セキュリティセンターのホームページと ServiceNow のチケットを追跡します。</span><span class="sxs-lookup"><span data-stu-id="aadf6-109">Track tickets in the security center home page and ServiceNow.</span></span>

- [<span data-ttu-id="aadf6-110">**前提条件、データ交換、およびトラブルシューティングについて説明します。**</span><span class="sxs-lookup"><span data-stu-id="aadf6-110">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="aadf6-111">**コンプライアンスセンターで ServiceNow チケットを管理する** (近日中)</span><span class="sxs-lookup"><span data-stu-id="aadf6-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="aadf6-112">Microsoft 365 セキュリティセンターを ServiceNow に接続する</span><span class="sxs-lookup"><span data-stu-id="aadf6-112">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="aadf6-113">Microsoft 365 セキュリティセンターのホームページに移動して、ServiceNow 接続カードを表示します。</span><span class="sxs-lookup"><span data-stu-id="aadf6-113">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![ServiceNow を使用していますか](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="aadf6-115">[ServiceNow に接続] を選択して、[ServiceNow セットアップ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="aadf6-115">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="aadf6-116">指示に従って、Microsoft 365 Connector アプリを承認します。</span><span class="sxs-lookup"><span data-stu-id="aadf6-116">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="aadf6-117">Microsoft 365 セキュリティセンターと ServiceNow 間の接続を承認する前に、インストール手順で作成した統合ユーザーログインとパスワードを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="aadf6-117">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="aadf6-118">個人の資格情報は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="aadf6-118">Do not use your personal credentials.</span></span>

<span data-ttu-id="aadf6-119">指示に従って接続を承認したら、Microsoft 365 セキュリティセンターの接続ページと ServiceNow Microsoft 365 のチケットコネクタアプリの機能の接続状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="aadf6-119">After you've followed the directions and authorized the connection, view the connection status in the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="aadf6-120">これで、タスクの作成を開始する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="aadf6-120">Now you're all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="aadf6-121">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="aadf6-121">Troubleshooting</span></span>

<span data-ttu-id="aadf6-122">接続プロセスで発生する可能性のある一般的なエラーと、それらを解決する方法については、 [「トラブルシューティング」](tickets.md#troubleshooting)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aadf6-122">Learn common errors you may come across in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="aadf6-123">タスクを作成して ServiceNow に共有する</span><span class="sxs-lookup"><span data-stu-id="aadf6-123">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="aadf6-124">統合がセットアップされたら、特定の [Microsoft セキュリティスコア](microsoft-secure-score.md) 向上アクションに基づいて ServiceNow タスクを作成します。</span><span class="sxs-lookup"><span data-stu-id="aadf6-124">Once the integration is set up, create ServiceNow tasks based on specific [Microsoft Secure Score](microsoft-secure-score.md) improvement actions.</span></span> <span data-ttu-id="aadf6-125">Microsoft 365 セキュリティセンターの [セキュリティで保護されたスコアの改善] アクションに移動し、[ **共有**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="aadf6-125">Go to any Secure Score improvement action in the Microsoft 365 security center, and select **Share**.</span></span> <span data-ttu-id="aadf6-126">ドロップダウンオプションの1つは ServiceNow です。</span><span class="sxs-lookup"><span data-stu-id="aadf6-126">One of the dropdown options is ServiceNow.</span></span>

<span data-ttu-id="aadf6-127">タスクが生成され、優先度を設定して、名前、説明、または期限を編集できます。</span><span class="sxs-lookup"><span data-stu-id="aadf6-127">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="aadf6-128">すべての必須フィールドが入力されたら、そのタスクを ServiceNow に送信します。</span><span class="sxs-lookup"><span data-stu-id="aadf6-128">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="aadf6-129">タスクは、Microsoft 365 のセキュリティおよび構成変更要求として ServiceNow に表示されます。</span><span class="sxs-lookup"><span data-stu-id="aadf6-129">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="aadf6-130">チケットを追跡する</span><span class="sxs-lookup"><span data-stu-id="aadf6-130">Track tickets</span></span>

<span data-ttu-id="aadf6-131">ServiceNow 変更管理およびインシデント管理チケットが作成されると、Microsoft 365 セキュリティセンターのホームページのカードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="aadf6-131">Once ServiceNow change management and incident management tickets have been created, they're displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="aadf6-132">これらのカードから、チケットの作成、すべてのチケットの表示、または ServiceNow 構成の管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="aadf6-132">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 変更管理チケット](../../media/change-management-375.png)  ![ServiceNow インシデント管理チケット](../../media/incident-management-375.png)

<span data-ttu-id="aadf6-135">Microsoft 365 セキュリティセンターで ServiceNow 統合を再準備または管理するには、いずれかのカードで **servicenow 構成を管理** するを選択します。</span><span class="sxs-lookup"><span data-stu-id="aadf6-135">To reprovision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="aadf6-136">そこから、現在の ServiceNow 接続を削除し、チケットの状態名をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="aadf6-136">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="aadf6-137">Microsoft 365 セキュリティセンターで ServiceNow チケットが表示されている場合は、自分のタスクが、他のセキュリティダッシュボードアイテムと一緒に追跡および操作できる場所に存在します。</span><span class="sxs-lookup"><span data-stu-id="aadf6-137">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="aadf6-138">リソース</span><span class="sxs-lookup"><span data-stu-id="aadf6-138">Resources</span></span>

- [<span data-ttu-id="aadf6-139">前提条件、データ交換、およびトラブルシューティングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="aadf6-139">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="aadf6-140">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="aadf6-140">Microsoft Secure Score</span></span>](microsoft-secure-score.md)
