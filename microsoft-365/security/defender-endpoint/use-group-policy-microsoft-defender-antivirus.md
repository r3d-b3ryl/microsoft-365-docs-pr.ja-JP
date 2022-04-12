---
title: グループ ポリシーを使用してMicrosoft Defender ウイルス対策を構成する
description: グループ ポリシーを使用して、Microsoft Defender for EndpointでエンドポイントのMicrosoft Defender ウイルス対策を構成および管理する方法について説明します。
keywords: グループ ポリシー, GPO, 構成, 設定
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/04/2022
ms.reviewer: ksarens, jtoole, pahuijbr
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: e8cda6f387814ed6ec613db8cb53ff030243a92b
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789422"
---
# <a name="use-group-policy-settings-to-configure-and-manage-microsoft-defender-antivirus"></a>グループ ポリシー設定を使用して Microsoft Defender ウイルス対策を管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

[グループ ポリシー](/windows/win32/srvnodes/group-policy)を使用して、エンドポイントのMicrosoft Defender ウイルス対策を構成および管理できます。

## <a name="configure-microsoft-defender-antivirus-using-group-policy"></a>グループ ポリシーを使用してMicrosoft Defender ウイルス対策を構成する

一般に、次の手順を使用して、グループ ポリシー設定Microsoft Defender ウイルス対策構成または変更できます。

1. グループ ポリシー管理マシンで、[グループ ポリシー管理コンソール](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))を開き、構成するグループ ポリシー オブジェクト (GPO) を右クリックし、[編集] をクリック **します**。

2. **グループ ポリシー管理エディター** を使用して **、コンピューターの構成** に移動します。

3. [ **管理用テンプレート]** をクリックします。

4. ツリーを展開して **、Microsoft Defender ウイルス対策コンポーネント** \> **をWindows** します。

5. 構成する設定を含むセクション (このトピックの「 **場所** 」と呼ばれます) を展開し、設定をダブルクリックして開き、構成を変更します。

6. [通常どおりに、更新された GPO をデプロイ](/windows/win32/srvnodes/group-policy)します。

## <a name="group-policy-settings-and-resources"></a>グループ ポリシー設定とリソース

次の表は、Windows 10で使用できる一般的なグループ ポリシー設定の一覧です。

