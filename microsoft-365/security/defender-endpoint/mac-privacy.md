---
title: Mac でのMicrosoft Defender for Endpointのプライバシー
description: プライバシー制御、Mac 上のMicrosoft Defender for Endpointで収集された診断データに関するプライバシーと情報に影響を与えるポリシー設定を構成する方法。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, privacy, diagnostic
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c49a6ff1440c7a3eee2e26eef90fb928e68458d1
ms.sourcegitcommit: 6c57f1e90339d5a95c9e7875599dac9d3e032c3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2022
ms.locfileid: "62365899"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-macos"></a>macOS でのMicrosoft Defender for Endpointのプライバシー

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft は、macOS でMicrosoft Defender for Endpointを使用するときにデータの収集方法と使用方法を選択するために必要な情報と制御を提供することに専念しています。

このトピックでは、製品内で使用できるプライバシー制御、ポリシー設定を使用してこれらのコントロールを管理する方法、および収集されるデータ イベントの詳細について説明します。

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-macos"></a>macOS でのMicrosoft Defender for Endpointのプライバシー制御の概要

このセクションでは、macOS 上のMicrosoft Defender for Endpointによって収集されるさまざまな種類のデータのプライバシー制御について説明します。

### <a name="diagnostic-data"></a>診断ログ

診断データは、Microsoft Defender for Endpointセキュリティと最新の状態を維持し、問題を検出、診断、修正し、製品の改善にも使用されます。

診断データには、必須のものとオプションのものがあります。 組織のポリシー設定などのプライバシー コントロールを使用することで、必須の診断データとオプションの診断データのどちらを Microsoft に送信するかを選択することができます。

Microsoft Defender for Endpoint クライアント ソフトウェアの診断データには、次の 2 つのレベルがあります。

- **必須**: インストールされているデバイスで、Microsoft Defender for Endpointセキュリティで保護され、最新の状態に保ち、期待どおりに動作するために必要な最小限のデータ。

- **省略可能**: Microsoft が製品の改善に役立ち、問題の検出、診断、修復に役立つ強化された情報を提供する追加データ。

既定では、必要な診断データのみが Microsoft に送信されます。

### <a name="cloud-delivered-protection-data"></a>クラウド配信の保護データ

クラウド配信保護は、クラウド内の最新の保護データにアクセスして、保護を強化し、より迅速に提供するために使用されます。

クラウド配信保護サービスを有効にすることは省略可能ですが、エンドポイントやネットワーク全体のマルウェアに対する重要な保護を提供するため、強くお勧めします。

### <a name="sample-data"></a>サンプル データ

サンプル データは、分析できるように Microsoft の疑わしいサンプルを送信することで、製品の保護機能を向上させるために使用されます。 サンプルの自動送信を有効にすることは省略可能です。

この機能が有効になっていて、収集されたサンプルに個人情報が含まれている可能性がある場合は、ユーザーに同意を求めるメッセージが表示されます。

## <a name="manage-privacy-controls-with-policy-settings"></a>ポリシーの設定でプライバシー コントロールを管理します

IT 管理者の場合は、エンタープライズ レベルでこれらのコントロールを構成できます。

前のセクションで説明したさまざまな種類のデータのプライバシー制御については、「[macOS でのMicrosoft Defender for Endpointの基本設定の設定](mac-preferences.md)」で詳しく説明しています。

新しいポリシー設定と同様に、組織でポリシー設定をより広く実装する前に、構成する設定が目的の効果を持っていることを確認するために、制限された制御された環境で慎重にテストする必要があります。

## <a name="diagnostic-data-events"></a>診断データ イベント

このセクションでは、必要な診断データと見なされるものと、省略可能な診断データと見なされるものと、収集されるイベントとフィールドの説明について説明します。

### <a name="data-fields-that-are-common-for-all-events"></a>すべてのイベントに共通するデータ フィールド

カテゴリやデータ サブタイプに関係なく、すべてのイベントに共通するイベントに関する情報があります。

次のフィールドは、すべてのイベントで共通と見なされます。

