---
title: サード パーティ製ソリューションからの移行中に Microsoft Defender ウイルス対策のトラブルシューティングを行う
description: Microsoft Defender ウイルス対策に移行する際の一般的なエラーのトラブルシューティング
keywords: イベント, エラー コード, ログ記録, トラブルシューティング, Microsoft Defender ウイルス対策, Windows Defender ウイルス対策, 移行
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3fcc79e767edb533a20402a2f92ba4abc7d8386a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764593"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a><span data-ttu-id="89699-104">サード パーティ製ソリューションからの移行中に Microsoft Defender ウイルス対策のトラブルシューティングを行う</span><span class="sxs-lookup"><span data-stu-id="89699-104">Troubleshoot Microsoft Defender Antivirus while migrating from a third-party solution</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="89699-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="89699-105">**Applies to:**</span></span>

- [<span data-ttu-id="89699-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="89699-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)


<span data-ttu-id="89699-107">サードパーティのセキュリティ ソリューションから Microsoft Defender Antivirus への移行中に問題が発生した場合は、ここでヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="89699-107">You can find help here if you encounter issues while migrating from a third-party security solution to Microsoft Defender Antivirus.</span></span>

## <a name="review-event-logs"></a><span data-ttu-id="89699-108">イベント ログの確認</span><span class="sxs-lookup"><span data-stu-id="89699-108">Review event logs</span></span>

<span data-ttu-id="89699-109">タスク バーの [検索]アイコンを選択し、イベント ビューアーを検索して、イベント ビューアー アプリ *を開きます*。</span><span class="sxs-lookup"><span data-stu-id="89699-109">Open the Event viewer app by selecting the **Search** icon in the taskbar, and searching for *event viewer*.</span></span>

<span data-ttu-id="89699-110">Microsoft Defender ウイルス対策に関する情報は、「**アプリケーション** とサービス ログ Microsoft Windows のログ」の下  >    >    >  Windows Defender。</span><span class="sxs-lookup"><span data-stu-id="89699-110">Information about Microsoft Defender Antivirus can be found under  **Applications and Services Logs** > **Microsoft** > **Windows** > **Windows Defender**.</span></span> 

<span data-ttu-id="89699-111">そこから、[操作] の **下にある [** 開く] **を選択します**。</span><span class="sxs-lookup"><span data-stu-id="89699-111">From there, select **Open** underneath **Operational**.</span></span>

<span data-ttu-id="89699-112">詳細ウィンドウからイベントを選択すると、[全般] タブと [詳細] タブの下の下部ウィンドウにイベントの詳細 **が\*\*\*\*表示** されます。</span><span class="sxs-lookup"><span data-stu-id="89699-112">Selecting an event from the details pane will show you more information about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

## <a name="microsoft-defender-antivirus-wont-start"></a><span data-ttu-id="89699-113">Microsoft Defender ウイルス対策が開始しない</span><span class="sxs-lookup"><span data-stu-id="89699-113">Microsoft Defender Antivirus won't start</span></span>

<span data-ttu-id="89699-114">この問題は、複数の異なるイベントの ID の形式で発生する可能性があります。そのすべてが同じ原因を持っています。</span><span class="sxs-lookup"><span data-stu-id="89699-114">This issue can manifest in the form of  several different event IDs, all of which have the same underlying cause.</span></span>

### <a name="associated-event-ids"></a><span data-ttu-id="89699-115">関連付けられたイベントの ID</span><span class="sxs-lookup"><span data-stu-id="89699-115">Associated event IDs</span></span>

 <span data-ttu-id="89699-116">イベント ID</span><span class="sxs-lookup"><span data-stu-id="89699-116">Event ID</span></span> | <span data-ttu-id="89699-117">ログ名</span><span class="sxs-lookup"><span data-stu-id="89699-117">Log name</span></span> | <span data-ttu-id="89699-118">説明</span><span class="sxs-lookup"><span data-stu-id="89699-118">Description</span></span> | <span data-ttu-id="89699-119">ソース</span><span class="sxs-lookup"><span data-stu-id="89699-119">Source</span></span>
