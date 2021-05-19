---
title: コマンド ラインを使用して、コマンド ラインをMicrosoft Defender ウイルス対策
description: 専用Microsoft Defender ウイルス対策を使用して、スキャンを実行し、次世代の保護を構成します。
keywords: Windows Defender スキャンの実行、コマンド ラインからのウイルス対策スキャンの実行、コマンド ラインからの Windows Defender スキャンの実行、mpcmdrun、Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/17/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: eb7fa7fdf5b88bd9361176003817116bcbb1a087
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538905"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="56846-104">コマンド ライン Microsoft Defender ウイルス対策を使用してmpcmdrun.exeを構成および管理する</span><span class="sxs-lookup"><span data-stu-id="56846-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

<span data-ttu-id="56846-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="56846-105">**Applies to:**</span></span>

- [<span data-ttu-id="56846-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="56846-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="56846-107">専用のコマンド ライン Microsoft Defender ウイルス対策を使用して、さまざまな機能 **を実行** mpcmdrun.exe。</span><span class="sxs-lookup"><span data-stu-id="56846-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="56846-108">このユーティリティは、使用を自動化する場合にMicrosoft Defender ウイルス対策です。</span><span class="sxs-lookup"><span data-stu-id="56846-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="56846-109">ユーティリティは で確認できます `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。</span><span class="sxs-lookup"><span data-stu-id="56846-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="56846-110">コマンド プロンプトから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56846-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="56846-111">管理者レベルのバージョンのコマンド プロンプトを開く必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="56846-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="56846-112">[スタート] メニューの **[コマンド プロンプト]** を検索する場合は、[管理者として **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="56846-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="56846-113">更新された Microsoft Defender プラットフォーム バージョンを実行している場合は、次 `**MpCmdRun**` の場所から実行します `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` 。</span><span class="sxs-lookup"><span data-stu-id="56846-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>`.</span></span>
> <span data-ttu-id="56846-114">マルウェア対策プラットフォームの詳細については、「更新プログラムとベースラインMicrosoft Defender ウイルス対策[を参照してください](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="56846-114">For more information about the antimalware platform, see [Microsoft Defender Antivirus updates and baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="56846-115">MpCmdRun ユーティリティは、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="56846-115">The MpCmdRun utility uses the following syntax:</span></span>

```console
MpCmdRun.exe [command] [-options]
```

<span data-ttu-id="56846-116">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="56846-116">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="56846-117">コマンド</span><span class="sxs-lookup"><span data-stu-id="56846-117">Command</span></span>  | <span data-ttu-id="56846-118">説明</span><span class="sxs-lookup"><span data-stu-id="56846-118">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="56846-119">`-?` **または** `-h`</span><span class="sxs-lookup"><span data-stu-id="56846-119">`-?` **or** `-h`</span></span>   | <span data-ttu-id="56846-120">このツールで使用可能なすべてのオプションを表示する</span><span class="sxs-lookup"><span data-stu-id="56846-120">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="56846-121">悪意のあるソフトウェアをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="56846-121">Scans for malicious software.</span></span> <span data-ttu-id="56846-122">**ScanType の値は次** のとおりです。</span><span class="sxs-lookup"><span data-stu-id="56846-122">Values for **ScanType** are:</span></span><p><span data-ttu-id="56846-123">**0** 構成に応じて既定</span><span class="sxs-lookup"><span data-stu-id="56846-123">**0** Default, according to your configuration</span></span><p><span data-ttu-id="56846-124">**-1** クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="56846-124">**-1** Quick scan</span></span><p><span data-ttu-id="56846-125">**-2** フル スキャン</span><span class="sxs-lookup"><span data-stu-id="56846-125">**-2** Full scan</span></span><p><span data-ttu-id="56846-126">**-3** ファイルとディレクトリのカスタム スキャン。</span><span class="sxs-lookup"><span data-stu-id="56846-126">**-3** File and directory custom scan.</span></span><p><span data-ttu-id="56846-127">CpuThrottling は、ポリシーから構成された CPU 調整を受け入れ</span><span class="sxs-lookup"><span data-stu-id="56846-127">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="56846-128">診断トレースを開始する</span><span class="sxs-lookup"><span data-stu-id="56846-128">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="56846-129">サポート情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="56846-129">Collects support information.</span></span> <span data-ttu-id="56846-130">「診断[データの収集」を参照](collect-diagnostic-data.md)してください。</span><span class="sxs-lookup"><span data-stu-id="56846-130">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="56846-131">と同 `-GetFiles` じですが、一時的な DiagTrack フォルダーへの出力</span><span class="sxs-lookup"><span data-stu-id="56846-131">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="56846-132">インストールされているセキュリティ インテリジェンスを以前のバックアップ コピーまたは元の既定のセットに復元します。</span><span class="sxs-lookup"><span data-stu-id="56846-132">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="56846-133">動的にダウンロードされたセキュリティ インテリジェンスのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="56846-133">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="56846-134">以前にインストールされたエンジンを復元する</span><span class="sxs-lookup"><span data-stu-id="56846-134">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="56846-135">新しいセキュリティ インテリジェンス更新プログラムのチェック</span><span class="sxs-lookup"><span data-stu-id="56846-135">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="56846-136">検疫済みアイテムを復元または一覧表示する</span><span class="sxs-lookup"><span data-stu-id="56846-136">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="56846-137">動的セキュリティ インテリジェンスを読み込む</span><span class="sxs-lookup"><span data-stu-id="56846-137">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="56846-138">読み込まれた動的セキュリティ インテリジェンスの一覧</span><span class="sxs-lookup"><span data-stu-id="56846-138">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="56846-139">動的セキュリティ インテリジェンスを削除します</span><span class="sxs-lookup"><span data-stu-id="56846-139">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="56846-140">パスが除外されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="56846-140">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="56846-141">ネットワークがクラウド サービスと通信Microsoft Defender ウイルス対策します。</span><span class="sxs-lookup"><span data-stu-id="56846-141">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="56846-142">このコマンドは、バージョン 1703 Windows 10上でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="56846-142">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="56846-143">コマンドを実行する場合の一般的なエラーは、mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="56846-143">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="56846-144">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="56846-144">Error message</span></span> | <span data-ttu-id="56846-145">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="56846-145">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="56846-146">サービスMicrosoft Defender ウイルス対策無効になっています。</span><span class="sxs-lookup"><span data-stu-id="56846-146">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="56846-147">サービスを有効にし、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="56846-147">Enable the service and try again.</span></span> <br>   <span data-ttu-id="56846-148">**注:** 1909 Windows 10以前で、サーバー 2019 Windows以前の場合、サービスは以前は Windows Defender ウイルス対策 サービス *と呼* ばばされています。</span><span class="sxs-lookup"><span data-stu-id="56846-148">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called the *Windows Defender Antivirus* service.</span></span>|
| `0x80070667` | <span data-ttu-id="56846-149">このコマンドは、バージョン 1607 以前Windows 10または以前のコンピューター `-ValidateMapsConnection` Windows Server 2016実行しています。</span><span class="sxs-lookup"><span data-stu-id="56846-149">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="56846-150">バージョン 1703 以降Windows 10サーバー 2019 以降Windowsコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="56846-150">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="56846-151">ツールは、次のいずれかから実行する必要があります (プラットフォームの更新プログラムは 3 月を除いて毎月行うので、異なる `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` 場合があります)</span><span class="sxs-lookup"><span data-stu-id="56846-151">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="56846-152">十分な特権ではありません。</span><span class="sxs-lookup"><span data-stu-id="56846-152">Not enough privileges.</span></span> <span data-ttu-id="56846-153">管理者としてコマンド プロンプト (cmd.exe) を使用します。</span><span class="sxs-lookup"><span data-stu-id="56846-153">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="56846-154">ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。</span><span class="sxs-lookup"><span data-stu-id="56846-154">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="56846-155">名前解決の問題など、ネットワーク関連の問題が考えられる</span><span class="sxs-lookup"><span data-stu-id="56846-155">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="56846-156">ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。</span><span class="sxs-lookup"><span data-stu-id="56846-156">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="56846-157">ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。</span><span class="sxs-lookup"><span data-stu-id="56846-157">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="56846-158">ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。</span><span class="sxs-lookup"><span data-stu-id="56846-158">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="56846-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="56846-159">See also</span></span>

- [<span data-ttu-id="56846-160">Microsoft Defender ウイルス対策機能を構成する</span><span class="sxs-lookup"><span data-stu-id="56846-160">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="56846-161">ビジネスMicrosoft Defender ウイルス対策管理する</span><span class="sxs-lookup"><span data-stu-id="56846-161">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="56846-162">管理および構成ツールのリファレンス トピック</span><span class="sxs-lookup"><span data-stu-id="56846-162">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="56846-163">Microsoft Defender ウイルス対策 (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="56846-163">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)