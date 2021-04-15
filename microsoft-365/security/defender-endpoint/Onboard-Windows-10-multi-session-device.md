---
title: Windows Virtual Desktop の Windows 10 マルチセッション デバイスのオンボード
description: Windows 仮想デスクトップでの Windows 10 マルチセッション デバイスのオンボードに関する記事の詳細
keywords: Windows 仮想デスクトップ、WVD、microsoft Defender、エンドポイント、オンボード
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
ms.openlocfilehash: 6ad61d583815f669affe989d7519ba0ade6fe08d
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760088"
---
# <a name="onboard-windows-10-multi-session-devices-in-windows-virtual-desktop"></a><span data-ttu-id="b4284-104">Windows Virtual Desktop の Windows 10 マルチセッション デバイスのオンボード</span><span class="sxs-lookup"><span data-stu-id="b4284-104">Onboard Windows 10 multi-session devices in Windows Virtual Desktop</span></span> 
<span data-ttu-id="b4284-105">読み取り 6 分</span><span class="sxs-lookup"><span data-stu-id="b4284-105">6 minutes to read</span></span> 

<span data-ttu-id="b4284-106">適用対象:</span><span class="sxs-lookup"><span data-stu-id="b4284-106">Applies to:</span></span> 
- <span data-ttu-id="b4284-107">Windows 仮想デスクトップで実行されている Windows 10 マルチセッション (WVD)</span><span class="sxs-lookup"><span data-stu-id="b4284-107">Windows 10 multi-session running on Windows Virtual Desktop (WVD)</span></span> 

<span data-ttu-id="b4284-108">Microsoft Defender for Endpoint では、VDI セッションと Windows 仮想デスクトップ セッションの両方の監視がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b4284-108">Microsoft Defender for Endpoint supports monitoring both VDI and Windows Virtual Desktop sessions.</span></span> <span data-ttu-id="b4284-109">組織のニーズに応じて、従業員が管理されていないデバイス、リモートの場所、または類似のシナリオから企業データやアプリにアクセスするために、VDI または Windows Virtual Desktop セッションを実装する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="b4284-109">Depending on your organization's needs, you might need to implement VDI or Windows Virtual Desktop sessions to help your employees access corporate data and apps from an unmanaged device, remote location, or similar scenario.</span></span> <span data-ttu-id="b4284-110">Microsoft Defender for Endpoint を使用すると、これらの仮想マシンで異常なアクティビティを監視できます。</span><span class="sxs-lookup"><span data-stu-id="b4284-110">With Microsoft Defender for Endpoint, you can monitor these virtual machines for anomalous activity.</span></span>

 ## <a name="before-you-begin"></a><span data-ttu-id="b4284-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="b4284-111">Before you begin</span></span>
