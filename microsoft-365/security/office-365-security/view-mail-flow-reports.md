---
title: レポート ダッシュボードでメール フロー レポートを表示する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ & コンプライアンス センターのレポート ダッシュボードで使用できるメール フロー レポートについて学習できます。
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d1fc133a8e05541f402e35cf8d62ee9662af661b
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476227"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>セキュリティ & コンプライアンス センターのレポート ダッシュボードでメール フロー レポートを表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> この記事のほとんどのレポートは、Microsoft 365 Defender ポータルまたはExchange管理センター (EAC) でも利用できます。 詳細については、次のトピックをご覧ください。
>
> - [新しいExchange管理センターのメール フロー レポート](/exchange/monitoring/mail-flow-reports/mail-flow-reports)
> - [Microsoft 365 Defender ポータルで電子メール セキュリティ レポートを表示する](view-email-security-reports.md)

セキュリティ & コンプライアンス センターの[メール フロー ダッシュボード](mail-flow-insights-v2.md)で使用できるメール フロー レポートに加えて、レポート ダッシュボードには、Microsoft 365組織の監視に役立つさまざまな追加のメール フロー レポートが用意されています。

[必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合は、レポート **ダッシュボード** に移動して、セキュリティ & コンプライアンス センターで<https://protection.office.com>これらの **レポート**\>を表示できます。 レポート ダッシュボードに直接移動するには、を開きます <https://protection.office.com/insightdashboard>。

:::image type="content" source="../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png" alt-text="セキュリティ & コンプライアンス センターのレポート ダッシュボード" lightbox="../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png":::

## <a name="connector-report"></a>コネクタ レポート

> [!NOTE]
> このレポートは、EAC の **受信メッセージ レポート** と **送信メッセージ レポート** に置き換えられました。 詳細については、 [新しい EAC の受信メッセージと送信メッセージのレポートに関するページを参照](/exchange/monitoring/mail-flow-reports/mfr-inbound-messages-and-outbound-messages-reports)してください。

## <a name="exchange-transport-rule-report"></a>Exchange トランスポート ルール レポート

**Exchangeトランスポート ルール レポート** は、組織内の受信メッセージと送信メッセージに対するメール フロー ルール (トランスポート ルールとも呼ばれます) の効果を示します。

レポートを表示するには、セキュリティ & コンプライアンス センターを<https://protection.office.com>開き、**レポート** \> **ダッシュボード** に移動し **、トランスポート ルールExchange** 選択します。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/ETRRuleReport>。

:::image type="content" source="../../media/scc-transport-rule-report-widget.png" alt-text="レポート ダッシュボードのExchangeトランスポート ルール ウィジェット" lightbox="../../media/scc-transport-rule-report-widget.png":::

> [!NOTE]
> **Exchangeトランスポート ルール レポート** が EAC で使用できるようになりました。 詳細については、[新しい EAC のトランスポート ルール レポートExchangeを参照してください](/exchange/monitoring/mail-flow-reports/mfr-exchange-transport-rule-report)。

## <a name="forwarding-report"></a>転送レポート

> [!NOTE]
> **転送レポート** は EAC で使用できるようになりました。 詳細については、 [新しい EAC の自動転送メッセージ レポートに関するページを参照してください](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)。

## <a name="mailflow-status-report"></a>Mailflow 状態レポート

**メールフローの状態レポート** は、送受信 [された電子メール レポートに](#sent-and-received-email-report)似ています。メールに関する追加情報は、エッジで許可またはブロックされます。 これは、エッジ保護情報を含む唯一のレポートであり、Exchange Online Protection (EOP) による評価のためにサービスに許可される前にブロックされる電子メールの量のみを示します。 メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされることを理解することが重要です。

レポートを表示するには、 [セキュリティ & コンプライアンス センター](https://protection.office.com)を開き、 **レポート** \> **ダッシュボード** に移動し、 **Mailflow 状態レポート** を選択します。 **メール フローの状態レポート** に直接移動するには、を開きます<https://security.microsoft.com/reports/mailflowStatusReport>。

:::image type="content" source="../../media/scc-mail-flow-status-report-widget.png" alt-text="レポート ダッシュボードの Mailflow 状態レポート ウィジェット" lightbox="../../media/scc-mail-flow-status-report-widget.png":::

> [!NOTE]
> セキュリティ & コンプライアンス センター (protection.office.com) でこのレポートのウィジェットをクリックすると、Microsoft 365 Defender ポータル (security.microsoft.com) で完全なレポートが表示されます。 レポートの詳細については、「 [Mailflow 状態レポート](view-email-security-reports.md#mailflow-status-report)」を参照してください。

## <a name="sent-and-received-email-report"></a>送受信された電子メール レポート

> [!NOTE]
> このレポートは、 [Mailflow 状態レポート](#mailflow-status-report)に置き換えられました。

## <a name="top-senders-and-recipients-report"></a>上位の送信者と受信者のレポート

**上位の送信者と受信者** には、組織内の上位メッセージ送信者と、EOP およびDefender for Office 365保護機能によって検出されたメッセージの上位受信者が表示されます。

レポートを表示するには、セキュリティ & コンプライアンス センターを <https://protection.office.com>開き、 **レポート** \> **ダッシュボード** に移動し、[ **上位の送信者と受信者**] を選択します。 レポートに直接移動するには、次のいずれかの URL を開きます。

- Defender for Office 365:<https://protection.office.com/TopSenderRecipientsATP>
- EOP： <https://protection.office.com/TopSenderRecipients>

:::image type="content" source="../../media/scc-top-senders-and-recipients-widget.png" alt-text="レポート ダッシュボードの上位送信者と受信者ウィジェット" lightbox="../../media/scc-top-senders-and-recipients-widget.png":::

> [!NOTE]
> セキュリティ & コンプライアンス センターでこのレポートのウィジェットをクリックすると、protection.office.com ページに移動しますが、ページコンテンツはMicrosoft 365 Defender ポータルから取得されます。 レポートの詳細については、「 [上位の送信者と受信者のレポート](view-email-security-reports.md#top-senders-and-recipients-report)」を参照してください。

## <a name="what-permissions-are-needed-to-view-these-reports"></a>これらのレポートを表示するには、どのようなアクセス許可が必要ですか?

この記事で説明されているレポートを表示して使用するには、セキュリティ & コンプライアンス センターで次のいずれかの役割グループのメンバーである必要があります。

- **組織の管理**
- **セキュリティ管理者**
- **セキュリティ閲覧者**
- **グローバル閲覧者**

詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

> [!NOTE]
> Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="related-topics"></a>関連項目

[セキュリティ/コンプライアンス センターのスマート レポートと分析情報](reports-and-insights-in-security-and-compliance.md)

[セキュリティとコンプライアンス センターのメッセージ追跡の分析情報](mail-flow-insights-v2.md)

[セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する](view-email-security-reports.md)

[Microsoft Defender for Office 365のレポートを表示する](view-reports-for-mdo.md)
