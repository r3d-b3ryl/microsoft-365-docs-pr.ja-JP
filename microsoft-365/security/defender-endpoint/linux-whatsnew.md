---
title: Microsoft Defender for Endpoint for Linux の新機能
description: Microsoft Defender ATP for Linux の主な変更点の一覧。
keywords: microsoft, defender, atp, linux, whatsnew, release
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
ms.openlocfilehash: dc3d775aced2ea3da42312cbf5a4d5e5af9fae50
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198779"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="38f23-104">Microsoft Defender for Endpoint for Linux の新機能</span><span class="sxs-lookup"><span data-stu-id="38f23-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012364-30121021123640"></a><span data-ttu-id="38f23-105">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="38f23-105">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="38f23-106">マウント ポイント全体がウイルス対策除外リストに追加される状況のパフォーマンスが向上しました。</span><span class="sxs-lookup"><span data-stu-id="38f23-106">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="38f23-107">このバージョンより前のバージョンでは、マウント ポイントから発生したファイル アクティビティは、製品によって引き続き処理されました。</span><span class="sxs-lookup"><span data-stu-id="38f23-107">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="38f23-108">このバージョンでは、除外されたマウント ポイントのファイル アクティビティが抑制され、製品のパフォーマンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="38f23-108">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="38f23-109">コマンド ライン ツールに、前回のオンデマンド スキャンに関する情報を表示する新しいオプションが追加されました。</span><span class="sxs-lookup"><span data-stu-id="38f23-109">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="38f23-110">最後のオンデマンド スキャンに関する情報を表示するには、次のコマンドを実行します。 `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="38f23-110">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="38f23-111">バグ修正に関するその他&改善点</span><span class="sxs-lookup"><span data-stu-id="38f23-111">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="38f23-112">101.18.53</span><span class="sxs-lookup"><span data-stu-id="38f23-112">101.18.53</span></span>

- <span data-ttu-id="38f23-113">Linux 用 EDR が一 [般提供されました](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="38f23-113">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="38f23-114">カスタム スキャン中に AV の除外を無視する新しいコマンド ライン スイッチ ( `--ignore-exclusions` ) を追加しました ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="38f23-114">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="38f23-115">診断ログを別のディレクトリに保存できる新しいパラメーター `mdatp diagnostic create` ( `--path [directory]` ) を使用して拡張</span><span class="sxs-lookup"><span data-stu-id="38f23-115">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="38f23-116">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="38f23-116">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="38f23-117">101.12.99</span><span class="sxs-lookup"><span data-stu-id="38f23-117">101.12.99</span></span>

- <span data-ttu-id="38f23-118">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="38f23-118">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="38f23-119">101.04.76</span><span class="sxs-lookup"><span data-stu-id="38f23-119">101.04.76</span></span>

- <span data-ttu-id="38f23-120">バグ修正</span><span class="sxs-lookup"><span data-stu-id="38f23-120">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="38f23-121">101.03.48</span><span class="sxs-lookup"><span data-stu-id="38f23-121">101.03.48</span></span>

- <span data-ttu-id="38f23-122">バグ修正</span><span class="sxs-lookup"><span data-stu-id="38f23-122">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="38f23-123">101.02.55</span><span class="sxs-lookup"><span data-stu-id="38f23-123">101.02.55</span></span>

- <span data-ttu-id="38f23-124">再起動/アップグレード後に製品が起動しない問題を修正しました</span><span class="sxs-lookup"><span data-stu-id="38f23-124">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="38f23-125">製品のアップグレードでプロキシ設定が保持されない問題を修正しました</span><span class="sxs-lookup"><span data-stu-id="38f23-125">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="38f23-126">101.00.75</span><span class="sxs-lookup"><span data-stu-id="38f23-126">101.00.75</span></span>

- <span data-ttu-id="38f23-127">次のファイル システムの種類のサポートが `ecryptfs` 追加されました。 `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf``vfat`</span><span class="sxs-lookup"><span data-stu-id="38f23-127">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="38f23-128">コマンド ライン ツールの [新しい構文](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="38f23-128">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="38f23-129">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="38f23-129">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="38f23-130">100.90.70</span><span class="sxs-lookup"><span data-stu-id="38f23-130">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="38f23-131">インストール済みパッケージを 100.90.70 より前の製品バージョンからアップグレードすると、Red Hat ベースおよび SLES ディストリビューションで更新が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="38f23-131">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="38f23-132">これは、ファイル パスの大きな変更のためです。</span><span class="sxs-lookup"><span data-stu-id="38f23-132">This is because of a major change in a file path.</span></span> <span data-ttu-id="38f23-133">一時的な解決策として、古いパッケージを削除し、新しいパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="38f23-133">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="38f23-134">この問題は、新しいバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="38f23-134">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="38f23-135">ウイルス [対策の除外でワイルドカードがサポートされる](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="38f23-135">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="38f23-136">コマンド ライン ツールを使用して [パフォーマンスの問題を](linux-support-perf.md) トラブルシューティング `mdatp` する機能が追加されました</span><span class="sxs-lookup"><span data-stu-id="38f23-136">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="38f23-137">パッケージのインストールをより堅牢にする改善点</span><span class="sxs-lookup"><span data-stu-id="38f23-137">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="38f23-138">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="38f23-138">Performance improvements & bug fixes</span></span>
