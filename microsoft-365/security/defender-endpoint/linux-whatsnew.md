---
title: Microsoft Defender for Endpoint on Linux の新機能
description: Microsoft Defender for Endpoint on Linux の主な変更点の一覧。
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, whatsnew, release
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
ms.openlocfilehash: 6aaf370ef0222c6c4a7f920a2a5ed8951f988839
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933567"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="dd05c-104">Microsoft Defender for Endpoint on Linux の新機能</span><span class="sxs-lookup"><span data-stu-id="dd05c-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012572-30121022125630"></a><span data-ttu-id="dd05c-105">101.25.72 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="dd05c-105">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="dd05c-106">Microsoft Defender for Endpoint on Linux は、米国政府機関のお客様向けプレビューで利用できます。</span><span class="sxs-lookup"><span data-stu-id="dd05c-106">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="dd05c-107">詳細については [、「Microsoft Defender for Endpoint for US Government customers」を参照してください](gov.md)。</span><span class="sxs-lookup"><span data-stu-id="dd05c-107">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="dd05c-108">FUSE ファイルシステムを使用するシステムで Linux 上の Microsoft Defender for Endpoint を使用すると OS がハングする問題を修正しました</span><span class="sxs-lookup"><span data-stu-id="dd05c-108">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="dd05c-109">他のバグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="dd05c-109">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="dd05c-110">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="dd05c-110">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="dd05c-111">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="dd05c-111">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="dd05c-112">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="dd05c-112">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="dd05c-113">マウント ポイント全体がウイルス対策除外リストに追加される状況のパフォーマンスが向上しました。</span><span class="sxs-lookup"><span data-stu-id="dd05c-113">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="dd05c-114">このバージョンより前のバージョンでは、マウント ポイントから発生したファイル アクティビティは、製品によって引き続き処理されました。</span><span class="sxs-lookup"><span data-stu-id="dd05c-114">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="dd05c-115">このバージョンでは、除外されたマウント ポイントのファイル アクティビティが抑制され、製品のパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="dd05c-115">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="dd05c-116">コマンド ライン ツールに、前回のオンデマンド スキャンに関する情報を表示する新しいオプションが追加されました。</span><span class="sxs-lookup"><span data-stu-id="dd05c-116">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="dd05c-117">最後のオンデマンド スキャンに関する情報を表示するには、次のコマンドを実行します。 `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="dd05c-117">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="dd05c-118">バグ修正に関するその他&改善点</span><span class="sxs-lookup"><span data-stu-id="dd05c-118">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="dd05c-119">101.18.53</span><span class="sxs-lookup"><span data-stu-id="dd05c-119">101.18.53</span></span>

- <span data-ttu-id="dd05c-120">Linux 用 EDR が一 [般提供されました](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="dd05c-120">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="dd05c-121">カスタム スキャン中に AV の除外を無視する新しいコマンド ライン スイッチ ( `--ignore-exclusions` ) を追加しました ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="dd05c-121">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="dd05c-122">診断ログを別のディレクトリに保存できる新しいパラメーター `mdatp diagnostic create` ( `--path [directory]` ) を使用して拡張</span><span class="sxs-lookup"><span data-stu-id="dd05c-122">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="dd05c-123">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="dd05c-123">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="dd05c-124">101.12.99</span><span class="sxs-lookup"><span data-stu-id="dd05c-124">101.12.99</span></span>

- <span data-ttu-id="dd05c-125">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="dd05c-125">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="dd05c-126">101.04.76</span><span class="sxs-lookup"><span data-stu-id="dd05c-126">101.04.76</span></span>

- <span data-ttu-id="dd05c-127">バグ修正</span><span class="sxs-lookup"><span data-stu-id="dd05c-127">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="dd05c-128">101.03.48</span><span class="sxs-lookup"><span data-stu-id="dd05c-128">101.03.48</span></span>

- <span data-ttu-id="dd05c-129">バグ修正</span><span class="sxs-lookup"><span data-stu-id="dd05c-129">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="dd05c-130">101.02.55</span><span class="sxs-lookup"><span data-stu-id="dd05c-130">101.02.55</span></span>

- <span data-ttu-id="dd05c-131">再起動/アップグレード後に製品が起動しない問題を修正しました</span><span class="sxs-lookup"><span data-stu-id="dd05c-131">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="dd05c-132">製品のアップグレードでプロキシ設定が保持されない問題を修正しました</span><span class="sxs-lookup"><span data-stu-id="dd05c-132">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="dd05c-133">101.00.75</span><span class="sxs-lookup"><span data-stu-id="dd05c-133">101.00.75</span></span>

- <span data-ttu-id="dd05c-134">次のファイル システムの種類のサポートが `ecryptfs` 追加されました。 `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf``vfat`</span><span class="sxs-lookup"><span data-stu-id="dd05c-134">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="dd05c-135">コマンド ライン ツールの [新しい構文](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="dd05c-135">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="dd05c-136">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="dd05c-136">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="dd05c-137">100.90.70</span><span class="sxs-lookup"><span data-stu-id="dd05c-137">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="dd05c-138">インストール済みパッケージを 100.90.70 より前の製品バージョンからアップグレードすると、Red Hat ベースおよび SLES ディストリビューションで更新が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dd05c-138">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="dd05c-139">これは、ファイル パスの大きな変更のためです。</span><span class="sxs-lookup"><span data-stu-id="dd05c-139">This is because of a major change in a file path.</span></span> <span data-ttu-id="dd05c-140">一時的な解決策として、古いパッケージを削除し、新しいパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="dd05c-140">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="dd05c-141">この問題は、新しいバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="dd05c-141">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="dd05c-142">ウイルス [対策の除外でワイルドカードがサポートされる](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="dd05c-142">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="dd05c-143">コマンド ライン ツールを使用して [パフォーマンスの問題を](linux-support-perf.md) トラブルシューティング `mdatp` する機能が追加されました</span><span class="sxs-lookup"><span data-stu-id="dd05c-143">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="dd05c-144">パッケージのインストールをより堅牢にする改善点</span><span class="sxs-lookup"><span data-stu-id="dd05c-144">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="dd05c-145">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="dd05c-145">Performance improvements & bug fixes</span></span>