-|-|-|-
<span data-ttu-id="89699-120">15 </span><span class="sxs-lookup"><span data-stu-id="89699-120">15</span></span> | <span data-ttu-id="89699-121">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="89699-121">Application</span></span> | <span data-ttu-id="89699-122">更新されたWindows Defender状態が正常に更新SECURITY_PRODUCT_STATE_OFF。</span><span class="sxs-lookup"><span data-stu-id="89699-122">Updated Windows Defender status successfully to SECURITY_PRODUCT_STATE_OFF.</span></span> | <span data-ttu-id="89699-123">セキュリティ センター</span><span class="sxs-lookup"><span data-stu-id="89699-123">Security Center</span></span>
<span data-ttu-id="89699-124">5007</span><span class="sxs-lookup"><span data-stu-id="89699-124">5007</span></span> | <span data-ttu-id="89699-125">Microsoft-Windows-Windows Defender/運用</span><span class="sxs-lookup"><span data-stu-id="89699-125">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="89699-126">Windows Defenderの構成が変更されました。</span><span class="sxs-lookup"><span data-stu-id="89699-126">Windows Defender Antivirus Configuration has changed.</span></span>  <span data-ttu-id="89699-127">予期しないイベントの場合は、マルウェアの結果である可能性がある設定を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="89699-127">If this is an unexpected event you should review the settings as this may be the result of malware.</span></span><br /><br /><span data-ttu-id="89699-128">**古い値:** Default\IsServiceRunning = 0x0</span><span class="sxs-lookup"><span data-stu-id="89699-128">**Old value:** Default\IsServiceRunning = 0x0</span></span><br /><span data-ttu-id="89699-129">**新しい値:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span><span class="sxs-lookup"><span data-stu-id="89699-129">**New value:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1</span></span> | <span data-ttu-id="89699-130">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="89699-130">Windows Defender</span></span>
<span data-ttu-id="89699-131">5010</span><span class="sxs-lookup"><span data-stu-id="89699-131">5010</span></span> | <span data-ttu-id="89699-132">Microsoft-Windows-Windows Defender/運用</span><span class="sxs-lookup"><span data-stu-id="89699-132">Microsoft-Windows-Windows Defender/Operational</span></span> | <span data-ttu-id="89699-133">Windows Defenderスパイウェアなどの望ましくない可能性があるソフトウェアのウイルス対策スキャンが無効になります。</span><span class="sxs-lookup"><span data-stu-id="89699-133">Windows Defender Antivirus scanning for spyware and other potentially unwanted software is disabled.</span></span> | <span data-ttu-id="89699-134">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="89699-134">Windows Defender</span></span>

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a><span data-ttu-id="89699-135">サード パーティ製ウイルス対策がインストールされたため、Microsoft Defender Antivirus が起動しないかを確認する方法</span><span class="sxs-lookup"><span data-stu-id="89699-135">How to tell if Microsoft Defender Antivirus won't start because a third-party antivirus is installed</span></span>

<span data-ttu-id="89699-136">Windows 10 デバイスで、Microsoft Defender for Endpoint を使用していない場合、サードパーティのウイルス対策がインストールされている場合、Microsoft Defender ウイルス対策は自動的に無効になります。</span><span class="sxs-lookup"><span data-stu-id="89699-136">On a Windows 10 device, if you are not using Microsoft Defender for Endpoint, and you have a third-party antivirus installed, then Microsoft Defender Antivirus will be automatically turned off.</span></span> <span data-ttu-id="89699-137">サードパーティのウイルス対策がインストールされている Microsoft Defender for Endpoint を使用している場合、Microsoft Defender Antivirus はパッシブ モードで起動し、機能が低下します。</span><span class="sxs-lookup"><span data-stu-id="89699-137">If you are using Microsoft Defender for Endpoint with a third-party antivirus installed, Microsoft Defender Antivirus will start in passive mode, with reduced functionality.</span></span>

