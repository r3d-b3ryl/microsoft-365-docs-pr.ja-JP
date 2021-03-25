---
title: Microsoft Defender for Endpoint for Mac の新機能
description: 以前のバージョンの Microsoft Defender for Endpoint for Mac の主な変更点について説明します。
keywords: microsoft, defender, atp, mac, installation, macos, whatsnew
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
ms.openlocfilehash: be906baca3a54183e22fa3b4ee424a9d8fc6957a
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198695"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="6f490-104">Microsoft Defender for Endpoint for Mac の新機能</span><span class="sxs-lookup"><span data-stu-id="6f490-104">What's new in Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6f490-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6f490-105">**Applies to:**</span></span>
- [<span data-ttu-id="6f490-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6f490-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6f490-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f490-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6f490-108">Microsoft Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="6f490-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6f490-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="6f490-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> <span data-ttu-id="6f490-110">macOS 11 (Big Sur) では、Microsoft Defender for Endpoint には追加の構成プロファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="6f490-110">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="6f490-111">以前のバージョンの macOS からアップグレードする既存の顧客の場合は、このページに記載されている追加の構成プロファイルを [必ず展開してください](mac-sysext-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6f490-111">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [this page](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f490-112">macOS 10.13 (High Sierra) のサポートは、2021 年 2 月 15 日に中止されます。</span><span class="sxs-lookup"><span data-stu-id="6f490-112">Support for macOS 10.13 (High Sierra) will be discontinued on February 15th, 2021.</span></span>

## <a name="1012279-20121012122790"></a><span data-ttu-id="6f490-113">101.22.79 (20.121012.12279.0)</span><span class="sxs-lookup"><span data-stu-id="6f490-113">101.22.79 (20.121012.12279.0)</span></span>

- <span data-ttu-id="6f490-114">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-114">Performance improvements & bug fixes</span></span>

## <a name="1011988-20121011119880"></a><span data-ttu-id="6f490-115">101.19.88 (20.121011.11988.0)</span><span class="sxs-lookup"><span data-stu-id="6f490-115">101.19.88 (20.121011.11988.0)</span></span>

- <span data-ttu-id="6f490-116">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-116">Performance improvements & bug fixes</span></span>

## <a name="1011948-20120121119480"></a><span data-ttu-id="6f490-117">101.19.48 (20.120121.11948.0)</span><span class="sxs-lookup"><span data-stu-id="6f490-117">101.19.48 (20.120121.11948.0)</span></span>

> [!NOTE]
> <span data-ttu-id="6f490-118">このリリースでは、古いコマンド ライン ツールの構文は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="6f490-118">The old command-line tool syntax has been deprecated with this release.</span></span> <span data-ttu-id="6f490-119">新しい構文の詳細については [、「Resources」を参照してください](mac-resources.md#configuring-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="6f490-119">For information on the new syntax, see [Resources](mac-resources.md#configuring-from-the-command-line).</span></span>

- <span data-ttu-id="6f490-120">ネットワーク拡張機能を無効にする新しいコマンド ライン スイッチを追加 `mdatp system-extension network-filter disable` しました。</span><span class="sxs-lookup"><span data-stu-id="6f490-120">Added a new command-line switch to disable the network extension: `mdatp system-extension network-filter disable`.</span></span> <span data-ttu-id="6f490-121">このコマンドは、Microsoft Defender for Endpoint for Mac に関連する可能性があるネットワークの問題のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6f490-121">This command can be useful to troubleshoot networking issues that could be related to Microsoft Defender for Endpoint for Mac</span></span>
- <span data-ttu-id="6f490-122">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-122">Performance improvements & bug fixes</span></span>

## <a name="1011921-20120101119210"></a><span data-ttu-id="6f490-123">101.19.21 (20.120101.11921.0)</span><span class="sxs-lookup"><span data-stu-id="6f490-123">101.19.21 (20.120101.11921.0)</span></span>

- <span data-ttu-id="6f490-124">バグ修正</span><span class="sxs-lookup"><span data-stu-id="6f490-124">Bug fixes</span></span>

## <a name="1011526-20120102115260"></a><span data-ttu-id="6f490-125">101.15.26 (20.120102.11526.0)</span><span class="sxs-lookup"><span data-stu-id="6f490-125">101.15.26 (20.120102.11526.0)</span></span>

- <span data-ttu-id="6f490-126">macOS 11 Big Sur で実行する場合のエージェントの信頼性が向上しました</span><span class="sxs-lookup"><span data-stu-id="6f490-126">Improved the reliability of the agent when running on macOS 11 Big Sur</span></span>
- <span data-ttu-id="6f490-127">カスタム スキャン中に AV の除外を無視する新しいコマンド ライン スイッチ ( `--ignore-exclusions` ) を追加しました ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="6f490-127">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="6f490-128">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-128">Performance improvements & bug fixes</span></span>

## <a name="1011375-20120101113750"></a><span data-ttu-id="6f490-129">101.13.75 (20.120101.11375.0)</span><span class="sxs-lookup"><span data-stu-id="6f490-129">101.13.75 (20.120101.11375.0)</span></span>

- <span data-ttu-id="6f490-130">Microsoft Defender for Endpoint がカーネル パニックに陥る macOS 11 (Big Sur) バグをトリガーした場合の条件を削除しました</span><span class="sxs-lookup"><span data-stu-id="6f490-130">Removed conditions when Microsoft Defender for Endpoint was triggering a macOS 11 (Big Sur) bug that manifests into a kernel panic</span></span>
- <span data-ttu-id="6f490-131">Mac 11 で実行されているエンドポイント セキュリティ システム拡張機能のメモリ リークを修正しました (Big Sur)</span><span class="sxs-lookup"><span data-stu-id="6f490-131">Fixed a memory leak in the Endpoint Security system extension when running on mac 11 (Big Sur)</span></span>
- <span data-ttu-id="6f490-132">バグ修正</span><span class="sxs-lookup"><span data-stu-id="6f490-132">Bug fixes</span></span>

## <a name="1011072"></a><span data-ttu-id="6f490-133">101.10.72</span><span class="sxs-lookup"><span data-stu-id="6f490-133">101.10.72</span></span>

- <span data-ttu-id="6f490-134">バグ修正</span><span class="sxs-lookup"><span data-stu-id="6f490-134">Bug fixes</span></span>

## <a name="1010961"></a><span data-ttu-id="6f490-135">101.09.61</span><span class="sxs-lookup"><span data-stu-id="6f490-135">101.09.61</span></span>

- <span data-ttu-id="6f490-136">フィードバックを送信するオプションを無効にする [新しい管理基本設定を追加しました](mac-preferences.md#show--hide-option-to-send-feedback)</span><span class="sxs-lookup"><span data-stu-id="6f490-136">Added a new managed preference for [disabling the option to send feedback](mac-preferences.md#show--hide-option-to-send-feedback)</span></span>
- <span data-ttu-id="6f490-137">[状態] メニュー アイコンに、製品設定が管理されているときに正常な状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f490-137">Status menu icon now shows a healthy state when the product settings are managed.</span></span> <span data-ttu-id="6f490-138">以前は、製品設定が管理者によって管理されているにもかかわらず、ステータス メニュー アイコンに警告またはエラー状態が表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="6f490-138">Previously, the status menu icon was displaying a warning or error state, even though the product settings were managed by the administrator</span></span>
- <span data-ttu-id="6f490-139">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-139">Performance improvements & bug fixes</span></span>

## <a name="1010950"></a><span data-ttu-id="6f490-140">101.09.50</span><span class="sxs-lookup"><span data-stu-id="6f490-140">101.09.50</span></span>

- <span data-ttu-id="6f490-141">この製品のバージョンは、macOS Big Sur 11 ベータ 9 で検証されています</span><span class="sxs-lookup"><span data-stu-id="6f490-141">This product version has been validated on macOS Big Sur 11 beta 9</span></span>

- <span data-ttu-id="6f490-142">コマンド ライン ツールの新 `mdatp` しい構文が既定の構文になります。</span><span class="sxs-lookup"><span data-stu-id="6f490-142">The new syntax for the `mdatp` command-line tool is now the default one.</span></span> <span data-ttu-id="6f490-143">新しい構文の詳細については [、「Resources for Microsoft Defender for Endpoint for Mac」を参照してください。](mac-resources.md#configuring-from-the-command-line)</span><span class="sxs-lookup"><span data-stu-id="6f490-143">For more information on the new syntax, see [Resources for Microsoft Defender for Endpoint for Mac](mac-resources.md#configuring-from-the-command-line)</span></span>

  > [!NOTE]
  > <span data-ttu-id="6f490-144">古いコマンド ライン ツールの構文は **、2021** 年 1 月 1 日に製品から削除されます。</span><span class="sxs-lookup"><span data-stu-id="6f490-144">The old command-line tool syntax will be removed from the product on **January 1st, 2021**.</span></span>

- <span data-ttu-id="6f490-145">診断ログを別のディレクトリに保存できる新しいパラメーター `mdatp diagnostic create` ( `--path [directory]` ) を使用して拡張</span><span class="sxs-lookup"><span data-stu-id="6f490-145">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="6f490-146">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-146">Performance improvements & bug fixes</span></span>

## <a name="1010949"></a><span data-ttu-id="6f490-147">101.09.49</span><span class="sxs-lookup"><span data-stu-id="6f490-147">101.09.49</span></span>

- <span data-ttu-id="6f490-148">IT 管理者が管理する除外とローカル ユーザーが定義した除外を区別するためのユーザー インターフェイスの改善</span><span class="sxs-lookup"><span data-stu-id="6f490-148">User interface improvements to differentiate exclusions that are managed by the IT administrator versus exclusions defined by the local user</span></span>
- <span data-ttu-id="6f490-149">オンデマンド スキャン時の CPU 使用率の向上</span><span class="sxs-lookup"><span data-stu-id="6f490-149">Improved CPU utilization during on-demand scans</span></span>
- <span data-ttu-id="6f490-150">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-150">Performance improvements & bug fixes</span></span>

## <a name="1010723"></a><span data-ttu-id="6f490-151">101.07.23</span><span class="sxs-lookup"><span data-stu-id="6f490-151">101.07.23</span></span>

- <span data-ttu-id="6f490-152">パッシブ モードと EDR グループ ID の状態を確認する新しいフィールドを出力 `mdatp --health` に追加しました</span><span class="sxs-lookup"><span data-stu-id="6f490-152">Added new fields to the output of `mdatp --health` for checking the status of passive mode and the EDR group ID</span></span>

  > [!NOTE]
  > <span data-ttu-id="6f490-153">`mdatp --health` は、将来の製品 `mdatp health` 更新プログラムに置き換えられる予定です。</span><span class="sxs-lookup"><span data-stu-id="6f490-153">`mdatp --health` will be replaced with `mdatp health` in a future product update.</span></span>

- <span data-ttu-id="6f490-154">自動サンプル送信がユーザー インターフェイスで管理済みとしてマークされていないバグを修正しました</span><span class="sxs-lookup"><span data-stu-id="6f490-154">Fixed a bug where automatic sample submission was not marked as managed in the user interface</span></span>
- <span data-ttu-id="6f490-155">ウイルス対策スキャン履歴内のアイテムの保持を制御するための新しい設定が追加されました。</span><span class="sxs-lookup"><span data-stu-id="6f490-155">Added new settings for controlling the retention of items in the antivirus scan history.</span></span> <span data-ttu-id="6f490-156">これで、 [スキャン履歴内の](mac-preferences.md#antivirus-scan-history-retention-in-days) アイテムを保持する日数を指定し、スキャン履歴内のアイテムの最大数 [を指定できます。](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span><span class="sxs-lookup"><span data-stu-id="6f490-156">You can now [specify the number of days to retain items in the scan history](mac-preferences.md#antivirus-scan-history-retention-in-days) and [specify the maximum number of items in the scan history](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)</span></span>
- <span data-ttu-id="6f490-157">バグ修正</span><span class="sxs-lookup"><span data-stu-id="6f490-157">Bug fixes</span></span>

## <a name="1010663"></a><span data-ttu-id="6f490-158">101.06.63</span><span class="sxs-lookup"><span data-stu-id="6f490-158">101.06.63</span></span>

- <span data-ttu-id="6f490-159">バージョンで導入されたパフォーマンス回帰に対処しました `101.05.17` 。</span><span class="sxs-lookup"><span data-stu-id="6f490-159">Addressed a performance regression introduced in version `101.05.17`.</span></span> <span data-ttu-id="6f490-160">この回帰は、SMB 共有にアクセスするときに一部のお客様が見たカーネル パニックを解消するための修正プログラムで導入されました。</span><span class="sxs-lookup"><span data-stu-id="6f490-160">The regression was introduced with the fix to eliminate the kernel panics some customers have observed when accessing SMB shares.</span></span> <span data-ttu-id="6f490-161">このコード変更を元に戻し、カーネル パニックを排除する別の方法を検討しています。</span><span class="sxs-lookup"><span data-stu-id="6f490-161">We have reverted this code change and are investigating alternative ways to eliminate the kernel panics.</span></span>

## <a name="1010517"></a><span data-ttu-id="6f490-162">101.05.17</span><span class="sxs-lookup"><span data-stu-id="6f490-162">101.05.17</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f490-163">コマンド ライン ツールの新しい拡張構文 `mdatp` に取り組む必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f490-163">We are working on a new and enhanced syntax for the `mdatp` command-line tool.</span></span> <span data-ttu-id="6f490-164">現在、新しい構文は Insider Fast および Insider Slow 更新チャネルの既定の構文です。</span><span class="sxs-lookup"><span data-stu-id="6f490-164">The new syntax is currently the default in the Insider Fast and Insider Slow update channels.</span></span> <span data-ttu-id="6f490-165">この新しい構文を使用して自分自身をfamliliarizeしてください。</span><span class="sxs-lookup"><span data-stu-id="6f490-165">We encourage you to famliliarize yourself with this new syntax.</span></span>
> 
> <span data-ttu-id="6f490-166">新しい構文と並行して古い構文をサポートし続け、今後数か月で古い構文の廃止計画に関するより多くのコミュニケーションを提供します。</span><span class="sxs-lookup"><span data-stu-id="6f490-166">We will continue supporting the old syntax in parallel with the new syntax and will provide more communication around the deprecation plan for the old syntax in the upcoming months.</span></span>

- <span data-ttu-id="6f490-167">SMB ファイル共有にアクセスするときに発生するカーネル パニックに対処しました</span><span class="sxs-lookup"><span data-stu-id="6f490-167">Addressed a kernel panic that occurred sometimes when accessing SMB file shares</span></span>
- <span data-ttu-id="6f490-168">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-168">Performance improvements & bug fixes</span></span>

## <a name="1010516"></a><span data-ttu-id="6f490-169">101.05.16</span><span class="sxs-lookup"><span data-stu-id="6f490-169">101.05.16</span></span>

- <span data-ttu-id="6f490-170">スキャンされたファイルの数を大幅に削減するクイック スキャン ロジックの改善</span><span class="sxs-lookup"><span data-stu-id="6f490-170">Improvements to quick scan logic to significantly reduce the number of scanned files</span></span>
- <span data-ttu-id="6f490-171">コマンド ライン [ツールのオート](mac-resources.md#how-to-enable-autocompletion) コンプリート サポートを追加しました</span><span class="sxs-lookup"><span data-stu-id="6f490-171">Added [autocompletion support](mac-resources.md#how-to-enable-autocompletion) for the command-line tool</span></span>
- <span data-ttu-id="6f490-172">バグ修正</span><span class="sxs-lookup"><span data-stu-id="6f490-172">Bug fixes</span></span>

## <a name="1010312"></a><span data-ttu-id="6f490-173">101.03.12</span><span class="sxs-lookup"><span data-stu-id="6f490-173">101.03.12</span></span>

- <span data-ttu-id="6f490-174">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-174">Performance improvements & bug fixes</span></span>

## <a name="1010154"></a><span data-ttu-id="6f490-175">101.01.54</span><span class="sxs-lookup"><span data-stu-id="6f490-175">101.01.54</span></span>

- <span data-ttu-id="6f490-176">タイム マシンとの互換性に関する改善点</span><span class="sxs-lookup"><span data-stu-id="6f490-176">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="6f490-177">アクセシビリティの改善</span><span class="sxs-lookup"><span data-stu-id="6f490-177">Accessibility improvements</span></span>
- <span data-ttu-id="6f490-178">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-178">Performance improvements & bug fixes</span></span>

## <a name="1010031"></a><span data-ttu-id="6f490-179">101.00.31</span><span class="sxs-lookup"><span data-stu-id="6f490-179">101.00.31</span></span>

- <span data-ttu-id="6f490-180">Intune ユーザー [の製品オンボーディング エクスペリエンスの向上](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span><span class="sxs-lookup"><span data-stu-id="6f490-180">Improved [product onboarding experience for Intune users](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)</span></span>
- <span data-ttu-id="6f490-181">ウイルス [対策の除外でワイルドカードがサポートされる](mac-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="6f490-181">Antivirus [exclusions now support wildcards](mac-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="6f490-182">macOS のコンテキスト メニューからウイルス対策スキャンをトリガーする機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="6f490-182">Added the ability to trigger antivirus scans from the macOS contextual menu.</span></span> <span data-ttu-id="6f490-183">Finder でファイルまたはフォルダーを右クリックし、[Microsoft Defender for Endpoint でスキャン **] を選択できます。**</span><span class="sxs-lookup"><span data-stu-id="6f490-183">You can now right-click a file or a folder in Finder and select **Scan with Microsoft Defender for Endpoint**</span></span>
- <span data-ttu-id="6f490-184">インプレイス製品のダウングレードは、インストーラーによって明示的に許可されません。</span><span class="sxs-lookup"><span data-stu-id="6f490-184">In-place product downgrades are now explicitly disallowed by the installer.</span></span> <span data-ttu-id="6f490-185">ダウングレードする必要がある場合は、まず既存のバージョンをアンインストールし、デバイスを再構成します。</span><span class="sxs-lookup"><span data-stu-id="6f490-185">If you need to downgrade, first uninstall the existing version and reconfigure your device</span></span>
- <span data-ttu-id="6f490-186">バグ修正に関するその他&改善点</span><span class="sxs-lookup"><span data-stu-id="6f490-186">Other performance improvements & bug fixes</span></span>

## <a name="1009027"></a><span data-ttu-id="6f490-187">100.90.27</span><span class="sxs-lookup"><span data-stu-id="6f490-187">100.90.27</span></span>

- <span data-ttu-id="6f490-188">システム全体 [の更新チャネル](mac-updates.md#set-the-channel-name) とは異なる Microsoft Defender for Endpoint for Mac の更新チャネルを設定できます。</span><span class="sxs-lookup"><span data-stu-id="6f490-188">You can now [set an update channel](mac-updates.md#set-the-channel-name) for Microsoft Defender for Endpoint for Mac that is different from the system-wide update channel</span></span>
- <span data-ttu-id="6f490-189">新しい製品アイコン</span><span class="sxs-lookup"><span data-stu-id="6f490-189">New product icon</span></span>
- <span data-ttu-id="6f490-190">その他のユーザー エクスペリエンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-190">Other user experience improvements</span></span>
- <span data-ttu-id="6f490-191">バグ修正</span><span class="sxs-lookup"><span data-stu-id="6f490-191">Bug fixes</span></span>

## <a name="1008692"></a><span data-ttu-id="6f490-192">100.86.92</span><span class="sxs-lookup"><span data-stu-id="6f490-192">100.86.92</span></span>

- <span data-ttu-id="6f490-193">タイム マシンとの互換性に関する改善点</span><span class="sxs-lookup"><span data-stu-id="6f490-193">Improvements around compatibility with Time Machine</span></span>
- <span data-ttu-id="6f490-194">アンインストール中に製品がすべてのファイルをクリーニングしていない問題 `/Library/Application Support/Microsoft/Defender` に対処しました</span><span class="sxs-lookup"><span data-stu-id="6f490-194">Addressed an issue where the product was sometimes not cleaning all files under `/Library/Application Support/Microsoft/Defender` during uninstallation</span></span>
- <span data-ttu-id="6f490-195">Microsoft AutoUpdate を使用して Microsoft 製品が更新された場合の製品の CPU 使用率の低下</span><span class="sxs-lookup"><span data-stu-id="6f490-195">Reduced the CPU utilization of the product when Microsoft products are updated through Microsoft AutoUpdate</span></span>
- <span data-ttu-id="6f490-196">バグ修正に関するその他&改善点</span><span class="sxs-lookup"><span data-stu-id="6f490-196">Other performance improvements & bug fixes</span></span>

## <a name="1008691"></a><span data-ttu-id="6f490-197">100.86.91</span><span class="sxs-lookup"><span data-stu-id="6f490-197">100.86.91</span></span>

> [!CAUTION]
> <span data-ttu-id="6f490-198">macOS デバイスの保護を最も完全に行い、Apple が [current – 2] より古い OS バージョンへの macOS ネイティブ セキュリティ更新プログラムの配信を停止するに合わせ、MDATP for Mac の展開と更新プログラムは macOS Sierra [10.12] ではサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="6f490-198">To ensure the most complete protection for your macOS devices and in alignment with Apple stopping delivery of macOS native security updates to OS versions older than [current – 2], MDATP for Mac deployment and updates will no longer be supported on macOS Sierra [10.12].</span></span> <span data-ttu-id="6f490-199">MDATP for Mac の更新プログラムと拡張機能は、バージョン Catalina [10.15]、Mojave [10.14]、High Sierra [10.13] を実行しているデバイスに配信されます。</span><span class="sxs-lookup"><span data-stu-id="6f490-199">MDATP for Mac updates and enhancements will be delivered to devices running versions Catalina [10.15], Mojave [10.14], and High Sierra [10.13].</span></span> 
>
> <span data-ttu-id="6f490-200">MDATP for Mac がシエラ [10.12] デバイスに既に展開されている場合は、保護を失うリスクを排除するために最新の macOS バージョンにアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="6f490-200">If you already have MDATP for Mac deployed to your Sierra [10.12] devices, please upgrade to the latest macOS version to eliminate risks of losing protection.</span></span>

- <span data-ttu-id="6f490-201">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-201">Performance improvements & bug fixes</span></span>

## <a name="1008373"></a><span data-ttu-id="6f490-202">100.83.73</span><span class="sxs-lookup"><span data-stu-id="6f490-202">100.83.73</span></span>

- <span data-ttu-id="6f490-203">除外の管理、脅威の種類の設定[](mac-preferences.md#exclusion-merge-policy)の管理、および禁止[](mac-preferences.md#threat-type-settings-merge-policy)された脅威アクションに関する IT 管理者向けコントロール[の追加](mac-preferences.md#disallowed-threat-actions)</span><span class="sxs-lookup"><span data-stu-id="6f490-203">Added more controls for IT administrators around [management of exclusions](mac-preferences.md#exclusion-merge-policy), [management of threat type settings](mac-preferences.md#threat-type-settings-merge-policy), and [disallowed threat actions](mac-preferences.md#disallowed-threat-actions)</span></span>
- <span data-ttu-id="6f490-204">デバイスでフル ディスク アクセスが有効になっていない場合は、状態メニューに警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f490-204">When Full Disk Access is not enabled on the device, a warning is now displayed in the status menu</span></span>
- <span data-ttu-id="6f490-205">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-205">Performance improvements & bug fixes</span></span>

## <a name="1008260"></a><span data-ttu-id="6f490-206">100.82.60</span><span class="sxs-lookup"><span data-stu-id="6f490-206">100.82.60</span></span>

- <span data-ttu-id="6f490-207">製品が定義の更新後に開始できない問題に対処しました。</span><span class="sxs-lookup"><span data-stu-id="6f490-207">Addressed an issue where the product fails to start following a definition update.</span></span>

## <a name="1008042"></a><span data-ttu-id="6f490-208">100.80.42</span><span class="sxs-lookup"><span data-stu-id="6f490-208">100.80.42</span></span>

- <span data-ttu-id="6f490-209">バグ修正</span><span class="sxs-lookup"><span data-stu-id="6f490-209">Bug fixes</span></span>

## <a name="1007942"></a><span data-ttu-id="6f490-210">100.79.42</span><span class="sxs-lookup"><span data-stu-id="6f490-210">100.79.42</span></span>

- <span data-ttu-id="6f490-211">Microsoft Defender for Endpoint for Mac がタイム マシンに干渉する場合がある問題を修正しました</span><span class="sxs-lookup"><span data-stu-id="6f490-211">Fixed an issue where Microsoft Defender for Endpoint for Mac was sometimes interfering with Time Machine</span></span>
- <span data-ttu-id="6f490-212">バックエンド サービスとの接続をテストするためにコマンド ライン ユーティリティに新しいスイッチを追加しました</span><span class="sxs-lookup"><span data-stu-id="6f490-212">Added a new switch to the command-line utility for testing the connectivity with the backend service</span></span>
  ```bash
  mdatp connectivity test
  ```
- <span data-ttu-id="6f490-213">ユーザー インターフェイスで完全な脅威履歴を表示する機能が追加されました (保護履歴 **ビューからアクセス** できます)</span><span class="sxs-lookup"><span data-stu-id="6f490-213">Added ability to view the full threat history in the user interface (can be accessed from the **Protection history** view)</span></span>
- <span data-ttu-id="6f490-214">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-214">Performance improvements & bug fixes</span></span>

## <a name="1007215"></a><span data-ttu-id="6f490-215">100.72.15</span><span class="sxs-lookup"><span data-stu-id="6f490-215">100.72.15</span></span>

- <span data-ttu-id="6f490-216">バグ修正</span><span class="sxs-lookup"><span data-stu-id="6f490-216">Bug fixes</span></span>

## <a name="1007099"></a><span data-ttu-id="6f490-217">100.70.99</span><span class="sxs-lookup"><span data-stu-id="6f490-217">100.70.99</span></span>

- <span data-ttu-id="6f490-218">一部のユーザーがリアルタイム保護が有効になっているときに macOS Catalina にアップグレードする機能に影響を与える問題に対処しました。</span><span class="sxs-lookup"><span data-stu-id="6f490-218">Addressed an issue that impacts the ability of some users to upgrade to macOS Catalina when real-time protection is enabled.</span></span> <span data-ttu-id="6f490-219">この散発的な問題は、Catalina アップグレード パッケージ内の Microsoft Defender for Endpoint locking ファイルが脅威のスキャン中に発生し、アップグレード シーケンスでエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6f490-219">This sporadic issue was caused by Microsoft Defender for Endpoint locking files within Catalina upgrade package while scanning them for threats, which led to failures in the upgrade sequence.</span></span>

## <a name="1006899"></a><span data-ttu-id="6f490-220">100.68.99</span><span class="sxs-lookup"><span data-stu-id="6f490-220">100.68.99</span></span>

- <span data-ttu-id="6f490-221">パッシブ モードで実行するウイルス対策機能を構成する機能 [が追加されました](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="6f490-221">Added the ability to configure the antivirus functionality to run in [passive mode](mac-preferences.md#enable--disable-passive-mode)</span></span>
- <span data-ttu-id="6f490-222">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-222">Performance improvements & bug fixes</span></span>

## <a name="1006528"></a><span data-ttu-id="6f490-223">100.65.28</span><span class="sxs-lookup"><span data-stu-id="6f490-223">100.65.28</span></span>

- <span data-ttu-id="6f490-224">macOS Catalina のサポートが追加されました</span><span class="sxs-lookup"><span data-stu-id="6f490-224">Added support for macOS Catalina</span></span>

  > [!CAUTION]
  > <span data-ttu-id="6f490-225">macOS 10.15 (Catalina) には、新しいセキュリティとプライバシーの強化が含まれている。</span><span class="sxs-lookup"><span data-stu-id="6f490-225">macOS 10.15 (Catalina) contains new security and privacy enhancements.</span></span> <span data-ttu-id="6f490-226">このバージョンでは、既定では、アプリケーションは明示的な同意なしにディスク上の特定の場所 (ドキュメント、ダウンロード、デスクトップなど) にアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="6f490-226">Beginning with this version, by default, applications are not able to access certain locations on disk (such as Documents, Downloads, Desktop, etc.) without explicit consent.</span></span> <span data-ttu-id="6f490-227">この同意がない場合、Microsoft Defender for Endpoint はデバイスを完全に保護できません。</span><span class="sxs-lookup"><span data-stu-id="6f490-227">In the absence of this consent, Microsoft Defender for Endpoint is not able to fully protect your device.</span></span>
  >
  > <span data-ttu-id="6f490-228">この同意を付与するメカニズムは、Microsoft Defender for Endpoint の展開方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6f490-228">The mechanism for granting this consent depends on how you deployed Microsoft Defender for Endpoint:</span></span>
  >
  > - <span data-ttu-id="6f490-229">手動展開については、「手動展開」の「更新された手順」 [を参照](mac-install-manually.md#how-to-allow-full-disk-access) してください。</span><span class="sxs-lookup"><span data-stu-id="6f490-229">For manual deployments, see the updated instructions in the [Manual deployment](mac-install-manually.md#how-to-allow-full-disk-access) topic.</span></span>
  > - <span data-ttu-id="6f490-230">管理展開については [、「JAMF](mac-install-with-jamf.md) ベースの展開」および「Microsoft Intune ベースの展開に関するトピック」の更新 [された手順を参照](mac-install-with-intune.md#create-system-configuration-profiles) してください。</span><span class="sxs-lookup"><span data-stu-id="6f490-230">For managed deployments, see the updated instructions in the [JAMF-based deployment](mac-install-with-jamf.md) and [Microsoft Intune-based deployment](mac-install-with-intune.md#create-system-configuration-profiles) topics.</span></span>

- <span data-ttu-id="6f490-231">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="6f490-231">Performance improvements & bug fixes</span></span>