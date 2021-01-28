---
title: メール フロー ダッシュボードでの送信および受信メール フローの分析情報
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: f2738dec-41b0-43c4-b814-84c0a4e45c6d
description: 管理者は、セキュリティ/コンプライアンス センターのメール フロー ダッシュボードで、送信メール フローと受信メール フロー&確認できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e46a0ebf0c14e31462d1e86d8a8d8c08486337af
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029824"
---
# <a name="outbound-and-inbound-mail-flow-insight-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターでの送信および受信メール フロー&分析情報

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


セキュリティ & コンプライアンス センターのメール フロー [](mail-flow-insights-v2.md)ダッシュボードの送信および [](https://protection.office.com)受信メール フローの分析情報は、[コネクタ](view-mail-flow-reports.md#connector-report)レポートと以前の **TLS** 概要レポートからの情報を 1 か所で結合します。

ウィジェットは、メッセージが組織との間で配信される場合に接続に使用される TLS 暗号化を表示します。 他の電子メール サービスとの接続は、TLS が両側で提供される場合に TLS によって暗号化されます。 ウィジェットは、メール フローの最後の週のスナップショットを提供します。

![セキュリティ/コンプライアンス センターのメール フロー ダッシュボードの送信および受信&ウィジェット](../../media/mfi-outbound-and-inbound-mail-flow-report-widget.png)

ウィジェットの情報は、Microsoft 365 のコネクタと TLS メッセージ保護に関連しています。 詳細については、以下のトピックを参照してください。

- [コネクタを使用してメール フローを構成する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)
- [メール接続をセキュリティで保護するために、Exchange Online が TLS を使用する方法](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-uses-tls-to-secure-email-connections)
- [Microsoft 365 での暗号化に関するテクニカル リファレンスの詳細](https://docs.microsoft.com/microsoft-365/compliance/technical-reference-details-about-encryption)

## <a name="message-protected-in-transit-by-tls"></a>転送中に保護されたメッセージ (TLS により)

ウィジェットの [詳細 **の** 表示] をクリックすると、転送中 **に (TLS によって)** 保護されたメッセージのフライアウトに、組織に入り出るメッセージの TLS 保護が表示されます。

![送信および受信電子メール ウィジェットの [詳細の表示] をクリックした後に表示される転送中に保護されたメッセージ (TLS による) フライアウト](../../media/mfi-outbound-and-inbound-mail-flow-report-details.png)

現在、TLS 1.2 は、Microsoft 365 が提供する最も安全なバージョンの TLS です。 多くの場合、コンプライアンス監査に使用されている TLS 暗号化を知る必要があります。 ほとんどの送信元および送信先の電子メール サーバーと直接的な関係を持たないので (自分は所有していないし、Microsoft もそうしていない)、これらのサーバーで使用される TLS 暗号化を改善するオプションは多くはありません。

ただし、コネクタ [を使用して](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) 、電子メール サーバーと Microsoft 365 の間で送信されるメッセージに対して最適な TLS 保護を確保できます。 Microsoft 365 とパートナーに属する独自の電子メール サーバーまたはサーバー間のメール フローは、通常のメッセージよりも重要で機密性が高い場合が多いので、これらのメッセージに対して追加のセキュリティと影響を適用する必要があります。

独自の電子メール サーバーをアップグレードまたは修正して、使用されている TLS 暗号化を向上させるか、パートナーに連絡して同じことを行います。 コネクタ **レポートには、Microsoft** 365 コネクタを使用するメッセージのメール フロー ボリュームと TLS 暗号化の両方が表示されます。

コネクタ レポートのリンク **をクリック** すると、コネクタ レポートに [移動できます](view-mail-flow-reports.md#connector-report)。 関連する条件が検出された場合は、[ **コネクタ** ] レポート ページで次の分析情報を使用できます。

- **受信パートナー コネクタに重大な TLS1.0 メール フローが表示される**
- **受信 OnPremises コネクタに重大な TLS1.0 メール フローが表示される**

TLS 1.0 接続の場合、TLS 1.0 のサポートが最終的に Microsoft 365 で廃止された場合に問題を回避するには、メール サーバーまたはパートナーのサーバーをアップグレードまたは修正する必要があります。

## <a name="see-also"></a>関連項目

メール フロー ダッシュボードの他の分析情報については、セキュリティ/コンプライアンス センターの「メール [フロー&参照してください](mail-flow-insights-v2.md)。
