---
title: Microsoft Defender for Endpoint on Mac のリソース
description: Microsoft Defender for Endpoint on Mac のリソース (アンインストール方法、診断ログの収集方法、CLI コマンド、製品に関する既知の問題など)。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7d09ce01bc8d9409d4537df8eaabb50915538aa6
ms.sourcegitcommit: 6a73f0f0c0360fc015d9c0d0af26fb6926d9477d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58747401"
---
# <a name="resources-for-microsoft-defender-for-endpoint-on-macos"></a>macOS 上のエンドポイント用 Microsoft Defender のリソース

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="collecting-diagnostic-information"></a>診断情報の収集

問題を再現できる場合は、ログ レベルを上げ、システムを一時実行し、ログ レベルを既定に復元します。

1. ログ レベルを上げ:

   ```bash
   mdatp log level set --level verbose
   ```

   ```Output
   Log level configured successfully
   ```

2. 問題を再現する

3. Microsoft `sudo mdatp diagnostic create` Defender for Endpoint ログをバックアップするために実行します。 ファイルは、アーカイブ内に.zipされます。 このコマンドは、操作が成功した後、バックアップへのファイル パスも出力します。

   > [!TIP]
   > 既定では、診断ログはに保存されます `/Library/Application Support/Microsoft/Defender/wdavdiag/` 。 診断ログが保存されているディレクトリを変更するには、次のコマンドに渡し、目的の `--path [directory]` `[directory]` ディレクトリに置き換わります。

   ```bash
   sudo mdatp diagnostic create
   ```

   ```console
   Diagnostic file created: "/Library/Application Support/Microsoft/Defender/wdavdiag/932e68a8-8f2e-4ad0-a7f2-65eb97c0de01.zip"
   ```

4. ログ レベルの復元:

   ```bash
   mdatp log level set --level info
   ```

   ```console
   Log level configured successfully
   ```

## <a name="logging-installation-issues"></a>インストールの問題をログに記録する

インストール中にエラーが発生した場合、インストーラーは一般的なエラーのみを報告します。

詳細ログはに保存されます `/Library/Logs/Microsoft/mdatp/install.log` 。 インストール中に問題が発生した場合は、このファイルを送信して、原因の診断に役立ちます。

## <a name="uninstalling"></a>アンインストール

macOS で Microsoft Defender for Endpoint をアンインストールするには、いくつかの方法があります。 JAMF では一般に管理されたアンインストールは使用できませんが、このアンインストールはMicrosoft Intune。

### <a name="interactive-uninstallation"></a>対話型アンインストール

- Finder **ファイル>開きます**。 [Microsoft **Defender for Endpoint] を右クリックし>に移動します**。

### <a name="from-the-command-line"></a>コマンド ラインから

- `sudo '/Library/Application Support/Microsoft/Defender/uninstall/uninstall'`

## <a name="configuring-from-the-command-line"></a>コマンド ラインからの構成

製品設定の制御やオンデマンド スキャンのトリガーなどの重要なタスクは、コマンド ラインから実行できます。

|グループ|シナリオ|コマンド|
|---|---|---|
|構成|リアルタイム保護のオン/オフ|`mdatp config real-time-protection --value [enabled/disabled]`|
|構成|クラウド保護のオン/オフ|`mdatp config cloud --value [enabled/disabled]`|
|構成|製品診断のオン/オフ|`mdatp config cloud-diagnostic --value [enabled/disabled]`|
|構成|自動サンプル申請のオン/オフ|`mdatp config cloud-automatic-sample-submission --value [enabled/disabled]`|
|構成|許可リストに脅威名を追加する|`mdatp threat allowed add --name [threat-name]`|
|構成|許可リストから脅威名を削除する|`mdatp threat allowed remove --name [threat-name]`|
|構成|許可されている脅威名の一覧を表示する|`mdatp threat allowed list`|
|構成|PUA 保護を有効にする|`mdatp threat policy set --type potentially_unwanted_application -- action block`|
|構成|PUA 保護をオフにする|`mdatp threat policy set --type potentially_unwanted_application -- action off`|
|構成|PUA 保護の監査モードを有効にする|`mdatp threat policy set --type potentially_unwanted_application -- action audit`|
|構成|パッシブ モードのオン/オフ|`mdatp config passive-mode --value enabled [enabled/disabled]`|
|Diagnostics|ログ レベルの変更|`mdatp log level set --level [error/warning/info/verbose]`|
|Diagnostics|診断ログの生成|`mdatp diagnostic create --path [directory]`|
|正常性|製品の正常性を確認する|`mdatp health`|
|正常性|spefic 製品属性を確認する|`mdatp health --field [attribute: healthy/licensed/engine_version...]`|
|保護|パスをスキャンする|`mdatp scan custom --path [path] [--ignore-exclusions]`|
|保護|クイック スキャンを実行する|`mdatp scan quick`|
|保護|フル スキャンを実行する|`mdatp scan full`|
|保護|進行中のオンデマンド スキャンをキャンセルする|`mdatp scan cancel`|
|保護|セキュリティ インテリジェンス更新プログラムの要求|`mdatp definitions update`|
|EDR|デバイスにグループ タグを追加します。 EDRタグは、デバイス グループの管理に使用されます。 詳細については、「/microsoft-365/security/defender-endpoint/machine-groups」を参照してください。|`mdatp edr tag set --name GROUP --value [name]`|
|EDR|デバイスからグループ タグを削除する|`mdatp edr tag remove --tag-name [name]`|
|EDR|グループ ID の追加|`mdatp edr group-ids --group-id [group]`|

### <a name="how-to-enable-autocompletion"></a>オートコンプリートを有効にする方法

bash でオートコンプリートを有効にするには、次のコマンドを実行し、ターミナル セッションを再起動します。

```bash
echo "source /Applications/Microsoft\ Defender\ ATP.app/Contents/Resources/Tools/mdatp_completion.bash" >> ~/.bash_profile
```

zsh でオートコンプリートを有効にするには、次の方法を実行します。

- デバイスでオートコンプリートが有効になっているかどうかを確認します。

   ```zsh
   cat ~/.zshrc | grep autoload
   ```

- 前のコマンドで出力が生成されない場合は、次のコマンドを使用してオートコンプリートを有効にできます。

   ```zsh
   echo "autoload -Uz compinit && compinit" >> ~/.zshrc
   ```

- 次のコマンドを実行して、macOS 上の Microsoft Defender for Endpoint のオートコンプリートを有効にし、ターミナル セッションを再起動します。

   ```zsh
   sudo mkdir -p /usr/local/share/zsh/site-functions

   sudo ln -svf "/Applications/Microsoft Defender ATP.app/Contents/Resources/Tools/mdatp_completion.zsh" /usr/local/share/zsh/site-functions/_mdatp
   ```

## <a name="client-microsoft-defender-for-endpoint-quarantine-directory"></a>エンドポイント検疫ディレクトリのクライアント Microsoft Defender

`/Library/Application Support/Microsoft/Defender/quarantine/` によって検疫されたファイルが含まれる `mdatp` 。 ファイルの名前は、脅威の追跡 Id にちなんで指定されます。 現在の trackingIds は 、 と一緒に表示されます `mdatp threat list` 。

## <a name="microsoft-defender-for-endpoint-portal-information"></a>Microsoft Defender for Endpoint ポータル情報

[EDR macOS](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/edr-capabilities-for-macos-have-now-arrived/ba-p/1047801)の機能が到着しました。Microsoft Defender for Endpoint ブログでは、Microsoft Defender for Endpoint Security Center で何を期待するのかについて詳細なガイダンスが提供されています。
