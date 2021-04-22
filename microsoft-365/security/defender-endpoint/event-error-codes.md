---
title: イベント ビューアーを使用してイベントとエラーを確認する
description: Microsoft Defender for Endpoint サービスによって報告されたすべてのイベントの説明とトラブルシューティング手順 (必要に応じて) を取得します。
keywords: トラブルシューティング、イベント ビューアー、ログの概要、エラー コード、失敗した、Microsoft Defender for Endpoint Service、開始できない、壊れている、開始できない
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
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: a8b7268e89470a85a34015967b69abb1818fe64f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933843"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="567fc-104">イベント ビューアーを使用してイベントとエラーを確認する</span><span class="sxs-lookup"><span data-stu-id="567fc-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="567fc-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="567fc-105">**Applies to:**</span></span>
- <span data-ttu-id="567fc-106">イベント ビューアー</span><span class="sxs-lookup"><span data-stu-id="567fc-106">Event Viewer</span></span>
- [<span data-ttu-id="567fc-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="567fc-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="567fc-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="567fc-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="567fc-109">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="567fc-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="567fc-110">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="567fc-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="567fc-111">イベントの ID は、個々のデバイスの [イベント ビューアー](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) で確認できます。</span><span class="sxs-lookup"><span data-stu-id="567fc-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="567fc-112">たとえば、[デバイス] リストにデバイスが表示されない場合は、デバイスでイベントの ID を探す必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="567fc-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="567fc-113">次に、この表を使用して、さらにトラブルシューティングの手順を決定できます。</span><span class="sxs-lookup"><span data-stu-id="567fc-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="567fc-114">**イベント ビューアーを開き、Microsoft Defender for Endpoint サービス イベント ログを検索します。**</span><span class="sxs-lookup"><span data-stu-id="567fc-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="567fc-115">**[Windows] メニューの**[スタート] をクリックし、「イベント ビューアー」**と入力し**、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="567fc-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="567fc-116">ログ リストの [ログの概要 **] で\*\*\*\*、Microsoft-Windows-SENSE/Operational が表示されるまでスクロールします**。</span><span class="sxs-lookup"><span data-stu-id="567fc-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="567fc-117">アイテムをダブルクリックしてログを開きます。</span><span class="sxs-lookup"><span data-stu-id="567fc-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="567fc-118">a.</span><span class="sxs-lookup"><span data-stu-id="567fc-118">a.</span></span>  <span data-ttu-id="567fc-119">[アプリケーションとサービス ログ] Microsoft Windows SENSE を展開して [操作] をクリックして、ログ  >    >    >  に **アクセスすることもできます**。</span><span class="sxs-lookup"><span data-stu-id="567fc-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="567fc-120">SENSE は、Microsoft Defender for Endpoint をサポートする動作センサーを参照するために使用される内部名です。</span><span class="sxs-lookup"><span data-stu-id="567fc-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="567fc-121">サービスによって記録されたイベントがログに表示されます。</span><span class="sxs-lookup"><span data-stu-id="567fc-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="567fc-122">サービスによって記録されるイベントの一覧については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="567fc-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="567fc-123">イベント ID</span><span class="sxs-lookup"><span data-stu-id="567fc-123">Event ID</span></span></th>
<th><span data-ttu-id="567fc-124">メッセージ</span><span class="sxs-lookup"><span data-stu-id="567fc-124">Message</span></span></th>
<th><span data-ttu-id="567fc-125">説明</span><span class="sxs-lookup"><span data-stu-id="567fc-125">Description</span></span></th>
<th><span data-ttu-id="567fc-126">Action</span><span class="sxs-lookup"><span data-stu-id="567fc-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="567fc-127">1</span><span class="sxs-lookup"><span data-stu-id="567fc-127">1</span></span></td>
<td><span data-ttu-id="567fc-128">Microsoft Defender for Endpoint service が開始されました (バージョン <code>variable</code> )。</span><span class="sxs-lookup"><span data-stu-id="567fc-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="567fc-129">システムの起動時、シャットダウン中、オンボーディング中に発生します。</span><span class="sxs-lookup"><span data-stu-id="567fc-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="567fc-130">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-131">2</span><span class="sxs-lookup"><span data-stu-id="567fc-131">2</span></span></td>
<td><span data-ttu-id="567fc-132">Microsoft Defender for Endpoint service shutdown.</span><span class="sxs-lookup"><span data-stu-id="567fc-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="567fc-133">デバイスがシャットダウンまたはオフボードされている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="567fc-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="567fc-134">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-135">3</span><span class="sxs-lookup"><span data-stu-id="567fc-135">3</span></span></td>
<td><span data-ttu-id="567fc-136">Microsoft Defender for Endpoint service の開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="567fc-137">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-138">サービスが開始しなかった。</span><span class="sxs-lookup"><span data-stu-id="567fc-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="567fc-139">他のメッセージを確認して、考えられる原因とトラブルシューティングの手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-140">4</span><span class="sxs-lookup"><span data-stu-id="567fc-140">4</span></span></td>
<td><span data-ttu-id="567fc-141">Microsoft Defender for Endpoint service がでサーバーに連絡しました <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="567fc-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-142">Variable = Defender for Endpoint 処理サーバーの URL。</span><span class="sxs-lookup"><span data-stu-id="567fc-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="567fc-143">この URL は、ファイアウォールまたはネットワーク アクティビティに表示される URL と一致します。</span><span class="sxs-lookup"><span data-stu-id="567fc-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="567fc-144">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-145">5</span><span class="sxs-lookup"><span data-stu-id="567fc-145">5</span></span></td>
<td><span data-ttu-id="567fc-146">Microsoft Defender for Endpoint service でサーバーへの接続に失敗しました <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="567fc-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-147">Variable = Defender for Endpoint 処理サーバーの URL。</span><span class="sxs-lookup"><span data-stu-id="567fc-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="567fc-148">サービスは、その URL の外部処理サーバーに接続できません。</span><span class="sxs-lookup"><span data-stu-id="567fc-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="567fc-149">URL への接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-149">Check the connection to the URL.</span></span> <span data-ttu-id="567fc-150">「Configure <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">proxy and Internet connectivity」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-151">6</span><span class="sxs-lookup"><span data-stu-id="567fc-151">6</span></span></td>
<td><span data-ttu-id="567fc-152">Microsoft Defender for Endpoint Service はオンボードされていないので、オンボーディング パラメーターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="567fc-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="567fc-153">デバイスが正しくオンボードされていないので、ポータルに報告されません。</span><span class="sxs-lookup"><span data-stu-id="567fc-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="567fc-154">サービスを開始する前にオンボーディングを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="567fc-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="567fc-155">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="567fc-156">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="567fc-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="567fc-157">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-158">7</span><span class="sxs-lookup"><span data-stu-id="567fc-158">7</span></span></td>
<td><span data-ttu-id="567fc-159">Microsoft Defender for Endpoint service では、オンボーディング パラメーターの読み取りが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="567fc-160">失敗: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-161">変数 = 詳細なエラーの説明。</span><span class="sxs-lookup"><span data-stu-id="567fc-161">Variable = detailed error description.</span></span> <span data-ttu-id="567fc-162">デバイスが正しくオンボードされていないので、ポータルに報告されません。</span><span class="sxs-lookup"><span data-stu-id="567fc-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="567fc-163">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="567fc-164">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="567fc-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="567fc-165">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-166">8</span><span class="sxs-lookup"><span data-stu-id="567fc-166">8</span></span></td>
<td><span data-ttu-id="567fc-167">Microsoft Defender for Endpoint service では、構成のクリーンアップに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="567fc-168">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-169"><b>オンボーディング中:</b> サービスは、オンボーディング中に構成のクリーンアップに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="567fc-170">オンボーディング プロセスは続行されます。</span><span class="sxs-lookup"><span data-stu-id="567fc-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="567fc-171"><b>オフボード中:</b> サービスは、オフボード中に構成のクリーンアップに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="567fc-172">オフボード プロセスは終了しましたが、サービスは実行を続ける。</span><span class="sxs-lookup"><span data-stu-id="567fc-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="567fc-173"><b>オンボーディング:</b> アクションは不要です。</span><span class="sxs-lookup"><span data-stu-id="567fc-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="567fc-174"><b>オフボード:</b> システムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="567fc-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="567fc-175">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-176">9</span><span class="sxs-lookup"><span data-stu-id="567fc-176">9</span></span></td>
<td><span data-ttu-id="567fc-177">Microsoft Defender for Endpoint service は、開始の種類を変更できなかった。</span><span class="sxs-lookup"><span data-stu-id="567fc-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="567fc-178">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-179"><b>オンボーディング中:</b> デバイスが正しくオンボードされていないので、ポータルに報告されません。</span><span class="sxs-lookup"><span data-stu-id="567fc-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="567fc-180"><b>オフボード中:</b> サービスの開始の種類を変更できなかった。</span><span class="sxs-lookup"><span data-stu-id="567fc-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="567fc-181">オフボードプロセスは続行されます。</span><span class="sxs-lookup"><span data-stu-id="567fc-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="567fc-182">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="567fc-183">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="567fc-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="567fc-184">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-185">10</span><span class="sxs-lookup"><span data-stu-id="567fc-185">10</span></span></td>
<td><span data-ttu-id="567fc-186">Microsoft Defender for Endpoint Service は、オンボーディング情報を保持できなかった。</span><span class="sxs-lookup"><span data-stu-id="567fc-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="567fc-187">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-188">デバイスが正しくオンボードされていないので、ポータルに報告されません。</span><span class="sxs-lookup"><span data-stu-id="567fc-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="567fc-189">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="567fc-190">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="567fc-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="567fc-191">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-192">11</span><span class="sxs-lookup"><span data-stu-id="567fc-192">11</span></span></td>
<td><span data-ttu-id="567fc-193">Defender for Endpoint サービスのオンボーディングまたは再オンボーディングが完了しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="567fc-194">デバイスが正しくオンボードされました。</span><span class="sxs-lookup"><span data-stu-id="567fc-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="567fc-195">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="567fc-196">デバイスがポータルに表示されるには数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="567fc-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-197">12 </span><span class="sxs-lookup"><span data-stu-id="567fc-197">12</span></span></td>
<td><span data-ttu-id="567fc-198">Microsoft Defender for Endpoint では、既定の構成の適用に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="567fc-199">サービスが既定の構成を適用できなかった。</span><span class="sxs-lookup"><span data-stu-id="567fc-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="567fc-200">このエラーは、短時間で解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="567fc-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-201">13</span><span class="sxs-lookup"><span data-stu-id="567fc-201">13</span></span></td>
<td><span data-ttu-id="567fc-202">Microsoft Defender for Endpoint デバイス ID が計算 <code>variable</code> されます。</span><span class="sxs-lookup"><span data-stu-id="567fc-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-203">通常の操作プロセス。</span><span class="sxs-lookup"><span data-stu-id="567fc-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="567fc-204">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-205">15 </span><span class="sxs-lookup"><span data-stu-id="567fc-205">15</span></span></td>
<td><span data-ttu-id="567fc-206">エンドポイントの Microsoft Defender は、URL を使用してコマンド チャネルを開始できません <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="567fc-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-207">Variable = Defender for Endpoint 処理サーバーの URL。</span><span class="sxs-lookup"><span data-stu-id="567fc-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="567fc-208">サービスは、その URL の外部処理サーバーに接続できません。</span><span class="sxs-lookup"><span data-stu-id="567fc-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="567fc-209">URL への接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-209">Check the connection to the URL.</span></span> <span data-ttu-id="567fc-210">「Configure <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">proxy and Internet connectivity」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-211">17 </span><span class="sxs-lookup"><span data-stu-id="567fc-211">17</span></span></td>
<td><span data-ttu-id="567fc-212">Microsoft Defender for Endpoint service は、接続されたユーザー エクスペリエンスとテレメトリ サービスの場所を変更できなかった。</span><span class="sxs-lookup"><span data-stu-id="567fc-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="567fc-213">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-214">Windows テレメトリ サービスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="567fc-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">診断データ サービスが有効になっているか確認します</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="567fc-216">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="567fc-217">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="567fc-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="567fc-218">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-219">18 </span><span class="sxs-lookup"><span data-stu-id="567fc-219">18</span></span></td>
<td><span data-ttu-id="567fc-220">OOBE (Windows ようこそ) が完了しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="567fc-221">サービスは、Windows 更新プログラムのインストールが完了した後にのみ開始されます。</span><span class="sxs-lookup"><span data-stu-id="567fc-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="567fc-222">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-223">19</span><span class="sxs-lookup"><span data-stu-id="567fc-223">19</span></span></td>
<td><span data-ttu-id="567fc-224">OOBE (Windows ようこそ) がまだ完了していません。</span><span class="sxs-lookup"><span data-stu-id="567fc-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="567fc-225">サービスは、Windows 更新プログラムのインストールが完了した後にのみ開始されます。</span><span class="sxs-lookup"><span data-stu-id="567fc-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="567fc-226">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="567fc-227">システムの再起動後もこのエラーが解決しない場合は、すべての Windows 更新プログラムが完全にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-228">20</span><span class="sxs-lookup"><span data-stu-id="567fc-228">20</span></span></td>
<td><span data-ttu-id="567fc-229">OOBE (Windows ようこそ) が完了するのを待つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="567fc-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="567fc-230">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-231">内部エラー。</span><span class="sxs-lookup"><span data-stu-id="567fc-231">Internal error.</span></span></td>
<td><span data-ttu-id="567fc-232">システムの再起動後もこのエラーが解決しない場合は、すべての Windows 更新プログラムが完全にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-233">25</span><span class="sxs-lookup"><span data-stu-id="567fc-233">25</span></span></td>
<td><span data-ttu-id="567fc-234">Microsoft Defender for Endpoint service は、レジストリの正常性状態をリセットできなかった。</span><span class="sxs-lookup"><span data-stu-id="567fc-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="567fc-235">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-236">デバイスが正しくオンボードされませんでした。</span><span class="sxs-lookup"><span data-stu-id="567fc-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="567fc-237">ポータルに報告しますが、サービスが SCCM またはレジストリに登録されていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="567fc-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="567fc-238">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="567fc-239">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="567fc-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="567fc-240">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-241">26</span><span class="sxs-lookup"><span data-stu-id="567fc-241">26</span></span></td>
<td><span data-ttu-id="567fc-242">Microsoft Defender for Endpoint service は、レジストリのオンボーディングの状態を設定できなかった。</span><span class="sxs-lookup"><span data-stu-id="567fc-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="567fc-243">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-244">デバイスが正しくオンボードされませんでした。</span><span class="sxs-lookup"><span data-stu-id="567fc-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="567fc-245">ポータルに報告しますが、サービスが SCCM またはレジストリに登録されていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="567fc-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="567fc-246">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="567fc-247">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="567fc-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="567fc-248">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-249">27</span><span class="sxs-lookup"><span data-stu-id="567fc-249">27</span></span></td>
<td><span data-ttu-id="567fc-250">Microsoft Defender for Endpoint Service は、Microsoft Defender ウイルス対策で SENSE 対応モードを有効にできなかった。</span><span class="sxs-lookup"><span data-stu-id="567fc-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="567fc-251">オンボーディング プロセスに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-251">Onboarding process failed.</span></span> <span data-ttu-id="567fc-252">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-253">通常、別のリアルタイムマルウェア対策製品がデバイスで適切に実行され、デバイスが Defender for Endpoint に報告されている場合、Microsoft Defender ウイルス対策は特別なパッシブ状態になります。</span><span class="sxs-lookup"><span data-stu-id="567fc-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="567fc-254">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="567fc-255">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="567fc-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="567fc-256">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="567fc-257">リアルタイムのマルウェア対策保護が正しく実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-258">28</span><span class="sxs-lookup"><span data-stu-id="567fc-258">28</span></span></td>
<td><span data-ttu-id="567fc-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span><span class="sxs-lookup"><span data-stu-id="567fc-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="567fc-260">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-261">Windows テレメトリ サービスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="567fc-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">診断データ サービスが有効になっているか確認します</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="567fc-263">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="567fc-264">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="567fc-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="567fc-265">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-266">29</span><span class="sxs-lookup"><span data-stu-id="567fc-266">29</span></span></td>
<td><span data-ttu-id="567fc-267">オフボード パラメーターの読み取りに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="567fc-268">エラーの種類: %1、エラー コード: %2、説明: %3</span><span class="sxs-lookup"><span data-stu-id="567fc-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="567fc-269">このイベントは、システムがオフボード パラメーター&#39;読み取りできない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="567fc-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="567fc-270">デバイスにインターネット アクセス権が設定されているのを確認し、オフボード プロセス全体を再度実行します。</span><span class="sxs-lookup"><span data-stu-id="567fc-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="567fc-271">オフボード パッケージの有効期限が切れていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-272">30</span><span class="sxs-lookup"><span data-stu-id="567fc-272">30</span></span></td>
<td><span data-ttu-id="567fc-273">Microsoft Defender for Endpoint Service は、Microsoft Defender ウイルス対策で SENSE 対応モードを無効にできなかった。</span><span class="sxs-lookup"><span data-stu-id="567fc-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="567fc-274">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-275">通常、別のリアルタイムマルウェア対策製品がデバイスで適切に実行され、デバイスが Defender for Endpoint に報告されている場合、Microsoft Defender ウイルス対策は特別なパッシブ状態になります。</span><span class="sxs-lookup"><span data-stu-id="567fc-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="567fc-276">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="567fc-277">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="567fc-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="567fc-278">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください。</a></span><span class="sxs-lookup"><span data-stu-id="567fc-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="567fc-279">リアルタイムのマルウェア対策保護が正しく実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-280">31</span><span class="sxs-lookup"><span data-stu-id="567fc-280">31</span></span></td>
<td><span data-ttu-id="567fc-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span><span class="sxs-lookup"><span data-stu-id="567fc-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="567fc-282">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-283">オンボード中に Windows テレメトリ サービスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="567fc-284">オフボードプロセスは続行されます。</span><span class="sxs-lookup"><span data-stu-id="567fc-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="567fc-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Windows テレメトリ サービスのエラーを確認します</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-286">32</span><span class="sxs-lookup"><span data-stu-id="567fc-286">32</span></span></td>
<td><span data-ttu-id="567fc-287">Microsoft Defender for Endpoint service は、オフボード プロセスの後に自身を停止する要求に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="567fc-288">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="567fc-289">オフボード中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="567fc-290">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="567fc-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-291">33</span><span class="sxs-lookup"><span data-stu-id="567fc-291">33</span></span></td>
<td><span data-ttu-id="567fc-292">エンドポイント サービスの Microsoft Defender は、SENSE GUID の永続化に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="567fc-293">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-294">一意の識別子を使用して、ポータルに報告する各デバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="567fc-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="567fc-295">識別子が保持されない場合、同じデバイスがポータルに 2 回表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="567fc-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="567fc-296">サービスがレジストリを更新できるデバイスのレジストリのアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-297">34</span><span class="sxs-lookup"><span data-stu-id="567fc-297">34</span></span></td>
<td><span data-ttu-id="567fc-298">Microsoft Defender for Endpoint Service は、接続されたユーザー エクスペリエンスとテレメトリ サービスへの依存関係として自分自身を追加できなかったので、オンボーディング プロセスが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="567fc-299">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-300">Windows テレメトリ サービスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="567fc-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">診断データ サービスが有効になっているか確認します</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="567fc-302">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="567fc-303">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="567fc-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="567fc-304">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="567fc-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-305">35</span><span class="sxs-lookup"><span data-stu-id="567fc-305">35</span></span></td>
<td><span data-ttu-id="567fc-306">Microsoft Defender for Endpoint Service は、接続されたユーザー エクスペリエンスとテレメトリ サービスへの依存関係として削除に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="567fc-307">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-308">オフボード中に Windows テレメトリ サービスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="567fc-309">オフボードプロセスは続行されます。</span><span class="sxs-lookup"><span data-stu-id="567fc-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="567fc-310">Windows 診断データ サービスのエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-311">36</span><span class="sxs-lookup"><span data-stu-id="567fc-311">36</span></span></td>
<td><span data-ttu-id="567fc-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span><span class="sxs-lookup"><span data-stu-id="567fc-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="567fc-313">完了コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="567fc-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="567fc-314">Defender for Endpoint の接続ユーザー エクスペリエンスとテレメトリ サービスへの登録が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="567fc-315">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-316">37</span><span class="sxs-lookup"><span data-stu-id="567fc-316">37</span></span></td>
<td><span data-ttu-id="567fc-317">Microsoft Defender for Endpoint A モジュールは、クォータを超えかねない状態です。</span><span class="sxs-lookup"><span data-stu-id="567fc-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="567fc-318">モジュール: %1、クォータ: {%2} {%3}、クォータ使用率の割合: %4。</span><span class="sxs-lookup"><span data-stu-id="567fc-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="567fc-319">デバイスは、現在の 24 時間ウィンドウの割り当てられたクォータをほとんど使用しています。</span><span class="sxs-lookup"><span data-stu-id="567fc-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="567fc-320">調整が必要です。</span><span class="sxs-lookup"><span data-stu-id="567fc-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="567fc-321">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-322">38</span><span class="sxs-lookup"><span data-stu-id="567fc-322">38</span></span></td>
<td><span data-ttu-id="567fc-323">ネットワーク接続は低として識別されます。</span><span class="sxs-lookup"><span data-stu-id="567fc-323">Network connection is identified as low.</span></span> <span data-ttu-id="567fc-324">Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="567fc-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="567fc-325">メーター接続: %2、インターネット利用可:%3、利用可能な無料ネットワーク:%4。</span><span class="sxs-lookup"><span data-stu-id="567fc-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="567fc-326">デバイスは、測定済み/有料ネットワークを使用し、サーバーへの接続頻度が低い。</span><span class="sxs-lookup"><span data-stu-id="567fc-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="567fc-327">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-328">39</span><span class="sxs-lookup"><span data-stu-id="567fc-328">39</span></span></td>
<td><span data-ttu-id="567fc-329">ネットワーク接続は通常と識別されます。</span><span class="sxs-lookup"><span data-stu-id="567fc-329">Network connection is identified as normal.</span></span> <span data-ttu-id="567fc-330">Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="567fc-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="567fc-331">メーター接続: %2、インターネット利用可:%3、利用可能な無料ネットワーク:%4。</span><span class="sxs-lookup"><span data-stu-id="567fc-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="567fc-332">デバイスは、メーター接続または有料接続を使用していなく、通常どおりサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="567fc-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="567fc-333">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-334">40</span><span class="sxs-lookup"><span data-stu-id="567fc-334">40</span></span></td>
<td><span data-ttu-id="567fc-335">バッテリーの状態は低と識別されます。</span><span class="sxs-lookup"><span data-stu-id="567fc-335">Battery state is identified as low.</span></span> <span data-ttu-id="567fc-336">Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="567fc-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="567fc-337">バッテリーの状態: %2。</span><span class="sxs-lookup"><span data-stu-id="567fc-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="567fc-338">デバイスのバッテリー 残量が少なく、サーバーに接続する頻度が低い。</span><span class="sxs-lookup"><span data-stu-id="567fc-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="567fc-339">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-340">41</span><span class="sxs-lookup"><span data-stu-id="567fc-340">41</span></span></td>
<td><span data-ttu-id="567fc-341">バッテリーの状態は、通常の状態として識別されます。</span><span class="sxs-lookup"><span data-stu-id="567fc-341">Battery state is identified as normal.</span></span> <span data-ttu-id="567fc-342">Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="567fc-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="567fc-343">バッテリーの状態: %2。</span><span class="sxs-lookup"><span data-stu-id="567fc-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="567fc-344">デバイスのバッテリー 残量が少なめで、通常どおりサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="567fc-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="567fc-345">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-346">42</span><span class="sxs-lookup"><span data-stu-id="567fc-346">42</span></span></td>
<td><span data-ttu-id="567fc-347">Microsoft Defender for Endpoint コンポーネントは、アクションの実行に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-347">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="567fc-348">コンポーネント: %1、Action: %2、例外の種類: %3、例外メッセージ: %4</span><span class="sxs-lookup"><span data-stu-id="567fc-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="567fc-349">内部エラー。</span><span class="sxs-lookup"><span data-stu-id="567fc-349">Internal error.</span></span> <span data-ttu-id="567fc-350">サービスの開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="567fc-351">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-352">43</span><span class="sxs-lookup"><span data-stu-id="567fc-352">43</span></span></td>
<td><span data-ttu-id="567fc-353">Microsoft Defender for Endpoint コンポーネントは、アクションの実行に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-353">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="567fc-354">コンポーネント: %1、Action: %2、例外の種類: %3、例外エラー: %4、例外メッセージ: %5</span><span class="sxs-lookup"><span data-stu-id="567fc-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="567fc-355">内部エラー。</span><span class="sxs-lookup"><span data-stu-id="567fc-355">Internal error.</span></span> <span data-ttu-id="567fc-356">サービスの開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="567fc-357">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-358">44</span><span class="sxs-lookup"><span data-stu-id="567fc-358">44</span></span></td>
<td><span data-ttu-id="567fc-359">Defender for Endpoint サービスのオフボーディングが完了しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="567fc-360">サービスはオフボードされました。</span><span class="sxs-lookup"><span data-stu-id="567fc-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="567fc-361">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-362">45</span><span class="sxs-lookup"><span data-stu-id="567fc-362">45</span></span></td>
<td><span data-ttu-id="567fc-363">イベント トレース セッション [%1] の登録と開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="567fc-364">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="567fc-364">Error code: %2</span></span></td>
<td><span data-ttu-id="567fc-365">ETW セッションの作成時にサービスの起動時にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="567fc-366">これにより、サービスの起動エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="567fc-367">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-368">46</span><span class="sxs-lookup"><span data-stu-id="567fc-368">46</span></span></td>
<td><span data-ttu-id="567fc-369">リソース不足のため、イベント トレース セッション [%1] の登録と開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="567fc-370">エラー コード: %2。</span><span class="sxs-lookup"><span data-stu-id="567fc-370">Error code: %2.</span></span> <span data-ttu-id="567fc-371">これは、アクティブなイベント トレース セッションが多すぎるためです。</span><span class="sxs-lookup"><span data-stu-id="567fc-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="567fc-372">サービスは 1 分で再試行します。</span><span class="sxs-lookup"><span data-stu-id="567fc-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="567fc-373">リソース不足のため、ETW セッションの作成中にサービスの起動時にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="567fc-374">サービスは開始され、実行中ですが、ETW セッションが開始されるまでセンサー イベントは報告できません。</span><span class="sxs-lookup"><span data-stu-id="567fc-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="567fc-375">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="567fc-376">サービスは、1 分ごとにセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="567fc-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-377">47</span><span class="sxs-lookup"><span data-stu-id="567fc-377">47</span></span></td>
<td><span data-ttu-id="567fc-378">イベント トレース セッションが正常に登録され、開始されました 。 以前に失敗した試行後に回復されました。</span><span class="sxs-lookup"><span data-stu-id="567fc-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="567fc-379">このイベントは、ETW セッションを正常に開始した後、前のイベントに従います。</span><span class="sxs-lookup"><span data-stu-id="567fc-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="567fc-380">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="567fc-381">48</span><span class="sxs-lookup"><span data-stu-id="567fc-381">48</span></span></td>
<td><span data-ttu-id="567fc-382">イベント トレース セッション [%2] にプロバイダー [%1] を追加できなかった。</span><span class="sxs-lookup"><span data-stu-id="567fc-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="567fc-383">エラー コード: %3。</span><span class="sxs-lookup"><span data-stu-id="567fc-383">Error code: %3.</span></span> <span data-ttu-id="567fc-384">つまり、このプロバイダーからのイベントは報告されません。</span><span class="sxs-lookup"><span data-stu-id="567fc-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="567fc-385">ETW セッションにプロバイダーを追加できなかった。</span><span class="sxs-lookup"><span data-stu-id="567fc-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="567fc-386">その結果、プロバイダー イベントは報告されません。</span><span class="sxs-lookup"><span data-stu-id="567fc-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="567fc-387">エラー コードを確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-387">Check the error code.</span></span> <span data-ttu-id="567fc-388">エラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="567fc-389">49</span><span class="sxs-lookup"><span data-stu-id="567fc-389">49</span></span></td>
   <td><span data-ttu-id="567fc-390">無効なクラウド構成コマンドが受信され、無視されます。</span><span class="sxs-lookup"><span data-stu-id="567fc-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="567fc-391">バージョン: %1、状態: %2、エラー コード: %3、メッセージ: %4</span><span class="sxs-lookup"><span data-stu-id="567fc-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="567fc-392">無視されたクラウド サービスから無効な構成ファイルを受け取った。</span><span class="sxs-lookup"><span data-stu-id="567fc-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="567fc-393">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-394">50</span><span class="sxs-lookup"><span data-stu-id="567fc-394">50</span></span></td>
   <td><span data-ttu-id="567fc-395">新しいクラウド構成が正常に適用されました。</span><span class="sxs-lookup"><span data-stu-id="567fc-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="567fc-396">バージョン: %1。</span><span class="sxs-lookup"><span data-stu-id="567fc-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="567fc-397">クラウド サービスから新しい構成を正常に適用しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="567fc-398">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-399">51</span><span class="sxs-lookup"><span data-stu-id="567fc-399">51</span></span></td>
   <td><span data-ttu-id="567fc-400">新しいクラウド構成の適用に失敗しました。バージョン: %1。</span><span class="sxs-lookup"><span data-stu-id="567fc-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="567fc-401">最後の既知の良い構成であるバージョン %2 が正常に適用されました。</span><span class="sxs-lookup"><span data-stu-id="567fc-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="567fc-402">クラウド サービスから悪い構成ファイルを受け取った。</span><span class="sxs-lookup"><span data-stu-id="567fc-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="567fc-403">最後に既知の良好な構成が正常に適用されました。</span><span class="sxs-lookup"><span data-stu-id="567fc-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="567fc-404">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-405">52</span><span class="sxs-lookup"><span data-stu-id="567fc-405">52</span></span></td>
   <td><span data-ttu-id="567fc-406">新しいクラウド構成の適用に失敗しました。バージョン: %1。</span><span class="sxs-lookup"><span data-stu-id="567fc-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="567fc-407">また、前回の既知の良好な構成バージョン %2 の適用にも失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="567fc-408">既定の構成が正常に適用されました。</span><span class="sxs-lookup"><span data-stu-id="567fc-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="567fc-409">クラウド サービスから悪い構成ファイルを受け取った。</span><span class="sxs-lookup"><span data-stu-id="567fc-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="567fc-410">前回の既知の良好な構成の適用に失敗し、既定の構成が適用されました。</span><span class="sxs-lookup"><span data-stu-id="567fc-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="567fc-411">サービスは、5 分以内に新しい構成ファイルのダウンロードを試みます。</span><span class="sxs-lookup"><span data-stu-id="567fc-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="567fc-412">イベント が表示#50サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-413">53</span><span class="sxs-lookup"><span data-stu-id="567fc-413">53</span></span></td>
   <td><span data-ttu-id="567fc-414">永続的な記憶域から読み込まれたクラウド構成のバージョン: %1。</span><span class="sxs-lookup"><span data-stu-id="567fc-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="567fc-415">構成は、サービスの起動時に永続的な記憶域から読み込まれた。</span><span class="sxs-lookup"><span data-stu-id="567fc-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="567fc-416">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-417">55</span><span class="sxs-lookup"><span data-stu-id="567fc-417">55</span></span></td>
   <td><span data-ttu-id="567fc-418">Secure ETW 自動ロガーの作成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="567fc-419">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="567fc-420">セキュリティで保護された ETW ロガーの作成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="567fc-421">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="567fc-421">Reboot the device.</span></span> <span data-ttu-id="567fc-422">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-423">56</span><span class="sxs-lookup"><span data-stu-id="567fc-423">56</span></span></td>
   <td><span data-ttu-id="567fc-424">Secure ETW 自動ロガーの削除に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="567fc-425">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="567fc-426">オフボーディング時にセキュリティで保護された ETW セッションを削除できなかった。</span><span class="sxs-lookup"><span data-stu-id="567fc-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="567fc-427">サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-428">57</span><span class="sxs-lookup"><span data-stu-id="567fc-428">57</span></span></td>
   <td><span data-ttu-id="567fc-429">トラブルシューティングの目的でコンピューターのスナップショットをキャプチャする。</span><span class="sxs-lookup"><span data-stu-id="567fc-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="567fc-430">調査パッケージ (forensics パッケージとも呼ばれる) が収集されています。</span><span class="sxs-lookup"><span data-stu-id="567fc-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="567fc-431">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-432">59</span><span class="sxs-lookup"><span data-stu-id="567fc-432">59</span></span></td>
   <td><span data-ttu-id="567fc-433">開始コマンド: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="567fc-434">応答コマンドの実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="567fc-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="567fc-435">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-436">60</span><span class="sxs-lookup"><span data-stu-id="567fc-436">60</span></span></td>
   <td><span data-ttu-id="567fc-437">コマンド %1 の実行に失敗しました。エラー: %2。</span><span class="sxs-lookup"><span data-stu-id="567fc-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="567fc-438">応答コマンドの実行に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="567fc-439">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-440">61</span><span class="sxs-lookup"><span data-stu-id="567fc-440">61</span></span></td>
   <td><span data-ttu-id="567fc-441">データ収集コマンド パラメーターが無効です。SasUri: %1、compressionLevel: %2。</span><span class="sxs-lookup"><span data-stu-id="567fc-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="567fc-442">データ収集コマンドの引数 (無効な引数) の読み取りまたは解析に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="567fc-443">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-444">62</span><span class="sxs-lookup"><span data-stu-id="567fc-444">62</span></span></td>
   <td><span data-ttu-id="567fc-445">接続ユーザー エクスペリエンスとテレメトリ サービスの開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="567fc-446">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="567fc-447">接続されたユーザー エクスペリエンスとテレメトリ (diagtrack) サービスの開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="567fc-448">Microsoft Defender for Endpoint テレメトリ以外は、このコンピューターから送信されません。</span><span class="sxs-lookup"><span data-stu-id="567fc-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="567fc-449">イベント ログのトラブルシューティング のヒントを探します。Microsoft-Windows-UniversalTelemetryClient/Operational。</span><span class="sxs-lookup"><span data-stu-id="567fc-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-450">63</span><span class="sxs-lookup"><span data-stu-id="567fc-450">63</span></span></td>
   <td><span data-ttu-id="567fc-451">外部サービスの開始の種類を更新します。</span><span class="sxs-lookup"><span data-stu-id="567fc-451">Updating the start type of external service.</span></span> <span data-ttu-id="567fc-452">名前: %1、実際の開始の種類: %2、予期される開始の種類: %3、終了コード: %4</span><span class="sxs-lookup"><span data-stu-id="567fc-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="567fc-453">外部サービスの開始の種類を更新しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="567fc-454">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-455">64</span><span class="sxs-lookup"><span data-stu-id="567fc-455">64</span></span></td>
   <td><span data-ttu-id="567fc-456">停止した外部サービスの開始。</span><span class="sxs-lookup"><span data-stu-id="567fc-456">Starting stopped external service.</span></span> <span data-ttu-id="567fc-457">名前: %1、終了コード: %2</span><span class="sxs-lookup"><span data-stu-id="567fc-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="567fc-458">外部サービスの開始。</span><span class="sxs-lookup"><span data-stu-id="567fc-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="567fc-459">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-460">65</span><span class="sxs-lookup"><span data-stu-id="567fc-460">65</span></span></td>
   <td><span data-ttu-id="567fc-461">Microsoft セキュリティ イベント コンポーネント ミニフィルター ドライバーの読み込みに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="567fc-462">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="567fc-463">ファイルシステムのミニフィルターMsSecFlt.sys読み込めない。</span><span class="sxs-lookup"><span data-stu-id="567fc-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="567fc-464">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="567fc-464">Reboot the device.</span></span> <span data-ttu-id="567fc-465">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-466">66</span><span class="sxs-lookup"><span data-stu-id="567fc-466">66</span></span></td>
   <td><span data-ttu-id="567fc-467">ポリシー更新プログラム: 待機時間モード - %1</span><span class="sxs-lookup"><span data-stu-id="567fc-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="567fc-468">C&C 接続頻度ポリシーが更新されました。</span><span class="sxs-lookup"><span data-stu-id="567fc-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="567fc-469">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-470">68</span><span class="sxs-lookup"><span data-stu-id="567fc-470">68</span></span></td>
   <td><span data-ttu-id="567fc-471">サービスの開始の種類が予期しない。</span><span class="sxs-lookup"><span data-stu-id="567fc-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="567fc-472">サービス名: %1、実際の開始の種類: %2、予期される開始の種類: %3</span><span class="sxs-lookup"><span data-stu-id="567fc-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="567fc-473">予期しない外部サービスの開始の種類。</span><span class="sxs-lookup"><span data-stu-id="567fc-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="567fc-474">外部サービスの開始の種類を修正します。</span><span class="sxs-lookup"><span data-stu-id="567fc-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-475">69</span><span class="sxs-lookup"><span data-stu-id="567fc-475">69</span></span></td>
   <td><span data-ttu-id="567fc-476">サービスが停止します。</span><span class="sxs-lookup"><span data-stu-id="567fc-476">The service is stopped.</span></span> <span data-ttu-id="567fc-477">サービス名: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="567fc-478">外部サービスが停止します。</span><span class="sxs-lookup"><span data-stu-id="567fc-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="567fc-479">外部サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="567fc-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-480">70</span><span class="sxs-lookup"><span data-stu-id="567fc-480">70</span></span></td>
   <td><span data-ttu-id="567fc-481">ポリシー更新: サンプル コレクションを許可する - %1</span><span class="sxs-lookup"><span data-stu-id="567fc-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="567fc-482">サンプル コレクション ポリシーが更新されました。</span><span class="sxs-lookup"><span data-stu-id="567fc-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="567fc-483">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-484">71</span><span class="sxs-lookup"><span data-stu-id="567fc-484">71</span></span></td>
   <td><span data-ttu-id="567fc-485">コマンドの実行に成功しました: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="567fc-486">コマンドが正常に実行されました。</span><span class="sxs-lookup"><span data-stu-id="567fc-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="567fc-487">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-488">72</span><span class="sxs-lookup"><span data-stu-id="567fc-488">72</span></span></td>
   <td><span data-ttu-id="567fc-489">最初の完全なコンピューター プロファイル レポートの送信を試みました。</span><span class="sxs-lookup"><span data-stu-id="567fc-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="567fc-490">結果コード: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="567fc-491">情報提供のみ。</span><span class="sxs-lookup"><span data-stu-id="567fc-491">Informational only.</span></span></td>
   <td><span data-ttu-id="567fc-492">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-493">73</span><span class="sxs-lookup"><span data-stu-id="567fc-493">73</span></span></td>
   <td><span data-ttu-id="567fc-494">プラットフォームの開始センス: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="567fc-495">情報提供のみ。</span><span class="sxs-lookup"><span data-stu-id="567fc-495">Informational only.</span></span></td>
   <td><span data-ttu-id="567fc-496">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-497">74</span><span class="sxs-lookup"><span data-stu-id="567fc-497">74</span></span></td>
   <td><span data-ttu-id="567fc-498">レジストリ内のデバイス タグが長さの制限を超えています。</span><span class="sxs-lookup"><span data-stu-id="567fc-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="567fc-499">タグ名: %2。</span><span class="sxs-lookup"><span data-stu-id="567fc-499">Tag name: %2.</span></span> <span data-ttu-id="567fc-500">長さの制限: %1。</span><span class="sxs-lookup"><span data-stu-id="567fc-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="567fc-501">デバイス タグが長さの制限を超えています。</span><span class="sxs-lookup"><span data-stu-id="567fc-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="567fc-502">短いデバイス タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="567fc-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-503">81</span><span class="sxs-lookup"><span data-stu-id="567fc-503">81</span></span></td>
   <td><span data-ttu-id="567fc-504">エンドポイント ETW 自動ロガー用 Microsoft Defender の作成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-504">Failed to create Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="567fc-505">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="567fc-506">ETW セッションの作成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="567fc-507">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="567fc-507">Reboot the device.</span></span> <span data-ttu-id="567fc-508">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-509">82</span><span class="sxs-lookup"><span data-stu-id="567fc-509">82</span></span></td>
   <td><span data-ttu-id="567fc-510">エンドポイント ETW 自動ロガー用 Microsoft Defender の削除に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-510">Failed to remove Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="567fc-511">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="567fc-512">ETW セッションの削除に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="567fc-513">サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-514">84</span><span class="sxs-lookup"><span data-stu-id="567fc-514">84</span></span></td>
   <td><span data-ttu-id="567fc-515">ウイルス対策Windows Defenderモードを設定します。</span><span class="sxs-lookup"><span data-stu-id="567fc-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="567fc-516">強制パッシブ モード: %1、結果コード: %2。</span><span class="sxs-lookup"><span data-stu-id="567fc-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="567fc-517">Defender の実行モード (アクティブまたはパッシブ) を設定します。</span><span class="sxs-lookup"><span data-stu-id="567fc-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="567fc-518">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-519">85</span><span class="sxs-lookup"><span data-stu-id="567fc-519">85</span></span></td>
   <td><span data-ttu-id="567fc-520">Microsoft Defender for Endpoint 実行可能ファイルのトリガーに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-520">Failed to trigger Microsoft Defender for Endpoint executable.</span></span> <span data-ttu-id="567fc-521">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="567fc-522">SenseIR 実行可能ファイルの主演に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="567fc-523">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="567fc-523">Reboot the device.</span></span> <span data-ttu-id="567fc-524">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-525">86</span><span class="sxs-lookup"><span data-stu-id="567fc-525">86</span></span></td>
   <td><span data-ttu-id="567fc-526">もう一度開始すると、起動する必要がある外部サービスが停止しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="567fc-527">名前: %1、終了コード: %2</span><span class="sxs-lookup"><span data-stu-id="567fc-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="567fc-528">外部サービスを再度開始します。</span><span class="sxs-lookup"><span data-stu-id="567fc-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="567fc-529">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-530">87</span><span class="sxs-lookup"><span data-stu-id="567fc-530">87</span></span></td>
   <td><span data-ttu-id="567fc-531">外部サービスを開始できません。</span><span class="sxs-lookup"><span data-stu-id="567fc-531">Cannot start the external service.</span></span> <span data-ttu-id="567fc-532">名前: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-532">Name: %1</span></span></td>
   <td><span data-ttu-id="567fc-533">外部サービスの開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="567fc-534">サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-535">88</span><span class="sxs-lookup"><span data-stu-id="567fc-535">88</span></span></td>
   <td><span data-ttu-id="567fc-536">外部サービスの開始の種類を再度更新します。</span><span class="sxs-lookup"><span data-stu-id="567fc-536">Updating the start type of external service again.</span></span> <span data-ttu-id="567fc-537">名前: %1、実際の開始の種類: %2、予期される開始の種類: %3、終了コード: %4</span><span class="sxs-lookup"><span data-stu-id="567fc-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="567fc-538">外部サービスの開始の種類を更新しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="567fc-539">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-540">89</span><span class="sxs-lookup"><span data-stu-id="567fc-540">89</span></span></td>
   <td><span data-ttu-id="567fc-541">外部サービスの開始の種類を更新できません。</span><span class="sxs-lookup"><span data-stu-id="567fc-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="567fc-542">名前: %1、実際の開始の種類: %2、予期される開始の種類: %3</span><span class="sxs-lookup"><span data-stu-id="567fc-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="567fc-543">外部サービスの開始の種類を更新できない。</span><span class="sxs-lookup"><span data-stu-id="567fc-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="567fc-544">サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-545">90</span><span class="sxs-lookup"><span data-stu-id="567fc-545">90</span></span></td>
   <td><span data-ttu-id="567fc-546">地域 %1 のクラウド サービスに接続するための System Guard ランタイム モニターの構成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="567fc-547">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="567fc-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="567fc-548">System Guard ランタイム モニターは、構成証明データをクラウド サービスに送信しない。</span><span class="sxs-lookup"><span data-stu-id="567fc-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="567fc-549">登録パスのアクセス許可を確認します。"HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。</span><span class="sxs-lookup"><span data-stu-id="567fc-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="567fc-550">問題が見つからない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-551">91</span><span class="sxs-lookup"><span data-stu-id="567fc-551">91</span></span></td>
   <td><span data-ttu-id="567fc-552">System Guard ランタイム モニター地域情報の削除に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="567fc-553">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="567fc-554">System Guard ランタイム モニターは、構成証明データをクラウド サービスに送信しない。</span><span class="sxs-lookup"><span data-stu-id="567fc-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="567fc-555">登録パスのアクセス許可を確認します。"HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。</span><span class="sxs-lookup"><span data-stu-id="567fc-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="567fc-556">問題が見つからない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-557">92</span><span class="sxs-lookup"><span data-stu-id="567fc-557">92</span></span></td>
   <td><span data-ttu-id="567fc-558">データ クォータを超えたため、センサーのサイバー データ クォータの送信を停止します。</span><span class="sxs-lookup"><span data-stu-id="567fc-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="567fc-559">クォータ期間が過ぎると、送信が再開されます。</span><span class="sxs-lookup"><span data-stu-id="567fc-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="567fc-560">状態マスク: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="567fc-561">調整の制限を超える。</span><span class="sxs-lookup"><span data-stu-id="567fc-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="567fc-562">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-563">93</span><span class="sxs-lookup"><span data-stu-id="567fc-563">93</span></span></td>
   <td><span data-ttu-id="567fc-564">センサーのサイバー データの送信を再送信する。</span><span class="sxs-lookup"><span data-stu-id="567fc-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="567fc-565">状態マスク: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="567fc-566">サイバー データの送信を再開します。</span><span class="sxs-lookup"><span data-stu-id="567fc-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="567fc-567">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-568">94</span><span class="sxs-lookup"><span data-stu-id="567fc-568">94</span></span></td>
   <td><span data-ttu-id="567fc-569">Microsoft Defender for Endpoint 実行可能ファイルが開始されました</span><span class="sxs-lookup"><span data-stu-id="567fc-569">Microsoft Defender for Endpoint executable has started</span></span></td>
   <td><span data-ttu-id="567fc-570">SenseCE 実行可能ファイルが開始されました。</span><span class="sxs-lookup"><span data-stu-id="567fc-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="567fc-571">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-572">95</span><span class="sxs-lookup"><span data-stu-id="567fc-572">95</span></span></td>
   <td><span data-ttu-id="567fc-573">Microsoft Defender for Endpoint 実行可能ファイルが終了しました</span><span class="sxs-lookup"><span data-stu-id="567fc-573">Microsoft Defender for Endpoint executable has ended</span></span></td>
   <td><span data-ttu-id="567fc-574">SenseCE 実行可能ファイルが終了しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="567fc-575">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-576">96</span><span class="sxs-lookup"><span data-stu-id="567fc-576">96</span></span></td>
   <td><span data-ttu-id="567fc-577">Microsoft Defender for Endpoint Init が呼び出しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-577">Microsoft Defender for Endpoint Init has called.</span></span> <span data-ttu-id="567fc-578">結果コード: %2</span><span class="sxs-lookup"><span data-stu-id="567fc-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="567fc-579">SenseCE 実行可能ファイルは MCE 初期化と呼ばされています。</span><span class="sxs-lookup"><span data-stu-id="567fc-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="567fc-580">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-581">97</span><span class="sxs-lookup"><span data-stu-id="567fc-581">97</span></span></td>
   <td><span data-ttu-id="567fc-582">DLP シナリオのクラウドへの接続に関する問題がある</span><span class="sxs-lookup"><span data-stu-id="567fc-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="567fc-583">DLP 分類フローに影響するネットワーク接続の問題があります。</span><span class="sxs-lookup"><span data-stu-id="567fc-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="567fc-584">ネットワーク接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="567fc-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-585">98</span><span class="sxs-lookup"><span data-stu-id="567fc-585">98</span></span></td>
   <td><span data-ttu-id="567fc-586">DLP シナリオのクラウドへの接続が復元されました</span><span class="sxs-lookup"><span data-stu-id="567fc-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="567fc-587">ネットワークへの接続が復元され、DLP 分類フローを続行できます。</span><span class="sxs-lookup"><span data-stu-id="567fc-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="567fc-588">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-589">99</span><span class="sxs-lookup"><span data-stu-id="567fc-589">99</span></span></td>
   <td><span data-ttu-id="567fc-590">サーバーとの通信中に、センスで次のエラーが発生しました。(%1)。</span><span class="sxs-lookup"><span data-stu-id="567fc-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="567fc-591">結果: (%2)</span><span class="sxs-lookup"><span data-stu-id="567fc-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="567fc-592">通信エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="567fc-593">詳細については、イベント ログで次のイベントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="567fc-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-594">100</span><span class="sxs-lookup"><span data-stu-id="567fc-594">100</span></span></td>
   <td><span data-ttu-id="567fc-595">Microsoft Defender for Endpoint 実行可能ファイルの起動に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-595">Microsoft Defender for Endpoint executable failed to start.</span></span> <span data-ttu-id="567fc-596">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="567fc-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="567fc-597">SenseCE 実行可能ファイルの起動に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="567fc-598">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="567fc-598">Reboot the device.</span></span> <span data-ttu-id="567fc-599">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="567fc-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-600">102</span><span class="sxs-lookup"><span data-stu-id="567fc-600">102</span></span></td>
   <td><span data-ttu-id="567fc-601">Microsoft Defender for Endpoint Network Detection and Response 実行可能ファイルが開始されました</span><span class="sxs-lookup"><span data-stu-id="567fc-601">Microsoft Defender for Endpoint Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="567fc-602">SenseNdr 実行可能ファイルが開始されました。</span><span class="sxs-lookup"><span data-stu-id="567fc-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="567fc-603">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="567fc-604">103</span><span class="sxs-lookup"><span data-stu-id="567fc-604">103</span></span></td>
   <td><span data-ttu-id="567fc-605">Microsoft Defender for Endpoint Network Detection and Response 実行可能ファイルが終了しました</span><span class="sxs-lookup"><span data-stu-id="567fc-605">Microsoft Defender for Endpoint Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="567fc-606">SenseNdr 実行可能ファイルが終了しました。</span><span class="sxs-lookup"><span data-stu-id="567fc-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="567fc-607">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="567fc-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="567fc-608">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="567fc-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="567fc-609">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="567fc-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="567fc-610">関連項目</span><span class="sxs-lookup"><span data-stu-id="567fc-610">Related topics</span></span>
- [<span data-ttu-id="567fc-611">Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="567fc-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="567fc-612">デバイス プロキシとインターネット接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="567fc-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="567fc-613">Microsoft Defender for Endpoint のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="567fc-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
