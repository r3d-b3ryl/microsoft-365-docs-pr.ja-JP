---
title: macOS 上の Microsoft Defender for Endpoint のクラウド接続の問題のトラブルシューティング
description: このトピックでは、macOS 上の Microsoft Defender for Endpoint のクラウド接続の問題をトラブルシューティングする方法について説明します。
keywords: microsoft、 defender、 Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 291cd3016dcb4e1a321f39b4d2731ce2068b6544
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935211"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="43f1b-104">macOS 上の Microsoft Defender for Endpoint のクラウド接続の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="43f1b-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="43f1b-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="43f1b-105">**Applies to:**</span></span>
- [<span data-ttu-id="43f1b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="43f1b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="43f1b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43f1b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="43f1b-108">**プラットフォーム** macOS</span><span class="sxs-lookup"><span data-stu-id="43f1b-108">**Platform** macOS</span></span>

<span data-ttu-id="43f1b-109">このトピックでは、macOS 上の Microsoft Defender for Endpoint のクラウド接続の問題をトラブルシューティングする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43f1b-109">This topic describes how to Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS.</span></span>

## <a name="run-the-connectivity-test"></a><span data-ttu-id="43f1b-110">接続テストの実行</span><span class="sxs-lookup"><span data-stu-id="43f1b-110">Run the connectivity test</span></span>
<span data-ttu-id="43f1b-111">Defender for Endpoint on Mac が現在のネットワーク設定とクラウドと通信できる場合にテストするには、コマンド ラインから接続テストを実行します。</span><span class="sxs-lookup"><span data-stu-id="43f1b-111">To test if Defender for Endpoint on Mac can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```Bash
mdatp connectivity test
```

<span data-ttu-id="43f1b-112">予期される出力:</span><span class="sxs-lookup"><span data-stu-id="43f1b-112">expected output:</span></span>
```Bash
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

<span data-ttu-id="43f1b-113">接続テストに失敗した場合は、デバイスにインターネット アクセス権が設定[](microsoft-defender-endpoint-mac.md#network-connections)されているのか、製品で必要なエンドポイントがプロキシまたはファイアウォールによってブロックされているのか確認します。</span><span class="sxs-lookup"><span data-stu-id="43f1b-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-mac.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="43f1b-114">カール エラー 35 または 60 のエラーは、証明書のピン留め拒否を示し、SSL または HTTPS 検査の潜在的な問題を示します。</span><span class="sxs-lookup"><span data-stu-id="43f1b-114">Failures with curl error 35 or 60 indicate certificate pinning rejection, which indicates a potential issue with SSL or HTTPS inspection.</span></span> <span data-ttu-id="43f1b-115">SSL 検査の構成については、以下の手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43f1b-115">See instructions below regarding SSL inspection configuration.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a><span data-ttu-id="43f1b-116">プロキシのない環境、またはプロキシ自動構成 (PAC) または Web プロキシ自動検出プロトコル (WPAD) を使用した環境のトラブルシューティング手順</span><span class="sxs-lookup"><span data-stu-id="43f1b-116">Troubleshooting steps for environments without proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD)</span></span>
<span data-ttu-id="43f1b-117">次の手順を使用して、プロキシのない環境、またはプロキシ自動構成 (PAC) または Web プロキシ自動検出プロトコル (WPAD) を使用して接続がブロックされていないとテストします。</span><span class="sxs-lookup"><span data-stu-id="43f1b-117">Use the following procedure to test that a connection is not blocked in an environment without a proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD).</span></span>

<span data-ttu-id="43f1b-118">プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合は、以前にリストした URL で匿名トラフィックが許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="43f1b-118">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="43f1b-119">認証されたプロキシはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="43f1b-119">Authenticated proxies are not supported.</span></span> <span data-ttu-id="43f1b-120">PAC、WPAD、または静的プロキシだけが使用されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="43f1b-120">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span> <span data-ttu-id="43f1b-121">SSL 検査および代行受信プロキシも、セキュリティ上の理由からサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="43f1b-121">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="43f1b-122">SSL インスペクションとプロキシ サーバーの例外を構成して、macOS 上の Microsoft Defender for Endpoint のデータを、傍受なしで関連する URL に直接渡します。</span><span class="sxs-lookup"><span data-stu-id="43f1b-122">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="43f1b-123">インターセプト証明書をグローバル ストアに追加すると、傍受は許可されない。</span><span class="sxs-lookup"><span data-stu-id="43f1b-123">Adding your interception certificate to the global store will not allow for interception.</span></span>
<span data-ttu-id="43f1b-124">接続がブロックされていないとテストするには:Mac または Safari の接続Microsoft Edgeなどのブラウザーで開 https://x.cp.wd.microsoft.com/api/report きます https://cdn.x.cp.wd.microsoft.com/ping 。</span><span class="sxs-lookup"><span data-stu-id="43f1b-124">To test that a connection is not blocked: In a browser such as Microsoft Edge for Mac or Safari open https://x.cp.wd.microsoft.com/api/report and https://cdn.x.cp.wd.microsoft.com/ping.</span></span>

<span data-ttu-id="43f1b-125">必要に応じて、ターミナルで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="43f1b-125">Optionally, in Terminal, run the following command:</span></span>

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

<span data-ttu-id="43f1b-126">このコマンドの出力は、次の値に似ている必要があります。</span><span class="sxs-lookup"><span data-stu-id="43f1b-126">The output from this command should be similar to:</span></span>
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
