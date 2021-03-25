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
ms.openlocfilehash: ad37427e8134c574690c3b3553d7fb9b8507593c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187723"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="9bc6d-104">Microsoft Defender for Endpoint for Linux の更新プログラムを展開する</span><span class="sxs-lookup"><span data-stu-id="9bc6d-104">Deploy updates for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="9bc6d-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="9bc6d-105">**Applies to:**</span></span>
- [<span data-ttu-id="9bc6d-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="9bc6d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9bc6d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9bc6d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9bc6d-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="9bc6d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9bc6d-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="9bc6d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="9bc6d-110">Microsoft は、パフォーマンス、セキュリティ、および新機能の提供を行うソフトウェア更新プログラムを定期的に発行しています。</span><span class="sxs-lookup"><span data-stu-id="9bc6d-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="9bc6d-111">Defender for Endpoint for Linux の各バージョンには有効期限が設定され、その後デバイスの保護は続行されます。</span><span class="sxs-lookup"><span data-stu-id="9bc6d-111">Each version of Defender for Endpoint for Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="9bc6d-112">この日付より前に製品を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bc6d-112">You must update the product prior to this date.</span></span> <span data-ttu-id="9bc6d-113">有効期限を確認するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9bc6d-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="9bc6d-114">Defender for Endpoint for Linux を手動で更新するには、次のいずれかのコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="9bc6d-114">To update Defender for Endpoint for Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="9bc6d-115">RHEL とバリアント (CentOS および Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="9bc6d-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="9bc6d-116">SLES とバリアント</span><span class="sxs-lookup"><span data-stu-id="9bc6d-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="9bc6d-117">Ubuntu システムと Debian システム</span><span class="sxs-lookup"><span data-stu-id="9bc6d-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
