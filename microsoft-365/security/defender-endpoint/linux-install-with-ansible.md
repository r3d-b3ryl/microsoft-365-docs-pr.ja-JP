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
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a><span data-ttu-id="7f1af-104">Linux でエンドポイント用のマイクロソフト ディフェンダーを展開する</span><span class="sxs-lookup"><span data-stu-id="7f1af-104">Deploy Microsoft Defender for Endpoint on Linux with Ansible</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7f1af-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7f1af-105">**Applies to:**</span></span>
- [<span data-ttu-id="7f1af-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7f1af-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7f1af-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f1af-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7f1af-108">エンドポイントのディフェンダーを体験したいですか?</span><span class="sxs-lookup"><span data-stu-id="7f1af-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7f1af-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="7f1af-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="7f1af-110">この記事では、Ansible を使用して Linux 上のエンドポイント用の Defender をデプロイする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-110">This article describes how to deploy Defender for Endpoint on Linux using Ansible.</span></span> <span data-ttu-id="7f1af-111">展開が正常に完了するには、次のすべてのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f1af-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="7f1af-112">オンボード パッケージのダウンロード</span><span class="sxs-lookup"><span data-stu-id="7f1af-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="7f1af-113">アンシブル YAML ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="7f1af-113">Create Ansible YAML files</span></span>](#create-ansible-yaml-files)
- [<span data-ttu-id="7f1af-114">展開</span><span class="sxs-lookup"><span data-stu-id="7f1af-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="7f1af-115">References</span><span class="sxs-lookup"><span data-stu-id="7f1af-115">References</span></span>](#references)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="7f1af-116">前提条件とシステム要件</span><span class="sxs-lookup"><span data-stu-id="7f1af-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="7f1af-117">開始する前に、現在のソフトウェア バージョンの前提条件とシステム要件の説明については [、Linux のエンドポイントのメイン Defender](microsoft-defender-endpoint-linux.md) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f1af-117">Before you get started, see [the main Defender for Endpoint on Linux page](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

<span data-ttu-id="7f1af-118">さらに、Ansible 展開では、Ansible 管理タスクを理解し、Ansible を構成し、プレイブックとタスクの展開方法を知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f1af-118">In addition, for Ansible deployment, you need to be familiar with Ansible administration tasks, have Ansible configured, and know how to deploy playbooks and tasks.</span></span> <span data-ttu-id="7f1af-119">Ansible には、同じタスクを完了する多くの方法があります。</span><span class="sxs-lookup"><span data-stu-id="7f1af-119">Ansible has many ways to complete the same task.</span></span> <span data-ttu-id="7f1af-120">以下の手順では、パッケージの展開に役立つ *apt* や *アンアーカイブ* など、サポートされている Ansible モジュールの可用性を前提としています。</span><span class="sxs-lookup"><span data-stu-id="7f1af-120">These instructions assume availability of supported Ansible modules, such as *apt* and *unarchive* to help deploy the package.</span></span> <span data-ttu-id="7f1af-121">組織で別のワークフローを使用している場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f1af-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="7f1af-122">詳細については [、Ansible のドキュメント](https://docs.ansible.com/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f1af-122">Refer to the [Ansible documentation](https://docs.ansible.com/) for details.</span></span>

- <span data-ttu-id="7f1af-123">少なくとも 1 台のコンピュータに Ansible をインストールする必要があります (Ansible はこれをコントロール ノードと呼びます)。</span><span class="sxs-lookup"><span data-stu-id="7f1af-123">Ansible needs to be installed on at least one computer (Ansible calls this the control node).</span></span>
- <span data-ttu-id="7f1af-124">SSH は、コントロール ノードとすべての管理対象ノード (Endpoint 用 Defender がインストールされるデバイス) との間の管理者アカウント用に構成する必要があり、公開キー認証を使用して構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f1af-124">SSH must be configured for an administrator account between the control node and all managed nodes (devices that will have Defender for Endpoint installed on them), and it is recommended to be configured with public key authentication.</span></span>
- <span data-ttu-id="7f1af-125">すべての管理対象ノードに次のソフトウェアをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f1af-125">The following software must be installed on all managed nodes:</span></span>
  - <span data-ttu-id="7f1af-126">カール</span><span class="sxs-lookup"><span data-stu-id="7f1af-126">curl</span></span>
  - <span data-ttu-id="7f1af-127">パイソン・アプト</span><span class="sxs-lookup"><span data-stu-id="7f1af-127">python-apt</span></span>

- <span data-ttu-id="7f1af-128">すべての管理対象ノードは、以下の形式で `/etc/ansible/hosts` 、または関連ファイルにリストされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f1af-128">All managed nodes must be listed in the following format in the `/etc/ansible/hosts` or relevant file:</span></span>

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- <span data-ttu-id="7f1af-129">ping テスト:</span><span class="sxs-lookup"><span data-stu-id="7f1af-129">Ping test:</span></span>

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="7f1af-130">オンボード パッケージのダウンロード</span><span class="sxs-lookup"><span data-stu-id="7f1af-130">Download the onboarding package</span></span>

<span data-ttu-id="7f1af-131">Microsoft Defender セキュリティ センターからオンボーディング パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="7f1af-131">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="7f1af-132">Microsoft Defender セキュリティ センターで、[**デバイス管理設定 >オンボード] >に移動** します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-132">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="7f1af-133">最初のドロップダウン メニューで、オペレーティング システムとして **[Linux サーバー]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-133">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="7f1af-134">2 番目のドロップダウン メニューで、デプロイメント方法として **[好みの Linux 構成管理ツール** ]を選択します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-134">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="7f1af-135">[ **オンボード パッケージのダウンロード] を** 選択します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-135">Select **Download onboarding package**.</span></span> <span data-ttu-id="7f1af-136">ファイルをWindowsDefenderATPOnboardingPackage.zipとして保存します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-136">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender セキュリティ センタースクリーンショット](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="7f1af-138">コマンド プロンプトで、ファイルがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-138">From a command prompt, verify that you have the file.</span></span> <span data-ttu-id="7f1af-139">アーカイブの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-139">Extract the contents of the archive:</span></span>

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

## <a name="create-ansible-yaml-files"></a><span data-ttu-id="7f1af-140">アンシブル YAML ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="7f1af-140">Create Ansible YAML files</span></span>

<span data-ttu-id="7f1af-141">プレイブックまたはタスクに貢献するサブタスクまたはロール ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-141">Create a subtask or role files that contribute to a playbook or task.</span></span>

- <span data-ttu-id="7f1af-142">オンボーディング タスクを作成 `onboarding_setup.yml` します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-142">Create the onboarding task, `onboarding_setup.yml`:</span></span>

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

- <span data-ttu-id="7f1af-143">エンドポイントリポジトリとキーの防御を追加 `add_apt_repo.yml` します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-143">Add the Defender for Endpoint repository and key, `add_apt_repo.yml`:</span></span>

    <span data-ttu-id="7f1af-144">Linux 上のエンドポイントの防御者は、次のいずれかのチャネル (以下に *[channel]* と示す ) から展開できます: *内部関係者の高速*、 *内部の遅い*、または *prod*.これらのチャネルは、Linux ソフトウェア リポジトリに対応します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-144">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

    <span data-ttu-id="7f1af-145">チャンネルの選択によって、デバイスに提供される更新の種類と頻度が決まります。</span><span class="sxs-lookup"><span data-stu-id="7f1af-145">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="7f1af-146">*インサイダー・ファスト* のデバイスは、アップデートや新機能を受け取る最初のデバイスで、後に *インサイダースロー* と最後に *prod*.</span><span class="sxs-lookup"><span data-stu-id="7f1af-146">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

    <span data-ttu-id="7f1af-147">新機能をプレビューし、早期にフィードバックを提供するために、企業内の一部のデバイスを *、インサイダー高速* または *インサイダースロー* のいずれかを使用するように設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="7f1af-147">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

    > [!WARNING]
    > <span data-ttu-id="7f1af-148">初期インストール後にチャネルを切り替える場合は、製品を再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f1af-148">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="7f1af-149">製品チャネルを切り替えるには:既存のパッケージをアンインストールし、新しいチャネルを使用するようにデバイスを再構成し、このドキュメントの手順に従って新しい場所からパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="7f1af-149">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

    <span data-ttu-id="7f1af-150">ディストリビューションとバージョンをメモし、 の下で最も近いエントリを特定 `https://packages.microsoft.com/config/` します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-150">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="7f1af-151">次のコマンドでは *、[distro]* と *[version] を* 、指定した情報に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="7f1af-151">In the following commands, replace *[distro]* and *[version]* with the information you've identified.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7f1af-152">Oracle Linuxの場合は *、[distro]を"rhel"* に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="7f1af-152">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

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

- <span data-ttu-id="7f1af-153">Ansible インストールを作成し、YAML ファイルをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="7f1af-153">Create the Ansible install and uninstall YAML files.</span></span>

    - <span data-ttu-id="7f1af-154">apt ベースのディストリビューションの場合は、次の YAML ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-154">For apt-based distributions use the following YAML file:</span></span>

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

    - <span data-ttu-id="7f1af-155">dnf ベースのディストリビューションの場合は、次の YAML ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-155">For dnf-based distributions use the following YAML file:</span></span>

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

## <a name="deployment"></a><span data-ttu-id="7f1af-156">展開</span><span class="sxs-lookup"><span data-stu-id="7f1af-156">Deployment</span></span>

<span data-ttu-id="7f1af-157">次に、タスク ファイルを `/etc/ansible/playbooks/` または関連するディレクトリで実行します。</span><span class="sxs-lookup"><span data-stu-id="7f1af-157">Now run the tasks files under `/etc/ansible/playbooks/` or relevant directory.</span></span>

- <span data-ttu-id="7f1af-158">取り付け：</span><span class="sxs-lookup"><span data-stu-id="7f1af-158">Installation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> <span data-ttu-id="7f1af-159">製品が初めて起動すると、最新のマルウェア対策定義がダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="7f1af-159">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="7f1af-160">インターネット接続によっては、この処理に数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="7f1af-160">Depending on your Internet connection, this can take up to a few minutes.</span></span>

- <span data-ttu-id="7f1af-161">検証/構成:</span><span class="sxs-lookup"><span data-stu-id="7f1af-161">Validation/configuration:</span></span>

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- <span data-ttu-id="7f1af-162">アンインストール:</span><span class="sxs-lookup"><span data-stu-id="7f1af-162">Uninstallation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a><span data-ttu-id="7f1af-163">ログのインストールに関する問題</span><span class="sxs-lookup"><span data-stu-id="7f1af-163">Log installation issues</span></span>

<span data-ttu-id="7f1af-164">エラーが発生したときにインストーラーによって自動的に生成されたログを検索する方法の詳細については、「 [ログのインストールに関](linux-resources.md#log-installation-issues) する問題」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f1af-164">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="7f1af-165">オペレーティング システムのアップグレード</span><span class="sxs-lookup"><span data-stu-id="7f1af-165">Operating system upgrades</span></span>

<span data-ttu-id="7f1af-166">オペレーティングシステムを新しいメジャーバージョンにアップグレードする場合は、まずLinux上でエンドポイント用のDefenderをアンインストールし、アップグレードをインストールし、最後にデバイス上のLinux上でエンドポイント用のDefenderを再設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f1af-166">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="references"></a><span data-ttu-id="7f1af-167">関連情報</span><span class="sxs-lookup"><span data-stu-id="7f1af-167">References</span></span>

- [<span data-ttu-id="7f1af-168">YUM リポジトリの追加または削除</span><span class="sxs-lookup"><span data-stu-id="7f1af-168">Add or remove YUM repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [<span data-ttu-id="7f1af-169">dnf パッケージマネージャーを使用してパッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="7f1af-169">Manage packages with the dnf package manager</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [<span data-ttu-id="7f1af-170">APT リポジトリの追加と削除</span><span class="sxs-lookup"><span data-stu-id="7f1af-170">Add and remove APT repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [<span data-ttu-id="7f1af-171">apt-パッケージの管理</span><span class="sxs-lookup"><span data-stu-id="7f1af-171">Manage apt-packages</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a><span data-ttu-id="7f1af-172">関連項目</span><span class="sxs-lookup"><span data-stu-id="7f1af-172">See also</span></span>
- [<span data-ttu-id="7f1af-173">エージェントの正常性に関する問題の調査</span><span class="sxs-lookup"><span data-stu-id="7f1af-173">Investigate agent health issues</span></span>](health-status.md)
