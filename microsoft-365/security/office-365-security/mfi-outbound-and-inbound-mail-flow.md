---
title: メールフローダッシュボードでの送信および受信メールフローの洞察
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 8/7/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードでの送信および受信メールフローの洞察について理解できます。
ms.openlocfilehash: 347e53c51c347f12795008d39458773a94ff433f
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577387"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンスセンターにおける送信および受信メールフローの洞察

セキュリティ & コンプライアンスセンターの[メールフローダッシュボード](mail-flow-insights-v2.md)に記載されている**送信および受信メールフロー**の洞察は、[コネクタレポート](view-mail-flow-reports.md#connector-report)と以前の**TLS 概要レポート**の情報を1つの場所にまとめたものです。

ウィジェットには、組織との間でメッセージが配信されるときに接続に使用される TLS 暗号化が表示されます。 他の電子メールサービスで確立された接続は、両方の側で TLS が提供されるときに TLS によって暗号化されます。 このウィジェットは、メールフローの最終週のスナップショットを提供します。

![セキュリティ & コンプライアンスセンターのメールフローダッシュボードの送信および受信メールフローウィジェット](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

ウィジェットの情報は、Microsoft 365 のコネクタと TLS メッセージ保護に関連しています。 詳細については、以下のトピックを参照してください。

- [コネクタを使用してメール フローを構成する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Exchange Online が TLS を使用して電子メール接続をセキュリティで保護する方法](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [Microsoft 365 での暗号化に関するテクニカルリファレンスの詳細](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a>送信で保護されたメッセージ (TLS)

ウィジェットの [**詳細の表示**] をクリックすると、[**送信中 (TLS) で保護さ**れたメッセージ] ポップアップには、組織に出入りするメッセージの TLS 保護が表示されます。

![送信および受信電子メールウィジェットの [詳細の表示] をクリックした後に表示される、転送中 (TLS) のポップアップで保護されたメッセージ](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

現時点では、TLS 1.2 は、Microsoft 365 で提供されている最も安全な TLS のバージョンです。 多くの場合、コンプライアンス監査に使用されている TLS 暗号化を知っておく必要があります。 ほとんどの場合、送信元および送信先の電子メールサーバー (それらを所有しておらず、Microsoft も対象としていません) との直接的な関係はありません。そのため、これらのサーバーで使用される TLS 暗号化を改善するためのオプションは多くありません。

ただし、[コネクタ](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)を使用して、電子メールサーバーと Microsoft 365 との間で送信されるメッセージに最適な TLS 保護を確保することができます。 Microsoft 365 と、パートナーに属する独自の電子メールサーバーまたはサーバー間のメールフローは、通常のメッセージよりも重要で重要なものなので、追加のセキュリティと警戒をこれらのメッセージに適用する必要があります。

独自の電子メールサーバーをアップグレードまたは修正して、使用されている TLS 暗号化を改善したり、パートナーに接続して同じ操作を実行したりすることができます。 **コネクタレポート**には、Microsoft 365 コネクタを使用するメッセージのメールフローボリュームと TLS 暗号化の両方が表示されます。

[**コネクタレポート**] リンクをクリックすると、[コネクタレポート](view-mail-flow-reports.md#connector-report)に移動できます。 関連付けられている条件が検出された場合、次の洞察が**コネクタレポート**ページに表示されることがあります。

- **受信パートナーコネクタが重要な TLS 1.0 メールフローを参照している**
- **受信 OnPremises connector で、TLS 1.0 メールフローが重要**

TLS 1.0 接続の場合、実際には、Microsoft 365 で TLS 1.0 サポートが廃止された場合の問題を回避するために、電子メールサーバーまたはパートナーのサーバーをアップグレードまたは修正する必要があります。

## <a name="see-also"></a>関連項目

メールフローダッシュボードの他の洞察の詳細については、「[セキュリティ & コンプライアンスセンター」の「mail flow insights](mail-flow-insights-v2.md)」を参照してください。
