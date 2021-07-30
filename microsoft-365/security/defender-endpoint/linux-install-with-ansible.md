---
title: Ansible を使用した Linux での Microsoft Defender for Endpoint の展開
ms.reviewer: ''
description: Ansible を使用して Microsoft Defender for Endpoint を Linux に展開する方法について説明します。
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
ms.openlocfilehash: c95c0e41fa37c0925e516312203c22cdd7a29768
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53651137"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Ansible を使用した Linux での Microsoft Defender for Endpoint の展開

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

この記事では、Ansible を使用して Defender for Endpoint を Linux に展開する方法について説明します。 展開が成功するには、次のすべてのタスクを完了する必要があります。

- [オンボーディング パッケージをダウンロードする](#download-the-onboarding-package)
- [Ansible YAML ファイルの作成](#create-ansible-yaml-files)
- [展開](#deployment)
- [関連情報](#references)

## <a name="prerequisites-and-system-requirements"></a>前提条件とシステム要件

開始する前に、現在のソフトウェア バージョンの前提条件とシステム要件の説明については、メインの [Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md) ページを参照してください。

さらに、Ansible 展開では、Ansible 管理タスクを理解し、Ansible を構成し、プレイブックとタスクを展開する方法を理解する必要があります。 Ansible には、同じタスクを実行する多くの方法があります。 これらの手順では、パッケージの展開に役立つ *apt* や *unarchive* など、サポートされている Ansible モジュールの可用性を前提とします。 組織で別のワークフローを使用する場合があります。 詳細については [、Ansible のドキュメント](https://docs.ansible.com/) を参照してください。

- Ansible は少なくとも 1 つのコンピューターにインストールする必要があります (Ansible はこれをコントロール ノードと呼び出します)。
- コントロール ノードとすべての管理ノード (Defender for Endpoint がインストールされているデバイス) の間の管理者アカウント用に SSH を構成する必要があります。公開キー認証を使用して構成する必要があります。
- 次のソフトウェアをすべての管理ノードにインストールする必要があります。
  - curl
  - python-apt

- すべての管理ノードは、関連するファイルに次の形式 `/etc/ansible/hosts` で一覧表示する必要があります。

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- Ping テスト:

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a>オンボーディング パッケージをダウンロードする

オンボーディング パッケージを次のポータルからMicrosoft 365 Defenderします。

1. [Microsoft 365 Defender] ポータルで、[デバイス管理設定 >オンボーディング>**エンドポイント>移動します**。
2. 最初のドロップダウン メニューで、オペレーティング システム **として [Linux Server]** を選択します。 2 番目のドロップダウン メニューで、展開 **方法として [優先する Linux 構成管理ツール** ] を選択します。
3. [オンボード **パッケージのダウンロード] を選択します**。 ファイルを [ファイル名] WindowsDefenderATPOnboardingPackage.zip。

    ![Microsoft 365 Defenderポータルのスクリーンショット](images/portal-onboarding-linux-2.png)

4. コマンド プロンプトから、ファイルが存在するように確認します。 アーカイブの内容を抽出します。

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-ansible-yaml-files"></a>Ansible YAML ファイルの作成

プレイブックまたはタスクに貢献するサブタスクまたは役割ファイルを作成します。

- オンボーディング タスクを作成します `onboarding_setup.yml` 。

    ```bash
    - name: Create MDATP directories
      file:
        path: /etc/opt/microsoft/mdatp/
        recurse: true
        state: directory
        mode: 0755
        owner: root
        group: root

    - name: Register mdatp_onboard.json
      stat:
        path: /etc/opt/microsoft/mdatp/mdatp_onboard.json
      register: mdatp_onboard

    - name: Extract WindowsDefenderATPOnboardingPackage.zip into /etc/opt/microsoft/mdatp
      unarchive:
        src: WindowsDefenderATPOnboardingPackage.zip
        dest: /etc/opt/microsoft/mdatp
        mode: 0600
        owner: root
        group: root
      when: not mdatp_onboard.stat.exists
    ```

- Defender for Endpoint リポジトリとキーを追加します `add_apt_repo.yml` 。

    Defender for Endpoint on Linux は、以下のいずれかのチャネル *([channel]* と示す) から展開できます。insiders-fast *、insiders-slow、**または prod* です。 これらの各チャネルは、Linux ソフトウェア リポジトリに対応します。

    チャネルの選択によって、デバイスに提供される更新プログラムの種類と頻度が決されます。 *insiders-fast* のデバイスは、更新プログラムと新機能を受け取る最初のデバイスで、後で *insiders-slow* と最後に *prod が続きます*。

    新機能をプレビューし、早期のフィードバックを提供するために、インサイダー高速またはインサイダー低速のいずれかを使用するために、企業の一部のデバイスを構成をお *勧めします*。

    > [!WARNING]
    > 最初のインストール後にチャネルを切り替える場合は、製品を再インストールする必要があります。 製品チャネルを切り替える: 既存のパッケージをアンインストールし、新しいチャネルを使用するデバイスを再構成し、このドキュメントの手順に従って新しい場所からパッケージをインストールします。

    配布とバージョンをメモし、その下の最も近いエントリを識別します `https://packages.microsoft.com/config/` 。

    次のコマンドで *、[distro]* と *[version]* を、特定した情報に置き換える必要があります。

    > [!NOTE]
    > Oracle Linux の場合 *、[distro] を "rhel"* に置き換える。

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      url: https://packages.microsoft.com/keys/microsoft.asc
      state: present
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel]
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-com-prod-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- Ansible インストールを作成し、YAML ファイルをアンインストールします。

    - apt ベースの配布では、次の YAML ファイルを使用します。

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - name: Install MDATP
              apt:
                name: mdatp
                state: latest
                update_cache: yes
        ```

        ```bash
        cat uninstall_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              apt:
                name: mdatp
                state: absent
        ```

    - dnf ベースの配布では、次の YAML ファイルを使用します。

        ```bash
        cat install_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - name: Install MDATP
              dnf:
                name: mdatp
                state: latest
                enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              dnf:
                name: mdatp
                state: absent
        ```

## <a name="deployment"></a>展開

次に、タスク ファイルを下または関連 `/etc/ansible/playbooks/` するディレクトリで実行します。

- インストール:

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> 製品が初めて起動すると、最新のマルウェア対策定義がダウンロードされます。 インターネット接続によっては、数分かかる場合があります。

- 検証/構成:

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- アンインストール:

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a>ログ インストールの問題

エラー [が発生した場合](linux-resources.md#log-installation-issues) にインストーラーによって作成される自動的に生成されたログを検索する方法の詳細については、「Log installation issues」を参照してください。

## <a name="operating-system-upgrades"></a>オペレーティング システムのアップグレード

オペレーティング システムを新しいメジャー バージョンにアップグレードする場合は、まず、Linux 上の Defender for Endpoint をアンインストールし、アップグレードをインストールし、最後にデバイス上で Defender for Endpoint on Linux を再構成する必要があります。

## <a name="references"></a>関連情報

- [YUM リポジトリの追加または削除](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [dnf パッケージ マネージャーを使用してパッケージを管理する](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [APT リポジトリの追加と削除](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [apt-packages の管理](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a>関連項目
- [エージェントの正常性に関する問題の調査](health-status.md)
