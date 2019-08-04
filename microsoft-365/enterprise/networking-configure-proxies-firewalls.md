---
title: '手順 4: トラフィック バイパスを構成する'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Office 365 が稼働している信頼できる場所にトラフィックをバイパスするのに必要となる Web ブラウザーとエッジ デバイスについて理解し、構成します。
ms.openlocfilehash: c7d4391d3274fd36a3f6fbf208cd94ce7b0f9339
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074227"
---
# <a name="step-4-configure-traffic-bypass"></a>手順 4: トラフィック バイパスを構成する

*この手順はオプションであり、Microsoft 365 Enterprise のバージョン E3 および E5 の両方に適用されます。*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

一般的なインターネット トラフィックにはリスクがあるため、組織のネットワークでは、通常、プロキシ サーバー、SSL 中断/検査、パケット検査デバイス、およびデータ損失防止システムのようなエッジ デバイスを使用して、セキュリティを適用します。ネットワーク傍受デバイスに関する問題については、「Office 365 トラフィックにサードパーティのネットワーク デバイスまたはソリューションを使用する」を参照してください。

ただし、Microsoft 365 のクラウドベース サービスで使用する DNS ドメイン名と IP アドレスはよく知られている上に、トラフィックとサービスは多くのセキュリティ機能で保護されています。この種のセキュリティと保護は既に適用されているので、エッジ デバイスで同じことを行う必要はありません。Microsoft 365 のトラフィックが、中間地点や重複するセキュリティ処理を経由する設定では、パフォーマンスが大幅に低下します。

中間地点や重複するセキュリティ処理を排除する最初の手順として、Microsoft 365 のトラフィックを識別します。Microsoft では、次の種類の DNS ドメイン名と IP アドレス範囲 (エンドポイントと呼ばれる) を定義しています。

- **最適化**: すべての Office 365 サービスへの接続に必須で、Microsoft 365 の帯域幅、接続、データ量の 75% 以上に相当します。 これらのエンドポイントは、ネットワーク パフォーマンス、待機時間、可用性の影響を最も受けやすい Microsoft 365 シナリオに該当します。
- **許可**: 特定の Microsoft 365 サービスや機能への接続に必須ですが、ネットワーク パフォーマンスや待機時間の影響は、最適化カテゴリのエンドポイントほど大きくありません。
 - **既定**: 最適化を必要としない Microsoft 365 サービスや依存関係を表します。 標準カテゴリのエンドポイントは、通常のインターネット トラフィックとして扱うことができます。

DNS ドメイン名と IP アドレスの範囲については、「[https://aka.ms/o365endpoints](https://aka.ms/o365endpoints)」を参照してください。

Microsoft では、次の方法を推奨しています。

- オンプレミスで使用するコンピューターのインターネット ブラウザー上で、プロキシ自動構成 (PAC) スクリプトを使用して、Microsoft 365 クラウドベース サービスの DNS ドメイン名用プロキシ サーバーをバイパスします。最新の Microsoft 365 PAC スクリプトについては、「Get-Pacfile PowerShell スクリプト」を参照してください。
- エッジ デバイスを分析して重複する処理を特定したら、それらのエッジ デバイスが "最適化" および "許可" エンドポイントにトラフィックを処理せずに転送するように構成します。これは、トラフィック バイパスと呼ばれます。 

エッジ デバイスには、ファイアウォール、SSL 中断/検査、パケット検査デバイス、およびデータ損失防止システムが含まれます。エッジ デバイスの構成と更新には、スクリプトや REST 呼び出しを使用して、Office 365 エンドポイント Web サービスから構造化されたエンドポイントのリストを使用できます。詳細については、「[Office 365 IP アドレスと URL の Web サービス](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)」を参照してください。

なお、バイパスするのは、Microsoft 365 で "最適化" および "許可" カテゴリに含まれるエンドポイントに対するトラフィックのための通常のプロキシとネットワーク セキュリティ処理のみです。他のすべての一般的なインターネット トラフィックは、プロキシ処理され、既存のネットワーク セキュリティ処理の対象になります。


中間チェックポイントとして、この手順の[終了条件](networking-exit-criteria.md#crit-networking-step4)を確認できます。

## <a name="next-step"></a>次の手順

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[クライアントと Office 365 サービスのパフォーマンスを最適化する](networking-optimize-tcp-performance.md) |



