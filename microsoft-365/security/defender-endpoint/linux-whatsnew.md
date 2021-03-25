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
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a>Microsoft Defender for Endpoint for Linux の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012364-30121021123640"></a>101.23.64 (30.121021.12364.0)

- マウント ポイント全体がウイルス対策除外リストに追加される状況のパフォーマンスが向上しました。 このバージョンより前のバージョンでは、マウント ポイントから発生したファイル アクティビティは、製品によって引き続き処理されました。 このバージョンでは、除外されたマウント ポイントのファイル アクティビティが抑制され、製品のパフォーマンスが向上します。
- コマンド ライン ツールに、前回のオンデマンド スキャンに関する情報を表示する新しいオプションが追加されました。 最後のオンデマンド スキャンに関する情報を表示するには、次のコマンドを実行します。 `mdatp health --details antivirus`
- バグ修正に関するその他&改善点

## <a name="1011853"></a>101.18.53

- Linux 用 EDR が一 [般提供されました](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
- カスタム スキャン中に AV の除外を無視する新しいコマンド ライン スイッチ ( `--ignore-exclusions` ) を追加しました ( `mdatp scan custom` )
- 診断ログを別のディレクトリに保存できる新しいパラメーター `mdatp diagnostic create` ( `--path [directory]` ) を使用して拡張
- バグ修正&パフォーマンスの向上

## <a name="1011299"></a>101.12.99

- バグ修正&パフォーマンスの向上

## <a name="1010476"></a>101.04.76

- バグ修正

## <a name="1010348"></a>101.03.48

- バグ修正

## <a name="1010255"></a>101.02.55

- 再起動/アップグレード後に製品が起動しない問題を修正しました
- 製品のアップグレードでプロキシ設定が保持されない問題を修正しました

## <a name="1010075"></a>101.00.75

- 次のファイル システムの種類のサポートが `ecryptfs` 追加されました。 `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf``vfat`
- コマンド ライン ツールの [新しい構文](linux-resources.md#configure-from-the-command-line)。
- バグ修正&パフォーマンスの向上

## <a name="1009070"></a>100.90.70

> [!WARNING]
> インストール済みパッケージを 100.90.70 より前の製品バージョンからアップグレードすると、Red Hat ベースおよび SLES ディストリビューションで更新が失敗する可能性があります。 これは、ファイル パスの大きな変更のためです。 一時的な解決策として、古いパッケージを削除し、新しいパッケージをインストールします。 この問題は、新しいバージョンには存在しません。

- ウイルス [対策の除外でワイルドカードがサポートされる](linux-exclusions.md#supported-exclusion-types)
- コマンド ライン ツールを使用して [パフォーマンスの問題を](linux-support-perf.md) トラブルシューティング `mdatp` する機能が追加されました
- パッケージのインストールをより堅牢にする改善点
- バグ修正&パフォーマンスの向上
