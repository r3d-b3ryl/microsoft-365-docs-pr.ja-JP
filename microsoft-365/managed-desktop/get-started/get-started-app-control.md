---
title: アプリコントロールの使用を開始する
description: ''
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170711"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="b6e36-103">アプリコントロールの使用を開始する</span><span class="sxs-lookup"><span data-stu-id="b6e36-103">Get started with app control</span></span>

<span data-ttu-id="b6e36-104">ご使用の環境でアプリの制御を有効にする前に、 [Microsoft Managed Desktop が it](../service-description/app-control.md)と自分の役割と責任をどのように実装しているかを確認し、理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="b6e36-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="b6e36-105">Microsoft マネージドデスクトップは、セキュリティで保護された基本ポリシーを取得するためのより困難な側面を考慮することによって、アプリの制御を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="b6e36-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="b6e36-106">IT 管理者は、テストリングでアプリをテストして、警告やエラーのログを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6e36-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="b6e36-107">アプリで除外が必要な場合は、最初に検出したユーザーに応じて、要求をファイルにすることも、Microsoft Managed Desktop 操作を実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="b6e36-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="b6e36-108">アプリの初期展開</span><span class="sxs-lookup"><span data-stu-id="b6e36-108">Initial deployment of apps</span></span>

<span data-ttu-id="b6e36-109">最初にアプリを展開するときに、Microsoft マネージドデスクトップは現在の動作を評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6e36-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="b6e36-110">アプリコントロールを有効にするための正確な手順は、デバイスが環境に展開されているかどうかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="b6e36-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="b6e36-111">デバイスは既に使用されています</span><span class="sxs-lookup"><span data-stu-id="b6e36-111">Devices already in use</span></span>

