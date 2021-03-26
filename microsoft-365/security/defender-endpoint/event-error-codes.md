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
ms.openlocfilehash: 1b8454107b6a2737f1236a066c3a24a2b9c776cb
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222656"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="29bf3-104">イベント ビューアーを使用してイベントとエラーを確認する</span><span class="sxs-lookup"><span data-stu-id="29bf3-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="29bf3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="29bf3-105">**Applies to:**</span></span>
- <span data-ttu-id="29bf3-106">イベント ビューアー</span><span class="sxs-lookup"><span data-stu-id="29bf3-106">Event Viewer</span></span>
- [<span data-ttu-id="29bf3-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="29bf3-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="29bf3-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="29bf3-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="29bf3-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="29bf3-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="29bf3-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="29bf3-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="29bf3-111">イベントの ID は、個々のデバイスの [イベント ビューアー](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) で確認できます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="29bf3-112">たとえば、[デバイス] リストにデバイスが表示されない場合は、デバイスでイベントの ID を探す必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="29bf3-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="29bf3-113">次に、この表を使用して、さらにトラブルシューティングの手順を決定できます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="29bf3-114">**イベント ビューアーを開き、Microsoft Defender for Endpoint サービス イベント ログを検索します。**</span><span class="sxs-lookup"><span data-stu-id="29bf3-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="29bf3-115">**[Windows] メニューの**[スタート] をクリックし、「イベント ビューアー」**と入力し**、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="29bf3-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="29bf3-116">ログ リストの [ログの概要 **] で\*\*\*\*、Microsoft-Windows-SENSE/Operational が表示されるまでスクロールします**。</span><span class="sxs-lookup"><span data-stu-id="29bf3-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="29bf3-117">アイテムをダブルクリックしてログを開きます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="29bf3-118">a.</span><span class="sxs-lookup"><span data-stu-id="29bf3-118">a.</span></span>  <span data-ttu-id="29bf3-119">[アプリケーションとサービス ログ] Microsoft Windows SENSE を展開して [操作] をクリックして、ログ  >    >    >  に **アクセスすることもできます**。</span><span class="sxs-lookup"><span data-stu-id="29bf3-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="29bf3-120">SENSE は、Microsoft Defender for Endpoint をサポートする動作センサーを参照するために使用される内部名です。</span><span class="sxs-lookup"><span data-stu-id="29bf3-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="29bf3-121">サービスによって記録されたイベントがログに表示されます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="29bf3-122">サービスによって記録されるイベントの一覧については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="29bf3-123">イベント ID</span><span class="sxs-lookup"><span data-stu-id="29bf3-123">Event ID</span></span></th>
<th><span data-ttu-id="29bf3-124">メッセージ</span><span class="sxs-lookup"><span data-stu-id="29bf3-124">Message</span></span></th>
<th><span data-ttu-id="29bf3-125">説明</span><span class="sxs-lookup"><span data-stu-id="29bf3-125">Description</span></span></th>
<th><span data-ttu-id="29bf3-126">アクション</span><span class="sxs-lookup"><span data-stu-id="29bf3-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="29bf3-127">1</span><span class="sxs-lookup"><span data-stu-id="29bf3-127">1</span></span></td>
<td><span data-ttu-id="29bf3-128">Microsoft Defender for Endpoint service が開始されました (バージョン <code>variable</code> )。</span><span class="sxs-lookup"><span data-stu-id="29bf3-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="29bf3-129">システムの起動時、シャットダウン中、オンボーディング中に発生します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="29bf3-130">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-131">2</span><span class="sxs-lookup"><span data-stu-id="29bf3-131">2</span></span></td>
<td><span data-ttu-id="29bf3-132">Microsoft Defender for Endpoint service shutdown.</span><span class="sxs-lookup"><span data-stu-id="29bf3-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="29bf3-133">デバイスがシャットダウンまたはオフボードされている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="29bf3-134">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-135">3</span><span class="sxs-lookup"><span data-stu-id="29bf3-135">3</span></span></td>
<td><span data-ttu-id="29bf3-136">Microsoft Defender for Endpoint service の開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="29bf3-137">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-138">サービスが開始しなかった。</span><span class="sxs-lookup"><span data-stu-id="29bf3-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="29bf3-139">他のメッセージを確認して、考えられる原因とトラブルシューティングの手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-140">4</span><span class="sxs-lookup"><span data-stu-id="29bf3-140">4</span></span></td>
<td><span data-ttu-id="29bf3-141">Microsoft Defender for Endpoint service がでサーバーに連絡しました <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="29bf3-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-142">Variable = Defender for Endpoint 処理サーバーの URL。</span><span class="sxs-lookup"><span data-stu-id="29bf3-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="29bf3-143">この URL は、ファイアウォールまたはネットワーク アクティビティに表示される URL と一致します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="29bf3-144">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-145">5</span><span class="sxs-lookup"><span data-stu-id="29bf3-145">5</span></span></td>
<td><span data-ttu-id="29bf3-146">Microsoft Defender for Endpoint service でサーバーへの接続に失敗しました <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="29bf3-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-147">Variable = Defender for Endpoint 処理サーバーの URL。</span><span class="sxs-lookup"><span data-stu-id="29bf3-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="29bf3-148">サービスは、その URL の外部処理サーバーに接続できません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="29bf3-149">URL への接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-149">Check the connection to the URL.</span></span> <span data-ttu-id="29bf3-150">「Configure <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">proxy and Internet connectivity」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-151">6</span><span class="sxs-lookup"><span data-stu-id="29bf3-151">6</span></span></td>
<td><span data-ttu-id="29bf3-152">Microsoft Defender for Endpoint Service はオンボードされていないので、オンボーディング パラメーターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="29bf3-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="29bf3-153">デバイスが正しくオンボードされていないので、ポータルに報告されません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="29bf3-154">サービスを開始する前にオンボーディングを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29bf3-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="29bf3-155">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="29bf3-156">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="29bf3-157">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-158">7</span><span class="sxs-lookup"><span data-stu-id="29bf3-158">7</span></span></td>
<td><span data-ttu-id="29bf3-159">Microsoft Defender for Endpoint service では、オンボーディング パラメーターの読み取りが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="29bf3-160">失敗: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-161">変数 = 詳細なエラーの説明。</span><span class="sxs-lookup"><span data-stu-id="29bf3-161">Variable = detailed error description.</span></span> <span data-ttu-id="29bf3-162">デバイスが正しくオンボードされていないので、ポータルに報告されません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="29bf3-163">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="29bf3-164">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="29bf3-165">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-166">8</span><span class="sxs-lookup"><span data-stu-id="29bf3-166">8</span></span></td>
<td><span data-ttu-id="29bf3-167">Microsoft Defender for Endpoint service では、構成のクリーンアップに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="29bf3-168">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-169"><b>オンボーディング中:</b> サービスは、オンボーディング中に構成のクリーンアップに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="29bf3-170">オンボーディング プロセスは続行されます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="29bf3-171"><b>オフボード中:</b> サービスは、オフボード中に構成のクリーンアップに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="29bf3-172">オフボード プロセスは終了しましたが、サービスは実行を続ける。</span><span class="sxs-lookup"><span data-stu-id="29bf3-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="29bf3-173"><b>オンボーディング:</b> アクションは不要です。</span><span class="sxs-lookup"><span data-stu-id="29bf3-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="29bf3-174"><b>オフボード:</b> システムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="29bf3-175">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-176">9</span><span class="sxs-lookup"><span data-stu-id="29bf3-176">9</span></span></td>
<td><span data-ttu-id="29bf3-177">Microsoft Defender for Endpoint service は、開始の種類を変更できなかった。</span><span class="sxs-lookup"><span data-stu-id="29bf3-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="29bf3-178">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-179"><b>オンボーディング中:</b> デバイスが正しくオンボードされていないので、ポータルに報告されません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="29bf3-180"><b>オフボード中:</b> サービスの開始の種類を変更できなかった。</span><span class="sxs-lookup"><span data-stu-id="29bf3-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="29bf3-181">オフボードプロセスは続行されます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="29bf3-182">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="29bf3-183">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="29bf3-184">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-185">10</span><span class="sxs-lookup"><span data-stu-id="29bf3-185">10</span></span></td>
<td><span data-ttu-id="29bf3-186">Microsoft Defender for Endpoint Service は、オンボーディング情報を保持できなかった。</span><span class="sxs-lookup"><span data-stu-id="29bf3-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="29bf3-187">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-188">デバイスが正しくオンボードされていないので、ポータルに報告されません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="29bf3-189">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="29bf3-190">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="29bf3-191">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-192">11</span><span class="sxs-lookup"><span data-stu-id="29bf3-192">11</span></span></td>
<td><span data-ttu-id="29bf3-193">Defender for Endpoint サービスのオンボーディングまたは再オンボーディングが完了しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="29bf3-194">デバイスが正しくオンボードされました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="29bf3-195">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="29bf3-196">デバイスがポータルに表示されるには数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="29bf3-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-197">12 </span><span class="sxs-lookup"><span data-stu-id="29bf3-197">12</span></span></td>
<td><span data-ttu-id="29bf3-198">Microsoft Defender for Endpoint では、既定の構成の適用に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="29bf3-199">サービスが既定の構成を適用できなかった。</span><span class="sxs-lookup"><span data-stu-id="29bf3-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="29bf3-200">このエラーは、短時間で解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="29bf3-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-201">13</span><span class="sxs-lookup"><span data-stu-id="29bf3-201">13</span></span></td>
<td><span data-ttu-id="29bf3-202">Microsoft Defender for Endpoint デバイス ID が計算 <code>variable</code> されます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-203">通常の操作プロセス。</span><span class="sxs-lookup"><span data-stu-id="29bf3-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="29bf3-204">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-205">15 </span><span class="sxs-lookup"><span data-stu-id="29bf3-205">15</span></span></td>
<td><span data-ttu-id="29bf3-206">エンドポイントの Microsoft Defender は、URL を使用してコマンド チャネルを開始できません <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="29bf3-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-207">Variable = Defender for Endpoint 処理サーバーの URL。</span><span class="sxs-lookup"><span data-stu-id="29bf3-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="29bf3-208">サービスは、その URL の外部処理サーバーに接続できません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="29bf3-209">URL への接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-209">Check the connection to the URL.</span></span> <span data-ttu-id="29bf3-210">「Configure <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">proxy and Internet connectivity」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-211">17 </span><span class="sxs-lookup"><span data-stu-id="29bf3-211">17</span></span></td>
<td><span data-ttu-id="29bf3-212">Microsoft Defender for Endpoint service は、接続されたユーザー エクスペリエンスとテレメトリ サービスの場所を変更できなかった。</span><span class="sxs-lookup"><span data-stu-id="29bf3-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="29bf3-213">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-214">Windows テレメトリ サービスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="29bf3-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">診断データ サービスが有効になっているか確認します</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="29bf3-216">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="29bf3-217">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="29bf3-218">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-219">18 </span><span class="sxs-lookup"><span data-stu-id="29bf3-219">18</span></span></td>
<td><span data-ttu-id="29bf3-220">OOBE (Windows ようこそ) が完了しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="29bf3-221">サービスは、Windows 更新プログラムのインストールが完了した後にのみ開始されます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="29bf3-222">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-223">19</span><span class="sxs-lookup"><span data-stu-id="29bf3-223">19</span></span></td>
<td><span data-ttu-id="29bf3-224">OOBE (Windows ようこそ) がまだ完了していません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="29bf3-225">サービスは、Windows 更新プログラムのインストールが完了した後にのみ開始されます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="29bf3-226">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="29bf3-227">システムの再起動後もこのエラーが解決しない場合は、すべての Windows 更新プログラムが完全にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-228">20</span><span class="sxs-lookup"><span data-stu-id="29bf3-228">20</span></span></td>
<td><span data-ttu-id="29bf3-229">OOBE (Windows ようこそ) が完了するのを待つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="29bf3-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="29bf3-230">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-231">内部エラー。</span><span class="sxs-lookup"><span data-stu-id="29bf3-231">Internal error.</span></span></td>
<td><span data-ttu-id="29bf3-232">システムの再起動後もこのエラーが解決しない場合は、すべての Windows 更新プログラムが完全にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-233">25</span><span class="sxs-lookup"><span data-stu-id="29bf3-233">25</span></span></td>
<td><span data-ttu-id="29bf3-234">Microsoft Defender for Endpoint service は、レジストリの正常性状態をリセットできなかった。</span><span class="sxs-lookup"><span data-stu-id="29bf3-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="29bf3-235">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-236">デバイスが正しくオンボードされませんでした。</span><span class="sxs-lookup"><span data-stu-id="29bf3-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="29bf3-237">ポータルに報告しますが、サービスが SCCM またはレジストリに登録されていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="29bf3-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="29bf3-238">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="29bf3-239">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="29bf3-240">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-241">26</span><span class="sxs-lookup"><span data-stu-id="29bf3-241">26</span></span></td>
<td><span data-ttu-id="29bf3-242">Microsoft Defender for Endpoint service は、レジストリのオンボーディングの状態を設定できなかった。</span><span class="sxs-lookup"><span data-stu-id="29bf3-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="29bf3-243">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-244">デバイスが正しくオンボードされませんでした。</span><span class="sxs-lookup"><span data-stu-id="29bf3-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="29bf3-245">ポータルに報告しますが、サービスが SCCM またはレジストリに登録されていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="29bf3-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="29bf3-246">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="29bf3-247">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="29bf3-248">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-249">27</span><span class="sxs-lookup"><span data-stu-id="29bf3-249">27</span></span></td>
<td><span data-ttu-id="29bf3-250">Microsoft Defender for Endpoint Service は、Microsoft Defender ウイルス対策で SENSE 対応モードを有効にできなかった。</span><span class="sxs-lookup"><span data-stu-id="29bf3-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="29bf3-251">オンボーディング プロセスに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-251">Onboarding process failed.</span></span> <span data-ttu-id="29bf3-252">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-253">通常、別のリアルタイムマルウェア対策製品がデバイスで適切に実行され、デバイスが Defender for Endpoint に報告されている場合、Microsoft Defender ウイルス対策は特別なパッシブ状態になります。</span><span class="sxs-lookup"><span data-stu-id="29bf3-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="29bf3-254">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="29bf3-255">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="29bf3-256">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="29bf3-257">リアルタイムのマルウェア対策保護が正しく実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-258">28</span><span class="sxs-lookup"><span data-stu-id="29bf3-258">28</span></span></td>
<td><span data-ttu-id="29bf3-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span><span class="sxs-lookup"><span data-stu-id="29bf3-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="29bf3-260">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-261">Windows テレメトリ サービスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="29bf3-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">診断データ サービスが有効になっているか確認します</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="29bf3-263">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="29bf3-264">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="29bf3-265">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-266">29</span><span class="sxs-lookup"><span data-stu-id="29bf3-266">29</span></span></td>
<td><span data-ttu-id="29bf3-267">オフボード パラメーターの読み取りに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="29bf3-268">エラーの種類: %1、エラー コード: %2、説明: %3</span><span class="sxs-lookup"><span data-stu-id="29bf3-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="29bf3-269">このイベントは、システムがオフボード パラメーター&#39;読み取りできない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="29bf3-270">デバイスにインターネット アクセス権が設定されているのを確認し、オフボード プロセス全体を再度実行します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="29bf3-271">オフボード パッケージの有効期限が切れていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-272">30</span><span class="sxs-lookup"><span data-stu-id="29bf3-272">30</span></span></td>
<td><span data-ttu-id="29bf3-273">Microsoft Defender for Endpoint Service は、Microsoft Defender ウイルス対策で SENSE 対応モードを無効にできなかった。</span><span class="sxs-lookup"><span data-stu-id="29bf3-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="29bf3-274">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-275">通常、別のリアルタイムマルウェア対策製品がデバイスで適切に実行され、デバイスが Defender for Endpoint に報告されている場合、Microsoft Defender ウイルス対策は特別なパッシブ状態になります。</span><span class="sxs-lookup"><span data-stu-id="29bf3-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="29bf3-276">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="29bf3-277">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="29bf3-278">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください。</a></span><span class="sxs-lookup"><span data-stu-id="29bf3-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="29bf3-279">リアルタイムのマルウェア対策保護が正しく実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-280">31</span><span class="sxs-lookup"><span data-stu-id="29bf3-280">31</span></span></td>
<td><span data-ttu-id="29bf3-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span><span class="sxs-lookup"><span data-stu-id="29bf3-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="29bf3-282">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-283">オンボード中に Windows テレメトリ サービスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="29bf3-284">オフボードプロセスは続行されます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="29bf3-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Windows テレメトリ サービスのエラーを確認します</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-286">32</span><span class="sxs-lookup"><span data-stu-id="29bf3-286">32</span></span></td>
<td><span data-ttu-id="29bf3-287">Microsoft Defender for Endpoint service は、オフボード プロセスの後に自身を停止する要求に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="29bf3-288">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="29bf3-289">オフボード中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="29bf3-290">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-291">33</span><span class="sxs-lookup"><span data-stu-id="29bf3-291">33</span></span></td>
<td><span data-ttu-id="29bf3-292">エンドポイント サービスの Microsoft Defender は、SENSE GUID の永続化に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="29bf3-293">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-294">一意の識別子を使用して、ポータルに報告する各デバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="29bf3-295">識別子が保持されない場合、同じデバイスがポータルに 2 回表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="29bf3-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="29bf3-296">サービスがレジストリを更新できるデバイスのレジストリのアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-297">34</span><span class="sxs-lookup"><span data-stu-id="29bf3-297">34</span></span></td>
<td><span data-ttu-id="29bf3-298">Microsoft Defender for Endpoint Service は、接続されたユーザー エクスペリエンスとテレメトリ サービスへの依存関係として自分自身を追加できなかったので、オンボーディング プロセスが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="29bf3-299">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-300">Windows テレメトリ サービスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="29bf3-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">診断データ サービスが有効になっているか確認します</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="29bf3-302">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="29bf3-303">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="29bf3-304">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="29bf3-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-305">35</span><span class="sxs-lookup"><span data-stu-id="29bf3-305">35</span></span></td>
<td><span data-ttu-id="29bf3-306">Microsoft Defender for Endpoint Service は、接続されたユーザー エクスペリエンスとテレメトリ サービスへの依存関係として削除に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="29bf3-307">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-308">オフボード中に Windows テレメトリ サービスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="29bf3-309">オフボードプロセスは続行されます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="29bf3-310">Windows 診断データ サービスのエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-311">36</span><span class="sxs-lookup"><span data-stu-id="29bf3-311">36</span></span></td>
<td><span data-ttu-id="29bf3-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span><span class="sxs-lookup"><span data-stu-id="29bf3-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="29bf3-313">完了コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="29bf3-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="29bf3-314">Defender for Endpoint の接続ユーザー エクスペリエンスとテレメトリ サービスへの登録が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="29bf3-315">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-316">37</span><span class="sxs-lookup"><span data-stu-id="29bf3-316">37</span></span></td>
<td><span data-ttu-id="29bf3-317">Microsoft Defender for Endpoint A モジュールは、クォータを超えかねない状態です。</span><span class="sxs-lookup"><span data-stu-id="29bf3-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="29bf3-318">モジュール: %1、クォータ: {%2} {%3}、クォータ使用率の割合: %4。</span><span class="sxs-lookup"><span data-stu-id="29bf3-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="29bf3-319">デバイスは、現在の 24 時間ウィンドウの割り当てられたクォータをほとんど使用しています。</span><span class="sxs-lookup"><span data-stu-id="29bf3-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="29bf3-320">調整が必要です。</span><span class="sxs-lookup"><span data-stu-id="29bf3-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="29bf3-321">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-322">38</span><span class="sxs-lookup"><span data-stu-id="29bf3-322">38</span></span></td>
<td><span data-ttu-id="29bf3-323">ネットワーク接続は低として識別されます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-323">Network connection is identified as low.</span></span> <span data-ttu-id="29bf3-324">Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="29bf3-325">メーター接続: %2、インターネット利用可:%3、利用可能な無料ネットワーク:%4。</span><span class="sxs-lookup"><span data-stu-id="29bf3-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="29bf3-326">デバイスは、測定済み/有料ネットワークを使用し、サーバーへの接続頻度が低い。</span><span class="sxs-lookup"><span data-stu-id="29bf3-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="29bf3-327">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-328">39</span><span class="sxs-lookup"><span data-stu-id="29bf3-328">39</span></span></td>
<td><span data-ttu-id="29bf3-329">ネットワーク接続は通常と識別されます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-329">Network connection is identified as normal.</span></span> <span data-ttu-id="29bf3-330">Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="29bf3-331">メーター接続: %2、インターネット利用可:%3、利用可能な無料ネットワーク:%4。</span><span class="sxs-lookup"><span data-stu-id="29bf3-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="29bf3-332">デバイスは、メーター接続または有料接続を使用していなく、通常どおりサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="29bf3-333">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-334">40</span><span class="sxs-lookup"><span data-stu-id="29bf3-334">40</span></span></td>
<td><span data-ttu-id="29bf3-335">バッテリーの状態は低と識別されます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-335">Battery state is identified as low.</span></span> <span data-ttu-id="29bf3-336">Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="29bf3-337">バッテリーの状態: %2。</span><span class="sxs-lookup"><span data-stu-id="29bf3-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="29bf3-338">デバイスのバッテリー 残量が少なく、サーバーに接続する頻度が低い。</span><span class="sxs-lookup"><span data-stu-id="29bf3-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="29bf3-339">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-340">41</span><span class="sxs-lookup"><span data-stu-id="29bf3-340">41</span></span></td>
<td><span data-ttu-id="29bf3-341">バッテリーの状態は、通常の状態として識別されます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-341">Battery state is identified as normal.</span></span> <span data-ttu-id="29bf3-342">Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="29bf3-343">バッテリーの状態: %2。</span><span class="sxs-lookup"><span data-stu-id="29bf3-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="29bf3-344">デバイスのバッテリー 残量が少なめで、通常どおりサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="29bf3-345">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-346">42</span><span class="sxs-lookup"><span data-stu-id="29bf3-346">42</span></span></td>
<td><span data-ttu-id="29bf3-347">Microsoft Defender for Endpoint WDATP コンポーネントは、アクションの実行に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-347">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="29bf3-348">コンポーネント: %1、Action: %2、例外の種類: %3、例外メッセージ: %4</span><span class="sxs-lookup"><span data-stu-id="29bf3-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="29bf3-349">内部エラー。</span><span class="sxs-lookup"><span data-stu-id="29bf3-349">Internal error.</span></span> <span data-ttu-id="29bf3-350">サービスの開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="29bf3-351">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-352">43</span><span class="sxs-lookup"><span data-stu-id="29bf3-352">43</span></span></td>
<td><span data-ttu-id="29bf3-353">Microsoft Defender for Endpoint WDATP コンポーネントは、アクションの実行に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-353">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="29bf3-354">コンポーネント: %1、Action: %2、例外の種類: %3、例外エラー: %4、例外メッセージ: %5</span><span class="sxs-lookup"><span data-stu-id="29bf3-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="29bf3-355">内部エラー。</span><span class="sxs-lookup"><span data-stu-id="29bf3-355">Internal error.</span></span> <span data-ttu-id="29bf3-356">サービスの開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="29bf3-357">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-358">44</span><span class="sxs-lookup"><span data-stu-id="29bf3-358">44</span></span></td>
<td><span data-ttu-id="29bf3-359">Defender for Endpoint サービスのオフボーディングが完了しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="29bf3-360">サービスはオフボードされました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="29bf3-361">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-362">45</span><span class="sxs-lookup"><span data-stu-id="29bf3-362">45</span></span></td>
<td><span data-ttu-id="29bf3-363">イベント トレース セッション [%1] の登録と開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="29bf3-364">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="29bf3-364">Error code: %2</span></span></td>
<td><span data-ttu-id="29bf3-365">ETW セッションの作成時にサービスの起動時にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="29bf3-366">これにより、サービスの起動エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="29bf3-367">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-368">46</span><span class="sxs-lookup"><span data-stu-id="29bf3-368">46</span></span></td>
<td><span data-ttu-id="29bf3-369">リソース不足のため、イベント トレース セッション [%1] の登録と開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="29bf3-370">エラー コード: %2。</span><span class="sxs-lookup"><span data-stu-id="29bf3-370">Error code: %2.</span></span> <span data-ttu-id="29bf3-371">これは、アクティブなイベント トレース セッションが多すぎるためです。</span><span class="sxs-lookup"><span data-stu-id="29bf3-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="29bf3-372">サービスは 1 分で再試行します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="29bf3-373">リソース不足のため、ETW セッションの作成中にサービスの起動時にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="29bf3-374">サービスは開始され、実行中ですが、ETW セッションが開始されるまでセンサー イベントは報告できません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="29bf3-375">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="29bf3-376">サービスは、1 分ごとにセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-377">47</span><span class="sxs-lookup"><span data-stu-id="29bf3-377">47</span></span></td>
<td><span data-ttu-id="29bf3-378">イベント トレース セッションが正常に登録され、開始されました 。 以前に失敗した試行後に回復されました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="29bf3-379">このイベントは、ETW セッションを正常に開始した後、前のイベントに従います。</span><span class="sxs-lookup"><span data-stu-id="29bf3-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="29bf3-380">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="29bf3-381">48</span><span class="sxs-lookup"><span data-stu-id="29bf3-381">48</span></span></td>
<td><span data-ttu-id="29bf3-382">イベント トレース セッション [%2] にプロバイダー [%1] を追加できなかった。</span><span class="sxs-lookup"><span data-stu-id="29bf3-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="29bf3-383">エラー コード: %3。</span><span class="sxs-lookup"><span data-stu-id="29bf3-383">Error code: %3.</span></span> <span data-ttu-id="29bf3-384">つまり、このプロバイダーからのイベントは報告されません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="29bf3-385">ETW セッションにプロバイダーを追加できなかった。</span><span class="sxs-lookup"><span data-stu-id="29bf3-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="29bf3-386">その結果、プロバイダー イベントは報告されません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="29bf3-387">エラー コードを確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-387">Check the error code.</span></span> <span data-ttu-id="29bf3-388">エラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-389">49</span><span class="sxs-lookup"><span data-stu-id="29bf3-389">49</span></span></td>
   <td><span data-ttu-id="29bf3-390">無効なクラウド構成コマンドが受信され、無視されます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="29bf3-391">バージョン: %1、状態: %2、エラー コード: %3、メッセージ: %4</span><span class="sxs-lookup"><span data-stu-id="29bf3-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="29bf3-392">無視されたクラウド サービスから無効な構成ファイルを受け取った。</span><span class="sxs-lookup"><span data-stu-id="29bf3-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="29bf3-393">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-394">50</span><span class="sxs-lookup"><span data-stu-id="29bf3-394">50</span></span></td>
   <td><span data-ttu-id="29bf3-395">新しいクラウド構成が正常に適用されました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="29bf3-396">バージョン: %1。</span><span class="sxs-lookup"><span data-stu-id="29bf3-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="29bf3-397">クラウド サービスから新しい構成を正常に適用しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="29bf3-398">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-399">51</span><span class="sxs-lookup"><span data-stu-id="29bf3-399">51</span></span></td>
   <td><span data-ttu-id="29bf3-400">新しいクラウド構成の適用に失敗しました。バージョン: %1。</span><span class="sxs-lookup"><span data-stu-id="29bf3-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="29bf3-401">最後の既知の良い構成であるバージョン %2 が正常に適用されました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="29bf3-402">クラウド サービスから悪い構成ファイルを受け取った。</span><span class="sxs-lookup"><span data-stu-id="29bf3-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="29bf3-403">最後に既知の良好な構成が正常に適用されました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="29bf3-404">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-405">52</span><span class="sxs-lookup"><span data-stu-id="29bf3-405">52</span></span></td>
   <td><span data-ttu-id="29bf3-406">新しいクラウド構成の適用に失敗しました。バージョン: %1。</span><span class="sxs-lookup"><span data-stu-id="29bf3-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="29bf3-407">また、前回の既知の良好な構成バージョン %2 の適用にも失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="29bf3-408">既定の構成が正常に適用されました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="29bf3-409">クラウド サービスから悪い構成ファイルを受け取った。</span><span class="sxs-lookup"><span data-stu-id="29bf3-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="29bf3-410">前回の既知の良好な構成の適用に失敗し、既定の構成が適用されました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="29bf3-411">サービスは、5 分以内に新しい構成ファイルのダウンロードを試みます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="29bf3-412">イベント が表示#50サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-413">53</span><span class="sxs-lookup"><span data-stu-id="29bf3-413">53</span></span></td>
   <td><span data-ttu-id="29bf3-414">永続的な記憶域から読み込まれたクラウド構成のバージョン: %1。</span><span class="sxs-lookup"><span data-stu-id="29bf3-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="29bf3-415">構成は、サービスの起動時に永続的な記憶域から読み込まれた。</span><span class="sxs-lookup"><span data-stu-id="29bf3-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="29bf3-416">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-417">55</span><span class="sxs-lookup"><span data-stu-id="29bf3-417">55</span></span></td>
   <td><span data-ttu-id="29bf3-418">Secure ETW 自動ロガーの作成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="29bf3-419">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="29bf3-420">セキュリティで保護された ETW ロガーの作成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="29bf3-421">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-421">Reboot the device.</span></span> <span data-ttu-id="29bf3-422">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-423">56</span><span class="sxs-lookup"><span data-stu-id="29bf3-423">56</span></span></td>
   <td><span data-ttu-id="29bf3-424">Secure ETW 自動ロガーの削除に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="29bf3-425">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="29bf3-426">オフボーディング時にセキュリティで保護された ETW セッションを削除できなかった。</span><span class="sxs-lookup"><span data-stu-id="29bf3-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="29bf3-427">サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-428">57</span><span class="sxs-lookup"><span data-stu-id="29bf3-428">57</span></span></td>
   <td><span data-ttu-id="29bf3-429">トラブルシューティングの目的でコンピューターのスナップショットをキャプチャする。</span><span class="sxs-lookup"><span data-stu-id="29bf3-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="29bf3-430">調査パッケージ (forensics パッケージとも呼ばれる) が収集されています。</span><span class="sxs-lookup"><span data-stu-id="29bf3-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="29bf3-431">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-432">59</span><span class="sxs-lookup"><span data-stu-id="29bf3-432">59</span></span></td>
   <td><span data-ttu-id="29bf3-433">開始コマンド: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="29bf3-434">応答コマンドの実行を開始します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="29bf3-435">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-436">60</span><span class="sxs-lookup"><span data-stu-id="29bf3-436">60</span></span></td>
   <td><span data-ttu-id="29bf3-437">コマンド %1 の実行に失敗しました。エラー: %2。</span><span class="sxs-lookup"><span data-stu-id="29bf3-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="29bf3-438">応答コマンドの実行に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="29bf3-439">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-440">61</span><span class="sxs-lookup"><span data-stu-id="29bf3-440">61</span></span></td>
   <td><span data-ttu-id="29bf3-441">データ収集コマンド パラメーターが無効です。SasUri: %1、compressionLevel: %2。</span><span class="sxs-lookup"><span data-stu-id="29bf3-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="29bf3-442">データ収集コマンドの引数 (無効な引数) の読み取りまたは解析に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="29bf3-443">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-444">62</span><span class="sxs-lookup"><span data-stu-id="29bf3-444">62</span></span></td>
   <td><span data-ttu-id="29bf3-445">接続ユーザー エクスペリエンスとテレメトリ サービスの開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="29bf3-446">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="29bf3-447">接続されたユーザー エクスペリエンスとテレメトリ (diagtrack) サービスの開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="29bf3-448">Microsoft Defender for Endpoint テレメトリ以外は、このコンピューターから送信されません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="29bf3-449">イベント ログのトラブルシューティング のヒントを探します。Microsoft-Windows-UniversalTelemetryClient/Operational。</span><span class="sxs-lookup"><span data-stu-id="29bf3-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-450">63</span><span class="sxs-lookup"><span data-stu-id="29bf3-450">63</span></span></td>
   <td><span data-ttu-id="29bf3-451">外部サービスの開始の種類を更新します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-451">Updating the start type of external service.</span></span> <span data-ttu-id="29bf3-452">名前: %1、実際の開始の種類: %2、予期される開始の種類: %3、終了コード: %4</span><span class="sxs-lookup"><span data-stu-id="29bf3-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="29bf3-453">外部サービスの開始の種類を更新しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="29bf3-454">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-455">64</span><span class="sxs-lookup"><span data-stu-id="29bf3-455">64</span></span></td>
   <td><span data-ttu-id="29bf3-456">停止した外部サービスの開始。</span><span class="sxs-lookup"><span data-stu-id="29bf3-456">Starting stopped external service.</span></span> <span data-ttu-id="29bf3-457">名前: %1、終了コード: %2</span><span class="sxs-lookup"><span data-stu-id="29bf3-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="29bf3-458">外部サービスの開始。</span><span class="sxs-lookup"><span data-stu-id="29bf3-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="29bf3-459">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-460">65</span><span class="sxs-lookup"><span data-stu-id="29bf3-460">65</span></span></td>
   <td><span data-ttu-id="29bf3-461">Microsoft セキュリティ イベント コンポーネント ミニフィルター ドライバーの読み込みに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="29bf3-462">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="29bf3-463">ファイルシステムのミニフィルターMsSecFlt.sys読み込めない。</span><span class="sxs-lookup"><span data-stu-id="29bf3-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="29bf3-464">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-464">Reboot the device.</span></span> <span data-ttu-id="29bf3-465">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-466">66</span><span class="sxs-lookup"><span data-stu-id="29bf3-466">66</span></span></td>
   <td><span data-ttu-id="29bf3-467">ポリシー更新プログラム: 待機時間モード - %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="29bf3-468">C&C 接続頻度ポリシーが更新されました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="29bf3-469">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-470">68</span><span class="sxs-lookup"><span data-stu-id="29bf3-470">68</span></span></td>
   <td><span data-ttu-id="29bf3-471">サービスの開始の種類が予期しない。</span><span class="sxs-lookup"><span data-stu-id="29bf3-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="29bf3-472">サービス名: %1、実際の開始の種類: %2、予期される開始の種類: %3</span><span class="sxs-lookup"><span data-stu-id="29bf3-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="29bf3-473">予期しない外部サービスの開始の種類。</span><span class="sxs-lookup"><span data-stu-id="29bf3-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="29bf3-474">外部サービスの開始の種類を修正します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-475">69</span><span class="sxs-lookup"><span data-stu-id="29bf3-475">69</span></span></td>
   <td><span data-ttu-id="29bf3-476">サービスが停止します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-476">The service is stopped.</span></span> <span data-ttu-id="29bf3-477">サービス名: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="29bf3-478">外部サービスが停止します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="29bf3-479">外部サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-480">70</span><span class="sxs-lookup"><span data-stu-id="29bf3-480">70</span></span></td>
   <td><span data-ttu-id="29bf3-481">ポリシー更新: サンプル コレクションを許可する - %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="29bf3-482">サンプル コレクション ポリシーが更新されました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="29bf3-483">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-484">71</span><span class="sxs-lookup"><span data-stu-id="29bf3-484">71</span></span></td>
   <td><span data-ttu-id="29bf3-485">コマンドの実行に成功しました: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="29bf3-486">コマンドが正常に実行されました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="29bf3-487">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-488">72</span><span class="sxs-lookup"><span data-stu-id="29bf3-488">72</span></span></td>
   <td><span data-ttu-id="29bf3-489">最初の完全なコンピューター プロファイル レポートの送信を試みました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="29bf3-490">結果コード: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="29bf3-491">情報提供のみ。</span><span class="sxs-lookup"><span data-stu-id="29bf3-491">Informational only.</span></span></td>
   <td><span data-ttu-id="29bf3-492">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-493">73</span><span class="sxs-lookup"><span data-stu-id="29bf3-493">73</span></span></td>
   <td><span data-ttu-id="29bf3-494">プラットフォームの開始センス: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="29bf3-495">情報提供のみ。</span><span class="sxs-lookup"><span data-stu-id="29bf3-495">Informational only.</span></span></td>
   <td><span data-ttu-id="29bf3-496">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-497">74</span><span class="sxs-lookup"><span data-stu-id="29bf3-497">74</span></span></td>
   <td><span data-ttu-id="29bf3-498">レジストリ内のデバイス タグが長さの制限を超えています。</span><span class="sxs-lookup"><span data-stu-id="29bf3-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="29bf3-499">タグ名: %2。</span><span class="sxs-lookup"><span data-stu-id="29bf3-499">Tag name: %2.</span></span> <span data-ttu-id="29bf3-500">長さの制限: %1。</span><span class="sxs-lookup"><span data-stu-id="29bf3-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="29bf3-501">デバイス タグが長さの制限を超えています。</span><span class="sxs-lookup"><span data-stu-id="29bf3-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="29bf3-502">短いデバイス タグを使用します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-503">81</span><span class="sxs-lookup"><span data-stu-id="29bf3-503">81</span></span></td>
   <td><span data-ttu-id="29bf3-504">Advanced Threat Protection ETW Windows Defenderを作成できなかった。</span><span class="sxs-lookup"><span data-stu-id="29bf3-504">Failed to create Windows Defender Advanced Threat Protection ETW autologger.</span></span> <span data-ttu-id="29bf3-505">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="29bf3-506">ETW セッションの作成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="29bf3-507">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-507">Reboot the device.</span></span> <span data-ttu-id="29bf3-508">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-509">82</span><span class="sxs-lookup"><span data-stu-id="29bf3-509">82</span></span></td>
   <td><span data-ttu-id="29bf3-510">Advanced Threat Protection ETW Windows Defenderを削除できなかった。</span><span class="sxs-lookup"><span data-stu-id="29bf3-510">Failed to remove Windows Defender Advanced Threat Protection ETW autologger.</span></span> <span data-ttu-id="29bf3-511">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="29bf3-512">ETW セッションの削除に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="29bf3-513">サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-514">84</span><span class="sxs-lookup"><span data-stu-id="29bf3-514">84</span></span></td>
   <td><span data-ttu-id="29bf3-515">ウイルス対策Windows Defenderモードを設定します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="29bf3-516">強制パッシブ モード: %1、結果コード: %2。</span><span class="sxs-lookup"><span data-stu-id="29bf3-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="29bf3-517">Defender の実行モード (アクティブまたはパッシブ) を設定します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="29bf3-518">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-519">85</span><span class="sxs-lookup"><span data-stu-id="29bf3-519">85</span></span></td>
   <td><span data-ttu-id="29bf3-520">Advanced Threat Protection 実行可能ファイルWindows Defenderトリガーに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-520">Failed to trigger Windows Defender Advanced Threat Protection executable.</span></span> <span data-ttu-id="29bf3-521">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="29bf3-522">SenseIR 実行可能ファイルの主演に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="29bf3-523">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-523">Reboot the device.</span></span> <span data-ttu-id="29bf3-524">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-525">86</span><span class="sxs-lookup"><span data-stu-id="29bf3-525">86</span></span></td>
   <td><span data-ttu-id="29bf3-526">もう一度開始すると、起動する必要がある外部サービスが停止しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="29bf3-527">名前: %1、終了コード: %2</span><span class="sxs-lookup"><span data-stu-id="29bf3-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="29bf3-528">外部サービスを再度開始します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="29bf3-529">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-530">87</span><span class="sxs-lookup"><span data-stu-id="29bf3-530">87</span></span></td>
   <td><span data-ttu-id="29bf3-531">外部サービスを開始できません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-531">Cannot start the external service.</span></span> <span data-ttu-id="29bf3-532">名前: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-532">Name: %1</span></span></td>
   <td><span data-ttu-id="29bf3-533">外部サービスの開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="29bf3-534">サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-535">88</span><span class="sxs-lookup"><span data-stu-id="29bf3-535">88</span></span></td>
   <td><span data-ttu-id="29bf3-536">外部サービスの開始の種類を再度更新します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-536">Updating the start type of external service again.</span></span> <span data-ttu-id="29bf3-537">名前: %1、実際の開始の種類: %2、予期される開始の種類: %3、終了コード: %4</span><span class="sxs-lookup"><span data-stu-id="29bf3-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="29bf3-538">外部サービスの開始の種類を更新しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="29bf3-539">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-540">89</span><span class="sxs-lookup"><span data-stu-id="29bf3-540">89</span></span></td>
   <td><span data-ttu-id="29bf3-541">外部サービスの開始の種類を更新できません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="29bf3-542">名前: %1、実際の開始の種類: %2、予期される開始の種類: %3</span><span class="sxs-lookup"><span data-stu-id="29bf3-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="29bf3-543">外部サービスの開始の種類を更新できない。</span><span class="sxs-lookup"><span data-stu-id="29bf3-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="29bf3-544">サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-545">90</span><span class="sxs-lookup"><span data-stu-id="29bf3-545">90</span></span></td>
   <td><span data-ttu-id="29bf3-546">地域 %1 のクラウド サービスに接続するための System Guard ランタイム モニターの構成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="29bf3-547">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="29bf3-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="29bf3-548">System Guard ランタイム モニターは、構成証明データをクラウド サービスに送信しない。</span><span class="sxs-lookup"><span data-stu-id="29bf3-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="29bf3-549">登録パスのアクセス許可を確認します。"HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。</span><span class="sxs-lookup"><span data-stu-id="29bf3-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="29bf3-550">問題が見つからない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-551">91</span><span class="sxs-lookup"><span data-stu-id="29bf3-551">91</span></span></td>
   <td><span data-ttu-id="29bf3-552">System Guard ランタイム モニター地域情報の削除に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="29bf3-553">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="29bf3-554">System Guard ランタイム モニターは、構成証明データをクラウド サービスに送信しない。</span><span class="sxs-lookup"><span data-stu-id="29bf3-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="29bf3-555">登録パスのアクセス許可を確認します。"HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm"。</span><span class="sxs-lookup"><span data-stu-id="29bf3-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="29bf3-556">問題が見つからない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-557">92</span><span class="sxs-lookup"><span data-stu-id="29bf3-557">92</span></span></td>
   <td><span data-ttu-id="29bf3-558">データ クォータを超えたため、センサーのサイバー データ クォータの送信を停止します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="29bf3-559">クォータ期間が過ぎると、送信が再開されます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="29bf3-560">状態マスク: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="29bf3-561">調整の制限を超える。</span><span class="sxs-lookup"><span data-stu-id="29bf3-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="29bf3-562">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-563">93</span><span class="sxs-lookup"><span data-stu-id="29bf3-563">93</span></span></td>
   <td><span data-ttu-id="29bf3-564">センサーのサイバー データの送信を再送信する。</span><span class="sxs-lookup"><span data-stu-id="29bf3-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="29bf3-565">状態マスク: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="29bf3-566">サイバー データの送信を再開します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="29bf3-567">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-568">94</span><span class="sxs-lookup"><span data-stu-id="29bf3-568">94</span></span></td>
   <td><span data-ttu-id="29bf3-569">Windows Defender高度な脅威保護の実行可能ファイルが開始されました</span><span class="sxs-lookup"><span data-stu-id="29bf3-569">Windows Defender Advanced Threat Protection executable has started</span></span></td>
   <td><span data-ttu-id="29bf3-570">SenseCE 実行可能ファイルが開始されました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="29bf3-571">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-572">95</span><span class="sxs-lookup"><span data-stu-id="29bf3-572">95</span></span></td>
   <td><span data-ttu-id="29bf3-573">Windows Defender Advanced Threat Protection 実行可能ファイルが終了しました</span><span class="sxs-lookup"><span data-stu-id="29bf3-573">Windows Defender Advanced Threat Protection executable has ended</span></span></td>
   <td><span data-ttu-id="29bf3-574">SenseCE 実行可能ファイルが終了しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="29bf3-575">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-576">96</span><span class="sxs-lookup"><span data-stu-id="29bf3-576">96</span></span></td>
   <td><span data-ttu-id="29bf3-577">Windows Defender高度な脅威保護 Init が呼び出しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-577">Windows Defender Advanced Threat Protection Init has called.</span></span> <span data-ttu-id="29bf3-578">結果コード: %2</span><span class="sxs-lookup"><span data-stu-id="29bf3-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="29bf3-579">SenseCE 実行可能ファイルは MCE 初期化と呼ばされています。</span><span class="sxs-lookup"><span data-stu-id="29bf3-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="29bf3-580">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-581">97</span><span class="sxs-lookup"><span data-stu-id="29bf3-581">97</span></span></td>
   <td><span data-ttu-id="29bf3-582">DLP シナリオのクラウドへの接続に関する問題がある</span><span class="sxs-lookup"><span data-stu-id="29bf3-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="29bf3-583">DLP 分類フローに影響するネットワーク接続の問題があります。</span><span class="sxs-lookup"><span data-stu-id="29bf3-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="29bf3-584">ネットワーク接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-585">98</span><span class="sxs-lookup"><span data-stu-id="29bf3-585">98</span></span></td>
   <td><span data-ttu-id="29bf3-586">DLP シナリオのクラウドへの接続が復元されました</span><span class="sxs-lookup"><span data-stu-id="29bf3-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="29bf3-587">ネットワークへの接続が復元され、DLP 分類フローを続行できます。</span><span class="sxs-lookup"><span data-stu-id="29bf3-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="29bf3-588">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-589">99</span><span class="sxs-lookup"><span data-stu-id="29bf3-589">99</span></span></td>
   <td><span data-ttu-id="29bf3-590">サーバーとの通信中に、センスで次のエラーが発生しました。(%1)。</span><span class="sxs-lookup"><span data-stu-id="29bf3-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="29bf3-591">結果: (%2)</span><span class="sxs-lookup"><span data-stu-id="29bf3-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="29bf3-592">通信エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="29bf3-593">詳細については、イベント ログで次のイベントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-594">100</span><span class="sxs-lookup"><span data-stu-id="29bf3-594">100</span></span></td>
   <td><span data-ttu-id="29bf3-595">Windows Defender Advanced Threat Protection 実行可能ファイルの起動に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-595">Windows Defender Advanced Threat Protection executable failed to start.</span></span> <span data-ttu-id="29bf3-596">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="29bf3-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="29bf3-597">SenseCE 実行可能ファイルの起動に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="29bf3-598">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="29bf3-598">Reboot the device.</span></span> <span data-ttu-id="29bf3-599">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="29bf3-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-600">102</span><span class="sxs-lookup"><span data-stu-id="29bf3-600">102</span></span></td>
   <td><span data-ttu-id="29bf3-601">Windows Defender高度な脅威保護ネットワークの検出と応答の実行可能ファイルが開始されました</span><span class="sxs-lookup"><span data-stu-id="29bf3-601">Windows Defender Advanced Threat Protection Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="29bf3-602">SenseNdr 実行可能ファイルが開始されました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="29bf3-603">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="29bf3-604">103</span><span class="sxs-lookup"><span data-stu-id="29bf3-604">103</span></span></td>
   <td><span data-ttu-id="29bf3-605">Windows Defender高度な脅威保護ネットワークの検出と応答の実行可能ファイルが終了しました</span><span class="sxs-lookup"><span data-stu-id="29bf3-605">Windows Defender Advanced Threat Protection Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="29bf3-606">SenseNdr 実行可能ファイルが終了しました。</span><span class="sxs-lookup"><span data-stu-id="29bf3-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="29bf3-607">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="29bf3-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="29bf3-608">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="29bf3-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="29bf3-609">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="29bf3-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="29bf3-610">関連項目</span><span class="sxs-lookup"><span data-stu-id="29bf3-610">Related topics</span></span>
- [<span data-ttu-id="29bf3-611">オンボード Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="29bf3-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="29bf3-612">デバイス プロキシとインターネット接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="29bf3-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="29bf3-613">エンドポイントの Microsoft Defender のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="29bf3-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
