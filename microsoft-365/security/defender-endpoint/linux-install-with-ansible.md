---
title: Ansible を使用して Linux にMicrosoft Defender for Endpointをデプロイする
ms.reviewer: ''
description: Ansible を使用して Linux にMicrosoft Defender for Endpointをデプロイする方法について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, Linux, インストール, デプロイ, アンインストール, Puppet, ansible, Linux, redhat, ubuntu, debian, sles, suse, centos, fedora, amazon Linux 2
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
ms.openlocfilehash: 57f0687fce422f26b76fc8b98a06ce0566f90f60
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476073"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Ansible を使用して Linux にMicrosoft Defender for Endpointをデプロイする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

この記事では、Ansible を使用して Linux 上に Defender for Endpoint をデプロイする方法について説明します。 展開を成功させるには、次のすべてのタスクを完了する必要があります。

- [オンボーディング パッケージをダウンロードする](#download-the-onboarding-package)
- [Ansible YAML ファイルを作成する](#create-ansible-yaml-files)
- [展開](#deployment)
- [関連情報](#references)

## <a name="prerequisites-and-system-requirements"></a>前提条件とシステム要件

作業を開始する前に、現在のソフトウェア バージョンの前提条件とシステム要件の説明については、 [メインの Defender for Endpoint on Linux ページ](microsoft-defender-endpoint-linux.md) を参照してください。

さらに、Ansible デプロイの場合は、Ansible 管理タスクに精通し、Ansible を構成し、プレイブックとタスクを展開する方法を理解する必要があります。 Ansible には、同じタスクを完了するための多くの方法があります。 これらの手順では、パッケージのデプロイに役立つ *apt* や *unarchive* など、サポートされている Ansible モジュールの可用性を前提としています。 組織が別のワークフローを使用している可能性があります。 詳細については、 [Ansible のドキュメント](https://docs.ansible.com/) を参照してください。

- Ansible は、少なくとも 1 つのコンピューターにインストールする必要があります (Ansible はこれをコントロール ノードと呼びます)。
- SSH は、コントロール ノードとすべてのマネージド ノード (Defender for Endpoint がインストールされるデバイス) 間の管理者アカウントに対して構成する必要があり、公開キー認証を使用して構成することをお勧めします。
- 次のソフトウェアは、すべてのマネージド ノードにインストールする必要があります。
  - カール
  - python-apt

- すべてのマネージド ノードは、次の形式で、または関連するファイルに `/etc/ansible/hosts` 一覧表示する必要があります。

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

Microsoft 365 Defender ポータルからオンボーディング パッケージをダウンロードします。

1. Microsoft 365 Defender ポータルで、**設定 > エンドポイント>デバイス管理>オンボードに** 移動します。
2. 最初のドロップダウン メニューで、オペレーティング システムとして **[Linux サーバー]** を選択します。 2 番目のドロップダウン メニューで、展開方法として [ **お好みの Linux 構成管理ツール** ] を選択します。
3. **[オンボーディング パッケージをダウンロードする]** を選択します。 ファイルを WindowsDefenderATPOnboardingPackage.zip として保存します。

   :::image type="content" source="images/portal-onboarding-linux-2.png" alt-text="[オンボード パッケージのダウンロード] オプション" lightbox="images/portal-onboarding-linux-2.png":::

4. コマンド プロンプトから、ファイルがあることを確認します。 アーカイブの内容を抽出します。

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

## <a name="create-ansible-yaml-files"></a>Ansible YAML ファイルを作成する

プレイブックまたはタスクに貢献するサブタスクまたはロール ファイルを作成します。

- オンボード タスク `onboarding_setup.yml`を作成します。

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

- Defender for Endpoint リポジトリとキー `add_apt_repo.yml`を追加します。

    Linux 用 Defender for Endpoint は、次のチャネル (以下、*[チャネル]* と表記) のいずれかから展開できます: *insiders-fast*、*insiders-slow*、または *prod*。これらの各チャネルは、Linux ソフトウェア リポジトリに対応しています。

    チャネルの選択により、デバイスに提供される更新プログラムの種類と頻度が決まります。 *insiders-fast* のデバイスが最初に更新プログラムと新機能を受け取り、その後に *insiders-slow*、最後に *prod* が続きます。

    新機能をプレビューし、早期のフィードバックを提供するために、企業内の一部のデバイスを *insiders-fast* または *insiders-slow* のいずれかを使用するように構成することをお勧めします。

    > [!WARNING]
    > 初期インストール後にチャネルを切り替えるには、製品を再インストールする必要があります。製品チャネルを切り替えるには: 既存のパッケージをアンインストールし、新しいチャネルを使用するようにデバイスを再構成し、このドキュメントの手順に従って新しい場所からパッケージをインストールします。

    ディストリビューションとバージョンをメモし、その下 `https://packages.microsoft.com/config/[distro]/`に最も近いエントリを特定します。

    次のコマンドで *、[distro]* と *[version] を* 特定した情報に置き換えます。

    > [!NOTE]
    > Oracle Linux と Amazon Linux 2 の場合は、[ *distro] を* "rhel" に置き換えます。

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      url: https://packages.microsoft.com/keys/microsoft.asc
      state: present
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [codename] main
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
      name: packages-microsoft-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/ 
      gpgcheck: yes
      enabled: Yes
    when: ansible_os_family == "RedHat"
  ```

- Ansible のインストールとアンインストールの YAML ファイルを作成します。

    - apt ベースのディストリビューションでは、次の YAML ファイルを使用します。

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

    - dnf ベースのディストリビューションの場合は、次の YAML ファイルを使用します。

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
                enablerepo: packages-microsoft-[channel]
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

次に、関連するディレクトリの下または関連するディレクトリで `/etc/ansible/playbooks/` タスク ファイルを実行します。

- インストール：

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> 製品が初めて起動すると、最新のウイルス対策定義がダウンロードされます。 インターネット接続によっては、これには数分かかる場合があります。

- 検証/構成:

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- アンインストール：

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a>インストールの問題をログする

エラーが発生したときにインストーラーによって作成される自動生成されたログを見つける方法の詳細については、「[インストールの問題をログする](linux-resources.md#log-installation-issues)」を参照してください。

## <a name="operating-system-upgrades"></a>オペレーティング システムのアップグレード

オペレーティング システムを新しいメジャー バージョンにアップグレードするときは、最初に Linux 用 Defender for Endpoint をアンインストールし、アップグレードをインストールしてから、最後にデバイスの Linux 用 Defender for Endpoint を再構成する必要があります。

## <a name="references"></a>関連情報

- [YUM リポジトリを追加または削除する](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [dnf パッケージ マネージャーを使用してパッケージを管理する](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [APT リポジトリの追加と削除](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [apt-packages を管理する](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a>関連項目
- [エージェントの正常性に関する問題の調査](health-status.md)
