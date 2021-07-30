---
title: Microsoft Defender for Endpoint on Mac のプライバシー
description: プライバシー制御、プライバシーに影響を与えるポリシー設定を構成する方法、および Microsoft Defender for Endpoint on Mac で収集された診断データに関する情報。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, privacy, diagnostic
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 580663a2644ff19ff580cfd0b13ac60e2ef233bb
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53648161"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-macos"></a>macOS 上のエンドポイント用 Microsoft Defender のプライバシー

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft は、macOS で Microsoft Defender for Endpoint を使用する場合に、データの収集方法と使用方法について選択する必要がある情報とコントロールを提供します。

このトピックでは、製品内で使用できるプライバシーコントロール、ポリシー設定を使用してこれらのコントロールを管理する方法、および収集されるデータ イベントの詳細について説明します。

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-macos"></a>macOS 上の Microsoft Defender for Endpoint のプライバシー制御の概要

このセクションでは、Microsoft Defender for Endpoint on macOS で収集されるさまざまな種類のデータのプライバシー制御について説明します。

### <a name="diagnostic-data"></a>診断ログ

診断データは、Microsoft Defender for Endpoint を安全かつ最新の状態に保ち、問題を検出、診断、修正し、製品の改善を行う場合に使用されます。

診断データには、必須のものとオプションのものがあります。 組織のポリシー設定などのプライバシー コントロールを使用することで、必須の診断データとオプションの診断データのどちらを Microsoft に送信するかを選択することができます。

Microsoft Defender for Endpoint クライアント ソフトウェアの診断データには、次の 2 つのレベルから選択できます。

* **必須**: Microsoft Defender for Endpoint をセキュリティで保護し、最新の状態に保ち、インストールされているデバイスで期待通り実行するために必要な最小データ。

* **オプション**: Microsoft が製品の改善を行い、問題の検出、診断、修復に役立つ拡張情報を提供する追加データ。

既定では、必要な診断データだけが Microsoft に送信されます。

### <a name="cloud-delivered-protection-data"></a>クラウドによって提供される保護データ

クラウドによって提供される保護は、クラウド内の最新の保護データへのアクセスを強化し、より速く保護するために使用されます。

クラウド配信保護サービスの有効化はオプションですが、エンドポイントやネットワーク全体のマルウェアに対する重要な保護を提供しますので、強くお勧めします。

### <a name="sample-data"></a>サンプル データ

サンプル データは、Microsoft の疑わしいサンプルを送信して分析することで、製品の保護機能を向上させるために使用されます。 自動サンプル送信を有効に設定する方法はオプションです。

この機能が有効で、収集されるサンプルに個人情報が含まれている可能性がある場合は、ユーザーに同意を求めるメッセージが表示されます。

## <a name="manage-privacy-controls-with-policy-settings"></a>ポリシーの設定でプライバシー コントロールを管理します

IT 管理者の場合は、エンタープライズ レベルでこれらのコントロールを構成できます。 

前のセクションで説明したさまざまな種類のデータのプライバシー制御については、「MacOS での Microsoft Defender for Endpoint の基本設定の設定」 [で詳しく説明します](mac-preferences.md)。

新しいポリシー設定と同様に、組織でポリシー設定を広く実装する前に、構成する設定が望ましい効果を得られるか確認するために、制限された制御された環境で慎重にテストする必要があります。

## <a name="diagnostic-data-events"></a>診断データ イベント

このセクションでは、必要な診断データと見なされる内容、オプションの診断データと見なされる内容、および収集されるイベントとフィールドの説明について説明します。

### <a name="data-fields-that-are-common-for-all-events"></a>すべてのイベントで一般的なデータ フィールド
カテゴリやデータ サブタイプに関係なく、すべてのイベントに共通するイベントに関する情報があります。 

次のフィールドは、すべてのイベントで一般的と見なされます。

