---
title: サーバー Microsoft Defender ウイルス対策の除外をWindowsする
ms.reviewer: ''
manager: dansimp
description: Windowsサーバーには、サーバーの役割に基づく自動除外が含まれます。 カスタム除外を追加できます。
keywords: 除外、サーバー、自動除外、自動、カスタム、スキャン、Microsoft Defender ウイルス対策
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 02/10/2021
ms.openlocfilehash: 31d5c22d11a28c9604b2be3145ebd46715a6e5b3
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925517"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a><span data-ttu-id="3487a-105">サーバー Microsoft Defender ウイルス対策の除外をWindowsする</span><span class="sxs-lookup"><span data-stu-id="3487a-105">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>


<span data-ttu-id="3487a-106">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3487a-106">**Applies to:**</span></span>

- [<span data-ttu-id="3487a-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3487a-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="3487a-108">Microsoft Defender ウイルス対策サーバー 2019 Windows Server 2016および Windowsサーバー 2019 では、指定したサーバーの役割で定義されている特定の除外に自動的に登録されます。</span><span class="sxs-lookup"><span data-stu-id="3487a-108">Microsoft Defender Antivirus on Windows Server 2016 and Windows Server 2019 automatically enrolls you in certain exclusions, as defined by your specified server role.</span></span> <span data-ttu-id="3487a-109">これらの除外は、アプリに表示される標準の除外リスト[にはWindows セキュリティされません](microsoft-defender-security-center-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="3487a-109">These exclusions do not appear in the standard exclusion lists that are shown in the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3487a-110">自動除外は、リアルタイム保護 (RTP) スキャンにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3487a-110">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="3487a-111">フル/クイック スキャンまたはオンデマンド スキャンでは、自動除外は適用されません。</span><span class="sxs-lookup"><span data-stu-id="3487a-111">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>

<span data-ttu-id="3487a-112">サーバーの役割定義の自動除外に加えて、カスタム除外を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="3487a-112">In addition to server role-defined automatic exclusions, you can add or remove custom exclusions.</span></span> <span data-ttu-id="3487a-113">これを行うには、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3487a-113">To do that, refer to these articles:</span></span>
- [<span data-ttu-id="3487a-114">ファイル名、拡張子、フォルダーの場所に基づいて除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="3487a-114">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3487a-115">プロセスによって開いたファイルの除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="3487a-115">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="a-few-points-to-keep-in-mind"></a><span data-ttu-id="3487a-116">いくつかの点に気を付ける必要があります</span><span class="sxs-lookup"><span data-stu-id="3487a-116">A few points to keep in mind</span></span>

<span data-ttu-id="3487a-117">次の重要な点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="3487a-117">Keep the following important points in mind:</span></span>

- <span data-ttu-id="3487a-118">カスタム除外は、自動除外よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="3487a-118">Custom exclusions take precedence over automatic exclusions.</span></span>
- <span data-ttu-id="3487a-119">自動除外は、リアルタイム保護 (RTP) スキャンにのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="3487a-119">Automatic exclusions only apply to Real-time protection (RTP) scanning.</span></span> <span data-ttu-id="3487a-120">フル/クイック スキャンまたはオンデマンド スキャンでは、自動除外は適用されません。</span><span class="sxs-lookup"><span data-stu-id="3487a-120">Automatic exclusions are not honored during a Full/Quick or On-demand scan.</span></span>
- <span data-ttu-id="3487a-121">カスタム除外と重複除外は、自動除外と競合しない。</span><span class="sxs-lookup"><span data-stu-id="3487a-121">Custom and duplicate exclusions do not conflict with automatic exclusions.</span></span>
- <span data-ttu-id="3487a-122">Microsoft Defender ウイルス対策展開イメージのサービスと管理 (DISM) ツールを使用して、コンピューターにインストールされている役割を特定します。</span><span class="sxs-lookup"><span data-stu-id="3487a-122">Microsoft Defender Antivirus uses the Deployment Image Servicing and Management (DISM) tools to determine which roles are installed on your computer.</span></span>

## <a name="opt-out-of-automatic-exclusions"></a><span data-ttu-id="3487a-123">自動除外をオプトアウトする</span><span class="sxs-lookup"><span data-stu-id="3487a-123">Opt out of automatic exclusions</span></span>

<span data-ttu-id="3487a-124">サーバー 2019 Windows Server 2016および Windowsでは、セキュリティ インテリジェンス更新プログラムによって提供される定義済みの除外は、役割または機能の既定のパスのみを除外します。</span><span class="sxs-lookup"><span data-stu-id="3487a-124">In Windows Server 2016 and Windows Server 2019, the predefined exclusions delivered by Security intelligence updates only exclude the default paths for a role or feature.</span></span> <span data-ttu-id="3487a-125">カスタム パスに役割または機能をインストールした場合、または一連の除外を手動で制御する場合は、セキュリティ インテリジェンス更新プログラムで配信される自動除外をオプトアウトしてください。</span><span class="sxs-lookup"><span data-stu-id="3487a-125">If you installed a role or feature in a custom path, or you want to manually control the set of exclusions, make sure to opt out of the automatic exclusions delivered in Security intelligence updates.</span></span> <span data-ttu-id="3487a-126">ただし、自動的に配信される除外は、2019 年と 2019 年Windows Server 2016に最適化されています。</span><span class="sxs-lookup"><span data-stu-id="3487a-126">But keep in mind that the exclusions that are delivered automatically are optimized for Windows Server 2016 and 2019 roles.</span></span> <span data-ttu-id="3487a-127">除外 [リストを定義する前に、「除外を](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 定義するための推奨事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3487a-127">See [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) before defining your exclusion lists.</span></span>

> [!WARNING]
> <span data-ttu-id="3487a-128">自動除外をオプトアウトすると、パフォーマンスに悪影響を及ぼすか、データが破損する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3487a-128">Opting out of automatic exclusions may adversely impact performance, or result in data corruption.</span></span> <span data-ttu-id="3487a-129">自動的に配信される除外は、サーバー 2019 Windows Server 2016およびWindowsに最適化されます。</span><span class="sxs-lookup"><span data-stu-id="3487a-129">The exclusions that are delivered automatically are optimized for Windows Server 2016 and Windows Server 2019 roles.</span></span>

<span data-ttu-id="3487a-130">定義済みの除外は既定のパスのみを除外しますので、NTDS と SYSVOL を元のパスとは異なる別のドライブまたはパスに移動する場合は、ここでの情報[](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension)を使用して手動で除外を追加する必要があります。 </span><span class="sxs-lookup"><span data-stu-id="3487a-130">Because predefined exclusions only exclude **default paths**, if you move NTDS and SYSVOL to another drive or path that is *different from the original path*, you must add exclusions manually using the information [here](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension) .</span></span>

<span data-ttu-id="3487a-131">グループ ポリシー、PowerShell コマンドレット、および WMI を使用して、自動除外リストを無効にできます。</span><span class="sxs-lookup"><span data-stu-id="3487a-131">You can disable the automatic exclusion lists with Group Policy, PowerShell cmdlets, and WMI.</span></span>

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="3487a-132">グループ ポリシーを使用して、サーバー 2019 およびサーバー 2019 のWindows Server 2016 Windows無効にする</span><span class="sxs-lookup"><span data-stu-id="3487a-132">Use Group Policy to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

1. <span data-ttu-id="3487a-133">グループ ポリシー管理コンピューターで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11))を開きます。</span><span class="sxs-lookup"><span data-stu-id="3487a-133">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11)).</span></span> <span data-ttu-id="3487a-134">構成するグループ ポリシー オブジェクトを右クリックし、[編集] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="3487a-134">Right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>
2. <span data-ttu-id="3487a-135">グループ ポリシー **管理エディターで 、[** コンピューターの構成] **に移動し**、[管理用テンプレート] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="3487a-135">In the **Group Policy Management Editor** go to **Computer configuration**, and then click **Administrative templates**.</span></span>
3. <span data-ttu-id="3487a-136">ツリーを展開して、[**除外Windowsコンポーネント**  >  **Microsoft Defender ウイルス対策**  >  **展開します**。</span><span class="sxs-lookup"><span data-stu-id="3487a-136">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Exclusions**.</span></span>
4. <span data-ttu-id="3487a-137">[自動除外を **オフにする] をダブルクリック** し、オプションを [有効] に **設定します**。</span><span class="sxs-lookup"><span data-stu-id="3487a-137">Double-click **Turn off Auto Exclusions**, and set the option to **Enabled**.</span></span> <span data-ttu-id="3487a-138">次に、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3487a-138">Then click **OK**.</span></span> 

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-2019"></a><span data-ttu-id="3487a-139">PowerShell コマンドレットを使用して、2019 年と 2019 年の自動除外リストWindows Server 2016無効にする</span><span class="sxs-lookup"><span data-stu-id="3487a-139">Use PowerShell cmdlets to disable the auto-exclusions list on Windows Server 2016 and 2019</span></span>

<span data-ttu-id="3487a-140">次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3487a-140">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

<span data-ttu-id="3487a-141">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3487a-141">To learn more, see the following resources:</span></span>

- <span data-ttu-id="3487a-142">[PowerShell コマンドレットを使用して、PowerShell コマンドレットを構成して実行Microsoft Defender ウイルス対策。](use-powershell-cmdlets-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="3487a-142">[Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md).</span></span>
- <span data-ttu-id="3487a-143">[PowerShell と一緒にMicrosoft Defender ウイルス対策。](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="3487a-143">[Use PowerShell with Microsoft Defender Antivirus](/powershell/module/defender/).</span></span>

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a><span data-ttu-id="3487a-144">サーバー Windowsサーバー 2019 の自動除外リストを無効にするには、Windows管理命令 (WMI Windows Server 2016) をWindowsします。</span><span class="sxs-lookup"><span data-stu-id="3487a-144">Use Windows Management Instruction (WMI) to disable the auto-exclusions list on Windows Server 2016 and Windows Server 2019</span></span>

<span data-ttu-id="3487a-145">次の **プロパティ** に対して [、MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) クラスの Set メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="3487a-145">Use the **Set** method of the [MSFT_MpPreference](/previous-versions/windows/desktop/defender/msft-mppreference) class for the following properties:</span></span>

```WMI
DisableAutoExclusions
```

<span data-ttu-id="3487a-146">詳細と許可されるパラメーターについては、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3487a-146">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="3487a-147">Windows DefenderWMIv2 API</span><span class="sxs-lookup"><span data-stu-id="3487a-147">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="list-of-automatic-exclusions"></a><span data-ttu-id="3487a-148">自動除外の一覧</span><span class="sxs-lookup"><span data-stu-id="3487a-148">List of automatic exclusions</span></span>

<span data-ttu-id="3487a-149">次のセクションでは、自動除外ファイル パスとファイルの種類で配信される除外について説明します。</span><span class="sxs-lookup"><span data-stu-id="3487a-149">The following sections contain the exclusions that are delivered with automatic exclusions file paths and file types.</span></span>

### <a name="default-exclusions-for-all-roles"></a><span data-ttu-id="3487a-150">すべての役割の既定の除外</span><span class="sxs-lookup"><span data-stu-id="3487a-150">Default exclusions for all roles</span></span>

<span data-ttu-id="3487a-151">このセクションでは、すべてのユーザーロールと 2019 Windows Server 2016の除外を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="3487a-151">This section lists the default exclusions for all Windows Server 2016 and 2019 roles.</span></span>

> [!NOTE]
> <span data-ttu-id="3487a-152">既定の場所は、この記事に記載されている場所とは異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3487a-152">The default locations could be different than what's listed in this article.</span></span>

#### <a name="windows-tempedb-files"></a><span data-ttu-id="3487a-153">Windows"temp.edb" ファイル</span><span class="sxs-lookup"><span data-stu-id="3487a-153">Windows "temp.edb" files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

#### <a name="windows-update-files-or-automatic-update-files"></a><span data-ttu-id="3487a-154">Windowsファイルの更新または自動更新ファイル</span><span class="sxs-lookup"><span data-stu-id="3487a-154">Windows Update files or Automatic Update files</span></span>

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

#### <a name="windows-security-files"></a><span data-ttu-id="3487a-155">Windows セキュリティファイル</span><span class="sxs-lookup"><span data-stu-id="3487a-155">Windows Security files</span></span>

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

#### <a name="group-policy-files"></a><span data-ttu-id="3487a-156">グループ ポリシー ファイル</span><span class="sxs-lookup"><span data-stu-id="3487a-156">Group Policy files</span></span>

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

#### <a name="wins-files"></a><span data-ttu-id="3487a-157">WINS ファイル</span><span class="sxs-lookup"><span data-stu-id="3487a-157">WINS files</span></span>

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

#### <a name="file-replication-service-frs-exclusions"></a><span data-ttu-id="3487a-158">ファイル レプリケーション サービス (FRS) の除外</span><span class="sxs-lookup"><span data-stu-id="3487a-158">File Replication Service (FRS) exclusions</span></span>

- <span data-ttu-id="3487a-159">ファイル レプリケーション サービス (FRS) 作業フォルダー内のファイル。</span><span class="sxs-lookup"><span data-stu-id="3487a-159">Files in the File Replication Service (FRS) working folder.</span></span> <span data-ttu-id="3487a-160">FRS 作業フォルダーがレジストリ キーで指定されている `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span><span class="sxs-lookup"><span data-stu-id="3487a-160">The FRS working folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`</span></span>

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- <span data-ttu-id="3487a-161">FRS データベース ログ ファイル。</span><span class="sxs-lookup"><span data-stu-id="3487a-161">FRS Database log files.</span></span> <span data-ttu-id="3487a-162">FRS データベース ログ ファイル フォルダーがレジストリ キーで指定されている `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span><span class="sxs-lookup"><span data-stu-id="3487a-162">The FRS Database log file folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`</span></span>

  - `%windir%\Ntfrs\*\Edb\*.log`

- <span data-ttu-id="3487a-163">FRS ステージング フォルダー。</span><span class="sxs-lookup"><span data-stu-id="3487a-163">The FRS staging folder.</span></span> <span data-ttu-id="3487a-164">ステージング フォルダーがレジストリ キーで指定されている `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span><span class="sxs-lookup"><span data-stu-id="3487a-164">The staging folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`</span></span>

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- <span data-ttu-id="3487a-165">FRS プレインストール フォルダー。</span><span class="sxs-lookup"><span data-stu-id="3487a-165">The FRS preinstall folder.</span></span> <span data-ttu-id="3487a-166">このフォルダーは、フォルダーによって指定されます。 `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span><span class="sxs-lookup"><span data-stu-id="3487a-166">This folder is specified by the folder `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`</span></span>

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- <span data-ttu-id="3487a-167">分散ファイル システム レプリケーション (DFSR) データベースと作業フォルダー。</span><span class="sxs-lookup"><span data-stu-id="3487a-167">The Distributed File System Replication (DFSR) database and working folders.</span></span> <span data-ttu-id="3487a-168">これらのフォルダーは、レジストリ キーによって指定されます。 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span><span class="sxs-lookup"><span data-stu-id="3487a-168">These folders are specified by the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`</span></span>

  > [!NOTE]
  > <span data-ttu-id="3487a-169">カスタムの場所については、「自動除外 [をオプトアウトする」を参照してください](#opt-out-of-automatic-exclusions)。</span><span class="sxs-lookup"><span data-stu-id="3487a-169">For custom locations, see [Opt out of automatic exclusions](#opt-out-of-automatic-exclusions).</span></span>

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

#### <a name="process-exclusions"></a><span data-ttu-id="3487a-170">プロセスの除外</span><span class="sxs-lookup"><span data-stu-id="3487a-170">Process exclusions</span></span>

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

#### <a name="hyper-v-exclusions"></a><span data-ttu-id="3487a-171">Hyper-V の除外</span><span class="sxs-lookup"><span data-stu-id="3487a-171">Hyper-V exclusions</span></span>

<span data-ttu-id="3487a-172">次の表に、Hyper-V の役割をインストールするときに自動的に配信されるファイルの種類の除外、フォルダーの除外、およびプロセスの除外の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3487a-172">The following table lists the file type exclusions, folder exclusions, and process exclusions that are delivered automatically when you install the Hyper-V role.</span></span>

|<span data-ttu-id="3487a-173">ファイルの種類の除外</span><span class="sxs-lookup"><span data-stu-id="3487a-173">File type exclusions</span></span> |<span data-ttu-id="3487a-174">フォルダーの除外</span><span class="sxs-lookup"><span data-stu-id="3487a-174">Folder exclusions</span></span>  | <span data-ttu-id="3487a-175">Process exclusions</span><span class="sxs-lookup"><span data-stu-id="3487a-175">Process exclusions</span></span> |
|:--|:--|:--|
| `*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs` | `%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks` | `%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe` |

#### <a name="sysvol-files"></a><span data-ttu-id="3487a-176">SYSVOL ファイル</span><span class="sxs-lookup"><span data-stu-id="3487a-176">SYSVOL files</span></span>

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


### <a name="active-directory-exclusions"></a><span data-ttu-id="3487a-177">Active Directory の除外</span><span class="sxs-lookup"><span data-stu-id="3487a-177">Active Directory exclusions</span></span>

<span data-ttu-id="3487a-178">このセクションでは、Active Directory ドメイン サービスをインストールするときに自動的に配信される除外の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3487a-178">This section lists the exclusions that are delivered automatically when you install Active Directory Domain Services.</span></span>

#### <a name="ntds-database-files"></a><span data-ttu-id="3487a-179">NTDS データベース ファイル</span><span class="sxs-lookup"><span data-stu-id="3487a-179">NTDS database files</span></span>

<span data-ttu-id="3487a-180">データベース ファイルはレジストリ キーで指定されます。 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span><span class="sxs-lookup"><span data-stu-id="3487a-180">The database files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`</span></span>

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

#### <a name="the-ad-ds-transaction-log-files"></a><span data-ttu-id="3487a-181">DS ADログ ファイル</span><span class="sxs-lookup"><span data-stu-id="3487a-181">The AD DS transaction log files</span></span>

<span data-ttu-id="3487a-182">トランザクション ログ ファイルはレジストリ キーで指定されます。 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span><span class="sxs-lookup"><span data-stu-id="3487a-182">The transaction log files are specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`</span></span>

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

#### <a name="the-ntds-working-folder"></a><span data-ttu-id="3487a-183">NTDS 作業フォルダー</span><span class="sxs-lookup"><span data-stu-id="3487a-183">The NTDS working folder</span></span>

<span data-ttu-id="3487a-184">このフォルダーはレジストリ キーで指定されます。 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span><span class="sxs-lookup"><span data-stu-id="3487a-184">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`</span></span>

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

#### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a><span data-ttu-id="3487a-185">DS および DS 関連のADファイルAD除外を処理する</span><span class="sxs-lookup"><span data-stu-id="3487a-185">Process exclusions for AD DS and AD DS-related support files</span></span>

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

### <a name="dhcp-server-exclusions"></a><span data-ttu-id="3487a-186">DHCP サーバーの除外</span><span class="sxs-lookup"><span data-stu-id="3487a-186">DHCP Server exclusions</span></span>

<span data-ttu-id="3487a-187">このセクションでは、DHCP Server の役割をインストールするときに自動的に配信される除外の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3487a-187">This section lists the exclusions that are delivered automatically when you install the DHCP Server role.</span></span> <span data-ttu-id="3487a-188">DHCP Server ファイルの場所は、レジストリ キーの *DatabasePath、DhcpLogFilePath、\*\*および BackupDatabasePath* パラメーターによって指定されます。 `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span><span class="sxs-lookup"><span data-stu-id="3487a-188">The DHCP Server file locations are specified by the *DatabasePath*, *DhcpLogFilePath*, and *BackupDatabasePath* parameters in the registry key `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`</span></span>

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

### <a name="dns-server-exclusions"></a><span data-ttu-id="3487a-189">DNS サーバーの除外</span><span class="sxs-lookup"><span data-stu-id="3487a-189">DNS Server exclusions</span></span>

<span data-ttu-id="3487a-190">このセクションでは、DNS Server の役割をインストールするときに自動的に配信されるファイルとフォルダーの除外とプロセスの除外の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3487a-190">This section lists the file and folder exclusions and the process exclusions that are delivered automatically when you install the DNS Server role.</span></span>

#### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a><span data-ttu-id="3487a-191">DNS Server の役割のファイルとフォルダーの除外</span><span class="sxs-lookup"><span data-stu-id="3487a-191">File and folder exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

#### <a name="process-exclusions-for-the-dns-server-role"></a><span data-ttu-id="3487a-192">DNS Server の役割の除外を処理する</span><span class="sxs-lookup"><span data-stu-id="3487a-192">Process exclusions for the DNS Server role</span></span>

- `%systemroot%\System32\dns.exe`

### <a name="file-and-storage-services-exclusions"></a><span data-ttu-id="3487a-193">ファイルとStorageサービスの除外</span><span class="sxs-lookup"><span data-stu-id="3487a-193">File and Storage Services exclusions</span></span>

<span data-ttu-id="3487a-194">このセクションでは、File および Storage サービスの役割をインストールするときに自動的に配信されるファイルとフォルダーの除外の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3487a-194">This section lists the file and folder exclusions that are delivered automatically when you install the File and Storage Services role.</span></span> <span data-ttu-id="3487a-195">以下に示す除外には、クラスター化の役割の除外は含めされません。</span><span class="sxs-lookup"><span data-stu-id="3487a-195">The exclusions listed below do not include exclusions for the Clustering role.</span></span>

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

### <a name="print-server-exclusions"></a><span data-ttu-id="3487a-196">サーバーの除外を印刷する</span><span class="sxs-lookup"><span data-stu-id="3487a-196">Print Server exclusions</span></span>

<span data-ttu-id="3487a-197">このセクションでは、Print Server の役割をインストールするときに自動的に配信されるファイルの種類の除外、フォルダーの除外、およびプロセスの除外を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="3487a-197">This section lists the file type exclusions, folder exclusions, and the process exclusions that are delivered automatically when you install the Print Server role.</span></span>

#### <a name="file-type-exclusions"></a><span data-ttu-id="3487a-198">ファイルの種類の除外</span><span class="sxs-lookup"><span data-stu-id="3487a-198">File type exclusions</span></span>

- `*.shd`
- `*.spl`

#### <a name="folder-exclusions"></a><span data-ttu-id="3487a-199">フォルダーの除外</span><span class="sxs-lookup"><span data-stu-id="3487a-199">Folder exclusions</span></span>

<span data-ttu-id="3487a-200">このフォルダーはレジストリ キーで指定されます。 `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span><span class="sxs-lookup"><span data-stu-id="3487a-200">This folder is specified in the registry key `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`</span></span>

- `%system32%\spool\printers\*`

#### <a name="process-exclusions"></a><span data-ttu-id="3487a-201">プロセスの除外</span><span class="sxs-lookup"><span data-stu-id="3487a-201">Process exclusions</span></span>

- `spoolsv.exe`

### <a name="web-server-exclusions"></a><span data-ttu-id="3487a-202">Web サーバーの除外</span><span class="sxs-lookup"><span data-stu-id="3487a-202">Web Server exclusions</span></span>

<span data-ttu-id="3487a-203">このセクションでは、Web Server の役割をインストールするときに自動的に配信されるフォルダーの除外とプロセスの除外の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3487a-203">This section lists the folder exclusions and the process exclusions that are delivered automatically when you install the Web Server role.</span></span>

#### <a name="folder-exclusions"></a><span data-ttu-id="3487a-204">フォルダーの除外</span><span class="sxs-lookup"><span data-stu-id="3487a-204">Folder exclusions</span></span>

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

#### <a name="process-exclusions"></a><span data-ttu-id="3487a-205">Process exclusions</span><span class="sxs-lookup"><span data-stu-id="3487a-205">Process exclusions</span></span>

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

#### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a><span data-ttu-id="3487a-206">Sysvol\Sysvol フォルダーまたは sysvol フォルダー内のファイルのスキャンをオフSYSVOL_DFSR\Sysvol フォルダー</span><span class="sxs-lookup"><span data-stu-id="3487a-206">Turning off scanning of files in the Sysvol\Sysvol folder or the SYSVOL_DFSR\Sysvol folder</span></span>

<span data-ttu-id="3487a-207">or フォルダーとすべてのサブフォルダーの現在の場所は、レプリカ セット ルートのファイル システムの再 `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` 解析ターゲットです。</span><span class="sxs-lookup"><span data-stu-id="3487a-207">The current location of the `Sysvol\Sysvol` or `SYSVOL_DFSR\Sysvol` folder and all the subfolders is the file system reparse target of the replica set root.</span></span> <span data-ttu-id="3487a-208">フォルダー `Sysvol\Sysvol` は `SYSVOL_DFSR\Sysvol` 、既定で次の場所を使用します。</span><span class="sxs-lookup"><span data-stu-id="3487a-208">The `Sysvol\Sysvol` and `SYSVOL_DFSR\Sysvol` folders use the following locations by default:</span></span>

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

<span data-ttu-id="3487a-209">現在アクティブなパスは NETLOGON 共有によって参照され、次のサブキーの `SYSVOL` SysVol 値名によって決定できます。 `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span><span class="sxs-lookup"><span data-stu-id="3487a-209">The path to the currently active `SYSVOL` is referenced by the NETLOGON share and can be determined by the SysVol value name in the following subkey: `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`</span></span>

<span data-ttu-id="3487a-210">このフォルダーとそのすべてのサブフォルダーから次のファイルを除外します。</span><span class="sxs-lookup"><span data-stu-id="3487a-210">Exclude the following files from this folder and all its subfolders:</span></span>

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

### <a name="windows-server-update-services-exclusions"></a><span data-ttu-id="3487a-211">Windows Server Update Services除外</span><span class="sxs-lookup"><span data-stu-id="3487a-211">Windows Server Update Services exclusions</span></span>

<span data-ttu-id="3487a-212">このセクションでは、ユーザー (WSUS) の役割をインストールするときに自動的に配信されるフォルダー Windows Server Update Services一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="3487a-212">This section lists the folder exclusions that are delivered automatically when you install the Windows Server Update Services (WSUS) role.</span></span> <span data-ttu-id="3487a-213">WSUS フォルダーがレジストリ キーで指定されている `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span><span class="sxs-lookup"><span data-stu-id="3487a-213">The WSUS folder is specified in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`</span></span>

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="see-also"></a><span data-ttu-id="3487a-214">関連項目</span><span class="sxs-lookup"><span data-stu-id="3487a-214">See also</span></span>

- [<span data-ttu-id="3487a-215">スキャンの除外を構成およびMicrosoft Defender ウイルス対策する</span><span class="sxs-lookup"><span data-stu-id="3487a-215">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3487a-216">ファイル名、拡張子、フォルダーの場所に基づいて除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="3487a-216">Configure and validate exclusions based on file name, extension, and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3487a-217">プロセスによって開いたファイルの除外を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="3487a-217">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3487a-218">除外を定義する際に避ける必要のある一般的な間違い</span><span class="sxs-lookup"><span data-stu-id="3487a-218">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3487a-219">スキャンと修復の結果をカスタマイズ、開始Microsoft Defender ウイルス対策確認する</span><span class="sxs-lookup"><span data-stu-id="3487a-219">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="3487a-220">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="3487a-220">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
