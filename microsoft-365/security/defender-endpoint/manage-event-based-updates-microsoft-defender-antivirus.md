---
title: 特定のMicrosoft Defender ウイルス対策後に更新プログラムを適用する
description: スタートアップ後Microsoft Defender ウイルス対策クラウド配信の検出レポートの受信後にセキュリティ インテリジェンス更新プログラムを適用する方法を管理します。
keywords: 更新、保護、強制的な更新、イベント、スタートアップ、最新のチェック、通知
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
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82aff7adedc9e490520851ad8c8e87fad60abf0a
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926081"
---
# <a name="manage-event-based-forced-updates"></a><span data-ttu-id="baf12-104">イベントベースの強制更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="baf12-104">Manage event-based forced updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="baf12-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="baf12-105">**Applies to:**</span></span>

- [<span data-ttu-id="baf12-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="baf12-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="baf12-107">Microsoft Defender ウイルス対策を使用すると、起動時やクラウド配信の保護サービスから特定のレポートを受信した後など、特定のイベントの後に更新プログラムが発生する必要があるかどうかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="baf12-107">Microsoft Defender Antivirus allows you to determine if updates should (or should not) occur after certain events, such as at startup or after receiving specific reports from the cloud-delivered protection service.</span></span>

## <a name="check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="baf12-108">スキャンを実行する前に保護更新プログラムを確認する</span><span class="sxs-lookup"><span data-stu-id="baf12-108">Check for protection updates before running a scan</span></span>

<span data-ttu-id="baf12-109">スケジュールされたスキャンをMicrosoft Endpoint Configuration Manager前に、Microsoft Endpoint Configuration Manager、グループ ポリシー、PowerShell コマンドレット、WMI を使用して、Microsoft Defender ウイルス対策 に強制的に保護更新プログラムをチェックしてダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="baf12-109">You can use Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, and WMI to force Microsoft Defender Antivirus to check and download protection updates before running a scheduled scan.</span></span>

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="baf12-110">Configuration Manager を使用して、スキャンを実行する前に保護更新プログラムを確認する</span><span class="sxs-lookup"><span data-stu-id="baf12-110">Use Configuration Manager to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="baf12-111">Microsoft エンドポイント マネージャー コンソールで、変更するマルウェア対策ポリシーを開きます (左側のナビゲーションウィンドウで [アセットとコンプライアンス] をクリックし、ツリーを[概要] Endpoint Protection マルウェア対策ポリシー  >    >  ) に展開します。</span><span class="sxs-lookup"><span data-stu-id="baf12-111">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2. <span data-ttu-id="baf12-112">[スケジュールされたスキャン **] セクションに移動** し、スキャンを実行する前に最新のセキュリティ インテリジェンス更新プログラムのチェックを [は **い** ] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-112">Go to the **Scheduled scans** section and set **Check for the latest security intelligence updates before running a scan** to **Yes**.</span></span>

3. <span data-ttu-id="baf12-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="baf12-113">Click **OK**.</span></span>

4. <span data-ttu-id="baf12-114">[更新されたポリシーを通常どおり展開します](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。</span><span class="sxs-lookup"><span data-stu-id="baf12-114">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="baf12-115">グループ ポリシーを使用して、スキャンを実行する前に保護更新プログラムを確認する</span><span class="sxs-lookup"><span data-stu-id="baf12-115">Use Group Policy to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="baf12-116">グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-116">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="baf12-117">グループ ポリシー管理 **エディターを使用して、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-117">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="baf12-118">[ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="baf12-118">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="baf12-119">ツリーを展開して、[**スキャン] WindowsコンポーネントMicrosoft Defender ウイルス対策**  >    >  **展開します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-119">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="baf12-120">[スケジュールされたスキャン **を実行する** 前に最新のウイルスとスパイウェアの定義を確認する] をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-120">Double-click **Check for the latest virus and spyware definitions before running a scheduled scan** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="baf12-121">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="baf12-121">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="baf12-122">PowerShell コマンドレットを使用して、スキャンを実行する前に保護更新プログラムを確認する</span><span class="sxs-lookup"><span data-stu-id="baf12-122">Use PowerShell cmdlets to check for protection updates before running a scan</span></span>

<span data-ttu-id="baf12-123">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="baf12-123">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="baf12-124">詳細については、「[PowerShell コマンドレットを使用して Microsoft Defender ウイルス対策を構成および実行する](use-powershell-cmdlets-microsoft-defender-antivirus.md)」および「[Defender コマンドレット](/powershell/module/defender/index)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="baf12-124">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="baf12-125">スキャンWindows前に保護更新プログラムを確認するには、WMI (管理命令) を使用します。</span><span class="sxs-lookup"><span data-stu-id="baf12-125">Use Windows Management Instruction (WMI) to check for protection updates before running a scan</span></span>

<span data-ttu-id="baf12-126">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="baf12-126">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="baf12-127">詳細については[、「WMIv2 API Windows Defenderを参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="baf12-127">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="check-for-protection-updates-on-startup"></a><span data-ttu-id="baf12-128">起動時に保護更新プログラムを確認する</span><span class="sxs-lookup"><span data-stu-id="baf12-128">Check for protection updates on startup</span></span>

<span data-ttu-id="baf12-129">グループ ポリシーを使用して、コンピューターのMicrosoft Defender ウイルス対策保護更新プログラムを強制的に確認してダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="baf12-129">You can use Group Policy to force Microsoft Defender Antivirus to check and download protection updates when the machine is started.</span></span>

1. <span data-ttu-id="baf12-130">グループ ポリシー管理コンピューターで、グループ ポリシー [管理](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-130">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="baf12-131">グループ ポリシー管理 **エディターを使用して、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-131">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="baf12-132">[ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="baf12-132">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="baf12-133">ツリーを展開して、**セキュリティ Windows更新**  >  **Microsoft Defender ウイルス対策**  >  **コンポーネントを展開します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-133">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="baf12-134">[起動時に **最新のウイルス** とスパイウェアの定義を確認する] をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-134">Double-click **Check for the latest virus and spyware definitions on startup** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="baf12-135">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="baf12-135">Click **OK**.</span></span>

<span data-ttu-id="baf12-136">また、グループ ポリシー、PowerShell、または WMI を使用して、実行中Microsoft Defender ウイルス対策起動時に更新プログラムを確認するサーバーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="baf12-136">You can also use Group Policy, PowerShell, or WMI to configure Microsoft Defender Antivirus to check for updates at startup even when it is not running.</span></span>

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="baf12-137">グループ ポリシーを使用して、ユーザーが存在Microsoft Defender ウイルス対策更新プログラムをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="baf12-137">Use Group Policy to download updates when Microsoft Defender Antivirus is not present</span></span>

1. <span data-ttu-id="baf12-138">グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="baf12-139">グループ ポリシー **管理エディターを使用して、[** コンピューターの構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-139">Using the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="baf12-140">[ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="baf12-140">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="baf12-141">ツリーを展開して、**セキュリティ Windows更新**  >  **Microsoft Defender ウイルス対策**  >  **コンポーネントを展開します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="baf12-142">[起動時にセキュリティ **インテリジェンス更新プログラムを開始** する] をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-142">Double-click **Initiate security intelligence update on startup** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="baf12-143">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="baf12-143">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="baf12-144">PowerShell コマンドレットを使用して、ユーザーが存在しないMicrosoft Defender ウイルス対策更新プログラムをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="baf12-144">Use PowerShell cmdlets to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="baf12-145">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="baf12-145">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="baf12-146">詳細については[、「PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)コマンドレットを使用して powerShell コマンドレットを使用して、Microsoft Defender ウイルス対策 および[Defender](/powershell/module/defender/index)コマンドレットを管理する」を Microsoft Defender ウイルス対策参照してください。</span><span class="sxs-lookup"><span data-stu-id="baf12-146">For more information, see [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="baf12-147">[Windows管理命令 (WMI) を使用して、インストールされていないMicrosoft Defender ウイルス対策更新プログラムをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="baf12-147">Use Windows Management Instruction (WMI) to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="baf12-148">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="baf12-148">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="baf12-149">詳細については[、「WMIv2 API Windows Defenderを参照してください](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)。</span><span class="sxs-lookup"><span data-stu-id="baf12-149">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a><span data-ttu-id="baf12-150">クラウドによる保護に基づく保護に対するアドホックな変更を許可する</span><span class="sxs-lookup"><span data-stu-id="baf12-150">Allow ad hoc changes to protection based on cloud-delivered protection</span></span>

<span data-ttu-id="baf12-151">Microsoft Defender AV は、クラウドによる保護に基づいて保護を変更できます。</span><span class="sxs-lookup"><span data-stu-id="baf12-151">Microsoft Defender AV can make changes to its protection based on cloud-delivered protection.</span></span> <span data-ttu-id="baf12-152">このような変更は、通常またはスケジュールされた保護更新プログラムの外部で行われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="baf12-152">Such changes can occur outside of normal or scheduled protection updates.</span></span>

<span data-ttu-id="baf12-153">クラウド配信保護を有効にしている場合、Microsoft Defender AV は疑わしいファイルをクラウドに送信Windows Defenderします。</span><span class="sxs-lookup"><span data-stu-id="baf12-153">If you have enabled cloud-delivered protection, Microsoft Defender AV will send files it is suspicious about to the Windows Defender cloud.</span></span> <span data-ttu-id="baf12-154">クラウド サービスがファイルが悪意のあると報告し、最近の保護更新プログラムでファイルが検出された場合は、グループ ポリシーを使用して Microsoft Defender AV を構成して、その保護更新プログラムを自動的に受信できます。</span><span class="sxs-lookup"><span data-stu-id="baf12-154">If the cloud service reports that the file is malicious, and the file is detected in a recent protection update, you can use Group Policy to configure Microsoft Defender AV to automatically receive that protection update.</span></span> <span data-ttu-id="baf12-155">その他の重要な保護更新プログラムも適用できます。</span><span class="sxs-lookup"><span data-stu-id="baf12-155">Other important protection updates can also be applied.</span></span>

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a><span data-ttu-id="baf12-156">グループ ポリシーを使用して、クラウド配信の保護に基づいて最新の更新プログラムを自動的にダウンロードする</span><span class="sxs-lookup"><span data-stu-id="baf12-156">Use Group Policy to automatically download recent updates based on cloud-delivered protection</span></span>

1. <span data-ttu-id="baf12-157">グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-157">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="baf12-158">グループ ポリシー管理 **エディターを使用して、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-158">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="baf12-159">[ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="baf12-159">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="baf12-160">ツリーを展開して、**セキュリティ Windows更新**  >  **Microsoft Defender ウイルス対策**  >  **コンポーネントを展開します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-160">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="baf12-161">[Microsoft **MAPS へのレポートに基づいて** リアルタイムのセキュリティ インテリジェンス更新を許可する] をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-161">Double-click **Allow real-time security intelligence updates based on reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="baf12-162">次に、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="baf12-162">Then click **OK**.</span></span>

6. <span data-ttu-id="baf12-163">**Microsoft MAPS への定義ベースのレポートを** 無効にし、オプションを [有効] に設定する通知を **許可します**。</span><span class="sxs-lookup"><span data-stu-id="baf12-163">**Allow notifications to disable definitions-based reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="baf12-164">次に、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="baf12-164">Then click **OK**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="baf12-165">**定義ベースのレポートを無効にする通知を許可すると** 、Microsoft MAPS は誤検知レポートを引き起こすと知られている定義を無効にできます。</span><span class="sxs-lookup"><span data-stu-id="baf12-165">**Allow notifications to disable definitions based reports** enables Microsoft MAPS to disable those definitions known to cause false-positive reports.</span></span> <span data-ttu-id="baf12-166">この関数を動作するには、Microsoft MAPS に参加するコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="baf12-166">You must configure your computer to join Microsoft MAPS for this function to work.</span></span>

## <a name="see-also"></a><span data-ttu-id="baf12-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="baf12-167">See also</span></span>

- [<span data-ttu-id="baf12-168">展開Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="baf12-168">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="baf12-169">更新Microsoft Defender ウイルス対策を管理し、基準計画を適用する</span><span class="sxs-lookup"><span data-stu-id="baf12-169">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="baf12-170">保護更新プログラムをダウンロードして適用する場合の管理</span><span class="sxs-lookup"><span data-stu-id="baf12-170">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="baf12-171">最新のエンドポイントの更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="baf12-171">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="baf12-172">モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="baf12-172">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="baf12-173">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="baf12-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)