> [!TIP]
> <span data-ttu-id="89699-138">説明したシナリオは、Windows 10 にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="89699-138">The scenario just described applies only to Windows 10.</span></span> <span data-ttu-id="89699-139">他のバージョンの Windows[](microsoft-defender-antivirus-compatibility.md)では、サードパーティのセキュリティ ソフトウェアと共に実行されている Microsoft Defender ウイルス対策に対する応答が異なります。</span><span class="sxs-lookup"><span data-stu-id="89699-139">Other versions of Windows have [different responses](microsoft-defender-antivirus-compatibility.md) to Microsoft Defender Antivirus being run alongside third-party security software.</span></span>

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a><span data-ttu-id="89699-140">サービス アプリを使用して Microsoft Defender ウイルス対策が無効になっているか確認する</span><span class="sxs-lookup"><span data-stu-id="89699-140">Use Services app to check if Microsoft Defender Antivirus is turned off</span></span>

<span data-ttu-id="89699-141">サービス アプリを開く場合は、タスク バーから **[検索** ] アイコンを選択し、サービスを検索 *します*。</span><span class="sxs-lookup"><span data-stu-id="89699-141">To open the Services app, select the **Search** icon from the taskbar and search for *services*.</span></span> <span data-ttu-id="89699-142">services.msc と入力して、コマンド ラインから *アプリを開く方法もあります*。</span><span class="sxs-lookup"><span data-stu-id="89699-142">You can also open the app from the command-line by typing *services.msc*.</span></span>

<span data-ttu-id="89699-143">Microsoft Defender ウイルス対策に関する情報は、[運用]の [サービス] アプリWindows Defender  >  **されます**。</span><span class="sxs-lookup"><span data-stu-id="89699-143">Information about Microsoft Defender Antivirus will be listed within the Services app under **Windows Defender** > **Operational**.</span></span> <span data-ttu-id="89699-144">ウイルス対策サービス名はウイルス *Windows Defenderサービスです*。</span><span class="sxs-lookup"><span data-stu-id="89699-144">The antivirus service name is *Windows Defender Antivirus Service*.</span></span>

<span data-ttu-id="89699-145">アプリの確認中に *、Windows Defender ウイルス* 対策サービスが手動に設定されている場合がありますが、このサービスを手動で開始しようとすると、ローカル コンピューターの Windows Defender ウイルス対策サービス サービスが開始され、停止したという警告が表示されます。 *一部のサービスは、他のサービスやプログラムで使用されていない場合に自動的に停止します。*</span><span class="sxs-lookup"><span data-stu-id="89699-145">While checking the app, you may see that *Windows Defender Antivirus Service* is set to manual — but when you try to start this service manually, you get a warning stating, *The Windows Defender Antivirus Service service on Local Computer started and then stopped. Some services stop automatically if they are not in use by other services or programs.*</span></span>

<span data-ttu-id="89699-146">これは、サードパーティのウイルス対策との互換性を維持するために Microsoft Defender ウイルス対策が自動的にオフになっていることを示します。</span><span class="sxs-lookup"><span data-stu-id="89699-146">This indicates that Microsoft Defender Antivirus has been automatically turned off to preserve compatibility with a third-party antivirus.</span></span>

#### <a name="generate-a-detailed-report"></a><span data-ttu-id="89699-147">詳細レポートの生成</span><span class="sxs-lookup"><span data-stu-id="89699-147">Generate a detailed report</span></span>

<span data-ttu-id="89699-148">管理モードでコマンド プロンプトを開き、次のコマンドを入力すると、現在アクティブなグループ ポリシーに関する詳細なレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="89699-148">You can generate a detailed report about currently active group policies by opening a command prompt in **Run as admin** mode, then entering the following command:</span></span>

```powershell
GPresult.exe /h gpresult.html
```

