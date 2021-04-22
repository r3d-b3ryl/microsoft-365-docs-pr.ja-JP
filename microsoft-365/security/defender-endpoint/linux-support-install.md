---
title: Microsoft Defender for Endpoint on Linux のインストールに関する問題のトラブルシューティング
ms.reviewer: ''
description: Microsoft Defender for Endpoint on Linux のインストールに関する問題のトラブルシューティング
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, linux, installation
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
ms.openlocfilehash: 12f648ce476f6e29cbb6b038cc42f2e744d77104
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933303"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="24013-104">Microsoft Defender for Endpoint on Linux のインストールに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="24013-104">Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="24013-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="24013-105">**Applies to:**</span></span>
- [<span data-ttu-id="24013-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="24013-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="24013-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24013-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="24013-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="24013-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="24013-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="24013-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a><span data-ttu-id="24013-110">インストールが成功した場合の確認</span><span class="sxs-lookup"><span data-stu-id="24013-110">Verify if installation succeeded</span></span>

<span data-ttu-id="24013-111">インストール時にエラーが発生した場合と、パッケージ マネージャーによる意味のあるエラー メッセージが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="24013-111">An error in installation may or may not result in a meaningful error message by the package manager.</span></span> <span data-ttu-id="24013-112">インストールが成功した場合は、以下を使用してインストール ログを取得して確認します。</span><span class="sxs-lookup"><span data-stu-id="24013-112">To verify if the installation succeeded, obtain and check the installation logs using:</span></span>

 ```bash
 sudo journalctl | grep 'microsoft-mdatp'  > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
 ```

<span data-ttu-id="24013-113">正しい日付とインストール時刻を持つ前のコマンドからの出力は、成功を示します。</span><span class="sxs-lookup"><span data-stu-id="24013-113">An output from the previous command with correct date and time of installation indicates success.</span></span>

<span data-ttu-id="24013-114">また、クライアント構成 [を確認](linux-install-manually.md#client-configuration) して製品の正常性を確認し、EICAR テキスト ファイルを検出します。</span><span class="sxs-lookup"><span data-stu-id="24013-114">Also check the [Client configuration](linux-install-manually.md#client-configuration) to verify the health of the product and detect the EICAR text file.</span></span>

## <a name="make-sure-you-have-the-correct-package"></a><span data-ttu-id="24013-115">正しいパッケージがインストールされていることを確認する</span><span class="sxs-lookup"><span data-stu-id="24013-115">Make sure you have the correct package</span></span>

<span data-ttu-id="24013-116">インストールするパッケージがホストの配布とバージョンと一致している場合に注意してください。</span><span class="sxs-lookup"><span data-stu-id="24013-116">Please mind that the package you are installing is matching the host distribution and version.</span></span>

| <span data-ttu-id="24013-117">package</span><span class="sxs-lookup"><span data-stu-id="24013-117">package</span></span>                       | <span data-ttu-id="24013-118">配布</span><span class="sxs-lookup"><span data-stu-id="24013-118">distribution</span></span>                             |
|-------------------------------|------------------------------------------|
| <span data-ttu-id="24013-119">mdatp-rhel8。Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="24013-119">mdatp-rhel8.Linux.x86_64.rpm</span></span>  | <span data-ttu-id="24013-120">Oracle、RHEL、CentOS 8.x</span><span class="sxs-lookup"><span data-stu-id="24013-120">Oracle, RHEL and CentOS 8.x</span></span>              |
| <span data-ttu-id="24013-121">mdatp-sles12.Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="24013-121">mdatp-sles12.Linux.x86_64.rpm</span></span> | <span data-ttu-id="24013-122">SuSE Linux Enterprise Server 12.x</span><span class="sxs-lookup"><span data-stu-id="24013-122">SuSE Linux Enterprise Server 12.x</span></span>        |
| <span data-ttu-id="24013-123">mdatp-sles15.Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="24013-123">mdatp-sles15.Linux.x86_64.rpm</span></span> | <span data-ttu-id="24013-124">SuSE Linux Enterprise Server 15.x</span><span class="sxs-lookup"><span data-stu-id="24013-124">SuSE Linux Enterprise Server 15.x</span></span>        |
| <span data-ttu-id="24013-125">mdatp。Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="24013-125">mdatp.Linux.x86_64.rpm</span></span>        | <span data-ttu-id="24013-126">Oracle、RHEL、CentOS 7.x</span><span class="sxs-lookup"><span data-stu-id="24013-126">Oracle, RHEL and CentOS 7.x</span></span>              |
| <span data-ttu-id="24013-127">mdatp。Linux.x86_64.deb</span><span class="sxs-lookup"><span data-stu-id="24013-127">mdatp.Linux.x86_64.deb</span></span>        | <span data-ttu-id="24013-128">Debian と Ubuntu 16.04、18.04、20.04</span><span class="sxs-lookup"><span data-stu-id="24013-128">Debian and Ubuntu 16.04, 18.04 and 20.04</span></span> |

<span data-ttu-id="24013-129">手動 [展開の場合](linux-install-manually.md)は、正しいディストリビューションとバージョンが選択されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24013-129">For [manual deployment](linux-install-manually.md), make sure the correct distro and version had been chosen.</span></span>

## <a name="installation-failed"></a><span data-ttu-id="24013-130">インストールに失敗しました</span><span class="sxs-lookup"><span data-stu-id="24013-130">Installation failed</span></span>

<span data-ttu-id="24013-131">mdatp サービスが実行されている場合は、次のチェックを行います。</span><span class="sxs-lookup"><span data-stu-id="24013-131">Check if the mdatp service is running:</span></span>

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

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a><span data-ttu-id="24013-132">mdatp サービスが実行されていない場合のトラブルシューティング手順</span><span class="sxs-lookup"><span data-stu-id="24013-132">Steps to troubleshoot if mdatp service isn't running</span></span>

1. <span data-ttu-id="24013-133">"mdatp" ユーザーが存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="24013-133">Check if "mdatp" user exists:</span></span>

    ```bash
    id "mdatp"
    ```

    <span data-ttu-id="24013-134">出力がない場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="24013-134">If there’s no output, run</span></span>

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. <span data-ttu-id="24013-135">次のコマンドを使用して、サービスを有効にし、再起動してみてください。</span><span class="sxs-lookup"><span data-stu-id="24013-135">Try enabling and restarting the service using:</span></span>

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. <span data-ttu-id="24013-136">前のコマンドを実行した際に mdatp.service が見つからない場合は、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="24013-136">If mdatp.service isn't found upon running the previous command, run:</span></span>

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    <span data-ttu-id="24013-137">Ubuntu ```<systemd_path>``` ```/lib/systemd/system``` と Debian の配布と ```/usr/lib/systemd/system``` 、Rhel、CentOS、Oracle、SLES の場合です。</span><span class="sxs-lookup"><span data-stu-id="24013-137">where ```<systemd_path>``` is ```/lib/systemd/system``` for Ubuntu and Debian distributions and ```/usr/lib/systemd/system``` for Rhel, CentOS, Oracle and SLES.</span></span>
   <span data-ttu-id="24013-138">次に、手順 2 を再実行します。</span><span class="sxs-lookup"><span data-stu-id="24013-138">Then rerun step 2.</span></span>

4. <span data-ttu-id="24013-139">上記の手順が機能しない場合は、SELinux がインストールされ、エンフォースモードになっているか確認してください。</span><span class="sxs-lookup"><span data-stu-id="24013-139">If the above steps don’t work, check if SELinux is installed and in enforcing mode.</span></span> <span data-ttu-id="24013-140">その場合は、これを制限モード (できれば) または無効モードに設定してみてください。</span><span class="sxs-lookup"><span data-stu-id="24013-140">If so, try setting it to permissive (preferably) or disabled mode.</span></span> <span data-ttu-id="24013-141">これは、パラメーターをファイル内で "permissive" または "disabled" に設定し、その後再起動 `SELINUX` `/etc/selinux/config` することで実行できます。</span><span class="sxs-lookup"><span data-stu-id="24013-141">It can be done by setting the parameter `SELINUX` to "permissive" or "disabled" in `/etc/selinux/config` file, followed by reboot.</span></span> <span data-ttu-id="24013-142">詳細については、selinux のマン ページを確認してください。</span><span class="sxs-lookup"><span data-stu-id="24013-142">Check the man-page of selinux for more details.</span></span>
<span data-ttu-id="24013-143">次に、手順 2 を使用して mdatp サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="24013-143">Now try restarting the mdatp service using step 2.</span></span> <span data-ttu-id="24013-144">試して再起動した後、セキュリティ上の理由から、構成の変更を直ちに元に戻します。</span><span class="sxs-lookup"><span data-stu-id="24013-144">Revert the configuration change immediately though for security reasons after trying it and reboot.</span></span>

5. <span data-ttu-id="24013-145">ディレクトリ `/opt` がシンボリック リンクの場合は、バインド マウントを作成します `/opt/microsoft` 。</span><span class="sxs-lookup"><span data-stu-id="24013-145">If `/opt` directory is a symbolic link, create a bind mount for `/opt/microsoft`.</span></span>

6. <span data-ttu-id="24013-146">デーモンが実行可能なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="24013-146">Ensure that the daemon has executable permission.</span></span>

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="24013-147">デーモンに実行可能なアクセス許可が設定できない場合は、次のコマンドを使用して実行可能にします。</span><span class="sxs-lookup"><span data-stu-id="24013-147">If the daemon doesn't have executable permissions, make it executable using:</span></span>

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="24013-148">をクリックし、手順 2 の実行を再試行します。</span><span class="sxs-lookup"><span data-stu-id="24013-148">and retry running step 2.</span></span>

7. <span data-ttu-id="24013-149">wdavdaemon を含むファイル システムが "noexec" でマウントされていないか確認します。</span><span class="sxs-lookup"><span data-stu-id="24013-149">Ensure that the file system containing wdavdaemon isn't mounted with "noexec".</span></span>

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a><span data-ttu-id="24013-150">mdatp サービスが実行されているが、EICAR テキスト ファイルの検出が機能しない場合</span><span class="sxs-lookup"><span data-stu-id="24013-150">If mdatp service is running, but EICAR text file detection doesn't work</span></span>

1. <span data-ttu-id="24013-151">次を使用してファイル システムの種類を確認します。</span><span class="sxs-lookup"><span data-stu-id="24013-151">Check the file system type using:</span></span>

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    <span data-ttu-id="24013-152">現在、オンアクセス アクティビティでサポートされているファイル システムの一覧を次に示 [します](microsoft-defender-endpoint-linux.md#system-requirements)。</span><span class="sxs-lookup"><span data-stu-id="24013-152">Currently supported file systems for on-access activity are listed [here](microsoft-defender-endpoint-linux.md#system-requirements).</span></span> <span data-ttu-id="24013-153">これらのファイル システム外のファイルはスキャンされません。</span><span class="sxs-lookup"><span data-stu-id="24013-153">Any files outside these file systems won't be scanned.</span></span>

## <a name="command-line-tool-mdatp-isnt-working"></a><span data-ttu-id="24013-154">コマンド ライン ツール "mdatp" が機能しない</span><span class="sxs-lookup"><span data-stu-id="24013-154">Command-line tool “mdatp” isn't working</span></span>

1. <span data-ttu-id="24013-155">コマンド ライン ツールを実行するとエラーが `mdatp` 発生する場合は `command not found` 、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="24013-155">If running the command-line tool `mdatp` gives an error `command not found`, run the following command:</span></span>

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    <span data-ttu-id="24013-156">もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="24013-156">and try again.</span></span>

    <span data-ttu-id="24013-157">上記の手順のいずれも問題が解決しない場合は、診断ログを収集します。</span><span class="sxs-lookup"><span data-stu-id="24013-157">If none of the above steps help, collect the diagnostic logs:</span></span>

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    <span data-ttu-id="24013-158">ログを含む zip ファイルへのパスが出力として表示されます。</span><span class="sxs-lookup"><span data-stu-id="24013-158">Path to a zip file that contains the logs will be displayed as an output.</span></span> <span data-ttu-id="24013-159">これらのログを使用してカスタマー サポートに問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="24013-159">Reach out to our customer support with these logs.</span></span>
