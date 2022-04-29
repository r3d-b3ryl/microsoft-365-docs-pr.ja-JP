---
title: メール フロー ダッシュボードの送信メール フローと受信メール フローの分析情報
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで、送信メール フローと受信メール フローの分析情報を確認できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f856e2b9a4829531966802f2594f26c19e6ab7e5
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65131198"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>セキュリティ & コンプライアンス センターの送信および受信メール フローの分析情報

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[セキュリティ & コンプライアンス センター](https://protection.office.com)の [メール フロー ダッシュボード](mail-flow-insights-v2.md)の **送信および受信メール フロー** の分析情報は、[コネクタ レポート](view-mail-flow-reports.md#connector-report)と以前の **TLS 概要レポート** の情報を 1 か所にまとめます。

ウィジェットには、組織との間でメッセージが配信されるときに接続に使用される TLS 暗号化が表示されます。 他の電子メール サービスで確立された接続は、TLS が両側から提供されるときに TLS によって暗号化されます。 このウィジェットは、メール フローの最後の週のスナップショットを提供します。

:::image type="content" source="../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png" alt-text="セキュリティ & コンプライアンス センターのメール フロー ダッシュボードの送信および受信メール フロー ウィジェット" lightbox="../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png":::

ウィジェットの情報は、Microsoft 365のコネクタと TLS メッセージ保護に関連しています。 詳細については、以下のトピックを参照してください。

- [コネクタを使用してメール フローを構成する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [メール接続をセキュリティで保護するために、Exchange Online が TLS を使用する方法](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [Microsoft 365での暗号化に関するテクニカル リファレンスの詳細](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a>転送中に保護されたメッセージ (TLS によって)

ウィジェットで **[詳細の表示** ] をクリックすると、 **転送中に保護されたメッセージ (TLS によって)** ポップアップに、組織に出入りするメッセージに対する TLS 保護が表示されます。

:::image type="content" source="../../media/mfi-outbound-and-inbound-mail-flow-report-details.png" alt-text="送信および受信電子メール ウィジェットで [詳細の表示] をクリックした後に表示される転送中に保護されたメッセージ (TLS によって) ポップアップ" lightbox="../../media/mfi-outbound-and-inbound-mail-flow-report-details.png":::

現在、TLS 1.2 は、Microsoft 365によって提供される TLS の最も安全なバージョンです。 多くの場合、コンプライアンス監査に使用されている TLS 暗号化を把握しておく必要があります。 ほとんどの送信元と宛先の電子メール サーバーと直接的な関係がない可能性があります (これらは所有されておらず、Microsoft も所有していません)。そのため、それらのサーバーで使用される TLS 暗号化を改善するためのオプションはあまりありません。

ただし、[コネクタ](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)を使用して、電子メール サーバーとMicrosoft 365間で送信されるメッセージに対して最大限の TLS 保護を確保できます。 Microsoft 365とパートナーに属する独自の電子メール サーバーまたはサーバー間のメール フローは、通常のメッセージよりも重要で機密性が高いことが多いため、これらのメッセージにセキュリティと警戒を追加で適用する必要があります。

独自の電子メール サーバーをアップグレードまたは修正して、使用されている TLS 暗号化を改善したり、パートナーに連絡して同じ操作を行ったりすることができます。 **コネクタ レポート** には、Microsoft 365 コネクタを使用するメッセージのメール フロー ボリュームと TLS 暗号化の両方が表示されます。

**コネクタ レポート** のリンクをクリックすると、[コネクタ レポート](view-mail-flow-reports.md#connector-report)に移動できます。 関連する条件が検出された場合は、 **コネクタ レポート** ページで次の分析情報を使用できます。

- **重要な TLS1.0 メール フローが表示される受信パートナー コネクタ**
- **受信 OnPremises コネクタに重大な TLS1.0 メール フローが表示される**

TLS 1.0 接続の場合、tls 1.0 のサポートが最終的にMicrosoft 365で非推奨になった場合に問題が発生しないように、メール サーバーまたはパートナーのサーバーをアップグレードまたは修正する必要があります。

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードのその他の分析情報については、 [セキュリティ & コンプライアンス センターのメール フロー分析情報に関する](mail-flow-insights-v2.md)ページを参照してください。
