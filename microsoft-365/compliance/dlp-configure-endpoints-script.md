---
title: ローカルスクリプトを使用した Windows 10 デバイスのオンボード
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
description: ローカルスクリプトを使用して、サービスに利用するように構成パッケージをデバイスに展開します。
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769472"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a><span data-ttu-id="ea38e-103">ローカルスクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ea38e-103">Onboard Windows 10 devices using a local script</span></span>

<span data-ttu-id="ea38e-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ea38e-104">**Applies to:**</span></span>

- [<span data-ttu-id="ea38e-105">Microsoft 365 エンドポイントのデータ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="ea38e-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="ea38e-106">個別のデバイスを手動で Microsoft 365 エンドポイントのデータ損失防止にオンボードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ea38e-106">You can also manually onboard individual devices to Microsoft 365 Endpoint data loss prevention.</span></span> <span data-ttu-id="ea38e-107">ネットワーク内のすべてのデバイスをオンボードにする前に、サービスをテストするときに最初にこの操作を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ea38e-107">You might want to do this first when testing the service before you commit to onboarding all devices in your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea38e-108">このスクリプトは最大10台のデバイスで使用するように最適化されています。</span><span class="sxs-lookup"><span data-stu-id="ea38e-108">This script has been optimized for use on up to 10 devices.</span></span>
>
> <span data-ttu-id="ea38e-109">スケールで展開するには、 [他の展開オプション](dlp-configure-endpoints.md)を使用します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-109">To deploy at scale, use [other deployment options](dlp-configure-endpoints.md).</span></span> <span data-ttu-id="ea38e-110">たとえば、 [グループポリシーを使用して Windows 10 デバイス](dlp-configure-endpoints-gp.md)で使用可能なスクリプトを使用して、オンボードスクリプトを運用環境の10台以上のデバイスに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="ea38e-110">For example, you can deploy an onboarding script to more than 10 devices in production with the script available in [Onboard Windows 10 devices using Group Policy](dlp-configure-endpoints-gp.md).</span></span>

## <a name="onboard-devices"></a><span data-ttu-id="ea38e-111">オンボードデバイス</span><span class="sxs-lookup"><span data-stu-id="ea38e-111">Onboard devices</span></span>
 
1.  <span data-ttu-id="ea38e-112">サービスオンボードウィザードからダウンロードした GP 構成パッケージ .zip ファイル ( *DeviceComplianceOnboardingPackage.zip* ) を開きます。</span><span class="sxs-lookup"><span data-stu-id="ea38e-112">Open the GP configuration package .zip file ( *DeviceComplianceOnboardingPackage.zip* ) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="ea38e-113">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com)からパッケージを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea38e-113">You can also get the package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="ea38e-114">ナビゲーションウィンドウで、[ **設定** ] [  >  **デバイスのオンボード** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-114">In the navigation pane, select **Settings** > **Device onboarding** .</span></span>

