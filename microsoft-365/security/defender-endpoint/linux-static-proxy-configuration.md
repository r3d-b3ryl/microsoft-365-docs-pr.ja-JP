---
title: Microsoft Defender for Endpoint on Linux 静的プロキシ検出
ms.reviewer: ''
description: 静的プロキシ検出用に Microsoft Defender for Endpoint on Linux を構成する方法について説明します。
keywords: microsoft、defender、Microsoft Defender for Endpoint、Linux、インストール、プロキシ
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
ms.openlocfilehash: 5a8e1cbda5f4361532c7fac0892be7ffe72f64ca
ms.sourcegitcommit: 8b79d276f71f22bcaeb150e78e35101cb1ae0375
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2021
ms.locfileid: "53114733"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a><span data-ttu-id="3e589-104">静的プロキシ検出用に Microsoft Defender for Endpoint on Linux を構成する</span><span class="sxs-lookup"><span data-stu-id="3e589-104">Configure Microsoft Defender for Endpoint on Linux for static proxy discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3e589-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="3e589-105">**Applies to:**</span></span>
- [<span data-ttu-id="3e589-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="3e589-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3e589-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3e589-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3e589-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="3e589-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3e589-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="3e589-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="3e589-110">Microsoft Defender for Endpoint では、環境変数を使用してプロキシ サーバーを `HTTPS_PROXY` 検出できます。</span><span class="sxs-lookup"><span data-stu-id="3e589-110">Microsoft Defender for Endpoint can discover a proxy server using the `HTTPS_PROXY` environment variable.</span></span> <span data-ttu-id="3e589-111">この設定は、インストール時 **と** 製品のインストール後の両方で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e589-111">This setting must be configured **both** at installation time and after the product has been installed.</span></span>

## <a name="installation-time-configuration"></a><span data-ttu-id="3e589-112">インストール時間の構成</span><span class="sxs-lookup"><span data-stu-id="3e589-112">Installation time configuration</span></span>

<span data-ttu-id="3e589-113">インストール時に、 `HTTPS_PROXY` 環境変数をパッケージ マネージャーに渡す必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e589-113">During installation, the `HTTPS_PROXY` environment variable must be passed to the package manager.</span></span> <span data-ttu-id="3e589-114">パッケージ マネージャーは、次の方法でこの変数を読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="3e589-114">The package manager can read this variable in any of the following ways:</span></span>

- <span data-ttu-id="3e589-115">変数 `HTTPS_PROXY` は次の `/etc/environment` 行で定義されます。</span><span class="sxs-lookup"><span data-stu-id="3e589-115">The `HTTPS_PROXY` variable is defined in `/etc/environment` with the following line:</span></span>

  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

- <span data-ttu-id="3e589-116">この `HTTPS_PROXY` 変数は、パッケージ マネージャーのグローバル構成で定義されます。</span><span class="sxs-lookup"><span data-stu-id="3e589-116">The `HTTPS_PROXY` variable is defined in the package manager global configuration.</span></span> <span data-ttu-id="3e589-117">たとえば、Ubuntu 18.04 では、次の行を次に追加できます `/etc/apt/apt.conf.d/proxy.conf` 。</span><span class="sxs-lookup"><span data-stu-id="3e589-117">For example, in Ubuntu 18.04, you can add the following line to `/etc/apt/apt.conf.d/proxy.conf`:</span></span>
  
  ```bash
  Acquire::https::Proxy "http://proxy.server:port/";
  ```

  > [!CAUTION]
  > <span data-ttu-id="3e589-118">上記の 2 つの方法では、システム上の他のアプリケーションに使用するプロキシを定義できます。</span><span class="sxs-lookup"><span data-stu-id="3e589-118">Note that above two methods could define the proxy to use for other applications on your system.</span></span> <span data-ttu-id="3e589-119">このメソッドは、一般的にグローバル構成を意図している場合にのみ、慎重に使用してください。</span><span class="sxs-lookup"><span data-stu-id="3e589-119">Use this method with caution, or only if this is meant to be a generally global configuration.</span></span>
  
- <span data-ttu-id="3e589-120">変数 `HTTPS_PROXY` は、インストールまたはアンインストール コマンドの先頭に追加されます。</span><span class="sxs-lookup"><span data-stu-id="3e589-120">The `HTTPS_PROXY` variable is prepended to the installation or uninstallation commands.</span></span> <span data-ttu-id="3e589-121">たとえば、APT パッケージ マネージャーを使用して、Microsoft Defender for Endpoint をインストールするときに、次のように変数の先頭に変数を追加します。</span><span class="sxs-lookup"><span data-stu-id="3e589-121">For example, with the APT package manager, prepend the variable as follows when installing Microsoft Defender for Endpoint:</span></span> 

  ```bash  
  HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
  ```

  > [!NOTE]
  > <span data-ttu-id="3e589-122">環境変数定義と apt の間に sudo を追加しない場合、変数は伝達されません。</span><span class="sxs-lookup"><span data-stu-id="3e589-122">Do not add sudo between the environment variable definition and apt, otherwise the variable will not be propagated.</span></span>

<span data-ttu-id="3e589-123">環境変数 `HTTPS_PROXY` は、アンインストール時にも同様に定義できます。</span><span class="sxs-lookup"><span data-stu-id="3e589-123">The `HTTPS_PROXY` environment variable may similarly be defined during uninstallation.</span></span>

<span data-ttu-id="3e589-124">プロキシが必要だが構成されていない場合、インストールとアンインストールは必ずしも失敗しない点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="3e589-124">Note that installation and uninstallation will not necessarily fail if a proxy is required but not configured.</span></span> <span data-ttu-id="3e589-125">ただし、テレメトリは送信されないので、ネットワーク のタイムアウトにより操作に時間がかかる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3e589-125">However, telemetry will not be submitted, and the operation could take much longer due to network timeouts.</span></span>

## <a name="post-installation-configuration"></a><span data-ttu-id="3e589-126">インストール後の構成</span><span class="sxs-lookup"><span data-stu-id="3e589-126">Post installation configuration</span></span>
  
<span data-ttu-id="3e589-127">インストール後、環境変数は Defender for Endpoint サービス `HTTPS_PROXY` ファイルで定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e589-127">After installation, the `HTTPS_PROXY` environment variable must be defined in the Defender for Endpoint service file.</span></span> <span data-ttu-id="3e589-128">これを行うには、ルート `/lib/systemd/system/mdatp.service` ユーザーとして実行している間にテキスト エディターで開きます。</span><span class="sxs-lookup"><span data-stu-id="3e589-128">To do this, open `/lib/systemd/system/mdatp.service` in a text editor while running as the root user.</span></span> <span data-ttu-id="3e589-129">その後、次の 2 つの方法のいずれかを使用して、変数をサービスに伝達できます。</span><span class="sxs-lookup"><span data-stu-id="3e589-129">You can then propagate the variable to the service in one of two ways:</span></span>

> [!NOTE]
> <span data-ttu-id="3e589-130">CentOS または RedHat Linux ディストリビューションでは、エンドポイント サービス ファイルの場所はです `/usr/lib/systemd/system/mdatp.service` 。</span><span class="sxs-lookup"><span data-stu-id="3e589-130">On CentOS or RedHat Linux distributions the location of the Endpoint service file is `/usr/lib/systemd/system/mdatp.service`.</span></span>

- <span data-ttu-id="3e589-131">行のアンコメント `#Environment="HTTPS_PROXY=http://address:port"` を解除し、静的プロキシ アドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3e589-131">Uncomment the line `#Environment="HTTPS_PROXY=http://address:port"` and specify your static proxy address.</span></span>

- <span data-ttu-id="3e589-132">行を追加します `EnvironmentFile=/path/to/env/file` 。</span><span class="sxs-lookup"><span data-stu-id="3e589-132">Add a line `EnvironmentFile=/path/to/env/file`.</span></span> <span data-ttu-id="3e589-133">このパスは、次の行を追加する必要がある、またはカスタム ファイル `/etc/environment` を指すことができます。</span><span class="sxs-lookup"><span data-stu-id="3e589-133">This path can point to `/etc/environment` or a custom file, either of which needs to add the following line:</span></span>
  
  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

<span data-ttu-id="3e589-134">ファイルを変更した `mdatp.service` 後、ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="3e589-134">After modifying the `mdatp.service` file, save and close it.</span></span> <span data-ttu-id="3e589-135">変更を適用できるよう、サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="3e589-135">Restart the service so the changes can be applied.</span></span> <span data-ttu-id="3e589-136">Ubuntu では、これには次の 2 つのコマンドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3e589-136">In Ubuntu, this involves two commands:</span></span>  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
