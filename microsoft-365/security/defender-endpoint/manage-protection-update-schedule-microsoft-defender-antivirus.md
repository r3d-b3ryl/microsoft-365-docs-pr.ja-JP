---
title: Microsoft Defender ウイルス対策の更新プログラムをスケジュールする
description: 保護更新プログラムをダウンロードする日、時刻、間隔をスケジュールする
keywords: 更新プログラム、セキュリティ基準、更新プログラムのスケジュール
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: e4ba9a438ff4640a556a236b50b0be6e816fc7e8
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691031"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a><span data-ttu-id="d69fd-104">保護更新プログラムをダウンロードして適用するスケジュールを管理する</span><span class="sxs-lookup"><span data-stu-id="d69fd-104">Manage the schedule for when protection updates should be downloaded and applied</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d69fd-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d69fd-105">**Applies to:**</span></span>

- [<span data-ttu-id="d69fd-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d69fd-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d69fd-107">Microsoft Defender ウイルス対策では、更新プログラムを探してダウンロードする必要がある場合に判断できます。</span><span class="sxs-lookup"><span data-stu-id="d69fd-107">Microsoft Defender Antivirus lets you determine when it should look for and download updates.</span></span>

<span data-ttu-id="d69fd-108">エンドポイントの更新プログラムは、次の方法でスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="d69fd-108">You can schedule updates for your endpoints by:</span></span> 

- <span data-ttu-id="d69fd-109">保護更新プログラムを確認する週の日を指定する</span><span class="sxs-lookup"><span data-stu-id="d69fd-109">Specifying the day of the week to check for protection updates</span></span> 
- <span data-ttu-id="d69fd-110">保護更新プログラムを確認する間隔を指定する</span><span class="sxs-lookup"><span data-stu-id="d69fd-110">Specifying the interval to check for protection updates</span></span>
- <span data-ttu-id="d69fd-111">保護更新プログラムを確認する時間を指定する</span><span class="sxs-lookup"><span data-stu-id="d69fd-111">Specifying the time to check for protection updates</span></span>

<span data-ttu-id="d69fd-112">また、各エンドポイントが保護更新プログラムをチェックしてダウンロードする時間をランダム化できます。</span><span class="sxs-lookup"><span data-stu-id="d69fd-112">You can also randomize the times when each endpoint checks and downloads protection updates.</span></span> <span data-ttu-id="d69fd-113">詳細については、「 [スキャンのスケジュール」](scheduled-catch-up-scans-microsoft-defender-antivirus.md) のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d69fd-113">See the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="use-configuration-manager-to-schedule-protection-updates"></a><span data-ttu-id="d69fd-114">Configuration Manager を使用して保護更新プログラムをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="d69fd-114">Use Configuration Manager to schedule protection updates</span></span>

1.  <span data-ttu-id="d69fd-115">Microsoft Endpoint Manager コンソールで、変更するマルウェア対策ポリシーを開きます (左側のナビゲーション ウィンドウで [アセットとコンプライアンス] をクリックし、ツリーを [Overview  >  **Endpoint Protection**  >  **Antimalware Policies]** に展開します)。</span><span class="sxs-lookup"><span data-stu-id="d69fd-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="d69fd-116">[セキュリティ インテリジェンスの **更新プログラム] セクションに移動** します。</span><span class="sxs-lookup"><span data-stu-id="d69fd-116">Go to the **Security intelligence updates** section.</span></span>

3. <span data-ttu-id="d69fd-117">特定の時間に更新プログラムを確認してダウンロードするには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="d69fd-117">To check and download updates at a certain time:</span></span>
      1. <span data-ttu-id="d69fd-118">[ **エンドポイント保護のセキュリティ インテリジェンス更新プログラムの確認]** を特定の間隔で設定します。. **に 0 を設定します**。</span><span class="sxs-lookup"><span data-stu-id="d69fd-118">Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.</span></span>
      2. <span data-ttu-id="d69fd-119">[ **エンドポイント保護のセキュリティ インテリジェンス更新プログラム** を毎日チェックする] を設定します。更新プログラムをチェックする必要がある時刻に設定します。</span><span class="sxs-lookup"><span data-stu-id="d69fd-119">Set **Check for Endpoint Protection security intelligence updates daily at...** to the time when updates should be checked.</span></span>
      <span data-ttu-id="d69fd-120">3</span><span class="sxs-lookup"><span data-stu-id="d69fd-120">3</span></span>
4. <span data-ttu-id="d69fd-121">継続的な間隔で更新プログラムを確認してダウンロードするには、特定の間隔でエンドポイント保護セキュリティ インテリジェンス更新プログラムのチェックを設定 **します** 。更新プログラムの間に発生する時間数を指定します。</span><span class="sxs-lookup"><span data-stu-id="d69fd-121">To check and download updates on a continual interval, Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to the number of hours that should occur between updates.</span></span>

5.  <span data-ttu-id="d69fd-122">[更新されたポリシーを通常どおり展開します](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)。</span><span class="sxs-lookup"><span data-stu-id="d69fd-122">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="use-group-policy-to-schedule-protection-updates"></a><span data-ttu-id="d69fd-123">グループ ポリシーを使用して保護更新プログラムをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="d69fd-123">Use Group Policy to schedule protection updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d69fd-124">既定では、Microsoft Defender ウイルス対策は、スケジュールされたスキャンの 15 分前に更新プログラムをチェックします。</span><span class="sxs-lookup"><span data-stu-id="d69fd-124">By default, Microsoft Defender Antivirus will check for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="d69fd-125">これらの設定を有効にすると、既定の設定は上書きされます。</span><span class="sxs-lookup"><span data-stu-id="d69fd-125">Enabling these settings will override that default.</span></span>

1.  <span data-ttu-id="d69fd-126">グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。</span><span class="sxs-lookup"><span data-stu-id="d69fd-126">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="d69fd-127">グループ ポリシー **管理エディターで、[コンピューター** の構成] **に移動します**。</span><span class="sxs-lookup"><span data-stu-id="d69fd-127">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="d69fd-128">[ポリシー **] をクリックし** 、[ **管理用テンプレート] をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="d69fd-128">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="d69fd-129">ツリーを Windows コンポーネント **の Microsoft** Defender  >  **ウイルス対策シグネチャ** インテリジェンス更新プログラムに展開  >  **し、** 次の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d69fd-129">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Intelligence Updates** and configure the following settings:</span></span>

    1. <span data-ttu-id="d69fd-130">[セキュリティ インテリジェンスの更新 **プログラム** を確認する週の日を指定する] 設定をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="d69fd-130">Double-click the **Specify the day of the week to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="d69fd-131">更新プログラムを確認する週の日を入力します。</span><span class="sxs-lookup"><span data-stu-id="d69fd-131">Enter the day of the week to check for updates.</span></span> <span data-ttu-id="d69fd-132">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d69fd-132">Click **OK**.</span></span>
    2. <span data-ttu-id="d69fd-133">[セキュリティ インテリジェンスの更新 **プログラム** を確認する間隔を指定する] 設定をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="d69fd-133">Double-click the **Specify the interval to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="d69fd-134">更新間の時間数を入力します。</span><span class="sxs-lookup"><span data-stu-id="d69fd-134">Enter the number of hours between updates.</span></span> <span data-ttu-id="d69fd-135">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d69fd-135">Click **OK**.</span></span>
    3. <span data-ttu-id="d69fd-136">[セキュリティ インテリジェンスの更新 **プログラム** を確認する時間を指定する] 設定をダブルクリックし、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="d69fd-136">Double-click the **Specify the time to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="d69fd-137">更新プログラムをチェックする時刻を入力します。</span><span class="sxs-lookup"><span data-stu-id="d69fd-137">Enter the time when updates should be checked.</span></span> <span data-ttu-id="d69fd-138">時刻は、エンドポイントのローカル時刻に基づいて行います。</span><span class="sxs-lookup"><span data-stu-id="d69fd-138">The time is based on the local time of the endpoint.</span></span> <span data-ttu-id="d69fd-139">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d69fd-139">Click **OK**.</span></span>


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a><span data-ttu-id="d69fd-140">PowerShell コマンドレットを使用して保護更新プログラムをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="d69fd-140">Use PowerShell cmdlets to schedule protection updates</span></span>

<span data-ttu-id="d69fd-141">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="d69fd-141">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

<span data-ttu-id="d69fd-142">[Microsoft Defender ウイルス対策で PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md)を使用する方法の詳細については、「Use PowerShell コマンドレットを使用して Microsoft Defender Antivirus コマンドレットと[Defender](/powershell/module/defender/)コマンドレットを構成および実行する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d69fd-142">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a><span data-ttu-id="d69fd-143">Windows 管理命令 (WMI) を使用して保護更新プログラムをスケジュールする</span><span class="sxs-lookup"><span data-stu-id="d69fd-143">Use Windows Management Instruction (WMI) to schedule protection updates</span></span>

<span data-ttu-id="d69fd-144">次の [**プロパティ** に対して **、MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d69fd-144">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

<span data-ttu-id="d69fd-145">詳細と許可されるパラメーターについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d69fd-145">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="d69fd-146">Windows Defender WMIv2 API</span><span class="sxs-lookup"><span data-stu-id="d69fd-146">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a><span data-ttu-id="d69fd-147">関連記事</span><span class="sxs-lookup"><span data-stu-id="d69fd-147">Related articles</span></span>

- [<span data-ttu-id="d69fd-148">Microsoft Defender ウイルス対策の展開</span><span class="sxs-lookup"><span data-stu-id="d69fd-148">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d69fd-149">Microsoft Defender ウイルス対策の更新プログラムを管理し、ベースラインを適用する</span><span class="sxs-lookup"><span data-stu-id="d69fd-149">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d69fd-150">最新のエンドポイントの更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="d69fd-150">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d69fd-151">イベントベースの強制的な更新の管理</span><span class="sxs-lookup"><span data-stu-id="d69fd-151">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d69fd-152">モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する</span><span class="sxs-lookup"><span data-stu-id="d69fd-152">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d69fd-153">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="d69fd-153">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)