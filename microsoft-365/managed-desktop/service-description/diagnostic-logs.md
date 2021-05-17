---
title: 診断ログ
description: トラブルシューティング中にデバイスから収集される可能性があるログと、デバイスの保存方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ef7d19fef989610c10323c2a9820a5314d5e1641
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272897"
---
# <a name="diagnostic-logs"></a><span data-ttu-id="ee39a-104">診断ログ</span><span class="sxs-lookup"><span data-stu-id="ee39a-104">Diagnostic logs</span></span>

<span data-ttu-id="ee39a-105">Microsoft Managed Desktop が管理するデバイスに関する問題のトラブルシューティングを行う場合は、報告したデバイスか、サービスによって識別されたデバイスかを問わずに、ユーザーの介入なしにデバイスから特定の診断ログを収集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee39a-105">When we troubleshoot an issue on a device managed by Microsoft Managed Desktop, whether one you've reported or one identified by our service, we might have to collect certain diagnostic logs from the device without intervention from the user.</span></span> <span data-ttu-id="ee39a-106">ユーザーが生成したコンテンツや情報をユーザー ディレクトリから収集しません。</span><span class="sxs-lookup"><span data-stu-id="ee39a-106">We don't collect any user-generated content or information from user directories.</span></span> <span data-ttu-id="ee39a-107">デバイスの正常性と状態に関する診断データとログ データのみを収集します。</span><span class="sxs-lookup"><span data-stu-id="ee39a-107">We only collect diagnostic and log data that concerns device health and status.</span></span>

<span data-ttu-id="ee39a-108">収集されたログは 28 日間保存され、削除されます。</span><span class="sxs-lookup"><span data-stu-id="ee39a-108">We store any collected logs for 28 days, and then delete them.</span></span> <span data-ttu-id="ee39a-109">データ処理標準に従ってデバイスから収集されたログ [を処理します](privacy-personal-data.md)。</span><span class="sxs-lookup"><span data-stu-id="ee39a-109">We process any logs collected from a device following our [data handling standards](privacy-personal-data.md).</span></span>

## <a name="data-collected"></a><span data-ttu-id="ee39a-110">収集されるデータ</span><span class="sxs-lookup"><span data-stu-id="ee39a-110">Data collected</span></span>

<span data-ttu-id="ee39a-111">この一覧には、Microsoft Managed Desktop が診断ログを収集する可能性があるすべてのフォルダー、イベント ログ、実行可能ファイル、またはレジストリの場所が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ee39a-111">This list includes all the folders, event logs, executables, or registry locations that Microsoft Managed Desktop might collect diagnostic logs from.</span></span> <span data-ttu-id="ee39a-112">収集される実際のデータは、このリストのサブセットであり、特定された問題に依存します。</span><span class="sxs-lookup"><span data-stu-id="ee39a-112">The actual data collected will be a subset of this list and depends on the identified issue.</span></span>

### <a name="registry-keys"></a><span data-ttu-id="ee39a-113">レジストリ キー</span><span class="sxs-lookup"><span data-stu-id="ee39a-113">Registry keys</span></span>

