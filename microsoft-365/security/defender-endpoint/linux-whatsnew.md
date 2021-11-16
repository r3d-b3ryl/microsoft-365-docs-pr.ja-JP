---
title: Microsoft Defender for Endpoint on Linux の新機能
description: Microsoft Defender for Endpoint on Linux の主な変更点の一覧。
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, whatsnew, release
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: 379fc203c16c319b293f29d396f121dc81148bd9
ms.sourcegitcommit: d40b8c506c34a661a275f756081a27ef9ad5bf4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/16/2021
ms.locfileid: "60972038"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender for Endpoint on Linux の新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1014776-30121092147760"></a>101.47.76 (30.121092.14776.0)

- コマンド ライン ツールに新しいスイッチを追加し、オンデマンド スキャン中にアーカイブをスキャンするかどうかを制御しました。 これは、 を使用して構成できます `mdatp config scan-archives --value [enabled/disabled]` 。 既定では、 に設定されています `enabled` 。
- バグ修正

## <a name="1014513-30121082145130"></a>101.45.13 (30.121082.14513.0)

- このバージョンでは、Microsoft Defender for Endpoint のサポートを次のディストリビューションに追加しています。 
  - RHEL6.7-6.10 および CentOS6.7-6.10 バージョン。
  - Amazon Linux 2
  - Fedora 33 以上
- バグ修正


## <a name="1014500-30121072145000"></a>101.45.00 (30.121072.14500.0)

- コマンド ライン ツールに新しいスイッチを追加しました。
  - オンデマンド スキャンの並列処理の程度を制御します。 これは、 を使用して構成できます `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]` 。 既定では、並列処理の程度が `2` 使用されます。
  - セキュリティ インテリジェンス更新プログラムが有効または無効にされた後のスキャンを制御します。 これは、 を使用して構成できます `mdatp config scan-after-definition-update --value [enabled/disabled]` 。 既定では、 に設定されています `enabled` 。
- 製品ログ レベルを変更するには、昇格が必要になります。
- バグ修正

## <a name="1013998-30121062139980"></a>101.39.98 (30.121062.13998.0)

- バグ修正&パフォーマンスの向上

## <a name="1013427-30121052134270"></a>101.34.27 (30.121052.13427.0)

- バグ修正&パフォーマンスの向上

## <a name="1012964-30121042129640"></a>101.29.64 (30.121042.12964.0)

- このバージョンから、コマンド ライン クライアントを介してトリガーされるオンデマンド ウイルス対策スキャン中に検出された脅威は自動的に修復されます。 ユーザー インターフェイスを介してトリガーされるスキャン中に検出された脅威には、手動操作が必要です。
- `mdatp diagnostic real-time-protection-statistics` 2 つの追加スイッチがサポートされます。
  - `--sort`: スキャンされたファイルの総数で降順に出力を並べ替える
  - `--top N`: 上位 N の結果を表示します (指定されている `--sort` 場合にのみ機能します)
- バグ修正&パフォーマンスの向上

## <a name="1012572-30121022125630"></a>101.25.72 (30.121022.12563.0)

- Microsoft Defender for Endpoint on Linux は、米国政府機関のお客様向けプレビューで利用できます。 詳細については [、「Microsoft Defender for Endpoint for US Government customers」を参照してください](gov.md)。
- FUSE ファイルシステムを使用するシステムで Linux 上の Microsoft Defender for Endpoint を使用すると OS がハングする問題を修正しました
- 他のバグ修正&パフォーマンスの向上

## <a name="1012563-30121022125630"></a>101.25.63 (30.121022.12563.0)

- バグ修正&パフォーマンスの向上

## <a name="1012364-30121021123640"></a>101.23.64 (30.121021.12364.0)

- マウント ポイント全体がウイルス対策除外リストに追加される状況のパフォーマンスが向上しました。 このバージョンより前のバージョンでは、マウント ポイントから発生したファイル アクティビティは、製品によって引き続き処理されました。 このバージョンでは、除外されたマウント ポイントのファイル アクティビティが抑制され、製品のパフォーマンスが向上します。
- コマンド ライン ツールに、前回のオンデマンド スキャンに関する情報を表示する新しいオプションが追加されました。 最後のオンデマンド スキャンに関する情報を表示するには、次のコマンドを実行します。 `mdatp health --details antivirus`
- バグ修正に関するその他&改善点

## <a name="1011853"></a>101.18.53

- EDR Linux の一般[提供が可能](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
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
