---
title: Microsoft Defender for Endpoint on Linux リソース
ms.reviewer: ''
description: Microsoft Defender for Endpoint on Linux のリソース (アンインストール方法、診断ログの収集方法、CLI コマンド、製品に関する既知の問題など) について説明します。
keywords: Microsoft、Defender、Microsoft Defender for Endpoint、Linux、インストール、展開、アンインストール、puppet、ansible、linux、redhat、ubuntu、debian、sles、suse、centos
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
ms.openlocfilehash: 89178fc9c8ec44da0f9f51e2c4bfc6b1dfbab138
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211071"
---
# <a name="resources"></a>リソース

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a>診断情報の収集

問題を再現できる場合は、まずログ レベルを上げ、システムを一時実行してから、ログ レベルを既定に復元します。

1. ログ レベルを上げ:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. 問題を再現します。

3. 次のコマンドを実行して、Defender for Endpoint のログをバックアップします。 ファイルは、アーカイブ内に.zipされます。

   ```bash
   sudo mdatp diagnostic create
   ```

    このコマンドは、操作が成功した後、バックアップへのファイル パスも出力します。

   ```Output
   Diagnostic file created: <path to file>
   ```

4. ログ レベルの復元:

   ```bash
   mdatp log level set --level info
   ```

   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a>インストールの問題をログする

インストール中にエラーが発生した場合、インストーラーは一般的なエラーのみを報告します。

詳細ログはに保存されます `/var/log/microsoft/mdatp/install.log` 。
インストール中に問題が発生した場合は、このファイルを送信して、原因の診断に役立ちます。

## <a name="uninstall"></a>アンインストール

Linux で Defender for Endpoint をアンインストールするには、いくつかの方法があります。 Puppet などの構成ツールを使用している場合は、構成ツールのパッケージのアンインストール手順に従います。

### <a name="manual-uninstallation"></a>手動アンインストール

- `sudo yum remove mdatp` RHEL およびバリアント (CentOS および Oracle Linux) の場合。
- `sudo zypper remove mdatp` SLES およびバリアントの場合。
- `sudo apt-get purge mdatp` Ubuntu および Debian システム用。

## <a name="configure-from-the-command-line"></a>コマンド ラインから構成する

製品設定の制御やオンデマンド スキャンのトリガーなどの重要なタスクは、コマンド ラインから実行できます。

### <a name="global-options"></a>グローバル オプション

既定では、コマンド ライン ツールは人間が読み取り可能な形式で結果を出力します。 さらに、このツールは JSON としての結果の出力もサポートしています。これは自動化シナリオに役立ちます。 出力を JSON に変更するには、次 `--output json` のコマンドに渡します。

### <a name="supported-commands"></a>サポート対象コマンド

次の表に、最も一般的なシナリオの一部のコマンドを示します。 ターミナル `mdatp help` から実行して、サポートされているコマンドの完全な一覧を表示します。

<br>

****

