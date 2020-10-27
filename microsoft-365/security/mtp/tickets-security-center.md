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
ms.openlocfilehash: 8992efdd79295b6b56b8f033bd97b10f59a7a4d5
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769677"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a><span data-ttu-id="622dd-104">Microsoft 365 セキュリティセンターで ServiceNow チケットを作成および追跡する</span><span class="sxs-lookup"><span data-stu-id="622dd-104">Create and track ServiceNow tickets in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
><span data-ttu-id="622dd-105">**ServiceNow コネクタのプレビュー期間は終了しています**</span><span class="sxs-lookup"><span data-stu-id="622dd-105">**The preview period for the ServiceNow connector is ending**</span></span><br>
><span data-ttu-id="622dd-106">この機能は、2020年11月末までは利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="622dd-106">This capability will no longer available by the end of November 2020.</span></span> <span data-ttu-id="622dd-107">フィードバックをお寄せいただきありがとうございます。次の手順を決定しています。</span><span class="sxs-lookup"><span data-stu-id="622dd-107">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="622dd-108">[Microsoft 365 セキュリティセンター](overview-security-center.md)は、ServiceNow のチケットをネイティブに作成および追跡する機能によって強化されました。</span><span class="sxs-lookup"><span data-stu-id="622dd-108">The [Microsoft 365 security center](overview-security-center.md) has been enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> [<span data-ttu-id="622dd-109">ServiceNow の詳細情報</span><span class="sxs-lookup"><span data-stu-id="622dd-109">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="622dd-110">セキュリティセンターでは、セキュリティ管理者が Microsoft のセキュリティ [で保護されたスコア](microsoft-secure-score.md) 向上アクションを ServiceNow に直接送信して、チケットを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="622dd-110">In the security center, security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="622dd-111">インシデント管理チケットと変更管理チケットの両方を作成できます。</span><span class="sxs-lookup"><span data-stu-id="622dd-111">Both incident management and change management tickets can be created.</span></span> <span data-ttu-id="622dd-112">セキュリティセンターのホームページと ServiceNow のチケットを追跡します。</span><span class="sxs-lookup"><span data-stu-id="622dd-112">Track tickets in the security center home page and ServiceNow.</span></span>

- [<span data-ttu-id="622dd-113">**前提条件、データ交換、およびトラブルシューティングについて説明します。**</span><span class="sxs-lookup"><span data-stu-id="622dd-113">**Learn about prerequisites, data exchange, and troubleshooting**</span></span>](tickets.md)
- <span data-ttu-id="622dd-114">**コンプライアンスセンターで ServiceNow チケットを管理する** (利用不可)</span><span class="sxs-lookup"><span data-stu-id="622dd-114">**Manage ServiceNow tickets in the compliance center** (not available)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="622dd-115">Microsoft 365 セキュリティセンターを ServiceNow に接続する</span><span class="sxs-lookup"><span data-stu-id="622dd-115">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="622dd-116">Microsoft 365 セキュリティセンターのホームページに移動して、ServiceNow 接続カードを表示します。</span><span class="sxs-lookup"><span data-stu-id="622dd-116">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![ServiceNow を使用していますか](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="622dd-118">[ServiceNow に接続] を選択して、[ServiceNow セットアップ] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="622dd-118">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="622dd-119">指示に従って、Microsoft 365 Connector アプリを承認します。</span><span class="sxs-lookup"><span data-stu-id="622dd-119">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="622dd-120">Microsoft 365 セキュリティセンターと ServiceNow 間の接続を承認する前に、インストール手順で作成した統合ユーザーログインとパスワードを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="622dd-120">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="622dd-121">個人の資格情報は使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="622dd-121">Do not use your personal credentials.</span></span>

<span data-ttu-id="622dd-122">指示に従って接続を承認したら、Microsoft 365 セキュリティセンターの接続ページと ServiceNow Microsoft 365 のチケットコネクタアプリの機能の接続状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="622dd-122">After you've followed the directions and authorized the connection, view the connection status in the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="622dd-123">これで、タスクの作成を開始する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="622dd-123">Now you're all set to start creating tasks!</span></span>

### <a name="troubleshooting"></a><span data-ttu-id="622dd-124">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="622dd-124">Troubleshooting</span></span>

<span data-ttu-id="622dd-125">接続プロセスで発生する可能性のある一般的なエラーと、それらを解決する方法については、 [「トラブルシューティング」](tickets.md#troubleshooting)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="622dd-125">Learn common errors you may come across in the connection process, and how to mitigate them, in the [troubleshooting section](tickets.md#troubleshooting).</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="622dd-126">タスクを作成して ServiceNow に共有する</span><span class="sxs-lookup"><span data-stu-id="622dd-126">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="622dd-127">統合がセットアップされたら、特定の [Microsoft セキュリティスコア](microsoft-secure-score.md) 向上アクションに基づいて ServiceNow タスクを作成します。</span><span class="sxs-lookup"><span data-stu-id="622dd-127">Once the integration is set up, create ServiceNow tasks based on specific [Microsoft Secure Score](microsoft-secure-score.md) improvement actions.</span></span> <span data-ttu-id="622dd-128">Microsoft 365 セキュリティセンターの [セキュリティで保護されたスコアの改善] アクションに移動し、[ **共有** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="622dd-128">Go to any Secure Score improvement action in the Microsoft 365 security center, and select **Share** .</span></span> <span data-ttu-id="622dd-129">ドロップダウンオプションの1つは ServiceNow です。</span><span class="sxs-lookup"><span data-stu-id="622dd-129">One of the dropdown options is ServiceNow.</span></span>

<span data-ttu-id="622dd-130">タスクが生成され、優先度を設定して、名前、説明、または期限を編集できます。</span><span class="sxs-lookup"><span data-stu-id="622dd-130">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="622dd-131">すべての必須フィールドが入力されたら、そのタスクを ServiceNow に送信します。</span><span class="sxs-lookup"><span data-stu-id="622dd-131">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="622dd-132">タスクは、Microsoft 365 のセキュリティおよび構成変更要求として ServiceNow に表示されます。</span><span class="sxs-lookup"><span data-stu-id="622dd-132">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="622dd-133">チケットを追跡する</span><span class="sxs-lookup"><span data-stu-id="622dd-133">Track tickets</span></span>

<span data-ttu-id="622dd-134">ServiceNow 変更管理およびインシデント管理チケットが作成されると、Microsoft 365 セキュリティセンターのホームページのカードに表示されます。</span><span class="sxs-lookup"><span data-stu-id="622dd-134">Once ServiceNow change management and incident management tickets have been created, they're displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="622dd-135">これらのカードから、チケットの作成、すべてのチケットの表示、または ServiceNow 構成の管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="622dd-135">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow 変更管理チケット](../../media/change-management-375.png)  ![ServiceNow インシデント管理チケット](../../media/incident-management-375.png)

<span data-ttu-id="622dd-138">Microsoft 365 セキュリティセンターで ServiceNow 統合を再準備または管理するには、いずれかのカードで **servicenow 構成を管理** するを選択します。</span><span class="sxs-lookup"><span data-stu-id="622dd-138">To reprovision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="622dd-139">そこから、現在の ServiceNow 接続を削除し、チケットの状態名をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="622dd-139">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="622dd-140">Microsoft 365 セキュリティセンターで ServiceNow チケットが表示されている場合は、自分のタスクが、他のセキュリティダッシュボードアイテムと一緒に追跡および操作できる場所に存在します。</span><span class="sxs-lookup"><span data-stu-id="622dd-140">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="resources"></a><span data-ttu-id="622dd-141">リソース</span><span class="sxs-lookup"><span data-stu-id="622dd-141">Resources</span></span>

- [<span data-ttu-id="622dd-142">前提条件、データ交換、およびトラブルシューティングについて説明します。</span><span class="sxs-lookup"><span data-stu-id="622dd-142">Learn about prerequisites, data exchange, and troubleshooting</span></span>](tickets.md)
- [<span data-ttu-id="622dd-143">Microsoft セキュア スコア</span><span class="sxs-lookup"><span data-stu-id="622dd-143">Microsoft Secure Score</span></span>](microsoft-secure-score.md)