|フィールド|説明|
|---|---|
|platform|アプリが実行されているプラットフォームの広範な分類。 Microsoft は、問題が発生している可能性のあるプラットフォームを特定し、正しく優先順位を付けることができます。|
|machine_guid|デバイスに関連付けられている一意の識別子。 Microsoft は、問題が一連のインストールに影響を与えているかどうか、および影響を受けるユーザーの数を特定できます。|
|sense_guid|デバイスに関連付けられている一意の識別子。 Microsoft は、問題が一連のインストールに影響を与えているかどうか、および影響を受けるユーザーの数を特定できます。|
|org_id|デバイスが属するエンタープライズに関連付けられている一意の識別子。 Microsoft は、問題が一連の企業に影響を与えているかどうか、および影響を受ける企業の数を特定できます。|
|ホスト|ローカル デバイス名 (DNS サフィックスなし)。 Microsoft は、問題が一連のインストールに影響を与えているかどうか、および影響を受けるユーザーの数を特定できます。|
|product_guid|製品の一意の識別子。 Microsoft は、製品のさまざまなフレーバーに影響を与える問題を区別できます。|
|app_version|macOS アプリケーション上のMicrosoft Defender for Endpointのバージョン。 正しく優先順位を付けることができるように、問題が表示されている製品のバージョンを Microsoft が特定できるようにします。|
|sig_version|セキュリティ インテリジェンス データベースのバージョン。 Microsoft は、どのバージョンのセキュリティ インテリジェンスに問題が表示されているかを特定し、正しく優先順位を付けることができます。|
|supported_compressions|たとえば、アプリケーションでサポートされている圧縮アルゴリズムの `['gzip']`一覧。 Microsoft は、アプリケーションと通信するときに使用できる圧縮の種類を理解できます。|
|release_ring|デバイスが関連付けられているリング (Insider Fast、Insider Slow、Production など)。 Microsoft は、どのリリース リングで問題が発生している可能性があるかを特定し、正しく優先順位を付けることができます。|

### <a name="required-diagnostic-data"></a>必須診断データ

**必要な診断データ** は、Microsoft Defender for Endpointセキュリティで保護され、最新の状態に保ち、インストールされているデバイスで期待どおりに実行するために必要な最小限のデータです。

必要な診断データは、デバイスまたはソフトウェアの構成に関連する可能性があるMicrosoft Defender for Endpointに関する問題を特定するのに役立ちます。 たとえば、特定のオペレーティング システム のバージョン、新しく導入された機能、または特定のMicrosoft Defender for Endpoint機能が無効になっている場合に、Microsoft Defender for Endpoint機能がより頻繁にクラッシュするかどうかを判断するのに役立ちます。 必要な診断データは、Microsoft がこれらの問題をより迅速に検出、診断、修正し、ユーザーや組織への影響を軽減するのに役立ちます。

#### <a name="software-setup-and-inventory-data-events"></a>ソフトウェアのセットアップと在庫データ イベント

**Microsoft Defender for Endpointインストール/アンインストール**:

収集されるフィールドは、次のとおりです。

|フィールド|説明|
|---|---|
|correlation_id|インストールに関連付けられている一意の識別子。|
|version|パッケージのバージョン。|
|severity|メッセージの重大度 (Informational など)。|
|code|操作を記述するコード。|
|テキスト|製品のインストールに関連する追加情報。|

**Microsoft Defender for Endpoint構成**:

収集されるフィールドは、次のとおりです。

|フィールド|説明|
|---|---|
|antivirus_engine.enable_real_time_protection|デバイスでリアルタイム保護が有効になっているかどうか。|
|antivirus_engine.passive_mode|デバイスでパッシブ モードが有効になっているかどうか。|
|cloud_service.enabled|クラウド配信保護がデバイスで有効になっているかどうか。|
|cloud_service.timeout|アプリケーションがMicrosoft Defender for Endpoint クラウドと通信するときにタイムアウトします。|
|cloud_service.heartbeat_interval|製品からクラウドに送信される連続したハートビート間の間隔。|
|cloud_service.service_uri|クラウドとの通信に使用される URI。|
|cloud_service.diagnostic_level|デバイスの診断レベル (必須、省略可能)。|
|cloud_service.automatic_sample_submission|サンプルの自動送信を有効にするかどうか。|
|cloud_service.automatic_definition_update_enabled|定義の自動更新が有効になっているかどうか。|
|edr.early_preview|デバイスが早期プレビュー機能EDR実行する必要があるかどうか。|
|edr.group_id|検出コンポーネントと応答コンポーネントによって使用されるグループ識別子。|
|edr.tags|ユーザー定義タグ。|
|機能。\[オプションの機能名\]|プレビュー機能の一覧と、それらが有効になっているかどうか。|

#### <a name="product-and-service-usage-data-events"></a>製品とサービスの利用状況データ イベント

**セキュリティ インテリジェンス更新プログラム レポート**:

