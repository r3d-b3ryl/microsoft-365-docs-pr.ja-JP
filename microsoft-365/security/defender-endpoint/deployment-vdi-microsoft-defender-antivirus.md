---
title: Microsoft Defender ウイルス対策仮想デスクトップ インフラストラクチャの展開ガイド
description: 仮想デスクトップ環境にMicrosoft Defender ウイルス対策、保護とパフォーマンスの最適なバランスを保つ方法について説明します。
keywords: vdi、hyper-v、vm、仮想マシン、Windows Defender、ウイルス対策、av、仮想デスクトップ、rds、リモート デスクトップ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: jesquive
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4ecd14e055646804d81e22da7c192988cf1e6f6f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275254"
---
# <a name="deployment-guide-for-microsoft-defender-antivirus-in-a-virtual-desktop-infrastructure-vdi-environment"></a><span data-ttu-id="f565a-104">仮想デスクトップ インフラストラクチャ (VDI) 環境での Microsoft Defender ウイルス対策の展開ガイド</span><span class="sxs-lookup"><span data-stu-id="f565a-104">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f565a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f565a-105">**Applies to:**</span></span>

- [<span data-ttu-id="f565a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f565a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f565a-107">標準のオンプレミスまたはハードウェア構成に加えて、リモート デスクトップ (RDS) または仮想デスクトップ インフラストラクチャ (VDI) 環境でも Microsoft Defender ウイルス対策 を使用できます。</span><span class="sxs-lookup"><span data-stu-id="f565a-107">In addition to standard on-premises or hardware configurations, you can also use Microsoft Defender Antivirus in a remote desktop (RDS) or virtual desktop infrastructure (VDI) environment.</span></span>

<span data-ttu-id="f565a-108">サービス[Windows VDI サポート](/azure/virtual-desktop)の詳細については、「仮想デスクトップ のドキュメントMicrosoft リモート デスクトップ参照してください。</span><span class="sxs-lookup"><span data-stu-id="f565a-108">See [Windows Virtual Desktop Documentation](/azure/virtual-desktop) for more details on Microsoft Remote Desktop Services and VDI support.</span></span>

<span data-ttu-id="f565a-109">Azure ベースの仮想マシンについては[、「Install Endpoint Protection In Azure Defender」を参照してください](/azure/security-center/security-center-install-endpoint-protection)。</span><span class="sxs-lookup"><span data-stu-id="f565a-109">For Azure-based virtual machines, see [Install Endpoint Protection in Azure Defender](/azure/security-center/security-center-install-endpoint-protection).</span></span>

<span data-ttu-id="f565a-110">VDIs で実行されている VM に更新プログラムを簡単に展開する機能により、このガイドを短縮して、コンピューターの更新プログラムをすばやく簡単に取得する方法に焦点を当ててください。</span><span class="sxs-lookup"><span data-stu-id="f565a-110">With the ability to easily deploy updates to VMs running in VDIs, we've shortened this guide to focus on how you can get updates on your machines quickly and easily.</span></span> <span data-ttu-id="f565a-111">更新プログラムはホスト サーバー上のコンポーネント ビットに展開され、有効になったときに VM に直接ダウンロードされるので、定期的にゴールデン イメージを作成してシールする必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="f565a-111">You no longer need to create and seal golden images on a periodic basis, as updates are expanded into their component bits on the host server and then downloaded directly to the VM when it's turned on.</span></span>

<span data-ttu-id="f565a-112">このガイドでは、最適な保護とパフォーマンスを実現するために VM を構成する方法について説明します。これには、次の方法が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f565a-112">This guide describes how to configure your VMs for optimal protection and performance, including how to:</span></span>

- [<span data-ttu-id="f565a-113">セキュリティ インテリジェンス更新プログラム用に専用の VDI ファイル共有をセットアップする</span><span class="sxs-lookup"><span data-stu-id="f565a-113">Set up a dedicated VDI file share for security intelligence updates</span></span>](#set-up-a-dedicated-vdi-file-share)
- [<span data-ttu-id="f565a-114">スケジュールされたスキャンをランダム化する</span><span class="sxs-lookup"><span data-stu-id="f565a-114">Randomize scheduled scans</span></span>](#randomize-scheduled-scans)
- [<span data-ttu-id="f565a-115">クイック スキャンの使用</span><span class="sxs-lookup"><span data-stu-id="f565a-115">Use quick scans</span></span>](#use-quick-scans)
- [<span data-ttu-id="f565a-116">通知を防止する</span><span class="sxs-lookup"><span data-stu-id="f565a-116">Prevent notifications</span></span>](#prevent-notifications)
- [<span data-ttu-id="f565a-117">更新後にスキャンを無効にする</span><span class="sxs-lookup"><span data-stu-id="f565a-117">Disable scans from occurring after every update</span></span>](#disable-scans-after-an-update)
- [<span data-ttu-id="f565a-118">しばらくオフラインだった古いコンピューターまたはコンピューターをスキャンする</span><span class="sxs-lookup"><span data-stu-id="f565a-118">Scan out-of-date machines or machines that have been offline for a while</span></span>](#scan-vms-that-have-been-offline)
- [<span data-ttu-id="f565a-119">除外を適用する</span><span class="sxs-lookup"><span data-stu-id="f565a-119">Apply exclusions</span></span>](#exclusions)

<span data-ttu-id="f565a-120">また、新しい共有セキュリティ インテリジェンス更新機能を参照する仮想デスクトップ インフラストラクチャのホワイトペーパー [Microsoft Defender ウイルス対策](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf)をダウンロードし、独自の VDI でウイルス対策のパフォーマンスをテストする方法に関するパフォーマンス テストとガイダンスを参照できます。</span><span class="sxs-lookup"><span data-stu-id="f565a-120">You can also download the whitepaper [Microsoft Defender Antivirus on Virtual Desktop Infrastructure](https://demo.wd.microsoft.com/Content/wdav-testing-vdi-ssu.pdf), which looks at the new shared security intelligence update feature, alongside performance testing and guidance on how you can test antivirus performance on your own VDI.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f565a-121">VDI は Windows Server 2012 または Windows Server 2016 でホストすることができますが、以前のバージョンの Windows では使用できない保護テクノロジと機能が強化されたので、仮想マシン (VM) は少なくとも 1607 の Windows 10 を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f565a-121">Although the VDI can be hosted on Windows Server 2012 or Windows Server 2016, the virtual machines (VMs) should be running Windows 10, 1607 at a minimum, due to increased protection technologies and features that are unavailable in earlier versions of Windows.</span></span><br/><span data-ttu-id="f565a-122">microsoft Defender AV が Windows 10 Insider Preview の仮想マシンで動作する方法には、パフォーマンスと機能の改善点があります。ビルド 18323 (以降)。</span><span class="sxs-lookup"><span data-stu-id="f565a-122">There are performance and feature improvements to the way in which Microsoft Defender AV operates on virtual machines in Windows 10 Insider Preview, build 18323 (and later).</span></span> <span data-ttu-id="f565a-123">Insider Preview ビルドを使用する必要がある場合は、このガイドで確認します。指定されていない場合、最適な保護とパフォーマンスを実現するために必要な最小バージョンは 1607 Windows 10です。</span><span class="sxs-lookup"><span data-stu-id="f565a-123">We'll identify in this guide if you need to be using an Insider Preview build; if it isn't specified, then the minimum required version for the best protection and performance is Windows 10 1607.</span></span>

## <a name="set-up-a-dedicated-vdi-file-share"></a><span data-ttu-id="f565a-124">専用の VDI ファイル共有をセットアップする</span><span class="sxs-lookup"><span data-stu-id="f565a-124">Set up a dedicated VDI file share</span></span>

<span data-ttu-id="f565a-125">Windows 10 バージョン 1903 では、共有セキュリティ インテリジェンス機能が導入され、ダウンロードしたセキュリティ インテリジェンス更新プログラムのアンパック処理がホスト コンピューターにオフロードされ、以前の CPU、ディスク、メモリ リソースが個々のコンピューターに保存されました。</span><span class="sxs-lookup"><span data-stu-id="f565a-125">In Windows 10, version 1903, we introduced the shared security intelligence feature, which offloads the unpackaging of downloaded security intelligence updates onto a host machine—thus saving previous CPU, disk, and memory resources on individual machines.</span></span> <span data-ttu-id="f565a-126">この機能はバックポートされ、バージョン 1703 Windows 10で動作します。</span><span class="sxs-lookup"><span data-stu-id="f565a-126">This feature has been backported and now works in Windows 10 version 1703 and above.</span></span> <span data-ttu-id="f565a-127">この機能は、グループ ポリシーまたは PowerShell で設定できます。</span><span class="sxs-lookup"><span data-stu-id="f565a-127">You can set this feature with a Group Policy, or PowerShell.</span></span>

### <a name="use-group-policy-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="f565a-128">グループ ポリシーを使用して、共有セキュリティ インテリジェンス機能を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f565a-128">Use Group Policy to enable the shared security intelligence feature:</span></span>

1. <span data-ttu-id="f565a-129">グループ ポリシー管理コンピューターで、グループ ポリシー管理コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-129">On your Group Policy management computer, open the Group Policy Management Console, right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="f565a-130">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-130">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="f565a-131">[管理 **用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="f565a-131">Click **Administrative templates**.</span></span>

4. <span data-ttu-id="f565a-132">ツリーを展開して、**セキュリティ Windows更新**  >  **Microsoft Defender ウイルス対策**  >  **コンポーネントを展開します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-132">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="f565a-133">[VDI クライアント **のセキュリティ インテリジェンスの場所** を定義する] をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-133">Double-click **Define security intelligence location for VDI clients**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="f565a-134">フィールドが自動的に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f565a-134">A field automatically appears.</span></span>

6. <span data-ttu-id="f565a-135">Enter `\\<sharedlocation\>\wdav-update` (この値のヘルプについては、「ダウンロードとアンパック [」を参照してください](#download-and-unpackage-the-latest-updates))。</span><span class="sxs-lookup"><span data-stu-id="f565a-135">Enter `\\<sharedlocation\>\wdav-update` (for help with this value, see [Download and unpackage](#download-and-unpackage-the-latest-updates)).</span></span>

7. <span data-ttu-id="f565a-136">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f565a-136">Click **OK**.</span></span>

8. <span data-ttu-id="f565a-137">テストする VM に GPO を展開します。</span><span class="sxs-lookup"><span data-stu-id="f565a-137">Deploy the GPO to the VMs you want to test.</span></span>

### <a name="use-powershell-to-enable-the-shared-security-intelligence-feature"></a><span data-ttu-id="f565a-138">PowerShell を使用して共有セキュリティ インテリジェンス機能を有効にする</span><span class="sxs-lookup"><span data-stu-id="f565a-138">Use PowerShell to enable the shared security intelligence feature</span></span>

<span data-ttu-id="f565a-139">この機能を有効にするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f565a-139">Use the following cmdlet to enable the feature.</span></span> <span data-ttu-id="f565a-140">通常、PowerShell ベースの構成ポリシーを VM にプッシュする場合は、これをプッシュする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f565a-140">You’ll need to then push this as you normally would push PowerShell-based configuration policies onto the VMs:</span></span>

```PowerShell
Set-MpPreference -SharedSignaturesPath \\<shared location>\wdav-update
```

<span data-ttu-id="f565a-141">詳細については [、「ダウンロードとアンパック](#download-and-unpackage-the-latest-updates) 」セクション \<shared location\> を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f565a-141">See the [Download and unpackage](#download-and-unpackage-the-latest-updates) section for what the \<shared location\> will be.</span></span>

## <a name="download-and-unpackage-the-latest-updates"></a><span data-ttu-id="f565a-142">最新の更新プログラムをダウンロードして開梱する</span><span class="sxs-lookup"><span data-stu-id="f565a-142">Download and unpackage the latest updates</span></span>

<span data-ttu-id="f565a-143">これで、新しい更新プログラムのダウンロードとインストールを開始できます。</span><span class="sxs-lookup"><span data-stu-id="f565a-143">Now you can get started on downloading and installing new updates.</span></span> <span data-ttu-id="f565a-144">以下に、サンプルの PowerShell スクリプトを作成しました。</span><span class="sxs-lookup"><span data-stu-id="f565a-144">We’ve created a sample PowerShell script for you below.</span></span> <span data-ttu-id="f565a-145">このスクリプトは、新しい更新プログラムをダウンロードして VM の準備を整える最も簡単な方法です。</span><span class="sxs-lookup"><span data-stu-id="f565a-145">This script is the easiest way to download new updates and get them ready for your VMs.</span></span> <span data-ttu-id="f565a-146">その後、スケジュールされたタスクを使用して管理マシン上で一定の時間に実行するようにスクリプトを設定する必要があります (または、Azure、Intune、または SCCM で PowerShell スクリプトを使用する場合は、これらのスクリプトを使用することもできます)。</span><span class="sxs-lookup"><span data-stu-id="f565a-146">You should then set the script to run at a certain time on the management machine by using a scheduled task (or, if you’re familiar with using PowerShell scripts in Azure, Intune, or SCCM, you could also use those scripts).</span></span>

```PowerShell
$vdmpathbase = "$env:systemdrive\wdav-update\{00000000-0000-0000-0000-"
$vdmpathtime = Get-Date -format "yMMddHHmmss"
$vdmpath = $vdmpathbase + $vdmpathtime + '}'
$vdmpackage = $vdmpath + '\mpam-fe.exe'

New-Item -ItemType Directory -Force -Path $vdmpath | Out-Null

Invoke-WebRequest -Uri 'https://go.microsoft.com/fwlink/?LinkID=121721&arch=x64' -OutFile $vdmpackage

cmd /c "cd $vdmpath & c: & mpam-fe.exe /x"
```

<span data-ttu-id="f565a-147">スケジュールされたタスクを 1 日 1 回実行して、パッケージをダウンロードして開梱するたびに VM が新しい更新プログラムを受け取るのを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f565a-147">You can set a scheduled task to run once a day so that whenever the package is downloaded and unpacked then the VMs will receive the new update.</span></span> <span data-ttu-id="f565a-148">1 日 1 回から始める方法をお勧めしますが、影響を理解するために頻度を増やしたり減らしたりして試す必要があります。</span><span class="sxs-lookup"><span data-stu-id="f565a-148">We suggest starting with once a day—but you should experiment with increasing or decreasing the frequency to understand the impact.</span></span> 

<span data-ttu-id="f565a-149">通常、セキュリティ インテリジェンス パッケージは 3 ~ 4 時間に 1 回発行されます。</span><span class="sxs-lookup"><span data-stu-id="f565a-149">Security intelligence packages are typically published once every three to four hours.</span></span> <span data-ttu-id="f565a-150">頻度を 4 時間より短く設定すると、管理マシンのネットワーク オーバーヘッドが増加し、利益が得らないのでお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="f565a-150">Setting a frequency shorter than four hours isn’t advised because it will increase the network overhead on your management machine for no benefit.</span></span>

### <a name="set-a-scheduled-task-to-run-the-powershell-script"></a><span data-ttu-id="f565a-151">PowerShell スクリプトを実行するスケジュールされたタスクを設定する</span><span class="sxs-lookup"><span data-stu-id="f565a-151">Set a scheduled task to run the PowerShell script</span></span>

1. <span data-ttu-id="f565a-152">管理マシンで、[スタート] メニューを開き、[タスク スケジューラ] **と入力します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-152">On the management machine, open the Start menu and type **Task Scheduler**.</span></span> <span data-ttu-id="f565a-153">それを開き、[タスクの **作成...] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="f565a-153">Open it and select **Create task…**</span></span> <span data-ttu-id="f565a-154">をサイド パネルに表示します。</span><span class="sxs-lookup"><span data-stu-id="f565a-154">on the side panel.</span></span>

2. <span data-ttu-id="f565a-155">名前をセキュリティ インテリジェンス **アンパックとして入力します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-155">Enter the name as **Security intelligence unpacker**.</span></span> <span data-ttu-id="f565a-156">[トリガー] タブ **に移動** します。[ **新規...] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="f565a-156">Go to the **Trigger** tab. Select **New…**</span></span><span data-ttu-id="f565a-157"> > **[日**] を選択し **、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-157"> > **Daily**, and select **OK**.</span></span>

3. <span data-ttu-id="f565a-158">[操作] タブ **に移動** します。[ **新規...] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="f565a-158">Go to the **Actions** tab. Select **New…**</span></span> <span data-ttu-id="f565a-159">[ **プログラム/スクリプト]** フィールドに **「PowerShell」と入力** します。</span><span class="sxs-lookup"><span data-stu-id="f565a-159">Enter **PowerShell** in the **Program/Script** field.</span></span> <span data-ttu-id="f565a-160">[ `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` 引数の追加 **] フィールドに入力** します。</span><span class="sxs-lookup"><span data-stu-id="f565a-160">Enter `-ExecutionPolicy Bypass c:\wdav-update\vdmdlunpack.ps1` in the **Add arguments** field.</span></span> <span data-ttu-id="f565a-161">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f565a-161">Select **OK**.</span></span>

4. <span data-ttu-id="f565a-162">必要に応じて、追加の設定を構成できます。</span><span class="sxs-lookup"><span data-stu-id="f565a-162">You can choose to configure additional settings if you wish.</span></span>

5. <span data-ttu-id="f565a-163">**[OK] を** 選択して、スケジュールされたタスクを保存します。</span><span class="sxs-lookup"><span data-stu-id="f565a-163">Select **OK** to save the scheduled task.</span></span>
 
<span data-ttu-id="f565a-164">タスクを右クリックして [実行] をクリックすると、手動で更新を開始 **できます**。</span><span class="sxs-lookup"><span data-stu-id="f565a-164">You can initiate the update manually by right-clicking on the task and clicking **Run**.</span></span>

### <a name="download-and-unpackage-manually"></a><span data-ttu-id="f565a-165">手動でダウンロードして開梱する</span><span class="sxs-lookup"><span data-stu-id="f565a-165">Download and unpackage manually</span></span>

<span data-ttu-id="f565a-166">すべてを手動で実行する場合は、スクリプトの動作をレプリケートするために実行する操作を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f565a-166">If you would prefer to do everything manually, here's what to do to replicate the script’s behavior:</span></span>

1. <span data-ttu-id="f565a-167">インテリジェンス更新プログラムを格納するために呼び出されるシステム ルートに新しいフォルダーを作成します。たとえば、 `wdav_update` フォルダーを作成します `c:\wdav_update` 。</span><span class="sxs-lookup"><span data-stu-id="f565a-167">Create a new folder on the system root called `wdav_update` to store intelligence updates, for example, create the folder `c:\wdav_update`.</span></span>

2. <span data-ttu-id="f565a-168">GUID 名を *持つ* wdav_updateサブフォルダーを作成します。 `{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="f565a-168">Create a subfolder under *wdav_update* with a GUID name, such as `{00000000-0000-0000-0000-000000000000}`</span></span>

<span data-ttu-id="f565a-169">例を次に示します。 `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span><span class="sxs-lookup"><span data-stu-id="f565a-169">Here's an example: `c:\wdav_update\{00000000-0000-0000-0000-000000000000}`</span></span>

   > [!NOTE]
   > <span data-ttu-id="f565a-170">スクリプトでは、GUID の最後の 12 桁が、ファイルがダウンロードされた年、月、日、および時刻として設定し、その度に新しいフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f565a-170">In the script we set it so the last 12 digits of the GUID are the year, month, day, and time when the file was downloaded so that a new folder is created each time.</span></span> <span data-ttu-id="f565a-171">これを変更して、ファイルを同じフォルダーにダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="f565a-171">You can change this so that the file is downloaded to the same folder each time.</span></span>

3. <span data-ttu-id="f565a-172">セキュリティ インテリジェンス パッケージを [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  GUID フォルダーにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f565a-172">Download a security intelligence package from [https://www.microsoft.com/wdsi/definitions](https://www.microsoft.com/wdsi/definitions)  into the GUID folder.</span></span> <span data-ttu-id="f565a-173">ファイルの名前を指定する必要があります `mpam-fe.exe` 。</span><span class="sxs-lookup"><span data-stu-id="f565a-173">The file should be named `mpam-fe.exe`.</span></span>

4. <span data-ttu-id="f565a-174">cmd プロンプト ウィンドウを開き、作成した GUID フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="f565a-174">Open a cmd prompt window and navigate to the GUID folder you created.</span></span> <span data-ttu-id="f565a-175">**/X 抽出コマンドを** 使用して、たとえばファイルを抽出します `mpam-fe.exe /X` 。</span><span class="sxs-lookup"><span data-stu-id="f565a-175">Use the **/X** extraction command to extract the files, for example `mpam-fe.exe /X`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f565a-176">VM は、抽出された更新パッケージを使用して新しい GUID フォルダーが作成されるたびに、または既存のフォルダーが新しい抽出されたパッケージで更新されるたびに、更新されたパッケージを取得します。</span><span class="sxs-lookup"><span data-stu-id="f565a-176">The VMs will pick up the updated package whenever a new GUID folder is created with an extracted update package or whenever an existing folder is updated with a new extracted package.</span></span>

## <a name="randomize-scheduled-scans"></a><span data-ttu-id="f565a-177">スケジュールされたスキャンをランダム化する</span><span class="sxs-lookup"><span data-stu-id="f565a-177">Randomize scheduled scans</span></span>

<span data-ttu-id="f565a-178">スケジュールされたスキャンは、リアルタイムの保護 [とスキャンに加えて実行されます](configure-real-time-protection-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="f565a-178">Scheduled scans run in addition to [real-time protection and scanning](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="f565a-179">スキャン自体の開始時刻は、スケジュールされたスキャン ポリシー **(ScheduleDay、ScheduleTime、\*\*\*\*および** **ScheduleQuickScanTime) に基づいて引き続き実行されます**。</span><span class="sxs-lookup"><span data-stu-id="f565a-179">The start time of the scan itself is still based on the scheduled scan policy (**ScheduleDay**, **ScheduleTime**, and **ScheduleQuickScanTime**).</span></span> <span data-ttu-id="f565a-180">ランダム化を行Microsoft Defender ウイルス対策、スケジュールされたスキャンに設定された時刻から 4 時間以内に各コンピューターでスキャンを開始します。</span><span class="sxs-lookup"><span data-stu-id="f565a-180">Randomization will cause Microsoft Defender Antivirus to start a scan on each machine within a 4-hour window from the time set for the scheduled scan.</span></span>

<span data-ttu-id="f565a-181">「スケジュール [されたスキャンで](scheduled-catch-up-scans-microsoft-defender-antivirus.md) 使用できるその他の構成オプションについては、スキャンをスケジュールする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f565a-181">See [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) for other configuration options available for scheduled scans.</span></span>

## <a name="use-quick-scans"></a><span data-ttu-id="f565a-182">クイック スキャンの使用</span><span class="sxs-lookup"><span data-stu-id="f565a-182">Use quick scans</span></span>

<span data-ttu-id="f565a-183">スケジュールされたスキャン中に実行するスキャンの種類を指定できます。</span><span class="sxs-lookup"><span data-stu-id="f565a-183">You can specify the type of scan that should be performed during a scheduled scan.</span></span> <span data-ttu-id="f565a-184">クイック スキャンは、マルウェアをアクティブにする必要があるすべての場所を検索するように設計された、優先的な方法です。</span><span class="sxs-lookup"><span data-stu-id="f565a-184">Quick scans are the preferred approach as they are designed to look in all places where malware needs to reside to be active.</span></span> <span data-ttu-id="f565a-185">次の手順では、グループ ポリシーを使用してクイック スキャンを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f565a-185">The following procedure describes how to set up quick scans using Group Policy.</span></span>

1. <span data-ttu-id="f565a-186">グループ ポリシー エディターで、[スキャン] の **[** 管理  >  **用Windows]**  >  **Microsoft Defender ウイルス対策**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-186">In your Group Policy Editor, go to **Administrative templates** > **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="f565a-187">[ **スケジュールされたスキャンに使用するスキャンの種類を指定する] を選択** し、ポリシー設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="f565a-187">Select **Specify the scan type to use for a scheduled scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="f565a-188">ポリシーを [有効] **に設定し**、[オプション] で **[クイック** スキャン]  **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-188">Set the policy to **Enabled**, and then under **Options**, select  **Quick scan**.</span></span>

4. <span data-ttu-id="f565a-189">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f565a-189">Select **OK**.</span></span> 

5. <span data-ttu-id="f565a-190">グループ ポリシー オブジェクトは、通常と同じ方法で展開します。</span><span class="sxs-lookup"><span data-stu-id="f565a-190">Deploy your Group Policy object as you usually do.</span></span>

## <a name="prevent-notifications"></a><span data-ttu-id="f565a-191">通知を防止する</span><span class="sxs-lookup"><span data-stu-id="f565a-191">Prevent notifications</span></span>

<span data-ttu-id="f565a-192">場合によっては、Microsoft Defender ウイルス対策通知が複数のセッションに送信または保持される場合があります。</span><span class="sxs-lookup"><span data-stu-id="f565a-192">Sometimes, Microsoft Defender Antivirus notifications may be sent to or persist across multiple sessions.</span></span> <span data-ttu-id="f565a-193">この問題を最小限に抑えるために、ユーザー インターフェイスのMicrosoft Defender ウイルス対策できます。</span><span class="sxs-lookup"><span data-stu-id="f565a-193">In order to minimize this problem, you can lock down the Microsoft Defender Antivirus user interface.</span></span> <span data-ttu-id="f565a-194">次の手順では、グループ ポリシーを使用して通知を抑制する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="f565a-194">The following procedure describes how to suppress notifications with Group Policy.</span></span>

1. <span data-ttu-id="f565a-195">グループ ポリシー エディターで、[クライアント インターフェイスWindows **コンポーネント**  >  **Microsoft Defender ウイルス対策**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-195">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="f565a-196">[すべての **通知を非表示にする] を** 選択し、ポリシー設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="f565a-196">Select **Suppress all notifications** and then edit the policy settings.</span></span> 

3. <span data-ttu-id="f565a-197">ポリシーを [有効]**に設定し\*\*\*\*、[OK] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-197">Set the policy to **Enabled**, and then select **OK**.</span></span>

4. <span data-ttu-id="f565a-198">グループ ポリシー オブジェクトは、通常と同じ方法で展開します。</span><span class="sxs-lookup"><span data-stu-id="f565a-198">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="f565a-199">通知を抑制すると、スキャンMicrosoft Defender ウイルス対策修復アクションが実行された場合Windows 10アクション センターに通知が表示されません。</span><span class="sxs-lookup"><span data-stu-id="f565a-199">Suppressing notifications prevents notifications from Microsoft Defender Antivirus from showing up in the Action Center on Windows 10 when scans are done or remediation actions are taken.</span></span> <span data-ttu-id="f565a-200">ただし、セキュリティ運用チームは、スキャンの結果を [ファイル] () にMicrosoft Defender セキュリティ センター [https://securitycenter.windows.com](https://securitycenter.windows.com) します。</span><span class="sxs-lookup"><span data-stu-id="f565a-200">However, your security operations team will see the results of the scan in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="f565a-201">[アクション センター] を開Windows 10、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f565a-201">To open the Action Center on Windows 10, take one of the following steps:</span></span>
> - <span data-ttu-id="f565a-202">タスク バーの右側にある [アクション センター] アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="f565a-202">On the right end of the taskbar, select the Action Center icon.</span></span>
> - <span data-ttu-id="f565a-203">[ロゴ] Windows + A を押します。</span><span class="sxs-lookup"><span data-stu-id="f565a-203">Press the Windows logo key button + A.</span></span>
> - <span data-ttu-id="f565a-204">タッチスクリーン デバイスで、画面の右端からスワイプします。</span><span class="sxs-lookup"><span data-stu-id="f565a-204">On a touchscreen device, swipe in from the right edge of the screen.</span></span>

## <a name="disable-scans-after-an-update"></a><span data-ttu-id="f565a-205">更新後にスキャンを無効にする</span><span class="sxs-lookup"><span data-stu-id="f565a-205">Disable scans after an update</span></span>

<span data-ttu-id="f565a-206">更新後にスキャンを無効にすると、更新プログラムを受信した後にスキャンが発生しなくなります。</span><span class="sxs-lookup"><span data-stu-id="f565a-206">Disabling a scan after an update will prevent a scan from occurring after receiving an update.</span></span> <span data-ttu-id="f565a-207">クイック スキャンも実行している場合は、基本イメージの作成時にこの設定を適用できます。</span><span class="sxs-lookup"><span data-stu-id="f565a-207">You can apply this setting when creating the base image if you have also run a quick scan.</span></span> <span data-ttu-id="f565a-208">これにより、新しく更新された VM がスキャンを再度実行し(ベース イメージの作成時に既にスキャン済み) のを防ぐことが可能です。</span><span class="sxs-lookup"><span data-stu-id="f565a-208">This way, you can prevent the newly updated VM from performing a scan again (as you've already scanned it when you created the base image).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f565a-209">更新後にスキャンを実行すると、最新のセキュリティ インテリジェンス更新プログラムで VM が保護されます。</span><span class="sxs-lookup"><span data-stu-id="f565a-209">Running scans after an update will help ensure your VMs are protected with the latest Security intelligence updates.</span></span> <span data-ttu-id="f565a-210">このオプションを無効にすると、VM の保護レベルが低下し、基本イメージを最初に作成または展開するときにのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f565a-210">Disabling this option will reduce the protection level of your VMs and should only be used when first creating or deploying the base image.</span></span>

1. <span data-ttu-id="f565a-211">グループ ポリシー エディターで、[セキュリティ インテリジェンス **の更新WindowsのMicrosoft Defender ウイルス対策**  >    >  **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-211">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

2. <span data-ttu-id="f565a-212">[ **セキュリティ インテリジェンスの更新後にスキャンを有効にする] を選択** し、ポリシー設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="f565a-212">Select **Turn on scan after security intelligence update** and then edit the policy setting.</span></span>

3. <span data-ttu-id="f565a-213">ポリシーを [無効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-213">Set the policy to **Disabled**.</span></span>

4. <span data-ttu-id="f565a-214">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f565a-214">Select **OK**.</span></span>

5. <span data-ttu-id="f565a-215">グループ ポリシー オブジェクトは、通常と同じ方法で展開します。</span><span class="sxs-lookup"><span data-stu-id="f565a-215">Deploy your Group Policy object as you usually do.</span></span>

<span data-ttu-id="f565a-216">このポリシーは、更新後すぐにスキャンが実行されるのを防ぐためです。</span><span class="sxs-lookup"><span data-stu-id="f565a-216">This policy prevents a scan from running immediately after an update.</span></span>

## <a name="scan-vms-that-have-been-offline"></a><span data-ttu-id="f565a-217">オフラインの VM をスキャンする</span><span class="sxs-lookup"><span data-stu-id="f565a-217">Scan VMs that have been offline</span></span>

1. <span data-ttu-id="f565a-218">グループ ポリシー エディターで、[スキャン] の [Windows **コンポーネント**  >  **Microsoft Defender ウイルス対策**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-218">In your Group Policy Editor, go to to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

2. <span data-ttu-id="f565a-219">[ **キャッチアップ クイック スキャンを有効にする] を選択** し、ポリシー設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="f565a-219">Select **Turn on catch-up quick scan** and then edit the policy setting.</span></span>

3. <span data-ttu-id="f565a-220">ポリシーを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-220">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="f565a-221">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f565a-221">Select **OK**.</span></span>

5. <span data-ttu-id="f565a-222">通常と同じ方法でグループ ポリシー オブジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="f565a-222">Deploy your Group Policy Object as you usually do.</span></span>

<span data-ttu-id="f565a-223">このポリシーは、VM が 2 つ以上の連続したスケジュールされたスキャンを見逃した場合にスキャンを強制的に実行します。</span><span class="sxs-lookup"><span data-stu-id="f565a-223">This policy forces a scan if the VM has missed two or more consecutive scheduled scans.</span></span>

## <a name="enable-headless-ui-mode"></a><span data-ttu-id="f565a-224">ヘッドレス UI モードを有効にする</span><span class="sxs-lookup"><span data-stu-id="f565a-224">Enable headless UI mode</span></span>

1. <span data-ttu-id="f565a-225">グループ ポリシー エディターで、[クライアント インターフェイスWindows **コンポーネント**  >  **Microsoft Defender ウイルス対策**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-225">In your Group Policy Editor, go to **Windows components** > **Microsoft Defender Antivirus** > **Client Interface**.</span></span>

2. <span data-ttu-id="f565a-226">[ヘッド **レス UI モードを有効にする] を選択** し、ポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="f565a-226">Select **Enable headless UI mode** and edit the policy.</span></span>

3. <span data-ttu-id="f565a-227">ポリシーを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="f565a-227">Set the policy to **Enabled**.</span></span>

4. <span data-ttu-id="f565a-228">[**OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f565a-228">Click **OK**.</span></span>

5. <span data-ttu-id="f565a-229">通常と同じ方法でグループ ポリシー オブジェクトを展開します。</span><span class="sxs-lookup"><span data-stu-id="f565a-229">Deploy your Group Policy Object as you usually do.</span></span>
 
<span data-ttu-id="f565a-230">このポリシーは、組織内のエンド Microsoft Defender ウイルス対策ユーザー インターフェイス全体を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="f565a-230">This policy hides the entire Microsoft Defender Antivirus user interface from end users in your organization.</span></span>

## <a name="exclusions"></a><span data-ttu-id="f565a-231">除外</span><span class="sxs-lookup"><span data-stu-id="f565a-231">Exclusions</span></span>

<span data-ttu-id="f565a-232">除外は、ニーズに合わせて追加、削除、またはカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="f565a-232">Exclusions can be added, removed, or customized to suit your needs.</span></span>

<span data-ttu-id="f565a-233">詳細については、「Configure [Microsoft Defender ウイルス対策 サーバー」をWindowsしてください](configure-exclusions-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="f565a-233">For more information, see [Configure Microsoft Defender Antivirus exclusions on Windows Server](configure-exclusions-microsoft-defender-antivirus.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f565a-234">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="f565a-234">Additional resources</span></span>

- [<span data-ttu-id="f565a-235">Tech Communityブログ: 非永続的な VDI Microsoft Defender ウイルス対策の構成</span><span class="sxs-lookup"><span data-stu-id="f565a-235">Tech Community Blog: Configuring Microsoft Defender Antivirus for non-persistent VDI machines</span></span>](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/configuring-microsoft-defender-antivirus-for-non-persistent-vdi/ba-p/1489633)
- [<span data-ttu-id="f565a-236">リモート デスクトップ サービスと VDI の TechNet フォーラム</span><span class="sxs-lookup"><span data-stu-id="f565a-236">TechNet forums on Remote Desktop Services and VDI</span></span>](https://social.technet.microsoft.com/Forums/windowsserver/en-US/home?forum=winserverTS)
- [<span data-ttu-id="f565a-237">SignatureDownloadCustomTask PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="f565a-237">SignatureDownloadCustomTask PowerShell script</span></span>](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4)