---
title: 手順 1. Microsoft 365 のネットワークを準備する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise のクラウド サービスに必要なインターネット帯域幅について理解します。
ms.openlocfilehash: 412ef53b0e2f87ff07d7a5b3f0d640629d40fbfd
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869642"
---
# <a name="step-1-prepare-your-network-for-microsoft-365"></a><span data-ttu-id="b9d83-103">手順 1. Microsoft 365 のネットワークを準備する</span><span class="sxs-lookup"><span data-stu-id="b9d83-103">Step 1: Prepare your network for Microsoft 365</span></span>

<span data-ttu-id="b9d83-104">*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*</span><span class="sxs-lookup"><span data-stu-id="b9d83-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="b9d83-105">手順 1 では、以下を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9d83-105">In Step 1, you must:</span></span>

- <span data-ttu-id="b9d83-106">内部リンクとインターネット接続が、Microsoft 365 Enterprise のクラウド サービスに対するトラフィックを処理できるように、ネットワーク帯域幅を評価して調整します。</span><span class="sxs-lookup"><span data-stu-id="b9d83-106">Evaluate and adjust network bandwidth for internal links and Internet connections to account for traffic to Microsoft 365 Enterprise cloud services</span></span>
- <span data-ttu-id="b9d83-107">[Office 365 の参照アーキテクチャ](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2)に合わせてネットワークを調整します。</span><span class="sxs-lookup"><span data-stu-id="b9d83-107">Align your network with an [Office 365 reference architecture](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2)</span></span>
- <span data-ttu-id="b9d83-108">変更点を計画し、パイロット運用してから、帯域幅とトラフィック待機時間の要件に合っているかどうかテストします。</span><span class="sxs-lookup"><span data-stu-id="b9d83-108">Plan the changes, pilot them, and then test whether the changes fit your bandwidth and traffic latency requirements</span></span>

<span data-ttu-id="b9d83-109">中間チェックポイントとして、この手順に対応する[終了条件](networking-exit-criteria.md#crit-networking-step1)を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b9d83-109">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step1) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="b9d83-110">次の手順</span><span class="sxs-lookup"><span data-stu-id="b9d83-110">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)|[<span data-ttu-id="b9d83-111">オフィスごとにローカルのインターネット接続を構成する</span><span class="sxs-lookup"><span data-stu-id="b9d83-111">Configure local Internet connections for each office</span></span>](networking-dns-resolution-same-location.md)|