収集されるフィールドは、次のとおりです。

|フィールド|説明|
|---|---|
|from_version|元のセキュリティ インテリジェンス バージョン。|
|to_version|新しいセキュリティ インテリジェンス バージョン。|
|status|成功または失敗を示す更新プログラムの状態。|
|using_proxy|プロキシ経由で更新が行われたかどうか。|
|error|更新に失敗した場合のエラー コード。|
|理由|更新されたファイルが送信された場合のエラー メッセージ。|

#### <a name="product-and-service-performance-data-events-for-required-diagnostic-data"></a>必要な診断データの製品とサービスのパフォーマンス データ イベント

**予期しないアプリケーション終了 (クラッシュ)**:

アプリケーションが予期せず終了したときに、システム情報とアプリケーションの状態を収集します。

収集されるフィールドは、次のとおりです。

|フィールド|説明|
|---|---|
|v1_crash_count|クライアント マシンで 1 時間ごとに V1 エンジン プロセスがクラッシュした回数|
|v2_crash_count|クライアント マシンで 1 時間ごとに V2 エンジン プロセスがクラッシュした回数|
|EDR_crash_count|クライアント コンピューター EDRプロセスが 1 時間ごとにクラッシュした回数|

**カーネル拡張機能の統計**:

収集されるフィールドは、次のとおりです。

|フィールド|説明|
|---|---|
|version|macOS でのMicrosoft Defender for Endpointのバージョン。|
|instance_id|カーネル拡張機能の起動時に生成される一意の識別子。|
|trace_level|カーネル拡張機能のトレース レベル。|
|サブシステム|リアルタイム保護に使用される基になるサブシステム。|
|ipc.connects|カーネル拡張機能によって受信された接続要求の数。|
|ipc.rejects|カーネル拡張機能によって拒否された接続要求の数。|
|ipc.connected|カーネル拡張機能へのアクティブな接続があるかどうかを示します。|

#### <a name="support-data"></a>データをサポートする

**診断ログ**:

診断ログは、フィードバック送信機能の一部としてユーザーの同意を得た場合にのみ収集されます。 次のファイルは、サポート ログの一部として収集されます。

- */Library/Logs/Microsoft/mdatp/* の下のすべてのファイル
- macOS 上のMicrosoft Defender for Endpointによって作成および使用される */Library/Application Support/Microsoft/Defender/* の下のファイルのサブセット
- macOS 上のMicrosoft Defender for Endpointによって使用される */Library/Managed Preferences* の下のファイルのサブセット
- /Library/Logs/Microsoft/autoupdate.log
- $HOME/Library/Preferences/com.microsoft.autoupdate2.plist

### <a name="optional-diagnostic-data"></a>オプションの診断データ

**オプションの診断データ** は、Microsoft が製品の改善に役立つ追加データであり、問題の検出、診断、修正に役立つ強化された情報を提供します。

オプションの診断データを送信するよう選択した場合は、必須の診断データも含まれています。

オプションの診断データの例には、Microsoft が製品構成に関して収集するデータ (デバイスに設定された除外の数など) と製品のパフォーマンス (製品のコンポーネントのパフォーマンスに関する集計メジャー) が含まれます。

#### <a name="software-setup-and-inventory-data-events-for-optional-diagnostic-data"></a>オプションの診断データのソフトウェアセットアップとインベントリ データ イベント

**Microsoft Defender for Endpoint構成**:

収集されるフィールドは、次のとおりです。

|フィールド|説明|
|---|---|
|connection_retry_timeout|接続の再試行は、クラウドとの通信時にタイムアウトします。|
|file_hash_cache_maximum|製品キャッシュのサイズ。|
|crash_upload_daily_limit|毎日アップロードされるクラッシュ ログの制限。|
|antivirus_engine.exclusions[].is_directory|スキャンからの除外がディレクトリかどうか。|
|antivirus_engine.exclusions[].path|スキャンから除外されたパス。|
|antivirus_engine.exclusions[].extension|スキャンから除外された拡張機能。|
|antivirus_engine.exclusions[].name|スキャンから除外されたファイルの名前。|
|antivirus_engine.scan_cache_maximum|製品キャッシュのサイズ。|
|antivirus_engine.maximum_scan_threads|スキャンに使用されるスレッドの最大数。|
|antivirus_engine.threat_restoration_exclusion_time|検疫から復元されたファイルを再度検出する前にタイムアウトします。|
|antivirus_engine.threat_type_settings|製品によって異なる脅威の種類がどのように処理されるかに関する構成。|
|filesystem_scanner.full_scan_directory|フル スキャン ディレクトリ。|
|filesystem_scanner.quick_scan_directories|クイック スキャンで使用されるディレクトリの一覧。|
|edr.latency_mode|検出コンポーネントと応答コンポーネントによって使用される待機時間モード。|
|edr.proxy_address|検出および応答コンポーネントで使用されるプロキシ アドレス。|