<span data-ttu-id="b4284-112">非永続的な [VDI の考慮事項について理解してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)。</span><span class="sxs-lookup"><span data-stu-id="b4284-112">Familiarize yourself with the [considerations for non-persistent VDI](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span> <span data-ttu-id="b4284-113">[Windows Virtual Desktop には](https://docs.microsoft.com/azure/virtual-desktop/overview)永続性以外のオプションは用意されませんが、新しいホストの準備やマシンの再展開に使用できる、ゴールデン Windows イメージを使用する方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="b4284-113">While [Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview) doesn't provide non-persistence options, it does provide ways to use a golden Windows image that can be used to provision new hosts and redeploy machines.</span></span> <span data-ttu-id="b4284-114">これにより、環境の変動性が高まるため、Microsoft Defender for Endpoint ポータルで作成および管理されるエントリに影響が及び、セキュリティ アナリストの可視性が低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b4284-114">This increases volatility in the environment and thus impacts what entries are created and maintained in the Microsoft Defender for Endpoint portal, potentially reducing visibility for your security analysts.</span></span>

> [!NOTE]
> <span data-ttu-id="b4284-115">オンボーディング方法の選択に応じて、デバイスは次のように Microsoft Defender for Endpoint ポータルに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4284-115">Depending on your choice of onboarding method, devices can appear in Microsoft Defender for Endpoint portal as either:</span></span> 
> - <span data-ttu-id="b4284-116">仮想デスクトップごとに 1 つのエントリ</span><span class="sxs-lookup"><span data-stu-id="b4284-116">Single entry for each virtual desktop</span></span> 
> - <span data-ttu-id="b4284-117">仮想デスクトップごとに複数のエントリ</span><span class="sxs-lookup"><span data-stu-id="b4284-117">Multiple entries for each virtual desktop</span></span> 

<span data-ttu-id="b4284-118">Microsoft では、仮想デスクトップごとに 1 つのエントリとして Windows Virtual Desktop をオンボーディングをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b4284-118">Microsoft recommends onboarding Windows Virtual Desktop as a single entry per virtual desktop.</span></span> <span data-ttu-id="b4284-119">これにより、Microsoft Defender Endpoint ポータルでの調査エクスペリエンスが、コンピューター名に基づいて 1 つのデバイスのコンテキスト内に確実に表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4284-119">This ensures that the investigation experience in the Microsoft Defender Endpoint portal is in the context of one device based on the machine name.</span></span> <span data-ttu-id="b4284-120">WVD ホストを頻繁に削除および再展開する組織では、同じコンピューターの複数のオブジェクトが Microsoft Defender for Endpoint ポータルに作成されるのを防ぐため、このメソッドの使用を強く検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4284-120">Organizations that frequently delete and redeploy WVD hosts should strongly consider using this method as it prevents multiple objects for the same machine from being created in the Microsoft Defender for Endpoint portal.</span></span> <span data-ttu-id="b4284-121">これは、インシデントを調査するときに混乱を招く可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b4284-121">This can lead to confusion when investigating incidents.</span></span> <span data-ttu-id="b4284-122">テスト環境または非揮発性環境の場合は、別の方法で選択できます。</span><span class="sxs-lookup"><span data-stu-id="b4284-122">For test or non-volatile environments, you may opt to choose differently.</span></span> 

<span data-ttu-id="b4284-123">Microsoft では、Microsoft Defender for Endpoint オンボーディング スクリプトを WVD ゴールデン イメージに追加する方法をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b4284-123">Microsoft recommends adding the Microsoft Defender for Endpoint onboarding script to the WVD golden image.</span></span> <span data-ttu-id="b4284-124">この方法で、このオンボーディング スクリプトが最初の起動時にすぐに実行されるのを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b4284-124">This way, you can be sure that this onboarding script runs immediately at first boot.</span></span> <span data-ttu-id="b4284-125">これは、WVD ゴールデン イメージからプロビジョニングされたすべての WVD コンピューターで最初に起動スクリプトとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="b4284-125">It's executed as a startup script at first boot on all the WVD machines that are provisioned from the WVD golden image.</span></span> <span data-ttu-id="b4284-126">ただし、変更せずにギャラリー イメージのいずれかを使用している場合は、スクリプトを共有の場所に配置し、ローカル またはドメイン グループ ポリシーから呼び出します。</span><span class="sxs-lookup"><span data-stu-id="b4284-126">However, if you're using one of the gallery images without modification, place the script in a shared location and call it from either local or domain group policy.</span></span> 

> [!NOTE]
> <span data-ttu-id="b4284-127">WVD ゴールデン イメージ上の VDI オンボーディングスタートアップ スクリプトの配置と構成によって、WVD の起動時に実行されるスタートアップ スクリプトとして構成されます。</span><span class="sxs-lookup"><span data-stu-id="b4284-127">The placement and configuration of the VDI onboarding startup script on the WVD golden image configures it as a startup script that runs when the WVD starts.</span></span> <span data-ttu-id="b4284-128">実際の WVD ゴールデン イメージのオンボードは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="b4284-128">It's NOT recommended to onboard the actual WVD golden image.</span></span> <span data-ttu-id="b4284-129">もう 1 つの考慮事項は、スクリプトの実行に使用されるメソッドです。</span><span class="sxs-lookup"><span data-stu-id="b4284-129">Another consideration is the method used to run the script.</span></span> <span data-ttu-id="b4284-130">セッションを受信できるコンピューターとサービスへのデバイスオンボーディングの時間を短縮するには、スタートアップ/プロビジョニング プロセスの早い段階で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4284-130">It should run as early in the startup/provisioning process as possible to reduce the time between the machine being available to receive sessions and the device onboarding to the service.</span></span> <span data-ttu-id="b4284-131">以下のシナリオ 1 & 2 では、これを考慮します。</span><span class="sxs-lookup"><span data-stu-id="b4284-131">Below scenarios 1 & 2 take this into account.</span></span>

### <a name="scenarios"></a><span data-ttu-id="b4284-132">シナリオ</span><span class="sxs-lookup"><span data-stu-id="b4284-132">Scenarios</span></span>
<span data-ttu-id="b4284-133">WVD ホスト コンピューターをオンボードする方法は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="b4284-133">There are several ways to onboard a WVD host machine:</span></span>

- <span data-ttu-id="b4284-134">起動時に、ゴールデン イメージ (または共有の場所から) でスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4284-134">Run the script in the golden image (or from a shared location) during startup.</span></span>
- <span data-ttu-id="b4284-135">管理ツールを使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4284-135">Use a management tool to run the script.</span></span>

#### <a name="scenario-1-using-local-group-policy"></a><span data-ttu-id="b4284-136">*シナリオ 1: ローカル グループ ポリシーの使用*</span><span class="sxs-lookup"><span data-stu-id="b4284-136">*Scenario 1: Using local group policy*</span></span>
<span data-ttu-id="b4284-137">このシナリオでは、スクリプトをゴールデン イメージに配置する必要があります。ローカル グループ ポリシーを使用して、起動プロセスの早い段階で実行します。</span><span class="sxs-lookup"><span data-stu-id="b4284-137">This scenario requires placing the script in a golden image and uses local group policy to run early in the boot process.</span></span>

<span data-ttu-id="b4284-138">「非永続的な仮想デスクトップ インフラストラクチャ VDI デバイスのオンボード [」の手順を使用します](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)。</span><span class="sxs-lookup"><span data-stu-id="b4284-138">Use the instructions in [Onboard non-persistent virtual desktop infrastructure VDI devices](configure-endpoints-vdi.md#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1).</span></span>

<span data-ttu-id="b4284-139">デバイスごとに 1 つのエントリの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="b4284-139">Follow the instructions for a single entry for each device.</span></span>

#### <a name="scenario-2-using-domain-group-policy"></a><span data-ttu-id="b4284-140">*シナリオ 2: ドメイン グループ ポリシーの使用*</span><span class="sxs-lookup"><span data-stu-id="b4284-140">*Scenario 2: Using domain group policy*</span></span>
<span data-ttu-id="b4284-141">このシナリオでは、中央に位置するスクリプトを使用し、ドメイン ベースのグループ ポリシーを使用してスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="b4284-141">This scenario uses a centrally located script and runs it using a domain-based group policy.</span></span> <span data-ttu-id="b4284-142">また、スクリプトをゴールデン イメージに配置し、同じ方法で実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="b4284-142">You can also place the script in the golden image and run it in the same way.</span></span>

<span data-ttu-id="b4284-143">**セキュリティ センターWindowsDefenderATPOnboardingPackage.zipファイルをWindows Defenderする**</span><span class="sxs-lookup"><span data-stu-id="b4284-143">**Download the WindowsDefenderATPOnboardingPackage.zip file from the Windows Defender Security Center**</span></span>

1. <span data-ttu-id="b4284-144">VDI 構成パッケージ .zip ファイルを開きます (WindowsDefenderATPOnboardingPackage.zip)</span><span class="sxs-lookup"><span data-stu-id="b4284-144">Open the VDI configuration package .zip file (WindowsDefenderATPOnboardingPackage.zip)</span></span>  

    1. <span data-ttu-id="b4284-145">Microsoft Defender セキュリティ センター ナビゲーションウィンドウで、[設定オンボード]  >  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="b4284-145">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Onboarding**.</span></span> 
    1. <span data-ttu-id="b4284-146">オペレーティング システムとして [Windows 10] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b4284-146">Select Windows 10 as the operating system.</span></span> 
    1. <span data-ttu-id="b4284-147">[展開方法 **] フィールド** で、永続的でないエンドポイントの VDI オンボーディング スクリプトを選択します。</span><span class="sxs-lookup"><span data-stu-id="b4284-147">In the **Deployment method** field, select VDI onboarding scripts for non-persistent endpoints.</span></span> 
    1. <span data-ttu-id="b4284-148">[パッケージ **のダウンロード] を** クリックし、.zip ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="b4284-148">Click **Download package** and save the .zip file.</span></span> 

2. <span data-ttu-id="b4284-149">.zip ファイルの内容を、デバイスがアクセスできる共有の読み取り専用の場所に展開します。</span><span class="sxs-lookup"><span data-stu-id="b4284-149">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the device.</span></span> <span data-ttu-id="b4284-150">**OptionalParamsPolicy** という名前のフォルダーと **、WindowsDefenderATPOnboardingScript.cmd** とファイルが必要 **Onboard-NonPersistentMachine.ps1。**</span><span class="sxs-lookup"><span data-stu-id="b4284-150">You should have a folder called **OptionalParamsPolicy** and the files **WindowsDefenderATPOnboardingScript.cmd** and **Onboard-NonPersistentMachine.ps1**.</span></span>

<span data-ttu-id="b4284-151">**グループ ポリシー管理コンソールを使用して、仮想マシンの起動時にスクリプトを実行する**</span><span class="sxs-lookup"><span data-stu-id="b4284-151">**Use Group Policy management console to run the script when the virtual machine starts**</span></span>

1. <span data-ttu-id="b4284-152">グループ ポリシー管理コンソール (GPMC) を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b4284-152">Open the Group Policy Management Console (GPMC), right-click the Group Policy Object (GPO) you want to configure and click **Edit**.</span></span>

1. <span data-ttu-id="b4284-153">グループ ポリシー管理エディターで、[コンピューター構成の基本設定 \> **] コントロール** \> **パネルの設定に移動します**。</span><span class="sxs-lookup"><span data-stu-id="b4284-153">In the Group Policy Management Editor, go to **Computer configuration** \> **Preferences** \> **Control panel settings**.</span></span> 

1. <span data-ttu-id="b4284-154">[スケジュールされたタスク **] を右クリックし**、[ **新規**] をクリックし、[ **イミディエイ** ト タスク] (少なくとも Windows 7) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4284-154">Right-click **Scheduled tasks**, click **New**, and then click **Immediate Task** (At least Windows 7).</span></span> 

1. <span data-ttu-id="b4284-155">開く [タスク] ウィンドウで、[全般] タブ **に移動** します。[セキュリティ **オプション] で、[\*\*\*\*ユーザーまたはグループの変更] をクリックし、「SYSTEM」** と入力します。</span><span class="sxs-lookup"><span data-stu-id="b4284-155">In the Task window that opens, go to the **General** tab. Under **Security options** click **Change User or Group** and type SYSTEM.</span></span> <span data-ttu-id="b4284-156">[名前 **の確認] をクリック** し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b4284-156">Click **Check Names** and then click OK.</span></span> <span data-ttu-id="b4284-157">NT AUTHORITY\SYSTEM は、タスクが実行されるユーザー アカウントとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="b4284-157">NT AUTHORITY\SYSTEM appears as the user account the task will run as.</span></span> 

1. <span data-ttu-id="b4284-158">[ **ユーザーがログオンするかどうかを実行する] を選択し** 、[最高の特権で実行する **] チェック ボックスを** オンにします。</span><span class="sxs-lookup"><span data-stu-id="b4284-158">Select **Run whether user is logged on or not** and check the **Run with highest privileges** check box.</span></span> 

1. <span data-ttu-id="b4284-159">[操作] タブに **移動し** 、[新規] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="b4284-159">Go to the **Actions** tab and click **New**.</span></span> <span data-ttu-id="b4284-160">[アクション **] フィールドで [プログラム** の開始] が選択されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4284-160">Ensure that **Start a program** is selected in the Action field.</span></span> <span data-ttu-id="b4284-161">次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="b4284-161">Enter the following:</span></span> 

    > <span data-ttu-id="b4284-162">Action = "プログラムの開始"</span><span class="sxs-lookup"><span data-stu-id="b4284-162">Action = "Start a program"</span></span> <br>
    > <span data-ttu-id="b4284-163">Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe</span><span class="sxs-lookup"><span data-stu-id="b4284-163">Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe</span></span> <br>
    > <span data-ttu-id="b4284-164">引数の追加 (省略可能) = -ExecutionPolicy Bypass -command \\ "&Path\To\Onboard-NonPersistentMachine.ps1"</span><span class="sxs-lookup"><span data-stu-id="b4284-164">Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"</span></span>

1. <span data-ttu-id="b4284-165">**[OK] を** クリックし、開いている GPMC ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b4284-165">Click **OK** and close any open GPMC windows.</span></span>

#### <a name="scenario-3-onboarding-using-management-tools"></a><span data-ttu-id="b4284-166">*シナリオ 3: 管理ツールを使用したオンボーディング*</span><span class="sxs-lookup"><span data-stu-id="b4284-166">*Scenario 3: Onboarding using management tools*</span></span>

<span data-ttu-id="b4284-167">管理ツールを使用してコンピューターを管理する場合は、Microsoft Endpoint Configuration Manager を使用してデバイスをオンボードできます。</span><span class="sxs-lookup"><span data-stu-id="b4284-167">If you plan to manage your machines using a management tool, you can onboard devices with Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="b4284-168">詳細については、「Configuration Manager を使用 [したオンボード Windows 10 デバイス」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)。</span><span class="sxs-lookup"><span data-stu-id="b4284-168">For more information, see [Onboard Windows 10 devices using Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm).</span></span> 

> [!WARNING]
> <span data-ttu-id="b4284-169">攻撃表面縮小ルールを使用する場合は、Configuration [Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)クライアントが正しく機能するために使用する WMI コマンドをブロックしますので[、"PSExec](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)コマンドおよび WMI コマンドから発生するプロセス作成をブロックする" というルールは、Microsoft Endpoint Configuration Manager による管理と互換性がないので使用できません。</span><span class="sxs-lookup"><span data-stu-id="b4284-169">If you plan to use [Attack Surface reduction Rules](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction), please note that rule “[Block process creations originating from PSExec and WMI commands](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)" should not be used as it is incompatible with management through Microsoft Endpoint Configuration Manager because this rule blocks WMI commands the Configuration Manager client uses to function correctly.</span></span> 

> [!TIP]
> <span data-ttu-id="b4284-170">デバイスのオンボード後、検出テストを実行して、デバイスがサービスに適切にオンボードされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="b4284-170">After onboarding the device, you can choose to run a detection test to verify that the device is properly onboarded to the service.</span></span> <span data-ttu-id="b4284-171">詳細については、「新しくオンボードされた Microsoft Defender for Endpoint デバイスで検出テストを実行する [」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test)。</span><span class="sxs-lookup"><span data-stu-id="b4284-171">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test).</span></span> 

#### <a name="tagging-your-machines-when-building-your-golden-image"></a><span data-ttu-id="b4284-172">ゴールデン イメージを作成する際のコンピューターのタグ付け</span><span class="sxs-lookup"><span data-stu-id="b4284-172">Tagging your machines when building your golden image</span></span> 

<span data-ttu-id="b4284-173">オンボーディングの一環として、Microsoft セキュリティ センターで WVD マシンを容易に区別できるよう、コンピューター タグの設定を検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b4284-173">As part of your onboarding, you may want to consider setting a machine tag to can differentiate WVD machines more easily in the Microsoft Security Center.</span></span> <span data-ttu-id="b4284-174">詳細については、「レジストリ キーの [値を設定してデバイス タグを追加する」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags#add-device-tags-by-setting-a-registry-key-value)。</span><span class="sxs-lookup"><span data-stu-id="b4284-174">For more information, see [Add device tags by setting a registry key value](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-tags#add-device-tags-by-setting-a-registry-key-value).</span></span> 

#### <a name="other-recommended-configuration-settings"></a><span data-ttu-id="b4284-175">その他の推奨構成設定</span><span class="sxs-lookup"><span data-stu-id="b4284-175">Other recommended configuration settings</span></span> 

<span data-ttu-id="b4284-176">ゴールデン イメージを作成する場合は、初期保護設定も構成できます。</span><span class="sxs-lookup"><span data-stu-id="b4284-176">When building your golden image, you may want to configure initial protection settings as well.</span></span> <span data-ttu-id="b4284-177">詳細については、「その他の推奨 [される構成設定」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp#other-recommended-configuration-settings)。</span><span class="sxs-lookup"><span data-stu-id="b4284-177">For more information, see [Other recommended configuration settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp#other-recommended-configuration-settings).</span></span> 

<span data-ttu-id="b4284-178">また、FSlogix ユーザー プロファイルを使用している場合は、次のファイルを常時保護から除外することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b4284-178">Also, if you're using FSlogix user profiles, we recommend you exclude the following files from always-on protection:</span></span> 

<span data-ttu-id="b4284-179">**ファイルの除外:**</span><span class="sxs-lookup"><span data-stu-id="b4284-179">**Exclude Files:**</span></span> 

> <span data-ttu-id="b4284-180">%ProgramFiles%\FSLogix\Apps\frxdrv.sys</span><span class="sxs-lookup"><span data-stu-id="b4284-180">%ProgramFiles%\FSLogix\Apps\frxdrv.sys</span></span> <br>
> <span data-ttu-id="b4284-181">%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys</span><span class="sxs-lookup"><span data-stu-id="b4284-181">%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys</span></span> <br>
> <span data-ttu-id="b4284-182">%ProgramFiles%\FSLogix\Apps\frxccd.sys</span><span class="sxs-lookup"><span data-stu-id="b4284-182">%ProgramFiles%\FSLogix\Apps\frxccd.sys</span></span> <br>
> <span data-ttu-id="b4284-183">%TEMP% \* .VHD</span><span class="sxs-lookup"><span data-stu-id="b4284-183">%TEMP%\*.VHD</span></span> <br>
> <span data-ttu-id="b4284-184">%TEMP% \* .VHDX</span><span class="sxs-lookup"><span data-stu-id="b4284-184">%TEMP%\*.VHDX</span></span> <br>
> <span data-ttu-id="b4284-185">%Windir%\TEMP \* .VHD</span><span class="sxs-lookup"><span data-stu-id="b4284-185">%Windir%\TEMP\*.VHD</span></span> <br>
> <span data-ttu-id="b4284-186">%Windir%\TEMP \* .VHDX</span><span class="sxs-lookup"><span data-stu-id="b4284-186">%Windir%\TEMP\*.VHDX</span></span> <br>
> <span data-ttu-id="b4284-187">\\storageaccount.file.core.windows.net\share \* \* .VHD</span><span class="sxs-lookup"><span data-stu-id="b4284-187">\\storageaccount.file.core.windows.net\share\*\*.VHD</span></span> <br>
> <span data-ttu-id="b4284-188">\\storageaccount.file.core.windows.net\share \* \* .VHDX</span><span class="sxs-lookup"><span data-stu-id="b4284-188">\\storageaccount.file.core.windows.net\share\*\*.VHDX</span></span> <br>

<span data-ttu-id="b4284-189">**プロセスを除外する:**</span><span class="sxs-lookup"><span data-stu-id="b4284-189">**Exclude Processes:**</span></span>

> <span data-ttu-id="b4284-190">%ProgramFiles%\FSLogix\Apps\frxccd.exe</span><span class="sxs-lookup"><span data-stu-id="b4284-190">%ProgramFiles%\FSLogix\Apps\frxccd.exe</span></span> <br>
> <span data-ttu-id="b4284-191">%ProgramFiles%\FSLogix\Apps\frxccds.exe</span><span class="sxs-lookup"><span data-stu-id="b4284-191">%ProgramFiles%\FSLogix\Apps\frxccds.exe</span></span> <br>
> <span data-ttu-id="b4284-192">%ProgramFiles%\FSLogix\Apps\frxsvc.exe</span><span class="sxs-lookup"><span data-stu-id="b4284-192">%ProgramFiles%\FSLogix\Apps\frxsvc.exe</span></span> <br>

#### <a name="licensing-requirements"></a><span data-ttu-id="b4284-193">ライセンスの要件</span><span class="sxs-lookup"><span data-stu-id="b4284-193">Licensing requirements</span></span> 

<span data-ttu-id="b4284-194">Windows 10 マルチセッションはクライアント OS です。</span><span class="sxs-lookup"><span data-stu-id="b4284-194">Windows 10 Multi-session is a client OS.</span></span> <span data-ttu-id="b4284-195">エンドポイントの Microsoft Defender のライセンス要件については、「ライセンス要件」 [を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。</span><span class="sxs-lookup"><span data-stu-id="b4284-195">Licensing requirements for Microsoft Defender for endpoint can be found at: [Licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements).</span></span>
