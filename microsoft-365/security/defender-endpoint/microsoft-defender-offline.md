---
title: Microsoft Defender Offline in Windows 10
description: Microsoft Defender Offline は、ウイルス対策アプリから直接Windows Defender使用できます。 ネットワークでの展開方法を管理できます。
keywords: スキャン、ディフェンダー、オフライン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 44a0e78ecfe3854a070831bf01a012c2cec06ce7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690932"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a><span data-ttu-id="5659d-105">Microsoft Defender オフライン スキャンの結果を実行して確認する</span><span class="sxs-lookup"><span data-stu-id="5659d-105">Run and review the results of a Microsoft Defender Offline scan</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5659d-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5659d-106">**Applies to:**</span></span>

- [<span data-ttu-id="5659d-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5659d-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5659d-108">Microsoft Defender Offline は、信頼できる環境からスキャンを起動して実行できるマルウェア対策スキャン ツールです。</span><span class="sxs-lookup"><span data-stu-id="5659d-108">Microsoft Defender Offline is an antimalware scanning tool that lets you boot and run a scan from a trusted environment.</span></span> <span data-ttu-id="5659d-109">スキャンは通常の Windows カーネルの外部から実行され、マスター ブート レコード (MBR) に感染または上書きするウイルスやルートキットなど、Windows シェルをバイパスしようとするマルウェアをターゲットにできます。</span><span class="sxs-lookup"><span data-stu-id="5659d-109">The scan runs from outside the normal Windows kernel so it can target malware that attempts to bypass the Windows shell, such as viruses and rootkits that infect or overwrite the master boot record (MBR).</span></span>

<span data-ttu-id="5659d-110">マルウェア感染の疑いがある場合、またはマルウェアの発生後にエンドポイントの完全なクリーンを確認する場合は、Microsoft Defender Offline を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5659d-110">You can use Microsoft Defender Offline if you suspect a malware infection, or you want to confirm a thorough clean of the endpoint after a malware outbreak.</span></span>

<span data-ttu-id="5659d-111">Windows 10 では、Windows セキュリティ アプリから直接 1 回のクリックで Microsoft Defender [Offline を実行できます](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="5659d-111">In Windows 10, Microsoft Defender Offline can be run with one click directly from the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="5659d-112">以前のバージョンの Windows では、ユーザーは Microsoft Defender Offline を起動可能なメディアにインストールし、エンドポイントを再起動し、起動可能なメディアを読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="5659d-112">In previous versions of Windows, a user had to install Microsoft Defender Offline to bootable media, restart the endpoint, and load the bootable media.</span></span>

## <a name="prerequisites-and-requirements"></a><span data-ttu-id="5659d-113">前提条件と要件</span><span class="sxs-lookup"><span data-stu-id="5659d-113">prerequisites and requirements</span></span>

<span data-ttu-id="5659d-114">Windows 10 の Microsoft Defender Offline には、Windows 10 と同じハードウェア要件があります。</span><span class="sxs-lookup"><span data-stu-id="5659d-114">Microsoft Defender Offline in Windows 10 has the same hardware requirements as Windows 10.</span></span> 

<span data-ttu-id="5659d-115">Windows 10 の要件の詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5659d-115">For more information about Windows 10 requirements, see the following topics:</span></span>

- [<span data-ttu-id="5659d-116">ハードウェアの最小要件</span><span class="sxs-lookup"><span data-stu-id="5659d-116">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [<span data-ttu-id="5659d-117">ハードウェア コンポーネントのガイドライン</span><span class="sxs-lookup"><span data-stu-id="5659d-117">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> <span data-ttu-id="5659d-118">Microsoft Defender Offline は、プロセッサが搭載されたコンピューター、ARM Windows Server Stock Keeping Units ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5659d-118">Microsoft Defender Offline is not supported on machines with ARM processors, or on Windows Server Stock Keeping Units.</span></span>

<span data-ttu-id="5659d-119">エンドポイントから Microsoft Defender Offline を実行するには、管理者特権でログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5659d-119">To run Microsoft Defender Offline from the endpoint, the user must be logged in with administrator privileges.</span></span>
 
## <a name="microsoft-defender-offline-updates"></a><span data-ttu-id="5659d-120">Microsoft Defender オフライン更新プログラム</span><span class="sxs-lookup"><span data-stu-id="5659d-120">Microsoft Defender Offline updates</span></span>

<span data-ttu-id="5659d-121">Microsoft Defender Offline は、エンドポイントで利用可能な最新の保護更新プログラムを使用します。ウイルス対策が更新されるたびにWindows Defender更新されます。</span><span class="sxs-lookup"><span data-stu-id="5659d-121">Microsoft Defender Offline uses the most recent protection updates available on the endpoint; it's updated whenever Windows Defender Antivirus is updated.</span></span> 

> [!NOTE]
> <span data-ttu-id="5659d-122">オフライン スキャンを実行する前に、Microsoft Defender AV 保護の更新を試みる必要があります。</span><span class="sxs-lookup"><span data-stu-id="5659d-122">Before running an offline scan, you should attempt to update Microsoft Defender AV protection.</span></span> <span data-ttu-id="5659d-123">グループ ポリシーを使用して更新を強制するか、通常はエンドポイントに更新プログラムを展開するか、マイクロソフト マルウェア プロテクション センター から最新の保護更新プログラムを手動でダウンロードして [インストールすることができます](https://www.microsoft.com/security/portal/definitions/adl.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5659d-123">You can either force an update with Group Policy or however you normally deploy updates to endpoints, or you can manually download and install the latest protection updates from the [Microsoft Malware Protection Center](https://www.microsoft.com/security/portal/definitions/adl.aspx).</span></span>

<span data-ttu-id="5659d-124">詳細については [、「Microsoft Defender ウイルス対策セキュリティ インテリジェンス更新プログラムの管理」](manage-protection-updates-microsoft-defender-antivirus.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5659d-124">See the [Manage Microsoft Defender Antivirus Security intelligence  updates](manage-protection-updates-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="usage-scenarios"></a><span data-ttu-id="5659d-125">使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="5659d-125">Usage scenarios</span></span>

<span data-ttu-id="5659d-126">Windows 10 バージョン 1607 では、手動でオフライン スキャンを強制できます。</span><span class="sxs-lookup"><span data-stu-id="5659d-126">In Windows 10, version 1607, you can manually force an offline scan.</span></span> <span data-ttu-id="5659d-127">または、Microsoft Defender オフラインWindows Defender必要と判断した場合は、エンドポイントでユーザーにメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="5659d-127">Alternatively, if Windows Defender determines that Microsoft Defender Offline needs to run, it will prompt the user on the endpoint.</span></span> 

<span data-ttu-id="5659d-128">オフライン スキャンを実行する必要性は、エンドポイントの管理に使用している場合は、Microsoft Endpoint Manager でも表示されます。</span><span class="sxs-lookup"><span data-stu-id="5659d-128">The need to perform an offline scan will also be revealed in Microsoft Endpoint Manager if you're using it to manage your endpoints.</span></span>

<span data-ttu-id="5659d-129">このプロンプトは、次のような通知を介して実行できます。</span><span class="sxs-lookup"><span data-stu-id="5659d-129">The prompt can occur via a notification, similar to the following:</span></span>

![Microsoft Defender Offline を実行する要件を示す Windows 通知](images/defender/notification.png)

<span data-ttu-id="5659d-131">ユーザーには、クライアント内で通知Windows Defenderされます。</span><span class="sxs-lookup"><span data-stu-id="5659d-131">The user will also be notified within the Windows Defender client.</span></span>

<span data-ttu-id="5659d-132">Configuration Manager では、[監視> 概要> セキュリティ> エンドポイント保護の状態> System **Center Endpoint Protection Status]** に移動して、エンドポイントの状態を識別できます。</span><span class="sxs-lookup"><span data-stu-id="5659d-132">In Configuration Manager, you can identify the status of endpoints by navigating to **Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status**.</span></span> 

<span data-ttu-id="5659d-133">Microsoft Defender オフライン スキャンは、マルウェア修復状態 **の下に** オフライン スキャン **が必要と示されています**。</span><span class="sxs-lookup"><span data-stu-id="5659d-133">Microsoft Defender Offline scans are indicated under **Malware remediation status** as **Offline scan required**.</span></span>

![Microsoft Defender オフライン スキャンが必要であることを示す Microsoft エンドポイント マネージャー](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a><span data-ttu-id="5659d-135">通知の構成</span><span class="sxs-lookup"><span data-stu-id="5659d-135">Configure notifications</span></span>

<span data-ttu-id="5659d-136">Microsoft Defender オフライン通知は、他の Microsoft Defender AV 通知と同じポリシー設定で構成されます。</span><span class="sxs-lookup"><span data-stu-id="5659d-136">Microsoft Defender Offline notifications are configured in the same policy setting as other Microsoft Defender AV notifications.</span></span>

<span data-ttu-id="5659d-137">アプリの通知の詳細については、「Windows Defenderに表示される通知を構成する [」を参照](configure-notifications-microsoft-defender-antivirus.md) してください。</span><span class="sxs-lookup"><span data-stu-id="5659d-137">For more information about notifications in Windows Defender, see the [Configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md) topic.</span></span>

## <a name="run-a-scan"></a><span data-ttu-id="5659d-138">スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="5659d-138">Run a scan</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="5659d-139">Microsoft Defender Offline を使用する前に、ファイルを保存し、実行中のプログラムをシャットダウンしてください。</span><span class="sxs-lookup"><span data-stu-id="5659d-139">Before you use Microsoft Defender Offline, make sure you save any files and shut down running programs.</span></span> <span data-ttu-id="5659d-140">Microsoft Defender Offline スキャンの実行には約 15 分かかります。</span><span class="sxs-lookup"><span data-stu-id="5659d-140">The Microsoft Defender Offline scan takes about 15 minutes to run.</span></span> <span data-ttu-id="5659d-141">スキャンが完了すると、エンドポイントが再起動します。</span><span class="sxs-lookup"><span data-stu-id="5659d-141">It will restart the endpoint when the scan is complete.</span></span> <span data-ttu-id="5659d-142">スキャンは、通常の Windows オペレーティング環境の外部で実行されます。</span><span class="sxs-lookup"><span data-stu-id="5659d-142">The scan is performed outside of the usual Windows operating environment.</span></span> <span data-ttu-id="5659d-143">ユーザー インターフェイスは、ユーザー インターフェイスによって実行される通常のスキャンとは異Windows Defender。</span><span class="sxs-lookup"><span data-stu-id="5659d-143">The user interface will appear different to a normal scan performed by Windows Defender.</span></span> <span data-ttu-id="5659d-144">スキャンが完了すると、エンドポイントが再起動され、Windows が正常に読み込されます。</span><span class="sxs-lookup"><span data-stu-id="5659d-144">After the scan is completed, the endpoint will be restarted and Windows will load normally.</span></span>

<span data-ttu-id="5659d-145">Microsoft Defender オフライン スキャンを実行するには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="5659d-145">You can run a Microsoft Defender Offline scan with the following:</span></span>

- <span data-ttu-id="5659d-146">PowerShell</span><span class="sxs-lookup"><span data-stu-id="5659d-146">PowerShell</span></span>
- <span data-ttu-id="5659d-147">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="5659d-147">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="5659d-148">Windows セキュリティ アプリ</span><span class="sxs-lookup"><span data-stu-id="5659d-148">The Windows Security app</span></span>



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a><span data-ttu-id="5659d-149">PowerShell コマンドレットを使用してオフライン スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="5659d-149">Use PowerShell cmdlets to run an offline scan</span></span>

<span data-ttu-id="5659d-150">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="5659d-150">Use the following cmdlets:</span></span>

```PowerShell
Start-MpWDOScan
```

<span data-ttu-id="5659d-151">[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5659d-151">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a><span data-ttu-id="5659d-152">Windows 管理命令 (WMI) を使用してオフライン スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="5659d-152">Use Windows Management Instruction (WMI) to run an offline scan</span></span>

<span data-ttu-id="5659d-153">オフライン スキャンを [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) するには、MSFT_MpWDOScan クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="5659d-153">Use the [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class to run an offline scan.</span></span>

<span data-ttu-id="5659d-154">次の WMI スクリプト スニペットは直ちに Microsoft Defender Offline スキャンを実行し、エンドポイントを再起動し、オフライン スキャンを実行し、Windows で再起動して起動します。</span><span class="sxs-lookup"><span data-stu-id="5659d-154">The following WMI script snippet will immediately run a Microsoft Defender Offline scan, which will cause the endpoint to restart, run the offline scan, and then restart and boot into Windows.</span></span>

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

<span data-ttu-id="5659d-155">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5659d-155">See the following for more information:</span></span>
- [<span data-ttu-id="5659d-156">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="5659d-156">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a><span data-ttu-id="5659d-157">Windows Defender セキュリティ アプリを使用してオフライン スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="5659d-157">Use the Windows Defender Security app to run an offline scan</span></span>

1. <span data-ttu-id="5659d-158">タスク バーのシールド アイコンをクリックするか、Defender のスタート メニューを検索して、Windows セキュリティ アプリを開 **きます**。</span><span class="sxs-lookup"><span data-stu-id="5659d-158">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="5659d-159">[ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) をクリックし、[高度なスキャン] **ラベルをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="5659d-159">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Advanced scan** label:</span></span>
    
3. <span data-ttu-id="5659d-160">[Microsoft **Defender オフライン スキャン] を選択し** 、[今すぐスキャン **] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="5659d-160">Select **Microsoft Defender Offline scan** and click **Scan now**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5659d-161">Windows 10 バージョン 1607 では **、Windows Settings** Update & セキュリティ Windows Defender またはクライアントからオフライン スキャン  >    >  をWindows Defenderできます。</span><span class="sxs-lookup"><span data-stu-id="5659d-161">In Windows 10, version 1607, the offline scan could be run from under **Windows Settings** > **Update & security** > **Windows Defender** or from the Windows Defender client.</span></span>


## <a name="review-scan-results"></a><span data-ttu-id="5659d-162">スキャン結果の確認</span><span class="sxs-lookup"><span data-stu-id="5659d-162">Review scan results</span></span>

<span data-ttu-id="5659d-163">Microsoft Defender オフライン スキャンの結果は、Windows セキュリティ アプリの [スキャン [履歴] セクションに表示されます](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="5659d-163">Microsoft Defender Offline scan results will be listed in the [Scan history section of the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> 


## <a name="related-articles"></a><span data-ttu-id="5659d-164">関連記事</span><span class="sxs-lookup"><span data-stu-id="5659d-164">Related articles</span></span>

- [<span data-ttu-id="5659d-165">スキャンと修復の結果をカスタマイズ、開始、および確認する</span><span class="sxs-lookup"><span data-stu-id="5659d-165">Customize, initiate, and review the results of scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="5659d-166">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="5659d-166">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)