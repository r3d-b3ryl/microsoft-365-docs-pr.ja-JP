---
title: Linux リソースでのMicrosoft Defender for Endpoint
ms.reviewer: ''
description: Linux 上のMicrosoft Defender for Endpointのリソースについて説明します。アンインストール方法、診断ログの収集方法、CLI コマンド、製品に関する既知の問題などです。
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
ms.openlocfilehash: a32c8c91350218da619de18e0b1b398a93bf7fda
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63312657"
---
# <a name="resources"></a>リソース

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="collect-diagnostic-information"></a>診断情報を収集する

問題を再現できる場合は、まずログ レベルを上げて、しばらくシステムを実行してから、ログ レベルを既定に復元します。

1. ログ レベルを上げる:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. 問題を再現します。

3. 次のコマンドを実行して、Defender for Endpoint のログをバックアップします。 ファイルは、.zip アーカイブ内に格納されます。

   ```bash
   sudo mdatp diagnostic create
   ```

    このコマンドは、操作が成功した後、バックアップへのファイル パスも出力します。

   ```Output
   Diagnostic file created: <path to file>
   ```

4. ログ レベルを復元する:

   ```bash
   mdatp log level set --level info
   ```

   ```Output
   Log level configured successfully
   ```

## <a name="log-installation-issues"></a>インストールの問題をログする

インストール中にエラーが発生した場合、インストーラーは一般的なエラーのみを報告します。

詳細なログが保存 `/var/log/microsoft/mdatp/install.log`されます。
インストール中に問題が発生した場合は、原因の診断に役立つよう、このファイルを送信してください。

## <a name="uninstall"></a>アンインストール

Linux 上の Defender for Endpoint をアンインストールするには、いくつかの方法があります。 Puppet などの構成ツールを使用している場合は、構成ツールのパッケージアンインストール手順に従います。

### <a name="manual-uninstallation"></a>手動アンインストール

- `sudo yum remove mdatp` RHEL とバリアント (CentOS および Oracle Linux) の場合。
- `sudo zypper remove mdatp` SLES とバリアントの場合。
- `sudo apt-get purge mdatp` Ubuntu および Debian システムの場合。

## <a name="configure-from-the-command-line"></a>コマンド ラインから構成する

製品設定の制御やオンデマンド スキャンのトリガーなどの重要なタスクは、コマンド ラインから実行できます。

### <a name="global-options"></a>グローバル オプション

既定では、コマンド ライン ツールは結果を人間が判読できる形式で出力します。 さらに、このツールは、自動化シナリオに役立つ JSON としての結果の出力もサポートします。 出力を JSON に変更するには、次のいずれかのコマンドに渡 `--output json` します。

### <a name="supported-commands"></a>サポート対象コマンド

次の表に、最も一般的なシナリオの一部のコマンドを示します。 ターミナルから実行 `mdatp help` して、サポートされているコマンドの完全な一覧を表示します。

<br>

****

|Group|シナリオ|コマンド|
|---|---|---|
|構成|リアルタイム保護のオン/オフを切り替える|`mdatp config real-time-protection --value [enabled\|disabled]`|
|構成|動作の監視のオン/オフを切り替える|`mdatp config behavior-monitoring --value [enabled\|disabled]`
|構成|クラウド保護のオン/オフを切り替える|`mdatp config cloud --value [enabled\|disabled]`|
|構成|製品診断のオン/オフを切り替える|`mdatp config cloud-diagnostic --value [enabled\|disabled]`|
|構成|サンプルの自動送信のオン/オフを切り替える|`mdatp config cloud-automatic-sample-submission [enabled\|disabled]`|
|構成|AV パッシブ モードのオン/オフを切り替える|`mdatp config passive-mode --value [enabled\|disabled]`|
|構成|ファイル拡張子のウイルス対策除外を追加または削除する|`mdatp exclusion extension [add\|remove] --name [extension]`|
|構成|ファイルのウイルス対策除外を追加または削除する|`mdatp exclusion file [add\|remove] --path [path-to-file]`|
|構成|ディレクトリのウイルス対策除外を追加または削除する|`mdatp exclusion folder [add\|remove] --path [path-to-directory]`|
|構成|プロセスのウイルス対策除外を追加または削除する|`mdatp exclusion process [add\|remove] --path [path-to-process]` <p> `mdatp exclusion process [add\|remove] --name [process-name]`|
|構成|すべてのウイルス対策除外を一覧表示する|`mdatp exclusion list`|
|構成|許可されたリストに脅威名を追加する|`mdatp threat allowed add --name [threat-name]`|
|構成|許可されたリストから脅威名を削除する|`mdatp threat allowed remove --name [threat-name]`|
|構成|許可されているすべての脅威名を一覧表示する|`mdatp threat allowed list`|
|構成|PUA 保護を有効にする|`mdatp threat policy set --type potentially_unwanted_application --action block`|
|構成|PUA 保護をオフにする|`mdatp threat policy set --type potentially_unwanted_application --action off`|
|構成|PUA 保護の監査モードを有効にする|`mdatp threat policy set --type potentially_unwanted_application --action audit`|
|構成|オンデマンド スキャンの並列処理の程度を構成する|`mdatp config maximum-on-demand-scan-threads --value [numerical-value-between-1-and-64]`|
|構成|セキュリティ インテリジェンスの更新後にスキャンをオン/オフにする|`mdatp config scan-after-definition-update --value [enabled/disabled]`|
|構成|アーカイブ スキャンのオン/オフを切り替える (オンデマンド スキャンのみ)|`mdatp config scan-archives --value [enabled/disabled]`|
|診断|ログ レベルを変更する|`mdatp log level set --level verbose [error|warning|info|verbose]`|
|診断|診断ログを生成する|`mdatp diagnostic create --path [directory]`|
|正常性|製品の正常性を確認する|`mdatp health`|
|保護|パスをスキャンする|`mdatp scan custom --path [path] [--ignore-exclusions]`|
|保護|クイック スキャンを実行する|`mdatp scan quick`|
|保護|フル スキャンを実行する|`mdatp scan full`|
|保護|進行中のオンデマンド スキャンをキャンセルする|`mdatp scan cancel`|
|保護|セキュリティ インテリジェンス更新プログラムを要求する|`mdatp definitions update`|
|保護履歴|完全な保護履歴を印刷する|`mdatp threat list`|
|保護履歴|脅威の詳細を取得する|`mdatp threat get --id [threat-id]`|
|検疫管理|検疫されたすべてのファイルを一覧表示する|`mdatp threat quarantine list`|
|検疫管理|検疫からすべてのファイルを削除する|`mdatp threat quarantine remove-all`|
|検疫管理|脅威として検出されたファイルを検疫に追加する|`mdatp threat quarantine add --id [threat-id]`|
|検疫管理|検疫から脅威として検出されたファイルを削除する|`mdatp threat quarantine remove --id [threat-id]`|
|検疫管理|検疫からファイルを復元する|`mdatp threat quarantine restore --id [threat-id] --path [destination-folder]`|
|エンドポイントの検出と応答|早期プレビューを設定する (未使用)|`mdatp edr early-preview [enable|disable]`|
|エンドポイントの検出と応答|group-id を設定する|`mdatp edr group-ids --group-id [group-id]`|
|エンドポイントの検出と応答|タグを設定/削除する(サポートされているのみ)`GROUP`|`mdatp edr tag set --name GROUP --value [tag]`|
|エンドポイントの検出と応答|リストの除外 (ルート)|`mdatp edr exclusion list [processes|paths|extensions|all]`|
|
