---
title: Windows Virtual Desktop の Windows 10 マルチセッション デバイスのオンボード
description: この記事の詳細については、「Windows 10デスクトップでのマルチセッション デバイスのオンボーディングWindows参照してください。
keywords: Windows仮想デスクトップ、WVD、microsoft Defender、エンドポイント、オンボード
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 9114a825ad011f0b2a17cea4929ab2a09bfa2172
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339480"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a><span data-ttu-id="fa51a-104">Windows Virtual Desktop の Windows 10 マルチセッション デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="fa51a-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span></span> 
<span data-ttu-id="fa51a-105">読み取り 6 分</span><span class="sxs-lookup"><span data-stu-id="fa51a-105">6 minutes to read</span></span> 

<span data-ttu-id="fa51a-106">適用対象:</span><span class="sxs-lookup"><span data-stu-id="fa51a-106">Applies to:</span></span> 
- <span data-ttu-id="fa51a-107">Windows 10仮想デスクトップ (WVD) でWindowsセッションを実行する場合</span><span class="sxs-lookup"><span data-stu-id="fa51a-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span></span> 

<span data-ttu-id="fa51a-108">Microsoft Defender for Endpoint は、VDI セッションと仮想デスクトップ セッションWindowsサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fa51a-108">Microsoft Defender for Endpoint supports monitoring both VDI and Windows Virtual Desktop sessions.</span></span> <span data-ttu-id="fa51a-109">組織のニーズに応じて、従業員が管理されていないデバイス、リモートの場所、または類似のシナリオから企業データやアプリにアクセスするために、VDI または Windows Virtual Desktop セッションを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa51a-109">Depending on your organization's needs, you might need to implement VDI or Windows Virtual Desktop sessions to help your employees access corporate data and apps from an unmanaged device, remote location, or similar scenario.</span></span> <span data-ttu-id="fa51a-110">Microsoft Defender for Endpoint を使用すると、これらの仮想マシンで異常なアクティビティを監視できます。</span><span class="sxs-lookup"><span data-stu-id="fa51a-110">With Microsoft Defender for Endpoint, you can monitor these virtual machines for anomalous activity.</span></span>

 ## <a name="before-you-begin"></a><span data-ttu-id="fa51a-111">開始する前に</span><span class="sxs-lookup"><span data-stu-id="fa51a-111">Before you begin</span></span>
