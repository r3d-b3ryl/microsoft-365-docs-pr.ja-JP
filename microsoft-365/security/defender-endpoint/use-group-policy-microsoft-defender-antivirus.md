---
title: グループ ポリシー Microsoft Defender ウイルス対策を構成する
description: グループ ポリシーを使用して、Microsoft Defender for Endpoint のMicrosoft Defender ウイルス対策を構成および管理する方法について説明します。
keywords: グループ ポリシー、GPO、構成、設定
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/08/2021
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: aa7ed07b02a4ae7783b5167f4127168aa50cdad1
ms.sourcegitcommit: 4ea16de333421e24b15dd1f164963bc9678653fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2021
ms.locfileid: "60009399"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>グループ ポリシー設定を使用して、グループ ポリシーの構成とMicrosoft Defender ウイルス対策

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

グループ ポリシーを[使用して](/windows/win32/srvnodes/group-policy)、エンドポイントのMicrosoft Defender ウイルス対策管理できます。

## <a name="configure-microsoft-defender-antivirus-using-group-policy"></a>グループ Microsoft Defender ウイルス対策を使用して構成する

一般に、次の手順を使用して、グループ ポリシー設定を構成Microsoft Defender ウイルス対策変更できます。

1. グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))コンソールを開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] をクリック **します**。

2. グループ ポリシー管理 **エディターを使用して、[コンピューター** の構成] **に移動します**。

3. [管理 **用テンプレート] をクリックします**。

4. ツリーを展開して、Windows **コンポーネントMicrosoft Defender ウイルス対策。** \> 

5. 構成する設定を含むセクション(このトピックの表では Location と呼ばれます) を展開し、設定をダブルクリックして開き、構成を変更します。

6. [通常と同じ方法で更新された GPO を展開します](/windows/win32/srvnodes/group-policy)。

## <a name="group-policy-settings-and-resources"></a>グループ ポリシーの設定とリソース

このトピックの次の表に、Windows 10 バージョン 1703 で使用できるグループ ポリシー設定の一覧を示し、このドキュメント ライブラリの該当するトピック (該当する場合) へのリンクを示します。

