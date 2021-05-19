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
ms.openlocfilehash: b3460e2c9b6073c518bea46147be69d4b89cd96a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538641"
---
# <a name="enable-attack-surface-reduction-rules"></a><span data-ttu-id="d97b6-104">攻撃面の減少ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="d97b6-104">Enable attack surface reduction rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d97b6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d97b6-105">**Applies to:**</span></span>

- [<span data-ttu-id="d97b6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d97b6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d97b6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d97b6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="d97b6-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="d97b6-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d97b6-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="d97b6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="d97b6-110">[攻撃表面の縮小ルール](attack-surface-reduction.md) (ASR ルール) は、マルウェアが頻繁にデバイスやネットワークを侵害するアクションを防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-110">[Attack surface reduction rules](attack-surface-reduction.md) (ASR rules) help prevent actions that malware often abuses to compromise devices and networks.</span></span>

<span data-ttu-id="d97b6-111">**要件** 次のエディションとバージョンのデバイスを実行しているデバイスに対して攻撃表面の縮小ルールをWindows。</span><span class="sxs-lookup"><span data-stu-id="d97b6-111">**Requirements** You can set attack surface reduction rules for devices that are running any of the following editions and versions of Windows:</span></span>

- <span data-ttu-id="d97b6-112">Windows 10 Proバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="d97b6-112">Windows 10 Pro, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="d97b6-113">Windows 10 Enterpriseバージョン[1709](/windows/whats-new/whats-new-windows-10-version-1709)以降</span><span class="sxs-lookup"><span data-stu-id="d97b6-113">Windows 10 Enterprise, [version 1709](/windows/whats-new/whats-new-windows-10-version-1709) or later</span></span>
- <span data-ttu-id="d97b6-114">Windowsサーバー、[バージョン 1803 (半期チャネル)](/windows-server/get-started/whats-new-in-windows-server-1803)以降</span><span class="sxs-lookup"><span data-stu-id="d97b6-114">Windows Server, [version 1803 (Semi-Annual Channel)](/windows-server/get-started/whats-new-in-windows-server-1803) or later</span></span>
- [<span data-ttu-id="d97b6-115">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="d97b6-115">Windows Server 2019</span></span>](/windows-server/get-started-19/whats-new-19)

<span data-ttu-id="d97b6-116">攻撃表面の縮小ルールでは[E5](/windows/deployment/deploy-enterprise-licenses)ライセンスをWindows必要とWindows、高度な管理機能を利用できます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-116">Although attack surface reduction rules don't require a [Windows E5 license](/windows/deployment/deploy-enterprise-licenses), if you have Windows E5, you get advanced management capabilities.</span></span> <span data-ttu-id="d97b6-117">Windows E5 でのみ使用できるこれらの機能には[、Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true)で使用できる監視、分析、ワークフロー、および Microsoft 365 セキュリティ センターのレポート機能と構成[機能が含まれます](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="d97b6-117">These capabilities available only in Windows E5 include monitoring, analytics, and workflows available in [Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true), as well as reporting and configuration capabilities in the [Microsoft 365 security center](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true).</span></span> <span data-ttu-id="d97b6-118">これらの高度な機能は、E3 ライセンスWindows ProfessionalまたはWindows使用できません。ただし、これらのライセンスを持っている場合は、イベント ビューアーとログMicrosoft Defender ウイルス対策を使用して、攻撃表面の縮小ルール イベントを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-118">These advanced capabilities aren't available with a Windows Professional or Windows E3 license; however, if you do have those licenses, you can use Event Viewer and Microsoft Defender Antivirus logs to review your attack surface reduction rule events.</span></span>

<span data-ttu-id="d97b6-119">各 ASR ルールには、次の 4 つの設定のいずれかを含む。</span><span class="sxs-lookup"><span data-stu-id="d97b6-119">Each ASR rule contains one of four settings:</span></span>

- <span data-ttu-id="d97b6-120">**構成されていません**: ASR ルールを無効にする</span><span class="sxs-lookup"><span data-stu-id="d97b6-120">**Not configured**: Disable the ASR rule</span></span>
- <span data-ttu-id="d97b6-121">**ブロック**: ASR ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="d97b6-121">**Block**: Enable the ASR rule</span></span>
- <span data-ttu-id="d97b6-122">**監査**: ASR ルールが有効な場合に組織に与える影響を評価する</span><span class="sxs-lookup"><span data-stu-id="d97b6-122">**Audit**: Evaluate how the ASR rule would impact your organization if enabled</span></span>
- <span data-ttu-id="d97b6-123">**警告**: ASR ルールを有効にするが、エンド ユーザーがブロックをバイパスできる</span><span class="sxs-lookup"><span data-stu-id="d97b6-123">**Warn**: Enable the ASR rule but allow the end user to bypass the block</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d97b6-124">現在、警告モードは、3 つの ASR ルール (MEM) で ASR ルールを構成するときにMicrosoft エンドポイント マネージャーサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d97b6-124">Currently, warn mode is not supported for three ASR rules when you configure ASR rules in Microsoft Endpoint Manager (MEM).</span></span> <span data-ttu-id="d97b6-125">詳細については、「警告モード [がサポートされていないケース」を参照してください](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)。</span><span class="sxs-lookup"><span data-stu-id="d97b6-125">To learn more, see [Cases where warn mode is not supported](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported).</span></span>

<span data-ttu-id="d97b6-126">microsoft [Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint) で利用可能な高度な監視およびレポート機能を利用するには、Windows E5 ライセンス (または類似のライセンス SKU) で ASR ルールを使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d97b6-126">It's highly recommended you use ASR rules with a Windows E5 license (or similar licensing SKU) to take advantage of the advanced monitoring and reporting capabilities available in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint).</span></span> <span data-ttu-id="d97b6-127">ただし、高度な監視およびレポート機能にアクセスできない Windows Professional や E3 などの他のライセンスの場合は、ASR ルールがトリガーされる際に各エンドポイントで生成されるイベント (イベント転送など) の上に独自の監視およびレポート ツールを開発できます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-127">However, for other licenses like Windows Professional or E3 that don't have access to advanced monitoring and reporting capabilities, you can develop your own monitoring and reporting tools on top of the events that are generated at each endpoint when ASR rules are triggered (e.g., Event Forwarding).</span></span>

> [!TIP]
> <span data-ttu-id="d97b6-128">ライセンスの詳細については、「Windows ライセンス」を参照し[](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5)Windows 10ボリューム ライセンス ガイド[を](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)参照Windows 10。</span><span class="sxs-lookup"><span data-stu-id="d97b6-128">To learn more about Windows licensing, see [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the [Volume Licensing guide for Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).</span></span>

<span data-ttu-id="d97b6-129">攻撃表面の縮小ルールは、次の方法で有効にできます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-129">You can enable attack surface reduction rules by using any of these methods:</span></span>

- [<span data-ttu-id="d97b6-130">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d97b6-130">Microsoft Intune</span></span>](#intune)
- [<span data-ttu-id="d97b6-131">モバイル デバイス管理 (MDM)</span><span class="sxs-lookup"><span data-stu-id="d97b6-131">Mobile Device Management (MDM)</span></span>](#mdm)
- [<span data-ttu-id="d97b6-132">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d97b6-132">Microsoft Endpoint Configuration Manager</span></span>](#microsoft-endpoint-configuration-manager)
- [<span data-ttu-id="d97b6-133">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="d97b6-133">Group Policy</span></span>](#group-policy)
- [<span data-ttu-id="d97b6-134">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d97b6-134">PowerShell</span></span>](#powershell)

<span data-ttu-id="d97b6-135">Enterprise、Intune などのレベルのMicrosoft エンドポイント マネージャーをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d97b6-135">Enterprise-level management such as Intune or Microsoft Endpoint Manager is recommended.</span></span> <span data-ttu-id="d97b6-136">Enterpriseレベルの管理では、起動時に競合するグループ ポリシーまたは PowerShell 設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-136">Enterprise-level management will overwrite any conflicting Group Policy or PowerShell settings on startup.</span></span>

## <a name="exclude-files-and-folders-from-asr-rules"></a><span data-ttu-id="d97b6-137">ASR ルールからファイルとフォルダーを除外する</span><span class="sxs-lookup"><span data-stu-id="d97b6-137">Exclude files and folders from ASR rules</span></span>

<span data-ttu-id="d97b6-138">ほとんどの攻撃表面の縮小ルールによってファイルとフォルダーが評価されるのを除外できます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-138">You can exclude files and folders from being evaluated by most attack surface reduction rules.</span></span> <span data-ttu-id="d97b6-139">つまり、ASR ルールがファイルまたはフォルダーに悪意のある動作が含まれていると判断した場合でも、ファイルの実行をブロックしません。</span><span class="sxs-lookup"><span data-stu-id="d97b6-139">This means that even if an ASR rule determines the file or folder contains malicious behavior, it will not block the file from running.</span></span> <span data-ttu-id="d97b6-140">これにより、安全でないファイルを実行してデバイスに感染する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d97b6-140">This could potentially allow unsafe files to run and infect your devices.</span></span>

<span data-ttu-id="d97b6-141">指定された Defender for Endpoint ファイルと証明書インジケーターを許可することで、証明書とファイル ハッシュに基づいて ASR ルールをトリガーから除外することもできます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-141">You can also exclude ASR rules from triggering based on certificate and file hashes by allowing specified Defender for Endpoint file and certificate indicators.</span></span> <span data-ttu-id="d97b6-142">(「指標 [の管理」を参照](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)してください。</span><span class="sxs-lookup"><span data-stu-id="d97b6-142">(See [Manage indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d97b6-143">ファイルまたはフォルダーを除外すると、ASR ルールによって提供される保護が大幅に低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d97b6-143">Excluding files or folders can severely reduce the protection provided by ASR rules.</span></span> <span data-ttu-id="d97b6-144">除外されたファイルの実行が許可され、レポートやイベントは記録されません。</span><span class="sxs-lookup"><span data-stu-id="d97b6-144">Excluded files will be allowed to run, and no report or event will be recorded.</span></span>
> <span data-ttu-id="d97b6-145">ASR ルールで検出すべきではないと思うファイルを検出する場合は、まず監査モードを使用して [ルールをテストする必要があります](evaluate-attack-surface-reduction.md)。</span><span class="sxs-lookup"><span data-stu-id="d97b6-145">If ASR rules are detecting files that you believe shouldn't be detected, you should [use audit mode first to test the rule](evaluate-attack-surface-reduction.md).</span></span>

<span data-ttu-id="d97b6-146">個々のファイルまたはフォルダー (フォルダー パスまたは完全修飾リソース名を使用) を指定できますが、除外が適用されるルールを指定することはできません。</span><span class="sxs-lookup"><span data-stu-id="d97b6-146">You can specify individual files or folders (using folder paths or fully qualified resource names), but you can't specify which rules the exclusions apply to.</span></span> <span data-ttu-id="d97b6-147">除外は、除外されたアプリケーションまたはサービスが開始された場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-147">An exclusion is applied only when the excluded application or service starts.</span></span> <span data-ttu-id="d97b6-148">たとえば、既に実行されている更新サービスの除外を追加すると、サービスが停止して再起動されるまで、更新サービスはイベントをトリガーし続ける。</span><span class="sxs-lookup"><span data-stu-id="d97b6-148">For example, if you add an exclusion for an update service that is already running, the update service will continue to trigger events until the service is stopped and restarted.</span></span>

<span data-ttu-id="d97b6-149">ASR ルールは、環境変数とワイルドカードをサポートします。</span><span class="sxs-lookup"><span data-stu-id="d97b6-149">ASR rules support environment variables and wildcards.</span></span> <span data-ttu-id="d97b6-150">ワイルドカードの使用の詳細については、「ファイル名とフォルダー パスまたは拡張子の除外リストでワイルドカードを使用する」 [を参照してください](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)。</span><span class="sxs-lookup"><span data-stu-id="d97b6-150">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="d97b6-151">ASR ルールを有効にする次の手順には、ファイルとフォルダーを除外する方法の手順が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-151">The following procedures for enabling ASR rules include instructions for how to exclude files and folders.</span></span>

## <a name="intune"></a><span data-ttu-id="d97b6-152">Intune</span><span class="sxs-lookup"><span data-stu-id="d97b6-152">Intune</span></span>

1. <span data-ttu-id="d97b6-153">[デバイス **構成プロファイル**  >  **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-153">Select **Device configuration** > **Profiles**.</span></span> <span data-ttu-id="d97b6-154">既存のエンドポイント保護プロファイルを選択するか、新しいエンドポイント保護プロファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-154">Choose an existing endpoint protection profile or create a new one.</span></span> <span data-ttu-id="d97b6-155">新しいプロファイルを作成するには、[プロファイルの作成] **を選択し** 、このプロファイルの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-155">To create a new one, select **Create profile** and enter information for this profile.</span></span> <span data-ttu-id="d97b6-156">[プロファイル **の種類] で**、[ **エンドポイント保護] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-156">For **Profile type**, select **Endpoint protection**.</span></span> <span data-ttu-id="d97b6-157">既存のプロファイルを選択した場合は、[プロパティ] を選択 **し、[プロパティ**] を選択 **設定。**</span><span class="sxs-lookup"><span data-stu-id="d97b6-157">If you've chosen an existing profile, select **Properties** and then select **Settings**.</span></span>

2. <span data-ttu-id="d97b6-158">[エンドポイント保護 **] ウィンドウで**、[Exploit **Guard] をWindows Defenderし**、[攻撃表面の縮小 **] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-158">In the **Endpoint protection** pane, select **Windows Defender Exploit Guard**, then select **Attack Surface Reduction**.</span></span> <span data-ttu-id="d97b6-159">各 ASR ルールの目的の設定を選択します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-159">Select the desired setting for each ASR rule.</span></span>

3. <span data-ttu-id="d97b6-160">[ **攻撃表面の縮小の例外] で**、個々のファイルとフォルダーを入力します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-160">Under **Attack Surface Reduction exceptions**, enter individual files and folders.</span></span> <span data-ttu-id="d97b6-161">[インポート] を **選択して** 、ASR ルールから除外するファイルとフォルダーを含む CSV ファイルをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-161">You can also select **Import** to import a CSV file that contains files and folders to exclude from ASR rules.</span></span> <span data-ttu-id="d97b6-162">CSV ファイルの各行は、次のように書式設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d97b6-162">Each line in the CSV file should be formatted as follows:</span></span>

   <span data-ttu-id="d97b6-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span><span class="sxs-lookup"><span data-stu-id="d97b6-163">`C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`</span></span>

4. <span data-ttu-id="d97b6-164">3 つの構成ウィンドウで **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-164">Select **OK** on the three configuration panes.</span></span> <span data-ttu-id="d97b6-165">次に、**新しい** エンドポイント保護ファイルを作成する場合は[作成] を選択し、既存のエンドポイント保護ファイルを編集する場合は [保存] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-165">Then select **Create** if you're creating a new endpoint protection file or **Save** if you're editing an existing one.</span></span>

## <a name="mem"></a><span data-ttu-id="d97b6-166">MEM</span><span class="sxs-lookup"><span data-stu-id="d97b6-166">MEM</span></span>

<span data-ttu-id="d97b6-167">カスタム ASR ルールMicrosoft エンドポイント マネージャー(MEM) OMA-URI を使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-167">You can use Microsoft Endpoint Manager (MEM) OMA-URI to configure custom ASR rules.</span></span> <span data-ttu-id="d97b6-168">次の手順では、この例で「悪用された脆弱な署名済みドライバーの悪用を [ブロックする」](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) というルールを使用します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-168">The following procedure uses the rule [Block abuse of exploited vulnerable signed drivers](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) for the example.</span></span>

1. <span data-ttu-id="d97b6-169">新しいMicrosoft エンドポイント マネージャー (MEM) 管理センターを開きます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-169">Open the Microsoft Endpoint Manager (MEM) admin center.</span></span> <span data-ttu-id="d97b6-170">[ホーム] **メニューの [** デバイス] を  **クリックし**、[構成プロファイル] **を** 選択し、[プロファイルの作成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-170">In the **Home** menu, click  **Devices**, select **Configuration profile**, and then click **Create profile**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d97b6-171">![MEM Create Profile](images/mem01-create-profile.png)</span><span class="sxs-lookup"><span data-stu-id="d97b6-171">![MEM Create Profile](images/mem01-create-profile.png)</span></span>

2. <span data-ttu-id="d97b6-172">[ **プロファイルの作成]** で、次の 2 つのドロップダウン リストで、次の項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-172">In **Create a profile**, in the following two drop-down lists, select the following:</span></span>

   - <span data-ttu-id="d97b6-173">[**プラットフォーム]** で、[Windows 10 **以降] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="d97b6-173">In **Platform**, select **Windows 10 and later**</span></span>
   - <span data-ttu-id="d97b6-174">[ **プロファイルの種類] で**、[ **テンプレート] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="d97b6-174">In **Profile type**, select **Templates**</span></span>

   <span data-ttu-id="d97b6-175">[カスタム **] を** 選択し、[作成] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-175">Select **Custom**, and then click **Create**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d97b6-176">![MEM ルール プロファイルの属性](images/mem02-profile-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="d97b6-176">![MEM rule profile attributes](images/mem02-profile-attributes.png)</span></span>

3. <span data-ttu-id="d97b6-177">[カスタム テンプレート] ツールが開き、手順 **1 [基本] に進みます**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-177">The Custom template tool opens to step **1 Basics**.</span></span> <span data-ttu-id="d97b6-178">**[1 基本]** の [**名前]** にテンプレートの名前を入力し、[説明] に説明を入力できます (オプション)。</span><span class="sxs-lookup"><span data-stu-id="d97b6-178">In **1 Basics**, in **Name**, type a name for your template, and in **Description** you can type a description (optional).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d97b6-179">![MEM の基本的な属性](images/mem03-1-basics.png)</span><span class="sxs-lookup"><span data-stu-id="d97b6-179">![MEM basic attributes](images/mem03-1-basics.png)</span></span>

4. <span data-ttu-id="d97b6-180">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d97b6-180">Click **Next**.</span></span> <span data-ttu-id="d97b6-181">手順 **2 構成設定が開** きます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-181">Step **2 Configuration settings** opens.</span></span> <span data-ttu-id="d97b6-182">[OMA-URI] の設定をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-182">For OMA-URI Settings, click **Add**.</span></span> <span data-ttu-id="d97b6-183">2 つのオプションが表示 **されます。**</span><span class="sxs-lookup"><span data-stu-id="d97b6-183">Two options now appear: **Add** and **Export**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d97b6-184">![MEM 構成の設定](images/mem04-2-configuration-settings.png)</span><span class="sxs-lookup"><span data-stu-id="d97b6-184">![MEM Configuration settings](images/mem04-2-configuration-settings.png)</span></span>

5. <span data-ttu-id="d97b6-185">[追加 **] を再度クリック** します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-185">Click **Add** again.</span></span> <span data-ttu-id="d97b6-186">[**行 OMA-URI の追加] 設定** 開きます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-186">The **Add Row OMA-URI Settings** opens.</span></span> <span data-ttu-id="d97b6-187">[ **行の追加]** で、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d97b6-187">In **Add Row**, do the following:</span></span>

   - <span data-ttu-id="d97b6-188">[ **名前]** に、ルールの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-188">In **Name**, type a name for the rule.</span></span>
   - <span data-ttu-id="d97b6-189">[ **説明]** に簡単な説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-189">In **Description**, type a brief description.</span></span>
   - <span data-ttu-id="d97b6-190">**OMA-URI で**、追加するルールの特定の OMA-URI リンクを入力または貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-190">In **OMA-URI**, type or paste the specific OMA-URI link for the rule that you are adding.</span></span>
   - <span data-ttu-id="d97b6-191">[ **データ型] で**、[文字列] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-191">In **Data type**, select **String**.</span></span>
   - <span data-ttu-id="d97b6-192">[ **値]** で、GUID 値、記号、およびスペースを含む State 値 \= _(GUID=StateValue) を入力または貼り付けます_。</span><span class="sxs-lookup"><span data-stu-id="d97b6-192">In **Value**, type or paste the GUID value, the \= sign and the State value with no spaces (_GUID=StateValue_).</span></span> <span data-ttu-id="d97b6-193">Where: {0 : Disable (DISABLE the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (有効な場合は ASR ルールが組織に与える影響を評価する)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span><span class="sxs-lookup"><span data-stu-id="d97b6-193">Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d97b6-194">![MEM OMA URI 構成](images/mem05-add-row-oma-uri.png)</span><span class="sxs-lookup"><span data-stu-id="d97b6-194">![MEM OMA URI configuration](images/mem05-add-row-oma-uri.png)</span></span>

6. <span data-ttu-id="d97b6-195">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d97b6-195">Click **Save**.</span></span> <span data-ttu-id="d97b6-196">**[行の追加]** が閉じます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-196">**Add Row** closes.</span></span> <span data-ttu-id="d97b6-197">[カスタム **] で**、[次へ] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-197">In **Custom**, click **Next**.</span></span> <span data-ttu-id="d97b6-198">手順 **3 スコープ タグでは、** スコープ タグは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="d97b6-198">In step **3 Scope tags**, scope tags are optional.</span></span> <span data-ttu-id="d97b6-199">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d97b6-199">Do one of the following:</span></span>

   - <span data-ttu-id="d97b6-200">[ **スコープ タグの選択]** をクリックし、スコープ タグ (オプション) を選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-200">Click **Select Scope tags**, select the scope tag (optional) and then click **Next**.</span></span>
   - <span data-ttu-id="d97b6-201">または、[次へ] **をクリックします。**</span><span class="sxs-lookup"><span data-stu-id="d97b6-201">Or click **Next**</span></span>

7. <span data-ttu-id="d97b6-202">手順 **4 [割り当** て] の **[含** まれるグループ] で、このルールを適用するグループの場合は、次のオプションから選択します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-202">In step **4 Assignments**, in **Included Groups** - for the groups that you want this rule to apply - select from the following options:</span></span>

   - <span data-ttu-id="d97b6-203">**グループの追加**</span><span class="sxs-lookup"><span data-stu-id="d97b6-203">**Add groups**</span></span>
   - <span data-ttu-id="d97b6-204">**すべてのユーザーを追加する**</span><span class="sxs-lookup"><span data-stu-id="d97b6-204">**Add all users**</span></span>
   - <span data-ttu-id="d97b6-205">**すべてのデバイスを追加する**</span><span class="sxs-lookup"><span data-stu-id="d97b6-205">**Add all devices**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d97b6-206">![MEM の割り当て](images/mem06-4-assignments.png)</span><span class="sxs-lookup"><span data-stu-id="d97b6-206">![MEM assignments](images/mem06-4-assignments.png)</span></span>

8. <span data-ttu-id="d97b6-207">[ **除外グループ] で**、このルールから除外するグループを選択し、[次へ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-207">In **Excluded groups**, select any groups that you want to exclude from this rule, and then click **Next**.</span></span>

9. <span data-ttu-id="d97b6-208">手順 **5 次の設定の** 適用ルールで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d97b6-208">In step **5 Applicability Rules** for the following settings, do the following:</span></span>

   - <span data-ttu-id="d97b6-209">[ **ルール] で**、[プロファイルを **割り当てる場合**] または [プロファイルを割り当 **てない場合] を選択します。**</span><span class="sxs-lookup"><span data-stu-id="d97b6-209">In **Rule**, select either **Assign profile if**, or **Don’t assign profile if**</span></span>
   - <span data-ttu-id="d97b6-210">[ **プロパティ**] で、このルールを適用するプロパティを選択します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-210">In **Property**, select the property to which you want this rule to apply</span></span>
   - <span data-ttu-id="d97b6-211">[ **値]** に、該当する値または値の範囲を入力します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-211">In **Value**, enter the applicable value or value range</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d97b6-212">![MEM 適用ルール](images/mem07-5-applicability-rules.png)</span><span class="sxs-lookup"><span data-stu-id="d97b6-212">![MEM Applicability rules](images/mem07-5-applicability-rules.png)</span></span>

10. <span data-ttu-id="d97b6-213">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d97b6-213">Click **Next**.</span></span> <span data-ttu-id="d97b6-214">手順 **6 [レビュー] + [作成**] で、選択して入力した設定と情報を確認し、[作成] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-214">In step **6 Review + create**, review the settings and information you have selected and entered, and then click **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d97b6-215">![MEM レビューと作成](images/mem08-6-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="d97b6-215">![MEM Review and create](images/mem08-6-review-create.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="d97b6-216">ルールはアクティブで、数分以内に有効です。</span><span class="sxs-lookup"><span data-stu-id="d97b6-216">Rules are active and live within minutes.</span></span>

>[!NOTE]
> <span data-ttu-id="d97b6-217">競合の処理:</span><span class="sxs-lookup"><span data-stu-id="d97b6-217">Conflict handling:</span></span>
> 
> <span data-ttu-id="d97b6-218">デバイスに 2 つの異なる ASR ポリシーを割り当てると、競合の処理方法は、異なる状態が割り当てられたルールであり、競合管理が行われるので、結果はエラーになります。</span><span class="sxs-lookup"><span data-stu-id="d97b6-218">If you assign a device two different ASR policies, the way conflict is handled is rules that are assigned different states, there is no conflict management in place, and the result is an error.</span></span>
> 
> <span data-ttu-id="d97b6-219">競合しないルールではエラーが発生し、ルールが正しく適用されます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-219">Non-conflicting rules will not result in an error, and the rule will be applied correctly.</span></span> <span data-ttu-id="d97b6-220">その結果、最初のルールが適用され、それ以降の競合しないルールがポリシーにマージされます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-220">The result is that the first rule is applied, and subsequent non-conflicting rules are merged into the policy.</span></span>

## <a name="mdm"></a><span data-ttu-id="d97b6-221">MDM</span><span class="sxs-lookup"><span data-stu-id="d97b6-221">MDM</span></span>

<span data-ttu-id="d97b6-222">各ルールのモードを個別に有効にして設定するには [、./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) 構成サービス プロバイダー (CSP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-222">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) configuration service provider (CSP) to individually enable and set the mode for each rule.</span></span>

<span data-ttu-id="d97b6-223">ASR ルールに GUID 値を使用して参照 [するサンプルを次に示します](attack-surface-reduction.md#attack-surface-reduction-rules)。</span><span class="sxs-lookup"><span data-stu-id="d97b6-223">The following is a sample for reference, using [GUID values for ASR rules](attack-surface-reduction.md#attack-surface-reduction-rules).</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

<span data-ttu-id="d97b6-224">監査モードで有効 (ブロック)、無効化、警告、または有効にする値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d97b6-224">The values to enable (Block), disable, warn, or enable in audit mode are:</span></span>

- <span data-ttu-id="d97b6-225">0 : 無効にする (ASR ルールを無効にする)</span><span class="sxs-lookup"><span data-stu-id="d97b6-225">0 : Disable (Disable the ASR rule)</span></span>
- <span data-ttu-id="d97b6-226">1 : ブロック (ASR ルールを有効にする)</span><span class="sxs-lookup"><span data-stu-id="d97b6-226">1 : Block (Enable the ASR rule)</span></span>
- <span data-ttu-id="d97b6-227">2 : 監査 (ASR ルールが有効な場合に組織に与える影響を評価する)</span><span class="sxs-lookup"><span data-stu-id="d97b6-227">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
- <span data-ttu-id="d97b6-228">6 : 警告 (ASR ルールを有効にするが、エンド ユーザーがブロックをバイパスできる)。</span><span class="sxs-lookup"><span data-stu-id="d97b6-228">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block).</span></span> <span data-ttu-id="d97b6-229">警告モードは、ほとんどの ASR ルールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-229">Warn mode is now available for most of the ASR rules.</span></span>

<span data-ttu-id="d97b6-230">除外を追加するには [、./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) 構成サービス プロバイダー (CSP) を使用します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-230">Use the [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) configuration service provider (CSP) to add exclusions.</span></span>

<span data-ttu-id="d97b6-231">例:</span><span class="sxs-lookup"><span data-stu-id="d97b6-231">Example:</span></span>

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> <span data-ttu-id="d97b6-232">スペースを使用せずに OMA-URI 値を入力してください。</span><span class="sxs-lookup"><span data-stu-id="d97b6-232">Be sure to enter OMA-URI values without spaces.</span></span>

## <a name="microsoft-endpoint-configuration-manager"></a><span data-ttu-id="d97b6-233">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d97b6-233">Microsoft Endpoint Configuration Manager</span></span>

1. <span data-ttu-id="d97b6-234">この **Microsoft Endpoint Configuration Manager、Exploit** Guard の [アセットと  >  **コンプライアンス] Endpoint Protection Windows Defender**  >  **移動します**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-234">In Microsoft Endpoint Configuration Manager, go to **Assets and Compliance** > **Endpoint Protection** > **Windows Defender Exploit Guard**.</span></span>

2. <span data-ttu-id="d97b6-235">[ホーム **エクスプ**  >  **ロイト ガード ポリシーの作成] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-235">Select **Home** > **Create Exploit Guard Policy**.</span></span>

3. <span data-ttu-id="d97b6-236">名前と説明を入力し、[攻撃表面の縮小] を **選択** し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-236">Enter a name and a description, select **Attack Surface Reduction**, and select **Next**.</span></span>

4. <span data-ttu-id="d97b6-237">アクションをブロックまたは監査するルールを選択し、[次へ] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-237">Choose which rules will block or audit actions and select **Next**.</span></span>

5. <span data-ttu-id="d97b6-238">設定を確認し、[次へ] **を選択** してポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-238">Review the settings and select **Next** to create the policy.</span></span>

6. <span data-ttu-id="d97b6-239">ポリシーが作成された後、閉 **じます**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-239">After the policy is created, **Close**.</span></span>

## <a name="group-policy"></a><span data-ttu-id="d97b6-240">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="d97b6-240">Group Policy</span></span>

> [!WARNING]
> <span data-ttu-id="d97b6-241">Intune、Configuration Manager、または他のエンタープライズ レベルの管理プラットフォームを使用してコンピューターとデバイスを管理する場合、管理ソフトウェアは起動時に競合するグループ ポリシー設定を上書きします。</span><span class="sxs-lookup"><span data-stu-id="d97b6-241">If you manage your computers and devices with Intune, Configuration Manager, or other enterprise-level management platform, the management software will overwrite any conflicting Group Policy settings on startup.</span></span>

1. <span data-ttu-id="d97b6-242">グループ ポリシー管理コンピューターで、[[グループ ポリシー管理コンソール]](https://technet.microsoft.com/library/cc731212.aspx) を開き、構成するグループ ポリシー オブジェクトを右クリックして、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d97b6-242">On your Group Policy management computer, open the [Group Policy Management Console](https://technet.microsoft.com/library/cc731212.aspx), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="d97b6-243">**[グループ ポリシー管理エディター]** で、**[コンピューターの構成]** に移動し、**[管理用テンプレート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-243">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="d97b6-244">ツリーを展開して **、攻撃Windows縮小**  >  **Microsoft Defender ウイルス対策Microsoft Defender Exploit Guard**  >    >  **コンポーネントを表示します**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-244">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Microsoft Defender Exploit Guard** > **Attack surface reduction**.</span></span>

4. <span data-ttu-id="d97b6-245">[攻撃 **表面縮小ルールの構成] を選択し、[** 有効] を **選択します**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-245">Select **Configure Attack surface reduction rules** and select **Enabled**.</span></span> <span data-ttu-id="d97b6-246">その後、[オプション] セクションで各ルールの個別の状態を設定できます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-246">You can then set the individual state for each rule in the options section.</span></span>

   <span data-ttu-id="d97b6-247">**[Show....]** を選択し、[値名] 列にルール ID を入力し、[値] 列に選択した状態 **を** 次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-247">Select **Show...** and enter the rule ID in the **Value name** column and your chosen state in the **Value** column as follows:</span></span>

   - <span data-ttu-id="d97b6-248">0 : 無効にする (ASR ルールを無効にする)</span><span class="sxs-lookup"><span data-stu-id="d97b6-248">0 : Disable (Disable the ASR rule)</span></span>
   - <span data-ttu-id="d97b6-249">1 : ブロック (ASR ルールを有効にする)</span><span class="sxs-lookup"><span data-stu-id="d97b6-249">1 : Block (Enable the ASR rule)</span></span>
   - <span data-ttu-id="d97b6-250">2 : 監査 (ASR ルールが有効な場合に組織に与える影響を評価する)</span><span class="sxs-lookup"><span data-stu-id="d97b6-250">2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)</span></span>
   - <span data-ttu-id="d97b6-251">6 : 警告 (ASR ルールを有効にするが、エンド ユーザーがブロックをバイパスできる)</span><span class="sxs-lookup"><span data-stu-id="d97b6-251">6 : Warn  (Enable the ASR rule but allow the end-user to bypass the block)</span></span>

   :::image type="content" source="images/asr-rules-gp.png" alt-text="グループ ポリシーの ASR ルール":::

5. <span data-ttu-id="d97b6-253">ASR ルールからファイルとフォルダーを除外するには、[攻撃表面の縮小ルールからファイルとパスを除外する] 設定を選択し、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-253">To exclude files and folders from ASR rules, select the **Exclude files and paths from Attack surface reduction rules** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="d97b6-254">[ **表示] を** 選択し、[値の名前] 列に各ファイル **またはフォルダーを入力** します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-254">Select **Show** and enter each file or folder in the **Value name** column.</span></span> <span data-ttu-id="d97b6-255">各 **アイテムの [** 値] **列に 0** を入力します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-255">Enter **0** in the **Value** column for each item.</span></span>

   > [!WARNING]
   > <span data-ttu-id="d97b6-256">[値の名前] 列または [値] 列でサポートされていない引用符は **使用** しません。</span><span class="sxs-lookup"><span data-stu-id="d97b6-256">Do not use quotes as they are not supported for either the **Value name** column or the **Value** column.</span></span>

## <a name="powershell"></a><span data-ttu-id="d97b6-257">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d97b6-257">PowerShell</span></span>

> [!WARNING]
> <span data-ttu-id="d97b6-258">Intune、Configuration Manager、または別のエンタープライズ レベルの管理プラットフォームを使用してコンピューターとデバイスを管理すると、起動時に競合する PowerShell 設定が管理ソフトウェアによって上書きされます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-258">If you manage your computers and devices with Intune, Configuration Manager, or another enterprise-level management platform, the management software will overwrite any conflicting PowerShell settings on startup.</span></span> <span data-ttu-id="d97b6-259">PowerShell を使用して値を定義するには、管理プラットフォームのルールに "User Defined" オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-259">To allow users to define the value using PowerShell, use the "User Defined" option for the rule in the management platform.</span></span>

1. <span data-ttu-id="d97b6-260">[**スタート] メニューに「powershell」** と入力し、Windows PowerShellを右クリックし **、[** 管理者として **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="d97b6-260">Type **powershell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="d97b6-261">次の cmdlet を入力します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-261">Type the following cmdlet:</span></span>

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    <span data-ttu-id="d97b6-262">監査モードで ASR ルールを有効にするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-262">To enable ASR rules in audit mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    <span data-ttu-id="d97b6-263">警告モードで ASR ルールを有効にするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-263">To enable ASR rules in warn mode, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    <span data-ttu-id="d97b6-264">悪用された脆弱な署名済みドライバーの ASR ブロックの悪用を有効にするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-264">To enable ASR Block abuse of exploited vulnerable signed drivers, use the following cmdlet:</span></span>

   ```PowerShell
   "& {&'Add-MpPreference' -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled"}
   ```

    <span data-ttu-id="d97b6-265">ASR ルールをオフにするには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-265">To turn off ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="d97b6-266">ルールごとに状態を個別に指定する必要がありますが、コンマ区切りのリストでルールと状態を組み合わせて使用できます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-266">You must specify the state individually for each rule, but you can combine rules and states in a comma-separated list.</span></span>
    >
    > <span data-ttu-id="d97b6-267">次の例では、最初の 2 つのルールが有効になり、3 番目のルールが無効になり、4 番目のルールが監査モードで有効になります。</span><span class="sxs-lookup"><span data-stu-id="d97b6-267">In the following example, the first two rules will be enabled, the third rule will be disabled, and the fourth rule will be enabled in audit mode:</span></span>
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    <span data-ttu-id="d97b6-268">PowerShell 動詞を使用 `Add-MpPreference` して、既存のリストに新しいルールを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-268">You can also use the `Add-MpPreference` PowerShell verb to add new rules to the existing list.</span></span>

    > [!WARNING]
    > <span data-ttu-id="d97b6-269">`Set-MpPreference` ルールの既存のセットは常に上書きされます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-269">`Set-MpPreference` will always overwrite the existing set of rules.</span></span> <span data-ttu-id="d97b6-270">既存のセットに追加する場合は、代わりに `Add-MpPreference` 使用します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-270">If you want to add to the existing set, use `Add-MpPreference` instead.</span></span>
    > <span data-ttu-id="d97b6-271">を使用して、ルールとその現在の状態の一覧を取得できます `Get-MpPreference` 。</span><span class="sxs-lookup"><span data-stu-id="d97b6-271">You can obtain a list of rules and their current state by using `Get-MpPreference`.</span></span>

3. <span data-ttu-id="d97b6-272">ASR ルールからファイルとフォルダーを除外するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-272">To exclude files and folders from ASR rules, use the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    <span data-ttu-id="d97b6-273">引き続き使用 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` して、リストにファイルとフォルダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-273">Continue to use `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` to add more files and folders to the list.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d97b6-274">リスト `Add-MpPreference` にアプリを追加または追加する場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="d97b6-274">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="d97b6-275">コマンドレットを `Set-MpPreference` 使用すると、既存のリストが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="d97b6-275">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

## <a name="related-articles"></a><span data-ttu-id="d97b6-276">関連記事</span><span class="sxs-lookup"><span data-stu-id="d97b6-276">Related articles</span></span>

- [<span data-ttu-id="d97b6-277">攻撃表面の縮小ルールを使用して攻撃表面を削減する</span><span class="sxs-lookup"><span data-stu-id="d97b6-277">Reduce attack surfaces with attack surface reduction rules</span></span>](attack-surface-reduction.md)

- [<span data-ttu-id="d97b6-278">攻撃表面の縮小を評価する</span><span class="sxs-lookup"><span data-stu-id="d97b6-278">Evaluate attack surface reduction</span></span>](evaluate-attack-surface-reduction.md)

- [<span data-ttu-id="d97b6-279">攻撃面の減少の FAQ</span><span class="sxs-lookup"><span data-stu-id="d97b6-279">Attack surface reduction FAQ</span></span>](attack-surface-reduction.md)
