---
title: 手順 1. Microsoft 365 のネットワークを準備する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 01/29/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Microsoft 365 Enterprise のクラウド サービスに必要なインターネット帯域幅について理解します。
ms.openlocfilehash: a0af61e378618bba4fbda0518543d89ba8da2b4e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074187"
---
# <a name="step-1-prepare-your-network-for-microsoft-365"></a>手順 1. Microsoft 365 のネットワークを準備する

*この手順は必須であり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

手順 1 では、以下を行う必要があります。

- 内部リンクとインターネット接続が、Microsoft 365 Enterprise のクラウド サービスに対するトラフィックを処理できるように、ネットワーク帯域幅を評価して調整します。
- [Office 365 の参照アーキテクチャ](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2)に合わせてネットワークを調整します。
- 変更点を計画し、パイロット運用してから、帯域幅とトラフィック待機時間の要件に合っているかどうかテストします。

Office 365 や、Microsoft 365 Enterprise の他のクラウド サービスでの ExpressRoute の使用に関する詳細および推奨事項については、「[Office 365 向け Azure ExpressRoute](https://docs.microsoft.com/office365/enterprise/azure-expressroute)」を参照してください。

中間チェックポイントとして、この手順に対応する[終了条件](networking-exit-criteria.md#crit-networking-step1)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)|[オフィスごとにローカルのインターネット接続を構成する](networking-dns-resolution-same-location.md)|