- <span data-ttu-id="ee39a-114">HKLM \\ SYSTEM \\ CurrentControlSet \\ Services</span><span class="sxs-lookup"><span data-stu-id="ee39a-114">HKLM\\SYSTEM\\CurrentControlSet\\Services</span></span>
- <span data-ttu-id="ee39a-115">HKLM \\ SOFTWARE \\ Microsoft \\ Surface</span><span class="sxs-lookup"><span data-stu-id="ee39a-115">HKLM\\SOFTWARE\\Microsoft\\Surface</span></span>
- <span data-ttu-id="ee39a-116">HKLM \\ ソフトウェア ポリシー Microsoft Windows \\ \\ \\ \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="ee39a-116">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows\\WindowsUpdate</span></span>
- <span data-ttu-id="ee39a-117">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ MUI \\ UILanguages</span><span class="sxs-lookup"><span data-stu-id="ee39a-117">HKLM\\SYSTEM\\CurrentControlSet\\Control\\MUI\\UILanguages</span></span>
- <span data-ttu-id="ee39a-118">HKLM \\ ソフトウェア ポリシー Microsoft \\ \\ \\ WindowsStore</span><span class="sxs-lookup"><span data-stu-id="ee39a-118">HKLM\\Software\\Policies\\Microsoft\\WindowsStore</span></span>
- <span data-ttu-id="ee39a-119">HKLM \\ ソフトウェア Microsoft Windows \\ \\ \\ CurrentVersion \\ WindowsStore \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="ee39a-119">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\WindowsStore\\WindowsUpdate</span></span>
- <span data-ttu-id="ee39a-120">HKLM \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="ee39a-120">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="ee39a-121">HKLM \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion</span><span class="sxs-lookup"><span data-stu-id="ee39a-121">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion</span></span>
- <span data-ttu-id="ee39a-122">HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ AppModel</span><span class="sxs-lookup"><span data-stu-id="ee39a-122">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\AppModel</span></span>
- <span data-ttu-id="ee39a-123">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ FirmwareResources</span><span class="sxs-lookup"><span data-stu-id="ee39a-123">HKLM\\SYSTEM\\CurrentControlSet\\Control\\FirmwareResources</span></span>
- <span data-ttu-id="ee39a-124">HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost</span><span class="sxs-lookup"><span data-stu-id="ee39a-124">HKLM\\SOFTWARE\\Microsoft\\WindowsSelfhost</span></span>
- <span data-ttu-id="ee39a-125">HKLM \\ ソフトウェア \\ Microsoft \\ WindowsUpdate</span><span class="sxs-lookup"><span data-stu-id="ee39a-125">HKLM\\SOFTWARE\\Microsoft\\WindowsUpdate</span></span>
- <span data-ttu-id="ee39a-126">HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ Appx</span><span class="sxs-lookup"><span data-stu-id="ee39a-126">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Appx</span></span>
- <span data-ttu-id="ee39a-127">HKLM \\ SOFTWARE \\ Microsoft \\ Windows NT \\ CurrentVersion \\ Superfetch</span><span class="sxs-lookup"><span data-stu-id="ee39a-127">HKLM\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Superfetch</span></span>
- <span data-ttu-id="ee39a-128">HKLM \\ SYSTEM \\ Setup</span><span class="sxs-lookup"><span data-stu-id="ee39a-128">HKLM\\SYSTEM\\Setup</span></span>
- <span data-ttu-id="ee39a-129">HKLM \\ ソフトウェア \\ Microsoft \\ IntuneManagementExtension</span><span class="sxs-lookup"><span data-stu-id="ee39a-129">HKLM\\Software\\Microsoft\\IntuneManagementExtension</span></span>
- <span data-ttu-id="ee39a-130">HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot</span><span class="sxs-lookup"><span data-stu-id="ee39a-130">HKLM\\SOFTWARE\\Microsoft\\SystemCertificates\\AuthRoot</span></span>
- <span data-ttu-id="ee39a-131">HKLM \\ SOFTWARE \\ Microsoft \\ Windows Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ee39a-131">HKLM\\SOFTWARE\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="ee39a-132">HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ Authentication \\ LogonUI</span><span class="sxs-lookup"><span data-stu-id="ee39a-132">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI</span></span>
- <span data-ttu-id="ee39a-133">HKLM \\ SOFTWARE \\ Microsoft \\ Windows \\ CurrentVersion \\ Internet Settings</span><span class="sxs-lookup"><span data-stu-id="ee39a-133">HKLM\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings</span></span>
- <span data-ttu-id="ee39a-134">HKLM \\ ソフトウェア Microsoft Windows \\ \\ \\ CurrentVersion \\ アンインストール</span><span class="sxs-lookup"><span data-stu-id="ee39a-134">HKLM\\Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="ee39a-135">HKLM \\ ソフトウェア \\ ポリシー</span><span class="sxs-lookup"><span data-stu-id="ee39a-135">HKLM\\Software\\Policies</span></span>
- <span data-ttu-id="ee39a-136">HKLM \\ SOFTWARE \\ Policies \\ Microsoft \\ Cryptography \\ Configuration \\ SSL</span><span class="sxs-lookup"><span data-stu-id="ee39a-136">HKLM\\SOFTWARE\\Policies\\Microsoft\\Cryptography\\Configuration\\SSL</span></span>
- <span data-ttu-id="ee39a-137">HKLM \\ ソフトウェア ポリシー Microsoft Windows Advanced Threat \\ \\ \\ Protection</span><span class="sxs-lookup"><span data-stu-id="ee39a-137">HKLM\\SOFTWARE\\Policies\\Microsoft\\Windows Advanced Threat Protection</span></span>
- <span data-ttu-id="ee39a-138">HKLM \\ SOFTWARE \\ WOW6432Node \\ Microsoft \\ Windows \\ CurrentVersion \\ Uninstall</span><span class="sxs-lookup"><span data-stu-id="ee39a-138">HKLM\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall</span></span>
- <span data-ttu-id="ee39a-139">HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL</span><span class="sxs-lookup"><span data-stu-id="ee39a-139">HKLM\\SYSTEM\\CurrentControlSet\\Control\\SecurityProviders\\SCHANNEL</span></span>

