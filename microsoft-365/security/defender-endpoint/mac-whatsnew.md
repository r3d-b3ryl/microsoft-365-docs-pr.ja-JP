---
title: Microsoft Defender for Endpoint on Mac の新機能
description: 以前のバージョンの Microsoft Defender for Endpoint on Mac の主な変更点について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, macos, whatsnew
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: a6415ec7d39bceeb4b68de164bbdcf6ef34755ff
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984774"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="114d6-104">Microsoft Defender for Endpoint on Mac の新機能</span><span class="sxs-lookup"><span data-stu-id="114d6-104">What's new in Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="114d6-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="114d6-105">**Applies to:**</span></span>
- [<span data-ttu-id="114d6-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="114d6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="114d6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="114d6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="114d6-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="114d6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="114d6-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="114d6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="114d6-110">macOS 11 (Big Sur) では、Microsoft Defender for Endpoint には追加の構成プロファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="114d6-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="114d6-111">以前のバージョンの macOS からアップグレードする既存の顧客の場合は、このページに記載されている追加の構成プロファイルを [必ず展開してください](mac-sysext-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="114d6-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

## <a name="1013269-20121042132690"></a><span data-ttu-id="114d6-112">101.32.69 (20.121042.13269.0)</span><span class="sxs-lookup"><span data-stu-id="114d6-112">101.32.69 (20.121042.13269.0)</span></span>

- <span data-ttu-id="114d6-113">Microsoft Defender for Endpoint および他のアプリケーションからキーチェーンに同時にアクセスすると、キーチェーンが破損する可能性がある問題に対処しました。</span><span class="sxs-lookup"><span data-stu-id="114d6-113">Addressed an issue where concurrent access to the keychain from Microsoft Defender for Endpoint and other applications can lead to keychain corruption.</span></span>

## <a name="1012964-20121042129640"></a><span data-ttu-id="114d6-114">101.29.64 (20.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="114d6-114">101.29.64 (20.121042.12964.0)</span></span>

- <span data-ttu-id="114d6-115">このバージョンから、コマンド ライン クライアントを介してトリガーされるオンデマンド ウイルス対策スキャン中に検出された脅威は自動的に修復されます。</span><span class="sxs-lookup"><span data-stu-id="114d6-115">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="114d6-116">ユーザー インターフェイスを介してトリガーされるスキャン中に検出された脅威には、手動操作が必要です。</span><span class="sxs-lookup"><span data-stu-id="114d6-116">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="114d6-117">`mdatp diagnostic real-time-protection-statistics` 2 つの追加スイッチがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="114d6-117">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="114d6-118">`--sort`: スキャンされたファイルの総数で降順に出力を並べ替える</span><span class="sxs-lookup"><span data-stu-id="114d6-118">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="114d6-119">`--top N`: 上位 N の結果を表示します (指定されている `--sort` 場合にのみ機能します)</span><span class="sxs-lookup"><span data-stu-id="114d6-119">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="114d6-120">パフォーマンスの向上 (特に YARN を使用する場合) &修正</span><span class="sxs-lookup"><span data-stu-id="114d6-120">Performance improvements (specifically for when YARN is used) & bug fixes</span></span>

## <a name="1012750-20121022127500"></a><span data-ttu-id="114d6-121">101.27.50 (20.121022.12750.0)</span><span class="sxs-lookup"><span data-stu-id="114d6-121">101.27.50 (20.121022.12750.0)</span></span>

- <span data-ttu-id="114d6-122">macOS Catalina 以前の Apple 証明書の有効期限に対応するように修正しました。</span><span class="sxs-lookup"><span data-stu-id="114d6-122">Fix to accommodate for Apple certificate expiration for macOS Catalina and earlier.</span></span> <span data-ttu-id="114d6-123">この修正プログラムは、脅威&管理 (TVM) 機能を復元します。</span><span class="sxs-lookup"><span data-stu-id="114d6-123">This fix restores Threat & Vulnerability Management (TVM) functionality.</span></span>

## <a name="1012569-20121022125690"></a><span data-ttu-id="114d6-124">101.25.69 (20.121022.12569.0)</span><span class="sxs-lookup"><span data-stu-id="114d6-124">101.25.69 (20.121022.12569.0)</span></span>

- <span data-ttu-id="114d6-125">Microsoft Defender for Endpoint on macOS は、米国政府機関のお客様向けプレビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="114d6-125">Microsoft Defender for Endpoint on macOS is now available in preview for US Government customers.</span></span> <span data-ttu-id="114d6-126">詳細については [、「Microsoft Defender for Endpoint for US Government customers」を参照してください](gov.md)。</span><span class="sxs-lookup"><span data-stu-id="114d6-126">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="114d6-127">パフォーマンスの向上 (特に、XCode Simulator アプリを使用する場合の状況) は、&修正されます。</span><span class="sxs-lookup"><span data-stu-id="114d6-127">Performance improvements (specifically for the situation when the XCode Simulator app is used) & bug fixes.</span></span>

## <a name="1012364-20121021123640"></a><span data-ttu-id="114d6-128">101.23.64 (20.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="114d6-128">101.23.64 (20.121021.12364.0)</span></span>

- <span data-ttu-id="114d6-129">コマンド ライン ツールに、前回のオンデマンド スキャンに関する情報を表示する新しいオプションが追加されました。</span><span class="sxs-lookup"><span data-stu-id="114d6-129">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="114d6-130">最後のオンデマンド スキャンに関する情報を表示するには、次のコマンドを実行します。 `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="114d6-130">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="114d6-131">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-131">Performance improvements & bug fixes</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="114d6-132">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="114d6-132">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="114d6-133">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-133">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="114d6-134">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="114d6-134">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="114d6-135">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-135">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="114d6-136">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="114d6-136">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="114d6-137">このリリースでは、古いコマンド ライン ツールの構文は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="114d6-137">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="114d6-138">新しい構文の詳細については [、「Resources」を参照してください](mac-resources.md#configuring-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="114d6-138">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="114d6-139">ネットワーク拡張機能を無効にする新しいコマンド ライン スイッチを追加 `mdatp system-extension network-filter disable` しました。</span><span class="sxs-lookup"><span data-stu-id="114d6-139">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="114d6-140">このコマンドは、Microsoft Defender for Endpoint on Mac に関連する可能性があるネットワークの問題のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="114d6-140">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint on Mac</span></span>
- <span data-ttu-id="114d6-141">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-141">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="114d6-142">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="114d6-142">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="114d6-143">バグ修正</span><span class="sxs-lookup"><span data-stu-id="114d6-143">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="114d6-144">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="114d6-144">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="114d6-145">macOS 11 Big Sur で実行する場合のエージェントの信頼性が向上しました</span><span class="sxs-lookup"><span data-stu-id="114d6-145">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="114d6-146">カスタム スキャン中に AV の除外を無視する新しいコマンド ライン スイッチ ( `--ignore-exclusions` ) を追加しました ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="114d6-146">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="114d6-147">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-147">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="114d6-148">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="114d6-148">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="114d6-149">Microsoft Defender for Endpoint がカーネル パニックに陥る macOS 11 (Big Sur) バグをトリガーした場合の条件を削除しました</span><span class="sxs-lookup"><span data-stu-id="114d6-149">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="114d6-150">Mac 11 で実行されているエンドポイント セキュリティ システム拡張機能のメモリ リークを修正しました (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="114d6-150">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="114d6-151">バグ修正</span><span class="sxs-lookup"><span data-stu-id="114d6-151">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="114d6-152">101.10.72</span><span class="sxs-lookup"><span data-stu-id="114d6-152">101.10.72</span></span>

- <span data-ttu-id="114d6-153">バグ修正</span><span class="sxs-lookup"><span data-stu-id="114d6-153">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="114d6-154">101.09.61</span><span class="sxs-lookup"><span data-stu-id="114d6-154">101.09.61</span></span>

- <span data-ttu-id="114d6-155">フィードバックを送信するオプションを無効にする [新しい管理基本設定を追加しました](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="114d6-155">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="114d6-156">[状態] メニュー アイコンに、製品設定が管理されているときに正常な状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="114d6-156">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="114d6-157">以前は、製品設定が管理者によって管理されているにもかかわらず、ステータス メニュー アイコンに警告またはエラー状態が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="114d6-157">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="114d6-158">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-158">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="114d6-159">101.09.50</span><span class="sxs-lookup"><span data-stu-id="114d6-159">101.09.50</span></span>

- <span data-ttu-id="114d6-160">この製品のバージョンは、macOS Big Sur 11 ベータ 9 で検証されています</span><span class="sxs-lookup"><span data-stu-id="114d6-160">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="114d6-161">コマンド ライン ツールの新 `mdatp` しい構文が既定の構文になります。</span><span class="sxs-lookup"><span data-stu-id="114d6-161">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="114d6-162">新しい構文の詳細については [、「Resources for Microsoft Defender for Endpoint on macOS」を参照してください。](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="114d6-162">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint on macOS](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="114d6-163">古いコマンド ライン ツールの構文は **、2021** 年 1 月 1 日に製品から削除されます。</span><span class="sxs-lookup"><span data-stu-id="114d6-163">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="114d6-164">診断ログを別のディレクトリに保存できる新しいパラメーター `mdatp diagnostic create` ( `--path [directory]` ) を使用して拡張</span><span class="sxs-lookup"><span data-stu-id="114d6-164">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="114d6-165">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-165">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="114d6-166">101.09.49</span><span class="sxs-lookup"><span data-stu-id="114d6-166">101.09.49</span></span>

- <span data-ttu-id="114d6-167">IT 管理者が管理する除外とローカル ユーザーが定義した除外を区別するためのユーザー インターフェイスの改善</span><span class="sxs-lookup"><span data-stu-id="114d6-167">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="114d6-168">オンデマンド スキャン時の CPU 使用率の向上</span><span class="sxs-lookup"><span data-stu-id="114d6-168">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="114d6-169">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-169">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="114d6-170">101.07.23</span><span class="sxs-lookup"><span data-stu-id="114d6-170">101.07.23</span></span>

- <span data-ttu-id="114d6-171">パッシブ モードとグループ ID の状態を確認するために、新しいフィールド `mdatp --health` EDR追加しました</span><span class="sxs-lookup"><span data-stu-id="114d6-171">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="114d6-172">`mdatp --health` は、将来の製品 `mdatp health` 更新プログラムに置き換えられる予定です。</span><span class="sxs-lookup"><span data-stu-id="114d6-172">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="114d6-173">自動サンプル送信がユーザー インターフェイスで管理済みとしてマークされていないバグを修正しました</span><span class="sxs-lookup"><span data-stu-id="114d6-173">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="114d6-174">ウイルス対策スキャン履歴内のアイテムの保持を制御するための新しい設定が追加されました。</span><span class="sxs-lookup"><span data-stu-id="114d6-174">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="114d6-175">これで、 [スキャン履歴内の](mac-preferences.md#antivirus-scan-history-retention-in-days) アイテムを保持する日数を指定し、スキャン履歴内のアイテムの最大数 [を指定できます。](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="114d6-175">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="114d6-176">バグ修正</span><span class="sxs-lookup"><span data-stu-id="114d6-176">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="114d6-177">101.06.63</span><span class="sxs-lookup"><span data-stu-id="114d6-177">101.06.63</span></span>

- <span data-ttu-id="114d6-178">バージョンで導入されたパフォーマンス回帰に対処しました `101.05.17` 。</span><span class="sxs-lookup"><span data-stu-id="114d6-178">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="114d6-179">この回帰は、SMB 共有にアクセスするときに一部のお客様が見たカーネル パニックを解消するための修正プログラムで導入されました。</span><span class="sxs-lookup"><span data-stu-id="114d6-179">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="114d6-180">このコード変更を元に戻し、カーネル パニックを排除する別の方法を検討しています。</span><span class="sxs-lookup"><span data-stu-id="114d6-180">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="114d6-181">101.05.17</span><span class="sxs-lookup"><span data-stu-id="114d6-181">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="114d6-182">コマンド ライン ツールの新しい拡張構文 `mdatp` に取り組む必要があります。</span><span class="sxs-lookup"><span data-stu-id="114d6-182">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="114d6-183">現在、新しい構文は Insider Fast および Insider Slow 更新チャネルの既定の構文です。</span><span class="sxs-lookup"><span data-stu-id="114d6-183">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="114d6-184">この新しい構文を使用して自分自身をfamliliarizeしてください。</span><span class="sxs-lookup"><span data-stu-id="114d6-184">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="114d6-185">新しい構文と並行して古い構文をサポートし続け、今後数か月で古い構文の廃止計画に関するより多くのコミュニケーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="114d6-185">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="114d6-186">SMB ファイル共有にアクセスするときに発生するカーネル パニックに対処しました</span><span class="sxs-lookup"><span data-stu-id="114d6-186">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="114d6-187">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-187">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="114d6-188">101.05.16</span><span class="sxs-lookup"><span data-stu-id="114d6-188">101.05.16</span></span>

- <span data-ttu-id="114d6-189">スキャンされたファイルの数を大幅に削減するクイック スキャン ロジックの改善</span><span class="sxs-lookup"><span data-stu-id="114d6-189">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="114d6-190">コマンド ライン [ツールのオート](mac-resources.md#how-to-enable-autocompletion) コンプリート サポートを追加しました</span><span class="sxs-lookup"><span data-stu-id="114d6-190">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="114d6-191">バグ修正</span><span class="sxs-lookup"><span data-stu-id="114d6-191">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="114d6-192">101.03.12</span><span class="sxs-lookup"><span data-stu-id="114d6-192">101.03.12</span></span>

- <span data-ttu-id="114d6-193">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-193">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="114d6-194">101.01.54</span><span class="sxs-lookup"><span data-stu-id="114d6-194">101.01.54</span></span>

- <span data-ttu-id="114d6-195">タイム マシンとの互換性に関する改善点</span><span class="sxs-lookup"><span data-stu-id="114d6-195">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="114d6-196">アクセシビリティの改善</span><span class="sxs-lookup"><span data-stu-id="114d6-196">Accessibility improvements</span></span>
- <span data-ttu-id="114d6-197">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-197">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="114d6-198">101.00.31</span><span class="sxs-lookup"><span data-stu-id="114d6-198">101.00.31</span></span>

- <span data-ttu-id="114d6-199">Intune ユーザー [の製品オンボーディング エクスペリエンスの向上](/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="114d6-199">Improved [product onboarding experience for Intune users](/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="114d6-200">ウイルス [対策の除外でワイルドカードがサポートされる](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="114d6-200">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="114d6-201">macOS のコンテキスト メニューからウイルス対策スキャンをトリガーする機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="114d6-201">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="114d6-202">Finder でファイルまたはフォルダーを右クリックし、[Microsoft Defender for Endpoint でスキャン **] を選択できます。**</span><span class="sxs-lookup"><span data-stu-id="114d6-202">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="114d6-203">インプレイス製品のダウングレードは、インストーラーによって明示的に許可されません。</span><span class="sxs-lookup"><span data-stu-id="114d6-203">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="114d6-204">ダウングレードする必要がある場合は、まず既存のバージョンをアンインストールし、デバイスを再構成します。</span><span class="sxs-lookup"><span data-stu-id="114d6-204">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="114d6-205">バグ修正に関するその他&改善点</span><span class="sxs-lookup"><span data-stu-id="114d6-205">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="114d6-206">100.90.27</span><span class="sxs-lookup"><span data-stu-id="114d6-206">100.90.27</span></span>

- <span data-ttu-id="114d6-207">システム全体 [の更新チャネル](mac-updates.md#set-the-channel-name) とは異なる macOS 上の Microsoft Defender for Endpoint の更新チャネルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="114d6-207">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint on macOS that is different from the system-wide update channel</span></span>
- <span data-ttu-id="114d6-208">新しい製品アイコン</span><span class="sxs-lookup"><span data-stu-id="114d6-208">New product icon</span></span>
- <span data-ttu-id="114d6-209">その他のユーザー エクスペリエンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-209">Other user experience improvements</span></span>
- <span data-ttu-id="114d6-210">バグ修正</span><span class="sxs-lookup"><span data-stu-id="114d6-210">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="114d6-211">100.86.92</span><span class="sxs-lookup"><span data-stu-id="114d6-211">100.86.92</span></span>

- <span data-ttu-id="114d6-212">タイム マシンとの互換性に関する改善点</span><span class="sxs-lookup"><span data-stu-id="114d6-212">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="114d6-213">アンインストール中に製品がすべてのファイルをクリーニングしていない問題 `/Library/Application Support/Microsoft/Defender` に対処しました</span><span class="sxs-lookup"><span data-stu-id="114d6-213">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="114d6-214">Microsoft AutoUpdate を使用して Microsoft 製品が更新された場合の製品の CPU 使用率の低下</span><span class="sxs-lookup"><span data-stu-id="114d6-214">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="114d6-215">バグ修正に関するその他&改善点</span><span class="sxs-lookup"><span data-stu-id="114d6-215">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="114d6-216">100.86.91</span><span class="sxs-lookup"><span data-stu-id="114d6-216">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="114d6-217">macOS デバイスの保護を最も完全に行い、Apple が [current – 2] より古い OS バージョンへの macOS ネイティブ セキュリティ更新プログラムの配信を停止するに合わせ、MDATP for Mac の展開と更新プログラムは macOS Sierra [10.12] ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="114d6-217">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="114d6-218">MDATP for Mac の更新プログラムと拡張機能は、バージョン Catalina [10.15]、Mojave [10.14]、High Sierra [10.13] を実行しているデバイスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="114d6-218">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="114d6-219">MDATP for Mac がシエラ [10.12] デバイスに既に展開されている場合は、保護を失うリスクを排除するために最新の macOS バージョンにアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="114d6-219">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="114d6-220">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-220">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="114d6-221">100.83.73</span><span class="sxs-lookup"><span data-stu-id="114d6-221">100.83.73</span></span>

- <span data-ttu-id="114d6-222">除外の管理、脅威の種類の設定[](mac-preferences.md#exclusion-merge-policy)の管理、および禁止[](mac-preferences.md#threat-type-settings-merge-policy)された脅威アクションに関する IT 管理者向けコントロール[の追加](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="114d6-222">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="114d6-223">デバイスでフル ディスク アクセスが有効になっていない場合は、状態メニューに警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="114d6-223">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="114d6-224">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-224">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="114d6-225">100.82.60</span><span class="sxs-lookup"><span data-stu-id="114d6-225">100.82.60</span></span>

- <span data-ttu-id="114d6-226">製品が定義の更新後に開始できない問題に対処しました。</span><span class="sxs-lookup"><span data-stu-id="114d6-226">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="114d6-227">100.80.42</span><span class="sxs-lookup"><span data-stu-id="114d6-227">100.80.42</span></span>

- <span data-ttu-id="114d6-228">バグ修正</span><span class="sxs-lookup"><span data-stu-id="114d6-228">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="114d6-229">100.79.42</span><span class="sxs-lookup"><span data-stu-id="114d6-229">100.79.42</span></span>

- <span data-ttu-id="114d6-230">Mac 上の Microsoft Defender for Endpoint がタイム マシンに干渉する場合がある問題を修正しました</span><span class="sxs-lookup"><span data-stu-id="114d6-230">Fixed an issue where Microsoft Defender for Endpoint on Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="114d6-231">バックエンド サービスとの接続をテストするためにコマンド ライン ユーティリティに新しいスイッチを追加しました</span><span class="sxs-lookup"><span data-stu-id="114d6-231">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="114d6-232">ユーザー インターフェイスで完全な脅威履歴を表示する機能が追加されました (保護履歴 **ビューからアクセス** できます)</span><span class="sxs-lookup"><span data-stu-id="114d6-232">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="114d6-233">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-233">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="114d6-234">100.72.15</span><span class="sxs-lookup"><span data-stu-id="114d6-234">100.72.15</span></span>

- <span data-ttu-id="114d6-235">バグ修正</span><span class="sxs-lookup"><span data-stu-id="114d6-235">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="114d6-236">100.70.99</span><span class="sxs-lookup"><span data-stu-id="114d6-236">100.70.99</span></span>

- <span data-ttu-id="114d6-237">一部のユーザーがリアルタイム保護が有効になっているときに macOS Catalina にアップグレードする機能に影響を与える問題に対処しました。</span><span class="sxs-lookup"><span data-stu-id="114d6-237">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="114d6-238">この散発的な問題は、Catalina アップグレード パッケージ内の Microsoft Defender for Endpoint locking ファイルが脅威のスキャン中に発生し、アップグレード シーケンスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="114d6-238">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="114d6-239">100.68.99</span><span class="sxs-lookup"><span data-stu-id="114d6-239">100.68.99</span></span>

- <span data-ttu-id="114d6-240">パッシブ モードで実行するウイルス対策機能を構成する機能 [が追加されました](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="114d6-240">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="114d6-241">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-241">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="114d6-242">100.65.28</span><span class="sxs-lookup"><span data-stu-id="114d6-242">100.65.28</span></span>

- <span data-ttu-id="114d6-243">macOS Catalina のサポートが追加されました</span><span class="sxs-lookup"><span data-stu-id="114d6-243">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="114d6-244">macOS 10.15 (Catalina) には、新しいセキュリティとプライバシーの強化が含まれている。</span><span class="sxs-lookup"><span data-stu-id="114d6-244">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="114d6-245">このバージョンでは、既定では、アプリケーションは明示的な同意なしにディスク上の特定の場所 (ドキュメント、ダウンロード、デスクトップなど) にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="114d6-245">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="114d6-246">この同意がない場合、Microsoft Defender for Endpoint はデバイスを完全に保護できません。</span><span class="sxs-lookup"><span data-stu-id="114d6-246">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="114d6-247">この同意を付与するメカニズムは、Microsoft Defender for Endpoint の展開方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="114d6-247">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="114d6-248">手動展開については、「手動展開」の「更新された手順」 [を参照](mac-install-manually.md#how-to-allow-full-disk-access) してください。</span><span class="sxs-lookup"><span data-stu-id="114d6-248">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="114d6-249">管理展開については[、「JAMF](mac-install-with-jamf.md)ベースの展開」および「Microsoft Intune展開」の更新された手順[を参照](mac-install-with-intune.md#create-system-configuration-profiles)してください。</span><span class="sxs-lookup"><span data-stu-id="114d6-249">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="114d6-250">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="114d6-250">Performance improvements & bug fixes</span></span>
