---
title: 攻撃面の減少ルールを有効にする
description: 攻撃表面の縮小 (ASR) ルールを有効にして、マクロ、スクリプト、一般的なインジェクション手法を使用する攻撃からデバイスを保護します。
keywords: 攻撃表面の縮小、腰、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、有効化、有効にする
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e6f3d6da2424b2b3b6b7c1f2c9973e4046d6e27f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689178"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="4773f-104">攻撃面の減少ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="4773f-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4773f-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="4773f-105">**Applies to:**</span></span>
- [<span data-ttu-id="4773f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4773f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4773f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4773f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="4773f-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="4773f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4773f-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="4773f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="4773f-110">[攻撃表面の縮小ルール](attack-surface-reduction.md) (ASR ルール) は、マルウェアが頻繁にデバイスやネットワークを侵害するアクションを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4773f-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span> <span data-ttu-id="4773f-111">次のエディションとバージョンの Windows を実行しているデバイスに対して ASR ルールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="4773f-111">You can set ASR rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="4773f-112">Windows 10 Pro [バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 以降</span><span class="sxs-lookup"><span data-stu-id="4773f-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="4773f-113">Windows 10 Enterprise バージョン [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 以降</span><span class="sxs-lookup"><span data-stu-id="4773f-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="4773f-114">Windows Server バージョン [1803 (半期チャネル)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) 以降</span><span class="sxs-lookup"><span data-stu-id="4773f-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="4773f-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="4773f-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="4773f-116">各 ASR ルールには、次の 4 つの設定のいずれかを含む。</span><span class="sxs-lookup"><span data-stu-id="4773f-116">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="4773f-117">**構成されていません**: ASR ルールを無効にする</span><span class="sxs-lookup"><span data-stu-id="4773f-117">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="4773f-118">**ブロック**: ASR ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="4773f-118">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="4773f-119">**監査**: ASR ルールが有効な場合に組織に与える影響を評価する</span><span class="sxs-lookup"><span data-stu-id="4773f-119">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="4773f-120">**警告**: ASR ルールを有効にするが、エンド ユーザーがブロックをバイパスする</span><span class="sxs-lookup"><span data-stu-id="4773f-120">**Warn**: Enable the ASR rule but alow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4773f-121">現在、Microsoft Endpoint Manager (MEM) で ASR ルールを構成する場合、3 つの ASR ルールでは警告モードはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="4773f-121">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="4773f-122">詳細については、「警告モード [がサポートされていないケース」を参照してください](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)。</span><span class="sxs-lookup"><span data-stu-id="4773f-122">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="4773f-123">Microsoft Defender for Endpoint (Defender [for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection) で使用できる高度な監視およびレポート機能を利用するには、Windows E5 ライセンス (または類似のライセンス SKU) で ASR ルールを使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4773f-123">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="4773f-124">ただし、高度な監視およびレポート機能にアクセスできない Windows Professional や E3 などの他のライセンスの場合は、ASR ルールがトリガーされる際に各エンドポイントで生成されるイベント (イベント転送など) の上に独自の監視およびレポート ツールを開発できます。</span><span class="sxs-lookup"><span data-stu-id="4773f-124">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="4773f-125">Windows ライセンスの詳細については [、「Windows 10 Licensing」](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) を参照し [、Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)のボリューム ライセンス ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4773f-125">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="4773f-126">攻撃表面の縮小ルールは、次の方法で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="4773f-126">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="4773f-127">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4773f-127">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="4773f-128">モバイル デバイス管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="4773f-128">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="4773f-129">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4773f-129">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="4773f-130">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="4773f-130">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="4773f-131">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4773f-131">PowerShell</span></span>](#powershell)

<span data-ttu-id="4773f-132">Intune や Microsoft Endpoint Manager などのエンタープライズ レベルの管理をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4773f-132">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="4773f-133">エンタープライズ レベルの管理では、起動時に競合するグループ ポリシーまたは PowerShell 設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="4773f-133">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="4773f-134">ASR ルールからファイルとフォルダーを除外する</span><span class="sxs-lookup"><span data-stu-id="4773f-134">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="4773f-135">ほとんどの攻撃表面の縮小ルールによってファイルとフォルダーが評価されるのを除外できます。</span><span class="sxs-lookup"><span data-stu-id="4773f-135">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="4773f-136">つまり、ASR ルールがファイルまたはフォルダーに悪意のある動作が含まれていると判断した場合でも、ファイルの実行をブロックしません。</span><span class="sxs-lookup"><span data-stu-id="4773f-136">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="4773f-137">これにより、安全でないファイルを実行してデバイスに感染する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4773f-137">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="4773f-138">指定された Defender for Endpoint ファイルと証明書インジケーターを許可することで、証明書とファイル ハッシュに基づいて ASR ルールをトリガーから除外することもできます。</span><span class="sxs-lookup"><span data-stu-id="4773f-138">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="4773f-139">(「指標 [の管理」を参照](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)してください。</span><span class="sxs-lookup"><span data-stu-id="4773f-139">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4773f-140">ファイルまたはフォルダーを除外すると、ASR ルールによって提供される保護が大幅に低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4773f-140">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="4773f-141">除外されたファイルの実行が許可され、レポートやイベントは記録されません。</span><span class="sxs-lookup"><span data-stu-id="4773f-141">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="4773f-142">ASR ルールで検出すべきではないと思うファイルを検出する場合は、まず監査モードを使用して [ルールをテストする必要があります](evaluate-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="4773f-142">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="4773f-143">個々のファイルまたはフォルダー (フォルダー パスまたは完全修飾リソース名を使用) を指定できますが、除外が適用されるルールを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="4773f-143">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="4773f-144">除外は、除外されたアプリケーションまたはサービスが開始された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="4773f-144">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="4773f-145">たとえば、既に実行されている更新サービスの除外を追加すると、サービスが停止して再起動されるまで、更新サービスはイベントをトリガーし続ける。</span><span class="sxs-lookup"><span data-stu-id="4773f-145">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="4773f-146">ASR ルールは、環境変数とワイルドカードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="4773f-146">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="4773f-147">ワイルドカードの使用の詳細については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。</span><span class="sxs-lookup"><span data-stu-id="4773f-147">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="4773f-148">ASR ルールを有効にする次の手順には、ファイルとフォルダーを除外する方法の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="4773f-148">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="4773f-149">Intune</span><span class="sxs-lookup"><span data-stu-id="4773f-149">Intune</span></span>

1. <span data-ttu-id="4773f-150">[デバイス **構成プロファイル**  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4773f-150">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="4773f-151">既存のエンドポイント保護プロファイルを選択するか、新しいエンドポイント保護プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="4773f-151">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="4773f-152">新しいプロファイルを作成するには、[プロファイルの作成] **を選択し** 、このプロファイルの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="4773f-152">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="4773f-153">[プロファイル **の種類] で**、[ **エンドポイント保護] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4773f-153">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="4773f-154">既存のプロファイルを選択した場合は、[プロパティ] を選択 **し、[設定** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4773f-154">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="4773f-155">[エンドポイント保護 **] ウィンドウで** 、[Exploit **Guard] をWindows Defenderし**、[攻撃表面の縮小 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4773f-155">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="4773f-156">各 ASR ルールの目的の設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="4773f-156">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="4773f-157">[ **攻撃表面の縮小の例外] で**、個々のファイルとフォルダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="4773f-157">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="4773f-158">[インポート] を **選択して** 、ASR ルールから除外するファイルとフォルダーを含む CSV ファイルをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="4773f-158">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="4773f-159">CSV ファイルの各行は、次のように書式設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4773f-159">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="4773f-160">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="4773f-160">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="4773f-161">3 つの構成ウィンドウで **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="4773f-161">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="4773f-162">次に、**新しい** エンドポイント保護ファイルを作成する場合は[作成] を選択し、既存のエンドポイント保護ファイルを編集する場合は [保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4773f-162">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="4773f-163">MDM</span><span class="sxs-lookup"><span data-stu-id="4773f-163">MDM</span></span>

<span data-ttu-id="4773f-164">各ルールのモードを個別に有効にして設定するには [、./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) 構成サービス プロバイダー (CSP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4773f-164">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="4773f-165">ASR ルールに GUID 値を使用して参照 [するサンプルを次に示します](attack-surface-reduction.md#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="4773f-165">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="4773f-166">監査モードで有効 (ブロック)、無効化、警告、または有効にする値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4773f-166">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="4773f-167">0 : 無効にする (ASR ルールを無効にする)</span><span class="sxs-lookup"><span data-stu-id="4773f-167">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="4773f-168">1 : ブロック (ASR ルールを有効にする)</span><span class="sxs-lookup"><span data-stu-id="4773f-168">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="4773f-169">2 : 監査 (ASR ルールが有効な場合に組織に与える影響を評価する)</span><span class="sxs-lookup"><span data-stu-id="4773f-169">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="4773f-170">6 : 警告 (ASR ルールを有効にするが、エンド ユーザーがブロックをバイパスできる)</span><span class="sxs-lookup"><span data-stu-id="4773f-170">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

<span data-ttu-id="4773f-171">除外を追加するには [、./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 構成サービス プロバイダー (CSP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="4773f-171">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="4773f-172">例:</span><span class="sxs-lookup"><span data-stu-id="4773f-172">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="4773f-173">スペースを使用せずに OMA-URI 値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="4773f-173">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="4773f-174">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4773f-174">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="4773f-175">Microsoft Endpoint Configuration Manager で、[アセットとコンプライアンス エンドポイント保護] に移動 **し**、[Exploit  >    >  **Guard Windows Defenderに移動します**。</span><span class="sxs-lookup"><span data-stu-id="4773f-175">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="4773f-176">[ホーム **エクスプ**  >  **ロイト ガード ポリシーの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4773f-176">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="4773f-177">名前と説明を入力し、[攻撃表面の縮小] を **選択** し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4773f-177">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="4773f-178">アクションをブロックまたは監査するルールを選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4773f-178">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="4773f-179">設定を確認し、[次へ] **を選択** してポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4773f-179">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="4773f-180">ポリシーが作成された後、閉 **じます**。</span><span class="sxs-lookup"><span data-stu-id="4773f-180">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="4773f-181">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="4773f-181">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="4773f-182">Intune、Configuration Manager、または他のエンタープライズ レベルの管理プラットフォームを使用してコンピューターとデバイスを管理する場合、管理ソフトウェアは起動時に競合するグループ ポリシー設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="4773f-182">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="4773f-183">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](https://technet.microsoft.com/library/cc731212.aspx)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="4773f-183">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="4773f-184">グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4773f-184">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="4773f-185">ツリーを Windows コンポーネント **に展開**  >  **する Microsoft Defender ウイルス** 対策  >  **Microsoft Defender Exploit Guard**  >  **攻撃表面の縮小**。</span><span class="sxs-lookup"><span data-stu-id="4773f-185">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="4773f-186">[攻撃 **表面縮小ルールの構成] を選択し、[** 有効] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="4773f-186">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="4773f-187">その後、[オプション] セクションで各ルールの個別の状態を設定できます。</span><span class="sxs-lookup"><span data-stu-id="4773f-187">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="4773f-188">**[Show....]** を選択し、[値名] 列にルール ID を入力し、[値] 列に選択した状態 **を** 次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="4773f-188">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="4773f-189">0 : 無効にする (ASR ルールを無効にする)</span><span class="sxs-lookup"><span data-stu-id="4773f-189">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="4773f-190">1 : ブロック (ASR ルールを有効にする)</span><span class="sxs-lookup"><span data-stu-id="4773f-190">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="4773f-191">2 : 監査 (ASR ルールが有効な場合に組織に与える影響を評価する)</span><span class="sxs-lookup"><span data-stu-id="4773f-191">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="4773f-192">6 : 警告 (ASR ルールを有効にするが、エンド ユーザーがブロックをバイパスできる)</span><span class="sxs-lookup"><span data-stu-id="4773f-192">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="グループ ポリシーの ASR ルール":::

5. <span data-ttu-id="4773f-194">ASR ルールからファイルとフォルダーを除外するには、[攻撃表面の縮小ルールからファイルとパスを除外する] 設定を選択し、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="4773f-194">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="4773f-195">[ **表示] を** 選択し、[値の名前] 列に各ファイル **またはフォルダーを入力** します。</span><span class="sxs-lookup"><span data-stu-id="4773f-195">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="4773f-196">各 **アイテムの [** 値] **列に 0** を入力します。</span><span class="sxs-lookup"><span data-stu-id="4773f-196">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="4773f-197">[値の名前] 列または [値] 列でサポートされていない引用符は **使用** しません。</span><span class="sxs-lookup"><span data-stu-id="4773f-197">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="4773f-198">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4773f-198">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="4773f-199">Intune、Configuration Manager、または別のエンタープライズ レベルの管理プラットフォームを使用してコンピューターとデバイスを管理すると、起動時に競合する PowerShell 設定が管理ソフトウェアによって上書きされます。</span><span class="sxs-lookup"><span data-stu-id="4773f-199">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="4773f-200">PowerShell を使用して値を定義するには、管理プラットフォームのルールに "User Defined" オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="4773f-200">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="4773f-201">[ **スタート] メニューに「powershell」** と入力し、Windows PowerShellを右クリックし **、[** 管理者として **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="4773f-201">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="4773f-202">次の cmdlet を入力します。</span><span class="sxs-lookup"><span data-stu-id="4773f-202">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="4773f-203">監査モードで ASR ルールを有効にするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4773f-203">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="4773f-204">警告モードで ASR ルールを有効にするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4773f-204">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="4773f-205">ASR ルールをオフにするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4773f-205">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="4773f-206">ルールごとに状態を個別に指定する必要がありますが、コンマ区切りのリストでルールと状態を組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="4773f-206">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="4773f-207">次の例では、最初の 2 つのルールが有効になり、3 番目のルールが無効になり、4 番目のルールが監査モードで有効になります。</span><span class="sxs-lookup"><span data-stu-id="4773f-207">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="4773f-208">PowerShell 動詞を使用 `Add-MpPreference` して、既存のリストに新しいルールを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="4773f-208">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="4773f-209">`Set-MpPreference` ルールの既存のセットは常に上書きされます。</span><span class="sxs-lookup"><span data-stu-id="4773f-209">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="4773f-210">既存のセットに追加する場合は、代わりに `Add-MpPreference` 使用します。</span><span class="sxs-lookup"><span data-stu-id="4773f-210">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="4773f-211">を使用して、ルールとその現在の状態の一覧を取得できます `Get-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="4773f-211">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="4773f-212">ASR ルールからファイルとフォルダーを除外するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="4773f-212">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="4773f-213">引き続き使用 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` して、リストにファイルとフォルダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="4773f-213">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4773f-214">リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="4773f-214">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="4773f-215">コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="4773f-215">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="4773f-216">関連記事</span><span class="sxs-lookup"><span data-stu-id="4773f-216">Related articles</span></span>

- [<span data-ttu-id="4773f-217">攻撃表面の縮小ルールを使用して攻撃表面を削減する</span><span class="sxs-lookup"><span data-stu-id="4773f-217">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="4773f-218">攻撃表面の縮小を評価する</span><span class="sxs-lookup"><span data-stu-id="4773f-218">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="4773f-219">攻撃面の減少の FAQ</span><span class="sxs-lookup"><span data-stu-id="4773f-219">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
