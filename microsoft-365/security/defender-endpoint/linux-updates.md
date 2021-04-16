---
title: Microsoft Defender for Endpoint for Linux の更新プログラムを展開する
ms.reviewer: ''
description: エンタープライズ環境で Microsoft Defender for Endpoint for Linux の更新プログラムを展開する方法について説明します。
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
ms.openlocfilehash: 77b428e359596e73e08dc04f15190ecf68db29be
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861149"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="7eea0-104">Microsoft Defender for Endpoint の更新プログラムを Linux に展開する</span><span class="sxs-lookup"><span data-stu-id="7eea0-104">Deploy updates for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7eea0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="7eea0-105">**Applies to:**</span></span>
- [<span data-ttu-id="7eea0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7eea0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7eea0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7eea0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7eea0-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="7eea0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7eea0-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="7eea0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="7eea0-110">Microsoft は、パフォーマンス、セキュリティ、および新機能の提供を行うソフトウェア更新プログラムを定期的に発行しています。</span><span class="sxs-lookup"><span data-stu-id="7eea0-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="7eea0-111">Defender for Endpoint for Linux の各バージョンには有効期限が設定され、その後デバイスの保護は続行されます。</span><span class="sxs-lookup"><span data-stu-id="7eea0-111">Each version of Defender for Endpoint for Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="7eea0-112">この日付より前に製品を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7eea0-112">You must update the product prior to this date.</span></span> <span data-ttu-id="7eea0-113">有効期限を確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7eea0-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="7eea0-114">Defender for Endpoint for Linux を手動で更新するには、次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="7eea0-114">To update Defender for Endpoint for Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="7eea0-115">RHEL とバリアント (CentOS および Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="7eea0-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="7eea0-116">SLES とバリアント</span><span class="sxs-lookup"><span data-stu-id="7eea0-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="7eea0-117">Ubuntu システムと Debian システム</span><span class="sxs-lookup"><span data-stu-id="7eea0-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
