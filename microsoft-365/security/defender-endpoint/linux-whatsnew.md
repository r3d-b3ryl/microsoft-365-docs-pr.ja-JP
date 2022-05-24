---
title: Linux でのMicrosoft Defender for Endpointの新機能
description: Linux でのMicrosoft Defender for Endpointの主な変更点の一覧。
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
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: c58c447a4aed08af48576b461a638c1cd43aca83
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65649245"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a>Linux でのMicrosoft Defender for Endpointの新機能

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

## <a name="1016880-30122042168800"></a>101.68.80 (30.122042.16880.0)

- RHEL 6 で実行するときのカーネル バージョン `2.6.32-754.47.1.el6.x86_64` のサポートを追加しました
- RHEL 6 で、製品を、Unbreakable Enterprise Kernel (UEK) を実行しているデバイスにインストールできるようになりました
- 実行中と同じように `unknown` プロセス名が正しく表示されない問題を修正しました `mdatp diagnostic real-time-protection-statistics`
- 製品が検疫フォルダー内のファイルを誤って検出する場合があるバグを修正しました
- ソフト リンクとしてマウントされたときにコマンド ライン ツールが`/opt`機能しない問題`mdatp`を修正しました
- バグ修正&パフォーマンスの向上

## <a name="1016577-30122032165770"></a>101.65.77 (30.122032.16577.0)

- フィールド`mdatp health`を`conflicting_applications`改善し、最新の 10 個のプロセスのみを表示し、プロセス名を含める必要があります。 これにより、Linux のMicrosoft Defender for Endpointと競合する可能性があるプロセスを簡単に特定できます。
- バグ修正

## <a name="1016274-30122022162740"></a>101.62.74 (30.122022.16274.0)

- 以前のカーネル バージョンで実行しているときに、製品がサイズが 2 GB を超えるファイルへのアクセスを誤ってブロックする問題に対処しました
- バグ修正

## <a name="1016093-30122012160930"></a>101.60.93 (30.122012.16093.0)

