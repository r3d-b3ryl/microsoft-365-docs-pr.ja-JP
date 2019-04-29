---
title: 'フェーズ 1: Microsoft 365 Enterprise のネットワーク インフラストラクチャ'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: " Microsoft 365 Enterprise のネットワーク インフラストラクチャを展開する手順。"
ms.openlocfilehash: 9b8c23d543eca97147801d70e42de7105266c52d
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2019
ms.locfileid: "33399961"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a>フェーズ 1: Microsoft 365 Enterprise のネットワーク インフラストラクチャ

![](./media/deploy-foundation-infrastructure/networking_icon.png)

Microsoft 365 Enterprise には、エンタープライズ管理とセキュリティ (EMS) の一部として、Office 365 と Microsoft Intune が含まれています。 これらのクラウド ベースのサービスは両方とも、クライアント デバイスからインターネットや専用回線経由の接続のセキュリティ、パフォーマンス、および信頼性に依存しています。 これらのサービスをホストし、世界中のお客様に利用可能にするため、Microsoft はパフォーマンスと統合を重視するネットワーク インフラストラクチャを設計しました。 

このフェーズでは、Microsoft 365 Enterprise のクラウド サービスへの高パフォーマンス接続を作成するための主な検討事項について、順を追って説明します。概要については、「[Office 365 のネットワークの原則](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)」を参照してください。

>[!Note]
>既にネットワーク インフラストラクチャを展開している場合は、このフェーズの[終了条件](networking-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認してください。

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a>Microsoft 365 Enterprise のネットワーク インフラストラクチャを計画および展開する 

Microsoft 365 Enterprise の要件と機能に対応したネットワーク インフラストラクチャを構築するには、次の手順を使用します。

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[Microsoft 365 のネットワークを準備する](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[オフィスごとにローカルのインターネット接続を構成する](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[ネットワーク ヘアピンを回避する](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[トラフィック バイパスを構成する](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[クライアントと Office 365 サービスのパフォーマンスを最適化する](networking-optimize-tcp-performance.md)|


上記の手順が完了したら、このフェーズの[終了条件](networking-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認します。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

「[Microsoft Office 365 のネットワーク パフォーマンスを最適化する](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)」を参照すると、Microsoft が会社として、内部的にどのように Office 365 クラウド サービス用に Microsoft ネットワークを最適化しているかを確認することができます。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 社での Microsoft 365 Enterprise の活用方法

架空の典型的な多国籍企業である Contoso Corporation が、Microsoft 365 のクラウド サービス向けに[ネットワークを最適化](contoso-networking.md)している方法をご紹介します。

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[Microsoft 365 のネットワークを準備する](networking-provide-bandwidth-cloud-services.md)|

