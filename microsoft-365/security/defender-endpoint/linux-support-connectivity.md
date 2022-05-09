---
title: Linux でのMicrosoft Defender for Endpointに関するクラウド接続の問題のトラブルシューティング
ms.reviewer: ''
description: Linux 上のMicrosoft Defender for Endpointのクラウド接続の問題をトラブルシューティングする方法について説明します
keywords: microsoft, defender, Microsoft Defender for Endpoint, Linux, クラウド, 接続, 通信
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
ms.openlocfilehash: a4c279dff6fa5a5c85a2f65144a301dde75a1615
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61167225"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Linux でのMicrosoft Defender for Endpointに関するクラウド接続の問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a>接続テストを実行する

Linux 上の Defender for Endpoint が現在のネットワーク設定でクラウドと通信できるかどうかをテストするには、コマンド ラインから接続テストを実行します。

```bash
mdatp connectivity test
```

予想される出力:

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

接続テストに失敗した場合は、デバイスがインターネットにアクセスできるかどうかを確認し、 [製品で必要なエンドポイントのいずれかが](microsoft-defender-endpoint-linux.md#network-connections) プロキシまたはファイアウォールによってブロックされているかどうかを確認します。

curl エラー 35 または 60 のエラーは、証明書のピン留め拒否を示します。 接続が SSL または HTTPS 検査の下にあるかどうかを確認してください。 その場合は、許可リストにMicrosoft Defender for Endpointを追加します。

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a>プロキシのない環境または透過的なプロキシを使用した環境のトラブルシューティング手順

プロキシのない環境や透過プロキシを使用して接続がブロックされないことをテストするには、ターミナルで次のコマンドを実行します。

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

このコマンドの出力は次のようになります。

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a>静的プロキシを使用する環境のトラブルシューティング手順

> [!WARNING]
> PAC、WPAD、および認証されたプロキシはサポートされていません。 静的プロキシまたは透過プロキシのみが使用されていることを確認します。
>
> セキュリティ上の理由から、SSL 検査とインターセプト プロキシもサポートされていません。 SSL 検査とプロキシ サーバーの例外を構成して、Defender for Endpoint on Linux から関連する URL にデータをインターセプトせずに直接渡すようにします。 インターセプト証明書をグローバル ストアに追加すると、インターセプトは許可されません。

静的プロキシが必要な場合は、プロキシ アドレスとポートに対応するプロキシ パラメーターを上記のコマンド `proxy_address:port` に追加します。

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

ファイルで構成されているのと同じプロキシ アドレスとポートを `/lib/system/system/mdatp.service` 使用していることを確認します。 上記のコマンドでエラーが発生した場合は、プロキシ構成を確認します。

mdatp のプロキシを設定するには、次のコマンドを使用します。

```bash
mdatp config proxy set --value http://address:port 
```


成功したら、コマンド ラインから別の接続テストを試みます。

```bash
mdatp connectivity test
```

問題が解決しない場合は、カスタマー サポートにお問い合わせください。

## <a name="resources"></a>リソース

- 静的プロキシを使用するように製品を構成する方法の詳細については、「静的プロキシ[検出のMicrosoft Defender for Endpointを構成](linux-static-proxy-configuration.md)する」を参照してください。