> [!TIP]
> [2020 年 5 設定更新プログラム (2004)](https://www.microsoft.com/download/101451)Windows 10グループ ポリシー のリファレンス スプレッドシートをダウンロードします。 このスプレッドシートには、Windows 10 2020 年 5 月更新プログラム (2004) 用に提供される管理用テンプレート ファイルに含まれるコンピューターとユーザー構成のポリシー設定が一覧表示されます。 グループ ポリシー オブジェクトを編集するときに、スプレッドシートを参照して構成できます。<br/><br/>

<br>

****

|Location|Setting|記事|
|---|---|---|
|クライアント インターフェイス|ヘッドレス UI モードを有効にする|[ユーザーがユーザー インターフェイスを表示または操作Microsoft Defender ウイルス対策防止する](prevent-end-user-interaction-microsoft-defender-antivirus.md)|
|クライアント インターフェイス|アクションを実行する必要がある場合にクライアントに追加のテキストを表示する|[エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)|
|クライアント インターフェイス|すべての通知を抑制する|[エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)|
|クライアント インターフェイス|再起動通知を抑制する|[エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)|
|除外|拡張機能の除外|[カスタム スキャンで除外を構成Microsoft Defender ウイルス対策する](configure-exclusions-microsoft-defender-antivirus.md)|
|除外|パスの除外|[カスタム スキャンで除外を構成Microsoft Defender ウイルス対策する](configure-exclusions-microsoft-defender-antivirus.md)|
|除外|プロセスの除外|[カスタム スキャンで除外を構成Microsoft Defender ウイルス対策する](configure-exclusions-microsoft-defender-antivirus.md)|
|除外|自動除外をオフにする|[カスタム スキャンで除外を構成Microsoft Defender ウイルス対策する](configure-exclusions-microsoft-defender-antivirus.md)|
|MAPS|'一目でブロックする' 機能を構成する|[一目でブロックを有効にする](configure-block-at-first-sight-microsoft-defender-antivirus.md)|
|MAPS|Microsoft MAPS に参加する|[クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md)|
|MAPS|詳細な分析が必要な場合にファイル サンプルを送信する|[クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md)|
|MAPS|Microsoft MAPS へのレポート用にローカル設定の上書きを構成する|[ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|MpEngine|拡張クラウド チェックの構成|[クラウド ブロックのタイムアウト期間の構成](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)|
|MpEngine|クラウド保護レベルの選択|[クラウドによる保護レベルを指定する](specify-cloud-protection-level-microsoft-defender-antivirus.md)|
|ネットワーク検査システム|ネットワーク トラフィック検査用の追加の定義セットを指定する|[ネットワーク トラフィック検査用の追加の定義セットを指定する](specify-additional-definitions-network-traffic-inspection-mdav.md)|
|ネットワーク検査システム|定義の削除を有効にする|[定義の削除を構成する](turn-on-definition-retirement.md)|
|ネットワーク検査システム|プロトコル認識を有効にする|[プロトコル認識を有効にする](turn-on-protocol-recognition.md)|
|検疫する|検疫フォルダーからアイテムを削除するローカル設定の上書きを構成する|[ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|検疫する|検疫フォルダーからのアイテムの削除を構成する|[スキャンの修復をMicrosoft Defender ウイルス対策する](configure-remediation-microsoft-defender-antivirus.md)|
|リアルタイム保護|コンピューター上のファイルとプログラムのアクティビティを監視するローカル設定の上書きを構成する|[ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|リアルタイム保護|受信および送信ファイルのアクティビティを監視するローカル設定の上書きを構成する|[ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|リアルタイム保護|ダウンロードしたファイルと添付ファイルをスキャンするローカル設定の上書きを構成する|[ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|リアルタイム保護|オンの動作監視用にローカル設定の上書きを構成する|[ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|リアルタイム保護|ローカル設定の上書きを構成してリアルタイム保護を有効にする|[ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|リアルタイム保護|スキャンするダウンロード ファイルと添付ファイルの最大サイズを定義する|[常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|リアルタイム保護|コンピューター上のファイルとプログラムのアクティビティを監視する|[常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|リアルタイム保護|ダウンロードしたファイルと添付ファイルをスキャンする|[常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|リアルタイム保護|リアルタイム保護をオフにする|[常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|リアルタイム保護|動作の監視を有効にする|[常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|リアルタイム保護|リアルタイム保護が有効な場合は常にプロセス スキャンを有効にする|[常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|リアルタイム保護|生のボリューム書き込み通知を有効にする|[常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|リアルタイム保護|受信および送信のファイルとプログラムのアクティビティの監視を構成する|[常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|修復|スケジュールされたフル スキャンを実行して修復を完了するために、時刻のローカル設定の上書きを構成する|[ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|修復|スケジュールされたフル スキャンを実行して修復を完了する日を指定する|[スケジュールされたスキャンMicrosoft Defender ウイルス対策構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|修復|スケジュールされたフル スキャンを実行して修復を完了する時刻を指定する|[スケジュールされたスキャンMicrosoft Defender ウイルス対策構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|レポート|拡張通知を無効にする|[エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)
|ルート|[オフにする] Microsoft Defender ウイルス対策|使用しない (インストールされているサード パーティ製ウイルス対策アプリが正しく動作するように、この設定を [構成されていない] に設定する必要があります)
|ルート|プロキシ サーバーをバイパスするアドレスを定義する|[デバイス プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)|
|ルート|ネットワークに接続するためのプロキシの自動構成 (.pac) を定義する|[デバイス プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)|
|ルート|ネットワークに接続するためのプロキシ サーバーを定義する|[デバイス プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)|
|ルート|リストのローカル管理者のマージ動作を構成する|[ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|ルート|マルウェア対策サービスが通常の優先度で起動を許可する|[スキャンの修復をMicrosoft Defender ウイルス対策する](configure-remediation-microsoft-defender-antivirus.md)|
|ルート|マルウェア対策サービスの実行を常に許可する|[スキャンの修復をMicrosoft Defender ウイルス対策する](configure-remediation-microsoft-defender-antivirus.md)|
|ルート|定期的な修復をオフにする|[スキャンの修復をMicrosoft Defender ウイルス対策する](configure-remediation-microsoft-defender-antivirus.md)|
|ルート|スケジュールされたタスク時間をランダム化する|[スケジュールされたスキャンを構成Microsoft Defender ウイルス対策](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|スキャン|ユーザーによるスキャンの一時停止を許可する|[ユーザーがユーザー インターフェイスを表示](prevent-end-user-interaction-microsoft-defender-antivirus.md)または操作Microsoft Defender ウイルス対策する (ユーザー インターフェイスではWindows 10)|
|スキャン|スケジュールされたスキャンを実行する前に、最新のウイルス定義とスパイウェア定義を確認する|[イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md)|
|スキャン|キャッチアップ スキャンを強制する日数を定義する|[最新のエンドポイントの更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|スキャン|フル スキャンのキャッチアップを有効にする|[最新のエンドポイントの更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|スキャン|クイック スキャンのキャッチアップを有効にする|[最新のエンドポイントの更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|スキャン|CPU 使用率の最大割合に対するローカル設定の上書きを構成する|[ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|スキャン|スケジュール スキャン日のローカル設定の上書きを構成する|[ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|スキャン|スケジュールされたクイック スキャン時間のローカル設定の上書きを構成する|[ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|スキャン|スケジュールされたスキャン時間のローカル設定の上書きを構成する|[ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|スキャン|スケジュールされたスキャンに使用するスキャンの種類のローカル設定の上書きを構成する|[ユーザーによるポリシー設定のローカル変更を防止または許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|スキャン|システム復元ポイントの作成|[スキャンの修復をMicrosoft Defender ウイルス対策する](configure-remediation-microsoft-defender-antivirus.md)|
|スキャン|スキャン履歴フォルダーからのアイテムの削除を有効にする|[スキャンの修復をMicrosoft Defender ウイルス対策する](configure-remediation-microsoft-defender-antivirus.md)|
|スキャン|ヒューリスティックを有効にする|[常時オンのMicrosoft Defender ウイルス対策監視を有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|スキャン|電子メール スキャンを有効にする|[[スキャン オプションの構成] Microsoft Defender ウイルス対策](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|再解析ポイントスキャンを有効にする|[[スキャン オプションの構成] Microsoft Defender ウイルス対策](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|マップされたネットワーク ドライブでフル スキャンを実行する|[[スキャン オプションの構成] Microsoft Defender ウイルス対策](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|アーカイブ ファイルのスキャン|[[スキャン オプションの構成] Microsoft Defender ウイルス対策](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|ネットワーク ファイルのスキャン|[[スキャン オプションの構成] Microsoft Defender ウイルス対策](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|パックされた実行可能ファイルをスキャンする|[[スキャン オプションの構成] Microsoft Defender ウイルス対策](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|リムーバブル ドライブのスキャン|[[スキャン オプションの構成] Microsoft Defender ウイルス対策](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|アーカイブ ファイルをスキャンする最大深度を指定する|[[スキャン オプションの構成] Microsoft Defender ウイルス対策](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|スキャン中の CPU 使用率の最大割合を指定する|[[スキャン オプションの構成] Microsoft Defender ウイルス対策](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|スキャンするアーカイブ ファイルの最大サイズを指定する|[[スキャン オプションの構成] Microsoft Defender ウイルス対策](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|スケジュールされたスキャンを実行する週の日を指定する|[スケジュールされたスキャンを構成Microsoft Defender ウイルス対策](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|スキャン|1 日あたりのクイック スキャンを実行する間隔を指定する|[スケジュールされたスキャンを構成Microsoft Defender ウイルス対策](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|スキャン|スケジュールされたスキャンに使用するスキャンの種類を指定する|[スケジュールされたスキャンを構成Microsoft Defender ウイルス対策](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|スキャン|毎日のクイック スキャンの時間を指定する|[スケジュールされたスキャンを構成Microsoft Defender ウイルス対策](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|スキャン|スケジュールされたスキャンを実行する時刻を指定する|[スケジュールされたスキャンを構成Microsoft Defender ウイルス対策](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|スキャン|コンピューターがオンで、使用されていない場合にのみ、スケジュールされたスキャンを開始する|[スケジュールされたスキャンを構成Microsoft Defender ウイルス対策](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|Microsoft Update からのセキュリティ インテリジェンスの更新を許可する|[モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|バッテリーの電源で実行するときにセキュリティ インテリジェンスの更新を許可する|[モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|Microsoft MAPS への定義ベースのレポートを無効にする通知を許可する|[イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|Microsoft MAPS へのレポートに基づいてリアルタイムのセキュリティ インテリジェンス更新を許可する|[イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|起動時に最新のウイルスとスパイウェアの定義を確認する|[イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|セキュリティ インテリジェンス更新プログラムをダウンロードするためのファイル共有の定義|[保護Microsoft Defender ウイルス対策セキュリティ インテリジェンス更新プログラムを管理する](manage-protection-updates-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|セキュリティ インテリジェンス更新プログラムのキャッチアップが必要になる日数を定義する|[最新のエンドポイントの更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|スパイウェア定義が最新でないと見なされる日数を定義する|[最新のエンドポイントの更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|ウイルス定義が最新でないと見なされる日数を定義する|[最新のエンドポイントの更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|セキュリティ インテリジェンス更新プログラムをダウンロードするためのソースの順序を定義する|[保護Microsoft Defender ウイルス対策セキュリティ インテリジェンス更新プログラムを管理する](manage-protection-updates-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|起動時にセキュリティ インテリジェンス更新プログラムを開始する|[イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|セキュリティ インテリジェンスの更新プログラムを確認する週の日を指定する|[保護更新プログラムをダウンロードして適用する場合の管理](manage-protection-update-schedule-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|セキュリティ インテリジェンスの更新プログラムを確認する間隔を指定する|[保護更新プログラムをダウンロードして適用する場合の管理](manage-protection-update-schedule-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|セキュリティ インテリジェンスの更新プログラムを確認する時間を指定する|[保護更新プログラムをダウンロードして適用する場合の管理](manage-protection-update-schedule-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|セキュリティ インテリジェンスの更新後にスキャンを有効にする|[スケジュールされたスキャンを構成Microsoft Defender ウイルス対策](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|Threats|検出時に既定のアクションを実行しない脅威アラート レベルを指定する|[スキャンの修復をMicrosoft Defender ウイルス対策する](configure-remediation-microsoft-defender-antivirus.md)|
|Threats|検出時に既定のアクションを実行しない脅威を指定する|[スキャンの修復をMicrosoft Defender ウイルス対策する](configure-remediation-microsoft-defender-antivirus.md)|
|

## <a name="see-also"></a>関連項目

- [管理および構成ツールのリファレンス トピック](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