<span data-ttu-id="b6e36-112">少なくとも1つの Microsoft Managed Desktop デバイスが使用されている場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="b6e36-112">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="b6e36-113">アプリコントロールを有効にすることを要求する Microsoft マネージドデスクトップ操作を使用してサービスチケットを開きます。</span><span class="sxs-lookup"><span data-stu-id="b6e36-113">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="b6e36-114">操作によって、すべてのデバイスに[監査ポリシー](../service-description/app-control.md#audit-policy)が展開されます。</span><span class="sxs-lookup"><span data-stu-id="b6e36-114">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="b6e36-115">[アプリケーションをテスト](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app)して、ブロックされるものがないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6e36-115">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="b6e36-116">アプリケーションがブロックされる場合は、[署名者の要求](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)を開きます。</span><span class="sxs-lookup"><span data-stu-id="b6e36-116">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="b6e36-117">テストが完了し、結果が何であっても、操作を通知し、保留中の署名者の要求を記録します。</span><span class="sxs-lookup"><span data-stu-id="b6e36-117">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="b6e36-118">このスケジュールに従って、ポリシーは展開グループに段階的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="b6e36-118">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="b6e36-119">展開グループ</span><span class="sxs-lookup"><span data-stu-id="b6e36-119">Deployment group</span></span>  |<span data-ttu-id="b6e36-120">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="b6e36-120">Policy type</span></span>  |<span data-ttu-id="b6e36-121">Timing</span><span class="sxs-lookup"><span data-stu-id="b6e36-121">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b6e36-122">テスト</span><span class="sxs-lookup"><span data-stu-id="b6e36-122">Test</span></span>     |  <span data-ttu-id="b6e36-123">監査</span><span class="sxs-lookup"><span data-stu-id="b6e36-123">Audit</span></span>       |  <span data-ttu-id="b6e36-124">0日</span><span class="sxs-lookup"><span data-stu-id="b6e36-124">Day 0</span></span>       |
|<span data-ttu-id="b6e36-125">第 1</span><span class="sxs-lookup"><span data-stu-id="b6e36-125">First</span></span>     | <span data-ttu-id="b6e36-126">Enforced</span><span class="sxs-lookup"><span data-stu-id="b6e36-126">Enforced</span></span>        | <span data-ttu-id="b6e36-127">1 日目</span><span class="sxs-lookup"><span data-stu-id="b6e36-127">Day 1</span></span>        |
|<span data-ttu-id="b6e36-128">高速</span><span class="sxs-lookup"><span data-stu-id="b6e36-128">Fast</span></span>     | <span data-ttu-id="b6e36-129">Enforced</span><span class="sxs-lookup"><span data-stu-id="b6e36-129">Enforced</span></span>        |  <span data-ttu-id="b6e36-130">3 日目</span><span class="sxs-lookup"><span data-stu-id="b6e36-130">Day 3</span></span>       |
|<span data-ttu-id="b6e36-131">広範な質問</span><span class="sxs-lookup"><span data-stu-id="b6e36-131">Broad</span></span>     | <span data-ttu-id="b6e36-132">Enforced</span><span class="sxs-lookup"><span data-stu-id="b6e36-132">Enforced</span></span>        |  <span data-ttu-id="b6e36-133">7 日目</span><span class="sxs-lookup"><span data-stu-id="b6e36-133">Day 7</span></span>       |

<span data-ttu-id="b6e36-134">いつでも別のサービス要求を開いて、いつでもこの展開の一部を停止またはロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6e36-134">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="b6e36-135">まだ使用されていないデバイス</span><span class="sxs-lookup"><span data-stu-id="b6e36-135">Devices not yet in use</span></span>

<span data-ttu-id="b6e36-136">まだ使用しているデバイスがない場合は、Microsoft マネージドデスクトップ操作を使用してサービスチケットを開いて、アプリのコントロールを有効にするように要求します。</span><span class="sxs-lookup"><span data-stu-id="b6e36-136">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="b6e36-137">このスケジュールに従って、ポリシーは展開グループに段階的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="b6e36-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="b6e36-138">展開グループ</span><span class="sxs-lookup"><span data-stu-id="b6e36-138">Deployment group</span></span>  |<span data-ttu-id="b6e36-139">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="b6e36-139">Policy type</span></span>  |<span data-ttu-id="b6e36-140">Timing</span><span class="sxs-lookup"><span data-stu-id="b6e36-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="b6e36-141">テスト</span><span class="sxs-lookup"><span data-stu-id="b6e36-141">Test</span></span>     |  <span data-ttu-id="b6e36-142">監査</span><span class="sxs-lookup"><span data-stu-id="b6e36-142">Audit</span></span>       |  <span data-ttu-id="b6e36-143">0日</span><span class="sxs-lookup"><span data-stu-id="b6e36-143">Day 0</span></span>       |
|<span data-ttu-id="b6e36-144">第 1</span><span class="sxs-lookup"><span data-stu-id="b6e36-144">First</span></span>     | <span data-ttu-id="b6e36-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="b6e36-145">Enforced</span></span>        | <span data-ttu-id="b6e36-146">1 日目</span><span class="sxs-lookup"><span data-stu-id="b6e36-146">Day 1</span></span>        |
|<span data-ttu-id="b6e36-147">高速</span><span class="sxs-lookup"><span data-stu-id="b6e36-147">Fast</span></span>     | <span data-ttu-id="b6e36-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="b6e36-148">Enforced</span></span>        |  <span data-ttu-id="b6e36-149">3 日目</span><span class="sxs-lookup"><span data-stu-id="b6e36-149">Day 3</span></span>       |
|<span data-ttu-id="b6e36-150">広範な質問</span><span class="sxs-lookup"><span data-stu-id="b6e36-150">Broad</span></span>     | <span data-ttu-id="b6e36-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="b6e36-151">Enforced</span></span>        |  <span data-ttu-id="b6e36-152">7 日目</span><span class="sxs-lookup"><span data-stu-id="b6e36-152">Day 7</span></span>       |

<span data-ttu-id="b6e36-153">いつでも別のサービス要求を開いて、いつでもこの展開の一部を停止またはロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6e36-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

