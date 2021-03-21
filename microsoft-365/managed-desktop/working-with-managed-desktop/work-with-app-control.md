---
title: アプリ制御を操作する
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
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917642"
---
# <a name="work-with-app-control"></a><span data-ttu-id="2d448-103">アプリ制御を操作する</span><span class="sxs-lookup"><span data-stu-id="2d448-103">Work with app control</span></span>

<span data-ttu-id="2d448-104">アプリコントロールが環境に展開された後、ユーザーと Microsoft Managed Desktop Operations の両方に継続的な責任があります。</span><span class="sxs-lookup"><span data-stu-id="2d448-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="2d448-105">たとえば、環境に新しいアプリを追加したり、信頼できる署名者を追加 (または削除) することができます。</span><span class="sxs-lookup"><span data-stu-id="2d448-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="2d448-106">セキュリティを強化するには、ユーザーにリリースする前に、すべてのアプリにコード署名が必要です。</span><span class="sxs-lookup"><span data-stu-id="2d448-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="2d448-107">アプリの発行元の詳細には、署名者に関する情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2d448-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="2d448-108">新しいアプリの追加</span><span class="sxs-lookup"><span data-stu-id="2d448-108">Add a new app</span></span>

<span data-ttu-id="2d448-109">新しいアプリを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d448-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="2d448-110">アプリを [Microsoft Intune に追加します](/mem/intune/apps/apps-win32-app-management)。</span><span class="sxs-lookup"><span data-stu-id="2d448-110">Add the app to [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="2d448-111">テスト リング内の任意のデバイスにアプリを展開します。</span><span class="sxs-lookup"><span data-stu-id="2d448-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="2d448-112">標準のビジネス プロセスに従ってアプリをテストします。</span><span class="sxs-lookup"><span data-stu-id="2d448-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="2d448-113">[アプリケーションとサービス ログ **\Microsoft\Windows\AppLocker]** の [イベント ビューアー] で **、8003** イベントまたは **8006** イベントを探します。</span><span class="sxs-lookup"><span data-stu-id="2d448-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="2d448-114">これらのイベントは、アプリがブロックされる可能性を示します。</span><span class="sxs-lookup"><span data-stu-id="2d448-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="2d448-115">すべてのアプリ ロッカー イベントとその意味の詳細については、「Using Event Viewer with [AppLocker」を参照してください](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)。</span><span class="sxs-lookup"><span data-stu-id="2d448-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="2d448-116">これらのイベントが見つけた場合は、Microsoft Managed Desktop Operations を使用して署名者要求を開きます。</span><span class="sxs-lookup"><span data-stu-id="2d448-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="2d448-117">信頼できる署名者を追加 (または削除) する</span><span class="sxs-lookup"><span data-stu-id="2d448-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="2d448-118">署名者要求を開く場合は、最初に重要な発行元の詳細を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d448-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="2d448-119">次に、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2d448-119">Then follow these steps:</span></span>

1. <span data-ttu-id="2d448-120">[発行元の詳細を収集します](#gather-publisher-details)。</span><span class="sxs-lookup"><span data-stu-id="2d448-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="2d448-121">Microsoft Managed Desktop Operations でチケットを開き、署名者ルールを要求し、次の詳細を含める。</span><span class="sxs-lookup"><span data-stu-id="2d448-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="2d448-122">アプリケーション名</span><span class="sxs-lookup"><span data-stu-id="2d448-122">Application name</span></span> 
    - <span data-ttu-id="2d448-123">アプリケーションのバージョン</span><span class="sxs-lookup"><span data-stu-id="2d448-123">Application version</span></span> 
    - <span data-ttu-id="2d448-124">説明</span><span class="sxs-lookup"><span data-stu-id="2d448-124">Description</span></span> 
    - <span data-ttu-id="2d448-125">変更の種類 ("add" または "remove")</span><span class="sxs-lookup"><span data-stu-id="2d448-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="2d448-126">発行元の詳細 (例: "O= <publisher name> ,L= <location> ,S=State,C=Country")</span><span class="sxs-lookup"><span data-stu-id="2d448-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="2d448-127">アプリの信頼を削除するには、同じ手順に従いますが、[変更の種類] を **[削除]** に *設定します*。</span><span class="sxs-lookup"><span data-stu-id="2d448-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="2d448-128">このスケジュールに従って、運用は展開グループにポリシーを段階的に展開します。</span><span class="sxs-lookup"><span data-stu-id="2d448-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="2d448-129">展開グループ</span><span class="sxs-lookup"><span data-stu-id="2d448-129">Deployment group</span></span>  |<span data-ttu-id="2d448-130">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="2d448-130">Policy type</span></span>  |<span data-ttu-id="2d448-131">Timing</span><span class="sxs-lookup"><span data-stu-id="2d448-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="2d448-132">テスト</span><span class="sxs-lookup"><span data-stu-id="2d448-132">Test</span></span>     |  <span data-ttu-id="2d448-133">監査</span><span class="sxs-lookup"><span data-stu-id="2d448-133">Audit</span></span>       |  <span data-ttu-id="2d448-134">Day 0</span><span class="sxs-lookup"><span data-stu-id="2d448-134">Day 0</span></span>       |
|<span data-ttu-id="2d448-135">第 1</span><span class="sxs-lookup"><span data-stu-id="2d448-135">First</span></span>     | <span data-ttu-id="2d448-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="2d448-136">Enforced</span></span>        | <span data-ttu-id="2d448-137">1 日目</span><span class="sxs-lookup"><span data-stu-id="2d448-137">Day 1</span></span>        |
|<span data-ttu-id="2d448-138">高速</span><span class="sxs-lookup"><span data-stu-id="2d448-138">Fast</span></span>     | <span data-ttu-id="2d448-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="2d448-139">Enforced</span></span>        |  <span data-ttu-id="2d448-140">2 日目</span><span class="sxs-lookup"><span data-stu-id="2d448-140">Day 2</span></span>       |
|<span data-ttu-id="2d448-141">広範な質問</span><span class="sxs-lookup"><span data-stu-id="2d448-141">Broad</span></span>     | <span data-ttu-id="2d448-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="2d448-142">Enforced</span></span>        |  <span data-ttu-id="2d448-143">3 日目</span><span class="sxs-lookup"><span data-stu-id="2d448-143">Day 3</span></span>       |


<span data-ttu-id="2d448-144">ロールアウト中は、いつでも展開を一時停止またはロールバックできます。</span><span class="sxs-lookup"><span data-stu-id="2d448-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="2d448-145">これを行うには、Operations を使用して別のサービス要求を開きます。</span><span class="sxs-lookup"><span data-stu-id="2d448-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="2d448-146">署名者ルールのリリースを一時停止する場合は、別のロールアウトを開始する前に、そのルールをロールバックまたは完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d448-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="2d448-147">発行元の詳細を収集する</span><span class="sxs-lookup"><span data-stu-id="2d448-147">Gather publisher details</span></span>

<span data-ttu-id="2d448-148">アプリの発行元データにアクセスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2d448-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="2d448-149">監査モード ポリシーが適用されているテスト リングで Microsoft Managed Desktop デバイスを探します。</span><span class="sxs-lookup"><span data-stu-id="2d448-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="2d448-150">デバイスにアプリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2d448-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="2d448-151">そのデバイスでイベント ビューアーを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d448-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="2d448-152">イベント ビューアーで、[アプリケーションとサービス ログ **\Microsoft\Windows]** に移動し **、[AppLocker] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="2d448-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="2d448-153">**8003** または **8006** イベントを検索し、イベントから情報をコピーします。</span><span class="sxs-lookup"><span data-stu-id="2d448-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="2d448-154">アプリケーション名</span><span class="sxs-lookup"><span data-stu-id="2d448-154">Application name</span></span> 
    - <span data-ttu-id="2d448-155">アプリケーションのバージョン</span><span class="sxs-lookup"><span data-stu-id="2d448-155">Application version</span></span> 
    - <span data-ttu-id="2d448-156">説明</span><span class="sxs-lookup"><span data-stu-id="2d448-156">Description</span></span> 
    - <span data-ttu-id="2d448-157">発行元の詳細 (例: "O= <publisher name> , L= <location> , S=State, C=Country")</span><span class="sxs-lookup"><span data-stu-id="2d448-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span>