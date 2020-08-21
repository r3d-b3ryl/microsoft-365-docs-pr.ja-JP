---
title: メール フロー ダッシュボードのメール フローの分析情報
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
description: 管理者は、セキュリティ/コンプライアンス センターのメール フロー ダッシュボードで使用できる分析情報やレポートについて&できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 06e9449553d008bc383ae6f2b6098f9598cad43c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826567"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センター のメール フロー インサイト

管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードを使用して、傾向、見つけ、および組織のメール フローに関連する問題を修正するためのアクションを実行できます。

![コンプライアンス センターのメール & フロー ダッシュボード](../../media/mail-flow-dashboard-v2.png)

使用可能な分析情報を次に示します。

- [自動転送されたメッセージのインサイト](mfi-auto-forwarded-messages-report.md)

- [メール ループの可能性についての分析情報 1 の](mfi-mail-loop-insight.md)<sup>修正</sup>

- [低速メール フローのルールを修正する](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [メール フローのマップ](mfi-mail-flow-map-report.md)

- [受信メールのインサイト 2 で転送される新しいドメイン](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [新しいユーザーがメールのインサイト 2 を転送](mfi-new-users-forwarding-email.md)<sup>する</sup>

- [承認されていないドメインのレポート](mfi-non-accepted-domain-report.md)

- [配信不能レポート](mfi-non-delivery-report.md)

- [送信および受信メール フローのインサイト](mfi-outbound-and-inbound-mail-flow.md)

- [キューのインサイト](mfi-queue-alerts-and-queues.md)

- [SMTP Auth クライアントのインサイトとレポート](mfi-smtp-auth-clients-report.md)

- [トップドメインのメール フローの状態洞察](mfi-domain-mail-flow-status-insight.md)　

<sup>1</sup>この分析情報は、問題が検出された**Recommended for you**後でのみ、[メール フロー] ダッシュボードの [推奨] 領域に表示されます。 そうしないと、表示されない。

<sup>2</sup> つの分析情報はメール フロー ダッシュボードには表示されませんが、問題が検出された後に [転送レポート](view-mail-flow-reports.md#forwarding-report) ページに表示されます。 そうしないと、表示されない。

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>メール フロー ダッシュボードを表示するために必要なアクセス許可

メール フロー ダッシュボードは、次のルート グループのメンバーが利用できます。

- **セキュリティ グループ** コンプライアンス センター (&での組織の管理)。

- Azure AD の**[Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** AD。

- セキュリティ & コンプライアンス センターの**MailFlow**管理者:この役割グループのメンバーが、グローバル管理者または Exchange 管理者役割グループのメンバーでもない場合は、次の問題と要件に注意してください。

  - ユーザーは、直下のセキュリティ 構成&にログインする必要があります <https://protection.office.com> 。
  - ユーザーは、メール フロー ダッシュボードへの読み取り専用アクセス許可のみを持つ必要があります。
  - ユーザーは、Microsoft 365 管理センターにアクセスできません。

セキュリティ コンプライアンス センターのアクセス許可の詳細については &、 [セキュリティ & コンプライアンス センターのアクセス許可を参照し、ユーザー](permissions-in-the-security-and-compliance-center.md) にセキュリティ コンプライアンス [センターへのアクセス&許可を付与します](grant-access-to-the-security-and-compliance-center.md)。

## <a name="where-to-find-the-mail-flow-dashboard"></a>メール フロー ダッシュボードの場所

セキュリティ センターの&、[メール フロー] <https://protection.office.com> を展開 **し、[** ダッシュボード] を選択 **します**。

メール フローのダッシュボードに直接移動するには、開きます <https://protection.office.com/mailflow/dashboard> 。
