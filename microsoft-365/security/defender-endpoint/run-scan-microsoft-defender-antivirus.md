---
title: オンデマンド スキャンを実行してカスタマイズする方法は、Microsoft Defender ウイルス対策
description: PowerShell、Windows 管理インストルメンテーション、またはアプリを使用してエンドポイントで個別にオンデマンド スキャンを実行Windows セキュリティする
keywords: スキャン、オンデマンド、dos、intune、インスタント スキャン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: fdca059633ab0993e07b5b1be0c6f33cfe327fcf
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789173"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="be6ee-104">オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する</span><span class="sxs-lookup"><span data-stu-id="be6ee-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="be6ee-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="be6ee-105">**Applies to:**</span></span>

- [<span data-ttu-id="be6ee-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="be6ee-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="be6ee-107">個々のエンドポイントでオンデマンド スキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="be6ee-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="be6ee-108">これらのスキャンはすぐに開始され、場所や種類などのスキャンのパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="be6ee-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="be6ee-109">クイック スキャンとフル スキャン</span><span class="sxs-lookup"><span data-stu-id="be6ee-109">Quick scan versus full scan</span></span>

<span data-ttu-id="be6ee-110">クイック スキャンは、レジストリ キーや既知のスタートアップ フォルダーなど、システムで開始するマルウェアが登録されている可能性があるすべての場所Windowsします。</span><span class="sxs-lookup"><span data-stu-id="be6ee-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be6ee-111">Microsoft Defender ウイルス対策スキャンを実行するときに[、LocalSystem](/windows/win32/services/localsystem-account)アカウントのコンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="be6ee-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="be6ee-112">ネットワーク スキャンでは、デバイス アカウントのコンテキストが使用されます。</span><span class="sxs-lookup"><span data-stu-id="be6ee-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="be6ee-113">ドメイン デバイス アカウントが共有にアクセスするための適切なアクセス許可を持ってない場合、スキャンは機能しません。</span><span class="sxs-lookup"><span data-stu-id="be6ee-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="be6ee-114">デバイスがアクセス ネットワーク共有に対するアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="be6ee-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="be6ee-115">常時オン [のリアルタイム](configure-real-time-protection-microsoft-defender-antivirus.md)保護機能と組み合わせて、クイック スキャンは、システムから始まるマルウェアとカーネル レベルのマルウェアの両方に強力な範囲を提供します。</span><span class="sxs-lookup"><span data-stu-id="be6ee-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="be6ee-116">常時オンのリアルタイム保護は、ファイルを開いて閉じたときに、およびユーザーがフォルダーに移動するたびにファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="be6ee-116">Always-on, real-time protection reviews files when they're opened and closed, and whenever a user navigates to a folder.</span></span> <span data-ttu-id="be6ee-117">既定では、USB ドライブなどのマウントされたリムーバブル デバイスでクイック スキャンが実行されます。</span><span class="sxs-lookup"><span data-stu-id="be6ee-117">By default, quick scans run on mounted removable devices, such as USB drives.</span></span> <span data-ttu-id="be6ee-118">ほとんどの場合、クイック スキャンは、リアルタイム保護によって検出されていないマルウェアを見つけるのに十分です。</span><span class="sxs-lookup"><span data-stu-id="be6ee-118">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="be6ee-119">フル スキャンは、エンドポイントでマルウェアの脅威が報告される場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="be6ee-119">A full scan can be useful when a malware threat is reported on an endpoint.</span></span> <span data-ttu-id="be6ee-120">スキャンでは、より完全なクリーンアップを必要とする非アクティブなコンポーネントが含されているかどうかを特定できます。</span><span class="sxs-lookup"><span data-stu-id="be6ee-120">The scan can identify whether there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="be6ee-121">ただし、通常、フル スキャンではなくクイック スキャンの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="be6ee-121">However, Microsoft generally recommends using quick scans instead of full scans.</span></span> <span data-ttu-id="be6ee-122">フル スキャンは、スキャンする必要があるデータの量と種類に応じて、完了に数時間または数日かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="be6ee-122">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span> 

> [!TIP]
> <span data-ttu-id="be6ee-123">クイック スキャンとフル スキャンの違いの詳細については、「クイック スキャンとフル スキャンとカスタム スキャン」 [を参照してください](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan)。</span><span class="sxs-lookup"><span data-stu-id="be6ee-123">To learn more about the differences between quick and full scans, see [Quick scan versus full scan and custom scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan).</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="be6ee-124">スキャンMicrosoft エンドポイント マネージャー実行するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="be6ee-124">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="be6ee-125">管理センター ( ) Microsoft エンドポイント マネージャーに移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、ログインします。</span><span class="sxs-lookup"><span data-stu-id="be6ee-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="be6ee-126">[エンドポイント **セキュリティウイルス**  >  **対策] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="be6ee-126">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="be6ee-127">タブの一覧で、[不健康 **なWindows 10を選択します**。</span><span class="sxs-lookup"><span data-stu-id="be6ee-127">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="be6ee-128">指定されたアクションの一覧から、[クイック スキャン] または **[フル スキャン]** **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="be6ee-128">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="be6ee-129">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="be6ee-129">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="be6ee-130">スキャンの実行に Microsoft エンドポイント マネージャーの詳細については、「マルウェア対策タスクとファイアウォール タスク: オンデマンド スキャンを実行する[方法」を参照してください](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)。</span><span class="sxs-lookup"><span data-stu-id="be6ee-130">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="be6ee-131">スキャンをmpcmdrun.exeコマンド ライン ユーティリティを使用する</span><span class="sxs-lookup"><span data-stu-id="be6ee-131">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="be6ee-132">次のパラメーターを使用 `-scan` します。</span><span class="sxs-lookup"><span data-stu-id="be6ee-132">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="be6ee-133">ツールの使用方法と、フル スキャンの開始、パスの定義など、追加のパラメーターの詳細については、「mpcmdrun.exe コマンド ライン ツールを使用して、Microsoft Defender ウイルス対策 を構成および管理する」[を参照してください](command-line-arguments-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="be6ee-133">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="be6ee-134">スキャンMicrosoft Intune実行するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="be6ee-134">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="be6ee-135">管理センター ( ) Microsoft エンドポイント マネージャーに移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、ログインします。</span><span class="sxs-lookup"><span data-stu-id="be6ee-135">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="be6ee-136">サイドバーで、[すべてのデバイス] **>選択** し、スキャンするデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="be6ee-136">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="be6ee-137">**[..] を選択します。More**. More .</span><span class="sxs-lookup"><span data-stu-id="be6ee-137">Select **...More**.</span></span> <span data-ttu-id="be6ee-138">オプションから、[クイック スキャン] **または [フル スキャン** ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="be6ee-138">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="be6ee-139">スキャンを実行Windows セキュリティアプリを使用する</span><span class="sxs-lookup"><span data-stu-id="be6ee-139">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="be6ee-140">個々[のエンドポイントでスキャン](microsoft-defender-security-center-antivirus.md)を実行する方法については、「Windows セキュリティ アプリでスキャンを実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be6ee-140">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="be6ee-141">PowerShell コマンドレットを使用してスキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="be6ee-141">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="be6ee-142">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="be6ee-142">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="be6ee-143">PowerShell を Microsoft Defender ウイルス対策と一緒に使用する方法の詳細については[、「Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して、PowerShell コマンドレットと Defender コマンドレットを構成およびMicrosoft Defender ウイルス対策実行する」を[参照してください](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="be6ee-143">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="be6ee-144">スキャンWindows実行するには、管理命令 (WMI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="be6ee-144">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="be6ee-145">クラスの [**Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan)メソッドを **MSFT_MpScan** します。</span><span class="sxs-lookup"><span data-stu-id="be6ee-145">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="be6ee-146">使用できるパラメーターの詳細については[、「WMIv2 API のWindows Defender参照してください。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="be6ee-146">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="be6ee-147">関連資料</span><span class="sxs-lookup"><span data-stu-id="be6ee-147">Related articles</span></span>

- [<span data-ttu-id="be6ee-148">Microsoft Defender ウイルス対策スキャン オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="be6ee-148">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="be6ee-149">スケジュールされたスキャンMicrosoft Defender ウイルス対策構成する</span><span class="sxs-lookup"><span data-stu-id="be6ee-149">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="be6ee-150">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="be6ee-150">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)