3. <span data-ttu-id="ea38e-115">[ **展開方法** ] フィールドで、[ **ローカルスクリプト** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-115">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="ea38e-116">[ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-116">Click **Download package** and save the .zip file.</span></span>
  
5. <span data-ttu-id="ea38e-117">構成パッケージの内容を、展開するデバイス上の場所 (たとえば、デスクトップ) に抽出します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-117">Extract the contents of the configuration package to a location on the device you want to onboard (for example, the Desktop).</span></span> <span data-ttu-id="ea38e-118">*Deviceonboardingscript* という名前のファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="ea38e-118">You should have a file named *DeviceOnboardingScript.cmd* .</span></span>

6.  <span data-ttu-id="ea38e-119">デバイス上で管理者特権のコマンドラインプロンプトを開き、次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-119">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="ea38e-120">[ **スタート** ] に移動し、「 **cmd** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-120">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="ea38e-121">[ **コマンドプロンプト** ] を右クリックし、[ **管理者として実行** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-121">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![[管理者として実行] をポイントする [スタート] メニュー](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="ea38e-123">スクリプトファイルの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-123">Type the location of the script file.</span></span> <span data-ttu-id="ea38e-124">ファイルをデスクトップにコピーした場合は、次のように入力します。 *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span><span class="sxs-lookup"><span data-stu-id="ea38e-124">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*</span></span>

10.  <span data-ttu-id="ea38e-125">Enter キーを押すか、[ **OK]\*\*\*\*を** クリックします。</span><span class="sxs-lookup"><span data-stu-id="ea38e-125">Press the **Enter** key or click **OK** .</span></span>

<span data-ttu-id="ea38e-126">デバイスが準拠しており、センサーデータを正しく報告するかどうかを手動で検証する方法については、 [Microsoft Defender Advanced Threat Protection のオンボード問題のトラブルシューティング](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)を行う方法を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea38e-126">For information on how you can manually validate that the device is compliant and correctly reports sensor data see, [Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding).</span></span>

## <a name="offboard-devices-using-a-local-script"></a><span data-ttu-id="ea38e-127">ローカルスクリプトを使用した offboard デバイス</span><span class="sxs-lookup"><span data-stu-id="ea38e-127">Offboard devices using a local script</span></span>
<span data-ttu-id="ea38e-128">セキュリティ上の理由から、デバイスをオフにするために使用されるパッケージの有効期限は、ダウンロードされた日付から30日後になります。</span><span class="sxs-lookup"><span data-stu-id="ea38e-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="ea38e-129">有効期限切れのデバイスに送信されたオフボードパッケージは拒否されます。</span><span class="sxs-lookup"><span data-stu-id="ea38e-129">Expired offboarding packages sent to an device will be rejected.</span></span> <span data-ttu-id="ea38e-130">オフボードパッケージをダウンロードすると、パッケージの有効期限日が通知され、パッケージ名にも含まれるようになります。</span><span class="sxs-lookup"><span data-stu-id="ea38e-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="ea38e-131">オンボードポリシーとオフボードポリシーを同じデバイスに同時に展開することはできません。そうしないと、予期しない競合が発生します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="ea38e-132">[Microsoft コンプライアンスセンター](https://compliance.microsoft.com)からオフボードパッケージを取得する</span><span class="sxs-lookup"><span data-stu-id="ea38e-132">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com)</span></span>

2. <span data-ttu-id="ea38e-133">ナビゲーションウィンドウで、[ **設定** とデバイスのオフボード] を選択し  >  **Device offboarding** ます。</span><span class="sxs-lookup"><span data-stu-id="ea38e-133">In the navigation pane, select **Settings** > **Device offboarding** .</span></span>

3. <span data-ttu-id="ea38e-134">[ **展開方法** ] フィールドで、[ **ローカルスクリプト** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-134">In the **Deployment method** field, select **Local Script** .</span></span>

4. <span data-ttu-id="ea38e-135">[ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-135">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="ea38e-136">.Zip ファイルの内容を、デバイスからアクセスできる共有の読み取り専用の場所に抽出します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-136">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the devices.</span></span> <span data-ttu-id="ea38e-137">*DeviceComplianceOffboardingScript_valid_until_YYYY* という名前のファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="ea38e-137">You should have a file named *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* .</span></span>

6.  <span data-ttu-id="ea38e-138">デバイス上で管理者特権のコマンドラインプロンプトを開き、次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-138">Open an elevated command-line prompt on the device and run the script:</span></span>

7.  <span data-ttu-id="ea38e-139">[ **スタート** ] に移動し、「 **cmd** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-139">Go to **Start** and type **cmd** .</span></span>

8.  <span data-ttu-id="ea38e-140">[ **コマンドプロンプト** ] を右クリックし、[ **管理者として実行** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-140">Right-click **Command prompt** and select **Run as administrator** .</span></span>

![[管理者として実行] をポイントする [スタート] メニュー](../media/dlp-run-as-admin.png)

9.  <span data-ttu-id="ea38e-142">スクリプトファイルの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-142">Type the location of the script file.</span></span> <span data-ttu-id="ea38e-143">ファイルをデスクトップにコピーした場合は、次のように入力します。 *%userprofile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY mmmm*</span><span class="sxs-lookup"><span data-stu-id="ea38e-143">If you copied the file to the desktop, type: *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd*</span></span>

10.  <span data-ttu-id="ea38e-144">Enter キーを押すか、[ **OK]\*\*\*\*を** クリックします。</span><span class="sxs-lookup"><span data-stu-id="ea38e-144">Press the **Enter** key or click **OK** .</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea38e-145">オフボードは、デバイスがポータルへのセンサーデータの送信を停止させます。</span><span class="sxs-lookup"><span data-stu-id="ea38e-145">Offboarding causes the device to stop sending sensor data to the portal.</span></span>


## <a name="monitor-device-configuration"></a><span data-ttu-id="ea38e-146">デバイス構成の監視</span><span class="sxs-lookup"><span data-stu-id="ea38e-146">Monitor device configuration</span></span>
<span data-ttu-id="ea38e-147">[トラブルシューティングの問題のトラブルシューティング] (( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) スクリプトが正常に完了し、エージェントが実行されていることを確認する) にある、さまざまな検証手順を実行できます。</span><span class="sxs-lookup"><span data-stu-id="ea38e-147">You can follow the different verification steps in the [Troubleshoot onboarding issues]((https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) to verify that the script completed successfully and the agent is running.</span></span>

<span data-ttu-id="ea38e-148">また、ポータル上で、またはさまざまな展開ツールを使用して、監視を直接実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea38e-148">Monitoring can also be done directly on the portal, or by using the different deployment tools.</span></span>

### <a name="monitor-devices-using-the-portal"></a><span data-ttu-id="ea38e-149">ポータルを使用してデバイスを監視する</span><span class="sxs-lookup"><span data-stu-id="ea38e-149">Monitor devices using the portal</span></span>
1. <span data-ttu-id="ea38e-150">[Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)に移動します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-150">Go to [Microsoft 365 Compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="ea38e-151">[ **設定**  >  **デバイスのオンボード** デバイス] を選択し  >  **Devices** ます。</span><span class="sxs-lookup"><span data-stu-id="ea38e-151">Choose **Settings** > **Device onboarding** > **Devices** .</span></span>

3. <span data-ttu-id="ea38e-152">デバイスが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea38e-152">Verify that devices are appearing.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ea38e-153">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea38e-153">Related topics</span></span>
- [<span data-ttu-id="ea38e-154">グループポリシーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ea38e-154">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="ea38e-155">Microsoft エンドポイント構成マネージャーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ea38e-155">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="ea38e-156">モバイルデバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ea38e-156">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="ea38e-157">オンボードの非永続仮想デスクトップインフラストラクチャ (VDI) デバイス</span><span class="sxs-lookup"><span data-stu-id="ea38e-157">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="ea38e-158">新しく利用 Microsoft Defender ATP デバイスで検出テストを実行する</span><span class="sxs-lookup"><span data-stu-id="ea38e-158">Run a detection test on a newly onboarded Microsoft Defender ATP device</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [<span data-ttu-id="ea38e-159">Microsoft Defender Advanced Threat Protection のオンボード問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ea38e-159">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
