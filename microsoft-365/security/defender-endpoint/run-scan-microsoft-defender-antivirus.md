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
ms.date: 05/05/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 124ebde48c008743a486a4454e7772fd93f9eca7
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275362"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="7ea57-104">オンデマンドの Microsoft Defender ウイルス対策スキャンを構成して実行する</span><span class="sxs-lookup"><span data-stu-id="7ea57-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7ea57-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7ea57-105">**Applies to:**</span></span>

- [<span data-ttu-id="7ea57-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7ea57-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="7ea57-107">個々のエンドポイントでオンデマンド スキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7ea57-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="7ea57-108">これらのスキャンはすぐに開始され、場所や種類などのスキャンのパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="7ea57-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="7ea57-109">クイック スキャンとフル スキャン</span><span class="sxs-lookup"><span data-stu-id="7ea57-109">Quick scan versus full scan</span></span>

<span data-ttu-id="7ea57-110">クイック スキャンは、レジストリ キーや既知のスタートアップ フォルダーなど、システムで開始するマルウェアが登録されている可能性があるすべての場所Windowsします。</span><span class="sxs-lookup"><span data-stu-id="7ea57-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ea57-111">Microsoft Defender ウイルス対策スキャンを実行するときに[、LocalSystem](/windows/win32/services/localsystem-account)アカウントのコンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="7ea57-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="7ea57-112">ネットワーク スキャンでは、デバイス アカウントのコンテキストが使用されます。</span><span class="sxs-lookup"><span data-stu-id="7ea57-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="7ea57-113">ドメイン デバイス アカウントが共有にアクセスするための適切なアクセス許可を持ってない場合、スキャンは機能しません。</span><span class="sxs-lookup"><span data-stu-id="7ea57-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="7ea57-114">デバイスがアクセス ネットワーク共有に対するアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7ea57-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="7ea57-115">常時オン[](configure-real-time-protection-microsoft-defender-antivirus.md)のリアルタイム保護機能と組み合わせて、ファイルを開いて閉じたときに確認し、ユーザーがフォルダーに移動するたびに、クイック スキャンを実行すると、システムとカーネル レベルのマルウェアから始まるマルウェアの両方に対して強力な範囲を提供できます。</span><span class="sxs-lookup"><span data-stu-id="7ea57-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md)--which reviews files when they're opened and closed, and whenever a user navigates to a folder--a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="7ea57-116">ほとんどの場合、クイック スキャンは、リアルタイム保護によって検出されていないマルウェアを見つけるのに十分です。</span><span class="sxs-lookup"><span data-stu-id="7ea57-116">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="7ea57-117">フル スキャンは、マルウェアの脅威を報告したエンドポイントで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7ea57-117">A full scan can be useful on endpoints that have reported a malware threat.</span></span> <span data-ttu-id="7ea57-118">スキャンでは、より完全なクリーンアップを必要とする非アクティブなコンポーネントが含む場合に特定できます。</span><span class="sxs-lookup"><span data-stu-id="7ea57-118">The scan can identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="7ea57-119">これは、組織がオンデマンド スキャンを実行している場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="7ea57-119">This is  ideal if your organization is running on-demand scans.</span></span>

> [!NOTE]
> <span data-ttu-id="7ea57-120">既定では、USB ドライブなどのマウントされたリムーバブル デバイスでクイック スキャンが実行されます。</span><span class="sxs-lookup"><span data-stu-id="7ea57-120">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="7ea57-121">スキャンMicrosoft エンドポイント マネージャー実行するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7ea57-121">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="7ea57-122">管理センター ( ) Microsoft エンドポイント マネージャーに移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、ログインします。</span><span class="sxs-lookup"><span data-stu-id="7ea57-122">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="7ea57-123">[エンドポイント **セキュリティウイルス**  >  **対策] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7ea57-123">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="7ea57-124">タブの一覧で、[不健康 **なWindows 10を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7ea57-124">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="7ea57-125">指定されたアクションの一覧から、[クイック スキャン] または **[フル スキャン]** **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7ea57-125">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="7ea57-126">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="7ea57-126">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="7ea57-127">スキャンの実行に Microsoft エンドポイント マネージャーの詳細については、「マルウェア対策タスクとファイアウォール タスク: オンデマンド スキャンを実行する[方法」を参照してください](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)。</span><span class="sxs-lookup"><span data-stu-id="7ea57-127">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="7ea57-128">スキャンをmpcmdrun.exeコマンド ライン ユーティリティを使用する</span><span class="sxs-lookup"><span data-stu-id="7ea57-128">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="7ea57-129">次のパラメーターを使用 `-scan` します。</span><span class="sxs-lookup"><span data-stu-id="7ea57-129">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="7ea57-130">ツールの使用方法と、フル スキャンの開始、パスの定義など、追加のパラメーターの詳細については、「mpcmdrun.exe コマンド ライン ツールを使用して、Microsoft Defender ウイルス対策 を構成および管理する」[を参照してください](command-line-arguments-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="7ea57-130">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="7ea57-131">スキャンMicrosoft Intune実行するには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="7ea57-131">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="7ea57-132">管理センター ( ) Microsoft エンドポイント マネージャーに移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、ログインします。</span><span class="sxs-lookup"><span data-stu-id="7ea57-132">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="7ea57-133">サイドバーで、[すべてのデバイス] **>選択** し、スキャンするデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="7ea57-133">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="7ea57-134">**[..] を選択します。More**. More .</span><span class="sxs-lookup"><span data-stu-id="7ea57-134">Select **...More**.</span></span> <span data-ttu-id="7ea57-135">オプションから、[クイック スキャン] **または [フル スキャン** ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="7ea57-135">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="7ea57-136">スキャンを実行Windows セキュリティアプリを使用する</span><span class="sxs-lookup"><span data-stu-id="7ea57-136">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="7ea57-137">個々[のエンドポイントでスキャン](microsoft-defender-security-center-antivirus.md)を実行する方法については、「Windows セキュリティ アプリでスキャンを実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7ea57-137">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="7ea57-138">PowerShell コマンドレットを使用してスキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="7ea57-138">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="7ea57-139">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7ea57-139">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="7ea57-140">PowerShell を Microsoft Defender ウイルス対策と一緒に使用する方法の詳細については[、「Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して、PowerShell コマンドレットと Defender コマンドレットを構成およびMicrosoft Defender ウイルス対策実行する」を[参照してください](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="7ea57-140">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="7ea57-141">スキャンWindows実行するには、管理命令 (WMI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="7ea57-141">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="7ea57-142">クラスの [**Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan)メソッドを **MSFT_MpScan** します。</span><span class="sxs-lookup"><span data-stu-id="7ea57-142">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="7ea57-143">使用できるパラメーターの詳細については[、「WMIv2 API のWindows Defender参照してください。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="7ea57-143">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="7ea57-144">関連記事</span><span class="sxs-lookup"><span data-stu-id="7ea57-144">Related articles</span></span>

- [<span data-ttu-id="7ea57-145">Microsoft Defender ウイルス対策スキャン オプションを構成する</span><span class="sxs-lookup"><span data-stu-id="7ea57-145">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7ea57-146">スケジュールされたスキャンMicrosoft Defender ウイルス対策構成する</span><span class="sxs-lookup"><span data-stu-id="7ea57-146">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="7ea57-147">Microsoft Defender ウイルス対策のWindows 10</span><span class="sxs-lookup"><span data-stu-id="7ea57-147">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)