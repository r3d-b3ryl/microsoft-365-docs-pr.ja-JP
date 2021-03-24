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
ms.openlocfilehash: 43324b0f3a0d5d351d7164bb05415899bf7d181c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062451"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="09b19-104">Microsoft Defender for Endpoint for Linux の新機能</span><span class="sxs-lookup"><span data-stu-id="09b19-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1011853"></a><span data-ttu-id="09b19-105">101.18.53</span><span class="sxs-lookup"><span data-stu-id="09b19-105">101.18.53</span></span>

- <span data-ttu-id="09b19-106">Linux 用 EDR が一 [般提供されました](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="09b19-106">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="09b19-107">カスタム スキャン中に AV の除外を無視する新しいコマンド ライン スイッチ ( `--ignore-exclusions` ) を追加しました ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="09b19-107">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="09b19-108">診断ログを別のディレクトリに保存できる新しいパラメーター `mdatp diagnostic create` ( `--path [directory]` ) を使用して拡張</span><span class="sxs-lookup"><span data-stu-id="09b19-108">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="09b19-109">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="09b19-109">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="09b19-110">101.12.99</span><span class="sxs-lookup"><span data-stu-id="09b19-110">101.12.99</span></span>

- <span data-ttu-id="09b19-111">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="09b19-111">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="09b19-112">101.04.76</span><span class="sxs-lookup"><span data-stu-id="09b19-112">101.04.76</span></span>

- <span data-ttu-id="09b19-113">バグ修正</span><span class="sxs-lookup"><span data-stu-id="09b19-113">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="09b19-114">101.03.48</span><span class="sxs-lookup"><span data-stu-id="09b19-114">101.03.48</span></span>

- <span data-ttu-id="09b19-115">バグ修正</span><span class="sxs-lookup"><span data-stu-id="09b19-115">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="09b19-116">101.02.55</span><span class="sxs-lookup"><span data-stu-id="09b19-116">101.02.55</span></span>

- <span data-ttu-id="09b19-117">再起動/アップグレード後に製品が起動しない問題を修正しました</span><span class="sxs-lookup"><span data-stu-id="09b19-117">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="09b19-118">製品のアップグレードでプロキシ設定が保持されない問題を修正しました</span><span class="sxs-lookup"><span data-stu-id="09b19-118">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="09b19-119">101.00.75</span><span class="sxs-lookup"><span data-stu-id="09b19-119">101.00.75</span></span>

- <span data-ttu-id="09b19-120">次のファイル システムの種類のサポートが `ecryptfs` 追加されました。 `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf``vfat`</span><span class="sxs-lookup"><span data-stu-id="09b19-120">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="09b19-121">コマンド ライン ツールの [新しい構文](linux-resources.md#configure-from-the-command-line)。</span><span class="sxs-lookup"><span data-stu-id="09b19-121">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="09b19-122">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="09b19-122">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="09b19-123">100.90.70</span><span class="sxs-lookup"><span data-stu-id="09b19-123">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="09b19-124">インストール済みパッケージを 100.90.70 より前の製品バージョンからアップグレードすると、Red Hat ベースおよび SLES ディストリビューションで更新が失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="09b19-124">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="09b19-125">これは、ファイル パスの大きな変更のためです。</span><span class="sxs-lookup"><span data-stu-id="09b19-125">This is because of a major change in a file path.</span></span> <span data-ttu-id="09b19-126">一時的な解決策として、古いパッケージを削除し、新しいパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="09b19-126">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="09b19-127">この問題は、新しいバージョンには存在しません。</span><span class="sxs-lookup"><span data-stu-id="09b19-127">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="09b19-128">ウイルス [対策の除外でワイルドカードがサポートされる](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="09b19-128">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="09b19-129">コマンド ライン ツールを使用して [パフォーマンスの問題を](linux-support-perf.md) トラブルシューティング `mdatp` する機能が追加されました</span><span class="sxs-lookup"><span data-stu-id="09b19-129">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="09b19-130">パッケージのインストールをより堅牢にする改善点</span><span class="sxs-lookup"><span data-stu-id="09b19-130">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="09b19-131">バグ修正&パフォーマンスの向上</span><span class="sxs-lookup"><span data-stu-id="09b19-131">Performance improvements & bug fixes</span></span>
