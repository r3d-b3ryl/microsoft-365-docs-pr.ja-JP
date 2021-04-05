---
title: Microsoft Defender ATP for Linux リソース
ms.reviewer: ''
description: Microsoft Defender ATP for Linux のリソース (アンインストール方法、診断ログの収集方法、CLI コマンド、製品に関する既知の問題など) について説明します。
keywords: microsoft、 defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a4f2324bc47bdee38e1cdeed1e21b5f9063e9a5c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587066"
---
# <a name="resources"></a><span data-ttu-id="8dd13-104">リソース</span><span class="sxs-lookup"><span data-stu-id="8dd13-104">Resources</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8dd13-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="8dd13-105">**Applies to:**</span></span>
- [<span data-ttu-id="8dd13-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="8dd13-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8dd13-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8dd13-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8dd13-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="8dd13-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8dd13-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="8dd13-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a><span data-ttu-id="8dd13-110">診断情報の収集</span><span class="sxs-lookup"><span data-stu-id="8dd13-110">Collect diagnostic information</span></span>

<span data-ttu-id="8dd13-111">問題を再現できる場合は、まずログ レベルを上げ、システムを一時実行してから、ログ レベルを既定に復元します。</span><span class="sxs-lookup"><span data-stu-id="8dd13-111">If you can reproduce a problem, first increase the logging level, run the system for some time, and then restore the logging level to the default.</span></span>

1. <span data-ttu-id="8dd13-112">ログ レベルを上げ:</span><span class="sxs-lookup"><span data-stu-id="8dd13-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="8dd13-113">問題を再現します。</span><span class="sxs-lookup"><span data-stu-id="8dd13-113">Reproduce the problem.</span></span>

3. <span data-ttu-id="8dd13-114">次のコマンドを実行して、Defender for Endpoint のログをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="8dd13-114">Run the following command to back up Defender for Endpoint's logs.</span></span> <span data-ttu-id="8dd13-115">ファイルは .zip アーカイブ内に格納されます。</span><span class="sxs-lookup"><span data-stu-id="8dd13-115">The files will be stored inside of a .zip archive.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

    <span data-ttu-id="8dd13-116">このコマンドは、操作が成功した後、バックアップへのファイル パスも出力します。</span><span class="sxs-lookup"><span data-stu-id="8dd13-116">This command will also print out the file path to the backup after the operation succeeds:</span></span>

   ```Output
   Diagnostic file created: <path to file>
   ```

4. <span data-ttu-id="8dd13-117">ログ レベルの復元:</span><span class="sxs-lookup"><span data-stu-id="8dd13-117">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a><span data-ttu-id="8dd13-118">ログ インストールの問題</span><span class="sxs-lookup"><span data-stu-id="8dd13-118">Log installation issues</span></span>

<span data-ttu-id="8dd13-119">インストール中にエラーが発生した場合、インストーラーは一般的なエラーのみを報告します。</span><span class="sxs-lookup"><span data-stu-id="8dd13-119">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="8dd13-120">詳細ログはに保存されます `/var/log/microsoft/mdatp_install.log` 。</span><span class="sxs-lookup"><span data-stu-id="8dd13-120">The detailed log will be saved to `/var/log/microsoft/mdatp_install.log`.</span></span> <span data-ttu-id="8dd13-121">インストール中に問題が発生した場合は、このファイルを送信して、原因の診断に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8dd13-121">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstall"></a><span data-ttu-id="8dd13-122">Uninstall</span><span class="sxs-lookup"><span data-stu-id="8dd13-122">Uninstall</span></span>

<span data-ttu-id="8dd13-123">Defender for Endpoint for Linux をアンインストールするには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="8dd13-123">There are several ways to uninstall Defender for Endpoint for Linux.</span></span> <span data-ttu-id="8dd13-124">Puppet などの構成ツールを使用している場合は、構成ツールのパッケージのアンインストール手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8dd13-124">If you are using a configuration tool such as Puppet, follow the package uninstallation instructions for the configuration tool.</span></span>

### <a name="manual-uninstallation"></a><span data-ttu-id="8dd13-125">手動アンインストール</span><span class="sxs-lookup"><span data-stu-id="8dd13-125">Manual uninstallation</span></span>

- <span data-ttu-id="8dd13-126">`sudo yum remove mdatp` RHEL およびバリアント (CentOS および Oracle Linux) の場合。</span><span class="sxs-lookup"><span data-stu-id="8dd13-126">`sudo yum remove mdatp` for RHEL and variants(CentOS and Oracle Linux).</span></span>
- <span data-ttu-id="8dd13-127">`sudo zypper remove mdatp` SLES およびバリアントの場合。</span><span class="sxs-lookup"><span data-stu-id="8dd13-127">`sudo zypper remove mdatp` for SLES and variants.</span></span>
- <span data-ttu-id="8dd13-128">`sudo apt-get purge mdatp` Ubuntu および Debian システム用。</span><span class="sxs-lookup"><span data-stu-id="8dd13-128">`sudo apt-get purge mdatp` for Ubuntu and Debian systems.</span></span>

## <a name="configure-from-the-command-line"></a><span data-ttu-id="8dd13-129">コマンド ラインから構成する</span><span class="sxs-lookup"><span data-stu-id="8dd13-129">Configure from the command line</span></span>

<span data-ttu-id="8dd13-130">製品設定の制御やオンデマンド スキャンのトリガーなどの重要なタスクは、コマンド ラインから実行できます。</span><span class="sxs-lookup"><span data-stu-id="8dd13-130">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line.</span></span>

### <a name="global-options"></a><span data-ttu-id="8dd13-131">グローバル オプション</span><span class="sxs-lookup"><span data-stu-id="8dd13-131">Global options</span></span>

<span data-ttu-id="8dd13-132">既定では、コマンド ライン ツールは人間が読み取り可能な形式で結果を出力します。</span><span class="sxs-lookup"><span data-stu-id="8dd13-132">By default, the command-line tool outputs the result in human-readable format.</span></span> <span data-ttu-id="8dd13-133">さらに、このツールは JSON としての結果の出力もサポートしています。これは自動化シナリオに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8dd13-133">In addition, the tool also supports outputting the result as JSON, which is useful for automation scenarios.</span></span> <span data-ttu-id="8dd13-134">出力を JSON に変更するには、次 `--output json` のコマンドに渡します。</span><span class="sxs-lookup"><span data-stu-id="8dd13-134">To change the output to JSON, pass `--output json` to any of the below commands.</span></span>

### <a name="supported-commands"></a><span data-ttu-id="8dd13-135">サポートされているコマンド</span><span class="sxs-lookup"><span data-stu-id="8dd13-135">Supported commands</span></span>

<span data-ttu-id="8dd13-136">次の表に、最も一般的なシナリオの一部のコマンドを示します。</span><span class="sxs-lookup"><span data-stu-id="8dd13-136">The following table lists commands for some of the most common scenarios.</span></span> <span data-ttu-id="8dd13-137">ターミナル `mdatp help` から実行して、サポートされているコマンドの完全な一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="8dd13-137">Run `mdatp help` from the Terminal to view the full list of supported commands.</span></span>

|<span data-ttu-id="8dd13-138">Group</span><span class="sxs-lookup"><span data-stu-id="8dd13-138">Group</span></span>                 |<span data-ttu-id="8dd13-139">シナリオ</span><span class="sxs-lookup"><span data-stu-id="8dd13-139">Scenario</span></span>                                                |<span data-ttu-id="8dd13-140">コマンド</span><span class="sxs-lookup"><span data-stu-id="8dd13-140">Command</span></span>                                                                |
|----------------------|--------------------------------------------------------|-----------------------------------------------------------------------|
|<span data-ttu-id="8dd13-141">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-141">Configuration</span></span>         |<span data-ttu-id="8dd13-142">リアルタイム保護のオン/オフ</span><span class="sxs-lookup"><span data-stu-id="8dd13-142">Turn on/off real-time protection</span></span>                        |`mdatp config real-time-protection --value [enabled\|disabled]`        |
|<span data-ttu-id="8dd13-143">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-143">Configuration</span></span>         |<span data-ttu-id="8dd13-144">動作監視のオン/オフを切り替えます</span><span class="sxs-lookup"><span data-stu-id="8dd13-144">Turn on/off behavior monitoring</span></span>                         |`mdatp config behavior-monitoring --value [enabled\|disabled]` 
|<span data-ttu-id="8dd13-145">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-145">Configuration</span></span>         |<span data-ttu-id="8dd13-146">クラウド保護のオン/オフ</span><span class="sxs-lookup"><span data-stu-id="8dd13-146">Turn on/off cloud protection</span></span>                            |`mdatp config cloud --value [enabled\|disabled]`                       |
|<span data-ttu-id="8dd13-147">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-147">Configuration</span></span>         |<span data-ttu-id="8dd13-148">製品診断のオン/オフ</span><span class="sxs-lookup"><span data-stu-id="8dd13-148">Turn on/off product diagnostics</span></span>                         |`mdatp config cloud-diagnostic --value [enabled\|disabled]`            |
|<span data-ttu-id="8dd13-149">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-149">Configuration</span></span>         |<span data-ttu-id="8dd13-150">自動サンプル申請のオン/オフ</span><span class="sxs-lookup"><span data-stu-id="8dd13-150">Turn on/off automatic sample submission</span></span>                 |`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`   |
|<span data-ttu-id="8dd13-151">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-151">Configuration</span></span>         |<span data-ttu-id="8dd13-152">AV パッシブ モードのオン/オフ</span><span class="sxs-lookup"><span data-stu-id="8dd13-152">Turn on/off AV passive mode</span></span>                             |`mdatp config passive-mode --value [enabled\|disabled]`                |
|<span data-ttu-id="8dd13-153">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-153">Configuration</span></span>         |<span data-ttu-id="8dd13-154">ファイル拡張子のウイルス対策除外を追加/削除する</span><span class="sxs-lookup"><span data-stu-id="8dd13-154">Add/remove an antivirus exclusion for a file extension</span></span>  |`mdatp exclusion extension [add\|remove] --name [extension]`           |
|<span data-ttu-id="8dd13-155">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-155">Configuration</span></span>         |<span data-ttu-id="8dd13-156">ファイルのウイルス対策除外を追加/削除する</span><span class="sxs-lookup"><span data-stu-id="8dd13-156">Add/remove an antivirus exclusion for a file</span></span>            |`mdatp exclusion file [add\|remove] --path [path-to-file]`             |
|<span data-ttu-id="8dd13-157">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-157">Configuration</span></span>         |<span data-ttu-id="8dd13-158">ディレクトリのウイルス対策の除外を追加/削除する</span><span class="sxs-lookup"><span data-stu-id="8dd13-158">Add/remove an antivirus exclusion for a directory</span></span>       |`mdatp exclusion folder [add\|remove] --path [path-to-directory]`      |
|<span data-ttu-id="8dd13-159">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-159">Configuration</span></span>         |<span data-ttu-id="8dd13-160">プロセスのウイルス対策除外を追加/削除する</span><span class="sxs-lookup"><span data-stu-id="8dd13-160">Add/remove an antivirus exclusion for a process</span></span>         |`mdatp exclusion process [add\|remove] --path [path-to-process]`<br/>`mdatp exclusion process [add\|remove] --name [process-name]` |
|<span data-ttu-id="8dd13-161">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-161">Configuration</span></span>         |<span data-ttu-id="8dd13-162">すべてのウイルス対策の除外を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="8dd13-162">List all antivirus exclusions</span></span>                           |`mdatp exclusion list`                                                 |
|<span data-ttu-id="8dd13-163">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-163">Configuration</span></span>         |<span data-ttu-id="8dd13-164">許可リストに脅威名を追加する</span><span class="sxs-lookup"><span data-stu-id="8dd13-164">Add a threat name to the allowed list</span></span>                   |`mdatp threat allowed add --name [threat-name]`                        |
|<span data-ttu-id="8dd13-165">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-165">Configuration</span></span>         |<span data-ttu-id="8dd13-166">許可リストから脅威名を削除する</span><span class="sxs-lookup"><span data-stu-id="8dd13-166">Remove a threat name from the allowed list</span></span>              |`mdatp threat allowed remove --name [threat-name]`                     |
|<span data-ttu-id="8dd13-167">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-167">Configuration</span></span>         |<span data-ttu-id="8dd13-168">許可されている脅威名の一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="8dd13-168">List all allowed threat names</span></span>                           |`mdatp threat allowed list`                                            |
|<span data-ttu-id="8dd13-169">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-169">Configuration</span></span>         |<span data-ttu-id="8dd13-170">PUA 保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="8dd13-170">Turn on PUA protection</span></span>                                  |`mdatp threat policy set --type potentially_unwanted_application --action block` |
|<span data-ttu-id="8dd13-171">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-171">Configuration</span></span>         |<span data-ttu-id="8dd13-172">PUA 保護をオフにする</span><span class="sxs-lookup"><span data-stu-id="8dd13-172">Turn off PUA protection</span></span>                                 |`mdatp threat policy set --type potentially_unwanted_application --action off` |
|<span data-ttu-id="8dd13-173">構成</span><span class="sxs-lookup"><span data-stu-id="8dd13-173">Configuration</span></span>         |<span data-ttu-id="8dd13-174">PUA 保護の監査モードを有効にする</span><span class="sxs-lookup"><span data-stu-id="8dd13-174">Turn on audit mode for PUA protection</span></span>                   |`mdatp threat policy set --type potentially_unwanted_application --action audit` |
|<span data-ttu-id="8dd13-175">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="8dd13-175">Diagnostics</span></span>           |<span data-ttu-id="8dd13-176">ログ レベルの変更</span><span class="sxs-lookup"><span data-stu-id="8dd13-176">Change the log level</span></span>                                    |`mdatp log level set --level verbose [error|warning|info|verbose]`     |
|<span data-ttu-id="8dd13-177">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="8dd13-177">Diagnostics</span></span>           |<span data-ttu-id="8dd13-178">診断ログの生成</span><span class="sxs-lookup"><span data-stu-id="8dd13-178">Generate diagnostic logs</span></span>                                |`mdatp diagnostic create --path [directory]`                           |
|<span data-ttu-id="8dd13-179">正常性</span><span class="sxs-lookup"><span data-stu-id="8dd13-179">Health</span></span>                |<span data-ttu-id="8dd13-180">製品の正常性を確認する</span><span class="sxs-lookup"><span data-stu-id="8dd13-180">Check the product's health</span></span>                              |`mdatp health`                                                         |
|<span data-ttu-id="8dd13-181">保護</span><span class="sxs-lookup"><span data-stu-id="8dd13-181">Protection</span></span>            |<span data-ttu-id="8dd13-182">パスをスキャンする</span><span class="sxs-lookup"><span data-stu-id="8dd13-182">Scan a path</span></span>                                             |`mdatp scan custom --path [path] [--ignore-exclusions]`                |
|<span data-ttu-id="8dd13-183">保護</span><span class="sxs-lookup"><span data-stu-id="8dd13-183">Protection</span></span>            |<span data-ttu-id="8dd13-184">クイック スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="8dd13-184">Do a quick scan</span></span>                                         |`mdatp scan quick`                                                     |
|<span data-ttu-id="8dd13-185">保護</span><span class="sxs-lookup"><span data-stu-id="8dd13-185">Protection</span></span>            |<span data-ttu-id="8dd13-186">フル スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="8dd13-186">Do a full scan</span></span>                                          |`mdatp scan full`                                                      |
|<span data-ttu-id="8dd13-187">保護</span><span class="sxs-lookup"><span data-stu-id="8dd13-187">Protection</span></span>            |<span data-ttu-id="8dd13-188">進行中のオンデマンド スキャンをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="8dd13-188">Cancel an ongoing on-demand scan</span></span>                        |`mdatp scan cancel`                                                    |
|<span data-ttu-id="8dd13-189">保護</span><span class="sxs-lookup"><span data-stu-id="8dd13-189">Protection</span></span>            |<span data-ttu-id="8dd13-190">セキュリティ インテリジェンス更新プログラムの要求</span><span class="sxs-lookup"><span data-stu-id="8dd13-190">Request a security intelligence update</span></span>                  |`mdatp definitions update`                                             |
|<span data-ttu-id="8dd13-191">保護履歴</span><span class="sxs-lookup"><span data-stu-id="8dd13-191">Protection history</span></span>    |<span data-ttu-id="8dd13-192">完全な保護履歴を印刷する</span><span class="sxs-lookup"><span data-stu-id="8dd13-192">Print the full protection history</span></span>                       |`mdatp threat list`                                                    |
|<span data-ttu-id="8dd13-193">保護履歴</span><span class="sxs-lookup"><span data-stu-id="8dd13-193">Protection history</span></span>    |<span data-ttu-id="8dd13-194">脅威の詳細を取得する</span><span class="sxs-lookup"><span data-stu-id="8dd13-194">Get threat details</span></span>                                      |`mdatp threat get --id [threat-id]`                                    |
|<span data-ttu-id="8dd13-195">検疫の管理</span><span class="sxs-lookup"><span data-stu-id="8dd13-195">Quarantine management</span></span> |<span data-ttu-id="8dd13-196">検疫済みファイルの一覧表示</span><span class="sxs-lookup"><span data-stu-id="8dd13-196">List all quarantined files</span></span>                              |`mdatp threat quarantine list`                                         |
|<span data-ttu-id="8dd13-197">検疫の管理</span><span class="sxs-lookup"><span data-stu-id="8dd13-197">Quarantine management</span></span> |<span data-ttu-id="8dd13-198">検疫からすべてのファイルを削除する</span><span class="sxs-lookup"><span data-stu-id="8dd13-198">Remove all files from the quarantine</span></span>                    |`mdatp threat quarantine remove-all`                                   |
|<span data-ttu-id="8dd13-199">検疫の管理</span><span class="sxs-lookup"><span data-stu-id="8dd13-199">Quarantine management</span></span> |<span data-ttu-id="8dd13-200">脅威として検出されたファイルを検疫に追加する</span><span class="sxs-lookup"><span data-stu-id="8dd13-200">Add a file detected as a threat to the quarantine</span></span>       |`mdatp threat quarantine add --id [threat-id]`                         |
|<span data-ttu-id="8dd13-201">検疫の管理</span><span class="sxs-lookup"><span data-stu-id="8dd13-201">Quarantine management</span></span> |<span data-ttu-id="8dd13-202">脅威として検出されたファイルを検疫から削除する</span><span class="sxs-lookup"><span data-stu-id="8dd13-202">Remove a file detected as a threat from the quarantine</span></span>  |`mdatp threat quarantine remove --id [threat-id]`                      |
|<span data-ttu-id="8dd13-203">検疫の管理</span><span class="sxs-lookup"><span data-stu-id="8dd13-203">Quarantine management</span></span> |<span data-ttu-id="8dd13-204">検疫からファイルを復元する</span><span class="sxs-lookup"><span data-stu-id="8dd13-204">Restore a file from the quarantine</span></span>                      |`mdatp threat quarantine restore --id [threat-id]`                     |
|<span data-ttu-id="8dd13-205">エンドポイントの検出と応答</span><span class="sxs-lookup"><span data-stu-id="8dd13-205">Endpoint Detection and Response</span></span> |<span data-ttu-id="8dd13-206">早期プレビューの設定 (未使用)</span><span class="sxs-lookup"><span data-stu-id="8dd13-206">Set early preview (unused)</span></span>                    |`mdatp edr early-preview [enable|disable]`                             |
|<span data-ttu-id="8dd13-207">エンドポイントの検出と応答</span><span class="sxs-lookup"><span data-stu-id="8dd13-207">Endpoint Detection and Response</span></span> |<span data-ttu-id="8dd13-208">group-id を設定する</span><span class="sxs-lookup"><span data-stu-id="8dd13-208">Set group-id</span></span>                                  |`mdatp edr group-ids --group-id [group-id]`                            |
|<span data-ttu-id="8dd13-209">エンドポイントの検出と応答</span><span class="sxs-lookup"><span data-stu-id="8dd13-209">Endpoint Detection and Response</span></span> |<span data-ttu-id="8dd13-210">タグの設定と削除、 `GROUP` サポートのみ</span><span class="sxs-lookup"><span data-stu-id="8dd13-210">Set/Remove tag, only `GROUP` supported</span></span>        |`mdatp edr tag set --name GROUP --value [tag]`                         |
|<span data-ttu-id="8dd13-211">エンドポイントの検出と応答</span><span class="sxs-lookup"><span data-stu-id="8dd13-211">Endpoint Detection and Response</span></span> |<span data-ttu-id="8dd13-212">リストの除外 (ルート)</span><span class="sxs-lookup"><span data-stu-id="8dd13-212">list exclusions (root)</span></span>                        |`mdatp edr exclusion list [processes|paths|extensions|all]`            |

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="8dd13-213">Microsoft Defender for Endpoint ポータル情報</span><span class="sxs-lookup"><span data-stu-id="8dd13-213">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="8dd13-214">Defender for Endpoint ポータルには、次の 2 つのカテゴリの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8dd13-214">In the Defender for Endpoint portal, you'll see two categories of information:</span></span>

- <span data-ttu-id="8dd13-215">次のウイルス対策アラートを含む。</span><span class="sxs-lookup"><span data-stu-id="8dd13-215">Antivirus alerts, including:</span></span>
  - <span data-ttu-id="8dd13-216">重要度</span><span class="sxs-lookup"><span data-stu-id="8dd13-216">Severity</span></span>
  - <span data-ttu-id="8dd13-217">スキャンの種類</span><span class="sxs-lookup"><span data-stu-id="8dd13-217">Scan type</span></span>
  - <span data-ttu-id="8dd13-218">デバイス情報 (ホスト名、デバイス識別子、テナント識別子、アプリのバージョン、OS の種類)</span><span class="sxs-lookup"><span data-stu-id="8dd13-218">Device information (hostname, device identifier, tenant identifier, app version, and OS type)</span></span>
  - <span data-ttu-id="8dd13-219">ファイル情報 (名前、パス、サイズ、ハッシュ)</span><span class="sxs-lookup"><span data-stu-id="8dd13-219">File information (name, path, size, and hash)</span></span>
  - <span data-ttu-id="8dd13-220">脅威情報 (名前、種類、状態)</span><span class="sxs-lookup"><span data-stu-id="8dd13-220">Threat information (name, type, and state)</span></span>
- <span data-ttu-id="8dd13-221">次のデバイス情報を含むデバイス情報。</span><span class="sxs-lookup"><span data-stu-id="8dd13-221">Device information, including:</span></span>
  - <span data-ttu-id="8dd13-222">デバイス識別子</span><span class="sxs-lookup"><span data-stu-id="8dd13-222">Device identifier</span></span>
  - <span data-ttu-id="8dd13-223">テナント識別子</span><span class="sxs-lookup"><span data-stu-id="8dd13-223">Tenant identifier</span></span>
  - <span data-ttu-id="8dd13-224">アプリのバージョン</span><span class="sxs-lookup"><span data-stu-id="8dd13-224">App version</span></span>
  - <span data-ttu-id="8dd13-225">ホスト名</span><span class="sxs-lookup"><span data-stu-id="8dd13-225">Hostname</span></span>
  - <span data-ttu-id="8dd13-226">OS の種類</span><span class="sxs-lookup"><span data-stu-id="8dd13-226">OS type</span></span>
  - <span data-ttu-id="8dd13-227">OS のバージョン</span><span class="sxs-lookup"><span data-stu-id="8dd13-227">OS version</span></span>
  - <span data-ttu-id="8dd13-228">コンピューター モデル</span><span class="sxs-lookup"><span data-stu-id="8dd13-228">Computer model</span></span>
  - <span data-ttu-id="8dd13-229">プロセッサアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="8dd13-229">Processor architecture</span></span>
  - <span data-ttu-id="8dd13-230">デバイスが仮想マシンかどうか</span><span class="sxs-lookup"><span data-stu-id="8dd13-230">Whether the device is a virtual machine</span></span>

### <a name="known-issues"></a><span data-ttu-id="8dd13-231">既知の問題</span><span class="sxs-lookup"><span data-stu-id="8dd13-231">Known issues</span></span>

- <span data-ttu-id="8dd13-232">製品が期待通り動作している場合でも、Microsoft Defender Security Center ポータルのコンピューター情報ページに「センサー データなし、通信障害」が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="8dd13-232">You might see "No sensor data, impaired communications" in the machine information page of the Microsoft Defender Security Center portal, even though the product is working as expected.</span></span> <span data-ttu-id="8dd13-233">この問題の解決に取り組み中です。</span><span class="sxs-lookup"><span data-stu-id="8dd13-233">We are working on addressing this issue.</span></span>
- <span data-ttu-id="8dd13-234">ログオンしているユーザーは、Microsoft Defender セキュリティ センター ポータルに表示されません。</span><span class="sxs-lookup"><span data-stu-id="8dd13-234">Logged on users do not appear in the Microsoft Defender Security Center portal.</span></span>
- <span data-ttu-id="8dd13-235">SUSE ディストリビューションで *、libatomic1* のインストールが失敗した場合は、OS が登録されているのを検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8dd13-235">In SUSE distributions, if the installation of *libatomic1* fails, you should validate that your OS is registered:</span></span>

   ```bash
   sudo SUSEConnect --status-text
   ```
