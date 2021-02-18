---
title: メール フロー ダッシュボードのメール フローの分析情報
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: 管理者は、セキュリティ/コンプライアンス センターのメール フロー ダッシュボードで利用できる分析情報&確認できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7432eca577fb264126b9fc8f10bdd83de32711cf
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289677"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>セキュリティ/コンプライアンス センターのメール追跡の分析情報

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードを使用して、傾向、分析情報を検出し、組織内のメール フローに関連する問題を解決するためのアクションを実行できます。

![セキュリティ/コンプライアンス センターのメール & ダッシュボード](../../media/mail-flow-dashboard-v2.png)

利用可能な分析情報は次のとおりです。

- [自動転送されたメッセージの分析情報](mfi-auto-forwarded-messages-report.md)

- [考えられるメール ループの分析情報](mfi-mail-loop-insight.md)<sup>を修正する 1</sup>

- [低速メール フロー ルールの分析情報](mfi-slow-mail-flow-rules-insight.md)<sup>を修正する 1</sup>

- [メール フローのマップ](mfi-mail-flow-map-report.md)

- [メールを転送する新しいドメインの分析](mfi-new-domains-being-forwarded-email.md)<sup>情報 2</sup>

- [新しいユーザーが電子メールの分析情報](mfi-new-users-forwarding-email.md)<sup>を転送する 2</sup>

- [承認されていないドメインのレポート](mfi-non-accepted-domain-report.md)

- [配信不能レポート](mfi-non-delivery-report.md)

- [送信および受信メール フローのインサイト](mfi-outbound-and-inbound-mail-flow.md)

- [キューの分析情報](mfi-queue-alerts-and-queues.md)

- [SMTP Auth クライアントの分析情報とレポート](mfi-smtp-auth-clients-report.md)

- [トップドメインのメール フローの状態洞察](mfi-domain-mail-flow-status-insight.md)　

<sup>1</sup>この分析情報は、問題が検出された後にのみ、メール フロー ダッシュボードの [推奨されるユーザー] 領域に表示されます。 それ以外の場合は、表示されます。

<sup>2</sup>この分析情報はメール フロー ダッシュボードには表示されませんが、問題が[](view-mail-flow-reports.md#forwarding-report)検出された後、[転送レポート] ページに表示されます。 それ以外の場合は、表示されます。

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>メール フロー ダッシュボードを表示するために必要なアクセス許可

メール フロー ダッシュボードは、次の役割グループのメンバーが使用できます。

- **セキュリティ/** コンプライアンス センター (&管理者) の組織の管理。

- **[Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** Active Directory の Exchange 管理者。

- **セキュリティ/コンプライアンス** センター& MailFlow 管理者。 アカウントが組織の管理役割グループまたは Exchange 管理者役割グループのメンバーではない場合は、次の問題を考慮してください。
  - ユーザーは、セキュリティ センターコンプライアンス センターに直接&する必要があります <https://protection.office.com> 。
  - ユーザーは、メール フロー ダッシュボードに対する読み取り専用アクセス許可のみを持つ必要があります。
  - ユーザーは Microsoft 365 管理センターにアクセスできない。

アクセス許可の詳細については、「セキュリティ/[](permissions-in-the-security-and-compliance-center.md)コンプライアンス センターのアクセス許可」および「セキュリティ/コンプライアンス センター&ユーザーにアクセス権を付与する[」を&してください](grant-access-to-the-security-and-compliance-center.md)。

## <a name="where-to-find-the-mail-flow-dashboard"></a>メール フロー ダッシュボードの場所

セキュリティ/コンプライアンス センター&開き、[メール フロー] を展開して、[ダッシュボード] <https://protection.office.com> を選択 **します**。 

メール フロー ダッシュボードに直接移動するには、開きます <https://protection.office.com/mailflow/dashboard> 。
