---
title: Ansible を使用した Linux での Microsoft Defender for Endpoint の展開
ms.reviewer: ''
description: Ansible を使用して Microsoft Defender for Endpoint を Linux に展開する方法について説明します。
keywords: microsoft、 defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 697fcddad595c6883fe1e1f7258ca6154c48b94d
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903906"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a><span data-ttu-id="ae464-104">Ansible を使用した Linux での Microsoft Defender for Endpoint の展開</span><span class="sxs-lookup"><span data-stu-id="ae464-104">Deploy Microsoft Defender for Endpoint on Linux with Ansible</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ae464-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ae464-105">**Applies to:**</span></span>
- [<span data-ttu-id="ae464-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="ae464-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ae464-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ae464-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ae464-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="ae464-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ae464-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="ae464-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="ae464-110">この記事では、Ansible を使用して Defender for Endpoint for Linux を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ae464-110">This article describes how to deploy Defender for Endpoint for Linux using Ansible.</span></span> <span data-ttu-id="ae464-111">展開が成功するには、次のすべてのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae464-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="ae464-112">オンボーディング パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="ae464-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="ae464-113">Ansible YAML ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="ae464-113">Create Ansible YAML files</span></span>](#create-ansible-yaml-files)
- [<span data-ttu-id="ae464-114">展開</span><span class="sxs-lookup"><span data-stu-id="ae464-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="ae464-115">References</span><span class="sxs-lookup"><span data-stu-id="ae464-115">References</span></span>](#references)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="ae464-116">前提条件とシステム要件</span><span class="sxs-lookup"><span data-stu-id="ae464-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="ae464-117">開始する前に、現在のソフトウェア バージョンの前提条件とシステム要件の説明については、メインの [Defender for Endpoint for Linux](microsoft-defender-endpoint-linux.md) ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae464-117">Before you get started, see [the main Defender for Endpoint for Linux page](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

<span data-ttu-id="ae464-118">さらに、Ansible 展開では、Ansible 管理タスクを理解し、Ansible を構成し、プレイブックとタスクを展開する方法を理解する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae464-118">In addition, for Ansible deployment, you need to be familiar with Ansible administration tasks, have Ansible configured, and know how to deploy playbooks and tasks.</span></span> <span data-ttu-id="ae464-119">Ansible には、同じタスクを実行する多くの方法があります。</span><span class="sxs-lookup"><span data-stu-id="ae464-119">Ansible has many ways to complete the same task.</span></span> <span data-ttu-id="ae464-120">これらの手順では、パッケージの展開に役立つ *apt* や *unarchive* など、サポートされている Ansible モジュールの可用性を前提とします。</span><span class="sxs-lookup"><span data-stu-id="ae464-120">These instructions assume availability of supported Ansible modules, such as *apt* and *unarchive* to help deploy the package.</span></span> <span data-ttu-id="ae464-121">組織で別のワークフローを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae464-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="ae464-122">詳細については [、Ansible のドキュメント](https://docs.ansible.com/) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae464-122">Refer to the [Ansible documentation](https://docs.ansible.com/) for details.</span></span>

- <span data-ttu-id="ae464-123">Ansible は、少なくとも 1 つのコンピューターにインストールする必要があります (プライマリ コンピューターと呼ぶ)。</span><span class="sxs-lookup"><span data-stu-id="ae464-123">Ansible needs to be installed on at least one computer (we will call it the primary computer).</span></span>
- <span data-ttu-id="ae464-124">プライマリ コンピューターとすべてのクライアントの間で管理者アカウント用に SSH を構成する必要があります。公開キー認証を使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae464-124">SSH must be configured for an administrator account between the primary computer and all clients, and it is recommended be configured with public key authentication.</span></span>
- <span data-ttu-id="ae464-125">次のソフトウェアをすべてのクライアントにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae464-125">The following software must be installed on all clients:</span></span>
  - <span data-ttu-id="ae464-126">curl</span><span class="sxs-lookup"><span data-stu-id="ae464-126">curl</span></span>
  - <span data-ttu-id="ae464-127">python-apt</span><span class="sxs-lookup"><span data-stu-id="ae464-127">python-apt</span></span>

- <span data-ttu-id="ae464-128">すべてのホストは、関連するファイルに次の形式 `/etc/ansible/hosts` で一覧表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae464-128">All hosts must be listed in the following format in the `/etc/ansible/hosts` or relevant file:</span></span>

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- <span data-ttu-id="ae464-129">Ping テスト:</span><span class="sxs-lookup"><span data-stu-id="ae464-129">Ping test:</span></span>

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="ae464-130">オンボーディング パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="ae464-130">Download the onboarding package</span></span>

<span data-ttu-id="ae464-131">Microsoft Defender セキュリティ センターからオンボーディング パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ae464-131">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="ae464-132">Microsoft Defender セキュリティ センターで、[デバイス管理とオンボード **>設定>移動します**。</span><span class="sxs-lookup"><span data-stu-id="ae464-132">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="ae464-133">最初のドロップダウン メニューで、オペレーティング システム **として [Linux Server]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae464-133">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="ae464-134">2 番目のドロップダウン メニューで、展開 **方法として [優先する Linux 構成管理ツール** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ae464-134">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="ae464-135">[オンボード **パッケージのダウンロード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="ae464-135">Select **Download onboarding package**.</span></span> <span data-ttu-id="ae464-136">ファイルを [ファイル名] WindowsDefenderATPOnboardingPackage.zip。</span><span class="sxs-lookup"><span data-stu-id="ae464-136">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender セキュリティ センターのスクリーンショット](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="ae464-138">コマンド プロンプトから、ファイルが存在するように確認します。</span><span class="sxs-lookup"><span data-stu-id="ae464-138">From a command prompt, verify that you have the file.</span></span> <span data-ttu-id="ae464-139">アーカイブの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="ae464-139">Extract the contents of the archive:</span></span>

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

## <a name="create-ansible-yaml-files"></a><span data-ttu-id="ae464-140">Ansible YAML ファイルの作成</span><span class="sxs-lookup"><span data-stu-id="ae464-140">Create Ansible YAML files</span></span>

<span data-ttu-id="ae464-141">プレイブックまたはタスクに貢献するサブタスクファイルまたは役割ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="ae464-141">Create a subtask or role files that contribute to an playbook or task.</span></span>

- <span data-ttu-id="ae464-142">オンボーディング タスクを作成します `onboarding_setup.yml` 。</span><span class="sxs-lookup"><span data-stu-id="ae464-142">Create the onboarding task, `onboarding_setup.yml`:</span></span>

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

- <span data-ttu-id="ae464-143">Defender for Endpoint リポジトリとキーを追加します。</span><span class="sxs-lookup"><span data-stu-id="ae464-143">Add the Defender for Endpoint repository and key.</span></span>

    <span data-ttu-id="ae464-144">Defender for Endpoint for Linux は、以下のいずれかのチャネル *([channel] と* 示す) から展開できます。insiders-fast *、insiders-slow、\*\*または prod* です。 これらの各チャネルは、Linux ソフトウェア リポジトリに対応します。</span><span class="sxs-lookup"><span data-stu-id="ae464-144">Defender for Endpoint for Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

    <span data-ttu-id="ae464-145">チャネルの選択によって、デバイスに提供される更新プログラムの種類と頻度が決されます。</span><span class="sxs-lookup"><span data-stu-id="ae464-145">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="ae464-146">*insiders-fast* のデバイスは、更新プログラムと新機能を受け取る最初のデバイスで、後で *insiders-slow* と最後に *prod が続きます*。</span><span class="sxs-lookup"><span data-stu-id="ae464-146">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

    <span data-ttu-id="ae464-147">新機能をプレビューし、早期のフィードバックを提供するために、インサイダー高速またはインサイダー低速のいずれかを使用するために、企業の一部のデバイスを構成をお *勧めします*。</span><span class="sxs-lookup"><span data-stu-id="ae464-147">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

    > [!WARNING]
    > <span data-ttu-id="ae464-148">最初のインストール後にチャネルを切り替える場合は、製品を再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae464-148">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="ae464-149">製品チャネルを切り替える: 既存のパッケージをアンインストールし、新しいチャネルを使用するデバイスを再構成し、このドキュメントの手順に従って新しい場所からパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae464-149">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

    <span data-ttu-id="ae464-150">配布とバージョンをメモし、その下の最も近いエントリを識別します `https://packages.microsoft.com/config/` 。</span><span class="sxs-lookup"><span data-stu-id="ae464-150">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="ae464-151">次のコマンドで *、[distro]* と *[version]* を、特定した情報に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae464-151">In the following commands, replace *[distro]* and *[version]* with the information you've identified.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ae464-152">Oracle Linux の場合 *、[distro] を "rhel"* に置き換える。</span><span class="sxs-lookup"><span data-stu-id="ae464-152">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

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

- <span data-ttu-id="ae464-153">Ansible インストールを作成し、YAML ファイルをアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="ae464-153">Create the Ansible install and uninstall YAML files.</span></span>

    - <span data-ttu-id="ae464-154">apt ベースの配布では、次の YAML ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae464-154">For apt-based distributions use the following YAML file:</span></span>

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

    - <span data-ttu-id="ae464-155">dnf ベースの配布では、次の YAML ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="ae464-155">For dnf-based distributions use the following YAML file:</span></span>

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

## <a name="deployment"></a><span data-ttu-id="ae464-156">展開</span><span class="sxs-lookup"><span data-stu-id="ae464-156">Deployment</span></span>

<span data-ttu-id="ae464-157">次に、タスク ファイルを下または関連 `/etc/ansible/playbooks/` するディレクトリで実行します。</span><span class="sxs-lookup"><span data-stu-id="ae464-157">Now run the tasks files under `/etc/ansible/playbooks/` or relevant directory.</span></span>

- <span data-ttu-id="ae464-158">インストール:</span><span class="sxs-lookup"><span data-stu-id="ae464-158">Installation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> <span data-ttu-id="ae464-159">製品が初めて起動すると、最新のマルウェア対策定義がダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="ae464-159">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="ae464-160">インターネット接続によっては、数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="ae464-160">Depending on your Internet connection, this can take up to a few minutes.</span></span>

- <span data-ttu-id="ae464-161">検証/構成:</span><span class="sxs-lookup"><span data-stu-id="ae464-161">Validation/configuration:</span></span>

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- <span data-ttu-id="ae464-162">アンインストール:</span><span class="sxs-lookup"><span data-stu-id="ae464-162">Uninstallation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a><span data-ttu-id="ae464-163">ログ インストールの問題</span><span class="sxs-lookup"><span data-stu-id="ae464-163">Log installation issues</span></span>

<span data-ttu-id="ae464-164">エラー [が発生した場合](linux-resources.md#log-installation-issues) にインストーラーによって作成される自動的に生成されたログを検索する方法の詳細については、「Log installation issues」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae464-164">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="ae464-165">オペレーティング システムのアップグレード</span><span class="sxs-lookup"><span data-stu-id="ae464-165">Operating system upgrades</span></span>

<span data-ttu-id="ae464-166">オペレーティング システムを新しいメジャー バージョンにアップグレードする場合は、まず Defender for Endpoint for Linux をアンインストールし、アップグレードをインストールし、最後にデバイスで Defender for Endpoint for Linux を再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae464-166">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint for Linux, install the upgrade, and finally reconfigure Defender for Endpoint for Linux on your device.</span></span>

## <a name="references"></a><span data-ttu-id="ae464-167">関連情報</span><span class="sxs-lookup"><span data-stu-id="ae464-167">References</span></span>

- [<span data-ttu-id="ae464-168">YUM リポジトリの追加または削除</span><span class="sxs-lookup"><span data-stu-id="ae464-168">Add or remove YUM repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [<span data-ttu-id="ae464-169">dnf パッケージ マネージャーを使用してパッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="ae464-169">Manage packages with the dnf package manager</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [<span data-ttu-id="ae464-170">APT リポジトリの追加と削除</span><span class="sxs-lookup"><span data-stu-id="ae464-170">Add and remove APT repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [<span data-ttu-id="ae464-171">apt-packages の管理</span><span class="sxs-lookup"><span data-stu-id="ae464-171">Manage apt-packages</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)
