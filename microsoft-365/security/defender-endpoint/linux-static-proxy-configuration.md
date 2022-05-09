---
title: Linux 静的プロキシ検出でのMicrosoft Defender for Endpoint
ms.reviewer: ''
description: 静的プロキシ検出用に Linux でMicrosoft Defender for Endpointを構成する方法について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, Linux, インストール, プロキシ
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
ms.openlocfilehash: 3b5061f0230a9704cb0fb9b80752c4d38954ad12
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168544"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a>静的プロキシ検出用に Linux でMicrosoft Defender for Endpointを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft Defender for Endpointは、環境変数を使用してプロキシ サーバーを`HTTPS_PROXY`検出できます。 この設定は、インストール時と製品のインストール後の **両方** で構成する必要があります。

## <a name="installation-time-configuration"></a>インストール時間の構成

インストール中は、環境変数を `HTTPS_PROXY` パッケージ マネージャーに渡す必要があります。 パッケージ マネージャーは、次のいずれかの方法でこの変数を読み取ることができます。

- 変数は `HTTPS_PROXY` 次の行で `/etc/environment` 定義されます。

  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

- 変数は `HTTPS_PROXY` 、パッケージ マネージャーのグローバル構成で定義されます。 たとえば、Ubuntu 18.04 では、次の行を次の行に `/etc/apt/apt.conf.d/proxy.conf`追加できます。

  ```bash
  Acquire::https::Proxy "http://proxy.server:port/";
  ```

  > [!CAUTION]
  > 上記の 2 つの方法では、システム上の他のアプリケーションで使用するプロキシを定義できることに注意してください。 このメソッドは注意して使用するか、一般的にグローバルな構成を意図している場合にのみ使用してください。

- この `HTTPS_PROXY` 変数は、インストール コマンドまたはアンインストール コマンドの先頭に追加されます。 たとえば、APT パッケージ マネージャーを使用して、Microsoft Defender for Endpointをインストールするときに次のように変数を先頭に追加します。

  ```bash
  HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
  ```

  > [!NOTE]
  > 環境変数定義と apt の間に sudo を追加しないでください。それ以外の場合、変数は反映されません。

同様に `HTTPS_PROXY` 、アンインストール時に環境変数を定義できます。

プロキシが必要なが構成されていない場合、インストールとアンインストールは必ずしも失敗するわけではないことに注意してください。 ただし、テレメトリは送信されず、ネットワーク タイムアウトが原因で操作にかかる時間が大幅に長くなる可能性があります。

## <a name="post-installation-configuration"></a>インストール後の構成

インストール後、 `HTTPS_PROXY` Defender for Endpoint サービス ファイルで環境変数を定義する必要があります。 これを行うには、.`sudo systemctl edit --full mdatp.service`
その後、次の 2 つの方法のいずれかで、変数をサービスに伝達できます。

- 行 `#Environment="HTTPS_PROXY=http://address:port"` のコメントを解除し、静的プロキシ アドレスを指定します。

- 行を追加します `EnvironmentFile=/path/to/env/file`。 このパスは、次の行を `/etc/environment` 追加する必要があるカスタム ファイルまたはカスタム ファイルを指すことができます。

  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

変更後、ファイルを `mdatp.service`保存し、サービスを再起動して、次のコマンドを使用して変更を適用できるようにします。

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```
