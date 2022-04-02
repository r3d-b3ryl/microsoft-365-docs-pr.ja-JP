---
title: 外部受信者サービスの通知
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- admindeeplinkMAC
- admindeeplinkEXCHANGE
f1.keywords:
- NOCSH
description: 外部受信者サービス通知を使用して、メールボックスクォータに達している保留状態のメールボックスを監視します。
ms.openlocfilehash: 8db8e090ec5430f13153bc3edf5b3315c041d9cf
ms.sourcegitcommit: a4729532278de62f80f2160825d446f6ecd36995
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2022
ms.locfileid: "64568008"
---
# <a name="service-alerts-for-messages-pending-delivery-to-external-recipients-in-exchange-online-monitoring"></a>監視中の外部受信者への配信を保留しているメッセージに対するサービスExchange Online通知

サービスアラートは、管理者にメール キューが外部の受信者に通知Exchange Online。 これらのアラートには、Microsoft 以外の修復アクションが必要な場合がありますが、修復に必要な情報を提供できます。

これらのサービス通知は、サービス ウィンドウにMicrosoft 365 管理センター。 これらのサービス通知を表示するには、[<a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank"></a> >  > 正常性サービス正常性Exchange Online] に移動し **、[** アクティブな問題] **タブをクリック** します。これらのサービス 通知の名前は、「しきい値を超える外部受信者へのメッセージ キュー」です。

![監視ダッシュボードに表示される外部受信者への配信を保留しているメッセージExchange Online通知します。](../media/microsoft-365-exchange-monitoring/ExternalRecipientsServiceAlerts1.png)

サービス アラートをダブルクリックすると、次のようなフライアウト ページが表示されます。

![外部受信者への配信を保留しているメッセージのサービス アラート内のコンテンツ。](../media/microsoft-365-exchange-monitoring/ExternalRecipientsServiceAlerts2.png)

## <a name="what-do-these-service-alerts-indicate"></a>これらのサービスアラートは何を示していますか?

外部受信者への配信を保留しているメッセージに対するサービス通知では、外部の受信者宛てのメッセージがExchange Onlineされる可能性があります。 メッセージのキューは、オンプレミス環境またはサードパーティのメッセージングまたはジャーナリング ソリューションによって発生する可能性があります。

外部受信者にメッセージをキューに入れ込む一般的な理由を次に示します。 ただし、これらのサービス通知の原因となる問題は、これらの理由に限定されない場合があります。

- DNS の変更

- 過剰な送信速度

- ディスク容量が少ないオンプレミスのメッセージ転送エージェント (MTA) またはジャーナリング ソリューション

- バックプレキュアの MTA

- ロード バランサーを含むネットワークの問題

- 証明書の問題

各サービスアラートには、問題を修復する上での高レベルの推奨事項が含まれている。 また、サービスアラートは、アラート時にキューに入っているメッセージの数、メッセージがキューに入っているドメイン、およびキューに入っているほとんどのメッセージに関連付けられた SMTP エラー コードも示します。

これらのサービス通知の根本原因を特定する方法の詳細については、「メール フロー インテリジェンス」を参照[Exchange Online。](../security/office-365-security/mail-flow-intelligence-in-office-365.md) この記事には、根本原因を修正するための推奨されるアクションも含まれています。

> [!NOTE]
> Microsoft は、サード パーティベンダーが提供する SMTP エラー コードを考慮することはできません。 そのため、管理者は、組織で使用する MTA またはジャーナリング ソリューションに固有のエラー コードを調査する必要があります。

## <a name="more-information"></a>詳細情報

組織が、オンプレミスまたは組織のメール フロー コネクタを最近作成または変更したExchange Online詳細については、次の記事を参照してください。

- [Exchange Online でコネクタを使用してメール フローを構成する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

- [メールをルーティングするコネクタの設定](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)

- [メール フローのベスト プラクティス](/exchange/mail-flow-best-practices/mail-flow-best-practices)

- [セキュリティとコンプライアンス センターのメッセージ追跡の分析情報](/microsoft-365/security/office-365-security/mail-flow-insights-v2)

- [メール フロー ダッシュボードのキューの分析情報](/microsoft-365/security/office-365-security/mfi-queue-alerts-and-queues#queues-insight-in-the-mail-flow-dashboard)

- [[メール メッセージの追跡] Exchange Online](/exchange/monitoring/trace-an-email-message/trace-an-email-message)
