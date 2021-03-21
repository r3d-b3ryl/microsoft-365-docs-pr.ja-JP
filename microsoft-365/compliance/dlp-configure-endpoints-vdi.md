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
description: 構成パッケージを仮想デスクトップ インフラストラクチャ (VDI) デバイスに展開して、Microsoft 365 Endpoint データ損失防止サービスにオンボードします。
ms.openlocfilehash: 2a62de6c238c1f681bde8a9bf25ecd596a10d390
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917953"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="5c5ed-103">非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="5c5ed-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="5c5ed-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5c5ed-104">**Applies to:**</span></span>
- [<span data-ttu-id="5c5ed-105">Microsoft 365 Endpoint データ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="5c5ed-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

- <span data-ttu-id="5c5ed-106">仮想デスクトップ インフラストラクチャ (VDI) デバイス</span><span class="sxs-lookup"><span data-stu-id="5c5ed-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="5c5ed-107">Windows Virtual Desktop の Microsoft 365 Endpoint データ損失防止サポートは、単一のセッション シナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="5c5ed-108">Windows Virtual Desktop でのマルチセッション シナリオは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="5c5ed-109">オンボード VDI デバイス</span><span class="sxs-lookup"><span data-stu-id="5c5ed-109">Onboard VDI devices</span></span>

<span data-ttu-id="5c5ed-110">Microsoft 365 Endpoint data loss Prevention は、永続的でない VDI セッションオンボーディングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="5c5ed-111">永続的でない VDI セッションをオンボードするには、VDI デバイスが Windows 10 1809 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="5c5ed-112">VDIs をオンボーディングする際に関連する課題が生じ得る場合があります。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="5c5ed-113">このシナリオの一般的な課題は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="5c5ed-114">短命のセッションの早期オンボーディングは、実際のプロビジョニングの前に Microsoft 365 Endpoint データ損失防止にオンボードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="5c5ed-115">通常、デバイス名は新しいセッションに再利用されます。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="5c5ed-116">VDI デバイスは、Microsoft 365 コンプライアンス センターに次のように表示できます。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="5c5ed-117">デバイスごとに 1 つのエントリ。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-117">Single entry for each device.</span></span>  
<span data-ttu-id="5c5ed-118">この場合、セッションの作成時に、無人応答ファイルを使用する場合など、同じデバイス名を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="5c5ed-119">デバイスごとに複数のエントリ (セッションごとに 1 つ)。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="5c5ed-120">次の手順では、VDI デバイスのオンボードについて説明し、単一エントリと複数エントリの手順を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="5c5ed-121">リソース構成が低い環境では、VDI ブート手順によって Microsoft 365 Endpoint データ損失防止オンボーディングが遅くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="5c5ed-122">サービス オンボーディング ウィザードからダウンロードした VDI *構成パッケージ*.zip ファイル (DeviceCompliancePackage.zip) を開きます。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-122">Open the VDI configuration package .zip file (*DeviceCompliancePackage.zip*) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="5c5ed-123">ナビゲーション ウィンドウで、[設定デバイスオン **ボーディング**  >  **オンボーディング**]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding**.</span></span>

3. <span data-ttu-id="5c5ed-124">[展開方法 **] フィールドで** 、[永続的でないエンドポイントの VDI オンボーディング **スクリプト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

5. <span data-ttu-id="5c5ed-125">[パッケージ **のダウンロード] を** クリックし、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="5c5ed-126">.zip ファイルから抽出された DeviceCompliancePackage フォルダーからパスの下の `golden/master` イメージにファイルをコピーします `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="5c5ed-127">デバイスごとに 1 つのエントリを実装していない場合は、DeviceComplianceOnboardingScript.cmd をコピーします。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="5c5ed-128">デバイスごとに 1 つのエントリを実装する場合は、デバイスと DeviceComplianceOnboardingScript.cmd の両方Onboard-NonPersistentMachine.ps1コピーします。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5c5ed-129">フォルダーが表示しない場合 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` は、非表示になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="5c5ed-130">エクスプローラーから [非表示のファイル **とフォルダーを** 表示する] オプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="5c5ed-131">[ローカル グループ ポリシー エディター] ウィンドウを開き、[コンピューター **構成**  >  **] [Windows 設定スクリプト**  >  **の起動] に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5c5ed-132">ドメイン グループ ポリシーは、永続的でない VDI デバイスのオンボーディングにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="5c5ed-133">実装するメソッドに応じて、適切な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="5c5ed-134">**デバイスごとに 1 つのエントリの場合**</span><span class="sxs-lookup"><span data-stu-id="5c5ed-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="5c5ed-135">**[PowerShell スクリプト] タブを選択** し、[追加] を **クリックします**(Windows エクスプローラーは、以前にオンボーディング スクリプトをコピーしたパスで直接開きます)。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="5c5ed-136">PowerShell スクリプトのオンボーディングに移動します `Onboard-NonPersistentMachine.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="5c5ed-137">**各デバイスの複数のエントリの場合**:</span><span class="sxs-lookup"><span data-stu-id="5c5ed-137">**For multiple entries for each device**:</span></span>
   
   <span data-ttu-id="5c5ed-138">[スクリプト **] タブを** 選択し、[追加] を **クリックします** (Windows エクスプローラーは、以前にオンボーディング スクリプトをコピーしたパスで直接開きます)。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="5c5ed-139">オンボーディング bash スクリプトに移動します `DeviceComplianceOnboardingScript.cmd` 。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="5c5ed-140">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-140">Test your solution:</span></span>

   1. <span data-ttu-id="5c5ed-141">1 つのデバイスでプールを作成します。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="5c5ed-142">デバイスへのログオン。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="5c5ed-143">デバイスからのログオフ。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-143">Logoff from device.</span></span>

   1. <span data-ttu-id="5c5ed-144">別のユーザーと一緒にデバイスにログオンします。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="5c5ed-145">**デバイスごとに 1 つのエントリの** 場合: Microsoft Defender セキュリティ センターで 1 つのエントリのみを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-145">**For single entry for each device**: Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="5c5ed-146">**デバイスごとに複数のエントリについて**: Microsoft Defender セキュリティ センターで複数のエントリを確認します。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-146">**For multiple entries for each device**: Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="5c5ed-147">[ナビゲーション **] ウィンドウの [** デバイス] リストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="5c5ed-148">デバイス名を入力して検索機能を使用し、[検索の種類として **デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="5c5ed-149">非永続的仮想デスクトップ インフラストラクチャ (VDI) イメージの更新</span><span class="sxs-lookup"><span data-stu-id="5c5ed-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="5c5ed-150">ベスト プラクティスとして、オフライン サービス ツールを使用してゴールデン/マスター イメージにパッチを適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="5c5ed-151">たとえば、次のコマンドを使用して、イメージがオフラインのままで更新プログラムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="5c5ed-152">DISM コマンドとオフライン サービスの詳細については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="5c5ed-153">DISM を使用して Windows イメージを変更する</span><span class="sxs-lookup"><span data-stu-id="5c5ed-153">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="5c5ed-154">DISM イメージ管理Command-Lineオプション</span><span class="sxs-lookup"><span data-stu-id="5c5ed-154">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="5c5ed-155">オフライン Windows イメージのコンポーネント ストアのサイズを小さい</span><span class="sxs-lookup"><span data-stu-id="5c5ed-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="5c5ed-156">非永続的な VDI 環境でオフライン サービスが実行可能なオプションでない場合は、一貫性とセンサーの正常性を確保するために次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="5c5ed-157">オンライン サービスまたは修正プログラムのマスター イメージを起動した後、オフボード スクリプトを実行して Microsoft 365 Endpoint データ損失防止センサーをオフにします。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="5c5ed-158">詳細については、「ローカル スクリプトを [使用したオフボード デバイス」を参照してください](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="5c5ed-159">CMD ウィンドウで以下のコマンドを実行して、センサーが停止した状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="5c5ed-160">必要に応じてイメージをサービスします。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-160">Service the image as needed.</span></span>

4. <span data-ttu-id="5c5ed-161">次のコマンドを PsExec.exe を使用して実行します (起動後にセンサーが蓄積した可能性があるサイバー フォルダーの内容をクリーンアップするためにダウンロード https://download.sysinternals.com/files/PSTools.zip) できます。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="5c5ed-162">通常と同じ方法で、ゴールデン/マスター イメージを再シールします。</span><span class="sxs-lookup"><span data-stu-id="5c5ed-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5c5ed-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c5ed-163">Related topics</span></span>
- [<span data-ttu-id="5c5ed-164">グループ ポリシーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="5c5ed-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="5c5ed-165">Microsoft Endpoint Configuration Manager を使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="5c5ed-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="5c5ed-166">モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="5c5ed-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="5c5ed-167">ローカル スクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="5c5ed-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="5c5ed-168">Microsoft Defender Advanced Threat Protection オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5c5ed-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)