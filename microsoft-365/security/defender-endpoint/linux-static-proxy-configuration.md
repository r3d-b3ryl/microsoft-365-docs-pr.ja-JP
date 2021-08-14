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
ms.openlocfilehash: dedab8ba3acda9b42e14fc7acae0b321bc26a45179cbc941839d93b33bb9bf7a
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53811163"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a>静的プロキシ検出用に Microsoft Defender for Endpoint on Linux を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft Defender for Endpoint では、環境変数を使用してプロキシ サーバーを `HTTPS_PROXY` 検出できます。 この設定は、インストール時 **と** 製品のインストール後の両方で構成する必要があります。

## <a name="installation-time-configuration"></a>インストール時間の構成

インストール時に、 `HTTPS_PROXY` 環境変数をパッケージ マネージャーに渡す必要があります。 パッケージ マネージャーは、次の方法でこの変数を読み取ることができます。

- 変数 `HTTPS_PROXY` は次の `/etc/environment` 行で定義されます。

  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

- この `HTTPS_PROXY` 変数は、パッケージ マネージャーのグローバル構成で定義されます。 たとえば、Ubuntu 18.04 では、次の行を次に追加できます `/etc/apt/apt.conf.d/proxy.conf` 。
  
  ```bash
  Acquire::https::Proxy "http://proxy.server:port/";
  ```

  > [!CAUTION]
  > 上記の 2 つの方法では、システム上の他のアプリケーションに使用するプロキシを定義できます。 このメソッドは、一般的にグローバル構成を意図している場合にのみ、慎重に使用してください。
  
- 変数 `HTTPS_PROXY` は、インストールまたはアンインストール コマンドの先頭に追加されます。 たとえば、APT パッケージ マネージャーを使用して、Microsoft Defender for Endpoint をインストールするときに、次のように変数の先頭に変数を追加します。 

  ```bash  
  HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
  ```

  > [!NOTE]
  > 環境変数定義と apt の間に sudo を追加しない場合、変数は伝達されません。

環境変数 `HTTPS_PROXY` は、アンインストール時にも同様に定義できます。

プロキシが必要だが構成されていない場合、インストールとアンインストールは必ずしも失敗しない点に注意してください。 ただし、テレメトリは送信されないので、ネットワーク のタイムアウトにより操作に時間がかかる可能性があります。

## <a name="post-installation-configuration"></a>インストール後の構成
  
インストール後、環境変数は Defender for Endpoint サービス `HTTPS_PROXY` ファイルで定義する必要があります。 これを行うには、ルート `/lib/systemd/system/mdatp.service` ユーザーとして実行している間にテキスト エディターで開きます。 その後、次の 2 つの方法のいずれかを使用して、変数をサービスに伝達できます。

> [!NOTE]
> CentOS または RedHat Linux ディストリビューションでは、エンドポイント サービス ファイルの場所はです `/usr/lib/systemd/system/mdatp.service` 。

- 行のアンコメント `#Environment="HTTPS_PROXY=http://address:port"` を解除し、静的プロキシ アドレスを指定します。

- 行を追加します `EnvironmentFile=/path/to/env/file` 。 このパスは、次の行を追加する必要がある、またはカスタム ファイル `/etc/environment` を指すことができます。
  
  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

ファイルを変更した `mdatp.service` 後、ファイルを保存して閉じます。 変更を適用できるよう、サービスを再起動します。 Ubuntu では、これには次の 2 つのコマンドが含まれます。  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