> [!TIP]
> グループ ポリシー参照スプレッドシートをダウンロードします。このスプレッドシートには、Windows用に配信される管理用テンプレート ファイルに含まれるコンピューターとユーザーの構成のポリシー設定が一覧表示されます。 グループ ポリシー オブジェクトを編集するときにスプレッドシートを参照するように構成できます。 <br/><br/> 最新バージョンを次に示します。
> - [Windows 10 2020 年 5 月更新 (2004 年) のグループ ポリシー 設定参照スプレッドシート](https://www.microsoft.com/download/details.aspx?id=101451)
> - [Windows 11 2021 年 10 月更新 (21H2) のグループ ポリシー 設定参照スプレッドシート](https://www.microsoft.com/download/details.aspx?id=103506)

<br/><br/>

|場所|設定|記事|
|---|---|---|
|クライアント インターフェイス|ヘッドレス UI モードを有効にする|[ユーザーがMicrosoft Defender ウイルス対策ユーザー インターフェイスを表示または操作できないようにする](prevent-end-user-interaction-microsoft-defender-antivirus.md)|
|クライアント インターフェイス|アクションを実行する必要がある場合にクライアントに追加のテキストを表示する|[エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)|
|クライアント インターフェイス|すべての通知を非表示にする|[エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)|
|クライアント インターフェイス|再起動通知を抑制する|[エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)|
|除外|拡張機能の除外|[Microsoft Defender ウイルス対策 スキャンでの除外の構成と検証](configure-exclusions-microsoft-defender-antivirus.md)|
|除外|パスの除外|[Microsoft Defender ウイルス対策 スキャンでの除外の構成と検証](configure-exclusions-microsoft-defender-antivirus.md)|
|除外|プロセスの除外|[Microsoft Defender ウイルス対策 スキャンでの除外の構成と検証](configure-exclusions-microsoft-defender-antivirus.md)|
|除外|自動除外をオフにする|[Microsoft Defender ウイルス対策 スキャンでの除外の構成と検証](configure-exclusions-microsoft-defender-antivirus.md)|
|マップ|"一目でブロック" 機能を構成する|[ブロックを一目で有効にする](configure-block-at-first-sight-microsoft-defender-antivirus.md)|
|マップ|Microsoft MAPS に参加する|[クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md)|
|マップ|さらなる分析が必要な場合にファイル サンプルを送信する|[クラウドによる保護の有効化](enable-cloud-protection-microsoft-defender-antivirus.md)|
|マップ|Microsoft MAPS へのレポートのローカル設定のオーバーライドを構成する|[ユーザーがポリシー設定をローカルで変更できないようにするか許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|MpEngine|拡張クラウド チェックを構成する|[クラウド ブロックのタイムアウト期間の構成](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)|
|MpEngine|クラウド保護レベルを選択する|[クラウドによる保護レベルを指定する](specify-cloud-protection-level-microsoft-defender-antivirus.md)|
|ネットワーク検査システム|ネットワーク トラフィック検査用に追加の定義セットを指定する| 使用されません (非推奨) |
|ネットワーク検査システム|定義の廃止を有効にする| 使用されません (非推奨)|
|ネットワーク検査システム|プロトコル認識を有効にする| 使用されません (非推奨)|
|検疫する|検疫フォルダーからアイテムを削除するためのローカル設定のオーバーライドを構成する|[ユーザーがポリシー設定をローカルで変更できないようにするか許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|検疫する|検疫フォルダーからのアイテムの削除を構成する|[Microsoft Defender ウイルス対策 スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md)|
|リアルタイム保護|コンピューター上のファイルとプログラムのアクティビティを監視するためのローカル設定のオーバーライドを構成する|[ユーザーがポリシー設定をローカルで変更できないようにするか許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|リアルタイム保護|受信および送信ファイル アクティビティを監視するためのローカル設定のオーバーライドを構成する|[ユーザーがポリシー設定をローカルで変更できないようにするか許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|リアルタイム保護|ダウンロードしたすべてのファイルと添付ファイルをスキャンするためのローカル設定のオーバーライドを構成する|[ユーザーがポリシー設定をローカルで変更できないようにするか許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|リアルタイム保護|動作の監視を有効にするためのローカル設定のオーバーライドを構成する|[ユーザーがポリシー設定をローカルで変更できないようにするか許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|リアルタイム保護|リアルタイム保護を有効にするローカル設定のオーバーライドを構成する|[ユーザーがポリシー設定をローカルで変更できないようにするか許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|リアルタイム保護|スキャンするダウンロードしたファイルと添付ファイルの最大サイズを定義する|[常時オンの保護と監視Microsoft Defender ウイルス対策有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|リアルタイム保護|コンピューター上のファイルとプログラムのアクティビティを監視する|[常時オンの保護と監視Microsoft Defender ウイルス対策有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|リアルタイム保護|ダウンロードしたすべてのファイルと添付ファイルをスキャンする|[常時オンの保護と監視Microsoft Defender ウイルス対策有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|リアルタイム保護|リアルタイム保護を無効にする|[常時オンの保護と監視Microsoft Defender ウイルス対策有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|リアルタイム保護|動作の監視を有効にする|[常時オンの保護と監視Microsoft Defender ウイルス対策有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|リアルタイム保護|リアルタイム保護が有効になっている場合は必ずプロセス スキャンを有効にする|[常時オンの保護と監視Microsoft Defender ウイルス対策有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|リアルタイム保護|未加工ボリューム書き込み通知を有効にする|[常時オンの保護と監視Microsoft Defender ウイルス対策有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|リアルタイム保護|受信および送信ファイルとプログラム アクティビティの監視を構成する|[常時オンの保護と監視Microsoft Defender ウイルス対策有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|修復|スケジュールされたフル スキャンを実行して修復を完了するように、時刻のローカル設定のオーバーライドを構成する|[ユーザーがポリシー設定をローカルで変更できないようにするか許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|修復|スケジュールされたフル スキャンを実行して修復を完了する曜日を指定する|[スケジュールされたMicrosoft Defender ウイルス対策 スキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|修復|スケジュールされたフル スキャンを実行して修復を完了する時刻を指定する|[スケジュールされたMicrosoft Defender ウイルス対策 スキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|レポート|強化された通知をオフにする|[エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)
|ルート|Microsoft Defender ウイルス対策をオフにする|不使用。 Microsoft 以外のウイルス対策製品を使用または使用する予定がある場合は、[他のセキュリティ製品との互換性Microsoft Defender ウイルス対策](microsoft-defender-antivirus-compatibility.md)参照してください。|
|ルート|プロキシ サーバーをバイパスするアドレスを定義する|[デバイス プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)|
|ルート|ネットワークに接続するためのプロキシ自動構成 (.pac) を定義する|[デバイス プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)|
|ルート|ネットワークに接続するためのプロキシ サーバーを定義する|[デバイス プロキシとインターネット接続の設定を構成する](configure-proxy-internet.md#configure-a-static-proxy-for-microsoft-defender-antivirus)|
|ルート|リストのローカル管理者マージ動作を構成する|[ユーザーがポリシー設定をローカルで変更できないようにするか許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|ルート|マルウェア対策サービスを通常の優先度で起動できるようにする|[Microsoft Defender ウイルス対策 スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md)|
|ルート|マルウェア対策サービスを常に実行したままにする|[Microsoft Defender ウイルス対策 スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md)|
|ルート|定期的な修復を無効にする|[Microsoft Defender ウイルス対策 スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md)|
|ルート|スケジュールされたタスク時間をランダム化する|[Microsoft Defender ウイルス対策のスケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|スキャン|ユーザーによるスキャンの一時停止を許可する|[ユーザーがMicrosoft Defender ウイルス対策ユーザー インターフェイスを表示または操作できないようにする](prevent-end-user-interaction-microsoft-defender-antivirus.md) (Windows 10ではサポートされていません)|
|スキャン|スケジュールされたスキャンを実行する前に、最新のウイルス定義とスパイウェア定義を確認する|[イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md)|
|スキャン|キャッチアップ スキャンが強制されるまでの日数を定義する|[最新でないエンドポイント用の更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|スキャン|フル スキャンのキャッチアップを有効にする|[最新でないエンドポイント用の更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|スキャン|クイック スキャンのキャッチアップを有効にする|[最新でないエンドポイント用の更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|スキャン|CPU 使用率の最大パーセンテージに対してローカル設定のオーバーライドを構成する|[ユーザーがポリシー設定をローカルで変更できないようにするか許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|スキャン|スケジュール スキャン日のローカル設定のオーバーライドを構成する|[ユーザーがポリシー設定をローカルで変更できないようにするか許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|スキャン|スケジュールされたクイック スキャン時間のローカル設定のオーバーライドを構成する|[ユーザーがポリシー設定をローカルで変更できないようにするか許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|スキャン|スケジュールされたスキャン時間のローカル設定のオーバーライドを構成する|[ユーザーがポリシー設定をローカルで変更できないようにするか許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|スキャン|スケジュールされたスキャンに使用するスキャンの種類のローカル設定のオーバーライドを構成する|[ユーザーがポリシー設定をローカルで変更できないようにするか許可する](configure-local-policy-overrides-microsoft-defender-antivirus.md)|
|スキャン|システム復元ポイントを作成する|[Microsoft Defender ウイルス対策 スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md)|
|スキャン|スキャン履歴フォルダーからのアイテムの削除を有効にする|[Microsoft Defender ウイルス対策 スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md)|
|スキャン|ヒューリスティックを有効にする|[常時オンの保護と監視Microsoft Defender ウイルス対策有効にして構成する](configure-real-time-protection-microsoft-defender-antivirus.md)|
|スキャン|電子メール スキャンを有効にする|[Microsoft Defender ウイルス対策でスキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|再解析ポイントスキャンを有効にする|[Microsoft Defender ウイルス対策でスキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|マップされたネットワーク ドライブでフル スキャンを実行する|[Microsoft Defender ウイルス対策でスキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|アーカイブ ファイルをスキャンする|[Microsoft Defender ウイルス対策でスキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|ネットワーク ファイルをスキャンする|[Microsoft Defender ウイルス対策でスキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|パックされた実行可能ファイルをスキャンする|[Microsoft Defender ウイルス対策でスキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
| スキャン | スクリプトをスキャンする | [Microsoft Defender ウイルス対策でスキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md) <p>[Defender/AllowScriptScanning](/windows/client-management/mdm/policy-csp-defender) も参照してください。|
|スキャン|リムーバブル ドライブをスキャンする|[Microsoft Defender ウイルス対策でスキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|アーカイブ ファイルをスキャンする最大深度を指定する|[Microsoft Defender ウイルス対策でスキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|スキャン中の CPU 使用率の最大割合を指定する|[Microsoft Defender ウイルス対策でスキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|スキャンするアーカイブ ファイルの最大サイズを指定する|[Microsoft Defender ウイルス対策でスキャン オプションを構成する](configure-advanced-scan-types-microsoft-defender-antivirus.md)|
|スキャン|スケジュールされたスキャンを実行する曜日を指定する|[Microsoft Defender ウイルス対策のスケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|スキャン|1 日あたりのクイック スキャンを実行する間隔を指定する|[Microsoft Defender ウイルス対策のスケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|スキャン|スケジュールされたスキャンに使用するスキャンの種類を指定する|[Microsoft Defender ウイルス対策のスケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|スキャン|1 日のクイック スキャンの時間を指定する|[Microsoft Defender ウイルス対策のスケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|スキャン|スケジュールされたスキャンを実行する時刻を指定する|[Microsoft Defender ウイルス対策のスケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|スキャン|コンピューターがオンになっていて使用中でない場合にのみ、スケジュールされたスキャンを開始する|[Microsoft Defender ウイルス対策のスケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|Microsoft Update からセキュリティ インテリジェンスの更新を許可する|[モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|バッテリ電源で実行しているときにセキュリティ インテリジェンスの更新を許可する|[モバイル デバイスと仮想マシン (VM) の更新プログラムを管理する](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|Microsoft MAPS に対する定義ベースのレポートを無効にする通知を許可する|[イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|Microsoft MAPS へのレポートに基づいてリアルタイムのセキュリティ インテリジェンス更新を許可する|[イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|起動時に最新のウイルス定義とスパイウェア定義を確認する|[イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|セキュリティ インテリジェンス更新プログラムをダウンロードするためのファイル共有を定義する|[Microsoft Defender ウイルス対策保護とセキュリティ インテリジェンスの更新を管理する](manage-protection-updates-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|セキュリティ インテリジェンス更新プログラムのキャッチアップが必要になるまでの日数を定義する|[最新でないエンドポイント用の更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|スパイウェア定義が古いと見なされるまでの日数を定義する|[最新でないエンドポイント用の更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|ウイルス定義が古いと見なされるまでの日数を定義する|[最新でないエンドポイント用の更新プログラムを管理する](manage-outdated-endpoints-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|セキュリティ インテリジェンス更新プログラムをダウンロードするためのソースの順序を定義する|[Microsoft Defender ウイルス対策保護とセキュリティ インテリジェンスの更新を管理する](manage-protection-updates-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|起動時にセキュリティ インテリジェンスの更新を開始する|[イベントベースの強制更新プログラムを管理する](manage-event-based-updates-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|セキュリティ インテリジェンス更新プログラムを確認する曜日を指定する|[保護更新プログラムをダウンロードして適用するタイミングを管理する](manage-protection-update-schedule-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|セキュリティ インテリジェンス更新プログラムを確認する間隔を指定する|[保護更新プログラムをダウンロードして適用するタイミングを管理する](manage-protection-update-schedule-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|セキュリティ インテリジェンス更新プログラムを確認する時間を指定する|[保護更新プログラムをダウンロードして適用するタイミングを管理する](manage-protection-update-schedule-microsoft-defender-antivirus.md)|
|セキュリティ インテリジェンスの更新プログラム|セキュリティ インテリジェンスの更新後にスキャンを有効にする|[Microsoft Defender ウイルス対策のスケジュールされたスキャンを構成する](scheduled-catch-up-scans-microsoft-defender-antivirus.md)|
|Threats|検出されたときに既定のアクションを実行しない脅威アラート レベルを指定する|[Microsoft Defender ウイルス対策 スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md)|
|Threats|検出されたときに既定のアクションを実行しない脅威を指定する|[Microsoft Defender ウイルス対策 スキャンの修復を構成する](configure-remediation-microsoft-defender-antivirus.md)|

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS でMicrosoft Defender for Endpointの基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [IntuneのMicrosoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux でMicrosoft Defender for Endpointの基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android の機能で Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能でMicrosoft Defender for Endpointを構成する](ios-configure-features.md)

## <a name="see-also"></a>関連項目

- [管理および構成ツールのリファレンス トピック](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
