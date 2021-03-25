---
title: イベント ビューアーを使用してイベントとエラーを確認する
description: Microsoft Defender for Endpoint サービスによって報告されたすべてのイベントの説明とトラブルシューティング手順 (必要な場合) を取得します。
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
ms.openlocfilehash: 98c0f790c228989b261b95f3b87cdc9d18e4fa76
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068580"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="5fcdf-104">イベント ビューアーを使用してイベントとエラーを確認する</span><span class="sxs-lookup"><span data-stu-id="5fcdf-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5fcdf-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5fcdf-105">**Applies to:**</span></span>
- <span data-ttu-id="5fcdf-106">イベント ビューアー</span><span class="sxs-lookup"><span data-stu-id="5fcdf-106">Event Viewer</span></span>
- [<span data-ttu-id="5fcdf-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5fcdf-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="5fcdf-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5fcdf-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5fcdf-109">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="5fcdf-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5fcdf-110">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="5fcdf-111">イベントの ID は、個々のデバイスの [イベント ビューアー](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) で確認できます。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="5fcdf-112">たとえば、[デバイス] リストにデバイスが表示されない場合は、デバイスでイベントの ID を探す必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-112">For example, if devices are not appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="5fcdf-113">次に、この表を使用して、さらにトラブルシューティングの手順を決定できます。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="5fcdf-114">**イベント ビューアーを開き、Microsoft Defender for Endpoint サービス イベント ログを検索します。**</span><span class="sxs-lookup"><span data-stu-id="5fcdf-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="5fcdf-115">**[Windows] メニューの**[スタート] をクリックし、「イベント ビューアー」**と入力し**、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="5fcdf-116">ログ リストの [ログの概要 **] で\*\*\*\*、Microsoft-Windows-SENSE/Operational が表示されるまでスクロールします**。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="5fcdf-117">アイテムをダブルクリックしてログを開きます。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="5fcdf-118">a.</span><span class="sxs-lookup"><span data-stu-id="5fcdf-118">a.</span></span>  <span data-ttu-id="5fcdf-119">[アプリケーションとサービス ログ] Microsoft Windows SENSE を展開して [操作] をクリックして、ログ  >    >    >  に **アクセスすることもできます**。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5fcdf-120">SENSE は、Microsoft Defender for Endpoint をサポートする動作センサーを参照するために使用される内部名です。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="5fcdf-121">サービスによって記録されたイベントがログに表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="5fcdf-122">サービスによって記録されるイベントの一覧については、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="5fcdf-123">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5fcdf-123">Event ID</span></span></th>
<th><span data-ttu-id="5fcdf-124">メッセージ</span><span class="sxs-lookup"><span data-stu-id="5fcdf-124">Message</span></span></th>
<th><span data-ttu-id="5fcdf-125">説明</span><span class="sxs-lookup"><span data-stu-id="5fcdf-125">Description</span></span></th>
<th><span data-ttu-id="5fcdf-126">アクション</span><span class="sxs-lookup"><span data-stu-id="5fcdf-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-127">1</span><span class="sxs-lookup"><span data-stu-id="5fcdf-127">1</span></span></td>
<td><span data-ttu-id="5fcdf-128">Microsoft Defender for Endpoint service が開始されました (バージョン <code>variable</code> )。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="5fcdf-129">システムの起動、シャットダウン、およびオンボード中に発生します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-129">Occurs during system start up, shut down, and during onbboarding.</span></span></td>
<td><span data-ttu-id="5fcdf-130">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-131">2</span><span class="sxs-lookup"><span data-stu-id="5fcdf-131">2</span></span></td>
<td><span data-ttu-id="5fcdf-132">Microsoft Defender for Endpoint service shutdown.</span><span class="sxs-lookup"><span data-stu-id="5fcdf-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="5fcdf-133">デバイスがシャットダウンまたはオフボードされている場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="5fcdf-134">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-135">3</span><span class="sxs-lookup"><span data-stu-id="5fcdf-135">3</span></span></td>
<td><span data-ttu-id="5fcdf-136">Microsoft Defender for Endpoint service の開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="5fcdf-137">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-138">サービスが開始しなかった。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-138">Service did not start.</span></span></td>
<td><span data-ttu-id="5fcdf-139">他のメッセージを確認して、考えられる原因とトラブルシューティングの手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-140">4</span><span class="sxs-lookup"><span data-stu-id="5fcdf-140">4</span></span></td>
<td><span data-ttu-id="5fcdf-141">Microsoft Defender for Endpoint service がでサーバーに連絡しました <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-142">Variable = Defender for Endpoint 処理サーバーの URL。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="5fcdf-143">この URL は、ファイアウォールまたはネットワーク アクティビティに表示される URL と一致します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="5fcdf-144">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-145">5</span><span class="sxs-lookup"><span data-stu-id="5fcdf-145">5</span></span></td>
<td><span data-ttu-id="5fcdf-146">Microsoft Defender for Endpoint service でサーバーへの接続に失敗しました <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-147">Variable = Defender for Endpoint 処理サーバーの URL。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="5fcdf-148">サービスは、その URL の外部処理サーバーに接続できません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-148">The service could not contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="5fcdf-149">URL への接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-149">Check the connection to the URL.</span></span> <span data-ttu-id="5fcdf-150">「Configure <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">proxy and Internet connectivity」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-151">6</span><span class="sxs-lookup"><span data-stu-id="5fcdf-151">6</span></span></td>
<td><span data-ttu-id="5fcdf-152">Microsoft Defender for Endpoint Service はオンボードされていないので、オンボーディング パラメーターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="5fcdf-153">デバイスが正しくオンボードされていないので、ポータルに報告されません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-153">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="5fcdf-154">サービスを開始する前にオンボーディングを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="5fcdf-155">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5fcdf-156">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5fcdf-157">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-158">7</span><span class="sxs-lookup"><span data-stu-id="5fcdf-158">7</span></span></td>
<td><span data-ttu-id="5fcdf-159">Microsoft Defender for Endpoint service では、オンボーディング パラメーターの読み取りが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="5fcdf-160">失敗: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-161">変数 = 詳細なエラーの説明。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-161">Variable = detailed error description.</span></span> <span data-ttu-id="5fcdf-162">デバイスが正しくオンボードされていないので、ポータルに報告されません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-162">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="5fcdf-163">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5fcdf-164">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5fcdf-165">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-166">8</span><span class="sxs-lookup"><span data-stu-id="5fcdf-166">8</span></span></td>
<td><span data-ttu-id="5fcdf-167">Microsoft Defender for Endpoint service では、構成のクリーンアップに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="5fcdf-168">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-169"><b>オンボーディング中:</b> サービスは、オンボーディング中に構成のクリーンアップに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="5fcdf-170">オンボーディング プロセスは続行されます。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="5fcdf-171"><b>オフボード中:</b> サービスは、オフボード中に構成のクリーンアップに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="5fcdf-172">オフボード プロセスは終了しましたが、サービスは実行を続ける。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="5fcdf-173"><b>オンボーディング:</b> アクションは不要です。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="5fcdf-174"><b>オフボード:</b> システムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="5fcdf-175">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-176">9</span><span class="sxs-lookup"><span data-stu-id="5fcdf-176">9</span></span></td>
<td><span data-ttu-id="5fcdf-177">Microsoft Defender for Endpoint service は、開始の種類を変更できなかった。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="5fcdf-178">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-179"><b>オンボーディング中:</b> デバイスが正しくオンボードされていないので、ポータルに報告されません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-179"><b>During onboarding:</b> The device did not onboard correctly and will not be reporting to the portal.</span></span> <br><br><span data-ttu-id="5fcdf-180"><b>オフボード中:</b> サービスの開始の種類を変更できなかった。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="5fcdf-181">オフボードプロセスは続行されます。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="5fcdf-182">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5fcdf-183">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5fcdf-184">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-185">10</span><span class="sxs-lookup"><span data-stu-id="5fcdf-185">10</span></span></td>
<td><span data-ttu-id="5fcdf-186">Microsoft Defender for Endpoint Service は、オンボーディング情報を保持できなかった。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="5fcdf-187">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-188">デバイスが正しくオンボードされていないので、ポータルに報告されません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-188">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="5fcdf-189">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5fcdf-190">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5fcdf-191">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-192">11</span><span class="sxs-lookup"><span data-stu-id="5fcdf-192">11</span></span></td>
<td><span data-ttu-id="5fcdf-193">Defender for Endpoint サービスのオンボーディングまたは再オンボーディングが完了しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="5fcdf-194">デバイスが正しくオンボードされました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="5fcdf-195">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="5fcdf-196">デバイスがポータルに表示されるには数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-197">12 </span><span class="sxs-lookup"><span data-stu-id="5fcdf-197">12</span></span></td>
<td><span data-ttu-id="5fcdf-198">Microsoft Defender for Endpoint では、既定の構成の適用に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="5fcdf-199">サービスが既定の構成を適用できなかった。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="5fcdf-200">このエラーは、短時間で解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-201">13</span><span class="sxs-lookup"><span data-stu-id="5fcdf-201">13</span></span></td>
<td><span data-ttu-id="5fcdf-202">Microsoft Defender for Endpoint デバイス ID が計算 <code>variable</code> されます。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-203">通常の操作プロセス。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="5fcdf-204">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-205">15 </span><span class="sxs-lookup"><span data-stu-id="5fcdf-205">15</span></span></td>
<td><span data-ttu-id="5fcdf-206">エンドポイントの Microsoft Defender は、URL を使用してコマンド チャネルを開始できません <code>variable</code> 。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-207">Variable = Defender for Endpoint 処理サーバーの URL。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="5fcdf-208">サービスは、その URL の外部処理サーバーに接続できません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-208">The service could not contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="5fcdf-209">URL への接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-209">Check the connection to the URL.</span></span> <span data-ttu-id="5fcdf-210">「Configure <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">proxy and Internet connectivity」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-211">17 </span><span class="sxs-lookup"><span data-stu-id="5fcdf-211">17</span></span></td>
<td><span data-ttu-id="5fcdf-212">Microsoft Defender for Endpoint service は、接続されたユーザー エクスペリエンスとテレメトリ サービスの場所を変更できなかった。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="5fcdf-213">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-214">Windows テレメトリ サービスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="5fcdf-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">診断データ サービスが有効になっているか確認します</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="5fcdf-216">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5fcdf-217">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5fcdf-218">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-219">18 </span><span class="sxs-lookup"><span data-stu-id="5fcdf-219">18</span></span></td>
<td><span data-ttu-id="5fcdf-220">OOBE (Windows ようこそ) が完了しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="5fcdf-221">サービスは、Windows 更新プログラムのインストールが完了した後にのみ開始されます。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="5fcdf-222">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-223">19</span><span class="sxs-lookup"><span data-stu-id="5fcdf-223">19</span></span></td>
<td><span data-ttu-id="5fcdf-224">OOBE (Windows ようこそ) がまだ完了していません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="5fcdf-225">サービスは、Windows 更新プログラムのインストールが完了した後にのみ開始されます。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="5fcdf-226">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="5fcdf-227">システムの再起動後もこのエラーが解決しない場合は、すべての Windows 更新プログラムが完全にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-228">20</span><span class="sxs-lookup"><span data-stu-id="5fcdf-228">20</span></span></td>
<td><span data-ttu-id="5fcdf-229">OOBE (Windows ようこそ) が完了するのを待つ必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="5fcdf-230">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-231">内部エラー。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-231">Internal error.</span></span></td>
<td><span data-ttu-id="5fcdf-232">システムの再起動後もこのエラーが解決しない場合は、すべての Windows 更新プログラムが完全にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-233">25</span><span class="sxs-lookup"><span data-stu-id="5fcdf-233">25</span></span></td>
<td><span data-ttu-id="5fcdf-234">Microsoft Defender for Endpoint service は、レジストリの正常性状態をリセットできなかった。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="5fcdf-235">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-236">デバイスが正しくオンボードされませんでした。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-236">The device did not onboard correctly.</span></span>
<span data-ttu-id="5fcdf-237">ポータルに報告しますが、サービスが SCCM またはレジストリに登録されていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="5fcdf-238">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5fcdf-239">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5fcdf-240">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-241">26</span><span class="sxs-lookup"><span data-stu-id="5fcdf-241">26</span></span></td>
<td><span data-ttu-id="5fcdf-242">Microsoft Defender for Endpoint service は、レジストリのオンボーディングの状態を設定できなかった。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="5fcdf-243">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-244">デバイスが正しくオンボードされませんでした。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-244">The device did not onboard correctly.</span></span><br>
<span data-ttu-id="5fcdf-245">ポータルに報告しますが、サービスが SCCM またはレジストリに登録されていない場合があります。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="5fcdf-246">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5fcdf-247">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5fcdf-248">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-249">27</span><span class="sxs-lookup"><span data-stu-id="5fcdf-249">27</span></span></td>
<td><span data-ttu-id="5fcdf-250">Microsoft Defender for Endpoint Service は、Microsoft Defender ウイルス対策で SENSE 対応モードを有効にできなかった。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="5fcdf-251">オンボーディング プロセスに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-251">Onboarding process failed.</span></span> <span data-ttu-id="5fcdf-252">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-253">通常、別のリアルタイムマルウェア対策製品がデバイスで適切に実行され、デバイスが Defender for Endpoint に報告されている場合、Microsoft Defender ウイルス対策は特別なパッシブ状態になります。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="5fcdf-254">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5fcdf-255">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5fcdf-256">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="5fcdf-257">リアルタイムのマルウェア対策保護が正しく実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-258">28</span><span class="sxs-lookup"><span data-stu-id="5fcdf-258">28</span></span></td>
<td><span data-ttu-id="5fcdf-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span><span class="sxs-lookup"><span data-stu-id="5fcdf-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="5fcdf-260">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-261">Windows テレメトリ サービスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="5fcdf-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">診断データ サービスが有効になっているか確認します</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="5fcdf-263">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5fcdf-264">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5fcdf-265">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-266">29</span><span class="sxs-lookup"><span data-stu-id="5fcdf-266">29</span></span></td>
<td><span data-ttu-id="5fcdf-267">オフボード パラメーターの読み取りに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="5fcdf-268">エラーの種類: %1、エラー コード: %2、説明: %3</span><span class="sxs-lookup"><span data-stu-id="5fcdf-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="5fcdf-269">このイベントは、システムがオフボード パラメーター&#39;読み取りできない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="5fcdf-270">デバイスにインターネット アクセス権が設定されているのを確認し、オフボード プロセス全体を再度実行します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="5fcdf-271">オフボード パッケージの有効期限が切れていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-271">Ensure the offboarding package has not expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-272">30</span><span class="sxs-lookup"><span data-stu-id="5fcdf-272">30</span></span></td>
<td><span data-ttu-id="5fcdf-273">Microsoft Defender for Endpoint Service は、Microsoft Defender ウイルス対策で SENSE 対応モードを無効にできなかった。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="5fcdf-274">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-275">通常、別のリアルタイムマルウェア対策製品がデバイスで適切に実行され、デバイスが Defender for Endpoint に報告されている場合、Microsoft Defender ウイルス対策は特別なパッシブ状態になります。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="5fcdf-276">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5fcdf-277">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5fcdf-278">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください。</a></span><span class="sxs-lookup"><span data-stu-id="5fcdf-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="5fcdf-279">リアルタイムのマルウェア対策保護が正しく実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-280">31</span><span class="sxs-lookup"><span data-stu-id="5fcdf-280">31</span></span></td>
<td><span data-ttu-id="5fcdf-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span><span class="sxs-lookup"><span data-stu-id="5fcdf-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="5fcdf-282">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-283">オンボード中に Windows テレメトリ サービスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="5fcdf-284">オフボードプロセスは続行されます。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="5fcdf-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Windows テレメトリ サービスのエラーを確認します</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-286">32</span><span class="sxs-lookup"><span data-stu-id="5fcdf-286">32</span></span></td>
<td><span data-ttu-id="5fcdf-287">Microsoft Defender for Endpoint service は、オフボード プロセスの後に自身を停止する要求に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="5fcdf-288">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="5fcdf-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="5fcdf-289">オフボード中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="5fcdf-290">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-291">33</span><span class="sxs-lookup"><span data-stu-id="5fcdf-291">33</span></span></td>
<td><span data-ttu-id="5fcdf-292">エンドポイント サービスの Microsoft Defender は、SENSE GUID の永続化に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="5fcdf-293">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-294">一意の識別子を使用して、ポータルに報告する各デバイスを表します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="5fcdf-295">識別子が保持されない場合、同じデバイスがポータルに 2 回表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-295">If the identifier does not persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="5fcdf-296">サービスがレジストリを更新できるデバイスのレジストリのアクセス許可を確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-297">34</span><span class="sxs-lookup"><span data-stu-id="5fcdf-297">34</span></span></td>
<td><span data-ttu-id="5fcdf-298">Microsoft Defender for Endpoint Service は、接続されたユーザー エクスペリエンスとテレメトリ サービスへの依存関係として自分自身を追加できなかったので、オンボーディング プロセスが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="5fcdf-299">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-300">Windows テレメトリ サービスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="5fcdf-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">診断データ サービスが有効になっているか確認します</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="5fcdf-302">オンボーディング設定とスクリプトが適切に展開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="5fcdf-303">構成パッケージを再展開してみてください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="5fcdf-304">「 <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">オンボード Windows 10 デバイス」を参照してください</a>。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-305">35</span><span class="sxs-lookup"><span data-stu-id="5fcdf-305">35</span></span></td>
<td><span data-ttu-id="5fcdf-306">Microsoft Defender for Endpoint Service は、接続されたユーザー エクスペリエンスとテレメトリ サービスへの依存関係として削除に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="5fcdf-307">エラー コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-308">オフボード中に Windows テレメトリ サービスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="5fcdf-309">オフボードプロセスは続行されます。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="5fcdf-310">Windows 診断データ サービスのエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-311">36</span><span class="sxs-lookup"><span data-stu-id="5fcdf-311">36</span></span></td>
<td><span data-ttu-id="5fcdf-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span><span class="sxs-lookup"><span data-stu-id="5fcdf-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="5fcdf-313">完了コード: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="5fcdf-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="5fcdf-314">Defender for Endpoint の接続ユーザー エクスペリエンスとテレメトリ サービスへの登録が正常に完了しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="5fcdf-315">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-316">37</span><span class="sxs-lookup"><span data-stu-id="5fcdf-316">37</span></span></td>
<td><span data-ttu-id="5fcdf-317">Microsoft Defender for Endpoint A モジュールは、クォータを超えかねない状態です。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="5fcdf-318">モジュール: %1、クォータ: {%2} {%3}、クォータ使用率の割合: %4。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="5fcdf-319">デバイスは、現在の 24 時間ウィンドウの割り当てられたクォータをほとんど使用しています。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="5fcdf-320">調整が必要です。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="5fcdf-321">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-322">38</span><span class="sxs-lookup"><span data-stu-id="5fcdf-322">38</span></span></td>
<td><span data-ttu-id="5fcdf-323">ネットワーク接続は低として識別されます。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-323">Network connection is identified as low.</span></span> <span data-ttu-id="5fcdf-324">Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="5fcdf-325">メーター接続: %2、インターネット利用可:%3、利用可能な無料ネットワーク:%4。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="5fcdf-326">デバイスは、測定済み/有料ネットワークを使用し、サーバーへの接続頻度が低い。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="5fcdf-327">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-328">39</span><span class="sxs-lookup"><span data-stu-id="5fcdf-328">39</span></span></td>
<td><span data-ttu-id="5fcdf-329">ネットワーク接続は通常と識別されます。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-329">Network connection is identified as normal.</span></span> <span data-ttu-id="5fcdf-330">Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="5fcdf-331">メーター接続: %2、インターネット利用可:%3、利用可能な無料ネットワーク:%4。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="5fcdf-332">デバイスは、メーター接続または有料接続を使用していないので、通常どおりサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-332">The device is not using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="5fcdf-333">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-334">40</span><span class="sxs-lookup"><span data-stu-id="5fcdf-334">40</span></span></td>
<td><span data-ttu-id="5fcdf-335">バッテリーの状態は低と識別されます。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-335">Battery state is identified as low.</span></span> <span data-ttu-id="5fcdf-336">Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="5fcdf-337">バッテリーの状態: %2。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="5fcdf-338">デバイスのバッテリー 残量が少なく、サーバーに接続する頻度が低い。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="5fcdf-339">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-340">41</span><span class="sxs-lookup"><span data-stu-id="5fcdf-340">41</span></span></td>
<td><span data-ttu-id="5fcdf-341">バッテリーの状態は、通常の状態として識別されます。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-341">Battery state is identified as normal.</span></span> <span data-ttu-id="5fcdf-342">Microsoft Defender for Endpoint は、%1 分ごとにサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="5fcdf-343">バッテリーの状態: %2。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="5fcdf-344">デバイスのバッテリー 残量が少なめで、通常どおりサーバーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="5fcdf-345">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-346">42</span><span class="sxs-lookup"><span data-stu-id="5fcdf-346">42</span></span></td>
<td><span data-ttu-id="5fcdf-347">Microsoft Defender for Endpoint WDATP コンポーネントは、アクションの実行に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-347">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="5fcdf-348">コンポーネント: %1、Action: %2、例外の種類: %3、例外メッセージ: %4</span><span class="sxs-lookup"><span data-stu-id="5fcdf-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="5fcdf-349">内部エラー。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-349">Internal error.</span></span> <span data-ttu-id="5fcdf-350">サービスの開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="5fcdf-351">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-352">43</span><span class="sxs-lookup"><span data-stu-id="5fcdf-352">43</span></span></td>
<td><span data-ttu-id="5fcdf-353">Microsoft Defender for Endpoint WDATP コンポーネントは、アクションの実行に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-353">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="5fcdf-354">コンポーネント: %1、Action: %2、例外の種類: %3、例外エラー: %4、例外メッセージ: %5</span><span class="sxs-lookup"><span data-stu-id="5fcdf-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="5fcdf-355">内部エラー。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-355">Internal error.</span></span> <span data-ttu-id="5fcdf-356">サービスの開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="5fcdf-357">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-358">44</span><span class="sxs-lookup"><span data-stu-id="5fcdf-358">44</span></span></td>
<td><span data-ttu-id="5fcdf-359">Defender for Endpoint サービスのオフボーディングが完了しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="5fcdf-360">サービスはオフボードされました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="5fcdf-361">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-362">45</span><span class="sxs-lookup"><span data-stu-id="5fcdf-362">45</span></span></td>
<td><span data-ttu-id="5fcdf-363">イベント トレース セッション [%1] の登録と開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="5fcdf-364">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="5fcdf-364">Error code: %2</span></span></td>
<td><span data-ttu-id="5fcdf-365">ETW セッションの作成時にサービスの起動時にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="5fcdf-366">これにより、サービスの起動エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="5fcdf-367">このエラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-368">46</span><span class="sxs-lookup"><span data-stu-id="5fcdf-368">46</span></span></td>
<td><span data-ttu-id="5fcdf-369">リソース不足のため、イベント トレース セッション [%1] の登録と開始に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="5fcdf-370">エラー コード: %2。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-370">Error code: %2.</span></span> <span data-ttu-id="5fcdf-371">これは、アクティブなイベント トレース セッションが多すぎるためです。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="5fcdf-372">サービスは 1 分で再試行します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="5fcdf-373">リソース不足のため、ETW セッションの作成中にサービスの起動時にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="5fcdf-374">サービスは開始され、実行中ですが、ETW セッションが開始されるまでセンサー イベントは報告できません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-374">The service started and is running, but will not report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="5fcdf-375">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="5fcdf-376">サービスは、1 分ごとにセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-377">47</span><span class="sxs-lookup"><span data-stu-id="5fcdf-377">47</span></span></td>
<td><span data-ttu-id="5fcdf-378">イベント トレース セッションが正常に登録され、開始されました 。 以前に失敗した試行後に回復されました。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="5fcdf-379">このイベントは、ETW セッションを正常に開始した後、前のイベントに従います。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="5fcdf-380">通常の動作通知。アクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5fcdf-381">48</span><span class="sxs-lookup"><span data-stu-id="5fcdf-381">48</span></span></td>
<td><span data-ttu-id="5fcdf-382">イベント トレース セッション [%2] にプロバイダー [%1] を追加できなかった。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="5fcdf-383">エラー コード: %3。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-383">Error code: %3.</span></span> <span data-ttu-id="5fcdf-384">つまり、このプロバイダーからのイベントは報告されません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="5fcdf-385">ETW セッションにプロバイダーを追加できなかった。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="5fcdf-386">その結果、プロバイダー イベントは報告されません。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="5fcdf-387">エラー コードを確認します。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-387">Check the error code.</span></span> <span data-ttu-id="5fcdf-388">エラーが解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
</tbody>
</table>

><span data-ttu-id="5fcdf-389">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="5fcdf-389">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5fcdf-390">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="5fcdf-390">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="5fcdf-391">関連項目</span><span class="sxs-lookup"><span data-stu-id="5fcdf-391">Related topics</span></span>
- [<span data-ttu-id="5fcdf-392">オンボード Windows 10 デバイス</span><span class="sxs-lookup"><span data-stu-id="5fcdf-392">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="5fcdf-393">デバイス プロキシとインターネット接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="5fcdf-393">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="5fcdf-394">エンドポイントの Microsoft Defender のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5fcdf-394">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
