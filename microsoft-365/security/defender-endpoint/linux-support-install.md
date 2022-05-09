---
title: Linux でのMicrosoft Defender for Endpointのインストールに関する問題のトラブルシューティング
ms.reviewer: ''
description: Linux でのMicrosoft Defender for Endpointのインストールに関する問題のトラブルシューティング
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, インストール
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
ms.openlocfilehash: a0b2a571be5f78818279a343d253709e05814908
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62766017"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Linux でのMicrosoft Defender for Endpointのインストールに関する問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-that-the-installation-succeeded"></a>インストールが成功したことを確認する

インストール時にエラーが発生すると、パッケージ マネージャーによって意味のあるエラー メッセージが表示される場合とそうでない場合があります。 インストールが成功したかどうかを確認するには、次を使用してインストール ログを取得して確認します。

```bash
 sudo journalctl --no-pager|grep 'microsoft-mdatp' > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
```

インストールの日付と時刻が正しい前のコマンドからの出力は、成功を示します。

また、 [クライアント構成](linux-install-manually.md#client-configuration) を確認して製品の正常性を確認し、EICAR テキスト ファイルを検出します。

## <a name="make-sure-you-have-the-correct-package"></a>正しいパッケージがあることを確認する

インストールするパッケージがホストのディストリビューションとバージョンと一致することを確認します。

<br>

****

|package|配布|
|---|---|
|mdatp-rhel8.Linux.x86_64.rpm|Oracle、RHEL、CentOS 8.x|
|mdatp-sles12.Linux.x86_64.rpm|SUSE Linux Enterprise Server 12.x|
|mdatp-sles15.Linux.x86_64.rpm|SUSE Linux Enterprise Server 15.x|
|mdatp.Linux.x86_64.rpm|Oracle、RHEL、CentOS 7.x|
|mdatp.Linux.x86_64.eb|Debian と Ubuntu 16.04、18.04、20.04|
|

[手動デプロイ](linux-install-manually.md)の場合は、正しいディストリビューションとバージョンが選択されていることを確認します。

## <a name="installation-failed"></a>インストールに失敗しました

Defender for Endpoint サービスが実行されているかどうかを確認します。

```bash
service mdatp status
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

## <a name="steps-to-troubleshoot-if-the-mdatp-service-isnt-running"></a>mdatp サービスが実行されていない場合のトラブルシューティングの手順

1. "mdatp" ユーザーが存在するかどうかを確認します。

    ```bash
    id "mdatp"
    ```

    出力がない場合は、次のコマンドを実行します。

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. 次を使用してサービスを有効にして再起動してみてください。

    ```bash
    sudo service mdatp start
    ```

    ```bash
    sudo service mdatp restart
    ```

3. 前のコマンドの実行時に mdatp.service が見つからない場合は、次のコマンドを実行します。

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path> 
    ```

    ここで `<systemd_path>` 、Rhel、 `/lib/systemd/system` CentOS、Oracle、SLES の Ubuntu ディストリビューションと Debian ディストリビューションおよび /usr/lib/systemd/system' 用です。 次に、手順 2. を再実行します。

4. 上記の手順が機能しない場合は、SELinux がインストールされ、強制モードになっているかどうかを確認します。 その場合は、許可モード (できれば) または無効モードに設定してみてください。 これは、ファイル内`/etc/selinux/config`のパラメーター`SELINUX`を "許可" または "無効" に設定した後、再起動することによって実行できます。 詳細については、selinux のマニュアル ページを参照してください。
次に、手順 2. を使用して mdatp サービスを再起動してみてください。 セキュリティ上の理由から、構成変更を試して再起動した後、すぐに構成変更を元に戻します。

5. ディレクトリがシンボリック リンクの場合 `/opt` は、 `/opt/microsoft`.

6. デーモンに実行可能アクセス許可があることを確認します。

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    デーモンに実行可能アクセス許可がない場合は、次を使用して実行可能にします。

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    手順 2. を実行して再試行します。

7. wdavdaemon を含むファイル システムが "noexec" でマウントされていないことを確認します。

## <a name="if-the-defender-for-endpoint-service-is-running-but-the-eicar-text-file-detection-doesnt-work"></a>Defender for Endpoint サービスが実行されているのに EICAR テキスト ファイルの検出が機能しない場合

1. 次を使用してファイル システムの種類を確認します。

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    現在、オンアクセス アクティビティでサポートされているファイル システムを次に示 [します](microsoft-defender-endpoint-linux.md#system-requirements)。 これらのファイル システムの外部にあるファイルはスキャンされません。

## <a name="command-line-tool-mdatp-isnt-working"></a>コマンド ライン ツール "mdatp" が機能しない

1. コマンド ライン ツール `mdatp` を実行するとエラーが発生 `command not found`する場合は、次のコマンドを実行します。

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    もう一度やり直してください。

    上記の手順で解決しない場合は、診断ログを収集します。

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    ログを含む zip ファイルへのパスが出力として表示されます。 これらのログを使用して、カスタマー サポートにお問い合わせください。
