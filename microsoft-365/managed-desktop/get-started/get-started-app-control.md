---
title: アプリ制御の使用を開始する
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
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430461"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="bf249-103">アプリ制御の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="bf249-103">Get started with app control</span></span>

<span data-ttu-id="bf249-104">環境でアプリ制御を有効にする前に [、Microsoft Managed Desktop](../service-description/app-control.md) がどのようにアプリを実装し、役割と責任を果たしたのか、必ず確認して理解してください。</span><span class="sxs-lookup"><span data-stu-id="bf249-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="bf249-105">Microsoft Managed Desktop は、セキュリティで保護された基本ポリシーを取得するより困難な側面に注意を引き付け、アプリの制御を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="bf249-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="bf249-106">IT 管理者は、テスト リングでアプリをテストし、警告やエラーが発生した場合はログを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf249-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="bf249-107">アプリで除外が必要な場合は、要求を申請するか、Microsoft Managed Desktop 操作を実行できます (最初に検出したユーザーに応じて)。</span><span class="sxs-lookup"><span data-stu-id="bf249-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="bf249-108">アプリの初期展開</span><span class="sxs-lookup"><span data-stu-id="bf249-108">Initial deployment of apps</span></span>

<span data-ttu-id="bf249-109">アプリを初めて展開する場合、Microsoft Managed Desktop は現在の動作を評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf249-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="bf249-110">アプリ制御を有効にする正確な手順は、デバイスが環境に既に展開されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="bf249-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="bf249-111">まだ使用されていないデバイス</span><span class="sxs-lookup"><span data-stu-id="bf249-111">Devices not yet in use</span></span>

<span data-ttu-id="bf249-112">デバイスがまだ使用されていない場合は、Microsoft Managed Desktop Operations でサービス チケットを開き、アプリコントロールを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="bf249-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="bf249-113">このスケジュールに従って、運用は展開グループにポリシーを段階的に展開します。</span><span class="sxs-lookup"><span data-stu-id="bf249-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="bf249-114">展開グループ</span><span class="sxs-lookup"><span data-stu-id="bf249-114">Deployment group</span></span>  |<span data-ttu-id="bf249-115">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="bf249-115">Policy type</span></span>  |<span data-ttu-id="bf249-116">Timing</span><span class="sxs-lookup"><span data-stu-id="bf249-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="bf249-117">テスト</span><span class="sxs-lookup"><span data-stu-id="bf249-117">Test</span></span>     |  <span data-ttu-id="bf249-118">監査</span><span class="sxs-lookup"><span data-stu-id="bf249-118">Audit</span></span>       |  <span data-ttu-id="bf249-119">Day 0</span><span class="sxs-lookup"><span data-stu-id="bf249-119">Day 0</span></span>       |
|<span data-ttu-id="bf249-120">第 1</span><span class="sxs-lookup"><span data-stu-id="bf249-120">First</span></span>     | <span data-ttu-id="bf249-121">Enforced</span><span class="sxs-lookup"><span data-stu-id="bf249-121">Enforced</span></span>        | <span data-ttu-id="bf249-122">1 日目</span><span class="sxs-lookup"><span data-stu-id="bf249-122">Day 1</span></span>        |
|<span data-ttu-id="bf249-123">高速</span><span class="sxs-lookup"><span data-stu-id="bf249-123">Fast</span></span>     | <span data-ttu-id="bf249-124">Enforced</span><span class="sxs-lookup"><span data-stu-id="bf249-124">Enforced</span></span>        |  <span data-ttu-id="bf249-125">2 日目</span><span class="sxs-lookup"><span data-stu-id="bf249-125">Day 2</span></span>       |
|<span data-ttu-id="bf249-126">広範な質問</span><span class="sxs-lookup"><span data-stu-id="bf249-126">Broad</span></span>     | <span data-ttu-id="bf249-127">Enforced</span><span class="sxs-lookup"><span data-stu-id="bf249-127">Enforced</span></span>        |  <span data-ttu-id="bf249-128">3 日目</span><span class="sxs-lookup"><span data-stu-id="bf249-128">Day 3</span></span>       |

