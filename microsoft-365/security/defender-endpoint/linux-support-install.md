---
title: Microsoft Defender for Endpoint on Linux のインストールに関する問題のトラブルシューティング
ms.reviewer: ''
description: Microsoft Defender for Endpoint on Linux のインストールに関する問題のトラブルシューティング
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, linux, installation
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c90841ac9312fcc5f36ae9807ce757d9268b4cea
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173093"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender for Endpoint on Linux のインストールに関する問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a>インストールが成功した場合の確認

インストール時にエラーが発生した場合と、パッケージ マネージャーによる意味のあるエラー メッセージが表示されない場合があります。 インストールが成功した場合は、以下を使用してインストール ログを取得して確認します。

```bash
 sudo journalctl --no-pager|grep 'microsoft-mdatp' > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
```

正しい日付とインストール時刻を持つ前のコマンドからの出力は、成功を示します。

また、クライアント構成 [を確認](linux-install-manually.md#client-configuration) して製品の正常性を確認し、EICAR テキスト ファイルを検出します。

## <a name="make-sure-you-have-the-correct-package"></a>正しいパッケージがインストールされていることを確認する

インストールするパッケージがホストの配布とバージョンと一致している場合に注意してください。

<br>

****

|package|配布|
|---|---|
|mdatp-rhel8。Linux.x86_64.rpm|Oracle、RHEL、CentOS 8.x|
|mdatp-sles12.Linux.x86_64.rpm|SuSE Linux Enterprise サーバー 12.x|
|mdatp-sles15.Linux.x86_64.rpm|SuSE Linux Enterprise サーバー 15.x|
|mdatp。Linux.x86_64.rpm|Oracle、RHEL、CentOS 7.x|
|mdatp。Linux.x86_64.deb|Debian と Ubuntu 16.04、18.04、20.04|
|

手動 [展開の場合](linux-install-manually.md)は、正しいディストリビューションとバージョンが選択されていることを確認します。

## <a name="installation-failed"></a>インストールに失敗しました

mdatp サービスが実行されている場合は、次のチェックを行います。

```bash
systemctl status mdatp
```

```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a>mdatp サービスが実行されていない場合のトラブルシューティング手順

1. "mdatp" ユーザーが存在するかどうかを確認します。

    ```bash
    id "mdatp"
    ```

    出力がない場合は、次のコマンドを実行します。

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. 次のコマンドを使用して、サービスを有効にし、再起動してみてください。

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. 前のコマンドを実行した際に mdatp.service が見つからない場合は、次のコマンドを実行します。

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    Ubuntu `<systemd_path>` `/lib/systemd/system` と Debian の配布と `/usr/lib/systemd/system` 、Rhel、CentOS、Oracle、SLES の場合です。
   次に、手順 2 を再実行します。

4. 上記の手順が機能しない場合は、SELinux がインストールされ、エンフォースモードになっているか確認してください。 その場合は、これを制限モード (できれば) または無効モードに設定してみてください。 これは、パラメーターをファイル内で "permissive" または "disabled" に設定し、その後再起動 `SELINUX` `/etc/selinux/config` することで実行できます。 詳細については、selinux のマン ページを確認してください。
次に、手順 2 を使用して mdatp サービスを再起動します。 試して再起動した後、セキュリティ上の理由から、構成の変更を直ちに元に戻します。

5. ディレクトリ `/opt` がシンボリック リンクの場合は、バインド マウントを作成します `/opt/microsoft` 。

6. デーモンが実行可能なアクセス許可を持っている必要があります。

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    デーモンに実行可能なアクセス許可が設定できない場合は、次のコマンドを使用して実行可能にします。

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    をクリックし、手順 2 の実行を再試行します。

7. wdavdaemon を含むファイル システムが "noexec" でマウントされていないか確認します。

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a>mdatp サービスが実行されているが、EICAR テキスト ファイルの検出が機能しない場合

1. 次を使用してファイル システムの種類を確認します。

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    現在、オンアクセス アクティビティでサポートされているファイル システムの一覧を次に示 [します](microsoft-defender-endpoint-linux.md#system-requirements)。 これらのファイル システム外のファイルはスキャンされません。

## <a name="command-line-tool-mdatp-isnt-working"></a>コマンド ライン ツール "mdatp" が機能しない

1. コマンド ライン ツールを実行するとエラーが `mdatp` 発生する場合は `command not found` 、次のコマンドを実行します。

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    もう一度やり直してください。

    上記の手順のいずれも問題が解決しない場合は、診断ログを収集します。

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    ログを含む zip ファイルへのパスが出力として表示されます。 これらのログを使用してカスタマー サポートに問い合わせください。
