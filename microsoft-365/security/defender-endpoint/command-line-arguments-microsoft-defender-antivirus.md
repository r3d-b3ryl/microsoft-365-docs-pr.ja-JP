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
ms.date: 05/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 25f038846f9dd9855823382d4e1babcf0547fed6
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636172"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="82eb0-104">コマンド ライン Microsoft Defender ウイルス対策を使用してmpcmdrun.exeを構成および管理する</span><span class="sxs-lookup"><span data-stu-id="82eb0-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

<span data-ttu-id="82eb0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="82eb0-105">**Applies to:**</span></span>

- [<span data-ttu-id="82eb0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="82eb0-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="82eb0-107">専用のコマンド ライン ツール を使用して、Microsoft Defender ウイルス対策でさまざまな **機能を実行** mpcmdrun.exe。</span><span class="sxs-lookup"><span data-stu-id="82eb0-107">You can perform various functions in Microsoft Defender Antivirus using the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="82eb0-108">このユーティリティは、タスクを自動化する場合Microsoft Defender ウイルス対策です。</span><span class="sxs-lookup"><span data-stu-id="82eb0-108">This utility is useful when you want to automate Microsoft Defender Antivirus tasks.</span></span> <span data-ttu-id="82eb0-109">ユーティリティは で確認できます `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。</span><span class="sxs-lookup"><span data-stu-id="82eb0-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="82eb0-110">コマンド プロンプトから実行します。</span><span class="sxs-lookup"><span data-stu-id="82eb0-110">Run it from a command prompt.</span></span>

> [!TIP]
> <span data-ttu-id="82eb0-111">管理者レベルのバージョンのコマンド プロンプトを開く必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="82eb0-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="82eb0-112">[スタート] メニューの **[コマンド プロンプト]** を検索する場合は、[管理者として **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="82eb0-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span> <span data-ttu-id="82eb0-113">更新された Microsoft Defender プラットフォーム バージョンを実行している場合は、次 `MpCmdRun` の場所から実行します `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` 。</span><span class="sxs-lookup"><span data-stu-id="82eb0-113">If you're running an updated Microsoft Defender Platform version, run `MpCmdRun` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>`.</span></span> <span data-ttu-id="82eb0-114">マルウェア対策プラットフォームの詳細については、「更新プログラムとベースラインMicrosoft Defender ウイルス対策[を参照してください](manage-updates-baselines-microsoft-defender-antivirus.md)。</span><span class="sxs-lookup"><span data-stu-id="82eb0-114">For more information about the antimalware platform, see [Microsoft Defender Antivirus updates and baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="82eb0-115">MpCmdRun ユーティリティは、次の構文を使用します。</span><span class="sxs-lookup"><span data-stu-id="82eb0-115">The MpCmdRun utility uses the following syntax:</span></span>

```console
MpCmdRun.exe [command] [-options]
```

<span data-ttu-id="82eb0-116">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="82eb0-116">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

<span data-ttu-id="82eb0-117">この例では、MpCmdRun ユーティリティはデバイスで完全なウイルス対策スキャンを開始します。</span><span class="sxs-lookup"><span data-stu-id="82eb0-117">In our example, the MpCmdRun utility starts a full antivirus scan on the device.</span></span>

## <a name="commands"></a><span data-ttu-id="82eb0-118">コマンド</span><span class="sxs-lookup"><span data-stu-id="82eb0-118">Commands</span></span>

| <span data-ttu-id="82eb0-119">コマンド</span><span class="sxs-lookup"><span data-stu-id="82eb0-119">Command</span></span>  | <span data-ttu-id="82eb0-120">説明</span><span class="sxs-lookup"><span data-stu-id="82eb0-120">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="82eb0-121">`-?`**または**`-h`</span><span class="sxs-lookup"><span data-stu-id="82eb0-121">`-?` **or** `-h`</span></span>   | <span data-ttu-id="82eb0-122">MpCmdRun ツールで使用可能なすべてのオプションを表示する</span><span class="sxs-lookup"><span data-stu-id="82eb0-122">Displays all available options for the MpCmdRun tool</span></span> |
| `-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="82eb0-123">悪意のあるソフトウェアをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="82eb0-123">Scans for malicious software.</span></span> <span data-ttu-id="82eb0-124">**ScanType の値は次** のとおりです。</span><span class="sxs-lookup"><span data-stu-id="82eb0-124">Values for **ScanType** are:</span></span><p><span data-ttu-id="82eb0-125">**0** 構成に応じて既定</span><span class="sxs-lookup"><span data-stu-id="82eb0-125">**0** Default, according to your configuration</span></span><p><span data-ttu-id="82eb0-126">**1** クイック スキャン</span><span class="sxs-lookup"><span data-stu-id="82eb0-126">**1** Quick scan</span></span><p><span data-ttu-id="82eb0-127">**2** フル スキャン</span><span class="sxs-lookup"><span data-stu-id="82eb0-127">**2** Full scan</span></span><p><span data-ttu-id="82eb0-128">**3** ファイルとディレクトリのカスタム スキャン。</span><span class="sxs-lookup"><span data-stu-id="82eb0-128">**3** File and directory custom scan.</span></span><p><span data-ttu-id="82eb0-129">CpuThrottling はポリシー構成に従って実行されます</span><span class="sxs-lookup"><span data-stu-id="82eb0-129">CpuThrottling runs according to policy configurations</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="82eb0-130">診断トレースを開始する</span><span class="sxs-lookup"><span data-stu-id="82eb0-130">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="82eb0-131">サポート情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="82eb0-131">Collects support information.</span></span> <span data-ttu-id="82eb0-132">「診断[データの収集」を参照](collect-diagnostic-data.md)してください。</span><span class="sxs-lookup"><span data-stu-id="82eb0-132">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="82eb0-133">と同 `-GetFiles` じですが、一時的な DiagTrack フォルダーへの出力</span><span class="sxs-lookup"><span data-stu-id="82eb0-133">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="82eb0-134">インストールされているセキュリティ インテリジェンスを以前のバックアップ コピーまたは元の既定のセットに復元します。</span><span class="sxs-lookup"><span data-stu-id="82eb0-134">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="82eb0-135">動的にダウンロードされたセキュリティ インテリジェンスのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="82eb0-135">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="82eb0-136">以前にインストールされたエンジンを復元する</span><span class="sxs-lookup"><span data-stu-id="82eb0-136">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="82eb0-137">新しいセキュリティ インテリジェンス更新プログラムのチェック</span><span class="sxs-lookup"><span data-stu-id="82eb0-137">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="82eb0-138">検疫済みアイテムを復元または一覧表示する</span><span class="sxs-lookup"><span data-stu-id="82eb0-138">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="82eb0-139">動的セキュリティ インテリジェンスを読み込む</span><span class="sxs-lookup"><span data-stu-id="82eb0-139">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="82eb0-140">読み込まれた動的セキュリティ インテリジェンスの一覧</span><span class="sxs-lookup"><span data-stu-id="82eb0-140">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="82eb0-141">動的セキュリティ インテリジェンスを削除します</span><span class="sxs-lookup"><span data-stu-id="82eb0-141">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="82eb0-142">パスが除外されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="82eb0-142">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="82eb0-143">ネットワークがクラウド サービスと通信Microsoft Defender ウイルス対策します。</span><span class="sxs-lookup"><span data-stu-id="82eb0-143">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="82eb0-144">このコマンドは、バージョン 1703 Windows 10上でのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="82eb0-144">This command will only work on Windows 10, version 1703 or higher.</span></span>|

## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="82eb0-145">コマンドを実行する場合の一般的なエラーは、mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="82eb0-145">Common errors in running commands via mpcmdrun.exe</span></span> 

<span data-ttu-id="82eb0-146">次の表に、MpCmdRun ツールの使用中に発生する可能性がある一般的なエラーの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="82eb0-146">The following table lists common errors that can occur while using the MpCmdRun tool.</span></span>

|<span data-ttu-id="82eb0-147">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="82eb0-147">Error message</span></span> | <span data-ttu-id="82eb0-148">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="82eb0-148">Possible reason</span></span> |
|:----|:----|
| <span data-ttu-id="82eb0-149">**ValidateMapsConnection が失敗しました (800106BA)** **または** 0x800106BA</span><span class="sxs-lookup"><span data-stu-id="82eb0-149">**ValidateMapsConnection failed (800106BA)** or **0x800106BA**</span></span> | <span data-ttu-id="82eb0-150">サービスMicrosoft Defender ウイルス対策無効になっています。</span><span class="sxs-lookup"><span data-stu-id="82eb0-150">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="82eb0-151">サービスを有効にし、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="82eb0-151">Enable the service and try again.</span></span> <span data-ttu-id="82eb0-152">アプリケーションの再有効化に関するヘルプがMicrosoft Defender ウイルス対策、エンドポイント[の再インストール/有効化Microsoft Defender ウイルス対策を参照してください](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="82eb0-152">If you need help re-enabling Microsoft Defender Antivirus, see [Reinstall/enable Microsoft Defender Antivirus on your endpoints](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints).</span></span><p>   <span data-ttu-id="82eb0-153">**ヒント** 1909 Windows 10以前で、サーバー 2019 Windows以前の場合、このサービスは以前は Windows Defender ウイルス対策 と *呼ばWindows Defender ウイルス対策。*</span><span class="sxs-lookup"><span data-stu-id="82eb0-153">**TIP**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service was formerly called *Windows Defender Antivirus*.</span></span> |
| <span data-ttu-id="82eb0-154">**0x80070667**</span><span class="sxs-lookup"><span data-stu-id="82eb0-154">**0x80070667**</span></span> | <span data-ttu-id="82eb0-155">このコマンドは、バージョン 1607 以前Windows 10または以前のコンピューター `-ValidateMapsConnection` Windows Server 2016実行しています。</span><span class="sxs-lookup"><span data-stu-id="82eb0-155">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="82eb0-156">バージョン 1703 以降Windows 10サーバー 2019 以降Windowsコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="82eb0-156">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| <span data-ttu-id="82eb0-157">**MpCmdRun は、内部または外部のコマンド、操作可能なプログラム、またはバッチ ファイルとして認識されません。**</span><span class="sxs-lookup"><span data-stu-id="82eb0-157">**MpCmdRun is not recognized as an internal or external command, operable program, or batch file.**</span></span> | <span data-ttu-id="82eb0-158">ツールを実行する必要があります (プラットフォームの更新プログラムは 3 月を除いて毎月行うので、異なる `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` 場合があります)</span><span class="sxs-lookup"><span data-stu-id="82eb0-158">The tool must be run from either `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| <span data-ttu-id="82eb0-159">**ValidateMapsConnection が MAPS への接続を確立できなかった (hr=80070005 httpcode=450)**</span><span class="sxs-lookup"><span data-stu-id="82eb0-159">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)**</span></span> | <span data-ttu-id="82eb0-160">コマンドは、不十分な特権を使用して試行されました。</span><span class="sxs-lookup"><span data-stu-id="82eb0-160">The command was attempted using insufficient privileges.</span></span> <span data-ttu-id="82eb0-161">管理者としてコマンド プロンプト (cmd.exe) を使用します。</span><span class="sxs-lookup"><span data-stu-id="82eb0-161">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| <span data-ttu-id="82eb0-162">**ValidateMapsConnection が MAPS への接続を確立できなかった (hr=80070006 httpcode=451)**</span><span class="sxs-lookup"><span data-stu-id="82eb0-162">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)**</span></span> | <span data-ttu-id="82eb0-163">ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。</span><span class="sxs-lookup"><span data-stu-id="82eb0-163">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| <span data-ttu-id="82eb0-164">**ValidateMapsConnection が MAPS への接続を確立できなかった (hr=80004005 httpcode=450)**</span><span class="sxs-lookup"><span data-stu-id="82eb0-164">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)**</span></span> | <span data-ttu-id="82eb0-165">名前解決の問題など、ネットワーク関連の問題が考えられる</span><span class="sxs-lookup"><span data-stu-id="82eb0-165">Possible network-related issues, like name resolution problems</span></span>|
| <span data-ttu-id="82eb0-166">**ValidateMapsConnection が MAPS への接続を確立できなかった (hr=0x80508015**</span><span class="sxs-lookup"><span data-stu-id="82eb0-166">**ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015**</span></span> | <span data-ttu-id="82eb0-167">ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。</span><span class="sxs-lookup"><span data-stu-id="82eb0-167">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| <span data-ttu-id="82eb0-168">**ValidateMapsConnection が MAPS への接続を確立できなかった (hr=800722F0D**</span><span class="sxs-lookup"><span data-stu-id="82eb0-168">**ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D**</span></span> | <span data-ttu-id="82eb0-169">ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。</span><span class="sxs-lookup"><span data-stu-id="82eb0-169">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| <span data-ttu-id="82eb0-170">**ValidateMapsConnection が MAPS への接続を確立できなかった (hr=80072EE7 httpcode=451)**</span><span class="sxs-lookup"><span data-stu-id="82eb0-170">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)**</span></span> | <span data-ttu-id="82eb0-171">ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。</span><span class="sxs-lookup"><span data-stu-id="82eb0-171">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="82eb0-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="82eb0-172">See also</span></span>

- [<span data-ttu-id="82eb0-173">Microsoft Defender ウイルス対策機能を構成する</span><span class="sxs-lookup"><span data-stu-id="82eb0-173">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="82eb0-174">Microsoft Defender ウイルス対策 ネットワーク接続を構成および検証する</span><span class="sxs-lookup"><span data-stu-id="82eb0-174">Configure and validate Microsoft Defender Antivirus network connections</span></span>](configure-network-connections-microsoft-defender-antivirus.md)
- [<span data-ttu-id="82eb0-175">管理および構成ツールのリファレンス トピック</span><span class="sxs-lookup"><span data-stu-id="82eb0-175">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
