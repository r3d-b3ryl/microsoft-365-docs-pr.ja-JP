---
title: Puppet を使用して Microsoft Defender ATP for Linux を展開する
ms.reviewer: ''
description: Puppet を使用して Microsoft Defender ATP for Linux を展開する方法について説明します。
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2f0e2dacdbc20821cde30e241666373751db18ee
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186667"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-linux-with-puppet"></a><span data-ttu-id="340cd-104">Puppet を使用して Microsoft Defender for Endpoint for Linux を展開する</span><span class="sxs-lookup"><span data-stu-id="340cd-104">Deploy Microsoft Defender for Endpoint for Linux with Puppet</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="340cd-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="340cd-105">**Applies to:**</span></span>
- [<span data-ttu-id="340cd-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="340cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="340cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="340cd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="340cd-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="340cd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="340cd-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="340cd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="340cd-110">この記事では、Puppet を使用して Defender for Endpoint for Linux を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="340cd-110">This article describes how to deploy Defender for Endpoint for Linux using Puppet.</span></span> <span data-ttu-id="340cd-111">展開が成功するには、次のすべてのタスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="340cd-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="340cd-112">オンボーディング パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="340cd-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="340cd-113">Puppet マニフェストの作成</span><span class="sxs-lookup"><span data-stu-id="340cd-113">Create Puppet manifest</span></span>](#create-a-puppet-manifest)
- [<span data-ttu-id="340cd-114">展開</span><span class="sxs-lookup"><span data-stu-id="340cd-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="340cd-115">オンボーディングの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="340cd-115">Check onboarding status</span></span>](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="340cd-116">前提条件とシステム要件</span><span class="sxs-lookup"><span data-stu-id="340cd-116">Prerequisites and system requirements</span></span>

 <span data-ttu-id="340cd-117">現在のソフトウェア バージョンの前提条件とシステム要件の説明については、メイン [の Defender for Endpoint for Linux ページを参照してください](microsoft-defender-endpoint-linux.md)。</span><span class="sxs-lookup"><span data-stu-id="340cd-117">For a description of prerequisites and system requirements for the current software version, see [the main Defender for Endpoint for Linux page](microsoft-defender-endpoint-linux.md).</span></span>

<span data-ttu-id="340cd-118">さらに、Puppet の展開では、Puppet 管理タスクを理解し、Puppet を構成し、パッケージを展開する方法を知る必要があります。</span><span class="sxs-lookup"><span data-stu-id="340cd-118">In addition, for Puppet deployment, you need to be familiar with Puppet administration tasks, have Puppet configured, and know how to deploy packages.</span></span> <span data-ttu-id="340cd-119">Puppet には、同じタスクを実行する多くの方法があります。</span><span class="sxs-lookup"><span data-stu-id="340cd-119">Puppet has many ways to complete the same task.</span></span> <span data-ttu-id="340cd-120">これらの手順では、パッケージの展開に役立つ apt など、サポートされている *Puppet* モジュールの可用性を前提とします。</span><span class="sxs-lookup"><span data-stu-id="340cd-120">These instructions assume availability of supported Puppet modules, such as *apt* to help deploy the package.</span></span> <span data-ttu-id="340cd-121">組織で別のワークフローを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="340cd-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="340cd-122">詳細については [、Puppet のドキュメント](https://puppet.com/docs) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="340cd-122">Refer to the [Puppet documentation](https://puppet.com/docs) for details.</span></span>

## <a name="download-the-onboarding-package"></a><span data-ttu-id="340cd-123">オンボーディング パッケージをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="340cd-123">Download the onboarding package</span></span>

<span data-ttu-id="340cd-124">Microsoft Defender セキュリティ センターからオンボーディング パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="340cd-124">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="340cd-125">Microsoft Defender セキュリティ センターで、[デバイス管理とオンボード **>設定>移動します**。</span><span class="sxs-lookup"><span data-stu-id="340cd-125">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="340cd-126">最初のドロップダウン メニューで、オペレーティング システム **として [Linux Server]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="340cd-126">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="340cd-127">2 番目のドロップダウン メニューで、展開 **方法として [優先する Linux 構成管理ツール** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="340cd-127">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="340cd-128">[オンボード **パッケージのダウンロード] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="340cd-128">Select **Download onboarding package**.</span></span> <span data-ttu-id="340cd-129">ファイルを [ファイル名] WindowsDefenderATPOnboardingPackage.zip。</span><span class="sxs-lookup"><span data-stu-id="340cd-129">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender セキュリティ センターのスクリーンショット](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="340cd-131">コマンド プロンプトから、ファイルが存在するように確認します。</span><span class="sxs-lookup"><span data-stu-id="340cd-131">From a command prompt, verify that you have the file.</span></span> 

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
5. <span data-ttu-id="340cd-132">アーカイブの内容を抽出します。</span><span class="sxs-lookup"><span data-stu-id="340cd-132">Extract the contents of the archive.</span></span>
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-a-puppet-manifest"></a><span data-ttu-id="340cd-133">Puppet マニフェストの作成</span><span class="sxs-lookup"><span data-stu-id="340cd-133">Create a Puppet manifest</span></span>

<span data-ttu-id="340cd-134">Defender for Endpoint for Linux を、Puppet サーバーによって管理されるデバイスに展開するために、Puppet マニフェストを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="340cd-134">You need to create a Puppet manifest for deploying Defender for Endpoint for Linux to devices managed by a Puppet server.</span></span> <span data-ttu-id="340cd-135">この例では *、puppetlabs* から利用できる apt モジュールと *yumrepo* モジュールを使用し、モジュールが Puppet サーバーにインストールされていることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="340cd-135">This example makes use of the *apt* and *yumrepo* modules available from puppetlabs, and assumes that the modules have been installed on your Puppet server.</span></span>

<span data-ttu-id="340cd-136">Puppet インストールの *modules フォルダー install_mdatp下に、install_mdatp/* ファイル、install_mdatp/マニフェストのフォルダーを作成します。 </span><span class="sxs-lookup"><span data-stu-id="340cd-136">Create the folders *install_mdatp/files* and *install_mdatp/manifests* under the modules folder of your Puppet installation.</span></span> <span data-ttu-id="340cd-137">このフォルダーは、通常 *、/etc/puppetlabs/code/environments/production/modules* on your Puppet server にあります。</span><span class="sxs-lookup"><span data-stu-id="340cd-137">This folder is typically located in */etc/puppetlabs/code/environments/production/modules* on your Puppet server.</span></span> <span data-ttu-id="340cd-138">上記でmdatp_onboard.jsしたファイルのコピーを *、install_mdatp/files フォルダーにコピー* します。</span><span class="sxs-lookup"><span data-stu-id="340cd-138">Copy the mdatp_onboard.json file created above to the *install_mdatp/files* folder.</span></span> <span data-ttu-id="340cd-139">*init.pp を作成する*</span><span class="sxs-lookup"><span data-stu-id="340cd-139">Create an *init.pp*</span></span> <span data-ttu-id="340cd-140">展開手順を含むファイルを次に示します。</span><span class="sxs-lookup"><span data-stu-id="340cd-140">file that contains the deployment instructions:</span></span>

```bash
pwd
```
```Output
/etc/puppetlabs/code/environments/production/modules
```

```bash
tree install_mdatp
```
```Output
install_mdatp
├── files
│   └── mdatp_onboard.json
└── manifests
    └── init.pp
```

### <a name="contents-of-install_mdatpmanifestsinitpp"></a><span data-ttu-id="340cd-141">`install_mdatp/manifests/init.pp` のコンテンツ</span><span class="sxs-lookup"><span data-stu-id="340cd-141">Contents of `install_mdatp/manifests/init.pp`</span></span>

<span data-ttu-id="340cd-142">Defender for Endpoint for Linux は、以下のいずれかのチャネル *([channel] と* 示す) から展開できます。insiders-fast *、insiders-slow、\*\*または prod* です。 これらの各チャネルは、Linux ソフトウェア リポジトリに対応します。</span><span class="sxs-lookup"><span data-stu-id="340cd-142">Defender for Endpoint for Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

<span data-ttu-id="340cd-143">チャネルの選択によって、デバイスに提供される更新プログラムの種類と頻度が決されます。</span><span class="sxs-lookup"><span data-stu-id="340cd-143">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="340cd-144">*insiders-fast* のデバイスは、更新プログラムと新機能を受け取る最初のデバイスで、後で *insiders-slow* と最後に *prod が続きます*。</span><span class="sxs-lookup"><span data-stu-id="340cd-144">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="340cd-145">新機能をプレビューし、早期のフィードバックを提供するために、インサイダー高速またはインサイダー低速のいずれかを使用するために、企業の一部のデバイスを構成をお *勧めします*。</span><span class="sxs-lookup"><span data-stu-id="340cd-145">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="340cd-146">最初のインストール後にチャネルを切り替える場合は、製品を再インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="340cd-146">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="340cd-147">製品チャネルを切り替える: 既存のパッケージをアンインストールし、新しいチャネルを使用するデバイスを再構成し、このドキュメントの手順に従って新しい場所からパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="340cd-147">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

<span data-ttu-id="340cd-148">配布とバージョンをメモし、その下の最も近いエントリを識別します `https://packages.microsoft.com/config/` 。</span><span class="sxs-lookup"><span data-stu-id="340cd-148">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

<span data-ttu-id="340cd-149">以下のコマンドで *、[distro]* と *[version]* を、特定した情報に置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="340cd-149">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

> [!NOTE]
> <span data-ttu-id="340cd-150">RedHat、Oracle EL、CentOS 8 の場合 *、[distro] を 'rhel'* に置き換える。</span><span class="sxs-lookup"><span data-stu-id="340cd-150">In case of RedHat, Oracle EL, and CentOS 8, replace *[distro]* with 'rhel'.</span></span>

```puppet
# Puppet manifest to install Microsoft Defender ATP.
# @param channel The release channel based on your environment, insider-fast or prod.
# @param distro The Linux distribution in lowercase. In case of RedHat, Oracle EL, and CentOS 8, the distro variable should be 'rhel'.
# @param version The Linux distribution release number, e.g. 7.4.

class install_mdatp (
$channel = 'insiders-fast',
$distro = undef,
$version = undef
){
    case $::osfamily {
        'Debian' : {
            apt::source { 'microsoftpackages' :
                location => "https://packages.microsoft.com/${distro}/${version}/prod",
                release  => $channel,
                repos    => 'main',
                key      => {
                    'id'     => 'BC528686B50D79E339D3721CEB3E94ADBE1229CF',
                    'server' => 'keyserver.ubuntu.com',
                },
            }
        }
        'RedHat' : {
            yumrepo { 'microsoftpackages' :
                baseurl  => "https://packages.microsoft.com/${distro}/${version}/${channel}",
                descr    => "packages-microsoft-com-prod-${channel}",
                enabled  => 1,
                gpgcheck => 1,
                gpgkey   => 'https://packages.microsoft.com/keys/microsoft.asc'
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }

    case $::osfamily {
        /(Debian|RedHat)/: {
            file { ['/etc/opt', '/etc/opt/microsoft', '/etc/opt/microsoft/mdatp']:
                ensure => directory,
                owner  => root,
                group  => root,
                mode   => '0755'
            }

            file { '/etc/opt/microsoft/mdatp/mdatp_onboard.json':
                source  => 'puppet:///modules/install_mdatp/mdatp_onboard.json',
                owner   => root,
                group   => root,
                mode    => '0600',
                require => File['/etc/opt/microsoft/mdatp']
            }

            package { 'mdatp':
                ensure  => 'installed',
                require => File['/etc/opt/microsoft/mdatp/mdatp_onboard.json']
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }
}
```

## <a name="deployment"></a><span data-ttu-id="340cd-151">展開</span><span class="sxs-lookup"><span data-stu-id="340cd-151">Deployment</span></span>

<span data-ttu-id="340cd-152">上記のマニフェストを site.pp に含める</span><span class="sxs-lookup"><span data-stu-id="340cd-152">Include the above manifest in your site.pp</span></span> <span data-ttu-id="340cd-153">file:</span><span class="sxs-lookup"><span data-stu-id="340cd-153">file:</span></span>

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```
```Output
node "default" {
    include install_mdatp
}
```

<span data-ttu-id="340cd-154">登録されたエージェント デバイスは、定期的に Puppet Server をポーリングし、検出されるとすぐに新しい構成プロファイルとポリシーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="340cd-154">Enrolled agent devices periodically poll the Puppet Server and install new configuration profiles and policies as soon as they are detected.</span></span>

## <a name="monitor-puppet-deployment"></a><span data-ttu-id="340cd-155">Puppet の展開を監視する</span><span class="sxs-lookup"><span data-stu-id="340cd-155">Monitor Puppet deployment</span></span>

<span data-ttu-id="340cd-156">エージェント デバイスで、次のコマンドを実行してオンボーディングの状態を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="340cd-156">On the agent device, you can also check the onboarding status by running:</span></span>

```bash
mdatp health
```
```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- <span data-ttu-id="340cd-157">**licensed**: これにより、デバイスが組織に関連付けられているのが確認されます。</span><span class="sxs-lookup"><span data-stu-id="340cd-157">**licensed**: This confirms that the device is tied to your organization.</span></span>

- <span data-ttu-id="340cd-158">**orgId**: これは Defender for Endpoint 組織識別子です。</span><span class="sxs-lookup"><span data-stu-id="340cd-158">**orgId**: This is your Defender for Endpoint organization identifier.</span></span>

## <a name="check-onboarding-status"></a><span data-ttu-id="340cd-159">オンボーディングの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="340cd-159">Check onboarding status</span></span>

<span data-ttu-id="340cd-160">スクリプトを作成すると、デバイスが正しくオンボードされていることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="340cd-160">You can check that devices have been correctly onboarded by creating a script.</span></span> <span data-ttu-id="340cd-161">たとえば、次のスクリプトは、登録されているデバイスでオンボーディングの状態をチェックします。</span><span class="sxs-lookup"><span data-stu-id="340cd-161">For example, the following script checks enrolled devices for onboarding status:</span></span>

```bash
mdatp health --field healthy
```

<span data-ttu-id="340cd-162">上記のコマンドは、 `1` 製品がオンボードされ、期待通り機能している場合に出力されます。</span><span class="sxs-lookup"><span data-stu-id="340cd-162">The above command prints `1` if the product is onboarded and functioning as expected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="340cd-163">製品が初めて起動すると、最新のマルウェア対策定義がダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="340cd-163">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="340cd-164">インターネット接続によっては、数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="340cd-164">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="340cd-165">この間、上記のコマンドはの値を返します `0` 。</span><span class="sxs-lookup"><span data-stu-id="340cd-165">During this time the above command returns a value of `0`.</span></span>

<span data-ttu-id="340cd-166">製品が正常ではない場合、終了コード (チェックスルー `echo $?` 可能) は問題を示します。</span><span class="sxs-lookup"><span data-stu-id="340cd-166">If the product is not healthy, the exit code (which can be checked through `echo $?`) indicates the problem:</span></span>

- <span data-ttu-id="340cd-167">デバイスがまだオンボードされていない場合は 1。</span><span class="sxs-lookup"><span data-stu-id="340cd-167">1 if the device isn't onboarded yet.</span></span>
- <span data-ttu-id="340cd-168">デーモンへの接続を確立できない場合は 3。</span><span class="sxs-lookup"><span data-stu-id="340cd-168">3 if the connection to the daemon cannot be established.</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="340cd-169">ログ インストールの問題</span><span class="sxs-lookup"><span data-stu-id="340cd-169">Log installation issues</span></span>

 <span data-ttu-id="340cd-170">エラーが発生した場合にインストーラーによって作成される自動的に生成されたログを検索する方法の詳細については [、「Log installation issues 」を参照してください](linux-resources.md#log-installation-issues)。</span><span class="sxs-lookup"><span data-stu-id="340cd-170">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Log installation issues](linux-resources.md#log-installation-issues).</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="340cd-171">オペレーティング システムのアップグレード</span><span class="sxs-lookup"><span data-stu-id="340cd-171">Operating system upgrades</span></span>

<span data-ttu-id="340cd-172">オペレーティング システムを新しいメジャー バージョンにアップグレードする場合は、まず Defender for Endpoint for Linux をアンインストールし、アップグレードをインストールし、最後にデバイスで Defender for Endpoint for Linux を再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="340cd-172">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint for Linux, install the upgrade, and finally reconfigure Defender for Endpoint for Linux on your device.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="340cd-173">アンインストール</span><span class="sxs-lookup"><span data-stu-id="340cd-173">Uninstallation</span></span>

<span data-ttu-id="340cd-174">*init.pp* *でremove_mdatp\*\*の内容* install_mdatpに似たモジュール を作成する</span><span class="sxs-lookup"><span data-stu-id="340cd-174">Create a module *remove_mdatp* similar to *install_mdatp* with the following contents in *init.pp*</span></span> <span data-ttu-id="340cd-175">file:</span><span class="sxs-lookup"><span data-stu-id="340cd-175">file:</span></span>

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
