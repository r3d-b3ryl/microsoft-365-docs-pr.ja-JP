---
title: メール フロー ダッシュボードの送信と受信のメール フロー分析情報
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 管理者は、セキュリティグループ ポリシー のメール フロー ダッシュボードで、送信と受信のメール フローのインサイトについて&できます。
ms.openlocfilehash: 920c1212f4d6dee508704c93272e48140e199710
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826895"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>コンプライアンス センターの送信と受信のメール &分析情報

セキュリティ & コンプライアンス**センターのメール フロー ダッシュボードの**送信[Mail flow dashboard](mail-flow-insights-v2.md)と受信のメール フローのインサイトでは、コネクタ レポートからの[Connector report](view-mail-flow-reports.md#connector-report)情報と、元の**TLS**概要レポートを 1 かの場所で結合します。

このウィジェットには、組織との間でメッセージが配信されたときの接続に使用される TLS 暗号化が表示されます。 他のメール サービスと確立される接続は、両方の側側で TLS が提供されている場合に TLS によって暗号化されます。 ウィジェットは、過去 1 週間のメール フローのスナップショットを提供します。

![セキュリティ コンプライアンス センターのメール フロー ダッシュボードの送信と受信のメール フロー ウィ& ウィジェット](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

ウィジェット内の情報は、Microsoft 365 のコネクタと TLS メッセージ保護に関連しています。 詳細については、以下のトピックを参照してください。

- [コネクタを使用してメール フローを構成する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [Exchange Online が TLS を使ってメール接続をセキュリティで保護する方法](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [Microsoft 365 の暗号化についてのテクニカル リファレンスの詳細](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a>送信中に保護されたメッセージ (TLS 別)

ウィジェ **ットの [詳細** の表示] をクリックすると、 **送信中に保護されたメッセージ (TLS で保護)** ポップアップに、組織が出入りするメッセージの TLS 保護が表示されます。

![[送信および受信メール ウィジェットの詳細を表示] をクリックした後に表示される、送信中 (TLS) ポップアップで保護されているメッセージ](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

現在、TLS 1.2 は Microsoft 365 が提供する TLS の中で最も安全なバージョンです。 多くの場合、コンプライアンス監査に使用される TLS 暗号化を知っておく必要があります。 送信元と宛先のほとんどの電子メール サーバーとの間には直接の関係がない可能性があるため (所有していないが Microsoft もしまっていない)、これらのサーバーで使用される TLS 暗号化を改善するオプションは多数ありません。

しかし、電子メール サーバー [と](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) Microsoft 365 の間で送信されるメッセージに対して利用可能な TLS 保護を確実にするためにコネクタを使用できます。 Microsoft 365 とパートナーに属している独自の電子メール サーバーやサーバー間のメール フローは通常のメッセージよりも重要かつ機密性の高いため、これらのメッセージには追加のセキュリティとアクセス性を適用したいと考えないでください。

使用中の TLS 暗号化の向上のために独自のメール サーバーをアップグレードまたは修正したり、パートナーに同じ操作を行ってもらう場合があります。 コネクタ **レポートには** 、Microsoft 365 コネクタを使用するメッセージのメール フロー ボリュームと TLS 暗号化の両方が表示されます。

コネクタ レポート リンク **をクリックして、** コネクタ レポートに [移動できます](view-mail-flow-reports.md#connector-report)。 関連する条件が検出された場合は、[コネクタ レポート] **ページで** 次の分析情報が使用可能となる可能性があります。

- **受信パートナー コネクタで、TLS1.0 の重要なメール フローが表示されている**
- **受信 OnPremises コネクタに関する、大幅な TLS1.0 メール フローが表示されている**

TLS 1.0 接続の場合、Microsoft 365 で TLS 1.0 のサポートが最終的に廃止された場合でも問題が発生しないように、電子メール サーバーまたはパートナーのサーバーをアップグレードまたは修正する必要があります。

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、セキュリティ コンプライアンス センターの [メール フローの詳細&を参照してください](mail-flow-insights-v2.md)。
