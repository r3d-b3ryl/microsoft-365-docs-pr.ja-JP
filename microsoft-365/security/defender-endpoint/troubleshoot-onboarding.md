---
title: Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング
description: デバイスのオンボーディング中または Microsoft Defender for Endpoint サービスで発生する可能性のある問題のトラブルシューティングを行います。
keywords: オンボーディング、オンボーディングの問題、イベント ビューアー、データ収集とプレビュー ビルド、センサー データ、診断のトラブルシューティング
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 4599741f501e9b55bc73e0eb8def9208bc988957
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689667"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-onboarding-issues"></a><span data-ttu-id="538d2-104">Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="538d2-104">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="538d2-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="538d2-105">**Applies to:**</span></span>

- [<span data-ttu-id="538d2-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="538d2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- <span data-ttu-id="538d2-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="538d2-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="538d2-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="538d2-108">Windows Server 2016</span></span>
- [<span data-ttu-id="538d2-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="538d2-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="538d2-110">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="538d2-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="538d2-111">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="538d2-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="538d2-112">問題が発生した場合は、Microsoft Defender for Endpoint オンボーディング プロセスのトラブルシューティングが必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-112">You might need to troubleshoot the Microsoft Defender for Endpoint onboarding process if you encounter issues.</span></span>
<span data-ttu-id="538d2-113">このページでは、展開ツールのいずれかを使用して展開するときに発生する可能性のあるオンボーディングの問題と、デバイスで発生する可能性のある一般的なエラーをトラブルシューティングするための詳細な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="538d2-113">This page provides detailed steps to troubleshoot onboarding issues that might occur when deploying with one of the deployment tools and common errors that might occur on the devices.</span></span>

## <a name="troubleshoot-issues-with-onboarding-tools"></a><span data-ttu-id="538d2-114">オンボーディング ツールに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="538d2-114">Troubleshoot issues with onboarding tools</span></span>

<span data-ttu-id="538d2-115">オンボーディング プロセスを完了し、1 時間後に [デバイス[](investigate-machines.md)] リストにデバイスが表示されない場合は、オンボーディングまたは接続の問題を示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-115">If you have completed the onboarding process and don't see devices in the [Devices list](investigate-machines.md) after an hour, it might indicate an onboarding or connectivity problem.</span></span>

### <a name="troubleshoot-onboarding-when-deploying-with-group-policy"></a><span data-ttu-id="538d2-116">グループ ポリシーを使用して展開する場合のオンボーディングのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="538d2-116">Troubleshoot onboarding when deploying with Group Policy</span></span>

<span data-ttu-id="538d2-117">グループ ポリシーによる展開は、デバイスでオンボーディング スクリプトを実行して行います。</span><span class="sxs-lookup"><span data-stu-id="538d2-117">Deployment with Group Policy is done by running the onboarding script on the devices.</span></span> <span data-ttu-id="538d2-118">グループ ポリシー コンソールは、展開が成功したかどうかを示しません。</span><span class="sxs-lookup"><span data-stu-id="538d2-118">The Group Policy console does not indicate if the deployment has succeeded or not.</span></span>

<span data-ttu-id="538d2-119">オンボーディング プロセスが完了し、1 時間後に [デバイス[](investigate-machines.md)] リストにデバイスが表示されない場合は、デバイス上のスクリプトの出力を確認できます。</span><span class="sxs-lookup"><span data-stu-id="538d2-119">If you have completed the onboarding process and don't see devices in the [Devices list](investigate-machines.md) after an hour, you can check the output of the script on the devices.</span></span> <span data-ttu-id="538d2-120">詳細については、「スクリプトを使用 [して展開する場合のオンボードのトラブルシューティング」を参照してください](#troubleshoot-onboarding-when-deploying-with-a-script)。</span><span class="sxs-lookup"><span data-stu-id="538d2-120">For more information, see [Troubleshoot onboarding when deploying with a script](#troubleshoot-onboarding-when-deploying-with-a-script).</span></span>

<span data-ttu-id="538d2-121">スクリプトが正常に完了した場合は、「[](#troubleshoot-onboarding-issues-on-the-device)デバイスのオンボードの問題のトラブルシューティング」を参照して、発生する可能性がある追加のエラーについて説明します。</span><span class="sxs-lookup"><span data-stu-id="538d2-121">If the script completes successfully, see [Troubleshoot onboarding issues on the devices](#troubleshoot-onboarding-issues-on-the-device) for additional errors that might occur.</span></span>

### <a name="troubleshoot-onboarding-issues-when-deploying-with-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="538d2-122">Microsoft Endpoint Configuration Manager を使用して展開する場合のオンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="538d2-122">Troubleshoot onboarding issues when deploying with Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="538d2-123">Configuration Manager の次のバージョンを使用してデバイスをオンボーディングする場合:</span><span class="sxs-lookup"><span data-stu-id="538d2-123">When onboarding devices using the following versions of Configuration Manager:</span></span>

- <span data-ttu-id="538d2-124">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="538d2-124">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="538d2-125">System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="538d2-125">System Center 2012 Configuration Manager</span></span>
- <span data-ttu-id="538d2-126">System Center 2012 R2 構成マネージャー</span><span class="sxs-lookup"><span data-stu-id="538d2-126">System Center 2012 R2 Configuration Manager</span></span>

<span data-ttu-id="538d2-127">上記のバージョンの Configuration Manager を使用した展開は、デバイスでオンボーディング スクリプトを実行して行います。</span><span class="sxs-lookup"><span data-stu-id="538d2-127">Deployment with the above-mentioned versions of Configuration Manager is done by running the onboarding script on the devices.</span></span> <span data-ttu-id="538d2-128">Configuration Manager コンソールで展開を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="538d2-128">You can track the deployment in the Configuration Manager Console.</span></span>

<span data-ttu-id="538d2-129">展開が失敗した場合は、デバイス上のスクリプトの出力を確認できます。</span><span class="sxs-lookup"><span data-stu-id="538d2-129">If the deployment fails, you can check the output of the script on the devices.</span></span>

<span data-ttu-id="538d2-130">オンボーディングが正常に完了したが、デバイスが 1 時間後に [デバイス] リスト[](#troubleshoot-onboarding-issues-on-the-device)に表示されない場合は、「発生する可能性がある追加のエラーについては、デバイスのオンボードの問題のトラブルシューティング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="538d2-130">If the onboarding completed successfully but the devices are not showing up in the **Devices list** after an hour, see [Troubleshoot onboarding issues on the device](#troubleshoot-onboarding-issues-on-the-device) for additional errors that might occur.</span></span>

### <a name="troubleshoot-onboarding-when-deploying-with-a-script"></a><span data-ttu-id="538d2-131">スクリプトを使用して展開する場合のオンボーディングのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="538d2-131">Troubleshoot onboarding when deploying with a script</span></span>

<span data-ttu-id="538d2-132">**デバイス上のスクリプトの結果を確認します。**</span><span class="sxs-lookup"><span data-stu-id="538d2-132">**Check the result of the script on the device:**</span></span>

1. <span data-ttu-id="538d2-133">[スタート **] ボタンを** クリックし、「 **イベント ビューアー」と入力** し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-133">Click **Start**, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="538d2-134">[Windows ログ **アプリケーション] に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-134">Go to **Windows Logs** > **Application**.</span></span>

3. <span data-ttu-id="538d2-135">**WDATPOnboarding イベント ソースからイベントを** 探します。</span><span class="sxs-lookup"><span data-stu-id="538d2-135">Look for an event from **WDATPOnboarding** event source.</span></span>

<span data-ttu-id="538d2-136">スクリプトが失敗し、イベントがエラーである場合は、次の表のイベント ID を確認して、問題のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="538d2-136">If the script fails and the event is an error, you can check the event ID in the following table to help you troubleshoot the issue.</span></span>

> [!NOTE]
> <span data-ttu-id="538d2-137">次のイベントの ID は、オンボーディング スクリプトにのみ固有のイベントです。</span><span class="sxs-lookup"><span data-stu-id="538d2-137">The following event IDs are specific to the onboarding script only.</span></span>

<span data-ttu-id="538d2-138">イベント ID</span><span class="sxs-lookup"><span data-stu-id="538d2-138">Event ID</span></span> | <span data-ttu-id="538d2-139">エラーの種類</span><span class="sxs-lookup"><span data-stu-id="538d2-139">Error Type</span></span> | <span data-ttu-id="538d2-140">解決手順</span><span class="sxs-lookup"><span data-stu-id="538d2-140">Resolution steps</span></span>
:---:|:---|:---
 `5` | <span data-ttu-id="538d2-141">オフボード データが見つかりましたが、削除できなかった</span><span class="sxs-lookup"><span data-stu-id="538d2-141">Offboarding data was found but couldn't be deleted</span></span> | <span data-ttu-id="538d2-142">レジストリのアクセス許可を確認する (具体的には)</span><span class="sxs-lookup"><span data-stu-id="538d2-142">Check the permissions on the registry, specifically</span></span><br> <span data-ttu-id="538d2-143">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span><span class="sxs-lookup"><span data-stu-id="538d2-143">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span></span>
`10` | <span data-ttu-id="538d2-144">オンボード データをレジストリに書き込めなかった</span><span class="sxs-lookup"><span data-stu-id="538d2-144">Onboarding data couldn't be written to registry</span></span> |  <span data-ttu-id="538d2-145">レジストリのアクセス許可を確認する (具体的には)</span><span class="sxs-lookup"><span data-stu-id="538d2-145">Check the permissions on the registry, specifically</span></span><br> <span data-ttu-id="538d2-146">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span><span class="sxs-lookup"><span data-stu-id="538d2-146">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span></span><br><span data-ttu-id="538d2-147">スクリプトが管理者として実行されたと確認します。</span><span class="sxs-lookup"><span data-stu-id="538d2-147">Verify that the script has been run as an administrator.</span></span>
`15` |  <span data-ttu-id="538d2-148">SENSE サービスの開始に失敗しました</span><span class="sxs-lookup"><span data-stu-id="538d2-148">Failed to start SENSE service</span></span> |<span data-ttu-id="538d2-149">サービスの正常性 (コマンド) を `sc query sense` 確認します。</span><span class="sxs-lookup"><span data-stu-id="538d2-149">Check the service health (`sc query sense` command).</span></span> <span data-ttu-id="538d2-150">中間の状態 *('Pending_Stopped'*、 *'Pending_Running'*) に含めず、(管理者権限を持つ) スクリプトを再度実行してください。</span><span class="sxs-lookup"><span data-stu-id="538d2-150">Make sure it's not in an intermediate state (*'Pending_Stopped'*, *'Pending_Running'*) and try to run the script again (with administrator rights).</span></span> <br> <br> <span data-ttu-id="538d2-151">デバイスが Windows 10 バージョン 1607 を実行し、コマンドを実行している場合は、デバイス `sc query sense` `START_PENDING` を再起動します。</span><span class="sxs-lookup"><span data-stu-id="538d2-151">If the device is running Windows 10, version 1607 and running the command `sc query sense` returns `START_PENDING`, reboot the device.</span></span> <span data-ttu-id="538d2-152">デバイスを再起動しても問題が解決しない場合は、KB4015217 にアップグレードして、もう一度オンボーディングを試してください。</span><span class="sxs-lookup"><span data-stu-id="538d2-152">If rebooting the device doesn't address the issue, upgrade to KB4015217 and try onboarding again.</span></span>
`15` | <span data-ttu-id="538d2-153">SENSE サービスの開始に失敗しました</span><span class="sxs-lookup"><span data-stu-id="538d2-153">Failed to start SENSE service</span></span> | <span data-ttu-id="538d2-154">エラーのメッセージが次の場合:システム エラー 577 またはエラー 1058 が発生した場合は、Microsoft Defender ウイルス対策 ELAM ドライバーを有効にする必要があります。手順については [、「Microsoft Defender Antivirus](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy) がポリシーによって無効にされない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="538d2-154">If the message of the error is: System error 577  or error 1058 has occurred, you need to enable the Microsoft Defender Antivirus ELAM driver, see [Ensure that Microsoft Defender Antivirus is not disabled by a policy](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy) for instructions.</span></span>
`30` |  <span data-ttu-id="538d2-155">スクリプトがサービスの実行を待機できなかった</span><span class="sxs-lookup"><span data-stu-id="538d2-155">The script failed to wait for the service to start running</span></span> | <span data-ttu-id="538d2-156">サービスの開始に時間がかかったか、開始しようとしている間にエラーが発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-156">The service could have taken more time to start or has encountered errors while trying to start.</span></span> <span data-ttu-id="538d2-157">SENSE に関連するイベントとエラーの詳細については、「イベント ビューアーを使用してイベント [とエラーを確認する」を参照してください](event-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="538d2-157">For more information on events and errors related to SENSE, see [Review events and errors using Event viewer](event-error-codes.md).</span></span>
`35` |  <span data-ttu-id="538d2-158">スクリプトが必要なオンボーディング状態レジストリ値を見つけ出すに失敗しました</span><span class="sxs-lookup"><span data-stu-id="538d2-158">The script failed to find needed onboarding status registry value</span></span> | <span data-ttu-id="538d2-159">SENSE サービスが初めて開始されると、オンボード状態がレジストリの場所に書き込み</span><span class="sxs-lookup"><span data-stu-id="538d2-159">When the SENSE service starts for the first time, it writes onboarding status to the registry location</span></span><br><span data-ttu-id="538d2-160">`HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status`.</span><span class="sxs-lookup"><span data-stu-id="538d2-160">`HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status`.</span></span><br> <span data-ttu-id="538d2-161">スクリプトは数秒後に検索に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="538d2-161">The script failed to find it after several seconds.</span></span> <span data-ttu-id="538d2-162">手動でテストし、それがそこにあるか確認できます。</span><span class="sxs-lookup"><span data-stu-id="538d2-162">You can manually test it and check if it's there.</span></span> <span data-ttu-id="538d2-163">SENSE に関連するイベントとエラーの詳細については、「イベント ビューアーを使用してイベント [とエラーを確認する」を参照してください](event-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="538d2-163">For more information on events and errors related to SENSE, see [Review events and errors using Event viewer](event-error-codes.md).</span></span>
`40` | <span data-ttu-id="538d2-164">SENSE サービスオンボーディングの状態が **1 に設定されていない**</span><span class="sxs-lookup"><span data-stu-id="538d2-164">SENSE service onboarding status is not set to **1**</span></span> | <span data-ttu-id="538d2-165">SENSE サービスが正しくオンボードに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="538d2-165">The SENSE service has failed to onboard properly.</span></span> <span data-ttu-id="538d2-166">SENSE に関連するイベントとエラーの詳細については、「イベント ビューアーを使用してイベント [とエラーを確認する」を参照してください](event-error-codes.md)。</span><span class="sxs-lookup"><span data-stu-id="538d2-166">For more information on events and errors related to SENSE, see [Review events and errors using Event viewer](event-error-codes.md).</span></span>
`65` | <span data-ttu-id="538d2-167">不十分な特権</span><span class="sxs-lookup"><span data-stu-id="538d2-167">Insufficient privileges</span></span>| <span data-ttu-id="538d2-168">管理者特権でスクリプトを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="538d2-168">Run the script again with administrator privileges.</span></span>

### <a name="troubleshoot-onboarding-issues-using-microsoft-intune"></a><span data-ttu-id="538d2-169">Microsoft Intune を使用したオンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="538d2-169">Troubleshoot onboarding issues using Microsoft Intune</span></span>

<span data-ttu-id="538d2-170">Microsoft Intune を使用してエラー コードを確認し、問題の原因のトラブルシューティングを試みできます。</span><span class="sxs-lookup"><span data-stu-id="538d2-170">You can use Microsoft Intune to check error codes and attempt to troubleshoot the cause of the issue.</span></span>

<span data-ttu-id="538d2-171">Intune でポリシーを構成し、デバイスに反映されない場合は、MDM の自動登録を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-171">If you have configured policies in Intune and they are not propagated on devices, you might need to configure automatic MDM enrollment.</span></span>

<span data-ttu-id="538d2-172">オンボーディング中に発生する可能性がある問題の原因を理解するには、次の表を使用します。</span><span class="sxs-lookup"><span data-stu-id="538d2-172">Use the following tables to understand the possible causes of issues while onboarding:</span></span>

- <span data-ttu-id="538d2-173">Microsoft Intune のエラー コードとOMA-URIs表</span><span class="sxs-lookup"><span data-stu-id="538d2-173">Microsoft Intune error codes and OMA-URIs table</span></span>
- <span data-ttu-id="538d2-174">コンプライアンス以外のテーブルに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="538d2-174">Known issues with non-compliance table</span></span>
- <span data-ttu-id="538d2-175">モバイル デバイス管理 (MDM) イベント ログ テーブル</span><span class="sxs-lookup"><span data-stu-id="538d2-175">Mobile Device Management (MDM) event logs table</span></span>

<span data-ttu-id="538d2-176">イベント ログとトラブルシューティング手順が機能しない場合は、ポータルの [デバイス管理] セクションからローカル スクリプトをダウンロードし、管理者特権でコマンド プロンプトで実行します。</span><span class="sxs-lookup"><span data-stu-id="538d2-176">If none of the event logs and troubleshooting steps work, download the Local script from the **Device management** section of the portal, and run it in an elevated command prompt.</span></span>

#### <a name="microsoft-intune-error-codes-and-oma-uris"></a><span data-ttu-id="538d2-177">Microsoft Intune のエラー コードとエラー OMA-URIs</span><span class="sxs-lookup"><span data-stu-id="538d2-177">Microsoft Intune error codes and OMA-URIs</span></span>

<span data-ttu-id="538d2-178">エラー コード 16 進数</span><span class="sxs-lookup"><span data-stu-id="538d2-178">Error Code Hex</span></span> | <span data-ttu-id="538d2-179">エラー コード 12 月</span><span class="sxs-lookup"><span data-stu-id="538d2-179">Error Code Dec</span></span> | <span data-ttu-id="538d2-180">エラーの説明</span><span class="sxs-lookup"><span data-stu-id="538d2-180">Error Description</span></span> | <span data-ttu-id="538d2-181">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="538d2-181">OMA-URI</span></span> | <span data-ttu-id="538d2-182">考えられる原因とトラブルシューティングの手順</span><span class="sxs-lookup"><span data-stu-id="538d2-182">Possible cause and troubleshooting steps</span></span>
:---:|:---|:---|:---|:---
<span data-ttu-id="538d2-183">0x87D1FDE8</span><span class="sxs-lookup"><span data-stu-id="538d2-183">0x87D1FDE8</span></span> | <span data-ttu-id="538d2-184">-2016281112</span><span class="sxs-lookup"><span data-stu-id="538d2-184">-2016281112</span></span> | <span data-ttu-id="538d2-185">修復に失敗しました</span><span class="sxs-lookup"><span data-stu-id="538d2-185">Remediation failed</span></span> | <span data-ttu-id="538d2-186">オンボード</span><span class="sxs-lookup"><span data-stu-id="538d2-186">Onboarding</span></span> <br> <span data-ttu-id="538d2-187">オフボード</span><span class="sxs-lookup"><span data-stu-id="538d2-187">Offboarding</span></span> | <span data-ttu-id="538d2-188">**考えられる原因:** 誤った BLOB でオンボーディングまたはオフボードが失敗しました。署名が間違っていたり、PreviousOrgIds フィールドが見つからない場合。</span><span class="sxs-lookup"><span data-stu-id="538d2-188">**Possible cause:** Onboarding or offboarding failed on a wrong blob: wrong signature or missing PreviousOrgIds fields.</span></span> <br><br> <span data-ttu-id="538d2-189">**トラブルシューティングの手順:**</span><span class="sxs-lookup"><span data-stu-id="538d2-189">**Troubleshooting steps:**</span></span> <br> <span data-ttu-id="538d2-190">[デバイス イベント ログのエージェントオンボーディング エラーの表示] セクション [でイベントの ID を確認](#view-agent-onboarding-errors-in-the-device-event-log) します。</span><span class="sxs-lookup"><span data-stu-id="538d2-190">Check the event IDs in the [View agent onboarding errors in the device event log](#view-agent-onboarding-errors-in-the-device-event-log) section.</span></span> <br><br> <span data-ttu-id="538d2-191">次の表の MDM イベント ログを確認するか [、「Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10)での MDM エラーの診断」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="538d2-191">Check the MDM event logs in the following table or follow the instructions in [Diagnose MDM failures in Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).</span></span>
 | | | | <span data-ttu-id="538d2-192">オンボード</span><span class="sxs-lookup"><span data-stu-id="538d2-192">Onboarding</span></span> <br> <span data-ttu-id="538d2-193">オフボード</span><span class="sxs-lookup"><span data-stu-id="538d2-193">Offboarding</span></span> <br> <span data-ttu-id="538d2-194">SampleSharing</span><span class="sxs-lookup"><span data-stu-id="538d2-194">SampleSharing</span></span> | <span data-ttu-id="538d2-195">**考えられる原因:** Microsoft Defender for Endpoint Policy レジストリ キーが存在しないか、OMA DM クライアントに書き込み権限が付与されていない。</span><span class="sxs-lookup"><span data-stu-id="538d2-195">**Possible cause:** Microsoft Defender for Endpoint Policy registry key does not exist or the OMA DM client doesn't have permissions to write to it.</span></span> <br><br> <span data-ttu-id="538d2-196">**トラブルシューティングの手順:** 次のレジストリ キーが存在することを確認します。 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="538d2-196">**Troubleshooting steps:** Ensure that the following registry key exists: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span> <br> <br> <span data-ttu-id="538d2-197">存在しない場合は、管理者特権でコマンドを開き、キーを追加します。</span><span class="sxs-lookup"><span data-stu-id="538d2-197">If it doesn't exist, open an elevated command and add the key.</span></span>
 | | | | <span data-ttu-id="538d2-198">SenseIsRunning</span><span class="sxs-lookup"><span data-stu-id="538d2-198">SenseIsRunning</span></span> <br> <span data-ttu-id="538d2-199">OnboardingState</span><span class="sxs-lookup"><span data-stu-id="538d2-199">OnboardingState</span></span> <br> <span data-ttu-id="538d2-200">OrgId</span><span class="sxs-lookup"><span data-stu-id="538d2-200">OrgId</span></span> |  <span data-ttu-id="538d2-201">**考えられる原因:** 読み取り専用プロパティによる修復の試行。</span><span class="sxs-lookup"><span data-stu-id="538d2-201">**Possible cause:** An attempt to remediate by read-only property.</span></span> <span data-ttu-id="538d2-202">オンボーディングに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="538d2-202">Onboarding has failed.</span></span> <br><br> <span data-ttu-id="538d2-203">**トラブルシューティングの手順:** 「デバイスでのオンボードの問題の [トラブルシューティング」のトラブルシューティング手順を確認します](#troubleshoot-onboarding-issues-on-the-device)。</span><span class="sxs-lookup"><span data-stu-id="538d2-203">**Troubleshooting steps:** Check the troubleshooting steps in [Troubleshoot onboarding issues on the device](#troubleshoot-onboarding-issues-on-the-device).</span></span> <br><br> <span data-ttu-id="538d2-204">次の表の MDM イベント ログを確認するか [、「Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10)での MDM エラーの診断」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="538d2-204">Check the MDM event logs in the following table or follow the instructions in [Diagnose MDM failures in Windows 10](https://docs.microsoft.com/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).</span></span>
 | | | | <span data-ttu-id="538d2-205">すべて</span><span class="sxs-lookup"><span data-stu-id="538d2-205">All</span></span> | <span data-ttu-id="538d2-206">**考えられる原因:** Microsoft Defender for Endpoint をサポートされていない SKU/プラットフォーム (特に Holographic SKU) に展開します。</span><span class="sxs-lookup"><span data-stu-id="538d2-206">**Possible cause:** Attempt to deploy Microsoft Defender for Endpoint on non-supported SKU/Platform, particularly Holographic SKU.</span></span> <br><br> <span data-ttu-id="538d2-207">現在サポートされているプラットフォーム:</span><span class="sxs-lookup"><span data-stu-id="538d2-207">Currently supported platforms:</span></span><br> <span data-ttu-id="538d2-208">エンタープライズ、教育、およびプロフェッショナル。</span><span class="sxs-lookup"><span data-stu-id="538d2-208">Enterprise, Education, and Professional.</span></span><br> <span data-ttu-id="538d2-209">サーバーはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="538d2-209">Server is not supported.</span></span>
 <span data-ttu-id="538d2-210">0x87D101A9</span><span class="sxs-lookup"><span data-stu-id="538d2-210">0x87D101A9</span></span> | <span data-ttu-id="538d2-211">-2016345687</span><span class="sxs-lookup"><span data-stu-id="538d2-211">-2016345687</span></span> |<span data-ttu-id="538d2-212">SyncML(425): 要求されたコマンドは、送信者が受信者に適切なアクセス制御アクセス許可 (ACL) を持たないので失敗しました。</span><span class="sxs-lookup"><span data-stu-id="538d2-212">SyncML(425): The requested command failed because the sender does not have adequate access control permissions (ACL) on the recipient.</span></span> | <span data-ttu-id="538d2-213">すべて</span><span class="sxs-lookup"><span data-stu-id="538d2-213">All</span></span> |  <span data-ttu-id="538d2-214">**考えられる原因:** Microsoft Defender for Endpoint をサポートされていない SKU/プラットフォーム (特に Holographic SKU) に展開します。</span><span class="sxs-lookup"><span data-stu-id="538d2-214">**Possible cause:** Attempt to deploy Microsoft Defender for Endpoint on non-supported SKU/Platform, particularly Holographic SKU.</span></span><br><br> <span data-ttu-id="538d2-215">現在サポートされているプラットフォーム:</span><span class="sxs-lookup"><span data-stu-id="538d2-215">Currently supported platforms:</span></span><br>  <span data-ttu-id="538d2-216">エンタープライズ、教育、およびプロフェッショナル。</span><span class="sxs-lookup"><span data-stu-id="538d2-216">Enterprise, Education, and Professional.</span></span>

#### <a name="known-issues-with-non-compliance"></a><span data-ttu-id="538d2-217">コンプライアンスに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="538d2-217">Known issues with non-compliance</span></span>

<span data-ttu-id="538d2-218">次の表に、コンプライアンス以外の問題に関する情報と、問題に対処する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="538d2-218">The following table provides information on issues with non-compliance and how you can address the issues.</span></span>

<span data-ttu-id="538d2-219">ケース</span><span class="sxs-lookup"><span data-stu-id="538d2-219">Case</span></span> | <span data-ttu-id="538d2-220">現象</span><span class="sxs-lookup"><span data-stu-id="538d2-220">Symptoms</span></span> | <span data-ttu-id="538d2-221">考えられる原因とトラブルシューティングの手順</span><span class="sxs-lookup"><span data-stu-id="538d2-221">Possible cause and troubleshooting steps</span></span>
:---:|:---|:---
 `1` | <span data-ttu-id="538d2-222">デバイスは SenseIsRunning OMA-URI に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="538d2-222">Device is compliant by SenseIsRunning OMA-URI.</span></span> <span data-ttu-id="538d2-223">ただし、OrgId、Onboarding、OnboardingState OMA-URI では非準拠です。</span><span class="sxs-lookup"><span data-stu-id="538d2-223">But is non-compliant by OrgId, Onboarding and OnboardingState OMA-URIs.</span></span> | <span data-ttu-id="538d2-224">**考えられる原因:** Windows のインストールまたはアップグレード後にユーザーが OOBE を渡したのを確認します。</span><span class="sxs-lookup"><span data-stu-id="538d2-224">**Possible cause:** Check that user passed OOBE after Windows installation or upgrade.</span></span> <span data-ttu-id="538d2-225">OOBE オンボーディングを完了できなかったが、SENSE が既に実行されている。</span><span class="sxs-lookup"><span data-stu-id="538d2-225">During OOBE onboarding couldn't be completed but SENSE is running already.</span></span><br><br> <span data-ttu-id="538d2-226">**トラブルシューティングの手順:** OOBE が完了するのを待ちます。</span><span class="sxs-lookup"><span data-stu-id="538d2-226">**Troubleshooting steps:** Wait for OOBE to complete.</span></span>
 `2` |  <span data-ttu-id="538d2-227">デバイスは OrgId、Onboarding、および OnboardingState OMA-URI に準拠していますが、SenseIsRunning OMA-URI では非準拠です。</span><span class="sxs-lookup"><span data-stu-id="538d2-227">Device is compliant by OrgId, Onboarding, and OnboardingState OMA-URIs, but is non-compliant by SenseIsRunning OMA-URI.</span></span> |  <span data-ttu-id="538d2-228">**考えられる原因:** センス サービスのスタートアップの種類は、"遅延開始" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="538d2-228">**Possible cause:** Sense service's startup type is set as "Delayed Start".</span></span> <span data-ttu-id="538d2-229">システムの起動時に DM セッションが発生すると、Microsoft Intune サーバーが SenseIsRunning によってデバイスを非準拠として報告することがあります。</span><span class="sxs-lookup"><span data-stu-id="538d2-229">Sometimes this causes the Microsoft Intune server to report the device as non-compliant by SenseIsRunning when DM session occurs on system start.</span></span> <br><br> <span data-ttu-id="538d2-230">**トラブルシューティングの手順:** この問題は、24 時間以内に自動的に修正されるはずです。</span><span class="sxs-lookup"><span data-stu-id="538d2-230">**Troubleshooting steps:** The issue should automatically be fixed within 24 hours.</span></span>
 `3` | <span data-ttu-id="538d2-231">デバイスが非準拠</span><span class="sxs-lookup"><span data-stu-id="538d2-231">Device is non-compliant</span></span> | <span data-ttu-id="538d2-232">**トラブルシューティングの手順:** オンボーディング ポリシーとオフボード ポリシーが同じデバイスに同時に展開されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="538d2-232">**Troubleshooting steps:** Ensure that Onboarding and Offboarding policies are not deployed on the same device at same time.</span></span>

#### <a name="mobile-device-management-mdm-event-logs"></a><span data-ttu-id="538d2-233">モバイル デバイス管理 (MDM) イベント ログ</span><span class="sxs-lookup"><span data-stu-id="538d2-233">Mobile Device Management (MDM) event logs</span></span>

<span data-ttu-id="538d2-234">MDM イベント ログを表示して、オンボーディング中に発生する可能性のある問題のトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="538d2-234">View the MDM event logs to troubleshoot issues that might arise during onboarding:</span></span>

<span data-ttu-id="538d2-235">ログ名: Microsoft\Windows\DeviceManagement-EnterpriseDiagnostics-Provider</span><span class="sxs-lookup"><span data-stu-id="538d2-235">Log name: Microsoft\Windows\DeviceManagement-EnterpriseDiagnostics-Provider</span></span>

<span data-ttu-id="538d2-236">チャネル名: 管理者</span><span class="sxs-lookup"><span data-stu-id="538d2-236">Channel name: Admin</span></span>

<span data-ttu-id="538d2-237">ID</span><span class="sxs-lookup"><span data-stu-id="538d2-237">ID</span></span> | <span data-ttu-id="538d2-238">重要度</span><span class="sxs-lookup"><span data-stu-id="538d2-238">Severity</span></span> | <span data-ttu-id="538d2-239">イベントの説明</span><span class="sxs-lookup"><span data-stu-id="538d2-239">Event description</span></span> | <span data-ttu-id="538d2-240">トラブルシューティングの手順</span><span class="sxs-lookup"><span data-stu-id="538d2-240">Troubleshooting steps</span></span>
:---|:---|:---|:---
<span data-ttu-id="538d2-241">1819</span><span class="sxs-lookup"><span data-stu-id="538d2-241">1819</span></span> | <span data-ttu-id="538d2-242">Error</span><span class="sxs-lookup"><span data-stu-id="538d2-242">Error</span></span> | <span data-ttu-id="538d2-243">エンドポイント CSP 用 Microsoft Defender: ノードの値の設定に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="538d2-243">Microsoft Defender for Endpoint CSP: Failed to Set Node's Value.</span></span> <span data-ttu-id="538d2-244">NodeId: (%1), TokenName: (%2), Result: (%3)。</span><span class="sxs-lookup"><span data-stu-id="538d2-244">NodeId: (%1), TokenName: (%2), Result: (%3).</span></span> | <span data-ttu-id="538d2-245">Windows [10、1607](https://go.microsoft.com/fwlink/?linkid=829760)の累積的な更新プログラムをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="538d2-245">Download the [Cumulative Update for Windows 10, 1607](https://go.microsoft.com/fwlink/?linkid=829760).</span></span>

## <a name="troubleshoot-onboarding-issues-on-the-device"></a><span data-ttu-id="538d2-246">デバイスでのオンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="538d2-246">Troubleshoot onboarding issues on the device</span></span>

<span data-ttu-id="538d2-247">使用する展開ツールがオンボーディング プロセスでエラーを示していないが、デバイスが 1 時間以内にデバイスリストに表示されない場合は、次の検証トピックを参照して、Microsoft Defender for Endpoint エージェントでエラーが発生したかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="538d2-247">If the deployment tools used does not indicate an error in the onboarding process, but devices are still not appearing in the devices list in an hour, go through the following verification topics to check if an error occurred with the Microsoft Defender for Endpoint agent.</span></span>

- [<span data-ttu-id="538d2-248">デバイス イベント ログでエージェントオンボーディング エラーを表示する</span><span class="sxs-lookup"><span data-stu-id="538d2-248">View agent onboarding errors in the device event log</span></span>](#view-agent-onboarding-errors-in-the-device-event-log)
- [<span data-ttu-id="538d2-249">診断データ サービスが有効になっているか確認する</span><span class="sxs-lookup"><span data-stu-id="538d2-249">Ensure the diagnostic data service is enabled</span></span>](#ensure-the-diagnostics-service-is-enabled)
- [<span data-ttu-id="538d2-250">サービスが開始に設定されているのを確認する</span><span class="sxs-lookup"><span data-stu-id="538d2-250">Ensure the service is set to start</span></span>](#ensure-the-service-is-set-to-start)
- [<span data-ttu-id="538d2-251">デバイスにインターネット接続が接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-251">Ensure the device has an Internet connection</span></span>](#ensure-the-device-has-an-internet-connection)
- [<span data-ttu-id="538d2-252">ポリシーによって Microsoft Defender ウイルス対策が無効にされていないか確認する</span><span class="sxs-lookup"><span data-stu-id="538d2-252">Ensure that Microsoft Defender Antivirus is not disabled by a policy</span></span>](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)

### <a name="view-agent-onboarding-errors-in-the-device-event-log"></a><span data-ttu-id="538d2-253">デバイス イベント ログでエージェントオンボーディング エラーを表示する</span><span class="sxs-lookup"><span data-stu-id="538d2-253">View agent onboarding errors in the device event log</span></span>

1. <span data-ttu-id="538d2-254">[スタート **] ボタンを** クリックし、「 **イベント ビューアー」と入力** し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-254">Click **Start**, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="538d2-255">[イベント **ビューアー (ローカル)] ウィンドウ** で、[**アプリケーション** とサービス ログ] Microsoft Windows SENSE  >    >  **を**  >  **展開します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-255">In the **Event Viewer (Local)** pane, expand **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="538d2-256">SENSE は、Microsoft Defender for Endpoint をサポートする動作センサーを参照するために使用される内部名です。</span><span class="sxs-lookup"><span data-stu-id="538d2-256">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="538d2-257">[操作 **] を** 選択してログを読み込む。</span><span class="sxs-lookup"><span data-stu-id="538d2-257">Select **Operational** to load the log.</span></span>

4. <span data-ttu-id="538d2-258">[操作] **ウィンドウで** 、[現在のログの **フィルター] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="538d2-258">In the **Action** pane, click **Filter Current log**.</span></span>

5. <span data-ttu-id="538d2-259">[フィルター **] タブの**[イベント レベル] **で、[重大**] 、[警告] **、および**[**エラー**] を選択し **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="538d2-259">On the **Filter** tab, under **Event level:** select **Critical**, **Warning**, and **Error**, and click **OK**.</span></span>

   ![イベント ビューアー ログ フィルターのイメージ](images/filter-log.png)

6. <span data-ttu-id="538d2-261">[操作] ウィンドウに問題を示すイベント **が表示** されます。</span><span class="sxs-lookup"><span data-stu-id="538d2-261">Events which can indicate issues will appear in the **Operational** pane.</span></span> <span data-ttu-id="538d2-262">次の表のソリューションに基づいて、トラブルシューティングを試みできます。</span><span class="sxs-lookup"><span data-stu-id="538d2-262">You can attempt to troubleshoot them based on the solutions in the following table:</span></span>

<span data-ttu-id="538d2-263">イベント ID</span><span class="sxs-lookup"><span data-stu-id="538d2-263">Event ID</span></span> | <span data-ttu-id="538d2-264">メッセージ</span><span class="sxs-lookup"><span data-stu-id="538d2-264">Message</span></span> | <span data-ttu-id="538d2-265">解決手順</span><span class="sxs-lookup"><span data-stu-id="538d2-265">Resolution steps</span></span>
:---:|:---|:---
 `5` | <span data-ttu-id="538d2-266">Microsoft Defender for Endpoint service が変数でサーバーに接続 _できなかった_</span><span class="sxs-lookup"><span data-stu-id="538d2-266">Microsoft Defender for Endpoint service failed to connect to the server at _variable_</span></span> | <span data-ttu-id="538d2-267">[デバイスにインターネット アクセス権が設定されている必要があります](#ensure-the-device-has-an-internet-connection)。</span><span class="sxs-lookup"><span data-stu-id="538d2-267">[Ensure the device has Internet access](#ensure-the-device-has-an-internet-connection).</span></span>
 `6` | <span data-ttu-id="538d2-268">Microsoft Defender for Endpoint Service はオンボードされていないので、オンボーディング パラメーターが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="538d2-268">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span> <span data-ttu-id="538d2-269">エラー コード: _変数_</span><span class="sxs-lookup"><span data-stu-id="538d2-269">Failure code: _variable_</span></span> | <span data-ttu-id="538d2-270">[オンボーディング スクリプトを再度実行します](configure-endpoints-script.md)。</span><span class="sxs-lookup"><span data-stu-id="538d2-270">[Run the onboarding script again](configure-endpoints-script.md).</span></span>
 `7` | <span data-ttu-id="538d2-271">Microsoft Defender for Endpoint service では、オンボーディング パラメーターの読み取りが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="538d2-271">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="538d2-272">エラー コード: _変数_</span><span class="sxs-lookup"><span data-stu-id="538d2-272">Failure code: _variable_</span></span> | <span data-ttu-id="538d2-273">[デバイスにインターネット アクセス権が設定されているのを](#ensure-the-device-has-an-internet-connection)確認し、オンボーディング プロセス全体を再度実行します。</span><span class="sxs-lookup"><span data-stu-id="538d2-273">[Ensure the device has Internet access](#ensure-the-device-has-an-internet-connection), then run the entire onboarding process again.</span></span>
 `9` | <span data-ttu-id="538d2-274">Microsoft Defender for Endpoint service は、開始の種類を変更できなかった。</span><span class="sxs-lookup"><span data-stu-id="538d2-274">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="538d2-275">エラー コード: 変数</span><span class="sxs-lookup"><span data-stu-id="538d2-275">Failure code: variable</span></span> | <span data-ttu-id="538d2-276">オンボーディング中にイベントが発生した場合は、再起動し、オンボーディング スクリプトの実行を再試みします。</span><span class="sxs-lookup"><span data-stu-id="538d2-276">If the event happened during onboarding, reboot and re-attempt running the onboarding script.</span></span> <span data-ttu-id="538d2-277">詳細については、「オンボード スクリプトを [再度実行する」を参照してください](configure-endpoints-script.md)。</span><span class="sxs-lookup"><span data-stu-id="538d2-277">For more information, see [Run the onboarding script again](configure-endpoints-script.md).</span></span> <br><br><span data-ttu-id="538d2-278">オフボード中にイベントが発生した場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="538d2-278">If the event happened during offboarding, contact support.</span></span>
`10` | <span data-ttu-id="538d2-279">Microsoft Defender for Endpoint Service は、オンボーディング情報を保持できなかった。</span><span class="sxs-lookup"><span data-stu-id="538d2-279">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="538d2-280">エラー コード: 変数</span><span class="sxs-lookup"><span data-stu-id="538d2-280">Failure code: variable</span></span> | <span data-ttu-id="538d2-281">オンボーディング中にイベントが発生した場合は、オンボーディング スクリプトの実行を再試みします。</span><span class="sxs-lookup"><span data-stu-id="538d2-281">If the event happened during onboarding, re-attempt running the onboarding script.</span></span> <span data-ttu-id="538d2-282">詳細については、「オンボード スクリプトを [再度実行する」を参照してください](configure-endpoints-script.md)。</span><span class="sxs-lookup"><span data-stu-id="538d2-282">For more information, see [Run the onboarding script again](configure-endpoints-script.md).</span></span> <br><br><span data-ttu-id="538d2-283">問題が解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="538d2-283">If the problem persists, contact support.</span></span>
`15` | <span data-ttu-id="538d2-284">Microsoft Defender for Endpoint では、URL 変数を使用してコマンド チャネルを開始 _できません。_</span><span class="sxs-lookup"><span data-stu-id="538d2-284">Microsoft Defender for Endpoint cannot start command channel with URL: _variable_</span></span> | <span data-ttu-id="538d2-285">[デバイスにインターネット アクセス権が設定されている必要があります](#ensure-the-device-has-an-internet-connection)。</span><span class="sxs-lookup"><span data-stu-id="538d2-285">[Ensure the device has Internet access](#ensure-the-device-has-an-internet-connection).</span></span>
`17` | <span data-ttu-id="538d2-286">Microsoft Defender for Endpoint service は、接続されたユーザー エクスペリエンスとテレメトリ サービスの場所を変更できなかった。</span><span class="sxs-lookup"><span data-stu-id="538d2-286">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="538d2-287">エラー コード: 変数</span><span class="sxs-lookup"><span data-stu-id="538d2-287">Failure code: variable</span></span> | <span data-ttu-id="538d2-288">[オンボーディング スクリプトを再度実行します](configure-endpoints-script.md)。</span><span class="sxs-lookup"><span data-stu-id="538d2-288">[Run the onboarding script again](configure-endpoints-script.md).</span></span> <span data-ttu-id="538d2-289">問題が解決しない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="538d2-289">If the problem persists, contact support.</span></span>
`25` | <span data-ttu-id="538d2-290">Microsoft Defender for Endpoint service は、レジストリの正常性状態をリセットできなかった。</span><span class="sxs-lookup"><span data-stu-id="538d2-290">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="538d2-291">エラー コード: _変数_</span><span class="sxs-lookup"><span data-stu-id="538d2-291">Failure code: _variable_</span></span> | <span data-ttu-id="538d2-292">サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="538d2-292">Contact support.</span></span>
`27` | <span data-ttu-id="538d2-293">Microsoft Defender for Endpoint モードを有効にWindows Defender。</span><span class="sxs-lookup"><span data-stu-id="538d2-293">Failed to enable Microsoft Defender for Endpoint mode in Windows Defender.</span></span> <span data-ttu-id="538d2-294">オンボーディング プロセスに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="538d2-294">Onboarding process failed.</span></span> <span data-ttu-id="538d2-295">エラー コード: 変数</span><span class="sxs-lookup"><span data-stu-id="538d2-295">Failure code: variable</span></span> | <span data-ttu-id="538d2-296">サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="538d2-296">Contact support.</span></span>
`29` | <span data-ttu-id="538d2-297">オフボード パラメーターの読み取りに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="538d2-297">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="538d2-298">エラーの種類: %1、エラー コード: %2、説明: %3</span><span class="sxs-lookup"><span data-stu-id="538d2-298">Error type: %1, Error code: %2, Description: %3</span></span> | <span data-ttu-id="538d2-299">デバイスにインターネット アクセス権が設定されているのを確認し、オフボード プロセス全体を再度実行します。</span><span class="sxs-lookup"><span data-stu-id="538d2-299">Ensure the device has Internet access, then run the entire offboarding process again.</span></span>
`30` | <span data-ttu-id="538d2-300">Microsoft Defender for Endpoint で $(build.sense.productDisplayName) モードを無効にしました。</span><span class="sxs-lookup"><span data-stu-id="538d2-300">Failed to disable $(build.sense.productDisplayName) mode in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="538d2-301">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="538d2-301">Failure code: %1</span></span> | <span data-ttu-id="538d2-302">サポートに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="538d2-302">Contact support.</span></span>
`32` | <span data-ttu-id="538d2-303">$(build.sense.productDisplayName) サービスは、オフボード プロセスの後に自分自身を停止する要求に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="538d2-303">$(build.sense.productDisplayName) service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="538d2-304">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="538d2-304">Failure code: %1</span></span> | <span data-ttu-id="538d2-305">サービスの開始の種類が手動で行い、デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="538d2-305">Verify that the service start type is manual and reboot the device.</span></span>
`55` | <span data-ttu-id="538d2-306">Secure ETW 自動ロガーの作成に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="538d2-306">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="538d2-307">エラー コード: %1</span><span class="sxs-lookup"><span data-stu-id="538d2-307">Failure code: %1</span></span> | <span data-ttu-id="538d2-308">デバイスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="538d2-308">Reboot the device.</span></span>
`63` | <span data-ttu-id="538d2-309">外部サービスの開始の種類を更新します。</span><span class="sxs-lookup"><span data-stu-id="538d2-309">Updating the start type of external service.</span></span> <span data-ttu-id="538d2-310">名前: %1、実際の開始の種類: %2、予期される開始の種類: %3、終了コード: %4</span><span class="sxs-lookup"><span data-stu-id="538d2-310">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span> | <span data-ttu-id="538d2-311">前述のサービスの開始の種類の変更の原因を特定します。</span><span class="sxs-lookup"><span data-stu-id="538d2-311">Identify what is causing changes in start type of mentioned service.</span></span> <span data-ttu-id="538d2-312">終了コードが 0 ではない場合は、開始の種類を手動で予期される開始の種類に修正します。</span><span class="sxs-lookup"><span data-stu-id="538d2-312">If the exit code is not 0, fix the start type manually to expected start type.</span></span>
`64` | <span data-ttu-id="538d2-313">停止した外部サービスの開始。</span><span class="sxs-lookup"><span data-stu-id="538d2-313">Starting stopped external service.</span></span> <span data-ttu-id="538d2-314">名前: %1、終了コード: %2</span><span class="sxs-lookup"><span data-stu-id="538d2-314">Name: %1, exit code: %2</span></span> | <span data-ttu-id="538d2-315">イベントが再表示され続ける場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="538d2-315">Contact support if the event keeps re-appearing.</span></span>
`68` | <span data-ttu-id="538d2-316">サービスの開始の種類が予期しない。</span><span class="sxs-lookup"><span data-stu-id="538d2-316">The start type of the service is unexpected.</span></span> <span data-ttu-id="538d2-317">サービス名: %1、実際の開始の種類: %2、予期される開始の種類: %3</span><span class="sxs-lookup"><span data-stu-id="538d2-317">Service name: %1, actual start type: %2, expected start type: %3</span></span> | <span data-ttu-id="538d2-318">開始の種類の変更の原因を特定します。</span><span class="sxs-lookup"><span data-stu-id="538d2-318">Identify what is causing changes in start type.</span></span> <span data-ttu-id="538d2-319">前述のサービス開始の種類を修正しました。</span><span class="sxs-lookup"><span data-stu-id="538d2-319">Fix mentioned service start type.</span></span>
`69` | <span data-ttu-id="538d2-320">サービスが停止します。</span><span class="sxs-lookup"><span data-stu-id="538d2-320">The service is stopped.</span></span> <span data-ttu-id="538d2-321">サービス名: %1</span><span class="sxs-lookup"><span data-stu-id="538d2-321">Service name: %1</span></span> | <span data-ttu-id="538d2-322">前述のサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="538d2-322">Start the mentioned service.</span></span> <span data-ttu-id="538d2-323">継続する場合はサポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="538d2-323">Contact support if persists.</span></span>

<br />

<span data-ttu-id="538d2-324">デバイスには、Microsoft Defender for Endpoint エージェントが適切に機能するために依存しているその他のコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="538d2-324">There are additional components on the device that the Microsoft Defender for Endpoint agent depends on to function properly.</span></span> <span data-ttu-id="538d2-325">Microsoft Defender for Endpoint エージェント イベント ログにオンボード関連のエラーがない場合は、次の手順に進み、追加のコンポーネントが正しく構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="538d2-325">If there are no onboarding related errors in the Microsoft Defender for Endpoint agent event log, proceed with the following steps to ensure that the additional components are configured correctly.</span></span>

<span id="ensure-the-diagnostics-service-is-enabled" />

### <a name="ensure-the-diagnostic-data-service-is-enabled"></a><span data-ttu-id="538d2-326">診断データ サービスが有効になっているか確認する</span><span class="sxs-lookup"><span data-stu-id="538d2-326">Ensure the diagnostic data service is enabled</span></span>

<span data-ttu-id="538d2-327">デバイスが正しく報告されていない場合は、Windows 10 診断データ サービスが自動的に開始するように設定され、デバイスで実行されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-327">If the devices aren't reporting correctly, you might need to check that the Windows 10 diagnostic data service is set to automatically start and is running on the device.</span></span> <span data-ttu-id="538d2-328">このサービスは、他のプログラムやユーザー構成の変更によって無効になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-328">The service might have been disabled by other programs or user configuration changes.</span></span>

<span data-ttu-id="538d2-329">まず、Windows の起動時にサービスが自動的に開始されるのを確認し、サービスが現在実行されている (実行されていない場合は開始する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-329">First, you should check that the service is set to start automatically when Windows starts, then you should check that the service is currently running (and start it if it isn't).</span></span>

### <a name="ensure-the-service-is-set-to-start"></a><span data-ttu-id="538d2-330">サービスが開始に設定されているのを確認する</span><span class="sxs-lookup"><span data-stu-id="538d2-330">Ensure the service is set to start</span></span>

<span data-ttu-id="538d2-331">**コマンド ラインを使用して、Windows 10 診断データ サービスのスタートアップの種類を確認します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-331">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="538d2-332">デバイスで管理者特権のコマンド ライン プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="538d2-332">Open an elevated command-line prompt on the device:</span></span>

   <span data-ttu-id="538d2-333">a.</span><span class="sxs-lookup"><span data-stu-id="538d2-333">a.</span></span> <span data-ttu-id="538d2-334">[スタート **] ボタンを** クリックし **、「cmd」** と入力し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-334">Click **Start**, type **cmd**, and press **Enter**.</span></span>

   <span data-ttu-id="538d2-335">b.</span><span class="sxs-lookup"><span data-stu-id="538d2-335">b.</span></span> <span data-ttu-id="538d2-336">**[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="538d2-336">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="538d2-337">次のコマンドを入力し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-337">Enter the following command, and press **Enter**:</span></span>

   ```text
   sc qc diagtrack
   ```

   <span data-ttu-id="538d2-338">サービスが有効になっている場合、結果は次のスクリーンショットのようになります。</span><span class="sxs-lookup"><span data-stu-id="538d2-338">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![diagtrack の sc クエリ コマンドの結果](images/windefatp-sc-qc-diagtrack.png)

   <span data-ttu-id="538d2-340">に設定されていない場合は、自動的に開始するサービス `START_TYPE` `AUTO_START` を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-340">If the `START_TYPE` is not set to `AUTO_START`, then you'll need to set the service to automatically start.</span></span>

<span data-ttu-id="538d2-341">**コマンド ラインを使用して、Windows 10 診断データ サービスを自動的に開始する設定を行います。**</span><span class="sxs-lookup"><span data-stu-id="538d2-341">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1. <span data-ttu-id="538d2-342">デバイスで管理者特権のコマンド ライン プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="538d2-342">Open an elevated command-line prompt on the device:</span></span>

   <span data-ttu-id="538d2-343">a.</span><span class="sxs-lookup"><span data-stu-id="538d2-343">a.</span></span> <span data-ttu-id="538d2-344">[スタート **] ボタンを** クリックし **、「cmd」** と入力し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-344">Click **Start**, type **cmd**, and press **Enter**.</span></span>

   <span data-ttu-id="538d2-345">b.</span><span class="sxs-lookup"><span data-stu-id="538d2-345">b.</span></span> <span data-ttu-id="538d2-346">**[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="538d2-346">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="538d2-347">次のコマンドを入力し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-347">Enter the following command, and press **Enter**:</span></span>

   ```text
   sc config diagtrack start=auto
   ```

3. <span data-ttu-id="538d2-348">成功メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="538d2-348">A success message is displayed.</span></span> <span data-ttu-id="538d2-349">次のコマンドを入力して変更を確認し、Enter キーを **押します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-349">Verify the change by entering the following command, and press **Enter**:</span></span>

   ```text
   sc qc diagtrack
   ```

4. <span data-ttu-id="538d2-350">サービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="538d2-350">Start the service.</span></span>

   <span data-ttu-id="538d2-351">a.</span><span class="sxs-lookup"><span data-stu-id="538d2-351">a.</span></span> <span data-ttu-id="538d2-352">コマンド プロンプトで、次のコマンドを入力し **、Enter** キーを押します。</span><span class="sxs-lookup"><span data-stu-id="538d2-352">In the command prompt, type the following command and press **Enter**:</span></span>

   ```text
   sc start diagtrack
   ```

### <a name="ensure-the-device-has-an-internet-connection"></a><span data-ttu-id="538d2-353">デバイスにインターネット接続が接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-353">Ensure the device has an Internet connection</span></span>

<span data-ttu-id="538d2-354">Window Defender ATP センサーでは、センサー データを報告し、Microsoft Defender for Endpoint サービスと通信するために Microsoft Windows HTTP (WinHTTP) が必要です。</span><span class="sxs-lookup"><span data-stu-id="538d2-354">The Window Defender ATP sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="538d2-355">WinHTTP は、インターネット閲覧プロキシ設定や他のユーザー コンテキスト アプリケーションとは独立しています。特定の環境で使用できるプロキシ サーバーを検出できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-355">WinHTTP is independent of the Internet browsing proxy settings and other user context applications and must be able to detect the proxy servers that are available in your particular environment.</span></span>

<span data-ttu-id="538d2-356">センサーがサービス接続を確立するには [、「Microsoft Defender for Endpoint](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls) Service URL へのクライアント接続を確認する」のトピックで説明されている手順に従います。</span><span class="sxs-lookup"><span data-stu-id="538d2-356">To ensure that sensor has service connectivity, follow the steps described in the [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls) topic.</span></span>

<span data-ttu-id="538d2-357">検証が失敗し、環境でプロキシを使用してインターネットに接続している場合は、「プロキシとインターネット接続の設定の構成」のトピックで説明されている手順 [に従](configure-proxy-internet.md) います。</span><span class="sxs-lookup"><span data-stu-id="538d2-357">If the verification fails and your environment is using a proxy to connect to the Internet, then follow the steps described in [Configure proxy and Internet connectivity settings](configure-proxy-internet.md) topic.</span></span>

### <a name="ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy"></a><span data-ttu-id="538d2-358">ポリシーによって Microsoft Defender ウイルス対策が無効にされていないか確認する</span><span class="sxs-lookup"><span data-stu-id="538d2-358">Ensure that Microsoft Defender Antivirus is not disabled by a policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="538d2-359">以下は、Microsoft Defender Antivirusの 2020 年 8 月 (バージョン 4.18.2007.8) 更新プログラムをまだ受け取っていないデバイスにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="538d2-359">The following only applies to devices that have **not** yet received the August 2020 (version 4.18.2007.8) update to Microsoft Defender Antivirus.</span></span>
>
> <span data-ttu-id="538d2-360">この更新プログラムは、システム ポリシーを介してクライアント デバイスで Microsoft Defender Antivirus をオフにできないことを保証します。</span><span class="sxs-lookup"><span data-stu-id="538d2-360">The update ensures that Microsoft Defender Antivirus cannot be turned off on client devices via system policy.</span></span>

<span data-ttu-id="538d2-361">**問題**: Microsoft Defender for Endpoint サービスは、オンボーディング後に開始されない。</span><span class="sxs-lookup"><span data-stu-id="538d2-361">**Problem**: The Microsoft Defender for Endpoint service does not start after onboarding.</span></span>

<span data-ttu-id="538d2-362">**現象**: オンボードは正常に完了しますが、サービスを開始しようとするときにエラー 577 またはエラー 1058 が表示されます。</span><span class="sxs-lookup"><span data-stu-id="538d2-362">**Symptom**: Onboarding successfully completes, but you see error 577 or error 1058 when trying to start the service.</span></span>

<span data-ttu-id="538d2-363">**解決策**: デバイスがサードパーティのマルウェア対策クライアントを実行している場合、Microsoft Defender for Endpoint エージェントでは、早期起動マルウェア対策 (ELAM) ドライバーを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-363">**Solution**: If your devices are running a third-party antimalware client, the Microsoft Defender for Endpoint agent needs the Early Launch Antimalware (ELAM) driver to be enabled.</span></span> <span data-ttu-id="538d2-364">システム ポリシーによってオフにされていない必要があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-364">You must ensure that it's not turned off by a system policy.</span></span>

- <span data-ttu-id="538d2-365">ポリシーの実装に使用するツールに応じて、次のポリシーがクリアWindows Defender必要があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-365">Depending on the tool that you use to implement policies, you'll need to verify that the following Windows Defender policies are cleared:</span></span>

  - <span data-ttu-id="538d2-366">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="538d2-366">DisableAntiSpyware</span></span>
  - <span data-ttu-id="538d2-367">DisableAntiVirus</span><span class="sxs-lookup"><span data-stu-id="538d2-367">DisableAntiVirus</span></span>

  <span data-ttu-id="538d2-368">たとえば、グループ ポリシーには、次の値などのエントリはありません。</span><span class="sxs-lookup"><span data-stu-id="538d2-368">For example, in Group Policy there should be no entries such as the following values:</span></span>

  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiSpyware"/></Key>`
  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiVirus"/></Key>`

> [!IMPORTANT]
> <span data-ttu-id="538d2-369">この設定は中止され、Microsoft Defender Antivirus の `disableAntiSpyware` 2020 年 8 月 (バージョン 4.18.2007.8) 更新時に、すべてのクライアント デバイスで無視されます。</span><span class="sxs-lookup"><span data-stu-id="538d2-369">The `disableAntiSpyware` setting is discontinued and will be ignored on all client devices, as of the August 2020 (version 4.18.2007.8) update to Microsoft Defender Antivirus.</span></span>

- <span data-ttu-id="538d2-370">ポリシーをクリアした後、オンボーディング手順を再度実行します。</span><span class="sxs-lookup"><span data-stu-id="538d2-370">After clearing the policy, run the onboarding steps again.</span></span>

- <span data-ttu-id="538d2-371">以前のレジストリ キーの値を確認して、レジストリ キーを開いてポリシーが無効になっているか確認することもできます `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` 。</span><span class="sxs-lookup"><span data-stu-id="538d2-371">You can also check the previous registry key values to verify that the policy is disabled, by opening the registry key `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.</span></span>

    ![Microsoft Defender ウイルス対策のレジストリ キーのイメージ](images/atp-disableantispyware-regkey.png)

   > [!NOTE]
   > <span data-ttu-id="538d2-373">さらに、既定の開始値wdfilter.syswdboot.sysの開始値が "0" に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-373">In addition, you must ensure that wdfilter.sys and wdboot.sys are set to their default start values of "0".</span></span>
   >
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdBoot"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdFilter"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`

## <a name="troubleshoot-onboarding-issues-on-a-server"></a><span data-ttu-id="538d2-374">サーバーでのオンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="538d2-374">Troubleshoot onboarding issues on a server</span></span>

<span data-ttu-id="538d2-375">サーバーのオンボード中に問題が発生した場合は、次の検証手順を実行して、考えられる問題に対処します。</span><span class="sxs-lookup"><span data-stu-id="538d2-375">If you encounter issues while onboarding a server, go through the following verification steps to address possible issues.</span></span>

- [<span data-ttu-id="538d2-376">Microsoft Monitoring Agent (MMA) がインストールされ、センサー データをサービスに報告するように構成されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="538d2-376">Ensure Microsoft Monitoring Agent (MMA) is installed and configured to report sensor data to the service</span></span>](configure-server-endpoints.md#server-mma)
- [<span data-ttu-id="538d2-377">サーバー プロキシとインターネット接続の設定が正しく構成されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="538d2-377">Ensure that the server proxy and Internet connectivity settings are configured properly</span></span>](configure-server-endpoints.md#server-proxy)

<span data-ttu-id="538d2-378">また、次の情報を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-378">You might also need to check the following:</span></span>

- <span data-ttu-id="538d2-379">タスク マネージャーの [プロセス] タブで Microsoft Defender for Endpoint Service が **実行されている\*\*\*\*のを確認します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-379">Check that there is a Microsoft Defender for Endpoint Service running in the **Processes** tab in **Task Manager**.</span></span> <span data-ttu-id="538d2-380">例:</span><span class="sxs-lookup"><span data-stu-id="538d2-380">For example:</span></span>

    ![Microsoft Defender for Endpoint Service が実行されているプロセス ビューのイメージ](images/atp-task-manager.png)

- <span data-ttu-id="538d2-382">イベント **ビューアー アプリケーション**  >  **とサービス ログ操作** マネージャー  >  **をチェックして**、エラーが発生した場合を確認します。</span><span class="sxs-lookup"><span data-stu-id="538d2-382">Check **Event Viewer** > **Applications and Services Logs** > **Operation Manager** to see if there are any errors.</span></span>

- <span data-ttu-id="538d2-383">[ **サービス]** で **、Microsoft 監視エージェントがサーバー** 上で実行されている場合に確認します。</span><span class="sxs-lookup"><span data-stu-id="538d2-383">In **Services**, check if the **Microsoft Monitoring Agent** is running on the server.</span></span> <span data-ttu-id="538d2-384">例えば、</span><span class="sxs-lookup"><span data-stu-id="538d2-384">For example,</span></span>

    ![サービスのイメージ](images/atp-services.png)

- <span data-ttu-id="538d2-386">**Microsoft Monitoring Agent** Azure Log Analytics (OMS) で、ワークスペースを確認し、状態が  >  実行されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="538d2-386">In **Microsoft Monitoring Agent** > **Azure Log Analytics (OMS)**, check the Workspaces and verify that the status is running.</span></span>

    ![Microsoft Monitoring Agent のプロパティのイメージ](images/atp-mma-properties.png)

- <span data-ttu-id="538d2-388">デバイスがポータルの [デバイス] リスト **に反映されているのを** 確認します。</span><span class="sxs-lookup"><span data-stu-id="538d2-388">Check to see that devices are reflected in the **Devices list** in the portal.</span></span>

## <a name="confirming-onboarding-of-newly-built-devices"></a><span data-ttu-id="538d2-389">新しく構築されたデバイスのオンボーディングの確認</span><span class="sxs-lookup"><span data-stu-id="538d2-389">Confirming onboarding of newly built devices</span></span>

<span data-ttu-id="538d2-390">新しく構築されたデバイスにオンボーディングが展開されているが、完了していない場合は、インスタンスが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="538d2-390">There may be instances when onboarding is deployed on a newly built device but not completed.</span></span>

<span data-ttu-id="538d2-391">以下の手順では、次のシナリオのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="538d2-391">The steps below provide guidance for the following scenario:</span></span>

- <span data-ttu-id="538d2-392">オンボード パッケージが新しく構築されたデバイスに展開される</span><span class="sxs-lookup"><span data-stu-id="538d2-392">Onboarding package is deployed to newly built devices</span></span>
- <span data-ttu-id="538d2-393">センサーが起動しないのは、アウトオブボックス エクスペリエンス (OOBE) または最初のユーザー ログオンが完了していないためです。</span><span class="sxs-lookup"><span data-stu-id="538d2-393">Sensor does not start because the Out-of-box experience (OOBE) or first user logon has not been completed</span></span>
- <span data-ttu-id="538d2-394">エンド ユーザーが最初のログオンを実行する前にデバイスがオフまたは再起動される</span><span class="sxs-lookup"><span data-stu-id="538d2-394">Device is turned off or restarted before the end user performs a first logon</span></span>
- <span data-ttu-id="538d2-395">このシナリオでは、オンボード パッケージが展開された場合でも、SENSE サービスは自動的に開始されません</span><span class="sxs-lookup"><span data-stu-id="538d2-395">In this scenario, the SENSE service will not start automatically even though onboarding package was deployed</span></span>

> [!NOTE]
> <span data-ttu-id="538d2-396">次の手順は、Microsoft Endpoint Configuration Manager を使用する場合にのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="538d2-396">The following steps are only relevant when using Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="538d2-397">Microsoft Endpoint Configuration Manager を使用したオンボーディングの詳細については [、「Microsoft Defender for Endpoint」を参照してください](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection)。</span><span class="sxs-lookup"><span data-stu-id="538d2-397">For more details about onboarding using Microsoft Endpoint Configuration Manager, see [Microsoft Defender for Endpoint](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection).</span></span>

1. <span data-ttu-id="538d2-398">Microsoft Endpoint Configuration Manager でアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="538d2-398">Create an application in Microsoft Endpoint Configuration Manager.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration1 のイメージ](images/mecm-1.png)

2. <span data-ttu-id="538d2-400">[アプリケーション **情報を手動で指定する] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-400">Select **Manually specify the application information**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration2 のイメージ](images/mecm-2.png)

3. <span data-ttu-id="538d2-402">アプリケーションに関する情報を指定し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-402">Specify information about the application, then select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration3 のイメージ](images/mecm-3.png)

4. <span data-ttu-id="538d2-404">ソフトウェア センターに関する情報を指定し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-404">Specify information about the software center, then select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration4 のイメージ](images/mecm-4.png)

5. <span data-ttu-id="538d2-406">[展開 **の種類] で、[** 追加] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-406">In **Deployment types** select **Add**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration5 のイメージ](images/mecm-5.png)

6. <span data-ttu-id="538d2-408">[展開 **の種類情報を手動で指定する] を選択し**、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-408">Select **Manually specify the deployment type information**, then select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration6 のイメージ](images/mecm-6.png)

7. <span data-ttu-id="538d2-410">展開の種類に関する情報を指定し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-410">Specify information about the deployment type, then select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration7 のイメージ](images/mecm-7.png)

8. <span data-ttu-id="538d2-412">[**コンテンツ インストール**  >  **プログラム] で、** 次のコマンドを指定します `net start sense` 。</span><span class="sxs-lookup"><span data-stu-id="538d2-412">In **Content** > **Installation program** specify the command: `net start sense`.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration8 のイメージ](images/mecm-8.png)

9. <span data-ttu-id="538d2-414">[ **検出方法] で**、[ **ルールを構成してこの** 展開の種類の存在を検出する] を選択し、[句の追加] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-414">In **Detection method**, select **Configure rules to detect the presence of this deployment type**, then select **Add Clause**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration9 のイメージ](images/mecm-9.png)

10. <span data-ttu-id="538d2-416">次の検出ルールの詳細を指定し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-416">Specify the following detection rule details, then select **OK**:</span></span>

    ![Microsoft Endpoint Configuration Manager configuration10 のイメージ](images/mecm-10.png)

11. <span data-ttu-id="538d2-418">[検出 **方法] で、[次** へ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-418">In **Detection method** select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration11 のイメージ](images/mecm-11.png)

12. <span data-ttu-id="538d2-420">[ **ユーザー エクスペリエンス] で**、次の情報を指定し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-420">In **User Experience**, specify the following information, then select **Next**:</span></span>

    ![Microsoft Endpoint Configuration Manager configuration12 のイメージ](images/mecm-12.png)

13. <span data-ttu-id="538d2-422">[要件 **] で、[** 次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-422">In **Requirements**, select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration13 のイメージ](images/mecm-13.png)

14. <span data-ttu-id="538d2-424">[ **依存関係] で、[** 次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-424">In **Dependencies**, select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration14 のイメージ](images/mecm-14.png)

15. <span data-ttu-id="538d2-426">[概要 **] で、[** 次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-426">In **Summary**, select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration15 のイメージ](images/mecm-15.png)

16. <span data-ttu-id="538d2-428">[ **完了] で**、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-428">In **Completion**, select **Close**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration16 のイメージ](images/mecm-16.png)

17. <span data-ttu-id="538d2-430">[展開 **の種類] で**、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-430">In **Deployment types**, select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration17 のイメージ](images/mecm-17.png)

18. <span data-ttu-id="538d2-432">[概要 **] で、[** 次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-432">In **Summary**, select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration18 のイメージ](images/mecm-18.png)

    <span data-ttu-id="538d2-434">次に、状態が表示されます ![ 。Microsoft Endpoint Configuration Manager configuration19 のイメージ](images/mecm-19.png)</span><span class="sxs-lookup"><span data-stu-id="538d2-434">The status is then displayed: ![Image of Microsoft Endpoint Configuration Manager configuration19](images/mecm-19.png)</span></span>

19. <span data-ttu-id="538d2-435">[ **完了] で**、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-435">In **Completion**, select **Close**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration20 のイメージ](images/mecm-20.png)

20. <span data-ttu-id="538d2-437">これで、アプリを右クリックして [展開] を選択して、アプリケーションを **展開できます**。</span><span class="sxs-lookup"><span data-stu-id="538d2-437">You can now deploy the application by right-clicking the app and selecting **Deploy**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration21 のイメージ](images/mecm-21.png)

21. <span data-ttu-id="538d2-439">[全般 **] で** 、[ **依存関係のコンテンツを自動的に配布する] と [参照]** を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-439">In **General** select **Automatically distribute content for dependencies** and **Browse**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration22 のイメージ](images/mecm-22.png)

22. <span data-ttu-id="538d2-441">[コンテンツ **] で [次** へ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-441">In **Content** select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration23 のイメージ](images/mecm-23.png)

23. <span data-ttu-id="538d2-443">[展開 **の設定] で**、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-443">In **Deployment settings**, select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration24 のイメージ](images/mecm-24.png)

24. <span data-ttu-id="538d2-445">[**スケジュール] で\*\*\*\*、利用可能な時間の後にできるだけ早く** 選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-445">In **Scheduling** select **As soon as possible after the available time**, then select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration25 のイメージ](images/mecm-25.png)

25. <span data-ttu-id="538d2-447">[ **ユーザー エクスペリエンス] で**、[期限内またはメンテナンス 期間中に変更をコミットする **] (** 再起動が必要) を選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-447">In **User experience**, select **Commit changes at deadline or during a maintenance window (requires restarts)**, then select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration26 のイメージ](images/mecm-26.png)

26. <span data-ttu-id="538d2-449">[アラート **] で [** 次へ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-449">In **Alerts** select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration27 のイメージ](images/mecm-27.png)

27. <span data-ttu-id="538d2-451">[概要 **] で、[** 次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-451">In **Summary**, select **Next**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration28 のイメージ](images/mecm-28.png)

    <span data-ttu-id="538d2-453">次に、状態が ![ 表示される Microsoft Endpoint Configuration Manager configuration29 のイメージ](images/mecm-29.png)</span><span class="sxs-lookup"><span data-stu-id="538d2-453">The status is then displayed ![Image of Microsoft Endpoint Configuration Manager configuration29](images/mecm-29.png)</span></span>

28. <span data-ttu-id="538d2-454">[ **完了] で**、[閉じる] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="538d2-454">In **Completion**, select **Close**.</span></span>

    ![Microsoft Endpoint Configuration Manager configuration30 のイメージ](images/mecm-30.png)


## <a name="related-topics"></a><span data-ttu-id="538d2-456">関連項目</span><span class="sxs-lookup"><span data-stu-id="538d2-456">Related topics</span></span>

- [<span data-ttu-id="538d2-457">Microsoft Defender for Endpoint のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="538d2-457">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-mdatp.md)
- [<span data-ttu-id="538d2-458">デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="538d2-458">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="538d2-459">デバイス プロキシとインターネット接続の設定を構成する</span><span class="sxs-lookup"><span data-stu-id="538d2-459">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
