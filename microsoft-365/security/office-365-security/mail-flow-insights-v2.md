---
title: メールフローダッシュボードのメールフローインサイト
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードで使用できる洞察およびレポートについて学習できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f9ac8b8b0d346d78af252a9e427d0ef2b1a4c4ea
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769020"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターのメール追跡の分析情報

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


管理者は、セキュリティ & コンプライアンスセンターのメールフローダッシュボードを使用して、組織内のメールフローに関連する問題を解決するための傾向、洞察、アクションの実行を検索できます。

![セキュリティ & コンプライアンスセンターのメールフローダッシュボード](../../media/mail-flow-dashboard-v2.png)

利用可能な洞察は次のとおりです。

- [自動転送されたメッセージの分析情報](mfi-auto-forwarded-messages-report.md)

- [使用可能なメールループの洞察](mfi-mail-loop-insight.md)<sup>1</sup>を修正する

- [低速メールフロールールの見通しを修正](mfi-slow-mail-flow-rules-insight.md)する<sup>1</sup>

- [メール フローのマップ](mfi-mail-flow-map-report.md)

- [転送される新しいドメインメールの洞察](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [新しいユーザーの転送メールの洞察](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [承認されていないドメインのレポート](mfi-non-accepted-domain-report.md)

- [配信不能レポート](mfi-non-delivery-report.md)

- [送信および受信メール フローのインサイト](mfi-outbound-and-inbound-mail-flow.md)

- [キューの分析情報](mfi-queue-alerts-and-queues.md)

- [SMTP Auth クライアントの分析情報とレポート](mfi-smtp-auth-clients-report.md)

- [トップドメインのメール フローの状態洞察](mfi-domain-mail-flow-status-insight.md)　

<sup>1</sup> この洞察は、問題が検出された後にのみ、メールフローダッシュボードの **お勧め** の領域に表示されます。 それ以外の場合は、表示されません。

<sup>2</sup> この洞察はメールフローダッシュボードには表示されませんが、問題が検出された後、 [転送レポート](view-mail-flow-reports.md#forwarding-report) ページに表示されます。 それ以外の場合は、表示されません。

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>メールフローダッシュボードを表示するために必要なアクセス許可

メールフローダッシュボードは、次の役割グループのメンバーが使用できます。

- セキュリティ & コンプライアンスセンター (グローバル管理者) での **組織の管理** 。

- Azure Active Directory の **[Exchange 管理者](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** 。

- セキュリティ & コンプライアンスセンターの **メールフロー管理者** : この役割グループのメンバーが全体管理者または Exchange 管理者の役割グループのメンバーでもない場合は、次の問題と要件を確認してください。

  - ユーザーは、セキュリティ & コンプライアンスセンターに直接ログインする必要があり <https://protection.office.com> ます。
  - ユーザーには、メールフローダッシュボードに対する読み取り専用アクセス許可のみが付与されます。
  - ユーザーは、Microsoft 365 管理センターへのアクセス権を持ちません。

セキュリティ & コンプライアンスセンターでのアクセス許可の詳細については、「 [セキュリティ & コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md) 」を参照し、 [セキュリティ & コンプライアンスセンターへのアクセス権をユーザーに付与](grant-access-to-the-security-and-compliance-center.md)します。

## <a name="where-to-find-the-mail-flow-dashboard"></a>メールフローダッシュボードの検索先

[セキュリティ & コンプライアンスセンター] <https://protection.office.com> を開き、[ **メールフロー** ] を展開して、[ **ダッシュボード** ] を選択します。

メールフローダッシュボードに直接移動するには、を開き <https://protection.office.com/mailflow/dashboard> ます。