<span data-ttu-id="89699-149">これにより、./gpresult.html にある *レポートが生成されます*。</span><span class="sxs-lookup"><span data-stu-id="89699-149">This will generate a report located at *./gpresult.html*.</span></span> <span data-ttu-id="89699-150">このファイルを開き、Microsoft Defender ウイルス対策がオフになっている方法に応じて、次の結果が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="89699-150">Open this file and you might see the following results, depending on how Microsoft Defender Antivirus was turned off.</span></span>

##### <a name="group-policy-results"></a><span data-ttu-id="89699-151">グループ ポリシーの結果</span><span class="sxs-lookup"><span data-stu-id="89699-151">Group policy results</span></span>

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a><span data-ttu-id="89699-152">セキュリティ設定がドメインまたはローカル レベルのグループ ポリシー (GPO) または System Center Configuration Manager (SCCM) を介して実装されている場合</span><span class="sxs-lookup"><span data-stu-id="89699-152">If security settings are implemented via group policy (GPO) at the domain or local level, or though System center configuration manager (SCCM)</span></span>

<span data-ttu-id="89699-153">GPResults レポートの見出しの下にある *[Windows コンポーネント/Windows Defender ウイルス* 対策] では、Microsoft Defender ウイルス対策がオフになっていることを示す次のエントリのようなものが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="89699-153">Within the GPResults report, under the heading, *Windows Components/Windows Defender Antivirus*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="89699-154">ポリシー</span><span class="sxs-lookup"><span data-stu-id="89699-154">Policy</span></span> | <span data-ttu-id="89699-155">設定</span><span class="sxs-lookup"><span data-stu-id="89699-155">Setting</span></span> | <span data-ttu-id="89699-156">GPO を獲得する</span><span class="sxs-lookup"><span data-stu-id="89699-156">Winning GPO</span></span>
-|-|-
<span data-ttu-id="89699-157">ウイルス対策をWindows Defenderする</span><span class="sxs-lookup"><span data-stu-id="89699-157">Turn off Windows Defender Antivirus</span></span> | <span data-ttu-id="89699-158">Enabled</span><span class="sxs-lookup"><span data-stu-id="89699-158">Enabled</span></span> | <span data-ttu-id="89699-159">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="89699-159">Win10-Workstations</span></span>

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a><span data-ttu-id="89699-160">グループ ポリシーの基本設定 (GPP) を使用してセキュリティ設定を実装する場合</span><span class="sxs-lookup"><span data-stu-id="89699-160">If security settings are implemented via Group policy preference (GPP)</span></span>

<span data-ttu-id="89699-161">見出しの下にあるレジストリ アイテム (キー パス *: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender、 Value name: DisableAntiSpyware)* では、Microsoft Defender Antivirus がオフになっていることを示す次のエントリのようなものが表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="89699-161">Under the heading, *Registry item (Key path: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Value name: DisableAntiSpyware)*, you may see something like the following entry, indicating that Microsoft Defender Antivirus is turned off.</span></span>