### <a name="commands"></a><span data-ttu-id="ee39a-140">コマンド</span><span class="sxs-lookup"><span data-stu-id="ee39a-140">Commands</span></span>

- <span data-ttu-id="ee39a-141">%programfiles% \\ windows defendermpcmdrun.exe \\ -GetFiles</span><span class="sxs-lookup"><span data-stu-id="ee39a-141">%programfiles%\\windows defender\\mpcmdrun.exe -GetFiles</span></span>
- <span data-ttu-id="ee39a-142">%windir% \\ system32 \\certutil.exe -store</span><span class="sxs-lookup"><span data-stu-id="ee39a-142">%windir%\\system32\\certutil.exe -store</span></span>
- <span data-ttu-id="ee39a-143">%windir% \\ system32 \\certutil.exe -store -user my</span><span class="sxs-lookup"><span data-stu-id="ee39a-143">%windir%\\system32\\certutil.exe -store -user my</span></span>
- <span data-ttu-id="ee39a-144">%windir% \\ system32 \\Dsregcmd.exe /status</span><span class="sxs-lookup"><span data-stu-id="ee39a-144">%windir%\\system32\\Dsregcmd.exe /status</span></span>
- <span data-ttu-id="ee39a-145">%windir% \\ system32 \\ipconfig.exe /all</span><span class="sxs-lookup"><span data-stu-id="ee39a-145">%windir%\\system32\\ipconfig.exe /all</span></span>
- <span data-ttu-id="ee39a-146">%windir% \\ system32 \\ipconfig.exe/displaydns</span><span class="sxs-lookup"><span data-stu-id="ee39a-146">%windir%\\system32\\ipconfig.exe /displaydns</span></span>
- <span data-ttu-id="ee39a-147">%windir% \\ system32 \\mdmdiagnosticstool.exe</span><span class="sxs-lookup"><span data-stu-id="ee39a-147">%windir%\\system32\\mdmdiagnosticstool.exe</span></span>
- <span data-ttu-id="ee39a-148">%windir% \\ system32msinfo32.exe \\ /report %temp% \\ MDMDiagnostics \\ msinfo32.log</span><span class="sxs-lookup"><span data-stu-id="ee39a-148">%windir%\\system32\\msinfo32.exe /report %temp%\\MDMDiagnostics\\msinfo32.log</span></span>
- <span data-ttu-id="ee39a-149">%windir% \\ system32 \\netsh.exe advfirewall show allprofiles</span><span class="sxs-lookup"><span data-stu-id="ee39a-149">%windir%\\system32\\netsh.exe advfirewall show allprofiles</span></span>
- <span data-ttu-id="ee39a-150">%windir% \\ system32netsh.exe \\ advfirewall show global</span><span class="sxs-lookup"><span data-stu-id="ee39a-150">%windir%\\system32\\netsh.exe advfirewall show global</span></span>
- <span data-ttu-id="ee39a-151">%windir% \\ system32 \\netsh.exe LAN ショー プロファイル</span><span class="sxs-lookup"><span data-stu-id="ee39a-151">%windir%\\system32\\netsh.exe lan show profiles</span></span>
- <span data-ttu-id="ee39a-152">%windir% \\ system32 \\netsh.exe winhttp show proxy</span><span class="sxs-lookup"><span data-stu-id="ee39a-152">%windir%\\system32\\netsh.exe winhttp show proxy</span></span>
- <span data-ttu-id="ee39a-153">%windir% \\ system32 \\netsh.exe wlan show profiles</span><span class="sxs-lookup"><span data-stu-id="ee39a-153">%windir%\\system32\\netsh.exe wlan show profiles</span></span>
- <span data-ttu-id="ee39a-154">%windir% \\ system32 \\netsh.exe wlan show wlanreport</span><span class="sxs-lookup"><span data-stu-id="ee39a-154">%windir%\\system32\\netsh.exe wlan show wlanreport</span></span>
- <span data-ttu-id="ee39a-155">%windir% \\ system32 \\ping.exe -n 50 localhost</span><span class="sxs-lookup"><span data-stu-id="ee39a-155">%windir%\\system32\\ping.exe -n 50 localhost</span></span>
- <span data-ttu-id="ee39a-156">%windir% \\ system32powercfg.exe \\ /batteryreport /output %temp% \\ MDMDiagnosticsbattery-report.htm\\ l</span><span class="sxs-lookup"><span data-stu-id="ee39a-156">%windir%\\system32\\powercfg.exe /batteryreport /output %temp%\\MDMDiagnostics\\battery-report.html</span></span>
- <span data-ttu-id="ee39a-157">%windir% \\ system32powercfg.exe \\ /energy/output %temp% \\ MDMDiagnosticsenergy-report.htm\\ l</span><span class="sxs-lookup"><span data-stu-id="ee39a-157">%windir%\\system32\\powercfg.exe /energy /output %temp%\\MDMDiagnostics\\energy-report.html</span></span>
- <span data-ttu-id="ee39a-158">bitsadmin /list /allusers /verbose</span><span class="sxs-lookup"><span data-stu-id="ee39a-158">bitsadmin /list /allusers /verbose</span></span>
- <span data-ttu-id="ee39a-159">fltMC.exe</span><span class="sxs-lookup"><span data-stu-id="ee39a-159">fltMC.exe</span></span>
- <span data-ttu-id="ee39a-160">bcdedit /enum all /v</span><span class="sxs-lookup"><span data-stu-id="ee39a-160">bcdedit /enum all /v</span></span>
- <span data-ttu-id="ee39a-161">manage-bde -protectors -get</span><span class="sxs-lookup"><span data-stu-id="ee39a-161">manage-bde -protectors -get</span></span>
- <span data-ttu-id="ee39a-162">Windows PowerShellコマンド:</span><span class="sxs-lookup"><span data-stu-id="ee39a-162">Windows PowerShell commands:</span></span>
    - <span data-ttu-id="ee39a-163">Get-appxpackage -allusers</span><span class="sxs-lookup"><span data-stu-id="ee39a-163">Get-appxpackage -allusers</span></span>
    - <span data-ttu-id="ee39a-164">Get-appxpackage -packagetype バンドル</span><span class="sxs-lookup"><span data-stu-id="ee39a-164">Get-appxpackage -packagetype bundle</span></span>
    - <span data-ttu-id="ee39a-165">Get-Service wuauserv</span><span class="sxs-lookup"><span data-stu-id="ee39a-165">Get-Service wuauserv</span></span>
    - <span data-ttu-id="ee39a-166">Get-NetFirewallRule</span><span class="sxs-lookup"><span data-stu-id="ee39a-166">Get-NetFirewallRule</span></span>
    - <span data-ttu-id="ee39a-167">Get-WmiObject -Class win32 \_ 製品</span><span class="sxs-lookup"><span data-stu-id="ee39a-167">Get-WmiObject -Class win32\_product</span></span>
    - <span data-ttu-id="ee39a-168">Get-ComputerInfo</span><span class="sxs-lookup"><span data-stu-id="ee39a-168">Get-ComputerInfo</span></span>
    - <span data-ttu-id="ee39a-169">Get-Service</span><span class="sxs-lookup"><span data-stu-id="ee39a-169">Get-Service</span></span>
    - <span data-ttu-id="ee39a-170">Get-Process</span><span class="sxs-lookup"><span data-stu-id="ee39a-170">Get-Process</span></span>
    - <span data-ttu-id="ee39a-171">Get-WmiObject Win32 \_ PnPSignedDriver</span><span class="sxs-lookup"><span data-stu-id="ee39a-171">Get-WmiObject Win32\_PnPSignedDriver</span></span>

