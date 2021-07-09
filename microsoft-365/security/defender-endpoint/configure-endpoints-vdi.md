---
title: 非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード
description: 構成パッケージを仮想デスクトップ インフラストラクチャ (VDI) デバイスに展開して、Microsoft Defender for Endpoint サービスにオンボードします。
keywords: 仮想デスクトップ インフラストラクチャ (VDI) デバイス、vdi、デバイス管理の構成、エンドポイント用 Microsoft Defender の構成、エンドポイント
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
ms.date: 04/16/2020
ms.technology: mde
ms.openlocfilehash: 555f96dc1f45fb6a406b5993d0b8e4a3745c283b
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339636"
---
# <a name="onboard-the-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="ae95a-104">非永続的仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ae95a-104">Onboard the non-persistent virtual desktop infrastructure (VDI) devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ae95a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ae95a-105">**Applies to:**</span></span>
- [<span data-ttu-id="ae95a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ae95a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ae95a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ae95a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- <span data-ttu-id="ae95a-108">仮想デスクトップ インフラストラクチャ (VDI) デバイス</span><span class="sxs-lookup"><span data-stu-id="ae95a-108">Virtual desktop infrastructure (VDI) devices</span></span>
- <span data-ttu-id="ae95a-109">Windows 10、Windows Server 2019、Windows Server 2008R2/2012R2/2016</span><span class="sxs-lookup"><span data-stu-id="ae95a-109">Windows 10, Windows Server 2019, Windows Server 2008R2/2012R2/2016</span></span>

><span data-ttu-id="ae95a-110">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="ae95a-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ae95a-111">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="ae95a-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configvdi-abovefoldlink)

## <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a><span data-ttu-id="ae95a-112">非永続的な仮想デスクトップ インフラストラクチャ (VDI) デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ae95a-112">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>

<span data-ttu-id="ae95a-113">Defender for Endpoint は、永続的でない VDI セッションオンボーディングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ae95a-113">Defender for Endpoint supports non-persistent VDI session onboarding.</span></span> 


<span data-ttu-id="ae95a-114">VDIs をオンボーディングする際に関連する課題が生じ得る場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae95a-114">There might be associated challenges when onboarding VDIs.</span></span> <span data-ttu-id="ae95a-115">このシナリオの一般的な課題は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ae95a-115">The following are typical challenges for this scenario:</span></span>

- <span data-ttu-id="ae95a-116">実際のプロビジョニングの前に Defender for Endpoint にオンボードする必要がある短命セッションの早期オンボーディング。</span><span class="sxs-lookup"><span data-stu-id="ae95a-116">Instant early onboarding of a short-lived sessions, which must be onboarded to Defender for Endpoint prior to the actual provisioning.</span></span>
- <span data-ttu-id="ae95a-117">通常、デバイス名は新しいセッションに再利用されます。</span><span class="sxs-lookup"><span data-stu-id="ae95a-117">The device name is typically reused for new sessions.</span></span>

<span data-ttu-id="ae95a-118">VDI デバイスは、Defender for Endpoint ポータルに次のように表示できます。</span><span class="sxs-lookup"><span data-stu-id="ae95a-118">VDI devices can appear in Defender for Endpoint portal as either:</span></span>

- <span data-ttu-id="ae95a-119">デバイスごとに 1 つのエントリ。</span><span class="sxs-lookup"><span data-stu-id="ae95a-119">Single entry for each device.</span></span>

  > [!NOTE]
  > <span data-ttu-id="ae95a-120">この場合、セッションの作成 *時* に、無人応答ファイルを使用する場合など、同じデバイス名を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae95a-120">In this case, the *same* device name must be configured when the session is created, for example using an unattended answer file.</span></span>

- <span data-ttu-id="ae95a-121">デバイスごとに複数のエントリ (セッションごとに 1 つ)。</span><span class="sxs-lookup"><span data-stu-id="ae95a-121">Multiple entries for each device - one for each session.</span></span>

<span data-ttu-id="ae95a-122">次の手順では、VDI デバイスのオンボードについて説明し、単一エントリと複数エントリの手順を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="ae95a-122">The following steps will guide you through onboarding VDI devices and will highlight steps for single and multiple entries.</span></span>

>[!WARNING]
> <span data-ttu-id="ae95a-123">リソース構成が低い環境では、VDI ブート手順によって Defender for Endpoint センサーのオンボーディングが遅くなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae95a-123">For environments where there are low resource configurations, the VDI boot procedure might slow the Defender for Endpoint sensor onboarding.</span></span> 


### <a name="for-windows-10-or-windows-server-2019"></a><span data-ttu-id="ae95a-124">サーバー Windows 10またはWindowsサーバー 2019 の場合</span><span class="sxs-lookup"><span data-stu-id="ae95a-124">For Windows 10 or Windows Server 2019</span></span>

1.  <span data-ttu-id="ae95a-125">サービス オンボーディング ウィザードから.zipした VDI *構成パッケージ*(WindowsDefenderATPOnboardingPackage.zip) を開きます。</span><span class="sxs-lookup"><span data-stu-id="ae95a-125">Open the VDI configuration package .zip file (*WindowsDefenderATPOnboardingPackage.zip*) that you downloaded from the service onboarding wizard.</span></span> <span data-ttu-id="ae95a-126">また、次のポータルから[パッケージをMicrosoft 365 Defenderすることもできます](https://security.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="ae95a-126">You can also get the package from [Microsoft 365 Defender portal](https://security.microsoft.com/):</span></span>

    1. <span data-ttu-id="ae95a-127">ナビゲーション ウィンドウで、[エンドポイント **デバイス設定**  >    >  **オンボーディング]**  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae95a-127">In the navigation pane, select **Settings** > **Endpoints** > **Device management** > **Onboarding**.</span></span>

    1. <span data-ttu-id="ae95a-128">オペレーティング システムWindows 10を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae95a-128">Select Windows 10 as the operating system.</span></span>

    1.  <span data-ttu-id="ae95a-129">[展開方法 **] フィールドで** 、[永続的でないエンドポイントの VDI オンボーディング **スクリプト] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae95a-129">In the **Deployment method** field, select **VDI onboarding scripts for non-persistent endpoints**.</span></span>

    1. <span data-ttu-id="ae95a-130">[パッケージ **のダウンロード] を** クリックし、.zip保存します。</span><span class="sxs-lookup"><span data-stu-id="ae95a-130">Click **Download package** and save the .zip file.</span></span>

2. <span data-ttu-id="ae95a-131">windowsDefenderATPOnboardingPackage フォルダーからファイルをコピーし、.zip ファイルからパスの `golden/master` 下のイメージにコピーします `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 。</span><span class="sxs-lookup"><span data-stu-id="ae95a-131">Copy the files from the WindowsDefenderATPOnboardingPackage folder extracted from the .zip file into the `golden/master` image under the path `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup`.</span></span> 

    1. <span data-ttu-id="ae95a-132">デバイスごとに 1 つのエントリを実装していない場合は、WindowsDefenderATPOnboardingScript.cmd をコピーします。</span><span class="sxs-lookup"><span data-stu-id="ae95a-132">If you are not implementing a single entry for each device, copy WindowsDefenderATPOnboardingScript.cmd.</span></span>

    1. <span data-ttu-id="ae95a-133">デバイスごとに 1 つのエントリを実装する場合は、Onboard-NonPersistentMachine.ps1 WindowsDefenderATPOnboardingScript.cmd の両方をコピーします。</span><span class="sxs-lookup"><span data-stu-id="ae95a-133">If you are implementing a single entry for each device, copy both Onboard-NonPersistentMachine.ps1 and WindowsDefenderATPOnboardingScript.cmd.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ae95a-134">フォルダーが表示しない場合 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` は、非表示になる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ae95a-134">If you don't see the `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` folder, it might be hidden.</span></span> <span data-ttu-id="ae95a-135">エクスプローラーから [非表示のファイル **とフォルダーを** 表示する] オプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae95a-135">You'll need to choose the **Show hidden files and folders** option from File Explorer.</span></span>

3. <span data-ttu-id="ae95a-136">[ローカル グループ ポリシー エディター] ウィンドウを開き、[コンピューター **の構成**] Windows 設定  >    >  **に**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="ae95a-136">Open a Local Group Policy Editor window and navigate to **Computer Configuration** > **Windows Settings** > **Scripts** > **Startup**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ae95a-137">ドメイン グループ ポリシーは、永続的でない VDI デバイスのオンボーディングにも使用できます。</span><span class="sxs-lookup"><span data-stu-id="ae95a-137">Domain Group Policy may also be used for onboarding non-persistent VDI devices.</span></span>

4. <span data-ttu-id="ae95a-138">実装するメソッドに応じて、適切な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ae95a-138">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>

   - <span data-ttu-id="ae95a-139">デバイスごとに 1 つのエントリの場合:</span><span class="sxs-lookup"><span data-stu-id="ae95a-139">For single entry for each device:</span></span>
   
     <span data-ttu-id="ae95a-140">**[PowerShell スクリプト]** タブを選択し、[追加] **(Windows** オンボーディング スクリプトをコピーしたパスでエクスプローラーが直接開きます) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae95a-140">Select the **PowerShell Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="ae95a-141">PowerShell スクリプトのオンボーディングに移動します `Onboard-NonPersistentMachine.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="ae95a-141">Navigate to onboarding PowerShell script `Onboard-NonPersistentMachine.ps1`.</span></span> <span data-ttu-id="ae95a-142">他のファイルは自動的にトリガーされますので、指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ae95a-142">There is no need to specify the other file, as it will be triggered automatically.</span></span>
   
   - <span data-ttu-id="ae95a-143">各デバイスの複数のエントリの場合:</span><span class="sxs-lookup"><span data-stu-id="ae95a-143">For multiple entries for each device:</span></span>
   
     <span data-ttu-id="ae95a-144">[スクリプト **] タブを** 選択し、[追加]**をクリック** します (Windows、以前にオンボーディング スクリプトをコピーしたパスでエクスプローラーが直接開きます)。</span><span class="sxs-lookup"><span data-stu-id="ae95a-144">Select the **Scripts** tab, then click **Add** (Windows Explorer will open directly in the path where you copied the onboarding script earlier).</span></span> <span data-ttu-id="ae95a-145">オンボーディング bash スクリプトに移動します `WindowsDefenderATPOnboardingScript.cmd` 。</span><span class="sxs-lookup"><span data-stu-id="ae95a-145">Navigate to the onboarding bash script `WindowsDefenderATPOnboardingScript.cmd`.</span></span>

5. <span data-ttu-id="ae95a-146">ソリューションをテストします。</span><span class="sxs-lookup"><span data-stu-id="ae95a-146">Test your solution:</span></span>

   1. <span data-ttu-id="ae95a-147">1 つのデバイスでプールを作成します。</span><span class="sxs-lookup"><span data-stu-id="ae95a-147">Create a pool with one device.</span></span>
      
   1. <span data-ttu-id="ae95a-148">デバイスへのログオン。</span><span class="sxs-lookup"><span data-stu-id="ae95a-148">Logon to device.</span></span>
      
   1. <span data-ttu-id="ae95a-149">デバイスからのログオフ。</span><span class="sxs-lookup"><span data-stu-id="ae95a-149">Logoff from device.</span></span>

   1. <span data-ttu-id="ae95a-150">別のユーザーと一緒にデバイスにログオンします。</span><span class="sxs-lookup"><span data-stu-id="ae95a-150">Logon to device with another user.</span></span>
      
   1. <span data-ttu-id="ae95a-151">実装するメソッドに応じて、適切な手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ae95a-151">Depending on the method you'd like to implement, follow the appropriate steps:</span></span>
   
      - <span data-ttu-id="ae95a-152">デバイスごとに 1 つのエントリの場合:</span><span class="sxs-lookup"><span data-stu-id="ae95a-152">For single entry for each device:</span></span> 
    
        <span data-ttu-id="ae95a-153">ポータルで 1 つのエントリMicrosoft 365 Defenderします。</span><span class="sxs-lookup"><span data-stu-id="ae95a-153">Check only one entry in Microsoft 365 Defender portal.</span></span>

      - <span data-ttu-id="ae95a-154">各デバイスの複数のエントリの場合:</span><span class="sxs-lookup"><span data-stu-id="ae95a-154">For multiple entries for each device:</span></span> 
       
        <span data-ttu-id="ae95a-155">ポータルで複数のエントリMicrosoft 365 Defenderします。</span><span class="sxs-lookup"><span data-stu-id="ae95a-155">Check multiple entries in Microsoft 365 Defender portal.</span></span>

6. <span data-ttu-id="ae95a-156">[ナビゲーション **] ウィンドウの [** デバイス] リストをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ae95a-156">Click **Devices list** on the Navigation pane.</span></span>

7. <span data-ttu-id="ae95a-157">デバイス名を入力して検索機能を使用し、[検索の種類として **デバイス]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae95a-157">Use the search function by entering the device name and select **Device** as search type.</span></span>


## <a name="for-downlevel-skus"></a><span data-ttu-id="ae95a-158">ダウンレベル SKU の場合</span><span class="sxs-lookup"><span data-stu-id="ae95a-158">For downlevel SKUs</span></span>

> [!NOTE]
> <span data-ttu-id="ae95a-159">次のレジストリは、目的が "デバイスごとに 1 つのエントリ" を達成する場合にのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="ae95a-159">The following registry is relevant only when the aim is to achieve a 'Single entry for each device'.</span></span>

1. <span data-ttu-id="ae95a-160">レジストリ値を次に設定します。</span><span class="sxs-lookup"><span data-stu-id="ae95a-160">Set registry value to:</span></span>

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    <span data-ttu-id="ae95a-161">またはコマンド ラインを使用する:</span><span class="sxs-lookup"><span data-stu-id="ae95a-161">or using command line:</span></span>

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. <span data-ttu-id="ae95a-162">サーバーのオン [ボーディング プロセスに従います](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="ae95a-162">Follow the [server onboarding process](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span> 



## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a><span data-ttu-id="ae95a-163">非永続的仮想デスクトップ インフラストラクチャ (VDI) イメージの更新</span><span class="sxs-lookup"><span data-stu-id="ae95a-163">Updating non-persistent virtual desktop infrastructure (VDI) images</span></span>
<span data-ttu-id="ae95a-164">ベスト プラクティスとして、オフライン サービス ツールを使用してゴールデン/マスター イメージにパッチを適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ae95a-164">As a best practice, we recommend using offline servicing tools to patch golden/master images.</span></span><br>
<span data-ttu-id="ae95a-165">たとえば、次のコマンドを使用して、イメージがオフラインのままで更新プログラムをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ae95a-165">For example, you can use the below commands to install an update while the image remains offline:</span></span>

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing" 
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

<span data-ttu-id="ae95a-166">DISM コマンドとオフライン サービスの詳細については、以下の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae95a-166">For more information on DISM commands and offline servicing, please refer to the articles below:</span></span>
- [<span data-ttu-id="ae95a-167">DISM を使用Windowsイメージを変更する</span><span class="sxs-lookup"><span data-stu-id="ae95a-167">Modify a Windows image using DISM</span></span>](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [<span data-ttu-id="ae95a-168">DISM イメージ管理Command-Lineオプション</span><span class="sxs-lookup"><span data-stu-id="ae95a-168">DISM Image Management Command-Line Options</span></span>](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [<span data-ttu-id="ae95a-169">オフライン イメージ内のコンポーネント ストアのサイズを小Windowsする</span><span class="sxs-lookup"><span data-stu-id="ae95a-169">Reduce the Size of the Component Store in an Offline Windows Image</span></span>](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

<span data-ttu-id="ae95a-170">非永続的な VDI 環境でオフライン サービスが実行可能なオプションでない場合は、一貫性とセンサーの正常性を確保するために次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae95a-170">If offline servicing is not a viable option for your non-persistent VDI environment, the following steps should be taken to ensure consistency and sensor health:</span></span>

1. <span data-ttu-id="ae95a-171">オンライン サービスまたは修正プログラムのマスター イメージを起動した後、オフボード スクリプトを実行して Defender for Endpoint センサーをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ae95a-171">After booting the master image for online servicing or patching, run an offboarding script to turn off the Defender for Endpoint sensor.</span></span> <span data-ttu-id="ae95a-172">詳細については、「ローカル スクリプトを [使用したオフボード デバイス」を参照してください](configure-endpoints-script.md#offboard-devices-using-a-local-script)。</span><span class="sxs-lookup"><span data-stu-id="ae95a-172">For more information, see [Offboard devices using a local script](configure-endpoints-script.md#offboard-devices-using-a-local-script).</span></span>

2. <span data-ttu-id="ae95a-173">CMD ウィンドウで以下のコマンドを実行して、センサーが停止した状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="ae95a-173">Ensure the sensor is stopped by running the command below in a CMD window:</span></span>

   ```console
   sc query sense
   ```

3. <span data-ttu-id="ae95a-174">必要に応じてイメージをサービスします。</span><span class="sxs-lookup"><span data-stu-id="ae95a-174">Service the image as needed.</span></span>

4. <span data-ttu-id="ae95a-175">次のコマンドを PsExec.exe を使用して実行します (起動後にセンサーが蓄積した可能性があるサイバー フォルダーの内容をクリーンアップするためにダウンロード https://download.sysinternals.com/files/PSTools.zip) できます。</span><span class="sxs-lookup"><span data-stu-id="ae95a-175">Run the below commands using PsExec.exe (which can be downloaded from https://download.sysinternals.com/files/PSTools.zip) to cleanup the cyber folder contents that the sensor may have accumulated since boot:</span></span>

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. <span data-ttu-id="ae95a-176">通常と同じ方法で、ゴールデン/マスター イメージを再シールします。</span><span class="sxs-lookup"><span data-stu-id="ae95a-176">Re-seal the golden/master image as you normally would.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ae95a-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="ae95a-177">Related topics</span></span>
- [<span data-ttu-id="ae95a-178">グループ ポリシー Windows 10デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ae95a-178">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="ae95a-179">デバイスをWindows 10デバイスをオンボードMicrosoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ae95a-179">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="ae95a-180">モバイル デバイス管理ツールを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ae95a-180">Onboard Windows 10 devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md)
- [<span data-ttu-id="ae95a-181">ローカル スクリプトを使用した Windows 10 デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="ae95a-181">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="ae95a-182">Microsoft Defender for Endpoint オンボーディングの問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="ae95a-182">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
