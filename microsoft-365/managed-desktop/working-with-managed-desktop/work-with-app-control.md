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
ms.openlocfilehash: 0b76a14a30caeb75cfdcb8acc5715fe6710e0625
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289461"
---
# <a name="work-with-app-control"></a><span data-ttu-id="cd162-103">アプリ制御を操作する</span><span class="sxs-lookup"><span data-stu-id="cd162-103">Work with app control</span></span>

<span data-ttu-id="cd162-104">ご使用の環境でアプリ管理が展開されると、お客様と Microsoft が管理するデスクトップ操作の両方に、継続的な責任があります。</span><span class="sxs-lookup"><span data-stu-id="cd162-104">Once app control has been deployed in your environment, both you and Microsoft Managed Desktop Operations have ongoing responsibilities.</span></span> <span data-ttu-id="cd162-105">たとえば、環境に新しいアプリを追加したり、信頼できる署名者を追加 (または削除) したりする場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd162-105">For example, you might want to add a new app in the environment or add (or remove) a trusted signer.</span></span> <span data-ttu-id="cd162-106">セキュリティを強化するには、ユーザーにリリースする前に、すべてのアプリをコード署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd162-106">To improve security, all apps should be code-signed before you release them to users.</span></span> <span data-ttu-id="cd162-107">アプリの発行元の詳細には、署名者に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd162-107">An app's publisher details includes information about the signer.</span></span>


## <a name="add-a-new-app"></a><span data-ttu-id="cd162-108">新しいアプリの追加</span><span class="sxs-lookup"><span data-stu-id="cd162-108">Add a new app</span></span>

<span data-ttu-id="cd162-109">新しいアプリを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cd162-109">To add a new app, follow these steps:</span></span>