### <a name="event-logs"></a><span data-ttu-id="ee39a-172">イベント ログ</span><span class="sxs-lookup"><span data-stu-id="ee39a-172">Event logs</span></span>

- <span data-ttu-id="ee39a-173">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="ee39a-173">Application</span></span>
- <span data-ttu-id="ee39a-174">Microsoft-Windows-AppLocker/EXE および DLL</span><span class="sxs-lookup"><span data-stu-id="ee39a-174">Microsoft-Windows-AppLocker/EXE and DLL</span></span>
- <span data-ttu-id="ee39a-175">Microsoft-Windows-AppLocker/MSI とスクリプト</span><span class="sxs-lookup"><span data-stu-id="ee39a-175">Microsoft-Windows-AppLocker/MSI and Script</span></span>
- <span data-ttu-id="ee39a-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span><span class="sxs-lookup"><span data-stu-id="ee39a-176">Microsoft-Windows-AppLocker/Packaged app-Deployment</span></span>
- <span data-ttu-id="ee39a-177">Microsoft-Windows-AppLocker/Packaged app-Execution</span><span class="sxs-lookup"><span data-stu-id="ee39a-177">Microsoft-Windows-AppLocker/Packaged app-Execution</span></span>
- <span data-ttu-id="ee39a-178">Microsoft-Windows-Bitlocker/Bitlocker 管理</span><span class="sxs-lookup"><span data-stu-id="ee39a-178">Microsoft-Windows-Bitlocker/Bitlocker Management</span></span>
- <span data-ttu-id="ee39a-179">Microsoft-Windows-SENSE/Operational</span><span class="sxs-lookup"><span data-stu-id="ee39a-179">Microsoft-Windows-SENSE/Operational</span></span>
- <span data-ttu-id="ee39a-180">Microsoft-Windows-SenseIR/Operational</span><span class="sxs-lookup"><span data-stu-id="ee39a-180">Microsoft-Windows-SenseIR/Operational</span></span>
- <span data-ttu-id="ee39a-181">セットアップ</span><span class="sxs-lookup"><span data-stu-id="ee39a-181">Setup</span></span>
- <span data-ttu-id="ee39a-182">System</span><span class="sxs-lookup"><span data-stu-id="ee39a-182">System</span></span>