| Field                   | 説明 |
| ----------------------- | ----------- |
| platform                | アプリが実行されているプラットフォームの広範な分類。 Microsoft は、問題が発生している可能性のあるプラットフォームを特定して、問題の優先順位を正しく設定できます。 |
| machine_guid            | デバイスに関連付けられている一意の識別子。 Microsoft は、問題がインストールの選択セットに影響を与えるかどうか、および影響を受け取るユーザーの数を特定できます。 |
| sense_guid              | デバイスに関連付けられている一意の識別子。 Microsoft は、問題がインストールの選択セットに影響を与えるかどうか、および影響を受け取るユーザーの数を特定できます。 |
| org_id                  | デバイスが属する企業に関連付けられた一意の識別子。 Microsoft は、問題が一部の企業に影響を与えるかどうか、および影響を受け取る企業の数を特定できます。 |
| ホスト名                | ローカル デバイス名 (DNS サフィックスなし)。 Microsoft は、問題がインストールの選択セットに影響を与えるかどうか、および影響を受け取るユーザーの数を特定できます。 |
| product_guid            | 製品の一意の識別子。 Microsoft は、製品の異なる味に影響を与える問題を区別できます。 |
| app_version             | macOS アプリケーションの Microsoft Defender for Endpoint のバージョン。 Microsoft は、問題を表示している製品のバージョンを特定して、問題の優先順位を正しく設定できます。|
| sig_version             | セキュリティ インテリジェンス データベースのバージョン。 Microsoft が問題を表示しているセキュリティ インテリジェンスのバージョンを特定して、問題を正しく優先順位付けできます。 |
| supported_compressions  | アプリケーションでサポートされている圧縮アルゴリズムの一覧 (例 `['gzip']` : . Microsoft は、アプリケーションと通信するときに使用できる圧縮の種類を理解できます。 |
| release_ring            | デバイスが関連付けられているリング (Insider Fast、Insider Slow、Production など)。 Microsoft は、問題が発生している可能性のあるリリース リングを特定して、問題の優先順位を正しく設定できます。 |


### <a name="required-diagnostic-data"></a>必須診断データ

**必要な診断データ** は、Microsoft Defender for Endpoint をセキュリティで保護し、最新の状態に保ち、インストールされているデバイスで期待した通り実行するために必要な最小データです。

必要な診断データは、デバイスまたはソフトウェア構成に関連する可能性がある Microsoft Defender for Endpoint の問題を特定するのに役立ちます。 たとえば、特定のオペレーティング システム バージョンで Microsoft Defender for Endpoint 機能がクラッシュする頻度が高い場合、新しく導入された機能、または特定の Microsoft Defender for Endpoint 機能が無効になっているかどうかを判断するのに役立ちます。 必要な診断データは、Microsoft がこれらの問題の検出、診断、および修正を迅速に行い、ユーザーや組織への影響を軽減するのに役立ちます。

#### <a name="software-setup-and-inventory-data-events"></a>ソフトウェアのセットアップと在庫データ イベント

**Microsoft Defender for Endpoint のインストール/アンインストール**

収集されるフィールドは、次のとおりです。

| Field            | 説明 |
| ---------------- | ----------- |
| correlation_id   | インストールに関連付けられた一意の識別子。 |
| version          | パッケージのバージョン。 |
| severity         | メッセージの重大度 (Informational など)。 |
| code             | 操作を説明するコード。 |
| テキスト             | 製品のインストールに関連する追加情報。 |

**Microsoft Defender for Endpoint の構成**

収集されるフィールドは、次のとおりです。

| Field                                               | 説明 |
| --------------------------------------------------- | ----------- |
| antivirus_engine.enable_real_time_protection        | デバイスでリアルタイム保護が有効になっているかどうか。 |
| antivirus_engine.passive_mode                       | デバイスでパッシブ モードが有効になっているかどうか。 |
| cloud_service.enabled                               | クラウドによって提供される保護がデバイスで有効になっているかどうか。 |
| cloud_service.timeout                               | アプリケーションが Microsoft Defender for Endpoint クラウドと通信する際のタイム アウト。 |
| cloud_service.heartbeat_interval                    | 製品がクラウドに送信する連続ハートビートの間隔。 |
| cloud_service.service_uri                           | クラウドとの通信に使用される URI。 |
| cloud_service.diagnostic_level                      | デバイスの診断レベル (必須、省略可能)。 |
| cloud_service.automatic_sample_submission           | 自動サンプル提出を有効にするかどうか。 |
| cloud_service.automatic_definition_update_enabled   | 自動定義更新を有効にするかどうか。 |
| edr.early_preview                                   | デバイスを早期プレビュー機能でEDRするかどうか。 |
| edr.group_id                                        | 検出および応答コンポーネントで使用されるグループ識別子。 |
| edr.tags                                            | ユーザー定義のタグ。 |
| 機能。 \[オプションの機能名\]                  | プレビュー機能の一覧と、機能が有効かどうか。 |

#### <a name="product-and-service-usage-data-events"></a>製品とサービスの利用状況データ イベント

**セキュリティ インテリジェンス更新レポート**

収集されるフィールドは、次のとおりです。

| Field            | 説明 |
| ---------------- | ----------- |
| from_version     | 元のセキュリティ インテリジェンスバージョン。 |
| to_version       | 新しいセキュリティ インテリジェンスのバージョン。 |
| status           | 成功または失敗を示す更新プログラムの状態。 |
| using_proxy      | プロキシを使用して更新が行われたかどうか。 |
| error            | 更新に失敗した場合のエラー コード。 |
| 理由           | 更新されたファイルが送信された場合にエラー メッセージが表示されます。 |

#### <a name="product-and-service-performance-data-events"></a>製品とサービスのパフォーマンス データ イベント

**原因不明のアプリケーションの終了 (クラッシュ)**

アプリケーションが予期せず終了した場合のシステム情報とアプリケーションの状態を収集します。

収集されるフィールドは、次のとおりです。

| Field                          | 説明 |
| ------------------------------ | ----------- |
| v1_crash_count                 | クライアント コンピューターで V1 エンジン プロセスが 1 時間ごとにクラッシュした回数  |
| v2_crash_count                 | クライアント コンピューターで V2 エンジン プロセスが 1 時間ごとにクラッシュした回数  |
| EDR_crash_count                | クライアント コンピューターでEDRプロセスが 1 時間ごとにクラッシュした回数        |

**カーネル拡張機能の統計情報**

収集されるフィールドは、次のとおりです。

| Field            | 説明 |
| ---------------- | ----------- |
| version          | macOS 上のエンドポイント用 Microsoft Defender のバージョン。 |
| instance_id      | カーネル拡張機能の起動時に生成される一意の識別子。 |
| trace_level      | カーネル拡張機能のトレース レベル。 |
| サブシステム        | リアルタイム保護に使用される基になるサブシステム。 |
| ipc.connects     | カーネル拡張機能によって受信された接続要求の数。 |
| ipc.rejects      | カーネル拡張機能によって拒否された接続要求の数。 |
| ipc.connected    | カーネル拡張機能へのアクティブな接続が確立されているかどうかを指定します。 |

#### <a name="support-data"></a>サポート データ

**診断ログ**

診断ログは、フィードバック送信機能の一部としてユーザーの同意を得た場合にのみ収集されます。 次のファイルは、サポート ログの一部として収集されます。

- */Library/Logs/Microsoft/mdatp/ の下のすべてのファイル*
- MacOS 上の Microsoft Defender for Endpoint で作成および使用される */Library/Application Support/Microsoft/Defender/* の下のファイルのサブセット
- MacOS 上の Microsoft Defender for Endpoint で使用される */Library/Managed Preferences* の下のファイルのサブセット
- /Library/Logs/Microsoft/autoupdate.log
- $HOME/ライブラリ/基本設定/com.microsoft.autoupdate2.plist

### <a name="optional-diagnostic-data"></a>オプションの診断データ

**オプションの診断データは** 、Microsoft が製品の改善を行い、問題の検出、診断、修正に役立つ拡張情報を提供する追加データです。

オプションの診断データを送信するよう選択した場合は、必須の診断データも含まれています。

オプションの診断データの例には、製品構成 (デバイスで設定された除外の数など) と製品のパフォーマンス (製品のコンポーネントのパフォーマンスに関する集計メジャー) に関して Microsoft が収集するデータがあります。

#### <a name="software-setup-and-inventory-data-events"></a>ソフトウェアのセットアップと在庫データ イベント

**Microsoft Defender for Endpoint の構成**

収集されるフィールドは、次のとおりです。

| Field                                              | 説明 |
| -------------------------------------------------- | ----------- |
| connection_retry_timeout                           | クラウドとの通信時に接続の再試行が時間切れになります。 |
| file_hash_cache_maximum                            | 製品キャッシュのサイズ。 |
| crash_upload_daily_limit                           | 毎日アップロードされるクラッシュ ログの制限。 |
| antivirus_engine.exclusions[].is_directory         | スキャンからの除外がディレクトリかどうか。 |
| antivirus_engine.exclusions[].path                 | スキャンから除外されたパス。 |
| antivirus_engine.exclusions[].extension            | 拡張機能はスキャンから除外されます。 |
| antivirus_engine.exclusions[].name                 | スキャンから除外されたファイルの名前。 |
| antivirus_engine.scan_cache_maximum                | 製品キャッシュのサイズ。 |
| antivirus_engine.maximum_scan_threads              | スキャンに使用されるスレッドの最大数。 |
| antivirus_engine.threat_restoration_exclusion_time | 検疫から復元されたファイルが再び検出される前に、タイム アウトします。 |
| antivirus_engine.threat_type_settings              | 製品によるさまざまな脅威の種類の処理方法の構成。 |
| filesystem_scanner.full_scan_directory             | フル スキャン ディレクトリ。 |
| filesystem_scanner.quick_scan_directories          | クイック スキャンで使用されるディレクトリの一覧。 |
| edr.latency_mode                                   | 検出および応答コンポーネントで使用される待機時間モード。 |
| edr.proxy_address                                  | 検出および応答コンポーネントで使用されるプロキシ アドレス。 |

**Microsoft 自動更新の構成**

収集されるフィールドは、次のとおりです。

| Field                       | 説明 |
| --------------------------- | ----------- |
| how_to_check                | 製品の更新プログラムのチェック方法 (自動または手動など) を決定します。 |
| channel_name                | デバイスに関連付けられているチャネルを更新します。 |
| manifest_server             | 更新プログラムのダウンロードに使用されるサーバー。 |
| update_cache                | 更新プログラムの格納に使用されるキャッシュの場所。 |

### <a name="product-and-service-usage"></a>製品とサービスの使用

#### <a name="diagnostic-log-upload-started-report"></a>診断ログのアップロード開始レポート

収集されるフィールドは、次のとおりです。

| Field            | 説明 |
| ---------------- | ----------- |
| sha256           | サポート ログの SHA256 識別子。 |
| size             | サポート ログのサイズ。 |
| original_path    | サポート ログへのパス (常に */Library/Application Support/Microsoft/Defender/wdavdiag/ の下*)。 |
| format           | サポート ログの形式。 |

#### <a name="diagnostic-log-upload-completed-report"></a>診断ログのアップロード完了レポート

収集されるフィールドは、次のとおりです。

| Field            | 説明 |
| ---------------- | ----------- |
| request_id       | サポート ログのアップロード要求の相関関係 ID。 |
| sha256           | サポート ログの SHA256 識別子。 |
| blob_sas_uri     | アプリケーションがサポート ログをアップロードするために使用する URI。 |

#### <a name="product-and-service-performance-data-events"></a>製品とサービスのパフォーマンス データ イベント

**原因不明のアプリケーションの終了 (クラッシュ)**

原因不明のアプリケーションの終了と発生時のアプリケーションの状態。

**カーネル拡張機能の統計情報**

収集されるフィールドは、次のとおりです。

| Field                          | 説明 |
| ------------------------------ | ----------- |
| pkt_ack_timeout                | 次のプロパティは、カーネル拡張機能の起動後に発生したイベントの数を表す集計された数値です。 |
| pkt_ack_conn_timeout             | |
| ipc.ack_pkts                     | |
| ipc.nack_pkts                    | |
| ipc.send.ack_no_conn             | |
| ipc.send.nack_no_conn            | |
| ipc.send.ack_no_qsq              | |
| ipc.send.nack_no_qsq             | |
| ipc.ack.no_space                 | |
| ipc.ack.timeout                  | |
| ipc.ack.ackd_fast                | |
| ipc.ack.ackd                     | |
| ipc.recv.bad_pkt_len             | |
| ipc.recv.bad_reply_len           | |
| ipc.recv.no_waiter               | |
| ipc.recv.copy_failed             | |
| ipc.kauth.vnode.mask             | |
| ipc.kauth.vnode.read             | |
| ipc.kauth.vnode.write            | |
| ipc.kauth.vnode.exec             | |
| ipc.kauth.vnode.del              | |
| ipc.kauth.vnode.read_attr        | |
| ipc.kauth.vnode.write_attr       | |
| ipc.kauth.vnode.read_ex_attr     | |
| ipc.kauth.vnode.write_ex_attr    | |
| ipc.kauth.vnode.read_sec         | |
| ipc.kauth.vnode.write_sec        | |
| ipc.kauth.vnode.take_own         | |
| ipc.kauth.vnode.link             | |
| ipc.kauth.vnode.create           | |
| ipc.kauth.vnode.move             | |
| ipc.kauth.vnode.mount            | |
| ipc.kauth.vnode.denied           | |
| ipc.kauth.vnode.ackd_before_deadline | |
| ipc.kauth.vnode.missed_deadline  | |
| ipc.kauth.file_op.mask           | |
| ipc.kauth_file_op.open           | |
| ipc.kauth.file_op.close          | |
| ipc.kauth.file_op.close_modified | |
| ipc.kauth.file_op.move           | |
| ipc.kauth.file_op.link           | |
| ipc.kauth.file_op.exec           | |
| ipc.kauth.file_op.remove         | |
| ipc.kauth.file_op.unmount        | |
| ipc.kauth.file_op.fork           | |
| ipc.kauth.file_op.create         | |

## <a name="resources"></a>リソース

- [Microsoft におけるプライバシー](https://privacy.microsoft.com/)