<span data-ttu-id="bf249-129">ロールアウト中はいつでも、別のサービス要求を開き、この展開の一部を一時停止またはロールバックできます。</span><span class="sxs-lookup"><span data-stu-id="bf249-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="bf249-130">既に使用されているデバイス</span><span class="sxs-lookup"><span data-stu-id="bf249-130">Devices already in use</span></span>

<span data-ttu-id="bf249-131">少なくとも 1 つの Microsoft Managed Desktop デバイスが既に使用されている場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bf249-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="bf249-132">Microsoft Managed Desktop Operations でサービス チケットを開き、アプリコントロールを有効にしてください。</span><span class="sxs-lookup"><span data-stu-id="bf249-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="bf249-133">操作によって、監査ポリシー [がすべてのデバイス](../service-description/app-control.md#audit-policy) に展開されます。</span><span class="sxs-lookup"><span data-stu-id="bf249-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="bf249-134">[アプリケーションをテストして](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) 、ブロックされるアプリケーションを確認します。</span><span class="sxs-lookup"><span data-stu-id="bf249-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="bf249-135">アプリケーションがブロックされる場合は、署名者要求 [を開きます](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)。</span><span class="sxs-lookup"><span data-stu-id="bf249-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="bf249-136">テストが完了したら (結果が何であれ)、保留中の署名者要求に気を付け、Operations に通知します。</span><span class="sxs-lookup"><span data-stu-id="bf249-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="bf249-137">このスケジュールに従って、運用は展開グループにポリシーを段階的に展開します。</span><span class="sxs-lookup"><span data-stu-id="bf249-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="bf249-138">展開グループ</span><span class="sxs-lookup"><span data-stu-id="bf249-138">Deployment group</span></span>  |<span data-ttu-id="bf249-139">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="bf249-139">Policy type</span></span>  |<span data-ttu-id="bf249-140">Timing</span><span class="sxs-lookup"><span data-stu-id="bf249-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="bf249-141">テスト</span><span class="sxs-lookup"><span data-stu-id="bf249-141">Test</span></span>     |  <span data-ttu-id="bf249-142">監査</span><span class="sxs-lookup"><span data-stu-id="bf249-142">Audit</span></span>       |  <span data-ttu-id="bf249-143">Day 0</span><span class="sxs-lookup"><span data-stu-id="bf249-143">Day 0</span></span>       |
|<span data-ttu-id="bf249-144">第 1</span><span class="sxs-lookup"><span data-stu-id="bf249-144">First</span></span>     | <span data-ttu-id="bf249-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="bf249-145">Enforced</span></span>        | <span data-ttu-id="bf249-146">1 日目</span><span class="sxs-lookup"><span data-stu-id="bf249-146">Day 1</span></span>        |
|<span data-ttu-id="bf249-147">高速</span><span class="sxs-lookup"><span data-stu-id="bf249-147">Fast</span></span>     | <span data-ttu-id="bf249-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="bf249-148">Enforced</span></span>        |  <span data-ttu-id="bf249-149">要求に応じて一時停止、ロールアウト</span><span class="sxs-lookup"><span data-stu-id="bf249-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="bf249-150">広範な質問</span><span class="sxs-lookup"><span data-stu-id="bf249-150">Broad</span></span>     | <span data-ttu-id="bf249-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="bf249-151">Enforced</span></span>        |  <span data-ttu-id="bf249-152">要求に応じて一時停止、ロールアウト</span><span class="sxs-lookup"><span data-stu-id="bf249-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="bf249-153">ロールアウト中はいつでも、別のサービス要求を開き、この展開の一部を一時停止またはロールバックできます。</span><span class="sxs-lookup"><span data-stu-id="bf249-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



