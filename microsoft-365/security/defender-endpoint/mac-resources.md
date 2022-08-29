---
title: Mac 上のMicrosoft Defender for Endpoint用リソース
description: Mac でのMicrosoft Defender for Endpointのリソース (アンインストール方法、診断ログの収集方法、CLI コマンド、製品に関する既知の問題など)。
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, インストール, 展開, アンインストール, intune, jamf, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 7215beeec25f4d343e574b8e2bcda22a43f0f45e
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67386804"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a>macOS でのMicrosoft Defender for Endpointのリソース

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a>診断情報の収集

問題を再現できる場合は、ログ レベルを上げてしばらくシステムを実行し、ログ レベルを既定に復元します。

1. ログ レベルを上げる:

   ```bash
   mdatp log level set --level debug
   ```

   ```Output
   Log level configured successfully
   ```

2. 問題を再現する

3. Microsoft Defender for Endpoint ログをバックアップするために実行`sudo mdatp diagnostic create`します。 ファイルは、.zip アーカイブ内に格納されます。 このコマンドは、操作が成功した後、バックアップへのファイル パスも出力します。

   > [!TIP]
   > 既定では、診断ログは .`/Library/Application Support/Microsoft/Defender/wdavdiag/` 診断ログが保存されているディレクトリを変更するには、次のコマンドに渡 `--path [directory]` し、目的のディレクトリに置き換えます `[directory]` 。

   ```bash
   sudo mdatp diagnostic create
   ```

   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. ログ レベルを復元する:

   ```bash
   mdatp log level set --level info
   ```

   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a>インストールの問題のログ記録

インストール中にエラーが発生した場合、インストーラーは一般的なエラーのみを報告します。

詳細なログが保存 `/Library/Logs/Microsoft/mdatp/install.log`されます。 インストール中に問題が発生した場合は、原因の診断に役立つよう、このファイルを送信してください。

## <a name="uninstalling"></a>アンインストール

macOS でMicrosoft Defender for Endpointをアンインストールするには、いくつかの方法があります。 一元的に管理されたアンインストールは JAMF で使用できますが、Microsoft Intuneではまだ使用できないことに注意してください。

### <a name="interactive-uninstallation"></a>対話型アンインストール

- **Finder > アプリケーション** を開きます。 **[ごみ箱に移動] Microsoft Defender for Endpoint >** 右クリックします。

### <a name="supported-output-types"></a>サポートされている出力の種類

テーブルと JSON 形式の出力の種類をサポートします。 コマンドごとに、既定の出力動作があります。 次のコマンドを使用して、好みの出力形式で出力を変更できます。

`-output json`

`-output table`

### <a name="from-the-command-line"></a>コマンド ラインから

- `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`

## <a name="configuring-from-the-command-line"></a>コマンド ラインからの構成

製品設定の制御やオンデマンド スキャンのトリガーなどの重要なタスクは、コマンド ラインから実行できます。

|Group|シナリオ|コマンド|
|---|---|---|
|構成|リアルタイム保護のオン/オフを切り替える|`mdatp config real-time-protection --value [enabled/disabled]`|
|構成|クラウド保護のオン/オフを切り替える|`mdatp config cloud --value [enabled/disabled]`|
|構成|製品診断のオン/オフを切り替える|`mdatp config cloud-diagnostic --value [enabled/disabled]`|
|構成|サンプルの自動送信のオン/オフを切り替える|`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`|
|構成|許可されたリストに脅威名を追加する|`mdatp threat allowed add --name [threat-name]`|
|構成|許可されたリストから脅威名を削除する|`mdatp threat allowed remove --name [threat-name]`|
|構成|許可されているすべての脅威名を一覧表示する|`mdatp threat allowed list`|
|構成|PUA 保護を有効にする|`mdatp threat policy set --type potentially_unwanted_application -- action block`|
|構成|PUA 保護をオフにする|`mdatp threat policy set --type potentially_unwanted_application -- action off`|
|構成|PUA 保護の監査モードを有効にする|`mdatp threat policy set --type potentially_unwanted_application -- action audit`|
|構成|ウイルス対策パッシブ モードのオン/オフを切り替える|`mdatp config passive-mode --value [enabled/disabled]`|
|構成|オンデマンド スキャンの並列処理の程度を構成する|`mdatp config maximum-on-demand-scan-threads --value [numerical-value-between-1-and-64]`|
|構成|セキュリティ インテリジェンスの更新後にスキャンをオン/オフにする|`mdatp config scan-after-definition-update --value [enabled/disabled]`|
|構成|アーカイブ スキャンのオン/オフを切り替える (オンデマンド スキャンのみ)|`mdatp config scan-archives --value [enabled/disabled]`|
|構成|ファイル ハッシュの計算のオン/オフを切り替える|`mdatp config enable-file-hash-computation --value [enabled/disabled]`|
|構成|data_loss_preventionのオン/オフを切り替える|`mdatp config data_loss_prevention --value [enabled/disabled]`|
|診断|ログ レベルを変更する|`mdatp log level set --level [error/warning/info/verbose]`|
|診断|診断ログを生成する|`mdatp diagnostic create --path [directory]`|
|正常性|製品の正常性を確認する|`mdatp health`|
|正常性|spefic 製品属性を確認する|`mdatp health --field [attribute: healthy/licensed/engine_version...]`|
|保護|パスをスキャンする|`mdatp scan custom --path [path] [--ignore-exclusions]`|
|保護|クイック スキャンを実行する|`mdatp scan quick`|
|保護|フル スキャンを実行する|`mdatp scan full`|
|保護|進行中のオンデマンド スキャンをキャンセルする|`mdatp scan cancel`|
|保護|セキュリティ インテリジェンス更新プログラムを要求する|`mdatp definitions update`|
|EDR|Set/Remove タグ、サポートされている GROUP のみ|`mdatp edr tag set --name GROUP --value [name]`|
|EDR|デバイスからグループ タグを削除する|`mdatp edr tag remove --tag-name [name]`|
|EDR|グループ ID を追加する|`mdatp edr group-ids --group-id [group]`|

### <a name="how-to-enable-autocompletion"></a>オートコンプリートを有効にする方法

bash でオートコンプリートを有効にするには、次のコマンドを実行し、ターミナル セッションを再起動します。

```bash
echo "source /Applications/Microsoft\ Defender.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

zsh でオートコンプリートを有効にするには:

- デバイスでオートコンプリートが有効になっているかどうかを確認します。

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- 上記のコマンドで出力が生成されない場合は、次のコマンドを使用してオートコンプリートを有効にすることができます。

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- macOS でMicrosoft Defender for Endpointのオートコンプリートを有効にし、ターミナル セッションを再起動するには、次のコマンドを実行します。

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions

   sudo ln -svf "/Applications/Microsoft Defender.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>クライアント Microsoft Defender for Endpoint検疫ディレクトリ

`/Library/Application Support/Microsoft/Defender/quarantine/` によって検疫されたファイルが `mdatp`含まれています。 ファイルの名前は、脅威 trackingId の後に付けられます。 現在の trackingIds は `mdatp threat list`.

## <a name="microsoft-defender-for-endpoint-portal-information"></a>ポータル情報をMicrosoft Defender for Endpointする

[macOS の EDR 機能は](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)、Microsoft Defender for Endpoint ブログで、Microsoft Defender for Endpoint Security Center で期待される内容に関する詳細なガイダンスを提供するようになりました。