- このバージョンには[、CVE-2022-23278](https://msrc-blog.microsoft.com/2022/03/08/guidance-for-cve-2022-23278-spoofing-in-microsoft-defender-for-endpoint/) のセキュリティ更新プログラムが含まれています

## <a name="1016005-30122012160050"></a>101.60.05 (30.122012.16005.0)

- RHEL 6.10 のカーネル バージョン 2.6.32-754.43.1.el6.x86_64のサポートを追加しました
- バグ修正

## <a name="1015880-30122012158800"></a>101.58.80 (30.122012.15880.0)

- コマンド ライン ツールでは、検疫されたファイルを、ファイルが最初に検出された場所以外の場所に復元できるようになりました。 これは 、 `mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`.
- このバージョン以降、Linux のネットワーク保護をオンデマンドで評価できます
- バグ修正

## <a name="1015662-30121122156620"></a>101.56.62 (30.121122.15662.0)

- 101.53.02 で発生し、複数の顧客に影響を与えた製品のクラッシュを修正しました

## <a name="1015302-30121112153020"></a>101.53.02 (30.121112.15302.0)

- バグ修正&パフォーマンスの向上

## <a name="1015257-30121092152570"></a>101.52.57 (30.121092.15257.0)

- Java アプリケーションで使用されている脆弱な log4j jar を検出する機能を追加しました。 マシンは、読み込まれた log4j jar を使用して Java プロセスを実行するために定期的に検査されます。 この情報はMicrosoft Defender for Endpoint バックエンドに報告され、ポータルの [脆弱性管理] 領域で公開されます。

## <a name="1014776-30121092147760"></a>101.47.76 (30.121092.14776.0)

- オンデマンド スキャン中にアーカイブをスキャンするかどうかを制御する新しいスイッチをコマンド ライン ツールに追加しました。 これを構成 `mdatp config scan-archives --value [enabled/disabled]`するには、 . 既定では、これは `enabled`.
- バグ修正

## <a name="1014513-30121082145130"></a>101.45.13 (30.121082.14513.0)

- このバージョン以降、次のディストリビューションにMicrosoft Defender for Endpointサポートを提供しています。 
  - RHEL6.7-6.10 および CentOS6.7-6.10 バージョン。
  - Amazon Linux 2
  - Fedora 33 以降
- バグ修正


## <a name="1014500-30121072145000"></a>101.45.00 (30.121072.14500.0)

- コマンド ライン ツールに新しいスイッチを追加しました。
  - オンデマンド スキャンの並列処理の度合いを制御します。 これを構成 `mdatp config maximum-on-demand-scan-threads --value [number-between-1-and-64]`するには、 . 既定では、ある程度の並列処理 `2` が使用されます。
  - セキュリティ インテリジェンスの更新後のスキャンを有効または無効にするかどうかを制御します。 これを構成 `mdatp config scan-after-definition-update --value [enabled/disabled]`するには、 . 既定では、これは `enabled`.
- 製品ログ レベルを変更するには、昇格が必要になりました
- バグ修正

## <a name="1013998-30121062139980"></a>101.39.98 (30.121062.13998.0)

- バグ修正&パフォーマンスの向上

## <a name="1013427-30121052134270"></a>101.34.27 (30.121052.13427.0)

- バグ修正&パフォーマンスの向上

## <a name="1012964-30121042129640"></a>101.29.64 (30.121042.12964.0)

- このバージョン以降、コマンド ライン クライアントを介してトリガーされたオンデマンドウイルス対策スキャン中に検出された脅威は自動的に修復されます。 ユーザー インターフェイスを介してトリガーされたスキャン中に検出された脅威には、手動操作が必要です。
- `mdatp diagnostic real-time-protection-statistics` 次の 2 つの追加スイッチがサポートされるようになりました。
  - `--sort`: 出力を降順に並べ替え、スキャンされたファイルの合計数で並べ替えます。
  - `--top N`: 上位 N 個の結果が表示されます (指定されている場合 `--sort` にのみ機能します)
- バグ修正&パフォーマンスの向上

## <a name="1012572-30121022125630"></a>101.25.72 (30.121022.12563.0)

- Linux 上のMicrosoft Defender for Endpointは、米国政府機関のお客様向けのプレビューで利用できるようになりました。 詳細については、「[米国政府機関のお客様向けのMicrosoft Defender for Endpoint」を参照してください](gov.md)。
- FUSE ファイルシステムを使用するシステムで Linux でMicrosoft Defender for Endpointを使用すると OS がハングする問題を修正しました
- その他のバグ修正&パフォーマンスの向上

## <a name="1012563-30121022125630"></a>101.25.63 (30.121022.12563.0)

- バグ修正&パフォーマンスの向上

## <a name="1012364-30121021123640"></a>101.23.64 (30.121021.12364.0)

- マウント ポイント全体がウイルス対策除外リストに追加される状況のパフォーマンスが向上しました。 このバージョンより前のバージョンでは、マウント ポイントから発生したファイル アクティビティは、製品によって処理されていました。 このバージョン以降、除外されたマウント ポイントのファイル アクティビティが抑制され、製品のパフォーマンスが向上します
- 最後のオンデマンド スキャンに関する情報を表示する新しいオプションをコマンド ライン ツールに追加しました。 最後のオンデマンド スキャンに関する情報を表示するには、次のコマンドを実行します。 `mdatp health --details antivirus`
- バグ修正&その他のパフォーマンスの向上

## <a name="1011853"></a>101.18.53

- EDR for Linux が[一般公開](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)されるようになりました
- カスタム スキャン中に AV 除外を無視する新しいコマンド ライン スイッチ (`--ignore-exclusions`) を追加しました (`mdatp scan custom`)
- `mdatp diagnostic create`診断ログを別のディレクトリに保存できるようにする新しいパラメーター (`--path [directory]`) で拡張
- バグ修正&パフォーマンスの向上

## <a name="1011299"></a>101.12.99

- バグ修正&パフォーマンスの向上

## <a name="1010476"></a>101.04.76

- バグ修正

## <a name="1010348"></a>101.03.48

- バグ修正

## <a name="1010255"></a>101.02.55

- 再起動/アップグレード後に製品が起動しない場合がある問題を修正しました
- 製品のアップグレード間でプロキシ設定が保持されない問題を修正しました

## <a name="1010075"></a>101.00.75

- 次のファイル システムの種類のサポートが追加されました。 `ecryptfs``fuse``fuseblk``jfs``nfs``overlay``ramfs``reiserfs``udf``vfat`
- [コマンド ライン ツール](linux-resources.md#configure-from-the-command-line)の新しい構文。
- バグ修正&パフォーマンスの向上

## <a name="1009070"></a>100.90.70

> [!WARNING]
> インストールされたパッケージを 100.90.70 より前の製品バージョンからアップグレードすると、Red Hat ベースおよび SLES ディストリビューションで更新が失敗する可能性があります。 これは、ファイル パスが大きく変更されたためです。 一時的な解決策は、古いパッケージを削除してから、新しいパッケージをインストールすることです。 この問題は、新しいバージョンには存在しません。

- ウイルス対策 [の除外でワイルドカードがサポートされるようになりました](linux-exclusions.md#supported-exclusion-types)
- コマンド ライン ツールを使用して [パフォーマンスの問題をトラブルシューティング](linux-support-perf.md) する機能を `mdatp` 追加しました
- パッケージのインストールをより堅牢にするための機能強化
- バグ修正&パフォーマンスの向上
