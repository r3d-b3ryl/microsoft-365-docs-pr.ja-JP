---
title: '手順 4: トラフィック バイパスを構成する'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/13/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Office 365 が稼働している信頼できる場所にトラフィックをバイパスするのに必要となる Web ブラウザーとエッジ デバイスについて理解し、構成します。
ms.openlocfilehash: b04e16b249dccf8f2461189b8b47abdd252a75d8
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "43504081"
---
# <a name="step-4-configure-traffic-bypass"></a>手順 4: トラフィック バイパスを構成する

*この手順は省略可能で、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます*

![フェーズ 1 - ネットワーキング](../media/deploy-foundation-infrastructure/networking_icon-small.png)

一般的なインターネット トラフィックにはリスクがあるため、標準的な組織のネットワークでは、プロキシ サーバー、SSL 中断/検査、パケット検査デバイス、およびデータ損失防止システムのようなエッジ デバイスを使用して、セキュリティを強化します。 ネットワーク傍受デバイスに関する問題については、「[Office 365 トラフィックにサードパーティのネットワーク デバイスまたはソリューションを使用する](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365)」を参照してください。

ただし、Microsoft 365 のクラウドベース サービスで使用する DNS ドメイン名と IP アドレスはよく知られている上に、トラフィックとサービスは多くのセキュリティ機能で保護されています。この種のセキュリティと保護は既に適用されているので、エッジ デバイスで同じことを行う必要はありません。Microsoft 365 のトラフィックが、中間地点や重複するセキュリティ処理を経由する設定では、パフォーマンスが大幅に低下します。

中間地点や重複するセキュリティ処理を排除する最初の手順として、Microsoft 365 のトラフィックを識別します。Microsoft では、次の種類の DNS ドメイン名と IP アドレス範囲 (エンドポイントと呼ばれる) を定義しています。

- **最適化**: すべての Office 365 サービスへの接続に必須で、Microsoft 365 の帯域幅、接続、データ量の 75% 以上に相当します。 これらのエンドポイントは、ネットワーク パフォーマンス、待機時間、可用性の影響を最も受けやすい Microsoft 365 シナリオに該当します。
- **許可**: 特定の Microsoft 365 サービスや機能への接続に必須ですが、ネットワーク パフォーマンスや待機時間の影響は、最適化カテゴリのエンドポイントほど大きくありません。
 - **既定**: 最適化を必要としない Microsoft 365 サービスや依存関係を表します。 標準カテゴリのエンドポイントは、通常のインターネット トラフィックとして扱うことができます。

DNS ドメイン名と IP アドレスの範囲については、「[https://aka.ms/o365endpoints](https://aka.ms/o365endpoints)」を参照してください。

Microsoft では、次の方法を推奨しています。

- オンプレミスのコンピューターのインターネット ブラウザーで、プロキシ自動構成 (PAC) スクリプトを使用し、Microsoft 365 クラウドベース サービスの DNS ドメイン名用のプロキシ サーバーをバイパスします。 最新の Microsoft 365 PAC スクリプトについては、[Get-Pacfile の PowerShell スクリプト](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic) を参照してください。

- エッジ デバイスを分析して重複する処理を特定したら、それらのエッジ デバイスが "最適化" および "許可" エンドポイントにトラフィックを処理せずに転送するように構成します。これは、トラフィック バイパスと呼ばれます。 

ネットワーク インフラストラクチャでのそれらの推奨事項は次の通りです。

![オンプレミスのトラフィックを最適化するための推奨事項](../media/networking-configure-proxies-firewalls/bypassing-edge-devices.png)

エッジ デバイスには、ファイアウォール、SSL 中断/検査、パケット検査デバイス、およびデータ損失防止システムが含まれます。 エッジ デバイスの構成を構成したり更新したりするには、スクリプトまたは REST 呼び出しを使用して、Office 365 エンドポイントの Web サービスからエンドポイントの構造化リストを利用します。 詳細については、「[Office 365 IP アドレスと URL の Web サービス](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)」を参照してください。

なお、バイパスするのは、Microsoft 365 で "最適化" および "許可" カテゴリに含まれるエンドポイントに対するトラフィックのための通常のプロキシとネットワーク セキュリティ処理のみです。他のすべての一般的なインターネット トラフィックは、プロキシ処理され、既存のネットワーク セキュリティ処理の対象になります。

## <a name="optimizing-traffic-for-remote-workers-that-use-vpn-connections"></a>VPN 接続を使用するリモート ワーカーのためにトラフィックを最適化する

リモート ワーカーが組織のイントラネット上のリソースにアクセスするには、一般的に仮想プライベート ネットワーク (VPN) 接続を使用します。 従来の VPN 接続では、インターネット トラフィックを含むすべてのトラフィックが組織のイントラネットにルーティングされます。 インターネット トラフィックは、組織のエッジ ネットワークとパケット処理デバイスにルーティングされます。 このトラフィックの移動と処理には遅延が発生しやすく、遅延によってパフォーマンスが大幅に低下し、リモート ワークの生産性に影響する可能性があります。 

スプリット トンネリングは、VPN 接続でトラフィックをイントラネットに送信するのではなく、指定したトラフィックをインターネット経由でルーティングする VPN 接続の機能です。 リモート ワーカーが Teams、SharePoint Online、Exchange Online などの極めて重要な Microsoft 365 サービスに最適なパフォーマンスでアクセスできるようにするには、トラフィックを最適化カテゴリの Office 365 エンドポイントにインターネット経由で直接送信するように、スプリット トンネリング VPN 接続を構成します。 

詳細については、[VPN スプリット トンネリングを使用してリモート ユーザーの Office 365 の接続を最適化する](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)をご覧ください。

中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step4)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![手順 5](../media/stepnumbers/Step5.png)|[クライアントと Office 365 サービスのパフォーマンスを最適化する](networking-optimize-tcp-performance.md) |



