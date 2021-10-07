---
title: メール フロー ダッシュボードのメール フローの分析情報
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 管理者は、セキュリティ コンプライアンス センターのメール フロー ダッシュボードで利用可能な分析情報とレポート&できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 81313744f8c5f14abed59b77182f64e410f9d588
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60180879"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センター のメール フロー インサイト

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードを使用して、傾向、分析情報を検出し、組織内のメール フローに関連する問題を解決するためのアクションを実行できます。

![セキュリティ センターのメール フロー ダッシュボード&センターです。](../../media/mail-flow-dashboard-v2.png)

利用可能な分析情報は次のとおりです。

- [自動転送されたメッセージのインサイト](mfi-auto-forwarded-messages-report.md)

- [メール ループの分析情報を修正](mfi-mail-loop-insight.md)<sup>する 1</sup>

- [低速メール フロー ルールの分析情報](mfi-slow-mail-flow-rules-insight.md)<sup>の修正 1</sup>

- [メール フローのマップ](mfi-mail-flow-map-report.md)

- [転送される新しいドメインの電子メール分析情報](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [新しいユーザーが電子メールの分析情報](mfi-new-users-forwarding-email.md)<sup>を転送する 2</sup>

- [承認されていないドメインのレポート](mfi-non-accepted-domain-report.md)

- [配信不能レポート](mfi-non-delivery-report.md)

- [送信および受信メール フローのインサイト](mfi-outbound-and-inbound-mail-flow.md)

- [キューのインサイト](mfi-queue-alerts-and-queues.md)

- [SMTP Auth クライアントのインサイトとレポート](mfi-smtp-auth-clients-report.md)

- [トップドメインのメール フローの状態洞察](mfi-domain-mail-flow-status-insight.md)　

<sup>1</sup>この分析情報は、問題が検出された後にのみ、メール フロー ダッシュボードの [推奨されるユーザー] 領域に表示されます。 それ以外の場合は、表示されない。

<sup>2</sup>この分析情報はメール フロー ダッシュボードには表示されませんが、問題が[](view-mail-flow-reports.md#forwarding-report)検出された後、[転送レポート] ページに表示されます。 それ以外の場合は、表示されない。

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>メール フロー ダッシュボードを表示するために必要なアクセス許可

メール フロー ダッシュボードは、次の役割グループのメンバーが利用できます。

- **コンプライアンス センター** (グローバル管理者) &の組織の管理。

- **[Exchangeの管理者](/azure/active-directory/roles/permissions-reference#exchange-administrator)** Azure Active Directory。

- **コンプライアンス センターの** セキュリティ & MailFlow 管理者。 アカウントが組織の管理または管理者役割グループのメンバーでExchange場合は、次の問題を検討してください。
  - ユーザーは、コンプライアンス センターのセキュリティ &に直接サインインする必要があります <https://protection.office.com> 。
  - ユーザーは、メール フロー ダッシュボードに対する読み取り専用のアクセス許可のみを持つ。
  - ユーザーはユーザーにアクセスMicrosoft 365 管理センター。

アクセス許可の詳細については、「Security [&](permissions-in-the-security-and-compliance-center.md) コンプライアンス センターのアクセス許可」および「セキュリティ コンプライアンス センターへのアクセス許可をユーザーに付与する」 [を参照&してください](grant-access-to-the-security-and-compliance-center.md)。

## <a name="where-to-find-the-mail-flow-dashboard"></a>メール フロー ダッシュボードの場所

[セキュリティ とコンプライアンス センター&開き、[メール フロー] を展開し、[ <https://protection.office.com> ダッシュボード] を **選択します**。

メール フロー ダッシュボードに直接移動するには、開きます <https://protection.office.com/mailflow/dashboard> 。