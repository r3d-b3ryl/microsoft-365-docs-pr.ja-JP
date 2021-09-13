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
ms.openlocfilehash: 02ed42cf2d95a2693949ee6dd9e7aeaae314e4bd
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212184"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender for Endpoint on Linux のクラウド接続の問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a>接続テストの実行

Defender for Endpoint on Linux が現在のネットワーク設定とクラウドと通信できる場合にテストするには、コマンド ラインから接続テストを実行します。

```bash
mdatp connectivity test
```

予期される出力:

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

接続テストに失敗した場合は、デバイスにインターネット アクセス権が設定[](microsoft-defender-endpoint-linux.md#network-connections)されているのか、製品で必要なエンドポイントがプロキシまたはファイアウォールによってブロックされているのか確認します。

カール エラー 35 または 60 のエラーは、証明書のピン留め拒否を示します。 接続が SSL または HTTPS 検査の下にあるか確認してください。 その場合は、許可リストに Microsoft Defender for Endpoint を追加します。

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a>プロキシのない環境、または透過的なプロキシを使用した環境のトラブルシューティング手順

プロキシのない環境または透過プロキシを使用して接続がブロックされていないとテストするには、ターミナルで次のコマンドを実行します。

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

このコマンドの出力は、次の値に似ている必要があります。

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a>静的プロキシを使用する環境のトラブルシューティング手順

> [!WARNING]
> PAC、WPAD、および認証されたプロキシはサポートされていません。 静的プロキシまたは透過プロキシのみを使用してください。
>
> SSL 検査および代行受信プロキシも、セキュリティ上の理由からサポートされていません。 SSL インスペクションとプロキシ サーバーの例外を構成して、Defender for Endpoint on Linux のデータを、インターセプトなしで関連する URL に直接渡します。 インターセプト証明書をグローバル ストアに追加すると、傍受は許可されない。

静的プロキシが必要な場合は、プロキシ のアドレスとポートに対応するプロキシ パラメーターを上記の `proxy_address:port` コマンドに追加します。

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

ファイルで構成されているのと同じプロキシ アドレスとポートを使用してください `/lib/system/system/mdatp.service` 。 上記のコマンドでエラーが発生した場合は、プロキシ構成を確認します。

> [!WARNING]
> 静的プロキシは、システム全体の環境変数を使用して `HTTPS_PROXY` 構成できません。 代わりに、ファイルに `HTTPS_PROXY` 正しく設定されていることを確認 `/lib/system/system/mdatp.service` します。

静的プロキシを使用するには、ファイル `mdatp.service` を変更する必要があります。 先頭が削除 `#` され、次の行のアンコメントが解除されます `/lib/systemd/system/mdatp.service` 。

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

また、置換するために正しい静的プロキシ アドレスが入力されていることを確認します `address:port` 。

このファイルが正しい場合は、ターミナルで次のコマンドを実行して、Defender for Endpoint on Linux を再読み込みし、設定を伝達してください。

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

成功した場合は、コマンド ラインから別の接続テストを試してください。

```bash
mdatp connectivity test
```

問題が解決しない場合は、カスタマー サポートにお問い合わせください。

## <a name="resources"></a>リソース

- 静的プロキシを使用する製品を構成する方法の詳細については [、「Configure Microsoft Defender for Endpoint for static proxy discovery」を参照してください](linux-static-proxy-configuration.md)。