**Microsoft 自動更新の構成**:

収集されるフィールドは、次のとおりです。

|フィールド|説明|
|---|---|
|how_to_check|製品の更新プログラムのチェック方法 (自動や手動など) を決定します。|
|channel_name|デバイスに関連付けられているチャネルを更新します。|
|manifest_server|更新プログラムのダウンロードに使用されるサーバー。|
|update_cache|更新プログラムの格納に使用されるキャッシュの場所。|

### <a name="product-and-service-usage"></a>製品とサービスの使用

#### <a name="diagnostic-log-upload-started-report"></a>診断ログのアップロードが開始されたレポート

収集されるフィールドは、次のとおりです。

|フィールド|説明|
|---|---|
|sha256|サポート ログの SHA256 識別子。|
|サイズ|サポート ログのサイズ。|
|original_path|サポート ログへのパス (常に */Library/Application Support/Microsoft/Defender/wdavdiag/* の下)。|
|format|サポート ログの形式。|
|metadata|サポート ログの内容に関する情報。|

#### <a name="diagnostic-log-upload-completed-report"></a>診断ログのアップロード完了レポート

収集されるフィールドは、次のとおりです。

|フィールド|説明|
|---|---|
|request_id|サポート ログアップロード要求の関連付け ID。|
|sha256|サポート ログの SHA256 識別子。|
|blob_sas_uri|サポート ログをアップロードするためにアプリケーションが使用する URI。|

#### <a name="product-and-service-performance-data-events-for-product-and-service-usage"></a>製品とサービスの使用状況に関する製品とサービスのパフォーマンス データ イベント

**予期しないアプリケーション終了 (クラッシュ)**:

原因不明のアプリケーションの終了とその発生時のアプリケーションの状態。

**カーネル拡張機能の統計**:

収集されるフィールドは、次のとおりです。

|フィールド|説明|
|---|---|
|pkt_ack_timeout|次のプロパティは集計された数値であり、カーネル拡張機能の起動以降に発生したイベントの数を表します。|
|pkt_ack_conn_timeout||
|ipc.ack_pkts||
|ipc.nack_pkts||
|ipc.send.ack_no_conn||
|ipc.send.nack_no_conn||
|ipc.send.ack_no_qsq||
|ipc.send.nack_no_qsq||
|ipc.ack.no_space||
|ipc.ack.timeout||
|ipc.ack.ackd_fast||
|ipc.ack.ackd||
|ipc.recv.bad_pkt_len||
|ipc.recv.bad_reply_len||
|ipc.recv.no_waiter||
|ipc.recv.copy_failed||
|ipc.kauth.vnode.mask||
|ipc.kauth.vnode.read||
|ipc.kauth.vnode.write||
|ipc.kauth.vnode.exec||
|ipc.kauth.vnode.del||
|ipc.kauth.vnode.read_attr||
|ipc.kauth.vnode.write_attr||
|ipc.kauth.vnode.read_ex_attr||
|ipc.kauth.vnode.write_ex_attr||
|ipc.kauth.vnode.read_sec||
|ipc.kauth.vnode.write_sec||
|ipc.kauth.vnode.take_own||
|ipc.kauth.vnode.link||
|ipc.kauth.vnode.create||
|ipc.kauth.vnode.move||
|ipc.kauth.vnode.mount||
|ipc.kauth.vnode.denied||
|ipc.kauth.vnode.ackd_before_deadline||
|ipc.kauth.vnode.missed_deadline||
|ipc.kauth.file_op.mask||
|ipc.kauth_file_op.open||
|ipc.kauth.file_op.close||
|ipc.kauth.file_op.close_modified||
|ipc.kauth.file_op.move||
|ipc.kauth.file_op.link||
|ipc.kauth.file_op.exec||
|ipc.kauth.file_op.remove||
|ipc.kauth.file_op.unmount||
|ipc.kauth.file_op.fork||
|ipc.kauth.file_op.create||

## <a name="resources"></a>リソース

- [Microsoft におけるプライバシー](https://privacy.microsoft.com/)
