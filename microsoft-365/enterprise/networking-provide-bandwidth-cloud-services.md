---
title: 手順 1. Microsoft 365 のネットワークを準備する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise のクラウド サービスに必要なインターネット帯域幅について理解します。
ms.openlocfilehash: ea92bcbd19c0b4cef16292d652cf5f8aa45aee07
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370294"
---
# <a name="step-1-prepare-your-network-for-microsoft-365"></a><span data-ttu-id="91bcc-103">手順 1. Microsoft 365 のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="91bcc-103">Step 1: Prepare your network for Microsoft 365</span></span>

<span data-ttu-id="91bcc-104">*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="91bcc-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![フェーズ 1 - ネットワーキング](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="91bcc-106">手順 1 では、以下を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="91bcc-106">In Step 1, you must:</span></span>

- <span data-ttu-id="91bcc-107">内部リンクとインターネット接続が、Microsoft 365 Enterprise のクラウド サービスに対するトラフィックを処理できるように、ネットワーク帯域幅を評価して調整します。</span><span class="sxs-lookup"><span data-stu-id="91bcc-107">Evaluate and adjust network bandwidth for internal links and Internet connections to account for traffic to Microsoft 365 Enterprise cloud services.</span></span>
- <span data-ttu-id="91bcc-108">[Office 365 の参照アーキテクチャ](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2)に合わせてネットワークを調整します。</span><span class="sxs-lookup"><span data-stu-id="91bcc-108">Align your network with an [Office 365 reference architecture](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).</span></span>
- <span data-ttu-id="91bcc-109">変更点を計画し、パイロット運用してから、帯域幅とトラフィック待機時間の要件に合っているかどうかテストします。</span><span class="sxs-lookup"><span data-stu-id="91bcc-109">Plan the changes, pilot them, and then test whether the changes fit your bandwidth and traffic latency requirements.</span></span>

<span data-ttu-id="91bcc-110">Office 365 や、Microsoft 365 Enterprise の他のクラウド サービスでの ExpressRoute の使用に関する詳細および推奨事項については、「[Office 365 向け Azure ExpressRoute](https://docs.microsoft.com/office365/enterprise/azure-expressroute)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="91bcc-110">For information and recommendations about using ExpressRoute with Office 365 and the other cloud services of Microsoft 365 Enterprise, see [Azure ExpressRoute for Office 365](https://docs.microsoft.com/office365/enterprise/azure-expressroute).</span></span>

<span data-ttu-id="91bcc-111">中間チェックポイントとして、この手順に対応する[終了条件](networking-exit-criteria.md#crit-networking-step1)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="91bcc-111">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="91bcc-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="91bcc-112">Next step</span></span>

|||
|:-------|:-----|
|![手順 2](./media/stepnumbers/Step2.png)|[<span data-ttu-id="91bcc-114">オフィスごとにローカルのインターネット接続を構成する</span><span class="sxs-lookup"><span data-stu-id="91bcc-114">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|

