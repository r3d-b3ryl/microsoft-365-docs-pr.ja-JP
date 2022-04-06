---
title: メール フロー ダッシュボードのメール フローの分析情報
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
description: 管理者は、セキュリティ コンプライアンス センターのメール フロー ダッシュボードで利用可能な分析情報とレポート&できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b5cc3eba5807838b0a797f606d8a6aa3c152f60c
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476469"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センター のメール フロー インサイト

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードを使用して、傾向、分析情報を検出し、組織内のメール フローに関連する問題を解決するためのアクションを実行できます。

:::image type="content" source="../../media/mail-flow-dashboard-v2.png" alt-text="セキュリティ センターコンプライアンス センターのメール フロー ダッシュボード&ダッシュボード" lightbox="../../media/mail-flow-dashboard-v2.png":::

利用可能な分析情報は次のとおりです。

- [自動転送されたメッセージのインサイト](mfi-auto-forwarded-messages-report.md)

- [メール ループの分析情報を修正](mfi-mail-loop-insight.md)<sup>する1</sup>

- [低速メール フロー ルールの分析情報の修正](mfi-slow-mail-flow-rules-insight.md) <sup>1</sup>

- [メール フローのマップ](mfi-mail-flow-map-report.md)

- [転送される新しいドメインの電子メールの分析情報](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [新しいユーザーが電子メールの分析情報を転送](mfi-new-users-forwarding-email.md)<sup>する2</sup>

- [承認されていないドメインのレポート](mfi-non-accepted-domain-report.md)

- [配信不能レポート](mfi-non-delivery-report.md)

- [送信および受信メール フローのインサイト](mfi-outbound-and-inbound-mail-flow.md)

- [キューのインサイト](mfi-queue-alerts-and-queues.md)

- [SMTP Auth クライアントのインサイトとレポート](mfi-smtp-auth-clients-report.md)

- [トップドメインのメール フローの状態洞察](mfi-domain-mail-flow-status-insight.md)　

<sup>1</sup> この分析情報は、問題が検出された後にのみ、メール フロー ダッシュボードの [推奨されるユーザー] 領域に表示されます。 それ以外の場合は、表示されない。

<sup>2</sup> この分析情報はメール フロー ダッシュボードには表示されませんが、問題が検出された後、[[](view-mail-flow-reports.md#forwarding-report)転送レポート] ページに表示されます。 それ以外の場合は、表示されない。

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>メール フロー ダッシュボードを表示するために必要なアクセス許可

メール フロー ダッシュボードは、次の役割グループのメンバーが利用できます。

- **セキュリティ コンプライアンス センター** の組織&管理 (グローバル管理者)。

- **[Exchangeの管理者](/azure/active-directory/roles/permissions-reference#exchange-administrator)** Azure Active Directory。

- **コンプライアンス センターのセキュリティ & MailFlow** 管理者。 アカウントが組織の管理または管理者役割グループのメンバーでExchange場合は、次の問題を検討してください。
  - ユーザーは、コンプライアンス センターのセキュリティ &に直接サインインする必要があります <https://protection.office.com>。
  - ユーザーは、メール フロー ダッシュボードに対する読み取り専用のアクセス許可のみを持つ。
  - ユーザーはユーザーにアクセスMicrosoft 365 管理センター。

アクセス許可の詳細については、「Security [&](permissions-in-the-security-and-compliance-center.md) コンプライアンス センターのアクセス許可」および「セキュリティ コンプライアンス センターへのアクセス許可をユーザーに付与する& [参照してください](grant-access-to-the-security-and-compliance-center.md)。

## <a name="where-to-find-the-mail-flow-dashboard"></a>メール フロー ダッシュボードの場所

[セキュリティ とコンプライアンス センター&開き<https://protection.office.com>**、[メール フロー**] を展開し、[ダッシュボード] を **選択します**。

メール フロー ダッシュボードに直接移動するには、開きます <https://protection.office.com/mailflow/dashboard>。