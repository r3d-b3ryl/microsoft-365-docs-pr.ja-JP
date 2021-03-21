---
title: ローカル スクリプトを使用した Windows 10 デバイスのオンボード
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: ローカル スクリプトを使用してデバイスに構成パッケージを展開し、サービスにオンボードします。
ms.openlocfilehash: 69a8295b170f9186d14862a7247cac3fb4c4ef3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917973"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="03e84-103">ローカル スクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="03e84-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="03e84-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="03e84-104">**Applies to:**</span></span>

- [<span data-ttu-id="03e84-105">Microsoft 365 Endpoint データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="03e84-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="03e84-106">また、個々のデバイスを Microsoft 365 Endpoint データ損失防止に手動でオンボードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="03e84-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="03e84-107">ネットワーク内のすべてのデバイスのオンボーディングにコミットする前に、サービスをテストするときに最初にこれを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="03e84-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03e84-108">このスクリプトは、最大 10 台のデバイスで使用するために最適化されています。</span><span class="sxs-lookup"><span data-stu-id="03e84-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="03e84-109">大規模に展開するには、他の [展開オプションを使用します](dlp-configure-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="03e84-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="03e84-110">たとえば、グループ ポリシーを使用してオンボード Windows 10 デバイスで使用可能なスクリプトを使用して、オンボーディング スクリプトを実稼働 [環境の 10](dlp-configure-endpoints-gp.md)台以上のデバイスに展開できます。</span><span class="sxs-lookup"><span data-stu-id="03e84-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="03e84-111">オンボード デバイス</span><span class="sxs-lookup"><span data-stu-id="03e84-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="03e84-112">サービス オンボーディング ウィザードからダウンロードした GP *構成パッケージ*.zip ファイル (DeviceComplianceOnboardingPackage.zip) を開きます。</span><span class="sxs-lookup"><span data-stu-id="03e84-112">Open the GP configuration package .zip file (*DeviceComplianceOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="03e84-113">また、Microsoft コンプライアンス センターからパッケージ [を取得できます。](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="03e84-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="03e84-114">ナビゲーション ウィンドウで、[設定 **デバイスのオン** ボーディング  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="03e84-114">In the navigation pane, select **Settings** > **Device onboarding**.</span></span>

3. <span data-ttu-id="03e84-115">[展開方法 **] フィールドで** 、[ローカル スクリプト] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="03e84-115">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="03e84-116">[パッケージ **のダウンロード] を** クリックし、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="03e84-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="03e84-117">構成パッケージの内容を、オンボードするデバイスの場所 (デスクトップなど) に展開します。</span><span class="sxs-lookup"><span data-stu-id="03e84-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="03e84-118">*DeviceOnboardingScript.cmd という名前のファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="03e84-118">You should have a file named *DeviceOnboardingScript.cmd*.</span></span>

6.  <span data-ttu-id="03e84-119">デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="03e84-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="03e84-120">**[スタート]** をクリックし、「**cmd**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="03e84-120">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="03e84-121">**[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="03e84-121">Right-click **Command prompt** and select **Run as administrator**.</span></span>

![[ウィンドウのスタート] メニューの [管理者として実行] をポイントする](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="03e84-123">スクリプト ファイルの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="03e84-123">Type the location of the script file.</span></span> <span data-ttu-id="03e84-124">ファイルをデスクトップにコピーした場合は *、「%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd」と入力します。*</span><span class="sxs-lookup"><span data-stu-id="03e84-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="03e84-125">Enter キーを **押** するか **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="03e84-125">Press the **Enter** key or click **OK**.</span></span>

<span data-ttu-id="03e84-126">デバイスが準拠し、センサー データが正しく報告されていることを手動で検証する方法については [、「Microsoft Defender Advanced Threat Protection](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)オンボーディングの問題のトラブルシューティング」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03e84-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="03e84-127">ローカル スクリプトを使用してデバイスをオフボードする</span><span class="sxs-lookup"><span data-stu-id="03e84-127">Offboard devices using a local script</span></span>
<span data-ttu-id="03e84-128">セキュリティ上の理由から、Offboard デバイスに使用されるパッケージは、ダウンロード日から 30 日後に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="03e84-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="03e84-129">デバイスに送信された期限切れのオフボード パッケージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="03e84-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="03e84-130">オフボード パッケージをダウンロードすると、パッケージの有効期限が通知され、パッケージ名にも含まれます。</span><span class="sxs-lookup"><span data-stu-id="03e84-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="03e84-131">オンボーディングポリシーとオフボード ポリシーを同じデバイスに同時に展開し、それ以外の場合は予期しない競合を引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="03e84-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="03e84-132">Microsoft コンプライアンス センターからオフボード パッケージ [を取得する](https://compliance.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="03e84-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="03e84-133">ナビゲーション ウィンドウで、[設定デバイスの **オフ**  >  **ボード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="03e84-133">In the navigation pane, select **Settings** > **Device offboarding**.</span></span>

3. <span data-ttu-id="03e84-134">[展開方法 **] フィールドで** 、[ローカル スクリプト] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="03e84-134">In the **Deployment method** field, select **Local Script**.</span></span>

4. <span data-ttu-id="03e84-135">[パッケージ **のダウンロード] を** クリックし、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="03e84-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="03e84-136">.zip ファイルの内容を、デバイスがアクセスできる共有の読み取り専用の場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="03e84-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="03e84-137">*-MM-DD.cmd DeviceComplianceOffboardingScript_valid_until_YYYYという名前のファイルが必要です*。</span><span class="sxs-lookup"><span data-stu-id="03e84-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd*.</span></span>

6.  <span data-ttu-id="03e84-138">デバイスで管理者特権のコマンド ライン プロンプトを開き、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="03e84-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="03e84-139">**[スタート]** をクリックし、「**cmd**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="03e84-139">Go to **Start** and type **cmd**.</span></span>

8.  <span data-ttu-id="03e84-140">**[コマンド プロンプト]** を右クリックして **[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="03e84-140">Right-click **Command prompt** and select **Run as administrator**.</span></span>

![[ウィンドウのスタート] メニューの [管理者として実行] をポイントする](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="03e84-142">スクリプト ファイルの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="03e84-142">Type the location of the script file.</span></span> <span data-ttu-id="03e84-143">ファイルをデスクトップにコピーした場合は *、「%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd」と入力します。*</span><span class="sxs-lookup"><span data-stu-id="03e84-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="03e84-144">Enter キーを **押** するか **、[OK] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="03e84-144">Press the **Enter** key or click **OK**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="03e84-145">オフボードにより、デバイスはポータルへのセンサー データの送信を停止します。</span><span class="sxs-lookup"><span data-stu-id="03e84-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="03e84-146">デバイス構成の監視</span><span class="sxs-lookup"><span data-stu-id="03e84-146">Monitor device configuration</span></span>
<span data-ttu-id="03e84-147">[オンボードの問題のトラブルシューティング]() の異なる検証手順に従って、スクリプトが正常に完了し、エージェントが https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) 実行されたことを確認できます。</span><span class="sxs-lookup"><span data-stu-id="03e84-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="03e84-148">監視は、ポータルまたはさまざまな展開ツールを使用して直接実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="03e84-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="03e84-149">ポータルを使用してデバイスを監視する</span><span class="sxs-lookup"><span data-stu-id="03e84-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="03e84-150">[Microsoft [365 コンプライアンス センター] に移動します](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="03e84-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="03e84-151">[デバイス **の**  >  **オンボーディング デバイスの設定]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="03e84-151">Choose **Settings** > **Device onboarding** > **Devices**.</span></span>

3. <span data-ttu-id="03e84-152">デバイスが表示されているのを確認します。</span><span class="sxs-lookup"><span data-stu-id="03e84-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="03e84-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="03e84-153">Related topics</span></span>
- [<span data-ttu-id="03e84-154">グループ ポリシーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="03e84-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="03e84-155">Microsoft Endpoint Configuration Manager を使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="03e84-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="03e84-156">モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="03e84-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="03e84-157">非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="03e84-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="03e84-158">新しくオンボードされた Microsoft Defender ATP デバイスで検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="03e84-158">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="03e84-159">Microsoft Defender Advanced Threat Protection オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="03e84-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)