### <a name="files"></a><span data-ttu-id="ee39a-183">ファイル</span><span class="sxs-lookup"><span data-stu-id="ee39a-183">Files</span></span>

- <span data-ttu-id="ee39a-184">%ProgramData% \\ Microsoft \\ DiagnosticLogCSP \\ コレクター \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="ee39a-184">%ProgramData%\\Microsoft\\DiagnosticLogCSP\\Collectors\\\*.etl</span></span>
- <span data-ttu-id="ee39a-185">%ProgramData% \\ \\ Microsoft IntuneManagementExtension \\ Logs \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="ee39a-185">%ProgramData%\\Microsoft\\IntuneManagementExtension\\Logs\\\*.\*</span></span>
- <span data-ttu-id="ee39a-186">%ProgramData% \\ Microsoft Windows Defender サポート \\ \\ \\MpSupportFiles.cab</span><span class="sxs-lookup"><span data-stu-id="ee39a-186">%ProgramData%\\Microsoft\\Windows Defender\\Support\\MpSupportFiles.cab</span></span>
- <span data-ttu-id="ee39a-187">%ProgramData% \\ \\ Microsoft Windows \\ WlanReport \\wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="ee39a-187">%ProgramData%\\Microsoft\\Windows\\WlanReport\\wlan-report-latest.html</span></span>
- <span data-ttu-id="ee39a-188">%ProgramData% \\ \\ Microsoft Windows \\ WlanReport -SourceFileName wlan-report-latest.html</span><span class="sxs-lookup"><span data-stu-id="ee39a-188">%ProgramData%\\Microsoft\\Windows\\WlanReport -SourceFileName wlan-report-latest.html</span></span>
- <span data-ttu-id="ee39a-189">%windir% \\ ccm \\ ログ \* .log</span><span class="sxs-lookup"><span data-stu-id="ee39a-189">%windir%\\ccm\\logs\*.log</span></span>
- <span data-ttu-id="ee39a-190">%windir% \\ ccmsetup \\ ログ \* .log</span><span class="sxs-lookup"><span data-stu-id="ee39a-190">%windir%\\ccmsetup\\logs\*.log</span></span>
- <span data-ttu-id="ee39a-191">%windir% \\ ログ \\ CBS \\ cbs.log</span><span class="sxs-lookup"><span data-stu-id="ee39a-191">%windir%\\logs\\CBS\\cbs.log</span></span>
- <span data-ttu-id="ee39a-192">%windir% \\ logs \\ measuredboot \* .\*</span><span class="sxs-lookup"><span data-stu-id="ee39a-192">%windir%\\logs\\measuredboot\*.\*</span></span>
- <span data-ttu-id="ee39a-193">%windir% \\ Logs \\ WindowsUpdate \* .etl</span><span class="sxs-lookup"><span data-stu-id="ee39a-193">%windir%\\Logs\\WindowsUpdate\*.etl</span></span>
- <span data-ttu-id="ee39a-194">%windir% \\ inf \\ \* .log</span><span class="sxs-lookup"><span data-stu-id="ee39a-194">%windir%\\inf\\\*.log</span></span>
- <span data-ttu-id="ee39a-195">%windir% \\ サービス \\ \\ セッションActionList.xml</span><span class="sxs-lookup"><span data-stu-id="ee39a-195">%windir%\\servicing\\sessions\\ActionList.xml</span></span>
- <span data-ttu-id="ee39a-196">%windir% \\ サービス \\ \\ セッションSessions.xml</span><span class="sxs-lookup"><span data-stu-id="ee39a-196">%windir%\\servicing\\sessions\\Sessions.xml</span></span>
- <span data-ttu-id="ee39a-197">%windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log</span><span class="sxs-lookup"><span data-stu-id="ee39a-197">%windir%\\SoftwareDistribution\\DataStore\\Logs\\edb.log</span></span>
- <span data-ttu-id="ee39a-198">%windir% \\ SoftwareDistribution \\ DataStore \\ DataStore.edb</span><span class="sxs-lookup"><span data-stu-id="ee39a-198">%windir%\\SoftwareDistribution\\DataStore\\DataStore.edb</span></span>
- <span data-ttu-id="ee39a-199">%windir% \\ ログ \\ \\ dism dism.log</span><span class="sxs-lookup"><span data-stu-id="ee39a-199">%windir%\\logs\\dism\\dism.log</span></span>
- <span data-ttu-id="ee39a-200">%SystemRoot% \\ System32 \\ Winevt \\ ログ</span><span class="sxs-lookup"><span data-stu-id="ee39a-200">%SystemRoot%\\System32\\Winevt\\Logs</span></span>\\
- <span data-ttu-id="ee39a-201">%appdata% \\ Microsoft Teams メディア スタック \\ \\ \\ \* .blog</span><span class="sxs-lookup"><span data-stu-id="ee39a-201">%appdata%\\Microsoft\\Teams\\media-stack\\\*.blog</span></span>
- <span data-ttu-id="ee39a-202">%appdata% \\ Microsoft \\ Teams \\ skylib \\ \* .blog</span><span class="sxs-lookup"><span data-stu-id="ee39a-202">%appdata%\\Microsoft\\Teams\\skylib\\\*.blog</span></span>
- <span data-ttu-id="ee39a-203">%appdata% \\ Microsoft Teams メディア スタック \\ \\ \\ \* .etl</span><span class="sxs-lookup"><span data-stu-id="ee39a-203">%appdata%\\Microsoft\\Teams\\media-stack\\\*.etl</span></span>
- <span data-ttu-id="ee39a-204">%appdata% \\ Microsoft \\ Teams \\logs.txt</span><span class="sxs-lookup"><span data-stu-id="ee39a-204">%appdata%\\Microsoft\\Teams\\logs.txt</span></span>
- <span data-ttu-id="ee39a-205">%windir% \\ Windows \\ System32 \\ winevt \\ \* .\*</span><span class="sxs-lookup"><span data-stu-id="ee39a-205">%windir%\\Windows\\System32\\winevt\\\*.\*</span></span>