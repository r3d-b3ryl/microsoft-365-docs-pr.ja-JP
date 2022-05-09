---
title: macOS でのMicrosoft Defender for Endpointのクラウド接続の問題のトラブルシューティング
description: このトピックでは、macOS でのMicrosoft Defender for Endpointのクラウド接続の問題をトラブルシューティングする方法について説明します
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, インストール, 展開, アンインストール, intune, jamf, macos, catalina, mojave, high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 677737f530e35ed52a2a1f3fe7a8d6f18c26e7b6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63326568"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a>macOS でのMicrosoft Defender for Endpointのクラウド接続の問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**プラットフォーム** macOS

このトピックでは、macOS でのMicrosoft Defender for Endpointのクラウド接続の問題をトラブルシューティングする方法について説明します。

## <a name="run-the-connectivity-test"></a>接続テストを実行する
Mac 上の Defender for Endpoint が現在のネットワーク設定でクラウドと通信できるかどうかをテストするには、コマンド ラインから接続テストを実行します。

```Bash
mdatp connectivity test
```

予想される出力:
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

接続テストに失敗した場合は、デバイスがインターネットにアクセスできるかどうかを確認し、 [製品で必要なエンドポイントのいずれかが](microsoft-defender-endpoint-mac.md#network-connections) プロキシまたはファイアウォールによってブロックされているかどうかを確認します。

curl エラー 35 または 60 のエラーは、証明書のピン留め拒否を示します。これは、SSL または HTTPS 検査に関する潜在的な問題を示します。 SSL 検査の構成については、以下の手順を参照してください。

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a>プロキシのない環境、またはプロキシ自動構成 (PAC) または Web プロキシ自動検出プロトコル (WPAD) を使用した環境のトラブルシューティング手順
プロキシのない環境、またはプロキシ自動構成 (PAC) または Web プロキシ自動検出プロトコル (WPAD) を使用して接続がブロックされないことをテストするには、次の手順に従います。

プロキシまたはファイアウォールが匿名トラフィックをブロックしている場合は、前述の URL で匿名トラフィックが許可されていることを確認します。

> [!WARNING]
> 認証されたプロキシはサポートされていません。 PAC、WPAD、または静的プロキシのみが使用されていることを確認します。 セキュリティ上の理由から、SSL 検査とインターセプト プロキシもサポートされていません。 SSL 検査とプロキシ サーバーの例外を構成して、macOS 上のMicrosoft Defender for Endpointからインターセプトなしで関連する URL にデータを直接渡します。 インターセプト証明書をグローバル ストアに追加すると、インターセプトは許可されません。
接続がブロックされていないかどうかをテストするには:Mac や Safari のMicrosoft Edgeなどのブラウザーで開https://x.cp.wd.microsoft.com/api/reportき、https://cdn.x.cp.wd.microsoft.com/ping.

必要に応じて、ターミナルで次のコマンドを実行します。

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

このコマンドの出力は次のようになります。
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
