---
title: 非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード
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
description: 構成パッケージを仮想デスクトップ インフラストラクチャ (VDI) デバイスに展開して、エンドポイント データ損失防止サービスMicrosoft 365オンボーディングします。
ms.openlocfilehash: 64d9bfed3d1d5600b5843c697e894577f83527fe
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226877"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="33170-103">非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="33170-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="33170-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="33170-104">**Applies to:**</span></span>
- [<span data-ttu-id="33170-105">Microsoft 365エンドポイント データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="33170-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

- <span data-ttu-id="33170-106">仮想デスクトップ インフラストラクチャ (VDI) デバイス</span><span class="sxs-lookup"><span data-stu-id="33170-106">Virtual desktop infrastructure (VDI) devices</span></span>

> [!WARNING]
> <span data-ttu-id="33170-107">Microsoft 365仮想デスクトップのエンドポイント データ損失防止Windowsは、単一のセッション シナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="33170-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="33170-108">仮想デスクトップ上の複数Windowsシナリオは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="33170-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="33170-109">オンボード VDI デバイス</span><span class="sxs-lookup"><span data-stu-id="33170-109">Onboard VDI devices</span></span>

<span data-ttu-id="33170-110">Microsoft 365エンドポイント データ損失防止は、永続的でない VDI セッションオンボーディングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="33170-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span>

> [!NOTE]
> <span data-ttu-id="33170-111">永続的でない VDI セッションをオンボードするには、VDI デバイスが 1809 以上Windows 10必要があります。</span><span class="sxs-lookup"><span data-stu-id="33170-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="33170-112">VDIs をオンボーディングする際に関連する課題が生じ得る場合があります。</span><span class="sxs-lookup"><span data-stu-id="33170-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="33170-113">このシナリオの一般的な課題は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="33170-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="33170-114">短命セッションの早期オンボーディングは、実際のプロビジョニングの前にMicrosoft 365エンドポイント のデータ損失防止にオンボードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="33170-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="33170-115">通常、デバイス名は新しいセッションに再利用されます。</span><span class="sxs-lookup"><span data-stu-id="33170-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="33170-116">VDI デバイスは、次のいずれかのMicrosoft 365コンプライアンス センターに表示できます。</span><span class="sxs-lookup"><span data-stu-id="33170-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="33170-117">デバイスごとに 1 つのエントリ。</span><span class="sxs-lookup"><span data-stu-id="33170-117">Single entry for each device.</span></span>
<span data-ttu-id="33170-118">この場合、セッションの作成時に、無人応答ファイルを使用する場合など、同じデバイス名を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33170-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="33170-119">デバイスごとに複数のエントリ (セッションごとに 1 つ)。</span><span class="sxs-lookup"><span data-stu-id="33170-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="33170-120">次の手順では、VDI デバイスのオンボードについて説明し、単一エントリと複数エントリの手順を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="33170-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

> [!WARNING]
> <span data-ttu-id="33170-121">リソース構成が低い環境では、VDI ブート手順によってエンドポイント のデータ損失防止オンボーディングMicrosoft 365遅くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33170-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span>

1. <span data-ttu-id="33170-122">サービス オンボーディング ウィザードから.zipした VDI *構成パッケージ*(DeviceCompliancePackage.zip) を開きます。</span><span class="sxs-lookup"><span data-stu-id="33170-122">Open the VDI configuration package .zip file (*DeviceCompliancePackage.zip*) that you downloaded from the service onboarding wizard.</span></span>

2. <span data-ttu-id="33170-123">ナビゲーション ウィンドウで、[デバイスオンボーディングオンボーディング]**設定**  >  **を**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="33170-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="33170-124">[展開方法 **] フィールドで** 、[永続的でないエンドポイントの VDI オンボーディング **スクリプト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="33170-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

4. <span data-ttu-id="33170-125">[パッケージ **のダウンロード] を** クリックし、.zip保存します。</span><span class="sxs-lookup"><span data-stu-id="33170-125">Click **Download package** and save the .zip file.</span></span>

5. <span data-ttu-id="33170-126">パスの下のイメージに、.zipから抽出された DeviceCompliancePackage フォルダーからファイル `golden/master` をコピーします `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 。</span><span class="sxs-lookup"><span data-stu-id="33170-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span>

6. <span data-ttu-id="33170-127">デバイスごとに 1 つのエントリを実装していない場合は、DeviceComplianceOnboardingScript.cmd をコピーします。</span><span class="sxs-lookup"><span data-stu-id="33170-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

7. <span data-ttu-id="33170-128">デバイスごとに 1 つのエントリを実装する場合は、デバイスと DeviceComplianceOnboardingScript.cmd の両方Onboard-NonPersistentMachine.ps1コピーします。</span><span class="sxs-lookup"><span data-stu-id="33170-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>

    > [!NOTE]
    > <span data-ttu-id="33170-129">フォルダーが表示しない場合 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` は、非表示になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="33170-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="33170-130">エクスプローラーから [非表示のファイル **とフォルダーを** 表示する] オプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33170-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

8. <span data-ttu-id="33170-131">[ローカル グループ ポリシー エディター] ウィンドウを開き、[コンピューター **の構成**] Windows 設定  >    >  **に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="33170-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="33170-132">ドメイン グループ ポリシーは、永続的でない VDI デバイスのオンボーディングにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="33170-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

9. <span data-ttu-id="33170-133">実装するメソッドに応じて、適切な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="33170-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="33170-134">**デバイスごとに 1 つのエントリの場合**</span><span class="sxs-lookup"><span data-stu-id="33170-134">**For single entry for each device**</span></span>

   <span data-ttu-id="33170-135">**[PowerShell スクリプト]** タブを選択し、[追加] **(Windows** オンボーディング スクリプトをコピーしたパスでエクスプローラーが直接開きます) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="33170-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="33170-136">PowerShell スクリプトのオンボーディングに移動します `Onboard-NonPersistentMachine.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="33170-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>

   <span data-ttu-id="33170-137">**各デバイスの複数のエントリの場合**:</span><span class="sxs-lookup"><span data-stu-id="33170-137">**For multiple entries for each device**:</span></span>

   <span data-ttu-id="33170-138">[スクリプト **] タブを** 選択し、[追加]**をクリック** します (Windows、以前にオンボーディング スクリプトをコピーしたパスでエクスプローラーが直接開きます)。</span><span class="sxs-lookup"><span data-stu-id="33170-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="33170-139">オンボーディング bash スクリプトに移動します `DeviceComplianceOnboardingScript.cmd` 。</span><span class="sxs-lookup"><span data-stu-id="33170-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

10. <span data-ttu-id="33170-140">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="33170-140">Test your solution:</span></span>
    1. <span data-ttu-id="33170-141">1 つのデバイスでプールを作成します。</span><span class="sxs-lookup"><span data-stu-id="33170-141">Create a pool with one device.</span></span>
    1. <span data-ttu-id="33170-142">デバイスへのログオン。</span><span class="sxs-lookup"><span data-stu-id="33170-142">Logon to device.</span></span>
    1. <span data-ttu-id="33170-143">デバイスからのログオフ。</span><span class="sxs-lookup"><span data-stu-id="33170-143">Logoff from device.</span></span>
    1. <span data-ttu-id="33170-144">別のユーザーと一緒にデバイスにログオンします。</span><span class="sxs-lookup"><span data-stu-id="33170-144">Logon to device with another user.</span></span>
    1. <span data-ttu-id="33170-145">**デバイスごとに 1 つのエントリの場合**: デバイス内の 1 つのエントリMicrosoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="33170-145">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span>
       <span data-ttu-id="33170-146">**デバイスごとに複数のエントリについて**: デバイス内の複数のエントリをMicrosoft Defender セキュリティ センター。</span><span class="sxs-lookup"><span data-stu-id="33170-146">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

11. <span data-ttu-id="33170-147">[ナビゲーション **] ウィンドウの [** デバイス] リストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="33170-147">Click **Devices list** on the Navigation pane.</span></span>

12. <span data-ttu-id="33170-148">デバイス名を入力して検索機能を使用し、[検索の種類として **デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="33170-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="33170-149">非永続的仮想デスクトップ インフラストラクチャ (VDI) イメージの更新</span><span class="sxs-lookup"><span data-stu-id="33170-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>

<span data-ttu-id="33170-150">ベスト プラクティスとして、オフライン サービス ツールを使用してゴールデン/マスター イメージにパッチを適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="33170-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span>

<span data-ttu-id="33170-151">たとえば、次のコマンドを使用して、イメージがオフラインのままで更新プログラムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="33170-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing"
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="33170-152">DISM コマンドとオフライン サービスの詳細については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33170-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>

- [<span data-ttu-id="33170-153">DISM を使用Windowsイメージを変更する</span><span class="sxs-lookup"><span data-stu-id="33170-153">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="33170-154">DISM イメージ管理Command-Lineオプション</span><span class="sxs-lookup"><span data-stu-id="33170-154">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="33170-155">オフライン イメージ内のコンポーネント ストアのサイズを小Windowsする</span><span class="sxs-lookup"><span data-stu-id="33170-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="33170-156">非永続的な VDI 環境でオフライン サービスが実行可能なオプションでない場合は、一貫性とセンサーの正常性を確保するために次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33170-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="33170-157">オンライン サービスまたは修正プログラムのマスター イメージを起動した後、オフボード スクリプトを実行して、エンドポイント データ損失防止センサー Microsoft 365オフにします。</span><span class="sxs-lookup"><span data-stu-id="33170-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="33170-158">詳細については、「ローカル スクリプトを [使用したオフボード デバイス」を参照してください](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)。</span><span class="sxs-lookup"><span data-stu-id="33170-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="33170-159">CMD ウィンドウで以下のコマンドを実行して、センサーが停止した状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="33170-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="33170-160">必要に応じてイメージをサービスします。</span><span class="sxs-lookup"><span data-stu-id="33170-160">Service the image as needed.</span></span>

4. <span data-ttu-id="33170-161">次のコマンドを PsExec.exe を使用して実行します (起動後にセンサーが蓄積した可能性があるサイバー フォルダーの内容をクリーンアップするためにダウンロード https://download.sysinternals.com/files/PSTools.zip) できます。</span><span class="sxs-lookup"><span data-stu-id="33170-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="33170-162">通常と同じ方法で、ゴールデン/マスター イメージを再シールします。</span><span class="sxs-lookup"><span data-stu-id="33170-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="33170-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="33170-163">Related topics</span></span>

- [<span data-ttu-id="33170-164">グループ ポリシー Windows 10デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="33170-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="33170-165">デバイスをWindows 10デバイスをオンボードMicrosoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="33170-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="33170-166">モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="33170-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="33170-167">ローカル スクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="33170-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="33170-168">Microsoft Defender Advanced Threat Protection オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="33170-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
