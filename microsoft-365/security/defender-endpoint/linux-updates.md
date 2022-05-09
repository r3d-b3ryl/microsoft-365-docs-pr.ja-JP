---
title: Linux 用 Microsoft Defender for Endpoint の更新プログラムを展開する
ms.reviewer: ''
description: エンタープライズ環境で Linux 上にMicrosoft Defender for Endpointの更新プログラムをデプロイする方法について説明します。
keywords: microsoft, defender, Microsoft Defender for Endpoint, Linux, updates, deploy
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
ms.openlocfilehash: 71c689143feca3d8c87d219a55c4ea42b4f9d950
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2022
ms.locfileid: "62767609"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>Linux 用 Microsoft Defender for Endpoint の更新プログラムを展開する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft は、パフォーマンス、セキュリティ、新機能を提供するために、ソフトウェア更新プログラムを定期的に発行しています。

> [!WARNING]
> Linux 上の Defender for Endpoint の各バージョンには有効期限があり、その後はデバイスの保護は続行されません。 この日付より前に製品を更新する必要があります。 有効期限を確認するには、次のコマンドを実行します。
> ```bash
> mdatp health --field product_expiration
> ```


一般提供Microsoft Defender for Endpoint機能は、展開に使用される更新チャネル (ベータ (Insider)、プレビュー (外部)、現在の (運用)) に関係なく、同等です。


Linux 上の Defender for Endpoint を手動で更新するには、次のいずれかのコマンドを実行します。

## <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL とバリエーション (CentOS および Oracle Linux)

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a>SLES とバリエーション

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a>Ubuntu および Debian システム

```bash
sudo apt-get install --only-upgrade mdatp
```

> [!IMPORTANT]
> Microsoft Defender for EndpointとDefender for Cloudを統合すると、mdatp エージェントは既定で更新プログラムを自動的に受信します。
