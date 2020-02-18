---
title: 'フェーズ 1: Microsoft 365 Enterprise のネットワーク インフラストラクチャ'
f1.keywords:
- NOCSH
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
description: " Microsoft 365 Enterprise のネットワーク インフラストラクチャを展開する手順。"
ms.openlocfilehash: 9a805ffbdbdc19ef5943a0c0ba0ff8f010d3e19b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066594"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a>フェーズ 1: Microsoft 365 Enterprise のネットワーク インフラストラクチャ

![フェーズ 1: ネットワーク](../media/deploy-foundation-infrastructure/networking_icon.png)

Microsoft 365 Enterprise には、Office 365、Microsoft Intune、および Microsoft Azure の多くの ID およびセキュリティ サービスが含まれます。 これらのクラウド ベースのサービスはすべて、クライアント デバイスからインターネットや専用回線経由の接続のセキュリティ、パフォーマンス、および信頼性に依存しています。 これらのサービスをホストし、世界中のお客様に利用可能にするため、Microsoft はパフォーマンスと統合を重視するネットワーク インフラストラクチャを設計しました。 

このフェーズでは、Microsoft 365 Enterprise のクラウド サービスへの高パフォーマンス接続を作成するための主な検討事項について、順を追って説明します。概要については、「[Office 365 のネットワークの原則](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694)」を参照してください。

>[!Note]
>既にネットワーク インフラストラクチャを展開している場合は、このフェーズの[終了条件](networking-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認してください。

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a>Microsoft 365 Enterprise のネットワーク インフラストラクチャを計画および展開する 

Microsoft 365 Enterprise の要件と機能に対応したネットワーク インフラストラクチャを構築するには、次の手順を使用します。

|||
|:-------|:-----|
|![手順 1](../media/stepnumbers/Step1.png)|[Microsoft 365 用のネットワークを準備する](networking-provide-bandwidth-cloud-services.md)|
|![手順 2](../media/stepnumbers/Step2.png)|[オフィスごとにローカルのインターネット接続を構成する](networking-dns-resolution-same-location.md)|
|![手順 3](../media/stepnumbers/Step3.png)|[ネットワーク ヘアピンを回避する](networking-avoid-network-hairpins.md)|
|![手順 4](../media/stepnumbers/Step4.png)|[トラフィック バイパスを構成する](networking-configure-proxies-firewalls.md)|
|![手順 5](../media/stepnumbers/Step5.png)|[クライアントと Office 365 サービスのパフォーマンスを最適化する](networking-optimize-tcp-performance.md)|


上記の手順が完了したら、このフェーズの[終了条件](networking-exit-criteria.md)を参照し、Microsoft 365 Enterprise の必須条件とオプションの条件を満たしていることを確認します。

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft での Microsoft 365 Enterprise の活用方法

Microsoft の内部を見て、[クラウド サービス向けに Microsoft ネットワークを最適化](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR4)している方法をご紹介します。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 社での Microsoft 365 Enterprise の活用方法

架空ではあるものの代表的な多国籍企業である Contoso Corporation が Microsoft 365 クラウド サービス用に[ネットワーク デバイスおよびインターネット接続を最適化](contoso-networking.md)した方法をご覧ください。

![Contoso 社](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![手順 1](../media/stepnumbers/Step1.png)|[Microsoft 365 のネットワークを準備する](networking-provide-bandwidth-cloud-services.md)|