<span data-ttu-id="89699-162">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="89699-162">DisableAntiSpyware</span></span> | -
-|-
<span data-ttu-id="89699-163">GPO を獲得する</span><span class="sxs-lookup"><span data-stu-id="89699-163">Winning GPO</span></span> | <span data-ttu-id="89699-164">Win10-Workstations</span><span class="sxs-lookup"><span data-stu-id="89699-164">Win10-Workstations</span></span>
<span data-ttu-id="89699-165">結果: 成功</span><span class="sxs-lookup"><span data-stu-id="89699-165">Result: Success</span></span> | 
<span data-ttu-id="89699-166">**全般**</span><span class="sxs-lookup"><span data-stu-id="89699-166">**General**</span></span> | 
<span data-ttu-id="89699-167">Action</span><span class="sxs-lookup"><span data-stu-id="89699-167">Action</span></span> | <span data-ttu-id="89699-168">Update</span><span class="sxs-lookup"><span data-stu-id="89699-168">Update</span></span>
<span data-ttu-id="89699-169">**プロパティ**</span><span class="sxs-lookup"><span data-stu-id="89699-169">**Properties**</span></span> | 
<span data-ttu-id="89699-170">ハイブ</span><span class="sxs-lookup"><span data-stu-id="89699-170">Hive</span></span> | <span data-ttu-id="89699-171">HKEY_LOCAL_MACHINE</span><span class="sxs-lookup"><span data-stu-id="89699-171">HKEY_LOCAL_MACHINE</span></span>
<span data-ttu-id="89699-172">キー パス</span><span class="sxs-lookup"><span data-stu-id="89699-172">Key path</span></span> | <span data-ttu-id="89699-173">SOFTWARE\Policies\Microsoft\Windows Defender</span><span class="sxs-lookup"><span data-stu-id="89699-173">SOFTWARE\Policies\Microsoft\Windows Defender</span></span>
<span data-ttu-id="89699-174">値の名前</span><span class="sxs-lookup"><span data-stu-id="89699-174">Value name</span></span> | <span data-ttu-id="89699-175">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="89699-175">DisableAntiSpyware</span></span>
<span data-ttu-id="89699-176">値の型</span><span class="sxs-lookup"><span data-stu-id="89699-176">Value type</span></span> | <span data-ttu-id="89699-177">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="89699-177">REG_DWORD</span></span>
<span data-ttu-id="89699-178">値データ</span><span class="sxs-lookup"><span data-stu-id="89699-178">Value data</span></span> | <span data-ttu-id="89699-179">0x1 (1)</span><span class="sxs-lookup"><span data-stu-id="89699-179">0x1 (1)</span></span>

###### <a name="if-security-settings-are-implemented-via-registry-key"></a><span data-ttu-id="89699-180">セキュリティ設定がレジストリ キーを使用して実装されている場合</span><span class="sxs-lookup"><span data-stu-id="89699-180">If security settings are implemented via registry key</span></span>

<span data-ttu-id="89699-181">レポートには、Microsoft Defender ウイルス対策が無効になっていることを示す次のテキストが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="89699-181">The report may contain the following text, indicating that Microsoft Defender Antivirus is turned off:</span></span>
 
> <span data-ttu-id="89699-182">レジストリ (regedit.exe)</span><span class="sxs-lookup"><span data-stu-id="89699-182">Registry (regedit.exe)</span></span>
>
> <span data-ttu-id="89699-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (16 進数)</span><span class="sxs-lookup"><span data-stu-id="89699-183">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)</span></span>

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a><span data-ttu-id="89699-184">Windows または Windows Server イメージでセキュリティ設定が設定されている場合</span><span class="sxs-lookup"><span data-stu-id="89699-184">If security settings are set in Windows or your Windows Server image</span></span>

<span data-ttu-id="89699-185">想像上の管理者は、セキュリティ ポリシー **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)** を *GPEdit.exe*、 *LGPO.exe* 経由でローカルに設定するか、タスク シーケンスでレジストリを変更している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89699-185">Your imagining admin might have set the security policy, **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, locally via *GPEdit.exe*, *LGPO.exe*, or by modifying the registry in their task sequence.</span></span> <span data-ttu-id="89699-186">Microsoft Defender [ウイルス対策の信頼済みイメージ識別子](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) を構成できます。</span><span class="sxs-lookup"><span data-stu-id="89699-186">You can [configure a Trusted Image Identifier](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) for Microsoft Defender Antivirus.</span></span>

### <a name="turn-microsoft-defender-antivirus-back-on"></a><span data-ttu-id="89699-187">Microsoft Defender ウイルス対策を有効に戻す</span><span class="sxs-lookup"><span data-stu-id="89699-187">Turn Microsoft Defender Antivirus back on</span></span>

<span data-ttu-id="89699-188">他のウイルス対策が現在アクティブにされていない場合、Microsoft Defender ウイルス対策は自動的に有効になります。</span><span class="sxs-lookup"><span data-stu-id="89699-188">Microsoft Defender Antivirus will automatically turn on if no other antivirus is currently active.</span></span> <span data-ttu-id="89699-189">Microsoft Defender Antivirus を完全な機能で実行するには、サードパーティのウイルス対策を完全にオフにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="89699-189">You'll need to turn the third-party antivirus completely off to ensure Microsoft Defender Antivirus can run with full functionality.</span></span>

