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
author: denisebmsft
ms.author: deniseb
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.date: 06/02/2021
ms.openlocfilehash: 65215d15e79ab03611bbf28c153d6882fd1c355d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229145"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="01283-104">攻撃面の減少ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="01283-104">Enable attack surface reduction rules</span></span>

<span data-ttu-id="01283-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="01283-105">**Applies to:**</span></span>

- [<span data-ttu-id="01283-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="01283-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="01283-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01283-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="01283-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="01283-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="01283-109">[無料試用版にサインアップします](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)。</span><span class="sxs-lookup"><span data-stu-id="01283-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="01283-110">[攻撃表面の縮小ルール](attack-surface-reduction.md) (ASR ルール) は、マルウェアが頻繁にデバイスやネットワークを侵害するアクションを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="01283-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span>

## <a name="requirements"></a><span data-ttu-id="01283-111">要件</span><span class="sxs-lookup"><span data-stu-id="01283-111">Requirements</span></span>

<span data-ttu-id="01283-112">複数のバージョンの攻撃表面Windows機能</span><span class="sxs-lookup"><span data-stu-id="01283-112">Attack surface reduction features across Windows versions</span></span>

<span data-ttu-id="01283-113">次のエディションとバージョンのデバイスを実行しているデバイスに対して攻撃表面の縮小ルールをWindows。</span><span class="sxs-lookup"><span data-stu-id="01283-113">You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="01283-114">Windows 10 Proバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="01283-114">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="01283-115">Windows 10 Enterpriseバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="01283-115">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="01283-116">Windowsサーバー、[バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降</span><span class="sxs-lookup"><span data-stu-id="01283-116">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="01283-117">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="01283-117">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="01283-118">攻撃表面の縮小ルールの機能セット全体を使用するには、以下が必要です。</span><span class="sxs-lookup"><span data-stu-id="01283-118">To use the entire feature-set of attack surface reduction rules, you need:</span></span>

- <span data-ttu-id="01283-119">Windows Defender ウイルス対策 AV として設定する (リアルタイム保護オン)</span><span class="sxs-lookup"><span data-stu-id="01283-119">Windows Defender Antivirus as primary AV (real-time protection on)</span></span>
- <span data-ttu-id="01283-120">[Cloud-Delivery Protection on](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) (一部のルールでは必要)</span><span class="sxs-lookup"><span data-stu-id="01283-120">[Cloud-Delivery Protection](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) on (some rules require that)</span></span>
- <span data-ttu-id="01283-121">Windows 10 EnterpriseE5 または E3 ライセンスまたはMicrosoft 365ビジネス ライセンス</span><span class="sxs-lookup"><span data-stu-id="01283-121">Windows 10 Enterprise E5 or E3 License or Microsoft 365 Business License</span></span>

<span data-ttu-id="01283-122">攻撃表面の縮小ルールでは[、Windows E5](/windows/deployment/deploy-enterprise-licenses)ライセンスを使用して Windows E5 ライセンスを必要としますが、Defender for Endpoint で使用できる監視、分析、ワークフロー、および Microsoft 365 セキュリティ センターのレポート機能と構成機能などの高度な管理機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="01283-122">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), with a Windows E5 license, you get advanced management capabilities including monitoring, analytics, and workflows available in Defender for Endpoint, as well as reporting and configuration capabilities in the Microsoft 365 security center.</span></span> <span data-ttu-id="01283-123">これらの高度な機能は E3 ライセンスでは使用できませんが、イベント ビューアーを使用して攻撃表面の縮小ルール イベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="01283-123">These advanced capabilities aren't available with an E3 license, but you can still use Event Viewer to review attack surface reduction rule events.</span></span>

<span data-ttu-id="01283-124">各 ASR ルールには、次の 4 つの設定のいずれかを含む。</span><span class="sxs-lookup"><span data-stu-id="01283-124">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="01283-125">**構成されていません**: ASR ルールを無効にする</span><span class="sxs-lookup"><span data-stu-id="01283-125">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="01283-126">**ブロック**: ASR ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="01283-126">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="01283-127">**監査**: ASR ルールが有効な場合に組織に与える影響を評価する</span><span class="sxs-lookup"><span data-stu-id="01283-127">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="01283-128">**警告**: ASR ルールを有効にするが、エンド ユーザーがブロックをバイパスできる</span><span class="sxs-lookup"><span data-stu-id="01283-128">**Warn**: Enable the ASR rule but allow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01283-129">現在、警告モードは、3 つの ASR ルール (MEM) で ASR ルールを構成するときにMicrosoft エンドポイント マネージャーサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="01283-129">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="01283-130">詳細については、「警告モード [がサポートされていないケース」を参照してください](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)。</span><span class="sxs-lookup"><span data-stu-id="01283-130">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="01283-131">microsoft [Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint) で利用可能な高度な監視およびレポート機能を利用するには、Windows E5 ライセンス (または類似のライセンス SKU) で ASR ルールを使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="01283-131">It's highly recommended to use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) (Defender for Endpoint).</span></span> <span data-ttu-id="01283-132">ただし、高度な監視機能やレポート機能を含む Windows Professional や Windows E3 などの別のライセンスがある場合は、ASR ルールがトリガーされる際に各エンドポイントで生成されるイベント (イベント転送など) の上に独自の監視およびレポート ツールを開発できます。</span><span class="sxs-lookup"><span data-stu-id="01283-132">However, if you have another license, such as Windows Professional or Windows E3 that don't include advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (for example, Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="01283-133">ライセンスの詳細については、「Windows ライセンス」を参照し[](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5)Windows 10ボリューム ライセンス ガイド[を](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)参照Windows 10。</span><span class="sxs-lookup"><span data-stu-id="01283-133">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="01283-134">攻撃表面の縮小ルールは、次の方法で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="01283-134">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="01283-135">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="01283-135">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="01283-136">モバイル デバイス管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="01283-136">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="01283-137">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="01283-137">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="01283-138">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="01283-138">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="01283-139">PowerShell</span><span class="sxs-lookup"><span data-stu-id="01283-139">PowerShell</span></span>](#powershell)

<span data-ttu-id="01283-140">Enterprise、Intune などのレベルのMicrosoft エンドポイント マネージャーをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="01283-140">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="01283-141">Enterpriseレベルの管理では、起動時に競合するグループ ポリシーまたは PowerShell 設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="01283-141">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="01283-142">ASR ルールからファイルとフォルダーを除外する</span><span class="sxs-lookup"><span data-stu-id="01283-142">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="01283-143">ほとんどの攻撃表面の縮小ルールによってファイルとフォルダーが評価されるのを除外できます。</span><span class="sxs-lookup"><span data-stu-id="01283-143">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="01283-144">つまり、ASR ルールがファイルまたはフォルダーに悪意のある動作が含まれていると判断した場合でも、ファイルの実行をブロックしません。</span><span class="sxs-lookup"><span data-stu-id="01283-144">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="01283-145">これにより、安全でないファイルを実行してデバイスに感染する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01283-145">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="01283-146">指定された Defender for Endpoint ファイルと証明書インジケーターを許可することで、証明書とファイル ハッシュに基づいて ASR ルールをトリガーから除外することもできます。</span><span class="sxs-lookup"><span data-stu-id="01283-146">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="01283-147">(「指標 [の管理」を参照](manage-indicators.md)してください。</span><span class="sxs-lookup"><span data-stu-id="01283-147">(See [Manage indicators](manage-indicators.md).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01283-148">ファイルまたはフォルダーを除外すると、ASR ルールによって提供される保護が大幅に低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01283-148">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="01283-149">除外されたファイルの実行が許可され、レポートやイベントは記録されません。</span><span class="sxs-lookup"><span data-stu-id="01283-149">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="01283-150">ASR ルールで検出すべきではないと思うファイルを検出する場合は、まず監査モードを使用して [ルールをテストする必要があります](evaluate-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="01283-150">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="01283-151">個々のファイルまたはフォルダー (フォルダー パスまたは完全修飾リソース名を使用) を指定できますが、除外が適用されるルールを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="01283-151">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="01283-152">除外は、除外されたアプリケーションまたはサービスが開始された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="01283-152">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="01283-153">たとえば、既に実行されている更新サービスの除外を追加すると、サービスが停止して再起動されるまで、更新サービスはイベントをトリガーし続ける。</span><span class="sxs-lookup"><span data-stu-id="01283-153">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="01283-154">ASR ルールは、環境変数とワイルドカードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="01283-154">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="01283-155">ワイルドカードの使用の詳細については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する」 [を参照してください](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。</span><span class="sxs-lookup"><span data-stu-id="01283-155">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="01283-156">ASR ルールを有効にする次の手順には、ファイルとフォルダーを除外する方法の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="01283-156">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="01283-157">Intune</span><span class="sxs-lookup"><span data-stu-id="01283-157">Intune</span></span>

1. <span data-ttu-id="01283-158">[デバイス **構成プロファイル**  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="01283-158">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="01283-159">既存のエンドポイント保護プロファイルを選択するか、新しいエンドポイント保護プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="01283-159">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="01283-160">新しいプロファイルを作成するには、[プロファイルの作成] **を選択し** 、このプロファイルの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="01283-160">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="01283-161">[プロファイル **の種類] で**、[ **エンドポイント保護] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="01283-161">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="01283-162">既存のプロファイルを選択した場合は、[プロパティ] を選択 **し、[プロパティ**] を選択 **設定。**</span><span class="sxs-lookup"><span data-stu-id="01283-162">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="01283-163">[エンドポイント保護 **] ウィンドウで**、[Exploit **Guard] をWindows Defenderし**、[攻撃表面の縮小 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="01283-163">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="01283-164">各 ASR ルールの目的の設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="01283-164">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="01283-165">[ **攻撃表面の縮小の例外] で**、個々のファイルとフォルダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="01283-165">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="01283-166">[インポート] を **選択して** 、ASR ルールから除外するファイルとフォルダーを含む CSV ファイルをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="01283-166">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="01283-167">CSV ファイルの各行は、次のように書式設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="01283-167">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="01283-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="01283-168">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="01283-169">3 つの構成ウィンドウで **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01283-169">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="01283-170">次に、**新しい** エンドポイント保護ファイルを作成する場合は[作成] を選択し、既存のエンドポイント保護ファイルを編集する場合は [保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01283-170">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mem"></a><span data-ttu-id="01283-171">MEM</span><span class="sxs-lookup"><span data-stu-id="01283-171">MEM</span></span>

<span data-ttu-id="01283-172">カスタム ASR ルールMicrosoft エンドポイント マネージャー(MEM) OMA-URI を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="01283-172">You can use Microsoft Endpoint Manager (MEM) OMA-URI to configure custom ASR rules.</span></span> <span data-ttu-id="01283-173">次の手順では、この例で「悪用された脆弱な署名済みドライバーの悪用を [ブロックする」](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) というルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="01283-173">The following procedure uses the rule [Block abuse of exploited vulnerable signed drivers](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) for the example.</span></span>

1. <span data-ttu-id="01283-174">新しいMicrosoft エンドポイント マネージャー (MEM) 管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="01283-174">Open the Microsoft Endpoint Manager (MEM) admin center.</span></span> <span data-ttu-id="01283-175">[ホーム] **メニューの [** デバイス] を  **クリックし**、[構成プロファイル] **を** 選択し、[プロファイルの作成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="01283-175">In the **Home** menu, click  **Devices**, select **Configuration profile**, and then click **Create profile**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01283-176">![MEM Create Profile](images/mem01-create-profile.png)</span><span class="sxs-lookup"><span data-stu-id="01283-176">![MEM Create Profile](images/mem01-create-profile.png)</span></span>

2. <span data-ttu-id="01283-177">[ **プロファイルの作成]** で、次の 2 つのドロップダウン リストで、次の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="01283-177">In **Create a profile**, in the following two drop-down lists, select the following:</span></span>

   - <span data-ttu-id="01283-178">[**プラットフォーム]** で、[Windows 10 **以降] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="01283-178">In **Platform**, select **Windows 10 and later**</span></span>
   - <span data-ttu-id="01283-179">[ **プロファイルの種類] で**、[ **テンプレート] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="01283-179">In **Profile type**, select **Templates**</span></span>

   <span data-ttu-id="01283-180">[カスタム **] を** 選択し、[作成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="01283-180">Select **Custom**, and then click **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01283-181">![MEM ルール プロファイルの属性](images/mem02-profile-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="01283-181">![MEM rule profile attributes](images/mem02-profile-attributes.png)</span></span>

3. <span data-ttu-id="01283-182">[カスタム テンプレート] ツールが開き、手順 **1 [基本] に進みます**。</span><span class="sxs-lookup"><span data-stu-id="01283-182">The Custom template tool opens to step **1 Basics**.</span></span> <span data-ttu-id="01283-183">**[1 基本]** の [**名前]** にテンプレートの名前を入力し、[説明] に説明を入力できます (オプション)。</span><span class="sxs-lookup"><span data-stu-id="01283-183">In **1 Basics**, in **Name**, type a name for your template, and in **Description** you can type a description (optional).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01283-184">![MEM の基本的な属性](images/mem03-1-basics.png)</span><span class="sxs-lookup"><span data-stu-id="01283-184">![MEM basic attributes](images/mem03-1-basics.png)</span></span>

4. <span data-ttu-id="01283-185">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01283-185">Click **Next**.</span></span> <span data-ttu-id="01283-186">手順 **2 構成設定が開** きます。</span><span class="sxs-lookup"><span data-stu-id="01283-186">Step **2 Configuration settings** opens.</span></span> <span data-ttu-id="01283-187">[OMA-URI] の設定をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="01283-187">For OMA-URI Settings, click **Add**.</span></span> <span data-ttu-id="01283-188">2 つのオプションが表示 **されます。**</span><span class="sxs-lookup"><span data-stu-id="01283-188">Two options now appear: **Add** and **Export**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01283-189">![MEM 構成の設定](images/mem04-2-configuration-settings.png)</span><span class="sxs-lookup"><span data-stu-id="01283-189">![MEM Configuration settings](images/mem04-2-configuration-settings.png)</span></span>

5. <span data-ttu-id="01283-190">[追加 **] を再度クリック** します。</span><span class="sxs-lookup"><span data-stu-id="01283-190">Click **Add** again.</span></span> <span data-ttu-id="01283-191">[**行 OMA-URI の追加] 設定** 開きます。</span><span class="sxs-lookup"><span data-stu-id="01283-191">The **Add Row OMA-URI Settings** opens.</span></span> <span data-ttu-id="01283-192">[ **行の追加]** で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="01283-192">In **Add Row**, do the following:</span></span>

   - <span data-ttu-id="01283-193">[ **名前]** に、ルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="01283-193">In **Name**, type a name for the rule.</span></span>
   - <span data-ttu-id="01283-194">[ **説明]** に簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="01283-194">In **Description**, type a brief description.</span></span>
   - <span data-ttu-id="01283-195">**OMA-URI で**、追加するルールの特定の OMA-URI リンクを入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="01283-195">In **OMA-URI**, type or paste the specific OMA-URI link for the rule that you are adding.</span></span>
   - <span data-ttu-id="01283-196">[ **データ型] で**、[文字列] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="01283-196">In **Data type**, select **String**.</span></span>
   - <span data-ttu-id="01283-197">[ **値]** で、GUID 値、記号、およびスペースを含む State 値 \= _(GUID=StateValue) を入力または貼り付けます_。</span><span class="sxs-lookup"><span data-stu-id="01283-197">In **Value**, type or paste the GUID value, the \= sign and the State value with no spaces (_GUID=StateValue_).</span></span> <span data-ttu-id="01283-198">Where: {0 : Disable (DISABLE the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (有効な場合は ASR ルールが組織に与える影響を評価する)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span><span class="sxs-lookup"><span data-stu-id="01283-198">Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01283-199">![MEM OMA URI 構成](images/mem05-add-row-oma-uri.png)</span><span class="sxs-lookup"><span data-stu-id="01283-199">![MEM OMA URI configuration](images/mem05-add-row-oma-uri.png)</span></span>

6. <span data-ttu-id="01283-200">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01283-200">Click **Save**.</span></span> <span data-ttu-id="01283-201">**[行の追加]** が閉じます。</span><span class="sxs-lookup"><span data-stu-id="01283-201">**Add Row** closes.</span></span> <span data-ttu-id="01283-202">[カスタム **] で**、[次へ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="01283-202">In **Custom**, click **Next**.</span></span> <span data-ttu-id="01283-203">手順 **3 スコープ タグでは、** スコープ タグは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="01283-203">In step **3 Scope tags**, scope tags are optional.</span></span> <span data-ttu-id="01283-204">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="01283-204">Do one of the following:</span></span>

   - <span data-ttu-id="01283-205">[ **スコープ タグの選択]** をクリックし、スコープ タグ (オプション) を選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="01283-205">Click **Select Scope tags**, select the scope tag (optional) and then click **Next**.</span></span>
   - <span data-ttu-id="01283-206">または、[次へ] **をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="01283-206">Or click **Next**</span></span>

7. <span data-ttu-id="01283-207">手順 **4 [割り当** て] の **[含** まれるグループ] で、このルールを適用するグループの場合は、次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="01283-207">In step **4 Assignments**, in **Included Groups** - for the groups that you want this rule to apply - select from the following options:</span></span>

   - <span data-ttu-id="01283-208">**グループの追加**</span><span class="sxs-lookup"><span data-stu-id="01283-208">**Add groups**</span></span>
   - <span data-ttu-id="01283-209">**すべてのユーザーを追加する**</span><span class="sxs-lookup"><span data-stu-id="01283-209">**Add all users**</span></span>
   - <span data-ttu-id="01283-210">**すべてのデバイスを追加する**</span><span class="sxs-lookup"><span data-stu-id="01283-210">**Add all devices**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01283-211">![MEM の割り当て](images/mem06-4-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="01283-211">![MEM assignments](images/mem06-4-assignments.png)</span></span>

8. <span data-ttu-id="01283-212">[ **除外グループ] で**、このルールから除外するグループを選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="01283-212">In **Excluded groups**, select any groups that you want to exclude from this rule, and then click **Next**.</span></span>

9. <span data-ttu-id="01283-213">手順 **5 次の設定の** 適用ルールで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="01283-213">In step **5 Applicability Rules** for the following settings, do the following:</span></span>

   - <span data-ttu-id="01283-214">[ **ルール] で**、[プロファイルを **割り当てる場合**] または [プロファイルを割り当 **てない場合] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="01283-214">In **Rule**, select either **Assign profile if**, or **Don’t assign profile if**</span></span>
   - <span data-ttu-id="01283-215">[ **プロパティ**] で、このルールを適用するプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="01283-215">In **Property**, select the property to which you want this rule to apply</span></span>
   - <span data-ttu-id="01283-216">[ **値]** に、該当する値または値の範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="01283-216">In **Value**, enter the applicable value or value range</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="01283-217">![MEM 適用ルール](images/mem07-5-applicability-rules.png)</span><span class="sxs-lookup"><span data-stu-id="01283-217">![MEM Applicability rules](images/mem07-5-applicability-rules.png)</span></span>

10. <span data-ttu-id="01283-218">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01283-218">Click **Next**.</span></span> <span data-ttu-id="01283-219">手順 **6 [レビュー] + [作成**] で、選択して入力した設定と情報を確認し、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="01283-219">In step **6 Review + create**, review the settings and information you have selected and entered, and then click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="01283-220">![MEM レビューと作成](images/mem08-6-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="01283-220">![MEM Review and create](images/mem08-6-review-create.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="01283-221">ルールはアクティブで、数分以内に有効です。</span><span class="sxs-lookup"><span data-stu-id="01283-221">Rules are active and live within minutes.</span></span>

>[!NOTE]
> <span data-ttu-id="01283-222">競合の処理:</span><span class="sxs-lookup"><span data-stu-id="01283-222">Conflict handling:</span></span>
>
> <span data-ttu-id="01283-223">デバイスに 2 つの異なる ASR ポリシーを割り当てると、競合の処理方法は、異なる状態が割り当てられたルールであり、競合管理が行われるので、結果はエラーになります。</span><span class="sxs-lookup"><span data-stu-id="01283-223">If you assign a device two different ASR policies, the way conflict is handled is rules that are assigned different states, there is no conflict management in place, and the result is an error.</span></span>
>
> <span data-ttu-id="01283-224">競合しないルールではエラーが発生し、ルールが正しく適用されます。</span><span class="sxs-lookup"><span data-stu-id="01283-224">Non-conflicting rules will not result in an error, and the rule will be applied correctly.</span></span> <span data-ttu-id="01283-225">その結果、最初のルールが適用され、それ以降の競合しないルールがポリシーにマージされます。</span><span class="sxs-lookup"><span data-stu-id="01283-225">The result is that the first rule is applied, and subsequent non-conflicting rules are merged into the policy.</span></span>

## <a name="mdm"></a><span data-ttu-id="01283-226">MDM</span><span class="sxs-lookup"><span data-stu-id="01283-226">MDM</span></span>

<span data-ttu-id="01283-227">各ルールのモードを個別に有効にして設定するには [、./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) 構成サービス プロバイダー (CSP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="01283-227">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="01283-228">ASR ルールに GUID 値を使用して参照 [するサンプルを次に示します](attack-surface-reduction.md#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="01283-228">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="01283-229">監査モードで有効 (ブロック)、無効化、警告、または有効にする値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="01283-229">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="01283-230">0 : 無効にする (ASR ルールを無効にする)</span><span class="sxs-lookup"><span data-stu-id="01283-230">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="01283-231">1 : ブロック (ASR ルールを有効にする)</span><span class="sxs-lookup"><span data-stu-id="01283-231">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="01283-232">2 : 監査 (ASR ルールが有効な場合に組織に与える影響を評価する)</span><span class="sxs-lookup"><span data-stu-id="01283-232">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="01283-233">6 : 警告 (ASR ルールを有効にするが、エンド ユーザーがブロックをバイパスできる)。</span><span class="sxs-lookup"><span data-stu-id="01283-233">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="01283-234">警告モードは、ほとんどの ASR ルールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="01283-234">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="01283-235">除外を追加するには [、./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 構成サービス プロバイダー (CSP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="01283-235">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="01283-236">例:</span><span class="sxs-lookup"><span data-stu-id="01283-236">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="01283-237">スペースを使用せずに OMA-URI 値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="01283-237">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="01283-238">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="01283-238">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="01283-239">この **Microsoft Endpoint Configuration Manager、Exploit** Guard の [アセットと  >  **コンプライアンス] Endpoint Protection Windows Defender**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="01283-239">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="01283-240">[ホーム **エクスプ**  >  **ロイト ガード ポリシーの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="01283-240">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="01283-241">名前と説明を入力し、[攻撃表面の縮小] を **選択** し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="01283-241">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="01283-242">アクションをブロックまたは監査するルールを選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="01283-242">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="01283-243">設定を確認し、[次へ] **を選択** してポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="01283-243">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="01283-244">ポリシーが作成された後、閉 **じます**。</span><span class="sxs-lookup"><span data-stu-id="01283-244">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="01283-245">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="01283-245">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="01283-246">Intune、Configuration Manager、または他のエンタープライズ レベルの管理プラットフォームを使用してコンピューターとデバイスを管理する場合、管理ソフトウェアは起動時に競合するグループ ポリシー設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="01283-246">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="01283-247">グループ ポリシー管理コンピューターで、[[グループ ポリシー管理コンソール]](https://technet.microsoft.com/library/cc731212.aspx) を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01283-247">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="01283-248">**[グループ ポリシー管理エディター]** で、**[コンピューターの構成]** に移動し、**[管理用テンプレート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="01283-248">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="01283-249">ツリーを展開して **、攻撃Windows縮小**  >  **Microsoft Defender ウイルス対策Microsoft Defender Exploit Guard**  >    >  **コンポーネントを表示します**。</span><span class="sxs-lookup"><span data-stu-id="01283-249">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="01283-250">[攻撃 **表面縮小ルールの構成] を選択し、[** 有効] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="01283-250">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="01283-251">その後、[オプション] セクションで各ルールの個別の状態を設定できます。</span><span class="sxs-lookup"><span data-stu-id="01283-251">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="01283-252">**[Show....]** を選択し、[値名] 列にルール ID を入力し、[値] 列に選択した状態 **を** 次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="01283-252">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="01283-253">0 : 無効にする (ASR ルールを無効にする)</span><span class="sxs-lookup"><span data-stu-id="01283-253">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="01283-254">1 : ブロック (ASR ルールを有効にする)</span><span class="sxs-lookup"><span data-stu-id="01283-254">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="01283-255">2 : 監査 (ASR ルールが有効な場合に組織に与える影響を評価する)</span><span class="sxs-lookup"><span data-stu-id="01283-255">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="01283-256">6 : 警告 (ASR ルールを有効にするが、エンド ユーザーがブロックをバイパスできる)</span><span class="sxs-lookup"><span data-stu-id="01283-256">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="グループ ポリシーの ASR ルール":::

5. <span data-ttu-id="01283-258">ASR ルールからファイルとフォルダーを除外するには、[攻撃表面の縮小ルールからファイルとパスを除外する] 設定を選択し、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="01283-258">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="01283-259">[ **表示] を** 選択し、[値の名前] 列に各ファイル **またはフォルダーを入力** します。</span><span class="sxs-lookup"><span data-stu-id="01283-259">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="01283-260">各 **アイテムの [** 値] **列に 0** を入力します。</span><span class="sxs-lookup"><span data-stu-id="01283-260">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="01283-261">[値の名前] 列または [値] 列でサポートされていない引用符は **使用** しません。</span><span class="sxs-lookup"><span data-stu-id="01283-261">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="01283-262">PowerShell</span><span class="sxs-lookup"><span data-stu-id="01283-262">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="01283-263">Intune、Configuration Manager、または別のエンタープライズ レベルの管理プラットフォームを使用してコンピューターとデバイスを管理すると、起動時に競合する PowerShell 設定が管理ソフトウェアによって上書きされます。</span><span class="sxs-lookup"><span data-stu-id="01283-263">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="01283-264">PowerShell を使用して値を定義するには、管理プラットフォームのルールに "User Defined" オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="01283-264">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="01283-265">**[powershell]** と入力スタート メニュー **右クリックし**、[管理者Windows PowerShell **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="01283-265">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="01283-266">次の cmdlet を入力します。</span><span class="sxs-lookup"><span data-stu-id="01283-266">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="01283-267">監査モードで ASR ルールを有効にするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="01283-267">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="01283-268">警告モードで ASR ルールを有効にするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="01283-268">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="01283-269">悪用された脆弱な署名済みドライバーの ASR ブロックの悪用を有効にするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="01283-269">To enable ASR Block abuse of exploited vulnerable signed drivers, use the following cmdlet:</span></span>

   ```PowerShell
   Add-MpPreference -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled
   ```

    <span data-ttu-id="01283-270">ASR ルールをオフにするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="01283-270">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="01283-271">ルールごとに状態を個別に指定する必要がありますが、コンマ区切りのリストでルールと状態を組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="01283-271">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="01283-272">次の例では、最初の 2 つのルールが有効になり、3 番目のルールが無効になり、4 番目のルールが監査モードで有効になります。</span><span class="sxs-lookup"><span data-stu-id="01283-272">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="01283-273">PowerShell 動詞を使用 `Add-MpPreference` して、既存のリストに新しいルールを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="01283-273">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="01283-274">`Set-MpPreference` ルールの既存のセットは常に上書きされます。</span><span class="sxs-lookup"><span data-stu-id="01283-274">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="01283-275">既存のセットに追加する場合は、代わりに `Add-MpPreference` 使用します。</span><span class="sxs-lookup"><span data-stu-id="01283-275">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="01283-276">を使用して、ルールとその現在の状態の一覧を取得できます `Get-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="01283-276">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="01283-277">ASR ルールからファイルとフォルダーを除外するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="01283-277">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="01283-278">引き続き使用 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` して、リストにファイルとフォルダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="01283-278">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="01283-279">リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="01283-279">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="01283-280">コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="01283-280">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="01283-281">関連記事</span><span class="sxs-lookup"><span data-stu-id="01283-281">Related articles</span></span>

- [<span data-ttu-id="01283-282">攻撃表面の縮小ルールを使用して攻撃表面を削減する</span><span class="sxs-lookup"><span data-stu-id="01283-282">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="01283-283">攻撃表面の縮小を評価する</span><span class="sxs-lookup"><span data-stu-id="01283-283">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="01283-284">攻撃面の減少の FAQ</span><span class="sxs-lookup"><span data-stu-id="01283-284">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
