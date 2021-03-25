---
title: Microsoft Defender ATP for Mac のリソース
description: Microsoft Defender ATP for Mac のリソース (アンインストール方法、診断ログの収集方法、CLI コマンド、製品に関する既知の問題など)。
keywords: microsoft、 defender, atp, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 37d31fe93a849871e7da92fff521b6a75beac531
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187639"
---
# <a name="resources-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="ec3a8-104">Microsoft Defender for Endpoint for Mac のリソース</span><span class="sxs-lookup"><span data-stu-id="ec3a8-104">Resources for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ec3a8-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ec3a8-105">**Applies to:**</span></span>
- [<span data-ttu-id="ec3a8-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ec3a8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ec3a8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec3a8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ec3a8-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="ec3a8-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ec3a8-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a><span data-ttu-id="ec3a8-110">診断情報の収集</span><span class="sxs-lookup"><span data-stu-id="ec3a8-110">Collecting diagnostic information</span></span>

<span data-ttu-id="ec3a8-111">問題を再現できる場合は、ログ レベルを上げ、システムを一時実行し、ログ レベルを既定に復元します。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-111">If you can reproduce a problem, increase the logging level, run the system for some time, and restore the logging level to the default.</span></span>

1. <span data-ttu-id="ec3a8-112">ログ レベルを上げ:</span><span class="sxs-lookup"><span data-stu-id="ec3a8-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="ec3a8-113">問題を再現する</span><span class="sxs-lookup"><span data-stu-id="ec3a8-113">Reproduce the problem</span></span>

3. <span data-ttu-id="ec3a8-114">Microsoft `sudo mdatp diagnostic create` Defender for Endpoint ログをバックアップするために実行します。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-114">Run `sudo mdatp diagnostic create` to back up the Microsoft Defender for Endpoint logs.</span></span> <span data-ttu-id="ec3a8-115">ファイルは .zip アーカイブ内に格納されます。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-115">The files will be stored inside a .zip archive.</span></span> <span data-ttu-id="ec3a8-116">このコマンドは、操作が成功した後、バックアップへのファイル パスも出力します。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-116">This command will also print out the file path to the backup after the operation succeeds.</span></span>

   > [!TIP]
   > <span data-ttu-id="ec3a8-117">既定では、診断ログはに保存されます `/Library/Application Support/Microsoft/Defender/wdavdiag/` 。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-117">By default, diagnostic logs are saved to `/Library/Application Support/Microsoft/Defender/wdavdiag/`.</span></span> <span data-ttu-id="ec3a8-118">診断ログが保存されているディレクトリを変更するには、次のコマンドに渡し、目的の `--path [directory]` `[directory]` ディレクトリに置き換わります。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-118">To change the directory where diagnostic logs are saved, pass `--path [directory]` to the below command, replacing `[directory]` with the desired directory.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```
   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. <span data-ttu-id="ec3a8-119">ログ レベルの復元:</span><span class="sxs-lookup"><span data-stu-id="ec3a8-119">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```
   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a><span data-ttu-id="ec3a8-120">インストールの問題をログに記録する</span><span class="sxs-lookup"><span data-stu-id="ec3a8-120">Logging installation issues</span></span>

<span data-ttu-id="ec3a8-121">インストール中にエラーが発生した場合、インストーラーは一般的なエラーのみを報告します。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-121">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="ec3a8-122">詳細ログはに保存されます `/Library/Logs/Microsoft/mdatp/install.log` 。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-122">The detailed log will be saved to `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="ec3a8-123">インストール中に問題が発生した場合は、このファイルを送信して、原因の診断に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-123">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstalling"></a><span data-ttu-id="ec3a8-124">アンインストール</span><span class="sxs-lookup"><span data-stu-id="ec3a8-124">Uninstalling</span></span>

<span data-ttu-id="ec3a8-125">Microsoft Defender for Endpoint for Mac をアンインストールするには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-125">There are several ways to uninstall Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="ec3a8-126">中央管理アンインストールは JAMF で使用できるが、Microsoft Intune ではまだ利用できない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-126">Note that while centrally managed uninstall is available on JAMF, it is not yet available for Microsoft Intune.</span></span>

### <a name="interactive-uninstallation"></a><span data-ttu-id="ec3a8-127">対話型アンインストール</span><span class="sxs-lookup"><span data-stu-id="ec3a8-127">Interactive uninstallation</span></span>

- <span data-ttu-id="ec3a8-128">Finder **ファイル>開きます**。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-128">Open **Finder > Applications**.</span></span> <span data-ttu-id="ec3a8-129">Microsoft Defender ATP の **[ごみ箱に移動>を右クリックします**。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-129">Right click on **Microsoft Defender ATP > Move to Trash**.</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="ec3a8-130">コマンド ラインから</span><span class="sxs-lookup"><span data-stu-id="ec3a8-130">From the command line</span></span>

- ```sudo rm -rf '/Applications/Microsoft Defender ATP.app'```
- ```sudo rm -rf '/Library/Application Support/Microsoft/Defender/'```

## <a name="configuring-from-the-command-line"></a><span data-ttu-id="ec3a8-131">コマンド ラインからの構成</span><span class="sxs-lookup"><span data-stu-id="ec3a8-131">Configuring from the command line</span></span>

<span data-ttu-id="ec3a8-132">製品設定の制御やオンデマンド スキャンのトリガーなどの重要なタスクは、コマンド ラインから実行できます。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-132">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line:</span></span>

|<span data-ttu-id="ec3a8-133">Group</span><span class="sxs-lookup"><span data-stu-id="ec3a8-133">Group</span></span>        |<span data-ttu-id="ec3a8-134">シナリオ</span><span class="sxs-lookup"><span data-stu-id="ec3a8-134">Scenario</span></span>                                   |<span data-ttu-id="ec3a8-135">コマンド</span><span class="sxs-lookup"><span data-stu-id="ec3a8-135">Command</span></span>                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|<span data-ttu-id="ec3a8-136">構成</span><span class="sxs-lookup"><span data-stu-id="ec3a8-136">Configuration</span></span>|<span data-ttu-id="ec3a8-137">リアルタイム保護のオン/オフ</span><span class="sxs-lookup"><span data-stu-id="ec3a8-137">Turn on/off real-time protection</span></span>           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|<span data-ttu-id="ec3a8-138">構成</span><span class="sxs-lookup"><span data-stu-id="ec3a8-138">Configuration</span></span>|<span data-ttu-id="ec3a8-139">クラウド保護のオン/オフ</span><span class="sxs-lookup"><span data-stu-id="ec3a8-139">Turn on/off cloud protection</span></span>               |`mdatp config cloud --value [enabled/disabled]`                                   |
|<span data-ttu-id="ec3a8-140">構成</span><span class="sxs-lookup"><span data-stu-id="ec3a8-140">Configuration</span></span>|<span data-ttu-id="ec3a8-141">製品診断のオン/オフ</span><span class="sxs-lookup"><span data-stu-id="ec3a8-141">Turn on/off product diagnostics</span></span>            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|<span data-ttu-id="ec3a8-142">構成</span><span class="sxs-lookup"><span data-stu-id="ec3a8-142">Configuration</span></span>|<span data-ttu-id="ec3a8-143">自動サンプル申請のオン/オフ</span><span class="sxs-lookup"><span data-stu-id="ec3a8-143">Turn on/off automatic sample submission</span></span>    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|<span data-ttu-id="ec3a8-144">構成</span><span class="sxs-lookup"><span data-stu-id="ec3a8-144">Configuration</span></span>|<span data-ttu-id="ec3a8-145">許可リストに脅威名を追加する</span><span class="sxs-lookup"><span data-stu-id="ec3a8-145">Add a threat name to the allowed list</span></span>      |`mdatp threat allowed add --name [threat-name]`                                   |
|<span data-ttu-id="ec3a8-146">構成</span><span class="sxs-lookup"><span data-stu-id="ec3a8-146">Configuration</span></span>|<span data-ttu-id="ec3a8-147">許可リストから脅威名を削除する</span><span class="sxs-lookup"><span data-stu-id="ec3a8-147">Remove a threat name from the allowed list</span></span> |`mdatp threat allowed remove --name [threat-name]`                                |
|<span data-ttu-id="ec3a8-148">構成</span><span class="sxs-lookup"><span data-stu-id="ec3a8-148">Configuration</span></span>|<span data-ttu-id="ec3a8-149">許可されている脅威名の一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="ec3a8-149">List all allowed threat names</span></span>              |`mdatp threat allowed list`                                                       |
|<span data-ttu-id="ec3a8-150">構成</span><span class="sxs-lookup"><span data-stu-id="ec3a8-150">Configuration</span></span>|<span data-ttu-id="ec3a8-151">PUA 保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="ec3a8-151">Turn on PUA protection</span></span>                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|<span data-ttu-id="ec3a8-152">構成</span><span class="sxs-lookup"><span data-stu-id="ec3a8-152">Configuration</span></span>|<span data-ttu-id="ec3a8-153">PUA 保護をオフにする</span><span class="sxs-lookup"><span data-stu-id="ec3a8-153">Turn off PUA protection</span></span>                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|<span data-ttu-id="ec3a8-154">構成</span><span class="sxs-lookup"><span data-stu-id="ec3a8-154">Configuration</span></span>|<span data-ttu-id="ec3a8-155">PUA 保護の監査モードを有効にする</span><span class="sxs-lookup"><span data-stu-id="ec3a8-155">Turn on audit mode for PUA protection</span></span>      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|<span data-ttu-id="ec3a8-156">構成</span><span class="sxs-lookup"><span data-stu-id="ec3a8-156">Configuration</span></span>|<span data-ttu-id="ec3a8-157">パッシブ モードのオン/オフ</span><span class="sxs-lookup"><span data-stu-id="ec3a8-157">Turn on/off passiveMode</span></span>                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|<span data-ttu-id="ec3a8-158">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="ec3a8-158">Diagnostics</span></span>  |<span data-ttu-id="ec3a8-159">ログ レベルの変更</span><span class="sxs-lookup"><span data-stu-id="ec3a8-159">Change the log level</span></span>                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|<span data-ttu-id="ec3a8-160">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="ec3a8-160">Diagnostics</span></span>  |<span data-ttu-id="ec3a8-161">診断ログの生成</span><span class="sxs-lookup"><span data-stu-id="ec3a8-161">Generate diagnostic logs</span></span>                   |`mdatp diagnostic create --path [directory]`                                      |
|<span data-ttu-id="ec3a8-162">正常性</span><span class="sxs-lookup"><span data-stu-id="ec3a8-162">Health</span></span>       |<span data-ttu-id="ec3a8-163">製品の正常性を確認する</span><span class="sxs-lookup"><span data-stu-id="ec3a8-163">Check the product's health</span></span>                 |`mdatp health`                                                                    |
|<span data-ttu-id="ec3a8-164">正常性</span><span class="sxs-lookup"><span data-stu-id="ec3a8-164">Health</span></span>       |<span data-ttu-id="ec3a8-165">spefic 製品属性を確認する</span><span class="sxs-lookup"><span data-stu-id="ec3a8-165">Check for a spefic product attribute</span></span>       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|<span data-ttu-id="ec3a8-166">保護</span><span class="sxs-lookup"><span data-stu-id="ec3a8-166">Protection</span></span>   |<span data-ttu-id="ec3a8-167">パスをスキャンする</span><span class="sxs-lookup"><span data-stu-id="ec3a8-167">Scan a path</span></span>                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|<span data-ttu-id="ec3a8-168">保護</span><span class="sxs-lookup"><span data-stu-id="ec3a8-168">Protection</span></span>   |<span data-ttu-id="ec3a8-169">クイック スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="ec3a8-169">Do a quick scan</span></span>                            |`mdatp scan quick`                                                                |
|<span data-ttu-id="ec3a8-170">保護</span><span class="sxs-lookup"><span data-stu-id="ec3a8-170">Protection</span></span>   |<span data-ttu-id="ec3a8-171">フル スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="ec3a8-171">Do a full scan</span></span>                             |`mdatp scan full`                                                                 |
|<span data-ttu-id="ec3a8-172">保護</span><span class="sxs-lookup"><span data-stu-id="ec3a8-172">Protection</span></span>   |<span data-ttu-id="ec3a8-173">進行中のオンデマンド スキャンをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="ec3a8-173">Cancel an ongoing on-demand scan</span></span>           |`mdatp scan cancel`                                                               |
|<span data-ttu-id="ec3a8-174">保護</span><span class="sxs-lookup"><span data-stu-id="ec3a8-174">Protection</span></span>   |<span data-ttu-id="ec3a8-175">セキュリティ インテリジェンス更新プログラムの要求</span><span class="sxs-lookup"><span data-stu-id="ec3a8-175">Request a security intelligence update</span></span>     |`mdatp definitions update`                                                        |
|<span data-ttu-id="ec3a8-176">EDR</span><span class="sxs-lookup"><span data-stu-id="ec3a8-176">EDR</span></span>          |<span data-ttu-id="ec3a8-177">デバイスにグループ タグを追加します。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-177">Add group tag to device.</span></span> <span data-ttu-id="ec3a8-178">EDR タグは、デバイス グループの管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-178">EDR tags are used for managing device groups.</span></span> <span data-ttu-id="ec3a8-179">詳細については、次のページをご覧ください。 https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span><span class="sxs-lookup"><span data-stu-id="ec3a8-179">For more information, please visit https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span></span> |`mdatp edr tag set --name GROUP --value [name]` |
|<span data-ttu-id="ec3a8-180">EDR</span><span class="sxs-lookup"><span data-stu-id="ec3a8-180">EDR</span></span>          |<span data-ttu-id="ec3a8-181">デバイスからグループ タグを削除する</span><span class="sxs-lookup"><span data-stu-id="ec3a8-181">Remove group tag from device</span></span>               |`mdatp edr tag remove --tag-name [name]`                                          |
|<span data-ttu-id="ec3a8-182">EDR</span><span class="sxs-lookup"><span data-stu-id="ec3a8-182">EDR</span></span>          |<span data-ttu-id="ec3a8-183">グループ ID の追加</span><span class="sxs-lookup"><span data-stu-id="ec3a8-183">Add Group ID</span></span>                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a><span data-ttu-id="ec3a8-184">オートコンプリートを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="ec3a8-184">How to enable autocompletion</span></span>

<span data-ttu-id="ec3a8-185">bash でオートコンプリートを有効にするには、次のコマンドを実行し、ターミナル セッションを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-185">To enable autocompletion in bash, run the following command and restart the Terminal session:</span></span>

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

<span data-ttu-id="ec3a8-186">zsh でオートコンプリートを有効にするには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-186">To enable autocompletion in zsh:</span></span>

- <span data-ttu-id="ec3a8-187">デバイスでオートコンプリートが有効になっているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-187">Check whether autocompletion is enabled on your device:</span></span>

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- <span data-ttu-id="ec3a8-188">前のコマンドで出力が生成されない場合は、次のコマンドを使用してオートコンプリートを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-188">If the preceding command does not produce any output, you can enable autocompletion using the following command:</span></span>

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- <span data-ttu-id="ec3a8-189">次のコマンドを実行して、Microsoft Defender for Endpoint for Mac のオートコンプリートを有効にし、ターミナル セッションを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-189">Run the following commands to enable autocompletion for Microsoft Defender for Endpoint for Mac and restart the Terminal session:</span></span>

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a><span data-ttu-id="ec3a8-190">エンドポイント検疫ディレクトリのクライアント Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ec3a8-190">Client Microsoft Defender for Endpoint quarantine directory</span></span>

<span data-ttu-id="ec3a8-191">`/Library/Application Support/Microsoft/Defender/quarantine/` によって検疫されたファイルが含まれる `mdatp` 。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contains the files quarantined by `mdatp`.</span></span> <span data-ttu-id="ec3a8-192">ファイルの名前は、脅威の追跡 Id にちなんで指定されます。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-192">The files are named after the threat trackingId.</span></span> <span data-ttu-id="ec3a8-193">現在の trackingIds は 、 と一緒に表示されます `mdatp threat list` 。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-193">The current trackingIds is shown with `mdatp threat list`.</span></span>

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="ec3a8-194">Microsoft Defender for Endpoint ポータル情報</span><span class="sxs-lookup"><span data-stu-id="ec3a8-194">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="ec3a8-195">[macOS の EDR](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)機能が、Microsoft Defender for Endpoint ブログに届き、Microsoft Defender for Endpoint Security Center で何を期待する必要があるかについての詳細なガイダンスが提供されています。</span><span class="sxs-lookup"><span data-stu-id="ec3a8-195">[EDR capabilities for macOS have now arrived](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), on the Microsoft Defender for Endpoint blog, provides detailed guidance on what to expect in Microsoft Defender for Endpoint Security Center.</span></span>