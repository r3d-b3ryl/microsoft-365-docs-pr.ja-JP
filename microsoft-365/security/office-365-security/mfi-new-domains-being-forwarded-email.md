---
title: 新しいドメインにメールが転送されていますのインサイト
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: 管理者は、セキュリティ & コンプライアンス センターのメール フロー ダッシュボードで、転送される新しいドメインを使用して、転送されたことがない外部ドメインにメッセージを転送するユーザーを調査する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 98705d1f865886db91c8073188beaa0b3bc6b6da711839c0e43f6c81b1a7eae4
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "57002694"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>セキュリティ コンプライアンス センターで電子メールの分析情報を転送&ドメイン

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

特定のドメインの外部受信者に電子メール メッセージを転送するには、有効なビジネス上の理由があります。 ただし、組織内のユーザーが突然、組織内の誰もメッセージを (新しいドメイン) に転送したユーザーがいないドメインにメッセージを転送し始める場合、疑わしい場合があります。

この条件は、ユーザー アカウントが侵害された可能性があります。 アカウントが侵害された疑いがある場合は、「侵害されたメール アカウントに応答 [する」を参照してください](responding-to-a-compromised-email-account.md)。

セキュリティ **&** コンプライアンス センターでメールを転送する新しいドメインは、組織内 [の](https://protection.office.com) ユーザーが新しいドメインにメッセージを転送するときに通知します。

この分析情報は、問題が検出された場合にのみ表示され、[転送レポート] ページ [に表示](view-mail-flow-reports.md#forwarding-report) されます。

![新しいドメインにメールが転送されていますのインサイト](../../media/mfi-new-domains-being-forwarded.png)

ウィジェットをクリックすると、転送されたメッセージの詳細 (転送レポートへのリンクなど) を確認できるフライアウトが [表示されます](view-mail-flow-reports.md#forwarding-report)。

![[転送される新しいドメイン] をクリックした後に表示される詳細フライアウト](../../media/mfi-new-domains-being-forwarded-details.png)

[レポート ダッシュボード] または [ おすすめ] 領域の[トップ インサイト] 領域で [すべて表示] をクリックした後で&を選択すると、**この詳細** ページに \> **アクセス** することもできます <https://protection.office.com/insightdashboard> 。

外部ドメインへのメッセージの自動転送を防止するには、一部またはすべての外部ドメインにリモート ドメインを構成します。 詳細については、「リモート ドメインを[管理する」を参照Exchange Online。](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)

## <a name="related-topics"></a>関連項目

メール フロー ダッシュボードの他の分析情報の詳細については、「Security & コンプライアンス センター」 [を参照してください](mail-flow-insights-v2.md)。