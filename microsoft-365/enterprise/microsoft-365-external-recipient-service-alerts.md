---
title: 外部受信者サービスの通知
ms.author: markjjo
author: markjjo
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
ms.openlocfilehash: 931be51ee51bd5557633415004eed9a1c7e77888
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331172"
---
# <a name="service-alerts-for-messages-pending-delivery-to-external-recipients-in-exchange-online-monitoring"></a>監視中の外部受信者への配信を保留しているメッセージに対するサービスExchange Online通知

サービスアラートは、管理者にメール キューが外部の受信者に通知Exchange Online。 これらのアラートには、Microsoft 以外の修復アクションが必要な場合がありますが、修復に必要な情報を提供できます。

これらのサービス通知は、サービス ウィンドウにMicrosoft 365 管理センター。 これらのサービス通知を表示するには、[**HealthService** >  正常性] に移動 <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">**Exchange Online**</a> > **、[アクティブ** な問題] **タブをクリック** します。これらのサービス 通知の名前は、「しきい値を超える外部受信者へのメッセージ キュー」です。

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

## <a name="more-information"></a>詳細

組織が、オンプレミスまたは組織のメール フロー コネクタを最近作成または変更したExchange Online詳細については、次の記事を参照してください。

- [コネクタを使用してメール フローを構成Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

- [メールをルーティングするコネクタの設定](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)

- [メール フローのベスト プラクティス](/exchange/mail-flow-best-practices/mail-flow-best-practices)

- [セキュリティとコンプライアンス センターのメッセージ追跡の分析情報](/microsoft-365/security/office-365-security/mail-flow-insights-v2)

- [メール フロー ダッシュボードのキューの分析情報](/microsoft-365/security/office-365-security/mfi-queue-alerts-and-queues#queues-insight-in-the-mail-flow-dashboard)

- [[メール メッセージの追跡] Exchange Online](/exchange/monitoring/trace-an-email-message/trace-an-email-message)
