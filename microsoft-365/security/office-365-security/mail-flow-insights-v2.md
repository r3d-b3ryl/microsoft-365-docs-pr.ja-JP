---
title: メール フロー ダッシュボードのメール フロー分析情報
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: overview
ms.collection: M365-security-compliance
ms.localizationpriority: medium
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで使用できる分析情報とレポートについて学習できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5850612fbd0de89e5eafe101f55d368b0f4b0c8f
ms.sourcegitcommit: 725a92b0b1555572b306b285a0e7a7614d34e5e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/24/2022
ms.locfileid: "65648725"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センター のメール フロー インサイト

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードを使用して、傾向、分析情報を検出し、組織内のメール フローに関連する問題を解決するためのアクションを実行できます。

:::image type="content" source="../../media/mail-flow-dashboard-v2.png" alt-text="セキュリティ & コンプライアンス センターのメール フロー ダッシュボード" lightbox="../../media/mail-flow-dashboard-v2.png":::

使用可能な分析情報は次のとおりです。

- [自動転送されたメッセージのインサイト](mfi-auto-forwarded-messages-report.md)
- [可能なメール ループ分析情報](mfi-mail-loop-insight.md) <sup>1 を</sup>修正する
- [低速メール フロー ルールの分析情報](mfi-slow-mail-flow-rules-insight.md) <sup>1</sup> を修正する
- [メール フローのマップ](mfi-mail-flow-map-report.md)
- [新しいドメインが転送される電子メール分析情報](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>
- [メール分析情報を転送する新しいユーザー](mfi-new-users-forwarding-email.md) <sup>2</sup>
- [承認されていないドメインのレポート](mfi-non-accepted-domain-report.md)
- [配信不能レポート](mfi-non-delivery-report.md)
- [送信および受信メール フローのインサイト](mfi-outbound-and-inbound-mail-flow.md)
- [キューのインサイト](mfi-queue-alerts-and-queues.md)
- [SMTP Auth クライアントのインサイトとレポート](mfi-smtp-auth-clients-report.md)
- [トップドメインのメール フローの状態洞察](mfi-domain-mail-flow-status-insight.md)　

<sup>1</sup> この分析情報は、問題が検出された後にのみ、[メール フロー] ダッシュボードの **[推奨** される情報] 領域に表示されます。 それ以外の場合は、表示されません。

<sup>2</sup> この分析情報はメール フロー ダッシュボードには表示されませんが、問題が検出された後、 [転送レポート](view-mail-flow-reports.md#forwarding-report) ページに表示されます。 それ以外の場合は、表示されません。

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>メール フロー ダッシュボードを表示するために必要なアクセス許可

メール フロー ダッシュボードは、次の役割グループのメンバーが利用できます。

- セキュリティ & コンプライアンス センターの **組織管理** (グローバル管理者)。

- **[Azure Active Directoryの管理者](/azure/active-directory/roles/permissions-reference#exchange-administrator)** Exchange。

- セキュリティ & コンプライアンス センターの **MailFlow 管理者**。 アカウントが組織管理またはExchange管理者ロール グループのメンバーでなければ、次の問題を考慮してください。
  - ユーザーは、セキュリティ & コンプライアンス センターに直接 <https://protection.office.com>サインインする必要があります。
  - ユーザーには、メール フロー ダッシュボードに対する読み取り専用アクセス許可のみが付与されます。
  - ユーザーはMicrosoft 365 管理センターにアクセスできません。

アクセス許可の詳細については、「 [セキュリティ & コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md) 」と「セキュリティ [& コンプライアンス センターへのアクセス権をユーザーに付与する](grant-access-to-the-security-and-compliance-center.md)」を参照してください。

## <a name="where-to-find-the-mail-flow-dashboard"></a>メール フロー ダッシュボードの場所

メール フロー ダッシュボードに直接移動するには、を開きます <https://protection.office.com/mailflow/dashboard>。
