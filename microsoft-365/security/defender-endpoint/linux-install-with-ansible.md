---
title: Linux でエンドポイント用のマイクロソフト ディフェンダーを展開する
ms.reviewer: ''
description: Ansible を使用して Linux 上にエンドポイント用のマイクロソフト ディフェンダーを展開する方法について説明します。
keywords: マイクロソフト, ディフェンダー, エンドポイント用マイクロソフトディフェンダー, Linux, インストール, 展開, アンインストール, 人形, アンシブル, Linux, Redhat, ubuntu, Debian, sles, suse, centos
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
ms.openlocfilehash: 36095f14ad3ed71c6a8d4707522c08c07ea738c4
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572731"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a>Linux でエンドポイント用のマイクロソフト ディフェンダーを展開する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> エンドポイントのディフェンダーを体験したいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

この記事では、Ansible を使用して Linux 上のエンドポイント用の Defender をデプロイする方法について説明します。 展開が正常に完了するには、次のすべてのタスクを完了する必要があります。

- [オンボード パッケージのダウンロード](#download-the-onboarding-package)
- [アンシブル YAML ファイルの作成](#create-ansible-yaml-files)
- [展開](#deployment)
- [References](#references)

## <a name="prerequisites-and-system-requirements"></a>前提条件とシステム要件

開始する前に、現在のソフトウェア バージョンの前提条件とシステム要件の説明については [、Linux のエンドポイントのメイン Defender](microsoft-defender-endpoint-linux.md) ページを参照してください。

さらに、Ansible 展開では、Ansible 管理タスクを理解し、Ansible を構成し、プレイブックとタスクの展開方法を知っている必要があります。 Ansible には、同じタスクを完了する多くの方法があります。 以下の手順では、パッケージの展開に役立つ *apt* や *アンアーカイブ* など、サポートされている Ansible モジュールの可用性を前提としています。 組織で別のワークフローを使用している場合があります。 詳細については [、Ansible のドキュメント](https://docs.ansible.com/) を参照してください。

- 少なくとも 1 台のコンピュータに Ansible をインストールする必要があります (Ansible はこれをコントロール ノードと呼びます)。
- SSH は、コントロール ノードとすべての管理対象ノード (Endpoint 用 Defender がインストールされるデバイス) との間の管理者アカウント用に構成する必要があり、公開キー認証を使用して構成することをお勧めします。
- すべての管理対象ノードに次のソフトウェアをインストールする必要があります。
  - カール
  - パイソン・アプト

- すべての管理対象ノードは、以下の形式で `/etc/ansible/hosts` 、または関連ファイルにリストされている必要があります。

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- ping テスト:

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a>オンボード パッケージのダウンロード

Microsoft Defender セキュリティ センターからオンボーディング パッケージをダウンロードします。

1. Microsoft Defender セキュリティ センターで、[**デバイス管理設定 >オンボード] >に移動** します。
2. 最初のドロップダウン メニューで、オペレーティング システムとして **[Linux サーバー]** を選択します。 2 番目のドロップダウン メニューで、デプロイメント方法として **[好みの Linux 構成管理ツール** ]を選択します。
3. [ **オンボード パッケージのダウンロード] を** 選択します。 ファイルをWindowsDefenderATPOnboardingPackage.zipとして保存します。

    ![Microsoft Defender セキュリティ センタースクリーンショット](images/atp-portal-onboarding-linux-2.png)

4. コマンド プロンプトで、ファイルがあることを確認します。 アーカイブの内容を抽出します。

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

## <a name="create-ansible-yaml-files"></a>アンシブル YAML ファイルの作成

プレイブックまたはタスクに貢献するサブタスクまたはロール ファイルを作成します。

- オンボーディング タスクを作成 `onboarding_setup.yml` します。

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

- エンドポイントリポジトリとキーの防御を追加 `add_apt_repo.yml` します。

    Linux 上のエンドポイントの防御者は、次のいずれかのチャネル (以下に *[channel]* と示す ) から展開できます: *内部関係者の高速*、 *内部の遅い*、または *prod*.これらのチャネルは、Linux ソフトウェア リポジトリに対応します。

    チャンネルの選択によって、デバイスに提供される更新の種類と頻度が決まります。 *インサイダー・ファスト* のデバイスは、アップデートや新機能を受け取る最初のデバイスで、後に *インサイダースロー* と最後に *prod*.

    新機能をプレビューし、早期にフィードバックを提供するために、企業内の一部のデバイスを *、インサイダー高速* または *インサイダースロー* のいずれかを使用するように設定することをお勧めします。

    > [!WARNING]
    > 初期インストール後にチャネルを切り替える場合は、製品を再インストールする必要があります。 製品チャネルを切り替えるには:既存のパッケージをアンインストールし、新しいチャネルを使用するようにデバイスを再構成し、このドキュメントの手順に従って新しい場所からパッケージをインストールします。

    ディストリビューションとバージョンをメモし、 の下で最も近いエントリを特定 `https://packages.microsoft.com/config/` します。

    次のコマンドでは *、[distro]* と *[version] を* 、指定した情報に置き換えます。

    > [!NOTE]
    > Oracle Linuxの場合は *、[distro]を"rhel"* に置き換えてください。

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      keyserver: https://packages.microsoft.com/
      id: BC528686B50D79E339D3721CEB3E94ADBE1229CF
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel].list
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

    - apt ベースのディストリビューションの場合は、次の YAML ファイルを使用します。

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

次に、タスク ファイルを `/etc/ansible/playbooks/` または関連するディレクトリで実行します。

- 取り付け：

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> 製品が初めて起動すると、最新のマルウェア対策定義がダウンロードされます。 インターネット接続によっては、この処理に数分かかる場合があります。

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

## <a name="log-installation-issues"></a>ログのインストールに関する問題

エラーが発生したときにインストーラーによって自動的に生成されたログを検索する方法の詳細については、「 [ログのインストールに関](linux-resources.md#log-installation-issues) する問題」を参照してください。

## <a name="operating-system-upgrades"></a>オペレーティング システムのアップグレード

オペレーティングシステムを新しいメジャーバージョンにアップグレードする場合は、まずLinux上でエンドポイント用のDefenderをアンインストールし、アップグレードをインストールし、最後にデバイス上のLinux上でエンドポイント用のDefenderを再設定する必要があります。

## <a name="references"></a>関連情報

- [YUM リポジトリの追加または削除](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [dnf パッケージマネージャーを使用してパッケージを管理する](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [APT リポジトリの追加と削除](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [apt-パッケージの管理](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a>関連項目
- [エージェントの正常性に関する問題の調査](health-status.md)
