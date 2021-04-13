---
title: Microsoft Defender AV でオンデマンド スキャンを実行してカスタマイズする
description: PowerShell、Windows 管理インストルメンテーション、または Windows セキュリティ アプリを使用してエンドポイントで個別にオンデマンド スキャンを実行および構成する
keywords: スキャン、オンデマンド、dos、intune、インスタント スキャン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 2f60bdb0bbd8b87895547e608b5c3c92414ea834
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691172"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="5756b-104">Microsoft Defender ウイルス対策スキャンの構成と実行</span><span class="sxs-lookup"><span data-stu-id="5756b-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5756b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5756b-105">**Applies to:**</span></span>

- [<span data-ttu-id="5756b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5756b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5756b-107">個々のエンドポイントでオンデマンド スキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="5756b-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="5756b-108">これらのスキャンはすぐに開始され、場所や種類などのスキャンのパラメーターを定義できます。</span><span class="sxs-lookup"><span data-stu-id="5756b-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="5756b-109">クイック スキャンとフル スキャン</span><span class="sxs-lookup"><span data-stu-id="5756b-109">Quick scan versus full scan</span></span>

<span data-ttu-id="5756b-110">クイック スキャンでは、レジストリ キーや既知の Windows スタートアップ フォルダーなど、システムで起動するマルウェアが登録されている可能性があるすべての場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="5756b-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5756b-111">Microsoft Defender ウイルス対策は、ローカル スキャンの実行時に [LocalSystem](/windows/win32/services/localsystem-account) アカウントのコンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="5756b-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="5756b-112">ネットワーク スキャンでは、デバイス アカウントのコンテキストが使用されます。</span><span class="sxs-lookup"><span data-stu-id="5756b-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="5756b-113">ドメイン デバイス アカウントが共有にアクセスするための適切なアクセス許可を持ってない場合、スキャンは機能しません。</span><span class="sxs-lookup"><span data-stu-id="5756b-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="5756b-114">デバイスがアクセス ネットワーク共有に対するアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5756b-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="5756b-115">常時オン[](configure-real-time-protection-microsoft-defender-antivirus.md)のリアルタイム保護機能と組み合わせて、ファイルを開いて閉じたときに確認し、ユーザーがフォルダーに移動するたびに、クイック スキャンを実行すると、システムとカーネル レベルのマルウェアから始まるマルウェアの両方に対して強力な範囲を提供できます。</span><span class="sxs-lookup"><span data-stu-id="5756b-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md)--which reviews files when they're opened and closed, and whenever a user navigates to a folder--a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="5756b-116">ほとんどの場合、クイック スキャンは、リアルタイム保護によって検出されていないマルウェアを見つけるのに十分です。</span><span class="sxs-lookup"><span data-stu-id="5756b-116">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="5756b-117">フル スキャンは、マルウェアの脅威を報告したエンドポイントで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5756b-117">A full scan can be useful on endpoints that have reported a malware threat.</span></span> <span data-ttu-id="5756b-118">スキャンでは、より完全なクリーンアップを必要とする非アクティブなコンポーネントが含む場合に特定できます。</span><span class="sxs-lookup"><span data-stu-id="5756b-118">The scan can identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="5756b-119">これは、組織がオンデマンド スキャンを実行している場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="5756b-119">This is  ideal if your organization is running on-demand scans.</span></span>

> [!NOTE]
> <span data-ttu-id="5756b-120">既定では、USB ドライブなどのマウントされたリムーバブル デバイスでクイック スキャンが実行されます。</span><span class="sxs-lookup"><span data-stu-id="5756b-120">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="5756b-121">Microsoft Endpoint Manager を使用してスキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="5756b-121">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="5756b-122">Microsoft Endpoint Manager 管理センター ( ) に移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、ログインします。</span><span class="sxs-lookup"><span data-stu-id="5756b-122">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="5756b-123">[エンドポイント **セキュリティウイルス**  >  **対策] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5756b-123">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="5756b-124">タブの一覧で、[Windows 10 の不健康な **エンドポイント] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5756b-124">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="5756b-125">指定されたアクションの一覧から、[クイック スキャン] または **[フル スキャン]** **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5756b-125">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="5756b-126">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5756b-126">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="5756b-127">Microsoft Endpoint Manager を使用してスキャンを実行する方法の詳細については、「マルウェア対策タスクとファイアウォール タスク: オンデマンド スキャンを実行する方法」 [を参照してください](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers)。</span><span class="sxs-lookup"><span data-stu-id="5756b-127">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="5756b-128">スキャンをmpcmdrun.exeコマンド ライン ユーティリティを使用する</span><span class="sxs-lookup"><span data-stu-id="5756b-128">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="5756b-129">次のパラメーターを使用 `-scan` します。</span><span class="sxs-lookup"><span data-stu-id="5756b-129">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="5756b-130">ツールの使用方法と、フル スキャンの開始、パスの定義など、追加のパラメーターの詳細については [、「microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md)を構成および管理するには、mpcmdrun.exe コマンド ライン ツールを使用する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5756b-130">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="5756b-131">Microsoft Intune を使用してスキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="5756b-131">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="5756b-132">Microsoft Endpoint Manager 管理センター ( ) に移動し [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 、ログインします。</span><span class="sxs-lookup"><span data-stu-id="5756b-132">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="5756b-133">サイドバーで、[すべてのデバイス] **>選択** し、スキャンするデバイスを選択します。</span><span class="sxs-lookup"><span data-stu-id="5756b-133">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="5756b-134">**[..] を選択します。More**. More .</span><span class="sxs-lookup"><span data-stu-id="5756b-134">Select **...More**.</span></span> <span data-ttu-id="5756b-135">オプションから、[クイック スキャン] **または [フル スキャン** ] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="5756b-135">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="5756b-136">Windows セキュリティ アプリを使用してスキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="5756b-136">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="5756b-137">個々 [のエンドポイントでスキャンを実行する手順については、「Windows セキュリティ](microsoft-defender-security-center-antivirus.md) アプリでスキャンを実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5756b-137">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="5756b-138">PowerShell コマンドレットを使用してスキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="5756b-138">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="5756b-139">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5756b-139">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="5756b-140">Microsoft Defender ウイルス対策で PowerShell を使用する方法の詳細については [、「Use PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと Defender コマンドレットを構成および実行する」を [参照してください](/powershell/module/defender/)。</span><span class="sxs-lookup"><span data-stu-id="5756b-140">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="5756b-141">Windows 管理命令 (WMI) を使用してスキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="5756b-141">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="5756b-142">クラスの [**Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan)メソッドを **MSFT_MpScan** します。</span><span class="sxs-lookup"><span data-stu-id="5756b-142">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="5756b-143">使用できるパラメーターの詳細については [、「WMIv2 API のWindows Defender参照してください。](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="5756b-143">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="5756b-144">関連記事</span><span class="sxs-lookup"><span data-stu-id="5756b-144">Related articles</span></span>

- [<span data-ttu-id="5756b-145">Microsoft Defender ウイルス対策スキャン オプションの構成</span><span class="sxs-lookup"><span data-stu-id="5756b-145">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5756b-146">スケジュールされた Microsoft Defender ウイルス対策スキャンを構成する</span><span class="sxs-lookup"><span data-stu-id="5756b-146">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5756b-147">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="5756b-147">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)