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
description: 管理者は、セキュリティ コンプライアンス センターのメール フロー ダッシュボードで、送信メール フローと受信メール フロー&できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3bc9d6c08dfc1c232018d79e988d741505079604
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64475721"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターでの送信メール フローと受信メール フロー&分析

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[](mail-flow-insights-v2.md)セキュリティ **&** コンプライアンス センターのメール フロー ダッシュボードの送信メール フローと受信メール フロー [](https://protection.office.com)の分析情報は、コネクタ レポートと以前の **TLS** 概要 [](view-mail-flow-reports.md#connector-report)レポートの情報を 1 か所で結合します。

ウィジェットには、組織との間でメッセージが配信される際に接続に使用される TLS 暗号化が表示されます。 他の電子メール サービスで確立された接続は、TLS が両側から提供される場合、TLS によって暗号化されます。 ウィジェットは、メール フローの最後の週のスナップショットを提供します。

:::image type="content" source="../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png" alt-text="セキュリティ コンプライアンス センターの [メール フロー] ダッシュボードの送信および受信メール フロー &ウィジェット" lightbox="../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png":::

ウィジェット内の情報は、コネクタと TLS メッセージ保護に関連Microsoft 365。 詳細については、以下のトピックを参照してください。

- [コネクタを使用してメール フローを構成する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [メール接続をセキュリティで保護するために、Exchange Online が TLS を使用する方法](../../compliance/exchange-online-uses-tls-to-secure-email-connections.md)
- [暗号化に関するテクニカル リファレンスMicrosoft 365](../../compliance/technical-reference-details-about-encryption.md)

## <a name="message-protected-in-transit-by-tls"></a>転送中に保護されたメッセージ (TLS によって)

ウィジェットの [ **詳細の表示]** をクリックすると、転送中 **に保護されたメッセージ (TLS によって)** フライアウトに、組織に入退出するメッセージに対する TLS 保護が表示されます。

:::image type="content" source="../../media/mfi-outbound-and-inbound-mail-flow-report-details.png" alt-text="送信メール ウィジェットと受信メール ウィジェットの [詳細の表示] をクリックした後に表示される、転送中に保護されたメッセージ (TLS) のフライアウト" lightbox="../../media/mfi-outbound-and-inbound-mail-flow-report-details.png":::

現在、TLS 1.2 は、ユーザーが提供する TLS の最も安全なMicrosoft 365。 多くの場合、コンプライアンス監査に使用されている TLS 暗号化を知る必要があります。 ほとんどの送信元および宛先の電子メール サーバー (所有していない、Microsoft は所有していない) と直接関係がない可能性があります。そのため、これらのサーバーで使用される TLS 暗号化を改善するためのオプションは多くはありません。

ただし、コネクタを使用[して](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)、電子メール サーバーとメール サーバー間で送信されるメッセージに対して最適な TLS 保護をMicrosoft 365。 Microsoft 365 とパートナーに属する独自の電子メール サーバーまたはサーバー間のメール フローは、通常のメッセージよりも重要で機密性が高い場合が多いので、それらのメッセージにセキュリティと注意を追加する必要があります。

自分のメール サーバーをアップグレードまたは修正して、使用されている TLS 暗号化を向上させるか、パートナーに連絡して同じことを行います。 コネクタ **レポートには、** コネクタ コネクタを使用するメッセージのメール フロー ボリュームと TLS 暗号化Microsoft 365表示されます。

[コネクタ レポート] **リンクをクリックすると** 、コネクタ レポートに [移動できます](view-mail-flow-reports.md#connector-report)。 関連付けられた条件が検出された場合は、[ **コネクタ** ] レポート ページで次の分析情報を使用できます。

- **重要な TLS1.0 メール フローが表示される受信パートナー コネクタ**
- **重要な TLS1.0 メール フローが表示される受信 OnPremises コネクタ**

TLS 1.0 接続の場合は、Microsoft 365 で TLS 1.0 のサポートが最終的に廃止された場合に問題が発生しないように、メール サーバーまたはパートナーのサーバーをアップグレードまたは修正する必要があります。

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、「Security [& コンプライアンス センター」を参照してください](mail-flow-insights-v2.md)。