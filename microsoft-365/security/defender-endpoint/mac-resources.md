---
title: Microsoft Defender for Endpoint on Mac のリソース
description: Microsoft Defender for Endpoint on Mac のリソース (アンインストール方法、診断ログの収集方法、CLI コマンド、製品に関する既知の問題など)。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 29e9eefdf85c80b6d3c44eba01d0df57be0193a4
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346392"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="7ed6d-104">macOS 上のエンドポイント用 Microsoft Defender のリソース</span><span class="sxs-lookup"><span data-stu-id="7ed6d-104">Resources for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7ed6d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7ed6d-105">**Applies to:**</span></span>

- [<span data-ttu-id="7ed6d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7ed6d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7ed6d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7ed6d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7ed6d-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="7ed6d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7ed6d-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a><span data-ttu-id="7ed6d-110">診断情報の収集</span><span class="sxs-lookup"><span data-stu-id="7ed6d-110">Collecting diagnostic information</span></span>

<span data-ttu-id="7ed6d-111">問題を再現できる場合は、ログ レベルを上げ、システムを一時実行し、ログ レベルを既定に復元します。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-111">If you can reproduce a problem, increase the logging level, run the system for some time, and restore the logging level to the default.</span></span>

1. <span data-ttu-id="7ed6d-112">ログ レベルを上げ:</span><span class="sxs-lookup"><span data-stu-id="7ed6d-112">Increase logging level:</span></span>

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. <span data-ttu-id="7ed6d-113">問題を再現する</span><span class="sxs-lookup"><span data-stu-id="7ed6d-113">Reproduce the problem</span></span>

3. <span data-ttu-id="7ed6d-114">Microsoft `sudo mdatp diagnostic create` Defender for Endpoint ログをバックアップするために実行します。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-114">Run `sudo mdatp diagnostic create` to back up the Microsoft Defender for Endpoint logs.</span></span> <span data-ttu-id="7ed6d-115">ファイルは、アーカイブ内に.zipされます。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-115">The files will be stored inside a .zip archive.</span></span> <span data-ttu-id="7ed6d-116">このコマンドは、操作が成功した後、バックアップへのファイル パスも出力します。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-116">This command will also print out the file path to the backup after the operation succeeds.</span></span>

   > [!TIP]
   > <span data-ttu-id="7ed6d-117">既定では、診断ログはに保存されます `/Library/Application Support/Microsoft/Defender/wdavdiag/` 。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-117">By default, diagnostic logs are saved to `/Library/Application Support/Microsoft/Defender/wdavdiag/`.</span></span> <span data-ttu-id="7ed6d-118">診断ログが保存されているディレクトリを変更するには、次のコマンドに渡し、目的の `--path [directory]` `[directory]` ディレクトリに置き換わります。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-118">To change the directory where diagnostic logs are saved, pass `--path [directory]` to the below command, replacing `[directory]` with the desired directory.</span></span>

   ```bash
   sudo mdatp diagnostic create
   ```

   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. <span data-ttu-id="7ed6d-119">ログ レベルの復元:</span><span class="sxs-lookup"><span data-stu-id="7ed6d-119">Restore logging level:</span></span>

   ```bash
   mdatp log level set --level info
   ```

   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a><span data-ttu-id="7ed6d-120">インストールの問題をログに記録する</span><span class="sxs-lookup"><span data-stu-id="7ed6d-120">Logging installation issues</span></span>

<span data-ttu-id="7ed6d-121">インストール中にエラーが発生した場合、インストーラーは一般的なエラーのみを報告します。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-121">If an error occurs during installation, the installer will only report a general failure.</span></span>

<span data-ttu-id="7ed6d-122">詳細ログはに保存されます `/Library/Logs/Microsoft/mdatp/install.log` 。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-122">The detailed log will be saved to `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="7ed6d-123">インストール中に問題が発生した場合は、このファイルを送信して、原因の診断に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-123">If you experience issues during installation, send us this file so we can help diagnose the cause.</span></span>

## <a name="uninstalling"></a><span data-ttu-id="7ed6d-124">アンインストール</span><span class="sxs-lookup"><span data-stu-id="7ed6d-124">Uninstalling</span></span>

<span data-ttu-id="7ed6d-125">macOS で Microsoft Defender for Endpoint をアンインストールするには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-125">There are several ways to uninstall Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="7ed6d-126">JAMF では一般に管理されたアンインストールは使用できませんが、このアンインストールはMicrosoft Intune。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-126">Note that while centrally managed uninstall is available on JAMF, it is not yet available for Microsoft Intune.</span></span>

### <a name="interactive-uninstallation"></a><span data-ttu-id="7ed6d-127">対話型アンインストール</span><span class="sxs-lookup"><span data-stu-id="7ed6d-127">Interactive uninstallation</span></span>

- <span data-ttu-id="7ed6d-128">Finder **ファイル>開きます**。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-128">Open **Finder > Applications**.</span></span> <span data-ttu-id="7ed6d-129">[Microsoft **Defender for Endpoint] を右クリックし>に移動します**。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-129">Right click on **Microsoft Defender for Endpoint > Move to Trash**.</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="7ed6d-130">コマンド ラインから</span><span class="sxs-lookup"><span data-stu-id="7ed6d-130">From the command line</span></span>

- ```sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'```

## <a name="configuring-from-the-command-line"></a><span data-ttu-id="7ed6d-131">コマンド ラインからの構成</span><span class="sxs-lookup"><span data-stu-id="7ed6d-131">Configuring from the command line</span></span>

<span data-ttu-id="7ed6d-132">製品設定の制御やオンデマンド スキャンのトリガーなどの重要なタスクは、コマンド ラインから実行できます。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-132">Important tasks, such as controlling product settings and triggering on-demand scans, can be done from the command line:</span></span>

|<span data-ttu-id="7ed6d-133">Group</span><span class="sxs-lookup"><span data-stu-id="7ed6d-133">Group</span></span>        |<span data-ttu-id="7ed6d-134">シナリオ</span><span class="sxs-lookup"><span data-stu-id="7ed6d-134">Scenario</span></span>                                   |<span data-ttu-id="7ed6d-135">command</span><span class="sxs-lookup"><span data-stu-id="7ed6d-135">Command</span></span>                                                                           |
|-------------|-------------------------------------------|----------------------------------------------------------------------------------|
|<span data-ttu-id="7ed6d-136">構成</span><span class="sxs-lookup"><span data-stu-id="7ed6d-136">Configuration</span></span>|<span data-ttu-id="7ed6d-137">リアルタイム保護のオン/オフ</span><span class="sxs-lookup"><span data-stu-id="7ed6d-137">Turn on/off real-time protection</span></span>           |`mdatp config real-time-protection --value [enabled/disabled]`                    |
|<span data-ttu-id="7ed6d-138">構成</span><span class="sxs-lookup"><span data-stu-id="7ed6d-138">Configuration</span></span>|<span data-ttu-id="7ed6d-139">クラウド保護のオン/オフ</span><span class="sxs-lookup"><span data-stu-id="7ed6d-139">Turn on/off cloud protection</span></span>               |`mdatp config cloud --value [enabled/disabled]`                                   |
|<span data-ttu-id="7ed6d-140">構成</span><span class="sxs-lookup"><span data-stu-id="7ed6d-140">Configuration</span></span>|<span data-ttu-id="7ed6d-141">製品診断のオン/オフ</span><span class="sxs-lookup"><span data-stu-id="7ed6d-141">Turn on/off product diagnostics</span></span>            |`mdatp config cloud-diagnostic --value [enabled/disabled]`                        |
|<span data-ttu-id="7ed6d-142">構成</span><span class="sxs-lookup"><span data-stu-id="7ed6d-142">Configuration</span></span>|<span data-ttu-id="7ed6d-143">自動サンプル申請のオン/オフ</span><span class="sxs-lookup"><span data-stu-id="7ed6d-143">Turn on/off automatic sample submission</span></span>    |`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`       |
|<span data-ttu-id="7ed6d-144">構成</span><span class="sxs-lookup"><span data-stu-id="7ed6d-144">Configuration</span></span>|<span data-ttu-id="7ed6d-145">許可リストに脅威名を追加する</span><span class="sxs-lookup"><span data-stu-id="7ed6d-145">Add a threat name to the allowed list</span></span>      |`mdatp threat allowed add --name [threat-name]`                                   |
|<span data-ttu-id="7ed6d-146">構成</span><span class="sxs-lookup"><span data-stu-id="7ed6d-146">Configuration</span></span>|<span data-ttu-id="7ed6d-147">許可リストから脅威名を削除する</span><span class="sxs-lookup"><span data-stu-id="7ed6d-147">Remove a threat name from the allowed list</span></span> |`mdatp threat allowed remove --name [threat-name]`                                |
|<span data-ttu-id="7ed6d-148">構成</span><span class="sxs-lookup"><span data-stu-id="7ed6d-148">Configuration</span></span>|<span data-ttu-id="7ed6d-149">許可されている脅威名の一覧を表示する</span><span class="sxs-lookup"><span data-stu-id="7ed6d-149">List all allowed threat names</span></span>              |`mdatp threat allowed list`                                                       |
|<span data-ttu-id="7ed6d-150">構成</span><span class="sxs-lookup"><span data-stu-id="7ed6d-150">Configuration</span></span>|<span data-ttu-id="7ed6d-151">PUA 保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="7ed6d-151">Turn on PUA protection</span></span>                     |`mdatp threat policy set --type potentially_unwanted_application -- action block` |
|<span data-ttu-id="7ed6d-152">構成</span><span class="sxs-lookup"><span data-stu-id="7ed6d-152">Configuration</span></span>|<span data-ttu-id="7ed6d-153">PUA 保護をオフにする</span><span class="sxs-lookup"><span data-stu-id="7ed6d-153">Turn off PUA protection</span></span>                    |`mdatp threat policy set --type potentially_unwanted_application -- action off`   |
|<span data-ttu-id="7ed6d-154">構成</span><span class="sxs-lookup"><span data-stu-id="7ed6d-154">Configuration</span></span>|<span data-ttu-id="7ed6d-155">PUA 保護の監査モードを有効にする</span><span class="sxs-lookup"><span data-stu-id="7ed6d-155">Turn on audit mode for PUA protection</span></span>      |`mdatp threat policy set --type potentially_unwanted_application -- action audit` |
|<span data-ttu-id="7ed6d-156">構成</span><span class="sxs-lookup"><span data-stu-id="7ed6d-156">Configuration</span></span>|<span data-ttu-id="7ed6d-157">パッシブ モードのオン/オフ</span><span class="sxs-lookup"><span data-stu-id="7ed6d-157">Turn on/off passiveMode</span></span>                    |`mdatp config passive-mode --value enabled [enabled/disabled]`                    |
|<span data-ttu-id="7ed6d-158">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="7ed6d-158">Diagnostics</span></span>  |<span data-ttu-id="7ed6d-159">ログ レベルの変更</span><span class="sxs-lookup"><span data-stu-id="7ed6d-159">Change the log level</span></span>                       |`mdatp log level set --level [error/warning/info/verbose]`                        |
|<span data-ttu-id="7ed6d-160">Diagnostics</span><span class="sxs-lookup"><span data-stu-id="7ed6d-160">Diagnostics</span></span>  |<span data-ttu-id="7ed6d-161">診断ログの生成</span><span class="sxs-lookup"><span data-stu-id="7ed6d-161">Generate diagnostic logs</span></span>                   |`mdatp diagnostic create --path [directory]`                                      |
|<span data-ttu-id="7ed6d-162">正常性</span><span class="sxs-lookup"><span data-stu-id="7ed6d-162">Health</span></span>       |<span data-ttu-id="7ed6d-163">製品の正常性を確認する</span><span class="sxs-lookup"><span data-stu-id="7ed6d-163">Check the product's health</span></span>                 |`mdatp health`                                                                    |
|<span data-ttu-id="7ed6d-164">正常性</span><span class="sxs-lookup"><span data-stu-id="7ed6d-164">Health</span></span>       |<span data-ttu-id="7ed6d-165">spefic 製品属性を確認する</span><span class="sxs-lookup"><span data-stu-id="7ed6d-165">Check for a spefic product attribute</span></span>       |`mdatp health --field [attribute: healthy/licensed/engine_version...]`            |
|<span data-ttu-id="7ed6d-166">Protection</span><span class="sxs-lookup"><span data-stu-id="7ed6d-166">Protection</span></span>   |<span data-ttu-id="7ed6d-167">パスをスキャンする</span><span class="sxs-lookup"><span data-stu-id="7ed6d-167">Scan a path</span></span>                                |`mdatp scan custom --path [path] [--ignore-exclusions]`                           |
|<span data-ttu-id="7ed6d-168">Protection</span><span class="sxs-lookup"><span data-stu-id="7ed6d-168">Protection</span></span>   |<span data-ttu-id="7ed6d-169">クイック スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="7ed6d-169">Do a quick scan</span></span>                            |`mdatp scan quick`                                                                |
|<span data-ttu-id="7ed6d-170">Protection</span><span class="sxs-lookup"><span data-stu-id="7ed6d-170">Protection</span></span>   |<span data-ttu-id="7ed6d-171">フル スキャンを実行する</span><span class="sxs-lookup"><span data-stu-id="7ed6d-171">Do a full scan</span></span>                             |`mdatp scan full`                                                                 |
|<span data-ttu-id="7ed6d-172">Protection</span><span class="sxs-lookup"><span data-stu-id="7ed6d-172">Protection</span></span>   |<span data-ttu-id="7ed6d-173">進行中のオンデマンド スキャンをキャンセルする</span><span class="sxs-lookup"><span data-stu-id="7ed6d-173">Cancel an ongoing on-demand scan</span></span>           |`mdatp scan cancel`                                                               |
|<span data-ttu-id="7ed6d-174">Protection</span><span class="sxs-lookup"><span data-stu-id="7ed6d-174">Protection</span></span>   |<span data-ttu-id="7ed6d-175">セキュリティ インテリジェンス更新プログラムの要求</span><span class="sxs-lookup"><span data-stu-id="7ed6d-175">Request a security intelligence update</span></span>     |`mdatp definitions update`                                                        |
|<span data-ttu-id="7ed6d-176">EDR</span><span class="sxs-lookup"><span data-stu-id="7ed6d-176">EDR</span></span>          |<span data-ttu-id="7ed6d-177">デバイスにグループ タグを追加します。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-177">Add group tag to device.</span></span> <span data-ttu-id="7ed6d-178">EDRタグは、デバイス グループの管理に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-178">EDR tags are used for managing device groups.</span></span> <span data-ttu-id="7ed6d-179">詳細については、次のページをご覧ください。 https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span><span class="sxs-lookup"><span data-stu-id="7ed6d-179">For more information, please visit https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups</span></span> |`mdatp edr tag set --name GROUP --value [name]` |
|<span data-ttu-id="7ed6d-180">EDR</span><span class="sxs-lookup"><span data-stu-id="7ed6d-180">EDR</span></span>          |<span data-ttu-id="7ed6d-181">デバイスからグループ タグを削除する</span><span class="sxs-lookup"><span data-stu-id="7ed6d-181">Remove group tag from device</span></span>               |`mdatp edr tag remove --tag-name [name]`                                          |
|<span data-ttu-id="7ed6d-182">EDR</span><span class="sxs-lookup"><span data-stu-id="7ed6d-182">EDR</span></span>          |<span data-ttu-id="7ed6d-183">グループ ID の追加</span><span class="sxs-lookup"><span data-stu-id="7ed6d-183">Add Group ID</span></span>                               |`mdatp edr group-ids --group-id [group]`                                          |

### <a name="how-to-enable-autocompletion"></a><span data-ttu-id="7ed6d-184">オートコンプリートを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="7ed6d-184">How to enable autocompletion</span></span>

<span data-ttu-id="7ed6d-185">bash でオートコンプリートを有効にするには、次のコマンドを実行し、ターミナル セッションを再起動します。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-185">To enable autocompletion in bash, run the following command and restart the Terminal session:</span></span>

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

<span data-ttu-id="7ed6d-186">zsh でオートコンプリートを有効にするには、次の方法を実行します。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-186">To enable autocompletion in zsh:</span></span>

- <span data-ttu-id="7ed6d-187">デバイスでオートコンプリートが有効になっているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-187">Check whether autocompletion is enabled on your device:</span></span>

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- <span data-ttu-id="7ed6d-188">前のコマンドで出力が生成されない場合は、次のコマンドを使用してオートコンプリートを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-188">If the preceding command does not produce any output, you can enable autocompletion using the following command:</span></span>

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- <span data-ttu-id="7ed6d-189">次のコマンドを実行して、macOS 上の Microsoft Defender for Endpoint のオートコンプリートを有効にし、ターミナル セッションを再起動します。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-189">Run the following commands to enable autocompletion for Microsoft Defender for Endpoint on macOS and restart the Terminal session:</span></span>

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions
   ```
   ```zsh
   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a><span data-ttu-id="7ed6d-190">エンドポイント検疫ディレクトリのクライアント Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7ed6d-190">Client Microsoft Defender for Endpoint quarantine directory</span></span>

<span data-ttu-id="7ed6d-191">`/Library/Application Support/Microsoft/Defender/quarantine/` によって検疫されたファイルが含まれる `mdatp` 。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-191">`/Library/Application Support/Microsoft/Defender/quarantine/` contains the files quarantined by `mdatp`.</span></span> <span data-ttu-id="7ed6d-192">ファイルの名前は、脅威の追跡 Id にちなんで指定されます。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-192">The files are named after the threat trackingId.</span></span> <span data-ttu-id="7ed6d-193">現在の trackingIds は 、 と一緒に表示されます `mdatp threat list` 。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-193">The current trackingIds is shown with `mdatp threat list`.</span></span>

## <a name="microsoft-defender-for-endpoint-portal-information"></a><span data-ttu-id="7ed6d-194">Microsoft Defender for Endpoint ポータル情報</span><span class="sxs-lookup"><span data-stu-id="7ed6d-194">Microsoft Defender for Endpoint portal information</span></span>

<span data-ttu-id="7ed6d-195">[EDR macOS](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)の機能が到着しました。Microsoft Defender for Endpoint ブログでは、Microsoft Defender for Endpoint Security Center で何を期待するのかについて詳細なガイダンスが提供されています。</span><span class="sxs-lookup"><span data-stu-id="7ed6d-195">[EDR capabilities for macOS have now arrived](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801), on the Microsoft Defender for Endpoint blog, provides detailed guidance on what to expect in Microsoft Defender for Endpoint Security Center.</span></span>
