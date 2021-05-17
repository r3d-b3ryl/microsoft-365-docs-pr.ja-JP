---
title: Microsoft Defender for Endpoint on Linux のクラウド接続の問題のトラブルシューティング
ms.reviewer: ''
description: Microsoft Defender for Endpoint on Linux のクラウド接続の問題のトラブルシューティング
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, Linux, cloud, connectivity, communication
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
ms.openlocfilehash: 0345d7f88d147abb750e66a5e61f516abf38d553
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933111"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="5f7b7-104">Microsoft Defender for Endpoint on Linux のクラウド接続の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5f7b7-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5f7b7-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="5f7b7-105">**Applies to:**</span></span>
- [<span data-ttu-id="5f7b7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="5f7b7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5f7b7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f7b7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5f7b7-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="5f7b7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5f7b7-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a><span data-ttu-id="5f7b7-110">接続テストの実行</span><span class="sxs-lookup"><span data-stu-id="5f7b7-110">Run the connectivity test</span></span>

<span data-ttu-id="5f7b7-111">Defender for Endpoint on Linux が現在のネットワーク設定とクラウドと通信できる場合にテストするには、コマンド ラインから接続テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-111">To test if Defender for Endpoint on Linux can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="5f7b7-112">予期される出力:</span><span class="sxs-lookup"><span data-stu-id="5f7b7-112">expected output:</span></span>

```output
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

<span data-ttu-id="5f7b7-113">接続テストに失敗した場合は、デバイスにインターネット アクセス権が設定[](microsoft-defender-endpoint-linux.md#network-connections)されているのか、製品で必要なエンドポイントがプロキシまたはファイアウォールによってブロックされているのか確認します。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-linux.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="5f7b7-114">カール エラー 35 または 60 のエラーは、証明書のピン留め拒否を示します。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-114">Failures with curl error 35 or 60, indicate certificate pinning rejection.</span></span> <span data-ttu-id="5f7b7-115">接続が SSL または HTTPS 検査の下にあるか確認してください。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-115">Please check if the connection is under SSL or HTTPS inspection.</span></span> <span data-ttu-id="5f7b7-116">その場合は、許可リストに Microsoft Defender for Endpoint を追加します。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-116">If so, add Microsoft Defender for Endpoint to the allow list.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a><span data-ttu-id="5f7b7-117">プロキシのない環境、または透過的なプロキシを使用した環境のトラブルシューティング手順</span><span class="sxs-lookup"><span data-stu-id="5f7b7-117">Troubleshooting steps for environments without proxy or with transparent proxy</span></span>

<span data-ttu-id="5f7b7-118">プロキシのない環境または透過プロキシを使用して接続がブロックされていないとテストするには、ターミナルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-118">To test that a connection is not blocked in an environment without a proxy or with a transparent proxy, run the following command in the terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="5f7b7-119">このコマンドの出力は、次の値に似ている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-119">The output from this command should be similar to:</span></span>

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a><span data-ttu-id="5f7b7-120">静的プロキシを使用する環境のトラブルシューティング手順</span><span class="sxs-lookup"><span data-stu-id="5f7b7-120">Troubleshooting steps for environments with static proxy</span></span>

> [!WARNING]
> <span data-ttu-id="5f7b7-121">PAC、WPAD、および認証されたプロキシはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-121">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="5f7b7-122">静的プロキシまたは透過プロキシのみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-122">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="5f7b7-123">SSL 検査および代行受信プロキシも、セキュリティ上の理由からサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-123">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="5f7b7-124">SSL インスペクションとプロキシ サーバーの例外を構成して、Defender for Endpoint on Linux のデータを、インターセプトなしで関連する URL に直接渡します。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-124">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="5f7b7-125">インターセプト証明書をグローバル ストアに追加すると、傍受は許可されない。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-125">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="5f7b7-126">静的プロキシが必要な場合は、プロキシ のアドレスとポートに対応するプロキシ パラメーターを上記の `proxy_address:port` コマンドに追加します。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-126">If a static proxy is required, add a proxy parameter to the above command, where `proxy_address:port` correspond to the proxy address and port:</span></span>

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="5f7b7-127">ファイルで構成されているのと同じプロキシ アドレスとポートを使用してください `/lib/system/system/mdatp.service` 。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-127">Ensure that you use the same proxy address and port as configured in the `/lib/system/system/mdatp.service` file.</span></span> <span data-ttu-id="5f7b7-128">上記のコマンドでエラーが発生した場合は、プロキシ構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-128">Check your proxy configuration if there are errors from the above commands.</span></span>

> [!WARNING]
> <span data-ttu-id="5f7b7-129">静的プロキシは、システム全体の環境変数を使用して `HTTPS_PROXY` 構成できません。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-129">The static proxy cannot be configured through a system-wide `HTTPS_PROXY` environment variable.</span></span> <span data-ttu-id="5f7b7-130">代わりに、ファイルに `HTTPS_PROXY` 正しく設定されていることを確認 `/lib/system/system/mdatp.service` します。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-130">Instead, ensure that `HTTPS_PROXY` is properly set in the `/lib/system/system/mdatp.service` file.</span></span>

<span data-ttu-id="5f7b7-131">静的プロキシを使用するには、ファイル `mdatp.service` を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-131">To use a static proxy, the `mdatp.service` file must be modified.</span></span> <span data-ttu-id="5f7b7-132">先頭が削除 `#` され、次の行のアンコメントが解除されます `/lib/systemd/system/mdatp.service` 。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-132">Ensure the leading `#` is removed to uncomment the following line from `/lib/systemd/system/mdatp.service`:</span></span>

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

<span data-ttu-id="5f7b7-133">また、置換するために正しい静的プロキシ アドレスが入力されていることを確認します `address:port` 。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-133">Also ensure that the correct static proxy address is filled in to replace `address:port`.</span></span>

<span data-ttu-id="5f7b7-134">このファイルが正しい場合は、ターミナルで次のコマンドを実行して、Defender for Endpoint on Linux を再読み込みし、設定を伝達してください。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-134">If this file is correct, try running the following command in the terminal to reload Defender for Endpoint on Linux and propagate the setting:</span></span>

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

<span data-ttu-id="5f7b7-135">成功した場合は、コマンド ラインから別の接続テストを試してください。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-135">Upon success, attempt another connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="5f7b7-136">問題が解決しない場合は、カスタマー サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-136">If the problem persists, contact customer support.</span></span>

## <a name="resources"></a><span data-ttu-id="5f7b7-137">リソース</span><span class="sxs-lookup"><span data-stu-id="5f7b7-137">Resources</span></span>

- <span data-ttu-id="5f7b7-138">静的プロキシを使用する製品を構成する方法の詳細については [、「Configure Microsoft Defender for Endpoint for static proxy discovery」を参照してください](linux-static-proxy-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="5f7b7-138">For more information about how to configure the product to use a static proxy, see [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).</span></span>