|Group|シナリオ|コマンド|
|---|---|---|
|構成|リアルタイム保護のオン/オフ|`mdatp config real-time-protection --value [enabled\|disabled]`|
|構成|動作監視のオン/オフを切り替えます|`mdatp config behavior-monitoring --value [enabled\|disabled]`
|構成|クラウド保護のオン/オフ|`mdatp config cloud --value [enabled\|disabled]`|
|構成|製品診断のオン/オフ|`mdatp config cloud-diagnostic --value [enabled\|disabled]`|
|構成|自動サンプル申請のオン/オフ|`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`|
|構成|AV パッシブ モードのオン/オフ|`mdatp config passive-mode --value [enabled\|disabled]`|
|構成|ファイル拡張子のウイルス対策除外を追加/削除する|`mdatp exclusion extension [add\|remove] --name [extension]`|
|構成|ファイルのウイルス対策除外を追加/削除する|`mdatp exclusion file [add\|remove] --path [path-to-file]`|
|構成|ディレクトリのウイルス対策の除外を追加/削除する|`mdatp exclusion folder [add\|remove] --path [path-to-directory]`|
|構成|プロセスのウイルス対策除外を追加/削除する|`mdatp exclusion process [add\|remove] --path [path-to-process]` <p> `mdatp exclusion process [add\|remove] --name [process-name]`|
|構成|すべてのウイルス対策の除外を一覧表示する|`mdatp exclusion list`|
|構成|許可リストに脅威名を追加する|`mdatp threat allowed add --name [threat-name]`|
|構成|許可リストから脅威名を削除する|`mdatp threat allowed remove --name [threat-name]`|
|構成|許可されている脅威名の一覧を表示する|`mdatp threat allowed list`|
|構成|PUA 保護を有効にする|`mdatp threat policy set --type potentially_unwanted_application --action block`|
|構成|PUA 保護をオフにする|`mdatp threat policy set --type potentially_unwanted_application --action off`|
|構成|PUA 保護の監査モードを有効にする|`mdatp threat policy set --type potentially_unwanted_application --action audit`|
|Diagnostics|ログ レベルの変更|`mdatp log level set --level verbose [error|warning|info|verbose]`|
|Diagnostics|診断ログの生成|`mdatp diagnostic create --path [directory]`|
|正常性|製品の正常性を確認する|`mdatp health`|
|保護|パスをスキャンする|`mdatp scan custom --path [path] [--ignore-exclusions]`|
|保護|クイック スキャンを実行する|`mdatp scan quick`|
|保護|フル スキャンを実行する|`mdatp scan full`|
|保護|進行中のオンデマンド スキャンをキャンセルする|`mdatp scan cancel`|
|保護|セキュリティ インテリジェンス更新プログラムの要求|`mdatp definitions update`|
|保護履歴|完全な保護履歴を印刷する|`mdatp threat list`|
|保護履歴|脅威の詳細を取得する|`mdatp threat get --id [threat-id]`|
|検疫の管理|検疫済みファイルの一覧表示|`mdatp threat quarantine list`|
|検疫の管理|検疫からすべてのファイルを削除する|`mdatp threat quarantine remove-all`|
|検疫の管理|脅威として検出されたファイルを検疫に追加する|`mdatp threat quarantine add --id [threat-id]`|
|検疫の管理|脅威として検出されたファイルを検疫から削除する|`mdatp threat quarantine remove --id [threat-id]`|
|検疫の管理|検疫からファイルを復元する|`mdatp threat quarantine restore --id [threat-id]`|
|エンドポイントの検出と応答|早期プレビューの設定 (未使用)|`mdatp edr early-preview [enable|disable]`|
|エンドポイントの検出と応答|group-id を設定する|`mdatp edr group-ids --group-id [group-id]`|
|エンドポイントの検出と応答|タグの設定と削除、 `GROUP` サポートのみ|`mdatp edr tag set --name GROUP --value [tag]`|
|エンドポイントの検出と応答|リストの除外 (ルート)|`mdatp edr exclusion list [processes|paths|extensions|all]`|
|

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Microsoft Defender for Endpoint ポータル情報

Defender for Endpoint ポータルには、次の 2 つのカテゴリの情報が表示されます。

- 次のウイルス対策アラートを含む。
  - 重要度
  - スキャンの種類
  - デバイス情報 (ホスト名、デバイス識別子、テナント識別子、アプリのバージョン、OS の種類)
  - ファイル情報 (名前、パス、サイズ、ハッシュ)
  - 脅威情報 (名前、種類、状態)
- 次のデバイス情報を含むデバイス情報。
  - デバイス識別子
  - テナント識別子
  - アプリのバージョン
  - ホスト名
  - OS の種類
  - OS のバージョン
  - コンピューター モデル
  - プロセッサアーキテクチャ
  - デバイスが仮想マシンかどうか

### <a name="known-issues"></a>既知の問題

- 製品が期待通り動作している場合でも、Microsoft 365 Defender ポータルのコンピューター情報ページに「センサー データなし、通信障害」が表示される場合があります。 この問題の解決に取り組み中です。
- ログオンしているユーザーは、ポータルにMicrosoft 365 Defenderされません。
- SUSE ディストリビューションで *、libatomic1* のインストールが失敗した場合は、OS が登録されているのを検証する必要があります。

   ```bash
   sudo SUSEConnect --status-text
   ```
