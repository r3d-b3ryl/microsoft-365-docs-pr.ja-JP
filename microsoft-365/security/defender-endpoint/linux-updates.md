---
title: Microsoft Defender ATP for Linux の更新プログラムを展開する
ms.reviewer: ''
description: エンタープライズ環境で Microsoft Defender ATP for Linux の更新プログラムを展開する方法について説明します。
keywords: microsoft、Defender、atp、Linux、更新プログラム、展開
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
ms.openlocfilehash: 2e4ea4942446317aef90288da9fb181935503fa9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687468"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender for Endpoint の更新プログラムを Linux に展開する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft は、パフォーマンス、セキュリティ、および新機能の提供を行うソフトウェア更新プログラムを定期的に発行しています。

> [!WARNING]
> Defender for Endpoint for Linux の各バージョンには有効期限が設定され、その後デバイスの保護は続行されます。 この日付より前に製品を更新する必要があります。 有効期限を確認するには、次のコマンドを実行します。
> ```bash
> mdatp health --field product_expiration
> ```

Defender for Endpoint for Linux を手動で更新するには、次のいずれかのコマンドを実行します。

## <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL とバリアント (CentOS および Oracle Linux)

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a>SLES とバリアント

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a>Ubuntu システムと Debian システム

```bash
sudo apt-get install --only-upgrade mdatp
```
