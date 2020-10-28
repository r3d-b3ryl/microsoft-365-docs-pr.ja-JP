---
title: オンボードの非永続仮想デスクトップインフラストラクチャ (VDI) デバイス
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
description: 仮想デスクトップインフラストラクチャ (VDI) デバイスに構成パッケージを展開して、それらが Microsoft 365 エンドポイントのデータ損失防止サービスに利用されるようにします。
ms.openlocfilehash: ce5ad0ba6af3e18a6f6c53e1860fc47a77c38770
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769452"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="a1b05-103">オンボードの非永続仮想デスクトップインフラストラクチャ (VDI) デバイス</span><span class="sxs-lookup"><span data-stu-id="a1b05-103">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="a1b05-104">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="a1b05-104">**Applies to:**</span></span>
- [<span data-ttu-id="a1b05-105">Microsoft 365 エンドポイントのデータ損失防止 (DLP)</span><span class="sxs-lookup"><span data-stu-id="a1b05-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

- <span data-ttu-id="a1b05-106">仮想デスクトップインフラストラクチャ (VDI) デバイス</span><span class="sxs-lookup"><span data-stu-id="a1b05-106">Virtual desktop infrastructure (VDI) devices</span></span>

>[!WARNING]
> <span data-ttu-id="a1b05-107">Microsoft 365 エンドポイントのデータ損失防止サポート Windows 仮想デスクトップは1つのセッションシナリオをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="a1b05-107">Microsoft 365 Endpoint data loss prevention support for Windows Virtual Desktop supports single session scenarios.</span></span> <span data-ttu-id="a1b05-108">Windows 仮想デスクトップ上のマルチセッションシナリオは現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="a1b05-108">Multi-session scenarios on Windows Virtual Desktop are currently not supported.</span></span>

## <a name="onboard-vdi-devices"></a><span data-ttu-id="a1b05-109">オンボード VDI デバイス</span><span class="sxs-lookup"><span data-stu-id="a1b05-109">Onboard VDI devices</span></span>

<span data-ttu-id="a1b05-110">Microsoft 365 エンドポイントのデータ損失防止は、非永続的な VDI セッションのオンボードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="a1b05-110">Microsoft 365 Endpoint data loss prevention supports non-persistent VDI session onboarding.</span></span> 

>[!Note]
><span data-ttu-id="a1b05-111">非永続的な VDI セッションをオンボードにするには、VDI デバイスが Windows 10 1809 以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1b05-111">To onboard non-persistent VDI sessions, VDI devices must be on Windows 10 1809 or higher.</span></span>

<span data-ttu-id="a1b05-112">オンボード VDIs の場合、課題が関連付けられている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a1b05-112">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="a1b05-113">このシナリオの一般的な課題は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a1b05-113">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="a1b05-114">短時間セッションの早期の初期処理。これは、実際のプロビジョニング前に Microsoft 365 エンドポイントのデータ損失防止に利用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1b05-114">Instant early onboarding of a short-lived sessions, which must be onboarded to  Microsoft 365 Endpoint data loss prevention prior to the actual provisioning.</span></span>
- <span data-ttu-id="a1b05-115">デバイス名は、通常、新しいセッションに再利用されます。</span><span class="sxs-lookup"><span data-stu-id="a1b05-115">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="a1b05-116">VDI デバイスは、次のいずれかの方法で Microsoft 365 コンプライアンスセンターに表示できます。</span><span class="sxs-lookup"><span data-stu-id="a1b05-116">VDI devices can appear in the Microsoft 365 Compliance center as either:</span></span>

- <span data-ttu-id="a1b05-117">デバイスごとに1つのエントリ。</span><span class="sxs-lookup"><span data-stu-id="a1b05-117">Single entry for each device.</span></span>  
<span data-ttu-id="a1b05-118">この場合は、セッションの作成時に、無人応答ファイルを使用するなど、 *同じ* デバイス名を構成する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a1b05-118">Note that in this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>
- <span data-ttu-id="a1b05-119">各デバイスの複数のエントリ。セッションごとに1つ。</span><span class="sxs-lookup"><span data-stu-id="a1b05-119">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="a1b05-120">次の手順では、オンボード VDI デバイスについて説明し、単一および複数のエントリのステップを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="a1b05-120">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="a1b05-121">リソース構成が少ない環境では、VDI のブート手順により、Microsoft 365 エンドポイントのデータ損失防止のオンボードが遅くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a1b05-121">For environments where there are low resource configurations, the VDI boot procedure might slow the Microsoft 365 Endpoint data loss prevention onboarding.</span></span> 

1.  <span data-ttu-id="a1b05-122">サービスオンボードウィザードからダウンロードした VDI 構成パッケージ .zip ファイル ( *DeviceCompliancePackage.zip* ) を開きます。</span><span class="sxs-lookup"><span data-stu-id="a1b05-122">Open the VDI configuration package .zip file ( *DeviceCompliancePackage.zip* ) that you downloaded from the service onboarding wizard.</span></span>

2.  <span data-ttu-id="a1b05-123">ナビゲーションウィンドウで、[ **設定** ] [  >  **デバイスのオン** ボードオンボード] を選択し  >  **Onboarding** ます。</span><span class="sxs-lookup"><span data-stu-id="a1b05-123">In the navigation pane, select **Settings** > **Device onboarding** > **Onboarding** .</span></span>

3. <span data-ttu-id="a1b05-124">[ **展開方法** ] フィールドで、 **非永続エンドポイントの VDI オンボードスクリプト** を選択します。</span><span class="sxs-lookup"><span data-stu-id="a1b05-124">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints** .</span></span>

5. <span data-ttu-id="a1b05-125">[ **パッケージのダウンロード** ] をクリックし、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="a1b05-125">Click **Download package** and save the .zip file.</span></span>

6. <span data-ttu-id="a1b05-126">.Zip ファイルから抽出された DeviceCompliancePackage フォルダーからパスの下の画像にファイルをコピーし `golden/master` `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` ます。</span><span class="sxs-lookup"><span data-stu-id="a1b05-126">Copy the files from the DeviceCompliancePackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

7. <span data-ttu-id="a1b05-127">各デバイスに対して単一のエントリを実装していない場合は、Devicecompliare On掲示板をコピーします。</span><span class="sxs-lookup"><span data-stu-id="a1b05-127">If you are not implementing a single entry for each device, copy DeviceComplianceOnboardingScript.cmd.</span></span>

8. <span data-ttu-id="a1b05-128">各デバイスに対して単一のエントリを実装する場合は、Onboard-NonPersistentMachine.ps1 と Devicecompliare On掲示用の両方をコピーします。</span><span class="sxs-lookup"><span data-stu-id="a1b05-128">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and DeviceComplianceOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a1b05-129">フォルダーが表示されていない場合は `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 、非表示になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="a1b05-129">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="a1b05-130">[ファイルエクスプローラー] の [ **非表示のファイルとフォルダーを表示** する] オプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1b05-130">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

9. <span data-ttu-id="a1b05-131">ローカルグループポリシーエディターウィンドウを開き、[ **コンピューターの構成** ]  >  **Windows の設定**  >  **スクリプト** のスタートアップに移動し  >  **Startup** ます。</span><span class="sxs-lookup"><span data-stu-id="a1b05-131">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup** .</span></span>

   > [!NOTE]
   > <span data-ttu-id="a1b05-132">ドメイングループポリシーは、非永続的な VDI デバイスのオンボードにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="a1b05-132">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="a1b05-133">実装する方法に応じて、適切な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a1b05-133">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   <span data-ttu-id="a1b05-134">**各デバイスの単一エントリの場合**</span><span class="sxs-lookup"><span data-stu-id="a1b05-134">**For single entry for each device**</span></span>
   
   <span data-ttu-id="a1b05-135">[ **PowerShell スクリプト** ] タブを選択し、[ **追加** ] をクリックします (前の手順を実行した後、前の手順で開始した開始位置のパスで、Windows Explorer が直接開きます)。</span><span class="sxs-lookup"><span data-stu-id="a1b05-135">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="a1b05-136">オンボード PowerShell スクリプトに移動 `Onboard-NonPersistentMachine.ps1` します。</span><span class="sxs-lookup"><span data-stu-id="a1b05-136">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span>
   
   <span data-ttu-id="a1b05-137">**各デバイスの複数のエントリの場合** :</span><span class="sxs-lookup"><span data-stu-id="a1b05-137">**For multiple entries for each device** :</span></span>
   
   <span data-ttu-id="a1b05-138">[ **スクリプト** ] タブを選択し、[ **追加** ] をクリックします (前の手順を実行した後、前の手順で開始したパスで、Windows Explorer が直接開きます)。</span><span class="sxs-lookup"><span data-stu-id="a1b05-138">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="a1b05-139">オンボード bash スクリプトに移動し `DeviceComplianceOnboardingScript.cmd` ます。</span><span class="sxs-lookup"><span data-stu-id="a1b05-139">Navigate to the onboarding bash script `DeviceComplianceOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="a1b05-140">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="a1b05-140">Test your solution:</span></span>

   1. <span data-ttu-id="a1b05-141">1つのデバイスでプールを作成します。</span><span class="sxs-lookup"><span data-stu-id="a1b05-141">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="a1b05-142">デバイスへのログオン。</span><span class="sxs-lookup"><span data-stu-id="a1b05-142">Logon to device.</span></span>
      
   1. <span data-ttu-id="a1b05-143">デバイスからログオフします。</span><span class="sxs-lookup"><span data-stu-id="a1b05-143">Logoff from device.</span></span>

   1. <span data-ttu-id="a1b05-144">別のユーザーとデバイスにログオンします。</span><span class="sxs-lookup"><span data-stu-id="a1b05-144">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="a1b05-145">**各デバイスの単一エントリの場合** : Microsoft Defender セキュリティセンターの1つのエントリのみをチェックします。</span><span class="sxs-lookup"><span data-stu-id="a1b05-145">**For single entry for each device** : Check only one entry in Microsoft Defender Security Center.</span></span><br>
      <span data-ttu-id="a1b05-146">**各デバイスの複数のエントリについて** : Microsoft Defender セキュリティセンターの複数のエントリをチェックします。</span><span class="sxs-lookup"><span data-stu-id="a1b05-146">**For multiple entries for each device** : Check multiple entries in Microsoft Defender Security Center.</span></span>

6. <span data-ttu-id="a1b05-147">ナビゲーションウィンドウの [ **デバイス] リスト** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a1b05-147">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="a1b05-148">デバイス名を入力して search 関数を使用し、検索の種類として [ **デバイス** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a1b05-148">Use the search function by entering the device name and select **Device** as search type.</span></span>

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="a1b05-149">非永続仮想デスクトップインフラストラクチャ (VDI) の画像を更新する</span><span class="sxs-lookup"><span data-stu-id="a1b05-149">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="a1b05-150">ベストプラクティスとして、オフラインサービスツールを使用してゴールデン/マスタイメージにパッチを適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a1b05-150">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="a1b05-151">たとえば、次のコマンドを使用して更新プログラムをインストールし、画像はオフラインのままにしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="a1b05-151">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="a1b05-152">DISM コマンドとオフラインサービスの詳細については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1b05-152">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="a1b05-153">DISM を使用して Windows イメージを変更する</span><span class="sxs-lookup"><span data-stu-id="a1b05-153">Modify a Windows image using DISM</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="a1b05-154">DISM イメージ管理 Command-Line オプション</span><span class="sxs-lookup"><span data-stu-id="a1b05-154">DISM Image Management Command-Line Options</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="a1b05-155">オフライン Windows イメージのコンポーネントストアのサイズを小さくする</span><span class="sxs-lookup"><span data-stu-id="a1b05-155">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](https://docs.microsoft.com/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="a1b05-156">オフラインサービスが非永続的な VDI 環境に対して有効なオプションではない場合は、一貫性とセンサーの正常性を確保するために、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a1b05-156">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="a1b05-157">オンラインサービスまたはパッチを適用するためにマスターイメージを起動した後、オフボードスクリプトを実行して、Microsoft 365 エンドポイントのデータ損失防止センサーをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a1b05-157">After booting the master image for online servicing or patching, run an offboarding script to turn off the Microsoft 365 Endpoint data loss prevention sensor.</span></span> <span data-ttu-id="a1b05-158">詳細については、「 [Offboard devices using local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a1b05-158">For more information, see [Offboard devices using a local script](dlp-configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="a1b05-159">CMD ウィンドウで以下のコマンドを実行して、センサーが停止していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a1b05-159">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="a1b05-160">必要に応じて、画像を処理します。</span><span class="sxs-lookup"><span data-stu-id="a1b05-160">Service the image as needed.</span></span>

4. <span data-ttu-id="a1b05-161">PsExec.exe を使用して以下のコマンドを実行します (からダウンロードして、 https://download.sysinternals.com/files/PSTools.zip) センサーがブート後に蓄積したサイバーフォルダーの内容をクリーンアップすることができます)。</span><span class="sxs-lookup"><span data-stu-id="a1b05-161">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="a1b05-162">通常どおり、ゴールデン/マスターイメージを再シールします。</span><span class="sxs-lookup"><span data-stu-id="a1b05-162">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a1b05-163">関連項目</span><span class="sxs-lookup"><span data-stu-id="a1b05-163">Related topics</span></span>
- [<span data-ttu-id="a1b05-164">グループポリシーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="a1b05-164">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="a1b05-165">Microsoft エンドポイント構成マネージャーを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="a1b05-165">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="a1b05-166">モバイルデバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="a1b05-166">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](dlp-configure-endpoints-mdm.md)
- [<span data-ttu-id="a1b05-167">ローカルスクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="a1b05-167">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="a1b05-168">Microsoft Defender Advanced Threat Protection のオンボード問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="a1b05-168">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
