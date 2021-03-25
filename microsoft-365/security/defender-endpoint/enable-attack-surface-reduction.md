---
title: 攻撃表面の縮小ルールを有効にする
description: 攻撃表面の縮小 (ASR) ルールを有効にして、マクロ、スクリプト、一般的なインジェクション手法を使用する攻撃からデバイスを保護します。
keywords: 攻撃表面の縮小、腰、ホスト侵入防止システム、保護ルール、悪用防止、脆弱性対策、悪用、感染防止、有効化、有効にする
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 1deec767c6af777b23ab5a91c9e719f690e0c048
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165143"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="f3213-104">攻撃表面の縮小ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="f3213-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f3213-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="f3213-105">**Applies to:**</span></span>
- [<span data-ttu-id="f3213-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="f3213-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f3213-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3213-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f3213-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="f3213-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f3213-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="f3213-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="f3213-110">[攻撃表面の縮小ルール](attack-surface-reduction.md) (ASR ルール) は、マルウェアが頻繁にデバイスやネットワークを侵害するアクションを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f3213-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span> <span data-ttu-id="f3213-111">次のエディションとバージョンの Windows を実行しているデバイスに対して ASR ルールを設定できます。</span><span class="sxs-lookup"><span data-stu-id="f3213-111">You can set ASR rules for devices running any of the following editions and versions of Windows:</span></span>
- <span data-ttu-id="f3213-112">Windows 10 Pro [バージョン 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 以降</span><span class="sxs-lookup"><span data-stu-id="f3213-112">Windows 10 Pro, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="f3213-113">Windows 10 Enterprise バージョン [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 以降</span><span class="sxs-lookup"><span data-stu-id="f3213-113">Windows 10 Enterprise, [version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="f3213-114">Windows Server バージョン [1803 (半期チャネル)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) 以降</span><span class="sxs-lookup"><span data-stu-id="f3213-114">Windows Server, [version 1803 (Semi-Annual Channel)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="f3213-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="f3213-115">Windows Server 2019</span></span>](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="f3213-116">各 ASR ルールには、次の 3 つの設定のいずれかを含む。</span><span class="sxs-lookup"><span data-stu-id="f3213-116">Each ASR rule contains one of three settings:</span></span>

- <span data-ttu-id="f3213-117">構成されていません: ASR ルールを無効にする</span><span class="sxs-lookup"><span data-stu-id="f3213-117">Not configured: Disable the ASR rule</span></span>
- <span data-ttu-id="f3213-118">ブロック: ASR ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="f3213-118">Block: Enable the ASR rule</span></span>
- <span data-ttu-id="f3213-119">監査: ASR ルールが有効な場合に組織に与える影響を評価する</span><span class="sxs-lookup"><span data-stu-id="f3213-119">Audit: Evaluate how the ASR rule would impact your organization if enabled</span></span>

<span data-ttu-id="f3213-120">Microsoft Defender for Endpoint (Defender [for Endpoint)](https://docs.microsoft.com/windows/security/threat-protection) で使用できる高度な監視およびレポート機能を利用するには、Windows E5 ライセンス (または類似のライセンス SKU) で ASR ルールを使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f3213-120">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="f3213-121">ただし、高度な監視およびレポート機能にアクセスできない Windows Professional や E3 などの他のライセンスの場合は、ASR ルールがトリガーされる際に各エンドポイントで生成されるイベント (イベント転送など) の上に独自の監視およびレポート ツールを開発できます。</span><span class="sxs-lookup"><span data-stu-id="f3213-121">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="f3213-122">Windows ライセンスの詳細については [、「Windows 10 Licensing」](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) を参照し [、Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)のボリューム ライセンス ガイドを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3213-122">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="f3213-123">攻撃表面の縮小ルールは、次の方法で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="f3213-123">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="f3213-124">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f3213-124">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="f3213-125">モバイル デバイス管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="f3213-125">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="f3213-126">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f3213-126">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="f3213-127">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="f3213-127">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="f3213-128">PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3213-128">PowerShell</span></span>](#powershell)

<span data-ttu-id="f3213-129">Intune や Microsoft Endpoint Manager などのエンタープライズ レベルの管理をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f3213-129">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="f3213-130">エンタープライズ レベルの管理では、起動時に競合するグループ ポリシーまたは PowerShell 設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f3213-130">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="f3213-131">ASR ルールからファイルとフォルダーを除外する</span><span class="sxs-lookup"><span data-stu-id="f3213-131">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="f3213-132">ほとんどの攻撃表面の縮小ルールによってファイルとフォルダーが評価されるのを除外できます。</span><span class="sxs-lookup"><span data-stu-id="f3213-132">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="f3213-133">つまり、ASR ルールがファイルまたはフォルダーに悪意のある動作が含まれていると判断した場合でも、ファイルの実行をブロックしません。</span><span class="sxs-lookup"><span data-stu-id="f3213-133">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="f3213-134">これにより、安全でないファイルを実行してデバイスに感染する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3213-134">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="f3213-135">指定された Defender for Endpoint ファイルと証明書インジケーターを許可することで、証明書とファイル ハッシュに基づいて ASR ルールをトリガーから除外することもできます。</span><span class="sxs-lookup"><span data-stu-id="f3213-135">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="f3213-136">(「指標 [の管理」を参照](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)してください。</span><span class="sxs-lookup"><span data-stu-id="f3213-136">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f3213-137">ファイルまたはフォルダーを除外すると、ASR ルールによって提供される保護が大幅に低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3213-137">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="f3213-138">除外されたファイルの実行が許可され、レポートやイベントは記録されません。</span><span class="sxs-lookup"><span data-stu-id="f3213-138">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="f3213-139">ASR ルールで検出すべきではないと思うファイルを検出する場合は、まず監査モードを使用して [ルールをテストする必要があります](evaluate-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="f3213-139">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>


<span data-ttu-id="f3213-140">個々のファイルまたはフォルダー (フォルダー パスまたは完全修飾リソース名を使用) を指定できますが、除外が適用されるルールを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="f3213-140">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="f3213-141">除外は、除外されたアプリケーションまたはサービスが開始された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="f3213-141">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="f3213-142">たとえば、既に実行されている更新サービスの除外を追加すると、サービスが停止して再起動されるまで、更新サービスはイベントをトリガーし続ける。</span><span class="sxs-lookup"><span data-stu-id="f3213-142">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="f3213-143">ASR ルールは、環境変数とワイルドカードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f3213-143">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="f3213-144">ワイルドカードの使用の詳細については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。</span><span class="sxs-lookup"><span data-stu-id="f3213-144">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="f3213-145">ASR ルールを有効にする次の手順には、ファイルとフォルダーを除外する方法の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f3213-145">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="f3213-146">Intune</span><span class="sxs-lookup"><span data-stu-id="f3213-146">Intune</span></span>

1. <span data-ttu-id="f3213-147">[デバイス **構成プロファイル**  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f3213-147">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="f3213-148">既存のエンドポイント保護プロファイルを選択するか、新しいエンドポイント保護プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3213-148">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="f3213-149">新しいプロファイルを作成するには、[プロファイルの作成] **を選択し** 、このプロファイルの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="f3213-149">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="f3213-150">[プロファイル **の種類] で**、[ **エンドポイント保護] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f3213-150">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="f3213-151">既存のプロファイルを選択した場合は、[プロパティ] を選択 **し、[設定** ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f3213-151">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="f3213-152">[エンドポイント保護 **] ウィンドウで** 、[Exploit **Guard] をWindows Defenderし**、[攻撃表面の縮小 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f3213-152">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="f3213-153">各 ASR ルールの目的の設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3213-153">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="f3213-154">[ **攻撃表面の縮小の例外] で**、個々のファイルとフォルダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="f3213-154">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="f3213-155">[インポート] を **選択して** 、ASR ルールから除外するファイルとフォルダーを含む CSV ファイルをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f3213-155">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="f3213-156">CSV ファイルの各行は、次のように書式設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3213-156">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="f3213-157">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="f3213-157">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="f3213-158">3 つの構成ウィンドウで **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3213-158">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="f3213-159">次に、**新しい** エンドポイント保護ファイルを作成する場合は[作成] を選択し、既存のエンドポイント保護ファイルを編集する場合は [保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f3213-159">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mdm"></a><span data-ttu-id="f3213-160">MDM</span><span class="sxs-lookup"><span data-stu-id="f3213-160">MDM</span></span>

<span data-ttu-id="f3213-161">各ルールのモードを個別に有効にして設定するには [、./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) 構成サービス プロバイダー (CSP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f3213-161">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="f3213-162">ASR ルールに GUID 値を使用して参照 [するサンプルを次に示します](attack-surface-reduction.md#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="f3213-162">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="f3213-163">監査モードで有効、無効、または有効にする値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="f3213-163">The values to enable, disable, or enable in audit mode are:</span></span>

- <span data-ttu-id="f3213-164">Disable = 0</span><span class="sxs-lookup"><span data-stu-id="f3213-164">Disable = 0</span></span>
- <span data-ttu-id="f3213-165">ブロック (ASR ルールを有効にする) = 1</span><span class="sxs-lookup"><span data-stu-id="f3213-165">Block (enable ASR rule) = 1</span></span>
- <span data-ttu-id="f3213-166">監査 = 2</span><span class="sxs-lookup"><span data-stu-id="f3213-166">Audit = 2</span></span>

<span data-ttu-id="f3213-167">除外を追加するには [、./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 構成サービス プロバイダー (CSP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="f3213-167">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="f3213-168">例:</span><span class="sxs-lookup"><span data-stu-id="f3213-168">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="f3213-169">スペースを使用せずに OMA-URI 値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="f3213-169">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="f3213-170">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f3213-170">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="f3213-171">Microsoft Endpoint Configuration Manager で、[アセットとコンプライアンス エンドポイント保護] に移動 **し**、[Exploit  >    >  **Guard Windows Defenderに移動します**。</span><span class="sxs-lookup"><span data-stu-id="f3213-171">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="f3213-172">[ホーム **エクスプ**  >  **ロイト ガード ポリシーの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f3213-172">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="f3213-173">名前と説明を入力し、[攻撃表面の縮小] を **選択** し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f3213-173">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="f3213-174">アクションをブロックまたは監査するルールを選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f3213-174">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="f3213-175">設定を確認し、[次へ] **を選択** してポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f3213-175">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="f3213-176">ポリシーが作成された後、閉 **じます**。</span><span class="sxs-lookup"><span data-stu-id="f3213-176">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="f3213-177">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="f3213-177">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="f3213-178">Intune、Configuration Manager、または他のエンタープライズ レベルの管理プラットフォームを使用してコンピューターとデバイスを管理する場合、管理ソフトウェアは起動時に競合するグループ ポリシー設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="f3213-178">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="f3213-179">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](https://technet.microsoft.com/library/cc731212.aspx)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] を選択 **します**。</span><span class="sxs-lookup"><span data-stu-id="f3213-179">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="f3213-180">グループ ポリシー **管理エディターで、[コンピューター** の構成] に移動 **し、[** 管理用 **テンプレート] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f3213-180">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="f3213-181">ツリーを Windows コンポーネント **に展開**  >  **します。Microsoft Defender ウイルス対策Windows Defender**  >  **エクスプロイト ガード**  >  **攻撃の表面の縮小です**。</span><span class="sxs-lookup"><span data-stu-id="f3213-181">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="f3213-182">[攻撃 **表面縮小ルールの構成] を選択し、[** 有効] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="f3213-182">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="f3213-183">その後、[オプション] セクションで各ルールの個別の状態を設定できます。</span><span class="sxs-lookup"><span data-stu-id="f3213-183">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="f3213-184">**[Show....]** を選択し、[値名] 列にルール ID を入力し、[値] 列に選択した状態 **を** 次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="f3213-184">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="f3213-185">Disable = 0</span><span class="sxs-lookup"><span data-stu-id="f3213-185">Disable = 0</span></span>
   - <span data-ttu-id="f3213-186">ブロック (ASR ルールを有効にする) = 1</span><span class="sxs-lookup"><span data-stu-id="f3213-186">Block (enable ASR rule) = 1</span></span>
   - <span data-ttu-id="f3213-187">監査 = 2</span><span class="sxs-lookup"><span data-stu-id="f3213-187">Audit = 2</span></span>

   ![空の攻撃表面縮小ルール ID と値 1 を示すグループ ポリシー設定](/microsoft-365/security/defender-endpoint/images/asr-rules-gp)

5. <span data-ttu-id="f3213-189">ASR ルールからファイルとフォルダーを除外するには、[攻撃表面の縮小ルールからファイルとパスを除外する] 設定を選択し、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="f3213-189">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="f3213-190">[ **表示] を** 選択し、[値の名前] 列に各ファイル **またはフォルダーを入力** します。</span><span class="sxs-lookup"><span data-stu-id="f3213-190">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="f3213-191">各 **アイテムの [** 値] **列に 0** を入力します。</span><span class="sxs-lookup"><span data-stu-id="f3213-191">Enter **0** in the **Value** column for each item.</span></span>

> [!WARNING]
> <span data-ttu-id="f3213-192">[値の名前] 列または [値] 列でサポートされていない引用符は **使用** しません。</span><span class="sxs-lookup"><span data-stu-id="f3213-192">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="f3213-193">PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3213-193">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="f3213-194">Intune、Configuration Manager、または別のエンタープライズ レベルの管理プラットフォームを使用してコンピューターとデバイスを管理すると、起動時に競合する PowerShell 設定が管理ソフトウェアによって上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f3213-194">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="f3213-195">PowerShell を使用して値を定義するには、管理プラットフォームのルールに "User Defined" オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="f3213-195">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="f3213-196">[ **スタート] メニューに「powershell」** と入力し、Windows PowerShellを右クリックし **、[** 管理者として **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="f3213-196">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="f3213-197">次のコマンドレットを入力します。</span><span class="sxs-lookup"><span data-stu-id="f3213-197">Enter the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="f3213-198">監査モードで ASR ルールを有効にするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f3213-198">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="f3213-199">ASR ルールをオフにするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f3213-199">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="f3213-200">ルールごとに状態を個別に指定する必要がありますが、コンマ区切りのリストでルールと状態を組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3213-200">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="f3213-201">次の例では、最初の 2 つのルールが有効になり、3 番目のルールが無効になり、4 番目のルールが監査モードで有効になります。</span><span class="sxs-lookup"><span data-stu-id="f3213-201">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="f3213-202">PowerShell 動詞を使用 `Add-MpPreference` して、既存のリストに新しいルールを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="f3213-202">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="f3213-203">`Set-MpPreference` ルールの既存のセットは常に上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f3213-203">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="f3213-204">既存のセットに追加する場合は、代わりに使用する `Add-MpPreference` 必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3213-204">If you want to add to the existing set, you should use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="f3213-205">を使用して、ルールとその現在の状態の一覧を取得できます `Get-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="f3213-205">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="f3213-206">ASR ルールからファイルとフォルダーを除外するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="f3213-206">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="f3213-207">引き続き使用 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` して、リストにファイルとフォルダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="f3213-207">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f3213-208">リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="f3213-208">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="f3213-209">コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="f3213-209">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f3213-210">関連記事</span><span class="sxs-lookup"><span data-stu-id="f3213-210">Related articles</span></span>

- [<span data-ttu-id="f3213-211">攻撃表面の縮小ルールを使用して攻撃表面を削減する</span><span class="sxs-lookup"><span data-stu-id="f3213-211">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="f3213-212">攻撃表面の縮小を評価する</span><span class="sxs-lookup"><span data-stu-id="f3213-212">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="f3213-213">攻撃表面の縮小に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="f3213-213">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
