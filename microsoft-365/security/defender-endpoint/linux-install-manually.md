---
title: Linux での Microsoft Defender for Endpoint の手動展開
ms.reviewer: ''
description: コマンド ラインから手動で Microsoft Defender for Endpoint を Linux に展開する方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, Linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 704e44a61a89e176433058bc62ed02ed96001ed28fda38354b85e1cbc977545d
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53806876"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a>Linux での Microsoft Defender for Endpoint の手動展開

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

この記事では、Microsoft Defender for Endpoint を Linux に手動で展開する方法について説明します。 展開が成功するには、次のすべてのタスクを完了する必要があります。

- [Linux での Microsoft Defender for Endpoint の手動展開](#deploy-microsoft-defender-for-endpoint-on-linux-manually)
  - [前提条件とシステム要件](#prerequisites-and-system-requirements)
  - [Linux ソフトウェア リポジトリの構成](#configure-the-linux-software-repository)
    - [RHEL とバリアント (CentOS および Oracle Linux)](#rhel-and-variants-centos-and-oracle-linux)
    - [SLES とバリアント](#sles-and-variants)
    - [Ubuntu システムと Debian システム](#ubuntu-and-debian-systems)
  - [アプリケーションのインストール](#application-installation)
  - [オンボーディング パッケージをダウンロードする](#download-the-onboarding-package)
  - [クライアント構成](#client-configuration)
  - [インストーラー スクリプト](#installer-script)
  - [ログ インストールの問題](#log-installation-issues)
  - [オペレーティング システムのアップグレード](#operating-system-upgrades)
  - [アンインストール](#uninstallation)

## <a name="prerequisites-and-system-requirements"></a>前提条件とシステム要件

開始する前に、現在のソフトウェア バージョンの前提条件とシステム要件の説明については [、「Microsoft Defender for Endpoint on Linux」](microsoft-defender-endpoint-linux.md) を参照してください。

## <a name="configure-the-linux-software-repository"></a>Linux ソフトウェア リポジトリの構成

Defender for Endpoint on Linux は、以下のいずれかのチャネル *([channel]* と示す) から展開できます。insiders-fast *、insiders-slow、**または prod* です。 これらの各チャネルは、Linux ソフトウェア リポジトリに対応します。 これらのリポジトリのいずれかを使用するためにデバイスを構成する手順を以下に示します。

チャネルの選択によって、デバイスに提供される更新プログラムの種類と頻度が決されます。 *insiders-fast* のデバイスは、更新プログラムと新機能を受け取る最初のデバイスで、後で *insiders-slow* と最後に *prod が続きます*。

新機能をプレビューし、早期のフィードバックを提供するために、インサイダー高速またはインサイダー低速のいずれかを使用するために、企業の一部のデバイスを構成をお *勧めします*。

> [!WARNING]
> 最初のインストール後にチャネルを切り替える場合は、製品を再インストールする必要があります。 製品チャネルを切り替える: 既存のパッケージをアンインストールし、新しいチャネルを使用するデバイスを再構成し、このドキュメントの手順に従って新しい場所からパッケージをインストールします。

### <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL とバリアント (CentOS および Oracle Linux)

- まだ `yum-utils` インストールされていない場合はインストールします。

    ```bash
    sudo yum install yum-utils
    ```

- 配布とバージョンに注意し、その下の最も近いエントリ (メジャー、マイナー) を識別します `https://packages.microsoft.com/config/` 。 たとえば、RHEL 7.9 は 8 よりも 7.4 に近いです。

    以下のコマンドで *、[distro]* と *[version]* を、特定した情報に置き換える必要があります。

    > [!NOTE]
    > Oracle Linux の場合 *、[distro] を "rhel"* に置き換える。

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    たとえば、CentOS 7 を実行し、Prod チャネルから Linux 上の Defender for Endpoint を展開する場合は、次の *コマンドを実行* します。

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/prod.repo
    ```

    または、選択したデバイス上の新機能を確認する場合は、Linux 上の Microsoft Defender for Endpoint を *insiders-fast チャネルに展開* できます。

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/insiders-fast.repo
    ```

- Microsoft GPG 公開キーをインストールします。

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

- 現在有効になっている yum リポジトリのすべてのメタデータをダウンロードして使用可能にします。

    ```bash
    yum makecache
    ```

### <a name="sles-and-variants"></a>SLES とバリアント

- 配布とバージョンをメモし、その下で最も近いエントリ (メジャー、マイナー) を識別します `https://packages.microsoft.com/config/` 。

    次のコマンドで *、[distro]* と *[version]* を、特定した情報に置き換える必要があります。

    ```bash
    sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    たとえば、SLES 12 を実行し、Prod チャネルから Linux 上の Microsoft Defender for Endpoint を展開する場合は、次の *コマンドを実行* します。

    ```bash
    sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
    ```

- Microsoft GPG 公開キーをインストールします。

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a>Ubuntu システムと Debian システム

- まだ `curl` インストールされていない場合はインストールします。

    ```bash
    sudo apt-get install curl
    ```

- まだ `libplist-utils` インストールされていない場合はインストールします。

    ```bash
    sudo apt-get install libplist-utils
    ```

- 配布とバージョンに注意し、その下の最も近いエントリ (メジャー、マイナー) を識別します `https://packages.microsoft.com/config` 。

    次のコマンドで *、[distro]* と *[version]* を、特定した情報に置き換える必要があります。

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
    ```

    たとえば、Ubuntu 18.04 を実行し *、Prod* チャネルから Linux 用 MDE を展開する場合は、次のようにします。

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
    ```

- リポジトリ構成をインストールします。

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```

    たとえば、prod チャネル *を選択した* 場合は、次のようになります。

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```

- まだインストール `gpg` されていない場合は、パッケージをインストールします。

    ```bash
    sudo apt-get install gpg
    ```

  使用 `gpg` できない場合は、インストールします `gnupg` 。

- Microsoft GPG 公開キーをインストールします。

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- https ドライバーが存在しない場合は、インストールします。

    ```bash
    sudo apt-get install apt-transport-https
    ```

- リポジトリ のメタデータを更新します。

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a>アプリケーションのインストール

- RHEL とバリアント (CentOS および Oracle Linux):

    ```bash
    sudo yum install mdatp
    ```

    デバイスに複数の Microsoft リポジトリが構成されている場合は、パッケージをインストールするリポジトリを特定できます。 次の例は、このデバイスでリポジトリ チャネルも構成されている場合に、チャネルからパッケージをインストール `production` `insiders-fast` する方法を示しています。 この状況は、デバイスで複数の Microsoft 製品を使用している場合に発生する可能性があります。 サーバーの配布とバージョンによっては、リポジトリ エイリアスが次の例と異なる場合があります。

    ```bash
    # list all repositories
    yum repolist
    ```

    ```Output
    ...
    packages-microsoft-com-prod               packages-microsoft-com-prod        316
    packages-microsoft-com-prod-insiders-fast packages-microsoft-com-prod-ins      2
    ...
    ```

    ```bash
    # install the package from the production repository
    sudo yum --enablerepo=packages-microsoft-com-prod install mdatp
    ```

- SLES とバリアント:

    ```bash
    sudo zypper install mdatp
    ```

    デバイスに複数の Microsoft リポジトリが構成されている場合は、パッケージをインストールするリポジトリを特定できます。 次の例は、このデバイスでリポジトリ チャネルも構成されている場合に、チャネルからパッケージをインストール `production` `insiders-fast` する方法を示しています。 この状況は、デバイスで複数の Microsoft 製品を使用している場合に発生する可能性があります。

    ```bash
    zypper repos
    ```

    ```Output
    ...
    #  | Alias | Name | ...
    XX | packages-microsoft-com-insiders-fast | microsoft-insiders-fast | ...
    XX | packages-microsoft-com-prod | microsoft-prod | ...
    ...

    ```

    ```bash
    sudo zypper install packages-microsoft-com-prod:mdatp
    ```

- Ubuntu および Debian システム:

    ```bash
    sudo apt-get install mdatp
    ```

    デバイスに複数の Microsoft リポジトリが構成されている場合は、パッケージをインストールするリポジトリを特定できます。 次の例は、このデバイスでリポジトリ チャネルも構成されている場合に、チャネルからパッケージをインストール `production` `insiders-fast` する方法を示しています。 この状況は、デバイスで複数の Microsoft 製品を使用している場合に発生する可能性があります。

    ```bash
    cat /etc/apt/sources.list.d/*
    ```

    ```Output
    deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/ubuntu/18.04/prod insiders-fast main
    deb [arch=amd64] https://packages.microsoft.com/ubuntu/18.04/prod bionic main
    ```

    ```bash
    sudo apt -t bionic install mdatp
    ```

## <a name="download-the-onboarding-package"></a>オンボーディング パッケージをダウンロードする

オンボーディング パッケージを次のポータルからMicrosoft 365 Defenderします。

1. ポータルで、[Microsoft 365 Defenderオンボーディング] の [設定 >エンドポイント>**に移動>します**。
2. 最初のドロップダウン メニューで、オペレーティング システム **として [Linux Server]** を選択します。 2 番目のドロップダウン メニューで、展開 **方法として [ローカル スクリプト** ] を選択します。
3. [オンボード **パッケージのダウンロード] を選択します**。 ファイルを [ファイル名] WindowsDefenderATPOnboardingPackage.zip。

    ![Microsoft 365 Defenderポータルのスクリーンショット](images/portal-onboarding-linux.png)

4. コマンド プロンプトから、ファイルが存在するように確認します。
    アーカイブの内容を抽出します。

    ```bash
    ls -l
    ```

    ```Output
    total 8
    -rw-r--r-- 1 test  staff  5752 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```

    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

## <a name="client-configuration"></a>クライアント構成

1. ターゲット MicrosoftDefenderATPOnboardingLinuxServer.py にコピーします。

    最初は、クライアント デバイスは組織に関連付けではありません。 *orgId 属性は空白* です。

    ```bash
    mdatp health --field org_id
    ```

2. 実行 MicrosoftDefenderATPOnboardingLinuxServer.py。

    > [!NOTE]
    > このコマンドを実行するには、デバイスに `python` インストールされている必要があります。 RHEL 8.x または Ubuntu 20.04 以降を実行している場合は、Python ではなく Python 3 を使用する必要があります。

    ```bash
    python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. デバイスが組織に関連付けられていると確認し、有効な組織識別子を報告します。

    ```bash
    mdatp health --field org_id
    ```

4. インストールが完了した数分後に、次のコマンドを実行して状態を確認できます。 戻り値は `1` 、製品が期待通り機能している状態であることを示します。

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > 製品が初めて起動すると、最新のマルウェア対策定義がダウンロードされます。 インターネット接続によっては、数分かかる場合があります。 この間、上記のコマンドはの値を返します `false` 。 定義の更新の状態は、次のコマンドを使用して確認できます。
    >
    > ```bash
    > mdatp health --field definitions_status
    > ```
    >
    > 初期インストールの完了後にプロキシの構成が必要な場合があります。 「Configure Defender for Endpoint on Linux for static proxy [discovery: Post-installation configuration」を参照してください](/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration)。

5. 検出テストを実行して、デバイスが適切にオンボードされ、サービスに報告されていることを確認します。 新しくオンボードされたデバイスで次の手順を実行します。

    - リアルタイム保護が有効であることを確認します (次のコマンドを実行した結果 `1` で示されます)。

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    - ターミナル ウィンドウを開きます。 次のコマンドをコピーして実行します。

        ``` bash
        curl -o /tmp/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - このファイルは、Linux 上の Defender for Endpoint によって検疫されている必要があります。 次のコマンドを使用して、検出された脅威の一覧を表示します。

        ```bash
        mdatp threat list
        ```

## <a name="experience-linux-endpoint-detection-and-response-edr-capabilities-with-simulated-attacks"></a>シミュレートされた攻撃で Linux エンドポイントの検出と応答 (EDR) 機能を体験する

Linux 用の EDR機能をテストするには、以下の手順に従って、Linux サーバーでの検出をシミュレートし、ケースを調査します。

1. オンボードされた Linux サーバーがサーバーに表示Microsoft 365 Defender。 これがコンピューターの最初のオンボーディングである場合、表示されるまでに最大 20 分かかる場合があります。

2. スクリプト ファイルをダウンロード [してオンボード](https://aka.ms/LinuxDIY) の Linux サーバーに展開し、次のコマンドを実行します。 `./mde_linux_edr_diy.sh`

3. 数分後に、検出が発生する必要Microsoft 365 Defender。

4. アラートの詳細、コンピューターのタイムラインを確認し、一般的な調査手順を実行します。

## <a name="installer-script"></a>インストーラー スクリプト

または、パブリック リポジトリで提供されている自動[](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh)インストーラー bash[スクリプトGitHubすることもできます](https://github.com/microsoft/mdatp-xplat/)。
スクリプトは配布とバージョンを識別し、最新のパッケージをプルしてインストールするデバイスをセットアップします。
指定されたスクリプトを使用してオンボードすることもできます。

```bash
❯ ./mde_installer.sh --help
usage: basename ./mde_installer.sh [OPTIONS]
Options:
-c|--channel      specify the channel from which you want to install. Default: insiders-fast
-i|--install      install the product
-r|--remove       remove the product
-u|--upgrade      upgrade the existing product
-o|--onboard      onboard/offboard the product with <onboarding_script>
-p|--passive-mode set EPP to passive mode
-t|--tag          set a tag by declaring <name> and <value>. ex: -t GROUP Coders
-m|--min_req      enforce minimum requirements
-w|--clean        remove repo from package manager for a specific channel
-v|--version      print out script version
-h|--help         display help
```

詳細については、 [こちらを参照してください](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation)。

## <a name="log-installation-issues"></a>ログ インストールの問題

エラー [が発生した場合](linux-resources.md#log-installation-issues) にインストーラーによって作成される自動的に生成されたログを検索する方法の詳細については、「Log installation issues」を参照してください。

## <a name="operating-system-upgrades"></a>オペレーティング システムのアップグレード

オペレーティング システムを新しいメジャー バージョンにアップグレードする場合は、まず、Linux 上の Defender for Endpoint をアンインストールし、アップグレードをインストールし、最後にデバイス上で Defender for Endpoint on Linux を再構成する必要があります。

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a>サーバーから実稼働チャネルInsiders-Fast移行する方法

1. Linux 上のエンドポイント用 Defender の "Insiders-Fast チャネル" バージョンをアンインストールします。

    ```bash
    sudo yum remove mdatp
    ```

1. Linux サーバーのエンドポイントの Defender を無効Insiders-Fastします。

    ```bash
    sudo yum repolist
    ```

    > [!NOTE]
    > 出力には "packages-microsoft-com-fast-prod" が表示されます。

    ```bash
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ```

1. "実稼働チャネル" を使用して Linux 用 MDE を再展開します。

## <a name="uninstallation"></a>アンインストール

クライアント デバイス [から Linux](linux-resources.md#uninstall) 上の Defender for Endpoint を削除する方法の詳細については、「アンインストール」を参照してください。

## <a name="see-also"></a>関連項目

- [エージェントの正常性に関する問題の調査](health-status.md)
