---
title: Windows セキュリティ アプリの Microsoft Defender ウイルス対策
description: Microsoft Defender Antivirus が Windows セキュリティ アプリに含まれるので、一般的なタスクを確認、比較、実行できます。
keywords: wdav, ウイルス対策, ファイアウォール, セキュリティ, Windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7635209c03dfc0367df16bfb650a4e52d2b2b3f8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765325"
---
# <a name="microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="522f6-104">Windows セキュリティ アプリの Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="522f6-104">Microsoft Defender Antivirus in the Windows Security app</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="522f6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="522f6-105">**Applies to:**</span></span>

- [<span data-ttu-id="522f6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="522f6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="522f6-107">Windows 10 バージョン 1703 以降では、Windows Defenderは Windows セキュリティの一部です。</span><span class="sxs-lookup"><span data-stu-id="522f6-107">In Windows 10, version 1703 and later, the Windows Defender app is part of the Windows Security.</span></span>

<span data-ttu-id="522f6-108">Windows Defender クライアントとメインの Windows 設定の一部だった設定が結合され、新しいアプリに移動され、Windows 10 バージョン 1703 の一部として既定でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="522f6-108">Settings that were previously part of the Windows Defender client and main Windows Settings have been combined and moved to the new app, which is installed by default as part of Windows 10, version 1703.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="522f6-109">Windows セキュリティ センター サービスを無効にしても、Microsoft Defender ウイルス対策やファイアウォールWindows Defender [無効にしない](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)。</span><span class="sxs-lookup"><span data-stu-id="522f6-109">Disabling the Windows Security Center service does not disable Microsoft Defender Antivirus or [Windows Defender Firewall](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span> <span data-ttu-id="522f6-110">これらは、サードパーティのウイルス対策製品またはファイアウォール製品がインストールされ、最新の状態に保たれ、自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="522f6-110">These are disabled automatically when a third-party antivirus or firewall product is installed and kept up to date.</span></span>
>
> <span data-ttu-id="522f6-111">Windows セキュリティ センター サービスを無効にするか、関連するグループ ポリシー設定を構成して開始または実行を防ぐ場合、Windows セキュリティ アプリは、デバイスにインストールしたウイルス対策製品またはファイアウォール製品に関する古い情報や不正確な情報を表示する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="522f6-111">If you do disable the Windows Security Center service, or configure its associated Group Policy settings to prevent it from starting or running, the Windows Security app might display stale or inaccurate information about any antivirus or firewall products you have installed on the device.</span></span>
> <span data-ttu-id="522f6-112">また、古いまたは古いサードパーティ製のウイルス対策を使用している場合、または以前にインストールしたサードパーティのウイルス対策製品をアンインストールした場合、Microsoft Defender Antivirus がそれ自体を有効にしなくなっている可能性もあります。</span><span class="sxs-lookup"><span data-stu-id="522f6-112">It might also prevent Microsoft Defender Antivirus from enabling itself if you have an old or outdated third-party antivirus, or if you uninstall any third-party antivirus products you might have previously installed.</span></span>
> <span data-ttu-id="522f6-113">これにより、デバイスの保護が大幅に低下し、マルウェアの感染につながる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="522f6-113">This will significantly lower the protection of your device and could lead to malware infection.</span></span>

<span data-ttu-id="522f6-114">アプリで [監視できる他](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) の Windows セキュリティ機能の詳細については、「Windows セキュリティ」の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="522f6-114">See the [Windows Security article](/windows/threat-protection/windows-defender-security-center/windows-defender-security-center) for more information on other Windows security features that can be monitored in the app.</span></span>

<span data-ttu-id="522f6-115">Windows セキュリティ アプリは、Windows 10 バージョン 1703 以降のクライアント インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="522f6-115">The Windows Security app is a client interface on Windows 10, version 1703 and later.</span></span> <span data-ttu-id="522f6-116">Microsoft Defender for Endpoint の確認と管理に使用される Microsoft Defender セキュリティ センター [Web ポータルではありません](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)。</span><span class="sxs-lookup"><span data-stu-id="522f6-116">It is not the Microsoft Defender Security Center web portal that is used to review and manage [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint).</span></span>

## <a name="review-virus-and-threat-protection-settings-in-the-windows-security-app"></a><span data-ttu-id="522f6-117">Windows セキュリティ アプリでウイルスと脅威保護の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="522f6-117">Review virus and threat protection settings in the Windows Security app</span></span>

![Windows セキュリティ アプリの [ウイルス&保護設定] ラベルのスクリーンショット](images/defender/wdav-protection-settings-wdsc.png)

1. <span data-ttu-id="522f6-119">タスク バーのシールド アイコンをクリックするか、Defender のスタート メニューを検索して、Windows セキュリティ アプリを開 **きます**。</span><span class="sxs-lookup"><span data-stu-id="522f6-119">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="522f6-120">[ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="522f6-120">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>
   
<span data-ttu-id="522f6-121">次のセクションでは、Windows セキュリティ アプリで Microsoft Defender ウイルス対策によって提供される脅威保護を確認または操作する際に、最も一般的なタスクの一部を実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="522f6-121">The following sections describe how to perform some of the most common tasks when reviewing or interacting with the threat protection provided by Microsoft Defender Antivirus in the Windows Security app.</span></span>

> [!NOTE]
> <span data-ttu-id="522f6-122">これらの設定がグループ ポリシーを使用して構成および展開されている場合、このセクションで説明する設定はグレー表示され、個々のエンドポイントで使用できません。</span><span class="sxs-lookup"><span data-stu-id="522f6-122">If these settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> <span data-ttu-id="522f6-123">グループ ポリシー オブジェクトを使用して行った変更は、Windows の設定で設定を更新する前に、最初に個々のエンドポイントに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="522f6-123">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span> <span data-ttu-id="522f6-124">「Microsoft [Defender ウイルス対策によるエンド](configure-end-user-interaction-microsoft-defender-antivirus.md) ユーザー操作の構成」トピックでは、ローカル ポリシーの上書き設定を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="522f6-124">The [Configure end-user interaction with Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md) topic describes how local policy override settings can be configured.</span></span>

## <a name="run-a-scan-with-the-windows-security-app"></a><span data-ttu-id="522f6-125">Windows セキュリティ アプリでスキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="522f6-125">Run a scan with the Windows Security app</span></span>

1. <span data-ttu-id="522f6-126">[セキュリティ] のスタート メニューを検索し、[Windows セキュリティ] を選択して、Windows セキュリティ アプリ **を開きます**。 </span><span class="sxs-lookup"><span data-stu-id="522f6-126">Open the Windows Security app by searching the start menu for **Security**, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="522f6-127">[ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="522f6-127">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="522f6-128">[クイック **スキャン] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="522f6-128">Select **Quick scan**.</span></span> <span data-ttu-id="522f6-129">または、フル スキャンを実行するには、[スキャン **オプション]** を選択し、[フル スキャン] などのオプション **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="522f6-129">Or, to run a full scan, select **Scan options**, and then select an option, such as **Full scan**.</span></span>

## <a name="review-the-security-intelligence-update-version-and-download-the-latest-updates-in-the-windows-security-app"></a><span data-ttu-id="522f6-130">セキュリティ インテリジェンス更新プログラムのバージョンを確認し、Windows セキュリティ アプリで最新の更新プログラムをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="522f6-130">Review the security intelligence update version and download the latest updates in the Windows Security app</span></span>

![セキュリティ インテリジェンスのバージョン番号情報](images/defender/wdav-wdsc-defs.png)

1. <span data-ttu-id="522f6-132">[セキュリティ] のスタート メニューを検索し、[Windows セキュリティ] を選択して、Windows セキュリティ アプリ **を開きます**。 </span><span class="sxs-lookup"><span data-stu-id="522f6-132">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="522f6-133">[ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="522f6-133">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="522f6-134">[ウイルス **対策&更新プログラム] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="522f6-134">Select **Virus & threat protection updates**.</span></span> <span data-ttu-id="522f6-135">現在インストールされているバージョンが、ダウンロードされた時点に関する情報と共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="522f6-135">The currently installed version is displayed along with some information about when it was downloaded.</span></span> <span data-ttu-id="522f6-136">手動でダウンロードできる最新バージョンに対して現在の状態を確認するか、そのバージョンの変更ログを確認できます。</span><span class="sxs-lookup"><span data-stu-id="522f6-136">You can check your current against the latest version available for manual download, or review the change log for that version.</span></span> <span data-ttu-id="522f6-137">「Microsoft [Defender ウイルス対策と他の Microsoft マルウェア](https://www.microsoft.com/en-us/wdsi/defenderupdates)対策のセキュリティ インテリジェンス更新プログラム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="522f6-137">See [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

4. <span data-ttu-id="522f6-138">[更新 **プログラムの確認] を** 選択して、新しい保護更新プログラムをダウンロードします (ある場合)。</span><span class="sxs-lookup"><span data-stu-id="522f6-138">Select **Check for updates** to download new protection updates (if there are any).</span></span>

## <a name="ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app"></a><span data-ttu-id="522f6-139">Windows セキュリティ アプリで Microsoft Defender ウイルス対策が有効になっているか確認する</span><span class="sxs-lookup"><span data-stu-id="522f6-139">Ensure Microsoft Defender Antivirus is enabled in the Windows Security app</span></span>

1. <span data-ttu-id="522f6-140">[セキュリティ] のスタート メニューを検索し、[Windows セキュリティ] を選択して、Windows セキュリティ アプリ **を開きます**。 </span><span class="sxs-lookup"><span data-stu-id="522f6-140">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="522f6-141">[ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="522f6-141">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="522f6-142">[ウイルス **対策&の設定] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="522f6-142">Select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="522f6-143">[リアルタイム保護 **] スイッチを [オン]** に **切り替えます**。</span><span class="sxs-lookup"><span data-stu-id="522f6-143">Toggle the **Real-time protection** switch to **On**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="522f6-144">リアルタイム保護を **オフに** した場合、短時間の遅延後に自動的にオンに戻されます。</span><span class="sxs-lookup"><span data-stu-id="522f6-144">If you switch **Real-time protection** off, it will automatically turn back on after a short delay.</span></span> <span data-ttu-id="522f6-145">これは、マルウェアや脅威から保護されます。</span><span class="sxs-lookup"><span data-stu-id="522f6-145">This is to ensure you are protected from malware and threats.</span></span>
    > <span data-ttu-id="522f6-146">別のウイルス対策製品をインストールすると、Microsoft Defender Antivirus は自動的に自身を無効にし、Windows セキュリティ アプリでそのような状態で示されます。</span><span class="sxs-lookup"><span data-stu-id="522f6-146">If you install another antivirus product, Microsoft Defender Antivirus automatically disables itself and is indicated as such in the Windows Security app.</span></span> <span data-ttu-id="522f6-147">制限された定期的なスキャンを有効にできる [設定が表示されます](limited-periodic-scanning-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="522f6-147">A setting will appear that will allow you to enable [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md).</span></span>

## <a name="add-exclusions-for-microsoft-defender-antivirus-in-the-windows-security-app"></a><span data-ttu-id="522f6-148">Windows セキュリティ アプリで Microsoft Defender ウイルス対策の除外を追加する</span><span class="sxs-lookup"><span data-stu-id="522f6-148">Add exclusions for Microsoft Defender Antivirus in the Windows Security app</span></span>

1. <span data-ttu-id="522f6-149">[セキュリティ] のスタート メニューを検索し、[Windows セキュリティ] を選択して、Windows セキュリティ アプリ **を開きます**。 </span><span class="sxs-lookup"><span data-stu-id="522f6-149">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="522f6-150">[ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="522f6-150">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="522f6-151">[設定の **管理] で**、[ **ウイルス対策の脅威&設定] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="522f6-151">Under the **Manage settings**, select **Virus & threat protection settings**.</span></span>

4. <span data-ttu-id="522f6-152">[除外 **] 設定で** 、[除外の追加と **削除] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="522f6-152">Under the **Exclusions** setting, select **Add or remove exclusions**.</span></span> 

5. <span data-ttu-id="522f6-153">プラス アイコン ( ) を **+** 選択して種類を選択し、除外ごとにオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="522f6-153">Select the plus icon (**+**) to choose the type and set the options for each exclusion.</span></span> 

<span data-ttu-id="522f6-154">次の表に、除外の種類と実行内容の概要を示します。</span><span class="sxs-lookup"><span data-stu-id="522f6-154">The following table summarizes exclusion types and what happens:</span></span>

|<span data-ttu-id="522f6-155">除外の種類</span><span class="sxs-lookup"><span data-stu-id="522f6-155">Exclusion type</span></span>  |<span data-ttu-id="522f6-156">によって定義される</span><span class="sxs-lookup"><span data-stu-id="522f6-156">Defined by</span></span>  |<span data-ttu-id="522f6-157">結果</span><span class="sxs-lookup"><span data-stu-id="522f6-157">What happens</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="522f6-158">**File**</span><span class="sxs-lookup"><span data-stu-id="522f6-158">**File**</span></span> |<span data-ttu-id="522f6-159">場所</span><span class="sxs-lookup"><span data-stu-id="522f6-159">Location</span></span> <br/><span data-ttu-id="522f6-160">例: `c:\sample\sample.test`</span><span class="sxs-lookup"><span data-stu-id="522f6-160">Example: `c:\sample\sample.test`</span></span> |<span data-ttu-id="522f6-161">特定のファイルは、Microsoft Defender ウイルス対策によってスキップされます。</span><span class="sxs-lookup"><span data-stu-id="522f6-161">The specific file is skipped by Microsoft Defender Antivirus.</span></span> |
|<span data-ttu-id="522f6-162">**Folder**</span><span class="sxs-lookup"><span data-stu-id="522f6-162">**Folder**</span></span>    |<span data-ttu-id="522f6-163">場所</span><span class="sxs-lookup"><span data-stu-id="522f6-163">Location</span></span> <br/><span data-ttu-id="522f6-164">例: `c:\test\sample`</span><span class="sxs-lookup"><span data-stu-id="522f6-164">Example: `c:\test\sample`</span></span>       |<span data-ttu-id="522f6-165">指定したフォルダー内のすべてのアイテムは、Microsoft Defender ウイルス対策によってスキップされます。</span><span class="sxs-lookup"><span data-stu-id="522f6-165">All items in the specified folder are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="522f6-166">**ファイルの種類**</span><span class="sxs-lookup"><span data-stu-id="522f6-166">**File type**</span></span>   |<span data-ttu-id="522f6-167">ファイル拡張子</span><span class="sxs-lookup"><span data-stu-id="522f6-167">File extension</span></span> <br/><span data-ttu-id="522f6-168">例: `.test`</span><span class="sxs-lookup"><span data-stu-id="522f6-168">Example: `.test`</span></span> |<span data-ttu-id="522f6-169">デバイス上の任意 `.test` の場所に拡張子を持つすべてのファイルは、Microsoft Defender Antivirus によってスキップされます。</span><span class="sxs-lookup"><span data-stu-id="522f6-169">All files with the `.test` extension anywhere on your device are skipped by Microsoft Defender Antivirus.</span></span>         |
|<span data-ttu-id="522f6-170">**プロセス**</span><span class="sxs-lookup"><span data-stu-id="522f6-170">**Process**</span></span>     |<span data-ttu-id="522f6-171">実行可能ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="522f6-171">Executable file path</span></span> <br><span data-ttu-id="522f6-172">例: `c:\test\process.exe`</span><span class="sxs-lookup"><span data-stu-id="522f6-172">Example: `c:\test\process.exe`</span></span>         |<span data-ttu-id="522f6-173">特定のプロセスと、そのプロセスによって開くファイルは、Microsoft Defender ウイルス対策によってスキップされます。</span><span class="sxs-lookup"><span data-stu-id="522f6-173">The specific process and any files that are opened by that process are skipped by Microsoft Defender Antivirus.</span></span>         |

<span data-ttu-id="522f6-174">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="522f6-174">To learn more, see the following resources:</span></span>
- [<span data-ttu-id="522f6-175">ファイル拡張子とフォルダーの場所に基づいて除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="522f6-175">Configure and validate exclusions based on file extension and folder location</span></span>](./configure-extension-file-exclusions-microsoft-defender-antivirus.md) 
- [<span data-ttu-id="522f6-176">プロセスによって開いたファイルの除外を構成する</span><span class="sxs-lookup"><span data-stu-id="522f6-176">Configure exclusions for files opened by processes</span></span>](./configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="review-threat-detection-history-in-the-windows-defender-security-center-app"></a><span data-ttu-id="522f6-177">セキュリティ センター アプリで脅威検出Windows Defender確認する</span><span class="sxs-lookup"><span data-stu-id="522f6-177">Review threat detection history in the Windows Defender Security Center app</span></span>

1. <span data-ttu-id="522f6-178">[セキュリティ] のスタート メニューを検索し、[Windows セキュリティ] を選択して、Windows セキュリティ アプリ **を開きます**。 </span><span class="sxs-lookup"><span data-stu-id="522f6-178">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="522f6-179">[ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="522f6-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="522f6-180">[保護 **履歴] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="522f6-180">Select **Protection history**.</span></span> <span data-ttu-id="522f6-181">最近のアイテムが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="522f6-181">Any recent items are listed.</span></span>

## <a name="set-ransomware-protection-and-recovery-options"></a><span data-ttu-id="522f6-182">ランサムウェアの保護と回復のオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="522f6-182">Set ransomware protection and recovery options</span></span>

1. <span data-ttu-id="522f6-183">[セキュリティ] のスタート メニューを検索し、[Windows セキュリティ] を選択して、Windows セキュリティ アプリ **を開きます**。 </span><span class="sxs-lookup"><span data-stu-id="522f6-183">Open the Windows Security app by searching the start menu for *Security*, and then selecting **Windows Security**.</span></span>

2. <span data-ttu-id="522f6-184">[ウイルス **対策] &タイル** (または左側のメニュー バーのシールド アイコン) を選択します。</span><span class="sxs-lookup"><span data-stu-id="522f6-184">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar).</span></span>

3. <span data-ttu-id="522f6-185">[ **ランサムウェア保護] で、[** ランサムウェア **保護の管理] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="522f6-185">Under **Ransomware protection**, select **Manage ransomware protection**.</span></span>

4. <span data-ttu-id="522f6-186">[フォルダー アクセス **の制御] 設定を変更** するには、「フォルダー アクセスの制御を [使用して重要なフォルダーを保護する」を参照してください](/microsoft-365/security/defender-endpoint/controlled-folders)。</span><span class="sxs-lookup"><span data-stu-id="522f6-186">To change **Controlled folder access** settings, see [Protect important folders with Controlled folder access](/microsoft-365/security/defender-endpoint/controlled-folders).</span></span>

5. <span data-ttu-id="522f6-187">ランサムウェアの回復オプションを設定するには、[ランサムウェア のデータ復旧] で [セットアップ] を選択し、OneDrive アカウントをリンクまたはセットアップする手順に従って、ランサムウェア攻撃から簡単に回復できます。</span><span class="sxs-lookup"><span data-stu-id="522f6-187">To set up ransomware recovery options, select **Set up** under **Ransomware data recovery** and follow the instructions for linking or setting up your OneDrive account so you can easily recover from a ransomware attack.</span></span>

## <a name="see-also"></a><span data-ttu-id="522f6-188">関連項目</span><span class="sxs-lookup"><span data-stu-id="522f6-188">See also</span></span>
- [<span data-ttu-id="522f6-189">Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="522f6-189">Microsoft Defender Antivirus</span></span>](microsoft-defender-antivirus-in-windows-10.md)