> [!WARNING]
> <span data-ttu-id="89699-190">HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Servicesの wdboot、wdfilter、wdnisdrv、wdnisdrv、*および* *windefend* の Windows Defender の開始値を編集するソリューションはサポートされていないため、強制的にシステムを再イメージ化する可能性があります。   </span><span class="sxs-lookup"><span data-stu-id="89699-190">Solutions suggesting that you edit the *Windows Defender* start values for *wdboot*, *wdfilter*, *wdnisdrv*, *wdnissvc*, and *windefend* in  HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services are unsupported, and may force you to re-image your system.</span></span>

<span data-ttu-id="89699-191">パッシブ モードは、Microsoft Defender for Endpoint の使用を開始し、Microsoft Defender Antivirus と共にサードパーティのウイルス対策を開始する場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="89699-191">Passive mode is available if you start using Microsoft Defender for Endpoint and a third-party antivirus together with Microsoft Defender Antivirus.</span></span> <span data-ttu-id="89699-192">パッシブ モードでは、Microsoft Defender はファイルをスキャンしてそれ自体を更新できますが、脅威を修復しません。</span><span class="sxs-lookup"><span data-stu-id="89699-192">Passive mode allows Microsoft Defender to scan files and update itself, but it will not remediate threats.</span></span> <span data-ttu-id="89699-193">さらに、リアルタイム保護による動作[](configure-real-time-protection-microsoft-defender-antivirus.md)監視は、エンドポイント データ損失防止[(DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview)が展開されていない限り、パッシブ モードでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="89699-193">In addition, behavior monitoring via [Real Time Protection](configure-real-time-protection-microsoft-defender-antivirus.md) is not available under passive mode, unless [Endpoint data loss prevention (DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) is deployed.</span></span>

<span data-ttu-id="89699-194">Microsoft Defender Antivirus [が自動的に](limited-periodic-scanning-microsoft-defender-antivirus.md)オフに設定されている場合は、制限付き定期的なスキャンと呼ばれるもう 1 つの機能をエンド ユーザーが利用できます。</span><span class="sxs-lookup"><span data-stu-id="89699-194">Another feature, known as [limited periodic scanning](limited-periodic-scanning-microsoft-defender-antivirus.md), is available to end-users when Microsoft Defender Antivirus is set to automatically turn off.</span></span> <span data-ttu-id="89699-195">この機能を使用すると、Microsoft Defender Antivirus は、限られた数の検出を使用して、サードパーティのウイルス対策と一緒に定期的にファイルをスキャンできます。</span><span class="sxs-lookup"><span data-stu-id="89699-195">This feature allows Microsoft Defender Antivirus to scan files periodically alongside a third-party antivirus, using a limited number of detections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89699-196">エンタープライズ環境では、限定的な定期的なスキャンは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="89699-196">Limited periodic scanning is not recommended in enterprise environments.</span></span> <span data-ttu-id="89699-197">このモードで Microsoft Defender ウイルス対策を実行するときに使用できる検出、管理、およびレポート機能は、アクティブ モードと比較して低下します。</span><span class="sxs-lookup"><span data-stu-id="89699-197">The detection, management and reporting capabilities available when running Microsoft Defender Antivirus in this mode are reduced as compared to active mode.</span></span>

### <a name="see-also"></a><span data-ttu-id="89699-198">関連項目</span><span class="sxs-lookup"><span data-stu-id="89699-198">See also</span></span>

* [<span data-ttu-id="89699-199">Microsoft Defender ウイルス対策の互換性</span><span class="sxs-lookup"><span data-stu-id="89699-199">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
* [<span data-ttu-id="89699-200">Windows セキュリティ アプリの Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="89699-200">Microsoft Defender Antivirus in the Windows Security app</span></span>](microsoft-defender-security-center-antivirus.md)