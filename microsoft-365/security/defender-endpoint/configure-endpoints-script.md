---
title: ローカル スクリプトを使用した Windows 10 デバイスのオンボード
description: ローカル スクリプトを使用してデバイスに構成パッケージを展開し、サービスにオンボードします。
keywords: ローカル スクリプトを使用してデバイスを構成し、デバイス管理を行い、Microsoft Defender for Endpoint デバイスを構成する
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
ms.technology: mde
ms.openlocfilehash: 2510fb1a187bbe136669e11bc73103438b51d811
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842172"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="015a6-104">ローカル スクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="015a6-104">Onboard Windows 10 devices using a local script</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

- [<span data-ttu-id="015a6-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="015a6-105">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="015a6-106">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="015a6-106">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="015a6-107">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="015a6-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="015a6-108">また、個々のデバイスを Defender for Endpoint に手動でオンボードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="015a6-108">You can also manually onboard individual devices to Defender for Endpoint.</span></span> <span data-ttu-id="015a6-109">ネットワーク内のすべてのデバイスのオンボーディングにコミットする前に、サービスをテストするときに最初にこれを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="015a6-109">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="015a6-110">このスクリプトは、最大 10 台のデバイスで使用するために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="015a6-110">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="015a6-111">大規模に展開するには、他の [展開オプションを使用します](configure-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="015a6-111">To deploy at scale, use [other deployment options](configure-endpoints.md).</span></span> <span data-ttu-id="015a6-112">たとえば、オンボーディング スクリプトを 10 台以上のデバイスに展開し、グループ ポリシーを使用してオンボード Windows 10 デバイスで使用[できます](configure-endpoints-gp.md)。</span><span class="sxs-lookup"><span data-stu-id="015a6-112">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="015a6-113">デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="015a6-113">Onboard devices</span></span> 

<span data-ttu-id="015a6-114">[![さまざまな展開パスを示す PDF のイメージ](images/onboard-script.png)](images/onboard-script.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="015a6-114">[![Image of the PDF showing the various deployment paths](images/onboard-script.png)](images/onboard-script.png#lightbox)</span></span>


<span data-ttu-id="015a6-115">[[](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)エンドポイント用 Defender [Visio展開](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx)] のさまざまなパスを確認するには、PDF またはドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="015a6-115">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 


1.  <span data-ttu-id="015a6-116">サービス オンボーディング ウィザードから.zipした gp 構成 *パッケージ*(WindowsDefenderATPOnboardingPackage.zip) を開きます。</span><span class="sxs-lookup"><span data-stu-id="015a6-116">Open the GP configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="015a6-117">パッケージは次の方法で取得[Microsoft Defender セキュリティ センター。](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="015a6-117">You can also get the package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="015a6-118">ナビゲーション ウィンドウで、[オンボーディング]**設定**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="015a6-118">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

    1. <span data-ttu-id="015a6-119">オペレーティング システムWindows 10を選択します。</span><span class="sxs-lookup"><span data-stu-id="015a6-119">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="015a6-120">[展開方法 **] フィールドで** 、[ローカル スクリプト] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="015a6-120">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="015a6-121">[パッケージ **のダウンロード] を** クリックし、.zip保存します。</span><span class="sxs-lookup"><span data-stu-id="015a6-121">Click **Download package** and save the .zip file.</span></span>

  
2.  <span data-ttu-id="015a6-122">構成パッケージの内容を、オンボードするデバイスの場所 (デスクトップなど) に展開します。</span><span class="sxs-lookup"><span data-stu-id="015a6-122">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="015a6-123">*WindowsDefenderATPLocalOnboardingScript.cmd という名前のファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="015a6-123">You should have a file named *WindowsDefenderATPLocalOnboardingScript.cmd*.</span></span>

3.  <span data-ttu-id="015a6-124">デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="015a6-124">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="015a6-125">**[スタート]** をクリックし、「**cmd**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="015a6-125">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="015a6-126">**[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="015a6-126">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![[ウィンドウのスタート] メニューの [管理者として実行] をポイントする](images/run-as-admin.png)

4.  <span data-ttu-id="015a6-128">スクリプト ファイルの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="015a6-128">Type the location of the script file.</span></span> <span data-ttu-id="015a6-129">ファイルをデスクトップにコピーした場合は *、「%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd」と入力します。*</span><span class="sxs-lookup"><span data-stu-id="015a6-129">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPLocalOnboardingScript.cmd*</span></span>

5.  <span data-ttu-id="015a6-130">Enter キーを **押** するか **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="015a6-130">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="015a6-131">デバイスが準拠し、センサー データが正しく報告されていることを手動で検証する方法については、「Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング」 [を参照してください](troubleshoot-onboarding.md)。</span><span class="sxs-lookup"><span data-stu-id="015a6-131">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender for Endpoint onboarding issues](troubleshoot-onboarding.md).</span></span>


>[!TIP]
> <span data-ttu-id="015a6-132">デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="015a6-132">After onboarding the device, you can choose to run a detection test to verify that an device is properly onboarded to the service.</span></span> <span data-ttu-id="015a6-133">詳細については、「新しくオンボードされた Microsoft Defender for Endpoint エンドポイントで検出テストを実行する [」を参照してください](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="015a6-133">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-sample-collection-settings"></a><span data-ttu-id="015a6-134">サンプル コレクション設定の構成</span><span class="sxs-lookup"><span data-stu-id="015a6-134">Configure sample collection settings</span></span>
<span data-ttu-id="015a6-135">デバイスごとに構成値を設定して、Microsoft Defender セキュリティ センター から詳細分析用にファイルを送信する要求が行われたときに、デバイスからサンプルを収集できるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="015a6-135">For each device, you can set a configuration value to state whether samples can be collected from the device when a request is made through Microsoft Defender Security Center to submit a file for deep analysis.</span></span>

<span data-ttu-id="015a6-136">regedit を使用するか *、.reg* ファイルを作成して実行することで、デバイスのサンプル共有設定 *を手動で構成* できます。</span><span class="sxs-lookup"><span data-stu-id="015a6-136">You can manually configure the sample sharing setting on the device by using *regedit* or creating and running a *.reg* file.</span></span>  

<span data-ttu-id="015a6-137">構成は、次のレジストリ キー エントリを使用して設定されます。</span><span class="sxs-lookup"><span data-stu-id="015a6-137">The configuration is set through the following registry key entry:</span></span>

```console
Path: “HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection”
Name: "AllowSampleCollection"
Value: 0 or 1
```
<span data-ttu-id="015a6-138">ここで、</span><span class="sxs-lookup"><span data-stu-id="015a6-138">Where:</span></span><br>
<span data-ttu-id="015a6-139">名前の種類は D-WORD です。</span><span class="sxs-lookup"><span data-stu-id="015a6-139">Name type is a D-WORD.</span></span> <br>
<span data-ttu-id="015a6-140">使用可能な値は次のいずれかです。</span><span class="sxs-lookup"><span data-stu-id="015a6-140">Possible values are:</span></span>
- <span data-ttu-id="015a6-141">0 - このデバイスからのサンプル共有を許可しない</span><span class="sxs-lookup"><span data-stu-id="015a6-141">0 - doesn't allow sample sharing  from this device</span></span>
- <span data-ttu-id="015a6-142">1 - このデバイスからすべての種類のファイルを共有できます</span><span class="sxs-lookup"><span data-stu-id="015a6-142">1 - allows sharing of all file types from this device</span></span>

<span data-ttu-id="015a6-143">レジストリ キーが存在しない場合の既定値は 1 です。</span><span class="sxs-lookup"><span data-stu-id="015a6-143">The default value in case the registry key doesn’t exist is 1.</span></span>


## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="015a6-144">ローカル スクリプトを使用してデバイスをオフボードする</span><span class="sxs-lookup"><span data-stu-id="015a6-144">Offboard devices using a local script</span></span>
<span data-ttu-id="015a6-145">セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="015a6-145">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="015a6-146">デバイスに送信された期限切れのオフボード パッケージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="015a6-146">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="015a6-147">オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="015a6-147">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="015a6-148">オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="015a6-148">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="015a6-149">次の方法でオフボード[パッケージを取得Microsoft Defender セキュリティ センター。](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="015a6-149">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

    1. <span data-ttu-id="015a6-150">ナビゲーション ウィンドウで、[オフボーディング]**設定**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="015a6-150">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

    1. <span data-ttu-id="015a6-151">オペレーティング システムWindows 10を選択します。</span><span class="sxs-lookup"><span data-stu-id="015a6-151">Select Windows 10 as the operating system.</span></span>

    1. <span data-ttu-id="015a6-152">[展開方法 **] フィールドで** 、[ローカル スクリプト] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="015a6-152">In the **Deployment method** field, select **Local Script**.</span></span>

    1. <span data-ttu-id="015a6-153">[パッケージ **のダウンロード] を** クリックし、.zip保存します。</span><span class="sxs-lookup"><span data-stu-id="015a6-153">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="015a6-154">デバイスがアクセスできる共有.zipファイルの内容を読み取り専用の場所に抽出します。</span><span class="sxs-lookup"><span data-stu-id="015a6-154">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="015a6-155">*-MM-DD.cmd WindowsDefenderATPOffboardingScript_valid_until_YYYYという名前のファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="015a6-155">You should have a file named *WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

3.  <span data-ttu-id="015a6-156">デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="015a6-156">Open an elevated command-line prompt on the device and run the script:</span></span>

    1.  <span data-ttu-id="015a6-157">**[スタート]** をクリックし、「**cmd**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="015a6-157">Go to **Start** and type **cmd**.</span></span>

    1.  <span data-ttu-id="015a6-158">**[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="015a6-158">Right-click **Command prompt** and select **Run as administrator**.</span></span>

        ![[ウィンドウのスタート] メニューの [管理者として実行] をポイントする](images/run-as-admin.png)

4.  <span data-ttu-id="015a6-160">スクリプト ファイルの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="015a6-160">Type the location of the script file.</span></span> <span data-ttu-id="015a6-161">ファイルをデスクトップにコピーした場合は *、「%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd」と入力します。*</span><span class="sxs-lookup"><span data-stu-id="015a6-161">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

5.  <span data-ttu-id="015a6-162">Enter キーを **押** するか **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="015a6-162">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="015a6-163">Offboarding を使用すると、デバイスはポータルへのセンサー データの送信を停止しますが、デバイスからのデータ (通知への参照を含む) は最大 6 か月間保持されます。</span><span class="sxs-lookup"><span data-stu-id="015a6-163">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="015a6-164">デバイス構成の監視</span><span class="sxs-lookup"><span data-stu-id="015a6-164">Monitor device configuration</span></span>
<span data-ttu-id="015a6-165">「オンボードの問題のトラブルシューティング」の異[](troubleshoot-onboarding.md)なる検証手順に従って、スクリプトが正常に完了し、エージェントが実行されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="015a6-165">You can follow the different verification steps in the [Troubleshoot onboarding issues](troubleshoot-onboarding.md) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="015a6-166">監視は、ポータルまたはさまざまな展開ツールを使用して直接実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="015a6-166">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="015a6-167">ポータルを使用してデバイスを監視する</span><span class="sxs-lookup"><span data-stu-id="015a6-167">Monitor devices using the portal</span></span>
1. <span data-ttu-id="015a6-168">[次へ] Microsoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="015a6-168">Go to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="015a6-169">[デバイス **] リストをクリックします**。</span><span class="sxs-lookup"><span data-stu-id="015a6-169">Click **Devices list**.</span></span>

3. <span data-ttu-id="015a6-170">デバイスが表示されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="015a6-170">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="015a6-171">関連項目</span><span class="sxs-lookup"><span data-stu-id="015a6-171">Related topics</span></span>
- [<span data-ttu-id="015a6-172">グループ ポリシー Windows 10デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="015a6-172">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="015a6-173">デバイスをWindows 10デバイスをオンボードMicrosoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="015a6-173">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="015a6-174">モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="015a6-174">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="015a6-175">非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="015a6-175">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="015a6-176">新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="015a6-176">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="015a6-177">Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="015a6-177">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