1. <span data-ttu-id="cd162-110">アプリを [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)に追加します。</span><span class="sxs-lookup"><span data-stu-id="cd162-110">Add the app to [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).</span></span>
2. <span data-ttu-id="cd162-111">アプリをテストリングの任意のデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="cd162-111">Deploy the app to any device in the Test ring.</span></span> 
3. <span data-ttu-id="cd162-112">標準のビジネスプロセスに従ってアプリをテストします。</span><span class="sxs-lookup"><span data-stu-id="cd162-112">Test your app according to your standard business processes.</span></span> 
4. <span data-ttu-id="cd162-113">**Application And Services Logs\Microsoft\Windows\AppLocker**の下にあるイベントビューアーを調べて、 **8003**または**8006**イベントを探します。</span><span class="sxs-lookup"><span data-stu-id="cd162-113">Check Event Viewer under **Application and Services Logs\Microsoft\Windows\AppLocker**, looking for any **8003** or **8006** events.</span></span> <span data-ttu-id="cd162-114">これらのイベントは、アプリがブロックされることを示します。</span><span class="sxs-lookup"><span data-stu-id="cd162-114">These events indicate that the app would be blocked.</span></span> <span data-ttu-id="cd162-115">すべてのアプリケーションのロッカーイベントとその意味については、「 [AppLocker でイベントビューアーを使用する](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cd162-115">For more information about all App Locker events and their meanings, see [Using Event Viewer with AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).</span></span>
5. <span data-ttu-id="cd162-116">これらのイベントのいずれかが見つかった場合は、Microsoft マネージドデスクトップ操作を使用して署名者の要求を開きます。</span><span class="sxs-lookup"><span data-stu-id="cd162-116">If you find any of these events, open a signer request with Microsoft Managed Desktop Operations.</span></span>

## <a name="add-or-remove-a-trusted-signer"></a><span data-ttu-id="cd162-117">信頼できる署名者を追加 (または削除) する</span><span class="sxs-lookup"><span data-stu-id="cd162-117">Add (or remove) a trusted signer</span></span>

<span data-ttu-id="cd162-118">署名者の要求を開くときには、最初にいくつかの重要な発行者の詳細を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd162-118">When you open a signer request, you'll need to provide some important publisher details first.</span></span> <span data-ttu-id="cd162-119">その後、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cd162-119">Then follow these steps:</span></span>

1. <span data-ttu-id="cd162-120">[発行元の詳細を収集](#gather-publisher-details)します。</span><span class="sxs-lookup"><span data-stu-id="cd162-120">[Gather publisher details](#gather-publisher-details).</span></span>
2. <span data-ttu-id="cd162-121">Microsoft マネージドデスクトップ操作でチケットを開き、署名者ルールを要求し、次の詳細情報を含めます。</span><span class="sxs-lookup"><span data-stu-id="cd162-121">Open a ticket with Microsoft Managed Desktop Operations to request the signer rule and include following details:</span></span>  
    - <span data-ttu-id="cd162-122">アプリケーション名</span><span class="sxs-lookup"><span data-stu-id="cd162-122">Application name</span></span> 
    - <span data-ttu-id="cd162-123">アプリケーションのバージョン</span><span class="sxs-lookup"><span data-stu-id="cd162-123">Application version</span></span> 
    - <span data-ttu-id="cd162-124">説明</span><span class="sxs-lookup"><span data-stu-id="cd162-124">Description</span></span> 
    - <span data-ttu-id="cd162-125">変更の種類 ("追加" または "削除")</span><span class="sxs-lookup"><span data-stu-id="cd162-125">Change type ("add" or "remove")</span></span>  
    - <span data-ttu-id="cd162-126">発行元の詳細 (例: "O = <publisher name> , L = <location> , S = State, C = Country")</span><span class="sxs-lookup"><span data-stu-id="cd162-126">Publisher details (for example: “O=<publisher name>,L=<location>,S=State,C=Country”)</span></span> 

> [!NOTE]
> <span data-ttu-id="cd162-127">アプリの信頼を削除するには、同じ手順を実行しますが、[ **変更の種類** ] を [ *削除*] に設定します。</span><span class="sxs-lookup"><span data-stu-id="cd162-127">To remove trust for an app, follow the same steps, but set **Change type** to *remove*.</span></span>

<span data-ttu-id="cd162-128">このスケジュールに従って、ポリシーは展開グループに段階的に展開されます。</span><span class="sxs-lookup"><span data-stu-id="cd162-128">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>


|<span data-ttu-id="cd162-129">展開グループ</span><span class="sxs-lookup"><span data-stu-id="cd162-129">Deployment group</span></span>  |<span data-ttu-id="cd162-130">ポリシーの種類</span><span class="sxs-lookup"><span data-stu-id="cd162-130">Policy type</span></span>  |<span data-ttu-id="cd162-131">Timing</span><span class="sxs-lookup"><span data-stu-id="cd162-131">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="cd162-132">テスト</span><span class="sxs-lookup"><span data-stu-id="cd162-132">Test</span></span>     |  <span data-ttu-id="cd162-133">監査</span><span class="sxs-lookup"><span data-stu-id="cd162-133">Audit</span></span>       |  <span data-ttu-id="cd162-134">0日</span><span class="sxs-lookup"><span data-stu-id="cd162-134">Day 0</span></span>       |
|<span data-ttu-id="cd162-135">第 1</span><span class="sxs-lookup"><span data-stu-id="cd162-135">First</span></span>     | <span data-ttu-id="cd162-136">Enforced</span><span class="sxs-lookup"><span data-stu-id="cd162-136">Enforced</span></span>        | <span data-ttu-id="cd162-137">1 日目</span><span class="sxs-lookup"><span data-stu-id="cd162-137">Day 1</span></span>        |
|<span data-ttu-id="cd162-138">高速</span><span class="sxs-lookup"><span data-stu-id="cd162-138">Fast</span></span>     | <span data-ttu-id="cd162-139">Enforced</span><span class="sxs-lookup"><span data-stu-id="cd162-139">Enforced</span></span>        |  <span data-ttu-id="cd162-140">2 日目</span><span class="sxs-lookup"><span data-stu-id="cd162-140">Day 2</span></span>       |
|<span data-ttu-id="cd162-141">広範な質問</span><span class="sxs-lookup"><span data-stu-id="cd162-141">Broad</span></span>     | <span data-ttu-id="cd162-142">Enforced</span><span class="sxs-lookup"><span data-stu-id="cd162-142">Enforced</span></span>        |  <span data-ttu-id="cd162-143">3 日目</span><span class="sxs-lookup"><span data-stu-id="cd162-143">Day 3</span></span>       |


<span data-ttu-id="cd162-144">ロールアウトの間に、いつでも展開を一時停止またはロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="cd162-144">You can pause or roll back the deployment at any time during the rollout.</span></span> <span data-ttu-id="cd162-145">これを行うには、操作を使用して別のサービス要求を開きます。</span><span class="sxs-lookup"><span data-stu-id="cd162-145">To do this, open another service request with Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="cd162-146">署名者ルールのリリースを一時停止した場合は、別のロールアウトを開始する前に、そのルールをロールバックするか、完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd162-146">If you pause the release of a signer rule, that rule must be either rolled back or completed before another rollout can start.</span></span>

## <a name="gather-publisher-details"></a><span data-ttu-id="cd162-147">発行元の詳細を収集する</span><span class="sxs-lookup"><span data-stu-id="cd162-147">Gather publisher details</span></span>

<span data-ttu-id="cd162-148">アプリの発行元データにアクセスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cd162-148">To access the publisher data for an app, follow these steps:</span></span>

1. <span data-ttu-id="cd162-149">テストリングで監査モードポリシーが適用された Microsoft マネージドデスクトップデバイスを検索します。</span><span class="sxs-lookup"><span data-stu-id="cd162-149">Find a Microsoft Managed Desktop device in the Test ring that has an Audit Mode policy applied.</span></span> 
2. <span data-ttu-id="cd162-150">デバイスにアプリをインストールしようとしています。</span><span class="sxs-lookup"><span data-stu-id="cd162-150">Attempt to install the app on the device.</span></span>
3. <span data-ttu-id="cd162-151">そのデバイスでイベントビューアーを開きます。</span><span class="sxs-lookup"><span data-stu-id="cd162-151">Open Event Viewer on that device.</span></span> 
4. <span data-ttu-id="cd162-152">イベントビューアーで、[ **アプリケーションとサービス Logs\Microsoft\Windows**] に移動し、[ **AppLocker**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="cd162-152">In Event Viewer, navigate to **Application and Services Logs\Microsoft\Windows**, and then select **AppLocker**.</span></span> 
5. <span data-ttu-id="cd162-153">任意の **8003** または **8006** イベントを検索し、そのイベントから情報をコピーします。</span><span class="sxs-lookup"><span data-stu-id="cd162-153">Find any **8003** or **8006** event, and then copy information from the event:</span></span> 
    - <span data-ttu-id="cd162-154">アプリケーション名</span><span class="sxs-lookup"><span data-stu-id="cd162-154">Application name</span></span> 
    - <span data-ttu-id="cd162-155">アプリケーションのバージョン</span><span class="sxs-lookup"><span data-stu-id="cd162-155">Application version</span></span> 
    - <span data-ttu-id="cd162-156">説明</span><span class="sxs-lookup"><span data-stu-id="cd162-156">Description</span></span> 
    - <span data-ttu-id="cd162-157">発行元の詳細 (例: "O = <publisher name> , L = <location> , S = State, C = Country")</span><span class="sxs-lookup"><span data-stu-id="cd162-157">Publisher details (for example: “O=<publisher name>, L=<location>, S=State, C=Country”)</span></span> 
