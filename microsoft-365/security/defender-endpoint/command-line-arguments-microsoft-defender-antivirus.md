---
title: コマンド ラインを使用して Microsoft Defender ウイルス対策を管理する
description: 専用のコマンド ライン ユーティリティを使用して、Microsoft Defender ウイルス対策スキャンを実行し、次世代の保護を構成します。
keywords: Windows Defender スキャンの実行、コマンド ラインからのウイルス対策スキャンの実行、コマンド ラインからの Windows Defender スキャンの実行、mpcmdrun、Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 03/19/2021
ms.technology: mde
ms.openlocfilehash: 2b20227ac27b90d142d263dfa4522aa41319b9d5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691082"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="26a5e-104">Microsoft Defender Antivirus を構成および管理するには、mpcmdrun.exe コマンド ライン ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="26a5e-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="26a5e-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="26a5e-105">**Applies to:**</span></span>

- [<span data-ttu-id="26a5e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="26a5e-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="26a5e-107">専用のコマンド ライン ツールを使用して、さまざまな Microsoft Defender ウイルス対策機能 **を実行** mpcmdrun.exe。</span><span class="sxs-lookup"><span data-stu-id="26a5e-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="26a5e-108">このユーティリティは、Microsoft Defender ウイルス対策の使用を自動化する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="26a5e-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="26a5e-109">ユーティリティは で確認できます `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 。</span><span class="sxs-lookup"><span data-stu-id="26a5e-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="26a5e-110">コマンド プロンプトから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="26a5e-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="26a5e-111">管理者レベルのバージョンのコマンド プロンプトを開く必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="26a5e-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="26a5e-112">[スタート] メニューの **[コマンド プロンプト]** を検索する場合は、[管理者として **実行] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="26a5e-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="26a5e-113">更新された Microsoft Defender プラットフォーム バージョンを実行している場合は、次 `**MpCmdRun**` の場所から実行します `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` 。</span><span class="sxs-lookup"><span data-stu-id="26a5e-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

<span data-ttu-id="26a5e-114">ユーティリティには、次のコマンドがあります。</span><span class="sxs-lookup"><span data-stu-id="26a5e-114">The utility has the following commands:</span></span>

```console
MpCmdRun.exe [command] [-options]
```
<span data-ttu-id="26a5e-115">次に例を示します:</span><span class="sxs-lookup"><span data-stu-id="26a5e-115">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="26a5e-116">コマンド</span><span class="sxs-lookup"><span data-stu-id="26a5e-116">Command</span></span>  | <span data-ttu-id="26a5e-117">説明</span><span class="sxs-lookup"><span data-stu-id="26a5e-117">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="26a5e-118">`-?` **または** `-h`</span><span class="sxs-lookup"><span data-stu-id="26a5e-118">`-?` **or** `-h`</span></span>   | <span data-ttu-id="26a5e-119">このツールで使用可能なすべてのオプションを表示する</span><span class="sxs-lookup"><span data-stu-id="26a5e-119">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="26a5e-120">悪意のあるソフトウェアをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="26a5e-120">Scans for malicious software.</span></span> <span data-ttu-id="26a5e-121">**ScanType の値** は **、構成** に応じて 0 **Default、-1** クイック スキャン **、-2** フル スキャン **、-3** ファイルおよびディレクトリ のカスタム スキャンです。</span><span class="sxs-lookup"><span data-stu-id="26a5e-121">Values for **ScanType** are: **0** Default, according to your configuration, **-1** Quick scan, **-2** Full scan, **-3** File and directory custom scan.</span></span>  <span data-ttu-id="26a5e-122">CpuThrottling は、ポリシーから構成された CPU 調整を受け入れ</span><span class="sxs-lookup"><span data-stu-id="26a5e-122">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="26a5e-123">診断トレースを開始する</span><span class="sxs-lookup"><span data-stu-id="26a5e-123">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="26a5e-124">サポート情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="26a5e-124">Collects support information.</span></span> <span data-ttu-id="26a5e-125">「診断[データの収集」を参照](collect-diagnostic-data.md)してください。</span><span class="sxs-lookup"><span data-stu-id="26a5e-125">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="26a5e-126">と同 `-GetFiles` じですが、一時的な DiagTrack フォルダーへの出力</span><span class="sxs-lookup"><span data-stu-id="26a5e-126">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="26a5e-127">インストールされているセキュリティ インテリジェンスを以前のバックアップ コピーまたは元の既定のセットに復元します。</span><span class="sxs-lookup"><span data-stu-id="26a5e-127">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="26a5e-128">動的にダウンロードされたセキュリティ インテリジェンスのみを削除します。</span><span class="sxs-lookup"><span data-stu-id="26a5e-128">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="26a5e-129">以前にインストールされたエンジンを復元する</span><span class="sxs-lookup"><span data-stu-id="26a5e-129">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="26a5e-130">新しいセキュリティ インテリジェンス更新プログラムのチェック</span><span class="sxs-lookup"><span data-stu-id="26a5e-130">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="26a5e-131">検疫済みアイテムを復元または一覧表示する</span><span class="sxs-lookup"><span data-stu-id="26a5e-131">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="26a5e-132">動的セキュリティ インテリジェンスを読み込む</span><span class="sxs-lookup"><span data-stu-id="26a5e-132">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="26a5e-133">読み込まれた動的セキュリティ インテリジェンスの一覧</span><span class="sxs-lookup"><span data-stu-id="26a5e-133">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="26a5e-134">動的セキュリティ インテリジェンスを削除します</span><span class="sxs-lookup"><span data-stu-id="26a5e-134">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="26a5e-135">パスが除外されているかどうかを確認する</span><span class="sxs-lookup"><span data-stu-id="26a5e-135">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="26a5e-136">ネットワークが Microsoft Defender ウイルス対策クラウド サービスと通信できると確認します。</span><span class="sxs-lookup"><span data-stu-id="26a5e-136">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="26a5e-137">このコマンドは、Windows 10 バージョン 1703 以上でのみ動作します。</span><span class="sxs-lookup"><span data-stu-id="26a5e-137">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="26a5e-138">コマンドを実行する場合の一般的なエラーは、mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="26a5e-138">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="26a5e-139">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="26a5e-139">Error message</span></span> | <span data-ttu-id="26a5e-140">考えられる理由</span><span class="sxs-lookup"><span data-stu-id="26a5e-140">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="26a5e-141">Microsoft Defender ウイルス対策サービスが無効になっています。</span><span class="sxs-lookup"><span data-stu-id="26a5e-141">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="26a5e-142">サービスを有効にし、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="26a5e-142">Enable the service and try again.</span></span> <br>   <span data-ttu-id="26a5e-143">**注:**  Windows 10 1909 以前および Windows Server 2019 以前の場合、このサービスは以前は "Windows Defender ウイルス対策" サービスと呼ばばがありました。</span><span class="sxs-lookup"><span data-stu-id="26a5e-143">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called "Windows Defender Antivirus" service.</span></span>|
| `0x80070667` | <span data-ttu-id="26a5e-144">このコマンドは `-ValidateMapsConnection` 、Windows 10 バージョン 1607 以前のコンピューター、または Windows Server 2016 以前のコンピューターから実行しています。</span><span class="sxs-lookup"><span data-stu-id="26a5e-144">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="26a5e-145">Windows 10 バージョン 1703 以降、または Windows Server 2019 以降のコンピューターからコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="26a5e-145">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="26a5e-146">ツールは、次のいずれかから実行する必要があります (プラットフォームの更新プログラムは 3 月を除いて毎月行うので、異なる `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` 場合があります)</span><span class="sxs-lookup"><span data-stu-id="26a5e-146">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="26a5e-147">十分な特権ではありません。</span><span class="sxs-lookup"><span data-stu-id="26a5e-147">Not enough privileges.</span></span> <span data-ttu-id="26a5e-148">管理者としてコマンド プロンプト (cmd.exe) を使用します。</span><span class="sxs-lookup"><span data-stu-id="26a5e-148">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="26a5e-149">ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。</span><span class="sxs-lookup"><span data-stu-id="26a5e-149">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="26a5e-150">名前解決の問題など、ネットワーク関連の問題が考えられる</span><span class="sxs-lookup"><span data-stu-id="26a5e-150">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="26a5e-151">ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。</span><span class="sxs-lookup"><span data-stu-id="26a5e-151">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="26a5e-152">ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。</span><span class="sxs-lookup"><span data-stu-id="26a5e-152">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="26a5e-153">ファイアウォールが接続をブロックしている、または SSL インスペクションを実行しています。</span><span class="sxs-lookup"><span data-stu-id="26a5e-153">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="26a5e-154">関連項目</span><span class="sxs-lookup"><span data-stu-id="26a5e-154">See also</span></span>

- [<span data-ttu-id="26a5e-155">Microsoft Defender ウイルス対策機能の構成</span><span class="sxs-lookup"><span data-stu-id="26a5e-155">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="26a5e-156">ビジネスで Microsoft Defender ウイルス対策を管理する</span><span class="sxs-lookup"><span data-stu-id="26a5e-156">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="26a5e-157">管理および構成ツールのリファレンス トピック</span><span class="sxs-lookup"><span data-stu-id="26a5e-157">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="26a5e-158">Windows 10 の Microsoft Defender ウイルス対策</span><span class="sxs-lookup"><span data-stu-id="26a5e-158">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)