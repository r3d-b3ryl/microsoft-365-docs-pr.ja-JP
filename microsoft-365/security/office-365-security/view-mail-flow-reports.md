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
description: 管理者は、セキュリティ コンプライアンス センターの [レポート] ダッシュボードで使用できるメール フロー &できます。
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
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>セキュリティ コンプライアンス センターの [レポート] ダッシュボードでメール フロー レポート&表示する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
>
> この記事のレポートの大部分は、Microsoft 365 Defender Exchange管理センター (EAC) でも利用できます。 詳細については、次のトピックをご覧ください。
>
> - [新しい管理センターのメール フロー Exchangeレポート](/exchange/monitoring/mail-flow-reports/mail-flow-reports)
> - [ポータルで電子メール セキュリティ レポートをMicrosoft 365 Defenderする](view-email-security-reports.md)

セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで使用できるメール [](mail-flow-insights-v2.md) フロー レポートに加えて、レポート ダッシュボードには、Microsoft 365 組織の監視に役立つさまざまなメール フロー レポートがあります。

必要なアクセス許可 [がある](#what-permissions-are-needed-to-view-these-reports)場合は、[レポート ダッシュボード] に移動して、セキュリティ &コンプライアンス センターで <https://protection.office.com> これらのレポート **を表示** \> **できます**。 レポート ダッシュボードに直接移動するには、を開きます <https://protection.office.com/insightdashboard>。

:::image type="content" source="../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png" alt-text="セキュリティ コンプライアンス センターの [レポート] &ダッシュボード" lightbox="../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png":::

## <a name="connector-report"></a>コネクタ レポート

> [!NOTE]
> このレポートは、EAC の **受信** メッセージ レポートと **送信メッセージ レポート** に置き換えられた。 詳細については、「新しい [EAC の受信メッセージと送信メッセージ レポート」を参照してください](/exchange/monitoring/mail-flow-reports/mfr-inbound-messages-and-outbound-messages-reports)。

## <a name="exchange-transport-rule-report"></a>Exchangeルール レポート

トランスポート **Exchangeレポート** には、組織内の受信メッセージと送信メッセージに対するメール フロー ルール (トランスポート ルールとも呼ばれる) の影響が表示されます。

レポートを表示するには、コンプライアンス センターの [セキュリティ &] を開き、[<https://protection.office.com>\>レポート ダッシュボード] に移動し、[トランスポート ルールExchange **選択します**。 レポートに直接移動するには、を開きます <https://security.microsoft.com/reports/ETRRuleReport>。

:::image type="content" source="../../media/scc-transport-rule-report-widget.png" alt-text="レポート Exchangeのトランスポート ルール ウィジェット" lightbox="../../media/scc-transport-rule-report-widget.png":::

> [!NOTE]
> EAC **Exchangeトランスポート ルール レポート** を使用できます。 詳細については、「新しい [EAC Exchangeトランスポート ルール レポート」を参照してください](/exchange/monitoring/mail-flow-reports/mfr-exchange-transport-rule-report)。

## <a name="forwarding-report"></a>転送レポート

> [!NOTE]
> 転送 **レポートは** EAC で利用できます。 詳細については、「新しい [EAC の自動転送メッセージ レポート」を参照してください](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)。

## <a name="mailflow-status-report"></a>メールフローの状態レポート

メール **フローの状態レポートは**、送信済 [](#sent-and-received-email-report)みおよび受信済みメール レポートに似ています。電子メールに関する追加情報がエッジで許可またはブロックされています。 これは、エッジ保護情報を含む唯一のレポートであり、EOP (EOP) による評価のためにサービスに許可される前にブロックされる電子メールの量Exchange Online Protection示しています。 メッセージが 5 人の受信者に送信された場合、メッセージは 1 つのメッセージではなく 5 つの異なるメッセージとしてカウントされます。

レポートを表示するには、コンプライアンス センターでセキュリティ &[開](https://protection.office.com)\>き、[レポート ダッシュボード] に移動し、[メールフローの状態レポート **] を選択します**。 メール フローの状態レポートに **直接移動するには、** を開きます <https://security.microsoft.com/reports/mailflowStatusReport>。

:::image type="content" source="../../media/scc-mail-flow-status-report-widget.png" alt-text="レポート ダッシュボードのメールフロー状態レポート ウィジェット" lightbox="../../media/scc-mail-flow-status-report-widget.png":::

> [!NOTE]
> セキュリティ & コンプライアンス センター (protection.office.com) でこのレポートのウィジェットをクリックすると、Microsoft 365 Defender ポータル (security.microsoft.com) の完全なレポートが表示されます。 レポートの詳細については、「 [Mailflow status report」を参照してください](view-email-security-reports.md#mailflow-status-report)。

## <a name="sent-and-received-email-report"></a>送信および受信した電子メール レポート

> [!NOTE]
> このレポートは、 [Mailflow 状態レポートに置き換えられた](#mailflow-status-report)。

## <a name="top-senders-and-recipients-report"></a>上位の送信者と受信者レポート

[**上位の送信者** と受信者] には、組織内の上位メッセージ送信者と、EOP および Defender によって検出されたメッセージの上位受信者が Office 365 保護機能で表示されます。

レポートを表示するには、コンプライアンス センターでセキュリティ &を<https://protection.office.com>\>開き、[レポート ダッシュボード] に移動し、[上位の送信者と受信者 **] を選択します**。 レポートに直接移動するには、次のいずれかの URL を開きます。

- Defender for Office 365:<https://protection.office.com/TopSenderRecipientsATP>
- EOP: <https://protection.office.com/TopSenderRecipients>

:::image type="content" source="../../media/scc-top-senders-and-recipients-widget.png" alt-text="レポート ダッシュボードの [上位の送信者と受信者] ウィジェット" lightbox="../../media/scc-top-senders-and-recipients-widget.png":::

> [!NOTE]
> セキュリティ & コンプライアンス センターでこのレポートのウィジェットをクリックすると、protection.office.com ページに移動しますが、ページのコンテンツは Microsoft 365 Defender ポータルから提供されます。 レポートの詳細については、「上位の送信者 [と受信者レポート」を参照してください](view-email-security-reports.md#top-senders-and-recipients-report)。

## <a name="what-permissions-are-needed-to-view-these-reports"></a>これらのレポートを表示するために必要なアクセス許可

この記事で説明するレポートを表示および使用するには、セキュリティ コンプライアンス センターで次のいずれかの役割グループの&必要があります。

- **組織の管理**
- **セキュリティ管理者**
- **セキュリティ リーダー**
- **グローバル リーダー**

詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

> [!NOTE]
> Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](../../admin/add-users/about-admin-roles.md)」を参照してください。

## <a name="related-topics"></a>関連項目

[セキュリティ/コンプライアンス センターのスマート レポートと分析情報](reports-and-insights-in-security-and-compliance.md)

[セキュリティとコンプライアンス センターのメッセージ追跡の分析情報](mail-flow-insights-v2.md)

[セキュリティとコンプライアンス センターで電子メールのセキュリティ レポートを表示する](view-email-security-reports.md)

[Microsoft Defender for microsoft Defender for Office 365](view-reports-for-mdo.md)