<span data-ttu-id="fa51a-112">非永続的な [VDI の考慮事項について理解してください](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)。</span><span class="sxs-lookup"><span data-stu-id="fa51a-112">Familiarize yourself with the [considerations for non-persistent VDI](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span> <span data-ttu-id="fa51a-113">仮想[Windows非](/azure/virtual-desktop/overview)永続化オプションは提供されませんが、新しいホストのプロビジョニングとマシンの再展開に使用できるゴールデン Windows イメージを使用する方法を提供します。</span><span class="sxs-lookup"><span data-stu-id="fa51a-113">While [Windows Virtual Desktop](/azure/virtual-desktop/overview) doesn't provide non-persistence options, it does provide ways to use a golden Windows image that can be used to provision new hosts and redeploy machines.</span></span> <span data-ttu-id="fa51a-114">これにより、環境の変動性が高まるため、Microsoft Defender for Endpoint ポータルで作成および管理されるエントリに影響が及び、セキュリティ アナリストの可視性が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa51a-114">This increases volatility in the environment and thus impacts what entries are created and maintained in the Microsoft Defender for Endpoint portal, potentially reducing visibility for your security analysts.</span></span>

> [!NOTE]
> <span data-ttu-id="fa51a-115">オンボーディング方法の選択に応じて、デバイスは次のように Microsoft Defender for Endpoint ポータルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa51a-115">Depending on your choice of onboarding method, devices can appear in Microsoft Defender for Endpoint portal as either:</span></span> 
> - <span data-ttu-id="fa51a-116">仮想デスクトップごとに 1 つのエントリ</span><span class="sxs-lookup"><span data-stu-id="fa51a-116">Single entry for each virtual desktop</span></span> 
> - <span data-ttu-id="fa51a-117">仮想デスクトップごとに複数のエントリ</span><span class="sxs-lookup"><span data-stu-id="fa51a-117">Multiple entries for each virtual desktop</span></span> 

<span data-ttu-id="fa51a-118">Microsoft では、仮想Windows 1 つのエントリとして仮想デスクトップをオンボーディングする方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fa51a-118">Microsoft recommends onboarding Windows Virtual Desktop as a single entry per virtual desktop.</span></span> <span data-ttu-id="fa51a-119">これにより、Microsoft Defender Endpoint ポータルでの調査エクスペリエンスが、コンピューター名に基づいて 1 つのデバイスのコンテキスト内に確実に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa51a-119">This ensures that the investigation experience in the Microsoft Defender Endpoint portal is in the context of one device based on the machine name.</span></span> <span data-ttu-id="fa51a-120">WVD ホストを頻繁に削除および再展開する組織では、同じコンピューターの複数のオブジェクトが Microsoft Defender for Endpoint ポータルに作成されるのを防ぐため、このメソッドの使用を強く検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa51a-120">Organizations that frequently delete and redeploy WVD hosts should strongly consider using this method as it prevents multiple objects for the same machine from being created in the Microsoft Defender for Endpoint portal.</span></span> <span data-ttu-id="fa51a-121">これは、インシデントを調査するときに混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa51a-121">This can lead to confusion when investigating incidents.</span></span> <span data-ttu-id="fa51a-122">テスト環境または非揮発性環境の場合は、別の方法で選択できます。</span><span class="sxs-lookup"><span data-stu-id="fa51a-122">For test or non-volatile environments, you may opt to choose differently.</span></span> 

<span data-ttu-id="fa51a-123">Microsoft では、Microsoft Defender for Endpoint オンボーディング スクリプトを WVD ゴールデン イメージに追加する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fa51a-123">Microsoft recommends adding the Microsoft Defender for Endpoint onboarding script to the WVD golden image.</span></span> <span data-ttu-id="fa51a-124">この方法で、このオンボーディング スクリプトが最初の起動時にすぐに実行されるのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fa51a-124">This way, you can be sure that this onboarding script runs immediately at first boot.</span></span> <span data-ttu-id="fa51a-125">これは、WVD ゴールデン イメージからプロビジョニングされたすべての WVD コンピューターで最初に起動スクリプトとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="fa51a-125">It's executed as a startup script at first boot on all the WVD machines that are provisioned from the WVD golden image.</span></span> <span data-ttu-id="fa51a-126">ただし、変更せずにギャラリー イメージのいずれかを使用している場合は、スクリプトを共有の場所に配置し、ローカル またはドメイン グループ ポリシーから呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fa51a-126">However, if you're using one of the gallery images without modification, place the script in a shared location and call it from either local or domain group policy.</span></span> 

> [!NOTE]
> <span data-ttu-id="fa51a-127">WVD ゴールデン イメージ上の VDI オンボーディングスタートアップ スクリプトの配置と構成によって、WVD の起動時に実行されるスタートアップ スクリプトとして構成されます。</span><span class="sxs-lookup"><span data-stu-id="fa51a-127">The placement and configuration of the VDI onboarding startup script on the WVD golden image configures it as a startup script that runs when the WVD starts.</span></span> <span data-ttu-id="fa51a-128">実際の WVD ゴールデン イメージのオンボードは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="fa51a-128">It's NOT recommended to onboard the actual WVD golden image.</span></span> <span data-ttu-id="fa51a-129">もう 1 つの考慮事項は、スクリプトの実行に使用されるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="fa51a-129">Another consideration is the method used to run the script.</span></span> <span data-ttu-id="fa51a-130">セッションを受信できるコンピューターとサービスへのデバイスオンボーディングの時間を短縮するには、スタートアップ/プロビジョニング プロセスの早い段階で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa51a-130">It should run as early in the startup/provisioning process as possible to reduce the time between the machine being available to receive sessions and the device onboarding to the service.</span></span> <span data-ttu-id="fa51a-131">以下のシナリオ 1 & 2 では、これを考慮します。</span><span class="sxs-lookup"><span data-stu-id="fa51a-131">Below scenarios 1 & 2 take this into account.</span></span>

### <a name="scenarios"></a><span data-ttu-id="fa51a-132">シナリオ</span><span class="sxs-lookup"><span data-stu-id="fa51a-132">Scenarios</span></span>
<span data-ttu-id="fa51a-133">WVD ホスト コンピューターをオンボードする方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fa51a-133">There are several ways to onboard a WVD host machine:</span></span>

- <span data-ttu-id="fa51a-134">起動時に、ゴールデン イメージ (または共有の場所から) でスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa51a-134">Run the script in the golden image (or from a shared location) during startup.</span></span>
- <span data-ttu-id="fa51a-135">管理ツールを使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa51a-135">Use a management tool to run the script.</span></span>

#### <a name="scenario-1-using-local-group-policy"></a><span data-ttu-id="fa51a-136">*シナリオ 1: ローカル グループ ポリシーの使用*</span><span class="sxs-lookup"><span data-stu-id="fa51a-136">*Scenario 1: Using local group policy*</span></span>
<span data-ttu-id="fa51a-137">このシナリオでは、スクリプトをゴールデン イメージに配置する必要があります。ローカル グループ ポリシーを使用して、起動プロセスの早い段階で実行します。</span><span class="sxs-lookup"><span data-stu-id="fa51a-137">This scenario requires placing the script in a golden image and uses local group policy to run early in the boot process.</span></span>

<span data-ttu-id="fa51a-138">「非永続的仮想デスクトップ インフラストラクチャ [(VDI) デバイスのオンボード」の手順を使用します](configure-endpoints-vdi.md#onboard-the-non-persistent-virtual-desktop-infrastructure-vdi-devices)。</span><span class="sxs-lookup"><span data-stu-id="fa51a-138">Use the instructions in [Onboard the non-persistent virtual desktop infrastructure (VDI) devices](configure-endpoints-vdi.md#onboard-the-non-persistent-virtual-desktop-infrastructure-vdi-devices).</span></span>

<span data-ttu-id="fa51a-139">デバイスごとに 1 つのエントリの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="fa51a-139">Follow the instructions for a single entry for each device.</span></span>

#### <a name="scenario-2-using-domain-group-policy"></a><span data-ttu-id="fa51a-140">*シナリオ 2: ドメイン グループ ポリシーの使用*</span><span class="sxs-lookup"><span data-stu-id="fa51a-140">*Scenario 2: Using domain group policy*</span></span>
<span data-ttu-id="fa51a-141">このシナリオでは、中央に位置するスクリプトを使用し、ドメイン ベースのグループ ポリシーを使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="fa51a-141">This scenario uses a centrally located script and runs it using a domain-based group policy.</span></span> <span data-ttu-id="fa51a-142">また、スクリプトをゴールデン イメージに配置し、同じ方法で実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa51a-142">You can also place the script in the golden image and run it in the same way.</span></span>

<span data-ttu-id="fa51a-143">**セキュリティ センターWindowsDefenderATPOnboardingPackage.zipファイルをWindows Defenderする**</span><span class="sxs-lookup"><span data-stu-id="fa51a-143">**Download the WindowsDefenderATPOnboardingPackage.zip file from the Windows Defender Security Center**</span></span>

1. <span data-ttu-id="fa51a-144">VDI 構成パッケージ ファイルを開.zip (WindowsDefenderATPOnboardingPackage.zip)</span><span class="sxs-lookup"><span data-stu-id="fa51a-144">Open the VDI configuration package .zip file (WindowsDefenderATPOnboardingPackage.zip)</span></span>  

    1. <span data-ttu-id="fa51a-145">[新しいMicrosoft Defender セキュリティ センター] ウィンドウで、[オンボーディング]**設定**  >  **選択します**。</span><span class="sxs-lookup"><span data-stu-id="fa51a-145">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Onboarding**.</span></span> 
    1. <span data-ttu-id="fa51a-146">オペレーティング システムWindows 10を選択します。</span><span class="sxs-lookup"><span data-stu-id="fa51a-146">Select Windows 10 as the operating system.</span></span> 
    1. <span data-ttu-id="fa51a-147">[展開方法 **] フィールド** で、永続的でないエンドポイントの VDI オンボーディング スクリプトを選択します。</span><span class="sxs-lookup"><span data-stu-id="fa51a-147">In the **Deployment method** field, select VDI onboarding scripts for non-persistent endpoints.</span></span> 
    1. <span data-ttu-id="fa51a-148">[パッケージ **のダウンロード] を** クリックし、.zip保存します。</span><span class="sxs-lookup"><span data-stu-id="fa51a-148">Click **Download package** and save the .zip file.</span></span> 

2. <span data-ttu-id="fa51a-149">デバイスからアクセスできる.zipファイルの内容を読み取り専用の共有場所に抽出します。</span><span class="sxs-lookup"><span data-stu-id="fa51a-149">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="fa51a-150">**OptionalParamsPolicy** という名前のフォルダーと **、WindowsDefenderATPOnboardingScript.cmd** とファイルが必要 **Onboard-NonPersistentMachine.ps1。**</span><span class="sxs-lookup"><span data-stu-id="fa51a-150">You should have a folder called **OptionalParamsPolicy** and the files **WindowsDefenderATPOnboardingScript.cmd** and **Onboard-NonPersistentMachine.ps1**.</span></span>

<span data-ttu-id="fa51a-151">**グループ ポリシー管理コンソールを使用して、仮想マシンの起動時にスクリプトを実行する**</span><span class="sxs-lookup"><span data-stu-id="fa51a-151">**Use Group Policy management console to run the script when the virtual machine starts**</span></span>

1. <span data-ttu-id="fa51a-152">グループ ポリシー管理コンソール (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="fa51a-152">Open the Group Policy Management Console (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="fa51a-153">グループ ポリシー管理エディターで、[コンピューター構成の基本設定 \> **] コントロール** \> **パネルの設定に移動します**。</span><span class="sxs-lookup"><span data-stu-id="fa51a-153">In the Group Policy Management Editor, go to **Computer configuration** \> **Preferences** \> **Control panel settings**.</span></span> 

3. <span data-ttu-id="fa51a-154">[スケジュールされたタスク **] を右クリック** し、[**新規**] をクリックし、[イ **ミディ** エイト タスク] (少なくとも 7) をWindowsします。</span><span class="sxs-lookup"><span data-stu-id="fa51a-154">Right-click **Scheduled tasks**, click **New**, and then click **Immediate Task** (At least Windows 7).</span></span> 

4. <span data-ttu-id="fa51a-155">開く [タスク] ウィンドウで、[全般] タブ **に移動** します。[セキュリティ **オプション] で、[\*\*\*\*ユーザーまたはグループの変更] をクリックし、「SYSTEM」** と入力します。</span><span class="sxs-lookup"><span data-stu-id="fa51a-155">In the Task window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM.</span></span> <span data-ttu-id="fa51a-156">[名前 **の確認] をクリック** し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fa51a-156">Click **Check Names** and then click OK.</span></span> <span data-ttu-id="fa51a-157">NT AUTHORITY\SYSTEM は、タスクが実行されるユーザー アカウントとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="fa51a-157">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span> 

5. <span data-ttu-id="fa51a-158">[ **ユーザーがログオンするかどうかを実行する] を選択し** 、[最高の特権で実行する **] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="fa51a-158">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span> 

6. <span data-ttu-id="fa51a-159">[操作] タブに **移動し** 、[新規] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="fa51a-159">Go to the **Actions** tab and click **New**.</span></span> <span data-ttu-id="fa51a-160">[アクション **] フィールドで [プログラム** の開始] が選択されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa51a-160">Ensure that **Start a program** is selected in the Action field.</span></span> <span data-ttu-id="fa51a-161">次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="fa51a-161">Enter the following:</span></span> 

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   <span data-ttu-id="fa51a-162">次に **、[OK] を** 選択し、開いている GPMC ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="fa51a-162">Then select **OK** and close any open GPMC windows.</span></span>

#### <a name="scenario-3-onboarding-using-management-tools"></a><span data-ttu-id="fa51a-163">*シナリオ 3: 管理ツールを使用したオンボーディング*</span><span class="sxs-lookup"><span data-stu-id="fa51a-163">*Scenario 3: Onboarding using management tools*</span></span>

<span data-ttu-id="fa51a-164">管理ツールを使用してコンピューターを管理する予定の場合は、デバイスを管理ツールでオンボードMicrosoft Endpoint Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="fa51a-164">If you plan to manage your machines using a management tool, you can onboard devices with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="fa51a-165">詳細については、「Configuration Manager を使用[したオンボード Windows 10デバイス」を参照してください](configure-endpoints-sccm.md)。</span><span class="sxs-lookup"><span data-stu-id="fa51a-165">For more information, see [Onboard Windows 10 devices using Configuration Manager](configure-endpoints-sccm.md).</span></span>

> [!WARNING]
> <span data-ttu-id="fa51a-166">攻撃表面縮小ルールを[](attack-surface-reduction.md)使用する場合は、ルール["PSExec](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)および WMI コマンドから発生するプロセスの作成をブロックする" は使用できません。このルールは、Microsoft Endpoint Configuration Manager による管理と互換性がありません。</span><span class="sxs-lookup"><span data-stu-id="fa51a-166">If you plan to use [Attack Surface reduction Rules](attack-surface-reduction.md), note that the rule “[Block process creations originating from PSExec and WMI commands](attack-surface-reduction.md#block-process-creations-originating-from-psexec-and-wmi-commands)" should not be used, because that rule is incompatible with management through Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="fa51a-167">このルールは、Configuration Manager クライアントが正しく機能するために使用する WMI コマンドをブロックします。</span><span class="sxs-lookup"><span data-stu-id="fa51a-167">The rule blocks WMI commands that the Configuration Manager client uses to function correctly.</span></span> 

> [!TIP]
> <span data-ttu-id="fa51a-168">デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="fa51a-168">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="fa51a-169">詳細については、「新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する [」を参照してください](run-detection-test.md)。</span><span class="sxs-lookup"><span data-stu-id="fa51a-169">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span> 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a><span data-ttu-id="fa51a-170">ゴールデン イメージを作成する際のコンピューターのタグ付け</span><span class="sxs-lookup"><span data-stu-id="fa51a-170">Tagging your machines when building your golden image</span></span> 

<span data-ttu-id="fa51a-171">オンボーディングの一環として、Microsoft セキュリティ センターで WVD マシンを容易に区別できるよう、コンピューター タグの設定を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fa51a-171">As part of your onboarding, you may want to consider setting a machine tag to can differentiate WVD machines more easily in the Microsoft Security Center.</span></span> <span data-ttu-id="fa51a-172">詳細については、「レジストリ キーの [値を設定してデバイス タグを追加する」を参照してください](machine-tags.md#add-device-tags-by-setting-a-registry-key-value)。</span><span class="sxs-lookup"><span data-stu-id="fa51a-172">For more information, see [Add device tags by setting a registry key value](machine-tags.md#add-device-tags-by-setting-a-registry-key-value).</span></span> 

#### <a name="other-recommended-configuration-settings"></a><span data-ttu-id="fa51a-173">その他の推奨構成設定</span><span class="sxs-lookup"><span data-stu-id="fa51a-173">Other recommended configuration settings</span></span> 

<span data-ttu-id="fa51a-174">ゴールデン イメージを作成する場合は、初期保護設定も構成できます。</span><span class="sxs-lookup"><span data-stu-id="fa51a-174">When building your golden image, you may want to configure initial protection settings as well.</span></span> <span data-ttu-id="fa51a-175">詳細については、「その他の推奨 [される構成設定」を参照してください](configure-endpoints-gp.md#other-recommended-configuration-settings)。</span><span class="sxs-lookup"><span data-stu-id="fa51a-175">For more information, see [Other recommended configuration settings](configure-endpoints-gp.md#other-recommended-configuration-settings).</span></span> 

<span data-ttu-id="fa51a-176">また、FSlogix ユーザー プロファイルを使用している場合は、次のファイルを常時保護から除外することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fa51a-176">Also, if you're using FSlogix user profiles, we recommend you exclude the following files from always-on protection:</span></span> 

<span data-ttu-id="fa51a-177">**ファイルの除外:**</span><span class="sxs-lookup"><span data-stu-id="fa51a-177">**Exclude Files:**</span></span> 

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

<span data-ttu-id="fa51a-178">**プロセスを除外する:**</span><span class="sxs-lookup"><span data-stu-id="fa51a-178">**Exclude Processes:**</span></span>

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a><span data-ttu-id="fa51a-179">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="fa51a-179">Licensing requirements</span></span> 

<span data-ttu-id="fa51a-180">ライセンスに関する注意: Windows 10 Enterprise マルチセッションを使用する場合は、要件に応じて、Microsoft Defender for Endpoint (ユーザーあたり)、Windows Enterprise E5、Microsoft 365 Security、または Microsoft 365 E5 を介してすべてのユーザーにライセンスを取得するか、Azure Defender を介して VM のライセンスを取得するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="fa51a-180">Note on licensing: When using Windows 10 Enterprise multi-session, depending on your requirements, you can choose to either have all users licensed through Microsoft Defender for Endpoint (per user), Windows Enterprise E5, Microsoft 365 Security, or Microsoft 365 E5, or have the VM licensed through Azure Defender.</span></span>
<span data-ttu-id="fa51a-181">エンドポイントの Microsoft Defender のライセンス要件については、「ライセンス要件」 [を参照してください](minimum-requirements.md#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="fa51a-181">Licensing requirements for Microsoft Defender for endpoint can be found at: [Licensing requirements](minimum-requirements.md#licensing-requirements).</span></span>

#### <a name="related-links"></a><span data-ttu-id="fa51a-182">関連リンク</span><span class="sxs-lookup"><span data-stu-id="fa51a-182">Related Links</span></span>

[<span data-ttu-id="fa51a-183">PowerShell を使用して Microsoft Defender の除外を追加する</span><span class="sxs-lookup"><span data-stu-id="fa51a-183">Add exclusions for Microsoft Defender by using PowerShell</span></span>](/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#add-exclusions-for-windows-defender-by-using-powershell)
