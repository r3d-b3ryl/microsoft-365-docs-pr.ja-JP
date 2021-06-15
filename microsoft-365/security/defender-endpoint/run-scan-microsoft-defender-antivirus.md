---
title: オンデマンド スキャンを実行してカスタマイズする方法は、Microsoft Defender ウイルス対策
description: PowerShell、Windows 管理インストルメンテーション、またはアプリを使用してエンドポイントで個別にオンデマンド スキャンを実行Windows セキュリティする
keywords: スキャン、オンデマンド、dos、intune、インスタント スキャン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b2910f9fe1c49178b8696d1a421248156b0fc4c2
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925733"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="f27c5-104">オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する</span><span class="sxs-lookup"><span data-stu-id="f27c5-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="f27c5-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f27c5-105">**Applies to:**</span></span>

- [<span data-ttu-id="f27c5-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f27c5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f27c5-107">個々のエンドポイントでオンデマンド スキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="f27c5-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="f27c5-108">これらのスキャンはすぐに開始され、場所や種類などのスキャンのパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="f27c5-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span> <span data-ttu-id="f27c5-109">スキャンを実行する場合は、クイック スキャン、フル スキャン、カスタム スキャンの 3 種類から選択できます。</span><span class="sxs-lookup"><span data-stu-id="f27c5-109">When you run a scan, you can choose from among three types: Quick scan, full scan, and custom scan.</span></span> <span data-ttu-id="f27c5-110">ほとんどの場合、クイック スキャンを使用します。</span><span class="sxs-lookup"><span data-stu-id="f27c5-110">In most cases, use a quick scan.</span></span> <span data-ttu-id="f27c5-111">クイック スキャンでは、レジストリ キーや既知のスタートアップ フォルダーなど、システムで起動するマルウェアが登録されている可能性があるすべての場所Windowsします。</span><span class="sxs-lookup"><span data-stu-id="f27c5-111">A quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span> 

<span data-ttu-id="f27c5-112">ファイルを開いて閉じたときに確認する常時オンのリアルタイム保護と組み合わせて、ユーザーがフォルダーに移動するたびに、クイック スキャンを実行すると、システムとカーネル レベルのマルウェアから始まるマルウェアに対する強力な保護を提供できます。</span><span class="sxs-lookup"><span data-stu-id="f27c5-112">Combined with always-on, real-time protection, which reviews files when they are opened and closed, and whenever a user navigates to a folder, a quick scan helps provide strong protection against malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="f27c5-113">ほとんどの場合、クイック スキャンで十分であり、スケジュールされたスキャンまたはオンデマンド スキャンに推奨されるオプションです。</span><span class="sxs-lookup"><span data-stu-id="f27c5-113">In most cases, a quick scan is sufficient and is the recommended option for scheduled or on-demand scans.</span></span>  <span data-ttu-id="f27c5-114">[スキャンの種類について詳しくは、以下を参照してください](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan)。</span><span class="sxs-lookup"><span data-stu-id="f27c5-114">[Learn more about scan types](schedule-antivirus-scans.md#quick-scan-full-scan-and-custom-scan).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f27c5-115">Microsoft Defender ウイルス対策スキャンを実行するときに[、LocalSystem](/windows/win32/services/localsystem-account)アカウントのコンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="f27c5-115">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="f27c5-116">ネットワーク スキャンでは、デバイス アカウントのコンテキストが使用されます。</span><span class="sxs-lookup"><span data-stu-id="f27c5-116">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="f27c5-117">ドメイン デバイス アカウントが共有にアクセスするための適切なアクセス許可を持ってない場合、スキャンは機能しません。</span><span class="sxs-lookup"><span data-stu-id="f27c5-117">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="f27c5-118">デバイスがアクセス ネットワーク共有に対するアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f27c5-118">Ensure that the device has permissions to the access network share.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="f27c5-119">スキャンMicrosoft エンドポイント マネージャー実行するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f27c5-119">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="f27c5-120">管理センター ( ) Microsoft エンドポイント マネージャーに移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、ログインします。</span><span class="sxs-lookup"><span data-stu-id="f27c5-120">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="f27c5-121">[エンドポイント **セキュリティウイルス**  >  **対策] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f27c5-121">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="f27c5-122">タブの一覧で、[不健康 **なWindows 10を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f27c5-122">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>

4. <span data-ttu-id="f27c5-123">指定されたアクションの一覧から、[クイック **スキャン** (推奨)] または [フル スキャン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f27c5-123">From the list of actions provided, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

<span data-ttu-id="f27c5-124">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="f27c5-124">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="f27c5-125">スキャンの実行に Microsoft エンドポイント マネージャーの詳細については、「マルウェア対策タスクとファイアウォール タスク: オンデマンド スキャンを実行する[方法」を参照してください](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)。</span><span class="sxs-lookup"><span data-stu-id="f27c5-125">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="f27c5-126">スキャンをmpcmdrun.exeコマンド ライン ユーティリティを使用する</span><span class="sxs-lookup"><span data-stu-id="f27c5-126">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="f27c5-127">次のパラメーターを使用 `-scan` します。</span><span class="sxs-lookup"><span data-stu-id="f27c5-127">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="f27c5-128">ツールの使用方法と、フル スキャンの開始、パスの定義など、追加のパラメーターの詳細については、「mpcmdrun.exe コマンド ライン ツールを使用して、Microsoft Defender ウイルス対策 を構成および管理する」[を参照してください](command-line-arguments-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="f27c5-128">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="f27c5-129">スキャンMicrosoft Intune実行するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f27c5-129">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="f27c5-130">管理センター ( ) Microsoft エンドポイント マネージャーに移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、ログインします。</span><span class="sxs-lookup"><span data-stu-id="f27c5-130">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="f27c5-131">サイドバーで[デバイスすべての **デバイス]**  >  **を選択** し、スキャンするデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="f27c5-131">From the sidebar, select **Devices** > **All Devices** and choose the device you want to scan.</span></span>

3. <span data-ttu-id="f27c5-132">**[..] を選択します。More**. More .</span><span class="sxs-lookup"><span data-stu-id="f27c5-132">Select **...More**.</span></span> <span data-ttu-id="f27c5-133">オプションから、[クイック スキャン ( **推奨** ) ] または [フル スキャン] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f27c5-133">From the options, select **Quick Scan** (recommended) or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="f27c5-134">スキャンを実行Windows セキュリティアプリを使用する</span><span class="sxs-lookup"><span data-stu-id="f27c5-134">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="f27c5-135">個々[のエンドポイントでスキャン](microsoft-defender-security-center-antivirus.md)を実行する方法については、「Windows セキュリティ アプリでスキャンを実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f27c5-135">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="f27c5-136">PowerShell コマンドレットを使用してスキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="f27c5-136">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="f27c5-137">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f27c5-137">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="f27c5-138">PowerShell を Microsoft Defender ウイルス対策と一緒に使用する方法の詳細については[、「Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して、PowerShell コマンドレットと Defender コマンドレットを構成およびMicrosoft Defender ウイルス対策実行する」を[参照してください](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="f27c5-138">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="f27c5-139">スキャンWindows実行するには、管理命令 (WMI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f27c5-139">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="f27c5-140">クラスの [**Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan)メソッドを **MSFT_MpScan** します。</span><span class="sxs-lookup"><span data-stu-id="f27c5-140">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="f27c5-141">使用できるパラメーターの詳細については[、「WMIv2 API のWindows Defender参照してください。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="f27c5-141">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

