---
title: Microsoft Defender オフラインのWindows 10
description: アプリから直接Microsoft Defender オフラインを使用Windows Defender ウイルス対策できます。 ネットワークでの展開方法を管理できます。
keywords: スキャン、ディフェンダー、オフライン
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a25a2ec513cd7c25f9f6ddf3d5e328928837bf2d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275146"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a><span data-ttu-id="082f6-105">Microsoft Defender オフライン スキャンの結果を実行してレビューする</span><span class="sxs-lookup"><span data-stu-id="082f6-105">Run and review the results of a Microsoft Defender Offline scan</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="082f6-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="082f6-106">**Applies to:**</span></span>

- [<span data-ttu-id="082f6-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="082f6-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="082f6-108">Microsoft Defender オフラインは、信頼できる環境からスキャンを起動して実行できるマルウェア対策スキャン ツールです。</span><span class="sxs-lookup"><span data-stu-id="082f6-108">Microsoft Defender Offline is an antimalware scanning tool that lets you boot and run a scan from a trusted environment.</span></span> <span data-ttu-id="082f6-109">スキャンは通常の Windows カーネルの外部から実行され、マスター ブート レコード (MBR) に感染または上書きするウイルスやルートキットなど、Windows シェルをバイパスしようとするマルウェアをターゲットにできます。</span><span class="sxs-lookup"><span data-stu-id="082f6-109">The scan runs from outside the normal Windows kernel so it can target malware that attempts to bypass the Windows shell, such as viruses and rootkits that infect or overwrite the master boot record (MBR).</span></span>

<span data-ttu-id="082f6-110">マルウェア感染がMicrosoft Defender オフライン疑われる場合、またはマルウェアの発生後にエンドポイントの完全なクリーンを確認する場合は、このツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="082f6-110">You can use Microsoft Defender Offline if you suspect a malware infection, or you want to confirm a thorough clean of the endpoint after a malware outbreak.</span></span>

<span data-ttu-id="082f6-111">このWindows 10、Microsoft Defender オフラインアプリから直接 1 回のクリックで実行Windows セキュリティ[できます](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="082f6-111">In Windows 10, Microsoft Defender Offline can be run with one click directly from the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="082f6-112">以前のバージョンの Windowsユーザーは、起動可能なメディアにMicrosoft Defender オフラインをインストールし、エンドポイントを再起動し、起動可能なメディアを読み込む必要があります。</span><span class="sxs-lookup"><span data-stu-id="082f6-112">In previous versions of Windows, a user had to install Microsoft Defender Offline to bootable media, restart the endpoint, and load the bootable media.</span></span>

## <a name="prerequisites-and-requirements"></a><span data-ttu-id="082f6-113">前提条件と要件</span><span class="sxs-lookup"><span data-stu-id="082f6-113">prerequisites and requirements</span></span>

<span data-ttu-id="082f6-114">Microsoft Defender オフラインはWindows 10ハードウェア要件と同じWindows 10。</span><span class="sxs-lookup"><span data-stu-id="082f6-114">Microsoft Defender Offline in Windows 10 has the same hardware requirements as Windows 10.</span></span> 

<span data-ttu-id="082f6-115">要件の詳細についてはWindows 10トピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="082f6-115">For more information about Windows 10 requirements, see the following topics:</span></span>

- [<span data-ttu-id="082f6-116">ハードウェアの最小要件</span><span class="sxs-lookup"><span data-stu-id="082f6-116">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [<span data-ttu-id="082f6-117">ハードウェア コンポーネントのガイドライン</span><span class="sxs-lookup"><span data-stu-id="082f6-117">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> <span data-ttu-id="082f6-118">Microsoft Defender オフラインプロセッサを搭載したコンピューター、またはサーバーストックARMユニットではWindowsサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="082f6-118">Microsoft Defender Offline is not supported on machines with ARM processors, or on Windows Server Stock Keeping Units.</span></span>

<span data-ttu-id="082f6-119">エンドポイントからMicrosoft Defender オフラインするには、管理者特権でログインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="082f6-119">To run Microsoft Defender Offline from the endpoint, the user must be logged in with administrator privileges.</span></span>
 
## <a name="microsoft-defender-offline-updates"></a><span data-ttu-id="082f6-120">Microsoft Defender オフライン更新プログラム</span><span class="sxs-lookup"><span data-stu-id="082f6-120">Microsoft Defender Offline updates</span></span>

<span data-ttu-id="082f6-121">Microsoft Defender オフラインエンドポイントで利用可能な最新の保護更新プログラムを使用します。更新されるたびに更新Windows Defender ウイルス対策されます。</span><span class="sxs-lookup"><span data-stu-id="082f6-121">Microsoft Defender Offline uses the most recent protection updates available on the endpoint; it's updated whenever Windows Defender Antivirus is updated.</span></span> 

> [!NOTE]
> <span data-ttu-id="082f6-122">オフライン スキャンを実行する前に、Microsoft Defender AV 保護の更新を試みる必要があります。</span><span class="sxs-lookup"><span data-stu-id="082f6-122">Before running an offline scan, you should attempt to update Microsoft Defender AV protection.</span></span> <span data-ttu-id="082f6-123">グループ ポリシーを使用して更新を強制するか、通常はエンドポイントに更新プログラムを展開するか、最新の保護更新プログラムを手動でダウンロードしてインストール[Microsoft マルウェア プロテクション センター。](https://www.microsoft.com/security/portal/definitions/adl.aspx)</span><span class="sxs-lookup"><span data-stu-id="082f6-123">You can either force an update with Group Policy or however you normally deploy updates to endpoints, or you can manually download and install the latest protection updates from the [Microsoft Malware Protection Center](https://www.microsoft.com/security/portal/definitions/adl.aspx).</span></span>

<span data-ttu-id="082f6-124">詳細については[、「セキュリティ インテリジェンスMicrosoft Defender ウイルス対策更新プログラムの管理」](manage-protection-updates-microsoft-defender-antivirus.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="082f6-124">See the [Manage Microsoft Defender Antivirus Security intelligence  updates](manage-protection-updates-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="usage-scenarios"></a><span data-ttu-id="082f6-125">使用シナリオ</span><span class="sxs-lookup"><span data-stu-id="082f6-125">Usage scenarios</span></span>

<span data-ttu-id="082f6-126">バージョン 1607 Windows 10では、手動でオフライン スキャンを強制できます。</span><span class="sxs-lookup"><span data-stu-id="082f6-126">In Windows 10, version 1607, you can manually force an offline scan.</span></span> <span data-ttu-id="082f6-127">または、実行Windows Defender必要Microsoft Defender オフライン判断した場合は、エンドポイントでユーザーにメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="082f6-127">Alternatively, if Windows Defender determines that Microsoft Defender Offline needs to run, it will prompt the user on the endpoint.</span></span> 

<span data-ttu-id="082f6-128">オフライン スキャンを実行する必要性は、エンドポイントの管理に使用している場合Microsoft エンドポイント マネージャーで表示されます。</span><span class="sxs-lookup"><span data-stu-id="082f6-128">The need to perform an offline scan will also be revealed in Microsoft Endpoint Manager if you're using it to manage your endpoints.</span></span>

<span data-ttu-id="082f6-129">このプロンプトは、次のような通知を介して実行できます。</span><span class="sxs-lookup"><span data-stu-id="082f6-129">The prompt can occur via a notification, similar to the following:</span></span>

![Windows実行の要件を示す通知Microsoft Defender オフライン](images/defender/notification.png)

<span data-ttu-id="082f6-131">ユーザーには、クライアント内で通知Windows Defenderされます。</span><span class="sxs-lookup"><span data-stu-id="082f6-131">The user will also be notified within the Windows Defender client.</span></span>

<span data-ttu-id="082f6-132">Configuration Manager で、エンドポイントの状態を識別するには、[監視] > [セキュリティの概要] > [状態 **> Endpoint Protection]**> System Center Endpoint Protectionします。</span><span class="sxs-lookup"><span data-stu-id="082f6-132">In Configuration Manager, you can identify the status of endpoints by navigating to **Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status**.</span></span> 

<span data-ttu-id="082f6-133">Microsoft Defender オフラインは[マルウェアの修復状態 **] で [** オフライン スキャンが必要]**と表示されます**。</span><span class="sxs-lookup"><span data-stu-id="082f6-133">Microsoft Defender Offline scans are indicated under **Malware remediation status** as **Offline scan required**.</span></span>

![Microsoft エンドポイント マネージャースキャンが必要Microsoft Defender オフライン示すメッセージ](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a><span data-ttu-id="082f6-135">通知の構成</span><span class="sxs-lookup"><span data-stu-id="082f6-135">Configure notifications</span></span>

<span data-ttu-id="082f6-136">Microsoft Defender オフラインは、他の Microsoft Defender AV 通知と同じポリシー設定で構成されます。</span><span class="sxs-lookup"><span data-stu-id="082f6-136">Microsoft Defender Offline notifications are configured in the same policy setting as other Microsoft Defender AV notifications.</span></span>

<span data-ttu-id="082f6-137">[エンドポイントに表示される通知Windows Defender構成する] トピック[を参照](configure-notifications-microsoft-defender-antivirus.md)してください。</span><span class="sxs-lookup"><span data-stu-id="082f6-137">For more information about notifications in Windows Defender, see the [Configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md) topic.</span></span>

## <a name="run-a-scan"></a><span data-ttu-id="082f6-138">スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="082f6-138">Run a scan</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="082f6-139">このファイルを使用Microsoft Defender オフライン、ファイルを保存し、実行中のプログラムをシャットダウンしてください。</span><span class="sxs-lookup"><span data-stu-id="082f6-139">Before you use Microsoft Defender Offline, make sure you save any files and shut down running programs.</span></span> <span data-ttu-id="082f6-140">スキャンMicrosoft Defender オフライン実行に約 15 分かかります。</span><span class="sxs-lookup"><span data-stu-id="082f6-140">The Microsoft Defender Offline scan takes about 15 minutes to run.</span></span> <span data-ttu-id="082f6-141">スキャンが完了すると、エンドポイントが再起動します。</span><span class="sxs-lookup"><span data-stu-id="082f6-141">It will restart the endpoint when the scan is complete.</span></span> <span data-ttu-id="082f6-142">スキャンは、通常のオペレーティング環境Windows外で実行されます。</span><span class="sxs-lookup"><span data-stu-id="082f6-142">The scan is performed outside of the usual Windows operating environment.</span></span> <span data-ttu-id="082f6-143">ユーザー インターフェイスは、ユーザー インターフェイスによって実行される通常のスキャンとは異Windows Defender。</span><span class="sxs-lookup"><span data-stu-id="082f6-143">The user interface will appear different to a normal scan performed by Windows Defender.</span></span> <span data-ttu-id="082f6-144">スキャンが完了すると、エンドポイントが再起動され、Windows読み込みされます。</span><span class="sxs-lookup"><span data-stu-id="082f6-144">After the scan is completed, the endpoint will be restarted and Windows will load normally.</span></span>

<span data-ttu-id="082f6-145">次のコマンドを使用Microsoft Defender オフラインスキャンを実行できます。</span><span class="sxs-lookup"><span data-stu-id="082f6-145">You can run a Microsoft Defender Offline scan with the following:</span></span>

- <span data-ttu-id="082f6-146">PowerShell</span><span class="sxs-lookup"><span data-stu-id="082f6-146">PowerShell</span></span>
- <span data-ttu-id="082f6-147">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="082f6-147">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="082f6-148">アプリWindows セキュリティアプリ</span><span class="sxs-lookup"><span data-stu-id="082f6-148">The Windows Security app</span></span>



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a><span data-ttu-id="082f6-149">PowerShell コマンドレットを使用してオフライン スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="082f6-149">Use PowerShell cmdlets to run an offline scan</span></span>

<span data-ttu-id="082f6-150">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="082f6-150">Use the following cmdlets:</span></span>

```PowerShell
Start-MpWDOScan
```

<span data-ttu-id="082f6-151">PowerShell[コマンドレットを](use-powershell-cmdlets-microsoft-defender-antivirus.md)構成して実行する方法の詳細については、「powerShell コマンドレットを使用して Microsoft Defender ウイルス対策 および[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照Microsoft Defender ウイルス対策。</span><span class="sxs-lookup"><span data-stu-id="082f6-151">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a><span data-ttu-id="082f6-152">オフライン Windowsを実行するには、管理者管理命令 (WMI) を使用します。</span><span class="sxs-lookup"><span data-stu-id="082f6-152">Use Windows Management Instruction (WMI) to run an offline scan</span></span>

<span data-ttu-id="082f6-153">オフライン スキャンを [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) するには、MSFT_MpWDOScan クラスを使用します。</span><span class="sxs-lookup"><span data-stu-id="082f6-153">Use the [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class to run an offline scan.</span></span>

<span data-ttu-id="082f6-154">次の WMI スクリプト スニペットは直ちに Microsoft Defender オフライン スキャンを実行します。この結果、エンドポイントが再起動され、オフライン スキャンが実行され、再起動して Windows に起動されます。</span><span class="sxs-lookup"><span data-stu-id="082f6-154">The following WMI script snippet will immediately run a Microsoft Defender Offline scan, which will cause the endpoint to restart, run the offline scan, and then restart and boot into Windows.</span></span>

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

<span data-ttu-id="082f6-155">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="082f6-155">See the following for more information:</span></span>
- [<span data-ttu-id="082f6-156">Windows DefenderWMIv2 API</span><span class="sxs-lookup"><span data-stu-id="082f6-156">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a><span data-ttu-id="082f6-157">Windows Defender セキュリティ アプリを使用してオフライン スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="082f6-157">Use the Windows Defender Security app to run an offline scan</span></span>

1. <span data-ttu-id="082f6-158">タスク バーのWindows セキュリティをクリックするか、Defender のスタート メニューを検索して、アプリを開 **きます**。</span><span class="sxs-lookup"><span data-stu-id="082f6-158">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="082f6-159">[ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) をクリックし、[高度なスキャン] **ラベルをクリック** します。</span><span class="sxs-lookup"><span data-stu-id="082f6-159">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Advanced scan** label:</span></span>
    
3. <span data-ttu-id="082f6-160">[スキャン **Microsoft Defender オフライン選択し、[** 今すぐスキャン]**をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="082f6-160">Select **Microsoft Defender Offline scan** and click **Scan now**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="082f6-161">バージョン Windows 10 1607 では、オフライン スキャンは Windows 設定 Update   >  **&** セキュリティ &  >  **Windows Defender** または Windows Defender クライアントから実行できます。</span><span class="sxs-lookup"><span data-stu-id="082f6-161">In Windows 10, version 1607, the offline scan could be run from under **Windows Settings** > **Update & security** > **Windows Defender** or from the Windows Defender client.</span></span>


## <a name="review-scan-results"></a><span data-ttu-id="082f6-162">スキャン結果の確認</span><span class="sxs-lookup"><span data-stu-id="082f6-162">Review scan results</span></span>

<span data-ttu-id="082f6-163">Microsoft Defender オフライン結果は、アプリの [スキャン履歴] セクションにWindows セキュリティ[されます](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="082f6-163">Microsoft Defender Offline scan results will be listed in the [Scan history section of the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> 


## <a name="related-articles"></a><span data-ttu-id="082f6-164">関連記事</span><span class="sxs-lookup"><span data-stu-id="082f6-164">Related articles</span></span>

- [<span data-ttu-id="082f6-165">スキャンと修復の結果をカスタマイズ、開始、および確認する</span><span class="sxs-lookup"><span data-stu-id="082f6-165">Customize, initiate, and review the results of scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="082f6-166">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="082f6-166">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)